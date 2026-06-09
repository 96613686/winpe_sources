# CdDismountVcb

- ea: `0x140002630`
- end: `0x140002876`
- name: `CdDismountVcb`
- size: `582`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400024e0`
- `0x1400142d8`

## callees

- `0x140002630`
- `0x14000bcf8`
- `0x14000c374`
- `0x140018a3c`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x14000265a`
- `ntoskrnl!ExAcquireFastMutex` at `0x140002724`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000265a`
- `ntoskrnl!ExAcquireFastMutex` at `0x140002724`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400026fb`
- `ntoskrnl!ExReleaseFastMutex` at `0x140002826`
- `ntoskrnl!ExReleaseFastMutex` at `0x140002859`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400026fb`
- `ntoskrnl!ExReleaseFastMutex` at `0x140002826`
- `ntoskrnl!ExReleaseFastMutex` at `0x140002859`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002688`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002688`
- `ntoskrnl!IoAcquireVpbSpinLock` at `0x140002749`
- `ntoskrnl!IoAcquireVpbSpinLock` at `0x140002749`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x1400027c9`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x140002810`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x140002843`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x1400027c9`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x140002810`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x140002843`

## pseudocode

```c
char __fastcall CdDismountVcb(__int64 a1, __int64 a2)
{
  struct _FAST_MUTEX *v2; // rsi
  char v5; // di
  void *v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rbp
  struct _KTHREAD *CurrentThread; // rax
  _DWORD *v12; // rcx
  char v13; // dl
  __int64 v14; // rcx
  KIRQL Irql; // [rsp+68h] [rbp+10h] BYREF

  v2 = (struct _FAST_MUTEX *)(a2 + 336);
  Irql = 0;
  v5 = 1;
  ExAcquireFastMutex((PFAST_MUTEX)(a2 + 336));
  v6 = *(void **)(a2 + 112);
  *(_QWORD *)(a2 + 392) = KeGetCurrentThread();
  *(_DWORD *)(a2 + 52) = 4;
  if ( v6 )
  {
    ExFreePoolWithTag(v6, 0);
    *(_QWORD *)(a2 + 112) = 0;
    *(_QWORD *)(a2 + 120) = 0;
  }
  v7 = *(_QWORD *)(a2 + 80);
  if ( v7 )
  {
    --*(_DWORD *)(v7 + 164);
    --*(_DWORD *)(*(_QWORD *)(a2 + 80) + 168LL);
  }
  v8 = *(_QWORD *)(a2 + 88);
  if ( v8 )
  {
    --*(_DWORD *)(v8 + 164);
    --*(_DWORD *)(*(_QWORD *)(a2 + 88) + 168LL);
  }
  v9 = *(_QWORD *)(a2 + 72);
  if ( v9 )
  {
    --*(_DWORD *)(v9 + 164);
    --*(_DWORD *)(*(_QWORD *)(a2 + 72) + 168LL);
  }
  *(_QWORD *)(a2 + 392) = 0;
  ExReleaseFastMutex(v2);
  CdPurgeVolume(a1, a2, 1);
  CdFspClose(a2);
  v10 = *(_QWORD *)(a2 + 8);
  ExAcquireFastMutex(v2);
  CurrentThread = KeGetCurrentThread();
  --*(_DWORD *)(a2 + 60);
  *(_QWORD *)(a2 + 392) = CurrentThread;
  IoAcquireVpbSpinLock(&Irql);
  v12 = (_DWORD *)(v10 + 28);
  if ( *(_DWORD *)(a2 + 60) || (v13 = 1, *v12 != 1) )
    v13 = 0;
  if ( *(_QWORD *)(*(_QWORD *)(v10 + 16) + 56LL) == v10 )
  {
    if ( !v13 )
    {
      **(_WORD **)(a2 + 560) = 10;
      *(_WORD *)(*(_QWORD *)(a2 + 560) + 2LL) = 96;
      *(_QWORD *)(*(_QWORD *)(a2 + 560) + 16LL) = *(_QWORD *)(v10 + 16);
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 560) + 16LL) + 56LL) = *(_QWORD *)(a2 + 560);
      *(_WORD *)(*(_QWORD *)(a2 + 560) + 4LL) = *(_WORD *)(v10 + 4) & 8;
      IoReleaseVpbSpinLock(Irql);
      *(_QWORD *)(a2 + 560) = 0;
