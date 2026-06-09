# RealtimeProtection::DlpUserConfigManagement::DlpUserConfig::CheckAndUpdateUserConfig(ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x1801f7658`
- end: `0x1801f7a80`
- name: `?CheckAndUpdateUserConfig@DlpUserConfig@DlpUserConfigManagement@RealtimeProtection@@QEAAJKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `1064`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1801f7104`

## callees

- `0x180027a90`
- `0x180028d80`
- `0x180034420`
- `0x18005fc80`
- `0x180080030`
- `0x1800809d0`
- `0x180081e64`
- `0x180089510`
- `0x18009351c`
- `0x1801028a0`
- `0x180103bb4`
- `0x18010cb40`
- `0x1801f73f8`
- `0x1801f7658`
- `0x1801f7a80`
- `0x1801f7b18`
- `0x1801f7b94`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1801f775d`
- `KERNEL32!CloseHandle` at `0x1801f7818`
- `KERNEL32!CloseHandle` at `0x1801f7887`
- `KERNEL32!CloseHandle` at `0x1801f7a43`
- `KERNEL32!CloseHandle` at `0x1801f775d`
- `KERNEL32!CloseHandle` at `0x1801f7818`
- `KERNEL32!CloseHandle` at `0x1801f7887`
- `KERNEL32!CloseHandle` at `0x1801f7a43`
- `ADVAPI32!RegCloseKey` at `0x1801f792d`
- `ADVAPI32!RegCloseKey` at `0x1801f79a3`
- `ADVAPI32!RegCloseKey` at `0x1801f7a22`
- `ADVAPI32!RegCloseKey` at `0x1801f792d`
- `ADVAPI32!RegCloseKey` at `0x1801f79a3`
- `ADVAPI32!RegCloseKey` at `0x1801f7a22`
- `WTSAPI32!WTSQueryUserToken` at `0x1801f7729`
- `WTSAPI32!WTSQueryUserToken` at `0x1801f7729`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::DlpUserConfigManagement::DlpUserConfig::CheckAndUpdateUserConfig(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rbx
  ULONG v4; // edi
  _QWORD *v6; // r9
  int v7; // edx
  __int64 *v9; // rdi
  int UserData; // eax
  unsigned int v11; // esi
  int v12; // eax
  unsigned int v13; // edi
  HKEY *v14; // rdi
  HKEY v15; // r8
  int Key; // eax
  const wchar_t *v17; // r9
  const wchar_t *v18; // r8
  HKEY v19; // rdx
  int v20; // eax
  __int64 v21; // rdx
  HKEY v22; // r9
  struct _SECURITY_ATTRIBUTES *v23; // [rsp+28h] [rbp-51h]
  void *phToken; // [rsp+30h] [rbp-49h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-41h] BYREF
  std::_Ref_count_base *v26[2]; // [rsp+40h] [rbp-39h] BYREF
  wchar_t *v27[2]; // [rsp+50h] [rbp-29h] BYREF
  __m128i v28; // [rsp+60h] [rbp-19h]
  __int128 v29; // [rsp+70h] [rbp-9h] BYREF
  __m128i si128; // [rsp+80h] [rbp+7h]

  v3 = a3;
  v4 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v6 = a3;
    if ( a3[3] > 7u )
      v6 = (_QWORD *)*a3;
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_52f8bf60e92e37343f383b9802101c60_Traceguids, v6);
  }
  if ( !(unsigned __int8)Dlp::FeatureControl::GetBoolValue(217, a2)
    || (unsigned __int8)RealtimeProtection::DlpUserConfigManagement::DlpUserConfig::GetUserConfigInitializedValue(
                          a1,
                          v3)
    || !(unsigned __int8)RealtimeProtection::DlpUserConfigManagement::DlpUserConfig::ShouldFetchUserConfig(a1, v3) )
  {
    return 0;
  }
  *(_OWORD *)v26 = 0;
  std::make_shared<RealtimeProtection::CSenseCloudCncProxy,>(v26);
  v7 = 0;
  phToken = 0;
  if ( !byte_180313878 )
  {
    if ( !WTSQueryUserToken(v4, &phToken) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_52f8bf60e92e37343f383b9802101c60_Traceguids);
      if ( phToken )
        CloseHandle(phToken);
      if ( v26[1] )
        std::_Ref_count_base::_Decref(v26[1]);
      return 2147500037LL;
    }
    v7 = (int)phToken;
  }
  v29 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v29) = 0;
  *(_OWORD *)v27 = 0;
  v28 = si128;
  LOWORD(v27[0]) = 0;
  v9 = &qword_1803120E8;
  UserData = RealtimeProtection::CSenseCloudCncProxy::QueryUserData((int)v26[0], v7);
  v11 = UserData;
  if ( UserData < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      if ( (unsigned __int64)qword_180312100 > 7 )
        LODWORD(v9) = qword_1803120E8;
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)WPP_52f8bf60e92e37343f383b9802101c60_Traceguids,
        (_DWORD)v9,
        UserData);
    }
LABEL_26:
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v27);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v29);
    if ( phToken )
      CloseHandle(phToken);
    if ( v26[1] )
      std::_Ref_count_base::_Decref(v26[1]);
    return v11;
  }
  v12 = RealtimeProtection::DlpCloudConfig::ParseUserConfigResponse(&v29, v27);
  v13 = v12;
  if ( v12 >= 0 )
  {
    hKey = 0;
    v14 = &qword_1803120A8;
    v15 = (HKEY)&qword_1803120A8;
    if ( (unsigned __int64)qword_1803120C0 > 7 )
      v15 = qword_1803120A8;
    LODWORD(v23) = 0;
    Key = CommonUtil::UtilRegCreateKey(
            (CommonUtil *)&hKey,
            (HKEY *)0xFFFFFFFF80000002LL,
            v15,
            (const wchar_t *)0x2001F,
            0,
            v23,
            (unsigned int)phToken);
    v11 = Key;
    if ( Key < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        if ( (unsigned __int64)qword_1803120C0 > 7 )
          LODWORD(v14) = (_DWORD)qword_1803120A8;
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          (unsigned int)WPP_52f8bf60e92e37343f383b9802101c60_Traceguids,
          (_DWORD)v14,
          Key);
      }
      if ( hKey )
        RegCloseKey(hKey);
      goto LABEL_26;
    }
    v18 = (const wchar_t *)v27;
    if ( v28.m128i_i64[1] > 7uLL )
      v18 = v27[0];
    v19 = (HKEY)v3;
    if ( v3[3] > 7u )
      v19 = (HKEY)*v3;
    v20 = CommonUtil::UtilRegSetValueString((CommonUtil *)hKey, v19, v18, v17);
    v13 = v20;
    if ( v20 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        if ( v3[3] > 7u )
          v3 = (_QWORD *)*v3;
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          (unsigned int)WPP_52f8bf60e92e37343f383b9802101c60_Traceguids,
          (_DWORD)v3,
          v20);
      }
      if ( hKey )
        RegCloseKey(hKey);
      goto LABEL_35;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v22 = (HKEY)v3;
      if ( v3[3] > 7u )
        v22 = (HKEY)*v3;
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_52f8bf60e92e37343f383b9802101c60_Traceguids, v22);
    }
    RealtimeProtection::DlpUserConfigManagement::DlpUserConfig::SetUserConfigInitializedValue(a1, v21, v3);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      if ( v3[3] > 7u )
        v3 = (_QWORD *)*v3;
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_52f8bf60e92e37343f383b9802101c60_Traceguids, v3);
    }
    if ( hKey )
      RegCloseKey(hKey);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v27);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v29);
    if ( phToken )
      CloseHandle(phToken);
    if ( v26[1] )
      std::_Ref_count_base::_Decref(v26[1]);
    return 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      WPP_52f8bf60e92e37343f383b9802101c60_Traceguids,
      (unsigned int)v12);
LABEL_35:
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v27);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v29);
  if ( phToken )
    CloseHandle(phToken);
  if ( v26[1] )
    std::_Ref_count_base::_Decref(v26[1]);
  return v13;
}

```

