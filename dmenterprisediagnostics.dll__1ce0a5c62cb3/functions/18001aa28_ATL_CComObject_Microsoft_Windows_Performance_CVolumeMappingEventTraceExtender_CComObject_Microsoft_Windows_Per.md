# ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>(void)

- ea: `0x18001aa28`
- end: `0x18001aa62`
- name: `??1?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ`
- size: `58`
- prototype: `void __fastcall(Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001ac90`

## callees

- `0x18001aa68`
- `0x180026010`

## pseudocode

```c
void __fastcall ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>(
        Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender *this)
{
  *((_DWORD *)this + 6) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender::~CVolumeMappingEventTraceExtender(this);
}

```

## disassembly

```asm
0x18001aa28  push    rbx
0x18001aa2a  sub     rsp, 20h
0x18001aa2e  mov     dword ptr [rcx+18h], 0C0000001h
0x18001aa35  lea     rax, ??_7?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::`vftable'
0x18001aa3c  mov     [rcx], rax
0x18001aa3f  mov     rbx, rcx
0x18001aa42  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001aa49  mov     rax, [rcx]
0x18001aa4c  mov     rax, [rax+10h]
0x18001aa50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa55  mov     rcx, rbx; this
0x18001aa58  add     rsp, 20h
0x18001aa5c  pop     rbx
0x18001aa5d  jmp     ??1CVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender::~CVolumeMappingEventTraceExtender(void)
```
