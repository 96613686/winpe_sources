# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180005d9c`
- end: `0x180005e37`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800045a8`

## callees

- `0x180003b50`
- `0x180005cf8`
- `0x180005d9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005dba`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005dba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005dce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005de2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005dce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005de2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005e05`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005e05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005df3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005df3`

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
0x180005d9c  push    rbx
0x180005d9e  push    rbp
0x180005d9f  push    rsi
0x180005da0  push    rdi
0x180005da1  sub     rsp, 38h
0x180005da5  mov     rdi, rcx
0x180005da8  mov     [rsp+58h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180005db0  xor     ecx, ecx; lpSemaphoreAttributes
0x180005db2  mov     [rsp+58h+dwFlags], 0; dwFlags
0x180005dba  call    cs:__imp_CreateSemaphoreExW
0x180005dc1  nop     dword ptr [rax+rax+00h]
0x180005dc6  mov     rbp, rax
0x180005dc9  test    rax, rax
0x180005dcc  jz      short loc_180005E18
0x180005dce  call    cs:__imp_GetLastError
0x180005dd5  nop     dword ptr [rax+rax+00h]
0x180005dda  mov     rbx, [rdi]
0x180005ddd  test    rbx, rbx
0x180005de0  jz      short loc_180005E11
0x180005de2  call    cs:__imp_GetLastError
0x180005de9  nop     dword ptr [rax+rax+00h]
0x180005dee  mov     rcx, rbx; hObject
0x180005df1  mov     esi, eax
0x180005df3  call    cs:__imp_CloseHandle
0x180005dfa  nop     dword ptr [rax+rax+00h]
0x180005dff  test    eax, eax
0x180005e01  jz      short loc_180005E27
0x180005e03  mov     ecx, esi; dwErrCode
0x180005e05  call    cs:__imp_SetLastError
0x180005e0c  nop     dword ptr [rax+rax+00h]
0x180005e11  mov     [rdi], rbp
0x180005e14  xor     eax, eax
0x180005e16  jmp     short loc_180005E1D
0x180005e18  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005e1d  add     rsp, 38h
0x180005e21  pop     rdi
0x180005e22  pop     rsi
0x180005e23  pop     rbp
0x180005e24  pop     rbx
0x180005e25  retn
0x180005e27  mov     rcx, [rsp+58h]; this
0x180005e2c  mov     edx, 0A0Bh; void *
0x180005e31  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
