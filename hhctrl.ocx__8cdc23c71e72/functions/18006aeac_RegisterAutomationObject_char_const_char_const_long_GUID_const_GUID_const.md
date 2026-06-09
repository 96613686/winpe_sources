# RegisterAutomationObject(char const *,char const *,long,_GUID const &,_GUID const &)

- ea: `0x18006aeac`
- end: `0x18006b5f1`
- name: `?RegisterAutomationObject@@YAHPEBD0JAEBU_GUID@@1@Z`
- size: `1861`
- prototype: `int(const char *, const char *, int, const struct _GUID *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004040c`
- `0x18006b5f8`

## callees

- `0x1800029b8`
- `0x1800095c8`
- `0x18000f460`
- `0x18006aeac`
- `0x18006ba44`
- `0x18006bf3c`
- `0x180075c90`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18006b0c0`
- `ADVAPI32!RegCloseKey` at `0x18006b17b`
- `ADVAPI32!RegCloseKey` at `0x18006b186`
- `ADVAPI32!RegCloseKey` at `0x18006b2cc`
- `ADVAPI32!RegCloseKey` at `0x18006b2d7`
- `ADVAPI32!RegCloseKey` at `0x18006b442`
- `ADVAPI32!RegCloseKey` at `0x18006b4f9`
- `ADVAPI32!RegCloseKey` at `0x18006b58d`
- `ADVAPI32!RegCloseKey` at `0x18006b598`
- `ADVAPI32!RegCloseKey` at `0x18006b5af`
- `ADVAPI32!RegCloseKey` at `0x18006b5bf`
- `ADVAPI32!RegCloseKey` at `0x18006b0c0`
- `ADVAPI32!RegCloseKey` at `0x18006b17b`
- `ADVAPI32!RegCloseKey` at `0x18006b186`
- `ADVAPI32!RegCloseKey` at `0x18006b2cc`
- `ADVAPI32!RegCloseKey` at `0x18006b2d7`
- `ADVAPI32!RegCloseKey` at `0x18006b442`
- `ADVAPI32!RegCloseKey` at `0x18006b4f9`
- `ADVAPI32!RegCloseKey` at `0x18006b58d`
- `ADVAPI32!RegCloseKey` at `0x18006b598`
- `ADVAPI32!RegCloseKey` at `0x18006b5af`
- `ADVAPI32!RegCloseKey` at `0x18006b5bf`
- `ADVAPI32!RegCreateKeyExA` at `0x18006af9c`
- `ADVAPI32!RegCreateKeyExA` at `0x18006b05c`
- `ADVAPI32!RegCreateKeyExA` at `0x18006b102`
- `ADVAPI32!RegCreateKeyExA` at `0x18006b1c7`
- `ADVAPI32!RegCreateKeyExA` at `0x18006b27d`
- `ADVAPI32!RegCreateKeyExA` at `0x18006b362`
- `ADVAPI32!RegCreateKeyExA` at `0x18006b3a8`
- `ADVAPI32!RegCreateKeyExA` at `0x18006b480`
- `ADVAPI32!RegCreateKeyExA` at `0x18006b537`
- `ADVAPI32!RegCreateKeyExA` at `0x18006af9c`
- `ADVAPI32!RegCreateKeyExA` at `0x18006b05c`
- `ADVAPI32!RegCreateKeyExA` at `0x18006b102`
- `ADVAPI32!RegCreateKeyExA` at `0x18006b1c7`
- `ADVAPI32!RegCreateKeyExA` at `0x18006b27d`
- `ADVAPI32!RegCreateKeyExA` at `0x18006b362`
- `ADVAPI32!RegCreateKeyExA` at `0x18006b3a8`
- `ADVAPI32!RegCreateKeyExA` at `0x18006b480`
- `ADVAPI32!RegCreateKeyExA` at `0x18006b537`
- `ADVAPI32!RegSetValueExA` at `0x18006b012`
- `ADVAPI32!RegSetValueExA` at `0x18006b0ad`
- `ADVAPI32!RegSetValueExA` at `0x18006b168`
- `ADVAPI32!RegSetValueExA` at `0x18006b233`
- `ADVAPI32!RegSetValueExA` at `0x18006b2b9`
- `ADVAPI32!RegSetValueExA` at `0x18006b42f`
- `ADVAPI32!RegSetValueExA` at `0x18006b4e6`
- `ADVAPI32!RegSetValueExA` at `0x18006b57e`
- `ADVAPI32!RegSetValueExA` at `0x18006b012`
- `ADVAPI32!RegSetValueExA` at `0x18006b0ad`
- `ADVAPI32!RegSetValueExA` at `0x18006b168`
- `ADVAPI32!RegSetValueExA` at `0x18006b233`
- `ADVAPI32!RegSetValueExA` at `0x18006b2b9`
- `ADVAPI32!RegSetValueExA` at `0x18006b42f`
- `ADVAPI32!RegSetValueExA` at `0x18006b4e6`
- `ADVAPI32!RegSetValueExA` at `0x18006b57e`

## string_xrefs

- `0x18006b043`: `CLSID`
- `0x18006b264`: `CLSID`
- `0x18006b2f2`: `CLSID\`

## pseudocode

```c
__int64 __fastcall RegisterAutomationObject(
        const char *a1,
        const char *a2,
        int a3,
        const struct _GUID *a4,
        const struct _GUID *a5)
{
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  DWORD dwDisposition; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  BYTE Data[40]; // [rsp+68h] [rbp-98h] BYREF
  CHAR SubKey[272]; // [rsp+90h] [rbp-70h] BYREF

  hKey = 0;
  phkResult = 0;
  dwDisposition = 0;
  if ( (unsigned int)RegisterUnknownObject(a2, a5) )
  {
    if ( StringCchCopyA(SubKey, 0x104u, "Internet") >= 0
      && (int)StringCchCatA(SubKey, 0x104u, ".") >= 0
      && (int)StringCchCatA(SubKey, 0x104u, a2) >= 0
      && !RegCreateKeyExA(HKEY_CLASSES_ROOT, SubKey, 0, (LPSTR)Class, 0, 0x2001Fu, 0, &hKey, &dwDisposition)
      && StringCchCopyA(SubKey, 0x104u, a2) >= 0
      && (int)StringCchCatA(SubKey, 0x104u, " Object") >= 0 )
    {
      v7 = -1;
      v8 = -1;
      do
        ++v8;
      while ( SubKey[v8] );
      if ( !RegSetValueExA(hKey, 0, 0, 1u, (const BYTE *)SubKey, v8 + 1)
        && !RegCreateKeyExA(hKey, "CLSID", 0, (LPSTR)Class, 0, 0x2001Fu, 0, &phkResult, &dwDisposition) )
      {
        if ( StringFromGuidA(a5, (char *)Data) )
        {
          v9 = -1;
          do
            ++v9;
          while ( Data[v9] );
          if ( !RegSetValueExA(phkResult, 0, 0, 1u, Data, v9 + 1) )
          {
            RegCloseKey(phkResult);
            if ( !RegCreateKeyExA(hKey, "CurVer", 0, (LPSTR)Class, 0, 0x2001Fu, 0, &phkResult, &dwDisposition)
              && (int)StringCchPrintfA(SubKey, 0x104u, "%s.%s.%ld", "Internet", a2, a3) >= 0 )
            {
              v10 = -1;
              do
                ++v10;
              while ( SubKey[v10] );
              if ( !RegSetValueExA(phkResult, 0, 0, 1u, (const BYTE *)SubKey, v10 + 1) )
              {
                RegCloseKey(phkResult);
                RegCloseKey(hKey);
                if ( !RegCreateKeyExA(HKEY_CLASSES_ROOT, SubKey, 0, (LPSTR)Class, 0, 0x2001Fu, 0, &hKey, &dwDisposition)
                  && StringCchCopyA(SubKey, 0x104u, a2) >= 0
                  && (int)StringCchCatA(SubKey, 0x104u, " Object") >= 0 )
                {
                  v11 = -1;
                  do
                    ++v11;
                  while ( SubKey[v11] );
                  if ( !RegSetValueExA(hKey, 0, 0, 1u, (const BYTE *)SubKey, v11 + 1)
                    && !RegCreateKeyExA(hKey, "CLSID", 0, (LPSTR)Class, 0, 0x2001Fu, 0, &phkResult, &dwDisposition) )
                  {
                    v12 = -1;
                    do
                      ++v12;
                    while ( Data[v12] );
                    if ( !RegSetValueExA(phkResult, 0, 0, 1u, Data, v12 + 1) )
                    {
                      RegCloseKey(phkResult);
                      RegCloseKey(hKey);
                      if ( StringFromGuidA(a5, (char *)Data) )
                      {
                        if ( StringCchCopyA(SubKey, 0x104u, "CLSID\\") >= 0
                          && (int)StringCchCatA(SubKey, 0x104u, (const char *)Data) >= 0
                          && !RegCreateKeyExA(
                                HKEY_CLASSES_ROOT,
                                SubKey,
                                0,
                                (LPSTR)Class,
                                0,
                                0x2001Fu,
                                0,
                                &hKey,
                                &dwDisposition)
                          && !RegCreateKeyExA(
                                hKey,
                                "VersionIndependentProgID",
                                0,
                                (LPSTR)Class,
                                0,
                                0x2001Fu,
                                0,
                                &phkResult,
                                &dwDisposition)
                          && StringCchCopyA(SubKey, 0x104u, "Internet") >= 0
                          && (int)StringCchCatA(SubKey, 0x104u, ".") >= 0
                          && (int)StringCchCatA(SubKey, 0x104u, a2) >= 0 )
                        {
                          v13 = -1;
                          do
                            ++v13;
                          while ( SubKey[v13] );
                          if ( !RegSetValueExA(phkResult, 0, 0, 1u, (const BYTE *)SubKey, v13 + 1) )
                          {
                            RegCloseKey(phkResult);
                            if ( !RegCreateKeyExA(
                                    hKey,
                                    "ProgID",
                                    0,
                                    (LPSTR)Class,
                                    0,
                                    0x2001Fu,
                                    0,
                                    &phkResult,
                                    &dwDisposition)
                              && (int)StringCchPrintfA(SubKey, 0x104u, "%s.%s.%ld", "Internet", a2, a3) >= 0 )
                            {
                              v14 = -1;
                              do
                                ++v14;
                              while ( SubKey[v14] );
                              if ( !RegSetValueExA(phkResult, 0, 0, 1u, (const BYTE *)SubKey, v14 + 1) )
                              {
                                RegCloseKey(phkResult);
                                RegCreateKeyExA(
                                  hKey,
                                  "TypeLib",
                                  0,
                                  (LPSTR)Class,
                                  0,
                                  0x2001Fu,
                                  0,
                                  &phkResult,
                                  &dwDisposition);
                                if ( StringFromGuidA(&LIBID_HHCTRLLib, (char *)Data) )
                                {
                                  do
                                    ++v7;
                                  while ( Data[v7] );
                                  if ( !RegSetValueExA(phkResult, 0, 0, 1u, Data, v7 + 1) )
                                  {
                                    RegCloseKey(phkResult);
                                    RegCloseKey(hKey);
                                    return 1;
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    if ( hKey )
    {
      RegCloseKey(phkResult);
      if ( hKey )
        RegCloseKey(hKey);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18006aeac  mov     [rsp-8+arg_0], rbx
0x18006aeb1  push    rbp
0x18006aeb2  push    rsi
0x18006aeb3  push    rdi
0x18006aeb4  push    r12
0x18006aeb6  push    r13
0x18006aeb8  push    r14
0x18006aeba  push    r15
0x18006aebc  lea     rbp, [rsp-0B0h]
0x18006aec4  sub     rsp, 1B0h
0x18006aecb  mov     rax, cs:__security_cookie
0x18006aed2  xor     rax, rsp
0x18006aed5  mov     [rbp+0E0h+var_40], rax
0x18006aedc  mov     rsi, [rbp+0E0h+arg_20]
0x18006aee3  mov     rdi, rdx
0x18006aee6  xor     r15d, r15d
0x18006aee9  mov     rdx, rsi; struct _GUID *
0x18006aeec  mov     rcx, rdi; char *
0x18006aeef  mov     [rsp+1E0h+hKey], r15
0x18006aef4  mov     r14d, r8d
0x18006aef7  mov     [rsp+1E0h+var_188], r15
0x18006aefc  mov     [rsp+1E0h+dwDisposition], r15d
0x18006af01  call    ?RegisterUnknownObject@@YAHPEBDAEBU_GUID@@@Z; RegisterUnknownObject(char const *,_GUID const &)
0x18006af06  test    eax, eax
0x18006af08  jz      loc_18006B5C5
0x18006af0e  mov     r12d, 104h
0x18006af14  lea     r8, ?g_szLibName@@3QBDB; "Internet"
0x18006af1b  mov     edx, r12d; unsigned __int64
0x18006af1e  lea     rcx, [rbp+0E0h+SubKey]; char *
0x18006af22  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18006af27  test    eax, eax
0x18006af29  js      loc_18006B5A3
0x18006af2f  lea     r8, asc_18007FE14; "."
0x18006af36  mov     edx, r12d; unsigned __int64
0x18006af39  lea     rcx, [rbp+0E0h+SubKey]; char *
0x18006af3d  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18006af42  test    eax, eax
0x18006af44  js      loc_18006B5A3
0x18006af4a  mov     r8, rdi; char *
0x18006af4d  lea     rcx, [rbp+0E0h+SubKey]; char *
0x18006af51  mov     edx, r12d; unsigned __int64
0x18006af54  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18006af59  test    eax, eax
0x18006af5b  js      loc_18006B5A3
0x18006af61  lea     rax, [rsp+1E0h+dwDisposition]
0x18006af66  xor     r8d, r8d; Reserved
0x18006af69  mov     [rsp+1E0h+lpdwDisposition], rax; lpdwDisposition
0x18006af6e  lea     r9, Class; lpClass
0x18006af75  lea     rax, [rsp+1E0h+hKey]
0x18006af7a  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18006af81  mov     [rsp+1E0h+phkResult], rax; phkResult
0x18006af86  lea     rdx, [rbp+0E0h+SubKey]; lpSubKey
0x18006af8a  mov     [rsp+1E0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18006af8f  mov     [rsp+1E0h+samDesired], 2001Fh; samDesired
0x18006af97  mov     [rsp+1E0h+dwOptions], r15d; dwOptions
0x18006af9c  call    cs:__imp_RegCreateKeyExA
0x18006afa2  test    eax, eax
0x18006afa4  jnz     loc_18006B5A3
0x18006afaa  mov     r8, rdi; char *
0x18006afad  lea     rcx, [rbp+0E0h+SubKey]; char *
0x18006afb1  mov     edx, r12d; unsigned __int64
0x18006afb4  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18006afb9  test    eax, eax
0x18006afbb  js      loc_18006B5A3
0x18006afc1  lea     r8, aObject; " Object"
0x18006afc8  mov     edx, r12d; unsigned __int64
0x18006afcb  lea     rcx, [rbp+0E0h+SubKey]; char *
0x18006afcf  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18006afd4  test    eax, eax
0x18006afd6  js      loc_18006B5A3
0x18006afdc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18006afe0  lea     rcx, [rbp+0E0h+SubKey]
0x18006afe4  mov     rax, rbx
0x18006afe7  inc     rax
0x18006afea  cmp     [rcx+rax], r15b
0x18006afee  jnz     short loc_18006AFE7
0x18006aff0  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18006aff5  inc     eax
0x18006aff7  mov     [rsp+1E0h+samDesired], eax; cbData
0x18006affb  mov     r13d, 1
0x18006b001  lea     rax, [rbp+0E0h+SubKey]
0x18006b005  mov     r9d, r13d; dwType
0x18006b008  xor     r8d, r8d; Reserved
0x18006b00b  mov     qword ptr [rsp+1E0h+dwOptions], rax; lpData
0x18006b010  xor     edx, edx; lpValueName
0x18006b012  call    cs:__imp_RegSetValueExA
0x18006b018  test    eax, eax
0x18006b01a  jnz     loc_18006B5A3
0x18006b020  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18006b025  lea     rax, [rsp+1E0h+dwDisposition]
0x18006b02a  mov     [rsp+1E0h+lpdwDisposition], rax; lpdwDisposition
0x18006b02f  lea     r9, Class; lpClass
0x18006b036  lea     rax, [rsp+1E0h+var_188]
0x18006b03b  xor     r8d, r8d; Reserved
0x18006b03e  mov     [rsp+1E0h+phkResult], rax; phkResult
0x18006b043  lea     rdx, aClsid; "CLSID"
0x18006b04a  mov     [rsp+1E0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18006b04f  mov     [rsp+1E0h+samDesired], 2001Fh; samDesired
0x18006b057  mov     [rsp+1E0h+dwOptions], r15d; dwOptions
0x18006b05c  call    cs:__imp_RegCreateKeyExA
0x18006b062  test    eax, eax
0x18006b064  jnz     loc_18006B5A3
0x18006b06a  lea     rdx, [rsp+1E0h+Data]; char *
0x18006b06f  mov     rcx, rsi; struct _GUID *
0x18006b072  call    ?StringFromGuidA@@YAHAEBU_GUID@@PEAD@Z; StringFromGuidA(_GUID const &,char *)
0x18006b077  test    eax, eax
0x18006b079  jz      loc_18006B5A3
0x18006b07f  lea     rcx, [rsp+1E0h+Data]
0x18006b084  mov     rax, rbx
0x18006b087  inc     rax
0x18006b08a  cmp     [rcx+rax], r15b
0x18006b08e  jnz     short loc_18006B087
0x18006b090  mov     rcx, [rsp+1E0h+var_188]; hKey
0x18006b095  inc     eax
0x18006b097  mov     [rsp+1E0h+samDesired], eax; cbData
0x18006b09b  mov     r9d, r13d; dwType
0x18006b09e  lea     rax, [rsp+1E0h+Data]
0x18006b0a3  xor     r8d, r8d; Reserved
0x18006b0a6  xor     edx, edx; lpValueName
0x18006b0a8  mov     qword ptr [rsp+1E0h+dwOptions], rax; lpData
0x18006b0ad  call    cs:__imp_RegSetValueExA
0x18006b0b3  test    eax, eax
0x18006b0b5  jnz     loc_18006B5A3
0x18006b0bb  mov     rcx, [rsp+1E0h+var_188]; hKey
0x18006b0c0  call    cs:__imp_RegCloseKey
0x18006b0c6  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18006b0cb  lea     rax, [rsp+1E0h+dwDisposition]
0x18006b0d0  mov     [rsp+1E0h+lpdwDisposition], rax; lpdwDisposition
0x18006b0d5  lea     r9, Class; lpClass
0x18006b0dc  lea     rax, [rsp+1E0h+var_188]
0x18006b0e1  xor     r8d, r8d; Reserved
0x18006b0e4  mov     [rsp+1E0h+phkResult], rax; phkResult
0x18006b0e9  lea     rdx, aCurver; "CurVer"
0x18006b0f0  mov     [rsp+1E0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18006b0f5  mov     [rsp+1E0h+samDesired], 2001Fh; samDesired
0x18006b0fd  mov     [rsp+1E0h+dwOptions], r15d; dwOptions
0x18006b102  call    cs:__imp_RegCreateKeyExA
0x18006b108  test    eax, eax
0x18006b10a  jnz     loc_18006B5A3
0x18006b110  mov     [rsp+1E0h+samDesired], r14d
0x18006b115  lea     r9, ?g_szLibName@@3QBDB; "Internet"
0x18006b11c  lea     r8, aSSLd; "%s.%s.%ld"
0x18006b123  mov     qword ptr [rsp+1E0h+dwOptions], rdi
0x18006b128  mov     rdx, r12; unsigned __int64
0x18006b12b  lea     rcx, [rbp+0E0h+SubKey]; char *
0x18006b12f  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18006b134  test    eax, eax
0x18006b136  js      loc_18006B5A3
0x18006b13c  lea     rcx, [rbp+0E0h+SubKey]
0x18006b140  mov     rax, rbx
0x18006b143  inc     rax
0x18006b146  cmp     [rcx+rax], r15b
0x18006b14a  jnz     short loc_18006B143
0x18006b14c  mov     rcx, [rsp+1E0h+var_188]; hKey
0x18006b151  inc     eax
0x18006b153  mov     [rsp+1E0h+samDesired], eax; cbData
0x18006b157  mov     r9d, r13d; dwType
0x18006b15a  lea     rax, [rbp+0E0h+SubKey]
0x18006b15e  xor     r8d, r8d; Reserved
0x18006b161  xor     edx, edx; lpValueName
0x18006b163  mov     qword ptr [rsp+1E0h+dwOptions], rax; lpData
0x18006b168  call    cs:__imp_RegSetValueExA
0x18006b16e  test    eax, eax
0x18006b170  jnz     loc_18006B5A3
0x18006b176  mov     rcx, [rsp+1E0h+var_188]; hKey
0x18006b17b  call    cs:__imp_RegCloseKey
0x18006b181  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18006b186  call    cs:__imp_RegCloseKey
0x18006b18c  lea     rax, [rsp+1E0h+dwDisposition]
0x18006b191  xor     r8d, r8d; Reserved
0x18006b194  mov     [rsp+1E0h+lpdwDisposition], rax; lpdwDisposition
0x18006b199  lea     r9, Class; lpClass
0x18006b1a0  lea     rax, [rsp+1E0h+hKey]
0x18006b1a5  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18006b1ac  mov     [rsp+1E0h+phkResult], rax; phkResult
0x18006b1b1  lea     rdx, [rbp+0E0h+SubKey]; lpSubKey
0x18006b1b5  mov     [rsp+1E0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18006b1ba  mov     [rsp+1E0h+samDesired], 2001Fh; samDesired
0x18006b1c2  mov     [rsp+1E0h+dwOptions], r15d; dwOptions
0x18006b1c7  call    cs:__imp_RegCreateKeyExA
0x18006b1cd  test    eax, eax
0x18006b1cf  jnz     loc_18006B5A3
0x18006b1d5  mov     r8, rdi; char *
0x18006b1d8  lea     rcx, [rbp+0E0h+SubKey]; char *
0x18006b1dc  mov     rdx, r12; unsigned __int64
0x18006b1df  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18006b1e4  test    eax, eax
0x18006b1e6  js      loc_18006B5A3
0x18006b1ec  lea     r8, aObject; " Object"
0x18006b1f3  mov     rdx, r12; unsigned __int64
0x18006b1f6  lea     rcx, [rbp+0E0h+SubKey]; char *
0x18006b1fa  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18006b1ff  test    eax, eax
0x18006b201  js      loc_18006B5A3
0x18006b207  lea     rcx, [rbp+0E0h+SubKey]
0x18006b20b  mov     rax, rbx
0x18006b20e  inc     rax
0x18006b211  cmp     [rcx+rax], r15b
0x18006b215  jnz     short loc_18006B20E
0x18006b217  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18006b21c  inc     eax
0x18006b21e  mov     [rsp+1E0h+samDesired], eax; cbData
0x18006b222  mov     r9d, r13d; dwType
0x18006b225  lea     rax, [rbp+0E0h+SubKey]
0x18006b229  xor     r8d, r8d; Reserved
0x18006b22c  xor     edx, edx; lpValueName
0x18006b22e  mov     qword ptr [rsp+1E0h+dwOptions], rax; lpData
0x18006b233  call    cs:__imp_RegSetValueExA
0x18006b239  test    eax, eax
0x18006b23b  jnz     loc_18006B5A3
0x18006b241  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18006b246  lea     rax, [rsp+1E0h+dwDisposition]
0x18006b24b  mov     [rsp+1E0h+lpdwDisposition], rax; lpdwDisposition
0x18006b250  lea     r9, Class; lpClass
0x18006b257  lea     rax, [rsp+1E0h+var_188]
0x18006b25c  xor     r8d, r8d; Reserved
0x18006b25f  mov     [rsp+1E0h+phkResult], rax; phkResult
0x18006b264  lea     rdx, aClsid; "CLSID"
0x18006b26b  mov     [rsp+1E0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18006b270  mov     [rsp+1E0h+samDesired], 2001Fh; samDesired
0x18006b278  mov     [rsp+1E0h+dwOptions], r15d; dwOptions
0x18006b27d  call    cs:__imp_RegCreateKeyExA
0x18006b283  test    eax, eax
0x18006b285  jnz     loc_18006B5A3
0x18006b28b  lea     rcx, [rsp+1E0h+Data]
0x18006b290  mov     rax, rbx
0x18006b293  inc     rax
0x18006b296  cmp     [rcx+rax], r15b
0x18006b29a  jnz     short loc_18006B293
0x18006b29c  mov     rcx, [rsp+1E0h+var_188]; hKey
0x18006b2a1  inc     eax
0x18006b2a3  mov     [rsp+1E0h+samDesired], eax; cbData
0x18006b2a7  mov     r9d, r13d; dwType
0x18006b2aa  lea     rax, [rsp+1E0h+Data]
0x18006b2af  xor     r8d, r8d; Reserved
0x18006b2b2  xor     edx, edx; lpValueName
0x18006b2b4  mov     qword ptr [rsp+1E0h+dwOptions], rax; lpData
0x18006b2b9  call    cs:__imp_RegSetValueExA
0x18006b2bf  test    eax, eax
0x18006b2c1  jnz     loc_18006B5A3
0x18006b2c7  mov     rcx, [rsp+1E0h+var_188]; hKey
0x18006b2cc  call    cs:__imp_RegCloseKey
0x18006b2d2  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18006b2d7  call    cs:__imp_RegCloseKey
0x18006b2dd  lea     rdx, [rsp+1E0h+Data]; char *
0x18006b2e2  mov     rcx, rsi; struct _GUID *
0x18006b2e5  call    ?StringFromGuidA@@YAHAEBU_GUID@@PEAD@Z; StringFromGuidA(_GUID const &,char *)
0x18006b2ea  test    eax, eax
0x18006b2ec  jz      loc_18006B5A3
0x18006b2f2  lea     r8, aClsid_0; "CLSID\\"
0x18006b2f9  mov     rdx, r12; unsigned __int64
0x18006b2fc  lea     rcx, [rbp+0E0h+SubKey]; char *
0x18006b300  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18006b305  test    eax, eax
0x18006b307  js      loc_18006B5A3
0x18006b30d  lea     r8, [rsp+1E0h+Data]; char *
0x18006b312  mov     rdx, r12; unsigned __int64
0x18006b315  lea     rcx, [rbp+0E0h+SubKey]; char *
0x18006b319  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18006b31e  test    eax, eax
0x18006b320  js      loc_18006B5A3
0x18006b326  lea     rax, [rsp+1E0h+dwDisposition]
0x18006b32b  mov     esi, 2001Fh
0x18006b330  mov     [rsp+1E0h+lpdwDisposition], rax; lpdwDisposition
0x18006b335  lea     r9, Class; lpClass
0x18006b33c  lea     rax, [rsp+1E0h+hKey]
0x18006b341  xor     r8d, r8d; Reserved
0x18006b344  mov     [rsp+1E0h+phkResult], rax; phkResult
0x18006b349  lea     rdx, [rbp+0E0h+SubKey]; lpSubKey
0x18006b34d  mov     [rsp+1E0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18006b352  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18006b359  mov     [rsp+1E0h+samDesired], esi; samDesired
0x18006b35d  mov     [rsp+1E0h+dwOptions], r15d; dwOptions
0x18006b362  call    cs:__imp_RegCreateKeyExA
0x18006b368  test    eax, eax
0x18006b36a  jnz     loc_18006B5A3
0x18006b370  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18006b375  lea     rax, [rsp+1E0h+dwDisposition]
0x18006b37a  mov     [rsp+1E0h+lpdwDisposition], rax; lpdwDisposition
0x18006b37f  lea     r9, Class; lpClass
0x18006b386  lea     rax, [rsp+1E0h+var_188]
0x18006b38b  xor     r8d, r8d; Reserved
0x18006b38e  mov     [rsp+1E0h+phkResult], rax; phkResult
0x18006b393  lea     rdx, aVersionindepen; "VersionIndependentProgID"
0x18006b39a  mov     [rsp+1E0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18006b39f  mov     [rsp+1E0h+samDesired], esi; samDesired
0x18006b3a3  mov     [rsp+1E0h+dwOptions], r15d; dwOptions
0x18006b3a8  call    cs:__imp_RegCreateKeyExA
0x18006b3ae  test    eax, eax
0x18006b3b0  jnz     loc_18006B5A3
0x18006b3b6  lea     r8, ?g_szLibName@@3QBDB; "Internet"
0x18006b3bd  mov     rdx, r12; unsigned __int64
0x18006b3c0  lea     rcx, [rbp+0E0h+SubKey]; char *
0x18006b3c4  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18006b3c9  test    eax, eax
0x18006b3cb  js      loc_18006B5A3
0x18006b3d1  lea     r8, asc_18007FE14; "."
0x18006b3d8  mov     rdx, r12; unsigned __int64
0x18006b3db  lea     rcx, [rbp+0E0h+SubKey]; char *
0x18006b3df  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
  ... truncated ...
```
