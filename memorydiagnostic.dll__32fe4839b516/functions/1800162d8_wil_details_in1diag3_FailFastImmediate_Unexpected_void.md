# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1800162d8`
- end: `0x1800162df`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x1800052ec`
- `0x1800055b0`
- `0x180005870`
- `0x180006bc4`
- `0x180006d20`
- `0x18000a490`
- `0x1800103c4`
- `0x180017444`
- `0x18001758c`
- `0x1800177e4`
- `0x180017904`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1800162d8  mov     ecx, 7
0x1800162dd  int     29h; Win8: RtlFailFast(ecx)
```
