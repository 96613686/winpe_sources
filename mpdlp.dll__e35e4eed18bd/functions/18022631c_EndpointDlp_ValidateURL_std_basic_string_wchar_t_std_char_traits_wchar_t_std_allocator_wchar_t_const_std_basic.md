# EndpointDlp::ValidateURL(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x18022631c`
- end: `0x180226871`
- name: `?ValidateURL@EndpointDlp@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV23@1@Z`
- size: `1365`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x180217d00`

## callees

- `0x1800058a4`
- `0x18002c150`
- `0x1800301a0`
- `0x180034420`
- `0x180037afc`
- `0x1800398a0`
- `0x18004de90`
- `0x180055fa0`
- `0x18006e580`
- `0x1800810c0`
- `0x1800815e4`
- `0x1800943dc`
- `0x1800ca65c`
- `0x1800ca8e8`
- `0x18010cb40`
- `0x1801b721c`
- `0x18022631c`
- `0x18023a310`

## import_xrefs

- `SHLWAPI!PathMatchSpecW` at `0x180226370`
- `SHLWAPI!PathMatchSpecW` at `0x18022638e`
- `SHLWAPI!PathMatchSpecW` at `0x1802263ac`
- `SHLWAPI!PathMatchSpecW` at `0x1802263ca`
- `SHLWAPI!PathMatchSpecW` at `0x18022648e`
- `SHLWAPI!PathMatchSpecW` at `0x1802264bd`
- `SHLWAPI!PathMatchSpecW` at `0x180226370`
- `SHLWAPI!PathMatchSpecW` at `0x18022638e`
- `SHLWAPI!PathMatchSpecW` at `0x1802263ac`
- `SHLWAPI!PathMatchSpecW` at `0x1802263ca`
- `SHLWAPI!PathMatchSpecW` at `0x18022648e`
- `SHLWAPI!PathMatchSpecW` at `0x1802264bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
char __fastcall EndpointDlp::ValidateURL(__int64 a1, void *a2, void *a3)
{
  const WCHAR *v6; // rcx
  const WCHAR *v7; // rcx
  const WCHAR *v8; // rcx
  const WCHAR *v9; // rcx
  struct EndpointDlp::TraceLoggingProvider *v10; // rax
  int v11; // r8d
  int v12; // r9d
  _DWORD *v13; // rcx
  const WCHAR *v15; // rcx
  const WCHAR *v16; // rcx
  struct EndpointDlp::TraceLoggingProvider *v17; // rax
  int v18; // r8d
  int v19; // r9d
  _DWORD *v20; // rcx
  struct EndpointDlp::TraceLoggingProvider *v21; // rax
  int v22; // r8d
  int v23; // r9d
  _DWORD *v24; // rcx
  __int64 v25; // rax
  _WORD *v26; // rax
  struct EndpointDlp::TraceLoggingProvider *v27; // rax
  int v28; // r8d
  int v29; // r9d
  _DWORD *v30; // rcx
  __int64 v31; // rax
  struct EndpointDlp::TraceLoggingProvider *v32; // rax
  int v33; // r8d
  int v34; // r9d
  _DWORD *v35; // rcx
  int v36; // [rsp+40h] [rbp-398h] BYREF
  _QWORD v37[3]; // [rsp+48h] [rbp-390h] BYREF
  _BYTE v38[32]; // [rsp+60h] [rbp-378h] BYREF
  _BYTE v39[240]; // [rsp+80h] [rbp-358h] BYREF
  LPCWSTR pszFile[3]; // [rsp+170h] [rbp-268h] BYREF
  unsigned __int64 v41; // [rsp+188h] [rbp-250h]
  _QWORD v42[4]; // [rsp+190h] [rbp-248h] BYREF
  __int128 Src; // [rsp+1B0h] [rbp-228h] BYREF
  __int64 v44; // [rsp+1C0h] [rbp-218h]
  __int64 v45; // [rsp+1C8h] [rbp-210h]
  _BYTE v46[64]; // [rsp+1D0h] [rbp-208h] BYREF
  _BYTE v47[176]; // [rsp+210h] [rbp-1C8h] BYREF
  _BYTE v48[240]; // [rsp+2C0h] [rbp-118h] BYREF

  v37[1] = a1;
  if ( !(unsigned __int8)web::uri::validate() )
    return 1;
  v6 = (const WCHAR *)a1;
  if ( *(_QWORD *)(a1 + 24) > 7u )
    v6 = *(const WCHAR **)a1;
  if ( !PathMatchSpecW(v6, L"https://*.blob.core.windows.net/*") )
  {
    v7 = (const WCHAR *)a1;
    if ( *(_QWORD *)(a1 + 24) > 7u )
      v7 = *(const WCHAR **)a1;
    if ( !PathMatchSpecW(v7, L"http://*.blob.core.windows.net/*") )
    {
      v8 = (const WCHAR *)a1;
      if ( *(_QWORD *)(a1 + 24) > 7u )
        v8 = *(const WCHAR **)a1;
      if ( !PathMatchSpecW(v8, L"https://*.blob.core.usgovcloudapi.net/*") )
      {
        v9 = (const WCHAR *)a1;
        if ( *(_QWORD *)(a1 + 24) > 7u )
          v9 = *(const WCHAR **)a1;
        if ( !PathMatchSpecW(v9, L"http://*.blob.core.usgovcloudapi.net/*") )
          return 1;
      }
    }
  }
  web::uri::uri(v46, a1);
  std::wstring::wstring(pszFile, v47);
  if ( !pszFile[2] )
  {
    v10 = EndpointDlp::TraceLoggingProvider::Instance();
    v13 = *(_DWORD **)v10;
    if ( **(_DWORD **)v10 > 2u )
    {
      v37[0] = L"ValidateURL: Empty Host";
      v36 = -2147024809;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        (_DWORD)v13,
        (unsigned int)&dword_1802CABC4,
        v11,
        v12,
        (__int64)&v36,
        (__int64)v37);
    }
LABEL_17:
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(pszFile);
    web::uri::~uri((web::uri *)v46);
    return 0;
  }
  v15 = (const WCHAR *)pszFile;
  if ( v41 > 7 )
    v15 = pszFile[0];
  if ( !PathMatchSpecW(v15, L"*.blob.core.windows.net") )
  {
    v16 = (const WCHAR *)pszFile;
    if ( v41 > 7 )
      v16 = pszFile[0];
    if ( !PathMatchSpecW(v16, L"*.blob.core.usgovcloudapi.net") )
    {
      v17 = EndpointDlp::TraceLoggingProvider::Instance();
      v20 = *(_DWORD **)v17;
      if ( **(_DWORD **)v17 > 2u )
      {
        v37[0] = L"ValidateURL: Account Expression does not match";
        v36 = -2147024809;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          (_DWORD)v20,
          (unsigned int)byte_1802CAAC3,
          v18,
          v19,
          (__int64)&v36,
          (__int64)v37);
      }
      goto LABEL_17;
    }
  }
  memset(v48, 0, sizeof(v48));
  std::wistringstream::wistringstream(v48, v47);
  Src = 0;
  v44 = 0;
  v45 = 7;
  LOWORD(Src) = 0;
  std::getline<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v48, &Src, 46);
  if ( v44 )
  {
    v25 = web::uri::resource(v46, v39);
    std::filesystem::path::operator std::wstring(v25, v42);
    web::uri::~uri((web::uri *)v39);
    if ( v42[2] < 2u )
    {
      v32 = EndpointDlp::TraceLoggingProvider::Instance();
      v35 = *(_DWORD **)v32;
      if ( **(_DWORD **)v32 > 2u )
      {
        v37[0] = L"ValidateURL: Empty Resource Name";
        v36 = -2147024809;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          (_DWORD)v35,
          (unsigned int)byte_1802CAB5D,
          v33,
          v34,
          (__int64)&v36,
          (__int64)v37);
      }
      goto LABEL_37;
    }
    v26 = v42;
    if ( v42[3] > 7u )
      v26 = (_WORD *)v42[0];
    if ( *v26 != 47 )
    {
      v27 = EndpointDlp::TraceLoggingProvider::Instance();
      v30 = *(_DWORD **)v27;
      if ( **(_DWORD **)v27 > 2u )
      {
        v37[0] = L"ValidateURL: Invalid Resource Name";
        v36 = -2147024809;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          (_DWORD)v30,
          (unsigned int)byte_1802CAA93,
          v28,
          v29,
          (__int64)&v36,
          (__int64)v37);
      }
