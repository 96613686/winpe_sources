# GetLocationList

- ea: `0x18005d5c4`
- end: `0x18005d774`
- name: `GetLocationList`
- size: `432`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18005d988`

## callees

- `0x18005cfc4`
- `0x18005d5c4`
- `0x1800606cc`
- `0x18006070c`
- `0x180060830`
- `0x180060954`
- `0x1800e8ef0`

## import_xrefs

- `msvcrt!_wtol` at `0x18005d67e`
- `msvcrt!_wtol` at `0x18005d67e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005d62a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005d66a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005d62a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005d66a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d6de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d732`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d6de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d732`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005d717`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005d717`

## pseudocode

```c
__int64 __fastcall GetLocationList(HKEY hKey, HGLOBAL *a2)
{
  __int64 result; // rax
  __int64 v5; // rdi
  DWORD v6; // r14d
  DWORD i; // edx
  int v8; // eax
  unsigned int v9; // ebx
  __int64 LocationNode; // rax
  LSTATUS v11; // eax
  DWORD cchName; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v13; // [rsp+44h] [rbp-3Ch] BYREF
  unsigned int v14; // [rsp+48h] [rbp-38h] BYREF
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
          v8 = _wtol(SubKey);
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
0x18005d5c4  mov     [rsp-28h+arg_10], rbx
0x18005d5c9  push    rbp
0x18005d5ca  push    rsi
0x18005d5cb  push    rdi
0x18005d5cc  push    r14
0x18005d5ce  push    r15
0x18005d5d0  mov     rbp, rsp
0x18005d5d3  sub     rsp, 80h
0x18005d5da  mov     rax, cs:__security_cookie
0x18005d5e1  xor     rax, rsp
0x18005d5e4  mov     [rbp+var_8], rax
0x18005d5e8  xor     r15d, r15d
0x18005d5eb  mov     rsi, rdx
0x18005d5ee  mov     [rbp+cchName], r15d
0x18005d5f2  mov     rbx, rcx
0x18005d5f5  mov     [rbp+hKey], r15
0x18005d5f9  mov     [rbp+var_28], r15
0x18005d5fd  call    DtlCreateList
0x18005d602  mov     rdi, rax
0x18005d605  test    rax, rax
0x18005d608  jz      loc_18005D750
0x18005d60e  lea     rax, [rbp+hKey]
0x18005d612  mov     r9d, 20019h; samDesired
0x18005d618  xor     r8d, r8d; ulOptions
0x18005d61b  mov     [rsp+80h+phkResult], rax; phkResult
0x18005d620  lea     rdx, aLocation; "Location"
0x18005d627  mov     rcx, rbx; hKey
0x18005d62a  call    cs:__imp_RegOpenKeyExW
0x18005d631  nop     dword ptr [rax+rax+00h]
0x18005d636  test    eax, eax
0x18005d638  jnz     loc_18005D73E
0x18005d63e  mov     r14d, r15d
0x18005d641  xor     edx, edx
0x18005d643  jmp     loc_18005D6F0
0x18005d648  test    eax, eax
0x18005d64a  jnz     loc_18005D6EA
0x18005d650  mov     rcx, [rbp+hKey]; hKey
0x18005d654  lea     rax, [rbp+var_28]
0x18005d658  mov     r9d, 20019h; samDesired
0x18005d65e  mov     [rsp+80h+phkResult], rax; phkResult
0x18005d663  xor     r8d, r8d; ulOptions
0x18005d666  lea     rdx, [rbp+SubKey]; lpSubKey
0x18005d66a  call    cs:__imp_RegOpenKeyExW
0x18005d671  nop     dword ptr [rax+rax+00h]
0x18005d676  test    eax, eax
0x18005d678  jnz     short loc_18005D6EA
0x18005d67a  lea     rcx, [rbp+SubKey]; String
0x18005d67e  call    cs:__imp__wtol
0x18005d685  nop     dword ptr [rax+rax+00h]
0x18005d68a  mov     rcx, [rbp+var_28]
0x18005d68e  lea     r8, [rbp+var_38]
0x18005d692  lea     rdx, aPrefix; "Prefix"
0x18005d699  mov     [rbp+var_38], r15d
0x18005d69d  mov     ebx, eax
0x18005d69f  call    GetRegDword
0x18005d6a4  mov     rcx, [rbp+var_28]
0x18005d6a8  lea     r8, [rbp+var_3C]
0x18005d6ac  lea     rdx, aSuffix; "Suffix"
0x18005d6b3  mov     [rbp+var_3C], r15d
0x18005d6b7  call    GetRegDword
0x18005d6bc  mov     r8d, [rbp+var_3C]
0x18005d6c0  mov     ecx, ebx
0x18005d6c2  mov     edx, [rbp+var_38]
0x18005d6c5  call    CreateLocationNode
0x18005d6ca  test    rax, rax
0x18005d6cd  jz      short loc_18005D6EA
0x18005d6cf  mov     rdx, rax
0x18005d6d2  mov     rcx, rdi
0x18005d6d5  call    DtlAddNodeLast
0x18005d6da  mov     rcx, [rbp+var_28]; hKey
0x18005d6de  call    cs:__imp_RegCloseKey
0x18005d6e5  nop     dword ptr [rax+rax+00h]
0x18005d6ea  inc     r14d
0x18005d6ed  mov     edx, r14d; dwIndex
0x18005d6f0  mov     rcx, [rbp+hKey]; hKey
0x18005d6f4  lea     r9, [rbp+cchName]; lpcchName
0x18005d6f8  mov     [rsp+80h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18005d6fd  lea     r8, [rbp+SubKey]; lpName
0x18005d701  mov     [rsp+80h+lpcchClass], r15; lpcchClass
0x18005d706  mov     [rsp+80h+lpClass], r15; lpClass
0x18005d70b  mov     [rsp+80h+phkResult], r15; lpReserved
0x18005d710  mov     [rbp+cchName], 0Ch
0x18005d717  call    cs:__imp_RegEnumKeyExW
0x18005d71e  nop     dword ptr [rax+rax+00h]
0x18005d723  cmp     eax, 103h
0x18005d728  jnz     loc_18005D648
0x18005d72e  mov     rcx, [rbp+hKey]; hKey
0x18005d732  call    cs:__imp_RegCloseKey
0x18005d739  nop     dword ptr [rax+rax+00h]
0x18005d73e  mov     rcx, [rsi]; hMem
0x18005d741  lea     rdx, DestroyEntryTypeNode
0x18005d748  call    DtlDestroyList
0x18005d74d  mov     [rsi], rdi
0x18005d750  mov     rcx, [rbp+var_8]
0x18005d754  xor     rcx, rsp; StackCookie
0x18005d757  call    __security_check_cookie
0x18005d75c  mov     rbx, [rsp+80h+arg_10]
0x18005d764  add     rsp, 80h
0x18005d76b  pop     r15
0x18005d76d  pop     r14
0x18005d76f  pop     rdi
0x18005d770  pop     rsi
0x18005d771  pop     rbp
0x18005d772  retn
```
