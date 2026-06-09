# AcceptCredentialsAsyncWorker(void *)

- ea: `0x18005a420`
- end: `0x18005a624`
- name: `?AcceptCredentialsAsyncWorker@@YAIPEAX@Z`
- size: `516`
- prototype: `ULONG __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x180020b10`
- `0x1800336a4`
- `0x18005a1fc`
- `0x18005a26c`
- `0x18005a420`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a4c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a4cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a4d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a4c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a4cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a4d5`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18005a4b7`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18005a5bd`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18005a4b7`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18005a5bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005a43f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005a59f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005a43f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005a59f`
- `ntdll!NtClose` at `0x18005a5f9`
- `ntdll!NtClose` at `0x18005a5f9`
- `ntdll!NtSetInformationThread` at `0x18005a533`
- `ntdll!NtSetInformationThread` at `0x18005a5e5`
- `ntdll!NtSetInformationThread` at `0x18005a533`
- `ntdll!NtSetInformationThread` at `0x18005a5e5`
- `ntdll!RtlNtStatusToDosError` at `0x18005a61d`

## string_xrefs

- `0x18005a45b`: `onecore\ds\ext\cloudap\dll\credapi.cpp`
- `0x18005a4eb`: `onecore\ds\ext\cloudap\dll\credapi.cpp`
- `0x18005a55f`: `onecore\ds\ext\cloudap\dll\credapi.cpp`
- `0x18005a480`: `threadParam`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
ULONG __fastcall AcceptCredentialsAsyncWorker(_QWORD *a1)
{
  _QWORD *v1; // rsi
  char v3; // r15
  unsigned int LastError; // edi
  const char *v5; // rax
  const char *v6; // rax
  const char *v7; // rax
  void *v8; // rcx
  __int64 v10; // [rsp+20h] [rbp-20h]
  __int64 ThreadInformation; // [rsp+70h] [rbp+30h] BYREF
  DWORD CurrentThreadId; // [rsp+78h] [rbp+38h] BYREF
  _QWORD *v13; // [rsp+80h] [rbp+40h] BYREF

  v1 = 0;
  v13 = 0;
  v3 = 0;
  LODWORD(ThreadInformation) = GetCurrentThreadId();
  CloudAPProvider::AcceptCredentialsAsyncWorkerStart<unsigned long>(&ThreadInformation);
  if ( a1 )
  {
    v13 = a1;
    v1 = a1;
    if ( TlsSetValue(g_dwTlsCloudAPIndex, a1 + 5)
      || ((int)GetLastError() > 0
        ? (LastError = (unsigned __int16)GetLastError() | 0xC0070000)
        : (LastError = GetLastError()),
          (LODWORD(ThreadInformation) = LastError) == 0) )
    {
      if ( a1[5] )
      {
        NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, a1 + 5, 8u);
        v3 = 1;
      }
      LODWORD(ThreadInformation) = SpAcceptCredentialsInternal(
                                     *(unsigned int *)a1,
                                     a1 + 1,
                                     a1[3],
                                     a1[4],
                                     *((_DWORD *)a1 + 12));
      LastError = ThreadInformation;
      if ( (_DWORD)ThreadInformation )
      {
        v7 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\credapi.cpp");
        LODWORD(v10) = 736;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LastError, v7, v10, "AcceptCredentialsAsyncWorker", &Class);
      }
    }
    else
    {
      v6 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\credapi.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LastError, v6, 716, "TlsSetValue", &Class);
    }
  }
  else
  {
    LastError = -1073741811;
    LODWORD(ThreadInformation) = -1073741811;
    v5 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\credapi.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v5, 707, "threadParam", &Class);
  }
  CurrentThreadId = GetCurrentThreadId();
  CloudAPProvider::AcceptCredentialsAsyncWorkerStop<long &,unsigned long>(&ThreadInformation, &CurrentThreadId);
  TlsSetValue(g_dwTlsCloudAPIndex, 0);
  if ( v3 )
  {
    ThreadInformation = 0;
    NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
  }
  if ( a1 )
  {
    v8 = (void *)v1[5];
    if ( v8 )
      NtClose(v8);
  }
  FreeAcceptCredentialsData(&v13);
  return RtlNtStatusToDosError(LastError);
}

```

