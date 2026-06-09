# FatCommonSetInformation

- ea: `0x140039e94`
- end: `0x14003a3d9`
- name: `FatCommonSetInformation`
- size: `1349`
- prototype: `__int64 __fastcall(PVOID Entry, PIRP Irp)`
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x14003a610`
- `0x1400438e0`

## callees

- `0x140007408`
- `0x14002486c`
- `0x140038eb4`
- `0x140039e94`
- `0x14003ad44`
- `0x14003b00c`
- `0x14003b698`
- `0x14003b9d0`
- `0x14003bea4`
- `0x14003d708`
- `0x14003d880`
- `0x1400465f4`
- `0x1400466c8`
- `0x14004a1d4`

## import_xrefs

- `ntoskrnl!FsRtlCheckOplock` at `0x140039fa2`
- `ntoskrnl!FsRtlCheckOplock` at `0x14003a14b`
- `ntoskrnl!FsRtlCheckOplock` at `0x140039fa2`
- `ntoskrnl!FsRtlCheckOplock` at `0x14003a14b`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140039fd5`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14003a170`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140039fd5`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14003a170`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003a38a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003a3ac`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e37c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e39d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003a38a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003a3ac`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e37c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e39d`
- `ntoskrnl!KeBugCheckEx` at `0x14003a0b2`
- `ntoskrnl!KeBugCheckEx` at `0x14003a0b2`

## pseudocode

