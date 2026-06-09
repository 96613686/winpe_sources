# __imp_load_QuerySecurityContextToken

- ea: `0x180014c2a`
- end: `0x180014c36`
- name: `__imp_load_QuerySecurityContextToken`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800147fb`

## import_xrefs

- `SspiCli!QuerySecurityContextToken` at `0x180014c2a`

## pseudocode

```c
__int64 load_QuerySecurityContextToken()
{
  return _tailMerge_sspicli_dll();
}

```

## disassembly

```asm
0x180014c2a  lea     rax, __imp_QuerySecurityContextToken
0x180014c31  jmp     __tailMerge_sspicli_dll
```
