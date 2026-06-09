# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x1800139c8`
- end: `0x180013a63`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `155`
- prototype: `__int64 __fastcall(void **, LONG, LONG, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a80c`

## callees

- `0x18000b398`
- `0x1800134a0`
- `0x1800139c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800139e6`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800139e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013a31`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013a31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800139fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800139fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013a1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013a1f`

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
0x1800139c8  push    rbx
0x1800139ca  push    rbp
0x1800139cb  push    rsi
0x1800139cc  push    rdi
0x1800139cd  sub     rsp, 38h
0x1800139d1  mov     rdi, rcx
0x1800139d4  mov     [rsp+58h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800139dc  xor     ecx, ecx; lpSemaphoreAttributes
0x1800139de  mov     [rsp+58h+dwFlags], 0; dwFlags
0x1800139e6  call    cs:__imp_CreateSemaphoreExW
0x1800139ed  nop     dword ptr [rax+rax+00h]
0x1800139f2  mov     rbp, rax
0x1800139f5  test    rax, rax
0x1800139f8  jz      short loc_180013A44
0x1800139fa  call    cs:__imp_GetLastError
0x180013a01  nop     dword ptr [rax+rax+00h]
0x180013a06  mov     rbx, [rdi]
0x180013a09  test    rbx, rbx
0x180013a0c  jz      short loc_180013A3D
0x180013a0e  call    cs:__imp_GetLastError
0x180013a15  nop     dword ptr [rax+rax+00h]
0x180013a1a  mov     rcx, rbx; hObject
0x180013a1d  mov     esi, eax
0x180013a1f  call    cs:__imp_CloseHandle
0x180013a26  nop     dword ptr [rax+rax+00h]
0x180013a2b  test    eax, eax
0x180013a2d  jz      short loc_180013A53
0x180013a2f  mov     ecx, esi; dwErrCode
0x180013a31  call    cs:__imp_SetLastError
0x180013a38  nop     dword ptr [rax+rax+00h]
0x180013a3d  mov     [rdi], rbp
0x180013a40  xor     eax, eax
0x180013a42  jmp     short loc_180013A49
0x180013a44  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180013a49  add     rsp, 38h
0x180013a4d  pop     rdi
0x180013a4e  pop     rsi
0x180013a4f  pop     rbp
0x180013a50  pop     rbx
0x180013a51  retn
0x180013a53  mov     rcx, [rsp+58h]; this
0x180013a58  mov     edx, 0A0Bh; void *
0x180013a5d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
