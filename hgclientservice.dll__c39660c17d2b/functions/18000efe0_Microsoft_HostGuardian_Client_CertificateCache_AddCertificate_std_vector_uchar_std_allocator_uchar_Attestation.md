# Microsoft::HostGuardian::Client::CertificateCache::AddCertificate(std::vector<uchar,std::allocator<uchar>>,AttestationResultType,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,ShsAttestationFlag)

- ea: `0x18000efe0`
- end: `0x18000f1a3`
- name: `?AddCertificate@CertificateCache@Client@HostGuardian@Microsoft@@QEAAXV?$vector@EV?$allocator@E@std@@@std@@W4AttestationResultType@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@6@W4ShsAttestationFlag@@@Z`
- size: `451`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c8ec`

## callees

- `0x180001770`
- `0x180003e18`
- `0x180003e24`
- `0x180003e30`
- `0x180004274`
- `0x180008760`
- `0x18000a7bc`
- `0x18000b8b0`
- `0x18000c45c`
- `0x18000e7cc`
- `0x18000efe0`
- `0x18000f1ac`
- `0x180014e74`

## import_xrefs

- `CRYPT32!CertFreeCertificateContext` at `0x18000f0f1`
- `CRYPT32!CertFreeCertificateContext` at `0x18000f0f1`
- `CRYPT32!CertCreateCertificateContext` at `0x18000f04c`
- `CRYPT32!CertCreateCertificateContext` at `0x18000f04c`

## string_xrefs

- `0x18000f140`: `servercommon\base\securehostingservice\common\service\lib\hgcertificatecache.cpp`
- `0x18000f167`: `servercommon\base\securehostingservice\common\service\lib\hgcertificatecache.cpp`
- `0x18000f17f`: `servercommon\base\securehostingservice\common\service\lib\hgcertificatecache.cpp`
- `0x18000f191`: `servercommon\base\securehostingservice\common\service\lib\hgcertificatecache.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::CertificateCache::AddCertificate(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        int a5)
{
  __int64 v9; // r8
  PCCERT_CONTEXT CertificateContext; // rax
  const char *v12; // r9
  const CERT_CONTEXT *v13; // rsi
  __int64 v14; // rcx
  FILETIME NotAfter; // rbx
  __int64 v16; // rdi
  _QWORD *v17; // rax
  unsigned int v19; // eax
  unsigned int v20; // eax
  int v21; // [rsp+20h] [rbp-B8h]
  PCCERT_CONTEXT v22; // [rsp+30h] [rbp-A8h] BYREF
  __int64 v23; // [rsp+38h] [rbp-A0h]
  _QWORD v24[3]; // [rsp+50h] [rbp-88h] BYREF
  _BYTE v25[32]; // [rsp+68h] [rbp-70h] BYREF
  __int64 v26; // [rsp+88h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v23 = a2;
  v26 = a4;
  v9 = *(_QWORD *)(a2 + 8);
  if ( *(_QWORD *)a2 == v9 || !*(_QWORD *)(a4 + 16) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x97,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgcertificatecache.cpp",
      (const char *)0x80070057LL,
      v21);
  CertificateContext = CertCreateCertificateContext(0x10001u, *(const BYTE **)a2, (int)v9 - *(_DWORD *)a2);
  v13 = CertificateContext;
  v22 = CertificateContext;
  if ( !CertificateContext )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x9D,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgcertificatecache.cpp",
      v12);
  if ( (unsigned int)Microsoft::HostGuardian::Client::Utilities::GetCertificateDurationStatus(CertificateContext) != 1 )
  {
    LOBYTE(v14) = *(_QWORD *)(wil::unique_any_t<wil::cert_context_t>::get(&v22) + 24) == 0;
    if ( !(unsigned __int8)wil::verify_bool<bool,0>(v14) )
    {
      v19 = wil::verify_hresult<long>(2148204801LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAC,
        (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgcertificatecache.cpp",
        (const char *)v19,
        v21);
    }
    v20 = wil::verify_hresult<long>(2148204808LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgcertificatecache.cpp",
      (const char *)v20,
      v21);
  }
  NotAfter = v13->pCertInfo->NotAfter;
  v16 = std::wstring::wstring((__int64)v25, a4);
  v17 = std::vector<unsigned char>::vector<unsigned char>(v24, a2);
  ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD, _QWORD))Microsoft::HostGuardian::Client::CertificateCache::AddCertificateInternal)(
    a1,
    v17,
    a3,
    v16,
    a5,
    NotAfter,
    v22,
    v23,
    v25);
  CertFreeCertificateContext(v13);
  std::vector<unsigned char>::~vector<unsigned char>((char **)a2);
  return std::wstring::~wstring((char **)a4);
}

