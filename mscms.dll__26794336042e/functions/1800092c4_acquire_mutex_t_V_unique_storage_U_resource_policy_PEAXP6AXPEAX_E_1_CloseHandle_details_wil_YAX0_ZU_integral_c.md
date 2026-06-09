# ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z

- ea: `0x1800092c4`
- end: `0x18000931b`
- name: `?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z`
- size: `87`
- prototype: `_QWORD *__fastcall(HANDLE *, _QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180007fa8`
- `0x180013df4`
- `0x180026820`
- `0x1800422b4`

## callees

- `0x1800092c4`
- `0x180040358`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800092dd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800092dd`

## string_xrefs

- `0x1800092f6`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x1800092c4  mov     [rsp+arg_0], rbx
0x1800092c9  push    rdi
0x1800092ca  sub     rsp, 20h
0x1800092ce  mov     rbx, [rcx]
0x1800092d1  mov     rdi, rdx
0x1800092d4  mov     rcx, rbx; hHandle
0x1800092d7  xor     r8d, r8d; bAlertable
0x1800092da  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800092dd  call    cs:__imp_WaitForSingleObjectEx
0x1800092e3  cmp     eax, 102h
0x1800092e8  jz      short loc_180009308
0x1800092ea  test    eax, 0FFFFFF7Fh
0x1800092ef  jz      short loc_18000930A
0x1800092f1  mov     rcx, [rsp+28h]; this
0x1800092f6  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800092fd  mov     edx, 0E01h; void *
0x180009302  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180009308  xor     ebx, ebx
0x18000930a  mov     [rdi], rbx
0x18000930d  mov     rax, rdi
0x180009310  mov     rbx, [rsp+28h+arg_0]
0x180009315  add     rsp, 20h
0x180009319  pop     rdi
0x18000931a  retn
```
