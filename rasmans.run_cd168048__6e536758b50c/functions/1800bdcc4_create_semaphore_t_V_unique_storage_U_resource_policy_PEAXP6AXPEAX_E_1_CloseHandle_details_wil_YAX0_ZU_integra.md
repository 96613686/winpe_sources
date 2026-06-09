# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x1800bdcc4`
- end: `0x1800bdd5f`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b65c4`

## callees

- `0x1800b7a70`
- `0x1800bdbb0`
- `0x1800bdcc4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bdd1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bdd1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdcf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdd0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdcf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdd0a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bdd2d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bdd2d`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800bdce2`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800bdce2`

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
0x1800bdcc4  push    rbx
0x1800bdcc6  push    rbp
0x1800bdcc7  push    rsi
0x1800bdcc8  push    rdi
0x1800bdcc9  sub     rsp, 38h
0x1800bdccd  mov     rdi, rcx
0x1800bdcd0  mov     [rsp+58h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800bdcd8  xor     ecx, ecx; lpSemaphoreAttributes
0x1800bdcda  mov     [rsp+58h+dwFlags], 0; dwFlags
0x1800bdce2  call    cs:__imp_CreateSemaphoreExW
0x1800bdce9  nop     dword ptr [rax+rax+00h]
0x1800bdcee  mov     rbp, rax
0x1800bdcf1  test    rax, rax
0x1800bdcf4  jz      short loc_1800BDD40
0x1800bdcf6  call    cs:__imp_GetLastError
0x1800bdcfd  nop     dword ptr [rax+rax+00h]
0x1800bdd02  mov     rbx, [rdi]
0x1800bdd05  test    rbx, rbx
0x1800bdd08  jz      short loc_1800BDD39
0x1800bdd0a  call    cs:__imp_GetLastError
0x1800bdd11  nop     dword ptr [rax+rax+00h]
0x1800bdd16  mov     rcx, rbx; hObject
0x1800bdd19  mov     esi, eax
0x1800bdd1b  call    cs:__imp_CloseHandle
0x1800bdd22  nop     dword ptr [rax+rax+00h]
0x1800bdd27  test    eax, eax
0x1800bdd29  jz      short loc_1800BDD4F
0x1800bdd2b  mov     ecx, esi; dwErrCode
0x1800bdd2d  call    cs:__imp_SetLastError
0x1800bdd34  nop     dword ptr [rax+rax+00h]
0x1800bdd39  mov     [rdi], rbp
0x1800bdd3c  xor     eax, eax
0x1800bdd3e  jmp     short loc_1800BDD45
0x1800bdd40  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800bdd45  add     rsp, 38h
0x1800bdd49  pop     rdi
0x1800bdd4a  pop     rsi
0x1800bdd4b  pop     rbp
0x1800bdd4c  pop     rbx
0x1800bdd4d  retn
0x1800bdd4f  mov     rcx, [rsp+58h]; this
0x1800bdd54  mov     edx, 0A0Bh; void *
0x1800bdd59  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
