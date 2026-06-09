# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1800056fc`
- end: `0x180005703`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002ef8`
- `0x1800034ac`
- `0x18000385c`
- `0x18000468c`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1800056fc  mov     ecx, 7
0x180005701  int     29h; Win8: RtlFailFast(ecx)
```
