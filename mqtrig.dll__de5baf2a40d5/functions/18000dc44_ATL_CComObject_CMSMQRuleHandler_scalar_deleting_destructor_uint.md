# ATL::CComObject<CMSMQRuleHandler>::`scalar deleting destructor'(uint)

- ea: `0x18000dc44`
- end: `0x18000dc66`
- name: `??_G?$CComObject@VCMSMQRuleHandler@@@ATL@@QEAAPEAXI@Z`
- size: `34`
- prototype: `CMSMQRuleHandler *__fastcall(CMSMQRuleHandler *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e2a0`
- `0x18000f8f0`

## callees

- `0x18000da1c`

## import_xrefs

- `msvcrt!free` at `0x18000dc56`
- `msvcrt!free` at `0x18000dc56`

## pseudocode

```c
CMSMQRuleHandler *__fastcall ATL::CComObject<CMSMQRuleHandler>::`scalar deleting destructor'(CMSMQRuleHandler *Block)
{
  ATL::CComObject<CMSMQRuleHandler>::~CComObject<CMSMQRuleHandler>(Block);
  free(Block);
  return Block;
}

```

## disassembly

```asm
0x18000dc44  push    rbx
0x18000dc46  sub     rsp, 20h
0x18000dc4a  mov     rbx, rcx
0x18000dc4d  call    ??1?$CComObject@VCMSMQRuleHandler@@@ATL@@QEAA@XZ; ATL::CComObject<CMSMQRuleHandler>::~CComObject<CMSMQRuleHandler>(void)
0x18000dc52  nop
0x18000dc53  mov     rcx, rbx; Block
0x18000dc56  call    cs:__imp_free
0x18000dc5c  nop
0x18000dc5d  mov     rax, rbx
0x18000dc60  add     rsp, 20h
0x18000dc64  pop     rbx
0x18000dc65  retn
```
