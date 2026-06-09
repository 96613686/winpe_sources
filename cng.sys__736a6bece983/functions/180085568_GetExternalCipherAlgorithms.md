# GetExternalCipherAlgorithms

- ea: `0x180085568`
- end: `0x180085836`
- name: `GetExternalCipherAlgorithms`
- size: `718`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
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
- `0x180084e5c`
- `0x180084f50`
- `0x180084f84`
- `0x1800854c4`
- `0x180085568`
- `0x18009f650`
- `0x18009fa80`

## import_xrefs

- `ntoskrnl!ZwEnumerateKey` at `0x18008562b`
- `ntoskrnl!ZwEnumerateKey` at `0x18008562b`
- `ntoskrnl!wcscpy_s` at `0x18008579c`
- `ntoskrnl!wcscpy_s` at `0x1800857b5`
- `ntoskrnl!wcscpy_s` at `0x18008579c`
- `ntoskrnl!wcscpy_s` at `0x1800857b5`

## string_xrefs

- `0x1800855d8`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Cipher`
- `0x180085675`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Cipher`

## pseudocode

```c
__int64 GetExternalCipherAlgorithms()
{
  __int64 result; // rax
  __int64 v1; // r9
  ULONG i; // edi
  unsigned __int64 v3; // rdx
  unsigned __int64 v4; // r9
  __int64 v5; // r9
  HANDLE v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 *v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rax
  void *v20; // rcx
  int v21; // ecx
  int v22; // eax
  UCHAR pbOutput[8]; // [rsp+30h] [rbp-D0h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v25; // [rsp+40h] [rbp-C0h] BYREF
  ULONG ResultLength; // [rsp+48h] [rbp-B8h] BYREF
  ULONG pcbResult; // [rsp+4Ch] [rbp-B4h] BYREF
  HANDLE KeyHandle[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszAlgId[128]; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD KeyInformation[136]; // [rsp+160h] [rbp+60h] BYREF
  WCHAR v31[64]; // [rsp+380h] [rbp+280h] BYREF

  KeyHandle[0] = 0;
  v25 = 0;
  memset(v31, 0, sizeof(v31));
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
               KeyHandle,
               v1);
    if ( (int)result >= 0 )
    {
      ResultLength = 0;
      for ( i = 0; ; ++i )
      {
        if ( (unsigned int)g_dwCipherInfoTotalCount >= 0x10 )
          return TlsCloseRegKey(KeyHandle);
        memset(KeyInformation, 0, 536);
        if ( ZwEnumerateKey(KeyHandle[0], i, KeyBasicInformation, KeyInformation, 0x218u, &ResultLength) < 0 )
          return TlsCloseRegKey(KeyHandle);
        v4 = -1;
        do
          ++v4;
        while ( *((_WORD *)&KeyInformation[4] + v4) );
        if ( (int)RtlStringCchCopyNW(v31, v3, (const unsigned __int16 *)&KeyInformation[4], v4) >= 0
          && (int)TlsOpenRegKey(
                    L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Prot"
                     "ocol Provider\\Cipher",
                    v31,
                    &v25,
                    v5) >= 0 )
        {
          memset(pszAlgId, 0, sizeof(pszAlgId));
          v6 = v25;
          if ( (int)GetSslStringFromRegistry(v25, L"CngAlgorithm", pszAlgId) < 0 )
          {
            TlsCloseRegKey(&v25);
          }
          else
          {
            GetSslStringFromRegistry(v6, L"CipherMode", &pszAlgId[64]);
            TlsCloseRegKey(&v25);
            if ( BCryptOpenAlgorithmProvider(&phAlgorithm, pszAlgId, 0, 0) < 0 )
              continue;
            if ( BCryptGetProperty(phAlgorithm, L"BlockLength", pbOutput, 4u, &pcbResult, 0) < 0 )
            {
              BCryptCloseAlgorithmProvider(phAlgorithm, 0);
              continue;
            }
            BCryptCloseAlgorithmProvider(phAlgorithm, 0);
            v10 = (__int64 *)MSCryptAlloc(32, v7, v8, v9);
            v14 = v10;
            if ( v10 )
            {
              *(_OWORD *)v10 = 0;
              *((_OWORD *)v10 + 1) = 0;
              v15 = MSCryptAlloc(128, v11, v12, v13);
              *v14 = v15;
              if ( !v15 )
                goto LABEL_15;
              v19 = MSCryptAlloc(128, v16, v17, v18);
              v20 = (void *)*v14;
              v14[3] = v19;
              if ( !v19 )
              {
                MSCryptFree(v20);
LABEL_15:
                MSCryptFree(v14);
                continue;
              }
              wcscpy_s((wchar_t *)v20, 0x40u, pszAlgId);
              wcscpy_s((wchar_t *)v14[3], 0x40u, &pszAlgId[64]);
              v21 = g_dwCipherInfoTotalCount;
              v22 = g_dwCipherInfoTotalCount - 1073741830;
              g_pCipherInfo[g_dwCipherInfoTotalCount] = (__int64)v14;
              *((_DWORD *)v14 + 3) = v22;
              *((_DWORD *)v14 + 4) = v21 + 28665;
              *((_DWORD *)v14 + 2) = *(_DWORD *)pbOutput;
              g_dwCipherInfoTotalCount = v21 + 1;
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180085568  push    rbp
0x18008556a  push    rbx
0x18008556b  push    rsi
0x18008556c  push    rdi
0x18008556d  push    r14
0x18008556f  lea     rbp, [rsp-310h]
0x180085577  sub     rsp, 410h
0x18008557e  mov     rax, cs:__security_cookie
0x180085585  xor     rax, rsp
0x180085588  mov     [rbp+330h+var_30], rax
0x18008558f  xor     esi, esi
0x180085591  lea     rcx, [rbp+330h+var_B0]; void *
0x180085598  mov     r14d, 80h
0x18008559e  mov     [rsp+430h+KeyHandle], rsi
0x1800855a3  mov     r8d, r14d; Size
0x1800855a6  mov     [rsp+430h+var_3F0], rsi
0x1800855ab  xor     edx, edx; Val
0x1800855ad  call    memset
0x1800855b2  mov     dword ptr [rsp+430h+pbOutput], esi
0x1800855b6  mov     [rsp+430h+phAlgorithm], rsi
0x1800855bb  mov     [rsp+430h+pcbResult], esi
0x1800855bf  call    FreeExternalCipherAlgorithms
0x1800855c4  cmp     cs:g_dwCipherInfoTotalCount, 10h
0x1800855cb  jnb     loc_180085818
0x1800855d1  lea     r8, [rsp+430h+KeyHandle]; KeyHandle
0x1800855d6  xor     edx, edx; PCWSTR
0x1800855d8  lea     rcx, aRegistryMachin_12; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x1800855df  call    TlsOpenRegKey
0x1800855e4  test    eax, eax
0x1800855e6  js      loc_180085818
0x1800855ec  mov     [rsp+430h+var_3E8], esi
0x1800855f0  mov     edi, esi
0x1800855f2  jmp     loc_180085801
0x1800855f7  xor     edx, edx; Val
0x1800855f9  mov     [rbp+330h+KeyInformation], esi
0x1800855fc  mov     r8d, 214h; Size
0x180085602  lea     rcx, [rbp+330h+var_2CC]; void *
0x180085606  call    memset
0x18008560b  mov     rcx, [rsp+430h+KeyHandle]; KeyHandle
0x180085610  lea     rax, [rsp+430h+var_3E8]
0x180085615  mov     [rsp+430h+ResultLength], rax; ResultLength
0x18008561a  lea     r9, [rbp+330h+KeyInformation]; KeyInformation
0x18008561e  xor     r8d, r8d; KeyInformationClass
0x180085621  mov     [rsp+430h+Length], 218h; Length
0x180085629  mov     edx, edi; Index
0x18008562b  call    cs:__imp_ZwEnumerateKey
0x180085632  nop     dword ptr [rax+rax+00h]
0x180085637  test    eax, eax
0x180085639  js      loc_18008580E
0x18008563f  lea     rax, [rbp+330h+var_2C0]
0x180085643  or      r9, 0FFFFFFFFFFFFFFFFh
0x180085647  inc     r9; unsigned __int64
0x18008564a  cmp     [rax+r9*2], si
0x18008564f  jnz     short loc_180085647
0x180085651  lea     r8, [rbp+330h+var_2C0]; unsigned __int16 *
0x180085655  lea     rcx, [rbp+330h+var_B0]; unsigned __int16 *
0x18008565c  call    ?RtlStringCchCopyNW@@YAJPEAG_KPEBG1@Z; RtlStringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180085661  test    eax, eax
0x180085663  js      loc_1800857FF
0x180085669  lea     r8, [rsp+430h+var_3F0]; KeyHandle
0x18008566e  lea     rdx, [rbp+330h+var_B0]; PCWSTR
0x180085675  lea     rcx, aRegistryMachin_12; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18008567c  call    TlsOpenRegKey
0x180085681  test    eax, eax
0x180085683  js      loc_1800857FF
0x180085689  xor     edx, edx; Val
0x18008568b  lea     rcx, [rsp+430h+pszAlgId]; void *
0x180085690  mov     r8d, 100h; Size
0x180085696  call    memset
0x18008569b  mov     rbx, [rsp+430h+var_3F0]
0x1800856a0  lea     r8, [rsp+430h+pszAlgId]; unsigned __int16 *
0x1800856a5  mov     rcx, rbx; KeyHandle
0x1800856a8  lea     rdx, aCngalgorithm; "CngAlgorithm"
0x1800856af  call    GetSslStringFromRegistry
0x1800856b4  test    eax, eax
0x1800856b6  js      loc_1800857F5
0x1800856bc  lea     r8, [rbp+330h+Src]; unsigned __int16 *
0x1800856c0  mov     rcx, rbx; KeyHandle
0x1800856c3  lea     rdx, aCiphermode; "CipherMode"
0x1800856ca  call    GetSslStringFromRegistry
0x1800856cf  lea     rcx, [rsp+430h+var_3F0]
0x1800856d4  call    TlsCloseRegKey
0x1800856d9  xor     r9d, r9d; dwFlags
0x1800856dc  lea     rdx, [rsp+430h+pszAlgId]; pszAlgId
0x1800856e1  xor     r8d, r8d; pszImplementation
0x1800856e4  lea     rcx, [rsp+430h+phAlgorithm]; phAlgorithm
0x1800856e9  call    BCryptOpenAlgorithmProvider
0x1800856ee  test    eax, eax
0x1800856f0  js      loc_1800857FF
0x1800856f6  mov     rcx, [rsp+430h+phAlgorithm]; hObject
0x1800856fb  lea     rax, [rsp+430h+pcbResult]
0x180085700  mov     dword ptr [rsp+430h+ResultLength], esi; dwFlags
0x180085704  lea     r8, [rsp+430h+pbOutput]; pbOutput
0x180085709  mov     r9d, 4; cbOutput
0x18008570f  mov     qword ptr [rsp+430h+Length], rax; pcbResult
0x180085714  lea     rdx, aBlocklength; "BlockLength"
0x18008571b  call    BCryptGetProperty
0x180085720  mov     rcx, [rsp+430h+phAlgorithm]; hAlgorithm
0x180085725  xor     edx, edx; dwFlags
0x180085727  test    eax, eax
0x180085729  jns     short loc_180085735
0x18008572b  call    BCryptCloseAlgorithmProvider
0x180085730  jmp     loc_1800857FF
0x180085735  call    BCryptCloseAlgorithmProvider
0x18008573a  mov     ecx, 20h ; ' '
0x18008573f  call    MSCryptAlloc
0x180085744  mov     rbx, rax
0x180085747  test    rax, rax
0x18008574a  jz      loc_1800857FF
0x180085750  xorps   xmm0, xmm0
0x180085753  mov     rcx, r14
0x180085756  movups  xmmword ptr [rax], xmm0
0x180085759  movups  xmmword ptr [rax+10h], xmm0
0x18008575d  call    MSCryptAlloc
0x180085762  mov     [rbx], rax
0x180085765  test    rax, rax
0x180085768  jnz     short loc_180085777
0x18008576a  mov     rcx, rbx; P
0x18008576d  call    MSCryptFree
0x180085772  jmp     loc_1800857FF
0x180085777  mov     rcx, r14
0x18008577a  call    MSCryptAlloc
0x18008577f  mov     rcx, [rbx]; P
0x180085782  mov     [rbx+18h], rax
0x180085786  test    rax, rax
0x180085789  jnz     short loc_180085792
0x18008578b  call    MSCryptFree
0x180085790  jmp     short loc_18008576A
0x180085792  lea     r8, [rsp+430h+pszAlgId]; Src
0x180085797  mov     edx, 40h ; '@'; SizeInWords
0x18008579c  call    cs:__imp_wcscpy_s
0x1800857a3  nop     dword ptr [rax+rax+00h]
0x1800857a8  mov     rcx, [rbx+18h]; Dst
0x1800857ac  lea     r8, [rbp+330h+Src]; Src
0x1800857b0  mov     edx, 40h ; '@'; SizeInWords
0x1800857b5  call    cs:__imp_wcscpy_s
0x1800857bc  nop     dword ptr [rax+rax+00h]
0x1800857c1  mov     ecx, cs:g_dwCipherInfoTotalCount
0x1800857c7  lea     rdx, g_pCipherInfo
0x1800857ce  lea     eax, [rcx-40000006h]
0x1800857d4  mov     [rdx+rcx*8], rbx
0x1800857d8  mov     [rbx+0Ch], eax
0x1800857db  lea     eax, [rcx+6FF9h]
0x1800857e1  mov     [rbx+10h], eax
0x1800857e4  inc     ecx
0x1800857e6  mov     eax, dword ptr [rsp+430h+pbOutput]
0x1800857ea  mov     [rbx+8], eax
0x1800857ed  mov     cs:g_dwCipherInfoTotalCount, ecx
0x1800857f3  jmp     short loc_1800857FF
0x1800857f5  lea     rcx, [rsp+430h+var_3F0]
0x1800857fa  call    TlsCloseRegKey
0x1800857ff  inc     edi
0x180085801  cmp     cs:g_dwCipherInfoTotalCount, 10h
0x180085808  jb      loc_1800855F7
0x18008580e  lea     rcx, [rsp+430h+KeyHandle]
0x180085813  call    TlsCloseRegKey
0x180085818  mov     rcx, [rbp+330h+var_30]
0x18008581f  xor     rcx, rsp; StackCookie
0x180085822  call    __security_check_cookie
0x180085827  add     rsp, 410h
0x18008582e  pop     r14
0x180085830  pop     rdi
0x180085831  pop     rsi
0x180085832  pop     rbx
0x180085833  pop     rbp
0x180085834  retn
```
