# ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::~CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>(void)

- ea: `0x1800094d4`
- end: `0x18000950f`
- name: `??1?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800099a0`

## callees

- `0x1800096c4`
- `0x180027010`

## pseudocode

```c
void __fastcall ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::~CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>(
        __int64 a1)
{
  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CEventTraceRelogger::~CEventTraceRelogger((Microsoft::Windows::Performance::CEventTraceRelogger *)(a1 + 16));
}

```

## disassembly

```asm
0x1800094d4  push    rbx
0x1800094d6  sub     rsp, 20h
0x1800094da  mov     dword ptr [rcx+8], 0C0000001h
0x1800094e1  lea     rax, ??_7?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vftable'
0x1800094e8  mov     [rcx], rax
0x1800094eb  mov     rbx, rcx
0x1800094ee  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800094f5  mov     rax, [rcx]
0x1800094f8  mov     rax, [rax+10h]
0x1800094fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009501  lea     rcx, [rbx+10h]; this
0x180009505  add     rsp, 20h
0x180009509  pop     rbx
0x18000950a  jmp     ??1CEventTraceRelogger@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventTraceRelogger::~CEventTraceRelogger(void)
```
