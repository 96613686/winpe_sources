# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18000be74`
- end: `0x18000bf0f`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800065d8`

## callees

- `0x180007430`
- `0x18000bdac`
- `0x18000be74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000be92`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000be92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bea6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000beba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bea6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000beba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bedd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bedd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000becb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000becb`

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
0x18000be74  push    rbx
0x18000be76  push    rbp
0x18000be77  push    rsi
0x18000be78  push    rdi
0x18000be79  sub     rsp, 38h
0x18000be7d  mov     rdi, rcx
0x18000be80  mov     [rsp+58h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000be88  xor     ecx, ecx; lpSemaphoreAttributes
0x18000be8a  mov     [rsp+58h+dwFlags], 0; dwFlags
0x18000be92  call    cs:__imp_CreateSemaphoreExW
0x18000be99  nop     dword ptr [rax+rax+00h]
0x18000be9e  mov     rbp, rax
0x18000bea1  test    rax, rax
0x18000bea4  jz      short loc_18000BEF0
0x18000bea6  call    cs:__imp_GetLastError
0x18000bead  nop     dword ptr [rax+rax+00h]
0x18000beb2  mov     rbx, [rdi]
0x18000beb5  test    rbx, rbx
0x18000beb8  jz      short loc_18000BEE9
0x18000beba  call    cs:__imp_GetLastError
0x18000bec1  nop     dword ptr [rax+rax+00h]
0x18000bec6  mov     rcx, rbx; hObject
0x18000bec9  mov     esi, eax
0x18000becb  call    cs:__imp_CloseHandle
0x18000bed2  nop     dword ptr [rax+rax+00h]
0x18000bed7  test    eax, eax
0x18000bed9  jz      short loc_18000BEFF
0x18000bedb  mov     ecx, esi; dwErrCode
0x18000bedd  call    cs:__imp_SetLastError
0x18000bee4  nop     dword ptr [rax+rax+00h]
0x18000bee9  mov     [rdi], rbp
0x18000beec  xor     eax, eax
0x18000beee  jmp     short loc_18000BEF5
0x18000bef0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000bef5  add     rsp, 38h
0x18000bef9  pop     rdi
0x18000befa  pop     rsi
0x18000befb  pop     rbp
0x18000befc  pop     rbx
0x18000befd  retn
0x18000beff  mov     rcx, [rsp+58h]; this
0x18000bf04  mov     edx, 0A0Bh; void *
0x18000bf09  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
