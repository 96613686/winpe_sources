# FSOp::CreateDirectoryWithSecurity(wchar_t const *,void *,wchar_t const *)

- ea: `0x1800abe78`
- end: `0x1800ac1c4`
- name: `?CreateDirectoryWithSecurity@FSOp@@YAXPEB_WPEAX0@Z`
- size: `844`
- prototype: `void __fastcall(wchar_t *this, const wchar_t *, void *, const wchar_t *)`
- caller_count: `10`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800ab934`
- `0x1800abce0`
- `0x1800ccddc`
- `0x1800e1880`
- `0x1800e4520`
- `0x180165e20`
- `0x180166430`
- `0x18017d66c`
- `0x180198860`
- `0x18019ace0`

## callees

- `0x1800ab770`
- `0x1800abe78`
- `0x1800ac8b4`
- `0x1800ac938`
- `0x1800ac99c`
- `0x1800ac9fc`
- `0x1800ad360`
- `0x1800d6f20`
- `0x1800e95f0`
- `0x1800f6254`
- `0x1801249b0`
- `0x180124d00`
- `0x18013dd98`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800abf1b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800abf8f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800abf1b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800abf8f`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1800abeee`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1800abf6d`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1800abeee`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1800abf6d`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1800abed1`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1800abf50`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1800abed1`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1800abf50`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800ac0a3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800ac0a3`

## string_xrefs

- `0x1800ac0b1`: `onecoreuap\base\appmodel\search\common\pkmutill\ssfsutil.cxx`
- `0x1800ac16b`: `onecoreuap\base\appmodel\search\common\pkmutill\ssfsutil.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall FSOp::CreateDirectoryWithSecurity(wchar_t *this, const wchar_t *a2, const WCHAR *a3, const wchar_t *a4)
{
  void *v7; // rbx
  DWORD SidLengthRequired; // eax
  void *v9; // r14
  __int64 v10; // rdi
  DWORD v11; // ebx
  void *v12; // rdi
  DWORD v13; // eax
  void *v14; // r14
  DWORD v15; // edi
  __int64 v16; // r8
  struct _SECURITY_ATTRIBUTES *v17; // r9
  __int64 v18; // r8
  __int64 v19; // r8
  __int64 v20; // r8
  int v21; // edx
  int v22; // r9d
  __int64 v23; // r8
  const char *v24; // r9
  __int64 v25; // r8
  void *v26; // rsi
  unsigned int v27; // [rsp+20h] [rbp-89h]
  int v28; // [rsp+30h] [rbp-79h] BYREF
  PSID Sid; // [rsp+38h] [rbp-71h] BYREF
  void *Block; // [rsp+40h] [rbp-69h] BYREF
  PSID v31; // [rsp+48h] [rbp-61h] BYREF
  unsigned int v32[4]; // [rsp+50h] [rbp-59h] BYREF
  __int64 v33; // [rsp+60h] [rbp-49h]
  void *v34; // [rsp+68h] [rbp-41h]
  void *v35; // [rsp+70h] [rbp-39h]
  _BYTE pSecurityDescriptor[128]; // [rsp+80h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]
  __int64 v38; // [rsp+118h] [rbp+6Fh] BYREF
  unsigned int v39; // [rsp+128h] [rbp+7Fh] BYREF

  v39 = 0;
  *(_OWORD *)v32 = 0;
  v32[0] = 24;
  v33 = 0;
  SecUtil::CSecurityDescriptor::CSecurityDescriptor(pSecurityDescriptor);
  v7 = 0;
  v34 = 0;
  v38 = 0;
  SidLengthRequired = GetSidLengthRequired(2u);
  v9 = operator new[](SidLengthRequired);
  if ( InitializeSid(v9, (PSID_IDENTIFIER_AUTHORITY)SecUtil::CSID_EveryoneAccount::s_sia.SubAuthority, 2u) )
  {
    v10 = 0;
    do
    {
      v11 = *(&SecUtil::CSID_AdministratorsGroup::s_rgSubAuth + v10);
      *GetSidSubAuthority(v9, v10) = v11;
      v10 = (unsigned int)(v10 + 1);
    }
    while ( (unsigned int)v10 < 2 );
    v38 = 0;
    v7 = v9;
    v34 = v9;
    TPointer<unsigned char>::~TPointer<unsigned char>(&v38);
  }
  else
  {
    operator delete(v9);
  }
  v12 = 0;
  v35 = 0;
  v38 = 0;
  v13 = GetSidLengthRequired(1u);
  v14 = operator new[](v13);
  if ( InitializeSid(v14, (PSID_IDENTIFIER_AUTHORITY)SecUtil::CSID_NetworkServiceAccount::s_sia.SubAuthority, 1u) )
  {
    v15 = SecUtil::CSID_SystemAccount::s_rgSubAuth;
    *GetSidSubAuthority(v14, 0) = v15;
    v38 = 0;
    v12 = v14;
    v35 = v14;
    TPointer<unsigned char>::~TPointer<unsigned char>(&v38);
  }
  else
  {
    operator delete(v14);
  }
  Block = 0;
  SecUtil::CACL::Reset((SecUtil::CACL *)&Block);
  if ( a2 )
  {
    *(_QWORD *)&v32[2] = a2;
    v26 = Block;
  }
  else
  {
    LOBYTE(v38) = 9;
    v28 = 0x10000000;
    Sid = v7;
    ((void (__fastcall *)(void **, __int64, __int64, PSID *, int *, __int64 *))SecUtil::CACL::AddAccessXXXAces)(
      &Block,
      1,
      v16,
      &Sid,
      &v28,
      &v38);
    LOBYTE(v38) = 2;
    v28 = 2032127;
    Sid = v7;
    ((void (__fastcall *)(void **, __int64, __int64, PSID *, int *, __int64 *))SecUtil::CACL::AddAccessXXXAces)(
      &Block,
      1,
      v18,
      &Sid,
      &v28,
      &v38);
    LOBYTE(v38) = 9;
    v28 = 0x10000000;
    Sid = v12;
    ((void (__fastcall *)(void **, __int64, __int64, PSID *, int *, __int64 *))SecUtil::CACL::AddAccessXXXAces)(
      &Block,
      1,
      v19,
      &Sid,
      &v28,
      &v38);
    LOBYTE(v38) = 2;
    v28 = 2032127;
    Sid = v12;
    ((void (__fastcall *)(void **, __int64, __int64, PSID *, int *, __int64 *))SecUtil::CACL::AddAccessXXXAces)(
      &Block,
      1,
      v20,
      &Sid,
      &v28,
      &v38);
    if ( a3 )
    {
      Sid = 0;
      if ( !ConvertStringSidToSidW(a3, &Sid) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x49,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutill\\ssfsutil.cxx",
          v24);
      LOBYTE(v38) = 9;
      v28 = 0x10000000;
      v31 = Sid;
      ((void (__fastcall *)(void **, __int64, __int64, PSID *, int *, __int64 *))SecUtil::CACL::AddAccessXXXAces)(
        &Block,
        1,
        v23,
        &v31,
        &v28,
        &v38);
      LOBYTE(v38) = 2;
      v28 = 2032127;
      v31 = Sid;
      ((void (__fastcall *)(void **, __int64, __int64, PSID *, int *, __int64 *))SecUtil::CACL::AddAccessXXXAces)(
        &Block,
        1,
        v25,
        &v31,
        &v28,
        &v38);
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
    }
    v26 = Block;
    SecUtil::CSecurityDescriptor::SetDacl(
      (SecUtil::CSecurityDescriptor *)pSecurityDescriptor,
      v21,
      (struct _ACL *)Block,
      v22);
    *(_QWORD *)&v32[2] = pSecurityDescriptor;
  }
  if ( !(unsigned int)FSOp::MakeDirectory(this, (const wchar_t *)&v39, v32, v17) )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x5B,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutill\\ssfsutil.cxx",
      (const char *)v39,
      v27);
  operator delete(v26);
  if ( v12 )
    operator delete(v12);
  if ( v7 )
    operator delete(v7);
  SecUtil::CSecurityDescriptor::~CSecurityDescriptor((SecUtil::CSecurityDescriptor *)pSecurityDescriptor);
}

