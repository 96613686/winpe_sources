# APP_POOL_CONFIG_STORE::SetTokenForWorkerProcesses(ushort const *,ushort const *,ulong,ulong,int,ushort const *,void *)

- ea: `0x180037234`
- end: `0x180037653`
- name: `?SetTokenForWorkerProcesses@APP_POOL_CONFIG_STORE@@AEAAHPEBG0KKH0PEAX@Z`
- size: `1055`
- prototype: `__int64 __usercall@<rax>(APP_POOL_CONFIG_STORE *__hidden this@<rcx>, LPWSTR AccountName@<rdx>, wchar_t *String1@<r8>, unsigned int@<r9d>, unsigned int, int, const unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180036128`
- `0x180036614`

## callees

- `0x180005878`
- `0x180035ecc`
- `0x1800362d8`
- `0x180037234`
- `0x18003765c`
- `0x18005f32c`
- `0x180060cc0`
- `0x18006101a`
- `0x180061026`
- `0x180061060`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800373ea`
- `ntdll!RtlNtStatusToDosError` at `0x1800373ea`
- `logoncli!NetIsServiceAccount` at `0x1800373de`
- `logoncli!NetIsServiceAccount` at `0x1800373de`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800375e4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800375e4`
- `iisutil!PuDbgPrintError` at `0x180037439`
- `iisutil!PuDbgPrintError` at `0x180037439`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003731a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003731a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18003734c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18003734c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800372a2`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800372a2`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180037332`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180037332`
- `iisutil!GetTokenSID` at `0x180037584`
- `iisutil!GetTokenSID` at `0x180037584`

## string_xrefs

- `0x18003749a`: `NT AUTHORITY\NetworkService`
- `0x1800374a3`: `NT AUTHORITY\LocalService`
- `0x180037428`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool_config_store.cxx`
- `0x180037409`: `Failed to determine if account %S is "password managed service account"`
- `0x18003741a`: `APP_POOL_CONFIG_STORE::SetTokenForWorkerProcesses`

## pseudocode

```c
_BOOL8 __fastcall APP_POOL_CONFIG_STORE::SetTokenForWorkerProcesses(
        struct TOKEN_CACHE_ENTRY **this,
        LPWSTR AccountName,
        wchar_t *String1,
        int a4,
        unsigned int a5,
        int a6,
        unsigned __int16 *a7,
        struct TOKEN_CACHE_ENTRY *pSid)
{
  struct TOKEN_CACHE_ENTRY *Owner; // r15
  signed int v12; // edi
  int v14; // ebx
  int v15; // ebx
  int v16; // ebx
  bool v17; // zf
  BOOL v18; // ebx
  char *v19; // r14
  const wchar_t *v20; // rbx
  int v21; // eax
  unsigned int v22; // r9d
  unsigned __int16 *v23; // rcx
  unsigned __int16 *v24; // rdx
  __int64 v25; // rax
  int IsServiceAccount; // eax
  signed int v27; // eax
  bool v28; // sf
  BOOL v29; // eax
  unsigned int v30; // ecx
  int v31; // eax
  struct TOKEN_CACHE_ENTRY *v32; // r9
  int v33; // ecx
  int v34; // eax
  int TokenForUser; // eax
  TOKEN_CACHE_ENTRY *v36; // rcx
  void *PrimaryToken; // rax
  unsigned __int16 *v38; // rcx
  void *v40; // rax
  int v41; // r14d
  struct TOKEN_CACHE_ENTRY **v42; // [rsp+30h] [rbp-D0h]
  BOOL IsService; // [rsp+40h] [rbp-C0h] BYREF
  struct _TOKEN_OWNER *v44; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v45; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v46[32]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v47; // [rsp+78h] [rbp-88h]
  unsigned __int16 v48[256]; // [rsp+90h] [rbp-70h] BYREF

