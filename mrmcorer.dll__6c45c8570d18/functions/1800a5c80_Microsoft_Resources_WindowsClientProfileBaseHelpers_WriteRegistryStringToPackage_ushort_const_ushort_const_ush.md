# Microsoft::Resources::WindowsClientProfileBaseHelpers::WriteRegistryStringToPackage(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x1800a5c80`
- end: `0x1800a5e1c`
- name: `?WriteRegistryStringToPackage@WindowsClientProfileBaseHelpers@Resources@Microsoft@@UEAAJPEBG000@Z`
- size: `412`
- prototype: `int(Microsoft::Resources::WindowsClientProfileBaseHelpers *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a5b30`
- `0x1800a5b90`
- `0x1800a5bf0`

## callees

- `0x18002c8d0`
- `0x180042f70`
- `0x180065f84`
- `0x1800a5c80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a5d50`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a5d50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a5d5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a5de6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a5d5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a5de6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a5dda`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a5dda`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a5db1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a5db1`

## string_xrefs

- `0x1800a5ccc`: `ResourcesConfig`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::WindowsClientProfileBaseHelpers::WriteRegistryStringToPackage(
        Microsoft::Resources::WindowsClientProfileBaseHelpers *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        BYTE *lpData)
{
  int v8; // ebx
  Microsoft::Resources::WindowsClientProfileBaseHelpers *v9; // rcx
  __int64 v10; // rdx
  bool v12; // sf
  __int64 v13; // rax
  LSTATUS v14; // eax
  bool v15; // sf
  int dwOptions; // [rsp+20h] [rbp-48h]
  HKEY phkResult; // [rsp+50h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]

  phkResult = 0;
  v8 = Microsoft::Resources::WindowsClientProfileBaseHelpers::OpenRegKeyForPackageName(
         this,
         a2,
         a3,
         0x2001Fu,
         &phkResult);
  if ( (unsigned int)(v8 + 2147024894) <= 1 && (unsigned int)DefString_CompareWithOptions(a3, L"ResourcesConfig", 1) )
  {
    hKey = 0;
    v8 = Microsoft::Resources::WindowsClientProfileBaseHelpers::OpenRegKeyForPackageName(v9, a2, 0, 0x2001Fu, &hKey);
    if ( v8 < 0 )
    {
      v10 = 2473;
      goto LABEL_5;
    }
    v8 = RegCreateKeyExW(hKey, a3, 0, 0, 0, 0x2001Fu, 0, &phkResult, 0);
    RegCloseKey(hKey);
    v12 = v8 < 0;
    if ( v8 )
    {
      if ( v8 > 0 )
      {
        v8 = (unsigned __int16)v8 | 0x80070000;
        v12 = v8 < 0;
      }
      if ( !v12 )
        return (unsigned int)v8;
      v10 = 2477;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecoreuap\\base\\mrt\\mrm\\src\\clientprofiles.cpp",
        (const char *)(unsigned int)v8,
        dwOptions);
      return (unsigned int)v8;
    }
  }
  else if ( v8 < 0 )
  {
    v10 = 2481;
    goto LABEL_5;
  }
  v13 = -1;
  do
    ++v13;
  while ( *(_WORD *)&lpData[2 * v13] );
  if ( (_DWORD)v13 )
  {
    v14 = RegSetValueExW(phkResult, a4, 0, 1u, lpData, 2 * v13 + 2);
  }
  else
  {
    v8 = RegDeleteValueW(phkResult, a4);
    if ( !v8 )
      goto LABEL_21;
    v14 = RegSetValueExW(phkResult, a4, 0, 1u, lpData, 2u);
  }
  v8 = v14;
LABEL_21:
  RegCloseKey(phkResult);
  v15 = v8 < 0;
  if ( v8 )
  {
    if ( v8 > 0 )
    {
      v8 = (unsigned __int16)v8 | 0x80070000;
      v15 = v8 < 0;
    }
    if ( !v15 )
      return (unsigned int)v8;
    v10 = 2503;
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x1800a5c80  push    rbp
0x1800a5c82  push    rbx
0x1800a5c83  push    rsi
0x1800a5c84  push    rdi
0x1800a5c85  push    r14
0x1800a5c87  push    r15
0x1800a5c89  mov     rbp, rsp
0x1800a5c8c  sub     rsp, 68h
0x1800a5c90  mov     rsi, r9
0x1800a5c93  lea     rax, [rbp+var_18]
0x1800a5c97  xor     r15d, r15d
0x1800a5c9a  mov     qword ptr [rsp+68h+dwOptions], rax; HKEY *
0x1800a5c9f  mov     r9d, 2001Fh; unsigned int
0x1800a5ca5  mov     [rbp+var_18], r15
0x1800a5ca9  mov     rdi, r8
0x1800a5cac  mov     r14, rdx
0x1800a5caf  call    ?OpenRegKeyForPackageName@WindowsClientProfileBaseHelpers@Resources@Microsoft@@AEAAJPEBG0KPEAPEAUHKEY__@@@Z; Microsoft::Resources::WindowsClientProfileBaseHelpers::OpenRegKeyForPackageName(ushort const *,ushort const *,ulong,HKEY__ * *)
0x1800a5cb4  mov     ebx, eax
0x1800a5cb6  lea     ecx, [rax+7FF8FFFEh]
0x1800a5cbc  cmp     ecx, 1
0x1800a5cbf  ja      loc_1800A5D7C
0x1800a5cc5  lea     r8d, [r15+1]
0x1800a5cc9  mov     rcx, rdi
0x1800a5ccc  lea     rdx, aResourcesconfi; "ResourcesConfig"
0x1800a5cd3  call    DefString_CompareWithOptions
0x1800a5cd8  test    eax, eax
0x1800a5cda  jz      loc_1800A5D7C
0x1800a5ce0  lea     rax, [rbp+hKey]
0x1800a5ce4  mov     [rbp+hKey], r15
0x1800a5ce8  mov     r9d, 2001Fh; unsigned int
0x1800a5cee  mov     qword ptr [rsp+68h+dwOptions], rax; int
0x1800a5cf3  xor     r8d, r8d; unsigned __int16 *
0x1800a5cf6  mov     rdx, r14; unsigned __int16 *
0x1800a5cf9  call    ?OpenRegKeyForPackageName@WindowsClientProfileBaseHelpers@Resources@Microsoft@@AEAAJPEBG0KPEAPEAUHKEY__@@@Z; Microsoft::Resources::WindowsClientProfileBaseHelpers::OpenRegKeyForPackageName(ushort const *,ushort const *,ulong,HKEY__ * *)
0x1800a5cfe  mov     ebx, eax
0x1800a5d00  test    eax, eax
0x1800a5d02  jns     short loc_1800A5D23
0x1800a5d04  mov     edx, 9A9h; void *
0x1800a5d09  mov     rcx, [rbp+30h]; this
0x1800a5d0d  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\mrt\\mrm\\src\\client"...
0x1800a5d14  mov     r9d, ebx; char *
0x1800a5d17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5d1c  mov     eax, ebx
0x1800a5d1e  jmp     loc_1800A5E0F
0x1800a5d23  mov     rcx, [rbp+hKey]; hKey
0x1800a5d27  lea     rax, [rbp+var_18]
0x1800a5d2b  mov     [rsp+68h+lpdwDisposition], r15; lpdwDisposition
0x1800a5d30  xor     r9d, r9d; lpClass
0x1800a5d33  mov     [rsp+68h+phkResult], rax; phkResult
0x1800a5d38  xor     r8d, r8d; Reserved
0x1800a5d3b  mov     [rsp+68h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800a5d40  mov     rdx, rdi; lpSubKey
0x1800a5d43  mov     [rsp+68h+samDesired], 2001Fh; samDesired
0x1800a5d4b  mov     [rsp+68h+dwOptions], r15d; dwOptions
0x1800a5d50  call    cs:__imp_RegCreateKeyExW
0x1800a5d56  mov     rcx, [rbp+hKey]; hKey
0x1800a5d5a  mov     ebx, eax
0x1800a5d5c  call    cs:__imp_RegCloseKey
0x1800a5d62  test    ebx, ebx
0x1800a5d64  jz      short loc_1800A5D87
0x1800a5d66  jle     short loc_1800A5D73
0x1800a5d68  movzx   ebx, bx
0x1800a5d6b  or      ebx, 80070000h
0x1800a5d71  test    ebx, ebx
0x1800a5d73  jns     short loc_1800A5D1C
0x1800a5d75  mov     edx, 9ADh
0x1800a5d7a  jmp     short loc_1800A5D09
0x1800a5d7c  test    ebx, ebx
0x1800a5d7e  jns     short loc_1800A5D87
0x1800a5d80  mov     edx, 9B1h
0x1800a5d85  jmp     short loc_1800A5D09
0x1800a5d87  mov     rdi, [rbp+lpData]
0x1800a5d8b  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a5d8f  inc     rax
0x1800a5d92  cmp     [rdi+rax*2], r15w
0x1800a5d97  jnz     short loc_1800A5D8F
0x1800a5d99  mov     rcx, [rbp+var_18]; hKey
0x1800a5d9d  mov     rdx, rsi; lpValueName
0x1800a5da0  test    eax, eax
0x1800a5da2  jz      short loc_1800A5DB1
0x1800a5da4  lea     eax, ds:2[rax*2]
0x1800a5dab  mov     [rsp+68h+samDesired], eax
0x1800a5daf  jmp     short loc_1800A5DCC
0x1800a5db1  call    cs:__imp_RegDeleteValueW
0x1800a5db7  mov     ebx, eax
0x1800a5db9  test    eax, eax
0x1800a5dbb  jz      short loc_1800A5DE2
0x1800a5dbd  mov     rcx, [rbp+var_18]; hKey
0x1800a5dc1  mov     rdx, rsi; lpValueName
0x1800a5dc4  mov     [rsp+68h+samDesired], 2; cbData
0x1800a5dcc  mov     r9d, 1; dwType
0x1800a5dd2  mov     qword ptr [rsp+68h+dwOptions], rdi; lpData
0x1800a5dd7  xor     r8d, r8d; Reserved
0x1800a5dda  call    cs:__imp_RegSetValueExW
0x1800a5de0  mov     ebx, eax
0x1800a5de2  mov     rcx, [rbp+var_18]; hKey
0x1800a5de6  call    cs:__imp_RegCloseKey
0x1800a5dec  test    ebx, ebx
0x1800a5dee  jz      short loc_1800A5E0D
0x1800a5df0  jle     short loc_1800A5DFD
0x1800a5df2  movzx   ebx, bx
0x1800a5df5  or      ebx, 80070000h
0x1800a5dfb  test    ebx, ebx
0x1800a5dfd  jns     loc_1800A5D1C
0x1800a5e03  mov     edx, 9C7h
0x1800a5e08  jmp     loc_1800A5D09
0x1800a5e0d  xor     eax, eax
0x1800a5e0f  add     rsp, 68h
0x1800a5e13  pop     r15
0x1800a5e15  pop     r14
0x1800a5e17  pop     rdi
0x1800a5e18  pop     rsi
0x1800a5e19  pop     rbx
0x1800a5e1a  pop     rbp
0x1800a5e1b  retn
```
