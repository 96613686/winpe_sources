# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000782c`
- end: `0x180007833`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1800025f8`
- `0x180003114`
- `0x1800034b8`
- `0x1800038a4`
- `0x180004e40`
- `0x1800060b4`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000782c  mov     ecx, 7
0x180007831  int     29h; Win8: RtlFailFast(ecx)
```
