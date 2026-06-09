# CRupUser::CRupUser(void *,ushort *)

- ea: `0x180018808`
- end: `0x1800188b4`
- name: `??0CRupUser@@QEAA@PEAXPEAG@Z`
- size: `172`
- prototype: `CRupUser *__fastcall(_DWORD *phNewToken, HANDLE hExistingToken, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180019380`

## callees

- `0x180011478`
- `0x1800186f0`
- `0x180018808`
- `0x180018a04`
- `0x18001a3bc`
- `0x18001a46c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180018865`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180018865`

## pseudocode

```c
CRupUser *__fastcall CRupUser::CRupUser(_DWORD *phNewToken, HANDLE hExistingToken, unsigned __int16 *a3)
{
  void *v6; // rdx
  unsigned int v7; // r8d
  const char *v8; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  char v11; // [rsp+68h] [rbp+20h] BYREF

  *(_QWORD *)phNewToken = 0;
  *((_QWORD *)phNewToken + 1) = 0;
  phNewToken[4] = 1;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    phNewToken,
    0);
  if ( !DuplicateTokenEx(hExistingToken, 0x2000000u, 0, SecurityImpersonation, TokenImpersonation, (PHANDLE)phNewToken) )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, v6, v7, v8);
  wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v11,
    a3);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    phNewToken + 2,
    &v11);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v11);
  return (CRupUser *)phNewToken;
}

```

## disassembly

```asm
0x180018808  mov     [rsp+arg_8], rbx
0x18001880d  mov     [rsp+arg_10], rbp
0x180018812  mov     [rsp+arg_0], rcx
0x180018817  push    rsi
0x180018818  push    rdi
0x180018819  push    r14
0x18001881b  sub     rsp, 30h
0x18001881f  mov     rbp, r8
0x180018822  mov     rbx, rdx
0x180018825  mov     rdi, rcx
0x180018828  mov     qword ptr [rcx], 0
0x18001882f  mov     qword ptr [rcx+8], 0
0x180018837  mov     dword ptr [rcx+10h], 1
0x18001883e  xor     edx, edx
0x180018840  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180018845  mov     rsi, [rsp+48h]
0x18001884a  mov     [rsp+48h+phNewToken], rdi; phNewToken
0x18001884f  mov     r9d, 2; ImpersonationLevel
0x180018855  mov     [rsp+48h+TokenType], r9d; TokenType
0x18001885a  xor     r8d, r8d; lpTokenAttributes
0x18001885d  mov     edx, 2000000h; dwDesiredAccess
0x180018862  mov     rcx, rbx; hExistingToken
0x180018865  call    cs:__imp_DuplicateTokenEx
0x18001886b  test    eax, eax
0x18001886d  jnz     short loc_180018878
0x18001886f  mov     rcx, rsi; this
0x180018872  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180018878  mov     rdx, rbp
0x18001887b  lea     rcx, [rsp+48h+arg_18]
0x180018880  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180018885  lea     rdx, [rsp+48h+arg_18]
0x18001888a  lea     rcx, [rdi+8]
0x18001888e  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180018893  lea     rcx, [rsp+48h+arg_18]
0x180018898  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001889d  nop
0x18001889e  mov     rax, rdi
0x1800188a1  mov     rbx, [rsp+48h+arg_8]
0x1800188a6  mov     rbp, [rsp+48h+arg_10]
0x1800188ab  add     rsp, 30h
0x1800188af  pop     r14
0x1800188b1  pop     rdi
0x1800188b2  pop     rsi
0x1800188b3  retn
```
