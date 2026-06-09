# I_GetSmartCardUserLogonCertificateHash(std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x1800098c4`
- end: `0x180009b52`
- name: `?I_GetSmartCardUserLogonCertificateHash@@YAKAEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `654`
- prototype: `SECURITY_STATUS __fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000971c`

## callees

- `0x180008d48`
- `0x1800098c4`
- `0x180010c58`
- `0x1800140d0`
- `0x180014114`
- `0x180015b30`
- `0x180016090`
- `0x180016a66`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099ad`
- `CRYPT32!CertFreeCertificateContext` at `0x180009ab4`
- `CRYPT32!CertFreeCertificateContext` at `0x180009ab4`
- `CRYPT32!CertCreateCertificateContext` at `0x18000999b`
- `CRYPT32!CertCreateCertificateContext` at `0x18000999b`
- `SspiCli!AcquireCredentialsHandleW` at `0x180009947`
- `SspiCli!AcquireCredentialsHandleW` at `0x180009947`
- `SspiCli!QueryCredentialsAttributesW` at `0x180009970`
- `SspiCli!QueryCredentialsAttributesW` at `0x180009970`

## pseudocode

```c
SECURITY_STATUS __fastcall I_GetSmartCardUserLogonCertificateHash(__int64 a1)
{
  SECURITY_STATUS result; // eax
  DWORD LastError; // ebx
  PCCERT_CONTEXT CertificateContext; // rax
  const CERT_CONTEXT *v5; // rbx
  DWORD v6; // esi
  __int64 v7; // rdx
  __int64 v8; // r14
  unsigned __int64 v9; // rcx
  __int64 v10; // rax
  size_t v11; // rsi
  __int64 v12; // rdx
  __int64 v13; // rsi
  unsigned __int64 v14; // rcx
  __int64 v15; // rax
  size_t v16; // rbx
  unsigned int v17; // [rsp+50h] [rbp-49h] BYREF
  PCCERT_CONTEXT v18; // [rsp+58h] [rbp-41h] BYREF
  _DWORD *p_dwCertEncodingType; // [rsp+60h] [rbp-39h] BYREF
  __int64 v20; // [rsp+68h] [rbp-31h] BYREF
  const CERT_CONTEXT *v21; // [rsp+70h] [rbp-29h] BYREF
  __int128 *p_pBuffer; // [rsp+78h] [rbp-21h] BYREF
  __int16 v23; // [rsp+80h] [rbp-19h]
  SECURITY_INTEGER ptsExpiry; // [rsp+88h] [rbp-11h] BYREF
  const CERT_CONTEXT **p_p_dwCertEncodingType; // [rsp+90h] [rbp-9h] BYREF
  __int64 *v26; // [rsp+98h] [rbp-1h]
  const CERT_CONTEXT **v27; // [rsp+A0h] [rbp+7h]
  __int128 pBuffer; // [rsp+A8h] [rbp+Fh] BYREF
  struct _SecHandle *p_phCredential; // [rsp+B8h] [rbp+1Fh] BYREF
  __int16 v30; // [rsp+C0h] [rbp+27h]
  struct _SecHandle phCredential; // [rsp+C8h] [rbp+2Fh] BYREF

  ptsExpiry.QuadPart = 0;
  pBuffer = 0;
  phCredential.dwUpper = -1;
  phCredential.dwLower = -1;
  result = AcquireCredentialsHandleW(0, (LPWSTR)L"Negotiate", 3u, 0, 0, 0, 0, &phCredential, &ptsExpiry);
  if ( !result )
  {
    p_phCredential = &phCredential;
    v30 = 256;
    LastError = QueryCredentialsAttributesW(&phCredential, 4u, &pBuffer);
    if ( LastError )
    {
LABEL_25:
      wil::details::ScopeExitFnGuard__lambda_aeeb90c9e0a0825fb70a29cc2e63d45c___::operator()(&p_phCredential);
      return LastError;
    }
    p_pBuffer = &pBuffer;
    v23 = 256;
    CertificateContext = CertCreateCertificateContext(0x10001u, *((const BYTE **)&pBuffer + 1), pBuffer);
    v5 = CertificateContext;
    v18 = CertificateContext;
    if ( !CertificateContext )
    {
      LastError = GetLastError();
      wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v18);
      wil::details::ScopeExitFnGuard__lambda_ea13126aeba3897b59b42b6e1e4229f4___::operator()(&p_pBuffer);
      goto LABEL_25;
    }
    v17 = 0;
    v21 = (const CERT_CONTEXT *)&v17;
    v20 = 0;
    p_dwCertEncodingType = &CertificateContext->dwCertEncodingType;
    p_p_dwCertEncodingType = (const CERT_CONTEXT **)&p_dwCertEncodingType;
    v26 = &v20;
    v27 = &v21;
    v6 = errcntrctlib::WinApiErrorContract__lambda_fe0af32c667aebe8836da51bba3d0136___(&p_p_dwCertEncodingType);
    if ( v6 )
    {
      wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v18);
LABEL_7:
      wil::details::ScopeExitFnGuard__lambda_ea13126aeba3897b59b42b6e1e4229f4___::operator()(&p_pBuffer);
      LastError = v6;
      goto LABEL_25;
    }
    v7 = *(_QWORD *)a1;
    v8 = *(_QWORD *)(a1 + 8);
    v9 = v8 - *(_QWORD *)a1;
    if ( v17 >= v9 )
    {
      if ( v17 <= v9 )
        goto LABEL_15;
      if ( v17 > (unsigned __int64)(*(_QWORD *)(a1 + 16) - v7) )
      {
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>((__int64 *)a1, v17);
        goto LABEL_15;
      }
      v11 = v17 - v9;
      memset_0(*(void **)(a1 + 8), 0, v11);
      v10 = v11 + v8;
    }
    else
    {
      v10 = v7 + v17;
    }
    *(_QWORD *)(a1 + 8) = v10;
LABEL_15:
    v20 = *(_QWORD *)a1;
    v21 = v5;
    p_dwCertEncodingType = &v17;
    p_p_dwCertEncodingType = &v21;
    v26 = &v20;
    v27 = (const CERT_CONTEXT **)&p_dwCertEncodingType;
    v6 = errcntrctlib::WinApiErrorContract__lambda_fe0af32c667aebe8836da51bba3d0136___(&p_p_dwCertEncodingType);
    if ( v6 )
    {
      CertFreeCertificateContext(v5);
      goto LABEL_7;
    }
    v12 = *(_QWORD *)a1;
    v13 = *(_QWORD *)(a1 + 8);
    v14 = v13 - *(_QWORD *)a1;
    if ( v17 < v14 )
    {
      v15 = v12 + v17;
LABEL_23:
      *(_QWORD *)(a1 + 8) = v15;
      goto LABEL_24;
    }
    if ( v17 > v14 )
    {
      if ( v17 <= (unsigned __int64)(*(_QWORD *)(a1 + 16) - v12) )
      {
        v16 = v17 - v14;
        memset_0(*(void **)(a1 + 8), 0, v16);
        v15 = v16 + v13;
        goto LABEL_23;
      }
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>((__int64 *)a1, v17);
    }
LABEL_24:
    wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v18);
    wil::details::ScopeExitFnGuard__lambda_ea13126aeba3897b59b42b6e1e4229f4___::operator()(&p_pBuffer);
    LastError = 0;
    goto LABEL_25;
  }
  return result;
}

```

