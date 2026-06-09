# SetCacheOptions

- ea: `0x18000ea28`
- end: `0x18000ec5d`
- name: `SetCacheOptions`
- size: `565`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c738`
- `0x18000f1c8`

## callees

- `0x18000ea28`
- `0x180012e70`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000eabc`
- `msvcrt!wcscat_s` at `0x18000eabc`
- `msvcrt!wcsncpy_s` at `0x18000eaa2`
- `msvcrt!wcsncpy_s` at `0x18000eaa2`
- `ADVAPI32!RegCloseKey` at `0x18000ec10`
- `ADVAPI32!RegCloseKey` at `0x18000ec10`
- `ADVAPI32!RegQueryValueExW` at `0x18000eb28`
- `ADVAPI32!RegQueryValueExW` at `0x18000eb5e`
- `ADVAPI32!RegQueryValueExW` at `0x18000eb94`
- `ADVAPI32!RegQueryValueExW` at `0x18000ebc9`
- `ADVAPI32!RegQueryValueExW` at `0x18000ebff`
- `ADVAPI32!RegQueryValueExW` at `0x18000eb28`
- `ADVAPI32!RegQueryValueExW` at `0x18000eb5e`
- `ADVAPI32!RegQueryValueExW` at `0x18000eb94`
- `ADVAPI32!RegQueryValueExW` at `0x18000ebc9`
- `ADVAPI32!RegQueryValueExW` at `0x18000ebff`
- `ADVAPI32!RegOpenKeyExW` at `0x18000eae7`
- `ADVAPI32!RegOpenKeyExW` at `0x18000eae7`

## string_xrefs

