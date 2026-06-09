# CPluginCollectionSink::_CopySecurityDescriptor(void *)

- ea: `0x180068ab0`
- end: `0x180068d9b`
- name: `?_CopySecurityDescriptor@CPluginCollectionSink@@AEAAJPEAX@Z`
- size: `747`
- prototype: `int(CPluginCollectionSink *__hidden this, void *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180062b80`

## callees

- `0x18000a23c`
- `0x18000ee60`
- `0x18000f880`
- `0x180068ab0`
- `0x1800692f4`
- `0x1800ab770`
- `0x1800ac8b4`
- `0x1800ac99c`
- `0x1800bbf58`
- `0x1800d6f20`
- `0x1800e2374`
- `0x1800e95f0`
- `0x180123174`
- `0x1801249b0`
- `0x1801249ec`
- `0x1801299c7`
- `0x18014694c`
- `0x18014ac14`
- `0x180241010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068c8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068c94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068c8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068c94`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180068b0e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180068b0e`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180068c86`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180068cfe`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180068c86`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180068cfe`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180068bde`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180068bde`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CPluginCollectionSink::_CopySecurityDescriptor(CPluginCollectionSink *this, void *a2)
{
  __int64 v4; // rbx
  CTransaction *v5; // rbx
  unsigned __int64 SecurityDescriptorLength; // rsi
  void *v7; // rax
  PSECURITY_DESCRIPTOR v8; // rbx
  void **v10; // rdx
  PSECURITY_DESCRIPTOR v11; // rax
  void *v12; // rcx
  const WCHAR *ContainerUserSid; // rax
  PSID *v14; // rdx
  BOOL v15; // eax
  const char *v16; // r9
  __int64 v17; // r8
  int v18; // edx
  int v19; // r9d
  DWORD LastError; // ebx
  signed int v21; // eax
  void *v22; // rax
  const char *v23; // r9
  int v24; // [rsp+20h] [rbp-98h]
  int v25; // [rsp+20h] [rbp-98h]
  PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor; // [rsp+30h] [rbp-88h] BYREF
  void *v27; // [rsp+38h] [rbp-80h] BYREF
  CTransaction *v28; // [rsp+40h] [rbp-78h] BYREF
  PSID v29; // [rsp+48h] [rbp-70h] BYREF
  _BYTE pAbsoluteSecurityDescriptor[56]; // [rsp+50h] [rbp-68h] BYREF
  struct _ACL *v31; // [rsp+88h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  int v33; // [rsp+C0h] [rbp+8h] BYREF
  DWORD dwBufferLength; // [rsp+D0h] [rbp+18h] BYREF
  int v35; // [rsp+D8h] [rbp+20h] BYREF

  v28 = 0;
  v4 = *(_QWORD *)this;
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)this + 296LL) + 8LL))(*(_QWORD *)(*(_QWORD *)this + 296LL));
  v5 = *(CTransaction **)(v4 + 296);
  v28 = v5;
  pSelfRelativeSecurityDescriptor = 0;
  if ( CTransaction::GetContainerUserSid(v5) )
  {
    v27 = 0;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(&v27);
    ContainerUserSid = CTransaction::GetContainerUserSid(v5);
    v15 = ConvertStringSidToSidW(ContainerUserSid, v14);
    try
    {
      if ( !v15 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x83D,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx",
          v16);
      SecUtil::CSecurityDescriptor::CSecurityDescriptor(pAbsoluteSecurityDescriptor);
      SecUtil::CSecurityDescriptor::InitializeFromSelfRelative(pAbsoluteSecurityDescriptor, a2);
      v29 = v27;
      LOBYTE(v33) = 0;
      v35 = 2031745;
      SecUtil::CACL::AddAccessXXXAces(&v31, 1, v17, &v29, (__int64)&v35, &v33);
      SecUtil::CSecurityDescriptor::SetDacl((SecUtil::CSecurityDescriptor *)pAbsoluteSecurityDescriptor, v18, v31, v19);
      dwBufferLength = 0;
      MakeSelfRelativeSD(pAbsoluteSecurityDescriptor, 0, &dwBufferLength);
      LastError = GetLastError();
      v21 = GetLastError();
      if ( v21 > 0 )
        v21 = (unsigned __int16)v21 | 0x80070000;
      if ( LastError != 122 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x848,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx",
          (const char *)(unsigned int)v21,
          v25);
      v22 = operator new[](dwBufferLength, (const struct std::nothrow_t *)&std::nothrow);
      std::unique_ptr<unsigned char [0]>::reset<unsigned char *,0>(&pSelfRelativeSecurityDescriptor, v22);
      v8 = pSelfRelativeSecurityDescriptor;
      if ( !pSelfRelativeSecurityDescriptor )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x84B,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx",
          (const char *)0x8007000ELL,
          v25);
      if ( !MakeSelfRelativeSD(pAbsoluteSecurityDescriptor, pSelfRelativeSecurityDescriptor, &dwBufferLength) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x84E,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx",
          v23);
      SecUtil::CSecurityDescriptor::~CSecurityDescriptor((SecUtil::CSecurityDescriptor *)pAbsoluteSecurityDescriptor);
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v27);
    }
    catch ( ... )
    {
      indexer::result::details::result_from_caught_exception<1>(
        retaddr,
        2128,
        "onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx");
    }
  }
  else
  {
    SecurityDescriptorLength = GetSecurityDescriptorLength(a2);
    v7 = operator new[](SecurityDescriptorLength, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v7;
    if ( !v7 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x856,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx",
        (const char *)0x8007000ELL,
        v24);
      TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v28);
      return 2147942414LL;
    }
    memcpy_0(v7, a2, SecurityDescriptorLength);
  }
  v10 = (void **)((char *)this + 176);
  if ( (PSECURITY_DESCRIPTOR *)((char *)this + 176) != &pSelfRelativeSecurityDescriptor )
  {
    v11 = v8;
    v8 = 0;
    v12 = *v10;
    *v10 = v11;
    if ( v12 )
      operator delete(v12);
  }
  if ( v8 )
    operator delete(v8);
  TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v28);
  return 0;
}

```

