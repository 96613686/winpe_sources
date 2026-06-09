# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000b3f4`
- end: `0x18000b3fb`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180002884`
- `0x180003828`
- `0x180003bf8`
- `0x180004bb4`
- `0x180006ba0`
- `0x180008558`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000b3f4  mov     ecx, 7
0x18000b3f9  int     29h; Win8: RtlFailFast(ecx)
```
