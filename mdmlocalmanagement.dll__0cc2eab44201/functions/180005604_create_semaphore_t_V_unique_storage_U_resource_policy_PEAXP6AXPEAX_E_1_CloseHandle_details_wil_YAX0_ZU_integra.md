# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180005604`
- end: `0x18000569f`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004210`

## callees

- `0x1800037f0`
- `0x1800055e8`
- `0x180005604`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005622`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005622`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000566d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000566d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005636`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000564a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005636`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000564a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000565b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000565b`

## pseudocode

```c
__int64 __fastcall _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1,
        LONG a2,
        LONG a3,
        const WCHAR *a4)
{
  wil::details *v5; // rcx
  HANDLE Semaphore; // rbp
  void *v7; // rbx
  DWORD LastError; // esi
  unsigned int v9; // r8d
  const char *v10; // r9
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  Semaphore = CreateSemaphoreExW(0, a2, a3, a4, 0, 0x1F0003u);
  if ( !Semaphore )
    return wil::details::GetLastErrorFailHr(v5);
  GetLastError();
  v7 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v7) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v9, v10);
    SetLastError(LastError);
  }
  *a1 = Semaphore;
  return 0;
}

```

## disassembly

```asm
0x180005604  push    rbx
0x180005606  push    rbp
0x180005607  push    rsi
0x180005608  push    rdi
0x180005609  sub     rsp, 38h
0x18000560d  mov     rdi, rcx
0x180005610  mov     [rsp+58h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180005618  xor     ecx, ecx; lpSemaphoreAttributes
0x18000561a  mov     [rsp+58h+dwFlags], 0; dwFlags
0x180005622  call    cs:__imp_CreateSemaphoreExW
0x180005629  nop     dword ptr [rax+rax+00h]
0x18000562e  mov     rbp, rax
0x180005631  test    rax, rax
0x180005634  jz      short loc_180005680
0x180005636  call    cs:__imp_GetLastError
0x18000563d  nop     dword ptr [rax+rax+00h]
0x180005642  mov     rbx, [rdi]
0x180005645  test    rbx, rbx
0x180005648  jz      short loc_180005679
0x18000564a  call    cs:__imp_GetLastError
0x180005651  nop     dword ptr [rax+rax+00h]
0x180005656  mov     rcx, rbx; hObject
0x180005659  mov     esi, eax
0x18000565b  call    cs:__imp_CloseHandle
0x180005662  nop     dword ptr [rax+rax+00h]
0x180005667  test    eax, eax
0x180005669  jz      short loc_18000568F
0x18000566b  mov     ecx, esi; dwErrCode
0x18000566d  call    cs:__imp_SetLastError
0x180005674  nop     dword ptr [rax+rax+00h]
0x180005679  mov     [rdi], rbp
0x18000567c  xor     eax, eax
0x18000567e  jmp     short loc_180005685
0x180005680  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005685  add     rsp, 38h
0x180005689  pop     rdi
0x18000568a  pop     rsi
0x18000568b  pop     rbp
0x18000568c  pop     rbx
0x18000568d  retn
0x18000568f  mov     rcx, [rsp+58h]; this
0x180005694  mov     edx, 0A0Bh; void *
0x180005699  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
