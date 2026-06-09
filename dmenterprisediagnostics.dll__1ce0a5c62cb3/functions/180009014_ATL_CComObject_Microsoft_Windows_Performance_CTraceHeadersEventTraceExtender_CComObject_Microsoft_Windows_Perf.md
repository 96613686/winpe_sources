# ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>(void)

- ea: `0x180009014`
- end: `0x18000904e`
- name: `??1?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ`
- size: `58`
- prototype: `void __fastcall(Microsoft::Windows::Performance::CEventTraceExtenderBase *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800094b0`

## callees

- `0x18000920c`
- `0x180026010`

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
0x180009014  push    rbx
0x180009016  sub     rsp, 20h
0x18000901a  mov     dword ptr [rcx+18h], 0C0000001h
0x180009021  lea     rax, ??_7?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::`vftable'
0x180009028  mov     [rcx], rax
0x18000902b  mov     rbx, rcx
0x18000902e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009035  mov     rax, [rcx]
0x180009038  mov     rax, [rax+10h]
0x18000903c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009041  mov     rcx, rbx; this
0x180009044  add     rsp, 20h
0x180009048  pop     rbx
0x180009049  jmp     ??1CEventTraceExtenderBase@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventTraceExtenderBase::~CEventTraceExtenderBase(void)
```
