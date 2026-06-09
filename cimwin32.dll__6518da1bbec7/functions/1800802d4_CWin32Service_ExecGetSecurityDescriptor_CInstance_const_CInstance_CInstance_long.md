# CWin32Service::ExecGetSecurityDescriptor(CInstance const &,CInstance *,CInstance *,long)

- ea: `0x1800802d4`
- end: `0x180080796`
- name: `?ExecGetSecurityDescriptor@CWin32Service@@AEAAJAEBVCInstance@@PEAV2@1J@Z`
- size: `1218`
- prototype: `__int64 __fastcall(CWin32Service *__hidden this, const struct CInstance *, struct CInstance *, struct CInstance *, int)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800cb160`

## callees

- `0x180015c80`
- `0x180032fd8`
- `0x180035e70`
- `0x18003d7b0`
- `0x18007f074`
- `0x18007f500`
- `0x1800802d4`
- `0x1800896cc`
- `0x180089784`
- `0x1800ca9e4`
- `0x1800caa14`
- `0x1800f353c`
- `0x1800f3570`
- `0x1800f3a80`
- `0x1800f85b4`
- `0x1800f8998`
- `0x1800f9700`
- `0x1800fc902`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080533`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080679`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080533`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080679`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800804a0`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180080586`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800804a0`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180080586`
- `framedynos!?SetEmbeddedObject@CInstance@@QEAA_NPEBGAEAV1@@Z` at `0x180080529`
- `framedynos!?SetEmbeddedObject@CInstance@@QEAA_NPEBGAEAV1@@Z` at `0x180080610`
- `framedynos!?SetEmbeddedObject@CInstance@@QEAA_NPEBGAEAV1@@Z` at `0x18008066f`
- `framedynos!?SetEmbeddedObject@CInstance@@QEAA_NPEBGAEAV1@@Z` at `0x180080529`
- `framedynos!?SetEmbeddedObject@CInstance@@QEAA_NPEBGAEAV1@@Z` at `0x180080610`
- `framedynos!?SetEmbeddedObject@CInstance@@QEAA_NPEBGAEAV1@@Z` at `0x18008066f`
- `framedynos!?GetEmptyInstance@CWbemProviderGlue@@SAJPEAVMethodContext@@PEBGPEAPEAVCInstance@@1@Z` at `0x1800803be`
- `framedynos!?GetEmptyInstance@CWbemProviderGlue@@SAJPEAVMethodContext@@PEBGPEAPEAVCInstance@@1@Z` at `0x1800804ed`
- `framedynos!?GetEmptyInstance@CWbemProviderGlue@@SAJPEAVMethodContext@@PEBGPEAPEAVCInstance@@1@Z` at `0x1800805d3`
- `framedynos!?GetEmptyInstance@CWbemProviderGlue@@SAJPEAVMethodContext@@PEBGPEAPEAVCInstance@@1@Z` at `0x1800803be`
- `framedynos!?GetEmptyInstance@CWbemProviderGlue@@SAJPEAVMethodContext@@PEBGPEAPEAVCInstance@@1@Z` at `0x1800804ed`
- `framedynos!?GetEmptyInstance@CWbemProviderGlue@@SAJPEAVMethodContext@@PEBGPEAPEAVCInstance@@1@Z` at `0x1800805d3`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180080307`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180080307`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800803dd`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800803dd`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18008038b`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180080412`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800804ba`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800805a0`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18008038b`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180080412`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800804ba`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800805a0`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800803f7`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180080438`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18008047f`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180080550`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180080691`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180080713`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800803f7`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180080438`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18008047f`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180080550`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180080691`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180080713`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800803a6`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800804d5`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800805bb`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800803a6`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800804d5`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800805bb`
- `framedynos!?GetNamespace@Provider@@IEAAAEBVCHString@@XZ` at `0x180080382`
- `framedynos!?GetNamespace@Provider@@IEAAAEBVCHString@@XZ` at `0x1800804b1`
- `framedynos!?GetNamespace@Provider@@IEAAAEBVCHString@@XZ` at `0x180080597`
- `framedynos!?GetNamespace@Provider@@IEAAAEBVCHString@@XZ` at `0x180080382`
- `framedynos!?GetNamespace@Provider@@IEAAAEBVCHString@@XZ` at `0x1800804b1`
- `framedynos!?GetNamespace@Provider@@IEAAAEBVCHString@@XZ` at `0x180080597`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800806fc`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180080773`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800806fc`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180080773`

