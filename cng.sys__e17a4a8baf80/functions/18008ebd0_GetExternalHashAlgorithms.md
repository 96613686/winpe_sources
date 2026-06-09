# GetExternalHashAlgorithms

- ea: `0x18008ebd0`
- end: `0x18008ee89`
- name: `GetExternalHashAlgorithms`
- size: `697`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004fd80`
- `0x18008b618`

## callees

- `0x18000c500`
- `0x18000dd90`
- `0x18000e090`
- `0x180010590`
- `0x18004eaa0`
- `0x18008df38`
- `0x18008df9c`
- `0x18008e05c`
- `0x18008e150`
- `0x18008e184`
- `0x18008eb54`
- `0x18008ebd0`
- `0x1800a4260`
- `0x1800a4380`

## import_xrefs

- `ntoskrnl!ZwEnumerateKey` at `0x18008ecab`
- `ntoskrnl!ZwEnumerateKey` at `0x18008ecab`
- `ntoskrnl!wcscpy_s` at `0x18008ee01`
- `ntoskrnl!wcscpy_s` at `0x18008ee01`

## string_xrefs

- `0x18008ec55`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Hash`
- `0x18008ecf7`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Hash`

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
0x18008ebd0  push    rbp
0x18008ebd2  push    rbx
0x18008ebd3  push    rsi
0x18008ebd4  push    rdi
0x18008ebd5  push    r14
0x18008ebd7  lea     rbp, [rsp-290h]
0x18008ebdf  sub     rsp, 390h
0x18008ebe6  mov     rax, cs:__security_cookie
0x18008ebed  xor     rax, rsp
0x18008ebf0  mov     [rbp+2B0h+var_30], rax
0x18008ebf7  xor     esi, esi
0x18008ebf9  lea     rcx, [rbp+2B0h+var_B0]; void *
0x18008ec00  mov     r14d, 80h
0x18008ec06  mov     [rsp+3B0h+KeyHandle], rsi
0x18008ec0b  mov     r8d, r14d; Size
0x18008ec0e  mov     [rsp+3B0h+var_378], rsi
0x18008ec13  xor     edx, edx; Val
0x18008ec15  call    memset
0x18008ec1a  mov     r8d, r14d; Size
0x18008ec1d  lea     rcx, [rbp+2B0h+pszAlgId]; void *
0x18008ec24  xor     edx, edx; Val
0x18008ec26  call    memset
0x18008ec2b  mov     dword ptr [rsp+3B0h+pbOutput], esi
0x18008ec2f  mov     [rsp+3B0h+phAlgorithm], rsi
0x18008ec34  mov     [rsp+3B0h+pcbResult], esi
0x18008ec38  mov     [rsp+3B0h+var_37C], esi
0x18008ec3c  call    FreeExternalHashAlgorithms
0x18008ec41  cmp     cs:g_dwHashInfoTotalCount, 10h
0x18008ec48  jnb     loc_18008EE6B
0x18008ec4e  lea     r8, [rsp+3B0h+KeyHandle]; KeyHandle
0x18008ec53  xor     edx, edx; PCWSTR
0x18008ec55  lea     rcx, aRegistryMachin_4; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18008ec5c  call    TlsOpenRegKey
0x18008ec61  test    eax, eax
0x18008ec63  js      loc_18008EE6B
0x18008ec69  mov     edi, esi
0x18008ec6b  jmp     loc_18008EE54
0x18008ec70  xor     edx, edx; Val
0x18008ec72  mov     [rsp+3B0h+KeyInformation], esi
0x18008ec76  mov     r8d, 214h; Size
0x18008ec7c  lea     rcx, [rsp+3B0h+var_34C]; void *
0x18008ec81  call    memset
0x18008ec86  mov     rcx, [rsp+3B0h+KeyHandle]; KeyHandle
0x18008ec8b  lea     rax, [rsp+3B0h+var_368]
0x18008ec90  mov     [rsp+3B0h+ResultLength], rax; ResultLength
0x18008ec95  lea     r9, [rsp+3B0h+KeyInformation]; KeyInformation
0x18008ec9a  xor     r8d, r8d; KeyInformationClass
0x18008ec9d  mov     [rsp+3B0h+Length], 218h; Length
0x18008eca5  mov     edx, edi; Index
0x18008eca7  mov     [rsp+3B0h+var_368], esi
0x18008ecab  call    cs:__imp_ZwEnumerateKey
0x18008ecb2  nop     dword ptr [rax+rax+00h]
0x18008ecb7  test    eax, eax
0x18008ecb9  js      loc_18008EE61
0x18008ecbf  lea     rax, [rsp+3B0h+var_340]
0x18008ecc4  or      r9, 0FFFFFFFFFFFFFFFFh
0x18008ecc8  inc     r9; unsigned __int64
0x18008eccb  cmp     [rax+r9*2], si
0x18008ecd0  jnz     short loc_18008ECC8
0x18008ecd2  lea     r8, [rsp+3B0h+var_340]; unsigned __int16 *
0x18008ecd7  lea     rcx, [rbp+2B0h+var_B0]; unsigned __int16 *
0x18008ecde  call    ?RtlStringCchCopyNW@@YAJPEAG_KPEBG1@Z; RtlStringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18008ece3  test    eax, eax
0x18008ece5  js      loc_18008EE52
0x18008eceb  lea     r8, [rsp+3B0h+var_378]; KeyHandle
0x18008ecf0  lea     rdx, [rbp+2B0h+var_B0]; PCWSTR
0x18008ecf7  lea     rcx, aRegistryMachin_4; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18008ecfe  call    TlsOpenRegKey
0x18008ed03  test    eax, eax
0x18008ed05  js      loc_18008EE52
0x18008ed0b  mov     rcx, [rsp+3B0h+var_378]; KeyHandle
0x18008ed10  lea     r8, [rbp+2B0h+pszAlgId]; unsigned __int16 *
0x18008ed17  lea     rdx, aCngalgorithm; "CngAlgorithm"
0x18008ed1e  call    GetSslStringFromRegistry
0x18008ed23  test    eax, eax
0x18008ed25  js      loc_18008EE48
0x18008ed2b  mov     rcx, [rsp+3B0h+var_378]; KeyHandle
0x18008ed30  lea     r8, [rsp+3B0h+var_37C]
0x18008ed35  lea     rdx, aTlscodepoint; "TlsCodePoint"
0x18008ed3c  call    GetSslDWordFromRegistry
0x18008ed41  test    eax, eax
0x18008ed43  js      loc_18008EE48
0x18008ed49  lea     rcx, [rsp+3B0h+var_378]
0x18008ed4e  call    TlsCloseRegKey
0x18008ed53  xor     r9d, r9d; dwFlags
0x18008ed56  lea     rdx, [rbp+2B0h+pszAlgId]; pszAlgId
0x18008ed5d  xor     r8d, r8d; pszImplementation
0x18008ed60  lea     rcx, [rsp+3B0h+phAlgorithm]; phAlgorithm
0x18008ed65  call    BCryptOpenAlgorithmProvider
0x18008ed6a  test    eax, eax
0x18008ed6c  js      loc_18008EE52
0x18008ed72  mov     rcx, [rsp+3B0h+phAlgorithm]; hObject
0x18008ed77  lea     rax, [rsp+3B0h+pcbResult]
0x18008ed7c  mov     dword ptr [rsp+3B0h+ResultLength], esi; dwFlags
0x18008ed80  lea     r8, [rsp+3B0h+pbOutput]; pbOutput
0x18008ed85  mov     r9d, 4; cbOutput
0x18008ed8b  mov     qword ptr [rsp+3B0h+Length], rax; pcbResult
0x18008ed90  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18008ed97  call    BCryptGetProperty
0x18008ed9c  mov     rcx, [rsp+3B0h+phAlgorithm]; hAlgorithm
0x18008eda1  xor     edx, edx; dwFlags
0x18008eda3  test    eax, eax
0x18008eda5  jns     short loc_18008EDB1
0x18008eda7  call    BCryptCloseAlgorithmProvider
0x18008edac  jmp     loc_18008EE52
0x18008edb1  call    BCryptCloseAlgorithmProvider
0x18008edb6  mov     ecx, 18h
0x18008edbb  call    MSCryptAlloc
0x18008edc0  mov     rbx, rax
0x18008edc3  test    rax, rax
0x18008edc6  jz      loc_18008EE52
0x18008edcc  xorps   xmm0, xmm0
0x18008edcf  xor     eax, eax
0x18008edd1  movups  xmmword ptr [rbx], xmm0
0x18008edd4  mov     rcx, r14
0x18008edd7  mov     [rbx+10h], rax
0x18008eddb  call    MSCryptAlloc
0x18008ede0  mov     [rbx], rax
0x18008ede3  test    rax, rax
0x18008ede6  jnz     short loc_18008EDF2
0x18008ede8  mov     rcx, rbx; P
0x18008edeb  call    MSCryptFree
0x18008edf0  jmp     short loc_18008EE52
0x18008edf2  lea     r8, [rbp+2B0h+pszAlgId]; Src
0x18008edf9  mov     edx, 40h ; '@'; SizeInWords
0x18008edfe  mov     rcx, rax; Dst
0x18008ee01  call    cs:__imp_wcscpy_s
0x18008ee08  nop     dword ptr [rax+rax+00h]
0x18008ee0d  mov     ecx, cs:g_dwHashInfoTotalCount
0x18008ee13  lea     rdx, g_pHashInfo
0x18008ee1a  mov     eax, dword ptr [rsp+3B0h+pbOutput]
0x18008ee1e  mov     [rbx+8], eax
0x18008ee21  lea     eax, [rcx+8FF9h]
0x18008ee27  mov     [rdx+rcx*8], rbx
0x18008ee2b  mov     [rbx+10h], eax
0x18008ee2e  lea     eax, [rcx-10000006h]
0x18008ee34  mov     [rbx+0Ch], eax
0x18008ee37  inc     ecx
0x18008ee39  mov     eax, [rsp+3B0h+var_37C]
0x18008ee3d  mov     [rbx+14h], eax
0x18008ee40  mov     cs:g_dwHashInfoTotalCount, ecx
0x18008ee46  jmp     short loc_18008EE52
0x18008ee48  lea     rcx, [rsp+3B0h+var_378]
0x18008ee4d  call    TlsCloseRegKey
0x18008ee52  inc     edi
0x18008ee54  cmp     cs:g_dwHashInfoTotalCount, 10h
0x18008ee5b  jb      loc_18008EC70
0x18008ee61  lea     rcx, [rsp+3B0h+KeyHandle]
0x18008ee66  call    TlsCloseRegKey
0x18008ee6b  mov     rcx, [rbp+2B0h+var_30]
0x18008ee72  xor     rcx, rsp; StackCookie
0x18008ee75  call    __security_check_cookie
0x18008ee7a  add     rsp, 390h
0x18008ee81  pop     r14
0x18008ee83  pop     rdi
0x18008ee84  pop     rsi
0x18008ee85  pop     rbx
0x18008ee86  pop     rbp
0x18008ee87  retn
```
