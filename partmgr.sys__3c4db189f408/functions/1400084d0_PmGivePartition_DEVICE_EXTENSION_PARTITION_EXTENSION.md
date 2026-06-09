# PmGivePartition(_DEVICE_EXTENSION *,_PARTITION_EXTENSION *)

- ea: `0x1400084d0`
- end: `0x1400087b5`
- name: `?PmGivePartition@@YAXPEAU_DEVICE_EXTENSION@@PEAU_PARTITION_EXTENSION@@@Z`
- size: `741`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *, struct _PARTITION_EXTENSION *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400087c0`

## callees

- `0x140005994`
- `0x1400079fc`
- `0x1400084d0`
- `0x140011440`

## import_xrefs

- `ntoskrnl!IoForwardIrpSynchronously` at `0x140008663`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140008763`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140008663`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140008763`
- `ntoskrnl!IoReuseIrp` at `0x14000860f`
- `ntoskrnl!IoReuseIrp` at `0x14000870b`
- `ntoskrnl!IoReuseIrp` at `0x14000860f`
- `ntoskrnl!IoReuseIrp` at `0x14000870b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400085f7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400086c9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400085f7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400086c9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008555`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400086ae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008555`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400086ae`

## pseudocode

```c
void __fastcall PmGivePartition(struct _DEVICE_EXTENSION *a1, struct _PARTITION_EXTENSION *a2)
{
  char v4; // r12
  char *DeviceExtension; // r15
  volatile signed __int32 **v6; // r15
  volatile signed __int32 *i; // r14
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  KIRQL v16; // r8
  __int64 v17; // rax
  __int64 v18; // rbx
  struct _DEVICE_OBJECT *v19; // rcx
  __int64 v20; // rax
  int v21; // eax
  KIRQL v22; // al
  IRP *v23; // rcx
  __int64 v24; // rax
  IRP *v25; // rbx
  struct _DEVICE_OBJECT *v26; // rcx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  int v28; // ecx
  unsigned int v29; // eax
  __int64 v30; // [rsp+20h] [rbp-99h] BYREF
  __int128 v31; // [rsp+28h] [rbp-91h]
  _OWORD v32[13]; // [rsp+40h] [rbp-79h] BYREF

  v4 = 0;
  DeviceExtension = (char *)PmControlObject->DeviceExtension;
  memset(v32, 0, 0x90u);
  v30 = 0;
  v31 = 0;
  if ( !*((_BYTE *)a1 + 604) || DeviceExtension[168] )
    *(_DWORD *)(*((_QWORD *)a2 + 1) + 52LL) |= *(_DWORD *)(*((_QWORD *)a1 + 1) + 52LL) & 0x40001;
  v6 = (volatile signed __int32 **)(DeviceExtension + 72);
  for ( i = *v6; i != (volatile signed __int32 *)v6; i = *(volatile signed __int32 **)i )
  {
    KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 14);
    v8 = *(_OWORD *)((char *)a2 + 184);
    v32[0] = *(_OWORD *)((char *)a2 + 168);
    v9 = *(_OWORD *)((char *)a2 + 200);
    v32[1] = v8;
    v10 = *(_OWORD *)((char *)a2 + 216);
    v32[2] = v9;
    v11 = *(_OWORD *)((char *)a2 + 232);
    v32[3] = v10;
    v12 = *(_OWORD *)((char *)a2 + 248);
    v32[4] = v11;
    v13 = *(_OWORD *)((char *)a2 + 264);
    v32[5] = v12;
    v14 = *(_OWORD *)((char *)a2 + 280);
    v32[6] = v13;
    v15 = *(_OWORD *)((char *)a2 + 296);
    v32[7] = v14;
    v32[8] = v15;
    *(_QWORD *)&v32[1] = PartitionLength(a2, 1u);
    v30 = *((_QWORD *)a2 + 1);
    *(_QWORD *)&v31 = *((_QWORD *)a1 + 3);
    *((_QWORD *)&v31 + 1) = v32;
    KeReleaseSpinLock((PKSPIN_LOCK)a1 + 14, v16);
    IoReuseIrp(*((PIRP *)a1 + 107), -1073741637);
    v17 = *((_QWORD *)a1 + 107);
    --*(_BYTE *)(v17 + 67);
    *(_QWORD *)(v17 + 184) -= 72LL;
    v18 = *((_QWORD *)a1 + 107);
    v19 = (struct _DEVICE_OBJECT *)*((_QWORD *)i + 5);
    v20 = *(_QWORD *)(v18 + 184);
    *(_BYTE *)v20 = 15;
    *(_QWORD *)(v18 + 24) = &v30;
    *(_DWORD *)(v20 + 8) = 1;
    *(_DWORD *)(v20 + 16) = 24;
    *(_DWORD *)(v20 + 24) = 7733248;
    IoForwardIrpSynchronously(v19, (PIRP)v18);
    v21 = *(_DWORD *)(v18 + 56);
    if ( *(int *)(v18 + 48) >= 0 )
    {
      _InterlockedIncrement(i + 8);
      *((_QWORD *)a2 + 14) = i;
      if ( v21 != 1 || !(_BYTE)v30 )
        v4 = 1;
      break;
    }
  }
  if ( *((_QWORD *)a2 + 14) && !v4
    || (v22 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 14),
        *((_DWORD *)a2 + 10) &= ~2u,
        KeReleaseSpinLock((PKSPIN_LOCK)a1 + 14, v22),
        PmDecrementPendingPartitionsCount(a1, 1),
        *((_QWORD *)a2 + 14)) )
  {
    v23 = (IRP *)*((_QWORD *)a1 + 107);
    v30 = *((_QWORD *)a2 + 1);
    *(_QWORD *)&v31 = *((_QWORD *)a1 + 3);
    IoReuseIrp(v23, -1073741637);
    v24 = *((_QWORD *)a1 + 107);
    --*(_BYTE *)(v24 + 67);
    *(_QWORD *)(v24 + 184) -= 72LL;
    v25 = (IRP *)*((_QWORD *)a1 + 107);
    v26 = *(struct _DEVICE_OBJECT **)(*((_QWORD *)a2 + 14) + 40LL);
    CurrentStackLocation = v25->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation->MajorFunction = 15;
    v25->AssociatedIrp.MasterIrp = (struct _IRP *)&v30;
    CurrentStackLocation->Parameters.Read.Length = 0;
    CurrentStackLocation->Parameters.Create.Options = 24;
    CurrentStackLocation->Parameters.Read.ByteOffset.LowPart = 7733296;
    IoForwardIrpSynchronously(v26, v25);
    if ( v25->IoStatus.Status < 0 )
    {
      v29 = 2;
    }
    else
    {
      v28 = *((_DWORD *)a1 + 163);
      *((_DWORD *)a1 + 163) = v28 + 1;
      *((_DWORD *)a2 + 26) = 1;
      v29 = v28 == 0;
    }
    _InterlockedAdd((volatile signed __int32 *)a1 + 162, v29);
  }
}

```

