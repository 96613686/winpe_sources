# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18001da3c`
- end: `0x18001da9b`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019270`

## callees

- `0x1800136d4`
- `0x18001da3c`
- `0x18001db50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18001da5b`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18001da5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da6f`

## pseudocode

```c
__int64 __fastcall _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
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
0x18001da3c  mov     [rsp+arg_0], rbx
0x18001da41  push    rdi
0x18001da42  sub     rsp, 30h
0x18001da46  mov     rdi, rcx
0x18001da49  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18001da51  xor     ecx, ecx; lpSemaphoreAttributes
0x18001da53  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18001da5b  call    cs:__imp_CreateSemaphoreExW
0x18001da62  nop     dword ptr [rax+rax+00h]
0x18001da67  mov     rbx, rax
0x18001da6a  test    rax, rax
0x18001da6d  jz      short loc_18001DA8A
0x18001da6f  call    cs:__imp_GetLastError
0x18001da76  nop     dword ptr [rax+rax+00h]
0x18001da7b  mov     rdx, rbx
0x18001da7e  mov     rcx, rdi
0x18001da81  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001da86  xor     eax, eax
0x18001da88  jmp     short loc_18001DA8F
0x18001da8a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001da8f  mov     rbx, [rsp+38h+arg_0]
0x18001da94  add     rsp, 30h
0x18001da98  pop     rdi
0x18001da99  retn
```
