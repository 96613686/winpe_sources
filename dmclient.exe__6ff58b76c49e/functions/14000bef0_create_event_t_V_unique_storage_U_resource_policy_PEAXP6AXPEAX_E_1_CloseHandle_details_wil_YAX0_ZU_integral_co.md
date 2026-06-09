# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x14000bef0`
- end: `0x14000bf67`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `119`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003e98`
- `0x140004110`

## callees

- `0x140006fb8`
- `0x14000bc2c`
- `0x14000bef0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x14000bf09`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x14000bf09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bf17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bf25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bf17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bf25`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000bf3c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000bf3c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bf30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bf30`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1)
{
  wil::details *v2; // rcx
  HANDLE Event; // rbp
  void *v4; // rbx
  DWORD LastError; // esi
  __int64 v6; // r8
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( !Event )
    return wil::details::GetLastErrorFailHr(v2);
  GetLastError();
  v4 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v4) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v6, v7);
    SetLastError(LastError);
  }
  *a1 = Event;
  return 0;
}

```

## disassembly

```asm
0x14000bef0  push    rbx
0x14000bef2  push    rbp
0x14000bef3  push    rsi
0x14000bef4  push    rdi
0x14000bef5  sub     rsp, 28h
0x14000bef9  mov     rdi, rcx
0x14000befc  mov     r9d, 1F0003h; dwDesiredAccess
0x14000bf02  xor     ecx, ecx; lpEventAttributes
0x14000bf04  xor     r8d, r8d; dwFlags
0x14000bf07  xor     edx, edx; lpName
0x14000bf09  call    cs:__imp_CreateEventExW
0x14000bf0f  mov     rbp, rax
0x14000bf12  test    rax, rax
0x14000bf15  jz      short loc_14000BF49
0x14000bf17  call    cs:__imp_GetLastError
0x14000bf1d  mov     rbx, [rdi]
0x14000bf20  test    rbx, rbx
0x14000bf23  jz      short loc_14000BF42
0x14000bf25  call    cs:__imp_GetLastError
0x14000bf2b  mov     rcx, rbx; hObject
0x14000bf2e  mov     esi, eax
0x14000bf30  call    cs:__imp_CloseHandle
0x14000bf36  test    eax, eax
0x14000bf38  jz      short loc_14000BF57
0x14000bf3a  mov     ecx, esi; dwErrCode
0x14000bf3c  call    cs:__imp_SetLastError
0x14000bf42  mov     [rdi], rbp
0x14000bf45  xor     eax, eax
0x14000bf47  jmp     short loc_14000BF4E
0x14000bf49  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000bf4e  add     rsp, 28h
0x14000bf52  pop     rdi
0x14000bf53  pop     rsi
0x14000bf54  pop     rbp
0x14000bf55  pop     rbx
0x14000bf56  retn
0x14000bf57  mov     rcx, [rsp+48h]; this
0x14000bf5c  mov     edx, 0A0Bh; void *
0x14000bf61  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
