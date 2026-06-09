# ATL::CComObject<CMSMQTriggersConfig>::`scalar deleting destructor'(uint)

- ea: `0x18000dcbc`
- end: `0x18000dcde`
- name: `??_G?$CComObject@VCMSMQTriggersConfig@@@ATL@@QEAAPEAXI@Z`
- size: `34`
- prototype: `CMSMQTriggersConfig *__fastcall(CMSMQTriggersConfig *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e570`
- `0x18000fa10`

## callees

- `0x18000dafc`

## import_xrefs

- `msvcrt!free` at `0x18000dcce`
- `msvcrt!free` at `0x18000dcce`

## pseudocode

```c
CMSMQTriggersConfig *__fastcall ATL::CComObject<CMSMQTriggersConfig>::`scalar deleting destructor'(
        CMSMQTriggersConfig *Block)
{
  ATL::CComObject<CMSMQTriggersConfig>::~CComObject<CMSMQTriggersConfig>(Block);
  free(Block);
  return Block;
}

```

## disassembly

```asm
0x18000dcbc  push    rbx
0x18000dcbe  sub     rsp, 20h
0x18000dcc2  mov     rbx, rcx
0x18000dcc5  call    ??1?$CComObject@VCMSMQTriggersConfig@@@ATL@@QEAA@XZ; ATL::CComObject<CMSMQTriggersConfig>::~CComObject<CMSMQTriggersConfig>(void)
0x18000dcca  nop
0x18000dccb  mov     rcx, rbx; Block
0x18000dcce  call    cs:__imp_free
0x18000dcd4  nop
0x18000dcd5  mov     rax, rbx
0x18000dcd8  add     rsp, 20h
0x18000dcdc  pop     rbx
0x18000dcdd  retn
```
