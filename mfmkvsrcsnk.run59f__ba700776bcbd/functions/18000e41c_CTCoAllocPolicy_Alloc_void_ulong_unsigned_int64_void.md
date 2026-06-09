# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x18000e41c`
- end: `0x18000e44a`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `46`
- prototype: `static int(void *, unsigned int, unsigned __int64, void **)`
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180011720`
- `0x18005555c`
- `0x180065424`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e428`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e428`

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
0x18000e41c  push    rbx
0x18000e41e  sub     rsp, 20h
0x18000e422  mov     rcx, r8; cb
0x18000e425  mov     rbx, r9
0x18000e428  call    cs:__imp_CoTaskMemAlloc
0x18000e42f  nop     dword ptr [rax+rax+00h]
0x18000e434  mov     [rbx], rax
0x18000e437  neg     rax
0x18000e43a  sbb     eax, eax
0x18000e43c  not     eax
0x18000e43e  and     eax, 8007000Eh
0x18000e443  add     rsp, 20h
0x18000e447  pop     rbx
0x18000e448  retn
```
