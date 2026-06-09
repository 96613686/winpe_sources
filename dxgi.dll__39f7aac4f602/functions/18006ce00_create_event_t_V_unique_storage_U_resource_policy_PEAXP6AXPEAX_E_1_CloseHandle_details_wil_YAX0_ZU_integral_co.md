# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18006ce00`
- end: `0x18006ce4d`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `77`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800289f8`
- `0x18006cc9c`
- `0x1800b1750`
- `0x1800bbbf0`

## callees

- `0x18003e5fc`
- `0x1800593f0`
- `0x18006ce00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18006ce1a`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18006ce1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ce28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ce28`

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
0x18006ce00  mov     [rsp+arg_0], rbx
0x18006ce05  push    rdi
0x18006ce06  sub     rsp, 20h
0x18006ce0a  mov     rdi, rcx
0x18006ce0d  mov     r9d, 1F0003h; dwDesiredAccess
0x18006ce13  xor     ecx, ecx; lpEventAttributes
0x18006ce15  xor     r8d, r8d; dwFlags
0x18006ce18  xor     edx, edx; lpName
0x18006ce1a  call    cs:__imp_CreateEventExW
0x18006ce20  mov     rbx, rax
0x18006ce23  test    rax, rax
0x18006ce26  jz      short loc_18006CE3D
0x18006ce28  call    cs:__imp_GetLastError
0x18006ce2e  mov     rdx, rbx
0x18006ce31  mov     rcx, rdi
0x18006ce34  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18006ce39  xor     eax, eax
0x18006ce3b  jmp     short loc_18006CE42
0x18006ce3d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18006ce42  mov     rbx, [rsp+28h+arg_0]
0x18006ce47  add     rsp, 20h
0x18006ce4b  pop     rdi
0x18006ce4c  retn
```
