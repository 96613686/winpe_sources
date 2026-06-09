# LuafvRunScavenger

- ea: `0x14000160c`
- end: `0x140001728`
- name: `LuafvRunScavenger`
- size: `284`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400051a8`
- `0x140019f90`
- `0x14001c420`

## callees

- `0x14000160c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000167a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000167a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400016f2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400016f2`
- `ntoskrnl!ExQueueWorkItem` at `0x1400016dc`
- `ntoskrnl!ExQueueWorkItem` at `0x1400016dc`

## pseudocode

```c
void LuafvRunScavenger()
{
  char v0; // si
  __int64 v1; // rbx
  char v2; // di
  char v3; // bp
  KIRQL v4; // r14

  v0 = 0;
  v1 = MEMORY[0xFFFFF78000000014];
  if ( MEMORY[0xFFFFF78000000014] >= NextFileTableTime || dword_14000F2FC > dword_14000F300 )
  {
    v2 = 1;
  }
  else
  {
    v2 = 0;
    if ( dword_14000F2F8 > 0 )
    {
      v2 = 1;
      v0 = 1;
    }
  }
  if ( MEMORY[0xFFFFF78000000014] >= NextUserTime )
  {
    v3 = 1;
  }
  else
  {
    v3 = 0;
    if ( !v2 )
      return;
  }
  v4 = KeAcquireSpinLockRaiseToDpc(&ScavengerSpinLock);
  if ( ScavengerInitialized )
  {
    if ( v2 )
    {
      RunFileTableAlgorithm = 1;
      InactiveJournalsOnly = v0;
      if ( !v0 )
        NextFileTableTime = v1 + LuafvFileTableScavengeInterval;
    }
    if ( v3 )
    {
      RunUserAlgorithm = 1;
      NextUserTime += v1 + LuafvUserScavengeInterval;
    }
    if ( !ScavengerRunning )
    {
      ScavengerRunning = 1;
      ExQueueWorkItem(&ScavengerWorkItem, DelayedWorkQueue);
    }
  }
  KeReleaseSpinLock(&ScavengerSpinLock, v4);
}

```

## disassembly

```asm
0x14000160c  push    rbx
0x14000160e  push    rbp
0x14000160f  push    rsi
0x140001610  push    rdi
0x140001611  push    r14
0x140001613  sub     rsp, 20h
0x140001617  mov     rbx, 0FFFFF78000000014h
0x140001621  xor     sil, sil
0x140001624  mov     rbx, [rbx]
0x140001627  cmp     rbx, cs:NextFileTableTime
0x14000162e  jge     short loc_14000166B
0x140001630  mov     eax, cs:dword_14000F300
0x140001636  cmp     cs:dword_14000F2FC, eax
0x14000163c  jg      short loc_14000166B
0x14000163e  xor     dil, dil
0x140001641  cmp     cs:dword_14000F2F8, 0
0x140001648  jg      loc_140001703
0x14000164e  cmp     rbx, cs:NextUserTime
0x140001655  jge     short loc_140001670
0x140001657  xor     bpl, bpl
0x14000165a  test    dil, dil
0x14000165d  jnz     short loc_140001673
0x14000165f  add     rsp, 20h
0x140001663  pop     r14
0x140001665  pop     rdi
0x140001666  pop     rsi
0x140001667  pop     rbp
0x140001668  pop     rbx
0x140001669  retn
0x14000166b  mov     dil, 1
0x14000166e  jmp     short loc_14000164E
0x140001670  mov     bpl, 1
0x140001673  lea     rcx, ScavengerSpinLock; SpinLock
0x14000167a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001681  nop     dword ptr [rax+rax+00h]
0x140001686  cmp     cs:ScavengerInitialized, 0
0x14000168d  mov     r14b, al
0x140001690  jz      short loc_1400016E8
0x140001692  test    dil, dil
0x140001695  jz      short loc_1400016BB
0x140001697  mov     cs:RunFileTableAlgorithm, 1
0x14000169e  mov     cs:InactiveJournalsOnly, sil
0x1400016a5  test    sil, sil
0x1400016a8  jnz     short loc_1400016BB
0x1400016aa  mov     rdx, cs:LuafvFileTableScavengeInterval
0x1400016b1  add     rdx, rbx
0x1400016b4  mov     cs:NextFileTableTime, rdx
0x1400016bb  test    bpl, bpl
0x1400016be  jnz     short loc_14000170E
0x1400016c0  cmp     cs:ScavengerRunning, 0
0x1400016c7  jnz     short loc_1400016E8
0x1400016c9  mov     edx, 1; QueueType
0x1400016ce  mov     cs:ScavengerRunning, 1
0x1400016d5  lea     rcx, ScavengerWorkItem; WorkItem
0x1400016dc  call    cs:__imp_ExQueueWorkItem
0x1400016e3  nop     dword ptr [rax+rax+00h]
0x1400016e8  mov     dl, r14b; NewIrql
0x1400016eb  lea     rcx, ScavengerSpinLock; SpinLock
0x1400016f2  call    cs:__imp_KeReleaseSpinLock
0x1400016f9  nop     dword ptr [rax+rax+00h]
0x1400016fe  jmp     loc_14000165F
0x140001703  mov     dil, 1
0x140001706  mov     sil, dil
0x140001709  jmp     loc_14000164E
0x14000170e  mov     r8, cs:LuafvUserScavengeInterval
0x140001715  add     r8, rbx
0x140001718  mov     cs:RunUserAlgorithm, 1
0x14000171f  add     cs:NextUserTime, r8
0x140001726  jmp     short loc_1400016C0
```
