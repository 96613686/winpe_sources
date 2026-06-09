# SetEfsData

- ea: `0x1402f2f38`
- end: `0x1402f38fc`
- name: `SetEfsData`
- size: `2500`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation`

## callers

- `0x1402eb230`

## callees

- `0x1400f99d8`
- `0x1401051c8`
- `0x1401051f8`
- `0x1401e9cc4`
- `0x1402e6ab4`
- `0x1402e6ad8`
- `0x1402e6afc`
- `0x1402e9978`
- `0x1402ea850`
- `0x1402eac70`
- `0x1402eb080`
- `0x1402ebb60`
- `0x1402f0b2c`
- `0x1402f1260`
- `0x1402f1ad8`
- `0x1402f1ca0`
- `0x1402f2bc4`
- `0x1402f2f38`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f2fef`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f3077`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f31cd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f32b0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f3389`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f3406`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f3456`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f34aa`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f3703`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f3792`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f38da`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140347454`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1403474d0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f2fef`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f3077`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f31cd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f32b0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f3389`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f3406`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f3456`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f34aa`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f3703`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f3792`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402f38da`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140347454`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1403474d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f320e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f33a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f33b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f3479`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f34c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f320e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f33a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f33b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f3479`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f34c2`
- `cng!BCryptDestroyKey` at `0x1402f319f`
- `cng!BCryptDestroyKey` at `0x1402f36d8`
- `cng!BCryptDestroyKey` at `0x1402f319f`
- `cng!BCryptDestroyKey` at `0x1402f36d8`

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
  local_unwind_0(v87, &loc_1402F37BC);
  return Size_4;
}

