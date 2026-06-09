# HrCoTaskMemAlloc(ulong,void * *)

- ea: `0x1800304e8`
- end: `0x18003050e`
- name: `?HrCoTaskMemAlloc@@YAJKPEAPEAX@Z`
- size: `38`
- prototype: `__int64 __fastcall(SIZE_T cb, void **)`
- caller_count: `4`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024db0`
- `0x18002a1b0`
- `0x18002b7d0`
- `0x18002bd30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800304f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800304f3`

## pseudocode

```c
__int64 __fastcall HrCoTaskMemAlloc(SIZE_T cb, void **a2)
{
  void *v3; // rax

  v3 = CoTaskMemAlloc((unsigned int)cb);
  *a2 = v3;
  return v3 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x1800304e8  push    rbx
0x1800304ea  sub     rsp, 20h
0x1800304ee  mov     ecx, ecx; cb
0x1800304f0  mov     rbx, rdx
0x1800304f3  call    cs:__imp_CoTaskMemAlloc
0x1800304f9  mov     [rbx], rax
0x1800304fc  neg     rax
0x1800304ff  sbb     eax, eax
0x180030501  not     eax
0x180030503  and     eax, 8007000Eh
0x180030508  add     rsp, 20h
0x18003050c  pop     rbx
0x18003050d  retn
```
