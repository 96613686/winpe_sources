# LKRhash::CTypedHashTable<SnapinCLSIDTable,SnapinRecord,CStr const *,LKRhash::CLKRLinearHashTable>::_ExtractKey(void const *)

- ea: `0x18000e530`
- end: `0x18000e547`
- name: `?_ExtractKey@?$CTypedHashTable@VSnapinCLSIDTable@@VSnapinRecord@@PEBVCStr@@VCLKRLinearHashTable@LKRhash@@@LKRhash@@CA?B_KPEBX@Z`
- size: `23`
- prototype: `unsigned __int64(const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000e530`
- `0x18001d010`

## pseudocode

```c
__int64 __fastcall LKRhash::CTypedHashTable<SnapinCLSIDTable,SnapinRecord,CStr const *,LKRhash::CLKRLinearHashTable>::_ExtractKey(
        const void *a1)
{
  if ( a1 )
    return (*(__int64 (__fastcall **)(const void *))(*(_QWORD *)a1 + 168LL))(a1);
  else
    return 0;
}

```

## disassembly

```asm
0x18000e530  test    rcx, rcx
0x18000e533  jz      short loc_18000E544
0x18000e535  mov     rax, [rcx]
0x18000e538  mov     rax, [rax+0A8h]
0x18000e53f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000e544  xor     eax, eax
0x18000e546  retn
```
