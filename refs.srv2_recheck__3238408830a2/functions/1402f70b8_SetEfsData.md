# SetEfsData

- ea: `0x1402f70b8`
- end: `0x1402f7a7c`
- name: `SetEfsData`
- size: `2500`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation`

## callers

- `0x1402ef3b0`

## callees

- `0x1400fe898`
- `0x14010a028`
- `0x14010a058`
- `0x1401f3f94`
- `0x1402eaca4`
- `0x1402eacc8`
- `0x1402eacec`
- `0x1402edaf8`
- `0x1402ee9d0`
- `0x1402eedf0`
- `0x1402ef200`
- `0x1402efce0`
- `0x1402f4cac`
- `0x1402f53e0`
- `0x1402f5c58`
- `0x1402f5e20`
- `0x1402f6d44`
- `0x1402f70b8`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f716f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f71f7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f734d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f7430`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f7509`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f7586`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f75d6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f762a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f7883`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f7912`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f7a5a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14034a35e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14034a3da`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f716f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f71f7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f734d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f7430`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f7509`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f7586`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f75d6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f762a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f7883`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f7912`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f7a5a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14034a35e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14034a3da`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f738e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f7523`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f7539`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f75f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f7642`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f738e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f7523`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f7539`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f75f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f7642`
- `cng!BCryptDestroyKey` at `0x1402f731f`
- `cng!BCryptDestroyKey` at `0x1402f7858`
- `cng!BCryptDestroyKey` at `0x1402f731f`
- `cng!BCryptDestroyKey` at `0x1402f7858`

## pseudocode

```c
__int64 __fastcall SetEfsData(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 *a6,
        char a7,
        __int64 a8,
        int *a9,
        _BYTE *a10,
        PVOID *a11)
{
  char v11; // r14
  _DWORD *v13; // rbx
  int EfsData; // esi
  __int64 KeyBlobBuffer; // rax
  __int64 v16; // rcx
  __int64 v17; // r8
  unsigned int v18; // ebx
  PVOID *v20; // r12
  _DWORD **v21; // r12
  __int64 v22; // rax
  _BYTE *v23; // rcx
  __int64 v24; // r15
  __int64 v25; // rax
  __int64 v26; // r8
  unsigned int *v27; // r14
  unsigned int v28; // eax
  char *v29; // rcx
  __int64 v30; // rax
  _BYTE *v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rax
  _BYTE *v34; // rcx
  int v35; // r14d
  PVOID v36; // r14
  __int64 v37; // rax
  _BYTE *v38; // rdx
  __int64 v39; // rax
  _BYTE *v40; // rcx
  __int64 v41; // rax
  _BYTE *v42; // rcx
  __int64 v43; // rax
  _BYTE *v44; // rcx
  int v45; // r9d
  __int64 v46; // rcx
  _BYTE *v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // r14
  int v50; // ecx
  int v51; // r8d
  __int64 v52; // rdx
  __int64 v53; // rcx
  int v54; // eax
  _QWORD *v55; // rax
  char *v56; // r13
  unsigned int *v57; // r14
  unsigned int v58; // eax
  char *v59; // rcx
  __int64 v60; // rax
  _BYTE *v61; // rcx
  __int64 v62; // rax
  _BYTE *v63; // rcx
  __int64 v64; // rax
  _DWORD *v65; // r14
  __int64 v66; // rcx
  _DWORD *v67; // rcx
  _DWORD *v68; // rcx
  __int64 v69; // rax
  _BYTE *v70; // rcx
  __int64 v71; // [rsp+0h] [rbp-E8h] BYREF
  __int64 v72; // [rsp+28h] [rbp-C0h]
  int v73; // [rsp+40h] [rbp-A8h] BYREF
  int v74; // [rsp+44h] [rbp-A4h] BYREF
  unsigned int v75; // [rsp+48h] [rbp-A0h] BYREF
  _DWORD *v76; // [rsp+50h] [rbp-98h]
  unsigned int Size; // [rsp+58h] [rbp-90h] BYREF
  unsigned int Size_4; // [rsp+5Ch] [rbp-8Ch]
  int v79; // [rsp+60h] [rbp-88h]
  __int64 v80; // [rsp+68h] [rbp-80h]
  PVOID P; // [rsp+70h] [rbp-78h] BYREF
  __int64 v82; // [rsp+78h] [rbp-70h] BYREF
  void *v83; // [rsp+80h] [rbp-68h] BYREF
  __int64 v84; // [rsp+88h] [rbp-60h]
  _DWORD *v85; // [rsp+90h] [rbp-58h]
  __int64 v86; // [rsp+98h] [rbp-50h]
  __int64 *v87; // [rsp+A0h] [rbp-48h]
  unsigned int **v88; // [rsp+F0h] [rbp+8h] BYREF
  int v89; // [rsp+F8h] [rbp+10h]
  int v90; // [rsp+100h] [rbp+18h]
  __int64 v91; // [rsp+108h] [rbp+20h]

  v91 = a4;
  v90 = a3;
  v89 = a2;
  v87 = &v71;
  v11 = a2;
  LOBYTE(v88) = 0;
  v13 = 0;
  v76 = 0;
  EfsData = 0;
  v82 = 0;
  v83 = 0;
  v75 = 0;
  P = 0;
  Size = 0;
  v73 = 0;
  v80 = 0;
  v79 = 0;
  v74 = *a9;
  if ( (*(_DWORD *)(a1 + 8) & 2) == 0 )
    goto LABEL_32;
  KeyBlobBuffer = GetKeyBlobBufferEx(
                    *(unsigned int *)(*(_QWORD *)(a1 + 24) + 4LL),
                    *(unsigned int *)(*(_QWORD *)(a1 + 24) + 8LL));
  v13 = (_DWORD *)KeyBlobBuffer;
  if ( !KeyBlobBuffer )
    return 3221225626LL;
  if ( !(unsigned __int8)SetKeyTable(KeyBlobBuffer, &v74, *(_QWORD *)(a1 + 24)) )
  {
    ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v13 + 9), v13);
    v17 = 3449;
