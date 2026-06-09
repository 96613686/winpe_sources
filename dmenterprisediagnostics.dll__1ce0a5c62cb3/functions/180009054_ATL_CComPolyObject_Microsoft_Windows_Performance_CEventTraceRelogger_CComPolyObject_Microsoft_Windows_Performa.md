# ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::~CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>(void)

- ea: `0x180009054`
- end: `0x18000908f`
- name: `??1?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ`
- size: `59`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800094f0`

## callees

- `0x180009234`
- `0x180026010`

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
0x180009054  push    rbx
0x180009056  sub     rsp, 20h
0x18000905a  mov     dword ptr [rcx+8], 0C0000001h
0x180009061  lea     rax, ??_7?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vftable'
0x180009068  mov     [rcx], rax
0x18000906b  mov     rbx, rcx
0x18000906e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009075  mov     rax, [rcx]
0x180009078  mov     rax, [rax+10h]
0x18000907c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009081  lea     rcx, [rbx+10h]; this
0x180009085  add     rsp, 20h
0x180009089  pop     rbx
0x18000908a  jmp     ??1CEventTraceRelogger@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventTraceRelogger::~CEventTraceRelogger(void)
```
