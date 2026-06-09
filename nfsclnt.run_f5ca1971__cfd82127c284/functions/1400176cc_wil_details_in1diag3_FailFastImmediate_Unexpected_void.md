# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1400176cc`
- end: `0x1400176d3`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1400128c8`
- `0x14001339c`
- `0x140013740`
- `0x140013b10`
- `0x140014ed0`
- `0x140016078`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1400176cc  mov     ecx, 7
0x1400176d1  int     29h; Win8: RtlFailFast(ecx)
```
