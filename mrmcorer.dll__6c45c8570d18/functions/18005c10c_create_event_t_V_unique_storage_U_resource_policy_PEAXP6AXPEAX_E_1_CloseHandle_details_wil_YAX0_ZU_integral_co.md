# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18005c10c`
- end: `0x18005c159`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800810c0`

## callees

- `0x18005c10c`
- `0x18005c160`
- `0x18005c680`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18005c126`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18005c126`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c134`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1)
{
  wil::details *v2; // rcx
  HANDLE Event; // rbx

  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( !Event )
    return wil::details::GetLastErrorFailHr(v2);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    a1,
    Event);
  return 0;
}

```

## disassembly

```asm
0x18005c10c  mov     [rsp+arg_0], rbx
0x18005c111  push    rdi
0x18005c112  sub     rsp, 20h
0x18005c116  mov     rdi, rcx
0x18005c119  mov     r9d, 1F0003h; dwDesiredAccess
0x18005c11f  xor     ecx, ecx; lpEventAttributes
0x18005c121  xor     r8d, r8d; dwFlags
0x18005c124  xor     edx, edx; lpName
0x18005c126  call    cs:__imp_CreateEventExW
0x18005c12c  mov     rbx, rax
0x18005c12f  test    rax, rax
0x18005c132  jz      short loc_18005C152
0x18005c134  call    cs:__imp_GetLastError
0x18005c13a  mov     rdx, rbx
0x18005c13d  mov     rcx, rdi
0x18005c140  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18005c145  xor     eax, eax
0x18005c147  mov     rbx, [rsp+28h+arg_0]
0x18005c14c  add     rsp, 20h
0x18005c150  pop     rdi
0x18005c151  retn
0x18005c152  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18005c157  jmp     short loc_18005C147
```
