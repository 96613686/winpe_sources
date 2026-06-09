# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1800078b4`
- end: `0x1800078bb`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002750`
- `0x180003518`
- `0x180003964`
- `0x180004d90`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1800078b4  mov     ecx, 7
0x1800078b9  int     29h; Win8: RtlFailFast(ecx)
```
