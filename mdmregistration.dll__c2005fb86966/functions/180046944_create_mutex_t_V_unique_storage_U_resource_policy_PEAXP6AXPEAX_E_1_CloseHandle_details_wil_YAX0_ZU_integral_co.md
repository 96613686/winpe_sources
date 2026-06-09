# ?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180046944`
- end: `0x1800469e2`
- name: `?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `158`
- prototype: `__int64 __fastcall(int, int, int, int, LPSECURITY_ATTRIBUTES lpMutexAttributes)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180045698`

## callees

- `0x180008700`
- `0x18000cc00`
- `0x180046944`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180046965`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180046965`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046979`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004698d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046979`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004698d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800469b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800469b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004699e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004699e`

## pseudocode

```c
__int64 __fastcall _create___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        LPSECURITY_ATTRIBUTES lpMutexAttributes)
{
  wil::details *v6; // rcx
  HANDLE Mutex; // rbp
  void *v8; // rbx
  DWORD LastError; // esi
  unsigned int v10; // r8d
  const char *v11; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  Mutex = CreateMutexExW(
            lpMutexAttributes,
            L"Global\\RegisterDeviceWithManagement-4C06D03A-BD79-458A-8889-FD9FECCAA86C",
            0,
            0x1F0001u);
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v6);
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
  return 0;
}

```

## disassembly

```asm
0x180046944  push    rbx
0x180046946  push    rbp
0x180046947  push    rsi
0x180046948  push    rdi
0x180046949  sub     rsp, 28h
0x18004694d  mov     rdi, rcx
0x180046950  lea     rdx, Name; "Global\\RegisterDeviceWithManagement-4C"...
0x180046957  mov     rcx, [rsp+48h+lpMutexAttributes]; lpMutexAttributes
0x18004695c  mov     r9d, 1F0001h; dwDesiredAccess
0x180046962  xor     r8d, r8d; dwFlags
0x180046965  call    cs:__imp_CreateMutexExW
0x18004696c  nop     dword ptr [rax+rax+00h]
0x180046971  mov     rbp, rax
0x180046974  test    rax, rax
0x180046977  jz      short loc_1800469C3
0x180046979  call    cs:__imp_GetLastError
0x180046980  nop     dword ptr [rax+rax+00h]
0x180046985  mov     rbx, [rdi]
0x180046988  test    rbx, rbx
0x18004698b  jz      short loc_1800469BC
0x18004698d  call    cs:__imp_GetLastError
0x180046994  nop     dword ptr [rax+rax+00h]
0x180046999  mov     rcx, rbx; hObject
0x18004699c  mov     esi, eax
0x18004699e  call    cs:__imp_CloseHandle
0x1800469a5  nop     dword ptr [rax+rax+00h]
0x1800469aa  test    eax, eax
0x1800469ac  jz      short loc_1800469D2
0x1800469ae  mov     ecx, esi; dwErrCode
0x1800469b0  call    cs:__imp_SetLastError
0x1800469b7  nop     dword ptr [rax+rax+00h]
0x1800469bc  mov     [rdi], rbp
0x1800469bf  xor     eax, eax
0x1800469c1  jmp     short loc_1800469C8
0x1800469c3  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800469c8  add     rsp, 28h
0x1800469cc  pop     rdi
0x1800469cd  pop     rsi
0x1800469ce  pop     rbp
0x1800469cf  pop     rbx
0x1800469d0  retn
0x1800469d2  mov     rcx, [rsp+48h]; this
0x1800469d7  mov     edx, 0A0Bh; void *
0x1800469dc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
