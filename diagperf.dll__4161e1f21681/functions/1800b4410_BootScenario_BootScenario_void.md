# BootScenario::BootScenario(void)

- ea: `0x1800b4410`
- end: `0x1800b44c2`
- name: `??0BootScenario@@QEAA@XZ`
- size: `178`
- prototype: `BootScenario *__fastcall(BootScenario *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18003ef2c`

## callees

- `0x1800282a4`
- `0x18002b1b0`
- `0x18002da30`
- `0x1800b4410`
- `0x1800d6010`

## import_xrefs

- `KERNEL32!CreateTimerQueue` at `0x1800b4485`
- `KERNEL32!CreateTimerQueue` at `0x1800b4485`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
BootScenario *__fastcall BootScenario::BootScenario(BootScenario *this)
{
  int v2; // eax
  const unsigned __int16 *v3; // r9

  *((_DWORD *)this + 4) = 0;
  PerfDiagDm::CDiagnosticModuleRootBase::CDiagnosticModuleRootBase(this);
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 56);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 64);
  *((_DWORD *)this + 18) = 0;
  *((_QWORD *)this + 10) = &PerfDiagBoot::CScenarioConfiguration::`vftable';
  *((_DWORD *)this + 22) = 30;
  *((_DWORD *)this + 23) = 60;
  *((_QWORD *)this + 4) = CreateTimerQueue();
  v2 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
  if ( v2 < 0 )
    PerfDiagOutput::StatusLog::Write(
      (PerfDiagOutput::StatusLog *)PDEvt_Boot_DMConfig_Failed,
      (const struct _EVENT_DESCRIPTOR *)(unsigned int)v2,
      0,
      v3);
  return this;
}

```

## disassembly

```asm
0x1800b4410  mov     [rsp+arg_8], rbx
0x1800b4415  mov     [rsp+arg_0], rcx
0x1800b441a  push    rdi
0x1800b441b  sub     rsp, 20h
0x1800b441f  mov     rdi, rcx
0x1800b4422  mov     dword ptr [rcx+10h], 0
0x1800b4429  call    ??0CDiagnosticModuleRootBase@PerfDiagDm@@IEAA@XZ; PerfDiagDm::CDiagnosticModuleRootBase::CDiagnosticModuleRootBase(void)
0x1800b442e  nop
0x1800b442f  mov     dword ptr [rdi+18h], 0
0x1800b4436  mov     qword ptr [rdi+20h], 0
0x1800b443e  mov     qword ptr [rdi+28h], 0
0x1800b4446  mov     qword ptr [rdi+30h], 0
0x1800b444e  lea     rcx, [rdi+38h]
0x1800b4452  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800b4457  nop
0x1800b4458  lea     rcx, [rdi+40h]
0x1800b445c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800b4461  nop
0x1800b4462  mov     dword ptr [rdi+48h], 0
0x1800b4469  lea     rbx, [rdi+50h]
0x1800b446d  lea     rax, ??_7CScenarioConfiguration@PerfDiagBoot@@6B@; const PerfDiagBoot::CScenarioConfiguration::`vftable'
0x1800b4474  mov     [rbx], rax
0x1800b4477  mov     dword ptr [rbx+8], 1Eh
0x1800b447e  mov     dword ptr [rbx+0Ch], 3Ch ; '<'
0x1800b4485  call    cs:__imp_CreateTimerQueue
0x1800b448b  mov     [rdi+20h], rax
0x1800b448f  mov     rax, [rbx]
0x1800b4492  mov     rcx, rbx
0x1800b4495  mov     rax, [rax+10h]
0x1800b4499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b449e  test    eax, eax
0x1800b44a0  jns     short loc_1800B44B4
0x1800b44a2  xor     r8d, r8d; unsigned int
0x1800b44a5  mov     edx, eax; struct _EVENT_DESCRIPTOR *
0x1800b44a7  lea     rcx, PDEvt_Boot_DMConfig_Failed; this
0x1800b44ae  call    ?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@KPEBG@Z; PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &,ulong,ushort const *)
0x1800b44b3  nop
0x1800b44b4  mov     rax, rdi
0x1800b44b7  mov     rbx, [rsp+28h+arg_8]
0x1800b44bc  add     rsp, 20h
0x1800b44c0  pop     rdi
0x1800b44c1  retn
```
