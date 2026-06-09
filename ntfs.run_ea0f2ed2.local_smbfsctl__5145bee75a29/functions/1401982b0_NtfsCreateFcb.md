# NtfsCreateFcb

- ea: `0x1401982b0`
- end: `0x140198c6e`
- name: `NtfsCreateFcb`
- size: `2494`
- prototype: ``
- caller_count: `32`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x140017480`
- `0x1400e7268`
- `0x1400e7f78`
- `0x1400e9d70`
- `0x1400ead40`
- `0x1400f77ec`
- `0x1400f8a14`
- `0x140105bcc`
- `0x140128140`
- `0x140130550`
- `0x1401321c0`
- `0x140132718`
- `0x140165c10`
- `0x14018cb48`
- `0x14019616c`
- `0x140196ff0`
- `0x1401975a0`
- `0x1401991d0`
- `0x1401c3700`
- `0x1401ca4dc`
- `0x140205560`
- `0x14020d830`
- `0x140210dd0`
- `0x140227518`
- `0x1402376ac`
- `0x140247554`
- `0x14024fba4`
- `0x140252788`
- `0x1402565ac`
- `0x14025e69c`
- `0x140260578`
- `0x140288010`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14000d1e0`
- `0x14000e9dc`
- `0x140012e70`
- `0x1400596c0`
- `0x140140f5c`
- `0x140168820`
- `0x140196ad0`
- `0x140196e30`
- `0x1401982b0`
- `0x1402078f0`
- `0x140212a40`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14019841f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140198688`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14019841f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140198688`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x140198764`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x140198764`
- `ntoskrnl!RtlAvlRemoveNode` at `0x140198b41`
- `ntoskrnl!RtlAvlRemoveNode` at `0x140198b9c`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1402ac4fc`
- `ntoskrnl!RtlAvlRemoveNode` at `0x140198b41`
- `ntoskrnl!RtlAvlRemoveNode` at `0x140198b9c`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1402ac4fc`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14019832c`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14019832c`
- `ntoskrnl!ExReleasePushLockEx` at `0x140198409`
- `ntoskrnl!ExReleasePushLockEx` at `0x14019849b`
- `ntoskrnl!ExReleasePushLockEx` at `0x140198798`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401988e0`
- `ntoskrnl!ExReleasePushLockEx` at `0x140198c4b`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402ac535`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402ac607`
- `ntoskrnl!ExReleasePushLockEx` at `0x140198409`
- `ntoskrnl!ExReleasePushLockEx` at `0x14019849b`
- `ntoskrnl!ExReleasePushLockEx` at `0x140198798`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401988e0`
- `ntoskrnl!ExReleasePushLockEx` at `0x140198c4b`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402ac535`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402ac607`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14019859f`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401987cf`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140198827`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14019886e`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14019859f`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401987cf`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140198827`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14019886e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140198c2c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ac5c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140198c2c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ac5c4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140198500`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140198500`

## pseudocode

```c
_DWORD *NtfsCreateFcb(__int64 a1, __int64 a2, __int64 a3, ...)
{
  __int64 v3; // rbx
  __int64 v5; // r13
  int *v6; // rdi
  _DWORD *v7; // r15
  __int64 v8; // rsi
  char v9; // r12
  char v10; // r10
  _QWORD *v11; // rax
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rdx
  bool v14; // zf
  unsigned int v15; // r14d
  char v16; // al
  int v17; // r15d
  int v18; // r12d
  char v19; // di
  int v20; // eax
  _DWORD *v21; // rsi
  _DWORD *v22; // rdi
  _DWORD *v23; // rax
  _DWORD *v24; // rdi
  int v25; // ecx
  int *v26; // r14
  _QWORD *v27; // rdx
  unsigned __int8 v28; // r11
  char v29; // r10
  unsigned __int64 v30; // r8
  unsigned __int64 v31; // r8
  _QWORD *v32; // rax
  int v33; // ebx
  __int64 v34; // r8
  char v35; // bl
  _DWORD *v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  int v39; // eax
  __int64 v40; // rdi
  __int64 v41; // r8
  __int64 v42; // rbx
  void *v43; // rcx
  char v45; // [rsp+31h] [rbp-87h]
  _DWORD *P; // [rsp+40h] [rbp-78h]
  int v47; // [rsp+48h] [rbp-70h] BYREF
  _QWORD *v48; // [rsp+50h] [rbp-68h]
  _QWORD *v49; // [rsp+58h] [rbp-60h]
  _DWORD *v50; // [rsp+60h] [rbp-58h]
  _DWORD *v51; // [rsp+68h] [rbp-50h]
  unsigned __int64 v52; // [rsp+70h] [rbp-48h]
  __int64 v56; // [rsp+D8h] [rbp+20h] BYREF
  va_list va; // [rsp+D8h] [rbp+20h]
  __int64 v58; // [rsp+E0h] [rbp+28h]
  int *v59; // [rsp+E8h] [rbp+30h]
  va_list va1; // [rsp+F0h] [rbp+38h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v56 = va_arg(va1, _QWORD);
  v58 = va_arg(va1, _QWORD);
  v59 = va_arg(va1, int *);
  v3 = v56;
  v5 = a2;
  v47 = 0;
  v45 = 0;
  v51 = 0;
  v6 = &v47;
  if ( v59 )
    v6 = v59;
  v59 = v6;
  *v6 = 0;
  v7 = 0;
  v8 = a2 + 656;
  ExAcquirePushLockSharedEx(a2 + 656, 0);
  v9 = 1;
  v10 = 1;
  while ( 2 )
  {
    v11 = *(_QWORD **)(v5 + 1344);
    v48 = v11;
    if ( !v11 )
    {
LABEL_17:
      v15 = -1;
LABEL_18:
      if ( v7 )
      {
        v16 = v58;
        if ( (v58 & 0x20) != 0 )
        {
          _InterlockedIncrement(v7 + 7);
          *v6 |= 4u;
        }
        if ( (v16 & 0x40) != 0 )
        {
          NtfsAcquireExclusiveFcbHoldingFcbTable(a1, v7);
          *v6 |= 8u;
        }
        goto LABEL_118;
      }
      goto LABEL_26;
    }
    while ( 1 )
    {
      v12 = *(v11 - 2);
      v52 = v12;
      if ( (v3 & 0xFFFFFFFFFFFFuLL) >= (v12 & 0xFFFFFFFFFFFFLL) )
      {
        if ( (v3 & 0xFFFFFFFFFFFFuLL) > (v12 & 0xFFFFFFFFFFFFLL) )
          goto LABEL_9;
        v13 = HIWORD(v12);
        if ( HIWORD(v3) >= (unsigned __int16)v13 )
          break;
      }
      v11 = (_QWORD *)*v11;
      v14 = v11 == 0;
LABEL_11:
      if ( v14 )
        goto LABEL_17;
      v48 = v11;
    }
    if ( HIWORD(v3) > (unsigned __int16)v13 )
    {
LABEL_9:
      v11 = (_QWORD *)v11[1];
      v14 = v11 == 0;
      goto LABEL_11;
    }
    v7 = (_DWORD *)*(v11 - 1);
    if ( (v7[1] & 1) == 0 )
    {
      if ( !a3 || *((_QWORD *)v7 + 40) )
      {
        v15 = -1;
      }
      else
      {
        if ( v10 )
          goto LABEL_16;
        _InterlockedIncrement((volatile signed __int32 *)(a3 + 64));
        _InterlockedIncrement((volatile signed __int32 *)(a3 + 36));
        v38 = *((_QWORD *)v7 + 40);
        v15 = -1;
        if ( v38 )
        {
          _InterlockedDecrement((volatile signed __int32 *)(v38 + 36));
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)v7 + 40) + 64LL), 0xFFFFFFFF) == 1 )
            TxfDeleteTxfRmcb(*((PVOID *)v7 + 40));
        }
        *((_QWORD *)v7 + 40) = a3;
      }
      *v6 |= 1u;
      goto LABEL_18;
    }
    if ( (v7[1] & 0x2000000) != 0 )
    {
      *v6 |= 2u;
      v39 = *v6;
      if ( (v58 & 0x10) != 0 )
      {
        if ( (v58 & 0x20) != 0 )
        {
          _InterlockedIncrement(v7 + 7);
          *v6 |= 4u;
          v39 = *v6;
        }
        if ( (v58 & 0x40) != 0 )
        {
          NtfsAcquireExclusiveFcbHoldingFcbTable(a1, v7);
          *v6 |= 8u;
          v39 = *v6;
        }
        *v6 = v39 | 1;
        goto LABEL_118;
      }
      if ( (v58 & 4) != 0 )
      {
        v7 = 0;
        goto LABEL_118;
      }
      ++NtfsFailedDIPRemoved;
    }
    if ( v10 )
    {
LABEL_16:
      ExReleasePushLockEx(v8, 0);
      ExAcquirePushLockExclusiveEx(v8, 0);
      v9 = 1;
      v10 = 0;
      continue;
    }
    break;
  }
  v40 = *((_QWORD *)v7 + 12);
  RtlAvlRemoveNode(v40 + 1344, *((_QWORD *)v7 + 13) + 256LL);
  --*(_DWORD *)(v40 + 1352);
  v7[1] &= ~0x40u;
  LOBYTE(v41) = 1;
  NtfsDereferenceMftView(v5, v7 + 2, v41);
  v7 = 0;
  v15 = -1;
