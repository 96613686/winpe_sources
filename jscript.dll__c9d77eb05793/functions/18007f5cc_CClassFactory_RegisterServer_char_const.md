# CClassFactory::RegisterServer(char const *)

- ea: `0x18007f5cc`
- end: `0x18007fbc5`
- name: `?RegisterServer@CClassFactory@@QEAAJPEBD@Z`
- size: `1529`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180073380`

## callees

- `0x18007f310`
- `0x18007f510`
- `0x18007f5cc`
- `0x18007fd2c`
- `0x1800942d0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x18007f9c4`
- `ADVAPI32!RegOpenKeyExA` at `0x18007f9c4`
- `ADVAPI32!RegCloseKey` at `0x18007f701`
- `ADVAPI32!RegCloseKey` at `0x18007f790`
- `ADVAPI32!RegCloseKey` at `0x18007f79b`
- `ADVAPI32!RegCloseKey` at `0x18007f7ae`
- `ADVAPI32!RegCloseKey` at `0x18007f890`
- `ADVAPI32!RegCloseKey` at `0x18007f937`
- `ADVAPI32!RegCloseKey` at `0x18007f99d`
- `ADVAPI32!RegCloseKey` at `0x18007f9d3`
- `ADVAPI32!RegCloseKey` at `0x18007f9de`
- `ADVAPI32!RegCloseKey` at `0x18007fa1a`
- `ADVAPI32!RegCloseKey` at `0x18007fa25`
- `ADVAPI32!RegCloseKey` at `0x18007fa30`
- `ADVAPI32!RegCloseKey` at `0x18007fa3b`
- `ADVAPI32!RegCloseKey` at `0x18007fabc`
- `ADVAPI32!RegCloseKey` at `0x18007f701`
- `ADVAPI32!RegCloseKey` at `0x18007f790`
- `ADVAPI32!RegCloseKey` at `0x18007f79b`
- `ADVAPI32!RegCloseKey` at `0x18007f7ae`
- `ADVAPI32!RegCloseKey` at `0x18007f890`
- `ADVAPI32!RegCloseKey` at `0x18007f937`
- `ADVAPI32!RegCloseKey` at `0x18007f99d`
- `ADVAPI32!RegCloseKey` at `0x18007f9d3`
- `ADVAPI32!RegCloseKey` at `0x18007f9de`
- `ADVAPI32!RegCloseKey` at `0x18007fa1a`
- `ADVAPI32!RegCloseKey` at `0x18007fa25`
- `ADVAPI32!RegCloseKey` at `0x18007fa30`
- `ADVAPI32!RegCloseKey` at `0x18007fa3b`
- `ADVAPI32!RegCloseKey` at `0x18007fabc`
- `ADVAPI32!RegSetValueExA` at `0x18007f724`
- `ADVAPI32!RegSetValueExA` at `0x18007f785`
- `ADVAPI32!RegSetValueExA` at `0x18007f8bf`
- `ADVAPI32!RegSetValueExA` at `0x18007f92c`
- `ADVAPI32!RegSetValueExA` at `0x18007f992`
- `ADVAPI32!RegSetValueExA` at `0x18007fa0f`
- `ADVAPI32!RegSetValueExA` at `0x18007faa9`
- `ADVAPI32!RegSetValueExA` at `0x18007f724`
- `ADVAPI32!RegSetValueExA` at `0x18007f785`
- `ADVAPI32!RegSetValueExA` at `0x18007f8bf`
- `ADVAPI32!RegSetValueExA` at `0x18007f92c`
- `ADVAPI32!RegSetValueExA` at `0x18007f992`
- `ADVAPI32!RegSetValueExA` at `0x18007fa0f`
- `ADVAPI32!RegSetValueExA` at `0x18007faa9`
- `ADVAPI32!RegCreateKeyExA` at `0x18007f6ad`
- `ADVAPI32!RegCreateKeyExA` at `0x18007f6ee`
- `ADVAPI32!RegCreateKeyExA` at `0x18007f75d`
- `ADVAPI32!RegCreateKeyExA` at `0x18007f806`
- `ADVAPI32!RegCreateKeyExA` at `0x18007f843`
- `ADVAPI32!RegCreateKeyExA` at `0x18007f881`
- `ADVAPI32!RegCreateKeyExA` at `0x18007f8f9`
- `ADVAPI32!RegCreateKeyExA` at `0x18007f96d`
- `ADVAPI32!RegCreateKeyExA` at `0x18007fa75`
- `ADVAPI32!RegCreateKeyExA` at `0x18007f6ad`
- `ADVAPI32!RegCreateKeyExA` at `0x18007f6ee`
- `ADVAPI32!RegCreateKeyExA` at `0x18007f75d`
- `ADVAPI32!RegCreateKeyExA` at `0x18007f806`
- `ADVAPI32!RegCreateKeyExA` at `0x18007f843`
- `ADVAPI32!RegCreateKeyExA` at `0x18007f881`
- `ADVAPI32!RegCreateKeyExA` at `0x18007f8f9`
- `ADVAPI32!RegCreateKeyExA` at `0x18007f96d`
- `ADVAPI32!RegCreateKeyExA` at `0x18007fa75`
- `KERNEL32!GetModuleHandleA` at `0x18007f63b`
- `KERNEL32!GetModuleHandleA` at `0x18007f63b`
- `KERNEL32!GetModuleFileNameA` at `0x18007f64e`
- `KERNEL32!GetModuleFileNameA` at `0x18007f64e`

## string_xrefs

- `0x18007f739`: `CLSID`
- `0x18007f7ed`: `CLSID`
- `0x18007f9fd`: `ThreadingModel`

## pseudocode

```c
__int64 __fastcall CClassFactory::RegisterServer(CClassFactory *this, const char *a2)
{
  __int64 v2; // rax
  __int64 v3; // rdi
  __int64 v4; // rsi
  __int64 v6; // r14
  HMODULE ModuleHandleA; // rax
  DWORD ModuleFileNameA; // r12d
  int i; // r15d
  HKEY v10; // rcx
  const BYTE *v12; // rcx
  __int64 v13; // rax
  const CHAR *v14; // rdx
  const BYTE *v15; // rcx
  LSTATUS v16; // eax
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v19[2]; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v20; // [rsp+70h] [rbp-90h] BYREF
  HKEY v21; // [rsp+78h] [rbp-88h] BYREF
  CHAR Filename[512]; // [rsp+80h] [rbp-80h] BYREF

  v2 = *((_QWORD *)this + 4);
  v3 = -1;
  hKey = 0;
  v4 = -1;
  phkResult = 0;
  v21 = 0;
  v20 = 0;
  do
    ++v4;
  while ( *(_BYTE *)(v2 + v4) );
  v6 = -1;
  do
    ++v6;
  while ( *(_BYTE *)(*((_QWORD *)this + 3) + v6) );
  ModuleHandleA = GetModuleHandleA(*((LPCSTR *)this + 6));
  ModuleFileNameA = GetModuleFileNameA(ModuleHandleA, Filename, 0x200u);
  if ( !ModuleFileNameA )
    return 2147500037LL;
  CClassFactory::UnregisterServer(this);
  for ( i = 0; i < *((_DWORD *)this + 16); ++i )
  {
    if ( RegCreateKeyExA(
           HKEY_CLASSES_ROOT,
           *(LPCSTR *)(*((_QWORD *)this + 7) + 8LL * i),
           0,
           0,
           0,
           0x2000000u,
           0,
           &hKey,
           0) )
    {
      return 2147500037LL;
    }
    if ( RegCreateKeyExA(hKey, "OLEScript", 0, 0, 0, 0x2000000u, 0, &phkResult, 0) )
      goto LABEL_12;
    RegCloseKey(phkResult);
    RegSetValueExA(hKey, 0, 0, 1u, *((const BYTE **)this + 4), v4);
    if ( RegCreateKeyExA(hKey, "CLSID", 0, 0, 0, 2u, 0, &phkResult, 0) )
      goto LABEL_12;
    RegSetValueExA(phkResult, 0, 0, 1u, *((const BYTE **)this + 3), v6);
    RegCloseKey(phkResult);
    RegCloseKey(hKey);
  }
  if ( RegCreateKeyExA(HKEY_CLASSES_ROOT, "CLSID", 0, 0, 0, 0x2000000u, 0, &hKey, 0) )
    return 2147500037LL;
  if ( RegCreateKeyExA(hKey, *((LPCSTR *)this + 3), 0, 0, 0, 0x2000000u, 0, &phkResult, 0) )
  {
LABEL_12:
    v10 = hKey;
LABEL_13:
    RegCloseKey(v10);
    return 2147500037LL;
  }
  if ( RegCreateKeyExA(phkResult, "OLEScript", 0, 0, 0, 0x2000000u, 0, &v21, 0) )
  {
    RegCloseKey(hKey);
    v10 = phkResult;
    goto LABEL_13;
  }
  RegSetValueExA(phkResult, 0, 0, 1u, *((const BYTE **)this + 4), v4);
  if ( !RegCreateKeyExA(phkResult, "ProgID", 0, 0, 0, 2u, 0, &v20, 0) )
  {
    v12 = (const BYTE *)**((_QWORD **)this + 7);
    v13 = -1;
    do
      ++v13;
    while ( v12[v13] );
    RegSetValueExA(v20, 0, 0, 1u, v12, v13);
    RegCloseKey(v20);
  }
  if ( !RegCreateKeyExA(phkResult, "InprocServer32", 0, 0, 0, 2u, 0, &v20, 0) )
  {
    RegSetValueExA(v20, 0, 0, 1u, (const BYTE *)Filename, ModuleFileNameA);
    RegCloseKey(v20);
  }
  v19[0] = 0;
  if ( RegOpenKeyExA(phkResult, "InprocServer32", 0, 2u, v19) )
  {
    RegCloseKey(v21);
    RegCloseKey(phkResult);
    goto LABEL_12;
  }
  RegSetValueExA(v19[0], "ThreadingModel", 0, 1u, "Both", 4u);
  RegCloseKey(v19[0]);
  RegCloseKey(v21);
  RegCloseKey(phkResult);
  RegCloseKey(hKey);
  v14 = (const CHAR *)*((_QWORD *)this + 5);
  if ( !v14 )
    goto LABEL_33;
  if ( RegCreateKeyExA(HKEY_CLASSES_ROOT, v14, 0, 0, 0, 2u, 0, &hKey, 0) )
    return 2147500037LL;
  v15 = (const BYTE *)**((_QWORD **)this + 7);
  do
    ++v3;
  while ( v15[v3] );
  v16 = RegSetValueExA(hKey, 0, 0, 1u, v15, v3);
  v10 = hKey;
  if ( v16 )
    goto LABEL_13;
  RegCloseKey(hKey);
LABEL_33:
  if ( (*((_BYTE *)this + 84) & 1) != 0 )
  {
    *(GUID *)v19 = CATID_ActiveScript;
    CreateComponentCategory(v19, L"Active Scripting Engine");
    *(GUID *)v19 = CATID_ActiveScript;
    RegisterCLSIDInCategory((char *)this + 68, v19);
  }
  if ( (*((_BYTE *)this + 84) & 2) != 0 )
  {
    *(GUID *)v19 = CATID_ActiveScriptParse;
    CreateComponentCategory(v19, L"Active Scripting Engine with Parsing");
    *(GUID *)v19 = CATID_ActiveScriptParse;
    RegisterCLSIDInCategory((char *)this + 68, v19);
  }
  if ( (*((_BYTE *)this + 84) & 4) != 0 )
  {
    *(GUID *)v19 = CATID_ActiveScriptAuthor;
    CreateComponentCategory(v19, L"Active Scripting Engine with Authoring");
    *(GUID *)v19 = CATID_ActiveScriptAuthor;
    RegisterCLSIDInCategory((char *)this + 68, v19);
  }
  if ( (*((_BYTE *)this + 84) & 8) != 0 )
  {
    *(GUID *)v19 = CATID_ActiveScriptEncode;
    CreateComponentCategory(v19, L"Active Scripting Engine with Encoding");
    *(GUID *)v19 = CATID_ActiveScriptEncode;
    RegisterCLSIDInCategory((char *)this + 68, v19);
  }
  return 0;
}

