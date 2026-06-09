# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180007b68`
- end: `0x180007bba`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: `__int64 __fastcall(__int64, LONG, LONG, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003c08`

## callees

- `0x180004618`
- `0x180007b68`
- `0x180008010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180007b95`
- `KERNEL32!GetLastError` at `0x180007b95`
- `KERNEL32!CreateSemaphoreExW` at `0x180007b87`
- `KERNEL32!CreateSemaphoreExW` at `0x180007b87`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180007b68  mov     [rsp+arg_0], rbx
0x180007b6d  push    rdi
0x180007b6e  sub     rsp, 30h
0x180007b72  mov     rdi, rcx
0x180007b75  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180007b7d  xor     ecx, ecx; lpSemaphoreAttributes
0x180007b7f  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180007b87  call    cs:__imp_CreateSemaphoreExW
0x180007b8d  mov     rbx, rax
0x180007b90  test    rax, rax
0x180007b93  jz      short loc_180007BAA
0x180007b95  call    cs:__imp_GetLastError
0x180007b9b  mov     rdx, rbx
0x180007b9e  mov     rcx, rdi
0x180007ba1  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180007ba6  xor     eax, eax
0x180007ba8  jmp     short loc_180007BAF
0x180007baa  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007baf  mov     rbx, [rsp+38h+arg_0]
0x180007bb4  add     rsp, 30h
0x180007bb8  pop     rdi
0x180007bb9  retn
```
