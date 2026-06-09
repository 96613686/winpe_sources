# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000ca3c`
- end: `0x18000ca43`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180007c38`
- `0x18000870c`
- `0x180008ab0`
- `0x180008e80`
- `0x18000a240`
- `0x18000b3e8`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000ca3c  mov     ecx, 7
0x18000ca41  int     29h; Win8: RtlFailFast(ecx)
```
