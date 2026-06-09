# GetExternalKeyExchangeAlgorithms

- ea: `0x180085e34`
- end: `0x180086122`
- name: `GetExternalKeyExchangeAlgorithms`
- size: `750`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180046720`
- `0x180082418`

## callees

- `0x180003f70`
- `0x180006470`
- `0x180084d38`
- `0x180084e5c`
- `0x180084f50`
- `0x180084f84`
- `0x180085db8`
- `0x180085e34`
- `0x18009f650`
- `0x18009fa80`

## import_xrefs

- `ntoskrnl!_wcsicmp` at `0x180086039`
- `ntoskrnl!_wcsicmp` at `0x180086060`
- `ntoskrnl!_wcsicmp` at `0x180086087`
- `ntoskrnl!_wcsicmp` at `0x1800860ae`
- `ntoskrnl!_wcsicmp` at `0x180086039`
- `ntoskrnl!_wcsicmp` at `0x180086060`
- `ntoskrnl!_wcsicmp` at `0x180086087`
- `ntoskrnl!_wcsicmp` at `0x1800860ae`
- `ntoskrnl!ZwEnumerateKey` at `0x180085f0f`
- `ntoskrnl!ZwEnumerateKey` at `0x180085f0f`
- `ntoskrnl!wcscpy_s` at `0x180086007`
- `ntoskrnl!wcscpy_s` at `0x180086007`

## string_xrefs

- `0x180085eb9`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\KeyExchange`
- `0x180085f5b`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\KeyExchange`

## pseudocode

```c
__int64 GetExternalKeyExchangeAlgorithms()
{
  __int64 result; // rax
  __int64 v1; // r9
  ULONG i; // edi
  unsigned __int64 v3; // rdx
  unsigned __int64 v4; // r9
  __int64 v5; // r9
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rdx
  wchar_t **v10; // rbx
  __int64 v11; // r8
  __int64 v12; // r9
  wchar_t *v13; // rax
  int v14; // ecx
  int v15; // ecx
  HANDLE v16; // [rsp+30h] [rbp-D0h] BYREF
  ULONG ResultLength; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE KeyHandle[2]; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD KeyInformation[136]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Str1[64]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR v21[64]; // [rsp+2F0h] [rbp+1F0h] BYREF
  wchar_t Src[64]; // [rsp+370h] [rbp+270h] BYREF

  KeyHandle[0] = 0;
  v16 = 0;
  memset(v21, 0, sizeof(v21));
  memset(Src, 0, sizeof(Src));
  memset(Str1, 0, sizeof(Str1));
  result = FreeExternalKeyExchangeAlgorithms();
  if ( (unsigned int)g_dwKeyExchangeInfoTotalCount < 0xC )
  {
    result = TlsOpenRegKey(
               L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Protocol "
                "Provider\\KeyExchange",
               0,
               KeyHandle,
               v1);
    if ( (int)result >= 0 )
    {
      for ( i = 0; (unsigned int)g_dwKeyExchangeInfoTotalCount < 0xC; ++i )
      {
        memset(KeyInformation, 0, 536);
        ResultLength = 0;
        if ( ZwEnumerateKey(KeyHandle[0], i, KeyBasicInformation, KeyInformation, 0x218u, &ResultLength) < 0 )
          break;
        v4 = -1;
        do
          ++v4;
        while ( *((_WORD *)&KeyInformation[4] + v4) );
        if ( (int)RtlStringCchCopyNW(v21, v3, (const unsigned __int16 *)&KeyInformation[4], v4) < 0 )
          break;
        if ( (int)TlsOpenRegKey(
                    L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Prot"
                     "ocol Provider\\KeyExchange",
                    v21,
                    &v16,
                    v5) >= 0 )
        {
          if ( (int)GetSslStringFromRegistry(v16, L"CngAlgorithm", Src) < 0
            || (int)GetSslStringFromRegistry(v16, L"MessageFlow", Str1) < 0 )
          {
            TlsCloseRegKey(&v16);
          }
          else
          {
            TlsCloseRegKey(&v16);
            v10 = (wchar_t **)MSCryptAlloc(24, v6, v7, v8);
            if ( v10 )
            {
              *(_OWORD *)v10 = 0;
              v10[2] = 0;
              v13 = (wchar_t *)MSCryptAlloc(128, v9, v11, v12);
              *v10 = v13;
              if ( v13 )
              {
                wcscpy_s(v13, 0x40u, Src);
                v14 = g_dwKeyExchangeInfoTotalCount;
                *((_DWORD *)v10 + 3) = g_dwKeyExchangeInfoTotalCount + 45049;
                *((_DWORD *)v10 + 2) = v14 - 805306374;
                if ( _wcsicmp(Str1, L"RSA") )
                {
                  if ( _wcsicmp(Str1, L"DH") )
                  {
                    if ( _wcsicmp(Str1, L"ECDH") )
                      *((_DWORD *)v10 + 4) = _wcsicmp(Str1, L"PSK") == 0 ? 4 : 0;
                    else
                      *((_DWORD *)v10 + 4) = 3;
                  }
                  else
                  {
                    *((_DWORD *)v10 + 4) = 2;
                  }
                }
                else
                {
                  *((_DWORD *)v10 + 4) = 1;
                }
                v15 = g_dwKeyExchangeInfoTotalCount;
                g_pKeyExchangeInfo[g_dwKeyExchangeInfoTotalCount] = (__int64)v10;
                g_dwKeyExchangeInfoTotalCount = v15 + 1;
              }
              else
              {
                MSCryptFree(v10);
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
0x180085e34  push    rbp
0x180085e36  push    rbx
0x180085e37  push    rsi
0x180085e38  push    rdi
0x180085e39  push    r14
0x180085e3b  lea     rbp, [rsp-300h]
0x180085e43  sub     rsp, 400h
0x180085e4a  mov     rax, cs:__security_cookie
0x180085e51  xor     rax, rsp
0x180085e54  mov     [rbp+320h+var_30], rax
0x180085e5b  xor     esi, esi
0x180085e5d  lea     rcx, [rbp+320h+var_130]; void *
0x180085e64  mov     r14d, 80h
0x180085e6a  mov     [rsp+420h+KeyHandle], rsi
0x180085e6f  mov     r8d, r14d; Size
0x180085e72  mov     [rsp+420h+var_3F0], rsi
0x180085e77  xor     edx, edx; Val
0x180085e79  call    memset
0x180085e7e  mov     r8d, r14d; Size
0x180085e81  lea     rcx, [rbp+320h+Src]; void *
0x180085e88  xor     edx, edx; Val
0x180085e8a  call    memset
0x180085e8f  mov     r8d, r14d; Size
0x180085e92  lea     rcx, [rbp+320h+Str1]; void *
0x180085e99  xor     edx, edx; Val
0x180085e9b  call    memset
0x180085ea0  call    FreeExternalKeyExchangeAlgorithms
0x180085ea5  cmp     cs:g_dwKeyExchangeInfoTotalCount, 0Ch
0x180085eac  jnb     loc_180086104
0x180085eb2  lea     r8, [rsp+420h+KeyHandle]; KeyHandle
0x180085eb7  xor     edx, edx; PCWSTR
0x180085eb9  lea     rcx, aRegistryMachin_5; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180085ec0  call    TlsOpenRegKey
0x180085ec5  test    eax, eax
0x180085ec7  js      loc_180086104
0x180085ecd  mov     edi, esi
0x180085ecf  jmp     loc_1800860ED
0x180085ed4  xor     edx, edx; Val
0x180085ed6  mov     [rsp+420h+KeyInformation], esi
0x180085eda  mov     r8d, 214h; Size
0x180085ee0  lea     rcx, [rsp+420h+var_3CC]; void *
0x180085ee5  call    memset
0x180085eea  mov     rcx, [rsp+420h+KeyHandle]; KeyHandle
0x180085eef  lea     rax, [rsp+420h+var_3E8]
0x180085ef4  mov     [rsp+420h+ResultLength], rax; ResultLength
0x180085ef9  lea     r9, [rsp+420h+KeyInformation]; KeyInformation
0x180085efe  xor     r8d, r8d; KeyInformationClass
0x180085f01  mov     [rsp+420h+Length], 218h; Length
0x180085f09  mov     edx, edi; Index
0x180085f0b  mov     [rsp+420h+var_3E8], esi
0x180085f0f  call    cs:__imp_ZwEnumerateKey
0x180085f16  nop     dword ptr [rax+rax+00h]
0x180085f1b  test    eax, eax
0x180085f1d  js      loc_1800860FA
0x180085f23  lea     rax, [rsp+420h+var_3C0]
0x180085f28  or      r9, 0FFFFFFFFFFFFFFFFh
0x180085f2c  inc     r9; unsigned __int64
0x180085f2f  cmp     [rax+r9*2], si
0x180085f34  jnz     short loc_180085F2C
0x180085f36  lea     r8, [rsp+420h+var_3C0]; unsigned __int16 *
0x180085f3b  lea     rcx, [rbp+320h+var_130]; unsigned __int16 *
0x180085f42  call    ?RtlStringCchCopyNW@@YAJPEAG_KPEBG1@Z; RtlStringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180085f47  test    eax, eax
0x180085f49  js      loc_1800860FA
0x180085f4f  lea     r8, [rsp+420h+var_3F0]; KeyHandle
0x180085f54  lea     rdx, [rbp+320h+var_130]; PCWSTR
0x180085f5b  lea     rcx, aRegistryMachin_5; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180085f62  call    TlsOpenRegKey
0x180085f67  test    eax, eax
0x180085f69  js      loc_1800860EB
0x180085f6f  mov     rcx, [rsp+420h+var_3F0]; KeyHandle
0x180085f74  lea     r8, [rbp+320h+Src]; unsigned __int16 *
0x180085f7b  lea     rdx, aCngalgorithm; "CngAlgorithm"
0x180085f82  call    GetSslStringFromRegistry
0x180085f87  test    eax, eax
0x180085f89  js      loc_1800860E1
0x180085f8f  mov     rcx, [rsp+420h+var_3F0]; KeyHandle
0x180085f94  lea     r8, [rbp+320h+Str1]; unsigned __int16 *
0x180085f9b  lea     rdx, aMessageflow; "MessageFlow"
0x180085fa2  call    GetSslStringFromRegistry
0x180085fa7  test    eax, eax
0x180085fa9  js      loc_1800860E1
0x180085faf  lea     rcx, [rsp+420h+var_3F0]
0x180085fb4  call    TlsCloseRegKey
0x180085fb9  mov     ecx, 18h
0x180085fbe  call    MSCryptAlloc
0x180085fc3  mov     rbx, rax
0x180085fc6  test    rax, rax
0x180085fc9  jz      loc_1800860EB
0x180085fcf  xorps   xmm0, xmm0
0x180085fd2  xor     eax, eax
0x180085fd4  movups  xmmword ptr [rbx], xmm0
0x180085fd7  mov     rcx, r14
0x180085fda  mov     [rbx+10h], rax
0x180085fde  call    MSCryptAlloc
0x180085fe3  mov     [rbx], rax
0x180085fe6  test    rax, rax
0x180085fe9  jnz     short loc_180085FF8
0x180085feb  mov     rcx, rbx; P
0x180085fee  call    MSCryptFree
0x180085ff3  jmp     loc_1800860EB
0x180085ff8  lea     r8, [rbp+320h+Src]; Src
0x180085fff  mov     edx, 40h ; '@'; SizeInWords
0x180086004  mov     rcx, rax; Dst
0x180086007  call    cs:__imp_wcscpy_s
0x18008600e  nop     dword ptr [rax+rax+00h]
0x180086013  mov     ecx, cs:g_dwKeyExchangeInfoTotalCount
0x180086019  lea     rdx, aRsa; "RSA"
0x180086020  lea     eax, [rcx+0AFF9h]
0x180086026  mov     [rbx+0Ch], eax
0x180086029  lea     eax, [rcx-30000006h]
0x18008602f  lea     rcx, [rbp+320h+Str1]; Str1
0x180086036  mov     [rbx+8], eax
0x180086039  call    cs:__imp__wcsicmp
0x180086040  nop     dword ptr [rax+rax+00h]
0x180086045  test    eax, eax
0x180086047  jnz     short loc_180086052
0x180086049  mov     dword ptr [rbx+10h], 1
0x180086050  jmp     short loc_1800860C6
0x180086052  lea     rdx, aDh; "DH"
0x180086059  lea     rcx, [rbp+320h+Str1]; Str1
0x180086060  call    cs:__imp__wcsicmp
0x180086067  nop     dword ptr [rax+rax+00h]
0x18008606c  test    eax, eax
0x18008606e  jnz     short loc_180086079
0x180086070  mov     dword ptr [rbx+10h], 2
0x180086077  jmp     short loc_1800860C6
0x180086079  lea     rdx, aEcdh; "ECDH"
0x180086080  lea     rcx, [rbp+320h+Str1]; Str1
0x180086087  call    cs:__imp__wcsicmp
0x18008608e  nop     dword ptr [rax+rax+00h]
0x180086093  test    eax, eax
0x180086095  jnz     short loc_1800860A0
0x180086097  mov     dword ptr [rbx+10h], 3
0x18008609e  jmp     short loc_1800860C6
0x1800860a0  lea     rdx, aPsk; "PSK"
0x1800860a7  lea     rcx, [rbp+320h+Str1]; Str1
0x1800860ae  call    cs:__imp__wcsicmp
0x1800860b5  nop     dword ptr [rax+rax+00h]
0x1800860ba  neg     eax
0x1800860bc  sbb     ecx, ecx
0x1800860be  not     ecx
0x1800860c0  and     ecx, 4
0x1800860c3  mov     [rbx+10h], ecx
0x1800860c6  mov     ecx, cs:g_dwKeyExchangeInfoTotalCount
0x1800860cc  lea     rdx, g_pKeyExchangeInfo
0x1800860d3  mov     [rdx+rcx*8], rbx
0x1800860d7  inc     ecx
0x1800860d9  mov     cs:g_dwKeyExchangeInfoTotalCount, ecx
0x1800860df  jmp     short loc_1800860EB
0x1800860e1  lea     rcx, [rsp+420h+var_3F0]
0x1800860e6  call    TlsCloseRegKey
0x1800860eb  inc     edi
0x1800860ed  cmp     cs:g_dwKeyExchangeInfoTotalCount, 0Ch
0x1800860f4  jb      loc_180085ED4
0x1800860fa  lea     rcx, [rsp+420h+KeyHandle]
0x1800860ff  call    TlsCloseRegKey
0x180086104  mov     rcx, [rbp+320h+var_30]
0x18008610b  xor     rcx, rsp; StackCookie
0x18008610e  call    __security_check_cookie
0x180086113  add     rsp, 400h
0x18008611a  pop     r14
0x18008611c  pop     rdi
0x18008611d  pop     rsi
0x18008611e  pop     rbx
0x18008611f  pop     rbp
0x180086120  retn
```
