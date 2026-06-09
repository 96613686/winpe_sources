# BookKeeping::RemoveItem(void *)

- ea: `0x180001940`
- end: `0x180001bf9`
- name: `?RemoveItem@BookKeeping@@SAJPEAX@Z`
- size: `697`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180001940`
- `0x180001f10`
- `0x180002370`
- `0x1800029d0`
- `0x180003840`
- `0x18000ecd8`
- `0x180019624`
- `0x18001d010`

## pseudocode

```c
__int64 __fastcall BookKeeping::RemoveItem(char *a1)
{
  LKRhash::CLKRLinearHashTable *v1; // rbp
  unsigned int v3; // ebx
  char *i; // rdi
  int j; // esi
  int v7; // eax
  char *v8; // r14
  char *v9; // rax
  __int64 v10; // r12
  bool k; // zf
  signed __int32 v12; // ecx
  LKRhash::CLKRLinearHashTable *v13; // rbx
  __int64 v14; // rax
  int v15; // eax
  signed __int32 v16; // edx
  int v17; // ebx
  char v18; // al
  char v19; // di
  unsigned int v20; // r15d
  unsigned int v21; // eax
  CReaderWriterLock2 *v22; // rbx
  signed __int32 v23; // edx

  v1 = BookKeeping::s_pItemHandleTable;
  if ( !BookKeeping::s_pItemHandleTable )
  {
    v3 = -2147221497;
    goto LABEL_5;
  }
  if ( (unsigned __int64)(a1 - 1) > 0xFFFFFFFFFFFEFFFEuLL && (unsigned __int64)(a1 + 65532) > 0xFFFA )
  {
    v3 = -2147024809;
LABEL_5:
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      WPP_SF_qd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 28, WPP_b1fef5ebbfd2305bddc8c1215ae5a760_Traceguids, a1, v3);
    return v3;
  }
  v3 = -2147319765;
  if ( *((_DWORD *)BookKeeping::s_pItemHandleTable + 5) )
    goto LABEL_5;
  v17 = (*((__int64 (**)(void))BookKeeping::s_pItemHandleTable + 5))();
  v18 = LKRhash::CLKRLinearHashTable::_ReadOrWriteLock(v1);
  v19 = v18;
  if ( *((_DWORD *)v1 + 5) )
  {
    LKRhash::CLKRLinearHashTable::_ReadOrWriteUnlock(v1, v18);
LABEL_25:
    v3 = -2147319765;
    goto LABEL_5;
  }
  v10 = 0;
  v20 = (69069 * v17 + 1) & 0xFFFF0000 | ((unsigned int)(1103515245 * v17 + 12345) >> 16);
  v21 = *((_DWORD *)v1 + 22) & v20;
  if ( v21 < *((_DWORD *)v1 + 24) )
    v21 = v20 & *((_DWORD *)v1 + 23);
  v22 = (CReaderWriterLock2 *)(((unsigned __int64)(v21 & *((_DWORD *)v1 + 19)) << 6)
                             + *(_QWORD *)(*((_QWORD *)v1 + 13) + 8 * ((unsigned __int64)v21 >> *((_DWORD *)v1 + 17))));
  if ( *((_BYTE *)v1 + 153) )
  {
    if ( (*(_DWORD *)v22 & 0xFFFF8000) != 0
      || (v23 = *(_DWORD *)v22, v23 != _InterlockedCompareExchange((volatile signed __int32 *)v22, v23 + 1, v23)) )
    {
      CReaderWriterLock2::_LockSpin(v22, 0);
    }
    if ( *((_BYTE *)v1 + 153) )
    {
      if ( v19 )
      {
        do
          v16 = *((_DWORD *)v1 + 6);
        while ( v16 != _InterlockedCompareExchange((volatile signed __int32 *)v1 + 6, v16 - 1, v16) );
      }
      else
      {
        CReaderWriterLock3::WriteUnlock((LKRhash::CLKRLinearHashTable *)((char *)v1 + 24));
      }
    }
  }
  for ( i = (char *)v22 + 8; i; i = (char *)*((_QWORD *)i + 2) )
  {
    for ( j = 0; j < 4; ++j )
    {
      v7 = *(_DWORD *)&i[4 * j];
      if ( v7 == 31678523 )
        goto LABEL_17;
      if ( v20 == v7 )
      {
        v8 = &i[8 * j];
        v9 = (char *)(*((__int64 (__fastcall **)(_QWORD))v1 + 4))(*((_QWORD *)v8 + 3));
        if ( a1 == v9 || (*((unsigned __int8 (__fastcall **)(char *, char *))v1 + 6))(a1, v9) )
        {
          v10 = *((_QWORD *)v8 + 3);
          (*((void (__fastcall **)(__int64, __int64))v1 + 7))(v10, 1);
          goto LABEL_17;
        }
      }
    }
  }
