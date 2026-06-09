# SortDirectoryEntries(void const *,void const *)

- ea: `0x180003900`
- end: `0x18000390f`
- name: `?SortDirectoryEntries@@YAHPEBX0@Z`
- size: `15`
- prototype: `int __fastcall(const wchar_t *, const wchar_t *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180003908`

## pseudocode

```c
int __fastcall SortDirectoryEntries(const wchar_t *a1, const wchar_t *a2)
{
  return _wcsicmp(a1 + 22, a2 + 22);
}

```

## disassembly

```asm
0x180003900  add     rdx, 2Ch ; ','
0x180003904  add     rcx, 2Ch ; ','
0x180003908  jmp     cs:__imp__wcsicmp
```
