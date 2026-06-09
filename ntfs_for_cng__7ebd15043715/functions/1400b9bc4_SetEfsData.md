# SetEfsData

- ea: `0x1400b9bc4`
- end: `0x1400ba629`
- name: `SetEfsData`
- size: `2661`
- prototype: `__int64 __fastcall(__int64, int, int, __int64, __int64, PVOID *, char, __int64, int *, _BYTE *, PVOID *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation`

## callers

- `0x1401158b0`

## callees

- `0x14001ebf0`
- `0x140059234`
- `0x1400593c0`
- `0x1400596c0`
- `0x1400b3838`
- `0x1400b9bc4`
- `0x1400ba630`
- `0x1401153c0`
- `0x140119778`
- `0x140142c10`
- `0x14014516c`
- `0x140145d8c`
- `0x1401462cc`
- `0x1401464f0`
- `0x140146fe4`
- `0x140147658`
- `0x1401487d0`
- `0x140232554`
- `0x140243f80`
- `0x140254f4c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400b9e86`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba019`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba02f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba0ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba138`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b9e86`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba019`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba02f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba0ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba138`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400b9c78`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400b9cfd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400b9e46`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400b9f27`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400b9fff`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ba07c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ba0cc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ba120`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ba3cc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ba45b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ba607`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402bebb6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402bec30`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400b9c78`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400b9cfd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400b9e46`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400b9f27`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400b9fff`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ba07c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ba0cc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ba120`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ba3cc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ba45b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ba607`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402bebb6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402bec30`
- `ksecdd!BCryptDestroyKey` at `0x1400b9e18`
- `ksecdd!BCryptDestroyKey` at `0x1400ba3a1`
- `ksecdd!BCryptDestroyKey` at `0x1400b9e18`
- `ksecdd!BCryptDestroyKey` at `0x1400ba3a1`

## pseudocode

```c
__int64 __fastcall SetEfsData(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        __int64 a5,
        PVOID *a6,
        char a7,
        __int64 a8,
        int *a9,
        _BYTE *a10,
        PVOID *a11)
{
  char v11; // r12
  char v12; // r14
  unsigned int *v14; // rdi
  int EfsData; // ebx
  unsigned int *KeyBlobBuffer; // rax
  __int64 v17; // rcx
  __int64 v18; // r8
  _QWORD *v19; // r12
  __int64 v20; // rax
  _BYTE *v21; // rcx
  PVOID *v22; // r15
  char *v23; // rax
  unsigned int *v24; // r8
  unsigned int *v25; // r14
  unsigned int v26; // eax
  char *v27; // rcx
  __int64 v28; // rax
  _BYTE *v29; // rcx
  PVOID *v30; // r14
  __int64 v31; // rcx
  __int64 v32; // rax
  _BYTE *v33; // rcx
  __int64 v35; // r12
  int v36; // r14d
  PVOID v37; // r14
  __int64 v38; // rax
  _BYTE *v39; // rdx
  __int64 v40; // rax
  _BYTE *v41; // rcx
  __int64 v42; // rax
  _BYTE *v43; // rcx
  __int64 v44; // rax
  _BYTE *v45; // rcx
  __int64 v46; // rcx
  _BYTE *v47; // rdx
  __int64 v48; // rcx
  _WORD *v49; // r14
  __int64 v50; // r8
  __int64 v51; // rdx
  int v52; // eax
  PVOID *v53; // r14
  char *v54; // rax
  unsigned int *v55; // r13
  _QWORD *v56; // r12
  unsigned int *v57; // r14
  unsigned int v58; // eax
  char *v59; // rcx
  __int64 v60; // rax
  _BYTE *v61; // rcx
  __int64 v62; // rax
  _BYTE *v63; // rcx
  __int64 v64; // rax
  _DWORD **v65; // r12
  __int64 v66; // rcx
  unsigned int *v67; // r14
  unsigned int v68; // r15d
  __int64 v69; // rcx
  unsigned int v70; // eax
  __int64 v71; // rbx
  unsigned int *v72; // rcx
  __int64 v73; // rax
  _BYTE *v74; // rcx
  __int64 v75; // [rsp+0h] [rbp-D8h] BYREF
  int v76; // [rsp+40h] [rbp-98h] BYREF
  int v77; // [rsp+44h] [rbp-94h] BYREF
  int v78; // [rsp+48h] [rbp-90h] BYREF
  unsigned int *v79; // [rsp+50h] [rbp-88h]
  unsigned int Size; // [rsp+58h] [rbp-80h] BYREF
  unsigned int Size_4; // [rsp+5Ch] [rbp-7Ch]
  __int64 v82; // [rsp+60h] [rbp-78h]
  PVOID P; // [rsp+68h] [rbp-70h] BYREF
  int v84[2]; // [rsp+70h] [rbp-68h] BYREF
  void *Src; // [rsp+78h] [rbp-60h] BYREF
  unsigned int *v86; // [rsp+80h] [rbp-58h]
  _DWORD *v87; // [rsp+88h] [rbp-50h]
  __int64 v88; // [rsp+90h] [rbp-48h]
  __int64 *v89; // [rsp+98h] [rbp-40h]
  unsigned int **v90; // [rsp+E0h] [rbp+8h] BYREF
  int v91; // [rsp+E8h] [rbp+10h]
  int v92; // [rsp+F0h] [rbp+18h]
  __int64 v93; // [rsp+F8h] [rbp+20h]

  v93 = a4;
  v92 = a3;
  v91 = a2;
  v89 = &v75;
  v11 = a3;
  v12 = a2;
  LOBYTE(v90) = 0;
  v14 = 0;
  v79 = 0;
  EfsData = 0;
  *(_QWORD *)v84 = 0;
  Src = 0;
  v78 = 0;
  P = 0;
  Size = 0;
  v76 = 0;
  v82 = 0;
  v77 = *a9;
  if ( (*(_DWORD *)(a1 + 8) & 2) == 0 )
    goto LABEL_33;
  KeyBlobBuffer = GetKeyBlobBufferEx(*(_DWORD *)(*(_QWORD *)(a1 + 24) + 4LL), *(_DWORD *)(*(_QWORD *)(a1 + 24) + 8LL));
  v14 = KeyBlobBuffer;
  if ( !KeyBlobBuffer )
    return 3221225626LL;
  if ( !(unsigned __int8)SetKeyTable(KeyBlobBuffer, &v77, *(_QWORD *)(a1 + 24)) )
  {
    ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v14 + 9), v14);
    v18 = 3449;
