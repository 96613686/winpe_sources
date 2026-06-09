# GetExternalKeyExchangeAlgorithms

- ea: `0x180024a3c`
- end: `0x180024cfe`
- name: `GetExternalKeyExchangeAlgorithms`
- size: `706`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012578`

## callees

- `0x180003ef0`
- `0x180007940`
- `0x1800126f0`
- `0x180012d6c`
- `0x180014660`
- `0x180018140`
- `0x180023d58`
- `0x1800244f0`
- `0x1800249c4`
- `0x180024a3c`
- `0x180024ef0`
- `0x180025660`

## import_xrefs

- `ntdll!NtEnumerateKey` at `0x180024b17`
- `ntdll!NtEnumerateKey` at `0x180024b17`

## string_xrefs

- `0x180024ac1`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\KeyExchange`
- `0x180024b5d`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\KeyExchange`

## pseudocode

```c
__int64 GetExternalKeyExchangeAlgorithms()
{
  __int64 result; // rax
  ULONG i; // edi
  unsigned __int64 v2; // rdx
  unsigned __int64 v3; // r9
  __int64 v4; // rbx
  wchar_t *v5; // rax
  int v6; // ecx
  __int64 v7; // rax
  HANDLE v8; // [rsp+30h] [rbp-D0h] BYREF
  ULONG ResultLength; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE KeyHandle[2]; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD KeyInformation[136]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t String1[64]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR v13[64]; // [rsp+2F0h] [rbp+1F0h] BYREF
  wchar_t Source[64]; // [rsp+370h] [rbp+270h] BYREF

  KeyHandle[0] = 0;
  v8 = 0;
  memset(v13, 0, sizeof(v13));
  memset(Source, 0, sizeof(Source));
  memset(String1, 0, sizeof(String1));
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
        if ( NtEnumerateKey(KeyHandle[0], i, KeyBasicInformation, KeyInformation, 0x218u, &ResultLength) < 0 )
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
          if ( (int)GetSslStringFromRegistry(v8, L"CngAlgorithm", Source) < 0
            || (int)GetSslStringFromRegistry(v8, L"MessageFlow", String1) < 0 )
          {
            TlsCloseRegKey(&v8);
          }
          else
          {
            TlsCloseRegKey(&v8);
            v4 = SafeAllocaAllocateFromHeap(24);
            if ( v4 )
            {
              *(_OWORD *)v4 = 0;
              *(_QWORD *)(v4 + 16) = 0;
              v5 = (wchar_t *)SafeAllocaAllocateFromHeap(128);
              *(_QWORD *)v4 = v5;
              if ( v5 )
              {
                wcscpy_s(v5, 0x40u, Source);
                v6 = g_dwKeyExchangeInfoTotalCount;
                *(_DWORD *)(v4 + 12) = g_dwKeyExchangeInfoTotalCount + 45049;
                *(_DWORD *)(v4 + 8) = v6 - 805306374;
                if ( wcsicmp(String1, L"RSA") )
                {
                  if ( wcsicmp(String1, L"DH") )
                  {
                    if ( wcsicmp(String1, L"ECDH") )
                      *(_DWORD *)(v4 + 16) = wcsicmp(String1, L"PSK") == 0 ? 4 : 0;
                    else
                      *(_DWORD *)(v4 + 16) = 3;
                  }
                  else
                  {
                    *(_DWORD *)(v4 + 16) = 2;
                  }
                }
                else
                {
                  *(_DWORD *)(v4 + 16) = 1;
                }
                v7 = (unsigned int)g_dwKeyExchangeInfoTotalCount++;
                g_pKeyExchangeInfo[v7] = v4;
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
0x180024a3c  push    rbp
0x180024a3e  push    rbx
0x180024a3f  push    rsi
0x180024a40  push    rdi
0x180024a41  push    r14
0x180024a43  lea     rbp, [rsp-300h]
0x180024a4b  sub     rsp, 400h
0x180024a52  mov     rax, cs:__security_cookie
0x180024a59  xor     rax, rsp
0x180024a5c  mov     [rbp+320h+var_30], rax
0x180024a63  xor     esi, esi
0x180024a65  lea     rcx, [rbp+320h+var_130]; void *
0x180024a6c  mov     r14d, 80h
0x180024a72  mov     [rsp+420h+KeyHandle], rsi
0x180024a77  mov     r8d, r14d; Size
0x180024a7a  mov     [rsp+420h+var_3F0], rsi
0x180024a7f  xor     edx, edx; Val
0x180024a81  call    memset
0x180024a86  mov     r8d, r14d; Size
0x180024a89  lea     rcx, [rbp+320h+Source]; void *
0x180024a90  xor     edx, edx; Val
0x180024a92  call    memset
0x180024a97  mov     r8d, r14d; Size
0x180024a9a  lea     rcx, [rbp+320h+String1]; void *
0x180024aa1  xor     edx, edx; Val
0x180024aa3  call    memset
0x180024aa8  call    FreeExternalKeyExchangeAlgorithms
0x180024aad  cmp     cs:g_dwKeyExchangeInfoTotalCount, 0Ch
0x180024ab4  jnb     loc_180024CE1
0x180024aba  lea     r8, [rsp+420h+KeyHandle]; KeyHandle
0x180024abf  xor     edx, edx; PCWSTR
0x180024ac1  lea     rcx, aRegistryMachin_0; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180024ac8  call    TlsOpenRegKey
0x180024acd  test    eax, eax
0x180024acf  js      loc_180024CE1
0x180024ad5  mov     edi, esi
0x180024ad7  jmp     loc_180024CCA
0x180024adc  xor     edx, edx; Val
0x180024ade  mov     [rsp+420h+KeyInformation], esi
0x180024ae2  mov     r8d, 214h; Size
0x180024ae8  lea     rcx, [rsp+420h+var_3CC]; void *
0x180024aed  call    memset
0x180024af2  mov     rcx, [rsp+420h+KeyHandle]; KeyHandle
0x180024af7  lea     rax, [rsp+420h+var_3E8]
0x180024afc  mov     [rsp+420h+ResultLength], rax; ResultLength
0x180024b01  lea     r9, [rsp+420h+KeyInformation]; KeyInformation
0x180024b06  xor     r8d, r8d; KeyInformationClass
0x180024b09  mov     [rsp+420h+Length], 218h; Length
0x180024b11  mov     edx, edi; Index
0x180024b13  mov     [rsp+420h+var_3E8], esi
0x180024b17  call    cs:__imp_NtEnumerateKey
0x180024b1d  test    eax, eax
0x180024b1f  js      loc_180024CD7
0x180024b25  lea     rax, [rsp+420h+var_3C0]
0x180024b2a  or      r9, 0FFFFFFFFFFFFFFFFh
0x180024b2e  inc     r9; unsigned __int64
0x180024b31  cmp     [rax+r9*2], si
0x180024b36  jnz     short loc_180024B2E
0x180024b38  lea     r8, [rsp+420h+var_3C0]; unsigned __int16 *
0x180024b3d  lea     rcx, [rbp+320h+var_130]; unsigned __int16 *
0x180024b44  call    ?RtlStringCchCopyNW@@YAJPEAG_KPEBG1@Z; RtlStringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180024b49  test    eax, eax
0x180024b4b  js      loc_180024CD7
0x180024b51  lea     r8, [rsp+420h+var_3F0]; KeyHandle
0x180024b56  lea     rdx, [rbp+320h+var_130]; PCWSTR
0x180024b5d  lea     rcx, aRegistryMachin_0; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180024b64  call    TlsOpenRegKey
0x180024b69  test    eax, eax
0x180024b6b  js      loc_180024CC8
0x180024b71  mov     rcx, [rsp+420h+var_3F0]; KeyHandle
0x180024b76  lea     r8, [rbp+320h+Source]; unsigned __int16 *
0x180024b7d  lea     rdx, aCngalgorithm; "CngAlgorithm"
0x180024b84  call    GetSslStringFromRegistry
0x180024b89  test    eax, eax
0x180024b8b  js      loc_180024CBE
0x180024b91  mov     rcx, [rsp+420h+var_3F0]; KeyHandle
0x180024b96  lea     r8, [rbp+320h+String1]; unsigned __int16 *
0x180024b9d  lea     rdx, aMessageflow; "MessageFlow"
0x180024ba4  call    GetSslStringFromRegistry
0x180024ba9  test    eax, eax
0x180024bab  js      loc_180024CBE
0x180024bb1  lea     rcx, [rsp+420h+var_3F0]
0x180024bb6  call    TlsCloseRegKey
0x180024bbb  mov     ecx, 18h
0x180024bc0  call    SafeAllocaAllocateFromHeap
0x180024bc5  mov     rbx, rax
0x180024bc8  test    rax, rax
0x180024bcb  jz      loc_180024CC8
0x180024bd1  xorps   xmm0, xmm0
0x180024bd4  xor     eax, eax
0x180024bd6  movups  xmmword ptr [rbx], xmm0
0x180024bd9  mov     rcx, r14
0x180024bdc  mov     [rbx+10h], rax
0x180024be0  call    SafeAllocaAllocateFromHeap
0x180024be5  mov     [rbx], rax
0x180024be8  test    rax, rax
0x180024beb  jnz     short loc_180024BFA
0x180024bed  mov     rcx, rbx
0x180024bf0  call    MSCryptFree
0x180024bf5  jmp     loc_180024CC8
0x180024bfa  lea     r8, [rbp+320h+Source]; Source
0x180024c01  mov     edx, 40h ; '@'; SizeInWords
0x180024c06  mov     rcx, rax; Destination
0x180024c09  call    wcscpy_s
0x180024c0e  mov     ecx, cs:g_dwKeyExchangeInfoTotalCount
0x180024c14  lea     rdx, aRsa; "RSA"
0x180024c1b  lea     eax, [rcx+0AFF9h]
0x180024c21  mov     [rbx+0Ch], eax
0x180024c24  lea     eax, [rcx-30000006h]
0x180024c2a  lea     rcx, [rbp+320h+String1]; String1
0x180024c31  mov     [rbx+8], eax
0x180024c34  call    _wcsicmp
0x180024c39  test    eax, eax
0x180024c3b  jnz     short loc_180024C46
0x180024c3d  mov     dword ptr [rbx+10h], 1
0x180024c44  jmp     short loc_180024CA5
0x180024c46  lea     rdx, aDh; "DH"
0x180024c4d  lea     rcx, [rbp+320h+String1]; String1
0x180024c54  call    _wcsicmp
0x180024c59  test    eax, eax
0x180024c5b  jnz     short loc_180024C66
0x180024c5d  mov     dword ptr [rbx+10h], 2
0x180024c64  jmp     short loc_180024CA5
0x180024c66  lea     rdx, aEcdh; "ECDH"
0x180024c6d  lea     rcx, [rbp+320h+String1]; String1
0x180024c74  call    _wcsicmp
0x180024c79  test    eax, eax
0x180024c7b  jnz     short loc_180024C86
0x180024c7d  mov     dword ptr [rbx+10h], 3
0x180024c84  jmp     short loc_180024CA5
0x180024c86  lea     rdx, aPsk; "PSK"
0x180024c8d  lea     rcx, [rbp+320h+String1]; String1
0x180024c94  call    _wcsicmp
0x180024c99  neg     eax
0x180024c9b  sbb     ecx, ecx
0x180024c9d  not     ecx
0x180024c9f  and     ecx, 4
0x180024ca2  mov     [rbx+10h], ecx
0x180024ca5  mov     eax, cs:g_dwKeyExchangeInfoTotalCount
0x180024cab  lea     rcx, g_pKeyExchangeInfo
0x180024cb2  inc     cs:g_dwKeyExchangeInfoTotalCount
0x180024cb8  mov     [rcx+rax*8], rbx
0x180024cbc  jmp     short loc_180024CC8
0x180024cbe  lea     rcx, [rsp+420h+var_3F0]
0x180024cc3  call    TlsCloseRegKey
0x180024cc8  inc     edi
0x180024cca  cmp     cs:g_dwKeyExchangeInfoTotalCount, 0Ch
0x180024cd1  jb      loc_180024ADC
0x180024cd7  lea     rcx, [rsp+420h+KeyHandle]
0x180024cdc  call    TlsCloseRegKey
0x180024ce1  mov     rcx, [rbp+320h+var_30]
0x180024ce8  xor     rcx, rsp; StackCookie
0x180024ceb  call    __security_check_cookie
0x180024cf0  add     rsp, 400h
0x180024cf7  pop     r14
0x180024cf9  pop     rdi
0x180024cfa  pop     rsi
0x180024cfb  pop     rbx
0x180024cfc  pop     rbp
0x180024cfd  retn
```
