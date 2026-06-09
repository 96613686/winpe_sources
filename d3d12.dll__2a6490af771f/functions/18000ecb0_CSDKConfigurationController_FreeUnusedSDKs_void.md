# CSDKConfigurationController::FreeUnusedSDKs(void)

- ea: `0x18000ecb0`
- end: `0x18000ecdc`
- name: `?FreeUnusedSDKs@CSDKConfigurationController@@UEAAXXZ`
- size: `44`
- prototype: `void __fastcall(CSDKConfigurationController *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18000afcc`
- `0x18000afec`
- `0x18000fde0`

## pseudocode

```c
void __fastcall CSDKConfigurationController::FreeUnusedSDKs(CSDKConfigurationController *this)
{
  Smtx_lock_exclusive(&qword_18001E7F8);
  CModule::FreeUnusedModules((CModule *)&g_Module);
  Smtx_unlock_exclusive(&qword_18001E7F8);
}

```

## disassembly

```asm
0x18000ecb0  sub     rsp, 28h
0x18000ecb4  lea     rcx, qword_18001E7F8; _Smtx_t *
0x18000ecbb  call    _Smtx_lock_exclusive
0x18000ecc0  lea     rcx, ?g_Module@@3VCModule@@A; this
0x18000ecc7  call    ?FreeUnusedModules@CModule@@QEAAXXZ; CModule::FreeUnusedModules(void)
0x18000eccc  lea     rcx, qword_18001E7F8; _Smtx_t *
0x18000ecd3  add     rsp, 28h
0x18000ecd7  jmp     _Smtx_unlock_exclusive
```