LABEL_5:
    EfsData = -1073741790;
LABEL_6:
    EfspTraceLogAssert(v17, 6, v18, (unsigned int)EfsData);
    return (unsigned int)EfsData;
  }
  v79 = v14;
  if ( *(_DWORD *)(a1 + 4) != 1 )
    goto LABEL_33;
  v19 = *a11;
  if ( !*a11 )
  {
    v11 = v92;
LABEL_33:
    v22 = a6;
    goto LABEL_34;
  }
  EfsData = EfsSameContext(v14, *v19, &v90, 0);
  v20 = *v14 - 87LL;
  v21 = v14 + 20;
  if ( *v14 != 87 )
  {
    do
    {
      *v21++ = 0;
      --v20;
    }
    while ( v20 );
  }
  ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v14 + 9), v14);
  if ( EfsData < 0 )
  {
    v18 = 3463;
    goto LABEL_6;
  }
  if ( !(_BYTE)v90 )
  {
    if ( (*(_DWORD *)(a1 + 8) & 1) != 0 )
    {
      EfsData = -1073741811;
      v18 = 3482;
      goto LABEL_6;
    }
    return 0;
  }
  v14 = 0;
  v79 = 0;
  v22 = a6;
  if ( a6 )
  {
    v23 = (char *)*a6;
    if ( *a6 )
    {
      if ( !v19[1] )
      {
        v24 = (unsigned int *)(v23 + 16);
        v86 = (unsigned int *)(v23 + 16);
        *((_QWORD *)v23 + 5) = *v19 + 80LL;
        *((_DWORD *)v23 + 12) = *(_DWORD *)*v19;
        *((_QWORD *)v23 + 7) = *(_QWORD *)(*v19 + 56LL);
        *((_QWORD *)v23 + 8) = *(_QWORD *)(*v19 + 64LL);
        *((_DWORD *)v23 + 18) = 512;
        *((_DWORD *)v23 + 19) = *(_DWORD *)(*v19 + 4LL);
        *((_DWORD *)v23 + 20) = *(_DWORD *)(*v19 + 24LL);
        *((_QWORD *)v23 + 4) = v23 + 40;
        v90 = (unsigned int **)*v22;
        v25 = *v90;
        if ( *v90 )
        {
          v26 = v25[1];
          if ( (v26 == 26126 || v26 == 26128 || v26 == 536897040 || v26 == 1073767952) && v25[20] == 1 )
          {
            v27 = (char *)*((_QWORD *)v25 + 11);
            if ( (unsigned __int64)(v27 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              BCryptDestroyKey(v27);
          }
          v28 = *v25 - 87LL;
          v29 = v25 + 20;
          if ( *v25 != 87 )
          {
            do
            {
              *v29++ = 0;
              --v28;
            }
            while ( v28 );
          }
          ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v25 + 9), v25);
          *v90 = 0;
          v24 = v86;
        }
        *(_QWORD *)*v22 = *v19;
        *((_QWORD *)*v22 + 1) = v24;
        v30 = a11;
        ExFreePoolWithTag(*a11, 0x6D736645u);
        *v30 = *v22;
        *v22 = 0;
        v12 = v91;
      }
    }
  }
  v11 = v92;
