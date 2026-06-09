# FatOpenExistingFile

- ea: `0x14002b790`
- end: `0x14002bf34`
- name: `FatOpenExistingFile`
- size: `1956`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1400268c0`

## callees

- `0x140002ed8`
- `0x1400201f4`
- `0x14002023c`
- `0x1400226b8`
- `0x140026864`
- `0x140028aa8`
- `0x14002b790`
- `0x14002cbe4`
- `0x140031938`
- `0x1400364fc`
- `0x140036ffc`
- `0x14003db44`
- `0x1400475e8`
- `0x140047960`
- `0x14004814c`
- `0x140048184`

## import_xrefs

- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x14002ba02`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x14002ba02`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14002bc0d`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14002bc0d`
- `ntoskrnl!IoSetShareAccess` at `0x14002b8d3`
- `ntoskrnl!IoSetShareAccess` at `0x14002b8d3`
- `ntoskrnl!FsRtlOplockFsctrl` at `0x14002bc3e`
- `ntoskrnl!FsRtlOplockFsctrl` at `0x14002bc3e`
- `ntoskrnl!KeBugCheckEx` at `0x14002bca6`
- `ntoskrnl!KeBugCheckEx` at `0x14002bca6`
- `ntoskrnl!ExRaiseStatus` at `0x14002ba25`
- `ntoskrnl!ExRaiseStatus` at `0x14002bc55`
- `ntoskrnl!ExRaiseStatus` at `0x14002bcfd`
- `ntoskrnl!ExRaiseStatus` at `0x14002becc`
- `ntoskrnl!ExRaiseStatus` at `0x14002bf10`
- `ntoskrnl!ExRaiseStatus` at `0x14002ba25`
- `ntoskrnl!ExRaiseStatus` at `0x14002bc55`
- `ntoskrnl!ExRaiseStatus` at `0x14002bcfd`
- `ntoskrnl!ExRaiseStatus` at `0x14002becc`
- `ntoskrnl!ExRaiseStatus` at `0x14002bf10`

## pseudocode

```c
__int64 __fastcall FatOpenExistingFile(
        __int64 a1,
        __int64 a2,
        struct _FILE_OBJECT *a3,
        __int64 a4,
        __int64 *a5,
        __int64 a6,
        __int64 a7,
        int a8,
        int a9,
        __int64 a10,
        __int64 a11,
        ACCESS_MASK *a12,
        unsigned __int16 a13,
        unsigned int a14,
        __int64 a15,
        int a16,
        unsigned __int16 a17,
        ULONG_PTR BugCheckParameter2,
        char a19,
        char a20,
        char a21,
        char a22,
        char a23)
{
  struct _FILE_OBJECT *v24; // r13
  __int64 v27; // rdx
  int v28; // r14d
  __int64 v29; // rcx
  int v30; // edi
  ACCESS_MASK *v31; // r12
  __int64 *v32; // rdi
  __int64 v33; // r13
  __int64 v34; // r8
  _DWORD *FsContext2; // r14
  __int64 v36; // r12
  char v37; // al
  __int64 v38; // rdx
  __int64 v39; // r8
  _DWORD *v40; // r9
  __int64 v41; // rdx
  int v42; // ecx
  unsigned int v43; // ecx
  int v44; // r8d
  int v45; // r9d
  NTSTATUS v46; // eax
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // rdx
  int v50; // eax
  __int64 v51; // rcx
  int v52; // eax
  NTSTATUS Callback; // eax
  NTSTATUS EncryptOnCloseProcessing; // eax
  int v56; // [rsp+64h] [rbp-74h]
  __int64 Fcb; // [rsp+70h] [rbp-68h]
  __int64 Ccb; // [rsp+78h] [rbp-60h]
  __int64 v59; // [rsp+80h] [rbp-58h]
  char v60[80]; // [rsp+88h] [rbp-50h] BYREF
  unsigned __int16 v61; // [rsp+E0h] [rbp+8h] BYREF
  int v62; // [rsp+E8h] [rbp+10h]
  struct _FILE_OBJECT *v63; // [rsp+F0h] [rbp+18h]
  __int64 v64; // [rsp+F8h] [rbp+20h]

  v64 = a4;
  v63 = a3;
  v24 = a3;
  *(_OWORD *)a1 = 0;
  v27 = 0;
  v28 = 0;
  v59 = *(_QWORD *)(*(_QWORD *)(a2 + 40) + 184LL);
  v29 = *(_QWORD *)(*(_QWORD *)(v59 + 8) + 8LL);
  v56 = *(_DWORD *)(v29 + 12) & 0x40000;
  v30 = BugCheckParameter2;
  if ( (_DWORD)BugCheckParameter2 == 2 )
  {
    *(_DWORD *)a1 = -1073741771;
    v31 = a12;
    v32 = a5;
    goto LABEL_15;
  }
  if ( (_DWORD)BugCheckParameter2 || a19 )
  {
    if ( (unsigned int)(BugCheckParameter2 - 4) > 1 || a19 )
    {
      v31 = a12;
      goto LABEL_11;
    }
    v29 = 274;
  }
  else
  {
    v29 = 0x10000;
  }
  v31 = a12;
  v28 = v29 & ~*a12;
  *a12 |= v29;
LABEL_11:
  v33 = a7;
  LOBYTE(v27) = *(_BYTE *)(a7 + 11);
  if ( !(unsigned __int8)FatCheckFileAccess(v29, v27, v31)
    || (*(_DWORD *)(a4 + 200) & 0x400000) != 0 && v56 && (*v31 & 0x27) != 0 && (*(_BYTE *)(v33 + 12) & 1) == 0 )
  {
    goto LABEL_12;
  }
  if ( a21 && (*(_BYTE *)(v33 + 11) & 1) != 0 )
  {
    *(_DWORD *)a1 = -1073741535;
    goto LABEL_13;
  }
  if ( (v30 & 0xFFFFFFFA) == 0 && v30 != 1 )
  {
    v37 = *(_BYTE *)(v33 + 11);
    if ( ((v37 & 2) == 0 || (a17 & 2) != 0) && ((v37 & 4) == 0 || (a17 & 4) != 0) || a19 )
    {
      if ( (*(_DWORD *)(a4 + 200) & 0x4000) != 0 )
      {
        IoSetHardErrorOrVerifyDevice(*(PIRP *)(a2 + 40), *(PDEVICE_OBJECT *)(*(_QWORD *)(a4 + 192) + 16LL));
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a4 + 192) + 16LL) + 48LL) |= 2u;
        *(_DWORD *)(a2 + 72) = -1073741662;
        ExRaiseStatus(-1073741662);
      }
      goto LABEL_44;
    }
