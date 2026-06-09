# ClfsCreateScanContext

- ea: `0x14006f400`
- end: `0x14006f8e9`
- name: `ClfsCreateScanContext`
- size: `1257`
- prototype: `NTSTATUS __stdcall(PLOG_FILE_OBJECT plfoLog, ULONG cFromContainer, ULONG cContainers, CLFS_SCAN_MODE eScanMode, PCLFS_SCAN_CONTEXT pcxScan)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140034e0c`
- `0x14006f1f4`

## callees

- `0x14000ed64`
- `0x140011d90`
- `0x14004d2d8`
- `0x14006f400`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14006f541`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006f541`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006f829`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007bbdd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006f829`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007bbdd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f7e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bb85`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f7e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bb85`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14006f6b4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14006f6b4`

## string_xrefs

- `0x14006f44f`: `ClfsCreateScanContext`
- `0x14006f5bb`: `ClfsCreateScanContext`
- `0x14006f857`: `ClfsCreateScanContext`
- `0x14006f8c0`: `ClfsCreateScanContext`

## pseudocode

```c
NTSTATUS __stdcall ClfsCreateScanContext(
        PLOG_FILE_OBJECT plfoLog,
        ULONG cFromContainer,
        ULONG cContainers,
        CLFS_SCAN_MODE eScanMode,
        PCLFS_SCAN_CONTEXT pcxScan)
{
  PLOG_FILE_OBJECT v6; // rdx
  char v7; // al
  CLFS_SCAN_CONTEXT *v8; // rdi
  char v9; // al
  PCLS_CONTAINER_INFORMATION pinfoContainer; // rax
  NTSTATUS v11; // ebx
  CClfsBaseFile *v12; // rcx
  int v13; // edx
  __int64 v14; // rcx
  WCHAR *v15; // rcx
  ULONG v16; // eax
  CClfsBaseFile *v17; // r10
  CLFS_SCAN_CONTEXT *PoolWithTag; // rax
  char v20; // [rsp+20h] [rbp-58h]
  int v21; // [rsp+28h] [rbp-50h]
  char v22; // [rsp+30h] [rbp-48h]
  WCHAR *P; // [rsp+38h] [rbp-40h]
  ULONG v26; // [rsp+90h] [rbp+18h]

  v26 = cContainers;
  v6 = plfoLog;
  if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      94,
      (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
      (unsigned int)"ClfsCreateScanContext",
      130);
    cContainers = v26;
    v6 = plfoLog;
  }
  v7 = eScanMode & 4;
  if ( (eScanMode & 2) == 0 && !v7 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        95,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsCreateScanContext",
        143,
        -1073741811);
    }
    return -1073741811;
  }
  if ( (eScanMode & 2) != 0 && v7 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        96,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsCreateScanContext",
        155,
        -1073741811);
    }
    return -1073741811;
  }
  if ( (eScanMode & 8) != 0 || (eScanMode & 0x10) != 0 || (eScanMode & 0x20) != 0 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        97,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsCreateScanContext",
        169,
        -1073741811);
    }
    return -1073741811;
  }
  if ( !v6 || !pcxScan || (v8 = 0, P = 0, !cContainers) )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        98,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsCreateScanContext",
        184,
        -1073741811);
    }
    return -1073741811;
  }
  KeEnterCriticalRegion();
  v9 = eScanMode & 1;
  v22 = eScanMode & 1;
  if ( (eScanMode & 1) == 0 )
  {
    *(_OWORD *)&pcxScan->cidNode.cType = 0;
    *(_OWORD *)&pcxScan->cIndex = 0;
    *(_OWORD *)&pcxScan->cContainersReturned = 0;
    pcxScan->pinfoContainer = 0;
    PoolWithTag = (CLFS_SCAN_CONTEXT *)ExAllocatePoolWithTag(PagedPool, 576 * v26 + 56, 0x73666C43u);
    v15 = (WCHAR *)PoolWithTag;
    P = (WCHAR *)PoolWithTag;
    if ( !PoolWithTag )
    {
      v11 = -1073741670;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClfsBaseFile *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) == 0 )
      {
        goto LABEL_49;
      }
      v13 = 102;
      v21 = -1073741670;
      v20 = 15;
