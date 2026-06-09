# MRxSmbSetFileInformation

- ea: `0x14002b980`
- end: `0x14002c055`
- name: `MRxSmbSetFileInformation`
- size: `1749`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
- tags: `file_ops, installer_update`

## callees

- `0x14000a340`
- `0x14000dfa8`
- `0x14000dfd8`
- `0x14000e01c`
- `0x14000e998`
- `0x14000ee0c`
- `0x1400169c0`
- `0x14002b980`
- `0x14002c06c`
- `0x14002cc54`
- `0x1400381d0`
- `0x14003c3f8`
- `0x14003dcc4`
- `0x140043228`
- `0x140043918`
- `0x1400439e0`
- `0x140043c5c`
- `0x14004442c`
- `0x140044568`
- `0x140044624`
- `0x14004ab38`
- `0x14004b1b0`
- `0x14004b470`
- `0x14004ef00`
- `0x1400507a0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002bb1a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bedd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bb1a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bedd`

## pseudocode

```c
__int64 __fastcall MRxSmbSetFileInformation(__int64 a1)
{
  __int64 v1; // rax
  __int64 v3; // rsi
  __int64 v4; // r13
  int v5; // eax
  __int64 v6; // r15
  unsigned int v7; // r8d
  unsigned int v8; // edi
  __int64 v9; // r14
  __int64 v10; // rax
  __int64 v11; // r12
  unsigned int v12; // esi
  bool v14; // sf
  int v15; // edx
  bool v16; // r15
  unsigned __int16 v17; // r12
  int v18; // eax
  bool v19; // zf
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rax
  char v23; // dl
  int v24; // eax
  unsigned int v25; // edi
  unsigned int v26; // edi
  unsigned int v27; // edi
  unsigned int v28; // edi
  unsigned int v29; // edi
  __int16 v30; // ax
  int v31; // [rsp+80h] [rbp-80h] BYREF
  __int16 v32; // [rsp+84h] [rbp-7Ch]
  __int64 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+90h] [rbp-70h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 v36; // [rsp+A0h] [rbp-60h]
  _BYTE v37[176]; // [rsp+B0h] [rbp-50h] BYREF
  __int16 v38; // [rsp+170h] [rbp+70h] BYREF
  __int16 v39; // [rsp+178h] [rbp+78h] BYREF
  unsigned int v40; // [rsp+180h] [rbp+80h] BYREF
  int v41; // [rsp+188h] [rbp+88h] BYREF

  v1 = *(_QWORD *)(a1 + 64);
  v40 = 0;
  v41 = 0;
  v3 = *(_QWORD *)(v1 + 32);
  v33 = v3;
  if ( v3 )
    v4 = *(_QWORD *)(v3 + 48);
  else
    v4 = 0;
  v36 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 40) + 40LL) + 104LL);
  v38 = 0;
  memset(v37, 0, 0x68u);
  v31 = 0;
  v32 = 0;
  v39 = 0;
  v5 = *(_DWORD *)(a1 + 120);
  if ( (v5 & 0x1000) != 0 )
  {
    if ( (v5 & 2) == 0 )
    {
      *(_BYTE *)(a1 + 35) = 1;
      return 3225485315LL;
    }
    *(_DWORD *)(a1 + 120) = v5 & 0xFFFFEFFF;
  }
  v6 = *(_QWORD *)(a1 + 56);
  v7 = *(_DWORD *)(a1 + 472);
  v8 = *(_DWORD *)(a1 + 448);
  v9 = *(_QWORD *)(a1 + 456);
  v10 = *(_QWORD *)(v6 + 120);
  v34 = v6;
  v11 = *(_QWORD *)(*(_QWORD *)(v10 + 32) + 32LL);
  v35 = v11;
  v40 = v7;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 66, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids, v8, v7);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      WPP_SF_Z(
        WPP_GLOBAL_Control->AttachedDevice,
        67,
        WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids,
        *(_QWORD *)(a1 + 56) + 360LL);
  }
  if ( (unsigned __int8)MRxSmbIsFileNotFoundCached(a1) )
  {
    v12 = -1073741772;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 68, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids);
LABEL_17:
    if ( v8 != 10 )
    {
LABEL_21:
      if ( v12 == -1073741772 || v12 == -1073741766 )
        MRxSmbCacheFileNotFound(a1);
      else
        MRxSmbInvalidateFileNotFoundCache(a1);
      MRxSmbInvalidateFileInfoCache(a1);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 72, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids);
      }
      MRxSmbInvalidateFullDirectoryCacheParent(a1, 0);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 73, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids, v12);
      }
      return v12;
    }
LABEL_18:
    if ( v9 != *(_QWORD *)(a1 + 456) && v9 )
      ExFreePoolWithTag((PVOID)v9, 0);
    goto LABEL_21;
  }
  if ( v8 != 4 && v8 != 13 )
  {
    if ( (*(_DWORD *)(v3 + 72) & 0x100000) != 0 )
    {
      v41 = MRxSmbDeferredCreate(a1);
      v12 = v41;
      v14 = v41 < 0;
      if ( v41 )
        goto LABEL_92;
      v3 = v33;
    }
    if ( v8 - 23 <= 2 )
      return MRxSmbSetNamedPipeInformation(a1, v8, v9, v40);
  }
  if ( (*(_DWORD *)(v3 + 72) & 0x100000) != 0 || (v15 = *(_DWORD *)(v11 + 420), (v15 & 0x20000000) == 0) )
  {
    if ( v8 == 4 )
    {
      v17 = 257;
      goto LABEL_68;
    }
    if ( v8 != 10 && v8 != 11 )
    {
      switch ( v8 )
      {
        case 0xDu:
          v17 = 258;
          break;
        case 0x13u:
          v17 = 259;
          break;
        case 0x14u:
          v17 = 260;
          break;
        default:
          goto LABEL_55;
      }
      goto LABEL_68;
    }
    v16 = 1;
    v17 = 0;
    goto LABEL_60;
  }
  v16 = 0;
  v17 = v8 + 1000;
  if ( v8 == 10 )
  {
    if ( *(_QWORD *)(v9 + 8) )
    {
      v16 = 1;
      goto LABEL_61;
    }
    v18 = *(_DWORD *)(v9 + 16);
    v19 = v18 == 0;
    if ( v18 )
    {
      do
      {
        if ( *(_WORD *)(v9 + 20) == 92 )
          break;
        v18 -= 2;
      }
      while ( v18 );
      v19 = v18 == 0;
    }
    v16 = !v19;
    if ( !v18 && (v15 & 0x40000) != 0 )
    {
      v20 = Smb64ThunkFileRenameInfo(v9, &v40, &v41);
      v12 = v41;
      if ( v41 < 0 )
        goto LABEL_18;
      v3 = v33;
      v9 = v20;
      goto LABEL_61;
    }
  }
  if ( v8 != 11 )
  {
LABEL_60:
    if ( v8 != 10 )
      goto LABEL_47;
LABEL_61:
    v21 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 40) + 184LL) + 24LL);
    if ( v21 && *(_QWORD *)(*(_QWORD *)(v21 + 24) + 120LL) != *(_QWORD *)(v34 + 120) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        WPP_SF_s(
          WPP_GLOBAL_Control->AttachedDevice,
          69,
          WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids,
          "NOT SAME DEVICE!!!!!!");
      }
      v12 = -1073741612;
      goto LABEL_18;
    }
    goto LABEL_47;
  }
  v16 = 1;
LABEL_47:
  if ( v16 )
  {
LABEL_87:
    if ( v8 - 10 > 1 )
    {
      v24 = MRxSmbCoreInformation(a1, v8, v9, (unsigned int)&v40, 2);
LABEL_91:
      v12 = v24;
      v14 = v24 < 0;
      goto LABEL_92;
    }
    if ( !MRxSmbBypassDownLevelRename )
    {
      v24 = MRxSmbRename(a1);
      goto LABEL_91;
    }
LABEL_55:
    v12 = -1073741811;
    goto LABEL_17;
  }
  v6 = v34;
LABEL_68:
  if ( (*(_DWORD *)(v35 + 420) & 0x40000) == 0 || (*(_DWORD *)(v3 + 72) & 0x100000) != 0 )
    goto LABEL_87;
  v38 = 8;
  LOWORD(v31) = *(_WORD *)(v4 + 8);
  v32 = 0;
  HIWORD(v31) = v17;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      70,
      WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids,
      *(unsigned __int16 *)(v4 + 8),
      v17);
  v12 = SmbCeTransact(
          a1,
          (int)&RxDefaultTransactionOptions,
          (int)&v38,
          2,
          0,
          0,
          (__int64)&v31,
          6,
          (__int64)&v39,
          2,
          v9,
          v40,
          0,
          0,
          (__int64)v37);
  v14 = (v12 & 0x80000000) != 0;
  if ( v12 )
  {
LABEL_92:
    if ( v14 )
      goto LABEL_17;
    goto LABEL_93;
  }
  if ( v8 == 10 || v8 == 13 )
  {
    MRxSmbCacheFileNotFound(a1);
    MRxSmbInvalidateFileInfoCache(a1);
    MRxSmbInvalidateInternalFileInfoCache(a1);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 71, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids);
    MRxSmbInvalidateFullDirectoryCacheParent(a1, 0);
    if ( v8 == 13 )
    {
      if ( v6 )
        v22 = *(_QWORD *)(v6 + 136);
      else
        v22 = 0;
      *(_DWORD *)(v22 + 4) |= 1u;
      *(_DWORD *)v4 |= 0x100u;
      return v12;
    }
    MRxSmbInvalidateFileNotFoundCacheForRename(a1);
    MRxSmbInvalidateFullDirectoryCacheParentForRename(a1, v23);
LABEL_84:
    if ( v9 != *(_QWORD *)(a1 + 456) && v9 )
      ExFreePoolWithTag((PVOID)v9, 0);
    return v12;
  }
LABEL_93:
  v25 = v8 - 4;
  if ( !v25 )
  {
    if ( *(_DWORD *)(v35 + 416) == 5 && *(_BYTE *)(v36 + 106) == 2 )
      MRxSmbUpdateBasicFileInfoCacheAll(a1, v9);
    else
      MRxSmbInvalidateBasicFileInfoCache(a1);
    return v12;
  }
  v26 = v25 - 1;
  if ( !v26 )
  {
    MRxSmbUpdateStandardFileInfoCache(a1, (struct _LIST_ENTRY *)v9, 0);
    return v12;
  }
  v27 = v26 - 2;
  if ( !v27 )
  {
    v30 = -2;
    goto LABEL_102;
  }
  v28 = v27 - 3;
  if ( !v28 )
    goto LABEL_84;
  v29 = v28 - 10;
  if ( v29 )
  {
    if ( v29 == 15 )
    {
      v30 = -5;
LABEL_102:
      *(_WORD *)(v4 + 152) &= v30;
    }
  }
  else
  {
    MRxSmbUpdateFileInfoCacheFileSize(a1, (struct _LIST_ENTRY **)v9);
  }
  return v12;
}

```