## disassembly

```asm
0x1801f7658  mov     [rsp-8+arg_18], rbx
0x1801f765d  push    rbp
0x1801f765e  push    rsi
0x1801f765f  push    rdi
0x1801f7660  push    r12
0x1801f7662  push    r13
0x1801f7664  push    r14
0x1801f7666  push    r15
0x1801f7668  lea     rbp, [rsp-27h]
0x1801f766d  sub     rsp, 0A0h
0x1801f7674  mov     rax, cs:__security_cookie
0x1801f767b  xor     rax, rsp
0x1801f767e  mov     [rbp+57h+var_40], rax
0x1801f7682  mov     rbx, r8
0x1801f7685  mov     edi, edx
0x1801f7687  mov     r14, rcx
0x1801f768a  lea     r12, WPP_GLOBAL_Control
0x1801f7691  lea     r13, WPP_52f8bf60e92e37343f383b9802101c60_Traceguids
0x1801f7698  mov     rcx, cs:WPP_GLOBAL_Control
0x1801f769f  cmp     rcx, r12
0x1801f76a2  jz      short loc_1801F76C8
0x1801f76a4  test    byte ptr [rcx+1Ch], 4
0x1801f76a8  jz      short loc_1801F76C8
0x1801f76aa  mov     r9, rbx
0x1801f76ad  cmp     qword ptr [r8+18h], 7
0x1801f76b2  jbe     short loc_1801F76B7
0x1801f76b4  mov     r9, [r8]
0x1801f76b7  mov     edx, 0Ah
0x1801f76bc  mov     r8, r13
0x1801f76bf  mov     rcx, [rcx+10h]
0x1801f76c3  call    WPP_SF_S
0x1801f76c8  mov     ecx, 0D9h
0x1801f76cd  call    ?GetBoolValue@FeatureControl@Dlp@@YA_NW4FeatureControlEnum@@@Z; Dlp::FeatureControl::GetBoolValue(FeatureControlEnum)
0x1801f76d2  xor     r15d, r15d
0x1801f76d5  test    al, al
0x1801f76d7  jz      loc_1801F7A57
0x1801f76dd  mov     rdx, rbx
0x1801f76e0  mov     rcx, r14
0x1801f76e3  call    ?GetUserConfigInitializedValue@DlpUserConfig@DlpUserConfigManagement@RealtimeProtection@@QEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; RealtimeProtection::DlpUserConfigManagement::DlpUserConfig::GetUserConfigInitializedValue(std::wstring const &)
0x1801f76e8  test    al, al
0x1801f76ea  jnz     loc_1801F7A57
0x1801f76f0  mov     rdx, rbx
0x1801f76f3  mov     rcx, r14
0x1801f76f6  call    ?ShouldFetchUserConfig@DlpUserConfig@DlpUserConfigManagement@RealtimeProtection@@AEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; RealtimeProtection::DlpUserConfigManagement::DlpUserConfig::ShouldFetchUserConfig(std::wstring const &)
0x1801f76fb  test    al, al
0x1801f76fd  jz      loc_1801F7A57
0x1801f7703  xorps   xmm0, xmm0
0x1801f7706  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x1801f770a  lea     rcx, [rbp+57h+var_90]
0x1801f770e  call    ??$make_shared@VCSenseCloudCncProxy@RealtimeProtection@@$$V@std@@YA?AV?$shared_ptr@VCSenseCloudCncProxy@RealtimeProtection@@@0@XZ; std::make_shared<RealtimeProtection::CSenseCloudCncProxy,>(void)
0x1801f7713  mov     edx, r15d
0x1801f7716  mov     [rbp+57h+phToken], rdx
0x1801f771a  cmp     cs:byte_180313878, r15b
0x1801f7721  jnz     short loc_1801F777F
0x1801f7723  lea     rdx, [rbp+57h+phToken]; phToken
0x1801f7727  mov     ecx, edi; SessionId
0x1801f7729  call    cs:__imp_WTSQueryUserToken
0x1801f772f  test    eax, eax
0x1801f7731  jnz     short loc_1801F777B
0x1801f7733  mov     rcx, cs:WPP_GLOBAL_Control
0x1801f773a  cmp     rcx, r12
0x1801f773d  jz      short loc_1801F7754
0x1801f773f  test    byte ptr [rcx+1Ch], 1
0x1801f7743  jz      short loc_1801F7754
0x1801f7745  lea     edx, [rax+0Bh]
0x1801f7748  mov     r8, r13
0x1801f774b  mov     rcx, [rcx+10h]
0x1801f774f  call    WPP_SF_
0x1801f7754  mov     rcx, [rbp+57h+phToken]; hObject
0x1801f7758  test    rcx, rcx
0x1801f775b  jz      short loc_1801F7763
0x1801f775d  call    cs:__imp_CloseHandle
0x1801f7763  mov     rcx, [rbp+57h+var_90+8]; this
0x1801f7767  test    rcx, rcx
0x1801f776a  jz      short loc_1801F7771
0x1801f776c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801f7771  mov     eax, 80004005h
0x1801f7776  jmp     loc_1801F7A59
0x1801f777b  mov     rdx, [rbp+57h+phToken]; int
0x1801f777f  xorps   xmm0, xmm0
0x1801f7782  movups  [rbp+57h+var_60], xmm0
0x1801f7786  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1801f778e  movdqu  [rbp+57h+var_50], xmm1
0x1801f7793  mov     word ptr [rbp+57h+var_60], r15w
0x1801f7798  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x1801f779c  movdqu  [rbp+57h+var_70], xmm1
0x1801f77a1  mov     word ptr [rbp+57h+var_80], r15w
0x1801f77a6  lea     r9, [rbp+57h+var_60]
0x1801f77aa  lea     rdi, qword_1803120E8
0x1801f77b1  mov     r8, rdi
0x1801f77b4  mov     rcx, [rbp+57h+var_90]; int
0x1801f77b8  call    ?QueryUserData@CSenseCloudCncProxy@RealtimeProtection@@QEAAJPEAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV34@@Z; RealtimeProtection::CSenseCloudCncProxy::QueryUserData(void *,std::wstring const &,std::wstring &)
0x1801f77bd  mov     esi, eax
0x1801f77bf  test    eax, eax
0x1801f77c1  jns     short loc_1801F7833
0x1801f77c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1801f77ca  cmp     rcx, r12
0x1801f77cd  jz      short loc_1801F77FD
0x1801f77cf  test    byte ptr [rcx+1Ch], 1
0x1801f77d3  jz      short loc_1801F77FD
0x1801f77d5  cmp     cs:qword_180312100, 7
0x1801f77dd  cmova   rdi, cs:qword_1803120E8
0x1801f77e5  mov     edx, 0Ch
0x1801f77ea  mov     [rsp+0D0h+var_B0], eax
0x1801f77ee  mov     r9, rdi
0x1801f77f1  mov     r8, r13
0x1801f77f4  mov     rcx, [rcx+10h]
0x1801f77f8  call    WPP_SF_Sd
0x1801f77fd  lea     rcx, [rbp+57h+var_80]; void *
0x1801f7801  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1801f7806  lea     rcx, [rbp+57h+var_60]; void *
0x1801f780a  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1801f780f  mov     rcx, [rbp+57h+phToken]; hObject
0x1801f7813  test    rcx, rcx
0x1801f7816  jz      short loc_1801F781E
0x1801f7818  call    cs:__imp_CloseHandle
0x1801f781e  mov     rcx, [rbp+57h+var_90+8]; this
0x1801f7822  test    rcx, rcx
0x1801f7825  jz      short loc_1801F782C
0x1801f7827  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801f782c  mov     eax, esi
0x1801f782e  jmp     loc_1801F7A59
0x1801f7833  lea     rdx, [rbp+57h+var_80]
0x1801f7837  lea     rcx, [rbp+57h+var_60]
0x1801f783b  call    ?ParseUserConfigResponse@DlpCloudConfig@RealtimeProtection@@YAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV34@@Z; RealtimeProtection::DlpCloudConfig::ParseUserConfigResponse(std::wstring const &,std::wstring &)
0x1801f7840  mov     edi, eax
0x1801f7842  test    eax, eax
0x1801f7844  jns     short loc_1801F78A2
0x1801f7846  mov     rcx, cs:WPP_GLOBAL_Control
0x1801f784d  cmp     rcx, r12
0x1801f7850  jz      short loc_1801F786C
0x1801f7852  test    byte ptr [rcx+1Ch], 1
0x1801f7856  jz      short loc_1801F786C
0x1801f7858  mov     edx, 0Dh
0x1801f785d  mov     r9d, eax
0x1801f7860  mov     r8, r13
0x1801f7863  mov     rcx, [rcx+10h]
0x1801f7867  call    WPP_SF_d
0x1801f786c  lea     rcx, [rbp+57h+var_80]; void *
0x1801f7870  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1801f7875  lea     rcx, [rbp+57h+var_60]; void *
0x1801f7879  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1801f787e  mov     rcx, [rbp+57h+phToken]; hObject
0x1801f7882  test    rcx, rcx
0x1801f7885  jz      short loc_1801F788D
0x1801f7887  call    cs:__imp_CloseHandle
0x1801f788d  mov     rcx, [rbp+57h+var_90+8]; this
0x1801f7891  test    rcx, rcx
0x1801f7894  jz      short loc_1801F789B
0x1801f7896  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801f789b  mov     eax, edi
0x1801f789d  jmp     loc_1801F7A59
0x1801f78a2  mov     [rbp+57h+hKey], r15
0x1801f78a6  lea     rdi, qword_1803120A8
0x1801f78ad  mov     r8, rdi
0x1801f78b0  cmp     cs:qword_1803120C0, 7
0x1801f78b8  cmova   r8, cs:qword_1803120A8; HKEY
0x1801f78c0  mov     dword ptr [rsp+0D0h+var_A8], r15d; struct _SECURITY_ATTRIBUTES *
0x1801f78c5  mov     qword ptr [rsp+0D0h+var_B0], r15; unsigned int
0x1801f78ca  mov     rdx, 0FFFFFFFF80000002h; HKEY *
0x1801f78d1  mov     r9d, 2001Fh; wchar_t *
0x1801f78d7  lea     rcx, [rbp+57h+hKey]; this
0x1801f78db  call    ?UtilRegCreateKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEB_WKPEAU_SECURITY_ATTRIBUTES@@K@Z; CommonUtil::UtilRegCreateKey(HKEY__ * *,HKEY__ *,wchar_t const *,ulong,_SECURITY_ATTRIBUTES *,ulong)
0x1801f78e0  mov     esi, eax
0x1801f78e2  test    eax, eax
0x1801f78e4  jns     short loc_1801F7938
0x1801f78e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1801f78ed  cmp     rcx, r12
0x1801f78f0  jz      short loc_1801F7920
0x1801f78f2  test    byte ptr [rcx+1Ch], 1
0x1801f78f6  jz      short loc_1801F7920
0x1801f78f8  cmp     cs:qword_1803120C0, 7
0x1801f7900  cmova   rdi, cs:qword_1803120A8
0x1801f7908  mov     edx, 0Eh
0x1801f790d  mov     [rsp+0D0h+var_B0], eax
0x1801f7911  mov     r9, rdi
0x1801f7914  mov     r8, r13
0x1801f7917  mov     rcx, [rcx+10h]
0x1801f791b  call    WPP_SF_Sd
0x1801f7920  mov     rcx, [rbp+57h+hKey]; hKey
0x1801f7924  test    rcx, rcx
0x1801f7927  jz      loc_1801F77FD
0x1801f792d  call    cs:__imp_RegCloseKey
0x1801f7933  jmp     loc_1801F77FD
0x1801f7938  lea     r8, [rbp+57h+var_80]
0x1801f793c  cmp     qword ptr [rbp+57h+var_70+8], 7
0x1801f7941  cmova   r8, [rbp+57h+var_80]; wchar_t *
0x1801f7946  mov     rdx, rbx
0x1801f7949  cmp     qword ptr [rbx+18h], 7
0x1801f794e  jbe     short loc_1801F7953
0x1801f7950  mov     rdx, [rbx]; HKEY
0x1801f7953  mov     rcx, [rbp+57h+hKey]; this
0x1801f7957  call    ?UtilRegSetValueString@CommonUtil@@YAJPEAUHKEY__@@PEB_W1@Z; CommonUtil::UtilRegSetValueString(HKEY__ *,wchar_t const *,wchar_t const *)
0x1801f795c  mov     edi, eax
0x1801f795e  test    eax, eax
0x1801f7960  jns     short loc_1801F79AE
0x1801f7962  mov     rcx, cs:WPP_GLOBAL_Control
0x1801f7969  cmp     rcx, r12
0x1801f796c  jz      short loc_1801F7996
0x1801f796e  test    byte ptr [rcx+1Ch], 1
0x1801f7972  jz      short loc_1801F7996
0x1801f7974  cmp     qword ptr [rbx+18h], 7
0x1801f7979  jbe     short loc_1801F797E
0x1801f797b  mov     rbx, [rbx]
0x1801f797e  mov     edx, 0Fh
0x1801f7983  mov     [rsp+0D0h+var_B0], edi
0x1801f7987  mov     r9, rbx
0x1801f798a  mov     r8, r13
0x1801f798d  mov     rcx, [rcx+10h]
0x1801f7991  call    WPP_SF_Sd
0x1801f7996  mov     rcx, [rbp+57h+hKey]; hKey
0x1801f799a  test    rcx, rcx
0x1801f799d  jz      loc_1801F786C
0x1801f79a3  call    cs:__imp_RegCloseKey
0x1801f79a9  jmp     loc_1801F786C
0x1801f79ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1801f79b5  cmp     rcx, r12
0x1801f79b8  jz      short loc_1801F79DE
0x1801f79ba  test    byte ptr [rcx+1Ch], 4
0x1801f79be  jz      short loc_1801F79DE
0x1801f79c0  mov     r9, rbx
0x1801f79c3  cmp     qword ptr [rbx+18h], 7
0x1801f79c8  jbe     short loc_1801F79CD
0x1801f79ca  mov     r9, [rbx]
0x1801f79cd  mov     edx, 10h
0x1801f79d2  mov     r8, r13
0x1801f79d5  mov     rcx, [rcx+10h]
0x1801f79d9  call    WPP_SF_S
0x1801f79de  mov     r8, rbx
0x1801f79e1  mov     rcx, r14
0x1801f79e4  call    ?SetUserConfigInitializedValue@DlpUserConfig@DlpUserConfigManagement@RealtimeProtection@@QEAAX_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; RealtimeProtection::DlpUserConfigManagement::DlpUserConfig::SetUserConfigInitializedValue(bool,std::wstring const &)
0x1801f79e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1801f79f0  cmp     rcx, r12
0x1801f79f3  jz      short loc_1801F7A19
0x1801f79f5  test    byte ptr [rcx+1Ch], 4
0x1801f79f9  jz      short loc_1801F7A19
0x1801f79fb  cmp     qword ptr [rbx+18h], 7
0x1801f7a00  jbe     short loc_1801F7A05
0x1801f7a02  mov     rbx, [rbx]
0x1801f7a05  mov     edx, 11h
0x1801f7a0a  mov     r9, rbx
0x1801f7a0d  mov     r8, r13
0x1801f7a10  mov     rcx, [rcx+10h]
0x1801f7a14  call    WPP_SF_S
0x1801f7a19  mov     rcx, [rbp+57h+hKey]; hKey
0x1801f7a1d  test    rcx, rcx
0x1801f7a20  jz      short loc_1801F7A28
0x1801f7a22  call    cs:__imp_RegCloseKey
0x1801f7a28  lea     rcx, [rbp+57h+var_80]; void *
0x1801f7a2c  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1801f7a31  lea     rcx, [rbp+57h+var_60]; void *
0x1801f7a35  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1801f7a3a  mov     rcx, [rbp+57h+phToken]; hObject
0x1801f7a3e  test    rcx, rcx
0x1801f7a41  jz      short loc_1801F7A49
0x1801f7a43  call    cs:__imp_CloseHandle
0x1801f7a49  mov     rcx, [rbp+57h+var_90+8]; this
0x1801f7a4d  test    rcx, rcx
0x1801f7a50  jz      short loc_1801F7A57
0x1801f7a52  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801f7a57  xor     eax, eax
0x1801f7a59  mov     rcx, [rbp+57h+var_40]
0x1801f7a5d  xor     rcx, rsp; StackCookie
0x1801f7a60  call    __security_check_cookie
0x1801f7a65  mov     rbx, [rsp+0D0h+arg_18]
0x1801f7a6d  add     rsp, 0A0h
0x1801f7a74  pop     r15
0x1801f7a76  pop     r14
0x1801f7a78  pop     r13
0x1801f7a7a  pop     r12
0x1801f7a7c  pop     rdi
0x1801f7a7d  pop     rsi
0x1801f7a7e  pop     rbp
0x1801f7a7f  retn
```
