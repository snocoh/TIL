参考  
> https://qiita.com/H-Iida/items/ee74ee8c5bd0a994edfd  
> https://qiita.com/jnchito/items/cdd9eef2ed193267c651  
  
  
# 今までインスタンス変数を使用していたけど「let」ってなに？？  
これまで↓↓↓  
```
  before do
    @user = FactoryBot.build(:user)
  end
 ```  
 letを使う方法↓↓↓
 ```
  let(:user) { FactoryBot.build(:user) }
 ```  
   
   
 # letを使用するメリット
 **1. typo（タイプミス）にすぐ気が付ける**  
 letはメソッドを作るためtypoするとNameErrorが発生する。  
 
 **2. 各exampleに必要なメソッドだけを呼び出して、無駄な初期化処理を減らせる。**  
 メソッドが呼ばれた時だけ初期化処理がなされる  
 
 **3. ローカル変数をそのままletに置き換えられる**  
 example内でローカル変数を使っている場合、そのまま変えなくて済むよという話。  
 
 **4. コードが見やすくなる**  
 主観的な話。  
 
 ### 感想
 実際のメリットとしては1と2になる。あまり技巧的になると却って見にくくなる、と翻訳元の執筆者も言っているため自分の理解度と見やすさを鑑みて使用してみたい。
