# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18000b614`
- end: `0x18000b6af`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `155`
- prototype: `__int64 __fastcall(void **, LONG, LONG, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006200`

## callees

- `0x180007080`
- `0x18000b5ac`
- `0x18000b614`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000b632`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000b632`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b67d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b67d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b646`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b65a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b646`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b65a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b66b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b66b`

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
0x18000b614  push    rbx
0x18000b616  push    rbp
0x18000b617  push    rsi
0x18000b618  push    rdi
0x18000b619  sub     rsp, 38h
0x18000b61d  mov     rdi, rcx
0x18000b620  mov     [rsp+58h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000b628  xor     ecx, ecx; lpSemaphoreAttributes
0x18000b62a  mov     [rsp+58h+dwFlags], 0; dwFlags
0x18000b632  call    cs:__imp_CreateSemaphoreExW
0x18000b639  nop     dword ptr [rax+rax+00h]
0x18000b63e  mov     rbp, rax
0x18000b641  test    rax, rax
0x18000b644  jz      short loc_18000B690
0x18000b646  call    cs:__imp_GetLastError
0x18000b64d  nop     dword ptr [rax+rax+00h]
0x18000b652  mov     rbx, [rdi]
0x18000b655  test    rbx, rbx
0x18000b658  jz      short loc_18000B689
0x18000b65a  call    cs:__imp_GetLastError
0x18000b661  nop     dword ptr [rax+rax+00h]
0x18000b666  mov     rcx, rbx; hObject
0x18000b669  mov     esi, eax
0x18000b66b  call    cs:__imp_CloseHandle
0x18000b672  nop     dword ptr [rax+rax+00h]
0x18000b677  test    eax, eax
0x18000b679  jz      short loc_18000B69F
0x18000b67b  mov     ecx, esi; dwErrCode
0x18000b67d  call    cs:__imp_SetLastError
0x18000b684  nop     dword ptr [rax+rax+00h]
0x18000b689  mov     [rdi], rbp
0x18000b68c  xor     eax, eax
0x18000b68e  jmp     short loc_18000B695
0x18000b690  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000b695  add     rsp, 38h
0x18000b699  pop     rdi
0x18000b69a  pop     rsi
0x18000b69b  pop     rbp
0x18000b69c  pop     rbx
0x18000b69d  retn
0x18000b69f  mov     rcx, [rsp+58h]; this
0x18000b6a4  mov     edx, 0A0Bh; void *
0x18000b6a9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