```

## disassembly

```asm
0x1402f2f38  mov     rax, rsp
0x1402f2f3b  mov     [rax+20h], r9
0x1402f2f3f  mov     [rax+18h], r8d
0x1402f2f43  mov     [rax+10h], edx
0x1402f2f46  push    rbx
0x1402f2f47  push    rsi
0x1402f2f48  push    rdi
0x1402f2f49  push    r12
0x1402f2f4b  push    r13
0x1402f2f4d  push    r14
0x1402f2f4f  push    r15
0x1402f2f51  sub     rsp, 0B0h
0x1402f2f58  mov     [rsp+0E8h+var_48], rsp
0x1402f2f60  mov     r14d, edx
0x1402f2f63  mov     r13, rcx
0x1402f2f66  xor     r9d, r9d
0x1402f2f69  mov     [rax+8], r9b
0x1402f2f6d  mov     ebx, r9d
0x1402f2f70  mov     [rsp+0E8h+var_98], rbx
0x1402f2f75  mov     esi, r9d
0x1402f2f78  mov     [rax-70h], r9
0x1402f2f7c  mov     [rax-68h], r9
0x1402f2f80  mov     [rsp+0E8h+var_A0], r9d
0x1402f2f85  mov     [rax-78h], r9
0x1402f2f89  mov     dword ptr [rsp+0E8h+Size], r9d
0x1402f2f8e  mov     [rsp+0E8h+var_A8], r9d
0x1402f2f93  mov     [rax-80h], r9
0x1402f2f97  mov     [rsp+0E8h+var_88], r9d
0x1402f2f9c  mov     rax, [rsp+0E8h+arg_40]
0x1402f2fa4  mov     eax, [rax]
0x1402f2fa6  mov     [rsp+0E8h+var_A4], eax
0x1402f2faa  mov     eax, [rcx+8]
0x1402f2fad  test    al, 2
0x1402f2faf  jz      loc_1402F323B
0x1402f2fb5  mov     rcx, [rcx+18h]
0x1402f2fb9  mov     edx, [rcx+8]
0x1402f2fbc  mov     ecx, [rcx+4]
0x1402f2fbf  call    GetKeyBlobBufferEx
0x1402f2fc4  mov     rbx, rax
0x1402f2fc7  test    rax, rax
0x1402f2fca  jz      loc_1402F380B
0x1402f2fd0  mov     r8, [r13+18h]
0x1402f2fd4  lea     rdx, [rsp+0E8h+var_A4]
0x1402f2fd9  mov     rcx, rax
0x1402f2fdc  call    SetKeyTable
0x1402f2fe1  xor     r9d, r9d
0x1402f2fe4  test    al, al
0x1402f2fe6  jnz     short loc_1402F301A
0x1402f2fe8  mov     rdx, rbx; Entry
0x1402f2feb  mov     rcx, [rbx+48h]; Lookaside
0x1402f2fef  call    cs:__imp_ExFreeToNPagedLookasideList
0x1402f2ff6  nop     dword ptr [rax+rax+00h]
0x1402f2ffb  mov     r8d, 0D79h
0x1402f3001  mov     ebx, 0C0000022h
0x1402f3006  mov     r9d, ebx
0x1402f3009  mov     edx, 6
0x1402f300e  call    EfspTraceLogAssert
0x1402f3013  mov     eax, ebx
0x1402f3015  jmp     loc_1402F38E8
0x1402f301a  mov     [rsp+0E8h+var_98], rbx
0x1402f301f  mov     edi, 1
0x1402f3024  mov     r12, [rsp+0E8h+arg_50]
0x1402f302c  cmp     [r13+4], edi
0x1402f3030  jnz     loc_1402F3231
0x1402f3036  mov     r12, [r12]
0x1402f303a  test    r12, r12
0x1402f303d  jz      loc_1402F3240
0x1402f3043  lea     r8, [rsp+0E8h+arg_0]
0x1402f304b  mov     rdx, [r12]
0x1402f304f  mov     rcx, rbx
0x1402f3052  call    EfsSameContext
0x1402f3057  mov     esi, eax
0x1402f3059  mov     eax, [rbx]
0x1402f305b  sub     rax, 57h ; 'W'
0x1402f305f  lea     rcx, [rbx+50h]
0x1402f3063  jz      short loc_1402F3070
0x1402f3065  mov     byte ptr [rcx], 0
0x1402f3068  add     rcx, rdi
0x1402f306b  sub     rax, rdi
0x1402f306e  jnz     short loc_1402F3065
0x1402f3070  mov     rdx, rbx; Entry
0x1402f3073  mov     rcx, [rbx+48h]; Lookaside
0x1402f3077  call    cs:__imp_ExFreeToNPagedLookasideList
0x1402f307e  nop     dword ptr [rax+rax+00h]
0x1402f3083  xor     r9d, r9d
0x1402f3086  test    esi, esi
0x1402f3088  jns     short loc_1402F30A2
0x1402f308a  mov     r9d, esi
0x1402f308d  mov     edx, 6
0x1402f3092  mov     r8d, 0D87h
0x1402f3098  call    EfspTraceLogAssert
0x1402f309d  jmp     loc_1402F38E6
0x1402f30a2  cmp     byte ptr [rsp+0E8h+arg_0], r9b
0x1402f30aa  jnz     short loc_1402F30C9
0x1402f30ac  mov     eax, [r13+8]
0x1402f30b0  test    dil, al
0x1402f30b3  jz      loc_1402F3462
0x1402f30b9  mov     ebx, 0C000000Dh
0x1402f30be  mov     r8d, 0D9Ah
0x1402f30c4  jmp     loc_1402F3006
0x1402f30c9  mov     rbx, r9
0x1402f30cc  mov     [rsp+0E8h+var_98], rbx
0x1402f30d1  mov     r15, [rsp+0E8h+arg_28]
0x1402f30d9  test    r15, r15
0x1402f30dc  jz      loc_1402F3248
0x1402f30e2  mov     rax, [r15]
0x1402f30e5  test    rax, rax
0x1402f30e8  jz      loc_1402F3248
0x1402f30ee  cmp     [r12+8], r9
0x1402f30f3  jnz     loc_1402F3248
0x1402f30f9  lea     r8, [rax+10h]
0x1402f30fd  mov     [rsp+0E8h+var_60], r8
0x1402f3105  lea     rdx, [r8+18h]
0x1402f3109  mov     rax, [r12]
0x1402f310d  add     rax, 50h ; 'P'
0x1402f3111  mov     [rdx], rax
0x1402f3114  mov     rax, [r12]
0x1402f3118  mov     ecx, [rax]
0x1402f311a  mov     [rdx+8], ecx
0x1402f311d  mov     rax, [r12]
0x1402f3121  mov     rcx, [rax+38h]
0x1402f3125  mov     [rdx+10h], rcx
0x1402f3129  mov     rax, [r12]
0x1402f312d  mov     rcx, [rax+40h]
0x1402f3131  mov     [rdx+18h], rcx
0x1402f3135  mov     dword ptr [rdx+20h], 200h
0x1402f313c  mov     rax, [r12]
0x1402f3140  mov     ecx, [rax+4]
0x1402f3143  mov     [rdx+24h], ecx
0x1402f3146  mov     rax, [r12]
0x1402f314a  mov     ecx, [rax+18h]
0x1402f314d  mov     [rdx+28h], ecx
0x1402f3150  mov     [r8+10h], rdx
0x1402f3154  mov     rax, [r15]
0x1402f3157  mov     [rsp+0E8h+arg_0], rax
0x1402f315f  mov     r14, [rax]
0x1402f3162  test    r14, r14
0x1402f3165  jz      loc_1402F31EC
0x1402f316b  mov     eax, [r14+4]
0x1402f316f  cmp     eax, 660Eh
0x1402f3174  jz      short loc_1402F318B
0x1402f3176  cmp     eax, 6610h
0x1402f317b  jz      short loc_1402F318B
0x1402f317d  cmp     eax, 20006610h
0x1402f3182  jz      short loc_1402F318B
0x1402f3184  cmp     eax, 40006610h
0x1402f3189  jnz     short loc_1402F31AE
0x1402f318b  cmp     [r14+50h], edi
0x1402f318f  jnz     short loc_1402F31AE
0x1402f3191  mov     rcx, [r14+58h]; hKey
0x1402f3195  lea     rax, [rcx-1]
0x1402f3199  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1402f319d  ja      short loc_1402F31AE
0x1402f319f  call    cs:__imp_BCryptDestroyKey
0x1402f31a6  nop     dword ptr [rax+rax+00h]
0x1402f31ab  xor     r9d, r9d
0x1402f31ae  mov     eax, [r14]
0x1402f31b1  sub     rax, 57h ; 'W'
0x1402f31b5  lea     rcx, [r14+50h]
0x1402f31b9  jz      short loc_1402F31C6
0x1402f31bb  mov     [rcx], r9b
0x1402f31be  add     rcx, rdi
0x1402f31c1  sub     rax, rdi
0x1402f31c4  jnz     short loc_1402F31BB
0x1402f31c6  mov     rdx, r14; Entry
0x1402f31c9  mov     rcx, [r14+48h]; Lookaside
0x1402f31cd  call    cs:__imp_ExFreeToNPagedLookasideList
0x1402f31d4  nop     dword ptr [rax+rax+00h]
0x1402f31d9  mov     rax, [rsp+0E8h+arg_0]
0x1402f31e1  mov     [rax], rbx
0x1402f31e4  mov     r8, [rsp+0E8h+var_60]
0x1402f31ec  mov     rcx, [r15]
0x1402f31ef  mov     rax, [r12]
0x1402f31f3  mov     [rcx], rax
0x1402f31f6  mov     rax, [r15]
0x1402f31f9  mov     [rax+8], r8
0x1402f31fd  mov     edx, 6D736645h; Tag
0x1402f3202  mov     r12, [rsp+0E8h+arg_50]
0x1402f320a  mov     rcx, [r12]; P
0x1402f320e  call    cs:__imp_ExFreePoolWithTag
0x1402f3215  nop     dword ptr [rax+rax+00h]
0x1402f321a  mov     rax, [r15]
0x1402f321d  mov     [r12], rax
0x1402f3221  xor     r9d, r9d
0x1402f3224  mov     [r15], r9
0x1402f3227  mov     r14d, [rsp+0E8h+arg_8]
0x1402f322f  jmp     short loc_1402F3250
0x1402f3231  mov     r15, [rsp+0E8h+arg_28]
0x1402f3239  jmp     short loc_1402F3250
0x1402f323b  mov     edi, 1
0x1402f3240  mov     r15, [rsp+0E8h+arg_28]
0x1402f3248  mov     r12, [rsp+0E8h+arg_50]
0x1402f3250  mov     ecx, [r13+8]
0x1402f3254  mov     eax, ecx
0x1402f3256  and     eax, edi
0x1402f3258  jnz     short loc_1402F3263
0x1402f325a  test    cl, 8
0x1402f325d  jz      loc_1402F3615
0x1402f3263  test    eax, eax
0x1402f3265  jz      short loc_1402F32C6
0x1402f3267  mov     eax, [r13+0Ch]
0x1402f326b  test    al, 2
0x1402f326d  jnz     short loc_1402F3288
0x1402f326f  mov     edx, 6
0x1402f3274  mov     r9d, 0C0000001h
0x1402f327a  mov     r8d, 0DDCh
0x1402f3280  call    EfspTraceLogAssert
0x1402f3285  xor     r9d, r9d
0x1402f3288  test    dil, r14b
0x1402f328b  jz      short loc_1402F32C6
0x1402f328d  test    rbx, rbx
0x1402f3290  jz      short loc_1402F32BC
0x1402f3292  mov     eax, [rbx]
0x1402f3294  sub     rax, 57h ; 'W'
0x1402f3298  lea     rcx, [rbx+50h]
0x1402f329c  jz      short loc_1402F32A9
0x1402f329e  mov     [rcx], r9b
0x1402f32a1  add     rcx, rdi
0x1402f32a4  sub     rax, rdi
0x1402f32a7  jnz     short loc_1402F329E
0x1402f32a9  mov     rdx, rbx; Entry
0x1402f32ac  mov     rcx, [rbx+48h]; Lookaside
0x1402f32b0  call    cs:__imp_ExFreeToNPagedLookasideList
0x1402f32b7  nop     dword ptr [rax+rax+00h]
0x1402f32bc  mov     eax, 0C00000A2h
0x1402f32c1  jmp     loc_1402F38E8
0x1402f32c6  test    byte ptr [rsp+0E8h+arg_10], 2
0x1402f32ce  jz      loc_1402F34F3
0x1402f32d4  lea     rax, [rsp+0E8h+var_A8]
0x1402f32d9  mov     [rsp+0E8h+var_C0], rax
0x1402f32de  lea     rax, [rsp+0E8h+Size]
0x1402f32e3  mov     qword ptr [rsp+0E8h+var_C8], rax
0x1402f32e8  lea     r9, [rsp+0E8h+P]
0x1402f32ed  xor     r8d, r8d
0x1402f32f0  mov     rdx, [rsp+0E8h+arg_20]
0x1402f32f8  mov     r14, [rsp+0E8h+arg_18]
0x1402f3300  mov     rcx, r14
0x1402f3303  call    EfsReadEfsData
0x1402f3308  mov     esi, eax
0x1402f330a  mov     dword ptr [rsp+0E8h+Size+4], eax
0x1402f330e  test    esi, esi
0x1402f3310  js      loc_1402F3487
0x1402f3316  cmp     [rsp+0E8h+var_A8], 200h
0x1402f331e  jz      short loc_1402F332E
0x1402f3320  cmp     [rsp+0E8h+var_A8], 10000h
0x1402f3328  jnz     loc_1402F3487
0x1402f332e  cmp     [rsp+0E8h+var_A8], 10000h
0x1402f3336  jnz     loc_1402F3469
0x1402f333c  mov     [rsp+0E8h+var_C8], 8; int
0x1402f3344  lea     r9, [rsp+0E8h+var_80]
0x1402f3349  mov     r8d, 0Bh
0x1402f334f  mov     edx, dword ptr [rsp+0E8h+Size]; Size
0x1402f3353  mov     r14, [rsp+0E8h+P]
0x1402f3358  mov     rcx, r14; Src
0x1402f335b  call    EfsGetEfsStreamInfo
0x1402f3360  mov     esi, eax
0x1402f3362  test    eax, eax
0x1402f3364  jns     short loc_1402F33B4
0x1402f3366  test    rbx, rbx
0x1402f3369  jz      short loc_1402F3395
0x1402f336b  mov     eax, [rbx]
0x1402f336d  sub     rax, 57h ; 'W'
0x1402f3371  lea     rdx, [rbx+50h]
0x1402f3375  jz      short loc_1402F3382
0x1402f3377  mov     byte ptr [rdx], 0
0x1402f337a  add     rdx, rdi
0x1402f337d  sub     rax, rdi
0x1402f3380  jnz     short loc_1402F3377
0x1402f3382  mov     rdx, rbx; Entry
0x1402f3385  mov     rcx, [rbx+48h]; Lookaside
0x1402f3389  call    cs:__imp_ExFreeToNPagedLookasideList
0x1402f3390  nop     dword ptr [rax+rax+00h]
0x1402f3395  test    r14, r14
0x1402f3398  jz      loc_1402F38E6
0x1402f339e  xor     edx, edx; Tag
0x1402f33a0  mov     rcx, r14; P
0x1402f33a3  call    cs:__imp_ExFreePoolWithTag
0x1402f33aa  nop     dword ptr [rax+rax+00h]
0x1402f33af  jmp     loc_1402F38E6
0x1402f33b4  xor     edx, edx; Tag
0x1402f33b6  mov     rcx, r14; P
0x1402f33b9  call    cs:__imp_ExFreePoolWithTag
0x1402f33c0  nop     dword ptr [rax+rax+00h]
0x1402f33c5  cmp     [rsp+0E8h+var_80], edi
0x1402f33c9  jnz     loc_1402F34F3
0x1402f33cf  test    [rsp+0E8h+var_7C], 3
0x1402f33d4  jz      loc_1402F34F3
0x1402f33da  mov     eax, [r13+8]
0x1402f33de  test    dil, al
0x1402f33e1  jz      short loc_1402F341D
0x1402f33e3  test    rbx, rbx
0x1402f33e6  jz      short loc_1402F3412
0x1402f33e8  mov     eax, [rbx]
0x1402f33ea  sub     rax, 57h ; 'W'
0x1402f33ee  lea     rcx, [rbx+50h]
0x1402f33f2  jz      short loc_1402F33FF
0x1402f33f4  mov     byte ptr [rcx], 0
0x1402f33f7  add     rcx, rdi
0x1402f33fa  sub     rax, rdi
0x1402f33fd  jnz     short loc_1402F33F4
  ... truncated ...
```
