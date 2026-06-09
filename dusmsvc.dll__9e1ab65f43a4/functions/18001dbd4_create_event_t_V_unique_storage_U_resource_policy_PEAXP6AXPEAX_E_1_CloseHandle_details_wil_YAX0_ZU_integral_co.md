# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18001dbd4`
- end: `0x18001dc25`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `81`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001af08`
- `0x180030d7c`

## callees

- `0x18000d114`
- `0x18001d854`
- `0x18001dbd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001dbf1`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001dbf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dbff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dbff`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
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
0x18001dbd4  mov     [rsp+arg_0], rbx
0x18001dbd9  push    rdi
0x18001dbda  sub     rsp, 20h
0x18001dbde  and     edx, 3
0x18001dbe1  mov     rdi, rcx
0x18001dbe4  mov     r8d, edx; dwFlags
0x18001dbe7  mov     r9d, 1F0003h; dwDesiredAccess
0x18001dbed  xor     edx, edx; lpName
0x18001dbef  xor     ecx, ecx; lpEventAttributes
0x18001dbf1  call    cs:__imp_CreateEventExW
0x18001dbf7  mov     rbx, rax
0x18001dbfa  test    rax, rax
0x18001dbfd  jz      short loc_18001DC1A
0x18001dbff  call    cs:__imp_GetLastError
0x18001dc05  mov     rdx, rbx
0x18001dc08  mov     rcx, rdi
0x18001dc0b  mov     rbx, [rsp+28h+arg_0]
0x18001dc10  add     rsp, 20h
0x18001dc14  pop     rdi
0x18001dc15  jmp     ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001dc1a  mov     rcx, [rsp+28h]; this
0x18001dc1f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
