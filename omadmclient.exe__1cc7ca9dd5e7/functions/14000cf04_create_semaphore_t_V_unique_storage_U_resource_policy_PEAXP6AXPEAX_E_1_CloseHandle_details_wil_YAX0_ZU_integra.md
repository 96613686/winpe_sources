# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x14000cf04`
- end: `0x14000cf9f`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400079a4`

## callees

- `0x1400089a8`
- `0x14000ce7c`
- `0x14000cf04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000cf22`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000cf22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cf36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cf4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cf36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cf4a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000cf6d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000cf6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000cf5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000cf5b`

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
0x14000cf04  push    rbx
0x14000cf06  push    rbp
0x14000cf07  push    rsi
0x14000cf08  push    rdi
0x14000cf09  sub     rsp, 38h
0x14000cf0d  mov     rdi, rcx
0x14000cf10  mov     [rsp+58h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x14000cf18  xor     ecx, ecx; lpSemaphoreAttributes
0x14000cf1a  mov     [rsp+58h+dwFlags], 0; dwFlags
0x14000cf22  call    cs:__imp_CreateSemaphoreExW
0x14000cf29  nop     dword ptr [rax+rax+00h]
0x14000cf2e  mov     rbp, rax
0x14000cf31  test    rax, rax
0x14000cf34  jz      short loc_14000CF80
0x14000cf36  call    cs:__imp_GetLastError
0x14000cf3d  nop     dword ptr [rax+rax+00h]
0x14000cf42  mov     rbx, [rdi]
0x14000cf45  test    rbx, rbx
0x14000cf48  jz      short loc_14000CF79
0x14000cf4a  call    cs:__imp_GetLastError
0x14000cf51  nop     dword ptr [rax+rax+00h]
0x14000cf56  mov     rcx, rbx; hObject
0x14000cf59  mov     esi, eax
0x14000cf5b  call    cs:__imp_CloseHandle
0x14000cf62  nop     dword ptr [rax+rax+00h]
0x14000cf67  test    eax, eax
0x14000cf69  jz      short loc_14000CF8F
0x14000cf6b  mov     ecx, esi; dwErrCode
0x14000cf6d  call    cs:__imp_SetLastError
0x14000cf74  nop     dword ptr [rax+rax+00h]
0x14000cf79  mov     [rdi], rbp
0x14000cf7c  xor     eax, eax
0x14000cf7e  jmp     short loc_14000CF85
0x14000cf80  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000cf85  add     rsp, 38h
0x14000cf89  pop     rdi
0x14000cf8a  pop     rsi
0x14000cf8b  pop     rbp
0x14000cf8c  pop     rbx
0x14000cf8d  retn
0x14000cf8f  mov     rcx, [rsp+58h]; this
0x14000cf94  mov     edx, 0A0Bh; void *
0x14000cf99  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
