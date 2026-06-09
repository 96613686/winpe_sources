# LKRhash::CLKRLinearHashTable_Iterator::_Increment(bool)

- ea: `0x180003cf0`
- end: `0x180003ec6`
- name: `?_Increment@CLKRLinearHashTable_Iterator@LKRhash@@IEAA_N_N@Z`
- size: `470`
- prototype: `bool __fastcall(LKRhash::CLKRLinearHashTable_Iterator *__hidden this, bool)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000813c`
- `0x18000f680`
- `0x180019c50`

## callees

- `0x180003cf0`
- `0x180003ed0`
- `0x180008224`
- `0x180019624`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003d92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003d92`

## pseudocode

```c
char __fastcall LKRhash::CLKRLinearHashTable_Iterator::_Increment(LKRhash::CLKRLinearHashTable_Iterator *this, char a2)
{
  char *v3; // rsi
  _QWORD *v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  _QWORD *v7; // r15
  __int64 v8; // rdx
  __int64 v9; // rbx
  unsigned int v10; // eax
  struct LKRhash::CBucket *v11; // r14
  int v12; // ebx
  DWORD CurrentThreadId; // eax
  LKRhash::CLKRLinearHashTable *v14; // rcx
  _BYTE *v15; // rax
  int v16; // eax
  char result; // al
  signed __int32 v18; // edx
  bool i; // zf
  signed __int32 v20; // edx
  signed __int32 v21; // edx
  signed __int32 v22; // edx

  if ( a2 )
    LKRhash::CLKRLinearHashTable_Iterator::_AddRef(this, -1);
  v3 = (char *)this + 8;
  while ( 2 )
  {
    v4 = v3;
    do
    {
      v5 = *((__int16 *)this + 10);
      *((_WORD *)this + 10) = v5 + 1;
      if ( (_WORD)v5 != 3 && *(_QWORD *)(*v4 + 8 * v5 + 32) )
      {
        LKRhash::CLKRLinearHashTable_Iterator::_AddRef(this, 1);
        return 1;
      }
      v6 = *v4;
      v7 = v4;
      *((_WORD *)this + 10) = -1;
      v3 = (char *)v4;
      v8 = *(_QWORD *)(v6 + 16);
      *v4 = v8;
    }
    while ( v8 );
    ++*((_DWORD *)this + 4);
    v9 = *(_QWORD *)this;
    v10 = *((_DWORD *)this + 4);
    if ( v10 < *(_DWORD *)(*(_QWORD *)this + 124LL) )
    {
      v11 = (struct LKRhash::CBucket *)(*(_QWORD *)(*(_QWORD *)(v9 + 104)
                                                  + 8 * ((unsigned __int64)v10 >> *(_DWORD *)(v9 + 68)))
                                      + ((unsigned __int64)(v10 & *(_DWORD *)(v9 + 76)) << 6));
      if ( *(_BYTE *)(v9 + 153) )
      {
        v12 = *(_DWORD *)(v9 + 28);
        CurrentThreadId = GetCurrentThreadId();
        v14 = *(LKRhash::CLKRLinearHashTable **)this;
        i = ((v12 ^ CurrentThreadId) & 0xFFFFFFFC) == 0;
        v15 = (_BYTE *)(*(_QWORD *)this + 153LL);
        if ( !i )
        {
          if ( !*v15 || (v16 = *((_DWORD *)v14 + 6), v14 = *(LKRhash::CLKRLinearHashTable **)this, (v16 & 0x7FFF) != 0) )
          {
            LKRhash::CLKRLinearHashTable::_BucketReadLock(v14, v11);
            if ( *(_BYTE *)(*(_QWORD *)this + 153LL) )
            {
              do
                v22 = *(_DWORD *)v11;
              while ( v22 != _InterlockedCompareExchange((volatile signed __int32 *)v11, v22 - 1, v22) );
            }
          }
LABEL_13:
          *v7 = (char *)v11 + 8;
          goto LABEL_14;
        }
      }
      else
      {
        v15 = (_BYTE *)(v9 + 153);
      }
      if ( *v15 )
      {
        if ( (unsigned __int16)*(_DWORD *)v11
          || (v18 = *(_DWORD *)v11,
              v18 != _InterlockedCompareExchange((volatile signed __int32 *)v11, (v18 + 0x10000) | 0xFFFF, v18)) )
        {
          do
            v21 = *(_DWORD *)v11;
          while ( v21 != _InterlockedCompareExchange((volatile signed __int32 *)v11, v21 + 0x10000, v21) );
          CReaderWriterLock2::_LockSpin(v11, 1);
        }
      }
      for ( i = *(_BYTE *)(*(_QWORD *)this + 153LL) == 0;
            !i;
            i = v20 == _InterlockedCompareExchange((volatile signed __int32 *)v11, (v20 - 0x10000) & 0xFFFF0000, v20) )
      {
        v20 = *(_DWORD *)v11;
      }
      goto LABEL_13;
    }
LABEL_14:
    if ( *((_DWORD *)this + 4) < *(_DWORD *)(*(_QWORD *)this + 124LL) )
      continue;
    break;
  }
  result = 0;
  *(_QWORD *)this = 0;
  *v7 = 0;
  *((_DWORD *)this + 4) = 0;
  *((_WORD *)this + 10) = 0;
  return result;
}

