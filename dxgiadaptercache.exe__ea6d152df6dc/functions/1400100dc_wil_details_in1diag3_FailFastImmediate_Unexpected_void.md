# wil::details::in1diag3::_FailFastImmediate_Unexpected(void)

- ea: `0x1400100dc`
- end: `0x1400100e3`
- name: `?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ`
- size: `7`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x140003f54`
- `0x1400042ec`
- `0x140007368`
- `0x140007738`
- `0x140007f28`
- `0x140009ee4`
- `0x14000badc`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFastImmediate_Unexpected(wil::details::in1diag3 *this)
{
  __fastfail(7u);
}

```

## disassembly

```asm
0x1400100dc  mov     ecx, 7
0x1400100e1  int     29h; Win8: RtlFailFast(ecx)
```
