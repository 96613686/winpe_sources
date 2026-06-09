# _invalid_parameter

- ea: `0x14000190c`
- end: `0x140001911`
- name: `_invalid_parameter`
- size: `5`
- prototype: `void __cdecl __noreturn(const wchar_t *Expression, const wchar_t *FunctionName, const wchar_t *FileName, unsigned int LineNo, uintptr_t Reserved)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x140004324`
- `0x1400043c0`
- `0x140004488`
- `0x14000456c`
- `0x1400052f4`
- `0x140006f4c`
- `0x14000a4d4`
- `0x14001490c`
- `0x140014f98`
- `0x14001b840`

## callees

- `0x140001918`

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
0x14000190c  jmp     _invoke_watson
```
