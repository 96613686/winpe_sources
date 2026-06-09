# RdpAutoTrace::Initialize(void)

- ea: `0x1800619a8`
- end: `0x180061f96`
- name: `?Initialize@RdpAutoTrace@@QEAAJXZ`
- size: `1518`
- prototype: `__int64 __fastcall(RdpAutoTrace *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800422e0`
- `0x180065850`

## callees

- `0x1800091a8`
- `0x18002e600`
- `0x180033da0`
- `0x180034970`
- `0x1800619a8`
- `0x180078208`
- `0x18014d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180061def`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180061def`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061f73`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061f73`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180061d5d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180061d5d`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180061dd0`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180061dd0`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180061e2c`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180061e2c`

## string_xrefs

- `0x180061e93`: `CWppAutoTrace_CreateInstance`
- `0x180061ed4`: `%SystemRoot%\ServiceProfiles\NetworkService\AppData\Local\AutoTrace\Transfer`
- `0x180061ee0`: `%SystemRoot%\ServiceProfiles\NetworkService\AppData\Local\AutoTrace\Capture`
- `0x180061f29`: `IWppAutoTrace::SetConfiguration() failed`

## pseudocode

```c
__int64 __fastcall RdpAutoTrace::Initialize(RdpAutoTrace *this)
{
  signed int v1; // ebx
  __int64 v3; // rdi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v5; // edx
  const char *v6; // rcx
  struct IWppAutoTrace *v7; // rcx
  struct IWppAutoTrace *v8; // rcx
  LPDWORD lpType; // [rsp+28h] [rbp-D8h]
  struct IWppAutoTrace *v11; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchValueName; // [rsp+48h] [rbp-B8h] BYREF
  DWORD Type; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  GUID iid; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v17[2]; // [rsp+70h] [rbp-90h] BYREF
  int v18; // [rsp+80h] [rbp-80h]
  int v19; // [rsp+84h] [rbp-7Ch]
  int v20; // [rsp+88h] [rbp-78h]
  int v21; // [rsp+8Ch] [rbp-74h]
  int v22; // [rsp+90h] [rbp-70h]
  int v23; // [rsp+94h] [rbp-6Ch]
  int v24; // [rsp+98h] [rbp-68h]
  int v25; // [rsp+9Ch] [rbp-64h]
  int v26; // [rsp+A0h] [rbp-60h]
  int v27; // [rsp+A4h] [rbp-5Ch]
  int v28; // [rsp+A8h] [rbp-58h]
  int v29; // [rsp+ACh] [rbp-54h]
  int v30; // [rsp+B0h] [rbp-50h]
  int v31; // [rsp+B4h] [rbp-4Ch]
  int v32; // [rsp+B8h] [rbp-48h]
  int v33; // [rsp+BCh] [rbp-44h]
  int v34; // [rsp+C0h] [rbp-40h]
  int v35; // [rsp+C4h] [rbp-3Ch]
  int v36; // [rsp+C8h] [rbp-38h]
  int v37; // [rsp+CCh] [rbp-34h]
  int v38; // [rsp+D0h] [rbp-30h]
  int v39; // [rsp+D4h] [rbp-2Ch]
  int v40; // [rsp+D8h] [rbp-28h]
  int v41; // [rsp+DCh] [rbp-24h]
  int v42; // [rsp+E0h] [rbp-20h]
  int v43; // [rsp+E4h] [rbp-1Ch]
  int v44; // [rsp+E8h] [rbp-18h]
  int v45; // [rsp+ECh] [rbp-14h]
  int v46; // [rsp+F0h] [rbp-10h]
  int v47; // [rsp+F4h] [rbp-Ch]
  int v48; // [rsp+F8h] [rbp-8h]
  int v49; // [rsp+FCh] [rbp-4h]
  int v50; // [rsp+100h] [rbp+0h]
  int v51; // [rsp+104h] [rbp+4h]
  int v52; // [rsp+108h] [rbp+8h]
  int v53; // [rsp+10Ch] [rbp+Ch]
  int v54; // [rsp+110h] [rbp+10h]
  int v55; // [rsp+114h] [rbp+14h]
  int v56; // [rsp+118h] [rbp+18h]
  int v57; // [rsp+11Ch] [rbp+1Ch]
  int v58; // [rsp+120h] [rbp+20h]
  int v59; // [rsp+124h] [rbp+24h]
  int v60; // [rsp+128h] [rbp+28h]
  int v61; // [rsp+12Ch] [rbp+2Ch]
  int v62; // [rsp+130h] [rbp+30h]
  int v63; // [rsp+134h] [rbp+34h]
  int v64; // [rsp+138h] [rbp+38h]
  int v65; // [rsp+13Ch] [rbp+3Ch]
  int v66; // [rsp+140h] [rbp+40h]
  int v67; // [rsp+144h] [rbp+44h]
  int v68; // [rsp+148h] [rbp+48h]
  int v69; // [rsp+14Ch] [rbp+4Ch]
  int v70; // [rsp+150h] [rbp+50h]
  int v71; // [rsp+154h] [rbp+54h]
  int v72; // [rsp+158h] [rbp+58h]
  int v73; // [rsp+15Ch] [rbp+5Ch]
  int v74; // [rsp+160h] [rbp+60h]
  int v75; // [rsp+164h] [rbp+64h]
  int v76; // [rsp+168h] [rbp+68h]
  int v77; // [rsp+16Ch] [rbp+6Ch]
  int v78; // [rsp+170h] [rbp+70h]
  int v79; // [rsp+174h] [rbp+74h]
  int v80; // [rsp+178h] [rbp+78h]
  int v81; // [rsp+17Ch] [rbp+7Ch]
  int v82; // [rsp+180h] [rbp+80h]
  int v83; // [rsp+184h] [rbp+84h]
  int v84; // [rsp+188h] [rbp+88h]
  int v85; // [rsp+18Ch] [rbp+8Ch]
  int v86; // [rsp+190h] [rbp+90h]
  int v87; // [rsp+194h] [rbp+94h]
  int v88; // [rsp+198h] [rbp+98h]
  int v89; // [rsp+19Ch] [rbp+9Ch]
  int v90; // [rsp+1A0h] [rbp+A0h]
  int v91; // [rsp+1A4h] [rbp+A4h]
  int v92; // [rsp+1A8h] [rbp+A8h]
  int v93; // [rsp+1ACh] [rbp+ACh]
  int v94; // [rsp+1B0h] [rbp+B0h]
  int v95; // [rsp+1B4h] [rbp+B4h]
  int v96; // [rsp+1B8h] [rbp+B8h]
  int v97; // [rsp+1BCh] [rbp+BCh]
  int v98; // [rsp+1C0h] [rbp+C0h]
  int v99; // [rsp+1C4h] [rbp+C4h]
  int v100; // [rsp+1C8h] [rbp+C8h]
  int v101; // [rsp+1CCh] [rbp+CCh]
  int v102; // [rsp+1D0h] [rbp+D0h]
  int v103; // [rsp+1D4h] [rbp+D4h]
  int v104; // [rsp+1D8h] [rbp+D8h]
  int v105; // [rsp+1DCh] [rbp+DCh]
  int v106; // [rsp+1E0h] [rbp+E0h]
  int v107; // [rsp+1E4h] [rbp+E4h]
  int v108; // [rsp+1E8h] [rbp+E8h]
  int v109; // [rsp+1ECh] [rbp+ECh]
  int v110; // [rsp+1F0h] [rbp+F0h]
  int v111; // [rsp+1F4h] [rbp+F4h]
  int v112; // [rsp+1F8h] [rbp+F8h]
  int v113; // [rsp+1FCh] [rbp+FCh]
  int v114; // [rsp+200h] [rbp+100h]
  int v115; // [rsp+204h] [rbp+104h]
  int v116; // [rsp+208h] [rbp+108h]
  int v117; // [rsp+20Ch] [rbp+10Ch]
  _BYTE v118[96]; // [rsp+210h] [rbp+110h] BYREF
  WCHAR ValueName[16]; // [rsp+270h] [rbp+170h] BYREF
  OLECHAR Data[38]; // [rsp+290h] [rbp+190h] BYREF
  __int16 v121; // [rsp+2DCh] [rbp+1DCh]

  v1 = 0;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  if ( *(_QWORD *)this )
    return (unsigned int)v1;
  v11 = 0;
  v82 = -736520635;
  v86 = -736520635;
  v90 = -736520635;
  v17[0] = 0x43F9F60D140C2428LL;
  v17[1] = 0xA03824625F3E079BuLL;
  v18 = 1010725001;
  v19 = 1145477583;
  v20 = -984972915;
  v21 = 1779324584;
  v22 = 1014187365;
  v23 = 1097367771;
  v24 = 1404114571;
  v25 = 1766790547;
  v26 = 1151225449;
  v27 = 1320235678;
  v28 = -1652498531;
  v29 = -1042243049;
  v30 = 1384371702;
  v31 = 1113548213;
  v32 = 1827736483;
  v33 = 1466662149;
  v34 = 1434264955;
  v35 = 1252923406;
  v36 = -997849457;
  v37 = 10317540;
  v38 = 1507734941;
  v39 = 1146940547;
  v40 = 1589060499;
  v41 = -1512745440;
  v42 = 1942350921;
  v43 = 1218299911;
  v44 = 1842562462;
  v45 = -2074139790;
  v46 = 2037325898;
  v47 = 1205814524;
  v48 = -1032330102;
  v49 = -195379952;
  v50 = -1746306530;
  v51 = 1267581097;
  v52 = 272811143;
  v53 = 2071827802;
  v54 = -1737701096;
  v55 = 1336636468;
  v56 = -1161527373;
  v57 = -1813851782;
  v58 = -1633549553;
  v59 = 1206901606;
  v60 = -1671353153;
  v61 = 457076679;
  v62 = -1630066748;
  v63 = 1264994998;
  v64 = 1914754962;
  v65 = 613514472;
  v66 = -1079618084;
  v67 = 299527249;
  v68 = 1811340939;
  v69 = 977215149;
  v70 = -1054359128;
  v71 = 299527403;
  v72 = 1811340939;
  v73 = 977215149;
  v74 = -983474726;
  v75 = 1201352108;
  v76 = -1930318973;
  v77 = 1947689109;
  v78 = -750889889;
  v79 = 1111448003;
  v80 = -999468656;
  v81 = -1466748008;
  v83 = 1339376062;
  v84 = 312897949;
  v85 = -956495675;
  v87 = 1339376062;
  v88 = 312897949;
  v89 = -939718459;
  v91 = 1339376062;
  v92 = 312898461;
  v93 = -956495675;
  v94 = -732863444;
  v95 = 299328422;
  v96 = -1342168937;
  v97 = 1191395024;
  v98 = -344708875;
  v99 = 1126345503;
  v100 = 438291620;
  v101 = -1738658661;
  v102 = -495365909;
  v103 = 1159665512;
  v104 = 1322036374;
  v105 = -791415276;
  v106 = 1519807772;
  v107 = 299526984;
  v108 = 1811340939;
  v109 = 977215149;
  v110 = 534037929;
  v111 = 1099638711;
  v112 = 1847721101;
  v113 = -1866881153;
  v114 = -1080857700;
  v115 = 1150605893;
  v116 = 521156258;
  v117 = 497394405;
  memset_0(v118, 0, sizeof(v118));
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Terminal Server\\AutoTrace\\Providers",
          0,
          0x20019u,
          &hKey) )
  {
    while ( (unsigned int)v1 < 0x20 )
    {
      cchValueName = 10;
      Type = 0;
      cbData = 78;
      iid = 0;
      if ( RegEnumValueW(hKey, v1, ValueName, &cchValueName, 0, &Type, (LPBYTE)Data, &cbData) )
        break;
      ValueName[9] = 0;
      v121 = 0;
      v3 = (int)_o__wtoi(ValueName);
      if ( cchValueName - 1 > 1
        || (unsigned __int16)(ValueName[0] - 48) > 9u
        || Type != 1
        || (unsigned int)v3 >= 0x20
        || IIDFromString(Data, &iid) < 0 )
      {
        break;
      }
      ++v1;
      *(GUID *)&v17[2 * v3] = iid;
    }
  }
  v1 = CWppAutoTrace_CreateInstance(&v11);
  if ( v1 >= 0 )
  {
    LODWORD(lpType) = 32;
    v1 = (*(__int64 (**)(struct IWppAutoTrace *, const wchar_t *, const wchar_t *, ...))(*(_QWORD *)v11 + 24LL))(
           v11,
           L"RdpCoreTS",
           L"%SystemRoot%\\ServiceProfiles\\NetworkService\\AppData\\Local\\AutoTrace\\Capture",
           L"%SystemRoot%\\ServiceProfiles\\NetworkService\\AppData\\Local\\AutoTrace\\Transfer",
           v17,
           lpType);
    if ( v1 >= 0 )
    {
      v7 = v11;
      *(_QWORD *)this = v11;
      (*(void (__fastcall **)(struct IWppAutoTrace *))(*(_QWORD *)v7 + 8LL))(v7);
      goto LABEL_23;
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_23;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 11;
    v6 = "IWppAutoTrace::SetConfiguration() failed";
  }
  else
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_23;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 10;
    v6 = "CWppAutoTrace_CreateInstance";
  }
  LODWORD(lpType) = v1;
  WPP_SF_DsD(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    v5,
    (unsigned int)WPP_6d9dc437661839af64978a47ef12cc9c_Traceguids,
    CurrentThreadActivityIdPrefix,
    (__int64)v6,
    lpType);
LABEL_23:
  v8 = v11;
  if ( v11 )
  {
    v11 = 0;
    (*(void (__fastcall **)(struct IWppAutoTrace *))(*(_QWORD *)v8 + 16LL))(v8);
  }
  if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(hKey);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800619a8  push    rbp
0x1800619aa  push    rbx
0x1800619ab  push    rsi
0x1800619ac  push    rdi
0x1800619ad  lea     rbp, [rsp-1F8h]
0x1800619b5  sub     rsp, 2F8h
0x1800619bc  mov     rax, cs:__security_cookie
0x1800619c3  xor     rax, rsp
0x1800619c6  mov     [rbp+210h+var_30], rax
0x1800619cd  xor     ebx, ebx
0x1800619cf  mov     [rsp+310h+hKey], 0FFFFFFFFFFFFFFFFh
0x1800619d8  mov     rsi, rcx
0x1800619db  cmp     [rcx], rbx
0x1800619de  jnz     loc_180061F79
0x1800619e4  mov     ecx, 0D4199645h
0x1800619e9  mov     [rsp+310h+var_2D0], rbx
0x1800619ee  mov     [rbp+210h+var_190], ecx
0x1800619f4  mov     [rbp+210h+var_180], ecx
0x1800619fa  mov     [rbp+210h+var_170], ecx
0x180061a00  mov     dword ptr [rsp+310h+var_2A0], 140C2428h
0x180061a08  mov     dword ptr [rsp+310h+var_2A0+4], 43F9F60Dh
0x180061a10  mov     dword ptr [rsp+310h+var_2A0+8], 5F3E079Bh
0x180061a18  mov     dword ptr [rsp+310h+var_2A0+0Ch], 0A0382462h
0x180061a20  mov     [rbp+210h+var_290], 3C3E7089h
0x180061a27  mov     [rbp+210h+var_28C], 444699CFh
0x180061a2e  mov     [rbp+210h+var_288], 0C54A818Dh
0x180061a35  mov     [rbp+210h+var_284], 6A0E56A8h
0x180061a3c  mov     [rbp+210h+var_280], 3C734565h
0x180061a43  mov     [rbp+210h+var_27C], 416880DBh
0x180061a4a  mov     [rbp+210h+var_278], 53B1168Bh
0x180061a51  mov     [rbp+210h+var_274], 694F1593h
0x180061a58  mov     [rbp+210h+var_270], 449E4E69h
0x180061a5f  mov     [rbp+210h+var_26C], 4EB1329Eh
0x180061a66  mov     [rbp+210h+var_268], 9D80DF9Dh
0x180061a6d  mov     [rbp+210h+var_264], 0C1E0A217h
0x180061a74  mov     [rbp+210h+var_260], 5283D5F6h
0x180061a7b  mov     [rbp+210h+var_25C], 425F65B5h
0x180061a82  mov     [rbp+210h+var_258], 6CF10BA3h
0x180061a89  mov     [rbp+210h+var_254], 576B7D05h
0x180061a90  mov     [rbp+210h+var_250], 557D257Bh
0x180061a97  mov     [rbp+210h+var_24C], 4AAE180Eh
0x180061a9e  mov     [rbp+210h+var_248], 0C486068Fh
0x180061aa5  mov     [rbp+210h+var_244], 9D6EE4h
0x180061aac  mov     [rbp+210h+var_240], 59DE359Dh
0x180061ab3  mov     [rbp+210h+var_23C], 445CEC83h
0x180061aba  mov     [rbp+210h+var_238], 5EB72393h
0x180061ac1  mov     [rbp+210h+var_234], 0A5D55620h
0x180061ac8  mov     [rbp+210h+var_230], 73C5EC49h
0x180061acf  mov     [rbp+210h+var_22C], 489DC807h
0x180061ad6  mov     [rbp+210h+var_228], 6DD3459Eh
0x180061add  mov     [rbp+210h+var_224], 845F2372h
0x180061ae4  mov     [rbp+210h+var_220], 796F204Ah
0x180061aeb  mov     [rbp+210h+var_21C], 47DF44FCh
0x180061af2  mov     [rbp+210h+var_218], 0C277E48Ah
0x180061af9  mov     [rbp+210h+var_214], 0F45ABD10h
0x180061b00  mov     [rbp+210h+var_210], 97E97A1Eh
0x180061b07  mov     [rbp+210h+var_20C], 4B8DC0A9h
0x180061b0e  mov     [rbp+210h+var_208], 1042C487h
0x180061b15  mov     [rbp+210h+var_204], 7B7D955Ah
0x180061b1c  mov     [rbp+210h+var_200], 986CC918h
0x180061b23  mov     [rbp+210h+var_1FC], 4FAB7434h
0x180061b2a  mov     [rbp+210h+var_1F8], 0BAC47FB3h
0x180061b31  mov     [rbp+210h+var_1F4], 93E2D17Ah
0x180061b38  mov     [rbp+210h+var_1F0], 9EA2030Fh
0x180061b3f  mov     [rbp+210h+var_1EC], 47EFDB66h
0x180061b46  mov     [rbp+210h+var_1E8], 9C612CBFh
0x180061b4d  mov     [rbp+210h+var_1E4], 1B3E6FC7h
0x180061b54  mov     [rbp+210h+var_1E0], 9ED727C4h
0x180061b5b  mov     [rbp+210h+var_1DC], 4B664AB6h
0x180061b62  mov     [rbp+210h+var_1D8], 7220D792h
0x180061b69  mov     [rbp+210h+var_1D4], 24917CE8h
0x180061b70  mov     [rbp+210h+var_1D0], 0BFA655DCh
0x180061b77  mov     [rbp+210h+var_1CC], 11DA6C51h
0x180061b7e  mov     [rbp+210h+var_1C8], 6BF6DE8Bh
0x180061b85  mov     [rbp+210h+var_1C4], 3A3F1EADh
0x180061b8c  mov     [rbp+210h+var_1C0], 0C127C1A8h
0x180061b93  mov     [rbp+210h+var_1BC], 11DA6CEBh
0x180061b9a  mov     [rbp+210h+var_1B8], 6BF6DE8Bh
0x180061ba1  mov     [rbp+210h+var_1B4], 3A3F1EADh
0x180061ba8  mov     [rbp+210h+var_1B0], 0C5615DDAh
0x180061baf  mov     [rbp+210h+var_1AC], 479B2DACh
0x180061bb6  mov     [rbp+210h+var_1A8], 8CF1AB83h
0x180061bbd  mov     [rbp+210h+var_1A4], 74176095h
0x180061bc4  mov     [rbp+210h+var_1A0], 0D33E545Fh
0x180061bcb  mov     [rbp+210h+var_19C], 423F59C3h
0x180061bd2  mov     [rbp+210h+var_198], 0C46D5190h
0x180061bd9  mov     [rbp+210h+var_194], 0A8933398h
0x180061be0  mov     [rbp+210h+var_18C], 4FD541BEh
0x180061bea  mov     [rbp+210h+var_188], 12A6719Dh
0x180061bf4  mov     [rbp+210h+var_184], 0C6FD08C5h
0x180061bfe  mov     [rbp+210h+var_17C], 4FD541BEh
0x180061c08  mov     [rbp+210h+var_178], 12A6719Dh
0x180061c12  mov     [rbp+210h+var_174], 0C7FD08C5h
0x180061c1c  mov     [rbp+210h+var_16C], 4FD541BEh
0x180061c26  mov     [rbp+210h+var_168], 12A6739Dh
0x180061c30  xor     edx, edx; Val
0x180061c32  mov     [rbp+210h+var_164], 0C6FD08C5h
0x180061c3c  lea     r8d, [rbx+60h]; Size
0x180061c40  mov     [rbp+210h+var_160], 0D451642Ch
0x180061c4a  lea     rcx, [rbp+210h+var_100]; void *
0x180061c51  mov     [rbp+210h+var_15C], 11D763A6h
0x180061c5b  mov     [rbp+210h+var_158], 0B0002097h
0x180061c65  mov     [rbp+210h+var_154], 47033ED0h
0x180061c6f  mov     [rbp+210h+var_150], 0EB7428F5h
0x180061c79  mov     [rbp+210h+var_14C], 4322AB1Fh
0x180061c83  mov     [rbp+210h+var_148], 1A1FCCA4h
0x180061c8d  mov     [rbp+210h+var_144], 985E2C9Bh
0x180061c97  mov     [rbp+210h+var_140], 0E27950EBh
0x180061ca1  mov     [rbp+210h+var_13C], 451F1768h
0x180061cab  mov     [rbp+210h+var_138], 4ECCAC96h
0x180061cb5  mov     [rbp+210h+var_134], 0D0D3F614h
0x180061cbf  mov     [rbp+210h+var_130], 5A966D1Ch
0x180061cc9  mov     [rbp+210h+var_12C], 11DA6B48h
0x180061cd3  mov     [rbp+210h+var_128], 6BF6DE8Bh
0x180061cdd  mov     [rbp+210h+var_124], 3A3F1EADh
0x180061ce7  mov     [rbp+210h+var_120], 1FD4C5A9h
0x180061cf1  mov     [rbp+210h+var_11C], 418B27B7h
0x180061cfb  mov     [rbp+210h+var_118], 6E21FC8Dh
0x180061d05  mov     [rbp+210h+var_114], 90B9A77Fh
0x180061d0f  mov     [rbp+210h+var_110], 0BF936B9Ch
0x180061d19  mov     [rbp+210h+var_10C], 4494DA45h
0x180061d23  mov     [rbp+210h+var_108], 1F1036A2h
0x180061d2d  mov     [rbp+210h+var_104], 1DA5A2E5h
0x180061d37  call    memset_0
0x180061d3c  lea     rax, [rsp+310h+hKey]
0x180061d41  mov     r9d, 20019h; samDesired
0x180061d47  xor     r8d, r8d; ulOptions
0x180061d4a  mov     [rsp+310h+phkResult], rax; phkResult
0x180061d4f  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows NT\\Curren"...
0x180061d56  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180061d5d  call    cs:__imp_RegOpenKeyExW
0x180061d63  test    eax, eax
0x180061d65  jnz     loc_180061E4E
0x180061d6b  cmp     ebx, 20h ; ' '
0x180061d6e  jnb     loc_180061E4E
0x180061d74  mov     rcx, [rsp+310h+hKey]; hKey
0x180061d79  lea     rax, [rsp+310h+cbData]
0x180061d7e  mov     [rsp+310h+lpcbData], rax; lpcbData
0x180061d83  lea     r9, [rsp+310h+cchValueName]; lpcchValueName
0x180061d88  lea     rax, [rbp+210h+Data]
0x180061d8f  mov     [rsp+310h+cchValueName], 0Ah
0x180061d97  mov     [rsp+310h+lpData], rax; lpData
0x180061d9c  lea     r8, [rbp+210h+ValueName]; lpValueName
0x180061da3  lea     rax, [rsp+310h+Type]
0x180061da8  mov     [rsp+310h+Type], 0
0x180061db0  xorps   xmm0, xmm0
0x180061db3  mov     [rsp+310h+lpType], rax; lpType
0x180061db8  mov     edx, ebx; dwIndex
0x180061dba  mov     [rsp+310h+phkResult], 0; lpReserved
0x180061dc3  mov     [rsp+310h+cbData], 4Eh ; 'N'
0x180061dcb  movups  xmmword ptr [rsp+310h+iid.Data1], xmm0
0x180061dd0  call    cs:__imp_RegEnumValueW
0x180061dd6  test    eax, eax
0x180061dd8  jnz     short loc_180061E4E
0x180061dda  lea     rcx, [rbp+210h+ValueName]
0x180061de1  mov     [rbp+210h+var_8E], ax
0x180061de8  mov     [rbp+210h+var_34], ax
0x180061def  call    cs:__imp__o__wtoi
0x180061df5  movsxd  rdi, eax
0x180061df8  mov     eax, [rsp+310h+cchValueName]
0x180061dfc  dec     eax
0x180061dfe  cmp     eax, 1
0x180061e01  ja      short loc_180061E4E
0x180061e03  movzx   ecx, [rbp+210h+ValueName]
0x180061e0a  sub     cx, 30h ; '0'
0x180061e0e  cmp     cx, 9
0x180061e12  ja      short loc_180061E4E
0x180061e14  cmp     [rsp+310h+Type], 1
0x180061e19  jnz     short loc_180061E4E
0x180061e1b  cmp     edi, 20h ; ' '
0x180061e1e  jnb     short loc_180061E4E
0x180061e20  lea     rdx, [rsp+310h+iid]; lpiid
0x180061e25  lea     rcx, [rbp+210h+Data]; lpsz
0x180061e2c  call    cs:__imp_IIDFromString
0x180061e32  test    eax, eax
0x180061e34  js      short loc_180061E4E
0x180061e36  movups  xmm0, xmmword ptr [rsp+310h+iid.Data1]
0x180061e3b  mov     rax, rdi
0x180061e3e  add     rax, rax
0x180061e41  inc     ebx
0x180061e43  movdqu  [rsp+rax*8+310h+var_2A0], xmm0
0x180061e49  jmp     loc_180061D6B
0x180061e4e  lea     rcx, [rsp+310h+var_2D0]; struct IWppAutoTrace **
0x180061e53  call    ?CWppAutoTrace_CreateInstance@@YAJPEAPEAUIWppAutoTrace@@@Z; CWppAutoTrace_CreateInstance(IWppAutoTrace * *)
0x180061e58  mov     ebx, eax
0x180061e5a  test    eax, eax
0x180061e5c  jns     short loc_180061EC2
0x180061e5e  mov     rax, cs:WPP_GLOBAL_Control
0x180061e65  lea     rcx, WPP_GLOBAL_Control
0x180061e6c  cmp     rax, rcx
0x180061e6f  jz      loc_180061F49
0x180061e75  test    byte ptr [rax+1Ch], 8
0x180061e79  jz      loc_180061F49
0x180061e7f  cmp     byte ptr [rax+19h], 2
0x180061e83  jb      loc_180061F49
0x180061e89  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180061e8e  mov     edx, 0Ah
0x180061e93  lea     rcx, aCwppautotraceC_2; "CWppAutoTrace_CreateInstance"
0x180061e9a  mov     dword ptr [rsp+310h+lpType], ebx
0x180061e9e  lea     r8, WPP_6d9dc437661839af64978a47ef12cc9c_Traceguids
0x180061ea5  mov     [rsp+310h+phkResult], rcx
0x180061eaa  mov     r9d, eax
0x180061ead  mov     rcx, cs:WPP_GLOBAL_Control
0x180061eb4  mov     rcx, [rcx+10h]
0x180061eb8  call    WPP_SF_DsD
0x180061ebd  jmp     loc_180061F49
0x180061ec2  mov     rcx, [rsp+310h+var_2D0]
0x180061ec7  lea     rdx, [rsp+310h+var_2A0]
0x180061ecc  mov     dword ptr [rsp+310h+lpType], 20h ; ' '
0x180061ed4  lea     r9, aSystemrootServ; "%SystemRoot%\\ServiceProfiles\\NetworkS"...
0x180061edb  mov     [rsp+310h+phkResult], rdx
0x180061ee0  lea     r8, aSystemrootServ_0; "%SystemRoot%\\ServiceProfiles\\NetworkS"...
0x180061ee7  lea     rdx, aRdpcorets; "RdpCoreTS"
0x180061eee  mov     rax, [rcx]
0x180061ef1  mov     rax, [rax+18h]
0x180061ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061efa  mov     ebx, eax
0x180061efc  test    eax, eax
0x180061efe  jns     short loc_180061F35
0x180061f00  mov     rax, cs:WPP_GLOBAL_Control
0x180061f07  lea     rcx, WPP_GLOBAL_Control
0x180061f0e  cmp     rax, rcx
0x180061f11  jz      short loc_180061F49
0x180061f13  test    byte ptr [rax+1Ch], 8
0x180061f17  jz      short loc_180061F49
0x180061f19  cmp     byte ptr [rax+19h], 2
0x180061f1d  jb      short loc_180061F49
0x180061f1f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180061f24  mov     edx, 0Bh
0x180061f29  lea     rcx, aIwppautotraceS; "IWppAutoTrace::SetConfiguration() faile"...
0x180061f30  jmp     loc_180061E9A
0x180061f35  mov     rcx, [rsp+310h+var_2D0]
0x180061f3a  mov     [rsi], rcx
0x180061f3d  mov     rax, [rcx]
0x180061f40  mov     rax, [rax+8]
0x180061f44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061f49  mov     rcx, [rsp+310h+var_2D0]
0x180061f4e  test    rcx, rcx
0x180061f51  jz      short loc_180061F68
0x180061f53  mov     [rsp+310h+var_2D0], 0
0x180061f5c  mov     rax, [rcx]
0x180061f5f  mov     rax, [rax+10h]
0x180061f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061f68  mov     rcx, [rsp+310h+hKey]; hKey
0x180061f6d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180061f71  jz      short loc_180061F79
0x180061f73  call    cs:__imp_RegCloseKey
0x180061f79  mov     eax, ebx
0x180061f7b  mov     rcx, [rbp+210h+var_30]
0x180061f82  xor     rcx, rsp; StackCookie
0x180061f85  call    __security_check_cookie
0x180061f8a  add     rsp, 2F8h
0x180061f91  pop     rdi
0x180061f92  pop     rsi
0x180061f93  pop     rbx
0x180061f94  pop     rbp
0x180061f95  retn
```
