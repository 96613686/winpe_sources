# ATL::CComAggObject<CRestoreSession>::~CComAggObject<CRestoreSession>(void)

- ea: `0x180003008`
- end: `0x18000304b`
- name: `??1?$CComAggObject@VCRestoreSession@@@ATL@@UEAA@XZ`
- size: `67`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003590`

## callees

- `0x1800033d0`
- `0x180023fcc`
- `0x180034010`

## pseudocode

```c
void __fastcall ATL::CComAggObject<CRestoreSession>::~CComAggObject<CRestoreSession>(__int64 a1)
{
  CRestoreSession *v1; // rbx

  *(_DWORD *)(a1 + 8) = -1073741823;
  v1 = (CRestoreSession *)(a1 + 24);
  *(_QWORD *)a1 = &ATL::CComAggObject<CRestoreSession>::`vftable';
  CRestoreSession::FinalRelease((CRestoreSession *)(a1 + 24));
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CRestoreSession::~CRestoreSession(v1);
}

```

## disassembly

```asm
0x180003008  push    rbx
0x18000300a  sub     rsp, 20h
0x18000300e  lea     rax, ??_7?$CComAggObject@VCRestoreSession@@@ATL@@6B@; const ATL::CComAggObject<CRestoreSession>::`vftable'
0x180003015  mov     dword ptr [rcx+8], 0C0000001h
0x18000301c  lea     rbx, [rcx+18h]
0x180003020  mov     [rcx], rax
0x180003023  mov     rcx, rbx; this
0x180003026  call    ?FinalRelease@CRestoreSession@@QEAAXXZ; CRestoreSession::FinalRelease(void)
0x18000302b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003032  mov     rax, [rcx]
0x180003035  mov     rax, [rax+10h]
0x180003039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000303e  mov     rcx, rbx; this
0x180003041  add     rsp, 20h
0x180003045  pop     rbx
0x180003046  jmp     ??1CRestoreSession@@QEAA@XZ; CRestoreSession::~CRestoreSession(void)
```
