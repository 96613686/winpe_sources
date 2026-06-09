# CShareable::_DeleteShareCreationStructData(tagSM_SHARECREATIONSTRUCT *)

- ea: `0x18005fe94`
- end: `0x18005feca`
- name: `?_DeleteShareCreationStructData@CShareable@@IEAAXPEAUtagSM_SHARECREATIONSTRUCT@@@Z`
- size: `54`
- prototype: `void __fastcall(CShareable *__hidden this, struct tagSM_SHARECREATIONSTRUCT *)`
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005f5e0`
- `0x18005fb28`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005fea1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005feab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005feb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005fea1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005feab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005feb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005fec3`

## pseudocode

```c
void __fastcall CShareable::_DeleteShareCreationStructData(CShareable *this, LPVOID *a2)
{
  CoTaskMemFree(a2[1]);
  CoTaskMemFree(a2[2]);
  CoTaskMemFree(*a2);
  CoTaskMemFree(a2[4]);
}

```

## disassembly

```asm
0x18005fe94  push    rbx
0x18005fe96  sub     rsp, 20h
0x18005fe9a  mov     rcx, [rdx+8]; pv
0x18005fe9e  mov     rbx, rdx
0x18005fea1  call    cs:__imp_CoTaskMemFree
0x18005fea7  mov     rcx, [rbx+10h]; pv
0x18005feab  call    cs:__imp_CoTaskMemFree
0x18005feb1  mov     rcx, [rbx]; pv
0x18005feb4  call    cs:__imp_CoTaskMemFree
0x18005feba  mov     rcx, [rbx+20h]
0x18005febe  add     rsp, 20h
0x18005fec2  pop     rbx
0x18005fec3  jmp     cs:__imp_CoTaskMemFree
```
