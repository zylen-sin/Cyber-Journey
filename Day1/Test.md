A. 觀念題
請分別解釋以下四者，不要只翻譯名稱：
Windows
WSL 2
Ubuntu
Terminal
它們之間是什麼關係？
1. Window: 微軟，他負責處理日常工作、遊戲...
   WSL 2:window subsystem for linux, 可以在window下建立如同linux 環境，方便我學習或工程操作。
   Ubuntu:Linux 的 一種系統名稱，以廣大社群資源聞名，適合我這種初學者
   Terminal:使用者介面(英文忘了)，是與operater與kernal互相交流的平台

下面三個位置有什麼不同？
Working directory
Staging area
Local repository
2. Working directory為terminal上自家使用者的folder
Staging area:是收集儲存台，可以到以後送到Local repository
Local repository:雲端的基地，放資料隨時可看，比較不受硬體影響

你修改 README.md 後，依序執行：
git add README.md
git commit -m "Update README" 
git push
請說明每個指令把什麼內容從哪裡送到哪裡。

3. :~/cyber-journey$ git add README.md
:~/cyber-journey$ git commit -m "Update README"
[main ee5ce08] Update README
 1 file changed, 10 insertions(+)
:~/cyber-journey$ git push
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 16 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 474 bytes | 474.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/zylen-sin/Cyber-Journey.git
   e13e754..ee5ce08  main -> main

git add -> 加入?追蹤
git commit -m -> 送至staging area
git push -> 送至github

解釋以下四個名稱：
main
origin
origin/main
upstream

4. main:主要git 的主線 與 branch戶對
後面不知道差異

第一次使用：
git push -u origin main
其中 -u 做了什麼？為什麼之後通常只要輸入 git push？
如果 git commit 成功，但網路斷線造成 git push 失敗：程式碼有沒有消失？
Commit 存在哪裡？
GitHub 上看得到嗎？
網路恢復後應該怎麼做？
5.-u使電腦連結成功(應該吧) 所以以後有記憶就不用了。git push失敗，沒消失還在staging area，github看不到。


如果 git status 顯示：
nothing to commit, working tree clean
是否能證明 GitHub 已經擁有最新 commit？為什麼？
GitHub CLI 的 gh auth login 與下面這項設定是否相同？各自負責什麼？
git config --global user.name "zylen"

6. 如果確定存檔了通常是，不過有合作者可能要git pull。設定不同，一個負責與雲端連線授權，另個是設定你要上傳的使用名稱

B. 實際操作題
在你的 cyber-journey Repository 內完成。不要直接複製整段，逐步操作並觀察每一步。
1. 確認所在環境
執行：
pwd
whoami
uname -a
git status
回答：
你目前在哪個目錄？
使用者是誰？
哪個結果證明目前處於 Linux／WSL？
Git 是否辨識這個 Repository？
zylen@Zylen:~/cyber-journey$ pwd
/home/zylen/cyber-journey
zylen@Zylen:~/cyber-journey$ whoami
zylen
zylen@Zylen:~/cyber-journey$ uname -a
Linux Zylen 6.18.33.2-microsoft-standard-WSL2 #1 SMP PREEMPT_DYNAMIC Thu Jun 18 21:54:43 UTC 2026 x86_64 GNU/Linux
zylen@Zylen:~/cyber-journey$ git status
On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        Day1/

nothing added to commit but untracked files present (use "git add" to track)

1. 目前在/home/zylen/cyber-journey、zylen、 6.18.33.2-microsoft-standard-WSL2、可以origin/main

2. 建立驗收紀錄
建立：
git status
最後先不要急著 push，執行：
git log --oneline -3
git branch -vv
觀察本機分支是否比遠端分支領先。
最後才執行：
git push
git status
git branch -vv
4. 提交結果
回覆我以下內容：
A1～A8 的答案

pwd：
git status 最終結果：
git log --oneline -3：
git branch -vv：

兩次 git status 有什麼差別：
push 前後 git branch -vv 有什麼變化：

labs/day-01-checkpoint/answers.md
內容用自己的話寫三項：
What I learned
What confused me
How local Git connects to GitHub
可以用 VS Code 建立，不必強迫自己用終端機文字編輯器。
3. 觀察 Git 的三種狀態
新增檔案後先執行：
git status
接著執行：
git add labs/day-01-checkpoint/answers.md
git status
比較兩次輸出：檔案從哪一種狀態變成哪一種狀態？
然後執行：
git commit -m "Complete day 1 checkpoint"