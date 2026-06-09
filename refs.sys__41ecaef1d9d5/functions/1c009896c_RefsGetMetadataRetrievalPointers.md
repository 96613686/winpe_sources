# RefsGetMetadataRetrievalPointers

- ea: `0x1c009896c`
- end: `0x1c009944f`
- name: `RefsGetMetadataRetrievalPointers`
- size: `2787`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1c015c128`

## callees

- `0x1c0004300`
- `0x1c0004484`
- `0x1c00049a0`
- `0x1c0004a30`
- `0x1c0005450`
- `0x1c0005768`
- `0x1c000f770`
- `0x1c0013f90`
- `0x1c0063db0`
- `0x1c0068168`
- `0x1c0068960`
- `0x1c009896c`
- `0x1c009df4c`
- `0x1c00b29f0`
- `0x1c00b2a20`
- `0x1c015ac58`
- `0x1c016154c`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1c00991df`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c009943b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c00991df`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c009943b`
- `ntoskrnl!ProbeForWrite` at `0x1c0098df3`
- `ntoskrnl!ProbeForWrite` at `0x1c0098df3`
- `ntoskrnl!ProbeForRead` at `0x1c0098dda`
- `ntoskrnl!ProbeForRead` at `0x1c0098dda`

## pseudocode

```c
__int64 __fastcall RefsGetMetadataRetrievalPointers(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v6; // ebx
  __int64 v7; // rsi
  SIZE_T v8; // r12
  unsigned int v9; // ebx
  _QWORD *v10; // r13
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // r15d
  __int64 v14; // rbx
  __int64 v15; // rbx
  __int64 v16; // rdx
  __int64 v17; // r8
  int v18; // eax
  NTSTATUS v19; // ebx
  __int64 v20; // rbx
  __int64 v21; // rsi
  int v22; // eax
  int v23; // eax
  __int64 v24; // rbx
  __int64 v25; // rdx
  unsigned int v26; // ecx
  unsigned int v27; // esi
  __int64 v28; // r8
  __int64 v29; // rax
  int v30; // eax
  unsigned int Status; // [rsp+44h] [rbp-94h]
  int Statusa; // [rsp+44h] [rbp-94h]
  unsigned int Statusb; // [rsp+44h] [rbp-94h]
  char v35; // [rsp+48h] [rbp-90h]
  char v36; // [rsp+49h] [rbp-8Fh]
  unsigned int v37; // [rsp+4Ch] [rbp-8Ch]
  unsigned int v38; // [rsp+50h] [rbp-88h]
  __int64 v39; // [rsp+58h] [rbp-80h] BYREF
  SIZE_T Length; // [rsp+60h] [rbp-78h]
  __int64 v41; // [rsp+68h] [rbp-70h] BYREF
  __int64 v42; // [rsp+70h] [rbp-68h] BYREF
  __int64 v43; // [rsp+78h] [rbp-60h]
  __int64 v44; // [rsp+80h] [rbp-58h]
  __int64 v45; // [rsp+88h] [rbp-50h] BYREF
  __int64 v46; // [rsp+90h] [rbp-48h]
  __int64 v47; // [rsp+98h] [rbp-40h] BYREF
  __int64 v48; // [rsp+A0h] [rbp-38h]

  v44 = a1;
  v41 = 0;
  v42 = 0;
  v39 = 0;
  v45 = 0;
  v37 = 0;
  v47 = -1;
  v48 = 0;
  v36 = 0;
  v35 = 0;
  if ( (dword_1C012E0B0 & 0x20000) == 0 )
  {
    v6 = -1073741637;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741637);
    RefsExtendedCompleteRequestInternal(a1, a2, 3221225659LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 183, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225659LL);
    }
    if ( !RefsStatusDebugEnabled )
      return v6;
    goto LABEL_142;
  }
  *(_DWORD *)(a1 + 8) |= 1u;
  v7 = *(_QWORD *)(a2 + 184);
  v8 = *(unsigned int *)(v7 + 16);
  v9 = *(_DWORD *)(v7 + 8);
  LODWORD(Length) = v9;
  v10 = (_QWORD *)RefsMapUserBuffer(a2, a2, a3, a4);
  v13 = RefsDecodeFileObject(
          a1,
          *(_QWORD *)(v7 + 48),
          (unsigned int)&v41,
          (unsigned int)&v42,
          (__int64)&v39,
          (__int64)&v45,
          0);
  if ( (unsigned int)(v13 - 2) > 2 || (unsigned int)v8 < 8 )
  {
    v6 = -1073741811;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811);
    RefsExtendedCompleteRequestInternal(a1, a2, 3221225485LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 184, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225485LL);
    }
    if ( !RefsStatusDebugEnabled )
      return v6;
LABEL_142:
    RefsStatusDebug(v6);
    return v6;
  }
  if ( v9 < 0x20 )
  {
    v6 = -1073741789;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741789);
    RefsExtendedCompleteRequestInternal(a1, a2, 3221225507LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 185, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225507LL);
    }
    if ( !RefsStatusDebugEnabled )
      return v6;
    goto LABEL_142;
  }
  if ( v13 == 4 )
  {
    if ( (*(_WORD *)(v45 + 88) & 0x200) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 186, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225506LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741790);
      Status = -1073741790;
      goto LABEL_119;
    }
    LOBYTE(v11) = 1;
    v14 = v41;
    RefsAcquireSharedVcb(a1, v41, v11, v12);
    v36 = 1;
    if ( (*(_DWORD *)(v14 + 4) & 1) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 187, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221226094LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741202);
      Status = -1073741202;
      goto LABEL_119;
    }
    v39 = *(_QWORD *)(v14 + 72);
    v42 = *(_QWORD *)(v39 + 120);
  }
  *(_DWORD *)(a1 + 4) |= 0x10000u;
  v15 = v39;
  RefsAcquireFcbWithPaging(a1, *(_QWORD *)(v39 + 120), v39, 4);
  v35 = 1;
  v18 = *(_DWORD *)(v15 + 304);
  if ( (v18 & 0x10000) != 0 )
    v19 = -1073741202;
  else
    v19 = (v18 & 0x1000000) != 0 ? 0xC0000008 : 0;
  Statusa = v19;
  if ( v19 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        188,
        WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids,
        (unsigned int)v19);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(v19);
    RefsRaiseStatusInternal(a1, (unsigned int)v19);
  }
  if ( !(unsigned __int8)RefsIsFileOpen(v42, v16, v17) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 189, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225768LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741528);
    RefsRaiseStatusInternal(a1, 3221225768LL);
  }
  if ( *(_BYTE *)(a2 + 64) )
  {
    ProbeForRead(*(volatile void **)(v7 + 32), v8, 1u);
    ProbeForWrite(v10, (unsigned int)Length, 1u);
  }
  v20 = **(_QWORD **)(v7 + 32);
  v43 = v20;
  if ( (unsigned int)v8 > 8 )
  {
    v37 = *(_DWORD *)(*(_QWORD *)(v7 + 32) + 8LL);
    v20 = v43;
  }
  *(_DWORD *)v10 = 0;
  v10[1] = 0;
  v21 = v39;
  v22 = *(_DWORD *)(v39 + 136);
  if ( (v22 & 0x20) == 0 && *(_DWORD *)(v39 + 200) != 160 )
  {
    RefsUpdateScbFromAttribute(a1, v39, 0);
    v22 = *(_DWORD *)(v21 + 136);
  }
  if ( (v22 & 8) != 0 )
  {
    *(_QWORD *)(a2 + 56) = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 190, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225489LL);
    }
    if ( !RefsStatusDebugEnabled )
      goto LABEL_72;
    goto LABEL_71;
  }
  if ( v20 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 191, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225485LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811);
    Status = -1073741811;
    goto LABEL_119;
  }
  if ( v13 == 4 )
  {
    RefsBindMinstoreTransaction(a1);
    v23 = MsLookupVolumeMetadataAllocation(*(_QWORD *)(a1 + 24), v37, v20, &v47);
LABEL_86:
    Statusa = v23;
    goto LABEL_87;
  }
  if ( v13 == 3 || v13 == 2 )
  {
    RefsBindMinstoreTransaction(a1);
    v23 = MsLookupStreamMetadataAllocation();
    goto LABEL_86;
  }
LABEL_87:
  if ( Statusa != -1073741197 )
  {
    if ( Statusa < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          193,
          WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids,
          (unsigned int)Statusa);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(Statusa);
      RefsRaiseStatusInternal(a1, (unsigned int)Statusa);
    }
    v24 = v43;
    v25 = v47;
    if ( v47 != -1 )
      v24 = v47;
    v43 = v24;
    v46 = v24;
    v10[1] = v24;
    v26 = 0;
    v27 = Length;
    while ( 16 * (v26 + 2) <= v27 )
    {
      v28 = v24 + v48;
      v24 = v28;
      v29 = 2LL * v26;
      v10[v29 + 2] = v28;
      v10[v29 + 3] = v25;
      ++*(_DWORD *)v10;
      v38 = v26 + 1;
      if ( v13 == 2 || v13 == 3 )
        v30 = MsLookupStreamMetadataAllocation();
      else
        v30 = MsLookupVolumeMetadataAllocation(*(_QWORD *)(a1 + 24), v37, v28, &v47);
      Statusb = v30;
      if ( v30 == -1073741197 )
      {
        *(_QWORD *)(a2 + 56) = (int)(16 * (v38 + 1));
        Status = 0;
        goto LABEL_119;
      }
      if ( v30 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            195,
            WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids,
            (unsigned int)v30);
        }
        if ( RefsStatusDebugEnabled )
          RefsStatusDebug(Statusb);
        RefsRaiseStatusInternal(a1, Statusb);
      }
      v46 = v24;
      v26 = v38;
      v25 = v47;
    }
    *(_QWORD *)(a2 + 56) = (int)(16 * (v26 + 1));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 194, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 2147483653LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-2147483643);
    Status = -2147483643;
    goto LABEL_119;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 192, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225489LL);
  }
  if ( !RefsStatusDebugEnabled )
    goto LABEL_72;
LABEL_71:
  RefsStatusDebug(-1073741807);
LABEL_72:
  Status = -1073741807;
LABEL_119:
  if ( v35 )
    RefsReleaseFcbWithPaging(a1, *(_QWORD *)(v39 + 120));
  if ( v36 )
    ExReleaseResourceLite((PERESOURCE)(v41 + 1424));
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(Status);
  RefsExtendedCompleteRequestInternal(a1, a2, Status);
  return Status;
}

```

