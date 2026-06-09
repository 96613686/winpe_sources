# SmbTransactExchangeStart

- ea: `0x140046bb0`
- end: `0x1400478db`
- name: `SmbTransactExchangeStart`
- size: `3371`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation`

## callees

- `0x14000dfa8`
- `0x14000dfd8`
- `0x14000e01c`
- `0x14000e52c`
- `0x1400146d4`
- `0x140014738`
- `0x14003f0c8`
- `0x140046bb0`
- `0x1400478f0`
- `0x14004e5b0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400471dc`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400471dc`
- `ntoskrnl!IoGetRequestorProcessId` at `0x14004704c`
- `ntoskrnl!IoGetRequestorProcessId` at `0x14004704c`
- `ntoskrnl!IoBuildPartialMdl` at `0x140047637`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400476ab`
- `ntoskrnl!IoBuildPartialMdl` at `0x140047726`
- `ntoskrnl!IoBuildPartialMdl` at `0x140047637`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400476ab`
- `ntoskrnl!IoBuildPartialMdl` at `0x140047726`
- `ntoskrnl!IoFreeMdl` at `0x140046ebc`
- `ntoskrnl!IoFreeMdl` at `0x140046fb7`
- `ntoskrnl!IoFreeMdl` at `0x140047886`
- `ntoskrnl!IoFreeMdl` at `0x14004789a`
- `ntoskrnl!IoFreeMdl` at `0x1400478ae`
- `ntoskrnl!IoFreeMdl` at `0x140046ebc`
- `ntoskrnl!IoFreeMdl` at `0x140046fb7`
- `ntoskrnl!IoFreeMdl` at `0x140047886`
- `ntoskrnl!IoFreeMdl` at `0x14004789a`
- `ntoskrnl!IoFreeMdl` at `0x1400478ae`
- `ntoskrnl!MmProbeAndLockPages` at `0x140046e43`
- `ntoskrnl!MmProbeAndLockPages` at `0x140046e43`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046fcd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046fcd`
- `rdbss!RxUnlockHeaderPages` at `0x1400478c2`
- `rdbss!RxUnlockHeaderPages` at `0x1400478c2`
- `rdbss!RxAllocateMdl2` at `0x140046dd5`
- `rdbss!RxAllocateMdl2` at `0x140047150`
- `rdbss!RxAllocateMdl2` at `0x140047188`
- `rdbss!RxAllocateMdl2` at `0x140047514`
- `rdbss!RxAllocateMdl2` at `0x140046dd5`
- `rdbss!RxAllocateMdl2` at `0x140047150`
- `rdbss!RxAllocateMdl2` at `0x140047188`
- `rdbss!RxAllocateMdl2` at `0x140047514`

## pseudocode

```c
__int64 __fastcall SmbTransactExchangeStart(unsigned __int8 *pContext)
{
  __int64 v2; // rdi
  unsigned __int8 v3; // r15
  unsigned int v4; // esi
  __int64 v5; // r8
  int v6; // ecx
  bool v7; // cl
  unsigned int v8; // r13d
  _WORD *v9; // rsi
  unsigned int v10; // eax
  unsigned int v11; // r10d
  unsigned int v12; // r9d
  ULONG v13; // r15d
  ULONG v14; // r11d
  __int64 v15; // r8
  ULONG v16; // eax
  ULONG v17; // r12d
  ULONG v18; // r9d
  int v19; // ecx
  __int16 v20; // cx
  __int16 v21; // dx
  __int64 v22; // rdx
  __int64 Mdl2; // rax
  __int64 v24; // rdi
  struct _MDL *v25; // r13
  struct _MDL *v26; // r12
  _BYTE *v27; // rax
  int v28; // eax
  int v29; // eax
  IRP *v31; // rcx
  ULONG RequestorProcessId; // eax
  ULONG v33; // eax
  PVOID v34; // rax
  int v35; // ecx
  int v36; // esi
  int v37; // ecx
  unsigned int v38; // edx
  PDEVICE_OBJECT v39; // rcx
  __int64 v40; // rdx
  ULONG v41; // [rsp+40h] [rbp-98h]
  _BYTE *v42; // [rsp+40h] [rbp-98h]
  ULONG v43; // [rsp+4Ch] [rbp-8Ch]
  unsigned int v44; // [rsp+58h] [rbp-80h]
  struct _MDL *TargetMdl; // [rsp+60h] [rbp-78h]
  _DWORD *v46; // [rsp+78h] [rbp-60h]
  PVOID P; // [rsp+88h] [rbp-50h]
  struct _MDL *v48; // [rsp+E0h] [rbp+8h]
  ULONG Length; // [rsp+E8h] [rbp+10h] BYREF
  unsigned int v50; // [rsp+F0h] [rbp+18h] BYREF
  unsigned __int8 *v51; // [rsp+F8h] [rbp+20h] BYREF

  P = (PVOID)*((_QWORD *)pContext + 60);
  v2 = *((_QWORD *)pContext + 61);
  v3 = pContext[509];
  v50 = 0;
  v51 = 0;
  v4 = SmbCeBuildSmbHeader((_DWORD)pContext, v2, 32, (unsigned int)&v50, (__int64)&Length, (__int64)&v51);
  if ( !v4 )
  {
    *v51 = v3;
    if ( (*(_DWORD *)(*((_QWORD *)pContext + 10) + 420LL) & 0x40000) != 0 && (*((_WORD *)pContext + 255) & 0x800) == 0 )
    {
      v31 = *(IRP **)(*((_QWORD *)pContext + 3) + 40LL);
      if ( v31 )
        RequestorProcessId = IoGetRequestorProcessId(v31);
      else
        RequestorProcessId = 65279;
      *((_DWORD *)pContext + 18) |= 0x4000u;
      *(_WORD *)(v2 + 26) = RequestorProcessId;
      *(_WORD *)(v2 + 12) = HIWORD(RequestorProcessId);
    }
    if ( _bittest16((const signed __int16 *)pContext + 255, 0xBu) )
      *(_WORD *)(v2 + 10) &= ~0x4000u;
    if ( _bittest16((const signed __int16 *)pContext + 255, 9u) )
      *(_WORD *)(v2 + 10) |= 0x1000u;
  }
  if ( v4 )
  {
LABEL_160:
    *((_DWORD *)pContext + 12) = v4;
    return v4;
  }
  v6 = pContext[509];
  if ( v6 == 50 || (v35 = v6 - 37) == 0 )
  {
    v7 = 0;
    v8 = 2 * *(unsigned __int8 *)(v2 + 59) + 61;
    v9 = (_WORD *)(v2 + v8);
    v10 = v8 + *((_DWORD *)pContext + 129);
  }
  else
  {
    if ( v35 != 123 )
      return 3221225485LL;
    v36 = *(unsigned __int8 *)(v2 + 68);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_dddd(
        WPP_GLOBAL_Control->AttachedDevice,
        13,
        v5,
        *(unsigned int *)(v2 + 36),
        *(_DWORD *)(v2 + 40),
        *(_DWORD *)(v2 + 44),
        *(_DWORD *)(v2 + 48));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_Dd(
        WPP_GLOBAL_Control->AttachedDevice,
        14,
        WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids,
        *(unsigned __int8 *)(v2 + 68),
        *(unsigned __int8 *)(v2 + 33));
    v8 = 2 * v36 + 71;
    v9 = (_WORD *)(v2 + v8);
    v7 = *((_WORD *)pContext + 256) == 8;
    v10 = v8;
  }
  v11 = (v10 + 5) & 0xFFFFFFFC;
  LODWORD(v51) = v11;
  v12 = *((_DWORD *)pContext + 130);
  v44 = v12;
  v46 = pContext + 416;
  v13 = v12 - v11;
  if ( v12 - v11 >= *((_DWORD *)pContext + 104) )
    v13 = *((_DWORD *)pContext + 104);
  v14 = v13 + v11;
  v41 = v13 + v11;
  if ( v7 )
    v15 = (v14 + 7) & 0xFFFFFFF8;
  else
    v15 = (v14 + 3) & 0xFFFFFFFC;
  v50 = v15;
  if ( (unsigned int)v15 < v12 )
  {
    v17 = v12 - v15;
    if ( v12 - (unsigned int)v15 >= *((_DWORD *)pContext + 94) )
      v17 = *((_DWORD *)pContext + 94);
    v43 = v17;
    v16 = v15 - v13 - v11;
    if ( v17 )
      goto LABEL_12;
  }
  else
  {
    v16 = 0;
    v17 = 0;
    v43 = 0;
  }
  v15 = 0;
  v50 = 0;
LABEL_12:
  v18 = 0;
  if ( v17 )
    v18 = v16;
  Length = v18;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
  {
    WPP_SF_ddd(WPP_GLOBAL_Control->AttachedDevice, &WPP_GLOBAL_Control, v15, v13, v18, v17);
    v18 = Length;
    v15 = v50;
    v11 = (unsigned int)v51;
    v14 = v41;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
  {
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, v11, v15);
    v18 = Length;
    v15 = v50;
    v11 = (unsigned int)v51;
    v14 = v41;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, v2, v9);
    v18 = Length;
    v15 = v50;
    v11 = (unsigned int)v51;
    v14 = v41;
  }
  v19 = pContext[509];
  if ( v19 == 50 || (v37 = v19 - 37) == 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids);
      v18 = Length;
      v11 = (unsigned int)v51;
      v14 = v41;
    }
    v20 = v13;
    *(_WORD *)(v2 + 51) = v13;
    v21 = v11;
    *(_WORD *)(v2 + 53) = v11;
    *(_WORD *)(v2 + 55) = v17;
    *(_WORD *)(v2 + 57) = v50;
