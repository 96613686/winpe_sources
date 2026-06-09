# GetExternalCipherAlgorithms

- ea: `0x14000d5d8`
- end: `0x14000d905`
- name: `GetExternalCipherAlgorithms`
- size: `813`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000bff0`

## callees

- `0x140006110`
- `0x14000c5d8`
- `0x14000c6fc`
- `0x14000c7f0`
- `0x14000c86c`
- `0x14000d510`
- `0x14000d5d8`
- `0x140010160`
- `0x1400105c0`

## import_xrefs

- `ntoskrnl!ZwEnumerateKey` at `0x14000d6b1`
- `ntoskrnl!ZwEnumerateKey` at `0x14000d6b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d82c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d861`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d82c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d861`
- `ntoskrnl!ExAllocatePool2` at `0x14000d7e7`
- `ntoskrnl!ExAllocatePool2` at `0x14000d812`
- `ntoskrnl!ExAllocatePool2` at `0x14000d846`
- `ntoskrnl!ExAllocatePool2` at `0x14000d7e7`
- `ntoskrnl!ExAllocatePool2` at `0x14000d812`
- `ntoskrnl!ExAllocatePool2` at `0x14000d846`
- `cng!BCryptOpenAlgorithmProvider` at `0x14000d76f`
- `cng!BCryptOpenAlgorithmProvider` at `0x14000d76f`
- `cng!BCryptGetProperty` at `0x14000d7a8`
- `cng!BCryptGetProperty` at `0x14000d7a8`
- `cng!BCryptCloseAlgorithmProvider` at `0x14000d7bf`
- `cng!BCryptCloseAlgorithmProvider` at `0x14000d7d0`
- `cng!BCryptCloseAlgorithmProvider` at `0x14000d7bf`
- `cng!BCryptCloseAlgorithmProvider` at `0x14000d7d0`

## string_xrefs

- `0x14000d64c`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Cipher`
- `0x14000d6fb`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Cipher`

## pseudocode