## disassembly

```asm
0x14002b980  push    rbp
0x14002b982  push    rbx
0x14002b983  push    rsi
0x14002b984  push    rdi
0x14002b985  push    r12
0x14002b987  push    r13
0x14002b989  push    r14
0x14002b98b  push    r15
0x14002b98d  lea     rbp, [rsp-28h]
0x14002b992  sub     rsp, 128h
0x14002b999  mov     rax, [rcx+40h]
0x14002b99d  mov     rbx, rcx
0x14002b9a0  mov     [rbp+60h+arg_10], 0
0x14002b9aa  mov     [rbp+60h+arg_18], 0
0x14002b9b4  mov     rsi, [rax+20h]
0x14002b9b8  mov     [rbp+60h+var_D8], rsi
0x14002b9bc  test    rsi, rsi
0x14002b9bf  jnz     short loc_14002B9C6
0x14002b9c1  xor     r13d, r13d
0x14002b9c4  jmp     short loc_14002B9CA
0x14002b9c6  mov     r13, [rsi+30h]
0x14002b9ca  mov     rax, [rsi+28h]
0x14002b9ce  xor     edx, edx; Val
0x14002b9d0  mov     rcx, [rax+28h]
0x14002b9d4  mov     rax, [rcx+68h]
0x14002b9d8  lea     rcx, [rbp+60h+var_B0]; void *
0x14002b9dc  mov     [rbp+60h+var_C0], rax
0x14002b9e0  xor     eax, eax
0x14002b9e2  mov     [rbp+60h+arg_0], ax
0x14002b9e6  lea     r8d, [rax+68h]; Size
0x14002b9ea  call    memset
0x14002b9ef  xor     eax, eax
0x14002b9f1  mov     [rbp+60h+var_E0], eax
0x14002b9f4  mov     [rbp+60h+var_DC], ax
0x14002b9f8  mov     [rbp+60h+arg_8], ax
0x14002b9fc  mov     eax, [rbx+78h]
0x14002b9ff  bt      eax, 0Ch
0x14002ba03  jnb     short loc_14002BA14
0x14002ba05  test    al, 2
0x14002ba07  jz      loc_14002BB4B
0x14002ba0d  btr     eax, 0Ch
0x14002ba11  mov     [rbx+78h], eax
0x14002ba14  mov     r15, [rbx+38h]
0x14002ba18  mov     r8d, [rbx+1D8h]
0x14002ba1f  mov     edi, [rbx+1C0h]
0x14002ba25  mov     r14, [rbx+1C8h]
0x14002ba2c  mov     rax, [r15+78h]
0x14002ba30  mov     [rbp+60h+var_D0], r15
0x14002ba34  mov     rcx, [rax+20h]
0x14002ba38  mov     r12, [rcx+20h]
0x14002ba3c  mov     [rbp+60h+var_C8], r12
0x14002ba40  mov     [rbp+60h+arg_10], r8d
0x14002ba47  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002ba4e  lea     rax, WPP_GLOBAL_Control
0x14002ba55  cmp     rcx, rax
0x14002ba58  jz      short loc_14002BABC
0x14002ba5a  test    dword ptr [rcx+2Ch], 400h
0x14002ba61  jz      short loc_14002BA80
0x14002ba63  mov     rcx, [rcx+18h]
0x14002ba67  mov     edx, 42h ; 'B'
0x14002ba6c  mov     dword ptr [rsp+160h+var_140], r8d
0x14002ba71  mov     r9d, edi
0x14002ba74  lea     r8, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids
0x14002ba7b  call    WPP_SF_Dd
0x14002ba80  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002ba87  lea     rax, WPP_GLOBAL_Control
0x14002ba8e  cmp     rcx, rax
0x14002ba91  jz      short loc_14002BABC
0x14002ba93  test    dword ptr [rcx+2Ch], 200h
0x14002ba9a  jz      short loc_14002BABC
0x14002ba9c  mov     r9, [rbx+38h]
0x14002baa0  lea     r8, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids
0x14002baa7  mov     rcx, [rcx+18h]
0x14002baab  add     r9, 168h
0x14002bab2  mov     edx, 43h ; 'C'
0x14002bab7  call    WPP_SF_Z
0x14002babc  mov     rcx, rbx
0x14002babf  call    MRxSmbIsFileNotFoundCached
0x14002bac4  test    al, al
0x14002bac6  jz      loc_14002BB59
0x14002bacc  mov     esi, 0C0000034h
0x14002bad1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002bad8  lea     rax, WPP_GLOBAL_Control
0x14002badf  cmp     rcx, rax
0x14002bae2  jz      short loc_14002BB02
0x14002bae4  test    dword ptr [rcx+2Ch], 400h
0x14002baeb  jz      short loc_14002BB02
0x14002baed  mov     rcx, [rcx+18h]
0x14002baf1  lea     r8, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids
0x14002baf8  mov     edx, 44h ; 'D'
0x14002bafd  call    WPP_SF_
0x14002bb02  cmp     edi, 0Ah
0x14002bb05  jnz     short loc_14002BB26
0x14002bb07  cmp     r14, [rbx+1C8h]
0x14002bb0e  jz      short loc_14002BB26
0x14002bb10  test    r14, r14
0x14002bb13  jz      short loc_14002BB26
0x14002bb15  xor     edx, edx; Tag
0x14002bb17  mov     rcx, r14; P
0x14002bb1a  call    cs:__imp_ExFreePoolWithTag
0x14002bb21  nop     dword ptr [rax+rax+00h]
0x14002bb26  cmp     esi, 0C0000034h
0x14002bb2c  jz      loc_14002BFC6
0x14002bb32  cmp     esi, 0C000003Ah
0x14002bb38  jz      loc_14002BFC6
0x14002bb3e  mov     rcx, rbx
0x14002bb41  call    MRxSmbInvalidateFileNotFoundCache
0x14002bb46  jmp     loc_14002BFCE
0x14002bb4b  mov     byte ptr [rbx+23h], 1
0x14002bb4f  mov     eax, 0C0410003h
0x14002bb54  jmp     loc_14002C040
0x14002bb59  cmp     edi, 4
0x14002bb5c  jz      short loc_14002BBA9
0x14002bb5e  cmp     edi, 0Dh
0x14002bb61  jz      short loc_14002BBA9
0x14002bb63  test    dword ptr [rsi+48h], 100000h
0x14002bb6a  jz      short loc_14002BB88
0x14002bb6c  mov     rcx, rbx
0x14002bb6f  call    MRxSmbDeferredCreate
0x14002bb74  mov     [rbp+60h+arg_18], eax
0x14002bb7a  mov     esi, eax
0x14002bb7c  test    eax, eax
0x14002bb7e  jnz     loc_14002BF2D
0x14002bb84  mov     rsi, [rbp+60h+var_D8]
0x14002bb88  lea     eax, [rdi-17h]
0x14002bb8b  cmp     eax, 2
0x14002bb8e  ja      short loc_14002BBA9
0x14002bb90  mov     r9d, [rbp+60h+arg_10]
0x14002bb97  mov     r8, r14
0x14002bb9a  mov     edx, edi
0x14002bb9c  mov     rcx, rbx
0x14002bb9f  call    MRxSmbSetNamedPipeInformation
0x14002bba4  jmp     loc_14002C040
0x14002bba9  test    dword ptr [rsi+48h], 100000h
0x14002bbb0  jnz     loc_14002BC54
0x14002bbb6  mov     edx, [r12+1A4h]
0x14002bbbe  bt      edx, 1Dh
0x14002bbc2  jnb     loc_14002BC54
0x14002bbc8  mov     r12d, 3E8h
0x14002bbce  xor     r15b, r15b
0x14002bbd1  add     r12d, edi
0x14002bbd4  cmp     edi, 0Ah
0x14002bbd7  jnz     short loc_14002BC3A
0x14002bbd9  cmp     qword ptr [r14+8], 0
0x14002bbde  jnz     short loc_14002BC35
0x14002bbe0  mov     eax, [r14+10h]
0x14002bbe4  test    eax, eax
0x14002bbe6  jz      short loc_14002BBFA
0x14002bbe8  movzx   ecx, word ptr [r14+14h]
0x14002bbed  cmp     cx, 5Ch ; '\'
0x14002bbf1  jz      short loc_14002BBF8
0x14002bbf3  add     eax, 0FFFFFFFEh
0x14002bbf6  jnz     short loc_14002BBED
0x14002bbf8  test    eax, eax
0x14002bbfa  setnz   r15b
0x14002bbfe  test    eax, eax
0x14002bc00  jnz     short loc_14002BC3A
0x14002bc02  bt      edx, 12h
0x14002bc06  jnb     short loc_14002BC3A
0x14002bc08  lea     r8, [rbp+60h+arg_18]
0x14002bc0f  mov     rcx, r14
0x14002bc12  lea     rdx, [rbp+60h+arg_10]
0x14002bc19  call    Smb64ThunkFileRenameInfo
0x14002bc1e  mov     esi, [rbp+60h+arg_18]
0x14002bc24  test    esi, esi
0x14002bc26  js      loc_14002BB07
0x14002bc2c  mov     rsi, [rbp+60h+var_D8]
0x14002bc30  mov     r14, rax
0x14002bc33  jmp     short loc_14002BCB1
0x14002bc35  mov     r15b, 1
0x14002bc38  jmp     short loc_14002BCB1
0x14002bc3a  cmp     edi, 0Bh
0x14002bc3d  jnz     short loc_14002BCAC
0x14002bc3f  mov     r15b, 1
0x14002bc42  test    r15b, r15b
0x14002bc45  jnz     loc_14002BEEE
0x14002bc4b  mov     r15, [rbp+60h+var_D0]
0x14002bc4f  jmp     loc_14002BD27
0x14002bc54  mov     ecx, edi
0x14002bc56  sub     ecx, 4
0x14002bc59  jz      loc_14002BD21
0x14002bc5f  sub     ecx, 6
0x14002bc62  jz      short loc_14002BCA3
0x14002bc64  sub     ecx, 1
0x14002bc67  jz      short loc_14002BCA3
0x14002bc69  sub     ecx, 2
0x14002bc6c  jz      short loc_14002BC98
0x14002bc6e  sub     ecx, 6
0x14002bc71  jz      short loc_14002BC8D
0x14002bc73  cmp     ecx, 1
0x14002bc76  jz      short loc_14002BC82
0x14002bc78  mov     esi, 0C000000Dh
0x14002bc7d  jmp     loc_14002BB02
0x14002bc82  mov     r12d, 104h
0x14002bc88  jmp     loc_14002BD27
0x14002bc8d  mov     r12d, 103h
0x14002bc93  jmp     loc_14002BD27
0x14002bc98  mov     r12d, 102h
0x14002bc9e  jmp     loc_14002BD27
0x14002bca3  xor     eax, eax
0x14002bca5  mov     r15b, 1
0x14002bca8  movzx   r12d, ax
0x14002bcac  cmp     edi, 0Ah
0x14002bcaf  jnz     short loc_14002BC42
0x14002bcb1  mov     rax, [rbx+28h]
0x14002bcb5  mov     rcx, [rax+0B8h]
0x14002bcbc  mov     rcx, [rcx+18h]
0x14002bcc0  test    rcx, rcx
0x14002bcc3  jz      loc_14002BC42
0x14002bcc9  mov     rax, [rbp+60h+var_D0]
0x14002bccd  mov     rcx, [rcx+18h]
0x14002bcd1  mov     rax, [rax+78h]
0x14002bcd5  cmp     [rcx+78h], rax
0x14002bcd9  jz      loc_14002BC42
0x14002bcdf  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002bce6  lea     rax, WPP_GLOBAL_Control
0x14002bced  cmp     rcx, rax
0x14002bcf0  jz      short loc_14002BD17
0x14002bcf2  test    dword ptr [rcx+2Ch], 200h
0x14002bcf9  jz      short loc_14002BD17
0x14002bcfb  mov     rcx, [rcx+18h]
0x14002bcff  lea     r9, aNotSameDevice; "NOT SAME DEVICE!!!!!!"
0x14002bd06  mov     edx, 45h ; 'E'
0x14002bd0b  lea     r8, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids
0x14002bd12  call    WPP_SF_s
0x14002bd17  mov     esi, 0C00000D4h
0x14002bd1c  jmp     loc_14002BB07
0x14002bd21  mov     r12d, 101h
0x14002bd27  mov     rax, [rbp+60h+var_C8]
0x14002bd2b  test    dword ptr [rax+1A4h], 40000h
0x14002bd35  setnz   cl
0x14002bd38  test    dword ptr [rsi+48h], 100000h
0x14002bd3f  setz    al
0x14002bd42  test    al, cl
0x14002bd44  jz      loc_14002BEEE
0x14002bd4a  mov     eax, 8
0x14002bd4f  mov     [rbp+60h+arg_0], ax
0x14002bd53  movzx   eax, word ptr [r13+8]
0x14002bd58  mov     word ptr [rbp+60h+var_E0], ax
0x14002bd5c  xor     eax, eax
0x14002bd5e  mov     [rbp+60h+var_DC], ax
0x14002bd62  mov     word ptr [rbp+60h+var_E0+2], r12w
0x14002bd67  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002bd6e  lea     rax, WPP_GLOBAL_Control
0x14002bd75  cmp     rcx, rax
0x14002bd78  jz      short loc_14002BDA5
0x14002bd7a  test    dword ptr [rcx+2Ch], 400h
0x14002bd81  jz      short loc_14002BDA5
0x14002bd83  movzx   r9d, word ptr [r13+8]
0x14002bd88  lea     r8, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids
0x14002bd8f  mov     rcx, [rcx+18h]
0x14002bd93  mov     edx, 46h ; 'F'
0x14002bd98  movzx   eax, r12w
0x14002bd9c  mov     dword ptr [rsp+160h+var_140], eax
0x14002bda0  call    WPP_SF_Dd
0x14002bda5  lea     rax, [rbp+60h+var_B0]
0x14002bda9  mov     r9d, 2
0x14002bdaf  mov     [rsp+160h+var_F0], rax
0x14002bdb4  lea     r8, [rbp+60h+arg_0]
0x14002bdb8  mov     eax, [rbp+60h+arg_10]
0x14002bdbe  lea     rdx, RxDefaultTransactionOptions
0x14002bdc5  mov     [rsp+160h+var_F8], 0
0x14002bdcd  mov     rcx, rbx
0x14002bdd0  mov     [rsp+160h+var_100], 0
0x14002bdd9  mov     [rsp+160h+var_108], eax
0x14002bddd  lea     rax, [rbp+60h+arg_8]
0x14002bde1  mov     [rsp+160h+var_110], r14
0x14002bde6  mov     [rsp+160h+var_118], 2
0x14002bdee  mov     [rsp+160h+var_120], rax
0x14002bdf3  lea     rax, [rbp+60h+var_E0]
0x14002bdf7  mov     [rsp+160h+var_128], 6
0x14002bdff  mov     [rsp+160h+var_130], rax
0x14002be04  mov     [rsp+160h+var_138], 0
0x14002be0c  mov     [rsp+160h+var_140], 0
0x14002be15  call    SmbCeTransact
0x14002be1a  mov     esi, eax
0x14002be1c  test    eax, eax
0x14002be1e  jnz     loc_14002BF2D
0x14002be24  cmp     edi, 0Ah
0x14002be27  jz      short loc_14002BE32
0x14002be29  cmp     edi, 0Dh
0x14002be2c  jnz     loc_14002BF33
0x14002be32  mov     rcx, rbx
0x14002be35  call    MRxSmbCacheFileNotFound
0x14002be3a  mov     rcx, rbx
0x14002be3d  call    MRxSmbInvalidateFileInfoCache
0x14002be42  mov     rcx, rbx
0x14002be45  call    MRxSmbInvalidateInternalFileInfoCache
0x14002be4a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002be51  lea     rax, WPP_GLOBAL_Control
0x14002be58  cmp     rcx, rax
0x14002be5b  jz      short loc_14002BE7B
0x14002be5d  test    dword ptr [rcx+2Ch], 200h
0x14002be64  jz      short loc_14002BE7B
0x14002be66  mov     rcx, [rcx+18h]
0x14002be6a  lea     r8, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids
0x14002be71  mov     edx, 47h ; 'G'
0x14002be76  call    WPP_SF_
0x14002be7b  xor     edx, edx
0x14002be7d  mov     rcx, rbx
  ... truncated ...
```
