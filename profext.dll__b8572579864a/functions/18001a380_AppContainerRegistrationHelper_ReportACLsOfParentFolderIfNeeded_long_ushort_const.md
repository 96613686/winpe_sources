# AppContainerRegistrationHelper::ReportACLsOfParentFolderIfNeeded(long,ushort const *)

- ea: `0x18001a380`
- end: `0x18001a49b`
- name: `?ReportACLsOfParentFolderIfNeeded@AppContainerRegistrationHelper@@CAJJPEBG@Z`
- size: `283`
- prototype: `__int64 __fastcall(int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180014750`
- `0x180014bd0`

## callees

- `0x1800012bc`
- `0x180004594`
- `0x18000c7d4`
- `0x18000ee08`
- `0x180013ab4`
- `0x18001a380`

## string_xrefs

- `0x18001a3ab`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`

## pseudocode

```c
__int64 __fastcall AppContainerRegistrationHelper::ReportACLsOfParentFolderIfNeeded(int a1, const unsigned __int16 *a2)
{
  unsigned int v3; // ebx
  int v4; // r8d
  int v5; // r9d
  int v6; // [rsp+20h] [rbp-29h]
  __int64 v7; // [rsp+50h] [rbp+7h] BYREF
  __int64 v8; // [rsp+58h] [rbp+Fh] BYREF
  __int64 v9; // [rsp+60h] [rbp+17h] BYREF
  const unsigned __int16 *v10; // [rsp+68h] [rbp+1Fh] BYREF
  LPWSTR *v11[6]; // [rsp+70h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]
  unsigned int v13; // [rsp+B0h] [rbp+67h] BYREF
  const unsigned __int16 *v14; // [rsp+B8h] [rbp+6Fh] BYREF
  int v15; // [rsp+C0h] [rbp+77h] BYREF
  __int64 v16; // [rsp+C8h] [rbp+7Fh] BYREF

  v14 = a2;
  if ( a1 != -2147024891 )
    return 0;
  if ( a2 )
  {
    v7 = 0;
    v11[0] = (LPWSTR *)&v7;
    v16 = 0;
    v11[1] = (LPWSTR *)&v16;
    v11[2] = (LPWSTR *)&v14;
    v3 = lambda_27334ae33285f87f8bd9f32967f76ee3_::operator()(v11);
    if ( (unsigned int)dword_180031038 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180031038, 0x400000000000LL) )
      {
        v9 = v16;
        v10 = v14;
        v8 = v7;
        v13 = v3;
        v15 = -2147024891;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
          v7,
          (unsigned int)&unk_18002B018,
          v4,
          v5,
          (__int64)&v15,
          (__int64)&v10,
          (__int64)&v9,
          (__int64)&v13,
          (__int64)&v8);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&v16);
    wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&v7);
  }
  else
  {
    v3 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8E2,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)0x80004003LL,
      v6);
  }
  return v3;
}

```

## disassembly

```asm
0x18001a380  mov     [rsp-8+arg_8], rdx
0x18001a385  push    rbp
0x18001a386  push    rbx
0x18001a387  lea     rbp, [rsp-4Fh]
0x18001a38c  sub     rsp, 98h
0x18001a393  cmp     ecx, 80070005h
0x18001a399  jz      short loc_18001A3A2
0x18001a39b  xor     eax, eax
0x18001a39d  jmp     loc_18001A490
0x18001a3a2  test    rdx, rdx
0x18001a3a5  jnz     short loc_18001A3C9
0x18001a3a7  mov     rcx, [rbp+5Fh]; this
0x18001a3ab  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001a3b2  mov     ebx, 80004003h
0x18001a3b7  mov     edx, 8E2h; void *
0x18001a3bc  mov     r9d, ebx; char *
0x18001a3bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a3c4  jmp     loc_18001A48E
0x18001a3c9  lea     rax, [rbp+57h+var_50]
0x18001a3cd  mov     [rbp+57h+var_50], 0
0x18001a3d5  mov     [rbp+57h+var_30], rax
0x18001a3d9  lea     rcx, [rbp+57h+var_30]
0x18001a3dd  lea     rax, [rbp+57h+arg_18]
0x18001a3e1  mov     [rbp+57h+arg_18], 0
0x18001a3e9  mov     [rbp+57h+var_28], rax
0x18001a3ed  lea     rax, [rbp+57h+arg_8]
0x18001a3f1  mov     [rbp+57h+var_20], rax
0x18001a3f5  call    _lambda_27334ae33285f87f8bd9f32967f76ee3___operator__
0x18001a3fa  mov     ecx, cs:dword_180031038
0x18001a400  mov     ebx, eax
0x18001a402  cmp     ecx, 5
0x18001a405  jbe     short loc_18001A47C
0x18001a407  mov     rdx, 400000000000h
0x18001a411  lea     rcx, dword_180031038
0x18001a418  call    _tlgKeywordOn
0x18001a41d  test    al, al
0x18001a41f  jz      short loc_18001A47C
0x18001a421  mov     rax, [rbp+57h+arg_18]
0x18001a425  lea     rdx, unk_18002B018
0x18001a42c  mov     rcx, [rbp+57h+var_50]
0x18001a430  mov     [rbp+57h+var_40], rax
0x18001a434  mov     rax, [rbp+57h+arg_8]
0x18001a438  mov     [rbp+57h+var_38], rax
0x18001a43c  lea     rax, [rbp+57h+var_48]
0x18001a440  mov     [rsp+0A0h+var_60], rax
0x18001a445  lea     rax, [rbp+57h+arg_0]
0x18001a449  mov     [rsp+0A0h+var_68], rax
0x18001a44e  lea     rax, [rbp+57h+var_40]
0x18001a452  mov     [rsp+0A0h+var_70], rax
0x18001a457  lea     rax, [rbp+57h+var_38]
0x18001a45b  mov     [rsp+0A0h+var_78], rax
0x18001a460  lea     rax, [rbp+57h+arg_10]
0x18001a464  mov     [rsp+0A0h+var_80], rax
0x18001a469  mov     [rbp+57h+var_48], rcx
0x18001a46d  mov     [rbp+57h+arg_0], ebx
0x18001a470  mov     [rbp+57h+arg_10], 80070005h
0x18001a477  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18001a47c  lea     rcx, [rbp+57h+arg_18]
0x18001a480  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18001a485  lea     rcx, [rbp+57h+var_50]
0x18001a489  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18001a48e  mov     eax, ebx
0x18001a490  add     rsp, 98h
0x18001a497  pop     rbx
0x18001a498  pop     rbp
0x18001a499  retn
```
