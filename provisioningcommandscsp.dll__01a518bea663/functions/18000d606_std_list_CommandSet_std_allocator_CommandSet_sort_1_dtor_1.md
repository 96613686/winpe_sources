# _std::list_CommandSet_std::allocator_CommandSet___::sort_::_1_::dtor$1

- ea: `0x18000d606`
- end: `0x18000d630`
- name: `_std::list_CommandSet_std::allocator_CommandSet___::sort_::_1_::dtor$1`
- size: `42`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001bb8`

## pseudocode

```c
void __fastcall std::list_CommandSet_std::allocator_CommandSet___::sort_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  `eh vector destructor iterator'(
    (void *)(a2 + 64),
    0x10u,
    26,
    (void (*)(void *))std::list<CommandSet>::~list<CommandSet>);
}

```

## disassembly

```asm
0x18000d606  push    rbp
0x18000d608  sub     rsp, 20h
0x18000d60c  mov     rbp, rdx
0x18000d60f  lea     r9, ??1?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ; void (*)(void *)
0x18000d616  mov     r8d, 1Ah; unsigned __int64
0x18000d61c  mov     edx, 10h; unsigned __int64
0x18000d621  lea     rcx, [rbp+40h]; void *
0x18000d625  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18000d62a  add     rsp, 20h
0x18000d62e  pop     rbp
0x18000d62f  retn
```
