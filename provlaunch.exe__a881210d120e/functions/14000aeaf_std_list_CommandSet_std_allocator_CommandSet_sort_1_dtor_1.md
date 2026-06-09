# _std::list_CommandSet_std::allocator_CommandSet___::sort_::_1_::dtor$1

- ea: `0x14000aeaf`
- end: `0x14000aed9`
- name: `_std::list_CommandSet_std::allocator_CommandSet___::sort_::_1_::dtor$1`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140002228`

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
0x14000aeaf  push    rbp
0x14000aeb1  sub     rsp, 20h
0x14000aeb5  mov     rbp, rdx
0x14000aeb8  lea     r9, ??1?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ; void (*)(void *)
0x14000aebf  mov     r8d, 1Ah; unsigned __int64
0x14000aec5  mov     edx, 10h; unsigned __int64
0x14000aeca  lea     rcx, [rbp+40h]; void *
0x14000aece  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x14000aed3  add     rsp, 20h
0x14000aed7  pop     rbp
0x14000aed8  retn
```
