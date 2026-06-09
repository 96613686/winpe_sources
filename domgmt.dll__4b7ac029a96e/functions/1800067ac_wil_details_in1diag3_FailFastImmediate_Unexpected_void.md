# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1800067ac`
- end: `0x1800067b3`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180003568`
- `0x180003db8`
- `0x180004188`
- `0x180005060`
- `0x1800070d0`
- `0x180009190`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1800067ac  mov     ecx, 7
0x1800067b1  int     29h; Win8: RtlFailFast(ecx)
```
