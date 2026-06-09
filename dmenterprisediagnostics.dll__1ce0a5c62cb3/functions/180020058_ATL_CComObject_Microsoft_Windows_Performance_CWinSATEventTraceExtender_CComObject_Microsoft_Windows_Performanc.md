# ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>(void)

- ea: `0x180020058`
- end: `0x180020092`
- name: `??1?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ`
- size: `58`
- prototype: `void __fastcall(Microsoft::Windows::Performance::CWinSATEventTraceExtender *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800200f0`

## callees

- `0x180020098`
- `0x180026010`

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
0x180020058  push    rbx
0x18002005a  sub     rsp, 20h
0x18002005e  mov     dword ptr [rcx+18h], 0C0000001h
0x180020065  lea     rax, ??_7?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::`vftable'
0x18002006c  mov     [rcx], rax
0x18002006f  mov     rbx, rcx
0x180020072  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180020079  mov     rax, [rcx]
0x18002007c  mov     rax, [rax+10h]
0x180020080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020085  mov     rcx, rbx; this
0x180020088  add     rsp, 20h
0x18002008c  pop     rbx
0x18002008d  jmp     ??1CWinSATEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CWinSATEventTraceExtender::~CWinSATEventTraceExtender(void)
```
