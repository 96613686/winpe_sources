# GetDllVersion

- ea: `0x180015780`
- end: `0x180015788`
- name: `GetDllVersion`
- size: `8`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
const char *GetDllVersion()
{
  return "5.00";
}

```

## disassembly

```asm
0x180015780  lea     rax, a500; "5.00"
0x180015787  retn
```
