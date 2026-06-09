# CCertificate::Install(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x1800248f4`
- end: `0x180024b15`
- name: `?Install@CCertificate@@QEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `545`
- prototype: `__int64 __fastcall(CCertificate *this)`
- caller_count: `14`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x180018358`
- `0x180018544`
- `0x180018730`
- `0x18001891c`
- `0x1800731a8`
- `0x180073394`
- `0x180073580`
- `0x18007376c`
- `0x180073958`
- `0x180073b44`
- `0x180073d30`
- `0x180073f1c`
- `0x180074108`
- `0x1800742f4`

## callees

- `0x180008de0`
- `0x18000f0c8`
- `0x180015804`
- `0x18002031c`
- `0x180023664`
- `0x180023874`
- `0x180023b58`
- `0x180023f6c`
- `0x180023fbc`
- `0x180024208`
- `0x1800248f4`
- `0x180107010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180024a64`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180024a64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800249f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800249f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024acb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024acb`
- `CRYPT32!CertCreateCertificateContext` at `0x1800249e0`
- `CRYPT32!CertCreateCertificateContext` at `0x1800249e0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18002493a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18002493a`
- `DMCmnUtils!DecodeBase64W` at `0x18002499e`
- `DMCmnUtils!DecodeBase64W` at `0x18002499e`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CCertificate::Install(CCertificate *this, __int64 a2)
{
  __int64 v4; // rax
  const unsigned __int16 *v5; // rax
  int v6; // eax
  PCCERT_CONTEXT CertificateContext; // rbx
  signed int LastError; // eax
  int UniqueId; // eax
  __int64 v10; // rax
  __int64 v11; // rdx
  _QWORD *Location; // rax
  int v14; // [rsp+20h] [rbp-39h] BYREF
  DWORD cbCertEncoded; // [rsp+24h] [rbp-35h] BYREF
  BYTE *pbCertEncoded; // [rsp+28h] [rbp-31h] BYREF
  __int128 v17; // [rsp+30h] [rbp-29h] BYREF
  __int64 v18; // [rsp+40h] [rbp-19h]
  char v19; // [rsp+48h] [rbp-11h]
  BYTE **p_pbCertEncoded; // [rsp+50h] [rbp-9h]
  char v21; // [rsp+58h] [rbp-1h]
  _BYTE v22[24]; // [rsp+60h] [rbp+7h] BYREF
  __int64 v23; // [rsp+78h] [rbp+1Fh]
  struct _SYSTEMTIME SystemTime; // [rsp+80h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v23 = a2;
  if ( !*((_QWORD *)this + 11) )
  {
    LOBYTE(v14) = 0;
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    v4 = lambda_bce58cd8b035bea36c4cb65f8e5b1b5c_::_lambda_bce58cd8b035bea36c4cb65f8e5b1b5c_(
           v22,
           &v14,
           &SystemTime,
           this);
    v17 = *(_OWORD *)v4;
    v18 = *(_QWORD *)(v4 + 16);
    v19 = 1;
    std::wstring::operator=((char *)this + 24, a2);
    pbCertEncoded = 0;
    cbCertEncoded = 0;
    v5 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 24);
    v6 = DecodeBase64W(v5, &pbCertEncoded, (int *)&cbCertEncoded);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x56,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\certificatecore\\certificate.cpp",
        (const char *)(unsigned int)v6,
        v14);
    p_pbCertEncoded = &pbCertEncoded;
    v21 = 1;
    CertificateContext = CertCreateCertificateContext(1u, pbCertEncoded, cbCertEncoded);
    *((_QWORD *)this + 11) = CertificateContext;
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( !CertificateContext )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5F,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\certificatecore\\certificate.cpp",
        (const char *)(unsigned int)LastError,
        v14);
    UniqueId = CCertificate::GenerateUniqueId(this);
    if ( UniqueId < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x62,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\certificatecore\\certificate.cpp",
        (const char *)(unsigned int)UniqueId,
        v14);
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 56);
    v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 56);
    if ( (unsigned int)_o__wcsicmp(v10, v11) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x67,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\certificatecore\\certificate.cpp",
        (const char *)0x80070057LL,
        v14);
    Location = (_QWORD *)CCertificateStore::GetLocation(*((_QWORD *)this + 1), v22);
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*Location + 8LL))(
      *Location,
      *(_QWORD *)(*((_QWORD *)this + 1) + 40LL),
      *((_QWORD *)this + 11));
    std::_Ptr_base<Dynamo::SyncmlPackProcessor>::_Decref(v22);
    LOBYTE(v14) = 1;
    LocalFree(pbCertEncoded);
    pbCertEncoded = 0;
    v19 = 0;
    lambda_8752aa6ba05ca6e6280601a98d58c600_::operator()(&v17);
  }
  return std::wstring::~wstring(a2);
}

```

