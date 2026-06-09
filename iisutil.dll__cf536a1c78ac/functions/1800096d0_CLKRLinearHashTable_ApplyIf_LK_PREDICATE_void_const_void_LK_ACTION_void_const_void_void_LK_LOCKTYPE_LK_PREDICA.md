# CLKRLinearHashTable::_ApplyIf(LK_PREDICATE (*)(void const *,void *),LK_ACTION (*)(void const *,void *),void *,LK_LOCKTYPE,LK_PREDICATE &)

- ea: `0x1800096d0`
- end: `0x180009bc7`
- name: `?_ApplyIf@CLKRLinearHashTable@@AEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@ZP6A?AW4LK_ACTION@@01@Z1W4LK_LOCKTYPE@@AEAW42@@Z`
- size: `1271`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180016620`

## callees

- `0x180008de0`
- `0x1800096d0`
- `0x180009bd0`
- `0x180009c10`
- `0x18000be70`
- `0x18000f810`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000972a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800097e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000972a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800097e5`

## pseudocode

```c
__int64 __fastcall CLKRLinearHashTable::_ApplyIf(
        __int64 a1,
        __int64 (__fastcall *a2)(_QWORD, __int64),
        __int64 (__fastcall *a3)(_QWORD, _QWORD),
        __int64 a4,
        int a5,
        _DWORD *a6)
{
  __int64 (__fastcall *v6)(_QWORD, _QWORD); // r10
  __int64 (__fastcall *v7)(_QWORD, __int64); // r9
  int v9; // r8d
  int v11; // ebx
  unsigned int v12; // r15d
  unsigned __int64 v13; // rbx
  signed __int32 v14; // edx
  unsigned int v15; // ebp
  DWORD CurrentThreadId; // eax
  __int64 v17; // rsi
  unsigned __int16 v18; // r8
  int v19; // edi
  int v20; // edx
  signed __int32 v21; // r8d
  signed __int32 v22; // edx
  struct _SLIST_ENTRY *v23; // r12
  unsigned __int64 v24; // r13
  struct _SLIST_ENTRY *Next; // rdi
  int i; // ebp
  int v27; // eax
  __int64 v28; // rcx
  int v29; // eax
  signed __int32 v30; // edx
  signed __int32 v31; // edx
  struct _SLIST_ENTRY *v32; // rdx
  int v33; // r8d
  __int64 v34; // rax
  int v35; // r8d
  unsigned __int64 v36; // rax
  CReaderWriterLock3 *v37; // rcx
  unsigned int v38; // [rsp+70h] [rbp+8h]

  v6 = a3;
  v7 = a2;
  if ( *(_DWORD *)(a1 + 20) )
    return 4294967197LL;
  v9 = a5;
  if ( a5 == 2 )
  {
    v11 = *(_DWORD *)(a1 + 28);
    if ( ((v11 ^ GetCurrentThreadId()) & 0xFFFFFFFC) != 0 )
      return 0;
    v9 = 2;
    v7 = a2;
    v6 = a3;
  }
  else if ( (*(_DWORD *)(a1 + 24) & 0x7FFF) == 0 )
  {
    return 0;
  }
  if ( !v7 || !v6 )
    return 0;
  v12 = 0;
  v38 = 0;
  while ( 1 )
  {
    if ( v12 >= *(_DWORD *)(a1 + 124) )
      return v38;
    v13 = *(_QWORD *)(*(_QWORD *)(a1 + 104) + 8 * ((unsigned __int64)v12 >> *(_DWORD *)(a1 + 68)))
        + ((unsigned __int64)(v12 & *(_DWORD *)(a1 + 76)) << 6);
    v14 = *(_DWORD *)v13;
    if ( v9 == 2 )
    {
      if ( (_WORD)v14
        || v14 != _InterlockedCompareExchange((volatile signed __int32 *)v13, (v14 + 0x10000) | 0xFFFF, v14) )
      {
        while ( 1 )
        {
          v22 = *(_DWORD *)v13;
          if ( v22 == _InterlockedCompareExchange((volatile signed __int32 *)v13, v22 + 0x10000, v22) )
            break;
          _mm_pause();
        }
        CReaderWriterLock2::_LockSpin((CReaderWriterLock2 *)v13, 1);
LABEL_25:
        v7 = a2;
      }
    }
    else if ( (v14 & 0xFFFF8000) != 0
           || v14 != _InterlockedCompareExchange((volatile signed __int32 *)v13, v14 + 1, v14) )
    {
      v15 = 0;
      CurrentThreadId = GetCurrentThreadId();
      v17 = 0;
      v18 = CReaderWriterLock2::sm_wDefaultSpinCount;
      v19 = (int)((double)CReaderWriterLock2::sm_wDefaultSpinCount * *(double *)&qword_180032E80[CurrentThreadId % 0xD]);
      while ( 1 )
      {
        v20 = v19;
        if ( g_cProcessors < 2 || !v18 )
          v20 = 1;
        while ( --v20 >= 0 )
        {
          if ( (*(_DWORD *)v13 & 0xFFFF8000) == 0 )
          {
            v21 = *(_DWORD *)v13;
            if ( v21 == _InterlockedCompareExchange((volatile signed __int32 *)v13, v21 + 1, v21) )
              goto LABEL_25;
          }
          _mm_pause();
        }
        SwitchOrSleep(v15);
        if ( (unsigned int)v17 < 4 )
          v15 = dword_180032D40[v17];
        else
          v15 = 100;
        v19 = (int)((double)v19 * CReaderWriterLock2::sm_dblDfltSpinAdjFctr);
        if ( v19 > 10000 )
        {
          v18 = CReaderWriterLock2::sm_wDefaultSpinCount;
          v19 = 10000;
          v17 = (unsigned int)(v17 + 1);
        }
        else
        {
          v18 = CReaderWriterLock2::sm_wDefaultSpinCount;
          if ( v19 <= 100 )
            v19 = 100;
          v17 = (unsigned int)(v17 + 1);
        }
      }
    }
    v23 = (struct _SLIST_ENTRY *)(v13 + 8);
    v24 = 0;
    Next = (struct _SLIST_ENTRY *)(v13 + 8);
LABEL_27:
    if ( Next )
      break;
LABEL_40:
    v9 = a5;
    v30 = *(_DWORD *)v13;
    if ( a5 == 2 )
    {
      while ( v30 != _InterlockedCompareExchange((volatile signed __int32 *)v13, (v30 - 0x10000) & 0xFFFF0000, v30) )
      {
        _mm_pause();
        v30 = *(_DWORD *)v13;
      }
    }
    else
    {
      while ( v30 != _InterlockedCompareExchange((volatile signed __int32 *)v13, v30 - 1, v30) )
      {
        _mm_pause();
        v30 = *(_DWORD *)v13;
      }
    }
    ++v12;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= 4 )
    {
      v24 = (unsigned __int64)Next;
      Next = Next[1].Next;
      goto LABEL_27;
    }
    if ( *((_DWORD *)&Next->Next + i) == 31678523 )
      goto LABEL_40;
    v27 = v7(*((_QWORD *)&Next[1].Next + i + 1), a4);
    *a6 = v27;
    if ( v27 == 6 )
      break;
    switch ( v27 )
    {
      case 1:
        v37 = (CReaderWriterLock3 *)v13;
        if ( a5 != 2 )
          goto LABEL_86;
        goto LABEL_88;
      case 3:
      case 4:
        goto LABEL_34;
      case 5:
        goto LABEL_43;
    }
LABEL_39:
    v7 = a2;
  }
LABEL_43:
  if ( a5 == 2 )
  {
LABEL_34:
    v28 = *((_QWORD *)&Next[1].Next + i + 1);
    if ( (unsigned int)(v27 - 5) <= 1 )
    {
      (*(void (__fastcall **)(__int64, __int64))(a1 + 56))(v28, 0xFFFFFFFFLL);
      v32 = Next;
      v33 = i;
      while ( v32[1].Next )
      {
        v32 = v32[1].Next;
        v33 = 0;
      }
      do
      {
        if ( *((_DWORD *)&v32->Next + v33) == 31678523 )
          break;
        ++v33;
      }
      while ( v33 != 4 );
      v34 = v33;
      v35 = v33 - 1;
      *((_QWORD *)&Next[1].Next + i + 1) = *((_QWORD *)&v32[1].Next + v34);
      *((_DWORD *)&Next->Next + i) = *((_DWORD *)v32 + v34 - 1);
      *((_QWORD *)&v32[1].Next + v34) = 0;
      *((_DWORD *)v32 + v34 - 1) = 31678523;
      if ( i )
      {
        --i;
      }
      else if ( Next == v23 )
      {
        i = -1;
      }
      else
      {
        i = 4;
        Next = (struct _SLIST_ENTRY *)v24;
        if ( (struct _SLIST_ENTRY *)v24 == v23 )
        {
          v24 = 0;
        }
        else
        {
          v24 = v13 + 8;
          if ( *(struct _SLIST_ENTRY **)(v13 + 24) != Next )
          {
            do
              v24 = *(_QWORD *)(v24 + 16);
            while ( *(struct _SLIST_ENTRY **)(v24 + 16) != Next );
          }
        }
      }
      if ( !v35 && v32 != v23 )
      {
        v36 = v13 + 8;
        if ( *(struct _SLIST_ENTRY **)(v13 + 24) != v32 )
        {
          do
            v36 = *(_QWORD *)(v36 + 16);
          while ( *(struct _SLIST_ENTRY **)(v36 + 16) != v32 );
        }
        *(_QWORD *)(v36 + 16) = 0;
        CNodeClump::operator delete(v32);
      }
      _InterlockedDecrement((volatile signed __int32 *)(a1 + 120));
    }
    else
    {
      v29 = a3(v28, a4) - 1;
      if ( !v29 )
        goto LABEL_87;
      if ( v29 != 2 )
      {
LABEL_38:
        if ( ((*a6 - 4) & 0xFFFFFFFD) != 0 )
          goto LABEL_39;
LABEL_87:
        v37 = (CReaderWriterLock3 *)v13;
        if ( a5 != 2 )
        {
LABEL_86:
          CReaderWriterLock3::ReadUnlock(v37);
          return v38;
        }
LABEL_88:
        CReaderWriterLock2::WriteUnlock(v37);
        return v38;
      }
    }
    ++v38;
    goto LABEL_38;
  }
  while ( 1 )
  {
    v31 = *(_DWORD *)v13;
    if ( v31 == _InterlockedCompareExchange((volatile signed __int32 *)v13, v31 - 1, v31) )
      break;
    _mm_pause();
  }
  return v38;
}

```