LABEL_35:
      v14 = *((_QWORD *)v17 + 3);
      goto LABEL_28;
    }
    v8 = PoolWithTag;
    PoolWithTag->cidNode.cType = -1040322546;
    PoolWithTag->cidNode.cbNode = 56;
    PoolWithTag->plfoLog = plfoLog;
    PoolWithTag->pinfoContainer = (PCLS_CONTAINER_INFORMATION)&PoolWithTag[1];
    v16 = v26;
    goto LABEL_44;
  }
  if ( pcxScan->cidNode.cType != -1040322546 || pcxScan->cidNode.cbNode != 56 )
  {
    v11 = -1073741811;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) == 0 )
        goto LABEL_29;
      v13 = 99;
      v21 = -1073741811;
      v20 = -48;
      goto LABEL_27;
    }
    goto LABEL_48;
  }
  pinfoContainer = pcxScan->pinfoContainer;
  if ( pinfoContainer )
  {
    v8 = (CLFS_SCAN_CONTEXT *)&pinfoContainer[-1].FileName[236];
    v15 = &pinfoContainer[-1].FileName[236];
    P = &pinfoContainer[-1].FileName[236];
    if ( *(PLOG_FILE_OBJECT *)&pinfoContainer[-1].FileName[240] != plfoLog || (v16 = v26, v8->cContainers < v26) )
    {
      v11 = -1073741811;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClfsBaseFile *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) == 0 )
      {
        goto LABEL_49;
      }
      v13 = 101;
      v21 = -1073741811;
      v20 = -13;
      goto LABEL_35;
    }
LABEL_44:
    v8->cIndex = cFromContainer;
    v8->cContainers = v16;
    v8->cContainersReturned = 0;
    v8->eScanMode = eScanMode | 1;
    v11 = ClfsScanLogContainersInternal(v8);
    v9 = v22;
    if ( v11 < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) == 0 )
          goto LABEL_29;
        v13 = 103;
        v21 = v11;
        v20 = 55;
        goto LABEL_27;
      }
    }
LABEL_48:
    v15 = P;
    goto LABEL_50;
  }
  v11 = -1073741811;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CClfsBaseFile *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) == 0 )
  {
    goto LABEL_29;
  }
  v13 = 100;
  v21 = -1073741811;
  v20 = -34;
LABEL_27:
  v14 = *((_QWORD *)v12 + 3);
LABEL_28:
  WPP_SF_slD(
    v14,
    v13,
    (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
    (unsigned int)"ClfsCreateScanContext",
    v20,
    v21);
LABEL_29:
  v15 = P;
LABEL_49:
  v9 = v22;
LABEL_50:
  if ( v11 >= 0 || v9 )
  {
    if ( v8 )
    {
      if ( v8->cContainersReturned )
        v8->eScanMode |= 0x30u;
      *pcxScan = *v8;
    }
  }
  else
  {
    pcxScan->plfoLog = 0;
    if ( v15 )
      ExFreePoolWithTag(v15, 0);
    pcxScan->eScanMode &= ~0x10u;
  }
  KeLeaveCriticalRegion();
  if ( v11 >= 0
    && WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      104,
      (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
      (unsigned int)"ClfsCreateScanContext",
      109);
  }
  return v11;
}

