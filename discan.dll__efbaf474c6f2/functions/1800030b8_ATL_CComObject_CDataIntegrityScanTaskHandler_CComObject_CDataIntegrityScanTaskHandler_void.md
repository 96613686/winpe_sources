# ATL::CComObject<CDataIntegrityScanTaskHandler>::~CComObject<CDataIntegrityScanTaskHandler>(void)

- ea: `0x1800030b8`
- end: `0x180003102`
- name: `??1?$CComObject@VCDataIntegrityScanTaskHandler@@@ATL@@UEAA@XZ`
- size: `74`
- prototype: `void __fastcall(CDataIntegrityScanTaskHandler *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180003420`

## callees

- `0x180003224`
- `0x1800048ac`
- `0x180039010`

## pseudocode

```c
void __fastcall ATL::CComObject<CDataIntegrityScanTaskHandler>::~CComObject<CDataIntegrityScanTaskHandler>(
        CDataIntegrityScanTaskHandler *this)
{
  *((_DWORD *)this + 4) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CDataIntegrityScanTaskHandler>::`vftable'{for `ITaskHandler'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CDataIntegrityScanTaskHandler>::`vftable'{for `ISystemScanNotify'};
  CDataIntegrityScanTaskHandler::FinalRelease(this);
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CDataIntegrityScanTaskHandler::~CDataIntegrityScanTaskHandler(this);
}

```

## disassembly

```asm
0x1800030b8  push    rbx
0x1800030ba  sub     rsp, 20h
0x1800030be  lea     rax, ??_7?$CComObject@VCDataIntegrityScanTaskHandler@@@ATL@@6BITaskHandler@@@; const ATL::CComObject<CDataIntegrityScanTaskHandler>::`vftable'{for `ITaskHandler'}
0x1800030c5  mov     dword ptr [rcx+10h], 0C0000001h
0x1800030cc  mov     [rcx], rax
0x1800030cf  mov     rbx, rcx
0x1800030d2  lea     rax, ??_7?$CComObject@VCDataIntegrityScanTaskHandler@@@ATL@@6BISystemScanNotify@@@; const ATL::CComObject<CDataIntegrityScanTaskHandler>::`vftable'{for `ISystemScanNotify'}
0x1800030d9  mov     [rcx+8], rax
0x1800030dd  call    ?FinalRelease@CDataIntegrityScanTaskHandler@@QEAAXXZ; CDataIntegrityScanTaskHandler::FinalRelease(void)
0x1800030e2  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800030e9  mov     rax, [rcx]
0x1800030ec  mov     rax, [rax+10h]
0x1800030f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030f5  mov     rcx, rbx; this
0x1800030f8  add     rsp, 20h
0x1800030fc  pop     rbx
0x1800030fd  jmp     ??1CDataIntegrityScanTaskHandler@@QEAA@XZ; CDataIntegrityScanTaskHandler::~CDataIntegrityScanTaskHandler(void)
```
