# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x14000bc1c`
- end: `0x14000bc23`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x140003828`
- `0x140003adc`
- `0x140004bd0`
- `0x140005600`
- `0x140007b00`
- `0x140013330`
- `0x14001556c`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x14000bc1c  mov     ecx, 7
0x14000bc21  int     29h; Win8: RtlFailFast(ecx)
```
