# UlpSetRequestQueueLengthLimit

- ea: `0x1400cff00`
- end: `0x1400d0036`
- name: `UlpSetRequestQueueLengthLimit`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400cd5e0`

## callees

- `0x1400cff00`
- `0x1401c3f58`
- `0x1401c5890`
- `0x1401d9f54`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400cffb8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400cffb8`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400cfff3`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400cfff3`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400cff89`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400cff89`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400cffd4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400cffd4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cffff`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cffff`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400cff76`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400cff76`

## pseudocode

```c
void __fastcall UlpSetRequestQueueLengthLimit(__int64 a1, unsigned int a2, int a3)
{
  unsigned int v5; // r14d
  unsigned __int16 i; // bp
  __int64 v7; // rbx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+40h] [rbp-48h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qD(1032, 134, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, a1, a2);
  if ( (BYTE2(xmmword_1401A2CA0) & 0x40) != 0 )
    WPP_SF_qZLH(a1, a2, a3, a1, a1 + 160, a2);
  v5 = a2 / (unsigned __int16)UlNumberOfLanes;
  KeEnterCriticalRegion();
  ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(a1 + 280));
  for ( i = 0; i < (unsigned __int16)UlNumberOfLanes; ++i )
  {
    v7 = *(_QWORD *)(*(_QWORD *)(a1 + 288) + 8LL * i);
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)v7, &LockHandle);
    *(_DWORD *)(v7 + 104) = a2;
    *(_DWORD *)(v7 + 108) = v5;
    *(_DWORD *)(v7 + 112) = v5;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(a1 + 280));
  KeLeaveCriticalRegion();
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_(1032, 136, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
}

```

## disassembly

```asm
0x1400cff00  push    rbx
0x1400cff02  push    rbp
0x1400cff03  push    rsi
0x1400cff04  push    rdi
0x1400cff05  push    r14
0x1400cff07  sub     rsp, 60h
0x1400cff0b  xorps   xmm0, xmm0
0x1400cff0e  xor     eax, eax
0x1400cff10  movups  xmmword ptr [rsp+88h+LockHandle.LockQueue.Next], xmm0
0x1400cff15  mov     qword ptr [rsp+88h+LockHandle.OldIrql], rax
0x1400cff1a  mov     esi, edx
0x1400cff1c  mov     rdi, rcx
0x1400cff1f  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400cff26  jz      short loc_1400CFF45
0x1400cff28  mov     edx, 86h
0x1400cff2d  mov     dword ptr [rsp+88h+var_68], esi
0x1400cff31  mov     ecx, 408h
0x1400cff36  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400cff3d  mov     r9, rdi
0x1400cff40  call    WPP_SF_qD
0x1400cff45  test    byte ptr cs:xmmword_1401A2CA0+2, 40h
0x1400cff4c  jz      short loc_1400CFF66
0x1400cff4e  lea     rax, [rdi+0A0h]
0x1400cff55  mov     [rsp+88h+var_60], esi
0x1400cff59  mov     r9, rdi
0x1400cff5c  mov     [rsp+88h+var_68], rax
0x1400cff61  call    WPP_SF_qZLH
0x1400cff66  movzx   ecx, cs:UlNumberOfLanes
0x1400cff6d  xor     edx, edx
0x1400cff6f  mov     eax, esi
0x1400cff71  div     ecx
0x1400cff73  mov     r14d, eax
0x1400cff76  call    cs:__imp_KeEnterCriticalRegion
0x1400cff7d  nop     dword ptr [rax+rax+00h]
0x1400cff82  mov     rcx, [rdi+118h]
0x1400cff89  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1400cff90  nop     dword ptr [rax+rax+00h]
0x1400cff95  xor     ecx, ecx
0x1400cff97  xor     ebp, ebp
0x1400cff99  cmp     cx, cs:UlNumberOfLanes
0x1400cffa0  jnb     short loc_1400CFFEC
0x1400cffa2  mov     rax, [rdi+120h]
0x1400cffa9  lea     rdx, [rsp+88h+LockHandle]; LockHandle
0x1400cffae  movzx   ecx, bp
0x1400cffb1  mov     rbx, [rax+rcx*8]
0x1400cffb5  mov     rcx, rbx; SpinLock
0x1400cffb8  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400cffbf  nop     dword ptr [rax+rax+00h]
0x1400cffc4  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x1400cffc9  mov     [rbx+68h], esi
0x1400cffcc  mov     [rbx+6Ch], r14d
0x1400cffd0  mov     [rbx+70h], r14d
0x1400cffd4  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400cffdb  nop     dword ptr [rax+rax+00h]
0x1400cffe0  inc     bp
0x1400cffe3  cmp     bp, cs:UlNumberOfLanes
0x1400cffea  jb      short loc_1400CFFA2
0x1400cffec  mov     rcx, [rdi+118h]
0x1400cfff3  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400cfffa  nop     dword ptr [rax+rax+00h]
0x1400cffff  call    cs:__imp_KeLeaveCriticalRegion
0x1400d0006  nop     dword ptr [rax+rax+00h]
0x1400d000b  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400d0012  jz      short loc_1400D002A
0x1400d0014  mov     edx, 88h
0x1400d0019  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400d0020  mov     ecx, 408h
0x1400d0025  call    WPP_SF_
0x1400d002a  add     rsp, 60h
0x1400d002e  pop     r14
0x1400d0030  pop     rdi
0x1400d0031  pop     rsi
0x1400d0032  pop     rbp
0x1400d0033  pop     rbx
0x1400d0034  retn
```
