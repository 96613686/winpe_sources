# ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>(void)

- ea: `0x18001b4dc`
- end: `0x18001b516`
- name: `??1?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ`
- size: `58`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001b740`

## callees

- `0x18001b51c`
- `0x180027010`

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
0x18001b4dc  push    rbx
0x18001b4de  sub     rsp, 20h
0x18001b4e2  mov     dword ptr [rcx+18h], 0C0000001h
0x18001b4e9  lea     rax, ??_7?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::`vftable'
0x18001b4f0  mov     [rcx], rax
0x18001b4f3  mov     rbx, rcx
0x18001b4f6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001b4fd  mov     rax, [rcx]
0x18001b500  mov     rax, [rax+10h]
0x18001b504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b509  mov     rcx, rbx; this
0x18001b50c  add     rsp, 20h
0x18001b510  pop     rbx
0x18001b511  jmp     ??1CVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender::~CVolumeMappingEventTraceExtender(void)
```
