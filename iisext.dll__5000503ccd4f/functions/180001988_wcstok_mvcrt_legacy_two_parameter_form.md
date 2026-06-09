# wcstok_mvcrt_legacy_two_parameter_form

- ea: `0x180001988`
- end: `0x18000198f`
- name: `wcstok_mvcrt_legacy_two_parameter_form`
- size: `7`
- prototype: `wchar_t *__cdecl(wchar_t *String, const wchar_t *Delimiter, wchar_t **Context)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000e408`
- `0x18000f908`
- `0x18000fd64`
- `0x1800103ac`

## import_xrefs

- `msvcrt!wcstok` at `0x180001988`

## pseudocode

```c
// attributes: thunk
wchar_t *__cdecl wcstok_mvcrt_legacy_two_parameter_form(wchar_t *String, const wchar_t *Delimiter, wchar_t **Context)
{
  return wcstok(String, Delimiter, Context);
}

```

## disassembly

```asm
0x180001988  jmp     cs:__imp_wcstok
```
