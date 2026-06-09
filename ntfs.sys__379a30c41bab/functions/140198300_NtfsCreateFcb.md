# NtfsCreateFcb

- ea: `0x140198300`
- end: `0x140198cbe`
- name: `NtfsCreateFcb`
- size: `2494`
- prototype: ``
- caller_count: `32`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x140017480`
- `0x1400e72b8`
- `0x1400e7fc8`
- `0x1400e9dc0`
- `0x1400ead90`
- `0x1400f783c`
- `0x1400f8a64`
- `0x140105c1c`
- `0x140128190`
- `0x1401305a0`
- `0x140132210`
- `0x140132768`
- `0x140165c60`
- `0x14018cb98`
- `0x1401961bc`
- `0x140197040`
- `0x1401975f0`
- `0x140199220`
- `0x1401c3750`
- `0x1401ca52c`
- `0x1402055b0`
- `0x14020d880`
- `0x140210e20`
- `0x140227568`
- `0x1402376fc`
- `0x1402475a4`
- `0x14024fbf4`
- `0x1402527d8`
- `0x1402565fc`
- `0x14025e6ec`
- `0x1402605c8`
- `0x140288060`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14000d1e0`
- `0x14000e9dc`
- `0x140012e70`
- `0x140059740`
- `0x140140fac`
- `0x140168870`
- `0x140196b20`
- `0x140196e80`
- `0x140198300`
- `0x140207940`
- `0x140212a90`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14019846f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401986d8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14019846f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401986d8`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x1401987b4`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x1401987b4`
- `ntoskrnl!RtlAvlRemoveNode` at `0x140198b91`
- `ntoskrnl!RtlAvlRemoveNode` at `0x140198bec`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1402ac54c`
- `ntoskrnl!RtlAvlRemoveNode` at `0x140198b91`
- `ntoskrnl!RtlAvlRemoveNode` at `0x140198bec`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1402ac54c`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14019837c`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14019837c`
- `ntoskrnl!ExReleasePushLockEx` at `0x140198459`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401984eb`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401987e8`
- `ntoskrnl!ExReleasePushLockEx` at `0x140198930`
- `ntoskrnl!ExReleasePushLockEx` at `0x140198c9b`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402ac585`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402ac657`
- `ntoskrnl!ExReleasePushLockEx` at `0x140198459`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401984eb`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401987e8`
- `ntoskrnl!ExReleasePushLockEx` at `0x140198930`
- `ntoskrnl!ExReleasePushLockEx` at `0x140198c9b`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402ac585`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402ac657`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401985ef`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14019881f`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140198877`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401988be`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401985ef`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14019881f`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140198877`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401988be`
- `ntoskrnl!ExFreePoolWithTag` at `0x140198c7c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ac614`
- `ntoskrnl!ExFreePoolWithTag` at `0x140198c7c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ac614`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140198550`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140198550`

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
0x140198300  mov     rax, rsp
0x140198303  mov     [rax+20h], r9
0x140198307  mov     [rax+18h], r8
0x14019830b  mov     [rax+10h], rdx
0x14019830f  mov     [rax+8], rcx
0x140198313  push    rbx
0x140198314  push    rsi
0x140198315  push    rdi
0x140198316  push    r12
0x140198318  push    r13
0x14019831a  push    r14
0x14019831c  push    r15
0x14019831e  sub     rsp, 80h
0x140198325  mov     rbx, r9
0x140198328  mov     r14, r8
0x14019832b  mov     r13, rdx
0x14019832e  xor     ecx, ecx
0x140198330  mov     [rax-70h], ecx
0x140198333  mov     [rsp+0B8h+var_83], cl
0x140198337  mov     [rsp+0B8h+var_88], cl
0x14019833b  mov     [rsp+0B8h+var_84], cl
0x14019833f  mov     [rsp+0B8h+var_87], cl
0x140198343  mov     [rax-78h], rcx
0x140198347  mov     [rax-50h], rcx
0x14019834b  lea     rdi, [rax-70h]
0x14019834f  mov     rax, [rsp+0B8h+arg_28]
0x140198357  test    rax, rax
0x14019835a  cmovnz  rdi, rax
0x14019835e  mov     [rsp+0B8h+arg_28], rdi
0x140198366  mov     [rdi], ecx
0x140198368  mov     r15d, ecx
0x14019836b  mov     [rsp+0B8h+var_80], rcx
0x140198370  lea     rsi, [rdx+290h]
0x140198377  xor     edx, edx
0x140198379  mov     rcx, rsi
0x14019837c  call    cs:__imp_ExAcquirePushLockSharedEx
0x140198383  nop     dword ptr [rax+rax+00h]
0x140198388  mov     r12b, 1
0x14019838b  mov     [rsp+0B8h+var_88], r12b
0x140198390  movzx   r10d, r12b
0x140198394  mov     r11, 0FFFFFFFFFFFFh
0x14019839e  mov     rax, [r13+540h]
0x1401983a5  mov     [rsp+0B8h+var_68], 0
0x1401983ae  mov     [rsp+0B8h+var_68], rax
0x1401983b3  mov     [rsp+0B8h+var_86], 0
0x1401983b8  test    rax, rax
0x1401983bb  jz      loc_14019848B
0x1401983c1  nop     dword ptr [rax+00h]
0x1401983c5  nop     word ptr [rax+rax+00000000h]
0x1401983d0  mov     r9, rbx
0x1401983d3  shr     r9, 30h
0x1401983d7  mov     rdx, [rax-10h]
0x1401983db  mov     [rsp+0B8h+var_48], rdx
0x1401983e0  mov     r8, rdx
0x1401983e3  and     r8, r11
0x1401983e6  mov     rcx, rbx
0x1401983e9  and     rcx, r11
0x1401983ec  cmp     rcx, r8
0x1401983ef  jb      short loc_140198411
0x1401983f1  mov     rcx, rbx
0x1401983f4  and     rcx, r11
0x1401983f7  cmp     rcx, r8
0x1401983fa  ja      short loc_140198408
0x1401983fc  shr     rdx, 30h
0x140198400  cmp     r9w, dx
0x140198404  jb      short loc_140198411
0x140198406  jbe     short loc_140198423
0x140198408  mov     rax, [rax+8]
0x14019840c  test    rax, rax
0x14019840f  jmp     short loc_14019841A
0x140198411  mov     rcx, [rax]
0x140198414  mov     rax, rcx
0x140198417  test    rcx, rcx
0x14019841a  jz      short loc_14019848B
0x14019841c  mov     [rsp+0B8h+var_68], rax
0x140198421  jmp     short loc_1401983D0
0x140198423  mov     [rsp+0B8h+var_86], 1
0x140198428  mov     r15, [rax-8]
0x14019842c  mov     [rsp+0B8h+var_80], r15
0x140198431  mov     eax, [r15+4]
0x140198435  test    al, 1
0x140198437  jz      loc_1401984C9
0x14019843d  test    dword ptr [r15+4], 2000000h
0x140198445  jnz     loc_140198B12
0x14019844b  test    r10b, r10b
0x14019844e  jz      loc_140198B7B
0x140198454  xor     edx, edx
0x140198456  mov     rcx, rsi
0x140198459  call    cs:__imp_ExReleasePushLockEx
0x140198460  nop     dword ptr [rax+rax+00h]
0x140198465  mov     [rsp+0B8h+var_88], 0
0x14019846a  xor     edx, edx
0x14019846c  mov     rcx, rsi
0x14019846f  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140198476  nop     dword ptr [rax+rax+00h]
0x14019847b  mov     r12b, 1
0x14019847e  mov     [rsp+0B8h+var_88], r12b
0x140198483  xor     r10b, r10b
0x140198486  jmp     loc_140198394
0x14019848b  mov     r14d, 0FFFFFFFFh
0x140198491  test    r15, r15
0x140198494  jz      short loc_1401984DD
0x140198496  mov     eax, dword ptr [rsp+0B8h+arg_20]
0x14019849d  test    al, 20h
0x14019849f  jz      short loc_1401984A9
0x1401984a1  lock inc dword ptr [r15+1Ch]
0x1401984a6  or      dword ptr [rdi], 4
0x1401984a9  test    al, 40h
0x1401984ab  jz      loc_140198C8D
0x1401984b1  mov     rdx, r15
0x1401984b4  mov     rcx, [rsp+0B8h+arg_0]
0x1401984bc  call    NtfsAcquireExclusiveFcbHoldingFcbTable
0x1401984c1  or      dword ptr [rdi], 8
0x1401984c4  jmp     loc_140198C8D
0x1401984c9  test    r14, r14
0x1401984cc  jnz     loc_140198AA7
0x1401984d2  mov     r14d, 0FFFFFFFFh
0x1401984d8  or      dword ptr [rdi], 1
0x1401984db  jmp     short loc_140198491
0x1401984dd  mov     [rsp+0B8h+var_58], 0
0x1401984e6  xor     edx, edx
0x1401984e8  mov     rcx, rsi
0x1401984eb  call    cs:__imp_ExReleasePushLockEx
0x1401984f2  nop     dword ptr [rax+rax+00h]
0x1401984f7  xor     r12b, r12b
0x1401984fa  mov     [rsp+0B8h+var_88], r12b
0x1401984ff  mov     eax, dword ptr [rsp+0B8h+arg_20]
0x140198506  test    al, al
0x140198508  js      loc_140198C8D
0x14019850e  movzx   edi, al
0x140198511  mov     r15d, eax
0x140198514  and     r15d, 2
0x140198518  mov     r12d, eax
0x14019851b  and     r12d, 8
0x14019851f  and     dil, 1
0x140198523  jnz     short loc_14019853C
0x140198525  cmp     ebx, 8
0x140198528  ja      loc_14019886B
0x14019852e  mov     eax, 143h
0x140198533  bt      eax, ebx
0x140198536  jnb     loc_14019886B
0x14019853c  mov     r8d, 6666744Eh; Tag
0x140198542  mov     r13d, 168h
0x140198548  mov     edx, r13d; NumberOfBytes
0x14019854b  mov     ecx, 210h; PoolType
0x140198550  call    cs:__imp_ExAllocatePoolWithTag
0x140198557  nop     dword ptr [rax+rax+00h]
0x14019855c  mov     [rsp+0B8h+P], rax
0x140198561  mov     rsi, rax
0x140198564  mov     [rsp+0B8h+var_80], rax
0x140198569  mov     r8d, r13d; Size
0x14019856c  xor     edx, edx; Val
0x14019856e  mov     rcx, rax; void *
0x140198571  call    memset
0x140198576  test    dil, dil
0x140198579  jnz     loc_1401989D2
0x14019857f  mov     rdi, rsi
0x140198582  or      dword ptr [rdi+4], 2
0x140198586  mov     dword ptr [rsi], 1680702h
0x14019858c  lea     rax, [rsi+30h]
0x140198590  mov     [rax+8], rax
0x140198594  mov     [rax], rax
0x140198597  mov     r13, [rsp+0B8h+arg_8]
0x14019859f  mov     [rsi+60h], r13
0x1401985a3  mov     rdi, [rsp+0B8h+arg_10]
0x1401985ab  cmp     [rsi+140h], rdi
0x1401985b2  jnz     loc_140198842
0x1401985b8  mov     [rsi+8], rbx
0x1401985bc  lea     rax, [rsi+40h]
0x1401985c0  mov     [rax+8], rax
0x1401985c4  mov     [rax], rax
0x1401985c7  xor     r14d, r14d
0x1401985ca  mov     [rsi+158h], r14
0x1401985d1  mov     [rsi+0C8h], r14
0x1401985d8  mov     [rsi+0D8h], r14
0x1401985df  test    r15d, r15d
0x1401985e2  jz      loc_140198818
0x1401985e8  lea     rcx, NtfsFcbNonpagedIndexLookasideList; Lookaside
0x1401985ef  call    cs:__imp_ExAllocateFromLookasideListEx
0x1401985f6  nop     dword ptr [rax+rax+00h]
0x1401985fb  mov     rdi, rax
0x1401985fe  test    rax, rax
0x140198601  jz      loc_1401988AF
0x140198607  mov     dword ptr [rax], 1180745h
0x14019860d  mov     rax, [rsi+8]
0x140198611  mov     [rdi+0F0h], rax
0x140198618  mov     [rdi+0F8h], rsi
0x14019861f  mov     [rdi+4], r14w
0x140198624  mov     [rsi+68h], rdi
0x140198628  mov     [rsp+0B8h+var_50], rdi
0x14019862d  test    rdi, rdi
0x140198630  jz      loc_140198990
0x140198636  lea     rdx, [rsp+0B8h+arg_18]
0x14019863e  mov     rcx, r13
0x140198641  call    NtfsReferenceMftView
0x140198646  mov     [rsp+0B8h+var_83], 1
0x14019864b  test    r12d, r12d
0x14019864e  jnz     loc_140198A21
0x140198654  cmp     ebx, 10h
0x140198657  jb      loc_140198A21
0x14019865d  mov     ecx, [rsi+4]
0x140198660  mov     eax, [r13+18h]
0x140198664  test    al, 1
0x140198666  jnz     loc_140198A2D
0x14019866c  mov     eax, [r13+18h]
0x140198670  test    al, 8
0x140198672  jnz     loc_140198A39
0x140198678  mov     byte ptr [rsi+0E8h], 0FFh
0x14019867f  mov     r9d, [rsi+4]
0x140198683  and     r9d, 400h
0x14019868a  mov     [rsp+0B8h+var_90], 1
0x140198692  mov     dword ptr [rsp+0B8h+var_98], r14d
0x140198697  lea     r8, [rsp+0B8h+arg_18]
0x14019869f  xor     edx, edx
0x1401986a1  mov     rcx, [rsi+60h]
0x1401986a5  call    TxfCreateTxfFcb
0x1401986aa  mov     [rsi+148h], rax
0x1401986b1  mov     r12, [rsp+0B8h+arg_0]
0x1401986b9  test    byte ptr [rsp+0B8h+arg_20], 40h
0x1401986c1  jnz     loc_140198A45
0x1401986c7  mov     r14, [rsp+0B8h+arg_28]
0x1401986cf  xor     edx, edx
0x1401986d1  lea     rcx, [r13+290h]
0x1401986d8  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1401986df  nop     dword ptr [rax+rax+00h]
0x1401986e4  mov     [rsp+0B8h+var_88], 1
0x1401986e9  mov     rdx, [r13+540h]
0x1401986f0  mov     [rsp+0B8h+var_60], 0
0x1401986f9  mov     [rsp+0B8h+var_60], rdx
0x1401986fe  xor     r11b, r11b
0x140198701  mov     [rsp+0B8h+var_85], r11b
0x140198706  xor     r10b, r10b
0x140198709  mov     [rsp+0B8h+var_86], r10b
0x14019870e  test    rdx, rdx
0x140198711  jz      short loc_140198787
0x140198713  mov     r15, 0FFFFFFFFFFFFh
0x14019871d  nop     dword ptr [rax]
0x140198720  mov     r9, rbx
0x140198723  shr     r9, 30h
0x140198727  mov     r8, [rdx-10h]
0x14019872b  mov     [rsp+0B8h+arg_28], r8
0x140198733  mov     rcx, r8
0x140198736  and     rcx, r15
0x140198739  mov     rax, rbx
0x14019873c  and     rax, r15
0x14019873f  cmp     rax, rcx
0x140198742  jb      short loc_140198772
0x140198744  mov     rax, rbx
0x140198747  and     rax, r15
0x14019874a  cmp     rax, rcx
0x14019874d  ja      short loc_14019875B
0x14019874f  shr     r8, 30h
0x140198753  cmp     r9w, r8w
0x140198757  jb      short loc_140198772
0x140198759  jbe     short loc_14019877F
0x14019875b  mov     rax, [rdx+8]
0x14019875f  test    rax, rax
0x140198762  jz      loc_14019880B
0x140198768  mov     rdx, rax
0x14019876b  mov     [rsp+0B8h+var_60], rax
0x140198770  jmp     short loc_140198720
0x140198772  mov     rax, [rdx]
0x140198775  test    rax, rax
0x140198778  jnz     short loc_140198768
0x14019877a  jmp     loc_14019880E
0x14019877f  mov     r10b, 1
0x140198782  mov     [rsp+0B8h+var_86], r10b
0x140198787  mov     ebx, dword ptr [rsp+0B8h+arg_20]
0x14019878e  and     ebx, 20h
0x140198791  test    r10b, r10b
0x140198794  jnz     loc_1401988FE
0x14019879a  mov     r9, [rsi+68h]
0x14019879e  add     r9, 100h
0x1401987a5  mov     rcx, [rsi+60h]
0x1401987a9  add     rcx, 540h
0x1401987b0  movzx   r8d, r11b
0x1401987b4  call    cs:__imp_RtlAvlInsertNodeEx
0x1401987bb  nop     dword ptr [rax+rax+00h]
0x1401987c0  mov     rax, [rsi+60h]
0x1401987c4  inc     dword ptr [rax+548h]
0x1401987ca  mov     eax, [rsi+4]
0x1401987cd  or      eax, 40h
0x1401987d0  mov     [rsi+4], eax
0x1401987d3  test    ebx, ebx
0x1401987d5  jz      short loc_1401987DF
0x1401987d7  lock inc dword ptr [rsi+1Ch]
0x1401987db  or      dword ptr [r14], 4
0x1401987df  lea     rcx, [r13+290h]
0x1401987e6  xor     edx, edx
0x1401987e8  call    cs:__imp_ExReleasePushLockEx
0x1401987ef  nop     dword ptr [rax+rax+00h]
0x1401987f4  xor     r12b, r12b
0x1401987f7  mov     [rsp+0B8h+var_88], r12b
0x1401987fc  mov     r15, rsi
0x1401987ff  mov     [rsp+0B8h+var_58], rsi
0x140198804  xor     bl, bl
0x140198806  jmp     loc_140198A95
0x14019880b  mov     r11b, 1
0x14019880e  mov     [rsp+0B8h+var_85], r11b
0x140198813  jmp     loc_140198787
  ... truncated ...
```
