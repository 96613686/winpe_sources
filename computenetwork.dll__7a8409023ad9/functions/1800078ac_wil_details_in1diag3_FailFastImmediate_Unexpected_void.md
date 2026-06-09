# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1800078ac`
- end: `0x1800078b3`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180003770`
- `0x180003a3c`
- `0x1800044f8`
- `0x1800048c8`
- `0x1800060f0`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1800078ac  mov     ecx, 7
0x1800078b1  int     29h; Win8: RtlFailFast(ecx)
```
