# ?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18003307c`
- end: `0x180033121`
- name: `?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `165`
- prototype: `__int64 __fastcall(int, int, int, int, LPSECURITY_ATTRIBUTES lpMutexAttributes)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180032c84`

## callees

- `0x180007834`
- `0x180024508`
- `0x18003307c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800330aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800330be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800330aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800330be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800330e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800330e1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180033096`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180033096`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800330cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800330cf`

## string_xrefs

- `0x18003310f`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
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
  unsigned int v10; // r8d
  const char *v11; // r9
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
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v10, v11);
    SetLastError(LastError);
  }
  *a1 = Mutex;
}

```

## disassembly

```asm
0x18003307c  push    rbx
0x18003307e  push    rbp
0x18003307f  push    rsi
0x180033080  push    rdi
0x180033081  sub     rsp, 28h
0x180033085  mov     rdi, rcx
0x180033088  mov     r9d, 1F0001h; dwDesiredAccess
0x18003308e  mov     rcx, [rsp+48h+lpMutexAttributes]; lpMutexAttributes
0x180033093  xor     r8d, r8d; dwFlags
0x180033096  call    cs:__imp_CreateMutexExW
0x18003309d  nop     dword ptr [rax+rax+00h]
0x1800330a2  mov     rbp, rax
0x1800330a5  test    rax, rax
0x1800330a8  jz      short loc_18003310A
0x1800330aa  call    cs:__imp_GetLastError
0x1800330b1  nop     dword ptr [rax+rax+00h]
0x1800330b6  mov     rbx, [rdi]
0x1800330b9  test    rbx, rbx
0x1800330bc  jz      short loc_1800330ED
0x1800330be  call    cs:__imp_GetLastError
0x1800330c5  nop     dword ptr [rax+rax+00h]
0x1800330ca  mov     rcx, rbx; hObject
0x1800330cd  mov     esi, eax
0x1800330cf  call    cs:__imp_CloseHandle
0x1800330d6  nop     dword ptr [rax+rax+00h]
0x1800330db  test    eax, eax
0x1800330dd  jz      short loc_1800330FA
0x1800330df  mov     ecx, esi; dwErrCode
0x1800330e1  call    cs:__imp_SetLastError
0x1800330e8  nop     dword ptr [rax+rax+00h]
0x1800330ed  mov     [rdi], rbp
0x1800330f0  add     rsp, 28h
0x1800330f4  pop     rdi
0x1800330f5  pop     rsi
0x1800330f6  pop     rbp
0x1800330f7  pop     rbx
0x1800330f8  retn
0x1800330fa  mov     rcx, [rsp+48h]; this
0x1800330ff  mov     edx, 0A0Bh; void *
0x180033104  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18003310a  mov     rcx, [rsp+48h]; this
0x18003310f  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180033116  mov     edx, 1CC8h; void *
0x18003311b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
