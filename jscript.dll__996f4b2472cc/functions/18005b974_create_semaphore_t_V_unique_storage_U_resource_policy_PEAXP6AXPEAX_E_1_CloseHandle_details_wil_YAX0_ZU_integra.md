# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18005b974`
- end: `0x18005b9d3`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180059ddc`

## callees

- `0x180043cc0`
- `0x180044240`
- `0x18005b974`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x18005b993`
- `KERNEL32!CreateSemaphoreExW` at `0x18005b993`
- `KERNEL32!GetLastError` at `0x18005b9a7`
- `KERNEL32!GetLastError` at `0x18005b9a7`

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
0x18005b974  mov     [rsp+arg_0], rbx
0x18005b979  push    rdi
0x18005b97a  sub     rsp, 30h
0x18005b97e  mov     rdi, rcx
0x18005b981  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18005b989  xor     ecx, ecx; lpSemaphoreAttributes
0x18005b98b  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18005b993  call    cs:__imp_CreateSemaphoreExW
0x18005b99a  nop     dword ptr [rax+rax+00h]
0x18005b99f  mov     rbx, rax
0x18005b9a2  test    rax, rax
0x18005b9a5  jz      short loc_18005B9C2
0x18005b9a7  call    cs:__imp_GetLastError
0x18005b9ae  nop     dword ptr [rax+rax+00h]
0x18005b9b3  mov     rdx, rbx
0x18005b9b6  mov     rcx, rdi
0x18005b9b9  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18005b9be  xor     eax, eax
0x18005b9c0  jmp     short loc_18005B9C7
0x18005b9c2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18005b9c7  mov     rbx, [rsp+38h+arg_0]
0x18005b9cc  add     rsp, 30h
0x18005b9d0  pop     rdi
0x18005b9d1  retn
```
