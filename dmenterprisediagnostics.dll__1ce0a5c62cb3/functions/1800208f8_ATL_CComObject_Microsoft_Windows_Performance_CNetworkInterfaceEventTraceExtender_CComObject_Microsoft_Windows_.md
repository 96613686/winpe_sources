# ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>(void)

- ea: `0x1800208f8`
- end: `0x180020932`
- name: `??1?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ`
- size: `58`
- prototype: `void __fastcall(Microsoft::Windows::Performance::CEventTraceExtenderBase *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180020940`

## callees

- `0x18000920c`
- `0x180026010`

## pseudocode

```c
void __fastcall ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>(
        Microsoft::Windows::Performance::CEventTraceExtenderBase *this)
{
  *((_DWORD *)this + 6) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CEventTraceExtenderBase::~CEventTraceExtenderBase(this);
}

```

## disassembly

```asm
0x1800208f8  push    rbx
0x1800208fa  sub     rsp, 20h
0x1800208fe  mov     dword ptr [rcx+18h], 0C0000001h
0x180020905  lea     rax, ??_7?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::`vftable'
0x18002090c  mov     [rcx], rax
0x18002090f  mov     rbx, rcx
0x180020912  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180020919  mov     rax, [rcx]
0x18002091c  mov     rax, [rax+10h]
0x180020920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020925  mov     rcx, rbx; this
0x180020928  add     rsp, 20h
0x18002092c  pop     rbx
0x18002092d  jmp     ??1CEventTraceExtenderBase@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventTraceExtenderBase::~CEventTraceExtenderBase(void)
```
