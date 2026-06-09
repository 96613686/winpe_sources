# PFXCertificate::GetCurrentUserSID(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800feac8`
- end: `0x1800fec69`
- name: `?GetCurrentUserSID@PFXCertificate@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `417`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800ff3bc`

## callees

- `0x1800232e4`
- `0x180023fa0`
- `0x180025a78`
- `0x18002dc38`
- `0x18004568c`
- `0x180048624`
- `0x180065770`
- `0x1800657d4`
- `0x1800feac8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800feb1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800feb75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800febb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fec0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800feb1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800feb75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800febb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fec0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800feaed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800feaed`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800feb0b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800feb0b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800feb65`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800feba9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800feb65`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800feba9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800febfd`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800febfd`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PFXCertificate::GetCurrentUserSID(__int64 a1, __int64 a2)
{
  HANDLE CurrentThread; // rax
  signed int v4; // eax
  unsigned int v5; // ebx
  signed int v6; // eax
  PSID *v7; // rbx
  signed int LastError; // eax
  LPVOID TokenInformation[4]; // [rsp+30h] [rbp-20h] BYREF
  __int64 TokenInformationLength; // [rsp+70h] [rbp+20h] BYREF
  LPWSTR StringSid; // [rsp+80h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+88h] [rbp+38h] BYREF

  TokenInformationLength = a1;
  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>(TokenInformation);
    LODWORD(TokenInformationLength) = 0;
    if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, (PDWORD)&TokenInformationLength)
      || GetLastError() == 122
      && (std::vector<unsigned short>::resize(TokenInformation, (unsigned int)TokenInformationLength),
          GetTokenInformation(
            TokenHandle,
            TokenUser,
            TokenInformation[0],
            TokenInformationLength,
            (PDWORD)&TokenInformationLength)) )
    {
      StringSid = 0;
      v7 = (PSID *)TokenInformation[0];
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &StringSid,
        0);
      if ( ConvertSidToStringSidW(*v7, &StringSid) )
      {
        std::wstring::operator=(a2, StringSid);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
        std::vector<unsigned short>::_Tidy(TokenInformation);
        v5 = 0;
        goto LABEL_15;
      }
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
    }
    else
    {
      v6 = GetLastError();
      v5 = v6;
      if ( v6 > 0 )
        v5 = (unsigned __int16)v6 | 0x80070000;
    }
    std::vector<unsigned short>::_Tidy(TokenInformation);
  }
  else
  {
    v4 = GetLastError();
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
  }
LABEL_15:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return v5;
}

