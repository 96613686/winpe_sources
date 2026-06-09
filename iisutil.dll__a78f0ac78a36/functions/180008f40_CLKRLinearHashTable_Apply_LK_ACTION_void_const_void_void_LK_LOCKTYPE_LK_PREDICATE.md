# CLKRLinearHashTable::_Apply(LK_ACTION (*)(void const *,void *),void *,LK_LOCKTYPE,LK_PREDICATE &)

- ea: `0x180008f40`
- end: `0x1800092c8`
- name: `?_Apply@CLKRLinearHashTable@@AEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@AEAW4LK_PREDICATE@@@Z`
- size: `904`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180019ea0`

## callees

- `0x1800080a0`
- `0x180008820`
- `0x180008eb0`
- `0x180008f40`
- `0x18000ada0`
- `0x18000e850`
- `0x180015ee0`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008fa8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008fa8`

## pseudocode

```c
__int64 __fastcall CLKRLinearHashTable::_Apply(
        __int64 a1,
        __int64 (__fastcall *a2)(__int64, __int64),
        __int64 a3,
        int a4,
        _DWORD *a5)
{
  int v9; // ebx
  unsigned int i; // r15d
  unsigned __int64 v11; // rdx
  __int64 v12; // rcx
  unsigned __int64 v13; // rbx
  struct _SLIST_ENTRY *Next; // rsi
  int j; // ebp
  char *v16; // r12
  int v17; // eax
  __int64 v18; // rcx
  int v19; // eax
  signed __int32 v20; // edx
  signed __int32 v21; // edx
  signed __int32 v22; // edx
  signed __int32 v23; // edx
  struct _SLIST_ENTRY *v24; // r8
  int v25; // edx
  __int64 v26; // rax
  int v27; // edx
  struct _SLIST_ENTRY *v28; // rcx
  unsigned __int64 v29; // rax
  unsigned __int64 v30; // rax
  unsigned __int64 v31; // [rsp+20h] [rbp-48h]
  unsigned int v32; // [rsp+70h] [rbp+8h]

  if ( *(_DWORD *)(a1 + 20) )
    return 4294967197LL;
  if ( a4 == 2 )
  {
    v9 = *(_DWORD *)(a1 + 28);
    if ( ((v9 ^ GetCurrentThreadId()) & 0xFFFFFFFC) != 0 )
      return 0;
  }
  else if ( (*(_DWORD *)(a1 + 24) & 0x7FFF) == 0 )
  {
    return 0;
  }
  if ( !a2 )
    return 0;
  v32 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= *(_DWORD *)(a1 + 124) )
      return v32;
    v11 = (unsigned __int64)i >> *(_DWORD *)(a1 + 68);
    v12 = *(_QWORD *)(a1 + 104);
    v13 = *(_QWORD *)(v12 + 8 * v11) + ((unsigned __int64)(i & *(_DWORD *)(a1 + 76)) << 6);
    if ( a4 == 2 )
    {
      if ( (unsigned __int16)*(_DWORD *)v13
        || (v21 = *(_DWORD *)v13,
            v21 != _InterlockedCompareExchange((volatile signed __int32 *)v13, (v21 + 0x10000) | 0xFFFF, v21)) )
      {
        while ( 1 )
        {
          v22 = *(_DWORD *)v13;
          if ( v22 == _InterlockedCompareExchange((volatile signed __int32 *)v13, v22 + 0x10000, v22) )
            break;
          _mm_pause();
        }
        CReaderWriterLock2::_LockSpin((CReaderWriterLock2 *)v13, 1);
      }
    }
    else
    {
      CReaderWriterLock2::ReadLock((CReaderWriterLock2 *)(*(_QWORD *)(v12 + 8 * v11)
                                                        + ((unsigned __int64)(i & *(_DWORD *)(a1 + 76)) << 6)));
    }
    Next = (struct _SLIST_ENTRY *)(v13 + 8);
    v31 = 0;
LABEL_13:
    if ( Next )
      break;
LABEL_26:
    v20 = *(_DWORD *)v13;
    if ( a4 == 2 )
    {
      while ( v20 != _InterlockedCompareExchange((volatile signed __int32 *)v13, (v20 - 0x10000) & 0xFFFF0000, v20) )
      {
        _mm_pause();
        v20 = *(_DWORD *)v13;
      }
    }
    else
    {
      while ( v20 != _InterlockedCompareExchange((volatile signed __int32 *)v13, v20 - 1, v20) )
      {
        _mm_pause();
        v20 = *(_DWORD *)v13;
      }
    }
  }
  for ( j = 0; ; ++j )
  {
    if ( j >= 4 )
    {
      v31 = (unsigned __int64)Next;
      Next = Next[1].Next;
      goto LABEL_13;
    }
    if ( *((_DWORD *)&Next->Next + j) == 31678523 )
      goto LABEL_26;
    v16 = (char *)Next + 8 * j;
    v17 = CLockBase<6,2,1,2,3,3>::QueueType(*((_QWORD *)v16 + 3), a3);
    *a5 = v17;
    if ( v17 == 6 )
      break;
    if ( v17 == 1 )
      goto LABEL_65;
    if ( v17 != 3 && v17 != 4 )
    {
      if ( v17 != 5 )
        continue;
      break;
    }
LABEL_20:
    v18 = *((_QWORD *)v16 + 3);
    if ( (unsigned int)(v17 - 5) <= 1 )
    {
      (*(void (__fastcall **)(__int64, __int64))(a1 + 56))(v18, 0xFFFFFFFFLL);
      v24 = Next;
      v25 = j;
      while ( v24[1].Next )
      {
        v24 = v24[1].Next;
        v25 = 0;
      }
      do
      {
        if ( *((_DWORD *)&v24->Next + v25) == 31678523 )
          break;
        ++v25;
      }
      while ( v25 != 4 );
      v26 = v25;
      v27 = v25 - 1;
      *((_QWORD *)v16 + 3) = *((_QWORD *)&v24[1].Next + v26);
      *((_DWORD *)&Next->Next + j) = *((_DWORD *)v24 + v26 - 1);
      *((_QWORD *)&v24[1].Next + v26) = 0;
      *((_DWORD *)v24 + v26 - 1) = 31678523;
      v28 = (struct _SLIST_ENTRY *)(v13 + 8);
      if ( j )
      {
        --j;
      }
      else if ( Next == v28 )
      {
        j = -1;
      }
      else
      {
        Next = (struct _SLIST_ENTRY *)v31;
        j = 4;
        if ( (struct _SLIST_ENTRY *)v31 == v28 )
        {
          v31 = 0;
        }
        else
        {
          v30 = v13 + 8;
          v31 = v13 + 8;
          if ( *(struct _SLIST_ENTRY **)(v13 + 24) != Next )
          {
            do
              v30 = *(_QWORD *)(v30 + 16);
            while ( *(struct _SLIST_ENTRY **)(v30 + 16) != Next );
            v31 = v30;
          }
        }
      }
      if ( !v27 && v24 != v28 )
      {
        v29 = v13 + 8;
        if ( *(struct _SLIST_ENTRY **)(v13 + 24) != v24 )
        {
          do
            v29 = *(_QWORD *)(v29 + 16);
          while ( *(struct _SLIST_ENTRY **)(v29 + 16) != v24 );
        }
        *(_QWORD *)(v29 + 16) = 0;
        CNodeClump::operator delete(v24);
      }
      _InterlockedDecrement((volatile signed __int32 *)(a1 + 120));
    }
    else
    {
      v19 = a2(v18, a3) - 1;
      if ( !v19 )
        goto LABEL_65;
      if ( v19 != 2 )
        goto LABEL_24;
    }
    ++v32;
LABEL_24:
    if ( ((*a5 - 4) & 0xFFFFFFFD) == 0 )
    {
LABEL_65:
      if ( a4 == 2 )
        CReaderWriterLock2::WriteUnlock((CReaderWriterLock2 *)v13);
      else
        CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)v13);
      return v32;
    }
  }
  if ( a4 == 2 )
    goto LABEL_20;
  while ( 1 )
  {
    v23 = *(_DWORD *)v13;
    if ( v23 == _InterlockedCompareExchange((volatile signed __int32 *)v13, v23 - 1, v23) )
      break;
    _mm_pause();
  }
  return v32;
}

```

