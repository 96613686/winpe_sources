# _CDimsJobTaskHandler::Start_::_1_::dtor$1

- ea: `0x18000af50`
- end: `0x18000af5c`
- name: `_CDimsJobTaskHandler::Start_::_1_::dtor$1`
- size: `12`
- prototype: `HLOCAL __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x1800032d0`

## pseudocode

```c
HLOCAL __fastcall CDimsJobTaskHandler::Start_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return operator delete(*(HLOCAL *)(a2 + 80));
}

```

## disassembly

```asm
0x18000af50  mov     rcx, [rdx+50h]; hMem
0x18000af57  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