LABEL_5:
    v18 = -1073741790;
LABEL_6:
    EfspTraceLogAssert(v16, 6, v17, v18);
    return v18;
  }
  v76 = v13;
  v20 = a11;
  if ( *(_DWORD *)(a1 + 4) != 1 )
  {
    v24 = (__int64)a6;
    goto LABEL_34;
  }
  v21 = (_DWORD **)*a11;
  if ( !*a11 )
  {
LABEL_32:
    v24 = (__int64)a6;
LABEL_33:
    v20 = a11;
    goto LABEL_34;
  }
  EfsData = EfsSameContext(v13, *v21, &v88, 0);
  v22 = (unsigned int)*v13 - 87LL;
  v23 = v13 + 20;
  if ( *v13 != 87 )
  {
    do
    {
      *v23++ = 0;
      --v22;
    }
    while ( v22 );
  }
  ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v13 + 9), v13);
  if ( EfsData < 0 )
  {
    EfspTraceLogAssert(v16, 6, 3463, (unsigned int)EfsData);
    return (unsigned int)EfsData;
  }
  if ( !(_BYTE)v88 )
  {
    if ( (*(_DWORD *)(a1 + 8) & 1) != 0 )
    {
      v18 = -1073741811;
      v17 = 3482;
      goto LABEL_6;
    }
    return 0;
  }
  v13 = 0;
  v76 = 0;
  v24 = (__int64)a6;
  if ( !a6 )
    goto LABEL_33;
  v25 = *a6;
  if ( !*a6 || v21[1] )
    goto LABEL_33;
  v26 = v25 + 16;
  v84 = v25 + 16;
  *(_QWORD *)(v25 + 40) = *v21 + 20;
  *(_DWORD *)(v25 + 48) = **v21;
  *(_QWORD *)(v25 + 56) = *((_QWORD *)*v21 + 7);
  *(_QWORD *)(v25 + 64) = *((_QWORD *)*v21 + 8);
  *(_DWORD *)(v25 + 72) = 512;
  *(_DWORD *)(v25 + 76) = (*v21)[1];
  *(_DWORD *)(v25 + 80) = (*v21)[6];
  *(_QWORD *)(v25 + 32) = v25 + 40;
  v88 = *(unsigned int ***)v24;
  v27 = *v88;
  if ( *v88 )
  {
    v28 = v27[1];
    if ( (v28 == 26126 || v28 == 26128 || v28 == 536897040 || v28 == 1073767952) && v27[20] == 1 )
    {
      v29 = (char *)*((_QWORD *)v27 + 11);
      if ( (unsigned __int64)(v29 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        BCryptDestroyKey(v29);
    }
    v30 = *v27 - 87LL;
    v31 = v27 + 20;
    if ( *v27 != 87 )
    {
      do
      {
        *v31++ = 0;
        --v30;
      }
      while ( v30 );
    }
    ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v27 + 9), v27);
    *v88 = 0;
    v26 = v84;
  }
  **(_QWORD **)v24 = *v21;
  *(_QWORD *)(*(_QWORD *)v24 + 8LL) = v26;
  v20 = a11;
  ExFreePoolWithTag(*a11, 0x6D736645u);
  *v20 = *(PVOID *)v24;
  *(_QWORD *)v24 = 0;
  v11 = v89;
