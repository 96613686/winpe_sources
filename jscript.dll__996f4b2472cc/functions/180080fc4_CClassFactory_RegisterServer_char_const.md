# CClassFactory::RegisterServer(char const *)

- ea: `0x180080fc4`
- end: `0x180081688`
- name: `?RegisterServer@CClassFactory@@QEAAJPEBD@Z`
- size: `1732`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180074810`

## callees

- `0x180080cd8`
- `0x180080f00`
- `0x180080fc4`
- `0x1800817f8`
- `0x1800966e0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x180081441`
- `ADVAPI32!RegOpenKeyExA` at `0x180081441`
- `ADVAPI32!RegCloseKey` at `0x180081111`
- `ADVAPI32!RegCloseKey` at `0x1800811b8`
- `ADVAPI32!RegCloseKey` at `0x1800811c9`
- `ADVAPI32!RegCloseKey` at `0x1800811e2`
- `ADVAPI32!RegCloseKey` at `0x1800812dd`
- `ADVAPI32!RegCloseKey` at `0x18008139c`
- `ADVAPI32!RegCloseKey` at `0x180081414`
- `ADVAPI32!RegCloseKey` at `0x180081456`
- `ADVAPI32!RegCloseKey` at `0x180081467`
- `ADVAPI32!RegCloseKey` at `0x1800814af`
- `ADVAPI32!RegCloseKey` at `0x1800814c0`
- `ADVAPI32!RegCloseKey` at `0x1800814d1`
- `ADVAPI32!RegCloseKey` at `0x1800814e2`
- `ADVAPI32!RegCloseKey` at `0x180081579`
- `ADVAPI32!RegCloseKey` at `0x180081111`
- `ADVAPI32!RegCloseKey` at `0x1800811b8`
- `ADVAPI32!RegCloseKey` at `0x1800811c9`
- `ADVAPI32!RegCloseKey` at `0x1800811e2`
- `ADVAPI32!RegCloseKey` at `0x1800812dd`
- `ADVAPI32!RegCloseKey` at `0x18008139c`
- `ADVAPI32!RegCloseKey` at `0x180081414`
- `ADVAPI32!RegCloseKey` at `0x180081456`
- `ADVAPI32!RegCloseKey` at `0x180081467`
- `ADVAPI32!RegCloseKey` at `0x1800814af`
- `ADVAPI32!RegCloseKey` at `0x1800814c0`
- `ADVAPI32!RegCloseKey` at `0x1800814d1`
- `ADVAPI32!RegCloseKey` at `0x1800814e2`
- `ADVAPI32!RegCloseKey` at `0x180081579`
- `ADVAPI32!RegSetValueExA` at `0x18008113a`
- `ADVAPI32!RegSetValueExA` at `0x1800811a7`
- `ADVAPI32!RegSetValueExA` at `0x180081312`
- `ADVAPI32!RegSetValueExA` at `0x18008138b`
- `ADVAPI32!RegSetValueExA` at `0x180081403`
- `ADVAPI32!RegSetValueExA` at `0x18008149e`
- `ADVAPI32!RegSetValueExA` at `0x180081560`
- `ADVAPI32!RegSetValueExA` at `0x18008113a`
- `ADVAPI32!RegSetValueExA` at `0x1800811a7`
- `ADVAPI32!RegSetValueExA` at `0x180081312`
- `ADVAPI32!RegSetValueExA` at `0x18008138b`
- `ADVAPI32!RegSetValueExA` at `0x180081403`
- `ADVAPI32!RegSetValueExA` at `0x18008149e`
- `ADVAPI32!RegSetValueExA` at `0x180081560`
- `ADVAPI32!RegCreateKeyExA` at `0x1800810b1`
- `ADVAPI32!RegCreateKeyExA` at `0x1800810f8`
- `ADVAPI32!RegCreateKeyExA` at `0x180081179`
- `ADVAPI32!RegCreateKeyExA` at `0x180081241`
- `ADVAPI32!RegCreateKeyExA` at `0x180081284`
- `ADVAPI32!RegCreateKeyExA` at `0x1800812c8`
- `ADVAPI32!RegCreateKeyExA` at `0x180081352`
- `ADVAPI32!RegCreateKeyExA` at `0x1800813d8`
- `ADVAPI32!RegCreateKeyExA` at `0x180081526`
- `ADVAPI32!RegCreateKeyExA` at `0x1800810b1`
- `ADVAPI32!RegCreateKeyExA` at `0x1800810f8`
- `ADVAPI32!RegCreateKeyExA` at `0x180081179`
- `ADVAPI32!RegCreateKeyExA` at `0x180081241`
- `ADVAPI32!RegCreateKeyExA` at `0x180081284`
- `ADVAPI32!RegCreateKeyExA` at `0x1800812c8`
- `ADVAPI32!RegCreateKeyExA` at `0x180081352`
- `ADVAPI32!RegCreateKeyExA` at `0x1800813d8`
- `ADVAPI32!RegCreateKeyExA` at `0x180081526`
- `KERNEL32!GetModuleHandleA` at `0x180081033`
- `KERNEL32!GetModuleHandleA` at `0x180081033`
- `KERNEL32!GetModuleFileNameA` at `0x18008104c`
- `KERNEL32!GetModuleFileNameA` at `0x18008104c`

## string_xrefs

- `0x180081155`: `CLSID`
- `0x180081228`: `CLSID`
- `0x18008148c`: `ThreadingModel`

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
0x180080fc4  push    rbp
0x180080fc6  push    rbx
0x180080fc7  push    rsi
0x180080fc8  push    rdi
0x180080fc9  push    r12
0x180080fcb  push    r13
0x180080fcd  push    r14
0x180080fcf  push    r15
0x180080fd1  lea     rbp, [rsp-198h]
0x180080fd9  sub     rsp, 298h
0x180080fe0  mov     rax, cs:__security_cookie
0x180080fe7  xor     rax, rsp
0x180080fea  mov     [rbp+1D0h+var_50], rax
0x180080ff1  mov     rax, [rcx+20h]
0x180080ff5  xor     r13d, r13d
0x180080ff8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180080ffc  mov     [rsp+2D0h+hKey], r13
0x180081001  mov     rsi, rdi
0x180081004  mov     [rsp+2D0h+var_278], r13
0x180081009  mov     rbx, rcx
0x18008100c  mov     [rsp+2D0h+var_258], r13
0x180081011  mov     [rsp+2D0h+var_260], r13
0x180081016  inc     rsi
0x180081019  cmp     [rax+rsi], r13b
0x18008101d  jnz     short loc_180081016
0x18008101f  mov     rax, [rcx+18h]
0x180081023  mov     r14, rdi
0x180081026  inc     r14
0x180081029  cmp     [rax+r14], r13b
0x18008102d  jnz     short loc_180081026
0x18008102f  mov     rcx, [rcx+30h]; lpModuleName
0x180081033  call    cs:__imp_GetModuleHandleA
0x18008103a  nop     dword ptr [rax+rax+00h]
0x18008103f  mov     r8d, 200h; nSize
0x180081045  lea     rdx, [rbp+1D0h+Filename]; lpFilename
0x180081049  mov     rcx, rax; hModule
0x18008104c  call    cs:__imp_GetModuleFileNameA
0x180081053  nop     dword ptr [rax+rax+00h]
0x180081058  mov     r12d, eax
0x18008105b  test    eax, eax
0x18008105d  jz      loc_1800811EE
0x180081063  mov     rcx, rbx; this
0x180081066  call    ?UnregisterServer@CClassFactory@@QEAAJXZ; CClassFactory::UnregisterServer(void)
0x18008106b  mov     r15d, r13d
0x18008106e  xor     r9d, r9d; lpClass
0x180081071  mov     [rsp+2D0h+lpdwDisposition], r13; lpdwDisposition
0x180081076  xor     r8d, r8d; Reserved
0x180081079  cmp     r15d, [rbx+40h]
0x18008107d  jge     loc_180081217
0x180081083  mov     rdx, [rbx+38h]
0x180081087  lea     rcx, [rsp+2D0h+hKey]
0x18008108c  mov     [rsp+2D0h+phkResult], rcx; phkResult
0x180081091  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180081098  movsxd  rax, r15d
0x18008109b  mov     [rsp+2D0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1800810a0  mov     [rsp+2D0h+samDesired], 2000000h; samDesired
0x1800810a8  mov     [rsp+2D0h+dwOptions], r13d; dwOptions
0x1800810ad  mov     rdx, [rdx+rax*8]; lpSubKey
0x1800810b1  call    cs:__imp_RegCreateKeyExA
0x1800810b8  nop     dword ptr [rax+rax+00h]
0x1800810bd  test    eax, eax
0x1800810bf  jnz     loc_1800811EE
0x1800810c5  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800810ca  lea     rax, [rsp+2D0h+var_278]
0x1800810cf  mov     [rsp+2D0h+lpdwDisposition], r13; lpdwDisposition
0x1800810d4  lea     rdx, aOlescript; "OLEScript"
0x1800810db  mov     [rsp+2D0h+phkResult], rax; phkResult
0x1800810e0  xor     r9d, r9d; lpClass
0x1800810e3  mov     [rsp+2D0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1800810e8  xor     r8d, r8d; Reserved
0x1800810eb  mov     [rsp+2D0h+samDesired], 2000000h; samDesired
0x1800810f3  mov     [rsp+2D0h+dwOptions], r13d; dwOptions
0x1800810f8  call    cs:__imp_RegCreateKeyExA
0x1800810ff  nop     dword ptr [rax+rax+00h]
0x180081104  test    eax, eax
0x180081106  jnz     loc_1800811DD
0x18008110c  mov     rcx, [rsp+2D0h+var_278]; hKey
0x180081111  call    cs:__imp_RegCloseKey
0x180081118  nop     dword ptr [rax+rax+00h]
0x18008111d  mov     rax, [rbx+20h]
0x180081121  mov     r9d, 1; dwType
0x180081127  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18008112c  xor     r8d, r8d; Reserved
0x18008112f  mov     [rsp+2D0h+samDesired], esi; cbData
0x180081133  xor     edx, edx; lpValueName
0x180081135  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x18008113a  call    cs:__imp_RegSetValueExA
0x180081141  nop     dword ptr [rax+rax+00h]
0x180081146  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18008114b  lea     rax, [rsp+2D0h+var_278]
0x180081150  mov     [rsp+2D0h+lpdwDisposition], r13; lpdwDisposition
0x180081155  lea     rdx, aClsid; "CLSID"
0x18008115c  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180081161  xor     r9d, r9d; lpClass
0x180081164  mov     [rsp+2D0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180081169  xor     r8d, r8d; Reserved
0x18008116c  mov     [rsp+2D0h+samDesired], 2; samDesired
0x180081174  mov     [rsp+2D0h+dwOptions], r13d; dwOptions
0x180081179  call    cs:__imp_RegCreateKeyExA
0x180081180  nop     dword ptr [rax+rax+00h]
0x180081185  test    eax, eax
0x180081187  jnz     short loc_1800811DD
0x180081189  mov     rax, [rbx+18h]
0x18008118d  mov     r9d, 1; dwType
0x180081193  mov     rcx, [rsp+2D0h+var_278]; hKey
0x180081198  xor     r8d, r8d; Reserved
0x18008119b  mov     [rsp+2D0h+samDesired], r14d; cbData
0x1800811a0  xor     edx, edx; lpValueName
0x1800811a2  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x1800811a7  call    cs:__imp_RegSetValueExA
0x1800811ae  nop     dword ptr [rax+rax+00h]
0x1800811b3  mov     rcx, [rsp+2D0h+var_278]; hKey
0x1800811b8  call    cs:__imp_RegCloseKey
0x1800811bf  nop     dword ptr [rax+rax+00h]
0x1800811c4  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800811c9  call    cs:__imp_RegCloseKey
0x1800811d0  nop     dword ptr [rax+rax+00h]
0x1800811d5  inc     r15d
0x1800811d8  jmp     loc_18008106E
0x1800811dd  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800811e2  call    cs:__imp_RegCloseKey
0x1800811e9  nop     dword ptr [rax+rax+00h]
0x1800811ee  mov     eax, 80004005h
0x1800811f3  mov     rcx, [rbp+1D0h+var_50]
0x1800811fa  xor     rcx, rsp; StackCookie
0x1800811fd  call    __security_check_cookie
0x180081202  add     rsp, 298h
0x180081209  pop     r15
0x18008120b  pop     r14
0x18008120d  pop     r13
0x18008120f  pop     r12
0x180081211  pop     rdi
0x180081212  pop     rsi
0x180081213  pop     rbx
0x180081214  pop     rbp
0x180081215  retn
0x180081217  lea     rax, [rsp+2D0h+hKey]
0x18008121c  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180081223  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180081228  lea     rdx, aClsid; "CLSID"
0x18008122f  mov     [rsp+2D0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180081234  mov     [rsp+2D0h+samDesired], 2000000h; samDesired
0x18008123c  mov     [rsp+2D0h+dwOptions], r13d; dwOptions
0x180081241  call    cs:__imp_RegCreateKeyExA
0x180081248  nop     dword ptr [rax+rax+00h]
0x18008124d  test    eax, eax
0x18008124f  jnz     short loc_1800811EE
0x180081251  mov     rdx, [rbx+18h]; lpSubKey
0x180081255  lea     rax, [rsp+2D0h+var_278]
0x18008125a  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18008125f  mov     r14d, 2000000h
0x180081265  mov     [rsp+2D0h+lpdwDisposition], r13; lpdwDisposition
0x18008126a  xor     r9d, r9d; lpClass
0x18008126d  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180081272  xor     r8d, r8d; Reserved
0x180081275  mov     [rsp+2D0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18008127a  mov     [rsp+2D0h+samDesired], r14d; samDesired
0x18008127f  mov     [rsp+2D0h+dwOptions], r13d; dwOptions
0x180081284  call    cs:__imp_RegCreateKeyExA
0x18008128b  nop     dword ptr [rax+rax+00h]
0x180081290  test    eax, eax
0x180081292  jnz     loc_1800811DD
0x180081298  mov     rcx, [rsp+2D0h+var_278]; hKey
0x18008129d  lea     rax, [rsp+2D0h+var_258]
0x1800812a2  mov     [rsp+2D0h+lpdwDisposition], r13; lpdwDisposition
0x1800812a7  lea     rdx, aOlescript; "OLEScript"
0x1800812ae  mov     [rsp+2D0h+phkResult], rax; phkResult
0x1800812b3  xor     r9d, r9d; lpClass
0x1800812b6  mov     [rsp+2D0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1800812bb  xor     r8d, r8d; Reserved
0x1800812be  mov     [rsp+2D0h+samDesired], r14d; samDesired
0x1800812c3  mov     [rsp+2D0h+dwOptions], r13d; dwOptions
0x1800812c8  call    cs:__imp_RegCreateKeyExA
0x1800812cf  nop     dword ptr [rax+rax+00h]
0x1800812d4  test    eax, eax
0x1800812d6  jz      short loc_1800812F3
0x1800812d8  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800812dd  call    cs:__imp_RegCloseKey
0x1800812e4  nop     dword ptr [rax+rax+00h]
0x1800812e9  mov     rcx, [rsp+2D0h+var_278]
0x1800812ee  jmp     loc_1800811E2
0x1800812f3  mov     rax, [rbx+20h]
0x1800812f7  xor     r8d, r8d; Reserved
0x1800812fa  mov     rcx, [rsp+2D0h+var_278]; hKey
0x1800812ff  xor     edx, edx; lpValueName
0x180081301  mov     [rsp+2D0h+samDesired], esi; cbData
0x180081305  mov     esi, 1
0x18008130a  mov     r9d, esi; dwType
0x18008130d  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x180081312  call    cs:__imp_RegSetValueExA
0x180081319  nop     dword ptr [rax+rax+00h]
0x18008131e  mov     rcx, [rsp+2D0h+var_278]; hKey
0x180081323  lea     rax, [rsp+2D0h+var_260]
0x180081328  mov     [rsp+2D0h+lpdwDisposition], r13; lpdwDisposition
0x18008132d  lea     r14d, [rsi+1]
0x180081331  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180081336  lea     rdx, aProgid; "ProgID"
0x18008133d  mov     [rsp+2D0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180081342  xor     r9d, r9d; lpClass
0x180081345  mov     [rsp+2D0h+samDesired], r14d; samDesired
0x18008134a  xor     r8d, r8d; Reserved
0x18008134d  mov     [rsp+2D0h+dwOptions], r13d; dwOptions
0x180081352  call    cs:__imp_RegCreateKeyExA
0x180081359  nop     dword ptr [rax+rax+00h]
0x18008135e  test    eax, eax
0x180081360  jnz     short loc_1800813A8
0x180081362  mov     rax, [rbx+38h]
0x180081366  mov     rcx, [rax]
0x180081369  mov     rax, rdi
0x18008136c  inc     rax
0x18008136f  cmp     [rcx+rax], r13b
0x180081373  jnz     short loc_18008136C
0x180081375  mov     [rsp+2D0h+samDesired], eax; cbData
0x180081379  mov     r9d, esi; dwType
0x18008137c  mov     qword ptr [rsp+2D0h+dwOptions], rcx; lpData
0x180081381  xor     r8d, r8d; Reserved
0x180081384  mov     rcx, [rsp+2D0h+var_260]; hKey
0x180081389  xor     edx, edx; lpValueName
0x18008138b  call    cs:__imp_RegSetValueExA
0x180081392  nop     dword ptr [rax+rax+00h]
0x180081397  mov     rcx, [rsp+2D0h+var_260]; hKey
0x18008139c  call    cs:__imp_RegCloseKey
0x1800813a3  nop     dword ptr [rax+rax+00h]
0x1800813a8  mov     rcx, [rsp+2D0h+var_278]; hKey
0x1800813ad  lea     rax, [rsp+2D0h+var_260]
0x1800813b2  mov     [rsp+2D0h+lpdwDisposition], r13; lpdwDisposition
0x1800813b7  lea     rdx, aInprocserver32; "InprocServer32"
0x1800813be  mov     [rsp+2D0h+phkResult], rax; phkResult
0x1800813c3  xor     r9d, r9d; lpClass
0x1800813c6  mov     [rsp+2D0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1800813cb  xor     r8d, r8d; Reserved
0x1800813ce  mov     [rsp+2D0h+samDesired], r14d; samDesired
0x1800813d3  mov     [rsp+2D0h+dwOptions], r13d; dwOptions
0x1800813d8  call    cs:__imp_RegCreateKeyExA
0x1800813df  nop     dword ptr [rax+rax+00h]
0x1800813e4  test    eax, eax
0x1800813e6  jnz     short loc_180081420
0x1800813e8  mov     rcx, [rsp+2D0h+var_260]; hKey
0x1800813ed  lea     rax, [rbp+1D0h+Filename]
0x1800813f1  mov     [rsp+2D0h+samDesired], r12d; cbData
0x1800813f6  mov     r9d, esi; dwType
0x1800813f9  xor     r8d, r8d; Reserved
0x1800813fc  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x180081401  xor     edx, edx; lpValueName
0x180081403  call    cs:__imp_RegSetValueExA
0x18008140a  nop     dword ptr [rax+rax+00h]
0x18008140f  mov     rcx, [rsp+2D0h+var_260]; hKey
0x180081414  call    cs:__imp_RegCloseKey
0x18008141b  nop     dword ptr [rax+rax+00h]
0x180081420  mov     rcx, [rsp+2D0h+var_278]; hKey
0x180081425  lea     rax, [rsp+2D0h+var_270]
0x18008142a  mov     r9d, r14d; samDesired
0x18008142d  mov     qword ptr [rsp+2D0h+dwOptions], rax; phkResult
0x180081432  xor     r8d, r8d; ulOptions
0x180081435  mov     [rsp+2D0h+var_270], r13
0x18008143a  lea     rdx, aInprocserver32; "InprocServer32"
0x180081441  call    cs:__imp_RegOpenKeyExA
0x180081448  nop     dword ptr [rax+rax+00h]
0x18008144d  test    eax, eax
0x18008144f  jz      short loc_180081478
0x180081451  mov     rcx, [rsp+2D0h+var_258]; hKey
0x180081456  call    cs:__imp_RegCloseKey
0x18008145d  nop     dword ptr [rax+rax+00h]
0x180081462  mov     rcx, [rsp+2D0h+var_278]; hKey
0x180081467  call    cs:__imp_RegCloseKey
0x18008146e  nop     dword ptr [rax+rax+00h]
0x180081473  jmp     loc_1800811DD
0x180081478  mov     rcx, [rsp+2D0h+var_270]; hKey
0x18008147d  lea     rax, Data; "Both"
0x180081484  mov     [rsp+2D0h+samDesired], 4; cbData
0x18008148c  lea     rdx, aThreadingmodel; "ThreadingModel"
0x180081493  mov     r9d, esi; dwType
0x180081496  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x18008149b  xor     r8d, r8d; Reserved
0x18008149e  call    cs:__imp_RegSetValueExA
0x1800814a5  nop     dword ptr [rax+rax+00h]
0x1800814aa  mov     rcx, [rsp+2D0h+var_270]; hKey
0x1800814af  call    cs:__imp_RegCloseKey
0x1800814b6  nop     dword ptr [rax+rax+00h]
0x1800814bb  mov     rcx, [rsp+2D0h+var_258]; hKey
0x1800814c0  call    cs:__imp_RegCloseKey
0x1800814c7  nop     dword ptr [rax+rax+00h]
0x1800814cc  mov     rcx, [rsp+2D0h+var_278]; hKey
0x1800814d1  call    cs:__imp_RegCloseKey
0x1800814d8  nop     dword ptr [rax+rax+00h]
0x1800814dd  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800814e2  call    cs:__imp_RegCloseKey
0x1800814e9  nop     dword ptr [rax+rax+00h]
0x1800814ee  mov     rdx, [rbx+28h]; lpSubKey
0x1800814f2  test    rdx, rdx
0x1800814f5  jz      loc_180081585
0x1800814fb  mov     [rsp+2D0h+lpdwDisposition], r13; lpdwDisposition
0x180081500  lea     rax, [rsp+2D0h+hKey]
0x180081505  mov     [rsp+2D0h+phkResult], rax; phkResult
0x18008150a  xor     r9d, r9d; lpClass
0x18008150d  mov     [rsp+2D0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180081512  xor     r8d, r8d; Reserved
0x180081515  mov     [rsp+2D0h+samDesired], r14d; samDesired
0x18008151a  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180081521  mov     [rsp+2D0h+dwOptions], r13d; dwOptions
  ... truncated ...
```
