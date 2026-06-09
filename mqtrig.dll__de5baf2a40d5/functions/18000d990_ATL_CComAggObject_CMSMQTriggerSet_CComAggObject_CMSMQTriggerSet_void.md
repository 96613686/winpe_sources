# ATL::CComAggObject<CMSMQTriggerSet>::~CComAggObject<CMSMQTriggerSet>(void)

- ea: `0x18000d990`
- end: `0x18000d9cb`
- name: `??1?$CComAggObject@VCMSMQTriggerSet@@@ATL@@QEAA@XZ`
- size: `59`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000dbf4`

## callees

- `0x18000fab4`
- `0x1800104f8`

## pseudocode

```c
void __fastcall ATL::CComAggObject<CMSMQTriggerSet>::~CComAggObject<CMSMQTriggerSet>(__int64 a1)
{
  *(_QWORD *)a1 = &ATL::CComAggObject<CMSMQTriggerSet>::`vftable';
  *(_DWORD *)(a1 + 8) = 1;
  ATL::CComPtr<IUnknown>::Release(a1 + 1208);
  _InterlockedDecrement(&dword_18002CFF8);
  CMSMQTriggerSet::~CMSMQTriggerSet((CMSMQTriggerSet *)(a1 + 24));
}

```

## disassembly

```asm
0x18000d990  push    rbx
0x18000d992  sub     rsp, 20h
0x18000d996  mov     rbx, rcx
0x18000d999  lea     rax, ??_7?$CComAggObject@VCMSMQTriggerSet@@@ATL@@6B@; const ATL::CComAggObject<CMSMQTriggerSet>::`vftable'
0x18000d9a0  mov     [rcx], rax
0x18000d9a3  mov     dword ptr [rcx+8], 1
0x18000d9aa  add     rcx, 4B8h
0x18000d9b1  call    ?Release@?$CComPtr@UIUnknown@@@ATL@@QEAAXXZ; ATL::CComPtr<IUnknown>::Release(void)
0x18000d9b6  lock dec cs:dword_18002CFF8
0x18000d9bd  lea     rcx, [rbx+18h]; this
0x18000d9c1  add     rsp, 20h
0x18000d9c5  pop     rbx
0x18000d9c6  jmp     ??1CMSMQTriggerSet@@QEAA@XZ; CMSMQTriggerSet::~CMSMQTriggerSet(void)
```