LABEL_17:
  for ( k = *((_BYTE *)v1 + 153) == 0;
        !k;
        k = v12 == _InterlockedCompareExchange((volatile signed __int32 *)v22, *(_DWORD *)v22 - 1, *(_DWORD *)v22) )
  {
    v12 = *(_DWORD *)v22;
  }
  if ( !v10 )
    goto LABEL_25;
  v13 = BookKeeping::s_pItemHandleTable;
  if ( !*((_DWORD *)BookKeeping::s_pItemHandleTable + 5) )
  {
    v14 = (*((__int64 (__fastcall **)(__int64))BookKeeping::s_pItemHandleTable + 4))(v10);
    v15 = (*((__int64 (__fastcall **)(__int64))v13 + 5))(v14);
    LKRhash::CLKRLinearHashTable::_DeleteRecord(
      (__int64)v13,
      v10,
      (69069 * v15 + 1) & 0xFFFF0000 | ((unsigned int)(1103515245 * v15 + 12345) >> 16));
  }
  return 0;
}

```

## disassembly

```asm
0x180001940  push    rbx
0x180001942  push    rbp
0x180001943  push    rdi
0x180001944  push    r12
0x180001946  push    r13
0x180001948  sub     rsp, 30h
0x18000194c  mov     rbp, cs:?s_pItemHandleTable@BookKeeping@@0PEAVItemHandleTable@@EA; ItemHandleTable * BookKeeping::s_pItemHandleTable
0x180001953  mov     r13, rcx
0x180001956  test    rbp, rbp
0x180001959  jz      loc_180001BDE
0x18000195f  lea     rax, [rcx-1]
0x180001963  cmp     rax, 0FFFFFFFFFFFEFFFEh
0x180001969  jbe     loc_180001B21
0x18000196f  lea     rax, [rcx+0FFFCh]
0x180001976  cmp     rax, 0FFFAh
0x18000197c  jbe     loc_180001B21
0x180001982  mov     ebx, 80070057h
0x180001987  mov     rcx, cs:WPP_GLOBAL_Control
0x18000198e  lea     rax, WPP_GLOBAL_Control
0x180001995  cmp     rcx, rax
0x180001998  jz      short loc_1800019BC
0x18000199a  cmp     byte ptr [rcx+19h], 2
0x18000199e  jb      short loc_1800019BC
0x1800019a0  mov     rcx, [rcx+10h]
0x1800019a4  lea     r8, WPP_b1fef5ebbfd2305bddc8c1215ae5a760_Traceguids
0x1800019ab  mov     edx, 1Ch
0x1800019b0  mov     [rsp+58h+var_38], ebx
0x1800019b4  mov     r9, r13
0x1800019b7  call    WPP_SF_qd
0x1800019bc  mov     eax, ebx
0x1800019be  jmp     loc_180001AA1
0x1800019c3  lea     rdi, [rbx+8]
0x1800019c7  test    rdi, rdi
0x1800019ca  jz      short loc_180001A1D
0x1800019cc  xor     esi, esi
0x1800019ce  cmp     esi, 4
0x1800019d1  jge     loc_180001BF0
0x1800019d7  movsxd  rcx, esi
0x1800019da  mov     eax, [rdi+rcx*4]
0x1800019dd  cmp     eax, 1E3603Bh
0x1800019e2  jz      short loc_180001A1D
0x1800019e4  cmp     r15d, eax
0x1800019e7  jnz     loc_180001ADA
0x1800019ed  mov     rax, [rbp+20h]
0x1800019f1  lea     r14, [rdi+rcx*8]
0x1800019f5  mov     rcx, [rdi+rcx*8+18h]
0x1800019fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800019ff  cmp     r13, rax
0x180001a02  jnz     loc_180001AC3
0x180001a08  mov     r12, [r14+18h]
0x180001a0c  mov     edx, 1
0x180001a11  mov     rax, [rbp+38h]
0x180001a15  mov     rcx, r12
0x180001a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a1d  mov     r15, [rsp+58h+arg_10]
0x180001a22  mov     r14, [rsp+58h+arg_8]
0x180001a27  mov     rsi, [rsp+58h+arg_0]
0x180001a2c  cmp     byte ptr [rbp+99h], 0
0x180001a33  jz      short loc_180001A44
0x180001a35  mov     ecx, [rbx]
0x180001a37  mov     eax, ecx
0x180001a39  lea     edx, [rcx-1]
0x180001a3c  lock cmpxchg [rbx], edx
0x180001a40  cmp     ecx, eax
0x180001a42  jmp     short loc_180001A33
0x180001a44  test    r12, r12
0x180001a47  jz      short loc_180001AB9
0x180001a49  mov     rbx, cs:?s_pItemHandleTable@BookKeeping@@0PEAVItemHandleTable@@EA; ItemHandleTable * BookKeeping::s_pItemHandleTable
0x180001a50  cmp     dword ptr [rbx+14h], 0
0x180001a54  jnz     short loc_180001A9F
0x180001a56  mov     rax, [rbx+20h]
0x180001a5a  mov     rcx, r12
0x180001a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a62  mov     rcx, rax
0x180001a65  mov     rax, [rbx+28h]
0x180001a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a6e  imul    r8d, eax, 41C64E6Dh
0x180001a75  mov     rdx, r12
0x180001a78  imul    r9d, eax, 10DCDh
0x180001a7f  mov     rcx, rbx
0x180001a82  add     r8d, 3039h
0x180001a89  inc     r9d
0x180001a8c  shr     r8d, 10h
0x180001a90  and     r9d, 0FFFF0000h
0x180001a97  or      r8d, r9d
0x180001a9a  call    ?_DeleteRecord@CLKRLinearHashTable@LKRhash@@AEAA?AW4LK_RETCODE@2@PEBXK@Z; LKRhash::CLKRLinearHashTable::_DeleteRecord(void const *,ulong)
0x180001a9f  xor     eax, eax
0x180001aa1  add     rsp, 30h
0x180001aa5  pop     r13
0x180001aa7  pop     r12
0x180001aa9  pop     rdi
0x180001aaa  pop     rbp
0x180001aab  pop     rbx
0x180001aac  retn
0x180001aad  movzx   edx, dil; bool
0x180001ab1  mov     rcx, rbp; this
0x180001ab4  call    ?_ReadOrWriteUnlock@CLKRLinearHashTable@LKRhash@@AEBAX_N@Z; LKRhash::CLKRLinearHashTable::_ReadOrWriteUnlock(bool)
0x180001ab9  mov     ebx, 8002802Bh
0x180001abe  jmp     loc_180001987
0x180001ac3  mov     rdx, rax
0x180001ac6  mov     rcx, r13
0x180001ac9  mov     rax, [rbp+30h]
0x180001acd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ad2  test    al, al
0x180001ad4  jnz     loc_180001A08
0x180001ada  inc     esi
0x180001adc  jmp     loc_1800019CE
0x180001ae1  xor     edx, edx; bool
0x180001ae3  mov     rcx, rbx; this
0x180001ae6  call    ?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z; CReaderWriterLock2::_LockSpin(bool)
0x180001aeb  cmp     [rbp+99h], r12b
0x180001af2  jz      loc_1800019C3
0x180001af8  test    dil, dil
0x180001afb  jz      short loc_180001B13
0x180001afd  mov     edx, [rbp+18h]
0x180001b00  mov     eax, edx
0x180001b02  lea     ecx, [rdx-1]
0x180001b05  lock cmpxchg [rbp+18h], ecx
0x180001b0a  cmp     edx, eax
0x180001b0c  jnz     short loc_180001AFD
0x180001b0e  jmp     loc_1800019C3
0x180001b13  lea     rcx, [rbp+18h]; this
0x180001b17  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180001b1c  jmp     loc_1800019C3
0x180001b21  cmp     dword ptr [rbp+14h], 0
0x180001b25  mov     ebx, 8002802Bh
0x180001b2a  jnz     loc_180001987
0x180001b30  mov     rax, [rbp+28h]
0x180001b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b39  mov     rcx, rbp; this
0x180001b3c  mov     ebx, eax
0x180001b3e  call    ?_ReadOrWriteLock@CLKRLinearHashTable@LKRhash@@AEBA_NXZ; LKRhash::CLKRLinearHashTable::_ReadOrWriteLock(void)
0x180001b43  cmp     dword ptr [rbp+14h], 0
0x180001b47  movzx   edi, al
0x180001b4a  jnz     loc_180001AAD
0x180001b50  mov     [rsp+58h+arg_0], rsi
0x180001b55  xor     r12d, r12d
0x180001b58  imul    eax, ebx, 10DCDh
0x180001b5e  mov     [rsp+58h+arg_8], r14
0x180001b63  mov     [rsp+58h+arg_10], r15
0x180001b68  imul    r15d, ebx, 41C64E6Dh
0x180001b6f  inc     eax
0x180001b71  and     eax, 0FFFF0000h
0x180001b76  add     r15d, 3039h
0x180001b7d  shr     r15d, 10h
0x180001b81  or      r15d, eax
0x180001b84  mov     eax, r15d
0x180001b87  and     eax, [rbp+58h]
0x180001b8a  cmp     eax, [rbp+60h]
0x180001b8d  jb      short loc_180001BE8
0x180001b8f  mov     ecx, [rbp+44h]
0x180001b92  mov     edx, [rbp+4Ch]
0x180001b95  and     rdx, rax
0x180001b98  mov     r8d, eax
0x180001b9b  shr     r8, cl
0x180001b9e  mov     rcx, [rbp+68h]
0x180001ba2  shl     rdx, 6
0x180001ba6  mov     rbx, [rcx+r8*8]
0x180001baa  add     rbx, rdx
0x180001bad  cmp     [rbp+99h], r12b
0x180001bb4  jz      loc_1800019C3
0x180001bba  mov     edx, [rbx]
0x180001bbc  test    edx, 0FFFF8000h
0x180001bc2  jnz     loc_180001AE1
0x180001bc8  lea     ecx, [rdx+1]
0x180001bcb  mov     eax, edx
0x180001bcd  lock cmpxchg [rbx], ecx
0x180001bd1  cmp     edx, eax
0x180001bd3  jz      loc_180001AEB
0x180001bd9  jmp     loc_180001AE1
0x180001bde  mov     ebx, 80040007h
0x180001be3  jmp     loc_180001987
0x180001be8  mov     eax, [rbp+5Ch]
0x180001beb  and     eax, r15d
0x180001bee  jmp     short loc_180001B8F
0x180001bf0  mov     rdi, [rdi+10h]
0x180001bf4  jmp     loc_1800019C7
```
