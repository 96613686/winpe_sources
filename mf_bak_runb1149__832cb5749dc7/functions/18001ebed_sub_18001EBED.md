# sub_18001EBED

- ea: `0x18001ebed`
- end: `0x18001ebf9`
- name: `sub_18001EBED`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18001eb6e`

## import_xrefs

- `ext-ms-win-setupapi-classinstallers-l1-1-2!SetupDiOpenDevRegKey` at `0x18001ebed`

## pseudocode

```c
__int64 sub_18001EBED()
{
  return sub_18001EB6E();
}

```

## disassembly

```asm
0x18001ebed  lea     rax, SetupDiOpenDevRegKey
0x18001ebf4  jmp     sub_18001EB6E
```
