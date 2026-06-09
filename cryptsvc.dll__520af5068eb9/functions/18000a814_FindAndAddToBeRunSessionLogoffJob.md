# FindAndAddToBeRunSessionLogoffJob

- ea: `0x18000a814`
- end: `0x18000a952`
- name: `FindAndAddToBeRunSessionLogoffJob`
- size: `318`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000a690`

## callees

- `0x180004180`
- `0x1800068f0`
- `0x18000a814`
- `0x18000a958`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a843`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a88c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a843`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a88c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a829`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a829`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000a8a5`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000a8a5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a936`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a936`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a84e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a84e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a8b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a8c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a8b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a8c1`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000a8ed`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000a8ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a941`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a941`

## pseudocode

```c
__int64 __fastcall FindAndAddToBeRunSessionLogoffJob(unsigned int a1)
{
  __int64 PendingLogoffExitJob; // rax
  __int64 v3; // rdx
  _QWORD *v4; // rsi
  unsigned int v5; // ebp
  _QWORD *v6; // rax
  _QWORD *v7; // rcx
  HANDLE EventA; // rax
  HANDLE CurrentProcess; // rax
  void *v10; // rdi
  void *v11; // rbx
  HANDLE v12; // rax
  HANDLE TargetHandle; // [rsp+78h] [rbp+10h] BYREF

  EnterCriticalSection(&JobsCriticalSection);
  PendingLogoffExitJob = FindPendingLogoffExitJob(a1, 0);
  v4 = (_QWORD *)PendingLogoffExitJob;
  if ( !PendingLogoffExitJob )
  {
    LeaveCriticalSection(&JobsCriticalSection);
    SetLastError(0x80092004);
    return 0;
  }
  v5 = 1;
  *(_DWORD *)(PendingLogoffExitJob + 64) = 1;
  v6 = *(_QWORD **)PendingLogoffExitJob;
  v7 = (_QWORD *)v4[1];
  if ( v6 )
  {
    v6[1] = v7;
    *v4 = v3;
  }
  if ( v7 )
  {
    *v7 = v6;
    v4[1] = v3;
  }
  else
  {
    pPendingLogoffExitJobHead = v6;
  }
  LeaveCriticalSection(&JobsCriticalSection);
  TargetHandle = 0;
  EventA = CreateEventA(0, 0, 0, 0);
  v4[9] = EventA;
  if ( EventA )
  {
    CurrentProcess = GetCurrentProcess();
    v10 = (void *)v4[9];
    v11 = CurrentProcess;
    v12 = GetCurrentProcess();
    if ( !DuplicateHandle(v12, v10, v11, &TargetHandle, 0, 0, 2u) )
      TargetHandle = 0;
  }
  if ( !(unsigned int)AddToBeRunJobEx((FILETIME)v4, 4, 0, 0) )
  {
    if ( TargetHandle )
      I_UrlCacheCloseHandle(TargetHandle);
    return 0;
  }
  if ( TargetHandle )
  {
    WaitForSingleObjectEx(TargetHandle, 0x1388u, 0);
    CloseHandle(TargetHandle);
  }
  return v5;
}

```

## disassembly