LABEL_34:
  v31 = *(unsigned int *)(a1 + 8);
  if ( (*(_DWORD *)(a1 + 8) & 1) == 0 && (v31 & 8) == 0 )
    goto LABEL_103;
  if ( (*(_DWORD *)(a1 + 8) & 1) != 0 )
  {
    if ( (*(_DWORD *)(a1 + 12) & 2) == 0 )
      EfspTraceLogAssert(v31, 6, 3548, 3221225473LL);
    if ( (v12 & 1) != 0 )
    {
      if ( v14 )
      {
        v32 = *v14 - 87LL;
        v33 = v14 + 20;
        if ( *v14 != 87 )
        {
          do
          {
            *v33++ = 0;
            --v32;
          }
          while ( v32 );
        }
        ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v14 + 9), v14);
      }
      return 3221225634LL;
    }
  }
  if ( (v11 & 2) == 0 )
  {
    v35 = a5;
LABEL_85:
    v36 = v93;
    goto LABEL_86;
  }
  v35 = a5;
  v36 = v93;
  EfsData = EfsReadEfsData(v93, a5, 0, (unsigned int)&P, (__int64)&Size, (__int64)&v76);
  Size_4 = EfsData;
  if ( EfsData < 0 || v76 != 512 && v76 != 0x10000 )
  {
    if ( v14 )
    {
      v44 = *v14 - 87LL;
      v45 = v14 + 20;
      if ( *v14 != 87 )
      {
        do
        {
          *v45++ = 0;
          --v44;
        }
        while ( v44 );
      }
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v14 + 9), v14);
    }
    if ( P )
      ExFreePoolWithTag(P, 0);
    if ( v76 == 2048 )
    {
      return (unsigned int)-1073741670;
    }
    else if ( EfsData >= 0 )
    {
      return (unsigned int)-1073741808;
    }
    return (unsigned int)EfsData;
  }
  if ( v76 == 0x10000 )
  {
    v37 = P;
    EfsData = EfsGetEfsStreamInfo(P, Size, 8);
    if ( EfsData < 0 )
    {
      if ( v14 )
      {
        v38 = *v14 - 87LL;
        v39 = v14 + 20;
        if ( *v14 != 87 )
        {
          do
          {
            *v39++ = 0;
            --v38;
          }
          while ( v38 );
        }
        ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v14 + 9), v14);
      }
      if ( v37 )
        ExFreePoolWithTag(v37, 0);
      return (unsigned int)EfsData;
    }
    ExFreePoolWithTag(v37, 0);
    if ( (_DWORD)v82 == 1 && (v82 & 0x300000000LL) != 0 )
    {
      if ( (*(_DWORD *)(a1 + 8) & 1) != 0 )
      {
        if ( v14 )
        {
          v40 = *v14 - 87LL;
          v41 = v14 + 20;
          if ( *v14 != 87 )
          {
            do
            {
              *v41++ = 0;
              --v40;
            }
            while ( v40 );
          }
          ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v14 + 9), v14);
        }
        v18 = 3667;
        goto LABEL_5;
      }
      if ( (v82 & 0x200000000LL) != 0 )
      {
        *a10 = 1;
        if ( v14 )
        {
          v42 = *v14 - 87LL;
          v43 = v14 + 20;
          if ( *v14 != 87 )
          {
            do
            {
              *v43++ = 0;
              --v42;
            }
            while ( v42 );
          }
          ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v14 + 9), v14);
        }
        return 0;
      }
    }
    goto LABEL_85;
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
LABEL_86:
  if ( (*(_DWORD *)(a1 + 8) & 1) == 0 )
    goto LABEL_103;
  EfsData = EfspGetEfsStreamForWrite(*(_QWORD *)(a1 + 16), **(unsigned int **)(a1 + 16), &Src, &v78);
  if ( EfsData < 0 )
  {
    if ( !v14 )
      return (unsigned int)EfsData;
    v46 = *v14 - 87LL;
    v47 = v14 + 20;
    if ( *v14 != 87 )
    {
      do
      {
        *v47++ = 0;
        --v46;
      }
      while ( v46 );
    }
LABEL_149:
    ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v14 + 9), v14);
    return (unsigned int)EfsData;
  }
  EfsData = NtOfsCreateAttributeEx(v35, v36, (unsigned int)&DestinationString, 256, 1, 1, (__int64)v84);
  Size_4 = EfsData;
  if ( EfsData == -1073741808 )
    EfspTraceLogAssert(v48, 6, 3722, 3221225488LL);
  if ( EfsData >= 0 )
  {
    v49 = *(_WORD **)v84;
    NtOfsSetLength(v35);
    NtOfsPutData(v35, (int)v49, 0, v78, Src);
    if ( !v49 || (unsigned __int16)(*v49 - 1795) > 2u )
      NtOfsFlushAttribute(v35, v49, 0);
    NtOfsMarkFileModified(v35, v93, v50, 0x40000);
    if ( *a11 && (*(_DWORD *)(a1 + 8) & 2) == 0 )
    {
      LOBYTE(v51) = a7;
      EfsCleanup(a11, v51, a8);
    }
    if ( v49 )
      NtfsDecrementCloseCounts(v35, (__int64)v49, 0, 1, 0, 1, 0);
LABEL_103:
    if ( !v14 || (*(_DWORD *)(a1 + 8) & 2) == 0 )
      return (unsigned int)EfsData;
    v52 = *(_DWORD *)(a1 + 4);
    v53 = a11;
    if ( v52 != 1 || *a11 )
    {
      if ( v52 != 4 )
        return (unsigned int)EfsData;
      v65 = (_DWORD **)*a11;
      if ( *a11 )
      {
        v67 = *v65;
        v68 = **v65;
        v69 = *v14;
        if ( (unsigned int)v69 > v68 )
        {
          EfsData = -1073740974;
          EfspTraceLogAssert(v69, 6, 3954, 3221226322LL);
        }
        else
        {
          v70 = v14[1];
          if ( (v70 == 26126 || v70 == 26128 || v70 == 536897040 || v70 == 1073767952) && v14[20] == 1 )
          {
            EfsData = EfspCopyAesKeyBlob(*v65);
          }
          else
          {
            v71 = *((_QWORD *)v67 + 9);
            memmove(*v65, v14, *v14);
            *((_QWORD *)v67 + 9) = v71;
            if ( *v14 < v68 )
            {
              *v67 = v68;
              memset((char *)v67 + *v14, 0, v68 - *v14);
            }
            EfsData = 0;
          }
          if ( EfsData >= 0 )
          {
            *((_DWORD *)v65 + 4) = 87119;
            v65[3] = 0;
            v72 = *v65;
            v65[5] = *v65 + 20;
            *((_DWORD *)v65 + 12) = *v72;
            v65[7] = (_DWORD *)*((_QWORD *)v72 + 7);
            v65[8] = (_DWORD *)*((_QWORD *)v72 + 8);
            *((_DWORD *)v65 + 18) = 512;
            *((_DWORD *)v65 + 19) = v72[1];
            *((_DWORD *)v65 + 20) = v72[6];
            v65[4] = v65 + 5;
            v65[1] = v65 + 2;
            *a9 = v77;
          }
        }
        v73 = *v14 - 87LL;
        v74 = v14 + 20;
        if ( *v14 != 87 )
        {
          do
          {
            *v74++ = 0;
            --v73;
          }
          while ( v73 );
        }
        goto LABEL_149;
      }
      v66 = AllocateAndSetContextDataBlock(v14);
      if ( v66 )
      {
        *a9 = v77;
        *v53 = (PVOID)v66;
        return (unsigned int)EfsData;
      }
    }
    else
    {
      if ( v22 )
      {
        v54 = (char *)*v22;
        if ( *v22 )
        {
          v55 = (unsigned int *)(v54 + 16);
          *((_QWORD *)v54 + 5) = v14 + 20;
          *((_DWORD *)v54 + 12) = *v14;
          *((_QWORD *)v54 + 7) = *((_QWORD *)v14 + 7);
          *((_QWORD *)v54 + 8) = *((_QWORD *)v14 + 8);
          *((_DWORD *)v54 + 18) = 512;
          *((_DWORD *)v54 + 19) = v14[1];
          *((_DWORD *)v54 + 20) = v14[6];
          *((_QWORD *)v54 + 4) = v54 + 40;
          v56 = *v22;
          v57 = *(unsigned int **)*v22;
          if ( v57 )
          {
            v58 = v57[1];
            if ( (v58 == 26126 || v58 == 26128 || v58 == 536897040 || v58 == 1073767952) && v57[20] == 1 )
            {
              v59 = (char *)*((_QWORD *)v57 + 11);
              if ( (unsigned __int64)(v59 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
                BCryptDestroyKey(v59);
            }
            v60 = *v57 - 87LL;
            v61 = v57 + 20;
            if ( *v57 != 87 )
            {
              do
              {
                *v61++ = 0;
                --v60;
              }
              while ( v60 );
            }
            ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v57 + 9), v57);
            *v56 = 0;
          }
          *(_QWORD *)*v22 = v14;
          *((_QWORD *)*v22 + 1) = v55;
          *a9 = v77;
          *a11 = *v22;
          *v22 = 0;
          return (unsigned int)EfsData;
        }
      }
      v64 = AllocateAndSetContextDataBlock(v14);
      if ( v64 )
      {
        *a9 = v77;
        *v53 = (PVOID)v64;
        return (unsigned int)EfsData;
      }
    }
    return 3221225626LL;
  }
  if ( v14 )
  {
    v62 = *v14 - 87LL;
    v88 = v62;
    v63 = v14 + 20;
    v87 = v14 + 20;
    while ( v62 )
    {
      *v63++ = 0;
      v87 = v63;
      v88 = --v62;
    }
    ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v14 + 9), v14);
    v79 = 0;
  }
  local_unwind_0((__int64)v89, (__int64)&loc_1400BA485);
  return Size_4;
}

