# FatFlushAndCleanAllVolumes

- ea: `0x140006918`
- end: `0x140006c62`
- name: `FatFlushAndCleanAllVolumes`
- size: `842`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1400068b0`

## callees

- `0x140002b30`
- `0x140006918`
- `0x140006dbc`
- `0x14000c680`
- `0x140039550`
- `0x14003e94c`
- `0x1400465f4`
- `0x1400466c8`
- `0x140048740`
- `0x14004a37c`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x140006b15`
- `ntoskrnl!KeCancelTimer` at `0x140006b15`
- `ntoskrnl!KeRemoveQueueDpc` at `0x140006b28`
- `ntoskrnl!KeRemoveQueueDpc` at `0x140006b28`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140006bb5`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140006bb5`
- `ntoskrnl!IoFreeIrp` at `0x140006bc9`
- `ntoskrnl!IoFreeIrp` at `0x140006bc9`
- `ntoskrnl!IoAllocateIrp` at `0x140006a92`
- `ntoskrnl!IoAllocateIrp` at `0x140006a92`
- `ntoskrnl!ExReleaseResourceLite` at `0x140006bef`
- `ntoskrnl!ExReleaseResourceLite` at `0x140006c15`
- `ntoskrnl!ExReleaseResourceLite` at `0x140006c28`
- `ntoskrnl!ExReleaseResourceLite` at `0x140006c43`
- `ntoskrnl!ExReleaseResourceLite` at `0x140006bef`
- `ntoskrnl!ExReleaseResourceLite` at `0x140006c15`
- `ntoskrnl!ExReleaseResourceLite` at `0x140006c28`
- `ntoskrnl!ExReleaseResourceLite` at `0x140006c43`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140006979`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140006979`

## pseudocode

```c
void __fastcall FatFlushAndCleanAllVolumes(char a1)
{
  char IsIrpTopLevel; // r13
  __int64 *i; // r14
  __int64 *v4; // rbx
  __int64 v5; // rcx
  _QWORD *v6; // r15
  __int64 j; // rdx
  __int64 NextFcbBottomUp; // rax
  __int64 v9; // rsi
  PIRP Irp; // rax
  __int64 v11; // rcx
  IRP *v12; // rsi
  struct _IO_STACK_LOCATION *v13; // rcx
  __int64 k; // rdx
  __int64 v15; // rax
  __int64 v16; // rsi
  _QWORD v17[25]; // [rsp+40h] [rbp-C8h] BYREF

  IsIrpTopLevel = 0;
  memset(v17, 0, 0x90u);
  LODWORD(v17[0]) = 9438472;
  LOWORD(v17[8]) = 16;
  HIDWORD(v17[8]) = 2086;
  ExAcquireResourceSharedLite(&Resource, 1u);
  for ( i = (__int64 *)qword_140017CB0; i != &qword_140017CB0; i = (__int64 *)*i )
  {
    v4 = i - 15;
    FatAcquireExclusiveVcb_Real(v17, i - 15, 0);
    if ( (i[10] & 0x40) == 0 && (v4[25] & 0x10000) == 0 && (v4[25] & 4) != 0 )
    {
      if ( a1 )
      {
        if ( (v4[25] & 0x200000) == 0 )
          goto LABEL_30;
      }
      else if ( (v4[25] & 0x1000) != 0 )
      {
        goto LABEL_30;
      }
      if ( *((_DWORD *)v4 + 51) == 1 && v4[24] )
      {
        FatAcquireExclusiveVcb_Real(v17, i - 15, 0);
        v6 = v4 + 26;
        for ( j = 0; ; j = v9 )
        {
          NextFcbBottomUp = FatGetNextFcbBottomUp(v5, j, *v6);
          v9 = NextFcbBottomUp;
          if ( !NextFcbBottomUp )
            break;
          FatAcquireExclusiveFcb(v17, NextFcbBottomUp);
        }
        v17[6] = *(_QWORD *)(v4[24] + 16);
        Irp = IoAllocateIrp(*(_BYTE *)(v4[17] + 76) + 1, 0);
        v12 = Irp;
        if ( Irp )
        {
          --Irp->CurrentLocation;
          v13 = --Irp->Tail.Overlay.CurrentStackLocation;
          v13->MajorFunction = 16;
          v13->DeviceObject = (PDEVICE_OBJECT)qword_140017CC8;
          v17[5] = Irp;
          IsIrpTopLevel = FatIsIrpTopLevel(Irp);
          FatVerifyVcb(v17, i - 15);
          FatFlushVolume(v17, i - 15, 1);
          v11 = *((unsigned int *)v4 + 50);
          if ( (v11 & 4) != 0 )
          {
            KeCancelTimer((PKTIMER)(v4 + 119));
            KeRemoveQueueDpc((PRKDPC)(v4 + 111));
            if ( (v4[25] & 0x10) == 0 )
            {
              FatMarkVolume((__int64)v17, (__int64)(i - 15), 0);
              _InterlockedAnd((volatile signed __int32 *)v4 + 50, 0xFFFFFFFB);
            }
            if ( (v4[25] & 2) != 0 && (v4[25] & 0x800) == 0 )
              FatToggleMediaEjectDisable(v11, i - 15, 0);
          }
        }
        if ( IsIrpTopLevel )
          IoSetTopLevelIrp(0);
        if ( v12 )
        {
          IoFreeIrp(v12);
          v17[5] = 0;
        }
        for ( k = 0; ; k = v16 )
        {
          v15 = FatGetNextFcbBottomUp(v11, k, *v6);
          v16 = v15;
          if ( !v15 )
            break;
          ExReleaseResourceLite(*(PERESOURCE *)(v15 + 8));
        }
        ExReleaseResourceLite((PERESOURCE)v4 + 5);
      }
    }
LABEL_30:
    ExReleaseResourceLite((PERESOURCE)v4 + 5);
  }
  ExReleaseResourceLite(&Resource);
}

```

