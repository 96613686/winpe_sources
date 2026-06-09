# SymCryptSswu

- ea: `0x14001d634`
- end: `0x14001e31a`
- name: `SymCryptSswu`
- size: `3302`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation`

## callers

- `0x14001c418`

## callees

- `0x1400047d0`
- `0x140004b1c`
- `0x140004b50`
- `0x140004ba8`
- `0x140004dcc`
- `0x140005010`
- `0x140007c6c`
- `0x140007cf0`
- `0x140007d24`
- `0x1400085e4`
- `0x14000bbcc`
- `0x14000bc04`
- `0x14001d0c0`
- `0x14001d634`
- `0x14001e320`
- `0x14001e3c4`
- `0x14002071c`
- `0x14002b740`
- `0x14002c550`
- `0x140059100`
- `0x14009bbb0`
- `0x14009bbf0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001e086`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001e0d5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001e128`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001e179`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001e1cf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001e21d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001e26c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001e2bb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001e086`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001e0d5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001e128`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001e179`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001e1cf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001e21d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001e26c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001e2bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e097`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e0e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e139`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e18a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e1e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e22e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e27d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e2cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e097`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e0e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e139`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e18a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e1e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e22e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e27d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e2cc`

## pseudocode

```c
__int64 __fastcall SymCryptSswu(__int64 a1, int a2, __int64 a3, __int64 a4, void *a5, __int64 a6)
{
  unsigned int v7; // eax
  __int64 v8; // r15
  unsigned int v9; // ebx
  unsigned int v10; // eax
  unsigned int v11; // edi
  _DWORD *v12; // rax
  __int64 v13; // rbx
  __int64 v14; // r14
  __int64 v15; // rax
  unsigned int v16; // ecx
  __int64 v17; // rbx
  __int64 v18; // r13
  __int64 v19; // rax
  unsigned int v20; // ecx
  __int64 v21; // rbx
  __int64 v22; // rbp
  __int64 v23; // rax
  unsigned int v24; // ecx
  __int64 v25; // rbx
  __int64 v26; // rax
  unsigned int v27; // ecx
  __int64 v28; // rbx
  __int64 v29; // r12
  __int64 v30; // rax
  unsigned int v31; // ecx
  __int64 v32; // rdi
  char *v33; // rbx
  char *v34; // rax
  unsigned int v35; // ecx
  __int64 v36; // rdi
  __int64 v37; // rax
  unsigned int v38; // ecx
  __int64 v39; // rdi
  __int64 v40; // rax
  __int64 v41; // rdx
  __int64 v42; // r8
  unsigned int v43; // ecx
  __int64 v44; // r9
  unsigned int v45; // r8d
  __int64 v46; // rcx
  unsigned int v47; // edx
  __int64 v48; // rcx
  unsigned __int64 v49; // rdi
  __int64 v50; // r9
  struct NETMON_VELAN *v51; // rbx
  unsigned int v52; // ebx
  int v53; // ebx
  unsigned __int64 v54; // rbx
  __int64 v55; // rdi
  __int64 v56; // r15
  char *v57; // rbx
  PNPAGED_LOOKASIDE_LIST *v58; // rbx
  __int64 v59; // r12
  __int64 v60; // rbx
  __int64 v61; // rbx
  __int64 v62; // rbp
  __int64 v63; // r13
  __int64 v64; // r14
  unsigned int v67; // [rsp+58h] [rbp-F0h]
  _DWORD *v68; // [rsp+60h] [rbp-E8h]
  __int64 v69; // [rsp+68h] [rbp-E0h]
  int v70; // [rsp+70h] [rbp-D8h] BYREF
  void *v71; // [rsp+78h] [rbp-D0h]
  __int64 v72; // [rsp+80h] [rbp-C8h]
  void *Src; // [rsp+88h] [rbp-C0h]
  __int64 v74; // [rsp+90h] [rbp-B8h]
  __int64 v75; // [rsp+98h] [rbp-B0h]
  _BYTE v76[96]; // [rsp+A0h] [rbp-A8h] BYREF

  v74 = a3;
  v75 = a4;
  memset(v76, 0, sizeof(v76));
  v7 = *(_DWORD *)(a1 + 12);
  v8 = 0;
  if ( v7 )
  {
    if ( v7 <= 0x100000 )
      v9 = (*(_DWORD *)(a1 + 12) >> 9) + (((*(_DWORD *)(a1 + 12) & 0x1FFu) + 511) >> 9);
    else
      v9 = 0;
  }
  else
  {
    v9 = 1;
  }
  v68 = 0;
  v10 = SymCryptFdefSizeofIntFromDigits(v9);
  v11 = v10;
  if ( v10 )
  {
    v12 = (_DWORD *)SymCryptCallbackAlloc(v10);
    if ( v12 )
    {
      *v12 = 1732837376;
      v12[1] = v9;
      v12[2] = v11;
      v68 = v12;
    }
  }
  v13 = *(_QWORD *)(a1 + 616);
  v14 = 0;
  v15 = SymCryptCallbackAlloc(*(unsigned int *)(v13 + 16));
  if ( v15 )
  {
    v14 = v15;
    v16 = (*(_DWORD *)(v13 + 4) << 6) - 64;
    *(_QWORD *)(v16 + v15) = 0;
    *(_QWORD *)(v16 + v15 + 8) = 0;
    *(_QWORD *)(v16 + v15 + 16) = 0;
    *(_QWORD *)(v16 + v15 + 24) = 0;
    *(_QWORD *)(v16 + v15 + 32) = 0;
    *(_QWORD *)(v16 + v15 + 40) = 0;
    *(_QWORD *)(v16 + v15 + 48) = 0;
    *(_QWORD *)(v16 + v15 + 56) = 0;
  }
  v17 = *(_QWORD *)(a1 + 616);
  v18 = 0;
  v19 = SymCryptCallbackAlloc(*(unsigned int *)(v17 + 16));
  if ( v19 )
  {
    v18 = v19;
    v20 = (*(_DWORD *)(v17 + 4) << 6) - 64;
    *(_QWORD *)(v20 + v19) = 0;
    *(_QWORD *)(v20 + v19 + 8) = 0;
    *(_QWORD *)(v20 + v19 + 16) = 0;
    *(_QWORD *)(v20 + v19 + 24) = 0;
    *(_QWORD *)(v20 + v19 + 32) = 0;
    *(_QWORD *)(v20 + v19 + 40) = 0;
    *(_QWORD *)(v20 + v19 + 48) = 0;
    *(_QWORD *)(v20 + v19 + 56) = 0;
  }
  v21 = *(_QWORD *)(a1 + 616);
  v22 = 0;
  v23 = SymCryptCallbackAlloc(*(unsigned int *)(v21 + 16));
  if ( v23 )
  {
    v22 = v23;
    v24 = (*(_DWORD *)(v21 + 4) << 6) - 64;
    *(_QWORD *)(v24 + v23) = 0;
    *(_QWORD *)(v24 + v23 + 8) = 0;
    *(_QWORD *)(v24 + v23 + 16) = 0;
    *(_QWORD *)(v24 + v23 + 24) = 0;
    *(_QWORD *)(v24 + v23 + 32) = 0;
    *(_QWORD *)(v24 + v23 + 40) = 0;
    *(_QWORD *)(v24 + v23 + 48) = 0;
    *(_QWORD *)(v24 + v23 + 56) = 0;
  }
  v25 = *(_QWORD *)(a1 + 616);
  v72 = 0;
  v26 = SymCryptCallbackAlloc(*(unsigned int *)(v25 + 16));
  if ( v26 )
  {
    v27 = (*(_DWORD *)(v25 + 4) << 6) - 64;
    v72 = v26;
    *(_QWORD *)(v27 + v26) = 0;
    *(_QWORD *)(v27 + v26 + 8) = 0;
    *(_QWORD *)(v27 + v26 + 16) = 0;
    *(_QWORD *)(v27 + v26 + 24) = 0;
    *(_QWORD *)(v27 + v26 + 32) = 0;
    *(_QWORD *)(v27 + v26 + 40) = 0;
    *(_QWORD *)(v27 + v26 + 48) = 0;
    *(_QWORD *)(v27 + v26 + 56) = 0;
  }
  v28 = *(_QWORD *)(a1 + 616);
  v29 = 0;
  v30 = SymCryptCallbackAlloc(*(unsigned int *)(v28 + 16));
  if ( v30 )
  {
    v29 = v30;
    v31 = (*(_DWORD *)(v28 + 4) << 6) - 64;
    *(_QWORD *)(v31 + v30) = 0;
    *(_QWORD *)(v31 + v30 + 8) = 0;
    *(_QWORD *)(v31 + v30 + 16) = 0;
    *(_QWORD *)(v31 + v30 + 24) = 0;
    *(_QWORD *)(v31 + v30 + 32) = 0;
    *(_QWORD *)(v31 + v30 + 40) = 0;
    *(_QWORD *)(v31 + v30 + 48) = 0;
    *(_QWORD *)(v31 + v30 + 56) = 0;
  }
  v32 = *(_QWORD *)(a1 + 616);
  v33 = 0;
  v71 = 0;
  v34 = (char *)SymCryptCallbackAlloc(*(unsigned int *)(v32 + 16));
  if ( v34 )
  {
    v33 = v34;
    v35 = (*(_DWORD *)(v32 + 4) << 6) - 64;
    v71 = v34;
    *(_QWORD *)&v34[v35] = 0;
    *(_QWORD *)&v34[v35 + 8] = 0;
    *(_QWORD *)&v34[v35 + 16] = 0;
    *(_QWORD *)&v34[v35 + 24] = 0;
    *(_QWORD *)&v34[v35 + 32] = 0;
    *(_QWORD *)&v34[v35 + 40] = 0;
    *(_QWORD *)&v34[v35 + 48] = 0;
    *(_QWORD *)&v34[v35 + 56] = 0;
  }
  v36 = *(_QWORD *)(a1 + 616);
  v37 = SymCryptCallbackAlloc(*(unsigned int *)(v36 + 16));
  if ( v37 )
  {
    v8 = v37;
    v38 = (*(_DWORD *)(v36 + 4) << 6) - 64;
    *(_QWORD *)(v38 + v37) = 0;
    *(_QWORD *)(v38 + v37 + 8) = 0;
    *(_QWORD *)(v38 + v37 + 16) = 0;
    *(_QWORD *)(v38 + v37 + 24) = 0;
    *(_QWORD *)(v38 + v37 + 32) = 0;
    *(_QWORD *)(v38 + v37 + 40) = 0;
    *(_QWORD *)(v38 + v37 + 48) = 0;
    *(_QWORD *)(v38 + v37 + 56) = 0;
  }
  v39 = 0;
  Src = *(void **)(a1 + 616);
  v69 = 0;
  v40 = SymCryptCallbackAlloc(*((unsigned int *)Src + 4));
  v42 = 0;
  if ( v40 )
  {
    v39 = v40;
    v69 = v40;
    v43 = (*((_DWORD *)Src + 1) << 6) - 64;
    *(_QWORD *)(v43 + v40) = 0;
    *(_QWORD *)(v43 + v40 + 8) = 0;
    *(_QWORD *)(v43 + v40 + 16) = 0;
    *(_QWORD *)(v43 + v40 + 24) = 0;
    *(_QWORD *)(v43 + v40 + 32) = 0;
    *(_QWORD *)(v43 + v40 + 40) = 0;
    *(_QWORD *)(v43 + v40 + 48) = 0;
    *(_QWORD *)(v43 + v40 + 56) = 0;
  }
  if ( v68 && v14 && v18 && v22 && v72 && v29 && v33 && v8 && v39 )
  {
    SymCryptFdefModElementSetValueNegUint32(-a2, *(_QWORD *)(a1 + 616), v18, (_DWORD)a5, a6);
    SymCryptModElementSetValueUint32(1, *(_QWORD *)(a1 + 616), v14, (_DWORD)a5, a6);
    SymCryptModSquare(*(_QWORD *)(a1 + 616), v74, v22, (_DWORD)a5, a6);
    SymCryptModMul(*(_QWORD *)(a1 + 616), v22, v18, v22, (__int64)a5, a6);
    SymCryptModAdd(*(_QWORD *)(a1 + 616), v22, v14, v14, (__int64)a5, a6);
    SymCryptModMul(*(_QWORD *)(a1 + 616), v22, v14, v22, (__int64)a5, a6);
    v44 = *(_QWORD *)(a1 + 616);
    v45 = 0;
    v46 = 0;
    v47 = 16 * *(_DWORD *)(v44 + 4);
    if ( v47 )
    {
      do
      {
        v45 |= *(_DWORD *)(v22 + 4 * v46);
        v46 = (unsigned int)(v46 + 1);
      }
      while ( (unsigned int)v46 < v47 );
    }
    v48 = v44 + 128;
    v49 = (unsigned __int64)-(__int64)v45 >> 32;
    v70 = ~(_DWORD)v49;
    v50 = (unsigned int)v68[1];
    Src = v68 + 8;
    SymCryptFdefRawSubUint32(v48, 2, v68 + 8, v50);
    SymCryptModExpWindowed(*(_QWORD *)(a1 + 616), v22, (_DWORD)v68, *(_DWORD *)(a1 + 12), v72, (__int64)a5, a6);
    SymCryptModMul(*(_QWORD *)(a1 + 616), v18, *(_QWORD *)(a1 + 632), v14, (__int64)a5, a6);
    SymCryptModInv(*(_QWORD *)(a1 + 616), v14, v14, 9, (__int64)a5, a6);
    SymCryptModMul(*(_QWORD *)(a1 + 616), *(_QWORD *)(a1 + 640), v14, v29, (__int64)a5, a6);
    SymCryptModInv(*(_QWORD *)(a1 + 616), *(_QWORD *)(a1 + 632), v14, 9, (__int64)a5, a6);
    SymCryptModMul(*(_QWORD *)(a1 + 616), *(_QWORD *)(a1 + 640), v14, v14, (__int64)a5, a6);
    SymCryptModNeg(*(_QWORD *)(a1 + 616), v14, v14, (_DWORD)a5, a6);
    SymCryptWipeAsm(v68 + 8, (unsigned int)(v68[1] << 6));
    v68[8] = 1;
    v51 = *(struct NETMON_VELAN **)(a1 + 616);
    SymCryptFdefRawDivMod(v68 + 8, v71, (__int64)a5);
    (*(void (__fastcall **)(struct NETMON_VELAN *, int, void *, unsigned int))((char *)&off_14009E030
                                                                             + (*(_DWORD *)v51 & 0x380)))(
      v51,
      (int)v71,
      a5,
      a6);
    SymCryptModAdd(*(_QWORD *)(a1 + 616), (_DWORD)v71, v72, (_DWORD)v71, (__int64)a5, a6);
    LODWORD(v51) = (_DWORD)v71;
    SymCryptModMul(*(_QWORD *)(a1 + 616), (_DWORD)v71, v14, (_DWORD)v71, (__int64)a5, a6);
    SymCryptFdefMaskedCopyAsm(v71, v29, *(unsigned int *)(*(_QWORD *)(a1 + 616) + 4LL), (unsigned int)v49);
    SymCryptModSquare(*(_QWORD *)(a1 + 616), v29, v8, (_DWORD)a5, a6);
    SymCryptModAdd(*(_QWORD *)(a1 + 616), v8, *(_QWORD *)(a1 + 632), v8, (__int64)a5, a6);
    SymCryptModMul(*(_QWORD *)(a1 + 616), v8, v29, v8, (__int64)a5, a6);
    SymCryptModAdd(*(_QWORD *)(a1 + 616), v8, *(_QWORD *)(a1 + 640), v8, (__int64)a5, a6);
    SymCryptModSquare(*(_QWORD *)(a1 + 616), v74, (_DWORD)v71, (_DWORD)a5, a6);
    SymCryptModMul(*(_QWORD *)(a1 + 616), (_DWORD)v51, v18, (_DWORD)v51, (__int64)a5, a6);
    SymCryptModMul(*(_QWORD *)(a1 + 616), (_DWORD)v51, v29, (_DWORD)v51, (__int64)a5, a6);
    SymCryptModSquare(*(_QWORD *)(a1 + 616), (_DWORD)v71, v69, (_DWORD)a5, a6);
    SymCryptModAdd(*(_QWORD *)(a1 + 616), v69, *(_QWORD *)(a1 + 632), v69, (__int64)a5, a6);
    SymCryptModMul(*(_QWORD *)(a1 + 616), v69, (_DWORD)v71, v69, (__int64)a5, a6);
    SymCryptModAdd(*(_QWORD *)(a1 + 616), v69, *(_QWORD *)(a1 + 640), v69, (__int64)a5, a6);
    v67 = SymCryptModSqrt(*(_QWORD *)(a1 + 616), v8, &v70, 0, a5, a6);
    if ( !v67 )
    {
      v52 = ~v70;
      SymCryptFdefMaskedCopyAsm(v69, v8, *(unsigned int *)(*(_QWORD *)(a1 + 616) + 4LL), (unsigned int)~v70);
      SymCryptFdefMaskedCopyAsm(v71, v29, *(unsigned int *)(*(_QWORD *)(a1 + 616) + 4LL), v52);
      SymCryptModSqrt(*(_QWORD *)(a1 + 616), v8, &v70, v8, a5, a6);
      SymCryptModElementToInt(*(_QWORD *)(a1 + 616), v74, (_DWORD)v68, (_DWORD)a5, a6);
      v53 = *(_DWORD *)Src;
      SymCryptModElementToInt(*(_QWORD *)(a1 + 616), v8, (_DWORD)v68, (_DWORD)a5, a6);
      v54 = (unsigned __int64)-(__int64)(((unsigned __int8)*(_DWORD *)Src ^ (unsigned __int8)v53) & 1) >> 32;
      SymCryptModNeg(*(_QWORD *)(a1 + 616), v8, v14, (_DWORD)a5, a6);
      SymCryptFdefMaskedCopyAsm(v14, v8, *(unsigned int *)(*(_QWORD *)(a1 + 616) + 4LL), (unsigned int)v54);
      SymCryptFdefModElementGetValue(*(_QWORD *)(a1 + 616), v29, v76, *(unsigned int *)(a1 + 20));
      SymCryptFdefModElementGetValue(
        *(_QWORD *)(a1 + 616),
        v8,
        &v76[*(unsigned int *)(a1 + 20)],
        *(unsigned int *)(a1 + 20));
      v67 = SymCryptEcpointSetValue(a1, v76, (unsigned int)(2 * *(_DWORD *)(a1 + 20)));
    }
    v39 = v69;
  }
  else
  {
    v67 = 32783;
    if ( !v39 )
      goto LABEL_46;
  }
  SymCryptWipeAsm(v39, *(unsigned int *)(*(_QWORD *)(a1 + 616) + 16LL));
  v55 = v39 - *(unsigned int *)(v39 - 4);
  if ( v55 )
  {
    if ( *(_QWORD *)(v55 - 16) )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v55 - 16), (PVOID)(v55 - 16));
    else
      ExFreePoolWithTag((PVOID)(v55 - 16), *(_DWORD *)(v55 - 16 + 8));
  }
