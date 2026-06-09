# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18042b3f4`
- end: `0x18042b45b`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1804263f0`

## callees

- `0x1804270c0`
- `0x18042b3f4`
- `0x18042b61c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18042b41b`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18042b41b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18042b42f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18042b42f`

## pseudocode

```c
__int64 __fastcall _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1,
        LONG a2,
        LONG a3,
        const WCHAR *a4)
{
  wil::details *v4; // rcx
  HANDLE Semaphore; // rbx

  Semaphore = CreateSemaphoreExW(0, a2, a3, a4, 0, 0x1F0003u);
  if ( !Semaphore )
    return wil::details::GetLastErrorFailHr(v4);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    a1,
    Semaphore);
  return 0;
}

```

## disassembly

```asm
0x18042b3f4  mov     rax, rsp
0x18042b3f7  mov     [rax+20h], r9
0x18042b3fb  mov     [rax+18h], r8d
0x18042b3ff  mov     [rax+10h], edx
0x18042b402  mov     [rax+8], rcx
0x18042b406  push    rbx
0x18042b407  sub     rsp, 30h
0x18042b40b  mov     dword ptr [rax-10h], 1F0003h
0x18042b412  xor     ecx, ecx; lpSemaphoreAttributes
0x18042b414  mov     dword ptr [rax-18h], 0
0x18042b41b  call    cs:__imp_CreateSemaphoreExW
0x18042b422  nop     dword ptr [rax+rax+00h]
0x18042b427  mov     rbx, rax
0x18042b42a  test    rax, rax
0x18042b42d  jz      short loc_18042B451
0x18042b42f  call    cs:__imp_GetLastError
0x18042b436  nop     dword ptr [rax+rax+00h]
0x18042b43b  mov     rcx, [rsp+38h+arg_0]
0x18042b440  mov     rdx, rbx
0x18042b443  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18042b448  xor     eax, eax
0x18042b44a  add     rsp, 30h
0x18042b44e  pop     rbx
0x18042b44f  retn
0x18042b451  add     rsp, 30h
0x18042b455  pop     rbx
0x18042b456  jmp     ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
```
