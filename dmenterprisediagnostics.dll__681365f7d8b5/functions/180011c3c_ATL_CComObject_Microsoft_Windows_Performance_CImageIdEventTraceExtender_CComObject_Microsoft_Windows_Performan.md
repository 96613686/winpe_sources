# ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>(void)

- ea: `0x180011c3c`
- end: `0x180011c76`
- name: `??1?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ`
- size: `58`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800123c0`

## callees

- `0x180011ff4`
- `0x180027010`

## pseudocode

```c
void __fastcall ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>(
        Microsoft::Windows::Performance::CImageIdEventTraceExtender *this)
{
  *((_DWORD *)this + 6) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CImageIdEventTraceExtender::~CImageIdEventTraceExtender(this);
}

```

## disassembly

```asm
0x180011c3c  push    rbx
0x180011c3e  sub     rsp, 20h
0x180011c42  mov     dword ptr [rcx+18h], 0C0000001h
0x180011c49  lea     rax, ??_7?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`vftable'
0x180011c50  mov     [rcx], rax
0x180011c53  mov     rbx, rcx
0x180011c56  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180011c5d  mov     rax, [rcx]
0x180011c60  mov     rax, [rax+10h]
0x180011c64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c69  mov     rcx, rbx; this
0x180011c6c  add     rsp, 20h
0x180011c70  pop     rbx
0x180011c71  jmp     ??1CImageIdEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CImageIdEventTraceExtender::~CImageIdEventTraceExtender(void)
```
