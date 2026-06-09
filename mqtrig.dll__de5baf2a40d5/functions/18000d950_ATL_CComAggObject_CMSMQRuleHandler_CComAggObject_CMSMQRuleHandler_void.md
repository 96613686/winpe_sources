# ATL::CComAggObject<CMSMQRuleHandler>::~CComAggObject<CMSMQRuleHandler>(void)

- ea: `0x18000d950`
- end: `0x18000d988`
- name: `??1?$CComAggObject@VCMSMQRuleHandler@@@ATL@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000dbcc`

## callees

- `0x18000561c`
- `0x18000fab4`

## pseudocode

```c
void __fastcall ATL::CComAggObject<CMSMQRuleHandler>::~CComAggObject<CMSMQRuleHandler>(__int64 a1)
{
  *(_QWORD *)a1 = &ATL::CComAggObject<CMSMQRuleHandler>::`vftable';
  *(_DWORD *)(a1 + 8) = 1;
  ATL::CComPtr<IUnknown>::Release(a1 + 96);
  _InterlockedDecrement(&dword_18002CFF8);
  CMSMQRuleHandler::~CMSMQRuleHandler((CMSMQRuleHandler *)(a1 + 24));
}

```

## disassembly

```asm
0x18000d950  push    rbx
0x18000d952  sub     rsp, 20h
0x18000d956  mov     rbx, rcx
0x18000d959  lea     rax, ??_7?$CComAggObject@VCMSMQRuleHandler@@@ATL@@6B@; const ATL::CComAggObject<CMSMQRuleHandler>::`vftable'
0x18000d960  mov     [rcx], rax
0x18000d963  mov     dword ptr [rcx+8], 1
0x18000d96a  add     rcx, 60h ; '`'
0x18000d96e  call    ?Release@?$CComPtr@UIUnknown@@@ATL@@QEAAXXZ; ATL::CComPtr<IUnknown>::Release(void)
0x18000d973  lock dec cs:dword_18002CFF8
0x18000d97a  lea     rcx, [rbx+18h]; this
0x18000d97e  add     rsp, 20h
0x18000d982  pop     rbx
0x18000d983  jmp     ??1CMSMQRuleHandler@@QEAA@XZ; CMSMQRuleHandler::~CMSMQRuleHandler(void)
```
