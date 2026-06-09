# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x140005704`
- end: `0x14000579f`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140004340`

## callees

- `0x140003920`
- `0x1400056e8`
- `0x140005704`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140005722`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140005722`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005736`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000574a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005736`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000574a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000576d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000576d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000575b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000575b`

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
0x140005704  push    rbx
0x140005706  push    rbp
0x140005707  push    rsi
0x140005708  push    rdi
0x140005709  sub     rsp, 38h
0x14000570d  mov     rdi, rcx
0x140005710  mov     [rsp+58h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140005718  xor     ecx, ecx; lpSemaphoreAttributes
0x14000571a  mov     [rsp+58h+dwFlags], 0; dwFlags
0x140005722  call    cs:__imp_CreateSemaphoreExW
0x140005729  nop     dword ptr [rax+rax+00h]
0x14000572e  mov     rbp, rax
0x140005731  test    rax, rax
0x140005734  jz      short loc_140005780
0x140005736  call    cs:__imp_GetLastError
0x14000573d  nop     dword ptr [rax+rax+00h]
0x140005742  mov     rbx, [rdi]
0x140005745  test    rbx, rbx
0x140005748  jz      short loc_140005779
0x14000574a  call    cs:__imp_GetLastError
0x140005751  nop     dword ptr [rax+rax+00h]
0x140005756  mov     rcx, rbx; hObject
0x140005759  mov     esi, eax
0x14000575b  call    cs:__imp_CloseHandle
0x140005762  nop     dword ptr [rax+rax+00h]
0x140005767  test    eax, eax
0x140005769  jz      short loc_14000578F
0x14000576b  mov     ecx, esi; dwErrCode
0x14000576d  call    cs:__imp_SetLastError
0x140005774  nop     dword ptr [rax+rax+00h]
0x140005779  mov     [rdi], rbp
0x14000577c  xor     eax, eax
0x14000577e  jmp     short loc_140005785
0x140005780  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140005785  add     rsp, 38h
0x140005789  pop     rdi
0x14000578a  pop     rsi
0x14000578b  pop     rbp
0x14000578c  pop     rbx
0x14000578d  retn
0x14000578f  mov     rcx, [rsp+58h]; this
0x140005794  mov     edx, 0A0Bh; void *
0x140005799  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
