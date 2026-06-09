# ATL::CComObject<CGameExplorer>::~CComObject<CGameExplorer>(void)

- ea: `0x180001c38`
- end: `0x180001c93`
- name: `??1?$CComObject@VCGameExplorer@@@ATL@@UEAA@XZ`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001d20`

## callees

- `0x180001cbc`
- `0x180004010`

## pseudocode

```c
void __fastcall ATL::CComObject<CGameExplorer>::~CComObject<CGameExplorer>(__int64 a1)
{
  *(_DWORD *)(a1 + 16) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<CGameExplorer>::`vftable'{for `IGameExplorer2'};
  *(_QWORD *)(a1 + 8) = &ATL::CComObject<CGameExplorer>::`vftable'{for `IGameExplorer'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  *(_QWORD *)a1 = &CGameExplorer::`vftable'{for `IGameExplorer2'};
  *(_QWORD *)(a1 + 8) = &CGameExplorer::`vftable'{for `IGameExplorer'};
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((ATL::CComSafeDeleteCriticalSection *)(a1 + 24));
}

```

## disassembly

```asm
0x180001c38  push    rbx
0x180001c3a  sub     rsp, 20h
0x180001c3e  mov     dword ptr [rcx+10h], 0C0000001h
0x180001c45  lea     rax, ??_7?$CComObject@VCGameExplorer@@@ATL@@6BIGameExplorer2@@@; const ATL::CComObject<CGameExplorer>::`vftable'{for `IGameExplorer2'}
0x180001c4c  mov     [rcx], rax
0x180001c4f  mov     rbx, rcx
0x180001c52  lea     rax, ??_7?$CComObject@VCGameExplorer@@@ATL@@6BIGameExplorer@@@; const ATL::CComObject<CGameExplorer>::`vftable'{for `IGameExplorer'}
0x180001c59  mov     [rcx+8], rax
0x180001c5d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180001c64  mov     rax, [rcx]
0x180001c67  mov     rax, [rax+10h]
0x180001c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c70  lea     rax, ??_7CGameExplorer@@6BIGameExplorer2@@@; const CGameExplorer::`vftable'{for `IGameExplorer2'}
0x180001c77  mov     [rbx], rax
0x180001c7a  lea     rcx, [rbx+18h]; this
0x180001c7e  lea     rax, ??_7CGameExplorer@@6BIGameExplorer@@@; const CGameExplorer::`vftable'{for `IGameExplorer'}
0x180001c85  mov     [rbx+8], rax
0x180001c89  add     rsp, 20h
0x180001c8d  pop     rbx
0x180001c8e  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
