# LOGON_USER_CONTEXT::HandleClientCertAuthLogon(void *)

- ea: `0x18001b90c`
- end: `0x18001bd76`
- name: `?HandleClientCertAuthLogon@LOGON_USER_CONTEXT@@AEAAJPEAX@Z`
- size: `1130`
- prototype: `int(LOGON_USER_CONTEXT *__hidden this, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001ccec`

## callees

- `0x1800022b8`
- `0x180015928`
- `0x18001a77c`
- `0x18001ae98`
- `0x18001b90c`
- `0x18001f04c`
- `0x18001ff3c`
- `0x18004700f`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001ba4b`
- `KERNEL32!GetLastError` at `0x18001ba4b`
- `KERNEL32!CloseHandle` at `0x18001bc50`
- `KERNEL32!CloseHandle` at `0x18001bc50`
- `ADVAPI32!DuplicateTokenEx` at `0x18001ba2a`
- `ADVAPI32!DuplicateTokenEx` at `0x18001ba2a`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001bc84`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001bc84`
- `iisutil!PuDbgPrint` at `0x18001ba74`
- `iisutil!PuDbgPrint` at `0x18001bb9b`
- `iisutil!PuDbgPrint` at `0x18001ba74`
- `iisutil!PuDbgPrint` at `0x18001bb9b`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18001ba81`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18001ba81`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18001ba07`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18001bc3e`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18001bd48`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18001ba07`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18001bc3e`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18001bd48`
- `iisutil!PuDbgPrintError` at `0x18001bb32`
- `iisutil!PuDbgPrintError` at `0x18001bb32`

## string_xrefs

- `0x18001bb0f`: `Failed to retrieve name from token.\n`
- `0x18001ba55`: `DuplicateTokenEx failed, GetLastError = %lx\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall LOGON_USER_CONTEXT::HandleClientCertAuthLogon(LOGON_USER_CONTEXT *this, void *a2)
{
  __int64 v4; // rax
  __int64 v5; // rbx
  CEtwTracer *v6; // rax
  DWORD LastError; // eax
  TOKEN_CACHE_ENTRY *v8; // rax
  volatile signed __int32 *v9; // rdi
  signed int NameFromToken; // esi
  void *ImpersonationToken; // rax
  LOGON_USER_CONTEXT *v12; // rcx
  int v13; // eax
  __int64 v14; // rax
  __int64 v15; // rbx
  CEtwTracer *v16; // rax
  __int64 v17; // rax
  __int64 v18; // rdi
  CEtwTracer *v19; // rbx
  const unsigned __int16 *TokenType; // [rsp+20h] [rbp-E0h]
  HANDLE hObject; // [rsp+40h] [rbp-C0h] BYREF
  union _LARGE_INTEGER v23; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v24; // [rsp+50h] [rbp-B0h] BYREF
  TOKEN_CACHE_ENTRY *v25; // [rsp+58h] [rbp-A8h]
  __int16 v26; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v27; // [rsp+62h] [rbp-9Eh] BYREF
  __int128 v28; // [rsp+72h] [rbp-8Eh]
  _BYTE v29[22]; // [rsp+82h] [rbp-7Eh]
  int v30; // [rsp+98h] [rbp-68h]
  int v31; // [rsp+9Ch] [rbp-64h]
  union _LARGE_INTEGER *v32; // [rsp+A0h] [rbp-60h]
  int v33; // [rsp+A8h] [rbp-58h]
  unsigned __int16 v34[256]; // [rsp+B0h] [rbp-50h] BYREF

  hObject = 0;
  v23.QuadPart = 0x7FFFFFFFFFFFFFFFLL;
  memset_0(v34, 0, sizeof(v34));
  v24 = 256;
  v4 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
  if ( *(_DWORD *)(v4 + 8) && (*(_BYTE *)(v4 + 40) & 8) != 0 && *(_DWORD *)(v4 + 44) >= 4u )
  {
    v5 = *((_QWORD *)this + 1) + 1272LL;
    v6 = (CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
    v27 = 0;
    v28 = 0;
    *(_OWORD *)v29 = 0;
    v31 = 0;
    *(_DWORD *)&v29[10] = 1703936;
    v26 = 64;
    WORD2(v27) = 1;
    BYTE2(v27) = 16;
    *(_QWORD *)((char *)&v28 + 6) = &`FtpAuthenticationEvents::GetAreaGuid'::`2'::AreaGuid;
    *(_QWORD *)&v29[14] = v5;
    v30 = 16;
    CEtwTracer::EtwTraceEvent(v6, (struct _EVENT_TRACE_HEADER *)&v26);
  }
  if ( !DuplicateTokenEx(a2, 0, 0, SecurityImpersonation, TokenImpersonation, &hObject) && (g_dwDebugFlags & 3) != 0 )
  {
    LastError = GetLastError();
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\logon_user_context.cxx",
      1467,
      "LOGON_USER_CONTEXT::HandleClientCertAuthLogon",
      "DuplicateTokenEx failed, GetLastError = %lx\n",
      LastError);
  }
  v8 = (TOKEN_CACHE_ENTRY *)ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry);
  v25 = v8;
  if ( v8 )
    v9 = (volatile signed __int32 *)TOKEN_CACHE_ENTRY::TOKEN_CACHE_ENTRY(v8);
  else
    v9 = 0;
  if ( v9 )
  {
    NameFromToken = TOKEN_CACHE_ENTRY::Create((TOKEN_CACHE_ENTRY *)v9, hObject, &WideCharStr, &v23, 1);
    if ( NameFromToken >= 0 )
    {
      hObject = 0;
      ImpersonationToken = TOKEN_CACHE_ENTRY::QueryImpersonationToken((TOKEN_CACHE_ENTRY *)v9);
      NameFromToken = LOGON_USER_CONTEXT::GetNameFromToken(v12, ImpersonationToken, v34, &v24);
      if ( NameFromToken >= 0 )
      {
        v13 = FTP_USER::Initialize(
                (FTP_USER *)(*((_QWORD *)this + 1) + 24LL),
                *((struct USER_SESSION **)this + 1),
                (struct TOKEN_CACHE_ENTRY *)v9,
                v34,
                TokenType,
                (wchar_t *)L"ClientCertAuth",
                0);
        NameFromToken = v13;
        if ( v13 >= 0 )
        {
          v9 = 0;
          v14 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
          if ( *(_DWORD *)(v14 + 8) && (*(_BYTE *)(v14 + 40) & 8) != 0 && *(_DWORD *)(v14 + 44) >= 4u )
          {
            v15 = *((_QWORD *)this + 1) + 1272LL;
            v16 = (CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
            v27 = 0;
            v28 = 0;
            *(_OWORD *)v29 = 0;
            v31 = 0;
            *(_DWORD *)&v29[10] = 1703936;
            v26 = 64;
            WORD2(v27) = 1;
            BYTE2(v27) = 17;
            *(_QWORD *)((char *)&v28 + 6) = &`FtpAuthenticationEvents::GetAreaGuid'::`2'::AreaGuid;
            *(_QWORD *)&v29[14] = v15;
            v30 = 16;
            CEtwTracer::EtwTraceEvent(v16, (struct _EVENT_TRACE_HEADER *)&v26);
          }
          NameFromToken = 0;
        }
        else if ( (g_dwDebugFlags & 3) != 0 )
        {
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\logon_user_context.cxx",
            1516,
            "LOGON_USER_CONTEXT::HandleClientCertAuthLogon",
            "Client Cert Mapping user context initialization failed with 0x%x.\r\n",
            v13);
        }
      }
      else if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\logon_user_context.cxx",
          1500,
          "LOGON_USER_CONTEXT::HandleClientCertAuthLogon",
          NameFromToken,
          "Failed to retrieve name from token.\r\n");
      }
    }
  }
  else
  {
    NameFromToken = -2147024888;
  }
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( v9 && _InterlockedExchangeAdd(v9 + 5, 0xFFFFFFFF) == 1 )
  {
    TOKEN_CACHE_ENTRY::~TOKEN_CACHE_ENTRY((TOKEN_CACHE_ENTRY *)v9);
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry, (void *)v9);
  }
  if ( NameFromToken < 0 )
  {
    v17 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
    if ( *(_DWORD *)(v17 + 8) )
    {
      if ( (*(_BYTE *)(v17 + 40) & 8) != 0 && *(_DWORD *)(v17 + 44) >= 3u )
      {
        v18 = *((_QWORD *)this + 1) + 1272LL;
        v19 = (CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
        v23.LowPart = NameFromToken;
        memset_0(&v27, 0, 0x4Eu);
        *(_DWORD *)&v29[10] = 1703936;
        v26 = 80;
        WORD2(v27) = 1;
        BYTE2(v27) = 18;
        *(_QWORD *)((char *)&v28 + 6) = &`FtpAuthenticationEvents::GetAreaGuid'::`2'::AreaGuid;
        *(_QWORD *)&v29[14] = v18;
        v30 = 16;
        v32 = &v23;
        v33 = 4;
        CEtwTracer::EtwTraceEvent(v19, (struct _EVENT_TRACE_HEADER *)&v26);
      }
    }
  }
  return (unsigned int)NameFromToken;
}

