# wil::details::in1diag5::_FailFastImmediate_Unexpected(void)

- ea: `0x180009e10`
- end: `0x180009e17`
- name: `?_FailFastImmediate_Unexpected@in1diag5@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag5 *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800053b4`
- `0x180006698`
- `0x180007688`
- `0x180007c9c`
- `0x180007df0`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag5::_FailFastImmediate_Unexpected(wil::details::in1diag5 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180009e10  mov     ecx, 7
0x180009e15  int     29h; Win8: RtlFailFast(ecx)
```