LABEL_12:
    *(_DWORD *)a1 = -1073741790;
LABEL_13:
    v32 = a5;
LABEL_14:
    v24 = v63;
    goto LABEL_15;
  }
LABEL_44:
  Fcb = FatCreateFcb(v29, a4, a6, a8, a9, v33, a10, a11, a19, 0);
  v32 = a5;
  *a5 = Fcb;
  if ( (*(_DWORD *)(a4 + 200) & 0x400000) != 0 && (*(_BYTE *)(v33 + 12) & 1) != 0 )
  {
    if ( a11 )
    {
      LOBYTE(v38) = 1;
      if ( (unsigned __int8)FatFileExtensionIsPfile(a11, v38) )
      {
        *(_DWORD *)(*v32 + 192) |= 0x8000u;
        *(_BYTE *)(*v32 + 136) = ((*(_BYTE *)(v33 + 12) & 4) != 0) | (*(_BYTE *)(v33 + 12) >> 4) & 0xE;
        *(_BYTE *)(*v32 + 5) = 2;
        v39 = *v32;
        v40 = (_DWORD *)(*v32 + 132);
        if ( (*(_BYTE *)(v33 + 12) & 2) == 0 )
        {
          *v40 = *(_DWORD *)(a4 + 372);
          v41 = *v32;
          v42 = *(_DWORD *)(v33 + 28) - *(unsigned __int8 *)(*v32 + 136) - *(_DWORD *)(*v32 + 132);
LABEL_54:
          *(_DWORD *)(v41 + 32) = v42;
          goto LABEL_55;
        }
        v61 = 0;
        FatGetEfsInfoFromHeaderOnDisk(a2, a4, *(_DWORD *)(v39 + 128), (_DWORD)v40, (__int64)&v61);
        *(_DWORD *)(*v32 + 32) = *(_DWORD *)(v33 + 28) - *(unsigned __int8 *)(*v32 + 136) - *(_DWORD *)(*v32 + 132);
        if ( v61 <= 0x7FFFu && *(_DWORD *)(*v32 + 32) != v61 )
        {
          *(_BYTE *)(*v32 + 136) = ((v61 + 15) & 0xF0) - v61;
          v43 = *(_DWORD *)(v33 + 28);
          v41 = *v32;
          v44 = *(_DWORD *)(*v32 + 132);
          v45 = *(unsigned __int8 *)(*v32 + 136);
          if ( v45 + v44 <= v43 )
          {
            v42 = v43 - v45 - v44;
            goto LABEL_54;
          }
        }
      }
    }
  }
