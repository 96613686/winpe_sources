# EnumInfo_Clear(PSFORMAT_ENUMINFO *)

- ea: `0x18002cd24`
- end: `0x18002cd8b`
- name: `?EnumInfo_Clear@@YAXPEAUPSFORMAT_ENUMINFO@@@Z`
- size: `103`
- prototype: `void __fastcall(struct PSFORMAT_ENUMINFO *)`
- caller_count: `6`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002b138`
- `0x18002bc2c`
- `0x18002c3fc`
- `0x18002c7b0`
- `0x18002d8f0`
- `0x180081ab0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002cd31`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002cd3b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002cd45`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002cd31`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002cd3b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002cd45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cd4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cd59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cd63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cd6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cd4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cd59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cd63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cd6d`

## pseudocode

```c
void __fastcall EnumInfo_Clear(PROPVARIANT *a1)
{
  PropVariantClear(a1 + 1);
  PropVariantClear(a1 + 4);
  PropVariantClear(a1 + 7);
  CoTaskMemFree(a1[10]);
  CoTaskMemFree(a1[11]);
  CoTaskMemFree(a1[12]);
  CoTaskMemFree(a1[13]);
  a1[10] = 0;
  a1[11] = 0;
  a1[12] = 0;
  a1[13] = 0;
}

```

## disassembly

```asm
0x18002cd24  push    rbx
0x18002cd26  sub     rsp, 20h
0x18002cd2a  mov     rbx, rcx
0x18002cd2d  add     rcx, 8; pvar
0x18002cd31  call    cs:__imp_PropVariantClear
0x18002cd37  lea     rcx, [rbx+20h]; pvar
0x18002cd3b  call    cs:__imp_PropVariantClear
0x18002cd41  lea     rcx, [rbx+38h]; pvar
0x18002cd45  call    cs:__imp_PropVariantClear
0x18002cd4b  mov     rcx, [rbx+50h]; pv
0x18002cd4f  call    cs:__imp_CoTaskMemFree
0x18002cd55  mov     rcx, [rbx+58h]; pv
0x18002cd59  call    cs:__imp_CoTaskMemFree
0x18002cd5f  mov     rcx, [rbx+60h]; pv
0x18002cd63  call    cs:__imp_CoTaskMemFree
0x18002cd69  mov     rcx, [rbx+68h]; pv
0x18002cd6d  call    cs:__imp_CoTaskMemFree
0x18002cd73  xor     eax, eax
0x18002cd75  mov     [rbx+50h], rax
0x18002cd79  mov     [rbx+58h], rax
0x18002cd7d  mov     [rbx+60h], rax
0x18002cd81  mov     [rbx+68h], rax
0x18002cd85  add     rsp, 20h
0x18002cd89  pop     rbx
0x18002cd8a  retn
```