## disassembly

```asm
0x1400084d0  push    rbp
0x1400084d2  push    rbx
0x1400084d3  push    rsi
0x1400084d4  push    rdi
0x1400084d5  push    r12
0x1400084d7  push    r13
0x1400084d9  push    r14
0x1400084db  push    r15
0x1400084dd  lea     rbp, [rsp-1Fh]
0x1400084e2  sub     rsp, 0D8h
0x1400084e9  mov     rax, cs:?PmControlObject@@3PEAU_DEVICE_OBJECT@@EA; _DEVICE_OBJECT * PmControlObject
0x1400084f0  mov     rsi, rdx
0x1400084f3  mov     rdi, rcx
0x1400084f6  xor     edx, edx; Val
0x1400084f8  mov     r8d, 90h; Size
0x1400084fe  lea     rcx, [rbp+57h+var_D0]; void *
0x140008502  xor     r12b, r12b
0x140008505  mov     r15, [rax+40h]
0x140008509  call    memset
0x14000850e  xorps   xmm0, xmm0
0x140008511  mov     [rsp+110h+var_F0], 0
0x14000851a  movups  [rsp+110h+var_E8], xmm0
0x14000851f  cmp     [rdi+25Ch], r12b
0x140008526  jz      short loc_140008531
0x140008528  cmp     [r15+0A8h], r12b
0x14000852f  jz      short loc_140008545
0x140008531  mov     rax, [rdi+8]
0x140008535  mov     rdx, [rsi+8]
0x140008539  mov     ecx, [rax+34h]
0x14000853c  and     ecx, 40001h
0x140008542  or      [rdx+34h], ecx
0x140008545  add     r15, 48h ; 'H'
0x140008549  mov     r14, [r15]
0x14000854c  jmp     loc_14000867B
0x140008551  lea     rcx, [rdi+70h]; SpinLock
0x140008555  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000855c  nop     dword ptr [rax+rax+00h]
0x140008561  movups  xmm0, xmmword ptr [rsi+0A8h]
0x140008568  mov     dl, 1; unsigned __int8
0x14000856a  mov     rcx, rsi; struct _PARTITION_EXTENSION *
0x14000856d  movups  xmm1, xmmword ptr [rsi+0B8h]
0x140008574  mov     r8b, al
0x140008577  movups  [rbp+57h+var_D0], xmm0
0x14000857b  movups  xmm0, xmmword ptr [rsi+0C8h]
0x140008582  movups  [rbp+57h+var_C0], xmm1
0x140008586  movups  xmm1, xmmword ptr [rsi+0D8h]
0x14000858d  movups  [rbp+57h+var_B0], xmm0
0x140008591  movups  xmm0, xmmword ptr [rsi+0E8h]
0x140008598  movups  [rbp+57h+var_A0], xmm1
0x14000859c  movups  xmm1, xmmword ptr [rsi+0F8h]
0x1400085a3  movups  [rbp+57h+var_90], xmm0
0x1400085a7  movups  xmm0, xmmword ptr [rsi+108h]
0x1400085ae  movups  [rbp+57h+var_80], xmm1
0x1400085b2  movups  xmm1, xmmword ptr [rsi+118h]
0x1400085b9  movups  [rbp+57h+var_70], xmm0
0x1400085bd  movups  xmm0, xmmword ptr [rsi+128h]
0x1400085c4  movups  [rbp+57h+var_60], xmm1
0x1400085c8  movups  [rbp+57h+var_50], xmm0
0x1400085cc  call    ?PartitionLength@@YA_KPEAU_PARTITION_EXTENSION@@E@Z; PartitionLength(_PARTITION_EXTENSION *,uchar)
0x1400085d1  mov     qword ptr [rbp+57h+var_C0], rax
0x1400085d5  lea     rcx, [rdi+70h]; SpinLock
0x1400085d9  mov     rax, [rsi+8]
0x1400085dd  mov     dl, r8b; NewIrql
0x1400085e0  mov     [rsp+110h+var_F0], rax
0x1400085e5  mov     rax, [rdi+18h]
0x1400085e9  mov     qword ptr [rsp+110h+var_E8], rax
0x1400085ee  lea     rax, [rbp+57h+var_D0]
0x1400085f2  mov     qword ptr [rsp+110h+var_E8+8], rax
0x1400085f7  call    cs:__imp_KeReleaseSpinLock
0x1400085fe  nop     dword ptr [rax+rax+00h]
0x140008603  mov     rcx, [rdi+358h]; Irp
0x14000860a  mov     edx, 0C00000BBh; Iostatus
0x14000860f  call    cs:__imp_IoReuseIrp
0x140008616  nop     dword ptr [rax+rax+00h]
0x14000861b  mov     rax, [rdi+358h]
0x140008622  lea     rdx, [rsp+110h+var_F0]
0x140008627  dec     byte ptr [rax+43h]
0x14000862a  add     qword ptr [rax+0B8h], 0FFFFFFFFFFFFFFB8h
0x140008632  mov     rbx, [rdi+358h]
0x140008639  mov     rcx, [r14+28h]; DeviceObject
0x14000863d  mov     rax, [rbx+0B8h]
0x140008644  mov     byte ptr [rax], 0Fh
0x140008647  mov     [rbx+18h], rdx
0x14000864b  mov     rdx, rbx; Irp
0x14000864e  mov     dword ptr [rax+8], 1
0x140008655  mov     dword ptr [rax+10h], 18h
0x14000865c  mov     dword ptr [rax+18h], 760000h
0x140008663  call    cs:__imp_IoForwardIrpSynchronously
0x14000866a  nop     dword ptr [rax+rax+00h]
0x14000866f  cmp     dword ptr [rbx+30h], 0
0x140008673  mov     eax, [rbx+38h]
0x140008676  jge     short loc_140008686
0x140008678  mov     r14, [r14]
0x14000867b  cmp     r14, r15
0x14000867e  jnz     loc_140008551
0x140008684  jmp     short loc_14000869E
0x140008686  lock inc dword ptr [r14+20h]
0x14000868b  mov     [rsi+70h], r14
0x14000868f  cmp     eax, 1
0x140008692  jnz     short loc_14000869B
0x140008694  cmp     byte ptr [rsp+110h+var_F0], r12b
0x140008699  jnz     short loc_14000869E
0x14000869b  mov     r12b, 1
0x14000869e  cmp     qword ptr [rsi+70h], 0
0x1400086a3  jz      short loc_1400086AA
0x1400086a5  test    r12b, r12b
0x1400086a8  jz      short loc_1400086ED
0x1400086aa  lea     rcx, [rdi+70h]; SpinLock
0x1400086ae  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400086b5  nop     dword ptr [rax+rax+00h]
0x1400086ba  mov     edx, [rsi+28h]
0x1400086bd  lea     rcx, [rdi+70h]; SpinLock
0x1400086c1  and     edx, 0FFFFFFFDh
0x1400086c4  mov     [rsi+28h], edx
0x1400086c7  mov     dl, al; NewIrql
0x1400086c9  call    cs:__imp_KeReleaseSpinLock
0x1400086d0  nop     dword ptr [rax+rax+00h]
0x1400086d5  mov     edx, 1; int
0x1400086da  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x1400086dd  call    ?PmDecrementPendingPartitionsCount@@YAXPEAU_DEVICE_EXTENSION@@J@Z; PmDecrementPendingPartitionsCount(_DEVICE_EXTENSION *,long)
0x1400086e2  cmp     qword ptr [rsi+70h], 0
0x1400086e7  jz      loc_1400087A0
0x1400086ed  mov     rax, [rsi+8]
0x1400086f1  mov     edx, 0C00000BBh; Iostatus
0x1400086f6  mov     rcx, [rdi+358h]; Irp
0x1400086fd  mov     [rsp+110h+var_F0], rax
0x140008702  mov     rax, [rdi+18h]
0x140008706  mov     qword ptr [rsp+110h+var_E8], rax
0x14000870b  call    cs:__imp_IoReuseIrp
0x140008712  nop     dword ptr [rax+rax+00h]
0x140008717  mov     rax, [rdi+358h]
0x14000871e  lea     rdx, [rsp+110h+var_F0]
0x140008723  dec     byte ptr [rax+43h]
0x140008726  add     qword ptr [rax+0B8h], 0FFFFFFFFFFFFFFB8h
0x14000872e  mov     rax, [rsi+70h]
0x140008732  mov     rbx, [rdi+358h]
0x140008739  mov     rcx, [rax+28h]; DeviceObject
0x14000873d  mov     rax, [rbx+0B8h]
0x140008744  mov     byte ptr [rax], 0Fh
0x140008747  mov     [rbx+18h], rdx
0x14000874b  mov     rdx, rbx; Irp
0x14000874e  mov     dword ptr [rax+8], 0
0x140008755  mov     dword ptr [rax+10h], 18h
0x14000875c  mov     dword ptr [rax+18h], 760030h
0x140008763  call    cs:__imp_IoForwardIrpSynchronously
0x14000876a  nop     dword ptr [rax+rax+00h]
0x14000876f  cmp     dword ptr [rbx+30h], 0
0x140008773  jl      short loc_140008794
0x140008775  mov     ecx, [rdi+28Ch]
0x14000877b  lea     eax, [rcx+1]
0x14000877e  mov     [rdi+28Ch], eax
0x140008784  xor     eax, eax
0x140008786  test    ecx, ecx
0x140008788  mov     dword ptr [rsi+68h], 1
0x14000878f  setz    al
0x140008792  jmp     short loc_140008799
0x140008794  mov     eax, 2
0x140008799  lock add [rdi+288h], eax
0x1400087a0  add     rsp, 0D8h
0x1400087a7  pop     r15
0x1400087a9  pop     r14
0x1400087ab  pop     r13
0x1400087ad  pop     r12
0x1400087af  pop     rdi
0x1400087b0  pop     rsi
0x1400087b1  pop     rbx
0x1400087b2  pop     rbp
0x1400087b3  retn
```
