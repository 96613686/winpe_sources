# ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)

- ea: `0x1800036c8`
- end: `0x1800036e8`
- name: `??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z`
- size: `32`
- prototype: `void *__fastcall(void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004bf0`
- `0x180006280`

## callees

- `0x180003190`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800036d9`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800036d9`

## pseudocode

```c
void *__fastcall ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(void *a1)
{
  ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>((__int64)a1);
  operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1800036c8  push    rbx
0x1800036ca  sub     rsp, 20h
0x1800036ce  mov     rbx, rcx
0x1800036d1  call    ??1?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>(void)
0x1800036d6  mov     rcx, rbx
0x1800036d9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800036df  mov     rax, rbx
0x1800036e2  add     rsp, 20h
0x1800036e6  pop     rbx
0x1800036e7  retn
```
