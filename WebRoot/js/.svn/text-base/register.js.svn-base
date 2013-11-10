var locMark;
var init = function() {

	var center = new QQMap.QLatLng(39.920, 116.405);

	var map = new QQMap.QMap(document.getElementById("container"), {
		center : center,
		zoomLevel : 13
	});
	
    var navControl = new QQMap.QNavigationControl({
        align: QQMap.QALIGN.TOP_RIGHT,
        margin: new QQMap.QSize(5, 15),
        map: map
    });

   var scaleControl = new QQMap.QScaleControl({
	   align: QQMap.QALIGN.BOTTOM_RIGHT,
	   margin: new QQMap.QSize(85, 15),
	   map: map
    });
	
	var icon = new QQMap.QMarkerImage('images/marker.png');
	locMark = new QQMap.QMarker( {
		icon: icon,
		draggable : true,
	});

	QQMap.QEvent.addListener(map, 'click', function(event) {
		locMark.setPosition(event.qLatLng);
		locMark.setMap(map);		
	});
}

eamilCheck = function (emailStr) {
	var emailPat = /^(.+)@(.+)$/;
	var matchArray = emailStr.match(emailPat);
	if (matchArray == null) {
		return false;
	}
	return true;
}

telCheck = function isTel(telStr){
    var reg=/^([0-9]|[\-])+$/g ;
    if(telStr.length<7 || telStr.length>18){
    	return false;
    }
    else{
      return reg.exec(str);
    }
}

isValid = function(myForm) {
	
	if(locMark.getPosition() == null) {
		alert("请在地图上选定你的位置！");
		return false;
	}
	
	if(document.getElementById('UserAction_user_username').value.trim()==""){
		alert("用户名不能为空！");
		return false;
	}
	
	if(document.getElementById('UserAction_user_pwd').value.trim()==""){
		alert("密码不能为空！");
		return false;
	}
	
	if(eamilCheck(document.getElementById('UserAction_user_email').value) == false)
	{
		alert("邮件地址格式不正确！");
		return false;
	}
	
	if(telCheck(document.getElementById('UserAction_user_phone').value) == false)
	{
		alert("电话号码格式不正确！");
		return false;
	}
	
	if(document.getElementById('UserAction_user_address').value == null){
		alert("地址不能为空！");
		return false;
	}
	
	var latLng = locMark.getPosition();
	document.getElementById('UserAction_r_lat').value = latLng.getLat();
	document.getElementById('UserAction_r_lon').value = latLng.getLng();
	return true;
}
