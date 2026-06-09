# ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>(void)

- ea: `0x180022368`
- end: `0x1800223a2`
- name: `??1?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ`
- size: `58`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CElfImageEventTraceExtender *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180022630`

## callees

- `0x180022544`
- `0x180027010`

## pseudocode

```c
void __fastcall ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>(
        Microsoft::Windows::Performance::CElfImageEventTraceExtender *this)
{
  *((_DWORD *)this + 6) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CElfImageEventTraceExtender::~CElfImageEventTraceExtender(this);
}

```

## disassembly

```asm
0x180022368  push    rbx
0x18002236a  sub     rsp, 20h
0x18002236e  mov     dword ptr [rcx+18h], 0C0000001h
0x180022375  lea     rax, ??_7?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vftable'
0x18002237c  mov     [rcx], rax
0x18002237f  mov     rbx, rcx
0x180022382  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180022389  mov     rax, [rcx]
0x18002238c  mov     rax, [rax+10h]
0x180022390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022395  mov     rcx, rbx; this
0x180022398  add     rsp, 20h
0x18002239c  pop     rbx
0x18002239d  jmp     ??1CElfImageEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CElfImageEventTraceExtender::~CElfImageEventTraceExtender(void)
```
