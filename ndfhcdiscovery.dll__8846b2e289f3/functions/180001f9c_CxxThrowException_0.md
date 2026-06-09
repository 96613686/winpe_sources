# _CxxThrowException_0

- ea: `0x180001f9c`
- end: `0x180001fa2`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `23`
- callee_count: `0`
- tags: ``

## callers

- `0x180001488`
- `0x1800014b0`
- `0x1800014dc`
- `0x180002fe0`
- `0x1800034b0`
- `0x1800068ec`
- `0x180013ac6`
- `0x180013b3e`
- `0x180013b64`
- `0x180013b8e`
- `0x180013bb7`
- `0x180013c3a`
- `0x180013e87`
- `0x180013ead`
- `0x180013fb9`
- `0x180013fdf`
- `0x180013ffc`
- `0x180014032`
- `0x18001406b`
- `0x1800140a1`
- `0x1800140d7`
- `0x18001431a`
- `0x180014340`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x180001f9c`

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
0x180001f9c  jmp     cs:__imp__CxxThrowException
```
