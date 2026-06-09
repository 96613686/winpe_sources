# I_GetCertificateContext_UPN_DN_Hash(_CERT_CONTEXT const *,uchar *,ulong *)

- ea: `0x180006f40`
- end: `0x1800075ca`
- name: `?I_GetCertificateContext_UPN_DN_Hash@@YAKPEBU_CERT_CONTEXT@@PEAEPEAK@Z`
- size: `1674`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, unsigned __int8 *Destination, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x180008d48`

## callees

- `0x180006f40`
- `0x180008554`
- `0x1800085c4`
- `0x1800085f4`
- `0x18000dae0`
- `0x18000e45c`
- `0x180010c58`
- `0x180010d5c`
- `0x180015640`
- `0x180016114`
- `0x180016a66`
- `0x18001df84`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800071ce`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800071ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007224`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007334`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007396`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007224`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007334`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007396`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073d6`
- `CRYPT32!CertNameToStrW` at `0x180007086`
- `CRYPT32!CertNameToStrW` at `0x180007086`
- `CRYPT32!CertGetNameStringW` at `0x180006f8a`
- `CRYPT32!CertGetNameStringW` at `0x18000700b`
- `CRYPT32!CertGetNameStringW` at `0x180007107`
- `CRYPT32!CertGetNameStringW` at `0x180006f8a`
- `CRYPT32!CertGetNameStringW` at `0x18000700b`
- `CRYPT32!CertGetNameStringW` at `0x180007107`
- `ADVAPI32!CryptGetHashParam` at `0x1800073cc`
- `ADVAPI32!CryptGetHashParam` at `0x180007460`
- `ADVAPI32!CryptGetHashParam` at `0x1800073cc`
- `ADVAPI32!CryptGetHashParam` at `0x180007460`
- `ADVAPI32!CryptDestroyHash` at `0x180007345`
- `ADVAPI32!CryptDestroyHash` at `0x1800074e6`
- `ADVAPI32!CryptDestroyHash` at `0x18000751c`
- `ADVAPI32!CryptDestroyHash` at `0x180007577`
- `ADVAPI32!CryptDestroyHash` at `0x180007345`
- `ADVAPI32!CryptDestroyHash` at `0x1800074e6`
- `ADVAPI32!CryptDestroyHash` at `0x18000751c`
- `ADVAPI32!CryptDestroyHash` at `0x180007577`
- `ADVAPI32!CryptHashData` at `0x18000738c`
- `ADVAPI32!CryptHashData` at `0x18000738c`
- `ADVAPI32!CryptCreateHash` at `0x18000732a`
- `ADVAPI32!CryptCreateHash` at `0x18000732a`
- `ADVAPI32!CryptAcquireContextW` at `0x180007216`
- `ADVAPI32!CryptAcquireContextW` at `0x180007216`
- `ADVAPI32!CryptReleaseContext` at `0x180007237`
- `ADVAPI32!CryptReleaseContext` at `0x180007589`
- `ADVAPI32!CryptReleaseContext` at `0x180007237`
- `ADVAPI32!CryptReleaseContext` at `0x180007589`

## pseudocode

```c
__int64 __fastcall I_GetCertificateContext_UPN_DN_Hash(
        PCCERT_CONTEXT pCertContext,
        unsigned __int8 *Destination,
        unsigned int *a3)
{
  DWORD NameStringW; // eax
  DWORD cchNameString; // edi
  unsigned __int64 v8; // r15
  char *v9; // r12
  size_t v10; // r15
  __int64 v11; // rax
  unsigned __int64 v12; // rdi
  char *v13; // r15
  WCHAR *v14; // rax
  size_t v15; // rdi
  DWORD v16; // eax
  DWORD v17; // edi
  unsigned __int64 v18; // r15
  LPWSTR v19; // r12
  size_t v20; // r15
  unsigned __int64 v21; // rbx
  LPWSTR v22; // rdi
  WCHAR *v23; // rax
  size_t v24; // rbx
  LPWSTR v25; // r9
  LPWSTR v26; // r8
  char *v27; // rdx
  DWORD LastError; // ebx
  BYTE *v29; // rcx
  LPWSTR v30; // rcx
  void *v31; // rcx
  DWORD v33; // ebx
  HCRYPTHASH v34; // rcx
  char *v35; // rdi
  BYTE *v36; // rax
  size_t v37; // rbx
  BYTE *v38; // r8
  BYTE *v39; // rbx
  size_t v40; // rdi
  HCRYPTPROV v41; // rcx
  rsize_t v42; // rbx
  rsize_t v43; // rdx
  void *v44; // [rsp+30h] [rbp-59h] BYREF
  HCRYPTPROV phProv; // [rsp+38h] [rbp-51h] BYREF
  void *v46; // [rsp+40h] [rbp-49h] BYREF
  LPWSTR v47[2]; // [rsp+48h] [rbp-41h] BYREF
  __int64 v48; // [rsp+58h] [rbp-31h]
  LPWSTR pszNameString; // [rsp+60h] [rbp-29h] BYREF
  void *v50; // [rsp+68h] [rbp-21h]
  __int64 v51; // [rsp+70h] [rbp-19h]
  BYTE *v52; // [rsp+78h] [rbp-11h] BYREF
  void *v53; // [rsp+80h] [rbp-9h]
  __int64 v54; // [rsp+88h] [rbp-1h]
  BYTE *pbData[2]; // [rsp+90h] [rbp+7h] BYREF
  __int64 v56; // [rsp+A0h] [rbp+17h]
  DWORD pdwDataLen; // [rsp+F0h] [rbp+67h] BYREF
  HCRYPTHASH phHash; // [rsp+108h] [rbp+7Fh] BYREF

  std::vector<unsigned char>::vector<unsigned char>(&pszNameString);
  NameStringW = CertGetNameStringW(pCertContext, 8u, 0, 0, 0, 0);
  cchNameString = NameStringW;
  if ( NameStringW > 1 )
  {
    v8 = 2LL * NameStringW;
    v9 = (char *)v50;
    if ( v8 >= (_BYTE *)v50 - (_BYTE *)pszNameString )
    {
      if ( 2 * (unsigned __int64)NameStringW > (_BYTE *)v50 - (_BYTE *)pszNameString )
      {
        if ( v8 <= v51 - (__int64)pszNameString )
        {
          v10 = v8 - ((_BYTE *)v50 - (_BYTE *)pszNameString);
          memset_0(v50, 0, v10);
          v50 = &v9[v10];
        }
        else
        {
          std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(
            (__int64 *)&pszNameString,
            2LL * NameStringW);
        }
      }
    }
    else
    {
      v50 = &pszNameString[v8 / 2];
    }
    v11 = CertGetNameStringW(pCertContext, 8u, 0, 0, pszNameString, cchNameString) - 1;
    v12 = 2 * v11;
    v13 = (char *)v50;
    if ( 2 * v11 >= (unsigned __int64)((_BYTE *)v50 - (_BYTE *)pszNameString) )
    {
      if ( 2 * v11 <= (unsigned __int64)((_BYTE *)v50 - (_BYTE *)pszNameString) )
        goto LABEL_15;
      if ( v12 > v51 - (__int64)pszNameString )
      {
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>((__int64 *)&pszNameString, v12);
        goto LABEL_15;
      }
      v15 = v12 - ((_BYTE *)v50 - (_BYTE *)pszNameString);
      memset_0(v50, 0, v15);
      v14 = (WCHAR *)&v13[v15];
    }
    else
    {
      v14 = &pszNameString[v12 / 2];
    }
    v50 = v14;
  }
LABEL_15:
  std::vector<unsigned char>::vector<unsigned char>(v47);
  v16 = CertNameToStrW(pCertContext->dwCertEncodingType, &pCertContext->pCertInfo->Subject, 2u, 0, 0);
  v17 = v16;
  if ( v16 <= 1 )
    goto LABEL_29;
  v18 = 2LL * v16;
  v19 = v47[1];
  if ( v18 >= (char *)v47[1] - (char *)v47[0] )
  {
    if ( 2 * (unsigned __int64)v16 > (char *)v47[1] - (char *)v47[0] )
    {
      if ( v18 <= v48 - (unsigned __int64)v47[0] )
      {
        v20 = v18 - ((char *)v47[1] - (char *)v47[0]);
        memset_0(v47[1], 0, v20);
        v47[1] = (LPWSTR)((char *)v19 + v20);
      }
      else
      {
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>((__int64 *)v47, 2LL * v16);
      }
    }
  }
  else
  {
    v47[1] = &v47[0][v18 / 2];
  }
  v21 = 2LL * (CertGetNameStringW(pCertContext, 4u, 0, 0, v47[0], v17) - 1);
  v22 = v47[1];
  if ( v21 >= (char *)v47[1] - (char *)v47[0] )
  {
    if ( v21 <= (char *)v47[1] - (char *)v47[0] )
      goto LABEL_29;
    if ( v21 > v48 - (unsigned __int64)v47[0] )
    {
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>((__int64 *)v47, v21);
      goto LABEL_29;
    }
    v24 = v21 - ((char *)v47[1] - (char *)v47[0]);
    memset_0(v47[1], 0, v24);
    v23 = (LPWSTR)((char *)v22 + v24);
  }
  else
  {
    v23 = &v47[0][v21 / 2];
  }
  v47[1] = v23;
LABEL_29:
  *(_OWORD *)pbData = 0;
  v56 = 0;
  v46 = pszNameString;
  v44 = v50;
  std::vector<unsigned char>::_Construct_n<unsigned char * const &,unsigned char * const &>(
    pbData,
    (_BYTE *)v50 - (_BYTE *)pszNameString,
    &v46,
    &v44);
  v25 = v47[1];
  v26 = v47[0];
  v27 = (char *)v50 + (char *)v47[1] - (char *)v47[0] - (_QWORD)pszNameString;
  v44 = v27;
  if ( (unsigned __int64)v27 > v56 - (unsigned __int64)pbData[0] )
  {
    if ( (unsigned __int64)v27 > 0x7FFFFFFFFFFFFFFFLL )
      std::_Xlength_error("vector too long");
    std::vector<unsigned char>::_Reallocate<0>(pbData, &v44);
    v25 = v47[1];
    v26 = v47[0];
  }
  std::vector<unsigned char>::_Insert_counted_range<unsigned char *>(pbData, pbData[1], v26, (char *)v25 - (char *)v26);
  phProv = 0;
  if ( !CryptAcquireContextW(&phProv, 0, 0, 0x18u, 0xF0000000) )
  {
    LastError = GetLastError();
    if ( phProv )
      CryptReleaseContext(phProv, 0);
    v29 = pbData[0];
    if ( pbData[0] )
    {
      v46 = (void *)(v56 - (unsigned __int64)pbData[0]);
      v44 = pbData[0];
      if ( v56 - (unsigned __int64)pbData[0] >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(&v44, (unsigned __int64 *)&v46);
        v29 = (BYTE *)v44;
      }
      operator delete(v29);
      *(_OWORD *)pbData = 0;
      v56 = 0;
    }
    v30 = v47[0];
    if ( v47[0] )
    {
      v44 = (void *)(v48 - (unsigned __int64)v47[0]);
      v46 = v47[0];
      if ( v48 - (unsigned __int64)v47[0] >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(&v46, (unsigned __int64 *)&v44);
        v30 = (LPWSTR)v46;
      }
      operator delete(v30);
      *(_OWORD *)v47 = 0;
      v48 = 0;
    }
    v31 = pszNameString;
    if ( pszNameString )
    {
      v44 = (void *)(v51 - (_QWORD)pszNameString);
      v46 = pszNameString;
      if ( (unsigned __int64)(v51 - (_QWORD)pszNameString) >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(&v46, (unsigned __int64 *)&v44);
        v31 = v46;
      }
      operator delete(v31);
    }
    return LastError;
  }
  phHash = 0;
  if ( !CryptCreateHash(phProv, 0x800Cu, 0, 0, &phHash) )
  {
    v33 = GetLastError();
    v34 = phHash;
    if ( !phHash )
    {
LABEL_52:
      __1__unique_any_t_V__unique_storage_U__resource_policy__KP6AX_K__E_1_CryptReleaseContextNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd___K_K_0A___T_details_wil___details_wil___wil__QEAA_XZ(&phProv);
      std::vector<unsigned char>::_Tidy((__int64)pbData);
      std::vector<unsigned char>::_Tidy((__int64)v47);
      std::vector<unsigned char>::_Tidy((__int64)&pszNameString);
      return v33;
    }
LABEL_51:
    CryptDestroyHash(v34);
    goto LABEL_52;
  }
  if ( !CryptHashData(phHash, pbData[0], LODWORD(pbData[1]) - LODWORD(pbData[0]), 0) )
  {
    v33 = GetLastError();
    v34 = phHash;
    if ( !phHash )
      goto LABEL_52;
    goto LABEL_51;
  }
  std::vector<unsigned char>::vector<unsigned char>(&v52);
  pdwDataLen = 0;
  if ( !CryptGetHashParam(phHash, 2u, 0, &pdwDataLen, 0) )
  {
LABEL_57:
    v33 = GetLastError();
    std::vector<unsigned char>::_Tidy((__int64)&v52);
    v34 = phHash;
    if ( !phHash )
      goto LABEL_52;
    goto LABEL_51;
  }
  v35 = (char *)v53;
  if ( pdwDataLen >= (unsigned __int64)((_BYTE *)v53 - v52) )
  {
    if ( pdwDataLen <= (unsigned __int64)((_BYTE *)v53 - v52) )
      goto LABEL_66;
    if ( pdwDataLen > (unsigned __int64)(v54 - (_QWORD)v52) )
    {
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>((__int64 *)&v52, pdwDataLen);
      goto LABEL_66;
    }
    v37 = pdwDataLen - ((_BYTE *)v53 - v52);
    memset_0(v53, 0, v37);
    v36 = (BYTE *)&v35[v37];
  }
  else
  {
    v36 = &v52[pdwDataLen];
  }
  v53 = v36;
LABEL_66:
  if ( !CryptGetHashParam(phHash, 2u, v52, &pdwDataLen, 0) )
    goto LABEL_57;
  v38 = v52;
  v39 = (BYTE *)v53;
  if ( pdwDataLen >= (unsigned __int64)((_BYTE *)v53 - v52) )
  {
    if ( pdwDataLen <= (unsigned __int64)((_BYTE *)v53 - v52) )
      goto LABEL_74;
    if ( pdwDataLen > (unsigned __int64)(v54 - (_QWORD)v52) )
    {
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>((__int64 *)&v52, pdwDataLen);
      v39 = (BYTE *)v53;
      v38 = v52;
      goto LABEL_74;
    }
    v40 = pdwDataLen - ((_BYTE *)v53 - v52);
    memset_0(v53, 0, v40);
    v39 += v40;
    v38 = v52;
  }
  else
  {
    v39 = &v52[pdwDataLen];
  }
  v53 = v39;
LABEL_74:
  if ( !Destination )
  {
    *a3 = (_DWORD)v39 - (_DWORD)v38;
    std::vector<unsigned char>::_Tidy((__int64)&v52);
    if ( phHash )
      CryptDestroyHash(phHash);
    v41 = phProv;
    if ( !phProv )
      goto LABEL_87;
    goto LABEL_86;
  }
  v42 = v39 - v38;
  v43 = *a3;
  if ( v43 >= v42 )
  {
    memcpy_s(Destination, v43, v38, v42);
    *a3 = (_DWORD)v53 - (_DWORD)v52;
    std::vector<unsigned char>::_Tidy((__int64)&v52);
    if ( phHash )
      CryptDestroyHash(phHash);
    v41 = phProv;
    if ( !phProv )
      goto LABEL_87;
LABEL_86:
    CryptReleaseContext(v41, 0);
LABEL_87:
    std::vector<unsigned char>::_Tidy((__int64)pbData);
    std::vector<unsigned char>::_Tidy((__int64)v47);
    std::vector<unsigned char>::_Tidy((__int64)&pszNameString);
    return 0;
  }
  std::vector<unsigned char>::_Tidy((__int64)&v52);
  if ( phHash )
    CryptDestroyHash(phHash);
  __1__unique_any_t_V__unique_storage_U__resource_policy__KP6AX_K__E_1_CryptReleaseContextNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd___K_K_0A___T_details_wil___details_wil___wil__QEAA_XZ(&phProv);
  std::vector<unsigned char>::_Tidy((__int64)pbData);
  std::vector<unsigned char>::_Tidy((__int64)v47);
  std::vector<unsigned char>::_Tidy((__int64)&pszNameString);
  return 2148532232LL;
}

