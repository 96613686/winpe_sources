# WriteCacheOpts

- ea: `0x18000f470`
- end: `0x18000f643`
- name: `WriteCacheOpts`
- size: `467`
- prototype: `__int64 __fastcall(HKEY hKey, wchar_t *Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000fc20`

## callees

- `0x18000f470`
- `0x180011ba0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000f4e7`
- `msvcrt!wcscat_s` at `0x18000f4e7`
- `msvcrt!wcscpy_s` at `0x18000f4d0`
- `msvcrt!wcscpy_s` at `0x18000f4d0`
- `ADVAPI32!RegCreateKeyExW` at `0x18000f528`
- `ADVAPI32!RegCreateKeyExW` at `0x18000f528`
- `ADVAPI32!RegSetValueExW` at `0x18000f568`
- `ADVAPI32!RegSetValueExW` at `0x18000f59b`
- `ADVAPI32!RegSetValueExW` at `0x18000f5c3`
- `ADVAPI32!RegSetValueExW` at `0x18000f5eb`
- `ADVAPI32!RegSetValueExW` at `0x18000f610`
- `ADVAPI32!RegSetValueExW` at `0x18000f568`
- `ADVAPI32!RegSetValueExW` at `0x18000f59b`
- `ADVAPI32!RegSetValueExW` at `0x18000f5c3`
- `ADVAPI32!RegSetValueExW` at `0x18000f5eb`
- `ADVAPI32!RegSetValueExW` at `0x18000f610`
- `ADVAPI32!RegCloseKey` at `0x18000f61b`
- `ADVAPI32!RegCloseKey` at `0x18000f61b`

## string_xrefs

- `0x18000f4d6`: `\Cache`
- `0x18000f539`: `FileAttributeCache`
- `0x18000f571`: `RemoteWriteCache`
- `0x18000f5fe`: `CacheBlocks`

## pseudocode

```c
LSTATUS __fastcall WriteCacheOpts(HKEY hKey, wchar_t *Source, const BYTE *a3)
{
  __int64 v3; // rsi
  LSTATUS result; // eax
  BYTE Data[8]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKeya; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition[4]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Destination[264]; // [rsp+70h] [rbp-90h] BYREF

  v3 = *(_QWORD *)a3;
  *(_DWORD *)Data = 0;
  dwDisposition[0] = 0;
  hKeya = 0;
  Destination[259] = 0;
  wcscpy_s(Destination, 0x104u, Source);
  wcscat_s(Destination, 0x104u, L"\\Cache");
  result = RegCreateKeyExW(hKey, Destination, 0, 0, 0, 0xF003Fu, 0, &hKeya, dwDisposition);
  if ( !result )
  {
    *(_DWORD *)Data = (*(_DWORD *)(v3 + 56) >> 4) & 1;
    RegSetValueExW(hKeya, L"FileAttributeCache", 0, 4u, Data, 4u);
    *(_DWORD *)Data = (*(_DWORD *)(v3 + 56) >> 3) & 1;
    RegSetValueExW(hKeya, L"RemoteWriteCache", 0, 4u, Data, 4u);
    RegSetValueExW(hKeya, L"HashTableSize", 0, 4u, (const BYTE *)(*(_QWORD *)a3 + 40LL), 4u);
    RegSetValueExW(hKeya, L"AttributeTimeDelta", 0, 4u, (const BYTE *)(*(_QWORD *)a3 + 48LL), 4u);
    RegSetValueExW(hKeya, L"CacheBlocks", 0, 4u, a3 + 32, 4u);
    return RegCloseKey(hKeya);
  }
  return result;
}

```

## disassembly

