# CGatherNotifyInline::OnDataChangeWithAumid(ulong,_INLINE_NOTIFY_DATA_CHANGE_ENTRY * const,wchar_t const *,ulong * const,long * const)

- ea: `0x1800a30b0`
- end: `0x1800a35d2`
- name: `?OnDataChangeWithAumid@CGatherNotifyInline@@UEAAJKQEAU_INLINE_NOTIFY_DATA_CHANGE_ENTRY@@PEB_WQEAKQEAJ@Z`
- size: `1314`
- prototype: `int(CGatherNotifyInline *__hidden this, unsigned int, struct _INLINE_NOTIFY_DATA_CHANGE_ENTRY *const, const wchar_t *, unsigned int *const, int *const)`
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180009be8`
- `0x18000f880`
- `0x18002b620`
- `0x1800495c0`
- `0x18006a618`
- `0x1800a1490`
- `0x1800a30b0`
- `0x1800a35d8`
- `0x1800eacf8`
- `0x1800f8f24`
- `0x180104880`
- `0x1801244c0`
- `0x18015bf20`
- `0x180161950`
- `0x180161e58`
- `0x180161f40`
- `0x18019d12c`
- `0x18019d1b8`
- `0x18019d27c`
- `0x180241010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a33ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a33ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a33bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a33bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a34c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a350c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a357f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a34c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a350c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a357f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800a31d9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800a31d9`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800a3199`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800a3199`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a342a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a3518`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a342a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a3518`
- `efswrt!CdplProtectSecretToLevel` at `0x1800a347f`
- `efswrt!CdplProtectSecretToLevel` at `0x1800a347f`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CGatherNotifyInline::OnDataChangeWithAumid(
        CGatherNotifyInline *this,
        unsigned int a2,
        struct _INLINE_NOTIFY_DATA_CHANGE_ENTRY *const a3,
        const wchar_t *a4,
        unsigned int *const a5,
        int *const a6)
{
  int v6; // r12d
  unsigned int LastError; // ebx
  __int64 v11; // rdx
  HRESULT v12; // eax
  unsigned int i; // edi
  __int64 v14; // rbx
  const wchar_t *v15; // rdx
  const wchar_t *v16; // rcx
  unsigned __int64 v17; // rdx
  CRegistry *v18; // rbx
  struct _RTL_CRITICAL_SECTION *v19; // rdi
  __int64 v20; // rax
  void *v21; // rbx
  const char *v22; // r9
  void *v23; // rcx
  int v24; // ebx
  void *v25; // rdi
  void *v26; // rcx
  int v27; // eax
  int v29; // [rsp+20h] [rbp-318h]
  _BYTE v30[4]; // [rsp+40h] [rbp-2F8h] BYREF
  int v31; // [rsp+44h] [rbp-2F4h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-2F0h] BYREF
  int v33; // [rsp+50h] [rbp-2E8h] BYREF
  int v34; // [rsp+58h] [rbp-2E0h] BYREF
  LPVOID v35; // [rsp+60h] [rbp-2D8h]
  int v36; // [rsp+68h] [rbp-2D0h]
  LPVOID *p_pv; // [rsp+70h] [rbp-2C8h] BYREF
  __int64 v38; // [rsp+78h] [rbp-2C0h] BYREF
  int v39; // [rsp+80h] [rbp-2B8h]
  int *v40; // [rsp+98h] [rbp-2A0h]
  char *v41; // [rsp+A0h] [rbp-298h]
  const int *v42; // [rsp+B0h] [rbp-288h] BYREF
  wchar_t *v43; // [rsp+B8h] [rbp-280h]
  __int64 v44; // [rsp+C0h] [rbp-278h]
  __int16 v45; // [rsp+C8h] [rbp-270h] BYREF
  void **v46; // [rsp+110h] [rbp-228h] BYREF
  int v47; // [rsp+118h] [rbp-220h]
  void **v48; // [rsp+128h] [rbp-210h]
  __int16 *v49; // [rsp+130h] [rbp-208h]
  __int64 v50; // [rsp+138h] [rbp-200h]
  __int16 v51; // [rsp+140h] [rbp-1F8h] BYREF
  int v52; // [rsp+2E8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+0h]

  v6 = (int)a4;
  v40 = a6;
  if ( g_pGatheringService )
  {
    _InterlockedAdd((volatile signed __int32 *)g_pGatheringService + 1670, a2);
    if ( !*((_DWORD *)this + 24) )
    {
      LastError = -2147418113;
      v11 = 175;
      goto LABEL_3;
    }
    if ( !*((_QWORD *)this + 14) )
    {
      LastError = -2147467261;
      v11 = 176;
      goto LABEL_3;
    }
    v43 = (wchar_t *)&v45;
    v44 = 33;
    v45 = 0;
    v42 = &TLMString<32,32,1024>::`vftable';
    if ( *((_DWORD *)this + 26) || IsCDPLEnabled() )
    {
      v12 = CoImpersonateClient();
      LastError = v12;
      v31 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB7,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgthrntfyinline.cxx",
          (const char *)(unsigned int)v12,
          v29);
