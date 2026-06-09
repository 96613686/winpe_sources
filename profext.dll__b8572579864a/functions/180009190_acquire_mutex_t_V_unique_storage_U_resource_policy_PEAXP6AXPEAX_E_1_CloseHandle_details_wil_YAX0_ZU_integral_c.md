# ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z

- ea: `0x180009190`
- end: `0x1800091f0`
- name: `?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z`
- size: `96`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800090c8`
- `0x180014234`
- `0x18001a2e4`

## callees

- `0x180009190`
- `0x180016ddc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800091a9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800091a9`

## string_xrefs

- `0x1800091de`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180009190  mov     [rsp+arg_0], rbx
0x180009195  push    rdi
0x180009196  sub     rsp, 20h
0x18000919a  mov     rbx, [rcx]
0x18000919d  mov     rdi, rdx
0x1800091a0  mov     rcx, rbx; hHandle
0x1800091a3  xor     r8d, r8d; bAlertable
0x1800091a6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800091a9  call    cs:__imp_WaitForSingleObjectEx
0x1800091b0  nop     dword ptr [rax+rax+00h]
0x1800091b5  cmp     eax, 102h
0x1800091ba  jz      short loc_1800091D5
0x1800091bc  test    eax, 0FFFFFF7Fh
0x1800091c1  jnz     short loc_1800091D9
0x1800091c3  mov     [rdi], rbx
0x1800091c6  mov     rax, rdi
0x1800091c9  mov     rbx, [rsp+28h+arg_0]
0x1800091ce  add     rsp, 20h
0x1800091d2  pop     rdi
0x1800091d3  retn
0x1800091d5  xor     ebx, ebx
0x1800091d7  jmp     short loc_1800091C3
0x1800091d9  mov     rcx, [rsp+28h]; this
0x1800091de  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800091e5  mov     edx, 0E01h; void *
0x1800091ea  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
