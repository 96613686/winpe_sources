# ?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x140010d70`
- end: `0x140010dc2`
- name: `?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000ea80`

## callees

- `0x14000725c`
- `0x1400092a8`
- `0x140010d70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010d9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010d9d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140010d8f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140010d8f`

## pseudocode

```c
__int64 __fastcall _create___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1)
{
  wil::details *v2; // rcx
  HANDLE Mutex; // rbx

  Mutex = CreateMutexExW(0, L"Local\\RdpDisplayControlMutex", 0, 0x1F0001u);
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v2);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    a1,
    Mutex);
  return 0;
}

```

## disassembly

```asm
0x140010d70  mov     [rsp+arg_0], rbx
0x140010d75  push    rdi
0x140010d76  sub     rsp, 20h
0x140010d7a  mov     rdi, rcx
0x140010d7d  lea     rdx, aLocalRdpdispla; "Local\\RdpDisplayControlMutex"
0x140010d84  xor     ecx, ecx; lpMutexAttributes
0x140010d86  mov     r9d, 1F0001h; dwDesiredAccess
0x140010d8c  xor     r8d, r8d; dwFlags
0x140010d8f  call    cs:__imp_CreateMutexExW
0x140010d95  mov     rbx, rax
0x140010d98  test    rax, rax
0x140010d9b  jz      short loc_140010DB2
0x140010d9d  call    cs:__imp_GetLastError
0x140010da3  mov     rdx, rbx
0x140010da6  mov     rcx, rdi
0x140010da9  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140010dae  xor     eax, eax
0x140010db0  jmp     short loc_140010DB7
0x140010db2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140010db7  mov     rbx, [rsp+28h+arg_0]
0x140010dbc  add     rsp, 20h
0x140010dc0  pop     rdi
0x140010dc1  retn
```