## disassembly

```asm
0x1800248f4  mov     [rsp-8+arg_10], rbx
0x1800248f9  push    rbp
0x1800248fa  push    rsi
0x1800248fb  push    rdi
0x1800248fc  lea     rbp, [rsp-47h]
0x180024901  sub     rsp, 0A0h
0x180024908  mov     rax, cs:__security_cookie
0x18002490f  xor     rax, rsp
0x180024912  mov     [rbp+57h+var_20], rax
0x180024916  mov     rsi, rdx
0x180024919  mov     rdi, rcx
0x18002491c  mov     [rbp+57h+var_38], rdx
0x180024920  cmp     qword ptr [rcx+58h], 0
0x180024925  jnz     loc_180024AED
0x18002492b  mov     byte ptr [rbp+57h+var_90], 0
0x18002492f  xorps   xmm0, xmm0
0x180024932  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180024936  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18002493a  call    cs:__imp_GetSystemTime
0x180024941  nop     dword ptr [rax+rax+00h]
0x180024946  mov     r9, rdi
0x180024949  lea     r8, [rbp+57h+SystemTime]
0x18002494d  lea     rdx, [rbp+57h+var_90]
0x180024951  lea     rcx, [rbp+57h+var_50]
0x180024955  call    _lambda_bce58cd8b035bea36c4cb65f8e5b1b5c____lambda_bce58cd8b035bea36c4cb65f8e5b1b5c_
0x18002495a  movups  xmm0, xmmword ptr [rax]
0x18002495d  movups  [rbp+57h+var_80], xmm0
0x180024961  movsd   xmm1, qword ptr [rax+10h]
0x180024966  movsd   [rbp+57h+var_70], xmm1
0x18002496b  mov     [rbp+57h+var_68], 1
0x18002496f  mov     rdx, rsi
0x180024972  lea     rcx, [rdi+18h]
0x180024976  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002497b  mov     [rbp+57h+pbCertEncoded], 0
0x180024983  mov     [rbp+57h+cbCertEncoded], 0
0x18002498a  lea     rcx, [rdi+18h]
0x18002498e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180024993  lea     r8, [rbp+57h+cbCertEncoded]
0x180024997  lea     rdx, [rbp+57h+pbCertEncoded]
0x18002499b  mov     rcx, rax
0x18002499e  call    cs:__imp_?DecodeBase64W@@YAJQEBGPEAPEAEPEAH@Z; DecodeBase64W(ushort const * const,uchar * *,int *)
0x1800249a5  nop     dword ptr [rax+rax+00h]
0x1800249aa  mov     rcx, [rbp+5Fh]; this
0x1800249ae  test    eax, eax
0x1800249b0  jns     short loc_1800249C7
0x1800249b2  mov     r9d, eax; char *
0x1800249b5  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800249bc  mov     edx, 56h ; 'V'; void *
0x1800249c1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800249c7  lea     rax, [rbp+57h+pbCertEncoded]
0x1800249cb  mov     [rbp+57h+var_60], rax
0x1800249cf  mov     [rbp+57h+var_58], 1
0x1800249d3  mov     r8d, [rbp+57h+cbCertEncoded]; cbCertEncoded
0x1800249d7  mov     rdx, [rbp+57h+pbCertEncoded]; pbCertEncoded
0x1800249db  mov     ecx, 1; dwCertEncodingType
0x1800249e0  call    cs:__imp_CertCreateCertificateContext
0x1800249e7  nop     dword ptr [rax+rax+00h]
0x1800249ec  mov     rbx, rax
0x1800249ef  mov     [rdi+58h], rax
0x1800249f3  call    cs:__imp_GetLastError
0x1800249fa  nop     dword ptr [rax+rax+00h]
0x1800249ff  test    eax, eax
0x180024a01  jle     short loc_180024A0B
0x180024a03  movzx   eax, ax
0x180024a06  or      eax, 80070000h
0x180024a0b  mov     rcx, [rbp+5Fh]; this
0x180024a0f  test    rbx, rbx
0x180024a12  jnz     short loc_180024A27
0x180024a14  mov     r9d, eax; char *
0x180024a17  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180024a1e  lea     edx, [rbx+5Fh]; void *
0x180024a21  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180024a27  mov     rcx, rdi; this
0x180024a2a  call    ?GenerateUniqueId@CCertificate@@AEAAJXZ; CCertificate::GenerateUniqueId(void)
0x180024a2f  mov     rcx, [rbp+5Fh]; this
0x180024a33  test    eax, eax
0x180024a35  jns     short loc_180024A4C
0x180024a37  mov     r9d, eax; char *
0x180024a3a  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180024a41  mov     edx, 62h ; 'b'; void *
0x180024a46  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180024a4c  lea     rcx, [rdi+38h]
0x180024a50  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180024a55  mov     rdx, rax
0x180024a58  lea     rcx, [rdi+38h]
0x180024a5c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180024a61  mov     rcx, rax
0x180024a64  call    cs:__imp__o__wcsicmp
0x180024a6b  nop     dword ptr [rax+rax+00h]
0x180024a70  test    eax, eax
0x180024a72  jz      short loc_180024A90
0x180024a74  mov     rcx, [rbp+5Fh]; this
0x180024a78  mov     r9d, 80070057h; char *
0x180024a7e  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180024a85  mov     edx, 67h ; 'g'; void *
0x180024a8a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180024a90  lea     rdx, [rbp+57h+var_50]
0x180024a94  mov     rcx, [rdi+8]
0x180024a98  call    ?GetLocation@CCertificateStore@@QEAA?AV?$shared_ptr@VCCertificateLocation@@@std@@XZ; CCertificateStore::GetLocation(void)
0x180024a9d  nop
0x180024a9e  mov     rcx, [rax]
0x180024aa1  mov     rax, [rcx]
0x180024aa4  mov     rdx, [rdi+8]
0x180024aa8  mov     r8, [rdi+58h]
0x180024aac  mov     rdx, [rdx+28h]
0x180024ab0  mov     rax, [rax+8]
0x180024ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ab9  nop
0x180024aba  lea     rcx, [rbp+57h+var_50]
0x180024abe  call    ?_Decref@?$_Ptr_base@VSyncmlPackProcessor@Dynamo@@@std@@IEAAXXZ; std::_Ptr_base<Dynamo::SyncmlPackProcessor>::_Decref(void)
0x180024ac3  mov     byte ptr [rbp+57h+var_90], 1
0x180024ac7  mov     rcx, [rbp+57h+pbCertEncoded]; hMem
0x180024acb  call    cs:__imp_LocalFree
0x180024ad2  nop     dword ptr [rax+rax+00h]
0x180024ad7  mov     [rbp+57h+pbCertEncoded], 0
0x180024adf  mov     [rbp+57h+var_68], 0
0x180024ae3  lea     rcx, [rbp+57h+var_80]
0x180024ae7  call    _lambda_8752aa6ba05ca6e6280601a98d58c600___operator__
0x180024aec  nop
0x180024aed  mov     rcx, rsi
0x180024af0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180024af5  mov     rcx, [rbp+57h+var_20]
0x180024af9  xor     rcx, rsp; StackCookie
0x180024afc  call    __security_check_cookie
0x180024b01  mov     rbx, [rsp+0B0h+arg_10]
0x180024b09  add     rsp, 0A0h
0x180024b10  pop     rdi
0x180024b11  pop     rsi
0x180024b12  pop     rbp
0x180024b13  retn
```
