# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x14000af58`
- end: `0x14000af5f`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x140003e8c`
- `0x140004158`
- `0x140005738`
- `0x140005b08`
- `0x140006434`
- `0x140007d88`
- `0x14000905c`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x14000af58  mov     ecx, 7
0x14000af5d  int     29h; Win8: RtlFailFast(ecx)
```
