# PerfDiagDm::CDmManager::~CDmManager(void)

- ea: `0x1800ae654`
- end: `0x1800ae6b3`
- name: `??1CDmManager@PerfDiagDm@@AEAA@XZ`
- size: `95`
- prototype: `void __fastcall(PerfDiagDm::CDmManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180044394`

## callees

- `0x18003268c`
- `0x18003c084`
- `0x180056c14`
- `0x1800ae654`

## import_xrefs

- `ntdll!EtwEventUnregister` at `0x1800ae686`
- `ntdll!EtwEventUnregister` at `0x1800ae686`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ae69b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ae69b`

## pseudocode

```c
void __fastcall PerfDiagDm::CDmManager::~CDmManager(PerfDiagDm::CDmManager *this)
{
  void *v1; // rdi

  v1 = (void *)*((_QWORD *)this + 7);
  if ( v1 )
  {
    PerfDiagDm::CObjectTable<PerfDiagDm::IScenario>::~CObjectTable<PerfDiagDm::IScenario>(*((_QWORD *)this + 7));
    operator delete(v1);
  }
  if ( PerfDiagOutput::StatusLog::g_RegHandle )
  {
    EtwEventUnregister(PerfDiagOutput::StatusLog::g_RegHandle);
    PerfDiagOutput::StatusLog::g_RegHandle = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(this);
}

```

## disassembly

```asm
0x1800ae654  mov     [rsp+arg_0], rbx
0x1800ae659  push    rdi
0x1800ae65a  sub     rsp, 20h
0x1800ae65e  mov     rdi, [rcx+38h]
0x1800ae662  mov     rbx, rcx
0x1800ae665  test    rdi, rdi
0x1800ae668  jz      short loc_1800AE67A
0x1800ae66a  mov     rcx, rdi
0x1800ae66d  call    ??1?$CObjectTable@UIScenario@PerfDiagDm@@@PerfDiagDm@@QEAA@XZ; PerfDiagDm::CObjectTable<PerfDiagDm::IScenario>::~CObjectTable<PerfDiagDm::IScenario>(void)
0x1800ae672  mov     rcx, rdi; Block
0x1800ae675  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ae67a  mov     rcx, cs:?g_RegHandle@StatusLog@PerfDiagOutput@@3_KA; unsigned __int64 PerfDiagOutput::StatusLog::g_RegHandle
0x1800ae681  test    rcx, rcx
0x1800ae684  jz      short loc_1800AE697
0x1800ae686  call    cs:__imp_EtwEventUnregister
0x1800ae68c  mov     cs:?g_RegHandle@StatusLog@PerfDiagOutput@@3_KA, 0; unsigned __int64 PerfDiagOutput::StatusLog::g_RegHandle
0x1800ae697  lea     rcx, [rbx+8]; lpCriticalSection
0x1800ae69b  call    cs:__imp_DeleteCriticalSection
0x1800ae6a1  mov     rcx, rbx
0x1800ae6a4  mov     rbx, [rsp+28h+arg_0]
0x1800ae6a9  add     rsp, 20h
0x1800ae6ad  pop     rdi
0x1800ae6ae  jmp     ??1?$CComPtrBase@UIEventSinkRegistry@XPerfCore@@@ATL@@QEAA@XZ; ATL::CComPtrBase<XPerfCore::IEventSinkRegistry>::~CComPtrBase<XPerfCore::IEventSinkRegistry>(void)
```
