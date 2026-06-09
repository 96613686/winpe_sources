# ATL::CComAggObject<CMSMQTriggerSet>::`scalar deleting destructor'(uint)

- ea: `0x18000dbf4`
- end: `0x18000dc16`
- name: `??_G?$CComAggObject@VCMSMQTriggerSet@@@ATL@@QEAAPEAXI@Z`
- size: `34`
- prototype: `void *__fastcall(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000e0e4`
- `0x18000f810`

## callees

- `0x18000d990`

## import_xrefs

- `msvcrt!free` at `0x18000dc06`
- `msvcrt!free` at `0x18000dc06`

## pseudocode

```c
void *__fastcall ATL::CComAggObject<CMSMQTriggerSet>::`scalar deleting destructor'(void *Block)
{
  ATL::CComAggObject<CMSMQTriggerSet>::~CComAggObject<CMSMQTriggerSet>((__int64)Block);
  free(Block);
  return Block;
}

```

## disassembly

```asm
0x18000dbf4  push    rbx
0x18000dbf6  sub     rsp, 20h
0x18000dbfa  mov     rbx, rcx
0x18000dbfd  call    ??1?$CComAggObject@VCMSMQTriggerSet@@@ATL@@QEAA@XZ; ATL::CComAggObject<CMSMQTriggerSet>::~CComAggObject<CMSMQTriggerSet>(void)
0x18000dc02  nop
0x18000dc03  mov     rcx, rbx; Block
0x18000dc06  call    cs:__imp_free
0x18000dc0c  nop
0x18000dc0d  mov     rax, rbx
0x18000dc10  add     rsp, 20h
0x18000dc14  pop     rbx
0x18000dc15  retn
```
