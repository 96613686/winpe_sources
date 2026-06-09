# CDDPDEV::InvalidateInternalBitmaps(_WORKERTHREAD_COMMAND)

- ea: `0x14002e61c`
- end: `0x14002e77c`
- name: `?InvalidateInternalBitmaps@CDDPDEV@@QEAAXW4_WORKERTHREAD_COMMAND@@@Z`
- size: `352`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140022c28`
- `0x14002d088`

## callees

- `0x140001b14`
- `0x140001cb4`
- `0x140002470`
- `0x140011220`
- `0x14002e61c`
- `0x140030bd0`
- `0x1400372d0`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14002e6f8`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14002e743`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14002e6f8`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14002e743`
- `watchdog!WdLogSingleEntry1` at `0x14002e638`
- `watchdog!WdLogSingleEntry1` at `0x14002e638`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14002e64f`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14002e64f`

## pseudocode

```c
void __fastcall CDDPDEV::InvalidateInternalBitmaps(__int64 a1, int a2)
{
  _QWORD *v4; // rax
  int v5; // r8d
  CddBitmapStagingVidMem *v6; // rcx
  int v7; // r8d
  _QWORD *i; // rbx
  CHwCommandBuffer *v9; // rcx
  CHwCommandBuffer *v10; // rcx
  unsigned int v11; // edx
  __int64 v12; // [rsp+20h] [rbp-18h] BYREF
  int v13; // [rsp+28h] [rbp-10h]

  WdLogSingleEntry1(4, a1);
  WdLogGlobalForLineNumber = 1933;
  v4 = (_QWORD *)WdLogNewEntry5_WdEvent();
  v4[3] = gCddImageInfo;
  v4[4] = (unsigned int)dword_14003E570;
  v4[5] = 215857758;
  WdLogGlobalForLineNumber = 1933;
  CStagingPoolBase::InvalidateStagingPool((PVOID *)(a1 + 5504), a2);
  CStagingPoolBase::InvalidateStagingPool((PVOID *)(a1 + 6320), a2);
  v6 = *(CddBitmapStagingVidMem **)(a1 + 5496);
  if ( v6 )
    CddBitmapStagingVidMem::InvalidateDeviceAllocations(v6);
  *(_DWORD *)(a1 + 2744) &= ~0x100u;
  CGuardMutexEx::CGuardMutexEx((CGuardMutexEx *)&v12, *(struct CDDMUTEX **)(a1 + 7256), v5);
  for ( i = *(_QWORD **)(a1 + 7240); i != (_QWORD *)(a1 + 7240); i = (_QWORD *)*i )
    (*(void (__fastcall **)(_QWORD *))(*(i - 18) + 72LL))(i - 18);
  if ( v13 )
    ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v12);
  CGuardMutexEx::CGuardMutexEx((CGuardMutexEx *)&v12, *(struct CDDMUTEX **)(a1 + 2896), v7);
  v9 = *(CHwCommandBuffer **)(a1 + 12696);
  if ( v9 )
    CHwCommandBuffer::ResetCommandBuffer(v9);
  v10 = *(CHwCommandBuffer **)(a1 + 12704);
  if ( v10 )
    CHwCommandBuffer::ResetCommandBuffer(v10);
  if ( v13 )
    ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v12);
  v11 = *(_DWORD *)(a1 + 7224);
  if ( v11 )
  {
    CDDPDEV::DestroyAllocation((CDDPDEV *)a1, v11);
    *(_DWORD *)(a1 + 7224) = 0;
  }
}

