# SecUtil::CACL::DeserializeResolved(CBlob &,bool *,bool *)

- ea: `0x1800ac1cc`
- end: `0x1800ac8ab`
- name: `?DeserializeResolved@CACL@SecUtil@@QEAAJAEAVCBlob@@PEA_N1@Z`
- size: `1759`
- prototype: `__int64 __fastcall(SecUtil::CACL *__hidden this, struct CBlob *, bool *, bool *)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18007a358`
- `0x180207dd4`

## callees

- `0x18000ee60`
- `0x1800ab770`
- `0x1800ac1cc`
- `0x1800ac938`
- `0x1800ad2a0`
- `0x1800ad2b4`
- `0x1800ad360`
- `0x1800ba67c`
- `0x1800e2374`
- `0x1801244c0`
- `0x1801249b0`
- `0x180124d00`
- `0x18014a41c`
- `0x18014a450`
- `0x18014a634`
- `0x18014a72c`
- `0x18014a9c4`
- `0x18014ab14`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800ac778`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800ac7c2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800ac778`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800ac7c2`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800ac317`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800ac38b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800ac3f3`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800ac45b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800ac317`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800ac38b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800ac3f3`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800ac45b`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1800ac2ea`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1800ac369`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1800ac3d1`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1800ac439`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1800ac2ea`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1800ac369`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1800ac3d1`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1800ac439`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1800ac2cd`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1800ac34c`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1800ac3b4`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1800ac41c`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1800ac2cd`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1800ac34c`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1800ac3b4`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1800ac41c`

## string_xrefs