## disassembly

```asm
0x1800098c4  mov     [rsp-8+arg_8], rbx
0x1800098c9  mov     [rsp-8+arg_10], rsi
0x1800098ce  push    rbp
0x1800098cf  push    rdi
0x1800098d0  push    r14
0x1800098d2  lea     rbp, [rsp-47h]
0x1800098d7  sub     rsp, 0E0h
0x1800098de  mov     rax, cs:__security_cookie
0x1800098e5  xor     rax, rsp
0x1800098e8  mov     [rbp+57h+var_18], rax
0x1800098ec  mov     rdi, rcx
0x1800098ef  mov     qword ptr [rbp+57h+var_68], 0
0x1800098f7  xorps   xmm0, xmm0
0x1800098fa  movups  [rbp+57h+pBuffer], xmm0
0x1800098fe  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009902  mov     [rbp+57h+var_28.dwUpper], rax
0x180009906  mov     [rbp+57h+var_28.dwLower], rax
0x18000990a  lea     rax, [rbp+57h+var_68]
0x18000990e  mov     [rsp+0F0h+ptsExpiry], rax; ptsExpiry
0x180009913  lea     rax, [rbp+57h+var_28]
0x180009917  mov     [rsp+0F0h+phCredential], rax; phCredential
0x18000991c  mov     [rsp+0F0h+pvGetKeyArgument], 0; pvGetKeyArgument
0x180009925  mov     [rsp+0F0h+pGetKeyFn], 0; pGetKeyFn
0x18000992e  mov     [rsp+0F0h+pAuthData], 0; pAuthData
0x180009937  xor     r9d, r9d; pvLogonId
0x18000993a  lea     r8d, [r9+3]; fCredentialUse
0x18000993e  lea     rdx, pszPackage; "Negotiate"
0x180009945  xor     ecx, ecx; pszPrincipal
0x180009947  call    cs:__imp_AcquireCredentialsHandleW
0x18000994d  test    eax, eax
0x18000994f  jnz     loc_180009B2E
0x180009955  lea     rax, [rbp+57h+var_28]
0x180009959  mov     [rbp+57h+var_38], rax
0x18000995d  mov     [rbp+57h+var_30], 100h
0x180009963  lea     r8, [rbp+57h+pBuffer]; pBuffer
0x180009967  mov     edx, 4; ulAttribute
0x18000996c  lea     rcx, [rbp+57h+var_28]; phCredential
0x180009970  call    cs:__imp_QueryCredentialsAttributesW
0x180009976  mov     ebx, eax
0x180009978  test    eax, eax
0x18000997a  jnz     loc_180009B23
0x180009980  lea     rax, [rbp+57h+pBuffer]
0x180009984  mov     [rbp+57h+var_78], rax
0x180009988  mov     [rbp+57h+var_70], 100h
0x18000998e  mov     r8d, dword ptr [rbp+57h+pBuffer]; cbCertEncoded
0x180009992  mov     rdx, qword ptr [rbp+57h+pBuffer+8]; pbCertEncoded
0x180009996  mov     ecx, 10001h; dwCertEncodingType
0x18000999b  call    cs:__imp_CertCreateCertificateContext
0x1800099a1  mov     rbx, rax
0x1800099a4  mov     [rbp+57h+var_98], rax
0x1800099a8  test    rax, rax
0x1800099ab  jnz     short loc_1800099CD
0x1800099ad  call    cs:__imp_GetLastError
0x1800099b3  mov     ebx, eax
0x1800099b5  lea     rcx, [rbp+57h+var_98]
0x1800099b9  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x1800099be  nop
0x1800099bf  lea     rcx, [rbp+57h+var_78]
0x1800099c3  call    wil__details__ScopeExitFnGuard__lambda_ea13126aeba3897b59b42b6e1e4229f4_____operator__
0x1800099c8  jmp     loc_180009B23
0x1800099cd  mov     [rbp+57h+var_A0], 0
0x1800099d4  lea     rax, [rbp+57h+var_A0]
0x1800099d8  mov     [rbp+57h+var_80], rax
0x1800099dc  mov     [rbp+57h+var_88], 0
0x1800099e4  mov     [rbp+57h+var_90], rbx
0x1800099e8  lea     rax, [rbp+57h+var_90]
0x1800099ec  mov     [rbp+57h+var_60], rax
0x1800099f0  lea     rax, [rbp+57h+var_88]
0x1800099f4  mov     [rbp+57h+var_58], rax
0x1800099f8  lea     rax, [rbp+57h+var_80]
0x1800099fc  mov     [rbp+57h+var_50], rax
0x180009a00  lea     rcx, [rbp+57h+var_60]
0x180009a04  call    errcntrctlib__WinApiErrorContract__lambda_fe0af32c667aebe8836da51bba3d0136___
0x180009a09  mov     esi, eax
0x180009a0b  test    eax, eax
0x180009a0d  jz      short loc_180009A29
0x180009a0f  lea     rcx, [rbp+57h+var_98]
0x180009a13  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180009a18  nop
0x180009a19  lea     rcx, [rbp+57h+var_78]
0x180009a1d  call    wil__details__ScopeExitFnGuard__lambda_ea13126aeba3897b59b42b6e1e4229f4_____operator__
0x180009a22  mov     ebx, esi
0x180009a24  jmp     loc_180009B23
0x180009a29  mov     esi, [rbp+57h+var_A0]
0x180009a2c  mov     rdx, [rdi]
0x180009a2f  mov     r14, [rdi+8]
0x180009a33  mov     rcx, r14
0x180009a36  sub     rcx, rdx
0x180009a39  cmp     rsi, rcx
0x180009a3c  jnb     short loc_180009A44
0x180009a3e  lea     rax, [rdx+rsi]
0x180009a42  jmp     short loc_180009A73
0x180009a44  jbe     short loc_180009A77
0x180009a46  mov     rax, [rdi+10h]
0x180009a4a  sub     rax, rdx
0x180009a4d  cmp     rsi, rax
0x180009a50  jbe     short loc_180009A5F
0x180009a52  mov     rdx, rsi
0x180009a55  mov     rcx, rdi
0x180009a58  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180009a5d  jmp     short loc_180009A77
0x180009a5f  sub     rsi, rcx
0x180009a62  mov     r8, rsi; Size
0x180009a65  xor     edx, edx; Val
0x180009a67  mov     rcx, r14; void *
0x180009a6a  call    memset_0
0x180009a6f  lea     rax, [rsi+r14]
0x180009a73  mov     [rdi+8], rax
0x180009a77  mov     rax, [rdi]
0x180009a7a  mov     [rbp+57h+var_88], rax
0x180009a7e  mov     [rbp+57h+var_80], rbx
0x180009a82  lea     rax, [rbp+57h+var_A0]
0x180009a86  mov     [rbp+57h+var_90], rax
0x180009a8a  lea     rax, [rbp+57h+var_80]
0x180009a8e  mov     [rbp+57h+var_60], rax
0x180009a92  lea     rax, [rbp+57h+var_88]
0x180009a96  mov     [rbp+57h+var_58], rax
0x180009a9a  lea     rax, [rbp+57h+var_90]
0x180009a9e  mov     [rbp+57h+var_50], rax
0x180009aa2  lea     rcx, [rbp+57h+var_60]
0x180009aa6  call    errcntrctlib__WinApiErrorContract__lambda_fe0af32c667aebe8836da51bba3d0136___
0x180009aab  mov     esi, eax
0x180009aad  test    eax, eax
0x180009aaf  jz      short loc_180009AC0
0x180009ab1  mov     rcx, rbx; pCertContext
0x180009ab4  call    cs:__imp_CertFreeCertificateContext
0x180009aba  nop
0x180009abb  jmp     loc_180009A19
0x180009ac0  mov     ebx, [rbp+57h+var_A0]
0x180009ac3  mov     rdx, [rdi]
0x180009ac6  mov     rsi, [rdi+8]
0x180009aca  mov     rcx, rsi
0x180009acd  sub     rcx, rdx
0x180009ad0  cmp     rbx, rcx
0x180009ad3  jnb     short loc_180009ADB
0x180009ad5  lea     rax, [rdx+rbx]
0x180009ad9  jmp     short loc_180009B0A
0x180009adb  jbe     short loc_180009B0E
0x180009add  mov     rax, [rdi+10h]
0x180009ae1  sub     rax, rdx
0x180009ae4  cmp     rbx, rax
0x180009ae7  jbe     short loc_180009AF6
0x180009ae9  mov     rdx, rbx
0x180009aec  mov     rcx, rdi
0x180009aef  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180009af4  jmp     short loc_180009B0E
0x180009af6  sub     rbx, rcx
0x180009af9  mov     r8, rbx; Size
0x180009afc  xor     edx, edx; Val
0x180009afe  mov     rcx, rsi; void *
0x180009b01  call    memset_0
0x180009b06  lea     rax, [rbx+rsi]
0x180009b0a  mov     [rdi+8], rax
0x180009b0e  lea     rcx, [rbp+57h+var_98]
0x180009b12  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180009b17  nop
0x180009b18  lea     rcx, [rbp+57h+var_78]
0x180009b1c  call    wil__details__ScopeExitFnGuard__lambda_ea13126aeba3897b59b42b6e1e4229f4_____operator__
0x180009b21  xor     ebx, ebx
0x180009b23  lea     rcx, [rbp+57h+var_38]
0x180009b27  call    wil__details__ScopeExitFnGuard__lambda_aeeb90c9e0a0825fb70a29cc2e63d45c_____operator__
0x180009b2c  mov     eax, ebx
0x180009b2e  mov     rcx, [rbp+57h+var_18]
0x180009b32  xor     rcx, rsp; StackCookie
0x180009b35  call    __security_check_cookie
0x180009b3a  lea     r11, [rsp+0F0h+var_10]
0x180009b42  mov     rbx, [r11+28h]
0x180009b46  mov     rsi, [r11+30h]
0x180009b4a  mov     rsp, r11
0x180009b4d  pop     r14
0x180009b4f  pop     rdi
0x180009b50  pop     rbp
0x180009b51  retn
```
