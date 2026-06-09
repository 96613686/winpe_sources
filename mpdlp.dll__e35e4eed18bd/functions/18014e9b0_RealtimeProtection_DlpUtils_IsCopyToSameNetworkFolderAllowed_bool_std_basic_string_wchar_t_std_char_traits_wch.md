# RealtimeProtection::DlpUtils::IsCopyToSameNetworkFolderAllowed(bool,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ulong,bool)

- ea: `0x18014e9b0`
- end: `0x18014ed11`
- name: `?IsCopyToSameNetworkFolderAllowed@DlpUtils@RealtimeProtection@@YA_N_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1K0@Z`
- size: `865`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180044374`

## callees

- `0x180034420`
- `0x180080030`
- `0x1800809d0`
- `0x1800943fc`
- `0x1800b7f88`
- `0x1800b9394`
- `0x18010674c`
- `0x18010cb40`
- `0x18014e9b0`
- `0x180183c68`
- `0x1801cac98`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x18014ec79`
- `KERNEL32!CompareStringOrdinal` at `0x18014ec79`
- `KERNEL32!CloseHandle` at `0x18014ebd4`
- `KERNEL32!CloseHandle` at `0x18014ed04`
- `KERNEL32!CloseHandle` at `0x18014ebd4`
- `KERNEL32!CloseHandle` at `0x18014ed04`
- `ADVAPI32!RevertToSelf` at `0x18014ebc5`
- `ADVAPI32!RevertToSelf` at `0x18014ecf5`
- `ADVAPI32!RevertToSelf` at `0x18014ebc5`
- `ADVAPI32!RevertToSelf` at `0x18014ecf5`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall RealtimeProtection::DlpUtils::IsCopyToSameNetworkFolderAllowed(
        char a1,
        _QWORD *a2,
        wchar_t *a3,
        bool *a4,
        char a5)
{
  unsigned int v5; // r14d
  wchar_t *v6; // rdi
  _QWORD *v7; // rsi
  wchar_t *v8; // rcx
  bool *v9; // r9
  wchar_t *v10; // rcx
  void **v11; // r8
  void *v12; // rbx
  int ImpersonationToken; // eax
  void *v14; // rcx
  wchar_t *v15; // rcx
  _QWORD *v16; // rcx
  LPCWCH *v18; // rax
  LPCWCH *v19; // r9
  const WCHAR *v20; // r8
  const WCHAR *v21; // rcx
  const wchar_t *v22; // r8
  const wchar_t *v23; // rdx
  void **v24; // rcx
  const wchar_t *v25; // r8
  void **v26; // rcx
  unsigned int v27[2]; // [rsp+30h] [rbp-41h] BYREF
  __int128 v28; // [rsp+38h] [rbp-39h] BYREF
  wchar_t v29; // [rsp+48h] [rbp-29h] BYREF
  LPCWCH lpString2[2]; // [rsp+50h] [rbp-21h] BYREF
  int cchCount2[4]; // [rsp+60h] [rbp-11h]
  LPCWCH lpString1[2]; // [rsp+70h] [rbp-1h] BYREF
  int cchCount1[4]; // [rsp+80h] [rbp+Fh]

  v5 = (unsigned int)a4;
  v6 = a3;
  v7 = a2;
  if ( !a1 || !a2[2] || !*((_QWORD *)a3 + 2) )
    return 0;
  LOBYTE(v29) = 0;
  v8 = (wchar_t *)a2;
  if ( a2[3] > 7u )
    v8 = (wchar_t *)*a2;
  CommonUtil::UtilIsNetworkPath(v8, &v29, 0, a4);
  if ( !(_BYTE)v29 )
    return 0;
  v10 = v6;
  if ( *((_QWORD *)v6 + 3) > 7u )
    v10 = *(wchar_t **)v6;
  CommonUtil::UtilIsNetworkPath(v10, &v29, 0, v9);
  if ( !(_BYTE)v29 )
    return 0;
  v12 = 0;
  *(_QWORD *)v27 = 0;
  if ( v5 )
  {
    ImpersonationToken = CommonUtil::MpGetImpersonationToken((CommonUtil *)v5, (unsigned int)v27, v11);
    if ( ImpersonationToken < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          &WPP_e6a39d1dc444391637ddeaca3af09117_Traceguids,
          (unsigned int)ImpersonationToken);
      v14 = *(void **)v27;
      if ( !*(_QWORD *)v27 )
        return 0;
      goto LABEL_39;
    }
    v12 = *(void **)v27;
  }
  v28 = 0;
  CommonUtil::CAutoImpersonateToken::CAutoImpersonateToken((CommonUtil::CAutoImpersonateToken *)&v28, v12);
  *(_OWORD *)lpString1 = 0;
  *(__m128i *)cchCount1 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpString1[0]) = 0;
  v15 = v6;
  if ( *((_QWORD *)v6 + 3) > 7u )
    v15 = *(wchar_t **)v6;
  if ( (int)RealtimeProtection::DlpUtils::GetNormalizedNWSharePath(v15, lpString1) < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      if ( *((_QWORD *)v6 + 3) > 7u )
        v6 = *(wchar_t **)v6;
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_e6a39d1dc444391637ddeaca3af09117_Traceguids, v6);
    }
    goto LABEL_35;
  }
  *(_OWORD *)lpString2 = 0;
  *(__m128i *)cchCount2 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpString2[0]) = 0;
  v16 = v7;
  if ( v7[3] > 7u )
    v16 = (_QWORD *)*v7;
  if ( (int)RealtimeProtection::DlpUtils::GetNormalizedNWSharePath(v16, lpString2) < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      if ( v7[3] > 7u )
        v7 = (_QWORD *)*v7;
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_e6a39d1dc444391637ddeaca3af09117_Traceguids, v7);
    }