- `0x1800ac274`: `onecoreuap\base\appmodel\Search\common\include\smartcls_common.hxx`
- `0x1800ac2a5`: `onecoreuap\base\appmodel\Search\common\include\smartcls_common.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=2
__int64 __fastcall SecUtil::CACL::DeserializeResolved(SecUtil::CACL *this, struct CBlob *a2, bool *a3, bool *a4)
{
  bool *v4; // r15
  struct CBlob *v5; // r14
  int *v6; // rcx
  int v7; // eax
  unsigned __int64 v9; // rax
  unsigned int v10; // r13d
  DWORD SidLengthRequired; // eax
  void *v12; // rdi
  DWORD i; // r12d
  DWORD v14; // ebx
  unsigned __int64 v15; // rcx
  void *v16; // rbx
  DWORD v17; // edi
  unsigned __int64 v18; // rcx
  void *v19; // rbx
  DWORD v20; // edi
  unsigned __int64 v21; // rcx
  void *v22; // rbx
  DWORD v23; // edi
  void *v24; // rdx
  PSID v25; // rbx
  __int64 v26; // r8
  PSID v27; // rbx
  __int64 v28; // r8
  int v29; // [rsp+20h] [rbp-308h]
  _BYTE v30[8]; // [rsp+30h] [rbp-2F8h] BYREF
  PSID pSid; // [rsp+38h] [rbp-2F0h] BYREF
  void *v32; // [rsp+40h] [rbp-2E8h] BYREF
  unsigned int v33[2]; // [rsp+48h] [rbp-2E0h] BYREF
  unsigned int v34; // [rsp+50h] [rbp-2D8h] BYREF
  unsigned int v35; // [rsp+58h] [rbp-2D0h] BYREF
  unsigned int j; // [rsp+5Ch] [rbp-2CCh]
  void *Block; // [rsp+60h] [rbp-2C8h] BYREF
  void *v38; // [rsp+68h] [rbp-2C0h] BYREF
  void *v39; // [rsp+70h] [rbp-2B8h] BYREF
  unsigned int v40; // [rsp+78h] [rbp-2B0h]
  struct CBlob *v41; // [rsp+80h] [rbp-2A8h]
  bool *v42; // [rsp+88h] [rbp-2A0h]
  unsigned int v43; // [rsp+90h] [rbp-298h]
  bool *v44; // [rsp+98h] [rbp-290h]
  SecUtil::CACL *v45; // [rsp+A0h] [rbp-288h]
  void *v46; // [rsp+A8h] [rbp-280h]
  void **v47; // [rsp+C0h] [rbp-268h] BYREF
  wchar_t *v48; // [rsp+C8h] [rbp-260h]
  __int64 v49; // [rsp+D0h] [rbp-258h]
  _WORD v50[260]; // [rsp+D8h] [rbp-250h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+0h]

  v4 = a3;
  v5 = a2;
  v45 = this;
  v41 = a2;
  v42 = a3;
  v44 = a4;
  v40 = 0;
  if ( a3 )
    *a3 = 0;
  *a4 = 0;
  SecUtil::CACL::Reset(v45);
  *((_DWORD *)v5 + 6) = 0;
  v6 = (int *)*((_QWORD *)v5 + 2);
  v7 = *v6;
  *((_DWORD *)v5 + 6) = 4;
  if ( v7 != -558183783 )
    return 2147500037LL;
  v9 = *((unsigned int *)v5 + 2) - 4LL;
  if ( v9 < 4 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2CF,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\smartcls_common.hxx",
      (const char *)0x80004005LL,
      v29);
  v10 = v6[1];
  *((_DWORD *)v5 + 6) = 8;
  if ( v9 < 8 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2CF,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\smartcls_common.hxx",
      (const char *)0x80004005LL,
      v29);
  *((_DWORD *)v5 + 6) = 12;
  v46 = 0;
  v39 = 0;
  SidLengthRequired = GetSidLengthRequired(2u);
  v12 = operator new[](SidLengthRequired);
  if ( InitializeSid(v12, (PSID_IDENTIFIER_AUTHORITY)SecUtil::CSID_EveryoneAccount::s_sia.SubAuthority, 2u) )
  {
    for ( i = 0; i < 2; ++i )
    {
      v14 = *(&SecUtil::CSID_AdministratorsGroup::s_rgSubAuth + i);
      *GetSidSubAuthority(v12, i) = v14;
    }
    v39 = 0;
    v46 = v12;
    TPointer<unsigned char>::~TPointer<unsigned char>(&v39);
  }
  else
  {
    operator delete(v12);
  }
  v39 = 0;
  v38 = 0;
  v15 = GetSidLengthRequired(1u);
  v16 = operator new[](v15);
  if ( InitializeSid(v16, (PSID_IDENTIFIER_AUTHORITY)SecUtil::CSID_NetworkServiceAccount::s_sia.SubAuthority, 1u) )
  {
    v17 = SecUtil::CSID_SystemAccount::s_rgSubAuth;
    *GetSidSubAuthority(v16, 0) = v17;
    v38 = 0;
    v39 = v16;
    TPointer<unsigned char>::~TPointer<unsigned char>(&v38);
  }
  else
  {
    operator delete(v16);
  }
  v38 = 0;
  Block = 0;
  v18 = GetSidLengthRequired(1u);
  v19 = operator new[](v18);
  if ( InitializeSid(v19, (PSID_IDENTIFIER_AUTHORITY)&SecUtil::CSID_EveryoneAccount::s_sia, 1u) )
  {
    v20 = SecUtil::CSID_EveryoneAccount::s_rgSubAuth;
    *GetSidSubAuthority(v19, 0) = v20;
    Block = 0;
    v38 = v19;
    TPointer<unsigned char>::~TPointer<unsigned char>(&Block);
  }
  else
  {
    operator delete(v19);
  }
  Block = 0;
  v32 = 0;
  v21 = GetSidLengthRequired(1u);
  v22 = operator new[](v21);
  if ( InitializeSid(v22, (PSID_IDENTIFIER_AUTHORITY)&SecUtil::CSID_NetworkServiceAccount::s_sia, 1u) )
  {
    v23 = (unsigned int)SecUtil::CSID_NetworkServiceAccount::s_rgSubAuth;
    *GetSidSubAuthority(v22, 0) = v23;
    v32 = 0;
    Block = v22;
    TPointer<unsigned char>::~TPointer<unsigned char>(&v32);
  }
  else
  {
    operator delete(v22);
  }
  v43 = v10;
  for ( j = 0; j < v43; ++j )
  {
    v34 = 0;
    CBlob::Deser(v5, &v34);
    CBlob::Deser(v5, &v35);
    v35 = 0;
    CBlob::Deser(v5, &v35);
    pSid = 0;
    v33[0] = 0;
    CBlob::Deser(v5, v33);
    if ( v33[0] )
    {
      switch ( v33[0] )
      {
        case 1u:
          v24 = v39;
          goto LABEL_45;
        case 2u:
          v24 = v38;
          goto LABEL_45;
        case 3u:
          v48 = v50;
          v49 = 65;
          v50[0] = 0;
          v47 = &TLMString<64,64,256>::`vftable';
          CBlob::Deser(v5, (struct CLMString *)&v47);
          try
          {
            v32 = 0;
            SecUtil::CSID::InitFromAccountName((SecUtil::CSID *)&v32, v48);
            SecUtil::CSID::operator=(&pSid, v32);
            SecUtil::CSID::~CSID((SecUtil::CSID *)&v32);
            if ( v4 )
              *v4 = 1;
            TLMString<64,64,256>::~TLMString<64,64,256>(&v47);
          }
          catch ( ... )
          {
            *v44 = 1;
            TLMString<64,64,256>::~TLMString<64,64,256>(&v47);
            SecUtil::CSID::~CSID((SecUtil::CSID *)&pSid);
            goto LABEL_52;
          }
          break;
        default:
          switch ( v33[0] )
          {
            case 4u:
              v24 = Block;
LABEL_45:
              SecUtil::CSID::operator=(&pSid, v24);
              goto LABEL_47;
            case 5u:
              v48 = v50;
              v49 = 256;
              v50[0] = 0;
              v47 = &TLMString<255,255,4096>::`vftable';
              CBlob::Deser(v5, (struct CLMString *)&v47);
              try
              {
                SecUtil::CSID::InitFromStringSid((SecUtil::CSID *)&pSid, v48);
                if ( v4 )
                  *v4 = 1;
              }
              catch ( ... )
              {
                *v44 = 1;
                TLMString<255,255,4096>::~TLMString<255,255,4096>(&v47);
                SecUtil::CSID::~CSID((SecUtil::CSID *)&pSid);
                goto LABEL_52;
              }
              break;
            case 6u:
              v48 = v50;
              v49 = 256;
              v50[0] = 0;
              v47 = &TLMString<255,255,4096>::`vftable';
              v33[0] = 0;
              CBlob::Deser(v5, (struct CLMString *)&v47);
              CBlob::Deser(v5, v33);
              v32 = operator new[](v33[0]);
              CBlob::Deser(v5, v32, v33[0]);
              try
              {
                SecUtil::CSID::InitFromStringSid((SecUtil::CSID *)&pSid, v48);
              }
              catch ( ... )
              {
                if ( IsValidSid(v32) )
                {
                  SecUtil::CSID::operator=(&pSid, v32);
                  v5 = v41;
                  v4 = v42;
                  goto LABEL_33;
                }
                *v44 = 1;
                std::unique_ptr<enum gsl::byte [0]>::~unique_ptr<enum gsl::byte [0]>(&v32);
                TLMString<255,255,4096>::~TLMString<255,255,4096>(&v47);
                SecUtil::CSID::~CSID((SecUtil::CSID *)&pSid);
LABEL_52:
                v4 = v42;
                v5 = v41;
                continue;
              }
LABEL_33:
              std::unique_ptr<enum gsl::byte [0]>::~unique_ptr<enum gsl::byte [0]>(&v32);
              break;
            default:
              goto LABEL_47;
          }
          TLMString<255,255,4096>::~TLMString<255,255,4096>(&v47);
          break;
      }
    }
    else
    {
      SecUtil::CSID::operator=(&pSid, v46);
    }
