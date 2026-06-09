# LKRhash::CLKRLinearHashTable::FindKey(unsigned __int64,void const * *)

- ea: `0x1800015e0`
- end: `0x1800018b2`
- name: `?FindKey@CLKRLinearHashTable@LKRhash@@QEBA?AW4LK_RETCODE@2@_KPEAPEBX@Z`
- size: `722`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180001230`
- `0x180001350`
- `0x180001420`
- `0x18000d698`
- `0x18000f3f8`

## callees

- `0x1800015e0`
- `0x180003840`
- `0x180004180`
- `0x180019624`
- `0x18001971c`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001647`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001647`

## pseudocode

```c
__int64 __fastcall LKRhash::CLKRLinearHashTable::FindKey(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 result; // rax
  int v6; // eax
  volatile signed __int32 *v7; // rdi
  int v8; // ebp
  int v9; // ebx
  signed __int32 v10; // edx
  char v11; // si
  unsigned int v12; // r12d
  unsigned int v13; // eax
  CReaderWriterLock2 *v14; // rbx
  signed __int32 v15; // edx
  signed __int32 v16; // edx
  char *i; // rdi
  int j; // esi
  int v19; // eax
  __int64 v20; // rax
  __int64 v21; // rcx
  void (__fastcall *v22)(__int64, __int64); // rax
  unsigned int v23; // r14d
  bool k; // zf
  signed __int32 v25; // ecx
  signed __int32 v26; // edx
  __int32 v27; // ecx
  signed __int32 v28; // edx

  result = *(unsigned int *)(a1 + 20);
  if ( (_DWORD)result )
    return result;
  if ( !a3 )
    return 4294967200LL;
  v6 = (*(__int64 (__fastcall **)(__int64))(a1 + 40))(a2);
  k = *(_BYTE *)(a1 + 153) == 0;
  v7 = (volatile signed __int32 *)(a1 + 24);
  v8 = v6;
  *a3 = 0;
  if ( !k )
  {
    v9 = *(_DWORD *)(a1 + 28);
    if ( ((v9 ^ GetCurrentThreadId()) & 0xFFFFFFFC) == 0 )
    {
      CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)(a1 + 24));
      v11 = 0;
      goto LABEL_9;
    }
    if ( (unsigned __int16)*v7 == 0xFFFF || (v10 = *v7, v10 != _InterlockedCompareExchange(v7, v10 + 1, v10)) )
      CReaderWriterLock3::_LockSpin((volatile signed __int32 *)(a1 + 24), 3);
  }
  v11 = 1;
LABEL_9:
  if ( *(_DWORD *)(a1 + 20) )
  {
    if ( *(_BYTE *)(a1 + 153) )
    {
      if ( v11 )
      {
        do
          v26 = *v7;
        while ( v26 != _InterlockedCompareExchange(v7, v26 - 1, v26) );
      }
      else
      {
        CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)(a1 + 24));
      }
    }
    return *(unsigned int *)(a1 + 20);
  }
  else
  {
    v12 = (69069 * v8 + 1) & 0xFFFF0000 | ((unsigned int)(1103515245 * v8 + 12345) >> 16);
    v13 = *(_DWORD *)(a1 + 88) & v12;
    if ( v13 < *(_DWORD *)(a1 + 96) )
      v13 = v12 & *(_DWORD *)(a1 + 92);
    v14 = (CReaderWriterLock2 *)(((unsigned __int64)(v13 & *(_DWORD *)(a1 + 76)) << 6)
                               + *(_QWORD *)(*(_QWORD *)(a1 + 104) + 8 * ((unsigned __int64)v13 >> *(_DWORD *)(a1 + 68))));
    if ( *(_BYTE *)(a1 + 153) )
    {
      if ( (*(_DWORD *)v14 & 0xFFFF8000) != 0
        || (v15 = *(_DWORD *)v14, v15 != _InterlockedCompareExchange((volatile signed __int32 *)v14, v15 + 1, v15)) )
      {
        CReaderWriterLock2::_LockSpin(v14, 0);
      }
      if ( *(_BYTE *)(a1 + 153) )
      {
        if ( v11 )
        {
          do
            v16 = *v7;
          while ( v16 != _InterlockedCompareExchange(v7, v16 - 1, v16) );
        }
        else
        {
          v27 = 0;
          if ( ((*(_BYTE *)(a1 + 28) - 1) & 3) != 0 )
            v27 = *(_DWORD *)(a1 + 28) - 1;
          _InterlockedExchange((volatile __int32 *)(a1 + 28), v27);
          if ( !v27 )
          {
            _m_prefetchw((const void *)v7);
            do
              v28 = *v7;
            while ( v28 != _InterlockedCompareExchange(v7, (v28 - 0x10000) & 0xFFFF0000, v28) );
          }
        }
      }
    }
    for ( i = (char *)v14 + 8; i; i = (char *)*((_QWORD *)i + 2) )
    {
      for ( j = 0; j < 4; ++j )
      {
        v19 = *(_DWORD *)&i[4 * j];
        if ( v19 == 31678523 )
          goto LABEL_45;
        if ( v12 == v19 )
        {
          v20 = (*(__int64 (__fastcall **)(_QWORD))(a1 + 32))(*(_QWORD *)&i[8 * j + 24]);
          if ( a2 == v20 || (*(unsigned __int8 (__fastcall **)(__int64, __int64))(a1 + 48))(a2, v20) )
          {
            v21 = *(_QWORD *)&i[8 * j + 24];
            v22 = *(void (__fastcall **)(__int64, __int64))(a1 + 56);
            v23 = 0;
            *a3 = v21;
            v22(v21, 1);
            goto LABEL_27;
          }
        }
      }
    }
LABEL_45:
    v23 = 2;
LABEL_27:
    for ( k = *(_BYTE *)(a1 + 153) == 0;
          !k;
          k = v25 == _InterlockedCompareExchange((volatile signed __int32 *)v14, v25 - 1, v25) )
    {
      v25 = *(_DWORD *)v14;
    }
  }
  return v23;
}

