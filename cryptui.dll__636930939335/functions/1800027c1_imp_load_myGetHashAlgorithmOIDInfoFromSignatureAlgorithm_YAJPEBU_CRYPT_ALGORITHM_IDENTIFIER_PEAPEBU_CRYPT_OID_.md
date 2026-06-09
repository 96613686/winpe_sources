# __imp_load_?myGetHashAlgorithmOIDInfoFromSignatureAlgorithm@@YAJPEBU_CRYPT_ALGORITHM_IDENTIFIER@@PEAPEBU_CRYPT_OID_INFO@@@Z

- ea: `0x1800027c1`
- end: `0x1800027cd`
- name: `__imp_load_?myGetHashAlgorithmOIDInfoFromSignatureAlgorithm@@YAJPEBU_CRYPT_ALGORITHM_IDENTIFIER@@PEAPEBU_CRYPT_OID_INFO@@@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180002658`

## import_xrefs

- `certca!__imp_?myGetHashAlgorithmOIDInfoFromSignatureAlgorithm@@YAJPEBU_CRYPT_ALGORITHM_IDENTIFIER@@PEAPEBU_CRYPT_OID_INFO@@@Z` at `0x1800027c1`

## pseudocode

```c
__int64 load__myGetHashAlgorithmOIDInfoFromSignatureAlgorithm__YAJPEBU_CRYPT_ALGORITHM_IDENTIFIER__PEAPEBU_CRYPT_OID_INFO___Z()
{
  return _tailMerge_certca_dll();
}

```

## disassembly

```asm
0x1800027c1  lea     rax, __imp_?myGetHashAlgorithmOIDInfoFromSignatureAlgorithm@@YAJPEBU_CRYPT_ALGORITHM_IDENTIFIER@@PEAPEBU_CRYPT_OID_INFO@@@Z; myGetHashAlgorithmOIDInfoFromSignatureAlgorithm(_CRYPT_ALGORITHM_IDENTIFIER const *,_CRYPT_OID_INFO const * *)
0x1800027c8  jmp     __tailMerge_certca_dll
```
