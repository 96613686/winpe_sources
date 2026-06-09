# IsPackagePreOrderAndNotAvailable(ushort const *)

- ea: `0x18009cb90`
- end: `0x18009cd08`
- name: `?IsPackagePreOrderAndNotAvailable@@YA_NPEBG@Z`
- size: `376`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18009c0d0`

## callees

- `0x180005fac`
- `0x180010a84`
- `0x18001432c`
- `0x180015ec8`
- `0x18002031c`
- `0x18009cb90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18009cbda`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18009cbda`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009cbbe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009cbbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009cca1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009cca1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009cc42`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009cc42`
- `ext-ms-win-core-storelicensing-l1-1-0!EnsureStoreLicenseForPackageActivation` at `0x18009cc6d`
- `ext-ms-win-core-storelicensing-l1-1-0!EnsureStoreLicenseForPackageActivation` at `0x18009cc6d`

## string_xrefs

- `0x18009cce5`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18009cccf`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x18009ccf7`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`

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
  void *v7; // rbx
  int v8; // eax
  unsigned int v9; // edi
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
      (void *)0x1C60,
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
  operator delete(v7);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  v17 = v9;
  return v9 == -2143322104;
}

```

## disassembly

```asm
0x18009cb90  mov     rax, rsp
0x18009cb93  mov     [rax+8], rcx
0x18009cb97  push    rbx
0x18009cb98  push    rsi
0x18009cb99  push    rdi
0x18009cb9a  sub     rsp, 50h
0x18009cb9e  mov     rdi, rcx
0x18009cba1  and     dword ptr [rax+20h], 0
0x18009cba5  and     [rsp+68h+arg_10], 0
0x18009cbad  and     qword ptr [rax-30h], 0
0x18009cbb2  lea     rcx, [rax-30h]
0x18009cbb6  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x18009cbbb  mov     rbx, rax
0x18009cbbe  call    cs:__imp_GetCurrentProcess
0x18009cbc5  nop     dword ptr [rax+rax+00h]
0x18009cbca  mov     rsi, [rsp+68h]
0x18009cbcf  mov     r8, rbx; TokenHandle
0x18009cbd2  mov     edx, 20008h; DesiredAccess
0x18009cbd7  mov     rcx, rax; ProcessHandle
0x18009cbda  call    cs:__imp_OpenProcessToken
0x18009cbe1  nop     dword ptr [rax+rax+00h]
0x18009cbe6  test    eax, eax
0x18009cbe8  jz      loc_18009CCCF
0x18009cbee  and     [rsp+68h+Block], 0
0x18009cbf4  mov     ebx, 4
0x18009cbf9  mov     [rsp+68h+arg_18], ebx
0x18009cc00  mov     rdx, [rsp+68h+TokenHandle]
0x18009cc05  lea     rcx, [rsp+68h+Block]
0x18009cc0a  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18009cc0f  mov     rcx, [rsp+68h]; this
0x18009cc14  test    eax, eax
0x18009cc16  js      loc_18009CCE2
0x18009cc1c  and     [rsp+68h+TokenInformation], 0
0x18009cc21  and     [rsp+68h+var_38], 0
0x18009cc26  lea     rax, [rsp+68h+var_38]
0x18009cc2b  mov     qword ptr [rsp+68h+ReturnLength], rax; ReturnLength
0x18009cc30  mov     r9d, ebx; TokenInformationLength
0x18009cc33  lea     r8, [rsp+68h+TokenInformation]; TokenInformation
0x18009cc38  mov     edx, 0Ch; TokenInformationClass
0x18009cc3d  mov     rcx, [rsp+68h+TokenHandle]; TokenHandle
0x18009cc42  call    cs:__imp_GetTokenInformation
0x18009cc49  nop     dword ptr [rax+rax+00h]
0x18009cc4e  mov     rcx, [rsp+68h]; this
0x18009cc53  test    eax, eax
0x18009cc55  jz      loc_18009CCF7
0x18009cc5b  mov     rbx, [rsp+68h+Block]
0x18009cc60  xor     r9d, r9d
0x18009cc63  mov     r8, [rbx]
0x18009cc66  mov     edx, [rsp+68h+TokenInformation]
0x18009cc6a  mov     rcx, rdi
0x18009cc6d  call    cs:__imp_EnsureStoreLicenseForPackageActivation
0x18009cc74  nop     dword ptr [rax+rax+00h]
0x18009cc79  mov     edi, eax
0x18009cc7b  test    eax, eax
0x18009cc7d  jns     short loc_18009CC89
0x18009cc7f  bt      eax, 1Dh
0x18009cc83  jnb     short loc_18009CC89
0x18009cc85  btr     edi, 1Dh
0x18009cc89  mov     rcx, rbx; Block
0x18009cc8c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18009cc91  nop
0x18009cc92  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x18009cc97  lea     rax, [rcx-1]
0x18009cc9b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18009cc9f  ja      short loc_18009CCAD
0x18009cca1  call    cs:__imp_CloseHandle
0x18009cca8  nop     dword ptr [rax+rax+00h]
0x18009ccad  mov     [rsp+68h+arg_10], edi
0x18009ccb4  jmp     short loc_18009CCBD
0x18009ccb6  mov     edi, [rsp+68h+arg_10]
0x18009ccbd  cmp     edi, 803F8008h
0x18009ccc3  setz    al
0x18009ccc6  add     rsp, 50h
0x18009ccca  pop     rdi
0x18009cccb  pop     rsi
0x18009cccc  pop     rbx
0x18009cccd  retn
0x18009cccf  lea     r8, aOnecoreBaseApp_26; "onecore\\base\\appmodel\\execmodel\\des"...
0x18009ccd6  lea     edx, [rax+49h]; void *
0x18009ccd9  mov     rcx, rsi; this
0x18009ccdc  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18009cce2  mov     r9d, eax; char *
0x18009cce5  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18009ccec  mov     edx, 1C60h; void *
0x18009ccf1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009ccf7  lea     r8, aOnecoreBaseApp_26; "onecore\\base\\appmodel\\execmodel\\des"...
0x18009ccfe  lea     edx, [rax+4Eh]; void *
0x18009cd01  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
