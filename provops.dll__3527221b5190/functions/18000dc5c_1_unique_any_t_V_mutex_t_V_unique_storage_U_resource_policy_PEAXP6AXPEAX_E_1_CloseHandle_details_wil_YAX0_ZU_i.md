# ??1?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@XZ

- ea: `0x18000dc5c`
- end: `0x18000dc8e`
- name: `??1?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@XZ`
- size: `50`
- prototype: `void __fastcall(void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180036241`
- `0x180036253`
- `0x18003644d`

## callees

- `0x18000864c`
- `0x18000dc5c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dc68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dc68`

## string_xrefs

- `0x18000dc7c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __1__unique_any_t_V__mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA_XZ(
        void **a1)
{
  void *v1; // rcx
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = *a1;
  if ( v1 )
  {
    if ( !CloseHandle(v1) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v2);
  }
}

```

## disassembly

```asm
0x18000dc5c  sub     rsp, 28h
0x18000dc60  mov     rcx, [rcx]; hObject
0x18000dc63  test    rcx, rcx
0x18000dc66  jz      short loc_18000DC72
0x18000dc68  call    cs:__imp_CloseHandle
0x18000dc6e  test    eax, eax
0x18000dc70  jz      short loc_18000DC77
0x18000dc72  add     rsp, 28h
0x18000dc76  retn
0x18000dc77  mov     rcx, [rsp+28h]; this
0x18000dc7c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000dc83  mov     edx, 0A0Bh; void *
0x18000dc88  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
