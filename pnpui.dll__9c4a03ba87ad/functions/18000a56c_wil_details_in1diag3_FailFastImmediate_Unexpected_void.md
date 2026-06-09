# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000a56c`
- end: `0x18000a573`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1800040fc`
- `0x180004d1c`
- `0x1800050c0`
- `0x1800056f4`
- `0x180007a74`
- `0x180008eac`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000a56c  mov     ecx, 7
0x18000a571  int     29h; Win8: RtlFailFast(ecx)
```
