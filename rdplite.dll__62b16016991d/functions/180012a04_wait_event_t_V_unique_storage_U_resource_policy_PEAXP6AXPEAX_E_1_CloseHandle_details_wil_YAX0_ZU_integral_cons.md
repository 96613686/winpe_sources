# ?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA_NKH@Z

- ea: `0x180012a04`
- end: `0x180012a40`
- name: `?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA_NKH@Z`
- size: `60`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000f338`
- `0x1800232c8`

## callees

- `0x180005650`
- `0x180012a04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180012a0e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180012a0e`

## string_xrefs

- `0x180012a24`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v3);
  return v4;
}

```

## disassembly

```asm
0x180012a04  sub     rsp, 28h
0x180012a08  mov     rcx, [rcx]; hHandle
0x180012a0b  xor     r8d, r8d; bAlertable
0x180012a0e  call    cs:__imp_WaitForSingleObjectEx
0x180012a14  cmp     eax, 102h
0x180012a19  jz      short loc_180012A36
0x180012a1b  test    eax, eax
0x180012a1d  jz      short loc_180012A38
0x180012a1f  mov     rcx, [rsp+28h]; this
0x180012a24  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180012a2b  mov     edx, 0B0Fh; void *
0x180012a30  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180012a36  test    eax, eax
0x180012a38  setz    al
0x180012a3b  add     rsp, 28h
0x180012a3f  retn
```
