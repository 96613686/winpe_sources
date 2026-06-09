# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18002894c`
- end: `0x1800289a9`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `93`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180037214`
- `0x180038eec`

## callees

- `0x18002894c`
- `0x180032e60`
- `0x180032fd8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180028969`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180028969`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002897d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002897d`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1,
        char a2)
{
  wil::details *v3; // rcx
  HANDLE Event; // rbx

  Event = CreateEventExW(0, 0, a2 & 3, 0x1F0003u);
  if ( !Event )
    return wil::details::GetLastErrorFailHr(v3);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    a1,
    Event);
  return 0;
}

```

## disassembly

```asm
0x18002894c  mov     [rsp+arg_0], rbx
0x180028951  push    rdi
0x180028952  sub     rsp, 20h
0x180028956  and     edx, 3
0x180028959  mov     rdi, rcx
0x18002895c  mov     r8d, edx; dwFlags
0x18002895f  mov     r9d, 1F0003h; dwDesiredAccess
0x180028965  xor     edx, edx; lpName
0x180028967  xor     ecx, ecx; lpEventAttributes
0x180028969  call    cs:__imp_CreateEventExW
0x180028970  nop     dword ptr [rax+rax+00h]
0x180028975  mov     rbx, rax
0x180028978  test    rax, rax
0x18002897b  jz      short loc_180028998
0x18002897d  call    cs:__imp_GetLastError
0x180028984  nop     dword ptr [rax+rax+00h]
0x180028989  mov     rdx, rbx
0x18002898c  mov     rcx, rdi
0x18002898f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180028994  xor     eax, eax
0x180028996  jmp     short loc_18002899D
0x180028998  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002899d  mov     rbx, [rsp+28h+arg_0]
0x1800289a2  add     rsp, 20h
0x1800289a6  pop     rdi
0x1800289a7  retn
```
