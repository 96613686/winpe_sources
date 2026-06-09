# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000a12c`
- end: `0x18000a133`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x180003424`
- `0x180004418`
- `0x1800047e8`
- `0x180004be0`
- `0x1800062f8`
- `0x1800077bc`
- `0x18000b488`
- `0x18000ce60`
- `0x18000dce4`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000a12c  mov     ecx, 7
0x18000a131  int     29h; Win8: RtlFailFast(ecx)
```
