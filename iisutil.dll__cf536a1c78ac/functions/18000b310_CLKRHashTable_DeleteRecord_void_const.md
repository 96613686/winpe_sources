# CLKRHashTable::DeleteRecord(void const *)

- ea: `0x18000b310`
- end: `0x18000b67d`
- name: `?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z`
- size: `877`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180007e60`
- `0x180008470`
- `0x180008de0`
- `0x180009c10`
- `0x18000b310`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b3e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b5dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b3e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b5dc`

## pseudocode

```c
__int64 __fastcall CLKRHashTable::DeleteRecord(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v5; // rax
  int v6; // eax
  int v7; // edx
  unsigned int v8; // ebp
  unsigned int v9; // ecx
  __int64 v10; // rdx
  __int64 v11; // rdi
  signed __int32 v12; // edx
  unsigned int v13; // eax
  unsigned __int64 v14; // rbx
  signed __int32 v15; // edx
  signed __int32 v16; // edx
  struct _SLIST_ENTRY *v17; // r15
  struct _SLIST_ENTRY *Next; // rsi
  int i; // ebp
  _DWORD *v20; // r12
  __int64 v21; // rcx
  char *v22; // r13
  unsigned int v23; // r12d
  signed __int32 v24; // edx
  double v25; // xmm6_8
  int v26; // ecx
  signed __int32 v27; // edx

  result = *(unsigned int *)(a1 + 48);
  if ( !(_DWORD)result )
  {
    if ( a2 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64))(a1 + 32))(a2);
      v6 = (*(__int64 (__fastcall **)(__int64))(a1 + 40))(v5);
      v7 = *(_DWORD *)(a1 + 52);
      v8 = (69069 * v6 + 1) & 0xFFFF0000 | ((unsigned int)(1103515245 * v6 + 12345) >> 16);
      v9 = (69069 * v8 + 1) & 0xFFFF0000 | ((1048583 * v8 + 12345) >> 16);
      if ( v7 >= 0 )
        v10 = v9 & v7;
      else
        v10 = v9 % *(_DWORD *)(a1 + 20);
      v11 = *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8 * v10);
      if ( *(_DWORD *)(v11 + 28)
        || (v12 = *(_DWORD *)(v11 + 24), (_WORD)v12)
        || v12 != _InterlockedCompareExchange((volatile signed __int32 *)(v11 + 24), (v12 + 0x10000) | 0xFFFF, v12) )
      {
        if ( (*(_DWORD *)(v11 + 28) & 0xFFFFFFFC) == (GetCurrentThreadId() & 0xFFFFFFFC) )
          _InterlockedIncrement((volatile signed __int32 *)(v11 + 28));
        else
          CReaderWriterLock3::_WriteLockSpin((CReaderWriterLock3 *)(v11 + 24));
      }
      else
      {
        _InterlockedExchange((volatile __int32 *)(v11 + 28), GetCurrentThreadId() & 0xFFFFFFFC | 1);
      }
      v13 = *(_DWORD *)(v11 + 88) & v8;
      if ( v13 < *(_DWORD *)(v11 + 96) )
        v13 = v8 & *(_DWORD *)(v11 + 92);
      v14 = ((unsigned __int64)(v13 & *(_DWORD *)(v11 + 76)) << 6)
          + *(_QWORD *)(*(_QWORD *)(v11 + 104) + 8 * ((unsigned __int64)v13 >> *(_DWORD *)(v11 + 68)));
      if ( (unsigned __int16)*(_DWORD *)v14
        || (v15 = *(_DWORD *)v14,
            v15 != _InterlockedCompareExchange((volatile signed __int32 *)v14, (v15 + 0x10000) | 0xFFFF, v15)) )
      {
        while ( 1 )
        {
          v16 = *(_DWORD *)v14;
          if ( v16 == _InterlockedCompareExchange((volatile signed __int32 *)v14, v16 + 0x10000, v16) )
            break;
          _mm_pause();
        }
        CReaderWriterLock2::_LockSpin((CReaderWriterLock2 *)v14, 1);
      }
      if ( ((*(_BYTE *)(v11 + 28) - 1) & 3) != 0 )
      {
        _InterlockedExchange((volatile __int32 *)(v11 + 28), *(_DWORD *)(v11 + 28) - 1);
      }
      else
      {
        _InterlockedExchange((volatile __int32 *)(v11 + 28), 0);
        while ( 1 )
        {
          v27 = *(_DWORD *)(v11 + 24);
          if ( v27 == _InterlockedCompareExchange(
                        (volatile signed __int32 *)(v11 + 24),
                        (v27 - 0x10000) & 0xFFFF0000,
                        v27) )
            break;
          _mm_pause();
        }
      }
      (*(void (__fastcall **)(__int64))(v11 + 32))(a2);
      v17 = (struct _SLIST_ENTRY *)(v14 + 8);
      Next = (struct _SLIST_ENTRY *)(v14 + 8);
LABEL_19:
      if ( Next )
      {
        for ( i = 0; ; ++i )
        {
          if ( i >= 4 )
          {
            Next = Next[1].Next;
            goto LABEL_19;
          }
          v20 = (_DWORD *)Next + i;
          if ( *v20 == 31678523 )
            goto LABEL_54;
          v21 = *((_QWORD *)&Next[1].Next + i + 1);
          v22 = (char *)Next + 8 * i;
          if ( v21 == a2 )
            break;
        }
        (*(void (__fastcall **)(__int64, __int64))(v11 + 56))(v21, 0xFFFFFFFFLL);
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
        *((_QWORD *)v22 + 3) = *((_QWORD *)&Next[1].Next + i);
        *v20 = *((_DWORD *)Next + i - 1);
        *((_QWORD *)&Next[1].Next + i) = 0;
        *((_DWORD *)Next + i - 1) = 31678523;
        if ( i == 1 && Next != v17 )
        {
          if ( *(struct _SLIST_ENTRY **)(v14 + 24) != Next )
          {
            do
              v17 = v17[1].Next;
            while ( v17[1].Next != Next );
          }
          v17[1].Next = 0;
          CNodeClump::operator delete(Next);
        }
        _InterlockedDecrement((volatile signed __int32 *)(v11 + 120));
        v23 = 0;
      }
      else
      {
LABEL_54:
        v23 = 2;
      }
      while ( 1 )
      {
        v24 = *(_DWORD *)v14;
        if ( v24 == _InterlockedCompareExchange((volatile signed __int32 *)v14, (v24 - 0x10000) & 0xFFFF0000, v24) )
          break;
        _mm_pause();
      }
      if ( !v23 )
      {
        v25 = (double)(*(_DWORD *)(v11 + 120) + (*(_DWORD *)(v11 + 120) >> 4));
        do
          v26 = *(_DWORD *)(v11 + 124);
        while ( (double)v26 * *(double *)(v11 + 80) > v25
             && (unsigned int)v26 > *(_DWORD *)(v11 + 72)
             && !(unsigned int)CLKRLinearHashTable::_Contract(v11) );
      }
      return v23;
    }
    else
    {
      return 4294967200LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000b310  push    rbx
0x18000b312  push    r14
0x18000b314  sub     rsp, 48h
0x18000b318  mov     eax, [rcx+30h]
0x18000b31b  mov     r14, rdx
0x18000b31e  mov     rbx, rcx
0x18000b321  test    eax, eax
0x18000b323  jnz     loc_18000B5BE
0x18000b329  test    rdx, rdx
0x18000b32c  jz      loc_18000B5C7
0x18000b332  mov     rax, [rbx+20h]
0x18000b336  mov     rcx, rdx
0x18000b339  mov     [rsp+58h+arg_0], rbp
0x18000b33e  mov     [rsp+58h+arg_8], rsi
0x18000b343  mov     [rsp+58h+arg_10], rdi
0x18000b348  mov     [rsp+58h+var_18], r12
0x18000b34d  mov     [rsp+58h+var_20], r13
0x18000b352  mov     [rsp+58h+var_28], r15
0x18000b357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b35c  mov     rcx, rax
0x18000b35f  mov     rax, [rbx+28h]
0x18000b363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b368  mov     edx, [rbx+34h]
0x18000b36b  imul    ebp, eax, 41C64E6Dh
0x18000b371  imul    ecx, eax, 10DCDh
0x18000b377  add     ebp, 3039h
0x18000b37d  inc     ecx
0x18000b37f  shr     ebp, 10h
0x18000b382  and     ecx, 0FFFF0000h
0x18000b388  or      ebp, ecx
0x18000b38a  imul    ecx, ebp, 100007h
0x18000b390  imul    eax, ebp, 10DCDh
0x18000b396  add     ecx, 3039h
0x18000b39c  inc     eax
0x18000b39e  shr     ecx, 10h
0x18000b3a1  and     eax, 0FFFF0000h
0x18000b3a6  or      ecx, eax
0x18000b3a8  test    edx, edx
0x18000b3aa  jns     loc_18000B5D5
0x18000b3b0  xor     edx, edx
0x18000b3b2  mov     eax, ecx
0x18000b3b4  div     dword ptr [rbx+14h]
0x18000b3b7  mov     rax, [rbx+18h]
0x18000b3bb  mov     rdi, [rax+rdx*8]
0x18000b3bf  mov     eax, [rdi+1Ch]
0x18000b3c2  test    eax, eax
0x18000b3c4  jnz     short loc_18000B3E9
0x18000b3c6  mov     edx, [rdi+18h]
0x18000b3c9  test    dx, dx
0x18000b3cc  jnz     short loc_18000B3E9
0x18000b3ce  lea     ecx, [rdx+10000h]
0x18000b3d4  mov     eax, edx
0x18000b3d6  or      ecx, 0FFFFh
0x18000b3dc  lock cmpxchg [rdi+18h], ecx
0x18000b3e1  cmp     edx, eax
0x18000b3e3  jz      loc_18000B5DC
0x18000b3e9  call    cs:__imp_GetCurrentThreadId
0x18000b3f0  nop     dword ptr [rax+rax+00h]
0x18000b3f5  mov     ecx, [rdi+1Ch]
0x18000b3f8  and     eax, 0FFFFFFFCh
0x18000b3fb  and     ecx, 0FFFFFFFCh
0x18000b3fe  cmp     ecx, eax
0x18000b400  jz      loc_18000B669
0x18000b406  lea     rcx, [rdi+18h]; this
0x18000b40a  call    ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
0x18000b40f  mov     eax, ebp
0x18000b411  and     eax, [rdi+58h]
0x18000b414  cmp     eax, [rdi+60h]
0x18000b417  jnb     short loc_18000B41E
0x18000b419  mov     eax, [rdi+5Ch]
0x18000b41c  and     eax, ebp
0x18000b41e  mov     ecx, [rdi+44h]
0x18000b421  mov     edx, [rdi+4Ch]
0x18000b424  and     rdx, rax
0x18000b427  mov     r8d, eax
0x18000b42a  shr     r8, cl
0x18000b42d  mov     rcx, [rdi+68h]
0x18000b431  shl     rdx, 6
0x18000b435  mov     rbx, [rcx+r8*8]
0x18000b439  add     rbx, rdx
0x18000b43c  mov     edx, [rbx]
0x18000b43e  test    dx, dx
0x18000b441  jnz     short loc_18000B459
0x18000b443  lea     ecx, [rdx+10000h]
0x18000b449  mov     eax, edx
0x18000b44b  or      ecx, 0FFFFh
0x18000b451  lock cmpxchg [rbx], ecx
0x18000b455  cmp     edx, eax
0x18000b457  jz      short loc_18000B479
0x18000b459  mov     edx, [rbx]
0x18000b45b  mov     eax, edx
0x18000b45d  lea     ecx, [rdx+10000h]
0x18000b463  lock cmpxchg [rbx], ecx
0x18000b467  cmp     edx, eax
0x18000b469  jnz     loc_18000B662
0x18000b46f  mov     dl, 1; bool
0x18000b471  mov     rcx, rbx; this
0x18000b474  call    ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x18000b479  mov     eax, [rdi+1Ch]
0x18000b47c  dec     eax
0x18000b47e  test    al, 3
0x18000b480  jz      loc_18000B611
0x18000b486  xchg    eax, [rdi+1Ch]
0x18000b489  mov     rax, [rdi+20h]
0x18000b48d  mov     rcx, r14
0x18000b490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b495  lea     r15, [rbx+8]
0x18000b499  mov     rsi, r15
0x18000b49c  test    rsi, rsi
0x18000b49f  jz      loc_18000B672
0x18000b4a5  xor     ebp, ebp
0x18000b4a7  cmp     ebp, 4
0x18000b4aa  jge     loc_18000B601
0x18000b4b0  movsxd  rax, ebp
0x18000b4b3  cmp     dword ptr [rsi+rax*4], 1E3603Bh
0x18000b4ba  lea     r12, [rsi+rax*4]
0x18000b4be  jz      loc_18000B672
0x18000b4c4  mov     rcx, [rsi+rax*8+18h]
0x18000b4c9  lea     r13, [rsi+rax*8]
0x18000b4cd  cmp     rcx, r14
0x18000b4d0  jnz     loc_18000B60A
0x18000b4d6  mov     rax, [rdi+38h]
0x18000b4da  mov     edx, 0FFFFFFFFh
0x18000b4df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4e4  xor     r14d, r14d
0x18000b4e7  mov     rax, [rsi+10h]
0x18000b4eb  test    rax, rax
0x18000b4ee  jnz     loc_18000B5F6
0x18000b4f4  movsxd  rax, ebp
0x18000b4f7  cmp     dword ptr [rsi+rax*4], 1E3603Bh
0x18000b4fe  jz      short loc_18000B507
0x18000b500  inc     ebp
0x18000b502  cmp     ebp, 4
0x18000b505  jnz     short loc_18000B4F4
0x18000b507  movsxd  rcx, ebp
0x18000b50a  mov     rax, [rsi+rcx*8+10h]
0x18000b50f  mov     [r13+18h], rax
0x18000b513  mov     eax, [rsi+rcx*4-4]
0x18000b517  mov     [r12], eax
0x18000b51b  lea     eax, [rbp-1]
0x18000b51e  mov     [rsi+rcx*8+10h], r14
0x18000b523  mov     dword ptr [rsi+rcx*4-4], 1E3603Bh
0x18000b52b  test    eax, eax
0x18000b52d  jz      loc_18000B638
0x18000b533  lock dec dword ptr [rdi+78h]
0x18000b537  mov     r12d, r14d
0x18000b53a  mov     r15, [rsp+58h+var_28]
0x18000b53f  mov     r13, [rsp+58h+var_20]
0x18000b544  mov     rsi, [rsp+58h+arg_8]
0x18000b549  mov     rbp, [rsp+58h+arg_0]
0x18000b54e  mov     edx, [rbx]
0x18000b550  mov     eax, edx
0x18000b552  lea     ecx, [rdx-10000h]
0x18000b558  and     ecx, 0FFFF0000h
0x18000b55e  lock cmpxchg [rbx], ecx
0x18000b562  cmp     edx, eax
0x18000b564  jz      short loc_18000B56A
0x18000b566  pause
0x18000b568  jmp     short loc_18000B54E
0x18000b56a  test    r12d, r12d
0x18000b56d  jnz     short loc_18000B5B1
0x18000b56f  mov     eax, [rdi+78h]
0x18000b572  shr     eax, 4
0x18000b575  add     eax, [rdi+78h]
0x18000b578  movaps  [rsp+58h+var_38], xmm6
0x18000b57d  xorps   xmm6, xmm6
0x18000b580  cvtsi2sd xmm6, rax
0x18000b585  mov     ecx, [rdi+7Ch]
0x18000b588  xorps   xmm0, xmm0
0x18000b58b  cvtsi2sd xmm0, rcx
0x18000b590  mulsd   xmm0, qword ptr [rdi+50h]
0x18000b595  comisd  xmm0, xmm6
0x18000b599  jbe     short loc_18000B5AC
0x18000b59b  cmp     ecx, [rdi+48h]
0x18000b59e  jbe     short loc_18000B5AC
0x18000b5a0  mov     rcx, rdi
0x18000b5a3  call    ?_Contract@CLKRLinearHashTable@@AEAA?AW4LK_RETCODE@@XZ; CLKRLinearHashTable::_Contract(void)
0x18000b5a8  test    eax, eax
0x18000b5aa  jz      short loc_18000B585
0x18000b5ac  movaps  xmm6, [rsp+58h+var_38]
0x18000b5b1  mov     rdi, [rsp+58h+arg_10]
0x18000b5b6  mov     eax, r12d
0x18000b5b9  mov     r12, [rsp+58h+var_18]
0x18000b5be  add     rsp, 48h
0x18000b5c2  pop     r14
0x18000b5c4  pop     rbx
0x18000b5c5  retn
0x18000b5c7  mov     eax, 0FFFFFFA0h
0x18000b5cc  add     rsp, 48h
0x18000b5d0  pop     r14
0x18000b5d2  pop     rbx
0x18000b5d3  retn
0x18000b5d5  and     edx, ecx
0x18000b5d7  jmp     loc_18000B3B7
0x18000b5dc  call    cs:__imp_GetCurrentThreadId
0x18000b5e3  nop     dword ptr [rax+rax+00h]
0x18000b5e8  and     eax, 0FFFFFFFCh
0x18000b5eb  or      eax, 1
0x18000b5ee  xchg    eax, [rdi+1Ch]
0x18000b5f1  jmp     loc_18000B40F
0x18000b5f6  mov     rsi, rax
0x18000b5f9  mov     ebp, r14d
0x18000b5fc  jmp     loc_18000B4E7
0x18000b601  mov     rsi, [rsi+10h]
0x18000b605  jmp     loc_18000B49C
0x18000b60a  inc     ebp
0x18000b60c  jmp     loc_18000B4A7
0x18000b611  xor     eax, eax
0x18000b613  xchg    eax, [rdi+1Ch]
0x18000b616  mov     edx, [rdi+18h]
0x18000b619  mov     eax, edx
0x18000b61b  lea     ecx, [rdx-10000h]
0x18000b621  and     ecx, 0FFFF0000h
0x18000b627  lock cmpxchg [rdi+18h], ecx
0x18000b62c  cmp     edx, eax
0x18000b62e  jz      loc_18000B489
0x18000b634  pause
0x18000b636  jmp     short loc_18000B616
0x18000b638  cmp     rsi, r15
0x18000b63b  jz      loc_18000B533
0x18000b641  cmp     [r15+10h], rsi
0x18000b645  jz      short loc_18000B651
0x18000b647  mov     r15, [r15+10h]
0x18000b64b  cmp     [r15+10h], rsi
0x18000b64f  jnz     short loc_18000B647
0x18000b651  mov     rcx, rsi; ListEntry
0x18000b654  mov     [r15+10h], r14
0x18000b658  call    ??3CNodeClump@@SAXPEAX@Z; CNodeClump::operator delete(void *)
0x18000b65d  jmp     loc_18000B533
0x18000b662  pause
0x18000b664  jmp     loc_18000B459
0x18000b669  lock inc dword ptr [rdi+1Ch]
0x18000b66d  jmp     loc_18000B40F
0x18000b672  mov     r12d, 2
0x18000b678  jmp     loc_18000B53A
```
