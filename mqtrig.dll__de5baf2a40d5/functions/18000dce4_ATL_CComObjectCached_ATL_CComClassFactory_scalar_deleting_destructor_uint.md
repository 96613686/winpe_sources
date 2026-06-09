# ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)

- ea: `0x18000dce4`
- end: `0x18000dd06`
- name: `??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z`
- size: `34`
- prototype: `void *__fastcall(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000e690`
- `0x18000fa70`

## callees

- `0x18000db44`

## import_xrefs

- `msvcrt!free` at `0x18000dcf6`
- `msvcrt!free` at `0x18000dcf6`

## pseudocode

```c
void *__fastcall ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(void *Block)
{
  ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>((__int64)Block);
  free(Block);
  return Block;
}

```

## disassembly

```asm
0x18000dce4  push    rbx
0x18000dce6  sub     rsp, 20h
0x18000dcea  mov     rbx, rcx
0x18000dced  call    ??1?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>(void)
0x18000dcf2  nop
0x18000dcf3  mov     rcx, rbx; Block
0x18000dcf6  call    cs:__imp_free
0x18000dcfc  nop
0x18000dcfd  mov     rax, rbx
0x18000dd00  add     rsp, 20h
0x18000dd04  pop     rbx
0x18000dd05  retn
```
