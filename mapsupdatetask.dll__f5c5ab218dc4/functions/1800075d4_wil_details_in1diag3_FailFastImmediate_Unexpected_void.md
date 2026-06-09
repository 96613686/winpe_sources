# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1800075d4`
- end: `0x1800075db`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002d24`
- `0x1800037d4`
- `0x180003bb4`
- `0x180004fe0`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1800075d4  mov     ecx, 7
0x1800075d9  int     29h; Win8: RtlFailFast(ecx)
```