```

## disassembly

```asm
0x1400b9bc4  mov     rax, rsp
0x1400b9bc7  mov     [rax+20h], r9
0x1400b9bcb  mov     [rax+18h], r8d
0x1400b9bcf  mov     [rax+10h], edx
0x1400b9bd2  push    rbx
0x1400b9bd3  push    rsi
0x1400b9bd4  push    rdi
0x1400b9bd5  push    r12
0x1400b9bd7  push    r13
0x1400b9bd9  push    r14
0x1400b9bdb  push    r15
0x1400b9bdd  sub     rsp, 0A0h
0x1400b9be4  mov     [rsp+0D8h+var_40], rsp
0x1400b9bec  mov     r12d, r8d
0x1400b9bef  mov     r14d, edx
0x1400b9bf2  mov     r13, rcx
0x1400b9bf5  xor     r9d, r9d
0x1400b9bf8  mov     [rax+8], r9b
0x1400b9bfc  mov     edi, r9d
0x1400b9bff  mov     [rsp+0D8h+var_88], r9
0x1400b9c04  mov     ebx, r9d
0x1400b9c07  mov     [rax-68h], r9
0x1400b9c0b  mov     [rax-60h], r9
0x1400b9c0f  mov     [rsp+0D8h+var_90], r9d
0x1400b9c14  mov     [rax-70h], r9
0x1400b9c18  mov     [rax-80h], r9d
0x1400b9c1c  mov     [rsp+0D8h+var_98], r9d
0x1400b9c21  mov     [rax-78h], r9
0x1400b9c25  mov     rax, [rsp+0D8h+arg_40]
0x1400b9c2d  mov     eax, [rax]
0x1400b9c2f  mov     [rsp+0D8h+var_94], eax
0x1400b9c33  mov     eax, [rcx+8]
0x1400b9c36  test    al, 2
0x1400b9c38  jz      loc_1400B9EBA
0x1400b9c3e  mov     rcx, [rcx+18h]
0x1400b9c42  mov     edx, [rcx+8]
0x1400b9c45  mov     ecx, [rcx+4]
0x1400b9c48  call    GetKeyBlobBufferEx
0x1400b9c4d  mov     rdi, rax
0x1400b9c50  test    rax, rax
0x1400b9c53  jz      loc_1400BA4D2
0x1400b9c59  mov     r8, [r13+18h]
0x1400b9c5d  lea     rdx, [rsp+0D8h+var_94]
0x1400b9c62  mov     rcx, rax
0x1400b9c65  call    SetKeyTable
0x1400b9c6a  xor     r9d, r9d
0x1400b9c6d  test    al, al
0x1400b9c6f  jnz     short loc_1400B9CA1
0x1400b9c71  mov     rdx, rdi; Entry
0x1400b9c74  mov     rcx, [rdi+48h]; Lookaside
0x1400b9c78  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400b9c7f  nop     dword ptr [rax+rax+00h]
0x1400b9c84  mov     r8d, 0D79h
0x1400b9c8a  mov     ebx, 0C0000022h
0x1400b9c8f  mov     edx, 6
0x1400b9c94  mov     r9d, ebx
0x1400b9c97  call    EfspTraceLogAssert
0x1400b9c9c  jmp     loc_1400BA613
0x1400b9ca1  mov     [rsp+0D8h+var_88], rdi
0x1400b9ca6  mov     esi, 1
0x1400b9cab  cmp     [r13+4], esi
0x1400b9caf  jnz     loc_1400B9EBF
0x1400b9cb5  mov     rcx, [rsp+0D8h+arg_50]
0x1400b9cbd  mov     r12, [rcx]
0x1400b9cc0  test    r12, r12
0x1400b9cc3  jz      loc_1400B9EB0
0x1400b9cc9  lea     r8, [rsp+0D8h+arg_0]
0x1400b9cd1  mov     rdx, [r12]
0x1400b9cd5  mov     rcx, rdi
0x1400b9cd8  call    EfsSameContext
0x1400b9cdd  mov     ebx, eax
0x1400b9cdf  mov     eax, [rdi]
0x1400b9ce1  sub     rax, 57h ; 'W'
0x1400b9ce5  lea     rcx, [rdi+50h]
0x1400b9ce9  jz      short loc_1400B9CF6
0x1400b9ceb  mov     byte ptr [rcx], 0
0x1400b9cee  add     rcx, rsi
0x1400b9cf1  sub     rax, rsi
0x1400b9cf4  jnz     short loc_1400B9CEB
0x1400b9cf6  mov     rdx, rdi; Entry
0x1400b9cf9  mov     rcx, [rdi+48h]; Lookaside
0x1400b9cfd  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400b9d04  nop     dword ptr [rax+rax+00h]
0x1400b9d09  xor     r9d, r9d
0x1400b9d0c  test    ebx, ebx
0x1400b9d0e  jns     short loc_1400B9D1B
0x1400b9d10  mov     r8d, 0D87h
0x1400b9d16  jmp     loc_1400B9C8F
0x1400b9d1b  cmp     byte ptr [rsp+0D8h+arg_0], r9b
0x1400b9d23  jnz     short loc_1400B9D42
0x1400b9d25  mov     eax, [r13+8]
0x1400b9d29  test    sil, al
0x1400b9d2c  jz      loc_1400BA0D8
0x1400b9d32  mov     ebx, 0C000000Dh
0x1400b9d37  mov     r8d, 0D9Ah
0x1400b9d3d  jmp     loc_1400B9C8F
0x1400b9d42  mov     rdi, r9
0x1400b9d45  mov     [rsp+0D8h+var_88], r9
0x1400b9d4a  mov     r15, [rsp+0D8h+arg_28]
0x1400b9d52  test    r15, r15
0x1400b9d55  jz      loc_1400B9EA6
0x1400b9d5b  mov     rax, [r15]
0x1400b9d5e  test    rax, rax
0x1400b9d61  jz      loc_1400B9EA6
0x1400b9d67  cmp     [r12+8], r9
0x1400b9d6c  jnz     loc_1400B9EA6
0x1400b9d72  lea     r8, [rax+10h]
0x1400b9d76  mov     [rsp+0D8h+var_58], r8
0x1400b9d7e  lea     rdx, [r8+18h]
0x1400b9d82  mov     rax, [r12]
0x1400b9d86  add     rax, 50h ; 'P'
0x1400b9d8a  mov     [rdx], rax
0x1400b9d8d  mov     rax, [r12]
0x1400b9d91  mov     ecx, [rax]
0x1400b9d93  mov     [rdx+8], ecx
0x1400b9d96  mov     rax, [r12]
0x1400b9d9a  mov     rcx, [rax+38h]
0x1400b9d9e  mov     [rdx+10h], rcx
0x1400b9da2  mov     rax, [r12]
0x1400b9da6  mov     rcx, [rax+40h]
0x1400b9daa  mov     [rdx+18h], rcx
0x1400b9dae  mov     dword ptr [rdx+20h], 200h
0x1400b9db5  mov     rax, [r12]
0x1400b9db9  mov     ecx, [rax+4]
0x1400b9dbc  mov     [rdx+24h], ecx
0x1400b9dbf  mov     rax, [r12]
0x1400b9dc3  mov     ecx, [rax+18h]
0x1400b9dc6  mov     [rdx+28h], ecx
0x1400b9dc9  mov     [r8+10h], rdx
0x1400b9dcd  mov     rax, [r15]
0x1400b9dd0  mov     [rsp+0D8h+arg_0], rax
0x1400b9dd8  mov     r14, [rax]
0x1400b9ddb  test    r14, r14
0x1400b9dde  jz      loc_1400B9E65
0x1400b9de4  mov     eax, [r14+4]
0x1400b9de8  cmp     eax, 660Eh
0x1400b9ded  jz      short loc_1400B9E04
0x1400b9def  cmp     eax, 6610h
0x1400b9df4  jz      short loc_1400B9E04
0x1400b9df6  cmp     eax, 20006610h
0x1400b9dfb  jz      short loc_1400B9E04
0x1400b9dfd  cmp     eax, 40006610h
0x1400b9e02  jnz     short loc_1400B9E27
0x1400b9e04  cmp     [r14+50h], esi
0x1400b9e08  jnz     short loc_1400B9E27
0x1400b9e0a  mov     rcx, [r14+58h]; hKey
0x1400b9e0e  lea     rax, [rcx-1]
0x1400b9e12  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400b9e16  ja      short loc_1400B9E27
0x1400b9e18  call    cs:__imp_BCryptDestroyKey
0x1400b9e1f  nop     dword ptr [rax+rax+00h]
0x1400b9e24  xor     r9d, r9d
0x1400b9e27  mov     eax, [r14]
0x1400b9e2a  sub     rax, 57h ; 'W'
0x1400b9e2e  lea     rcx, [r14+50h]
0x1400b9e32  jz      short loc_1400B9E3F
0x1400b9e34  mov     [rcx], r9b
0x1400b9e37  add     rcx, rsi
0x1400b9e3a  sub     rax, rsi
0x1400b9e3d  jnz     short loc_1400B9E34
0x1400b9e3f  mov     rdx, r14; Entry
0x1400b9e42  mov     rcx, [r14+48h]; Lookaside
0x1400b9e46  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400b9e4d  nop     dword ptr [rax+rax+00h]
0x1400b9e52  mov     rax, [rsp+0D8h+arg_0]
0x1400b9e5a  mov     [rax], rdi
0x1400b9e5d  mov     r8, [rsp+0D8h+var_58]
0x1400b9e65  mov     rcx, [r15]
0x1400b9e68  mov     rax, [r12]
0x1400b9e6c  mov     [rcx], rax
0x1400b9e6f  mov     rax, [r15]
0x1400b9e72  mov     [rax+8], r8
0x1400b9e76  mov     edx, 6D736645h; Tag
0x1400b9e7b  mov     r14, [rsp+0D8h+arg_50]
0x1400b9e83  mov     rcx, [r14]; P
0x1400b9e86  call    cs:__imp_ExFreePoolWithTag
0x1400b9e8d  nop     dword ptr [rax+rax+00h]
0x1400b9e92  mov     rax, [r15]
0x1400b9e95  mov     [r14], rax
0x1400b9e98  xor     r9d, r9d
0x1400b9e9b  mov     [r15], r9
0x1400b9e9e  mov     r14d, [rsp+0D8h+arg_8]
0x1400b9ea6  mov     r12d, [rsp+0D8h+arg_10]
0x1400b9eae  jmp     short loc_1400B9EC7
0x1400b9eb0  mov     r12d, [rsp+0D8h+arg_10]
0x1400b9eb8  jmp     short loc_1400B9EBF
0x1400b9eba  mov     esi, 1
0x1400b9ebf  mov     r15, [rsp+0D8h+arg_28]
0x1400b9ec7  mov     ecx, [r13+8]
0x1400b9ecb  mov     eax, ecx
0x1400b9ecd  and     eax, esi
0x1400b9ecf  jnz     short loc_1400B9EDA
0x1400b9ed1  test    cl, 8
0x1400b9ed4  jz      loc_1400BA2DE
0x1400b9eda  test    eax, eax
0x1400b9edc  jz      short loc_1400B9F3D
0x1400b9ede  mov     eax, [r13+0Ch]
0x1400b9ee2  test    al, 2
0x1400b9ee4  jnz     short loc_1400B9EFF
0x1400b9ee6  mov     edx, 6
0x1400b9eeb  mov     r9d, 0C0000001h
0x1400b9ef1  mov     r8d, 0DDCh
0x1400b9ef7  call    EfspTraceLogAssert
0x1400b9efc  xor     r9d, r9d
0x1400b9eff  test    sil, r14b
0x1400b9f02  jz      short loc_1400B9F3D
0x1400b9f04  test    rdi, rdi
0x1400b9f07  jz      short loc_1400B9F33
0x1400b9f09  mov     eax, [rdi]
0x1400b9f0b  sub     rax, 57h ; 'W'
0x1400b9f0f  lea     rcx, [rdi+50h]
0x1400b9f13  jz      short loc_1400B9F20
0x1400b9f15  mov     [rcx], r9b
0x1400b9f18  add     rcx, rsi
0x1400b9f1b  sub     rax, rsi
0x1400b9f1e  jnz     short loc_1400B9F15
0x1400b9f20  mov     rdx, rdi; Entry
0x1400b9f23  mov     rcx, [rdi+48h]; Lookaside
0x1400b9f27  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400b9f2e  nop     dword ptr [rax+rax+00h]
0x1400b9f33  mov     eax, 0C00000A2h
0x1400b9f38  jmp     loc_1400BA615
0x1400b9f3d  test    r12b, 2
0x1400b9f41  jz      loc_1400BA169
0x1400b9f47  lea     rax, [rsp+0D8h+var_98]
0x1400b9f4c  mov     [rsp+0D8h+var_B0], rax
0x1400b9f51  lea     rax, [rsp+0D8h+Size]
0x1400b9f56  mov     [rsp+0D8h+Src], rax
0x1400b9f5b  lea     r9, [rsp+0D8h+P]
0x1400b9f60  xor     r8d, r8d
0x1400b9f63  mov     r12, [rsp+0D8h+arg_20]
0x1400b9f6b  mov     rdx, r12
0x1400b9f6e  mov     r14, [rsp+0D8h+arg_18]
0x1400b9f76  mov     rcx, r14
0x1400b9f79  call    EfsReadEfsData
0x1400b9f7e  mov     ebx, eax
0x1400b9f80  mov     dword ptr [rsp+0D8h+Size+4], eax
0x1400b9f84  test    ebx, ebx
0x1400b9f86  js      loc_1400BA0FD
0x1400b9f8c  cmp     [rsp+0D8h+var_98], 200h
0x1400b9f94  jz      short loc_1400B9FA4
0x1400b9f96  cmp     [rsp+0D8h+var_98], 10000h
0x1400b9f9e  jnz     loc_1400BA0FD
0x1400b9fa4  cmp     [rsp+0D8h+var_98], 10000h
0x1400b9fac  jnz     loc_1400BA0DF
0x1400b9fb2  mov     dword ptr [rsp+0D8h+Src], 8; int
0x1400b9fba  lea     r9, [rsp+0D8h+var_78]
0x1400b9fbf  mov     r8d, 0Bh
0x1400b9fc5  mov     edx, dword ptr [rsp+0D8h+Size]; Size
0x1400b9fc9  mov     r14, [rsp+0D8h+P]
0x1400b9fce  mov     rcx, r14; Src
0x1400b9fd1  call    EfsGetEfsStreamInfo
0x1400b9fd6  mov     ebx, eax
0x1400b9fd8  test    eax, eax
0x1400b9fda  jns     short loc_1400BA02A
0x1400b9fdc  test    rdi, rdi
0x1400b9fdf  jz      short loc_1400BA00B
0x1400b9fe1  mov     eax, [rdi]
0x1400b9fe3  sub     rax, 57h ; 'W'
0x1400b9fe7  lea     rdx, [rdi+50h]
0x1400b9feb  jz      short loc_1400B9FF8
0x1400b9fed  mov     byte ptr [rdx], 0
0x1400b9ff0  add     rdx, rsi
0x1400b9ff3  sub     rax, rsi
0x1400b9ff6  jnz     short loc_1400B9FED
0x1400b9ff8  mov     rdx, rdi; Entry
0x1400b9ffb  mov     rcx, [rdi+48h]; Lookaside
0x1400b9fff  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400ba006  nop     dword ptr [rax+rax+00h]
0x1400ba00b  test    r14, r14
0x1400ba00e  jz      loc_1400BA613
0x1400ba014  xor     edx, edx; Tag
0x1400ba016  mov     rcx, r14; P
0x1400ba019  call    cs:__imp_ExFreePoolWithTag
0x1400ba020  nop     dword ptr [rax+rax+00h]
0x1400ba025  jmp     loc_1400BA613
0x1400ba02a  xor     edx, edx; Tag
0x1400ba02c  mov     rcx, r14; P
0x1400ba02f  call    cs:__imp_ExFreePoolWithTag
0x1400ba036  nop     dword ptr [rax+rax+00h]
0x1400ba03b  cmp     [rsp+0D8h+var_78], esi
0x1400ba03f  jnz     loc_1400BA171
0x1400ba045  test    [rsp+0D8h+var_74], 3
0x1400ba04a  jz      loc_1400BA171
0x1400ba050  mov     eax, [r13+8]
0x1400ba054  test    sil, al
0x1400ba057  jz      short loc_1400BA093
0x1400ba059  test    rdi, rdi
0x1400ba05c  jz      short loc_1400BA088
0x1400ba05e  mov     eax, [rdi]
0x1400ba060  sub     rax, 57h ; 'W'
0x1400ba064  lea     rcx, [rdi+50h]
0x1400ba068  jz      short loc_1400BA075
0x1400ba06a  mov     byte ptr [rcx], 0
0x1400ba06d  add     rcx, rsi
0x1400ba070  sub     rax, rsi
0x1400ba073  jnz     short loc_1400BA06A
0x1400ba075  mov     rdx, rdi; Entry
0x1400ba078  mov     rcx, [rdi+48h]; Lookaside
0x1400ba07c  call    cs:__imp_ExFreeToNPagedLookasideList
  ... truncated ...
```
