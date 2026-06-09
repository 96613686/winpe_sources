# UserHelpers::GetUserSidString(Windows::System::IUser *)

- ea: `0x1800522d0`
- end: `0x180052386`
- name: `?GetUserSidString@UserHelpers@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIUser@System@Windows@@@Z`
- size: `182`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004f180`
- `0x180060be0`

## callees

- `0x180003230`
- `0x180009784`
- `0x1800175bc`
- `0x1800194fc`
- `0x18004c054`
- `0x1800522d0`
- `0x18005238c`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005233d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005233d`

## string_xrefs

- `0x180052347`: `ShellCommon\internal\Shell\inc\helpers\UserHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall UserHelpers::GetUserSidString(_QWORD *a1, UserHelpers *a2)
{
  PHANDLE UserTokenHandle; // rax
  const char *v4; // r9
  void *v5; // rcx
  _QWORD *v7; // [rsp+28h] [rbp-18h] BYREF
  LPWSTR StringSid; // [rsp+30h] [rbp-10h] BYREF
  char v9; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  void *Block; // [rsp+70h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp+38h] BYREF

  *a1 = 0;
  v7 = a1;
  StringSid = 0;
  v9 = 1;
  UserTokenHandle = UserHelpers::GetUserTokenHandle(&TokenHandle, a2);
  wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(&Block, *UserTokenHandle);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  if ( !ConvertSidToStringSidW(*(PSID *)Block, &StringSid) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x73,
      (unsigned int)"ShellCommon\\internal\\Shell\\inc\\helpers\\UserHelpers.h",
      v4);
  v5 = Block;
  Block = 0;
  if ( v5 )
    operator delete(v5);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v7);
  return a1;
}

```

## disassembly

```asm
0x1800522d0  mov     [rsp-18h+arg_0], rcx
0x1800522d5  push    rbp
0x1800522d6  push    rbx
0x1800522d7  push    rdi
0x1800522d8  mov     rbp, rsp
0x1800522db  sub     rsp, 40h
0x1800522df  mov     rbx, rcx
0x1800522e2  mov     [rbp+var_20], 0
0x1800522e9  mov     qword ptr [rcx], 0
0x1800522f0  mov     [rbp+var_20], 1
0x1800522f7  mov     [rbp+var_18], rcx
0x1800522fb  mov     [rbp+StringSid], 0
0x180052303  mov     [rbp+var_8], 1
0x180052307  lea     rcx, [rbp+TokenHandle]; TokenHandle
0x18005230b  call    ?GetUserTokenHandle@UserHelpers@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAUIUser@System@Windows@@@Z; UserHelpers::GetUserTokenHandle(Windows::System::IUser *)
0x180052310  nop
0x180052311  mov     rdx, [rax]
0x180052314  lea     rcx, [rbp+Block]
0x180052318  call    ??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)
0x18005231d  mov     [rbp+var_20], 0Fh
0x180052324  lea     rcx, [rbp+TokenHandle]
0x180052328  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005232d  nop
0x18005232e  mov     rdi, [rbp+18h]
0x180052332  lea     rdx, [rbp+StringSid]; StringSid
0x180052336  mov     rcx, [rbp+Block]
0x18005233a  mov     rcx, [rcx]; Sid
0x18005233d  call    cs:__imp_ConvertSidToStringSidW
0x180052343  test    eax, eax
0x180052345  jnz     short loc_18005235A
0x180052347  lea     r8, aShellcommonInt_0; "ShellCommon\\internal\\Shell\\inc\\help"...
0x18005234e  lea     edx, [rax+73h]; void *
0x180052351  mov     rcx, rdi; this
0x180052354  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18005235a  mov     rcx, [rbp+Block]; Block
0x18005235e  mov     [rbp+Block], 0
0x180052366  test    rcx, rcx
0x180052369  jz      short loc_180052371
0x18005236b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180052370  nop
0x180052371  lea     rcx, [rbp+var_18]
0x180052375  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18005237a  mov     rax, rbx
0x18005237d  add     rsp, 40h
0x180052381  pop     rdi
0x180052382  pop     rbx
0x180052383  pop     rbp
0x180052384  retn
```