```asm
0x18000a814  push    rbx
0x18000a816  push    rbp
0x18000a817  push    rsi
0x18000a818  push    rdi
0x18000a819  sub     rsp, 48h
0x18000a81d  mov     ebx, ecx
0x18000a81f  lea     rdi, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION JobsCriticalSection
0x18000a826  mov     rcx, rdi; lpCriticalSection
0x18000a829  call    cs:__imp_EnterCriticalSection
0x18000a82f  xor     edx, edx
0x18000a831  mov     ecx, ebx
0x18000a833  call    FindPendingLogoffExitJob
0x18000a838  mov     rsi, rax
0x18000a83b  test    rax, rax
0x18000a83e  jnz     short loc_18000A859
0x18000a840  mov     rcx, rdi; lpCriticalSection
0x18000a843  call    cs:__imp_LeaveCriticalSection
0x18000a849  mov     ecx, 80092004h; dwErrCode
0x18000a84e  call    cs:__imp_SetLastError
0x18000a854  jmp     loc_18000A925
0x18000a859  mov     ebp, 1
0x18000a85e  mov     [rax+40h], ebp
0x18000a861  mov     rax, [rax]
0x18000a864  mov     rcx, [rsi+8]
0x18000a868  test    rax, rax
0x18000a86b  jz      short loc_18000A874
0x18000a86d  mov     [rax+8], rcx
0x18000a871  mov     [rsi], rdx
0x18000a874  test    rcx, rcx
0x18000a877  jz      short loc_18000A882
0x18000a879  mov     [rcx], rax
0x18000a87c  mov     [rsi+8], rdx
0x18000a880  jmp     short loc_18000A889
0x18000a882  mov     cs:?pPendingLogoffExitJobHead@@3PEAU_CUCS_LOGOFF_EXIT_JOB_ENTRY@@EA, rax; _CUCS_LOGOFF_EXIT_JOB_ENTRY * pPendingLogoffExitJobHead
0x18000a889  mov     rcx, rdi; lpCriticalSection
0x18000a88c  call    cs:__imp_LeaveCriticalSection
0x18000a892  xor     r9d, r9d; lpName
0x18000a895  mov     [rsp+68h+TargetHandle], 0
0x18000a89e  xor     r8d, r8d; bInitialState
0x18000a8a1  xor     edx, edx; bManualReset
0x18000a8a3  xor     ecx, ecx; lpEventAttributes
0x18000a8a5  call    cs:__imp_CreateEventA
0x18000a8ab  mov     [rsi+48h], rax
0x18000a8af  test    rax, rax
0x18000a8b2  jz      short loc_18000A900
0x18000a8b4  call    cs:__imp_GetCurrentProcess
0x18000a8ba  mov     rdi, [rsi+48h]
0x18000a8be  mov     rbx, rax
0x18000a8c1  call    cs:__imp_GetCurrentProcess
0x18000a8c7  mov     [rsp+68h+dwOptions], 2; dwOptions
0x18000a8cf  lea     r9, [rsp+68h+TargetHandle]; lpTargetHandle
0x18000a8d4  mov     rcx, rax; hSourceProcessHandle
0x18000a8d7  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x18000a8df  mov     r8, rbx; hTargetProcessHandle
0x18000a8e2  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x18000a8ea  mov     rdx, rdi; hSourceHandle
0x18000a8ed  call    cs:__imp_DuplicateHandle
0x18000a8f3  test    eax, eax
0x18000a8f5  jnz     short loc_18000A900
0x18000a8f7  mov     [rsp+68h+TargetHandle], 0
0x18000a900  xor     r9d, r9d
0x18000a903  xor     r8d, r8d
0x18000a906  mov     rcx, rsi
0x18000a909  lea     edx, [r9+4]
0x18000a90d  call    AddToBeRunJobEx
0x18000a912  mov     rcx, [rsp+68h+TargetHandle]; hObject
0x18000a917  test    eax, eax
0x18000a919  jnz     short loc_18000A929
0x18000a91b  test    rcx, rcx
0x18000a91e  jz      short loc_18000A925
0x18000a920  call    I_UrlCacheCloseHandle
0x18000a925  xor     ebp, ebp
0x18000a927  jmp     short loc_18000A947
0x18000a929  test    rcx, rcx
0x18000a92c  jz      short loc_18000A947
0x18000a92e  xor     r8d, r8d; bAlertable
0x18000a931  mov     edx, 1388h; dwMilliseconds
0x18000a936  call    cs:__imp_WaitForSingleObjectEx
0x18000a93c  mov     rcx, [rsp+68h+TargetHandle]; hObject
0x18000a941  call    cs:__imp_CloseHandle
0x18000a947  mov     eax, ebp
0x18000a949  add     rsp, 48h
0x18000a94d  pop     rdi
0x18000a94e  pop     rsi
0x18000a94f  pop     rbp
0x18000a950  pop     rbx
0x18000a951  retn
```
