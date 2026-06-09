# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x140009e10`
- end: `0x140009e17`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x14000330c`
- `0x140004a88`
- `0x140006158`
- `0x140007a24`
- `0x140014d88`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x140009e10  mov     ecx, 7
0x140009e15  int     29h; Win8: RtlFailFast(ecx)
```
