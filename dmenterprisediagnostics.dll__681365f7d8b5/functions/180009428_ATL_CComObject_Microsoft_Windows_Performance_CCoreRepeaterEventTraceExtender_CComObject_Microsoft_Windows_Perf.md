# ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>(void)

- ea: `0x180009428`
- end: `0x180009462`
- name: `??1?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ`
- size: `58`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEventTraceExtenderBase *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800098e0`

## callees

- `0x18000969c`
- `0x180027010`

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
0x180009428  push    rbx
0x18000942a  sub     rsp, 20h
0x18000942e  mov     dword ptr [rcx+18h], 0C0000001h
0x180009435  lea     rax, ??_7?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::`vftable'
0x18000943c  mov     [rcx], rax
0x18000943f  mov     rbx, rcx
0x180009442  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009449  mov     rax, [rcx]
0x18000944c  mov     rax, [rax+10h]
0x180009450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009455  mov     rcx, rbx; this
0x180009458  add     rsp, 20h
0x18000945c  pop     rbx
0x18000945d  jmp     ??1CEventTraceExtenderBase@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventTraceExtenderBase::~CEventTraceExtenderBase(void)
```
