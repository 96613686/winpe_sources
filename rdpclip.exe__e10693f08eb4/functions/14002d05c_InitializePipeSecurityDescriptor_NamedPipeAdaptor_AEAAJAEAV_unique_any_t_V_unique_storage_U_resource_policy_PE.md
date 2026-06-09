# ?InitializePipeSecurityDescriptor@NamedPipeAdaptor@@AEAAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z

- ea: `0x14002d05c`
- end: `0x14002d2fc`
- name: `?InitializePipeSecurityDescriptor@NamedPipeAdaptor@@AEAAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `672`
- prototype: `__int64 __fastcall(NamedPipeAdaptor *this, PSECURITY_DESCRIPTOR *SecurityDescriptor)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14002cef0`

## callees

- `0x140001efc`
- `0x140006058`
- `0x140006344`
- `0x140008168`
- `0x140008188`
- `0x14002b9b8`
- `0x14002bbb8`
- `0x14002c054`
- `0x14002cc10`
- `0x14002d05c`
- `0x14002d388`
- `0x14003292c`
- `0x14006b010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x14002d22a`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x14002d22a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14002d251`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14002d251`

## string_xrefs

- `0x14002d090`: `clientcore\termsrv\rdpplatform\common\namedpipe\namedpipeadaptor.cpp`
- `0x14002d0c9`: `clientcore\termsrv\rdpplatform\common\namedpipe\namedpipeadaptor.cpp`
- `0x14002d116`: `clientcore\termsrv\rdpplatform\common\namedpipe\namedpipeadaptor.cpp`
- `0x14002d17d`: `clientcore\termsrv\rdpplatform\common\namedpipe\namedpipeadaptor.cpp`
- `0x14002d25f`: `clientcore\termsrv\rdpplatform\common\namedpipe\namedpipeadaptor.cpp`

## pseudocode

```c
__int64 __fastcall NamedPipeAdaptor::InitializePipeSecurityDescriptor(
        NamedPipeAdaptor *this,
        PSECURITY_DESCRIPTOR *SecurityDescriptor)
{
  void *v4; // rcx
  unsigned int LastError; // ebx
  int LogonSid; // eax
  __int64 v7; // rcx
  int AceStringForSid; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  PSECURITY_DESCRIPTOR v15; // rbx
  const WCHAR *v16; // rbx
  const char *v17; // r9
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  int v22; // [rsp+20h] [rbp-40h]
  LPCWSTR StringSecurityDescriptor; // [rsp+40h] [rbp-20h] BYREF
  PSECURITY_DESCRIPTOR ObjectDescriptor; // [rsp+48h] [rbp-18h] BYREF
  const WCHAR *v25; // [rsp+50h] [rbp-10h] BYREF
  __int64 v26; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  void *v28; // [rsp+90h] [rbp+30h] BYREF
  __int64 v29; // [rsp+98h] [rbp+38h] BYREF

  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &StringSecurityDescriptor,
    L"D:",
    -1);
  if ( !StringSecurityDescriptor )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x250,
      (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\namedpipe\\namedpipeadaptor.cpp",
      (const char *)0x8007000ELL,
      v22);
    goto LABEL_32;
  }
  v28 = 0;
  LogonSid = GetLogonSid(v4, &v28);
  LastError = LogonSid;
  if ( LogonSid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x256,
      (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\namedpipe\\namedpipeadaptor.cpp",
      (const char *)(unsigned int)LogonSid,
      v22);
LABEL_5:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
    goto LABEL_32;
  }
  v29 = 0;
  AceStringForSid = NamedPipeAdaptor::MakeAceStringForSid(v7, L"(A;;FRFWGA;;;%s)", v28, &v29);
  LastError = AceStringForSid;
  if ( AceStringForSid < 0 )
  {
    v9 = 602;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\namedpipe\\namedpipeadaptor.cpp",
      (const char *)(unsigned int)AceStringForSid,
      v22);
