# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000a3bc`
- end: `0x18000a3c3`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180003ce8`
- `0x1800050b8`
- `0x180005488`
- `0x180005880`
- `0x180006e10`
- `0x18000830c`
- `0x180011b6c`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000a3bc  mov     ecx, 7
0x18000a3c1  int     29h; Win8: RtlFailFast(ecx)
```
