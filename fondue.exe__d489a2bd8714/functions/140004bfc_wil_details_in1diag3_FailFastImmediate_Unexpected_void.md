# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x140004bfc`
- end: `0x140004c03`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1400025a4`
- `0x140002ab8`
- `0x140002e5c`
- `0x140003d00`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x140004bfc  mov     ecx, 7
0x140004c01  int     29h; Win8: RtlFailFast(ecx)
```
