# _CWinTaskClassFactoryT_AOMDHandler_1_::CreateInstance_::_1_::dtor$0

- ea: `0x180021555`
- end: `0x180021572`
- name: `_CWinTaskClassFactoryT_AOMDHandler_1_::CreateInstance_::_1_::dtor$0`
- size: `29`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180003294`

## pseudocode

```c
void __fastcall CWinTaskClassFactoryT_AOMDHandler_1_::CreateInstance_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 72));
}

```

## disassembly

```asm
0x180021555  push    rbp
0x180021557  sub     rsp, 20h
0x18002155b  mov     rbp, rdx
0x18002155e  mov     edx, 0A8h
0x180021563  mov     rcx, [rbp+48h]; Block
0x180021567  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002156c  add     rsp, 20h
0x180021570  pop     rbp
0x180021571  retn
```
