# GetLocationList

- ea: `0x1800c3a64`
- end: `0x1800c3bee`
- name: `GetLocationList`
- size: `394`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800c3e70`

## callees

- `0x1800087b0`
- `0x1800208ec`
- `0x1800300ec`
- `0x180063da4`
- `0x1800c3498`
- `0x1800c3a64`
- `0x1800c4f8c`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800c3b9e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800c3b9e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c3aca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c3b04`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c3aca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c3b04`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c3b6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c3bb3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c3b6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c3bb3`

## pseudocode

```c
__int64 __fastcall GetLocationList(HKEY hKey, HGLOBAL *a2)
{
  __int64 result; // rax
  __int64 v5; // rdi
  DWORD v6; // r14d
  DWORD i; // edx
  int v8; // eax
  int v9; // ebx
  __int64 LocationNode; // rax
  LSTATUS v11; // eax
  DWORD cchName; // [rsp+40h] [rbp-40h] BYREF
  int v13; // [rsp+44h] [rbp-3Ch] BYREF
  int v14; // [rsp+48h] [rbp-38h] BYREF
  HKEY hKeya; // [rsp+50h] [rbp-30h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-28h] BYREF
  WCHAR SubKey[12]; // [rsp+60h] [rbp-20h] BYREF

  cchName = 0;
  hKeya = 0;
  phkResult = 0;
  result = DtlCreateList(hKey);
  v5 = result;
  if ( result )
  {
    if ( !RegOpenKeyExW(hKey, L"Location", 0, 0x20019u, &hKeya) )
    {
      v6 = 0;
      for ( i = 0; ; i = v6 )
      {
        cchName = 12;
        v11 = RegEnumKeyExW(hKeya, i, SubKey, &cchName, 0, 0, 0, 0);
        if ( v11 == 259 )
          break;
        if ( !v11 && !RegOpenKeyExW(hKeya, SubKey, 0, 0x20019u, &phkResult) )
        {
          v8 = wtol_0(SubKey);
          v14 = 0;
          v9 = v8;
          GetRegDword(phkResult, L"Prefix", &v14);
          v13 = 0;
          GetRegDword(phkResult, L"Suffix", &v13);
          LocationNode = CreateLocationNode(v9, v14, v13);
          if ( LocationNode )
          {
            DtlAddNodeLast(v5, LocationNode);
            RegCloseKey(phkResult);
          }
        }
        ++v6;
      }
      RegCloseKey(hKeya);
    }
    result = DtlDestroyList(*a2);
    *a2 = (HGLOBAL)v5;
  }
  return result;
}

```

## disassembly