LABEL_51:
        TLMString<32,32,1024>::~TLMString<32,32,1024>(&v42);
        return LastError;
      }
      CAccessControlImpl::GetuserSidFromToken((CLMString *)&v42);
      CoRevertToSelf();
    }
    for ( i = 0; i < a2; ++i )
    {
      v14 = 32LL * i;
      *(_DWORD *)((char *)a3 + v14) |= 0x1000000u;
      if ( !i )
      {
        v15 = *(const wchar_t **)((char *)a3 + v14 + 24);
        if ( v15 )
        {
          if ( !CUserSettings::IsUserSidAvailable((CRegistry *)((char *)g_pGatheringService + 6688), v15) )
            SearchIndexerDiagnosticTelemetry::UserProfileNotFound();
        }
      }
      if ( *((_DWORD *)this + 26) && !*(_QWORD *)((char *)a3 + v14 + 24) )
      {
        v47 = 0;
        v49 = &v51;
        v50 = 193;
        v51 = 0;
        v48 = &TLMString<192,64,32767>::`vftable';
        v46 = &CComObjectStackRefCount<CURL>::`vftable';
        v52 = 0;
        try
        {
          CURL::Init((CURL *)&v46, *(const wchar_t **)((char *)a3 + v14 + 8), 0xFFFFFFFF);
        }
        catch ( ... )
        {
          indexer::result::details::result_from_caught_exception<1>(
            retaddr,
            209,
            "onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgthrntfyinline.cxx");
        }
        CURLSecurityCheckBySid::CURLSecurityCheckBySid((CURLSecurityCheckBySid *)&p_pv, (struct CURL *)&v46);
        if ( !(unsigned int)CURLSecurityCheckBySid::AccessCheckBySid((CURLSecurityCheckBySid *)&p_pv, v43) )
        {
          LastError = -2147024891;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xD5,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgthrntfyinline.cxx",
            (const char *)0x80070005LL,
            v29);
          CComObjectStackRefCount<CURL>::~CComObjectStackRefCount<CURL>(&v46);
          goto LABEL_51;
        }
        CComObjectStackRefCount<CURL>::~CComObjectStackRefCount<CURL>(&v46);
      }
    }
    v35 = 0;
    v34 = 0;
    v33 = 0;
    v36 = 0;
    if ( a2 == 1 && (*(_DWORD *)a3 & 0xF) != 1 && IsCDPLEnabled() )
    {
      v16 = (const wchar_t *)*((_QWORD *)a3 + 1);
      v17 = -1;
      do
        ++v17;
      while ( v16[v17] );
      if ( IsWinRTURL(v16, v17) )
      {
        v18 = g_pGatheringService;
        LODWORD(p_pv) = 0;
        v38 = 0;
        v39 = 0;
        CUserTokenKey::Init((CUserTokenKey *)&p_pv, v43);
        v19 = (struct _RTL_CRITICAL_SECTION *)((char *)v18 + 7056);
        v41 = (char *)v18 + 7056;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)v18 + 7056));
        v20 = CTKPLiteHashMap<CUserTokenKey,CUserTokenValue>::Lookup((char *)v18 + 6752, &p_pv);
        if ( v20 )
          v21 = *(void **)(v20 + 40);
        else
          v21 = 0;
        LeaveCriticalSection(v19);
        v30[0] = 0;
        if ( !CImpersonateLogonUser::Impersonate((CImpersonateLogonUser *)v30, v21) )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0xE3,
                        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgthrntfyinline.cxx",
                        v22);
