# FatGetVolumeBitmap

- ea: `0x14003fcfc`
- end: `0x14003ffed`
- name: `FatGetVolumeBitmap`
- size: `753`
- prototype: `__int64 __fastcall(_DWORD *Entry, PIRP Irp)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140042ac0`

## callees

- `0x14000c260`
- `0x140020008`
- `0x14002006c`
- `0x140020168`
- `0x1400216f4`
- `0x14002d5a8`
- `0x140038eb4`
- `0x14003d880`
- `0x14003fcfc`
- `0x1400466c8`
- `0x140049fa8`

## import_xrefs

- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14003ff2f`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14003ff52`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14003ff7a`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14003ff9d`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14003ff2f`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14003ff52`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14003ff7a`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14003ff9d`
- `ntoskrnl!ProbeForWrite` at `0x14003fdb7`
- `ntoskrnl!ProbeForWrite` at `0x14003fdb7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003fef8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ed79`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003fef8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ed79`
- `ntoskrnl!ExRaiseStatus` at `0x14003ff68`
- `ntoskrnl!ExRaiseStatus` at `0x14003ffb3`
- `ntoskrnl!ExRaiseStatus` at `0x14003ff68`
- `ntoskrnl!ExRaiseStatus` at `0x14003ffb3`

## pseudocode

```c
__int64 __fastcall FatGetVolumeBitmap(_DWORD *Entry, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r14
  __int64 v5; // rcx
  unsigned int Options; // ebx
  unsigned int Length; // r13d
  ULONG *v8; // rax
  __int64 v9; // r15
  unsigned int v10; // r12d
  unsigned __int64 v11; // rbx
  unsigned int v12; // ebx
  unsigned int v13; // ecx
  unsigned int v14; // eax
  unsigned int v15; // r13d
  ULONG *v16; // rax
  _QWORD *v17; // rcx
  void *v18; // rcx
  void *v19; // rdx
  unsigned int v21; // ebx
  ULONG *v22; // [rsp+40h] [rbp-48h]
  int v23[2]; // [rsp+48h] [rbp-40h] BYREF
  __int64 v24; // [rsp+A0h] [rbp+18h] BYREF
  __int64 v25; // [rsp+A8h] [rbp+20h] BYREF

  *(_QWORD *)v23 = 0;
  v25 = 0;
  v24 = 0;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  Entry[17] |= 2u;
  if ( (unsigned int)FatDecodeFileObject(CurrentStackLocation->FileObject, v23, &v25, &v24) != 4
    || !v24
    || (*(_DWORD *)(v24 + 4) & 0x20000) == 0 )
  {
    goto LABEL_29;
  }
  Options = CurrentStackLocation->Parameters.Create.Options;
  Length = CurrentStackLocation->Parameters.Read.Length;
  v8 = (ULONG *)FatMapUserBuffer(v5, Irp);
  v22 = v8;
  if ( Options < 8 || Length < 0x18 )
  {
    v21 = -1073741789;
LABEL_30:
    FatCompleteRequest_Real(Entry, Irp);
    return v21;
  }
  v9 = *(_QWORD *)v23;
  v10 = *(_DWORD *)(*(_QWORD *)v23 + 364LL);
  if ( Irp->RequestorMode )
    ProbeForWrite(v8, Length, 1u);
  v11 = Irp->RequestorMode
      ? RtlReadULong64FromUser(CurrentStackLocation->Parameters.CreatePipe.Parameters)
      : *(_QWORD *)CurrentStackLocation->Parameters.CreatePipe.Parameters;
  if ( v11 >= v10 )
  {
LABEL_29:
    v21 = -1073741811;
    goto LABEL_30;
  }
  v12 = v11 & 0xFFFFFFF8;
  FatAcquireExclusiveVcb_Real(Entry, v9, 0);
  LODWORD(v24) = v10 - v12;
  v14 = (v10 - v12 + 7) >> 3;
  v15 = Length - 16;
  v13 = v15;
  if ( v15 >= v14 )
    v15 = (v10 - v12 + 7) >> 3;
  LODWORD(v25) = v13 < v14 ? 0x80000005 : 0;
  FatQuickVerifyVcb(Entry, v9);
  if ( Irp->RequestorMode )
  {
    RtlWriteULong64ToUser(v22, v12);
    v16 = v22;
  }
  else
  {
    v16 = v22;
    *(_QWORD *)v22 = v12;
  }
  v17 = v16 + 2;
  if ( Irp->RequestorMode )
    RtlWriteULong64ToUser(v17, (unsigned int)v24);
  else
    *v17 = (unsigned int)v24;
  v18 = v22 + 4;
  if ( *(_DWORD *)(v9 + 216) == 1 )
  {
    v19 = (void *)(((unsigned __int64)v12 >> 3) + *(_QWORD *)(v9 + 456));
    if ( Irp->RequestorMode )
      RtlCopyToUser(v18, v19, v15);
    else
      RtlCopyVolatileMemory(v18, v19, v15);
  }
  else
  {
    if ( v12 + 8 * v15 <= v10 )
      v10 = v12 + 8 * v15;
    FatExamineFatEntries((__int64)Entry, v9, v12 + 2, v10 + 1, 0, 0, v22 + 4);
  }
  ExReleaseResourceLite((PERESOURCE)(v9 + 520));
  Irp->IoStatus.Information = v15 + 16;
  FatCompleteRequest_Real(Entry, Irp);
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x14003fcfc  mov     rax, rsp
0x14003fcff  mov     [rax+10h], rdx
0x14003fd03  mov     [rax+8], rcx
0x14003fd07  push    rbx
0x14003fd08  push    rsi
0x14003fd09  push    rdi
0x14003fd0a  push    r12
0x14003fd0c  push    r13
0x14003fd0e  push    r14
0x14003fd10  push    r15
0x14003fd12  sub     rsp, 50h
0x14003fd16  mov     rdi, rdx
0x14003fd19  mov     rsi, rcx
0x14003fd1c  xor     ebx, ebx
0x14003fd1e  mov     [rax-40h], rbx
0x14003fd22  mov     [rax+20h], rbx
0x14003fd26  mov     [rax+18h], rbx
0x14003fd2a  mov     r14, [rdx+0B8h]
0x14003fd31  or      dword ptr [rcx+44h], 2
0x14003fd35  lea     r9, [rax+18h]
0x14003fd39  lea     r8, [rax+20h]
0x14003fd3d  lea     rdx, [rax-40h]
0x14003fd41  mov     rcx, [r14+30h]
0x14003fd45  call    FatDecodeFileObject
0x14003fd4a  cmp     eax, 4
0x14003fd4d  jnz     loc_14003FFC7
0x14003fd53  mov     rax, [rsp+88h+arg_10]
0x14003fd5b  test    rax, rax
0x14003fd5e  jz      loc_14003FFC7
0x14003fd64  test    dword ptr [rax+4], 20000h
0x14003fd6b  jz      loc_14003FFC7
0x14003fd71  mov     ebx, [r14+10h]
0x14003fd75  mov     r13d, [r14+8]
0x14003fd79  mov     rdx, rdi
0x14003fd7c  call    FatMapUserBuffer
0x14003fd81  mov     [rsp+88h+var_48], rax
0x14003fd86  cmp     ebx, 8
0x14003fd89  jb      loc_14003FFC0
0x14003fd8f  cmp     r13d, 18h
0x14003fd93  jb      loc_14003FFC0
0x14003fd99  mov     r15, qword ptr [rsp+88h+var_40]
0x14003fd9e  mov     r12d, [r15+16Ch]
0x14003fda5  cmp     byte ptr [rdi+40h], 0
0x14003fda9  jz      short loc_14003FDC3
0x14003fdab  mov     edx, r13d; Length
0x14003fdae  mov     r8d, 1; Alignment
0x14003fdb4  mov     rcx, rax; Address
0x14003fdb7  call    cs:__imp_ProbeForWrite
0x14003fdbe  nop     dword ptr [rax+rax+00h]
0x14003fdc3  mov     rbx, [r14+20h]
0x14003fdc7  cmp     byte ptr [rdi+40h], 0
0x14003fdcb  jz      short loc_14003FDDA
0x14003fdcd  mov     rcx, rbx
0x14003fdd0  call    RtlReadULong64FromUser
0x14003fdd5  mov     rbx, rax
0x14003fdd8  jmp     short loc_14003FDDD
0x14003fdda  mov     rbx, [rbx]
0x14003fddd  mov     rax, rbx
0x14003fde0  sar     rax, 20h
0x14003fde4  test    eax, eax
0x14003fde6  jnz     loc_14003FFC7
0x14003fdec  cmp     ebx, r12d
0x14003fdef  jnb     loc_14003FFC7
0x14003fdf5  and     ebx, 0FFFFFFF8h
0x14003fdf8  xor     r8d, r8d
0x14003fdfb  mov     rdx, r15
0x14003fdfe  mov     rcx, rsi
0x14003fe01  call    FatAcquireExclusiveVcb_Real
0x14003fe06  lea     ecx, [r13-10h]
0x14003fe0a  mov     eax, r12d
0x14003fe0d  sub     eax, ebx
0x14003fe0f  mov     dword ptr [rsp+88h+arg_10], eax
0x14003fe16  add     eax, 7
0x14003fe19  shr     eax, 3
0x14003fe1c  mov     r13d, ecx
0x14003fe1f  cmp     ecx, eax
0x14003fe21  cmovnb  r13d, eax
0x14003fe25  sbb     eax, eax
0x14003fe27  and     eax, 80000005h
0x14003fe2c  mov     dword ptr [rsp+88h+arg_18], eax
0x14003fe33  mov     rdx, r15
0x14003fe36  mov     rcx, rsi
0x14003fe39  call    FatQuickVerifyVcb
0x14003fe3e  mov     r14d, ebx
0x14003fe41  cmp     byte ptr [rdi+40h], 0
0x14003fe45  jz      short loc_14003FE5B
0x14003fe47  mov     edx, r14d
0x14003fe4a  mov     rcx, [rsp+88h+var_48]
0x14003fe4f  call    RtlWriteULong64ToUser
0x14003fe54  mov     rax, [rsp+88h+var_48]
0x14003fe59  jmp     short loc_14003FE63
0x14003fe5b  mov     rax, [rsp+88h+var_48]
0x14003fe60  mov     [rax], r14
0x14003fe63  lea     rcx, [rax+8]
0x14003fe67  cmp     byte ptr [rdi+40h], 0
0x14003fe6b  jz      short loc_14003FE7B
0x14003fe6d  mov     edx, dword ptr [rsp+88h+arg_10]
0x14003fe74  call    RtlWriteULong64ToUser
0x14003fe79  jmp     short loc_14003FE85
0x14003fe7b  mov     eax, dword ptr [rsp+88h+arg_10]
0x14003fe82  mov     [rcx], rax
0x14003fe85  mov     rcx, [rsp+88h+var_48]
0x14003fe8a  add     rcx, 10h; void *
0x14003fe8e  cmp     dword ptr [r15+0D8h], 1
0x14003fe96  jnz     short loc_14003FEBE
0x14003fe98  shr     r14, 3
0x14003fe9c  mov     rax, [r15+1C8h]
0x14003fea3  lea     rdx, [r14+rax]; Src
0x14003fea7  mov     r8d, r13d; Size
0x14003feaa  cmp     byte ptr [rdi+40h], 0
0x14003feae  jz      short loc_14003FEB7
0x14003feb0  call    RtlCopyToUser
0x14003feb5  jmp     short loc_14003FEF1
0x14003feb7  call    RtlCopyVolatileMemory
0x14003febc  jmp     short loc_14003FEF1
0x14003febe  lea     eax, [rbx+r13*8]
0x14003fec2  cmp     eax, r12d
0x14003fec5  cmovbe  r12d, eax
0x14003fec9  lea     r9d, [r12+1]; int
0x14003fece  lea     r8d, [rbx+2]; int
0x14003fed2  mov     [rsp+88h+BitMapBuffer], rcx; BitMapBuffer
0x14003fed7  mov     [rsp+88h+var_60], 0; __int64
0x14003fee0  mov     [rsp+88h+var_68], 0; char
0x14003fee5  mov     rdx, r15; int
0x14003fee8  mov     rcx, rsi; int
0x14003feeb  call    FatExamineFatEntries
0x14003fef0  nop
0x14003fef1  lea     rcx, [r15+208h]; Resource
0x14003fef8  call    cs:__imp_ExReleaseResourceLite
0x14003feff  nop     dword ptr [rax+rax+00h]
0x14003ff04  lea     edx, [r13+10h]
0x14003ff08  mov     [rdi+38h], rdx
0x14003ff0c  mov     r8d, dword ptr [rsp+88h+arg_18]
0x14003ff14  mov     rdx, rdi; Irp
0x14003ff17  mov     rcx, rsi; Entry
0x14003ff1a  call    FatCompleteRequest_Real
0x14003ff1f  mov     eax, dword ptr [rsp+88h+arg_18]
0x14003ff26  jmp     loc_14003FFDC
0x14003ff2b  mov     ebx, eax
0x14003ff2d  mov     ecx, eax; Exception
0x14003ff2f  call    cs:__imp_FsRtlIsNtstatusExpected
0x14003ff36  nop     dword ptr [rax+rax+00h]
0x14003ff3b  mov     edx, 0C00000E8h
0x14003ff40  test    al, al
0x14003ff42  cmovnz  edx, ebx
0x14003ff45  mov     rcx, [rsp+88h+arg_0]
0x14003ff4d  mov     [rcx+48h], edx
0x14003ff50  mov     ecx, ebx; Exception
0x14003ff52  call    cs:__imp_FsRtlIsNtstatusExpected
0x14003ff59  nop     dword ptr [rax+rax+00h]
0x14003ff5e  mov     ecx, 0C00000E8h
0x14003ff63  test    al, al
0x14003ff65  cmovnz  ecx, ebx; Status
0x14003ff68  call    cs:__imp_ExRaiseStatus
0x14003ff75  nop
0x14003ff76  mov     ebx, eax
0x14003ff78  mov     ecx, eax; Exception
0x14003ff7a  call    cs:__imp_FsRtlIsNtstatusExpected
0x14003ff81  nop     dword ptr [rax+rax+00h]
0x14003ff86  mov     edx, 0C00000E8h
0x14003ff8b  test    al, al
0x14003ff8d  cmovnz  edx, ebx
0x14003ff90  mov     rcx, [rsp+88h+arg_0]
0x14003ff98  mov     [rcx+48h], edx
0x14003ff9b  mov     ecx, ebx; Exception
0x14003ff9d  call    cs:__imp_FsRtlIsNtstatusExpected
0x14003ffa4  nop     dword ptr [rax+rax+00h]
0x14003ffa9  mov     ecx, 0C00000E8h
0x14003ffae  test    al, al
0x14003ffb0  cmovnz  ecx, ebx; Status
0x14003ffb3  call    cs:__imp_ExRaiseStatus
0x14003ffc0  mov     ebx, 0C0000023h
0x14003ffc5  jmp     short loc_14003FFCC
0x14003ffc7  mov     ebx, 0C000000Dh
0x14003ffcc  mov     r8d, ebx
0x14003ffcf  mov     rdx, rdi; Irp
0x14003ffd2  mov     rcx, rsi; Entry
0x14003ffd5  call    FatCompleteRequest_Real
0x14003ffda  mov     eax, ebx
0x14003ffdc  add     rsp, 50h
0x14003ffe0  pop     r15
0x14003ffe2  pop     r14
0x14003ffe4  pop     r13
0x14003ffe6  pop     r12
0x14003ffe8  pop     rdi
0x14003ffe9  pop     rsi
0x14003ffea  pop     rbx
0x14003ffeb  retn
0x14005ed27  push    rbp
0x14005ed29  sub     rsp, 40h
0x14005ed2d  mov     rbp, rdx
0x14005ed30  xor     eax, eax
0x14005ed32  mov     rcx, [rbp+98h]
0x14005ed39  cmp     [rcx+40h], al
0x14005ed3c  setnz   al
0x14005ed3f  add     rsp, 40h
0x14005ed43  pop     rbp
0x14005ed44  retn
0x14005ed46  push    rbp
0x14005ed48  sub     rsp, 40h
0x14005ed4c  mov     rbp, rdx
0x14005ed4f  xor     eax, eax
0x14005ed51  mov     rcx, [rbp+98h]
0x14005ed58  cmp     [rcx+40h], al
0x14005ed5b  setnz   al
0x14005ed5e  add     rsp, 40h
0x14005ed62  pop     rbp
0x14005ed63  retn
0x14005ed65  push    rbp
0x14005ed67  sub     rsp, 40h
0x14005ed6b  mov     rbp, rdx
0x14005ed6e  mov     rcx, [rbp+48h]
0x14005ed72  add     rcx, 208h; Resource
0x14005ed79  call    cs:__imp_ExReleaseResourceLite
0x14005ed80  nop     dword ptr [rax+rax+00h]
0x14005ed85  nop
0x14005ed86  add     rsp, 40h
0x14005ed8a  pop     rbp
0x14005ed8b  retn
```
