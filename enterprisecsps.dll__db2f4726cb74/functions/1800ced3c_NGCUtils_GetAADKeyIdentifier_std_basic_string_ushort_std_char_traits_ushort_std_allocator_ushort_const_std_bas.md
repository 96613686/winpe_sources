# NGCUtils::GetAADKeyIdentifier(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800ced3c`
- end: `0x1800cf274`
- name: `?GetAADKeyIdentifier@NGCUtils@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z`
- size: `1336`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18007eed0`

## callees

- `0x18000d4b4`
- `0x18000d4d4`
- `0x18002031c`
- `0x1800232e4`
- `0x180023fa0`
- `0x180065770`
- `0x1800657d4`
- `0x180083ca8`
- `0x180083d18`
- `0x1800ced3c`

## import_xrefs

- `CRYPT32!CryptExportPublicKeyInfo` at `0x1800cee70`
- `CRYPT32!CryptExportPublicKeyInfo` at `0x1800ceefd`
- `CRYPT32!CryptExportPublicKeyInfo` at `0x1800cee70`
- `CRYPT32!CryptExportPublicKeyInfo` at `0x1800ceefd`
- `CRYPT32!CryptHashCertificate2` at `0x1800cef9a`
- `CRYPT32!CryptHashCertificate2` at `0x1800cf044`
- `CRYPT32!CryptHashCertificate2` at `0x1800cef9a`
- `CRYPT32!CryptHashCertificate2` at `0x1800cf044`
- `CRYPT32!CryptBinaryToStringW` at `0x1800cf0de`
- `CRYPT32!CryptBinaryToStringW` at `0x1800cf18f`
- `CRYPT32!CryptBinaryToStringW` at `0x1800cf0de`
- `CRYPT32!CryptBinaryToStringW` at `0x1800cf18f`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800ced77`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800ced77`
- `ncrypt!NCryptFreeObject` at `0x1800cee1e`
- `ncrypt!NCryptFreeObject` at `0x1800ceea0`
- `ncrypt!NCryptFreeObject` at `0x1800ceeb2`
- `ncrypt!NCryptFreeObject` at `0x1800cef38`
- `ncrypt!NCryptFreeObject` at `0x1800cef4a`
- `ncrypt!NCryptFreeObject` at `0x1800cefd5`
- `ncrypt!NCryptFreeObject` at `0x1800cefe7`
- `ncrypt!NCryptFreeObject` at `0x1800cf08a`
- `ncrypt!NCryptFreeObject` at `0x1800cf09c`
- `ncrypt!NCryptFreeObject` at `0x1800cf124`
- `ncrypt!NCryptFreeObject` at `0x1800cf136`
- `ncrypt!NCryptFreeObject` at `0x1800cf1e3`
- `ncrypt!NCryptFreeObject` at `0x1800cf1f5`
- `ncrypt!NCryptFreeObject` at `0x1800cf23f`
- `ncrypt!NCryptFreeObject` at `0x1800cf251`
- `ncrypt!NCryptFreeObject` at `0x1800cee1e`
- `ncrypt!NCryptFreeObject` at `0x1800ceea0`
- `ncrypt!NCryptFreeObject` at `0x1800ceeb2`
- `ncrypt!NCryptFreeObject` at `0x1800cef38`
- `ncrypt!NCryptFreeObject` at `0x1800cef4a`
- `ncrypt!NCryptFreeObject` at `0x1800cefd5`
- `ncrypt!NCryptFreeObject` at `0x1800cefe7`
- `ncrypt!NCryptFreeObject` at `0x1800cf08a`
- `ncrypt!NCryptFreeObject` at `0x1800cf09c`
- `ncrypt!NCryptFreeObject` at `0x1800cf124`
- `ncrypt!NCryptFreeObject` at `0x1800cf136`
- `ncrypt!NCryptFreeObject` at `0x1800cf1e3`
- `ncrypt!NCryptFreeObject` at `0x1800cf1f5`
- `ncrypt!NCryptFreeObject` at `0x1800cf23f`
- `ncrypt!NCryptFreeObject` at `0x1800cf251`
- `ncrypt!NCryptOpenKey` at `0x1800cedea`
- `ncrypt!NCryptOpenKey` at `0x1800cedea`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall NGCUtils::GetAADKeyIdentifier(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax
  SECURITY_STATUS v6; // eax
  unsigned int v7; // ebx
  const WCHAR *v8; // rax
  SECURITY_STATUS v9; // eax
  unsigned int v10; // ebx
  const char *v11; // r9
  unsigned int v12; // ebx
  const char *v13; // r9
  unsigned int v14; // ebx
  const char *v15; // r9
  PCERT_PUBLIC_KEY_INFO v16; // rbx
  const char *v17; // r9
  unsigned int v18; // ebx
  const char *v19; // r9
  unsigned int v20; // ebx
  const char *v21; // r9
  unsigned int v22; // ebx
  const char *v23; // r9
  unsigned int LastError; // ebx
  int dwFlags; // [rsp+20h] [rbp-B8h]
  int dwFlagsa; // [rsp+20h] [rbp-B8h]
  NCRYPT_KEY_HANDLE phKey; // [rsp+40h] [rbp-98h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+48h] [rbp-90h] BYREF
  PCERT_PUBLIC_KEY_INFO pInfo[3]; // [rsp+50h] [rbp-88h] BYREF
  BYTE *pbBinary[3]; // [rsp+68h] [rbp-70h] BYREF
  LPWSTR pszString[4]; // [rsp+80h] [rbp-58h] BYREF
  char v32; // [rsp+A0h] [rbp-38h]
  NCRYPT_KEY_HANDLE *p_phKey; // [rsp+A8h] [rbp-30h]
  char v34; // [rsp+B0h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]
  __int64 cbBinary; // [rsp+E0h] [rbp+8h] BYREF
  DWORD pcbInfo; // [rsp+E8h] [rbp+10h] BYREF
  DWORD pcchString; // [rsp+F8h] [rbp+20h] BYREF

  cbBinary = a1;
  if ( !*(_QWORD *)(a2 + 16) )
    return 0;
  phProvider = 0;
  v6 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Passport Key Storage Provider", 0);
  v7 = v6;
  if ( v6 >= 0 )
  {
    pszString[3] = (LPWSTR)&phProvider;
    v32 = 1;
    phKey = 0;
    v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    v9 = NCryptOpenKey(phProvider, &phKey, v8, 0, 0);
    v10 = v9;
    if ( v9 >= 0 )
    {
      p_phKey = &phKey;
      v34 = 1;
      pcbInfo = 0;
      if ( CryptExportPublicKeyInfo(phKey, 0, 0x10001u, 0, &pcbInfo) )
      {
        std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>(pInfo);
        try
        {
          std::vector<unsigned char>::resize(pInfo, pcbInfo);
          if ( CryptExportPublicKeyInfo(phKey, 0, 0x10001u, pInfo[0], &pcbInfo) )
          {
            v16 = pInfo[0];
            LODWORD(cbBinary) = 0;
            if ( CryptHashCertificate2(
                   L"SHA256",
                   0,
                   0,
                   pInfo[0]->PublicKey.pbData,
                   pInfo[0]->PublicKey.cbData,
                   0,
                   (DWORD *)&cbBinary) )
            {
              std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>(pbBinary);
              std::vector<unsigned char>::resize(pbBinary, (unsigned int)cbBinary);
              if ( CryptHashCertificate2(
                     L"SHA256",
                     0,
                     0,
                     v16->PublicKey.pbData,
                     v16->PublicKey.cbData,
                     pbBinary[0],
                     (DWORD *)&cbBinary) )
              {
                pcchString = 0;
                if ( CryptBinaryToStringW(pbBinary[0], cbBinary, 0x4000000Cu, 0, &pcchString) )
                {
                  std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>(pszString);
                  std::vector<unsigned short>::resize(pszString, pcchString);
                  if ( CryptBinaryToStringW(pbBinary[0], cbBinary, 0x4000000Cu, pszString[0], &pcchString) )
                  {
                    std::wstring::operator=(a3, pszString[0]);
                    std::vector<unsigned short>::_Tidy(pszString);
                    std::vector<unsigned char>::_Tidy(pbBinary);
                    std::vector<unsigned char>::_Tidy(pInfo);
                    NCryptFreeObject(phKey);
                    NCryptFreeObject(phProvider);
                    result = 0;
                  }
                  else
                  {
                    LastError = wil::details::in1diag3::Return_GetLastError(
                                  retaddr,
                                  (void *)0x18C,
                                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\ngcutils\\ngcutils.cpp",
                                  v23);
                    std::vector<unsigned short>::_Tidy(pszString);
                    std::vector<unsigned char>::_Tidy(pbBinary);
                    std::vector<unsigned char>::_Tidy(pInfo);
                    NCryptFreeObject(phKey);
                    NCryptFreeObject(phProvider);
                    result = LastError;
                  }
                }
                else
                {
                  v22 = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x187,
                          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\ngcutils\\ngcutils.cpp",
                          v21);
                  std::vector<unsigned char>::_Tidy(pbBinary);
                  std::vector<unsigned char>::_Tidy(pInfo);
                  NCryptFreeObject(phKey);
                  NCryptFreeObject(phProvider);
                  result = v22;
                }
              }
              else
              {
                v20 = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x17F,
                        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\ngcutils\\ngcutils.cpp",
                        v19);
                std::vector<unsigned char>::_Tidy(pbBinary);
                std::vector<unsigned char>::_Tidy(pInfo);
                NCryptFreeObject(phKey);
                NCryptFreeObject(phProvider);
                result = v20;
              }
            }
            else
            {
              v18 = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x17A,
                      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\ngcutils\\ngcutils.cpp",
                      v17);
              std::vector<unsigned char>::_Tidy(pInfo);
              NCryptFreeObject(phKey);
              NCryptFreeObject(phProvider);
              result = v18;
            }
          }
          else
          {
            v14 = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x173,
                    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\ngcutils\\ngcutils.cpp",
                    v13);
            std::vector<unsigned char>::_Tidy(pInfo);
            NCryptFreeObject(phKey);
            NCryptFreeObject(phProvider);
            result = v14;
          }
        }
        catch ( ... )
        {
          LODWORD(cbBinary) = wil::details::in1diag3::Return_CaughtException(
                                retaddr,
                                (void *)0x195,
                                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\ngcutils\\ngcutils.cpp",
                                v15);
          return (unsigned int)cbBinary;
        }
      }
      else
      {
        v12 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x16E,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\ngcutils\\ngcutils.cpp",
                v11);
        NCryptFreeObject(phKey);
        NCryptFreeObject(phProvider);
        return v12;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x163,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\ngcutils\\ngcutils.cpp",
        (const char *)(unsigned int)v9,
        dwFlagsa);
      NCryptFreeObject(phProvider);
      return v10;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15A,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\ngcutils\\ngcutils.cpp",
      (const char *)(unsigned int)v6,
      dwFlags);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x1800ced3c  mov     [rsp+cbBinary], rcx
0x1800ced41  push    rbx
0x1800ced42  push    rsi
0x1800ced43  push    rdi
0x1800ced44  sub     rsp, 0C0h
0x1800ced4b  mov     rsi, r8
0x1800ced4e  mov     rdi, rdx
0x1800ced51  cmp     qword ptr [rdx+10h], 0
0x1800ced56  jnz     short loc_1800CED5F
0x1800ced58  xor     eax, eax
0x1800ced5a  jmp     loc_1800CF268
0x1800ced5f  mov     [rsp+0D8h+phProvider], 0
0x1800ced68  xor     r8d, r8d; dwFlags
0x1800ced6b  lea     rdx, aMicrosoftPassp; "Microsoft Passport Key Storage Provider"
0x1800ced72  lea     rcx, [rsp+0D8h+phProvider]; phProvider
0x1800ced77  call    cs:__imp_NCryptOpenStorageProvider
0x1800ced7e  nop     dword ptr [rax+rax+00h]
0x1800ced83  mov     ebx, eax
0x1800ced85  test    eax, eax
0x1800ced87  jns     short loc_1800CEDAC
0x1800ced89  mov     rcx, [rsp+0D8h]; this
0x1800ced91  mov     r9d, eax; char *
0x1800ced94  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800ced9b  mov     edx, 15Ah; void *
0x1800ceda0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ceda5  mov     eax, ebx
0x1800ceda7  jmp     loc_1800CF268
0x1800cedac  lea     rax, [rsp+0D8h+phProvider]
0x1800cedb1  mov     [rsp+0D8h+var_40], rax
0x1800cedb9  mov     [rsp+0D8h+var_38], 1
0x1800cedc1  mov     [rsp+0D8h+phKey], 0
0x1800cedca  mov     rcx, rdi
0x1800cedcd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800cedd2  mov     [rsp+0D8h+dwFlags], 0; int
0x1800cedda  xor     r9d, r9d; dwLegacyKeySpec
0x1800ceddd  mov     r8, rax; pszKeyName
0x1800cede0  lea     rdx, [rsp+0D8h+phKey]; phKey
0x1800cede5  mov     rcx, [rsp+0D8h+phProvider]; hProvider
0x1800cedea  call    cs:__imp_NCryptOpenKey
0x1800cedf1  nop     dword ptr [rax+rax+00h]
0x1800cedf6  mov     ebx, eax
0x1800cedf8  test    eax, eax
0x1800cedfa  jns     short loc_1800CEE31
0x1800cedfc  mov     rcx, [rsp+0D8h]; this
0x1800cee04  mov     r9d, eax; char *
0x1800cee07  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800cee0e  mov     edx, 163h; void *
0x1800cee13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cee18  nop
0x1800cee19  mov     rcx, [rsp+0D8h+phProvider]; hObject
0x1800cee1e  call    cs:__imp_NCryptFreeObject
0x1800cee25  nop     dword ptr [rax+rax+00h]
0x1800cee2a  mov     eax, ebx
0x1800cee2c  jmp     loc_1800CF268
0x1800cee31  lea     rax, [rsp+0D8h+phKey]
0x1800cee36  mov     [rsp+0D8h+var_30], rax
0x1800cee3e  mov     [rsp+0D8h+var_28], 1
0x1800cee46  mov     [rsp+0D8h+pcbInfo], 0
0x1800cee51  lea     rax, [rsp+0D8h+pcbInfo]
0x1800cee59  mov     qword ptr [rsp+0D8h+dwFlags], rax; pcbInfo
0x1800cee5e  xor     r9d, r9d; pInfo
0x1800cee61  mov     ebx, 10001h
0x1800cee66  mov     r8d, ebx; dwCertEncodingType
0x1800cee69  xor     edx, edx; dwKeySpec
0x1800cee6b  mov     rcx, [rsp+0D8h+phKey]; hCryptProvOrNCryptKey
0x1800cee70  call    cs:__imp_CryptExportPublicKeyInfo
0x1800cee77  nop     dword ptr [rax+rax+00h]
0x1800cee7c  test    eax, eax
0x1800cee7e  jnz     short loc_1800CEEC5
0x1800cee80  mov     rcx, [rsp+0D8h]; this
0x1800cee88  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800cee8f  mov     edx, 16Eh; void *
0x1800cee94  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800cee99  mov     ebx, eax
0x1800cee9b  mov     rcx, [rsp+0D8h+phKey]; hObject
0x1800ceea0  call    cs:__imp_NCryptFreeObject
0x1800ceea7  nop     dword ptr [rax+rax+00h]
0x1800ceeac  nop
0x1800ceead  mov     rcx, [rsp+0D8h+phProvider]; hObject
0x1800ceeb2  call    cs:__imp_NCryptFreeObject
0x1800ceeb9  nop     dword ptr [rax+rax+00h]
0x1800ceebe  mov     eax, ebx
0x1800ceec0  jmp     loc_1800CF268
0x1800ceec5  lea     rcx, [rsp+0D8h+pInfo]
0x1800ceeca  call    ??0?$vector@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@V?$allocator@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@3@@std@@QEAA@XZ; std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t>>::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t>>(void)
0x1800ceecf  nop
0x1800ceed0  mov     edx, [rsp+0D8h+pcbInfo]
0x1800ceed7  lea     rcx, [rsp+0D8h+pInfo]
0x1800ceedc  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x1800ceee1  lea     rax, [rsp+0D8h+pcbInfo]
0x1800ceee9  mov     qword ptr [rsp+0D8h+dwFlags], rax; pcbInfo
0x1800ceeee  mov     r9, [rsp+0D8h+pInfo]; pInfo
0x1800ceef3  mov     r8d, ebx; dwCertEncodingType
0x1800ceef6  xor     edx, edx; dwKeySpec
0x1800ceef8  mov     rcx, [rsp+0D8h+phKey]; hCryptProvOrNCryptKey
0x1800ceefd  call    cs:__imp_CryptExportPublicKeyInfo
0x1800cef04  nop     dword ptr [rax+rax+00h]
0x1800cef09  test    eax, eax
0x1800cef0b  jnz     short loc_1800CEF5D
0x1800cef0d  mov     rcx, [rsp+0D8h]; this
0x1800cef15  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800cef1c  mov     edx, 173h; void *
0x1800cef21  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800cef26  mov     ebx, eax
0x1800cef28  lea     rcx, [rsp+0D8h+pInfo]
0x1800cef2d  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800cef32  nop
0x1800cef33  mov     rcx, [rsp+0D8h+phKey]; hObject
0x1800cef38  call    cs:__imp_NCryptFreeObject
0x1800cef3f  nop     dword ptr [rax+rax+00h]
0x1800cef44  nop
0x1800cef45  mov     rcx, [rsp+0D8h+phProvider]; hObject
0x1800cef4a  call    cs:__imp_NCryptFreeObject
0x1800cef51  nop     dword ptr [rax+rax+00h]
0x1800cef56  mov     eax, ebx
0x1800cef58  jmp     loc_1800CF268
0x1800cef5d  mov     rbx, [rsp+0D8h+pInfo]
0x1800cef62  mov     dword ptr [rsp+0D8h+cbBinary], 0
0x1800cef6d  lea     rax, [rsp+0D8h+cbBinary]
0x1800cef75  mov     [rsp+0D8h+pcbComputedHash], rax; pcbComputedHash
0x1800cef7a  mov     [rsp+0D8h+pbComputedHash], 0; pbComputedHash
0x1800cef83  mov     eax, [rbx+18h]
0x1800cef86  mov     [rsp+0D8h+dwFlags], eax; cbEncoded
0x1800cef8a  mov     r9, [rbx+20h]; pbEncoded
0x1800cef8e  xor     r8d, r8d; pvReserved
0x1800cef91  xor     edx, edx; dwFlags
0x1800cef93  lea     rcx, aSha256; "SHA256"
0x1800cef9a  call    cs:__imp_CryptHashCertificate2
0x1800cefa1  nop     dword ptr [rax+rax+00h]
0x1800cefa6  test    eax, eax
0x1800cefa8  jnz     short loc_1800CEFFA
0x1800cefaa  mov     rcx, [rsp+0D8h]; this
0x1800cefb2  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800cefb9  mov     edx, 17Ah; void *
0x1800cefbe  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800cefc3  mov     ebx, eax
0x1800cefc5  lea     rcx, [rsp+0D8h+pInfo]
0x1800cefca  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800cefcf  nop
0x1800cefd0  mov     rcx, [rsp+0D8h+phKey]; hObject
0x1800cefd5  call    cs:__imp_NCryptFreeObject
0x1800cefdc  nop     dword ptr [rax+rax+00h]
0x1800cefe1  nop
0x1800cefe2  mov     rcx, [rsp+0D8h+phProvider]; hObject
0x1800cefe7  call    cs:__imp_NCryptFreeObject
0x1800cefee  nop     dword ptr [rax+rax+00h]
0x1800ceff3  mov     eax, ebx
0x1800ceff5  jmp     loc_1800CF268
0x1800ceffa  lea     rcx, [rsp+0D8h+pbBinary]
0x1800cefff  call    ??0?$vector@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@V?$allocator@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@3@@std@@QEAA@XZ; std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t>>::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t>>(void)
0x1800cf004  nop
0x1800cf005  mov     edx, dword ptr [rsp+0D8h+cbBinary]
0x1800cf00c  lea     rcx, [rsp+0D8h+pbBinary]
0x1800cf011  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x1800cf016  mov     rax, [rsp+0D8h+pbBinary]
0x1800cf01b  lea     rdx, [rsp+0D8h+cbBinary]
0x1800cf023  mov     [rsp+0D8h+pcbComputedHash], rdx; pcbComputedHash
0x1800cf028  mov     [rsp+0D8h+pbComputedHash], rax; pbComputedHash
0x1800cf02d  mov     eax, [rbx+18h]
0x1800cf030  mov     [rsp+0D8h+dwFlags], eax; cbEncoded
0x1800cf034  mov     r9, [rbx+20h]; pbEncoded
0x1800cf038  xor     r8d, r8d; pvReserved
0x1800cf03b  xor     edx, edx; dwFlags
0x1800cf03d  lea     rcx, aSha256; "SHA256"
0x1800cf044  call    cs:__imp_CryptHashCertificate2
0x1800cf04b  nop     dword ptr [rax+rax+00h]
0x1800cf050  test    eax, eax
0x1800cf052  jnz     short loc_1800CF0AF
0x1800cf054  mov     rcx, [rsp+0D8h]; this
0x1800cf05c  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800cf063  mov     edx, 17Fh; void *
0x1800cf068  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800cf06d  mov     ebx, eax
0x1800cf06f  lea     rcx, [rsp+0D8h+pbBinary]
0x1800cf074  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800cf079  nop
0x1800cf07a  lea     rcx, [rsp+0D8h+pInfo]
0x1800cf07f  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800cf084  nop
0x1800cf085  mov     rcx, [rsp+0D8h+phKey]; hObject
0x1800cf08a  call    cs:__imp_NCryptFreeObject
0x1800cf091  nop     dword ptr [rax+rax+00h]
0x1800cf096  nop
0x1800cf097  mov     rcx, [rsp+0D8h+phProvider]; hObject
0x1800cf09c  call    cs:__imp_NCryptFreeObject
0x1800cf0a3  nop     dword ptr [rax+rax+00h]
0x1800cf0a8  mov     eax, ebx
0x1800cf0aa  jmp     loc_1800CF268
0x1800cf0af  mov     [rsp+0D8h+pcchString], 0
0x1800cf0ba  lea     rax, [rsp+0D8h+pcchString]
0x1800cf0c2  mov     qword ptr [rsp+0D8h+dwFlags], rax; pcchString
0x1800cf0c7  xor     r9d, r9d; pszString
0x1800cf0ca  mov     ebx, 4000000Ch
0x1800cf0cf  mov     r8d, ebx; dwFlags
0x1800cf0d2  mov     edx, dword ptr [rsp+0D8h+cbBinary]; cbBinary
0x1800cf0d9  mov     rcx, [rsp+0D8h+pbBinary]; pbBinary
0x1800cf0de  call    cs:__imp_CryptBinaryToStringW
0x1800cf0e5  nop     dword ptr [rax+rax+00h]
0x1800cf0ea  test    eax, eax
0x1800cf0ec  jnz     short loc_1800CF149
0x1800cf0ee  mov     rcx, [rsp+0D8h]; this
0x1800cf0f6  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800cf0fd  mov     edx, 187h; void *
0x1800cf102  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800cf107  mov     ebx, eax
0x1800cf109  lea     rcx, [rsp+0D8h+pbBinary]
0x1800cf10e  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800cf113  nop
0x1800cf114  lea     rcx, [rsp+0D8h+pInfo]
0x1800cf119  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800cf11e  nop
0x1800cf11f  mov     rcx, [rsp+0D8h+phKey]; hObject
0x1800cf124  call    cs:__imp_NCryptFreeObject
0x1800cf12b  nop     dword ptr [rax+rax+00h]
0x1800cf130  nop
0x1800cf131  mov     rcx, [rsp+0D8h+phProvider]; hObject
0x1800cf136  call    cs:__imp_NCryptFreeObject
0x1800cf13d  nop     dword ptr [rax+rax+00h]
0x1800cf142  mov     eax, ebx
0x1800cf144  jmp     loc_1800CF268
0x1800cf149  lea     rcx, [rsp+0D8h+pszString]
0x1800cf151  call    ??0?$vector@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@V?$allocator@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@3@@std@@QEAA@XZ; std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t>>::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t>>(void)
0x1800cf156  nop
0x1800cf157  mov     edx, [rsp+0D8h+pcchString]
0x1800cf15e  lea     rcx, [rsp+0D8h+pszString]
0x1800cf166  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800cf16b  lea     rax, [rsp+0D8h+pcchString]
0x1800cf173  mov     qword ptr [rsp+0D8h+dwFlags], rax; pcchString
0x1800cf178  mov     r9, [rsp+0D8h+pszString]; pszString
0x1800cf180  mov     r8d, ebx; dwFlags
0x1800cf183  mov     edx, dword ptr [rsp+0D8h+cbBinary]; cbBinary
0x1800cf18a  mov     rcx, [rsp+0D8h+pbBinary]; pbBinary
0x1800cf18f  call    cs:__imp_CryptBinaryToStringW
0x1800cf196  nop     dword ptr [rax+rax+00h]
0x1800cf19b  test    eax, eax
0x1800cf19d  jnz     short loc_1800CF205
0x1800cf19f  mov     rcx, [rsp+0D8h]; this
0x1800cf1a7  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800cf1ae  mov     edx, 18Ch; void *
0x1800cf1b3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800cf1b8  mov     ebx, eax
0x1800cf1ba  lea     rcx, [rsp+0D8h+pszString]
0x1800cf1c2  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800cf1c7  nop
0x1800cf1c8  lea     rcx, [rsp+0D8h+pbBinary]
0x1800cf1cd  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800cf1d2  nop
0x1800cf1d3  lea     rcx, [rsp+0D8h+pInfo]
0x1800cf1d8  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800cf1dd  nop
0x1800cf1de  mov     rcx, [rsp+0D8h+phKey]; hObject
0x1800cf1e3  call    cs:__imp_NCryptFreeObject
0x1800cf1ea  nop     dword ptr [rax+rax+00h]
0x1800cf1ef  nop
0x1800cf1f0  mov     rcx, [rsp+0D8h+phProvider]; hObject
0x1800cf1f5  call    cs:__imp_NCryptFreeObject
0x1800cf1fc  nop     dword ptr [rax+rax+00h]
0x1800cf201  mov     eax, ebx
0x1800cf203  jmp     short loc_1800CF268
0x1800cf205  mov     rdx, [rsp+0D8h+pszString]
0x1800cf20d  mov     rcx, rsi
0x1800cf210  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x1800cf215  nop
0x1800cf216  lea     rcx, [rsp+0D8h+pszString]
0x1800cf21e  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800cf223  nop
0x1800cf224  lea     rcx, [rsp+0D8h+pbBinary]
0x1800cf229  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800cf22e  nop
0x1800cf22f  lea     rcx, [rsp+0D8h+pInfo]
0x1800cf234  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800cf239  nop
0x1800cf23a  mov     rcx, [rsp+0D8h+phKey]; hObject
0x1800cf23f  call    cs:__imp_NCryptFreeObject
0x1800cf246  nop     dword ptr [rax+rax+00h]
0x1800cf24b  nop
0x1800cf24c  mov     rcx, [rsp+0D8h+phProvider]; hObject
0x1800cf251  call    cs:__imp_NCryptFreeObject
0x1800cf258  nop     dword ptr [rax+rax+00h]
0x1800cf25d  xor     eax, eax
0x1800cf25f  jmp     short loc_1800CF268
0x1800cf261  mov     eax, dword ptr [rsp+0D8h+cbBinary]
0x1800cf268  add     rsp, 0C0h
0x1800cf26f  pop     rdi
0x1800cf270  pop     rsi
0x1800cf271  pop     rbx
0x1800cf272  retn
```
