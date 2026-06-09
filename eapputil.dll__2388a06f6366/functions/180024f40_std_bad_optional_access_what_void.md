# std::bad_optional_access::what(void)

- ea: `0x180024f40`
- end: `0x180024f48`
- name: `?what@bad_optional_access@std@@UEBAPEBDXZ`
- size: `8`
- prototype: `const char *__fastcall(std::bad_optional_access *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## string_xrefs

- `0x180024f40`: `Bad optional access`

## pseudocode

```c
const char *__fastcall std::bad_optional_access::what(std::bad_optional_access *this)
{
  return "Bad optional access";
}

```

## disassembly

```asm
0x180024f40  lea     rax, aBadOptionalAcc; "Bad optional access"
0x180024f47  retn
```
