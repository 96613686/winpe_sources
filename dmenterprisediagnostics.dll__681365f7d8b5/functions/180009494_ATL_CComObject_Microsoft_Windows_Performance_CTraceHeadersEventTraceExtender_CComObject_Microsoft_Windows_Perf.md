# ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>(void)

- ea: `0x180009494`
- end: `0x1800094ce`
- name: `??1?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ`
- size: `58`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEventTraceExtenderBase *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009960`

## callees

- `0x18000969c`
- `0x180027010`

## pseudocode

```c
void __fastcall ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>(
        Microsoft::Windows::Performance::CEventTraceExtenderBase *this)
{
  *((_DWORD *)this + 6) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CEventTraceExtenderBase::~CEventTraceExtenderBase(this);
}

```

## disassembly

```asm
0x180009494  push    rbx
0x180009496  sub     rsp, 20h
0x18000949a  mov     dword ptr [rcx+18h], 0C0000001h
0x1800094a1  lea     rax, ??_7?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::`vftable'
0x1800094a8  mov     [rcx], rax
0x1800094ab  mov     rbx, rcx
0x1800094ae  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800094b5  mov     rax, [rcx]
0x1800094b8  mov     rax, [rax+10h]
0x1800094bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094c1  mov     rcx, rbx; this
0x1800094c4  add     rsp, 20h
0x1800094c8  pop     rbx
0x1800094c9  jmp     ??1CEventTraceExtenderBase@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventTraceExtenderBase::~CEventTraceExtenderBase(void)
```
