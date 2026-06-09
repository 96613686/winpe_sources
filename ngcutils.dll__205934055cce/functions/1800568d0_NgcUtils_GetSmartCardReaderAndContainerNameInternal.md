# NgcUtils::GetSmartCardReaderAndContainerNameInternal

- ea: `0x1800568d0`
- end: `0x180056b84`
- name: `NgcUtils::GetSmartCardReaderAndContainerNameInternal`
- size: `692`
- prototype: `__int64 __fastcall(LPCWSTR pszKeyName)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800567c8`

## callees

- `0x18000113c`
- `0x180003080`
- `0x18000530d`
- `0x18000cfcc`
- `0x180014458`
- `0x1800163bc`
- `0x1800568d0`

## import_xrefs

- `ncrypt!NCryptFreeObject` at `0x180056970`
- `ncrypt!NCryptFreeObject` at `0x1800569fc`
- `ncrypt!NCryptFreeObject` at `0x180056a0c`
- `ncrypt!NCryptFreeObject` at `0x180056b48`
- `ncrypt!NCryptFreeObject` at `0x180056b58`
- `ncrypt!NCryptFreeObject` at `0x180056970`
- `ncrypt!NCryptFreeObject` at `0x1800569fc`
- `ncrypt!NCryptFreeObject` at `0x180056a0c`
- `ncrypt!NCryptFreeObject` at `0x180056b48`
- `ncrypt!NCryptFreeObject` at `0x180056b58`
- `ncrypt!NCryptOpenStorageProvider` at `0x180056912`
- `ncrypt!NCryptOpenStorageProvider` at `0x180056912`
- `ncrypt!NCryptGetProperty` at `0x180056a3c`
- `ncrypt!NCryptGetProperty` at `0x180056a8d`
- `ncrypt!NCryptGetProperty` at `0x180056a3c`
- `ncrypt!NCryptGetProperty` at `0x180056a8d`
- `ncrypt!NCryptOpenKey` at `0x18005699e`
- `ncrypt!NCryptOpenKey` at `0x18005699e`

## string_xrefs

- `0x180056a31`: `NgcSCardReaderAndContainerName`
- `0x180056a82`: `NgcSCardReaderAndContainerName`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NgcUtils::GetSmartCardReaderAndContainerNameInternal(const WCHAR *pszKeyName, char **a2)
{
  SECURITY_STATUS v4; // eax
  unsigned int v5; // esi
  SECURITY_STATUS Property; // ebx
  __int16 *v8; // rdx
  SECURITY_STATUS v9; // eax
  unsigned int v10; // r14d
  PBYTE v11; // r9
  unsigned __int64 v12; // rdx
  char *v13; // rsi
  __int64 v14; // rbx
  SECURITY_STATUS v15; // [rsp+30h] [rbp-39h] BYREF
  DWORD pcbResult; // [rsp+34h] [rbp-35h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+38h] [rbp-31h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+40h] [rbp-29h] BYREF
  PBYTE pbOutput[3]; // [rsp+48h] [rbp-21h] BYREF
  _BYTE v20[32]; // [rsp+60h] [rbp-9h] BYREF
  SECURITY_STATUS *v21; // [rsp+80h] [rbp+17h]
  __int64 v22; // [rsp+88h] [rbp+1Fh]

  phProvider = 0;
  v4 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Passport Key Storage Provider", 0x40u);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( (unsigned int)dword_180075000 > 2 )
    {
      v15 = v4;
      v21 = &v15;
      v22 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_180075000, byte_180069EBD, 0, 0, 3, v20);
    }
    if ( phProvider )
      NCryptFreeObject(phProvider);
    return v5;
  }
  if ( *((_QWORD *)pszKeyName + 3) > 7u )
    pszKeyName = *(const WCHAR **)pszKeyName;
  phKey = 0;
  Property = NCryptOpenKey(phProvider, &phKey, pszKeyName, 0, 0);
  if ( Property < 0 )
  {
    if ( (unsigned int)dword_180075000 <= 2 )
    {
LABEL_13:
      if ( phKey )
        NCryptFreeObject(phKey);
      if ( phProvider )
        NCryptFreeObject(phProvider);
      return (unsigned int)Property;
    }
    v8 = (__int16 *)qword_180069E40;
LABEL_12:
    v21 = &v15;
    v15 = Property;
    v22 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_180075000, v8, 0, 0, 3, v20);
    goto LABEL_13;
  }
  pcbResult = 0;
  Property = NCryptGetProperty(phKey, L"NgcSCardReaderAndContainerName", 0, 0, &pcbResult, 0);
  if ( Property < 0 )
  {
    if ( (unsigned int)dword_180075000 <= 2 )
      goto LABEL_13;
    v8 = &word_180069E06;
    goto LABEL_12;
  }
  std::vector<unsigned char>::vector<unsigned char>(pbOutput, pcbResult);
  v9 = NCryptGetProperty(phKey, L"NgcSCardReaderAndContainerName", pbOutput[0], pcbResult, &pcbResult, 0);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v11 = pbOutput[0];
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)&pbOutput[0][2 * v12] );
    if ( v12 > (unsigned __int64)a2[3] )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(a2);
    }
    else
    {
      if ( (unsigned __int64)a2[3] <= 7 )
        v13 = (char *)a2;
      else
        v13 = *a2;
      a2[2] = (char *)v12;
      v14 = 2 * v12;
      memmove_0(v13, v11, 2 * v12);
      *(_WORD *)&v13[v14] = 0;
    }
  }
  else if ( (unsigned int)dword_180075000 > 2 )
  {
    v15 = v9;
    v21 = &v15;
    v22 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_180075000, byte_180069E65, 0, 0, 3, v20);
  }
  std::vector<unsigned char>::~vector<unsigned char>(pbOutput);
  if ( phKey )
    NCryptFreeObject(phKey);
  if ( phProvider )
    NCryptFreeObject(phProvider);
  return v10;
}

