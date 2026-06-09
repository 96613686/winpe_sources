# ATL::CComObject<CMSMQTriggerSet>::`scalar deleting destructor'(uint)

- ea: `0x18000dc94`
- end: `0x18000dcb6`
- name: `??_G?$CComObject@VCMSMQTriggerSet@@@ATL@@QEAAPEAXI@Z`
- size: `34`
- prototype: `CMSMQTriggerSet *__fastcall(CMSMQTriggerSet *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000e488`
- `0x18000f9b0`

## callees

- `0x18000dab0`

## import_xrefs

- `msvcrt!free` at `0x18000dca6`
- `msvcrt!free` at `0x18000dca6`

## pseudocode

```c
CMSMQTriggerSet *__fastcall ATL::CComObject<CMSMQTriggerSet>::`scalar deleting destructor'(CMSMQTriggerSet *Block)
{
  ATL::CComObject<CMSMQTriggerSet>::~CComObject<CMSMQTriggerSet>(Block);
  free(Block);
  return Block;
}

```

## disassembly

```asm
0x18000dc94  push    rbx
0x18000dc96  sub     rsp, 20h
0x18000dc9a  mov     rbx, rcx
0x18000dc9d  call    ??1?$CComObject@VCMSMQTriggerSet@@@ATL@@QEAA@XZ; ATL::CComObject<CMSMQTriggerSet>::~CComObject<CMSMQTriggerSet>(void)
0x18000dca2  nop
0x18000dca3  mov     rcx, rbx; Block
0x18000dca6  call    cs:__imp_free
0x18000dcac  nop
0x18000dcad  mov     rax, rbx
0x18000dcb0  add     rsp, 20h
0x18000dcb4  pop     rbx
0x18000dcb5  retn
```
