# ATL::CComObject<IASTL::IASComponentObject<NTEventLog>>::~CComObject<IASTL::IASComponentObject<NTEventLog>>(void)

- ea: `0x18000d6a0`
- end: `0x18000d710`
- name: `??1?$CComObject@V?$IASComponentObject@VNTEventLog@@@IASTL@@@ATL@@UEAA@XZ`
- size: `112`
- prototype: `void __fastcall(IASTL::IASComponent *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000da70`

## callees

- `0x18000d6a0`
- `0x18000d904`
- `0x18001528c`
- `0x180019010`

## import_xrefs

- `ADVAPI32!DeregisterEventSource` at `0x18000d6e5`
- `ADVAPI32!DeregisterEventSource` at `0x18000d6e5`
- `KERNEL32!DeleteCriticalSection` at `0x18000d6f8`
- `KERNEL32!DeleteCriticalSection` at `0x18000d6f8`

## pseudocode

```c
void __fastcall ATL::CComObject<IASTL::IASComponentObject<NTEventLog>>::~CComObject<IASTL::IASComponentObject<NTEventLog>>(
        IASTL::IASComponent *this)
{
  void *v2; // rcx

  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<IASTL::IASComponentObject<NTEventLog>>::`vftable'{for `IASTL::IASComponent'};
  *((_QWORD *)this + 9) = &ATL::CComObject<IASTL::IASComponentObject<NTEventLog>>::`vftable'{for `IAuditSink'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v2 = (void *)*((_QWORD *)this + 10);
  if ( v2 )
    DeregisterEventSource(v2);
  CSecurityLogHelper::CleanUp((IASTL::IASComponent *)((char *)this + 104));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  IASTL::IASComponent::~IASComponent(this);
}

```

## disassembly

```asm
0x18000d6a0  mov     [rsp+arg_0], rbx
0x18000d6a5  push    rdi
0x18000d6a6  sub     rsp, 20h
0x18000d6aa  mov     dword ptr [rcx+8], 0C0000001h
0x18000d6b1  lea     rax, ??_7?$CComObject@V?$IASComponentObject@VNTEventLog@@@IASTL@@@ATL@@6BIASComponent@IASTL@@@; const ATL::CComObject<IASTL::IASComponentObject<NTEventLog>>::`vftable'{for `IASTL::IASComponent'}
0x18000d6b8  mov     [rcx], rax
0x18000d6bb  mov     rdi, rcx
0x18000d6be  lea     rax, ??_7?$CComObject@V?$IASComponentObject@VNTEventLog@@@IASTL@@@ATL@@6BIAuditSink@@@; const ATL::CComObject<IASTL::IASComponentObject<NTEventLog>>::`vftable'{for `IAuditSink'}
0x18000d6c5  mov     [rcx+48h], rax
0x18000d6c9  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000d6d0  mov     rax, [rcx]
0x18000d6d3  mov     rax, [rax+10h]
0x18000d6d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6dc  mov     rcx, [rdi+50h]; hEventLog
0x18000d6e0  test    rcx, rcx
0x18000d6e3  jz      short loc_18000D6EB
0x18000d6e5  call    cs:__imp_DeregisterEventSource
0x18000d6eb  lea     rcx, [rdi+68h]; this
0x18000d6ef  call    ?CleanUp@CSecurityLogHelper@@AEAAXXZ; CSecurityLogHelper::CleanUp(void)
0x18000d6f4  lea     rcx, [rdi+68h]; lpCriticalSection
0x18000d6f8  call    cs:__imp_DeleteCriticalSection
0x18000d6fe  mov     rcx, rdi; this
0x18000d701  mov     rbx, [rsp+28h+arg_0]
0x18000d706  add     rsp, 20h
0x18000d70a  pop     rdi
0x18000d70b  jmp     ??1IASComponent@IASTL@@QEAA@XZ; IASTL::IASComponent::~IASComponent(void)
```