```

## disassembly

```asm
0x1800feac8  mov     [rsp-18h+TokenInformationLength], rcx
0x1800feacd  push    rbp
0x1800feace  push    rbx
0x1800feacf  push    rdi
0x1800fead0  mov     rbp, rsp
0x1800fead3  sub     rsp, 50h
0x1800fead7  mov     rdi, rdx
0x1800feada  mov     [rbp+TokenHandle], 0
0x1800feae2  xor     edx, edx
0x1800feae4  lea     rcx, [rbp+TokenHandle]
0x1800feae8  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800feaed  call    cs:__imp_GetCurrentThread
0x1800feaf4  nop     dword ptr [rax+rax+00h]
0x1800feaf9  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800feafd  mov     ebx, 1
0x1800feb02  mov     r8d, ebx; OpenAsSelf
0x1800feb05  lea     edx, [rbx+7]; DesiredAccess
0x1800feb08  mov     rcx, rax; ThreadHandle
0x1800feb0b  call    cs:__imp_OpenThreadToken
0x1800feb12  nop     dword ptr [rax+rax+00h]
0x1800feb17  test    eax, eax
0x1800feb19  jnz     short loc_1800FEB3F
0x1800feb1b  call    cs:__imp_GetLastError
0x1800feb22  nop     dword ptr [rax+rax+00h]
0x1800feb27  mov     ebx, eax
0x1800feb29  test    eax, eax
0x1800feb2b  jle     loc_1800FEC55
0x1800feb31  movzx   ebx, ax
0x1800feb34  or      ebx, 80070000h
0x1800feb3a  jmp     loc_1800FEC55
0x1800feb3f  lea     rcx, [rbp+TokenInformation]
0x1800feb43  call    ??0?$vector@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@V?$allocator@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@3@@std@@QEAA@XZ; std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t>>::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t>>(void)
0x1800feb48  nop
0x1800feb49  mov     dword ptr [rbp+TokenInformationLength], 0
0x1800feb50  lea     rax, [rbp+TokenInformationLength]
0x1800feb54  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x1800feb59  xor     r9d, r9d; TokenInformationLength
0x1800feb5c  xor     r8d, r8d; TokenInformation
0x1800feb5f  mov     edx, ebx; TokenInformationClass
0x1800feb61  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800feb65  call    cs:__imp_GetTokenInformation
0x1800feb6c  nop     dword ptr [rax+rax+00h]
0x1800feb71  test    eax, eax
0x1800feb73  jnz     short loc_1800FEBDF
0x1800feb75  call    cs:__imp_GetLastError
0x1800feb7c  nop     dword ptr [rax+rax+00h]
0x1800feb81  cmp     eax, 7Ah ; 'z'
0x1800feb84  jnz     short loc_1800FEBB9
0x1800feb86  mov     edx, dword ptr [rbp+TokenInformationLength]
0x1800feb89  lea     rcx, [rbp+TokenInformation]
0x1800feb8d  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800feb92  lea     rax, [rbp+TokenInformationLength]
0x1800feb96  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x1800feb9b  mov     r9d, dword ptr [rbp+TokenInformationLength]; TokenInformationLength
0x1800feb9f  mov     r8, [rbp+TokenInformation]; TokenInformation
0x1800feba3  mov     edx, ebx; TokenInformationClass
0x1800feba5  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800feba9  call    cs:__imp_GetTokenInformation
0x1800febb0  nop     dword ptr [rax+rax+00h]
0x1800febb5  test    eax, eax
0x1800febb7  jnz     short loc_1800FEBDF
0x1800febb9  call    cs:__imp_GetLastError
0x1800febc0  nop     dword ptr [rax+rax+00h]
0x1800febc5  test    eax, eax
0x1800febc7  mov     ebx, eax
0x1800febc9  jle     short loc_1800FEBD4
0x1800febcb  movzx   ebx, ax
0x1800febce  or      ebx, 80070000h
0x1800febd4  lea     rcx, [rbp+TokenInformation]
0x1800febd8  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800febdd  jmp     short loc_1800FEC55
0x1800febdf  mov     [rbp+StringSid], 0
0x1800febe7  mov     rbx, [rbp+TokenInformation]
0x1800febeb  xor     edx, edx
0x1800febed  lea     rcx, [rbp+StringSid]
0x1800febf1  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800febf6  lea     rdx, [rbp+StringSid]; StringSid
0x1800febfa  mov     rcx, [rbx]; Sid
0x1800febfd  call    cs:__imp_ConvertSidToStringSidW
0x1800fec04  nop     dword ptr [rax+rax+00h]
0x1800fec09  test    eax, eax
0x1800fec0b  jnz     short loc_1800FEC33
0x1800fec0d  call    cs:__imp_GetLastError
0x1800fec14  nop     dword ptr [rax+rax+00h]
0x1800fec19  mov     ebx, eax
0x1800fec1b  test    eax, eax
0x1800fec1d  jle     short loc_1800FEC28
0x1800fec1f  movzx   ebx, ax
0x1800fec22  or      ebx, 80070000h
0x1800fec28  lea     rcx, [rbp+StringSid]
0x1800fec2c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800fec31  jmp     short loc_1800FEBD4
0x1800fec33  mov     rdx, [rbp+StringSid]
0x1800fec37  mov     rcx, rdi
0x1800fec3a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x1800fec3f  nop
0x1800fec40  lea     rcx, [rbp+StringSid]
0x1800fec44  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800fec49  nop
0x1800fec4a  lea     rcx, [rbp+TokenInformation]
0x1800fec4e  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800fec53  xor     ebx, ebx
0x1800fec55  lea     rcx, [rbp+TokenHandle]
0x1800fec59  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800fec5e  mov     eax, ebx
0x1800fec60  add     rsp, 50h
0x1800fec64  pop     rdi
0x1800fec65  pop     rbx
0x1800fec66  pop     rbp
0x1800fec67  retn
```
