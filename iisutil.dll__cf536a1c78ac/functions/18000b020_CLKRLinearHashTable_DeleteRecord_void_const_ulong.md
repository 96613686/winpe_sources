# CLKRLinearHashTable::_DeleteRecord(void const *,ulong)

- ea: `0x18000b020`
- end: `0x18000b30a`
- name: `?_DeleteRecord@CLKRLinearHashTable@@AEAA?AW4LK_RETCODE@@PEBXK@Z`
- size: `746`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001b2b0`

## callees

- `0x180007e60`
- `0x180008470`
- `0x180008de0`
- `0x180009c10`
- `0x18000b020`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b084`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b2e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b084`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b2e0`

## pseudocode

```c
__int64 __fastcall CLKRLinearHashTable::_DeleteRecord(__int64 a1, __int64 a2, int a3)
{
  unsigned int v6; // r13d
  signed __int32 v7; // r9d
  unsigned int v8; // eax
  unsigned __int64 v9; // rbx
  signed __int32 v10; // edx
  signed __int32 v11; // edx
  struct _SLIST_ENTRY *v12; // rbp
  struct _SLIST_ENTRY *Next; // r14
  int i; // esi
  _DWORD *v15; // r15
  __int64 v16; // rcx
  char *v17; // r12
  signed __int32 v18; // edx
  double v19; // xmm6_8
  int v20; // ecx
  signed __int32 v22; // edx

  v6 = 2;
  if ( *(_DWORD *)(a1 + 28)
    || (v7 = *(_DWORD *)(a1 + 24), (_WORD)v7)
    || v7 != _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 24), (v7 + 0x10000) | 0xFFFF, v7) )
  {
    if ( (*(_DWORD *)(a1 + 28) & 0xFFFFFFFC) == (GetCurrentThreadId() & 0xFFFFFFFC) )
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 28));
    else
      CReaderWriterLock3::_WriteLockSpin((CReaderWriterLock3 *)(a1 + 24));
  }
  else
  {
    _InterlockedExchange((volatile __int32 *)(a1 + 28), GetCurrentThreadId() & 0xFFFFFFFC | 1);
  }
  v8 = *(_DWORD *)(a1 + 88) & a3;
  if ( v8 < *(_DWORD *)(a1 + 96) )
    v8 = a3 & *(_DWORD *)(a1 + 92);
  v9 = ((unsigned __int64)(v8 & *(_DWORD *)(a1 + 76)) << 6)
     + *(_QWORD *)(*(_QWORD *)(a1 + 104) + 8 * ((unsigned __int64)v8 >> *(_DWORD *)(a1 + 68)));
  if ( (unsigned __int16)*(_DWORD *)v9
    || (v10 = *(_DWORD *)v9,
        v10 != _InterlockedCompareExchange((volatile signed __int32 *)v9, (v10 + 0x10000) | 0xFFFF, v10)) )
  {
    while ( 1 )
    {
      v11 = *(_DWORD *)v9;
      if ( v11 == _InterlockedCompareExchange((volatile signed __int32 *)v9, v11 + 0x10000, v11) )
        break;
      _mm_pause();
    }
    CReaderWriterLock2::_LockSpin((CReaderWriterLock2 *)v9, 1);
  }
  if ( ((*(_BYTE *)(a1 + 28) - 1) & 3) != 0 )
  {
    _InterlockedExchange((volatile __int32 *)(a1 + 28), *(_DWORD *)(a1 + 28) - 1);
  }
  else
  {
    _InterlockedExchange((volatile __int32 *)(a1 + 28), 0);
    while ( 1 )
    {
      v22 = *(_DWORD *)(a1 + 24);
      if ( v22 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 24), (v22 - 0x10000) & 0xFFFF0000, v22) )
        break;
      _mm_pause();
    }
  }
  (*(void (__fastcall **)(__int64))(a1 + 32))(a2);
  v12 = (struct _SLIST_ENTRY *)(v9 + 8);
  Next = (struct _SLIST_ENTRY *)(v9 + 8);
LABEL_15:
  if ( Next )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= 4 )
      {
        Next = Next[1].Next;
        goto LABEL_15;
      }
      v15 = (_DWORD *)Next + i;
      if ( *v15 == 31678523 )
        goto LABEL_26;
      v16 = *((_QWORD *)&Next[1].Next + i + 1);
      v17 = (char *)Next + 8 * i;
      if ( v16 == a2 )
        break;
    }
    (*(void (__fastcall **)(__int64, __int64))(a1 + 56))(v16, 0xFFFFFFFFLL);
    v6 = 0;
    while ( Next[1].Next )
    {
      Next = Next[1].Next;
      i = 0;
    }
    do
    {
      if ( *((_DWORD *)&Next->Next + i) == 31678523 )
        break;
      ++i;
    }
    while ( i != 4 );
    *((_QWORD *)v17 + 3) = *((_QWORD *)&Next[1].Next + i);
    *v15 = *((_DWORD *)Next + i - 1);
    *((_QWORD *)&Next[1].Next + i) = 0;
    *((_DWORD *)Next + i - 1) = 31678523;
    if ( i == 1 && Next != v12 )
    {
      if ( *(struct _SLIST_ENTRY **)(v9 + 24) != Next )
      {
        do
          v12 = v12[1].Next;
        while ( v12[1].Next != Next );
      }
      v12[1].Next = 0;
      CNodeClump::operator delete(Next);
    }
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 120));
  }
LABEL_26:
  while ( 1 )
  {
    v18 = *(_DWORD *)v9;
    if ( v18 == _InterlockedCompareExchange((volatile signed __int32 *)v9, (v18 - 0x10000) & 0xFFFF0000, v18) )
      break;
    _mm_pause();
  }
  if ( v6 )
    return v6;
  v19 = (double)(*(_DWORD *)(a1 + 120) + (*(_DWORD *)(a1 + 120) >> 4));
  do
    v20 = *(_DWORD *)(a1 + 124);
  while ( (double)v20 * *(double *)(a1 + 80) > v19
       && (unsigned int)v20 > *(_DWORD *)(a1 + 72)
       && !(unsigned int)CLKRLinearHashTable::_Contract(a1) );
  return 0;
}

```