```

## disassembly

```asm
0x18001b90c  mov     [rsp-8+arg_10], rbx
0x18001b911  push    rbp
0x18001b912  push    rsi
0x18001b913  push    rdi
0x18001b914  push    r12
0x18001b916  push    r14
0x18001b918  lea     rbp, [rsp-1C0h]
0x18001b920  sub     rsp, 2C0h
0x18001b927  mov     rax, cs:__security_cookie
0x18001b92e  xor     rax, rsp
0x18001b931  mov     [rbp+1E0h+var_30], rax
0x18001b938  mov     rdi, rdx
0x18001b93b  mov     r14, rcx
0x18001b93e  mov     [rsp+2E0h+hObject], 0
0x18001b947  mov     dword ptr [rsp+2E0h+var_298+4], 7FFFFFFFh
0x18001b94f  mov     dword ptr [rsp+2E0h+var_298], 0FFFFFFFFh
0x18001b957  xor     edx, edx; Val
0x18001b959  mov     r8d, 200h; Size
0x18001b95f  lea     rcx, [rbp+1E0h+var_230]; void *
0x18001b963  call    memset_0
0x18001b968  mov     [rsp+2E0h+var_290], 100h
0x18001b970  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001b977  mov     rax, [rcx]
0x18001b97a  mov     rax, [rax+20h]
0x18001b97e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b983  mov     esi, 40h ; '@'
0x18001b988  lea     r12d, [rsi-3Fh]
0x18001b98c  cmp     dword ptr [rax+8], 0
0x18001b990  jz      short loc_18001BA0D
0x18001b992  test    byte ptr [rax+28h], 8
0x18001b996  jz      short loc_18001BA0D
0x18001b998  cmp     dword ptr [rax+2Ch], 4
0x18001b99c  jb      short loc_18001BA0D
0x18001b99e  mov     rbx, [r14+8]
0x18001b9a2  add     rbx, 4F8h
0x18001b9a9  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001b9b0  mov     rax, [rcx]
0x18001b9b3  mov     rax, [rax+20h]
0x18001b9b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9bc  xorps   xmm0, xmm0
0x18001b9bf  movups  [rsp+2E0h+var_27E], xmm0
0x18001b9c4  movups  [rsp+2E0h+var_26E], xmm0
0x18001b9c9  movups  xmmword ptr [rbp+1E0h+var_25E], xmm0
0x18001b9cd  movups  xmmword ptr [rbp+1E0h+var_25E+0Eh], xmm0
0x18001b9d1  mov     dword ptr [rbp+1E0h+var_25E+0Ah], 1A0000h
0x18001b9d8  mov     [rsp+2E0h+var_280], si
0x18001b9dd  mov     word ptr [rsp+2E0h+var_27E+4], r12w
0x18001b9e3  mov     byte ptr [rsp+2E0h+var_27E+2], 10h
0x18001b9e8  lea     rcx, ?AreaGuid@?1??GetAreaGuid@FtpAuthenticationEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `FtpAuthenticationEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18001b9ef  mov     qword ptr [rsp+2E0h+var_26E+6], rcx
0x18001b9f4  mov     qword ptr [rbp+1E0h+var_25E+0Eh], rbx
0x18001b9f8  mov     [rbp+1E0h+var_248], 10h
0x18001b9ff  lea     rdx, [rsp+2E0h+var_280]
0x18001ba04  mov     rcx, rax
0x18001ba07  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z; CEtwTracer::EtwTraceEvent(_EVENT_TRACE_HEADER *)
0x18001ba0d  lea     rax, [rsp+2E0h+hObject]
0x18001ba12  mov     [rsp+2E0h+phNewToken], rax; phNewToken
0x18001ba17  mov     r9d, 2; ImpersonationLevel
0x18001ba1d  mov     [rsp+2E0h+TokenType], r9d; TokenType
0x18001ba22  xor     r8d, r8d; lpTokenAttributes
0x18001ba25  xor     edx, edx; dwDesiredAccess
0x18001ba27  mov     rcx, rdi; hExistingToken
0x18001ba2a  call    cs:__imp_DuplicateTokenEx
0x18001ba30  lea     rbx, aLogonUserConte_6; "LOGON_USER_CONTEXT::HandleClientCertAut"...
0x18001ba37  lea     r12, aInetsrvIisIisr_4; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18001ba3e  test    eax, eax
0x18001ba40  jnz     short loc_18001BA7A
0x18001ba42  test    byte ptr cs:g_dwDebugFlags, 3
0x18001ba49  jz      short loc_18001BA7A
0x18001ba4b  call    cs:__imp_GetLastError
0x18001ba51  mov     dword ptr [rsp+2E0h+phNewToken], eax
0x18001ba55  lea     rax, aDuplicatetoken; "DuplicateTokenEx failed, GetLastError ="...
0x18001ba5c  mov     qword ptr [rsp+2E0h+TokenType], rax
0x18001ba61  mov     r9, rbx
0x18001ba64  mov     r8d, 5BBh
0x18001ba6a  mov     rdx, r12
0x18001ba6d  mov     rcx, cs:g_pDebug
0x18001ba74  call    cs:__imp_PuDbgPrint
0x18001ba7a  mov     rcx, cs:?sm_pachTokenCacheEntry@TOKEN_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry
0x18001ba81  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18001ba87  mov     [rsp+2E0h+var_288], rax
0x18001ba8c  test    rax, rax
0x18001ba8f  jz      short loc_18001BA9E
0x18001ba91  mov     rcx, rax; this
0x18001ba94  call    ??0TOKEN_CACHE_ENTRY@@QEAA@XZ; TOKEN_CACHE_ENTRY::TOKEN_CACHE_ENTRY(void)
0x18001ba99  mov     rdi, rax
0x18001ba9c  jmp     short loc_18001BAA0
0x18001ba9e  xor     edi, edi
0x18001baa0  test    rdi, rdi
0x18001baa3  jnz     short loc_18001BAAF
0x18001baa5  mov     esi, 80070008h
0x18001baaa  jmp     loc_18001BC46
0x18001baaf  mov     [rsp+2E0h+TokenType], 1; unsigned __int16 *
0x18001bab7  lea     r9, [rsp+2E0h+var_298]; union _LARGE_INTEGER *
0x18001babc  lea     r8, WideCharStr; unsigned __int16 *
0x18001bac3  mov     rdx, [rsp+2E0h+hObject]; void *
0x18001bac8  mov     rcx, rdi; this
0x18001bacb  call    ?Create@TOKEN_CACHE_ENTRY@@QEAAJPEAXPEBGPEAT_LARGE_INTEGER@@H@Z; TOKEN_CACHE_ENTRY::Create(void *,ushort const *,_LARGE_INTEGER *,int)
0x18001bad0  mov     esi, eax
0x18001bad2  test    eax, eax
0x18001bad4  js      loc_18001BC46
0x18001bada  mov     [rsp+2E0h+hObject], 0
0x18001bae3  mov     rcx, rdi; this
0x18001bae6  call    ?QueryImpersonationToken@TOKEN_CACHE_ENTRY@@QEAAPEAXXZ; TOKEN_CACHE_ENTRY::QueryImpersonationToken(void)
0x18001baeb  mov     rdx, rax; void *
0x18001baee  lea     r9, [rsp+2E0h+var_290]; unsigned int *
0x18001baf3  lea     r8, [rbp+1E0h+var_230]; unsigned __int16 *
0x18001baf7  call    ?GetNameFromToken@LOGON_USER_CONTEXT@@AEAAJPEAXPEAGPEAK@Z; LOGON_USER_CONTEXT::GetNameFromToken(void *,ushort *,ulong *)
0x18001bafc  mov     esi, eax
0x18001bafe  test    eax, eax
0x18001bb00  jns     short loc_18001BB3D
0x18001bb02  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001bb09  jz      loc_18001BC46
0x18001bb0f  lea     rax, aFailedToRetrie_1; "Failed to retrieve name from token.\r\n"
0x18001bb16  mov     [rsp+2E0h+phNewToken], rax
0x18001bb1b  mov     [rsp+2E0h+TokenType], esi
0x18001bb1f  mov     r9, rbx
0x18001bb22  mov     r8d, 5DCh
0x18001bb28  mov     rdx, r12
0x18001bb2b  mov     rcx, cs:g_pDebug
0x18001bb32  call    cs:__imp_PuDbgPrintError
0x18001bb38  jmp     loc_18001BC46
0x18001bb3d  mov     rdx, [r14+8]; struct USER_SESSION *
0x18001bb41  lea     rcx, [rdx+18h]; this
0x18001bb45  mov     [rsp+2E0h+var_2B0], 0; int
0x18001bb4d  lea     rax, aClientcertauth_0; "ClientCertAuth"
0x18001bb54  mov     [rsp+2E0h+phNewToken], rax; unsigned __int16 *
0x18001bb59  lea     r9, [rbp+1E0h+var_230]; unsigned __int16 *
0x18001bb5d  mov     r8, rdi; struct TOKEN_CACHE_ENTRY *
0x18001bb60  call    ?Initialize@FTP_USER@@QEAAJPEAVUSER_SESSION@@PEAVTOKEN_CACHE_ENTRY@@PEBG22H@Z; FTP_USER::Initialize(USER_SESSION *,TOKEN_CACHE_ENTRY *,ushort const *,ushort const *,ushort const *,int)
0x18001bb65  mov     esi, eax
0x18001bb67  test    eax, eax
0x18001bb69  jns     short loc_18001BBA6
0x18001bb6b  test    byte ptr cs:g_dwDebugFlags, 3
0x18001bb72  jz      loc_18001BC46
0x18001bb78  mov     dword ptr [rsp+2E0h+phNewToken], eax
0x18001bb7c  lea     rax, aClientCertMapp; "Client Cert Mapping user context initia"...
0x18001bb83  mov     qword ptr [rsp+2E0h+TokenType], rax
0x18001bb88  mov     r9, rbx
0x18001bb8b  mov     r8d, 5ECh
0x18001bb91  mov     rdx, r12
0x18001bb94  mov     rcx, cs:g_pDebug
0x18001bb9b  call    cs:__imp_PuDbgPrint
0x18001bba1  jmp     loc_18001BC46
0x18001bba6  xor     edi, edi
0x18001bba8  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001bbaf  mov     rax, [rcx]
0x18001bbb2  mov     rax, [rax+20h]
0x18001bbb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bbbb  cmp     [rax+8], edi
0x18001bbbe  jz      loc_18001BC44
0x18001bbc4  test    byte ptr [rax+28h], 8
0x18001bbc8  jz      short loc_18001BC44
0x18001bbca  cmp     dword ptr [rax+2Ch], 4
0x18001bbce  jb      short loc_18001BC44
0x18001bbd0  mov     rbx, [r14+8]
0x18001bbd4  add     rbx, 4F8h
0x18001bbdb  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001bbe2  mov     rax, [rcx]
0x18001bbe5  mov     rax, [rax+20h]
0x18001bbe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bbee  xorps   xmm0, xmm0
0x18001bbf1  movups  [rsp+2E0h+var_27E], xmm0
0x18001bbf6  movups  [rsp+2E0h+var_26E], xmm0
0x18001bbfb  movups  xmmword ptr [rbp+1E0h+var_25E], xmm0
0x18001bbff  movups  xmmword ptr [rbp+1E0h+var_25E+0Eh], xmm0
0x18001bc03  mov     dword ptr [rbp+1E0h+var_25E+0Ah], 1A0000h
0x18001bc0a  lea     ecx, [rdi+40h]
0x18001bc0d  mov     [rsp+2E0h+var_280], cx
0x18001bc12  lea     ecx, [rdi+1]
0x18001bc15  mov     word ptr [rsp+2E0h+var_27E+4], cx
0x18001bc1a  mov     byte ptr [rsp+2E0h+var_27E+2], 11h
0x18001bc1f  lea     rcx, ?AreaGuid@?1??GetAreaGuid@FtpAuthenticationEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `FtpAuthenticationEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18001bc26  mov     qword ptr [rsp+2E0h+var_26E+6], rcx
0x18001bc2b  mov     qword ptr [rbp+1E0h+var_25E+0Eh], rbx
0x18001bc2f  mov     [rbp+1E0h+var_248], 10h
0x18001bc36  lea     rdx, [rsp+2E0h+var_280]
0x18001bc3b  mov     rcx, rax
0x18001bc3e  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z; CEtwTracer::EtwTraceEvent(_EVENT_TRACE_HEADER *)
0x18001bc44  xor     esi, esi
0x18001bc46  mov     rcx, [rsp+2E0h+hObject]; hObject
0x18001bc4b  test    rcx, rcx
0x18001bc4e  jz      short loc_18001BC5F
0x18001bc50  call    cs:__imp_CloseHandle
0x18001bc56  mov     [rsp+2E0h+hObject], 0
0x18001bc5f  test    rdi, rdi
0x18001bc62  jz      short loc_18001BC8B
0x18001bc64  or      eax, 0FFFFFFFFh
0x18001bc67  lock xadd [rdi+14h], eax
0x18001bc6c  cmp     eax, 1
0x18001bc6f  jnz     short loc_18001BC8B
0x18001bc71  mov     rcx, rdi; this
0x18001bc74  call    ??1TOKEN_CACHE_ENTRY@@AEAA@XZ; TOKEN_CACHE_ENTRY::~TOKEN_CACHE_ENTRY(void)
0x18001bc79  nop
0x18001bc7a  mov     rdx, rdi
0x18001bc7d  mov     rcx, cs:?sm_pachTokenCacheEntry@TOKEN_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry
0x18001bc84  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18001bc8a  nop
0x18001bc8b  test    esi, esi
0x18001bc8d  jns     loc_18001BD4E
0x18001bc93  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001bc9a  mov     rax, [rcx]
0x18001bc9d  mov     rax, [rax+20h]
0x18001bca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bca6  cmp     dword ptr [rax+8], 0
0x18001bcaa  jz      loc_18001BD4E
0x18001bcb0  test    byte ptr [rax+28h], 8
0x18001bcb4  jz      loc_18001BD4E
0x18001bcba  cmp     dword ptr [rax+2Ch], 3
0x18001bcbe  jb      loc_18001BD4E
0x18001bcc4  mov     rdi, [r14+8]
0x18001bcc8  add     rdi, 4F8h
0x18001bccf  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001bcd6  mov     rax, [rcx]
0x18001bcd9  mov     rax, [rax+20h]
0x18001bcdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bce2  mov     rbx, rax
0x18001bce5  mov     dword ptr [rsp+2E0h+var_298], esi
0x18001bce9  xor     edx, edx; Val
0x18001bceb  lea     r8d, [rdx+4Eh]; Size
0x18001bcef  lea     rcx, [rsp+2E0h+var_27E]; void *
0x18001bcf4  call    memset_0
0x18001bcf9  mov     dword ptr [rbp+1E0h+var_25E+0Ah], 1A0000h
0x18001bd00  mov     eax, 50h ; 'P'
0x18001bd05  mov     [rsp+2E0h+var_280], ax
0x18001bd0a  mov     eax, 1
0x18001bd0f  mov     word ptr [rsp+2E0h+var_27E+4], ax
0x18001bd14  mov     byte ptr [rsp+2E0h+var_27E+2], 12h
0x18001bd19  lea     rax, ?AreaGuid@?1??GetAreaGuid@FtpAuthenticationEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `FtpAuthenticationEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18001bd20  mov     qword ptr [rsp+2E0h+var_26E+6], rax
0x18001bd25  mov     qword ptr [rbp+1E0h+var_25E+0Eh], rdi
0x18001bd29  mov     [rbp+1E0h+var_248], 10h
0x18001bd30  lea     rax, [rsp+2E0h+var_298]
0x18001bd35  mov     [rbp+1E0h+var_240], rax
0x18001bd39  mov     [rbp+1E0h+var_238], 4
0x18001bd40  lea     rdx, [rsp+2E0h+var_280]
0x18001bd45  mov     rcx, rbx
0x18001bd48  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z; CEtwTracer::EtwTraceEvent(_EVENT_TRACE_HEADER *)
0x18001bd4e  mov     eax, esi
0x18001bd50  mov     rcx, [rbp+1E0h+var_30]
0x18001bd57  xor     rcx, rsp; StackCookie
0x18001bd5a  call    __security_check_cookie
0x18001bd5f  mov     rbx, [rsp+2E0h+arg_10]
0x18001bd67  add     rsp, 2C0h
0x18001bd6e  pop     r14
0x18001bd70  pop     r12
0x18001bd72  pop     rdi
0x18001bd73  pop     rsi
0x18001bd74  pop     rbp
0x18001bd75  retn
```