LABEL_47:
    if ( v34 )
    {
      if ( v34 == 1 )
      {
        v25 = pSid;
        GetLengthSid(pSid);
        v34 = v35;
        v32 = v25;
        v30[0] = 0;
        ((void (__fastcall *)(SecUtil::CACL *, _QWORD, __int64, void **, unsigned int *, _BYTE *))SecUtil::CACL::AddAccessXXXAces)(
          v45,
          0,
          v26,
          &v32,
          &v34,
          v30);
      }
    }
    else
    {
      v27 = pSid;
      GetLengthSid(pSid);
      v34 = v35;
      v32 = v27;
      v30[0] = 0;
      ((void (__fastcall *)(SecUtil::CACL *, __int64, __int64, void **, unsigned int *, _BYTE *))SecUtil::CACL::AddAccessXXXAces)(
        v45,
        1,
        v28,
        &v32,
        &v34,
        v30);
    }
    SecUtil::CSID::~CSID((SecUtil::CSID *)&pSid);
  }
  if ( Block )
    operator delete(Block);
  if ( v38 )
    operator delete(v38);
  if ( v39 )
    operator delete(v39);
  if ( v46 )
    operator delete(v46);
  return v40;
}

```

## disassembly

```asm
0x1800ac1cc  push    rbx
0x1800ac1ce  push    rsi
0x1800ac1cf  push    rdi
0x1800ac1d0  push    r12
0x1800ac1d2  push    r13
0x1800ac1d4  push    r14
0x1800ac1d6  push    r15
0x1800ac1d8  sub     rsp, 2F0h
0x1800ac1df  mov     rax, cs:__security_cookie
0x1800ac1e6  xor     rax, rsp
0x1800ac1e9  mov     [rsp+328h+var_48], rax
0x1800ac1f1  mov     r15, r8
0x1800ac1f4  mov     r14, rdx
0x1800ac1f7  mov     [rsp+328h+var_288], rcx
0x1800ac1ff  mov     [rsp+328h+var_2A8], rdx
0x1800ac207  mov     [rsp+328h+var_2A0], r8
0x1800ac20f  mov     [rsp+328h+var_290], r9
0x1800ac217  xor     esi, esi
0x1800ac219  mov     [rsp+328h+var_2B0], esi
0x1800ac21d  test    r8, r8
0x1800ac220  jz      short loc_1800AC225
0x1800ac222  mov     [r8], sil
0x1800ac225  mov     [r9], sil
0x1800ac228  mov     rcx, [rsp+328h+var_288]; this
0x1800ac230  call    ?Reset@CACL@SecUtil@@QEAAXXZ; SecUtil::CACL::Reset(void)
0x1800ac235  mov     [r14+18h], esi
0x1800ac239  mov     rcx, [r14+10h]
0x1800ac23d  mov     eax, [rcx]
0x1800ac23f  mov     dword ptr [r14+18h], 4
0x1800ac247  cmp     eax, 0DEBACA99h
0x1800ac24c  jz      short loc_1800AC258
0x1800ac24e  mov     eax, 80004005h
0x1800ac253  jmp     loc_1800AC887
0x1800ac258  mov     eax, [r14+8]
0x1800ac25c  add     rax, 0FFFFFFFFFFFFFFFCh
0x1800ac260  cmp     rax, 4
0x1800ac264  jnb     short loc_1800AC285
0x1800ac266  mov     rcx, [rsp+328h]; this
0x1800ac26e  mov     r9d, 80004005h; char *
0x1800ac274  lea     r8, aOnecoreuapBase_200; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1800ac27b  mov     edx, 2CFh; void *
0x1800ac280  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ac285  mov     r13d, [rcx+4]
0x1800ac289  mov     dword ptr [r14+18h], 8
0x1800ac291  cmp     rax, 8
0x1800ac295  jnb     short loc_1800AC2B6
0x1800ac297  mov     rcx, [rsp+328h]; this
0x1800ac29f  mov     r9d, 80004005h; char *
0x1800ac2a5  lea     r8, aOnecoreuapBase_200; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1800ac2ac  mov     edx, 2CFh; void *
0x1800ac2b1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ac2b6  mov     dword ptr [r14+18h], 0Ch
0x1800ac2be  mov     [rsp+328h+var_280], rsi
0x1800ac2c6  mov     [rsp+328h+var_2B8], rsi
0x1800ac2cb  mov     cl, 2; nSubAuthorityCount
0x1800ac2cd  call    cs:__imp_GetSidLengthRequired
0x1800ac2d3  mov     ecx, eax; unsigned __int64
0x1800ac2d5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800ac2da  mov     rdi, rax
0x1800ac2dd  mov     r8b, 2; nSubAuthorityCount
0x1800ac2e0  lea     rdx, ?s_sia@CSID_EveryoneAccount@SecUtil@@0U_SID_IDENTIFIER_AUTHORITY@@A.SubAuthority; pIdentifierAuthority
0x1800ac2e7  mov     rcx, rax; Sid
0x1800ac2ea  call    cs:__imp_InitializeSid
0x1800ac2f0  test    eax, eax
0x1800ac2f2  jnz     short loc_1800AC301
0x1800ac2f4  lea     edx, [rax+1]
0x1800ac2f7  mov     rcx, rdi; Block
0x1800ac2fa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ac2ff  jmp     short loc_1800AC340
0x1800ac301  mov     r12d, esi
0x1800ac304  mov     eax, r12d
0x1800ac307  lea     rbx, ?s_rgSubAuth@CSID_AdministratorsGroup@SecUtil@@0PAKA; ulong near * SecUtil::CSID_AdministratorsGroup::s_rgSubAuth
0x1800ac30e  mov     ebx, [rbx+rax*4]
0x1800ac311  mov     edx, r12d; nSubAuthority
0x1800ac314  mov     rcx, rdi; pSid
0x1800ac317  call    cs:__imp_GetSidSubAuthority
0x1800ac31d  mov     [rax], ebx
0x1800ac31f  inc     r12d
0x1800ac322  cmp     r12d, 2
0x1800ac326  jb      short loc_1800AC304
0x1800ac328  mov     [rsp+328h+var_2B8], rsi
0x1800ac32d  mov     [rsp+328h+var_280], rdi
0x1800ac335  lea     rcx, [rsp+328h+var_2B8]
0x1800ac33a  call    ??1?$TPointer@E@@QEAA@XZ; TPointer<uchar>::~TPointer<uchar>(void)
0x1800ac33f  nop
0x1800ac340  mov     [rsp+328h+var_2B8], rsi
0x1800ac345  mov     [rsp+328h+var_2C0], rsi
0x1800ac34a  mov     cl, 1; nSubAuthorityCount
0x1800ac34c  call    cs:__imp_GetSidLengthRequired
0x1800ac352  mov     ecx, eax; unsigned __int64
0x1800ac354  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800ac359  mov     rbx, rax
0x1800ac35c  mov     r8b, 1; nSubAuthorityCount
0x1800ac35f  lea     rdx, ?s_sia@CSID_NetworkServiceAccount@SecUtil@@0U_SID_IDENTIFIER_AUTHORITY@@A.SubAuthority; pIdentifierAuthority
0x1800ac366  mov     rcx, rax; Sid
0x1800ac369  call    cs:__imp_InitializeSid
0x1800ac36f  test    eax, eax
0x1800ac371  jnz     short loc_1800AC380
0x1800ac373  lea     edx, [rax+1]
0x1800ac376  mov     rcx, rbx; Block
0x1800ac379  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ac37e  jmp     short loc_1800AC3A8
0x1800ac380  mov     edi, cs:?s_rgSubAuth@CSID_SystemAccount@SecUtil@@0PAKA; ulong near * SecUtil::CSID_SystemAccount::s_rgSubAuth
0x1800ac386  xor     edx, edx; nSubAuthority
0x1800ac388  mov     rcx, rbx; pSid
0x1800ac38b  call    cs:__imp_GetSidSubAuthority
0x1800ac391  mov     [rax], edi
0x1800ac393  mov     [rsp+328h+var_2C0], rsi
0x1800ac398  mov     [rsp+328h+var_2B8], rbx
0x1800ac39d  lea     rcx, [rsp+328h+var_2C0]
0x1800ac3a2  call    ??1?$TPointer@E@@QEAA@XZ; TPointer<uchar>::~TPointer<uchar>(void)
0x1800ac3a7  nop
0x1800ac3a8  mov     [rsp+328h+var_2C0], rsi
0x1800ac3ad  mov     [rsp+328h+Block], rsi
0x1800ac3b2  mov     cl, 1; nSubAuthorityCount
0x1800ac3b4  call    cs:__imp_GetSidLengthRequired
0x1800ac3ba  mov     ecx, eax; unsigned __int64
0x1800ac3bc  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800ac3c1  mov     rbx, rax
0x1800ac3c4  mov     r8b, 1; nSubAuthorityCount
0x1800ac3c7  lea     rdx, ?s_sia@CSID_EveryoneAccount@SecUtil@@0U_SID_IDENTIFIER_AUTHORITY@@A; pIdentifierAuthority
0x1800ac3ce  mov     rcx, rax; Sid
0x1800ac3d1  call    cs:__imp_InitializeSid
0x1800ac3d7  test    eax, eax
0x1800ac3d9  jnz     short loc_1800AC3E8
0x1800ac3db  lea     edx, [rax+1]
0x1800ac3de  mov     rcx, rbx; Block
0x1800ac3e1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ac3e6  jmp     short loc_1800AC410
0x1800ac3e8  mov     edi, cs:?s_rgSubAuth@CSID_EveryoneAccount@SecUtil@@0PAKA; ulong near * SecUtil::CSID_EveryoneAccount::s_rgSubAuth
0x1800ac3ee  xor     edx, edx; nSubAuthority
0x1800ac3f0  mov     rcx, rbx; pSid
0x1800ac3f3  call    cs:__imp_GetSidSubAuthority
0x1800ac3f9  mov     [rax], edi
0x1800ac3fb  mov     [rsp+328h+Block], rsi
0x1800ac400  mov     [rsp+328h+var_2C0], rbx
0x1800ac405  lea     rcx, [rsp+328h+Block]
0x1800ac40a  call    ??1?$TPointer@E@@QEAA@XZ; TPointer<uchar>::~TPointer<uchar>(void)
0x1800ac40f  nop
0x1800ac410  mov     [rsp+328h+Block], rsi
0x1800ac415  mov     [rsp+328h+var_2E8], rsi
0x1800ac41a  mov     cl, 1; nSubAuthorityCount
0x1800ac41c  call    cs:__imp_GetSidLengthRequired
0x1800ac422  mov     ecx, eax; unsigned __int64
0x1800ac424  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800ac429  mov     rbx, rax
0x1800ac42c  mov     r8b, 1; nSubAuthorityCount
0x1800ac42f  lea     rdx, ?s_sia@CSID_NetworkServiceAccount@SecUtil@@0U_SID_IDENTIFIER_AUTHORITY@@A; pIdentifierAuthority
0x1800ac436  mov     rcx, rax; Sid
0x1800ac439  call    cs:__imp_InitializeSid
0x1800ac43f  test    eax, eax
0x1800ac441  jnz     short loc_1800AC450
0x1800ac443  lea     edx, [rax+1]
0x1800ac446  mov     rcx, rbx; Block
0x1800ac449  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ac44e  jmp     short loc_1800AC478
0x1800ac450  mov     edi, cs:?s_rgSubAuth@CSID_NetworkServiceAccount@SecUtil@@0PAKA; ulong near * SecUtil::CSID_NetworkServiceAccount::s_rgSubAuth
0x1800ac456  xor     edx, edx; nSubAuthority
0x1800ac458  mov     rcx, rbx; pSid
0x1800ac45b  call    cs:__imp_GetSidSubAuthority
0x1800ac461  mov     [rax], edi
0x1800ac463  mov     [rsp+328h+var_2E8], rsi
0x1800ac468  mov     [rsp+328h+Block], rbx
0x1800ac46d  lea     rcx, [rsp+328h+var_2E8]
0x1800ac472  call    ??1?$TPointer@E@@QEAA@XZ; TPointer<uchar>::~TPointer<uchar>(void)
0x1800ac477  nop
0x1800ac478  mov     [rsp+328h+var_298], r13d
0x1800ac480  mov     [rsp+328h+var_2CC], esi
0x1800ac484  lea     rdi, ??_7?$TLMString@$0PP@$0PP@$0BAAA@@@6B@; const TLMString<255,255,4096>::`vftable'
0x1800ac48b  mov     eax, [rsp+328h+var_298]
0x1800ac492  cmp     [rsp+328h+var_2CC], eax
0x1800ac496  jnb     loc_1800AC83E
0x1800ac49c  mov     [rsp+328h+var_2D8], esi
0x1800ac4a0  lea     rdx, [rsp+328h+var_2D8]; unsigned int *
0x1800ac4a5  mov     rcx, r14; this
0x1800ac4a8  call    ?Deser@CBlob@@QEAAXAEAK@Z; CBlob::Deser(ulong &)
0x1800ac4ad  lea     rdx, [rsp+328h+var_2D0]; unsigned int *
0x1800ac4b2  mov     rcx, r14; this
0x1800ac4b5  call    ?Deser@CBlob@@QEAAXAEAK@Z; CBlob::Deser(ulong &)
0x1800ac4ba  mov     [rsp+328h+var_2D0], esi
0x1800ac4be  lea     rdx, [rsp+328h+var_2D0]; unsigned int *
0x1800ac4c3  mov     rcx, r14; this
0x1800ac4c6  call    ?Deser@CBlob@@QEAAXAEAK@Z; CBlob::Deser(ulong &)
0x1800ac4cb  mov     [rsp+328h+pSid], rsi
0x1800ac4d0  mov     [rsp+328h+var_2E0], esi
0x1800ac4d4  lea     rdx, [rsp+328h+var_2E0]; unsigned int *
0x1800ac4d9  mov     rcx, r14; this
0x1800ac4dc  call    ?Deser@CBlob@@QEAAXAEAK@Z; CBlob::Deser(ulong &)
0x1800ac4e1  nop
0x1800ac4e2  mov     eax, [rsp+328h+var_2E0]
0x1800ac4e6  test    eax, eax
0x1800ac4e8  jz      loc_1800AC74C
0x1800ac4ee  sub     eax, 1
0x1800ac4f1  jz      loc_1800AC73B
0x1800ac4f7  sub     eax, 1
0x1800ac4fa  jz      loc_1800AC734
0x1800ac500  sub     eax, 1
0x1800ac503  jz      loc_1800AC688
0x1800ac509  sub     eax, 1
0x1800ac50c  jz      loc_1800AC67E
0x1800ac512  sub     eax, 1
0x1800ac515  jz      loc_1800AC5F6
0x1800ac51b  cmp     eax, 1
0x1800ac51e  jnz     loc_1800AC75F
0x1800ac524  lea     rax, [rsp+328h+var_250]
0x1800ac52c  mov     [rsp+328h+var_260], rax
0x1800ac534  mov     [rsp+328h+var_258], 100h
0x1800ac540  mov     [rsp+328h+var_250], si
0x1800ac548  mov     [rsp+328h+var_268], rdi
0x1800ac550  mov     [rsp+328h+var_2E0], esi
0x1800ac554  lea     rdx, [rsp+328h+var_268]; struct CLMString *
0x1800ac55c  mov     rcx, r14; this
0x1800ac55f  call    ?Deser@CBlob@@QEAAXAEAVCLMString@@@Z; CBlob::Deser(CLMString &)
0x1800ac564  lea     rdx, [rsp+328h+var_2E0]; unsigned int *
0x1800ac569  mov     rcx, r14; this
0x1800ac56c  call    ?Deser@CBlob@@QEAAXAEAK@Z; CBlob::Deser(ulong &)
0x1800ac571  mov     ecx, [rsp+328h+var_2E0]; unsigned __int64
0x1800ac575  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800ac57a  mov     [rsp+328h+var_2E8], rax
0x1800ac57f  mov     r8d, [rsp+328h+var_2E0]; unsigned int
0x1800ac584  mov     rdx, rax; void *
0x1800ac587  mov     rcx, r14; this
0x1800ac58a  call    ?Deser@CBlob@@QEAAXPEAXK@Z; CBlob::Deser(void *,ulong)
0x1800ac58f  nop
0x1800ac590  mov     rdx, [rsp+328h+var_260]; wchar_t *
0x1800ac598  lea     rcx, [rsp+328h+pSid]; this
0x1800ac59d  call    ?InitFromStringSid@CSID@SecUtil@@QEAAXPEB_W@Z; SecUtil::CSID::InitFromStringSid(wchar_t const *)
0x1800ac5a2  nop
0x1800ac5a3  jmp     short loc_1800AC5BE
0x1800ac5a5  xor     esi, esi
0x1800ac5a7  lea     rdi, ??_7?$TLMString@$0PP@$0PP@$0BAAA@@@6B@; const TLMString<255,255,4096>::`vftable'
0x1800ac5ae  mov     r14, [rsp+328h+var_2A8]
0x1800ac5b6  mov     r15, [rsp+328h+var_2A0]
0x1800ac5be  lea     rcx, [rsp+328h+var_2E8]
0x1800ac5c3  call    ??1?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@std@@@std@@QEAA@XZ; std::unique_ptr<gsl::byte [0]>::~unique_ptr<gsl::byte [0]>(void)
0x1800ac5c8  nop
0x1800ac5c9  jmp     loc_1800AC64F
0x1800ac5ce  lea     rcx, [rsp+328h+var_2E8]
0x1800ac5d3  call    ??1?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@std@@@std@@QEAA@XZ; std::unique_ptr<gsl::byte [0]>::~unique_ptr<gsl::byte [0]>(void)
0x1800ac5d8  nop
0x1800ac5d9  lea     rcx, [rsp+328h+var_268]
0x1800ac5e1  call    ??1?$TLMString@$0PP@$0PP@$0BAAA@@@UEAA@XZ; TLMString<255,255,4096>::~TLMString<255,255,4096>(void)
0x1800ac5e6  nop
0x1800ac5e7  lea     rcx, [rsp+328h+pSid]; this
0x1800ac5ec  call    ??1CSID@SecUtil@@QEAA@XZ; SecUtil::CSID::~CSID(void)
0x1800ac5f1  jmp     loc_1800AC81C
0x1800ac5f6  lea     rax, [rsp+328h+var_250]
0x1800ac5fe  mov     [rsp+328h+var_260], rax
0x1800ac606  mov     [rsp+328h+var_258], 100h
0x1800ac612  mov     [rsp+328h+var_250], si
0x1800ac61a  mov     [rsp+328h+var_268], rdi
0x1800ac622  lea     rdx, [rsp+328h+var_268]; struct CLMString *
0x1800ac62a  mov     rcx, r14; this
0x1800ac62d  call    ?Deser@CBlob@@QEAAXAEAVCLMString@@@Z; CBlob::Deser(CLMString &)
0x1800ac632  nop
0x1800ac633  mov     rdx, [rsp+328h+var_260]; wchar_t *
0x1800ac63b  lea     rcx, [rsp+328h+pSid]; this
0x1800ac640  call    ?InitFromStringSid@CSID@SecUtil@@QEAAXPEB_W@Z; SecUtil::CSID::InitFromStringSid(wchar_t const *)
0x1800ac645  nop
0x1800ac646  test    r15, r15
0x1800ac649  jz      short loc_1800AC64F
0x1800ac64b  mov     byte ptr [r15], 1
0x1800ac64f  lea     rcx, [rsp+328h+var_268]
0x1800ac657  call    ??1?$TLMString@$0PP@$0PP@$0BAAA@@@UEAA@XZ; TLMString<255,255,4096>::~TLMString<255,255,4096>(void)
0x1800ac65c  jmp     loc_1800AC75F
0x1800ac661  lea     rcx, [rsp+328h+var_268]
0x1800ac669  call    ??1?$TLMString@$0PP@$0PP@$0BAAA@@@UEAA@XZ; TLMString<255,255,4096>::~TLMString<255,255,4096>(void)
0x1800ac66e  nop
0x1800ac66f  lea     rcx, [rsp+328h+pSid]; this
0x1800ac674  call    ??1CSID@SecUtil@@QEAA@XZ; SecUtil::CSID::~CSID(void)
0x1800ac679  jmp     loc_1800AC81C
0x1800ac67e  mov     rdx, [rsp+328h+Block]
0x1800ac683  jmp     loc_1800AC740
0x1800ac688  lea     rax, [rsp+328h+var_250]
0x1800ac690  mov     [rsp+328h+var_260], rax
0x1800ac698  mov     [rsp+328h+var_258], 41h ; 'A'
0x1800ac6a4  mov     [rsp+328h+var_250], si
0x1800ac6ac  lea     rax, ??_7?$TLMString@$0EA@$0EA@$0BAA@@@6B@; const TLMString<64,64,256>::`vftable'
0x1800ac6b3  mov     [rsp+328h+var_268], rax
0x1800ac6bb  lea     rdx, [rsp+328h+var_268]; struct CLMString *
0x1800ac6c3  mov     rcx, r14; this
0x1800ac6c6  call    ?Deser@CBlob@@QEAAXAEAVCLMString@@@Z; CBlob::Deser(CLMString &)
0x1800ac6cb  nop
0x1800ac6cc  mov     [rsp+328h+var_2E8], rsi
0x1800ac6d1  mov     rdx, [rsp+328h+var_260]; wchar_t *
0x1800ac6d9  lea     rcx, [rsp+328h+var_2E8]; this
0x1800ac6de  call    ?InitFromAccountName@CSID@SecUtil@@QEAAXPEB_W@Z; SecUtil::CSID::InitFromAccountName(wchar_t const *)
0x1800ac6e3  nop
0x1800ac6e4  mov     rdx, [rsp+328h+var_2E8]
0x1800ac6e9  lea     rcx, [rsp+328h+pSid]
0x1800ac6ee  call    ??4CSID@SecUtil@@QEAAXPEAX@Z; SecUtil::CSID::operator=(void *)
0x1800ac6f3  nop
0x1800ac6f4  lea     rcx, [rsp+328h+var_2E8]; this
0x1800ac6f9  call    ??1CSID@SecUtil@@QEAA@XZ; SecUtil::CSID::~CSID(void)
0x1800ac6fe  nop
0x1800ac6ff  test    r15, r15
0x1800ac702  jz      short loc_1800AC708
0x1800ac704  mov     byte ptr [r15], 1
0x1800ac708  lea     rcx, [rsp+328h+var_268]
0x1800ac710  call    ??1?$TLMString@$0EA@$0EA@$0BAA@@@UEAA@XZ; TLMString<64,64,256>::~TLMString<64,64,256>(void)
  ... truncated ...
```