```

## disassembly

```asm
0x180003cf0  mov     [rsp+arg_10], rbp
0x180003cf5  mov     [rsp+arg_18], rsi
0x180003cfa  push    rdi
0x180003cfb  push    r14
0x180003cfd  push    r15
0x180003cff  sub     rsp, 20h
0x180003d03  mov     rdi, rcx
0x180003d06  mov     ebp, 0FFFFFFFFh
0x180003d0b  test    dl, dl
0x180003d0d  jnz     loc_180003EBA
0x180003d13  lea     rsi, [rdi+8]
0x180003d17  mov     [rsp+38h+arg_0], rbx
0x180003d1c  nop     dword ptr [rax+00h]
0x180003d20  mov     rax, rsi
0x180003d23  movsx   rdx, word ptr [rdi+14h]
0x180003d28  lea     ecx, [rdx+1]
0x180003d2b  mov     [rdi+14h], cx
0x180003d2f  cmp     cx, 4
0x180003d33  jz      short loc_180003D44
0x180003d35  mov     rcx, [rax]
0x180003d38  cmp     qword ptr [rcx+rdx*8+20h], 0
0x180003d3e  jnz     loc_180003E92
0x180003d44  mov     rcx, [rax]
0x180003d47  mov     r15, rax
0x180003d4a  mov     [rdi+14h], bp
0x180003d4e  mov     rsi, rax
0x180003d51  mov     rdx, [rcx+10h]
0x180003d55  mov     [rax], rdx
0x180003d58  test    rdx, rdx
0x180003d5b  jnz     short loc_180003D23
0x180003d5d  inc     dword ptr [rdi+10h]
0x180003d60  mov     rbx, [rdi]
0x180003d63  mov     eax, [rdi+10h]
0x180003d66  cmp     eax, [rbx+7Ch]
0x180003d69  jnb     short loc_180003DCF
0x180003d6b  mov     ecx, [rbx+44h]
0x180003d6e  mov     edx, eax
0x180003d70  mov     r14d, [rbx+4Ch]
0x180003d74  shr     rdx, cl
0x180003d77  and     r14, rax
0x180003d7a  mov     rcx, [rbx+68h]
0x180003d7e  shl     r14, 6
0x180003d82  add     r14, [rcx+rdx*8]
0x180003d86  cmp     byte ptr [rbx+99h], 0
0x180003d8d  jz      short loc_180003DF2
0x180003d8f  mov     ebx, [rbx+1Ch]
0x180003d92  call    cs:__imp_GetCurrentThreadId
0x180003d98  mov     rcx, [rdi]; this
0x180003d9b  xor     eax, ebx
0x180003d9d  test    eax, 0FFFFFFFCh
0x180003da2  lea     rax, [rcx+99h]
0x180003da9  jz      short loc_180003DF9
0x180003dab  cmp     byte ptr [rax], 0
0x180003dae  jz      loc_180003E63
0x180003db4  mov     eax, [rcx+18h]
0x180003db7  mov     rcx, [rdi]
0x180003dba  and     eax, 7FFFh
0x180003dbf  cmp     eax, 1
0x180003dc2  jnb     loc_180003E63
0x180003dc8  lea     rax, [r14+8]
0x180003dcc  mov     [r15], rax
0x180003dcf  mov     rax, [rdi]
0x180003dd2  mov     ecx, [rax+7Ch]
0x180003dd5  cmp     [rdi+10h], ecx
0x180003dd8  jb      loc_180003D20
0x180003dde  xor     eax, eax
0x180003de0  mov     [rdi], rax
0x180003de3  mov     [r15], rax
0x180003de6  mov     [rdi+10h], eax
0x180003de9  mov     [rdi+14h], ax
0x180003ded  jmp     loc_180003EA1
0x180003df2  lea     rax, [rbx+99h]
0x180003df9  cmp     byte ptr [rax], 0
0x180003dfc  jz      short loc_180003E1D
0x180003dfe  mov     edx, [r14]
0x180003e01  test    dx, dx
0x180003e04  jnz     short loc_180003E43
0x180003e06  lea     ecx, [rdx+10000h]
0x180003e0c  mov     eax, edx
0x180003e0e  or      ecx, 0FFFFh
0x180003e14  lock cmpxchg [r14], ecx
0x180003e19  cmp     edx, eax
0x180003e1b  jnz     short loc_180003E43
0x180003e1d  mov     rax, [rdi]
0x180003e20  cmp     byte ptr [rax+99h], 0
0x180003e27  jz      short loc_180003DC8
0x180003e29  mov     edx, [r14]
0x180003e2c  mov     eax, edx
0x180003e2e  lea     ecx, [rdx-10000h]
0x180003e34  and     ecx, 0FFFF0000h
0x180003e3a  lock cmpxchg [r14], ecx
0x180003e3f  cmp     edx, eax
0x180003e41  jmp     short loc_180003E27
0x180003e43  mov     edx, [r14]
0x180003e46  mov     eax, edx
0x180003e48  lea     ecx, [rdx+10000h]
0x180003e4e  lock cmpxchg [r14], ecx
0x180003e53  cmp     edx, eax
0x180003e55  jnz     short loc_180003E43
0x180003e57  mov     dl, 1; bool
0x180003e59  mov     rcx, r14; this
0x180003e5c  call    ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x180003e61  jmp     short loc_180003E1D
0x180003e63  mov     rdx, r14; struct LKRhash::CBucket *
0x180003e66  call    ?_BucketReadLock@CLKRLinearHashTable@LKRhash@@AEBAXPEAVCBucket@2@@Z; LKRhash::CLKRLinearHashTable::_BucketReadLock(LKRhash::CBucket *)
0x180003e6b  mov     rax, [rdi]
0x180003e6e  cmp     byte ptr [rax+99h], 0
0x180003e75  jz      loc_180003DC8
0x180003e7b  mov     edx, [r14]
0x180003e7e  mov     eax, edx
0x180003e80  lea     ecx, [rdx-1]
0x180003e83  lock cmpxchg [r14], ecx
0x180003e88  cmp     edx, eax
0x180003e8a  jz      loc_180003DC8
0x180003e90  jmp     short loc_180003E7B
0x180003e92  mov     edx, 1; int
0x180003e97  mov     rcx, rdi; this
0x180003e9a  call    ?_AddRef@CLKRLinearHashTable_Iterator@LKRhash@@IEBAXH@Z; LKRhash::CLKRLinearHashTable_Iterator::_AddRef(int)
0x180003e9f  mov     al, 1
0x180003ea1  mov     rbx, [rsp+38h+arg_0]
0x180003ea6  mov     rbp, [rsp+38h+arg_10]
0x180003eab  mov     rsi, [rsp+38h+arg_18]
0x180003eb0  add     rsp, 20h
0x180003eb4  pop     r15
0x180003eb6  pop     r14
0x180003eb8  pop     rdi
0x180003eb9  retn
0x180003eba  mov     edx, ebp; int
0x180003ebc  call    ?_AddRef@CLKRLinearHashTable_Iterator@LKRhash@@IEBAXH@Z; LKRhash::CLKRLinearHashTable_Iterator::_AddRef(int)
0x180003ec1  jmp     loc_180003D13
```
