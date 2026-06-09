# ATL::CComAggObject<CGameExplorer>::~CComAggObject<CGameExplorer>(void)

- ea: `0x180001be0`
- end: `0x180001c31`
- name: `??1?$CComAggObject@VCGameExplorer@@@ATL@@UEAA@XZ`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001ce0`

## callees

- `0x180001cbc`
- `0x180004010`

## pseudocode

```c
void __fastcall ATL::CComAggObject<CGameExplorer>::~CComAggObject<CGameExplorer>(__int64 a1)
{
  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComAggObject<CGameExplorer>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  *(_QWORD *)(a1 + 24) = &CGameExplorer::`vftable'{for `IGameExplorer2'};
  *(_QWORD *)(a1 + 32) = &CGameExplorer::`vftable'{for `IGameExplorer'};
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((ATL::CComSafeDeleteCriticalSection *)(a1 + 48));
}

```

## disassembly

```asm
0x180001be0  push    rbx
0x180001be2  sub     rsp, 20h
0x180001be6  mov     dword ptr [rcx+8], 0C0000001h
0x180001bed  lea     rax, ??_7?$CComAggObject@VCGameExplorer@@@ATL@@6B@; const ATL::CComAggObject<CGameExplorer>::`vftable'
0x180001bf4  mov     [rcx], rax
0x180001bf7  mov     rbx, rcx
0x180001bfa  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180001c01  mov     rax, [rcx]
0x180001c04  mov     rax, [rax+10h]
0x180001c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c0d  lea     rax, ??_7CGameExplorer@@6BIGameExplorer2@@@; const CGameExplorer::`vftable'{for `IGameExplorer2'}
0x180001c14  mov     [rbx+18h], rax
0x180001c18  lea     rcx, [rbx+30h]; this
0x180001c1c  lea     rax, ??_7CGameExplorer@@6BIGameExplorer@@@; const CGameExplorer::`vftable'{for `IGameExplorer'}
0x180001c23  mov     [rbx+20h], rax
0x180001c27  add     rsp, 20h
0x180001c2b  pop     rbx
0x180001c2c  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
