# ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>(void)

- ea: `0x18001c820`
- end: `0x18001c85a`
- name: `??1?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ`
- size: `58`
- prototype: `void __fastcall(Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001ccc0`

## callees

- `0x18001ca64`
- `0x180026010`

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
0x18001c820  push    rbx
0x18001c822  sub     rsp, 20h
0x18001c826  mov     dword ptr [rcx+18h], 0C0000001h
0x18001c82d  lea     rax, ??_7?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::`vftable'
0x18001c834  mov     [rcx], rax
0x18001c837  mov     rbx, rcx
0x18001c83a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001c841  mov     rax, [rcx]
0x18001c844  mov     rax, [rax+10h]
0x18001c848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c84d  mov     rcx, rbx; this
0x18001c850  add     rsp, 20h
0x18001c854  pop     rbx
0x18001c855  jmp     ??1CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::~CEventMetadataEventTraceExtender(void)
```
