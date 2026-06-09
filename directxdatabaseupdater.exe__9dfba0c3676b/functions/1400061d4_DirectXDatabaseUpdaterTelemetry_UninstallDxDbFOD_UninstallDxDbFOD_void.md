# DirectXDatabaseUpdaterTelemetry::UninstallDxDbFOD::~UninstallDxDbFOD(void)

- ea: `0x1400061d4`
- end: `0x1400061f9`
- name: `??1UninstallDxDbFOD@DirectXDatabaseUpdaterTelemetry@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(DirectXDatabaseUpdaterTelemetry::UninstallDxDbFOD *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140007ad8`
- `0x1400186dc`

## callees

- `0x140005884`
- `0x140006b80`

## pseudocode

```c
void __fastcall DirectXDatabaseUpdaterTelemetry::UninstallDxDbFOD::~UninstallDxDbFOD(
        DirectXDatabaseUpdaterTelemetry::UninstallDxDbFOD *this)
{
  *(_QWORD *)this = &DirectXDatabaseUpdaterTelemetry::UninstallDxDbFOD::`vftable';
  wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy();
  wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)this);
}

```

## disassembly

```asm
0x1400061d4  push    rbx
0x1400061d6  sub     rsp, 20h
0x1400061da  lea     rax, ??_7UninstallDxDbFOD@DirectXDatabaseUpdaterTelemetry@@6B@; const DirectXDatabaseUpdaterTelemetry::UninstallDxDbFOD::`vftable'
0x1400061e1  mov     rbx, rcx
0x1400061e4  mov     [rcx], rax
0x1400061e7  call    ?Destroy@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1400061ec  mov     rcx, rbx
0x1400061ef  add     rsp, 20h
0x1400061f3  pop     rbx
0x1400061f4  jmp     ??1?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
```