```

## disassembly

```asm
0x1800abe78  mov     [rsp-8+arg_0], rbx
0x1800abe7d  push    rbp
0x1800abe7e  push    rsi
0x1800abe7f  push    rdi
0x1800abe80  push    r12
0x1800abe82  push    r13
0x1800abe84  push    r14
0x1800abe86  push    r15
0x1800abe88  lea     rbp, [rsp-27h]
0x1800abe8d  sub     rsp, 0D0h
0x1800abe94  mov     r12, r8
0x1800abe97  mov     r15, rdx
0x1800abe9a  mov     r13, rcx
0x1800abe9d  mov     [rbp+57h+arg_18], 0
0x1800abea4  xorps   xmm0, xmm0
0x1800abea7  xor     eax, eax
0x1800abea9  movups  xmmword ptr [rbp+57h+var_B0], xmm0
0x1800abead  mov     [rbp+57h+var_A0], rax
0x1800abeb1  mov     [rbp+57h+var_B0], 18h
0x1800abeb8  mov     dword ptr [rbp+57h+var_A0], eax
0x1800abebb  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x1800abebf  call    ??0CSecurityDescriptor@SecUtil@@QEAA@XZ; SecUtil::CSecurityDescriptor::CSecurityDescriptor(void)
0x1800abec4  nop
0x1800abec5  xor     ebx, ebx
0x1800abec7  mov     [rbp+57h+var_98], rbx
0x1800abecb  mov     [rbp+57h+arg_8], rbx
0x1800abecf  mov     cl, 2; nSubAuthorityCount
0x1800abed1  call    cs:__imp_GetSidLengthRequired
0x1800abed7  mov     ecx, eax; unsigned __int64
0x1800abed9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800abede  mov     r14, rax
0x1800abee1  mov     r8b, 2; nSubAuthorityCount
0x1800abee4  lea     rdx, ?s_sia@CSID_EveryoneAccount@SecUtil@@0U_SID_IDENTIFIER_AUTHORITY@@A.SubAuthority; pIdentifierAuthority
0x1800abeeb  mov     rcx, rax; Sid
0x1800abeee  call    cs:__imp_InitializeSid
0x1800abef4  test    eax, eax
0x1800abef6  jnz     short loc_1800ABF07
0x1800abef8  lea     esi, [rbx+1]
0x1800abefb  mov     edx, esi
0x1800abefd  mov     rcx, r14; Block
0x1800abf00  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800abf05  jmp     short loc_1800ABF43
0x1800abf07  xor     edi, edi
0x1800abf09  lea     esi, [rdi+1]
0x1800abf0c  lea     rbx, ?s_rgSubAuth@CSID_AdministratorsGroup@SecUtil@@0PAKA; ulong near * SecUtil::CSID_AdministratorsGroup::s_rgSubAuth
0x1800abf13  mov     ebx, [rbx+rdi*4]
0x1800abf16  mov     edx, edi; nSubAuthority
0x1800abf18  mov     rcx, r14; pSid
0x1800abf1b  call    cs:__imp_GetSidSubAuthority
0x1800abf21  mov     [rax], ebx
0x1800abf23  add     edi, esi
0x1800abf25  cmp     edi, 2
0x1800abf28  jb      short loc_1800ABF0C
0x1800abf2a  mov     [rbp+57h+arg_8], 0
0x1800abf32  mov     rbx, r14
0x1800abf35  mov     [rbp+57h+var_98], rbx
0x1800abf39  lea     rcx, [rbp+57h+arg_8]
0x1800abf3d  call    ??1?$TPointer@E@@QEAA@XZ; TPointer<uchar>::~TPointer<uchar>(void)
0x1800abf42  nop
0x1800abf43  xor     edi, edi
0x1800abf45  mov     [rbp+57h+var_90], rdi
0x1800abf49  mov     [rbp+57h+arg_8], rdi
0x1800abf4d  mov     cl, sil; nSubAuthorityCount
0x1800abf50  call    cs:__imp_GetSidLengthRequired
0x1800abf56  mov     ecx, eax; unsigned __int64
0x1800abf58  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800abf5d  mov     r14, rax
0x1800abf60  mov     r8b, sil; nSubAuthorityCount
0x1800abf63  lea     rdx, ?s_sia@CSID_NetworkServiceAccount@SecUtil@@0U_SID_IDENTIFIER_AUTHORITY@@A.SubAuthority; pIdentifierAuthority
0x1800abf6a  mov     rcx, rax; Sid
0x1800abf6d  call    cs:__imp_InitializeSid
0x1800abf73  test    eax, eax
0x1800abf75  jnz     short loc_1800ABF84
0x1800abf77  mov     rdx, rsi
0x1800abf7a  mov     rcx, r14; Block
0x1800abf7d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800abf82  jmp     short loc_1800ABFB0
0x1800abf84  mov     edi, cs:?s_rgSubAuth@CSID_SystemAccount@SecUtil@@0PAKA; ulong near * SecUtil::CSID_SystemAccount::s_rgSubAuth
0x1800abf8a  xor     edx, edx; nSubAuthority
0x1800abf8c  mov     rcx, r14; pSid
0x1800abf8f  call    cs:__imp_GetSidSubAuthority
0x1800abf95  mov     [rax], edi
0x1800abf97  mov     [rbp+57h+arg_8], 0
0x1800abf9f  mov     rdi, r14
0x1800abfa2  mov     [rbp+57h+var_90], r14
0x1800abfa6  lea     rcx, [rbp+57h+arg_8]
0x1800abfaa  call    ??1?$TPointer@E@@QEAA@XZ; TPointer<uchar>::~TPointer<uchar>(void)
0x1800abfaf  nop
0x1800abfb0  mov     [rbp+57h+Block], 0
0x1800abfb8  lea     rcx, [rbp+57h+Block]; this
0x1800abfbc  call    ?Reset@CACL@SecUtil@@QEAAXXZ; SecUtil::CACL::Reset(void)
0x1800abfc1  nop
0x1800abfc2  test    r15, r15
0x1800abfc5  jnz     loc_1800AC147
0x1800abfcb  mov     byte ptr [rbp+57h+arg_8], 9
0x1800abfcf  mov     r14d, 10000000h
0x1800abfd5  mov     [rbp+57h+var_D0], r14d
0x1800abfd9  mov     [rbp+57h+Sid], rbx
0x1800abfdd  lea     rax, [rbp+57h+arg_8]
0x1800abfe1  mov     [rsp+100h+var_D8], rax
0x1800abfe6  lea     rax, [rbp+57h+var_D0]
0x1800abfea  mov     [rsp+100h+var_E0], rax
0x1800abfef  lea     r9, [rbp+57h+Sid]
0x1800abff3  mov     edx, esi
0x1800abff5  lea     rcx, [rbp+57h+Block]
0x1800abff9  call    ?AddAccessXXXAces@CACL@SecUtil@@AEAAXW4EACCESSTYPE@12@KQEAPEAXQEBKQEBE@Z; SecUtil::CACL::AddAccessXXXAces(SecUtil::CACL::EACCESSTYPE,ulong,void * * const,ulong const * const,uchar const * const)
0x1800abffe  mov     byte ptr [rbp+57h+arg_8], 2
0x1800ac002  mov     r15d, 1F01FFh
0x1800ac008  mov     [rbp+57h+var_D0], r15d
0x1800ac00c  mov     [rbp+57h+Sid], rbx
0x1800ac010  lea     rax, [rbp+57h+arg_8]
0x1800ac014  mov     [rsp+100h+var_D8], rax
0x1800ac019  lea     rax, [rbp+57h+var_D0]
0x1800ac01d  mov     [rsp+100h+var_E0], rax
0x1800ac022  lea     r9, [rbp+57h+Sid]
0x1800ac026  mov     edx, esi
0x1800ac028  lea     rcx, [rbp+57h+Block]
0x1800ac02c  call    ?AddAccessXXXAces@CACL@SecUtil@@AEAAXW4EACCESSTYPE@12@KQEAPEAXQEBKQEBE@Z; SecUtil::CACL::AddAccessXXXAces(SecUtil::CACL::EACCESSTYPE,ulong,void * * const,ulong const * const,uchar const * const)
0x1800ac031  mov     byte ptr [rbp+57h+arg_8], 9
0x1800ac035  mov     [rbp+57h+var_D0], r14d
0x1800ac039  mov     [rbp+57h+Sid], rdi
0x1800ac03d  lea     rax, [rbp+57h+arg_8]
0x1800ac041  mov     [rsp+100h+var_D8], rax
0x1800ac046  lea     rax, [rbp+57h+var_D0]
0x1800ac04a  mov     [rsp+100h+var_E0], rax
0x1800ac04f  lea     r9, [rbp+57h+Sid]
0x1800ac053  mov     edx, esi
0x1800ac055  lea     rcx, [rbp+57h+Block]
0x1800ac059  call    ?AddAccessXXXAces@CACL@SecUtil@@AEAAXW4EACCESSTYPE@12@KQEAPEAXQEBKQEBE@Z; SecUtil::CACL::AddAccessXXXAces(SecUtil::CACL::EACCESSTYPE,ulong,void * * const,ulong const * const,uchar const * const)
0x1800ac05e  mov     byte ptr [rbp+57h+arg_8], 2
0x1800ac062  mov     [rbp+57h+var_D0], r15d
0x1800ac066  mov     [rbp+57h+Sid], rdi
0x1800ac06a  lea     rax, [rbp+57h+arg_8]
0x1800ac06e  mov     [rsp+100h+var_D8], rax
0x1800ac073  lea     rax, [rbp+57h+var_D0]
0x1800ac077  mov     [rsp+100h+var_E0], rax
0x1800ac07c  lea     r9, [rbp+57h+Sid]
0x1800ac080  mov     edx, esi
0x1800ac082  lea     rcx, [rbp+57h+Block]
0x1800ac086  call    ?AddAccessXXXAces@CACL@SecUtil@@AEAAXW4EACCESSTYPE@12@KQEAPEAXQEBKQEBE@Z; SecUtil::CACL::AddAccessXXXAces(SecUtil::CACL::EACCESSTYPE,ulong,void * * const,ulong const * const,uchar const * const)
0x1800ac08b  test    r12, r12
0x1800ac08e  jz      loc_1800AC12D
0x1800ac094  mov     [rbp+57h+Sid], 0
0x1800ac09c  lea     rdx, [rbp+57h+Sid]; Sid
0x1800ac0a0  mov     rcx, r12; StringSid
0x1800ac0a3  call    cs:__imp_ConvertStringSidToSidW
0x1800ac0a9  mov     rcx, [rbp+5Fh]; this
0x1800ac0ad  test    eax, eax
0x1800ac0af  jnz     short loc_1800AC0C1
0x1800ac0b1  lea     r8, aOnecoreuapBase_268; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800ac0b8  lea     edx, [rax+49h]; void *
0x1800ac0bb  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800ac0c1  mov     byte ptr [rbp+57h+arg_8], 9
0x1800ac0c5  mov     [rbp+57h+var_D0], r14d
0x1800ac0c9  mov     rax, [rbp+57h+Sid]
0x1800ac0cd  mov     [rbp+57h+var_B8], rax
0x1800ac0d1  lea     rax, [rbp+57h+arg_8]
0x1800ac0d5  mov     [rsp+100h+var_D8], rax
0x1800ac0da  lea     rax, [rbp+57h+var_D0]
0x1800ac0de  mov     [rsp+100h+var_E0], rax
0x1800ac0e3  lea     r9, [rbp+57h+var_B8]
0x1800ac0e7  mov     edx, esi
0x1800ac0e9  lea     rcx, [rbp+57h+Block]
0x1800ac0ed  call    ?AddAccessXXXAces@CACL@SecUtil@@AEAAXW4EACCESSTYPE@12@KQEAPEAXQEBKQEBE@Z; SecUtil::CACL::AddAccessXXXAces(SecUtil::CACL::EACCESSTYPE,ulong,void * * const,ulong const * const,uchar const * const)
0x1800ac0f2  mov     byte ptr [rbp+57h+arg_8], 2
0x1800ac0f6  mov     [rbp+57h+var_D0], r15d
0x1800ac0fa  mov     rax, [rbp+57h+Sid]
0x1800ac0fe  mov     [rbp+57h+var_B8], rax
0x1800ac102  lea     rax, [rbp+57h+arg_8]
0x1800ac106  mov     [rsp+100h+var_D8], rax
0x1800ac10b  lea     rax, [rbp+57h+var_D0]
0x1800ac10f  mov     [rsp+100h+var_E0], rax
0x1800ac114  lea     r9, [rbp+57h+var_B8]
0x1800ac118  mov     edx, esi
0x1800ac11a  lea     rcx, [rbp+57h+Block]
0x1800ac11e  call    ?AddAccessXXXAces@CACL@SecUtil@@AEAAXW4EACCESSTYPE@12@KQEAPEAXQEBKQEBE@Z; SecUtil::CACL::AddAccessXXXAces(SecUtil::CACL::EACCESSTYPE,ulong,void * * const,ulong const * const,uchar const * const)
0x1800ac123  nop
0x1800ac124  lea     rcx, [rbp+57h+Sid]
0x1800ac128  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800ac12d  mov     rsi, [rbp+57h+Block]
0x1800ac131  mov     r8, rsi; struct _ACL *
0x1800ac134  lea     rcx, [rbp+57h+pSecurityDescriptor]; this
0x1800ac138  call    ?SetDacl@CSecurityDescriptor@SecUtil@@QEAAXHPEAU_ACL@@H@Z; SecUtil::CSecurityDescriptor::SetDacl(int,_ACL *,int)
0x1800ac13d  lea     rax, [rbp+57h+pSecurityDescriptor]
0x1800ac141  mov     qword ptr [rbp+57h+var_B0+8], rax
0x1800ac145  jmp     short loc_1800AC14F
0x1800ac147  mov     qword ptr [rbp+57h+var_B0+8], r15
0x1800ac14b  mov     rsi, [rbp+57h+Block]
0x1800ac14f  lea     r8, [rbp+57h+var_B0]; unsigned int *
0x1800ac153  lea     rdx, [rbp+57h+arg_18]; wchar_t *
0x1800ac157  mov     rcx, r13; this
0x1800ac15a  call    ?MakeDirectory@FSOp@@YAHPEB_WAEAKPEAU_SECURITY_ATTRIBUTES@@@Z; FSOp::MakeDirectory(wchar_t const *,ulong &,_SECURITY_ATTRIBUTES *)
0x1800ac15f  test    eax, eax
0x1800ac161  jnz     short loc_1800AC17B
0x1800ac163  mov     rcx, [rbp+5Fh]; this
0x1800ac167  mov     r9d, [rbp+57h+arg_18]; char *
0x1800ac16b  lea     r8, aOnecoreuapBase_268; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800ac172  lea     edx, [rax+5Bh]; void *
0x1800ac175  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800ac17b  mov     rcx, rsi; Block
0x1800ac17e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ac183  nop
0x1800ac184  test    rdi, rdi
0x1800ac187  jz      short loc_1800AC192
0x1800ac189  mov     rcx, rdi; Block
0x1800ac18c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ac191  nop
0x1800ac192  test    rbx, rbx
0x1800ac195  jz      short loc_1800AC1A0
0x1800ac197  mov     rcx, rbx; Block
0x1800ac19a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ac19f  nop
0x1800ac1a0  lea     rcx, [rbp+57h+pSecurityDescriptor]; this
0x1800ac1a4  call    ??1CSecurityDescriptor@SecUtil@@QEAA@XZ; SecUtil::CSecurityDescriptor::~CSecurityDescriptor(void)
0x1800ac1a9  mov     rbx, [rsp+100h+arg_0]
0x1800ac1b1  add     rsp, 0D0h
0x1800ac1b8  pop     r15
0x1800ac1ba  pop     r14
0x1800ac1bc  pop     r13
0x1800ac1be  pop     r12
0x1800ac1c0  pop     rdi
0x1800ac1c1  pop     rsi
0x1800ac1c2  pop     rbp
0x1800ac1c3  retn
```
