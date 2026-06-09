# _CWinTaskClassFactoryT_AOMDHandler_1_::CreateInstance_::_1_::dtor$0

- ea: `0x180022f1b`
- end: `0x180022f39`
- name: `_CWinTaskClassFactoryT_AOMDHandler_1_::CreateInstance_::_1_::dtor$0`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180002b0c`

## pseudocode

```c
void __fastcall CWinTaskClassFactoryT_AOMDHandler_1_::CreateInstance_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 72));
}

```

## disassembly

```asm
0x180022f1b  push    rbp
0x180022f1d  sub     rsp, 20h
0x180022f21  mov     rbp, rdx
0x180022f24  mov     edx, 0A8h; unsigned __int64
0x180022f29  mov     rcx, [rbp+48h]; void *
0x180022f2d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180022f32  add     rsp, 20h
0x180022f36  pop     rbp
0x180022f37  retn
```