## disassembly

```asm
0x1800096d0  mov     [rsp+arg_18], r9
0x1800096d5  mov     [rsp+arg_10], r8
0x1800096da  mov     [rsp+arg_8], rdx
0x1800096df  push    r14
0x1800096e1  sub     rsp, 60h
0x1800096e5  cmp     dword ptr [rcx+14h], 0
0x1800096e9  mov     r10, r8
0x1800096ec  mov     r9, rdx
0x1800096ef  mov     r14, rcx
0x1800096f2  jnz     loc_180009A35
0x1800096f8  mov     r8d, [rsp+68h+arg_20]
0x180009700  mov     [rsp+68h+var_10], rbx
0x180009705  cmp     r8d, 2
0x180009709  jz      short loc_180009727
0x18000970b  mov     eax, [rcx+18h]
0x18000970e  and     eax, 7FFFh
0x180009713  cmp     eax, 1
0x180009716  jnb     short loc_180009754
0x180009718  mov     rbx, [rsp+68h+var_10]
0x18000971d  xor     eax, eax
0x18000971f  add     rsp, 60h
0x180009723  pop     r14
0x180009725  retn
0x180009727  mov     ebx, [rcx+1Ch]
0x18000972a  call    cs:__imp_GetCurrentThreadId
0x180009731  nop     dword ptr [rax+rax+00h]
0x180009736  xor     eax, ebx
0x180009738  test    eax, 0FFFFFFFCh
0x18000973d  jnz     short loc_180009718
0x18000973f  mov     r8d, [rsp+68h+arg_20]
0x180009747  mov     r9, [rsp+68h+arg_8]
0x18000974c  mov     r10, [rsp+68h+arg_10]
0x180009754  test    r9, r9
0x180009757  jz      short loc_180009718
0x180009759  test    r10, r10
0x18000975c  jz      short loc_180009718
0x18000975e  mov     [rsp+68h+var_18], rbp
0x180009763  mov     [rsp+68h+var_20], rsi
0x180009768  mov     [rsp+68h+var_28], rdi
0x18000976d  mov     [rsp+68h+var_30], r12
0x180009772  mov     [rsp+68h+var_38], r13
0x180009777  mov     [rsp+68h+var_40], r15
0x18000977c  xor     r15d, r15d
0x18000977f  mov     [rsp+68h+arg_0], 0
0x180009787  lea     r13, __ImageBase
0x18000978e  mov     r12d, 64h ; 'd'
0x180009794  cmp     r15d, [r14+7Ch]
0x180009798  jnb     loc_1800099BD
0x18000979e  mov     ecx, [r14+44h]
0x1800097a2  mov     ebx, [r14+4Ch]
0x1800097a6  mov     edx, r15d
0x1800097a9  shr     rdx, cl
0x1800097ac  mov     rcx, [r14+68h]
0x1800097b0  mov     eax, r15d
0x1800097b3  and     rbx, rax
0x1800097b6  shl     rbx, 6
0x1800097ba  add     rbx, [rcx+rdx*8]
0x1800097be  mov     edx, [rbx]
0x1800097c0  cmp     r8d, 2
0x1800097c4  jz      loc_18000986B
0x1800097ca  test    edx, 0FFFF8000h
0x1800097d0  jnz     short loc_1800097E3
0x1800097d2  lea     ecx, [rdx+1]
0x1800097d5  mov     eax, edx
0x1800097d7  lock cmpxchg [rbx], ecx
0x1800097db  cmp     edx, eax
0x1800097dd  jz      loc_1800098AB
0x1800097e3  xor     ebp, ebp
0x1800097e5  call    cs:__imp_GetCurrentThreadId
0x1800097ec  nop     dword ptr [rax+rax+00h]
0x1800097f1  mov     r8d, eax
0x1800097f4  mov     eax, 4EC4EC4Fh
0x1800097f9  mul     r8d
0x1800097fc  shr     edx, 2
0x1800097ff  imul    ecx, edx, 0Dh
0x180009802  sub     r8d, ecx
0x180009805  mov     ecx, r8d
0x180009808  xor     esi, esi
0x18000980a  movzx   r8d, cs:?sm_wDefaultSpinCount@CReaderWriterLock2@@1GA; ushort CReaderWriterLock2::sm_wDefaultSpinCount
0x180009812  movd    xmm0, r8d
0x180009817  cvtdq2pd xmm0, xmm0
0x18000981b  mulsd   xmm0, ds:rva qword_180032E80[r13+rcx*8]
0x180009825  cvttsd2si edi, xmm0
0x180009829  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x180009830  mov     edx, edi
0x180009832  jb      loc_180009B8F
0x180009838  test    r8w, r8w
0x18000983c  jz      loc_180009B8F
0x180009842  sub     edx, 1
0x180009845  js      loc_1800099EC
0x18000984b  mov     r8d, [rbx]
0x18000984e  test    r8d, 0FFFF8000h
0x180009855  jnz     short loc_180009867
0x180009857  lea     ecx, [r8+1]
0x18000985b  mov     eax, r8d
0x18000985e  lock cmpxchg [rbx], ecx
0x180009862  cmp     r8d, eax
0x180009865  jz      short loc_1800098A6
0x180009867  pause
0x180009869  jmp     short loc_180009842
0x18000986b  test    dx, dx
0x18000986e  jnz     short loc_180009886
0x180009870  lea     ecx, [rdx+10000h]
0x180009876  mov     eax, edx
0x180009878  or      ecx, 0FFFFh
0x18000987e  lock cmpxchg [rbx], ecx
0x180009882  cmp     edx, eax
0x180009884  jz      short loc_1800098AB
0x180009886  mov     edx, [rbx]
0x180009888  mov     eax, edx
0x18000988a  lea     ecx, [rdx+10000h]
0x180009890  lock cmpxchg [rbx], ecx
0x180009894  cmp     edx, eax
0x180009896  jnz     loc_180009A7C
0x18000989c  mov     dl, 1; bool
0x18000989e  mov     rcx, rbx; this
0x1800098a1  call    ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x1800098a6  mov     r9, [rsp+68h+arg_8]
0x1800098ab  lea     r12, [rbx+8]
0x1800098af  xor     r13d, r13d
0x1800098b2  mov     rdi, r12
0x1800098b5  test    rdi, rdi
0x1800098b8  jz      loc_180009971
0x1800098be  xor     ebp, ebp
0x1800098c0  cmp     ebp, 4
0x1800098c3  jge     loc_180009A42
0x1800098c9  movsxd  rsi, ebp
0x1800098cc  cmp     dword ptr [rdi+rsi*4], 1E3603Bh
0x1800098d3  jz      loc_180009971
0x1800098d9  mov     rdx, [rsp+68h+arg_18]
0x1800098e1  mov     rax, r9
0x1800098e4  mov     rcx, [rdi+rsi*8+18h]
0x1800098e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098ee  mov     rcx, [rsp+68h+arg_28]
0x1800098f6  mov     [rcx], eax
0x1800098f8  cmp     eax, 6
0x1800098fb  jz      loc_18000999C
0x180009901  mov     edx, eax
0x180009903  sub     edx, 1
0x180009906  jz      loc_180009B99
0x18000990c  sub     edx, 2
0x18000990f  jnz     loc_180009B13
0x180009915  mov     rcx, [rdi+rsi*8+18h]
0x18000991a  add     eax, 0FFFFFFFBh
0x18000991d  cmp     eax, 1
0x180009920  jbe     loc_180009A83
0x180009926  mov     rdx, [rsp+68h+arg_18]
0x18000992e  mov     rax, [rsp+68h+arg_10]
0x180009936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000993b  sub     eax, 1
0x18000993e  jz      loc_180009BB0
0x180009944  cmp     eax, 2
0x180009947  jnz     short loc_18000994D
0x180009949  inc     [rsp+68h+arg_0]
0x18000994d  mov     rax, [rsp+68h+arg_28]
0x180009955  mov     eax, [rax]
0x180009957  sub     eax, 4
0x18000995a  test    eax, 0FFFFFFFDh
0x18000995f  jz      loc_180009BB0
0x180009965  mov     r9, [rsp+68h+arg_8]
0x18000996a  inc     ebp
0x18000996c  jmp     loc_1800098C0
0x180009971  mov     r8d, [rsp+68h+arg_20]
0x180009979  mov     edx, [rbx]
0x18000997b  cmp     r8d, 2
0x18000997f  jz      loc_180009A60
0x180009985  lea     ecx, [rdx-1]
0x180009988  mov     eax, edx
0x18000998a  lock cmpxchg [rbx], ecx
0x18000998e  cmp     edx, eax
0x180009990  jz      loc_180009A4E
0x180009996  pause
0x180009998  mov     edx, [rbx]
0x18000999a  jmp     short loc_180009985
0x18000999c  cmp     [rsp+68h+arg_20], 2
0x1800099a4  jz      loc_180009915
0x1800099aa  mov     edx, [rbx]
0x1800099ac  mov     eax, edx
0x1800099ae  lea     ecx, [rdx-1]
0x1800099b1  lock cmpxchg [rbx], ecx
0x1800099b5  cmp     edx, eax
0x1800099b7  jz      short loc_1800099BD
0x1800099b9  pause
0x1800099bb  jmp     short loc_1800099AA
0x1800099bd  mov     eax, [rsp+68h+arg_0]
0x1800099c1  mov     r13, [rsp+68h+var_38]
0x1800099c6  mov     r12, [rsp+68h+var_30]
0x1800099cb  mov     rdi, [rsp+68h+var_28]
0x1800099d0  mov     rsi, [rsp+68h+var_20]
0x1800099d5  mov     rbp, [rsp+68h+var_18]
0x1800099da  mov     r15, [rsp+68h+var_40]
0x1800099df  mov     rbx, [rsp+68h+var_10]
0x1800099e4  add     rsp, 60h
0x1800099e8  pop     r14
0x1800099ea  retn
0x1800099ec  mov     ecx, ebp; unsigned int
0x1800099ee  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x1800099f3  cmp     esi, 4
0x1800099f6  jb      loc_180009B2A
0x1800099fc  mov     ebp, r12d
0x1800099ff  movd    xmm0, edi
0x180009a03  cvtdq2pd xmm0, xmm0
0x180009a07  mulsd   xmm0, cs:?sm_dblDfltSpinAdjFctr@CReaderWriterLock2@@1NA; double CReaderWriterLock2::sm_dblDfltSpinAdjFctr
0x180009a0f  cvttsd2si edi, xmm0
0x180009a13  cmp     edi, 2710h
0x180009a19  jg      loc_180009B7B
0x180009a1f  movzx   r8d, cs:?sm_wDefaultSpinCount@CReaderWriterLock2@@1GA; ushort CReaderWriterLock2::sm_wDefaultSpinCount
0x180009a27  cmp     edi, 64h ; 'd'
0x180009a2a  cmovle  edi, r12d
0x180009a2e  inc     esi
0x180009a30  jmp     loc_180009829
0x180009a35  mov     eax, 0FFFFFF9Dh
0x180009a3a  add     rsp, 60h
0x180009a3e  pop     r14
0x180009a40  retn
0x180009a42  mov     r13, rdi
0x180009a45  mov     rdi, [rdi+10h]
0x180009a49  jmp     loc_1800098B5
0x180009a4e  inc     r15d
0x180009a51  jmp     loc_180009787
0x180009a60  lea     ecx, [rdx-10000h]
0x180009a66  mov     eax, edx
0x180009a68  and     ecx, 0FFFF0000h
0x180009a6e  lock cmpxchg [rbx], ecx
0x180009a72  cmp     edx, eax
0x180009a74  jz      short loc_180009A4E
0x180009a76  pause
0x180009a78  mov     edx, [rbx]
0x180009a7a  jmp     short loc_180009A60
0x180009a7c  pause
0x180009a7e  jmp     loc_180009886
0x180009a83  mov     rax, [r14+38h]
0x180009a87  mov     edx, 0FFFFFFFFh
0x180009a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a91  mov     rdx, rdi
0x180009a94  mov     r8d, ebp
0x180009a97  xor     r9d, r9d
0x180009a9a  mov     rax, [rdx+10h]
0x180009a9e  test    rax, rax
0x180009aa1  jnz     short loc_180009AFA
0x180009aa3  movsxd  rax, r8d
0x180009aa6  cmp     dword ptr [rdx+rax*4], 1E3603Bh
0x180009aad  jz      short loc_180009AB8
0x180009aaf  inc     r8d
0x180009ab2  cmp     r8d, 4
0x180009ab6  jnz     short loc_180009AA3
0x180009ab8  movsxd  rax, r8d
0x180009abb  dec     r8d
0x180009abe  mov     rcx, rax
0x180009ac1  mov     rax, [rdx+rax*8+10h]
0x180009ac6  mov     [rdi+rsi*8+18h], rax
0x180009acb  mov     eax, [rdx+rcx*4-4]
0x180009acf  mov     [rdi+rsi*4], eax
0x180009ad2  mov     [rdx+rcx*8+10h], r9
0x180009ad7  mov     dword ptr [rdx+rcx*4-4], 1E3603Bh
0x180009adf  test    ebp, ebp
0x180009ae1  jnz     short loc_180009B02
0x180009ae3  cmp     rdi, r12
0x180009ae6  jz      short loc_180009B5E
0x180009ae8  mov     ebp, 4
0x180009aed  mov     rdi, r13
0x180009af0  cmp     r13, r12
0x180009af3  jnz     short loc_180009B65
0x180009af5  mov     r13, r9
0x180009af8  jmp     short loc_180009B04
0x180009afa  mov     rdx, rax
0x180009afd  mov     r8d, r9d
0x180009b00  jmp     short loc_180009A9A
0x180009b02  dec     ebp
0x180009b04  test    r8d, r8d
0x180009b07  jz      short loc_180009B37
0x180009b09  lock dec dword ptr [r14+78h]
0x180009b0e  jmp     loc_180009949
0x180009b13  sub     edx, 1
0x180009b16  jz      loc_180009915
0x180009b1c  cmp     edx, 1
0x180009b1f  jnz     loc_180009965
0x180009b25  jmp     loc_18000999C
0x180009b2a  mov     ebp, ds:rva dword_180032D40[r13+rsi*4]
0x180009b32  jmp     loc_1800099FF
0x180009b37  cmp     rdx, r12
0x180009b3a  jz      short loc_180009B09
0x180009b3c  mov     rax, r12
0x180009b3f  cmp     [r12+10h], rdx
0x180009b44  jz      short loc_180009B50
0x180009b46  mov     rax, [rax+10h]
0x180009b4a  cmp     [rax+10h], rdx
0x180009b4e  jnz     short loc_180009B46
0x180009b50  mov     rcx, rdx; ListEntry
0x180009b53  mov     [rax+10h], r9
0x180009b57  call    ??3CNodeClump@@SAXPEAX@Z; CNodeClump::operator delete(void *)
0x180009b5c  jmp     short loc_180009B09
0x180009b5e  mov     ebp, 0FFFFFFFFh
0x180009b63  jmp     short loc_180009B04
0x180009b65  mov     r13, r12
0x180009b68  cmp     [r12+10h], rdi
0x180009b6d  jz      short loc_180009B04
0x180009b6f  mov     r13, [r13+10h]
0x180009b73  cmp     [r13+10h], rdi
0x180009b77  jnz     short loc_180009B6F
  ... truncated ...
```