## disassembly

```asm
0x180008f40  mov     [rsp+arg_10], r8
0x180008f45  mov     [rsp+arg_8], rdx
0x180008f4a  push    rsi
0x180008f4b  push    rdi
0x180008f4c  push    r13
0x180008f4e  sub     rsp, 50h
0x180008f52  cmp     dword ptr [rcx+14h], 0
0x180008f56  mov     r13d, r9d
0x180008f59  mov     rsi, rdx
0x180008f5c  mov     rdi, rcx
0x180008f5f  jz      short loc_180008F6F
0x180008f61  mov     eax, 0FFFFFF9Dh
0x180008f66  add     rsp, 50h
0x180008f6a  pop     r13
0x180008f6c  pop     rdi
0x180008f6d  pop     rsi
0x180008f6e  retn
0x180008f6f  mov     [rsp+68h+arg_18], rbx
0x180008f77  mov     [rsp+68h+var_20], rbp
0x180008f7c  mov     [rsp+68h+var_28], r12
0x180008f81  mov     [rsp+68h+var_30], r14
0x180008f86  mov     [rsp+68h+var_38], r15
0x180008f8b  cmp     r13d, 2
0x180008f8f  jz      short loc_180008FA5
0x180008f91  mov     eax, [rcx+18h]
0x180008f94  and     eax, 7FFFh
0x180008f99  cmp     eax, 1
0x180008f9c  jnb     short loc_180008FB7
0x180008f9e  xor     eax, eax
0x180008fa0  jmp     loc_180009144
0x180008fa5  mov     ebx, [rcx+1Ch]
0x180008fa8  call    cs:__imp_GetCurrentThreadId
0x180008fae  xor     eax, ebx
0x180008fb0  test    eax, 0FFFFFFFCh
0x180008fb5  jnz     short loc_180008F9E
0x180008fb7  test    rsi, rsi
0x180008fba  jz      short loc_180008F9E
0x180008fbc  xor     eax, eax
0x180008fbe  mov     [rsp+68h+arg_0], eax
0x180008fc2  xor     r15d, r15d
0x180008fc5  cmp     r15d, [rdi+7Ch]
0x180008fc9  jnb     loc_180009140
0x180008fcf  mov     ecx, [rdi+44h]
0x180008fd2  mov     ebx, [rdi+4Ch]
0x180008fd5  mov     edx, r15d
0x180008fd8  shr     rdx, cl
0x180008fdb  mov     rcx, [rdi+68h]
0x180008fdf  mov     eax, r15d
0x180008fe2  and     rbx, rax
0x180008fe5  shl     rbx, 6
0x180008fe9  add     rbx, [rcx+rdx*8]
0x180008fed  cmp     r13d, 2
0x180008ff1  jz      loc_1800090E8
0x180008ff7  mov     rcx, rbx; this
0x180008ffa  call    ?ReadLock@CReaderWriterLock2@@QEAAXXZ; CReaderWriterLock2::ReadLock(void)
0x180008fff  lea     rsi, [rbx+8]
0x180009003  mov     [rsp+68h+var_48], 0
0x18000900c  test    rsi, rsi
0x18000900f  jz      loc_1800090C5
0x180009015  xor     ebp, ebp
0x180009017  cmp     ebp, 4
0x18000901a  jge     loc_180009165
0x180009020  movsxd  rax, ebp
0x180009023  cmp     dword ptr [rsi+rax*4], 1E3603Bh
0x18000902a  lea     r14, [rsi+rax*4]
0x18000902e  jz      loc_1800090C5
0x180009034  mov     rcx, [rsi+rax*8+18h]
0x180009039  lea     r12, [rsi+rax*8]
0x18000903d  mov     rdx, [rsp+68h+arg_10]
0x180009045  call    ?QueueType@?$CLockBase@$05$01$00$01$02$02@@SA?AW4LOCK_QUEUE_TYPE@@XZ; CLockBase<6,2,1,2,3,3>::QueueType(void)
0x18000904a  mov     rcx, [rsp+68h+arg_20]
0x180009052  mov     [rcx], eax
0x180009054  cmp     eax, 6
0x180009057  jz      loc_180009123
0x18000905d  mov     edx, eax
0x18000905f  sub     edx, 1
0x180009062  jz      loc_1800092AB
0x180009068  sub     edx, 2
0x18000906b  jnz     loc_180009244
0x180009071  mov     rcx, [r12+18h]
0x180009076  add     eax, 0FFFFFFFBh
0x180009079  cmp     eax, 1
0x18000907c  jbe     loc_1800091AB
0x180009082  mov     rdx, [rsp+68h+arg_10]
0x18000908a  mov     rax, [rsp+68h+arg_8]
0x18000908f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009094  sub     eax, 1
0x180009097  jz      loc_1800092AB
0x18000909d  cmp     eax, 2
0x1800090a0  jnz     short loc_1800090A6
0x1800090a2  inc     [rsp+68h+arg_0]
0x1800090a6  mov     rax, [rsp+68h+arg_20]
0x1800090ae  mov     eax, [rax]
0x1800090b0  sub     eax, 4
0x1800090b3  test    eax, 0FFFFFFFDh
0x1800090b8  jz      loc_1800092AB
0x1800090be  inc     ebp
0x1800090c0  jmp     loc_180009017
0x1800090c5  mov     edx, [rbx]
0x1800090c7  cmp     r13d, 2
0x1800090cb  jz      loc_180009180
0x1800090d1  lea     ecx, [rdx-1]
0x1800090d4  mov     eax, edx
0x1800090d6  lock cmpxchg [rbx], ecx
0x1800090da  cmp     edx, eax
0x1800090dc  jz      loc_180009173
0x1800090e2  pause
0x1800090e4  mov     edx, [rbx]
0x1800090e6  jmp     short loc_1800090D1
0x1800090e8  mov     edx, [rbx]
0x1800090ea  test    dx, dx
0x1800090ed  jnz     short loc_180009109
0x1800090ef  lea     ecx, [rdx+10000h]
0x1800090f5  mov     eax, edx
0x1800090f7  or      ecx, 0FFFFh
0x1800090fd  lock cmpxchg [rbx], ecx
0x180009101  cmp     edx, eax
0x180009103  jz      loc_180008FFF
0x180009109  mov     edx, [rbx]
0x18000910b  mov     eax, edx
0x18000910d  lea     ecx, [rdx+10000h]
0x180009113  lock cmpxchg [rbx], ecx
0x180009117  cmp     edx, eax
0x180009119  jz      loc_18000919C
0x18000911f  pause
0x180009121  jmp     short loc_180009109
0x180009123  cmp     r13d, 2
0x180009127  jz      loc_180009071
0x18000912d  mov     edx, [rbx]
0x18000912f  mov     eax, edx
0x180009131  lea     ecx, [rdx-1]
0x180009134  lock cmpxchg [rbx], ecx
0x180009138  cmp     edx, eax
0x18000913a  jz      short loc_180009140
0x18000913c  pause
0x18000913e  jmp     short loc_18000912D
0x180009140  mov     eax, [rsp+68h+arg_0]
0x180009144  mov     r15, [rsp+68h+var_38]
0x180009149  mov     r14, [rsp+68h+var_30]
0x18000914e  mov     r12, [rsp+68h+var_28]
0x180009153  mov     rbp, [rsp+68h+var_20]
0x180009158  mov     rbx, [rsp+68h+arg_18]
0x180009160  jmp     loc_180008F66
0x180009165  mov     [rsp+68h+var_48], rsi
0x18000916a  mov     rsi, [rsi+10h]
0x18000916e  jmp     loc_18000900C
0x180009173  inc     r15d
0x180009176  jmp     loc_180008FC5
0x180009180  lea     ecx, [rdx-10000h]
0x180009186  mov     eax, edx
0x180009188  and     ecx, 0FFFF0000h
0x18000918e  lock cmpxchg [rbx], ecx
0x180009192  cmp     edx, eax
0x180009194  jz      short loc_180009173
0x180009196  pause
0x180009198  mov     edx, [rbx]
0x18000919a  jmp     short loc_180009180
0x18000919c  mov     dl, 1; bool
0x18000919e  mov     rcx, rbx; this
0x1800091a1  call    ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x1800091a6  jmp     loc_180008FFF
0x1800091ab  mov     rax, [rdi+38h]
0x1800091af  mov     edx, 0FFFFFFFFh
0x1800091b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091b9  mov     r8, rsi
0x1800091bc  mov     edx, ebp
0x1800091be  mov     rax, [r8+10h]
0x1800091c2  test    rax, rax
0x1800091c5  jnz     short loc_18000922E
0x1800091c7  movsxd  rax, edx
0x1800091ca  cmp     dword ptr [r8+rax*4], 1E3603Bh
0x1800091d2  jz      short loc_1800091DB
0x1800091d4  inc     edx
0x1800091d6  cmp     edx, 4
0x1800091d9  jnz     short loc_1800091C7
0x1800091db  movsxd  rax, edx
0x1800091de  dec     edx
0x1800091e0  mov     rcx, rax
0x1800091e3  mov     rax, [r8+rax*8+10h]
0x1800091e8  mov     [r12+18h], rax
0x1800091ed  mov     eax, [r8+rcx*4-4]
0x1800091f2  mov     [r14], eax
0x1800091f5  mov     qword ptr [r8+rcx*8+10h], 0
0x1800091fe  mov     dword ptr [r8+rcx*4-4], 1E3603Bh
0x180009207  lea     rcx, [rbx+8]
0x18000920b  test    ebp, ebp
0x18000920d  jnz     short loc_180009235
0x18000920f  cmp     rsi, rcx
0x180009212  jz      short loc_180009285
0x180009214  mov     rsi, [rsp+68h+var_48]
0x180009219  mov     ebp, 4
0x18000921e  cmp     rsi, rcx
0x180009221  jnz     short loc_18000928C
0x180009223  mov     [rsp+68h+var_48], 0
0x18000922c  jmp     short loc_180009237
0x18000922e  mov     r8, rax
0x180009231  xor     edx, edx
0x180009233  jmp     short loc_1800091BE
0x180009235  dec     ebp
0x180009237  test    edx, edx
0x180009239  jz      short loc_18000925B
0x18000923b  lock dec dword ptr [rdi+78h]
0x18000923f  jmp     loc_1800090A2
0x180009244  sub     edx, 1
0x180009247  jz      loc_180009071
0x18000924d  cmp     edx, 1
0x180009250  jnz     loc_1800090BE
0x180009256  jmp     loc_180009123
0x18000925b  cmp     r8, rcx
0x18000925e  jz      short loc_18000923B
0x180009260  mov     rax, rcx
0x180009263  cmp     [rcx+10h], r8
0x180009267  jz      short loc_180009273
0x180009269  mov     rax, [rax+10h]
0x18000926d  cmp     [rax+10h], r8
0x180009271  jnz     short loc_180009269
0x180009273  mov     rcx, r8; ListEntry
0x180009276  mov     qword ptr [rax+10h], 0
0x18000927e  call    ??3CNodeClump@@SAXPEAX@Z; CNodeClump::operator delete(void *)
0x180009283  jmp     short loc_18000923B
0x180009285  mov     ebp, 0FFFFFFFFh
0x18000928a  jmp     short loc_180009237
0x18000928c  mov     rax, rcx
0x18000928f  mov     [rsp+68h+var_48], rcx
0x180009294  cmp     [rcx+10h], rsi
0x180009298  jz      short loc_180009237
0x18000929a  mov     rax, [rax+10h]
0x18000929e  cmp     [rax+10h], rsi
0x1800092a2  jnz     short loc_18000929A
0x1800092a4  mov     [rsp+68h+var_48], rax
0x1800092a9  jmp     short loc_180009237
0x1800092ab  mov     rcx, rbx; this
0x1800092ae  cmp     r13d, 2
0x1800092b2  jnz     short loc_1800092BE
0x1800092b4  call    ?WriteUnlock@CReaderWriterLock2@@QEAAXXZ; CReaderWriterLock2::WriteUnlock(void)
0x1800092b9  jmp     loc_180009140
0x1800092be  call    ?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x1800092c3  jmp     loc_180009140
```