```c
__int64 __fastcall FatCommonSetInformation(PVOID Entry, PIRP Irp)
{
  PIRP v2; // r14
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  ULONG Options; // esi
  int v6; // eax
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // ebx
  __int64 v10; // r15
  char v11; // r12
  char v12; // al
  PIRP v13; // rdx
  PVOID v14; // rcx
  __int64 v15; // rcx
  ULONG v16; // esi
  ULONG v17; // esi
  ULONG v18; // esi
  ULONG v19; // esi
  ULONG v20; // esi
  ULONG v21; // esi
  ULONG v22; // esi
  int valid; // eax
  struct _IRP *MasterIrp; // rdx
  char v26; // [rsp+30h] [rbp-58h]
  char v27; // [rsp+31h] [rbp-57h]
  struct _FILE_OBJECT *FileObject; // [rsp+38h] [rbp-50h]
  __int64 v29[9]; // [rsp+40h] [rbp-48h] BYREF
  __int64 v30; // [rsp+A0h] [rbp+18h] BYREF
  __int64 v31; // [rsp+A8h] [rbp+20h] BYREF

  v2 = Irp;
  v30 = 0;
  v31 = 0;
  v29 = 0;
  v27 = 0;
  v26 = 0;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  Options = CurrentStackLocation->Parameters.Create.Options;
  FileObject = CurrentStackLocation->FileObject;
  v6 = FatDecodeFileObject(FileObject, &v30, &v31, &v29) - 2;
  if ( v6 )
  {
    if ( v6 != 1 )
    {
      v9 = -1073741811;
      v10 = v31;
      goto LABEL_79;
    }
    v10 = v31;
    goto LABEL_5;
  }
  v10 = v31;
  if ( (*(_DWORD *)(v31 + 192) & 4) != 0 )
  {
LABEL_5:
    v11 = 1;
    goto LABEL_6;
  }
  v11 = 1;
  if ( Options - 19 <= 1 || Options == 39 )
  {
    v9 = FsRtlCheckOplock((POPLOCK)(v31 + 88), v2, Entry, 0, 0);
    if ( v9 )
      goto LABEL_79;
    if ( *(_DWORD *)(v10 + 196) == 1 && *(_WORD *)v10 == 1282 && FsRtlOplockIsFastIoPossible((POPLOCK)(v10 + 88)) )
    {
      if ( *(_BYTE *)(v10 + 336)
        || *(_DWORD *)(*(_QWORD *)(v10 + 120) + 24LL)
        || (*(_DWORD *)(*(_QWORD *)(v10 + 184) + 200LL) & 0x4000) != 0
        || (*(_DWORD *)(v10 + 192) & 0x8000) != 0 )
      {
        v12 = 2;
      }
      else
      {
        v12 = 1;
      }
    }
    else
    {
      v12 = 0;
    }
    *(_BYTE *)(v10 + 5) = v12;
  }
LABEL_6:
  if ( *(_WORD *)v10 == 1284 )
  {
    v9 = -1073741811;
    if ( Options == 13 )
      v9 = -1073741535;
    goto LABEL_79;
  }
  if ( Options == 13 || Options == 10 )
  {
    if ( !(unsigned __int8)FatAcquireExclusiveVcb_Real(Entry, v30, 0, v8) )
    {
LABEL_28:
      v13 = v2;
      v14 = Entry;
LABEL_29:
      v9 = FatFsdPostRequest(v14, v13);
      v2 = 0;
      Entry = 0;
      goto LABEL_79;
    }
    v27 = 1;
    if ( (*(_DWORD *)(v30 + 200) & 0x200) != 0 )
      KeBugCheckEx(0x23u, 0x10033Bu, 0, 0, 0);
  }
  if ( (*(_DWORD *)(v10 + 192) & 4) == 0 || (*(_DWORD *)(*(_QWORD *)(v10 + 184) + 200LL) & 2) != 0 )
  {
    if ( !(unsigned __int8)FatAcquireExclusiveFcb(Entry, v10, v7, v8) )
      goto LABEL_28;
    v26 = 1;
  }
  FatVerifyFcb(Entry, v10);
  if ( (unsigned __int16)(*(_WORD *)v10 - 1282) > 2u
    || Options != 10 && (Options != 13 || !v2->AssociatedIrp.MasterIrp->Type) )
  {
    goto LABEL_53;
  }
  v9 = FsRtlCheckOplock((POPLOCK)(v10 + 88), v2, Entry, FatOplockComplete, 0);
  if ( *(_DWORD *)(v10 + 196) == 1 && *(_WORD *)v10 == 1282 && FsRtlOplockIsFastIoPossible((POPLOCK)(v10 + 88)) )
  {
    if ( *(_BYTE *)(v10 + 336)
      || *(_DWORD *)(*(_QWORD *)(v10 + 120) + 24LL)
      || (v15 = *(unsigned int *)(*(_QWORD *)(v10 + 184) + 200LL), (v15 & 0x4000) != 0)
      || (*(_DWORD *)(v10 + 192) & 0x8000) != 0 )
    {
      v11 = 2;
    }
  }
  else
  {
    v11 = 0;
  }
  *(_BYTE *)(v10 + 5) = v11;
  if ( v9 == 259 )
  {
    v2 = 0;
    Entry = 0;
  }
  if ( v9 >= 0 && v9 != 259 )
  {
LABEL_53:
    v16 = Options - 4;
    if ( !v16 )
    {
      valid = FatSetBasicInfo(Entry, v2, v10, v29);
      goto LABEL_76;
    }
    v17 = v16 - 6;
    if ( !v17 )
    {
      v13 = v2;
      v14 = Entry;
      if ( (*((_DWORD *)Entry + 17) & 2) == 0 )
        goto LABEL_29;
      v9 = FatSetRenameInfo((__int64)Entry, v2, v30, v10, v29);
      if ( v9 == 259 )
      {
        v2 = 0;
        Entry = 0;
      }
      goto LABEL_77;
    }
    v18 = v17 - 1;
    if ( !v18 )
    {
      v9 = -1073741808;
      goto LABEL_77;
    }
    v19 = v18 - 2;
    if ( !v19 )
    {
      if ( (*(_DWORD *)(v30 + 200) & 0x1000) != 0 && (*((_DWORD *)Entry + 17) & 2) == 0 )
        goto LABEL_28;
      valid = FatSetDispositionInfo((__int64)Entry, (__int64)v2, (__int64)FileObject, v10);
      goto LABEL_76;
    }
    v20 = v19 - 1;
    if ( v20 )
    {
      v21 = v20 - 5;
      if ( !v21 )
      {
        valid = FatSetAllocationInfo((__int64)Entry, (__int64)v2, v10, FileObject);
        goto LABEL_76;
      }
      v22 = v21 - 1;
      if ( !v22 )
      {
        valid = FatSetEndOfFileInfo((__int64)Entry, v2, FileObject, v30, (char *)v10);
        goto LABEL_76;
      }
      if ( v22 == 19 )
      {
        valid = FatSetValidDataLengthInfo(v15, (__int64)v2, FileObject, v10, v29);
LABEL_76:
        v9 = valid;
LABEL_77:
        if ( Entry )
          FatUnpinRepinnedBcbs((__int64)Entry);
        goto LABEL_79;
      }
    }
    else
    {
      MasterIrp = v2->AssociatedIrp.MasterIrp;
      if ( (FileObject->Flags & 8) == 0
        || (v2->Tail.Overlay.CurrentStackLocation->DeviceObject->AlignmentRequirement & *(_DWORD *)&MasterIrp->Type) == 0 )
      {
        FileObject->CurrentByteOffset.QuadPart = *(_QWORD *)&MasterIrp->Type;
        v9 = 0;
        goto LABEL_77;
      }
    }
    v9 = -1073741811;
    goto LABEL_77;
  }
LABEL_79:
  if ( v26 )
    ExReleaseResourceLite(*(PERESOURCE *)(v10 + 8));
  if ( v27 )
    ExReleaseResourceLite((PERESOURCE)(v30 + 520));
  FatCompleteRequest_Real(Entry, v2, (unsigned int)v9, v8);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140039e94  mov     r11, rsp
0x140039e97  mov     [r11+10h], rdx
0x140039e9b  mov     [r11+8], rcx
0x140039e9f  push    rbx
0x140039ea0  push    rsi
0x140039ea1  push    rdi
0x140039ea2  push    r12
0x140039ea4  push    r13
0x140039ea6  push    r14
0x140039ea8  push    r15
0x140039eaa  sub     rsp, 50h
0x140039eae  mov     r14, rdx
0x140039eb1  mov     rdi, rcx
0x140039eb4  mov     [rsp+88h+var_54], 0
0x140039ebc  mov     qword ptr [r11+18h], 0
0x140039ec4  mov     qword ptr [r11+20h], 0
0x140039ecc  mov     qword ptr [r11-48h], 0
0x140039ed4  mov     [rsp+88h+var_57], 0
0x140039ed9  mov     [rsp+88h+var_58], 0
0x140039ede  mov     rax, [rdx+0B8h]
0x140039ee5  mov     esi, [rax+10h]
0x140039ee8  mov     rax, [rax+30h]
0x140039eec  mov     [rsp+88h+var_50], rax
0x140039ef1  lea     r9, [r11-48h]
0x140039ef5  lea     r8, [r11+20h]
0x140039ef9  lea     rdx, [r11+18h]
0x140039efd  mov     rcx, rax
0x140039f00  call    FatDecodeFileObject
0x140039f05  nop
0x140039f06  mov     ebx, 2
0x140039f0b  sub     eax, ebx
0x140039f0d  jz      short loc_140039F66
0x140039f0f  sub     eax, 1
0x140039f12  jz      short loc_140039F2A
0x140039f14  mov     ebx, 0C000000Dh
0x140039f19  mov     [rsp+88h+var_54], ebx
0x140039f1d  mov     r15, [rsp+88h+arg_18]
0x140039f25  jmp     loc_14003A37F
0x140039f2a  mov     r15, [rsp+88h+arg_18]
0x140039f32  mov     r12d, 1
0x140039f38  mov     r13d, 502h
0x140039f3e  mov     eax, 504h
0x140039f43  cmp     [r15], ax
0x140039f47  jnz     loc_14003A035
0x140039f4d  mov     ebx, 0C000000Dh
0x140039f52  mov     eax, 0C0000121h
0x140039f57  cmp     esi, 0Dh
0x140039f5a  cmovz   ebx, eax
0x140039f5d  mov     [rsp+88h+var_54], ebx
0x140039f61  jmp     loc_14003A37F
0x140039f66  mov     r15, [rsp+88h+arg_18]
0x140039f6e  mov     eax, [r15+0C0h]
0x140039f75  test    al, 4
0x140039f77  jnz     short loc_140039F32
0x140039f79  lea     eax, [rsi-13h]
0x140039f7c  mov     r12d, 1
0x140039f82  cmp     eax, r12d
0x140039f85  jbe     short loc_140039F8C
0x140039f87  cmp     esi, 27h ; '''
0x140039f8a  jnz     short loc_140039F38
0x140039f8c  lea     rcx, [r15+58h]; Oplock
0x140039f90  mov     [rsp+88h+PostIrpRoutine], 0; PostIrpRoutine
0x140039f99  xor     r9d, r9d; CompletionRoutine
0x140039f9c  mov     r8, rdi; Context
0x140039f9f  mov     rdx, r14; Irp
0x140039fa2  call    cs:__imp_FsRtlCheckOplock
0x140039fa9  nop     dword ptr [rax+rax+00h]
0x140039fae  mov     ebx, eax
0x140039fb0  mov     [rsp+88h+var_54], eax
0x140039fb4  test    eax, eax
0x140039fb6  jnz     loc_14003A37F
0x140039fbc  mov     r13d, 502h
0x140039fc2  cmp     [r15+0C4h], r12d
0x140039fc9  jnz     short loc_14003A025
0x140039fcb  cmp     [r15], r13w
0x140039fcf  jnz     short loc_14003A025
0x140039fd1  lea     rcx, [r15+58h]; Oplock
0x140039fd5  call    cs:__imp_FsRtlOplockIsFastIoPossible
0x140039fdc  nop     dword ptr [rax+rax+00h]
0x140039fe1  test    al, al
0x140039fe3  jz      short loc_14003A025
0x140039fe5  cmp     [r15+150h], bl
0x140039fec  jnz     short loc_14003A01C
0x140039fee  mov     rax, [r15+78h]
0x140039ff2  cmp     [rax+18h], ebx
0x140039ff5  jnz     short loc_14003A01C
0x140039ff7  mov     rax, [r15+0B8h]
0x140039ffe  mov     ecx, [rax+0C8h]
0x14003a004  bt      ecx, 0Eh
0x14003a008  jb      short loc_14003A01C
0x14003a00a  test    dword ptr [r15+0C0h], 8000h
0x14003a015  jnz     short loc_14003A01C
0x14003a017  mov     eax, r12d
0x14003a01a  jmp     short loc_14003A027
0x14003a01c  mov     ebx, 2
0x14003a021  mov     eax, ebx
0x14003a023  jmp     short loc_14003A02C
0x14003a025  xor     eax, eax
0x14003a027  mov     ebx, 2
0x14003a02c  mov     [r15+5], al
0x14003a030  jmp     loc_140039F3E
0x14003a035  cmp     esi, 0Dh
0x14003a038  jz      short loc_14003A03F
0x14003a03a  cmp     esi, 0Ah
0x14003a03d  jnz     short loc_14003A0BE
0x14003a03f  xor     r8d, r8d
0x14003a042  mov     rdx, [rsp+88h+arg_10]
0x14003a04a  mov     rcx, rdi
0x14003a04d  call    FatAcquireExclusiveVcb_Real
0x14003a052  test    al, al
0x14003a054  jnz     short loc_14003A081
0x14003a056  mov     rdx, r14; Context2
0x14003a059  mov     rcx, rdi; Context1
0x14003a05c  call    FatFsdPostRequest
0x14003a061  mov     ebx, eax
0x14003a063  mov     [rsp+88h+var_54], eax
0x14003a067  xor     r14d, r14d
0x14003a06a  mov     [rsp+88h+arg_8], r14
0x14003a072  xor     edi, edi
0x14003a074  mov     [rsp+88h+arg_0], rdi
0x14003a07c  jmp     loc_14003A37F
0x14003a081  mov     [rsp+88h+var_57], r12b
0x14003a086  mov     rax, [rsp+88h+arg_10]
0x14003a08e  mov     ecx, [rax+0C8h]
0x14003a094  bt      ecx, 9
0x14003a098  jnb     short loc_14003A0BE
0x14003a09a  mov     [rsp+88h+PostIrpRoutine], 0; BugCheckParameter4
0x14003a0a3  xor     r9d, r9d; BugCheckParameter3
0x14003a0a6  xor     r8d, r8d; BugCheckParameter2
0x14003a0a9  mov     edx, 10033Bh; BugCheckParameter1
0x14003a0ae  lea     ecx, [r9+23h]; BugCheckCode
0x14003a0b2  call    cs:__imp_KeBugCheckEx
0x14003a0be  mov     eax, [r15+0C0h]
0x14003a0c5  test    al, 4
0x14003a0c7  jz      short loc_14003A0DA
0x14003a0c9  mov     rax, [r15+0B8h]
0x14003a0d0  mov     ecx, [rax+0C8h]
0x14003a0d6  test    bl, cl
0x14003a0d8  jz      short loc_14003A0F2
0x14003a0da  mov     rdx, r15
0x14003a0dd  mov     rcx, rdi
0x14003a0e0  call    FatAcquireExclusiveFcb
0x14003a0e5  test    al, al
0x14003a0e7  jz      loc_14003A056
0x14003a0ed  mov     [rsp+88h+var_58], r12b
0x14003a0f2  mov     [rsp+88h+var_54], 0
0x14003a0fa  mov     rdx, r15
0x14003a0fd  mov     rcx, rdi
0x14003a100  call    FatVerifyFcb
0x14003a105  movzx   eax, word ptr [r15]
0x14003a109  sub     ax, r13w
0x14003a10d  cmp     ax, bx
0x14003a110  ja      loc_14003A1FB
0x14003a116  cmp     esi, 0Ah
0x14003a119  jz      short loc_14003A131
0x14003a11b  cmp     esi, 0Dh
0x14003a11e  jnz     loc_14003A1FB
0x14003a124  mov     rax, [r14+18h]
0x14003a128  cmp     byte ptr [rax], 0
0x14003a12b  jz      loc_14003A1FB
0x14003a131  lea     rcx, [r15+58h]; Oplock
0x14003a135  mov     [rsp+88h+PostIrpRoutine], 0; PostIrpRoutine
0x14003a13e  lea     r9, FatOplockComplete; CompletionRoutine
0x14003a145  mov     r8, rdi; Context
0x14003a148  mov     rdx, r14; Irp
0x14003a14b  call    cs:__imp_FsRtlCheckOplock
0x14003a152  nop     dword ptr [rax+rax+00h]
0x14003a157  mov     ebx, eax
0x14003a159  mov     [rsp+88h+var_54], eax
0x14003a15d  cmp     [r15+0C4h], r12d
0x14003a164  jnz     short loc_14003A1BC
0x14003a166  cmp     [r15], r13w
0x14003a16a  jnz     short loc_14003A1BC
0x14003a16c  lea     rcx, [r15+58h]; Oplock
0x14003a170  call    cs:__imp_FsRtlOplockIsFastIoPossible
0x14003a177  nop     dword ptr [rax+rax+00h]
0x14003a17c  test    al, al
0x14003a17e  jz      short loc_14003A1BC
0x14003a180  cmp     byte ptr [r15+150h], 0
0x14003a188  jnz     short loc_14003A1B4
0x14003a18a  mov     rax, [r15+78h]
0x14003a18e  cmp     dword ptr [rax+18h], 0
0x14003a192  jnz     short loc_14003A1B4
0x14003a194  mov     rax, [r15+0B8h]
0x14003a19b  mov     ecx, [rax+0C8h]
0x14003a1a1  bt      ecx, 0Eh
0x14003a1a5  jb      short loc_14003A1B4
0x14003a1a7  test    dword ptr [r15+0C0h], 8000h
0x14003a1b2  jz      short loc_14003A1BF
0x14003a1b4  mov     r12d, 2
0x14003a1ba  jmp     short loc_14003A1BF
0x14003a1bc  xor     r12d, r12d
0x14003a1bf  mov     [r15+5], r12b
0x14003a1c3  mov     r12d, 103h
0x14003a1c9  cmp     ebx, r12d
0x14003a1cc  jnz     short loc_14003A1E3
0x14003a1ce  xor     r14d, r14d
0x14003a1d1  mov     [rsp+88h+arg_8], r14
0x14003a1d9  xor     edi, edi
0x14003a1db  mov     [rsp+88h+arg_0], rdi
0x14003a1e3  test    ebx, ebx
0x14003a1e5  js      loc_14003A37F
0x14003a1eb  cmp     ebx, r12d
0x14003a1ee  jz      loc_14003A37F
0x14003a1f4  mov     ebx, 2
0x14003a1f9  jmp     short loc_14003A201
0x14003a1fb  mov     r12d, 103h
0x14003a201  sub     esi, 4
0x14003a204  jz      loc_14003A358
0x14003a20a  sub     esi, 6
0x14003a20d  jz      loc_14003A30B
0x14003a213  sub     esi, 1
0x14003a216  jz      loc_14003A304
0x14003a21c  sub     esi, ebx
0x14003a21e  jz      loc_14003A2D0
0x14003a224  sub     esi, 1
0x14003a227  jz      short loc_14003A291
0x14003a229  sub     esi, 5
0x14003a22c  jz      short loc_14003A279
0x14003a22e  sub     esi, 1
0x14003a231  jz      short loc_14003A257
0x14003a233  cmp     esi, 13h
0x14003a236  jnz     short loc_14003A2B7
0x14003a238  mov     rax, [rsp+88h+var_48]
0x14003a23d  mov     [rsp+88h+PostIrpRoutine], rax
0x14003a242  mov     r9, r15
0x14003a245  mov     r8, [rsp+88h+var_50]
0x14003a24a  mov     rdx, r14
0x14003a24d  call    FatSetValidDataLengthInfo
0x14003a252  jmp     loc_14003A36B
0x14003a257  mov     [rsp+88h+PostIrpRoutine], r15
0x14003a25c  mov     r9, [rsp+88h+arg_10]
0x14003a264  mov     r8, [rsp+88h+var_50]
0x14003a269  mov     rdx, r14
0x14003a26c  mov     rcx, rdi
0x14003a26f  call    FatSetEndOfFileInfo
0x14003a274  jmp     loc_14003A36B
0x14003a279  mov     r9, [rsp+88h+var_50]
0x14003a27e  mov     r8, r15
0x14003a281  mov     rdx, r14
0x14003a284  mov     rcx, rdi
0x14003a287  call    FatSetAllocationInfo
0x14003a28c  jmp     loc_14003A36B
0x14003a291  mov     rdx, [r14+18h]
0x14003a295  mov     r8, [rsp+88h+var_50]
0x14003a29a  mov     eax, [r8+50h]
0x14003a29e  test    al, 8
0x14003a2a0  jz      short loc_14003A2BE
0x14003a2a2  mov     rax, [r14+0B8h]
0x14003a2a9  mov     rcx, [rax+28h]
0x14003a2ad  mov     eax, [rcx+98h]
0x14003a2b3  test    [rdx], eax
0x14003a2b5  jz      short loc_14003A2BE
0x14003a2b7  mov     ebx, 0C000000Dh
0x14003a2bc  jmp     short loc_14003A2C7
0x14003a2be  mov     rax, [rdx]
0x14003a2c1  mov     [r8+68h], rax
0x14003a2c5  xor     ebx, ebx
0x14003a2c7  mov     [rsp+88h+var_54], ebx
0x14003a2cb  jmp     loc_14003A371
0x14003a2d0  mov     rax, [rsp+88h+arg_10]
0x14003a2d8  mov     ecx, [rax+0C8h]
0x14003a2de  bt      ecx, 0Ch
0x14003a2e2  jnb     short loc_14003A2EF
0x14003a2e4  mov     eax, [rdi+44h]
0x14003a2e7  test    bl, al
0x14003a2e9  jz      loc_14003A056
0x14003a2ef  mov     r9, r15
0x14003a2f2  mov     r8, [rsp+88h+var_50]
0x14003a2f7  mov     rdx, r14
0x14003a2fa  mov     rcx, rdi; int
0x14003a2fd  call    FatSetDispositionInfo
0x14003a302  jmp     short loc_14003A36B
0x14003a304  mov     ebx, 0C0000010h
0x14003a309  jmp     short loc_14003A2C7
0x14003a30b  mov     eax, [rdi+44h]
0x14003a30e  mov     rdx, r14
0x14003a311  mov     rcx, rdi
0x14003a314  test    bl, al
0x14003a316  jz      loc_14003A05C
0x14003a31c  mov     rax, [rsp+88h+var_48]
0x14003a321  mov     [rsp+88h+PostIrpRoutine], rax
0x14003a326  mov     r9, r15
0x14003a329  mov     r8, [rsp+88h+arg_10]
0x14003a331  call    FatSetRenameInfo
0x14003a336  mov     ebx, eax
0x14003a338  mov     [rsp+88h+var_54], eax
0x14003a33c  cmp     eax, r12d
0x14003a33f  jnz     short loc_14003A371
0x14003a341  xor     r14d, r14d
0x14003a344  mov     [rsp+88h+arg_8], r14
0x14003a34c  xor     edi, edi
0x14003a34e  mov     [rsp+88h+arg_0], rdi
0x14003a356  jmp     short loc_14003A371
0x14003a358  mov     r9, [rsp+88h+var_48]
0x14003a35d  mov     r8, r15
0x14003a360  mov     rdx, r14
0x14003a363  mov     rcx, rdi
0x14003a366  call    FatSetBasicInfo
0x14003a36b  mov     ebx, eax
  ... truncated ...
```
