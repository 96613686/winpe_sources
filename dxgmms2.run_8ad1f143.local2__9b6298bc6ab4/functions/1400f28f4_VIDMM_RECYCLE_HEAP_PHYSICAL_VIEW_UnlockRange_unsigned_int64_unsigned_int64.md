# VIDMM_RECYCLE_HEAP_PHYSICAL_VIEW::UnlockRange(unsigned __int64,unsigned __int64)

- ea: `0x1400f28f4`
- end: `0x1400f305e`
- name: `?UnlockRange@VIDMM_RECYCLE_HEAP_PHYSICAL_VIEW@@QEAAJ_K0@Z`
- size: `1898`
- prototype: `__int64 __fastcall(VIDMM_RECYCLE_HEAP_PHYSICAL_VIEW *this, struct _MDL *, struct _MDL *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x1400f26b8`

## callees

- `0x1400037a0`
- `0x1400045ec`
- `0x140030ae0`
- `0x140033458`
- `0x140033638`
- `0x140033e0c`
- `0x140058ac0`
- `0x1400ede0c`
- `0x1400ee4c8`
- `0x1400f28f4`
- `0x1400f6130`
- `0x140109604`
- `0x14010e114`
- `0x1401108e0`
- `0x14011d0ec`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1400f3000`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400f3000`
- `watchdog!WdLogSingleEntry4` at `0x1400f2a2e`
- `watchdog!WdLogSingleEntry4` at `0x1400f2a2e`
- `watchdog!WdLogSingleEntry5` at `0x1400f2bd0`
- `watchdog!WdLogSingleEntry5` at `0x1400f2bd0`
- `watchdog!WdLogSingleEntry0` at `0x1400f2b64`
- `watchdog!WdLogSingleEntry0` at `0x1400f2c2a`
- `watchdog!WdLogSingleEntry0` at `0x1400f2ce1`
- `watchdog!WdLogSingleEntry0` at `0x1400f2ef9`
- `watchdog!WdLogSingleEntry0` at `0x1400f2b64`
- `watchdog!WdLogSingleEntry0` at `0x1400f2c2a`
- `watchdog!WdLogSingleEntry0` at `0x1400f2ce1`
- `watchdog!WdLogSingleEntry0` at `0x1400f2ef9`
- `watchdog!WdLogSingleEntry1` at `0x1400f2db3`
- `watchdog!WdLogSingleEntry1` at `0x1400f2de1`
- `watchdog!WdLogSingleEntry1` at `0x1400f2db3`
- `watchdog!WdLogSingleEntry1` at `0x1400f2de1`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f2baa`

## string_xrefs

- `0x1400f2cef`: `Failed to Lock second MDL range in split front / back path.`
- `0x1400f2dbf`: `Failed to LockUnlock MDL range in front path. Status = 0x%I64x`
- `0x1400f2ded`: `Failed to LockUnlock MDL range in back path. Status = 0x%I64x`
- `0x1400f2f07`: `Failed to Lock first MDL range in split front / back path.`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 __fastcall VIDMM_RECYCLE_HEAP_PHYSICAL_VIEW::UnlockRange(
        VIDMM_RECYCLE_HEAP_PHYSICAL_VIEW *this,
        struct _MDL *a2,
        struct _MDL *a3)
{
  __int64 *v3; // rbx
  __int64 v4; // rsi
  __int64 v5; // r12
  VIDMM_MDL_RANGE *v6; // r15
  struct _MDL *v7; // r13
  char *v8; // rdx
  char *v11; // rcx
  int v12; // eax
  __int64 *v13; // rdi
  bool v14; // zf
  unsigned __int64 v15; // r15
  __int64 v16; // rdx
  __int64 v17; // rcx
  unsigned __int64 v18; // r12
  __int64 v19; // rcx
  _DWORD *v20; // rax
  int v21; // eax
  __int64 v22; // r15
  int v23; // ecx
  int v24; // r8d
  int v25; // eax
  int v27; // ecx
  int v28; // r8d
  enum _LOCK_OPERATION v29; // r8d
  VIDMM_MDL_RANGE *v30; // r12
  int v31; // ecx
  int v32; // r8d
  unsigned int v33; // edx
  __int64 v34; // rax
  enum _LOCK_OPERATION v35; // r8d
  int v36; // r8d
  unsigned int v37; // edx
  unsigned int v38; // edx
  char v39; // r15
  VIDMM_MDL_RANGE *v40; // r8
  __int64 v41; // rdx
  __int64 v42; // rcx
  unsigned int v43; // edx
  VIDMM_MDL_RANGE *v44; // r8
  int v45; // ecx
  int v46; // r8d
  const wchar_t *v47; // r9
  __int64 v48; // rdx
  char v49; // r15
  __int64 v50; // rcx
  VIDMM_MDL_RANGE *v51; // rdi
  VIDMM_MDL_RANGE *v52; // r8
  __int64 v53; // rdx
  __int64 v54; // rcx
  unsigned int v55; // edx
  VIDMM_MDL_RANGE *v56; // r8
  int v57; // eax
  __int64 v58; // r8
  VIDMM_MDL_RANGE *v59; // rcx
  __int64 v60; // rdx
  unsigned int v61; // edx
  VIDMM_MDL_RANGE *v62; // r9
  int v63; // r8d
  __int64 v64; // rdx
  struct VIDMM_MDL_RANGE *v65; // r8
  __int64 v66; // rdx
  __int64 v67; // rcx
  struct VIDMM_MDL_RANGE *v68; // r8
  char v69; // r13
  VIDMM_MDL_RANGE *v70; // r8
  __int64 v71; // rdx
  __int64 v72; // rcx
  unsigned int v73; // edx
  VIDMM_MDL_RANGE *v74; // r8
  VIDMM_RECYCLE_HEAP_MGR *CurrentProcess; // rcx
  unsigned __int64 SmallAllocationSize; // rax
  struct _EPROCESS *v77; // rcx
  unsigned __int8 v78; // [rsp+20h] [rbp-88h]
  struct VIDMM_MDL_RANGE *v79; // [rsp+50h] [rbp-58h] BYREF
  unsigned __int64 v80; // [rsp+58h] [rbp-50h]
  struct VIDMM_MDL_RANGE *v81; // [rsp+60h] [rbp-48h]
  unsigned __int8 v82; // [rsp+B0h] [rbp+8h] BYREF
  struct _MDL *v83; // [rsp+B8h] [rbp+10h]
  void *v84; // [rsp+C8h] [rbp+20h] BYREF

  v83 = a2;
  v7 = a2;
  v8 = (char *)this + 8;
  v11 = (char *)*((_QWORD *)this + 1);
  v12 = -1;
  v13 = 0;
  if ( v11 != v8 )
  {
    while ( 1 )
    {
      v14 = v12 == 0;
      if ( v12 >= 0 )
        break;
      v13 = (__int64 *)(v11 - 24);
      if ( *((_QWORD *)v11 - 1) > (unsigned __int64)v7 )
        v12 = *((_QWORD *)v11 - 2) >= (unsigned __int64)a3;
      else
        v12 = -1;
      v11 = *(char **)v11;
      if ( v11 == v8 )
      {
        v14 = v12 == 0;
        break;
      }
    }
    if ( v14 )
    {
      v3 = v13;
      v15 = v13[1];
      while ( v3[2] < (unsigned __int64)a3 )
      {
        v16 = v3[3];
        v17 = v3[5] + 8;
        v3 = (__int64 *)(v16 - 24);
        if ( v16 == v17 )
          v3 = 0;
      }
      v18 = v3[2];
      if ( v15 >= (unsigned __int64)v7 && v18 <= (unsigned __int64)a3 )
      {
        LODWORD(v4) = 0;
        v39 = 0;
        do
        {
          VIDMM_MDL_RANGE::Unlock((VIDMM_MDL_RANGE *)v13);
          v40 = (VIDMM_MDL_RANGE *)v13;
          if ( v13 == v3 )
          {
            v39 = 1;
          }
          else
          {
            v41 = v13[3];
            v42 = v13[5] + 8;
            v13 = (__int64 *)(v41 - 24);
            if ( v41 == v42 )
              v13 = 0;
          }
          VIDMM_MDL_RANGE::RemoveFromLockedRanges(v40);
          if ( v44 )
            VIDMM_MDL_RANGE::`scalar deleting destructor'(v44, v43);
        }
        while ( !v39 );
