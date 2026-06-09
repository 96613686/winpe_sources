# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000b204`
- end: `0x18000b20b`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180008a54`
- `0x180008fc8`
- `0x18000936c`
- `0x18000a0fc`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000b204  mov     ecx, 7
0x18000b209  int     29h; Win8: RtlFailFast(ecx)
```
