# CcDeletePrivateVolumeCacheMap

- ea: `0x14041d0c4`
- end: `0x14041d3ad`
- name: `CcDeletePrivateVolumeCacheMap`
- size: `745`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x14037b524`
- `0x14041c36c`
- `0x1405bebc0`

## callees

- `0x1402055cc`
- `0x14021b8f0`
- `0x14021d2a0`
- `0x14024c9f0`
- `0x1402a2f90`
- `0x1402fcf10`
- `0x14033a550`
- `0x1403618d0`
- `0x14041d0c4`
- `0x14041d3e4`
- `0x14041d76c`
- `0x1406dd460`
- `0x1406dd5c0`
- `0x140bb19f0`

## string_xrefs

- `0x14041d0d9`: `[%04x:%04x]CcDeletePrivateVolumeCacheMap-BEGIN: PVCM:%p(vid:%2lx)\n`
- `0x14041d133`: `[%04x:%04x]CcDeletePrivateVolumeCacheMap: PVCM:%p(vid:%2lx) Setting ExitEvent\n`
- `0x14041d2c1`: `[%04x:%04x]CcDeletePrivateVolumeCacheMap-END: PVCM:%p(vid:%2lx), PVCMCount:%lu\n`

## pseudocode

```c
void __fastcall CcDeletePrivateVolumeCacheMap(char *P)
{
  __int64 v2; // rsi
  void *v3; // rcx
  _QWORD **v4; // rbx
  _QWORD *v5; // rcx
  void *v6; // rcx
  _QWORD *v7; // rbp
  _QWORD **v8; // r14
  _QWORD *v9; // rbx
  _QWORD *v10; // rax
  _QWORD *v11; // rbx
  _QWORD *v13; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+40h] [rbp-38h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  DbgPrintEx(
    0x7Fu,
    2u,
    "[%04x:%04x]CcDeletePrivateVolumeCacheMap-BEGIN: PVCM:%p(vid:%2lx)\n",
    LODWORD(KeGetCurrentThread()[1].CycleTime),
    KeGetCurrentThread()[1].CurrentRunTime,
    P,
    *((_DWORD *)P + 6));
  v2 = *((_QWORD *)P + 4);
  DbgPrintEx(
    0x7Fu,
    2u,
    "[%04x:%04x]CcDeletePrivateVolumeCacheMap: PVCM:%p(vid:%2lx) Setting ExitEvent\n",
    LODWORD(KeGetCurrentThread()[1].CycleTime),
    KeGetCurrentThread()[1].CurrentRunTime,
    P,
    *((_DWORD *)P + 6));
  KeSetEvent((PRKEVENT)P + 49, 0, 0);
  KeSetEvent((PRKEVENT)P + 50, 0, 0);
  v3 = (void *)*((_QWORD *)P + 153);
  if ( v3 )
  {
    ZwWaitForSingleObject(v3, 0, 0);
    ZwClose(*((HANDLE *)P + 153));
    *((_QWORD *)P + 153) = 0;
  }
  if ( *((_QWORD *)P + 5) )
    CcDecrementVolumeUseCountWithDelete();
  while ( *((_QWORD *)P + 1) != 1 )
    KeDelayExecutionThread(0, 0, &Cc5MicroSeconds);
  CcDereferencePartitionAndPrivateVolumeCacheMap(v2, P);
  if ( P[984] )
  {
    P[984] = 0;
    KeCancelTimer((PKTIMER)(P + 920));
  }
  v4 = (_QWORD **)(P + 1560);
  while ( 1 )
  {
    v5 = *v4;
    if ( *v4 == v4 )
      break;
    if ( (_QWORD **)v5[1] != v4 || (v13 = (_QWORD *)*v5, *(_QWORD **)(*v5 + 8LL) != v5) )
LABEL_28:
      __fastfail(3u);
    *v4 = v13;
    v13[1] = v4;
    ExFreePoolWithTag(v5, 0x71576343u);
  }
  v6 = (void *)*((_QWORD *)P + 134);
  v7 = 0;
  if ( v6 )
  {
    ExFreePoolWithTag(v6, 0x70546343u);
    *((_QWORD *)P + 134) = 0;
  }
  CcForEachNumaNode(CcUnInitializeAsyncReadForNodeHelper, v2, P, 0);
  CcForEachNumaNode(CcUninitializeAsyncLazywriteForNodeHelper, v2, P, 0);
  v8 = (_QWORD **)(P + 48);
  while ( 1 )
  {
    v9 = *v8;
    if ( *v8 == v8 )
      break;
    if ( (_QWORD **)v9[1] != v8 )
      goto LABEL_28;
    v10 = (_QWORD *)*v9;
    if ( *(_QWORD **)(*v9 + 8LL) != v9 )
      goto LABEL_28;
    *v8 = v10;
    v11 = v9 - 4;
    v10[1] = v8;
    CcDeleteNumaNode(v11);
    if ( v7 )
      v11 = v7;
    v7 = v11;
  }
  if ( v7 )
    ExFreePoolWithTag(v7, 0x754E6343u);
  DbgPrintEx(
    0x7Fu,
    2u,
    "[%04x:%04x]CcDeletePrivateVolumeCacheMap-END: PVCM:%p(vid:%2lx), PVCMCount:%lu\n",
    LODWORD(KeGetCurrentThread()[1].CycleTime),
    KeGetCurrentThread()[1].CurrentRunTime,
    P,
    *((_DWORD *)P + 6),
    *(_DWORD *)(v2 + 48) - 1);
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v2 + 768), &LockHandle);
  if ( (*(_DWORD *)(v2 + 48))-- == 1 )
    KeSetEvent((PRKEVENT)(v2 + 56), 0, 0);
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  ExFreePoolWithTag(P, 0x6D566343u);
}

