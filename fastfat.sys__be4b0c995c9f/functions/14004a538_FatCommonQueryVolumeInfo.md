# FatCommonQueryVolumeInfo

- ea: `0x14004a538`
- end: `0x14004a7e1`
- name: `FatCommonQueryVolumeInfo`
- size: `681`
- prototype: `__int64 __fastcall(PVOID Context1, PVOID Context2)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400438e0`
- `0x14004a8f0`

## callees

- `0x140007408`
- `0x14000c380`
- `0x140038eb4`
- `0x14003d880`
- `0x140046a28`
- `0x14004a1d4`
- `0x14004a538`
- `0x14004aa68`

## import_xrefs

- `ntoskrnl!FsRtlGetSectorSizeInformation` at `0x14004a5fd`
- `ntoskrnl!FsRtlGetSectorSizeInformation` at `0x14004a5fd`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004a7b4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005fed1`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004a7b4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005fed1`

## pseudocode

```c
__int64 __fastcall FatCommonQueryVolumeInfo(PVOID Context1, IRP *Context2)
{
  IRP *v2; // r13
  unsigned int SectorSizeInformation; // edi
  ULONG Length; // r14d
  ULONG Options; // ebx
  struct _IRP *MasterIrp; // rsi
  __int64 v8; // r15
  __int64 v9; // rcx
  __int64 v10; // r9
  ULONG v11; // ebx
  ULONG v12; // ebx
  ULONG v13; // ebx
  ULONG v14; // ebx
  ULONG v15; // ebx
  ULONG v16; // eax
  unsigned int v17; // r14d
  unsigned int v18; // ecx
  unsigned int v19; // eax
  unsigned int v20; // ebx
  char v22; // [rsp+20h] [rbp-58h]
  __int64 v23; // [rsp+28h] [rbp-50h] BYREF
  __int64 v24; // [rsp+30h] [rbp-48h] BYREF
  struct _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+38h] [rbp-40h]
  ULONG v26; // [rsp+90h] [rbp+18h] BYREF
  __int64 v27; // [rsp+98h] [rbp+20h] BYREF

  v2 = Context2;
  SectorSizeInformation = 0;
  v27 = 0;
  v24 = 0;
  v23 = 0;
  v22 = 0;
  CurrentStackLocation = Context2->Tail.Overlay.CurrentStackLocation;
  Length = CurrentStackLocation->Parameters.Read.Length;
  v26 = Length;
  Options = CurrentStackLocation->Parameters.Create.Options;
  MasterIrp = Context2->AssociatedIrp.MasterIrp;
  FatDecodeFileObject(CurrentStackLocation->FileObject, &v27, &v24, &v23);
  v8 = v27;
  FatVerifyFcb(Context1, *(_QWORD *)(v27 + 208));
  v11 = Options - 1;
  if ( !v11 )
  {
    if ( !(unsigned __int8)FatAcquireSharedVcb(Context1, v8) )
    {
      SectorSizeInformation = FatFsdPostRequest(Context1, v2);
      Context1 = 0;
      v2 = 0;
      goto LABEL_22;
    }
    v22 = 1;
    *(_OWORD *)&MasterIrp->Type = 0;
    *(_QWORD *)&MasterIrp->Flags = 0;
    LODWORD(MasterIrp->MdlAddress) = *(_DWORD *)(*(_QWORD *)(v8 + 192) + 24LL);
    v17 = Length - 18;
    v26 = v17;
    v18 = *(unsigned __int16 *)(*(_QWORD *)(v8 + 192) + 6LL);
    SectorSizeInformation = v17 < v18 ? 0x80000005 : 0;
    v19 = v18;
    if ( v17 < v18 )
      v19 = v17;
    v20 = v19;
    HIDWORD(MasterIrp->MdlAddress) = v18;
    memmove((char *)&MasterIrp->Flags + 2, (const void *)(*(_QWORD *)(v8 + 192) + 32LL), v19);
    Length = v17 - v20;
    goto LABEL_20;
  }
  v12 = v11 - 2;
  if ( !v12 )
  {
    *(_OWORD *)&MasterIrp->Type = 0;
    *(_QWORD *)&MasterIrp->Flags = 0;
    *(_DWORD *)&MasterIrp->Type = *(_DWORD *)(v8 + 364);
    LODWORD(MasterIrp->MdlAddress) = *(_DWORD *)(v8 + 368);
    MasterIrp->Flags = *(unsigned __int8 *)(v8 + 290);
    *(&MasterIrp->Flags + 1) = *(unsigned __int16 *)(v8 + 288);
    Length -= 24;
    goto LABEL_20;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
    *(_QWORD *)&MasterIrp->Type = 0;
    *(_DWORD *)&MasterIrp->Type = 7;
    *(_DWORD *)(&MasterIrp->Size + 1) = *(_DWORD *)(*(_QWORD *)(v8 + 136) + 52LL);
    Length -= 8;
LABEL_20:
    v26 = Length;
    goto LABEL_21;
  }
  v14 = v13 - 1;
  if ( v14 )
  {
    v15 = v14 - 2;
    if ( v15 )
    {
      if ( v15 == 4 )
      {
        SectorSizeInformation = FsRtlGetSectorSizeInformation(*(_QWORD *)(*(_QWORD *)(v8 + 192) + 16LL), MasterIrp);
        if ( (SectorSizeInformation & 0x80000000) == 0 )
        {
          Length -= 28;
          v26 = Length;
        }
      }
      else
      {
        SectorSizeInformation = -1073741811;
      }
      goto LABEL_21;
    }
    *(_OWORD *)&MasterIrp->Type = 0;
    *(_OWORD *)&MasterIrp->Flags = 0;
    *(_DWORD *)&MasterIrp->Type = *(_DWORD *)(v8 + 364);
    v16 = *(_DWORD *)(v8 + 368);
    LODWORD(MasterIrp->MdlAddress) = v16;
    MasterIrp->Flags = v16;
    MasterIrp->AssociatedIrp.IrpCount = *(unsigned __int8 *)(v8 + 290);
    HIDWORD(MasterIrp->AssociatedIrp.SystemBuffer) = *(unsigned __int16 *)(v8 + 288);
    Length -= 32;
    goto LABEL_20;
  }
  SectorSizeInformation = FatQueryFsAttributeInfo(v9, v8, MasterIrp, &v26);
  Length = v26;
LABEL_21:
  v2->IoStatus.Information = CurrentStackLocation->Parameters.Read.Length - Length;
LABEL_22:
  if ( v22 )
    ExReleaseResourceLite((PERESOURCE)(v8 + 520));
  FatCompleteRequest_Real(Context1, v2, SectorSizeInformation, v10);
  return SectorSizeInformation;
}

```

