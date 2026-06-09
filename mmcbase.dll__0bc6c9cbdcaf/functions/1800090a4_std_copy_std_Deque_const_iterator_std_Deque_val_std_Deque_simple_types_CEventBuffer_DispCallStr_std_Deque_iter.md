# std::copy<std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>>(std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>,std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>)

- ea: `0x1800090a4`
- end: `0x18000917a`
- name: `??$copy@V?$_Deque_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@UDispCallStr@CEventBuffer@@@std@@@std@@@std@@V?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@UDispCallStr@CEventBuffer@@@std@@@std@@@2@@std@@YA?AV?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@UDispCallStr@CEventBuffer@@@std@@@std@@@0@V?$_Deque_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@UDispCallStr@CEventBuffer@@@std@@@std@@@0@0V10@@Z`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180013a1c`

## callees

- `0x1800090a4`
- `0x1800092d0`
- `0x18000940c`

## pseudocode

```c
__int64 __fastcall std::copy<std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v8; // rbx
  __int64 v9; // r13
  __int64 v10; // rax
  __int64 v11; // rdi
  __int64 v12; // r14
  __int64 v13; // rax
  _QWORD *v14; // rcx
  __int64 v15; // rax
  __int128 v17; // [rsp+30h] [rbp-69h] BYREF
  __int64 v18; // [rsp+40h] [rbp-59h]
  _QWORD v19[2]; // [rsp+50h] [rbp-49h] BYREF
  _QWORD v20[2]; // [rsp+60h] [rbp-39h] BYREF
  _QWORD v21[2]; // [rsp+70h] [rbp-29h] BYREF
  _BYTE v22[24]; // [rsp+80h] [rbp-19h] BYREF
  _BYTE v23[88]; // [rsp+98h] [rbp-1h] BYREF

  std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>(
    &v17,
    a4);
  if ( (_QWORD)v17 )
    v8 = *(_QWORD *)v17;
  else
    v8 = 0;
  v9 = v18;
  v10 = std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>(
          v22,
          a3);
  if ( *(_QWORD *)v10 )
    v11 = **(_QWORD **)v10;
  else
    v11 = 0;
  v12 = *(_QWORD *)(v10 + 16);
  v13 = std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>(
          v23,
          a2);
  v14 = *(_QWORD **)v13;
  if ( *(_QWORD *)v13 )
    v14 = (_QWORD *)*v14;
  v15 = *(_QWORD *)(v13 + 16);
  v21[0] = v14;
  v21[1] = v15;
  v19[0] = v8;
  v19[1] = v9;
  v20[0] = v11;
  v20[1] = v12;
  std::_Copy_impl<std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>,std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>>(
    &v17,
    v21,
    (__int64)v20,
    v19);
  *(_QWORD *)(a4 + 16) = *((_QWORD *)&v17 + 1);
  std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>(
    a1,
    a4);
  return a1;
}

```

## disassembly

```asm
0x1800090a4  push    rbp
0x1800090a6  push    rbx
0x1800090a7  push    rsi
0x1800090a8  push    rdi
0x1800090a9  push    r12
0x1800090ab  push    r13
0x1800090ad  push    r14
0x1800090af  push    r15
0x1800090b1  lea     rbp, [rsp-1Fh]
0x1800090b6  sub     rsp, 0B8h
0x1800090bd  mov     r15, rdx
0x1800090c0  mov     r12, rcx
0x1800090c3  mov     rdx, r9
0x1800090c6  lea     rcx, [rbp+57h+var_C0]
0x1800090ca  mov     rsi, r9
0x1800090cd  mov     rdi, r8
0x1800090d0  call    ??0?$_Deque_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@UDispCallStr@CEventBuffer@@@std@@@std@@@std@@QEAA@$$QEAV01@@Z; std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>(std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>> &&)
0x1800090d5  mov     rax, [rbp+57h+var_C0]
0x1800090d9  test    rax, rax
0x1800090dc  jnz     short loc_1800090E2
0x1800090de  xor     ebx, ebx
0x1800090e0  jmp     short loc_1800090E5
0x1800090e2  mov     rbx, [rax]
0x1800090e5  mov     r13, [rbp+57h+var_B0]
0x1800090e9  lea     rcx, [rbp+57h+var_70]
0x1800090ed  mov     rdx, rdi
0x1800090f0  call    ??0?$_Deque_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@UDispCallStr@CEventBuffer@@@std@@@std@@@std@@QEAA@$$QEAV01@@Z; std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>(std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>> &&)
0x1800090f5  mov     rcx, [rax]
0x1800090f8  test    rcx, rcx
0x1800090fb  jnz     short loc_180009101
0x1800090fd  xor     edi, edi
0x1800090ff  jmp     short loc_180009104
0x180009101  mov     rdi, [rcx]
0x180009104  mov     r14, [rax+10h]
0x180009108  lea     rcx, [rbp+57h+var_58]
0x18000910c  mov     rdx, r15
0x18000910f  call    ??0?$_Deque_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@UDispCallStr@CEventBuffer@@@std@@@std@@@std@@QEAA@$$QEAV01@@Z; std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>(std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>> &&)
0x180009114  mov     rcx, [rax]
0x180009117  test    rcx, rcx
0x18000911a  jz      short loc_18000911F
0x18000911c  mov     rcx, [rcx]
0x18000911f  mov     rax, [rax+10h]
0x180009123  lea     r9, [rbp+57h+var_A0]
0x180009127  mov     [rbp+57h+var_80], rcx
0x18000912b  lea     r8, [rbp+57h+var_90]
0x18000912f  lea     rcx, [rbp+57h+var_C0]
0x180009133  mov     [rbp+57h+var_78], rax
0x180009137  lea     rdx, [rbp+57h+var_80]
0x18000913b  mov     [rbp+57h+var_A0], rbx
0x18000913f  mov     [rbp+57h+var_98], r13
0x180009143  mov     [rbp+57h+var_90], rdi
0x180009147  mov     [rbp+57h+var_88], r14
0x18000914b  call    ??$_Copy_impl@V?$_Deque_unchecked_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@UDispCallStr@CEventBuffer@@@std@@@std@@@std@@V?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@UDispCallStr@CEventBuffer@@@std@@@std@@@2@@std@@YA?AV?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@UDispCallStr@CEventBuffer@@@std@@@std@@@0@V?$_Deque_unchecked_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@UDispCallStr@CEventBuffer@@@std@@@std@@@0@0V10@U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Copy_impl<std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>,std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>>(std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>,std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>,std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>,std::_Nonscalar_ptr_iterator_tag)
0x180009150  mov     rax, [rbp+57h+var_B8]
0x180009154  mov     rdx, rsi
0x180009157  mov     rcx, r12
0x18000915a  mov     [rsi+10h], rax
0x18000915e  call    ??0?$_Deque_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@UDispCallStr@CEventBuffer@@@std@@@std@@@std@@QEAA@$$QEAV01@@Z; std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>(std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>> &&)
0x180009163  mov     rax, r12
0x180009166  add     rsp, 0B8h
0x18000916d  pop     r15
0x18000916f  pop     r14
0x180009171  pop     r13
0x180009173  pop     r12
0x180009175  pop     rdi
0x180009176  pop     rsi
0x180009177  pop     rbx
0x180009178  pop     rbp
0x180009179  retn
```
