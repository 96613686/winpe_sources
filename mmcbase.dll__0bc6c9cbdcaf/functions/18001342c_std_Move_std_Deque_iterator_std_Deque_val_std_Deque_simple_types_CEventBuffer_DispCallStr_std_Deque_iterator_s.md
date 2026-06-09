# std::_Move<std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>>(std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>)

- ea: `0x18001342c`
- end: `0x1800134cf`
- name: `??$_Move@V?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@UDispCallStr@CEventBuffer@@@std@@@std@@@std@@V12@@std@@YA?AV?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@UDispCallStr@CEventBuffer@@@std@@@std@@@0@V10@00@Z`
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
- `0x18001342c`
- `0x180013d80`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Move<std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 i; // rbx
  __int64 v8; // rax
  __int64 v9; // r8
  _BYTE v11[16]; // [rsp+30h] [rbp-19h] BYREF
  __int64 v12; // [rsp+40h] [rbp-9h]
  _BYTE v13[16]; // [rsp+48h] [rbp-1h] BYREF
  __int64 v14; // [rsp+58h] [rbp+Fh]
  _BYTE v15[16]; // [rsp+60h] [rbp+17h] BYREF
  __int64 v16; // [rsp+70h] [rbp+27h]

  std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>(
    v11,
    a4);
  std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>(
    v15,
    a3);
  std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>(
    v13,
    a2);
  for ( i = v14; i != v16; v14 = i )
  {
    std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>::operator*(v11);
    v8 = std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>::operator*(v13);
    CEventBuffer::DispCallStr::operator=(v9, v8);
    ++v12;
    ++i;
  }
  std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>(
    a1,
    v11);
  return a1;
}

```

## disassembly

```asm
0x18001342c  push    rbp
0x18001342e  push    rbx
0x18001342f  push    rsi
0x180013430  push    rdi
0x180013431  lea     rbp, [rsp-3Fh]
0x180013436  sub     rsp, 88h
0x18001343d  mov     rbx, r8
0x180013440  mov     rdi, rdx
0x180013443  mov     rsi, rcx
0x180013446  lea     rax, [rbp+57h+var_70]
0x18001344a  mov     [rbp+57h+arg_0], rax
0x18001344e  mov     rdx, r9
0x180013451  lea     rcx, [rbp+57h+var_70]
0x180013455  call    ??0?$_Deque_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@UDispCallStr@CEventBuffer@@@std@@@std@@@std@@QEAA@$$QEAV01@@Z; std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>(std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>> &&)
0x18001345a  nop
0x18001345b  lea     rax, [rbp+57h+var_40]
0x18001345f  mov     [rbp+57h+var_80], rax
0x180013463  mov     rdx, rbx
0x180013466  lea     rcx, [rbp+57h+var_40]
0x18001346a  call    ??0?$_Deque_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@UDispCallStr@CEventBuffer@@@std@@@std@@@std@@QEAA@$$QEAV01@@Z; std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>(std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>> &&)
0x18001346f  nop
0x180013470  mov     rdx, rdi
0x180013473  lea     rcx, [rbp+57h+var_58]
0x180013477  call    ??0?$_Deque_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@UDispCallStr@CEventBuffer@@@std@@@std@@@std@@QEAA@$$QEAV01@@Z; std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>(std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>> &&)
0x18001347c  nop
0x18001347d  mov     rbx, [rbp+57h+var_48]
0x180013481  cmp     rbx, [rbp+57h+var_30]
0x180013485  jz      short loc_1800134B4
0x180013487  lea     rcx, [rbp+57h+var_70]
0x18001348b  call    ??D?$_Deque_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@UDispCallStr@CEventBuffer@@@std@@@std@@@std@@QEBAAEBUDispCallStr@CEventBuffer@@XZ; std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>::operator*(void)
0x180013490  mov     r8, rax
0x180013493  lea     rcx, [rbp+57h+var_58]
0x180013497  call    ??D?$_Deque_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@UDispCallStr@CEventBuffer@@@std@@@std@@@std@@QEBAAEBUDispCallStr@CEventBuffer@@XZ; std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>::operator*(void)
0x18001349c  mov     rdx, rax
0x18001349f  mov     rcx, r8
0x1800134a2  call    ??4DispCallStr@CEventBuffer@@QEAAAEAU01@$$QEAU01@@Z; CEventBuffer::DispCallStr::operator=(CEventBuffer::DispCallStr &&)
0x1800134a7  inc     [rbp+57h+var_60]
0x1800134ab  inc     rbx
0x1800134ae  mov     [rbp+57h+var_48], rbx
0x1800134b2  jmp     short loc_180013481
0x1800134b4  lea     rdx, [rbp+57h+var_70]
0x1800134b8  mov     rcx, rsi
0x1800134bb  call    ??0?$_Deque_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@UDispCallStr@CEventBuffer@@@std@@@std@@@std@@QEAA@$$QEAV01@@Z; std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>(std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>> &&)
0x1800134c0  mov     rax, rsi
0x1800134c3  add     rsp, 88h
0x1800134ca  pop     rdi
0x1800134cb  pop     rsi
0x1800134cc  pop     rbx
0x1800134cd  pop     rbp
0x1800134ce  retn
```
