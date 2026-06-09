# GetExternalKeyExchangeAlgorithms

- ea: `0x18008f00c`
- end: `0x18008f2fa`
- name: `GetExternalKeyExchangeAlgorithms`
- size: `750`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004fd80`
- `0x18008b618`

## callees

- `0x18000e090`
- `0x180010590`
- `0x18008df38`
- `0x18008e05c`
- `0x18008e150`
- `0x18008e184`
- `0x18008ef90`
- `0x18008f00c`
- `0x1800a4260`
- `0x1800a4380`

## import_xrefs

- `ntoskrnl!_wcsicmp` at `0x18008f211`
- `ntoskrnl!_wcsicmp` at `0x18008f238`
- `ntoskrnl!_wcsicmp` at `0x18008f25f`
- `ntoskrnl!_wcsicmp` at `0x18008f286`
- `ntoskrnl!_wcsicmp` at `0x18008f211`
- `ntoskrnl!_wcsicmp` at `0x18008f238`
- `ntoskrnl!_wcsicmp` at `0x18008f25f`
- `ntoskrnl!_wcsicmp` at `0x18008f286`
- `ntoskrnl!ZwEnumerateKey` at `0x18008f0e7`
- `ntoskrnl!ZwEnumerateKey` at `0x18008f0e7`
- `ntoskrnl!wcscpy_s` at `0x18008f1df`
- `ntoskrnl!wcscpy_s` at `0x18008f1df`

## string_xrefs

- `0x18008f091`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\KeyExchange`
- `0x18008f133`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\KeyExchange`

## pseudocode

```c
__int64 GetExternalKeyExchangeAlgorithms()
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
  ULONG ResultLength; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE KeyHandle[2]; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD KeyInformation[136]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Str1[64]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR v15[64]; // [rsp+2F0h] [rbp+1F0h] BYREF
  wchar_t Src[64]; // [rsp+370h] [rbp+270h] BYREF

  KeyHandle[0] = 0;
  v10 = 0;
  memset(v15, 0, sizeof(v15));
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
        if ( (int)RtlStringCchCopyNW(v15, v2, (const unsigned __int16 *)&KeyInformation[4], v3) < 0 )
          break;
        if ( (int)TlsOpenRegKey(
                    L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Prot"
                     "ocol Provider\\KeyExchange",
                    v15,
                    &v10) >= 0 )
        {
          if ( (int)GetSslStringFromRegistry(v10, L"CngAlgorithm", Src) < 0
            || (int)GetSslStringFromRegistry(v10, L"MessageFlow", Str1) < 0 )
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
                v8 = g_dwKeyExchangeInfoTotalCount;
                *((_DWORD *)v6 + 3) = g_dwKeyExchangeInfoTotalCount + 45049;
                *((_DWORD *)v6 + 2) = v8 - 805306374;
                if ( _wcsicmp(Str1, L"RSA") )
                {
                  if ( _wcsicmp(Str1, L"DH") )
                  {
                    if ( _wcsicmp(Str1, L"ECDH") )
                      *((_DWORD *)v6 + 4) = _wcsicmp(Str1, L"PSK") == 0 ? 4 : 0;
                    else
                      *((_DWORD *)v6 + 4) = 3;
                  }
                  else
                  {
                    *((_DWORD *)v6 + 4) = 2;
                  }
                }
                else
                {
                  *((_DWORD *)v6 + 4) = 1;
                }
                v9 = g_dwKeyExchangeInfoTotalCount;
                g_pKeyExchangeInfo[g_dwKeyExchangeInfoTotalCount] = (__int64)v6;
                g_dwKeyExchangeInfoTotalCount = v9 + 1;
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
0x18008f00c  push    rbp
0x18008f00e  push    rbx
0x18008f00f  push    rsi
0x18008f010  push    rdi
0x18008f011  push    r14
0x18008f013  lea     rbp, [rsp-300h]
0x18008f01b  sub     rsp, 400h
0x18008f022  mov     rax, cs:__security_cookie
0x18008f029  xor     rax, rsp
0x18008f02c  mov     [rbp+320h+var_30], rax
0x18008f033  xor     esi, esi
0x18008f035  lea     rcx, [rbp+320h+var_130]; void *
0x18008f03c  mov     r14d, 80h
0x18008f042  mov     [rsp+420h+KeyHandle], rsi
0x18008f047  mov     r8d, r14d; Size
0x18008f04a  mov     [rsp+420h+var_3F0], rsi
0x18008f04f  xor     edx, edx; Val
0x18008f051  call    memset
0x18008f056  mov     r8d, r14d; Size
0x18008f059  lea     rcx, [rbp+320h+Src]; void *
0x18008f060  xor     edx, edx; Val
0x18008f062  call    memset
0x18008f067  mov     r8d, r14d; Size
0x18008f06a  lea     rcx, [rbp+320h+Str1]; void *
0x18008f071  xor     edx, edx; Val
0x18008f073  call    memset
0x18008f078  call    FreeExternalKeyExchangeAlgorithms
0x18008f07d  cmp     cs:g_dwKeyExchangeInfoTotalCount, 0Ch
0x18008f084  jnb     loc_18008F2DC
0x18008f08a  lea     r8, [rsp+420h+KeyHandle]; KeyHandle
0x18008f08f  xor     edx, edx; PCWSTR
0x18008f091  lea     rcx, aRegistryMachin_5; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18008f098  call    TlsOpenRegKey
0x18008f09d  test    eax, eax
0x18008f09f  js      loc_18008F2DC
0x18008f0a5  mov     edi, esi
0x18008f0a7  jmp     loc_18008F2C5
0x18008f0ac  xor     edx, edx; Val
0x18008f0ae  mov     [rsp+420h+KeyInformation], esi
0x18008f0b2  mov     r8d, 214h; Size
0x18008f0b8  lea     rcx, [rsp+420h+var_3CC]; void *
0x18008f0bd  call    memset
0x18008f0c2  mov     rcx, [rsp+420h+KeyHandle]; KeyHandle
0x18008f0c7  lea     rax, [rsp+420h+var_3E8]
0x18008f0cc  mov     [rsp+420h+ResultLength], rax; ResultLength
0x18008f0d1  lea     r9, [rsp+420h+KeyInformation]; KeyInformation
0x18008f0d6  xor     r8d, r8d; KeyInformationClass
0x18008f0d9  mov     [rsp+420h+Length], 218h; Length
0x18008f0e1  mov     edx, edi; Index
0x18008f0e3  mov     [rsp+420h+var_3E8], esi
0x18008f0e7  call    cs:__imp_ZwEnumerateKey
0x18008f0ee  nop     dword ptr [rax+rax+00h]
0x18008f0f3  test    eax, eax
0x18008f0f5  js      loc_18008F2D2
0x18008f0fb  lea     rax, [rsp+420h+var_3C0]
0x18008f100  or      r9, 0FFFFFFFFFFFFFFFFh
0x18008f104  inc     r9; unsigned __int64
0x18008f107  cmp     [rax+r9*2], si
0x18008f10c  jnz     short loc_18008F104
0x18008f10e  lea     r8, [rsp+420h+var_3C0]; unsigned __int16 *
0x18008f113  lea     rcx, [rbp+320h+var_130]; unsigned __int16 *
0x18008f11a  call    ?RtlStringCchCopyNW@@YAJPEAG_KPEBG1@Z; RtlStringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18008f11f  test    eax, eax
0x18008f121  js      loc_18008F2D2
0x18008f127  lea     r8, [rsp+420h+var_3F0]; KeyHandle
0x18008f12c  lea     rdx, [rbp+320h+var_130]; PCWSTR
0x18008f133  lea     rcx, aRegistryMachin_5; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18008f13a  call    TlsOpenRegKey
0x18008f13f  test    eax, eax
0x18008f141  js      loc_18008F2C3
0x18008f147  mov     rcx, [rsp+420h+var_3F0]; KeyHandle
0x18008f14c  lea     r8, [rbp+320h+Src]; unsigned __int16 *
0x18008f153  lea     rdx, aCngalgorithm; "CngAlgorithm"
0x18008f15a  call    GetSslStringFromRegistry
0x18008f15f  test    eax, eax
0x18008f161  js      loc_18008F2B9
0x18008f167  mov     rcx, [rsp+420h+var_3F0]; KeyHandle
0x18008f16c  lea     r8, [rbp+320h+Str1]; unsigned __int16 *
0x18008f173  lea     rdx, aMessageflow; "MessageFlow"
0x18008f17a  call    GetSslStringFromRegistry
0x18008f17f  test    eax, eax
0x18008f181  js      loc_18008F2B9
0x18008f187  lea     rcx, [rsp+420h+var_3F0]
0x18008f18c  call    TlsCloseRegKey
0x18008f191  mov     ecx, 18h
0x18008f196  call    MSCryptAlloc
0x18008f19b  mov     rbx, rax
0x18008f19e  test    rax, rax
0x18008f1a1  jz      loc_18008F2C3
0x18008f1a7  xorps   xmm0, xmm0
0x18008f1aa  xor     eax, eax
0x18008f1ac  movups  xmmword ptr [rbx], xmm0
0x18008f1af  mov     rcx, r14
0x18008f1b2  mov     [rbx+10h], rax
0x18008f1b6  call    MSCryptAlloc
0x18008f1bb  mov     [rbx], rax
0x18008f1be  test    rax, rax
0x18008f1c1  jnz     short loc_18008F1D0
0x18008f1c3  mov     rcx, rbx; P
0x18008f1c6  call    MSCryptFree
0x18008f1cb  jmp     loc_18008F2C3
0x18008f1d0  lea     r8, [rbp+320h+Src]; Src
0x18008f1d7  mov     edx, 40h ; '@'; SizeInWords
0x18008f1dc  mov     rcx, rax; Dst
0x18008f1df  call    cs:__imp_wcscpy_s
0x18008f1e6  nop     dword ptr [rax+rax+00h]
0x18008f1eb  mov     ecx, cs:g_dwKeyExchangeInfoTotalCount
0x18008f1f1  lea     rdx, aRsa; "RSA"
0x18008f1f8  lea     eax, [rcx+0AFF9h]
0x18008f1fe  mov     [rbx+0Ch], eax
0x18008f201  lea     eax, [rcx-30000006h]
0x18008f207  lea     rcx, [rbp+320h+Str1]; Str1
0x18008f20e  mov     [rbx+8], eax
0x18008f211  call    cs:__imp__wcsicmp
0x18008f218  nop     dword ptr [rax+rax+00h]
0x18008f21d  test    eax, eax
0x18008f21f  jnz     short loc_18008F22A
0x18008f221  mov     dword ptr [rbx+10h], 1
0x18008f228  jmp     short loc_18008F29E
0x18008f22a  lea     rdx, aDh; "DH"
0x18008f231  lea     rcx, [rbp+320h+Str1]; Str1
0x18008f238  call    cs:__imp__wcsicmp
0x18008f23f  nop     dword ptr [rax+rax+00h]
0x18008f244  test    eax, eax
0x18008f246  jnz     short loc_18008F251
0x18008f248  mov     dword ptr [rbx+10h], 2
0x18008f24f  jmp     short loc_18008F29E
0x18008f251  lea     rdx, aEcdh; "ECDH"
0x18008f258  lea     rcx, [rbp+320h+Str1]; Str1
0x18008f25f  call    cs:__imp__wcsicmp
0x18008f266  nop     dword ptr [rax+rax+00h]
0x18008f26b  test    eax, eax
0x18008f26d  jnz     short loc_18008F278
0x18008f26f  mov     dword ptr [rbx+10h], 3
0x18008f276  jmp     short loc_18008F29E
0x18008f278  lea     rdx, aPsk; "PSK"
0x18008f27f  lea     rcx, [rbp+320h+Str1]; Str1
0x18008f286  call    cs:__imp__wcsicmp
0x18008f28d  nop     dword ptr [rax+rax+00h]
0x18008f292  neg     eax
0x18008f294  sbb     ecx, ecx
0x18008f296  not     ecx
0x18008f298  and     ecx, 4
0x18008f29b  mov     [rbx+10h], ecx
0x18008f29e  mov     ecx, cs:g_dwKeyExchangeInfoTotalCount
0x18008f2a4  lea     rdx, g_pKeyExchangeInfo
0x18008f2ab  mov     [rdx+rcx*8], rbx
0x18008f2af  inc     ecx
0x18008f2b1  mov     cs:g_dwKeyExchangeInfoTotalCount, ecx
0x18008f2b7  jmp     short loc_18008F2C3
0x18008f2b9  lea     rcx, [rsp+420h+var_3F0]
0x18008f2be  call    TlsCloseRegKey
0x18008f2c3  inc     edi
0x18008f2c5  cmp     cs:g_dwKeyExchangeInfoTotalCount, 0Ch
0x18008f2cc  jb      loc_18008F0AC
0x18008f2d2  lea     rcx, [rsp+420h+KeyHandle]
0x18008f2d7  call    TlsCloseRegKey
0x18008f2dc  mov     rcx, [rbp+320h+var_30]
0x18008f2e3  xor     rcx, rsp; StackCookie
0x18008f2e6  call    __security_check_cookie
0x18008f2eb  add     rsp, 400h
0x18008f2f2  pop     r14
0x18008f2f4  pop     rdi
0x18008f2f5  pop     rsi
0x18008f2f6  pop     rbx
0x18008f2f7  pop     rbp
0x18008f2f8  retn
```
