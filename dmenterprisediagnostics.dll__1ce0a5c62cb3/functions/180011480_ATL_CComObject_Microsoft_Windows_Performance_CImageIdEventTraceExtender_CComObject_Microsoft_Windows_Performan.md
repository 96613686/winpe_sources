# ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>(void)

- ea: `0x180011480`
- end: `0x1800114ba`
- name: `??1?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ`
- size: `58`
- prototype: `void __fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011bc0`

## callees

- `0x18001182c`
- `0x180026010`

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
0x180011480  push    rbx
0x180011482  sub     rsp, 20h
0x180011486  mov     dword ptr [rcx+18h], 0C0000001h
0x18001148d  lea     rax, ??_7?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`vftable'
0x180011494  mov     [rcx], rax
0x180011497  mov     rbx, rcx
0x18001149a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800114a1  mov     rax, [rcx]
0x1800114a4  mov     rax, [rax+10h]
0x1800114a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114ad  mov     rcx, rbx; this
0x1800114b0  add     rsp, 20h
0x1800114b4  pop     rbx
0x1800114b5  jmp     ??1CImageIdEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CImageIdEventTraceExtender::~CImageIdEventTraceExtender(void)
```
