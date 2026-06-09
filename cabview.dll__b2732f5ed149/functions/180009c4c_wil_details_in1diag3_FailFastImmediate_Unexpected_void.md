# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180009c4c`
- end: `0x180009c53`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000360c`
- `0x18000527c`
- `0x180006a0c`
- `0x180006e60`
- `0x180006fd0`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180009c4c  mov     ecx, 7
0x180009c51  int     29h; Win8: RtlFailFast(ecx)
```
