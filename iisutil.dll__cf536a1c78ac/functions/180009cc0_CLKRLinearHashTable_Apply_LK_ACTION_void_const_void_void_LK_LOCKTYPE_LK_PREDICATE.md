# CLKRLinearHashTable::_Apply(LK_ACTION (*)(void const *,void *),void *,LK_LOCKTYPE,LK_PREDICATE &)

- ea: `0x180009cc0`
- end: `0x18000a058`
- name: `?_Apply@CLKRLinearHashTable@@AEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@AEAW4LK_PREDICATE@@@Z`
- size: `920`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001ad60`

## callees

- `0x180008de0`
- `0x180009570`
- `0x180009c10`
- `0x180009cc0`
- `0x18000be70`
- `0x18000f810`
- `0x180016770`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009d29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009d29`

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
0x180009cc0  mov     [rsp+arg_10], r8
0x180009cc5  mov     [rsp+arg_8], rdx
0x180009cca  push    rsi
0x180009ccb  push    rdi
0x180009ccc  push    r13
0x180009cce  sub     rsp, 50h
0x180009cd2  cmp     dword ptr [rcx+14h], 0
0x180009cd6  mov     r13d, r9d
0x180009cd9  mov     rsi, rdx
0x180009cdc  mov     rdi, rcx
0x180009cdf  jz      short loc_180009CF0
0x180009ce1  mov     eax, 0FFFFFF9Dh
0x180009ce6  add     rsp, 50h
0x180009cea  pop     r13
0x180009cec  pop     rdi
0x180009ced  pop     rsi
0x180009cee  retn
0x180009cf0  mov     [rsp+68h+arg_18], rbx
0x180009cf8  mov     [rsp+68h+var_20], rbp
0x180009cfd  mov     [rsp+68h+var_28], r12
0x180009d02  mov     [rsp+68h+var_30], r14
0x180009d07  mov     [rsp+68h+var_38], r15
0x180009d0c  cmp     r13d, 2
0x180009d10  jz      short loc_180009D26
0x180009d12  mov     eax, [rcx+18h]
0x180009d15  and     eax, 7FFFh
0x180009d1a  cmp     eax, 1
0x180009d1d  jnb     short loc_180009D3E
0x180009d1f  xor     eax, eax
0x180009d21  jmp     loc_180009ED3
0x180009d26  mov     ebx, [rcx+1Ch]
0x180009d29  call    cs:__imp_GetCurrentThreadId
0x180009d30  nop     dword ptr [rax+rax+00h]
0x180009d35  xor     eax, ebx
0x180009d37  test    eax, 0FFFFFFFCh
0x180009d3c  jnz     short loc_180009D1F
0x180009d3e  test    rsi, rsi
0x180009d41  jz      short loc_180009D1F
0x180009d43  xor     eax, eax
0x180009d45  mov     [rsp+68h+arg_0], eax
0x180009d49  xor     r15d, r15d
0x180009d4c  cmp     r15d, [rdi+7Ch]
0x180009d50  jnb     loc_180009ECF
0x180009d56  mov     ecx, [rdi+44h]
0x180009d59  mov     ebx, [rdi+4Ch]
0x180009d5c  mov     edx, r15d
0x180009d5f  shr     rdx, cl
0x180009d62  mov     rcx, [rdi+68h]
0x180009d66  mov     eax, r15d
0x180009d69  and     rbx, rax
0x180009d6c  shl     rbx, 6
0x180009d70  add     rbx, [rcx+rdx*8]
0x180009d74  cmp     r13d, 2
0x180009d78  jz      loc_180009E77
0x180009d7e  mov     rcx, rbx; this
0x180009d81  call    ?ReadLock@CReaderWriterLock2@@QEAAXXZ; CReaderWriterLock2::ReadLock(void)
0x180009d86  lea     rsi, [rbx+8]
0x180009d8a  mov     [rsp+68h+var_48], 0
0x180009d93  test    rsi, rsi
0x180009d96  jz      loc_180009E4C
0x180009d9c  xor     ebp, ebp
0x180009d9e  cmp     ebp, 4
0x180009da1  jge     loc_180009EF4
0x180009da7  movsxd  rax, ebp
0x180009daa  cmp     dword ptr [rsi+rax*4], 1E3603Bh
0x180009db1  lea     r14, [rsi+rax*4]
0x180009db5  jz      loc_180009E4C
0x180009dbb  mov     rcx, [rsi+rax*8+18h]
0x180009dc0  lea     r12, [rsi+rax*8]
0x180009dc4  mov     rdx, [rsp+68h+arg_10]
0x180009dcc  call    ?QueueType@?$CLockBase@$05$01$00$01$02$02@@SA?AW4LOCK_QUEUE_TYPE@@XZ; CLockBase<6,2,1,2,3,3>::QueueType(void)
0x180009dd1  mov     rcx, [rsp+68h+arg_20]
0x180009dd9  mov     [rcx], eax
0x180009ddb  cmp     eax, 6
0x180009dde  jz      loc_180009EB2
0x180009de4  mov     edx, eax
0x180009de6  sub     edx, 1
0x180009de9  jz      loc_18000A03B
0x180009def  sub     edx, 2
0x180009df2  jnz     loc_180009FD4
0x180009df8  mov     rcx, [r12+18h]
0x180009dfd  add     eax, 0FFFFFFFBh
0x180009e00  cmp     eax, 1
0x180009e03  jbe     loc_180009F3B
0x180009e09  mov     rdx, [rsp+68h+arg_10]
0x180009e11  mov     rax, [rsp+68h+arg_8]
0x180009e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e1b  sub     eax, 1
0x180009e1e  jz      loc_18000A03B
0x180009e24  cmp     eax, 2
0x180009e27  jnz     short loc_180009E2D
0x180009e29  inc     [rsp+68h+arg_0]
0x180009e2d  mov     rax, [rsp+68h+arg_20]
0x180009e35  mov     eax, [rax]
0x180009e37  sub     eax, 4
0x180009e3a  test    eax, 0FFFFFFFDh
0x180009e3f  jz      loc_18000A03B
0x180009e45  inc     ebp
0x180009e47  jmp     loc_180009D9E
0x180009e4c  mov     edx, [rbx]
0x180009e4e  cmp     r13d, 2
0x180009e52  jz      loc_180009F10
0x180009e58  nop     dword ptr [rax+rax+00000000h]
0x180009e60  lea     ecx, [rdx-1]
0x180009e63  mov     eax, edx
0x180009e65  lock cmpxchg [rbx], ecx
0x180009e69  cmp     edx, eax
0x180009e6b  jz      loc_180009F02
0x180009e71  pause
0x180009e73  mov     edx, [rbx]
0x180009e75  jmp     short loc_180009E60
0x180009e77  mov     edx, [rbx]
0x180009e79  test    dx, dx
0x180009e7c  jnz     short loc_180009E98
0x180009e7e  lea     ecx, [rdx+10000h]
0x180009e84  mov     eax, edx
0x180009e86  or      ecx, 0FFFFh
0x180009e8c  lock cmpxchg [rbx], ecx
0x180009e90  cmp     edx, eax
0x180009e92  jz      loc_180009D86
0x180009e98  mov     edx, [rbx]
0x180009e9a  mov     eax, edx
0x180009e9c  lea     ecx, [rdx+10000h]
0x180009ea2  lock cmpxchg [rbx], ecx
0x180009ea6  cmp     edx, eax
0x180009ea8  jz      loc_180009F2C
0x180009eae  pause
0x180009eb0  jmp     short loc_180009E98
0x180009eb2  cmp     r13d, 2
0x180009eb6  jz      loc_180009DF8
0x180009ebc  mov     edx, [rbx]
0x180009ebe  mov     eax, edx
0x180009ec0  lea     ecx, [rdx-1]
0x180009ec3  lock cmpxchg [rbx], ecx
0x180009ec7  cmp     edx, eax
0x180009ec9  jz      short loc_180009ECF
0x180009ecb  pause
0x180009ecd  jmp     short loc_180009EBC
0x180009ecf  mov     eax, [rsp+68h+arg_0]
0x180009ed3  mov     r15, [rsp+68h+var_38]
0x180009ed8  mov     r14, [rsp+68h+var_30]
0x180009edd  mov     r12, [rsp+68h+var_28]
0x180009ee2  mov     rbp, [rsp+68h+var_20]
0x180009ee7  mov     rbx, [rsp+68h+arg_18]
0x180009eef  jmp     loc_180009CE6
0x180009ef4  mov     [rsp+68h+var_48], rsi
0x180009ef9  mov     rsi, [rsi+10h]
0x180009efd  jmp     loc_180009D93
0x180009f02  inc     r15d
0x180009f05  jmp     loc_180009D4C
0x180009f10  lea     ecx, [rdx-10000h]
0x180009f16  mov     eax, edx
0x180009f18  and     ecx, 0FFFF0000h
0x180009f1e  lock cmpxchg [rbx], ecx
0x180009f22  cmp     edx, eax
0x180009f24  jz      short loc_180009F02
0x180009f26  pause
0x180009f28  mov     edx, [rbx]
0x180009f2a  jmp     short loc_180009F10
0x180009f2c  mov     dl, 1; bool
0x180009f2e  mov     rcx, rbx; this
0x180009f31  call    ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x180009f36  jmp     loc_180009D86
0x180009f3b  mov     rax, [rdi+38h]
0x180009f3f  mov     edx, 0FFFFFFFFh
0x180009f44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f49  mov     r8, rsi
0x180009f4c  mov     edx, ebp
0x180009f4e  mov     rax, [r8+10h]
0x180009f52  test    rax, rax
0x180009f55  jnz     short loc_180009FBE
0x180009f57  movsxd  rax, edx
0x180009f5a  cmp     dword ptr [r8+rax*4], 1E3603Bh
0x180009f62  jz      short loc_180009F6B
0x180009f64  inc     edx
0x180009f66  cmp     edx, 4
0x180009f69  jnz     short loc_180009F57
0x180009f6b  movsxd  rax, edx
0x180009f6e  dec     edx
0x180009f70  mov     rcx, rax
0x180009f73  mov     rax, [r8+rax*8+10h]
0x180009f78  mov     [r12+18h], rax
0x180009f7d  mov     eax, [r8+rcx*4-4]
0x180009f82  mov     [r14], eax
0x180009f85  mov     qword ptr [r8+rcx*8+10h], 0
0x180009f8e  mov     dword ptr [r8+rcx*4-4], 1E3603Bh
0x180009f97  lea     rcx, [rbx+8]
0x180009f9b  test    ebp, ebp
0x180009f9d  jnz     short loc_180009FC5
0x180009f9f  cmp     rsi, rcx
0x180009fa2  jz      short loc_18000A015
0x180009fa4  mov     rsi, [rsp+68h+var_48]
0x180009fa9  mov     ebp, 4
0x180009fae  cmp     rsi, rcx
0x180009fb1  jnz     short loc_18000A01C
0x180009fb3  mov     [rsp+68h+var_48], 0
0x180009fbc  jmp     short loc_180009FC7
0x180009fbe  mov     r8, rax
0x180009fc1  xor     edx, edx
0x180009fc3  jmp     short loc_180009F4E
0x180009fc5  dec     ebp
0x180009fc7  test    edx, edx
0x180009fc9  jz      short loc_180009FEB
0x180009fcb  lock dec dword ptr [rdi+78h]
0x180009fcf  jmp     loc_180009E29
0x180009fd4  sub     edx, 1
0x180009fd7  jz      loc_180009DF8
0x180009fdd  cmp     edx, 1
0x180009fe0  jnz     loc_180009E45
0x180009fe6  jmp     loc_180009EB2
0x180009feb  cmp     r8, rcx
0x180009fee  jz      short loc_180009FCB
0x180009ff0  mov     rax, rcx
0x180009ff3  cmp     [rcx+10h], r8
0x180009ff7  jz      short loc_18000A003
0x180009ff9  mov     rax, [rax+10h]
0x180009ffd  cmp     [rax+10h], r8
0x18000a001  jnz     short loc_180009FF9
0x18000a003  mov     rcx, r8; ListEntry
0x18000a006  mov     qword ptr [rax+10h], 0
0x18000a00e  call    ??3CNodeClump@@SAXPEAX@Z; CNodeClump::operator delete(void *)
0x18000a013  jmp     short loc_180009FCB
0x18000a015  mov     ebp, 0FFFFFFFFh
0x18000a01a  jmp     short loc_180009FC7
0x18000a01c  mov     rax, rcx
0x18000a01f  mov     [rsp+68h+var_48], rcx
0x18000a024  cmp     [rcx+10h], rsi
0x18000a028  jz      short loc_180009FC7
0x18000a02a  mov     rax, [rax+10h]
0x18000a02e  cmp     [rax+10h], rsi
0x18000a032  jnz     short loc_18000A02A
0x18000a034  mov     [rsp+68h+var_48], rax
0x18000a039  jmp     short loc_180009FC7
0x18000a03b  mov     rcx, rbx; this
0x18000a03e  cmp     r13d, 2
0x18000a042  jnz     short loc_18000A04E
0x18000a044  call    ?WriteUnlock@CReaderWriterLock2@@QEAAXXZ; CReaderWriterLock2::WriteUnlock(void)
0x18000a049  jmp     loc_180009ECF
0x18000a04e  call    ?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000a053  jmp     loc_180009ECF
```
