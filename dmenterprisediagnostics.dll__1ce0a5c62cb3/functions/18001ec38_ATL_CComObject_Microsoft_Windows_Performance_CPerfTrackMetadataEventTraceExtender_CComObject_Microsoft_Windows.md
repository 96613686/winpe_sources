# ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>(void)

- ea: `0x18001ec38`
- end: `0x18001ec72`
- name: `??1?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ`
- size: `58`
- prototype: `void __fastcall(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001ee70`

## callees

- `0x18001ed64`
- `0x180026010`

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
0x18001ec38  push    rbx
0x18001ec3a  sub     rsp, 20h
0x18001ec3e  mov     dword ptr [rcx+18h], 0C0000001h
0x18001ec45  lea     rax, ??_7?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::`vftable'
0x18001ec4c  mov     [rcx], rax
0x18001ec4f  mov     rbx, rcx
0x18001ec52  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001ec59  mov     rax, [rcx]
0x18001ec5c  mov     rax, [rax+10h]
0x18001ec60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec65  mov     rcx, rbx; this
0x18001ec68  add     rsp, 20h
0x18001ec6c  pop     rbx
0x18001ec6d  jmp     ??1CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::~CPerfTrackMetadataEventTraceExtender(void)
```
