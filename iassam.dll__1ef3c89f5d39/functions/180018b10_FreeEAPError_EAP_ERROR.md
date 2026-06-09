# FreeEAPError(_EAP_ERROR *)

- ea: `0x180018b10`
- end: `0x180018b41`
- name: `?FreeEAPError@@YAXPEAU_EAP_ERROR@@@Z`
- size: `49`
- prototype: `void __fastcall(struct _EAP_ERROR *)`
- caller_count: `8`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180018620`
- `0x180018fb0`
- `0x1800194b8`
- `0x18001a634`
- `0x18001ac5c`
- `0x18001ae80`
- `0x18001b084`
- `0x18001b170`

## callees

- `0x180018b10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018b22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018b2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018b22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018b2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018b3a`

## pseudocode

```c
void __fastcall FreeEAPError(struct _EAP_ERROR *a1)
{
  if ( a1 )
  {
    CoTaskMemFree(a1->pRootCauseString);
    CoTaskMemFree(a1->pRepairString);
  }
  CoTaskMemFree(a1);
}

```

## disassembly

```asm
0x180018b10  push    rbx
0x180018b12  sub     rsp, 20h
0x180018b16  mov     rbx, rcx
0x180018b19  test    rcx, rcx
0x180018b1c  jz      short loc_180018B32
0x180018b1e  mov     rcx, [rcx+48h]; pv
0x180018b22  call    cs:__imp_CoTaskMemFree
0x180018b28  mov     rcx, [rbx+50h]; pv
0x180018b2c  call    cs:__imp_CoTaskMemFree
0x180018b32  mov     rcx, rbx
0x180018b35  add     rsp, 20h
0x180018b39  pop     rbx
0x180018b3a  jmp     cs:__imp_CoTaskMemFree
```
