# IsProxyRegistrationCorrect

- ea: `0x1800096a0`
- end: `0x1800097ce`
- name: `IsProxyRegistrationCorrect`
- size: `302`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180008870`

## callees

- `0x1800096a0`
- `0x18001e4c0`
- `0x18001efc4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180009766`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180009793`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180009766`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180009793`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009730`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009730`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800097a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800097a2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800096e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800096e6`

## string_xrefs

- `0x1800096d8`: `Interface\{618736E0-3C3D-11CF-810C-00AA00389B71}\ProxyStubClsid32`

## pseudocode

```c
__int64 IsProxyRegistrationCorrect()
{
  unsigned int v0; // ebx
  DWORD Type; // [rsp+30h] [rbp-49h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-45h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-41h] BYREF
  BYTE Data[2]; // [rsp+40h] [rbp-39h] BYREF
  _BYTE v6[124]; // [rsp+42h] [rbp-37h] BYREF
  __int16 v7; // [rsp+BEh] [rbp+45h]

  v0 = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_CLASSES_ROOT,
          L"Interface\\{618736E0-3C3D-11CF-810C-00AA00389B71}\\ProxyStubClsid32",
          0,
          0x20019u,
          &hKey) )
  {
    Type = 0;
    *(_WORD *)Data = 0;
    memset_0(v6, 0, 0x7Eu);
    cbData = 128;
    if ( !RegQueryValueExW(hKey, 0, 0, &Type, Data, &cbData) && Type == 1 )
    {
      v7 = 0;
      if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)Data, -1, L"{00020424-0000-0000-C000-000000000046}", -1) == 2
        || CompareStringW(0x7Fu, 1u, (PCNZWCH)Data, -1, L"{03022430-ABC4-11D0-BDE2-00AA001A1953}", -1) == 2 )
      {
        v0 = 1;
      }
    }
    RegCloseKey(hKey);
  }
  return v0;
}

```

## disassembly

```asm
0x1800096a0  mov     [rsp-8+arg_0], rbx
0x1800096a5  push    rbp
0x1800096a6  lea     rbp, [rsp-57h]
0x1800096ab  sub     rsp, 0D0h
0x1800096b2  mov     rax, cs:__security_cookie
0x1800096b9  xor     rax, rsp
0x1800096bc  mov     [rbp+57h+var_10], rax
0x1800096c0  lea     rax, [rbp+57h+hKey]
0x1800096c4  xor     ebx, ebx
0x1800096c6  mov     r9d, 20019h; samDesired
0x1800096cc  mov     [rbp+57h+hKey], rbx
0x1800096d0  xor     r8d, r8d; ulOptions
0x1800096d3  mov     [rsp+0D0h+phkResult], rax; phkResult
0x1800096d8  lea     rdx, SubKey; "Interface\\{618736E0-3C3D-11CF-810C-00A"...
0x1800096df  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800096e6  call    cs:__imp_RegOpenKeyExW
0x1800096ec  test    eax, eax
0x1800096ee  jnz     loc_1800097A8
0x1800096f4  xor     edx, edx; Val
0x1800096f6  mov     [rbp+57h+Type], ebx
0x1800096f9  lea     r8d, [rbx+7Eh]; Size
0x1800096fd  mov     word ptr [rbp+57h+Data], ax
0x180009701  lea     rcx, [rbp+57h+var_8E]; void *
0x180009705  call    memset_0
0x18000970a  mov     rcx, [rbp+57h+hKey]; hKey
0x18000970e  lea     rax, [rbp+57h+cbData]
0x180009712  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x180009717  lea     r9, [rbp+57h+Type]; lpType
0x18000971b  lea     rax, [rbp+57h+Data]
0x18000971f  mov     [rbp+57h+cbData], 80h
0x180009726  xor     r8d, r8d; lpReserved
0x180009729  mov     [rsp+0D0h+phkResult], rax; lpData
0x18000972e  xor     edx, edx; lpValueName
0x180009730  call    cs:__imp_RegQueryValueExW
0x180009736  test    eax, eax
0x180009738  jnz     short loc_18000979E
0x18000973a  cmp     [rbp+57h+Type], 1
0x18000973e  jnz     short loc_18000979E
0x180009740  mov     [rbp+57h+var_12], ax
0x180009744  lea     r8, [rbp+57h+Data]; lpString1
0x180009748  lea     rax, a00020424000000; "{00020424-0000-0000-C000-000000000046}"
0x18000974f  mov     dword ptr [rsp+0D0h+lpcbData], 0FFFFFFFFh; cchCount2
0x180009757  or      r9d, 0FFFFFFFFh; cchCount1
0x18000975b  mov     [rsp+0D0h+phkResult], rax; lpString2
0x180009760  lea     edx, [rbx+1]; dwCmpFlags
0x180009763  lea     ecx, [rbx+7Fh]; Locale
0x180009766  call    cs:__imp_CompareStringW
0x18000976c  cmp     eax, 2
0x18000976f  jz      short loc_1800097C7
0x180009771  lea     rax, a03022430Abc411; "{03022430-ABC4-11D0-BDE2-00AA001A1953}"
0x180009778  mov     dword ptr [rsp+0D0h+lpcbData], 0FFFFFFFFh; cchCount2
0x180009780  or      r9d, 0FFFFFFFFh; cchCount1
0x180009784  mov     [rsp+0D0h+phkResult], rax; lpString2
0x180009789  lea     r8, [rbp+57h+Data]; lpString1
0x18000978d  lea     edx, [rbx+1]; dwCmpFlags
0x180009790  lea     ecx, [rbx+7Fh]; Locale
0x180009793  call    cs:__imp_CompareStringW
0x180009799  cmp     eax, 2
0x18000979c  jz      short loc_1800097C7
0x18000979e  mov     rcx, [rbp+57h+hKey]; hKey
0x1800097a2  call    cs:__imp_RegCloseKey
0x1800097a8  mov     eax, ebx
0x1800097aa  mov     rcx, [rbp+57h+var_10]
0x1800097ae  xor     rcx, rsp; StackCookie
0x1800097b1  call    __security_check_cookie
0x1800097b6  mov     rbx, [rsp+0D0h+arg_0]
0x1800097be  add     rsp, 0D0h
0x1800097c5  pop     rbp
0x1800097c6  retn
0x1800097c7  mov     ebx, 1
0x1800097cc  jmp     short loc_18000979E
```
