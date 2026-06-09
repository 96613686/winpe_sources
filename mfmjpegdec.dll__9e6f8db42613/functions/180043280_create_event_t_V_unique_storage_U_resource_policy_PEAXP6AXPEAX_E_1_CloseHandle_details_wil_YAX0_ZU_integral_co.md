# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180043280`
- end: `0x1800432d0`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `80`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180041444`
- `0x180054284`
- `0x180054510`

## callees

- `0x18003bf6c`
- `0x18003dcd0`
- `0x180043280`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18004329d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18004329d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800432ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800432ab`

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
0x180043280  mov     [rsp+arg_0], rbx
0x180043285  push    rdi
0x180043286  sub     rsp, 20h
0x18004328a  and     edx, 3
0x18004328d  mov     rdi, rcx
0x180043290  mov     r8d, edx; dwFlags
0x180043293  mov     r9d, 1F0003h; dwDesiredAccess
0x180043299  xor     edx, edx; lpName
0x18004329b  xor     ecx, ecx; lpEventAttributes
0x18004329d  call    cs:__imp_CreateEventExW
0x1800432a3  mov     rbx, rax
0x1800432a6  test    rax, rax
0x1800432a9  jz      short loc_1800432C0
0x1800432ab  call    cs:__imp_GetLastError
0x1800432b1  mov     rdx, rbx
0x1800432b4  mov     rcx, rdi
0x1800432b7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800432bc  xor     eax, eax
0x1800432be  jmp     short loc_1800432C5
0x1800432c0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800432c5  mov     rbx, [rsp+28h+arg_0]
0x1800432ca  add     rsp, 20h
0x1800432ce  pop     rdi
0x1800432cf  retn
```
