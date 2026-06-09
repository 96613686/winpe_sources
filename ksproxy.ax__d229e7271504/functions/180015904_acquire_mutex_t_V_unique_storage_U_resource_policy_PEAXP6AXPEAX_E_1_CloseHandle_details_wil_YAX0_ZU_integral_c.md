# ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z

- ea: `0x180015904`
- end: `0x180015962`
- name: `?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z`
- size: `94`
- prototype: `_QWORD *__fastcall(HANDLE *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006e3c`

## callees

- `0x180015904`
- `0x180021db4`

## import_xrefs

- `KERNEL32!WaitForSingleObjectEx` at `0x18001591d`
- `KERNEL32!WaitForSingleObjectEx` at `0x18001591d`

## string_xrefs

- `0x18001593c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
    wil::details::in1diag3::FailFast_Unexpected(
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
0x180015904  mov     [rsp+arg_0], rbx
0x180015909  push    rdi
0x18001590a  sub     rsp, 20h
0x18001590e  mov     rbx, [rcx]
0x180015911  mov     rdi, rdx
0x180015914  mov     rcx, rbx; hHandle
0x180015917  xor     r8d, r8d; bAlertable
0x18001591a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001591d  call    cs:__imp_WaitForSingleObjectEx
0x180015924  nop     dword ptr [rax+rax+00h]
0x180015929  cmp     eax, 102h
0x18001592e  jz      short loc_18001594E
0x180015930  test    eax, 0FFFFFF7Fh
0x180015935  jz      short loc_180015950
0x180015937  mov     rcx, [rsp+28h]; this
0x18001593c  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180015943  mov     edx, 0E01h; void *
0x180015948  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18001594e  xor     ebx, ebx
0x180015950  mov     [rdi], rbx
0x180015953  mov     rax, rdi
0x180015956  mov     rbx, [rsp+28h+arg_0]
0x18001595b  add     rsp, 20h
0x18001595f  pop     rdi
0x180015960  retn
```
