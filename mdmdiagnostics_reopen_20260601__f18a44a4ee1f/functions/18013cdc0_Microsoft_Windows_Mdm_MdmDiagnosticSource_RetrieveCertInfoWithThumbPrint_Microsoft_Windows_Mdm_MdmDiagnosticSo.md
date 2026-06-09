# Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveCertInfoWithThumbPrint(Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo &,_CERT_CONTEXT const *)

- ea: `0x18013cdc0`
- end: `0x18013d0b7`
- name: `?RetrieveCertInfoWithThumbPrint@MdmDiagnosticSource@Mdm@Windows@Microsoft@@YAJAEAVCertInfo@1234@PEBU_CERT_CONTEXT@@@Z`
- size: `759`
- prototype: `__int64 __fastcall(Microsoft::Windows::Mdm::MdmDiagnosticSource *__hidden this, struct _CERT_CONTEXT *, const struct _CERT_CONTEXT *)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18012b988`
- `0x18013c828`

## callees

- `0x180019080`
- `0x18001a054`
- `0x1800e688c`
- `0x1800e68b0`
- `0x1800ed46c`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x180109344`
- `0x1801129e8`
- `0x18013cdc0`
- `0x18013d0c0`

## import_xrefs

- `CRYPT32!CertFindExtension` at `0x18013cf2b`
- `CRYPT32!CertFindExtension` at `0x18013cf2b`
- `CRYPT32!CertGetNameStringW` at `0x18013ce8b`
- `CRYPT32!CertGetNameStringW` at `0x18013cedc`
- `CRYPT32!CertGetNameStringW` at `0x18013ce8b`
- `CRYPT32!CertGetNameStringW` at `0x18013cedc`
- `CRYPT32!CryptFormatObject` at `0x18013cf7e`
- `CRYPT32!CryptFormatObject` at `0x18013cfef`
- `CRYPT32!CryptFormatObject` at `0x18013cf7e`
- `CRYPT32!CryptFormatObject` at `0x18013cfef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013ce21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013cfff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013ce21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013cfff`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18013ce11`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18013ce11`

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
0x18013cdc0  mov     [rsp-8+arg_10], rbx
0x18013cdc5  mov     [rsp-8+arg_18], rsi
0x18013cdca  push    rbp
0x18013cdcb  push    rdi
0x18013cdcc  push    r12
0x18013cdce  lea     rbp, [rsp-1D0h]
0x18013cdd6  sub     rsp, 2D0h
0x18013cddd  mov     rax, cs:__security_cookie
0x18013cde4  xor     rax, rsp
0x18013cde7  mov     [rbp+1E0h+var_20], rax
0x18013cdee  mov     rsi, rdx
0x18013cdf1  mov     rdi, rcx
0x18013cdf4  xorps   xmm0, xmm0
0x18013cdf7  movups  xmmword ptr [rbp+1E0h+SystemTime.wYear], xmm0
0x18013cdfb  mov     rax, [rdx+18h]
0x18013cdff  mov     rcx, [rax+48h]
0x18013ce03  mov     qword ptr [rsp+2E0h+FileTime.dwLowDateTime], rcx
0x18013ce08  lea     rdx, [rbp+1E0h+SystemTime]; lpSystemTime
0x18013ce0c  lea     rcx, [rsp+2E0h+FileTime]; lpFileTime
0x18013ce11  call    cs:__imp_FileTimeToSystemTime
0x18013ce18  nop     dword ptr [rax+rax+00h]
0x18013ce1d  test    eax, eax
0x18013ce1f  jnz     short loc_18013CE42
0x18013ce21  call    cs:__imp_GetLastError
0x18013ce28  nop     dword ptr [rax+rax+00h]
0x18013ce2d  test    eax, eax
0x18013ce2f  jle     loc_18013D08F
0x18013ce35  movzx   eax, ax
0x18013ce38  or      eax, 80070000h
0x18013ce3d  jmp     loc_18013D08F
0x18013ce42  movups  xmm0, xmmword ptr [rbp+1E0h+SystemTime.wYear]
0x18013ce46  movdqu  xmmword ptr [rdi+0A0h], xmm0
0x18013ce4e  mov     dword ptr [rbp+1E0h+var_230], 0
0x18013ce55  xor     edx, edx; Val
0x18013ce57  mov     r8d, 204h; Size
0x18013ce5d  lea     rcx, [rbp+1E0h+var_22C]; void *
0x18013ce61  call    memset_0
0x18013ce66  mov     eax, 104h
0x18013ce6b  mov     [rsp+2E0h+var_290], eax
0x18013ce6f  mov     [rsp+2E0h+cchNameString], eax; cchNameString
0x18013ce73  lea     rax, [rbp+1E0h+var_230]
0x18013ce77  mov     [rsp+2E0h+pszNameString], rax; pszNameString
0x18013ce7c  xor     r9d, r9d; pvTypePara
0x18013ce7f  xor     r8d, r8d; dwFlags
0x18013ce82  lea     ebx, [r9+4]
0x18013ce86  mov     edx, ebx; dwType
0x18013ce88  mov     rcx, rsi; pCertContext
0x18013ce8b  call    cs:__imp_CertGetNameStringW
0x18013ce92  nop     dword ptr [rax+rax+00h]
0x18013ce97  lea     rdx, [rbp+1E0h+var_230]
0x18013ce9b  lea     rcx, [rsp+2E0h+var_280]
0x18013cea0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18013cea5  nop
0x18013cea6  lea     rcx, [rdi+60h]
0x18013ceaa  lea     rdx, [rsp+2E0h+var_280]
0x18013ceaf  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18013ceb4  nop
0x18013ceb5  lea     rcx, [rsp+2E0h+var_280]
0x18013ceba  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013cebf  mov     eax, [rsp+2E0h+var_290]
0x18013cec3  mov     [rsp+2E0h+cchNameString], eax; cchNameString
0x18013cec7  lea     rax, [rbp+1E0h+var_230]
0x18013cecb  mov     [rsp+2E0h+pszNameString], rax; pszNameString
0x18013ced0  xor     r9d, r9d; pvTypePara
0x18013ced3  lea     r8d, [rbx-3]; dwFlags
0x18013ced7  mov     edx, ebx; dwType
0x18013ced9  mov     rcx, rsi; pCertContext
0x18013cedc  call    cs:__imp_CertGetNameStringW
0x18013cee3  nop     dword ptr [rax+rax+00h]
0x18013cee8  lea     rdx, [rbp+1E0h+var_230]
0x18013ceec  lea     rcx, [rsp+2E0h+var_280]
0x18013cef1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18013cef6  nop
0x18013cef7  lea     rcx, [rdi+40h]
0x18013cefb  lea     rdx, [rsp+2E0h+var_280]
0x18013cf00  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18013cf05  nop
0x18013cf06  lea     rcx, [rsp+2E0h+var_280]
0x18013cf0b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013cf10  mov     rdx, [rsi+18h]
0x18013cf14  mov     r8, [rdx+0C8h]; rgExtensions
0x18013cf1b  mov     edx, [rdx+0C0h]; cExtensions
0x18013cf21  lea     r12, szStructType; "2.5.29.37"
0x18013cf28  mov     rcx, r12; pszObjId
0x18013cf2b  call    cs:__imp_CertFindExtension
0x18013cf32  nop     dword ptr [rax+rax+00h]
0x18013cf37  mov     rbx, rax
0x18013cf3a  test    rax, rax
0x18013cf3d  jz      loc_18013D084
0x18013cf43  mov     [rsp+2E0h+var_290], 0
0x18013cf4b  lea     rax, [rsp+2E0h+var_290]
0x18013cf50  mov     [rsp+2E0h+pcbFormat], rax; pcbFormat
0x18013cf55  mov     [rsp+2E0h+pbFormat], 0; pbFormat
0x18013cf5e  mov     ecx, [rbx+10h]
0x18013cf61  mov     [rsp+2E0h+cbEncoded], ecx; cbEncoded
0x18013cf65  mov     rcx, [rbx+18h]
0x18013cf69  mov     qword ptr [rsp+2E0h+cchNameString], rcx; pbEncoded
0x18013cf6e  mov     [rsp+2E0h+pszNameString], r12; lpszStructType
0x18013cf73  xor     r9d, r9d; pFormatStruct
0x18013cf76  xor     r8d, r8d; dwFormatStrType
0x18013cf79  xor     edx, edx; dwFormatType
0x18013cf7b  lea     ecx, [rdx+1]; dwCertEncodingType
0x18013cf7e  call    cs:__imp_CryptFormatObject
0x18013cf85  nop     dword ptr [rax+rax+00h]
0x18013cf8a  cmp     [rsp+2E0h+var_290], 0
0x18013cf8f  jbe     loc_18013D084
0x18013cf95  lea     rcx, [rsp+2E0h+var_280]
0x18013cf9a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18013cf9f  nop
0x18013cfa0  xor     r8d, r8d
0x18013cfa3  mov     edx, [rsp+2E0h+var_290]
0x18013cfa7  inc     edx
0x18013cfa9  shr     rdx, 1
0x18013cfac  lea     rcx, [rsp+2E0h+var_280]
0x18013cfb1  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18013cfb6  lea     rcx, [rsp+2E0h+var_280]
0x18013cfbb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013cfc0  lea     rcx, [rsp+2E0h+var_290]
0x18013cfc5  mov     [rsp+2E0h+pcbFormat], rcx; pcbFormat
0x18013cfca  mov     [rsp+2E0h+pbFormat], rax; pbFormat
0x18013cfcf  mov     eax, [rbx+10h]
0x18013cfd2  mov     [rsp+2E0h+cbEncoded], eax; cbEncoded
0x18013cfd6  mov     rax, [rbx+18h]
0x18013cfda  mov     qword ptr [rsp+2E0h+cchNameString], rax; pbEncoded
0x18013cfdf  mov     [rsp+2E0h+pszNameString], r12; int
0x18013cfe4  xor     r9d, r9d; pFormatStruct
0x18013cfe7  xor     r8d, r8d; dwFormatStrType
0x18013cfea  xor     edx, edx; dwFormatType
0x18013cfec  lea     ecx, [rdx+1]; dwCertEncodingType
0x18013cfef  call    cs:__imp_CryptFormatObject
0x18013cff6  nop     dword ptr [rax+rax+00h]
0x18013cffb  test    eax, eax
0x18013cffd  jnz     short loc_18013D048
0x18013cfff  call    cs:__imp_GetLastError
0x18013d006  nop     dword ptr [rax+rax+00h]
0x18013d00b  mov     ebx, eax
0x18013d00d  test    eax, eax
0x18013d00f  jle     short loc_18013D01A
0x18013d011  movzx   ebx, ax
0x18013d014  or      ebx, 80070000h
0x18013d01a  test    ebx, ebx
0x18013d01c  jns     short loc_18013D048
0x18013d01e  mov     rcx, [rbp+1E8h]; this
0x18013d025  mov     r9d, ebx; char *
0x18013d028  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013d02f  mov     edx, 7Fh; void *
0x18013d034  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013d039  nop
0x18013d03a  lea     rcx, [rsp+2E0h+var_280]
0x18013d03f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013d044  mov     eax, ebx
0x18013d046  jmp     short loc_18013D08F
0x18013d048  lea     rcx, [rsp+2E0h+var_280]
0x18013d04d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013d052  mov     rdx, rax
0x18013d055  lea     rcx, [rbp+1E0h+var_250]
0x18013d059  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18013d05e  nop
0x18013d05f  lea     rcx, [rdi+80h]
0x18013d066  lea     rdx, [rbp+1E0h+var_250]
0x18013d06a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18013d06f  nop
0x18013d070  lea     rcx, [rbp+1E0h+var_250]
0x18013d074  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013d079  nop
0x18013d07a  lea     rcx, [rsp+2E0h+var_280]
0x18013d07f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013d084  mov     rdx, rsi; struct _CERT_CONTEXT *
0x18013d087  mov     rcx, rdi; this
0x18013d08a  call    ?ValidateCertChain@CertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJPEBU_CERT_CONTEXT@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo::ValidateCertChain(_CERT_CONTEXT const *)
0x18013d08f  mov     rcx, [rbp+1E0h+var_20]
0x18013d096  xor     rcx, rsp; StackCookie
0x18013d099  call    __security_check_cookie
0x18013d09e  lea     r11, [rsp+2E0h+var_10]
0x18013d0a6  mov     rbx, [r11+30h]
0x18013d0aa  mov     rsi, [r11+38h]
0x18013d0ae  mov     rsp, r11
0x18013d0b1  pop     r12
0x18013d0b3  pop     rdi
0x18013d0b4  pop     rbp
0x18013d0b5  retn
```
