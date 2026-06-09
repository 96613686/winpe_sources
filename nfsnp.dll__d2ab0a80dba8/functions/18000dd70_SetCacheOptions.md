# SetCacheOptions

- ea: `0x18000dd70`
- end: `0x18000df6e`
- name: `SetCacheOptions`
- size: `510`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000be24`
- `0x18000e454`

## callees

- `0x18000dd70`
- `0x180011ba0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000ddfe`
- `msvcrt!wcscat_s` at `0x18000ddfe`
- `msvcrt!wcsncpy_s` at `0x18000ddea`
- `msvcrt!wcsncpy_s` at `0x18000ddea`
- `ADVAPI32!RegCloseKey` at `0x18000df28`
- `ADVAPI32!RegCloseKey` at `0x18000df28`
- `ADVAPI32!RegQueryValueExW` at `0x18000de5e`
- `ADVAPI32!RegQueryValueExW` at `0x18000de8e`
- `ADVAPI32!RegQueryValueExW` at `0x18000debe`
- `ADVAPI32!RegQueryValueExW` at `0x18000deed`
- `ADVAPI32!RegQueryValueExW` at `0x18000df1d`
- `ADVAPI32!RegQueryValueExW` at `0x18000de5e`
- `ADVAPI32!RegQueryValueExW` at `0x18000de8e`
- `ADVAPI32!RegQueryValueExW` at `0x18000debe`
- `ADVAPI32!RegQueryValueExW` at `0x18000deed`
- `ADVAPI32!RegQueryValueExW` at `0x18000df1d`
- `ADVAPI32!RegOpenKeyExW` at `0x18000de23`
- `ADVAPI32!RegOpenKeyExW` at `0x18000de23`

## string_xrefs

- `0x18000ddf0`: `\Cache`
- `0x18000de47`: `FileAttributeCache`
- `0x18000de73`: `RemoteWriteCache`
- `0x18000dedb`: `CacheBlocks`

## pseudocode

```c
__int64 __fastcall SetCacheOptions(__int64 a1, __int64 a2, BYTE *a3)
{
  __int64 v3; // rbx
  __int64 result; // rax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  BYTE v8[4]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE v9[4]; // [rsp+44h] [rbp-BCh] BYREF
  BYTE v10[4]; // [rsp+48h] [rbp-B8h] BYREF
  BYTE Data[4]; // [rsp+4Ch] [rbp-B4h] BYREF
  wchar_t Destination[264]; // [rsp+50h] [rbp-B0h] BYREF

  v3 = *(_QWORD *)a3;
  *(_DWORD *)v8 = 256;
  *(_DWORD *)Data = 1;
  *(_DWORD *)v10 = 1;
  *(_DWORD *)v9 = 30;
  cbData = 0;
  hKey = 0;
  Destination[259] = 0;
  wcsncpy_s(Destination, 0x104u, L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default", 0x103u);
  wcscat_s(Destination, 0x104u, L"\\Cache");
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, Destination, 0, 0x20019u, &hKey) )
  {
    cbData = 4;
    RegQueryValueExW(hKey, L"FileAttributeCache", 0, 0, Data, &cbData);
    cbData = 4;
    RegQueryValueExW(hKey, L"RemoteWriteCache", 0, 0, v10, &cbData);
    cbData = 4;
    RegQueryValueExW(hKey, L"HashTableSize", 0, 0, v8, &cbData);
    cbData = 4;
    RegQueryValueExW(hKey, L"CacheBlocks", 0, 0, a3 + 32, &cbData);
    cbData = 4;
    RegQueryValueExW(hKey, L"AttributeTimeDelta", 0, 0, v9, &cbData);
    RegCloseKey(hKey);
  }
  *(_DWORD *)(v3 + 40) = *(_DWORD *)v8;
  result = *(unsigned int *)v9;
  *(_QWORD *)(v3 + 48) = *(unsigned int *)v9;
  if ( *(_DWORD *)v10 )
    *(_DWORD *)(v3 + 56) |= 8u;
  if ( *(_DWORD *)Data )
    *(_DWORD *)(v3 + 56) |= 0x10u;
  return result;
}

