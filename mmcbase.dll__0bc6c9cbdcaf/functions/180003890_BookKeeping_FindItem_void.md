# BookKeeping::FindItem(void *)

- ea: `0x180003890`
- end: `0x180003b54`
- name: `?FindItem@BookKeeping@@SAPEAVItemHandle@@PEAX@Z`
- size: `708`
- prototype: `struct ItemHandle *__fastcall(void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000ff80`

## callees

- `0x180003840`
- `0x180003890`
- `0x180004180`
- `0x180019624`
- `0x18001971c`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000390e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000390e`

## pseudocode

```c
struct ItemHandle *__fastcall BookKeeping::FindItem(char *a1)
{
  LKRhash::CLKRLinearHashTable *v1; // r15
  struct ItemHandle *result; // rax
  volatile signed __int32 *v4; // rdi
  int v5; // ebp
  int v6; // ebx
  signed __int32 v7; // edx
  char v8; // si
  unsigned int v9; // r12d
  unsigned int v10; // eax
  CReaderWriterLock2 *v11; // rbx
  signed __int32 v12; // edx
  signed __int32 v13; // edx
  char *i; // rdi
  int j; // esi
  int v16; // eax
  char *v17; // r14
  char *v18; // rax
  signed __int32 v19; // ecx
  __int32 v20; // ecx
  signed __int32 v21; // edx
  signed __int32 v22; // edx
  __int64 v23; // [rsp+58h] [rbp+10h]

  v1 = BookKeeping::s_pItemHandleTable;
  result = 0;
  if ( !BookKeeping::s_pItemHandleTable
    || (unsigned __int64)(a1 - 1) > 0xFFFFFFFFFFFEFFFEuLL && (unsigned __int64)(a1 + 65532) > 0xFFFA
    || *((_DWORD *)BookKeeping::s_pItemHandleTable + 5) )
  {
    return result;
  }
  v4 = (volatile signed __int32 *)((char *)BookKeeping::s_pItemHandleTable + 24);
  v5 = (*((__int64 (**)(void))BookKeeping::s_pItemHandleTable + 5))();
  v23 = 0;
  if ( *((_BYTE *)v1 + 153) )
  {
    v6 = *((_DWORD *)v1 + 7);
    if ( ((v6 ^ GetCurrentThreadId()) & 0xFFFFFFFC) == 0 )
    {
      CReaderWriterLock3::WriteLock((LKRhash::CLKRLinearHashTable *)((char *)v1 + 24));
      v8 = 0;
      goto LABEL_12;
    }
    if ( (unsigned __int16)*v4 == 0xFFFF || (v7 = *v4, v7 != _InterlockedCompareExchange(v4, v7 + 1, v7)) )
      CReaderWriterLock3::_LockSpin((volatile signed __int32 *)v1 + 6, 3);
  }
  v8 = 1;
LABEL_12:
  if ( *((_DWORD *)v1 + 5) )
  {
    if ( *((_BYTE *)v1 + 153) )
    {
      if ( v8 )
      {
        do
          v22 = *v4;
        while ( v22 != _InterlockedCompareExchange(v4, v22 - 1, v22) );
      }
      else
      {
        CReaderWriterLock3::WriteUnlock((LKRhash::CLKRLinearHashTable *)((char *)v1 + 24));
      }
    }
  }
  else
  {
    v9 = (69069 * v5 + 1) & 0xFFFF0000 | ((unsigned int)(1103515245 * v5 + 12345) >> 16);
    v10 = *((_DWORD *)v1 + 22) & v9;
    if ( v10 < *((_DWORD *)v1 + 24) )
      v10 = v9 & *((_DWORD *)v1 + 23);
    v11 = (CReaderWriterLock2 *)(((unsigned __int64)(v10 & *((_DWORD *)v1 + 19)) << 6)
                               + *(_QWORD *)(*((_QWORD *)v1 + 13) + 8 * ((unsigned __int64)v10 >> *((_DWORD *)v1 + 17))));
    if ( *((_BYTE *)v1 + 153) )
    {
      if ( (*(_DWORD *)v11 & 0xFFFF8000) != 0
        || (v12 = *(_DWORD *)v11, v12 != _InterlockedCompareExchange((volatile signed __int32 *)v11, v12 + 1, v12)) )
      {
        CReaderWriterLock2::_LockSpin(v11, 0);
      }
      if ( *((_BYTE *)v1 + 153) )
      {
        if ( v8 )
        {
          do
            v13 = *v4;
          while ( v13 != _InterlockedCompareExchange(v4, v13 - 1, v13) );
        }
        else
        {
          v20 = 0;
          if ( ((*((_BYTE *)v1 + 28) - 1) & 3) != 0 )
            v20 = *((_DWORD *)v1 + 7) - 1;
          _InterlockedExchange((volatile __int32 *)v1 + 7, v20);
          if ( !v20 )
          {
            _m_prefetchw((const void *)v4);
            do
              v21 = *v4;
            while ( v21 != _InterlockedCompareExchange(v4, (v21 - 0x10000) & 0xFFFF0000, v21) );
          }
        }
      }
    }
    for ( i = (char *)v11 + 8; i; i = (char *)*((_QWORD *)i + 2) )
    {
      for ( j = 0; j < 4; ++j )
      {
        v16 = *(_DWORD *)&i[4 * j];
        if ( v16 == 31678523 )
          goto LABEL_30;
        if ( v9 == v16 )
        {
          v17 = &i[8 * j];
          v18 = (char *)(*((__int64 (__fastcall **)(_QWORD))v1 + 4))(*((_QWORD *)v17 + 3));
          if ( a1 == v18 || (*((unsigned __int8 (__fastcall **)(char *, char *))v1 + 6))(a1, v18) )
          {
            v23 = *((_QWORD *)v17 + 3);
            (*((void (__fastcall **)(__int64, __int64))v1 + 7))(v23, 1);
            goto LABEL_30;
          }
        }
      }
    }
LABEL_30:
    if ( *((_BYTE *)v1 + 153) )
    {
      do
        v19 = *(_DWORD *)v11;
      while ( v19 != _InterlockedCompareExchange((volatile signed __int32 *)v11, v19 - 1, v19) );
    }
  }
  return (struct ItemHandle *)v23;
}

