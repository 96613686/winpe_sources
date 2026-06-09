# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000714c`
- end: `0x180007153`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180003e50`
- `0x1800046a8`
- `0x180004a78`
- `0x180005a08`
- `0x180009a00`
- `0x180012254`
- `0x1800186d8`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000714c  mov     ecx, 7
0x180007151  int     29h; Win8: RtlFailFast(ecx)
```