LABEL_37:
          if ( v30[0] )
            RevertToSelf();
          CBlob::Free((CBlob *)&v33);
          goto LABEL_51;
        }
        pv = 0;
        v31 = 0;
        p_pv = &pv;
        v38 = 0;
        LOBYTE(v39) = 1;
        LastError = CdplProtectSecretToLevel(
                      2,
                      *(_QWORD *)(*((_QWORD *)a3 + 2) + 8LL),
                      **((unsigned int **)a3 + 2),
                      &v38);
        wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
        if ( (LastError & 0x80000000) != 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xED,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgthrntfyinline.cxx",
            (const char *)LastError,
            (int)&v31);
          v23 = pv;
          pv = 0;
          if ( v23 )
            CoTaskMemFree(v23);
          goto LABEL_37;
        }
        v24 = v31;
        v25 = pv;
        pv = 0;
        CBlob::Free((CBlob *)&v33);
        v34 = v24;
        v35 = v25;
        *((_QWORD *)a3 + 2) = &v34;
        v26 = pv;
        pv = 0;
        if ( v26 )
          CoTaskMemFree(v26);
        if ( v30[0] )
          RevertToSelf();
      }
    }
    v27 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, struct _INLINE_NOTIFY_DATA_CHANGE_ENTRY *const))(**((_QWORD **)this + 14) + 32LL))(
            *((_QWORD *)this + 14),
            *((unsigned int *)this + 25),
            a2,
            a3);
    LastError = v27;
    if ( v27 >= 0 )
    {
      CBlob::Free((CBlob *)&v33);
      LastError = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF4,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgthrntfyinline.cxx",
        (const char *)(unsigned int)v27,
        v6);
      if ( v34 )
      {
        CoTaskMemFree(v35);
        v35 = 0;
        v34 = 0;
        v33 = 0;
      }
    }
    goto LABEL_51;
  }
  LastError = -2147215342;
  v11 = 171;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgthrntfyinline.cxx",
    (const char *)LastError,
    v29);
  return LastError;
}

