# GetExternalHashAlgorithms

- ea: `0x1800849e0`
- end: `0x180084c99`
- name: `GetExternalHashAlgorithms`
- size: `697`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180045c90`
- `0x180081428`

## callees

- `0x1800023e0`
- `0x180003c70`
- `0x180003f70`
- `0x180006470`
- `0x1800449b0`
- `0x180083d48`
- `0x180083dac`
- `0x180083e6c`
- `0x180083f60`
- `0x180083f94`
- `0x180084964`
- `0x1800849e0`
- `0x18009d820`
- `0x18009dd40`

## import_xrefs

- `ntoskrnl!ZwEnumerateKey` at `0x180084abb`
- `ntoskrnl!ZwEnumerateKey` at `0x180084abb`
- `ntoskrnl!wcscpy_s` at `0x180084c11`
- `ntoskrnl!wcscpy_s` at `0x180084c11`

## string_xrefs

- `0x180084a65`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Hash`
- `0x180084b07`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Hash`

## pseudocode

```c
__int64 GetExternalHashAlgorithms()
{
  __int64 result; // rax
  ULONG i; // edi
  unsigned __int64 v2; // rdx
  unsigned __int64 v3; // r9
  __int64 v4; // rdx
  __int64 v5; // rdx
  wchar_t **v6; // rbx
  wchar_t *v7; // rax
  __int64 v8; // rcx
  UCHAR pbOutput[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v10; // [rsp+34h] [rbp-CCh]
  HANDLE v11; // [rsp+38h] [rbp-C8h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp-C0h] BYREF
  ULONG ResultLength; // [rsp+48h] [rbp-B8h] BYREF
  ULONG pcbResult; // [rsp+4Ch] [rbp-B4h] BYREF
  HANDLE KeyHandle[2]; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD KeyInformation[136]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszAlgId[64]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR v18[64]; // [rsp+300h] [rbp+200h] BYREF

  KeyHandle[0] = 0;
  v11 = 0;
  memset(v18, 0, sizeof(v18));
  memset(pszAlgId, 0, sizeof(pszAlgId));
  *(_DWORD *)pbOutput = 0;
  phAlgorithm = 0;
  pcbResult = 0;
  v10 = 0;
  result = FreeExternalHashAlgorithms();
  if ( (unsigned int)g_dwHashInfoTotalCount < 0x10 )
  {
    result = TlsOpenRegKey(
               L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Protocol Provider\\Hash",
               0,
               KeyHandle);
    if ( (int)result >= 0 )
    {
      for ( i = 0; (unsigned int)g_dwHashInfoTotalCount < 0x10; ++i )
      {
        memset(KeyInformation, 0, 536);
        ResultLength = 0;
        if ( ZwEnumerateKey(KeyHandle[0], i, KeyBasicInformation, KeyInformation, 0x218u, &ResultLength) < 0 )
          break;
        v3 = -1;
        do
          ++v3;
        while ( *((_WORD *)&KeyInformation[4] + v3) );
        if ( (int)RtlStringCchCopyNW(v18, v2, (const unsigned __int16 *)&KeyInformation[4], v3) >= 0
          && (int)TlsOpenRegKey(
                    L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Prot"
                     "ocol Provider\\Hash",
                    v18,
                    &v11) >= 0 )
        {
          if ( (int)GetSslStringFromRegistry(v11, L"CngAlgorithm", pszAlgId) < 0
            || (int)GetSslDWordFromRegistry(v11) < 0 )
          {
            TlsCloseRegKey(&v11);
          }
          else
          {
            TlsCloseRegKey(&v11);
            if ( BCryptOpenAlgorithmProvider(&phAlgorithm, pszAlgId, 0, 0) >= 0 )
            {
              if ( BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0) >= 0 )
              {
                BCryptCloseAlgorithmProvider(phAlgorithm, 0);
                v6 = (wchar_t **)MSCryptAlloc(24, v4);
                if ( v6 )
                {
                  *(_OWORD *)v6 = 0;
                  v6[2] = 0;
                  v7 = (wchar_t *)MSCryptAlloc(128, v5);
                  *v6 = v7;
                  if ( v7 )
                  {
                    wcscpy_s(v7, 0x40u, pszAlgId);
                    v8 = (unsigned int)g_dwHashInfoTotalCount;
                    *((_DWORD *)v6 + 2) = *(_DWORD *)pbOutput;
                    g_pHashInfo[v8] = (__int64)v6;
                    *((_DWORD *)v6 + 4) = v8 + 36857;
                    *((_DWORD *)v6 + 3) = v8 - 268435462;
                    *((_DWORD *)v6 + 5) = v10;
                    g_dwHashInfoTotalCount = v8 + 1;
                  }
                  else
                  {
                    MSCryptFree(v6);
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
0x1800849e0  push    rbp
0x1800849e2  push    rbx
0x1800849e3  push    rsi
0x1800849e4  push    rdi
0x1800849e5  push    r14
0x1800849e7  lea     rbp, [rsp-290h]
0x1800849ef  sub     rsp, 390h
0x1800849f6  mov     rax, cs:__security_cookie
0x1800849fd  xor     rax, rsp
0x180084a00  mov     [rbp+2B0h+var_30], rax
0x180084a07  xor     esi, esi
0x180084a09  lea     rcx, [rbp+2B0h+var_B0]; void *
0x180084a10  mov     r14d, 80h
0x180084a16  mov     [rsp+3B0h+KeyHandle], rsi
0x180084a1b  mov     r8d, r14d; Size
0x180084a1e  mov     [rsp+3B0h+var_378], rsi
0x180084a23  xor     edx, edx; Val
0x180084a25  call    memset
0x180084a2a  mov     r8d, r14d; Size
0x180084a2d  lea     rcx, [rbp+2B0h+pszAlgId]; void *
0x180084a34  xor     edx, edx; Val
0x180084a36  call    memset
0x180084a3b  mov     dword ptr [rsp+3B0h+pbOutput], esi
0x180084a3f  mov     [rsp+3B0h+phAlgorithm], rsi
0x180084a44  mov     [rsp+3B0h+pcbResult], esi
0x180084a48  mov     [rsp+3B0h+var_37C], esi
0x180084a4c  call    FreeExternalHashAlgorithms
0x180084a51  cmp     cs:g_dwHashInfoTotalCount, 10h
0x180084a58  jnb     loc_180084C7B
0x180084a5e  lea     r8, [rsp+3B0h+KeyHandle]; KeyHandle
0x180084a63  xor     edx, edx; PCWSTR
0x180084a65  lea     rcx, aRegistryMachin_4; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180084a6c  call    TlsOpenRegKey
0x180084a71  test    eax, eax
0x180084a73  js      loc_180084C7B
0x180084a79  mov     edi, esi
0x180084a7b  jmp     loc_180084C64
0x180084a80  xor     edx, edx; Val
0x180084a82  mov     [rsp+3B0h+KeyInformation], esi
0x180084a86  mov     r8d, 214h; Size
0x180084a8c  lea     rcx, [rsp+3B0h+var_34C]; void *
0x180084a91  call    memset
0x180084a96  mov     rcx, [rsp+3B0h+KeyHandle]; KeyHandle
0x180084a9b  lea     rax, [rsp+3B0h+var_368]
0x180084aa0  mov     [rsp+3B0h+ResultLength], rax; ResultLength
0x180084aa5  lea     r9, [rsp+3B0h+KeyInformation]; KeyInformation
0x180084aaa  xor     r8d, r8d; KeyInformationClass
0x180084aad  mov     [rsp+3B0h+Length], 218h; Length
0x180084ab5  mov     edx, edi; Index
0x180084ab7  mov     [rsp+3B0h+var_368], esi
0x180084abb  call    cs:__imp_ZwEnumerateKey
0x180084ac2  nop     dword ptr [rax+rax+00h]
0x180084ac7  test    eax, eax
0x180084ac9  js      loc_180084C71
0x180084acf  lea     rax, [rsp+3B0h+var_340]
0x180084ad4  or      r9, 0FFFFFFFFFFFFFFFFh
0x180084ad8  inc     r9; unsigned __int64
0x180084adb  cmp     [rax+r9*2], si
0x180084ae0  jnz     short loc_180084AD8
0x180084ae2  lea     r8, [rsp+3B0h+var_340]; unsigned __int16 *
0x180084ae7  lea     rcx, [rbp+2B0h+var_B0]; unsigned __int16 *
0x180084aee  call    ?RtlStringCchCopyNW@@YAJPEAG_KPEBG1@Z; RtlStringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180084af3  test    eax, eax
0x180084af5  js      loc_180084C62
0x180084afb  lea     r8, [rsp+3B0h+var_378]; KeyHandle
0x180084b00  lea     rdx, [rbp+2B0h+var_B0]; PCWSTR
0x180084b07  lea     rcx, aRegistryMachin_4; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180084b0e  call    TlsOpenRegKey
0x180084b13  test    eax, eax
0x180084b15  js      loc_180084C62
0x180084b1b  mov     rcx, [rsp+3B0h+var_378]; KeyHandle
0x180084b20  lea     r8, [rbp+2B0h+pszAlgId]; unsigned __int16 *
0x180084b27  lea     rdx, aCngalgorithm; "CngAlgorithm"
0x180084b2e  call    GetSslStringFromRegistry
0x180084b33  test    eax, eax
0x180084b35  js      loc_180084C58
0x180084b3b  mov     rcx, [rsp+3B0h+var_378]; KeyHandle
0x180084b40  lea     r8, [rsp+3B0h+var_37C]
0x180084b45  lea     rdx, aTlscodepoint; "TlsCodePoint"
0x180084b4c  call    GetSslDWordFromRegistry
0x180084b51  test    eax, eax
0x180084b53  js      loc_180084C58
0x180084b59  lea     rcx, [rsp+3B0h+var_378]
0x180084b5e  call    TlsCloseRegKey
0x180084b63  xor     r9d, r9d; dwFlags
0x180084b66  lea     rdx, [rbp+2B0h+pszAlgId]; pszAlgId
0x180084b6d  xor     r8d, r8d; pszImplementation
0x180084b70  lea     rcx, [rsp+3B0h+phAlgorithm]; phAlgorithm
0x180084b75  call    BCryptOpenAlgorithmProvider
0x180084b7a  test    eax, eax
0x180084b7c  js      loc_180084C62
0x180084b82  mov     rcx, [rsp+3B0h+phAlgorithm]; hObject
0x180084b87  lea     rax, [rsp+3B0h+pcbResult]
0x180084b8c  mov     dword ptr [rsp+3B0h+ResultLength], esi; dwFlags
0x180084b90  lea     r8, [rsp+3B0h+pbOutput]; pbOutput
0x180084b95  mov     r9d, 4; cbOutput
0x180084b9b  mov     qword ptr [rsp+3B0h+Length], rax; pcbResult
0x180084ba0  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180084ba7  call    BCryptGetProperty
0x180084bac  mov     rcx, [rsp+3B0h+phAlgorithm]; hAlgorithm
0x180084bb1  xor     edx, edx; dwFlags
0x180084bb3  test    eax, eax
0x180084bb5  jns     short loc_180084BC1
0x180084bb7  call    BCryptCloseAlgorithmProvider
0x180084bbc  jmp     loc_180084C62
0x180084bc1  call    BCryptCloseAlgorithmProvider
0x180084bc6  mov     ecx, 18h
0x180084bcb  call    MSCryptAlloc
0x180084bd0  mov     rbx, rax
0x180084bd3  test    rax, rax
0x180084bd6  jz      loc_180084C62
0x180084bdc  xorps   xmm0, xmm0
0x180084bdf  xor     eax, eax
0x180084be1  movups  xmmword ptr [rbx], xmm0
0x180084be4  mov     rcx, r14
0x180084be7  mov     [rbx+10h], rax
0x180084beb  call    MSCryptAlloc
0x180084bf0  mov     [rbx], rax
0x180084bf3  test    rax, rax
0x180084bf6  jnz     short loc_180084C02
0x180084bf8  mov     rcx, rbx; P
0x180084bfb  call    MSCryptFree
0x180084c00  jmp     short loc_180084C62
0x180084c02  lea     r8, [rbp+2B0h+pszAlgId]; Src
0x180084c09  mov     edx, 40h ; '@'; SizeInWords
0x180084c0e  mov     rcx, rax; Dst
0x180084c11  call    cs:__imp_wcscpy_s
0x180084c18  nop     dword ptr [rax+rax+00h]
0x180084c1d  mov     ecx, cs:g_dwHashInfoTotalCount
0x180084c23  lea     rdx, g_pHashInfo
0x180084c2a  mov     eax, dword ptr [rsp+3B0h+pbOutput]
0x180084c2e  mov     [rbx+8], eax
0x180084c31  lea     eax, [rcx+8FF9h]
0x180084c37  mov     [rdx+rcx*8], rbx
0x180084c3b  mov     [rbx+10h], eax
0x180084c3e  lea     eax, [rcx-10000006h]
0x180084c44  mov     [rbx+0Ch], eax
0x180084c47  inc     ecx
0x180084c49  mov     eax, [rsp+3B0h+var_37C]
0x180084c4d  mov     [rbx+14h], eax
0x180084c50  mov     cs:g_dwHashInfoTotalCount, ecx
0x180084c56  jmp     short loc_180084C62
0x180084c58  lea     rcx, [rsp+3B0h+var_378]
0x180084c5d  call    TlsCloseRegKey
0x180084c62  inc     edi
0x180084c64  cmp     cs:g_dwHashInfoTotalCount, 10h
0x180084c6b  jb      loc_180084A80
0x180084c71  lea     rcx, [rsp+3B0h+KeyHandle]
0x180084c76  call    TlsCloseRegKey
0x180084c7b  mov     rcx, [rbp+2B0h+var_30]
0x180084c82  xor     rcx, rsp; StackCookie
0x180084c85  call    __security_check_cookie
0x180084c8a  add     rsp, 390h
0x180084c91  pop     r14
0x180084c93  pop     rdi
0x180084c94  pop     rsi
0x180084c95  pop     rbx
0x180084c96  pop     rbp
0x180084c97  retn
```
