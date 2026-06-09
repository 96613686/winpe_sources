# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x1800097ec`
- end: `0x18000983e`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000556c`

## callees

- `0x180007808`
- `0x1800097ec`
- `0x180009888`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009819`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009819`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000980b`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000980b`

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
0x1800097ec  mov     [rsp+arg_0], rbx
0x1800097f1  push    rdi
0x1800097f2  sub     rsp, 30h
0x1800097f6  mov     rdi, rcx
0x1800097f9  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180009801  xor     ecx, ecx; lpSemaphoreAttributes
0x180009803  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18000980b  call    cs:__imp_CreateSemaphoreExW
0x180009811  mov     rbx, rax
0x180009814  test    rax, rax
0x180009817  jz      short loc_18000982E
0x180009819  call    cs:__imp_GetLastError
0x18000981f  mov     rdx, rbx
0x180009822  mov     rcx, rdi
0x180009825  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000982a  xor     eax, eax
0x18000982c  jmp     short loc_180009833
0x18000982e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009833  mov     rbx, [rsp+38h+arg_0]
0x180009838  add     rsp, 30h
0x18000983c  pop     rdi
0x18000983d  retn
```
