# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x140006370`
- end: `0x1400063c2`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: `__int64 __fastcall(__int64, LONG, LONG, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140004190`

## callees

- `0x1400048a0`
- `0x140006370`
- `0x1400063c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000638f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000638f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000639d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000639d`

## pseudocode

```c
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
0x140006370  mov     [rsp+arg_0], rbx
0x140006375  push    rdi
0x140006376  sub     rsp, 30h
0x14000637a  mov     rdi, rcx
0x14000637d  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140006385  xor     ecx, ecx; lpSemaphoreAttributes
0x140006387  mov     [rsp+38h+dwFlags], 0; dwFlags
0x14000638f  call    cs:__imp_CreateSemaphoreExW
0x140006395  mov     rbx, rax
0x140006398  test    rax, rax
0x14000639b  jz      short loc_1400063B2
0x14000639d  call    cs:__imp_GetLastError
0x1400063a3  mov     rdx, rbx
0x1400063a6  mov     rcx, rdi
0x1400063a9  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1400063ae  xor     eax, eax
0x1400063b0  jmp     short loc_1400063B7
0x1400063b2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400063b7  mov     rbx, [rsp+38h+arg_0]
0x1400063bc  add     rsp, 30h
0x1400063c0  pop     rdi
0x1400063c1  retn
```
