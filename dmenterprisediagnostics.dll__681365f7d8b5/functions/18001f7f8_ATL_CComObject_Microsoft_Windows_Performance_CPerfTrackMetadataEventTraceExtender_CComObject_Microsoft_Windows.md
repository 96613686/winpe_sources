# ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>(void)

- ea: `0x18001f7f8`
- end: `0x18001f832`
- name: `??1?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ`
- size: `58`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001fa60`

## callees

- `0x18001f934`
- `0x180027010`

## pseudocode

```c
void __fastcall ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>(
        Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *this)
{
  *((_DWORD *)this + 6) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::~CPerfTrackMetadataEventTraceExtender(this);
}

```

## disassembly

```asm
0x18001f7f8  push    rbx
0x18001f7fa  sub     rsp, 20h
0x18001f7fe  mov     dword ptr [rcx+18h], 0C0000001h
0x18001f805  lea     rax, ??_7?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::`vftable'
0x18001f80c  mov     [rcx], rax
0x18001f80f  mov     rbx, rcx
0x18001f812  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001f819  mov     rax, [rcx]
0x18001f81c  mov     rax, [rax+10h]
0x18001f820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f825  mov     rcx, rbx; this
0x18001f828  add     rsp, 20h
0x18001f82c  pop     rbx
0x18001f82d  jmp     ??1CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::~CPerfTrackMetadataEventTraceExtender(void)
```
