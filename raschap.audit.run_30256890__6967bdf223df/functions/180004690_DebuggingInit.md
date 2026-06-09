# DebuggingInit

- ea: `0x180004690`
- end: `0x180004791`
- name: `DebuggingInit`
- size: `257`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800042f0`
- `0x18000f300`
- `0x18000f950`
- `0x180016cb0`
- `0x180017400`
- `0x180017500`
- `0x1800176e0`
- `0x180017870`
- `0x18001cf30`
- `0x18001d130`
- `0x18001d950`

## callees

- `0x180004690`
- `0x1800047a0`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180004705`
- `ntdll!NtQueryInformationToken` at `0x180004705`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004782`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004782`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000471f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000471f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004736`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004736`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000469f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000469f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800046d8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800046d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800046c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800046c5`
- `rtutils!TraceDeregisterExA` at `0x180004769`
- `rtutils!TraceDeregisterExA` at `0x180004769`

## pseudocode

```c
__int64 __fastcall DebuggingInit(int a1)
{
  BOOL v2; // ebx
  HANDLE CurrentProcess; // rax
  int v5; // eax
  int TokenInformation; // [rsp+40h] [rbp+8h] BYREF
  ULONG ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  EnterCriticalSection(&g_criticalSection);
  if ( a1 )
  {
    if ( !g_dwDebuggingRefCount )
    {
      v2 = 0;
      TokenHandle = 0;
      ReturnLength = 0;
      TokenInformation = 0;
      CurrentProcess = GetCurrentProcess();
      if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      {
        if ( NtQueryInformationToken(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) >= 0 )
          v2 = TokenInformation != 0;
      }
      else
      {
        GetLastError();
      }
      if ( TokenHandle )
        CloseHandle(TokenHandle);
      if ( !v2 )
        DebugInitEx();
    }
    ++g_dwDebuggingRefCount;
  }
  else
  {
    v5 = g_dwDebuggingRefCount;
    if ( !g_dwDebuggingRefCount || (--g_dwDebuggingRefCount, v5 == 1) )
    {
      if ( g_dwTraceId != -1 )
      {
        TraceDeregisterExA(g_dwTraceId, 4u);
        g_dwTraceId = -1;
      }
    }
  }
  LeaveCriticalSection(&g_criticalSection);
  return 0;
}

```

## disassembly

```asm
0x180004690  push    rbx
0x180004692  sub     rsp, 30h
0x180004696  mov     ebx, ecx
0x180004698  lea     rcx, g_criticalSection; lpCriticalSection
0x18000469f  call    cs:__imp_EnterCriticalSection
0x1800046a5  test    ebx, ebx
0x1800046a7  jz      loc_180004744
0x1800046ad  cmp     cs:g_dwDebuggingRefCount, 0
0x1800046b4  jnz     short loc_180004729
0x1800046b6  xor     ebx, ebx
0x1800046b8  mov     [rsp+38h+TokenHandle], rbx
0x1800046bd  mov     [rsp+38h+arg_8], ebx
0x1800046c1  mov     [rsp+38h+TokenInformation], ebx
0x1800046c5  call    cs:__imp_GetCurrentProcess
0x1800046cb  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x1800046d0  mov     edx, 8; DesiredAccess
0x1800046d5  mov     rcx, rax; ProcessHandle
0x1800046d8  call    cs:__imp_OpenProcessToken
0x1800046de  test    eax, eax
0x1800046e0  jz      loc_180004782
0x1800046e6  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800046eb  lea     rax, [rsp+38h+arg_8]
0x1800046f0  mov     r9d, 4; TokenInformationLength
0x1800046f6  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800046fb  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180004700  mov     edx, 1Dh; TokenInformationClass
0x180004705  call    cs:__imp_NtQueryInformationToken
0x18000470b  test    eax, eax
0x18000470d  js      short loc_180004715
0x18000470f  cmp     [rsp+38h+TokenInformation], ebx
0x180004713  jnz     short loc_18000478A
0x180004715  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18000471a  test    rcx, rcx
0x18000471d  jz      short loc_180004725
0x18000471f  call    cs:__imp_CloseHandle
0x180004725  test    ebx, ebx
0x180004727  jz      short loc_18000477B
0x180004729  inc     cs:g_dwDebuggingRefCount
0x18000472f  lea     rcx, g_criticalSection; lpCriticalSection
0x180004736  call    cs:__imp_LeaveCriticalSection
0x18000473c  xor     eax, eax
0x18000473e  add     rsp, 30h
0x180004742  pop     rbx
0x180004743  retn
0x180004744  mov     eax, cs:g_dwDebuggingRefCount
0x18000474a  test    eax, eax
0x18000474c  jz      short loc_180004759
0x18000474e  add     eax, 0FFFFFFFFh
0x180004751  mov     cs:g_dwDebuggingRefCount, eax
0x180004757  jnz     short loc_18000472F
0x180004759  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000475f  cmp     ecx, 0FFFFFFFFh
0x180004762  jz      short loc_18000472F
0x180004764  mov     edx, 4; dwFlags
0x180004769  call    cs:__imp_TraceDeregisterExA
0x18000476f  mov     cs:g_dwTraceId, 0FFFFFFFFh
0x180004779  jmp     short loc_18000472F
0x18000477b  call    DebugInitEx
0x180004780  jmp     short loc_180004729
0x180004782  call    cs:__imp_GetLastError
0x180004788  jmp     short loc_180004715
0x18000478a  mov     ebx, 1
0x18000478f  jmp     short loc_180004715
```
