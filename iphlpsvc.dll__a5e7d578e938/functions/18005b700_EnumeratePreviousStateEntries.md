# EnumeratePreviousStateEntries

- ea: `0x18005b700`
- end: `0x18005b8d1`
- name: `EnumeratePreviousStateEntries`
- size: `465`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18005b8d8`

## callees

- `0x18000d7c0`
- `0x1800190f0`
- `0x18002b4ec`
- `0x18002c834`
- `0x180040088`
- `0x18004b5f0`
- `0x18005b700`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005b884`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005b884`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b839`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b89f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b839`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b89f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005b7fa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005b7fa`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005b750`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005b750`

## string_xrefs

- `0x18005b75c`: `System\CurrentControlSet\Services\iphlpsvc\Teredo\PreviousState`
- `0x18005b776`: `Unable to open previous state key. Error = %u`

## pseudocode

```c
__int64 __fastcall EnumeratePreviousStateEntries(DWORD *a1, wchar_t *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  DWORD v7; // ebx
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // r15
  DWORD i; // edx
  unsigned __int64 UlongLong; // rax
  HKEY v12; // rcx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[96]; // [rsp+60h] [rbp-A0h] BYREF

  cchName = 0;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v4 = TeredoCreateRegKey(&hKey, L"System\\CurrentControlSet\\Services\\iphlpsvc\\Teredo\\PreviousState");
  v5 = v4;
  if ( v4 )
  {
    EventWriteError0(0x100000, L"Unable to open previous state key. Error = %u", v4);
    return v5;
  }
  else
  {
    v7 = 0;
    v8 = *(unsigned __int64 *)&SystemTimeAsFileTime / 0x989680;
    v9 = *(unsigned __int64 *)&SystemTimeAsFileTime / 0x989680;
    for ( i = 0; ; i = v7 )
    {
      cchName = 96;
      if ( RegEnumKeyExW(hKey, i, SubKey, &cchName, 0, 0, 0, 0) )
        break;
      EventWrite0(0x100000, L"Enumerated Key %u : %s", v7, SubKey);
      RegOpenKeyExW(hKey, SubKey, 0, 1u, &phkResult);
      UlongLong = GetUlongLong(phkResult, L"AddressCreationTimestamp", v9);
      if ( UlongLong < v8 )
      {
        v8 = UlongLong;
        StringCchCopyW(a2, 0xFFu, SubKey);
      }
      RegCloseKey(phkResult);
      ++v7;
    }
    v12 = hKey;
    *a1 = v7;
    RegCloseKey(v12);
    return 0;
  }
}

```

## disassembly