LABEL_20:
    TargetMdl = 0;
    *v9 = v20 + v17 + v21 + v18 - v8 - 2;
    *((_QWORD *)pContext + 60) = 0;
    *((_QWORD *)pContext + 61) = 0;
    v42 = pContext + 508;
    if ( pContext[508] )
      v22 = v14 + v18;
    else
      v22 = v11;
    Mdl2 = RxAllocateMdl2(v2, v22, 0, 0, 0);
    v24 = Mdl2;
    if ( Mdl2 && *(_DWORD *)(Mdl2 + 44) >= 0x20u )
      *(_WORD *)(Mdl2 + 10) |= 0x1000u;
    if ( Mdl2 )
    {
      v4 = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids);
      }
      v4 = -1073741670;
    }
    if ( v17 && !v4 )
    {
      v38 = v44;
      if ( *((_DWORD *)pContext + 94) < v44 )
        v38 = *((_DWORD *)pContext + 94);
      TargetMdl = (struct _MDL *)RxAllocateMdl2(0, v38 + 4095, 0, 0, 0);
      if ( TargetMdl )
      {
        v4 = 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids);
        }
        v4 = -1073741670;
      }
    }
    if ( !v13 || *v42 || v4 )
    {
      v25 = 0;
      v26 = 0;
      if ( v4 )
        goto LABEL_41;
    }
    else
    {
      v25 = (struct _MDL *)RxAllocateMdl2(*((_QWORD *)pContext + 51), v13, 0, 0, 0);
      v33 = Length;
      if ( Length )
      {
        v26 = (struct _MDL *)RxAllocateMdl2(0, 4099, 0, 0, 0);
        v33 = Length;
      }
      else
      {
        v26 = 0;
      }
      if ( !v25 || !v26 && v33 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
        {
          WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, v25, v26);
        }
        v4 = -1073741670;
        goto LABEL_41;
      }
    }
    MmProbeAndLockPages((PMDL)v24, 0, IoModifyAccess);
    if ( (*(_BYTE *)(v24 + 10) & 5) != 0 )
      v34 = *(PVOID *)(v24 + 24);
    else
      v34 = MmMapLockedPagesSpecifyCache((PMDL)v24, 0, MmCached, 0, 0, 0x40000000u);
    if ( !v34 )
    {
      v4 = -1073741670;
      goto LABEL_41;
    }
    v48 = (struct _MDL *)v24;
    if ( v13 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_Dd(
          WPP_GLOBAL_Control->AttachedDevice,
          24,
          WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids,
          v13,
          (_DWORD)v51);
      }
      *((_DWORD *)pContext + 105) = v13;
      v27 = pContext + 508;
      if ( *v42 )
      {
LABEL_31:
        if ( v43 )
        {
          if ( !*v27 && Length )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, Length);
            }
            IoBuildPartialMdl(
              (PMDL)MrxSmbCeGlobalPadding,
              v26,
              (PVOID)(*((_QWORD *)MrxSmbCeGlobalPadding + 4) + *((unsigned int *)MrxSmbCeGlobalPadding + 11)),
              Length);
            v48->Next = v26;
            v48 = v26;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
          {
            WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, v43, v50);
          }
          *((_DWORD *)pContext + 95) = v43;
          IoBuildPartialMdl(
            *((PMDL *)pContext + 46),
            TargetMdl,
            (PVOID)(*(_QWORD *)(*((_QWORD *)pContext + 46) + 32LL) + *(unsigned int *)(*((_QWORD *)pContext + 46) + 44LL)),
            v43);
          v48->Next = TargetMdl;
        }
        v28 = *((_DWORD *)pContext + 18);
        if ( (v28 & 0x40) != 0 )
        {
          *((_DWORD *)pContext + 18) = v28 | 1;
          *((_WORD *)pContext + 32) = -1;
        }
        if ( (pContext[510] & 2) != 0 )
        {
          if ( *((_DWORD *)pContext + 94) != v43 )
            goto LABEL_36;
          if ( *v46 == v13 )
          {
            *((_DWORD *)pContext + 12) = 0;
            *(_DWORD *)(*((_QWORD *)pContext + 66) + 68LL) = 0;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids);
            }
            v4 = SmbCeSend(pContext);
            if ( v4 )
            {
              v39 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
              {
                v40 = 28;
LABEL_159:
                WPP_SF_d(v39->AttachedDevice, v40, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, v4);
              }
            }
