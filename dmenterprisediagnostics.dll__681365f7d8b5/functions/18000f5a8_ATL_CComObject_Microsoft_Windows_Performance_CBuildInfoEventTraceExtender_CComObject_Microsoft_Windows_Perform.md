# ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>(void)

- ea: `0x18000f5a8`
- end: `0x18000f5e2`
- name: `??1?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ`
- size: `58`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEventTraceExtenderBase *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f600`

## callees

- `0x18000969c`
- `0x180027010`

## pseudocode

```c
void __fastcall ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>(
        Microsoft::Windows::Performance::CEventTraceExtenderBase *this)
{
  *((_DWORD *)this + 6) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CEventTraceExtenderBase::~CEventTraceExtenderBase(this);
}

```

## disassembly

```asm
0x18000f5a8  push    rbx
0x18000f5aa  sub     rsp, 20h
0x18000f5ae  mov     dword ptr [rcx+18h], 0C0000001h
0x18000f5b5  lea     rax, ??_7?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::`vftable'
0x18000f5bc  mov     [rcx], rax
0x18000f5bf  mov     rbx, rcx
0x18000f5c2  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000f5c9  mov     rax, [rcx]
0x18000f5cc  mov     rax, [rax+10h]
0x18000f5d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5d5  mov     rcx, rbx; this
0x18000f5d8  add     rsp, 20h
0x18000f5dc  pop     rbx
0x18000f5dd  jmp     ??1CEventTraceExtenderBase@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventTraceExtenderBase::~CEventTraceExtenderBase(void)
```
