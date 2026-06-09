# ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>(void)

- ea: `0x180008fa8`
- end: `0x180008fe2`
- name: `??1?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ`
- size: `58`
- prototype: `void __fastcall(Microsoft::Windows::Performance::CEventTraceExtenderBase *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009430`

## callees

- `0x18000920c`
- `0x180026010`

## pseudocode

```c
void __fastcall ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>(
        Microsoft::Windows::Performance::CEventTraceExtenderBase *this)
{
  *((_DWORD *)this + 6) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CEventTraceExtenderBase::~CEventTraceExtenderBase(this);
}

```

## disassembly

```asm
0x180008fa8  push    rbx
0x180008faa  sub     rsp, 20h
0x180008fae  mov     dword ptr [rcx+18h], 0C0000001h
0x180008fb5  lea     rax, ??_7?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::`vftable'
0x180008fbc  mov     [rcx], rax
0x180008fbf  mov     rbx, rcx
0x180008fc2  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008fc9  mov     rax, [rcx]
0x180008fcc  mov     rax, [rax+10h]
0x180008fd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fd5  mov     rcx, rbx; this
0x180008fd8  add     rsp, 20h
0x180008fdc  pop     rbx
0x180008fdd  jmp     ??1CEventTraceExtenderBase@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventTraceExtenderBase::~CEventTraceExtenderBase(void)
```
