# ATL::CComObject<ShutdownScenario>::CComObject<ShutdownScenario>(void *)

- ea: `0x18004210c`
- end: `0x180042169`
- name: `??0?$CComObject@VShutdownScenario@@@ATL@@QEAA@PEAX@Z`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002a8a8`

## callees

- `0x18002da30`
- `0x1800d6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180042135`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180042135`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<ShutdownScenario>::CComObject<ShutdownScenario>(__int64 a1)
{
  HANDLE EventW; // rax
  struct ATL::CAtlModule *v3; // rcx

  *(_DWORD *)(a1 + 16) = 0;
  PerfDiagDm::CDiagnosticModuleRootBase::CDiagnosticModuleRootBase((PerfDiagDm::CDiagnosticModuleRootBase *)a1);
  *(_QWORD *)(a1 + 24) = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  v3 = ATL::_pAtlModule;
  *(_QWORD *)(a1 + 24) = EventW;
  *(_QWORD *)a1 = &ATL::CComObject<ShutdownScenario>::`vftable';
  *(_BYTE *)(a1 + 32) = 0;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v3 + 8LL))(v3);
  return a1;
}

```

## disassembly

```asm
0x18004210c  push    rbx
0x18004210e  sub     rsp, 20h
0x180042112  mov     rbx, rcx
0x180042115  mov     dword ptr [rcx+10h], 0
0x18004211c  call    ??0CDiagnosticModuleRootBase@PerfDiagDm@@IEAA@XZ; PerfDiagDm::CDiagnosticModuleRootBase::CDiagnosticModuleRootBase(void)
0x180042121  xor     r9d, r9d; lpName
0x180042124  mov     qword ptr [rbx+18h], 0
0x18004212c  xor     r8d, r8d; bInitialState
0x18004212f  xor     ecx, ecx; lpEventAttributes
0x180042131  lea     edx, [r9+1]; bManualReset
0x180042135  call    cs:__imp_CreateEventW
0x18004213b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180042142  mov     [rbx+18h], rax
0x180042146  lea     rax, ??_7?$CComObject@VShutdownScenario@@@ATL@@6B@; const ATL::CComObject<ShutdownScenario>::`vftable'
0x18004214d  mov     [rbx], rax
0x180042150  mov     byte ptr [rbx+20h], 0
0x180042154  mov     rax, [rcx]
0x180042157  mov     rax, [rax+8]
0x18004215b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042160  mov     rax, rbx
0x180042163  add     rsp, 20h
0x180042167  pop     rbx
0x180042168  retn
```
