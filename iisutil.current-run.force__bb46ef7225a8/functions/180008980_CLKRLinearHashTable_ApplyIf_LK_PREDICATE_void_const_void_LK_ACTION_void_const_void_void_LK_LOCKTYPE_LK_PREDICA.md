# CLKRLinearHashTable::_ApplyIf(LK_PREDICATE (*)(void const *,void *),LK_ACTION (*)(void const *,void *),void *,LK_LOCKTYPE,LK_PREDICATE &)

- ea: `0x180008980`
- end: `0x180008e67`
- name: `?_ApplyIf@CLKRLinearHashTable@@AEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@ZP6A?AW4LK_ACTION@@01@Z1W4LK_LOCKTYPE@@AEAW42@@Z`
- size: `1255`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180015990`

## callees

- `0x1800080a0`
- `0x180008980`
- `0x180008e70`
- `0x180008eb0`
- `0x18000ada0`
- `0x18000e850`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800089d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008a8e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800089d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008a8e`

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
      v19 = (int)((double)CReaderWriterLock2::sm_wDefaultSpinCount * *(double *)&qword_180030E80[CurrentThreadId % 0xD]);
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
          v15 = dword_180030D30[v17];
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
0x180008980  mov     [rsp+arg_18], r9
0x180008985  mov     [rsp+arg_10], r8
0x18000898a  mov     [rsp+arg_8], rdx
0x18000898f  push    r14
0x180008991  sub     rsp, 60h
0x180008995  cmp     dword ptr [rcx+14h], 0
0x180008999  mov     r10, r8
0x18000899c  mov     r9, rdx
0x18000899f  mov     r14, rcx
0x1800089a2  jnz     loc_180008CDF
0x1800089a8  mov     r8d, [rsp+68h+arg_20]
0x1800089b0  mov     [rsp+68h+var_10], rbx
0x1800089b5  cmp     r8d, 2
0x1800089b9  jz      short loc_1800089D6
0x1800089bb  mov     eax, [rcx+18h]
0x1800089be  and     eax, 7FFFh
0x1800089c3  cmp     eax, 1
0x1800089c6  jnb     short loc_1800089FD
0x1800089c8  mov     rbx, [rsp+68h+var_10]
0x1800089cd  xor     eax, eax
0x1800089cf  add     rsp, 60h
0x1800089d3  pop     r14
0x1800089d5  retn
0x1800089d6  mov     ebx, [rcx+1Ch]
0x1800089d9  call    cs:__imp_GetCurrentThreadId
0x1800089df  xor     eax, ebx
0x1800089e1  test    eax, 0FFFFFFFCh
0x1800089e6  jnz     short loc_1800089C8
0x1800089e8  mov     r8d, [rsp+68h+arg_20]
0x1800089f0  mov     r9, [rsp+68h+arg_8]
0x1800089f5  mov     r10, [rsp+68h+arg_10]
0x1800089fd  test    r9, r9
0x180008a00  jz      short loc_1800089C8
0x180008a02  test    r10, r10
0x180008a05  jz      short loc_1800089C8
0x180008a07  mov     [rsp+68h+var_18], rbp
0x180008a0c  mov     [rsp+68h+var_20], rsi
0x180008a11  mov     [rsp+68h+var_28], rdi
0x180008a16  mov     [rsp+68h+var_30], r12
0x180008a1b  mov     [rsp+68h+var_38], r13
0x180008a20  mov     [rsp+68h+var_40], r15
0x180008a25  xor     r15d, r15d
0x180008a28  mov     [rsp+68h+arg_0], 0
0x180008a30  lea     r13, __ImageBase
0x180008a37  mov     r12d, 64h ; 'd'
0x180008a3d  cmp     r15d, [r14+7Ch]
0x180008a41  jnb     loc_180008C68
0x180008a47  mov     ecx, [r14+44h]
0x180008a4b  mov     ebx, [r14+4Ch]
0x180008a4f  mov     edx, r15d
0x180008a52  shr     rdx, cl
0x180008a55  mov     rcx, [r14+68h]
0x180008a59  mov     eax, r15d
0x180008a5c  and     rbx, rax
0x180008a5f  shl     rbx, 6
0x180008a63  add     rbx, [rcx+rdx*8]
0x180008a67  mov     edx, [rbx]
0x180008a69  cmp     r8d, 2
0x180008a6d  jz      loc_180008B0E
0x180008a73  test    edx, 0FFFF8000h
0x180008a79  jnz     short loc_180008A8C
0x180008a7b  lea     ecx, [rdx+1]
0x180008a7e  mov     eax, edx
0x180008a80  lock cmpxchg [rbx], ecx
0x180008a84  cmp     edx, eax
0x180008a86  jz      loc_180008B4E
0x180008a8c  xor     ebp, ebp
0x180008a8e  call    cs:__imp_GetCurrentThreadId
0x180008a94  mov     r8d, eax
0x180008a97  mov     eax, 4EC4EC4Fh
0x180008a9c  mul     r8d
0x180008a9f  shr     edx, 2
0x180008aa2  imul    ecx, edx, 0Dh
0x180008aa5  sub     r8d, ecx
0x180008aa8  mov     ecx, r8d
0x180008aab  xor     esi, esi
0x180008aad  movzx   r8d, cs:?sm_wDefaultSpinCount@CReaderWriterLock2@@1GA; ushort CReaderWriterLock2::sm_wDefaultSpinCount
0x180008ab5  movd    xmm0, r8d
0x180008aba  cvtdq2pd xmm0, xmm0
0x180008abe  mulsd   xmm0, ds:rva qword_180030E80[r13+rcx*8]
0x180008ac8  cvttsd2si edi, xmm0
0x180008acc  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x180008ad3  mov     edx, edi
0x180008ad5  jb      loc_180008E2F
0x180008adb  test    r8w, r8w
0x180008adf  jz      loc_180008E2F
0x180008ae5  sub     edx, 1
0x180008ae8  js      loc_180008C96
0x180008aee  mov     r8d, [rbx]
0x180008af1  test    r8d, 0FFFF8000h
0x180008af8  jnz     short loc_180008B0A
0x180008afa  lea     ecx, [r8+1]
0x180008afe  mov     eax, r8d
0x180008b01  lock cmpxchg [rbx], ecx
0x180008b05  cmp     r8d, eax
0x180008b08  jz      short loc_180008B49
0x180008b0a  pause
0x180008b0c  jmp     short loc_180008AE5
0x180008b0e  test    dx, dx
0x180008b11  jnz     short loc_180008B29
0x180008b13  lea     ecx, [rdx+10000h]
0x180008b19  mov     eax, edx
0x180008b1b  or      ecx, 0FFFFh
0x180008b21  lock cmpxchg [rbx], ecx
0x180008b25  cmp     edx, eax
0x180008b27  jz      short loc_180008B4E
0x180008b29  mov     edx, [rbx]
0x180008b2b  mov     eax, edx
0x180008b2d  lea     ecx, [rdx+10000h]
0x180008b33  lock cmpxchg [rbx], ecx
0x180008b37  cmp     edx, eax
0x180008b39  jnz     loc_180008D1C
0x180008b3f  mov     dl, 1; bool
0x180008b41  mov     rcx, rbx; this
0x180008b44  call    ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x180008b49  mov     r9, [rsp+68h+arg_8]
0x180008b4e  lea     r12, [rbx+8]
0x180008b52  xor     r13d, r13d
0x180008b55  mov     rdi, r12
0x180008b58  test    rdi, rdi
0x180008b5b  jz      loc_180008C14
0x180008b61  xor     ebp, ebp
0x180008b63  cmp     ebp, 4
0x180008b66  jge     loc_180008CEB
0x180008b6c  movsxd  rsi, ebp
0x180008b6f  cmp     dword ptr [rdi+rsi*4], 1E3603Bh
0x180008b76  jz      loc_180008C14
0x180008b7c  mov     rdx, [rsp+68h+arg_18]
0x180008b84  mov     rax, r9
0x180008b87  mov     rcx, [rdi+rsi*8+18h]
0x180008b8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b91  mov     rcx, [rsp+68h+arg_28]
0x180008b99  mov     [rcx], eax
0x180008b9b  cmp     eax, 6
0x180008b9e  jz      loc_180008C47
0x180008ba4  mov     edx, eax
0x180008ba6  sub     edx, 1
0x180008ba9  jz      loc_180008E39
0x180008baf  sub     edx, 2
0x180008bb2  jnz     loc_180008DB3
0x180008bb8  mov     rcx, [rdi+rsi*8+18h]
0x180008bbd  add     eax, 0FFFFFFFBh
0x180008bc0  cmp     eax, 1
0x180008bc3  jbe     loc_180008D23
0x180008bc9  mov     rdx, [rsp+68h+arg_18]
0x180008bd1  mov     rax, [rsp+68h+arg_10]
0x180008bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bde  sub     eax, 1
0x180008be1  jz      loc_180008E50
0x180008be7  cmp     eax, 2
0x180008bea  jnz     short loc_180008BF0
0x180008bec  inc     [rsp+68h+arg_0]
0x180008bf0  mov     rax, [rsp+68h+arg_28]
0x180008bf8  mov     eax, [rax]
0x180008bfa  sub     eax, 4
0x180008bfd  test    eax, 0FFFFFFFDh
0x180008c02  jz      loc_180008E50
0x180008c08  mov     r9, [rsp+68h+arg_8]
0x180008c0d  inc     ebp
0x180008c0f  jmp     loc_180008B63
0x180008c14  mov     r8d, [rsp+68h+arg_20]
0x180008c1c  mov     edx, [rbx]
0x180008c1e  cmp     r8d, 2
0x180008c22  jz      loc_180008D00
0x180008c28  nop     dword ptr [rax+rax+00000000h]
0x180008c30  lea     ecx, [rdx-1]
0x180008c33  mov     eax, edx
0x180008c35  lock cmpxchg [rbx], ecx
0x180008c39  cmp     edx, eax
0x180008c3b  jz      loc_180008CF7
0x180008c41  pause
0x180008c43  mov     edx, [rbx]
0x180008c45  jmp     short loc_180008C30
0x180008c47  cmp     [rsp+68h+arg_20], 2
0x180008c4f  jz      loc_180008BB8
0x180008c55  mov     edx, [rbx]
0x180008c57  mov     eax, edx
0x180008c59  lea     ecx, [rdx-1]
0x180008c5c  lock cmpxchg [rbx], ecx
0x180008c60  cmp     edx, eax
0x180008c62  jz      short loc_180008C68
0x180008c64  pause
0x180008c66  jmp     short loc_180008C55
0x180008c68  mov     eax, [rsp+68h+arg_0]
0x180008c6c  mov     r13, [rsp+68h+var_38]
0x180008c71  mov     r12, [rsp+68h+var_30]
0x180008c76  mov     rdi, [rsp+68h+var_28]
0x180008c7b  mov     rsi, [rsp+68h+var_20]
0x180008c80  mov     rbp, [rsp+68h+var_18]
0x180008c85  mov     r15, [rsp+68h+var_40]
0x180008c8a  mov     rbx, [rsp+68h+var_10]
0x180008c8f  add     rsp, 60h
0x180008c93  pop     r14
0x180008c95  retn
0x180008c96  mov     ecx, ebp; unsigned int
0x180008c98  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x180008c9d  cmp     esi, 4
0x180008ca0  jb      loc_180008DCA
0x180008ca6  mov     ebp, r12d
0x180008ca9  movd    xmm0, edi
0x180008cad  cvtdq2pd xmm0, xmm0
0x180008cb1  mulsd   xmm0, cs:?sm_dblDfltSpinAdjFctr@CReaderWriterLock2@@1NA; double CReaderWriterLock2::sm_dblDfltSpinAdjFctr
0x180008cb9  cvttsd2si edi, xmm0
0x180008cbd  cmp     edi, 2710h
0x180008cc3  jg      loc_180008E1B
0x180008cc9  movzx   r8d, cs:?sm_wDefaultSpinCount@CReaderWriterLock2@@1GA; ushort CReaderWriterLock2::sm_wDefaultSpinCount
0x180008cd1  cmp     edi, 64h ; 'd'
0x180008cd4  cmovle  edi, r12d
0x180008cd8  inc     esi
0x180008cda  jmp     loc_180008ACC
0x180008cdf  mov     eax, 0FFFFFF9Dh
0x180008ce4  add     rsp, 60h
0x180008ce8  pop     r14
0x180008cea  retn
0x180008ceb  mov     r13, rdi
0x180008cee  mov     rdi, [rdi+10h]
0x180008cf2  jmp     loc_180008B58
0x180008cf7  inc     r15d
0x180008cfa  jmp     loc_180008A30
0x180008d00  lea     ecx, [rdx-10000h]
0x180008d06  mov     eax, edx
0x180008d08  and     ecx, 0FFFF0000h
0x180008d0e  lock cmpxchg [rbx], ecx
0x180008d12  cmp     edx, eax
0x180008d14  jz      short loc_180008CF7
0x180008d16  pause
0x180008d18  mov     edx, [rbx]
0x180008d1a  jmp     short loc_180008D00
0x180008d1c  pause
0x180008d1e  jmp     loc_180008B29
0x180008d23  mov     rax, [r14+38h]
0x180008d27  mov     edx, 0FFFFFFFFh
0x180008d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d31  mov     rdx, rdi
0x180008d34  mov     r8d, ebp
0x180008d37  xor     r9d, r9d
0x180008d3a  mov     rax, [rdx+10h]
0x180008d3e  test    rax, rax
0x180008d41  jnz     short loc_180008D9A
0x180008d43  movsxd  rax, r8d
0x180008d46  cmp     dword ptr [rdx+rax*4], 1E3603Bh
0x180008d4d  jz      short loc_180008D58
0x180008d4f  inc     r8d
0x180008d52  cmp     r8d, 4
0x180008d56  jnz     short loc_180008D43
0x180008d58  movsxd  rax, r8d
0x180008d5b  dec     r8d
0x180008d5e  mov     rcx, rax
0x180008d61  mov     rax, [rdx+rax*8+10h]
0x180008d66  mov     [rdi+rsi*8+18h], rax
0x180008d6b  mov     eax, [rdx+rcx*4-4]
0x180008d6f  mov     [rdi+rsi*4], eax
0x180008d72  mov     [rdx+rcx*8+10h], r9
0x180008d77  mov     dword ptr [rdx+rcx*4-4], 1E3603Bh
0x180008d7f  test    ebp, ebp
0x180008d81  jnz     short loc_180008DA2
0x180008d83  cmp     rdi, r12
0x180008d86  jz      short loc_180008DFE
0x180008d88  mov     ebp, 4
0x180008d8d  mov     rdi, r13
0x180008d90  cmp     r13, r12
0x180008d93  jnz     short loc_180008E05
0x180008d95  mov     r13, r9
0x180008d98  jmp     short loc_180008DA4
0x180008d9a  mov     rdx, rax
0x180008d9d  mov     r8d, r9d
0x180008da0  jmp     short loc_180008D3A
0x180008da2  dec     ebp
0x180008da4  test    r8d, r8d
0x180008da7  jz      short loc_180008DD7
0x180008da9  lock dec dword ptr [r14+78h]
0x180008dae  jmp     loc_180008BEC
0x180008db3  sub     edx, 1
0x180008db6  jz      loc_180008BB8
0x180008dbc  cmp     edx, 1
0x180008dbf  jnz     loc_180008C08
0x180008dc5  jmp     loc_180008C47
0x180008dca  mov     ebp, ds:rva dword_180030D30[r13+rsi*4]
0x180008dd2  jmp     loc_180008CA9
0x180008dd7  cmp     rdx, r12
0x180008dda  jz      short loc_180008DA9
0x180008ddc  mov     rax, r12
0x180008ddf  cmp     [r12+10h], rdx
0x180008de4  jz      short loc_180008DF0
0x180008de6  mov     rax, [rax+10h]
0x180008dea  cmp     [rax+10h], rdx
0x180008dee  jnz     short loc_180008DE6
0x180008df0  mov     rcx, rdx; ListEntry
0x180008df3  mov     [rax+10h], r9
0x180008df7  call    ??3CNodeClump@@SAXPEAX@Z; CNodeClump::operator delete(void *)
0x180008dfc  jmp     short loc_180008DA9
0x180008dfe  mov     ebp, 0FFFFFFFFh
0x180008e03  jmp     short loc_180008DA4
0x180008e05  mov     r13, r12
0x180008e08  cmp     [r12+10h], rdi
0x180008e0d  jz      short loc_180008DA4
0x180008e0f  mov     r13, [r13+10h]
0x180008e13  cmp     [r13+10h], rdi
0x180008e17  jnz     short loc_180008E0F
0x180008e19  jmp     short loc_180008DA4
  ... truncated ...
```