LABEL_41:
            if ( v25 )
              IoFreeMdl(v25);
            if ( TargetMdl )
              IoFreeMdl(TargetMdl);
            if ( v26 )
              IoFreeMdl(v26);
            if ( v24 )
            {
              if ( (*(_BYTE *)(v24 + 10) & 2) != 0 )
                RxUnlockHeaderPages(v24);
              IoFreeMdl((PMDL)v24);
            }
            ExFreePoolWithTag(P, 0);
            if ( v4 == 259 )
              return v4;
            goto LABEL_160;
          }
        }
        if ( *((_DWORD *)pContext + 94) == v43 && *v46 == v13 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids);
          }
          v29 = 5;
LABEL_37:
          *((_DWORD *)pContext + 90) = v29;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids);
          }
          v4 = SmbCeTranceive(pContext);
          if ( v4 )
          {
            v39 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
            {
              v40 = 31;
              goto LABEL_159;
            }
          }
          goto LABEL_41;
        }
LABEL_36:
        v29 = 3;
        goto LABEL_37;
      }
      IoBuildPartialMdl(
        *((PMDL *)pContext + 50),
        v25,
        (PVOID)(*(_QWORD *)(*((_QWORD *)pContext + 50) + 32LL) + *(unsigned int *)(*((_QWORD *)pContext + 50) + 44LL)),
        v13);
      *(_QWORD *)v24 = v25;
      v48 = v25;
    }
    v27 = pContext + 508;
    goto LABEL_31;
  }
  if ( v37 == 123 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids);
      v18 = Length;
      v15 = v50;
      v11 = (unsigned int)v51;
      v14 = v41;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    {
      WPP_SF_dddd(
        WPP_GLOBAL_Control->AttachedDevice,
        20,
        v15,
        *(unsigned int *)(v2 + 36),
        *(_DWORD *)(v2 + 40),
        *(_DWORD *)(v2 + 44),
        *(_DWORD *)(v2 + 48));
      v18 = Length;
      LODWORD(v15) = v50;
      v11 = (unsigned int)v51;
      v14 = v41;
    }
    *(_DWORD *)(v2 + 52) = v13;
    *(_DWORD *)(v2 + 56) = v11;
    *(_DWORD *)(v2 + 60) = v17;
    *(_DWORD *)(v2 + 64) = v15;
    v20 = v13;
    v21 = v11;
    goto LABEL_20;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x140046bb0  mov     r11, rsp