LABEL_9:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v29);
    goto LABEL_5;
  }
  AceStringForSid = wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                      &StringSecurityDescriptor,
                      &v29);
  LastError = AceStringForSid;
  if ( AceStringForSid < 0 )
  {
    v9 = 603;
    goto LABEL_8;
  }
  v11 = *((_QWORD *)this + 19);
  if ( v11 )
  {
    ObjectDescriptor = 0;
    v12 = NamedPipeAdaptor::MakeAceStringForSid(v10, L"(A;;FRFWGA;;;%s)", v11, &ObjectDescriptor);
    LastError = v12;
    if ( v12 < 0 )
    {
      v13 = 609;
LABEL_15:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\namedpipe\\namedpipeadaptor.cpp",
        (const char *)(unsigned int)v12,
        v22);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ObjectDescriptor);
      goto LABEL_9;
    }
    v12 = wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &StringSecurityDescriptor,
            &ObjectDescriptor);
    LastError = v12;
    if ( v12 < 0 )
    {
      v13 = 610;
      goto LABEL_15;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ObjectDescriptor);
  }
  v14 = *((_QWORD *)this + 20);
  if ( v14 )
  {
    ObjectDescriptor = 0;
    v12 = NamedPipeAdaptor::MakeAceStringForSid(v10, L"S:(ML;;NW;;;%ws)", v14, &ObjectDescriptor);
    LastError = v12;
    if ( v12 < 0 )
    {
      v13 = 617;
      goto LABEL_15;
    }
    v12 = wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &StringSecurityDescriptor,
            &ObjectDescriptor);
    LastError = v12;
    if ( v12 < 0 )
    {
      v13 = 618;
      goto LABEL_15;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ObjectDescriptor);
  }
  v15 = *SecurityDescriptor;
  if ( *SecurityDescriptor )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v25);
    ObjectDescriptor = v15;
    DestroyPrivateObjectSecurity(&ObjectDescriptor);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v25);
  }
  v16 = StringSecurityDescriptor;
  *SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v16, 1u, SecurityDescriptor, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x26E,
                  (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\namedpipe\\namedpipeadaptor.cpp",
                  v17);
    goto LABEL_9;
  }
  if ( (unsigned int)dword_140088090 > 5 )
  {
    v25 = v16;
    ObjectDescriptor = (PSECURITY_DESCRIPTOR)NamedPipeAdaptor::GetModeName(this);
    v26 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 6) + 48LL))((char *)this + 48);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v18,
      (unsigned int)byte_14007FC11,
      v19,
      v20,
      (__int64)&v26,
      (__int64)&ObjectDescriptor,
      (__int64)&v25);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v29);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
  LastError = 0;
LABEL_32:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSecurityDescriptor);
  return LastError;
}