```asm
0x18005b700  mov     [rsp-8+arg_10], rbx
0x18005b705  push    rbp
0x18005b706  push    rsi
0x18005b707  push    rdi
0x18005b708  push    r14
0x18005b70a  push    r15
0x18005b70c  lea     rbp, [rsp-30h]
0x18005b711  sub     rsp, 130h
0x18005b718  mov     rax, cs:__security_cookie
0x18005b71f  xor     rax, rsp
0x18005b722  mov     [rbp+50h+var_30], rax
0x18005b726  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005b72a  mov     [rsp+150h+cchName], 0
0x18005b732  mov     rsi, rcx
0x18005b735  mov     [rsp+150h+hKey], rax
0x18005b73a  lea     rcx, [rsp+150h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18005b73f  mov     [rsp+150h+var_100], rax
0x18005b744  mov     r14, rdx
0x18005b747  mov     qword ptr [rsp+150h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18005b750  call    cs:__imp_GetSystemTimeAsFileTime
0x18005b757  nop     dword ptr [rax+rax+00h]
0x18005b75c  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\ip"...
0x18005b763  lea     rcx, [rsp+150h+hKey]; phkResult
0x18005b768  call    TeredoCreateRegKey
0x18005b76d  mov     ebx, eax
0x18005b76f  test    eax, eax
0x18005b771  jz      short loc_18005B78E
0x18005b773  mov     r8d, eax
0x18005b776  lea     rdx, aUnableToOpenPr; "Unable to open previous state key. Erro"...
0x18005b77d  mov     ecx, 100000h
0x18005b782  call    EventWriteError0
0x18005b787  mov     eax, ebx
0x18005b789  jmp     loc_18005B8AD
0x18005b78e  xor     ebx, ebx
0x18005b790  mov     rax, 0D6BF94D5E57A42BDh
0x18005b79a  mul     qword ptr [rsp+150h+SystemTimeAsFileTime.dwLowDateTime]
0x18005b79f  mov     [rsp+150h+lpftLastWriteTime], rbx
0x18005b7a4  mov     rdi, rdx
0x18005b7a7  mov     [rsp+150h+lpcchClass], rbx
0x18005b7ac  shr     rdi, 17h
0x18005b7b0  mov     [rsp+150h+lpClass], rbx
0x18005b7b5  mov     r15, rdi
0x18005b7b8  xor     edx, edx
0x18005b7ba  mov     [rsp+150h+phkResult], rbx
0x18005b7bf  jmp     loc_18005B86D
0x18005b7c4  lea     r9, [rsp+150h+SubKey]
0x18005b7c9  mov     r8d, ebx
0x18005b7cc  lea     rdx, aEnumeratedKeyU; "Enumerated Key %u : %s"
0x18005b7d3  mov     ecx, 100000h
0x18005b7d8  call    EventWrite0
0x18005b7dd  mov     rcx, [rsp+150h+hKey]; hKey
0x18005b7e2  lea     rax, [rsp+150h+var_100]
0x18005b7e7  mov     r9d, 1; samDesired
0x18005b7ed  mov     [rsp+150h+phkResult], rax; phkResult
0x18005b7f2  xor     r8d, r8d; ulOptions
0x18005b7f5  lea     rdx, [rsp+150h+SubKey]; lpSubKey
0x18005b7fa  call    cs:__imp_RegOpenKeyExW
0x18005b801  nop     dword ptr [rax+rax+00h]
0x18005b806  mov     rcx, [rsp+150h+var_100]
0x18005b80b  lea     rdx, aAddresscreatio; "AddressCreationTimestamp"
0x18005b812  mov     r8, r15
0x18005b815  call    GetUlongLong
0x18005b81a  cmp     rax, rdi
0x18005b81d  jnb     short loc_18005B834
0x18005b81f  lea     r8, [rsp+150h+SubKey]; pszSrc
0x18005b824  mov     edx, 0FFh; cchDest
0x18005b829  mov     rcx, r14; pszDest
0x18005b82c  mov     rdi, rax
0x18005b82f  call    StringCchCopyW
0x18005b834  mov     rcx, [rsp+150h+var_100]; hKey
0x18005b839  call    cs:__imp_RegCloseKey
0x18005b840  nop     dword ptr [rax+rax+00h]
0x18005b845  mov     [rsp+150h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18005b84e  inc     ebx
0x18005b850  mov     [rsp+150h+lpcchClass], 0; lpcchClass
0x18005b859  mov     edx, ebx; dwIndex
0x18005b85b  mov     [rsp+150h+lpClass], 0; lpClass
0x18005b864  mov     [rsp+150h+phkResult], 0; lpReserved
0x18005b86d  mov     rcx, [rsp+150h+hKey]; hKey
0x18005b872  lea     r9, [rsp+150h+cchName]; lpcchName
0x18005b877  lea     r8, [rsp+150h+SubKey]; lpName
0x18005b87c  mov     [rsp+150h+cchName], 60h ; '`'
0x18005b884  call    cs:__imp_RegEnumKeyExW
0x18005b88b  nop     dword ptr [rax+rax+00h]
0x18005b890  test    eax, eax
0x18005b892  jz      loc_18005B7C4
0x18005b898  mov     rcx, [rsp+150h+hKey]; hKey
0x18005b89d  mov     [rsi], ebx
0x18005b89f  call    cs:__imp_RegCloseKey
0x18005b8a6  nop     dword ptr [rax+rax+00h]
0x18005b8ab  xor     eax, eax
0x18005b8ad  mov     rcx, [rbp+50h+var_30]
0x18005b8b1  xor     rcx, rsp; StackCookie
0x18005b8b4  call    __security_check_cookie
0x18005b8b9  mov     rbx, [rsp+150h+arg_10]
0x18005b8c1  add     rsp, 130h
0x18005b8c8  pop     r15
0x18005b8ca  pop     r14
0x18005b8cc  pop     rdi
0x18005b8cd  pop     rsi
0x18005b8ce  pop     rbp
0x18005b8cf  retn
```
