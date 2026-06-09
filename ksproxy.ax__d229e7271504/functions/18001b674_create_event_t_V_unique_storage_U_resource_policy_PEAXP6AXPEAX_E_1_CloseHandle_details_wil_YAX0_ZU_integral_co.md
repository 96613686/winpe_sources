# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18001b674`
- end: `0x18001b6ce`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `90`
- prototype: `__int64 __fastcall(wil::details **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006f1c`

## callees

- `0x180007318`
- `0x18001b674`
- `0x18001b77c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001b6a2`
- `KERNEL32!GetLastError` at `0x18001b6a2`
- `KERNEL32!CreateEventExW` at `0x18001b68e`
- `KERNEL32!CreateEventExW` at `0x18001b68e`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        wil::details **a1)
{
  wil::details *v2; // rcx
  wil::details *Event; // rbx

  Event = (wil::details *)CreateEventExW(0, 0, 0, 0x1F0003u);
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
0x18001b674  mov     [rsp+arg_0], rbx
0x18001b679  push    rdi
0x18001b67a  sub     rsp, 20h
0x18001b67e  mov     rdi, rcx
0x18001b681  mov     r9d, 1F0003h; dwDesiredAccess
0x18001b687  xor     ecx, ecx; lpEventAttributes
0x18001b689  xor     r8d, r8d; dwFlags
0x18001b68c  xor     edx, edx; lpName
0x18001b68e  call    cs:__imp_CreateEventExW
0x18001b695  nop     dword ptr [rax+rax+00h]
0x18001b69a  mov     rbx, rax
0x18001b69d  test    rax, rax
0x18001b6a0  jz      short loc_18001B6BD
0x18001b6a2  call    cs:__imp_GetLastError
0x18001b6a9  nop     dword ptr [rax+rax+00h]
0x18001b6ae  mov     rdx, rbx
0x18001b6b1  mov     rcx, rdi
0x18001b6b4  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001b6b9  xor     eax, eax
0x18001b6bb  jmp     short loc_18001B6C2
0x18001b6bd  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001b6c2  mov     rbx, [rsp+28h+arg_0]
0x18001b6c7  add     rsp, 20h
0x18001b6cb  pop     rdi
0x18001b6cc  retn
```
