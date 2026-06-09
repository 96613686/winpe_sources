# win_dox::OpcDigitalSignatureManagerImpl::CreateReferenceForRelationships(void *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70> const &,_CRYPT_XML_ALGORITHM const &,_CRYPT_XML_ALGORITHM *,win_dox::OpcSignatureRelationshipReference const &)

- ea: `0x1800a5bf8`
- end: `0x1800a5d14`
- name: `?CreateReferenceForRelationships@OpcDigitalSignatureManagerImpl@win_dox@@AEAAPEAXPEAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBU_CRYPT_XML_ALGORITHM@@PEAU5@AEBVOpcSignatureRelationshipReference@2@@Z`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800a5080`

## callees

- `0x1800147d0`
- `0x18001568c`
- `0x180074a70`
- `0x1800a5bf8`
- `0x1800a5d1c`
- `0x1800a5fe0`
- `0x1801178f0`

## import_xrefs

- `CRYPTXML!CryptXmlCreateReference` at `0x1800a5cc4`
- `CRYPTXML!CryptXmlCreateReference` at `0x1800a5cc4`

## string_xrefs

- `0x1800a5c51`: `http://schemas.openxmlformats.org/package/2006/RelationshipTransform`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HCRYPTXML __fastcall win_dox::OpcDigitalSignatureManagerImpl::CreateReferenceForRelationships(
        __int64 a1,
        void *a2,
        __int64 a3,
        const CRYPT_XML_ALGORITHM *a4,
        CRYPT_XML_ALGORITHM *rgTransform,
        __int64 a6)
{
  BYTE *v9; // rax
  const WCHAR *v10; // r9
  HRESULT Reference; // eax
  __int64 v12; // rdx
  const char *v13; // r8
  unsigned int v14; // r9d
  HCRYPTXML v15; // rbx
  __int64 v16; // rdx
  HCRYPTXML phReference[2]; // [rsp+50h] [rbp-49h] BYREF
  char v19[8]; // [rsp+60h] [rbp-39h] BYREF
  BYTE *v20; // [rsp+68h] [rbp-31h] BYREF
  ULONG v21; // [rsp+78h] [rbp-21h]
  unsigned __int64 v22; // [rsp+80h] [rbp-19h]
  char v23[8]; // [rsp+88h] [rbp-11h] BYREF
  __int16 v24; // [rsp+90h] [rbp-9h]
  __int64 v25; // [rsp+A0h] [rbp+7h]
  __int64 v26; // [rsp+A8h] [rbp+Fh]

  phReference[1] = (HCRYPTXML)-2LL;
  v26 = 7;
  v25 = 0;
  v24 = 0;
  win_dox::OpcSignatureRelationshipReferenceWriter::Write(a6, v23);
  rgTransform->wszAlgorithm = L"http://schemas.openxmlformats.org/package/2006/RelationshipTransform";
  win_musl::UnicodeWideToUnicode8(v19, v23);
  rgTransform->Encoded.cbData = v21;
  v9 = (BYTE *)&v20;
  if ( v22 >= 0x10 )
    v9 = v20;
  rgTransform->Encoded.pbData = v9;
  phReference[0] = 0;
  v10 = (const WCHAR *)(a3 + 8);
  if ( *(_QWORD *)(a3 + 32) >= 8u )
    v10 = *(const WCHAR **)v10;
  Reference = CryptXmlCreateReference(a2, 0, 0, v10, 0, a4, 2u, rgTransform, phReference);
  if ( Reference < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)Reference, v12, v13, v14);
  v15 = phReference[0];
  LOBYTE(v12) = 1;
  std::string::_Tidy(v19, v12, 0);
  LOBYTE(v16) = 1;
  std::wstring::_Tidy(v23, v16, 0);
  return v15;
}

