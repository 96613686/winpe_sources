# PerfDiagDm::CObjectTable<PerfDiagDm::IScenario>::~CObjectTable<PerfDiagDm::IScenario>(void)

- ea: `0x18003c084`
- end: `0x18003c0a5`
- name: `??1?$CObjectTable@UIScenario@PerfDiagDm@@@PerfDiagDm@@QEAA@XZ`
- size: `33`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18003b93c`
- `0x1800ae654`

## callees

- `0x18003c0ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003c09e`

## pseudocode

```c
void __fastcall PerfDiagDm::CObjectTable<PerfDiagDm::IScenario>::~CObjectTable<PerfDiagDm::IScenario>(
        struct _RTL_CRITICAL_SECTION *a1)
{
  std::_Tree<std::_Tmap_traits<_GUID,ATL::CComPtr<PerfDiagDm::IDiagnosticModule>,PerfDiagDm::lessGuid,std::allocator<std::pair<_GUID const,ATL::CComPtr<PerfDiagDm::IDiagnosticModule>>>,0>>::~_Tree<std::_Tmap_traits<_GUID,ATL::CComPtr<PerfDiagDm::IDiagnosticModule>,PerfDiagDm::lessGuid,std::allocator<std::pair<_GUID const,ATL::CComPtr<PerfDiagDm::IDiagnosticModule>>>,0>>(&a1[1]);
  DeleteCriticalSection(a1);
}

```

## disassembly

```asm
0x18003c084  push    rbx
0x18003c086  sub     rsp, 20h
0x18003c08a  mov     rbx, rcx
0x18003c08d  add     rcx, 28h ; '('
0x18003c091  call    ??1?$_Tree@V?$_Tmap_traits@U_GUID@@V?$CComPtr@UIDiagnosticModule@PerfDiagDm@@@ATL@@UlessGuid@PerfDiagDm@@V?$allocator@U?$pair@$$CBU_GUID@@V?$CComPtr@UIDiagnosticModule@PerfDiagDm@@@ATL@@@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_GUID,ATL::CComPtr<PerfDiagDm::IDiagnosticModule>,PerfDiagDm::lessGuid,std::allocator<std::pair<_GUID const,ATL::CComPtr<PerfDiagDm::IDiagnosticModule>>>,0>>::~_Tree<std::_Tmap_traits<_GUID,ATL::CComPtr<PerfDiagDm::IDiagnosticModule>,PerfDiagDm::lessGuid,std::allocator<std::pair<_GUID const,ATL::CComPtr<PerfDiagDm::IDiagnosticModule>>>,0>>(void)
0x18003c096  mov     rcx, rbx
0x18003c099  add     rsp, 20h
0x18003c09d  pop     rbx
0x18003c09e  jmp     cs:__imp_DeleteCriticalSection
```
