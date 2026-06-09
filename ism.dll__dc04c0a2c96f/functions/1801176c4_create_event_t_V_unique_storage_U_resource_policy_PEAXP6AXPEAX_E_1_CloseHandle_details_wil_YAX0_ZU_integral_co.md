# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x1801176c4`
- end: `0x180117714`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `80`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800cb104`
- `0x18011771c`
- `0x18011fce4`

## callees

- `0x180057a9c`
- `0x18008db50`
- `0x1801176c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801176ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801176ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1801176e1`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1801176e1`

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
0x1801176c4  mov     [rsp+arg_0], rbx
0x1801176c9  push    rdi
0x1801176ca  sub     rsp, 20h
0x1801176ce  and     edx, 3
0x1801176d1  mov     rdi, rcx
0x1801176d4  mov     r8d, edx; dwFlags
0x1801176d7  mov     r9d, 1F0003h; dwDesiredAccess
0x1801176dd  xor     edx, edx; lpName
0x1801176df  xor     ecx, ecx; lpEventAttributes
0x1801176e1  call    cs:__imp_CreateEventExW
0x1801176e7  mov     rbx, rax
0x1801176ea  test    rax, rax
0x1801176ed  jz      short loc_180117704
0x1801176ef  call    cs:__imp_GetLastError
0x1801176f5  mov     rdx, rbx
0x1801176f8  mov     rcx, rdi
0x1801176fb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180117700  xor     eax, eax
0x180117702  jmp     short loc_180117709
0x180117704  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180117709  mov     rbx, [rsp+28h+arg_0]
0x18011770e  add     rsp, 20h
0x180117712  pop     rdi
0x180117713  retn
```