```

## disassembly

```asm
0x1800a5bf8  push    rbp
0x1800a5bfa  push    rbx
0x1800a5bfb  push    rsi
0x1800a5bfc  push    rdi
0x1800a5bfd  push    r14
0x1800a5bff  lea     rbp, [rsp-27h]
0x1800a5c04  sub     rsp, 0C0h
0x1800a5c0b  mov     [rbp+47h+var_88], 0FFFFFFFFFFFFFFFEh
0x1800a5c13  mov     rax, cs:__security_cookie
0x1800a5c1a  xor     rax, rsp
0x1800a5c1d  mov     [rbp+47h+var_30], rax
0x1800a5c21  mov     r14, r9
0x1800a5c24  mov     rbx, r8
0x1800a5c27  mov     rsi, rdx
0x1800a5c2a  mov     rdi, [rbp+47h+arg_20]
0x1800a5c2e  mov     rcx, [rbp+47h+arg_28]
0x1800a5c32  mov     [rbp+47h+var_38], 7
0x1800a5c3a  mov     [rbp+47h+var_40], 0
0x1800a5c42  xor     eax, eax
0x1800a5c44  mov     [rbp+47h+var_50], ax
0x1800a5c48  lea     rdx, [rbp+47h+var_58]
0x1800a5c4c  call    ?Write@OpcSignatureRelationshipReferenceWriter@win_dox@@SAXAEBVOpcSignatureRelationshipReference@2@PEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_dox::OpcSignatureRelationshipReferenceWriter::Write(win_dox::OpcSignatureRelationshipReference const &,std::wstring *)
0x1800a5c51  lea     rax, ?gc_RelationshipTransform@Value@DigitalSignatures@win_musl@@3QB_WB; "http://schemas.openxmlformats.org/packa"...
0x1800a5c58  mov     [rdi+8], rax
0x1800a5c5c  lea     rdx, [rbp+47h+var_58]
0x1800a5c60  lea     rcx, [rbp+47h+var_80]
0x1800a5c64  call    ?UnicodeWideToUnicode8@win_musl@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@3@@Z; win_musl::UnicodeWideToUnicode8(std::wstring const &)
0x1800a5c69  nop
0x1800a5c6a  mov     eax, [rbp+47h+var_68]
0x1800a5c6d  mov     [rdi+14h], eax
0x1800a5c70  lea     rax, [rbp+47h+var_78]
0x1800a5c74  cmp     [rbp+47h+var_60], 10h
0x1800a5c79  cmovnb  rax, [rbp+47h+var_78]
0x1800a5c7e  mov     [rdi+18h], rax
0x1800a5c82  mov     [rbp+47h+var_90], 0
0x1800a5c8a  lea     r9, [rbx+8]
0x1800a5c8e  cmp     qword ptr [rbx+20h], 8
0x1800a5c93  jb      short loc_1800A5C98
0x1800a5c95  mov     r9, [r9]; wszURI
0x1800a5c98  lea     rax, [rbp+47h+var_90]
0x1800a5c9c  mov     [rsp+0E0h+phReference], rax; phReference
0x1800a5ca1  mov     [rsp+0E0h+rgTransform], rdi; rgTransform
0x1800a5ca6  mov     [rsp+0E0h+cTransform], 2; cTransform
0x1800a5cae  mov     [rsp+0E0h+pDigestMethod], r14; pDigestMethod
0x1800a5cb3  mov     [rsp+0E0h+wszType], 0; wszType
0x1800a5cbc  xor     r8d, r8d; wszId
0x1800a5cbf  xor     edx, edx; dwFlags
0x1800a5cc1  mov     rcx, rsi; hCryptXml
0x1800a5cc4  call    cs:__imp_CryptXmlCreateReference
0x1800a5cca  test    eax, eax
0x1800a5ccc  jns     short loc_1800A5CD6
0x1800a5cce  mov     ecx, eax; this
0x1800a5cd0  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1800a5cd6  mov     rbx, [rbp+47h+var_90]
0x1800a5cda  xor     r8d, r8d
0x1800a5cdd  mov     dl, 1
0x1800a5cdf  lea     rcx, [rbp+47h+var_80]
0x1800a5ce3  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x1800a5ce8  nop
0x1800a5ce9  xor     r8d, r8d
0x1800a5cec  mov     dl, 1
0x1800a5cee  lea     rcx, [rbp+47h+var_58]
0x1800a5cf2  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800a5cf7  mov     rax, rbx
0x1800a5cfa  mov     rcx, [rbp+47h+var_30]
0x1800a5cfe  xor     rcx, rsp; StackCookie
0x1800a5d01  call    __security_check_cookie
0x1800a5d06  add     rsp, 0C0h
0x1800a5d0d  pop     r14
0x1800a5d0f  pop     rdi
0x1800a5d10  pop     rsi
0x1800a5d11  pop     rbx
0x1800a5d12  pop     rbp
0x1800a5d13  retn
```
