# GetExternalSignatureAlgorithms

- ea: `0x180084174`
- end: `0x180084464`
- name: `GetExternalSignatureAlgorithms`
- size: `752`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180045c90`
- `0x180081428`

## callees

- `0x180003f70`
- `0x180006470`
- `0x180083d48`
- `0x180083dac`
- `0x180083e6c`
- `0x180083f60`
- `0x180083f94`
- `0x1800840f8`
- `0x180084174`
- `0x18009d820`
- `0x18009dd40`

## import_xrefs

- `ntoskrnl!_wcsicmp` at `0x1800843a2`
- `ntoskrnl!_wcsicmp` at `0x1800843c9`
- `ntoskrnl!_wcsicmp` at `0x1800843f0`
- `ntoskrnl!_wcsicmp` at `0x1800843a2`
- `ntoskrnl!_wcsicmp` at `0x1800843c9`
- `ntoskrnl!_wcsicmp` at `0x1800843f0`
- `ntoskrnl!ZwEnumerateKey` at `0x180084253`
- `ntoskrnl!ZwEnumerateKey` at `0x180084253`
- `ntoskrnl!wcscpy_s` at `0x180084369`
- `ntoskrnl!wcscpy_s` at `0x180084369`

## string_xrefs

- `0x1800841fd`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Signature`
- `0x18008429f`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Signature`

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
0x180084174  push    rbp
0x180084176  push    rbx
0x180084177  push    rsi
0x180084178  push    rdi
0x180084179  push    r14
0x18008417b  lea     rbp, [rsp-300h]
0x180084183  sub     rsp, 400h
0x18008418a  mov     rax, cs:__security_cookie
0x180084191  xor     rax, rsp
0x180084194  mov     [rbp+320h+var_30], rax
0x18008419b  xor     esi, esi
0x18008419d  lea     rcx, [rbp+320h+var_130]; void *
0x1800841a4  mov     r14d, 80h
0x1800841aa  mov     [rsp+420h+KeyHandle], rsi
0x1800841af  mov     r8d, r14d; Size
0x1800841b2  mov     [rsp+420h+var_3F0], rsi
0x1800841b7  xor     edx, edx; Val
0x1800841b9  call    memset
0x1800841be  mov     r8d, r14d; Size
0x1800841c1  lea     rcx, [rbp+320h+Src]; void *
0x1800841c8  xor     edx, edx; Val
0x1800841ca  call    memset
0x1800841cf  mov     r8d, r14d; Size
0x1800841d2  lea     rcx, [rbp+320h+Str1]; void *
0x1800841d9  xor     edx, edx; Val
0x1800841db  call    memset
0x1800841e0  mov     [rsp+420h+var_3E8], esi
0x1800841e4  call    FreeExternalSignatureAlgorithms
0x1800841e9  cmp     cs:g_dwSignatureInfoTotalCount, 10h
0x1800841f0  jnb     loc_180084446
0x1800841f6  lea     r8, [rsp+420h+KeyHandle]; KeyHandle
0x1800841fb  xor     edx, edx; PCWSTR
0x1800841fd  lea     rcx, aRegistryMachin_7; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180084204  call    TlsOpenRegKey
0x180084209  test    eax, eax
0x18008420b  js      loc_180084446
0x180084211  mov     edi, esi
0x180084213  jmp     loc_18008442F
0x180084218  xor     edx, edx; Val
0x18008421a  mov     [rsp+420h+KeyInformation], esi
0x18008421e  mov     r8d, 214h; Size
0x180084224  lea     rcx, [rsp+420h+var_3CC]; void *
0x180084229  call    memset
0x18008422e  mov     rcx, [rsp+420h+KeyHandle]; KeyHandle
0x180084233  lea     rax, [rsp+420h+var_3E4]
0x180084238  mov     [rsp+420h+ResultLength], rax; ResultLength
0x18008423d  lea     r9, [rsp+420h+KeyInformation]; KeyInformation
0x180084242  xor     r8d, r8d; KeyInformationClass
0x180084245  mov     [rsp+420h+Length], 218h; Length
0x18008424d  mov     edx, edi; Index
0x18008424f  mov     [rsp+420h+var_3E4], esi
0x180084253  call    cs:__imp_ZwEnumerateKey
0x18008425a  nop     dword ptr [rax+rax+00h]
0x18008425f  test    eax, eax
0x180084261  js      loc_18008443C
0x180084267  lea     rax, [rsp+420h+var_3C0]
0x18008426c  or      r9, 0FFFFFFFFFFFFFFFFh
0x180084270  inc     r9; unsigned __int64
0x180084273  cmp     [rax+r9*2], si
0x180084278  jnz     short loc_180084270
0x18008427a  lea     r8, [rsp+420h+var_3C0]; unsigned __int16 *
0x18008427f  lea     rcx, [rbp+320h+var_130]; unsigned __int16 *
0x180084286  call    ?RtlStringCchCopyNW@@YAJPEAG_KPEBG1@Z; RtlStringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18008428b  test    eax, eax
0x18008428d  js      loc_18008443C
0x180084293  lea     r8, [rsp+420h+var_3F0]; KeyHandle
0x180084298  lea     rdx, [rbp+320h+var_130]; PCWSTR
0x18008429f  lea     rcx, aRegistryMachin_7; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x1800842a6  call    TlsOpenRegKey
0x1800842ab  test    eax, eax
0x1800842ad  js      loc_18008442D
0x1800842b3  mov     rcx, [rsp+420h+var_3F0]; KeyHandle
0x1800842b8  lea     r8, [rbp+320h+Src]; unsigned __int16 *
0x1800842bf  lea     rdx, aCngalgorithm; "CngAlgorithm"
0x1800842c6  call    GetSslStringFromRegistry
0x1800842cb  test    eax, eax
0x1800842cd  js      loc_180084423
0x1800842d3  mov     rcx, [rsp+420h+var_3F0]; KeyHandle
0x1800842d8  lea     r8, [rsp+420h+var_3E8]
0x1800842dd  lea     rdx, aTlscodepoint; "TlsCodePoint"
0x1800842e4  call    GetSslDWordFromRegistry
0x1800842e9  test    eax, eax
0x1800842eb  js      loc_180084423
0x1800842f1  mov     rcx, [rsp+420h+var_3F0]; KeyHandle
0x1800842f6  lea     r8, [rbp+320h+Str1]; unsigned __int16 *
0x1800842fd  lea     rdx, aSignaturestyle; "SignatureStyle"
0x180084304  call    GetSslStringFromRegistry
0x180084309  test    eax, eax
0x18008430b  js      loc_180084423
0x180084311  lea     rcx, [rsp+420h+var_3F0]
0x180084316  call    TlsCloseRegKey
0x18008431b  mov     ecx, 18h
0x180084320  call    MSCryptAlloc
0x180084325  mov     rbx, rax
0x180084328  test    rax, rax
0x18008432b  jz      loc_18008442D
0x180084331  xorps   xmm0, xmm0
0x180084334  xor     eax, eax
0x180084336  movups  xmmword ptr [rbx], xmm0
0x180084339  mov     rcx, r14
0x18008433c  mov     [rbx+10h], rax
0x180084340  call    MSCryptAlloc
0x180084345  mov     [rbx], rax
0x180084348  test    rax, rax
0x18008434b  jnz     short loc_18008435A
0x18008434d  mov     rcx, rbx; P
0x180084350  call    MSCryptFree
0x180084355  jmp     loc_18008442D
0x18008435a  lea     r8, [rbp+320h+Src]; Src
0x180084361  mov     edx, 40h ; '@'; SizeInWords
0x180084366  mov     rcx, rax; Dst
0x180084369  call    cs:__imp_wcscpy_s
0x180084370  nop     dword ptr [rax+rax+00h]
0x180084375  mov     ecx, cs:g_dwSignatureInfoTotalCount
0x18008437b  lea     rdx, aRsa; "RSA"
0x180084382  lea     eax, [rcx+2FF9h]
0x180084388  mov     [rbx+0Ch], eax
0x18008438b  lea     eax, [rcx-20000006h]
0x180084391  mov     [rbx+8], eax
0x180084394  lea     rcx, [rbp+320h+Str1]; Str1
0x18008439b  mov     eax, [rsp+420h+var_3E8]
0x18008439f  mov     [rbx+10h], eax
0x1800843a2  call    cs:__imp__wcsicmp
0x1800843a9  nop     dword ptr [rax+rax+00h]
0x1800843ae  test    eax, eax
0x1800843b0  jnz     short loc_1800843BB
0x1800843b2  mov     dword ptr [rbx+14h], 2
0x1800843b9  jmp     short loc_180084408
0x1800843bb  lea     rdx, aDsa; "DSA"
0x1800843c2  lea     rcx, [rbp+320h+Str1]; Str1
0x1800843c9  call    cs:__imp__wcsicmp
0x1800843d0  nop     dword ptr [rax+rax+00h]
0x1800843d5  test    eax, eax
0x1800843d7  jnz     short loc_1800843E2
0x1800843d9  mov     dword ptr [rbx+14h], 3
0x1800843e0  jmp     short loc_180084408
0x1800843e2  lea     rdx, aEcdsa; "ECDSA"
0x1800843e9  lea     rcx, [rbp+320h+Str1]; Str1
0x1800843f0  call    cs:__imp__wcsicmp
0x1800843f7  nop     dword ptr [rax+rax+00h]
0x1800843fc  neg     eax
0x1800843fe  sbb     ecx, ecx
0x180084400  not     ecx
0x180084402  and     ecx, 4
0x180084405  mov     [rbx+14h], ecx
0x180084408  mov     ecx, cs:g_dwSignatureInfoTotalCount
0x18008440e  lea     rdx, g_pSignatureInfo
0x180084415  mov     [rdx+rcx*8], rbx
0x180084419  inc     ecx
0x18008441b  mov     cs:g_dwSignatureInfoTotalCount, ecx
0x180084421  jmp     short loc_18008442D
0x180084423  lea     rcx, [rsp+420h+var_3F0]
0x180084428  call    TlsCloseRegKey
0x18008442d  inc     edi
0x18008442f  cmp     cs:g_dwSignatureInfoTotalCount, 10h
0x180084436  jb      loc_180084218
0x18008443c  lea     rcx, [rsp+420h+KeyHandle]
0x180084441  call    TlsCloseRegKey
0x180084446  mov     rcx, [rbp+320h+var_30]
0x18008444d  xor     rcx, rsp; StackCookie
0x180084450  call    __security_check_cookie
0x180084455  add     rsp, 400h
0x18008445c  pop     r14
0x18008445e  pop     rdi
0x18008445f  pop     rsi
0x180084460  pop     rbx
0x180084461  pop     rbp
0x180084462  retn
```