```

## disassembly

```asm
0x18000efe0  mov     r11, rsp
0x18000efe3  push    rbx
0x18000efe4  push    rbp
0x18000efe5  push    rsi
0x18000efe6  push    rdi
0x18000efe7  push    r12
0x18000efe9  push    r14
0x18000efeb  push    r15
0x18000efed  sub     rsp, 0A0h
0x18000eff4  mov     rax, cs:__security_cookie
0x18000effb  xor     rax, rsp
0x18000effe  mov     [rsp+0D8h+var_48], rax
0x18000f006  mov     rbp, r9
0x18000f009  mov     r12d, r8d
0x18000f00c  mov     r14, rdx
0x18000f00f  mov     r15, rcx
0x18000f012  mov     [rsp+0D8h+var_A0], rdx
0x18000f017  mov     [r11-50h], r9
0x18000f01b  mov     r8, [rdx+8]
0x18000f01f  cmp     [rdx], r8
0x18000f022  jz      short loc_18000F02F
0x18000f024  cmp     qword ptr [r9+10h], 0
0x18000f029  jz      short loc_18000F02F
0x18000f02b  xor     al, al
0x18000f02d  jmp     short loc_18000F031
0x18000f02f  mov     al, 1
0x18000f031  mov     rcx, [rsp+0D8h]; this
0x18000f039  test    al, al
0x18000f03b  jnz     loc_18000F179
0x18000f041  sub     r8d, [rdx]; cbCertEncoded
0x18000f044  mov     rdx, [rdx]; pbCertEncoded
0x18000f047  mov     ecx, 10001h; dwCertEncodingType
0x18000f04c  call    cs:__imp_CertCreateCertificateContext
0x18000f052  mov     rsi, rax
0x18000f055  mov     [rsp+0D8h+var_A8], rax
0x18000f05a  mov     rcx, [rsp+0D8h]; this
0x18000f062  test    rax, rax
0x18000f065  jz      loc_18000F191
0x18000f06b  mov     rcx, rax
0x18000f06e  call    ?GetCertificateDurationStatus@Utilities@Client@HostGuardian@Microsoft@@YA?AW4DurationStatus@1234@PEBU_CERT_CONTEXT@@@Z; Microsoft::HostGuardian::Client::Utilities::GetCertificateDurationStatus(_CERT_CONTEXT const *)
0x18000f073  cmp     eax, 1
0x18000f076  jz      short loc_18000F09C
0x18000f078  lea     rcx, [rsp+0D8h+var_A8]
0x18000f07d  call    ?get@?$unique_any_t@Ucert_context_t@wil@@@wil@@QEBAPEBU_CERT_CONTEXT@@XZ; wil::unique_any_t<wil::cert_context_t>::get(void)
0x18000f082  cmp     qword ptr [rax+18h], 0
0x18000f087  setz    cl
0x18000f08a  call    ??$verify_bool@_N$0A@@wil@@YA_N_N@Z; wil::verify_bool<bool,0>(bool)
0x18000f08f  test    al, al
0x18000f091  jnz     loc_18000F152
0x18000f097  jmp     loc_18000F12B
0x18000f09c  mov     rbx, [rsi+18h]
0x18000f0a0  mov     rbx, [rbx+48h]
0x18000f0a4  lea     rax, [rsp+0D8h+var_70]
0x18000f0a9  mov     [rsp+0D8h+var_98], rax
0x18000f0ae  mov     rdx, rbp
0x18000f0b1  lea     rcx, [rsp+0D8h+var_70]
0x18000f0b6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000f0bb  mov     rdi, rax
0x18000f0be  mov     rdx, r14
0x18000f0c1  lea     rcx, [rsp+0D8h+var_88]
0x18000f0c6  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x18000f0cb  nop
0x18000f0cc  mov     [rsp+0D8h+var_B0], rbx
0x18000f0d1  mov     edx, [rsp+0D8h+arg_20]
0x18000f0d8  mov     [rsp+0D8h+var_B8], edx
0x18000f0dc  mov     r9, rdi
0x18000f0df  mov     r8d, r12d
0x18000f0e2  mov     rdx, rax
0x18000f0e5  mov     rcx, r15
0x18000f0e8  call    ?AddCertificateInternal@CertificateCache@Client@HostGuardian@Microsoft@@AEAAXV?$vector@EV?$allocator@E@std@@@std@@W4AttestationResultType@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@6@W4ShsAttestationFlag@@U_FILETIME@@@Z; Microsoft::HostGuardian::Client::CertificateCache::AddCertificateInternal(std::vector<uchar>,AttestationResultType,std::wstring,ShsAttestationFlag,_FILETIME)
0x18000f0ed  nop
0x18000f0ee  mov     rcx, rsi; pCertContext
0x18000f0f1  call    cs:__imp_CertFreeCertificateContext
0x18000f0f7  nop
0x18000f0f8  mov     rcx, r14
0x18000f0fb  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000f100  nop
0x18000f101  mov     rcx, rbp
0x18000f104  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f109  mov     rcx, [rsp+0D8h+var_48]
0x18000f111  xor     rcx, rsp; StackCookie
0x18000f114  call    __security_check_cookie
0x18000f119  add     rsp, 0A0h
0x18000f120  pop     r15
0x18000f122  pop     r14
0x18000f124  pop     r12
0x18000f126  pop     rdi
0x18000f127  pop     rsi
0x18000f128  pop     rbp
0x18000f129  pop     rbx
0x18000f12a  retn
0x18000f12b  mov     ecx, 800B0101h
0x18000f130  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18000f135  mov     r9d, eax; char *
0x18000f138  mov     rcx, [rsp+0D8h]; this
0x18000f140  lea     r8, aServercommonBa_8; "servercommon\\base\\securehostingservic"...
0x18000f147  mov     edx, 0ACh; void *
0x18000f14c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000f152  mov     ecx, 800B0108h
0x18000f157  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18000f15c  mov     r9d, eax; char *
0x18000f15f  mov     rcx, [rsp+0D8h]; this
0x18000f167  lea     r8, aServercommonBa_8; "servercommon\\base\\securehostingservic"...
0x18000f16e  mov     edx, 0ABh; void *
0x18000f173  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000f179  mov     r9d, 80070057h; char *
0x18000f17f  lea     r8, aServercommonBa_8; "servercommon\\base\\securehostingservic"...
0x18000f186  mov     edx, 97h; void *
0x18000f18b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000f191  lea     r8, aServercommonBa_8; "servercommon\\base\\securehostingservic"...
0x18000f198  mov     edx, 9Dh; void *
0x18000f19d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
