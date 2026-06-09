# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18001d4d4`
- end: `0x18001d526`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: `__int64 __fastcall(__int64, LONG, LONG, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017018`

## callees

- `0x180009634`
- `0x18000c7a8`
- `0x18001d4d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18001d4f3`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18001d4f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d501`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d501`

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
0x18001d4d4  mov     [rsp+arg_0], rbx
0x18001d4d9  push    rdi
0x18001d4da  sub     rsp, 30h
0x18001d4de  mov     rdi, rcx
0x18001d4e1  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18001d4e9  xor     ecx, ecx; lpSemaphoreAttributes
0x18001d4eb  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18001d4f3  call    cs:__imp_CreateSemaphoreExW
0x18001d4f9  mov     rbx, rax
0x18001d4fc  test    rax, rax
0x18001d4ff  jz      short loc_18001D516
0x18001d501  call    cs:__imp_GetLastError
0x18001d507  mov     rdx, rbx
0x18001d50a  mov     rcx, rdi
0x18001d50d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001d512  xor     eax, eax
0x18001d514  jmp     short loc_18001D51B
0x18001d516  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001d51b  mov     rbx, [rsp+38h+arg_0]
0x18001d520  add     rsp, 30h
0x18001d524  pop     rdi
0x18001d525  retn
```
