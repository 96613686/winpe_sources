# _CxxThrowException_0

- ea: `0x1800020bd`
- end: `0x1800020c3`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `26`
- callee_count: `0`
- tags: ``

## callers

- `0x180001484`
- `0x180001588`
- `0x180006a70`
- `0x1800076e0`
- `0x18000ce20`
- `0x1800110a4`
- `0x180013114`
- `0x180013390`
- `0x180017374`
- `0x180017428`
- `0x180017fe0`
- `0x1800180ec`
- `0x18001884c`
- `0x180019b1c`
- `0x180019e70`
- `0x18001a24c`
- `0x18001b428`
- `0x18001c4b8`
- `0x18001d18e`
- `0x18001d76e`
- `0x18001d794`
- `0x18001dc38`
- `0x18001dc5e`
- `0x18001e041`
- `0x18001e07b`
- `0x18001e0a4`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x1800020bd`

## pseudocode

```c
// attributes: thunk
void __stdcall __noreturn CxxThrowException_0(void *pExceptionObject, _ThrowInfo *pThrowInfo)
{
  _CxxThrowException(pExceptionObject, pThrowInfo);
}

```

## disassembly

```asm
0x1800020bd  jmp     cs:__imp__CxxThrowException
```
