# ATL::CComAggObject<CMSMQPropertyBag>::~CComAggObject<CMSMQPropertyBag>(void)

- ea: `0x18000d910`
- end: `0x18000d948`
- name: `??1?$CComAggObject@VCMSMQPropertyBag@@@ATL@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000dba4`

## callees

- `0x180003198`
- `0x18000fab4`

## pseudocode

```c
void __fastcall ATL::CComAggObject<CMSMQPropertyBag>::~CComAggObject<CMSMQPropertyBag>(__int64 a1)
{
  *(_QWORD *)a1 = &ATL::CComAggObject<CMSMQPropertyBag>::`vftable';
  *(_DWORD *)(a1 + 8) = 1;
  ATL::CComPtr<IUnknown>::Release(a1 + 40);
  _InterlockedDecrement(&dword_18002CFF8);
  CMSMQPropertyBag::~CMSMQPropertyBag((CMSMQPropertyBag *)(a1 + 16));
}

```

## disassembly

```asm
0x18000d910  push    rbx
0x18000d912  sub     rsp, 20h
0x18000d916  mov     rbx, rcx
0x18000d919  lea     rax, ??_7?$CComAggObject@VCMSMQPropertyBag@@@ATL@@6B@; const ATL::CComAggObject<CMSMQPropertyBag>::`vftable'
0x18000d920  mov     [rcx], rax
0x18000d923  mov     dword ptr [rcx+8], 1
0x18000d92a  add     rcx, 28h ; '('
0x18000d92e  call    ?Release@?$CComPtr@UIUnknown@@@ATL@@QEAAXXZ; ATL::CComPtr<IUnknown>::Release(void)
0x18000d933  lock dec cs:dword_18002CFF8
0x18000d93a  lea     rcx, [rbx+10h]; this
0x18000d93e  add     rsp, 20h
0x18000d942  pop     rbx
0x18000d943  jmp     ??1CMSMQPropertyBag@@QEAA@XZ; CMSMQPropertyBag::~CMSMQPropertyBag(void)
```
