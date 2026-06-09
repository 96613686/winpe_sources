# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x1800265ac`
- end: `0x1800265fc`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `80`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180036c28`
- `0x180037a80`

## callees

- `0x1800265ac`
- `0x1800321f4`
- `0x180032360`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800265c9`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800265c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800265d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800265d7`

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
0x1800265ac  mov     [rsp+arg_0], rbx
0x1800265b1  push    rdi
0x1800265b2  sub     rsp, 20h
0x1800265b6  and     edx, 3
0x1800265b9  mov     rdi, rcx
0x1800265bc  mov     r8d, edx; dwFlags
0x1800265bf  mov     r9d, 1F0003h; dwDesiredAccess
0x1800265c5  xor     edx, edx; lpName
0x1800265c7  xor     ecx, ecx; lpEventAttributes
0x1800265c9  call    cs:__imp_CreateEventExW
0x1800265cf  mov     rbx, rax
0x1800265d2  test    rax, rax
0x1800265d5  jz      short loc_1800265EC
0x1800265d7  call    cs:__imp_GetLastError
0x1800265dd  mov     rdx, rbx
0x1800265e0  mov     rcx, rdi
0x1800265e3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800265e8  xor     eax, eax
0x1800265ea  jmp     short loc_1800265F1
0x1800265ec  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800265f1  mov     rbx, [rsp+28h+arg_0]
0x1800265f6  add     rsp, 20h
0x1800265fa  pop     rdi
0x1800265fb  retn
```