LABEL_20:
      *(_QWORD *)(a2 + 392) = 0;
      ExReleaseFastMutex(v2);
      return v5;
    }
    --*v12;
    *(_QWORD *)(v10 + 8) = 0;
    *(_WORD *)(*(_QWORD *)(a2 + 8) + 4LL) &= ~1u;
    *(_WORD *)(*(_QWORD *)(a2 + 8) + 4LL) &= ~2u;
    *(_QWORD *)(a2 + 8) = 0;
  }
  else
  {
    if ( !v13 )
    {
      IoReleaseVpbSpinLock(Irql);
      goto LABEL_20;
    }
    --*v12;
  }
  IoReleaseVpbSpinLock(Irql);
  *(_QWORD *)(a2 + 392) = 0;
  ExReleaseFastMutex(v2);
  CdDeleteVcb(v14, a2);
  return 0;
}

```

## disassembly

```asm
0x140002630  push    rbx
0x140002632  push    rbp
0x140002633  push    rsi
0x140002634  push    rdi
0x140002635  push    r14
0x140002637  push    r15
0x140002639  sub     rsp, 28h
0x14000263d  lea     rsi, [rdx+150h]
0x140002644  mov     rbp, rcx
0x140002647  xor     r14d, r14d
0x14000264a  mov     rcx, rsi; FastMutex
0x14000264d  mov     rbx, rdx
0x140002650  mov     [rsp+58h+Irql], r14b
0x140002655  mov     edi, 1
0x14000265a  call    cs:__imp_ExAcquireFastMutex
0x140002661  nop     dword ptr [rax+rax+00h]
0x140002666  mov     rax, gs:188h
0x14000266f  mov     rcx, [rbx+70h]; P
0x140002673  mov     [rbx+188h], rax
0x14000267a  mov     dword ptr [rbx+34h], 4
0x140002681  test    rcx, rcx
0x140002684  jz      short loc_14000269C
0x140002686  xor     edx, edx; Tag
0x140002688  call    cs:__imp_ExFreePoolWithTag
0x14000268f  nop     dword ptr [rax+rax+00h]
0x140002694  mov     [rbx+70h], r14
0x140002698  mov     [rbx+78h], r14
0x14000269c  mov     rax, [rbx+50h]
0x1400026a0  or      r15d, 0FFFFFFFFh
0x1400026a4  test    rax, rax
0x1400026a7  jz      short loc_1400026BB
0x1400026a9  add     [rax+0A4h], r15d
0x1400026b0  mov     rax, [rbx+50h]
0x1400026b4  add     [rax+0A8h], r15d
0x1400026bb  mov     rax, [rbx+58h]
0x1400026bf  test    rax, rax
0x1400026c2  jz      short loc_1400026D6
0x1400026c4  add     [rax+0A4h], r15d
0x1400026cb  mov     rax, [rbx+58h]
0x1400026cf  add     [rax+0A8h], r15d
0x1400026d6  mov     rax, [rbx+48h]
0x1400026da  test    rax, rax
0x1400026dd  jz      short loc_1400026F1
0x1400026df  add     [rax+0A4h], r15d
0x1400026e6  mov     rax, [rbx+48h]
0x1400026ea  add     [rax+0A8h], r15d
0x1400026f1  mov     rcx, rsi; FastMutex
0x1400026f4  mov     [rbx+188h], r14
0x1400026fb  call    cs:__imp_ExReleaseFastMutex
0x140002702  nop     dword ptr [rax+rax+00h]
0x140002707  mov     r8b, dil
0x14000270a  mov     rdx, rbx
0x14000270d  mov     rcx, rbp
0x140002710  call    CdPurgeVolume
0x140002715  mov     rcx, rbx
0x140002718  call    CdFspClose
0x14000271d  mov     rbp, [rbx+8]
0x140002721  mov     rcx, rsi; FastMutex
0x140002724  call    cs:__imp_ExAcquireFastMutex
0x14000272b  nop     dword ptr [rax+rax+00h]
0x140002730  mov     rax, gs:188h
0x140002739  lea     rcx, [rsp+58h+Irql]; Irql
0x14000273e  add     [rbx+3Ch], r15d
0x140002742  mov     [rbx+188h], rax
0x140002749  call    cs:__imp_IoAcquireVpbSpinLock
0x140002750  nop     dword ptr [rax+rax+00h]
0x140002755  lea     rcx, [rbp+1Ch]
0x140002759  cmp     [rbx+3Ch], r14d
0x14000275d  jnz     short loc_140002766
0x14000275f  mov     dl, dil
0x140002762  cmp     [rcx], edi
0x140002764  jz      short loc_140002769
0x140002766  mov     dl, r14b
0x140002769  mov     rax, [rbp+10h]
0x14000276d  cmp     [rax+38h], rbp
0x140002771  jnz     loc_140002805
0x140002777  test    dl, dl
0x140002779  jnz     short loc_1400027DE
0x14000277b  mov     rax, [rbx+230h]
0x140002782  mov     word ptr [rax], 0Ah
0x140002787  mov     rax, [rbx+230h]
0x14000278e  mov     word ptr [rax+2], 60h ; '`'
0x140002794  mov     rdx, [rbx+230h]
0x14000279b  mov     rax, [rbp+10h]
0x14000279f  mov     [rdx+10h], rax
0x1400027a3  mov     rdx, [rbx+230h]
0x1400027aa  mov     rax, [rdx+10h]
0x1400027ae  mov     [rax+38h], rdx
0x1400027b2  movzx   edx, word ptr [rbp+4]
0x1400027b6  mov     rax, [rbx+230h]
0x1400027bd  and     dx, 8
0x1400027c1  mov     [rax+4], dx
0x1400027c5  mov     cl, [rsp+58h+Irql]; Irql
0x1400027c9  call    cs:__imp_IoReleaseVpbSpinLock
0x1400027d0  nop     dword ptr [rax+rax+00h]
0x1400027d5  mov     [rbx+230h], r14
0x1400027dc  jmp     short loc_14000284F
0x1400027de  add     [rcx], r15d
0x1400027e1  mov     ecx, 0FFFEh
0x1400027e6  mov     [rbp+8], r14
0x1400027ea  mov     rax, [rbx+8]
0x1400027ee  and     [rax+4], cx
0x1400027f2  mov     ecx, 0FFFDh
0x1400027f7  mov     rax, [rbx+8]
0x1400027fb  and     [rax+4], cx
0x1400027ff  mov     [rbx+8], r14
0x140002803  jmp     short loc_14000280C
0x140002805  test    dl, dl
0x140002807  jz      short loc_14000283F
0x140002809  add     [rcx], r15d
0x14000280c  mov     cl, [rsp+58h+Irql]; Irql
0x140002810  call    cs:__imp_IoReleaseVpbSpinLock
0x140002817  nop     dword ptr [rax+rax+00h]
0x14000281c  mov     rcx, rsi; FastMutex
0x14000281f  mov     [rbx+188h], r14
0x140002826  call    cs:__imp_ExReleaseFastMutex
0x14000282d  nop     dword ptr [rax+rax+00h]
0x140002832  mov     rdx, rbx
0x140002835  call    CdDeleteVcb
0x14000283a  mov     dil, r14b
0x14000283d  jmp     short loc_140002865
0x14000283f  mov     cl, [rsp+58h+Irql]; Irql
0x140002843  call    cs:__imp_IoReleaseVpbSpinLock
0x14000284a  nop     dword ptr [rax+rax+00h]
0x14000284f  mov     rcx, rsi; FastMutex
0x140002852  mov     [rbx+188h], r14
0x140002859  call    cs:__imp_ExReleaseFastMutex
0x140002860  nop     dword ptr [rax+rax+00h]
0x140002865  mov     al, dil
0x140002868  add     rsp, 28h
0x14000286c  pop     r15
0x14000286e  pop     r14
0x140002870  pop     rdi
0x140002871  pop     rsi
0x140002872  pop     rbp
0x140002873  pop     rbx
0x140002874  retn
```
