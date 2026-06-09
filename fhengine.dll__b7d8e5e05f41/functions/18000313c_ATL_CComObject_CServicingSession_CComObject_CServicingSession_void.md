# ATL::CComObject<CServicingSession>::~CComObject<CServicingSession>(void)

- ea: `0x18000313c`
- end: `0x180003189`
- name: `??1?$CComObject@VCServicingSession@@@ATL@@UEAA@XZ`
- size: `77`
- prototype: `void __fastcall(CServicingSession *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180003690`

## callees

- `0x18000344c`
- `0x1800232f0`
- `0x180034010`

## pseudocode

```c
void __fastcall ATL::CComObject<CServicingSession>::~CComObject<CServicingSession>(CServicingSession *this)
{
  *((_DWORD *)this + 72) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CServicingSession>::`vftable'{for `IFhEngineServicing'};
  *((_QWORD *)this + 1) = &ATL::CComContainedObject<CServicingSession>::`vftable'{for `CSessionBaseRW'};
  CServicingSession::FinalRelease(this);
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CServicingSession::~CServicingSession(this);
}

```

## disassembly

```asm
0x18000313c  push    rbx
0x18000313e  sub     rsp, 20h
0x180003142  lea     rax, ??_7?$CComObject@VCServicingSession@@@ATL@@6BIFhEngineServicing@@@; const ATL::CComObject<CServicingSession>::`vftable'{for `IFhEngineServicing'}
0x180003149  mov     dword ptr [rcx+120h], 0C0000001h
0x180003153  mov     [rcx], rax
0x180003156  mov     rbx, rcx
0x180003159  lea     rax, ??_7?$CComContainedObject@VCServicingSession@@@ATL@@6BCSessionBaseRW@@@; const ATL::CComContainedObject<CServicingSession>::`vftable'{for `CSessionBaseRW'}
0x180003160  mov     [rcx+8], rax
0x180003164  call    ?FinalRelease@CServicingSession@@QEAAXXZ; CServicingSession::FinalRelease(void)
0x180003169  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003170  mov     rax, [rcx]
0x180003173  mov     rax, [rax+10h]
0x180003177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000317c  mov     rcx, rbx; this
0x18000317f  add     rsp, 20h
0x180003183  pop     rbx
0x180003184  jmp     ??1CServicingSession@@QEAA@XZ; CServicingSession::~CServicingSession(void)
```