LABEL_34:
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(lpString2);
LABEL_35:
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(lpString1);
    if ( BYTE8(v28) )
      RevertToSelf();
    if ( !v12 )
      return 0;
    v14 = v12;
LABEL_39:
    CloseHandle(v14);
    return 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v18 = lpString2;
    if ( *(_QWORD *)&cchCount2[2] > 7u )
      v18 = (LPCWCH *)lpString2[0];
    v19 = lpString1;
    if ( *(_QWORD *)&cchCount1[2] > 7u )
      LODWORD(v19) = lpString1[0];
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      (unsigned int)&WPP_e6a39d1dc444391637ddeaca3af09117_Traceguids,
      (_DWORD)v19,
      (__int64)v18);
  }
  v20 = (const WCHAR *)lpString2;
  if ( *(_QWORD *)&cchCount2[2] > 7u )
    v20 = lpString2[0];
  v21 = (const WCHAR *)lpString1;
  if ( *(_QWORD *)&cchCount1[2] > 7u )
    v21 = lpString1[0];
  if ( CompareStringOrdinal(v21, cchCount1[0], v20, cchCount2[0], 1) != 2 )
  {
    if ( !a5 )
      goto LABEL_34;
    v23 = (const wchar_t *)lpString1;
    if ( *(_QWORD *)&cchCount1[2] > 7u )
      v23 = lpString1[0];
    v24 = (void **)lpString2;
    if ( *(_QWORD *)&cchCount2[2] > 7u )
      v24 = (void **)lpString2[0];
    if ( !RealtimeProtection::MpRtpIsSameFile(v24, v23, v22) )
    {
      if ( *((_QWORD *)v6 + 3) > 7u )
        v6 = *(wchar_t **)v6;
      v26 = (void **)lpString2;
      if ( *(_QWORD *)&cchCount2[2] > 7u )
        v26 = (void **)lpString2[0];
      if ( !RealtimeProtection::MpRtpIsSameFile(v26, v6, v25) )
        goto LABEL_34;
    }
  }
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(lpString2);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(lpString1);
  if ( BYTE8(v28) )
    RevertToSelf();
  if ( v12 )
    CloseHandle(v12);
  return 1;
}

