# FreeEAPMethodInfo(_EAP_METHOD_INFO *)

- ea: `0x180018b48`
- end: `0x180018b82`
- name: `?FreeEAPMethodInfo@@YAXPEAU_EAP_METHOD_INFO@@@Z`
- size: `58`
- prototype: `void __fastcall(struct _EAP_METHOD_INFO *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018620`
- `0x180018b48`

## callees

- `0x180018b48`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018b5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018b64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018b5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018b64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018b7b`

## pseudocode

```c
void __fastcall FreeEAPMethodInfo(struct _EAP_METHOD_INFO *a1)
{
  if ( a1 )
  {
    CoTaskMemFree(a1->pwszAuthorName);
    CoTaskMemFree(a1->pwszFriendlyName);
    FreeEAPMethodInfo(a1->pInnerMethodInfo);
  }
  CoTaskMemFree(a1);
}

```

## disassembly

```asm
0x180018b48  push    rbx
0x180018b4a  sub     rsp, 20h
0x180018b4e  mov     rbx, rcx
0x180018b51  test    rcx, rcx
0x180018b54  jz      short loc_180018B73
0x180018b56  mov     rcx, [rcx+10h]; pv
0x180018b5a  call    cs:__imp_CoTaskMemFree
0x180018b60  mov     rcx, [rbx+18h]; pv
0x180018b64  call    cs:__imp_CoTaskMemFree
0x180018b6a  mov     rcx, [rbx+28h]; struct _EAP_METHOD_INFO *
0x180018b6e  call    ?FreeEAPMethodInfo@@YAXPEAU_EAP_METHOD_INFO@@@Z; FreeEAPMethodInfo(_EAP_METHOD_INFO *)
0x180018b73  mov     rcx, rbx
0x180018b76  add     rsp, 20h
0x180018b7a  pop     rbx
0x180018b7b  jmp     cs:__imp_CoTaskMemFree
```
