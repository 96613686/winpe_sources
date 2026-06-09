# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180158f6c`
- end: `0x180158fbc`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `80`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801595a0`
- `0x1801f1970`
- `0x18021a6b0`
- `0x180227a80`
- `0x1802545d4`
- `0x180254d24`
- `0x180276394`
- `0x18027afe0`
- `0x18027b0ac`

## callees

- `0x180158f6c`
- `0x180158fc4`
- `0x180200520`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180158f89`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180158f89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180158f97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180158f97`

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
0x180158f6c  mov     [rsp+arg_0], rbx
0x180158f71  push    rdi
0x180158f72  sub     rsp, 20h
0x180158f76  and     edx, 3
0x180158f79  mov     rdi, rcx
0x180158f7c  mov     r8d, edx; dwFlags
0x180158f7f  mov     r9d, 1F0003h; dwDesiredAccess
0x180158f85  xor     edx, edx; lpName
0x180158f87  xor     ecx, ecx; lpEventAttributes
0x180158f89  call    cs:__imp_CreateEventExW
0x180158f8f  mov     rbx, rax
0x180158f92  test    rax, rax
0x180158f95  jz      short loc_180158FB5
0x180158f97  call    cs:__imp_GetLastError
0x180158f9d  mov     rdx, rbx
0x180158fa0  mov     rcx, rdi
0x180158fa3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180158fa8  xor     eax, eax
0x180158faa  mov     rbx, [rsp+28h+arg_0]
0x180158faf  add     rsp, 20h
0x180158fb3  pop     rdi
0x180158fb4  retn
0x180158fb5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180158fba  jmp     short loc_180158FAA
```
