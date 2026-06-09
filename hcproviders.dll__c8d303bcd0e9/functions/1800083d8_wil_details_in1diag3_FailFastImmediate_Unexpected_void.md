# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1800083d8`
- end: `0x1800083df`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180005f74`
- `0x18000692c`
- `0x180007474`
- `0x1800077f0`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1800083d8  mov     ecx, 7
0x1800083dd  int     29h; Win8: RtlFailFast(ecx)
```
