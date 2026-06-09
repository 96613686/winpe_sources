# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x1400090c8`
- end: `0x140009163`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `155`
- prototype: `__int64 __fastcall(void **, LONG, LONG, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140004568`

## callees

- `0x140004e70`
- `0x140008f74`
- `0x1400090c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400090e6`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400090e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009131`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009131`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400090fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000910e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400090fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000910e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000911f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000911f`

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
  __int64 v9; // r8
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
0x1400090c8  push    rbx
0x1400090ca  push    rbp
0x1400090cb  push    rsi
0x1400090cc  push    rdi
0x1400090cd  sub     rsp, 38h
0x1400090d1  mov     rdi, rcx
0x1400090d4  mov     [rsp+58h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1400090dc  xor     ecx, ecx; lpSemaphoreAttributes
0x1400090de  mov     [rsp+58h+dwFlags], 0; dwFlags
0x1400090e6  call    cs:__imp_CreateSemaphoreExW
0x1400090ed  nop     dword ptr [rax+rax+00h]
0x1400090f2  mov     rbp, rax
0x1400090f5  test    rax, rax
0x1400090f8  jz      short loc_140009144
0x1400090fa  call    cs:__imp_GetLastError
0x140009101  nop     dword ptr [rax+rax+00h]
0x140009106  mov     rbx, [rdi]
0x140009109  test    rbx, rbx
0x14000910c  jz      short loc_14000913D
0x14000910e  call    cs:__imp_GetLastError
0x140009115  nop     dword ptr [rax+rax+00h]
0x14000911a  mov     rcx, rbx; hObject
0x14000911d  mov     esi, eax
0x14000911f  call    cs:__imp_CloseHandle
0x140009126  nop     dword ptr [rax+rax+00h]
0x14000912b  test    eax, eax
0x14000912d  jz      short loc_140009153
0x14000912f  mov     ecx, esi; dwErrCode
0x140009131  call    cs:__imp_SetLastError
0x140009138  nop     dword ptr [rax+rax+00h]
0x14000913d  mov     [rdi], rbp
0x140009140  xor     eax, eax
0x140009142  jmp     short loc_140009149
0x140009144  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140009149  add     rsp, 38h
0x14000914d  pop     rdi
0x14000914e  pop     rsi
0x14000914f  pop     rbp
0x140009150  pop     rbx
0x140009151  retn
0x140009153  mov     rcx, [rsp+58h]; this
0x140009158  mov     edx, 0A0Bh; void *
0x14000915d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
