# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180010398`
- end: `0x18001039f`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000bc54`
- `0x18000c8ec`
- `0x18000cc94`
- `0x18000e034`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180010398  mov     ecx, 7
0x18001039d  int     29h; Win8: RtlFailFast(ecx)
```
