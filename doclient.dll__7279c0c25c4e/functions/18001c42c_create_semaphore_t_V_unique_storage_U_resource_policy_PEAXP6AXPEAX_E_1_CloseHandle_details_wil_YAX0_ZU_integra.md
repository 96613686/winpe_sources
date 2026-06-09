# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18001c42c`
- end: `0x18001c4c8`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c928`

## callees

- `0x180008a54`
- `0x18000a4e0`
- `0x18001c42c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c47d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c47d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c464`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c472`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c464`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c472`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c489`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c489`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18001c456`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18001c456`

## pseudocode

```c
__int64 __fastcall _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1,
        LONG a2,
        LONG a3,
        const WCHAR *a4)
{
  unsigned int v5; // ebx
  wil::details *v6; // rcx
  HANDLE Semaphore; // r14
  void *v8; // rdi
  DWORD LastError; // ebp
  unsigned int v10; // r8d
  const char *v11; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v5 = 0;
  Semaphore = CreateSemaphoreExW(0, a2, a3, a4, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    v8 = *a1;
    if ( *a1 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v8) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v10, v11);
      SetLastError(LastError);
    }
    *a1 = Semaphore;
  }
  else
  {
    return (unsigned int)wil::details::GetLastErrorFailHr(v6);
  }
  return v5;
}

```

## disassembly

```asm
0x18001c42c  mov     rax, rsp
0x18001c42f  mov     [rax+8], rbx
0x18001c433  mov     [rax+10h], rbp
0x18001c437  mov     [rax+18h], rsi
0x18001c43b  mov     [rax+20h], rdi
0x18001c43f  push    r14
0x18001c441  sub     rsp, 30h
0x18001c445  mov     rsi, rcx
0x18001c448  mov     dword ptr [rax-10h], 1F0003h
0x18001c44f  xor     ebx, ebx
0x18001c451  xor     ecx, ecx; lpSemaphoreAttributes
0x18001c453  mov     [rax-18h], ebx
0x18001c456  call    cs:__imp_CreateSemaphoreExW
0x18001c45c  mov     r14, rax
0x18001c45f  test    rax, rax
0x18001c462  jz      short loc_18001C494
0x18001c464  call    cs:__imp_GetLastError
0x18001c46a  mov     rdi, [rsi]
0x18001c46d  test    rdi, rdi
0x18001c470  jz      short loc_18001C48F
0x18001c472  call    cs:__imp_GetLastError
0x18001c478  mov     rcx, rdi; hObject
0x18001c47b  mov     ebp, eax
0x18001c47d  call    cs:__imp_CloseHandle
0x18001c483  test    eax, eax
0x18001c485  jz      short loc_18001C4B8
0x18001c487  mov     ecx, ebp; dwErrCode
0x18001c489  call    cs:__imp_SetLastError
0x18001c48f  mov     [rsi], r14
0x18001c492  jmp     short loc_18001C49B
0x18001c494  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001c499  mov     ebx, eax
0x18001c49b  mov     rbp, [rsp+38h+arg_8]
0x18001c4a0  mov     eax, ebx
0x18001c4a2  mov     rbx, [rsp+38h+arg_0]
0x18001c4a7  mov     rsi, [rsp+38h+arg_10]
0x18001c4ac  mov     rdi, [rsp+38h+arg_18]
0x18001c4b1  add     rsp, 30h
0x18001c4b5  pop     r14
0x18001c4b7  retn
0x18001c4b8  mov     rcx, [rsp+38h]; this
0x18001c4bd  mov     edx, 9D1h; void *
0x18001c4c2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
