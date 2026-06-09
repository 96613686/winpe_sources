# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x14002e5ec`
- end: `0x14002e63c`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `80`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002cc40`
- `0x14002ce94`
- `0x14002d534`

## callees

- `0x14000725c`
- `0x1400092a8`
- `0x14002e5ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002e617`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002e617`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x14002e609`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x14002e609`

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
0x14002e5ec  mov     [rsp+arg_0], rbx
0x14002e5f1  push    rdi
0x14002e5f2  sub     rsp, 20h
0x14002e5f6  and     edx, 3
0x14002e5f9  mov     rdi, rcx
0x14002e5fc  mov     r8d, edx; dwFlags
0x14002e5ff  mov     r9d, 1F0003h; dwDesiredAccess
0x14002e605  xor     edx, edx; lpName
0x14002e607  xor     ecx, ecx; lpEventAttributes
0x14002e609  call    cs:__imp_CreateEventExW
0x14002e60f  mov     rbx, rax
0x14002e612  test    rax, rax
0x14002e615  jz      short loc_14002E62C
0x14002e617  call    cs:__imp_GetLastError
0x14002e61d  mov     rdx, rbx
0x14002e620  mov     rcx, rdi
0x14002e623  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x14002e628  xor     eax, eax
0x14002e62a  jmp     short loc_14002E631
0x14002e62c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14002e631  mov     rbx, [rsp+28h+arg_0]
0x14002e636  add     rsp, 20h
0x14002e63a  pop     rdi
0x14002e63b  retn
```
