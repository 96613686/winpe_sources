# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18000bb20`
- end: `0x18000bb72`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: `__int64 __fastcall(__int64, LONG, LONG, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006d74`

## callees

- `0x180007d08`
- `0x18000bb20`
- `0x18000bd1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000bb3f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000bb3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb4d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1,
        LONG a2,
        LONG a3,
        const WCHAR *a4)
{
  wil::details *v5; // rcx
  HANDLE Semaphore; // rbx

  Semaphore = CreateSemaphoreExW(0, a2, a3, a4, 0, 0x1F0003u);
  if ( !Semaphore )
    return wil::details::GetLastErrorFailHr(v5);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    a1,
    Semaphore);
  return 0;
}

```

## disassembly

```asm
0x18000bb20  mov     [rsp+arg_0], rbx
0x18000bb25  push    rdi
0x18000bb26  sub     rsp, 30h
0x18000bb2a  mov     rdi, rcx
0x18000bb2d  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000bb35  xor     ecx, ecx; lpSemaphoreAttributes
0x18000bb37  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18000bb3f  call    cs:__imp_CreateSemaphoreExW
0x18000bb45  mov     rbx, rax
0x18000bb48  test    rax, rax
0x18000bb4b  jz      short loc_18000BB62
0x18000bb4d  call    cs:__imp_GetLastError
0x18000bb53  mov     rdx, rbx
0x18000bb56  mov     rcx, rdi
0x18000bb59  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000bb5e  xor     eax, eax
0x18000bb60  jmp     short loc_18000BB67
0x18000bb62  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000bb67  mov     rbx, [rsp+38h+arg_0]
0x18000bb6c  add     rsp, 30h
0x18000bb70  pop     rdi
0x18000bb71  retn
```
