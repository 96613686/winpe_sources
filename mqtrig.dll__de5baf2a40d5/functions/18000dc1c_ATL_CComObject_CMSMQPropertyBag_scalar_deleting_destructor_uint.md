# ATL::CComObject<CMSMQPropertyBag>::`scalar deleting destructor'(uint)

- ea: `0x18000dc1c`
- end: `0x18000dc3e`
- name: `??_G?$CComObject@VCMSMQPropertyBag@@@ATL@@QEAAPEAXI@Z`
- size: `34`
- prototype: `CMSMQPropertyBag *__fastcall(CMSMQPropertyBag *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000e1cc`
- `0x18000f890`

## callees

- `0x18000d9d4`

## import_xrefs

- `msvcrt!free` at `0x18000dc2e`
- `msvcrt!free` at `0x18000dc2e`

## pseudocode

```c
CMSMQPropertyBag *__fastcall ATL::CComObject<CMSMQPropertyBag>::`scalar deleting destructor'(CMSMQPropertyBag *Block)
{
  ATL::CComObject<CMSMQPropertyBag>::~CComObject<CMSMQPropertyBag>(Block);
  free(Block);
  return Block;
}

```

## disassembly

```asm
0x18000dc1c  push    rbx
0x18000dc1e  sub     rsp, 20h
0x18000dc22  mov     rbx, rcx
0x18000dc25  call    ??1?$CComObject@VCMSMQPropertyBag@@@ATL@@QEAA@XZ; ATL::CComObject<CMSMQPropertyBag>::~CComObject<CMSMQPropertyBag>(void)
0x18000dc2a  nop
0x18000dc2b  mov     rcx, rbx; Block
0x18000dc2e  call    cs:__imp_free
0x18000dc34  nop
0x18000dc35  mov     rax, rbx
0x18000dc38  add     rsp, 20h
0x18000dc3c  pop     rbx
0x18000dc3d  retn
```
