# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x140002f98`
- end: `0x140002f9f`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140001ed8`
- `0x140002920`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x140002f98  mov     ecx, 7
0x140002f9d  int     29h; Win8: RtlFailFast(ecx)
```
