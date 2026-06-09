# Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveCertInfoWithThumbPrint(Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo &,_CERT_CONTEXT const *)

- ea: `0x18013aadc`
- end: `0x18013ada2`
- name: `?RetrieveCertInfoWithThumbPrint@MdmDiagnosticSource@Mdm@Windows@Microsoft@@YAJAEAVCertInfo@1234@PEBU_CERT_CONTEXT@@@Z`
- size: `710`
- prototype: `__int64 __fastcall(Microsoft::Windows::Mdm::MdmDiagnosticSource *__hidden this, struct _CERT_CONTEXT *, const struct _CERT_CONTEXT *)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180129dc8`
- `0x18013a5ec`

## callees

- `0x180019000`
- `0x180019fc4`
- `0x1800e66b8`
- `0x1800e66dc`
- `0x1800ece5c`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x180108060`
- `0x18011150c`
- `0x18013aadc`
- `0x18013ada8`

## import_xrefs

- `CRYPT32!CertFindExtension` at `0x18013ac2f`
- `CRYPT32!CertFindExtension` at `0x18013ac2f`
- `CRYPT32!CertGetNameStringW` at `0x18013ab9b`
- `CRYPT32!CertGetNameStringW` at `0x18013abe6`
- `CRYPT32!CertGetNameStringW` at `0x18013ab9b`
- `CRYPT32!CertGetNameStringW` at `0x18013abe6`
- `CRYPT32!CryptFormatObject` at `0x18013ac7c`
- `CRYPT32!CryptFormatObject` at `0x18013ace7`
- `CRYPT32!CryptFormatObject` at `0x18013ac7c`
- `CRYPT32!CryptFormatObject` at `0x18013ace7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013ab37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013acf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013ab37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013acf1`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18013ab2d`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18013ab2d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
signed int __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveCertInfoWithThumbPrint(
        struct _SYSTEMTIME *this,
        struct _CERT_CONTEXT *a2,
        const struct _CERT_CONTEXT *a3)
{
  signed int result; // eax
  PCERT_EXTENSION Extension; // rbx
  void *pbFormat; // rax
  signed int LastError; // eax
  signed int v9; // ebx
  __int64 v10; // rax
  int pszNameString; // [rsp+20h] [rbp-E0h]
  DWORD pcbFormat; // [rsp+50h] [rbp-B0h] BYREF
  FILETIME FileTime; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v14[32]; // [rsp+60h] [rbp-A0h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v16[32]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR v17[2]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v18[524]; // [rsp+B4h] [rbp-4Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  SystemTime = 0;
  FileTime = a2->pCertInfo->NotAfter;
  if ( FileTimeToSystemTime(&FileTime, &SystemTime) )
  {
    this[10] = SystemTime;
    *(_DWORD *)v17 = 0;
    memset_0(v18, 0, 0x204u);
    pcbFormat = 260;
    CertGetNameStringW(a2, 4u, 0, 0, v17, 0x104u);
    std::wstring::wstring(v14, v17);
    std::wstring::operator=(&this[6], v14);
    std::wstring::_Tidy_deallocate(v14);
    CertGetNameStringW(a2, 4u, 1u, 0, v17, 0x104u);
    std::wstring::wstring(v14, v17);
    std::wstring::operator=(&this[4], v14);
    std::wstring::_Tidy_deallocate(v14);
    Extension = CertFindExtension("2.5.29.37", a2->pCertInfo->cExtension, a2->pCertInfo->rgExtension);
    if ( Extension )
    {
      pcbFormat = 0;
      CryptFormatObject(1u, 0, 0, 0, "2.5.29.37", Extension->Value.pbData, Extension->Value.cbData, 0, &pcbFormat);
      if ( pcbFormat )
      {
        std::wstring::wstring(v14);
        std::wstring::resize(v14, (unsigned __int64)(pcbFormat + 1) >> 1, 0);
        pbFormat = (void *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v14);
        if ( !CryptFormatObject(
                1u,
                0,
                0,
                0,
                "2.5.29.37",
                Extension->Value.pbData,
                Extension->Value.cbData,
                pbFormat,
                &pcbFormat) )
        {
          LastError = GetLastError();
          v9 = LastError;
          if ( LastError > 0 )
            v9 = (unsigned __int16)LastError | 0x80070000;
          if ( v9 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x7F,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\cert.cpp",
              (const char *)(unsigned int)v9,
              pszNameString);
            std::wstring::_Tidy_deallocate(v14);
            return v9;
          }
        }
        v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v14);
        std::wstring::wstring(v16, v10);
        std::wstring::operator=(&this[8], v16);
        std::wstring::_Tidy_deallocate(v16);
        std::wstring::_Tidy_deallocate(v14);
      }
    }
    return Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo::ValidateCertChain(
             (Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo *)this,
             a2);
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18013aadc  mov     [rsp-8+arg_10], rbx
0x18013aae1  mov     [rsp-8+arg_18], rsi
0x18013aae6  push    rbp
0x18013aae7  push    rdi
0x18013aae8  push    r12
0x18013aaea  lea     rbp, [rsp-1D0h]
0x18013aaf2  sub     rsp, 2D0h
0x18013aaf9  mov     rax, cs:__security_cookie
0x18013ab00  xor     rax, rsp
0x18013ab03  mov     [rbp+1E0h+var_20], rax
0x18013ab0a  mov     rsi, rdx
0x18013ab0d  mov     rdi, rcx
0x18013ab10  xorps   xmm0, xmm0
0x18013ab13  movups  xmmword ptr [rbp+1E0h+SystemTime.wYear], xmm0
0x18013ab17  mov     rax, [rdx+18h]
0x18013ab1b  mov     rcx, [rax+48h]
0x18013ab1f  mov     qword ptr [rsp+2E0h+FileTime.dwLowDateTime], rcx
0x18013ab24  lea     rdx, [rbp+1E0h+SystemTime]; lpSystemTime
0x18013ab28  lea     rcx, [rsp+2E0h+FileTime]; lpFileTime
0x18013ab2d  call    cs:__imp_FileTimeToSystemTime
0x18013ab33  test    eax, eax
0x18013ab35  jnz     short loc_18013AB52
0x18013ab37  call    cs:__imp_GetLastError
0x18013ab3d  test    eax, eax
0x18013ab3f  jle     loc_18013AD7B
0x18013ab45  movzx   eax, ax
0x18013ab48  or      eax, 80070000h
0x18013ab4d  jmp     loc_18013AD7B
0x18013ab52  movups  xmm0, xmmword ptr [rbp+1E0h+SystemTime.wYear]
0x18013ab56  movdqu  xmmword ptr [rdi+0A0h], xmm0
0x18013ab5e  mov     dword ptr [rbp+1E0h+var_230], 0
0x18013ab65  xor     edx, edx; Val
0x18013ab67  mov     r8d, 204h; Size
0x18013ab6d  lea     rcx, [rbp+1E0h+var_22C]; void *
0x18013ab71  call    memset_0
0x18013ab76  mov     eax, 104h
0x18013ab7b  mov     [rsp+2E0h+var_290], eax
0x18013ab7f  mov     [rsp+2E0h+cchNameString], eax; cchNameString
0x18013ab83  lea     rax, [rbp+1E0h+var_230]
0x18013ab87  mov     [rsp+2E0h+pszNameString], rax; pszNameString
0x18013ab8c  xor     r9d, r9d; pvTypePara
0x18013ab8f  xor     r8d, r8d; dwFlags
0x18013ab92  lea     ebx, [r9+4]
0x18013ab96  mov     edx, ebx; dwType
0x18013ab98  mov     rcx, rsi; pCertContext
0x18013ab9b  call    cs:__imp_CertGetNameStringW
0x18013aba1  lea     rdx, [rbp+1E0h+var_230]
0x18013aba5  lea     rcx, [rsp+2E0h+var_280]
0x18013abaa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18013abaf  nop
0x18013abb0  lea     rcx, [rdi+60h]
0x18013abb4  lea     rdx, [rsp+2E0h+var_280]
0x18013abb9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18013abbe  nop
0x18013abbf  lea     rcx, [rsp+2E0h+var_280]
0x18013abc4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013abc9  mov     eax, [rsp+2E0h+var_290]
0x18013abcd  mov     [rsp+2E0h+cchNameString], eax; cchNameString
0x18013abd1  lea     rax, [rbp+1E0h+var_230]
0x18013abd5  mov     [rsp+2E0h+pszNameString], rax; pszNameString
0x18013abda  xor     r9d, r9d; pvTypePara
0x18013abdd  lea     r8d, [rbx-3]; dwFlags
0x18013abe1  mov     edx, ebx; dwType
0x18013abe3  mov     rcx, rsi; pCertContext
0x18013abe6  call    cs:__imp_CertGetNameStringW
0x18013abec  lea     rdx, [rbp+1E0h+var_230]
0x18013abf0  lea     rcx, [rsp+2E0h+var_280]
0x18013abf5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18013abfa  nop
0x18013abfb  lea     rcx, [rdi+40h]
0x18013abff  lea     rdx, [rsp+2E0h+var_280]
0x18013ac04  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18013ac09  nop
0x18013ac0a  lea     rcx, [rsp+2E0h+var_280]
0x18013ac0f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013ac14  mov     rdx, [rsi+18h]
0x18013ac18  mov     r8, [rdx+0C8h]; rgExtensions
0x18013ac1f  mov     edx, [rdx+0C0h]; cExtensions
0x18013ac25  lea     r12, szStructType; "2.5.29.37"
0x18013ac2c  mov     rcx, r12; pszObjId
0x18013ac2f  call    cs:__imp_CertFindExtension
0x18013ac35  mov     rbx, rax
0x18013ac38  test    rax, rax
0x18013ac3b  jz      loc_18013AD70
0x18013ac41  mov     [rsp+2E0h+var_290], 0
0x18013ac49  lea     rax, [rsp+2E0h+var_290]
0x18013ac4e  mov     [rsp+2E0h+pcbFormat], rax; pcbFormat
0x18013ac53  mov     [rsp+2E0h+pbFormat], 0; pbFormat
0x18013ac5c  mov     ecx, [rbx+10h]
0x18013ac5f  mov     [rsp+2E0h+cbEncoded], ecx; cbEncoded
0x18013ac63  mov     rcx, [rbx+18h]
0x18013ac67  mov     qword ptr [rsp+2E0h+cchNameString], rcx; pbEncoded
0x18013ac6c  mov     [rsp+2E0h+pszNameString], r12; lpszStructType
0x18013ac71  xor     r9d, r9d; pFormatStruct
0x18013ac74  xor     r8d, r8d; dwFormatStrType
0x18013ac77  xor     edx, edx; dwFormatType
0x18013ac79  lea     ecx, [rdx+1]; dwCertEncodingType
0x18013ac7c  call    cs:__imp_CryptFormatObject
0x18013ac82  cmp     [rsp+2E0h+var_290], 0
0x18013ac87  jbe     loc_18013AD70
0x18013ac8d  lea     rcx, [rsp+2E0h+var_280]
0x18013ac92  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18013ac97  nop
0x18013ac98  xor     r8d, r8d
0x18013ac9b  mov     edx, [rsp+2E0h+var_290]
0x18013ac9f  inc     edx
0x18013aca1  shr     rdx, 1
0x18013aca4  lea     rcx, [rsp+2E0h+var_280]
0x18013aca9  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18013acae  lea     rcx, [rsp+2E0h+var_280]
0x18013acb3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013acb8  lea     rcx, [rsp+2E0h+var_290]
0x18013acbd  mov     [rsp+2E0h+pcbFormat], rcx; pcbFormat
0x18013acc2  mov     [rsp+2E0h+pbFormat], rax; pbFormat
0x18013acc7  mov     eax, [rbx+10h]
0x18013acca  mov     [rsp+2E0h+cbEncoded], eax; cbEncoded
0x18013acce  mov     rax, [rbx+18h]
0x18013acd2  mov     qword ptr [rsp+2E0h+cchNameString], rax; pbEncoded
0x18013acd7  mov     [rsp+2E0h+pszNameString], r12; int
0x18013acdc  xor     r9d, r9d; pFormatStruct
0x18013acdf  xor     r8d, r8d; dwFormatStrType
0x18013ace2  xor     edx, edx; dwFormatType
0x18013ace4  lea     ecx, [rdx+1]; dwCertEncodingType
0x18013ace7  call    cs:__imp_CryptFormatObject
0x18013aced  test    eax, eax
0x18013acef  jnz     short loc_18013AD34
0x18013acf1  call    cs:__imp_GetLastError
0x18013acf7  mov     ebx, eax
0x18013acf9  test    eax, eax
0x18013acfb  jle     short loc_18013AD06
0x18013acfd  movzx   ebx, ax
0x18013ad00  or      ebx, 80070000h
0x18013ad06  test    ebx, ebx
0x18013ad08  jns     short loc_18013AD34
0x18013ad0a  mov     rcx, [rbp+1E8h]; this
0x18013ad11  mov     r9d, ebx; char *
0x18013ad14  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013ad1b  mov     edx, 7Fh; void *
0x18013ad20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013ad25  nop
0x18013ad26  lea     rcx, [rsp+2E0h+var_280]
0x18013ad2b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013ad30  mov     eax, ebx
0x18013ad32  jmp     short loc_18013AD7B
0x18013ad34  lea     rcx, [rsp+2E0h+var_280]
0x18013ad39  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013ad3e  mov     rdx, rax
0x18013ad41  lea     rcx, [rbp+1E0h+var_250]
0x18013ad45  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18013ad4a  nop
0x18013ad4b  lea     rcx, [rdi+80h]
0x18013ad52  lea     rdx, [rbp+1E0h+var_250]
0x18013ad56  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18013ad5b  nop
0x18013ad5c  lea     rcx, [rbp+1E0h+var_250]
0x18013ad60  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013ad65  nop
0x18013ad66  lea     rcx, [rsp+2E0h+var_280]
0x18013ad6b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013ad70  mov     rdx, rsi; struct _CERT_CONTEXT *
0x18013ad73  mov     rcx, rdi; this
0x18013ad76  call    ?ValidateCertChain@CertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJPEBU_CERT_CONTEXT@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo::ValidateCertChain(_CERT_CONTEXT const *)
0x18013ad7b  mov     rcx, [rbp+1E0h+var_20]
0x18013ad82  xor     rcx, rsp; StackCookie
0x18013ad85  call    __security_check_cookie
0x18013ad8a  lea     r11, [rsp+2E0h+var_10]
0x18013ad92  mov     rbx, [r11+30h]
0x18013ad96  mov     rsi, [r11+38h]
0x18013ad9a  mov     rsp, r11
0x18013ad9d  pop     r12
0x18013ad9f  pop     rdi
0x18013ada0  pop     rbp
0x18013ada1  retn
```
