# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000843c`
- end: `0x180008443`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180003638`
- `0x18000410c`
- `0x1800044b0`
- `0x180004880`
- `0x180005c40`
- `0x180006de8`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000843c  mov     ecx, 7
0x180008441  int     29h; Win8: RtlFailFast(ecx)
```
