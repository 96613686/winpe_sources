# LKRhash::CLKRLinearHashTable::_DeleteRecord(void const *,ulong)

- ea: `0x1800029d0`
- end: `0x180002d59`
- name: `?_DeleteRecord@CLKRLinearHashTable@LKRhash@@AEAA?AW4LK_RETCODE@2@PEBXK@Z`
- size: `905`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180001940`
- `0x1800025c4`

## callees

- `0x1800029d0`
- `0x180002d60`
- `0x1800037e0`
- `0x180019624`
- `0x180019a34`
- `0x18001a284`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002a25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002cf1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002a25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002cf1`

## pseudocode

```c
__int64 __fastcall LKRhash::CLKRLinearHashTable::_DeleteRecord(__int64 a1, __int64 a2, int a3)
{
  signed __int32 v6; // r8d
  unsigned int v7; // eax
  unsigned int v8; // r12d
  unsigned __int64 v9; // rbx
  signed __int32 v10; // edx
  __int32 v11; // ecx
  unsigned __int64 v12; // r15
  unsigned __int64 v13; // rsi
  int i; // edi
  __int64 v15; // rbp
  __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  bool j; // zf
  signed __int32 v19; // edx
  double v21; // xmm6_8
  int v22; // ecx
  __int64 v23; // rax
  __int64 v24; // rcx
  signed __int32 v25; // edx
  signed __int32 v26; // edx

  if ( *(_BYTE *)(a1 + 153) )
  {
    if ( *(_DWORD *)(a1 + 28)
      || (v6 = *(_DWORD *)(a1 + 24), (_WORD)v6)
      || v6 != _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 24), (v6 + 0x10000) | 0xFFFF, v6) )
    {
      if ( (*(_DWORD *)(a1 + 28) & 0xFFFFFFFC) == (GetCurrentThreadId() & 0xFFFFFFFC) )
        _InterlockedExchange((volatile __int32 *)(a1 + 28), *(_DWORD *)(a1 + 28) + 1);
      else
        CReaderWriterLock3::_WriteLockSpin((CReaderWriterLock3 *)(a1 + 24));
    }
    else
    {
      _InterlockedExchange((volatile __int32 *)(a1 + 28), GetCurrentThreadId() & 0xFFFFFFFC | 1);
    }
  }
  if ( *(_DWORD *)(a1 + 20) )
  {
    LKRhash::CLKRLinearHashTable::WriteUnlock((LKRhash::CLKRLinearHashTable *)a1);
    return *(unsigned int *)(a1 + 20);
  }
  else
  {
    v7 = *(_DWORD *)(a1 + 88) & a3;
    v8 = 2;
    if ( v7 < *(_DWORD *)(a1 + 96) )
      v7 = a3 & *(_DWORD *)(a1 + 92);
    v9 = ((unsigned __int64)(v7 & *(_DWORD *)(a1 + 76)) << 6)
       + *(_QWORD *)(*(_QWORD *)(a1 + 104) + 8 * ((unsigned __int64)v7 >> *(_DWORD *)(a1 + 68)));
    if ( *(_BYTE *)(a1 + 153) )
    {
      if ( (unsigned __int16)*(_DWORD *)v9
        || (v10 = *(_DWORD *)v9,
            v10 != _InterlockedCompareExchange((volatile signed __int32 *)v9, (v10 + 0x10000) | 0xFFFF, v10)) )
      {
        do
          v25 = *(_DWORD *)v9;
        while ( v25 != _InterlockedCompareExchange((volatile signed __int32 *)v9, v25 + 0x10000, v25) );
        CReaderWriterLock2::_LockSpin((CReaderWriterLock2 *)v9, 1);
      }
      if ( *(_BYTE *)(a1 + 153) )
      {
        v11 = 0;
        if ( ((*(_BYTE *)(a1 + 28) - 1) & 3) != 0 )
          v11 = *(_DWORD *)(a1 + 28) - 1;
        _InterlockedExchange((volatile __int32 *)(a1 + 28), v11);
        if ( !v11 )
        {
          _m_prefetchw((const void *)(a1 + 24));
          do
            v26 = *(_DWORD *)(a1 + 24);
          while ( v26 != _InterlockedCompareExchange(
                           (volatile signed __int32 *)(a1 + 24),
                           (v26 - 0x10000) & 0xFFFF0000,
                           v26) );
        }
      }
    }
    (*(void (__fastcall **)(__int64))(a1 + 32))(a2);
    v12 = v9 + 8;
    v13 = v9 + 8;
LABEL_17:
    if ( v13 )
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= 4 )
        {
          v13 = *(_QWORD *)(v13 + 16);
          goto LABEL_17;
        }
        v15 = i;
        if ( *(_DWORD *)(v13 + 4LL * i) == 31678523 )
          goto LABEL_28;
        v16 = *(_QWORD *)(v13 + 8LL * i + 24);
        if ( v16 == a2 )
          break;
      }
      if ( (unsigned int)i <= 3 )
      {
        (*(void (__fastcall **)(__int64, __int64))(a1 + 56))(v16, 0xFFFFFFFFLL);
        v17 = v13;
        while ( *(_QWORD *)(v17 + 16) )
        {
          v17 = *(_QWORD *)(v17 + 16);
          i = 0;
        }
        do
        {
          if ( *(_DWORD *)(v17 + 4LL * i) == 31678523 )
            break;
          ++i;
        }
        while ( i != 4 );
        if ( (unsigned int)(i - 1) <= 3 )
        {
          v23 = *(_QWORD *)(v17 + 8LL * i + 16);
          v24 = 4LL * i - 4;
          if ( (v23 || *(_DWORD *)(v24 + v17) != 31678523)
            && (i == 4 || !*(_QWORD *)(v17 + 8LL * i + 24) && *(_DWORD *)(v17 + 4LL * i) == 31678523) )
          {
            *(_QWORD *)(v13 + 8 * v15 + 24) = v23;
            *(_DWORD *)(v13 + 4 * v15) = *(_DWORD *)(v17 + v24);
            *(_QWORD *)(v17 + 8LL * i + 16) = 0;
            *(_DWORD *)(v17 + v24) = 31678523;
            if ( i == 1 && v17 != v12 )
            {
              if ( *(_QWORD *)(v9 + 24) != v17 )
              {
                do
                  v12 = *(_QWORD *)(v12 + 16);
                while ( *(_QWORD *)(v12 + 16) != v17 );
              }
              *(_QWORD *)(v12 + 16) = 0;
              LKRhash::CLKRLinearHashTable::_FreeNodeClump(
                (LKRhash::CLKRLinearHashTable *)a1,
                (struct LKRhash::CNodeClump *)v17);
            }
            _InterlockedDecrement((volatile signed __int32 *)(a1 + 120));
          }
        }
      }
      v8 = 0;
    }
LABEL_28:
    for ( j = *(_BYTE *)(a1 + 153) == 0;
          !j;
          j = v19 == _InterlockedCompareExchange((volatile signed __int32 *)v9, (v19 - 0x10000) & 0xFFFF0000, v19) )
    {
      v19 = *(_DWORD *)v9;
    }
    if ( !v8 )
    {
      v21 = (double)(*(_DWORD *)(a1 + 120) + (*(_DWORD *)(a1 + 120) >> 4));
      do
        v22 = *(_DWORD *)(a1 + 124);
      while ( (double)v22 * *(double *)(a1 + 80) > v21
           && (unsigned int)v22 > *(_DWORD *)(a1 + 72)
           && !(unsigned int)LKRhash::CLKRLinearHashTable::_Contract(a1) );
    }
    return v8;
  }
}

```

