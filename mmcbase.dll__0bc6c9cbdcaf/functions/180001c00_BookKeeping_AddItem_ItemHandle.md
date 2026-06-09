# BookKeeping::AddItem(ItemHandle &)

- ea: `0x180001c00`
- end: `0x180001f0a`
- name: `?AddItem@BookKeeping@@SAJAEAVItemHandle@@@Z`
- size: `778`
- prototype: `__int64 __fastcall(struct ItemHandle *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180001c00`
- `0x180001f10`
- `0x180001f90`
- `0x1800022f0`
- `0x180002370`
- `0x1800026c0`
- `0x180003840`
- `0x180008630`
- `0x180019624`
- `0x18001984c`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001c3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001c3d`

## pseudocode

```c
__int64 __fastcall BookKeeping::AddItem(struct ItemHandle *a1)
{
  int inited; // ebx
  unsigned __int32 v3; // eax
  __int64 v4; // rsi
  LKRhash::CLKRLinearHashTable *v5; // rbp
  int v6; // ebx
  char v7; // al
  char v8; // di
  LKRhash::CLKRLinearHashTable *v9; // rbx
  int inserted; // eax
  __int64 result; // rax
  char *i; // rdi
  int j; // esi
  int v14; // eax
  char *v15; // r14
  __int64 v16; // rax
  __int64 v17; // r12
  bool k; // zf
  signed __int32 v19; // ecx
  signed __int32 v20; // edx
  unsigned int v21; // r15d
  unsigned int v22; // eax
  CReaderWriterLock2 *v23; // rbx
  signed __int32 v24; // edx
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // [rsp+68h] [rbp+10h]

  inited = BookKeeping::InitInstance();
  if ( inited < 0 )
    goto LABEL_42;
  if ( dword_18002F918
    || _InterlockedCompareExchange((volatile signed __int32 *)&dword_18002F918, GetCurrentThreadId(), 0) )
  {
    CSmallSpinLock::_LockSpin((CSmallSpinLock *)&dword_18002F918);
  }
  while ( 1 )
  {
    do
    {
      v3 = 314159269 * _InterlockedIncrement(&dword_18002C2FC);
      v4 = v3;
      v27 = v3;
    }
    while ( !v3 );
    v5 = BookKeeping::s_pItemHandleTable;
    if ( *((_DWORD *)BookKeeping::s_pItemHandleTable + 5) )
      break;
    v6 = (*((__int64 (__fastcall **)(_QWORD))BookKeeping::s_pItemHandleTable + 5))(v3);
    v7 = LKRhash::CLKRLinearHashTable::_ReadOrWriteLock(v5);
    v8 = v7;
    if ( *((_DWORD *)v5 + 5) )
    {
      LKRhash::CLKRLinearHashTable::_ReadOrWriteUnlock(v5, v7);
      break;
    }
    v17 = 0;
    v21 = (69069 * v6 + 1) & 0xFFFF0000 | ((unsigned int)(1103515245 * v6 + 12345) >> 16);
    v22 = *((_DWORD *)v5 + 22) & v21;
    if ( v22 < *((_DWORD *)v5 + 24) )
      v22 = v21 & *((_DWORD *)v5 + 23);
    v23 = (CReaderWriterLock2 *)(*(_QWORD *)(*((_QWORD *)v5 + 13) + 8 * ((unsigned __int64)v22 >> *((_DWORD *)v5 + 17)))
                               + ((unsigned __int64)(v22 & *((_DWORD *)v5 + 19)) << 6));
    if ( *((_BYTE *)v5 + 153) )
    {
      if ( (*(_DWORD *)v23 & 0xFFFF8000) != 0
        || (v24 = *(_DWORD *)v23, v24 != _InterlockedCompareExchange((volatile signed __int32 *)v23, v24 + 1, v24)) )
      {
        CReaderWriterLock2::_LockSpin(v23, 0);
      }
      if ( *((_BYTE *)v5 + 153) )
      {
        if ( v8 )
        {
          do
            v20 = *((_DWORD *)v5 + 6);
          while ( v20 != _InterlockedCompareExchange((volatile signed __int32 *)v5 + 6, v20 - 1, v20) );
        }
        else
        {
          CReaderWriterLock3::WriteUnlock((LKRhash::CLKRLinearHashTable *)((char *)v5 + 24));
        }
      }
    }
    for ( i = (char *)v23 + 8; i; i = (char *)*((_QWORD *)i + 2) )
    {
      for ( j = 0; j < 4; ++j )
      {
        v14 = *(_DWORD *)&i[4 * j];
        if ( v14 == 31678523 )
          goto LABEL_21;
        if ( v21 == v14 )
        {
          v15 = &i[8 * j];
          v16 = (*((__int64 (__fastcall **)(_QWORD))v5 + 4))(*((_QWORD *)v15 + 3));
          if ( v27 == v16 || (*((unsigned __int8 (__fastcall **)(__int64, __int64))v5 + 6))(v27, v16) )
          {
            v17 = *((_QWORD *)v15 + 3);
            (*((void (__fastcall **)(__int64, __int64))v5 + 7))(v17, 1);
            goto LABEL_21;
          }
        }
      }
    }
LABEL_21:
    for ( k = *((_BYTE *)v5 + 153) == 0;
          !k;
          k = v19 == _InterlockedCompareExchange((volatile signed __int32 *)v23, *(_DWORD *)v23 - 1, *(_DWORD *)v23) )
    {
      v19 = *(_DWORD *)v23;
    }
    if ( !v17 )
    {
      v4 = v27;
      break;
    }
  }
  _InterlockedExchange((volatile __int32 *)&dword_18002F918, 0);
  v9 = BookKeeping::s_pItemHandleTable;
  *((_QWORD *)a1 + 2) = v4;
  inserted = *((_DWORD *)v9 + 5);
  if ( !inserted )
  {
    v25 = (*((__int64 (__fastcall **)(struct ItemHandle *))v9 + 4))(a1);
    v26 = (*((__int64 (__fastcall **)(__int64))v9 + 5))(v25);
    inserted = LKRhash::CLKRLinearHashTable::_InsertRecord(
                 (__int64)v9,
                 (__int64)a1,
                 (69069 * v26 + 1) & 0xFFFF0000 | ((unsigned int)(1103515245 * v26 + 12345) >> 16));
  }
  result = BookKeeping::LKResult2HRESULT(inserted);
  inited = result;
  if ( (int)result < 0 )
  {
    *((_QWORD *)a1 + 2) = 0;
LABEL_42:
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        27,
        WPP_b1fef5ebbfd2305bddc8c1215ae5a760_Traceguids,
        (unsigned int)inited);
    return (unsigned int)inited;
  }
  return result;
}

