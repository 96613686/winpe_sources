# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x1800088dc`
- end: `0x18000892c`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `80`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006fe0`
- `0x180008f10`
- `0x18021a690`
- `0x180227a60`
- `0x1802545b4`
- `0x180254d04`
- `0x180276374`
- `0x18027afc0`
- `0x18027b08c`

## callees

- `0x1800088dc`
- `0x180008934`
- `0x180200500`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800088f9`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800088f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008907`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008907`

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
0x1800088dc  mov     [rsp+arg_0], rbx
0x1800088e1  push    rdi
0x1800088e2  sub     rsp, 20h
0x1800088e6  and     edx, 3
0x1800088e9  mov     rdi, rcx
0x1800088ec  mov     r8d, edx; dwFlags
0x1800088ef  mov     r9d, 1F0003h; dwDesiredAccess
0x1800088f5  xor     edx, edx; lpName
0x1800088f7  xor     ecx, ecx; lpEventAttributes
0x1800088f9  call    cs:__imp_CreateEventExW
0x1800088ff  mov     rbx, rax
0x180008902  test    rax, rax
0x180008905  jz      short loc_180008925
0x180008907  call    cs:__imp_GetLastError
0x18000890d  mov     rdx, rbx
0x180008910  mov     rcx, rdi
0x180008913  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180008918  xor     eax, eax
0x18000891a  mov     rbx, [rsp+28h+arg_0]
0x18000891f  add     rsp, 20h
0x180008923  pop     rdi
0x180008924  retn
0x180008925  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000892a  jmp     short loc_18000891A
```
