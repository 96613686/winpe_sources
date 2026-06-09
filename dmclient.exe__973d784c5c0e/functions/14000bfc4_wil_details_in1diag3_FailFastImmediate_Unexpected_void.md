# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x14000bfc4`
- end: `0x14000bfcb`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x140003884`
- `0x140003b48`
- `0x140005740`
- `0x140007c9c`
- `0x1400178ac`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x14000bfc4  mov     ecx, 7
0x14000bfc9  int     29h; Win8: RtlFailFast(ecx)
```
