# GetExternalKeyExchangeAlgorithms

- ea: `0x180084e1c`
- end: `0x18008510a`
- name: `GetExternalKeyExchangeAlgorithms`
- size: `750`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180045c90`
- `0x180081428`

## callees

- `0x180003f70`
- `0x180006470`
- `0x180083d48`
- `0x180083e6c`
- `0x180083f60`
- `0x180083f94`
- `0x180084da0`
- `0x180084e1c`
- `0x18009d820`
- `0x18009dd40`

## import_xrefs

- `ntoskrnl!_wcsicmp` at `0x180085021`
- `ntoskrnl!_wcsicmp` at `0x180085048`
- `ntoskrnl!_wcsicmp` at `0x18008506f`
- `ntoskrnl!_wcsicmp` at `0x180085096`
- `ntoskrnl!_wcsicmp` at `0x180085021`
- `ntoskrnl!_wcsicmp` at `0x180085048`
- `ntoskrnl!_wcsicmp` at `0x18008506f`
- `ntoskrnl!_wcsicmp` at `0x180085096`
- `ntoskrnl!ZwEnumerateKey` at `0x180084ef7`
- `ntoskrnl!ZwEnumerateKey` at `0x180084ef7`
- `ntoskrnl!wcscpy_s` at `0x180084fef`
- `ntoskrnl!wcscpy_s` at `0x180084fef`

## string_xrefs

- `0x180084ea1`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\KeyExchange`
- `0x180084f43`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\KeyExchange`

## pseudocode

```c
__int64 GetExternalKeyExchangeAlgorithms()
{
  __int64 result; // rax
  ULONG i; // edi
  unsigned __int64 v2; // rdx
  unsigned __int64 v3; // r9
  wchar_t **v4; // rbx
  wchar_t *v5; // rax
  int v6; // ecx
  int v7; // ecx
  HANDLE v8; // [rsp+30h] [rbp-D0h] BYREF
  ULONG ResultLength; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE KeyHandle[2]; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD KeyInformation[136]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Str1[64]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR v13[64]; // [rsp+2F0h] [rbp+1F0h] BYREF
  wchar_t Src[64]; // [rsp+370h] [rbp+270h] BYREF

  KeyHandle[0] = 0;
  v8 = 0;
  memset(v13, 0, sizeof(v13));
  memset(Src, 0, sizeof(Src));
  memset(Str1, 0, sizeof(Str1));
  result = FreeExternalKeyExchangeAlgorithms();
  if ( (unsigned int)g_dwKeyExchangeInfoTotalCount < 0xC )
  {
    result = TlsOpenRegKey(
               L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Protocol "
                "Provider\\KeyExchange",
               0,
               KeyHandle);
    if ( (int)result >= 0 )
    {
      for ( i = 0; (unsigned int)g_dwKeyExchangeInfoTotalCount < 0xC; ++i )
      {
        memset(KeyInformation, 0, 536);
        ResultLength = 0;
        if ( ZwEnumerateKey(KeyHandle[0], i, KeyBasicInformation, KeyInformation, 0x218u, &ResultLength) < 0 )
          break;
        v3 = -1;
        do
          ++v3;
        while ( *((_WORD *)&KeyInformation[4] + v3) );
        if ( (int)RtlStringCchCopyNW(v13, v2, (const unsigned __int16 *)&KeyInformation[4], v3) < 0 )
          break;
        if ( (int)TlsOpenRegKey(
                    L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Prot"
                     "ocol Provider\\KeyExchange",
                    v13,
                    &v8) >= 0 )
        {
          if ( (int)GetSslStringFromRegistry(v8, L"CngAlgorithm", Src) < 0
            || (int)GetSslStringFromRegistry(v8, L"MessageFlow", Str1) < 0 )
          {
            TlsCloseRegKey(&v8);
          }
          else
          {
            TlsCloseRegKey(&v8);
            v4 = (wchar_t **)MSCryptAlloc(24);
            if ( v4 )
            {
              *(_OWORD *)v4 = 0;
              v4[2] = 0;
              v5 = (wchar_t *)MSCryptAlloc(128);
              *v4 = v5;
              if ( v5 )
              {
                wcscpy_s(v5, 0x40u, Src);
                v6 = g_dwKeyExchangeInfoTotalCount;
                *((_DWORD *)v4 + 3) = g_dwKeyExchangeInfoTotalCount + 45049;
                *((_DWORD *)v4 + 2) = v6 - 805306374;
                if ( _wcsicmp(Str1, L"RSA") )
                {
                  if ( _wcsicmp(Str1, L"DH") )
                  {
                    if ( _wcsicmp(Str1, L"ECDH") )
                      *((_DWORD *)v4 + 4) = _wcsicmp(Str1, L"PSK") == 0 ? 4 : 0;
                    else
                      *((_DWORD *)v4 + 4) = 3;
                  }
                  else
                  {
                    *((_DWORD *)v4 + 4) = 2;
                  }
                }
                else
                {
                  *((_DWORD *)v4 + 4) = 1;
                }
                v7 = g_dwKeyExchangeInfoTotalCount;
                g_pKeyExchangeInfo[g_dwKeyExchangeInfoTotalCount] = (__int64)v4;
                g_dwKeyExchangeInfoTotalCount = v7 + 1;
              }
              else
              {
                MSCryptFree(v4);
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
0x180084e1c  push    rbp
0x180084e1e  push    rbx
0x180084e1f  push    rsi
0x180084e20  push    rdi
0x180084e21  push    r14
0x180084e23  lea     rbp, [rsp-300h]
0x180084e2b  sub     rsp, 400h
0x180084e32  mov     rax, cs:__security_cookie
0x180084e39  xor     rax, rsp
0x180084e3c  mov     [rbp+320h+var_30], rax
0x180084e43  xor     esi, esi
0x180084e45  lea     rcx, [rbp+320h+var_130]; void *
0x180084e4c  mov     r14d, 80h
0x180084e52  mov     [rsp+420h+KeyHandle], rsi
0x180084e57  mov     r8d, r14d; Size
0x180084e5a  mov     [rsp+420h+var_3F0], rsi
0x180084e5f  xor     edx, edx; Val
0x180084e61  call    memset
0x180084e66  mov     r8d, r14d; Size
0x180084e69  lea     rcx, [rbp+320h+Src]; void *
0x180084e70  xor     edx, edx; Val
0x180084e72  call    memset
0x180084e77  mov     r8d, r14d; Size
0x180084e7a  lea     rcx, [rbp+320h+Str1]; void *
0x180084e81  xor     edx, edx; Val
0x180084e83  call    memset
0x180084e88  call    FreeExternalKeyExchangeAlgorithms
0x180084e8d  cmp     cs:g_dwKeyExchangeInfoTotalCount, 0Ch
0x180084e94  jnb     loc_1800850EC
0x180084e9a  lea     r8, [rsp+420h+KeyHandle]; KeyHandle
0x180084e9f  xor     edx, edx; PCWSTR
0x180084ea1  lea     rcx, aRegistryMachin_5; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180084ea8  call    TlsOpenRegKey
0x180084ead  test    eax, eax
0x180084eaf  js      loc_1800850EC
0x180084eb5  mov     edi, esi
0x180084eb7  jmp     loc_1800850D5
0x180084ebc  xor     edx, edx; Val
0x180084ebe  mov     [rsp+420h+KeyInformation], esi
0x180084ec2  mov     r8d, 214h; Size
0x180084ec8  lea     rcx, [rsp+420h+var_3CC]; void *
0x180084ecd  call    memset
0x180084ed2  mov     rcx, [rsp+420h+KeyHandle]; KeyHandle
0x180084ed7  lea     rax, [rsp+420h+var_3E8]
0x180084edc  mov     [rsp+420h+ResultLength], rax; ResultLength
0x180084ee1  lea     r9, [rsp+420h+KeyInformation]; KeyInformation
0x180084ee6  xor     r8d, r8d; KeyInformationClass
0x180084ee9  mov     [rsp+420h+Length], 218h; Length
0x180084ef1  mov     edx, edi; Index
0x180084ef3  mov     [rsp+420h+var_3E8], esi
0x180084ef7  call    cs:__imp_ZwEnumerateKey
0x180084efe  nop     dword ptr [rax+rax+00h]
0x180084f03  test    eax, eax
0x180084f05  js      loc_1800850E2
0x180084f0b  lea     rax, [rsp+420h+var_3C0]
0x180084f10  or      r9, 0FFFFFFFFFFFFFFFFh
0x180084f14  inc     r9; unsigned __int64
0x180084f17  cmp     [rax+r9*2], si
0x180084f1c  jnz     short loc_180084F14
0x180084f1e  lea     r8, [rsp+420h+var_3C0]; unsigned __int16 *
0x180084f23  lea     rcx, [rbp+320h+var_130]; unsigned __int16 *
0x180084f2a  call    ?RtlStringCchCopyNW@@YAJPEAG_KPEBG1@Z; RtlStringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180084f2f  test    eax, eax
0x180084f31  js      loc_1800850E2
0x180084f37  lea     r8, [rsp+420h+var_3F0]; KeyHandle
0x180084f3c  lea     rdx, [rbp+320h+var_130]; PCWSTR
0x180084f43  lea     rcx, aRegistryMachin_5; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180084f4a  call    TlsOpenRegKey
0x180084f4f  test    eax, eax
0x180084f51  js      loc_1800850D3
0x180084f57  mov     rcx, [rsp+420h+var_3F0]; KeyHandle
0x180084f5c  lea     r8, [rbp+320h+Src]; unsigned __int16 *
0x180084f63  lea     rdx, aCngalgorithm; "CngAlgorithm"
0x180084f6a  call    GetSslStringFromRegistry
0x180084f6f  test    eax, eax
0x180084f71  js      loc_1800850C9
0x180084f77  mov     rcx, [rsp+420h+var_3F0]; KeyHandle
0x180084f7c  lea     r8, [rbp+320h+Str1]; unsigned __int16 *
0x180084f83  lea     rdx, aMessageflow; "MessageFlow"
0x180084f8a  call    GetSslStringFromRegistry
0x180084f8f  test    eax, eax
0x180084f91  js      loc_1800850C9
0x180084f97  lea     rcx, [rsp+420h+var_3F0]
0x180084f9c  call    TlsCloseRegKey
0x180084fa1  mov     ecx, 18h
0x180084fa6  call    MSCryptAlloc
0x180084fab  mov     rbx, rax
0x180084fae  test    rax, rax
0x180084fb1  jz      loc_1800850D3
0x180084fb7  xorps   xmm0, xmm0
0x180084fba  xor     eax, eax
0x180084fbc  movups  xmmword ptr [rbx], xmm0
0x180084fbf  mov     rcx, r14
0x180084fc2  mov     [rbx+10h], rax
0x180084fc6  call    MSCryptAlloc
0x180084fcb  mov     [rbx], rax
0x180084fce  test    rax, rax
0x180084fd1  jnz     short loc_180084FE0
0x180084fd3  mov     rcx, rbx; P
0x180084fd6  call    MSCryptFree
0x180084fdb  jmp     loc_1800850D3
0x180084fe0  lea     r8, [rbp+320h+Src]; Src
0x180084fe7  mov     edx, 40h ; '@'; SizeInWords
0x180084fec  mov     rcx, rax; Dst
0x180084fef  call    cs:__imp_wcscpy_s
0x180084ff6  nop     dword ptr [rax+rax+00h]
0x180084ffb  mov     ecx, cs:g_dwKeyExchangeInfoTotalCount
0x180085001  lea     rdx, aRsa; "RSA"
0x180085008  lea     eax, [rcx+0AFF9h]
0x18008500e  mov     [rbx+0Ch], eax
0x180085011  lea     eax, [rcx-30000006h]
0x180085017  lea     rcx, [rbp+320h+Str1]; Str1
0x18008501e  mov     [rbx+8], eax
0x180085021  call    cs:__imp__wcsicmp
0x180085028  nop     dword ptr [rax+rax+00h]
0x18008502d  test    eax, eax
0x18008502f  jnz     short loc_18008503A
0x180085031  mov     dword ptr [rbx+10h], 1
0x180085038  jmp     short loc_1800850AE
0x18008503a  lea     rdx, aDh; "DH"
0x180085041  lea     rcx, [rbp+320h+Str1]; Str1
0x180085048  call    cs:__imp__wcsicmp
0x18008504f  nop     dword ptr [rax+rax+00h]
0x180085054  test    eax, eax
0x180085056  jnz     short loc_180085061
0x180085058  mov     dword ptr [rbx+10h], 2
0x18008505f  jmp     short loc_1800850AE
0x180085061  lea     rdx, aEcdh; "ECDH"
0x180085068  lea     rcx, [rbp+320h+Str1]; Str1
0x18008506f  call    cs:__imp__wcsicmp
0x180085076  nop     dword ptr [rax+rax+00h]
0x18008507b  test    eax, eax
0x18008507d  jnz     short loc_180085088
0x18008507f  mov     dword ptr [rbx+10h], 3
0x180085086  jmp     short loc_1800850AE
0x180085088  lea     rdx, aPsk; "PSK"
0x18008508f  lea     rcx, [rbp+320h+Str1]; Str1
0x180085096  call    cs:__imp__wcsicmp
0x18008509d  nop     dword ptr [rax+rax+00h]
0x1800850a2  neg     eax
0x1800850a4  sbb     ecx, ecx
0x1800850a6  not     ecx
0x1800850a8  and     ecx, 4
0x1800850ab  mov     [rbx+10h], ecx
0x1800850ae  mov     ecx, cs:g_dwKeyExchangeInfoTotalCount
0x1800850b4  lea     rdx, g_pKeyExchangeInfo
0x1800850bb  mov     [rdx+rcx*8], rbx
0x1800850bf  inc     ecx
0x1800850c1  mov     cs:g_dwKeyExchangeInfoTotalCount, ecx
0x1800850c7  jmp     short loc_1800850D3
0x1800850c9  lea     rcx, [rsp+420h+var_3F0]
0x1800850ce  call    TlsCloseRegKey
0x1800850d3  inc     edi
0x1800850d5  cmp     cs:g_dwKeyExchangeInfoTotalCount, 0Ch
0x1800850dc  jb      loc_180084EBC
0x1800850e2  lea     rcx, [rsp+420h+KeyHandle]
0x1800850e7  call    TlsCloseRegKey
0x1800850ec  mov     rcx, [rbp+320h+var_30]
0x1800850f3  xor     rcx, rsp; StackCookie
0x1800850f6  call    __security_check_cookie
0x1800850fb  add     rsp, 400h
0x180085102  pop     r14
0x180085104  pop     rdi
0x180085105  pop     rsi
0x180085106  pop     rbx
0x180085107  pop     rbp
0x180085108  retn
```