```asm
0x18000f470  mov     [rsp-8+arg_18], rbx
0x18000f475  push    rbp
0x18000f476  push    rsi
0x18000f477  push    rdi
0x18000f478  lea     rbp, [rsp-190h]
0x18000f480  sub     rsp, 290h
0x18000f487  mov     rax, cs:__security_cookie
0x18000f48e  xor     rax, rsp
0x18000f491  mov     [rbp+1A0h+var_20], rax
0x18000f498  mov     rsi, [r8]
0x18000f49b  mov     rdi, r8
0x18000f49e  mov     r8, rdx; Source
0x18000f4a1  mov     dword ptr [rsp+2A0h+Data], 0
0x18000f4a9  mov     rbx, rcx
0x18000f4ac  mov     [rsp+2A0h+dwDisposition], 0
0x18000f4b4  xor     eax, eax
0x18000f4b6  mov     [rsp+2A0h+hKey], 0
0x18000f4bf  mov     edx, 104h; SizeInWords
0x18000f4c4  mov     [rbp+1A0h+var_2A], ax
0x18000f4cb  lea     rcx, [rsp+2A0h+Destination]; Destination
0x18000f4d0  call    cs:__imp_wcscpy_s
0x18000f4d6  lea     r8, aCache; "\\Cache"
0x18000f4dd  mov     edx, 104h; SizeInWords
0x18000f4e2  lea     rcx, [rsp+2A0h+Destination]; Destination
0x18000f4e7  call    cs:__imp_wcscat_s
0x18000f4ed  lea     rax, [rsp+2A0h+dwDisposition]
0x18000f4f2  xor     r9d, r9d; lpClass
0x18000f4f5  mov     [rsp+2A0h+lpdwDisposition], rax; lpdwDisposition
0x18000f4fa  lea     rdx, [rsp+2A0h+Destination]; lpSubKey
0x18000f4ff  lea     rax, [rsp+2A0h+hKey]
0x18000f504  xor     r8d, r8d; Reserved
0x18000f507  mov     [rsp+2A0h+phkResult], rax; phkResult
0x18000f50c  mov     rcx, rbx; hKey
0x18000f50f  mov     [rsp+2A0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000f518  mov     [rsp+2A0h+samDesired], 0F003Fh; samDesired
0x18000f520  mov     [rsp+2A0h+dwOptions], 0; dwOptions
0x18000f528  call    cs:__imp_RegCreateKeyExW
0x18000f52e  test    eax, eax
0x18000f530  jnz     loc_18000F621
0x18000f536  mov     eax, [rsi+38h]
0x18000f539  lea     rdx, aFileattributec; "FileAttributeCache"
0x18000f540  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18000f545  mov     ebx, 4
0x18000f54a  shr     eax, 4
0x18000f54d  mov     r9d, ebx; dwType
0x18000f550  and     eax, 1
0x18000f553  mov     [rsp+2A0h+samDesired], ebx; cbData
0x18000f557  mov     dword ptr [rsp+2A0h+Data], eax
0x18000f55b  xor     r8d, r8d; Reserved
0x18000f55e  lea     rax, [rsp+2A0h+Data]
0x18000f563  mov     qword ptr [rsp+2A0h+dwOptions], rax; lpData
0x18000f568  call    cs:__imp_RegSetValueExW
0x18000f56e  mov     eax, [rsi+38h]
0x18000f571  lea     rdx, aRemotewritecac; "RemoteWriteCache"
0x18000f578  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18000f57d  mov     r9d, ebx; dwType
0x18000f580  shr     eax, 3
0x18000f583  xor     r8d, r8d; Reserved
0x18000f586  and     eax, 1
0x18000f589  mov     [rsp+2A0h+samDesired], ebx; cbData
0x18000f58d  mov     dword ptr [rsp+2A0h+Data], eax
0x18000f591  lea     rax, [rsp+2A0h+Data]
0x18000f596  mov     qword ptr [rsp+2A0h+dwOptions], rax; lpData
0x18000f59b  call    cs:__imp_RegSetValueExW
0x18000f5a1  mov     rax, [rdi]
0x18000f5a4  lea     rdx, aHashtablesize; "HashTableSize"
0x18000f5ab  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18000f5b0  add     rax, 28h ; '('
0x18000f5b4  mov     [rsp+2A0h+samDesired], ebx; cbData
0x18000f5b8  mov     r9d, ebx; dwType
0x18000f5bb  xor     r8d, r8d; Reserved
0x18000f5be  mov     qword ptr [rsp+2A0h+dwOptions], rax; lpData
0x18000f5c3  call    cs:__imp_RegSetValueExW
0x18000f5c9  mov     rax, [rdi]
0x18000f5cc  lea     rdx, aAttributetimed; "AttributeTimeDelta"
0x18000f5d3  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18000f5d8  add     rax, 30h ; '0'
0x18000f5dc  mov     [rsp+2A0h+samDesired], ebx; cbData
0x18000f5e0  mov     r9d, ebx; dwType
0x18000f5e3  xor     r8d, r8d; Reserved
0x18000f5e6  mov     qword ptr [rsp+2A0h+dwOptions], rax; lpData
0x18000f5eb  call    cs:__imp_RegSetValueExW
0x18000f5f1  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18000f5f6  lea     rax, [rdi+20h]
0x18000f5fa  mov     [rsp+2A0h+samDesired], ebx; cbData
0x18000f5fe  lea     rdx, aCacheblocks; "CacheBlocks"
0x18000f605  mov     r9d, ebx; dwType
0x18000f608  mov     qword ptr [rsp+2A0h+dwOptions], rax; lpData
0x18000f60d  xor     r8d, r8d; Reserved
0x18000f610  call    cs:__imp_RegSetValueExW
0x18000f616  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18000f61b  call    cs:__imp_RegCloseKey
0x18000f621  mov     rcx, [rbp+1A0h+var_20]
0x18000f628  xor     rcx, rsp; StackCookie
0x18000f62b  call    __security_check_cookie
0x18000f630  mov     rbx, [rsp+2A0h+arg_18]
0x18000f638  add     rsp, 290h
0x18000f63f  pop     rdi
0x18000f640  pop     rsi
0x18000f641  pop     rbp
0x18000f642  retn
```
