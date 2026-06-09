# ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>(void)

- ea: `0x1800186ec`
- end: `0x180018726`
- name: `??1?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ`
- size: `58`
- prototype: `void __fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180018b30`

## callees

- `0x180018894`
- `0x180026010`

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
0x1800186ec  push    rbx
0x1800186ee  sub     rsp, 20h
0x1800186f2  mov     dword ptr [rcx+18h], 0C0000001h
0x1800186f9  lea     rax, ??_7?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`vftable'
0x180018700  mov     [rcx], rax
0x180018703  mov     rbx, rcx
0x180018706  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001870d  mov     rax, [rcx]
0x180018710  mov     rax, [rax+10h]
0x180018714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018719  mov     rcx, rbx; this
0x18001871c  add     rsp, 20h
0x180018720  pop     rbx
0x180018721  jmp     ??1CNGenEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CNGenEventTraceExtender::~CNGenEventTraceExtender(void)
```