## disassembly

```asm
0x1c009896c  mov     r11, rsp
0x1c009896f  mov     [r11+18h], rbx
0x1c0098973  mov     [r11+20h], rsi
0x1c0098977  push    rdi
0x1c0098978  push    r12
0x1c009897a  push    r13
0x1c009897c  push    r14
0x1c009897e  push    r15
0x1c0098980  sub     rsp, 0B0h
0x1c0098987  mov     rax, cs:__security_cookie
0x1c009898e  xor     rax, rsp
0x1c0098991  mov     [rsp+0D8h+var_30], rax
0x1c0098999  mov     r14, rdx
0x1c009899c  mov     rdi, rcx
0x1c009899f  mov     [rsp+0D8h+var_58], rcx
0x1c00989a7  xor     r15d, r15d
0x1c00989aa  mov     [r11-70h], r15
0x1c00989ae  mov     [r11-68h], r15
0x1c00989b2  mov     [r11-80h], r15
0x1c00989b6  mov     [r11-50h], r15
0x1c00989ba  mov     [rsp+0D8h+var_8C], r15d
0x1c00989bf  or      qword ptr [r11-40h], 0FFFFFFFFFFFFFFFFh
0x1c00989c4  mov     [r11-38h], r15
0x1c00989c8  mov     [rsp+0D8h+var_98], r15b
0x1c00989cd  mov     [rsp+0D8h+var_8F], r15b
0x1c00989d2  mov     [rsp+0D8h+var_90], r15b
0x1c00989d7  test    cs:dword_1C012E0B0, 20000h
0x1c00989e1  jnz     loc_1C0098A6B
0x1c00989e7  mov     al, cs:RefsStatusDebugEnabled
0x1c00989ed  mov     ebx, 0C00000BBh
0x1c00989f2  test    al, al
0x1c00989f4  jz      short loc_1C0098A0A
0x1c00989f6  mov     r8d, 1F1Dh
0x1c00989fc  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c0098a03  mov     ecx, ebx; Status
0x1c0098a05  call    RefsStatusDebug
0x1c0098a0a  mov     r8d, ebx
0x1c0098a0d  mov     rdx, r14
0x1c0098a10  mov     rcx, rdi
0x1c0098a13  call    RefsExtendedCompleteRequestInternal
0x1c0098a18  lea     rax, WPP_GLOBAL_Control
0x1c0098a1f  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0098a26  cmp     rcx, rax
0x1c0098a29  jz      short loc_1C0098A52
0x1c0098a2b  test    dword ptr [rcx+2Ch], 100h
0x1c0098a32  jz      short loc_1C0098A52
0x1c0098a34  cmp     byte ptr [rcx+29h], 4
0x1c0098a38  jb      short loc_1C0098A52
0x1c0098a3a  mov     edx, 0B7h
0x1c0098a3f  mov     r9d, ebx
0x1c0098a42  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c0098a49  mov     rcx, [rcx+18h]
0x1c0098a4d  call    WPP_SF_D
0x1c0098a52  mov     cl, cs:RefsStatusDebugEnabled
0x1c0098a58  test    cl, cl
0x1c0098a5a  jz      loc_1C00993AE
0x1c0098a60  mov     r8d, 1F1Eh
0x1c0098a66  jmp     loc_1C00993A0
0x1c0098a6b  or      dword ptr [rcx+8], 1
0x1c0098a6f  mov     rsi, [rdx+0B8h]
0x1c0098a76  mov     r12d, [rsi+10h]
0x1c0098a7a  mov     ebx, [rsi+8]
0x1c0098a7d  mov     dword ptr [rsp+0D8h+Length], ebx
0x1c0098a81  mov     rcx, r14
0x1c0098a84  call    RefsMapUserBuffer
0x1c0098a89  mov     r13, rax
0x1c0098a8c  mov     [rsp+0D8h+var_A8], r15b
0x1c0098a91  lea     rax, [rsp+0D8h+var_50]
0x1c0098a99  mov     [rsp+0D8h+var_B0], rax
0x1c0098a9e  lea     rax, [rsp+0D8h+var_80]
0x1c0098aa3  mov     [rsp+0D8h+var_B8], rax
0x1c0098aa8  lea     r9, [rsp+0D8h+var_68]
0x1c0098aad  lea     r8, [rsp+0D8h+var_70]
0x1c0098ab2  mov     rdx, [rsi+30h]
0x1c0098ab6  mov     rcx, rdi
0x1c0098ab9  call    RefsDecodeFileObject
0x1c0098abe  mov     r15d, eax
0x1c0098ac1  lea     ecx, [rax-2]
0x1c0098ac4  cmp     ecx, 2
0x1c0098ac7  ja      loc_1C0099325
0x1c0098acd  cmp     r12d, 8
0x1c0098ad1  jb      loc_1C0099325
0x1c0098ad7  cmp     ebx, 20h ; ' '
0x1c0098ada  jnb     loc_1C0098B64
0x1c0098ae0  mov     al, cs:RefsStatusDebugEnabled
0x1c0098ae6  mov     ebx, 0C0000023h
0x1c0098aeb  test    al, al
0x1c0098aed  jz      short loc_1C0098B03
0x1c0098aef  mov     r8d, 1F4Dh
0x1c0098af5  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c0098afc  mov     ecx, ebx; Status
0x1c0098afe  call    RefsStatusDebug
0x1c0098b03  mov     r8d, ebx
0x1c0098b06  mov     rdx, r14
0x1c0098b09  mov     rcx, rdi
0x1c0098b0c  call    RefsExtendedCompleteRequestInternal
0x1c0098b11  lea     rax, WPP_GLOBAL_Control
0x1c0098b18  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0098b1f  cmp     rcx, rax
0x1c0098b22  jz      short loc_1C0098B4B
0x1c0098b24  test    dword ptr [rcx+2Ch], 100h
0x1c0098b2b  jz      short loc_1C0098B4B
0x1c0098b2d  cmp     byte ptr [rcx+29h], 4
0x1c0098b31  jb      short loc_1C0098B4B
0x1c0098b33  mov     edx, 0B9h
0x1c0098b38  mov     r9d, ebx
0x1c0098b3b  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c0098b42  mov     rcx, [rcx+18h]
0x1c0098b46  call    WPP_SF_D
0x1c0098b4b  mov     cl, cs:RefsStatusDebugEnabled
0x1c0098b51  test    cl, cl
0x1c0098b53  jz      loc_1C00993AE
0x1c0098b59  mov     r8d, 1F4Eh
0x1c0098b5f  jmp     loc_1C00993A0
0x1c0098b64  cmp     r15d, 4
0x1c0098b68  jnz     loc_1C0098C93
0x1c0098b6e  mov     rax, [rsp+0D8h+var_50]
0x1c0098b76  movzx   ecx, word ptr [rax+58h]
0x1c0098b7a  mov     eax, 200h
0x1c0098b7f  test    ax, cx
0x1c0098b82  jnz     short loc_1C0098BF2
0x1c0098b84  lea     rax, WPP_GLOBAL_Control
0x1c0098b8b  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0098b92  cmp     rcx, rax
0x1c0098b95  jz      short loc_1C0098BC1
0x1c0098b97  mov     eax, [rcx+2Ch]
0x1c0098b9a  bt      eax, 8
0x1c0098b9e  jnb     short loc_1C0098BC1
0x1c0098ba0  cmp     [rcx+29h], r15b
0x1c0098ba4  jb      short loc_1C0098BC1
0x1c0098ba6  mov     edx, 0BAh
0x1c0098bab  mov     r9d, 0C0000022h
0x1c0098bb1  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c0098bb8  mov     rcx, [rcx+18h]
0x1c0098bbc  call    WPP_SF_D
0x1c0098bc1  mov     al, cs:RefsStatusDebugEnabled
0x1c0098bc7  xor     r12d, r12d
0x1c0098bca  test    al, al
0x1c0098bcc  jz      short loc_1C0098BE5
0x1c0098bce  mov     r8d, 1F60h
0x1c0098bd4  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c0098bdb  mov     ecx, 0C0000022h; Status
0x1c0098be0  call    RefsStatusDebug
0x1c0098be5  mov     [rsp+0D8h+Status], 0C0000022h
0x1c0098bed  jmp     loc_1C00991B4
0x1c0098bf2  mov     r8b, 1
0x1c0098bf5  mov     rbx, [rsp+0D8h+var_70]
0x1c0098bfa  mov     rdx, rbx
0x1c0098bfd  mov     rcx, rdi
0x1c0098c00  call    RefsAcquireSharedVcb
0x1c0098c05  mov     [rsp+0D8h+var_8F], 1
0x1c0098c0a  mov     eax, [rbx+4]
0x1c0098c0d  test    al, 1
0x1c0098c0f  jnz     short loc_1C0098C81
0x1c0098c11  lea     rax, WPP_GLOBAL_Control
0x1c0098c18  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0098c1f  cmp     rcx, rax
0x1c0098c22  jz      short loc_1C0098C52
0x1c0098c24  mov     eax, [rcx+2Ch]
0x1c0098c27  bt      eax, 8
0x1c0098c2b  jnb     short loc_1C0098C52
0x1c0098c2d  cmp     byte ptr [rcx+29h], 4
0x1c0098c31  jb      short loc_1C0098C52
0x1c0098c33  mov     edx, 0BBh
0x1c0098c38  mov     ebx, 0C000026Eh
0x1c0098c3d  mov     r9d, ebx
0x1c0098c40  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c0098c47  mov     rcx, [rcx+18h]
0x1c0098c4b  call    WPP_SF_D
0x1c0098c50  jmp     short loc_1C0098C57
0x1c0098c52  mov     ebx, 0C000026Eh
0x1c0098c57  mov     al, cs:RefsStatusDebugEnabled
0x1c0098c5d  xor     r12d, r12d
0x1c0098c60  test    al, al
0x1c0098c62  jz      short loc_1C0098C78
0x1c0098c64  mov     r8d, 1F6Dh
0x1c0098c6a  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c0098c71  mov     ecx, ebx; Status
0x1c0098c73  call    RefsStatusDebug
0x1c0098c78  mov     [rsp+0D8h+Status], ebx
0x1c0098c7c  jmp     loc_1C00991B4
0x1c0098c81  mov     rbx, [rbx+48h]
0x1c0098c85  mov     [rsp+0D8h+var_80], rbx
0x1c0098c8a  mov     rax, [rbx+78h]
0x1c0098c8e  mov     [rsp+0D8h+var_68], rax
0x1c0098c93  bts     dword ptr [rdi+4], 10h
0x1c0098c98  mov     r9d, 4
0x1c0098c9e  mov     rbx, [rsp+0D8h+var_80]
0x1c0098ca3  mov     r8, rbx
0x1c0098ca6  mov     rdx, [rbx+78h]
0x1c0098caa  mov     rcx, rdi
0x1c0098cad  call    RefsAcquireFcbWithPaging
0x1c0098cb2  mov     [rsp+0D8h+var_90], 1
0x1c0098cb7  mov     eax, [rbx+130h]
0x1c0098cbd  bt      eax, 10h
0x1c0098cc1  jnb     short loc_1C0098CCA
0x1c0098cc3  mov     ebx, 0C000026Eh
0x1c0098cc8  jmp     short loc_1C0098CD9
0x1c0098cca  and     eax, 1000000h
0x1c0098ccf  neg     eax
0x1c0098cd1  sbb     ebx, ebx
0x1c0098cd3  and     ebx, 0C0000008h
0x1c0098cd9  mov     [rsp+0D8h+Status], ebx
0x1c0098cdd  test    ebx, ebx
0x1c0098cdf  jns     short loc_1C0098D47
0x1c0098ce1  lea     rax, WPP_GLOBAL_Control
0x1c0098ce8  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0098cef  cmp     rcx, rax
0x1c0098cf2  jz      short loc_1C0098D1B
0x1c0098cf4  mov     eax, [rcx+2Ch]
0x1c0098cf7  bt      eax, 8
0x1c0098cfb  jnb     short loc_1C0098D1B
0x1c0098cfd  cmp     byte ptr [rcx+29h], 4
0x1c0098d01  jb      short loc_1C0098D1B
0x1c0098d03  mov     edx, 0BCh
0x1c0098d08  mov     r9d, ebx
0x1c0098d0b  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c0098d12  mov     rcx, [rcx+18h]
0x1c0098d16  call    WPP_SF_D
0x1c0098d1b  mov     al, cs:RefsStatusDebugEnabled
0x1c0098d21  test    al, al
0x1c0098d23  jz      short loc_1C0098D3B
0x1c0098d25  mov     r8d, 1F81h
0x1c0098d2b  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c0098d32  mov     ecx, [rsp+0D8h+Status]; Status
0x1c0098d36  call    RefsStatusDebug
0x1c0098d3b  mov     edx, [rsp+0D8h+Status]
0x1c0098d3f  mov     rcx, rdi
0x1c0098d42  call    RefsRaiseStatusInternal
0x1c0098d47  mov     rcx, [rsp+0D8h+var_68]
0x1c0098d4c  call    RefsIsFileOpen
0x1c0098d51  test    al, al
0x1c0098d53  jnz     short loc_1C0098DC1
0x1c0098d55  lea     rax, WPP_GLOBAL_Control
0x1c0098d5c  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0098d63  cmp     rcx, rax
0x1c0098d66  jz      short loc_1C0098D92
0x1c0098d68  mov     eax, [rcx+2Ch]
0x1c0098d6b  bt      eax, 8
0x1c0098d6f  jnb     short loc_1C0098D92
0x1c0098d71  cmp     byte ptr [rcx+29h], 4
0x1c0098d75  jb      short loc_1C0098D92
0x1c0098d77  mov     edx, 0BDh
0x1c0098d7c  mov     r9d, 0C0000128h
0x1c0098d82  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c0098d89  mov     rcx, [rcx+18h]
0x1c0098d8d  call    WPP_SF_D
0x1c0098d92  mov     al, cs:RefsStatusDebugEnabled
0x1c0098d98  test    al, al
0x1c0098d9a  jz      short loc_1C0098DB3
0x1c0098d9c  mov     r8d, 1F86h
0x1c0098da2  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c0098da9  mov     ecx, 0C0000128h; Status
0x1c0098dae  call    RefsStatusDebug
0x1c0098db3  mov     edx, 0C0000128h
0x1c0098db8  mov     rcx, rdi
0x1c0098dbb  call    RefsRaiseStatusInternal
0x1c0098dc0  nop
0x1c0098dc1  mov     [rsp+0D8h+var_98], 1
0x1c0098dc6  cmp     byte ptr [r14+40h], 0
0x1c0098dcb  jz      short loc_1C0098DFF
0x1c0098dcd  mov     rdx, r12; Length
0x1c0098dd0  mov     r8d, 1; Alignment
0x1c0098dd6  mov     rcx, [rsi+20h]; Address
0x1c0098dda  call    cs:__imp_ProbeForRead
0x1c0098de1  nop     dword ptr [rax+rax+00h]
0x1c0098de6  mov     edx, dword ptr [rsp+0D8h+Length]; Length
0x1c0098dea  mov     r8d, 1; Alignment
0x1c0098df0  mov     rcx, r13; Address
0x1c0098df3  call    cs:__imp_ProbeForWrite
0x1c0098dfa  nop     dword ptr [rax+rax+00h]
0x1c0098dff  mov     rax, [rsi+20h]
0x1c0098e03  mov     rbx, [rax]
0x1c0098e06  mov     [rsp+0D8h+var_60], rbx
0x1c0098e0b  cmp     r12d, 8
0x1c0098e0f  jbe     short loc_1C0098E21
0x1c0098e11  mov     rax, [rsi+20h]
0x1c0098e15  mov     ecx, [rax+8]
0x1c0098e18  mov     [rsp+0D8h+var_8C], ecx
0x1c0098e1c  mov     rbx, [rsp+0D8h+var_60]
0x1c0098e21  xor     r12d, r12d
0x1c0098e24  mov     [r13+0], r12d
0x1c0098e28  mov     [r13+8], r12
0x1c0098e2c  mov     [rsp+0D8h+var_98], r12b
0x1c0098e31  mov     rsi, [rsp+0D8h+var_80]
0x1c0098e36  mov     eax, [rsi+88h]
0x1c0098e3c  test    al, 20h
0x1c0098e3e  jnz     short loc_1C0098E60
0x1c0098e40  cmp     dword ptr [rsi+0C8h], 0A0h
0x1c0098e4a  jz      short loc_1C0098E60
0x1c0098e4c  xor     r8d, r8d
0x1c0098e4f  mov     rdx, rsi
0x1c0098e52  mov     rcx, rdi
0x1c0098e55  call    RefsUpdateScbFromAttribute
0x1c0098e5a  mov     eax, [rsi+88h]
0x1c0098e60  test    al, 8
0x1c0098e62  jz      short loc_1C0098ED3
0x1c0098e64  mov     [r14+38h], r12
0x1c0098e68  lea     rax, WPP_GLOBAL_Control
0x1c0098e6f  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
