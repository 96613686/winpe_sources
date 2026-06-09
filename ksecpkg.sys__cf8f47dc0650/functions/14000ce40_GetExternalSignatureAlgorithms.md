# GetExternalSignatureAlgorithms

- ea: `0x14000ce40`
- end: `0x14000d163`
- name: `GetExternalSignatureAlgorithms`
- size: `803`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000bff0`

## callees

- `0x140006110`
- `0x14000c5d8`
- `0x14000c63c`
- `0x14000c6fc`
- `0x14000c7f0`
- `0x14000c86c`
- `0x14000cdac`
- `0x14000ce40`
- `0x140010160`
- `0x1400105c0`

## import_xrefs

- `ntoskrnl!_wcsicmp` at `0x14000d09f`
- `ntoskrnl!_wcsicmp` at `0x14000d0c6`
- `ntoskrnl!_wcsicmp` at `0x14000d0ed`
- `ntoskrnl!_wcsicmp` at `0x14000d09f`
- `ntoskrnl!_wcsicmp` at `0x14000d0c6`
- `ntoskrnl!_wcsicmp` at `0x14000d0ed`
- `ntoskrnl!ZwEnumerateKey` at `0x14000cf2d`
- `ntoskrnl!ZwEnumerateKey` at `0x14000cf2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d04f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d04f`
- `ntoskrnl!ExAllocatePool2` at `0x14000d003`
- `ntoskrnl!ExAllocatePool2` at `0x14000d033`
- `ntoskrnl!ExAllocatePool2` at `0x14000d003`
- `ntoskrnl!ExAllocatePool2` at `0x14000d033`

## string_xrefs

- `0x14000cecb`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Signature`
- `0x14000cf79`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Signature`

## pseudocode

```c
__int64 GetExternalSignatureAlgorithms()
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
  int v9; // [rsp+38h] [rbp-C8h]
  ULONG ResultLength; // [rsp+3Ch] [rbp-C4h] BYREF
  HANDLE KeyHandle[2]; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD KeyInformation[136]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Str1[64]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR v14[64]; // [rsp+2F0h] [rbp+1F0h] BYREF
  wchar_t Src[64]; // [rsp+370h] [rbp+270h] BYREF

  KeyHandle[0] = 0;
  v8 = 0;
  memset(v14, 0, sizeof(v14));
  memset(Src, 0, sizeof(Src));
  memset(Str1, 0, sizeof(Str1));
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
        if ( ZwEnumerateKey(KeyHandle[0], i, KeyBasicInformation, KeyInformation, 0x218u, &ResultLength) < 0 )
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
          if ( (int)GetSslStringFromRegistry(v8, L"CngAlgorithm", Src) < 0
            || (int)GetSslDWordFromRegistry(v8) < 0
            || (int)GetSslStringFromRegistry(v8, L"SignatureStyle", Str1) < 0 )
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
                v6 = g_dwSignatureInfoTotalCount;
                *((_DWORD *)Pool2 + 3) = g_dwSignatureInfoTotalCount + 12281;
                *((_DWORD *)Pool2 + 2) = v6 - 536870918;
                *((_DWORD *)Pool2 + 4) = v9;
                if ( _wcsicmp(Str1, L"RSA") )
                {
                  if ( _wcsicmp(Str1, L"DSA") )
                    *((_DWORD *)Pool2 + 5) = _wcsicmp(Str1, L"ECDSA") == 0 ? 4 : 0;
                  else
                    *((_DWORD *)Pool2 + 5) = 3;
                }
                else
                {
                  *((_DWORD *)Pool2 + 5) = 2;
                }
                v7 = g_dwSignatureInfoTotalCount;
                g_pSignatureInfo[g_dwSignatureInfoTotalCount] = (__int64)Pool2;
                g_dwSignatureInfoTotalCount = v7 + 1;
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
0x14000ce40  push    rbp
0x14000ce42  push    rbx
0x14000ce43  push    rsi
0x14000ce44  push    rdi
0x14000ce45  push    r12
0x14000ce47  push    r14
0x14000ce49  lea     rbp, [rsp-308h]
0x14000ce51  sub     rsp, 408h
0x14000ce58  mov     rax, cs:__security_cookie
0x14000ce5f  xor     rax, rsp
0x14000ce62  mov     [rbp+330h+var_40], rax
0x14000ce69  xor     esi, esi
0x14000ce6b  lea     rcx, [rbp+330h+var_140]; void *
0x14000ce72  mov     r14d, 80h
0x14000ce78  mov     [rsp+430h+KeyHandle], rsi
0x14000ce7d  mov     r8d, r14d; Size
0x14000ce80  mov     [rsp+430h+var_400], rsi
0x14000ce85  xor     edx, edx; Val
0x14000ce87  call    memset
0x14000ce8c  mov     r8d, r14d; Size
0x14000ce8f  lea     rcx, [rbp+330h+Src]; void *
0x14000ce96  xor     edx, edx; Val
0x14000ce98  call    memset
0x14000ce9d  mov     r8d, r14d; Size
0x14000cea0  lea     rcx, [rbp+330h+Str1]; void *
0x14000cea7  xor     edx, edx; Val
0x14000cea9  call    memset
0x14000ceae  mov     [rsp+430h+var_3F8], esi
0x14000ceb2  call    FreeExternalSignatureAlgorithms
0x14000ceb7  cmp     cs:g_dwSignatureInfoTotalCount, 10h
0x14000cebe  jnb     loc_14000D143
0x14000cec4  lea     r8, [rsp+430h+KeyHandle]; KeyHandle
0x14000cec9  xor     edx, edx; PCWSTR
0x14000cecb  lea     rcx, aRegistryMachin_3; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x14000ced2  call    TlsOpenRegKey
0x14000ced7  test    eax, eax
0x14000ced9  js      loc_14000D143
0x14000cedf  cmp     cs:g_dwSignatureInfoTotalCount, 10h
0x14000cee6  mov     edi, esi
0x14000cee8  jnb     loc_14000D139
0x14000ceee  lea     r12d, [rsi+40h]
0x14000cef2  xor     edx, edx; Val
0x14000cef4  mov     [rsp+430h+KeyInformation], esi
0x14000cef8  mov     r8d, 214h; Size
0x14000cefe  lea     rcx, [rsp+430h+var_3DC]; void *
0x14000cf03  call    memset
0x14000cf08  mov     rcx, [rsp+430h+KeyHandle]; KeyHandle
0x14000cf0d  lea     rax, [rsp+430h+var_3F4]
0x14000cf12  mov     [rsp+430h+ResultLength], rax; ResultLength
0x14000cf17  lea     r9, [rsp+430h+KeyInformation]; KeyInformation
0x14000cf1c  xor     r8d, r8d; KeyInformationClass
0x14000cf1f  mov     [rsp+430h+Length], 218h; Length
0x14000cf27  mov     edx, edi; Index
0x14000cf29  mov     [rsp+430h+var_3F4], esi
0x14000cf2d  call    cs:__imp_ZwEnumerateKey
0x14000cf34  nop     dword ptr [rax+rax+00h]
0x14000cf39  test    eax, eax
0x14000cf3b  js      loc_14000D139
0x14000cf41  lea     rax, [rsp+430h+var_3D0]
0x14000cf46  or      r9, 0FFFFFFFFFFFFFFFFh
0x14000cf4a  inc     r9; unsigned __int64
0x14000cf4d  cmp     [rax+r9*2], si
0x14000cf52  jnz     short loc_14000CF4A
0x14000cf54  lea     r8, [rsp+430h+var_3D0]; unsigned __int16 *
0x14000cf59  lea     rcx, [rbp+330h+var_140]; unsigned __int16 *
0x14000cf60  call    ?RtlStringCchCopyNW@@YAJPEAG_KPEBG1@Z; RtlStringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x14000cf65  test    eax, eax
0x14000cf67  js      loc_14000D139
0x14000cf6d  lea     r8, [rsp+430h+var_400]; KeyHandle
0x14000cf72  lea     rdx, [rbp+330h+var_140]; PCWSTR
0x14000cf79  lea     rcx, aRegistryMachin_3; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x14000cf80  call    TlsOpenRegKey
0x14000cf85  test    eax, eax
0x14000cf87  js      loc_14000D12A
0x14000cf8d  mov     rcx, [rsp+430h+var_400]; KeyHandle
0x14000cf92  lea     r8, [rbp+330h+Src]; unsigned __int16 *
0x14000cf99  lea     rdx, aCngalgorithm; "CngAlgorithm"
0x14000cfa0  call    GetSslStringFromRegistry
0x14000cfa5  test    eax, eax
0x14000cfa7  js      loc_14000D120
0x14000cfad  mov     rcx, [rsp+430h+var_400]; KeyHandle
0x14000cfb2  lea     r8, [rsp+430h+var_3F8]
0x14000cfb7  lea     rdx, aTlscodepoint; "TlsCodePoint"
0x14000cfbe  call    GetSslDWordFromRegistry
0x14000cfc3  test    eax, eax
0x14000cfc5  js      loc_14000D120
0x14000cfcb  mov     rcx, [rsp+430h+var_400]; KeyHandle
0x14000cfd0  lea     r8, [rbp+330h+Str1]; unsigned __int16 *
0x14000cfd7  lea     rdx, aSignaturestyle; "SignatureStyle"
0x14000cfde  call    GetSslStringFromRegistry
0x14000cfe3  test    eax, eax
0x14000cfe5  js      loc_14000D120
0x14000cfeb  lea     rcx, [rsp+430h+var_400]
0x14000cff0  call    TlsCloseRegKey
0x14000cff5  mov     edx, 18h
0x14000cffa  mov     r8d, 436C7353h
0x14000d000  mov     rcx, r12
0x14000d003  call    cs:__imp_ExAllocatePool2
0x14000d00a  nop     dword ptr [rax+rax+00h]
0x14000d00f  mov     rbx, rax
0x14000d012  test    rax, rax
0x14000d015  jz      loc_14000D12A
0x14000d01b  xorps   xmm0, xmm0
0x14000d01e  xor     eax, eax
0x14000d020  movups  xmmword ptr [rbx], xmm0
0x14000d023  mov     r8d, 436C7353h
0x14000d029  mov     [rbx+10h], rax
0x14000d02d  mov     rdx, r14
0x14000d030  mov     rcx, r12
0x14000d033  call    cs:__imp_ExAllocatePool2
0x14000d03a  nop     dword ptr [rax+rax+00h]
0x14000d03f  mov     [rbx], rax
0x14000d042  test    rax, rax
0x14000d045  jnz     short loc_14000D060
0x14000d047  mov     edx, 436C7353h; Tag
0x14000d04c  mov     rcx, rbx; P
0x14000d04f  call    cs:__imp_ExFreePoolWithTag
0x14000d056  nop     dword ptr [rax+rax+00h]
0x14000d05b  jmp     loc_14000D12A
0x14000d060  lea     r8, [rbp+330h+Src]; Src
0x14000d067  mov     rdx, r12; SizeInWords
0x14000d06a  mov     rcx, rax; Dst
0x14000d06d  call    wcscpy_s
0x14000d072  mov     ecx, cs:g_dwSignatureInfoTotalCount
0x14000d078  lea     rdx, aRsa; "RSA"
0x14000d07f  lea     eax, [rcx+2FF9h]
0x14000d085  mov     [rbx+0Ch], eax
0x14000d088  lea     eax, [rcx-20000006h]
0x14000d08e  mov     [rbx+8], eax
0x14000d091  lea     rcx, [rbp+330h+Str1]; Str1
0x14000d098  mov     eax, [rsp+430h+var_3F8]
0x14000d09c  mov     [rbx+10h], eax
0x14000d09f  call    cs:__imp__wcsicmp
0x14000d0a6  nop     dword ptr [rax+rax+00h]
0x14000d0ab  test    eax, eax
0x14000d0ad  jnz     short loc_14000D0B8
0x14000d0af  mov     dword ptr [rbx+14h], 2
0x14000d0b6  jmp     short loc_14000D105
0x14000d0b8  lea     rdx, aDsa; "DSA"
0x14000d0bf  lea     rcx, [rbp+330h+Str1]; Str1
0x14000d0c6  call    cs:__imp__wcsicmp
0x14000d0cd  nop     dword ptr [rax+rax+00h]
0x14000d0d2  test    eax, eax
0x14000d0d4  jnz     short loc_14000D0DF
0x14000d0d6  mov     dword ptr [rbx+14h], 3
0x14000d0dd  jmp     short loc_14000D105
0x14000d0df  lea     rdx, aEcdsa; "ECDSA"
0x14000d0e6  lea     rcx, [rbp+330h+Str1]; Str1
0x14000d0ed  call    cs:__imp__wcsicmp
0x14000d0f4  nop     dword ptr [rax+rax+00h]
0x14000d0f9  neg     eax
0x14000d0fb  sbb     ecx, ecx
0x14000d0fd  not     ecx
0x14000d0ff  and     ecx, 4
0x14000d102  mov     [rbx+14h], ecx
0x14000d105  mov     ecx, cs:g_dwSignatureInfoTotalCount
0x14000d10b  lea     rdx, g_pSignatureInfo
0x14000d112  mov     [rdx+rcx*8], rbx
0x14000d116  inc     ecx
0x14000d118  mov     cs:g_dwSignatureInfoTotalCount, ecx
0x14000d11e  jmp     short loc_14000D12A
0x14000d120  lea     rcx, [rsp+430h+var_400]
0x14000d125  call    TlsCloseRegKey
0x14000d12a  inc     edi
0x14000d12c  cmp     cs:g_dwSignatureInfoTotalCount, 10h
0x14000d133  jb      loc_14000CEF2
0x14000d139  lea     rcx, [rsp+430h+KeyHandle]
0x14000d13e  call    TlsCloseRegKey
0x14000d143  mov     rcx, [rbp+330h+var_40]
0x14000d14a  xor     rcx, rsp; StackCookie
0x14000d14d  call    __security_check_cookie
0x14000d152  add     rsp, 408h
0x14000d159  pop     r14
0x14000d15b  pop     r12
0x14000d15d  pop     rdi
0x14000d15e  pop     rsi
0x14000d15f  pop     rbx
0x14000d160  pop     rbp
0x14000d161  retn
```
