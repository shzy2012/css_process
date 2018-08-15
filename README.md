# CSS 流程进度条

HTML
```html
<div class="container">
  <ul id="step-horizontal">
    <li class="active"><div></div><h3>退货申请</h3><h6>2018-03-02 18:00:10</h6></li>
    <li><div></div><h3>申请处理</h3><h6>2018-03-05(估计)</h6></li>
    <li><div></div><h3>退货成功</h3><h6></h6></li>
  </ul>
</div>
```
CSS
```css
.container{
  margin-top:10rem;
}

#step-horizontal {
  list-style-type: none;
  max-width: 60%;
  padding: 0px;
  margin: 0px;
  position: relative;
}
#step-horizontal li {
  float: left;
  position: relative;
  text-align: center;
  width: 30%;
}
#step-horizontal .active::after {
  position: absolute;
  top: 0rem;
  z-index: -1;
  width: 100%;
  height: 0.13rem;
  content: "";
  -webkit-transform: translate(0, -50%);
  transform: translate(0, -50%);
  background-color: #dda75c;
}
#step-horizontal li:not(.active)::after {
  position: absolute;
  top: 0rem;
  z-index: -1;
  width: 100%;
  height: 0.13rem;
  content: "";
  -webkit-transform: translate(0, -50%);
  transform: translate(0, -50%);
  background-color: #c9c8c6;
}
#step-horizontal li:last-child::after {
  position: absolute;
  top: 0rem;
  z-index: -1;
  width: 0px;
  content: "";
}
#step-horizontal li div::before {
  position: absolute;
  top: -0.5rem;
  left: 47%;
  width: 12px;
  height: 12px;
  border: solid 0.13rem #dda75c;
  background-color: #fff;
  border-radius: 50%;
  -moz-border-radius: 50%;
  -webkit-border-radius: 50%;
  content: '';
}
#step-horizontal li:not(.active) div::before {
  position: absolute;
  top: -0.5rem;
  left: 47%;
  width: 12px;
  height: 12px;
  border: solid 0.13rem #c9c8c6;
  background-color: #fff;
  border-radius: 50%;
  -moz-border-radius: 50%;
  -webkit-border-radius: 50%;
  content: '';
}
#step-horizontal li h3 {
  margin-top: -2rem;
}
#step-horizontal li h6 {
  margin-top: 1.5rem;
}
```
