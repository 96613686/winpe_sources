# GetExternalSignatureAlgorithms

- ea: `0x180024650`
- end: `0x18002491b`
- name: `GetExternalSignatureAlgorithms`
- size: `715`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012578`

## callees

- `0x180003ef0`
- `0x180007940`
- `0x1800126f0`
- `0x180012a7c`
- `0x180012d6c`
- `0x180014660`
- `0x180018140`
- `0x180023d58`
- `0x1800244f0`
- `0x1800245d8`
- `0x180024650`
- `0x180024ef0`
- `0x180025660`

## import_xrefs

- `ntdll!NtEnumerateKey` at `0x18002472f`
- `ntdll!NtEnumerateKey` at `0x18002472f`

## string_xrefs

- `0x1800246d9`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Signature`
- `0x180024775`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Signature`

## pseudocode

```c
__int64 GetExternalSignatureAlgorithms()
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
  int v9; // [rsp+38h] [rbp-C8h]
  ULONG ResultLength; // [rsp+3Ch] [rbp-C4h] BYREF
  HANDLE KeyHandle[2]; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD KeyInformation[136]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t String1[64]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR v14[64]; // [rsp+2F0h] [rbp+1F0h] BYREF
  wchar_t Source[64]; // [rsp+370h] [rbp+270h] BYREF

  KeyHandle[0] = 0;
  v8 = 0;
  memset(v14, 0, sizeof(v14));
  memset(Source, 0, sizeof(Source));
  memset(String1, 0, sizeof(String1));
  v9 = 0;
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
        if ( NtEnumerateKey(KeyHandle[0], i, KeyBasicInformation, KeyInformation, 0x218u, &ResultLength) < 0 )
          break;
        v3 = -1;
        do
          ++v3;
        while ( *((_WORD *)&KeyInformation[4] + v3) );
        if ( (int)RtlStringCchCopyNW(v14, v2, (const unsigned __int16 *)&KeyInformation[4], v3) < 0 )
          break;
        if ( (int)TlsOpenRegKey(
                    L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Prot"
                     "ocol Provider\\Signature",
                    v14,
                    &v8) >= 0 )
        {
          if ( (int)GetSslStringFromRegistry(v8, L"CngAlgorithm", Source) < 0
            || (int)GetSslDWordFromRegistry(v8) < 0
            || (int)GetSslStringFromRegistry(v8, L"SignatureStyle", String1) < 0 )
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
                v6 = g_dwSignatureInfoTotalCount;
                *(_DWORD *)(v4 + 12) = g_dwSignatureInfoTotalCount + 12281;
                *(_DWORD *)(v4 + 8) = v6 - 536870918;
                *(_DWORD *)(v4 + 16) = v9;
                if ( wcsicmp(String1, L"RSA") )
                {
                  if ( wcsicmp(String1, L"DSA") )
                    *(_DWORD *)(v4 + 20) = wcsicmp(String1, L"ECDSA") == 0 ? 4 : 0;
                  else
                    *(_DWORD *)(v4 + 20) = 3;
                }
                else
                {
                  *(_DWORD *)(v4 + 20) = 2;
                }
                v7 = (unsigned int)g_dwSignatureInfoTotalCount++;
                g_pSignatureInfo[v7] = v4;
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
0x180024650  push    rbp
0x180024652  push    rbx
0x180024653  push    rsi
0x180024654  push    rdi
0x180024655  push    r14
0x180024657  lea     rbp, [rsp-300h]
0x18002465f  sub     rsp, 400h
0x180024666  mov     rax, cs:__security_cookie
0x18002466d  xor     rax, rsp
0x180024670  mov     [rbp+320h+var_30], rax
0x180024677  xor     esi, esi
0x180024679  lea     rcx, [rbp+320h+var_130]; void *
0x180024680  mov     r14d, 80h
0x180024686  mov     [rsp+420h+KeyHandle], rsi
0x18002468b  mov     r8d, r14d; Size
0x18002468e  mov     [rsp+420h+var_3F0], rsi
0x180024693  xor     edx, edx; Val
0x180024695  call    memset
0x18002469a  mov     r8d, r14d; Size
0x18002469d  lea     rcx, [rbp+320h+Source]; void *
0x1800246a4  xor     edx, edx; Val
0x1800246a6  call    memset
0x1800246ab  mov     r8d, r14d; Size
0x1800246ae  lea     rcx, [rbp+320h+String1]; void *
0x1800246b5  xor     edx, edx; Val
0x1800246b7  call    memset
0x1800246bc  mov     [rsp+420h+var_3E8], esi
0x1800246c0  call    FreeExternalSignatureAlgorithms
0x1800246c5  cmp     cs:g_dwSignatureInfoTotalCount, 10h
0x1800246cc  jnb     loc_1800248FE
0x1800246d2  lea     r8, [rsp+420h+KeyHandle]; KeyHandle
0x1800246d7  xor     edx, edx; PCWSTR
0x1800246d9  lea     rcx, aRegistryMachin_1; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x1800246e0  call    TlsOpenRegKey
0x1800246e5  test    eax, eax
0x1800246e7  js      loc_1800248FE
0x1800246ed  mov     edi, esi
0x1800246ef  jmp     loc_1800248E7
0x1800246f4  xor     edx, edx; Val
0x1800246f6  mov     [rsp+420h+KeyInformation], esi
0x1800246fa  mov     r8d, 214h; Size
0x180024700  lea     rcx, [rsp+420h+var_3CC]; void *
0x180024705  call    memset
0x18002470a  mov     rcx, [rsp+420h+KeyHandle]; KeyHandle
0x18002470f  lea     rax, [rsp+420h+var_3E4]
0x180024714  mov     [rsp+420h+ResultLength], rax; ResultLength
0x180024719  lea     r9, [rsp+420h+KeyInformation]; KeyInformation
0x18002471e  xor     r8d, r8d; KeyInformationClass
0x180024721  mov     [rsp+420h+Length], 218h; Length
0x180024729  mov     edx, edi; Index
0x18002472b  mov     [rsp+420h+var_3E4], esi
0x18002472f  call    cs:__imp_NtEnumerateKey
0x180024735  test    eax, eax
0x180024737  js      loc_1800248F4
0x18002473d  lea     rax, [rsp+420h+var_3C0]
0x180024742  or      r9, 0FFFFFFFFFFFFFFFFh
0x180024746  inc     r9; unsigned __int64
0x180024749  cmp     [rax+r9*2], si
0x18002474e  jnz     short loc_180024746
0x180024750  lea     r8, [rsp+420h+var_3C0]; unsigned __int16 *
0x180024755  lea     rcx, [rbp+320h+var_130]; unsigned __int16 *
0x18002475c  call    ?RtlStringCchCopyNW@@YAJPEAG_KPEBG1@Z; RtlStringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180024761  test    eax, eax
0x180024763  js      loc_1800248F4
0x180024769  lea     r8, [rsp+420h+var_3F0]; KeyHandle
0x18002476e  lea     rdx, [rbp+320h+var_130]; PCWSTR
0x180024775  lea     rcx, aRegistryMachin_1; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18002477c  call    TlsOpenRegKey
0x180024781  test    eax, eax
0x180024783  js      loc_1800248E5
0x180024789  mov     rcx, [rsp+420h+var_3F0]; KeyHandle
0x18002478e  lea     r8, [rbp+320h+Source]; unsigned __int16 *
0x180024795  lea     rdx, aCngalgorithm; "CngAlgorithm"
0x18002479c  call    GetSslStringFromRegistry
0x1800247a1  test    eax, eax
0x1800247a3  js      loc_1800248DB
0x1800247a9  mov     rcx, [rsp+420h+var_3F0]; KeyHandle
0x1800247ae  lea     r8, [rsp+420h+var_3E8]
0x1800247b3  lea     rdx, aTlscodepoint; "TlsCodePoint"
0x1800247ba  call    GetSslDWordFromRegistry
0x1800247bf  test    eax, eax
0x1800247c1  js      loc_1800248DB
0x1800247c7  mov     rcx, [rsp+420h+var_3F0]; KeyHandle
0x1800247cc  lea     r8, [rbp+320h+String1]; unsigned __int16 *
0x1800247d3  lea     rdx, aSignaturestyle; "SignatureStyle"
0x1800247da  call    GetSslStringFromRegistry
0x1800247df  test    eax, eax
0x1800247e1  js      loc_1800248DB
0x1800247e7  lea     rcx, [rsp+420h+var_3F0]
0x1800247ec  call    TlsCloseRegKey
0x1800247f1  mov     ecx, 18h
0x1800247f6  call    SafeAllocaAllocateFromHeap
0x1800247fb  mov     rbx, rax
0x1800247fe  test    rax, rax
0x180024801  jz      loc_1800248E5
0x180024807  xorps   xmm0, xmm0
0x18002480a  xor     eax, eax
0x18002480c  movups  xmmword ptr [rbx], xmm0
0x18002480f  mov     rcx, r14
0x180024812  mov     [rbx+10h], rax
0x180024816  call    SafeAllocaAllocateFromHeap
0x18002481b  mov     [rbx], rax
0x18002481e  test    rax, rax
0x180024821  jnz     short loc_180024830
0x180024823  mov     rcx, rbx
0x180024826  call    MSCryptFree
0x18002482b  jmp     loc_1800248E5
0x180024830  lea     r8, [rbp+320h+Source]; Source
0x180024837  mov     edx, 40h ; '@'; SizeInWords
0x18002483c  mov     rcx, rax; Destination
0x18002483f  call    wcscpy_s
0x180024844  mov     ecx, cs:g_dwSignatureInfoTotalCount
0x18002484a  lea     rdx, aRsa; "RSA"
0x180024851  lea     eax, [rcx+2FF9h]
0x180024857  mov     [rbx+0Ch], eax
0x18002485a  lea     eax, [rcx-20000006h]
0x180024860  mov     [rbx+8], eax
0x180024863  lea     rcx, [rbp+320h+String1]; String1
0x18002486a  mov     eax, [rsp+420h+var_3E8]
0x18002486e  mov     [rbx+10h], eax
0x180024871  call    _wcsicmp
0x180024876  test    eax, eax
0x180024878  jnz     short loc_180024883
0x18002487a  mov     dword ptr [rbx+14h], 2
0x180024881  jmp     short loc_1800248C2
0x180024883  lea     rdx, aDsa; "DSA"
0x18002488a  lea     rcx, [rbp+320h+String1]; String1
0x180024891  call    _wcsicmp
0x180024896  test    eax, eax
0x180024898  jnz     short loc_1800248A3
0x18002489a  mov     dword ptr [rbx+14h], 3
0x1800248a1  jmp     short loc_1800248C2
0x1800248a3  lea     rdx, aEcdsa; "ECDSA"
0x1800248aa  lea     rcx, [rbp+320h+String1]; String1
0x1800248b1  call    _wcsicmp
0x1800248b6  neg     eax
0x1800248b8  sbb     ecx, ecx
0x1800248ba  not     ecx
0x1800248bc  and     ecx, 4
0x1800248bf  mov     [rbx+14h], ecx
0x1800248c2  mov     eax, cs:g_dwSignatureInfoTotalCount
0x1800248c8  lea     rcx, g_pSignatureInfo
0x1800248cf  inc     cs:g_dwSignatureInfoTotalCount
0x1800248d5  mov     [rcx+rax*8], rbx
0x1800248d9  jmp     short loc_1800248E5
0x1800248db  lea     rcx, [rsp+420h+var_3F0]
0x1800248e0  call    TlsCloseRegKey
0x1800248e5  inc     edi
0x1800248e7  cmp     cs:g_dwSignatureInfoTotalCount, 10h
0x1800248ee  jb      loc_1800246F4
0x1800248f4  lea     rcx, [rsp+420h+KeyHandle]
0x1800248f9  call    TlsCloseRegKey
0x1800248fe  mov     rcx, [rbp+320h+var_30]
0x180024905  xor     rcx, rsp; StackCookie
0x180024908  call    __security_check_cookie
0x18002490d  add     rsp, 400h
0x180024914  pop     r14
0x180024916  pop     rdi
0x180024917  pop     rsi
0x180024918  pop     rbx
0x180024919  pop     rbp
0x18002491a  retn
```
