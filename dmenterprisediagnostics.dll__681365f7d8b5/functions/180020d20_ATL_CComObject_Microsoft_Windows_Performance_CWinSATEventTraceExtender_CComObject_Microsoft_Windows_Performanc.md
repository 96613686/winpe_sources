# ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>(void)

- ea: `0x180020d20`
- end: `0x180020d5a`
- name: `??1?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ`
- size: `58`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CWinSATEventTraceExtender *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180020dd0`

## callees

- `0x180020d60`
- `0x180027010`

## pseudocode

```c
void __fastcall ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>(
        Microsoft::Windows::Performance::CWinSATEventTraceExtender *this)
{
  *((_DWORD *)this + 6) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CWinSATEventTraceExtender::~CWinSATEventTraceExtender(this);
}

```

## disassembly

```asm
0x180020d20  push    rbx
0x180020d22  sub     rsp, 20h
0x180020d26  mov     dword ptr [rcx+18h], 0C0000001h
0x180020d2d  lea     rax, ??_7?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::`vftable'
0x180020d34  mov     [rcx], rax
0x180020d37  mov     rbx, rcx
0x180020d3a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180020d41  mov     rax, [rcx]
0x180020d44  mov     rax, [rax+10h]
0x180020d48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d4d  mov     rcx, rbx; this
0x180020d50  add     rsp, 20h
0x180020d54  pop     rbx
0x180020d55  jmp     ??1CWinSATEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CWinSATEventTraceExtender::~CWinSATEventTraceExtender(void)
```
