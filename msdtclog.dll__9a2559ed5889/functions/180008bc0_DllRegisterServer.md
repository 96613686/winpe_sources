# DllRegisterServer

- ea: `0x180008bc0`
- end: `0x180008fa9`
- name: `DllRegisterServer`
- size: `1001`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180008bc0`
- `0x180012830`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x180008f00`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x180008f00`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180008edb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180008edb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008c86`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008d22`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008d2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008d35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008e1c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008e24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008e8d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008f74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008f7f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008f91`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008f9c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008c86`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008d22`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008d2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008d35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008e1c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008e24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008e8d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008f74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008f7f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008f91`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008f9c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180008c47`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180008ce0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180008d6c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180008ddd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180008e5d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180008ec6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180008c47`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180008ce0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180008d6c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180008ddd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180008e5d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180008ec6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180008c77`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180008d13`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180008d9c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180008e0d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180008e7e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180008f60`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180008c77`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180008d13`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180008d9c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180008e0d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180008e7e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180008f60`

## string_xrefs

- `0x180008cbf`: `CLSID`
- `0x180008d48`: `CLSID\{d959f1b0-9e42-11ce-8b97-0080c7a01d7f}`
- `0x180008ed4`: `MsDtcLog.dll`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  LSTATUS v0; // eax
  HKEY v1; // rcx
  LSTATUS v3; // eax
  LSTATUS v4; // eax
  HKEY v5; // rcx
  LSTATUS v6; // eax
  HMODULE ModuleHandleA; // rax
  __int64 v8; // rcx
  CHAR *v9; // rax
  HRESULT v10; // ebx
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v14; // [rsp+68h] [rbp-98h] BYREF
  CHAR Filename[272]; // [rsp+70h] [rbp-90h] BYREF

  phkResult = 0;
  v14 = 0;
  hKey = 0;
  dwDisposition = 0;
  if ( RegCreateKeyExA(
         HKEY_CLASSES_ROOT,
         (LPCSTR)"MSDTC.CLogMgr",
         0,
         (LPSTR)ValueName,
         0,
         0xF003Fu,
         0,
         &hKey,
         &dwDisposition) )
  {
    return -2147418113;
  }
  v0 = RegSetValueExA(hKey, ValueName, 0, 1u, "MSDTC Log Manager", 0x12u);
  v1 = hKey;
  if ( v0 )
    goto LABEL_3;
  if ( RegCreateKeyExA(hKey, "CLSID", 0, (LPSTR)ValueName, 0, 0xF003Fu, 0, &phkResult, &dwDisposition) )
    goto LABEL_6;
  if ( RegSetValueExA(phkResult, ValueName, 0, 1u, "{d959f1b0-9e42-11ce-8b97-0080c7a01d7f}", 0x27u) )
  {
    RegCloseKey(phkResult);
LABEL_6:
    v1 = hKey;
    goto LABEL_3;
  }
  RegCloseKey(phkResult);
  RegCloseKey(hKey);
  if ( RegCreateKeyExA(
         HKEY_CLASSES_ROOT,
         "CLSID\\{d959f1b0-9e42-11ce-8b97-0080c7a01d7f}",
         0,
         (LPSTR)ValueName,
         0,
         0xF003Fu,
         0,
         &phkResult,
         &dwDisposition) )
  {
    return -2147418113;
  }
  v3 = RegSetValueExA(phkResult, ValueName, 0, 1u, "MSDTC Log Manager", 0x12u);
  v1 = phkResult;
  if ( v3 )
  {
LABEL_3:
    RegCloseKey(v1);
    return -2147418113;
  }
  if ( RegCreateKeyExA(phkResult, "ProgID", 0, (LPSTR)ValueName, 0, 0xF003Fu, 0, &hKey, &dwDisposition) )
  {
LABEL_12:
    v1 = phkResult;
    goto LABEL_3;
  }
  v4 = RegSetValueExA(hKey, ValueName, 0, 1u, "MSDTC.CLogMgr", 0xEu);
  v5 = hKey;
  if ( v4 )
    goto LABEL_14;
  RegCloseKey(hKey);
  if ( RegCreateKeyExA(
         phkResult,
         "VersionIndependentProgID",
         0,
         (LPSTR)ValueName,
         0,
         0xF003Fu,
         0,
         &hKey,
         &dwDisposition) )
  {
    goto LABEL_12;
  }
  v6 = RegSetValueExA(hKey, ValueName, 0, 1u, "MSDTC.CLogMgr", 0xEu);
  v5 = hKey;
  if ( v6 )
  {
LABEL_14:
    RegCloseKey(v5);
    goto LABEL_12;
  }
  RegCloseKey(hKey);
  if ( RegCreateKeyExA(phkResult, "InprocServer32", 0, (LPSTR)ValueName, 0, 0xF003Fu, 0, &v14, &dwDisposition) )
    goto LABEL_12;
  ModuleHandleA = GetModuleHandleA("MsDtcLog.dll");
  if ( !ModuleHandleA )
  {
    v5 = v14;
    goto LABEL_14;
  }
  if ( !GetModuleFileNameA(ModuleHandleA, Filename, 0x105u) )
    goto LABEL_26;
  v8 = 261;
  v9 = Filename;
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v8;
  }
  while ( v8 );
  v10 = v8 == 0 ? 0x80070057 : 0;
  if ( !v8 )
    goto LABEL_27;
  if ( RegSetValueExA(v14, ValueName, 0, 1u, (const BYTE *)Filename, v8 != 0 ? 261 - v8 + 1 : 1) )
  {
LABEL_26:
    v10 = -2147418113;
LABEL_27:
    RegCloseKey(v14);
    RegCloseKey(phkResult);
    return v10;
  }
  RegCloseKey(v14);
  RegCloseKey(phkResult);
  return 0;
}

```

