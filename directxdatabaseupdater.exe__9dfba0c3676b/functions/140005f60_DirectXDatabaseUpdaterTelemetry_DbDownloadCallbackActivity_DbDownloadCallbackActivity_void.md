# DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity::~DbDownloadCallbackActivity(void)

- ea: `0x140005f60`
- end: `0x140005f85`
- name: `??1DbDownloadCallbackActivity@DirectXDatabaseUpdaterTelemetry@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140007ad8`
- `0x140018694`

## callees

- `0x140005884`
- `0x140006b80`

## pseudocode

```c
void __fastcall DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity::~DbDownloadCallbackActivity(
        DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity *this)
{
  *(_QWORD *)this = &DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity::`vftable';
  wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy();
  wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)this);
}

```

## disassembly

```asm
0x140005f60  push    rbx
0x140005f62  sub     rsp, 20h
0x140005f66  lea     rax, ??_7DbDownloadCallbackActivity@DirectXDatabaseUpdaterTelemetry@@6B@; const DirectXDatabaseUpdaterTelemetry::DbDownloadCallbackActivity::`vftable'
0x140005f6d  mov     rbx, rcx
0x140005f70  mov     [rcx], rax
0x140005f73  call    ?Destroy@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140005f78  mov     rcx, rbx
0x140005f7b  add     rsp, 20h
0x140005f7f  pop     rbx
0x140005f80  jmp     ??1?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
```
