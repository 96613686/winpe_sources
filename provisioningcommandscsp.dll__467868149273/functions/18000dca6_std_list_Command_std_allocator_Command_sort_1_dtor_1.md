# _std::list_Command_std::allocator_Command___::sort_::_1_::dtor$1

- ea: `0x18000dca6`
- end: `0x18000dcd1`
- name: `_std::list_Command_std::allocator_Command___::sort_::_1_::dtor$1`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001bc8`

## pseudocode

```c
void __fastcall std::list_Command_std::allocator_Command___::sort_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  `eh vector destructor iterator'((void *)(a2 + 64), 0x10u, 0x1Au, (void (*)(void *))std::list<Command>::~list<Command>);
}

```

## disassembly

```asm
0x18000dca6  push    rbp
0x18000dca8  sub     rsp, 20h
0x18000dcac  mov     rbp, rdx
0x18000dcaf  lea     r9, ??1?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@XZ; void (*)(void *)
0x18000dcb6  mov     r8d, 1Ah; unsigned __int64
0x18000dcbc  mov     edx, 10h; unsigned __int64
0x18000dcc1  lea     rcx, [rbp+40h]; void *
0x18000dcc5  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18000dcca  add     rsp, 20h
0x18000dcce  pop     rbp
0x18000dccf  retn
```