```

## disassembly

```asm
0x14002e61c  mov     [rsp+arg_0], rbx
0x14002e621  mov     [rsp+arg_8], rsi
0x14002e626  push    rdi
0x14002e627  sub     rsp, 30h
0x14002e62b  mov     ebx, edx
0x14002e62d  mov     rdi, rcx
0x14002e630  mov     rdx, rcx
0x14002e633  mov     ecx, 4
0x14002e638  call    cs:__imp_WdLogSingleEntry1
0x14002e63f  nop     dword ptr [rax+rax+00h]
0x14002e644  mov     esi, 78Dh
0x14002e649  mov     cs:WdLogGlobalForLineNumber, esi
0x14002e64f  call    cs:__imp_WdLogNewEntry5_WdEvent
0x14002e656  nop     dword ptr [rax+rax+00h]
0x14002e65b  mov     r8, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002e662  lea     rcx, [rdi+1580h]
0x14002e669  mov     edx, ebx
0x14002e66b  mov     [rax+18h], r8
0x14002e66f  mov     r8d, cs:dword_14003E570
0x14002e676  mov     [rax+20h], r8
0x14002e67a  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14002e682  mov     cs:WdLogGlobalForLineNumber, esi
0x14002e688  call    ?InvalidateStagingPool@CStagingPoolBase@@QEAAXW4_WORKERTHREAD_COMMAND@@@Z; CStagingPoolBase::InvalidateStagingPool(_WORKERTHREAD_COMMAND)
0x14002e68d  lea     rcx, [rdi+18B0h]
0x14002e694  mov     edx, ebx
0x14002e696  call    ?InvalidateStagingPool@CStagingPoolBase@@QEAAXW4_WORKERTHREAD_COMMAND@@@Z; CStagingPoolBase::InvalidateStagingPool(_WORKERTHREAD_COMMAND)
0x14002e69b  mov     rcx, [rdi+1578h]; this
0x14002e6a2  test    rcx, rcx
0x14002e6a5  jz      short loc_14002E6AC
0x14002e6a7  call    ?InvalidateDeviceAllocations@CddBitmapStagingVidMem@@QEAAXXZ; CddBitmapStagingVidMem::InvalidateDeviceAllocations(void)
0x14002e6ac  btr     dword ptr [rdi+0AB8h], 8
0x14002e6b4  lea     rcx, [rsp+38h+var_18]; this
0x14002e6b9  mov     rdx, [rdi+1C58h]; struct CDDMUTEX *
0x14002e6c0  call    ??0CGuardMutexEx@@QEAA@PEAVCDDMUTEX@@H@Z; CGuardMutexEx::CGuardMutexEx(CDDMUTEX *,int)
0x14002e6c5  lea     rsi, [rdi+1C48h]
0x14002e6cc  mov     rbx, [rsi]
0x14002e6cf  jmp     short loc_14002E6E7
0x14002e6d1  lea     rcx, [rbx-90h]
0x14002e6d8  mov     rax, [rcx]
0x14002e6db  mov     rax, [rax+48h]
0x14002e6df  call    _guard_dispatch_icall
0x14002e6e4  mov     rbx, [rbx]
0x14002e6e7  cmp     rbx, rsi
0x14002e6ea  jnz     short loc_14002E6D1
0x14002e6ec  cmp     [rsp+38h+var_10], 0
0x14002e6f1  jz      short loc_14002E704
0x14002e6f3  mov     rcx, [rsp+38h+var_18]
0x14002e6f8  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x14002e6ff  nop     dword ptr [rax+rax+00h]
0x14002e704  mov     rdx, [rdi+0B50h]; struct CDDMUTEX *
0x14002e70b  lea     rcx, [rsp+38h+var_18]; this
0x14002e710  call    ??0CGuardMutexEx@@QEAA@PEAVCDDMUTEX@@H@Z; CGuardMutexEx::CGuardMutexEx(CDDMUTEX *,int)
0x14002e715  mov     rcx, [rdi+3198h]; this
0x14002e71c  test    rcx, rcx
0x14002e71f  jz      short loc_14002E726
0x14002e721  call    ?ResetCommandBuffer@CHwCommandBuffer@@QEAAXXZ; CHwCommandBuffer::ResetCommandBuffer(void)
0x14002e726  mov     rcx, [rdi+31A0h]; this
0x14002e72d  test    rcx, rcx
0x14002e730  jz      short loc_14002E737
0x14002e732  call    ?ResetCommandBuffer@CHwCommandBuffer@@QEAAXXZ; CHwCommandBuffer::ResetCommandBuffer(void)
0x14002e737  cmp     [rsp+38h+var_10], 0
0x14002e73c  jz      short loc_14002E74F
0x14002e73e  mov     rcx, [rsp+38h+var_18]
0x14002e743  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x14002e74a  nop     dword ptr [rax+rax+00h]
0x14002e74f  mov     edx, [rdi+1C38h]; unsigned int
0x14002e755  test    edx, edx
0x14002e757  jz      short loc_14002E76B
0x14002e759  mov     rcx, rdi; this
0x14002e75c  call    ?DestroyAllocation@CDDPDEV@@QEAAJI@Z; CDDPDEV::DestroyAllocation(uint)
0x14002e761  mov     dword ptr [rdi+1C38h], 0
0x14002e76b  mov     rbx, [rsp+38h+arg_0]
0x14002e770  mov     rsi, [rsp+38h+arg_8]
0x14002e775  add     rsp, 30h
0x14002e779  pop     rdi
0x14002e77a  retn
```
