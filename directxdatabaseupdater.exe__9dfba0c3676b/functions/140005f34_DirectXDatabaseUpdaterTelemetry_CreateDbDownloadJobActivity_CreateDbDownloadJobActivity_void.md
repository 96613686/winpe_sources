# DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity::~CreateDbDownloadJobActivity(void)

- ea: `0x140005f34`
- end: `0x140005f59`
- name: `??1CreateDbDownloadJobActivity@DirectXDatabaseUpdaterTelemetry@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000b0cc`
- `0x140018a06`

## callees

- `0x140005884`
- `0x140006b80`

## pseudocode

```c
void __fastcall DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity::~CreateDbDownloadJobActivity(
        DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity *this)
{
  *(_QWORD *)this = &DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity::`vftable';
  wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy();
  wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)this);
}

```

## disassembly

```asm
0x140005f34  push    rbx
0x140005f36  sub     rsp, 20h
0x140005f3a  lea     rax, ??_7CreateDbDownloadJobActivity@DirectXDatabaseUpdaterTelemetry@@6B@; const DirectXDatabaseUpdaterTelemetry::CreateDbDownloadJobActivity::`vftable'
0x140005f41  mov     rbx, rcx
0x140005f44  mov     [rcx], rax
0x140005f47  call    ?Destroy@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140005f4c  mov     rcx, rbx
0x140005f4f  add     rsp, 20h
0x140005f53  pop     rbx
0x140005f54  jmp     ??1?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
```
