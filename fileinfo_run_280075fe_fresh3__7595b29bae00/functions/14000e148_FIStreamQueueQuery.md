# FIStreamQueueQuery

- ea: `0x14000e148`
- end: `0x14000e369`
- name: `FIStreamQueueQuery`
- size: `545`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140002a80`
- `0x140012bd8`

## callees

- `0x140001c00`
- `0x140001da0`
- `0x140001f20`
- `0x1400033f0`
- `0x14000e148`
- `0x140014580`
- `0x140016910`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14000e233`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000e233`
- `ntoskrnl!ObfReferenceObject` at `0x14000e2a1`
- `ntoskrnl!ObfReferenceObject` at `0x14000e2a1`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000e342`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000e342`
- `ntoskrnl!ObfDereferenceObject` at `0x14000e321`
- `ntoskrnl!ObfDereferenceObject` at `0x14000e321`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000e30d`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000e30d`
- `FLTMGR!FltQueueGenericWorkItem` at `0x14000e2c6`
- `FLTMGR!FltQueueGenericWorkItem` at `0x14000e2c6`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14000e253`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14000e253`

## pseudocode

```c
__int64 __fastcall FIStreamQueueQuery(__int64 a1, __int64 a2)
{
  NTSTATUS v4; // ebx
  __int64 v5; // rsi
  char v6; // r13
  char v7; // bl
  struct _FLT_GENERIC_WORKITEM *GenericWorkItem; // r12
  void *v9; // r14
  union _LARGE_INTEGER Timeout; // [rsp+70h] [rbp+18h] BYREF

  Timeout.QuadPart = 0;
  if ( dword_1400099F8 )
    return (unsigned int)-1073741079;
  v5 = a2 + 40;
  if ( !(unsigned int)FIStreamSafeToQuery(a2, *(_QWORD *)(a1 + 16)) )
  {
    FILockExclusiveAcquire(v5);
    FIStreamVolatileBitFieldBitSet(a2, 1, 1);
    FILockExclusiveRelease(v5);
    return (unsigned int)-1073741637;
  }
  v6 = 0;
  if ( Count != 0x7FFFFFFF )
  {
    FIStreamQueryWorker(0, *(PVOID *)(a1 + 8), *(PVOID *)(a1 + 16));
    FILockSharedAcquire(v5);
    v7 = ~*(_BYTE *)(a2 + 56);
    FILockExclusiveRelease(v5);
    if ( (v7 & 1) != 0 )
    {
      ++qword_140009A30;
      return 0;
    }
    ++qword_140009A38;
    Timeout.QuadPart = 0;
    if ( KeWaitForSingleObject(&Semaphore, Executive, 0, 0, &Timeout) == 258 )
      return (unsigned int)-1073741523;
    v6 = 1;
  }
  GenericWorkItem = FltAllocateGenericWorkItem();
  if ( GenericWorkItem )
  {
    FILockExclusiveAcquire(v5);
    if ( (*(_DWORD *)(a2 + 56) & 3) == 1 )
    {
      FIStreamVolatileBitFieldBitSet(a2, 1, 1);
      FILockExclusiveRelease(v5);
      v9 = *(void **)(a1 + 16);
      ObfReferenceObject(v9);
      v4 = FltQueueGenericWorkItem(GenericWorkItem, *(PVOID *)(a1 + 8), FIStreamQueryWorker, DelayedWorkQueue, v9);
      if ( v4 >= 0 )
      {
        ++qword_140009A40;
        return 0;
      }
      FILockExclusiveAcquire(v5);
      FIStreamVolatileBitFieldBitSet(a2, 1, 0);
    }
    else
    {
      v9 = 0;
      v4 = 0;
    }
    FILockExclusiveRelease(v5);
    FltFreeGenericWorkItem(GenericWorkItem);
    if ( v9 )
      ObfDereferenceObject(v9);
  }
  else
  {
    v4 = -1073741670;
  }
  if ( v6 )
    KeReleaseSemaphore(&Semaphore, 0, 1, 0);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000e148  mov     [rsp+arg_0], rbx
0x14000e14d  mov     [rsp+arg_8], rbp
0x14000e152  push    rsi
0x14000e153  push    r12
0x14000e155  push    r13
0x14000e157  push    r14
0x14000e159  push    r15
0x14000e15b  sub     rsp, 30h
0x14000e15f  mov     eax, cs:dword_1400099F8
0x14000e165  mov     rbp, rdx
0x14000e168  mov     qword ptr [rsp+58h+arg_10], 0
0x14000e171  mov     r15, rcx
0x14000e174  test    eax, eax
0x14000e176  jz      short loc_14000E182
0x14000e178  mov     ebx, 0C00002E9h
0x14000e17d  jmp     loc_14000E34E
0x14000e182  lea     rsi, [rdx+28h]
0x14000e186  mov     rdx, [rcx+10h]
0x14000e18a  mov     rcx, rbp
0x14000e18d  call    FIStreamSafeToQuery
0x14000e192  test    eax, eax
0x14000e194  jnz     short loc_14000E1C0
0x14000e196  mov     rcx, rsi
0x14000e199  call    FILockExclusiveAcquire
0x14000e19e  mov     edx, 1
0x14000e1a3  mov     rcx, rbp
0x14000e1a6  mov     r8d, edx
0x14000e1a9  call    FIStreamVolatileBitFieldBitSet
0x14000e1ae  mov     rcx, rsi
0x14000e1b1  call    FILockExclusiveRelease
0x14000e1b6  mov     ebx, 0C00000BBh
0x14000e1bb  jmp     loc_14000E34E
0x14000e1c0  xor     r13b, r13b
0x14000e1c3  cmp     cs:Count, 7FFFFFFFh
0x14000e1cd  jz      loc_14000E253
0x14000e1d3  mov     r8, [r15+10h]; Context
0x14000e1d7  xor     ecx, ecx; FltWorkItem
0x14000e1d9  mov     rdx, [r15+8]; FltObject
0x14000e1dd  call    FIStreamQueryWorker
0x14000e1e2  mov     rcx, rsi
0x14000e1e5  call    FILockSharedAcquire
0x14000e1ea  mov     bl, [rbp+38h]
0x14000e1ed  mov     rcx, rsi
0x14000e1f0  not     bl
0x14000e1f2  call    FILockExclusiveRelease
0x14000e1f7  test    bl, 1
0x14000e1fa  jz      short loc_14000E20A
0x14000e1fc  inc     cs:qword_140009A30
0x14000e203  xor     ebx, ebx
0x14000e205  jmp     loc_14000E34E
0x14000e20a  inc     cs:qword_140009A38
0x14000e211  lea     rax, [rsp+58h+arg_10]
0x14000e216  xor     r9d, r9d; Alertable
0x14000e219  mov     [rsp+58h+Timeout], rax; Timeout
0x14000e21e  xor     r8d, r8d; WaitMode
0x14000e221  mov     qword ptr [rsp+58h+arg_10], 0
0x14000e22a  xor     edx, edx; WaitReason
0x14000e22c  lea     rcx, Semaphore; Object
0x14000e233  call    cs:__imp_KeWaitForSingleObject
0x14000e23a  nop     dword ptr [rax+rax+00h]
0x14000e23f  cmp     eax, 102h
0x14000e244  jnz     short loc_14000E250
0x14000e246  mov     ebx, 0C000012Dh
0x14000e24b  jmp     loc_14000E34E
0x14000e250  mov     r13b, 1
0x14000e253  call    cs:__imp_FltAllocateGenericWorkItem
0x14000e25a  nop     dword ptr [rax+rax+00h]
0x14000e25f  mov     r12, rax
0x14000e262  test    rax, rax
0x14000e265  jnz     short loc_14000E271
0x14000e267  mov     ebx, 0C000009Ah
0x14000e26c  jmp     loc_14000E32D
0x14000e271  mov     rcx, rsi
0x14000e274  call    FILockExclusiveAcquire
0x14000e279  mov     eax, [rbp+38h]
0x14000e27c  and     al, 3
0x14000e27e  cmp     al, 1
0x14000e280  jnz     short loc_14000E2FD
0x14000e282  mov     edx, 1
0x14000e287  mov     rcx, rbp
0x14000e28a  mov     r8d, edx
0x14000e28d  call    FIStreamVolatileBitFieldBitSet
0x14000e292  mov     rcx, rsi
0x14000e295  call    FILockExclusiveRelease
0x14000e29a  mov     r14, [r15+10h]
0x14000e29e  mov     rcx, r14; Object
0x14000e2a1  call    cs:__imp_ObfReferenceObject
0x14000e2a8  nop     dword ptr [rax+rax+00h]
0x14000e2ad  mov     rdx, [r15+8]; FltObject
0x14000e2b1  lea     r8, FIStreamQueryWorker; WorkerRoutine
0x14000e2b8  mov     r9d, 1; QueueType
0x14000e2be  mov     [rsp+58h+Timeout], r14; Context
0x14000e2c3  mov     rcx, r12; FltWorkItem
0x14000e2c6  call    cs:__imp_FltQueueGenericWorkItem
0x14000e2cd  nop     dword ptr [rax+rax+00h]
0x14000e2d2  mov     ebx, eax
0x14000e2d4  test    eax, eax
0x14000e2d6  jns     short loc_14000E2F1
0x14000e2d8  mov     rcx, rsi
0x14000e2db  call    FILockExclusiveAcquire
0x14000e2e0  xor     r8d, r8d
0x14000e2e3  mov     rcx, rbp
0x14000e2e6  lea     edx, [r8+1]
0x14000e2ea  call    FIStreamVolatileBitFieldBitSet
0x14000e2ef  jmp     short loc_14000E302
0x14000e2f1  inc     cs:qword_140009A40
0x14000e2f8  jmp     loc_14000E203
0x14000e2fd  xor     r14d, r14d
0x14000e300  xor     ebx, ebx
0x14000e302  mov     rcx, rsi
0x14000e305  call    FILockExclusiveRelease
0x14000e30a  mov     rcx, r12; FltWorkItem
0x14000e30d  call    cs:__imp_FltFreeGenericWorkItem
0x14000e314  nop     dword ptr [rax+rax+00h]
0x14000e319  test    r14, r14
0x14000e31c  jz      short loc_14000E32D
0x14000e31e  mov     rcx, r14; Object
0x14000e321  call    cs:__imp_ObfDereferenceObject
0x14000e328  nop     dword ptr [rax+rax+00h]
0x14000e32d  test    r13b, r13b
0x14000e330  jz      short loc_14000E34E
0x14000e332  xor     r9d, r9d; Wait
0x14000e335  lea     rcx, Semaphore; Semaphore
0x14000e33c  xor     edx, edx; Increment
0x14000e33e  lea     r8d, [r9+1]; Adjustment
0x14000e342  call    cs:__imp_KeReleaseSemaphore
0x14000e349  nop     dword ptr [rax+rax+00h]
0x14000e34e  mov     rbp, [rsp+58h+arg_8]
0x14000e353  mov     eax, ebx
0x14000e355  mov     rbx, [rsp+58h+arg_0]
0x14000e35a  add     rsp, 30h
0x14000e35e  pop     r15
0x14000e360  pop     r14
0x14000e362  pop     r13
0x14000e364  pop     r12
0x14000e366  pop     rsi
0x14000e367  retn
```