```

## disassembly

```asm
0x180003890  push    r13
0x180003892  push    r15
0x180003894  sub     rsp, 38h
0x180003898  mov     r15, cs:?s_pItemHandleTable@BookKeeping@@0PEAVItemHandleTable@@EA; ItemHandleTable * BookKeeping::s_pItemHandleTable
0x18000389f  xor     eax, eax
0x1800038a1  mov     r13, rcx
0x1800038a4  test    r15, r15
0x1800038a7  jnz     short loc_1800038B2
0x1800038a9  add     rsp, 38h
0x1800038ad  pop     r15
0x1800038af  pop     r13
0x1800038b1  retn
0x1800038b2  lea     rdx, [rcx-1]
0x1800038b6  cmp     rdx, 0FFFFFFFFFFFEFFFEh
0x1800038bd  jbe     short loc_1800038CF
0x1800038bf  lea     rdx, [rcx+0FFFCh]
0x1800038c6  cmp     rdx, 0FFFAh
0x1800038cd  ja      short loc_1800038A9
0x1800038cf  cmp     [r15+14h], eax
0x1800038d3  jnz     short loc_1800038A9
0x1800038d5  mov     rax, [r15+28h]
0x1800038d9  mov     [rsp+48h+arg_10], rbp
0x1800038de  mov     [rsp+48h+arg_0], rbx
0x1800038e3  mov     [rsp+48h+arg_18], rsi
0x1800038e8  mov     [rsp+48h+var_18], rdi
0x1800038ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038f2  cmp     byte ptr [r15+99h], 0
0x1800038fa  lea     rdi, [r15+18h]
0x1800038fe  mov     ebp, eax
0x180003900  mov     [rsp+48h+arg_8], 0
0x180003909  jz      short loc_180003944
0x18000390b  mov     ebx, [rdi+4]
0x18000390e  call    cs:__imp_GetCurrentThreadId
0x180003914  xor     eax, ebx
0x180003916  test    eax, 0FFFFFFFCh
0x18000391b  jz      loc_180003B2F
0x180003921  mov     edx, [rdi]
0x180003923  cmp     dx, 0FFFFh
0x180003928  jz      short loc_180003937
0x18000392a  lea     ecx, [rdx+1]
0x18000392d  mov     eax, edx
0x18000392f  lock cmpxchg [rdi], ecx
0x180003933  cmp     edx, eax
0x180003935  jz      short loc_180003944
0x180003937  mov     edx, 3
0x18000393c  mov     rcx, rdi
0x18000393f  call    ?_LockSpin@CReaderWriterLock3@@AEAAXW4SPIN_TYPE@1@@Z; CReaderWriterLock3::_LockSpin(CReaderWriterLock3::SPIN_TYPE)
0x180003944  mov     sil, 1
0x180003947  cmp     dword ptr [r15+14h], 0
0x18000394c  jnz     loc_180003AFB
0x180003952  mov     [rsp+48h+var_20], r12
0x180003957  imul    r12d, ebp, 41C64E6Dh
0x18000395e  imul    eax, ebp, 10DCDh
0x180003964  mov     [rsp+48h+var_28], r14
0x180003969  add     r12d, 3039h
0x180003970  inc     eax
0x180003972  shr     r12d, 10h
0x180003976  and     eax, 0FFFF0000h
0x18000397b  or      r12d, eax
0x18000397e  mov     eax, r12d
0x180003981  and     eax, [r15+58h]
0x180003985  cmp     eax, [r15+60h]
0x180003989  jb      loc_180003B3F
0x18000398f  mov     ecx, [r15+44h]
0x180003993  mov     edx, [r15+4Ch]
0x180003997  and     rdx, rax
0x18000399a  mov     r8d, eax
0x18000399d  shr     r8, cl
0x1800039a0  mov     rcx, [r15+68h]
0x1800039a4  shl     rdx, 6
0x1800039a8  mov     rbx, [rcx+r8*8]
0x1800039ac  add     rbx, rdx
0x1800039af  cmp     byte ptr [r15+99h], 0
0x1800039b7  jz      short loc_1800039FC
0x1800039b9  mov     edx, [rbx]
0x1800039bb  test    edx, 0FFFF8000h
0x1800039c1  jnz     short loc_1800039D0
0x1800039c3  lea     ecx, [rdx+1]
0x1800039c6  mov     eax, edx
0x1800039c8  lock cmpxchg [rbx], ecx
0x1800039cc  cmp     edx, eax
0x1800039ce  jz      short loc_1800039DA
0x1800039d0  xor     edx, edx; bool
0x1800039d2  mov     rcx, rbx; this
0x1800039d5  call    ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x1800039da  cmp     byte ptr [r15+99h], 0
0x1800039e2  jz      short loc_1800039FC
0x1800039e4  test    sil, sil
0x1800039e7  jz      loc_180003A9C
0x1800039ed  mov     edx, [rdi]
0x1800039ef  mov     eax, edx
0x1800039f1  lea     ecx, [rdx-1]
0x1800039f4  lock cmpxchg [rdi], ecx
0x1800039f8  cmp     edx, eax
0x1800039fa  jnz     short loc_1800039ED
0x1800039fc  lea     rdi, [rbx+8]
0x180003a00  test    rdi, rdi
0x180003a03  jz      short loc_180003A5B
0x180003a05  xor     esi, esi
0x180003a07  cmp     esi, 4
0x180003a0a  jge     loc_180003B4B
0x180003a10  movsxd  rcx, esi
0x180003a13  mov     eax, [rdi+rcx*4]
0x180003a16  cmp     eax, 1E3603Bh
0x180003a1b  jz      short loc_180003A5B
0x180003a1d  cmp     r12d, eax
0x180003a20  jnz     loc_180003AF4
0x180003a26  mov     rax, [r15+20h]
0x180003a2a  lea     r14, [rdi+rcx*8]
0x180003a2e  mov     rcx, [rdi+rcx*8+18h]
0x180003a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a38  cmp     r13, rax
0x180003a3b  jnz     loc_180003ADD
0x180003a41  mov     rax, [r14+18h]
0x180003a45  mov     edx, 1
0x180003a4a  mov     [rsp+48h+arg_8], rax
0x180003a4f  mov     rcx, rax
0x180003a52  mov     rax, [r15+38h]
0x180003a56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a5b  cmp     byte ptr [r15+99h], 0
0x180003a63  mov     r14, [rsp+48h+var_28]
0x180003a68  mov     r12, [rsp+48h+var_20]
0x180003a6d  jz      short loc_180003A7E
0x180003a6f  mov     ecx, [rbx]
0x180003a71  mov     eax, ecx
0x180003a73  lea     edx, [rcx-1]
0x180003a76  lock cmpxchg [rbx], edx
0x180003a7a  cmp     ecx, eax
0x180003a7c  jnz     short loc_180003A6F
0x180003a7e  mov     rax, [rsp+48h+arg_8]
0x180003a83  mov     rsi, [rsp+48h+arg_18]
0x180003a88  mov     rbx, [rsp+48h+arg_0]
0x180003a8d  mov     rdi, [rsp+48h+var_18]
0x180003a92  mov     rbp, [rsp+48h+arg_10]
0x180003a97  jmp     loc_1800038A9
0x180003a9c  mov     eax, [rdi+4]
0x180003a9f  mov     ecx, 0
0x180003aa4  dec     eax
0x180003aa6  test    al, 3
0x180003aa8  cmovnz  ecx, eax
0x180003aab  mov     eax, ecx
0x180003aad  xchg    eax, [rdi+4]
0x180003ab0  test    ecx, ecx
0x180003ab2  jnz     loc_1800039FC
0x180003ab8  prefetchw byte ptr [rdi]
0x180003abb  nop     dword ptr [rax+rax+00h]
0x180003ac0  mov     edx, [rdi]
0x180003ac2  mov     eax, edx
0x180003ac4  lea     ecx, [rdx-10000h]
0x180003aca  and     ecx, 0FFFF0000h
0x180003ad0  lock cmpxchg [rdi], ecx
0x180003ad4  cmp     edx, eax
0x180003ad6  jnz     short loc_180003AC0
0x180003ad8  jmp     loc_1800039FC
0x180003add  mov     rdx, rax
0x180003ae0  mov     rcx, r13
0x180003ae3  mov     rax, [r15+30h]
0x180003ae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003aec  test    al, al
0x180003aee  jnz     loc_180003A41
0x180003af4  inc     esi
0x180003af6  jmp     loc_180003A07
0x180003afb  cmp     byte ptr [r15+99h], 0
0x180003b03  jz      loc_180003A7E
0x180003b09  test    sil, sil
0x180003b0c  jz      short loc_180003B22
0x180003b0e  mov     edx, [rdi]
0x180003b10  mov     eax, edx
0x180003b12  lea     ecx, [rdx-1]
0x180003b15  lock cmpxchg [rdi], ecx
0x180003b19  cmp     edx, eax
0x180003b1b  jnz     short loc_180003B0E
0x180003b1d  jmp     loc_180003A7E
0x180003b22  mov     rcx, rdi; this
0x180003b25  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180003b2a  jmp     loc_180003A7E
0x180003b2f  mov     rcx, rdi; this
0x180003b32  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180003b37  xor     sil, sil
0x180003b3a  jmp     loc_180003947
0x180003b3f  mov     eax, [r15+5Ch]
0x180003b43  and     eax, r12d
0x180003b46  jmp     loc_18000398F
0x180003b4b  mov     rdi, [rdi+10h]
0x180003b4f  jmp     loc_180003A00
```