0x140046bb3  mov     [r11+8], rcx
0x140046bb7  push    rbx
0x140046bb8  push    rsi
0x140046bb9  push    rdi
0x140046bba  push    r12
0x140046bbc  push    r13
0x140046bbe  push    r14
0x140046bc0  push    r15
0x140046bc2  sub     rsp, 0A0h
0x140046bc9  mov     rbx, rcx
0x140046bcc  mov     rax, [rcx+1E0h]
0x140046bd3  mov     [rsp+0D8h+P], rax
0x140046bdb  mov     [rsp+0D8h+var_40], rax
0x140046be3  mov     rdi, [rcx+1E8h]
0x140046bea  movzx   r15d, byte ptr [rcx+1FDh]
0x140046bf2  xor     r14d, r14d
0x140046bf5  mov     [r11+18h], r14d
0x140046bf9  mov     [r11+20h], r14
0x140046bfd  lea     rax, [r11+20h]
0x140046c01  mov     qword ptr [rsp+0D8h+Priority], rax
0x140046c06  lea     rax, [r11+10h]
0x140046c0a  mov     qword ptr [rsp+0D8h+BugCheckOnFailure], rax
0x140046c0f  lea     r9, [r11+18h]
0x140046c13  mov     r8d, 20h ; ' '
0x140046c19  mov     rdx, rdi
0x140046c1c  call    SmbCeBuildSmbHeader
0x140046c21  mov     esi, eax
0x140046c23  test    eax, eax
0x140046c25  jz      loc_140047008
0x140046c2b  test    esi, esi
0x140046c2d  jnz     loc_1400478D3
0x140046c33  movzx   ecx, byte ptr [rbx+1FDh]
0x140046c3a  cmp     ecx, 32h ; '2'
0x140046c3d  jnz     loc_1400472CB
0x140046c43  xor     cl, cl
0x140046c45  movzx   eax, byte ptr [rdi+3Bh]
0x140046c49  lea     r13d, ds:3Dh[rax*2]
0x140046c51  mov     esi, r13d
0x140046c54  add     rsi, rdi
0x140046c57  mov     eax, [rbx+204h]
0x140046c5d  add     eax, r13d
0x140046c60  lea     rdx, WPP_GLOBAL_Control
0x140046c67  lea     r10d, [rax+5]
0x140046c6b  and     r10d, 0FFFFFFFCh
0x140046c6f  mov     dword ptr [rsp+0D8h+arg_18], r10d
0x140046c77  mov     [rsp+0D8h+var_70], r10d
0x140046c7c  mov     r9d, [rbx+208h]
0x140046c83  mov     dword ptr [rsp+0D8h+var_80], r9d
0x140046c88  lea     rax, [rbx+1A0h]
0x140046c8f  mov     [rsp+0D8h+var_60], rax
0x140046c94  mov     eax, [rax]
0x140046c96  mov     r15d, r9d
0x140046c99  sub     r15d, r10d
0x140046c9c  cmp     r15d, eax
0x140046c9f  cmovnb  r15d, eax
0x140046ca3  mov     [rsp+0D8h+var_68], r15d
0x140046ca8  lea     r11d, [r15+r10]
0x140046cac  mov     dword ptr [rsp+0D8h+var_98], r11d
0x140046cb1  test    cl, cl
0x140046cb3  jnz     loc_140046FFB
0x140046cb9  lea     r8d, [r11+3]
0x140046cbd  and     r8d, 0FFFFFFFCh
0x140046cc1  mov     [rsp+0D8h+var_90], r8d
0x140046cc6  mov     [rsp+0D8h+arg_10], r8d
0x140046cce  cmp     r8d, r9d
0x140046cd1  jb      loc_1400471FB
0x140046cd7  mov     eax, r14d
0x140046cda  mov     r12d, r14d
0x140046cdd  mov     [rsp+0D8h+var_8C], r14d
0x140046ce2  mov     [rsp+0D8h+var_88], r14d
0x140046ce7  mov     r8d, r14d
0x140046cea  mov     [rsp+0D8h+arg_10], r14d
0x140046cf2  mov     [rsp+0D8h+var_90], r14d
0x140046cf7  mov     r9d, r14d; __annotation("TMF:",
0x140046cfa  test    r12d, r12d
0x140046cfd  cmovnz  r9d, eax
0x140046d01  mov     [rsp+0D8h+Length], r9d
0x140046d09  mov     [rsp+0D8h+var_6C], r9d
0x140046d0e  mov     rcx, cs:WPP_GLOBAL_Control
0x140046d15  cmp     rcx, rdx
0x140046d18  jnz     loc_14004738A
0x140046d1e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140046d25  cmp     rcx, rdx
0x140046d28  jnz     loc_140047247
0x140046d2e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140046d35  cmp     rcx, rdx
0x140046d38  jnz     loc_140047096
0x140046d3e  movzx   ecx, byte ptr [rbx+1FDh]
0x140046d45  cmp     ecx, 32h ; '2'
0x140046d48  jnz     loc_1400473D6
0x140046d4e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140046d55  cmp     rcx, rdx
0x140046d58  jnz     loc_1400470E9
0x140046d5e  movzx   ecx, r15w
0x140046d62  mov     [rdi+33h], cx
0x140046d66  movzx   edx, r10w
0x140046d6a  mov     [rdi+35h], dx
0x140046d6e  mov     [rdi+37h], r12w
0x140046d73  mov     eax, [rsp+0D8h+arg_10]
0x140046d7a  mov     [rdi+39h], ax
0x140046d7e  movzx   r8d, r12w
0x140046d82  mov     [rsp+0D8h+TargetMdl], r14
0x140046d87  movzx   eax, r9w
0x140046d8b  sub     ax, r13w
0x140046d8f  sub     ax, 2
0x140046d93  add     ax, dx
0x140046d96  add     ax, r12w
0x140046d9a  add     ax, cx
0x140046d9d  mov     [rsi], ax
0x140046da0  mov     [rbx+1E0h], r14
0x140046da7  mov     [rbx+1E8h], r14
0x140046dae  lea     rax, [rbx+1FCh]
0x140046db5  mov     [rsp+0D8h+var_98], rax
0x140046dba  cmp     [rax], r14b
0x140046dbd  jz      loc_14004723F
0x140046dc3  lea     edx, [r11+r9]
0x140046dc7  mov     qword ptr [rsp+0D8h+BugCheckOnFailure], r14
0x140046dcc  xor     r9d, r9d
0x140046dcf  xor     r8d, r8d
0x140046dd2  mov     rcx, rdi
0x140046dd5  call    cs:__imp_RxAllocateMdl2
0x140046ddc  nop     dword ptr [rax+rax+00h]
0x140046de1  mov     rdi, rax
0x140046de4  mov     [rsp+0D8h+var_48], rax
0x140046dec  test    rax, rax
0x140046def  jnz     loc_1400471A3
0x140046df5  lea     r13, WPP_GLOBAL_Control
0x140046dfc  test    rdi, rdi
0x140046dff  jz      loc_1400474B6
0x140046e05  mov     esi, r14d
0x140046e08  test    r12d, r12d
0x140046e0b  jnz     loc_1400474EA
0x140046e11  test    r15d, r15d
0x140046e14  jnz     loc_140047125
0x140046e1a  mov     r13, r14
0x140046e1d  mov     [rsp+0D8h+var_58], r14
0x140046e25  mov     r12, r14
0x140046e28  mov     [rsp+0D8h+var_80], r14
0x140046e2d  test    esi, esi
0x140046e2f  jnz     loc_140046F85
0x140046e35  mov     esi, r14d
0x140046e38  xor     edx, edx; AccessMode
0x140046e3a  mov     r8d, 2; Operation
0x140046e40  mov     rcx, rdi; MemoryDescriptorList
0x140046e43  call    cs:__imp_MmProbeAndLockPages
0x140046e4a  nop     dword ptr [rax+rax+00h]
0x140046e4f  jmp     short loc_140046EB1
0x140046e51  mov     esi, eax
0x140046e53  xor     r14d, r14d
0x140046e56  mov     rbx, [rsp+0D8h+arg_0]
0x140046e5e  mov     r13, [rsp+0D8h+var_58]
0x140046e66  mov     r12, [rsp+0D8h+var_80]
0x140046e6b  mov     rdi, [rsp+0D8h+var_48]
0x140046e73  mov     eax, [rsp+0D8h+var_88]
0x140046e77  mov     [rsp+0D8h+var_8C], eax
0x140046e7b  mov     eax, [rsp+0D8h+var_90]
0x140046e7f  mov     [rsp+0D8h+arg_10], eax
0x140046e86  mov     rax, [rsp+0D8h+var_40]
0x140046e8e  mov     [rsp+0D8h+P], rax
0x140046e96  mov     eax, [rsp+0D8h+var_70]
0x140046e9a  mov     dword ptr [rsp+0D8h+arg_18], eax
0x140046ea1  mov     eax, [rsp+0D8h+var_6C]
0x140046ea5  mov     [rsp+0D8h+Length], eax
0x140046eac  mov     r15d, [rsp+0D8h+var_68]
0x140046eb1  test    esi, esi
0x140046eb3  jz      loc_1400471BB
0x140046eb9  mov     rcx, rdi; Mdl
0x140046ebc  call    cs:__imp_IoFreeMdl
0x140046ec3  nop     dword ptr [rax+rax+00h]
0x140046ec8  mov     rdi, r14
0x140046ecb  test    esi, esi
0x140046ecd  jnz     loc_140046F85
0x140046ed3  mov     [rsp+0D8h+arg_0], rdi
0x140046edb  test    r15d, r15d
0x140046ede  jnz     loc_1400475C7
0x140046ee4  mov     rax, [rsp+0D8h+var_98]
0x140046ee9  lea     rdx, WPP_GLOBAL_Control
0x140046ef0  mov     esi, [rsp+0D8h+var_8C]
0x140046ef4  test    esi, esi
0x140046ef6  jnz     loc_140047653
0x140046efc  mov     eax, [rsp+0D8h+Length]
0x140046f03  add     eax, r15d
0x140046f06  add     eax, dword ptr [rsp+0D8h+arg_18]
0x140046f0d  add     eax, esi
0x140046f0f  mov     dword ptr [rsp+0D8h+arg_0], eax
0x140046f16  mov     eax, [rbx+48h]
0x140046f19  test    al, 40h
0x140046f1b  jnz     loc_14004774E
0x140046f21  mov     rax, [rsp+0D8h+var_60]
0x140046f26  test    byte ptr [rbx+1FEh], 2
0x140046f2d  jnz     loc_14004775F
0x140046f33  cmp     [rbx+178h], esi
0x140046f39  jz      loc_14004729A
0x140046f3f  mov     eax, 3
0x140046f44  mov     [rbx+168h], eax; __annotation("TMF:",
0x140046f4a  mov     rcx, cs:WPP_GLOBAL_Control
0x140046f51  cmp     rcx, rdx
0x140046f54  jz      short loc_140046F63
0x140046f56  test    dword ptr [rcx+2Ch], 400h
0x140046f5d  jnz     loc_140047828
0x140046f63  mov     r9d, dword ptr [rsp+0D8h+arg_0]
0x140046f6b  mov     r8, rdi
0x140046f6e  mov     edx, 90000000h
0x140046f73  mov     rcx, rbx; pContext
0x140046f76  call    SmbCeTranceive
0x140046f7b  mov     esi, eax
0x140046f7d  test    eax, eax
0x140046f7f  jnz     loc_140047842
0x140046f85  test    r13, r13
0x140046f88  jnz     loc_140047883
0x140046f8e  mov     rax, [rsp+0D8h+TargetMdl]
0x140046f93  test    rax, rax
0x140046f96  jnz     loc_140047897
0x140046f9c  test    r12, r12
0x140046f9f  jnz     loc_1400478AB
0x140046fa5  test    rdi, rdi
0x140046fa8  jz      short loc_140046FC3
0x140046faa  test    byte ptr [rdi+0Ah], 2
0x140046fae  jnz     loc_1400478BF
0x140046fb4  mov     rcx, rdi; Mdl
0x140046fb7  call    cs:__imp_IoFreeMdl
0x140046fbe  nop     dword ptr [rax+rax+00h]
0x140046fc3  xor     edx, edx; Tag
0x140046fc5  mov     rcx, [rsp+0D8h+P]; P
0x140046fcd  call    cs:__imp_ExFreePoolWithTag
0x140046fd4  nop     dword ptr [rax+rax+00h]
0x140046fd9  cmp     esi, 103h
0x140046fdf  jnz     loc_1400478D3
0x140046fe5  mov     eax, esi
0x140046fe7  add     rsp, 0A0h
0x140046fee  pop     r15
0x140046ff0  pop     r14
0x140046ff2  pop     r13
0x140046ff4  pop     r12
0x140046ff6  pop     rdi
0x140046ff7  pop     rsi
0x140046ff8  pop     rbx
0x140046ff9  retn
0x140046ffb  lea     r8d, [r11+7]
0x140046fff  and     r8d, 0FFFFFFF8h
0x140047003  jmp     loc_140046CC1
0x140047008  mov     rcx, [rsp+0D8h+arg_18]
0x140047010  mov     [rcx], r15b
0x140047013  mov     rcx, [rbx+50h]
0x140047017  test    dword ptr [rcx+1A4h], 40000h
0x140047021  setnz   dl
0x140047024  mov     eax, 0Bh
0x140047029  movzx   ecx, word ptr [rbx+1FEh]
0x140047030  bt      cx, ax
0x140047034  setnb   cl
0x140047037  test    cl, dl
0x140047039  jz      short loc_14004706A
0x14004703b  mov     rax, [rbx+18h]
0x14004703f  mov     rcx, [rax+28h]; Irp
0x140047043  test    rcx, rcx
0x140047046  jz      loc_14004722F
0x14004704c  call    cs:__imp_IoGetRequestorProcessId
0x140047053  nop     dword ptr [rax+rax+00h]
0x140047058  or      dword ptr [rbx+48h], 4000h
0x14004705f  mov     [rdi+1Ah], ax
0x140047063  shr     eax, 10h
0x140047066  mov     [rdi+0Ch], ax
0x14004706a  bt      word ptr [rbx+1FEh], 0Bh
0x140047073  jb      loc_1400472BD
0x140047079  bt      word ptr [rbx+1FEh], 9
0x140047082  jnb     loc_140046C2B
0x140047088  mov     eax, 1000h
0x14004708d  or      [rdi+0Ah], ax
0x140047091  jmp     loc_140046C2B
0x140047096  test    dword ptr [rcx+2Ch], 400h
0x14004709d  jz      loc_140046D3E
0x1400470a3  mov     edx, 11h
0x1400470a8  mov     qword ptr [rsp+0D8h+BugCheckOnFailure], rsi
0x1400470ad  mov     r9, rdi
0x1400470b0  lea     r8, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids
0x1400470b7  mov     rcx, [rcx+18h]
0x1400470bb  call    WPP_SF_qq
0x1400470c0  mov     r9d, [rsp+0D8h+Length]
0x1400470c8  mov     r8d, [rsp+0D8h+arg_10]
0x1400470d0  lea     rdx, WPP_GLOBAL_Control
0x1400470d7  mov     r10d, dword ptr [rsp+0D8h+arg_18]
0x1400470df  mov     r11d, dword ptr [rsp+0D8h+var_98]
0x1400470e4  jmp     loc_140046D3E
0x1400470e9  test    dword ptr [rcx+2Ch], 400h
0x1400470f0  jz      loc_140046D5E
0x1400470f6  mov     edx, 12h
0x1400470fb  lea     r8, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids
0x140047102  mov     rcx, [rcx+18h]
0x140047106  call    WPP_SF_
0x14004710b  mov     r9d, [rsp+0D8h+Length]
0x140047113  mov     r10d, dword ptr [rsp+0D8h+arg_18]
0x14004711b  mov     r11d, dword ptr [rsp+0D8h+var_98]
0x140047120  jmp     loc_140046D5E
0x140047125  mov     rax, [rsp+0D8h+var_98]
0x14004712a  cmp     [rax], r14b
0x14004712d  jnz     loc_140046E1A
0x140047133  test    esi, esi
0x140047135  jnz     loc_140046E1A
0x14004713b  mov     qword ptr [rsp+0D8h+BugCheckOnFailure], r14
  ... truncated ...
```