LABEL_55:
  *(_DWORD *)(*v32 + 40) = *(_DWORD *)(*v32 + 32);
  if ( a19 )
    FatLookupFileAllocationSize(a2, *v32);
  v46 = FsRtlCheckOplockEx((POPLOCK)(*v32 + 88), *(PIRP *)(a2 + 40), 2u, 0, 0, 0);
  *(_DWORD *)a1 = v46;
  if ( a22 )
  {
    if ( v46 )
      goto LABEL_61;
    v46 = FsRtlOplockFsctrl((POPLOCK)(*v32 + 88), *(PIRP *)(a2 + 40), *(_DWORD *)(*v32 + 228) + 1);
    *(_DWORD *)a1 = v46;
  }
  if ( v46 )
  {
LABEL_61:
    *(_DWORD *)(a2 + 72) = v46;
    ExRaiseStatus(v46);
  }
  v48 = (unsigned int)BugCheckParameter2;
  if ( !(_DWORD)BugCheckParameter2 )
  {
LABEL_72:
    v50 = FatCheckSystemSecurityAccess(a2);
    *(_DWORD *)a1 = v50;
    if ( v50 >= 0 )
    {
      v24 = v63;
      *(_OWORD *)a1 = *(_OWORD *)FatSupersedeOrOverwriteFile(
                                   (__int64)v60,
                                   a2,
                                   v63,
                                   *v32,
                                   a14,
                                   a15,
                                   a16,
                                   a17,
                                   BugCheckParameter2,
                                   a20);
      goto LABEL_15;
    }
    goto LABEL_14;
  }
  if ( (_DWORD)BugCheckParameter2 != 1 && (_DWORD)BugCheckParameter2 != 3 )
  {
    if ( (unsigned int)(BugCheckParameter2 - 4) >= 2 )
      KeBugCheckEx(0x23u, 0x615BBu, (unsigned int)BugCheckParameter2, 0, 0);
    goto LABEL_72;
  }
  if ( a20 )
  {
    if ( *(_BYTE *)(a4 + 376) != 32 )
    {
      v62 = 0;
      FatGetNeedEaCount(a2, a4);
      if ( v62 )
      {
        *(_DWORD *)(a2 + 72) = -1073741790;
        ExRaiseStatus(-1073741790);
      }
    }
  }
  Ccb = FatCreateCcb(v48, v47);
  v24 = v63;
  FatSetFileObject(v63, v49, *v32, Ccb);
  v24->SectionObjectPointer = *(PSECTION_OBJECT_POINTERS *)(*v32 + 120);
  *(_DWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 1;
LABEL_15:
  if ( *(int *)a1 >= 0 && *(_DWORD *)a1 != 259 )
  {
    *v31 &= ~v28;
    IoSetShareAccess(*v31, a13, v24, (PSHARE_ACCESS)(*v32 + 200));
    ++*(_DWORD *)(*v32 + 228);
    ++*(_DWORD *)(*v32 + 232);
    if ( (v24->Flags & 8) != 0 )
      ++*(_DWORD *)(*v32 + 236);
    ++*(_DWORD *)(a4 + 272);
    if ( !*(_WORD *)&v24->WriteAccess )
      ++*(_DWORD *)(a4 + 276);
  }
  v34 = 0;
  if ( *(int *)a1 < 0 )
  {
    v36 = v59;
  }
  else
  {
    FsContext2 = v24->FsContext2;
    if ( a21 )
      FsContext2[1] |= 0x400u;
    if ( a23 )
      FsContext2[1] |= 0x800u;
    v36 = v59;
    if ( (*(_BYTE *)(v59 + 2) & 1) != 0 )
      LOBYTE(v34) = 1;
    else
      LOBYTE(v34) = *(_BYTE *)(*(_QWORD *)(a2 + 40) + 64LL);
    if ( (unsigned __int8)FatCheckManageVolumeAccess(v29, *(_QWORD *)(*(_QWORD *)(v59 + 8) + 8LL), v34) )
      FsContext2[1] |= 0x20000u;
  }
  if ( (*(_DWORD *)(a4 + 200) & 0x400000) != 0 && *(int *)a1 >= 0 && *v32 )
  {
    v51 = *(_QWORD *)(*(_QWORD *)(v36 + 8) + 8LL);
    v52 = *(_DWORD *)(v51 + 16);
    if ( (*(_DWORD *)(*v32 + 192) & 0x60000) != 0 )
    {
      *(_DWORD *)(v51 + 20) |= v52;
      if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v36 + 8) + 8LL) + 20LL) & 0x27) != 0 )
      {
        *(_DWORD *)(a2 + 136) = 131090;
        if ( v56 )
          *(_DWORD *)(a2 + 136) = 131346;
        Callback = EfsFileCreateCallback(
                     *v32,
                     a6,
                     v36,
                     *(_DWORD *)(a2 + 136),
                     (*(_DWORD *)(a4 + 200) >> 14) & 1,
                     a2,
                     a4 - 416);
        if ( Callback < 0 )
        {
          *(_DWORD *)a1 = Callback;
          *(_DWORD *)(a2 + 72) = Callback;
          ExRaiseStatus(Callback);
        }
        *(_DWORD *)(a2 + 68) |= 0x8000u;
      }
    }
    else
    {
      *(_DWORD *)(v51 + 20) |= v52;
      EncryptOnCloseProcessing = FatCreateEncryptOnCloseProcessing(
                                   a2,
                                   *(_QWORD *)(a2 + 40),
                                   v36,
                                   a4,
                                   *v32,
                                   (__int64)v24->FsContext2);
      *(_DWORD *)a1 = EncryptOnCloseProcessing;
      if ( EncryptOnCloseProcessing < 0 )
      {
        *(_DWORD *)(a2 + 72) = EncryptOnCloseProcessing;
        ExRaiseStatus(EncryptOnCloseProcessing);
      }
    }
  }
  return a1;
}