- `0x18000eaae`: `\Cache`
- `0x18000eb11`: `FileAttributeCache`
- `0x18000eb43`: `RemoteWriteCache`
- `0x18000ebb7`: `CacheBlocks`

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
0x18000ea28  push    rbp
0x18000ea2a  push    rbx
0x18000ea2b  push    rsi
0x18000ea2c  push    rdi
0x18000ea2d  lea     rbp, [rsp-178h]
0x18000ea35  sub     rsp, 278h
0x18000ea3c  mov     rax, cs:__security_cookie
0x18000ea43  xor     rax, rsp
0x18000ea46  mov     [rbp+190h+var_30], rax
0x18000ea4d  mov     rbx, [r8]
0x18000ea50  lea     rcx, [rsp+290h+Destination]; Destination
0x18000ea55  mov     eax, 1
0x18000ea5a  mov     dword ptr [rsp+290h+var_250], 100h
0x18000ea62  mov     r9d, 103h; MaxCount
0x18000ea68  mov     dword ptr [rsp+290h+Data], eax
0x18000ea6c  mov     dword ptr [rsp+290h+var_248], eax
0x18000ea70  mov     rdi, r8
0x18000ea73  xor     eax, eax
0x18000ea75  mov     dword ptr [rsp+290h+var_24C], 1Eh
0x18000ea7d  lea     r8, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x18000ea84  mov     [rsp+290h+cbData], 0
0x18000ea8c  lea     esi, [r9+1]
0x18000ea90  mov     [rsp+290h+hKey], 0
0x18000ea99  mov     edx, esi; SizeInWords
0x18000ea9b  mov     [rbp+190h+var_3A], ax
0x18000eaa2  call    cs:__imp_wcsncpy_s
0x18000eaa9  nop     dword ptr [rax+rax+00h]
0x18000eaae  lea     r8, aCache; "\\Cache"
0x18000eab5  mov     edx, esi; SizeInWords
0x18000eab7  lea     rcx, [rsp+290h+Destination]; Destination
0x18000eabc  call    cs:__imp_wcscat_s
0x18000eac3  nop     dword ptr [rax+rax+00h]
0x18000eac8  lea     rax, [rsp+290h+hKey]
0x18000eacd  mov     r9d, 20019h; samDesired
0x18000ead3  xor     r8d, r8d; ulOptions
0x18000ead6  mov     [rsp+290h+phkResult], rax; phkResult
0x18000eadb  lea     rdx, [rsp+290h+Destination]; lpSubKey
0x18000eae0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000eae7  call    cs:__imp_RegOpenKeyExW
0x18000eaee  nop     dword ptr [rax+rax+00h]
0x18000eaf3  test    eax, eax
0x18000eaf5  jnz     loc_18000EC1C
0x18000eafb  mov     rcx, [rsp+290h+hKey]; hKey
0x18000eb00  lea     esi, [rax+4]
0x18000eb03  lea     rax, [rsp+290h+cbData]
0x18000eb08  mov     [rsp+290h+cbData], esi
0x18000eb0c  mov     [rsp+290h+lpcbData], rax; lpcbData
0x18000eb11  lea     rdx, aFileattributec; "FileAttributeCache"
0x18000eb18  lea     rax, [rsp+290h+Data]
0x18000eb1d  xor     r9d, r9d; lpType
0x18000eb20  xor     r8d, r8d; lpReserved
0x18000eb23  mov     [rsp+290h+phkResult], rax; lpData
0x18000eb28  call    cs:__imp_RegQueryValueExW
0x18000eb2f  nop     dword ptr [rax+rax+00h]
0x18000eb34  mov     rcx, [rsp+290h+hKey]; hKey
0x18000eb39  lea     rax, [rsp+290h+cbData]
0x18000eb3e  mov     [rsp+290h+lpcbData], rax; lpcbData
0x18000eb43  lea     rdx, aRemotewritecac; "RemoteWriteCache"
0x18000eb4a  lea     rax, [rsp+290h+var_248]
0x18000eb4f  mov     [rsp+290h+cbData], esi
0x18000eb53  xor     r9d, r9d; lpType
0x18000eb56  mov     [rsp+290h+phkResult], rax; lpData
0x18000eb5b  xor     r8d, r8d; lpReserved
0x18000eb5e  call    cs:__imp_RegQueryValueExW
0x18000eb65  nop     dword ptr [rax+rax+00h]
0x18000eb6a  mov     rcx, [rsp+290h+hKey]; hKey
0x18000eb6f  lea     rax, [rsp+290h+cbData]
0x18000eb74  mov     [rsp+290h+lpcbData], rax; lpcbData
0x18000eb79  lea     rdx, aHashtablesize; "HashTableSize"
0x18000eb80  lea     rax, [rsp+290h+var_250]
0x18000eb85  mov     [rsp+290h+cbData], esi
0x18000eb89  xor     r9d, r9d; lpType
0x18000eb8c  mov     [rsp+290h+phkResult], rax; lpData
0x18000eb91  xor     r8d, r8d; lpReserved
0x18000eb94  call    cs:__imp_RegQueryValueExW
0x18000eb9b  nop     dword ptr [rax+rax+00h]
0x18000eba0  lea     rcx, [rsp+290h+cbData]
0x18000eba5  mov     [rsp+290h+cbData], esi
0x18000eba9  mov     [rsp+290h+lpcbData], rcx; lpcbData
0x18000ebae  lea     rax, [rdi+20h]
0x18000ebb2  mov     rcx, [rsp+290h+hKey]; hKey
0x18000ebb7  lea     rdx, aCacheblocks; "CacheBlocks"
0x18000ebbe  xor     r9d, r9d; lpType
0x18000ebc1  mov     [rsp+290h+phkResult], rax; lpData
0x18000ebc6  xor     r8d, r8d; lpReserved
0x18000ebc9  call    cs:__imp_RegQueryValueExW
0x18000ebd0  nop     dword ptr [rax+rax+00h]
0x18000ebd5  mov     rcx, [rsp+290h+hKey]; hKey
0x18000ebda  lea     rax, [rsp+290h+cbData]
0x18000ebdf  mov     [rsp+290h+lpcbData], rax; lpcbData
0x18000ebe4  lea     rdx, aAttributetimed; "AttributeTimeDelta"
0x18000ebeb  lea     rax, [rsp+290h+var_24C]
0x18000ebf0  mov     [rsp+290h+cbData], esi
0x18000ebf4  xor     r9d, r9d; lpType
0x18000ebf7  mov     [rsp+290h+phkResult], rax; lpData
0x18000ebfc  xor     r8d, r8d; lpReserved
0x18000ebff  call    cs:__imp_RegQueryValueExW
0x18000ec06  nop     dword ptr [rax+rax+00h]
0x18000ec0b  mov     rcx, [rsp+290h+hKey]; hKey
0x18000ec10  call    cs:__imp_RegCloseKey
0x18000ec17  nop     dword ptr [rax+rax+00h]
0x18000ec1c  mov     eax, dword ptr [rsp+290h+var_250]
0x18000ec20  mov     [rbx+28h], eax
0x18000ec23  mov     eax, dword ptr [rsp+290h+var_24C]
0x18000ec27  mov     [rbx+30h], rax
0x18000ec2b  cmp     dword ptr [rsp+290h+var_248], 0
0x18000ec30  jz      short loc_18000EC36
0x18000ec32  or      dword ptr [rbx+38h], 8
0x18000ec36  cmp     dword ptr [rsp+290h+Data], 0
0x18000ec3b  jz      short loc_18000EC41
0x18000ec3d  or      dword ptr [rbx+38h], 10h
0x18000ec41  mov     rcx, [rbp+190h+var_30]
0x18000ec48  xor     rcx, rsp; StackCookie
0x18000ec4b  call    __security_check_cookie
0x18000ec50  add     rsp, 278h
0x18000ec57  pop     rdi
0x18000ec58  pop     rsi
0x18000ec59  pop     rbx
0x18000ec5a  pop     rbp
0x18000ec5b  retn
```
