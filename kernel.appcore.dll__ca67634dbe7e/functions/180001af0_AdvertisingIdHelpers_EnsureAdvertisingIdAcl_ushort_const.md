# AdvertisingIdHelpers::EnsureAdvertisingIdAcl(ushort const *)

- ea: `0x180001af0`
- end: `0x180001d18`
- name: `?EnsureAdvertisingIdAcl@AdvertisingIdHelpers@@YAJPEBG@Z`
- size: `552`
- prototype: `__int64 __fastcall(AdvertisingIdHelpers *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800011a0`
- `0x180001380`

## callees

- `0x180001af0`
- `0x180002b70`
- `0x1800058d0`
- `0x180005f54`
- `0x180006324`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001c44`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001d0d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001c44`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001d0d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180001b48`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180001c20`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180001b48`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180001c20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001b81`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001bb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001c72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001b81`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001bb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001c72`

## pseudocode

```c
__int64 __fastcall AdvertisingIdHelpers::EnsureAdvertisingIdAcl(WCHAR *this, const unsigned __int16 *a2)
{
  LSTATUS v3; // eax
  const unsigned __int16 *v4; // r8
  unsigned int v5; // edi
  int v6; // eax
  unsigned int v7; // ebx
  int UserAdvertisingRegPath; // eax
  WCHAR *v10; // rbx
  LSTATUS v11; // eax
  WCHAR *v12; // rcx
  DWORD dwOptions; // [rsp+20h] [rbp-48h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-48h]
  DWORD dwOptionsb; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  DWORD dwDisposition; // [rsp+70h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF
  LPCWSTR lpSubKey; // [rsp+80h] [rbp+18h]

  hKey = 0;
  dwDisposition = 0;
  if ( !this )
  {
    v3 = RegCreateKeyExW(
           HKEY_CURRENT_USER,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\AdvertisingInfo",
           0,
           0,
           0,
           0xF013Fu,
           0,
           &hKey,
           &dwDisposition);
    v5 = v3;
    if ( v3 > 0 )
      v5 = (unsigned __int16)v3 | 0x80070000;
    if ( (v5 & 0x80000000) == 0 )
    {
LABEL_5:
      v6 = AdvertisingIdHelpers::SetDaclForRootKey(hKey, this, v4);
      v7 = v6;
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x21E,
          (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
          (const char *)(unsigned int)v6,
          dwOptionsa);
        if ( hKey )
          RegCloseKey(hKey);
        return v7;
      }
      else
      {
        if ( hKey )
          RegCloseKey(hKey);
        return 0;
      }
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2FF,
      (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
      (const char *)v5,
      dwOptionsa);
    goto LABEL_9;
  }
  lpSubKey = 0;
  UserAdvertisingRegPath = AdvertisingIdHelpers::GetUserAdvertisingRegPath(this);
  v5 = UserAdvertisingRegPath;
  if ( UserAdvertisingRegPath < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x304,
      (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
      (const char *)(unsigned int)UserAdvertisingRegPath,
      dwOptions);
    v12 = (WCHAR *)lpSubKey;
    if ( !lpSubKey )
      goto LABEL_9;
LABEL_26:
    LocalFree(v12);
    goto LABEL_9;
  }
  v10 = (WCHAR *)lpSubKey;
  v11 = RegCreateKeyExW(HKEY_USERS, lpSubKey, 0, 0, 0, 0xF013Fu, 0, &hKey, &dwDisposition);
  v5 = v11;
  if ( v11 > 0 )
    v5 = (unsigned __int16)v11 | 0x80070000;
  if ( (v5 & 0x80000000) == 0 )
  {
    if ( v10 )
      LocalFree(v10);
    goto LABEL_5;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x30F,
    (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
    (const char *)v5,
    dwOptionsa);
  if ( v10 )
  {
    v12 = v10;
    goto LABEL_26;
  }
LABEL_9:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x21D,
    (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
    (const char *)v5,
    dwOptionsb);
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x180001af0  push    rbx
0x180001af2  push    rsi
0x180001af3  push    rdi
0x180001af4  sub     rsp, 50h
0x180001af8  xor     ebx, ebx
0x180001afa  mov     rsi, rcx
0x180001afd  mov     [rsp+68h+hKey], rbx
0x180001b02  mov     [rsp+68h+dwDisposition], ebx
0x180001b06  test    rcx, rcx
0x180001b09  jnz     loc_180001BC4
0x180001b0f  lea     rax, [rsp+68h+dwDisposition]
0x180001b14  xor     r9d, r9d; lpClass
0x180001b17  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x180001b1c  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180001b23  lea     rax, [rsp+68h+hKey]
0x180001b28  xor     r8d, r8d; Reserved
0x180001b2b  mov     [rsp+68h+phkResult], rax; phkResult
0x180001b30  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180001b37  mov     [rsp+68h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180001b3c  mov     [rsp+68h+samDesired], 0F013Fh; samDesired
0x180001b44  mov     [rsp+68h+dwOptions], ebx; int
0x180001b48  call    cs:__imp_RegCreateKeyExW
0x180001b4e  mov     edi, eax
0x180001b50  test    eax, eax
0x180001b52  jg      loc_180001C82
0x180001b58  test    edi, edi
0x180001b5a  js      loc_180001C90
0x180001b60  mov     rcx, [rsp+68h+hKey]; hKey
0x180001b65  mov     rdx, rsi; lpString2
0x180001b68  call    ?SetDaclForRootKey@AdvertisingIdHelpers@@YAJPEAUHKEY__@@PEBG@Z; AdvertisingIdHelpers::SetDaclForRootKey(HKEY__ *,ushort const *)
0x180001b6d  mov     ebx, eax
0x180001b6f  test    eax, eax
0x180001b71  js      loc_180001C4F
0x180001b77  mov     rcx, [rsp+68h+hKey]; hKey
0x180001b7c  test    rcx, rcx
0x180001b7f  jz      short loc_180001B87
0x180001b81  call    cs:__imp_RegCloseKey
0x180001b87  xor     eax, eax
0x180001b89  add     rsp, 50h
0x180001b8d  pop     rdi
0x180001b8e  pop     rsi
0x180001b8f  pop     rbx
0x180001b90  retn
0x180001b91  mov     rcx, [rsp+68h]; this
0x180001b96  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x180001b9d  mov     r9d, edi; char *
0x180001ba0  mov     edx, 21Dh; void *
0x180001ba5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180001baa  mov     rcx, [rsp+68h+hKey]; hKey
0x180001baf  test    rcx, rcx
0x180001bb2  jz      short loc_180001BBA
0x180001bb4  call    cs:__imp_RegCloseKey
0x180001bba  mov     eax, edi
0x180001bbc  add     rsp, 50h
0x180001bc0  pop     rdi
0x180001bc1  pop     rsi
0x180001bc2  pop     rbx
0x180001bc3  retn
0x180001bc4  lea     rdx, [rsp+68h+lpSubKey]
0x180001bcc  mov     [rsp+68h+lpSubKey], rbx
0x180001bd4  call    AdvertisingIdHelpers__GetUserAdvertisingRegPath
0x180001bd9  mov     edi, eax
0x180001bdb  test    eax, eax
0x180001bdd  js      loc_180001CAE
0x180001be3  lea     rax, [rsp+68h+dwDisposition]
0x180001be8  xor     r9d, r9d; lpClass
0x180001beb  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x180001bf0  xor     r8d, r8d; Reserved
0x180001bf3  lea     rax, [rsp+68h+hKey]
0x180001bf8  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180001bff  mov     [rsp+68h+phkResult], rax; phkResult
0x180001c04  mov     [rsp+68h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180001c09  mov     [rsp+68h+samDesired], 0F013Fh; samDesired
0x180001c11  mov     [rsp+68h+dwOptions], ebx; int
0x180001c15  mov     rbx, [rsp+68h+lpSubKey]
0x180001c1d  mov     rdx, rbx; lpSubKey
0x180001c20  call    cs:__imp_RegCreateKeyExW
0x180001c26  mov     edi, eax
0x180001c28  test    eax, eax
0x180001c2a  jg      loc_180001CDA
0x180001c30  test    edi, edi
0x180001c32  js      loc_180001CE8
0x180001c38  test    rbx, rbx
0x180001c3b  jz      loc_180001B60
0x180001c41  mov     rcx, rbx; hMem
0x180001c44  call    cs:__imp_LocalFree
0x180001c4a  jmp     loc_180001B60
0x180001c4f  mov     rcx, [rsp+68h]; this
0x180001c54  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x180001c5b  mov     r9d, ebx; char *
0x180001c5e  mov     edx, 21Eh; void *
0x180001c63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180001c68  mov     rcx, [rsp+68h+hKey]; hKey
0x180001c6d  test    rcx, rcx
0x180001c70  jz      short loc_180001C78
0x180001c72  call    cs:__imp_RegCloseKey
0x180001c78  mov     eax, ebx
0x180001c7a  add     rsp, 50h
0x180001c7e  pop     rdi
0x180001c7f  pop     rsi
0x180001c80  pop     rbx
0x180001c81  retn
0x180001c82  movzx   edi, ax
0x180001c85  or      edi, 80070000h
0x180001c8b  jmp     loc_180001B58
0x180001c90  mov     rcx, [rsp+68h]; this
0x180001c95  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x180001c9c  mov     r9d, edi; char *
0x180001c9f  mov     edx, 2FFh; void *
0x180001ca4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180001ca9  jmp     loc_180001B91
0x180001cae  mov     rcx, [rsp+68h]; this
0x180001cb3  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x180001cba  mov     r9d, eax; char *
0x180001cbd  mov     edx, 304h; void *
0x180001cc2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180001cc7  mov     rcx, [rsp+68h+lpSubKey]
0x180001ccf  test    rcx, rcx
0x180001cd2  jz      loc_180001B91
0x180001cd8  jmp     short loc_180001D0D
0x180001cda  movzx   edi, ax
0x180001cdd  or      edi, 80070000h
0x180001ce3  jmp     loc_180001C30
0x180001ce8  mov     rcx, [rsp+68h]; this
0x180001ced  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x180001cf4  mov     r9d, edi; char *
0x180001cf7  mov     edx, 30Fh; void *
0x180001cfc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180001d01  test    rbx, rbx
0x180001d04  jz      loc_180001B91
0x180001d0a  mov     rcx, rbx; hMem
0x180001d0d  call    cs:__imp_LocalFree
0x180001d13  jmp     loc_180001B91
```
