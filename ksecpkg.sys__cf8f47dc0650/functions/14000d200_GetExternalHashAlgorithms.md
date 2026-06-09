# GetExternalHashAlgorithms

- ea: `0x14000d200`
- end: `0x14000d508`
- name: `GetExternalHashAlgorithms`
- size: `776`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000bff0`

## callees

- `0x140006110`
- `0x14000c5d8`
- `0x14000c63c`
- `0x14000c6fc`
- `0x14000c7f0`
- `0x14000c86c`
- `0x14000d16c`
- `0x14000d200`
- `0x140010160`
- `0x1400105c0`

## import_xrefs

- `ntoskrnl!ZwEnumerateKey` at `0x14000d2e9`
- `ntoskrnl!ZwEnumerateKey` at `0x14000d2e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d46a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d46a`
- `ntoskrnl!ExAllocatePool2` at `0x14000d41e`
- `ntoskrnl!ExAllocatePool2` at `0x14000d44e`
- `ntoskrnl!ExAllocatePool2` at `0x14000d41e`
- `ntoskrnl!ExAllocatePool2` at `0x14000d44e`
- `cng!BCryptOpenAlgorithmProvider` at `0x14000d3a3`
- `cng!BCryptOpenAlgorithmProvider` at `0x14000d3a3`
- `cng!BCryptGetProperty` at `0x14000d3dc`
- `cng!BCryptGetProperty` at `0x14000d3dc`
- `cng!BCryptCloseAlgorithmProvider` at `0x14000d3f3`
- `cng!BCryptCloseAlgorithmProvider` at `0x14000d404`
- `cng!BCryptCloseAlgorithmProvider` at `0x14000d3f3`
- `cng!BCryptCloseAlgorithmProvider` at `0x14000d404`

## string_xrefs

- `0x14000d287`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Hash`
- `0x14000d335`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Hash`

## pseudocode

```c
__int64 GetExternalHashAlgorithms()
{
  __int64 result; // rax
  ULONG i; // edi
  unsigned __int64 v2; // rdx
  unsigned __int64 v3; // r9
  wchar_t **Pool2; // rbx
  wchar_t *v5; // rax
  __int64 v6; // rcx
  UCHAR pbOutput[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v8; // [rsp+34h] [rbp-CCh]
  HANDLE v9; // [rsp+38h] [rbp-C8h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp-C0h] BYREF
  ULONG ResultLength; // [rsp+48h] [rbp-B8h] BYREF
  ULONG pcbResult; // [rsp+4Ch] [rbp-B4h] BYREF
  HANDLE KeyHandle[2]; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD KeyInformation[136]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszAlgId[64]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR v16[64]; // [rsp+300h] [rbp+200h] BYREF

  KeyHandle[0] = 0;
  v9 = 0;
  memset(v16, 0, sizeof(v16));
  memset(pszAlgId, 0, sizeof(pszAlgId));
  *(_DWORD *)pbOutput = 0;
  phAlgorithm = 0;
  pcbResult = 0;
  v8 = 0;
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
        if ( (int)RtlStringCchCopyNW(v16, v2, (const unsigned __int16 *)&KeyInformation[4], v3) >= 0
          && (int)TlsOpenRegKey(
                    L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Prot"
                     "ocol Provider\\Hash",
                    v16,
                    &v9) >= 0 )
        {
          if ( (int)GetSslStringFromRegistry(v9, L"CngAlgorithm", pszAlgId) < 0 || (int)GetSslDWordFromRegistry(v9) < 0 )
          {
            TlsCloseRegKey(&v9);
          }
          else
          {
            TlsCloseRegKey(&v9);
            if ( BCryptOpenAlgorithmProvider(&phAlgorithm, pszAlgId, 0, 0) >= 0 )
            {
              if ( BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0) >= 0 )
              {
                BCryptCloseAlgorithmProvider(phAlgorithm, 0);
                Pool2 = (wchar_t **)ExAllocatePool2(64, 24, 1131180883);
                if ( Pool2 )
                {
                  *(_OWORD *)Pool2 = 0;
                  Pool2[2] = 0;
                  v5 = (wchar_t *)ExAllocatePool2(64, 128, 1131180883);
                  *Pool2 = v5;
                  if ( v5 )
                  {
                    wcscpy_s(v5, 0x40u, pszAlgId);
                    v6 = (unsigned int)g_dwHashInfoTotalCount;
                    *((_DWORD *)Pool2 + 2) = *(_DWORD *)pbOutput;
                    g_pHashInfo[v6] = (__int64)Pool2;
                    *((_DWORD *)Pool2 + 4) = v6 + 36857;
                    *((_DWORD *)Pool2 + 3) = v6 - 268435462;
                    *((_DWORD *)Pool2 + 5) = v8;
                    g_dwHashInfoTotalCount = v6 + 1;
                  }
                  else
                  {
                    ExFreePoolWithTag(Pool2, 0x436C7353u);
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
0x14000d200  push    rbp
0x14000d202  push    rbx
0x14000d203  push    rsi
0x14000d204  push    rdi
0x14000d205  push    r12
0x14000d207  push    r14
0x14000d209  lea     rbp, [rsp-298h]
0x14000d211  sub     rsp, 398h
0x14000d218  mov     rax, cs:__security_cookie
0x14000d21f  xor     rax, rsp
0x14000d222  mov     [rbp+2C0h+var_40], rax
0x14000d229  xor     esi, esi
0x14000d22b  lea     rcx, [rbp+2C0h+var_C0]; void *
0x14000d232  mov     r14d, 80h
0x14000d238  mov     [rsp+3C0h+KeyHandle], rsi
0x14000d23d  mov     r8d, r14d; Size
0x14000d240  mov     [rsp+3C0h+var_388], rsi
0x14000d245  xor     edx, edx; Val
0x14000d247  call    memset
0x14000d24c  mov     r8d, r14d; Size
0x14000d24f  lea     rcx, [rbp+2C0h+pszAlgId]; void *
0x14000d256  xor     edx, edx; Val
0x14000d258  call    memset
0x14000d25d  mov     dword ptr [rsp+3C0h+pbOutput], esi
0x14000d261  mov     [rsp+3C0h+phAlgorithm], rsi
0x14000d266  mov     [rsp+3C0h+pcbResult], esi
0x14000d26a  mov     [rsp+3C0h+var_38C], esi
0x14000d26e  call    FreeExternalHashAlgorithms
0x14000d273  cmp     cs:g_dwHashInfoTotalCount, 10h
0x14000d27a  jnb     loc_14000D4E8
0x14000d280  lea     r8, [rsp+3C0h+KeyHandle]; KeyHandle
0x14000d285  xor     edx, edx; PCWSTR
0x14000d287  lea     rcx, aRegistryMachin_0; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x14000d28e  call    TlsOpenRegKey
0x14000d293  test    eax, eax
0x14000d295  js      loc_14000D4E8
0x14000d29b  cmp     cs:g_dwHashInfoTotalCount, 10h
0x14000d2a2  mov     edi, esi
0x14000d2a4  jnb     loc_14000D4DE
0x14000d2aa  lea     r12d, [rsi+40h]
0x14000d2ae  xor     edx, edx; Val
0x14000d2b0  mov     [rsp+3C0h+KeyInformation], esi
0x14000d2b4  mov     r8d, 214h; Size
0x14000d2ba  lea     rcx, [rsp+3C0h+var_35C]; void *
0x14000d2bf  call    memset
0x14000d2c4  mov     rcx, [rsp+3C0h+KeyHandle]; KeyHandle
0x14000d2c9  lea     rax, [rsp+3C0h+var_378]
0x14000d2ce  mov     [rsp+3C0h+ResultLength], rax; ResultLength
0x14000d2d3  lea     r9, [rsp+3C0h+KeyInformation]; KeyInformation
0x14000d2d8  xor     r8d, r8d; KeyInformationClass
0x14000d2db  mov     [rsp+3C0h+Length], 218h; Length
0x14000d2e3  mov     edx, edi; Index
0x14000d2e5  mov     [rsp+3C0h+var_378], esi
0x14000d2e9  call    cs:__imp_ZwEnumerateKey
0x14000d2f0  nop     dword ptr [rax+rax+00h]
0x14000d2f5  test    eax, eax
0x14000d2f7  js      loc_14000D4DE
0x14000d2fd  lea     rax, [rsp+3C0h+var_350]
0x14000d302  or      r9, 0FFFFFFFFFFFFFFFFh
0x14000d306  inc     r9; unsigned __int64
0x14000d309  cmp     [rax+r9*2], si
0x14000d30e  jnz     short loc_14000D306
0x14000d310  lea     r8, [rsp+3C0h+var_350]; unsigned __int16 *
0x14000d315  lea     rcx, [rbp+2C0h+var_C0]; unsigned __int16 *
0x14000d31c  call    ?RtlStringCchCopyNW@@YAJPEAG_KPEBG1@Z; RtlStringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x14000d321  test    eax, eax
0x14000d323  js      loc_14000D4CF
0x14000d329  lea     r8, [rsp+3C0h+var_388]; KeyHandle
0x14000d32e  lea     rdx, [rbp+2C0h+var_C0]; PCWSTR
0x14000d335  lea     rcx, aRegistryMachin_0; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x14000d33c  call    TlsOpenRegKey
0x14000d341  test    eax, eax
0x14000d343  js      loc_14000D4CF
0x14000d349  mov     rcx, [rsp+3C0h+var_388]; KeyHandle
0x14000d34e  lea     r8, [rbp+2C0h+pszAlgId]; unsigned __int16 *
0x14000d355  lea     rdx, aCngalgorithm; "CngAlgorithm"
0x14000d35c  call    GetSslStringFromRegistry
0x14000d361  test    eax, eax
0x14000d363  js      loc_14000D4C5
0x14000d369  mov     rcx, [rsp+3C0h+var_388]; KeyHandle
0x14000d36e  lea     r8, [rsp+3C0h+var_38C]
0x14000d373  lea     rdx, aTlscodepoint; "TlsCodePoint"
0x14000d37a  call    GetSslDWordFromRegistry
0x14000d37f  test    eax, eax
0x14000d381  js      loc_14000D4C5
0x14000d387  lea     rcx, [rsp+3C0h+var_388]
0x14000d38c  call    TlsCloseRegKey
0x14000d391  xor     r9d, r9d; dwFlags
0x14000d394  lea     rdx, [rbp+2C0h+pszAlgId]; pszAlgId
0x14000d39b  xor     r8d, r8d; pszImplementation
0x14000d39e  lea     rcx, [rsp+3C0h+phAlgorithm]; phAlgorithm
0x14000d3a3  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14000d3aa  nop     dword ptr [rax+rax+00h]
0x14000d3af  test    eax, eax
0x14000d3b1  js      loc_14000D4CF
0x14000d3b7  mov     rcx, [rsp+3C0h+phAlgorithm]; hObject
0x14000d3bc  lea     rax, [rsp+3C0h+pcbResult]
0x14000d3c1  mov     dword ptr [rsp+3C0h+ResultLength], esi; dwFlags
0x14000d3c5  lea     r8, [rsp+3C0h+pbOutput]; pbOutput
0x14000d3ca  mov     r9d, 4; cbOutput
0x14000d3d0  mov     qword ptr [rsp+3C0h+Length], rax; pcbResult
0x14000d3d5  lea     rdx, pszProperty; "HashDigestLength"
0x14000d3dc  call    cs:__imp_BCryptGetProperty
0x14000d3e3  nop     dword ptr [rax+rax+00h]
0x14000d3e8  mov     rcx, [rsp+3C0h+phAlgorithm]; hAlgorithm
0x14000d3ed  xor     edx, edx; dwFlags
0x14000d3ef  test    eax, eax
0x14000d3f1  jns     short loc_14000D404
0x14000d3f3  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14000d3fa  nop     dword ptr [rax+rax+00h]
0x14000d3ff  jmp     loc_14000D4CF
0x14000d404  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14000d40b  nop     dword ptr [rax+rax+00h]
0x14000d410  mov     edx, 18h
0x14000d415  mov     r8d, 436C7353h
0x14000d41b  mov     rcx, r12
0x14000d41e  call    cs:__imp_ExAllocatePool2
0x14000d425  nop     dword ptr [rax+rax+00h]
0x14000d42a  mov     rbx, rax
0x14000d42d  test    rax, rax
0x14000d430  jz      loc_14000D4CF
0x14000d436  xorps   xmm0, xmm0
0x14000d439  xor     eax, eax
0x14000d43b  movups  xmmword ptr [rbx], xmm0
0x14000d43e  mov     r8d, 436C7353h
0x14000d444  mov     [rbx+10h], rax
0x14000d448  mov     rdx, r14
0x14000d44b  mov     rcx, r12
0x14000d44e  call    cs:__imp_ExAllocatePool2
0x14000d455  nop     dword ptr [rax+rax+00h]
0x14000d45a  mov     [rbx], rax
0x14000d45d  test    rax, rax
0x14000d460  jnz     short loc_14000D478
0x14000d462  mov     edx, 436C7353h; Tag
0x14000d467  mov     rcx, rbx; P
0x14000d46a  call    cs:__imp_ExFreePoolWithTag
0x14000d471  nop     dword ptr [rax+rax+00h]
0x14000d476  jmp     short loc_14000D4CF
0x14000d478  lea     r8, [rbp+2C0h+pszAlgId]; Src
0x14000d47f  mov     rdx, r12; SizeInWords
0x14000d482  mov     rcx, rax; Dst
0x14000d485  call    wcscpy_s
0x14000d48a  mov     ecx, cs:g_dwHashInfoTotalCount
0x14000d490  lea     rdx, g_pHashInfo
0x14000d497  mov     eax, dword ptr [rsp+3C0h+pbOutput]
0x14000d49b  mov     [rbx+8], eax
0x14000d49e  lea     eax, [rcx+8FF9h]
0x14000d4a4  mov     [rdx+rcx*8], rbx
0x14000d4a8  mov     [rbx+10h], eax
0x14000d4ab  lea     eax, [rcx-10000006h]
0x14000d4b1  mov     [rbx+0Ch], eax
0x14000d4b4  inc     ecx
0x14000d4b6  mov     eax, [rsp+3C0h+var_38C]
0x14000d4ba  mov     [rbx+14h], eax
0x14000d4bd  mov     cs:g_dwHashInfoTotalCount, ecx
0x14000d4c3  jmp     short loc_14000D4CF
0x14000d4c5  lea     rcx, [rsp+3C0h+var_388]
0x14000d4ca  call    TlsCloseRegKey
0x14000d4cf  inc     edi
0x14000d4d1  cmp     cs:g_dwHashInfoTotalCount, 10h
0x14000d4d8  jb      loc_14000D2AE
0x14000d4de  lea     rcx, [rsp+3C0h+KeyHandle]
0x14000d4e3  call    TlsCloseRegKey
0x14000d4e8  mov     rcx, [rbp+2C0h+var_40]
0x14000d4ef  xor     rcx, rsp; StackCookie
0x14000d4f2  call    __security_check_cookie
0x14000d4f7  add     rsp, 398h
0x14000d4fe  pop     r14
0x14000d500  pop     r12
0x14000d502  pop     rdi
0x14000d503  pop     rsi
0x14000d504  pop     rbx
0x14000d505  pop     rbp
0x14000d506  retn
```