```c
__int64 GetExternalCipherAlgorithms()
{
  __int64 result; // rax
  ULONG v1; // edi
  unsigned __int64 v2; // rdx
  unsigned __int64 v3; // r9
  HANDLE v4; // rbx
  wchar_t **Pool2; // rax
  wchar_t **v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rax
  wchar_t *v9; // rcx
  int v10; // ecx
  int v11; // eax
  UCHAR pbOutput[8]; // [rsp+30h] [rbp-D0h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v14; // [rsp+40h] [rbp-C0h] BYREF
  ULONG ResultLength; // [rsp+48h] [rbp-B8h] BYREF
  ULONG pcbResult; // [rsp+4Ch] [rbp-B4h] BYREF
  HANDLE KeyHandle[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszAlgId[128]; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD KeyInformation[136]; // [rsp+160h] [rbp+60h] BYREF
  WCHAR v20[64]; // [rsp+380h] [rbp+280h] BYREF

  KeyHandle[0] = 0;
  v14 = 0;
  memset(v20, 0, sizeof(v20));
  *(_DWORD *)pbOutput = 0;
  phAlgorithm = 0;
  pcbResult = 0;
  result = FreeExternalCipherAlgorithms();
  if ( (unsigned int)g_dwCipherInfoTotalCount < 0x10 )
  {
    result = TlsOpenRegKey(
               L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Protocol "
                "Provider\\Cipher",
               0,
               KeyHandle);
    if ( (int)result >= 0 )
    {
      v1 = 0;
      for ( ResultLength = 0; (unsigned int)g_dwCipherInfoTotalCount < 0x10; ++v1 )
      {
        memset(KeyInformation, 0, 536);
        if ( ZwEnumerateKey(KeyHandle[0], v1, KeyBasicInformation, KeyInformation, 0x218u, &ResultLength) < 0 )
          return TlsCloseRegKey(KeyHandle);
        v3 = -1;
        do
          ++v3;
        while ( *((_WORD *)&KeyInformation[4] + v3) );
        if ( (int)RtlStringCchCopyNW(v20, v2, (const unsigned __int16 *)&KeyInformation[4], v3) >= 0
          && (int)TlsOpenRegKey(
                    L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Prot"
                     "ocol Provider\\Cipher",
                    v20,
                    &v14) >= 0 )
        {
          memset(pszAlgId, 0, sizeof(pszAlgId));
          v4 = v14;
          if ( (int)GetSslStringFromRegistry(v14, L"CngAlgorithm", pszAlgId) < 0 )
          {
            TlsCloseRegKey(&v14);
            continue;
          }
          GetSslStringFromRegistry(v4, L"CipherMode", &pszAlgId[64]);
          TlsCloseRegKey(&v14);
          if ( BCryptOpenAlgorithmProvider(&phAlgorithm, pszAlgId, 0, 0) >= 0 )
          {
            if ( BCryptGetProperty(phAlgorithm, L"BlockLength", pbOutput, 4u, &pcbResult, 0) >= 0 )
            {
              BCryptCloseAlgorithmProvider(phAlgorithm, 0);
              Pool2 = (wchar_t **)ExAllocatePool2(64, 32, 1131180883);
              v6 = Pool2;
              if ( Pool2 )
              {
                *(_OWORD *)Pool2 = 0;
                *((_OWORD *)Pool2 + 1) = 0;
                v7 = ExAllocatePool2(64, 128, 1131180883);
                *v6 = (wchar_t *)v7;
                if ( v7 )
                {
                  v8 = ExAllocatePool2(64, 128, 1131180883);
                  v9 = *v6;
                  v6[3] = (wchar_t *)v8;
                  if ( v8 )
                  {
                    wcscpy_s(v9, 0x40u, pszAlgId);
                    wcscpy_s(v6[3], 0x40u, &pszAlgId[64]);
                    v10 = g_dwCipherInfoTotalCount;
                    v11 = g_dwCipherInfoTotalCount - 1073741830;
                    g_pCipherInfo[g_dwCipherInfoTotalCount] = (__int64)v6;
                    *((_DWORD *)v6 + 3) = v11;
                    *((_DWORD *)v6 + 4) = v10 + 28665;
                    *((_DWORD *)v6 + 2) = *(_DWORD *)pbOutput;
                    g_dwCipherInfoTotalCount = v10 + 1;
                    continue;
                  }
                  ExFreePoolWithTag(v9, 0x436C7353u);
                }
                ExFreePoolWithTag(v6, 0x436C7353u);
              }
            }
            else
            {
              BCryptCloseAlgorithmProvider(phAlgorithm, 0);
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
0x14000d5d8  push    rbp
0x14000d5da  push    rbx
0x14000d5db  push    rsi
0x14000d5dc  push    rdi
0x14000d5dd  push    r12
0x14000d5df  push    r14
0x14000d5e1  push    r15
0x14000d5e3  lea     rbp, [rsp-310h]
0x14000d5eb  sub     rsp, 410h
0x14000d5f2  mov     rax, cs:__security_cookie
0x14000d5f9  xor     rax, rsp
0x14000d5fc  mov     [rbp+340h+var_40], rax
0x14000d603  xor     esi, esi
0x14000d605  lea     rcx, [rbp+340h+var_C0]; void *
0x14000d60c  mov     r12d, 80h
0x14000d612  mov     [rsp+440h+KeyHandle], rsi
0x14000d617  mov     r8d, r12d; Size
0x14000d61a  mov     [rsp+440h+var_400], rsi
0x14000d61f  xor     edx, edx; Val
0x14000d621  call    memset
0x14000d626  mov     dword ptr [rsp+440h+pbOutput], esi
0x14000d62a  mov     [rsp+440h+phAlgorithm], rsi
0x14000d62f  mov     [rsp+440h+pcbResult], esi
0x14000d633  call    FreeExternalCipherAlgorithms
0x14000d638  cmp     cs:g_dwCipherInfoTotalCount, 10h
0x14000d63f  jnb     loc_14000D8E3
0x14000d645  lea     r8, [rsp+440h+KeyHandle]; KeyHandle
0x14000d64a  xor     edx, edx; PCWSTR
0x14000d64c  lea     rcx, aRegistryMachin_4; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x14000d653  call    TlsOpenRegKey
0x14000d658  test    eax, eax
0x14000d65a  js      loc_14000D8E3
0x14000d660  cmp     cs:g_dwCipherInfoTotalCount, 10h
0x14000d667  mov     edi, esi
0x14000d669  mov     [rsp+440h+var_3F8], esi
0x14000d66d  jnb     loc_14000D8D9
0x14000d673  mov     r14d, 436C7353h
0x14000d679  lea     r15d, [rsi+40h]
0x14000d67d  xor     edx, edx; Val
0x14000d67f  mov     [rbp+340h+KeyInformation], esi
0x14000d682  mov     r8d, 214h; Size
0x14000d688  lea     rcx, [rbp+340h+var_2DC]; void *
0x14000d68c  call    memset
0x14000d691  mov     rcx, [rsp+440h+KeyHandle]; KeyHandle
0x14000d696  lea     rax, [rsp+440h+var_3F8]
0x14000d69b  mov     [rsp+440h+ResultLength], rax; ResultLength
0x14000d6a0  lea     r9, [rbp+340h+KeyInformation]; KeyInformation
0x14000d6a4  xor     r8d, r8d; KeyInformationClass
0x14000d6a7  mov     [rsp+440h+Length], 218h; Length
0x14000d6af  mov     edx, edi; Index
0x14000d6b1  call    cs:__imp_ZwEnumerateKey
0x14000d6b8  nop     dword ptr [rax+rax+00h]
0x14000d6bd  test    eax, eax
0x14000d6bf  js      loc_14000D8D9
0x14000d6c5  lea     rax, [rbp+340h+var_2D0]
0x14000d6c9  or      r9, 0FFFFFFFFFFFFFFFFh
0x14000d6cd  inc     r9; unsigned __int64
0x14000d6d0  cmp     [rax+r9*2], si
0x14000d6d5  jnz     short loc_14000D6CD
0x14000d6d7  lea     r8, [rbp+340h+var_2D0]; unsigned __int16 *
0x14000d6db  lea     rcx, [rbp+340h+var_C0]; unsigned __int16 *
0x14000d6e2  call    ?RtlStringCchCopyNW@@YAJPEAG_KPEBG1@Z; RtlStringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x14000d6e7  test    eax, eax
0x14000d6e9  js      loc_14000D8CA
0x14000d6ef  lea     r8, [rsp+440h+var_400]; KeyHandle
0x14000d6f4  lea     rdx, [rbp+340h+var_C0]; PCWSTR
0x14000d6fb  lea     rcx, aRegistryMachin_4; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x14000d702  call    TlsOpenRegKey
0x14000d707  test    eax, eax
0x14000d709  js      loc_14000D8CA
0x14000d70f  xor     edx, edx; Val
0x14000d711  lea     rcx, [rsp+440h+pszAlgId]; void *
0x14000d716  mov     r8d, 100h; Size
0x14000d71c  call    memset
0x14000d721  mov     rbx, [rsp+440h+var_400]
0x14000d726  lea     r8, [rsp+440h+pszAlgId]; unsigned __int16 *
0x14000d72b  mov     rcx, rbx; KeyHandle
0x14000d72e  lea     rdx, aCngalgorithm; "CngAlgorithm"
0x14000d735  call    GetSslStringFromRegistry
0x14000d73a  test    eax, eax
0x14000d73c  js      loc_14000D8C0
0x14000d742  lea     r8, [rbp+340h+Src]; unsigned __int16 *
0x14000d746  mov     rcx, rbx; KeyHandle
0x14000d749  lea     rdx, aCiphermode; "CipherMode"
0x14000d750  call    GetSslStringFromRegistry
0x14000d755  lea     rcx, [rsp+440h+var_400]
0x14000d75a  call    TlsCloseRegKey
0x14000d75f  xor     r9d, r9d; dwFlags
0x14000d762  lea     rdx, [rsp+440h+pszAlgId]; pszAlgId
0x14000d767  xor     r8d, r8d; pszImplementation
0x14000d76a  lea     rcx, [rsp+440h+phAlgorithm]; phAlgorithm
0x14000d76f  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14000d776  nop     dword ptr [rax+rax+00h]
0x14000d77b  test    eax, eax
0x14000d77d  js      loc_14000D8CA
0x14000d783  mov     rcx, [rsp+440h+phAlgorithm]; hObject
0x14000d788  lea     rax, [rsp+440h+pcbResult]
0x14000d78d  mov     dword ptr [rsp+440h+ResultLength], esi; dwFlags
0x14000d791  lea     r8, [rsp+440h+pbOutput]; pbOutput
0x14000d796  mov     r9d, 4; cbOutput
0x14000d79c  mov     qword ptr [rsp+440h+Length], rax; pcbResult
0x14000d7a1  lea     rdx, aBlocklength; "BlockLength"
0x14000d7a8  call    cs:__imp_BCryptGetProperty
0x14000d7af  nop     dword ptr [rax+rax+00h]
0x14000d7b4  mov     rcx, [rsp+440h+phAlgorithm]; hAlgorithm
0x14000d7b9  xor     edx, edx; dwFlags
0x14000d7bb  test    eax, eax
0x14000d7bd  jns     short loc_14000D7D0
0x14000d7bf  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14000d7c6  nop     dword ptr [rax+rax+00h]
0x14000d7cb  jmp     loc_14000D8CA
0x14000d7d0  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14000d7d7  nop     dword ptr [rax+rax+00h]
0x14000d7dc  mov     r8d, r14d
0x14000d7df  mov     edx, 20h ; ' '
0x14000d7e4  mov     rcx, r15
0x14000d7e7  call    cs:__imp_ExAllocatePool2
0x14000d7ee  nop     dword ptr [rax+rax+00h]
0x14000d7f3  mov     rbx, rax
0x14000d7f6  test    rax, rax
0x14000d7f9  jz      loc_14000D8CA
0x14000d7ff  xorps   xmm0, xmm0
0x14000d802  mov     r8d, r14d
0x14000d805  movups  xmmword ptr [rax], xmm0
0x14000d808  mov     rdx, r12
0x14000d80b  mov     rcx, r15
0x14000d80e  movups  xmmword ptr [rax+10h], xmm0
0x14000d812  call    cs:__imp_ExAllocatePool2
0x14000d819  nop     dword ptr [rax+rax+00h]
0x14000d81e  mov     [rbx], rax
0x14000d821  test    rax, rax
0x14000d824  jnz     short loc_14000D83D
0x14000d826  mov     edx, r14d; Tag
0x14000d829  mov     rcx, rbx; P
0x14000d82c  call    cs:__imp_ExFreePoolWithTag
0x14000d833  nop     dword ptr [rax+rax+00h]
0x14000d838  jmp     loc_14000D8CA
0x14000d83d  mov     r8d, r14d
0x14000d840  mov     rdx, r12
0x14000d843  mov     rcx, r15
0x14000d846  call    cs:__imp_ExAllocatePool2
0x14000d84d  nop     dword ptr [rax+rax+00h]
0x14000d852  mov     rcx, [rbx]; Dst
0x14000d855  mov     [rbx+18h], rax
0x14000d859  test    rax, rax
0x14000d85c  jnz     short loc_14000D86F
0x14000d85e  mov     edx, r14d; Tag
0x14000d861  call    cs:__imp_ExFreePoolWithTag
0x14000d868  nop     dword ptr [rax+rax+00h]
0x14000d86d  jmp     short loc_14000D826
0x14000d86f  lea     r8, [rsp+440h+pszAlgId]; Src
0x14000d874  mov     rdx, r15; SizeInWords
0x14000d877  call    wcscpy_s
0x14000d87c  mov     rcx, [rbx+18h]; Dst
0x14000d880  lea     r8, [rbp+340h+Src]; Src
0x14000d884  mov     rdx, r15; SizeInWords
0x14000d887  call    wcscpy_s
0x14000d88c  mov     ecx, cs:g_dwCipherInfoTotalCount
0x14000d892  lea     rdx, g_pCipherInfo
0x14000d899  lea     eax, [rcx-40000006h]
0x14000d89f  mov     [rdx+rcx*8], rbx
0x14000d8a3  mov     [rbx+0Ch], eax
0x14000d8a6  lea     eax, [rcx+6FF9h]
0x14000d8ac  mov     [rbx+10h], eax
0x14000d8af  inc     ecx
0x14000d8b1  mov     eax, dword ptr [rsp+440h+pbOutput]
0x14000d8b5  mov     [rbx+8], eax
0x14000d8b8  mov     cs:g_dwCipherInfoTotalCount, ecx
0x14000d8be  jmp     short loc_14000D8CA
0x14000d8c0  lea     rcx, [rsp+440h+var_400]
0x14000d8c5  call    TlsCloseRegKey
0x14000d8ca  inc     edi
0x14000d8cc  cmp     cs:g_dwCipherInfoTotalCount, 10h
0x14000d8d3  jb      loc_14000D67D
0x14000d8d9  lea     rcx, [rsp+440h+KeyHandle]
0x14000d8de  call    TlsCloseRegKey
0x14000d8e3  mov     rcx, [rbp+340h+var_40]
0x14000d8ea  xor     rcx, rsp; StackCookie
0x14000d8ed  call    __security_check_cookie
0x14000d8f2  add     rsp, 410h
0x14000d8f9  pop     r15
0x14000d8fb  pop     r14
0x14000d8fd  pop     r12
0x14000d8ff  pop     rdi
0x14000d900  pop     rsi
0x14000d901  pop     rbx
0x14000d902  pop     rbp
0x14000d903  retn
```