LABEL_22:
        memset(
          (void *)(*((_QWORD *)this + 4) + 8 * (((unsigned __int64)v7 - *(_QWORD *)(*(_QWORD *)this + 40LL)) >> 12)),
          0,
          8 * ((unsigned __int64)((char *)a3 - (char *)v7) >> 12));
        if ( *((VIDMM_RECYCLE_HEAP_PHYSICAL_VIEW **)this + 1) == (VIDMM_RECYCLE_HEAP_PHYSICAL_VIEW *)((char *)this + 8) )
        {
          operator delete(*((void **)this + 4));
          *((_QWORD *)this + 4) = 0;
          *((_QWORD *)this + 3) = 0;
        }
        return (unsigned int)v4;
      }
      v19 = *(_QWORD *)this;
      v79 = 0;
      v84 = 0;
      v82 = 0;
      v20 = *(_DWORD **)(v19 + 32);
      v80 = v18 - v15;
      if ( (unsigned int)(*v20 - 3) > 1 )
      {
        v4 = v15;
      }
      else
      {
        v21 = VidMmRecycleHeapMapSection(
                *(PVOID *)(v19 + 56),
                v15,
                v18 - v15,
                *v20 == 4,
                v78,
                (void **)&v79,
                &v84,
                0,
                &v82);
        v4 = v21;
        if ( v21 < 0 )
        {
          _InterlockedIncrement(&dword_1400867CC);
          v22 = v80;
          WdLogSingleEntry4(6, v80, v13[1], *(_QWORD *)this, v21);
          WdLogGlobalForLineNumber = 6014;
          DxgkLogInternalTriageEvent(
            v23,
            262145,
            v24,
            (unsigned int)L"Unable to map %llu bytes from offset %llu in block 0x%I64p - Status:0x%I64p",
            v22,
            v13[1],
            *(_QWORD *)this,
            v4);
          return (unsigned int)v4;
        }
        v4 = (__int64)v79;
      }
      if ( v15 < (unsigned __int64)v7 )
      {
        if ( v18 > (unsigned __int64)a3 )
          goto LABEL_28;
        v25 = VIDMM_MDL_RANGE::LockUnlock((PMDL *)v13, (void *)v4, (struct _MDL *)v13[1], v7);
        v4 = v25;
        if ( v25 >= 0 )
        {
          if ( v13 != v3 )
          {
            v48 = v13[3];
            v49 = 0;
            v50 = v13[5] + 8;
            v51 = (VIDMM_MDL_RANGE *)(v48 - 24);
            if ( v48 == v50 )
              v51 = 0;
            do
            {
              VIDMM_MDL_RANGE::Unlock(v51);
              v52 = v51;
              if ( v51 == (VIDMM_MDL_RANGE *)v3 )
              {
                v49 = 1;
              }
              else
              {
                v53 = *((_QWORD *)v51 + 3);
                v54 = *((_QWORD *)v51 + 5) + 8LL;
                v51 = (VIDMM_MDL_RANGE *)(v53 - 24);
                if ( v53 == v54 )
                  v51 = 0;
              }
              VIDMM_MDL_RANGE::RemoveFromLockedRanges(v52);
              if ( v56 )
                VIDMM_MDL_RANGE::`scalar deleting destructor'(v56, v55);
            }
            while ( !v49 );
          }
          goto LABEL_20;
        }
        _InterlockedIncrement(&dword_140086794);
        WdLogSingleEntry1(6, v25);
        v47 = L"Failed to LockUnlock MDL range in front path. Status = 0x%I64x";
        WdLogGlobalForLineNumber = 6036;
      }
      else
      {
        if ( v18 <= (unsigned __int64)a3 )
        {
LABEL_28:
          v5 = 0;
          v6 = (VIDMM_MDL_RANGE *)operator new(48, 842099030, 258);
          if ( !v6 )
          {
            _InterlockedIncrement(&dword_140086794);
            WdLogSingleEntry0(6);
            WdLogGlobalForLineNumber = 6137;
            DxgkLogInternalTriageEvent(
              v27,
              262145,
              v28,
              (unsigned int)L"Failed to allocate memory for first MDL range.",
              6137,
              0,
              0,
              0);
LABEL_30:
            LODWORD(v4) = -1073741801;
            goto LABEL_20;
          }
          goto LABEL_32;
        }
        v57 = VIDMM_MDL_RANGE::LockUnlock((PMDL *)v3, (char *)a3 + v4 - v13[1], a3, (struct _MDL *)v3[2]);
        v4 = v57;
        if ( v57 >= 0 )
        {
          while ( v13 != v3 )
          {
            VIDMM_MDL_RANGE::Unlock((VIDMM_MDL_RANGE *)v13);
            v58 = v13[3];
            v59 = (VIDMM_MDL_RANGE *)v13;
            v60 = v13[5] + 8;
            v13 = (__int64 *)(v58 - 24);
            if ( v58 == v60 )
              v13 = 0;
            VIDMM_MDL_RANGE::RemoveFromLockedRanges(v59);
            if ( v62 )
              VIDMM_MDL_RANGE::`scalar deleting destructor'(v62, v61);
          }
          goto LABEL_20;
        }
        _InterlockedIncrement(&dword_140086794);
        WdLogSingleEntry1(6, v57);
        v47 = L"Failed to LockUnlock MDL range in back path. Status = 0x%I64x";
        WdLogGlobalForLineNumber = 6092;
      }
      DxgkLogInternalTriageEvent(v45, 262145, v46, (_DWORD)v47, v4, 0, 0, 0);
      goto LABEL_20;
    }
  }
  g_DxgMmsBugcheckExportIndex = 1;
  WdLogSingleEntry5(0, 270, 52);
  WdLogGlobalForLineNumber = 222;