```

## disassembly

```asm
0x14041d0c4  mov     r11, rsp
0x14041d0c7  mov     [r11+10h], rbx
0x14041d0cb  mov     [r11+18h], rbp
0x14041d0cf  push    rsi
0x14041d0d0  push    rdi
0x14041d0d1  push    r14
0x14041d0d3  sub     rsp, 60h
0x14041d0d7  xor     eax, eax
0x14041d0d9  lea     r8, a04x04xCcdelete_2; "[%04x:%04x]CcDeletePrivateVolumeCacheMa"...
0x14041d0e0  xorps   xmm0, xmm0
0x14041d0e3  mov     rdi, rcx
0x14041d0e6  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x14041d0eb  mov     [r11-28h], rax
0x14041d0ef  mov     rdx, gs:188h
0x14041d0f8  mov     r9, gs:188h
0x14041d101  mov     eax, [rcx+18h]
0x14041d104  mov     [rsp+78h+var_48], eax
0x14041d108  mov     eax, [rdx+510h]
0x14041d10e  mov     edx, 2; Level
0x14041d113  mov     r9d, [r9+508h]
0x14041d11a  mov     [r11-50h], rcx
0x14041d11e  mov     [rsp+78h+var_58], eax
0x14041d122  lea     ecx, [rdx+7Dh]; ComponentId
0x14041d125  call    DbgPrintEx
0x14041d12a  mov     rcx, gs:188h
0x14041d133  lea     r8, a04x04xCcdelete_1; "[%04x:%04x]CcDeletePrivateVolumeCacheMa"...
0x14041d13a  mov     r9, gs:188h
0x14041d143  mov     edx, 2; Level
0x14041d148  mov     eax, [rdi+18h]
0x14041d14b  mov     rsi, [rdi+20h]
0x14041d14f  mov     [rsp+78h+var_48], eax
0x14041d153  mov     eax, [rcx+510h]
0x14041d159  lea     ecx, [rdx+7Dh]; ComponentId
0x14041d15c  mov     r9d, [r9+508h]
0x14041d163  mov     [rsp+78h+var_50], rdi
0x14041d168  mov     [rsp+78h+var_58], eax
0x14041d16c  call    DbgPrintEx
0x14041d171  lea     rcx, [rdi+498h]; Event
0x14041d178  xor     r8d, r8d; Wait
0x14041d17b  xor     edx, edx; Increment
0x14041d17d  call    KeSetEvent
0x14041d182  lea     rcx, [rdi+4B0h]; Event
0x14041d189  xor     r8d, r8d; Wait
0x14041d18c  xor     edx, edx; Increment
0x14041d18e  call    KeSetEvent
0x14041d193  mov     rcx, [rdi+4C8h]; Handle
0x14041d19a  test    rcx, rcx
0x14041d19d  jnz     loc_14041D34A
0x14041d1a3  mov     rcx, [rdi+28h]
0x14041d1a7  test    rcx, rcx
0x14041d1aa  jz      short loc_14041D1C3
0x14041d1ac  call    CcDecrementVolumeUseCountWithDelete
0x14041d1b1  jmp     short loc_14041D1C3
0x14041d1b3  lea     r8, Cc5MicroSeconds; Interval
0x14041d1ba  xor     edx, edx; Alertable
0x14041d1bc  xor     ecx, ecx; WaitMode
0x14041d1be  call    KeDelayExecutionThread
0x14041d1c3  cmp     qword ptr [rdi+8], 1
0x14041d1c8  jnz     short loc_14041D1B3
0x14041d1ca  mov     rdx, rdi
0x14041d1cd  mov     rcx, rsi
0x14041d1d0  call    CcDereferencePartitionAndPrivateVolumeCacheMap
0x14041d1d5  cmp     byte ptr [rdi+3D8h], 0
0x14041d1dc  jnz     loc_14041D382
0x14041d1e2  lea     rbx, [rdi+618h]
0x14041d1e9  mov     rcx, [rbx]; P
0x14041d1ec  cmp     rcx, rbx
0x14041d1ef  jnz     loc_14041D31E
0x14041d1f5  mov     rcx, [rdi+430h]; P
0x14041d1fc  xor     ebp, ebp
0x14041d1fe  test    rcx, rcx
0x14041d201  jz      short loc_14041D214
0x14041d203  mov     edx, 70546343h; Tag
0x14041d208  call    ExFreePoolWithTag
0x14041d20d  mov     [rdi+430h], rbp
0x14041d214  xor     r9d, r9d
0x14041d217  lea     rcx, CcUnInitializeAsyncReadForNodeHelper
0x14041d21e  mov     r8, rdi
0x14041d221  mov     rdx, rsi
0x14041d224  call    CcForEachNumaNode
0x14041d229  xor     r9d, r9d
0x14041d22c  lea     rcx, CcUninitializeAsyncLazywriteForNodeHelper
0x14041d233  mov     r8, rdi
0x14041d236  mov     rdx, rsi
0x14041d239  call    CcForEachNumaNode
0x14041d23e  lea     r14, [rdi+30h]
0x14041d242  mov     rbx, [r14]
0x14041d245  cmp     rbx, r14
0x14041d248  jz      short loc_14041D280
0x14041d24a  cmp     [rbx+8], r14
0x14041d24e  jnz     loc_14041D343
0x14041d254  mov     rax, [rbx]
0x14041d257  cmp     [rax+8], rbx
0x14041d25b  jnz     loc_14041D343
0x14041d261  mov     [r14], rax
0x14041d264  add     rbx, 0FFFFFFFFFFFFFFE0h
0x14041d268  mov     rcx, rbx
0x14041d26b  mov     [rax+8], r14
0x14041d26f  call    CcDeleteNumaNode
0x14041d274  test    rbp, rbp
0x14041d277  cmovnz  rbx, rbp
0x14041d27b  mov     rbp, rbx
0x14041d27e  jmp     short loc_14041D242
0x14041d280  test    rbp, rbp
0x14041d283  jnz     loc_14041D370
0x14041d289  mov     r8, gs:188h
0x14041d292  mov     edx, 2; Level
0x14041d297  mov     r9, gs:188h
0x14041d2a0  mov     eax, [rsi+30h]
0x14041d2a3  dec     eax
0x14041d2a5  mov     [rsp+78h+var_40], eax
0x14041d2a9  lea     ecx, [rdx+7Dh]; ComponentId
0x14041d2ac  mov     eax, [rdi+18h]
0x14041d2af  mov     r9d, [r9+508h]
0x14041d2b6  mov     [rsp+78h+var_48], eax
0x14041d2ba  mov     eax, [r8+510h]
0x14041d2c1  lea     r8, a04x04xCcdelete; "[%04x:%04x]CcDeletePrivateVolumeCacheMa"...
0x14041d2c8  mov     [rsp+78h+var_50], rdi
0x14041d2cd  mov     [rsp+78h+var_58], eax
0x14041d2d1  call    DbgPrintEx
0x14041d2d6  lea     rcx, [rsi+300h]; SpinLock
0x14041d2dd  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x14041d2e2  call    KeAcquireInStackQueuedSpinLock
0x14041d2e7  add     dword ptr [rsi+30h], 0FFFFFFFFh
0x14041d2eb  jz      loc_14041D39A
0x14041d2f1  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x14041d2f6  call    KeReleaseInStackQueuedSpinLock
0x14041d2fb  mov     edx, 6D566343h; Tag
0x14041d300  mov     rcx, rdi; P
0x14041d303  call    ExFreePoolWithTag
0x14041d308  lea     r11, [rsp+78h+var_18]
0x14041d30d  mov     rbx, [r11+28h]
0x14041d311  mov     rbp, [r11+30h]
0x14041d315  mov     rsp, r11
0x14041d318  pop     r14
0x14041d31a  pop     rdi
0x14041d31b  pop     rsi
0x14041d31c  retn
0x14041d31e  cmp     [rcx+8], rbx
0x14041d322  jnz     short loc_14041D343
0x14041d324  mov     rax, [rcx]
0x14041d327  cmp     [rax+8], rcx
0x14041d32b  jnz     short loc_14041D343
0x14041d32d  mov     [rbx], rax
0x14041d330  mov     edx, 71576343h; Tag
0x14041d335  mov     [rax+8], rbx
0x14041d339  call    ExFreePoolWithTag
0x14041d33e  jmp     loc_14041D1E9
0x14041d343  mov     ecx, 3
0x14041d348  int     29h; Win8: RtlFailFast(ecx)
0x14041d34a  xor     r8d, r8d; Timeout
0x14041d34d  xor     edx, edx; Alertable
0x14041d34f  call    ZwWaitForSingleObject
0x14041d354  mov     rcx, [rdi+4C8h]; Handle
0x14041d35b  call    ZwClose
0x14041d360  mov     qword ptr [rdi+4C8h], 0
0x14041d36b  jmp     loc_14041D1A3
0x14041d370  mov     edx, 754E6343h; Tag
0x14041d375  mov     rcx, rbp; P
0x14041d378  call    ExFreePoolWithTag
0x14041d37d  jmp     loc_14041D289
0x14041d382  lea     rcx, [rdi+398h]; PKTIMER
0x14041d389  mov     byte ptr [rdi+3D8h], 0
0x14041d390  call    KeCancelTimer
0x14041d395  jmp     loc_14041D1E2
0x14041d39a  lea     rcx, [rsi+38h]; Event
0x14041d39e  xor     r8d, r8d; Wait
0x14041d3a1  xor     edx, edx; Increment
0x14041d3a3  call    KeSetEvent
0x14041d3a8  jmp     loc_14041D2F1
```
