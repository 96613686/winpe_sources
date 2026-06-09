# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18001d190`
- end: `0x18001d1e2`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017a6c`

## callees

- `0x180019900`
- `0x18001d190`
- `0x18001d714`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d1bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d1bd`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18001d1af`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18001d1af`

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
0x18001d190  mov     [rsp+arg_0], rbx
0x18001d195  push    rdi
0x18001d196  sub     rsp, 30h
0x18001d19a  mov     rdi, rcx
0x18001d19d  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18001d1a5  xor     ecx, ecx; lpSemaphoreAttributes
0x18001d1a7  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18001d1af  call    cs:__imp_CreateSemaphoreExW
0x18001d1b5  mov     rbx, rax
0x18001d1b8  test    rax, rax
0x18001d1bb  jz      short loc_18001D1D2
0x18001d1bd  call    cs:__imp_GetLastError
0x18001d1c3  mov     rdx, rbx
0x18001d1c6  mov     rcx, rdi
0x18001d1c9  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001d1ce  xor     eax, eax
0x18001d1d0  jmp     short loc_18001D1D7
0x18001d1d2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001d1d7  mov     rbx, [rsp+38h+arg_0]
0x18001d1dc  add     rsp, 30h
0x18001d1e0  pop     rdi
0x18001d1e1  retn
```
