# AddUndoForSliceFastPath

- ea: `0x140019740`
- end: `0x14001a0b4`
- name: `AddUndoForSliceFastPath`
- size: `2420`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140017c30`

## callees

- `0x140019740`
- `0x14001a0c0`
- `0x140024d20`
- `0x1400c4acc`
- `0x1400c8574`
- `0x1401e9ce0`
- `0x1401e9e40`
- `0x1401ea140`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x140019f3d`
- `ntoskrnl!KdDebuggerEnabled` at `0x140019f8b`
- `ntoskrnl!KdDebuggerEnabled` at `0x140019fbc`
- `ntoskrnl!KdDebuggerEnabled` at `0x140019fd2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001a00e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001a056`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001a00e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001a056`
- `ntoskrnl!ExAllocatePool2` at `0x14001985a`
- `ntoskrnl!ExAllocatePool2` at `0x1400198da`
- `ntoskrnl!ExAllocatePool2` at `0x14001985a`
- `ntoskrnl!ExAllocatePool2` at `0x1400198da`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001981b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001989a`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001981b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001989a`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401eebea`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401eebfc`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401eebea`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401eebfc`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14001a02b`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14001a073`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14001a02b`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14001a073`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140019c19`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140019d54`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140019c19`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140019d54`

## string_xrefs

- `0x1401eec0e`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall AddUndoForSliceFastPath(__int64 a1, __int64 a2, unsigned __int64 a3, unsigned int *a4, __int64 a5)
{
  __int64 v5; // rdi
  unsigned __int64 v7; // rdx
  unsigned int v8; // r15d
  __int64 *v10; // r14
  __int64 v11; // rbp
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rdx
  __int64 i; // rsi
  __int64 v15; // rcx
  unsigned int v16; // esi
  unsigned int v17; // esi
  unsigned __int64 v18; // rbx
  unsigned int *v19; // rdi
  unsigned __int64 v20; // rdx
  __int64 v21; // rax
  _DWORD *v22; // rbx
  unsigned __int64 v23; // rdi
  unsigned int *v24; // rbp
  unsigned __int64 v25; // rdx
  __int64 Pool2; // rax
  struct SmsUndoRecord **v27; // rdx
  _QWORD *v28; // rdi
  __int64 v29; // rcx
  int v30; // edx
  __int64 v31; // rcx
  int v32; // edx
  __int64 v33; // rcx
  int v34; // edx
  int v35; // ecx
  int v36; // ecx
  __int64 v37; // r9
  unsigned __int64 v38; // r8
  __int64 v39; // r9
  unsigned __int64 v40; // r8
  __int64 v41; // r9
  unsigned __int64 v42; // r8
  unsigned int v43; // r12d
  unsigned int *v44; // rdi
  unsigned int v45; // eax
  __int64 v46; // rsi
  __int64 v47; // rdx
  __int64 v48; // r8
  int v49; // r9d
  __int64 v50; // r10
  int v51; // r11d
  __int64 v52; // rax
  unsigned int v53; // eax
  unsigned int *v54; // rcx
  __int64 v55; // rbp
  __int64 v56; // r12
  struct SmsUndoRecord *v57; // rbx
  const void *v58; // rsi
  __int64 v59; // rdi
  __int64 v60; // rdx
  __int64 v61; // r8
  int v62; // r9d
  __int64 v63; // r10
  int v64; // r11d
  __int64 v65; // rax
  unsigned int v66; // eax
  void *v67; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v69; // rcx
  _QWORD *v70; // rax
  struct _NPAGED_LOOKASIDE_LIST *v71; // rcx
  _DWORD *v72; // rax
  unsigned int v73; // [rsp+20h] [rbp-B8h]
  __int64 *v75; // [rsp+38h] [rbp-A0h]
  struct SmsUndoRecord *v76[2]; // [rsp+70h] [rbp-68h] BYREF
  struct SmsUndoRecord *v77[2]; // [rsp+80h] [rbp-58h]

  v5 = 0;
  v75 = (__int64 *)a3;
  v7 = *((_QWORD *)a4 + 1);
  v8 = 0;
  v73 = 0;
  v10 = (__int64 *)a3;
  v11 = a1;
  *(_OWORD *)v76 = 0;
  *(_OWORD *)v77 = 0;
  if ( v7 )
  {
    if ( (*(_DWORD *)(*(_QWORD *)(a1 + 24) + 44LL) & 4) == 0 || *(_BYTE *)(*(_QWORD *)(a3 + 8) + 12LL) )
    {
      v29 = a4[4];
      if ( (_DWORD)v29 && (a3 = *((_QWORD *)a4 + 3), v7 >= a3) && v7 <= a3 + v29 )
      {
        v30 = 0;
      }
      else
      {
        v37 = *a4;
        if ( (_DWORD)v37 && (_DWORD)v29 && (v38 = *((_QWORD *)a4 + 3), v7 + v37 >= v38) && v7 + v37 <= v38 + v29 )
          a3 = (unsigned int)(v38 - v7);
        else
          a3 = (unsigned __int16)(v37 + 7) & 0xFFF8;
        v30 = (unsigned __int16)a3;
      }
      if ( v30 + (((_DWORD)v29 + 7) & 0xFFFFFFF8) + 16 )
        v8 = v30 + ((v29 + 7) & 0xFFFFFFF8) + 16;
    }
    else if ( ((a4[4] + 7) & 0xFFFFFFF8) != 0 )
    {
      v8 = (a4[4] + 7) & 0xFFFFFFF8;
    }
  }
  v12 = *((_QWORD *)a4 + 5);
  if ( v12 )
  {
    if ( (*(_DWORD *)(*(_QWORD *)(v11 + 24) + 44LL) & 4) == 0 || *(_BYTE *)(v10[1] + 12) )
    {
      v31 = a4[12];
      if ( (_DWORD)v31 && (a3 = *((_QWORD *)a4 + 7), v12 >= a3) && v12 <= a3 + v31 )
      {
        v32 = 0;
      }
      else
      {
        v39 = a4[8];
        if ( (_DWORD)v39 && (_DWORD)v31 && (v40 = *((_QWORD *)a4 + 7), v12 + v39 >= v40) && v12 + v39 <= v40 + v31 )
          a3 = (unsigned int)(v40 - v12);
        else
          a3 = (unsigned __int16)(v39 + 7) & 0xFFF8;
        v32 = (unsigned __int16)a3;
      }
      if ( v32 + (((_DWORD)v31 + 7) & 0xFFFFFFF8) + 16 > v8 )
        v8 = v32 + ((v31 + 7) & 0xFFFFFFF8) + 16;
    }
    else if ( ((a4[12] + 7) & 0xFFFFFFF8) > v8 )
    {
      v8 = (a4[12] + 7) & 0xFFFFFFF8;
    }
  }
  v13 = *((_QWORD *)a4 + 9);
  if ( v13 )
  {
    if ( (*(_DWORD *)(*(_QWORD *)(v11 + 24) + 44LL) & 4) == 0 || *(_BYTE *)(v10[1] + 12) )
    {
      v33 = a4[20];
      if ( (_DWORD)v33 && (a3 = *((_QWORD *)a4 + 11), v13 >= a3) && v13 <= a3 + v33 )
      {
        v34 = 0;
      }
      else
      {
        v41 = a4[16];
        if ( (_DWORD)v41 && (_DWORD)v33 && (v42 = *((_QWORD *)a4 + 11), v13 + v41 >= v42) && v13 + v41 <= v42 + v33 )
          a3 = (unsigned int)(v42 - v13);
        else
          a3 = (unsigned __int16)(v41 + 7) & 0xFFF8;
        v34 = (unsigned __int16)a3;
      }
      if ( v34 + (((_DWORD)v33 + 7) & 0xFFFFFFF8) + 16 > v8 )
        v8 = v34 + ((v33 + 7) & 0xFFFFFFF8) + 16;
    }
    else if ( ((a4[20] + 7) & 0xFFFFFFF8) > v8 )
    {
      v8 = (a4[20] + 7) & 0xFFFFFFF8;
    }
  }
  for ( i = 0; (unsigned int)i < 3; i = (unsigned int)(i + 1) )
  {
    if ( !*(_QWORD *)&a4[8 * (unsigned int)i + 2] )
      continue;
    if ( (*(_DWORD *)a2 & 0x1000LL) != 0 )
    {
      if ( (_BYTE)KdDebuggerEnabled )
        __debugbreak();
      LOBYTE(a3) = 1;
      CmsVolume::ChangeVolumeOptionDynamically(*(_QWORD *)(a2 + 8), 0x20000000, a3);
LABEL_142:
      v76[i] = 0;
LABEL_143:
      v43 = -1073741670;
      if ( v76[0] )
        CmsBPlusTable::FreeUndoRecord(v76[0], (struct CmsTransactionContext *)v27, a3);
      if ( v76[1] )
        CmsBPlusTable::FreeUndoRecord(v76[1], (struct CmsTransactionContext *)v27, a3);
      if ( v77[0] )
        CmsBPlusTable::FreeUndoRecord(v77[0], (struct CmsTransactionContext *)v27, a3);
      if ( v77[1] )
        CmsBPlusTable::FreeUndoRecord(v77[1], (struct CmsTransactionContext *)v27, a3);
      return v43;
    }
    v23 = ((v8 + 7) & 0xFFFFFFF8) + 88;
    v24 = (unsigned int *)(qword_140262410 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
    if ( v23 > *v24 )
    {
      v24 = 0;
      v25 = v23 + 16;
      goto LABEL_19;
    }
    if ( *((_BYTE *)v24 + 8) )
    {
      v69 = (struct _NPAGED_LOOKASIDE_LIST *)(v24 + 16);
      if ( *((_BYTE *)v24 + 9) )
        v70 = ExAllocateFromNPagedLookasideList(v69);
      else
        v70 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v69);
    }
    else
    {
      if ( (int)*((_QWORD *)v24 + 11) <= (int)HIDWORD(*((_QWORD *)v24 + 11)) )
        goto LABEL_50;
      v36 = _InterlockedDecrement((volatile signed __int32 *)v24 + 22);
      if ( v36 < (int)v24[23] || v36 < 0 )
      {
        _InterlockedIncrement((volatile signed __int32 *)v24 + 22);
LABEL_50:
        v25 = v24[1];
LABEL_19:
        Pool2 = ExAllocatePool2(66, v25, 1766871885);
        v28 = (_QWORD *)Pool2;
        if ( (Pool2 & 0xF) != 0 )
          goto LABEL_169;
        if ( !Pool2 )
          goto LABEL_134;
        goto LABEL_133;
      }
      v70 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v24 + 4);
    }
    v28 = v70;
    if ( !v70 )
      goto LABEL_50;
LABEL_133:
    *v28 = v24;
    v28 += 2;
LABEL_134:
    if ( !v28 )
      goto LABEL_142;
    v11 = a1;
    v28[5] = a1;
    *((_DWORD *)v28 + 4) = 31;
    *((_DWORD *)v28 + 3) = v8;
    *((_DWORD *)v28 + 2) = v8;
    *((_WORD *)v28 + 10) = 0;
    *((_OWORD *)v28 + 3) = 0;
    *((_OWORD *)v28 + 4) = 0;
    v28[10] = 0;
    *((_DWORD *)v28 + 8) = 0;
    if ( v8 )
    {
      v28[3] = v28 + 11;
      memset(v28 + 11, 0, v8);
    }
    else
    {
      v28[3] = 0;
    }
    v76[i] = (struct SmsUndoRecord *)v28;
    v5 = ++v73;
  }
  v15 = v10[2];
  if ( (*(_BYTE *)(v15 + 8) & 0x40) != 0 )
    v16 = (*(unsigned __int16 *)(v15 + 10) + 7) & 0xFFFFFFF8;
  else
    v16 = *(_DWORD *)v15;
  if ( (*(_DWORD *)a2 & 0x1000LL) != 0 )
  {
    if ( (_BYTE)KdDebuggerEnabled )
      __debugbreak();
    LOBYTE(a3) = 1;
    CmsVolume::ChangeVolumeOptionDynamically(*(_QWORD *)(a2 + 8), 0x20000000, a3);
    v27 = &v76[v5];
    goto LABEL_148;
  }
  v17 = 2 * v16;
  v18 = ((v17 + 7) & 0xFFFFFFF8) + 88;
  v19 = (unsigned int *)(qword_140262410 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
  if ( v18 > *v19 )
  {
    v19 = 0;
    v20 = v18 + 16;
    goto LABEL_13;
  }
  if ( *((_BYTE *)v19 + 8) )
  {
    v71 = (struct _NPAGED_LOOKASIDE_LIST *)(v19 + 16);
    if ( *((_BYTE *)v19 + 9) )
      v72 = ExAllocateFromNPagedLookasideList(v71);
    else
      v72 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v71);
LABEL_87:
    v22 = v72;
    if ( !v72 )
      goto LABEL_45;
    goto LABEL_88;
  }
  if ( (int)*((_QWORD *)v19 + 11) > (int)HIDWORD(*((_QWORD *)v19 + 11)) )
  {
    v35 = _InterlockedDecrement((volatile signed __int32 *)v19 + 22);
    if ( v35 >= (int)v19[23] && v35 >= 0 )
    {
      v72 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v19 + 4);
      goto LABEL_87;
    }
    _InterlockedIncrement((volatile signed __int32 *)v19 + 22);
  }
LABEL_45:
  v20 = v19[1];
LABEL_13:
  v21 = ExAllocatePool2(66, v20, 1766871885);
  v22 = (_DWORD *)v21;
  if ( (v21 & 0xF) != 0 )
LABEL_169:
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  if ( v21 )
  {
LABEL_88:
    *(_QWORD *)v22 = v19;
    v22 += 4;
  }
  if ( !v22 )
  {
    v27 = &v76[v73];
LABEL_148:
    *v27 = 0;
    goto LABEL_143;
  }
  v22[4] = 30;
  *((_QWORD *)v22 + 5) = v11;
  v22[3] = v17;
  v22[2] = v17;
  *((_WORD *)v22 + 10) = 0;
  *((_OWORD *)v22 + 3) = 0;
  *((_OWORD *)v22 + 4) = 0;
  *((_QWORD *)v22 + 10) = 0;
  v22[8] = 0;
  if ( v17 )
  {
    *((_QWORD *)v22 + 3) = v22 + 22;
    memset(v22 + 22, 0, v17);
  }
  else
  {
    *((_QWORD *)v22 + 3) = 0;
  }
  v43 = 0;
  v44 = (unsigned int *)v10[2];
  v76[v73] = (struct SmsUndoRecord *)v22;
  if ( (v44[2] & 0x40) != 0 )
    v45 = (*((unsigned __int16 *)v44 + 5) + 7) & 0xFFFFFFF8;
  else
    v45 = *v44;
  v22[2] = v45;
  v22[8] = 0;
  *((_QWORD *)v22 + 5) = v11;
  v46 = *v10;
  _InterlockedIncrement((volatile signed __int32 *)(*v10 + 380));
  if ( (unsigned __int8)ExIsFastResourceHeldExclusive(v46 + 560) )
    ++*(_DWORD *)(v46 + 384);
  else
    SmsPageLatch::AcquireShared((SmsPageLatch *)(v46 + 560), (struct CmsTransactionContext *)a2, 1);
  if ( *(char *)(*(_QWORD *)(v46 + 96) + 14LL) >= 0 )
    ++*(_DWORD *)(a2 + 196);
  ++*(_DWORD *)(v46 + 388);
  v47 = v10[1];
  v48 = v10[2];
  v49 = *((_DWORD *)v10 + 6);
  v50 = v10[4];
  v51 = *((_DWORD *)v10 + 7);
  if ( *((_QWORD *)v22 + 6) && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
  *((_QWORD *)v22 + 6) = *v10;
  *((_QWORD *)v22 + 7) = v47;
  *((_QWORD *)v22 + 8) = v48;
  v22[18] = v49;
  *((_QWORD *)v22 + 10) = v50;
  v22[19] = v51;
  v52 = *v10;
  if ( *v10 && (!*(_BYTE *)(v52 + 392) && *(_QWORD *)(v52 + 96) == a1 || !*(_BYTE *)(a1 + 212)) )
    *((_BYTE *)v22 + 20) |= 1u;
  v53 = v22[2];
  if ( v53 )
  {
    v54 = (unsigned int *)*((_QWORD *)v22 + 3);
    if ( v44 )
    {
      if ( v44 != v54 )
        memmove(v54, v44, v53);
    }
    else
    {
      memset(v54, 0, (unsigned int)v22[2]);
    }
  }
  v55 = 0;
  *(_QWORD *)v22 = *(_QWORD *)(a2 + 144);
  *(_QWORD *)(a2 + 144) = v22;
  if ( v73 )
  {
    do
    {
      v56 = 8 * v55;
      v57 = v76[v55];
      v58 = (const void *)*((_QWORD *)v57 + 3);
      *((_DWORD *)v57 + 2) = v8;
      *((_DWORD *)v57 + 8) = 0;
      *((_QWORD *)v57 + 5) = a1;
      v59 = *v10;
      _InterlockedIncrement((volatile signed __int32 *)(*v10 + 380));
      if ( (unsigned __int8)ExIsFastResourceHeldExclusive(v59 + 560) )
        ++*(_DWORD *)(v59 + 384);
      else
        SmsPageLatch::AcquireShared((SmsPageLatch *)(v59 + 560), (struct CmsTransactionContext *)a2, 1);
      if ( *(char *)(*(_QWORD *)(v59 + 96) + 14LL) >= 0 )
        ++*(_DWORD *)(a2 + 196);
      ++*(_DWORD *)(v59 + 388);
      v10 = v75;
      v60 = v75[1];
      v61 = v75[2];
      v62 = *((_DWORD *)v75 + 6);
      v63 = v75[4];
      v64 = *((_DWORD *)v75 + 7);
      if ( *((_QWORD *)v57 + 6) && (_BYTE)KdDebuggerEnabled )
        __debugbreak();
      *((_QWORD *)v57 + 6) = *v75;
      *((_QWORD *)v57 + 7) = v60;
      *((_QWORD *)v57 + 8) = v61;
      *((_DWORD *)v57 + 18) = v62;
      *((_QWORD *)v57 + 10) = v63;
      *((_DWORD *)v57 + 19) = v64;
      v65 = *v75;
      if ( *v75 && (!*(_BYTE *)(v65 + 392) && *(_QWORD *)(v65 + 96) == a1 || !*(_BYTE *)(a1 + 212)) )
        *((_BYTE *)v57 + 20) |= 1u;
      v66 = *((_DWORD *)v57 + 2);
      if ( v66 )
      {
        v67 = (void *)*((_QWORD *)v57 + 3);
        if ( v58 )
        {
          if ( v58 != v67 )
            memmove(v67, v58, v66);
        }
        else
        {
          memset(v67, 0, *((unsigned int *)v57 + 2));
        }
      }
      v55 = (unsigned int)(v55 + 1);
      *(_QWORD *)v57 = *(_QWORD *)(a2 + 144);
      *(_QWORD *)(a2 + 144) = v57;
      *(_QWORD *)(v56 + a5) = *((_QWORD *)v57 + 3);
    }
    while ( (unsigned int)v55 < v73 );
    return 0;
  }
  return v43;
}

```

