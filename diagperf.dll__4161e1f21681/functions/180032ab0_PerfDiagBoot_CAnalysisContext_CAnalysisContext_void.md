# PerfDiagBoot::CAnalysisContext::CAnalysisContext(void)

- ea: `0x180032ab0`
- end: `0x180032b98`
- name: `??0CAnalysisContext@PerfDiagBoot@@QEAA@XZ`
- size: `232`
- prototype: `PerfDiagBoot::CAnalysisContext *__fastcall(PerfDiagBoot::CAnalysisContext *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800279d8`

## callees

- `0x1800177b4`
- `0x18002b1b0`
- `0x180032ba0`
- `0x180032d3c`
- `0x180032e50`

## string_xrefs

- `0x180032b53`: `CscService,DcomLaunch,EventLog,EventSystem,gpsvc,ProfSvc,RpcSs,SENS,Themes,MMCSS,AudioEndpointBuilder,Audiosrv,Threadorder,Windefend`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
PerfDiagBoot::CAnalysisContext *__fastcall PerfDiagBoot::CAnalysisContext::CAnalysisContext(
        PerfDiagBoot::CAnalysisContext *this)
{
  PerfDiagShared::Serializer::CStringInterner::CStringInterner(this);
  PerfDiagBoot::CScenarioAnalysisContext<PerfDiagBoot::CSystemRegistryConfig,PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatSystemThresholdingConfig,1321801419>>::CScenarioAnalysisContext<PerfDiagBoot::CSystemRegistryConfig,PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatSystemThresholdingConfig,1321801419>>((char *)this + 64);
  *((_QWORD *)this + 285) = 0;
  *((_QWORD *)this + 286) = 0;
  *((_QWORD *)this + 287) = 0;
  *((_QWORD *)this + 288) = 0;
  PerfDiagBoot::CScenarioAnalysisContext<PerfDiagBoot::CUserRegistryConfig,PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatUserThresholdingConfig,2422555881>>::CScenarioAnalysisContext<PerfDiagBoot::CUserRegistryConfig,PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatUserThresholdingConfig,2422555881>>((char *)this + 2312);
  *((_QWORD *)this + 404) = 0;
  *((_QWORD *)this + 405) = 0;
  *((_DWORD *)this + 812) = 0;
  *((_QWORD *)this + 407) = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 3264);
  *((_QWORD *)this + 409) = &PerfDiagBoot::CSharedRegistryConfig::`vftable';
  *((_DWORD *)this + 820) = 20;
  *((_DWORD *)this + 821) = 10;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (char *)this + 3288,
    L"CscService,DcomLaunch,EventLog,EventSystem,gpsvc,ProfSvc,RpcSs,SENS,Themes,MMCSS,AudioEndpointBuilder,Audiosrv,Threa"
     "dorder,Windefend");
  *((_DWORD *)this + 824) = 10;
  *((_DWORD *)this + 825) = 1;
  *((_QWORD *)this + 413) = 0;
  *((_QWORD *)this + 414) = 0;
  *((_QWORD *)this + 8) = this;
  *((_QWORD *)this + 289) = this;
  return this;
}

```

## disassembly

```asm
0x180032ab0  mov     [rsp+arg_10], rbx
0x180032ab5  mov     [rsp+arg_18], rbp
0x180032aba  mov     [rsp+arg_0], rcx
0x180032abf  push    rsi
0x180032ac0  push    rdi
0x180032ac1  push    r15
0x180032ac3  sub     rsp, 20h
0x180032ac7  mov     rbp, rcx
0x180032aca  call    ??0CStringInterner@Serializer@PerfDiagShared@@QEAA@XZ; PerfDiagShared::Serializer::CStringInterner::CStringInterner(void)
0x180032acf  nop
0x180032ad0  lea     rcx, [rbp+40h]
0x180032ad4  call    ??0?$CScenarioAnalysisContext@VCSystemRegistryConfig@PerfDiagBoot@@U?$CScenarioArchiveBase@UCFlatSystemThresholdingConfig@PerfDiagBoot@@$0EOMJBGML@@2@@PerfDiagBoot@@QEAA@XZ; PerfDiagBoot::CScenarioAnalysisContext<PerfDiagBoot::CSystemRegistryConfig,PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatSystemThresholdingConfig,1321801419>>::CScenarioAnalysisContext<PerfDiagBoot::CSystemRegistryConfig,PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatSystemThresholdingConfig,1321801419>>(void)
0x180032ad9  xor     r15d, r15d
0x180032adc  mov     [rbp+8E8h], r15
0x180032ae3  mov     [rbp+8F0h], r15
0x180032aea  mov     [rbp+8F8h], r15
0x180032af1  mov     [rbp+900h], r15
0x180032af8  lea     rdi, [rbp+908h]
0x180032aff  mov     rcx, rdi
0x180032b02  call    ??0?$CScenarioAnalysisContext@VCUserRegistryConfig@PerfDiagBoot@@U?$CScenarioArchiveBase@UCFlatUserThresholdingConfig@PerfDiagBoot@@$0JAGFEEOJ@@2@@PerfDiagBoot@@QEAA@XZ; PerfDiagBoot::CScenarioAnalysisContext<PerfDiagBoot::CUserRegistryConfig,PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatUserThresholdingConfig,2422555881>>::CScenarioAnalysisContext<PerfDiagBoot::CUserRegistryConfig,PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatUserThresholdingConfig,2422555881>>(void)
0x180032b07  mov     [rdi+398h], r15
0x180032b0e  mov     [rdi+3A0h], r15
0x180032b15  mov     [rdi+3A8h], r15d
0x180032b1c  mov     [rdi+3B0h], r15
0x180032b23  lea     rcx, [rdi+3B8h]
0x180032b2a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180032b2f  nop
0x180032b30  lea     rbx, [rbp+0CC8h]
0x180032b37  lea     rax, ??_7CSharedRegistryConfig@PerfDiagBoot@@6B@; const PerfDiagBoot::CSharedRegistryConfig::`vftable'
0x180032b3e  mov     [rbx], rax
0x180032b41  mov     dword ptr [rbx+8], 14h
0x180032b48  mov     dword ptr [rbx+0Ch], 0Ah
0x180032b4f  lea     rcx, [rbx+10h]
0x180032b53  lea     rdx, aCscserviceDcom; "CscService,DcomLaunch,EventLog,EventSys"...
0x180032b5a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180032b5f  mov     dword ptr [rbx+18h], 0Ah
0x180032b66  mov     dword ptr [rbx+1Ch], 1
0x180032b6d  mov     [rbp+0CE8h], r15
0x180032b74  mov     [rbp+0CF0h], r15
0x180032b7b  mov     [rbp+40h], rbp
0x180032b7f  mov     [rdi], rbp
0x180032b82  mov     rax, rbp
0x180032b85  mov     rbx, [rsp+38h+arg_10]
0x180032b8a  mov     rbp, [rsp+38h+arg_18]
0x180032b8f  add     rsp, 20h
0x180032b93  pop     r15
0x180032b95  pop     rdi
0x180032b96  pop     rsi
0x180032b97  retn
```
