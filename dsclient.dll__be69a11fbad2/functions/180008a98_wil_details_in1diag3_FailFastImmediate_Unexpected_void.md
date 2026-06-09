# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180008a98`
- end: `0x180008a9f`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1800040f8`
- `0x180005074`
- `0x180006088`
- `0x1800061c8`
- `0x1800065dc`
- `0x18000672c`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180008a98  mov     ecx, 7
0x180008a9d  int     29h; Win8: RtlFailFast(ecx)
```
