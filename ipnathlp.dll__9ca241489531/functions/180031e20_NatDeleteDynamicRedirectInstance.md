# NatDeleteDynamicRedirectInstance

- ea: `0x180031e20`
- end: `0x18003201b`
- name: `NatDeleteDynamicRedirectInstance`
- size: `507`
- prototype: `BOOL __fastcall(LPCRITICAL_SECTION lpCriticalSection, _QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180031970`
- `0x180031c50`
- `0x1800573a0`

## callees

- `0x180031e20`
- `0x18004bff8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031e5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031fe5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031e5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031fe5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031e6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031e6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003200d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180031ef1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180031ef1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180031f97`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180031f97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031fa3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031fbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031fa3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031fbe`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180031e4f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180031e4f`
- `ntdll!NtDeviceIoControlFile` at `0x180031f82`
- `ntdll!NtDeviceIoControlFile` at `0x180031f82`
- `ntdll!RtlNtStatusToDosError` at `0x180031faf`
- `ntdll!RtlNtStatusToDosError` at `0x180031faf`

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
0x180031e20  mov     [rsp-8+arg_0], rbx
0x180031e25  push    rbp
0x180031e26  push    rsi
0x180031e27  push    rdi
0x180031e28  push    r12
0x180031e2a  push    r13
0x180031e2c  push    r14
0x180031e2e  push    r15
0x180031e30  lea     rbp, [rsp-27h]
0x180031e35  sub     rsp, 0B0h
0x180031e3c  mov     rsi, rcx
0x180031e3f  mov     rdi, rdx
0x180031e42  mov     rcx, [rdx+20h]; WaitHandle
0x180031e46  test    rcx, rcx
0x180031e49  jz      loc_180031FB5
0x180031e4f  call    cs:__imp_UnregisterWait
0x180031e55  test    eax, eax
0x180031e57  jz      short loc_180031E86
0x180031e59  mov     rbx, [rdi+28h]
0x180031e5d  call    cs:__imp_GetProcessHeap
0x180031e63  mov     r8, rbx; lpMem
0x180031e66  xor     edx, edx; dwFlags
0x180031e68  mov     rcx, rax; hHeap
0x180031e6b  call    cs:__imp_HeapFree
0x180031e71  or      eax, 0FFFFFFFFh
0x180031e74  lock xadd [rsi+28h], eax
0x180031e79  cmp     eax, 1
0x180031e7c  jnz     short loc_180031E86
0x180031e7e  mov     rcx, rsi; lpCriticalSection
0x180031e81  call    NatCleanupDynamicRedirect
0x180031e86  mov     qword ptr [rdi+20h], 0
0x180031e8e  xorps   xmm0, xmm0
0x180031e91  mov     eax, [rsi+6Ch]
0x180031e94  xor     r9d, r9d; lpName
0x180031e97  movzx   ebx, word ptr [rsi+80h]
0x180031e9e  xor     r8d, r8d; bInitialState
0x180031ea1  mov     r14d, [rsi+7Ch]
0x180031ea5  xor     edx, edx; bManualReset
0x180031ea7  movzx   r15d, word ptr [rsi+88h]
0x180031eaf  xor     ecx, ecx; lpEventAttributes
0x180031eb1  mov     r12d, [rsi+84h]
0x180031eb8  movzx   r13d, word ptr [rsi+70h]
0x180031ebd  mov     [rbp+57h+var_90], eax
0x180031ec0  movzx   eax, word ptr [rsi+78h]
0x180031ec4  mov     [rbp+57h+arg_10], ax
0x180031ec8  mov     eax, [rsi+74h]
0x180031ecb  mov     [rbp+57h+arg_18], eax
0x180031ece  mov     al, [rsi+68h]
0x180031ed1  mov     [rbp+57h+arg_8], al
0x180031ed4  mov     rax, [rsi+30h]
0x180031ed8  mov     [rbp+57h+FileHandle], rax
0x180031edc  xor     eax, eax
0x180031ede  mov     [rbp+57h+var_40], eax
0x180031ee1  movups  [rbp+57h+var_70], xmm0
0x180031ee5  movups  [rbp+57h+var_60], xmm0
0x180031ee9  movups  [rbp+57h+var_50], xmm0
0x180031eed  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x180031ef1  call    cs:__imp_CreateEventW
0x180031ef7  mov     rsi, rax
0x180031efa  test    rax, rax
0x180031efd  jz      loc_180031FB5
0x180031f03  mov     al, [rbp+57h+arg_8]
0x180031f06  xor     r9d, r9d; ApcContext
0x180031f09  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x180031f0d  xor     r8d, r8d; ApcRoutine
0x180031f10  mov     byte ptr [rbp+57h+var_60], al
0x180031f13  mov     rdx, rsi; Event
0x180031f16  mov     eax, [rbp+57h+arg_18]
0x180031f19  mov     dword ptr [rbp+57h+var_60+0Ch], eax
0x180031f1c  movzx   eax, [rbp+57h+arg_10]
0x180031f20  mov     [rsp+0E0h+OutputBufferLength], 0; OutputBufferLength
0x180031f28  mov     word ptr [rbp+57h+var_50], ax
0x180031f2c  mov     eax, [rbp+57h+var_90]
0x180031f2f  mov     [rsp+0E0h+OutputBuffer], 0; OutputBuffer
0x180031f38  mov     dword ptr [rbp+57h+var_60+4], eax
0x180031f3b  lea     rax, [rbp+57h+var_70]
0x180031f3f  mov     [rsp+0E0h+InputBufferLength], 38h ; '8'; InputBufferLength
0x180031f47  mov     [rsp+0E0h+InputBuffer], rax; InputBuffer
0x180031f4c  lea     rax, [rbp+57h+var_80]
0x180031f50  mov     [rsp+0E0h+IoControlCode], 128034h; IoControlCode
0x180031f58  mov     [rsp+0E0h+IoStatusBlock], rax; IoStatusBlock
0x180031f5d  mov     dword ptr [rbp+57h+var_70], 0
0x180031f64  mov     qword ptr [rbp+57h+var_70+8], 0
0x180031f6c  mov     word ptr [rbp+57h+var_60+8], r13w
0x180031f71  mov     dword ptr [rbp+57h+var_50+0Ch], r12d
0x180031f75  mov     word ptr [rbp+57h+var_40], r15w
0x180031f7a  mov     dword ptr [rbp+57h+var_50+4], r14d
0x180031f7e  mov     word ptr [rbp+57h+var_50+8], bx
0x180031f82  call    cs:__imp_NtDeviceIoControlFile
0x180031f88  mov     ebx, eax
0x180031f8a  cmp     eax, 103h
0x180031f8f  jnz     short loc_180031FA0
0x180031f91  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180031f94  mov     rcx, rsi; hHandle
0x180031f97  call    cs:__imp_WaitForSingleObject
0x180031f9d  mov     ebx, dword ptr [rbp+57h+var_80]
0x180031fa0  mov     rcx, rsi; hObject
0x180031fa3  call    cs:__imp_CloseHandle
0x180031fa9  test    ebx, ebx
0x180031fab  jns     short loc_180031FB5
0x180031fad  mov     ecx, ebx; Status
0x180031faf  call    cs:__imp_RtlNtStatusToDosError
0x180031fb5  mov     rcx, [rdi+18h]; hObject
0x180031fb9  test    rcx, rcx
0x180031fbc  jz      short loc_180031FCC
0x180031fbe  call    cs:__imp_CloseHandle
0x180031fc4  mov     qword ptr [rdi+18h], 0
0x180031fcc  mov     rax, [rdi]
0x180031fcf  cmp     [rax+8], rdi
0x180031fd3  jnz     short loc_180032014
0x180031fd5  mov     rcx, [rdi+8]
0x180031fd9  cmp     [rcx], rdi
0x180031fdc  jnz     short loc_180032014
0x180031fde  mov     [rcx], rax
0x180031fe1  mov     [rax+8], rcx
0x180031fe5  call    cs:__imp_GetProcessHeap
0x180031feb  mov     r8, rdi
0x180031fee  xor     edx, edx
0x180031ff0  mov     rcx, rax
0x180031ff3  mov     rbx, [rsp+0E0h+arg_0]
0x180031ffb  add     rsp, 0B0h
0x180032002  pop     r15
0x180032004  pop     r14
0x180032006  pop     r13
0x180032008  pop     r12
0x18003200a  pop     rdi
0x18003200b  pop     rsi
0x18003200c  pop     rbp
0x18003200d  jmp     cs:__imp_HeapFree
0x180032014  mov     ecx, 3
0x180032019  int     29h; Win8: RtlFailFast(ecx)
```
