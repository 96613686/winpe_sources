# FatDeleteVcb

- ea: `0x140048424`
- end: `0x14004867a`
- name: `FatDeleteVcb`
- size: `598`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140006350`

## callees

- `0x14000c680`
- `0x140023a5c`
- `0x140048184`
- `0x140048424`
- `0x140048740`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x1400485d3`
- `ntoskrnl!KeCancelTimer` at `0x1400485d3`
- `ntoskrnl!KeRemoveQueueDpc` at `0x1400485e6`
- `ntoskrnl!KeRemoveQueueDpc` at `0x1400485e6`
- `ntoskrnl!ExDeleteResourceLite` at `0x140048550`
- `ntoskrnl!ExDeleteResourceLite` at `0x140048563`
- `ntoskrnl!ExDeleteResourceLite` at `0x140048550`
- `ntoskrnl!ExDeleteResourceLite` at `0x140048563`
- `ntoskrnl!FsRtlNotifyUninitializeSync` at `0x14004853d`
- `ntoskrnl!FsRtlNotifyUninitializeSync` at `0x14004853d`
- `ntoskrnl!FsRtlDeleteTunnelCache` at `0x14004860e`
- `ntoskrnl!FsRtlDeleteTunnelCache` at `0x14004860e`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140048588`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14004859b`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140048588`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14004859b`
- `ntoskrnl!KeBugCheckEx` at `0x140048666`
- `ntoskrnl!KeBugCheckEx` at `0x140048666`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004844d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004846e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048488`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400485b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400485fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004844d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004846e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048488`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400485b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400485fb`
- `ntoskrnl!ObfDereferenceObject` at `0x140048621`
- `ntoskrnl!ObfDereferenceObject` at `0x140048621`

## pseudocode

```c
void *__fastcall FatDeleteVcb(__int64 a1, __int64 a2)
{
  void *v3; // rcx
  void *v4; // rcx
  __int64 v5; // rcx
  _QWORD *v6; // rdx
  __int64 v7; // rax
  __int64 v8; // r10
  __int64 v9; // rcx
  __int64 v10; // r10
  __int64 v11; // rcx
  void *v12; // rcx
  __int64 NextFcbBottomUp; // [rsp+40h] [rbp+8h] BYREF

  if ( *(_QWORD *)(a1 + 56) == a2 )
    *(_QWORD *)(a1 + 56) = 0;
  v3 = *(void **)(a2 + 1128);
  if ( v3 )
    ExFreePoolWithTag(v3, 0);
  if ( (*(_DWORD *)(a2 + 200) & 0x40000) != 0 )
    ExFreePoolWithTag(*(PVOID *)(a2 + 192), 0);
  v4 = *(void **)(a2 + 168);
  if ( v4 )
  {
    ExFreePoolWithTag(v4, 0);
    *(_QWORD *)(a2 + 168) = 0;
  }
  v5 = *(_QWORD *)(a2 + 120);
  if ( *(_QWORD *)(v5 + 8) != a2 + 120 || (v6 = *(_QWORD **)(a2 + 128), *v6 != a2 + 120) )
    __fastfail(3u);
  *v6 = v5;
  *(_QWORD *)(v5 + 8) = v6;
  if ( *(_DWORD *)(a2 + 240) || *(_DWORD *)(a2 + 272) )
    KeBugCheckEx(0x23u, 0x1C0346u, *(unsigned int *)(a2 + 240), *(unsigned int *)(a2 + 272), 0);
  v7 = *(_QWORD *)(a2 + 784);
  if ( v7 )
  {
    *(_DWORD *)(v7 + 232) = 0;
    FatDeleteFcb(v5, a2 + 784);
  }
  v8 = *(_QWORD *)(a2 + 208);
  if ( v8 )
  {
    while ( 1 )
    {
      NextFcbBottomUp = FatGetNextFcbBottomUp(v5, 0, v8);
      if ( NextFcbBottomUp == v10 )
        break;
      FatDeleteFcb(v9, &NextFcbBottomUp);
      v8 = *(_QWORD *)(a2 + 208);
    }
    FatDeleteFcb(v9, a2 + 208);
  }
  FsRtlNotifyUninitializeSync((PNOTIFY_SYNC *)(a2 + 816));
  ExDeleteResourceLite((PERESOURCE)(a2 + 520));
  ExDeleteResourceLite((PERESOURCE)(a2 + 624));
  if ( *(_QWORD *)(a2 + 456) )
    FatTearDownAllocationSupport(v11, a2);
  FsRtlUninitializeLargeMcb((PLARGE_MCB)(a2 + 384));
  FsRtlUninitializeLargeMcb((PLARGE_MCB)(a2 + 416));
  v12 = *(void **)(a2 + 336);
  if ( v12 )
  {
    ExFreePoolWithTag(v12, 0);
    *(_QWORD *)(a2 + 336) = 0;
  }
  KeCancelTimer((PKTIMER)(a2 + 952));
  KeRemoveQueueDpc((PRKDPC)(a2 + 888));
  ExFreePoolWithTag(*(PVOID *)(a2 + 1024), 0);
  FsRtlDeleteTunnelCache((TUNNEL *)(a2 + 1032));
  ObfDereferenceObject(*(PVOID *)(a2 + 136));
  return memset((void *)a2, 0, 0x548u);
}

