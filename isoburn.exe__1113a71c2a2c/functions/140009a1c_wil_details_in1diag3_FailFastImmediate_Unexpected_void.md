# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x140009a1c`
- end: `0x140009a23`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1400032c4`
- `0x140003ecc`
- `0x140004734`
- `0x140006cd4`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x140009a1c  mov     ecx, 7
0x140009a21  int     29h; Win8: RtlFailFast(ecx)
```
