# GetExternalHashAlgorithms

- ea: `0x1800859f8`
- end: `0x180085cb1`
- name: `GetExternalHashAlgorithms`
- size: `697`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180046720`
- `0x180082418`

## callees

- `0x1800023e0`
- `0x180003c70`
- `0x180003f70`
- `0x180006470`
- `0x180045440`
- `0x180084d38`
- `0x180084d9c`
- `0x180084e5c`
- `0x180084f50`
- `0x180084f84`
- `0x18008597c`
- `0x1800859f8`
- `0x18009f650`
- `0x18009fa80`

## import_xrefs

- `ntoskrnl!ZwEnumerateKey` at `0x180085ad3`
- `ntoskrnl!ZwEnumerateKey` at `0x180085ad3`
- `ntoskrnl!wcscpy_s` at `0x180085c29`
- `ntoskrnl!wcscpy_s` at `0x180085c29`

## string_xrefs

- `0x180085a7d`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Hash`
- `0x180085b1f`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Hash`

## pseudocode

```c
__int64 GetExternalHashAlgorithms()
{
  __int64 result; // rax
  __int64 v1; // r9
  ULONG i; // edi
  unsigned __int64 v3; // rdx
  unsigned __int64 v4; // r9
  __int64 v5; // r9
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rdx
  wchar_t **v10; // rbx
  __int64 v11; // r8
  __int64 v12; // r9
  wchar_t *v13; // rax
  __int64 v14; // rcx
  UCHAR pbOutput[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v16; // [rsp+34h] [rbp-CCh]
  HANDLE v17; // [rsp+38h] [rbp-C8h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp-C0h] BYREF
  ULONG ResultLength; // [rsp+48h] [rbp-B8h] BYREF
  ULONG pcbResult; // [rsp+4Ch] [rbp-B4h] BYREF
  HANDLE KeyHandle[2]; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD KeyInformation[136]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszAlgId[64]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR v24[64]; // [rsp+300h] [rbp+200h] BYREF

  KeyHandle[0] = 0;
  v17 = 0;
  memset(v24, 0, sizeof(v24));
  memset(pszAlgId, 0, sizeof(pszAlgId));
  *(_DWORD *)pbOutput = 0;
  phAlgorithm = 0;
  pcbResult = 0;
  v16 = 0;
  result = FreeExternalHashAlgorithms();
  if ( (unsigned int)g_dwHashInfoTotalCount < 0x10 )
  {
    result = TlsOpenRegKey(
               L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Protocol Provider\\Hash",
               0,
               KeyHandle,
               v1);
    if ( (int)result >= 0 )
    {
      for ( i = 0; (unsigned int)g_dwHashInfoTotalCount < 0x10; ++i )
      {
        memset(KeyInformation, 0, 536);
        ResultLength = 0;
        if ( ZwEnumerateKey(KeyHandle[0], i, KeyBasicInformation, KeyInformation, 0x218u, &ResultLength) < 0 )
          break;
        v4 = -1;
        do
          ++v4;
        while ( *((_WORD *)&KeyInformation[4] + v4) );
        if ( (int)RtlStringCchCopyNW(v24, v3, (const unsigned __int16 *)&KeyInformation[4], v4) >= 0
          && (int)TlsOpenRegKey(
                    L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Prot"
                     "ocol Provider\\Hash",
                    v24,
                    &v17,
                    v5) >= 0 )
        {
          if ( (int)GetSslStringFromRegistry(v17, L"CngAlgorithm", pszAlgId) < 0
            || (int)GetSslDWordFromRegistry(v17) < 0 )
          {
            TlsCloseRegKey(&v17);
          }
          else
          {
            TlsCloseRegKey(&v17);
            if ( BCryptOpenAlgorithmProvider(&phAlgorithm, pszAlgId, 0, 0) >= 0 )
            {
              if ( BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0) >= 0 )
              {
                BCryptCloseAlgorithmProvider(phAlgorithm, 0);
                v10 = (wchar_t **)MSCryptAlloc(24, v6, v7, v8);
                if ( v10 )
                {
                  *(_OWORD *)v10 = 0;
                  v10[2] = 0;
                  v13 = (wchar_t *)MSCryptAlloc(128, v9, v11, v12);
                  *v10 = v13;
                  if ( v13 )
                  {
                    wcscpy_s(v13, 0x40u, pszAlgId);
                    v14 = (unsigned int)g_dwHashInfoTotalCount;
                    *((_DWORD *)v10 + 2) = *(_DWORD *)pbOutput;
                    g_pHashInfo[v14] = (__int64)v10;
                    *((_DWORD *)v10 + 4) = v14 + 36857;
                    *((_DWORD *)v10 + 3) = v14 - 268435462;
                    *((_DWORD *)v10 + 5) = v16;
                    g_dwHashInfoTotalCount = v14 + 1;
                  }
                  else
                  {
                    MSCryptFree(v10);
                  }
                }
              }
              else
              {
                BCryptCloseAlgorithmProvider(phAlgorithm, 0);
              }
            }
          }
        }
      }
      return TlsCloseRegKey(KeyHandle);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800859f8  push    rbp
0x1800859fa  push    rbx
0x1800859fb  push    rsi
0x1800859fc  push    rdi
0x1800859fd  push    r14
0x1800859ff  lea     rbp, [rsp-290h]
0x180085a07  sub     rsp, 390h
0x180085a0e  mov     rax, cs:__security_cookie
0x180085a15  xor     rax, rsp
0x180085a18  mov     [rbp+2B0h+var_30], rax
0x180085a1f  xor     esi, esi
0x180085a21  lea     rcx, [rbp+2B0h+var_B0]; void *
0x180085a28  mov     r14d, 80h
0x180085a2e  mov     [rsp+3B0h+KeyHandle], rsi
0x180085a33  mov     r8d, r14d; Size
0x180085a36  mov     [rsp+3B0h+var_378], rsi
0x180085a3b  xor     edx, edx; Val
0x180085a3d  call    memset
0x180085a42  mov     r8d, r14d; Size
0x180085a45  lea     rcx, [rbp+2B0h+pszAlgId]; void *
0x180085a4c  xor     edx, edx; Val
0x180085a4e  call    memset
0x180085a53  mov     dword ptr [rsp+3B0h+pbOutput], esi
0x180085a57  mov     [rsp+3B0h+phAlgorithm], rsi
0x180085a5c  mov     [rsp+3B0h+pcbResult], esi
0x180085a60  mov     [rsp+3B0h+var_37C], esi
0x180085a64  call    FreeExternalHashAlgorithms
0x180085a69  cmp     cs:g_dwHashInfoTotalCount, 10h
0x180085a70  jnb     loc_180085C93
0x180085a76  lea     r8, [rsp+3B0h+KeyHandle]; KeyHandle
0x180085a7b  xor     edx, edx; PCWSTR
0x180085a7d  lea     rcx, aRegistryMachin_4; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180085a84  call    TlsOpenRegKey
0x180085a89  test    eax, eax
0x180085a8b  js      loc_180085C93
0x180085a91  mov     edi, esi
0x180085a93  jmp     loc_180085C7C
0x180085a98  xor     edx, edx; Val
0x180085a9a  mov     [rsp+3B0h+KeyInformation], esi
0x180085a9e  mov     r8d, 214h; Size
0x180085aa4  lea     rcx, [rsp+3B0h+var_34C]; void *
0x180085aa9  call    memset
0x180085aae  mov     rcx, [rsp+3B0h+KeyHandle]; KeyHandle
0x180085ab3  lea     rax, [rsp+3B0h+var_368]
0x180085ab8  mov     [rsp+3B0h+ResultLength], rax; ResultLength
0x180085abd  lea     r9, [rsp+3B0h+KeyInformation]; KeyInformation
0x180085ac2  xor     r8d, r8d; KeyInformationClass
0x180085ac5  mov     [rsp+3B0h+Length], 218h; Length
0x180085acd  mov     edx, edi; Index
0x180085acf  mov     [rsp+3B0h+var_368], esi
0x180085ad3  call    cs:__imp_ZwEnumerateKey
0x180085ada  nop     dword ptr [rax+rax+00h]
0x180085adf  test    eax, eax
0x180085ae1  js      loc_180085C89
0x180085ae7  lea     rax, [rsp+3B0h+var_340]
0x180085aec  or      r9, 0FFFFFFFFFFFFFFFFh
0x180085af0  inc     r9; unsigned __int64
0x180085af3  cmp     [rax+r9*2], si
0x180085af8  jnz     short loc_180085AF0
0x180085afa  lea     r8, [rsp+3B0h+var_340]; unsigned __int16 *
0x180085aff  lea     rcx, [rbp+2B0h+var_B0]; unsigned __int16 *
0x180085b06  call    ?RtlStringCchCopyNW@@YAJPEAG_KPEBG1@Z; RtlStringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180085b0b  test    eax, eax
0x180085b0d  js      loc_180085C7A
0x180085b13  lea     r8, [rsp+3B0h+var_378]; KeyHandle
0x180085b18  lea     rdx, [rbp+2B0h+var_B0]; PCWSTR
0x180085b1f  lea     rcx, aRegistryMachin_4; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180085b26  call    TlsOpenRegKey
0x180085b2b  test    eax, eax
0x180085b2d  js      loc_180085C7A
0x180085b33  mov     rcx, [rsp+3B0h+var_378]; KeyHandle
0x180085b38  lea     r8, [rbp+2B0h+pszAlgId]; unsigned __int16 *
0x180085b3f  lea     rdx, aCngalgorithm; "CngAlgorithm"
0x180085b46  call    GetSslStringFromRegistry
0x180085b4b  test    eax, eax
0x180085b4d  js      loc_180085C70
0x180085b53  mov     rcx, [rsp+3B0h+var_378]; KeyHandle
0x180085b58  lea     r8, [rsp+3B0h+var_37C]
0x180085b5d  lea     rdx, aTlscodepoint; "TlsCodePoint"
0x180085b64  call    GetSslDWordFromRegistry
0x180085b69  test    eax, eax
0x180085b6b  js      loc_180085C70
0x180085b71  lea     rcx, [rsp+3B0h+var_378]
0x180085b76  call    TlsCloseRegKey
0x180085b7b  xor     r9d, r9d; dwFlags
0x180085b7e  lea     rdx, [rbp+2B0h+pszAlgId]; pszAlgId
0x180085b85  xor     r8d, r8d; pszImplementation
0x180085b88  lea     rcx, [rsp+3B0h+phAlgorithm]; phAlgorithm
0x180085b8d  call    BCryptOpenAlgorithmProvider
0x180085b92  test    eax, eax
0x180085b94  js      loc_180085C7A
0x180085b9a  mov     rcx, [rsp+3B0h+phAlgorithm]; hObject
0x180085b9f  lea     rax, [rsp+3B0h+pcbResult]
0x180085ba4  mov     dword ptr [rsp+3B0h+ResultLength], esi; dwFlags
0x180085ba8  lea     r8, [rsp+3B0h+pbOutput]; pbOutput
0x180085bad  mov     r9d, 4; cbOutput
0x180085bb3  mov     qword ptr [rsp+3B0h+Length], rax; pcbResult
0x180085bb8  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180085bbf  call    BCryptGetProperty
0x180085bc4  mov     rcx, [rsp+3B0h+phAlgorithm]; hAlgorithm
0x180085bc9  xor     edx, edx; dwFlags
0x180085bcb  test    eax, eax
0x180085bcd  jns     short loc_180085BD9
0x180085bcf  call    BCryptCloseAlgorithmProvider
0x180085bd4  jmp     loc_180085C7A
0x180085bd9  call    BCryptCloseAlgorithmProvider
0x180085bde  mov     ecx, 18h
0x180085be3  call    MSCryptAlloc
0x180085be8  mov     rbx, rax
0x180085beb  test    rax, rax
0x180085bee  jz      loc_180085C7A
0x180085bf4  xorps   xmm0, xmm0
0x180085bf7  xor     eax, eax
0x180085bf9  movups  xmmword ptr [rbx], xmm0
0x180085bfc  mov     rcx, r14
0x180085bff  mov     [rbx+10h], rax
0x180085c03  call    MSCryptAlloc
0x180085c08  mov     [rbx], rax
0x180085c0b  test    rax, rax
0x180085c0e  jnz     short loc_180085C1A
0x180085c10  mov     rcx, rbx; P
0x180085c13  call    MSCryptFree
0x180085c18  jmp     short loc_180085C7A
0x180085c1a  lea     r8, [rbp+2B0h+pszAlgId]; Src
0x180085c21  mov     edx, 40h ; '@'; SizeInWords
0x180085c26  mov     rcx, rax; Dst
0x180085c29  call    cs:__imp_wcscpy_s
0x180085c30  nop     dword ptr [rax+rax+00h]
0x180085c35  mov     ecx, cs:g_dwHashInfoTotalCount
0x180085c3b  lea     rdx, g_pHashInfo
0x180085c42  mov     eax, dword ptr [rsp+3B0h+pbOutput]
0x180085c46  mov     [rbx+8], eax
0x180085c49  lea     eax, [rcx+8FF9h]
0x180085c4f  mov     [rdx+rcx*8], rbx
0x180085c53  mov     [rbx+10h], eax
0x180085c56  lea     eax, [rcx-10000006h]
0x180085c5c  mov     [rbx+0Ch], eax
0x180085c5f  inc     ecx
0x180085c61  mov     eax, [rsp+3B0h+var_37C]
0x180085c65  mov     [rbx+14h], eax
0x180085c68  mov     cs:g_dwHashInfoTotalCount, ecx
0x180085c6e  jmp     short loc_180085C7A
0x180085c70  lea     rcx, [rsp+3B0h+var_378]
0x180085c75  call    TlsCloseRegKey
0x180085c7a  inc     edi
0x180085c7c  cmp     cs:g_dwHashInfoTotalCount, 10h
0x180085c83  jb      loc_180085A98
0x180085c89  lea     rcx, [rsp+3B0h+KeyHandle]
0x180085c8e  call    TlsCloseRegKey
0x180085c93  mov     rcx, [rbp+2B0h+var_30]
0x180085c9a  xor     rcx, rsp; StackCookie
0x180085c9d  call    __security_check_cookie
0x180085ca2  add     rsp, 390h
0x180085ca9  pop     r14
0x180085cab  pop     rdi
0x180085cac  pop     rsi
0x180085cad  pop     rbx
0x180085cae  pop     rbp
0x180085caf  retn
```