  Owner = pSid;
  v44 = 0;
  v12 = 0;
  memset_0(v48, 0, sizeof(v48));
  STRU::STRU((STRU *)v46, v48, 0x100u);
  if ( !a4 )
  {
    v32 = 0;
    v33 = *((_DWORD *)g_pWebAdminService + 412);
    v34 = 1;
    if ( !v33 )
    {
      v34 = a6;
      v32 = pSid;
    }
    TokenForUser = CreateTokenForUser(
                     L"NT AUTHORITY\\System",
                     (unsigned __int16 *)&SourceString,
                     v33 != 0 ? -2 : 5,
                     0,
                     v34,
                     v32,
                     this + 23);
    if ( TokenForUser >= 0 )
    {
      v18 = 1;
    }
    else
    {
      v18 = 0;
      v12 = TokenForUser;
    }
LABEL_47:
    if ( *((_DWORD *)g_pWebAdminService + 412) )
    {
      v36 = this[23];
      if ( v36 )
        PrimaryToken = TOKEN_CACHE_ENTRY::QueryPrimaryToken(v36);
      else
        PrimaryToken = 0;
      if ( GetTokenSID(PrimaryToken, &v44) )
      {
LABEL_54:
        if ( v12 >= 0 || v18 )
          goto LABEL_59;
        goto LABEL_56;
      }
      Owner = (struct TOKEN_CACHE_ENTRY *)v44->Owner;
    }
    else if ( v18 )
    {
      v40 = TOKEN_CACHE_ENTRY::QueryPrimaryToken(this[23]);
      v41 = ChangeDefaultTokenDacl(v40, pSid);
      if ( v41 < 0 )
      {
        APP_POOL_CONFIG_STORE::TokenCacheFlushed((APP_POOL_CONFIG_STORE *)this);
        v12 = v41;
        v18 = 0;
LABEL_56:
        v38 = a7;
        if ( !a7 )
          v38 = L"<null>";
        v45 = v38;
        WEB_ADMIN_SERVICE::LogEvent(g_pWebAdminService, 0x8000139D, 1u, (const unsigned __int16 **const)&v45, v12);
        goto LABEL_59;
      }
    }
    this[91] = Owner;
    goto LABEL_54;
  }
  v14 = a4 - 1;
  if ( !v14 )
  {
    v23 = L"NT AUTHORITY\\LocalService";
    goto LABEL_37;
  }
  v15 = v14 - 1;
  if ( !v15 )
  {
    v23 = L"NT AUTHORITY\\NetworkService";
LABEL_37:
    v22 = 0;
    v42 = this + 23;
    v24 = (unsigned __int16 *)&SourceString;
LABEL_38:
    v31 = CreateTokenForUser(v23, v24, 5u, v22, a6, pSid, v42);
LABEL_39:
    if ( v31 < 0 )
      v12 = v31;
    v18 = v31 >= 0;
    goto LABEL_47;
  }
  v16 = v15 - 1;
  if ( !v16 )
  {
    if ( !AccountName || !String1 )
    {
      v12 = -2147023579;
      v18 = 0;
      goto LABEL_47;
    }
    IsService = 0;
    if ( !*AccountName )
      goto LABEL_32;
    v25 = -1;
    do
      ++v25;
    while ( AccountName[v25] );
    if ( AccountName[v25 - 1] != 36 )
      goto LABEL_32;
    IsServiceAccount = NetIsServiceAccount(0, AccountName, &IsService);
    if ( IsServiceAccount >= 0 )
      goto LABEL_29;
    v27 = RtlNtStatusToDosError(IsServiceAccount);
    v28 = v27 < 0;
    if ( v27 > 0 )
    {
      v27 = (unsigned __int16)v27 | 0x80070000;
      v28 = v27 < 0;
    }
    if ( v28 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool_config_store.cxx",
          1289,
          "APP_POOL_CONFIG_STORE::SetTokenForWorkerProcesses",
          v27,
          "Failed to determine if account %S is \"password managed service account\"",
          AccountName);
      v29 = 1;
      IsService = 1;
    }
    else
    {
LABEL_29:
      v29 = IsService;
    }
    if ( v29 )
    {
      String1 = L"_SA_{262E99C9-6160-4871-ACEC-4E61736B6F21}";
      v30 = 5;
    }
    else
    {
LABEL_32:
      v30 = 5 - (a5 != 1);
    }
    v31 = CreateTokenForUser(AccountName, String1, v30, 0, a6, pSid, this + 23);
    goto LABEL_39;
  }
  v17 = v16 == 1;
  v18 = 0;
  if ( !v17 )
  {
    v12 = -2147024809;
    goto LABEL_47;
  }
  v19 = (char *)(this + 92);
  if ( !*((_DWORD *)this + 187) )
  {
    if ( (int)EnsureLSAMapping(*(PCWSTR *)(*(_QWORD *)v19 + 56LL), pSid) < 0 )
      goto LABEL_59;
    *((_DWORD *)this + 187) = 1;
  }
  if ( (int)STRU::Copy((STRU *)v46, L"IIS APPPOOL") >= 0
    && (int)STRU::Append((STRU *)v46, 0x5Cu) >= 0
    && (int)STRU::Append((STRU *)v46, *(const unsigned __int16 **)(*(_QWORD *)v19 + 56LL)) >= 0 )
  {
    v20 = L"_VIRTUALACCOUNT_fd9d2ee1-ff72-459c-b66f-71135f5e41ca";
    v21 = wcscmp_0(String1, L"_VIRTUALACCOUNT_fd9d2ee1-ff72-459c-b66f-71135f5e41ca");
    v22 = 4;
    if ( v21 )
      v20 = &SourceString;
    v42 = this + 23;
    v23 = v47;
    v24 = (unsigned __int16 *)v20;
    goto LABEL_38;
  }
