# ATL::CComAggObject<CServicingSession>::~CComAggObject<CServicingSession>(void)

- ea: `0x180003054`
- end: `0x180003097`
- name: `??1?$CComAggObject@VCServicingSession@@@ATL@@UEAA@XZ`
- size: `67`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800035d0`

## callees

- `0x18000344c`
- `0x1800232f0`
- `0x180034010`

## pseudocode

```c
void __fastcall ATL::CComAggObject<CServicingSession>::~CComAggObject<CServicingSession>(__int64 a1)
{
  CServicingSession *v1; // rbx

  *(_DWORD *)(a1 + 8) = -1073741823;
  v1 = (CServicingSession *)(a1 + 24);
  *(_QWORD *)a1 = &ATL::CComAggObject<CServicingSession>::`vftable';
  CServicingSession::FinalRelease((CServicingSession *)(a1 + 24));
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CServicingSession::~CServicingSession(v1);
}

```

## disassembly

```asm
0x180003054  push    rbx
0x180003056  sub     rsp, 20h
0x18000305a  lea     rax, ??_7?$CComAggObject@VCServicingSession@@@ATL@@6B@; const ATL::CComAggObject<CServicingSession>::`vftable'
0x180003061  mov     dword ptr [rcx+8], 0C0000001h
0x180003068  lea     rbx, [rcx+18h]
0x18000306c  mov     [rcx], rax
0x18000306f  mov     rcx, rbx; this
0x180003072  call    ?FinalRelease@CServicingSession@@QEAAXXZ; CServicingSession::FinalRelease(void)
0x180003077  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000307e  mov     rax, [rcx]
0x180003081  mov     rax, [rax+10h]
0x180003085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000308a  mov     rcx, rbx; this
0x18000308d  add     rsp, 20h
0x180003091  pop     rbx
0x180003092  jmp     ??1CServicingSession@@QEAA@XZ; CServicingSession::~CServicingSession(void)
```
