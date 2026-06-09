# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180022e0c`
- end: `0x180022e5e`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f904`

## callees

- `0x180012690`
- `0x180022e0c`
- `0x180022f0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022e39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022e39`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180022e2b`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180022e2b`

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
0x180022e0c  mov     [rsp+arg_0], rbx
0x180022e11  push    rdi
0x180022e12  sub     rsp, 30h
0x180022e16  mov     rdi, rcx
0x180022e19  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180022e21  xor     ecx, ecx; lpSemaphoreAttributes
0x180022e23  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180022e2b  call    cs:__imp_CreateSemaphoreExW
0x180022e31  mov     rbx, rax
0x180022e34  test    rax, rax
0x180022e37  jz      short loc_180022E4E
0x180022e39  call    cs:__imp_GetLastError
0x180022e3f  mov     rdx, rbx
0x180022e42  mov     rcx, rdi
0x180022e45  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180022e4a  xor     eax, eax
0x180022e4c  jmp     short loc_180022E53
0x180022e4e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180022e53  mov     rbx, [rsp+38h+arg_0]
0x180022e58  add     rsp, 30h
0x180022e5c  pop     rdi
0x180022e5d  retn
```
