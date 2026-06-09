# GetRpcClientInfo

- ea: `0x18008dee8`
- end: `0x18008e42c`
- name: `GetRpcClientInfo`
- size: `1348`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008edac`

## callees

- `0x18000a504`
- `0x18000a52c`
- `0x180075ec0`
- `0x18007d320`
- `0x18007de08`
- `0x18007dec4`
- `0x18008c688`
- `0x18008db54`
- `0x18008dee8`
- `0x1800bb8e0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008e32f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008e32f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18008df4d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18008df69`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18008df85`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18008e09b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18008e13f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18008e381`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18008df4d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18008df69`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18008df85`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18008e09b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18008e13f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18008e381`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18008e2fe`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18008e2fe`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18008e317`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18008e317`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e041`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e191`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e041`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e191`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18008dfaf`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18008dfaf`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008e157`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008e157`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008e1a7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008e1a7`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18008e015`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18008e015`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18008df91`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18008df91`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008e183`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008e1da`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008e183`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008e1da`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18008e0c8`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18008e0c8`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18008e25b`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18008e25b`

## string_xrefs

- `0x18008e04d`: `RPC Attribution: Failed to open RPC client process PID %lu, error=%lu`
- `0x18008e07e`: `RPC Attribution: Failed to open RPC client process PID %lu, error=%lu`
- `0x18008e08c`: `Access Denied`
- `0x18008e0fd`: `RPC Attribution: Failed to get RPC client process path for PID %lu`
- `0x18008e122`: `RPC Attribution: Failed to get RPC client process path for PID %lu`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall GetRpcClientInfo(void *a1, unsigned int *a2)
{
  DWORD *v4; // rbx
  WCHAR *v5; // r14
  unsigned int v6; // eax
  HANDLE v7; // rax
  void *v8; // rbx
  void (*v9)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD LastError; // eax
  DWORD v11; // eax
  __int64 v13; // rax
  PSID *v14; // rbx
  __int64 v15; // rax
  wchar_t *v16; // rcx
  wchar_t *v17; // rax
  WCHAR *v18; // rcx
  DWORD TokenInformationLength; // [rsp+40h] [rbp-C0h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-B8h] BYREF
  DWORD dwSize; // [rsp+50h] [rbp-B0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+54h] [rbp-ACh] BYREF
  DWORD cchReferencedDomainName; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cchName; // [rsp+5Ch] [rbp-A4h] BYREF
  void *v25; // [rsp+60h] [rbp-A0h] BYREF
  PSID *v26; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR ReferencedDomainName[32768]; // [rsp+280h] [rbp+180h] BYREF

  if ( !a2 )
    return 0;
  *a2 = 0;
  v4 = a2 + 1;
  a2[1] = 0;
  v5 = (WCHAR *)(a2 + 2);
  _o_wcscpy_s(a2 + 2, 1300, L"Unknown");
  _o_wcscpy_s(a2 + 652, 513, L"Unknown");
  _o_wcscpy_s((char *)a2 + 3634, 260, &DomainName);
  v6 = I_RpcBindingInqLocalClientPID(a1, a2);
  if ( v6 || !*a2 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"RPC Attribution: Failed to get RPC client PID, status=0x%x", v6);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"RPC Attribution: Failed to get RPC client PID, status=0x%x", v6);
      }
    }
    return 0;
  }
  if ( !ProcessIdToSessionId(*a2, v4) )
  {
    *v4 = 0;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"RPC Attribution: Failed to get session ID for RPC client PID %lu", *a2);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"RPC Attribution: Failed to get session ID for RPC client PID %lu", *a2);
      }
    }
  }
  v7 = OpenProcess(0x1000u, 0, *a2);
  v8 = v7;
  v25 = v7;
  if ( v7 )
  {
    dwSize = 1300;
    if ( !QueryFullProcessImageNameW(v7, 0, v5, &dwSize) )
      goto LABEL_24;
    v13 = -1;
    do
      ++v13;
    while ( v5[v13] );
    if ( !v13 )
    {
LABEL_24:
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"RPC Attribution: Failed to get RPC client process path for PID %lu", *a2);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"RPC Attribution: Failed to get RPC client process path for PID %lu", *a2);
        }
      }
      _o_wcscpy_s(v5, 1300, L"Unknown Process");
    }
    TokenHandle = 0;
    if ( OpenProcessToken(v8, 8u, &TokenHandle) )
    {
      TokenInformationLength = 0;
      if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) && GetLastError() == 122 )
      {
        v14 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
        v26 = v14;
        if ( v14 )
        {
          if ( GetTokenInformation(TokenHandle, TokenUser, v14, TokenInformationLength, &TokenInformationLength) )
          {
            if ( *v14 )
            {
              memset_0(Name, 0, 0x200u);
              memset_0(ReferencedDomainName, 0, 0x200u);
              cchName = 256;
              cchReferencedDomainName = 256;
              peUse = 0;
              if ( LookupAccountSidW(0, *v14, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
              {
                v15 = -1;
                do
                  ++v15;
                while ( ReferencedDomainName[v15] );
                v16 = (wchar_t *)(a2 + 652);
                if ( v15 )
                {
                  if ( swprintf_s(v16, 0x201u, L"%ws\\%ws", ReferencedDomainName, Name) == -1
                    && *(_DWORD *)&g_dwDebugLevel )
                  {
                    if ( g_lpDebugMsg )
                    {
                      g_lpDebugMsg(2u, L"RPC Attribution: Failed to format Domain\\Username - buffer too small");
                    }
                    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                    {
                      RedirectDebugMsg(2u, L"RPC Attribution: Failed to format Domain\\Username - buffer too small");
                    }
                  }
                }
                else
                {
                  _o_wcsncpy_s(v16, 513, Name, -1);
                }
              }
            }
          }
        }
        XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v26);
      }
    }
    v17 = wcsrchr(v5, 0x5Cu);
    v18 = v17 + 1;
    if ( !v17 )
      v18 = v5;
    if ( !(unsigned int)_o__wcsicmp(v18, L"mmc.exe") )
    {
      memset_0(ReferencedDomainName, 0, sizeof(ReferencedDomainName));
      if ( (unsigned int)GetProcessCommandLine(*a2, ReferencedDomainName) )
      {
        ExtractMMCSnapInFromCommandLine(ReferencedDomainName, (char *)a2 + 3634);
        if ( *((_WORD *)a2 + 1817) )
        {
          _o_wcscpy_s(Name, 260, v5);
          swprintf_s(v5, 0x514u, L"%ws [%ws]", Name, (char *)a2 + 3634);
        }
      }
    }
    XHandle::~XHandle(&TokenHandle);
  }
  else
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v9 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        LastError = GetLastError();
        v9(2u, L"RPC Attribution: Failed to open RPC client process PID %lu, error=%lu", *a2, LastError);
      }
      else if ( g_lpDebugMsgContextInstance )
      {
        if ( g_lpDebugMsgContext )
        {
          v11 = GetLastError();
          RedirectDebugMsg(2u, L"RPC Attribution: Failed to open RPC client process PID %lu, error=%lu", *a2, v11);
        }
      }
    }
    _o_wcscpy_s(v5, 1300, L"Access Denied");
  }
  XHandle::~XHandle(&v25);
  return 1;
}

```

