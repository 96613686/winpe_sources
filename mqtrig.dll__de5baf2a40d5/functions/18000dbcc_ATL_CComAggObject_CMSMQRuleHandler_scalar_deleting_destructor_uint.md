# ATL::CComAggObject<CMSMQRuleHandler>::`scalar deleting destructor'(uint)

- ea: `0x18000dbcc`
- end: `0x18000dbee`
- name: `??_G?$CComAggObject@VCMSMQRuleHandler@@@ATL@@QEAAPEAXI@Z`
- size: `34`
- prototype: `void *__fastcall(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000dffc`
- `0x18000f7c0`

## callees

- `0x18000d950`

## import_xrefs

- `msvcrt!free` at `0x18000dbde`
- `msvcrt!free` at `0x18000dbde`

## pseudocode

```c
void *__fastcall ATL::CComAggObject<CMSMQRuleHandler>::`scalar deleting destructor'(void *Block)
{
  ATL::CComAggObject<CMSMQRuleHandler>::~CComAggObject<CMSMQRuleHandler>((__int64)Block);
  free(Block);
  return Block;
}

```

## disassembly

```asm
0x18000dbcc  push    rbx
0x18000dbce  sub     rsp, 20h
0x18000dbd2  mov     rbx, rcx
0x18000dbd5  call    ??1?$CComAggObject@VCMSMQRuleHandler@@@ATL@@QEAA@XZ; ATL::CComAggObject<CMSMQRuleHandler>::~CComAggObject<CMSMQRuleHandler>(void)
0x18000dbda  nop
0x18000dbdb  mov     rcx, rbx; Block
0x18000dbde  call    cs:__imp_free
0x18000dbe4  nop
0x18000dbe5  mov     rax, rbx
0x18000dbe8  add     rsp, 20h
0x18000dbec  pop     rbx
0x18000dbed  retn
```