## disassembly

```asm
0x18000b020  mov     rax, rsp
0x18000b023  mov     [rax+10h], rdx
0x18000b027  push    rdi
0x18000b028  push    r13
0x18000b02a  sub     rsp, 48h
0x18000b02e  mov     [rax+8], rbx
0x18000b032  mov     rdi, rcx
0x18000b035  mov     [rax+18h], rbp
0x18000b039  mov     ebx, r8d
0x18000b03c  mov     [rax+20h], rsi
0x18000b040  mov     rbp, rdx
0x18000b043  mov     [rax-18h], r12
0x18000b047  mov     r13d, 2
0x18000b04d  mov     [rax-20h], r14
0x18000b051  mov     [rax-28h], r15
0x18000b055  mov     eax, [rcx+1Ch]
0x18000b058  test    eax, eax
0x18000b05a  jnz     short loc_18000B084
0x18000b05c  mov     r9d, [rcx+18h]
0x18000b060  test    r9w, r9w
0x18000b064  jnz     short loc_18000B084
0x18000b066  lea     ecx, [r9+10000h]
0x18000b06d  mov     eax, r9d
0x18000b070  or      ecx, 0FFFFh
0x18000b076  lock cmpxchg [rdi+18h], ecx
0x18000b07b  cmp     r9d, eax
0x18000b07e  jz      loc_18000B2E0
0x18000b084  call    cs:__imp_GetCurrentThreadId
0x18000b08b  nop     dword ptr [rax+rax+00h]
0x18000b090  mov     ecx, [rdi+1Ch]
0x18000b093  and     eax, 0FFFFFFFCh
0x18000b096  and     ecx, 0FFFFFFFCh
0x18000b099  cmp     ecx, eax
0x18000b09b  jz      loc_18000B301
0x18000b0a1  lea     rcx, [rdi+18h]; this
0x18000b0a5  call    ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
0x18000b0aa  mov     eax, ebx
0x18000b0ac  and     eax, [rdi+58h]
0x18000b0af  cmp     eax, [rdi+60h]
0x18000b0b2  jnb     short loc_18000B0B9
0x18000b0b4  mov     eax, [rdi+5Ch]
0x18000b0b7  and     eax, ebx
0x18000b0b9  mov     ecx, [rdi+44h]
0x18000b0bc  mov     edx, [rdi+4Ch]
0x18000b0bf  and     rdx, rax
0x18000b0c2  mov     r8d, eax
0x18000b0c5  shr     r8, cl
0x18000b0c8  mov     rcx, [rdi+68h]
0x18000b0cc  shl     rdx, 6
0x18000b0d0  mov     rbx, [rcx+r8*8]
0x18000b0d4  add     rbx, rdx
0x18000b0d7  mov     edx, [rbx]
0x18000b0d9  test    dx, dx
0x18000b0dc  jnz     short loc_18000B0F4
0x18000b0de  lea     ecx, [rdx+10000h]
0x18000b0e4  mov     eax, edx
0x18000b0e6  or      ecx, 0FFFFh
0x18000b0ec  lock cmpxchg [rbx], ecx
0x18000b0f0  cmp     edx, eax
0x18000b0f2  jz      short loc_18000B114
0x18000b0f4  mov     edx, [rbx]
0x18000b0f6  mov     eax, edx
0x18000b0f8  lea     ecx, [rdx+10000h]
0x18000b0fe  lock cmpxchg [rbx], ecx
0x18000b102  cmp     edx, eax
0x18000b104  jnz     loc_18000B2FA
0x18000b10a  mov     dl, 1; bool
0x18000b10c  mov     rcx, rbx; this
0x18000b10f  call    ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x18000b114  mov     eax, [rdi+1Ch]
0x18000b117  dec     eax
0x18000b119  test    al, 3
0x18000b11b  jz      loc_18000B283
0x18000b121  xchg    eax, [rdi+1Ch]
0x18000b124  mov     rax, [rdi+20h]
0x18000b128  mov     rcx, rbp
0x18000b12b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b130  mov     rdx, [rsp+58h+arg_8]
0x18000b135  lea     rbp, [rbx+8]
0x18000b139  mov     r14, rbp
0x18000b13c  test    r14, r14
0x18000b13f  jz      loc_18000B1D7
0x18000b145  xor     esi, esi
0x18000b147  cmp     esi, 4
0x18000b14a  jge     loc_18000B273
0x18000b150  movsxd  rax, esi
0x18000b153  cmp     dword ptr [r14+rax*4], 1E3603Bh
0x18000b15b  lea     r15, [r14+rax*4]
0x18000b15f  jz      short loc_18000B1D7
0x18000b161  mov     rcx, [r14+rax*8+18h]
0x18000b166  lea     r12, [r14+rax*8]
0x18000b16a  cmp     rcx, rdx
0x18000b16d  jnz     loc_18000B27C
0x18000b173  mov     rax, [rdi+38h]
0x18000b177  mov     edx, 0FFFFFFFFh
0x18000b17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b181  xor     r13d, r13d
0x18000b184  mov     rax, [r14+10h]
0x18000b188  test    rax, rax
0x18000b18b  jnz     loc_18000B268
0x18000b191  movsxd  rax, esi
0x18000b194  cmp     dword ptr [r14+rax*4], 1E3603Bh
0x18000b19c  jz      short loc_18000B1A5
0x18000b19e  inc     esi
0x18000b1a0  cmp     esi, 4
0x18000b1a3  jnz     short loc_18000B191
0x18000b1a5  movsxd  rcx, esi
0x18000b1a8  mov     rax, [r14+rcx*8+10h]
0x18000b1ad  mov     [r12+18h], rax
0x18000b1b2  mov     eax, [r14+rcx*4-4]
0x18000b1b7  mov     [r15], eax
0x18000b1ba  lea     eax, [rsi-1]
0x18000b1bd  mov     [r14+rcx*8+10h], r13
0x18000b1c2  mov     dword ptr [r14+rcx*4-4], 1E3603Bh
0x18000b1cb  test    eax, eax
0x18000b1cd  jz      loc_18000B2B6
0x18000b1d3  lock dec dword ptr [rdi+78h]
0x18000b1d7  mov     r15, [rsp+58h+var_28]
0x18000b1dc  mov     r14, [rsp+58h+var_20]
0x18000b1e1  mov     r12, [rsp+58h+var_18]
0x18000b1e6  mov     rsi, [rsp+58h+arg_18]
0x18000b1eb  mov     rbp, [rsp+58h+arg_10]
0x18000b1f0  mov     edx, [rbx]
0x18000b1f2  mov     eax, edx
0x18000b1f4  lea     ecx, [rdx-10000h]
0x18000b1fa  and     ecx, 0FFFF0000h
0x18000b200  lock cmpxchg [rbx], ecx
0x18000b204  cmp     edx, eax
0x18000b206  jz      short loc_18000B20C
0x18000b208  pause
0x18000b20a  jmp     short loc_18000B1F0
0x18000b20c  mov     rbx, [rsp+58h+arg_0]
0x18000b211  test    r13d, r13d
0x18000b214  jnz     loc_18000B2AA
0x18000b21a  mov     eax, [rdi+78h]
0x18000b21d  shr     eax, 4
0x18000b220  add     eax, [rdi+78h]
0x18000b223  movaps  [rsp+58h+var_38], xmm6
0x18000b228  xorps   xmm6, xmm6
0x18000b22b  cvtsi2sd xmm6, rax
0x18000b230  mov     ecx, [rdi+7Ch]
0x18000b233  xorps   xmm0, xmm0
0x18000b236  cvtsi2sd xmm0, rcx
0x18000b23b  mulsd   xmm0, qword ptr [rdi+50h]
0x18000b240  comisd  xmm0, xmm6
0x18000b244  jbe     short loc_18000B257
0x18000b246  cmp     ecx, [rdi+48h]
0x18000b249  jbe     short loc_18000B257
0x18000b24b  mov     rcx, rdi
0x18000b24e  call    ?_Contract@CLKRLinearHashTable@@AEAA?AW4LK_RETCODE@@XZ; CLKRLinearHashTable::_Contract(void)
0x18000b253  test    eax, eax
0x18000b255  jz      short loc_18000B230
0x18000b257  movaps  xmm6, [rsp+58h+var_38]
0x18000b25c  mov     eax, r13d
0x18000b25f  add     rsp, 48h
0x18000b263  pop     r13
0x18000b265  pop     rdi
0x18000b266  retn
0x18000b268  mov     r14, rax
0x18000b26b  mov     esi, r13d
0x18000b26e  jmp     loc_18000B184
0x18000b273  mov     r14, [r14+10h]
0x18000b277  jmp     loc_18000B13C
0x18000b27c  inc     esi
0x18000b27e  jmp     loc_18000B147
0x18000b283  xor     eax, eax
0x18000b285  xchg    eax, [rdi+1Ch]
0x18000b288  mov     edx, [rdi+18h]
0x18000b28b  mov     eax, edx
0x18000b28d  lea     ecx, [rdx-10000h]
0x18000b293  and     ecx, 0FFFF0000h
0x18000b299  lock cmpxchg [rdi+18h], ecx
0x18000b29e  cmp     edx, eax
0x18000b2a0  jz      loc_18000B124
0x18000b2a6  pause
0x18000b2a8  jmp     short loc_18000B288
0x18000b2aa  mov     eax, r13d
0x18000b2ad  add     rsp, 48h
0x18000b2b1  pop     r13
0x18000b2b3  pop     rdi
0x18000b2b4  retn
0x18000b2b6  cmp     r14, rbp
0x18000b2b9  jz      loc_18000B1D3
0x18000b2bf  cmp     [rbp+10h], r14
0x18000b2c3  jz      short loc_18000B2CF
0x18000b2c5  mov     rbp, [rbp+10h]
0x18000b2c9  cmp     [rbp+10h], r14
0x18000b2cd  jnz     short loc_18000B2C5
0x18000b2cf  mov     rcx, r14; ListEntry
0x18000b2d2  mov     [rbp+10h], r13
0x18000b2d6  call    ??3CNodeClump@@SAXPEAX@Z; CNodeClump::operator delete(void *)
0x18000b2db  jmp     loc_18000B1D3
0x18000b2e0  call    cs:__imp_GetCurrentThreadId
0x18000b2e7  nop     dword ptr [rax+rax+00h]
0x18000b2ec  and     eax, 0FFFFFFFCh
0x18000b2ef  or      eax, 1
0x18000b2f2  xchg    eax, [rdi+1Ch]
0x18000b2f5  jmp     loc_18000B0AA
0x18000b2fa  pause
0x18000b2fc  jmp     loc_18000B0F4
0x18000b301  lock inc dword ptr [rdi+1Ch]
0x18000b305  jmp     loc_18000B0AA
```
