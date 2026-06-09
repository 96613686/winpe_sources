# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x14000ebc0`
- end: `0x14000ec12`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140009dcc`

## callees

- `0x14000ae58`
- `0x14000ebc0`
- `0x14000eda4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000ebed`
- `KERNEL32!GetLastError` at `0x14000ebed`
- `KERNEL32!CreateSemaphoreExW` at `0x14000ebdf`
- `KERNEL32!CreateSemaphoreExW` at `0x14000ebdf`

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
0x14000ebc0  mov     [rsp+arg_0], rbx
0x14000ebc5  push    rdi
0x14000ebc6  sub     rsp, 30h
0x14000ebca  mov     rdi, rcx
0x14000ebcd  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x14000ebd5  xor     ecx, ecx; lpSemaphoreAttributes
0x14000ebd7  mov     [rsp+38h+dwFlags], 0; dwFlags
0x14000ebdf  call    cs:__imp_CreateSemaphoreExW
0x14000ebe5  mov     rbx, rax
0x14000ebe8  test    rax, rax
0x14000ebeb  jz      short loc_14000EC02
0x14000ebed  call    cs:__imp_GetLastError
0x14000ebf3  mov     rdx, rbx
0x14000ebf6  mov     rcx, rdi
0x14000ebf9  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x14000ebfe  xor     eax, eax
0x14000ec00  jmp     short loc_14000EC07
0x14000ec02  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000ec07  mov     rbx, [rsp+38h+arg_0]
0x14000ec0c  add     rsp, 30h
0x14000ec10  pop     rdi
0x14000ec11  retn
```