## disassembly

```asm
0x180008bc0  push    rbp
0x180008bc2  push    rbx
0x180008bc3  push    rsi
0x180008bc4  push    rdi
0x180008bc5  push    r12
0x180008bc7  push    r14
0x180008bc9  push    r15
0x180008bcb  lea     rbp, [rsp-90h]
0x180008bd3  sub     rsp, 190h
0x180008bda  mov     rax, cs:__security_cookie
0x180008be1  xor     rax, rsp
0x180008be4  mov     [rbp+0C0h+var_40], rax
0x180008beb  xor     esi, esi
0x180008bed  lea     rax, [rsp+1C0h+dwDisposition]
0x180008bf2  mov     [rsp+1C0h+lpdwDisposition], rax; lpdwDisposition
0x180008bf7  lea     r14, ValueName
0x180008bfe  lea     rax, [rsp+1C0h+hKey]
0x180008c03  mov     [rsp+1C0h+var_170], rsi
0x180008c08  mov     [rsp+1C0h+phkResult], rax; phkResult
0x180008c0d  lea     r12, SubKey; "MSDTC.CLogMgr"
0x180008c14  mov     [rsp+1C0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180008c19  mov     ebx, 0F003Fh
0x180008c1e  mov     rdi, 0FFFFFFFF80000000h
0x180008c25  mov     [rsp+1C0h+samDesired], ebx; samDesired
0x180008c29  mov     r9, r14; lpClass
0x180008c2c  mov     [rsp+1C0h+dwOptions], esi; dwOptions
0x180008c30  xor     r8d, r8d; Reserved
0x180008c33  mov     [rsp+1C0h+var_158], rsi
0x180008c38  mov     rdx, r12; lpSubKey
0x180008c3b  mov     [rsp+1C0h+hKey], rsi
0x180008c40  mov     rcx, rdi; hKey
0x180008c43  mov     [rsp+1C0h+dwDisposition], esi
0x180008c47  call    cs:__imp_RegCreateKeyExA
0x180008c4d  test    eax, eax
0x180008c4f  jnz     short loc_180008C8C
0x180008c51  mov     rcx, [rsp+1C0h+hKey]; hKey
0x180008c56  lea     rax, Data; "MSDTC Log Manager"
0x180008c5d  lea     r15d, [rsi+1]
0x180008c61  mov     [rsp+1C0h+samDesired], 12h; cbData
0x180008c69  mov     r9d, r15d; dwType
0x180008c6c  mov     qword ptr [rsp+1C0h+dwOptions], rax; lpData
0x180008c71  xor     r8d, r8d; Reserved
0x180008c74  mov     rdx, r14; lpValueName
0x180008c77  call    cs:__imp_RegSetValueExA
0x180008c7d  mov     rcx, [rsp+1C0h+hKey]; hKey
0x180008c82  test    eax, eax
0x180008c84  jz      short loc_180008CB2
0x180008c86  call    cs:__imp_RegCloseKey
0x180008c8c  mov     eax, 8000FFFFh
0x180008c91  mov     rcx, [rbp+0C0h+var_40]
0x180008c98  xor     rcx, rsp; StackCookie
0x180008c9b  call    __security_check_cookie
0x180008ca0  add     rsp, 190h
0x180008ca7  pop     r15
0x180008ca9  pop     r14
0x180008cab  pop     r12
0x180008cad  pop     rdi
0x180008cae  pop     rsi
0x180008caf  pop     rbx
0x180008cb0  pop     rbp
0x180008cb1  retn
0x180008cb2  lea     rax, [rsp+1C0h+dwDisposition]
0x180008cb7  mov     r9, r14; lpClass
0x180008cba  mov     [rsp+1C0h+lpdwDisposition], rax; lpdwDisposition
0x180008cbf  lea     rdx, aClsid; "CLSID"
0x180008cc6  lea     rax, [rsp+1C0h+var_170]
0x180008ccb  xor     r8d, r8d; Reserved
0x180008cce  mov     [rsp+1C0h+phkResult], rax; phkResult
0x180008cd3  mov     [rsp+1C0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180008cd8  mov     [rsp+1C0h+samDesired], ebx; samDesired
0x180008cdc  mov     [rsp+1C0h+dwOptions], esi; dwOptions
0x180008ce0  call    cs:__imp_RegCreateKeyExA
0x180008ce6  test    eax, eax
0x180008ce8  jz      short loc_180008CF1
0x180008cea  mov     rcx, [rsp+1C0h+hKey]
0x180008cef  jmp     short loc_180008C86
0x180008cf1  mov     rcx, [rsp+1C0h+var_170]; hKey
0x180008cf6  lea     rax, aD959f1b09e4211; "{d959f1b0-9e42-11ce-8b97-0080c7a01d7f}"
0x180008cfd  mov     [rsp+1C0h+samDesired], 27h ; '''; cbData
0x180008d05  mov     r9d, r15d; dwType
0x180008d08  xor     r8d, r8d; Reserved
0x180008d0b  mov     qword ptr [rsp+1C0h+dwOptions], rax; lpData
0x180008d10  mov     rdx, r14; lpValueName
0x180008d13  call    cs:__imp_RegSetValueExA
0x180008d19  mov     rcx, [rsp+1C0h+var_170]; hKey
0x180008d1e  test    eax, eax
0x180008d20  jz      short loc_180008D2A
0x180008d22  call    cs:__imp_RegCloseKey
0x180008d28  jmp     short loc_180008CEA
0x180008d2a  call    cs:__imp_RegCloseKey
0x180008d30  mov     rcx, [rsp+1C0h+hKey]; hKey
0x180008d35  call    cs:__imp_RegCloseKey
0x180008d3b  lea     rax, [rsp+1C0h+dwDisposition]
0x180008d40  mov     r9, r14; lpClass
0x180008d43  mov     [rsp+1C0h+lpdwDisposition], rax; lpdwDisposition
0x180008d48  lea     rdx, aClsidD959f1b09; "CLSID\\{d959f1b0-9e42-11ce-8b97-0080c7a"...
0x180008d4f  lea     rax, [rsp+1C0h+var_170]
0x180008d54  xor     r8d, r8d; Reserved
0x180008d57  mov     [rsp+1C0h+phkResult], rax; phkResult
0x180008d5c  mov     rcx, rdi; hKey
0x180008d5f  mov     [rsp+1C0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180008d64  mov     [rsp+1C0h+samDesired], ebx; samDesired
0x180008d68  mov     [rsp+1C0h+dwOptions], esi; dwOptions
0x180008d6c  call    cs:__imp_RegCreateKeyExA
0x180008d72  test    eax, eax
0x180008d74  jnz     loc_180008C8C
0x180008d7a  mov     rcx, [rsp+1C0h+var_170]; hKey
0x180008d7f  lea     rax, Data; "MSDTC Log Manager"
0x180008d86  mov     [rsp+1C0h+samDesired], 12h; cbData
0x180008d8e  mov     r9d, r15d; dwType
0x180008d91  xor     r8d, r8d; Reserved
0x180008d94  mov     qword ptr [rsp+1C0h+dwOptions], rax; lpData
0x180008d99  mov     rdx, r14; lpValueName
0x180008d9c  call    cs:__imp_RegSetValueExA
0x180008da2  mov     rcx, [rsp+1C0h+var_170]; hKey
0x180008da7  test    eax, eax
0x180008da9  jnz     loc_180008C86
0x180008daf  lea     rax, [rsp+1C0h+dwDisposition]
0x180008db4  mov     r9, r14; lpClass
0x180008db7  mov     [rsp+1C0h+lpdwDisposition], rax; lpdwDisposition
0x180008dbc  lea     rdx, aProgid; "ProgID"
0x180008dc3  lea     rax, [rsp+1C0h+hKey]
0x180008dc8  xor     r8d, r8d; Reserved
0x180008dcb  mov     [rsp+1C0h+phkResult], rax; phkResult
0x180008dd0  mov     [rsp+1C0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180008dd5  mov     [rsp+1C0h+samDesired], ebx; samDesired
0x180008dd9  mov     [rsp+1C0h+dwOptions], esi; dwOptions
0x180008ddd  call    cs:__imp_RegCreateKeyExA
0x180008de3  test    eax, eax
0x180008de5  jz      short loc_180008DF1
0x180008de7  mov     rcx, [rsp+1C0h+var_170]
0x180008dec  jmp     loc_180008C86
0x180008df1  mov     rcx, [rsp+1C0h+hKey]; hKey
0x180008df6  mov     edi, 0Eh
0x180008dfb  mov     [rsp+1C0h+samDesired], edi; cbData
0x180008dff  mov     r9d, r15d; dwType
0x180008e02  xor     r8d, r8d; Reserved
0x180008e05  mov     qword ptr [rsp+1C0h+dwOptions], r12; lpData
0x180008e0a  mov     rdx, r14; lpValueName
0x180008e0d  call    cs:__imp_RegSetValueExA
0x180008e13  mov     rcx, [rsp+1C0h+hKey]; hKey
0x180008e18  test    eax, eax
0x180008e1a  jz      short loc_180008E24
0x180008e1c  call    cs:__imp_RegCloseKey
0x180008e22  jmp     short loc_180008DE7
0x180008e24  call    cs:__imp_RegCloseKey
0x180008e2a  mov     rcx, [rsp+1C0h+var_170]; hKey
0x180008e2f  lea     rax, [rsp+1C0h+dwDisposition]
0x180008e34  mov     [rsp+1C0h+lpdwDisposition], rax; lpdwDisposition
0x180008e39  lea     rdx, aVersionindepen; "VersionIndependentProgID"
0x180008e40  lea     rax, [rsp+1C0h+hKey]
0x180008e45  mov     r9, r14; lpClass
0x180008e48  mov     [rsp+1C0h+phkResult], rax; phkResult
0x180008e4d  xor     r8d, r8d; Reserved
0x180008e50  mov     [rsp+1C0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180008e55  mov     [rsp+1C0h+samDesired], ebx; samDesired
0x180008e59  mov     [rsp+1C0h+dwOptions], esi; dwOptions
0x180008e5d  call    cs:__imp_RegCreateKeyExA
0x180008e63  test    eax, eax
0x180008e65  jnz     short loc_180008DE7
0x180008e67  mov     rcx, [rsp+1C0h+hKey]; hKey
0x180008e6c  mov     r9d, r15d; dwType
0x180008e6f  mov     [rsp+1C0h+samDesired], edi; cbData
0x180008e73  xor     r8d, r8d; Reserved
0x180008e76  mov     rdx, r14; lpValueName
0x180008e79  mov     qword ptr [rsp+1C0h+dwOptions], r12; lpData
0x180008e7e  call    cs:__imp_RegSetValueExA
0x180008e84  mov     rcx, [rsp+1C0h+hKey]; hKey
0x180008e89  test    eax, eax
0x180008e8b  jnz     short loc_180008E1C
0x180008e8d  call    cs:__imp_RegCloseKey
0x180008e93  mov     rcx, [rsp+1C0h+var_170]; hKey
0x180008e98  lea     rax, [rsp+1C0h+dwDisposition]
0x180008e9d  mov     [rsp+1C0h+lpdwDisposition], rax; lpdwDisposition
0x180008ea2  lea     rdx, aInprocserver32; "InprocServer32"
0x180008ea9  lea     rax, [rsp+1C0h+var_158]
0x180008eae  mov     r9, r14; lpClass
0x180008eb1  mov     [rsp+1C0h+phkResult], rax; phkResult
0x180008eb6  xor     r8d, r8d; Reserved
0x180008eb9  mov     [rsp+1C0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180008ebe  mov     [rsp+1C0h+samDesired], ebx; samDesired
0x180008ec2  mov     [rsp+1C0h+dwOptions], esi; dwOptions
0x180008ec6  call    cs:__imp_RegCreateKeyExA
0x180008ecc  test    eax, eax
0x180008ece  jnz     loc_180008DE7
0x180008ed4  lea     rcx, ModuleName; "MsDtcLog.dll"
0x180008edb  call    cs:__imp_GetModuleHandleA
0x180008ee1  test    rax, rax
0x180008ee4  jnz     short loc_180008EF0
0x180008ee6  mov     rcx, [rsp+1C0h+var_158]
0x180008eeb  jmp     loc_180008E1C
0x180008ef0  mov     edi, 105h
0x180008ef5  lea     rdx, [rsp+1C0h+Filename]; lpFilename
0x180008efa  mov     r8d, edi; nSize
0x180008efd  mov     rcx, rax; hModule
0x180008f00  call    cs:__imp_GetModuleFileNameA
0x180008f06  test    eax, eax
0x180008f08  jz      short loc_180008F6A
0x180008f0a  mov     ecx, edi
0x180008f0c  lea     rax, [rsp+1C0h+Filename]
0x180008f11  cmp     [rax], sil
0x180008f14  jz      short loc_180008F1E
0x180008f16  add     rax, r15
0x180008f19  sub     rcx, r15
0x180008f1c  jnz     short loc_180008F11
0x180008f1e  mov     rax, rcx
0x180008f21  neg     rax
0x180008f24  mov     rax, rcx
0x180008f27  sbb     ebx, ebx
0x180008f29  sub     rdi, rcx
0x180008f2c  not     ebx
0x180008f2e  and     ebx, 80070057h
0x180008f34  neg     rax
0x180008f37  sbb     rax, rax
0x180008f3a  and     rax, rdi
0x180008f3d  test    rcx, rcx
0x180008f40  jz      short loc_180008F6F
0x180008f42  mov     rcx, [rsp+1C0h+var_158]; hKey
0x180008f47  inc     eax
0x180008f49  mov     [rsp+1C0h+samDesired], eax; cbData
0x180008f4d  mov     r9d, r15d; dwType
0x180008f50  lea     rax, [rsp+1C0h+Filename]
0x180008f55  xor     r8d, r8d; Reserved
0x180008f58  mov     rdx, r14; lpValueName
0x180008f5b  mov     qword ptr [rsp+1C0h+dwOptions], rax; lpData
0x180008f60  call    cs:__imp_RegSetValueExA
0x180008f66  test    eax, eax
0x180008f68  jz      short loc_180008F8C
0x180008f6a  mov     ebx, 8000FFFFh
0x180008f6f  mov     rcx, [rsp+1C0h+var_158]; hKey
0x180008f74  call    cs:__imp_RegCloseKey
0x180008f7a  mov     rcx, [rsp+1C0h+var_170]; hKey
0x180008f7f  call    cs:__imp_RegCloseKey
0x180008f85  mov     eax, ebx
0x180008f87  jmp     loc_180008C91
0x180008f8c  mov     rcx, [rsp+1C0h+var_158]; hKey
0x180008f91  call    cs:__imp_RegCloseKey
0x180008f97  mov     rcx, [rsp+1C0h+var_170]; hKey
0x180008f9c  call    cs:__imp_RegCloseKey
0x180008fa2  xor     eax, eax
0x180008fa4  jmp     loc_180008C91
```
