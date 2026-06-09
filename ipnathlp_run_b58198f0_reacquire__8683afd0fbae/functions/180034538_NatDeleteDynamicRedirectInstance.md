# NatDeleteDynamicRedirectInstance

- ea: `0x180034538`
- end: `0x180034774`
- name: `NatDeleteDynamicRedirectInstance`
- size: `572`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180034010`
- `0x180034328`
- `0x18005b880`

## callees

- `0x180034538`
- `0x18004fcf8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003457b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034733`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003457b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034733`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003458f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003458f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034761`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003461b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003461b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800346cd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800346cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800346df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034706`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800346df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034706`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180034567`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180034567`
- `ntdll!NtDeviceIoControlFile` at `0x1800346b2`
- `ntdll!NtDeviceIoControlFile` at `0x1800346b2`
- `ntdll!RtlNtStatusToDosError` at `0x1800346f1`
- `ntdll!RtlNtStatusToDosError` at `0x1800346f1`

## pseudocode

```c
BOOL __fastcall NatDeleteDynamicRedirectInstance(LPCRITICAL_SECTION lpCriticalSection, _QWORD *a2)
{
  void *v4; // rcx
  void *v5; // rbx
  HANDLE ProcessHeap; // rax
  __int16 LockCount; // bx
  int DebugInfo_high; // r14d
  __int16 OwningThread; // r15
  LONG RecursionCount; // r12d
  __int16 SpinCount; // r13
  HANDLE EventW; // rax
  void *v13; // rsi
  int Status; // ebx
  void *v15; // rcx
  __int64 v16; // rax
  _QWORD *v17; // rcx
  HANDLE v18; // rax
  int LockSemaphore_high; // [rsp+50h] [rbp-39h]
  HANDLE FileHandle; // [rsp+58h] [rbp-31h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-29h] BYREF
  __int128 InputBuffer; // [rsp+70h] [rbp-19h] BYREF
  __int128 v24; // [rsp+80h] [rbp-9h]
  __int128 v25; // [rsp+90h] [rbp+7h]
  int v26; // [rsp+A0h] [rbp+17h]
  char LockSemaphore; // [rsp+F8h] [rbp+6Fh]
  __int16 DebugInfo; // [rsp+100h] [rbp+77h]
  int SpinCount_high; // [rsp+108h] [rbp+7Fh]

  v4 = (void *)a2[4];
  if ( v4 )
  {
    if ( UnregisterWait(v4) )
    {
      v5 = (void *)a2[5];
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v5);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&lpCriticalSection[1], 0xFFFFFFFF) == 1 )
        NatCleanupDynamicRedirect(lpCriticalSection);
    }
    a2[4] = 0;
    LockCount = lpCriticalSection[3].LockCount;
    DebugInfo_high = HIDWORD(lpCriticalSection[3].DebugInfo);
    OwningThread = (__int16)lpCriticalSection[3].OwningThread;
    RecursionCount = lpCriticalSection[3].RecursionCount;
    SpinCount = lpCriticalSection[2].SpinCount;
    LockSemaphore_high = HIDWORD(lpCriticalSection[2].LockSemaphore);
    DebugInfo = (__int16)lpCriticalSection[3].DebugInfo;
    SpinCount_high = HIDWORD(lpCriticalSection[2].SpinCount);
    LockSemaphore = (char)lpCriticalSection[2].LockSemaphore;
    FileHandle = *(HANDLE *)&lpCriticalSection[1].LockCount;
    v26 = 0;
    InputBuffer = 0;
    v24 = 0;
    v25 = 0;
    IoStatusBlock = 0;
    EventW = CreateEventW(0, 0, 0, 0);
    v13 = EventW;
    if ( EventW )
    {
      LOBYTE(v24) = LockSemaphore;
      HIDWORD(v24) = SpinCount_high;
      LOWORD(v25) = DebugInfo;
      DWORD1(v24) = LockSemaphore_high;
      LODWORD(InputBuffer) = 0;
      *((_QWORD *)&InputBuffer + 1) = 0;
      WORD4(v24) = SpinCount;
      HIDWORD(v25) = RecursionCount;
      LOWORD(v26) = OwningThread;
      DWORD1(v25) = DebugInfo_high;
      WORD4(v25) = LockCount;
      Status = NtDeviceIoControlFile(FileHandle, EventW, 0, 0, &IoStatusBlock, 0x128034u, &InputBuffer, 0x38u, 0, 0);
      if ( Status == 259 )
      {
        WaitForSingleObject(v13, 0xFFFFFFFF);
        Status = IoStatusBlock.Status;
      }
      CloseHandle(v13);
      if ( Status < 0 )
        RtlNtStatusToDosError(Status);
    }
  }
  v15 = (void *)a2[3];
  if ( v15 )
  {
    CloseHandle(v15);
    a2[3] = 0;
  }
  v16 = *a2;
  if ( *(_QWORD **)(*a2 + 8LL) != a2 || (v17 = (_QWORD *)a2[1], (_QWORD *)*v17 != a2) )
    __fastfail(3u);
  *v17 = v16;
  *(_QWORD *)(v16 + 8) = v17;
  v18 = GetProcessHeap();
  return HeapFree(v18, 0, a2);
}

