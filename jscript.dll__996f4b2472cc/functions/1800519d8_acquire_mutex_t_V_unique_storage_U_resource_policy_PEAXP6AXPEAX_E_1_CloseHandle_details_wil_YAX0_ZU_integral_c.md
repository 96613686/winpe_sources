# ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z

- ea: `0x1800519d8`
- end: `0x180051a36`
- name: `?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z`
- size: `94`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800542b4`
- `0x18005aff0`
- `0x18005b07c`

## callees

- `0x1800519d8`
- `0x18005a008`

## import_xrefs

- `KERNEL32!WaitForSingleObjectEx` at `0x1800519f1`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800519f1`

## string_xrefs

- `0x180051a10`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x1800519d8  mov     [rsp+arg_0], rbx
0x1800519dd  push    rdi
0x1800519de  sub     rsp, 20h
0x1800519e2  mov     rbx, [rcx]
0x1800519e5  mov     rdi, rdx
0x1800519e8  mov     rcx, rbx; hHandle
0x1800519eb  xor     r8d, r8d; bAlertable
0x1800519ee  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800519f1  call    cs:__imp_WaitForSingleObjectEx
0x1800519f8  nop     dword ptr [rax+rax+00h]
0x1800519fd  cmp     eax, 102h
0x180051a02  jz      short loc_180051A22
0x180051a04  test    eax, 0FFFFFF7Fh
0x180051a09  jz      short loc_180051A24
0x180051a0b  mov     rcx, [rsp+28h]; this
0x180051a10  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180051a17  mov     edx, 0E01h; void *
0x180051a1c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180051a22  xor     ebx, ebx
0x180051a24  mov     [rdi], rbx
0x180051a27  mov     rax, rdi
0x180051a2a  mov     rbx, [rsp+28h+arg_0]
0x180051a2f  add     rsp, 20h
0x180051a33  pop     rdi
0x180051a34  retn
```
