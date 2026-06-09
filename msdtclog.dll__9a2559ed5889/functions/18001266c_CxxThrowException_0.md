# _CxxThrowException_0

- ea: `0x18001266c`
- end: `0x180012672`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `54`
- callee_count: `0`
- tags: ``

## callers

- `0x180001270`
- `0x180004708`
- `0x180005a7c`
- `0x180005c04`
- `0x180005ca8`
- `0x180006328`
- `0x180006f8c`
- `0x1800073b4`
- `0x180007b40`
- `0x180007d7c`
- `0x180008248`
- `0x180009050`
- `0x180009178`
- `0x180009298`
- `0x180009848`
- `0x180009934`
- `0x180009b00`
- `0x180009e6c`
- `0x18000a288`
- `0x18000a990`
- `0x18000aae4`
- `0x18000afa8`
- `0x18000b658`
- `0x18000b798`
- `0x18000b974`
- `0x18000c6b8`
- `0x18000c7fc`
- `0x18000cec8`
- `0x18000d160`
- `0x18000d2f0`
- `0x18000d3ec`
- `0x18000d694`
- `0x1800134ac`
- `0x1800134d6`
- `0x1800136bc`
- `0x1800136fe`
- `0x180013752`
- `0x18001377c`
- `0x1800137ee`
- `0x18001381b`
- `0x180013848`
- `0x1800138d6`
- `0x1800139f5`
- `0x180013a73`
- `0x180013af1`
- `0x180013b24`
- `0x180013df4`
- `0x180013e34`
- `0x180013e74`
- `0x180013f46`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x18001266c`

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
0x18001266c  jmp     cs:__imp__CxxThrowException
```