## disassembly

```asm
0x140019740  mov     [rsp+arg_0], rbx
0x140019745  push    rbp
0x140019746  push    rsi
0x140019747  push    rdi
0x140019748  push    r12
0x14001974a  push    r13
0x14001974c  push    r14
0x14001974e  push    r15
0x140019750  sub     rsp, 0A0h
0x140019757  mov     rax, cs:__security_cookie
0x14001975e  xor     rax, rsp
0x140019761  mov     [rsp+0D8h+var_48], rax
0x140019769  mov     rax, [rsp+0D8h+arg_20]
0x140019771  xor     edi, edi
0x140019773  xorps   xmm0, xmm0
0x140019776  mov     [rsp+0D8h+var_A0], r8
0x14001977b  mov     r13, rdx
0x14001977e  mov     [rsp+0D8h+var_B0], rcx
0x140019783  mov     rdx, [r9+8]
0x140019787  xor     r15d, r15d
0x14001978a  mov     [rsp+0D8h+var_98], rax
0x14001978f  mov     rbx, r9
0x140019792  mov     [rsp+0D8h+var_B8], edi
0x140019796  mov     r14, r8
0x140019799  mov     rbp, rcx
0x14001979c  movups  xmmword ptr [rsp+0D8h+var_68], xmm0
0x1400197a1  movups  xmmword ptr [rsp+0D8h+var_58], xmm0
0x1400197a9  test    rdx, rdx
0x1400197ac  jnz     loc_1400198FF
0x1400197b2  mov     rdx, [rbx+28h]
0x1400197b6  test    rdx, rdx
0x1400197b9  jnz     loc_14001993C
0x1400197bf  mov     rdx, [rbx+48h]
0x1400197c3  test    rdx, rdx
0x1400197c6  jnz     loc_140019978
0x1400197cc  xor     esi, esi
0x1400197ce  mov     r12d, 0FFFFFFFFh
0x1400197d4  cmp     esi, 3
0x1400197d7  jnb     short loc_1400197EF
0x1400197d9  mov     eax, esi
0x1400197db  shl     rax, 5
0x1400197df  cmp     qword ptr [rax+rbx+8], 0
0x1400197e5  jnz     loc_14001987F
0x1400197eb  inc     esi
0x1400197ed  jmp     short loc_1400197D4
0x1400197ef  mov     rcx, [r14+10h]
0x1400197f3  test    byte ptr [rcx+8], 40h
0x1400197f7  jnz     loc_1400199C6
0x1400197fd  mov     esi, [rcx]
0x1400197ff  mov     eax, [r13+0]
0x140019803  bt      rax, 0Ch
0x140019808  jb      loc_140019F8B
0x14001980e  add     esi, esi
0x140019810  xor     ecx, ecx; ProcNumber
0x140019812  lea     ebx, [rsi+7]
0x140019815  and     ebx, 0FFFFFFF8h
0x140019818  add     ebx, 58h ; 'X'
0x14001981b  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140019822  nop     dword ptr [rax+rax+00h]
0x140019827  xor     edx, edx
0x140019829  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x14001982f  lea     rdi, [rdx+rdx*2]
0x140019833  shl     rdi, 6
0x140019837  add     rdi, cs:qword_140262410
0x14001983e  mov     eax, [rdi]
0x140019840  cmp     rbx, rax
0x140019843  jbe     loc_1400199D5
0x140019849  xor     edi, edi
0x14001984b  lea     rdx, [rbx+10h]
0x14001984f  mov     ecx, 42h ; 'B'
0x140019854  mov     r8d, 6950534Dh
0x14001985a  call    cs:__imp_ExAllocatePool2
0x140019861  nop     dword ptr [rax+rax+00h]
0x140019866  mov     rbx, rax
0x140019869  test    al, 0Fh
0x14001986b  jnz     loc_1401EEC0E
0x140019871  test    rax, rax
0x140019874  jz      loc_140019BA1
0x14001987a  jmp     loc_140019B9A
0x14001987f  mov     eax, [r13+0]
0x140019883  bt      rax, 0Ch
0x140019888  jb      loc_140019F3D
0x14001988e  lea     edi, [r15+7]
0x140019892  xor     ecx, ecx; ProcNumber
0x140019894  and     edi, 0FFFFFFF8h
0x140019897  add     edi, 58h ; 'X'
0x14001989a  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400198a1  nop     dword ptr [rax+rax+00h]
0x1400198a6  xor     edx, edx
0x1400198a8  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x1400198ae  lea     rbp, [rdx+rdx*2]
0x1400198b2  shl     rbp, 6
0x1400198b6  add     rbp, cs:qword_140262410
0x1400198bd  mov     eax, [rbp+0]
0x1400198c0  cmp     rdi, rax
0x1400198c3  jbe     loc_140019A14
0x1400198c9  xor     ebp, ebp
0x1400198cb  lea     rdx, [rdi+10h]
0x1400198cf  mov     ecx, 42h ; 'B'
0x1400198d4  mov     r8d, 6950534Dh
0x1400198da  call    cs:__imp_ExAllocatePool2
0x1400198e1  nop     dword ptr [rax+rax+00h]
0x1400198e6  mov     rdi, rax
0x1400198e9  test    al, 0Fh
0x1400198eb  jnz     loc_1401EEC0E
0x1400198f1  test    rax, rax
0x1400198f4  jz      loc_140019EC1
0x1400198fa  jmp     loc_140019EBA
0x1400198ff  mov     rax, [rcx+18h]
0x140019903  mov     ecx, [rax+2Ch]
0x140019906  test    cl, 4
0x140019909  jnz     loc_140019AEA
0x14001990f  mov     ecx, [r9+10h]
0x140019913  test    ecx, ecx
0x140019915  jz      loc_140019A52
0x14001991b  mov     r8, [r9+18h]
0x14001991f  cmp     rdx, r8
0x140019922  jb      loc_140019A52
0x140019928  lea     rax, [r8+rcx]
0x14001992c  cmp     rdx, rax
0x14001992f  ja      loc_140019A52
0x140019935  xor     edx, edx
0x140019937  jmp     loc_140019A87
0x14001993c  mov     rax, [rbp+18h]
0x140019940  mov     ecx, [rax+2Ch]
0x140019943  test    cl, 4
0x140019946  jnz     loc_140019B0D
0x14001994c  mov     ecx, [rbx+30h]
0x14001994f  test    ecx, ecx
0x140019951  jz      loc_140019A9D
0x140019957  mov     r8, [rbx+38h]
0x14001995b  cmp     rdx, r8
0x14001995e  jb      loc_140019A9D
0x140019964  lea     rax, [r8+rcx]
0x140019968  cmp     rdx, rax
0x14001996b  ja      loc_140019A9D
0x140019971  xor     edx, edx
0x140019973  jmp     loc_140019AD3
0x140019978  mov     rax, [rbp+18h]
0x14001997c  mov     ecx, [rax+2Ch]
0x14001997f  test    cl, 4
0x140019982  jnz     loc_140019B30
0x140019988  mov     ecx, [rbx+50h]
0x14001998b  test    ecx, ecx
0x14001998d  jz      loc_140019B53
0x140019993  mov     r8, [rbx+58h]
0x140019997  cmp     rdx, r8
0x14001999a  jb      loc_140019B53
0x1400199a0  lea     rax, [r8+rcx]
0x1400199a4  cmp     rdx, rax
0x1400199a7  ja      loc_140019B53
0x1400199ad  xor     edx, edx
0x1400199af  lea     eax, [rcx+7]
0x1400199b2  and     eax, 0FFFFFFF8h
0x1400199b5  add     eax, 10h
0x1400199b8  add     eax, edx
0x1400199ba  cmp     eax, r15d
0x1400199bd  cmova   r15d, eax
0x1400199c1  jmp     loc_1400197CC
0x1400199c6  movzx   esi, word ptr [rcx+0Ah]
0x1400199ca  add     esi, 7
0x1400199cd  and     esi, 0FFFFFFF8h
0x1400199d0  jmp     loc_1400197FF
0x1400199d5  cmp     byte ptr [rdi+8], 0
0x1400199d9  jnz     loc_14001A048
0x1400199df  mov     rcx, [rdi+58h]
0x1400199e3  mov     rax, rcx
0x1400199e6  shr     rax, 20h
0x1400199ea  cmp     ecx, eax
0x1400199ec  jle     short loc_140019A0C
0x1400199ee  nop
0x1400199ef  lock xadd [rdi+58h], r12d
0x1400199f5  nop
0x1400199f6  lea     ecx, [r12-1]
0x1400199fb  mov     eax, [rdi+5Ch]
0x1400199fe  cmp     ecx, eax
0x140019a00  jge     loc_14001A067
0x140019a06  nop
0x140019a07  lock inc dword ptr [rdi+58h]
0x140019a0b  nop
0x140019a0c  mov     edx, [rdi+4]
0x140019a0f  jmp     loc_14001984F
0x140019a14  cmp     byte ptr [rbp+8], 0
0x140019a18  jnz     loc_14001A000
0x140019a1e  mov     rcx, [rbp+58h]
0x140019a22  mov     rax, rcx
0x140019a25  shr     rax, 20h
0x140019a29  cmp     ecx, eax
0x140019a2b  jle     short loc_140019A4A
0x140019a2d  nop
0x140019a2e  mov     ecx, r12d
0x140019a31  lock xadd [rbp+58h], ecx
0x140019a36  nop
0x140019a37  dec     ecx
0x140019a39  mov     eax, [rbp+5Ch]
0x140019a3c  cmp     ecx, eax
0x140019a3e  jge     loc_14001A01F
0x140019a44  nop
0x140019a45  lock inc dword ptr [rbp+58h]
0x140019a49  nop
0x140019a4a  mov     edx, [rbp+4]
0x140019a4d  jmp     loc_1400198CF
0x140019a52  mov     r9d, [r9]
0x140019a55  test    r9d, r9d
0x140019a58  jz      short loc_140019A78
0x140019a5a  test    ecx, ecx
0x140019a5c  jz      short loc_140019A78
0x140019a5e  mov     r8, [rbx+18h]
0x140019a62  lea     r10, [rdx+r9]
0x140019a66  cmp     r10, r8
0x140019a69  jb      short loc_140019A78
0x140019a6b  lea     rax, [r8+rcx]
0x140019a6f  cmp     r10, rax
0x140019a72  jbe     loc_140019FE8
0x140019a78  lea     r8d, [r9+7]
0x140019a7c  and     r8d, 0FFF8h
0x140019a83  movzx   edx, r8w
0x140019a87  lea     eax, [rcx+7]
0x140019a8a  and     eax, 0FFFFFFF8h
0x140019a8d  add     eax, 10h
0x140019a90  add     eax, edx
0x140019a92  test    eax, eax
0x140019a94  cmovnz  r15d, eax
0x140019a98  jmp     loc_1400197B2
0x140019a9d  mov     r9d, [rbx+20h]
0x140019aa1  test    r9d, r9d
0x140019aa4  jz      short loc_140019AC4
0x140019aa6  test    ecx, ecx
0x140019aa8  jz      short loc_140019AC4
0x140019aaa  mov     r8, [rbx+38h]
0x140019aae  lea     r10, [rdx+r9]
0x140019ab2  cmp     r10, r8
0x140019ab5  jb      short loc_140019AC4
0x140019ab7  lea     rax, [r8+rcx]
0x140019abb  cmp     r10, rax
0x140019abe  jbe     loc_140019FF0
0x140019ac4  lea     r8d, [r9+7]
0x140019ac8  and     r8d, 0FFF8h
0x140019acf  movzx   edx, r8w
0x140019ad3  lea     eax, [rcx+7]
0x140019ad6  and     eax, 0FFFFFFF8h
0x140019ad9  add     eax, 10h
0x140019adc  add     eax, edx
0x140019ade  cmp     eax, r15d
0x140019ae1  cmova   r15d, eax
0x140019ae5  jmp     loc_1400197BF
0x140019aea  mov     rax, [r8+8]
0x140019aee  cmp     [rax+0Ch], dil
0x140019af2  jnz     loc_14001990F
0x140019af8  mov     eax, [r9+10h]
0x140019afc  add     eax, 7
0x140019aff  and     eax, 0FFFFFFF8h
0x140019b02  test    eax, eax
0x140019b04  cmovnz  r15d, eax
0x140019b08  jmp     loc_1400197B2
0x140019b0d  mov     rax, [r14+8]
0x140019b11  cmp     [rax+0Ch], dil
0x140019b15  jnz     loc_14001994C
0x140019b1b  mov     eax, [rbx+30h]
0x140019b1e  add     eax, 7
0x140019b21  and     eax, 0FFFFFFF8h
0x140019b24  cmp     eax, r15d
0x140019b27  cmova   r15d, eax
0x140019b2b  jmp     loc_1400197BF
0x140019b30  mov     rax, [r14+8]
0x140019b34  cmp     [rax+0Ch], dil
0x140019b38  jnz     loc_140019988
0x140019b3e  mov     eax, [rbx+50h]
0x140019b41  add     eax, 7
0x140019b44  and     eax, 0FFFFFFF8h
0x140019b47  cmp     eax, r15d
0x140019b4a  cmova   r15d, eax
0x140019b4e  jmp     loc_1400197CC
0x140019b53  mov     r9d, [rbx+40h]
0x140019b57  test    r9d, r9d
0x140019b5a  jz      short loc_140019B7A
0x140019b5c  test    ecx, ecx
0x140019b5e  jz      short loc_140019B7A
0x140019b60  mov     r8, [rbx+58h]
0x140019b64  lea     r10, [rdx+r9]
0x140019b68  cmp     r10, r8
0x140019b6b  jb      short loc_140019B7A
0x140019b6d  lea     rax, [r8+rcx]
0x140019b71  cmp     r10, rax
0x140019b74  jbe     loc_140019FF8
0x140019b7a  lea     r8d, [r9+7]
0x140019b7e  and     r8d, 0FFF8h
0x140019b85  movzx   edx, r8w
0x140019b89  jmp     loc_1400199AF
0x140019b8e  mov     rbx, rax
0x140019b91  test    rax, rax
0x140019b94  jz      loc_140019A0C
0x140019b9a  mov     [rbx], rdi
0x140019b9d  add     rbx, 10h
0x140019ba1  test    rbx, rbx
0x140019ba4  jz      loc_14001A084
0x140019baa  mov     dword ptr [rbx+10h], 1Eh
0x140019bb1  xorps   xmm0, xmm0
0x140019bb4  mov     [rbx+28h], rbp
0x140019bb8  xor     eax, eax
  ... truncated ...
```
