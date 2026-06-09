# IsPackagePreOrderAndNotAvailable(ushort const *)

- ea: `0x18009e4a0`
- end: `0x18009e62f`
- name: `?IsPackagePreOrderAndNotAvailable@@YA_NPEBG@Z`
- size: `399`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18009db10`

## callees

- `0x1800057fc`
- `0x1800125f4`
- `0x1800160a0`
- `0x180017aa4`
- `0x1800210fc`
- `0x18009e4a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009e4d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009e4d7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18009e4f3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18009e4f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009e5c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009e5c8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009e564`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009e564`
- `ext-ms-win-core-storelicensing-l1-1-0!EnsureStoreLicenseForPackageActivation` at `0x18009e58f`
- `ext-ms-win-core-storelicensing-l1-1-0!EnsureStoreLicenseForPackageActivation` at `0x18009e58f`

## string_xrefs

- `0x18009e60c`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18009e5f6`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x18009e61e`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
bool __fastcall IsPackagePreOrderAndNotAvailable(const unsigned __int16 *a1)
{
  void **v2; // rbx
  HANDLE CurrentProcess; // rax
  const char *v4; // r9
  int token_information; // eax
  const char *v6; // r9
  void *v7; // rdi
  int v8; // eax
  unsigned int v9; // ebx
  int ReturnLength; // [rsp+20h] [rbp-48h]
  DWORD v12; // [rsp+30h] [rbp-38h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-30h] BYREF
  void *Block; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  unsigned int TokenInformation; // [rsp+78h] [rbp+10h] BYREF
  unsigned int v17; // [rsp+80h] [rbp+18h]
  int v18; // [rsp+88h] [rbp+20h]

  v18 = 0;
  v17 = 0;
  TokenHandle = 0;
  v2 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&TokenHandle);
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x20008u, v2) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x49,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
      v4);
  Block = 0;
  v18 = 4;
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, (__int64)TokenHandle);
  if ( token_information < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)token_information,
      ReturnLength);
  TokenInformation = 0;
  v12 = 0;
  if ( !GetTokenInformation(TokenHandle, TokenSessionId, &TokenInformation, 4u, &v12) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x4E,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
      v6);
  v7 = Block;
  v8 = EnsureStoreLicenseForPackageActivation(a1, TokenInformation, *(_QWORD *)Block, 0);
  v9 = v8;
  if ( v8 < 0 && (v8 & 0x20000000) != 0 )
    v9 = v8 & 0xDFFFFFFF;
  if ( v7 )
    operator delete(v7);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  v17 = v9;
  return v9 == -2143322104;
}

```

## disassembly

```asm
0x18009e4a0  mov     rax, rsp
0x18009e4a3  mov     [rax+8], rcx
0x18009e4a7  push    rbx
0x18009e4a8  push    rsi
0x18009e4a9  push    rdi
0x18009e4aa  sub     rsp, 50h
0x18009e4ae  mov     rsi, rcx
0x18009e4b1  mov     dword ptr [rax+20h], 0
0x18009e4b8  mov     [rsp+68h+arg_10], 0
0x18009e4c3  mov     qword ptr [rax-30h], 0
0x18009e4cb  lea     rcx, [rax-30h]
0x18009e4cf  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x18009e4d4  mov     rbx, rax
0x18009e4d7  call    cs:__imp_GetCurrentProcess
0x18009e4de  nop     dword ptr [rax+rax+00h]
0x18009e4e3  mov     rdi, [rsp+68h]
0x18009e4e8  mov     r8, rbx; TokenHandle
0x18009e4eb  mov     edx, 20008h; DesiredAccess
0x18009e4f0  mov     rcx, rax; ProcessHandle
0x18009e4f3  call    cs:__imp_OpenProcessToken
0x18009e4fa  nop     dword ptr [rax+rax+00h]
0x18009e4ff  test    eax, eax
0x18009e501  jz      loc_18009E5F6
0x18009e507  mov     [rsp+68h+Block], 0
0x18009e510  mov     ebx, 4
0x18009e515  mov     [rsp+68h+arg_18], ebx
0x18009e51c  mov     rdx, [rsp+68h+TokenHandle]
0x18009e521  lea     rcx, [rsp+68h+Block]
0x18009e526  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18009e52b  mov     rcx, [rsp+68h]; this
0x18009e530  test    eax, eax
0x18009e532  js      loc_18009E609
0x18009e538  mov     [rsp+68h+TokenInformation], 0
0x18009e540  mov     [rsp+68h+var_38], 0
0x18009e548  lea     rax, [rsp+68h+var_38]
0x18009e54d  mov     qword ptr [rsp+68h+ReturnLength], rax; ReturnLength
0x18009e552  mov     r9d, ebx; TokenInformationLength
0x18009e555  lea     r8, [rsp+68h+TokenInformation]; TokenInformation
0x18009e55a  mov     edx, 0Ch; TokenInformationClass
0x18009e55f  mov     rcx, [rsp+68h+TokenHandle]; TokenHandle
0x18009e564  call    cs:__imp_GetTokenInformation
0x18009e56b  nop     dword ptr [rax+rax+00h]
0x18009e570  mov     rcx, [rsp+68h]; this
0x18009e575  test    eax, eax
0x18009e577  jz      loc_18009E61E
0x18009e57d  xor     r9d, r9d
0x18009e580  mov     rdi, [rsp+68h+Block]
0x18009e585  mov     r8, [rdi]
0x18009e588  mov     edx, [rsp+68h+TokenInformation]
0x18009e58c  mov     rcx, rsi
0x18009e58f  call    cs:__imp_EnsureStoreLicenseForPackageActivation
0x18009e596  nop     dword ptr [rax+rax+00h]
0x18009e59b  mov     ebx, eax
0x18009e59d  test    eax, eax
0x18009e59f  jns     short loc_18009E5AB
0x18009e5a1  bt      eax, 1Dh
0x18009e5a5  jnb     short loc_18009E5AB
0x18009e5a7  btr     ebx, 1Dh
0x18009e5ab  test    rdi, rdi
0x18009e5ae  jz      short loc_18009E5B9
0x18009e5b0  mov     rcx, rdi; Block
0x18009e5b3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18009e5b8  nop
0x18009e5b9  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x18009e5be  lea     rax, [rcx-1]
0x18009e5c2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18009e5c6  ja      short loc_18009E5D4
0x18009e5c8  call    cs:__imp_CloseHandle
0x18009e5cf  nop     dword ptr [rax+rax+00h]
0x18009e5d4  mov     [rsp+68h+arg_10], ebx
0x18009e5db  jmp     short loc_18009E5E4
0x18009e5dd  mov     ebx, [rsp+68h+arg_10]
0x18009e5e4  cmp     ebx, 803F8008h
0x18009e5ea  setz    al
0x18009e5ed  add     rsp, 50h
0x18009e5f1  pop     rdi
0x18009e5f2  pop     rsi
0x18009e5f3  pop     rbx
0x18009e5f4  retn
0x18009e5f6  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\execmodel\\des"...
0x18009e5fd  lea     edx, [rax+49h]; void *
0x18009e600  mov     rcx, rdi; this
0x18009e603  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18009e609  mov     r9d, eax; char *
0x18009e60c  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18009e613  mov     edx, 1CBEh; void *
0x18009e618  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009e61e  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\execmodel\\des"...
0x18009e625  lea     edx, [rax+4Eh]; void *
0x18009e628  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
