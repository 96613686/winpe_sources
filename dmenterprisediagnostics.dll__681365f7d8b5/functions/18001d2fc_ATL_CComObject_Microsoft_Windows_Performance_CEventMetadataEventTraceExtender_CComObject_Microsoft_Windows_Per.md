# ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>(void)

- ea: `0x18001d2fc`
- end: `0x18001d336`
- name: `??1?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ`
- size: `58`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001d7d0`

## callees

- `0x18001d54c`
- `0x180027010`

## pseudocode

```c
void __fastcall ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>(
        Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *this)
{
  *((_DWORD *)this + 6) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::~CEventMetadataEventTraceExtender(this);
}

```

## disassembly

```asm
0x18001d2fc  push    rbx
0x18001d2fe  sub     rsp, 20h
0x18001d302  mov     dword ptr [rcx+18h], 0C0000001h
0x18001d309  lea     rax, ??_7?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::`vftable'
0x18001d310  mov     [rcx], rax
0x18001d313  mov     rbx, rcx
0x18001d316  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001d31d  mov     rax, [rcx]
0x18001d320  mov     rax, [rax+10h]
0x18001d324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d329  mov     rcx, rbx; this
0x18001d32c  add     rsp, 20h
0x18001d330  pop     rbx
0x18001d331  jmp     ??1CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::~CEventMetadataEventTraceExtender(void)
```
