# _std::list_Command_std::allocator_Command___::list_Command_std::allocator_Command____::_1_::catch$2

- ea: `0x18000d3ea`
- end: `0x18000d40a`
- name: `_std::list_Command_std::allocator_Command___::list_Command_std::allocator_Command____::_1_::catch$2`
- size: `32`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007d24`
- `0x18000c4b0`

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
0x18000d3ea  mov     [rsp+arg_8], rdx
0x18000d3ef  push    rbp
0x18000d3f0  sub     rsp, 30h
0x18000d3f4  mov     rbp, rdx
0x18000d3f7  mov     rcx, [rbp+40h]
0x18000d3fb  call    ?clear@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXXZ; std::list<Command>::clear(void)
0x18000d400  xor     edx, edx; pThrowInfo
0x18000d402  xor     ecx, ecx; pExceptionObject
0x18000d404  call    _CxxThrowException_0
```
