# _CCompRC::LoadLibraryHelper_::_1_::dtor$2

- ea: `0x140015d0c`
- end: `0x140015d18`
- name: `_CCompRC::LoadLibraryHelper_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140009d48`

## pseudocode

```c
void __fastcall CCompRC::LoadLibraryHelper_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  ExceptionHolderTemplate<Exception>::~ExceptionHolderTemplate<Exception>((__int64 *)(a2 + 104));
}

```

## disassembly

```asm
0x140015d0c  lea     rcx, [rdx+68h]
0x140015d13  jmp     ??1?$ExceptionHolderTemplate@VException@@@@QEAA@XZ; ExceptionHolderTemplate<Exception>::~ExceptionHolderTemplate<Exception>(void)
```
