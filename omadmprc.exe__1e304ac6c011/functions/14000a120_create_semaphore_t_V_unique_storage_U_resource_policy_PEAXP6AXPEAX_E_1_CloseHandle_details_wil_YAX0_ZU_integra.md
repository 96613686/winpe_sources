# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x14000a120`
- end: `0x14000a1bb`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140004a88`

## callees

- `0x140005940`
- `0x140009e20`
- `0x14000a120`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a152`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a166`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a152`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a166`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a189`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a189`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000a13e`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000a13e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a177`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a177`

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
0x14000a120  push    rbx
0x14000a122  push    rbp
0x14000a123  push    rsi
0x14000a124  push    rdi
0x14000a125  sub     rsp, 38h
0x14000a129  mov     rdi, rcx
0x14000a12c  mov     [rsp+58h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x14000a134  xor     ecx, ecx; lpSemaphoreAttributes
0x14000a136  mov     [rsp+58h+dwFlags], 0; dwFlags
0x14000a13e  call    cs:__imp_CreateSemaphoreExW
0x14000a145  nop     dword ptr [rax+rax+00h]
0x14000a14a  mov     rbp, rax
0x14000a14d  test    rax, rax
0x14000a150  jz      short loc_14000A19C
0x14000a152  call    cs:__imp_GetLastError
0x14000a159  nop     dword ptr [rax+rax+00h]
0x14000a15e  mov     rbx, [rdi]
0x14000a161  test    rbx, rbx
0x14000a164  jz      short loc_14000A195
0x14000a166  call    cs:__imp_GetLastError
0x14000a16d  nop     dword ptr [rax+rax+00h]
0x14000a172  mov     rcx, rbx; hObject
0x14000a175  mov     esi, eax
0x14000a177  call    cs:__imp_CloseHandle
0x14000a17e  nop     dword ptr [rax+rax+00h]
0x14000a183  test    eax, eax
0x14000a185  jz      short loc_14000A1AB
0x14000a187  mov     ecx, esi; dwErrCode
0x14000a189  call    cs:__imp_SetLastError
0x14000a190  nop     dword ptr [rax+rax+00h]
0x14000a195  mov     [rdi], rbp
0x14000a198  xor     eax, eax
0x14000a19a  jmp     short loc_14000A1A1
0x14000a19c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000a1a1  add     rsp, 38h
0x14000a1a5  pop     rdi
0x14000a1a6  pop     rsi
0x14000a1a7  pop     rbp
0x14000a1a8  pop     rbx
0x14000a1a9  retn
0x14000a1ab  mov     rcx, [rsp+58h]; this
0x14000a1b0  mov     edx, 0A0Bh; void *
0x14000a1b5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
