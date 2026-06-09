# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180017f10`
- end: `0x180017f61`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `81`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017ee4`
- `0x180017fbc`
- `0x180060528`

## callees

- `0x180017f10`
- `0x180017f68`
- `0x180060a10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180017f2d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180017f2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f3b`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1,
        char a2)
{
  void *v3; // rdx
  HANDLE Event; // rbx
  unsigned int v5; // r8d
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Event = CreateEventExW(0, 0, a2 & 3, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v3, v5, v6);
  GetLastError();
  return _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
           a1,
           Event);
}

```

## disassembly

```asm
0x180017f10  mov     [rsp+arg_0], rbx
0x180017f15  push    rdi
0x180017f16  sub     rsp, 20h
0x180017f1a  and     edx, 3
0x180017f1d  mov     rdi, rcx
0x180017f20  mov     r8d, edx; dwFlags
0x180017f23  mov     r9d, 1F0003h; dwDesiredAccess
0x180017f29  xor     edx, edx; lpName
0x180017f2b  xor     ecx, ecx; lpEventAttributes
0x180017f2d  call    cs:__imp_CreateEventExW
0x180017f33  mov     rbx, rax
0x180017f36  test    rax, rax
0x180017f39  jz      short loc_180017F56
0x180017f3b  call    cs:__imp_GetLastError
0x180017f41  mov     rdx, rbx
0x180017f44  mov     rcx, rdi
0x180017f47  mov     rbx, [rsp+28h+arg_0]
0x180017f4c  add     rsp, 20h
0x180017f50  pop     rdi
0x180017f51  jmp     ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180017f56  mov     rcx, [rsp+28h]; this
0x180017f5b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
