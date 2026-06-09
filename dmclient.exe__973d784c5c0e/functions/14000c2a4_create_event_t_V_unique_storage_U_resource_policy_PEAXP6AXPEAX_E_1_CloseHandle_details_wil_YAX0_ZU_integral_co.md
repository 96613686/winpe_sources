# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x14000c2a4`
- end: `0x14000c33a`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `150`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003f18`
- `0x140004198`

## callees

- `0x1400070c0`
- `0x14000bfd4`
- `0x14000c2a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x14000c2bd`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x14000c2bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c2d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c2e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c2d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c2e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c308`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c308`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c2f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c2f6`

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
0x14000c2a4  push    rbx
0x14000c2a6  push    rbp
0x14000c2a7  push    rsi
0x14000c2a8  push    rdi
0x14000c2a9  sub     rsp, 28h
0x14000c2ad  mov     rdi, rcx
0x14000c2b0  mov     r9d, 1F0003h; dwDesiredAccess
0x14000c2b6  xor     ecx, ecx; lpEventAttributes
0x14000c2b8  xor     r8d, r8d; dwFlags
0x14000c2bb  xor     edx, edx; lpName
0x14000c2bd  call    cs:__imp_CreateEventExW
0x14000c2c4  nop     dword ptr [rax+rax+00h]
0x14000c2c9  mov     rbp, rax
0x14000c2cc  test    rax, rax
0x14000c2cf  jz      short loc_14000C31B
0x14000c2d1  call    cs:__imp_GetLastError
0x14000c2d8  nop     dword ptr [rax+rax+00h]
0x14000c2dd  mov     rbx, [rdi]
0x14000c2e0  test    rbx, rbx
0x14000c2e3  jz      short loc_14000C314
0x14000c2e5  call    cs:__imp_GetLastError
0x14000c2ec  nop     dword ptr [rax+rax+00h]
0x14000c2f1  mov     rcx, rbx; hObject
0x14000c2f4  mov     esi, eax
0x14000c2f6  call    cs:__imp_CloseHandle
0x14000c2fd  nop     dword ptr [rax+rax+00h]
0x14000c302  test    eax, eax
0x14000c304  jz      short loc_14000C32A
0x14000c306  mov     ecx, esi; dwErrCode
0x14000c308  call    cs:__imp_SetLastError
0x14000c30f  nop     dword ptr [rax+rax+00h]
0x14000c314  mov     [rdi], rbp
0x14000c317  xor     eax, eax
0x14000c319  jmp     short loc_14000C320
0x14000c31b  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000c320  add     rsp, 28h
0x14000c324  pop     rdi
0x14000c325  pop     rsi
0x14000c326  pop     rbp
0x14000c327  pop     rbx
0x14000c328  retn
0x14000c32a  mov     rcx, [rsp+48h]; this
0x14000c32f  mov     edx, 0A0Bh; void *
0x14000c334  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
