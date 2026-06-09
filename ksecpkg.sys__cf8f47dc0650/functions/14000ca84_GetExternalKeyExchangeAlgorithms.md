# GetExternalKeyExchangeAlgorithms

- ea: `0x14000ca84`
- end: `0x14000cda5`
- name: `GetExternalKeyExchangeAlgorithms`
- size: `801`
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
- `0x14000c9f0`
- `0x14000ca84`
- `0x140010160`
- `0x1400105c0`

## import_xrefs

- `ntoskrnl!_wcsicmp` at `0x14000ccba`
- `ntoskrnl!_wcsicmp` at `0x14000cce1`
- `ntoskrnl!_wcsicmp` at `0x14000cd08`
- `ntoskrnl!_wcsicmp` at `0x14000cd2f`
- `ntoskrnl!_wcsicmp` at `0x14000ccba`
- `ntoskrnl!_wcsicmp` at `0x14000cce1`
- `ntoskrnl!_wcsicmp` at `0x14000cd08`
- `ntoskrnl!_wcsicmp` at `0x14000cd2f`
- `ntoskrnl!ZwEnumerateKey` at `0x14000cb6d`
- `ntoskrnl!ZwEnumerateKey` at `0x14000cb6d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cc71`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cc71`
- `ntoskrnl!ExAllocatePool2` at `0x14000cc25`
- `ntoskrnl!ExAllocatePool2` at `0x14000cc55`
- `ntoskrnl!ExAllocatePool2` at `0x14000cc25`
- `ntoskrnl!ExAllocatePool2` at `0x14000cc55`

## string_xrefs

- `0x14000cb0b`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\KeyExchange`
- `0x14000cbb9`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\KeyExchange`

## pseudocode

```c
__int64 GetExternalKeyExchangeAlgorithms()
{
  __int64 result; // rax
  ULONG i; // edi
  unsigned __int64 v2; // rdx
  unsigned __int64 v3; // r9
  wchar_t **Pool2; // rbx
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
            Pool2 = (wchar_t **)ExAllocatePool2(64, 24, 1131180883);
            if ( Pool2 )
            {
              *(_OWORD *)Pool2 = 0;
              Pool2[2] = 0;
              v5 = (wchar_t *)ExAllocatePool2(64, 128, 1131180883);
              *Pool2 = v5;
              if ( v5 )
              {
                wcscpy_s(v5, 0x40u, Src);
                v6 = g_dwKeyExchangeInfoTotalCount;
                *((_DWORD *)Pool2 + 3) = g_dwKeyExchangeInfoTotalCount + 45049;
                *((_DWORD *)Pool2 + 2) = v6 - 805306374;
                if ( _wcsicmp(Str1, L"RSA") )
                {
                  if ( _wcsicmp(Str1, L"DH") )
                  {
                    if ( _wcsicmp(Str1, L"ECDH") )
                      *((_DWORD *)Pool2 + 4) = _wcsicmp(Str1, L"PSK") == 0 ? 4 : 0;
                    else
                      *((_DWORD *)Pool2 + 4) = 3;
                  }
                  else
                  {
                    *((_DWORD *)Pool2 + 4) = 2;
                  }
                }
                else
                {
                  *((_DWORD *)Pool2 + 4) = 1;
                }
                v7 = g_dwKeyExchangeInfoTotalCount;
                g_pKeyExchangeInfo[g_dwKeyExchangeInfoTotalCount] = (__int64)Pool2;
                g_dwKeyExchangeInfoTotalCount = v7 + 1;
              }
              else
              {
                ExFreePoolWithTag(Pool2, 0x436C7353u);
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
0x14000ca84  push    rbp
0x14000ca86  push    rbx
0x14000ca87  push    rsi
0x14000ca88  push    rdi
0x14000ca89  push    r12
0x14000ca8b  push    r14
0x14000ca8d  lea     rbp, [rsp-308h]
0x14000ca95  sub     rsp, 408h
0x14000ca9c  mov     rax, cs:__security_cookie
0x14000caa3  xor     rax, rsp
0x14000caa6  mov     [rbp+330h+var_40], rax
0x14000caad  xor     esi, esi
0x14000caaf  lea     rcx, [rbp+330h+var_140]; void *
0x14000cab6  mov     r14d, 80h
0x14000cabc  mov     [rsp+430h+KeyHandle], rsi
0x14000cac1  mov     r8d, r14d; Size
0x14000cac4  mov     [rsp+430h+var_400], rsi
0x14000cac9  xor     edx, edx; Val
0x14000cacb  call    memset
0x14000cad0  mov     r8d, r14d; Size
0x14000cad3  lea     rcx, [rbp+330h+Src]; void *
0x14000cada  xor     edx, edx; Val
0x14000cadc  call    memset
0x14000cae1  mov     r8d, r14d; Size
0x14000cae4  lea     rcx, [rbp+330h+Str1]; void *
0x14000caeb  xor     edx, edx; Val
0x14000caed  call    memset
0x14000caf2  call    FreeExternalKeyExchangeAlgorithms
0x14000caf7  cmp     cs:g_dwKeyExchangeInfoTotalCount, 0Ch
0x14000cafe  jnb     loc_14000CD85
0x14000cb04  lea     r8, [rsp+430h+KeyHandle]; KeyHandle
0x14000cb09  xor     edx, edx; PCWSTR
0x14000cb0b  lea     rcx, aRegistryMachin_1; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x14000cb12  call    TlsOpenRegKey
0x14000cb17  test    eax, eax
0x14000cb19  js      loc_14000CD85
0x14000cb1f  cmp     cs:g_dwKeyExchangeInfoTotalCount, 0Ch
0x14000cb26  mov     edi, esi
0x14000cb28  jnb     loc_14000CD7B
0x14000cb2e  lea     r12d, [rsi+40h]
0x14000cb32  xor     edx, edx; Val
0x14000cb34  mov     [rsp+430h+KeyInformation], esi
0x14000cb38  mov     r8d, 214h; Size
0x14000cb3e  lea     rcx, [rsp+430h+var_3DC]; void *
0x14000cb43  call    memset
0x14000cb48  mov     rcx, [rsp+430h+KeyHandle]; KeyHandle
0x14000cb4d  lea     rax, [rsp+430h+var_3F8]
0x14000cb52  mov     [rsp+430h+ResultLength], rax; ResultLength
0x14000cb57  lea     r9, [rsp+430h+KeyInformation]; KeyInformation
0x14000cb5c  xor     r8d, r8d; KeyInformationClass
0x14000cb5f  mov     [rsp+430h+Length], 218h; Length
0x14000cb67  mov     edx, edi; Index
0x14000cb69  mov     [rsp+430h+var_3F8], esi
0x14000cb6d  call    cs:__imp_ZwEnumerateKey
0x14000cb74  nop     dword ptr [rax+rax+00h]
0x14000cb79  test    eax, eax
0x14000cb7b  js      loc_14000CD7B
0x14000cb81  lea     rax, [rsp+430h+var_3D0]
0x14000cb86  or      r9, 0FFFFFFFFFFFFFFFFh
0x14000cb8a  inc     r9; unsigned __int64
0x14000cb8d  cmp     [rax+r9*2], si
0x14000cb92  jnz     short loc_14000CB8A
0x14000cb94  lea     r8, [rsp+430h+var_3D0]; unsigned __int16 *
0x14000cb99  lea     rcx, [rbp+330h+var_140]; unsigned __int16 *
0x14000cba0  call    ?RtlStringCchCopyNW@@YAJPEAG_KPEBG1@Z; RtlStringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x14000cba5  test    eax, eax
0x14000cba7  js      loc_14000CD7B
0x14000cbad  lea     r8, [rsp+430h+var_400]; KeyHandle
0x14000cbb2  lea     rdx, [rbp+330h+var_140]; PCWSTR
0x14000cbb9  lea     rcx, aRegistryMachin_1; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x14000cbc0  call    TlsOpenRegKey
0x14000cbc5  test    eax, eax
0x14000cbc7  js      loc_14000CD6C
0x14000cbcd  mov     rcx, [rsp+430h+var_400]; KeyHandle
0x14000cbd2  lea     r8, [rbp+330h+Src]; unsigned __int16 *
0x14000cbd9  lea     rdx, aCngalgorithm; "CngAlgorithm"
0x14000cbe0  call    GetSslStringFromRegistry
0x14000cbe5  test    eax, eax
0x14000cbe7  js      loc_14000CD62
0x14000cbed  mov     rcx, [rsp+430h+var_400]; KeyHandle
0x14000cbf2  lea     r8, [rbp+330h+Str1]; unsigned __int16 *
0x14000cbf9  lea     rdx, aMessageflow; "MessageFlow"
0x14000cc00  call    GetSslStringFromRegistry
0x14000cc05  test    eax, eax
0x14000cc07  js      loc_14000CD62
0x14000cc0d  lea     rcx, [rsp+430h+var_400]
0x14000cc12  call    TlsCloseRegKey
0x14000cc17  mov     edx, 18h
0x14000cc1c  mov     r8d, 436C7353h
0x14000cc22  mov     rcx, r12
0x14000cc25  call    cs:__imp_ExAllocatePool2
0x14000cc2c  nop     dword ptr [rax+rax+00h]
0x14000cc31  mov     rbx, rax
0x14000cc34  test    rax, rax
0x14000cc37  jz      loc_14000CD6C
0x14000cc3d  xorps   xmm0, xmm0
0x14000cc40  xor     eax, eax
0x14000cc42  movups  xmmword ptr [rbx], xmm0
0x14000cc45  mov     r8d, 436C7353h
0x14000cc4b  mov     [rbx+10h], rax
0x14000cc4f  mov     rdx, r14
0x14000cc52  mov     rcx, r12
0x14000cc55  call    cs:__imp_ExAllocatePool2
0x14000cc5c  nop     dword ptr [rax+rax+00h]
0x14000cc61  mov     [rbx], rax
0x14000cc64  test    rax, rax
0x14000cc67  jnz     short loc_14000CC82
0x14000cc69  mov     edx, 436C7353h; Tag
0x14000cc6e  mov     rcx, rbx; P
0x14000cc71  call    cs:__imp_ExFreePoolWithTag
0x14000cc78  nop     dword ptr [rax+rax+00h]
0x14000cc7d  jmp     loc_14000CD6C
0x14000cc82  lea     r8, [rbp+330h+Src]; Src
0x14000cc89  mov     rdx, r12; SizeInWords
0x14000cc8c  mov     rcx, rax; Dst
0x14000cc8f  call    wcscpy_s
0x14000cc94  mov     ecx, cs:g_dwKeyExchangeInfoTotalCount
0x14000cc9a  lea     rdx, aRsa; "RSA"
0x14000cca1  lea     eax, [rcx+0AFF9h]
0x14000cca7  mov     [rbx+0Ch], eax
0x14000ccaa  lea     eax, [rcx-30000006h]
0x14000ccb0  lea     rcx, [rbp+330h+Str1]; Str1
0x14000ccb7  mov     [rbx+8], eax
0x14000ccba  call    cs:__imp__wcsicmp
0x14000ccc1  nop     dword ptr [rax+rax+00h]
0x14000ccc6  test    eax, eax
0x14000ccc8  jnz     short loc_14000CCD3
0x14000ccca  mov     dword ptr [rbx+10h], 1
0x14000ccd1  jmp     short loc_14000CD47
0x14000ccd3  lea     rdx, aDh; "DH"
0x14000ccda  lea     rcx, [rbp+330h+Str1]; Str1
0x14000cce1  call    cs:__imp__wcsicmp
0x14000cce8  nop     dword ptr [rax+rax+00h]
0x14000cced  test    eax, eax
0x14000ccef  jnz     short loc_14000CCFA
0x14000ccf1  mov     dword ptr [rbx+10h], 2
0x14000ccf8  jmp     short loc_14000CD47
0x14000ccfa  lea     rdx, aEcdh; "ECDH"
0x14000cd01  lea     rcx, [rbp+330h+Str1]; Str1
0x14000cd08  call    cs:__imp__wcsicmp
0x14000cd0f  nop     dword ptr [rax+rax+00h]
0x14000cd14  test    eax, eax
0x14000cd16  jnz     short loc_14000CD21
0x14000cd18  mov     dword ptr [rbx+10h], 3
0x14000cd1f  jmp     short loc_14000CD47
0x14000cd21  lea     rdx, aPsk; "PSK"
0x14000cd28  lea     rcx, [rbp+330h+Str1]; Str1
0x14000cd2f  call    cs:__imp__wcsicmp
0x14000cd36  nop     dword ptr [rax+rax+00h]
0x14000cd3b  neg     eax
0x14000cd3d  sbb     ecx, ecx
0x14000cd3f  not     ecx
0x14000cd41  and     ecx, 4
0x14000cd44  mov     [rbx+10h], ecx
0x14000cd47  mov     ecx, cs:g_dwKeyExchangeInfoTotalCount
0x14000cd4d  lea     rdx, g_pKeyExchangeInfo
0x14000cd54  mov     [rdx+rcx*8], rbx
0x14000cd58  inc     ecx
0x14000cd5a  mov     cs:g_dwKeyExchangeInfoTotalCount, ecx
0x14000cd60  jmp     short loc_14000CD6C
0x14000cd62  lea     rcx, [rsp+430h+var_400]
0x14000cd67  call    TlsCloseRegKey
0x14000cd6c  inc     edi
0x14000cd6e  cmp     cs:g_dwKeyExchangeInfoTotalCount, 0Ch
0x14000cd75  jb      loc_14000CB32
0x14000cd7b  lea     rcx, [rsp+430h+KeyHandle]
0x14000cd80  call    TlsCloseRegKey
0x14000cd85  mov     rcx, [rbp+330h+var_40]
0x14000cd8c  xor     rcx, rsp; StackCookie
0x14000cd8f  call    __security_check_cookie
0x14000cd94  add     rsp, 408h
0x14000cd9b  pop     r14
0x14000cd9d  pop     r12
0x14000cd9f  pop     rdi
0x14000cda0  pop     rsi
0x14000cda1  pop     rbx
0x14000cda2  pop     rbp
0x14000cda3  retn
```
