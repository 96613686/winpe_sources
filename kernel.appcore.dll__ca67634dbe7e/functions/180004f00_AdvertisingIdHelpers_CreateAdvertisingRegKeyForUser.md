# AdvertisingIdHelpers::CreateAdvertisingRegKeyForUser

- ea: `0x180004f00`
- end: `0x180005074`
- name: `AdvertisingIdHelpers::CreateAdvertisingRegKeyForUser`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800061c4`

## callees

- `0x180004f00`
- `0x180005f54`
- `0x180006324`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004fd2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000502e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005067`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004fd2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000502e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005067`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004f45`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004fba`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004f45`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004fba`

## pseudocode

```c
__int64 __fastcall AdvertisingIdHelpers::CreateAdvertisingRegKeyForUser(
        unsigned __int16 *a1,
        __int64 a2,
        HKEY *phkResult,
        DWORD *lpdwDisposition)
{
  LSTATUS v6; // eax
  unsigned int v7; // ebx
  int UserAdvertisingRegPath; // eax
  unsigned int v10; // ebp
  LSTATUS Key; // eax
  unsigned int v12; // edi
  DWORD dwOptions; // [rsp+20h] [rbp-58h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-58h]
  DWORD dwOptionsb; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( a1 )
  {
    UserAdvertisingRegPath = AdvertisingIdHelpers::GetUserAdvertisingRegPath(a1);
    v10 = UserAdvertisingRegPath;
    if ( UserAdvertisingRegPath < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x304,
        (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
        (const char *)(unsigned int)UserAdvertisingRegPath,
        dwOptions);
      return v10;
    }
    else
    {
      Key = RegCreateKeyExW(HKEY_USERS, 0, 0, 0, 0, 0xF013Fu, 0, phkResult, lpdwDisposition);
      v12 = Key;
      if ( Key > 0 )
        v12 = (unsigned __int16)Key | 0x80070000;
      if ( (v12 & 0x80000000) == 0 )
        return 0;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x30F,
        (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
        (const char *)v12,
        dwOptionsb);
      return v12;
    }
  }
  else
  {
    v6 = RegCreateKeyExW(
           HKEY_CURRENT_USER,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\AdvertisingInfo",
           0,
           0,
           0,
           0xF013Fu,
           0,
           phkResult,
           lpdwDisposition);
    v7 = v6;
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    if ( (v7 & 0x80000000) == 0 )
      return 0;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2FF,
      (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
      (const char *)v7,
      dwOptionsa);
    return v7;
  }
}

```

## disassembly

```asm
0x180004f00  push    rbx
0x180004f02  push    rbp
0x180004f03  push    rsi
0x180004f04  push    rdi
0x180004f05  sub     rsp, 58h
0x180004f09  xor     ebx, ebx
0x180004f0b  mov     rdi, r9
0x180004f0e  mov     rsi, r8
0x180004f11  test    rcx, rcx
0x180004f14  jnz     short loc_180004F68
0x180004f16  mov     [rsp+78h+lpdwDisposition], r9; lpdwDisposition
0x180004f1b  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180004f22  mov     [rsp+78h+phkResult], r8; phkResult
0x180004f27  xor     r9d, r9d; lpClass
0x180004f2a  mov     [rsp+78h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180004f2f  xor     r8d, r8d; Reserved
0x180004f32  mov     [rsp+78h+samDesired], 0F013Fh; samDesired
0x180004f3a  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180004f41  mov     [rsp+78h+dwOptions], ebx; int
0x180004f45  call    cs:__imp_RegCreateKeyExW
0x180004f4b  mov     ebx, eax
0x180004f4d  test    eax, eax
0x180004f4f  jg      loc_180004FDA
0x180004f55  test    ebx, ebx
0x180004f57  js      loc_180004FE8
0x180004f5d  xor     eax, eax
0x180004f5f  add     rsp, 58h
0x180004f63  pop     rdi
0x180004f64  pop     rsi
0x180004f65  pop     rbp
0x180004f66  pop     rbx
0x180004f67  retn
0x180004f68  lea     rdx, [rsp+78h+lpSubKey]
0x180004f70  mov     [rsp+78h+lpSubKey], rbx
0x180004f78  call    AdvertisingIdHelpers__GetUserAdvertisingRegPath
0x180004f7d  mov     ebp, eax
0x180004f7f  test    eax, eax
0x180004f81  js      loc_180005008
0x180004f87  mov     [rsp+78h+lpdwDisposition], rdi; lpdwDisposition
0x180004f8c  xor     r9d, r9d; lpClass
0x180004f8f  mov     [rsp+78h+phkResult], rsi; phkResult
0x180004f94  xor     r8d, r8d; Reserved
0x180004f97  mov     [rsp+78h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180004f9c  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180004fa3  mov     [rsp+78h+samDesired], 0F013Fh; samDesired
0x180004fab  mov     [rsp+78h+dwOptions], ebx; int
0x180004faf  mov     rbx, [rsp+78h+lpSubKey]
0x180004fb7  mov     rdx, rbx; lpSubKey
0x180004fba  call    cs:__imp_RegCreateKeyExW
0x180004fc0  mov     edi, eax
0x180004fc2  test    eax, eax
0x180004fc4  jg      short loc_18000503B
0x180004fc6  test    edi, edi
0x180004fc8  js      short loc_180005046
0x180004fca  test    rbx, rbx
0x180004fcd  jz      short loc_180004F5D
0x180004fcf  mov     rcx, rbx; hMem
0x180004fd2  call    cs:__imp_LocalFree
0x180004fd8  jmp     short loc_180004F5D
0x180004fda  movzx   ebx, ax
0x180004fdd  or      ebx, 80070000h
0x180004fe3  jmp     loc_180004F55
0x180004fe8  mov     rcx, [rsp+78h]; this
0x180004fed  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x180004ff4  mov     r9d, ebx; char *
0x180004ff7  mov     edx, 2FFh; void *
0x180004ffc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180005001  mov     eax, ebx
0x180005003  jmp     loc_180004F5F
0x180005008  mov     rcx, [rsp+78h]; this
0x18000500d  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x180005014  mov     r9d, ebp; char *
0x180005017  mov     edx, 304h; void *
0x18000501c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180005021  mov     rcx, [rsp+78h+lpSubKey]; hMem
0x180005029  test    rcx, rcx
0x18000502c  jz      short loc_180005034
0x18000502e  call    cs:__imp_LocalFree
0x180005034  mov     eax, ebp
0x180005036  jmp     loc_180004F5F
0x18000503b  movzx   edi, ax
0x18000503e  or      edi, 80070000h
0x180005044  jmp     short loc_180004FC6
0x180005046  mov     rcx, [rsp+78h]; this
0x18000504b  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x180005052  mov     r9d, edi; char *
0x180005055  mov     edx, 30Fh; void *
0x18000505a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000505f  test    rbx, rbx
0x180005062  jz      short loc_18000506D
0x180005064  mov     rcx, rbx; hMem
0x180005067  call    cs:__imp_LocalFree
0x18000506d  mov     eax, edi
0x18000506f  jmp     loc_180004F5F
```
