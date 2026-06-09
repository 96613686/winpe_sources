# CLKRHashTable::DeleteRecord(void const *)

- ea: `0x18000a9d0`
- end: `0x18000ad2f`
- name: `?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z`
- size: `863`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180007180`
- `0x180007750`
- `0x1800080a0`
- `0x180008eb0`
- `0x18000a9d0`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000aaa9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ac94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000aaa9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ac94`

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
0x18000a9d0  push    rbx
0x18000a9d2  push    r14
0x18000a9d4  sub     rsp, 48h
0x18000a9d8  mov     eax, [rcx+30h]
0x18000a9db  mov     r14, rdx
0x18000a9de  mov     rbx, rcx
0x18000a9e1  test    eax, eax
0x18000a9e3  jnz     loc_18000AC78
0x18000a9e9  test    rdx, rdx
0x18000a9ec  jz      loc_18000AC80
0x18000a9f2  mov     rax, [rbx+20h]
0x18000a9f6  mov     rcx, rdx
0x18000a9f9  mov     [rsp+58h+arg_0], rbp
0x18000a9fe  mov     [rsp+58h+arg_8], rsi
0x18000aa03  mov     [rsp+58h+arg_10], rdi
0x18000aa08  mov     [rsp+58h+var_18], r12
0x18000aa0d  mov     [rsp+58h+var_20], r13
0x18000aa12  mov     [rsp+58h+var_28], r15
0x18000aa17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa1c  mov     rcx, rax
0x18000aa1f  mov     rax, [rbx+28h]
0x18000aa23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa28  mov     edx, [rbx+34h]
0x18000aa2b  imul    ebp, eax, 41C64E6Dh
0x18000aa31  imul    ecx, eax, 10DCDh
0x18000aa37  add     ebp, 3039h
0x18000aa3d  inc     ecx
0x18000aa3f  shr     ebp, 10h
0x18000aa42  and     ecx, 0FFFF0000h
0x18000aa48  or      ebp, ecx
0x18000aa4a  imul    ecx, ebp, 100007h
0x18000aa50  imul    eax, ebp, 10DCDh
0x18000aa56  add     ecx, 3039h
0x18000aa5c  inc     eax
0x18000aa5e  shr     ecx, 10h
0x18000aa61  and     eax, 0FFFF0000h
0x18000aa66  or      ecx, eax
0x18000aa68  test    edx, edx
0x18000aa6a  jns     loc_18000AC8D
0x18000aa70  xor     edx, edx
0x18000aa72  mov     eax, ecx
0x18000aa74  div     dword ptr [rbx+14h]
0x18000aa77  mov     rax, [rbx+18h]
0x18000aa7b  mov     rdi, [rax+rdx*8]
0x18000aa7f  mov     eax, [rdi+1Ch]
0x18000aa82  test    eax, eax
0x18000aa84  jnz     short loc_18000AAA9
0x18000aa86  mov     edx, [rdi+18h]
0x18000aa89  test    dx, dx
0x18000aa8c  jnz     short loc_18000AAA9
0x18000aa8e  lea     ecx, [rdx+10000h]
0x18000aa94  mov     eax, edx
0x18000aa96  or      ecx, 0FFFFh
0x18000aa9c  lock cmpxchg [rdi+18h], ecx
0x18000aaa1  cmp     edx, eax
0x18000aaa3  jz      loc_18000AC94
0x18000aaa9  call    cs:__imp_GetCurrentThreadId
0x18000aaaf  mov     ecx, [rdi+1Ch]
0x18000aab2  and     eax, 0FFFFFFFCh
0x18000aab5  and     ecx, 0FFFFFFFCh
0x18000aab8  cmp     ecx, eax
0x18000aaba  jz      loc_18000AD1B
0x18000aac0  lea     rcx, [rdi+18h]; this
0x18000aac4  call    ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
0x18000aac9  mov     eax, ebp
0x18000aacb  and     eax, [rdi+58h]
0x18000aace  cmp     eax, [rdi+60h]
0x18000aad1  jnb     short loc_18000AAD8
0x18000aad3  mov     eax, [rdi+5Ch]
0x18000aad6  and     eax, ebp
0x18000aad8  mov     ecx, [rdi+44h]
0x18000aadb  mov     edx, [rdi+4Ch]
0x18000aade  and     rdx, rax
0x18000aae1  mov     r8d, eax
0x18000aae4  shr     r8, cl
0x18000aae7  mov     rcx, [rdi+68h]
0x18000aaeb  shl     rdx, 6
0x18000aaef  mov     rbx, [rcx+r8*8]
0x18000aaf3  add     rbx, rdx
0x18000aaf6  mov     edx, [rbx]
0x18000aaf8  test    dx, dx
0x18000aafb  jnz     short loc_18000AB13
0x18000aafd  lea     ecx, [rdx+10000h]
0x18000ab03  mov     eax, edx
0x18000ab05  or      ecx, 0FFFFh
0x18000ab0b  lock cmpxchg [rbx], ecx
0x18000ab0f  cmp     edx, eax
0x18000ab11  jz      short loc_18000AB33
0x18000ab13  mov     edx, [rbx]
0x18000ab15  mov     eax, edx
0x18000ab17  lea     ecx, [rdx+10000h]
0x18000ab1d  lock cmpxchg [rbx], ecx
0x18000ab21  cmp     edx, eax
0x18000ab23  jnz     loc_18000AD14
0x18000ab29  mov     dl, 1; bool
0x18000ab2b  mov     rcx, rbx; this
0x18000ab2e  call    ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x18000ab33  mov     eax, [rdi+1Ch]
0x18000ab36  dec     eax
0x18000ab38  test    al, 3
0x18000ab3a  jz      loc_18000ACC3
0x18000ab40  xchg    eax, [rdi+1Ch]
0x18000ab43  mov     rax, [rdi+20h]
0x18000ab47  mov     rcx, r14
0x18000ab4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab4f  lea     r15, [rbx+8]
0x18000ab53  mov     rsi, r15
0x18000ab56  test    rsi, rsi
0x18000ab59  jz      loc_18000AD24
0x18000ab5f  xor     ebp, ebp
0x18000ab61  cmp     ebp, 4
0x18000ab64  jge     loc_18000ACB3
0x18000ab6a  movsxd  rax, ebp
0x18000ab6d  cmp     dword ptr [rsi+rax*4], 1E3603Bh
0x18000ab74  lea     r12, [rsi+rax*4]
0x18000ab78  jz      loc_18000AD24
0x18000ab7e  mov     rcx, [rsi+rax*8+18h]
0x18000ab83  lea     r13, [rsi+rax*8]
0x18000ab87  cmp     rcx, r14
0x18000ab8a  jnz     loc_18000ACBC
0x18000ab90  mov     rax, [rdi+38h]
0x18000ab94  mov     edx, 0FFFFFFFFh
0x18000ab99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab9e  xor     r14d, r14d
0x18000aba1  mov     rax, [rsi+10h]
0x18000aba5  test    rax, rax
0x18000aba8  jnz     loc_18000ACA8
0x18000abae  movsxd  rax, ebp
0x18000abb1  cmp     dword ptr [rsi+rax*4], 1E3603Bh
0x18000abb8  jz      short loc_18000ABC1
0x18000abba  inc     ebp
0x18000abbc  cmp     ebp, 4
0x18000abbf  jnz     short loc_18000ABAE
0x18000abc1  movsxd  rcx, ebp
0x18000abc4  mov     rax, [rsi+rcx*8+10h]
0x18000abc9  mov     [r13+18h], rax
0x18000abcd  mov     eax, [rsi+rcx*4-4]
0x18000abd1  mov     [r12], eax
0x18000abd5  lea     eax, [rbp-1]
0x18000abd8  mov     [rsi+rcx*8+10h], r14
0x18000abdd  mov     dword ptr [rsi+rcx*4-4], 1E3603Bh
0x18000abe5  test    eax, eax
0x18000abe7  jz      loc_18000ACEA
0x18000abed  lock dec dword ptr [rdi+78h]
0x18000abf1  mov     r12d, r14d
0x18000abf4  mov     r15, [rsp+58h+var_28]
0x18000abf9  mov     r13, [rsp+58h+var_20]
0x18000abfe  mov     rsi, [rsp+58h+arg_8]
0x18000ac03  mov     rbp, [rsp+58h+arg_0]
0x18000ac08  mov     edx, [rbx]
0x18000ac0a  mov     eax, edx
0x18000ac0c  lea     ecx, [rdx-10000h]
0x18000ac12  and     ecx, 0FFFF0000h
0x18000ac18  lock cmpxchg [rbx], ecx
0x18000ac1c  cmp     edx, eax
0x18000ac1e  jz      short loc_18000AC24
0x18000ac20  pause
0x18000ac22  jmp     short loc_18000AC08
0x18000ac24  test    r12d, r12d
0x18000ac27  jnz     short loc_18000AC6B
0x18000ac29  mov     eax, [rdi+78h]
0x18000ac2c  shr     eax, 4
0x18000ac2f  add     eax, [rdi+78h]
0x18000ac32  movaps  [rsp+58h+var_38], xmm6
0x18000ac37  xorps   xmm6, xmm6
0x18000ac3a  cvtsi2sd xmm6, rax
0x18000ac3f  mov     ecx, [rdi+7Ch]
0x18000ac42  xorps   xmm0, xmm0
0x18000ac45  cvtsi2sd xmm0, rcx
0x18000ac4a  mulsd   xmm0, qword ptr [rdi+50h]
0x18000ac4f  comisd  xmm0, xmm6
0x18000ac53  jbe     short loc_18000AC66
0x18000ac55  cmp     ecx, [rdi+48h]
0x18000ac58  jbe     short loc_18000AC66
0x18000ac5a  mov     rcx, rdi
0x18000ac5d  call    ?_Contract@CLKRLinearHashTable@@AEAA?AW4LK_RETCODE@@XZ; CLKRLinearHashTable::_Contract(void)
0x18000ac62  test    eax, eax
0x18000ac64  jz      short loc_18000AC3F
0x18000ac66  movaps  xmm6, [rsp+58h+var_38]
0x18000ac6b  mov     rdi, [rsp+58h+arg_10]
0x18000ac70  mov     eax, r12d
0x18000ac73  mov     r12, [rsp+58h+var_18]
0x18000ac78  add     rsp, 48h
0x18000ac7c  pop     r14
0x18000ac7e  pop     rbx
0x18000ac7f  retn
0x18000ac80  mov     eax, 0FFFFFFA0h
0x18000ac85  add     rsp, 48h
0x18000ac89  pop     r14
0x18000ac8b  pop     rbx
0x18000ac8c  retn
0x18000ac8d  and     edx, ecx
0x18000ac8f  jmp     loc_18000AA77
0x18000ac94  call    cs:__imp_GetCurrentThreadId
0x18000ac9a  and     eax, 0FFFFFFFCh
0x18000ac9d  or      eax, 1
0x18000aca0  xchg    eax, [rdi+1Ch]
0x18000aca3  jmp     loc_18000AAC9
0x18000aca8  mov     rsi, rax
0x18000acab  mov     ebp, r14d
0x18000acae  jmp     loc_18000ABA1
0x18000acb3  mov     rsi, [rsi+10h]
0x18000acb7  jmp     loc_18000AB56
0x18000acbc  inc     ebp
0x18000acbe  jmp     loc_18000AB61
0x18000acc3  xor     eax, eax
0x18000acc5  xchg    eax, [rdi+1Ch]
0x18000acc8  mov     edx, [rdi+18h]
0x18000accb  mov     eax, edx
0x18000accd  lea     ecx, [rdx-10000h]
0x18000acd3  and     ecx, 0FFFF0000h
0x18000acd9  lock cmpxchg [rdi+18h], ecx
0x18000acde  cmp     edx, eax
0x18000ace0  jz      loc_18000AB43
0x18000ace6  pause
0x18000ace8  jmp     short loc_18000ACC8
0x18000acea  cmp     rsi, r15
0x18000aced  jz      loc_18000ABED
0x18000acf3  cmp     [r15+10h], rsi
0x18000acf7  jz      short loc_18000AD03
0x18000acf9  mov     r15, [r15+10h]
0x18000acfd  cmp     [r15+10h], rsi
0x18000ad01  jnz     short loc_18000ACF9
0x18000ad03  mov     rcx, rsi; ListEntry
0x18000ad06  mov     [r15+10h], r14
0x18000ad0a  call    ??3CNodeClump@@SAXPEAX@Z; CNodeClump::operator delete(void *)
0x18000ad0f  jmp     loc_18000ABED
0x18000ad14  pause
0x18000ad16  jmp     loc_18000AB13
0x18000ad1b  lock inc dword ptr [rdi+1Ch]
0x18000ad1f  jmp     loc_18000AAC9
0x18000ad24  mov     r12d, 2
0x18000ad2a  jmp     loc_18000ABF4
```