## string_xrefs

- `0x1800803b4`: `Win32_SecurityDescriptor`
- `0x180080665`: `Descriptor`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CWin32Service::ExecGetSecurityDescriptor(
        CWin32Service *this,
        const struct CInstance *a2,
        struct CInstance *a3,
        struct CInstance *a4)
{
  const struct CHString *Namespace; // rax
  const unsigned __int16 *v8; // rbx
  struct MethodContext *MethodContext; // rax
  signed int EmptyInstance; // eax
  unsigned int v11; // ebx
  const unsigned __int16 *v12; // rax
  enum _SE_OBJECT_TYPE v13; // r8d
  unsigned int v14; // r9d
  signed int v15; // eax
  unsigned int v16; // ebx
  CInstance *v17; // rax
  const struct CHString *v18; // rax
  const unsigned __int16 *v19; // rbx
  struct MethodContext *v20; // rax
  CInstance *v21; // rbx
  struct CInstance *v22; // rax
  DWORD LastError; // eax
  const struct CHString *v24; // rax
  const unsigned __int16 *v25; // rbx
  struct MethodContext *v26; // rax
  CInstance *v27; // rbx
  struct CInstance *v28; // rax
  struct CInstance *v29; // rax
  struct CInstance *v31; // [rsp+20h] [rbp-E0h] BYREF
  struct CInstance *v32; // [rsp+28h] [rbp-D8h] BYREF
  struct CInstance *v33; // [rsp+30h] [rbp-D0h] BYREF
  CSecurityDescriptor *v34[2]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v35[8]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v36[2]; // [rsp+50h] [rbp-B0h] BYREF
  PSID v37; // [rsp+60h] [rbp-A0h] BYREF
  int v38; // [rsp+68h] [rbp-98h]
  __int64 v39; // [rsp+70h] [rbp-90h]
  __int64 v40; // [rsp+78h] [rbp-88h]
  __int64 v41; // [rsp+80h] [rbp-80h]
  int v42; // [rsp+88h] [rbp-78h]
  PSID pSid; // [rsp+90h] [rbp-70h] BYREF
  int v44; // [rsp+98h] [rbp-68h]
  __int64 v45; // [rsp+A0h] [rbp-60h]
  __int64 v46; // [rsp+A8h] [rbp-58h]
  __int64 v47; // [rsp+B0h] [rbp-50h]
  int v48; // [rsp+B8h] [rbp-48h]
  void **v49; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v50[152]; // [rsp+C8h] [rbp-38h] BYREF

