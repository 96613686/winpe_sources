# DirectXDatabaseUpdaterTelemetry::WriteLastRunData::~WriteLastRunData(void)

- ea: `0x14000629c`
- end: `0x1400062c1`
- name: `??1WriteLastRunData@DirectXDatabaseUpdaterTelemetry@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(DirectXDatabaseUpdaterTelemetry::WriteLastRunData *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000f2a4`
- `0x140018ac2`

## callees

- `0x140005884`
- `0x140006b80`

## pseudocode

```c
void __fastcall DirectXDatabaseUpdaterTelemetry::WriteLastRunData::~WriteLastRunData(
        DirectXDatabaseUpdaterTelemetry::WriteLastRunData *this)
{
  *(_QWORD *)this = &DirectXDatabaseUpdaterTelemetry::WriteLastRunData::`vftable';
  wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy();
  wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)this);
}

```

## disassembly

```asm
0x14000629c  push    rbx
0x14000629e  sub     rsp, 20h
0x1400062a2  lea     rax, ??_7WriteLastRunData@DirectXDatabaseUpdaterTelemetry@@6B@; const DirectXDatabaseUpdaterTelemetry::WriteLastRunData::`vftable'
0x1400062a9  mov     rbx, rcx
0x1400062ac  mov     [rcx], rax
0x1400062af  call    ?Destroy@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1400062b4  mov     rcx, rbx
0x1400062b7  add     rsp, 20h
0x1400062bb  pop     rbx
0x1400062bc  jmp     ??1?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
```