## disassembly

```asm
0x1800029d0  push    rbx
0x1800029d2  push    rdi
0x1800029d3  push    r13
0x1800029d5  push    r14
0x1800029d7  sub     rsp, 38h
0x1800029db  cmp     byte ptr [rcx+99h], 0
0x1800029e2  mov     edi, r8d
0x1800029e5  mov     r14, rdx
0x1800029e8  mov     r13, rcx
0x1800029eb  jz      short loc_180002A35
0x1800029ed  mov     eax, [rcx+1Ch]
0x1800029f0  test    eax, eax
0x1800029f2  jnz     loc_180002CF1
0x1800029f8  mov     r8d, [rcx+18h]
0x1800029fc  test    r8w, r8w
0x180002a00  jnz     loc_180002CF1
0x180002a06  lea     ecx, [r8+10000h]
0x180002a0d  mov     eax, r8d
0x180002a10  or      ecx, 0FFFFh
0x180002a16  lock cmpxchg [r13+18h], ecx
0x180002a1c  cmp     r8d, eax
0x180002a1f  jnz     loc_180002CF1
0x180002a25  call    cs:__imp_GetCurrentThreadId
0x180002a2b  and     eax, 0FFFFFFFCh
0x180002a2e  or      eax, 1
0x180002a31  xchg    eax, [r13+1Ch]
0x180002a35  cmp     dword ptr [r13+14h], 0
0x180002a3a  jnz     loc_180002B93
0x180002a40  mov     [rsp+58h+arg_0], rbp
0x180002a45  mov     eax, edi
0x180002a47  and     eax, [r13+58h]
0x180002a4b  mov     [rsp+58h+arg_8], rsi
0x180002a50  mov     [rsp+58h+arg_10], r12
0x180002a55  mov     r12d, 2
0x180002a5b  mov     [rsp+58h+var_28], r15
0x180002a60  cmp     eax, [r13+60h]
0x180002a64  jb      loc_180002D22
0x180002a6a  mov     ecx, [r13+44h]
0x180002a6e  mov     edx, [r13+4Ch]
0x180002a72  and     rdx, rax
0x180002a75  mov     r8d, eax
0x180002a78  shr     r8, cl
0x180002a7b  mov     rcx, [r13+68h]
0x180002a7f  shl     rdx, 6
0x180002a83  mov     rbx, [rcx+r8*8]
0x180002a87  add     rbx, rdx
0x180002a8a  cmp     byte ptr [r13+99h], 0
0x180002a92  jz      short loc_180002AE1
0x180002a94  mov     edx, [rbx]
0x180002a96  test    dx, dx
0x180002a99  jnz     loc_180002CA8
0x180002a9f  lea     ecx, [rdx+10000h]
0x180002aa5  mov     eax, edx
0x180002aa7  or      ecx, 0FFFFh
0x180002aad  lock cmpxchg [rbx], ecx
0x180002ab1  cmp     edx, eax
0x180002ab3  jnz     loc_180002CA8
0x180002ab9  cmp     byte ptr [r13+99h], 0
0x180002ac1  jz      short loc_180002AE1
0x180002ac3  mov     eax, [r13+1Ch]
0x180002ac7  mov     ecx, 0
0x180002acc  dec     eax
0x180002ace  test    al, 3
0x180002ad0  cmovnz  ecx, eax
0x180002ad3  mov     eax, ecx
0x180002ad5  xchg    eax, [r13+1Ch]
0x180002ad9  test    ecx, ecx
0x180002adb  jz      loc_180002CC9
0x180002ae1  mov     rax, [r13+20h]
0x180002ae5  mov     rcx, r14
0x180002ae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002aed  lea     r15, [rbx+8]
0x180002af1  mov     rsi, r15
0x180002af4  test    rsi, rsi
0x180002af7  jz      short loc_180002B62
0x180002af9  xor     edi, edi
0x180002afb  cmp     edi, 4
0x180002afe  jge     loc_180002C2B
0x180002b04  movsxd  rbp, edi
0x180002b07  cmp     dword ptr [rsi+rbp*4], 1E3603Bh
0x180002b0e  jz      short loc_180002B62
0x180002b10  mov     rcx, [rsi+rbp*8+18h]
0x180002b15  cmp     rcx, r14
0x180002b18  jnz     loc_180002D2D
0x180002b1e  cmp     edi, 3
0x180002b21  ja      short loc_180002B5F
0x180002b23  mov     rax, [r13+38h]
0x180002b27  mov     edx, 0FFFFFFFFh
0x180002b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b31  mov     rdx, rsi; struct LKRhash::CNodeClump *
0x180002b34  mov     rax, [rdx+10h]
0x180002b38  test    rax, rax
0x180002b3b  jnz     loc_180002C21
0x180002b41  movsxd  rax, edi
0x180002b44  cmp     dword ptr [rdx+rax*4], 1E3603Bh
0x180002b4b  jnz     loc_180002C11
0x180002b51  lea     r9d, [rdi-1]
0x180002b55  cmp     r9d, 3
0x180002b59  jbe     loc_180002C34
0x180002b5f  xor     r12d, r12d
0x180002b62  mov     r15, [rsp+58h+var_28]
0x180002b67  mov     rsi, [rsp+58h+arg_8]
0x180002b6c  mov     rbp, [rsp+58h+arg_0]
0x180002b71  cmp     byte ptr [r13+99h], 0
0x180002b79  jz      short loc_180002BAA
0x180002b7b  mov     edx, [rbx]
0x180002b7d  mov     eax, edx
0x180002b7f  lea     ecx, [rdx-10000h]
0x180002b85  and     ecx, 0FFFF0000h
0x180002b8b  lock cmpxchg [rbx], ecx
0x180002b8f  cmp     edx, eax
0x180002b91  jmp     short loc_180002B79
0x180002b93  mov     rcx, r13; this
0x180002b96  call    ?WriteUnlock@CLKRLinearHashTable@LKRhash@@QEBAXXZ; LKRhash::CLKRLinearHashTable::WriteUnlock(void)
0x180002b9b  mov     eax, [r13+14h]
0x180002b9f  add     rsp, 38h
0x180002ba3  pop     r14
0x180002ba5  pop     r13
0x180002ba7  pop     rdi
0x180002ba8  pop     rbx
0x180002ba9  retn
0x180002baa  test    r12d, r12d
0x180002bad  jz      short loc_180002BC2
0x180002baf  mov     eax, r12d
0x180002bb2  mov     r12, [rsp+58h+arg_10]
0x180002bb7  add     rsp, 38h
0x180002bbb  pop     r14
0x180002bbd  pop     r13
0x180002bbf  pop     rdi
0x180002bc0  pop     rbx
0x180002bc1  retn
0x180002bc2  mov     eax, [r13+78h]
0x180002bc6  shr     eax, 4
0x180002bc9  add     eax, [r13+78h]
0x180002bcd  movaps  [rsp+58h+var_38], xmm6
0x180002bd2  xorps   xmm6, xmm6
0x180002bd5  cvtsi2sd xmm6, rax
0x180002bda  nop     word ptr [rax+rax+00h]
0x180002be0  mov     ecx, [r13+7Ch]
0x180002be4  xorps   xmm0, xmm0
0x180002be7  cvtsi2sd xmm0, rcx
0x180002bec  mulsd   xmm0, qword ptr [r13+50h]
0x180002bf2  comisd  xmm0, xmm6
0x180002bf6  jbe     short loc_180002C0A
0x180002bf8  cmp     ecx, [r13+48h]
0x180002bfc  jbe     short loc_180002C0A
0x180002bfe  mov     rcx, r13
0x180002c01  call    ?_Contract@CLKRLinearHashTable@LKRhash@@AEAA?AW4LK_RETCODE@2@XZ; LKRhash::CLKRLinearHashTable::_Contract(void)
0x180002c06  test    eax, eax
0x180002c08  jz      short loc_180002BE0
0x180002c0a  movaps  xmm6, [rsp+58h+var_38]
0x180002c0f  jmp     short loc_180002BAF
0x180002c11  inc     edi
0x180002c13  cmp     edi, 4
0x180002c16  jnz     loc_180002B41
0x180002c1c  jmp     loc_180002B51
0x180002c21  mov     rdx, rax
0x180002c24  xor     edi, edi
0x180002c26  jmp     loc_180002B34
0x180002c2b  mov     rsi, [rsi+10h]
0x180002c2f  jmp     loc_180002AF4
0x180002c34  movsxd  r8, edi
0x180002c37  mov     rax, [rdx+r8*8+10h]
0x180002c3c  lea     rcx, ds:0FFFFFFFFFFFFFFFCh[r8*4]
0x180002c44  test    rax, rax
0x180002c47  jnz     short loc_180002C56
0x180002c49  cmp     dword ptr [rcx+rdx], 1E3603Bh
0x180002c50  jz      loc_180002B5F
0x180002c56  cmp     edi, 4
0x180002c59  jz      short loc_180002C75
0x180002c5b  cmp     qword ptr [rdx+r8*8+18h], 0
0x180002c61  jnz     loc_180002B5F
0x180002c67  cmp     dword ptr [rdx+r8*4], 1E3603Bh
0x180002c6f  jnz     loc_180002B5F
0x180002c75  mov     [rsi+rbp*8+18h], rax
0x180002c7a  mov     eax, [rdx+rcx]
0x180002c7d  mov     [rsi+rbp*4], eax
0x180002c80  mov     qword ptr [rdx+r8*8+10h], 0
0x180002c89  mov     dword ptr [rdx+rcx], 1E3603Bh
0x180002c90  test    r9d, r9d
0x180002c93  jnz     short loc_180002C9E
0x180002c95  cmp     rdx, r15
0x180002c98  jnz     loc_180002D34
0x180002c9e  lock dec dword ptr [r13+78h]
0x180002ca3  jmp     loc_180002B5F
0x180002ca8  mov     edx, [rbx]
0x180002caa  mov     eax, edx
0x180002cac  lea     ecx, [rdx+10000h]
0x180002cb2  lock cmpxchg [rbx], ecx
0x180002cb6  cmp     edx, eax
0x180002cb8  jnz     short loc_180002CA8
0x180002cba  mov     dl, 1; bool
0x180002cbc  mov     rcx, rbx; this
0x180002cbf  call    ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x180002cc4  jmp     loc_180002AB9
0x180002cc9  prefetchw byte ptr [r13+18h]
0x180002cce  xchg    ax, ax
0x180002cd0  mov     edx, [r13+18h]
0x180002cd4  mov     eax, edx
0x180002cd6  lea     ecx, [rdx-10000h]
0x180002cdc  and     ecx, 0FFFF0000h
0x180002ce2  lock cmpxchg [r13+18h], ecx
0x180002ce8  cmp     edx, eax
0x180002cea  jnz     short loc_180002CD0
0x180002cec  jmp     loc_180002AE1
0x180002cf1  call    cs:__imp_GetCurrentThreadId
0x180002cf7  mov     ecx, [r13+1Ch]
0x180002cfb  and     eax, 0FFFFFFFCh
0x180002cfe  and     ecx, 0FFFFFFFCh
0x180002d01  cmp     ecx, eax
0x180002d03  jnz     short loc_180002D14
0x180002d05  mov     eax, [r13+1Ch]
0x180002d09  inc     eax
0x180002d0b  xchg    eax, [r13+1Ch]
0x180002d0f  jmp     loc_180002A35
0x180002d14  lea     rcx, [r13+18h]; this
0x180002d18  call    ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
0x180002d1d  jmp     loc_180002A35
0x180002d22  mov     eax, [r13+5Ch]
0x180002d26  and     eax, edi
0x180002d28  jmp     loc_180002A6A
0x180002d2d  inc     edi
0x180002d2f  jmp     loc_180002AFB
0x180002d34  cmp     [r15+10h], rdx
0x180002d38  jz      short loc_180002D44
0x180002d3a  mov     r15, [r15+10h]
0x180002d3e  cmp     [r15+10h], rdx
0x180002d42  jnz     short loc_180002D3A
0x180002d44  mov     rcx, r13; this
0x180002d47  mov     qword ptr [r15+10h], 0
0x180002d4f  call    ?_FreeNodeClump@CLKRLinearHashTable@LKRhash@@AEAA_NPEAVCNodeClump@2@@Z; LKRhash::CLKRLinearHashTable::_FreeNodeClump(LKRhash::CNodeClump *)
0x180002d54  jmp     loc_180002C9E
```