```

## disassembly

```asm
0x180001c00  push    rbx
0x180001c02  push    r13
0x180001c04  sub     rsp, 48h
0x180001c08  mov     r13, rcx
0x180001c0b  call    ?InitInstance@BookKeeping@@SAJXZ; BookKeeping::InitInstance(void)
0x180001c10  mov     ebx, eax
0x180001c12  test    eax, eax
0x180001c14  js      loc_180001ED2
0x180001c1a  mov     eax, cs:dword_18002F918
0x180001c20  mov     [rsp+58h+arg_0], rbp
0x180001c25  mov     [rsp+58h+arg_10], rsi
0x180001c2a  mov     [rsp+58h+arg_18], rdi
0x180001c2f  mov     [rsp+58h+var_20], r14
0x180001c34  mov     [rsp+58h+var_28], r15
0x180001c39  test    eax, eax
0x180001c3b  jnz     short loc_180001C51
0x180001c3d  call    cs:__imp_GetCurrentThreadId
0x180001c43  mov     edx, eax
0x180001c45  xor     eax, eax
0x180001c47  lock cmpxchg cs:dword_18002F918, edx
0x180001c4f  jz      short loc_180001C5D
0x180001c51  lea     rcx, dword_18002F918; this
0x180001c58  call    ?_LockSpin@CSmallSpinLock@@AEAAXXZ; CSmallSpinLock::_LockSpin(void)
0x180001c5d  mov     [rsp+58h+var_18], r12
0x180001c62  mov     eax, 1
0x180001c67  lock xadd cs:dword_18002C2FC, eax
0x180001c6f  inc     eax
0x180001c71  imul    eax, 12B9B0A5h
0x180001c77  mov     esi, eax
0x180001c79  mov     [rsp+58h+arg_8], rsi
0x180001c7e  test    eax, eax
0x180001c80  jz      short loc_180001C62
0x180001c82  mov     rbp, cs:?s_pItemHandleTable@BookKeeping@@0PEAVItemHandleTable@@EA; ItemHandleTable * BookKeeping::s_pItemHandleTable
0x180001c89  cmp     dword ptr [rbp+14h], 0
0x180001c8d  jnz     short loc_180001CBC
0x180001c8f  mov     rax, [rbp+28h]
0x180001c93  mov     ecx, esi
0x180001c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c9a  mov     rcx, rbp; this
0x180001c9d  mov     ebx, eax
0x180001c9f  call    ?_ReadOrWriteLock@CLKRLinearHashTable@LKRhash@@AEBA_NXZ; LKRhash::CLKRLinearHashTable::_ReadOrWriteLock(void)
0x180001ca4  cmp     dword ptr [rbp+14h], 0
0x180001ca8  movzx   edi, al
0x180001cab  jz      loc_180001DEB
0x180001cb1  movzx   edx, al; bool
0x180001cb4  mov     rcx, rbp; this
0x180001cb7  call    ?_ReadOrWriteUnlock@CLKRLinearHashTable@LKRhash@@AEBAX_N@Z; LKRhash::CLKRLinearHashTable::_ReadOrWriteUnlock(bool)
0x180001cbc  mov     r15, [rsp+58h+var_28]
0x180001cc1  xor     eax, eax
0x180001cc3  xchg    eax, cs:dword_18002F918
0x180001cc9  mov     rbx, cs:?s_pItemHandleTable@BookKeeping@@0PEAVItemHandleTable@@EA; ItemHandleTable * BookKeeping::s_pItemHandleTable
0x180001cd0  mov     r14, [rsp+58h+var_20]
0x180001cd5  mov     r12, [rsp+58h+var_18]
0x180001cda  mov     rdi, [rsp+58h+arg_18]
0x180001cdf  mov     rbp, [rsp+58h+arg_0]
0x180001ce4  mov     [r13+10h], rsi
0x180001ce8  mov     eax, [rbx+14h]
0x180001ceb  mov     rsi, [rsp+58h+arg_10]
0x180001cf0  test    eax, eax
0x180001cf2  jz      loc_180001E6B
0x180001cf8  movsxd  rcx, eax; __int64
0x180001cfb  call    ?LKResult2HRESULT@BookKeeping@@SAJ_J@Z; BookKeeping::LKResult2HRESULT(__int64)
0x180001d00  mov     ebx, eax
0x180001d02  test    eax, eax
0x180001d04  js      loc_180001ECA
0x180001d0a  add     rsp, 48h
0x180001d0e  pop     r13
0x180001d10  pop     rbx
0x180001d11  retn
0x180001d12  lea     rdi, [rbx+8]
0x180001d16  test    rdi, rdi
0x180001d19  jz      short loc_180001D69
0x180001d1b  xor     esi, esi
0x180001d1d  cmp     esi, 4
0x180001d20  jge     loc_180001EC1
0x180001d26  movsxd  rcx, esi
0x180001d29  mov     eax, [rdi+rcx*4]
0x180001d2c  cmp     eax, 1E3603Bh
0x180001d31  jz      short loc_180001D69
0x180001d33  cmp     r15d, eax
0x180001d36  jnz     short loc_180001DA4
0x180001d38  mov     rax, [rbp+20h]
0x180001d3c  lea     r14, [rdi+rcx*8]
0x180001d40  mov     rcx, [rdi+rcx*8+18h]
0x180001d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d4a  mov     rcx, [rsp+58h+arg_8]
0x180001d4f  cmp     rcx, rax
0x180001d52  jnz     short loc_180001D94
0x180001d54  mov     r12, [r14+18h]
0x180001d58  mov     edx, 1
0x180001d5d  mov     rax, [rbp+38h]
0x180001d61  mov     rcx, r12
0x180001d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d69  cmp     byte ptr [rbp+99h], 0
0x180001d70  jz      short loc_180001D81
0x180001d72  mov     ecx, [rbx]
0x180001d74  mov     eax, ecx
0x180001d76  lea     edx, [rcx-1]
0x180001d79  lock cmpxchg [rbx], edx
0x180001d7d  cmp     ecx, eax
0x180001d7f  jmp     short loc_180001D70
0x180001d81  test    r12, r12
0x180001d84  jnz     loc_180001C62
0x180001d8a  mov     rsi, [rsp+58h+arg_8]
0x180001d8f  jmp     loc_180001CBC
0x180001d94  mov     rdx, rax
0x180001d97  mov     rax, [rbp+30h]
0x180001d9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001da0  test    al, al
0x180001da2  jnz     short loc_180001D54
0x180001da4  inc     esi
0x180001da6  jmp     loc_180001D1D
0x180001dab  xor     edx, edx; bool
0x180001dad  mov     rcx, rbx; this
0x180001db0  call    ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x180001db5  cmp     [rbp+99h], r12b
0x180001dbc  jz      loc_180001D12
0x180001dc2  test    dil, dil
0x180001dc5  jz      short loc_180001DDD
0x180001dc7  mov     edx, [rbp+18h]
0x180001dca  mov     eax, edx
0x180001dcc  lea     ecx, [rdx-1]
0x180001dcf  lock cmpxchg [rbp+18h], ecx
0x180001dd4  cmp     edx, eax
0x180001dd6  jnz     short loc_180001DC7
0x180001dd8  jmp     loc_180001D12
0x180001ddd  lea     rcx, [rbp+18h]; this
0x180001de1  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180001de6  jmp     loc_180001D12
0x180001deb  imul    r15d, ebx, 41C64E6Dh
0x180001df2  xor     r12d, r12d
0x180001df5  imul    ecx, ebx, 10DCDh
0x180001dfb  add     r15d, 3039h
0x180001e02  inc     ecx
0x180001e04  shr     r15d, 10h
0x180001e08  and     ecx, 0FFFF0000h
0x180001e0e  or      r15d, ecx
0x180001e11  mov     eax, r15d
0x180001e14  and     eax, [rbp+58h]
0x180001e17  cmp     eax, [rbp+60h]
0x180001e1a  jb      loc_180001EB6
0x180001e20  mov     ecx, [rbp+44h]
0x180001e23  mov     ebx, [rbp+4Ch]
0x180001e26  and     rbx, rax
0x180001e29  mov     edx, eax
0x180001e2b  shr     rdx, cl
0x180001e2e  mov     rcx, [rbp+68h]
0x180001e32  shl     rbx, 6
0x180001e36  add     rbx, [rcx+rdx*8]
0x180001e3a  cmp     [rbp+99h], r12b
0x180001e41  jz      loc_180001D12
0x180001e47  mov     edx, [rbx]
0x180001e49  test    edx, 0FFFF8000h
0x180001e4f  jnz     loc_180001DAB
0x180001e55  lea     ecx, [rdx+1]
0x180001e58  mov     eax, edx
0x180001e5a  lock cmpxchg [rbx], ecx
0x180001e5e  cmp     edx, eax
0x180001e60  jz      loc_180001DB5
0x180001e66  jmp     loc_180001DAB
0x180001e6b  mov     rax, [rbx+20h]
0x180001e6f  mov     rcx, r13
0x180001e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e77  mov     rcx, rax
0x180001e7a  mov     rax, [rbx+28h]
0x180001e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e83  imul    edx, eax, 10DCDh
0x180001e89  mov     rcx, rbx
0x180001e8c  imul    r8d, eax, 41C64E6Dh
0x180001e93  inc     edx
0x180001e95  add     r8d, 3039h
0x180001e9c  and     edx, 0FFFF0000h
0x180001ea2  shr     r8d, 10h
0x180001ea6  or      r8d, edx
0x180001ea9  mov     rdx, r13
0x180001eac  call    ?_InsertRecord@CLKRLinearHashTable@LKRhash@@AEAA?AW4LK_RETCODE@2@PEBXK_NPEAPEBXPEAVCLKRLinearHashTable_Iterator@2@@Z; LKRhash::CLKRLinearHashTable::_InsertRecord(void const *,ulong,bool,void const * *,LKRhash::CLKRLinearHashTable_Iterator *)
0x180001eb1  jmp     loc_180001CF8
0x180001eb6  mov     eax, [rbp+5Ch]
0x180001eb9  and     eax, r15d
0x180001ebc  jmp     loc_180001E20
0x180001ec1  mov     rdi, [rdi+10h]
0x180001ec5  jmp     loc_180001D16
0x180001eca  mov     qword ptr [r13+10h], 0
0x180001ed2  mov     rcx, cs:WPP_GLOBAL_Control
0x180001ed9  lea     rax, WPP_GLOBAL_Control
0x180001ee0  cmp     rcx, rax
0x180001ee3  jz      short loc_180001F03
0x180001ee5  cmp     byte ptr [rcx+19h], 2
0x180001ee9  jb      short loc_180001F03
0x180001eeb  mov     rcx, [rcx+10h]
0x180001eef  lea     r8, WPP_b1fef5ebbfd2305bddc8c1215ae5a760_Traceguids
0x180001ef6  mov     edx, 1Bh
0x180001efb  mov     r9d, ebx
0x180001efe  call    WPP_SF_d
0x180001f03  mov     eax, ebx
0x180001f05  jmp     loc_180001D0A
```
