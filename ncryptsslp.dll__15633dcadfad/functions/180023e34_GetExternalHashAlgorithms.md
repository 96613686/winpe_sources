# GetExternalHashAlgorithms

- ea: `0x180023e34`
- end: `0x1800240e9`
- name: `GetExternalHashAlgorithms`
- size: `693`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012578`

## callees

- `0x180003ef0`
- `0x180007940`
- `0x1800126f0`
- `0x180012a7c`
- `0x180012d6c`
- `0x180014660`
- `0x180023d58`
- `0x180023dbc`
- `0x180023e34`
- `0x1800244f0`
- `0x180024ef0`
- `0x180025660`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180023fcb`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180023fcb`
- `bcrypt!BCryptGetProperty` at `0x180023ffe`
- `bcrypt!BCryptGetProperty` at `0x180023ffe`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002400f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002401a`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002400f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002401a`
- `ntdll!NtEnumerateKey` at `0x180023f17`
- `ntdll!NtEnumerateKey` at `0x180023f17`

## string_xrefs

- `0x180023eb9`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Hash`
- `0x180023f5d`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Hash`

## pseudocode

```c
__int64 GetExternalHashAlgorithms()
{
  __int64 result; // rax
  ULONG v1; // edi
  unsigned __int64 v2; // rdx
  unsigned __int64 v3; // r9
  __int64 v4; // rbx
  wchar_t *v5; // rax
  __int64 v6; // rcx
  unsigned int v7; // ecx
  UCHAR pbOutput[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v9; // [rsp+34h] [rbp-CCh]
  HANDLE v10; // [rsp+38h] [rbp-C8h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp-C0h] BYREF
  ULONG ResultLength; // [rsp+48h] [rbp-B8h] BYREF
  ULONG pcbResult; // [rsp+4Ch] [rbp-B4h] BYREF
  HANDLE KeyHandle[2]; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD KeyInformation[136]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszAlgId[64]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR v17[64]; // [rsp+300h] [rbp+200h] BYREF

  KeyHandle[0] = 0;
  v10 = 0;
  memset(v17, 0, sizeof(v17));
  memset(pszAlgId, 0, sizeof(pszAlgId));
  *(_DWORD *)pbOutput = 0;
  phAlgorithm = 0;
  pcbResult = 0;
  v9 = 0;
  result = FreeExternalHashAlgorithms();
  if ( (unsigned int)g_dwHashInfoTotalCount < 0x10 )
  {
    result = TlsOpenRegKey(
               L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Protocol Provider\\Hash",
               0,
               KeyHandle);
    if ( (int)result >= 0 )
    {
      v1 = 0;
      if ( (unsigned int)g_dwHashInfoTotalCount < 0x10 )
      {
        while ( 1 )
        {
          memset(KeyInformation, 0, 536);
          ResultLength = 0;
          if ( NtEnumerateKey(KeyHandle[0], v1, KeyBasicInformation, KeyInformation, 0x218u, &ResultLength) < 0 )
            return TlsCloseRegKey(KeyHandle);
          v3 = -1;
          do
            ++v3;
          while ( *((_WORD *)&KeyInformation[4] + v3) );
          if ( (int)RtlStringCchCopyNW(v17, v2, (const unsigned __int16 *)&KeyInformation[4], v3) < 0
            || (int)TlsOpenRegKey(
                      L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Pr"
                       "otocol Provider\\Hash",
                      v17,
                      &v10) < 0 )
          {
            goto LABEL_19;
          }
          if ( (int)GetSslStringFromRegistry(v10, L"CngAlgorithm", pszAlgId) < 0
            || (int)GetSslDWordFromRegistry(v10) < 0 )
          {
            TlsCloseRegKey(&v10);
            goto LABEL_19;
          }
          TlsCloseRegKey(&v10);
          if ( BCryptOpenAlgorithmProvider(&phAlgorithm, pszAlgId, 0, 0) < 0 )
            goto LABEL_19;
          if ( BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0) < 0 )
            break;
          BCryptCloseAlgorithmProvider(phAlgorithm, 0);
          v4 = SafeAllocaAllocateFromHeap(24);
          if ( !v4 )
            goto LABEL_19;
          *(_OWORD *)v4 = 0;
          *(_QWORD *)(v4 + 16) = 0;
          v5 = (wchar_t *)SafeAllocaAllocateFromHeap(128);
          *(_QWORD *)v4 = v5;
          if ( !v5 )
          {
            MSCryptFree(v4);
            goto LABEL_19;
          }
          wcscpy_s(v5, 0x40u, pszAlgId);
          v6 = (unsigned int)g_dwHashInfoTotalCount;
          *(_DWORD *)(v4 + 8) = *(_DWORD *)pbOutput;
          g_pHashInfo[v6] = v4;
          *(_DWORD *)(v4 + 16) = v6 + 36857;
          *(_DWORD *)(v4 + 12) = v6 - 268435462;
          v7 = v6 + 1;
          *(_DWORD *)(v4 + 20) = v9;
          g_dwHashInfoTotalCount = v7;
LABEL_20:
          ++v1;
          if ( v7 >= 0x10 )
            return TlsCloseRegKey(KeyHandle);
        }
        BCryptCloseAlgorithmProvider(phAlgorithm, 0);
LABEL_19:
        v7 = g_dwHashInfoTotalCount;
        goto LABEL_20;
      }
      return TlsCloseRegKey(KeyHandle);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180023e34  push    rbp
0x180023e36  push    rbx
0x180023e37  push    rsi
0x180023e38  push    rdi
0x180023e39  push    r14
0x180023e3b  lea     rbp, [rsp-290h]
0x180023e43  sub     rsp, 390h
0x180023e4a  mov     rax, cs:__security_cookie
0x180023e51  xor     rax, rsp
0x180023e54  mov     [rbp+2B0h+var_30], rax
0x180023e5b  xor     esi, esi
0x180023e5d  lea     rcx, [rbp+2B0h+var_B0]; void *
0x180023e64  mov     r14d, 80h
0x180023e6a  mov     [rsp+3B0h+KeyHandle], rsi
0x180023e6f  mov     r8d, r14d; Size
0x180023e72  mov     [rsp+3B0h+var_378], rsi
0x180023e77  xor     edx, edx; Val
0x180023e79  call    memset
0x180023e7e  mov     r8d, r14d; Size
0x180023e81  lea     rcx, [rbp+2B0h+pszAlgId]; void *
0x180023e88  xor     edx, edx; Val
0x180023e8a  call    memset
0x180023e8f  mov     dword ptr [rsp+3B0h+pbOutput], esi
0x180023e93  mov     [rsp+3B0h+phAlgorithm], rsi
0x180023e98  mov     [rsp+3B0h+pcbResult], esi
0x180023e9c  mov     [rsp+3B0h+var_37C], esi
0x180023ea0  call    FreeExternalHashAlgorithms
0x180023ea5  cmp     cs:g_dwHashInfoTotalCount, 10h
0x180023eac  jnb     loc_1800240CC
0x180023eb2  lea     r8, [rsp+3B0h+KeyHandle]; KeyHandle
0x180023eb7  xor     edx, edx; PCWSTR
0x180023eb9  lea     rcx, aRegistryMachin; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180023ec0  call    TlsOpenRegKey
0x180023ec5  test    eax, eax
0x180023ec7  js      loc_1800240CC
0x180023ecd  cmp     cs:g_dwHashInfoTotalCount, 10h
0x180023ed4  mov     edi, esi
0x180023ed6  jnb     loc_1800240C2
0x180023edc  xor     edx, edx; Val
0x180023ede  mov     [rsp+3B0h+KeyInformation], esi
0x180023ee2  mov     r8d, 214h; Size
0x180023ee8  lea     rcx, [rsp+3B0h+var_34C]; void *
0x180023eed  call    memset
0x180023ef2  mov     rcx, [rsp+3B0h+KeyHandle]; KeyHandle
0x180023ef7  lea     rax, [rsp+3B0h+var_368]
0x180023efc  mov     [rsp+3B0h+ResultLength], rax; ResultLength
0x180023f01  lea     r9, [rsp+3B0h+KeyInformation]; KeyInformation
0x180023f06  xor     r8d, r8d; KeyInformationClass
0x180023f09  mov     [rsp+3B0h+Length], 218h; Length
0x180023f11  mov     edx, edi; Index
0x180023f13  mov     [rsp+3B0h+var_368], esi
0x180023f17  call    cs:__imp_NtEnumerateKey
0x180023f1d  test    eax, eax
0x180023f1f  js      loc_1800240C2
0x180023f25  lea     rax, [rsp+3B0h+var_340]
0x180023f2a  or      r9, 0FFFFFFFFFFFFFFFFh
0x180023f2e  inc     r9; unsigned __int64
0x180023f31  cmp     [rax+r9*2], si
0x180023f36  jnz     short loc_180023F2E
0x180023f38  lea     r8, [rsp+3B0h+var_340]; unsigned __int16 *
0x180023f3d  lea     rcx, [rbp+2B0h+var_B0]; unsigned __int16 *
0x180023f44  call    ?RtlStringCchCopyNW@@YAJPEAG_KPEBG1@Z; RtlStringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180023f49  test    eax, eax
0x180023f4b  js      loc_1800240B1
0x180023f51  lea     r8, [rsp+3B0h+var_378]; KeyHandle
0x180023f56  lea     rdx, [rbp+2B0h+var_B0]; PCWSTR
0x180023f5d  lea     rcx, aRegistryMachin; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180023f64  call    TlsOpenRegKey
0x180023f69  test    eax, eax
0x180023f6b  js      loc_1800240B1
0x180023f71  mov     rcx, [rsp+3B0h+var_378]; KeyHandle
0x180023f76  lea     r8, [rbp+2B0h+pszAlgId]; unsigned __int16 *
0x180023f7d  lea     rdx, aCngalgorithm; "CngAlgorithm"
0x180023f84  call    GetSslStringFromRegistry
0x180023f89  test    eax, eax
0x180023f8b  js      loc_1800240A7
0x180023f91  mov     rcx, [rsp+3B0h+var_378]; KeyHandle
0x180023f96  lea     r8, [rsp+3B0h+var_37C]
0x180023f9b  lea     rdx, aTlscodepoint; "TlsCodePoint"
0x180023fa2  call    GetSslDWordFromRegistry
0x180023fa7  test    eax, eax
0x180023fa9  js      loc_1800240A7
0x180023faf  lea     rcx, [rsp+3B0h+var_378]
0x180023fb4  call    TlsCloseRegKey
0x180023fb9  xor     r9d, r9d; dwFlags
0x180023fbc  lea     rdx, [rbp+2B0h+pszAlgId]; pszAlgId
0x180023fc3  xor     r8d, r8d; pszImplementation
0x180023fc6  lea     rcx, [rsp+3B0h+phAlgorithm]; phAlgorithm
0x180023fcb  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180023fd1  test    eax, eax
0x180023fd3  js      loc_1800240B1
0x180023fd9  mov     rcx, [rsp+3B0h+phAlgorithm]; hObject
0x180023fde  lea     rax, [rsp+3B0h+pcbResult]
0x180023fe3  mov     dword ptr [rsp+3B0h+ResultLength], esi; dwFlags
0x180023fe7  lea     r8, [rsp+3B0h+pbOutput]; pbOutput
0x180023fec  mov     r9d, 4; cbOutput
0x180023ff2  mov     qword ptr [rsp+3B0h+Length], rax; pcbResult
0x180023ff7  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180023ffe  call    cs:__imp_BCryptGetProperty
0x180024004  mov     rcx, [rsp+3B0h+phAlgorithm]; hAlgorithm
0x180024009  xor     edx, edx; dwFlags
0x18002400b  test    eax, eax
0x18002400d  jns     short loc_18002401A
0x18002400f  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180024015  jmp     loc_1800240B1
0x18002401a  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180024020  mov     ecx, 18h
0x180024025  call    SafeAllocaAllocateFromHeap
0x18002402a  mov     rbx, rax
0x18002402d  test    rax, rax
0x180024030  jz      short loc_1800240B1
0x180024032  xorps   xmm0, xmm0
0x180024035  xor     eax, eax
0x180024037  movups  xmmword ptr [rbx], xmm0
0x18002403a  mov     rcx, r14
0x18002403d  mov     [rbx+10h], rax
0x180024041  call    SafeAllocaAllocateFromHeap
0x180024046  mov     [rbx], rax
0x180024049  test    rax, rax
0x18002404c  jnz     short loc_180024058
0x18002404e  mov     rcx, rbx
0x180024051  call    MSCryptFree
0x180024056  jmp     short loc_1800240B1
0x180024058  lea     r8, [rbp+2B0h+pszAlgId]; Source
0x18002405f  mov     edx, 40h ; '@'; SizeInWords
0x180024064  mov     rcx, rax; Destination
0x180024067  call    wcscpy_s
0x18002406c  mov     ecx, cs:g_dwHashInfoTotalCount
0x180024072  lea     rdx, g_pHashInfo
0x180024079  mov     eax, dword ptr [rsp+3B0h+pbOutput]
0x18002407d  mov     [rbx+8], eax
0x180024080  lea     eax, [rcx+8FF9h]
0x180024086  mov     [rdx+rcx*8], rbx
0x18002408a  mov     [rbx+10h], eax
0x18002408d  lea     eax, [rcx-10000006h]
0x180024093  mov     [rbx+0Ch], eax
0x180024096  inc     ecx
0x180024098  mov     eax, [rsp+3B0h+var_37C]
0x18002409c  mov     [rbx+14h], eax
0x18002409f  mov     cs:g_dwHashInfoTotalCount, ecx
0x1800240a5  jmp     short loc_1800240B7
0x1800240a7  lea     rcx, [rsp+3B0h+var_378]
0x1800240ac  call    TlsCloseRegKey
0x1800240b1  mov     ecx, cs:g_dwHashInfoTotalCount
0x1800240b7  inc     edi
0x1800240b9  cmp     ecx, 10h
0x1800240bc  jb      loc_180023EDC
0x1800240c2  lea     rcx, [rsp+3B0h+KeyHandle]
0x1800240c7  call    TlsCloseRegKey
0x1800240cc  mov     rcx, [rbp+2B0h+var_30]
0x1800240d3  xor     rcx, rsp; StackCookie
0x1800240d6  call    __security_check_cookie
0x1800240db  add     rsp, 390h
0x1800240e2  pop     r14
0x1800240e4  pop     rdi
0x1800240e5  pop     rsi
0x1800240e6  pop     rbx
0x1800240e7  pop     rbp
0x1800240e8  retn
```
