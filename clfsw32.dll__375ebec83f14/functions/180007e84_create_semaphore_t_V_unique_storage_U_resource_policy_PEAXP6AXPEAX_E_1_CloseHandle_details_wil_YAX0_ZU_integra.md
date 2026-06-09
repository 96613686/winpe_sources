# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180007e84`
- end: `0x180007f1f`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003f78`

## callees

- `0x180004c70`
- `0x180007e10`
- `0x180007e84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007eed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007eed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007eb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007eca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007eb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007eca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007edb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007edb`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007ea2`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007ea2`

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
0x180007e84  push    rbx
0x180007e86  push    rbp
0x180007e87  push    rsi
0x180007e88  push    rdi
0x180007e89  sub     rsp, 38h
0x180007e8d  mov     rdi, rcx
0x180007e90  mov     [rsp+58h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180007e98  xor     ecx, ecx; lpSemaphoreAttributes
0x180007e9a  mov     [rsp+58h+dwFlags], 0; dwFlags
0x180007ea2  call    cs:__imp_CreateSemaphoreExW
0x180007ea9  nop     dword ptr [rax+rax+00h]
0x180007eae  mov     rbp, rax
0x180007eb1  test    rax, rax
0x180007eb4  jz      short loc_180007F00
0x180007eb6  call    cs:__imp_GetLastError
0x180007ebd  nop     dword ptr [rax+rax+00h]
0x180007ec2  mov     rbx, [rdi]
0x180007ec5  test    rbx, rbx
0x180007ec8  jz      short loc_180007EF9
0x180007eca  call    cs:__imp_GetLastError
0x180007ed1  nop     dword ptr [rax+rax+00h]
0x180007ed6  mov     rcx, rbx; hObject
0x180007ed9  mov     esi, eax
0x180007edb  call    cs:__imp_CloseHandle
0x180007ee2  nop     dword ptr [rax+rax+00h]
0x180007ee7  test    eax, eax
0x180007ee9  jz      short loc_180007F0F
0x180007eeb  mov     ecx, esi; dwErrCode
0x180007eed  call    cs:__imp_SetLastError
0x180007ef4  nop     dword ptr [rax+rax+00h]
0x180007ef9  mov     [rdi], rbp
0x180007efc  xor     eax, eax
0x180007efe  jmp     short loc_180007F05
0x180007f00  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007f05  add     rsp, 38h
0x180007f09  pop     rdi
0x180007f0a  pop     rsi
0x180007f0b  pop     rbp
0x180007f0c  pop     rbx
0x180007f0d  retn
0x180007f0f  mov     rcx, [rsp+58h]; this
0x180007f14  mov     edx, 0A0Bh; void *
0x180007f19  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
