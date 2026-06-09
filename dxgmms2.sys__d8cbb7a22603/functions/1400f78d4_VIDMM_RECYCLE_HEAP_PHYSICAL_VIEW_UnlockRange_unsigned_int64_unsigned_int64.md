# VIDMM_RECYCLE_HEAP_PHYSICAL_VIEW::UnlockRange(unsigned __int64,unsigned __int64)

- ea: `0x1400f78d4`
- end: `0x1400f803e`
- name: `?UnlockRange@VIDMM_RECYCLE_HEAP_PHYSICAL_VIEW@@QEAAJ_K0@Z`
- size: `1898`
- prototype: `__int64 __fastcall(VIDMM_RECYCLE_HEAP_PHYSICAL_VIEW *this, struct _MDL *, struct _MDL *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x1400f7698`

## callees

- `0x140003490`
- `0x140004268`
- `0x14002e6c0`
- `0x1400312c8`
- `0x1400318ec`
- `0x1400321fc`
- `0x140059380`
- `0x1400f1564`
- `0x1400f78d4`
- `0x1400fb110`
- `0x14010ea34`
- `0x140110f0c`
- `0x140111a94`
- `0x1401131a8`
- `0x1401208cc`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1400f7fe0`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400f7fe0`
- `watchdog!WdLogSingleEntry4` at `0x1400f7a0e`
- `watchdog!WdLogSingleEntry4` at `0x1400f7a0e`
- `watchdog!WdLogSingleEntry5` at `0x1400f7bb0`
- `watchdog!WdLogSingleEntry5` at `0x1400f7bb0`
- `watchdog!WdLogSingleEntry0` at `0x1400f7b44`
- `watchdog!WdLogSingleEntry0` at `0x1400f7c0a`
- `watchdog!WdLogSingleEntry0` at `0x1400f7cc1`
- `watchdog!WdLogSingleEntry0` at `0x1400f7ed9`
- `watchdog!WdLogSingleEntry0` at `0x1400f7b44`
- `watchdog!WdLogSingleEntry0` at `0x1400f7c0a`
- `watchdog!WdLogSingleEntry0` at `0x1400f7cc1`
- `watchdog!WdLogSingleEntry0` at `0x1400f7ed9`
- `watchdog!WdLogSingleEntry1` at `0x1400f7d93`
- `watchdog!WdLogSingleEntry1` at `0x1400f7dc1`
- `watchdog!WdLogSingleEntry1` at `0x1400f7d93`
- `watchdog!WdLogSingleEntry1` at `0x1400f7dc1`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f7b8a`

## string_xrefs

- `0x1400f7ccf`: `Failed to Lock second MDL range in split front / back path.`
- `0x1400f7d9f`: `Failed to LockUnlock MDL range in front path. Status = 0x%I64x`
- `0x1400f7dcd`: `Failed to LockUnlock MDL range in back path. Status = 0x%I64x`
- `0x1400f7ee7`: `Failed to Lock first MDL range in split front / back path.`

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
          _InterlockedIncrement(&dword_1400877AC);
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
        _InterlockedIncrement(&dword_140087774);
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
            _InterlockedIncrement(&dword_140087774);
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
        _InterlockedIncrement(&dword_140087774);
        WdLogSingleEntry1(6, v57);
        v47 = L"Failed to LockUnlock MDL range in back path. Status = 0x%I64x";
        WdLogGlobalForLineNumber = 6092;
      }
      DxgkLogInternalTriageEvent(v45, 262145, v46, (_DWORD)v47, v4, 0, 0, 0);
      goto LABEL_20;
    }
  }
  g_DxgMmsBugcheckExportIndex = 1;
  WdLogSingleEntry5(0, 270, 52, 9, 0, 0);
  WdLogGlobalForLineNumber = 227;
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
    _InterlockedIncrement(&dword_140087774);
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
  if ( VIDMM_MDL_RANGE::Lock(v6, (void *)v4, v29, 0, 0) < 0 )
  {
    _InterlockedIncrement(&dword_140087774);
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
    _InterlockedIncrement(&dword_140087774);
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
0x1400f78d4  mov     [rsp+arg_10], rbx
0x1400f78d9  mov     [rsp+arg_8], rdx
0x1400f78de  push    rbp
0x1400f78df  push    rsi
0x1400f78e0  push    rdi
0x1400f78e1  push    r12
0x1400f78e3  push    r13
0x1400f78e5  push    r14
0x1400f78e7  push    r15
0x1400f78e9  sub     rsp, 70h
0x1400f78ed  xor     r10d, r10d
0x1400f78f0  mov     r13, rdx
0x1400f78f3  lea     rdx, [rcx+8]
0x1400f78f7  mov     rbp, r8
0x1400f78fa  or      r8d, 0FFFFFFFFh
0x1400f78fe  mov     r14, rcx
0x1400f7901  mov     rcx, [rdx]
0x1400f7904  mov     eax, r8d
0x1400f7907  mov     edi, r10d
0x1400f790a  cmp     rcx, rdx
0x1400f790d  jz      loc_1400F7B8A
0x1400f7913  test    eax, eax
0x1400f7915  jns     short loc_1400F7932
0x1400f7917  lea     rdi, [rcx-18h]
0x1400f791b  cmp     [rdi+10h], r13
0x1400f791f  ja      loc_1400F7A55
0x1400f7925  mov     eax, r8d
0x1400f7928  mov     rcx, [rcx]
0x1400f792b  cmp     rcx, rdx
0x1400f792e  jnz     short loc_1400F7913
0x1400f7930  test    eax, eax
0x1400f7932  jnz     loc_1400F7B8A
0x1400f7938  mov     rbx, rdi
0x1400f793b  mov     r15, [rdi+8]
0x1400f793f  cmp     [rdi+10h], rbp
0x1400f7943  jnb     short loc_1400F7962
0x1400f7945  mov     rdx, [rbx+18h]
0x1400f7949  mov     rcx, [rbx+28h]
0x1400f794d  add     rcx, 8
0x1400f7951  cmp     rdx, rcx
0x1400f7954  lea     rbx, [rdx-18h]
0x1400f7958  cmovz   rbx, r10
0x1400f795c  cmp     [rbx+10h], rbp
0x1400f7960  jb      short loc_1400F7945
0x1400f7962  mov     r12, [rbx+10h]
0x1400f7966  cmp     r15, r13
0x1400f7969  jnb     loc_1400F7D1F
0x1400f796f  mov     rcx, [r14]
0x1400f7972  mov     r8, r12
0x1400f7975  sub     r8, r15; unsigned __int64
0x1400f7978  mov     [rsp+0A8h+var_58], r10
0x1400f797d  mov     [rsp+0A8h+arg_18], r10
0x1400f7985  mov     [rsp+0A8h+arg_0], r10b
0x1400f798d  mov     rax, [rcx+20h]
0x1400f7991  mov     [rsp+0A8h+var_50], r8
0x1400f7996  mov     edx, [rax]
0x1400f7998  lea     eax, [rdx-3]
0x1400f799b  cmp     eax, 1
0x1400f799e  ja      loc_1400F7D7C
0x1400f79a4  mov     rcx, [rcx+38h]; Section
0x1400f79a8  lea     rax, [rsp+0A8h+arg_0]
0x1400f79b0  mov     [rsp+0A8h+var_68], rax; unsigned __int8 *
0x1400f79b5  cmp     edx, 4
0x1400f79b8  mov     [rsp+0A8h+var_70], r10b; unsigned __int8
0x1400f79bd  lea     rax, [rsp+0A8h+arg_18]
0x1400f79c5  mov     [rsp+0A8h+var_78], rax; void **
0x1400f79ca  setz    r9b; unsigned __int8
0x1400f79ce  lea     rax, [rsp+0A8h+var_58]
0x1400f79d3  mov     rdx, r15; unsigned __int64
0x1400f79d6  mov     [rsp+0A8h+var_80], rax; void **
0x1400f79db  call    ?VidMmRecycleHeapMapSection@@YAJPEAX_K1EEPEAPEAX2EPEAE@Z; VidMmRecycleHeapMapSection(void *,unsigned __int64,unsigned __int64,uchar,uchar,void * *,void * *,uchar,uchar *)
0x1400f79e0  movsxd  rsi, eax
0x1400f79e3  test    eax, eax
0x1400f79e5  jns     loc_1400F7AFF
0x1400f79eb  lock inc cs:dword_1400877AC
0x1400f79f2  mov     r15, [rsp+0A8h+var_50]
0x1400f79f7  mov     rbx, rsi
0x1400f79fa  mov     r9, [r14]
0x1400f79fd  mov     rdx, r15
0x1400f7a00  mov     r8, [rdi+8]
0x1400f7a04  mov     ecx, 6
0x1400f7a09  mov     [rsp+0A8h+var_88], rbx
0x1400f7a0e  call    cs:__imp_WdLogSingleEntry4
0x1400f7a15  nop     dword ptr [rax+rax+00h]
0x1400f7a1a  mov     cs:WdLogGlobalForLineNumber, 177Eh
0x1400f7a24  lea     r9, aUnableToMapLlu; "Unable to map %llu bytes from offset %l"...
0x1400f7a2b  mov     rax, [r14]
0x1400f7a2e  mov     edx, 40001h
0x1400f7a33  mov     qword ptr [rsp+0A8h+var_70], rbx
0x1400f7a38  mov     [rsp+0A8h+var_78], rax
0x1400f7a3d  mov     rax, [rdi+8]
0x1400f7a41  mov     [rsp+0A8h+var_80], rax
0x1400f7a46  mov     [rsp+0A8h+var_88], r15
0x1400f7a4b  call    DxgkLogInternalTriageEvent
0x1400f7a50  jmp     loc_1400F7AE4
0x1400f7a55  cmp     [rdi+8], rbp
0x1400f7a59  mov     eax, r10d
0x1400f7a5c  setnb   al
0x1400f7a5f  jmp     loc_1400F7928
0x1400f7a64  cmp     r12, rbp
0x1400f7a67  ja      loc_1400F7B16
0x1400f7a6d  mov     r8, [rdi+8]; unsigned __int64
0x1400f7a71  mov     r9, r13; unsigned __int64
0x1400f7a74  mov     rdx, rsi; void *
0x1400f7a77  mov     rcx, rdi; this
0x1400f7a7a  call    ?LockUnlock@VIDMM_MDL_RANGE@@QEAAJPEAX_K1@Z; VIDMM_MDL_RANGE::LockUnlock(void *,unsigned __int64,unsigned __int64)
0x1400f7a7f  xor     r12d, r12d
0x1400f7a82  movsxd  rsi, eax
0x1400f7a85  test    eax, eax
0x1400f7a87  js      loc_1400F7D84
0x1400f7a8d  cmp     rdi, rbx
0x1400f7a90  jnz     loc_1400F7E01
0x1400f7a96  mov     rax, [r14]
0x1400f7a99  mov     rcx, [rax+20h]
0x1400f7a9d  mov     eax, [rcx]
0x1400f7a9f  sub     eax, 3
0x1400f7aa2  cmp     eax, 1
0x1400f7aa5  jbe     loc_1400F7FD1
0x1400f7aab  test    esi, esi
0x1400f7aad  js      short loc_1400F7AE4
0x1400f7aaf  mov     rax, [r14]
0x1400f7ab2  sub     rbp, r13
0x1400f7ab5  shr     rbp, 0Ch
0x1400f7ab9  xor     edx, edx; Val
0x1400f7abb  shl     rbp, 3
0x1400f7abf  mov     r8, rbp; Size
0x1400f7ac2  sub     r13, [rax+28h]
0x1400f7ac6  mov     rax, [r14+20h]
0x1400f7aca  shr     r13, 0Ch
0x1400f7ace  lea     rcx, [rax+r13*8]; void *
0x1400f7ad2  call    memset
0x1400f7ad7  lea     rax, [r14+8]
0x1400f7adb  cmp     [rax], rax
0x1400f7ade  jz      loc_1400F8028
0x1400f7ae4  mov     rbx, [rsp+0A8h+arg_10]
0x1400f7aec  mov     eax, esi
0x1400f7aee  add     rsp, 70h
0x1400f7af2  pop     r15
0x1400f7af4  pop     r14
0x1400f7af6  pop     r13
0x1400f7af8  pop     r12
0x1400f7afa  pop     rdi
0x1400f7afb  pop     rsi
0x1400f7afc  pop     rbp
0x1400f7afd  retn
0x1400f7aff  mov     rsi, [rsp+0A8h+var_58]
0x1400f7b04  cmp     r15, r13
0x1400f7b07  jb      loc_1400F7A64
0x1400f7b0d  cmp     r12, rbp
0x1400f7b10  ja      loc_1400F7E66
0x1400f7b16  mov     edx, 32316956h
0x1400f7b1b  mov     ecx, 30h ; '0'
0x1400f7b20  mov     r8d, 102h
0x1400f7b26  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400f7b2b  xor     r12d, r12d
0x1400f7b2e  mov     r15, rax
0x1400f7b31  test    rax, rax
0x1400f7b34  jnz     loc_1400F7BC6
0x1400f7b3a  lock inc cs:dword_140087774
0x1400f7b41  lea     ecx, [rax+6]
0x1400f7b44  call    cs:__imp_WdLogSingleEntry0
0x1400f7b4b  nop     dword ptr [rax+rax+00h]
0x1400f7b50  mov     qword ptr [rsp+0A8h+var_70], r12
0x1400f7b55  lea     r9, aFailedToAlloca_78; "Failed to allocate memory for first MDL"...
0x1400f7b5c  mov     eax, 17F9h
0x1400f7b61  mov     [rsp+0A8h+var_78], r12
0x1400f7b66  mov     [rsp+0A8h+var_80], r12
0x1400f7b6b  mov     edx, 40001h
0x1400f7b70  mov     cs:WdLogGlobalForLineNumber, eax
0x1400f7b76  mov     [rsp+0A8h+var_88], rax
0x1400f7b7b  call    DxgkLogInternalTriageEvent
0x1400f7b80  mov     esi, 0C0000017h
0x1400f7b85  jmp     loc_1400F7A96
0x1400f7b8a  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400f7b91  mov     dword ptr [rax], 1
0x1400f7b97  xor     ecx, ecx
0x1400f7b99  mov     [rsp+0A8h+var_80], r10
0x1400f7b9e  mov     edx, 10Eh
0x1400f7ba3  mov     [rsp+0A8h+var_88], r10
0x1400f7ba8  lea     r9d, [rcx+9]
0x1400f7bac  lea     r8d, [rcx+34h]
0x1400f7bb0  call    cs:__imp_WdLogSingleEntry5
0x1400f7bb7  nop     dword ptr [rax+rax+00h]
0x1400f7bbc  mov     cs:WdLogGlobalForLineNumber, 0E3h
0x1400f7bc6  mov     rax, [rdi+8]
0x1400f7bca  mov     edx, 32316956h
0x1400f7bcf  mov     [r15+8], rax
0x1400f7bd3  mov     ecx, 30h ; '0'
0x1400f7bd8  mov     [r15], r12
0x1400f7bdb  mov     r8d, 102h
0x1400f7be1  mov     [r15+10h], r13
0x1400f7be5  mov     [r15+28h], r14
0x1400f7be9  mov     [r15+18h], r12
0x1400f7bed  mov     [r15+20h], r12
0x1400f7bf1  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400f7bf6  xor     ecx, ecx
0x1400f7bf8  mov     r12, rax
0x1400f7bfb  test    rax, rax
0x1400f7bfe  jnz     short loc_1400F7C53
0x1400f7c00  lock inc cs:dword_140087774
0x1400f7c07  lea     ecx, [rax+6]
0x1400f7c0a  call    cs:__imp_WdLogSingleEntry0
0x1400f7c11  nop     dword ptr [rax+rax+00h]
0x1400f7c16  mov     qword ptr [rsp+0A8h+var_70], r12
0x1400f7c1b  lea     r9, aFailedToAlloca_11; "Failed to allocate memory for second MD"...
0x1400f7c22  mov     eax, 1804h
0x1400f7c27  mov     [rsp+0A8h+var_78], r12
0x1400f7c2c  mov     [rsp+0A8h+var_80], r12
0x1400f7c31  mov     edx, 40001h
0x1400f7c36  mov     cs:WdLogGlobalForLineNumber, eax
0x1400f7c3c  mov     [rsp+0A8h+var_88], rax
0x1400f7c41  call    DxgkLogInternalTriageEvent
0x1400f7c46  mov     rcx, r15; this
0x1400f7c49  call    ??_GVIDMM_MDL_RANGE@@QEAAPEAXI@Z; VIDMM_MDL_RANGE::`scalar deleting destructor'(uint)
0x1400f7c4e  jmp     loc_1400F7B80
0x1400f7c53  mov     rax, [rbx+10h]
0x1400f7c57  xor     r9d, r9d; struct VIDMM_GLOBAL *
0x1400f7c5a  mov     [r12], rcx
0x1400f7c5e  mov     rdx, rsi; void *
0x1400f7c61  mov     [r12+10h], rax
0x1400f7c66  mov     [r12+8], rbp
0x1400f7c6b  mov     [r12+28h], r14
0x1400f7c70  mov     [r12+18h], rcx
0x1400f7c75  mov     [r12+20h], rcx
0x1400f7c7a  mov     [rsp+0A8h+var_88], rcx; struct VIDMM_GLOBAL_ALLOC *
0x1400f7c7f  mov     rcx, r15; this
0x1400f7c82  call    ?Lock@VIDMM_MDL_RANGE@@QEAAJPEAXW4_LOCK_OPERATION@@PEAVVIDMM_GLOBAL@@PEBUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_MDL_RANGE::Lock(void *,_LOCK_OPERATION,VIDMM_GLOBAL *,VIDMM_GLOBAL_ALLOC const *)
0x1400f7c87  test    eax, eax
0x1400f7c89  js      loc_1400F7ECD
0x1400f7c8f  sub     rsi, [rdi+8]
0x1400f7c93  xor     r9d, r9d; struct VIDMM_GLOBAL *
0x1400f7c96  mov     rcx, r12; this
0x1400f7c99  mov     [rsp+0A8h+var_88], 0; struct VIDMM_GLOBAL_ALLOC *
0x1400f7ca2  lea     rdx, [rsi+rbp]; void *
0x1400f7ca6  call    ?Lock@VIDMM_MDL_RANGE@@QEAAJPEAXW4_LOCK_OPERATION@@PEAVVIDMM_GLOBAL@@PEBUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_MDL_RANGE::Lock(void *,_LOCK_OPERATION,VIDMM_GLOBAL *,VIDMM_GLOBAL_ALLOC const *)
0x1400f7cab  mov     esi, eax
0x1400f7cad  test    eax, eax
0x1400f7caf  jns     loc_1400F7F1C
0x1400f7cb5  lock inc cs:dword_140087774
0x1400f7cbc  mov     ecx, 6
0x1400f7cc1  call    cs:__imp_WdLogSingleEntry0
0x1400f7cc8  nop     dword ptr [rax+rax+00h]
0x1400f7ccd  xor     ecx, ecx
0x1400f7ccf  lea     r9, aFailedToLockSe; "Failed to Lock second MDL range in spli"...
0x1400f7cd6  mov     qword ptr [rsp+0A8h+var_70], rcx
0x1400f7cdb  mov     eax, 182Ah
0x1400f7ce0  mov     [rsp+0A8h+var_78], rcx
0x1400f7ce5  mov     edx, 40001h
0x1400f7cea  mov     [rsp+0A8h+var_80], rcx
0x1400f7cef  mov     [rsp+0A8h+var_88], rax
0x1400f7cf4  mov     cs:WdLogGlobalForLineNumber, eax
0x1400f7cfa  call    DxgkLogInternalTriageEvent
0x1400f7cff  mov     rcx, r15; this
0x1400f7d02  call    ?Unlock@VIDMM_MDL_RANGE@@QEAAXXZ; VIDMM_MDL_RANGE::Unlock(void)
0x1400f7d07  mov     rcx, r15; this
0x1400f7d0a  call    ??_GVIDMM_MDL_RANGE@@QEAAPEAXI@Z; VIDMM_MDL_RANGE::`scalar deleting destructor'(uint)
0x1400f7d0f  mov     rcx, r12; this
0x1400f7d12  call    ??_GVIDMM_MDL_RANGE@@QEAAPEAXI@Z; VIDMM_MDL_RANGE::`scalar deleting destructor'(uint)
0x1400f7d17  xor     r12d, r12d
0x1400f7d1a  jmp     loc_1400F7B80
0x1400f7d1f  cmp     r12, rbp
0x1400f7d22  ja      loc_1400F796F
0x1400f7d28  xor     r12d, r12d
0x1400f7d2b  mov     esi, r12d
0x1400f7d2e  mov     r15b, r12b
0x1400f7d31  mov     rcx, rdi; this
0x1400f7d34  call    ?Unlock@VIDMM_MDL_RANGE@@QEAAXXZ; VIDMM_MDL_RANGE::Unlock(void)
0x1400f7d39  mov     r8, rdi
0x1400f7d3c  cmp     rdi, rbx
0x1400f7d3f  jz      short loc_1400F7D5A
0x1400f7d41  mov     rdx, [rdi+18h]
0x1400f7d45  mov     rcx, [rdi+28h]
0x1400f7d49  add     rcx, 8
0x1400f7d4d  cmp     rdx, rcx
0x1400f7d50  lea     rdi, [rdx-18h]
0x1400f7d54  cmovz   rdi, r12
0x1400f7d58  jmp     short loc_1400F7D5D
0x1400f7d5a  mov     r15b, 1
0x1400f7d5d  mov     rcx, r8; this
0x1400f7d60  call    ?RemoveFromLockedRanges@VIDMM_MDL_RANGE@@QEAAXXZ; VIDMM_MDL_RANGE::RemoveFromLockedRanges(void)
0x1400f7d65  test    r8, r8
0x1400f7d68  jz      short loc_1400F7D72
0x1400f7d6a  mov     rcx, r8; this
0x1400f7d6d  call    ??_GVIDMM_MDL_RANGE@@QEAAPEAXI@Z; VIDMM_MDL_RANGE::`scalar deleting destructor'(uint)
0x1400f7d72  test    r15b, r15b
0x1400f7d75  jz      short loc_1400F7D31
0x1400f7d77  jmp     loc_1400F7AAF
0x1400f7d7c  mov     rsi, r15
0x1400f7d7f  jmp     loc_1400F7B04
0x1400f7d84  lock inc cs:dword_140087774
0x1400f7d8b  mov     rdx, rsi
0x1400f7d8e  mov     ecx, 6
0x1400f7d93  call    cs:__imp_WdLogSingleEntry1
0x1400f7d9a  nop     dword ptr [rax+rax+00h]
0x1400f7d9f  lea     r9, aFailedToLockun; "Failed to LockUnlock MDL range in front"...
0x1400f7da6  mov     cs:WdLogGlobalForLineNumber, 1794h
0x1400f7db0  jmp     short loc_1400F7DDE
0x1400f7db2  lock inc cs:dword_140087774
0x1400f7db9  mov     rdx, rsi
0x1400f7dbc  mov     ecx, 6
  ... truncated ...
```
