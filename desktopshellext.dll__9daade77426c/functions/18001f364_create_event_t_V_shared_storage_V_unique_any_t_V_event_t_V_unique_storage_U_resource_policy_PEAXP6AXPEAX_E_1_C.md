# ?create@?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18001f364`
- end: `0x18001f410`
- name: `?create@?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800087a0`

## callees

- `0x180009c00`
- `0x18001a18c`
- `0x18001f364`
- `0x18002a8bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001f38b`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001f38b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f399`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f399`

## string_xrefs

- `0x18001f382`: `ShellLauncherReadyEvent`
- `0x18001f3fe`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall _create___event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        _QWORD *a1)
{
  HANDLE Event; // rdi
  const char *v3; // r9
  std::_Ref_count_base *v4; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  _DWORD *v6; // [rsp+48h] [rbp+20h]

  Event = CreateEventExW(0, L"ShellLauncherReadyEvent", 1u, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1CC8,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      v3);
  GetLastError();
  v6 = operator new(0x18u);
  *(_OWORD *)v6 = 0;
  v6[2] = 1;
  v6[3] = 1;
  *(_QWORD *)v6 = ___7___Ref_count_obj2_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___std__6B_;
  *((_QWORD *)v6 + 2) = Event;
  *a1 = v6 + 4;
  v4 = (std::_Ref_count_base *)a1[1];
  a1[1] = v6;
  if ( v4 )
    std::_Ref_count_base::_Decref(v4);
}

```

## disassembly

```asm
0x18001f364  mov     [rsp+arg_0], rbx
0x18001f369  mov     [rsp+arg_18], r9
0x18001f36e  push    rdi
0x18001f36f  sub     rsp, 20h
0x18001f373  mov     rbx, rcx
0x18001f376  mov     r9d, 1F0003h; dwDesiredAccess
0x18001f37c  mov     r8d, 1; dwFlags
0x18001f382  lea     rdx, Name; "ShellLauncherReadyEvent"
0x18001f389  xor     ecx, ecx; lpEventAttributes
0x18001f38b  call    cs:__imp_CreateEventExW
0x18001f391  mov     rdi, rax
0x18001f394  test    rax, rax
0x18001f397  jz      short loc_18001F3F9
0x18001f399  call    cs:__imp_GetLastError
0x18001f39f  mov     [rsp+28h+arg_18], rdi
0x18001f3a4  mov     ecx, 18h; Size
0x18001f3a9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f3ae  mov     [rsp+28h+arg_18], rax
0x18001f3b3  xorps   xmm0, xmm0
0x18001f3b6  movups  xmmword ptr [rax], xmm0
0x18001f3b9  mov     dword ptr [rax+8], 1
0x18001f3c0  mov     dword ptr [rax+0Ch], 1
0x18001f3c7  lea     rcx, ??_7?$_Ref_count_obj2@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@std@@6B@
0x18001f3ce  mov     [rax], rcx
0x18001f3d1  lea     rcx, [rax+10h]
0x18001f3d5  mov     [rcx], rdi
0x18001f3d8  mov     [rbx], rcx
0x18001f3db  mov     rcx, [rbx+8]; this
0x18001f3df  mov     [rbx+8], rax
0x18001f3e3  test    rcx, rcx
0x18001f3e6  jz      short loc_18001F3EE
0x18001f3e8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001f3ed  nop
0x18001f3ee  mov     rbx, [rsp+28h+arg_0]
0x18001f3f3  add     rsp, 20h
0x18001f3f7  pop     rdi
0x18001f3f8  retn
0x18001f3f9  mov     rcx, [rsp+28h]; this
0x18001f3fe  lea     r8, aOnecoreInterna_16; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001f405  mov     edx, 1CC8h; void *
0x18001f40a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
