# GetLsaUserAccountType(ushort const *,_LSA_USER_ACCOUNT_TYPE *)

- ea: `0x180064770`
- end: `0x180064880`
- name: `?GetLsaUserAccountType@@YAJPEBGPEAW4_LSA_USER_ACCOUNT_TYPE@@@Z`
- size: `272`
- prototype: `__int64 __fastcall(LPCWSTR StringSid, enum _LSA_USER_ACCOUNT_TYPE *)`
- caller_count: `5`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180064888`
- `0x18006494c`
- `0x180064a64`
- `0x180064c44`
- `0x1800650dc`

## callees

- `0x18003a5cc`
- `0x18003a8a8`
- `0x18003b944`
- `0x18003b964`
- `0x18003bf28`
- `0x18003c73c`
- `0x180064770`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800647f1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800647f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800647cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800647cf`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x18006482e`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x18006482e`

## string_xrefs

- `0x180064797`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x180064800`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x180064840`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetLsaUserAccountType(LPCWSTR StringSid, enum _LSA_USER_ACCOUNT_TYPE *a2)
{
  unsigned int LastError; // ebx
  const char *v5; // r9
  int v6; // eax
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HLOCAL hMem; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 )
  {
    LastError = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x100,
      (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
      (const char *)0x80004003LL,
      v7);
    return LastError;
  }
  hMem = 0;
  if ( !ConvertStringSidToSidW(StringSid, &hMem) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x102,
                  (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
                  v5);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
    return LastError;
  }
  *(_DWORD *)a2 = 0;
  v6 = LsaLookupUserAccountType(hMem, a2);
  if ( v6 < 0 )
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x105,
                  (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
                  (const char *)(unsigned int)v6,
                  v7);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
    return LastError;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
  return 0;
}

```

## disassembly

```asm
0x180064770  mov     [rsp+arg_0], rbx
0x180064775  mov     [rsp+arg_18], rsi
0x18006477a  push    rdi; int
0x18006477b  sub     rsp, 20h
0x18006477f  mov     rbx, rdx
0x180064782  mov     rsi, rcx
0x180064785  test    rdx, rdx
0x180064788  jnz     short loc_1800647AF
0x18006478a  mov     rcx, [rsp+28h]; this
0x18006478f  mov     ebx, 80004003h
0x180064794  mov     r9d, ebx; char *
0x180064797  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x18006479e  mov     edx, 100h; void *
0x1800647a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800647a8  mov     eax, ebx
0x1800647aa  jmp     loc_180064870
0x1800647af  mov     [rsp+28h+hMem], 0
0x1800647b8  mov     rdi, [rsp+28h+hMem]
0x1800647bd  test    rdi, rdi
0x1800647c0  jz      short loc_1800647E0
0x1800647c2  lea     rcx, [rsp+28h+arg_10]; this
0x1800647c7  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800647cc  mov     rcx, rdi; hMem
0x1800647cf  call    cs:__imp_LocalFree
0x1800647d5  lea     rcx, [rsp+28h+arg_10]; this
0x1800647da  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800647df  nop
0x1800647e0  mov     [rsp+28h+hMem], 0
0x1800647e9  lea     rdx, [rsp+28h+hMem]; Sid
0x1800647ee  mov     rcx, rsi; StringSid
0x1800647f1  call    cs:__imp_ConvertStringSidToSidW
0x1800647f7  test    eax, eax
0x1800647f9  jnz     short loc_180064820
0x1800647fb  mov     rcx, [rsp+28h]; this
0x180064800  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x180064807  mov     edx, 102h; void *
0x18006480c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180064811  mov     ebx, eax
0x180064813  lea     rcx, [rsp+28h+hMem]
0x180064818  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006481d  nop
0x18006481e  jmp     short loc_1800647A8
0x180064820  mov     dword ptr [rbx], 0
0x180064826  mov     rdx, rbx
0x180064829  mov     rcx, [rsp+28h+hMem]
0x18006482e  call    cs:__imp_LsaLookupUserAccountType
0x180064834  test    eax, eax
0x180064836  jns     short loc_180064863
0x180064838  mov     rcx, [rsp+28h]; this
0x18006483d  mov     r9d, eax; char *
0x180064840  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x180064847  mov     edx, 105h; void *
0x18006484c  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180064851  mov     ebx, eax
0x180064853  lea     rcx, [rsp+28h+hMem]
0x180064858  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006485d  nop
0x18006485e  jmp     loc_1800647A8
0x180064863  lea     rcx, [rsp+28h+hMem]
0x180064868  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006486d  nop
0x18006486e  xor     eax, eax
0x180064870  mov     rbx, [rsp+28h+arg_0]
0x180064875  mov     rsi, [rsp+28h+arg_18]
0x18006487a  add     rsp, 20h
0x18006487e  pop     rdi
0x18006487f  retn
```
