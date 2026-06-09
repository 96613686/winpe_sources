# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x140006ccc`
- end: `0x140006cd3`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x140002a34`
- `0x140002d48`
- `0x140003d68`
- `0x14000410c`
- `0x140005000`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x140006ccc  mov     ecx, 7
0x140006cd1  int     29h; Win8: RtlFailFast(ecx)
```
