# ATL::CComHeapPtr<_IASATTRIBUTE *>::~CComHeapPtr<_IASATTRIBUTE *>(void)

- ea: `0x1800129dc`
- end: `0x1800129fb`
- name: `??1?$CComHeapPtr@PEAU_IASATTRIBUTE@@@ATL@@QEAA@XZ`
- size: `31`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800133bc`
- `0x18002c2b7`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800129e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800129e8`

## pseudocode

```c
void __fastcall ATL::CComHeapPtr<_IASATTRIBUTE *>::~CComHeapPtr<_IASATTRIBUTE *>(LPVOID *a1)
{
  CoTaskMemFree(*a1);
  *a1 = 0;
}

```

## disassembly

```asm
0x1800129dc  push    rbx
0x1800129de  sub     rsp, 20h
0x1800129e2  mov     rbx, rcx
0x1800129e5  mov     rcx, [rcx]; pv
0x1800129e8  call    cs:__imp_CoTaskMemFree
0x1800129ee  mov     qword ptr [rbx], 0
0x1800129f5  add     rsp, 20h
0x1800129f9  pop     rbx
0x1800129fa  retn
```
