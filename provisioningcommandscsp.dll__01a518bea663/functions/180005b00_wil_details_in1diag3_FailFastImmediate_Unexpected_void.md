# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180005b00`
- end: `0x180005b07`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180002818`
- `0x180003140`
- `0x180003524`
- `0x180004400`
- `0x1800064ac`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180005b00  mov     ecx, 7
0x180005b05  int     29h; Win8: RtlFailFast(ecx)
```