## disassembly

```asm
0x18005a420  mov     [rsp-28h+arg_18], rbx
0x18005a425  push    rbp
0x18005a426  push    rsi
0x18005a427  push    rdi
0x18005a428  push    r14
0x18005a42a  push    r15
0x18005a42c  mov     rbp, rsp
0x18005a42f  sub     rsp, 40h
0x18005a433  xor     esi, esi
0x18005a435  mov     rbx, rcx
0x18005a438  mov     [rbp+arg_10], rsi
0x18005a43c  xor     r15b, r15b
0x18005a43f  call    cs:__imp_GetCurrentThreadId
0x18005a445  lea     rcx, [rbp+ThreadInformation]
0x18005a449  mov     dword ptr [rbp+ThreadInformation], eax
0x18005a44c  call    ??$AcceptCredentialsAsyncWorkerStart@K@CloudAPProvider@@SAX$$QEAK@Z; CloudAPProvider::AcceptCredentialsAsyncWorkerStart<ulong>(ulong &&)
0x18005a451  test    rbx, rbx
0x18005a454  jnz     short loc_18005A4A3
0x18005a456  mov     edi, 0C000000Dh
0x18005a45b  lea     rcx, aOnecoreDsExtCl_4; "onecore\\ds\\ext\\cloudap\\dll\\credapi"...
0x18005a462  mov     dword ptr [rbp+ThreadInformation], edi
0x18005a465  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005a46a  lea     rcx, Class
0x18005a471  mov     r9, rax
0x18005a474  mov     [rsp+40h+var_10], rcx
0x18005a479  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005a480  lea     rcx, aThreadparam; "threadParam"
0x18005a487  mov     r8d, edi
0x18005a48a  mov     [rsp+40h+var_18], rcx
0x18005a48f  xor     ecx, ecx
0x18005a491  mov     dword ptr [rsp+40h+var_20], 2C3h
0x18005a499  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005a49e  jmp     loc_18005A59F
0x18005a4a3  mov     ecx, cs:?g_dwTlsCloudAPIndex@@3KA; dwTlsIndex
0x18005a4a9  lea     r14, [rbx+28h]
0x18005a4ad  mov     rdx, r14; lpTlsValue
0x18005a4b0  mov     [rbp+arg_10], rbx
0x18005a4b4  mov     rsi, rbx
0x18005a4b7  call    cs:__imp_TlsSetValue
0x18005a4bd  test    eax, eax
0x18005a4bf  jnz     short loc_18005A519
0x18005a4c1  call    cs:__imp_GetLastError
0x18005a4c7  test    eax, eax
0x18005a4c9  jg      short loc_18005A4D5
0x18005a4cb  call    cs:__imp_GetLastError
0x18005a4d1  mov     edi, eax
0x18005a4d3  jmp     short loc_18005A4E4
0x18005a4d5  call    cs:__imp_GetLastError
0x18005a4db  movzx   edi, ax
0x18005a4de  or      edi, 0C0070000h
0x18005a4e4  mov     dword ptr [rbp+ThreadInformation], edi
0x18005a4e7  test    edi, edi
0x18005a4e9  jz      short loc_18005A519
0x18005a4eb  lea     rcx, aOnecoreDsExtCl_4; "onecore\\ds\\ext\\cloudap\\dll\\credapi"...
0x18005a4f2  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005a4f7  lea     rcx, Class
0x18005a4fe  mov     [rsp+40h+var_10], rcx
0x18005a503  lea     rcx, aTlssetvalue; "TlsSetValue"
0x18005a50a  mov     [rsp+40h+var_18], rcx
0x18005a50f  mov     dword ptr [rsp+40h+var_20], 2CCh
0x18005a517  jmp     short loc_18005A58B
0x18005a519  cmp     qword ptr [r14], 0
0x18005a51d  jz      short loc_18005A53C
0x18005a51f  mov     r9d, 8; ThreadInformationLength
0x18005a525  mov     r8, r14; ThreadInformation
0x18005a528  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18005a52f  lea     edx, [r9-3]; ThreadInformationClass
0x18005a533  call    cs:__imp_NtSetInformationThread
0x18005a539  mov     r15b, 1
0x18005a53c  mov     eax, [rbx+30h]
0x18005a53f  lea     rdx, [rbx+8]
0x18005a543  mov     r9, [rbx+20h]
0x18005a547  mov     r8, [rbx+18h]
0x18005a54b  mov     ecx, [rbx]
0x18005a54d  mov     dword ptr [rsp+40h+var_20], eax
0x18005a551  call    SpAcceptCredentialsInternal
0x18005a556  mov     dword ptr [rbp+ThreadInformation], eax
0x18005a559  mov     edi, eax
0x18005a55b  test    eax, eax
0x18005a55d  jz      short loc_18005A59F
0x18005a55f  lea     rcx, aOnecoreDsExtCl_4; "onecore\\ds\\ext\\cloudap\\dll\\credapi"...
0x18005a566  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005a56b  lea     rcx, Class
0x18005a572  mov     [rsp+40h+var_10], rcx
0x18005a577  lea     rcx, aAcceptcredenti; "AcceptCredentialsAsyncWorker"
0x18005a57e  mov     [rsp+40h+var_18], rcx
0x18005a583  mov     dword ptr [rsp+40h+var_20], 2E0h
0x18005a58b  mov     r9, rax
0x18005a58e  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005a595  mov     r8d, edi
0x18005a598  xor     ecx, ecx
0x18005a59a  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005a59f  call    cs:__imp_GetCurrentThreadId
0x18005a5a5  lea     rdx, [rbp+arg_8]
0x18005a5a9  mov     [rbp+arg_8], eax
0x18005a5ac  lea     rcx, [rbp+ThreadInformation]
0x18005a5b0  call    ??$AcceptCredentialsAsyncWorkerStop@AEAJK@CloudAPProvider@@SAXAEAJ$$QEAK@Z; CloudAPProvider::AcceptCredentialsAsyncWorkerStop<long &,ulong>(long &,ulong &&)
0x18005a5b5  mov     ecx, cs:?g_dwTlsCloudAPIndex@@3KA; dwTlsIndex
0x18005a5bb  xor     edx, edx; lpTlsValue
0x18005a5bd  call    cs:__imp_TlsSetValue
0x18005a5c3  test    r15b, r15b
0x18005a5c6  jz      short loc_18005A5EB
0x18005a5c8  mov     r9d, 8; ThreadInformationLength
0x18005a5ce  mov     [rbp+ThreadInformation], 0
0x18005a5d6  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x18005a5da  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18005a5e1  lea     edx, [r9-3]; ThreadInformationClass
0x18005a5e5  call    cs:__imp_NtSetInformationThread
0x18005a5eb  test    rbx, rbx
0x18005a5ee  jz      short loc_18005A5FF
0x18005a5f0  mov     rcx, [rsi+28h]; Handle
0x18005a5f4  test    rcx, rcx
0x18005a5f7  jz      short loc_18005A5FF
0x18005a5f9  call    cs:__imp_NtClose
0x18005a5ff  lea     rcx, [rbp+arg_10]
0x18005a603  call    FreeAcceptCredentialsData
0x18005a608  mov     ecx, edi
0x18005a60a  mov     rbx, [rsp+40h+arg_18]
0x18005a612  add     rsp, 40h
0x18005a616  pop     r15
0x18005a618  pop     r14
0x18005a61a  pop     rdi
0x18005a61b  pop     rsi
0x18005a61c  pop     rbp
0x18005a61d  jmp     cs:__imp_RtlNtStatusToDosError
```
