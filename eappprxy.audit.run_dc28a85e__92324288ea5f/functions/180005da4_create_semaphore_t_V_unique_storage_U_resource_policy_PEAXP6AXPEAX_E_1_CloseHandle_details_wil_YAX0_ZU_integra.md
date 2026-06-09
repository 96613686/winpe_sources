# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180005da4`
- end: `0x180005e3f`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800045a0`

## callees

- `0x180003b10`
- `0x180005d88`
- `0x180005da4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005dd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005dea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005dd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005dea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005e0d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005e0d`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005dc2`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005dc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005dfb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005dfb`

## pseudocode

```c
__int64 __fastcall _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
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
0x180005da4  push    rbx
0x180005da6  push    rbp
0x180005da7  push    rsi
0x180005da8  push    rdi
0x180005da9  sub     rsp, 38h
0x180005dad  mov     rdi, rcx
0x180005db0  mov     [rsp+58h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180005db8  xor     ecx, ecx; lpSemaphoreAttributes
0x180005dba  mov     [rsp+58h+dwFlags], 0; dwFlags
0x180005dc2  call    cs:__imp_CreateSemaphoreExW
0x180005dc9  nop     dword ptr [rax+rax+00h]
0x180005dce  mov     rbp, rax
0x180005dd1  test    rax, rax
0x180005dd4  jz      short loc_180005E20
0x180005dd6  call    cs:__imp_GetLastError
0x180005ddd  nop     dword ptr [rax+rax+00h]
0x180005de2  mov     rbx, [rdi]
0x180005de5  test    rbx, rbx
0x180005de8  jz      short loc_180005E19
0x180005dea  call    cs:__imp_GetLastError
0x180005df1  nop     dword ptr [rax+rax+00h]
0x180005df6  mov     rcx, rbx; hObject
0x180005df9  mov     esi, eax
0x180005dfb  call    cs:__imp_CloseHandle
0x180005e02  nop     dword ptr [rax+rax+00h]
0x180005e07  test    eax, eax
0x180005e09  jz      short loc_180005E2F
0x180005e0b  mov     ecx, esi; dwErrCode
0x180005e0d  call    cs:__imp_SetLastError
0x180005e14  nop     dword ptr [rax+rax+00h]
0x180005e19  mov     [rdi], rbp
0x180005e1c  xor     eax, eax
0x180005e1e  jmp     short loc_180005E25
0x180005e20  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005e25  add     rsp, 38h
0x180005e29  pop     rdi
0x180005e2a  pop     rsi
0x180005e2b  pop     rbp
0x180005e2c  pop     rbx
0x180005e2d  retn
0x180005e2f  mov     rcx, [rsp+58h]; this
0x180005e34  mov     edx, 0A0Bh; void *
0x180005e39  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
