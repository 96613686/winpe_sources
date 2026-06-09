# PerfDiagSecondaryLogons::CSecondaryLogonScenario::CSecondaryLogonScenario(void)

- ea: `0x180041034`
- end: `0x1800410c3`
- name: `??0CSecondaryLogonScenario@PerfDiagSecondaryLogons@@QEAA@XZ`
- size: `143`
- prototype: `__int64 __fastcall(PerfDiagSecondaryLogons::CSecondaryLogonScenario *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800422ec`

## callees

- `0x1800282a4`
- `0x18002da30`
- `0x180041034`
- `0x1800d6010`

## import_xrefs

- `KERNEL32!CreateTimerQueue` at `0x180041086`
- `KERNEL32!CreateTimerQueue` at `0x180041086`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PerfDiagSecondaryLogons::CSecondaryLogonScenario *__fastcall PerfDiagSecondaryLogons::CSecondaryLogonScenario::CSecondaryLogonScenario(
        PerfDiagSecondaryLogons::CSecondaryLogonScenario *this)
{
  int v2; // eax
  const unsigned __int16 *v3; // r9

  *((_DWORD *)this + 4) = 0;
  PerfDiagDm::CDiagnosticModuleRootBase::CDiagnosticModuleRootBase(this);
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 7) = &PerfDiagSecondaryLogons::CSecondaryLogonScenario::CScenarioConfiguration::`vftable';
  *((_DWORD *)this + 16) = 60;
  *((_QWORD *)this + 4) = CreateTimerQueue();
  v2 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 7) + 16LL))((char *)this + 56);
  if ( v2 < 0 )
    PerfDiagOutput::StatusLog::Write(
      (PerfDiagOutput::StatusLog *)PDEvt_SecondaryLogon_DMConfig_Failed,
      (const struct _EVENT_DESCRIPTOR *)(unsigned int)v2,
      0,
      v3);
  return this;
}

```

## disassembly

```asm
0x180041034  mov     [rsp+arg_8], rbx
0x180041039  mov     [rsp+arg_0], rcx
0x18004103e  push    rdi
0x18004103f  sub     rsp, 20h
0x180041043  mov     rdi, rcx
0x180041046  mov     dword ptr [rcx+10h], 0
0x18004104d  call    ??0CDiagnosticModuleRootBase@PerfDiagDm@@IEAA@XZ; PerfDiagDm::CDiagnosticModuleRootBase::CDiagnosticModuleRootBase(void)
0x180041052  nop
0x180041053  mov     dword ptr [rdi+18h], 0
0x18004105a  mov     qword ptr [rdi+20h], 0
0x180041062  mov     qword ptr [rdi+28h], 0
0x18004106a  mov     dword ptr [rdi+30h], 0
0x180041071  lea     rbx, [rdi+38h]
0x180041075  lea     rax, ??_7CScenarioConfiguration@CSecondaryLogonScenario@PerfDiagSecondaryLogons@@6B@; const PerfDiagSecondaryLogons::CSecondaryLogonScenario::CScenarioConfiguration::`vftable'
0x18004107c  mov     [rbx], rax
0x18004107f  mov     dword ptr [rbx+8], 3Ch ; '<'
0x180041086  call    cs:__imp_CreateTimerQueue
0x18004108c  mov     [rdi+20h], rax
0x180041090  mov     rax, [rbx]
0x180041093  mov     rcx, rbx
0x180041096  mov     rax, [rax+10h]
0x18004109a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004109f  test    eax, eax
0x1800410a1  jns     short loc_1800410B5
0x1800410a3  xor     r8d, r8d; unsigned int
0x1800410a6  mov     edx, eax; struct _EVENT_DESCRIPTOR *
0x1800410a8  lea     rcx, PDEvt_SecondaryLogon_DMConfig_Failed; this
0x1800410af  call    ?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@KPEBG@Z; PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &,ulong,ushort const *)
0x1800410b4  nop
0x1800410b5  mov     rax, rdi
0x1800410b8  mov     rbx, [rsp+28h+arg_8]
0x1800410bd  add     rsp, 20h
0x1800410c1  pop     rdi
0x1800410c2  retn
```