  if ( a4 )
  {
    CHString::CHString((CHString *)v35);
    pSid = 0;
    v44 = 8;
    v45 = 0;
    v46 = 0;
    v47 = 0;
    v48 = 0;
    v37 = 0;
    v38 = 8;
    v39 = 0;
    v40 = 0;
    v41 = 0;
    v42 = 0;
    v49 = &CDACL::`vftable';
    memset_0(v50, 0, 0x50u);
    v36[0] = &CSACL::`vftable';
    v36[1] = 0;
    v33 = 0;
    v32 = 0;
    v31 = 0;
    Namespace = Provider::GetNamespace(this);
    v8 = (const unsigned __int16 *)CHString::operator unsigned short const *(Namespace);
    _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v31);
    v31 = 0;
    MethodContext = CInstance::GetMethodContext(a2);
    EmptyInstance = CWbemProviderGlue::GetEmptyInstance(MethodContext, L"Win32_SecurityDescriptor", &v31, v8);
    v11 = EmptyInstance;
    if ( EmptyInstance < 0 )
    {
      CInstance::SetDWORD(a4, L"ReturnValue", EmptyInstance);
    }
    else
    {
      if ( CInstance::GetCHString(a2, L"Name", (struct CHString *)v35) )
      {
        CSecurityInfo::CSecurityInfo((CSecurityInfo *)v34);
        v12 = (const unsigned __int16 *)CHString::operator unsigned short const *(v35);
        v15 = CSecurityInfo::Initialize((CSecurityInfo *)v34, v12, v13, v14);
        v11 = v15;
        if ( v15 < 0 )
        {
          CInstance::SetDWORD(a4, L"ReturnValue", v15);
          if ( v11 != -2147217402 && v11 != -2147024888 )
            v11 = 0;
          CSecurityInfo::~CSecurityInfo((CSecurityInfo *)v34);
          goto LABEL_26;
        }
        v16 = *((unsigned __int16 *)v34[0] + 24);
        v17 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v31);
        CInstance::SetDWORD(v17, L"ControlFlags", v16);
        CSecurityDescriptor::GetOwner(v34[0], (struct CSid *)&pSid);
        if ( pSid )
        {
          if ( IsValidSid(pSid) )
          {
            v18 = Provider::GetNamespace(this);
            v19 = (const unsigned __int16 *)CHString::operator unsigned short const *(v18);
            _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v33);
            v33 = 0;
            v20 = CInstance::GetMethodContext(a2);
            if ( (int)CWbemProviderGlue::GetEmptyInstance(v20, L"Win32_Trustee", &v33, v19) >= 0 )
            {
              FillTrusteeFromSid(v33, (struct CSid *)&pSid);
              v21 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v31);
              v22 = (struct CInstance *)_com_ptr_t<_com_IIID<CIRQDescriptor,&__s_GUID const _GUID_cb0e0537_d375_11d2_b35e_00104bc97924>>::operator->(&v33);
              if ( !CInstance::SetEmbeddedObject(v21, L"Owner", v22) )
                goto LABEL_14;
            }
          }
        }
        CSecurityDescriptor::GetGroup(v34[0], (struct CSid *)&v37);
        if ( !v37 )
          goto LABEL_22;
        if ( !IsValidSid(v37) )
          goto LABEL_22;
        v24 = Provider::GetNamespace(this);
        v25 = (const unsigned __int16 *)CHString::operator unsigned short const *(v24);
        _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v32);
        v32 = 0;
        v26 = CInstance::GetMethodContext(a2);
        if ( (int)CWbemProviderGlue::GetEmptyInstance(v26, L"Win32_Trustee", &v32, v25) < 0 )
          goto LABEL_22;
        FillTrusteeFromSid(v32, (struct CSid *)&v37);
        v27 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v31);
        v28 = (struct CInstance *)_com_ptr_t<_com_IIID<CIRQDescriptor,&__s_GUID const _GUID_cb0e0537_d375_11d2_b35e_00104bc97924>>::operator->(&v32);
        if ( !CInstance::SetEmbeddedObject(v27, L"Group", v28) )
        {
LABEL_14:
          LastError = GetLastError();
          if ( !LastError )
            LastError = -2147217407;
        }
        else
        {
LABEL_22:
          CSecurityDescriptor::GetDACL(v34[0], (struct CDACL *)&v49);
          FillInstanceDACL(v31, (struct CDACL *)&v49);
          CSecurityDescriptor::GetSACL(v34[0], (struct CSACL *)v36);
          FillInstanceSACL(v31, (struct CSACL *)v36);
          v29 = (struct CInstance *)_com_ptr_t<_com_IIID<CIRQDescriptor,&__s_GUID const _GUID_cb0e0537_d375_11d2_b35e_00104bc97924>>::operator->(&v31);
          if ( CInstance::SetEmbeddedObject(a4, L"Descriptor", v29) )
          {
            CInstance::SetDWORD(a4, L"ReturnValue", 0);
            CSecurityInfo::~CSecurityInfo((CSecurityInfo *)v34);
            _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v31);
            _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v32);
            _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v33);
            v36[0] = &CSACL::`vftable';
            CSACL::Clear((CSACL *)v36);
            v49 = &CDACL::`vftable';
            CDACL::Clear((CDACL *)&v49);
            CSid::~CSid(&v37);
            CSid::~CSid(&pSid);
            CHString::~CHString((CHString *)v35);
            return 0;
          }
          LastError = GetLastError();
        }
        CInstance::SetDWORD(a4, L"ReturnValue", LastError);
        CSecurityInfo::~CSecurityInfo((CSecurityInfo *)v34);
      }
      else
      {
        CInstance::SetDWORD(a4, L"ReturnValue", 0x8004100F);
      }
      v11 = 0;
    }