## disassembly

```asm
0x140006918  mov     [rsp+arg_0], cl
0x14000691c  push    rbx
0x14000691d  push    rsi
0x14000691e  push    r12
0x140006920  push    r13
0x140006922  push    r14
0x140006924  push    r15
0x140006926  sub     rsp, 0D8h
0x14000692d  mov     r12b, cl
0x140006930  mov     [rsp+108h+var_E0], 0
0x140006939  xor     r13b, r13b
0x14000693c  mov     [rsp+108h+var_E8], r13b
0x140006941  xor     edx, edx; Val
0x140006943  mov     r8d, 90h; Size
0x140006949  lea     rcx, [rsp+108h+var_C8]; void *
0x14000694e  call    memset
0x140006953  mov     [rsp+108h+var_C8], 900508h
0x14000695b  mov     [rsp+108h+var_88], 10h
0x140006965  mov     [rsp+108h+var_84], 826h
0x140006970  mov     dl, 1; Wait
0x140006972  lea     rcx, Resource; Resource
0x140006979  call    cs:__imp_ExAcquireResourceSharedLite
0x140006980  nop     dword ptr [rax+rax+00h]
0x140006985  mov     r14, cs:qword_140017CB0
0x14000698c  mov     [rsp+108h+arg_8], r14
0x140006994  lea     rax, qword_140017CB0
0x14000699b  cmp     r14, rax
0x14000699e  jz      loc_140006C3C
0x1400069a4  lea     rbx, [r14-78h]
0x1400069a8  mov     [rsp+108h+arg_10], rbx
0x1400069b0  xor     r8d, r8d
0x1400069b3  mov     rdx, rbx
0x1400069b6  lea     rcx, [rsp+108h+var_C8]
0x1400069bb  call    FatAcquireExclusiveVcb_Real
0x1400069c0  mov     eax, [rbx+0C8h]
0x1400069c6  test    al, 40h
0x1400069c8  jnz     loc_140006C21
0x1400069ce  mov     eax, [rbx+0C8h]
0x1400069d4  bt      eax, 10h
0x1400069d8  jb      loc_140006C21
0x1400069de  mov     eax, [rbx+0C8h]
0x1400069e4  test    al, 4
0x1400069e6  jz      loc_140006C21
0x1400069ec  test    r12b, r12b
0x1400069ef  jnz     short loc_140006A06
0x1400069f1  mov     eax, [rbx+0C8h]
0x1400069f7  bt      eax, 0Ch
0x1400069fb  jb      loc_140006C21
0x140006a01  test    r12b, r12b
0x140006a04  jz      short loc_140006A16
0x140006a06  mov     eax, [rbx+0C8h]
0x140006a0c  bt      eax, 15h
0x140006a10  jnb     loc_140006C21
0x140006a16  cmp     dword ptr [rbx+0CCh], 1
0x140006a1d  jnz     loc_140006C21
0x140006a23  cmp     qword ptr [rbx+0C0h], 0
0x140006a2b  jz      loc_140006C21
0x140006a31  xor     r8d, r8d
0x140006a34  mov     rdx, rbx
0x140006a37  lea     rcx, [rsp+108h+var_C8]
0x140006a3c  call    FatAcquireExclusiveVcb_Real
0x140006a41  lea     r15, [rbx+0D0h]
0x140006a48  mov     [rsp+108h+arg_18], r15
0x140006a50  xor     edx, edx
0x140006a52  jmp     short loc_140006A64
0x140006a54  mov     rdx, rsi
0x140006a57  lea     rcx, [rsp+108h+var_C8]
0x140006a5c  call    FatAcquireExclusiveFcb
0x140006a61  mov     rdx, rsi
0x140006a64  mov     r8, [r15]
0x140006a67  call    FatGetNextFcbBottomUp
0x140006a6c  test    rax, rax
0x140006a6f  mov     rsi, rax
0x140006a72  jnz     short loc_140006A54
0x140006a74  mov     rax, [rbx+0C0h]
0x140006a7b  mov     rcx, [rax+10h]
0x140006a7f  mov     [rsp+108h+var_98], rcx
0x140006a84  mov     rax, [rbx+88h]
0x140006a8b  mov     cl, [rax+4Ch]
0x140006a8e  inc     cl; StackSize
0x140006a90  xor     edx, edx; ChargeQuota
0x140006a92  call    cs:__imp_IoAllocateIrp
0x140006a99  nop     dword ptr [rax+rax+00h]
0x140006a9e  mov     rsi, rax
0x140006aa1  mov     [rsp+108h+var_E0], rax
0x140006aa6  test    rax, rax
0x140006aa9  jz      loc_140006B77
0x140006aaf  dec     byte ptr [rax+43h]
0x140006ab2  add     qword ptr [rax+0B8h], 0FFFFFFFFFFFFFFB8h
0x140006aba  mov     rcx, [rax+0B8h]
0x140006ac1  mov     byte ptr [rcx], 10h
0x140006ac4  mov     rax, cs:qword_140017CC8
0x140006acb  mov     [rcx+28h], rax
0x140006acf  mov     [rsp+108h+var_A0], rsi
0x140006ad4  mov     rcx, rsi; Irp
0x140006ad7  call    FatIsIrpTopLevel
0x140006adc  mov     r13b, al
0x140006adf  mov     [rsp+108h+var_E8], al
0x140006ae3  mov     rdx, rbx
0x140006ae6  lea     rcx, [rsp+108h+var_C8]
0x140006aeb  call    FatVerifyVcb
0x140006af0  mov     r8d, 1
0x140006af6  mov     rdx, rbx
0x140006af9  lea     rcx, [rsp+108h+var_C8]
0x140006afe  call    FatFlushVolume
0x140006b03  mov     ecx, [rbx+0C8h]
0x140006b09  test    cl, 4
0x140006b0c  jz      short loc_140006B77
0x140006b0e  lea     rcx, [rbx+3B8h]; PKTIMER
0x140006b15  call    cs:__imp_KeCancelTimer
0x140006b1c  nop     dword ptr [rax+rax+00h]
0x140006b21  lea     rcx, [rbx+378h]; Dpc
0x140006b28  call    cs:__imp_KeRemoveQueueDpc
0x140006b2f  nop     dword ptr [rax+rax+00h]
0x140006b34  mov     eax, [rbx+0C8h]
0x140006b3a  test    al, 10h
0x140006b3c  jnz     short loc_140006B56
0x140006b3e  xor     r8d, r8d
0x140006b41  mov     rdx, rbx
0x140006b44  lea     rcx, [rsp+108h+var_C8]
0x140006b49  call    FatMarkVolume
0x140006b4e  lock and dword ptr [rbx+0C8h], 0FFFFFFFBh
0x140006b56  mov     eax, [rbx+0C8h]
0x140006b5c  test    al, 2
0x140006b5e  jz      short loc_140006B77
0x140006b60  mov     eax, [rbx+0C8h]
0x140006b66  bt      eax, 0Bh
0x140006b6a  jb      short loc_140006B77
0x140006b6c  xor     r8d, r8d
0x140006b6f  mov     rdx, rbx
0x140006b72  call    FatToggleMediaEjectDisable
0x140006b77  jmp     short loc_140006BAE
0x140006b79  mov     [rsp+108h+var_80], 0
0x140006b84  mov     r12b, [rsp+108h+arg_0]
0x140006b8c  mov     r14, [rsp+108h+arg_8]
0x140006b94  mov     rbx, [rsp+108h+arg_10]
0x140006b9c  mov     rsi, [rsp+108h+var_E0]
0x140006ba1  mov     r13b, [rsp+108h+var_E8]
0x140006ba6  mov     r15, [rsp+108h+arg_18]
0x140006bae  test    r13b, r13b
0x140006bb1  jz      short loc_140006BC1
0x140006bb3  xor     ecx, ecx; Irp
0x140006bb5  call    cs:__imp_IoSetTopLevelIrp
0x140006bbc  nop     dword ptr [rax+rax+00h]
0x140006bc1  test    rsi, rsi
0x140006bc4  jz      short loc_140006BE7
0x140006bc6  mov     rcx, rsi; Irp
0x140006bc9  call    cs:__imp_IoFreeIrp
0x140006bd0  nop     dword ptr [rax+rax+00h]
0x140006bd5  mov     [rsp+108h+var_E0], 0
0x140006bde  mov     [rsp+108h+var_A0], 0
0x140006be7  xor     edx, edx
0x140006be9  jmp     short loc_140006BFE
0x140006beb  mov     rcx, [rsi+8]; Resource
0x140006bef  call    cs:__imp_ExReleaseResourceLite
0x140006bf6  nop     dword ptr [rax+rax+00h]
0x140006bfb  mov     rdx, rsi
0x140006bfe  mov     r8, [r15]
0x140006c01  call    FatGetNextFcbBottomUp
0x140006c06  test    rax, rax
0x140006c09  mov     rsi, rax
0x140006c0c  jnz     short loc_140006BEB
0x140006c0e  lea     rcx, [rbx+208h]; Resource
0x140006c15  call    cs:__imp_ExReleaseResourceLite
0x140006c1c  nop     dword ptr [rax+rax+00h]
0x140006c21  lea     rcx, [rbx+208h]; Resource
0x140006c28  call    cs:__imp_ExReleaseResourceLite
0x140006c2f  nop     dword ptr [rax+rax+00h]
0x140006c34  mov     r14, [r14]
0x140006c37  jmp     loc_14000698C
0x140006c3c  lea     rcx, Resource; Resource
0x140006c43  call    cs:__imp_ExReleaseResourceLite
0x140006c4a  nop     dword ptr [rax+rax+00h]
0x140006c4f  add     rsp, 0D8h
0x140006c56  pop     r15
0x140006c58  pop     r14
0x140006c5a  pop     r13
0x140006c5c  pop     r12
0x140006c5e  pop     rsi
0x140006c5f  pop     rbx
0x140006c60  retn
0x14000d31b  push    rbp
0x14000d31d  sub     rsp, 20h
0x14000d321  mov     rbp, rdx
0x14000d324  mov     eax, 1
0x14000d329  add     rsp, 20h
0x14000d32d  pop     rbp
0x14000d32e  retn
```
