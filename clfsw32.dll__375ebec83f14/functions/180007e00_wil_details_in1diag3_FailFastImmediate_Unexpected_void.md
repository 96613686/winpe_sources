# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180007e00`
- end: `0x180007e07`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002dcc`
- `0x180003f78`
- `0x180005300`
- `0x18000658c`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180007e00  mov     ecx, 7
0x180007e05  int     29h; Win8: RtlFailFast(ecx)
```