LABEL_26:
  v50 = 0;
  ExReleasePushLockEx(v8, 0);
  v9 = 0;
  if ( (v58 & 0x80u) != 0LL )
    goto LABEL_118;
  v17 = v58 & 2;
  v18 = v58 & 8;
  v19 = v58 & 1;
  if ( (v58 & 1) == 0 )
  {
    if ( (unsigned int)v3 > 8 || (v20 = 323, !_bittest(&v20, v3)) )
    {
      if ( (v58 & 2) != 0 )
      {
        P = ExAllocateFromLookasideListEx(&NtfsFcbIndexLookasideList);
        v21 = P;
        memset(P, 0, 0x640u);
        P[1] |= 0x400u;
      }
      else
      {
        P = ExAllocateFromLookasideListEx(&NtfsFcbDataLookasideList);
        v21 = P;
        memset(P, 0, 0x570u);
        P[1] |= 0x200u;
      }
      goto LABEL_33;
    }
  }
  P = ExAllocatePoolWithTag((POOL_TYPE)528, 0x168u, 0x6666744Eu);
  v21 = P;
  memset(P, 0, 0x168u);
  if ( v19 )
    goto LABEL_84;
  v22 = P;
  while ( 2 )
  {
    v22[1] |= 2u;
LABEL_33:
    *v21 = 23594754;
    *((_QWORD *)v21 + 7) = v21 + 12;
    *((_QWORD *)v21 + 6) = v21 + 12;
    v5 = a2;
    *((_QWORD *)v21 + 12) = a2;
    if ( *((_QWORD *)v21 + 40) != a3 )
    {
      if ( a3 )
      {
        _InterlockedIncrement((volatile signed __int32 *)(a3 + 64));
        _InterlockedIncrement((volatile signed __int32 *)(a3 + 36));
      }
      v37 = *((_QWORD *)v21 + 40);
      if ( v37 )
      {
        _InterlockedDecrement((volatile signed __int32 *)(v37 + 36));
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)v21 + 40) + 64LL), v15) == 1 )
          TxfDeleteTxfRmcb(*((PVOID *)v21 + 40));
      }
      *((_QWORD *)v21 + 40) = a3;
    }
    *((_QWORD *)v21 + 1) = v3;
    *((_QWORD *)v21 + 9) = v21 + 16;
    *((_QWORD *)v21 + 8) = v21 + 16;
    v15 = 0;
    *((_QWORD *)v21 + 43) = 0;
    *((_QWORD *)v21 + 25) = 0;
    *((_QWORD *)v21 + 27) = 0;
    if ( v17 )
    {
      v23 = ExAllocateFromLookasideListEx(&NtfsFcbNonpagedIndexLookasideList);
      v24 = v23;
      if ( v23 )
      {
        *v23 = 18351941;
        goto LABEL_37;
      }
      v24 = 0;
    }
    else
    {
      v36 = ExAllocateFromLookasideListEx(&NtfsFcbNonpagedDataLookasideList);
      v24 = v36;
      if ( v36 )
      {
        *v36 = 25691971;
LABEL_37:
        *((_QWORD *)v24 + 30) = *((_QWORD *)v21 + 1);
        *((_QWORD *)v24 + 31) = v21;
        *((_WORD *)v24 + 2) = 0;
      }
      else
      {
        v24 = 0;
      }
    }
    *((_QWORD *)v21 + 13) = v24;
    v51 = v24;
    if ( !v24 )
    {
      while ( 1 )
      {
        v3 = a1;
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 3221225626LL, 2231415);
        NtfsRaiseStatusInternal(a1, -1073741670, 0, 0, 2231415);
LABEL_84:
        if ( (*(_DWORD *)(a2 + 4) & 0x2000000) == 0 )
          break;
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 3221225634LL, 2231326);
        NtfsRaiseStatusInternal(a1, -1073741662, 0, 0, 2231326);
      }
      v22 = P;
      P[1] |= 4u;
      continue;
    }
    break;
  }
  NtfsReferenceMftView(a2, (__int64 *)va);
  if ( v18 || (unsigned int)v3 < 0x10 )
    v21[1] |= 0x10000100u;
  v25 = v21[1];
  if ( (*(_DWORD *)(a2 + 24) & 1) != 0 )
  {
    v25 |= 0x80u;
    v21[1] = v25;
  }
  if ( (*(_DWORD *)(a2 + 24) & 8) != 0 )
    v21[1] = v25 | 0x8000000;
  *((_BYTE *)v21 + 232) = -1;
  *((_QWORD *)v21 + 41) = TxfCreateTxfFcb(*((_QWORD *)v21 + 12), 0, (unsigned int)va, v21[1] & 0x400, 0, 1);
  if ( (v58 & 0x40) != 0 )
  {
    NtfsAcquireExclusiveFcb(a1, v21, 0, 5);
    v45 = 1;
    v26 = v59;
    *v59 |= 8u;
  }
  else
  {
    v26 = v59;
  }
  ExAcquirePushLockExclusiveEx(a2 + 656, 0);
  v27 = *(_QWORD **)(a2 + 1344);
  v49 = v27;
  v28 = 0;
  v29 = 0;
  if ( v27 )
  {
    while ( 2 )
    {
      v30 = *(v27 - 2);
      v59 = (int *)v30;
      if ( (v3 & 0xFFFFFFFFFFFFuLL) < (v30 & 0xFFFFFFFFFFFFLL) )
        goto LABEL_54;
      if ( (v3 & 0xFFFFFFFFFFFFuLL) > (v30 & 0xFFFFFFFFFFFFLL) )
      {
LABEL_52:
        v32 = (_QWORD *)v27[1];
        if ( !v32 )
        {
          v28 = 1;
          break;
        }
      }
      else
      {
        v31 = HIWORD(v30);
        if ( HIWORD(v3) >= (unsigned __int16)v31 )
        {
          if ( HIWORD(v3) <= (unsigned __int16)v31 )
          {
            v29 = 1;
            break;
          }
          goto LABEL_52;
        }
LABEL_54:
        v32 = (_QWORD *)*v27;
        if ( !*v27 )
          break;
      }
      v27 = v32;
      v49 = v32;
      continue;
    }
  }
  v33 = v58 & 0x20;
  if ( v29 )
  {
    v7 = (_DWORD *)*(v27 - 1);
    if ( (v58 & 0x20) != 0 )
    {
      _InterlockedIncrement(v7 + 7);
      *v26 |= 4u;
    }
    if ( (v58 & 0x40) != 0 )
    {
      NtfsReleaseFcbEx(a1, v21, 1);
      v45 = 0;
      NtfsAcquireExclusiveFcbHoldingFcbTable(a1, v7);
    }
    v35 = 1;
    *v26 |= 1u;
    ExReleasePushLockEx(a2 + 656, 0);
    v9 = 0;
    v50 = v7;
  }
  else
  {
    RtlAvlInsertNodeEx(*((_QWORD *)v21 + 12) + 1344LL, v27, v28, *((_QWORD *)v21 + 13) + 256LL);
    ++*(_DWORD *)(*((_QWORD *)v21 + 12) + 1352LL);
    v21[1] |= 0x40u;
    if ( v33 )
    {
      _InterlockedIncrement(v21 + 7);
      *v26 |= 4u;
    }
    ExReleasePushLockEx(a2 + 656, 0);
    v9 = 0;
    v7 = v21;
    v50 = v21;
    v35 = 0;
  }
  if ( v35 )
  {
    if ( v21 )
    {
      if ( (v21[1] & 0x40) != 0 )
      {
        v42 = *((_QWORD *)v21 + 12);
        RtlAvlRemoveNode(v42 + 1344, *((_QWORD *)v21 + 13) + 256LL);
        --*(_DWORD *)(v42 + 1352);
        v21[1] &= ~0x40u;
      }
      v43 = (void *)*((_QWORD *)v21 + 41);
      if ( v43 )
      {
        TxfDereferenceTxfFcb(v43);
        *((_QWORD *)v21 + 41) = 0;
      }
    }
    LOBYTE(v34) = 1;
    NtfsDereferenceMftView(a2, (__int64 *)va, v34);
    if ( v21 && v45 )
      NtfsReleaseFcbEx(a1, v21, 1);
    NtfsDeleteNonpagedFcb(v24);
    if ( P )
      ExFreePoolWithTag(P, 0);
  }
