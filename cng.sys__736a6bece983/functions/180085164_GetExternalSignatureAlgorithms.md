# GetExternalSignatureAlgorithms

- ea: `0x180085164`
- end: `0x180085454`
- name: `GetExternalSignatureAlgorithms`
- size: `752`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180046720`
- `0x180082418`

## callees

- `0x180003f70`
- `0x180006470`
- `0x180084d38`
- `0x180084d9c`
- `0x180084e5c`
- `0x180084f50`
- `0x180084f84`
- `0x1800850e8`
- `0x180085164`
- `0x18009f650`
- `0x18009fa80`

## import_xrefs

- `ntoskrnl!_wcsicmp` at `0x180085392`
- `ntoskrnl!_wcsicmp` at `0x1800853b9`
- `ntoskrnl!_wcsicmp` at `0x1800853e0`
- `ntoskrnl!_wcsicmp` at `0x180085392`
- `ntoskrnl!_wcsicmp` at `0x1800853b9`
- `ntoskrnl!_wcsicmp` at `0x1800853e0`
- `ntoskrnl!ZwEnumerateKey` at `0x180085243`
- `ntoskrnl!ZwEnumerateKey` at `0x180085243`
- `ntoskrnl!wcscpy_s` at `0x180085359`
- `ntoskrnl!wcscpy_s` at `0x180085359`

## string_xrefs

- `0x1800851ed`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Signature`
- `0x18008528f`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Signature`

## pseudocode

```c
__int64 GetExternalSignatureAlgorithms()
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
  int v17; // [rsp+38h] [rbp-C8h]
  ULONG ResultLength; // [rsp+3Ch] [rbp-C4h] BYREF
  HANDLE KeyHandle[2]; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD KeyInformation[136]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Str1[64]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR v22[64]; // [rsp+2F0h] [rbp+1F0h] BYREF
  wchar_t Src[64]; // [rsp+370h] [rbp+270h] BYREF

  KeyHandle[0] = 0;
  v16 = 0;
  memset(v22, 0, sizeof(v22));
  memset(Src, 0, sizeof(Src));
  memset(Str1, 0, sizeof(Str1));
  v17 = 0;
  result = FreeExternalSignatureAlgorithms();
  if ( (unsigned int)g_dwSignatureInfoTotalCount < 0x10 )
  {
    result = TlsOpenRegKey(
               L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Protocol "
                "Provider\\Signature",
               0,
               KeyHandle,
               v1);
    if ( (int)result >= 0 )
    {
      for ( i = 0; (unsigned int)g_dwSignatureInfoTotalCount < 0x10; ++i )
      {
        memset(KeyInformation, 0, 536);
        ResultLength = 0;
        if ( ZwEnumerateKey(KeyHandle[0], i, KeyBasicInformation, KeyInformation, 0x218u, &ResultLength) < 0 )
          break;
        v4 = -1;
        do
          ++v4;
        while ( *((_WORD *)&KeyInformation[4] + v4) );
        if ( (int)RtlStringCchCopyNW(v22, v3, (const unsigned __int16 *)&KeyInformation[4], v4) < 0 )
          break;
        if ( (int)TlsOpenRegKey(
                    L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Prot"
                     "ocol Provider\\Signature",
                    v22,
                    &v16,
                    v5) >= 0 )
        {
          if ( (int)GetSslStringFromRegistry(v16, L"CngAlgorithm", Src) < 0
            || (int)GetSslDWordFromRegistry(v16) < 0
            || (int)GetSslStringFromRegistry(v16, L"SignatureStyle", Str1) < 0 )
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
                v14 = g_dwSignatureInfoTotalCount;
                *((_DWORD *)v10 + 3) = g_dwSignatureInfoTotalCount + 12281;
                *((_DWORD *)v10 + 2) = v14 - 536870918;
                *((_DWORD *)v10 + 4) = v17;
                if ( _wcsicmp(Str1, L"RSA") )
                {
                  if ( _wcsicmp(Str1, L"DSA") )
                    *((_DWORD *)v10 + 5) = _wcsicmp(Str1, L"ECDSA") == 0 ? 4 : 0;
                  else
                    *((_DWORD *)v10 + 5) = 3;
                }
                else
                {
                  *((_DWORD *)v10 + 5) = 2;
                }
                v15 = g_dwSignatureInfoTotalCount;
                g_pSignatureInfo[g_dwSignatureInfoTotalCount] = (__int64)v10;
                g_dwSignatureInfoTotalCount = v15 + 1;
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
0x180085164  push    rbp
0x180085166  push    rbx
0x180085167  push    rsi
0x180085168  push    rdi
0x180085169  push    r14
0x18008516b  lea     rbp, [rsp-300h]
0x180085173  sub     rsp, 400h
0x18008517a  mov     rax, cs:__security_cookie
0x180085181  xor     rax, rsp
0x180085184  mov     [rbp+320h+var_30], rax
0x18008518b  xor     esi, esi
0x18008518d  lea     rcx, [rbp+320h+var_130]; void *
0x180085194  mov     r14d, 80h
0x18008519a  mov     [rsp+420h+KeyHandle], rsi
0x18008519f  mov     r8d, r14d; Size
0x1800851a2  mov     [rsp+420h+var_3F0], rsi
0x1800851a7  xor     edx, edx; Val
0x1800851a9  call    memset
0x1800851ae  mov     r8d, r14d; Size
0x1800851b1  lea     rcx, [rbp+320h+Src]; void *
0x1800851b8  xor     edx, edx; Val
0x1800851ba  call    memset
0x1800851bf  mov     r8d, r14d; Size
0x1800851c2  lea     rcx, [rbp+320h+Str1]; void *
0x1800851c9  xor     edx, edx; Val
0x1800851cb  call    memset
0x1800851d0  mov     [rsp+420h+var_3E8], esi
0x1800851d4  call    FreeExternalSignatureAlgorithms
0x1800851d9  cmp     cs:g_dwSignatureInfoTotalCount, 10h
0x1800851e0  jnb     loc_180085436
0x1800851e6  lea     r8, [rsp+420h+KeyHandle]; KeyHandle
0x1800851eb  xor     edx, edx; PCWSTR
0x1800851ed  lea     rcx, aRegistryMachin_7; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x1800851f4  call    TlsOpenRegKey
0x1800851f9  test    eax, eax
0x1800851fb  js      loc_180085436
0x180085201  mov     edi, esi
0x180085203  jmp     loc_18008541F
0x180085208  xor     edx, edx; Val
0x18008520a  mov     [rsp+420h+KeyInformation], esi
0x18008520e  mov     r8d, 214h; Size
0x180085214  lea     rcx, [rsp+420h+var_3CC]; void *
0x180085219  call    memset
0x18008521e  mov     rcx, [rsp+420h+KeyHandle]; KeyHandle
0x180085223  lea     rax, [rsp+420h+var_3E4]
0x180085228  mov     [rsp+420h+ResultLength], rax; ResultLength
0x18008522d  lea     r9, [rsp+420h+KeyInformation]; KeyInformation
0x180085232  xor     r8d, r8d; KeyInformationClass
0x180085235  mov     [rsp+420h+Length], 218h; Length
0x18008523d  mov     edx, edi; Index
0x18008523f  mov     [rsp+420h+var_3E4], esi
0x180085243  call    cs:__imp_ZwEnumerateKey
0x18008524a  nop     dword ptr [rax+rax+00h]
0x18008524f  test    eax, eax
0x180085251  js      loc_18008542C
0x180085257  lea     rax, [rsp+420h+var_3C0]
0x18008525c  or      r9, 0FFFFFFFFFFFFFFFFh
0x180085260  inc     r9; unsigned __int64
0x180085263  cmp     [rax+r9*2], si
0x180085268  jnz     short loc_180085260
0x18008526a  lea     r8, [rsp+420h+var_3C0]; unsigned __int16 *
0x18008526f  lea     rcx, [rbp+320h+var_130]; unsigned __int16 *
0x180085276  call    ?RtlStringCchCopyNW@@YAJPEAG_KPEBG1@Z; RtlStringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18008527b  test    eax, eax
0x18008527d  js      loc_18008542C
0x180085283  lea     r8, [rsp+420h+var_3F0]; KeyHandle
0x180085288  lea     rdx, [rbp+320h+var_130]; PCWSTR
0x18008528f  lea     rcx, aRegistryMachin_7; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180085296  call    TlsOpenRegKey
0x18008529b  test    eax, eax
0x18008529d  js      loc_18008541D
0x1800852a3  mov     rcx, [rsp+420h+var_3F0]; KeyHandle
0x1800852a8  lea     r8, [rbp+320h+Src]; unsigned __int16 *
0x1800852af  lea     rdx, aCngalgorithm; "CngAlgorithm"
0x1800852b6  call    GetSslStringFromRegistry
0x1800852bb  test    eax, eax
0x1800852bd  js      loc_180085413
0x1800852c3  mov     rcx, [rsp+420h+var_3F0]; KeyHandle
0x1800852c8  lea     r8, [rsp+420h+var_3E8]
0x1800852cd  lea     rdx, aTlscodepoint; "TlsCodePoint"
0x1800852d4  call    GetSslDWordFromRegistry
0x1800852d9  test    eax, eax
0x1800852db  js      loc_180085413
0x1800852e1  mov     rcx, [rsp+420h+var_3F0]; KeyHandle
0x1800852e6  lea     r8, [rbp+320h+Str1]; unsigned __int16 *
0x1800852ed  lea     rdx, aSignaturestyle; "SignatureStyle"
0x1800852f4  call    GetSslStringFromRegistry
0x1800852f9  test    eax, eax
0x1800852fb  js      loc_180085413
0x180085301  lea     rcx, [rsp+420h+var_3F0]
0x180085306  call    TlsCloseRegKey
0x18008530b  mov     ecx, 18h
0x180085310  call    MSCryptAlloc
0x180085315  mov     rbx, rax
0x180085318  test    rax, rax
0x18008531b  jz      loc_18008541D
0x180085321  xorps   xmm0, xmm0
0x180085324  xor     eax, eax
0x180085326  movups  xmmword ptr [rbx], xmm0
0x180085329  mov     rcx, r14
0x18008532c  mov     [rbx+10h], rax
0x180085330  call    MSCryptAlloc
0x180085335  mov     [rbx], rax
0x180085338  test    rax, rax
0x18008533b  jnz     short loc_18008534A
0x18008533d  mov     rcx, rbx; P
0x180085340  call    MSCryptFree
0x180085345  jmp     loc_18008541D
0x18008534a  lea     r8, [rbp+320h+Src]; Src
0x180085351  mov     edx, 40h ; '@'; SizeInWords
0x180085356  mov     rcx, rax; Dst
0x180085359  call    cs:__imp_wcscpy_s
0x180085360  nop     dword ptr [rax+rax+00h]
0x180085365  mov     ecx, cs:g_dwSignatureInfoTotalCount
0x18008536b  lea     rdx, aRsa; "RSA"
0x180085372  lea     eax, [rcx+2FF9h]
0x180085378  mov     [rbx+0Ch], eax
0x18008537b  lea     eax, [rcx-20000006h]
0x180085381  mov     [rbx+8], eax
0x180085384  lea     rcx, [rbp+320h+Str1]; Str1
0x18008538b  mov     eax, [rsp+420h+var_3E8]
0x18008538f  mov     [rbx+10h], eax
0x180085392  call    cs:__imp__wcsicmp
0x180085399  nop     dword ptr [rax+rax+00h]
0x18008539e  test    eax, eax
0x1800853a0  jnz     short loc_1800853AB
0x1800853a2  mov     dword ptr [rbx+14h], 2
0x1800853a9  jmp     short loc_1800853F8
0x1800853ab  lea     rdx, aDsa; "DSA"
0x1800853b2  lea     rcx, [rbp+320h+Str1]; Str1
0x1800853b9  call    cs:__imp__wcsicmp
0x1800853c0  nop     dword ptr [rax+rax+00h]
0x1800853c5  test    eax, eax
0x1800853c7  jnz     short loc_1800853D2
0x1800853c9  mov     dword ptr [rbx+14h], 3
0x1800853d0  jmp     short loc_1800853F8
0x1800853d2  lea     rdx, aEcdsa; "ECDSA"
0x1800853d9  lea     rcx, [rbp+320h+Str1]; Str1
0x1800853e0  call    cs:__imp__wcsicmp
0x1800853e7  nop     dword ptr [rax+rax+00h]
0x1800853ec  neg     eax
0x1800853ee  sbb     ecx, ecx
0x1800853f0  not     ecx
0x1800853f2  and     ecx, 4
0x1800853f5  mov     [rbx+14h], ecx
0x1800853f8  mov     ecx, cs:g_dwSignatureInfoTotalCount
0x1800853fe  lea     rdx, g_pSignatureInfo
0x180085405  mov     [rdx+rcx*8], rbx
0x180085409  inc     ecx
0x18008540b  mov     cs:g_dwSignatureInfoTotalCount, ecx
0x180085411  jmp     short loc_18008541D
0x180085413  lea     rcx, [rsp+420h+var_3F0]
0x180085418  call    TlsCloseRegKey
0x18008541d  inc     edi
0x18008541f  cmp     cs:g_dwSignatureInfoTotalCount, 10h
0x180085426  jb      loc_180085208
0x18008542c  lea     rcx, [rsp+420h+KeyHandle]
0x180085431  call    TlsCloseRegKey
0x180085436  mov     rcx, [rbp+320h+var_30]
0x18008543d  xor     rcx, rsp; StackCookie
0x180085440  call    __security_check_cookie
0x180085445  add     rsp, 400h
0x18008544c  pop     r14
0x18008544e  pop     rdi
0x18008544f  pop     rsi
0x180085450  pop     rbx
0x180085451  pop     rbp
0x180085452  retn
```