## disassembly

```asm
0x180068ab0  mov     [rsp+arg_8], rbx
0x180068ab5  push    rsi
0x180068ab6  push    rdi
0x180068ab7  push    r14
0x180068ab9  sub     rsp, 0A0h
0x180068ac0  mov     rdi, rdx
0x180068ac3  mov     r14, rcx
0x180068ac6  mov     [rsp+0B8h+var_78], 0
0x180068acf  mov     rbx, [rcx]
0x180068ad2  mov     rcx, [rbx+128h]
0x180068ad9  mov     rax, [rcx]
0x180068adc  mov     rax, [rax+8]
0x180068ae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068ae5  mov     rbx, [rbx+128h]
0x180068aec  mov     [rsp+0B8h+var_78], rbx
0x180068af1  mov     [rsp+0B8h+pSelfRelativeSecurityDescriptor], 0
0x180068afa  mov     rcx, rbx; this
0x180068afd  call    ?GetContainerUserSid@CTransaction@@QEBAPEB_WXZ; CTransaction::GetContainerUserSid(void)
0x180068b02  test    rax, rax
0x180068b05  jnz     loc_180068BBD
0x180068b0b  mov     rcx, rdi; pSecurityDescriptor
0x180068b0e  call    cs:__imp_GetSecurityDescriptorLength
0x180068b14  mov     esi, eax
0x180068b16  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180068b1d  mov     ecx, eax; unsigned __int64
0x180068b1f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180068b24  mov     rbx, rax
0x180068b27  test    rax, rax
0x180068b2a  jnz     short loc_180068B5C
0x180068b2c  mov     rcx, [rsp+0B8h]; this
0x180068b34  mov     ebx, 8007000Eh
0x180068b39  mov     r9d, ebx; char *
0x180068b3c  lea     r8, aOnecoreuapBase_247; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180068b43  mov     edx, 856h; void *
0x180068b48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180068b4d  nop
0x180068b4e  lea     rcx, [rsp+0B8h+var_78]
0x180068b53  call    ??1?$TComPointer@UIGatherStoreManagerProvider@@@@QEAA@XZ; TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(void)
0x180068b58  mov     eax, ebx
0x180068b5a  jmp     short loc_180068BA9
0x180068b5c  mov     r8, rsi; Size
0x180068b5f  mov     rdx, rdi; Src
0x180068b62  mov     rcx, rax; void *
0x180068b65  call    memcpy_0
0x180068b6a  lea     rdx, [r14+0B0h]
0x180068b71  lea     rax, [rsp+0B8h+pSelfRelativeSecurityDescriptor]
0x180068b76  cmp     rdx, rax
0x180068b79  jz      short loc_180068B8F
0x180068b7b  mov     rax, rbx
0x180068b7e  xor     ebx, ebx
0x180068b80  mov     rcx, [rdx]; Block
0x180068b83  mov     [rdx], rax
0x180068b86  test    rcx, rcx
0x180068b89  jnz     loc_180068D90
0x180068b8f  test    rbx, rbx
0x180068b92  jz      short loc_180068B9D
0x180068b94  mov     rcx, rbx; Block
0x180068b97  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180068b9c  nop
0x180068b9d  lea     rcx, [rsp+0B8h+var_78]
0x180068ba2  call    ??1?$TComPointer@UIGatherStoreManagerProvider@@@@QEAA@XZ; TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(void)
0x180068ba7  xor     eax, eax
0x180068ba9  mov     rbx, [rsp+0B8h+arg_8]
0x180068bb1  add     rsp, 0A0h
0x180068bb8  pop     r14
0x180068bba  pop     rdi
0x180068bbb  pop     rsi
0x180068bbc  retn
0x180068bbd  mov     [rsp+0B8h+var_80], 0
0x180068bc6  lea     rcx, [rsp+0B8h+var_80]
0x180068bcb  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(void)
0x180068bd0  mov     rdx, rax
0x180068bd3  mov     rcx, rbx; this
0x180068bd6  call    ?GetContainerUserSid@CTransaction@@QEBAPEB_WXZ; CTransaction::GetContainerUserSid(void)
0x180068bdb  mov     rcx, rax; StringSid
0x180068bde  call    cs:__imp_ConvertStringSidToSidW
0x180068be4  mov     rcx, [rsp+0B8h]; this
0x180068bec  test    eax, eax
0x180068bee  jz      loc_180068D22
0x180068bf4  lea     rcx, [rsp+0B8h+pAbsoluteSecurityDescriptor]; pSecurityDescriptor
0x180068bf9  call    ??0CSecurityDescriptor@SecUtil@@QEAA@XZ; SecUtil::CSecurityDescriptor::CSecurityDescriptor(void)
0x180068bfe  nop
0x180068bff  mov     rdx, rdi; pSelfRelativeSecurityDescriptor
0x180068c02  lea     rcx, [rsp+0B8h+pAbsoluteSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x180068c07  call    ?InitializeFromSelfRelative@CSecurityDescriptor@SecUtil@@QEAAXPEAX@Z; SecUtil::CSecurityDescriptor::InitializeFromSelfRelative(void *)
0x180068c0c  mov     rax, [rsp+0B8h+var_80]
0x180068c11  mov     [rsp+0B8h+var_70], rax
0x180068c16  mov     byte ptr [rsp+0B8h+arg_0], 0
0x180068c1e  mov     [rsp+0B8h+arg_18], 1F0081h
0x180068c29  lea     rax, [rsp+0B8h+arg_0]
0x180068c31  mov     [rsp+0B8h+var_90], rax
0x180068c36  lea     rax, [rsp+0B8h+arg_18]
0x180068c3e  mov     qword ptr [rsp+0B8h+var_98], rax; int
0x180068c43  lea     r9, [rsp+0B8h+var_70]
0x180068c48  mov     edx, 1
0x180068c4d  lea     rcx, [rsp+0B8h+var_30]
0x180068c55  call    ?AddAccessXXXAces@CACL@SecUtil@@AEAAXW4EACCESSTYPE@12@KQEAPEAXQEBKQEBE@Z; SecUtil::CACL::AddAccessXXXAces(SecUtil::CACL::EACCESSTYPE,ulong,void * * const,ulong const * const,uchar const * const)
0x180068c5a  mov     r8, [rsp+0B8h+var_30]; struct _ACL *
0x180068c62  lea     rcx, [rsp+0B8h+pAbsoluteSecurityDescriptor]; this
0x180068c67  call    ?SetDacl@CSecurityDescriptor@SecUtil@@QEAAXHPEAU_ACL@@H@Z; SecUtil::CSecurityDescriptor::SetDacl(int,_ACL *,int)
0x180068c6c  mov     [rsp+0B8h+dwBufferLength], 0
0x180068c77  lea     r8, [rsp+0B8h+dwBufferLength]; lpdwBufferLength
0x180068c7f  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x180068c81  lea     rcx, [rsp+0B8h+pAbsoluteSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x180068c86  call    cs:__imp_MakeSelfRelativeSD
0x180068c8c  call    cs:__imp_GetLastError
0x180068c92  mov     ebx, eax
0x180068c94  call    cs:__imp_GetLastError
0x180068c9a  test    eax, eax
0x180068c9c  jle     short loc_180068CA6
0x180068c9e  movzx   eax, ax
0x180068ca1  or      eax, 80070000h
0x180068ca6  mov     rcx, [rsp+0B8h]; this
0x180068cae  cmp     ebx, 7Ah ; 'z'
0x180068cb1  jnz     loc_180068D4E
0x180068cb7  mov     ecx, [rsp+0B8h+dwBufferLength]; unsigned __int64
0x180068cbe  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180068cc5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180068cca  mov     rdx, rax
0x180068ccd  lea     rcx, [rsp+0B8h+pSelfRelativeSecurityDescriptor]
0x180068cd2  call    ??$reset@PEAE$0A@@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAAXPEAE@Z; std::unique_ptr<uchar [0]>::reset<uchar *,0>(uchar *)
0x180068cd7  mov     rbx, [rsp+0B8h+pSelfRelativeSecurityDescriptor]
0x180068cdc  test    rbx, rbx
0x180068cdf  setz    al
0x180068ce2  mov     rcx, [rsp+0B8h]; this
0x180068cea  test    al, al
0x180068cec  jnz     short loc_180068D62
0x180068cee  lea     r8, [rsp+0B8h+dwBufferLength]; lpdwBufferLength
0x180068cf6  mov     rdx, rbx; pSelfRelativeSecurityDescriptor
0x180068cf9  lea     rcx, [rsp+0B8h+pAbsoluteSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x180068cfe  call    cs:__imp_MakeSelfRelativeSD
0x180068d04  mov     rcx, [rsp+0B8h]; this
0x180068d0c  test    eax, eax
0x180068d0e  jnz     short loc_180068D33
0x180068d10  lea     r8, aOnecoreuapBase_247; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180068d17  mov     edx, 84Eh; void *
0x180068d1c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180068d22  lea     r8, aOnecoreuapBase_247; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180068d29  mov     edx, 83Dh; void *
0x180068d2e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180068d33  lea     rcx, [rsp+0B8h+pAbsoluteSecurityDescriptor]; this
0x180068d38  call    ??1CSecurityDescriptor@SecUtil@@QEAA@XZ; SecUtil::CSecurityDescriptor::~CSecurityDescriptor(void)
0x180068d3d  nop
0x180068d3e  lea     rcx, [rsp+0B8h+var_80]
0x180068d43  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180068d48  nop
0x180068d49  jmp     loc_180068B6A
0x180068d4e  mov     r9d, eax; char *
0x180068d51  lea     r8, aOnecoreuapBase_247; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180068d58  mov     edx, 848h; void *
0x180068d5d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180068d62  mov     r9d, 8007000Eh; char *
0x180068d68  lea     r8, aOnecoreuapBase_247; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180068d6f  mov     edx, 84Bh; void *
0x180068d74  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180068d7a  lea     rcx, [rsp+0B8h+pSelfRelativeSecurityDescriptor]
0x180068d7f  call    ??1?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@std@@@std@@QEAA@XZ; std::unique_ptr<gsl::byte [0]>::~unique_ptr<gsl::byte [0]>(void)
0x180068d84  mov     ebx, [rsp+0B8h+arg_0]
0x180068d8b  jmp     loc_180068B4E
0x180068d90  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180068d95  jmp     loc_180068B8F
```
