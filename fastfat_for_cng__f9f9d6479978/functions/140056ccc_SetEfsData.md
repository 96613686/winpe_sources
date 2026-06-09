# SetEfsData

- ea: `0x140056ccc`
- end: `0x1400576b8`
- name: `SetEfsData`
- size: `2540`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation`

## callers

- `0x14004eff0`

## callees

- `0x1400034f0`
- `0x14000363c`
- `0x1400040e4`
- `0x140004264`
- `0x140004554`
- `0x14000c212`
- `0x14004d720`
- `0x14004e610`
- `0x14004ea30`
- `0x14004ee40`
- `0x14004f910`
- `0x14005489c`
- `0x140054fd4`
- `0x14005584c`
- `0x140055a18`
- `0x14005693c`
- `0x140056ccc`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140056d82`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140056e0a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140056f60`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140057043`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005711c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140057199`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400571e9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005723d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400574bf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005754e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140057696`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400606e9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006075c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140056d82`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140056e0a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140056f60`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140057043`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005711c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140057199`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400571e9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005723d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400574bf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005754e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140057696`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400606e9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006075c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140056fa1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057136`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005714c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005720c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057255`
- `ntoskrnl!ExFreePoolWithTag` at `0x140056fa1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057136`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005714c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005720c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057255`
- `ksecdd!BCryptDestroyKey` at `0x140056f32`
- `ksecdd!BCryptDestroyKey` at `0x140057494`
- `ksecdd!BCryptDestroyKey` at `0x140056f32`
- `ksecdd!BCryptDestroyKey` at `0x140057494`

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
  unsigned int *v13; // rbx
  int EfsData; // esi
  unsigned int *KeyBlobBuffer; // rax
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
  __int64 v45; // rcx
  _BYTE *v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // r8
  _WORD *v49; // rdx
  int v50; // eax
  _QWORD *v51; // rax
  char *v52; // r13
  unsigned int *v53; // r14
  unsigned int v54; // eax
  char *v55; // rcx
  __int64 v56; // rax
  _BYTE *v57; // rcx
  __int64 v58; // rax
  _BYTE *v59; // rcx
  __int64 v60; // rax
  _DWORD *v61; // r14
  __int64 v62; // rcx
  _DWORD *v63; // rcx
  _DWORD *v64; // rcx
  __int64 v65; // rax
  _BYTE *v66; // rcx
  __int64 v67; // [rsp+0h] [rbp-D8h] BYREF
  int v68; // [rsp+40h] [rbp-98h] BYREF
  int v69; // [rsp+44h] [rbp-94h] BYREF
  unsigned int v70; // [rsp+48h] [rbp-90h] BYREF
  _WORD *v71; // [rsp+50h] [rbp-88h] BYREF
  unsigned int *v72; // [rsp+58h] [rbp-80h]
  unsigned int Size; // [rsp+60h] [rbp-78h] BYREF
  unsigned int Size_4; // [rsp+64h] [rbp-74h]
  __int64 v75; // [rsp+68h] [rbp-70h]
  PVOID P; // [rsp+70h] [rbp-68h] BYREF
  __int64 v77; // [rsp+78h] [rbp-60h] BYREF
  __int64 v78; // [rsp+80h] [rbp-58h]
  _DWORD *v79; // [rsp+88h] [rbp-50h]
  __int64 v80; // [rsp+90h] [rbp-48h]
  __int64 *v81; // [rsp+98h] [rbp-40h]
  unsigned int **v82; // [rsp+E0h] [rbp+8h] BYREF
  int v83; // [rsp+E8h] [rbp+10h]
  int v84; // [rsp+F0h] [rbp+18h]
  __int64 v85; // [rsp+F8h] [rbp+20h]

  v85 = a4;
  v84 = a3;
  v83 = a2;
  v81 = &v67;
  v11 = a2;
  LOBYTE(v82) = 0;
  v13 = 0;
  v72 = 0;
  EfsData = 0;
  v71 = 0;
  v77 = 0;
  v70 = 0;
  P = 0;
  Size = 0;
  v69 = 0;
  v75 = 0;
  v68 = 0;
  v68 = *a9;
  if ( (*(_DWORD *)(a1 + 8) & 2) == 0 )
    goto LABEL_32;
  KeyBlobBuffer = (unsigned int *)GetKeyBlobBufferEx(
                                    *(unsigned int *)(*(_QWORD *)(a1 + 24) + 4LL),
                                    *(unsigned int *)(*(_QWORD *)(a1 + 24) + 8LL));
  v13 = KeyBlobBuffer;
  if ( !KeyBlobBuffer )
    return 3221225626LL;
  if ( !SetKeyTable(KeyBlobBuffer, &v68, *(unsigned int **)(a1 + 24)) )
  {
    ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v13 + 9), v13);
    v17 = 3449;