```

## disassembly

```asm
0x18007f5cc  push    rbp
0x18007f5ce  push    rbx
0x18007f5cf  push    rsi
0x18007f5d0  push    rdi
0x18007f5d1  push    r12
0x18007f5d3  push    r13
0x18007f5d5  push    r14
0x18007f5d7  push    r15
0x18007f5d9  lea     rbp, [rsp-198h]
0x18007f5e1  sub     rsp, 298h
0x18007f5e8  mov     rax, cs:__security_cookie
0x18007f5ef  xor     rax, rsp
0x18007f5f2  mov     [rbp+1D0h+var_50], rax
0x18007f5f9  mov     rax, [rcx+20h]
0x18007f5fd  xor     r13d, r13d
0x18007f600  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18007f604  mov     [rsp+2D0h+hKey], r13
0x18007f609  mov     rsi, rdi
0x18007f60c  mov     [rsp+2D0h+var_278], r13
0x18007f611  mov     rbx, rcx
0x18007f614  mov     [rsp+2D0h+var_258], r13
0x18007f619  mov     [rsp+2D0h+var_260], r13
0x18007f61e  inc     rsi
0x18007f621  cmp     [rax+rsi], r13b
0x18007f625  jnz     short loc_18007F61E
0x18007f627  mov     rax, [rcx+18h]
0x18007f62b  mov     r14, rdi
0x18007f62e  inc     r14
0x18007f631  cmp     [rax+r14], r13b
0x18007f635  jnz     short loc_18007F62E
0x18007f637  mov     rcx, [rcx+30h]; lpModuleName
0x18007f63b  call    cs:__imp_GetModuleHandleA
0x18007f641  mov     r8d, 200h; nSize
0x18007f647  lea     rdx, [rbp+1D0h+Filename]; lpFilename
0x18007f64b  mov     rcx, rax; hModule
0x18007f64e  call    cs:__imp_GetModuleFileNameA
0x18007f654  mov     r12d, eax
0x18007f657  test    eax, eax
0x18007f659  jz      loc_18007F7B4
0x18007f65f  mov     rcx, rbx; this
0x18007f662  call    ?UnregisterServer@CClassFactory@@QEAAJXZ; CClassFactory::UnregisterServer(void)
0x18007f667  mov     r15d, r13d
0x18007f66a  xor     r9d, r9d; lpClass
0x18007f66d  mov     [rsp+2D0h+lpdwDisposition], r13; lpdwDisposition
0x18007f672  xor     r8d, r8d; Reserved
0x18007f675  cmp     r15d, [rbx+40h]
0x18007f679  jge     loc_18007F7DC
0x18007f67f  mov     rdx, [rbx+38h]
0x18007f683  lea     rcx, [rsp+2D0h+hKey]
0x18007f688  mov     [rsp+2D0h+phkResult], rcx; phkResult
0x18007f68d  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18007f694  movsxd  rax, r15d
0x18007f697  mov     [rsp+2D0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18007f69c  mov     [rsp+2D0h+samDesired], 2000000h; samDesired
0x18007f6a4  mov     [rsp+2D0h+dwOptions], r13d; dwOptions
0x18007f6a9  mov     rdx, [rdx+rax*8]; lpSubKey
0x18007f6ad  call    cs:__imp_RegCreateKeyExA
0x18007f6b3  test    eax, eax
0x18007f6b5  jnz     loc_18007F7B4
0x18007f6bb  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18007f6c0  lea     rax, [rsp+2D0h+var_278]
0x18007f6c5  mov     [rsp+2D0h+lpdwDisposition], r13; lpdwDisposition
0x18007f6ca  lea     rdx, aOlescript; "OLEScript"
0x18007f6d1  mov     [rsp+2D0h+phkResult], rax; phkResult
0x18007f6d6  xor     r9d, r9d; lpClass
0x18007f6d9  mov     [rsp+2D0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18007f6de  xor     r8d, r8d; Reserved
0x18007f6e1  mov     [rsp+2D0h+samDesired], 2000000h; samDesired
0x18007f6e9  mov     [rsp+2D0h+dwOptions], r13d; dwOptions
0x18007f6ee  call    cs:__imp_RegCreateKeyExA
0x18007f6f4  test    eax, eax
0x18007f6f6  jnz     loc_18007F7A9
0x18007f6fc  mov     rcx, [rsp+2D0h+var_278]; hKey
0x18007f701  call    cs:__imp_RegCloseKey
0x18007f707  mov     rax, [rbx+20h]
0x18007f70b  mov     r9d, 1; dwType
0x18007f711  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18007f716  xor     r8d, r8d; Reserved
0x18007f719  mov     [rsp+2D0h+samDesired], esi; cbData
0x18007f71d  xor     edx, edx; lpValueName
0x18007f71f  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x18007f724  call    cs:__imp_RegSetValueExA
0x18007f72a  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18007f72f  lea     rax, [rsp+2D0h+var_278]
0x18007f734  mov     [rsp+2D0h+lpdwDisposition], r13; lpdwDisposition
0x18007f739  lea     rdx, aClsid; "CLSID"
0x18007f740  mov     [rsp+2D0h+phkResult], rax; phkResult
0x18007f745  xor     r9d, r9d; lpClass
0x18007f748  mov     [rsp+2D0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18007f74d  xor     r8d, r8d; Reserved
0x18007f750  mov     [rsp+2D0h+samDesired], 2; samDesired
0x18007f758  mov     [rsp+2D0h+dwOptions], r13d; dwOptions
0x18007f75d  call    cs:__imp_RegCreateKeyExA
0x18007f763  test    eax, eax
0x18007f765  jnz     short loc_18007F7A9
0x18007f767  mov     rax, [rbx+18h]
0x18007f76b  mov     r9d, 1; dwType
0x18007f771  mov     rcx, [rsp+2D0h+var_278]; hKey
0x18007f776  xor     r8d, r8d; Reserved
0x18007f779  mov     [rsp+2D0h+samDesired], r14d; cbData
0x18007f77e  xor     edx, edx; lpValueName
0x18007f780  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x18007f785  call    cs:__imp_RegSetValueExA
0x18007f78b  mov     rcx, [rsp+2D0h+var_278]; hKey
0x18007f790  call    cs:__imp_RegCloseKey
0x18007f796  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18007f79b  call    cs:__imp_RegCloseKey
0x18007f7a1  inc     r15d
0x18007f7a4  jmp     loc_18007F66A
0x18007f7a9  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18007f7ae  call    cs:__imp_RegCloseKey
0x18007f7b4  mov     eax, 80004005h
0x18007f7b9  mov     rcx, [rbp+1D0h+var_50]
0x18007f7c0  xor     rcx, rsp; StackCookie
0x18007f7c3  call    __security_check_cookie
0x18007f7c8  add     rsp, 298h
0x18007f7cf  pop     r15
0x18007f7d1  pop     r14
0x18007f7d3  pop     r13
0x18007f7d5  pop     r12
0x18007f7d7  pop     rdi
0x18007f7d8  pop     rsi
0x18007f7d9  pop     rbx
0x18007f7da  pop     rbp
0x18007f7db  retn
0x18007f7dc  lea     rax, [rsp+2D0h+hKey]
0x18007f7e1  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18007f7e8  mov     [rsp+2D0h+phkResult], rax; phkResult
0x18007f7ed  lea     rdx, aClsid; "CLSID"
0x18007f7f4  mov     [rsp+2D0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18007f7f9  mov     [rsp+2D0h+samDesired], 2000000h; samDesired
0x18007f801  mov     [rsp+2D0h+dwOptions], r13d; dwOptions
0x18007f806  call    cs:__imp_RegCreateKeyExA
0x18007f80c  test    eax, eax
0x18007f80e  jnz     short loc_18007F7B4
0x18007f810  mov     rdx, [rbx+18h]; lpSubKey
0x18007f814  lea     rax, [rsp+2D0h+var_278]
0x18007f819  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18007f81e  mov     r14d, 2000000h
0x18007f824  mov     [rsp+2D0h+lpdwDisposition], r13; lpdwDisposition
0x18007f829  xor     r9d, r9d; lpClass
0x18007f82c  mov     [rsp+2D0h+phkResult], rax; phkResult
0x18007f831  xor     r8d, r8d; Reserved
0x18007f834  mov     [rsp+2D0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18007f839  mov     [rsp+2D0h+samDesired], r14d; samDesired
0x18007f83e  mov     [rsp+2D0h+dwOptions], r13d; dwOptions
0x18007f843  call    cs:__imp_RegCreateKeyExA
0x18007f849  test    eax, eax
0x18007f84b  jnz     loc_18007F7A9
0x18007f851  mov     rcx, [rsp+2D0h+var_278]; hKey
0x18007f856  lea     rax, [rsp+2D0h+var_258]
0x18007f85b  mov     [rsp+2D0h+lpdwDisposition], r13; lpdwDisposition
0x18007f860  lea     rdx, aOlescript; "OLEScript"
0x18007f867  mov     [rsp+2D0h+phkResult], rax; phkResult
0x18007f86c  xor     r9d, r9d; lpClass
0x18007f86f  mov     [rsp+2D0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18007f874  xor     r8d, r8d; Reserved
0x18007f877  mov     [rsp+2D0h+samDesired], r14d; samDesired
0x18007f87c  mov     [rsp+2D0h+dwOptions], r13d; dwOptions
0x18007f881  call    cs:__imp_RegCreateKeyExA
0x18007f887  test    eax, eax
0x18007f889  jz      short loc_18007F8A0
0x18007f88b  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18007f890  call    cs:__imp_RegCloseKey
0x18007f896  mov     rcx, [rsp+2D0h+var_278]
0x18007f89b  jmp     loc_18007F7AE
0x18007f8a0  mov     rax, [rbx+20h]
0x18007f8a4  xor     r8d, r8d; Reserved
0x18007f8a7  mov     rcx, [rsp+2D0h+var_278]; hKey
0x18007f8ac  xor     edx, edx; lpValueName
0x18007f8ae  mov     [rsp+2D0h+samDesired], esi; cbData
0x18007f8b2  mov     esi, 1
0x18007f8b7  mov     r9d, esi; dwType
0x18007f8ba  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x18007f8bf  call    cs:__imp_RegSetValueExA
0x18007f8c5  mov     rcx, [rsp+2D0h+var_278]; hKey
0x18007f8ca  lea     rax, [rsp+2D0h+var_260]
0x18007f8cf  mov     [rsp+2D0h+lpdwDisposition], r13; lpdwDisposition
0x18007f8d4  lea     r14d, [rsi+1]
0x18007f8d8  mov     [rsp+2D0h+phkResult], rax; phkResult
0x18007f8dd  lea     rdx, aProgid; "ProgID"
0x18007f8e4  mov     [rsp+2D0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18007f8e9  xor     r9d, r9d; lpClass
0x18007f8ec  mov     [rsp+2D0h+samDesired], r14d; samDesired
0x18007f8f1  xor     r8d, r8d; Reserved
0x18007f8f4  mov     [rsp+2D0h+dwOptions], r13d; dwOptions
0x18007f8f9  call    cs:__imp_RegCreateKeyExA
0x18007f8ff  test    eax, eax
0x18007f901  jnz     short loc_18007F93D
0x18007f903  mov     rax, [rbx+38h]
0x18007f907  mov     rcx, [rax]
0x18007f90a  mov     rax, rdi
0x18007f90d  inc     rax
0x18007f910  cmp     [rcx+rax], r13b
0x18007f914  jnz     short loc_18007F90D
0x18007f916  mov     [rsp+2D0h+samDesired], eax; cbData
0x18007f91a  mov     r9d, esi; dwType
0x18007f91d  mov     qword ptr [rsp+2D0h+dwOptions], rcx; lpData
0x18007f922  xor     r8d, r8d; Reserved
0x18007f925  mov     rcx, [rsp+2D0h+var_260]; hKey
0x18007f92a  xor     edx, edx; lpValueName
0x18007f92c  call    cs:__imp_RegSetValueExA
0x18007f932  mov     rcx, [rsp+2D0h+var_260]; hKey
0x18007f937  call    cs:__imp_RegCloseKey
0x18007f93d  mov     rcx, [rsp+2D0h+var_278]; hKey
0x18007f942  lea     rax, [rsp+2D0h+var_260]
0x18007f947  mov     [rsp+2D0h+lpdwDisposition], r13; lpdwDisposition
0x18007f94c  lea     rdx, aInprocserver32; "InprocServer32"
0x18007f953  mov     [rsp+2D0h+phkResult], rax; phkResult
0x18007f958  xor     r9d, r9d; lpClass
0x18007f95b  mov     [rsp+2D0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18007f960  xor     r8d, r8d; Reserved
0x18007f963  mov     [rsp+2D0h+samDesired], r14d; samDesired
0x18007f968  mov     [rsp+2D0h+dwOptions], r13d; dwOptions
0x18007f96d  call    cs:__imp_RegCreateKeyExA
0x18007f973  test    eax, eax
0x18007f975  jnz     short loc_18007F9A3
0x18007f977  mov     rcx, [rsp+2D0h+var_260]; hKey
0x18007f97c  lea     rax, [rbp+1D0h+Filename]
0x18007f980  mov     [rsp+2D0h+samDesired], r12d; cbData
0x18007f985  mov     r9d, esi; dwType
0x18007f988  xor     r8d, r8d; Reserved
0x18007f98b  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x18007f990  xor     edx, edx; lpValueName
0x18007f992  call    cs:__imp_RegSetValueExA
0x18007f998  mov     rcx, [rsp+2D0h+var_260]; hKey
0x18007f99d  call    cs:__imp_RegCloseKey
0x18007f9a3  mov     rcx, [rsp+2D0h+var_278]; hKey
0x18007f9a8  lea     rax, [rsp+2D0h+var_270]
0x18007f9ad  mov     r9d, r14d; samDesired
0x18007f9b0  mov     qword ptr [rsp+2D0h+dwOptions], rax; phkResult
0x18007f9b5  xor     r8d, r8d; ulOptions
0x18007f9b8  mov     [rsp+2D0h+var_270], r13
0x18007f9bd  lea     rdx, aInprocserver32; "InprocServer32"
0x18007f9c4  call    cs:__imp_RegOpenKeyExA
0x18007f9ca  test    eax, eax
0x18007f9cc  jz      short loc_18007F9E9
0x18007f9ce  mov     rcx, [rsp+2D0h+var_258]; hKey
0x18007f9d3  call    cs:__imp_RegCloseKey
0x18007f9d9  mov     rcx, [rsp+2D0h+var_278]; hKey
0x18007f9de  call    cs:__imp_RegCloseKey
0x18007f9e4  jmp     loc_18007F7A9
0x18007f9e9  mov     rcx, [rsp+2D0h+var_270]; hKey
0x18007f9ee  lea     rax, Data; "Both"
0x18007f9f5  mov     [rsp+2D0h+samDesired], 4; cbData
0x18007f9fd  lea     rdx, aThreadingmodel; "ThreadingModel"
0x18007fa04  mov     r9d, esi; dwType
0x18007fa07  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x18007fa0c  xor     r8d, r8d; Reserved
0x18007fa0f  call    cs:__imp_RegSetValueExA
0x18007fa15  mov     rcx, [rsp+2D0h+var_270]; hKey
0x18007fa1a  call    cs:__imp_RegCloseKey
0x18007fa20  mov     rcx, [rsp+2D0h+var_258]; hKey
0x18007fa25  call    cs:__imp_RegCloseKey
0x18007fa2b  mov     rcx, [rsp+2D0h+var_278]; hKey
0x18007fa30  call    cs:__imp_RegCloseKey
0x18007fa36  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18007fa3b  call    cs:__imp_RegCloseKey
0x18007fa41  mov     rdx, [rbx+28h]; lpSubKey
0x18007fa45  test    rdx, rdx
0x18007fa48  jz      short loc_18007FAC2
0x18007fa4a  mov     [rsp+2D0h+lpdwDisposition], r13; lpdwDisposition
0x18007fa4f  lea     rax, [rsp+2D0h+hKey]
0x18007fa54  mov     [rsp+2D0h+phkResult], rax; phkResult
0x18007fa59  xor     r9d, r9d; lpClass
0x18007fa5c  mov     [rsp+2D0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18007fa61  xor     r8d, r8d; Reserved
0x18007fa64  mov     [rsp+2D0h+samDesired], r14d; samDesired
0x18007fa69  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18007fa70  mov     [rsp+2D0h+dwOptions], r13d; dwOptions
0x18007fa75  call    cs:__imp_RegCreateKeyExA
0x18007fa7b  test    eax, eax
0x18007fa7d  jnz     loc_18007F7B4
0x18007fa83  mov     rax, [rbx+38h]
0x18007fa87  mov     rcx, [rax]
0x18007fa8a  inc     rdi
0x18007fa8d  cmp     [rcx+rdi], r13b
0x18007fa91  jnz     short loc_18007FA8A
0x18007fa93  mov     [rsp+2D0h+samDesired], edi; cbData
0x18007fa97  mov     r9d, esi; dwType
0x18007fa9a  mov     qword ptr [rsp+2D0h+dwOptions], rcx; lpData
0x18007fa9f  xor     r8d, r8d; Reserved
0x18007faa2  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18007faa7  xor     edx, edx; lpValueName
0x18007faa9  call    cs:__imp_RegSetValueExA
0x18007faaf  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18007fab4  test    eax, eax
0x18007fab6  jnz     loc_18007F7AE
0x18007fabc  call    cs:__imp_RegCloseKey
0x18007fac2  lea     rdi, [rbx+44h]
0x18007fac6  test    [rbx+54h], sil
0x18007faca  jz      short loc_18007FB04
0x18007facc  movups  xmm0, xmmword ptr cs:CATID_ActiveScript.Data1
0x18007fad3  lea     rdx, aActiveScriptin_1; "Active Scripting Engine"
0x18007fada  lea     rcx, [rsp+2D0h+var_270]
0x18007fadf  movdqu  xmmword ptr [rsp+2D0h+var_270], xmm0
0x18007fae5  call    CreateComponentCategory
0x18007faea  movups  xmm0, xmmword ptr cs:CATID_ActiveScript.Data1
0x18007faf1  lea     rdx, [rsp+2D0h+var_270]
0x18007faf6  mov     rcx, rdi
  ... truncated ...
```
