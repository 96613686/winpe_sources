# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000602c`
- end: `0x180006033`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002bb8`
- `0x1800034b8`
- `0x180003888`
- `0x1800048f8`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000602c  mov     ecx, 7
0x180006031  int     29h; Win8: RtlFailFast(ecx)
```