```

## disassembly

```asm
0x140048424  mov     [rsp+arg_8], rbx
0x140048429  push    rdi
0x14004842a  sub     rsp, 30h
0x14004842e  mov     rbx, rdx
0x140048431  cmp     [rcx+38h], rdx
0x140048435  jnz     short loc_14004843F
0x140048437  mov     qword ptr [rcx+38h], 0
0x14004843f  mov     rcx, [rdx+468h]; P
0x140048446  test    rcx, rcx
0x140048449  jz      short loc_140048459
0x14004844b  xor     edx, edx; Tag
0x14004844d  call    cs:__imp_ExFreePoolWithTag
0x140048454  nop     dword ptr [rax+rax+00h]
0x140048459  mov     eax, [rbx+0C8h]
0x14004845f  bt      eax, 12h
0x140048463  jnb     short loc_14004847A
0x140048465  mov     rcx, [rbx+0C0h]; P
0x14004846c  xor     edx, edx; Tag
0x14004846e  call    cs:__imp_ExFreePoolWithTag
0x140048475  nop     dword ptr [rax+rax+00h]
0x14004847a  mov     rcx, [rbx+0A8h]; P
0x140048481  test    rcx, rcx
0x140048484  jz      short loc_14004849F
0x140048486  xor     edx, edx; Tag
0x140048488  call    cs:__imp_ExFreePoolWithTag
0x14004848f  nop     dword ptr [rax+rax+00h]
0x140048494  mov     qword ptr [rbx+0A8h], 0
0x14004849f  lea     rax, [rbx+78h]
0x1400484a3  mov     rcx, [rax]
0x1400484a6  cmp     [rcx+8], rax
0x1400484aa  jnz     loc_140048673
0x1400484b0  mov     rdx, [rax+8]
0x1400484b4  cmp     [rdx], rax
0x1400484b7  jnz     loc_140048673
0x1400484bd  mov     [rdx], rcx
0x1400484c0  mov     [rcx+8], rdx
0x1400484c4  mov     eax, [rbx+0F0h]
0x1400484ca  test    eax, eax
0x1400484cc  jnz     loc_140048649
0x1400484d2  cmp     [rbx+110h], eax
0x1400484d8  jnz     loc_140048649
0x1400484de  lea     rdx, [rbx+310h]
0x1400484e5  mov     rax, [rdx]
0x1400484e8  test    rax, rax
0x1400484eb  jz      short loc_1400484FC
0x1400484ed  mov     dword ptr [rax+0E8h], 0
0x1400484f7  call    FatDeleteFcb
0x1400484fc  lea     rdi, [rbx+0D0h]
0x140048503  mov     r10, [rdi]
0x140048506  test    r10, r10
0x140048509  jz      short loc_140048536
0x14004850b  jmp     short loc_14004851A
0x14004850d  lea     rdx, [rsp+38h+arg_0]
0x140048512  call    FatDeleteFcb
0x140048517  mov     r10, [rdi]
0x14004851a  mov     r8, r10
0x14004851d  xor     edx, edx
0x14004851f  call    FatGetNextFcbBottomUp
0x140048524  mov     [rsp+38h+arg_0], rax
0x140048529  cmp     rax, r10
0x14004852c  jnz     short loc_14004850D
0x14004852e  mov     rdx, rdi
0x140048531  call    FatDeleteFcb
0x140048536  lea     rcx, [rbx+330h]; NotifySync
0x14004853d  call    cs:__imp_FsRtlNotifyUninitializeSync
0x140048544  nop     dword ptr [rax+rax+00h]
0x140048549  lea     rcx, [rbx+208h]; Resource
0x140048550  call    cs:__imp_ExDeleteResourceLite
0x140048557  nop     dword ptr [rax+rax+00h]
0x14004855c  lea     rcx, [rbx+270h]; Resource
0x140048563  call    cs:__imp_ExDeleteResourceLite
0x14004856a  nop     dword ptr [rax+rax+00h]
0x14004856f  cmp     qword ptr [rbx+1C8h], 0
0x140048577  jz      short loc_140048581
0x140048579  mov     rdx, rbx
0x14004857c  call    FatTearDownAllocationSupport
0x140048581  lea     rcx, [rbx+180h]; Mcb
0x140048588  call    cs:__imp_FsRtlUninitializeLargeMcb
0x14004858f  nop     dword ptr [rax+rax+00h]
0x140048594  lea     rcx, [rbx+1A0h]; Mcb
0x14004859b  call    cs:__imp_FsRtlUninitializeLargeMcb
0x1400485a2  nop     dword ptr [rax+rax+00h]
0x1400485a7  mov     rcx, [rbx+150h]; P
0x1400485ae  test    rcx, rcx
0x1400485b1  jz      short loc_1400485CC
0x1400485b3  xor     edx, edx; Tag
0x1400485b5  call    cs:__imp_ExFreePoolWithTag
0x1400485bc  nop     dword ptr [rax+rax+00h]
0x1400485c1  mov     qword ptr [rbx+150h], 0
0x1400485cc  lea     rcx, [rbx+3B8h]; PKTIMER
0x1400485d3  call    cs:__imp_KeCancelTimer
0x1400485da  nop     dword ptr [rax+rax+00h]
0x1400485df  lea     rcx, [rbx+378h]; Dpc
0x1400485e6  call    cs:__imp_KeRemoveQueueDpc
0x1400485ed  nop     dword ptr [rax+rax+00h]
0x1400485f2  mov     rcx, [rbx+400h]; P
0x1400485f9  xor     edx, edx; Tag
0x1400485fb  call    cs:__imp_ExFreePoolWithTag
0x140048602  nop     dword ptr [rax+rax+00h]
0x140048607  lea     rcx, [rbx+408h]; Cache
0x14004860e  call    cs:__imp_FsRtlDeleteTunnelCache
0x140048615  nop     dword ptr [rax+rax+00h]
0x14004861a  mov     rcx, [rbx+88h]; Object
0x140048621  call    cs:__imp_ObfDereferenceObject
0x140048628  nop     dword ptr [rax+rax+00h]
0x14004862d  xor     edx, edx; Val
0x14004862f  mov     r8d, 548h; Size
0x140048635  mov     rcx, rbx; void *
0x140048638  call    memset
0x14004863d  mov     rbx, [rsp+38h+arg_8]
0x140048642  add     rsp, 30h
0x140048646  pop     rdi
0x140048647  retn
0x140048649  mov     r9d, [rbx+110h]; BugCheckParameter3
0x140048650  mov     r8, rax; BugCheckParameter2
0x140048653  mov     edx, 1C0346h; BugCheckParameter1
0x140048658  mov     [rsp+38h+BugCheckParameter4], 0; BugCheckParameter4
0x140048661  mov     ecx, 23h ; '#'; BugCheckCode
0x140048666  call    cs:__imp_KeBugCheckEx
0x140048673  mov     ecx, 3
0x140048678  int     29h; Win8: RtlFailFast(ecx)
```
