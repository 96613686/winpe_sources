# NdrpRegisterInterface(HKEY__ *,_GUID const &,char const *,char const *,long,_GUID const *)

- ea: `0x180101e4c`
- end: `0x1801020c4`
- name: `?NdrpRegisterInterface@@YAJPEAUHKEY__@@AEBU_GUID@@PEBD2JPEBU2@@Z`
- size: `632`
- prototype: `__int64 __fastcall(HKEY hKeyInterface, const _GUID *riid, const BYTE *pszInterfaceName, const BYTE *pszClassID, unsigned int NumMethods, const _GUID *riidAsync)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18015abf0`

## callees

- `0x180101e4c`
- `0x1801020cc`
- `0x1801999b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itoa_s` at `0x180102065`
- `api-ms-win-crt-private-l1-1-0!_o__itoa_s` at `0x180102065`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180101eec`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180101f35`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180102046`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x18024c571`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180101eec`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180101f35`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180102046`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x18024c571`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180101f77`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180102001`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18010209b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18024c5bb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180101f77`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180102001`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18010209b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18024c5bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180101f83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180101f9a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801020a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18024c5c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180101f83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180101f9a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801020a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18024c5c7`

## string_xrefs

- `0x180101f1c`: `ProxyStubClsid32`

## pseudocode

```c
__int64 __fastcall NdrpRegisterInterface(
        HKEY hKeyInterface,
        const _GUID *riid,
        const BYTE *pszInterfaceName,
        const BYTE *pszClassID,
        unsigned int NumMethods,
        const _GUID *riidAsync)
{
  LSTATUS v9; // ebx
  __int64 v10; // rdi
  __int64 v11; // rax
  bool v12; // cc
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned int dwDisposition; // [rsp+50h] [rbp-39h] BYREF
  HKEY__ *hKey; // [rsp+58h] [rbp-31h] BYREF
  HKEY__ *hKeyIID; // [rsp+60h] [rbp-29h] BYREF
  BYTE szNumMethods[8]; // [rsp+68h] [rbp-21h] BYREF
  BYTE szIID[40]; // [rsp+70h] [rbp-19h] BYREF

  dwDisposition = 0;
  hKey = 0;
  hKeyIID = 0;
  memset(szIID, 0, 39);
  v9 = NdrStringFromIID(riid, (char *)szIID);
  if ( v9 >= 0 )
  {
    v9 = RegCreateKeyExA(hKeyInterface, (LPCSTR)szIID, 0, (LPSTR)"REG_SZ", 0, 0x20006u, 0, &hKeyIID, &dwDisposition);
    if ( v9 )
    {
      v12 = v9 < 0;
    }
    else
    {
      v10 = -1;
      v9 = RegCreateKeyExA(hKeyIID, "ProxyStubClsid32", 0, (LPSTR)"REG_SZ", 0, 0x20006u, 0, &hKey, &dwDisposition);
      if ( !v9 )
      {
        v11 = -1;
        do
          ++v11;
        while ( pszClassID[v11] );
        v9 = RegSetValueExA(hKey, Description4, 0, 1u, pszClassID, v11 + 1);
        RegCloseKey(hKey);
        if ( !v9 )
        {
          if ( !pszInterfaceName )
            goto LABEL_17;
          v14 = -1;
          do
            ++v14;
          while ( pszInterfaceName[v14] );
          v9 = RegSetValueExA(hKeyIID, Description4, 0, 1u, pszInterfaceName, v14 + 1);
          if ( !v9 )
          {
LABEL_17:
            v9 = RegCreateKeyExA(hKeyIID, "NumMethods", 0, (LPSTR)"REG_SZ", 0, 0x20006u, 0, &hKey, &dwDisposition);
            if ( !v9 )
            {
              _o__itoa_s(NumMethods, szNumMethods, 6, 10);
              v15 = -1;
              do
                ++v15;
              while ( szNumMethods[v15] );
              v9 = RegSetValueExA(hKey, Description4, 0, 1u, szNumMethods, v15 + 1);
              RegCloseKey(hKey);
            }
          }
        }
      }
      if ( riidAsync )
      {
        if ( !v9 )
        {
          v9 = RegCreateKeyExA(
                 hKeyIID,
                 "AsynchronousInterface",
                 0,
                 (LPSTR)"REG_SZ",
                 0,
                 0x20006u,
                 0,
                 &hKey,
                 &dwDisposition);
          if ( !v9 )
          {
            NdrStringFromIID(riidAsync, (char *)szIID);
            do
              ++v10;
            while ( szIID[v10] );
            v9 = RegSetValueExA(hKey, Description4, 0, 1u, szIID, v10 + 1);
            RegCloseKey(hKey);
          }
        }
      }
      RegCloseKey(hKeyIID);
      v12 = v9 <= 0;
      if ( !v9 )
        return 0;
    }
    if ( !v12 )
      return (unsigned __int16)v9 | 0x80070000;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180101e4c  push    rbp
0x180101e4e  push    rbx
0x180101e4f  push    rsi
0x180101e50  push    rdi
0x180101e51  push    r12
0x180101e53  push    r14
0x180101e55  push    r15
0x180101e57  lea     rbp, [rsp-17h]
0x180101e5c  sub     rsp, 0A0h
0x180101e63  mov     rax, cs:__security_cookie
0x180101e6a  xor     rax, rsp
0x180101e6d  mov     [rbp+47h+var_38], rax
0x180101e71  mov     r15, [rbp+47h+rclsid]
0x180101e75  mov     rdi, hKeyInterface
0x180101e78  xorps   xmm0, xmm0
0x180101e7b  xor     ecx, ecx
0x180101e7d  mov     rax, riid
0x180101e80  xor     r12d, r12d
0x180101e83  movups  xmmword ptr [rbp+47h+szIID+10h], xmm0
0x180101e87  mov     qword ptr [rbp+47h+szIID+1Fh], hKeyInterface
0x180101e8b  lea     riid, [rbp+47h+szIID]; lpsz
0x180101e8f  mov     hKeyInterface, rax; rclsid
0x180101e92  mov     [rbp+47h+dwDisposition], r12d
0x180101e96  mov     r14, pszClassID
0x180101e99  mov     [rbp+47h+hKey], r12
0x180101e9d  mov     rsi, pszInterfaceName
0x180101ea0  mov     [rbp+47h+hKeyIID], r12
0x180101ea4  movups  xmmword ptr [rbp+47h+szIID], xmm0
0x180101ea8  call    NdrStringFromIID
0x180101ead  mov     ebx, eax
0x180101eaf  test    eax, eax
0x180101eb1  js      loc_180101FA7
0x180101eb7  lea     rax, [rbp+47h+dwDisposition]
0x180101ebb  xor     r8d, r8d; Reserved
0x180101ebe  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x180101ec3  lea     pszClassID, Class; "REG_SZ"
0x180101eca  lea     rax, [rbp+47h+hKeyIID]
0x180101ece  mov     hKeyInterface, rdi; hKey
0x180101ed1  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180101ed6  lea     riid, [rbp+47h+szIID]; lpSubKey
0x180101eda  mov     [rsp+0D0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180101edf  mov     [rsp+0D0h+samDesired], 20006h; samDesired
0x180101ee7  mov     [rsp+0D0h+dwOptions], r12d; dwOptions
0x180101eec  call    cs:__imp_RegCreateKeyExA
0x180101ef2  mov     ebx, eax
0x180101ef4  test    eax, eax
0x180101ef6  jnz     loc_1801020BD
0x180101efc  mov     hKeyInterface, [rbp+47h+hKeyIID]; hKey
0x180101f00  lea     rax, [rbp+47h+dwDisposition]
0x180101f04  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x180101f09  lea     pszClassID, Class; "REG_SZ"
0x180101f10  lea     rax, [rbp+47h+hKey]
0x180101f14  xor     r8d, r8d; Reserved
0x180101f17  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180101f1c  lea     riid, aProxystubclsid_1; "ProxyStubClsid32"
0x180101f23  mov     [rsp+0D0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180101f28  mov     [rsp+0D0h+samDesired], 20006h; samDesired
0x180101f30  mov     [rsp+0D0h+dwOptions], r12d; dwOptions
0x180101f35  call    cs:__imp_RegCreateKeyExA
0x180101f3b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180101f3f  mov     ebx, eax
0x180101f41  test    eax, eax
0x180101f43  jnz     loc_1801020B2
0x180101f49  mov     rax, rdi
0x180101f4c  inc     rax
0x180101f4f  cmp     [r14+rax], r12b
0x180101f53  jnz     short loc_180101F4C
0x180101f55  mov     hKeyInterface, [rbp+47h+hKey]; hKey
0x180101f59  lea     riid, Description4; lpValueName
0x180101f60  inc     eax
0x180101f62  xor     r8d, r8d; Reserved
0x180101f65  mov     [rsp+0D0h+samDesired], eax; cbData
0x180101f69  mov     qword ptr [rsp+0D0h+dwOptions], r14; lpData
0x180101f6e  mov     r14d, 1
0x180101f74  mov     r9d, r14d; dwType
0x180101f77  call    cs:__imp_RegSetValueExA
0x180101f7d  mov     hKeyInterface, [rbp+47h+hKey]; hKey
0x180101f81  mov     ebx, eax
0x180101f83  call    cs:__imp_RegCloseKey
0x180101f89  test    ebx, ebx
0x180101f8b  jz      short loc_180101FD4
0x180101f8d  test    r15, r15
0x180101f90  jnz     loc_18024C530
0x180101f96  mov     hKeyInterface, [rbp+47h+hKeyIID]; hKey
0x180101f9a  call    cs:__imp_RegCloseKey
0x180101fa0  test    ebx, ebx
0x180101fa2  jnz     short loc_180101FC7
0x180101fa4  mov     ebx, r12d
0x180101fa7  mov     eax, ebx
0x180101fa9  mov     hKeyInterface, [rbp+47h+var_38]
0x180101fad  xor     hKeyInterface, rsp; StackCookie
0x180101fb0  call    __security_check_cookie
0x180101fb5  add     rsp, 0A0h
0x180101fbc  pop     r15
0x180101fbe  pop     r14
0x180101fc0  pop     r12
0x180101fc2  pop     rdi
0x180101fc3  pop     rsi
0x180101fc4  pop     rbx
0x180101fc5  pop     rbp
0x180101fc6  retn
0x180101fc7  jle     short loc_180101FA7
0x180101fc9  movzx   ebx, bx
0x180101fcc  or      ebx, 80070000h
0x180101fd2  jmp     short loc_180101FA7
0x180101fd4  test    rsi, rsi
0x180101fd7  jz      short loc_18010200D
0x180101fd9  mov     rax, rdi
0x180101fdc  inc     rax
0x180101fdf  cmp     [rsi+rax], r12b
0x180101fe3  jnz     short loc_180101FDC
0x180101fe5  mov     hKeyInterface, [rbp+47h+hKeyIID]; hKey
0x180101fe9  lea     riid, Description4; lpValueName
0x180101ff0  inc     eax
0x180101ff2  mov     r9d, r14d; dwType
0x180101ff5  mov     [rsp+0D0h+samDesired], eax; cbData
0x180101ff9  xor     r8d, r8d; Reserved
0x180101ffc  mov     qword ptr [rsp+0D0h+dwOptions], rsi; lpData
0x180102001  call    cs:__imp_RegSetValueExA
0x180102007  mov     ebx, eax
0x180102009  test    eax, eax
0x18010200b  jnz     short loc_180101F8D
0x18010200d  mov     hKeyInterface, [rbp+47h+hKeyIID]; hKey
0x180102011  lea     rax, [rbp+47h+dwDisposition]
0x180102015  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x18010201a  lea     pszClassID, Class; "REG_SZ"
0x180102021  lea     rax, [rbp+47h+hKey]
0x180102025  xor     r8d, r8d; Reserved
0x180102028  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18010202d  lea     riid, aNummethods; "NumMethods"
0x180102034  mov     [rsp+0D0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180102039  mov     [rsp+0D0h+samDesired], 20006h; samDesired
0x180102041  mov     [rsp+0D0h+dwOptions], r12d; dwOptions
0x180102046  call    cs:__imp_RegCreateKeyExA
0x18010204c  mov     ebx, eax
0x18010204e  test    eax, eax
0x180102050  jnz     loc_180101F8D
0x180102056  mov     ecx, [rbp+47h+arg_20]
0x180102059  lea     r9d, [rax+0Ah]
0x18010205d  lea     r8d, [rax+6]
0x180102061  lea     riid, [rbp+47h+szNumMethods]
0x180102065  call    cs:__imp__o__itoa_s
0x18010206b  lea     hKeyInterface, [rbp+47h+szNumMethods]
0x18010206f  mov     rax, rdi
0x180102072  inc     rax
0x180102075  cmp     [hKeyInterface+rax], r12b
0x180102079  jnz     short loc_180102072
0x18010207b  mov     hKeyInterface, [rbp+47h+hKey]; hKey
0x18010207f  lea     riid, Description4; lpValueName
0x180102086  inc     eax
0x180102088  mov     r9d, r14d; dwType
0x18010208b  mov     [rsp+0D0h+samDesired], eax; cbData
0x18010208f  xor     r8d, r8d; Reserved
0x180102092  lea     rax, [rbp+47h+szNumMethods]
0x180102096  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpData
0x18010209b  call    cs:__imp_RegSetValueExA
0x1801020a1  mov     hKeyInterface, [rbp+47h+hKey]; hKey
0x1801020a5  mov     ebx, eax
0x1801020a7  call    cs:__imp_RegCloseKey
0x1801020ad  jmp     loc_180101F8D
0x1801020b2  mov     r14d, 1
0x1801020b8  jmp     loc_180101F8D
0x1801020bd  test    ebx, ebx
0x1801020bf  jmp     loc_180101FC7
0x18024c530  test    ebx, ebx
0x18024c532  jnz     loc_180101F96
0x18024c538  mov     rcx, [rbp+47h+hKeyIID]; hKey
0x18024c53c  lea     rax, [rbp+47h+dwDisposition]
0x18024c540  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x18024c545  lea     r9, Class; "REG_SZ"
0x18024c54c  lea     rax, [rbp+47h+hKey]
0x18024c550  xor     r8d, r8d; Reserved
0x18024c553  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18024c558  lea     rdx, aAsynchronousin_0; "AsynchronousInterface"
0x18024c55f  mov     [rsp+0D0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18024c564  mov     [rsp+0D0h+samDesired], 20006h; samDesired
0x18024c56c  mov     [rsp+0D0h+dwOptions], r12d; dwOptions
0x18024c571  call    cs:__imp_RegCreateKeyExA
0x18024c577  mov     ebx, eax
0x18024c579  test    eax, eax
0x18024c57b  jnz     loc_180101F96
0x18024c581  lea     rdx, [rbp+47h+szIID]; lpsz
0x18024c585  mov     rcx, r15; rclsid
0x18024c588  call    NdrStringFromIID
0x18024c58d  lea     rax, [rbp+47h+szIID]
0x18024c591  inc     rdi
0x18024c594  cmp     [rax+rdi], r12b
0x18024c598  jnz     short loc_18024C591
0x18024c59a  mov     rcx, [rbp+47h+hKey]; hKey
0x18024c59e  lea     eax, [rdi+1]
0x18024c5a1  mov     [rsp+0D0h+samDesired], eax; cbData
0x18024c5a5  lea     rdx, Description4; lpValueName
0x18024c5ac  lea     rax, [rbp+47h+szIID]
0x18024c5b0  mov     r9d, r14d; dwType
0x18024c5b3  xor     r8d, r8d; Reserved
0x18024c5b6  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpData
0x18024c5bb  call    cs:__imp_RegSetValueExA
0x18024c5c1  mov     rcx, [rbp+47h+hKey]; hKey
0x18024c5c5  mov     ebx, eax
0x18024c5c7  call    cs:__imp_RegCloseKey
0x18024c5cd  nop
0x18024c5ce  jmp     loc_180101F96
```
