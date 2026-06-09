# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180023e5c`
- end: `0x180023ebb`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `95`
- prototype: `__int64 __fastcall(__int64, LONG, LONG, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800200e4`

## callees

- `0x18001be38`
- `0x180023e5c`
- `0x180023f84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180023e7b`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180023e7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e8f`

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
0x180023e5c  mov     [rsp+arg_0], rbx
0x180023e61  push    rdi
0x180023e62  sub     rsp, 30h
0x180023e66  mov     rdi, rcx
0x180023e69  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180023e71  xor     ecx, ecx; lpSemaphoreAttributes
0x180023e73  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180023e7b  call    cs:__imp_CreateSemaphoreExW
0x180023e82  nop     dword ptr [rax+rax+00h]
0x180023e87  mov     rbx, rax
0x180023e8a  test    rax, rax
0x180023e8d  jz      short loc_180023EAA
0x180023e8f  call    cs:__imp_GetLastError
0x180023e96  nop     dword ptr [rax+rax+00h]
0x180023e9b  mov     rdx, rbx
0x180023e9e  mov     rcx, rdi
0x180023ea1  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180023ea6  xor     eax, eax
0x180023ea8  jmp     short loc_180023EAF
0x180023eaa  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180023eaf  mov     rbx, [rsp+38h+arg_0]
0x180023eb4  add     rsp, 30h
0x180023eb8  pop     rdi
0x180023eb9  retn
```