## disassembly

```asm
0x14004a538  mov     r11, rsp
0x14004a53b  mov     [r11+10h], rdx
0x14004a53f  mov     [r11+8], rcx
0x14004a543  push    rbx
0x14004a544  push    rsi
0x14004a545  push    rdi
0x14004a546  push    r12
0x14004a548  push    r13
0x14004a54a  push    r14
0x14004a54c  push    r15
0x14004a54e  sub     rsp, 40h
0x14004a552  mov     r13, rdx
0x14004a555  mov     r12, rcx
0x14004a558  xor     edi, edi
0x14004a55a  mov     [rsp+78h+var_54], edi
0x14004a55e  mov     [r11+20h], rdi
0x14004a562  mov     [r11-48h], rdi
0x14004a566  mov     [r11-50h], rdi
0x14004a56a  mov     [rsp+78h+var_58], dil
0x14004a56f  mov     rax, [rdx+0B8h]
0x14004a576  mov     [rsp+78h+var_40], rax
0x14004a57b  mov     r14d, [rax+8]
0x14004a57f  mov     [r11+18h], r14d
0x14004a583  mov     ebx, [rax+10h]
0x14004a586  mov     rsi, [rdx+18h]
0x14004a58a  lea     r9, [r11-50h]
0x14004a58e  lea     r8, [r11-48h]
0x14004a592  lea     rdx, [r11+20h]
0x14004a596  mov     rcx, [rax+30h]
0x14004a59a  call    FatDecodeFileObject
0x14004a59f  nop
0x14004a5a0  mov     r15, [rsp+78h+arg_18]
0x14004a5a8  mov     rdx, [r15+0D0h]
0x14004a5af  mov     rcx, r12
0x14004a5b2  call    FatVerifyFcb
0x14004a5b7  sub     ebx, 1
0x14004a5ba  jz      loc_14004A6E8
0x14004a5c0  sub     ebx, 2
0x14004a5c3  jz      loc_14004A6AA
0x14004a5c9  sub     ebx, 1
0x14004a5cc  jz      loc_14004A689
0x14004a5d2  sub     ebx, 1
0x14004a5d5  jz      loc_14004A663
0x14004a5db  sub     ebx, 2
0x14004a5de  jz      short loc_14004A624
0x14004a5e0  cmp     ebx, 4
0x14004a5e3  jz      short loc_14004A5EF
0x14004a5e5  mov     edi, 0C000000Dh
0x14004a5ea  jmp     loc_14004A793
0x14004a5ef  mov     rcx, [r15+0C0h]
0x14004a5f6  mov     rdx, rsi
0x14004a5f9  mov     rcx, [rcx+10h]
0x14004a5fd  call    cs:__imp_FsRtlGetSectorSizeInformation
0x14004a604  nop     dword ptr [rax+rax+00h]
0x14004a609  mov     edi, eax
0x14004a60b  test    eax, eax
0x14004a60d  js      short loc_14004A61B
0x14004a60f  add     r14d, 0FFFFFFE4h
0x14004a613  mov     [rsp+78h+arg_10], r14d
0x14004a61b  mov     [rsp+78h+var_54], eax
0x14004a61f  jmp     loc_14004A797
0x14004a624  xorps   xmm0, xmm0
0x14004a627  movups  xmmword ptr [rsi], xmm0
0x14004a62a  movups  xmmword ptr [rsi+10h], xmm0
0x14004a62e  mov     eax, [r15+16Ch]
0x14004a635  mov     [rsi], eax
0x14004a637  mov     eax, [r15+170h]
0x14004a63e  mov     [rsi+8], eax
0x14004a641  mov     [rsi+10h], eax
0x14004a644  movzx   eax, byte ptr [r15+122h]
0x14004a64c  mov     [rsi+18h], eax
0x14004a64f  movzx   eax, word ptr [r15+120h]
0x14004a657  mov     [rsi+1Ch], eax
0x14004a65a  add     r14d, 0FFFFFFE0h
0x14004a65e  jmp     loc_14004A78B
0x14004a663  lea     r9, [rsp+78h+arg_10]
0x14004a66b  mov     r8, rsi
0x14004a66e  mov     rdx, r15
0x14004a671  call    FatQueryFsAttributeInfo
0x14004a676  mov     edi, eax
0x14004a678  mov     [rsp+78h+var_54], eax
0x14004a67c  mov     r14d, [rsp+78h+arg_10]
0x14004a684  jmp     loc_14004A797
0x14004a689  xor     eax, eax
0x14004a68b  mov     [rsi], rax
0x14004a68e  mov     dword ptr [rsi], 7
0x14004a694  mov     rax, [r15+88h]
0x14004a69b  mov     ecx, [rax+34h]
0x14004a69e  mov     [rsi+4], ecx
0x14004a6a1  add     r14d, 0FFFFFFF8h
0x14004a6a5  jmp     loc_14004A78B
0x14004a6aa  xorps   xmm0, xmm0
0x14004a6ad  xor     eax, eax
0x14004a6af  movups  xmmword ptr [rsi], xmm0
0x14004a6b2  mov     [rsi+10h], rax
0x14004a6b6  mov     eax, [r15+16Ch]
0x14004a6bd  mov     [rsi], eax
0x14004a6bf  mov     eax, [r15+170h]
0x14004a6c6  mov     [rsi+8], eax
0x14004a6c9  movzx   eax, byte ptr [r15+122h]
0x14004a6d1  mov     [rsi+10h], eax
0x14004a6d4  movzx   eax, word ptr [r15+120h]
0x14004a6dc  mov     [rsi+14h], eax
0x14004a6df  add     r14d, 0FFFFFFE8h
0x14004a6e3  jmp     loc_14004A78B
0x14004a6e8  mov     rdx, r15
0x14004a6eb  mov     rcx, r12
0x14004a6ee  call    FatAcquireSharedVcb
0x14004a6f3  test    al, al
0x14004a6f5  jnz     short loc_14004A723
0x14004a6f7  mov     rdx, r13; Context2
0x14004a6fa  mov     rcx, r12; Context1
0x14004a6fd  call    FatFsdPostRequest
0x14004a702  mov     edi, eax
0x14004a704  mov     [rsp+78h+var_54], eax
0x14004a708  xor     r12d, r12d
0x14004a70b  mov     [rsp+78h+arg_0], r12
0x14004a713  xor     r13d, r13d
0x14004a716  mov     [rsp+78h+arg_8], r13
0x14004a71e  jmp     loc_14004A7A6
0x14004a723  mov     [rsp+78h+var_58], 1
0x14004a728  xorps   xmm0, xmm0
0x14004a72b  xor     eax, eax
0x14004a72d  movups  xmmword ptr [rsi], xmm0
0x14004a730  mov     [rsi+10h], rax
0x14004a734  mov     rax, [r15+0C0h]
0x14004a73b  mov     ecx, [rax+18h]
0x14004a73e  mov     [rsi+8], ecx
0x14004a741  add     r14d, 0FFFFFFEEh
0x14004a745  mov     [rsp+78h+arg_10], r14d
0x14004a74d  mov     rax, [r15+0C0h]
0x14004a754  movzx   ecx, word ptr [rax+6]
0x14004a758  cmp     r14d, ecx
0x14004a75b  sbb     edi, edi
0x14004a75d  and     edi, 80000005h
0x14004a763  mov     eax, ecx
0x14004a765  cmp     r14d, ecx
0x14004a768  cmovb   eax, r14d
0x14004a76c  mov     ebx, eax
0x14004a76e  mov     [rsi+0Ch], ecx
0x14004a771  mov     r8d, eax; Size
0x14004a774  mov     rdx, [r15+0C0h]
0x14004a77b  add     rdx, 20h ; ' '; Src
0x14004a77f  lea     rcx, [rsi+12h]; void *
0x14004a783  call    memmove
0x14004a788  sub     r14d, ebx
0x14004a78b  mov     [rsp+78h+arg_10], r14d
0x14004a793  mov     [rsp+78h+var_54], edi
0x14004a797  mov     rax, [rsp+78h+var_40]
0x14004a79c  mov     eax, [rax+8]
0x14004a79f  sub     eax, r14d
0x14004a7a2  mov     [r13+38h], rax
0x14004a7a6  cmp     [rsp+78h+var_58], 0
0x14004a7ab  jz      short loc_14004A7C0
0x14004a7ad  lea     rcx, [r15+208h]; Resource
0x14004a7b4  call    cs:__imp_ExReleaseResourceLite
0x14004a7bb  nop     dword ptr [rax+rax+00h]
0x14004a7c0  mov     r8d, edi
0x14004a7c3  mov     rdx, r13; Irp
0x14004a7c6  mov     rcx, r12; Entry
0x14004a7c9  call    FatCompleteRequest_Real
0x14004a7ce  mov     eax, edi
0x14004a7d0  add     rsp, 40h
0x14004a7d4  pop     r15
0x14004a7d6  pop     r14
0x14004a7d8  pop     r13
0x14004a7da  pop     r12
0x14004a7dc  pop     rdi
0x14004a7dd  pop     rsi
0x14004a7de  pop     rbx
0x14004a7df  retn
0x14005feb0  push    rbx
0x14005feb2  push    rbp
0x14005feb3  sub     rsp, 28h
0x14005feb7  mov     rbp, rdx
0x14005feba  movzx   ebx, cl
0x14005febd  cmp     byte ptr [rbp+20h], 0
0x14005fec1  jz      short loc_14005FEDE
0x14005fec3  mov     rcx, [rbp+98h]
0x14005feca  add     rcx, 208h; Resource
0x14005fed1  call    cs:__imp_ExReleaseResourceLite
0x14005fed8  nop     dword ptr [rax+rax+00h]
0x14005fedd  nop
0x14005fede  mov     eax, ebx
0x14005fee0  test    bl, bl
0x14005fee2  jnz     short loc_14005FEFC
0x14005fee4  mov     r8d, [rbp+24h]
0x14005fee8  mov     rdx, [rbp+88h]; Irp
0x14005feef  mov     rcx, [rbp+80h]; Entry
0x14005fef6  call    FatCompleteRequest_Real
0x14005fefb  nop
0x14005fefc  add     rsp, 28h
0x14005ff00  pop     rbp
0x14005ff01  pop     rbx
0x14005ff02  retn
```
