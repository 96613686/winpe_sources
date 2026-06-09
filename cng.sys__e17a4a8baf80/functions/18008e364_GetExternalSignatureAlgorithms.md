# GetExternalSignatureAlgorithms

- ea: `0x18008e364`
- end: `0x18008e654`
- name: `GetExternalSignatureAlgorithms`
- size: `752`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004fd80`
- `0x18008b618`

## callees

- `0x18000e090`
- `0x180010590`
- `0x18008df38`
- `0x18008df9c`
- `0x18008e05c`
- `0x18008e150`
- `0x18008e184`
- `0x18008e2e8`
- `0x18008e364`
- `0x1800a4260`
- `0x1800a4380`

## import_xrefs

- `ntoskrnl!_wcsicmp` at `0x18008e592`
- `ntoskrnl!_wcsicmp` at `0x18008e5b9`
- `ntoskrnl!_wcsicmp` at `0x18008e5e0`
- `ntoskrnl!_wcsicmp` at `0x18008e592`
- `ntoskrnl!_wcsicmp` at `0x18008e5b9`
- `ntoskrnl!_wcsicmp` at `0x18008e5e0`
- `ntoskrnl!ZwEnumerateKey` at `0x18008e443`
- `ntoskrnl!ZwEnumerateKey` at `0x18008e443`
- `ntoskrnl!wcscpy_s` at `0x18008e559`
- `ntoskrnl!wcscpy_s` at `0x18008e559`

## string_xrefs

- `0x18008e3ed`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Signature`
- `0x18008e48f`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Signature`

## pseudocode

```c
__int64 GetExternalSignatureAlgorithms()
{
  __int64 result; // rax
  ULONG i; // edi
  unsigned __int64 v2; // rdx
  unsigned __int64 v3; // r9
  __int64 v4; // rdx
  __int64 v5; // rdx
  wchar_t **v6; // rbx
  wchar_t *v7; // rax
  int v8; // ecx
  int v9; // ecx
  HANDLE v10; // [rsp+30h] [rbp-D0h] BYREF
  int v11; // [rsp+38h] [rbp-C8h]
  ULONG ResultLength; // [rsp+3Ch] [rbp-C4h] BYREF
  HANDLE KeyHandle[2]; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD KeyInformation[136]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Str1[64]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR v16[64]; // [rsp+2F0h] [rbp+1F0h] BYREF
  wchar_t Src[64]; // [rsp+370h] [rbp+270h] BYREF

  KeyHandle[0] = 0;
  v10 = 0;
  memset(v16, 0, sizeof(v16));
  memset(Src, 0, sizeof(Src));
  memset(Str1, 0, sizeof(Str1));
  v11 = 0;
  result = FreeExternalSignatureAlgorithms();
  if ( (unsigned int)g_dwSignatureInfoTotalCount < 0x10 )
  {
    result = TlsOpenRegKey(
               L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Protocol "
                "Provider\\Signature",
               0,
               KeyHandle);
    if ( (int)result >= 0 )
    {
      for ( i = 0; (unsigned int)g_dwSignatureInfoTotalCount < 0x10; ++i )
      {
        memset(KeyInformation, 0, 536);
        ResultLength = 0;
        if ( ZwEnumerateKey(KeyHandle[0], i, KeyBasicInformation, KeyInformation, 0x218u, &ResultLength) < 0 )
          break;
        v3 = -1;
        do
          ++v3;
        while ( *((_WORD *)&KeyInformation[4] + v3) );
        if ( (int)RtlStringCchCopyNW(v16, v2, (const unsigned __int16 *)&KeyInformation[4], v3) < 0 )
          break;
        if ( (int)TlsOpenRegKey(
                    L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Prot"
                     "ocol Provider\\Signature",
                    v16,
                    &v10) >= 0 )
        {
          if ( (int)GetSslStringFromRegistry(v10, L"CngAlgorithm", Src) < 0
            || (int)GetSslDWordFromRegistry(v10) < 0
            || (int)GetSslStringFromRegistry(v10, L"SignatureStyle", Str1) < 0 )
          {
            TlsCloseRegKey(&v10);
          }
          else
          {
            TlsCloseRegKey(&v10);
            v6 = (wchar_t **)MSCryptAlloc(24, v4);
            if ( v6 )
            {
              *(_OWORD *)v6 = 0;
              v6[2] = 0;
              v7 = (wchar_t *)MSCryptAlloc(128, v5);
              *v6 = v7;
              if ( v7 )
              {
                wcscpy_s(v7, 0x40u, Src);
                v8 = g_dwSignatureInfoTotalCount;
                *((_DWORD *)v6 + 3) = g_dwSignatureInfoTotalCount + 12281;
                *((_DWORD *)v6 + 2) = v8 - 536870918;
                *((_DWORD *)v6 + 4) = v11;
                if ( _wcsicmp(Str1, L"RSA") )
                {
                  if ( _wcsicmp(Str1, L"DSA") )
                    *((_DWORD *)v6 + 5) = _wcsicmp(Str1, L"ECDSA") == 0 ? 4 : 0;
                  else
                    *((_DWORD *)v6 + 5) = 3;
                }
                else
                {
                  *((_DWORD *)v6 + 5) = 2;
                }
                v9 = g_dwSignatureInfoTotalCount;
                g_pSignatureInfo[g_dwSignatureInfoTotalCount] = (__int64)v6;
                g_dwSignatureInfoTotalCount = v9 + 1;
              }
              else
              {
                MSCryptFree(v6);
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
0x18008e364  push    rbp
0x18008e366  push    rbx
0x18008e367  push    rsi
0x18008e368  push    rdi
0x18008e369  push    r14
0x18008e36b  lea     rbp, [rsp-300h]
0x18008e373  sub     rsp, 400h
0x18008e37a  mov     rax, cs:__security_cookie
0x18008e381  xor     rax, rsp
0x18008e384  mov     [rbp+320h+var_30], rax
0x18008e38b  xor     esi, esi
0x18008e38d  lea     rcx, [rbp+320h+var_130]; void *
0x18008e394  mov     r14d, 80h
0x18008e39a  mov     [rsp+420h+KeyHandle], rsi
0x18008e39f  mov     r8d, r14d; Size
0x18008e3a2  mov     [rsp+420h+var_3F0], rsi
0x18008e3a7  xor     edx, edx; Val
0x18008e3a9  call    memset
0x18008e3ae  mov     r8d, r14d; Size
0x18008e3b1  lea     rcx, [rbp+320h+Src]; void *
0x18008e3b8  xor     edx, edx; Val
0x18008e3ba  call    memset
0x18008e3bf  mov     r8d, r14d; Size
0x18008e3c2  lea     rcx, [rbp+320h+Str1]; void *
0x18008e3c9  xor     edx, edx; Val
0x18008e3cb  call    memset
0x18008e3d0  mov     [rsp+420h+var_3E8], esi
0x18008e3d4  call    FreeExternalSignatureAlgorithms
0x18008e3d9  cmp     cs:g_dwSignatureInfoTotalCount, 10h
0x18008e3e0  jnb     loc_18008E636
0x18008e3e6  lea     r8, [rsp+420h+KeyHandle]; KeyHandle
0x18008e3eb  xor     edx, edx; PCWSTR
0x18008e3ed  lea     rcx, aRegistryMachin_7; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18008e3f4  call    TlsOpenRegKey
0x18008e3f9  test    eax, eax
0x18008e3fb  js      loc_18008E636
0x18008e401  mov     edi, esi
0x18008e403  jmp     loc_18008E61F
0x18008e408  xor     edx, edx; Val
0x18008e40a  mov     [rsp+420h+KeyInformation], esi
0x18008e40e  mov     r8d, 214h; Size
0x18008e414  lea     rcx, [rsp+420h+var_3CC]; void *
0x18008e419  call    memset
0x18008e41e  mov     rcx, [rsp+420h+KeyHandle]; KeyHandle
0x18008e423  lea     rax, [rsp+420h+var_3E4]
0x18008e428  mov     [rsp+420h+ResultLength], rax; ResultLength
0x18008e42d  lea     r9, [rsp+420h+KeyInformation]; KeyInformation
0x18008e432  xor     r8d, r8d; KeyInformationClass
0x18008e435  mov     [rsp+420h+Length], 218h; Length
0x18008e43d  mov     edx, edi; Index
0x18008e43f  mov     [rsp+420h+var_3E4], esi
0x18008e443  call    cs:__imp_ZwEnumerateKey
0x18008e44a  nop     dword ptr [rax+rax+00h]
0x18008e44f  test    eax, eax
0x18008e451  js      loc_18008E62C
0x18008e457  lea     rax, [rsp+420h+var_3C0]
0x18008e45c  or      r9, 0FFFFFFFFFFFFFFFFh
0x18008e460  inc     r9; unsigned __int64
0x18008e463  cmp     [rax+r9*2], si
0x18008e468  jnz     short loc_18008E460
0x18008e46a  lea     r8, [rsp+420h+var_3C0]; unsigned __int16 *
0x18008e46f  lea     rcx, [rbp+320h+var_130]; unsigned __int16 *
0x18008e476  call    ?RtlStringCchCopyNW@@YAJPEAG_KPEBG1@Z; RtlStringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18008e47b  test    eax, eax
0x18008e47d  js      loc_18008E62C
0x18008e483  lea     r8, [rsp+420h+var_3F0]; KeyHandle
0x18008e488  lea     rdx, [rbp+320h+var_130]; PCWSTR
0x18008e48f  lea     rcx, aRegistryMachin_7; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18008e496  call    TlsOpenRegKey
0x18008e49b  test    eax, eax
0x18008e49d  js      loc_18008E61D
0x18008e4a3  mov     rcx, [rsp+420h+var_3F0]; KeyHandle
0x18008e4a8  lea     r8, [rbp+320h+Src]; unsigned __int16 *
0x18008e4af  lea     rdx, aCngalgorithm; "CngAlgorithm"
0x18008e4b6  call    GetSslStringFromRegistry
0x18008e4bb  test    eax, eax
0x18008e4bd  js      loc_18008E613
0x18008e4c3  mov     rcx, [rsp+420h+var_3F0]; KeyHandle
0x18008e4c8  lea     r8, [rsp+420h+var_3E8]
0x18008e4cd  lea     rdx, aTlscodepoint; "TlsCodePoint"
0x18008e4d4  call    GetSslDWordFromRegistry
0x18008e4d9  test    eax, eax
0x18008e4db  js      loc_18008E613
0x18008e4e1  mov     rcx, [rsp+420h+var_3F0]; KeyHandle
0x18008e4e6  lea     r8, [rbp+320h+Str1]; unsigned __int16 *
0x18008e4ed  lea     rdx, aSignaturestyle; "SignatureStyle"
0x18008e4f4  call    GetSslStringFromRegistry
0x18008e4f9  test    eax, eax
0x18008e4fb  js      loc_18008E613
0x18008e501  lea     rcx, [rsp+420h+var_3F0]
0x18008e506  call    TlsCloseRegKey
0x18008e50b  mov     ecx, 18h
0x18008e510  call    MSCryptAlloc
0x18008e515  mov     rbx, rax
0x18008e518  test    rax, rax
0x18008e51b  jz      loc_18008E61D
0x18008e521  xorps   xmm0, xmm0
0x18008e524  xor     eax, eax
0x18008e526  movups  xmmword ptr [rbx], xmm0
0x18008e529  mov     rcx, r14
0x18008e52c  mov     [rbx+10h], rax
0x18008e530  call    MSCryptAlloc
0x18008e535  mov     [rbx], rax
0x18008e538  test    rax, rax
0x18008e53b  jnz     short loc_18008E54A
0x18008e53d  mov     rcx, rbx; P
0x18008e540  call    MSCryptFree
0x18008e545  jmp     loc_18008E61D
0x18008e54a  lea     r8, [rbp+320h+Src]; Src
0x18008e551  mov     edx, 40h ; '@'; SizeInWords
0x18008e556  mov     rcx, rax; Dst
0x18008e559  call    cs:__imp_wcscpy_s
0x18008e560  nop     dword ptr [rax+rax+00h]
0x18008e565  mov     ecx, cs:g_dwSignatureInfoTotalCount
0x18008e56b  lea     rdx, aRsa; "RSA"
0x18008e572  lea     eax, [rcx+2FF9h]
0x18008e578  mov     [rbx+0Ch], eax
0x18008e57b  lea     eax, [rcx-20000006h]
0x18008e581  mov     [rbx+8], eax
0x18008e584  lea     rcx, [rbp+320h+Str1]; Str1
0x18008e58b  mov     eax, [rsp+420h+var_3E8]
0x18008e58f  mov     [rbx+10h], eax
0x18008e592  call    cs:__imp__wcsicmp
0x18008e599  nop     dword ptr [rax+rax+00h]
0x18008e59e  test    eax, eax
0x18008e5a0  jnz     short loc_18008E5AB
0x18008e5a2  mov     dword ptr [rbx+14h], 2
0x18008e5a9  jmp     short loc_18008E5F8
0x18008e5ab  lea     rdx, aDsa; "DSA"
0x18008e5b2  lea     rcx, [rbp+320h+Str1]; Str1
0x18008e5b9  call    cs:__imp__wcsicmp
0x18008e5c0  nop     dword ptr [rax+rax+00h]
0x18008e5c5  test    eax, eax
0x18008e5c7  jnz     short loc_18008E5D2
0x18008e5c9  mov     dword ptr [rbx+14h], 3
0x18008e5d0  jmp     short loc_18008E5F8
0x18008e5d2  lea     rdx, aEcdsa; "ECDSA"
0x18008e5d9  lea     rcx, [rbp+320h+Str1]; Str1
0x18008e5e0  call    cs:__imp__wcsicmp
0x18008e5e7  nop     dword ptr [rax+rax+00h]
0x18008e5ec  neg     eax
0x18008e5ee  sbb     ecx, ecx
0x18008e5f0  not     ecx
0x18008e5f2  and     ecx, 4
0x18008e5f5  mov     [rbx+14h], ecx
0x18008e5f8  mov     ecx, cs:g_dwSignatureInfoTotalCount
0x18008e5fe  lea     rdx, g_pSignatureInfo
0x18008e605  mov     [rdx+rcx*8], rbx
0x18008e609  inc     ecx
0x18008e60b  mov     cs:g_dwSignatureInfoTotalCount, ecx
0x18008e611  jmp     short loc_18008E61D
0x18008e613  lea     rcx, [rsp+420h+var_3F0]
0x18008e618  call    TlsCloseRegKey
0x18008e61d  inc     edi
0x18008e61f  cmp     cs:g_dwSignatureInfoTotalCount, 10h
0x18008e626  jb      loc_18008E408
0x18008e62c  lea     rcx, [rsp+420h+KeyHandle]
0x18008e631  call    TlsCloseRegKey
0x18008e636  mov     rcx, [rbp+320h+var_30]
0x18008e63d  xor     rcx, rsp; StackCookie
0x18008e640  call    __security_check_cookie
0x18008e645  add     rsp, 400h
0x18008e64c  pop     r14
0x18008e64e  pop     rdi
0x18008e64f  pop     rsi
0x18008e650  pop     rbx
0x18008e651  pop     rbp
0x18008e652  retn
```
