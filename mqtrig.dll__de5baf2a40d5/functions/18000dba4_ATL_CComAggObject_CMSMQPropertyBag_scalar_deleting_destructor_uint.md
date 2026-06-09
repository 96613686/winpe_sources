# ATL::CComAggObject<CMSMQPropertyBag>::`scalar deleting destructor'(uint)

- ea: `0x18000dba4`
- end: `0x18000dbc6`
- name: `??_G?$CComAggObject@VCMSMQPropertyBag@@@ATL@@QEAAPEAXI@Z`
- size: `34`
- prototype: `void *__fastcall(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000df28`
- `0x18000f770`

## callees

- `0x18000d910`

## import_xrefs

- `msvcrt!free` at `0x18000dbb6`
- `msvcrt!free` at `0x18000dbb6`

## pseudocode

```c
void *__fastcall ATL::CComAggObject<CMSMQPropertyBag>::`scalar deleting destructor'(void *Block)
{
  ATL::CComAggObject<CMSMQPropertyBag>::~CComAggObject<CMSMQPropertyBag>((__int64)Block);
  free(Block);
  return Block;
}

```

## disassembly

```asm
0x18000dba4  push    rbx
0x18000dba6  sub     rsp, 20h
0x18000dbaa  mov     rbx, rcx
0x18000dbad  call    ??1?$CComAggObject@VCMSMQPropertyBag@@@ATL@@QEAA@XZ; ATL::CComAggObject<CMSMQPropertyBag>::~CComAggObject<CMSMQPropertyBag>(void)
0x18000dbb2  nop
0x18000dbb3  mov     rcx, rbx; Block
0x18000dbb6  call    cs:__imp_free
0x18000dbbc  nop
0x18000dbbd  mov     rax, rbx
0x18000dbc0  add     rsp, 20h
0x18000dbc4  pop     rbx
0x18000dbc5  retn
```
