# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x18000581c`
- end: `0x180005823`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800025f4`
- `0x180002e48`
- `0x180003218`
- `0x1800040e8`
- `0x1800072f0`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x18000581c  mov     ecx, 7
0x180005821  int     29h; Win8: RtlFailFast(ecx)
```
