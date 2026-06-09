# ATL::CComObject<CMSMQRuleSet>::`scalar deleting destructor'(uint)

- ea: `0x18000dc6c`
- end: `0x18000dc8e`
- name: `??_G?$CComObject@VCMSMQRuleSet@@@ATL@@QEAAPEAXI@Z`
- size: `34`
- prototype: `CMSMQRuleSet *__fastcall(CMSMQRuleSet *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000e388`
- `0x18000f950`

## callees

- `0x18000da64`

## import_xrefs

- `msvcrt!free` at `0x18000dc7e`
- `msvcrt!free` at `0x18000dc7e`

## pseudocode

```c
CMSMQRuleSet *__fastcall ATL::CComObject<CMSMQRuleSet>::`scalar deleting destructor'(CMSMQRuleSet *Block)
{
  ATL::CComObject<CMSMQRuleSet>::~CComObject<CMSMQRuleSet>(Block);
  free(Block);
  return Block;
}

```

## disassembly

```asm
0x18000dc6c  push    rbx
0x18000dc6e  sub     rsp, 20h
0x18000dc72  mov     rbx, rcx
0x18000dc75  call    ??1?$CComObject@VCMSMQRuleSet@@@ATL@@QEAA@XZ; ATL::CComObject<CMSMQRuleSet>::~CComObject<CMSMQRuleSet>(void)
0x18000dc7a  nop
0x18000dc7b  mov     rcx, rbx; Block
0x18000dc7e  call    cs:__imp_free
0x18000dc84  nop
0x18000dc85  mov     rax, rbx
0x18000dc88  add     rsp, 20h
0x18000dc8c  pop     rbx
0x18000dc8d  retn
```
