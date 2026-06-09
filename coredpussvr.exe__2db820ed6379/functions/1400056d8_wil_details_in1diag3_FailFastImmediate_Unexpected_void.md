# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1400056d8`
- end: `0x1400056df`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140002788`
- `0x140003fac`
- `0x140004340`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1400056d8  mov     ecx, 7
0x1400056dd  int     29h; Win8: RtlFailFast(ecx)
```
