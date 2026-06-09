# Dispatcher::fillRequests(void)

- ea: `0x180017478`
- end: `0x1800175c5`
- name: `?fillRequests@Dispatcher@@IEAAXXZ`
- size: `333`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180017720`

## callees

- `0x180017478`
- `0x180019010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800175b6`
- `KERNEL32!CloseHandle` at `0x1800175b6`
- `KERNEL32!TryEnterCriticalSection` at `0x1800174e8`
- `KERNEL32!TryEnterCriticalSection` at `0x18001751f`
- `KERNEL32!TryEnterCriticalSection` at `0x1800174e8`
- `KERNEL32!TryEnterCriticalSection` at `0x18001751f`
- `KERNEL32!SwitchToThread` at `0x1800174df`
- `KERNEL32!SwitchToThread` at `0x180017516`
- `KERNEL32!SwitchToThread` at `0x1800174df`
- `KERNEL32!SwitchToThread` at `0x180017516`
- `KERNEL32!WaitForSingleObject` at `0x1800175ad`
- `KERNEL32!WaitForSingleObject` at `0x1800175ad`
- `KERNEL32!GetQueuedCompletionStatus` at `0x1800174b7`
- `KERNEL32!GetQueuedCompletionStatus` at `0x1800174b7`
- `KERNEL32!DuplicateHandle` at `0x18001757f`
- `KERNEL32!DuplicateHandle` at `0x18001757f`
- `KERNEL32!SetEvent` at `0x180017594`
- `KERNEL32!SetEvent` at `0x180017594`
- `KERNEL32!EnterCriticalSection` at `0x1800174f7`
- `KERNEL32!EnterCriticalSection` at `0x18001752e`
- `KERNEL32!EnterCriticalSection` at `0x1800174f7`
- `KERNEL32!EnterCriticalSection` at `0x18001752e`
- `KERNEL32!LeaveCriticalSection` at `0x180017503`
- `KERNEL32!LeaveCriticalSection` at `0x18001759d`
- `KERNEL32!LeaveCriticalSection` at `0x180017503`
- `KERNEL32!LeaveCriticalSection` at `0x18001759d`
- `KERNEL32!GetLastError` at `0x18001753e`
- `KERNEL32!GetLastError` at `0x18001753e`

## pseudocode

```c
void __fastcall Dispatcher::fillRequests(LPCRITICAL_SECTION lpCriticalSection)
{
  BOOL QueuedCompletionStatus; // esi
  int v3; // edi
  int v4; // edi
  void *SpinCount; // rdi
  DWORD NumberOfBytesTransferred; // [rsp+60h] [rbp+8h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+70h] [rbp+18h] BYREF
  unsigned __int64 CompletionKey; // [rsp+78h] [rbp+20h] BYREF

  NumberOfBytesTransferred = 0;
  CompletionKey = 0;
  Overlapped = 0;
  while ( 1 )
  {
    QueuedCompletionStatus = GetQueuedCompletionStatus(
                               lpCriticalSection[1].OwningThread,
                               &NumberOfBytesTransferred,
                               &CompletionKey,
                               &Overlapped,
                               lpCriticalSection[1].RecursionCount);
    if ( Overlapped )
    {
      ((void (__fastcall *)(LPOVERLAPPED))Overlapped->Internal)(Overlapped);
      v3 = 0;
      while ( !TryEnterCriticalSection(lpCriticalSection) )
      {
        if ( ++v3 >= 100 )
        {
          EnterCriticalSection(lpCriticalSection);
          break;
        }
        SwitchToThread();
      }
      ++lpCriticalSection[1].LockCount;
      goto LABEL_10;
    }
    v4 = 0;
    while ( !TryEnterCriticalSection(lpCriticalSection) )
    {
      if ( ++v4 >= 100 )
      {
        EnterCriticalSection(lpCriticalSection);
        break;
      }
      SwitchToThread();
    }
    if ( lpCriticalSection[1].LockCount > 0 || QueuedCompletionStatus || GetLastError() != 258 )
      break;
LABEL_10:
    LeaveCriticalSection(lpCriticalSection);
  }
  SpinCount = (void *)lpCriticalSection[1].SpinCount;
  lpCriticalSection[1].SpinCount = 0;
  DuplicateHandle(
    (HANDLE)0xFFFFFFFFFFFFFFFFLL,
    (HANDLE)0xFFFFFFFFFFFFFFFELL,
    (HANDLE)0xFFFFFFFFFFFFFFFFLL,
    (LPHANDLE)&lpCriticalSection[1].SpinCount,
    0,
    0,
    2u);
  --lpCriticalSection[1].LockCount;
  if ( LODWORD(lpCriticalSection[1].DebugInfo)-- == 1 )
    SetEvent(lpCriticalSection[1].LockSemaphore);
  LeaveCriticalSection(lpCriticalSection);
  if ( SpinCount )
  {
    WaitForSingleObject(SpinCount, 0xFFFFFFFF);
    CloseHandle(SpinCount);
  }
}

