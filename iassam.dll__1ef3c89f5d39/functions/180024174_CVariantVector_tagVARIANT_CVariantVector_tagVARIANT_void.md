# CVariantVector<tagVARIANT>::~CVariantVector<tagVARIANT>(void)

- ea: `0x180024174`
- end: `0x180024187`
- name: `??1?$CVariantVector@UtagVARIANT@@@@QEAA@XZ`
- size: `19`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18002d15e`
- `0x18002d394`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002417b`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002417b`

## pseudocode

```c
HRESULT __fastcall CVariantVector<tagVARIANT>::~CVariantVector<tagVARIANT>(SAFEARRAY **a1)
{
  return SafeArrayUnaccessData(*a1);
}

```

## disassembly

```asm
0x180024174  sub     rsp, 28h
0x180024178  mov     rcx, [rcx]; psa
0x18002417b  call    cs:__imp_SafeArrayUnaccessData
0x180024181  nop
0x180024182  add     rsp, 28h
0x180024186  retn
```