```

## disassembly

```asm
0x14002b790  mov     r11, rsp
0x14002b793  mov     [r11+20h], r9
0x14002b797  mov     [r11+18h], r8
0x14002b79b  push    rbx
0x14002b79c  push    rsi
0x14002b79d  push    rdi
0x14002b79e  push    r12
0x14002b7a0  push    r13
0x14002b7a2  push    r14
0x14002b7a4  push    r15
0x14002b7a6  sub     rsp, 0A0h
0x14002b7ad  mov     r15, r9
0x14002b7b0  mov     r13, r8
0x14002b7b3  mov     rbx, rdx
0x14002b7b6  mov     rsi, rcx
0x14002b7b9  xorps   xmm0, xmm0
0x14002b7bc  movups  xmmword ptr [rcx], xmm0
0x14002b7bf  xor     edx, edx
0x14002b7c1  mov     r14d, edx
0x14002b7c4  mov     rax, [rbx+28h]
0x14002b7c8  mov     rax, [rax+0B8h]
0x14002b7cf  mov     [rsp+0D8h+var_58], rax
0x14002b7d7  mov     [r11-68h], rdx
0x14002b7db  mov     [r11-60h], rdx
0x14002b7df  mov     [rsp+0D8h+var_78], dl
0x14002b7e3  mov     rax, [rax+8]
0x14002b7e7  mov     rcx, [rax+8]
0x14002b7eb  mov     eax, [rcx+0Ch]
0x14002b7ee  and     eax, 40000h
0x14002b7f3  mov     [rsp+0D8h+var_74], eax
0x14002b7f7  mov     edi, dword ptr [rsp+0D8h+BugCheckParameter2]
0x14002b7fe  cmp     edi, 2
0x14002b801  jnz     short loc_14002B81E
0x14002b803  mov     dword ptr [rsi], 0C0000035h
0x14002b809  mov     r12, [rsp+0D8h+arg_58]
0x14002b811  mov     rdi, [rsp+0D8h+arg_20]
0x14002b819  jmp     loc_14002B8A6
0x14002b81e  test    edi, edi
0x14002b820  jnz     short loc_14002B852
0x14002b822  cmp     [rsp+0D8h+arg_90], dl
0x14002b829  jnz     short loc_14002B852
0x14002b82b  mov     ecx, 10000h
0x14002b830  mov     r12, [rsp+0D8h+arg_58]
0x14002b838  mov     eax, [r12]
0x14002b83c  mov     r14d, eax
0x14002b83f  not     r14d
0x14002b842  and     r14d, ecx
0x14002b845  mov     [rsp+0D8h+var_70], r14d
0x14002b84a  or      eax, ecx
0x14002b84c  mov     [r12], eax
0x14002b850  jmp     short loc_14002B872
0x14002b852  lea     eax, [rdi-4]
0x14002b855  cmp     eax, 1
0x14002b858  ja      short loc_14002B86A
0x14002b85a  cmp     [rsp+0D8h+arg_90], dl
0x14002b861  jnz     short loc_14002B86A
0x14002b863  mov     ecx, 112h
0x14002b868  jmp     short loc_14002B830
0x14002b86a  mov     r12, [rsp+0D8h+arg_58]
0x14002b872  mov     r13, [rsp+0D8h+arg_30]
0x14002b87a  mov     r8, r12
0x14002b87d  mov     dl, [r13+0Bh]
0x14002b881  call    FatCheckFileAccess
0x14002b886  xor     edx, edx
0x14002b888  test    al, al
0x14002b88a  jnz     loc_14002B96B
0x14002b890  mov     dword ptr [rsi], 0C0000022h
0x14002b896  mov     rdi, [rsp+0D8h+arg_20]
0x14002b89e  mov     r13, [rsp+0D8h+arg_10]
0x14002b8a6  mov     eax, [rsi]
0x14002b8a8  test    eax, eax
0x14002b8aa  js      short loc_14002B91F
0x14002b8ac  cmp     eax, 103h
0x14002b8b1  jz      short loc_14002B91F
0x14002b8b3  not     r14d
0x14002b8b6  and     [r12], r14d
0x14002b8ba  mov     ecx, [r12]; DesiredAccess
0x14002b8be  mov     r9, [rdi]
0x14002b8c1  add     r9, 0C8h; ShareAccess
0x14002b8c8  movzx   edx, [rsp+0D8h+arg_60]; DesiredShareAccess
0x14002b8d0  mov     r8, r13; FileObject
0x14002b8d3  call    cs:__imp_IoSetShareAccess
0x14002b8da  nop     dword ptr [rax+rax+00h]
0x14002b8df  mov     rax, [rdi]
0x14002b8e2  inc     dword ptr [rax+0E4h]
0x14002b8e8  mov     rax, [rdi]
0x14002b8eb  inc     dword ptr [rax+0E8h]
0x14002b8f1  mov     eax, [r13+50h]
0x14002b8f5  test    al, 8
0x14002b8f7  jz      short loc_14002B902
0x14002b8f9  mov     rax, [rdi]
0x14002b8fc  inc     dword ptr [rax+0ECh]
0x14002b902  inc     dword ptr [r15+110h]
0x14002b909  mov     al, [r13+4Ch]
0x14002b90d  or      al, [r13+4Bh]
0x14002b911  jnz     short loc_14002B91A
0x14002b913  inc     dword ptr [r15+114h]
0x14002b91a  mov     [rsp+0D8h+var_78], 1
0x14002b91f  xor     r8d, r8d
0x14002b922  cmp     [rsi], r8d
0x14002b925  jl      loc_14002BDEE
0x14002b92b  mov     r14, [r13+20h]
0x14002b92f  cmp     [rsp+0D8h+arg_A0], r8b
0x14002b937  jz      short loc_14002B93F
0x14002b939  bts     dword ptr [r14+4], 0Ah
0x14002b93f  cmp     [rsp+0D8h+arg_B0], r8b
0x14002b947  jz      short loc_14002B94F
0x14002b949  bts     dword ptr [r14+4], 0Bh
0x14002b94f  mov     r12, [rsp+0D8h+var_58]
0x14002b957  test    byte ptr [r12+2], 1
0x14002b95d  jz      loc_14002BDC9
0x14002b963  mov     r8b, 1
0x14002b966  jmp     loc_14002BDD1
0x14002b96b  mov     eax, [r15+0C8h]
0x14002b972  bt      eax, 16h
0x14002b976  jnb     short loc_14002B991
0x14002b978  cmp     [rsp+0D8h+var_74], edx
0x14002b97c  jz      short loc_14002B991
0x14002b97e  mov     eax, [r12]
0x14002b982  test    al, 27h
0x14002b984  jz      short loc_14002B991
0x14002b986  test    byte ptr [r13+0Ch], 1
0x14002b98b  jz      loc_14002B890
0x14002b991  cmp     [rsp+0D8h+arg_A0], dl
0x14002b998  jz      short loc_14002B9AC
0x14002b99a  test    byte ptr [r13+0Bh], 1
0x14002b99f  jz      short loc_14002B9AC
0x14002b9a1  mov     dword ptr [rsi], 0C0000121h
0x14002b9a7  jmp     loc_14002B896
0x14002b9ac  test    edi, 0FFFFFFFAh
0x14002b9b2  jnz     short loc_14002BA31
0x14002b9b4  cmp     edi, 1
0x14002b9b7  jz      short loc_14002BA31
0x14002b9b9  mov     al, [r13+0Bh]
0x14002b9bd  test    al, 2
0x14002b9bf  jz      short loc_14002B9CB
0x14002b9c1  test    byte ptr [rsp+0D8h+arg_80], 2
0x14002b9c9  jz      short loc_14002B9D9
0x14002b9cb  test    al, 4
0x14002b9cd  jz      short loc_14002B9E6
0x14002b9cf  test    byte ptr [rsp+0D8h+arg_80], 4
0x14002b9d7  jnz     short loc_14002B9E6
0x14002b9d9  cmp     [rsp+0D8h+arg_90], dl
0x14002b9e0  jz      loc_14002B890
0x14002b9e6  mov     eax, [r15+0C8h]
0x14002b9ed  bt      eax, 0Eh
0x14002b9f1  jnb     short loc_14002BA31
0x14002b9f3  mov     rdx, [r15+0C0h]
0x14002b9fa  mov     rdx, [rdx+10h]; DeviceObject
0x14002b9fe  mov     rcx, [rbx+28h]; Irp
0x14002ba02  call    cs:__imp_IoSetHardErrorOrVerifyDevice
0x14002ba09  nop     dword ptr [rax+rax+00h]
0x14002ba0e  mov     rax, [r15+0C0h]
0x14002ba15  mov     rcx, [rax+10h]
0x14002ba19  or      dword ptr [rcx+30h], 2
0x14002ba1d  mov     ecx, 0C00000A2h; Status
0x14002ba22  mov     [rbx+48h], ecx
0x14002ba25  call    cs:__imp_ExRaiseStatus
0x14002ba31  mov     byte ptr [rsp+0D8h+var_90], dl
0x14002ba35  mov     al, [rsp+0D8h+arg_90]
0x14002ba3c  mov     byte ptr [rsp+0D8h+var_98], al
0x14002ba40  mov     rax, [rsp+0D8h+arg_50]
0x14002ba48  mov     [rsp+0D8h+var_A0], rax
0x14002ba4d  mov     rax, [rsp+0D8h+arg_48]
0x14002ba55  mov     [rsp+0D8h+var_A8], rax
0x14002ba5a  mov     [rsp+0D8h+PostIrpRoutine], r13
0x14002ba5f  mov     eax, [rsp+0D8h+arg_40]
0x14002ba66  mov     dword ptr [rsp+0D8h+CompletionRoutine], eax
0x14002ba6a  mov     r9d, [rsp+0D8h+arg_38]
0x14002ba72  mov     r8, [rsp+0D8h+arg_28]
0x14002ba7a  mov     rdx, r15
0x14002ba7d  call    FatCreateFcb
0x14002ba82  mov     [rsp+0D8h+var_68], rax
0x14002ba87  mov     rdi, [rsp+0D8h+arg_20]
0x14002ba8f  mov     [rdi], rax
0x14002ba92  mov     eax, [r15+0C8h]
0x14002ba99  bt      eax, 16h
0x14002ba9d  jnb     loc_14002BBCB
0x14002baa3  test    byte ptr [r13+0Ch], 1
0x14002baa8  jz      loc_14002BBCB
0x14002baae  mov     rax, [rsp+0D8h+arg_50]
0x14002bab6  test    rax, rax
0x14002bab9  jz      loc_14002BBCB
0x14002babf  mov     dl, 1
0x14002bac1  mov     rcx, rax
0x14002bac4  call    FatFileExtensionIsPfile
0x14002bac9  test    al, al
0x14002bacb  jz      loc_14002BBCB
0x14002bad1  mov     rax, [rdi]
0x14002bad4  bts     dword ptr [rax+0C0h], 0Fh
0x14002badc  movzx   eax, byte ptr [r13+0Ch]
0x14002bae1  mov     ecx, eax
0x14002bae3  shr     ecx, 4
0x14002bae6  and     cl, 0Eh
0x14002bae9  shr     eax, 2
0x14002baec  and     al, 1
0x14002baee  or      cl, al
0x14002baf0  mov     rax, [rdi]
0x14002baf3  mov     [rax+88h], cl
0x14002baf9  mov     rax, [rdi]
0x14002bafc  mov     byte ptr [rax+5], 2
0x14002bb00  mov     r8, [rdi]
0x14002bb03  lea     r9, [r8+84h]
0x14002bb0a  test    byte ptr [r13+0Ch], 2
0x14002bb0f  jnz     short loc_14002BB36
0x14002bb11  mov     eax, [r15+174h]
0x14002bb18  mov     [r9], eax
0x14002bb1b  mov     rdx, [rdi]
0x14002bb1e  movzx   eax, byte ptr [rdx+88h]
0x14002bb25  mov     ecx, [r13+1Ch]
0x14002bb29  sub     ecx, eax
0x14002bb2b  sub     ecx, [rdx+84h]
0x14002bb31  jmp     loc_14002BBC8
0x14002bb36  xor     eax, eax
0x14002bb38  mov     [rsp+0D8h+arg_0], ax
0x14002bb40  lea     rax, [rsp+0D8h+arg_0]
0x14002bb48  mov     [rsp+0D8h+CompletionRoutine], rax
0x14002bb4d  mov     r8d, [r8+80h]
0x14002bb54  mov     rdx, r15
0x14002bb57  mov     rcx, rbx
0x14002bb5a  call    FatGetEfsInfoFromHeaderOnDisk
0x14002bb5f  mov     rdx, [rdi]
0x14002bb62  movzx   eax, byte ptr [rdx+88h]
0x14002bb69  mov     ecx, [r13+1Ch]
0x14002bb6d  sub     ecx, eax
0x14002bb6f  sub     ecx, [rdx+84h]
0x14002bb75  mov     [rdx+20h], ecx
0x14002bb78  mov     eax, 7FFFh
0x14002bb7d  cmp     [rsp+0D8h+arg_0], ax
0x14002bb85  ja      short loc_14002BBCB
0x14002bb87  movzx   ecx, [rsp+0D8h+arg_0]
0x14002bb8f  mov     rdx, [rdi]
0x14002bb92  cmp     [rdx+20h], ecx
0x14002bb95  jz      short loc_14002BBCB
0x14002bb97  lea     eax, [rcx+0Fh]
0x14002bb9a  and     al, 0F0h
0x14002bb9c  sub     al, cl
0x14002bb9e  mov     [rdx+88h], al
0x14002bba4  mov     ecx, [r13+1Ch]
0x14002bba8  mov     rdx, [rdi]
0x14002bbab  mov     r8d, [rdx+84h]
0x14002bbb2  movzx   r9d, byte ptr [rdx+88h]
0x14002bbba  lea     eax, [r9+r8]
0x14002bbbe  cmp     eax, ecx
0x14002bbc0  ja      short loc_14002BBCB
0x14002bbc2  sub     ecx, r9d
0x14002bbc5  sub     ecx, r8d
0x14002bbc8  mov     [rdx+20h], ecx
0x14002bbcb  mov     rcx, [rdi]
0x14002bbce  mov     eax, [rcx+20h]
0x14002bbd1  mov     [rcx+28h], eax
0x14002bbd4  cmp     [rsp+0D8h+arg_90], 0
0x14002bbdc  jz      short loc_14002BBE9
0x14002bbde  mov     rdx, [rdi]
0x14002bbe1  mov     rcx, rbx
0x14002bbe4  call    FatLookupFileAllocationSize
0x14002bbe9  mov     rcx, [rdi]
0x14002bbec  add     rcx, 58h ; 'X'; Oplock
0x14002bbf0  mov     [rsp+0D8h+PostIrpRoutine], 0; PostIrpRoutine
0x14002bbf9  mov     [rsp+0D8h+CompletionRoutine], 0; CompletionRoutine
0x14002bc02  xor     r9d, r9d; Context
0x14002bc05  lea     r8d, [r9+2]; Flags
0x14002bc09  mov     rdx, [rbx+28h]; Irp
0x14002bc0d  call    cs:__imp_FsRtlCheckOplockEx
0x14002bc14  nop     dword ptr [rax+rax+00h]
0x14002bc19  mov     [rsi], eax
0x14002bc1b  cmp     [rsp+0D8h+arg_A8], 0
0x14002bc23  jz      short loc_14002BC4C
0x14002bc25  test    eax, eax
0x14002bc27  jnz     short loc_14002BC50
0x14002bc29  mov     rcx, [rdi]
0x14002bc2c  mov     r8d, [rcx+0E4h]
0x14002bc33  inc     r8d; OpenCount
0x14002bc36  add     rcx, 58h ; 'X'; Oplock
0x14002bc3a  mov     rdx, [rbx+28h]; Irp
0x14002bc3e  call    cs:__imp_FsRtlOplockFsctrl
0x14002bc45  nop     dword ptr [rax+rax+00h]
0x14002bc4a  mov     [rsi], eax
0x14002bc4c  test    eax, eax
0x14002bc4e  jz      short loc_14002BC61
0x14002bc50  mov     [rbx+48h], eax
0x14002bc53  mov     ecx, eax; Status
0x14002bc55  call    cs:__imp_ExRaiseStatus
0x14002bc61  mov     ecx, dword ptr [rsp+0D8h+BugCheckParameter2]
0x14002bc68  mov     eax, ecx
0x14002bc6a  test    ecx, ecx
0x14002bc6c  jz      loc_14002BD47
0x14002bc72  sub     eax, 1
0x14002bc75  jz      short loc_14002BCB2
0x14002bc77  sub     eax, 2
0x14002bc7a  jz      short loc_14002BCB2
0x14002bc7c  sub     eax, 1
0x14002bc7f  jz      loc_14002BD47
0x14002bc85  cmp     eax, 1
0x14002bc88  jz      loc_14002BD47
0x14002bc8e  mov     r8d, ecx; BugCheckParameter2
0x14002bc91  mov     [rsp+0D8h+CompletionRoutine], 0; BugCheckParameter4
0x14002bc9a  xor     r9d, r9d; BugCheckParameter3
0x14002bc9d  mov     edx, 615BBh; BugCheckParameter1
0x14002bca2  lea     ecx, [r9+23h]; BugCheckCode
  ... truncated ...
```