```

## disassembly

```asm
0x18014e9b0  mov     [rsp-8+arg_0], rbx
0x18014e9b5  push    rbp
0x18014e9b6  push    rsi
0x18014e9b7  push    rdi
0x18014e9b8  push    r14
0x18014e9ba  push    r15
0x18014e9bc  lea     rbp, [rsp-2Fh]
0x18014e9c1  sub     rsp, 0A0h
0x18014e9c8  mov     rax, cs:__security_cookie
0x18014e9cf  xor     rax, rsp
0x18014e9d2  mov     [rbp+4Fh+var_30], rax
0x18014e9d6  mov     r14d, r9d
0x18014e9d9  mov     rdi, r8
0x18014e9dc  mov     rsi, rdx
0x18014e9df  xor     r15d, r15d
0x18014e9e2  test    cl, cl
0x18014e9e4  jz      loc_18014EBDA
0x18014e9ea  cmp     [rdx+10h], r15
0x18014e9ee  jz      loc_18014EBDA
0x18014e9f4  cmp     [r8+10h], r15
0x18014e9f8  jz      loc_18014EBDA
0x18014e9fe  mov     byte ptr [rbp+4Fh+var_78], r15b
0x18014ea02  mov     rcx, rdx
0x18014ea05  cmp     qword ptr [rdx+18h], 7
0x18014ea0a  jbe     short loc_18014EA0F
0x18014ea0c  mov     rcx, [rdx]; String1
0x18014ea0f  xor     r8d, r8d; bool *
0x18014ea12  lea     rdx, [rbp+4Fh+var_78]; wchar_t *
0x18014ea16  call    ?UtilIsNetworkPath@CommonUtil@@YAJPEB_WPEA_N1@Z; CommonUtil::UtilIsNetworkPath(wchar_t const *,bool *,bool *)
0x18014ea1b  cmp     byte ptr [rbp+4Fh+var_78], r15b
0x18014ea1f  jz      loc_18014EBDA
0x18014ea25  mov     rcx, rdi
0x18014ea28  cmp     qword ptr [rdi+18h], 7
0x18014ea2d  jbe     short loc_18014EA32
0x18014ea2f  mov     rcx, [rdi]; String1
0x18014ea32  xor     r8d, r8d; bool *
0x18014ea35  lea     rdx, [rbp+4Fh+var_78]; wchar_t *
0x18014ea39  call    ?UtilIsNetworkPath@CommonUtil@@YAJPEB_WPEA_N1@Z; CommonUtil::UtilIsNetworkPath(wchar_t const *,bool *,bool *)
0x18014ea3e  cmp     byte ptr [rbp+4Fh+var_78], r15b
0x18014ea42  jz      loc_18014EBDA
0x18014ea48  mov     rbx, r15
0x18014ea4b  mov     qword ptr [rbp+4Fh+var_90], rbx
0x18014ea4f  test    r14d, r14d
0x18014ea52  jz      short loc_18014EAAC
0x18014ea54  lea     rdx, [rbp+4Fh+var_90]; unsigned int
0x18014ea58  mov     ecx, r14d; this
0x18014ea5b  call    ?MpGetImpersonationToken@CommonUtil@@YAJKPEAPEAX@Z; CommonUtil::MpGetImpersonationToken(ulong,void * *)
0x18014ea60  test    eax, eax
0x18014ea62  jns     short loc_18014EAA8
0x18014ea64  lea     rdx, WPP_GLOBAL_Control
0x18014ea6b  mov     rcx, cs:WPP_GLOBAL_Control
0x18014ea72  cmp     rcx, rdx
0x18014ea75  jz      short loc_18014EA96
0x18014ea77  test    byte ptr [rcx+1Ch], 1
0x18014ea7b  jz      short loc_18014EA96
0x18014ea7d  mov     edx, 10h
0x18014ea82  mov     r9d, eax
0x18014ea85  lea     r8, WPP_e6a39d1dc444391637ddeaca3af09117_Traceguids
0x18014ea8c  mov     rcx, [rcx+10h]
0x18014ea90  call    WPP_SF_d
0x18014ea95  nop
0x18014ea96  mov     rcx, qword ptr [rbp+4Fh+var_90]
0x18014ea9a  test    rcx, rcx
0x18014ea9d  jz      loc_18014EBDA
0x18014eaa3  jmp     loc_18014EBD4
0x18014eaa8  mov     rbx, qword ptr [rbp+4Fh+var_90]
0x18014eaac  xorps   xmm0, xmm0
0x18014eaaf  movups  [rbp+4Fh+var_88], xmm0
0x18014eab3  mov     rdx, rbx; void *
0x18014eab6  lea     rcx, [rbp+4Fh+var_88]; this
0x18014eaba  call    ??0CAutoImpersonateToken@CommonUtil@@QEAA@PEAX@Z; CommonUtil::CAutoImpersonateToken::CAutoImpersonateToken(void *)
0x18014eabf  nop
0x18014eac0  xorps   xmm0, xmm0
0x18014eac3  movups  xmmword ptr [rbp+4Fh+lpString1], xmm0
0x18014eac7  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18014eacf  movdqu  xmmword ptr [rbp+4Fh+cchCount1], xmm1
0x18014ead4  mov     word ptr [rbp+4Fh+lpString1], r15w
0x18014ead9  mov     rcx, rdi
0x18014eadc  cmp     qword ptr [rdi+18h], 7
0x18014eae1  jbe     short loc_18014EAE6
0x18014eae3  mov     rcx, [rdi]
0x18014eae6  lea     rdx, [rbp+4Fh+lpString1]
0x18014eaea  call    ?GetNormalizedNWSharePath@DlpUtils@RealtimeProtection@@YAJPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; RealtimeProtection::DlpUtils::GetNormalizedNWSharePath(wchar_t const *,std::wstring &)
0x18014eaef  test    eax, eax
0x18014eaf1  jns     short loc_18014EB38
0x18014eaf3  lea     rdx, WPP_GLOBAL_Control
0x18014eafa  mov     rcx, cs:WPP_GLOBAL_Control
0x18014eb01  cmp     rcx, rdx
0x18014eb04  jz      loc_18014EBB5
0x18014eb0a  test    byte ptr [rcx+1Ch], 4
0x18014eb0e  jz      loc_18014EBB5
0x18014eb14  cmp     qword ptr [rdi+18h], 7
0x18014eb19  jbe     short loc_18014EB1E
0x18014eb1b  mov     rdi, [rdi]
0x18014eb1e  mov     edx, 11h
0x18014eb23  mov     r9, rdi
0x18014eb26  lea     r8, WPP_e6a39d1dc444391637ddeaca3af09117_Traceguids
0x18014eb2d  mov     rcx, [rcx+10h]
0x18014eb31  call    WPP_SF_S
0x18014eb36  jmp     short loc_18014EBB5
0x18014eb38  xorps   xmm0, xmm0
0x18014eb3b  movups  xmmword ptr [rbp+4Fh+lpString2], xmm0
0x18014eb3f  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18014eb47  movdqu  xmmword ptr [rbp+4Fh+cchCount2], xmm1
0x18014eb4c  mov     word ptr [rbp+4Fh+lpString2], r15w
0x18014eb51  mov     rcx, rsi
0x18014eb54  cmp     qword ptr [rsi+18h], 7
0x18014eb59  jbe     short loc_18014EB5E
0x18014eb5b  mov     rcx, [rsi]
0x18014eb5e  lea     rdx, [rbp+4Fh+lpString2]
0x18014eb62  call    ?GetNormalizedNWSharePath@DlpUtils@RealtimeProtection@@YAJPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; RealtimeProtection::DlpUtils::GetNormalizedNWSharePath(wchar_t const *,std::wstring &)
0x18014eb67  test    eax, eax
0x18014eb69  jns     loc_18014EBFF
0x18014eb6f  lea     rdx, WPP_GLOBAL_Control
0x18014eb76  mov     rcx, cs:WPP_GLOBAL_Control
0x18014eb7d  cmp     rcx, rdx
0x18014eb80  jz      short loc_18014EBAB
0x18014eb82  test    byte ptr [rcx+1Ch], 4
0x18014eb86  jz      short loc_18014EBAB
0x18014eb88  cmp     qword ptr [rsi+18h], 7
0x18014eb8d  jbe     short loc_18014EB92
0x18014eb8f  mov     rsi, [rsi]
0x18014eb92  mov     edx, 12h
0x18014eb97  mov     r9, rsi
0x18014eb9a  lea     r8, WPP_e6a39d1dc444391637ddeaca3af09117_Traceguids
0x18014eba1  mov     rcx, [rcx+10h]
0x18014eba5  call    WPP_SF_S
0x18014ebaa  nop
0x18014ebab  lea     rcx, [rbp+4Fh+lpString2]; void *
0x18014ebaf  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18014ebb4  nop
0x18014ebb5  lea     rcx, [rbp+4Fh+lpString1]; void *
0x18014ebb9  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18014ebbe  nop
0x18014ebbf  cmp     byte ptr [rbp+4Fh+var_88+8], r15b
0x18014ebc3  jz      short loc_18014EBCC
0x18014ebc5  call    cs:__imp_RevertToSelf
0x18014ebcb  nop
0x18014ebcc  test    rbx, rbx
0x18014ebcf  jz      short loc_18014EBDA
0x18014ebd1  mov     rcx, rbx; hObject
0x18014ebd4  call    cs:__imp_CloseHandle
0x18014ebda  xor     al, al
0x18014ebdc  mov     rcx, [rbp+4Fh+var_30]
0x18014ebe0  xor     rcx, rsp; StackCookie
0x18014ebe3  call    __security_check_cookie
0x18014ebe8  mov     rbx, [rsp+0C0h+arg_0]
0x18014ebf0  add     rsp, 0A0h
0x18014ebf7  pop     r15
0x18014ebf9  pop     r14
0x18014ebfb  pop     rdi
0x18014ebfc  pop     rsi
0x18014ebfd  pop     rbp
0x18014ebfe  retn
0x18014ebff  lea     rdx, WPP_GLOBAL_Control
0x18014ec06  mov     rcx, cs:WPP_GLOBAL_Control
0x18014ec0d  cmp     rcx, rdx
0x18014ec10  jz      short loc_18014EC4E
0x18014ec12  test    byte ptr [rcx+1Ch], 4
0x18014ec16  jz      short loc_18014EC4E
0x18014ec18  lea     rax, [rbp+4Fh+lpString2]
0x18014ec1c  cmp     qword ptr [rbp+4Fh+cchCount2+8], 7
0x18014ec21  cmova   rax, [rbp+4Fh+lpString2]
0x18014ec26  lea     r9, [rbp+4Fh+lpString1]
0x18014ec2a  cmp     qword ptr [rbp+4Fh+cchCount1+8], 7
0x18014ec2f  cmova   r9, [rbp+4Fh+lpString1]
0x18014ec34  mov     edx, 13h
0x18014ec39  mov     qword ptr [rsp+0C0h+bIgnoreCase], rax
0x18014ec3e  lea     r8, WPP_e6a39d1dc444391637ddeaca3af09117_Traceguids
0x18014ec45  mov     rcx, [rcx+10h]
0x18014ec49  call    WPP_SF_SS
0x18014ec4e  lea     r8, [rbp+4Fh+lpString2]
0x18014ec52  cmp     qword ptr [rbp+4Fh+cchCount2+8], 7
0x18014ec57  cmova   r8, [rbp+4Fh+lpString2]; lpString2
0x18014ec5c  lea     rcx, [rbp+4Fh+lpString1]
0x18014ec60  cmp     qword ptr [rbp+4Fh+cchCount1+8], 7
0x18014ec65  cmova   rcx, [rbp+4Fh+lpString1]; lpString1
0x18014ec6a  mov     [rsp+0C0h+bIgnoreCase], 1; bIgnoreCase
0x18014ec72  mov     r9d, [rbp+4Fh+cchCount2]; cchCount2
0x18014ec76  mov     edx, [rbp+4Fh+cchCount1]; cchCount1
0x18014ec79  call    cs:__imp_CompareStringOrdinal
0x18014ec7f  cmp     eax, 2
0x18014ec82  jz      short loc_18014ECDB
0x18014ec84  cmp     [rbp+4Fh+arg_20], r15b
0x18014ec88  jz      loc_18014EBAB
0x18014ec8e  lea     rdx, [rbp+4Fh+lpString1]
0x18014ec92  cmp     qword ptr [rbp+4Fh+cchCount1+8], 7
0x18014ec97  cmova   rdx, [rbp+4Fh+lpString1]; wchar_t *
0x18014ec9c  lea     rcx, [rbp+4Fh+lpString2]
0x18014eca0  cmp     qword ptr [rbp+4Fh+cchCount2+8], 7
0x18014eca5  cmova   rcx, [rbp+4Fh+lpString2]; this
0x18014ecaa  call    ?MpRtpIsSameFile@RealtimeProtection@@YA_NPEB_W0@Z; RealtimeProtection::MpRtpIsSameFile(wchar_t const *,wchar_t const *)
0x18014ecaf  test    al, al
0x18014ecb1  jnz     short loc_18014ECDB
0x18014ecb3  cmp     qword ptr [rdi+18h], 7
0x18014ecb8  jbe     short loc_18014ECBD
0x18014ecba  mov     rdi, [rdi]
0x18014ecbd  lea     rcx, [rbp+4Fh+lpString2]
0x18014ecc1  cmp     qword ptr [rbp+4Fh+cchCount2+8], 7
0x18014ecc6  cmova   rcx, [rbp+4Fh+lpString2]; this
0x18014eccb  mov     rdx, rdi; wchar_t *
0x18014ecce  call    ?MpRtpIsSameFile@RealtimeProtection@@YA_NPEB_W0@Z; RealtimeProtection::MpRtpIsSameFile(wchar_t const *,wchar_t const *)
0x18014ecd3  test    al, al
0x18014ecd5  jz      loc_18014EBAB
0x18014ecdb  lea     rcx, [rbp+4Fh+lpString2]; void *
0x18014ecdf  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18014ece4  nop
0x18014ece5  lea     rcx, [rbp+4Fh+lpString1]; void *
0x18014ece9  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x18014ecee  nop
0x18014ecef  cmp     byte ptr [rbp+4Fh+var_88+8], r15b
0x18014ecf3  jz      short loc_18014ECFC
0x18014ecf5  call    cs:__imp_RevertToSelf
0x18014ecfb  nop
0x18014ecfc  test    rbx, rbx
0x18014ecff  jz      short loc_18014ED0A
0x18014ed01  mov     rcx, rbx; hObject
0x18014ed04  call    cs:__imp_CloseHandle
0x18014ed0a  mov     al, 1
0x18014ed0c  jmp     loc_18014EBDC
```
