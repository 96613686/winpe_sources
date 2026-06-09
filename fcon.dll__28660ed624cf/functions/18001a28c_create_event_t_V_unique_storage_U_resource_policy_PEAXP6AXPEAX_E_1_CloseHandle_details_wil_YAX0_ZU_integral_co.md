# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18001a28c`
- end: `0x18001a2da`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001fa18`

## callees

- `0x180007218`
- `0x18000adb8`
- `0x18001a28c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001a2a7`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001a2a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a2b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a2b5`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1)
{
  wil::details *v2; // rcx
  HANDLE Event; // rbx

  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
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
0x18001a28c  mov     [rsp+arg_0], rbx
0x18001a291  push    rdi
0x18001a292  sub     rsp, 20h
0x18001a296  xor     edx, edx; lpName
0x18001a298  mov     rdi, rcx
0x18001a29b  xor     ecx, ecx; lpEventAttributes
0x18001a29d  mov     r9d, 1F0003h; dwDesiredAccess
0x18001a2a3  lea     r8d, [rdx+1]; dwFlags
0x18001a2a7  call    cs:__imp_CreateEventExW
0x18001a2ad  mov     rbx, rax
0x18001a2b0  test    rax, rax
0x18001a2b3  jz      short loc_18001A2CA
0x18001a2b5  call    cs:__imp_GetLastError
0x18001a2bb  mov     rdx, rbx
0x18001a2be  mov     rcx, rdi
0x18001a2c1  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001a2c6  xor     eax, eax
0x18001a2c8  jmp     short loc_18001A2CF
0x18001a2ca  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001a2cf  mov     rbx, [rsp+28h+arg_0]
0x18001a2d4  add     rsp, 20h
0x18001a2d8  pop     rdi
0x18001a2d9  retn
```
