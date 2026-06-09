# CLKRLinearHashTable::_DeleteRecord(void const *,ulong)

- ea: `0x18000a110`
- end: `0x18000a3ec`
- name: `?_DeleteRecord@CLKRLinearHashTable@@AEAA?AW4LK_RETCODE@@PEBXK@Z`
- size: `732`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001a3d0`

## callees

- `0x180007180`
- `0x180007750`
- `0x1800080a0`
- `0x180008eb0`
- `0x18000a110`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a174`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a3c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a174`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a3c8`

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
0x18000a110  mov     rax, rsp
0x18000a113  mov     [rax+10h], rdx
0x18000a117  push    rdi
0x18000a118  push    r13
0x18000a11a  sub     rsp, 48h
0x18000a11e  mov     [rax+8], rbx
0x18000a122  mov     rdi, rcx
0x18000a125  mov     [rax+18h], rbp
0x18000a129  mov     ebx, r8d
0x18000a12c  mov     [rax+20h], rsi
0x18000a130  mov     rbp, rdx
0x18000a133  mov     [rax-18h], r12
0x18000a137  mov     r13d, 2
0x18000a13d  mov     [rax-20h], r14
0x18000a141  mov     [rax-28h], r15
0x18000a145  mov     eax, [rcx+1Ch]
0x18000a148  test    eax, eax
0x18000a14a  jnz     short loc_18000A174
0x18000a14c  mov     r9d, [rcx+18h]
0x18000a150  test    r9w, r9w
0x18000a154  jnz     short loc_18000A174
0x18000a156  lea     ecx, [r9+10000h]
0x18000a15d  mov     eax, r9d
0x18000a160  or      ecx, 0FFFFh
0x18000a166  lock cmpxchg [rdi+18h], ecx
0x18000a16b  cmp     r9d, eax
0x18000a16e  jz      loc_18000A3C8
0x18000a174  call    cs:__imp_GetCurrentThreadId
0x18000a17a  mov     ecx, [rdi+1Ch]
0x18000a17d  and     eax, 0FFFFFFFCh
0x18000a180  and     ecx, 0FFFFFFFCh
0x18000a183  cmp     ecx, eax
0x18000a185  jz      loc_18000A3E3
0x18000a18b  lea     rcx, [rdi+18h]; this
0x18000a18f  call    ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
0x18000a194  mov     eax, ebx
0x18000a196  and     eax, [rdi+58h]
0x18000a199  cmp     eax, [rdi+60h]
0x18000a19c  jnb     short loc_18000A1A3
0x18000a19e  mov     eax, [rdi+5Ch]
0x18000a1a1  and     eax, ebx
0x18000a1a3  mov     ecx, [rdi+44h]
0x18000a1a6  mov     edx, [rdi+4Ch]
0x18000a1a9  and     rdx, rax
0x18000a1ac  mov     r8d, eax
0x18000a1af  shr     r8, cl
0x18000a1b2  mov     rcx, [rdi+68h]
0x18000a1b6  shl     rdx, 6
0x18000a1ba  mov     rbx, [rcx+r8*8]
0x18000a1be  add     rbx, rdx
0x18000a1c1  mov     edx, [rbx]
0x18000a1c3  test    dx, dx
0x18000a1c6  jnz     short loc_18000A1DE
0x18000a1c8  lea     ecx, [rdx+10000h]
0x18000a1ce  mov     eax, edx
0x18000a1d0  or      ecx, 0FFFFh
0x18000a1d6  lock cmpxchg [rbx], ecx
0x18000a1da  cmp     edx, eax
0x18000a1dc  jz      short loc_18000A1FE
0x18000a1de  mov     edx, [rbx]
0x18000a1e0  mov     eax, edx
0x18000a1e2  lea     ecx, [rdx+10000h]
0x18000a1e8  lock cmpxchg [rbx], ecx
0x18000a1ec  cmp     edx, eax
0x18000a1ee  jnz     loc_18000A3DC
0x18000a1f4  mov     dl, 1; bool
0x18000a1f6  mov     rcx, rbx; this
0x18000a1f9  call    ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x18000a1fe  mov     eax, [rdi+1Ch]
0x18000a201  dec     eax
0x18000a203  test    al, 3
0x18000a205  jz      loc_18000A36C
0x18000a20b  xchg    eax, [rdi+1Ch]
0x18000a20e  mov     rax, [rdi+20h]
0x18000a212  mov     rcx, rbp
0x18000a215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a21a  mov     rdx, [rsp+58h+arg_8]
0x18000a21f  lea     rbp, [rbx+8]
0x18000a223  mov     r14, rbp
0x18000a226  test    r14, r14
0x18000a229  jz      loc_18000A2C1
0x18000a22f  xor     esi, esi
0x18000a231  cmp     esi, 4
0x18000a234  jge     loc_18000A35C
0x18000a23a  movsxd  rax, esi
0x18000a23d  cmp     dword ptr [r14+rax*4], 1E3603Bh
0x18000a245  lea     r15, [r14+rax*4]
0x18000a249  jz      short loc_18000A2C1
0x18000a24b  mov     rcx, [r14+rax*8+18h]
0x18000a250  lea     r12, [r14+rax*8]
0x18000a254  cmp     rcx, rdx
0x18000a257  jnz     loc_18000A365
0x18000a25d  mov     rax, [rdi+38h]
0x18000a261  mov     edx, 0FFFFFFFFh
0x18000a266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a26b  xor     r13d, r13d
0x18000a26e  mov     rax, [r14+10h]
0x18000a272  test    rax, rax
0x18000a275  jnz     loc_18000A351
0x18000a27b  movsxd  rax, esi
0x18000a27e  cmp     dword ptr [r14+rax*4], 1E3603Bh
0x18000a286  jz      short loc_18000A28F
0x18000a288  inc     esi
0x18000a28a  cmp     esi, 4
0x18000a28d  jnz     short loc_18000A27B
0x18000a28f  movsxd  rcx, esi
0x18000a292  mov     rax, [r14+rcx*8+10h]
0x18000a297  mov     [r12+18h], rax
0x18000a29c  mov     eax, [r14+rcx*4-4]
0x18000a2a1  mov     [r15], eax
0x18000a2a4  lea     eax, [rsi-1]
0x18000a2a7  mov     [r14+rcx*8+10h], r13
0x18000a2ac  mov     dword ptr [r14+rcx*4-4], 1E3603Bh
0x18000a2b5  test    eax, eax
0x18000a2b7  jz      loc_18000A39E
0x18000a2bd  lock dec dword ptr [rdi+78h]
0x18000a2c1  mov     r15, [rsp+58h+var_28]
0x18000a2c6  mov     r14, [rsp+58h+var_20]
0x18000a2cb  mov     r12, [rsp+58h+var_18]
0x18000a2d0  mov     rsi, [rsp+58h+arg_18]
0x18000a2d5  mov     rbp, [rsp+58h+arg_10]
0x18000a2da  mov     edx, [rbx]
0x18000a2dc  mov     eax, edx
0x18000a2de  lea     ecx, [rdx-10000h]
0x18000a2e4  and     ecx, 0FFFF0000h
0x18000a2ea  lock cmpxchg [rbx], ecx
0x18000a2ee  cmp     edx, eax
0x18000a2f0  jz      short loc_18000A2F6
0x18000a2f2  pause
0x18000a2f4  jmp     short loc_18000A2DA
0x18000a2f6  mov     rbx, [rsp+58h+arg_0]
0x18000a2fb  test    r13d, r13d
0x18000a2fe  jnz     loc_18000A393
0x18000a304  mov     eax, [rdi+78h]
0x18000a307  shr     eax, 4
0x18000a30a  add     eax, [rdi+78h]
0x18000a30d  movaps  [rsp+58h+var_38], xmm6
0x18000a312  xorps   xmm6, xmm6
0x18000a315  cvtsi2sd xmm6, rax
0x18000a31a  mov     ecx, [rdi+7Ch]
0x18000a31d  xorps   xmm0, xmm0
0x18000a320  cvtsi2sd xmm0, rcx
0x18000a325  mulsd   xmm0, qword ptr [rdi+50h]
0x18000a32a  comisd  xmm0, xmm6
0x18000a32e  jbe     short loc_18000A341
0x18000a330  cmp     ecx, [rdi+48h]
0x18000a333  jbe     short loc_18000A341
0x18000a335  mov     rcx, rdi
0x18000a338  call    ?_Contract@CLKRLinearHashTable@@AEAA?AW4LK_RETCODE@@XZ; CLKRLinearHashTable::_Contract(void)
0x18000a33d  test    eax, eax
0x18000a33f  jz      short loc_18000A31A
0x18000a341  movaps  xmm6, [rsp+58h+var_38]
0x18000a346  mov     eax, r13d
0x18000a349  add     rsp, 48h
0x18000a34d  pop     r13
0x18000a34f  pop     rdi
0x18000a350  retn
0x18000a351  mov     r14, rax
0x18000a354  mov     esi, r13d
0x18000a357  jmp     loc_18000A26E
0x18000a35c  mov     r14, [r14+10h]
0x18000a360  jmp     loc_18000A226
0x18000a365  inc     esi
0x18000a367  jmp     loc_18000A231
0x18000a36c  xor     eax, eax
0x18000a36e  xchg    eax, [rdi+1Ch]
0x18000a371  mov     edx, [rdi+18h]
0x18000a374  mov     eax, edx
0x18000a376  lea     ecx, [rdx-10000h]
0x18000a37c  and     ecx, 0FFFF0000h
0x18000a382  lock cmpxchg [rdi+18h], ecx
0x18000a387  cmp     edx, eax
0x18000a389  jz      loc_18000A20E
0x18000a38f  pause
0x18000a391  jmp     short loc_18000A371
0x18000a393  mov     eax, r13d
0x18000a396  add     rsp, 48h
0x18000a39a  pop     r13
0x18000a39c  pop     rdi
0x18000a39d  retn
0x18000a39e  cmp     r14, rbp
0x18000a3a1  jz      loc_18000A2BD
0x18000a3a7  cmp     [rbp+10h], r14
0x18000a3ab  jz      short loc_18000A3B7
0x18000a3ad  mov     rbp, [rbp+10h]
0x18000a3b1  cmp     [rbp+10h], r14
0x18000a3b5  jnz     short loc_18000A3AD
0x18000a3b7  mov     rcx, r14; ListEntry
0x18000a3ba  mov     [rbp+10h], r13
0x18000a3be  call    ??3CNodeClump@@SAXPEAX@Z; CNodeClump::operator delete(void *)
0x18000a3c3  jmp     loc_18000A2BD
0x18000a3c8  call    cs:__imp_GetCurrentThreadId
0x18000a3ce  and     eax, 0FFFFFFFCh
0x18000a3d1  or      eax, 1
0x18000a3d4  xchg    eax, [rdi+1Ch]
0x18000a3d7  jmp     loc_18000A194
0x18000a3dc  pause
0x18000a3de  jmp     loc_18000A1DE
0x18000a3e3  lock inc dword ptr [rdi+1Ch]
0x18000a3e7  jmp     loc_18000A194
```