```

## disassembly

```asm
0x1800015e0  mov     [rsp+arg_8], rdx
0x1800015e5  push    r13
0x1800015e7  push    r15
0x1800015e9  sub     rsp, 38h
0x1800015ed  mov     eax, [rcx+14h]
0x1800015f0  mov     r13, r8
0x1800015f3  mov     r15, rcx
0x1800015f6  test    eax, eax
0x1800015f8  jnz     loc_1800017FB
0x1800015fe  test    r8, r8
0x180001601  jz      loc_180001883
0x180001607  mov     rax, [r15+28h]
0x18000160b  mov     rcx, rdx
0x18000160e  mov     [rsp+48h+arg_0], rbx
0x180001613  mov     [rsp+48h+arg_10], rbp
0x180001618  mov     [rsp+48h+arg_18], rsi
0x18000161d  mov     [rsp+48h+var_18], rdi
0x180001622  mov     [rsp+48h+var_28], r14
0x180001627  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000162c  cmp     byte ptr [r15+99h], 0
0x180001634  lea     rdi, [r15+18h]
0x180001638  mov     ebp, eax
0x18000163a  mov     qword ptr [r13+0], 0
0x180001642  jz      short loc_18000167D
0x180001644  mov     ebx, [rdi+4]
0x180001647  call    cs:__imp_GetCurrentThreadId
0x18000164d  xor     eax, ebx
0x18000164f  test    eax, 0FFFFFFFCh
0x180001654  jz      loc_18000188D
0x18000165a  mov     edx, [rdi]
0x18000165c  cmp     dx, 0FFFFh
0x180001661  jz      short loc_180001670
0x180001663  lea     ecx, [rdx+1]
0x180001666  mov     eax, edx
0x180001668  lock cmpxchg [rdi], ecx
0x18000166c  cmp     edx, eax
0x18000166e  jz      short loc_18000167D
0x180001670  mov     edx, 3
0x180001675  mov     rcx, rdi
0x180001678  call    ?_LockSpin@CReaderWriterLock3@@AEAAXW4SPIN_TYPE@1@@Z; CReaderWriterLock3::_LockSpin(CReaderWriterLock3::SPIN_TYPE)
0x18000167d  mov     sil, 1
0x180001680  cmp     dword ptr [r15+14h], 0
0x180001685  jnz     loc_1800017B9
0x18000168b  mov     [rsp+48h+var_20], r12
0x180001690  imul    r12d, ebp, 41C64E6Dh
0x180001697  imul    eax, ebp, 10DCDh
0x18000169d  add     r12d, 3039h
0x1800016a4  inc     eax
0x1800016a6  shr     r12d, 10h
0x1800016aa  and     eax, 0FFFF0000h
0x1800016af  or      r12d, eax
0x1800016b2  mov     eax, r12d
0x1800016b5  and     eax, [r15+58h]
0x1800016b9  cmp     eax, [r15+60h]
0x1800016bd  jb      loc_18000189D
0x1800016c3  mov     ecx, [r15+44h]
0x1800016c7  mov     edx, [r15+4Ch]
0x1800016cb  and     rdx, rax
0x1800016ce  mov     r8d, eax
0x1800016d1  shr     r8, cl
0x1800016d4  mov     rcx, [r15+68h]
0x1800016d8  shl     rdx, 6
0x1800016dc  mov     rbx, [rcx+r8*8]
0x1800016e0  add     rbx, rdx
0x1800016e3  cmp     byte ptr [r15+99h], 0
0x1800016eb  jz      short loc_180001730
0x1800016ed  mov     edx, [rbx]
0x1800016ef  test    edx, 0FFFF8000h
0x1800016f5  jnz     short loc_180001704
0x1800016f7  lea     ecx, [rdx+1]
0x1800016fa  mov     eax, edx
0x1800016fc  lock cmpxchg [rbx], ecx
0x180001700  cmp     edx, eax
0x180001702  jz      short loc_18000170E
0x180001704  xor     edx, edx; bool
0x180001706  mov     rcx, rbx; this
0x180001709  call    ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x18000170e  cmp     byte ptr [r15+99h], 0
0x180001716  jz      short loc_180001730
0x180001718  test    sil, sil
0x18000171b  jz      loc_180001804
0x180001721  mov     edx, [rdi]
0x180001723  mov     eax, edx
0x180001725  lea     ecx, [rdx-1]
0x180001728  lock cmpxchg [rdi], ecx
0x18000172c  cmp     edx, eax
0x18000172e  jnz     short loc_180001721
0x180001730  mov     rbp, [rsp+48h+arg_8]
0x180001735  lea     rdi, [rbx+8]
0x180001739  test    rdi, rdi
0x18000173c  jz      loc_180001878
0x180001742  xor     esi, esi
0x180001744  cmp     esi, 4
0x180001747  jge     loc_1800018A9
0x18000174d  movsxd  rcx, esi
0x180001750  mov     eax, [rdi+rcx*4]
0x180001753  cmp     eax, 1E3603Bh
0x180001758  jz      loc_180001878
0x18000175e  cmp     r12d, eax
0x180001761  jnz     loc_180001864
0x180001767  mov     rax, [r15+20h]
0x18000176b  lea     r14, [rdi+rcx*8]
0x18000176f  mov     rcx, [rdi+rcx*8+18h]
0x180001774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001779  cmp     rbp, rax
0x18000177c  jnz     loc_18000184D
0x180001782  mov     rcx, [r14+18h]
0x180001786  mov     edx, 1
0x18000178b  mov     rax, [r15+38h]
0x18000178f  xor     r14d, r14d
0x180001792  mov     [r13+0], rcx
0x180001796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000179b  mov     r12, [rsp+48h+var_20]
0x1800017a0  cmp     byte ptr [r15+99h], 0
0x1800017a8  jz      short loc_1800017DF
0x1800017aa  mov     ecx, [rbx]
0x1800017ac  mov     eax, ecx
0x1800017ae  lea     edx, [rcx-1]
0x1800017b1  lock cmpxchg [rbx], edx
0x1800017b5  cmp     ecx, eax
0x1800017b7  jmp     short loc_1800017A8
0x1800017b9  cmp     byte ptr [r15+99h], 0
0x1800017c1  jz      short loc_1800017DB
0x1800017c3  test    sil, sil
0x1800017c6  jz      loc_18000186B
0x1800017cc  mov     edx, [rdi]
0x1800017ce  mov     eax, edx
0x1800017d0  lea     ecx, [rdx-1]
0x1800017d3  lock cmpxchg [rdi], ecx
0x1800017d7  cmp     edx, eax
0x1800017d9  jnz     short loc_1800017CC
0x1800017db  mov     r14d, [r15+14h]
0x1800017df  mov     rdi, [rsp+48h+var_18]
0x1800017e4  mov     eax, r14d
0x1800017e7  mov     r14, [rsp+48h+var_28]
0x1800017ec  mov     rsi, [rsp+48h+arg_18]
0x1800017f1  mov     rbp, [rsp+48h+arg_10]
0x1800017f6  mov     rbx, [rsp+48h+arg_0]
0x1800017fb  add     rsp, 38h
0x1800017ff  pop     r15
0x180001801  pop     r13
0x180001803  retn
0x180001804  mov     eax, [rdi+4]
0x180001807  mov     ecx, 0
0x18000180c  dec     eax
0x18000180e  test    al, 3
0x180001810  cmovnz  ecx, eax
0x180001813  mov     eax, ecx
0x180001815  xchg    eax, [rdi+4]
0x180001818  test    ecx, ecx
0x18000181a  jnz     loc_180001730
0x180001820  prefetchw byte ptr [rdi]
0x180001823  nop     dword ptr [rax+00h]
0x180001827  nop     word ptr [rax+rax+00000000h]
0x180001830  mov     edx, [rdi]
0x180001832  mov     eax, edx
0x180001834  lea     ecx, [rdx-10000h]
0x18000183a  and     ecx, 0FFFF0000h
0x180001840  lock cmpxchg [rdi], ecx
0x180001844  cmp     edx, eax
0x180001846  jnz     short loc_180001830
0x180001848  jmp     loc_180001730
0x18000184d  mov     rdx, rax
0x180001850  mov     rcx, rbp
0x180001853  mov     rax, [r15+30h]
0x180001857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000185c  test    al, al
0x18000185e  jnz     loc_180001782
0x180001864  inc     esi
0x180001866  jmp     loc_180001744
0x18000186b  mov     rcx, rdi; this
0x18000186e  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180001873  jmp     loc_1800017DB
0x180001878  mov     r14d, 2
0x18000187e  jmp     loc_18000179B
0x180001883  mov     eax, 0FFFFFFA0h
0x180001888  jmp     loc_1800017FB
0x18000188d  mov     rcx, rdi; this
0x180001890  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180001895  xor     sil, sil
0x180001898  jmp     loc_180001680
0x18000189d  mov     eax, [r15+5Ch]
0x1800018a1  and     eax, r12d
0x1800018a4  jmp     loc_1800016C3
0x1800018a9  mov     rdi, [rdi+10h]
0x1800018ad  jmp     loc_180001739
```
