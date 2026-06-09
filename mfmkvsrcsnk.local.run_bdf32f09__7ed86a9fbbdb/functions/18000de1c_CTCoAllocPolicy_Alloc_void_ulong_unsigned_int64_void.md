# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x18000de1c`
- end: `0x18000de43`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `39`
- prototype: `static int(void *, unsigned int, unsigned __int64, void **)`
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180010fd0`
- `0x1800531c8`
- `0x180062a04`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000de28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000de28`

## pseudocode

```c
__int64 __fastcall CTCoAllocPolicy::Alloc(void *a1, __int64 a2, SIZE_T a3, void **a4)
{
  void *v5; // rax

  v5 = CoTaskMemAlloc(a3);
  *a4 = v5;
  return v5 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x18000de1c  push    rbx
0x18000de1e  sub     rsp, 20h
0x18000de22  mov     rcx, r8; cb
0x18000de25  mov     rbx, r9
0x18000de28  call    cs:__imp_CoTaskMemAlloc
0x18000de2e  mov     [rbx], rax
0x18000de31  neg     rax
0x18000de34  sbb     eax, eax
0x18000de36  not     eax
0x18000de38  and     eax, 8007000Eh
0x18000de3d  add     rsp, 20h
0x18000de41  pop     rbx
0x18000de42  retn
```
