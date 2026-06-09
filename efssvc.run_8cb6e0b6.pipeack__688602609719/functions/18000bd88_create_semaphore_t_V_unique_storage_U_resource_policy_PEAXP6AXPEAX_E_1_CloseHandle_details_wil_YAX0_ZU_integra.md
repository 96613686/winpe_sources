# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18000bd88`
- end: `0x18000be23`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ac68`

## callees

- `0x18000a378`
- `0x18000bd6c`
- `0x18000bd88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bdf1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bdf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdce`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000bda6`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000bda6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bddf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bddf`

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
0x18000bd88  push    rbx
0x18000bd8a  push    rbp
0x18000bd8b  push    rsi
0x18000bd8c  push    rdi
0x18000bd8d  sub     rsp, 38h
0x18000bd91  mov     rdi, rcx
0x18000bd94  mov     [rsp+58h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000bd9c  xor     ecx, ecx; lpSemaphoreAttributes
0x18000bd9e  mov     [rsp+58h+dwFlags], 0; dwFlags
0x18000bda6  call    cs:__imp_CreateSemaphoreExW
0x18000bdad  nop     dword ptr [rax+rax+00h]
0x18000bdb2  mov     rbp, rax
0x18000bdb5  test    rax, rax
0x18000bdb8  jz      short loc_18000BE04
0x18000bdba  call    cs:__imp_GetLastError
0x18000bdc1  nop     dword ptr [rax+rax+00h]
0x18000bdc6  mov     rbx, [rdi]
0x18000bdc9  test    rbx, rbx
0x18000bdcc  jz      short loc_18000BDFD
0x18000bdce  call    cs:__imp_GetLastError
0x18000bdd5  nop     dword ptr [rax+rax+00h]
0x18000bdda  mov     rcx, rbx; hObject
0x18000bddd  mov     esi, eax
0x18000bddf  call    cs:__imp_CloseHandle
0x18000bde6  nop     dword ptr [rax+rax+00h]
0x18000bdeb  test    eax, eax
0x18000bded  jz      short loc_18000BE13
0x18000bdef  mov     ecx, esi; dwErrCode
0x18000bdf1  call    cs:__imp_SetLastError
0x18000bdf8  nop     dword ptr [rax+rax+00h]
0x18000bdfd  mov     [rdi], rbp
0x18000be00  xor     eax, eax
0x18000be02  jmp     short loc_18000BE09
0x18000be04  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000be09  add     rsp, 38h
0x18000be0d  pop     rdi
0x18000be0e  pop     rsi
0x18000be0f  pop     rbp
0x18000be10  pop     rbx
0x18000be11  retn
0x18000be13  mov     rcx, [rsp+58h]; this
0x18000be18  mov     edx, 0A0Bh; void *
0x18000be1d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
