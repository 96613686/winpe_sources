# ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z

- ea: `0x18003e694`
- end: `0x18003e6f2`
- name: `?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z`
- size: `94`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18003b0dc`
- `0x18003b258`
- `0x18003d11c`
- `0x18003d1a8`

## callees

- `0x18003b7a4`
- `0x18003e694`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18003e6ad`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18003e6ad`

## string_xrefs

- `0x18003e6cc`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
        HANDLE *a1,
        _QWORD *a2)
{
  HANDLE v2; // rbx
  DWORD v4; // eax
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *a1;
  v4 = WaitForSingleObjectEx(*a1, 0xFFFFFFFF, 0);
  if ( v4 == 258 )
  {
    v2 = 0;
  }
  else if ( (v4 & 0xFFFFFF7F) != 0 )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xE01,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v5);
  }
  *a2 = v2;
  return a2;
}

```

## disassembly

```asm
0x18003e694  mov     [rsp+arg_0], rbx
0x18003e699  push    rdi
0x18003e69a  sub     rsp, 20h
0x18003e69e  mov     rbx, [rcx]
0x18003e6a1  mov     rdi, rdx
0x18003e6a4  mov     rcx, rbx; hHandle
0x18003e6a7  xor     r8d, r8d; bAlertable
0x18003e6aa  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18003e6ad  call    cs:__imp_WaitForSingleObjectEx
0x18003e6b4  nop     dword ptr [rax+rax+00h]
0x18003e6b9  cmp     eax, 102h
0x18003e6be  jz      short loc_18003E6DE
0x18003e6c0  test    eax, 0FFFFFF7Fh
0x18003e6c5  jz      short loc_18003E6E0
0x18003e6c7  mov     rcx, [rsp+28h]; this
0x18003e6cc  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003e6d3  mov     edx, 0E01h; void *
0x18003e6d8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18003e6de  xor     ebx, ebx
0x18003e6e0  mov     [rdi], rbx
0x18003e6e3  mov     rax, rdi
0x18003e6e6  mov     rbx, [rsp+28h+arg_0]
0x18003e6eb  add     rsp, 20h
0x18003e6ef  pop     rdi
0x18003e6f0  retn
```