LABEL_46:
  if ( v8 )
  {
    SymCryptWipeAsm(v8, *(unsigned int *)(*(_QWORD *)(a1 + 616) + 16LL));
    v56 = v8 - *(unsigned int *)(v8 - 4);
    if ( v56 )
    {
      if ( *(_QWORD *)(v56 - 16) )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v56 - 16), (PVOID)(v56 - 16));
      else
        ExFreePoolWithTag((PVOID)(v56 - 16), *(_DWORD *)(v56 - 16 + 8));
    }
  }
  v57 = (char *)v71;
  if ( v71 )
  {
    SymCryptWipeAsm(v71, *(unsigned int *)(*(_QWORD *)(a1 + 616) + 16LL));
    v58 = (PNPAGED_LOOKASIDE_LIST *)&v57[-*((unsigned int *)v57 - 1)];
    if ( v58 )
    {
      if ( *(v58 - 2) )
        ExFreeToNPagedLookasideList(*(v58 - 2), v58 - 2);
      else
        ExFreePoolWithTag(v58 - 2, *((_DWORD *)v58 - 2));
    }
  }
  if ( v29 )
  {
    SymCryptWipeAsm(v29, *(unsigned int *)(*(_QWORD *)(a1 + 616) + 16LL));
    v59 = v29 - *(unsigned int *)(v29 - 4);
    if ( v59 )
    {
      if ( *(_QWORD *)(v59 - 16) )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v59 - 16), (PVOID)(v59 - 16));
      else
        ExFreePoolWithTag((PVOID)(v59 - 16), *(_DWORD *)(v59 - 16 + 8));
    }
  }
  v60 = v72;
  if ( v72 )
  {
    SymCryptWipeAsm(v72, *(unsigned int *)(*(_QWORD *)(a1 + 616) + 16LL));
    v61 = v60 - *(unsigned int *)(v60 - 4);
    if ( v61 )
    {
      if ( *(_QWORD *)(v61 - 16) )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v61 - 16), (PVOID)(v61 - 16));
      else
        ExFreePoolWithTag((PVOID)(v61 - 16), *(_DWORD *)(v61 - 16 + 8));
    }
  }
  if ( v22 )
  {
    SymCryptWipeAsm(v22, *(unsigned int *)(*(_QWORD *)(a1 + 616) + 16LL));
    v62 = v22 - *(unsigned int *)(v22 - 4);
    if ( v62 )
    {
      if ( *(_QWORD *)(v62 - 16) )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v62 - 16), (PVOID)(v62 - 16));
      else
        ExFreePoolWithTag((PVOID)(v62 - 16), *(_DWORD *)(v62 - 16 + 8));
    }
  }
  if ( v18 )
  {
    SymCryptWipeAsm(v18, *(unsigned int *)(*(_QWORD *)(a1 + 616) + 16LL));
    v63 = v18 - *(unsigned int *)(v18 - 4);
    if ( v63 )
    {
      if ( *(_QWORD *)(v63 - 16) )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v63 - 16), (PVOID)(v63 - 16));
      else
        ExFreePoolWithTag((PVOID)(v63 - 16), *(_DWORD *)(v63 - 16 + 8));
    }
  }
  if ( v14 )
  {
    SymCryptWipeAsm(v14, *(unsigned int *)(*(_QWORD *)(a1 + 616) + 16LL));
    v64 = v14 - *(unsigned int *)(v14 - 4);
    if ( v64 )
    {
      if ( *(_QWORD *)(v64 - 16) )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v64 - 16), (PVOID)(v64 - 16));
      else
        ExFreePoolWithTag((PVOID)(v64 - 16), *(_DWORD *)(v64 - 16 + 8));
    }
  }
  if ( v68 )
    SymCryptIntFree(v68, v41, v42);
  return v67;
}

