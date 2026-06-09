# CLKRHashTable::InsertRecord(void const *,bool)

- ea: `0x18000d1a0`
- end: `0x18000d54c`
- name: `?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z`
- size: `940`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007180`
- `0x180008000`
- `0x1800080a0`
- `0x180008220`
- `0x18000d1a0`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d27f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d485`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d27f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d485`

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
0x18000d1a0  mov     r11, rsp
0x18000d1a3  mov     [r11+18h], r8b
0x18000d1a7  push    rbx
0x18000d1a8  push    r12
0x18000d1aa  sub     rsp, 48h
0x18000d1ae  mov     eax, [rcx+30h]
0x18000d1b1  mov     r12, rdx
0x18000d1b4  mov     rbx, rcx
0x18000d1b7  test    eax, eax
0x18000d1b9  jnz     loc_18000D423
0x18000d1bf  test    rdx, rdx
0x18000d1c2  jz      loc_18000D53F
0x18000d1c8  mov     rax, [rbx+20h]
0x18000d1cc  mov     rcx, rdx
0x18000d1cf  mov     [r11+10h], rbp
0x18000d1d3  mov     [r11-18h], rsi
0x18000d1d7  mov     [r11-20h], rdi
0x18000d1db  mov     [r11-28h], r13
0x18000d1df  mov     [r11-30h], r14
0x18000d1e3  mov     [r11-38h], r15
0x18000d1e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1ec  mov     rcx, rax
0x18000d1ef  mov     rax, [rbx+28h]
0x18000d1f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1f8  mov     edx, [rbx+34h]
0x18000d1fb  imul    r14d, eax, 41C64E6Dh
0x18000d202  imul    ecx, eax, 10DCDh
0x18000d208  add     r14d, 3039h
0x18000d20f  inc     ecx
0x18000d211  shr     r14d, 10h
0x18000d215  and     ecx, 0FFFF0000h
0x18000d21b  or      r14d, ecx
0x18000d21e  imul    ecx, r14d, 100007h
0x18000d225  imul    eax, r14d, 10DCDh
0x18000d22c  add     ecx, 3039h
0x18000d232  inc     eax
0x18000d234  shr     ecx, 10h
0x18000d237  and     eax, 0FFFF0000h
0x18000d23c  or      ecx, eax
0x18000d23e  test    edx, edx
0x18000d240  jns     loc_18000D47E
0x18000d246  xor     edx, edx
0x18000d248  mov     eax, ecx
0x18000d24a  div     dword ptr [rbx+14h]
0x18000d24d  mov     rax, [rbx+18h]
0x18000d251  mov     rdi, [rax+rdx*8]
0x18000d255  mov     eax, [rdi+1Ch]
0x18000d258  test    eax, eax
0x18000d25a  jnz     short loc_18000D27F
0x18000d25c  mov     edx, [rdi+18h]
0x18000d25f  test    dx, dx
0x18000d262  jnz     short loc_18000D27F
0x18000d264  lea     ecx, [rdx+10000h]
0x18000d26a  mov     eax, edx
0x18000d26c  or      ecx, 0FFFFh
0x18000d272  lock cmpxchg [rdi+18h], ecx
0x18000d277  cmp     edx, eax
0x18000d279  jz      loc_18000D485
0x18000d27f  call    cs:__imp_GetCurrentThreadId
0x18000d285  mov     ecx, eax
0x18000d287  mov     eax, [rdi+1Ch]
0x18000d28a  and     eax, 0FFFFFFFCh
0x18000d28d  and     ecx, 0FFFFFFFCh
0x18000d290  cmp     eax, ecx
0x18000d292  jz      loc_18000D536
0x18000d298  lea     rcx, [rdi+18h]; this
0x18000d29c  call    ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
0x18000d2a1  mov     eax, r14d
0x18000d2a4  and     eax, [rdi+58h]
0x18000d2a7  cmp     eax, [rdi+60h]
0x18000d2aa  jnb     short loc_18000D2B2
0x18000d2ac  mov     eax, [rdi+5Ch]
0x18000d2af  and     eax, r14d
0x18000d2b2  mov     ecx, [rdi+44h]
0x18000d2b5  mov     edx, [rdi+4Ch]
0x18000d2b8  and     rdx, rax
0x18000d2bb  mov     r8d, eax
0x18000d2be  shr     r8, cl
0x18000d2c1  mov     rcx, [rdi+68h]
0x18000d2c5  shl     rdx, 6
0x18000d2c9  mov     rbx, [rcx+r8*8]
0x18000d2cd  add     rbx, rdx
0x18000d2d0  mov     edx, [rbx]
0x18000d2d2  test    dx, dx
0x18000d2d5  jnz     short loc_18000D2ED
0x18000d2d7  lea     ecx, [rdx+10000h]
0x18000d2dd  mov     eax, edx
0x18000d2df  or      ecx, 0FFFFh
0x18000d2e5  lock cmpxchg [rbx], ecx
0x18000d2e9  cmp     edx, eax
0x18000d2eb  jz      short loc_18000D30D
0x18000d2ed  mov     edx, [rbx]
0x18000d2ef  mov     eax, edx
0x18000d2f1  lea     ecx, [rdx+10000h]
0x18000d2f7  lock cmpxchg [rbx], ecx
0x18000d2fb  cmp     edx, eax
0x18000d2fd  jnz     loc_18000D499
0x18000d303  mov     dl, 1; bool
0x18000d305  mov     rcx, rbx; this
0x18000d308  call    ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x18000d30d  mov     eax, [rdi+1Ch]
0x18000d310  dec     eax
0x18000d312  test    al, 3
0x18000d314  jz      loc_18000D457
0x18000d31a  xchg    eax, [rdi+1Ch]
0x18000d31d  mov     rax, [rdi+20h]
0x18000d321  xor     r15d, r15d
0x18000d324  xor     r13b, r13b
0x18000d327  mov     rcx, r12
0x18000d32a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d32f  mov     [rsp+58h+arg_0], rax
0x18000d334  lea     rsi, [rbx+8]
0x18000d338  xor     ebp, ebp
0x18000d33a  cmp     ebp, 4
0x18000d33d  jge     loc_18000D42B
0x18000d343  movsxd  rcx, ebp
0x18000d346  mov     eax, [rsi+rcx*4]
0x18000d349  cmp     eax, 1E3603Bh
0x18000d34e  jz      short loc_18000D393
0x18000d350  cmp     r14d, eax
0x18000d353  jnz     loc_18000D4B4
0x18000d359  mov     rcx, [rsi+rcx*8+18h]
0x18000d35e  cmp     r12, rcx
0x18000d361  jz      short loc_18000D385
0x18000d363  mov     rax, [rdi+20h]
0x18000d367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d36c  mov     rcx, [rsp+58h+arg_0]
0x18000d371  mov     rdx, rax
0x18000d374  mov     rax, [rdi+30h]
0x18000d378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d37d  test    al, al
0x18000d37f  jz      loc_18000D4B4
0x18000d385  cmp     [rsp+58h+arg_10], r13b
0x18000d38a  jz      loc_18000D4A0
0x18000d390  mov     r13b, 1
0x18000d393  test    rsi, rsi
0x18000d396  jz      loc_18000D43B
0x18000d39c  xor     eax, eax
0x18000d39e  mov     r15d, eax
0x18000d3a1  mov     edx, 1
0x18000d3a6  mov     rax, [rdi+38h]
0x18000d3aa  mov     rcx, r12
0x18000d3ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3b2  test    r13b, r13b
0x18000d3b5  jz      loc_18000D4AB
0x18000d3bb  mov     rax, [rdi+38h]
0x18000d3bf  mov     edx, 0FFFFFFFFh
0x18000d3c4  movsxd  rcx, ebp
0x18000d3c7  mov     rcx, [rsi+rcx*8+18h]
0x18000d3cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3d1  movsxd  rax, ebp
0x18000d3d4  mov     [rsi+rax*4], r14d
0x18000d3d8  mov     [rsi+rax*8+18h], r12
0x18000d3dd  mov     r14, [rsp+58h+var_30]
0x18000d3e2  mov     r13, [rsp+58h+var_28]
0x18000d3e7  mov     rsi, [rsp+58h+var_18]
0x18000d3ec  mov     rbp, [rsp+58h+arg_8]
0x18000d3f1  mov     edx, [rbx]
0x18000d3f3  mov     eax, edx
0x18000d3f5  lea     ecx, [rdx-10000h]
0x18000d3fb  and     ecx, 0FFFF0000h
0x18000d401  lock cmpxchg [rbx], ecx
0x18000d405  cmp     edx, eax
0x18000d407  jz      short loc_18000D40D
0x18000d409  pause
0x18000d40b  jmp     short loc_18000D3F1
0x18000d40d  test    r15d, r15d
0x18000d410  jz      loc_18000D500
0x18000d416  mov     rdi, [rsp+58h+var_20]
0x18000d41b  mov     eax, r15d
0x18000d41e  mov     r15, [rsp+58h+var_38]
0x18000d423  add     rsp, 48h
0x18000d427  pop     r12
0x18000d429  pop     rbx
0x18000d42a  retn
0x18000d42b  mov     r15, rsi
0x18000d42e  mov     rsi, [rsi+10h]
0x18000d432  test    rsi, rsi
0x18000d435  jnz     loc_18000D338
0x18000d43b  mov     rcx, cs:?sm_palloc@CNodeClump@@1PEAVALLOC_CACHE_HANDLER@@EA; this
0x18000d442  call    ?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18000d447  mov     rsi, rax
0x18000d44a  test    rax, rax
0x18000d44d  jnz     short loc_18000D4BB
0x18000d44f  mov     r15d, 0FFFFFF9Eh
0x18000d455  jmp     short loc_18000D3DD
0x18000d457  xor     eax, eax
0x18000d459  xchg    eax, [rdi+1Ch]
0x18000d45c  mov     edx, [rdi+18h]
0x18000d45f  mov     eax, edx
0x18000d461  lea     ecx, [rdx-10000h]
0x18000d467  and     ecx, 0FFFF0000h
0x18000d46d  lock cmpxchg [rdi+18h], ecx
0x18000d472  cmp     edx, eax
0x18000d474  jz      loc_18000D31D
0x18000d47a  pause
0x18000d47c  jmp     short loc_18000D45C
0x18000d47e  and     edx, ecx
0x18000d480  jmp     loc_18000D24D
0x18000d485  call    cs:__imp_GetCurrentThreadId
0x18000d48b  and     eax, 0FFFFFFFCh
0x18000d48e  or      eax, 1
0x18000d491  xchg    eax, [rdi+1Ch]
0x18000d494  jmp     loc_18000D2A1
0x18000d499  pause
0x18000d49b  jmp     loc_18000D2ED
0x18000d4a0  mov     r15d, 1
0x18000d4a6  jmp     loc_18000D3DD
0x18000d4ab  lock inc dword ptr [rdi+78h]
0x18000d4af  jmp     loc_18000D3D1
0x18000d4b4  inc     ebp
0x18000d4b6  jmp     loc_18000D33A
0x18000d4bb  xor     eax, eax
0x18000d4bd  mov     [rsi+10h], rax
0x18000d4c1  mov     ebp, eax
0x18000d4c3  mov     dword ptr [rsi+0Ch], 1E3603Bh
0x18000d4ca  mov     [rsi+30h], rax
0x18000d4ce  mov     dword ptr [rsi+8], 1E3603Bh
0x18000d4d5  mov     [rsi+28h], rax
0x18000d4d9  mov     dword ptr [rsi+4], 1E3603Bh
0x18000d4e0  mov     [rsi+20h], rax
0x18000d4e4  mov     dword ptr [rsi], 1E3603Bh
0x18000d4ea  mov     [rsi+18h], rax
0x18000d4ee  mov     [r15+10h], rsi
0x18000d4f2  jmp     loc_18000D39E
0x18000d500  mov     eax, [rdi+78h]
0x18000d503  xorps   xmm0, xmm0
0x18000d506  xorps   xmm1, xmm1
0x18000d509  cvtsi2sd xmm1, rax
0x18000d50e  mov     eax, [rdi+7Ch]
0x18000d511  cvtsi2sd xmm0, rax
0x18000d516  mulsd   xmm0, qword ptr [rdi+50h]
0x18000d51b  comisd  xmm1, xmm0
0x18000d51f  jbe     loc_18000D416
0x18000d525  mov     rcx, rdi
0x18000d528  call    ?_Expand@CLKRLinearHashTable@@AEAA?AW4LK_RETCODE@@XZ; CLKRLinearHashTable::_Expand(void)
0x18000d52d  test    eax, eax
0x18000d52f  jz      short loc_18000D500
0x18000d531  jmp     loc_18000D416
0x18000d536  lock inc dword ptr [rdi+1Ch]
0x18000d53a  jmp     loc_18000D2A1
0x18000d53f  mov     eax, 0FFFFFFA0h
0x18000d544  add     rsp, 48h
0x18000d548  pop     r12
0x18000d54a  pop     rbx
0x18000d54b  retn
```