```

## disassembly

```asm
0x18000dd70  push    rbp
0x18000dd72  push    rbx
0x18000dd73  push    rsi
0x18000dd74  push    rdi
0x18000dd75  lea     rbp, [rsp-178h]
0x18000dd7d  sub     rsp, 278h
0x18000dd84  mov     rax, cs:__security_cookie
0x18000dd8b  xor     rax, rsp
0x18000dd8e  mov     [rbp+190h+var_30], rax
0x18000dd95  mov     rbx, [r8]
0x18000dd98  lea     rcx, [rsp+290h+Destination]; Destination
0x18000dd9d  mov     eax, 1
0x18000dda2  mov     dword ptr [rsp+290h+var_250], 100h
0x18000ddaa  mov     r9d, 103h; MaxCount
0x18000ddb0  mov     dword ptr [rsp+290h+Data], eax
0x18000ddb4  mov     dword ptr [rsp+290h+var_248], eax
0x18000ddb8  mov     rdi, r8
0x18000ddbb  xor     eax, eax
0x18000ddbd  mov     dword ptr [rsp+290h+var_24C], 1Eh
0x18000ddc5  lea     r8, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x18000ddcc  mov     [rsp+290h+cbData], 0
0x18000ddd4  lea     esi, [r9+1]
0x18000ddd8  mov     [rsp+290h+hKey], 0
0x18000dde1  mov     edx, esi; SizeInWords
0x18000dde3  mov     [rbp+190h+var_3A], ax
0x18000ddea  call    cs:__imp_wcsncpy_s
0x18000ddf0  lea     r8, aCache; "\\Cache"
0x18000ddf7  mov     edx, esi; SizeInWords
0x18000ddf9  lea     rcx, [rsp+290h+Destination]; Destination
0x18000ddfe  call    cs:__imp_wcscat_s
0x18000de04  lea     rax, [rsp+290h+hKey]
0x18000de09  mov     r9d, 20019h; samDesired
0x18000de0f  xor     r8d, r8d; ulOptions
0x18000de12  mov     [rsp+290h+phkResult], rax; phkResult
0x18000de17  lea     rdx, [rsp+290h+Destination]; lpSubKey
0x18000de1c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000de23  call    cs:__imp_RegOpenKeyExW
0x18000de29  test    eax, eax
0x18000de2b  jnz     loc_18000DF2E
0x18000de31  mov     rcx, [rsp+290h+hKey]; hKey
0x18000de36  lea     esi, [rax+4]
0x18000de39  lea     rax, [rsp+290h+cbData]
0x18000de3e  mov     [rsp+290h+cbData], esi
0x18000de42  mov     [rsp+290h+lpcbData], rax; lpcbData
0x18000de47  lea     rdx, aFileattributec; "FileAttributeCache"
0x18000de4e  lea     rax, [rsp+290h+Data]
0x18000de53  xor     r9d, r9d; lpType
0x18000de56  xor     r8d, r8d; lpReserved
0x18000de59  mov     [rsp+290h+phkResult], rax; lpData
0x18000de5e  call    cs:__imp_RegQueryValueExW
0x18000de64  mov     rcx, [rsp+290h+hKey]; hKey
0x18000de69  lea     rax, [rsp+290h+cbData]
0x18000de6e  mov     [rsp+290h+lpcbData], rax; lpcbData
0x18000de73  lea     rdx, aRemotewritecac; "RemoteWriteCache"
0x18000de7a  lea     rax, [rsp+290h+var_248]
0x18000de7f  mov     [rsp+290h+cbData], esi
0x18000de83  xor     r9d, r9d; lpType
0x18000de86  mov     [rsp+290h+phkResult], rax; lpData
0x18000de8b  xor     r8d, r8d; lpReserved
0x18000de8e  call    cs:__imp_RegQueryValueExW
0x18000de94  mov     rcx, [rsp+290h+hKey]; hKey
0x18000de99  lea     rax, [rsp+290h+cbData]
0x18000de9e  mov     [rsp+290h+lpcbData], rax; lpcbData
0x18000dea3  lea     rdx, aHashtablesize; "HashTableSize"
0x18000deaa  lea     rax, [rsp+290h+var_250]
0x18000deaf  mov     [rsp+290h+cbData], esi
0x18000deb3  xor     r9d, r9d; lpType
0x18000deb6  mov     [rsp+290h+phkResult], rax; lpData
0x18000debb  xor     r8d, r8d; lpReserved
0x18000debe  call    cs:__imp_RegQueryValueExW
0x18000dec4  lea     rcx, [rsp+290h+cbData]
0x18000dec9  mov     [rsp+290h+cbData], esi
0x18000decd  mov     [rsp+290h+lpcbData], rcx; lpcbData
0x18000ded2  lea     rax, [rdi+20h]
0x18000ded6  mov     rcx, [rsp+290h+hKey]; hKey
0x18000dedb  lea     rdx, aCacheblocks; "CacheBlocks"
0x18000dee2  xor     r9d, r9d; lpType
0x18000dee5  mov     [rsp+290h+phkResult], rax; lpData
0x18000deea  xor     r8d, r8d; lpReserved
0x18000deed  call    cs:__imp_RegQueryValueExW
0x18000def3  mov     rcx, [rsp+290h+hKey]; hKey
0x18000def8  lea     rax, [rsp+290h+cbData]
0x18000defd  mov     [rsp+290h+lpcbData], rax; lpcbData
0x18000df02  lea     rdx, aAttributetimed; "AttributeTimeDelta"
0x18000df09  lea     rax, [rsp+290h+var_24C]
0x18000df0e  mov     [rsp+290h+cbData], esi
0x18000df12  xor     r9d, r9d; lpType
0x18000df15  mov     [rsp+290h+phkResult], rax; lpData
0x18000df1a  xor     r8d, r8d; lpReserved
0x18000df1d  call    cs:__imp_RegQueryValueExW
0x18000df23  mov     rcx, [rsp+290h+hKey]; hKey
0x18000df28  call    cs:__imp_RegCloseKey
0x18000df2e  mov     eax, dword ptr [rsp+290h+var_250]
0x18000df32  mov     [rbx+28h], eax
0x18000df35  mov     eax, dword ptr [rsp+290h+var_24C]
0x18000df39  mov     [rbx+30h], rax
0x18000df3d  cmp     dword ptr [rsp+290h+var_248], 0
0x18000df42  jz      short loc_18000DF48
0x18000df44  or      dword ptr [rbx+38h], 8
0x18000df48  cmp     dword ptr [rsp+290h+Data], 0
0x18000df4d  jz      short loc_18000DF53
0x18000df4f  or      dword ptr [rbx+38h], 10h
0x18000df53  mov     rcx, [rbp+190h+var_30]
0x18000df5a  xor     rcx, rsp; StackCookie
0x18000df5d  call    __security_check_cookie
0x18000df62  add     rsp, 278h
0x18000df69  pop     rdi
0x18000df6a  pop     rsi
0x18000df6b  pop     rbx
0x18000df6c  pop     rbp
0x18000df6d  retn
```