LABEL_5:
    v18 = -1073741790;
LABEL_6:
    EfspTraceLogAssert(v16, 6, v17);
    return v18;
  }
  v72 = v13;
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
  EfsData = EfsSameContext(v13, *v21, &v82, 0);
  v22 = *v13 - 87LL;
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
    EfspTraceLogAssert(v16, 6, 3463);
    return (unsigned int)EfsData;
  }
  if ( !(_BYTE)v82 )
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
  v72 = 0;
  v24 = (__int64)a6;
  if ( !a6 )
    goto LABEL_33;
  v25 = *a6;
  if ( !*a6 || v21[1] )
    goto LABEL_33;
  v26 = v25 + 16;
  v78 = v25 + 16;
  *(_QWORD *)(v25 + 40) = *v21 + 20;
  *(_DWORD *)(v25 + 48) = **v21;
  *(_QWORD *)(v25 + 56) = *((_QWORD *)*v21 + 7);
  *(_QWORD *)(v25 + 64) = *((_QWORD *)*v21 + 8);
  *(_DWORD *)(v25 + 72) = 512;
  *(_DWORD *)(v25 + 76) = (*v21)[1];
  *(_DWORD *)(v25 + 80) = (*v21)[6];
  *(_QWORD *)(v25 + 32) = v25 + 40;
  v82 = *(unsigned int ***)v24;
  v27 = *v82;
  if ( *v82 )
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
    *v82 = 0;
    v26 = v78;
  }
  **(_QWORD **)v24 = *v21;
  *(_QWORD *)(*(_QWORD *)v24 + 8LL) = v26;
  v20 = a11;
  ExFreePoolWithTag(*a11, 0x6D736645u);
  *v20 = *(PVOID *)v24;
  *(_QWORD *)v24 = 0;
  v11 = v83;
