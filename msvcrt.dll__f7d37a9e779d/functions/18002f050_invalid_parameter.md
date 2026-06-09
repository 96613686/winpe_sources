# _invalid_parameter

- ea: `0x18002f050`
- end: `0x18002f055`
- name: `_invalid_parameter`
- size: `5`
- prototype: `void __cdecl __noreturn(const wchar_t *Expression, const wchar_t *FunctionName, const wchar_t *FileName, unsigned int LineNo, uintptr_t Reserved)`
- caller_count: `465`
- callee_count: `1`
- tags: ``

## callers

- `0x180001180`
- `0x180002318`
- `0x180002460`
- `0x180002640`
- `0x180002770`
- `0x180002bac`
- `0x180002cd0`
- `0x1800030cc`
- `0x180003200`
- `0x18000389c`
- `0x180003a80`
- `0x180003d20`
- `0x180003f80`
- `0x180004140`
- `0x18000447c`
- `0x180004830`
- `0x180004dc0`
- `0x180004f70`
- `0x1800052f4`
- `0x18000568c`
- `0x180005990`
- `0x180005b60`
- `0x180005da0`
- `0x1800060ec`
- `0x180006380`
- `0x180006564`
- `0x180006760`
- `0x180006820`
- `0x18000697c`
- `0x180006c90`
- `0x180006e00`
- `0x180006f90`
- `0x1800070b0`
- `0x180007220`
- `0x180007454`
- `0x1800075b4`
- `0x180007718`
- `0x180007878`
- `0x180007d80`
- `0x180007e00`
- `0x180007f30`
- `0x180007f80`
- `0x1800080a0`
- `0x180008140`
- `0x180008290`
- `0x180008410`
- `0x1800084a0`
- `0x180008960`
- `0x180008e90`
- `0x180008f30`

## callees

- `0x18002f05c`

## pseudocode

```c
// attributes: thunk
void __cdecl __noreturn invalid_parameter(
        const wchar_t *Expression,
        const wchar_t *FunctionName,
        const wchar_t *FileName,
        unsigned int LineNo,
        uintptr_t Reserved)
{
  invoke_watson(Expression, FunctionName, FileName, LineNo, Reserved);
}

```

## disassembly

```asm
0x18002f050  jmp     _invoke_watson
```
