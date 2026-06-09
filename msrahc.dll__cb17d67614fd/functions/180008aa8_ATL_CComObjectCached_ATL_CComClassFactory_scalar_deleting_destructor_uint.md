# ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)

- ea: `0x180008aa8`
- end: `0x180008ac8`
- name: `??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z`
- size: `32`
- prototype: `void *__fastcall(void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000a220`
- `0x18000bac0`

## callees

- `0x180008904`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180008ab9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008ab9`

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
0x180008aa8  push    rbx
0x180008aaa  sub     rsp, 20h
0x180008aae  mov     rbx, rcx
0x180008ab1  call    ??1?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>(void)
0x180008ab6  mov     rcx, rbx
0x180008ab9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008abf  mov     rax, rbx
0x180008ac2  add     rsp, 20h
0x180008ac6  pop     rbx
0x180008ac7  retn
```
