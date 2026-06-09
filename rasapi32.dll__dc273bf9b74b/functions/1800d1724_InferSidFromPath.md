# InferSidFromPath

- ea: `0x1800d1724`
- end: `0x1800d1a63`
- name: `InferSidFromPath`
- size: `831`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800da068`

## callees

- `0x180002418`
- `0x18000b0f4`
- `0x18003e50c`
- `0x18003fa6c`
- `0x180040844`
- `0x18004e580`
- `0x18004e984`
- `0x18004e9ac`
- `0x1800d1724`
- `0x1800ded06`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800d17d9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800d17d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d19a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d1a2b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d19a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d1a2b`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800d192b`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800d192b`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800d1911`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800d1911`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrA` at `0x1800d1780`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrA` at `0x1800d1780`

## string_xrefs

- `0x1800d18e1`: `ProfileImagePath`

## pseudocode

```c
__int64 __fastcall InferSidFromPath(const WCHAR *a1, char **a2)
{
  const CHAR *v3; // rax
  const CHAR *v4; // rbx
  PSTR v5; // rax
  _BYTE *i; // rax
  unsigned int v7; // eax
  unsigned int v8; // edi
  DWORD j; // edi
  unsigned int StringValue; // esi
  char *v12; // rax
  STRSAFE_LPSTR *v13; // r9
  DWORD cchCount2; // [rsp+28h] [rbp-D8h]
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cSubKeys; // [rsp+38h] [rbp-C8h] BYREF
  CHAR String1[256]; // [rsp+40h] [rbp-C0h] BYREF
  char pszSrc[1552]; // [rsp+140h] [rbp+40h] BYREF

  if ( !a1 || !a2 )
    return 87;
  v3 = (const CHAR *)StrDupAFromTInternal(a1);
  v4 = v3;
  if ( !v3 )
    return 8;
  v5 = StrStrA(v3, "\\Users\\");
  if ( !v5 )
    return 635;
  for ( i = v5 + 7; *i != 92 && *i; ++i )
    ;
  if ( !*i )
    return 635;
  *i = 0;
  hKey = 0;
  v7 = RegOpenKeyExA(
         HKEY_LOCAL_MACHINE,
         "SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
         0,
         0x20219u,
         &hKey);
  v8 = v7;
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v7);
    }
    return v8;
  }
  cSubKeys = 0;
  memset_0(pszSrc, 0, 0x601u);
  if ( !(unsigned int)RegGetNumberOfSubkeys(hKey, &cSubKeys) )
  {
    for ( j = 0; ; ++j )
    {
      if ( j >= cSubKeys )
      {
        Free0(v4);
        RegCloseKey(hKey);
        return 635;
      }
      if ( !(unsigned int)RegGetIthSectionName(hKey, j, pszSrc) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids);
        }
        return 635;
      }
      memset_0(String1, 0, sizeof(String1));
      StringValue = RegReadStringValue(hKey, "ProfileImagePath", String1, pszSrc, 0x100u);
      if ( StringValue )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            23,
            WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids,
            StringValue);
        }
        return StringValue;
      }
      if ( CompareStringA(0x7Fu, 1u, String1, -1, v4, -1) == 2 )
        break;
    }
    v12 = (char *)GlobalAlloc(0x40u, 0x100u);
    *a2 = v12;
    if ( v12 )
    {
      StringCchCopyExA(v12, 0x100u, pszSrc, v13, 0, cchCount2);
      Free0(v4);
      RegCloseKey(hKey);
      return 0;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, 8);
    }
    return 8;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, 1);
  }
  return 1;
}

```

## disassembly

