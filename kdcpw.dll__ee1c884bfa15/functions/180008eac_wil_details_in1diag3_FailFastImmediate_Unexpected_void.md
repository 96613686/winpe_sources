# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180008eac`
- end: `0x180008eb3`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180002d7c`
- `0x1800039e4`
- `0x180003d88`
- `0x180004158`
- `0x180005bec`
- `0x180007248`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180008eac  mov     ecx, 7
0x180008eb1  int     29h; Win8: RtlFailFast(ecx)
```
