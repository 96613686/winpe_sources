# GetExternalCipherAlgorithms

- ea: `0x18008e740`
- end: `0x18008ea0e`
- name: `GetExternalCipherAlgorithms`
- size: `718`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
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
- `0x18008e05c`
- `0x18008e150`
- `0x18008e184`
- `0x18008e6c4`
- `0x18008e740`
- `0x1800a4260`
- `0x1800a4380`

## import_xrefs

- `ntoskrnl!ZwEnumerateKey` at `0x18008e803`
- `ntoskrnl!ZwEnumerateKey` at `0x18008e803`
- `ntoskrnl!wcscpy_s` at `0x18008e974`
- `ntoskrnl!wcscpy_s` at `0x18008e98d`
- `ntoskrnl!wcscpy_s` at `0x18008e974`
- `ntoskrnl!wcscpy_s` at `0x18008e98d`

## string_xrefs

- `0x18008e7b0`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Cipher`
- `0x18008e84d`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Cipher`

## pseudocode

```c
__int64 GetExternalCipherAlgorithms()
{
  __int64 result; // rax
  ULONG i; // edi
  unsigned __int64 v2; // rdx
  unsigned __int64 v3; // r9
  HANDLE v4; // rbx
  __int64 v5; // rdx
  __int64 *v6; // rax
  __int64 v7; // rdx
  __int64 *v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rax
  void *v12; // rcx
  int v13; // ecx
  int v14; // eax
  UCHAR pbOutput[8]; // [rsp+30h] [rbp-D0h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v17; // [rsp+40h] [rbp-C0h] BYREF
  ULONG ResultLength; // [rsp+48h] [rbp-B8h] BYREF
  ULONG pcbResult; // [rsp+4Ch] [rbp-B4h] BYREF
  HANDLE KeyHandle[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszAlgId[128]; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD KeyInformation[136]; // [rsp+160h] [rbp+60h] BYREF
  WCHAR v23[64]; // [rsp+380h] [rbp+280h] BYREF

  KeyHandle[0] = 0;
  v17 = 0;
  memset(v23, 0, sizeof(v23));
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
      ResultLength = 0;
      for ( i = 0; ; ++i )
      {
        if ( (unsigned int)g_dwCipherInfoTotalCount >= 0x10 )
          return TlsCloseRegKey(KeyHandle);
        memset(KeyInformation, 0, 536);
        if ( ZwEnumerateKey(KeyHandle[0], i, KeyBasicInformation, KeyInformation, 0x218u, &ResultLength) < 0 )
          return TlsCloseRegKey(KeyHandle);
        v3 = -1;
        do
          ++v3;
        while ( *((_WORD *)&KeyInformation[4] + v3) );
        if ( (int)RtlStringCchCopyNW(v23, v2, (const unsigned __int16 *)&KeyInformation[4], v3) >= 0
          && (int)TlsOpenRegKey(
                    L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Prot"
                     "ocol Provider\\Cipher",
                    v23,
                    &v17) >= 0 )
        {
          memset(pszAlgId, 0, sizeof(pszAlgId));
          v4 = v17;
          if ( (int)GetSslStringFromRegistry(v17, L"CngAlgorithm", pszAlgId) < 0 )
          {
            TlsCloseRegKey(&v17);
          }
          else
          {
            GetSslStringFromRegistry(v4, L"CipherMode", &pszAlgId[64]);
            TlsCloseRegKey(&v17);
            if ( BCryptOpenAlgorithmProvider(&phAlgorithm, pszAlgId, 0, 0) < 0 )
              continue;
            if ( BCryptGetProperty(phAlgorithm, L"BlockLength", pbOutput, 4u, &pcbResult, 0) < 0 )
            {
              BCryptCloseAlgorithmProvider(phAlgorithm, 0);
              continue;
            }
            BCryptCloseAlgorithmProvider(phAlgorithm, 0);
            v6 = (__int64 *)MSCryptAlloc(32, v5);
            v8 = v6;
            if ( v6 )
            {
              *(_OWORD *)v6 = 0;
              *((_OWORD *)v6 + 1) = 0;
              v9 = MSCryptAlloc(128, v7);
              *v8 = v9;
              if ( !v9 )
                goto LABEL_15;
              v11 = MSCryptAlloc(128, v10);
              v12 = (void *)*v8;
              v8[3] = v11;
              if ( !v11 )
              {
                MSCryptFree(v12);
LABEL_15:
                MSCryptFree(v8);
                continue;
              }
              wcscpy_s((wchar_t *)v12, 0x40u, pszAlgId);
              wcscpy_s((wchar_t *)v8[3], 0x40u, &pszAlgId[64]);
              v13 = g_dwCipherInfoTotalCount;
              v14 = g_dwCipherInfoTotalCount - 1073741830;
              g_pCipherInfo[g_dwCipherInfoTotalCount] = (__int64)v8;
              *((_DWORD *)v8 + 3) = v14;
              *((_DWORD *)v8 + 4) = v13 + 28665;
              *((_DWORD *)v8 + 2) = *(_DWORD *)pbOutput;
              g_dwCipherInfoTotalCount = v13 + 1;
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
0x18008e740  push    rbp
0x18008e742  push    rbx
0x18008e743  push    rsi
0x18008e744  push    rdi
0x18008e745  push    r14
0x18008e747  lea     rbp, [rsp-310h]
0x18008e74f  sub     rsp, 410h
0x18008e756  mov     rax, cs:__security_cookie
0x18008e75d  xor     rax, rsp
0x18008e760  mov     [rbp+330h+var_30], rax
0x18008e767  xor     esi, esi
0x18008e769  lea     rcx, [rbp+330h+var_B0]; void *
0x18008e770  mov     r14d, 80h
0x18008e776  mov     [rsp+430h+KeyHandle], rsi
0x18008e77b  mov     r8d, r14d; Size
0x18008e77e  mov     [rsp+430h+var_3F0], rsi
0x18008e783  xor     edx, edx; Val
0x18008e785  call    memset
0x18008e78a  mov     dword ptr [rsp+430h+pbOutput], esi
0x18008e78e  mov     [rsp+430h+phAlgorithm], rsi
0x18008e793  mov     [rsp+430h+pcbResult], esi
0x18008e797  call    FreeExternalCipherAlgorithms
0x18008e79c  cmp     cs:g_dwCipherInfoTotalCount, 10h
0x18008e7a3  jnb     loc_18008E9F0
0x18008e7a9  lea     r8, [rsp+430h+KeyHandle]; KeyHandle
0x18008e7ae  xor     edx, edx; PCWSTR
0x18008e7b0  lea     rcx, aRegistryMachin_12; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18008e7b7  call    TlsOpenRegKey
0x18008e7bc  test    eax, eax
0x18008e7be  js      loc_18008E9F0
0x18008e7c4  mov     [rsp+430h+var_3E8], esi
0x18008e7c8  mov     edi, esi
0x18008e7ca  jmp     loc_18008E9D9
0x18008e7cf  xor     edx, edx; Val
0x18008e7d1  mov     [rbp+330h+KeyInformation], esi
0x18008e7d4  mov     r8d, 214h; Size
0x18008e7da  lea     rcx, [rbp+330h+var_2CC]; void *
0x18008e7de  call    memset
0x18008e7e3  mov     rcx, [rsp+430h+KeyHandle]; KeyHandle
0x18008e7e8  lea     rax, [rsp+430h+var_3E8]
0x18008e7ed  mov     [rsp+430h+ResultLength], rax; ResultLength
0x18008e7f2  lea     r9, [rbp+330h+KeyInformation]; KeyInformation
0x18008e7f6  xor     r8d, r8d; KeyInformationClass
0x18008e7f9  mov     [rsp+430h+Length], 218h; Length
0x18008e801  mov     edx, edi; Index
0x18008e803  call    cs:__imp_ZwEnumerateKey
0x18008e80a  nop     dword ptr [rax+rax+00h]
0x18008e80f  test    eax, eax
0x18008e811  js      loc_18008E9E6
0x18008e817  lea     rax, [rbp+330h+var_2C0]
0x18008e81b  or      r9, 0FFFFFFFFFFFFFFFFh
0x18008e81f  inc     r9; unsigned __int64
0x18008e822  cmp     [rax+r9*2], si
0x18008e827  jnz     short loc_18008E81F
0x18008e829  lea     r8, [rbp+330h+var_2C0]; unsigned __int16 *
0x18008e82d  lea     rcx, [rbp+330h+var_B0]; unsigned __int16 *
0x18008e834  call    ?RtlStringCchCopyNW@@YAJPEAG_KPEBG1@Z; RtlStringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18008e839  test    eax, eax
0x18008e83b  js      loc_18008E9D7
0x18008e841  lea     r8, [rsp+430h+var_3F0]; KeyHandle
0x18008e846  lea     rdx, [rbp+330h+var_B0]; PCWSTR
0x18008e84d  lea     rcx, aRegistryMachin_12; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18008e854  call    TlsOpenRegKey
0x18008e859  test    eax, eax
0x18008e85b  js      loc_18008E9D7
0x18008e861  xor     edx, edx; Val
0x18008e863  lea     rcx, [rsp+430h+pszAlgId]; void *
0x18008e868  mov     r8d, 100h; Size
0x18008e86e  call    memset
0x18008e873  mov     rbx, [rsp+430h+var_3F0]
0x18008e878  lea     r8, [rsp+430h+pszAlgId]; unsigned __int16 *
0x18008e87d  mov     rcx, rbx; KeyHandle
0x18008e880  lea     rdx, aCngalgorithm; "CngAlgorithm"
0x18008e887  call    GetSslStringFromRegistry
0x18008e88c  test    eax, eax
0x18008e88e  js      loc_18008E9CD
0x18008e894  lea     r8, [rbp+330h+Src]; unsigned __int16 *
0x18008e898  mov     rcx, rbx; KeyHandle
0x18008e89b  lea     rdx, aCiphermode; "CipherMode"
0x18008e8a2  call    GetSslStringFromRegistry
0x18008e8a7  lea     rcx, [rsp+430h+var_3F0]
0x18008e8ac  call    TlsCloseRegKey
0x18008e8b1  xor     r9d, r9d; dwFlags
0x18008e8b4  lea     rdx, [rsp+430h+pszAlgId]; pszAlgId
0x18008e8b9  xor     r8d, r8d; pszImplementation
0x18008e8bc  lea     rcx, [rsp+430h+phAlgorithm]; phAlgorithm
0x18008e8c1  call    BCryptOpenAlgorithmProvider
0x18008e8c6  test    eax, eax
0x18008e8c8  js      loc_18008E9D7
0x18008e8ce  mov     rcx, [rsp+430h+phAlgorithm]; hObject
0x18008e8d3  lea     rax, [rsp+430h+pcbResult]
0x18008e8d8  mov     dword ptr [rsp+430h+ResultLength], esi; dwFlags
0x18008e8dc  lea     r8, [rsp+430h+pbOutput]; pbOutput
0x18008e8e1  mov     r9d, 4; cbOutput
0x18008e8e7  mov     qword ptr [rsp+430h+Length], rax; pcbResult
0x18008e8ec  lea     rdx, aBlocklength; "BlockLength"
0x18008e8f3  call    BCryptGetProperty
0x18008e8f8  mov     rcx, [rsp+430h+phAlgorithm]; hAlgorithm
0x18008e8fd  xor     edx, edx; dwFlags
0x18008e8ff  test    eax, eax
0x18008e901  jns     short loc_18008E90D
0x18008e903  call    BCryptCloseAlgorithmProvider
0x18008e908  jmp     loc_18008E9D7
0x18008e90d  call    BCryptCloseAlgorithmProvider
0x18008e912  mov     ecx, 20h ; ' '
0x18008e917  call    MSCryptAlloc
0x18008e91c  mov     rbx, rax
0x18008e91f  test    rax, rax
0x18008e922  jz      loc_18008E9D7
0x18008e928  xorps   xmm0, xmm0
0x18008e92b  mov     rcx, r14
0x18008e92e  movups  xmmword ptr [rax], xmm0
0x18008e931  movups  xmmword ptr [rax+10h], xmm0
0x18008e935  call    MSCryptAlloc
0x18008e93a  mov     [rbx], rax
0x18008e93d  test    rax, rax
0x18008e940  jnz     short loc_18008E94F
0x18008e942  mov     rcx, rbx; P
0x18008e945  call    MSCryptFree
0x18008e94a  jmp     loc_18008E9D7
0x18008e94f  mov     rcx, r14
0x18008e952  call    MSCryptAlloc
0x18008e957  mov     rcx, [rbx]; P
0x18008e95a  mov     [rbx+18h], rax
0x18008e95e  test    rax, rax
0x18008e961  jnz     short loc_18008E96A
0x18008e963  call    MSCryptFree
0x18008e968  jmp     short loc_18008E942
0x18008e96a  lea     r8, [rsp+430h+pszAlgId]; Src
0x18008e96f  mov     edx, 40h ; '@'; SizeInWords
0x18008e974  call    cs:__imp_wcscpy_s
0x18008e97b  nop     dword ptr [rax+rax+00h]
0x18008e980  mov     rcx, [rbx+18h]; Dst
0x18008e984  lea     r8, [rbp+330h+Src]; Src
0x18008e988  mov     edx, 40h ; '@'; SizeInWords
0x18008e98d  call    cs:__imp_wcscpy_s
0x18008e994  nop     dword ptr [rax+rax+00h]
0x18008e999  mov     ecx, cs:g_dwCipherInfoTotalCount
0x18008e99f  lea     rdx, g_pCipherInfo
0x18008e9a6  lea     eax, [rcx-40000006h]
0x18008e9ac  mov     [rdx+rcx*8], rbx
0x18008e9b0  mov     [rbx+0Ch], eax
0x18008e9b3  lea     eax, [rcx+6FF9h]
0x18008e9b9  mov     [rbx+10h], eax
0x18008e9bc  inc     ecx
0x18008e9be  mov     eax, dword ptr [rsp+430h+pbOutput]
0x18008e9c2  mov     [rbx+8], eax
0x18008e9c5  mov     cs:g_dwCipherInfoTotalCount, ecx
0x18008e9cb  jmp     short loc_18008E9D7
0x18008e9cd  lea     rcx, [rsp+430h+var_3F0]
0x18008e9d2  call    TlsCloseRegKey
0x18008e9d7  inc     edi
0x18008e9d9  cmp     cs:g_dwCipherInfoTotalCount, 10h
0x18008e9e0  jb      loc_18008E7CF
0x18008e9e6  lea     rcx, [rsp+430h+KeyHandle]
0x18008e9eb  call    TlsCloseRegKey
0x18008e9f0  mov     rcx, [rbp+330h+var_30]
0x18008e9f7  xor     rcx, rsp; StackCookie
0x18008e9fa  call    __security_check_cookie
0x18008e9ff  add     rsp, 410h
0x18008ea06  pop     r14
0x18008ea08  pop     rdi
0x18008ea09  pop     rsi
0x18008ea0a  pop     rbx
0x18008ea0b  pop     rbp
0x18008ea0c  retn
```
