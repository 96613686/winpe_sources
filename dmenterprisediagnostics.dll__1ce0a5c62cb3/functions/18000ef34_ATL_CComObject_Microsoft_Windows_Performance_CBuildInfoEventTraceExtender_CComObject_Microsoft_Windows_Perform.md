# ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>(void)

- ea: `0x18000ef34`
- end: `0x18000ef6e`
- name: `??1?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ`
- size: `58`
- prototype: `void __fastcall(Microsoft::Windows::Performance::CEventTraceExtenderBase *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ef80`

## callees

- `0x18000920c`
- `0x180026010`

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
0x18000ef34  push    rbx
0x18000ef36  sub     rsp, 20h
0x18000ef3a  mov     dword ptr [rcx+18h], 0C0000001h
0x18000ef41  lea     rax, ??_7?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::`vftable'
0x18000ef48  mov     [rcx], rax
0x18000ef4b  mov     rbx, rcx
0x18000ef4e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000ef55  mov     rax, [rcx]
0x18000ef58  mov     rax, [rax+10h]
0x18000ef5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef61  mov     rcx, rbx; this
0x18000ef64  add     rsp, 20h
0x18000ef68  pop     rbx
0x18000ef69  jmp     ??1CEventTraceExtenderBase@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventTraceExtenderBase::~CEventTraceExtenderBase(void)
```