```

## disassembly

```asm
0x14002d05c  mov     [rsp-18h+arg_0], rbx
0x14002d061  push    rbp
0x14002d062  push    rsi
0x14002d063  push    rdi
0x14002d064  mov     rbp, rsp
0x14002d067  sub     rsp, 60h
0x14002d06b  mov     rsi, rdx
0x14002d06e  mov     rdi, rcx
0x14002d071  lea     rdx, aD; "D:"
0x14002d078  or      r8, 0FFFFFFFFFFFFFFFFh
0x14002d07c  lea     rcx, [rbp+StringSecurityDescriptor]
0x14002d080  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x14002d085  cmp     [rbp+StringSecurityDescriptor], 0
0x14002d08a  jnz     short loc_14002D0AE
0x14002d08c  mov     rcx, [rbp+18h]; this
0x14002d090  lea     r8, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14002d097  mov     ebx, 8007000Eh
0x14002d09c  mov     edx, 250h; void *
0x14002d0a1  mov     r9d, ebx; char *
0x14002d0a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002d0a9  jmp     loc_14002D2E1
0x14002d0ae  lea     rdx, [rbp+arg_10]; void **
0x14002d0b2  mov     [rbp+arg_10], 0
0x14002d0ba  call    ?GetLogonSid@@YAJPEAXPEAPEAX@Z; GetLogonSid(void *,void * *)
0x14002d0bf  mov     ebx, eax
0x14002d0c1  test    eax, eax
0x14002d0c3  jns     short loc_14002D0EB
0x14002d0c5  mov     rcx, [rbp+18h]; this
0x14002d0c9  lea     r8, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14002d0d0  mov     r9d, eax; char *
0x14002d0d3  mov     edx, 256h; void *
0x14002d0d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002d0dd  lea     rcx, [rbp+arg_10]
0x14002d0e1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14002d0e6  jmp     loc_14002D2E1
0x14002d0eb  mov     r8, [rbp+arg_10]
0x14002d0ef  lea     r9, [rbp+arg_18]
0x14002d0f3  lea     rdx, aAFrfwgaS; "(A;;FRFWGA;;;%s)"
0x14002d0fa  mov     [rbp+arg_18], 0
0x14002d102  call    ?MakeAceStringForSid@NamedPipeAdaptor@@AEAAJQEAGQEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; NamedPipeAdaptor::MakeAceStringForSid(ushort * const,void * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x14002d107  mov     ebx, eax
0x14002d109  test    eax, eax
0x14002d10b  jns     short loc_14002D130
0x14002d10d  mov     edx, 25Ah; void *
0x14002d112  mov     rcx, [rbp+18h]; this
0x14002d116  lea     r8, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14002d11d  mov     r9d, eax; char *
0x14002d120  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002d125  lea     rcx, [rbp+arg_18]
0x14002d129  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14002d12e  jmp     short loc_14002D0DD
0x14002d130  lea     rdx, [rbp+arg_18]
0x14002d134  lea     rcx, [rbp+StringSecurityDescriptor]
0x14002d138  call    ??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V12@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV10@@Z; wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &)
0x14002d13d  mov     ebx, eax
0x14002d13f  test    eax, eax
0x14002d141  jns     short loc_14002D14A
0x14002d143  mov     edx, 25Bh
0x14002d148  jmp     short loc_14002D112
0x14002d14a  mov     r8, [rdi+98h]
0x14002d151  test    r8, r8
0x14002d154  jz      short loc_14002D1BA
0x14002d156  lea     r9, [rbp+ObjectDescriptor]
0x14002d15a  mov     [rbp+ObjectDescriptor], 0
0x14002d162  lea     rdx, aAFrfwgaS; "(A;;FRFWGA;;;%s)"
0x14002d169  call    ?MakeAceStringForSid@NamedPipeAdaptor@@AEAAJQEAGQEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; NamedPipeAdaptor::MakeAceStringForSid(ushort * const,void * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x14002d16e  mov     ebx, eax
0x14002d170  test    eax, eax
0x14002d172  jns     short loc_14002D197
0x14002d174  mov     edx, 261h; void *
0x14002d179  mov     rcx, [rbp+18h]; this
0x14002d17d  lea     r8, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14002d184  mov     r9d, eax; char *
0x14002d187  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002d18c  lea     rcx, [rbp+ObjectDescriptor]
0x14002d190  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14002d195  jmp     short loc_14002D125
0x14002d197  lea     rdx, [rbp+ObjectDescriptor]
0x14002d19b  lea     rcx, [rbp+StringSecurityDescriptor]
0x14002d19f  call    ??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V12@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV10@@Z; wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &)
0x14002d1a4  mov     ebx, eax
0x14002d1a6  test    eax, eax
0x14002d1a8  jns     short loc_14002D1B1
0x14002d1aa  mov     edx, 262h
0x14002d1af  jmp     short loc_14002D179
0x14002d1b1  lea     rcx, [rbp+ObjectDescriptor]
0x14002d1b5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14002d1ba  mov     r8, [rdi+0A0h]
0x14002d1c1  test    r8, r8
0x14002d1c4  jz      short loc_14002D211
0x14002d1c6  lea     r9, [rbp+ObjectDescriptor]
0x14002d1ca  mov     [rbp+ObjectDescriptor], 0
0x14002d1d2  lea     rdx, aSMlNwWs; "S:(ML;;NW;;;%ws)"
0x14002d1d9  call    ?MakeAceStringForSid@NamedPipeAdaptor@@AEAAJQEAGQEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; NamedPipeAdaptor::MakeAceStringForSid(ushort * const,void * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x14002d1de  mov     ebx, eax
0x14002d1e0  test    eax, eax
0x14002d1e2  jns     short loc_14002D1EB
0x14002d1e4  mov     edx, 269h
0x14002d1e9  jmp     short loc_14002D179
0x14002d1eb  lea     rdx, [rbp+ObjectDescriptor]
0x14002d1ef  lea     rcx, [rbp+StringSecurityDescriptor]
0x14002d1f3  call    ??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V12@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV10@@Z; wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &)
0x14002d1f8  mov     ebx, eax
0x14002d1fa  test    eax, eax
0x14002d1fc  jns     short loc_14002D208
0x14002d1fe  mov     edx, 26Ah
0x14002d203  jmp     loc_14002D179
0x14002d208  lea     rcx, [rbp+ObjectDescriptor]
0x14002d20c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14002d211  mov     rbx, [rsi]
0x14002d214  test    rbx, rbx
0x14002d217  jz      short loc_14002D239
0x14002d219  lea     rcx, [rbp+var_10]; this
0x14002d21d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14002d222  lea     rcx, [rbp+ObjectDescriptor]; ObjectDescriptor
0x14002d226  mov     [rbp+ObjectDescriptor], rbx
0x14002d22a  call    cs:__imp_DestroyPrivateObjectSecurity
0x14002d230  lea     rcx, [rbp+var_10]; this
0x14002d234  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14002d239  mov     rbx, [rbp+StringSecurityDescriptor]
0x14002d23d  xor     r9d, r9d; SecurityDescriptorSize
0x14002d240  mov     r8, rsi; SecurityDescriptor
0x14002d243  mov     qword ptr [rsi], 0
0x14002d24a  mov     rcx, rbx; StringSecurityDescriptor
0x14002d24d  lea     edx, [r9+1]; StringSDRevision
0x14002d251  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x14002d257  test    eax, eax
0x14002d259  jnz     short loc_14002D277
0x14002d25b  mov     rcx, [rbp+18h]; this
0x14002d25f  lea     r8, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14002d266  mov     edx, 26Eh; void *
0x14002d26b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14002d270  mov     ebx, eax
0x14002d272  jmp     loc_14002D125
0x14002d277  mov     eax, cs:dword_140088090
0x14002d27d  cmp     eax, 5
0x14002d280  jbe     short loc_14002D2CD
0x14002d282  mov     rcx, rdi; this
0x14002d285  mov     [rbp+var_10], rbx
0x14002d289  call    ?GetModeName@NamedPipeAdaptor@@AEBAPEBGXZ; NamedPipeAdaptor::GetModeName(void)
0x14002d28e  mov     [rbp+ObjectDescriptor], rax
0x14002d292  lea     rcx, [rdi+30h]
0x14002d296  mov     rax, [rcx]
0x14002d299  mov     rax, [rax+30h]
0x14002d29d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d2a2  mov     [rbp+var_8], rax
0x14002d2a6  lea     rdx, byte_14007FC11
0x14002d2ad  lea     rax, [rbp+var_10]
0x14002d2b1  mov     [rsp+60h+var_30], rax
0x14002d2b6  lea     rax, [rbp+ObjectDescriptor]
0x14002d2ba  mov     [rsp+60h+var_38], rax
0x14002d2bf  lea     rax, [rbp+var_8]
0x14002d2c3  mov     [rsp+60h+var_40], rax
0x14002d2c8  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14002d2cd  lea     rcx, [rbp+arg_18]
0x14002d2d1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14002d2d6  lea     rcx, [rbp+arg_10]
0x14002d2da  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14002d2df  xor     ebx, ebx
0x14002d2e1  lea     rcx, [rbp+StringSecurityDescriptor]
0x14002d2e5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14002d2ea  mov     eax, ebx
0x14002d2ec  mov     rbx, [rsp+60h+arg_0]
0x14002d2f4  add     rsp, 60h
0x14002d2f8  pop     rdi
0x14002d2f9  pop     rsi
0x14002d2fa  pop     rbp
0x14002d2fb  retn
```
