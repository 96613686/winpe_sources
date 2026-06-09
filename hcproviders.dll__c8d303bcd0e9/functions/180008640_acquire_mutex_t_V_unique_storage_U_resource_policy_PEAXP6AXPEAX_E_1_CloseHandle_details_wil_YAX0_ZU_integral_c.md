# ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z

- ea: `0x180008640`
- end: `0x180008692`
- name: `?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z`
- size: `82`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180004914`
- `0x1800066b8`

## callees

- `0x180006a64`
- `0x180008640`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008659`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008659`

## pseudocode

```c
_QWORD *__fastcall _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
        HANDLE *a1,
        _QWORD *a2)
{
  HANDLE v2; // rbx
  DWORD v4; // eax
  void *v5; // rdx
  unsigned int v6; // r8d
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *a1;
  v4 = WaitForSingleObjectEx(*a1, 0xFFFFFFFF, 0);
  if ( v4 == 258 )
  {
    v2 = 0;
  }
  else if ( (v4 & 0xFFFFFF7F) != 0 )
  {
    wil::details::in1diag3::FailFast_Unexpected(retaddr, v5, v6, v7);
  }
  *a2 = v2;
  return a2;
}

```

## disassembly

```asm
0x180008640  mov     [rsp+arg_0], rbx
0x180008645  push    rdi
0x180008646  sub     rsp, 20h
0x18000864a  mov     rbx, [rcx]
0x18000864d  mov     rdi, rdx
0x180008650  mov     rcx, rbx; hHandle
0x180008653  xor     r8d, r8d; bAlertable
0x180008656  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180008659  call    cs:__imp_WaitForSingleObjectEx
0x180008660  nop     dword ptr [rax+rax+00h]
0x180008665  cmp     eax, 102h
0x18000866a  jz      short loc_18000867E
0x18000866c  test    eax, 0FFFFFF7Fh
0x180008671  jz      short loc_180008680
0x180008673  mov     rcx, [rsp+28h]; this
0x180008678  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000867e  xor     ebx, ebx
0x180008680  mov     [rdi], rbx
0x180008683  mov     rax, rdi
0x180008686  mov     rbx, [rsp+28h+arg_0]
0x18000868b  add     rsp, 20h
0x18000868f  pop     rdi
0x180008690  retn
```
