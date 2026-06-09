# _std::list_Command_std::allocator_Command___::list_Command_std::allocator_Command____::_1_::catch$2

- ea: `0x18000dab6`
- end: `0x18000dad6`
- name: `_std::list_Command_std::allocator_Command___::list_Command_std::allocator_Command____::_1_::catch$2`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800080bc`
- `0x18000cb69`

## pseudocode

```c
void __fastcall __noreturn std::list_Command_std::allocator_Command___::list_Command_std::allocator_Command____::_1_::catch_2(
        __int64 a1,
        __int64 a2)
{
  std::list<Command>::clear(*(_QWORD *)(a2 + 64));
  throw;
}

```

## disassembly

```asm
0x18000dab6  mov     [rsp+arg_8], rdx
0x18000dabb  push    rbp
0x18000dabc  sub     rsp, 30h
0x18000dac0  mov     rbp, rdx
0x18000dac3  mov     rcx, [rbp+40h]
0x18000dac7  call    ?clear@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXXZ; std::list<Command>::clear(void)
0x18000dacc  xor     edx, edx; pThrowInfo
0x18000dace  xor     ecx, ecx; pExceptionObject
0x18000dad0  call    _CxxThrowException_0
```