LABEL_26:
    _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v31);
    _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v32);
    _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v33);
    v36[0] = &CSACL::`vftable';
    CSACL::Clear((CSACL *)v36);
    v49 = &CDACL::`vftable';
    CDACL::Clear((CDACL *)&v49);
    CSid::~CSid(&v37);
    CSid::~CSid(&pSid);
    CHString::~CHString((CHString *)v35);
    return v11;
  }
  return 2147749896LL;
}

```

## disassembly

```asm
0x1800802d4  push    rbp
0x1800802d6  push    rbx
0x1800802d7  push    rsi
0x1800802d8  push    rdi
0x1800802d9  push    r12
0x1800802db  push    r13
0x1800802dd  push    r14
0x1800802df  push    r15
0x1800802e1  lea     rbp, [rsp-28h]
0x1800802e6  sub     rsp, 128h
0x1800802ed  mov     rdi, r9
0x1800802f0  mov     rsi, rdx
0x1800802f3  mov     r14, rcx
0x1800802f6  xor     r15d, r15d
0x1800802f9  test    r9, r9
0x1800802fc  jz      loc_18008077D
0x180080302  lea     rcx, [rsp+160h+var_118]
0x180080307  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x18008030d  nop
0x18008030e  mov     [rbp+60h+pSid], r15
0x180080312  lea     eax, [r15+8]
0x180080316  mov     [rbp+60h+var_C8], eax
0x180080319  mov     [rbp+60h+var_C0], r15
0x18008031d  mov     [rbp+60h+var_B8], r15
0x180080321  mov     [rbp+60h+var_B0], r15
0x180080325  mov     [rbp+60h+var_A8], r15d
0x180080329  mov     [rsp+160h+var_100], r15
0x18008032e  mov     [rsp+160h+var_F8], eax
0x180080332  mov     [rsp+160h+var_F0], r15
0x180080337  mov     [rsp+160h+var_E8], r15
0x18008033c  mov     [rbp+60h+var_E0], r15
0x180080340  mov     [rbp+60h+var_D8], r15d
0x180080344  lea     r12, ??_7CDACL@@6B@; const CDACL::`vftable'
0x18008034b  mov     [rbp+60h+var_A0], r12
0x18008034f  xor     edx, edx; Val
0x180080351  lea     r8d, [r15+50h]; Size
0x180080355  lea     rcx, [rbp+60h+var_98]; void *
0x180080359  call    memset_0
0x18008035e  nop
0x18008035f  lea     r13, ??_7CSACL@@6B@; const CSACL::`vftable'
0x180080366  mov     [rsp+160h+var_110], r13
0x18008036b  mov     [rsp+160h+var_108], r15
0x180080370  mov     [rsp+160h+var_130], r15
0x180080375  mov     [rsp+160h+var_138], r15
0x18008037a  mov     [rsp+160h+var_140], r15
0x18008037f  mov     rcx, r14
0x180080382  call    cs:__imp_?GetNamespace@Provider@@IEAAAEBVCHString@@XZ; Provider::GetNamespace(void)
0x180080388  mov     rcx, rax
0x18008038b  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x180080391  mov     rbx, rax
0x180080394  lea     rcx, [rsp+160h+var_140]
0x180080399  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(void)
0x18008039e  mov     [rsp+160h+var_140], r15
0x1800803a3  mov     rcx, rsi
0x1800803a6  call    cs:__imp_?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ; CInstance::GetMethodContext(void)
0x1800803ac  mov     r9, rbx
0x1800803af  lea     r8, [rsp+160h+var_140]
0x1800803b4  lea     rdx, aWin32Securityd; "Win32_SecurityDescriptor"
0x1800803bb  mov     rcx, rax
0x1800803be  call    cs:__imp_?GetEmptyInstance@CWbemProviderGlue@@SAJPEAVMethodContext@@PEBGPEAPEAVCInstance@@1@Z; CWbemProviderGlue::GetEmptyInstance(MethodContext *,ushort const *,CInstance * *,ushort const *)
0x1800803c4  mov     ebx, eax
0x1800803c6  test    eax, eax
0x1800803c8  js      loc_180080706
0x1800803ce  lea     r8, [rsp+160h+var_118]
0x1800803d3  lea     rdx, aName; "Name"
0x1800803da  mov     rcx, rsi
0x1800803dd  call    cs:__imp_?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z; CInstance::GetCHString(ushort const *,CHString &)
0x1800803e3  test    al, al
0x1800803e5  jnz     short loc_180080402
0x1800803e7  mov     r8d, 8004100Fh
0x1800803ed  lea     rdx, aReturnvalue; "ReturnValue"
0x1800803f4  mov     rcx, rdi
0x1800803f7  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x1800803fd  jmp     loc_180080561
0x180080402  lea     rcx, [rsp+160h+var_128]; this
0x180080407  call    ??0CSecurityInfo@@QEAA@XZ; CSecurityInfo::CSecurityInfo(void)
0x18008040c  nop
0x18008040d  lea     rcx, [rsp+160h+var_118]
0x180080412  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x180080418  mov     rdx, rax; unsigned __int16 *
0x18008041b  lea     rcx, [rsp+160h+var_128]; this
0x180080420  call    ?Initialize@CSecurityInfo@@QEAAJPEBGW4_SE_OBJECT_TYPE@@K@Z; CSecurityInfo::Initialize(ushort const *,_SE_OBJECT_TYPE,ulong)
0x180080425  mov     ebx, eax
0x180080427  test    eax, eax
0x180080429  jns     short loc_18008045F
0x18008042b  mov     r8d, eax
0x18008042e  lea     rdx, aReturnvalue; "ReturnValue"
0x180080435  mov     rcx, rdi
0x180080438  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x18008043e  cmp     ebx, 80041006h
0x180080444  jz      short loc_180080450
0x180080446  cmp     ebx, 80070008h
0x18008044c  cmovnz  ebx, r15d
0x180080450  lea     rcx, [rsp+160h+var_128]; this
0x180080455  call    ??1CSecurityInfo@@QEAA@XZ; CSecurityInfo::~CSecurityInfo(void)
0x18008045a  jmp     loc_18008071A
0x18008045f  mov     rax, [rsp+160h+var_128]
0x180080464  movzx   ebx, word ptr [rax+30h]
0x180080468  lea     rcx, [rsp+160h+var_140]
0x18008046d  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x180080472  mov     r8d, ebx
0x180080475  lea     rdx, aControlflags; "ControlFlags"
0x18008047c  mov     rcx, rax
0x18008047f  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x180080485  lea     rdx, [rbp+60h+pSid]; struct CSid *
0x180080489  mov     rcx, [rsp+160h+var_128]; this
0x18008048e  call    ?GetOwner@CSecurityDescriptor@@QEAAXAEAVCSid@@@Z; CSecurityDescriptor::GetOwner(CSid &)
0x180080493  mov     rcx, [rbp+60h+pSid]; pSid
0x180080497  test    rcx, rcx
0x18008049a  jz      loc_180080569
0x1800804a0  call    cs:__imp_IsValidSid
0x1800804a6  test    eax, eax
0x1800804a8  jz      loc_180080569
0x1800804ae  mov     rcx, r14
0x1800804b1  call    cs:__imp_?GetNamespace@Provider@@IEAAAEBVCHString@@XZ; Provider::GetNamespace(void)
0x1800804b7  mov     rcx, rax
0x1800804ba  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x1800804c0  mov     rbx, rax
0x1800804c3  lea     rcx, [rsp+160h+var_130]
0x1800804c8  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(void)
0x1800804cd  mov     [rsp+160h+var_130], r15
0x1800804d2  mov     rcx, rsi
0x1800804d5  call    cs:__imp_?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ; CInstance::GetMethodContext(void)
0x1800804db  mov     r9, rbx
0x1800804de  lea     r8, [rsp+160h+var_130]
0x1800804e3  lea     rdx, aWin32Trustee; "Win32_Trustee"
0x1800804ea  mov     rcx, rax
0x1800804ed  call    cs:__imp_?GetEmptyInstance@CWbemProviderGlue@@SAJPEAVMethodContext@@PEBGPEAPEAVCInstance@@1@Z; CWbemProviderGlue::GetEmptyInstance(MethodContext *,ushort const *,CInstance * *,ushort const *)
0x1800804f3  test    eax, eax
0x1800804f5  js      short loc_180080569
0x1800804f7  lea     rdx, [rbp+60h+pSid]; struct CSid *
0x1800804fb  mov     rcx, [rsp+160h+var_130]; struct CInstance *
0x180080500  call    ?FillTrusteeFromSid@@YAXPEAVCInstance@@AEAVCSid@@@Z; FillTrusteeFromSid(CInstance *,CSid &)
0x180080505  lea     rcx, [rsp+160h+var_140]
0x18008050a  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x18008050f  mov     rbx, rax
0x180080512  lea     rcx, [rsp+160h+var_130]
0x180080517  call    ??C?$_com_ptr_t@V?$_com_IIID@VCIRQDescriptor@@$1?_GUID_cb0e0537_d375_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCIRQDescriptor@@XZ; _com_ptr_t<_com_IIID<CIRQDescriptor,&__s_GUID const _GUID_cb0e0537_d375_11d2_b35e_00104bc97924>>::operator->(void)
0x18008051c  mov     r8, rax
0x18008051f  lea     rdx, aOwner; "Owner"
0x180080526  mov     rcx, rbx
0x180080529  call    cs:__imp_?SetEmbeddedObject@CInstance@@QEAA_NPEBGAEAV1@@Z; CInstance::SetEmbeddedObject(ushort const *,CInstance &)
0x18008052f  test    al, al
0x180080531  jnz     short loc_180080569
0x180080533  call    cs:__imp_GetLastError
0x180080539  mov     ecx, 80041001h
0x18008053e  test    eax, eax
0x180080540  cmovz   eax, ecx
0x180080543  mov     r8d, eax
0x180080546  lea     rdx, aReturnvalue; "ReturnValue"
0x18008054d  mov     rcx, rdi
0x180080550  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x180080556  nop
0x180080557  lea     rcx, [rsp+160h+var_128]; this
0x18008055c  call    ??1CSecurityInfo@@QEAA@XZ; CSecurityInfo::~CSecurityInfo(void)
0x180080561  mov     ebx, r15d
0x180080564  jmp     loc_18008071A
0x180080569  lea     rdx, [rsp+160h+var_100]; struct CSid *
0x18008056e  mov     rcx, [rsp+160h+var_128]; this
0x180080573  call    ?GetGroup@CSecurityDescriptor@@QEAAXAEAVCSid@@@Z; CSecurityDescriptor::GetGroup(CSid &)
0x180080578  mov     rcx, [rsp+160h+var_100]; pSid
0x18008057d  test    rcx, rcx
0x180080580  jz      loc_18008061E
0x180080586  call    cs:__imp_IsValidSid
0x18008058c  test    eax, eax
0x18008058e  jz      loc_18008061E
0x180080594  mov     rcx, r14
0x180080597  call    cs:__imp_?GetNamespace@Provider@@IEAAAEBVCHString@@XZ; Provider::GetNamespace(void)
0x18008059d  mov     rcx, rax
0x1800805a0  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x1800805a6  mov     rbx, rax
0x1800805a9  lea     rcx, [rsp+160h+var_138]
0x1800805ae  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(void)
0x1800805b3  mov     [rsp+160h+var_138], r15
0x1800805b8  mov     rcx, rsi
0x1800805bb  call    cs:__imp_?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ; CInstance::GetMethodContext(void)
0x1800805c1  mov     r9, rbx
0x1800805c4  lea     r8, [rsp+160h+var_138]
0x1800805c9  lea     rdx, aWin32Trustee; "Win32_Trustee"
0x1800805d0  mov     rcx, rax
0x1800805d3  call    cs:__imp_?GetEmptyInstance@CWbemProviderGlue@@SAJPEAVMethodContext@@PEBGPEAPEAVCInstance@@1@Z; CWbemProviderGlue::GetEmptyInstance(MethodContext *,ushort const *,CInstance * *,ushort const *)
0x1800805d9  test    eax, eax
0x1800805db  js      short loc_18008061E
0x1800805dd  lea     rdx, [rsp+160h+var_100]; struct CSid *
0x1800805e2  mov     rcx, [rsp+160h+var_138]; struct CInstance *
0x1800805e7  call    ?FillTrusteeFromSid@@YAXPEAVCInstance@@AEAVCSid@@@Z; FillTrusteeFromSid(CInstance *,CSid &)
0x1800805ec  lea     rcx, [rsp+160h+var_140]
0x1800805f1  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x1800805f6  mov     rbx, rax
0x1800805f9  lea     rcx, [rsp+160h+var_138]
0x1800805fe  call    ??C?$_com_ptr_t@V?$_com_IIID@VCIRQDescriptor@@$1?_GUID_cb0e0537_d375_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCIRQDescriptor@@XZ; _com_ptr_t<_com_IIID<CIRQDescriptor,&__s_GUID const _GUID_cb0e0537_d375_11d2_b35e_00104bc97924>>::operator->(void)
0x180080603  mov     r8, rax
0x180080606  lea     rdx, aGroup; "Group"
0x18008060d  mov     rcx, rbx
0x180080610  call    cs:__imp_?SetEmbeddedObject@CInstance@@QEAA_NPEBGAEAV1@@Z; CInstance::SetEmbeddedObject(ushort const *,CInstance &)
0x180080616  test    al, al
0x180080618  jz      loc_180080533
0x18008061e  lea     rdx, [rbp+60h+var_A0]; struct CDACL *
0x180080622  mov     rcx, [rsp+160h+var_128]; this
0x180080627  call    ?GetDACL@CSecurityDescriptor@@QEAA_NAEAVCDACL@@@Z; CSecurityDescriptor::GetDACL(CDACL &)
0x18008062c  lea     rdx, [rbp+60h+var_A0]; struct CDACL *
0x180080630  mov     rcx, [rsp+160h+var_140]; struct CInstance *
0x180080635  call    ?FillInstanceDACL@@YAXPEAVCInstance@@AEAVCDACL@@@Z; FillInstanceDACL(CInstance *,CDACL &)
0x18008063a  lea     rdx, [rsp+160h+var_110]; struct CSACL *
0x18008063f  mov     rcx, [rsp+160h+var_128]; this
0x180080644  call    ?GetSACL@CSecurityDescriptor@@QEAA_NAEAVCSACL@@@Z; CSecurityDescriptor::GetSACL(CSACL &)
0x180080649  lea     rdx, [rsp+160h+var_110]; struct CSACL *
0x18008064e  mov     rcx, [rsp+160h+var_140]; struct CInstance *
0x180080653  call    ?FillInstanceSACL@@YAXPEAVCInstance@@AEAVCSACL@@@Z; FillInstanceSACL(CInstance *,CSACL &)
0x180080658  lea     rcx, [rsp+160h+var_140]
0x18008065d  call    ??C?$_com_ptr_t@V?$_com_IIID@VCIRQDescriptor@@$1?_GUID_cb0e0537_d375_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCIRQDescriptor@@XZ; _com_ptr_t<_com_IIID<CIRQDescriptor,&__s_GUID const _GUID_cb0e0537_d375_11d2_b35e_00104bc97924>>::operator->(void)
0x180080662  mov     r8, rax
0x180080665  lea     rdx, aDescriptor; "Descriptor"
0x18008066c  mov     rcx, rdi
0x18008066f  call    cs:__imp_?SetEmbeddedObject@CInstance@@QEAA_NPEBGAEAV1@@Z; CInstance::SetEmbeddedObject(ushort const *,CInstance &)
0x180080675  test    al, al
0x180080677  jnz     short loc_180080684
0x180080679  call    cs:__imp_GetLastError
0x18008067f  jmp     loc_180080543
0x180080684  xor     r8d, r8d
0x180080687  lea     rdx, aReturnvalue; "ReturnValue"
0x18008068e  mov     rcx, rdi
0x180080691  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x180080697  nop
0x180080698  lea     rcx, [rsp+160h+var_128]; this
0x18008069d  call    ??1CSecurityInfo@@QEAA@XZ; CSecurityInfo::~CSecurityInfo(void)
0x1800806a2  nop
0x1800806a3  lea     rcx, [rsp+160h+var_140]
0x1800806a8  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(void)
0x1800806ad  nop
0x1800806ae  lea     rcx, [rsp+160h+var_138]
0x1800806b3  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(void)
0x1800806b8  nop
0x1800806b9  lea     rcx, [rsp+160h+var_130]
0x1800806be  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(void)
0x1800806c3  nop
0x1800806c4  mov     [rsp+160h+var_110], r13
0x1800806c9  lea     rcx, [rsp+160h+var_110]; this
0x1800806ce  call    ?Clear@CSACL@@QEAAXXZ; CSACL::Clear(void)
0x1800806d3  nop
0x1800806d4  mov     [rbp+60h+var_A0], r12
0x1800806d8  lea     rcx, [rbp+60h+var_A0]; this
0x1800806dc  call    ?Clear@CDACL@@QEAAXXZ; CDACL::Clear(void)
0x1800806e1  nop
0x1800806e2  lea     rcx, [rsp+160h+var_100]; this
0x1800806e7  call    ??1CSid@@QEAA@XZ; CSid::~CSid(void)
0x1800806ec  nop
0x1800806ed  lea     rcx, [rbp+60h+pSid]; this
0x1800806f1  call    ??1CSid@@QEAA@XZ; CSid::~CSid(void)
0x1800806f6  nop
0x1800806f7  lea     rcx, [rsp+160h+var_118]
0x1800806fc  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x180080702  xor     eax, eax
0x180080704  jmp     short loc_180080782
0x180080706  mov     r8d, eax
0x180080709  lea     rdx, aReturnvalue; "ReturnValue"
0x180080710  mov     rcx, rdi
0x180080713  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x180080719  nop
0x18008071a  lea     rcx, [rsp+160h+var_140]
0x18008071f  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(void)
0x180080724  nop
0x180080725  lea     rcx, [rsp+160h+var_138]
0x18008072a  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(void)
0x18008072f  nop
0x180080730  lea     rcx, [rsp+160h+var_130]
0x180080735  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(void)
0x18008073a  nop
0x18008073b  mov     [rsp+160h+var_110], r13
0x180080740  lea     rcx, [rsp+160h+var_110]; this
0x180080745  call    ?Clear@CSACL@@QEAAXXZ; CSACL::Clear(void)
0x18008074a  nop
0x18008074b  mov     [rbp+60h+var_A0], r12
0x18008074f  lea     rcx, [rbp+60h+var_A0]; this
0x180080753  call    ?Clear@CDACL@@QEAAXXZ; CDACL::Clear(void)
0x180080758  nop
0x180080759  lea     rcx, [rsp+160h+var_100]; this
0x18008075e  call    ??1CSid@@QEAA@XZ; CSid::~CSid(void)
0x180080763  nop
0x180080764  lea     rcx, [rbp+60h+pSid]; this
0x180080768  call    ??1CSid@@QEAA@XZ; CSid::~CSid(void)
0x18008076d  nop
0x18008076e  lea     rcx, [rsp+160h+var_118]
0x180080773  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x180080779  mov     eax, ebx
0x18008077b  jmp     short loc_180080782
0x18008077d  mov     eax, 80041008h
0x180080782  add     rsp, 128h
0x180080789  pop     r15
0x18008078b  pop     r14
0x18008078d  pop     r13
0x18008078f  pop     r12
0x180080791  pop     rdi
0x180080792  pop     rsi
0x180080793  pop     rbx
0x180080794  pop     rbp
0x180080795  retn
```
