# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180005fc4`
- end: `0x180005fcb`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000317c`
- `0x180003c14`
- `0x180004afc`
- `0x180004e4c`
- `0x1800083b0`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180005fc4  mov     ecx, 7
0x180005fc9  int     29h; Win8: RtlFailFast(ecx)
```
