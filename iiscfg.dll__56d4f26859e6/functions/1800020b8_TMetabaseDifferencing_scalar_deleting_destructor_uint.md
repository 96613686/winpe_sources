# TMetabaseDifferencing::`scalar deleting destructor'(uint)

- ea: `0x1800020b8`
- end: `0x1800020d8`
- name: `??_GTMetabaseDifferencing@@QEAAPEAXI@Z`
- size: `32`
- prototype: `void *__fastcall(TMetabaseDifferencing *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180002970`
- `0x180014f20`

## callees

- `0x180014200`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800020c9`
- `ole32!CoTaskMemFree` at `0x1800020c9`

## pseudocode

```c
TMetabaseDifferencing *__fastcall TMetabaseDifferencing::`scalar deleting destructor'(TMetabaseDifferencing *this)
{
  TMetabaseDifferencing::~TMetabaseDifferencing(this);
  CoTaskMemFree(this);
  return this;
}

```

## disassembly

```asm
0x1800020b8  push    rbx
0x1800020ba  sub     rsp, 20h
0x1800020be  mov     rbx, rcx
0x1800020c1  call    ??1TMetabaseDifferencing@@QEAA@XZ; TMetabaseDifferencing::~TMetabaseDifferencing(void)
0x1800020c6  mov     rcx, rbx; pv
0x1800020c9  call    cs:__imp_CoTaskMemFree
0x1800020cf  mov     rax, rbx
0x1800020d2  add     rsp, 20h
0x1800020d6  pop     rbx
0x1800020d7  retn
```
