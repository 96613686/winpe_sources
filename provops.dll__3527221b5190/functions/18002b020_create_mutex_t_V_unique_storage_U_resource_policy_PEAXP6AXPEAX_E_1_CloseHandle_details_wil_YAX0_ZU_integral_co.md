# ?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18002b020`
- end: `0x18002b0ad`
- name: `?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `141`
- prototype: `void __fastcall(void **, const WCHAR *, __int64, __int64, LPSECURITY_ATTRIBUTES lpMutexAttributes)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002a170`

## callees

- `0x18000864c`
- `0x180020710`
- `0x18002b020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002b03a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002b03a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b048`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b056`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b048`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b056`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b06d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b06d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b061`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b061`

## string_xrefs

- `0x18002b084`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002b09b`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall _create___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1,
        const WCHAR *a2,
        __int64 a3,
        __int64 a4,
        LPSECURITY_ATTRIBUTES lpMutexAttributes)
{
  HANDLE Mutex; // rbp
  const char *v7; // r9
  void *v8; // rbx
  DWORD LastError; // esi
  const char *v10; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  Mutex = CreateMutexExW(lpMutexAttributes, a2, 0, 0x1F0001u);
  if ( !Mutex )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1CC8,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      v7);
  GetLastError();
  v8 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v8) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    SetLastError(LastError);
  }
  *a1 = Mutex;
}

```

## disassembly

```asm
0x18002b020  push    rbx
0x18002b022  push    rbp
0x18002b023  push    rsi
0x18002b024  push    rdi
0x18002b025  sub     rsp, 28h
0x18002b029  mov     rdi, rcx
0x18002b02c  mov     r9d, 1F0001h; dwDesiredAccess
0x18002b032  mov     rcx, [rsp+48h+lpMutexAttributes]; lpMutexAttributes
0x18002b037  xor     r8d, r8d; dwFlags
0x18002b03a  call    cs:__imp_CreateMutexExW
0x18002b040  mov     rbp, rax
0x18002b043  test    rax, rax
0x18002b046  jz      short loc_18002B096
0x18002b048  call    cs:__imp_GetLastError
0x18002b04e  mov     rbx, [rdi]
0x18002b051  test    rbx, rbx
0x18002b054  jz      short loc_18002B073
0x18002b056  call    cs:__imp_GetLastError
0x18002b05c  mov     rcx, rbx; hObject
0x18002b05f  mov     esi, eax
0x18002b061  call    cs:__imp_CloseHandle
0x18002b067  test    eax, eax
0x18002b069  jz      short loc_18002B07F
0x18002b06b  mov     ecx, esi; dwErrCode
0x18002b06d  call    cs:__imp_SetLastError
0x18002b073  mov     [rdi], rbp
0x18002b076  add     rsp, 28h
0x18002b07a  pop     rdi
0x18002b07b  pop     rsi
0x18002b07c  pop     rbp
0x18002b07d  pop     rbx
0x18002b07e  retn
0x18002b07f  mov     rcx, [rsp+48h]; this
0x18002b084  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002b08b  mov     edx, 0A0Bh; void *
0x18002b090  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002b096  mov     rcx, [rsp+48h]; this
0x18002b09b  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002b0a2  mov     edx, 1CC8h; void *
0x18002b0a7  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
