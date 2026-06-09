# ?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x14005d8c4`
- end: `0x14005d95f`
- name: `?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140058a5c`

## callees

- `0x1400089a8`
- `0x14000ce7c`
- `0x14005d8c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14005d8e2`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14005d8e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005d8f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005d90a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005d8f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005d90a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005d92d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005d92d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005d91b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005d91b`

## string_xrefs

- `0x14005d8d0`: `Global\DeclaredConfigurationMutex`

## pseudocode

```c
__int64 __fastcall _create___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1)
{
  wil::details *v2; // rcx
  HANDLE Mutex; // rbp
  void *v4; // rbx
  DWORD LastError; // esi
  unsigned int v6; // r8d
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  Mutex = CreateMutexExW(0, L"Global\\DeclaredConfigurationMutex", 0, 0x1F0001u);
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v2);
  GetLastError();
  v4 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v4) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v6, v7);
    SetLastError(LastError);
  }
  *a1 = Mutex;
  return 0;
}

```

## disassembly

```asm
0x14005d8c4  push    rbx
0x14005d8c6  push    rbp
0x14005d8c7  push    rsi
0x14005d8c8  push    rdi
0x14005d8c9  sub     rsp, 28h
0x14005d8cd  mov     rdi, rcx
0x14005d8d0  lea     rdx, Name; "Global\\DeclaredConfigurationMutex"
0x14005d8d7  xor     ecx, ecx; lpMutexAttributes
0x14005d8d9  mov     r9d, 1F0001h; dwDesiredAccess
0x14005d8df  xor     r8d, r8d; dwFlags
0x14005d8e2  call    cs:__imp_CreateMutexExW
0x14005d8e9  nop     dword ptr [rax+rax+00h]
0x14005d8ee  mov     rbp, rax
0x14005d8f1  test    rax, rax
0x14005d8f4  jz      short loc_14005D940
0x14005d8f6  call    cs:__imp_GetLastError
0x14005d8fd  nop     dword ptr [rax+rax+00h]
0x14005d902  mov     rbx, [rdi]
0x14005d905  test    rbx, rbx
0x14005d908  jz      short loc_14005D939
0x14005d90a  call    cs:__imp_GetLastError
0x14005d911  nop     dword ptr [rax+rax+00h]
0x14005d916  mov     rcx, rbx; hObject
0x14005d919  mov     esi, eax
0x14005d91b  call    cs:__imp_CloseHandle
0x14005d922  nop     dword ptr [rax+rax+00h]
0x14005d927  test    eax, eax
0x14005d929  jz      short loc_14005D94F
0x14005d92b  mov     ecx, esi; dwErrCode
0x14005d92d  call    cs:__imp_SetLastError
0x14005d934  nop     dword ptr [rax+rax+00h]
0x14005d939  mov     [rdi], rbp
0x14005d93c  xor     eax, eax
0x14005d93e  jmp     short loc_14005D945
0x14005d940  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14005d945  add     rsp, 28h
0x14005d949  pop     rdi
0x14005d94a  pop     rsi
0x14005d94b  pop     rbp
0x14005d94c  pop     rbx
0x14005d94d  retn
0x14005d94f  mov     rcx, [rsp+48h]; this
0x14005d954  mov     edx, 0A0Bh; void *
0x14005d959  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
