# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x140009340`
- end: `0x1400093db`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140004520`

## callees

- `0x140005240`
- `0x140009040`
- `0x140009340`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x14000935e`
- `KERNEL32!CreateSemaphoreExW` at `0x14000935e`
- `KERNEL32!SetLastError` at `0x1400093a9`
- `KERNEL32!SetLastError` at `0x1400093a9`
- `KERNEL32!CloseHandle` at `0x140009397`
- `KERNEL32!CloseHandle` at `0x140009397`
- `KERNEL32!GetLastError` at `0x140009372`
- `KERNEL32!GetLastError` at `0x140009386`
- `KERNEL32!GetLastError` at `0x140009372`
- `KERNEL32!GetLastError` at `0x140009386`

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
0x140009340  push    rbx
0x140009342  push    rbp
0x140009343  push    rsi
0x140009344  push    rdi
0x140009345  sub     rsp, 38h
0x140009349  mov     rdi, rcx
0x14000934c  mov     [rsp+58h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140009354  xor     ecx, ecx; lpSemaphoreAttributes
0x140009356  mov     [rsp+58h+dwFlags], 0; dwFlags
0x14000935e  call    cs:__imp_CreateSemaphoreExW
0x140009365  nop     dword ptr [rax+rax+00h]
0x14000936a  mov     rbp, rax
0x14000936d  test    rax, rax
0x140009370  jz      short loc_1400093BC
0x140009372  call    cs:__imp_GetLastError
0x140009379  nop     dword ptr [rax+rax+00h]
0x14000937e  mov     rbx, [rdi]
0x140009381  test    rbx, rbx
0x140009384  jz      short loc_1400093B5
0x140009386  call    cs:__imp_GetLastError
0x14000938d  nop     dword ptr [rax+rax+00h]
0x140009392  mov     rcx, rbx; hObject
0x140009395  mov     esi, eax
0x140009397  call    cs:__imp_CloseHandle
0x14000939e  nop     dword ptr [rax+rax+00h]
0x1400093a3  test    eax, eax
0x1400093a5  jz      short loc_1400093CB
0x1400093a7  mov     ecx, esi; dwErrCode
0x1400093a9  call    cs:__imp_SetLastError
0x1400093b0  nop     dword ptr [rax+rax+00h]
0x1400093b5  mov     [rdi], rbp
0x1400093b8  xor     eax, eax
0x1400093ba  jmp     short loc_1400093C1
0x1400093bc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400093c1  add     rsp, 38h
0x1400093c5  pop     rdi
0x1400093c6  pop     rsi
0x1400093c7  pop     rbp
0x1400093c8  pop     rbx
0x1400093c9  retn
0x1400093cb  mov     rcx, [rsp+58h]; this
0x1400093d0  mov     edx, 0A0Bh; void *
0x1400093d5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