```

## disassembly

```asm
0x1800568d0  mov     [rsp-8+arg_10], rbx
0x1800568d5  push    rbp
0x1800568d6  push    rsi
0x1800568d7  push    rdi
0x1800568d8  push    r14
0x1800568da  push    r15
0x1800568dc  lea     rbp, [rsp-37h]
0x1800568e1  sub     rsp, 0A0h
0x1800568e8  mov     rax, cs:__security_cookie
0x1800568ef  xor     rax, rsp
0x1800568f2  mov     [rbp+57h+var_30], rax
0x1800568f6  mov     rdi, rdx
0x1800568f9  mov     rbx, rcx
0x1800568fc  xor     r15d, r15d
0x1800568ff  mov     [rbp+57h+phProvider], r15
0x180056903  lea     r8d, [r15+40h]; dwFlags
0x180056907  lea     rdx, pszProviderName; "Microsoft Passport Key Storage Provider"
0x18005690e  lea     rcx, [rbp+57h+phProvider]; phProvider
0x180056912  call    cs:__imp_NCryptOpenStorageProvider
0x180056918  mov     esi, eax
0x18005691a  test    eax, eax
0x18005691c  jns     short loc_18005697D
0x18005691e  mov     ecx, cs:dword_180075000
0x180056924  cmp     ecx, 2
0x180056927  jbe     short loc_180056967
0x180056929  mov     [rbp+57h+var_90], eax
0x18005692c  lea     rax, [rbp+57h+var_90]
0x180056930  mov     [rbp+57h+var_40], rax
0x180056934  mov     [rbp+57h+var_38], 4
0x18005693c  lea     rax, [rbp+57h+var_60]
0x180056940  mov     qword ptr [rsp+0C0h+var_98], rax
0x180056945  mov     [rsp+0C0h+dwFlags], 3
0x18005694d  xor     r9d, r9d
0x180056950  xor     r8d, r8d
0x180056953  lea     rdx, byte_180069EBD
0x18005695a  lea     rcx, dword_180075000
0x180056961  call    _tlgWriteTransfer_EventWriteTransfer
0x180056966  nop
0x180056967  mov     rcx, [rbp+57h+phProvider]; hObject
0x18005696b  test    rcx, rcx
0x18005696e  jz      short loc_180056976
0x180056970  call    cs:__imp_NCryptFreeObject
0x180056976  mov     eax, esi
0x180056978  jmp     loc_180056B61
0x18005697d  cmp     qword ptr [rbx+18h], 7
0x180056982  jbe     short loc_180056987
0x180056984  mov     rbx, [rbx]
0x180056987  mov     [rbp+57h+phKey], r15
0x18005698b  mov     [rsp+0C0h+dwFlags], r15d; dwFlags
0x180056990  xor     r9d, r9d; dwLegacyKeySpec
0x180056993  mov     r8, rbx; pszKeyName
0x180056996  lea     rdx, [rbp+57h+phKey]; phKey
0x18005699a  mov     rcx, [rbp+57h+phProvider]; hProvider
0x18005699e  call    cs:__imp_NCryptOpenKey
0x1800569a4  mov     ebx, eax
0x1800569a6  test    eax, eax
0x1800569a8  jns     short loc_180056A19
0x1800569aa  mov     ecx, cs:dword_180075000
0x1800569b0  cmp     ecx, 2
0x1800569b3  jbe     short loc_1800569F3
0x1800569b5  lea     rdx, qword_180069E40
0x1800569bc  lea     rax, [rbp+57h+var_90]
0x1800569c0  mov     [rbp+57h+var_40], rax
0x1800569c4  lea     rax, [rbp+57h+var_60]
0x1800569c8  mov     qword ptr [rsp+0C0h+var_98], rax
0x1800569cd  mov     [rsp+0C0h+dwFlags], 3
0x1800569d5  mov     [rbp+57h+var_90], ebx
0x1800569d8  mov     [rbp+57h+var_38], 4
0x1800569e0  xor     r9d, r9d
0x1800569e3  xor     r8d, r8d
0x1800569e6  lea     rcx, dword_180075000
0x1800569ed  call    _tlgWriteTransfer_EventWriteTransfer
0x1800569f2  nop
0x1800569f3  mov     rcx, [rbp+57h+phKey]; hObject
0x1800569f7  test    rcx, rcx
0x1800569fa  jz      short loc_180056A03
0x1800569fc  call    cs:__imp_NCryptFreeObject
0x180056a02  nop
0x180056a03  mov     rcx, [rbp+57h+phProvider]; hObject
0x180056a07  test    rcx, rcx
0x180056a0a  jz      short loc_180056A12
0x180056a0c  call    cs:__imp_NCryptFreeObject
0x180056a12  mov     eax, ebx
0x180056a14  jmp     loc_180056B61
0x180056a19  mov     [rbp+57h+pcbResult], r15d
0x180056a1d  mov     [rsp+0C0h+var_98], r15d; dwFlags
0x180056a22  lea     rax, [rbp+57h+pcbResult]
0x180056a26  mov     qword ptr [rsp+0C0h+dwFlags], rax; pcbResult
0x180056a2b  xor     r9d, r9d; cbOutput
0x180056a2e  xor     r8d, r8d; pbOutput
0x180056a31  lea     rdx, aNgcscardreader; "NgcSCardReaderAndContainerName"
0x180056a38  mov     rcx, [rbp+57h+phKey]; hObject
0x180056a3c  call    cs:__imp_NCryptGetProperty
0x180056a42  mov     ebx, eax
0x180056a44  test    eax, eax
0x180056a46  jns     short loc_180056A5F
0x180056a48  mov     ecx, cs:dword_180075000
0x180056a4e  cmp     ecx, 2
0x180056a51  jbe     short loc_1800569F3
0x180056a53  lea     rdx, word_180069E06
0x180056a5a  jmp     loc_1800569BC
0x180056a5f  mov     edx, [rbp+57h+pcbResult]
0x180056a62  lea     rcx, [rbp+57h+pbOutput]
0x180056a66  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180056a6b  nop
0x180056a6c  mov     [rsp+0C0h+var_98], r15d; dwFlags
0x180056a71  lea     rax, [rbp+57h+pcbResult]
0x180056a75  mov     qword ptr [rsp+0C0h+dwFlags], rax; pcbResult
0x180056a7a  mov     r9d, [rbp+57h+pcbResult]; cbOutput
0x180056a7e  mov     r8, [rbp+57h+pbOutput]; pbOutput
0x180056a82  lea     rdx, aNgcscardreader; "NgcSCardReaderAndContainerName"
0x180056a89  mov     rcx, [rbp+57h+phKey]; hObject
0x180056a8d  call    cs:__imp_NCryptGetProperty
0x180056a93  mov     r14d, eax
0x180056a96  test    eax, eax
0x180056a98  jns     short loc_180056AE8
0x180056a9a  mov     ecx, cs:dword_180075000
0x180056aa0  cmp     ecx, 2
0x180056aa3  jbe     loc_180056B35
0x180056aa9  mov     [rbp+57h+var_90], eax
0x180056aac  lea     rax, [rbp+57h+var_90]
0x180056ab0  mov     [rbp+57h+var_40], rax
0x180056ab4  mov     [rbp+57h+var_38], 4
0x180056abc  lea     rax, [rbp+57h+var_60]
0x180056ac0  mov     qword ptr [rsp+0C0h+var_98], rax
0x180056ac5  mov     [rsp+0C0h+dwFlags], 3
0x180056acd  xor     r9d, r9d
0x180056ad0  xor     r8d, r8d
0x180056ad3  lea     rdx, byte_180069E65
0x180056ada  lea     rcx, dword_180075000
0x180056ae1  call    _tlgWriteTransfer_EventWriteTransfer
0x180056ae6  jmp     short loc_180056B35
0x180056ae8  mov     r9, [rbp+57h+pbOutput]
0x180056aec  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180056af0  inc     rdx
0x180056af3  cmp     [r9+rdx*2], r15w
0x180056af8  jnz     short loc_180056AF0
0x180056afa  cmp     rdx, [rdi+18h]
0x180056afe  ja      short loc_180056B2C
0x180056b00  cmp     qword ptr [rdi+18h], 7
0x180056b05  jbe     short loc_180056B0C
0x180056b07  mov     rsi, [rdi]
0x180056b0a  jmp     short loc_180056B0F
0x180056b0c  mov     rsi, rdi
0x180056b0f  mov     [rdi+10h], rdx
0x180056b13  lea     rbx, [rdx+rdx]
0x180056b17  mov     r8, rbx; Size
0x180056b1a  mov     rdx, r9; Src
0x180056b1d  mov     rcx, rsi; void *
0x180056b20  call    memmove_0
0x180056b25  mov     [rbx+rsi], r15w
0x180056b2a  jmp     short loc_180056B35
0x180056b2c  mov     rcx, rdi
0x180056b2f  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180056b34  nop
0x180056b35  lea     rcx, [rbp+57h+pbOutput]
0x180056b39  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180056b3e  nop
0x180056b3f  mov     rcx, [rbp+57h+phKey]; hObject
0x180056b43  test    rcx, rcx
0x180056b46  jz      short loc_180056B4F
0x180056b48  call    cs:__imp_NCryptFreeObject
0x180056b4e  nop
0x180056b4f  mov     rcx, [rbp+57h+phProvider]; hObject
0x180056b53  test    rcx, rcx
0x180056b56  jz      short loc_180056B5E
0x180056b58  call    cs:__imp_NCryptFreeObject
0x180056b5e  mov     eax, r14d
0x180056b61  mov     rcx, [rbp+57h+var_30]
0x180056b65  xor     rcx, rsp; StackCookie
0x180056b68  call    __security_check_cookie
0x180056b6d  mov     rbx, [rsp+0C0h+arg_10]
0x180056b75  add     rsp, 0A0h
0x180056b7c  pop     r15
0x180056b7e  pop     r14
0x180056b80  pop     rdi
0x180056b81  pop     rsi
0x180056b82  pop     rbp
0x180056b83  retn
```