```

## disassembly

```asm
0x14006f400  mov     rax, rsp
0x14006f403  mov     [rax+20h], r9b
0x14006f407  mov     [rax+18h], r8d
0x14006f40b  mov     [rax+10h], edx
0x14006f40e  mov     [rax+8], rcx
0x14006f412  push    rbx
0x14006f413  push    rsi
0x14006f414  push    rdi
0x14006f415  push    r12
0x14006f417  push    r13
0x14006f419  sub     rsp, 50h
0x14006f41d  mov     bl, r9b
0x14006f420  mov     rdx, rcx
0x14006f423  lea     r12, WPP_GLOBAL_Control
0x14006f42a  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f431  mov     esi, 4000000h
0x14006f436  cmp     rcx, r12
0x14006f439  jz      short loc_14006F476
0x14006f43b  mov     eax, [rcx+2Ch]
0x14006f43e  test    esi, eax
0x14006f440  jz      short loc_14006F476
0x14006f442  mov     edx, 5Eh ; '^'
0x14006f447  mov     dword ptr [rsp+78h+var_58], 0B82h
0x14006f44f  lea     r9, aClfscreatescan; "ClfsCreateScanContext"
0x14006f456  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14006f45d  mov     rcx, [rcx+18h]
0x14006f461  call    WPP_SF_sd
0x14006f466  mov     r8d, [rsp+78h+arg_10]
0x14006f46e  mov     rdx, [rsp+78h+arg_0]
0x14006f476  mov     cl, bl
0x14006f478  mov     al, bl
0x14006f47a  and     al, 4
0x14006f47c  and     cl, 2
0x14006f47f  jnz     short loc_14006F4B8
0x14006f481  test    al, al
0x14006f483  jnz     short loc_14006F4B8
0x14006f485  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f48c  cmp     rcx, r12
0x14006f48f  jz      loc_14006F8D7
0x14006f495  test    [rcx+2Ch], esi
0x14006f498  jz      loc_14006F8D7
0x14006f49e  mov     edx, 5Fh ; '_'
0x14006f4a3  mov     [rsp+78h+var_50], 0C000000Dh
0x14006f4ab  mov     dword ptr [rsp+78h+var_58], 0B8Fh
0x14006f4b3  jmp     loc_14006F8C0
0x14006f4b8  test    cl, cl
0x14006f4ba  jz      short loc_14006F4F3
0x14006f4bc  test    al, al
0x14006f4be  jz      short loc_14006F4F3
0x14006f4c0  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f4c7  cmp     rcx, r12
0x14006f4ca  jz      loc_14006F8D7
0x14006f4d0  test    [rcx+2Ch], esi
0x14006f4d3  jz      loc_14006F8D7
0x14006f4d9  mov     edx, 60h ; '`'
0x14006f4de  mov     [rsp+78h+var_50], 0C000000Dh
0x14006f4e6  mov     dword ptr [rsp+78h+var_58], 0B9Bh
0x14006f4ee  jmp     loc_14006F8C0
0x14006f4f3  test    bl, 8
0x14006f4f6  jnz     loc_14006F89A
0x14006f4fc  test    bl, 10h
0x14006f4ff  jnz     loc_14006F89A
0x14006f505  test    bl, 20h
0x14006f508  jnz     loc_14006F89A
0x14006f50e  test    rdx, rdx
0x14006f511  jz      loc_14006F872
0x14006f517  mov     r13, [rsp+78h+pcxScan]
0x14006f51f  test    r13, r13
0x14006f522  jz      loc_14006F872
0x14006f528  xor     edi, edi
0x14006f52a  mov     [rsp+78h+var_38], rdi
0x14006f52f  mov     [rsp+78h+P], rdi
0x14006f534  mov     [rsp+78h+var_44], edi
0x14006f538  test    r8d, r8d
0x14006f53b  jz      loc_14006F872
0x14006f541  call    cs:__imp_KeEnterCriticalRegion
0x14006f548  nop     dword ptr [rax+rax+00h]
0x14006f54d  mov     al, bl
0x14006f54f  and     al, 1
0x14006f551  mov     [rsp+78h+var_48], al
0x14006f555  mov     [rsp+78h+var_47], al
0x14006f559  jz      loc_14006F681
0x14006f55f  cmp     dword ptr [r13+0], 0C1FDF00Eh
0x14006f567  jnz     loc_14006F643
0x14006f56d  cmp     dword ptr [r13+4], 38h ; '8'
0x14006f572  jnz     loc_14006F643
0x14006f578  mov     rax, [r13+30h]
0x14006f57c  test    rax, rax
0x14006f57f  jnz     short loc_14006F5D1
0x14006f581  mov     ebx, 0C000000Dh
0x14006f586  mov     [rsp+78h+var_44], ebx
0x14006f58a  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f591  cmp     rcx, r12
0x14006f594  jz      short loc_14006F5C7
0x14006f596  mov     eax, [rcx+2Ch]
0x14006f599  test    esi, eax
0x14006f59b  jz      short loc_14006F5C7
0x14006f59d  lea     edx, [rdi+64h]
0x14006f5a0  mov     [rsp+78h+var_50], 0C000000Dh
0x14006f5a8  mov     dword ptr [rsp+78h+var_58], 0BDEh
0x14006f5b0  mov     rcx, [rcx+18h]
0x14006f5b4  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14006f5bb  lea     r9, aClfscreatescan; "ClfsCreateScanContext"
0x14006f5c2  call    WPP_SF_slD
0x14006f5c7  mov     rcx, [rsp+78h+P]; P
0x14006f5cc  jmp     loc_14006F7C7
0x14006f5d1  lea     rdi, [rax-38h]
0x14006f5d5  mov     rcx, rdi
0x14006f5d8  mov     [rsp+78h+P], rcx
0x14006f5dd  mov     [rsp+78h+var_38], rdi
0x14006f5e2  mov     rax, [rsp+78h+arg_0]
0x14006f5ea  cmp     [rdi+8], rax
0x14006f5ee  jnz     short loc_14006F600
0x14006f5f0  mov     eax, [rsp+78h+arg_10]
0x14006f5f7  cmp     [rdi+18h], eax
0x14006f5fa  jnb     loc_14006F73A
0x14006f600  mov     ebx, 0C000000Dh
0x14006f605  mov     [rsp+78h+var_44], ebx
0x14006f609  mov     r10, cs:WPP_GLOBAL_Control
0x14006f610  cmp     r10, r12
0x14006f613  jz      loc_14006F7C7
0x14006f619  mov     eax, [r10+2Ch]
0x14006f61d  test    esi, eax
0x14006f61f  jz      loc_14006F7C7
0x14006f625  mov     edx, 65h ; 'e'
0x14006f62a  mov     [rsp+78h+var_50], 0C000000Dh
0x14006f632  mov     dword ptr [rsp+78h+var_58], 0BF3h
0x14006f63a  mov     rcx, [r10+18h]
0x14006f63e  jmp     loc_14006F5B4
0x14006f643  mov     ebx, 0C000000Dh
0x14006f648  mov     [rsp+78h+var_44], ebx
0x14006f64c  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f653  cmp     rcx, r12
0x14006f656  jz      loc_14006F7C0
0x14006f65c  mov     eax, [rcx+2Ch]
0x14006f65f  test    esi, eax
0x14006f661  jz      loc_14006F5C7
0x14006f667  mov     edx, 63h ; 'c'
0x14006f66c  mov     [rsp+78h+var_50], 0C000000Dh
0x14006f674  mov     dword ptr [rsp+78h+var_58], 0BD0h
0x14006f67c  jmp     loc_14006F5B0
0x14006f681  xorps   xmm0, xmm0
0x14006f684  xor     eax, eax
0x14006f686  movups  xmmword ptr [r13+0], xmm0
0x14006f68b  movups  xmmword ptr [r13+10h], xmm0
0x14006f690  movups  xmmword ptr [r13+20h], xmm0
0x14006f695  mov     [r13+30h], rax
0x14006f699  mov     eax, [rsp+78h+arg_10]
0x14006f6a0  lea     edx, [rax+rax*8]
0x14006f6a3  shl     edx, 6
0x14006f6a6  add     edx, 38h ; '8'; NumberOfBytes
0x14006f6a9  mov     ecx, 1; PoolType
0x14006f6ae  mov     r8d, 73666C43h; Tag
0x14006f6b4  call    cs:__imp_ExAllocatePoolWithTag
0x14006f6bb  nop     dword ptr [rax+rax+00h]
0x14006f6c0  mov     rcx, rax
0x14006f6c3  mov     [rsp+78h+P], rax
0x14006f6c8  test    rax, rax
0x14006f6cb  jnz     short loc_14006F70A
0x14006f6cd  mov     ebx, 0C000009Ah
0x14006f6d2  mov     [rsp+78h+var_44], ebx
0x14006f6d6  mov     r10, cs:WPP_GLOBAL_Control
0x14006f6dd  cmp     r10, r12
0x14006f6e0  jz      loc_14006F7C7
0x14006f6e6  mov     eax, [r10+2Ch]
0x14006f6ea  test    esi, eax
0x14006f6ec  jz      loc_14006F7C7
0x14006f6f2  lea     edx, [rcx+66h]
0x14006f6f5  mov     [rsp+78h+var_50], 0C000009Ah
0x14006f6fd  mov     dword ptr [rsp+78h+var_58], 0C0Fh
0x14006f705  jmp     loc_14006F63A
0x14006f70a  mov     rdi, rcx
0x14006f70d  mov     [rsp+78h+var_38], rcx
0x14006f712  mov     dword ptr [rax], 0C1FDF00Eh
0x14006f718  mov     dword ptr [rax+4], 38h ; '8'
0x14006f71f  mov     rax, [rsp+78h+arg_0]
0x14006f727  mov     [rcx+8], rax
0x14006f72b  lea     rax, [rcx+38h]
0x14006f72f  mov     [rcx+30h], rax
0x14006f733  mov     eax, [rsp+78h+arg_10]
0x14006f73a  mov     ecx, [rsp+78h+arg_8]
0x14006f741  mov     [rdi+10h], ecx
0x14006f744  mov     [rdi+18h], eax
0x14006f747  mov     dword ptr [rdi+20h], 0
0x14006f74e  or      bl, 1
0x14006f751  mov     [rdi+28h], bl
0x14006f754  mov     rcx, rdi
0x14006f757  call    ClfsScanLogContainersInternal
0x14006f75c  mov     ebx, eax
0x14006f75e  mov     [rsp+78h+var_44], eax
0x14006f762  mov     al, [rsp+78h+var_48]
0x14006f766  jmp     short loc_14006F78F
0x14006f768  mov     ebx, eax
0x14006f76a  mov     [rsp+78h+var_44], eax
0x14006f76e  lea     r12, WPP_GLOBAL_Control
0x14006f775  mov     esi, 4000000h
0x14006f77a  mov     r13, [rsp+78h+pcxScan]
0x14006f782  mov     rdi, [rsp+78h+var_38]
0x14006f787  mov     al, [rsp+78h+var_47]
0x14006f78b  mov     [rsp+78h+var_48], al
0x14006f78f  test    ebx, ebx
0x14006f791  jns     short loc_14006F7C0
0x14006f793  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f79a  cmp     rcx, r12
0x14006f79d  jz      short loc_14006F7C0
0x14006f79f  mov     eax, [rcx+2Ch]
0x14006f7a2  test    esi, eax
0x14006f7a4  jz      loc_14006F5C7
0x14006f7aa  mov     edx, 67h ; 'g'
0x14006f7af  mov     [rsp+78h+var_50], ebx
0x14006f7b3  mov     dword ptr [rsp+78h+var_58], 0C37h
0x14006f7bb  jmp     loc_14006F5B0
0x14006f7c0  mov     rcx, [rsp+78h+P]
0x14006f7c5  jmp     short loc_14006F7CB
0x14006f7c7  mov     al, [rsp+78h+var_48]
0x14006f7cb  test    ebx, ebx
0x14006f7cd  jns     short loc_14006F7F5
0x14006f7cf  test    al, al
0x14006f7d1  jnz     short loc_14006F7F5
0x14006f7d3  mov     qword ptr [r13+8], 0
0x14006f7db  test    rcx, rcx
0x14006f7de  jz      short loc_14006F7EE
0x14006f7e0  xor     edx, edx; Tag
0x14006f7e2  call    cs:__imp_ExFreePoolWithTag
0x14006f7e9  nop     dword ptr [rax+rax+00h]
0x14006f7ee  and     byte ptr [r13+28h], 0EFh
0x14006f7f3  jmp     short loc_14006F829
0x14006f7f5  test    rdi, rdi
0x14006f7f8  jz      short loc_14006F829
0x14006f7fa  cmp     dword ptr [rdi+20h], 0
0x14006f7fe  jbe     short loc_14006F804
0x14006f800  or      byte ptr [rdi+28h], 30h
0x14006f804  movups  xmm0, xmmword ptr [rdi]
0x14006f807  movups  xmmword ptr [r13+0], xmm0
0x14006f80c  movups  xmm1, xmmword ptr [rdi+10h]
0x14006f810  movups  xmmword ptr [r13+10h], xmm1
0x14006f815  movups  xmm0, xmmword ptr [rdi+20h]
0x14006f819  movups  xmmword ptr [r13+20h], xmm0
0x14006f81e  movsd   xmm1, qword ptr [rdi+30h]
0x14006f823  movsd   qword ptr [r13+30h], xmm1
0x14006f829  call    cs:__imp_KeLeaveCriticalRegion
0x14006f830  nop     dword ptr [rax+rax+00h]
0x14006f835  test    ebx, ebx
0x14006f837  js      short loc_14006F86E
0x14006f839  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f840  cmp     rcx, r12
0x14006f843  jz      short loc_14006F86E
0x14006f845  test    [rcx+2Ch], esi
0x14006f848  jz      short loc_14006F86E
0x14006f84a  mov     edx, 68h ; 'h'
0x14006f84f  mov     dword ptr [rsp+78h+var_58], 0C6Dh
0x14006f857  lea     r9, aClfscreatescan; "ClfsCreateScanContext"
0x14006f85e  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14006f865  mov     rcx, [rcx+18h]
0x14006f869  call    WPP_SF_sd
0x14006f86e  mov     eax, ebx
0x14006f870  jmp     short loc_14006F8DC
0x14006f872  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f879  cmp     rcx, r12
0x14006f87c  jz      short loc_14006F8D7
0x14006f87e  test    [rcx+2Ch], esi
0x14006f881  jz      short loc_14006F8D7
0x14006f883  mov     edx, 62h ; 'b'
0x14006f888  mov     [rsp+78h+var_50], 0C000000Dh
0x14006f890  mov     dword ptr [rsp+78h+var_58], 0BB8h
0x14006f898  jmp     short loc_14006F8C0
0x14006f89a  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f8a1  cmp     rcx, r12
0x14006f8a4  jz      short loc_14006F8D7
0x14006f8a6  test    [rcx+2Ch], esi
0x14006f8a9  jz      short loc_14006F8D7
0x14006f8ab  mov     edx, 61h ; 'a'
0x14006f8b0  mov     [rsp+78h+var_50], 0C000000Dh
0x14006f8b8  mov     dword ptr [rsp+78h+var_58], 0BA9h
0x14006f8c0  lea     r9, aClfscreatescan; "ClfsCreateScanContext"
0x14006f8c7  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14006f8ce  mov     rcx, [rcx+18h]
0x14006f8d2  call    WPP_SF_slD
0x14006f8d7  mov     eax, 0C000000Dh
0x14006f8dc  add     rsp, 50h
0x14006f8e0  pop     r13
0x14006f8e2  pop     r12
0x14006f8e4  pop     rdi
0x14006f8e5  pop     rsi
0x14006f8e6  pop     rbx
0x14006f8e7  retn
0x14007bb43  push    rbx
0x14007bb45  push    rbp
0x14007bb46  sub     rsp, 38h
0x14007bb4a  mov     rbp, rdx
0x14007bb4d  cmp     dword ptr [rbp+34h], 0
0x14007bb51  jge     short loc_14007BBA3
0x14007bb53  xor     al, al
0x14007bb55  test    byte ptr [rbp+98h], 1
0x14007bb5c  movzx   eax, al
0x14007bb5f  mov     ecx, 1
0x14007bb64  cmovnz  eax, ecx
0x14007bb67  test    al, al
0x14007bb69  jnz     short loc_14007BBA3
0x14007bb6b  mov     rbx, [rbp+0A0h]
  ... truncated ...
```
