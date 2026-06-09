# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000cedc`
- end: `0x18000cee3`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1800079f8`
- `0x180008828`
- `0x180008bcc`
- `0x180009044`
- `0x18000a344`
- `0x18000b500`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000cedc  mov     ecx, 7
0x18000cee1  int     29h; Win8: RtlFailFast(ecx)
```