```asm
0x1800d1724  mov     [rsp-8+arg_10], rbx
0x1800d1729  push    rbp
0x1800d172a  push    rsi
0x1800d172b  push    rdi
0x1800d172c  push    r13
0x1800d172e  push    r14
0x1800d1730  lea     rbp, [rsp-660h]
0x1800d1738  sub     rsp, 760h
0x1800d173f  mov     rax, cs:__security_cookie
0x1800d1746  xor     rax, rsp
0x1800d1749  mov     [rbp+680h+var_30], rax
0x1800d1750  mov     r14, rdx
0x1800d1753  test    rcx, rcx
0x1800d1756  jz      loc_1800D1A38
0x1800d175c  test    rdx, rdx
0x1800d175f  jz      loc_1800D1A38
0x1800d1765  call    StrDupAFromTInternal
0x1800d176a  mov     rbx, rax
0x1800d176d  test    rax, rax
0x1800d1770  jz      loc_1800D1971
0x1800d1776  lea     rdx, aUsers; "\\Users\\"
0x1800d177d  mov     rcx, rax; pszFirst
0x1800d1780  call    cs:__imp_StrStrA
0x1800d1786  test    rax, rax
0x1800d1789  jz      loc_1800D1A31
0x1800d178f  add     rax, 7
0x1800d1793  jmp     short loc_1800D179C
0x1800d1795  test    cl, cl
0x1800d1797  jz      short loc_1800D17A3
0x1800d1799  inc     rax
0x1800d179c  mov     cl, [rax]
0x1800d179e  cmp     cl, 5Ch ; '\'
0x1800d17a1  jnz     short loc_1800D1795
0x1800d17a3  cmp     byte ptr [rax], 0
0x1800d17a6  jz      loc_1800D1A31
0x1800d17ac  mov     byte ptr [rax], 0
0x1800d17af  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800d17b6  lea     rax, [rsp+780h+hKey]
0x1800d17bb  mov     [rsp+780h+hKey], 0
0x1800d17c4  mov     r9d, 20219h; samDesired
0x1800d17ca  mov     [rsp+780h+phkResult], rax; phkResult
0x1800d17cf  xor     r8d, r8d; ulOptions
0x1800d17d2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d17d9  call    cs:__imp_RegOpenKeyExA
0x1800d17df  mov     edi, eax
0x1800d17e1  test    eax, eax
0x1800d17e3  jz      short loc_1800D1825
0x1800d17e5  mov     r10, cs:WPP_GLOBAL_Control
0x1800d17ec  lea     rcx, WPP_GLOBAL_Control
0x1800d17f3  cmp     r10, rcx
0x1800d17f6  jz      short loc_1800D181E
0x1800d17f8  test    byte ptr [r10+1Ch], 80h
0x1800d17fd  jz      short loc_1800D181E
0x1800d17ff  cmp     byte ptr [r10+19h], 2
0x1800d1804  jb      short loc_1800D181E
0x1800d1806  mov     rcx, [r10+10h]
0x1800d180a  lea     r8, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids
0x1800d1811  mov     edx, 14h
0x1800d1816  mov     r9d, eax
0x1800d1819  call    WPP_SF_d
0x1800d181e  mov     eax, edi
0x1800d1820  jmp     loc_1800D1A3D
0x1800d1825  xor     edx, edx; Val
0x1800d1827  mov     [rsp+780h+cSubKeys], 0
0x1800d182f  mov     r8d, 601h; Size
0x1800d1835  lea     rcx, [rbp+680h+pszSrc]; void *
0x1800d1839  call    memset_0
0x1800d183e  mov     rcx, [rsp+780h+hKey]; hKey
0x1800d1843  lea     rdx, [rsp+780h+cSubKeys]; lpcSubKeys
0x1800d1848  call    RegGetNumberOfSubkeys
0x1800d184d  test    eax, eax
0x1800d184f  jz      short loc_1800D1895
0x1800d1851  mov     r10, cs:WPP_GLOBAL_Control
0x1800d1858  lea     rcx, WPP_GLOBAL_Control
0x1800d185f  cmp     r10, rcx
0x1800d1862  jz      short loc_1800D188B
0x1800d1864  test    byte ptr [r10+1Ch], 80h
0x1800d1869  jz      short loc_1800D188B
0x1800d186b  cmp     byte ptr [r10+19h], 2
0x1800d1870  jb      short loc_1800D188B
0x1800d1872  mov     rcx, [r10+10h]
0x1800d1876  lea     r8, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids
0x1800d187d  mov     edx, 15h
0x1800d1882  lea     r9d, [rdx-14h]
0x1800d1886  call    WPP_SF_d
0x1800d188b  mov     eax, 1
0x1800d1890  jmp     loc_1800D1A3D
0x1800d1895  xor     edi, edi
0x1800d1897  mov     r13d, 100h
0x1800d189d  cmp     edi, [rsp+780h+cSubKeys]
0x1800d18a1  jnb     loc_1800D1A1E
0x1800d18a7  mov     rcx, [rsp+780h+hKey]
0x1800d18ac  lea     r8, [rbp+680h+pszSrc]
0x1800d18b0  mov     edx, edi
0x1800d18b2  call    RegGetIthSectionName
0x1800d18b7  test    eax, eax
0x1800d18b9  jz      loc_1800D19E8
0x1800d18bf  mov     r8, r13; Size
0x1800d18c2  lea     rcx, [rsp+780h+String1]; void *
0x1800d18c7  xor     edx, edx; Val
0x1800d18c9  call    memset_0
0x1800d18ce  mov     rcx, [rsp+780h+hKey]; hkey
0x1800d18d3  lea     r9, [rbp+680h+pszSrc]; lpSubKey
0x1800d18d7  lea     r8, [rsp+780h+String1]; pvData
0x1800d18dc  mov     dword ptr [rsp+780h+phkResult], r13d; DWORD
0x1800d18e1  lea     rdx, aProfileimagepa; "ProfileImagePath"
0x1800d18e8  call    RegReadStringValue
0x1800d18ed  mov     esi, eax
0x1800d18ef  test    eax, eax
0x1800d18f1  jnz     loc_1800D19AD
0x1800d18f7  or      esi, 0FFFFFFFFh
0x1800d18fa  lea     r8, [rsp+780h+String1]; lpString1
0x1800d18ff  mov     [rsp+780h+cchCount2], esi; dwFlags
0x1800d1903  lea     edx, [rax+1]; dwCmpFlags
0x1800d1906  mov     r9d, esi; cchCount1
0x1800d1909  mov     [rsp+780h+phkResult], rbx; lpString2
0x1800d190e  lea     ecx, [rax+7Fh]; Locale
0x1800d1911  call    cs:__imp_CompareStringA
0x1800d1917  cmp     eax, 2
0x1800d191a  jz      short loc_1800D1923
0x1800d191c  inc     edi
0x1800d191e  jmp     loc_1800D189D
0x1800d1923  mov     rdx, r13; dwBytes
0x1800d1926  mov     ecx, 40h ; '@'; uFlags
0x1800d192b  call    cs:__imp_GlobalAlloc
0x1800d1931  mov     [r14], rax
0x1800d1934  test    rax, rax
0x1800d1937  jnz     short loc_1800D197B
0x1800d1939  mov     rax, cs:WPP_GLOBAL_Control
0x1800d1940  lea     rcx, WPP_GLOBAL_Control
0x1800d1947  cmp     rax, rcx
0x1800d194a  jz      short loc_1800D1971
0x1800d194c  test    byte ptr [rax+1Ch], 80h
0x1800d1950  jz      short loc_1800D1971
0x1800d1952  cmp     byte ptr [rax+19h], 2
0x1800d1956  jb      short loc_1800D1971
0x1800d1958  mov     rcx, [rax+10h]
0x1800d195c  lea     r8, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids
0x1800d1963  mov     edx, 18h
0x1800d1968  lea     r9d, [rdx-10h]
0x1800d196c  call    WPP_SF_d
0x1800d1971  mov     eax, 8
0x1800d1976  jmp     loc_1800D1A3D
0x1800d197b  lea     r8, [rbp+680h+pszSrc]; pszSrc
0x1800d197f  mov     [rsp+780h+phkResult], 0; pcchRemaining
0x1800d1988  mov     rdx, r13; cchDest
0x1800d198b  mov     rcx, rax; pszDest
0x1800d198e  call    StringCchCopyExA
0x1800d1993  mov     rcx, rbx
0x1800d1996  call    Free0
0x1800d199b  mov     rcx, [rsp+780h+hKey]; hKey
0x1800d19a0  call    cs:__imp_RegCloseKey
0x1800d19a6  xor     eax, eax
0x1800d19a8  jmp     loc_1800D1A3D
0x1800d19ad  mov     rax, cs:WPP_GLOBAL_Control
0x1800d19b4  lea     rcx, WPP_GLOBAL_Control
0x1800d19bb  cmp     rax, rcx
0x1800d19be  jz      short loc_1800D19E4
0x1800d19c0  test    byte ptr [rax+1Ch], 80h
0x1800d19c4  jz      short loc_1800D19E4
0x1800d19c6  cmp     byte ptr [rax+19h], 2
0x1800d19ca  jb      short loc_1800D19E4
0x1800d19cc  mov     rcx, [rax+10h]
0x1800d19d0  lea     r8, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids
0x1800d19d7  mov     edx, 17h
0x1800d19dc  mov     r9d, esi
0x1800d19df  call    WPP_SF_d
0x1800d19e4  mov     eax, esi
0x1800d19e6  jmp     short loc_1800D1A3D
0x1800d19e8  mov     rax, cs:WPP_GLOBAL_Control
0x1800d19ef  lea     rcx, WPP_GLOBAL_Control
0x1800d19f6  cmp     rax, rcx
0x1800d19f9  jz      short loc_1800D1A31
0x1800d19fb  test    byte ptr [rax+1Ch], 80h
0x1800d19ff  jz      short loc_1800D1A31
0x1800d1a01  cmp     byte ptr [rax+19h], 6
0x1800d1a05  jb      short loc_1800D1A31
0x1800d1a07  mov     rcx, [rax+10h]
0x1800d1a0b  lea     r8, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids
0x1800d1a12  mov     edx, 16h
0x1800d1a17  call    WPP_SF_
0x1800d1a1c  jmp     short loc_1800D1A31
0x1800d1a1e  mov     rcx, rbx
0x1800d1a21  call    Free0
0x1800d1a26  mov     rcx, [rsp+780h+hKey]; hKey
0x1800d1a2b  call    cs:__imp_RegCloseKey
0x1800d1a31  mov     eax, 27Bh
0x1800d1a36  jmp     short loc_1800D1A3D
0x1800d1a38  mov     eax, 57h ; 'W'
0x1800d1a3d  mov     rcx, [rbp+680h+var_30]
0x1800d1a44  xor     rcx, rsp; StackCookie
0x1800d1a47  call    __security_check_cookie
0x1800d1a4c  mov     rbx, [rsp+780h+arg_10]
0x1800d1a54  add     rsp, 760h
0x1800d1a5b  pop     r14
0x1800d1a5d  pop     r13
0x1800d1a5f  pop     rdi
0x1800d1a60  pop     rsi
0x1800d1a61  pop     rbp
0x1800d1a62  retn
```
