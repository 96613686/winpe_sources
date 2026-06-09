# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x140006564`
- end: `0x14000656b`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x140003868`
- `0x1400043e4`
- `0x140005174`
- `0x1400054dc`
- `0x140007bb0`
- `0x140007dd0`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x140006564  mov     ecx, 7
0x140006569  int     29h; Win8: RtlFailFast(ecx)
```
