# FatSetEncryption

- ea: `0x140037ab0`
- end: `0x140038056`
- name: `FatSetEncryption`
- size: `1446`
- prototype: `__int64 __fastcall(int, PIRP Irp)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140042ac0`

## callees

- `0x140002ea0`
- `0x140002fd4`
- `0x1400200a8`
- `0x140020120`
- `0x14002486c`
- `0x14002d5a8`
- `0x140034054`
- `0x140037ab0`
- `0x140038eb4`
- `0x14003d880`
- `0x1400465f4`
- `0x1400466c8`

## import_xrefs

- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140037d8c`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140037daf`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140037fe0`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140038003`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140037d8c`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140037daf`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140037fe0`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140038003`
- `ntoskrnl!ProbeForRead` at `0x140037bc2`
- `ntoskrnl!ProbeForRead` at `0x140037bc2`
- `ntoskrnl!ProbeForWrite` at `0x140037c15`
- `ntoskrnl!ProbeForWrite` at `0x140037c15`
- `ntoskrnl!ExReleaseResourceLite` at `0x140037f81`
- `ntoskrnl!ExReleaseResourceLite` at `0x140037f91`
- `ntoskrnl!ExReleaseResourceLite` at `0x140037fb6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ddbc`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ddd6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ddfa`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005de56`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005de77`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005de9b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005dee0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005df01`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005df25`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005df6a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005df8b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005dfaf`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e002`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e01a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e03d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e082`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e09a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e0bd`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e0fb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e113`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e136`
- `ntoskrnl!ExReleaseResourceLite` at `0x140037f81`
- `ntoskrnl!ExReleaseResourceLite` at `0x140037f91`
- `ntoskrnl!ExReleaseResourceLite` at `0x140037fb6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ddbc`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ddd6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ddfa`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005de56`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005de77`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005de9b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005dee0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005df01`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005df25`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005df6a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005df8b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005dfaf`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e002`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e01a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e03d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e082`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e09a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e0bd`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e0fb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e113`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e136`
- `ntoskrnl!ExRaiseStatus` at `0x140037dc5`
- `ntoskrnl!ExRaiseStatus` at `0x140038019`
- `ntoskrnl!ExRaiseStatus` at `0x140037dc5`
- `ntoskrnl!ExRaiseStatus` at `0x140038019`

## pseudocode

