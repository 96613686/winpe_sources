# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180053644`
- end: `0x180053698`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `84`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016224`
- `0x180018a30`
- `0x180074ed0`
- `0x180077b90`
- `0x180077f00`

## callees

- `0x1800104b0`
- `0x180023214`
- `0x180053644`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180053665`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180053665`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053673`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053673`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1,
        char a2,
        const WCHAR *a3)
{
  wil::details *v4; // rcx
  HANDLE Event; // rbx

  Event = CreateEventExW(0, a3, a2 & 3, 0x1F0003u);
  if ( !Event )
    return wil::details::GetLastErrorFailHr(v4);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    a1,
    Event);
  return 0;
}

```

## disassembly

```asm
0x180053644  mov     [rsp+arg_0], rbx
0x180053649  push    rdi
0x18005364a  sub     rsp, 20h
0x18005364e  and     edx, 3
0x180053651  mov     rax, r8
0x180053654  mov     r8d, edx; dwFlags
0x180053657  mov     rdi, rcx
0x18005365a  mov     rdx, rax; lpName
0x18005365d  mov     r9d, 1F0003h; dwDesiredAccess
0x180053663  xor     ecx, ecx; lpEventAttributes
0x180053665  call    cs:__imp_CreateEventExW
0x18005366b  mov     rbx, rax
0x18005366e  test    rax, rax
0x180053671  jz      short loc_180053688
0x180053673  call    cs:__imp_GetLastError
0x180053679  mov     rdx, rbx
0x18005367c  mov     rcx, rdi
0x18005367f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180053684  xor     eax, eax
0x180053686  jmp     short loc_18005368D
0x180053688  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18005368d  mov     rbx, [rsp+28h+arg_0]
0x180053692  add     rsp, 20h
0x180053696  pop     rdi
0x180053697  retn
```
