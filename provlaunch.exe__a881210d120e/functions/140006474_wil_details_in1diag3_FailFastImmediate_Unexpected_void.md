# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x140006474`
- end: `0x14000647b`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x140002a5c`
- `0x140002d10`
- `0x140003830`
- `0x140003e60`
- `0x140004c54`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x140006474  mov     ecx, 7
0x140006479  int     29h; Win8: RtlFailFast(ecx)
```
