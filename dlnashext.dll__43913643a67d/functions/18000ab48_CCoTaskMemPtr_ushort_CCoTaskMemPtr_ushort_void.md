# CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)

- ea: `0x18000ab48`
- end: `0x18000ab5c`
- name: `??1?$CCoTaskMemPtr@G@@QEAA@XZ`
- size: `20`
- prototype: ``
- caller_count: `49`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e2c8`
- `0x18000f740`
- `0x18000fda8`
- `0x180011204`
- `0x18001538c`
- `0x180015bac`
- `0x180016af0`
- `0x180016ce4`
- `0x180017a8c`
- `0x1800180f0`
- `0x1800181dc`
- `0x180018354`
- `0x180018728`
- `0x180018864`
- `0x180018934`
- `0x180018b94`
- `0x180019298`
- `0x180019370`
- `0x18001949c`
- `0x18001a848`
- `0x18001a8d8`
- `0x18001fdc0`
- `0x180020150`
- `0x180020228`
- `0x180020578`
- `0x180020ab0`
- `0x180020ae0`
- `0x18002260c`
- `0x180025c58`
- `0x180033560`
- `0x180033620`
- `0x180033862`
- `0x180033900`
- `0x180033920`
- `0x180033bb1`
- `0x180033d3e`
- `0x180033daa`
- `0x180033dbc`
- `0x180033de0`
- `0x180033fc8`
- `0x180034010`
- `0x180034022`
- `0x1800340b2`
- `0x1800340c4`
- `0x180034151`
- `0x180034163`
- `0x1800341bd`
- `0x1800343a3`
- `0x1800343b9`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ab55`

## pseudocode

```c
void __fastcall CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  *a1 = 0;
  CoTaskMemFree(v2);
}

```

## disassembly

```asm
0x18000ab48  mov     rax, rcx
0x18000ab4b  mov     rcx, [rcx]
0x18000ab4e  mov     qword ptr [rax], 0
0x18000ab55  jmp     cs:__imp_CoTaskMemFree
```
