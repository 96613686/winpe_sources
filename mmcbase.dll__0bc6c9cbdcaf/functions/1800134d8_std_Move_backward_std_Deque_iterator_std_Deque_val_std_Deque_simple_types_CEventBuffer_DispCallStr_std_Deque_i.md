# std::_Move_backward<std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>>(std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>)

- ea: `0x1800134d8`
- end: `0x18001357b`
- name: `??$_Move_backward@V?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@UDispCallStr@CEventBuffer@@@std@@@std@@@std@@V12@@std@@YA?AV?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@UDispCallStr@CEventBuffer@@@std@@@std@@@0@V10@00@Z`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180014040`

## callees

- `0x1800052b4`
- `0x1800092d0`
- `0x1800134d8`
- `0x180013d80`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Move_backward<std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v7; // rax
  __int64 v8; // r8
  _BYTE v10[16]; // [rsp+30h] [rbp-19h] BYREF
  __int64 v11; // [rsp+40h] [rbp-9h]
  _BYTE v12[16]; // [rsp+48h] [rbp-1h] BYREF
  __int64 v13; // [rsp+58h] [rbp+Fh]
  _BYTE v14[16]; // [rsp+60h] [rbp+17h] BYREF
  __int64 v15; // [rsp+70h] [rbp+27h]

  std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>(
    v10,
    a4);
  std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>(
    v12,
    a3);
  std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>(
    v14,
    a2);
  while ( v15 != v13 )
  {
    --v13;
    std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>::operator*(v12);
    --v11;
    v7 = std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>::operator*(v10);
    CEventBuffer::DispCallStr::operator=(v7, v8);
  }
  std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>(
    a1,
    v10);
  return a1;
}

```

## disassembly

```asm
0x1800134d8  push    rbp
0x1800134da  push    rbx
0x1800134db  push    rsi
0x1800134dc  push    rdi
0x1800134dd  lea     rbp, [rsp-3Fh]
0x1800134e2  sub     rsp, 88h
0x1800134e9  mov     rbx, r8
0x1800134ec  mov     rdi, rdx
0x1800134ef  mov     rsi, rcx
0x1800134f2  lea     rax, [rbp+57h+var_70]
0x1800134f6  mov     [rbp+57h+arg_0], rax
0x1800134fa  mov     rdx, r9
0x1800134fd  lea     rcx, [rbp+57h+var_70]
0x180013501  call    ??0?$_Deque_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@UDispCallStr@CEventBuffer@@@std@@@std@@@std@@QEAA@$$QEAV01@@Z; std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>(std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>> &&)
0x180013506  nop
0x180013507  lea     rax, [rbp+57h+var_58]
0x18001350b  mov     [rbp+57h+var_80], rax
0x18001350f  mov     rdx, rbx
0x180013512  lea     rcx, [rbp+57h+var_58]
0x180013516  call    ??0?$_Deque_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@UDispCallStr@CEventBuffer@@@std@@@std@@@std@@QEAA@$$QEAV01@@Z; std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>(std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>> &&)
0x18001351b  nop
0x18001351c  mov     rdx, rdi
0x18001351f  lea     rcx, [rbp+57h+var_40]
0x180013523  call    ??0?$_Deque_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@UDispCallStr@CEventBuffer@@@std@@@std@@@std@@QEAA@$$QEAV01@@Z; std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>(std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>> &&)
0x180013528  nop
0x180013529  mov     rax, [rbp+57h+var_48]
0x18001352d  cmp     [rbp+57h+var_30], rax
0x180013531  jz      short loc_180013560
0x180013533  dec     rax
0x180013536  mov     [rbp+57h+var_48], rax
0x18001353a  lea     rcx, [rbp+57h+var_58]
0x18001353e  call    ??D?$_Deque_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@UDispCallStr@CEventBuffer@@@std@@@std@@@std@@QEBAAEBUDispCallStr@CEventBuffer@@XZ; std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>::operator*(void)
0x180013543  mov     r8, rax
0x180013546  dec     [rbp+57h+var_60]
0x18001354a  lea     rcx, [rbp+57h+var_70]
0x18001354e  call    ??D?$_Deque_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@UDispCallStr@CEventBuffer@@@std@@@std@@@std@@QEBAAEBUDispCallStr@CEventBuffer@@XZ; std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>::operator*(void)
0x180013553  mov     rdx, r8
0x180013556  mov     rcx, rax
0x180013559  call    ??4DispCallStr@CEventBuffer@@QEAAAEAU01@$$QEAU01@@Z; CEventBuffer::DispCallStr::operator=(CEventBuffer::DispCallStr &&)
0x18001355e  jmp     short loc_180013529
0x180013560  lea     rdx, [rbp+57h+var_70]
0x180013564  mov     rcx, rsi
0x180013567  call    ??0?$_Deque_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@UDispCallStr@CEventBuffer@@@std@@@std@@@std@@QEAA@$$QEAV01@@Z; std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>(std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>> &&)
0x18001356c  mov     rax, rsi
0x18001356f  add     rsp, 88h
0x180013576  pop     rdi
0x180013577  pop     rsi
0x180013578  pop     rbx
0x180013579  pop     rbp
0x18001357a  retn
```
