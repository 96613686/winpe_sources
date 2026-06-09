# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x180006790`
- end: `0x180006797`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1800034f0`
- `0x180003d40`
- `0x180004110`
- `0x180004fc8`
- `0x180007e80`
- `0x18000fdb0`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x180006790  mov     ecx, 7
0x180006795  int     29h; Win8: RtlFailFast(ecx)
```