```

## disassembly

```asm
0x180006f40  mov     [rsp-8+arg_8], rbx
0x180006f45  push    rbp
0x180006f46  push    rsi
0x180006f47  push    rdi
0x180006f48  push    r12
0x180006f4a  push    r13
0x180006f4c  push    r14
0x180006f4e  push    r15
0x180006f50  lea     rbp, [rsp-27h]
0x180006f55  sub     rsp, 0B0h
0x180006f5c  mov     rsi, r8
0x180006f5f  mov     r14, rdx
0x180006f62  mov     rbx, rcx
0x180006f65  lea     rcx, [rbp+57h+var_80]
0x180006f69  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::vector<uchar>(void)
0x180006f6e  nop
0x180006f6f  xor     r13d, r13d
0x180006f72  mov     [rsp+0E0h+cchNameString], r13d; cchNameString
0x180006f77  mov     [rsp+0E0h+pszNameString], r13; pszNameString
0x180006f7c  xor     r9d, r9d; pvTypePara
0x180006f7f  xor     r8d, r8d; dwFlags
0x180006f82  mov     edx, 8; dwType
0x180006f87  mov     rcx, rbx; pCertContext
0x180006f8a  call    cs:__imp_CertGetNameStringW
0x180006f90  mov     edi, eax
0x180006f92  cmp     eax, 1
0x180006f95  jbe     loc_180007064
0x180006f9b  lea     r15, [rdi+rdi]
0x180006f9f  mov     rdx, [rbp+57h+var_80]
0x180006fa3  mov     r12, [rbp+57h+var_78]
0x180006fa7  mov     rcx, r12
0x180006faa  sub     rcx, rdx
0x180006fad  cmp     r15, rcx
0x180006fb0  jnb     short loc_180006FBC
0x180006fb2  lea     rcx, [r15+rdx]
0x180006fb6  mov     [rbp+57h+var_78], rcx
0x180006fba  jmp     short loc_180006FF0
0x180006fbc  jbe     short loc_180006FF0
0x180006fbe  mov     rax, [rbp+57h+var_70]
0x180006fc2  sub     rax, rdx
0x180006fc5  cmp     r15, rax
0x180006fc8  jbe     short loc_180006FD8
0x180006fca  mov     rdx, r15
0x180006fcd  lea     rcx, [rbp+57h+var_80]
0x180006fd1  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180006fd6  jmp     short loc_180006FF0
0x180006fd8  sub     r15, rcx
0x180006fdb  mov     r8, r15; Size
0x180006fde  xor     edx, edx; Val
0x180006fe0  mov     rcx, r12; void *
0x180006fe3  call    memset_0
0x180006fe8  lea     rax, [r15+r12]
0x180006fec  mov     [rbp+57h+var_78], rax
0x180006ff0  mov     [rsp+0E0h+cchNameString], edi; cchNameString
0x180006ff4  mov     rax, [rbp+57h+var_80]
0x180006ff8  mov     [rsp+0E0h+pszNameString], rax; pszNameString
0x180006ffd  xor     r9d, r9d; pvTypePara
0x180007000  xor     r8d, r8d; dwFlags
0x180007003  mov     edx, 8; dwType
0x180007008  mov     rcx, rbx; pCertContext
0x18000700b  call    cs:__imp_CertGetNameStringW
0x180007011  dec     eax
0x180007013  lea     rdi, [rax+rax]
0x180007017  mov     rdx, [rbp+57h+var_80]
0x18000701b  mov     r15, [rbp+57h+var_78]
0x18000701f  mov     rcx, r15
0x180007022  sub     rcx, rdx
0x180007025  cmp     rdi, rcx
0x180007028  jnb     short loc_180007030
0x18000702a  lea     rax, [rdi+rdx]
0x18000702e  jmp     short loc_180007060
0x180007030  jbe     short loc_180007064
0x180007032  mov     rax, [rbp+57h+var_70]
0x180007036  sub     rax, rdx
0x180007039  cmp     rdi, rax
0x18000703c  jbe     short loc_18000704C
0x18000703e  mov     rdx, rdi
0x180007041  lea     rcx, [rbp+57h+var_80]
0x180007045  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18000704a  jmp     short loc_180007064
0x18000704c  sub     rdi, rcx
0x18000704f  mov     r8, rdi; Size
0x180007052  xor     edx, edx; Val
0x180007054  mov     rcx, r15; void *
0x180007057  call    memset_0
0x18000705c  lea     rax, [rdi+r15]
0x180007060  mov     [rbp+57h+var_78], rax
0x180007064  lea     rcx, [rbp+57h+var_98]
0x180007068  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::vector<uchar>(void)
0x18000706d  nop
0x18000706e  mov     rdx, [rbx+18h]
0x180007072  add     rdx, 50h ; 'P'; pName
0x180007076  mov     dword ptr [rsp+0E0h+pszNameString], r13d; csz
0x18000707b  xor     r9d, r9d; psz
0x18000707e  mov     r8d, 2; dwStrType
0x180007084  mov     ecx, [rbx]; dwCertEncodingType
0x180007086  call    cs:__imp_CertNameToStrW
0x18000708c  mov     edi, eax
0x18000708e  cmp     eax, 1
0x180007091  jbe     loc_180007160
0x180007097  lea     r15, [rdi+rdi]
0x18000709b  mov     rdx, [rbp+57h+var_98]
0x18000709f  mov     r12, [rbp+57h+var_98+8]
0x1800070a3  mov     rcx, r12
0x1800070a6  sub     rcx, rdx
0x1800070a9  cmp     r15, rcx
0x1800070ac  jnb     short loc_1800070B8
0x1800070ae  lea     rcx, [r15+rdx]
0x1800070b2  mov     [rbp+57h+var_98+8], rcx
0x1800070b6  jmp     short loc_1800070EC
0x1800070b8  jbe     short loc_1800070EC
0x1800070ba  mov     rax, [rbp+57h+var_88]
0x1800070be  sub     rax, rdx
0x1800070c1  cmp     r15, rax
0x1800070c4  jbe     short loc_1800070D4
0x1800070c6  mov     rdx, r15
0x1800070c9  lea     rcx, [rbp+57h+var_98]
0x1800070cd  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800070d2  jmp     short loc_1800070EC
0x1800070d4  sub     r15, rcx
0x1800070d7  mov     r8, r15; Size
0x1800070da  xor     edx, edx; Val
0x1800070dc  mov     rcx, r12; void *
0x1800070df  call    memset_0
0x1800070e4  lea     rax, [r15+r12]
0x1800070e8  mov     [rbp+57h+var_98+8], rax
0x1800070ec  mov     [rsp+0E0h+cchNameString], edi; cchNameString
0x1800070f0  mov     rax, [rbp+57h+var_98]
0x1800070f4  mov     [rsp+0E0h+pszNameString], rax; pszNameString
0x1800070f9  xor     r9d, r9d; pvTypePara
0x1800070fc  xor     r8d, r8d; dwFlags
0x1800070ff  mov     edx, 4; dwType
0x180007104  mov     rcx, rbx; pCertContext
0x180007107  call    cs:__imp_CertGetNameStringW
0x18000710d  dec     eax
0x18000710f  lea     rbx, [rax+rax]
0x180007113  mov     rdx, [rbp+57h+var_98]
0x180007117  mov     rdi, [rbp+57h+var_98+8]
0x18000711b  mov     rcx, rdi
0x18000711e  sub     rcx, rdx
0x180007121  cmp     rbx, rcx
0x180007124  jnb     short loc_18000712C
0x180007126  lea     rax, [rbx+rdx]
0x18000712a  jmp     short loc_18000715C
0x18000712c  jbe     short loc_180007160
0x18000712e  mov     rax, [rbp+57h+var_88]
0x180007132  sub     rax, rdx
0x180007135  cmp     rbx, rax
0x180007138  jbe     short loc_180007148
0x18000713a  mov     rdx, rbx
0x18000713d  lea     rcx, [rbp+57h+var_98]
0x180007141  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180007146  jmp     short loc_180007160
0x180007148  sub     rbx, rcx
0x18000714b  mov     r8, rbx; Size
0x18000714e  xor     edx, edx; Val
0x180007150  mov     rcx, rdi; void *
0x180007153  call    memset_0
0x180007158  lea     rax, [rbx+rdi]
0x18000715c  mov     [rbp+57h+var_98+8], rax
0x180007160  mov     rdx, [rbp+57h+var_78]
0x180007164  mov     rax, [rbp+57h+var_80]
0x180007168  xorps   xmm0, xmm0
0x18000716b  movdqu  xmmword ptr [rbp+57h+pbData], xmm0
0x180007170  mov     [rbp+57h+var_40], r13
0x180007174  mov     [rbp+57h+var_A0], rax
0x180007178  mov     [rbp+57h+var_B0], rdx
0x18000717c  sub     rdx, rax
0x18000717f  lea     r9, [rbp+57h+var_B0]
0x180007183  lea     r8, [rbp+57h+var_A0]
0x180007187  lea     rcx, [rbp+57h+pbData]
0x18000718b  call    ??$_Construct_n@AEBQEAEAEBQEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBQEAE1@Z; std::vector<uchar>::_Construct_n<uchar * const &,uchar * const &>(unsigned __int64,uchar * const &,uchar * const &)
0x180007190  nop
0x180007191  mov     r9, [rbp+57h+var_98+8]
0x180007195  mov     rdx, r9
0x180007198  mov     r8, [rbp+57h+var_98]
0x18000719c  sub     rdx, r8
0x18000719f  sub     rdx, [rbp+57h+var_80]
0x1800071a3  add     rdx, [rbp+57h+var_78]
0x1800071a7  mov     [rbp+57h+var_B0], rdx
0x1800071ab  mov     rax, [rbp+57h+var_40]
0x1800071af  sub     rax, [rbp+57h+pbData]
0x1800071b3  cmp     rdx, rax
0x1800071b6  jbe     short loc_1800071EA
0x1800071b8  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800071c2  cmp     rdx, rax
0x1800071c5  jbe     short loc_1800071D5
0x1800071c7  lea     rcx, aVectorTooLong; "vector too long"
0x1800071ce  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800071d5  lea     rdx, [rbp+57h+var_B0]
0x1800071d9  lea     rcx, [rbp+57h+pbData]
0x1800071dd  call    ??$_Reallocate@$0A@@?$vector@EV?$allocator@E@std@@@std@@AEAAXAEA_K@Z; std::vector<uchar>::_Reallocate<0>(unsigned __int64 &)
0x1800071e2  mov     r9, [rbp+57h+var_98+8]
0x1800071e6  mov     r8, [rbp+57h+var_98]
0x1800071ea  sub     r9, r8
0x1800071ed  mov     rdx, [rbp+57h+pbData+8]
0x1800071f1  lea     rcx, [rbp+57h+pbData]
0x1800071f5  call    ??$_Insert_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEAE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,unsigned __int64)
0x1800071fa  nop
0x1800071fb  mov     [rbp+57h+phProv], r13
0x1800071ff  mov     dword ptr [rsp+0E0h+pszNameString], 0F0000000h; dwFlags
0x180007207  mov     r9d, 18h; dwProvType
0x18000720d  xor     r8d, r8d; szProvider
0x180007210  xor     edx, edx; szContainer
0x180007212  lea     rcx, [rbp+57h+phProv]; phProv
0x180007216  call    cs:__imp_CryptAcquireContextW
0x18000721c  test    eax, eax
0x18000721e  jnz     loc_18000730E
0x180007224  call    cs:__imp_GetLastError
0x18000722a  mov     ebx, eax
0x18000722c  mov     rcx, [rbp+57h+phProv]; hProv
0x180007230  test    rcx, rcx
0x180007233  jz      short loc_18000723E
0x180007235  xor     edx, edx; dwFlags
0x180007237  call    cs:__imp_CryptReleaseContext
0x18000723d  nop
0x18000723e  mov     rcx, [rbp+57h+pbData]
0x180007242  test    rcx, rcx
0x180007245  jz      short loc_180007285
0x180007247  mov     rdx, [rbp+57h+var_40]
0x18000724b  sub     rdx, rcx
0x18000724e  mov     [rbp+57h+var_A0], rdx
0x180007252  mov     [rbp+57h+var_B0], rcx
0x180007256  cmp     rdx, 1000h
0x18000725d  jb      short loc_180007274
0x18000725f  lea     rdx, [rbp+57h+var_A0]; unsigned __int64 *
0x180007263  lea     rcx, [rbp+57h+var_B0]; void **
0x180007267  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x18000726c  mov     rdx, [rbp+57h+var_A0]; unsigned __int64
0x180007270  mov     rcx, [rbp+57h+var_B0]; void *
0x180007274  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007279  xorps   xmm0, xmm0
0x18000727c  movdqu  xmmword ptr [rbp+57h+pbData], xmm0
0x180007281  mov     [rbp+57h+var_40], r13
0x180007285  mov     rcx, [rbp+57h+var_98]
0x180007289  test    rcx, rcx
0x18000728c  jz      short loc_1800072CC
0x18000728e  mov     rdx, [rbp+57h+var_88]
0x180007292  sub     rdx, rcx
0x180007295  mov     [rbp+57h+var_B0], rdx
0x180007299  mov     [rbp+57h+var_A0], rcx
0x18000729d  cmp     rdx, 1000h
0x1800072a4  jb      short loc_1800072BB
0x1800072a6  lea     rdx, [rbp+57h+var_B0]; unsigned __int64 *
0x1800072aa  lea     rcx, [rbp+57h+var_A0]; void **
0x1800072ae  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x1800072b3  mov     rdx, [rbp+57h+var_B0]; unsigned __int64
0x1800072b7  mov     rcx, [rbp+57h+var_A0]; void *
0x1800072bb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800072c0  xorps   xmm0, xmm0
0x1800072c3  movdqu  xmmword ptr [rbp+57h+var_98], xmm0
0x1800072c8  mov     [rbp+57h+var_88], r13
0x1800072cc  mov     rcx, [rbp+57h+var_80]
0x1800072d0  test    rcx, rcx
0x1800072d3  jz      short loc_180007307
0x1800072d5  mov     rdx, [rbp+57h+var_70]
0x1800072d9  sub     rdx, rcx
0x1800072dc  mov     [rbp+57h+var_B0], rdx
0x1800072e0  mov     [rbp+57h+var_A0], rcx
0x1800072e4  cmp     rdx, 1000h
0x1800072eb  jb      short loc_180007302
0x1800072ed  lea     rdx, [rbp+57h+var_B0]; unsigned __int64 *
0x1800072f1  lea     rcx, [rbp+57h+var_A0]; void **
0x1800072f5  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x1800072fa  mov     rdx, [rbp+57h+var_B0]; unsigned __int64
0x1800072fe  mov     rcx, [rbp+57h+var_A0]; void *
0x180007302  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007307  mov     eax, ebx
0x180007309  jmp     loc_1800075AF
0x18000730e  mov     [rbp+57h+phHash], r13
0x180007312  lea     rax, [rbp+57h+phHash]
0x180007316  mov     [rsp+0E0h+pszNameString], rax; phHash
0x18000731b  xor     r9d, r9d; dwFlags
0x18000731e  xor     r8d, r8d; hKey
0x180007321  mov     edx, 800Ch; Algid
0x180007326  mov     rcx, [rbp+57h+phProv]; hProv
0x18000732a  call    cs:__imp_CryptCreateHash
0x180007330  test    eax, eax
0x180007332  jnz     short loc_18000737A
0x180007334  call    cs:__imp_GetLastError
0x18000733a  mov     ebx, eax
0x18000733c  mov     rcx, [rbp+57h+phHash]; hHash
0x180007340  test    rcx, rcx
0x180007343  jz      short loc_18000734C
0x180007345  call    cs:__imp_CryptDestroyHash
0x18000734b  nop
0x18000734c  lea     rcx, [rbp+57h+phProv]
0x180007350  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AX_K@_E$1?CryptReleaseContextNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ
0x180007355  nop
0x180007356  lea     rcx, [rbp+57h+pbData]
0x18000735a  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000735f  nop
0x180007360  lea     rcx, [rbp+57h+var_98]
0x180007364  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180007369  nop
0x18000736a  lea     rcx, [rbp+57h+var_80]
0x18000736e  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180007373  mov     eax, ebx
0x180007375  jmp     loc_1800075AF
0x18000737a  mov     rdx, [rbp+57h+pbData]; pbData
  ... truncated ...
```
