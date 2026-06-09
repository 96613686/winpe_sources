# ATL::CComAggObject<CDataIntegrityScanTaskHandler>::~CComAggObject<CDataIntegrityScanTaskHandler>(void)

- ea: `0x18000306c`
- end: `0x1800030af`
- name: `??1?$CComAggObject@VCDataIntegrityScanTaskHandler@@@ATL@@UEAA@XZ`
- size: `67`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800033e0`

## callees

- `0x180003224`
- `0x1800048ac`
- `0x180039010`

## pseudocode

```c
void __fastcall ATL::CComAggObject<CDataIntegrityScanTaskHandler>::~CComAggObject<CDataIntegrityScanTaskHandler>(
        __int64 a1)
{
  CDataIntegrityScanTaskHandler *v1; // rbx

  *(_DWORD *)(a1 + 8) = -1073741823;
  v1 = (CDataIntegrityScanTaskHandler *)(a1 + 24);
  *(_QWORD *)a1 = &ATL::CComAggObject<CDataIntegrityScanTaskHandler>::`vftable';
  CDataIntegrityScanTaskHandler::FinalRelease((CDataIntegrityScanTaskHandler *)(a1 + 24));
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CDataIntegrityScanTaskHandler::~CDataIntegrityScanTaskHandler(v1);
}

```

## disassembly

```asm
0x18000306c  push    rbx
0x18000306e  sub     rsp, 20h
0x180003072  lea     rax, ??_7?$CComAggObject@VCDataIntegrityScanTaskHandler@@@ATL@@6B@; const ATL::CComAggObject<CDataIntegrityScanTaskHandler>::`vftable'
0x180003079  mov     dword ptr [rcx+8], 0C0000001h
0x180003080  lea     rbx, [rcx+18h]
0x180003084  mov     [rcx], rax
0x180003087  mov     rcx, rbx; this
0x18000308a  call    ?FinalRelease@CDataIntegrityScanTaskHandler@@QEAAXXZ; CDataIntegrityScanTaskHandler::FinalRelease(void)
0x18000308f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003096  mov     rax, [rcx]
0x180003099  mov     rax, [rax+10h]
0x18000309d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030a2  mov     rcx, rbx; this
0x1800030a5  add     rsp, 20h
0x1800030a9  pop     rbx
0x1800030aa  jmp     ??1CDataIntegrityScanTaskHandler@@QEAA@XZ; CDataIntegrityScanTaskHandler::~CDataIntegrityScanTaskHandler(void)
```
