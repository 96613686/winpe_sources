# GetExternalCipherAlgorithms

- ea: `0x180084550`
- end: `0x18008481e`
- name: `GetExternalCipherAlgorithms`
- size: `718`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
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
- `0x180083e6c`
- `0x180083f60`
- `0x180083f94`
- `0x1800844d4`
- `0x180084550`
- `0x18009d820`
- `0x18009dd40`

## import_xrefs

- `ntoskrnl!ZwEnumerateKey` at `0x180084613`
- `ntoskrnl!ZwEnumerateKey` at `0x180084613`
- `ntoskrnl!wcscpy_s` at `0x180084784`
- `ntoskrnl!wcscpy_s` at `0x18008479d`
- `ntoskrnl!wcscpy_s` at `0x180084784`
- `ntoskrnl!wcscpy_s` at `0x18008479d`

## string_xrefs

- `0x1800845c0`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Cipher`
- `0x18008465d`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Cipher`

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
0x180084550  push    rbp
0x180084552  push    rbx
0x180084553  push    rsi
0x180084554  push    rdi
0x180084555  push    r14
0x180084557  lea     rbp, [rsp-310h]
0x18008455f  sub     rsp, 410h
0x180084566  mov     rax, cs:__security_cookie
0x18008456d  xor     rax, rsp
0x180084570  mov     [rbp+330h+var_30], rax
0x180084577  xor     esi, esi
0x180084579  lea     rcx, [rbp+330h+var_B0]; void *
0x180084580  mov     r14d, 80h
0x180084586  mov     [rsp+430h+KeyHandle], rsi
0x18008458b  mov     r8d, r14d; Size
0x18008458e  mov     [rsp+430h+var_3F0], rsi
0x180084593  xor     edx, edx; Val
0x180084595  call    memset
0x18008459a  mov     dword ptr [rsp+430h+pbOutput], esi
0x18008459e  mov     [rsp+430h+phAlgorithm], rsi
0x1800845a3  mov     [rsp+430h+pcbResult], esi
0x1800845a7  call    FreeExternalCipherAlgorithms
0x1800845ac  cmp     cs:g_dwCipherInfoTotalCount, 10h
0x1800845b3  jnb     loc_180084800
0x1800845b9  lea     r8, [rsp+430h+KeyHandle]; KeyHandle
0x1800845be  xor     edx, edx; PCWSTR
0x1800845c0  lea     rcx, aRegistryMachin_12; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x1800845c7  call    TlsOpenRegKey
0x1800845cc  test    eax, eax
0x1800845ce  js      loc_180084800
0x1800845d4  mov     [rsp+430h+var_3E8], esi
0x1800845d8  mov     edi, esi
0x1800845da  jmp     loc_1800847E9
0x1800845df  xor     edx, edx; Val
0x1800845e1  mov     [rbp+330h+KeyInformation], esi
0x1800845e4  mov     r8d, 214h; Size
0x1800845ea  lea     rcx, [rbp+330h+var_2CC]; void *
0x1800845ee  call    memset
0x1800845f3  mov     rcx, [rsp+430h+KeyHandle]; KeyHandle
0x1800845f8  lea     rax, [rsp+430h+var_3E8]
0x1800845fd  mov     [rsp+430h+ResultLength], rax; ResultLength
0x180084602  lea     r9, [rbp+330h+KeyInformation]; KeyInformation
0x180084606  xor     r8d, r8d; KeyInformationClass
0x180084609  mov     [rsp+430h+Length], 218h; Length
0x180084611  mov     edx, edi; Index
0x180084613  call    cs:__imp_ZwEnumerateKey
0x18008461a  nop     dword ptr [rax+rax+00h]
0x18008461f  test    eax, eax
0x180084621  js      loc_1800847F6
0x180084627  lea     rax, [rbp+330h+var_2C0]
0x18008462b  or      r9, 0FFFFFFFFFFFFFFFFh
0x18008462f  inc     r9; unsigned __int64
0x180084632  cmp     [rax+r9*2], si
0x180084637  jnz     short loc_18008462F
0x180084639  lea     r8, [rbp+330h+var_2C0]; unsigned __int16 *
0x18008463d  lea     rcx, [rbp+330h+var_B0]; unsigned __int16 *
0x180084644  call    ?RtlStringCchCopyNW@@YAJPEAG_KPEBG1@Z; RtlStringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180084649  test    eax, eax
0x18008464b  js      loc_1800847E7
0x180084651  lea     r8, [rsp+430h+var_3F0]; KeyHandle
0x180084656  lea     rdx, [rbp+330h+var_B0]; PCWSTR
0x18008465d  lea     rcx, aRegistryMachin_12; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180084664  call    TlsOpenRegKey
0x180084669  test    eax, eax
0x18008466b  js      loc_1800847E7
0x180084671  xor     edx, edx; Val
0x180084673  lea     rcx, [rsp+430h+pszAlgId]; void *
0x180084678  mov     r8d, 100h; Size
0x18008467e  call    memset
0x180084683  mov     rbx, [rsp+430h+var_3F0]
0x180084688  lea     r8, [rsp+430h+pszAlgId]; unsigned __int16 *
0x18008468d  mov     rcx, rbx; KeyHandle
0x180084690  lea     rdx, aCngalgorithm; "CngAlgorithm"
0x180084697  call    GetSslStringFromRegistry
0x18008469c  test    eax, eax
0x18008469e  js      loc_1800847DD
0x1800846a4  lea     r8, [rbp+330h+Src]; unsigned __int16 *
0x1800846a8  mov     rcx, rbx; KeyHandle
0x1800846ab  lea     rdx, aCiphermode; "CipherMode"
0x1800846b2  call    GetSslStringFromRegistry
0x1800846b7  lea     rcx, [rsp+430h+var_3F0]
0x1800846bc  call    TlsCloseRegKey
0x1800846c1  xor     r9d, r9d; dwFlags
0x1800846c4  lea     rdx, [rsp+430h+pszAlgId]; pszAlgId
0x1800846c9  xor     r8d, r8d; pszImplementation
0x1800846cc  lea     rcx, [rsp+430h+phAlgorithm]; phAlgorithm
0x1800846d1  call    BCryptOpenAlgorithmProvider
0x1800846d6  test    eax, eax
0x1800846d8  js      loc_1800847E7
0x1800846de  mov     rcx, [rsp+430h+phAlgorithm]; hObject
0x1800846e3  lea     rax, [rsp+430h+pcbResult]
0x1800846e8  mov     dword ptr [rsp+430h+ResultLength], esi; dwFlags
0x1800846ec  lea     r8, [rsp+430h+pbOutput]; pbOutput
0x1800846f1  mov     r9d, 4; cbOutput
0x1800846f7  mov     qword ptr [rsp+430h+Length], rax; pcbResult
0x1800846fc  lea     rdx, aBlocklength; "BlockLength"
0x180084703  call    BCryptGetProperty
0x180084708  mov     rcx, [rsp+430h+phAlgorithm]; hAlgorithm
0x18008470d  xor     edx, edx; dwFlags
0x18008470f  test    eax, eax
0x180084711  jns     short loc_18008471D
0x180084713  call    BCryptCloseAlgorithmProvider
0x180084718  jmp     loc_1800847E7
0x18008471d  call    BCryptCloseAlgorithmProvider
0x180084722  mov     ecx, 20h ; ' '
0x180084727  call    MSCryptAlloc
0x18008472c  mov     rbx, rax
0x18008472f  test    rax, rax
0x180084732  jz      loc_1800847E7
0x180084738  xorps   xmm0, xmm0
0x18008473b  mov     rcx, r14
0x18008473e  movups  xmmword ptr [rax], xmm0
0x180084741  movups  xmmword ptr [rax+10h], xmm0
0x180084745  call    MSCryptAlloc
0x18008474a  mov     [rbx], rax
0x18008474d  test    rax, rax
0x180084750  jnz     short loc_18008475F
0x180084752  mov     rcx, rbx; P
0x180084755  call    MSCryptFree
0x18008475a  jmp     loc_1800847E7
0x18008475f  mov     rcx, r14
0x180084762  call    MSCryptAlloc
0x180084767  mov     rcx, [rbx]; P
0x18008476a  mov     [rbx+18h], rax
0x18008476e  test    rax, rax
0x180084771  jnz     short loc_18008477A
0x180084773  call    MSCryptFree
0x180084778  jmp     short loc_180084752
0x18008477a  lea     r8, [rsp+430h+pszAlgId]; Src
0x18008477f  mov     edx, 40h ; '@'; SizeInWords
0x180084784  call    cs:__imp_wcscpy_s
0x18008478b  nop     dword ptr [rax+rax+00h]
0x180084790  mov     rcx, [rbx+18h]; Dst
0x180084794  lea     r8, [rbp+330h+Src]; Src
0x180084798  mov     edx, 40h ; '@'; SizeInWords
0x18008479d  call    cs:__imp_wcscpy_s
0x1800847a4  nop     dword ptr [rax+rax+00h]
0x1800847a9  mov     ecx, cs:g_dwCipherInfoTotalCount
0x1800847af  lea     rdx, g_pCipherInfo
0x1800847b6  lea     eax, [rcx-40000006h]
0x1800847bc  mov     [rdx+rcx*8], rbx
0x1800847c0  mov     [rbx+0Ch], eax
0x1800847c3  lea     eax, [rcx+6FF9h]
0x1800847c9  mov     [rbx+10h], eax
0x1800847cc  inc     ecx
0x1800847ce  mov     eax, dword ptr [rsp+430h+pbOutput]
0x1800847d2  mov     [rbx+8], eax
0x1800847d5  mov     cs:g_dwCipherInfoTotalCount, ecx
0x1800847db  jmp     short loc_1800847E7
0x1800847dd  lea     rcx, [rsp+430h+var_3F0]
0x1800847e2  call    TlsCloseRegKey
0x1800847e7  inc     edi
0x1800847e9  cmp     cs:g_dwCipherInfoTotalCount, 10h
0x1800847f0  jb      loc_1800845DF
0x1800847f6  lea     rcx, [rsp+430h+KeyHandle]
0x1800847fb  call    TlsCloseRegKey
0x180084800  mov     rcx, [rbp+330h+var_30]
0x180084807  xor     rcx, rsp; StackCookie
0x18008480a  call    __security_check_cookie
0x18008480f  add     rsp, 410h
0x180084816  pop     r14
0x180084818  pop     rdi
0x180084819  pop     rsi
0x18008481a  pop     rbx
0x18008481b  pop     rbp
0x18008481c  retn
```