```asm
0x1800c3a64  mov     [rsp-28h+arg_10], rbx
0x1800c3a69  push    rbp
0x1800c3a6a  push    rsi
0x1800c3a6b  push    rdi
0x1800c3a6c  push    r14
0x1800c3a6e  push    r15
0x1800c3a70  mov     rbp, rsp
0x1800c3a73  sub     rsp, 80h
0x1800c3a7a  mov     rax, cs:__security_cookie
0x1800c3a81  xor     rax, rsp
0x1800c3a84  mov     [rbp+var_8], rax
0x1800c3a88  xor     r15d, r15d
0x1800c3a8b  mov     rsi, rdx
0x1800c3a8e  mov     [rbp+cchName], r15d
0x1800c3a92  mov     rbx, rcx
0x1800c3a95  mov     [rbp+hKey], r15
0x1800c3a99  mov     [rbp+var_28], r15
0x1800c3a9d  call    DtlCreateList
0x1800c3aa2  mov     rdi, rax
0x1800c3aa5  test    rax, rax
0x1800c3aa8  jz      loc_1800C3BCB
0x1800c3aae  lea     rax, [rbp+hKey]
0x1800c3ab2  mov     r9d, 20019h; samDesired
0x1800c3ab8  xor     r8d, r8d; ulOptions
0x1800c3abb  mov     [rsp+80h+phkResult], rax; phkResult
0x1800c3ac0  lea     rdx, aLocation; "Location"
0x1800c3ac7  mov     rcx, rbx; hKey
0x1800c3aca  call    cs:__imp_RegOpenKeyExW
0x1800c3ad0  test    eax, eax
0x1800c3ad2  jnz     loc_1800C3BB9
0x1800c3ad8  mov     r14d, r15d
0x1800c3adb  xor     edx, edx
0x1800c3add  jmp     loc_1800C3B77
0x1800c3ae2  test    eax, eax
0x1800c3ae4  jnz     loc_1800C3B71
0x1800c3aea  mov     rcx, [rbp+hKey]; hKey
0x1800c3aee  lea     rax, [rbp+var_28]
0x1800c3af2  mov     r9d, 20019h; samDesired
0x1800c3af8  mov     [rsp+80h+phkResult], rax; phkResult
0x1800c3afd  xor     r8d, r8d; ulOptions
0x1800c3b00  lea     rdx, [rbp+SubKey]; lpSubKey
0x1800c3b04  call    cs:__imp_RegOpenKeyExW
0x1800c3b0a  test    eax, eax
0x1800c3b0c  jnz     short loc_1800C3B71
0x1800c3b0e  lea     rcx, [rbp+SubKey]; String
0x1800c3b12  call    _wtol_0
0x1800c3b17  mov     rcx, [rbp+var_28]
0x1800c3b1b  lea     r8, [rbp+var_38]
0x1800c3b1f  lea     rdx, aPrefix; "Prefix"
0x1800c3b26  mov     [rbp+var_38], r15d
0x1800c3b2a  mov     ebx, eax
0x1800c3b2c  call    GetRegDword
0x1800c3b31  mov     rcx, [rbp+var_28]
0x1800c3b35  lea     r8, [rbp+var_3C]
0x1800c3b39  lea     rdx, aSuffix; "Suffix"
0x1800c3b40  mov     [rbp+var_3C], r15d
0x1800c3b44  call    GetRegDword
0x1800c3b49  mov     r8d, [rbp+var_3C]
0x1800c3b4d  mov     ecx, ebx
0x1800c3b4f  mov     edx, [rbp+var_38]
0x1800c3b52  call    CreateLocationNode
0x1800c3b57  test    rax, rax
0x1800c3b5a  jz      short loc_1800C3B71
0x1800c3b5c  mov     rdx, rax
0x1800c3b5f  mov     rcx, rdi
0x1800c3b62  call    DtlAddNodeLast
0x1800c3b67  mov     rcx, [rbp+var_28]; hKey
0x1800c3b6b  call    cs:__imp_RegCloseKey
0x1800c3b71  inc     r14d
0x1800c3b74  mov     edx, r14d; dwIndex
0x1800c3b77  mov     rcx, [rbp+hKey]; hKey
0x1800c3b7b  lea     r9, [rbp+cchName]; lpcchName
0x1800c3b7f  mov     [rsp+80h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800c3b84  lea     r8, [rbp+SubKey]; lpName
0x1800c3b88  mov     [rsp+80h+lpcchClass], r15; lpcchClass
0x1800c3b8d  mov     [rsp+80h+lpClass], r15; lpClass
0x1800c3b92  mov     [rsp+80h+phkResult], r15; lpReserved
0x1800c3b97  mov     [rbp+cchName], 0Ch
0x1800c3b9e  call    cs:__imp_RegEnumKeyExW
0x1800c3ba4  cmp     eax, 103h
0x1800c3ba9  jnz     loc_1800C3AE2
0x1800c3baf  mov     rcx, [rbp+hKey]; hKey
0x1800c3bb3  call    cs:__imp_RegCloseKey
0x1800c3bb9  mov     rcx, [rsi]; hMem
0x1800c3bbc  lea     rdx, DestroyEntryTypeNode
0x1800c3bc3  call    DtlDestroyList
0x1800c3bc8  mov     [rsi], rdi
0x1800c3bcb  mov     rcx, [rbp+var_8]
0x1800c3bcf  xor     rcx, rsp; StackCookie
0x1800c3bd2  call    __security_check_cookie
0x1800c3bd7  mov     rbx, [rsp+80h+arg_10]
0x1800c3bdf  add     rsp, 80h
0x1800c3be6  pop     r15
0x1800c3be8  pop     r14
0x1800c3bea  pop     rdi
0x1800c3beb  pop     rsi
0x1800c3bec  pop     rbp
0x1800c3bed  retn
```
