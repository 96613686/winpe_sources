# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180009a4c`
- end: `0x180009a53`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x18000328c`
- `0x180004428`
- `0x1800047cc`
- `0x180004b9c`
- `0x180006214`
- `0x18000778c`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180009a4c  mov     ecx, 7
0x180009a51  int     29h; Win8: RtlFailFast(ecx)
```
