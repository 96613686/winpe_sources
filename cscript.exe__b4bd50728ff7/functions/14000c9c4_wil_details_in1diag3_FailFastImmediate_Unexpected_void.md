# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x14000c9c4`
- end: `0x14000c9cb`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x14000a99c`
- `0x14000b1fc`
- `0x14000bb90`
- `0x14000bee0`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x14000c9c4  mov     ecx, 7
0x14000c9c9  int     29h; Win8: RtlFailFast(ecx)
```