```

## disassembly

```asm
0x180017478  push    rbx
0x18001747a  push    rsi
0x18001747b  push    rdi
0x18001747c  sub     rsp, 40h
0x180017480  mov     rbx, rcx
0x180017483  mov     [rsp+58h+NumberOfBytesTransferred], 0
0x18001748b  mov     [rsp+58h+CompletionKey], 0
0x180017494  mov     [rsp+58h+Overlapped], 0
0x18001749d  mov     eax, [rbx+34h]
0x1800174a0  mov     [rsp+58h+dwMilliseconds], eax; dwMilliseconds
0x1800174a4  lea     r9, [rsp+58h+Overlapped]; lpOverlapped
0x1800174a9  lea     r8, [rsp+58h+CompletionKey]; lpCompletionKey
0x1800174ae  lea     rdx, [rsp+58h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1800174b3  mov     rcx, [rbx+38h]; CompletionPort
0x1800174b7  call    cs:__imp_GetQueuedCompletionStatus
0x1800174bd  mov     esi, eax
0x1800174bf  mov     rax, [rsp+58h+Overlapped]
0x1800174c4  test    rax, rax
0x1800174c7  jz      short loc_18001750B
0x1800174c9  mov     rcx, rax
0x1800174cc  mov     rax, [rax]
0x1800174cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174d4  xor     edi, edi
0x1800174d6  jmp     short loc_1800174E5
0x1800174d8  inc     edi
0x1800174da  cmp     edi, 64h ; 'd'
0x1800174dd  jge     short loc_1800174F4
0x1800174df  call    cs:__imp_SwitchToThread
0x1800174e5  mov     rcx, rbx; lpCriticalSection
0x1800174e8  call    cs:__imp_TryEnterCriticalSection
0x1800174ee  test    eax, eax
0x1800174f0  jz      short loc_1800174D8
0x1800174f2  jmp     short loc_1800174FD
0x1800174f4  mov     rcx, rbx; lpCriticalSection
0x1800174f7  call    cs:__imp_EnterCriticalSection
0x1800174fd  inc     dword ptr [rbx+30h]
0x180017500  mov     rcx, rbx; lpCriticalSection
0x180017503  call    cs:__imp_LeaveCriticalSection
0x180017509  jmp     short loc_18001749D
0x18001750b  xor     edi, edi
0x18001750d  jmp     short loc_18001751C
0x18001750f  inc     edi
0x180017511  cmp     edi, 64h ; 'd'
0x180017514  jge     short loc_18001752B
0x180017516  call    cs:__imp_SwitchToThread
0x18001751c  mov     rcx, rbx; lpCriticalSection
0x18001751f  call    cs:__imp_TryEnterCriticalSection
0x180017525  test    eax, eax
0x180017527  jz      short loc_18001750F
0x180017529  jmp     short loc_180017534
0x18001752b  mov     rcx, rbx; lpCriticalSection
0x18001752e  call    cs:__imp_EnterCriticalSection
0x180017534  cmp     dword ptr [rbx+30h], 0
0x180017538  jg      short loc_18001754B
0x18001753a  test    esi, esi
0x18001753c  jnz     short loc_18001754B
0x18001753e  call    cs:__imp_GetLastError
0x180017544  cmp     eax, 102h
0x180017549  jz      short loc_180017500
0x18001754b  lea     r9, [rbx+48h]; lpTargetHandle
0x18001754f  mov     rdi, [r9]
0x180017552  mov     qword ptr [r9], 0
0x180017559  mov     [rsp+58h+dwOptions], 2; dwOptions
0x180017561  mov     [rsp+58h+bInheritHandle], 0; bInheritHandle
0x180017569  mov     [rsp+58h+dwMilliseconds], 0; dwDesiredAccess
0x180017571  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180017575  mov     r8, rsi; hTargetProcessHandle
0x180017578  lea     rdx, [rsi-1]; hSourceHandle
0x18001757c  mov     rcx, rsi; hSourceProcessHandle
0x18001757f  call    cs:__imp_DuplicateHandle
0x180017585  add     [rbx+30h], esi
0x180017588  or      esi, 0FFFFFFFFh
0x18001758b  add     [rbx+28h], esi
0x18001758e  jnz     short loc_18001759A
0x180017590  mov     rcx, [rbx+40h]; hEvent
0x180017594  call    cs:__imp_SetEvent
0x18001759a  mov     rcx, rbx; lpCriticalSection
0x18001759d  call    cs:__imp_LeaveCriticalSection
0x1800175a3  test    rdi, rdi
0x1800175a6  jz      short loc_1800175BD
0x1800175a8  mov     edx, esi; dwMilliseconds
0x1800175aa  mov     rcx, rdi; hHandle
0x1800175ad  call    cs:__imp_WaitForSingleObject
0x1800175b3  mov     rcx, rdi; hObject
0x1800175b6  call    cs:__imp_CloseHandle
0x1800175bc  nop
0x1800175bd  add     rsp, 40h
0x1800175c1  pop     rdi
0x1800175c2  pop     rsi
0x1800175c3  pop     rbx
0x1800175c4  retn
```
