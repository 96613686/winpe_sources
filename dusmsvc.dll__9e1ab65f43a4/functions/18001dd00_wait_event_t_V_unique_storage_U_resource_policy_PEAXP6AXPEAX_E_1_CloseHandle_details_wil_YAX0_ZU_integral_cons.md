# ?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA_NKH@Z

- ea: `0x18001dd00`
- end: `0x18001dd3c`
- name: `?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA_NKH@Z`
- size: `60`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001c508`
- `0x1800313e4`

## callees

- `0x18000aeb8`
- `0x18001dd00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001dd0a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001dd0a`

## string_xrefs

- `0x18001dd20`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
bool __fastcall _wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_NKH_Z(
        HANDLE *a1,
        DWORD a2)
{
  DWORD v2; // eax
  const char *v3; // r9
  bool v4; // zf
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = WaitForSingleObjectEx(*a1, a2, 0);
  if ( v2 == 258 )
    return 0;
  v4 = v2 == 0;
  if ( v2 )
    wil::details::in1diag3::FailFast_Unexpected(
      retaddr,
      (void *)0xB0F,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v3);
  return v4;
}

```

## disassembly

```asm
0x18001dd00  sub     rsp, 28h
0x18001dd04  mov     rcx, [rcx]; hHandle
0x18001dd07  xor     r8d, r8d; bAlertable
0x18001dd0a  call    cs:__imp_WaitForSingleObjectEx
0x18001dd10  cmp     eax, 102h
0x18001dd15  jz      short loc_18001DD32
0x18001dd17  test    eax, eax
0x18001dd19  jz      short loc_18001DD34
0x18001dd1b  mov     rcx, [rsp+28h]; this
0x18001dd20  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001dd27  mov     edx, 0B0Fh; void *
0x18001dd2c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18001dd32  test    eax, eax
0x18001dd34  setz    al
0x18001dd37  add     rsp, 28h
0x18001dd3b  retn
```
