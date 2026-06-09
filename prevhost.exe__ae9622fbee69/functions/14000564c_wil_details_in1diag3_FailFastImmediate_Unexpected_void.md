# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x14000564c`
- end: `0x140005653`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1400023cc`
- `0x140002b44`
- `0x140002f74`
- `0x1400040dc`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x14000564c  mov     ecx, 7
0x140005651  int     29h; Win8: RtlFailFast(ecx)
```
