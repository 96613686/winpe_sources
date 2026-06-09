# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1400083ac`
- end: `0x1400083b3`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x14000290c`
- `0x140002bb8`
- `0x1400039d8`
- `0x140003da8`
- `0x1400041a0`
- `0x1400064cc`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1400083ac  mov     ecx, 7
0x1400083b1  int     29h; Win8: RtlFailFast(ecx)
```
