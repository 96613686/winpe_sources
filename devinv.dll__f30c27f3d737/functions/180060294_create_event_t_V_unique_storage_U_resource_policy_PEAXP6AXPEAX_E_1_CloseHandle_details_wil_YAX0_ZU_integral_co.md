# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180060294`
- end: `0x18006030b`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005de74`

## callees

- `0x18000aa58`
- `0x18000eabc`
- `0x180060294`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800602ad`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800602ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800602e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800602e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800602bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800602c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800602bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800602c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800602d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800602d4`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1)
{
  wil::details *v2; // rcx
  HANDLE Event; // rbp
  void *v4; // rbx
  DWORD LastError; // esi
  unsigned int v6; // r8d
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
0x180060294  push    rbx
0x180060296  push    rbp
0x180060297  push    rsi
0x180060298  push    rdi
0x180060299  sub     rsp, 28h
0x18006029d  mov     rdi, rcx
0x1800602a0  mov     r9d, 1F0003h; dwDesiredAccess
0x1800602a6  xor     ecx, ecx; lpEventAttributes
0x1800602a8  xor     r8d, r8d; dwFlags
0x1800602ab  xor     edx, edx; lpName
0x1800602ad  call    cs:__imp_CreateEventExW
0x1800602b3  mov     rbp, rax
0x1800602b6  test    rax, rax
0x1800602b9  jz      short loc_1800602ED
0x1800602bb  call    cs:__imp_GetLastError
0x1800602c1  mov     rbx, [rdi]
0x1800602c4  test    rbx, rbx
0x1800602c7  jz      short loc_1800602E6
0x1800602c9  call    cs:__imp_GetLastError
0x1800602cf  mov     rcx, rbx; hObject
0x1800602d2  mov     esi, eax
0x1800602d4  call    cs:__imp_CloseHandle
0x1800602da  test    eax, eax
0x1800602dc  jz      short loc_1800602FB
0x1800602de  mov     ecx, esi; dwErrCode
0x1800602e0  call    cs:__imp_SetLastError
0x1800602e6  mov     [rdi], rbp
0x1800602e9  xor     eax, eax
0x1800602eb  jmp     short loc_1800602F2
0x1800602ed  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800602f2  add     rsp, 28h
0x1800602f6  pop     rdi
0x1800602f7  pop     rsi
0x1800602f8  pop     rbp
0x1800602f9  pop     rbx
0x1800602fa  retn
0x1800602fb  mov     rcx, [rsp+48h]; this
0x180060300  mov     edx, 0A0Bh; void *
0x180060305  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