LABEL_32:
  *((_QWORD *)v6 + 1) = v13[1];
  *(_QWORD *)v6 = v5;
  *((_QWORD *)v6 + 2) = v7;
  *((_QWORD *)v6 + 5) = this;
  *((_QWORD *)v6 + 3) = v5;
  *((_QWORD *)v6 + 4) = v5;
  v30 = (VIDMM_MDL_RANGE *)operator new(48, 842099030, 258);
  if ( !v30 )
  {
    _InterlockedIncrement(&dword_140086794);
    WdLogSingleEntry0(6);
    WdLogGlobalForLineNumber = 6148;
    DxgkLogInternalTriageEvent(
      v31,
      262145,
      v32,
      (unsigned int)L"Failed to allocate memory for second MDL range",
      6148,
      0,
      0,
      0);
    VIDMM_MDL_RANGE::`scalar deleting destructor'(v6, v33);
    goto LABEL_30;
  }
  v34 = v3[2];
  *(_QWORD *)v30 = 0;
  *((_QWORD *)v30 + 2) = v34;
  *((_QWORD *)v30 + 1) = a3;
  *((_QWORD *)v30 + 5) = this;
  *((_QWORD *)v30 + 3) = 0;
  *((_QWORD *)v30 + 4) = 0;
  if ( (int)VIDMM_MDL_RANGE::Lock(v6, (void *)v4, v29, 0, 0) < 0 )
  {
    _InterlockedIncrement(&dword_140086794);
    WdLogSingleEntry0(6);
    WdLogGlobalForLineNumber = 6166;
    DxgkLogInternalTriageEvent(
      0,
      262145,
      v63,
      (unsigned int)L"Failed to Lock first MDL range in split front / back path.",
      6166,
      0,
      0,
      0);
    goto LABEL_37;
  }
  LODWORD(v4) = VIDMM_MDL_RANGE::Lock(v30, (char *)a3 + v4 - v13[1], v35, 0, 0);
  if ( (int)v4 < 0 )
  {
    _InterlockedIncrement(&dword_140086794);
    WdLogSingleEntry0(6);
    WdLogGlobalForLineNumber = 6186;
    DxgkLogInternalTriageEvent(
      0,
      262145,
      v36,
      (unsigned int)L"Failed to Lock second MDL range in split front / back path.",
      6186,
      0,
      0,
      0);
    VIDMM_MDL_RANGE::Unlock(v6);
LABEL_37:
    VIDMM_MDL_RANGE::`scalar deleting destructor'(v6, v37);
    VIDMM_MDL_RANGE::`scalar deleting destructor'(v30, v38);
    goto LABEL_30;
  }
  v64 = v13[4];
  v14 = v64 == v13[5] + 8;
  v65 = (struct VIDMM_MDL_RANGE *)(v64 - 24);
  v66 = v3[3];
  if ( v14 )
    v65 = 0;
  v67 = v3[5] + 8;
  v79 = v65;
  v68 = (struct VIDMM_MDL_RANGE *)(v66 - 24);
  if ( v66 == v67 )
    v68 = 0;
  v69 = 0;
  v81 = v68;
  do
  {
    VIDMM_MDL_RANGE::Unlock((VIDMM_MDL_RANGE *)v13);
    v70 = (VIDMM_MDL_RANGE *)v13;
    if ( v13 == v3 )
    {
      v69 = 1;
    }
    else
    {
      v71 = v13[3];
      v72 = v13[5] + 8;
      v13 = (__int64 *)(v71 - 24);
      if ( v71 == v72 )
        v13 = 0;
    }
    VIDMM_MDL_RANGE::RemoveFromLockedRanges(v70);
    if ( v74 )
      VIDMM_MDL_RANGE::`scalar deleting destructor'(v74, v73);
  }
  while ( !v69 );
  VIDMM_MDL_RANGE::InsertBetween(v6, v79, v30);
  VIDMM_MDL_RANGE::InsertBetween(v30, v6, v81);
  v7 = v83;
