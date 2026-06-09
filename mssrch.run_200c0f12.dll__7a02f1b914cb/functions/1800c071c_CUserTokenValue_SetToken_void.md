# CUserTokenValue::SetToken(void *)

- ea: `0x1800c071c`
- end: `0x1800c0855`
- name: `?SetToken@CUserTokenValue@@QEAAJPEAX@Z`
- size: `313`
- prototype: `int(CUserTokenValue *__hidden this, void *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18010c1d0`
- `0x18010c3c0`

## callees

- `0x180022710`
- `0x180026b58`
- `0x1800a35d8`
- `0x1800c071c`
- `0x1800eb1b0`
- `0x18011fa70`
- `0x1801249b0`
- `0x1801249ec`
- `0x18019d12c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c0756`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c0756`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c0791`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c0791`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c074c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c07cb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c074c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c07cb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800c07fe`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800c07fe`

## pseudocode

```c
__int64 __fastcall CUserTokenValue::SetToken(const wchar_t **this, void *a2)
{
  int Error; // edi
  void **v5; // rsi
  void *v7; // rcx
  BOOL v8; // ebx
  char *v9; // [rsp+30h] [rbp-58h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-50h] BYREF
  char v11; // [rsp+40h] [rbp-48h]
  DWORD TokenInformationLength; // [rsp+A0h] [rbp+18h] BYREF

  Error = 0;
  TokenInformationLength = 0;
  if ( !GetTokenInformation(a2, TokenUser, 0, 0, &TokenInformationLength) && GetLastError() != 122 )
    Error = ResultFromLastError();
  v5 = 0;
  if ( Error < 0 )
    goto LABEL_7;
  v5 = (void **)operator new[](TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v5 )
  {
    Error = -2147024882;
LABEL_7:
    CloseHandle(a2);
    goto LABEL_8;
  }
  if ( !GetTokenInformation(a2, TokenUser, v5, TokenInformationLength, &TokenInformationLength) )
    Error = ResultFromLastError();
  if ( Error < 0 )
    goto LABEL_7;
  v7 = *v5;
  v9 = (char *)(this + 6);
  StringSid = 0;
  v11 = 1;
  v8 = ConvertSidToStringSidW(v7, &StringSid);
  wil::details::out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v9);
  if ( !v8 )
  {
    Error = ResultFromLastError();
    if ( Error < 0 )
      goto LABEL_7;
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    this + 5,
    a2);
  CUserTokenKey::Init((CUserTokenKey *)(this + 2), this[6]);
  if ( IsCDPLEnabled() )
    CUserTokenValue::UpdateDplKeyStatus((CUserTokenValue *)this);
LABEL_8:
  operator delete(v5);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800c071c  mov     rax, rsp
0x1800c071f  push    rbx
0x1800c0720  push    rbp
0x1800c0721  push    rsi
0x1800c0722  push    rdi
0x1800c0723  push    r14
0x1800c0725  push    r15
0x1800c0727  sub     rsp, 58h
0x1800c072b  mov     r14, rdx
0x1800c072e  lea     rax, [rax+18h]
0x1800c0732  xor     edi, edi
0x1800c0734  mov     [rsp+88h+ReturnLength], rax; ReturnLength
0x1800c0739  mov     [rax], edi
0x1800c073b  mov     rbp, rcx
0x1800c073e  xor     r9d, r9d; TokenInformationLength
0x1800c0741  xor     r8d, r8d; TokenInformation
0x1800c0744  mov     rcx, r14; TokenHandle
0x1800c0747  lea     ebx, [rdi+1]
0x1800c074a  mov     edx, ebx; TokenInformationClass
0x1800c074c  call    cs:__imp_GetTokenInformation
0x1800c0752  test    eax, eax
0x1800c0754  jnz     short loc_1800C0768
0x1800c0756  call    cs:__imp_GetLastError
0x1800c075c  cmp     eax, 7Ah ; 'z'
0x1800c075f  jz      short loc_1800C0768
0x1800c0761  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800c0766  mov     edi, eax
0x1800c0768  xor     esi, esi
0x1800c076a  test    edi, edi
0x1800c076c  js      short loc_1800C078E
0x1800c076e  mov     ecx, [rsp+88h+TokenInformationLength]; unsigned __int64
0x1800c0775  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800c077c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800c0781  mov     rsi, rax
0x1800c0784  test    rax, rax
0x1800c0787  jnz     short loc_1800C07AE
0x1800c0789  mov     edi, 8007000Eh
0x1800c078e  mov     rcx, r14; hObject
0x1800c0791  call    cs:__imp_CloseHandle
0x1800c0797  mov     rcx, rsi; Block
0x1800c079a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c079f  mov     eax, edi
0x1800c07a1  add     rsp, 58h
0x1800c07a5  pop     r15
0x1800c07a7  pop     r14
0x1800c07a9  pop     rdi
0x1800c07aa  pop     rsi
0x1800c07ab  pop     rbp
0x1800c07ac  pop     rbx
0x1800c07ad  retn
0x1800c07ae  mov     r9d, [rsp+88h+TokenInformationLength]; TokenInformationLength
0x1800c07b6  lea     rax, [rsp+88h+TokenInformationLength]
0x1800c07be  mov     r8, rsi; TokenInformation
0x1800c07c1  mov     [rsp+88h+ReturnLength], rax; ReturnLength
0x1800c07c6  mov     edx, ebx; TokenInformationClass
0x1800c07c8  mov     rcx, r14; TokenHandle
0x1800c07cb  call    cs:__imp_GetTokenInformation
0x1800c07d1  test    eax, eax
0x1800c07d3  jnz     short loc_1800C07DC
0x1800c07d5  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800c07da  mov     edi, eax
0x1800c07dc  test    edi, edi
0x1800c07de  js      short loc_1800C078E
0x1800c07e0  mov     rcx, [rsi]; Sid
0x1800c07e3  lea     r15, [rbp+30h]
0x1800c07e7  lea     rdx, [rsp+88h+StringSid]; StringSid
0x1800c07ec  mov     [rsp+88h+var_58], r15
0x1800c07f1  mov     [rsp+88h+StringSid], 0
0x1800c07fa  mov     [rsp+88h+var_48], bl
0x1800c07fe  call    cs:__imp_ConvertSidToStringSidW
0x1800c0804  lea     rcx, [rsp+88h+var_58]
0x1800c0809  mov     ebx, eax
0x1800c080b  call    ??1?$out_param_t@V?$unique_ptr@_WU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800c0810  test    ebx, ebx
0x1800c0812  jnz     short loc_1800C0823
0x1800c0814  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800c0819  mov     edi, eax
0x1800c081b  test    eax, eax
0x1800c081d  js      loc_1800C078E
0x1800c0823  lea     rcx, [rbp+28h]
0x1800c0827  mov     rdx, r14
0x1800c082a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800c082f  mov     rdx, [r15]; wchar_t *
0x1800c0832  lea     rcx, [rbp+10h]; this
0x1800c0836  call    ?Init@CUserTokenKey@@QEAAXPEB_W@Z; CUserTokenKey::Init(wchar_t const *)
0x1800c083b  call    ?IsCDPLEnabled@@YA_NXZ; IsCDPLEnabled(void)
0x1800c0840  test    al, al
0x1800c0842  jz      loc_1800C0797
0x1800c0848  mov     rcx, rbp; this
0x1800c084b  call    ?UpdateDplKeyStatus@CUserTokenValue@@QEAAJXZ; CUserTokenValue::UpdateDplKeyStatus(void)
0x1800c0850  jmp     loc_1800C0797
```