```

## disassembly

```asm
0x14001d634  mov     [rsp+arg_8], rbx
0x14001d639  push    rbp
0x14001d63a  push    rsi
0x14001d63b  push    rdi
0x14001d63c  push    r12
0x14001d63e  push    r13
0x14001d640  push    r14
0x14001d642  push    r15
0x14001d644  sub     rsp, 110h
0x14001d64b  mov     rax, cs:__security_cookie
0x14001d652  xor     rax, rsp
0x14001d655  mov     [rsp+148h+var_48], rax
0x14001d65d  mov     rax, [rsp+148h+arg_20]
0x14001d665  mov     rsi, rcx
0x14001d668  mov     [rsp+148h+var_F0], edx
0x14001d66c  lea     rcx, [rsp+148h+var_A8]; void *
0x14001d674  xor     edx, edx; Val
0x14001d676  mov     [rsp+148h+var_B8], r8
0x14001d67e  mov     [rsp+148h+var_B0], r9
0x14001d686  mov     [rsp+148h+var_F8], rax
0x14001d68b  lea     r8d, [rdx+60h]; Size
0x14001d68f  call    memset
0x14001d694  mov     eax, [rsi+0Ch]
0x14001d697  xor     r15d, r15d
0x14001d69a  test    eax, eax
0x14001d69c  jnz     short loc_14001D6A3
0x14001d69e  lea     ebx, [rax+1]
0x14001d6a1  jmp     short loc_14001D6C2
0x14001d6a3  cmp     eax, 100000h
0x14001d6a8  jbe     short loc_14001D6AF
0x14001d6aa  mov     ebx, r15d
0x14001d6ad  jmp     short loc_14001D6C2
0x14001d6af  mov     ebx, eax
0x14001d6b1  mov     ecx, 1FFh
0x14001d6b6  and     ebx, ecx
0x14001d6b8  shr     eax, 9
0x14001d6bb  add     ebx, ecx
0x14001d6bd  shr     ebx, 9
0x14001d6c0  add     ebx, eax
0x14001d6c2  mov     ecx, ebx
0x14001d6c4  mov     [rsp+148h+var_E8], r15
0x14001d6c9  call    SymCryptFdefSizeofIntFromDigits
0x14001d6ce  mov     edi, eax
0x14001d6d0  test    eax, eax
0x14001d6d2  jz      short loc_14001D6F1
0x14001d6d4  mov     ecx, edi
0x14001d6d6  call    SymCryptCallbackAlloc
0x14001d6db  test    rax, rax
0x14001d6de  jz      short loc_14001D6F1
0x14001d6e0  mov     dword ptr [rax], 67490000h
0x14001d6e6  mov     [rax+4], ebx
0x14001d6e9  mov     [rax+8], edi
0x14001d6ec  mov     [rsp+148h+var_E8], rax
0x14001d6f1  mov     rbx, [rsi+268h]
0x14001d6f8  mov     r14, r15
0x14001d6fb  mov     ecx, [rbx+10h]
0x14001d6fe  call    SymCryptCallbackAlloc
0x14001d703  test    rax, rax
0x14001d706  jz      short loc_14001D73B
0x14001d708  mov     ecx, [rbx+4]
0x14001d70b  mov     r14, rax
0x14001d70e  shl     ecx, 6
0x14001d711  sub     ecx, 40h ; '@'
0x14001d714  mov     [rcx+rax], r15
0x14001d718  mov     [rcx+rax+8], r15
0x14001d71d  mov     [rcx+rax+10h], r15
0x14001d722  mov     [rcx+rax+18h], r15
0x14001d727  mov     [rcx+rax+20h], r15
0x14001d72c  mov     [rcx+rax+28h], r15
0x14001d731  mov     [rcx+rax+30h], r15
0x14001d736  mov     [rcx+rax+38h], r15
0x14001d73b  mov     rbx, [rsi+268h]
0x14001d742  mov     r13, r15
0x14001d745  mov     ecx, [rbx+10h]
0x14001d748  call    SymCryptCallbackAlloc
0x14001d74d  test    rax, rax
0x14001d750  jz      short loc_14001D785
0x14001d752  mov     ecx, [rbx+4]
0x14001d755  mov     r13, rax
0x14001d758  shl     ecx, 6
0x14001d75b  sub     ecx, 40h ; '@'
0x14001d75e  mov     [rcx+rax], r15
0x14001d762  mov     [rcx+rax+8], r15
0x14001d767  mov     [rcx+rax+10h], r15
0x14001d76c  mov     [rcx+rax+18h], r15
0x14001d771  mov     [rcx+rax+20h], r15
0x14001d776  mov     [rcx+rax+28h], r15
0x14001d77b  mov     [rcx+rax+30h], r15
0x14001d780  mov     [rcx+rax+38h], r15
0x14001d785  mov     rbx, [rsi+268h]
0x14001d78c  mov     rbp, r15
0x14001d78f  mov     ecx, [rbx+10h]
0x14001d792  call    SymCryptCallbackAlloc
0x14001d797  test    rax, rax
0x14001d79a  jz      short loc_14001D7CF
0x14001d79c  mov     ecx, [rbx+4]
0x14001d79f  mov     rbp, rax
0x14001d7a2  shl     ecx, 6
0x14001d7a5  sub     ecx, 40h ; '@'
0x14001d7a8  mov     [rcx+rax], r15
0x14001d7ac  mov     [rcx+rax+8], r15
0x14001d7b1  mov     [rcx+rax+10h], r15
0x14001d7b6  mov     [rcx+rax+18h], r15
0x14001d7bb  mov     [rcx+rax+20h], r15
0x14001d7c0  mov     [rcx+rax+28h], r15
0x14001d7c5  mov     [rcx+rax+30h], r15
0x14001d7ca  mov     [rcx+rax+38h], r15
0x14001d7cf  mov     rbx, [rsi+268h]
0x14001d7d6  mov     [rsp+148h+var_C8], r15
0x14001d7de  mov     ecx, [rbx+10h]
0x14001d7e1  call    SymCryptCallbackAlloc
0x14001d7e6  test    rax, rax
0x14001d7e9  jz      short loc_14001D823
0x14001d7eb  mov     ecx, [rbx+4]
0x14001d7ee  shl     ecx, 6
0x14001d7f1  sub     ecx, 40h ; '@'
0x14001d7f4  mov     [rsp+148h+var_C8], rax
0x14001d7fc  mov     [rcx+rax], r15
0x14001d800  mov     [rcx+rax+8], r15
0x14001d805  mov     [rcx+rax+10h], r15
0x14001d80a  mov     [rcx+rax+18h], r15
0x14001d80f  mov     [rcx+rax+20h], r15
0x14001d814  mov     [rcx+rax+28h], r15
0x14001d819  mov     [rcx+rax+30h], r15
0x14001d81e  mov     [rcx+rax+38h], r15
0x14001d823  mov     rbx, [rsi+268h]
0x14001d82a  mov     r12, r15
0x14001d82d  mov     ecx, [rbx+10h]
0x14001d830  call    SymCryptCallbackAlloc
0x14001d835  test    rax, rax
0x14001d838  jz      short loc_14001D86D
0x14001d83a  mov     ecx, [rbx+4]
0x14001d83d  mov     r12, rax
0x14001d840  shl     ecx, 6
0x14001d843  sub     ecx, 40h ; '@'
0x14001d846  mov     [rcx+rax], r15
0x14001d84a  mov     [rcx+rax+8], r15
0x14001d84f  mov     [rcx+rax+10h], r15
0x14001d854  mov     [rcx+rax+18h], r15
0x14001d859  mov     [rcx+rax+20h], r15
0x14001d85e  mov     [rcx+rax+28h], r15
0x14001d863  mov     [rcx+rax+30h], r15
0x14001d868  mov     [rcx+rax+38h], r15
0x14001d86d  mov     rdi, [rsi+268h]
0x14001d874  mov     rbx, r15
0x14001d877  mov     [rsp+148h+var_D0], rbx
0x14001d87c  mov     ecx, [rdi+10h]
0x14001d87f  call    SymCryptCallbackAlloc
0x14001d884  test    rax, rax
0x14001d887  jz      short loc_14001D8C1
0x14001d889  mov     ecx, [rdi+4]
0x14001d88c  mov     rbx, rax
0x14001d88f  shl     ecx, 6
0x14001d892  sub     ecx, 40h ; '@'
0x14001d895  mov     [rsp+148h+var_D0], rax
0x14001d89a  mov     [rcx+rax], r15
0x14001d89e  mov     [rcx+rax+8], r15
0x14001d8a3  mov     [rcx+rax+10h], r15
0x14001d8a8  mov     [rcx+rax+18h], r15
0x14001d8ad  mov     [rcx+rax+20h], r15
0x14001d8b2  mov     [rcx+rax+28h], r15
0x14001d8b7  mov     [rcx+rax+30h], r15
0x14001d8bc  mov     [rcx+rax+38h], r15
0x14001d8c1  mov     rdi, [rsi+268h]
0x14001d8c8  mov     ecx, [rdi+10h]
0x14001d8cb  call    SymCryptCallbackAlloc
0x14001d8d0  xor     r8d, r8d
0x14001d8d3  test    rax, rax
0x14001d8d6  jz      short loc_14001D90B
0x14001d8d8  mov     ecx, [rdi+4]
0x14001d8db  mov     r15, rax
0x14001d8de  shl     ecx, 6
0x14001d8e1  sub     ecx, 40h ; '@'
0x14001d8e4  mov     [rcx+rax], r8
0x14001d8e8  mov     [rcx+rax+8], r8
0x14001d8ed  mov     [rcx+rax+10h], r8
0x14001d8f2  mov     [rcx+rax+18h], r8
0x14001d8f7  mov     [rcx+rax+20h], r8
0x14001d8fc  mov     [rcx+rax+28h], r8
0x14001d901  mov     [rcx+rax+30h], r8
0x14001d906  mov     [rcx+rax+38h], r8
0x14001d90b  mov     rax, [rsi+268h]
0x14001d912  mov     rdi, r8
0x14001d915  mov     [rsp+148h+Src], rax
0x14001d91d  mov     [rsp+148h+var_E0], r8
0x14001d922  mov     ecx, [rax+10h]
0x14001d925  call    SymCryptCallbackAlloc
0x14001d92a  xor     r8d, r8d
0x14001d92d  test    rax, rax
0x14001d930  jz      short loc_14001D972
0x14001d932  mov     rcx, [rsp+148h+Src]
0x14001d93a  mov     rdi, rax
0x14001d93d  mov     [rsp+148h+var_E0], rax
0x14001d942  mov     ecx, [rcx+4]
0x14001d945  shl     ecx, 6
0x14001d948  sub     ecx, 40h ; '@'
0x14001d94b  mov     [rcx+rax], r8
0x14001d94f  mov     [rcx+rax+8], r8
0x14001d954  mov     [rcx+rax+10h], r8
0x14001d959  mov     [rcx+rax+18h], r8
0x14001d95e  mov     [rcx+rax+20h], r8
0x14001d963  mov     [rcx+rax+28h], r8
0x14001d968  mov     [rcx+rax+30h], r8
0x14001d96d  mov     [rcx+rax+38h], r8
0x14001d972  cmp     [rsp+148h+var_E8], r8
0x14001d977  jz      loc_14001E048
0x14001d97d  test    r14, r14
0x14001d980  jz      loc_14001E048
0x14001d986  test    r13, r13
0x14001d989  jz      loc_14001E048
0x14001d98f  test    rbp, rbp
0x14001d992  jz      loc_14001E048
0x14001d998  cmp     [rsp+148h+var_C8], r8
0x14001d9a0  jz      loc_14001E048
0x14001d9a6  test    r12, r12
0x14001d9a9  jz      loc_14001E048
0x14001d9af  test    rbx, rbx
0x14001d9b2  jz      loc_14001E048
0x14001d9b8  test    r15, r15
0x14001d9bb  jz      loc_14001E048
0x14001d9c1  test    rdi, rdi
0x14001d9c4  jz      loc_14001E048
0x14001d9ca  mov     ecx, [rsp+148h+var_F0]
0x14001d9ce  mov     r8, r13
0x14001d9d1  mov     rdi, [rsp+148h+var_F8]
0x14001d9d6  neg     ecx
0x14001d9d8  mov     rbx, [rsp+148h+arg_28]
0x14001d9e0  mov     r9, rdi
0x14001d9e3  mov     rdx, [rsi+268h]
0x14001d9ea  mov     [rsp+148h+var_128], rbx
0x14001d9ef  call    SymCryptFdefModElementSetValueNegUint32
0x14001d9f4  mov     rdx, [rsi+268h]
0x14001d9fb  mov     r9, rdi
0x14001d9fe  mov     r8, r14
0x14001da01  mov     [rsp+148h+var_128], rbx
0x14001da06  mov     ecx, 1
0x14001da0b  call    SymCryptModElementSetValueUint32
0x14001da10  mov     rdx, [rsp+148h+var_B8]
0x14001da18  mov     r9, rdi
0x14001da1b  mov     rcx, [rsi+268h]
0x14001da22  mov     r8, rbp
0x14001da25  mov     [rsp+148h+var_128], rbx
0x14001da2a  call    SymCryptModSquare
0x14001da2f  mov     rcx, [rsi+268h]
0x14001da36  mov     r9, rbp
0x14001da39  mov     r8, r13
0x14001da3c  mov     [rsp+148h+var_120], rbx
0x14001da41  mov     rdx, rbp
0x14001da44  mov     [rsp+148h+var_128], rdi
0x14001da49  call    SymCryptModMul
0x14001da4e  mov     rcx, [rsi+268h]
0x14001da55  mov     r9, r14
0x14001da58  mov     r8, r14
0x14001da5b  mov     [rsp+148h+var_120], rbx
0x14001da60  mov     rdx, rbp
0x14001da63  mov     [rsp+148h+var_128], rdi
0x14001da68  call    SymCryptModAdd
0x14001da6d  mov     rcx, [rsi+268h]
0x14001da74  mov     r9, rbp
0x14001da77  mov     r8, r14
0x14001da7a  mov     [rsp+148h+var_120], rbx
0x14001da7f  mov     rdx, rbp
0x14001da82  mov     [rsp+148h+var_128], rdi
0x14001da87  call    SymCryptModMul
0x14001da8c  mov     r9, [rsi+268h]
0x14001da93  xor     r8d, r8d
0x14001da96  xor     ecx, ecx
0x14001da98  mov     edx, [r9+4]
0x14001da9c  shl     edx, 4
0x14001da9f  test    edx, edx
0x14001daa1  jz      short loc_14001DAAE
0x14001daa3  or      r8d, [rbp+rcx*4+0]
0x14001daa8  inc     ecx
0x14001daaa  cmp     ecx, edx
0x14001daac  jb      short loc_14001DAA3
0x14001daae  mov     edi, r8d
0x14001dab1  lea     rcx, [r9+80h]
0x14001dab8  neg     rdi
0x14001dabb  shr     rdi, 20h
0x14001dabf  mov     eax, edi
0x14001dac1  not     eax
0x14001dac3  mov     [rsp+148h+var_D8], eax
0x14001dac7  mov     rax, [rsp+148h+var_E8]
0x14001dacc  mov     r9d, [rax+4]
0x14001dad0  lea     rdx, [rax+20h]
0x14001dad4  mov     r8, rdx
0x14001dad7  mov     [rsp+148h+Src], rdx
0x14001dadf  mov     edx, 2
0x14001dae4  call    SymCryptFdefRawSubUint32
0x14001dae9  mov     r8, [rsp+148h+var_F8]
0x14001daee  mov     rdx, rbp
0x14001daf1  mov     rax, [rsp+148h+var_C8]
0x14001daf9  mov     r9d, [rsi+0Ch]
0x14001dafd  mov     rcx, [rsi+268h]
0x14001db04  mov     [rsp+148h+var_118], rbx
0x14001db09  mov     [rsp+148h+var_120], r8
0x14001db0e  mov     r8, [rsp+148h+var_E8]
0x14001db13  mov     [rsp+148h+var_128], rax
0x14001db18  call    SymCryptModExpWindowed
0x14001db1d  mov     rax, [rsp+148h+var_F8]
  ... truncated ...
```