```

## disassembly

```asm
0x1800a30b0  push    rbx
0x1800a30b2  push    rsi
0x1800a30b3  push    rdi
0x1800a30b4  push    r12
0x1800a30b6  push    r13
0x1800a30b8  push    r14
0x1800a30ba  push    r15
0x1800a30bc  sub     rsp, 300h
0x1800a30c3  mov     rax, cs:__security_cookie
0x1800a30ca  xor     rax, rsp
0x1800a30cd  mov     [rsp+338h+var_48], rax
0x1800a30d5  mov     r12, r9
0x1800a30d8  mov     rsi, r8
0x1800a30db  mov     r15d, edx
0x1800a30de  mov     r14, rcx
0x1800a30e1  mov     r13, [rsp+338h+arg_20]
0x1800a30e9  mov     rax, [rsp+338h+arg_28]
0x1800a30f1  mov     [rsp+338h+var_2A0], rax
0x1800a30f9  mov     rax, cs:?g_pGatheringService@@3PEAVCGatheringService@@EA; CGatheringService * g_pGatheringService
0x1800a3100  xor     ebx, ebx
0x1800a3102  test    rax, rax
0x1800a3105  jnz     short loc_1800A312D
0x1800a3107  mov     ebx, 80041812h
0x1800a310c  mov     edx, 0ABh; void *
0x1800a3111  mov     rcx, [rsp+338h]; this
0x1800a3119  mov     r9d, ebx; char *
0x1800a311c  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800a3123  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3128  jmp     loc_1800A35AD
0x1800a312d  lock add [rax+1A18h], r15d
0x1800a3135  cmp     [rcx+60h], ebx
0x1800a3138  jnz     short loc_1800A3146
0x1800a313a  mov     ebx, 8000FFFFh
0x1800a313f  mov     edx, 0AFh
0x1800a3144  jmp     short loc_1800A3111
0x1800a3146  cmp     [rcx+70h], rbx
0x1800a314a  jnz     short loc_1800A3158
0x1800a314c  mov     ebx, 80004003h
0x1800a3151  mov     edx, 0B0h
0x1800a3156  jmp     short loc_1800A3111
0x1800a3158  lea     rax, [rsp+338h+var_270]
0x1800a3160  mov     [rsp+338h+var_280], rax
0x1800a3168  mov     [rsp+338h+var_278], 21h ; '!'
0x1800a3174  mov     [rsp+338h+var_270], bx
0x1800a317c  lea     rax, ??_7?$TLMString@$0CA@$0CA@$0EAA@@@6B@; const TLMString<32,32,1024>::`vftable'
0x1800a3183  mov     [rsp+338h+var_288], rax
0x1800a318b  cmp     [rcx+68h], ebx
0x1800a318e  jnz     short loc_1800A3199
0x1800a3190  call    ?IsCDPLEnabled@@YA_NXZ; IsCDPLEnabled(void)
0x1800a3195  test    al, al
0x1800a3197  jz      short loc_1800A31E1
0x1800a3199  call    cs:__imp_CoImpersonateClient
0x1800a319f  mov     ebx, eax
0x1800a31a1  mov     [rsp+338h+var_2F4], eax
0x1800a31a5  test    eax, eax
0x1800a31a7  jns     short loc_1800A31CB
0x1800a31a9  mov     rcx, [rsp+338h]; this
0x1800a31b1  mov     r9d, eax; char *
0x1800a31b4  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800a31bb  mov     edx, 0B7h; void *
0x1800a31c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a31c5  nop
0x1800a31c6  jmp     loc_1800A35A0
0x1800a31cb  lea     rcx, [rsp+338h+var_288]; this
0x1800a31d3  call    ?GetuserSidFromToken@CAccessControlImpl@@SAXAEAV?$TLMString@$0CA@$0CA@$0EAA@@@@Z; CAccessControlImpl::GetuserSidFromToken(TLMString<32,32,1024> &)
0x1800a31d8  nop
0x1800a31d9  call    cs:__imp_CoRevertToSelf
0x1800a31df  xor     ebx, ebx
0x1800a31e1  mov     edi, ebx
0x1800a31e3  cmp     edi, r15d
0x1800a31e6  jnb     loc_1800A332F
0x1800a31ec  mov     ebx, edi
0x1800a31ee  shl     rbx, 5
0x1800a31f2  bts     dword ptr [rbx+rsi], 18h
0x1800a31f7  xor     ecx, ecx
0x1800a31f9  test    edi, edi
0x1800a31fb  jnz     short loc_1800A3227
0x1800a31fd  mov     rdx, [rbx+rsi+18h]; wchar_t *
0x1800a3202  test    rdx, rdx
0x1800a3205  jz      short loc_1800A3227
0x1800a3207  mov     rcx, cs:?g_pGatheringService@@3PEAVCGatheringService@@EA; CGatheringService * g_pGatheringService
0x1800a320e  add     rcx, 1A20h; this
0x1800a3215  call    ?IsUserSidAvailable@CUserSettings@@QEAA_NPEB_W@Z; CUserSettings::IsUserSidAvailable(wchar_t const *)
0x1800a321a  xor     ecx, ecx
0x1800a321c  test    al, al
0x1800a321e  jnz     short loc_1800A3227
0x1800a3220  call    ?UserProfileNotFound@SearchIndexerDiagnosticTelemetry@@SAXXZ; SearchIndexerDiagnosticTelemetry::UserProfileNotFound(void)
0x1800a3225  xor     ecx, ecx
0x1800a3227  cmp     [r14+68h], ecx
0x1800a322b  jz      loc_1800A3326
0x1800a3231  cmp     [rbx+rsi+18h], rcx
0x1800a3236  jnz     loc_1800A3326
0x1800a323c  mov     [rsp+338h+var_220], ecx
0x1800a3243  lea     rax, [rsp+338h+var_1F8]
0x1800a324b  mov     [rsp+338h+var_208], rax
0x1800a3253  mov     [rsp+338h+var_200], 0C1h
0x1800a325f  mov     [rsp+338h+var_1F8], cx
0x1800a3267  lea     rax, ??_7?$TLMString@$0MA@$0EA@$0HPPP@@@6B@; const TLMString<192,64,32767>::`vftable'
0x1800a326e  mov     [rsp+338h+var_210], rax
0x1800a3276  lea     rax, ??_7?$CComObjectStackRefCount@VCURL@@@@6B@; const CComObjectStackRefCount<CURL>::`vftable'
0x1800a327d  mov     [rsp+338h+var_228], rax
0x1800a3285  mov     [rsp+338h+var_50], ecx
0x1800a328c  or      r8d, 0FFFFFFFFh; unsigned int
0x1800a3290  mov     rdx, [rbx+rsi+8]; wchar_t *
0x1800a3295  lea     rcx, [rsp+338h+var_228]; this
0x1800a329d  call    ?Init@CURL@@QEAAJPEB_WK@Z; CURL::Init(wchar_t const *,ulong)
0x1800a32a2  nop
0x1800a32a3  lea     rdx, [rsp+338h+var_228]; struct CURL *
0x1800a32ab  lea     rcx, [rsp+338h+var_2C8]; this
0x1800a32b0  call    ??0CURLSecurityCheckBySid@@QEAA@AEAVCURL@@@Z; CURLSecurityCheckBySid::CURLSecurityCheckBySid(CURL &)
0x1800a32b5  mov     rdx, [rsp+338h+var_280]; wchar_t *
0x1800a32bd  lea     rcx, [rsp+338h+var_2C8]; this
0x1800a32c2  call    ?AccessCheckBySid@CURLSecurityCheckBySid@@UEBAHPEB_W@Z; CURLSecurityCheckBySid::AccessCheckBySid(wchar_t const *)
0x1800a32c7  xor     ebx, ebx
0x1800a32c9  test    eax, eax
0x1800a32cb  jnz     short loc_1800A3301
0x1800a32cd  mov     rcx, [rsp+338h]; this
0x1800a32d5  mov     ebx, 80070005h
0x1800a32da  mov     r9d, ebx; char *
0x1800a32dd  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800a32e4  mov     edx, 0D5h; void *
0x1800a32e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a32ee  nop
0x1800a32ef  lea     rcx, [rsp+338h+var_228]
0x1800a32f7  call    ??1?$CComObjectStackRefCount@VCURL@@@@QEAA@XZ; CComObjectStackRefCount<CURL>::~CComObjectStackRefCount<CURL>(void)
0x1800a32fc  jmp     loc_1800A35A0
0x1800a3301  lea     rcx, [rsp+338h+var_228]
0x1800a3309  call    ??1?$CComObjectStackRefCount@VCURL@@@@QEAA@XZ; CComObjectStackRefCount<CURL>::~CComObjectStackRefCount<CURL>(void)
0x1800a330e  jmp     short loc_1800A3328
0x1800a3310  lea     rcx, [rsp+338h+var_228]
0x1800a3318  call    ??1?$CComObjectStackRefCount@VCURL@@@@QEAA@XZ; CComObjectStackRefCount<CURL>::~CComObjectStackRefCount<CURL>(void)
0x1800a331d  mov     ebx, [rsp+338h+var_2F4]
0x1800a3321  jmp     loc_1800A35A0
0x1800a3326  xor     ebx, ebx
0x1800a3328  inc     edi
0x1800a332a  jmp     loc_1800A31E3
0x1800a332f  mov     [rsp+338h+var_2D8], rbx
0x1800a3334  mov     [rsp+338h+var_2E0], ebx
0x1800a3338  mov     [rsp+338h+var_2E8], ebx
0x1800a333c  mov     [rsp+338h+var_2D0], ebx
0x1800a3340  cmp     r15d, 1
0x1800a3344  jnz     loc_1800A351E
0x1800a334a  mov     eax, [rsi]
0x1800a334c  and     al, 0Fh
0x1800a334e  cmp     al, r15b
0x1800a3351  jz      loc_1800A351E
0x1800a3357  call    ?IsCDPLEnabled@@YA_NXZ; IsCDPLEnabled(void)
0x1800a335c  test    al, al
0x1800a335e  jz      loc_1800A351E
0x1800a3364  mov     rcx, [rsi+8]; wchar_t *
0x1800a3368  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800a336c  inc     rdx; unsigned __int64
0x1800a336f  cmp     [rcx+rdx*2], bx
0x1800a3373  jnz     short loc_1800A336C
0x1800a3375  call    ?IsWinRTURL@@YA_NPEB_W_K@Z; IsWinRTURL(wchar_t const *,unsigned __int64)
0x1800a337a  test    al, al
0x1800a337c  jz      loc_1800A351E
0x1800a3382  mov     rbx, cs:?g_pGatheringService@@3PEAVCGatheringService@@EA; CGatheringService * g_pGatheringService
0x1800a3389  xor     eax, eax
0x1800a338b  mov     dword ptr [rsp+338h+var_2C8], eax
0x1800a338f  mov     [rsp+338h+var_2C0], rax
0x1800a3394  mov     [rsp+338h+var_2B8], eax
0x1800a339b  mov     rdx, [rsp+338h+var_280]; wchar_t *
0x1800a33a3  lea     rcx, [rsp+338h+var_2C8]; this
0x1800a33a8  call    ?Init@CUserTokenKey@@QEAAXPEB_W@Z; CUserTokenKey::Init(wchar_t const *)
0x1800a33ad  lea     rdi, [rbx+1B90h]
0x1800a33b4  mov     [rsp+338h+var_298], rdi
0x1800a33bc  mov     rcx, rdi; lpCriticalSection
0x1800a33bf  call    cs:__imp_EnterCriticalSection
0x1800a33c5  nop
0x1800a33c6  lea     rcx, [rbx+1A60h]
0x1800a33cd  lea     rdx, [rsp+338h+var_2C8]
0x1800a33d2  call    ?Lookup@?$CTKPLiteHashMap@VCUserTokenKey@@VCUserTokenValue@@@@QEBAPEAVCUserTokenValue@@PEBVCUserTokenKey@@@Z; CTKPLiteHashMap<CUserTokenKey,CUserTokenValue>::Lookup(CUserTokenKey const *)
0x1800a33d7  xor     ecx, ecx
0x1800a33d9  test    rax, rax
0x1800a33dc  jz      short loc_1800A33E4
0x1800a33de  mov     rbx, [rax+28h]
0x1800a33e2  jmp     short loc_1800A33E7
0x1800a33e4  mov     rbx, rcx
0x1800a33e7  mov     rcx, rdi; lpCriticalSection
0x1800a33ea  call    cs:__imp_LeaveCriticalSection
0x1800a33f0  xor     edi, edi
0x1800a33f2  mov     [rsp+338h+var_2F8], dil
0x1800a33f7  mov     rdx, rbx; void *
0x1800a33fa  lea     rcx, [rsp+338h+var_2F8]; this
0x1800a33ff  call    ?Impersonate@CImpersonateLogonUser@@QEAA_NPEAX@Z; CImpersonateLogonUser::Impersonate(void *)
0x1800a3404  test    al, al
0x1800a3406  jnz     short loc_1800A3440
0x1800a3408  mov     rcx, [rsp+338h]; this
0x1800a3410  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800a3417  mov     edx, 0E3h; void *
0x1800a341c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a3421  mov     ebx, eax
0x1800a3423  cmp     [rsp+338h+var_2F8], dil
0x1800a3428  jz      short loc_1800A3431
0x1800a342a  call    cs:__imp_RevertToSelf
0x1800a3430  nop
0x1800a3431  lea     rcx, [rsp+338h+var_2E8]; this
0x1800a3436  call    ?Free@CBlob@@AEAAXXZ; CBlob::Free(void)
0x1800a343b  jmp     loc_1800A35A0
0x1800a3440  mov     [rsp+338h+pv], rdi
0x1800a3445  mov     [rsp+338h+var_2F4], edi
0x1800a3449  lea     rax, [rsp+338h+pv]
0x1800a344e  mov     [rsp+338h+var_2C8], rax
0x1800a3453  mov     [rsp+338h+var_2C0], rdi
0x1800a3458  mov     byte ptr [rsp+338h+var_2B8], 1
0x1800a3460  mov     rdx, [rsi+10h]
0x1800a3464  lea     rax, [rsp+338h+var_2F4]
0x1800a3469  mov     qword ptr [rsp+338h+var_318], rax; int
0x1800a346e  lea     r9, [rsp+338h+var_2C0]
0x1800a3473  mov     r8d, [rdx]
0x1800a3476  mov     rdx, [rdx+8]
0x1800a347a  mov     ecx, 2
0x1800a347f  call    cs:__imp_CdplProtectSecretToLevel
0x1800a3485  mov     ebx, eax
0x1800a3487  lea     rcx, [rsp+338h+var_2C8]
0x1800a348c  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800a3491  test    ebx, ebx
0x1800a3493  jns     short loc_1800A34CF
0x1800a3495  mov     rcx, [rsp+338h]; this
0x1800a349d  mov     r9d, ebx; char *
0x1800a34a0  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800a34a7  mov     edx, 0EDh; void *
0x1800a34ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a34b1  mov     rcx, [rsp+338h+pv]; pv
0x1800a34b6  mov     [rsp+338h+pv], rdi
0x1800a34bb  test    rcx, rcx
0x1800a34be  jz      loc_1800A3423
0x1800a34c4  call    cs:__imp_CoTaskMemFree
0x1800a34ca  jmp     loc_1800A3423
0x1800a34cf  mov     ebx, [rsp+338h+var_2F4]
0x1800a34d3  mov     rdi, [rsp+338h+pv]
0x1800a34d8  xor     ecx, ecx
0x1800a34da  mov     [rsp+338h+pv], rcx
0x1800a34df  lea     rcx, [rsp+338h+var_2E8]; this
0x1800a34e4  call    ?Free@CBlob@@AEAAXXZ; CBlob::Free(void)
0x1800a34e9  mov     [rsp+338h+var_2E0], ebx
0x1800a34ed  mov     [rsp+338h+var_2D8], rdi
0x1800a34f2  lea     rax, [rsp+338h+var_2E0]
0x1800a34f7  mov     [rsi+10h], rax
0x1800a34fb  mov     rcx, [rsp+338h+pv]; pv
0x1800a3500  xor     ebx, ebx
0x1800a3502  mov     [rsp+338h+pv], rbx
0x1800a3507  test    rcx, rcx
0x1800a350a  jz      short loc_1800A3512
0x1800a350c  call    cs:__imp_CoTaskMemFree
0x1800a3512  cmp     [rsp+338h+var_2F8], bl
0x1800a3516  jz      short loc_1800A351E
0x1800a3518  call    cs:__imp_RevertToSelf
0x1800a351e  mov     rcx, [r14+70h]
0x1800a3522  mov     rax, [rcx]
0x1800a3525  mov     rdx, [rsp+338h+var_2A0]
0x1800a352d  mov     [rsp+338h+var_308], rdx
0x1800a3532  mov     [rsp+338h+var_310], r13
0x1800a3537  mov     qword ptr [rsp+338h+var_318], r12; int
0x1800a353c  mov     r9, rsi
0x1800a353f  mov     r8d, r15d
0x1800a3542  mov     edx, [r14+64h]
0x1800a3546  mov     rax, [rax+20h]
0x1800a354a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a354f  mov     ebx, eax
0x1800a3551  xor     esi, esi
0x1800a3553  test    eax, eax
0x1800a3555  jns     short loc_1800A3594
0x1800a3557  mov     rcx, [rsp+338h]; this
0x1800a355f  mov     r9d, eax; char *
0x1800a3562  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800a3569  mov     edx, 0F4h; void *
0x1800a356e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3573  nop
0x1800a3574  cmp     [rsp+338h+var_2E0], esi
0x1800a3578  jz      short loc_1800A35A0
0x1800a357a  mov     rcx, [rsp+338h+var_2D8]; pv
0x1800a357f  call    cs:__imp_CoTaskMemFree
0x1800a3585  mov     [rsp+338h+var_2D8], rsi
0x1800a358a  mov     [rsp+338h+var_2E0], esi
0x1800a358e  mov     [rsp+338h+var_2E8], esi
0x1800a3592  jmp     short loc_1800A35A0
0x1800a3594  lea     rcx, [rsp+338h+var_2E8]; this
0x1800a3599  call    ?Free@CBlob@@AEAAXXZ; CBlob::Free(void)
0x1800a359e  mov     ebx, esi
0x1800a35a0  lea     rcx, [rsp+338h+var_288]
0x1800a35a8  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x1800a35ad  mov     eax, ebx
0x1800a35af  mov     rcx, [rsp+338h+var_48]
0x1800a35b7  xor     rcx, rsp; StackCookie
0x1800a35ba  call    __security_check_cookie
0x1800a35bf  add     rsp, 300h
0x1800a35c6  pop     r15
0x1800a35c8  pop     r14
0x1800a35ca  pop     r13
0x1800a35cc  pop     r12
0x1800a35ce  pop     rdi
0x1800a35cf  pop     rsi
0x1800a35d0  pop     rbx
0x1800a35d1  retn
```
