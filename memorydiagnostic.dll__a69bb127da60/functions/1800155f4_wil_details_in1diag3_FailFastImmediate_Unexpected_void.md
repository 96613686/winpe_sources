# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1800155f4`
- end: `0x1800155fb`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x1800057f0`
- `0x180005aa4`
- `0x180006b88`
- `0x180006cb0`
- `0x180008cc8`
- `0x180009098`
- `0x18000a294`
- `0x18000de68`
- `0x18000faac`
- `0x180016818`
- `0x180016954`
- `0x180016ba4`
- `0x180016cc4`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1800155f4  mov     ecx, 7
0x1800155f9  int     29h; Win8: RtlFailFast(ecx)
```
