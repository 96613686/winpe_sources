# IsAccountCloudPasswordLess(ushort const *,int *)

- ea: `0x18006494c`
- end: `0x180064a5b`
- name: `?IsAccountCloudPasswordLess@@YAJPEBGPEAH@Z`
- size: `271`
- prototype: `__int64 __fastcall(LPCWSTR StringSid, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003a3bc`

## callees

- `0x1800331d0`
- `0x18003a5cc`
- `0x18003b944`
- `0x18003b964`
- `0x18003bf28`
- `0x18003c73c`
- `0x180064770`
- `0x18006494c`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800649d8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800649d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800649b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800649b9`

## string_xrefs

- `0x180064984`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x1800649e6`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x180064a21`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IsAccountCloudPasswordLess(LPCWSTR StringSid, int *a2)
{
  int LsaUserAccountType; // eax
  unsigned int LastError; // ebx
  const char *v7; // r9
  int v8; // eax
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  unsigned int v11; // [rsp+48h] [rbp+28h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp+30h] BYREF

  *a2 = 0;
  v11 = 0;
  LsaUserAccountType = GetLsaUserAccountType(StringSid, (enum _LSA_USER_ACCOUNT_TYPE *)&v11);
  LastError = LsaUserAccountType;
  if ( LsaUserAccountType < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CA,
      (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
      (const char *)(unsigned int)LsaUserAccountType,
      savedregs);
    return LastError;
  }
  hMem = 0;
  if ( !ConvertStringSidToSidW(StringSid, &hMem) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1CD,
                  (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
                  v7);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
    return LastError;
  }
  v8 = IsAccountCloudPasswordLessInternal(hMem, v11, a2);
  LastError = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CE,
      (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
      (const char *)(unsigned int)v8,
      savedregs);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
    return LastError;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
  return 0;
}

```

## disassembly

```asm
0x18006494c  mov     [rsp-18h+arg_0], rbx
0x180064951  push    rbp
0x180064952  push    rsi
0x180064953  push    rdi; int
0x180064954  mov     rbp, rsp
0x180064957  sub     rsp, 20h
0x18006495b  mov     rsi, rdx
0x18006495e  mov     rdi, rcx
0x180064961  mov     dword ptr [rdx], 0
0x180064967  mov     [rbp+arg_8], 0
0x18006496e  lea     rdx, [rbp+arg_8]; enum _LSA_USER_ACCOUNT_TYPE *
0x180064972  call    ?GetLsaUserAccountType@@YAJPEBGPEAW4_LSA_USER_ACCOUNT_TYPE@@@Z; GetLsaUserAccountType(ushort const *,_LSA_USER_ACCOUNT_TYPE *)
0x180064977  mov     ebx, eax
0x180064979  test    eax, eax
0x18006497b  jns     short loc_18006499C
0x18006497d  mov     rcx, [rbp+18h]; this
0x180064981  mov     r9d, eax; char *
0x180064984  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x18006498b  mov     edx, 1CAh; void *
0x180064990  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064995  mov     eax, ebx
0x180064997  jmp     loc_180064A4E
0x18006499c  mov     [rbp+hMem], 0
0x1800649a4  mov     rbx, [rbp+hMem]
0x1800649a8  test    rbx, rbx
0x1800649ab  jz      short loc_1800649C9
0x1800649ad  lea     rcx, [rbp+arg_18]; this
0x1800649b1  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800649b6  mov     rcx, rbx; hMem
0x1800649b9  call    cs:__imp_LocalFree
0x1800649bf  lea     rcx, [rbp+arg_18]; this
0x1800649c3  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800649c8  nop
0x1800649c9  mov     [rbp+hMem], 0
0x1800649d1  lea     rdx, [rbp+hMem]; Sid
0x1800649d5  mov     rcx, rdi; StringSid
0x1800649d8  call    cs:__imp_ConvertStringSidToSidW
0x1800649de  test    eax, eax
0x1800649e0  jnz     short loc_180064A05
0x1800649e2  mov     rcx, [rbp+18h]; this
0x1800649e6  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x1800649ed  mov     edx, 1CDh; void *
0x1800649f2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800649f7  mov     ebx, eax
0x1800649f9  lea     rcx, [rbp+hMem]
0x1800649fd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180064a02  nop
0x180064a03  jmp     short loc_180064995
0x180064a05  mov     r8, rsi
0x180064a08  mov     edx, [rbp+arg_8]
0x180064a0b  mov     rcx, [rbp+hMem]
0x180064a0f  call    ?IsAccountCloudPasswordLessInternal@@YAJQEAXW4_LSA_USER_ACCOUNT_TYPE@@PEAH@Z; IsAccountCloudPasswordLessInternal(void * const,_LSA_USER_ACCOUNT_TYPE,int *)
0x180064a14  mov     ebx, eax
0x180064a16  test    eax, eax
0x180064a18  jns     short loc_180064A42
0x180064a1a  mov     rcx, [rbp+18h]; this
0x180064a1e  mov     r9d, eax; char *
0x180064a21  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x180064a28  mov     edx, 1CEh; void *
0x180064a2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064a32  nop
0x180064a33  lea     rcx, [rbp+hMem]
0x180064a37  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180064a3c  nop
0x180064a3d  jmp     loc_180064995
0x180064a42  lea     rcx, [rbp+hMem]
0x180064a46  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180064a4b  nop
0x180064a4c  xor     eax, eax
0x180064a4e  mov     rbx, [rsp+20h+arg_0]
0x180064a53  add     rsp, 20h
0x180064a57  pop     rdi
0x180064a58  pop     rsi
0x180064a59  pop     rbp
0x180064a5a  retn
```
