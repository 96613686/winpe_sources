# ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>(void)

- ea: `0x180018ff0`
- end: `0x18001902a`
- name: `??1?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ`
- size: `58`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180019540`

## callees

- `0x1800191a0`
- `0x180027010`

## pseudocode

```c
void __fastcall ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this)
{
  *((_DWORD *)this + 6) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CNGenEventTraceExtender::~CNGenEventTraceExtender(this);
}

```

## disassembly

```asm
0x180018ff0  push    rbx
0x180018ff2  sub     rsp, 20h
0x180018ff6  mov     dword ptr [rcx+18h], 0C0000001h
0x180018ffd  lea     rax, ??_7?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`vftable'
0x180019004  mov     [rcx], rax
0x180019007  mov     rbx, rcx
0x18001900a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180019011  mov     rax, [rcx]
0x180019014  mov     rax, [rax+10h]
0x180019018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001901d  mov     rcx, rbx; this
0x180019020  add     rsp, 20h
0x180019024  pop     rbx
0x180019025  jmp     ??1CNGenEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CNGenEventTraceExtender::~CNGenEventTraceExtender(void)
```