LABEL_34:
  v32 = *(unsigned int *)(a1 + 8);
  if ( (*(_DWORD *)(a1 + 8) & 1) == 0 && (v32 & 8) == 0 )
    goto LABEL_102;
  if ( (*(_DWORD *)(a1 + 8) & 1) != 0 )
  {
    if ( (*(_DWORD *)(a1 + 12) & 2) == 0 )
      EfspTraceLogAssert(v32, 6, 3548);
    if ( (v11 & 1) != 0 )
    {
      if ( v13 )
      {
        v33 = *v13 - 87LL;
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
  if ( (v84 & 2) == 0 )
    goto LABEL_84;
  v35 = v85;
  EfsData = EfsReadEfsData(v85, a5, 0, (unsigned int)&P, (__int64)&Size, (__int64)&v69);
  Size_4 = EfsData;
  if ( EfsData < 0 || v69 != 512 && v69 != 0x10000 )
  {
    if ( v13 )
    {
      v43 = *v13 - 87LL;
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
    if ( v69 == 2048 )
    {
      return (unsigned int)-1073741670;
    }
    else if ( EfsData >= 0 )
    {
      return (unsigned int)-1073741808;
    }
    return (unsigned int)EfsData;
  }
  if ( v69 == 0x10000 )
  {
    v36 = P;
    EfsData = EfsGetEfsStreamInfo(P, Size, 8);
    if ( EfsData < 0 )
    {
      if ( v13 )
      {
        v37 = *v13 - 87LL;
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
    if ( (_DWORD)v75 == 1 && (v75 & 0x300000000LL) != 0 )
    {
      if ( (*(_DWORD *)(a1 + 8) & 1) != 0 )
      {
        if ( v13 )
        {
          v39 = *v13 - 87LL;
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
      if ( (v75 & 0x200000000LL) != 0 )
      {
        *a10 = 1;
        if ( v13 )
        {
          v41 = *v13 - 87LL;
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
    v35 = v85;
    goto LABEL_85;
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
LABEL_85:
  if ( (*(_DWORD *)(a1 + 8) & 1) == 0 )
    goto LABEL_102;
  EfsData = EfspGetEfsStreamForWrite(*(_QWORD *)(a1 + 16), **(unsigned int **)(a1 + 16), &v77, &v70);
  if ( EfsData < 0 )
  {
    if ( !v13 )
      return (unsigned int)EfsData;
    v45 = *v13 - 87LL;
    v46 = v13 + 20;
    if ( *v13 != 87 )
    {
      do
      {
        *v46++ = 0;
        --v45;
      }
      while ( v45 );
    }
LABEL_139:
    ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v13 + 9), v13);
    return (unsigned int)EfsData;
  }
  EfsData = NtOfsCreateAttributeEx(a5, v35, &DestinationString, 1, 1, (__int64)&v71);
  Size_4 = EfsData;
  if ( EfsData == -1073741808 )
    EfspTraceLogAssert(v47, 6, 3722);
  if ( EfsData >= 0 )
  {
    NtOfsSetLength(a5);
    NtOfsPutData(a5, v71, v48, v70, v77);
    v49 = v71;
    if ( !v71 || (unsigned __int16)(*v71 - 1795) > 2u )
    {
      NtOfsFlushAttribute();
      v49 = v71;
    }
    if ( *v20 && (*(_DWORD *)(a1 + 8) & 2) == 0 )
    {
      LOBYTE(v49) = a7;
      EfsCleanup(v20, v49, a8);
      v49 = v71;
    }
    if ( v49 )
      NtOfsCloseAttribute(a5);
LABEL_102:
    if ( !v13 || (*(_DWORD *)(a1 + 8) & 2) == 0 )
      return (unsigned int)EfsData;
    v50 = *(_DWORD *)(a1 + 4);
    if ( v50 != 1 || *v20 )
    {
      if ( v50 != 4 )
        return (unsigned int)EfsData;
      v61 = *v20;
      if ( *v20 )
      {
        v63 = *(_DWORD **)v61;
        if ( *v13 > **(_DWORD **)v61 )
        {
          EfsData = -1073740974;
          EfspTraceLogAssert(v63, 6, 3954);
        }
        else
        {
          EfsData = EfspCopyEfsKeyBlob(v63, v13);
          if ( EfsData >= 0 )
          {
            v61[4] = 87119;
            *((_QWORD *)v61 + 3) = 0;
            v64 = *(_DWORD **)v61;
            *((_QWORD *)v61 + 5) = *(_QWORD *)v61 + 80LL;
            v61[12] = *v64;
            *((_QWORD *)v61 + 7) = *((_QWORD *)v64 + 7);
            *((_QWORD *)v61 + 8) = *((_QWORD *)v64 + 8);
            v61[18] = 512;
            v61[19] = v64[1];
            v61[20] = v64[6];
            *((_QWORD *)v61 + 4) = v61 + 10;
            *((_QWORD *)v61 + 1) = v61 + 4;
            *a9 = v68;
          }
        }
        v65 = *v13 - 87LL;
        v66 = v13 + 20;
        if ( *v13 != 87 )
        {
          do
          {
            *v66++ = 0;
            --v65;
          }
          while ( v65 );
        }
        goto LABEL_139;
      }
      v62 = AllocateAndSetContextDataBlock(v13);
      if ( v62 )
      {
        *a9 = v68;
        *v20 = (PVOID)v62;
        return (unsigned int)EfsData;
      }
    }
    else
    {
      if ( v24 )
      {
        v51 = *(_QWORD **)v24;
        if ( *(_QWORD *)v24 )
        {
          v52 = (char *)(v51 + 2);
          v51[5] = v13 + 20;
          *((_DWORD *)v51 + 12) = *v13;
          v51[7] = *((_QWORD *)v13 + 7);
          v51[8] = *((_QWORD *)v13 + 8);
          *((_DWORD *)v51 + 18) = 512;
          *((_DWORD *)v51 + 19) = v13[1];
          *((_DWORD *)v51 + 20) = v13[6];
          v51[4] = v51 + 5;
          v82 = *(unsigned int ***)v24;
          v53 = *v82;
          if ( *v82 )
          {
            v54 = v53[1];
            if ( (v54 == 26126 || v54 == 26128 || v54 == 536897040 || v54 == 1073767952) && v53[20] == 1 )
            {
              v55 = (char *)*((_QWORD *)v53 + 11);
              if ( (unsigned __int64)(v55 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
                BCryptDestroyKey(v55);
            }
            v56 = *v53 - 87LL;
            v57 = v53 + 20;
            if ( *v53 != 87 )
            {
              do
              {
                *v57++ = 0;
                --v56;
              }
              while ( v56 );
            }
            ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v53 + 9), v53);
            *v82 = 0;
          }
          **(_QWORD **)v24 = v13;
          *(_QWORD *)(*(_QWORD *)v24 + 8LL) = v52;
          *a9 = v68;
          *v20 = *(PVOID *)v24;
          *(_QWORD *)v24 = 0;
          return (unsigned int)EfsData;
        }
      }
      v60 = AllocateAndSetContextDataBlock(v13);
      if ( v60 )
      {
        *a9 = v68;
        *v20 = (PVOID)v60;
        return (unsigned int)EfsData;
      }
    }
    return 3221225626LL;
  }
  if ( v13 )
  {
    v58 = *v13 - 87LL;
    v80 = v58;
    v59 = v13 + 20;
    v79 = v13 + 20;
    while ( v58 )
    {
      *v59++ = 0;
      v79 = v59;
      v80 = --v58;
    }
    ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v13 + 9), v13);
    v72 = 0;
  }
  local_unwind_0(v81, &loc_140057578);
  return Size_4;
}

```

## disassembly

```asm
0x140056ccc  mov     rax, rsp
0x140056ccf  mov     [rax+20h], r9
0x140056cd3  mov     [rax+18h], r8d
0x140056cd7  mov     [rax+10h], edx
0x140056cda  push    rbx
0x140056cdb  push    rsi
0x140056cdc  push    rdi
0x140056cdd  push    r12
0x140056cdf  push    r13
0x140056ce1  push    r14
0x140056ce3  push    r15
0x140056ce5  sub     rsp, 0A0h
0x140056cec  mov     [rsp+0D8h+var_40], rsp
0x140056cf4  mov     r14d, edx
0x140056cf7  mov     r13, rcx
0x140056cfa  xor     r9d, r9d
0x140056cfd  mov     [rax+8], r9b
0x140056d01  mov     ebx, r9d
0x140056d04  mov     [rax-80h], rbx
0x140056d08  mov     esi, r9d
0x140056d0b  mov     [rsp+0D8h+var_88], r9
0x140056d10  mov     [rax-60h], r9
0x140056d14  mov     [rsp+0D8h+var_90], r9d
0x140056d19  mov     [rax-68h], r9
0x140056d1d  mov     [rax-78h], r9d
0x140056d21  mov     [rsp+0D8h+var_94], r9d
0x140056d26  mov     [rax-70h], r9
0x140056d2a  mov     [rsp+0D8h+var_98], r9d
0x140056d2f  mov     rax, [rsp+0D8h+arg_40]
0x140056d37  mov     eax, [rax]
0x140056d39  mov     [rsp+0D8h+var_98], eax
0x140056d3d  mov     eax, [rcx+8]
0x140056d40  test    al, 2
0x140056d42  jz      loc_140056FCE
0x140056d48  mov     rcx, [rcx+18h]
0x140056d4c  mov     edx, [rcx+8]
0x140056d4f  mov     ecx, [rcx+4]
0x140056d52  call    GetKeyBlobBufferEx
0x140056d57  mov     rbx, rax
0x140056d5a  test    rax, rax
0x140056d5d  jz      loc_1400575C7
0x140056d63  mov     r8, [r13+18h]
0x140056d67  lea     rdx, [rsp+0D8h+var_98]
0x140056d6c  mov     rcx, rax
0x140056d6f  call    SetKeyTable
0x140056d74  xor     r9d, r9d
0x140056d77  test    al, al
0x140056d79  jnz     short loc_140056DAD
0x140056d7b  mov     rdx, rbx; Entry
0x140056d7e  mov     rcx, [rbx+48h]; Lookaside
0x140056d82  call    cs:__imp_ExFreeToNPagedLookasideList
0x140056d89  nop     dword ptr [rax+rax+00h]
0x140056d8e  mov     r8d, 0D79h
0x140056d94  mov     ebx, 0C0000022h
0x140056d99  mov     r9d, ebx
0x140056d9c  mov     edx, 6
0x140056da1  call    EfspTraceLogAssert
0x140056da6  mov     eax, ebx
0x140056da8  jmp     loc_1400576A4
0x140056dad  mov     [rsp+0D8h+var_80], rbx
0x140056db2  mov     edi, 1
0x140056db7  mov     r12, [rsp+0D8h+arg_50]
0x140056dbf  cmp     [r13+4], edi
0x140056dc3  jnz     loc_140056FC4
0x140056dc9  mov     r12, [r12]
0x140056dcd  test    r12, r12
0x140056dd0  jz      loc_140056FD3
0x140056dd6  lea     r8, [rsp+0D8h+arg_0]
0x140056dde  mov     rdx, [r12]
0x140056de2  mov     rcx, rbx
0x140056de5  call    EfsSameContext
0x140056dea  mov     esi, eax
0x140056dec  mov     eax, [rbx]
0x140056dee  sub     rax, 57h ; 'W'
0x140056df2  lea     rcx, [rbx+50h]
0x140056df6  jz      short loc_140056E03
0x140056df8  mov     byte ptr [rcx], 0
0x140056dfb  add     rcx, rdi
0x140056dfe  sub     rax, rdi
0x140056e01  jnz     short loc_140056DF8
0x140056e03  mov     rdx, rbx; Entry
0x140056e06  mov     rcx, [rbx+48h]; Lookaside
0x140056e0a  call    cs:__imp_ExFreeToNPagedLookasideList
0x140056e11  nop     dword ptr [rax+rax+00h]
0x140056e16  xor     r9d, r9d
0x140056e19  test    esi, esi
0x140056e1b  jns     short loc_140056E35
0x140056e1d  mov     r9d, esi
0x140056e20  mov     edx, 6
0x140056e25  mov     r8d, 0D87h
0x140056e2b  call    EfspTraceLogAssert
0x140056e30  jmp     loc_1400576A2
0x140056e35  cmp     byte ptr [rsp+0D8h+arg_0], r9b
0x140056e3d  jnz     short loc_140056E5C
0x140056e3f  mov     eax, [r13+8]
0x140056e43  test    dil, al
0x140056e46  jz      loc_1400571F5
0x140056e4c  mov     ebx, 0C000000Dh
0x140056e51  mov     r8d, 0D9Ah
0x140056e57  jmp     loc_140056D99
0x140056e5c  mov     rbx, r9
0x140056e5f  mov     [rsp+0D8h+var_80], rbx
0x140056e64  mov     r15, [rsp+0D8h+arg_28]
0x140056e6c  test    r15, r15
0x140056e6f  jz      loc_140056FDB
0x140056e75  mov     rax, [r15]
0x140056e78  test    rax, rax
0x140056e7b  jz      loc_140056FDB
0x140056e81  cmp     [r12+8], r9
0x140056e86  jnz     loc_140056FDB
0x140056e8c  lea     r8, [rax+10h]
0x140056e90  mov     [rsp+0D8h+var_58], r8
0x140056e98  lea     rdx, [r8+18h]
0x140056e9c  mov     rax, [r12]
0x140056ea0  add     rax, 50h ; 'P'
0x140056ea4  mov     [rdx], rax
0x140056ea7  mov     rax, [r12]
0x140056eab  mov     ecx, [rax]
0x140056ead  mov     [rdx+8], ecx
0x140056eb0  mov     rax, [r12]
0x140056eb4  mov     rcx, [rax+38h]
0x140056eb8  mov     [rdx+10h], rcx
0x140056ebc  mov     rax, [r12]
0x140056ec0  mov     rcx, [rax+40h]
0x140056ec4  mov     [rdx+18h], rcx
0x140056ec8  mov     dword ptr [rdx+20h], 200h
0x140056ecf  mov     rax, [r12]
0x140056ed3  mov     ecx, [rax+4]
0x140056ed6  mov     [rdx+24h], ecx
0x140056ed9  mov     rax, [r12]
0x140056edd  mov     ecx, [rax+18h]
0x140056ee0  mov     [rdx+28h], ecx
0x140056ee3  mov     [r8+10h], rdx
0x140056ee7  mov     rax, [r15]
0x140056eea  mov     [rsp+0D8h+arg_0], rax
0x140056ef2  mov     r14, [rax]
0x140056ef5  test    r14, r14
0x140056ef8  jz      loc_140056F7F
0x140056efe  mov     eax, [r14+4]
0x140056f02  cmp     eax, 660Eh
0x140056f07  jz      short loc_140056F1E
0x140056f09  cmp     eax, 6610h
0x140056f0e  jz      short loc_140056F1E
0x140056f10  cmp     eax, 20006610h
0x140056f15  jz      short loc_140056F1E
0x140056f17  cmp     eax, 40006610h
0x140056f1c  jnz     short loc_140056F41
0x140056f1e  cmp     [r14+50h], edi
0x140056f22  jnz     short loc_140056F41
0x140056f24  mov     rcx, [r14+58h]; hKey
0x140056f28  lea     rax, [rcx-1]
0x140056f2c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140056f30  ja      short loc_140056F41
0x140056f32  call    cs:__imp_BCryptDestroyKey
0x140056f39  nop     dword ptr [rax+rax+00h]
0x140056f3e  xor     r9d, r9d
0x140056f41  mov     eax, [r14]
0x140056f44  sub     rax, 57h ; 'W'
0x140056f48  lea     rcx, [r14+50h]
0x140056f4c  jz      short loc_140056F59
0x140056f4e  mov     [rcx], r9b
0x140056f51  add     rcx, rdi
0x140056f54  sub     rax, rdi
0x140056f57  jnz     short loc_140056F4E
0x140056f59  mov     rdx, r14; Entry
0x140056f5c  mov     rcx, [r14+48h]; Lookaside
0x140056f60  call    cs:__imp_ExFreeToNPagedLookasideList
0x140056f67  nop     dword ptr [rax+rax+00h]
0x140056f6c  mov     rax, [rsp+0D8h+arg_0]
0x140056f74  mov     [rax], rbx
0x140056f77  mov     r8, [rsp+0D8h+var_58]
0x140056f7f  mov     rcx, [r15]
0x140056f82  mov     rax, [r12]
0x140056f86  mov     [rcx], rax
0x140056f89  mov     rax, [r15]
0x140056f8c  mov     [rax+8], r8
0x140056f90  mov     edx, 6D736645h; Tag
0x140056f95  mov     r12, [rsp+0D8h+arg_50]
0x140056f9d  mov     rcx, [r12]; P
0x140056fa1  call    cs:__imp_ExFreePoolWithTag
0x140056fa8  nop     dword ptr [rax+rax+00h]
0x140056fad  mov     rax, [r15]
0x140056fb0  mov     [r12], rax
0x140056fb4  xor     r9d, r9d
0x140056fb7  mov     [r15], r9
0x140056fba  mov     r14d, [rsp+0D8h+arg_8]
0x140056fc2  jmp     short loc_140056FE3
0x140056fc4  mov     r15, [rsp+0D8h+arg_28]
0x140056fcc  jmp     short loc_140056FE3
0x140056fce  mov     edi, 1
0x140056fd3  mov     r15, [rsp+0D8h+arg_28]
0x140056fdb  mov     r12, [rsp+0D8h+arg_50]
0x140056fe3  mov     ecx, [r13+8]
0x140056fe7  mov     eax, ecx
0x140056fe9  and     eax, edi
0x140056feb  jnz     short loc_140056FF6
0x140056fed  test    cl, 8
0x140056ff0  jz      loc_1400573D1
0x140056ff6  test    eax, eax
0x140056ff8  jz      short loc_140057059
0x140056ffa  mov     eax, [r13+0Ch]
0x140056ffe  test    al, 2
0x140057000  jnz     short loc_14005701B
0x140057002  mov     edx, 6
0x140057007  mov     r9d, 0C0000001h
0x14005700d  mov     r8d, 0DDCh
0x140057013  call    EfspTraceLogAssert
0x140057018  xor     r9d, r9d
0x14005701b  test    dil, r14b
0x14005701e  jz      short loc_140057059
0x140057020  test    rbx, rbx
0x140057023  jz      short loc_14005704F
0x140057025  mov     eax, [rbx]
0x140057027  sub     rax, 57h ; 'W'
0x14005702b  lea     rcx, [rbx+50h]
0x14005702f  jz      short loc_14005703C
0x140057031  mov     [rcx], r9b
0x140057034  add     rcx, rdi
0x140057037  sub     rax, rdi
0x14005703a  jnz     short loc_140057031
0x14005703c  mov     rdx, rbx; Entry
0x14005703f  mov     rcx, [rbx+48h]; Lookaside
0x140057043  call    cs:__imp_ExFreeToNPagedLookasideList
0x14005704a  nop     dword ptr [rax+rax+00h]
0x14005704f  mov     eax, 0C00000A2h
0x140057054  jmp     loc_1400576A4
0x140057059  test    byte ptr [rsp+0D8h+arg_10], 2
0x140057061  jz      loc_140057286
0x140057067  lea     rax, [rsp+0D8h+var_94]
0x14005706c  mov     [rsp+0D8h+var_B0], rax
0x140057071  lea     rax, [rsp+0D8h+Size]
0x140057076  mov     qword ptr [rsp+0D8h+var_B8], rax
0x14005707b  lea     r9, [rsp+0D8h+P]
0x140057080  xor     r8d, r8d
0x140057083  mov     rdx, [rsp+0D8h+arg_20]
0x14005708b  mov     r14, [rsp+0D8h+arg_18]
0x140057093  mov     rcx, r14
0x140057096  call    EfsReadEfsData
0x14005709b  mov     esi, eax
0x14005709d  mov     dword ptr [rsp+0D8h+Size+4], eax
0x1400570a1  test    esi, esi
0x1400570a3  js      loc_14005721A
0x1400570a9  cmp     [rsp+0D8h+var_94], 200h
0x1400570b1  jz      short loc_1400570C1
0x1400570b3  cmp     [rsp+0D8h+var_94], 10000h
0x1400570bb  jnz     loc_14005721A
0x1400570c1  cmp     [rsp+0D8h+var_94], 10000h
0x1400570c9  jnz     loc_1400571FC
0x1400570cf  mov     [rsp+0D8h+var_B8], 8; int
0x1400570d7  lea     r9, [rsp+0D8h+var_70]
0x1400570dc  mov     r8d, 0Bh
0x1400570e2  mov     edx, dword ptr [rsp+0D8h+Size]; Size
0x1400570e6  mov     r14, [rsp+0D8h+P]
0x1400570eb  mov     rcx, r14; Src
0x1400570ee  call    EfsGetEfsStreamInfo
0x1400570f3  mov     esi, eax
0x1400570f5  test    eax, eax
0x1400570f7  jns     short loc_140057147
0x1400570f9  test    rbx, rbx
0x1400570fc  jz      short loc_140057128
0x1400570fe  mov     eax, [rbx]
0x140057100  sub     rax, 57h ; 'W'
0x140057104  lea     rdx, [rbx+50h]
0x140057108  jz      short loc_140057115
0x14005710a  mov     byte ptr [rdx], 0
0x14005710d  add     rdx, rdi
0x140057110  sub     rax, rdi
0x140057113  jnz     short loc_14005710A
0x140057115  mov     rdx, rbx; Entry
0x140057118  mov     rcx, [rbx+48h]; Lookaside
0x14005711c  call    cs:__imp_ExFreeToNPagedLookasideList
0x140057123  nop     dword ptr [rax+rax+00h]
0x140057128  test    r14, r14
0x14005712b  jz      loc_1400576A2
0x140057131  xor     edx, edx; Tag
0x140057133  mov     rcx, r14; P
0x140057136  call    cs:__imp_ExFreePoolWithTag
0x14005713d  nop     dword ptr [rax+rax+00h]
0x140057142  jmp     loc_1400576A2
0x140057147  xor     edx, edx; Tag
0x140057149  mov     rcx, r14; P
0x14005714c  call    cs:__imp_ExFreePoolWithTag
0x140057153  nop     dword ptr [rax+rax+00h]
0x140057158  cmp     [rsp+0D8h+var_70], edi
0x14005715c  jnz     loc_140057286
0x140057162  test    [rsp+0D8h+var_6C], 3
0x140057167  jz      loc_140057286
0x14005716d  mov     eax, [r13+8]
0x140057171  test    dil, al
0x140057174  jz      short loc_1400571B0
0x140057176  test    rbx, rbx
0x140057179  jz      short loc_1400571A5
0x14005717b  mov     eax, [rbx]
0x14005717d  sub     rax, 57h ; 'W'
0x140057181  lea     rcx, [rbx+50h]
0x140057185  jz      short loc_140057192
0x140057187  mov     byte ptr [rcx], 0
0x14005718a  add     rcx, rdi
0x14005718d  sub     rax, rdi
0x140057190  jnz     short loc_140057187
  ... truncated ...
```
