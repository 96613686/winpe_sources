# _lambda_35ec1d53f6ae987b90537d50ba3aa7ca_::operator()

- ea: `0x1800276d8`
- end: `0x18002781d`
- name: `_lambda_35ec1d53f6ae987b90537d50ba3aa7ca_::operator()`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180038db0`

## callees

- `0x180006538`
- `0x180009510`
- `0x1800167f8`
- `0x1800276d8`
- `0x180027d20`
- `0x180028f9c`
- `0x180028ff0`
- `0x180029138`
- `0x180032fcc`

## import_xrefs

- `ncrypt!NCryptDeleteKey` at `0x180027794`
- `ncrypt!NCryptDeleteKey` at `0x180027794`

## string_xrefs

- `0x1800276f3`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x180027732`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x180027779`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x1800277a5`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x1800277e6`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`

## pseudocode

```c
__int64 __fastcall lambda_35ec1d53f6ae987b90537d50ba3aa7ca_::operator()(_QWORD **a1)
{
  _QWORD *v2; // rcx
  unsigned int v3; // ebx
  int v4; // eax
  int UserIdKeyCertificate; // eax
  SECURITY_STATUS v6; // eax
  int v7; // eax
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  struct _CERT_CONTEXT *v11; // [rsp+30h] [rbp+8h] BYREF
  NCRYPT_KEY_HANDLE hKey; // [rsp+38h] [rbp+10h] BYREF

  v2 = *a1;
  if ( *v2 )
  {
    hKey = 0;
    v4 = NgcOpenUserIdKey(*v2, &hKey);
    v3 = v4;
    if ( v4 >= 0 )
    {
      v11 = 0;
      wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(
        &v11,
        0);
      UserIdKeyCertificate = NgcGetUserIdKeyCertificate(**a1, &v11);
      if ( UserIdKeyCertificate < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x58B,
          (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
          (const char *)(unsigned int)UserIdKeyCertificate,
          v9);
      v6 = NCryptDeleteKey(hKey, 0);
      v3 = v6;
      if ( v6 >= 0 )
      {
        hKey = 0;
        if ( v11 )
        {
          v7 = DeleteUserIdKeyCertificates(v11);
          if ( v7 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x59A,
              (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
              (const char *)(unsigned int)v7,
              v9);
        }
        wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v11);
        v3 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x58F,
          (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
          (const char *)(unsigned int)v6,
          v9);
        wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v11);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x584,
        (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
        (const char *)(unsigned int)v4,
        v9);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hKey);
  }
  else
  {
    v3 = -2146893785;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x57F,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
      (const char *)0x80090027LL,
      v9);
  }
  return v3;
}

```

## disassembly

```asm
0x1800276d8  mov     [rsp+arg_10], rbx
0x1800276dd  push    rdi; int
0x1800276de  sub     rsp, 20h
0x1800276e2  mov     rdi, rcx
0x1800276e5  mov     rcx, [rcx]
0x1800276e8  cmp     qword ptr [rcx], 0
0x1800276ec  jnz     short loc_180027711
0x1800276ee  mov     rcx, [rsp+28h]; this
0x1800276f3  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x1800276fa  mov     ebx, 80090027h
0x1800276ff  mov     edx, 57Fh; void *
0x180027704  mov     r9d, ebx; char *
0x180027707  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002770c  jmp     loc_180027810
0x180027711  mov     [rsp+28h+hKey], 0
0x18002771a  lea     rdx, [rsp+28h+hKey]
0x18002771f  mov     rcx, [rcx]
0x180027722  call    NgcOpenUserIdKey
0x180027727  mov     ebx, eax
0x180027729  test    eax, eax
0x18002772b  jns     short loc_18002774B
0x18002772d  mov     rcx, [rsp+28h]; this
0x180027732  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180027739  mov     r9d, eax; char *
0x18002773c  mov     edx, 584h; void *
0x180027741  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027746  jmp     loc_180027806
0x18002774b  xor     edx, edx
0x18002774d  mov     [rsp+28h+arg_0], 0
0x180027756  lea     rcx, [rsp+28h+arg_0]
0x18002775b  call    ?reset@?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEBU_CERT_CONTEXT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(_CERT_CONTEXT const *)
0x180027760  mov     rcx, [rdi]
0x180027763  lea     rdx, [rsp+28h+arg_0]
0x180027768  mov     rcx, [rcx]
0x18002776b  call    NgcGetUserIdKeyCertificate
0x180027770  test    eax, eax
0x180027772  jns     short loc_18002778D
0x180027774  mov     rcx, [rsp+28h]; this
0x180027779  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180027780  mov     r9d, eax; char *
0x180027783  mov     edx, 58Bh; void *
0x180027788  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002778d  mov     rcx, [rsp+28h+hKey]; hKey
0x180027792  xor     edx, edx; dwFlags
0x180027794  call    cs:__imp_NCryptDeleteKey
0x18002779a  mov     ebx, eax
0x18002779c  test    eax, eax
0x18002779e  jns     short loc_1800277C5
0x1800277a0  mov     rcx, [rsp+28h]; this
0x1800277a5  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x1800277ac  mov     r9d, eax; char *
0x1800277af  mov     edx, 58Fh; void *
0x1800277b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800277b9  lea     rcx, [rsp+28h+arg_0]
0x1800277be  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x1800277c3  jmp     short loc_180027806
0x1800277c5  mov     rcx, [rsp+28h+arg_0]; struct _CERT_CONTEXT *
0x1800277ca  mov     [rsp+28h+hKey], 0
0x1800277d3  test    rcx, rcx
0x1800277d6  jz      short loc_1800277FA
0x1800277d8  call    ?DeleteUserIdKeyCertificates@@YAJPEBU_CERT_CONTEXT@@@Z; DeleteUserIdKeyCertificates(_CERT_CONTEXT const *)
0x1800277dd  test    eax, eax
0x1800277df  jns     short loc_1800277FA
0x1800277e1  mov     rcx, [rsp+28h]; this
0x1800277e6  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x1800277ed  mov     r9d, eax; char *
0x1800277f0  mov     edx, 59Ah; void *
0x1800277f5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800277fa  lea     rcx, [rsp+28h+arg_0]
0x1800277ff  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180027804  xor     ebx, ebx
0x180027806  lea     rcx, [rsp+28h+hKey]
0x18002780b  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180027810  mov     eax, ebx
0x180027812  mov     rbx, [rsp+28h+arg_10]
0x180027817  add     rsp, 20h
0x18002781b  pop     rdi
0x18002781c  retn
```