LABEL_20:
  if ( (unsigned int)(**(_DWORD **)(*(_QWORD *)this + 32LL) - 3) <= 1 )
  {
    if ( v82 )
      CurrentProcess = 0;
    else
      CurrentProcess = (VIDMM_RECYCLE_HEAP_MGR *)PsGetCurrentProcess();
    SmallAllocationSize = VIDMM_RECYCLE_HEAP_MGR::GetSmallAllocationSize(CurrentProcess, 0);
    if ( v80 <= SmallAllocationSize )
      VidMmUnmapView(v77, v84);
    else
      VidMmUnmapViewAsync(v77, *(PVOID *)(*(_QWORD *)this + 56LL), v84);
  }
  if ( (int)v4 >= 0 )
    goto LABEL_22;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400f28f4  mov     [rsp+arg_10], rbx
0x1400f28f9  mov     [rsp+arg_8], rdx
0x1400f28fe  push    rbp
0x1400f28ff  push    rsi
0x1400f2900  push    rdi
0x1400f2901  push    r12
0x1400f2903  push    r13
0x1400f2905  push    r14
0x1400f2907  push    r15
0x1400f2909  sub     rsp, 70h
0x1400f290d  xor     r10d, r10d
0x1400f2910  mov     r13, rdx
0x1400f2913  lea     rdx, [rcx+8]
0x1400f2917  mov     rbp, r8
0x1400f291a  or      r8d, 0FFFFFFFFh
0x1400f291e  mov     r14, rcx
0x1400f2921  mov     rcx, [rdx]
0x1400f2924  mov     eax, r8d
0x1400f2927  mov     edi, r10d
0x1400f292a  cmp     rcx, rdx
0x1400f292d  jz      loc_1400F2BAA
0x1400f2933  test    eax, eax
0x1400f2935  jns     short loc_1400F2952
0x1400f2937  lea     rdi, [rcx-18h]
0x1400f293b  cmp     [rdi+10h], r13
0x1400f293f  ja      loc_1400F2A75
0x1400f2945  mov     eax, r8d
0x1400f2948  mov     rcx, [rcx]
0x1400f294b  cmp     rcx, rdx
0x1400f294e  jnz     short loc_1400F2933
0x1400f2950  test    eax, eax
0x1400f2952  jnz     loc_1400F2BAA
0x1400f2958  mov     rbx, rdi
0x1400f295b  mov     r15, [rdi+8]
0x1400f295f  cmp     [rdi+10h], rbp
0x1400f2963  jnb     short loc_1400F2982
0x1400f2965  mov     rdx, [rbx+18h]
0x1400f2969  mov     rcx, [rbx+28h]
0x1400f296d  add     rcx, 8
0x1400f2971  cmp     rdx, rcx
0x1400f2974  lea     rbx, [rdx-18h]
0x1400f2978  cmovz   rbx, r10
0x1400f297c  cmp     [rbx+10h], rbp
0x1400f2980  jb      short loc_1400F2965
0x1400f2982  mov     r12, [rbx+10h]
0x1400f2986  cmp     r15, r13
0x1400f2989  jnb     loc_1400F2D3F
0x1400f298f  mov     rcx, [r14]
0x1400f2992  mov     r8, r12
0x1400f2995  sub     r8, r15; unsigned __int64
0x1400f2998  mov     [rsp+0A8h+var_58], r10
0x1400f299d  mov     [rsp+0A8h+arg_18], r10
0x1400f29a5  mov     [rsp+0A8h+arg_0], r10b
0x1400f29ad  mov     rax, [rcx+20h]
0x1400f29b1  mov     [rsp+0A8h+var_50], r8
0x1400f29b6  mov     edx, [rax]
0x1400f29b8  lea     eax, [rdx-3]
0x1400f29bb  cmp     eax, 1
0x1400f29be  ja      loc_1400F2D9C
0x1400f29c4  mov     rcx, [rcx+38h]; Section
0x1400f29c8  lea     rax, [rsp+0A8h+arg_0]
0x1400f29d0  mov     [rsp+0A8h+var_68], rax; unsigned __int8 *
0x1400f29d5  cmp     edx, 4
0x1400f29d8  mov     [rsp+0A8h+var_70], r10b; unsigned __int8
0x1400f29dd  lea     rax, [rsp+0A8h+arg_18]
0x1400f29e5  mov     [rsp+0A8h+var_78], rax; void **
0x1400f29ea  setz    r9b; unsigned __int8
0x1400f29ee  lea     rax, [rsp+0A8h+var_58]
0x1400f29f3  mov     rdx, r15; unsigned __int64
0x1400f29f6  mov     [rsp+0A8h+var_80], rax; void **
0x1400f29fb  call    ?VidMmRecycleHeapMapSection@@YAJPEAX_K1EEPEAPEAX2EPEAE@Z; VidMmRecycleHeapMapSection(void *,unsigned __int64,unsigned __int64,uchar,uchar,void * *,void * *,uchar,uchar *)
0x1400f2a00  movsxd  rsi, eax
0x1400f2a03  test    eax, eax
0x1400f2a05  jns     loc_1400F2B1F
0x1400f2a0b  lock inc cs:dword_1400867CC
0x1400f2a12  mov     r15, [rsp+0A8h+var_50]
0x1400f2a17  mov     rbx, rsi
0x1400f2a1a  mov     r9, [r14]
0x1400f2a1d  mov     rdx, r15
0x1400f2a20  mov     r8, [rdi+8]
0x1400f2a24  mov     ecx, 6
0x1400f2a29  mov     [rsp+0A8h+var_88], rbx
0x1400f2a2e  call    cs:__imp_WdLogSingleEntry4
0x1400f2a35  nop     dword ptr [rax+rax+00h]
0x1400f2a3a  mov     cs:WdLogGlobalForLineNumber, 177Eh
0x1400f2a44  lea     r9, aUnableToMapLlu; "Unable to map %llu bytes from offset %l"...
0x1400f2a4b  mov     rax, [r14]
0x1400f2a4e  mov     edx, 40001h
0x1400f2a53  mov     qword ptr [rsp+0A8h+var_70], rbx
0x1400f2a58  mov     [rsp+0A8h+var_78], rax
0x1400f2a5d  mov     rax, [rdi+8]
0x1400f2a61  mov     [rsp+0A8h+var_80], rax
0x1400f2a66  mov     [rsp+0A8h+var_88], r15
0x1400f2a6b  call    DxgkLogInternalTriageEvent
0x1400f2a70  jmp     loc_1400F2B04
0x1400f2a75  cmp     [rdi+8], rbp
0x1400f2a79  mov     eax, r10d
0x1400f2a7c  setnb   al
0x1400f2a7f  jmp     loc_1400F2948
0x1400f2a84  cmp     r12, rbp
0x1400f2a87  ja      loc_1400F2B36
0x1400f2a8d  mov     r8, [rdi+8]; unsigned __int64
0x1400f2a91  mov     r9, r13; unsigned __int64
0x1400f2a94  mov     rdx, rsi; void *
0x1400f2a97  mov     rcx, rdi; this
0x1400f2a9a  call    ?LockUnlock@VIDMM_MDL_RANGE@@QEAAJPEAX_K1@Z; VIDMM_MDL_RANGE::LockUnlock(void *,unsigned __int64,unsigned __int64)
0x1400f2a9f  xor     r12d, r12d
0x1400f2aa2  movsxd  rsi, eax
0x1400f2aa5  test    eax, eax
0x1400f2aa7  js      loc_1400F2DA4
0x1400f2aad  cmp     rdi, rbx
0x1400f2ab0  jnz     loc_1400F2E21
0x1400f2ab6  mov     rax, [r14]
0x1400f2ab9  mov     rcx, [rax+20h]
0x1400f2abd  mov     eax, [rcx]
0x1400f2abf  sub     eax, 3
0x1400f2ac2  cmp     eax, 1
0x1400f2ac5  jbe     loc_1400F2FF1
0x1400f2acb  test    esi, esi
0x1400f2acd  js      short loc_1400F2B04
0x1400f2acf  mov     rax, [r14]
0x1400f2ad2  sub     rbp, r13
0x1400f2ad5  shr     rbp, 0Ch
0x1400f2ad9  xor     edx, edx; Val
0x1400f2adb  shl     rbp, 3
0x1400f2adf  mov     r8, rbp; Size
0x1400f2ae2  sub     r13, [rax+28h]
0x1400f2ae6  mov     rax, [r14+20h]
0x1400f2aea  shr     r13, 0Ch
0x1400f2aee  lea     rcx, [rax+r13*8]; void *
0x1400f2af2  call    memset
0x1400f2af7  lea     rax, [r14+8]
0x1400f2afb  cmp     [rax], rax
0x1400f2afe  jz      loc_1400F3048
0x1400f2b04  mov     rbx, [rsp+0A8h+arg_10]
0x1400f2b0c  mov     eax, esi
0x1400f2b0e  add     rsp, 70h
0x1400f2b12  pop     r15
0x1400f2b14  pop     r14
0x1400f2b16  pop     r13
0x1400f2b18  pop     r12
0x1400f2b1a  pop     rdi
0x1400f2b1b  pop     rsi
0x1400f2b1c  pop     rbp
0x1400f2b1d  retn
0x1400f2b1f  mov     rsi, [rsp+0A8h+var_58]
0x1400f2b24  cmp     r15, r13
0x1400f2b27  jb      loc_1400F2A84
0x1400f2b2d  cmp     r12, rbp
0x1400f2b30  ja      loc_1400F2E86
0x1400f2b36  mov     edx, 32316956h
0x1400f2b3b  mov     ecx, 30h ; '0'
0x1400f2b40  mov     r8d, 102h
0x1400f2b46  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400f2b4b  xor     r12d, r12d
0x1400f2b4e  mov     r15, rax
0x1400f2b51  test    rax, rax
0x1400f2b54  jnz     loc_1400F2BE6
0x1400f2b5a  lock inc cs:dword_140086794
0x1400f2b61  lea     ecx, [rax+6]
0x1400f2b64  call    cs:__imp_WdLogSingleEntry0
0x1400f2b6b  nop     dword ptr [rax+rax+00h]
0x1400f2b70  mov     qword ptr [rsp+0A8h+var_70], r12
0x1400f2b75  lea     r9, aFailedToAlloca_74; "Failed to allocate memory for first MDL"...
0x1400f2b7c  mov     eax, 17F9h
0x1400f2b81  mov     [rsp+0A8h+var_78], r12
0x1400f2b86  mov     [rsp+0A8h+var_80], r12
0x1400f2b8b  mov     edx, 40001h
0x1400f2b90  mov     cs:WdLogGlobalForLineNumber, eax
0x1400f2b96  mov     [rsp+0A8h+var_88], rax
0x1400f2b9b  call    DxgkLogInternalTriageEvent
0x1400f2ba0  mov     esi, 0C0000017h
0x1400f2ba5  jmp     loc_1400F2AB6
0x1400f2baa  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400f2bb1  mov     dword ptr [rax], 1
0x1400f2bb7  xor     ecx, ecx
0x1400f2bb9  mov     [rsp+0A8h+var_80], r10
0x1400f2bbe  mov     edx, 10Eh
0x1400f2bc3  mov     [rsp+0A8h+var_88], r10
0x1400f2bc8  lea     r9d, [rcx+9]
0x1400f2bcc  lea     r8d, [rcx+34h]
0x1400f2bd0  call    cs:__imp_WdLogSingleEntry5
0x1400f2bd7  nop     dword ptr [rax+rax+00h]
0x1400f2bdc  mov     cs:WdLogGlobalForLineNumber, 0DEh
0x1400f2be6  mov     rax, [rdi+8]
0x1400f2bea  mov     edx, 32316956h
0x1400f2bef  mov     [r15+8], rax
0x1400f2bf3  mov     ecx, 30h ; '0'
0x1400f2bf8  mov     [r15], r12
0x1400f2bfb  mov     r8d, 102h
0x1400f2c01  mov     [r15+10h], r13
0x1400f2c05  mov     [r15+28h], r14
0x1400f2c09  mov     [r15+18h], r12
0x1400f2c0d  mov     [r15+20h], r12
0x1400f2c11  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400f2c16  xor     ecx, ecx
0x1400f2c18  mov     r12, rax
0x1400f2c1b  test    rax, rax
0x1400f2c1e  jnz     short loc_1400F2C73
0x1400f2c20  lock inc cs:dword_140086794
0x1400f2c27  lea     ecx, [rax+6]
0x1400f2c2a  call    cs:__imp_WdLogSingleEntry0
0x1400f2c31  nop     dword ptr [rax+rax+00h]
0x1400f2c36  mov     qword ptr [rsp+0A8h+var_70], r12
0x1400f2c3b  lea     r9, aFailedToAlloca_9; "Failed to allocate memory for second MD"...
0x1400f2c42  mov     eax, 1804h
0x1400f2c47  mov     [rsp+0A8h+var_78], r12
0x1400f2c4c  mov     [rsp+0A8h+var_80], r12
0x1400f2c51  mov     edx, 40001h
0x1400f2c56  mov     cs:WdLogGlobalForLineNumber, eax
0x1400f2c5c  mov     [rsp+0A8h+var_88], rax
0x1400f2c61  call    DxgkLogInternalTriageEvent
0x1400f2c66  mov     rcx, r15; this
0x1400f2c69  call    ??_GVIDMM_MDL_RANGE@@QEAAPEAXI@Z; VIDMM_MDL_RANGE::`scalar deleting destructor'(uint)
0x1400f2c6e  jmp     loc_1400F2BA0
0x1400f2c73  mov     rax, [rbx+10h]
0x1400f2c77  xor     r9d, r9d; struct VIDMM_GLOBAL *
0x1400f2c7a  mov     [r12], rcx
0x1400f2c7e  mov     rdx, rsi; void *
0x1400f2c81  mov     [r12+10h], rax
0x1400f2c86  mov     [r12+8], rbp
0x1400f2c8b  mov     [r12+28h], r14
0x1400f2c90  mov     [r12+18h], rcx
0x1400f2c95  mov     [r12+20h], rcx
0x1400f2c9a  mov     [rsp+0A8h+var_88], rcx; struct VIDMM_GLOBAL_ALLOC *
0x1400f2c9f  mov     rcx, r15; this
0x1400f2ca2  call    ?Lock@VIDMM_MDL_RANGE@@QEAAJPEAXW4_LOCK_OPERATION@@PEAVVIDMM_GLOBAL@@PEBUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_MDL_RANGE::Lock(void *,_LOCK_OPERATION,VIDMM_GLOBAL *,VIDMM_GLOBAL_ALLOC const *)
0x1400f2ca7  test    eax, eax
0x1400f2ca9  js      loc_1400F2EED
0x1400f2caf  sub     rsi, [rdi+8]
0x1400f2cb3  xor     r9d, r9d; struct VIDMM_GLOBAL *
0x1400f2cb6  mov     rcx, r12; this
0x1400f2cb9  mov     [rsp+0A8h+var_88], 0; struct VIDMM_GLOBAL_ALLOC *
0x1400f2cc2  lea     rdx, [rsi+rbp]; void *
0x1400f2cc6  call    ?Lock@VIDMM_MDL_RANGE@@QEAAJPEAXW4_LOCK_OPERATION@@PEAVVIDMM_GLOBAL@@PEBUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_MDL_RANGE::Lock(void *,_LOCK_OPERATION,VIDMM_GLOBAL *,VIDMM_GLOBAL_ALLOC const *)
0x1400f2ccb  mov     esi, eax
0x1400f2ccd  test    eax, eax
0x1400f2ccf  jns     loc_1400F2F3C
0x1400f2cd5  lock inc cs:dword_140086794
0x1400f2cdc  mov     ecx, 6
0x1400f2ce1  call    cs:__imp_WdLogSingleEntry0
0x1400f2ce8  nop     dword ptr [rax+rax+00h]
0x1400f2ced  xor     ecx, ecx
0x1400f2cef  lea     r9, aFailedToLockSe; "Failed to Lock second MDL range in spli"...
0x1400f2cf6  mov     qword ptr [rsp+0A8h+var_70], rcx
0x1400f2cfb  mov     eax, 182Ah
0x1400f2d00  mov     [rsp+0A8h+var_78], rcx
0x1400f2d05  mov     edx, 40001h
0x1400f2d0a  mov     [rsp+0A8h+var_80], rcx
0x1400f2d0f  mov     [rsp+0A8h+var_88], rax
0x1400f2d14  mov     cs:WdLogGlobalForLineNumber, eax
0x1400f2d1a  call    DxgkLogInternalTriageEvent
0x1400f2d1f  mov     rcx, r15; this
0x1400f2d22  call    ?Unlock@VIDMM_MDL_RANGE@@QEAAXXZ; VIDMM_MDL_RANGE::Unlock(void)
0x1400f2d27  mov     rcx, r15; this
0x1400f2d2a  call    ??_GVIDMM_MDL_RANGE@@QEAAPEAXI@Z; VIDMM_MDL_RANGE::`scalar deleting destructor'(uint)
0x1400f2d2f  mov     rcx, r12; this
0x1400f2d32  call    ??_GVIDMM_MDL_RANGE@@QEAAPEAXI@Z; VIDMM_MDL_RANGE::`scalar deleting destructor'(uint)
0x1400f2d37  xor     r12d, r12d
0x1400f2d3a  jmp     loc_1400F2BA0
0x1400f2d3f  cmp     r12, rbp
0x1400f2d42  ja      loc_1400F298F
0x1400f2d48  xor     r12d, r12d
0x1400f2d4b  mov     esi, r12d
0x1400f2d4e  mov     r15b, r12b
0x1400f2d51  mov     rcx, rdi; this
0x1400f2d54  call    ?Unlock@VIDMM_MDL_RANGE@@QEAAXXZ; VIDMM_MDL_RANGE::Unlock(void)
0x1400f2d59  mov     r8, rdi
0x1400f2d5c  cmp     rdi, rbx
0x1400f2d5f  jz      short loc_1400F2D7A
0x1400f2d61  mov     rdx, [rdi+18h]
0x1400f2d65  mov     rcx, [rdi+28h]
0x1400f2d69  add     rcx, 8
0x1400f2d6d  cmp     rdx, rcx
0x1400f2d70  lea     rdi, [rdx-18h]
0x1400f2d74  cmovz   rdi, r12
0x1400f2d78  jmp     short loc_1400F2D7D
0x1400f2d7a  mov     r15b, 1
0x1400f2d7d  mov     rcx, r8; this
0x1400f2d80  call    ?RemoveFromLockedRanges@VIDMM_MDL_RANGE@@QEAAXXZ; VIDMM_MDL_RANGE::RemoveFromLockedRanges(void)
0x1400f2d85  test    r8, r8
0x1400f2d88  jz      short loc_1400F2D92
0x1400f2d8a  mov     rcx, r8; this
0x1400f2d8d  call    ??_GVIDMM_MDL_RANGE@@QEAAPEAXI@Z; VIDMM_MDL_RANGE::`scalar deleting destructor'(uint)
0x1400f2d92  test    r15b, r15b
0x1400f2d95  jz      short loc_1400F2D51
0x1400f2d97  jmp     loc_1400F2ACF
0x1400f2d9c  mov     rsi, r15
0x1400f2d9f  jmp     loc_1400F2B24
0x1400f2da4  lock inc cs:dword_140086794
0x1400f2dab  mov     rdx, rsi
0x1400f2dae  mov     ecx, 6
0x1400f2db3  call    cs:__imp_WdLogSingleEntry1
0x1400f2dba  nop     dword ptr [rax+rax+00h]
0x1400f2dbf  lea     r9, aFailedToLockun; "Failed to LockUnlock MDL range in front"...
0x1400f2dc6  mov     cs:WdLogGlobalForLineNumber, 1794h
0x1400f2dd0  jmp     short loc_1400F2DFE
0x1400f2dd2  lock inc cs:dword_140086794
0x1400f2dd9  mov     rdx, rsi
0x1400f2ddc  mov     ecx, 6
  ... truncated ...
```