LABEL_118:
  if ( v9 )
    ExReleasePushLockEx(v5 + 656, 0);
  return v7;
}

```

## disassembly

```asm
0x1401982b0  mov     rax, rsp
0x1401982b3  mov     [rax+20h], r9
0x1401982b7  mov     [rax+18h], r8
0x1401982bb  mov     [rax+10h], rdx
0x1401982bf  mov     [rax+8], rcx
0x1401982c3  push    rbx
0x1401982c4  push    rsi
0x1401982c5  push    rdi
0x1401982c6  push    r12
0x1401982c8  push    r13
0x1401982ca  push    r14
0x1401982cc  push    r15
0x1401982ce  sub     rsp, 80h
0x1401982d5  mov     rbx, r9
0x1401982d8  mov     r14, r8
0x1401982db  mov     r13, rdx
0x1401982de  xor     ecx, ecx
0x1401982e0  mov     [rax-70h], ecx
0x1401982e3  mov     [rsp+0B8h+var_83], cl
0x1401982e7  mov     [rsp+0B8h+var_88], cl
0x1401982eb  mov     [rsp+0B8h+var_84], cl
0x1401982ef  mov     [rsp+0B8h+var_87], cl
0x1401982f3  mov     [rax-78h], rcx
0x1401982f7  mov     [rax-50h], rcx
0x1401982fb  lea     rdi, [rax-70h]
0x1401982ff  mov     rax, [rsp+0B8h+arg_28]
0x140198307  test    rax, rax
0x14019830a  cmovnz  rdi, rax
0x14019830e  mov     [rsp+0B8h+arg_28], rdi
0x140198316  mov     [rdi], ecx
0x140198318  mov     r15d, ecx
0x14019831b  mov     [rsp+0B8h+var_80], rcx
0x140198320  lea     rsi, [rdx+290h]
0x140198327  xor     edx, edx
0x140198329  mov     rcx, rsi
0x14019832c  call    cs:__imp_ExAcquirePushLockSharedEx
0x140198333  nop     dword ptr [rax+rax+00h]
0x140198338  mov     r12b, 1
0x14019833b  mov     [rsp+0B8h+var_88], r12b
0x140198340  movzx   r10d, r12b
0x140198344  mov     r11, 0FFFFFFFFFFFFh
0x14019834e  mov     rax, [r13+540h]
0x140198355  mov     [rsp+0B8h+var_68], 0
0x14019835e  mov     [rsp+0B8h+var_68], rax
0x140198363  mov     [rsp+0B8h+var_86], 0
0x140198368  test    rax, rax
0x14019836b  jz      loc_14019843B
0x140198371  nop     dword ptr [rax+00h]
0x140198375  nop     word ptr [rax+rax+00000000h]
0x140198380  mov     r9, rbx
0x140198383  shr     r9, 30h
0x140198387  mov     rdx, [rax-10h]
0x14019838b  mov     [rsp+0B8h+var_48], rdx
0x140198390  mov     r8, rdx
0x140198393  and     r8, r11
0x140198396  mov     rcx, rbx
0x140198399  and     rcx, r11
0x14019839c  cmp     rcx, r8
0x14019839f  jb      short loc_1401983C1
0x1401983a1  mov     rcx, rbx
0x1401983a4  and     rcx, r11
0x1401983a7  cmp     rcx, r8
0x1401983aa  ja      short loc_1401983B8
0x1401983ac  shr     rdx, 30h
0x1401983b0  cmp     r9w, dx
0x1401983b4  jb      short loc_1401983C1
0x1401983b6  jbe     short loc_1401983D3
0x1401983b8  mov     rax, [rax+8]
0x1401983bc  test    rax, rax
0x1401983bf  jmp     short loc_1401983CA
0x1401983c1  mov     rcx, [rax]
0x1401983c4  mov     rax, rcx
0x1401983c7  test    rcx, rcx
0x1401983ca  jz      short loc_14019843B
0x1401983cc  mov     [rsp+0B8h+var_68], rax
0x1401983d1  jmp     short loc_140198380
0x1401983d3  mov     [rsp+0B8h+var_86], 1
0x1401983d8  mov     r15, [rax-8]
0x1401983dc  mov     [rsp+0B8h+var_80], r15
0x1401983e1  mov     eax, [r15+4]
0x1401983e5  test    al, 1
0x1401983e7  jz      loc_140198479
0x1401983ed  test    dword ptr [r15+4], 2000000h
0x1401983f5  jnz     loc_140198AC2
0x1401983fb  test    r10b, r10b
0x1401983fe  jz      loc_140198B2B
0x140198404  xor     edx, edx
0x140198406  mov     rcx, rsi
0x140198409  call    cs:__imp_ExReleasePushLockEx
0x140198410  nop     dword ptr [rax+rax+00h]
0x140198415  mov     [rsp+0B8h+var_88], 0
0x14019841a  xor     edx, edx
0x14019841c  mov     rcx, rsi
0x14019841f  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140198426  nop     dword ptr [rax+rax+00h]
0x14019842b  mov     r12b, 1
0x14019842e  mov     [rsp+0B8h+var_88], r12b
0x140198433  xor     r10b, r10b
0x140198436  jmp     loc_140198344
0x14019843b  mov     r14d, 0FFFFFFFFh
0x140198441  test    r15, r15
0x140198444  jz      short loc_14019848D
0x140198446  mov     eax, dword ptr [rsp+0B8h+arg_20]
0x14019844d  test    al, 20h
0x14019844f  jz      short loc_140198459
0x140198451  lock inc dword ptr [r15+1Ch]
0x140198456  or      dword ptr [rdi], 4
0x140198459  test    al, 40h
0x14019845b  jz      loc_140198C3D
0x140198461  mov     rdx, r15
0x140198464  mov     rcx, [rsp+0B8h+arg_0]
0x14019846c  call    NtfsAcquireExclusiveFcbHoldingFcbTable
0x140198471  or      dword ptr [rdi], 8
0x140198474  jmp     loc_140198C3D
0x140198479  test    r14, r14
0x14019847c  jnz     loc_140198A57
0x140198482  mov     r14d, 0FFFFFFFFh
0x140198488  or      dword ptr [rdi], 1
0x14019848b  jmp     short loc_140198441
0x14019848d  mov     [rsp+0B8h+var_58], 0
0x140198496  xor     edx, edx
0x140198498  mov     rcx, rsi
0x14019849b  call    cs:__imp_ExReleasePushLockEx
0x1401984a2  nop     dword ptr [rax+rax+00h]
0x1401984a7  xor     r12b, r12b
0x1401984aa  mov     [rsp+0B8h+var_88], r12b
0x1401984af  mov     eax, dword ptr [rsp+0B8h+arg_20]
0x1401984b6  test    al, al
0x1401984b8  js      loc_140198C3D
0x1401984be  movzx   edi, al
0x1401984c1  mov     r15d, eax
0x1401984c4  and     r15d, 2
0x1401984c8  mov     r12d, eax
0x1401984cb  and     r12d, 8
0x1401984cf  and     dil, 1
0x1401984d3  jnz     short loc_1401984EC
0x1401984d5  cmp     ebx, 8
0x1401984d8  ja      loc_14019881B
0x1401984de  mov     eax, 143h
0x1401984e3  bt      eax, ebx
0x1401984e6  jnb     loc_14019881B
0x1401984ec  mov     r8d, 6666744Eh; Tag
0x1401984f2  mov     r13d, 168h
0x1401984f8  mov     edx, r13d; NumberOfBytes
0x1401984fb  mov     ecx, 210h; PoolType
0x140198500  call    cs:__imp_ExAllocatePoolWithTag
0x140198507  nop     dword ptr [rax+rax+00h]
0x14019850c  mov     [rsp+0B8h+P], rax
0x140198511  mov     rsi, rax
0x140198514  mov     [rsp+0B8h+var_80], rax
0x140198519  mov     r8d, r13d; Size
0x14019851c  xor     edx, edx; Val
0x14019851e  mov     rcx, rax; void *
0x140198521  call    memset
0x140198526  test    dil, dil
0x140198529  jnz     loc_140198982
0x14019852f  mov     rdi, rsi
0x140198532  or      dword ptr [rdi+4], 2
0x140198536  mov     dword ptr [rsi], 1680702h
0x14019853c  lea     rax, [rsi+30h]
0x140198540  mov     [rax+8], rax
0x140198544  mov     [rax], rax
0x140198547  mov     r13, [rsp+0B8h+arg_8]
0x14019854f  mov     [rsi+60h], r13
0x140198553  mov     rdi, [rsp+0B8h+arg_10]
0x14019855b  cmp     [rsi+140h], rdi
0x140198562  jnz     loc_1401987F2
0x140198568  mov     [rsi+8], rbx
0x14019856c  lea     rax, [rsi+40h]
0x140198570  mov     [rax+8], rax
0x140198574  mov     [rax], rax
0x140198577  xor     r14d, r14d
0x14019857a  mov     [rsi+158h], r14
0x140198581  mov     [rsi+0C8h], r14
0x140198588  mov     [rsi+0D8h], r14
0x14019858f  test    r15d, r15d
0x140198592  jz      loc_1401987C8
0x140198598  lea     rcx, NtfsFcbNonpagedIndexLookasideList; Lookaside
0x14019859f  call    cs:__imp_ExAllocateFromLookasideListEx
0x1401985a6  nop     dword ptr [rax+rax+00h]
0x1401985ab  mov     rdi, rax
0x1401985ae  test    rax, rax
0x1401985b1  jz      loc_14019885F
0x1401985b7  mov     dword ptr [rax], 1180745h
0x1401985bd  mov     rax, [rsi+8]
0x1401985c1  mov     [rdi+0F0h], rax
0x1401985c8  mov     [rdi+0F8h], rsi
0x1401985cf  mov     [rdi+4], r14w
0x1401985d4  mov     [rsi+68h], rdi
0x1401985d8  mov     [rsp+0B8h+var_50], rdi
0x1401985dd  test    rdi, rdi
0x1401985e0  jz      loc_140198940
0x1401985e6  lea     rdx, [rsp+0B8h+arg_18]
0x1401985ee  mov     rcx, r13
0x1401985f1  call    NtfsReferenceMftView
0x1401985f6  mov     [rsp+0B8h+var_83], 1
0x1401985fb  test    r12d, r12d
0x1401985fe  jnz     loc_1401989D1
0x140198604  cmp     ebx, 10h
0x140198607  jb      loc_1401989D1
0x14019860d  mov     ecx, [rsi+4]
0x140198610  mov     eax, [r13+18h]
0x140198614  test    al, 1
0x140198616  jnz     loc_1401989DD
0x14019861c  mov     eax, [r13+18h]
0x140198620  test    al, 8
0x140198622  jnz     loc_1401989E9
0x140198628  mov     byte ptr [rsi+0E8h], 0FFh
0x14019862f  mov     r9d, [rsi+4]
0x140198633  and     r9d, 400h
0x14019863a  mov     [rsp+0B8h+var_90], 1
0x140198642  mov     dword ptr [rsp+0B8h+var_98], r14d
0x140198647  lea     r8, [rsp+0B8h+arg_18]
0x14019864f  xor     edx, edx
0x140198651  mov     rcx, [rsi+60h]
0x140198655  call    TxfCreateTxfFcb
0x14019865a  mov     [rsi+148h], rax
0x140198661  mov     r12, [rsp+0B8h+arg_0]
0x140198669  test    byte ptr [rsp+0B8h+arg_20], 40h
0x140198671  jnz     loc_1401989F5
0x140198677  mov     r14, [rsp+0B8h+arg_28]
0x14019867f  xor     edx, edx
0x140198681  lea     rcx, [r13+290h]
0x140198688  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14019868f  nop     dword ptr [rax+rax+00h]
0x140198694  mov     [rsp+0B8h+var_88], 1
0x140198699  mov     rdx, [r13+540h]
0x1401986a0  mov     [rsp+0B8h+var_60], 0
0x1401986a9  mov     [rsp+0B8h+var_60], rdx
0x1401986ae  xor     r11b, r11b
0x1401986b1  mov     [rsp+0B8h+var_85], r11b
0x1401986b6  xor     r10b, r10b
0x1401986b9  mov     [rsp+0B8h+var_86], r10b
0x1401986be  test    rdx, rdx
0x1401986c1  jz      short loc_140198737
0x1401986c3  mov     r15, 0FFFFFFFFFFFFh
0x1401986cd  nop     dword ptr [rax]
0x1401986d0  mov     r9, rbx
0x1401986d3  shr     r9, 30h
0x1401986d7  mov     r8, [rdx-10h]
0x1401986db  mov     [rsp+0B8h+arg_28], r8
0x1401986e3  mov     rcx, r8
0x1401986e6  and     rcx, r15
0x1401986e9  mov     rax, rbx
0x1401986ec  and     rax, r15
0x1401986ef  cmp     rax, rcx
0x1401986f2  jb      short loc_140198722
0x1401986f4  mov     rax, rbx
0x1401986f7  and     rax, r15
0x1401986fa  cmp     rax, rcx
0x1401986fd  ja      short loc_14019870B
0x1401986ff  shr     r8, 30h
0x140198703  cmp     r9w, r8w
0x140198707  jb      short loc_140198722
0x140198709  jbe     short loc_14019872F
0x14019870b  mov     rax, [rdx+8]
0x14019870f  test    rax, rax
0x140198712  jz      loc_1401987BB
0x140198718  mov     rdx, rax
0x14019871b  mov     [rsp+0B8h+var_60], rax
0x140198720  jmp     short loc_1401986D0
0x140198722  mov     rax, [rdx]
0x140198725  test    rax, rax
0x140198728  jnz     short loc_140198718
0x14019872a  jmp     loc_1401987BE
0x14019872f  mov     r10b, 1
0x140198732  mov     [rsp+0B8h+var_86], r10b
0x140198737  mov     ebx, dword ptr [rsp+0B8h+arg_20]
0x14019873e  and     ebx, 20h
0x140198741  test    r10b, r10b
0x140198744  jnz     loc_1401988AE
0x14019874a  mov     r9, [rsi+68h]
0x14019874e  add     r9, 100h
0x140198755  mov     rcx, [rsi+60h]
0x140198759  add     rcx, 540h
0x140198760  movzx   r8d, r11b
0x140198764  call    cs:__imp_RtlAvlInsertNodeEx
0x14019876b  nop     dword ptr [rax+rax+00h]
0x140198770  mov     rax, [rsi+60h]
0x140198774  inc     dword ptr [rax+548h]
0x14019877a  mov     eax, [rsi+4]
0x14019877d  or      eax, 40h
0x140198780  mov     [rsi+4], eax
0x140198783  test    ebx, ebx
0x140198785  jz      short loc_14019878F
0x140198787  lock inc dword ptr [rsi+1Ch]
0x14019878b  or      dword ptr [r14], 4
0x14019878f  lea     rcx, [r13+290h]
0x140198796  xor     edx, edx
0x140198798  call    cs:__imp_ExReleasePushLockEx
0x14019879f  nop     dword ptr [rax+rax+00h]
0x1401987a4  xor     r12b, r12b
0x1401987a7  mov     [rsp+0B8h+var_88], r12b
0x1401987ac  mov     r15, rsi
0x1401987af  mov     [rsp+0B8h+var_58], rsi
0x1401987b4  xor     bl, bl
0x1401987b6  jmp     loc_140198A45
0x1401987bb  mov     r11b, 1
0x1401987be  mov     [rsp+0B8h+var_85], r11b
0x1401987c3  jmp     loc_140198737
  ... truncated ...
```
