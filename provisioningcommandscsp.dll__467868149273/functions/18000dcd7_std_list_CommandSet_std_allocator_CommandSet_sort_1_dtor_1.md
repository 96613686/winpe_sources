# _std::list_CommandSet_std::allocator_CommandSet___::sort_::_1_::dtor$1

- ea: `0x18000dcd7`
- end: `0x18000dd02`
- name: `_std::list_CommandSet_std::allocator_CommandSet___::sort_::_1_::dtor$1`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001bc8`

## pseudocode

```c
void __fastcall std::list_CommandSet_std::allocator_CommandSet___::sort_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  `eh vector destructor iterator'(
    (void *)(a2 + 64),
    0x10u,
    0x1Au,
    (void (*)(void *))std::list<CommandSet>::~list<CommandSet>);
}

```

## disassembly

```asm
0x18000dcd7  push    rbp
0x18000dcd9  sub     rsp, 20h
0x18000dcdd  mov     rbp, rdx
0x18000dce0  lea     r9, ??1?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ; void (*)(void *)
0x18000dce7  mov     r8d, 1Ah; unsigned __int64
0x18000dced  mov     edx, 10h; unsigned __int64
0x18000dcf2  lea     rcx, [rbp+40h]; void *
0x18000dcf6  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18000dcfb  add     rsp, 20h
0x18000dcff  pop     rbp
0x18000dd00  retn
```