LABEL_59:
  STRU::~STRU((STRU *)v46);
  return v18;
}

```

## disassembly

```asm
0x180037234  mov     [rsp-8+arg_18], rbx
0x180037239  push    rbp
0x18003723a  push    rsi
0x18003723b  push    rdi
0x18003723c  push    r12
0x18003723e  push    r13
0x180037240  push    r14
0x180037242  push    r15
0x180037244  lea     rbp, [rsp-1A0h]
0x18003724c  sub     rsp, 2A0h
0x180037253  mov     rax, cs:__security_cookie
0x18003725a  xor     rax, rsp
0x18003725d  mov     [rbp+1D0h+var_40], rax
0x180037264  mov     r15, [rbp+1D0h+pSid]
0x18003726b  mov     r12, r8
0x18003726e  mov     r14, rdx
0x180037271  mov     rsi, rcx
0x180037274  xor     r13d, r13d
0x180037277  lea     rcx, [rbp+1D0h+var_240]; void *
0x18003727b  xor     edx, edx; Val
0x18003727d  mov     [rsp+2D0h+var_288], r13
0x180037282  mov     r8d, 200h; Size
0x180037288  mov     edi, r13d
0x18003728b  mov     ebx, r9d
0x18003728e  call    memset_0
0x180037293  mov     r8d, 100h
0x180037299  lea     rdx, [rbp+1D0h+var_240]
0x18003729d  lea     rcx, [rsp+2D0h+var_278]
0x1800372a2  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800372a8  test    ebx, ebx
0x1800372aa  jz      loc_1800374E8
0x1800372b0  sub     ebx, 1
0x1800372b3  jz      loc_1800374A3
0x1800372b9  sub     ebx, 1
0x1800372bc  jz      loc_18003749A
0x1800372c2  sub     ebx, 1
0x1800372c5  jz      loc_180037398
0x1800372cb  cmp     ebx, 1
0x1800372ce  mov     ebx, r13d
0x1800372d1  jz      short loc_1800372DD
0x1800372d3  mov     edi, 80070057h
0x1800372d8  jmp     loc_180037552
0x1800372dd  lea     r14, [rsi+2E0h]
0x1800372e4  cmp     [rsi+2ECh], r13d
0x1800372eb  jnz     short loc_18003730E
0x1800372ed  mov     rcx, [r14]
0x1800372f0  mov     rdx, r15; AccountSid
0x1800372f3  mov     rcx, [rcx+38h]; SourceString
0x1800372f7  call    ?EnsureLSAMapping@@YAJPEBGPEAX@Z; EnsureLSAMapping(ushort const *,void *)
0x1800372fc  test    eax, eax
0x1800372fe  js      loc_1800375DF
0x180037304  mov     dword ptr [rsi+2ECh], 1
0x18003730e  lea     rdx, aIisApppool; "IIS APPPOOL"
0x180037315  lea     rcx, [rsp+2D0h+var_278]
0x18003731a  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180037320  test    eax, eax
0x180037322  js      loc_1800375DF
0x180037328  mov     edx, 5Ch ; '\'
0x18003732d  lea     rcx, [rsp+2D0h+var_278]
0x180037332  call    cs:__imp_?Append@STRU@@QEAAJG@Z; STRU::Append(ushort)
0x180037338  test    eax, eax
0x18003733a  js      loc_1800375DF
0x180037340  mov     rdx, [r14]
0x180037343  lea     rcx, [rsp+2D0h+var_278]
0x180037348  mov     rdx, [rdx+38h]
0x18003734c  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180037352  test    eax, eax
0x180037354  js      loc_1800375DF
0x18003735a  lea     rbx, aVirtualaccount; "_VIRTUALACCOUNT_fd9d2ee1-ff72-459c-b66f"...
0x180037361  mov     rcx, r12; String1
0x180037364  mov     rdx, rbx; String2
0x180037367  call    wcscmp_0
0x18003736c  lea     rdx, SourceString
0x180037373  test    eax, eax
0x180037375  lea     rcx, [rsi+0B8h]
0x18003737c  mov     r9d, 4
0x180037382  cmovnz  rbx, rdx
0x180037386  mov     [rsp+2D0h+var_2A0], rcx
0x18003738b  mov     rcx, [rsp+2D0h+var_258]
0x180037390  mov     rdx, rbx
0x180037393  jmp     loc_1800374C0
0x180037398  test    r14, r14
0x18003739b  jz      loc_18003748D
0x1800373a1  test    r12, r12
0x1800373a4  jz      loc_18003748D
0x1800373aa  mov     [rsp+2D0h+IsService], r13d
0x1800373af  cmp     [r14], r13w
0x1800373b3  jz      loc_180037460
0x1800373b9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800373bd  inc     rax
0x1800373c0  cmp     [r14+rax*2], r13w
0x1800373c5  jnz     short loc_1800373BD
0x1800373c7  cmp     word ptr [r14+rax*2-2], 24h ; '$'
0x1800373ce  jnz     loc_180037460
0x1800373d4  lea     r8, [rsp+2D0h+IsService]; IsService
0x1800373d9  mov     rdx, r14; AccountName
0x1800373dc  xor     ecx, ecx; ServerName
0x1800373de  call    cs:__imp_NetIsServiceAccount
0x1800373e4  test    eax, eax
0x1800373e6  jns     short loc_18003744A
0x1800373e8  mov     ecx, eax; Status
0x1800373ea  call    cs:__imp_RtlNtStatusToDosError
0x1800373f0  test    eax, eax
0x1800373f2  jle     short loc_1800373FE
0x1800373f4  movzx   eax, ax
0x1800373f7  or      eax, 80070000h
0x1800373fc  test    eax, eax
0x1800373fe  jns     short loc_18003744A
0x180037400  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180037407  jz      short loc_18003743F
0x180037409  lea     rcx, aFailedToDeterm; "Failed to determine if account %S is \""...
0x180037410  mov     [rsp+2D0h+var_2A0], r14
0x180037415  mov     [rsp+2D0h+var_2A8], rcx
0x18003741a  lea     r9, aAppPoolConfigS_0; "APP_POOL_CONFIG_STORE::SetTokenForWorke"...
0x180037421  mov     rcx, cs:g_pDebug
0x180037428  lea     rdx, aServercommonIn_48; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18003742f  mov     r8d, 509h
0x180037435  mov     [rsp+2D0h+var_2B0], eax
0x180037439  call    cs:__imp_PuDbgPrintError
0x18003743f  mov     eax, 1
0x180037444  mov     [rsp+2D0h+IsService], eax
0x180037448  jmp     short loc_18003744E
0x18003744a  mov     eax, [rsp+2D0h+IsService]
0x18003744e  test    eax, eax
0x180037450  jz      short loc_180037460
0x180037452  lea     r12, aSa262e99c96160; "_SA_{262E99C9-6160-4871-ACEC-4E61736B6F"...
0x180037459  mov     ecx, 5
0x18003745e  jmp     short loc_180037473
0x180037460  mov     eax, [rbp+1D0h+arg_20]
0x180037466  mov     ecx, 5
0x18003746b  dec     eax
0x18003746d  neg     eax
0x18003746f  sbb     eax, eax
0x180037471  add     ecx, eax
0x180037473  lea     rax, [rsi+0B8h]
0x18003747a  mov     r8d, ecx
0x18003747d  mov     [rsp+2D0h+var_2A0], rax
0x180037482  xor     r9d, r9d
0x180037485  mov     rdx, r12
0x180037488  mov     rcx, r14
0x18003748b  jmp     short loc_1800374C6
0x18003748d  mov     edi, 80070525h
0x180037492  mov     ebx, r13d
0x180037495  jmp     loc_180037552
0x18003749a  lea     rcx, aNtAuthorityNet; "NT AUTHORITY\\NetworkService"
0x1800374a1  jmp     short loc_1800374AA
0x1800374a3  lea     rcx, aNtAuthorityLoc; "NT AUTHORITY\\LocalService"
0x1800374aa  lea     rax, [rsi+0B8h]
0x1800374b1  xor     r9d, r9d; unsigned int
0x1800374b4  mov     [rsp+2D0h+var_2A0], rax; struct TOKEN_CACHE_ENTRY **
0x1800374b9  lea     rdx, SourceString; unsigned __int16 *
0x1800374c0  mov     r8d, 5; unsigned int
0x1800374c6  mov     eax, [rbp+1D0h+arg_28]
0x1800374cc  mov     [rsp+2D0h+var_2A8], r15; void *
0x1800374d1  mov     [rsp+2D0h+var_2B0], eax; int
0x1800374d5  call    ?CreateTokenForUser@@YAJPEBG0KKHPEAXPEAPEAVTOKEN_CACHE_ENTRY@@@Z; CreateTokenForUser(ushort const *,ushort const *,ulong,ulong,int,void *,TOKEN_CACHE_ENTRY * *)
0x1800374da  test    eax, eax
0x1800374dc  mov     ebx, eax
0x1800374de  not     ebx
0x1800374e0  cmovs   edi, eax
0x1800374e3  shr     ebx, 1Fh
0x1800374e6  jmp     short loc_180037552
0x1800374e8  mov     rax, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x1800374ef  lea     rdx, [rsi+0B8h]
0x1800374f6  mov     [rsp+2D0h+var_2A0], rdx; struct TOKEN_CACHE_ENTRY **
0x1800374fb  mov     r9, r13
0x1800374fe  lea     rdx, SourceString; unsigned __int16 *
0x180037505  mov     ecx, [rax+670h]
0x18003750b  test    ecx, ecx
0x18003750d  mov     eax, 1
0x180037512  cmovz   eax, [rbp+1D0h+arg_28]
0x180037519  cmovz   r9, r15
0x18003751d  neg     ecx
0x18003751f  mov     [rsp+2D0h+var_2A8], r9; void *
0x180037524  lea     rcx, aNtAuthoritySys; "NT AUTHORITY\\System"
0x18003752b  mov     [rsp+2D0h+var_2B0], eax; int
0x18003752f  sbb     r8d, r8d
0x180037532  xor     r9d, r9d; unsigned int
0x180037535  and     r8d, 0FFFFFFF9h
0x180037539  add     r8d, 5; unsigned int
0x18003753d  call    ?CreateTokenForUser@@YAJPEBG0KKHPEAXPEAPEAVTOKEN_CACHE_ENTRY@@@Z; CreateTokenForUser(ushort const *,ushort const *,ulong,ulong,int,void *,TOKEN_CACHE_ENTRY * *)
0x180037542  test    eax, eax
0x180037544  jns     short loc_18003754D
0x180037546  mov     ebx, r13d
0x180037549  mov     edi, eax
0x18003754b  jmp     short loc_180037552
0x18003754d  mov     ebx, 1
0x180037552  mov     rax, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180037559  cmp     [rax+670h], r13d
0x180037560  jz      loc_180037616
0x180037566  mov     rcx, [rsi+0B8h]; this
0x18003756d  test    rcx, rcx
0x180037570  jz      short loc_180037579
0x180037572  call    ?QueryPrimaryToken@TOKEN_CACHE_ENTRY@@QEAAPEAXXZ; TOKEN_CACHE_ENTRY::QueryPrimaryToken(void)
0x180037577  jmp     short loc_18003757C
0x180037579  mov     rax, r13
0x18003757c  lea     rdx, [rsp+2D0h+var_288]
0x180037581  mov     rcx, rax
0x180037584  call    cs:__imp_?GetTokenSID@@YAKPEAXPEAPEAU_TOKEN_OWNER@@@Z; GetTokenSID(void *,_TOKEN_OWNER * *)
0x18003758a  test    eax, eax
0x18003758c  jnz     short loc_18003759D
0x18003758e  mov     rax, [rsp+2D0h+var_288]
0x180037593  mov     r15, [rax]
0x180037596  mov     [rsi+2D8h], r15
0x18003759d  test    edi, edi
0x18003759f  jns     short loc_1800375DF
0x1800375a1  test    ebx, ebx
0x1800375a3  jnz     short loc_1800375DF
0x1800375a5  mov     rcx, [rbp+1D0h+arg_30]
0x1800375ac  lea     rax, aNull; "<null>"
0x1800375b3  test    rcx, rcx
0x1800375b6  mov     [rsp+2D0h+var_2B0], edi; unsigned int
0x1800375ba  mov     r8d, 1; unsigned __int16
0x1800375c0  lea     r9, [rsp+2D0h+var_280]; unsigned __int16 **
0x1800375c5  cmovz   rcx, rax
0x1800375c9  mov     edx, 8000139Dh; unsigned int
0x1800375ce  mov     [rsp+2D0h+var_280], rcx
0x1800375d3  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; this
0x1800375da  call    ?LogEvent@WEB_ADMIN_SERVICE@@QEAAXKGQEAPEBGK@Z; WEB_ADMIN_SERVICE::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x1800375df  lea     rcx, [rsp+2D0h+var_278]
0x1800375e4  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800375ea  mov     eax, ebx
0x1800375ec  mov     rcx, [rbp+1D0h+var_40]
0x1800375f3  xor     rcx, rsp; StackCookie
0x1800375f6  call    __security_check_cookie
0x1800375fb  mov     rbx, [rsp+2D0h+arg_18]
0x180037603  add     rsp, 2A0h
0x18003760a  pop     r15
0x18003760c  pop     r14
0x18003760e  pop     r13
0x180037610  pop     r12
0x180037612  pop     rdi
0x180037613  pop     rsi
0x180037614  pop     rbp
0x180037615  retn
0x180037616  test    ebx, ebx
0x180037618  jz      loc_180037596
0x18003761e  mov     rcx, [rsi+0B8h]; this
0x180037625  call    ?QueryPrimaryToken@TOKEN_CACHE_ENTRY@@QEAAPEAXXZ; TOKEN_CACHE_ENTRY::QueryPrimaryToken(void)
0x18003762a  mov     rcx, rax; TokenHandle
0x18003762d  mov     rdx, r15; pSid
0x180037630  call    ?ChangeDefaultTokenDacl@@YAJPEAX0@Z; ChangeDefaultTokenDacl(void *,void *)
0x180037635  mov     r14d, eax
0x180037638  test    eax, eax
0x18003763a  jns     loc_180037596
0x180037640  mov     rcx, rsi; this
0x180037643  call    ?TokenCacheFlushed@APP_POOL_CONFIG_STORE@@QEAAXXZ; APP_POOL_CONFIG_STORE::TokenCacheFlushed(void)
0x180037648  mov     edi, r14d
0x18003764b  mov     ebx, r13d
0x18003764e  jmp     loc_1800375A5
```