```

## disassembly

```asm
0x180034538  mov     [rsp-8+arg_0], rbx
0x18003453d  push    rbp
0x18003453e  push    rsi
0x18003453f  push    rdi
0x180034540  push    r12
0x180034542  push    r13
0x180034544  push    r14
0x180034546  push    r15
0x180034548  lea     rbp, [rsp-27h]
0x18003454d  sub     rsp, 0B0h
0x180034554  mov     rsi, rcx
0x180034557  mov     rdi, rdx
0x18003455a  mov     rcx, [rdx+20h]; WaitHandle
0x18003455e  test    rcx, rcx
0x180034561  jz      loc_1800346FD
0x180034567  call    cs:__imp_UnregisterWait
0x18003456e  nop     dword ptr [rax+rax+00h]
0x180034573  test    eax, eax
0x180034575  jz      short loc_1800345B0
0x180034577  mov     rbx, [rdi+28h]
0x18003457b  call    cs:__imp_GetProcessHeap
0x180034582  nop     dword ptr [rax+rax+00h]
0x180034587  mov     r8, rbx; lpMem
0x18003458a  xor     edx, edx; dwFlags
0x18003458c  mov     rcx, rax; hHeap
0x18003458f  call    cs:__imp_HeapFree
0x180034596  nop     dword ptr [rax+rax+00h]
0x18003459b  or      eax, 0FFFFFFFFh
0x18003459e  lock xadd [rsi+28h], eax
0x1800345a3  cmp     eax, 1
0x1800345a6  jnz     short loc_1800345B0
0x1800345a8  mov     rcx, rsi; lpCriticalSection
0x1800345ab  call    NatCleanupDynamicRedirect
0x1800345b0  mov     qword ptr [rdi+20h], 0
0x1800345b8  xorps   xmm0, xmm0
0x1800345bb  mov     eax, [rsi+6Ch]
0x1800345be  xor     r9d, r9d; lpName
0x1800345c1  movzx   ebx, word ptr [rsi+80h]
0x1800345c8  xor     r8d, r8d; bInitialState
0x1800345cb  mov     r14d, [rsi+7Ch]
0x1800345cf  xor     edx, edx; bManualReset
0x1800345d1  movzx   r15d, word ptr [rsi+88h]
0x1800345d9  xor     ecx, ecx; lpEventAttributes
0x1800345db  mov     r12d, [rsi+84h]
0x1800345e2  movzx   r13d, word ptr [rsi+70h]
0x1800345e7  mov     [rbp+57h+var_90], eax
0x1800345ea  movzx   eax, word ptr [rsi+78h]
0x1800345ee  mov     [rbp+57h+arg_10], ax
0x1800345f2  mov     eax, [rsi+74h]
0x1800345f5  mov     [rbp+57h+arg_18], eax
0x1800345f8  mov     al, [rsi+68h]
0x1800345fb  mov     [rbp+57h+arg_8], al
0x1800345fe  mov     rax, [rsi+30h]
0x180034602  mov     [rbp+57h+FileHandle], rax
0x180034606  xor     eax, eax
0x180034608  mov     [rbp+57h+var_40], eax
0x18003460b  movups  [rbp+57h+var_70], xmm0
0x18003460f  movups  [rbp+57h+var_60], xmm0
0x180034613  movups  [rbp+57h+var_50], xmm0
0x180034617  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x18003461b  call    cs:__imp_CreateEventW
0x180034622  nop     dword ptr [rax+rax+00h]
0x180034627  mov     rsi, rax
0x18003462a  test    rax, rax
0x18003462d  jz      loc_1800346FD
0x180034633  mov     al, [rbp+57h+arg_8]
0x180034636  xor     r9d, r9d; ApcContext
0x180034639  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x18003463d  xor     r8d, r8d; ApcRoutine
0x180034640  mov     byte ptr [rbp+57h+var_60], al
0x180034643  mov     rdx, rsi; Event
0x180034646  mov     eax, [rbp+57h+arg_18]
0x180034649  mov     dword ptr [rbp+57h+var_60+0Ch], eax
0x18003464c  movzx   eax, [rbp+57h+arg_10]
0x180034650  mov     [rsp+0E0h+OutputBufferLength], 0; OutputBufferLength
0x180034658  mov     word ptr [rbp+57h+var_50], ax
0x18003465c  mov     eax, [rbp+57h+var_90]
0x18003465f  mov     [rsp+0E0h+OutputBuffer], 0; OutputBuffer
0x180034668  mov     dword ptr [rbp+57h+var_60+4], eax
0x18003466b  lea     rax, [rbp+57h+var_70]
0x18003466f  mov     [rsp+0E0h+InputBufferLength], 38h ; '8'; InputBufferLength
0x180034677  mov     [rsp+0E0h+InputBuffer], rax; InputBuffer
0x18003467c  lea     rax, [rbp+57h+var_80]
0x180034680  mov     [rsp+0E0h+IoControlCode], 128034h; IoControlCode
0x180034688  mov     [rsp+0E0h+IoStatusBlock], rax; IoStatusBlock
0x18003468d  mov     dword ptr [rbp+57h+var_70], 0
0x180034694  mov     qword ptr [rbp+57h+var_70+8], 0
0x18003469c  mov     word ptr [rbp+57h+var_60+8], r13w
0x1800346a1  mov     dword ptr [rbp+57h+var_50+0Ch], r12d
0x1800346a5  mov     word ptr [rbp+57h+var_40], r15w
0x1800346aa  mov     dword ptr [rbp+57h+var_50+4], r14d
0x1800346ae  mov     word ptr [rbp+57h+var_50+8], bx
0x1800346b2  call    cs:__imp_NtDeviceIoControlFile
0x1800346b9  nop     dword ptr [rax+rax+00h]
0x1800346be  mov     ebx, eax
0x1800346c0  cmp     eax, 103h
0x1800346c5  jnz     short loc_1800346DC
0x1800346c7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800346ca  mov     rcx, rsi; hHandle
0x1800346cd  call    cs:__imp_WaitForSingleObject
0x1800346d4  nop     dword ptr [rax+rax+00h]
0x1800346d9  mov     ebx, dword ptr [rbp+57h+var_80]
0x1800346dc  mov     rcx, rsi; hObject
0x1800346df  call    cs:__imp_CloseHandle
0x1800346e6  nop     dword ptr [rax+rax+00h]
0x1800346eb  test    ebx, ebx
0x1800346ed  jns     short loc_1800346FD
0x1800346ef  mov     ecx, ebx; Status
0x1800346f1  call    cs:__imp_RtlNtStatusToDosError
0x1800346f8  nop     dword ptr [rax+rax+00h]
0x1800346fd  mov     rcx, [rdi+18h]; hObject
0x180034701  test    rcx, rcx
0x180034704  jz      short loc_18003471A
0x180034706  call    cs:__imp_CloseHandle
0x18003470d  nop     dword ptr [rax+rax+00h]
0x180034712  mov     qword ptr [rdi+18h], 0
0x18003471a  mov     rax, [rdi]
0x18003471d  cmp     [rax+8], rdi
0x180034721  jnz     short loc_18003476D
0x180034723  mov     rcx, [rdi+8]
0x180034727  cmp     [rcx], rdi
0x18003472a  jnz     short loc_18003476D
0x18003472c  mov     [rcx], rax
0x18003472f  mov     [rax+8], rcx
0x180034733  call    cs:__imp_GetProcessHeap
0x18003473a  nop     dword ptr [rax+rax+00h]
0x18003473f  mov     r8, rdi
0x180034742  xor     edx, edx
0x180034744  mov     rcx, rax
0x180034747  mov     rbx, [rsp+0E0h+arg_0]
0x18003474f  add     rsp, 0B0h
0x180034756  pop     r15
0x180034758  pop     r14
0x18003475a  pop     r13
0x18003475c  pop     r12
0x18003475e  pop     rdi
0x18003475f  pop     rsi
0x180034760  pop     rbp
0x180034761  jmp     cs:__imp_HeapFree
0x18003476d  mov     ecx, 3
0x180034772  int     29h; Win8: RtlFailFast(ecx)
```
