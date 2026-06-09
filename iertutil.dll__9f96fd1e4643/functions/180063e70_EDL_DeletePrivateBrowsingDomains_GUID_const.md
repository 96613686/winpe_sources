# EDL_DeletePrivateBrowsingDomains(_GUID const &)

- ea: `0x180063e70`
- end: `0x180063fa0`
- name: `?EDL_DeletePrivateBrowsingDomains@@YAJAEBU_GUID@@@Z`
- size: `304`
- prototype: `__int64 __fastcall(const struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180063d30`

## callees

- `0x180063e70`
- `0x18006441c`
- `0x180083c10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180063f21`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180063f21`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180063f4f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180063f4f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180063ef1`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180063ef1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063f5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063f7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063f5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180063f7d`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180063f70`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180063f70`

## string_xrefs

- `0x180063f30`: `AddedDuringPrivateBrowsing`

## pseudocode

```c
__int64 __fastcall EDL_DeletePrivateBrowsingDomains(const struct _GUID *a1, unsigned int a2)
{
  unsigned int v2; // esi
  DWORD i; // edi
  LSTATUS Value; // ebx
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  v2 = OpenAllowedDomainsKey(a1, a2, &hKey);
  if ( !v2 )
  {
    for ( i = 0; ; ++i )
    {
      cchName = 260;
      if ( RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0) )
        break;
      phkResult = 0;
      if ( !RegOpenKeyExW(hKey, Name, 0, 0x2001Fu, &phkResult) )
      {
        Value = RegQueryValueExW(phkResult, L"AddedDuringPrivateBrowsing", 0, 0, 0, 0);
        RegCloseKey(phkResult);
        if ( !Value )
          RegDeleteKeyW(hKey, Name);
      }
    }
    RegCloseKey(hKey);
  }
  return v2;
}

```

## disassembly

```asm
0x180063e70  push    rbp
0x180063e72  push    rbx
0x180063e73  push    rsi
0x180063e74  push    rdi
0x180063e75  lea     rbp, [rsp-188h]
0x180063e7d  sub     rsp, 288h
0x180063e84  mov     rax, cs:__security_cookie
0x180063e8b  xor     rax, rsp
0x180063e8e  mov     [rbp+1A0h+var_30], rax
0x180063e95  lea     r8, [rsp+2A0h+hKey]; HKEY *
0x180063e9a  mov     [rsp+2A0h+hKey], 0
0x180063ea3  call    ?OpenAllowedDomainsKey@@YAJAEBU_GUID@@KPEAPEAUHKEY__@@@Z; OpenAllowedDomainsKey(_GUID const &,ulong,HKEY__ * *)
0x180063ea8  mov     esi, eax
0x180063eaa  test    eax, eax
0x180063eac  jnz     loc_180063F83
0x180063eb2  xor     edi, edi
0x180063eb4  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180063eb9  lea     r9, [rsp+2A0h+cchName]; lpcchName
0x180063ebe  mov     [rsp+2A0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180063ec7  lea     r8, [rsp+2A0h+Name]; lpName
0x180063ecc  mov     [rsp+2A0h+lpcchClass], 0; lpcchClass
0x180063ed5  mov     edx, edi; dwIndex
0x180063ed7  mov     [rsp+2A0h+lpClass], 0; lpClass
0x180063ee0  mov     [rsp+2A0h+lpReserved], 0; lpReserved
0x180063ee9  mov     [rsp+2A0h+cchName], 104h
0x180063ef1  call    cs:__imp_RegEnumKeyExW
0x180063ef7  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180063efc  test    eax, eax
0x180063efe  jnz     short loc_180063F7D
0x180063f00  lea     rax, [rsp+2A0h+phkResult]
0x180063f05  mov     [rsp+2A0h+phkResult], 0
0x180063f0e  mov     r9d, 2001Fh; samDesired
0x180063f14  mov     [rsp+2A0h+lpReserved], rax; phkResult
0x180063f19  xor     r8d, r8d; ulOptions
0x180063f1c  lea     rdx, [rsp+2A0h+Name]; lpSubKey
0x180063f21  call    cs:__imp_RegOpenKeyExW
0x180063f27  test    eax, eax
0x180063f29  jnz     short loc_180063F76
0x180063f2b  mov     rcx, [rsp+2A0h+phkResult]; hKey
0x180063f30  lea     rdx, aAddedduringpri; "AddedDuringPrivateBrowsing"
0x180063f37  mov     [rsp+2A0h+lpClass], 0; lpcbData
0x180063f40  xor     r9d, r9d; lpType
0x180063f43  xor     r8d, r8d; lpReserved
0x180063f46  mov     [rsp+2A0h+lpReserved], 0; lpData
0x180063f4f  call    cs:__imp_RegQueryValueExW
0x180063f55  mov     rcx, [rsp+2A0h+phkResult]; hKey
0x180063f5a  mov     ebx, eax
0x180063f5c  call    cs:__imp_RegCloseKey
0x180063f62  test    ebx, ebx
0x180063f64  jnz     short loc_180063F76
0x180063f66  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180063f6b  lea     rdx, [rsp+2A0h+Name]; lpSubKey
0x180063f70  call    cs:__imp_RegDeleteKeyW
0x180063f76  inc     edi
0x180063f78  jmp     loc_180063EB4
0x180063f7d  call    cs:__imp_RegCloseKey
0x180063f83  mov     eax, esi
0x180063f85  mov     rcx, [rbp+1A0h+var_30]
0x180063f8c  xor     rcx, rsp; StackCookie
0x180063f8f  call    __security_check_cookie
0x180063f94  add     rsp, 288h
0x180063f9b  pop     rdi
0x180063f9c  pop     rsi
0x180063f9d  pop     rbx
0x180063f9e  pop     rbp
0x180063f9f  retn
```