```c
__int64 __fastcall FatSetEncryption(_DWORD *a1, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r13
  unsigned int v5; // ebx
  IRP *v6; // rdx
  _DWORD *p_NamedPipeType; // r14
  SIZE_T v8; // r12
  __int64 v9; // rax
  _BYTE *v10; // r15
  SIZE_T Length; // rbx
  int v12; // r12d
  unsigned int ULongFromUser; // r14d
  __int64 v14; // rbx
  __int64 v15; // rdx
  __int64 v16; // rdx
  int v17; // ecx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  int v21; // r15d
  char v23; // [rsp+90h] [rbp-88h]
  char v24; // [rsp+91h] [rbp-87h]
  char v25; // [rsp+93h] [rbp-85h]
  __int64 v26; // [rsp+98h] [rbp-80h] BYREF
  __int64 v27; // [rsp+A0h] [rbp-78h] BYREF
  int v28; // [rsp+A8h] [rbp-70h]
  __int64 v29; // [rsp+B0h] [rbp-68h] BYREF
  int v30; // [rsp+B8h] [rbp-60h]
  unsigned int v31; // [rsp+BCh] [rbp-5Ch]
  ULONG Options; // [rsp+C0h] [rbp-58h]
  struct _IO_STACK_LOCATION *v33; // [rsp+C8h] [rbp-50h]
  _DWORD *v34; // [rsp+D0h] [rbp-48h]

  v28 = 0;
  v27 = 0;
  v26 = 0;
  v29 = 0;
  v31 = 0;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v23 = 0;
  v25 = 0;
  a1[17] |= 2u;
  if ( (unsigned int)FatDecodeFileObject(CurrentStackLocation->FileObject, &v27, &v26, &v29) - 2 > 1 )
    goto LABEL_62;
  if ( (*(_DWORD *)(v27 + 200) & 0x400000) == 0 )
  {
    v5 = -1073741808;
LABEL_63:
    v6 = Irp;
    goto LABEL_64;
  }
  v6 = Irp;
  if ( (*(_DWORD *)(v27 + 200) & 0x4000) != 0 )
  {
    v5 = -1073741662;
LABEL_64:
    FatCompleteRequest_Real(a1, v6);
    return v5;
  }
  p_NamedPipeType = &CurrentStackLocation->Parameters.CreatePipe.Parameters->NamedPipeType;
  v34 = p_NamedPipeType;
  Options = CurrentStackLocation->Parameters.Create.Options;
  v8 = Options;
  v9 = FatMapUserBuffer(v27, Irp);
  v10 = (_BYTE *)v9;
  if ( (unsigned int)v8 < 8
    || (v33 = CurrentStackLocation, Length = CurrentStackLocation->Parameters.Read.Length, v9) && !(_DWORD)Length )
  {
    v5 = -1073741789;
    goto LABEL_63;
  }
  if ( Irp->RequestorMode )
    ProbeForRead(p_NamedPipeType, v8, 1u);
  v12 = 0;
  if ( Irp->RequestorMode )
    ULongFromUser = RtlReadULongFromUser(p_NamedPipeType);
  else
    ULongFromUser = *p_NamedPipeType;
  v31 = ULongFromUser;
  if ( v10 )
  {
    if ( Irp->RequestorMode && (ProbeForWrite(v10, Length, 1u), Irp->RequestorMode) )
      RtlWriteUCharToUser(v10, 0);
    else
      *v10 = 0;
  }
  Irp->IoStatus.Information = 0;
  if ( ULongFromUser > 4 )
  {
LABEL_62:
    v5 = -1073741811;
    goto LABEL_63;
  }
  v30 = 0;
  v24 = FatAcquireExclusiveVcb_Real(a1, v27, 0);
  v14 = v26;
  FatAcquireExclusiveFcb(a1, v26);
  v15 = *(_QWORD *)(v14 + 176);
  if ( v15 )
  {
    FatAcquireExclusiveFcb(a1, v15);
    v16 = 1;
    v23 = 1;
  }
  else
  {
    v16 = 1;
  }
  v17 = *(_DWORD *)(v14 + 192);
  if ( (v17 & 0x20000) != 0 )
    v12 = 2;
  v30 = v12;
  if ( (v17 & 0x40000) != 0 )
  {
    v12 |= 1u;
    v30 = v12;
  }
  if ( ULongFromUser == 3 )
  {
    v17 |= 0x40000u;
  }
  else
  {
    if ( ULongFromUser != 4 )
      goto LABEL_32;
    v17 &= ~0x40000u;
  }
  *(_DWORD *)(v14 + 192) = v17;
LABEL_32:
  if ( ((ULongFromUser - 1) & 0xFFFFFFFD) != 0 )
  {
    if ( ((ULongFromUser - 2) & 0xFFFFFFFD) == 0 )
    {
      if ( (v17 & 0x20000) != 0 )
      {
        *(_DWORD *)(v14 + 192) = v17 & 0xFFFDFFFF;
        CurrentStackLocation->FileObject->Flags |= 0x2000u;
        v25 = 1;
        FatUpdateDirentFromFcb((int)a1, 1);
      }
      if ( v10 )
      {
        if ( Irp->RequestorMode )
        {
          LOBYTE(v16) = 1;
          RtlWriteUCharToUser(v10, v16);
        }
        else
        {
          *v10 = 1;
        }
        Irp->IoStatus.Information = 1;
      }
    }
  }
  else
  {
    if ( (v17 & 0x20000) == 0 )
    {
      *(_DWORD *)(v14 + 192) = v17 | 0x20000;
      CurrentStackLocation->FileObject->Flags |= 0x2000u;
      v25 = 1;
      FatUpdateDirentFromFcb((int)a1, 1);
    }
    if ( *(_QWORD *)(v14 + 144) )
    {
      EfsCleanUpCallback(v14 + 144);
      *(_QWORD *)(v14 + 144) = 0;
    }
  }
  v21 = EfsFileSystemControlCallback((_DWORD)v34, Options, 0, 0, v12);
  v28 = v21;
  if ( v21 >= 0 || !v25 )
    goto LABEL_56;
  if ( ((ULongFromUser - 1) & 0xFFFFFFFD) != 0 )
  {
    if ( ((ULongFromUser - 2) & 0xFFFFFFFD) != 0 )
      goto LABEL_52;
    *(_DWORD *)(v14 + 192) |= 0x20000u;
  }
  else
  {
    *(_DWORD *)(v14 + 192) &= ~0x20000u;
  }
  CurrentStackLocation->FileObject->Flags |= 0x2000u;
  FatUpdateDirentFromFcb((int)a1, 1);
LABEL_52:
  if ( ULongFromUser == 3 )
  {
    *(_DWORD *)(v14 + 192) &= ~0x40000u;
  }
  else if ( ULongFromUser == 4 )
  {
    *(_DWORD *)(v14 + 192) |= 0x40000u;
  }
LABEL_56:
  FatUnpinRepinnedBcbs(a1, v18, v19, v20);
  if ( v23 )
    ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(v14 + 176) + 8LL));
  ExReleaseResourceLite(*(PERESOURCE *)(v14 + 8));
  if ( v24 )
    ExReleaseResourceLite((PERESOURCE)(v27 + 520));
  FatCompleteRequest_Real(a1, Irp);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x140037ab0  mov     r11, rsp
0x140037ab3  mov     [r11+10h], rdx
0x140037ab7  mov     [r11+8], rcx
0x140037abb  push    rbx
0x140037abc  push    rsi
0x140037abd  push    rdi
0x140037abe  push    r12
0x140037ac0  push    r13
0x140037ac2  push    r14
0x140037ac4  push    r15
0x140037ac6  sub     rsp, 0E0h
0x140037acd  mov     rdi, rdx
0x140037ad0  mov     rsi, rcx
0x140037ad3  xor     eax, eax
0x140037ad5  mov     [r11-70h], eax
0x140037ad9  mov     [r11-78h], rax
0x140037add  mov     [r11-80h], rax
0x140037ae1  mov     [r11-68h], rax
0x140037ae5  mov     [r11-5Ch], eax
0x140037ae9  mov     r13, [rdx+0B8h]
0x140037af0  mov     [rsp+118h+var_86], al
0x140037af7  mov     [rsp+118h+var_88], al
0x140037afe  mov     [rsp+118h+var_87], al
0x140037b05  mov     [r11+18h], al
0x140037b09  mov     [rsp+118h+var_85], al
0x140037b10  or      dword ptr [rcx+44h], 2
0x140037b14  lea     r9, [r11-68h]
0x140037b18  lea     r8, [r11-80h]
0x140037b1c  lea     rdx, [r11-78h]
0x140037b20  mov     rcx, [r13+30h]
0x140037b24  call    FatDecodeFileObject
0x140037b29  add     eax, 0FFFFFFFEh
0x140037b2c  cmp     eax, 1
0x140037b2f  ja      loc_14003802D
0x140037b35  mov     rcx, [rsp+118h+var_78]
0x140037b3d  mov     eax, [rcx+0C8h]
0x140037b43  bt      eax, 16h
0x140037b47  jb      short loc_140037B53
0x140037b49  mov     ebx, 0C0000010h
0x140037b4e  jmp     loc_140038032
0x140037b53  mov     eax, [rcx+0C8h]
0x140037b59  mov     rdx, rdi
0x140037b5c  bt      eax, 0Eh
0x140037b60  jnb     short loc_140037B6C
0x140037b62  mov     ebx, 0C00000A2h
0x140037b67  jmp     loc_140038035
0x140037b6c  mov     r14, [r13+20h]
0x140037b70  mov     [rsp+118h+var_48], r14
0x140037b78  mov     r12d, [r13+10h]
0x140037b7c  mov     [rsp+118h+var_58], r12d
0x140037b84  call    FatMapUserBuffer
0x140037b89  mov     r15, rax
0x140037b8c  cmp     r12d, 8
0x140037b90  jb      loc_140038026
0x140037b96  mov     [rsp+118h+var_50], r13
0x140037b9e  mov     ebx, [r13+8]
0x140037ba2  test    rax, rax
0x140037ba5  jz      short loc_140037BB0
0x140037ba7  cmp     ebx, 1
0x140037baa  jb      loc_140038026
0x140037bb0  cmp     byte ptr [rdi+40h], 0
0x140037bb4  jz      short loc_140037BCE
0x140037bb6  mov     rdx, r12; Length
0x140037bb9  mov     r8d, 1; Alignment
0x140037bbf  mov     rcx, r14; Address
0x140037bc2  call    cs:__imp_ProbeForRead
0x140037bc9  nop     dword ptr [rax+rax+00h]
0x140037bce  xor     r12d, r12d
0x140037bd1  cmp     [rdi+40h], r12b
0x140037bd5  jz      short loc_140037BEB
0x140037bd7  mov     rcx, r14
0x140037bda  call    RtlReadULongFromUser
0x140037bdf  mov     r14d, eax
0x140037be2  mov     [rsp+118h+arg_18], eax
0x140037be9  jmp     short loc_140037BF6
0x140037beb  mov     r14d, [r14]
0x140037bee  mov     [rsp+118h+arg_18], r14d
0x140037bf6  mov     [rsp+118h+var_5C], r14d
0x140037bfe  test    r15, r15
0x140037c01  jz      short loc_140037C36
0x140037c03  cmp     [rdi+40h], r12b
0x140037c07  jz      short loc_140037C33
0x140037c09  mov     rdx, rbx; Length
0x140037c0c  mov     r8d, 1; Alignment
0x140037c12  mov     rcx, r15; Address
0x140037c15  call    cs:__imp_ProbeForWrite
0x140037c1c  nop     dword ptr [rax+rax+00h]
0x140037c21  cmp     [rdi+40h], r12b
0x140037c25  jz      short loc_140037C33
0x140037c27  xor     edx, edx
0x140037c29  mov     rcx, r15
0x140037c2c  call    RtlWriteUCharToUser
0x140037c31  jmp     short loc_140037C36
0x140037c33  mov     [r15], r12b
0x140037c36  mov     [rdi+38h], r12
0x140037c3a  cmp     r14d, 4
0x140037c3e  ja      loc_14003802D
0x140037c44  mov     [rsp+118h+var_60], r12d
0x140037c4c  xor     r8d, r8d
0x140037c4f  mov     rdx, [rsp+118h+var_78]
0x140037c57  mov     rcx, rsi
0x140037c5a  call    FatAcquireExclusiveVcb_Real
0x140037c5f  mov     [rsp+118h+var_87], al
0x140037c66  mov     rbx, [rsp+118h+var_80]
0x140037c6e  mov     rdx, rbx
0x140037c71  mov     rcx, rsi
0x140037c74  call    FatAcquireExclusiveFcb
0x140037c79  mov     [rsp+118h+var_86], 1
0x140037c81  mov     rdx, [rbx+0B0h]
0x140037c88  test    rdx, rdx
0x140037c8b  jz      short loc_140037CA3
0x140037c8d  mov     rcx, rsi
0x140037c90  call    FatAcquireExclusiveFcb
0x140037c95  mov     edx, 1
0x140037c9a  mov     [rsp+118h+var_88], dl
0x140037ca1  jmp     short loc_140037CA8
0x140037ca3  mov     edx, 1
0x140037ca8  mov     ecx, [rbx+0C0h]
0x140037cae  mov     r9d, 20000h
0x140037cb4  test    r9d, ecx
0x140037cb7  mov     eax, 2
0x140037cbc  cmovnz  r12d, eax
0x140037cc0  mov     [rsp+118h+var_60], r12d
0x140037cc8  mov     eax, 40000h
0x140037ccd  test    eax, ecx
0x140037ccf  jz      short loc_140037CDC
0x140037cd1  or      r12d, edx
0x140037cd4  mov     [rsp+118h+var_60], r12d
0x140037cdc  cmp     r14d, 3
0x140037ce0  jnz     short loc_140037CE6
0x140037ce2  or      ecx, eax
0x140037ce4  jmp     short loc_140037CF0
0x140037ce6  cmp     r14d, 4
0x140037cea  jnz     short loc_140037CF6
0x140037cec  btr     ecx, 12h
0x140037cf0  mov     [rbx+0C0h], ecx
0x140037cf6  lea     eax, [r14-1]
0x140037cfa  mov     r8d, 0FFFFFFFDh
0x140037d00  test    r8d, eax
0x140037d03  jz      loc_140037DD2
0x140037d09  lea     eax, [r14-2]
0x140037d0d  test    r8d, eax
0x140037d10  jnz     loc_140037E2C
0x140037d16  test    r9d, ecx
0x140037d19  jz      short loc_140037D55
0x140037d1b  btr     ecx, 11h
0x140037d1f  mov     [rbx+0C0h], ecx
0x140037d25  mov     rcx, [r13+30h]
0x140037d29  mov     eax, [rcx+50h]
0x140037d2c  bts     eax, 0Dh
0x140037d30  mov     [rcx+50h], eax
0x140037d33  mov     [rsp+118h+var_85], dl
0x140037d3a  mov     [rsp+118h+var_F8], dl; char
0x140037d3e  mov     r9, [rsp+118h+var_68]
0x140037d46  mov     r8, rbx
0x140037d49  mov     rdx, [r13+30h]
0x140037d4d  mov     rcx, rsi; int
0x140037d50  call    FatUpdateDirentFromFcb
0x140037d55  test    r15, r15
0x140037d58  jz      loc_140037E2C
0x140037d5e  cmp     byte ptr [rdi+40h], 0
0x140037d62  jz      short loc_140037D70
0x140037d64  mov     dl, 1
0x140037d66  mov     rcx, r15
0x140037d69  call    RtlWriteUCharToUser
0x140037d6e  jmp     short loc_140037D74
0x140037d70  mov     byte ptr [r15], 1
0x140037d74  mov     qword ptr [rdi+38h], 1
0x140037d7c  jmp     loc_140037E2C
0x140037d81  mov     ebx, eax
0x140037d83  mov     [rsp+118h+var_70], eax
0x140037d8a  mov     ecx, eax; Exception
0x140037d8c  call    cs:__imp_FsRtlIsNtstatusExpected
0x140037d93  nop     dword ptr [rax+rax+00h]
0x140037d98  mov     edx, 0C00000E8h
0x140037d9d  test    al, al
0x140037d9f  cmovnz  edx, ebx
0x140037da2  mov     rcx, [rsp+118h+arg_0]
0x140037daa  mov     [rcx+48h], edx
0x140037dad  mov     ecx, ebx; Exception
0x140037daf  call    cs:__imp_FsRtlIsNtstatusExpected
0x140037db6  nop     dword ptr [rax+rax+00h]
0x140037dbb  mov     ecx, 0C00000E8h
0x140037dc0  test    al, al
0x140037dc2  cmovnz  ecx, ebx; Status
0x140037dc5  call    cs:__imp_ExRaiseStatus
0x140037dd2  test    r9d, ecx
0x140037dd5  jnz     short loc_140037E10
0x140037dd7  or      ecx, r9d
0x140037dda  mov     [rbx+0C0h], ecx
0x140037de0  mov     rcx, [r13+30h]
0x140037de4  mov     eax, [rcx+50h]
0x140037de7  bts     eax, 0Dh
0x140037deb  mov     [rcx+50h], eax
0x140037dee  mov     [rsp+118h+var_85], dl
0x140037df5  mov     [rsp+118h+var_F8], dl; char
0x140037df9  mov     r9, [rsp+118h+var_68]
0x140037e01  mov     r8, rbx
0x140037e04  mov     rdx, [r13+30h]
0x140037e08  mov     rcx, rsi; int
0x140037e0b  call    FatUpdateDirentFromFcb
0x140037e10  lea     r15, [rbx+90h]
0x140037e17  cmp     qword ptr [r15], 0
0x140037e1b  jz      short loc_140037E2C
0x140037e1d  mov     rcx, r15
0x140037e20  call    EfsCleanUpCallback
0x140037e25  mov     qword ptr [r15], 0
0x140037e2c  mov     ecx, 503h
0x140037e31  movzx   eax, word ptr [rbx]
0x140037e34  sub     ax, cx
0x140037e37  mov     r10d, 1
0x140037e3d  cmp     ax, r10w
0x140037e41  setbe   cl
0x140037e44  mov     rdx, [rsp+118h+var_78]
0x140037e4c  mov     r9d, [rdx+0C8h]
0x140037e53  lea     rax, [rbx+90h]
0x140037e5a  lea     r8, [rdx-1A0h]
0x140037e61  shr     r9d, 0Eh
0x140037e65  and     r9d, r10d
0x140037e68  mov     [rsp+118h+var_98], rax
0x140037e70  lea     rax, [rsp+118h+arg_10]
0x140037e78  mov     [rsp+118h+var_A0], rax
0x140037e7d  mov     [rsp+118h+var_A8], cl
0x140037e81  mov     [rsp+118h+var_B0], rbx
0x140037e86  mov     rax, [rdx+88h]
0x140037e8d  mov     [rsp+118h+var_B8], rax
0x140037e92  mov     [rsp+118h+var_C0], r8
0x140037e97  mov     [rsp+118h+var_C8], rsi
0x140037e9c  mov     rax, [rsi+28h]
0x140037ea0  mov     [rsp+118h+var_D0], rax
0x140037ea5  mov     [rsp+118h+var_D8], rbx
0x140037eaa  mov     eax, [r13+18h]
0x140037eae  mov     [rsp+118h+var_E0], eax
0x140037eb2  mov     [rsp+118h+var_E8], r9d
0x140037eb7  mov     dword ptr [rsp+118h+var_F8], r12d
0x140037ebc  xor     r9d, r9d
0x140037ebf  xor     r8d, r8d
0x140037ec2  mov     edx, [rsp+118h+var_58]
0x140037ec9  mov     rcx, [rsp+118h+var_48]
0x140037ed1  call    EfsFileSystemControlCallback
0x140037ed6  mov     r15d, eax
0x140037ed9  mov     [rsp+118h+var_70], eax
0x140037ee0  nop
0x140037ee1  xor     r12d, r12d
0x140037ee4  test    r15d, r15d
0x140037ee7  jns     short loc_140037F62
0x140037ee9  cmp     [rsp+118h+var_85], r12b
0x140037ef1  jz      short loc_140037F62
0x140037ef3  lea     eax, [r14-1]
0x140037ef7  mov     ecx, 0FFFFFFFDh
0x140037efc  test    ecx, eax
0x140037efe  jz      short loc_140037F12
0x140037f00  lea     eax, [r14-2]
0x140037f04  test    ecx, eax
0x140037f06  jnz     short loc_140037F44
0x140037f08  bts     dword ptr [rbx+0C0h], 11h
0x140037f10  jmp     short loc_140037F1A
0x140037f12  btr     dword ptr [rbx+0C0h], 11h
0x140037f1a  mov     rcx, [r13+30h]
0x140037f1e  mov     eax, [rcx+50h]
0x140037f21  bts     eax, 0Dh
0x140037f25  mov     [rcx+50h], eax
0x140037f28  mov     [rsp+118h+var_F8], 1; char
0x140037f2d  mov     r9, [rsp+118h+var_68]
0x140037f35  mov     r8, rbx
0x140037f38  mov     rdx, [r13+30h]
0x140037f3c  mov     rcx, rsi; int
0x140037f3f  call    FatUpdateDirentFromFcb
0x140037f44  cmp     r14d, 3
0x140037f48  jnz     short loc_140037F54
0x140037f4a  btr     dword ptr [rbx+0C0h], 12h
0x140037f52  jmp     short loc_140037F62
0x140037f54  cmp     r14d, 4
0x140037f58  jnz     short loc_140037F62
0x140037f5a  bts     dword ptr [rbx+0C0h], 12h
0x140037f62  nop
0x140037f63  mov     rcx, rsi
0x140037f66  call    FatUnpinRepinnedBcbs
0x140037f6b  nop
0x140037f6c  cmp     [rsp+118h+var_88], r12b
0x140037f74  jz      short loc_140037F8D
0x140037f76  mov     rcx, [rbx+0B0h]
0x140037f7d  mov     rcx, [rcx+8]; Resource
0x140037f81  call    cs:__imp_ExReleaseResourceLite
0x140037f88  nop     dword ptr [rax+rax+00h]
0x140037f8d  mov     rcx, [rbx+8]; Resource
0x140037f91  call    cs:__imp_ExReleaseResourceLite
0x140037f98  nop     dword ptr [rax+rax+00h]
0x140037f9d  cmp     [rsp+118h+var_87], r12b
0x140037fa5  jz      short loc_140037FC2
0x140037fa7  mov     rcx, [rsp+118h+var_78]
0x140037faf  add     rcx, 208h; Resource
0x140037fb6  call    cs:__imp_ExReleaseResourceLite
0x140037fbd  nop     dword ptr [rax+rax+00h]
0x140037fc2  mov     r8d, r15d
0x140037fc5  mov     rdx, rdi; Irp
0x140037fc8  mov     rcx, rsi; Entry
0x140037fcb  call    FatCompleteRequest_Real
0x140037fd0  mov     eax, r15d
0x140037fd3  jmp     short loc_140038042
  ... truncated ...
```