## disassembly

```asm
0x18008dee8  mov     [rsp-8+arg_10], rbx
0x18008deed  push    rbp
0x18008deee  push    rsi
0x18008deef  push    rdi
0x18008def0  push    r12
0x18008def2  push    r13
0x18008def4  push    r14
0x18008def6  push    r15
0x18008def8  lea     rbp, [rsp-10190h]
0x18008df00  mov     eax, 10290h
0x18008df05  call    _alloca_probe
0x18008df0a  sub     rsp, rax
0x18008df0d  mov     rax, cs:__security_cookie
0x18008df14  xor     rax, rsp
0x18008df17  mov     [rbp+101C0h+var_40], rax
0x18008df1e  mov     rsi, rdx
0x18008df21  mov     rdi, rcx
0x18008df24  xor     r13d, r13d
0x18008df27  test    rdx, rdx
0x18008df2a  jz      loc_18008E400
0x18008df30  mov     [rdx], r13d
0x18008df33  lea     rbx, [rdx+4]
0x18008df37  mov     [rbx], r13d
0x18008df3a  lea     r14, [rdx+8]
0x18008df3e  lea     r8, aUnknown_0; "Unknown"
0x18008df45  mov     edx, 514h
0x18008df4a  mov     rcx, r14
0x18008df4d  call    cs:__imp__o_wcscpy_s
0x18008df53  lea     r12, [rsi+0A30h]
0x18008df5a  lea     r8, aUnknown_0; "Unknown"
0x18008df61  mov     edx, 201h
0x18008df66  mov     rcx, r12
0x18008df69  call    cs:__imp__o_wcscpy_s
0x18008df6f  lea     r15, [rsi+0E32h]
0x18008df76  lea     r8, DomainName
0x18008df7d  mov     edx, 104h
0x18008df82  mov     rcx, r15
0x18008df85  call    cs:__imp__o_wcscpy_s
0x18008df8b  mov     rdx, rsi; Pid
0x18008df8e  mov     rcx, rdi; Binding
0x18008df91  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18008df97  mov     r8d, eax
0x18008df9a  test    eax, eax
0x18008df9c  jnz     loc_18008E3B5
0x18008dfa2  mov     ecx, [rsi]; dwProcessId
0x18008dfa4  test    ecx, ecx
0x18008dfa6  jz      loc_18008E3B5
0x18008dfac  mov     rdx, rbx; pSessionId
0x18008dfaf  call    cs:__imp_ProcessIdToSessionId
0x18008dfb5  lea     edi, [r13+2]
0x18008dfb9  test    eax, eax
0x18008dfbb  jnz     short loc_18008E00B
0x18008dfbd  mov     [rbx], r13d
0x18008dfc0  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18008dfc7  jz      short loc_18008E00B
0x18008dfc9  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18008dfd0  test    rax, rax
0x18008dfd3  jz      short loc_18008DFE8
0x18008dfd5  mov     r8d, [rsi]
0x18008dfd8  lea     rdx, aRpcAttribution_6; "RPC Attribution: Failed to get session "...
0x18008dfdf  mov     ecx, edi
0x18008dfe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008dfe6  jmp     short loc_18008E00B
0x18008dfe8  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18008dfef  jz      short loc_18008E00B
0x18008dff1  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18008dff8  jz      short loc_18008E00B
0x18008dffa  mov     r8d, [rsi]
0x18008dffd  lea     rdx, aRpcAttribution_6; "RPC Attribution: Failed to get session "...
0x18008e004  mov     ecx, edi; unsigned int
0x18008e006  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18008e00b  mov     r8d, [rsi]; dwProcessId
0x18008e00e  xor     edx, edx; bInheritHandle
0x18008e010  mov     ecx, 1000h; dwDesiredAccess
0x18008e015  call    cs:__imp_OpenProcess
0x18008e01b  mov     rbx, rax
0x18008e01e  mov     [rsp+102C0h+var_10260], rax
0x18008e023  test    rax, rax
0x18008e026  jnz     loc_18008E0B3
0x18008e02c  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18008e033  jz      short loc_18008E08C
0x18008e035  mov     rbx, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18008e03c  test    rbx, rbx
0x18008e03f  jz      short loc_18008E060
0x18008e041  call    cs:__imp_GetLastError
0x18008e047  mov     r9d, eax
0x18008e04a  mov     r8d, [rsi]
0x18008e04d  lea     rdx, aRpcAttribution_2; "RPC Attribution: Failed to open RPC cli"...
0x18008e054  mov     ecx, edi
0x18008e056  mov     rax, rbx
0x18008e059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e05e  jmp     short loc_18008E08C
0x18008e060  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18008e067  jz      short loc_18008E08C
0x18008e069  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18008e070  jz      short loc_18008E08C
0x18008e072  call    cs:__imp_GetLastError
0x18008e078  mov     r9d, eax
0x18008e07b  mov     r8d, [rsi]
0x18008e07e  lea     rdx, aRpcAttribution_2; "RPC Attribution: Failed to open RPC cli"...
0x18008e085  mov     ecx, edi; unsigned int
0x18008e087  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18008e08c  lea     r8, aAccessDenied; "Access Denied"
0x18008e093  mov     edx, 514h
0x18008e098  mov     rcx, r14
0x18008e09b  call    cs:__imp__o_wcscpy_s
0x18008e0a1  nop
0x18008e0a2  lea     rcx, [rsp+102C0h+var_10260]; this
0x18008e0a7  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x18008e0ac  mov     al, 1
0x18008e0ae  jmp     loc_18008E402
0x18008e0b3  mov     [rsp+102C0h+dwSize], 514h
0x18008e0bb  lea     r9, [rsp+102C0h+dwSize]; lpdwSize
0x18008e0c0  mov     r8, r14; lpExeName
0x18008e0c3  xor     edx, edx; dwFlags
0x18008e0c5  mov     rcx, rbx; hProcess
0x18008e0c8  call    cs:__imp_QueryFullProcessImageNameW
0x18008e0ce  test    eax, eax
0x18008e0d0  jz      short loc_18008E0E5
0x18008e0d2  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008e0d6  inc     rax
0x18008e0d9  cmp     [r14+rax*2], r13w
0x18008e0de  jnz     short loc_18008E0D6
0x18008e0e0  test    rax, rax
0x18008e0e3  jnz     short loc_18008E145
0x18008e0e5  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18008e0ec  jz      short loc_18008E130
0x18008e0ee  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18008e0f5  test    rax, rax
0x18008e0f8  jz      short loc_18008E10D
0x18008e0fa  mov     r8d, [rsi]
0x18008e0fd  lea     rdx, aRpcAttribution_7; "RPC Attribution: Failed to get RPC clie"...
0x18008e104  mov     ecx, edi
0x18008e106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e10b  jmp     short loc_18008E130
0x18008e10d  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18008e114  jz      short loc_18008E130
0x18008e116  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18008e11d  jz      short loc_18008E130
0x18008e11f  mov     r8d, [rsi]
0x18008e122  lea     rdx, aRpcAttribution_7; "RPC Attribution: Failed to get RPC clie"...
0x18008e129  mov     ecx, edi; unsigned int
0x18008e12b  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18008e130  lea     r8, aUnknownProcess; "Unknown Process"
0x18008e137  mov     edx, 514h
0x18008e13c  mov     rcx, r14
0x18008e13f  call    cs:__imp__o_wcscpy_s
0x18008e145  mov     [rsp+102C0h+TokenHandle], r13
0x18008e14a  lea     r8, [rsp+102C0h+TokenHandle]; TokenHandle
0x18008e14f  mov     edx, 8; DesiredAccess
0x18008e154  mov     rcx, rbx; ProcessHandle
0x18008e157  call    cs:__imp_OpenProcessToken
0x18008e15d  test    eax, eax
0x18008e15f  jz      loc_18008E30F
0x18008e165  mov     [rsp+102C0h+TokenInformationLength], r13d
0x18008e16a  lea     rax, [rsp+102C0h+TokenInformationLength]
0x18008e16f  mov     [rsp+102C0h+ReturnLength], rax; ReturnLength
0x18008e174  xor     r9d, r9d; TokenInformationLength
0x18008e177  xor     r8d, r8d; TokenInformation
0x18008e17a  lea     edx, [r9+1]; TokenInformationClass
0x18008e17e  mov     rcx, [rsp+102C0h+TokenHandle]; TokenHandle
0x18008e183  call    cs:__imp_GetTokenInformation
0x18008e189  test    eax, eax
0x18008e18b  jnz     loc_18008E30F
0x18008e191  call    cs:__imp_GetLastError
0x18008e197  cmp     eax, 7Ah ; 'z'
0x18008e19a  jnz     loc_18008E30F
0x18008e1a0  mov     edx, [rsp+102C0h+TokenInformationLength]; uBytes
0x18008e1a4  lea     ecx, [rax-3Ah]; uFlags
0x18008e1a7  call    cs:__imp_LocalAlloc
0x18008e1ad  mov     rbx, rax
0x18008e1b0  mov     [rsp+102C0h+var_10258], rax
0x18008e1b5  test    rax, rax
0x18008e1b8  jz      loc_18008E305
0x18008e1be  lea     rax, [rsp+102C0h+TokenInformationLength]
0x18008e1c3  mov     [rsp+102C0h+ReturnLength], rax; ReturnLength
0x18008e1c8  mov     r9d, [rsp+102C0h+TokenInformationLength]; TokenInformationLength
0x18008e1cd  mov     r8, rbx; TokenInformation
0x18008e1d0  mov     edx, 1; TokenInformationClass
0x18008e1d5  mov     rcx, [rsp+102C0h+TokenHandle]; TokenHandle
0x18008e1da  call    cs:__imp_GetTokenInformation
0x18008e1e0  test    eax, eax
0x18008e1e2  jz      loc_18008E305
0x18008e1e8  cmp     [rbx], r13
0x18008e1eb  jz      loc_18008E305
0x18008e1f1  mov     r13d, 200h
0x18008e1f7  mov     r8d, r13d; Size
0x18008e1fa  xor     edx, edx; Val
0x18008e1fc  lea     rcx, [rsp+102C0h+Name]; void *
0x18008e201  call    memset_0
0x18008e206  mov     r8d, r13d; Size
0x18008e209  xor     edx, edx; Val
0x18008e20b  lea     rcx, [rbp+101C0h+ReferencedDomainName]; void *
0x18008e212  call    memset_0
0x18008e217  mov     eax, 100h
0x18008e21c  mov     [rsp+102C0h+cchName], eax
0x18008e220  mov     [rsp+102C0h+var_10268], eax
0x18008e224  xor     r13d, r13d
0x18008e227  mov     [rsp+102C0h+var_1026C], r13d
0x18008e22c  lea     rax, [rsp+102C0h+var_1026C]
0x18008e231  mov     [rsp+102C0h+peUse], rax; peUse
0x18008e236  lea     rax, [rsp+102C0h+var_10268]
0x18008e23b  mov     [rsp+102C0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18008e240  lea     rax, [rbp+101C0h+ReferencedDomainName]
0x18008e247  mov     [rsp+102C0h+ReturnLength], rax; ReferencedDomainName
0x18008e24c  lea     r9, [rsp+102C0h+cchName]; cchName
0x18008e251  lea     r8, [rsp+102C0h+Name]; Name
0x18008e256  mov     rdx, [rbx]; Sid
0x18008e259  xor     ecx, ecx; lpSystemName
0x18008e25b  call    cs:__imp_LookupAccountSidW
0x18008e261  test    eax, eax
0x18008e263  jz      loc_18008E305
0x18008e269  lea     rcx, [rbp+101C0h+ReferencedDomainName]
0x18008e270  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18008e274  mov     rax, rbx
0x18008e277  inc     rax
0x18008e27a  cmp     [rcx+rax*2], r13w
0x18008e27f  jnz     short loc_18008E277
0x18008e281  mov     edx, 201h; BufferCount
0x18008e286  mov     rcx, r12; Buffer
0x18008e289  test    rax, rax
0x18008e28c  jz      short loc_18008E2F6
0x18008e28e  lea     rax, [rsp+102C0h+Name]
0x18008e293  mov     [rsp+102C0h+ReturnLength], rax
0x18008e298  lea     r9, [rbp+101C0h+ReferencedDomainName]
0x18008e29f  lea     r8, aWsWs_0; "%ws\\%ws"
0x18008e2a6  call    swprintf_s
0x18008e2ab  cmp     eax, ebx
0x18008e2ad  jnz     short loc_18008E305
0x18008e2af  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18008e2b6  jz      short loc_18008E305
0x18008e2b8  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18008e2bf  test    rax, rax
0x18008e2c2  jz      short loc_18008E2D4
0x18008e2c4  lea     rdx, aRpcAttribution_9; "RPC Attribution: Failed to format Domai"...
0x18008e2cb  mov     ecx, edi
0x18008e2cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e2d2  jmp     short loc_18008E305
0x18008e2d4  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18008e2db  jz      short loc_18008E305
0x18008e2dd  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18008e2e4  jz      short loc_18008E305
0x18008e2e6  lea     rdx, aRpcAttribution_9; "RPC Attribution: Failed to format Domai"...
0x18008e2ed  mov     ecx, edi; unsigned int
0x18008e2ef  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18008e2f4  jmp     short loc_18008E305
0x18008e2f6  mov     r9, rbx
0x18008e2f9  lea     r8, [rsp+102C0h+Name]
0x18008e2fe  call    cs:__imp__o_wcsncpy_s
0x18008e304  nop
0x18008e305  lea     rcx, [rsp+102C0h+var_10258]
0x18008e30a  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x18008e30f  mov     edx, 5Ch ; '\'; Ch
0x18008e314  mov     rcx, r14; Str
0x18008e317  call    cs:__imp_wcsrchr
0x18008e31d  lea     rcx, [rax+2]
0x18008e321  test    rax, rax
0x18008e324  cmovz   rcx, r14
0x18008e328  lea     rdx, aMmcExe; "mmc.exe"
0x18008e32f  call    cs:__imp__o__wcsicmp
0x18008e335  test    eax, eax
0x18008e337  jnz     short loc_18008E3A6
0x18008e339  xor     edx, edx; Val
0x18008e33b  mov     r8d, 10000h; Size
0x18008e341  lea     rcx, [rbp+101C0h+ReferencedDomainName]; void *
0x18008e348  call    memset_0
0x18008e34d  lea     rdx, [rbp+101C0h+ReferencedDomainName]
0x18008e354  mov     ecx, [rsi]
0x18008e356  call    GetProcessCommandLine
0x18008e35b  test    eax, eax
0x18008e35d  jz      short loc_18008E3A6
0x18008e35f  mov     rdx, r15
0x18008e362  lea     rcx, [rbp+101C0h+ReferencedDomainName]
0x18008e369  call    ExtractMMCSnapInFromCommandLine
0x18008e36e  cmp     [r15], r13w
0x18008e372  jz      short loc_18008E3A6
0x18008e374  mov     r8, r14
0x18008e377  mov     edx, 104h
0x18008e37c  lea     rcx, [rsp+102C0h+Name]
0x18008e381  call    cs:__imp__o_wcscpy_s
0x18008e387  mov     [rsp+102C0h+ReturnLength], r15
0x18008e38c  lea     r9, [rsp+102C0h+Name]
0x18008e391  lea     r8, aWsWs; "%ws [%ws]"
0x18008e398  mov     edx, 514h; BufferCount
0x18008e39d  mov     rcx, r14; Buffer
0x18008e3a0  call    swprintf_s
0x18008e3a5  nop
0x18008e3a6  lea     rcx, [rsp+102C0h+TokenHandle]; this
0x18008e3ab  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x18008e3b0  jmp     loc_18008E0A2
0x18008e3b5  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18008e3bc  jz      short loc_18008E400
0x18008e3be  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18008e3c5  test    rax, rax
0x18008e3c8  jz      short loc_18008E3DD
0x18008e3ca  lea     rdx, aRpcAttribution_5; "RPC Attribution: Failed to get RPC clie"...
0x18008e3d1  mov     ecx, 2
0x18008e3d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e3db  jmp     short loc_18008E400
0x18008e3dd  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
  ... truncated ...
```