LABEL_34:
  v32 = *(unsigned int *)(a1 + 8);
  if ( (*(_DWORD *)(a1 + 8) & 1) == 0 && (v32 & 8) == 0 )
    goto LABEL_99;
  if ( (*(_DWORD *)(a1 + 8) & 1) != 0 )
  {
    if ( (*(_DWORD *)(a1 + 12) & 2) == 0 )
      EfspTraceLogAssert(v32, 6, 3548, 3221225473LL);
    if ( (v11 & 1) != 0 )
    {
      if ( v13 )
      {
        v33 = (unsigned int)*v13 - 87LL;
        v34 = v13 + 20;
        if ( *v13 != 87 )
        {
          do
          {
            *v34++ = 0;
            --v33;
          }
          while ( v33 );
        }
        ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v13 + 9), v13);
      }
      return 3221225634LL;
    }
  }
  if ( (v90 & 2) == 0 )
    goto LABEL_84;
  v35 = v91;
  EfsData = EfsReadEfsData(v91, a5, 0, (unsigned int)&P, (__int64)&Size, (__int64)&v73);
  Size_4 = EfsData;
  if ( EfsData < 0 || v73 != 512 && v73 != 0x10000 )
  {
    if ( v13 )
    {
      v43 = (unsigned int)*v13 - 87LL;
      v44 = v13 + 20;
      if ( *v13 != 87 )
      {
        do
        {
          *v44++ = 0;
          --v43;
        }
        while ( v43 );
      }
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v13 + 9), v13);
    }
    if ( P )
      ExFreePoolWithTag(P, 0);
    if ( v73 == 2048 )
    {
      return (unsigned int)-1073741670;
    }
    else if ( EfsData >= 0 )
    {
      return (unsigned int)-1073741808;
    }
    return (unsigned int)EfsData;
  }
  if ( v73 == 0x10000 )
  {
    v36 = P;
    EfsData = EfsGetEfsStreamInfo(P, Size, 8);
    if ( EfsData < 0 )
    {
      if ( v13 )
      {
        v37 = (unsigned int)*v13 - 87LL;
        v38 = v13 + 20;
        if ( *v13 != 87 )
        {
          do
          {
            *v38++ = 0;
            --v37;
          }
          while ( v37 );
        }
        ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v13 + 9), v13);
      }
      if ( v36 )
        ExFreePoolWithTag(v36, 0);
      return (unsigned int)EfsData;
    }
    ExFreePoolWithTag(v36, 0);
    if ( (_DWORD)v80 == 1 && (v80 & 0x300000000LL) != 0 )
    {
      if ( (*(_DWORD *)(a1 + 8) & 1) != 0 )
      {
        if ( v13 )
        {
          v39 = (unsigned int)*v13 - 87LL;
          v40 = v13 + 20;
          if ( *v13 != 87 )
          {
            do
            {
              *v40++ = 0;
              --v39;
            }
            while ( v39 );
          }
          ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v13 + 9), v13);
        }
        v17 = 3667;
        goto LABEL_5;
      }
      if ( (v80 & 0x200000000LL) != 0 )
      {
        *a10 = 1;
        if ( v13 )
        {
          v41 = (unsigned int)*v13 - 87LL;
          v42 = v13 + 20;
          if ( *v13 != 87 )
          {
            do
            {
              *v42++ = 0;
              --v41;
            }
            while ( v41 );
          }
          ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v13 + 9), v13);
        }
        return 0;
      }
    }
