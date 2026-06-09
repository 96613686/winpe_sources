# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000d71c`
- end: `0x18000d723`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000b088`
- `0x18000b59c`
- `0x18000b940`
- `0x18000c830`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000d71c  mov     ecx, 7
0x18000d721  int     29h; Win8: RtlFailFast(ecx)
```
