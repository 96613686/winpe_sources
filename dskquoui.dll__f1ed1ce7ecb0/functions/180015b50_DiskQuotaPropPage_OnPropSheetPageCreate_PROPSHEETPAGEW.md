# DiskQuotaPropPage::OnPropSheetPageCreate(_PROPSHEETPAGEW *)

- ea: `0x180015b50`
- end: `0x180015b56`
- name: `?OnPropSheetPageCreate@DiskQuotaPropPage@@MEAAIPEAU_PROPSHEETPAGEW@@@Z`
- size: `6`
- prototype: `unsigned int __fastcall(DiskQuotaPropPage *__hidden this, struct _PROPSHEETPAGEW *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001650`

## pseudocode

```c
__int64 __fastcall DiskQuotaPropPage::OnPropSheetPageCreate(DiskQuotaPropPage *this, struct _PROPSHEETPAGEW *a2)
{
  return 1;
}

```

## disassembly

```asm
0x180015b50  mov     eax, 1
0x180015b55  retn
```