LABEL_84:
    v35 = v91;
    goto LABEL_85;
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
LABEL_85:
  if ( (*(_DWORD *)(a1 + 8) & 1) == 0 )
    goto LABEL_99;
  EfsData = EfspGetEfsStreamForWrite(*(_QWORD *)(a1 + 16), **(unsigned int **)(a1 + 16), &v83, &v75);
  if ( EfsData < 0 )
  {
    if ( !v13 )
      return (unsigned int)EfsData;
    v46 = (unsigned int)*v13 - 87LL;
    v47 = v13 + 20;
    if ( *v13 != 87 )
    {
      do
      {
        *v47++ = 0;
        --v46;
      }
      while ( v46 );
    }
LABEL_136:
    ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v13 + 9), v13);
    return (unsigned int)EfsData;
  }
  EfsData = NtOfsCreateAttributeEx(a5, v35, (unsigned int)&DestinationString, v45, 1, v72, (__int64)&v82);
  Size_4 = EfsData;
  if ( EfsData == -1073741808 )
    EfspTraceLogAssert(v48, 6, 3722, 3221225488LL);
  if ( EfsData >= 0 )
  {
    v49 = v82;
    NtOfsSetLength(v48, v82, v75);
    NtOfsPutData(v50, v49, v51, v75, v83);
    NtOfsMarkFileModified(a5, v91, v49);
    if ( *v20 && (*(_DWORD *)(a1 + 8) & 2) == 0 )
    {
      LOBYTE(v52) = a7;
      EfsCleanup(v20, v52, a8);
    }
    if ( v49 )
      NtOfsCloseAttribute(v53, v49);
LABEL_99:
    if ( !v13 || (*(_DWORD *)(a1 + 8) & 2) == 0 )
      return (unsigned int)EfsData;
    v54 = *(_DWORD *)(a1 + 4);
    if ( v54 != 1 || *v20 )
    {
      if ( v54 != 4 )
        return (unsigned int)EfsData;
      v65 = *v20;
      if ( *v20 )
      {
        v67 = *(_DWORD **)v65;
        if ( *v13 > **(_DWORD **)v65 )
        {
          EfsData = -1073740974;
          EfspTraceLogAssert(v67, 6, 3954, 3221226322LL);
        }
        else
        {
          EfsData = EfspCopyEfsKeyBlob(v67, v13);
          if ( EfsData >= 0 )
          {
            v65[4] = 87119;
            *((_QWORD *)v65 + 3) = 0;
            v68 = *(_DWORD **)v65;
            *((_QWORD *)v65 + 5) = *(_QWORD *)v65 + 80LL;
            v65[12] = *v68;
            *((_QWORD *)v65 + 7) = *((_QWORD *)v68 + 7);
            *((_QWORD *)v65 + 8) = *((_QWORD *)v68 + 8);
            v65[18] = 512;
            v65[19] = v68[1];
            v65[20] = v68[6];
            *((_QWORD *)v65 + 4) = v65 + 10;
            *((_QWORD *)v65 + 1) = v65 + 4;
            *a9 = v74;
          }
        }
        v69 = (unsigned int)*v13 - 87LL;
        v70 = v13 + 20;
        if ( *v13 != 87 )
        {
          do
          {
            *v70++ = 0;
            --v69;
          }
          while ( v69 );
        }
        goto LABEL_136;
      }
      v66 = AllocateAndSetContextDataBlock(v13);
      if ( v66 )
      {
        *a9 = v74;
        *v20 = (PVOID)v66;
        return (unsigned int)EfsData;
      }
    }
    else
    {
      if ( v24 )
      {
        v55 = *(_QWORD **)v24;
        if ( *(_QWORD *)v24 )
        {
          v56 = (char *)(v55 + 2);
          v55[5] = v13 + 20;
          *((_DWORD *)v55 + 12) = *v13;
          v55[7] = *((_QWORD *)v13 + 7);
          v55[8] = *((_QWORD *)v13 + 8);
          *((_DWORD *)v55 + 18) = 512;
          *((_DWORD *)v55 + 19) = v13[1];
          *((_DWORD *)v55 + 20) = v13[6];
          v55[4] = v55 + 5;
          v88 = *(unsigned int ***)v24;
          v57 = *v88;
          if ( *v88 )
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
            *v88 = 0;
          }
          **(_QWORD **)v24 = v13;
          *(_QWORD *)(*(_QWORD *)v24 + 8LL) = v56;
          *a9 = v74;
          *v20 = *(PVOID *)v24;
          *(_QWORD *)v24 = 0;
          return (unsigned int)EfsData;
        }
      }
      v64 = AllocateAndSetContextDataBlock(v13);
      if ( v64 )
      {
        *a9 = v74;
        *v20 = (PVOID)v64;
        return (unsigned int)EfsData;
      }
    }
    return 3221225626LL;
  }
  if ( v13 )
  {
    v62 = (unsigned int)*v13 - 87LL;
    v86 = v62;
    v63 = v13 + 20;
    v85 = v13 + 20;
    while ( v62 )
    {
      *v63++ = 0;
      v85 = v63;
      v86 = --v62;
    }
    ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v13 + 9), v13);
    v76 = 0;
  }
  local_unwind_0(v87, &loc_1402F793C);
  return Size_4;
}

