# CLKRHashTable::InsertRecord(void const *,bool)

- ea: `0x18000e280`
- end: `0x18000e63d`
- name: `?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z`
- size: `957`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007e60`
- `0x180008d30`
- `0x180008de0`
- `0x180008f60`
- `0x18000e280`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e35f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e56c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e35f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e56c`

## pseudocode

```c
__int64 __fastcall CLKRHashTable::InsertRecord(__int64 a1, __int64 a2, char a3)
{
  __int64 result; // rax
  __int64 v6; // rax
  int v7; // eax
  int v8; // edx
  unsigned int v9; // r14d
  unsigned int v10; // ecx
  __int64 v11; // rdx
  __int64 v12; // rdi
  signed __int32 v13; // edx
  unsigned int v14; // eax
  volatile signed __int32 *v15; // rbx
  signed __int32 v16; // edx
  signed __int32 v17; // edx
  _QWORD *v18; // r15
  char v19; // r13
  _QWORD *v20; // rsi
  int i; // ebp
  int v22; // eax
  __int64 v23; // rax
  unsigned int v24; // r15d
  signed __int32 v25; // edx
  signed __int32 v26; // edx
  __int64 v27; // [rsp+60h] [rbp+8h]

  result = *(unsigned int *)(a1 + 48);
  if ( !(_DWORD)result )
  {
    if ( a2 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64))(a1 + 32))(a2);
      v7 = (*(__int64 (__fastcall **)(__int64))(a1 + 40))(v6);
      v8 = *(_DWORD *)(a1 + 52);
      v9 = (69069 * v7 + 1) & 0xFFFF0000 | ((unsigned int)(1103515245 * v7 + 12345) >> 16);
      v10 = (69069 * v9 + 1) & 0xFFFF0000 | ((1048583 * v9 + 12345) >> 16);
      if ( v8 >= 0 )
        v11 = v10 & v8;
      else
        v11 = v10 % *(_DWORD *)(a1 + 20);
      v12 = *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8 * v11);
      if ( *(_DWORD *)(v12 + 28)
        || (v13 = *(_DWORD *)(v12 + 24), (_WORD)v13)
        || v13 != _InterlockedCompareExchange((volatile signed __int32 *)(v12 + 24), (v13 + 0x10000) | 0xFFFF, v13) )
      {
        if ( (*(_DWORD *)(v12 + 28) & 0xFFFFFFFC) == (GetCurrentThreadId() & 0xFFFFFFFC) )
          _InterlockedIncrement((volatile signed __int32 *)(v12 + 28));
        else
          CReaderWriterLock3::_WriteLockSpin((CReaderWriterLock3 *)(v12 + 24));
      }
      else
      {
        _InterlockedExchange((volatile __int32 *)(v12 + 28), GetCurrentThreadId() & 0xFFFFFFFC | 1);
      }
      v14 = *(_DWORD *)(v12 + 88) & v9;
      if ( v14 < *(_DWORD *)(v12 + 96) )
        v14 = v9 & *(_DWORD *)(v12 + 92);
      v15 = (volatile signed __int32 *)(((unsigned __int64)(v14 & *(_DWORD *)(v12 + 76)) << 6)
                                      + *(_QWORD *)(*(_QWORD *)(v12 + 104)
                                                  + 8 * ((unsigned __int64)v14 >> *(_DWORD *)(v12 + 68))));
      if ( (unsigned __int16)*v15
        || (v16 = *v15, v16 != _InterlockedCompareExchange(v15, (v16 + 0x10000) | 0xFFFF, v16)) )
      {
        while ( 1 )
        {
          v17 = *v15;
          if ( v17 == _InterlockedCompareExchange(v15, v17 + 0x10000, v17) )
            break;
          _mm_pause();
        }
        CReaderWriterLock2::_LockSpin((CReaderWriterLock2 *)v15, 1);
      }
      if ( ((*(_BYTE *)(v12 + 28) - 1) & 3) != 0 )
      {
        _InterlockedExchange((volatile __int32 *)(v12 + 28), *(_DWORD *)(v12 + 28) - 1);
      }
      else
      {
        _InterlockedExchange((volatile __int32 *)(v12 + 28), 0);
        while ( 1 )
        {
          v26 = *(_DWORD *)(v12 + 24);
          if ( v26 == _InterlockedCompareExchange(
                        (volatile signed __int32 *)(v12 + 24),
                        (v26 - 0x10000) & 0xFFFF0000,
                        v26) )
            break;
          _mm_pause();
        }
      }
      v18 = 0;
      v19 = 0;
      v27 = (*(__int64 (__fastcall **)(__int64))(v12 + 32))(a2);
      v20 = v15 + 2;
LABEL_19:
      for ( i = 0; ; ++i )
      {
        if ( i >= 4 )
        {
          v18 = v20;
          v20 = (_QWORD *)v20[2];
          if ( v20 )
            goto LABEL_19;
          goto LABEL_37;
        }
        v22 = *((_DWORD *)v20 + i);
        if ( v22 == 31678523 )
          break;
        if ( v9 == v22 )
        {
          if ( a2 == v20[i + 3]
            || (v23 = (*(__int64 (**)(void))(v12 + 32))(),
                (*(unsigned __int8 (__fastcall **)(__int64, __int64))(v12 + 48))(v27, v23)) )
          {
            if ( !a3 )
            {
              v24 = 1;
              goto LABEL_31;
            }
            v19 = 1;
            break;
          }
        }
      }
      if ( v20 )
        goto LABEL_28;
LABEL_37:
      v20 = ALLOC_CACHE_HANDLER::Alloc(CNodeClump::sm_palloc);
      if ( !v20 )
      {
        v24 = -98;
        goto LABEL_31;
      }
      v20[2] = 0;
      i = 0;
      *((_DWORD *)v20 + 3) = 31678523;
      v20[6] = 0;
      *((_DWORD *)v20 + 2) = 31678523;
      v20[5] = 0;
      *((_DWORD *)v20 + 1) = 31678523;
      v20[4] = 0;
      *(_DWORD *)v20 = 31678523;
      v20[3] = 0;
      v18[2] = v20;
LABEL_28:
      v24 = 0;
      (*(void (__fastcall **)(__int64, __int64))(v12 + 56))(a2, 1);
      if ( v19 )
        (*(void (__fastcall **)(_QWORD, __int64))(v12 + 56))(v20[i + 3], 0xFFFFFFFFLL);
      else
        _InterlockedIncrement((volatile signed __int32 *)(v12 + 120));
      *((_DWORD *)v20 + i) = v9;
      v20[i + 3] = a2;
LABEL_31:
      while ( 1 )
      {
        v25 = *v15;
        if ( v25 == _InterlockedCompareExchange(v15, (v25 - 0x10000) & 0xFFFF0000, v25) )
          break;
        _mm_pause();
      }
      if ( !v24 )
      {
        while ( (double)*(int *)(v12 + 120) > (double)*(int *)(v12 + 124) * *(double *)(v12 + 80)
             && !(unsigned int)CLKRLinearHashTable::_Expand(v12) )
          ;
      }
      return v24;
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
0x18000e280  mov     r11, rsp
0x18000e283  mov     [r11+18h], r8b
0x18000e287  push    rbx
0x18000e288  push    r12
0x18000e28a  sub     rsp, 48h
0x18000e28e  mov     eax, [rcx+30h]
0x18000e291  mov     r12, rdx
0x18000e294  mov     rbx, rcx
0x18000e297  test    eax, eax
0x18000e299  jnz     loc_18000E509
0x18000e29f  test    rdx, rdx
0x18000e2a2  jz      loc_18000E62F
0x18000e2a8  mov     rax, [rbx+20h]
0x18000e2ac  mov     rcx, rdx
0x18000e2af  mov     [r11+10h], rbp
0x18000e2b3  mov     [r11-18h], rsi
0x18000e2b7  mov     [r11-20h], rdi
0x18000e2bb  mov     [r11-28h], r13
0x18000e2bf  mov     [r11-30h], r14
0x18000e2c3  mov     [r11-38h], r15
0x18000e2c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2cc  mov     rcx, rax
0x18000e2cf  mov     rax, [rbx+28h]
0x18000e2d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2d8  mov     edx, [rbx+34h]
0x18000e2db  imul    r14d, eax, 41C64E6Dh
0x18000e2e2  imul    ecx, eax, 10DCDh
0x18000e2e8  add     r14d, 3039h
0x18000e2ef  inc     ecx
0x18000e2f1  shr     r14d, 10h
0x18000e2f5  and     ecx, 0FFFF0000h
0x18000e2fb  or      r14d, ecx
0x18000e2fe  imul    ecx, r14d, 100007h
0x18000e305  imul    eax, r14d, 10DCDh
0x18000e30c  add     ecx, 3039h
0x18000e312  inc     eax
0x18000e314  shr     ecx, 10h
0x18000e317  and     eax, 0FFFF0000h
0x18000e31c  or      ecx, eax
0x18000e31e  test    edx, edx
0x18000e320  jns     loc_18000E565
0x18000e326  xor     edx, edx
0x18000e328  mov     eax, ecx
0x18000e32a  div     dword ptr [rbx+14h]
0x18000e32d  mov     rax, [rbx+18h]
0x18000e331  mov     rdi, [rax+rdx*8]
0x18000e335  mov     eax, [rdi+1Ch]
0x18000e338  test    eax, eax
0x18000e33a  jnz     short loc_18000E35F
0x18000e33c  mov     edx, [rdi+18h]
0x18000e33f  test    dx, dx
0x18000e342  jnz     short loc_18000E35F
0x18000e344  lea     ecx, [rdx+10000h]
0x18000e34a  mov     eax, edx
0x18000e34c  or      ecx, 0FFFFh
0x18000e352  lock cmpxchg [rdi+18h], ecx
0x18000e357  cmp     edx, eax
0x18000e359  jz      loc_18000E56C
0x18000e35f  call    cs:__imp_GetCurrentThreadId
0x18000e366  nop     dword ptr [rax+rax+00h]
0x18000e36b  mov     ecx, eax
0x18000e36d  mov     eax, [rdi+1Ch]
0x18000e370  and     eax, 0FFFFFFFCh
0x18000e373  and     ecx, 0FFFFFFFCh
0x18000e376  cmp     eax, ecx
0x18000e378  jz      loc_18000E626
0x18000e37e  lea     rcx, [rdi+18h]; this
0x18000e382  call    ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
0x18000e387  mov     eax, r14d
0x18000e38a  and     eax, [rdi+58h]
0x18000e38d  cmp     eax, [rdi+60h]
0x18000e390  jnb     short loc_18000E398
0x18000e392  mov     eax, [rdi+5Ch]
0x18000e395  and     eax, r14d
0x18000e398  mov     ecx, [rdi+44h]
0x18000e39b  mov     edx, [rdi+4Ch]
0x18000e39e  and     rdx, rax
0x18000e3a1  mov     r8d, eax
0x18000e3a4  shr     r8, cl
0x18000e3a7  mov     rcx, [rdi+68h]
0x18000e3ab  shl     rdx, 6
0x18000e3af  mov     rbx, [rcx+r8*8]
0x18000e3b3  add     rbx, rdx
0x18000e3b6  mov     edx, [rbx]
0x18000e3b8  test    dx, dx
0x18000e3bb  jnz     short loc_18000E3D3
0x18000e3bd  lea     ecx, [rdx+10000h]
0x18000e3c3  mov     eax, edx
0x18000e3c5  or      ecx, 0FFFFh
0x18000e3cb  lock cmpxchg [rbx], ecx
0x18000e3cf  cmp     edx, eax
0x18000e3d1  jz      short loc_18000E3F3
0x18000e3d3  mov     edx, [rbx]
0x18000e3d5  mov     eax, edx
0x18000e3d7  lea     ecx, [rdx+10000h]
0x18000e3dd  lock cmpxchg [rbx], ecx
0x18000e3e1  cmp     edx, eax
0x18000e3e3  jnz     loc_18000E586
0x18000e3e9  mov     dl, 1; bool
0x18000e3eb  mov     rcx, rbx; this
0x18000e3ee  call    ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x18000e3f3  mov     eax, [rdi+1Ch]
0x18000e3f6  dec     eax
0x18000e3f8  test    al, 3
0x18000e3fa  jz      loc_18000E53E
0x18000e400  xchg    eax, [rdi+1Ch]
0x18000e403  mov     rax, [rdi+20h]
0x18000e407  xor     r15d, r15d
0x18000e40a  xor     r13b, r13b
0x18000e40d  mov     rcx, r12
0x18000e410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e415  mov     [rsp+58h+arg_0], rax
0x18000e41a  lea     rsi, [rbx+8]
0x18000e41e  xor     ebp, ebp
0x18000e420  cmp     ebp, 4
0x18000e423  jge     loc_18000E512
0x18000e429  movsxd  rcx, ebp
0x18000e42c  mov     eax, [rsi+rcx*4]
0x18000e42f  cmp     eax, 1E3603Bh
0x18000e434  jz      short loc_18000E479
0x18000e436  cmp     r14d, eax
0x18000e439  jnz     loc_18000E5A1
0x18000e43f  mov     rcx, [rsi+rcx*8+18h]
0x18000e444  cmp     r12, rcx
0x18000e447  jz      short loc_18000E46B
0x18000e449  mov     rax, [rdi+20h]
0x18000e44d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e452  mov     rcx, [rsp+58h+arg_0]
0x18000e457  mov     rdx, rax
0x18000e45a  mov     rax, [rdi+30h]
0x18000e45e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e463  test    al, al
0x18000e465  jz      loc_18000E5A1
0x18000e46b  cmp     [rsp+58h+arg_10], r13b
0x18000e470  jz      loc_18000E58D
0x18000e476  mov     r13b, 1
0x18000e479  test    rsi, rsi
0x18000e47c  jz      loc_18000E522
0x18000e482  xor     eax, eax
0x18000e484  mov     r15d, eax
0x18000e487  mov     edx, 1
0x18000e48c  mov     rax, [rdi+38h]
0x18000e490  mov     rcx, r12
0x18000e493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e498  test    r13b, r13b
0x18000e49b  jz      loc_18000E598
0x18000e4a1  mov     rax, [rdi+38h]
0x18000e4a5  mov     edx, 0FFFFFFFFh
0x18000e4aa  movsxd  rcx, ebp
0x18000e4ad  mov     rcx, [rsi+rcx*8+18h]
0x18000e4b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4b7  movsxd  rax, ebp
0x18000e4ba  mov     [rsi+rax*4], r14d
0x18000e4be  mov     [rsi+rax*8+18h], r12
0x18000e4c3  mov     r14, [rsp+58h+var_30]
0x18000e4c8  mov     r13, [rsp+58h+var_28]
0x18000e4cd  mov     rsi, [rsp+58h+var_18]
0x18000e4d2  mov     rbp, [rsp+58h+arg_8]
0x18000e4d7  mov     edx, [rbx]
0x18000e4d9  mov     eax, edx
0x18000e4db  lea     ecx, [rdx-10000h]
0x18000e4e1  and     ecx, 0FFFF0000h
0x18000e4e7  lock cmpxchg [rbx], ecx
0x18000e4eb  cmp     edx, eax
0x18000e4ed  jz      short loc_18000E4F3
0x18000e4ef  pause
0x18000e4f1  jmp     short loc_18000E4D7
0x18000e4f3  test    r15d, r15d
0x18000e4f6  jz      loc_18000E5F0
0x18000e4fc  mov     rdi, [rsp+58h+var_20]
0x18000e501  mov     eax, r15d
0x18000e504  mov     r15, [rsp+58h+var_38]
0x18000e509  add     rsp, 48h
0x18000e50d  pop     r12
0x18000e50f  pop     rbx
0x18000e510  retn
0x18000e512  mov     r15, rsi
0x18000e515  mov     rsi, [rsi+10h]
0x18000e519  test    rsi, rsi
0x18000e51c  jnz     loc_18000E41E
0x18000e522  mov     rcx, cs:?sm_palloc@CNodeClump@@1PEAVALLOC_CACHE_HANDLER@@EA; this
0x18000e529  call    ?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18000e52e  mov     rsi, rax
0x18000e531  test    rax, rax
0x18000e534  jnz     short loc_18000E5A8
0x18000e536  mov     r15d, 0FFFFFF9Eh
0x18000e53c  jmp     short loc_18000E4C3
0x18000e53e  xor     eax, eax
0x18000e540  xchg    eax, [rdi+1Ch]
0x18000e543  mov     edx, [rdi+18h]
0x18000e546  mov     eax, edx
0x18000e548  lea     ecx, [rdx-10000h]
0x18000e54e  and     ecx, 0FFFF0000h
0x18000e554  lock cmpxchg [rdi+18h], ecx
0x18000e559  cmp     edx, eax
0x18000e55b  jz      loc_18000E403
0x18000e561  pause
0x18000e563  jmp     short loc_18000E543
0x18000e565  and     edx, ecx
0x18000e567  jmp     loc_18000E32D
0x18000e56c  call    cs:__imp_GetCurrentThreadId
0x18000e573  nop     dword ptr [rax+rax+00h]
0x18000e578  and     eax, 0FFFFFFFCh
0x18000e57b  or      eax, 1
0x18000e57e  xchg    eax, [rdi+1Ch]
0x18000e581  jmp     loc_18000E387
0x18000e586  pause
0x18000e588  jmp     loc_18000E3D3
0x18000e58d  mov     r15d, 1
0x18000e593  jmp     loc_18000E4C3
0x18000e598  lock inc dword ptr [rdi+78h]
0x18000e59c  jmp     loc_18000E4B7
0x18000e5a1  inc     ebp
0x18000e5a3  jmp     loc_18000E420
0x18000e5a8  xor     eax, eax
0x18000e5aa  mov     [rsi+10h], rax
0x18000e5ae  mov     ebp, eax
0x18000e5b0  mov     dword ptr [rsi+0Ch], 1E3603Bh
0x18000e5b7  mov     [rsi+30h], rax
0x18000e5bb  mov     dword ptr [rsi+8], 1E3603Bh
0x18000e5c2  mov     [rsi+28h], rax
0x18000e5c6  mov     dword ptr [rsi+4], 1E3603Bh
0x18000e5cd  mov     [rsi+20h], rax
0x18000e5d1  mov     dword ptr [rsi], 1E3603Bh
0x18000e5d7  mov     [rsi+18h], rax
0x18000e5db  mov     [r15+10h], rsi
0x18000e5df  jmp     loc_18000E484
0x18000e5f0  mov     eax, [rdi+78h]
0x18000e5f3  xorps   xmm0, xmm0
0x18000e5f6  xorps   xmm1, xmm1
0x18000e5f9  cvtsi2sd xmm1, rax
0x18000e5fe  mov     eax, [rdi+7Ch]
0x18000e601  cvtsi2sd xmm0, rax
0x18000e606  mulsd   xmm0, qword ptr [rdi+50h]
0x18000e60b  comisd  xmm1, xmm0
0x18000e60f  jbe     loc_18000E4FC
0x18000e615  mov     rcx, rdi
0x18000e618  call    ?_Expand@CLKRLinearHashTable@@AEAA?AW4LK_RETCODE@@XZ; CLKRLinearHashTable::_Expand(void)
0x18000e61d  test    eax, eax
0x18000e61f  jz      short loc_18000E5F0
0x18000e621  jmp     loc_18000E4FC
0x18000e626  lock inc dword ptr [rdi+1Ch]
0x18000e62a  jmp     loc_18000E387
0x18000e62f  mov     eax, 0FFFFFFA0h
0x18000e634  add     rsp, 48h
0x18000e638  pop     r12
0x18000e63a  pop     rbx
0x18000e63b  retn
```