LABEL_37:
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v42);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&Src);
      std::wistringstream::`vbase destructor'(v48);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(pszFile);
      web::uri::~uri((web::uri *)v46);
      return 0;
    }
    v31 = std::wstring::substr(v42, v38, 1, -1);
    std::wstring::operator=(v42, v31);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v38);
    std::wstring::operator=(a2, &Src);
    std::wstring::operator=(a3, v42);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v42);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&Src);
    std::wistringstream::`vbase destructor'(v48);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(pszFile);
    web::uri::~uri((web::uri *)v46);
    return 1;
  }
  v21 = EndpointDlp::TraceLoggingProvider::Instance();
  v24 = *(_DWORD **)v21;
  if ( **(_DWORD **)v21 > 2u )
  {
    v37[0] = L"ValidateURL: Empty Account Name";
    v36 = -2147024809;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
      (_DWORD)v24,
      (unsigned int)byte_1802CAB2D,
      v22,
      v23,
      (__int64)&v36,
      (__int64)v37);
  }
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&Src);
  std::wistringstream::`vbase destructor'(v48);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(pszFile);
  web::uri::~uri((web::uri *)v46);
  return 0;
}

```

## disassembly

```asm
0x18022631c  mov     [rsp+arg_18], rbx
0x180226321  push    rsi
0x180226322  push    rdi
0x180226323  push    r14
0x180226325  sub     rsp, 3C0h
0x18022632c  mov     rax, cs:__security_cookie
0x180226333  xor     rax, rsp
0x180226336  mov     [rsp+3D8h+var_28], rax
0x18022633e  mov     rdi, r8
0x180226341  mov     rsi, rdx
0x180226344  mov     rbx, rcx
0x180226347  mov     [rsp+3D8h+var_388], rcx
0x18022634c  call    ?validate@uri@web@@SA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::uri::validate(std::wstring const &)
0x180226351  xor     r14d, r14d
0x180226354  test    al, al
0x180226356  jz      loc_180226846
0x18022635c  mov     rcx, rbx
0x18022635f  cmp     qword ptr [rbx+18h], 7
0x180226364  jbe     short loc_180226369
0x180226366  mov     rcx, [rbx]; pszFile
0x180226369  lea     rdx, pszSpec; "https://*.blob.core.windows.net/*"
0x180226370  call    cs:__imp_PathMatchSpecW
0x180226376  test    eax, eax
0x180226378  jnz     short loc_1802263D8
0x18022637a  mov     rcx, rbx
0x18022637d  cmp     qword ptr [rbx+18h], 7
0x180226382  jbe     short loc_180226387
0x180226384  mov     rcx, [rbx]; pszFile
0x180226387  lea     rdx, aHttpBlobCoreWi; "http://*.blob.core.windows.net/*"
0x18022638e  call    cs:__imp_PathMatchSpecW
0x180226394  test    eax, eax
0x180226396  jnz     short loc_1802263D8
0x180226398  mov     rcx, rbx
0x18022639b  cmp     qword ptr [rbx+18h], 7
0x1802263a0  jbe     short loc_1802263A5
0x1802263a2  mov     rcx, [rbx]; pszFile
0x1802263a5  lea     rdx, aHttpsBlobCoreU; "https://*.blob.core.usgovcloudapi.net/*"
0x1802263ac  call    cs:__imp_PathMatchSpecW
0x1802263b2  test    eax, eax
0x1802263b4  jnz     short loc_1802263D8
0x1802263b6  mov     rcx, rbx
0x1802263b9  cmp     qword ptr [rbx+18h], 7
0x1802263be  jbe     short loc_1802263C3
0x1802263c0  mov     rcx, [rbx]; pszFile
0x1802263c3  lea     rdx, aHttpBlobCoreUs; "http://*.blob.core.usgovcloudapi.net/*"
0x1802263ca  call    cs:__imp_PathMatchSpecW
0x1802263d0  test    eax, eax
0x1802263d2  jz      loc_180226846
0x1802263d8  mov     rdx, rbx
0x1802263db  lea     rcx, [rsp+3D8h+var_208]
0x1802263e3  call    ??0uri@web@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::uri::uri(std::wstring const &)
0x1802263e8  nop
0x1802263e9  lea     rdx, [rsp+3D8h+var_1C8]
0x1802263f1  lea     rcx, [rsp+3D8h+pszFile]
0x1802263f9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1802263fe  nop
0x1802263ff  cmp     [rsp+3D8h+var_258], r14
0x180226407  jnz     short loc_18022646D
0x180226409  call    ?Instance@TraceLoggingProvider@EndpointDlp@@SAAEAV12@XZ; EndpointDlp::TraceLoggingProvider::Instance(void)
0x18022640e  mov     rcx, [rax]
0x180226411  cmp     dword ptr [rcx], 2
0x180226414  jbe     short loc_18022644B
0x180226416  lea     rax, aValidateurlEmp; "ValidateURL: Empty Host"
0x18022641d  mov     [rsp+3D8h+var_390], rax
0x180226422  mov     [rsp+3D8h+var_398], 80070057h
0x18022642a  lea     rax, [rsp+3D8h+var_390]
0x18022642f  mov     [rsp+3D8h+var_3B0], rax
0x180226434  lea     rax, [rsp+3D8h+var_398]
0x180226439  mov     [rsp+3D8h+var_3B8], rax
0x18022643e  lea     rdx, dword_1802CABC4
0x180226445  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x18022644a  nop
0x18022644b  lea     rcx, [rsp+3D8h+pszFile]; void *
0x180226453  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180226458  nop
0x180226459  lea     rcx, [rsp+3D8h+var_208]; this
0x180226461  call    ??1uri@web@@QEAA@XZ; web::uri::~uri(void)
0x180226466  xor     al, al
0x180226468  jmp     loc_18022684C
0x18022646d  lea     rcx, [rsp+3D8h+pszFile]
0x180226475  cmp     [rsp+3D8h+var_250], 7
0x18022647e  cmova   rcx, [rsp+3D8h+pszFile]; pszFile
0x180226487  lea     rdx, aBlobCoreWindow; "*.blob.core.windows.net"
0x18022648e  call    cs:__imp_PathMatchSpecW
0x180226494  test    eax, eax
0x180226496  jnz     loc_18022652B
0x18022649c  lea     rcx, [rsp+3D8h+pszFile]
0x1802264a4  cmp     [rsp+3D8h+var_250], 7
0x1802264ad  cmova   rcx, [rsp+3D8h+pszFile]; pszFile
0x1802264b6  lea     rdx, aBlobCoreUsgovc; "*.blob.core.usgovcloudapi.net"
0x1802264bd  call    cs:__imp_PathMatchSpecW
0x1802264c3  test    eax, eax
0x1802264c5  jnz     short loc_18022652B
0x1802264c7  call    ?Instance@TraceLoggingProvider@EndpointDlp@@SAAEAV12@XZ; EndpointDlp::TraceLoggingProvider::Instance(void)
0x1802264cc  mov     rcx, [rax]
0x1802264cf  cmp     dword ptr [rcx], 2
0x1802264d2  jbe     short loc_180226509
0x1802264d4  lea     rax, aValidateurlAcc; "ValidateURL: Account Expression does no"...
0x1802264db  mov     [rsp+3D8h+var_390], rax
0x1802264e0  mov     [rsp+3D8h+var_398], 80070057h
0x1802264e8  lea     rax, [rsp+3D8h+var_390]
0x1802264ed  mov     [rsp+3D8h+var_3B0], rax
0x1802264f2  lea     rax, [rsp+3D8h+var_398]
0x1802264f7  mov     [rsp+3D8h+var_3B8], rax
0x1802264fc  lea     rdx, byte_1802CAAC3
0x180226503  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x180226508  nop
0x180226509  lea     rcx, [rsp+3D8h+pszFile]; void *
0x180226511  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180226516  nop
0x180226517  lea     rcx, [rsp+3D8h+var_208]; this
0x18022651f  call    ??1uri@web@@QEAA@XZ; web::uri::~uri(void)
0x180226524  xor     al, al
0x180226526  jmp     loc_18022684C
0x18022652b  xor     edx, edx; Val
0x18022652d  mov     r8d, 0F0h; Size
0x180226533  lea     rcx, [rsp+3D8h+var_118]; void *
0x18022653b  call    memset
0x180226540  lea     rdx, [rsp+3D8h+var_1C8]
0x180226548  lea     rcx, [rsp+3D8h+var_118]
0x180226550  call    ??0?$basic_istringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@H@Z; std::wistringstream::wistringstream(std::wstring const &,int)
0x180226555  nop
0x180226556  xorps   xmm0, xmm0
0x180226559  movups  [rsp+3D8h+Src], xmm0
0x180226561  mov     [rsp+3D8h+var_218], r14
0x180226569  mov     [rsp+3D8h+var_210], 7
0x180226575  mov     word ptr [rsp+3D8h+Src], r14w
0x18022657e  mov     r8d, 2Eh ; '.'
0x180226584  lea     rdx, [rsp+3D8h+Src]
0x18022658c  lea     rcx, [rsp+3D8h+var_118]
0x180226594  call    ??$getline@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@YAAEAV?$basic_istream@_WU?$char_traits@_W@std@@@0@$$QEAV10@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@_W@Z; std::getline<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(std::wistream &&,std::wstring &,wchar_t)
0x180226599  cmp     [rsp+3D8h+var_218], r14
0x1802265a1  jnz     loc_180226627
0x1802265a7  call    ?Instance@TraceLoggingProvider@EndpointDlp@@SAAEAV12@XZ; EndpointDlp::TraceLoggingProvider::Instance(void)
0x1802265ac  mov     rcx, [rax]
0x1802265af  cmp     dword ptr [rcx], 2
0x1802265b2  jbe     short loc_1802265E9
0x1802265b4  lea     rax, aValidateurlEmp_0; "ValidateURL: Empty Account Name"
0x1802265bb  mov     [rsp+3D8h+var_390], rax
0x1802265c0  mov     [rsp+3D8h+var_398], 80070057h
0x1802265c8  lea     rax, [rsp+3D8h+var_390]
0x1802265cd  mov     [rsp+3D8h+var_3B0], rax
0x1802265d2  lea     rax, [rsp+3D8h+var_398]
0x1802265d7  mov     [rsp+3D8h+var_3B8], rax
0x1802265dc  lea     rdx, byte_1802CAB2D
0x1802265e3  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x1802265e8  nop
0x1802265e9  lea     rcx, [rsp+3D8h+Src]; void *
0x1802265f1  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1802265f6  nop
0x1802265f7  lea     rcx, [rsp+3D8h+var_118]
0x1802265ff  call    ??_D?$basic_istringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAXXZ; std::wistringstream::`vbase destructor'(void)
0x180226604  nop
0x180226605  lea     rcx, [rsp+3D8h+pszFile]; void *
0x18022660d  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180226612  nop
0x180226613  lea     rcx, [rsp+3D8h+var_208]; this
0x18022661b  call    ??1uri@web@@QEAA@XZ; web::uri::~uri(void)
0x180226620  xor     al, al
0x180226622  jmp     loc_18022684C
0x180226627  lea     rdx, [rsp+3D8h+var_358]
0x18022662f  lea     rcx, [rsp+3D8h+var_208]
0x180226637  call    ?resource@uri@web@@QEBA?AV12@XZ; web::uri::resource(void)
0x18022663c  nop
0x18022663d  lea     rdx, [rsp+3D8h+var_248]
0x180226645  mov     rcx, rax
0x180226648  call    ??Bpath@filesystem@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::filesystem::path::operator std::wstring(void)
0x18022664d  nop
0x18022664e  lea     rcx, [rsp+3D8h+var_358]; this
0x180226656  call    ??1uri@web@@QEAA@XZ; web::uri::~uri(void)
0x18022665b  cmp     [rsp+3D8h+var_238], 2
0x180226664  jb      loc_1802267BB
0x18022666a  lea     rax, [rsp+3D8h+var_248]
0x180226672  cmp     [rsp+3D8h+var_230], 7
0x18022667b  cmova   rax, [rsp+3D8h+var_248]
0x180226684  cmp     word ptr [rax], 2Fh ; '/'
0x180226688  jz      loc_18022671C
0x18022668e  call    ?Instance@TraceLoggingProvider@EndpointDlp@@SAAEAV12@XZ; EndpointDlp::TraceLoggingProvider::Instance(void)
0x180226693  mov     rcx, [rax]
0x180226696  cmp     dword ptr [rcx], 2
0x180226699  jbe     short loc_1802266D0
0x18022669b  lea     rax, aValidateurlInv; "ValidateURL: Invalid Resource Name"
0x1802266a2  mov     [rsp+3D8h+var_390], rax
0x1802266a7  mov     [rsp+3D8h+var_398], 80070057h
0x1802266af  lea     rax, [rsp+3D8h+var_390]
0x1802266b4  mov     [rsp+3D8h+var_3B0], rax
0x1802266b9  lea     rax, [rsp+3D8h+var_398]
0x1802266be  mov     [rsp+3D8h+var_3B8], rax
0x1802266c3  lea     rdx, byte_1802CAA93
0x1802266ca  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x1802266cf  nop
0x1802266d0  lea     rcx, [rsp+3D8h+var_248]; void *
0x1802266d8  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1802266dd  nop
0x1802266de  lea     rcx, [rsp+3D8h+Src]; void *
0x1802266e6  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1802266eb  nop
0x1802266ec  lea     rcx, [rsp+3D8h+var_118]
0x1802266f4  call    ??_D?$basic_istringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAXXZ; std::wistringstream::`vbase destructor'(void)
0x1802266f9  nop
0x1802266fa  lea     rcx, [rsp+3D8h+pszFile]; void *
0x180226702  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180226707  nop
0x180226708  lea     rcx, [rsp+3D8h+var_208]; this
0x180226710  call    ??1uri@web@@QEAA@XZ; web::uri::~uri(void)
0x180226715  xor     al, al
0x180226717  jmp     loc_18022684C
0x18022671c  or      r9, 0FFFFFFFFFFFFFFFFh
0x180226720  lea     r8d, [r9+2]
0x180226724  lea     rdx, [rsp+3D8h+var_378]
0x180226729  lea     rcx, [rsp+3D8h+var_248]
0x180226731  call    ?substr@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180226736  mov     rdx, rax
0x180226739  lea     rcx, [rsp+3D8h+var_248]
0x180226741  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180226746  lea     rcx, [rsp+3D8h+var_378]; void *
0x18022674b  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180226750  lea     rdx, [rsp+3D8h+Src]; Src
0x180226758  mov     rcx, rsi; void *
0x18022675b  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180226760  lea     rdx, [rsp+3D8h+var_248]; Src
0x180226768  mov     rcx, rdi; void *
0x18022676b  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180226770  nop
0x180226771  lea     rcx, [rsp+3D8h+var_248]; void *
0x180226779  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18022677e  nop
0x18022677f  lea     rcx, [rsp+3D8h+Src]; void *
0x180226787  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18022678c  nop
0x18022678d  lea     rcx, [rsp+3D8h+var_118]
0x180226795  call    ??_D?$basic_istringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAXXZ; std::wistringstream::`vbase destructor'(void)
0x18022679a  nop
0x18022679b  lea     rcx, [rsp+3D8h+pszFile]; void *
0x1802267a3  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1802267a8  nop
0x1802267a9  lea     rcx, [rsp+3D8h+var_208]; this
0x1802267b1  call    ??1uri@web@@QEAA@XZ; web::uri::~uri(void)
0x1802267b6  jmp     loc_180226846
0x1802267bb  call    ?Instance@TraceLoggingProvider@EndpointDlp@@SAAEAV12@XZ; EndpointDlp::TraceLoggingProvider::Instance(void)
0x1802267c0  mov     rcx, [rax]
0x1802267c3  cmp     dword ptr [rcx], 2
0x1802267c6  jbe     short loc_1802267FD
0x1802267c8  lea     rax, aValidateurlEmp_1; "ValidateURL: Empty Resource Name"
0x1802267cf  mov     [rsp+3D8h+var_390], rax
0x1802267d4  mov     [rsp+3D8h+var_398], 80070057h
0x1802267dc  lea     rax, [rsp+3D8h+var_390]
0x1802267e1  mov     [rsp+3D8h+var_3B0], rax
0x1802267e6  lea     rax, [rsp+3D8h+var_398]
0x1802267eb  mov     [rsp+3D8h+var_3B8], rax
0x1802267f0  lea     rdx, byte_1802CAB5D
0x1802267f7  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x1802267fc  nop
0x1802267fd  lea     rcx, [rsp+3D8h+var_248]; void *
0x180226805  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18022680a  nop
0x18022680b  lea     rcx, [rsp+3D8h+Src]; void *
0x180226813  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180226818  nop
0x180226819  lea     rcx, [rsp+3D8h+var_118]
0x180226821  call    ??_D?$basic_istringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAXXZ; std::wistringstream::`vbase destructor'(void)
0x180226826  nop
0x180226827  lea     rcx, [rsp+3D8h+pszFile]; void *
0x18022682f  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180226834  nop
0x180226835  lea     rcx, [rsp+3D8h+var_208]; this
0x18022683d  call    ??1uri@web@@QEAA@XZ; web::uri::~uri(void)
0x180226842  xor     al, al
0x180226844  jmp     short loc_18022684C
0x180226846  mov     al, 1
0x180226848  jmp     short loc_18022684C
0x18022684a  xor     al, al
0x18022684c  mov     rcx, [rsp+3D8h+var_28]
0x180226854  xor     rcx, rsp; StackCookie
0x180226857  call    __security_check_cookie
0x18022685c  mov     rbx, [rsp+3D8h+arg_18]
0x180226864  add     rsp, 3C0h
0x18022686b  pop     r14
0x18022686d  pop     rdi
0x18022686e  pop     rsi
0x18022686f  retn
```
