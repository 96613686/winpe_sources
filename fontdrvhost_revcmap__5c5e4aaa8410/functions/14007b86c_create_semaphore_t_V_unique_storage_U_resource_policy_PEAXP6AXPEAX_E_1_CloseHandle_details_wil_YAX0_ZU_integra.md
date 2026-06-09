# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x14007b86c`
- end: `0x14007b8be`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400783b8`

## callees

- `0x140078d78`
- `0x14007b86c`
- `0x14007b9fc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14007b899`
- `KERNEL32!GetLastError` at `0x14007b899`
- `KERNEL32!CreateSemaphoreExW` at `0x14007b88b`
- `KERNEL32!CreateSemaphoreExW` at `0x14007b88b`

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
0x14007b86c  mov     [rsp+arg_0], rbx
0x14007b871  push    rdi
0x14007b872  sub     rsp, 30h
0x14007b876  mov     rdi, rcx
0x14007b879  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x14007b881  xor     ecx, ecx; lpSemaphoreAttributes
0x14007b883  mov     [rsp+38h+dwFlags], 0; dwFlags
0x14007b88b  call    cs:__imp_CreateSemaphoreExW
0x14007b891  mov     rbx, rax
0x14007b894  test    rax, rax
0x14007b897  jz      short loc_14007B8AE
0x14007b899  call    cs:__imp_GetLastError
0x14007b89f  mov     rdx, rbx
0x14007b8a2  mov     rcx, rdi
0x14007b8a5  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x14007b8aa  xor     eax, eax
0x14007b8ac  jmp     short loc_14007B8B3
0x14007b8ae  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14007b8b3  mov     rbx, [rsp+38h+arg_0]
0x14007b8b8  add     rsp, 30h
0x14007b8bc  pop     rdi
0x14007b8bd  retn
```
