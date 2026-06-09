# ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>(void)

- ea: `0x18002162c`
- end: `0x180021666`
- name: `??1?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ`
- size: `58`
- prototype: `void __fastcall(Microsoft::Windows::Performance::CElfImageEventTraceExtender *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800218e0`

## callees

- `0x180021804`
- `0x180026010`

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
0x18002162c  push    rbx
0x18002162e  sub     rsp, 20h
0x180021632  mov     dword ptr [rcx+18h], 0C0000001h
0x180021639  lea     rax, ??_7?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vftable'
0x180021640  mov     [rcx], rax
0x180021643  mov     rbx, rcx
0x180021646  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002164d  mov     rax, [rcx]
0x180021650  mov     rax, [rax+10h]
0x180021654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021659  mov     rcx, rbx; this
0x18002165c  add     rsp, 20h
0x180021660  pop     rbx
0x180021661  jmp     ??1CElfImageEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CElfImageEventTraceExtender::~CElfImageEventTraceExtender(void)
```
