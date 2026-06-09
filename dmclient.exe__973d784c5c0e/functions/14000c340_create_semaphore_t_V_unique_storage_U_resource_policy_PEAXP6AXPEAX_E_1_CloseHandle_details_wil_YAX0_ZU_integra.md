# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x14000c340`
- end: `0x14000c3db`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005740`

## callees

- `0x1400070c0`
- `0x14000bfd4`
- `0x14000c340`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000c35e`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000c35e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c372`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c386`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c372`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c386`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c3a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c3a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c397`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c397`

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
0x14000c340  push    rbx
0x14000c342  push    rbp
0x14000c343  push    rsi
0x14000c344  push    rdi
0x14000c345  sub     rsp, 38h
0x14000c349  mov     rdi, rcx
0x14000c34c  mov     [rsp+58h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x14000c354  xor     ecx, ecx; lpSemaphoreAttributes
0x14000c356  mov     [rsp+58h+dwFlags], 0; dwFlags
0x14000c35e  call    cs:__imp_CreateSemaphoreExW
0x14000c365  nop     dword ptr [rax+rax+00h]
0x14000c36a  mov     rbp, rax
0x14000c36d  test    rax, rax
0x14000c370  jz      short loc_14000C3BC
0x14000c372  call    cs:__imp_GetLastError
0x14000c379  nop     dword ptr [rax+rax+00h]
0x14000c37e  mov     rbx, [rdi]
0x14000c381  test    rbx, rbx
0x14000c384  jz      short loc_14000C3B5
0x14000c386  call    cs:__imp_GetLastError
0x14000c38d  nop     dword ptr [rax+rax+00h]
0x14000c392  mov     rcx, rbx; hObject
0x14000c395  mov     esi, eax
0x14000c397  call    cs:__imp_CloseHandle
0x14000c39e  nop     dword ptr [rax+rax+00h]
0x14000c3a3  test    eax, eax
0x14000c3a5  jz      short loc_14000C3CB
0x14000c3a7  mov     ecx, esi; dwErrCode
0x14000c3a9  call    cs:__imp_SetLastError
0x14000c3b0  nop     dword ptr [rax+rax+00h]
0x14000c3b5  mov     [rdi], rbp
0x14000c3b8  xor     eax, eax
0x14000c3ba  jmp     short loc_14000C3C1
0x14000c3bc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000c3c1  add     rsp, 38h
0x14000c3c5  pop     rdi
0x14000c3c6  pop     rsi
0x14000c3c7  pop     rbp
0x14000c3c8  pop     rbx
0x14000c3c9  retn
0x14000c3cb  mov     rcx, [rsp+58h]; this
0x14000c3d0  mov     edx, 0A0Bh; void *
0x14000c3d5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
