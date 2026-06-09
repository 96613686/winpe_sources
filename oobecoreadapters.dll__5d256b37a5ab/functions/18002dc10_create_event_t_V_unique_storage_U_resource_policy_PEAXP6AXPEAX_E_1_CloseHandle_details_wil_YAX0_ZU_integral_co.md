# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18002dc10`
- end: `0x18002dc60`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `80`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f3c0`
- `0x18001f490`
- `0x18001f560`
- `0x180030b18`
- `0x180046384`
- `0x180049c8c`
- `0x18005aa98`
- `0x18005ace8`

## callees

- `0x180006148`
- `0x18000890c`
- `0x18002dc10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002dc2d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002dc2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dc3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dc3b`

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
0x18002dc10  mov     [rsp+arg_0], rbx
0x18002dc15  push    rdi
0x18002dc16  sub     rsp, 20h
0x18002dc1a  and     edx, 3
0x18002dc1d  mov     rdi, rcx
0x18002dc20  mov     r8d, edx; dwFlags
0x18002dc23  mov     r9d, 1F0003h; dwDesiredAccess
0x18002dc29  xor     edx, edx; lpName
0x18002dc2b  xor     ecx, ecx; lpEventAttributes
0x18002dc2d  call    cs:__imp_CreateEventExW
0x18002dc33  mov     rbx, rax
0x18002dc36  test    rax, rax
0x18002dc39  jz      short loc_18002DC50
0x18002dc3b  call    cs:__imp_GetLastError
0x18002dc41  mov     rdx, rbx
0x18002dc44  mov     rcx, rdi
0x18002dc47  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18002dc4c  xor     eax, eax
0x18002dc4e  jmp     short loc_18002DC55
0x18002dc50  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002dc55  mov     rbx, [rsp+28h+arg_0]
0x18002dc5a  add     rsp, 20h
0x18002dc5e  pop     rdi
0x18002dc5f  retn
```
