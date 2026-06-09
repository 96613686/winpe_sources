# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x1400104d8`
- end: `0x140010573`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000f768`

## callees

- `0x14000ee68`
- `0x1400104bc`
- `0x1400104d8`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14001052f`
- `KERNEL32!CloseHandle` at `0x14001052f`
- `KERNEL32!SetLastError` at `0x140010541`
- `KERNEL32!SetLastError` at `0x140010541`
- `KERNEL32!CreateSemaphoreExW` at `0x1400104f6`
- `KERNEL32!CreateSemaphoreExW` at `0x1400104f6`
- `KERNEL32!GetLastError` at `0x14001050a`
- `KERNEL32!GetLastError` at `0x14001051e`
- `KERNEL32!GetLastError` at `0x14001050a`
- `KERNEL32!GetLastError` at `0x14001051e`

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
0x1400104d8  push    rbx
0x1400104da  push    rbp
0x1400104db  push    rsi
0x1400104dc  push    rdi
0x1400104dd  sub     rsp, 38h
0x1400104e1  mov     rdi, rcx
0x1400104e4  mov     [rsp+58h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1400104ec  xor     ecx, ecx; lpSemaphoreAttributes
0x1400104ee  mov     [rsp+58h+dwFlags], 0; dwFlags
0x1400104f6  call    cs:__imp_CreateSemaphoreExW
0x1400104fd  nop     dword ptr [rax+rax+00h]
0x140010502  mov     rbp, rax
0x140010505  test    rax, rax
0x140010508  jz      short loc_140010554
0x14001050a  call    cs:__imp_GetLastError
0x140010511  nop     dword ptr [rax+rax+00h]
0x140010516  mov     rbx, [rdi]
0x140010519  test    rbx, rbx
0x14001051c  jz      short loc_14001054D
0x14001051e  call    cs:__imp_GetLastError
0x140010525  nop     dword ptr [rax+rax+00h]
0x14001052a  mov     rcx, rbx; hObject
0x14001052d  mov     esi, eax
0x14001052f  call    cs:__imp_CloseHandle
0x140010536  nop     dword ptr [rax+rax+00h]
0x14001053b  test    eax, eax
0x14001053d  jz      short loc_140010563
0x14001053f  mov     ecx, esi; dwErrCode
0x140010541  call    cs:__imp_SetLastError
0x140010548  nop     dword ptr [rax+rax+00h]
0x14001054d  mov     [rdi], rbp
0x140010550  xor     eax, eax
0x140010552  jmp     short loc_140010559
0x140010554  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140010559  add     rsp, 38h
0x14001055d  pop     rdi
0x14001055e  pop     rsi
0x14001055f  pop     rbp
0x140010560  pop     rbx
0x140010561  retn
0x140010563  mov     rcx, [rsp+58h]; this
0x140010568  mov     edx, 0A0Bh; void *
0x14001056d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
