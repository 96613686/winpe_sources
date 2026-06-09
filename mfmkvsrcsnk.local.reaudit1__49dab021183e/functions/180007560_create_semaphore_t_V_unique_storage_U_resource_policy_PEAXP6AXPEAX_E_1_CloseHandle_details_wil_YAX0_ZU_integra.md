# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180007560`
- end: `0x1800075bf`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004c24`

## callees

- `0x1800055e0`
- `0x180007560`
- `0x1800075c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000757f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000757f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007593`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007593`

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
0x180007560  mov     [rsp+arg_0], rbx
0x180007565  push    rdi
0x180007566  sub     rsp, 30h
0x18000756a  mov     rdi, rcx
0x18000756d  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180007575  xor     ecx, ecx; lpSemaphoreAttributes
0x180007577  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18000757f  call    cs:__imp_CreateSemaphoreExW
0x180007586  nop     dword ptr [rax+rax+00h]
0x18000758b  mov     rbx, rax
0x18000758e  test    rax, rax
0x180007591  jz      short loc_1800075AE
0x180007593  call    cs:__imp_GetLastError
0x18000759a  nop     dword ptr [rax+rax+00h]
0x18000759f  mov     rdx, rbx
0x1800075a2  mov     rcx, rdi
0x1800075a5  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800075aa  xor     eax, eax
0x1800075ac  jmp     short loc_1800075B3
0x1800075ae  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800075b3  mov     rbx, [rsp+38h+arg_0]
0x1800075b8  add     rsp, 30h
0x1800075bc  pop     rdi
0x1800075bd  retn
```
