# EnumeratePreviousStateEntries

- ea: `0x18005b6e0`
- end: `0x18005b8b1`
- name: `EnumeratePreviousStateEntries`
- size: `465`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18005b8b8`

## callees

- `0x18000d7b0`
- `0x1800190e0`
- `0x18002b4dc`
- `0x18002c824`
- `0x1800400c8`
- `0x18004b630`
- `0x18005b6e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005b864`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005b864`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b819`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b87f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b819`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b87f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005b7da`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005b7da`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005b730`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005b730`

## string_xrefs

- `0x18005b73c`: `System\CurrentControlSet\Services\iphlpsvc\Teredo\PreviousState`
- `0x18005b756`: `Unable to open previous state key. Error = %u`

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
0x18005b6e0  mov     [rsp-8+arg_10], rbx
0x18005b6e5  push    rbp
0x18005b6e6  push    rsi
0x18005b6e7  push    rdi
0x18005b6e8  push    r14
0x18005b6ea  push    r15
0x18005b6ec  lea     rbp, [rsp-30h]
0x18005b6f1  sub     rsp, 130h
0x18005b6f8  mov     rax, cs:__security_cookie
0x18005b6ff  xor     rax, rsp
0x18005b702  mov     [rbp+50h+var_30], rax
0x18005b706  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005b70a  mov     [rsp+150h+cchName], 0
0x18005b712  mov     rsi, rcx
0x18005b715  mov     [rsp+150h+hKey], rax
0x18005b71a  lea     rcx, [rsp+150h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18005b71f  mov     [rsp+150h+var_100], rax
0x18005b724  mov     r14, rdx
0x18005b727  mov     qword ptr [rsp+150h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18005b730  call    cs:__imp_GetSystemTimeAsFileTime
0x18005b737  nop     dword ptr [rax+rax+00h]
0x18005b73c  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\ip"...
0x18005b743  lea     rcx, [rsp+150h+hKey]; phkResult
0x18005b748  call    TeredoCreateRegKey
0x18005b74d  mov     ebx, eax
0x18005b74f  test    eax, eax
0x18005b751  jz      short loc_18005B76E
0x18005b753  mov     r8d, eax
0x18005b756  lea     rdx, aUnableToOpenPr; "Unable to open previous state key. Erro"...
0x18005b75d  mov     ecx, 100000h
0x18005b762  call    EventWriteError0
0x18005b767  mov     eax, ebx
0x18005b769  jmp     loc_18005B88D
0x18005b76e  xor     ebx, ebx
0x18005b770  mov     rax, 0D6BF94D5E57A42BDh
0x18005b77a  mul     qword ptr [rsp+150h+SystemTimeAsFileTime.dwLowDateTime]
0x18005b77f  mov     [rsp+150h+lpftLastWriteTime], rbx
0x18005b784  mov     rdi, rdx
0x18005b787  mov     [rsp+150h+lpcchClass], rbx
0x18005b78c  shr     rdi, 17h
0x18005b790  mov     [rsp+150h+lpClass], rbx
0x18005b795  mov     r15, rdi
0x18005b798  xor     edx, edx
0x18005b79a  mov     [rsp+150h+phkResult], rbx
0x18005b79f  jmp     loc_18005B84D
0x18005b7a4  lea     r9, [rsp+150h+SubKey]
0x18005b7a9  mov     r8d, ebx
0x18005b7ac  lea     rdx, aEnumeratedKeyU; "Enumerated Key %u : %s"
0x18005b7b3  mov     ecx, 100000h
0x18005b7b8  call    EventWrite0
0x18005b7bd  mov     rcx, [rsp+150h+hKey]; hKey
0x18005b7c2  lea     rax, [rsp+150h+var_100]
0x18005b7c7  mov     r9d, 1; samDesired
0x18005b7cd  mov     [rsp+150h+phkResult], rax; phkResult
0x18005b7d2  xor     r8d, r8d; ulOptions
0x18005b7d5  lea     rdx, [rsp+150h+SubKey]; lpSubKey
0x18005b7da  call    cs:__imp_RegOpenKeyExW
0x18005b7e1  nop     dword ptr [rax+rax+00h]
0x18005b7e6  mov     rcx, [rsp+150h+var_100]
0x18005b7eb  lea     rdx, aAddresscreatio; "AddressCreationTimestamp"
0x18005b7f2  mov     r8, r15
0x18005b7f5  call    GetUlongLong
0x18005b7fa  cmp     rax, rdi
0x18005b7fd  jnb     short loc_18005B814
0x18005b7ff  lea     r8, [rsp+150h+SubKey]; pszSrc
0x18005b804  mov     edx, 0FFh; cchDest
0x18005b809  mov     rcx, r14; pszDest
0x18005b80c  mov     rdi, rax
0x18005b80f  call    StringCchCopyW
0x18005b814  mov     rcx, [rsp+150h+var_100]; hKey
0x18005b819  call    cs:__imp_RegCloseKey
0x18005b820  nop     dword ptr [rax+rax+00h]
0x18005b825  mov     [rsp+150h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18005b82e  inc     ebx
0x18005b830  mov     [rsp+150h+lpcchClass], 0; lpcchClass
0x18005b839  mov     edx, ebx; dwIndex
0x18005b83b  mov     [rsp+150h+lpClass], 0; lpClass
0x18005b844  mov     [rsp+150h+phkResult], 0; lpReserved
0x18005b84d  mov     rcx, [rsp+150h+hKey]; hKey
0x18005b852  lea     r9, [rsp+150h+cchName]; lpcchName
0x18005b857  lea     r8, [rsp+150h+SubKey]; lpName
0x18005b85c  mov     [rsp+150h+cchName], 60h ; '`'
0x18005b864  call    cs:__imp_RegEnumKeyExW
0x18005b86b  nop     dword ptr [rax+rax+00h]
0x18005b870  test    eax, eax
0x18005b872  jz      loc_18005B7A4
0x18005b878  mov     rcx, [rsp+150h+hKey]; hKey
0x18005b87d  mov     [rsi], ebx
0x18005b87f  call    cs:__imp_RegCloseKey
0x18005b886  nop     dword ptr [rax+rax+00h]
0x18005b88b  xor     eax, eax
0x18005b88d  mov     rcx, [rbp+50h+var_30]
0x18005b891  xor     rcx, rsp; StackCookie
0x18005b894  call    __security_check_cookie
0x18005b899  mov     rbx, [rsp+150h+arg_10]
0x18005b8a1  add     rsp, 130h
0x18005b8a8  pop     r15
0x18005b8aa  pop     r14
0x18005b8ac  pop     rdi
0x18005b8ad  pop     rsi
0x18005b8ae  pop     rbp
0x18005b8af  retn
```
