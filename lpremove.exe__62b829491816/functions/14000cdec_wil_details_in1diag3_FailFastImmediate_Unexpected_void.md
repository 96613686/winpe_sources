# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x14000cdec`
- end: `0x14000cdf3`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x140003e58`
- `0x140005ce8`
- `0x1400060b8`
- `0x140006810`
- `0x1400086ac`
- `0x140009dac`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x14000cdec  mov     ecx, 7
0x14000cdf1  int     29h; Win8: RtlFailFast(ecx)
```