```

## disassembly

```asm
0x1402f70b8  mov     rax, rsp
0x1402f70bb  mov     [rax+20h], r9
0x1402f70bf  mov     [rax+18h], r8d
0x1402f70c3  mov     [rax+10h], edx
0x1402f70c6  push    rbx
0x1402f70c7  push    rsi
0x1402f70c8  push    rdi
0x1402f70c9  push    r12
0x1402f70cb  push    r13
0x1402f70cd  push    r14
0x1402f70cf  push    r15
0x1402f70d1  sub     rsp, 0B0h
0x1402f70d8  mov     [rsp+0E8h+var_48], rsp
0x1402f70e0  mov     r14d, edx
0x1402f70e3  mov     r13, rcx
0x1402f70e6  xor     r9d, r9d
0x1402f70e9  mov     [rax+8], r9b
0x1402f70ed  mov     ebx, r9d
0x1402f70f0  mov     [rsp+0E8h+var_98], rbx
0x1402f70f5  mov     esi, r9d
0x1402f70f8  mov     [rax-70h], r9
0x1402f70fc  mov     [rax-68h], r9
0x1402f7100  mov     [rsp+0E8h+var_A0], r9d
0x1402f7105  mov     [rax-78h], r9
0x1402f7109  mov     dword ptr [rsp+0E8h+Size], r9d
0x1402f710e  mov     [rsp+0E8h+var_A8], r9d
0x1402f7113  mov     [rax-80h], r9
0x1402f7117  mov     [rsp+0E8h+var_88], r9d
0x1402f711c  mov     rax, [rsp+0E8h+arg_40]
0x1402f7124  mov     eax, [rax]
0x1402f7126  mov     [rsp+0E8h+var_A4], eax
0x1402f712a  mov     eax, [rcx+8]
0x1402f712d  test    al, 2
0x1402f712f  jz      loc_1402F73BB
0x1402f7135  mov     rcx, [rcx+18h]
0x1402f7139  mov     edx, [rcx+8]
0x1402f713c  mov     ecx, [rcx+4]
0x1402f713f  call    GetKeyBlobBufferEx
0x1402f7144  mov     rbx, rax
0x1402f7147  test    rax, rax
0x1402f714a  jz      loc_1402F798B
0x1402f7150  mov     r8, [r13+18h]
0x1402f7154  lea     rdx, [rsp+0E8h+var_A4]
0x1402f7159  mov     rcx, rax
0x1402f715c  call    SetKeyTable
0x1402f7161  xor     r9d, r9d
0x1402f7164  test    al, al
0x1402f7166  jnz     short loc_1402F719A
0x1402f7168  mov     rdx, rbx; Entry
0x1402f716b  mov     rcx, [rbx+48h]; Lookaside
0x1402f716f  call    cs:__imp_ExFreeToNPagedLookasideList
0x1402f7176  nop     dword ptr [rax+rax+00h]
0x1402f717b  mov     r8d, 0D79h
0x1402f7181  mov     ebx, 0C0000022h
0x1402f7186  mov     r9d, ebx
0x1402f7189  mov     edx, 6
0x1402f718e  call    EfspTraceLogAssert
0x1402f7193  mov     eax, ebx
0x1402f7195  jmp     loc_1402F7A68
0x1402f719a  mov     [rsp+0E8h+var_98], rbx
0x1402f719f  mov     edi, 1
0x1402f71a4  mov     r12, [rsp+0E8h+arg_50]
0x1402f71ac  cmp     [r13+4], edi
0x1402f71b0  jnz     loc_1402F73B1
0x1402f71b6  mov     r12, [r12]
0x1402f71ba  test    r12, r12
0x1402f71bd  jz      loc_1402F73C0
0x1402f71c3  lea     r8, [rsp+0E8h+arg_0]
0x1402f71cb  mov     rdx, [r12]
0x1402f71cf  mov     rcx, rbx
0x1402f71d2  call    EfsSameContext
0x1402f71d7  mov     esi, eax
0x1402f71d9  mov     eax, [rbx]
0x1402f71db  sub     rax, 57h ; 'W'
0x1402f71df  lea     rcx, [rbx+50h]
0x1402f71e3  jz      short loc_1402F71F0
0x1402f71e5  mov     byte ptr [rcx], 0
0x1402f71e8  add     rcx, rdi
0x1402f71eb  sub     rax, rdi
0x1402f71ee  jnz     short loc_1402F71E5
0x1402f71f0  mov     rdx, rbx; Entry
0x1402f71f3  mov     rcx, [rbx+48h]; Lookaside
0x1402f71f7  call    cs:__imp_ExFreeToNPagedLookasideList
0x1402f71fe  nop     dword ptr [rax+rax+00h]
0x1402f7203  xor     r9d, r9d
0x1402f7206  test    esi, esi
0x1402f7208  jns     short loc_1402F7222
0x1402f720a  mov     r9d, esi
0x1402f720d  mov     edx, 6
0x1402f7212  mov     r8d, 0D87h
0x1402f7218  call    EfspTraceLogAssert
0x1402f721d  jmp     loc_1402F7A66
0x1402f7222  cmp     byte ptr [rsp+0E8h+arg_0], r9b
0x1402f722a  jnz     short loc_1402F7249
0x1402f722c  mov     eax, [r13+8]
0x1402f7230  test    dil, al
0x1402f7233  jz      loc_1402F75E2
0x1402f7239  mov     ebx, 0C000000Dh
0x1402f723e  mov     r8d, 0D9Ah
0x1402f7244  jmp     loc_1402F7186
0x1402f7249  mov     rbx, r9
0x1402f724c  mov     [rsp+0E8h+var_98], rbx
0x1402f7251  mov     r15, [rsp+0E8h+arg_28]
0x1402f7259  test    r15, r15
0x1402f725c  jz      loc_1402F73C8
0x1402f7262  mov     rax, [r15]
0x1402f7265  test    rax, rax
0x1402f7268  jz      loc_1402F73C8
0x1402f726e  cmp     [r12+8], r9
0x1402f7273  jnz     loc_1402F73C8
0x1402f7279  lea     r8, [rax+10h]
0x1402f727d  mov     [rsp+0E8h+var_60], r8
0x1402f7285  lea     rdx, [r8+18h]
0x1402f7289  mov     rax, [r12]
0x1402f728d  add     rax, 50h ; 'P'
0x1402f7291  mov     [rdx], rax
0x1402f7294  mov     rax, [r12]
0x1402f7298  mov     ecx, [rax]
0x1402f729a  mov     [rdx+8], ecx
0x1402f729d  mov     rax, [r12]
0x1402f72a1  mov     rcx, [rax+38h]
0x1402f72a5  mov     [rdx+10h], rcx
0x1402f72a9  mov     rax, [r12]
0x1402f72ad  mov     rcx, [rax+40h]
0x1402f72b1  mov     [rdx+18h], rcx
0x1402f72b5  mov     dword ptr [rdx+20h], 200h
0x1402f72bc  mov     rax, [r12]
0x1402f72c0  mov     ecx, [rax+4]
0x1402f72c3  mov     [rdx+24h], ecx
0x1402f72c6  mov     rax, [r12]
0x1402f72ca  mov     ecx, [rax+18h]
0x1402f72cd  mov     [rdx+28h], ecx
0x1402f72d0  mov     [r8+10h], rdx
0x1402f72d4  mov     rax, [r15]
0x1402f72d7  mov     [rsp+0E8h+arg_0], rax
0x1402f72df  mov     r14, [rax]
0x1402f72e2  test    r14, r14
0x1402f72e5  jz      loc_1402F736C
0x1402f72eb  mov     eax, [r14+4]
0x1402f72ef  cmp     eax, 660Eh
0x1402f72f4  jz      short loc_1402F730B
0x1402f72f6  cmp     eax, 6610h
0x1402f72fb  jz      short loc_1402F730B
0x1402f72fd  cmp     eax, 20006610h
0x1402f7302  jz      short loc_1402F730B
0x1402f7304  cmp     eax, 40006610h
0x1402f7309  jnz     short loc_1402F732E
0x1402f730b  cmp     [r14+50h], edi
0x1402f730f  jnz     short loc_1402F732E
0x1402f7311  mov     rcx, [r14+58h]; hKey
0x1402f7315  lea     rax, [rcx-1]
0x1402f7319  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1402f731d  ja      short loc_1402F732E
0x1402f731f  call    cs:__imp_BCryptDestroyKey
0x1402f7326  nop     dword ptr [rax+rax+00h]
0x1402f732b  xor     r9d, r9d
0x1402f732e  mov     eax, [r14]
0x1402f7331  sub     rax, 57h ; 'W'
0x1402f7335  lea     rcx, [r14+50h]
0x1402f7339  jz      short loc_1402F7346
0x1402f733b  mov     [rcx], r9b
0x1402f733e  add     rcx, rdi
0x1402f7341  sub     rax, rdi
0x1402f7344  jnz     short loc_1402F733B
0x1402f7346  mov     rdx, r14; Entry
0x1402f7349  mov     rcx, [r14+48h]; Lookaside
0x1402f734d  call    cs:__imp_ExFreeToNPagedLookasideList
0x1402f7354  nop     dword ptr [rax+rax+00h]
0x1402f7359  mov     rax, [rsp+0E8h+arg_0]
0x1402f7361  mov     [rax], rbx
0x1402f7364  mov     r8, [rsp+0E8h+var_60]
0x1402f736c  mov     rcx, [r15]
0x1402f736f  mov     rax, [r12]
0x1402f7373  mov     [rcx], rax
0x1402f7376  mov     rax, [r15]
0x1402f7379  mov     [rax+8], r8
0x1402f737d  mov     edx, 6D736645h; Tag
0x1402f7382  mov     r12, [rsp+0E8h+arg_50]
0x1402f738a  mov     rcx, [r12]; P
0x1402f738e  call    cs:__imp_ExFreePoolWithTag
0x1402f7395  nop     dword ptr [rax+rax+00h]
0x1402f739a  mov     rax, [r15]
0x1402f739d  mov     [r12], rax
0x1402f73a1  xor     r9d, r9d
0x1402f73a4  mov     [r15], r9
0x1402f73a7  mov     r14d, [rsp+0E8h+arg_8]
0x1402f73af  jmp     short loc_1402F73D0
0x1402f73b1  mov     r15, [rsp+0E8h+arg_28]
0x1402f73b9  jmp     short loc_1402F73D0
0x1402f73bb  mov     edi, 1
0x1402f73c0  mov     r15, [rsp+0E8h+arg_28]
0x1402f73c8  mov     r12, [rsp+0E8h+arg_50]
0x1402f73d0  mov     ecx, [r13+8]
0x1402f73d4  mov     eax, ecx
0x1402f73d6  and     eax, edi
0x1402f73d8  jnz     short loc_1402F73E3
0x1402f73da  test    cl, 8
0x1402f73dd  jz      loc_1402F7795
0x1402f73e3  test    eax, eax
0x1402f73e5  jz      short loc_1402F7446
0x1402f73e7  mov     eax, [r13+0Ch]
0x1402f73eb  test    al, 2
0x1402f73ed  jnz     short loc_1402F7408
0x1402f73ef  mov     edx, 6
0x1402f73f4  mov     r9d, 0C0000001h
0x1402f73fa  mov     r8d, 0DDCh
0x1402f7400  call    EfspTraceLogAssert
0x1402f7405  xor     r9d, r9d
0x1402f7408  test    dil, r14b
0x1402f740b  jz      short loc_1402F7446
0x1402f740d  test    rbx, rbx
0x1402f7410  jz      short loc_1402F743C
0x1402f7412  mov     eax, [rbx]
0x1402f7414  sub     rax, 57h ; 'W'
0x1402f7418  lea     rcx, [rbx+50h]
0x1402f741c  jz      short loc_1402F7429
0x1402f741e  mov     [rcx], r9b
0x1402f7421  add     rcx, rdi
0x1402f7424  sub     rax, rdi
0x1402f7427  jnz     short loc_1402F741E
0x1402f7429  mov     rdx, rbx; Entry
0x1402f742c  mov     rcx, [rbx+48h]; Lookaside
0x1402f7430  call    cs:__imp_ExFreeToNPagedLookasideList
0x1402f7437  nop     dword ptr [rax+rax+00h]
0x1402f743c  mov     eax, 0C00000A2h
0x1402f7441  jmp     loc_1402F7A68
0x1402f7446  test    byte ptr [rsp+0E8h+arg_10], 2
0x1402f744e  jz      loc_1402F7673
0x1402f7454  lea     rax, [rsp+0E8h+var_A8]
0x1402f7459  mov     [rsp+0E8h+var_C0], rax
0x1402f745e  lea     rax, [rsp+0E8h+Size]
0x1402f7463  mov     qword ptr [rsp+0E8h+var_C8], rax
0x1402f7468  lea     r9, [rsp+0E8h+P]
0x1402f746d  xor     r8d, r8d
0x1402f7470  mov     rdx, [rsp+0E8h+arg_20]
0x1402f7478  mov     r14, [rsp+0E8h+arg_18]
0x1402f7480  mov     rcx, r14
0x1402f7483  call    EfsReadEfsData
0x1402f7488  mov     esi, eax
0x1402f748a  mov     dword ptr [rsp+0E8h+Size+4], eax
0x1402f748e  test    esi, esi
0x1402f7490  js      loc_1402F7607
0x1402f7496  cmp     [rsp+0E8h+var_A8], 200h
0x1402f749e  jz      short loc_1402F74AE
0x1402f74a0  cmp     [rsp+0E8h+var_A8], 10000h
0x1402f74a8  jnz     loc_1402F7607
0x1402f74ae  cmp     [rsp+0E8h+var_A8], 10000h
0x1402f74b6  jnz     loc_1402F75E9
0x1402f74bc  mov     [rsp+0E8h+var_C8], 8; int
0x1402f74c4  lea     r9, [rsp+0E8h+var_80]
0x1402f74c9  mov     r8d, 0Bh
0x1402f74cf  mov     edx, dword ptr [rsp+0E8h+Size]; Size
0x1402f74d3  mov     r14, [rsp+0E8h+P]
0x1402f74d8  mov     rcx, r14; Src
0x1402f74db  call    EfsGetEfsStreamInfo
0x1402f74e0  mov     esi, eax
0x1402f74e2  test    eax, eax
0x1402f74e4  jns     short loc_1402F7534
0x1402f74e6  test    rbx, rbx
0x1402f74e9  jz      short loc_1402F7515
0x1402f74eb  mov     eax, [rbx]
0x1402f74ed  sub     rax, 57h ; 'W'
0x1402f74f1  lea     rdx, [rbx+50h]
0x1402f74f5  jz      short loc_1402F7502
0x1402f74f7  mov     byte ptr [rdx], 0
0x1402f74fa  add     rdx, rdi
0x1402f74fd  sub     rax, rdi
0x1402f7500  jnz     short loc_1402F74F7
0x1402f7502  mov     rdx, rbx; Entry
0x1402f7505  mov     rcx, [rbx+48h]; Lookaside
0x1402f7509  call    cs:__imp_ExFreeToNPagedLookasideList
0x1402f7510  nop     dword ptr [rax+rax+00h]
0x1402f7515  test    r14, r14
0x1402f7518  jz      loc_1402F7A66
0x1402f751e  xor     edx, edx; Tag
0x1402f7520  mov     rcx, r14; P
0x1402f7523  call    cs:__imp_ExFreePoolWithTag
0x1402f752a  nop     dword ptr [rax+rax+00h]
0x1402f752f  jmp     loc_1402F7A66
0x1402f7534  xor     edx, edx; Tag
0x1402f7536  mov     rcx, r14; P
0x1402f7539  call    cs:__imp_ExFreePoolWithTag
0x1402f7540  nop     dword ptr [rax+rax+00h]
0x1402f7545  cmp     [rsp+0E8h+var_80], edi
0x1402f7549  jnz     loc_1402F7673
0x1402f754f  test    [rsp+0E8h+var_7C], 3
0x1402f7554  jz      loc_1402F7673
0x1402f755a  mov     eax, [r13+8]
0x1402f755e  test    dil, al
0x1402f7561  jz      short loc_1402F759D
0x1402f7563  test    rbx, rbx
0x1402f7566  jz      short loc_1402F7592
0x1402f7568  mov     eax, [rbx]
0x1402f756a  sub     rax, 57h ; 'W'
0x1402f756e  lea     rcx, [rbx+50h]
0x1402f7572  jz      short loc_1402F757F
0x1402f7574  mov     byte ptr [rcx], 0
0x1402f7577  add     rcx, rdi
0x1402f757a  sub     rax, rdi
0x1402f757d  jnz     short loc_1402F7574
  ... truncated ...
```
