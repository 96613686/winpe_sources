# RegisterControlObject(char const *,char const *,long,_GUID const &,_GUID const &,ulong,ushort)

- ea: `0x18006b5f8`
- end: `0x18006ba3d`
- name: `?RegisterControlObject@@YAHPEBD0JAEBU_GUID@@1KG@Z`
- size: `1093`
- prototype: `__int64 __fastcall(const char *, const char *, int, const struct _GUID *, const struct _GUID *, unsigned int, unsigned __int16)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004040c`

## callees

- `0x1800029b8`
- `0x18000f460`
- `0x18006aeac`
- `0x18006b5f8`
- `0x18006bf3c`
- `0x180075c90`

## import_xrefs

- `KERNEL32!GetModuleFileNameA` at `0x18006b869`
- `KERNEL32!GetModuleFileNameA` at `0x18006b869`
- `ADVAPI32!RegCloseKey` at `0x18006b714`
- `ADVAPI32!RegCloseKey` at `0x18006b842`
- `ADVAPI32!RegCloseKey` at `0x18006b855`
- `ADVAPI32!RegCloseKey` at `0x18006b94e`
- `ADVAPI32!RegCloseKey` at `0x18006b9f1`
- `ADVAPI32!RegCloseKey` at `0x18006ba01`
- `ADVAPI32!RegCloseKey` at `0x18006b714`
- `ADVAPI32!RegCloseKey` at `0x18006b842`
- `ADVAPI32!RegCloseKey` at `0x18006b855`
- `ADVAPI32!RegCloseKey` at `0x18006b94e`
- `ADVAPI32!RegCloseKey` at `0x18006b9f1`
- `ADVAPI32!RegCloseKey` at `0x18006ba01`
- `ADVAPI32!RegCreateKeyExA` at `0x18006b6ff`
- `ADVAPI32!RegCreateKeyExA` at `0x18006b754`
- `ADVAPI32!RegCreateKeyExA` at `0x18006b7ce`
- `ADVAPI32!RegCreateKeyExA` at `0x18006b8fa`
- `ADVAPI32!RegCreateKeyExA` at `0x18006b989`
- `ADVAPI32!RegCreateKeyExA` at `0x18006b6ff`
- `ADVAPI32!RegCreateKeyExA` at `0x18006b754`
- `ADVAPI32!RegCreateKeyExA` at `0x18006b7ce`
- `ADVAPI32!RegCreateKeyExA` at `0x18006b8fa`
- `ADVAPI32!RegCreateKeyExA` at `0x18006b989`
- `ADVAPI32!RegSetValueExA` at `0x18006b789`
- `ADVAPI32!RegSetValueExA` at `0x18006b835`
- `ADVAPI32!RegSetValueExA` at `0x18006b939`
- `ADVAPI32!RegSetValueExA` at `0x18006b9df`
- `ADVAPI32!RegSetValueExA` at `0x18006b789`
- `ADVAPI32!RegSetValueExA` at `0x18006b835`
- `ADVAPI32!RegSetValueExA` at `0x18006b939`
- `ADVAPI32!RegSetValueExA` at `0x18006b9df`
- `ADVAPI32!RegOpenKeyExA` at `0x18006b6b5`
- `ADVAPI32!RegOpenKeyExA` at `0x18006b6b5`

## string_xrefs

- `0x18006b67a`: `CLSID\%s`

## pseudocode

```c
_BOOL8 __fastcall RegisterControlObject(
        const char *a1,
        const char *a2,
        int a3,
        const struct _GUID *a4,
        const struct _GUID *a5,
        unsigned int a6,
        unsigned __int16 a7)
{
  LSTATUS v8; // ebx
  __int64 v9; // rdi
  __int64 v10; // rax
  DWORD ModuleFileNameA; // eax
  __int64 v12; // rax
  HKEY v14; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v17; // [rsp+68h] [rbp-98h] BYREF
  char v18[48]; // [rsp+70h] [rbp-90h] BYREF
  CHAR SubKey[259]; // [rsp+A0h] [rbp-60h] BYREF
  char v20; // [rsp+1A3h] [rbp+A3h]

  hKey = 0;
  v14 = 0;
  v17 = 0;
  dwDisposition = 0;
  if ( !(unsigned int)RegisterAutomationObject(a1, a2, a3, a4, a5) )
    return 0;
  StringFromGuidA(a5, v18);
  v8 = 5;
  if ( (int)StringCchPrintfA(SubKey, 0x104u, "CLSID\\%s", v18) >= 0 )
  {
    if ( !RegOpenKeyExA(HKEY_CLASSES_ROOT, SubKey, 0, 0xF003Fu, &hKey) )
    {
      v8 = RegCreateKeyExA(hKey, "Control", 0, (LPSTR)Class, 0, 0xF003Fu, 0, &v14, &dwDisposition);
      if ( !v8 )
      {
        RegCloseKey(v14);
        v14 = 0;
        v8 = RegCreateKeyExA(hKey, "MiscStatus", 0, (LPSTR)Class, 0, 0xF003Fu, 0, &v14, &dwDisposition);
        if ( !v8 )
        {
          strcpy(SubKey, "0");
          v8 = RegSetValueExA(v14, 0, 0, 1u, (const BYTE *)SubKey, 2u);
          if ( !v8 )
          {
            v8 = RegCreateKeyExA(v14, "1", 0, (LPSTR)Class, 0, 0xF003Fu, 0, &v17, &dwDisposition);
            if ( !v8 )
            {
              v8 = 5;
              if ( (int)StringCchPrintfA(SubKey, 0x104u, "%d", a6) >= 0 )
              {
                v9 = -1;
                v10 = -1;
                do
                  ++v10;
                while ( SubKey[v10] );
                v8 = RegSetValueExA(v17, 0, 0, 1u, (const BYTE *)SubKey, v10 + 1);
                RegCloseKey(v17);
                if ( !v8 )
                {
                  RegCloseKey(v14);
                  ModuleFileNameA = GetModuleFileNameA(hInstance, SubKey, 0x104u);
                  v20 = 0;
                  if ( ModuleFileNameA - 1 <= 0x102 )
                  {
                    v8 = 5;
                    if ( (int)StringCchPrintfA(v18, 0x28u, ", %d", a7) >= 0
                      && (int)StringCchCatA(SubKey, 0x104u, v18) >= 0 )
                    {
                      v8 = RegCreateKeyExA(
                             hKey,
                             "ToolboxBitmap32",
                             0,
                             (LPSTR)Class,
                             0,
                             0xF003Fu,
                             0,
                             &v14,
                             &dwDisposition);
                      if ( !v8 )
                      {
                        v12 = -1;
                        do
                          ++v12;
                        while ( SubKey[v12] );
                        v8 = RegSetValueExA(v14, 0, 0, 1u, (const BYTE *)SubKey, v12 + 1);
                        if ( !v8 )
                        {
                          RegCloseKey(v14);
                          v8 = RegCreateKeyExA(hKey, "Version", 0, (LPSTR)Class, 0, 0xF003Fu, 0, &v14, &dwDisposition);
                          if ( !v8 )
                          {
                            v8 = 5;
                            if ( (int)StringCchPrintfA(SubKey, 0x104u, "%ld.0", a3) >= 0 )
                            {
                              do
                                ++v9;
                              while ( SubKey[v9] );
                              v8 = RegSetValueExA(v14, 0, 0, 1u, (const BYTE *)SubKey, v9 + 1);
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
      goto LABEL_23;
    }
    return 0;
  }
LABEL_23:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v14 )
    RegCloseKey(v14);
  return v8 == 0;
}

```

## disassembly

```asm
0x18006b5f8  mov     [rsp-8+arg_0], rbx
0x18006b5fd  push    rbp
0x18006b5fe  push    rsi
0x18006b5ff  push    rdi
0x18006b600  push    r12
0x18006b602  push    r13
0x18006b604  push    r14
0x18006b606  push    r15
0x18006b608  lea     rbp, [rsp-0C0h]
0x18006b610  sub     rsp, 1C0h
0x18006b617  mov     rax, cs:__security_cookie
0x18006b61e  xor     rax, rsp
0x18006b621  mov     [rbp+0F0h+var_40], rax
0x18006b628  mov     rbx, [rbp+0F0h+arg_20]
0x18006b62f  xor     r14d, r14d
0x18006b632  mov     [rsp+1F0h+hKey], r14
0x18006b637  mov     esi, r8d
0x18006b63a  mov     [rsp+1F0h+var_1A0], r14
0x18006b63f  mov     [rsp+1F0h+var_188], r14
0x18006b644  mov     [rsp+1F0h+dwDisposition], r14d
0x18006b649  mov     [rsp+1F0h+phkResult], rbx; struct _GUID *
0x18006b64e  call    ?RegisterAutomationObject@@YAHPEBD0JAEBU_GUID@@1@Z; RegisterAutomationObject(char const *,char const *,long,_GUID const &,_GUID const &)
0x18006b653  test    eax, eax
0x18006b655  jz      loc_18006BA11
0x18006b65b  lea     rdx, [rsp+1F0h+var_180]; char *
0x18006b660  mov     rcx, rbx; struct _GUID *
0x18006b663  call    ?StringFromGuidA@@YAHAEBU_GUID@@PEAD@Z; StringFromGuidA(_GUID const &,char *)
0x18006b668  mov     r12d, 104h
0x18006b66e  lea     edi, [r14+5]
0x18006b672  mov     edx, r12d; unsigned __int64
0x18006b675  lea     r9, [rsp+1F0h+var_180]
0x18006b67a  lea     r8, aClsidS; "CLSID\\%s"
0x18006b681  mov     ebx, edi
0x18006b683  lea     rcx, [rbp+0F0h+SubKey]; char *
0x18006b687  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18006b68c  test    eax, eax
0x18006b68e  js      loc_18006B9E7
0x18006b694  lea     rax, [rsp+1F0h+hKey]
0x18006b699  mov     r15d, 0F003Fh
0x18006b69f  mov     r9d, r15d; samDesired
0x18006b6a2  mov     [rsp+1F0h+phkResult], rax; phkResult
0x18006b6a7  xor     r8d, r8d; ulOptions
0x18006b6aa  lea     rdx, [rbp+0F0h+SubKey]; lpSubKey
0x18006b6ae  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18006b6b5  call    cs:__imp_RegOpenKeyExA
0x18006b6bb  test    eax, eax
0x18006b6bd  jnz     loc_18006BA11
0x18006b6c3  mov     rcx, [rsp+1F0h+hKey]; hKey
0x18006b6c8  lea     rax, [rsp+1F0h+dwDisposition]
0x18006b6cd  mov     [rsp+1F0h+lpdwDisposition], rax; lpdwDisposition
0x18006b6d2  lea     r13, Class
0x18006b6d9  lea     rax, [rsp+1F0h+var_1A0]
0x18006b6de  mov     r9, r13; lpClass
0x18006b6e1  mov     [rsp+1F0h+var_1B8], rax; phkResult
0x18006b6e6  lea     rdx, aControl; "Control"
0x18006b6ed  mov     [rsp+1F0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18006b6f2  xor     r8d, r8d; Reserved
0x18006b6f5  mov     [rsp+1F0h+samDesired], r15d; samDesired
0x18006b6fa  mov     dword ptr [rsp+1F0h+phkResult], r14d; dwOptions
0x18006b6ff  call    cs:__imp_RegCreateKeyExA
0x18006b705  mov     ebx, eax
0x18006b707  test    eax, eax
0x18006b709  jnz     loc_18006B9E7
0x18006b70f  mov     rcx, [rsp+1F0h+var_1A0]; hKey
0x18006b714  call    cs:__imp_RegCloseKey
0x18006b71a  mov     rcx, [rsp+1F0h+hKey]; hKey
0x18006b71f  lea     rax, [rsp+1F0h+dwDisposition]
0x18006b724  mov     [rsp+1F0h+lpdwDisposition], rax; lpdwDisposition
0x18006b729  lea     rdx, aMiscstatus; "MiscStatus"
0x18006b730  lea     rax, [rsp+1F0h+var_1A0]
0x18006b735  mov     [rsp+1F0h+var_1A0], r14
0x18006b73a  mov     [rsp+1F0h+var_1B8], rax; phkResult
0x18006b73f  mov     r9, r13; lpClass
0x18006b742  mov     [rsp+1F0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18006b747  xor     r8d, r8d; Reserved
0x18006b74a  mov     [rsp+1F0h+samDesired], r15d; samDesired
0x18006b74f  mov     dword ptr [rsp+1F0h+phkResult], r14d; dwOptions
0x18006b754  call    cs:__imp_RegCreateKeyExA
0x18006b75a  mov     ebx, eax
0x18006b75c  test    eax, eax
0x18006b75e  jnz     loc_18006B9E7
0x18006b764  mov     rcx, [rsp+1F0h+var_1A0]; hKey
0x18006b769  lea     rax, [rbp+0F0h+SubKey]
0x18006b76d  mov     [rsp+1F0h+samDesired], 2; cbData
0x18006b775  lea     r9d, [r14+1]; dwType
0x18006b779  xor     r8d, r8d; Reserved
0x18006b77c  mov     [rsp+1F0h+phkResult], rax; lpData
0x18006b781  xor     edx, edx; lpValueName
0x18006b783  mov     word ptr [rbp+0F0h+SubKey], 30h ; '0'
0x18006b789  call    cs:__imp_RegSetValueExA
0x18006b78f  mov     ebx, eax
0x18006b791  test    eax, eax
0x18006b793  jnz     loc_18006B9E7
0x18006b799  mov     rcx, [rsp+1F0h+var_1A0]; hKey
0x18006b79e  lea     rax, [rsp+1F0h+dwDisposition]
0x18006b7a3  mov     [rsp+1F0h+lpdwDisposition], rax; lpdwDisposition
0x18006b7a8  lea     rdx, a1; "1"
0x18006b7af  lea     rax, [rsp+1F0h+var_188]
0x18006b7b4  mov     r9, r13; lpClass
0x18006b7b7  mov     [rsp+1F0h+var_1B8], rax; phkResult
0x18006b7bc  xor     r8d, r8d; Reserved
0x18006b7bf  mov     [rsp+1F0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18006b7c4  mov     [rsp+1F0h+samDesired], r15d; samDesired
0x18006b7c9  mov     dword ptr [rsp+1F0h+phkResult], r14d; dwOptions
0x18006b7ce  call    cs:__imp_RegCreateKeyExA
0x18006b7d4  mov     ebx, eax
0x18006b7d6  test    eax, eax
0x18006b7d8  jnz     loc_18006B9E7
0x18006b7de  mov     r9d, [rbp+0F0h+arg_28]
0x18006b7e5  lea     r8, aD_0; "%d"
0x18006b7ec  mov     edx, r12d; unsigned __int64
0x18006b7ef  lea     rcx, [rbp+0F0h+SubKey]; char *
0x18006b7f3  mov     ebx, edi
0x18006b7f5  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18006b7fa  test    eax, eax
0x18006b7fc  js      loc_18006B9E7
0x18006b802  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18006b806  lea     rcx, [rbp+0F0h+SubKey]
0x18006b80a  mov     rax, rdi
0x18006b80d  inc     rax
0x18006b810  cmp     [rcx+rax], r14b
0x18006b814  jnz     short loc_18006B80D
0x18006b816  mov     rcx, [rsp+1F0h+var_188]; hKey
0x18006b81b  inc     eax
0x18006b81d  mov     [rsp+1F0h+samDesired], eax; cbData
0x18006b821  mov     r9d, 1; dwType
0x18006b827  lea     rax, [rbp+0F0h+SubKey]
0x18006b82b  xor     r8d, r8d; Reserved
0x18006b82e  xor     edx, edx; lpValueName
0x18006b830  mov     [rsp+1F0h+phkResult], rax; lpData
0x18006b835  call    cs:__imp_RegSetValueExA
0x18006b83b  mov     rcx, [rsp+1F0h+var_188]; hKey
0x18006b840  mov     ebx, eax
0x18006b842  call    cs:__imp_RegCloseKey
0x18006b848  test    ebx, ebx
0x18006b84a  jnz     loc_18006B9E7
0x18006b850  mov     rcx, [rsp+1F0h+var_1A0]; hKey
0x18006b855  call    cs:__imp_RegCloseKey
0x18006b85b  mov     rcx, cs:hInstance; hModule
0x18006b862  lea     rdx, [rbp+0F0h+SubKey]; lpFilename
0x18006b866  mov     r8d, r12d; nSize
0x18006b869  call    cs:__imp_GetModuleFileNameA
0x18006b86f  dec     eax
0x18006b871  mov     [rbp+0F0h+var_4D], r14b
0x18006b878  cmp     eax, 102h
0x18006b87d  ja      loc_18006B9E7
0x18006b883  movzx   r9d, [rbp+0F0h+arg_30]
0x18006b88b  lea     r8, aD_1; ", %d"
0x18006b892  mov     ebx, 5
0x18006b897  lea     rcx, [rsp+1F0h+var_180]; char *
0x18006b89c  lea     edx, [rbx+23h]; unsigned __int64
0x18006b89f  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18006b8a4  test    eax, eax
0x18006b8a6  js      loc_18006B9E7
0x18006b8ac  lea     r8, [rsp+1F0h+var_180]; char *
0x18006b8b1  mov     rdx, r12; unsigned __int64
0x18006b8b4  lea     rcx, [rbp+0F0h+SubKey]; char *
0x18006b8b8  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18006b8bd  test    eax, eax
0x18006b8bf  js      loc_18006B9E7
0x18006b8c5  mov     rcx, [rsp+1F0h+hKey]; hKey
0x18006b8ca  lea     rax, [rsp+1F0h+dwDisposition]
0x18006b8cf  mov     [rsp+1F0h+lpdwDisposition], rax; lpdwDisposition
0x18006b8d4  lea     rdx, aToolboxbitmap3; "ToolboxBitmap32"
0x18006b8db  lea     rax, [rsp+1F0h+var_1A0]
0x18006b8e0  mov     r9, r13; lpClass
0x18006b8e3  mov     [rsp+1F0h+var_1B8], rax; phkResult
0x18006b8e8  xor     r8d, r8d; Reserved
0x18006b8eb  mov     [rsp+1F0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18006b8f0  mov     [rsp+1F0h+samDesired], r15d; samDesired
0x18006b8f5  mov     dword ptr [rsp+1F0h+phkResult], r14d; dwOptions
0x18006b8fa  call    cs:__imp_RegCreateKeyExA
0x18006b900  mov     ebx, eax
0x18006b902  test    eax, eax
0x18006b904  jnz     loc_18006B9E7
0x18006b90a  lea     rcx, [rbp+0F0h+SubKey]
0x18006b90e  mov     rax, rdi
0x18006b911  inc     rax
0x18006b914  cmp     [rcx+rax], r14b
0x18006b918  jnz     short loc_18006B911
0x18006b91a  mov     rcx, [rsp+1F0h+var_1A0]; hKey
0x18006b91f  inc     eax
0x18006b921  mov     [rsp+1F0h+samDesired], eax; cbData
0x18006b925  mov     r9d, 1; dwType
0x18006b92b  lea     rax, [rbp+0F0h+SubKey]
0x18006b92f  xor     r8d, r8d; Reserved
0x18006b932  xor     edx, edx; lpValueName
0x18006b934  mov     [rsp+1F0h+phkResult], rax; lpData
0x18006b939  call    cs:__imp_RegSetValueExA
0x18006b93f  mov     ebx, eax
0x18006b941  test    eax, eax
0x18006b943  jnz     loc_18006B9E7
0x18006b949  mov     rcx, [rsp+1F0h+var_1A0]; hKey
0x18006b94e  call    cs:__imp_RegCloseKey
0x18006b954  mov     rcx, [rsp+1F0h+hKey]; hKey
0x18006b959  lea     rax, [rsp+1F0h+dwDisposition]
0x18006b95e  mov     [rsp+1F0h+lpdwDisposition], rax; lpdwDisposition
0x18006b963  lea     rdx, aVersion; "Version"
0x18006b96a  lea     rax, [rsp+1F0h+var_1A0]
0x18006b96f  mov     r9, r13; lpClass
0x18006b972  mov     [rsp+1F0h+var_1B8], rax; phkResult
0x18006b977  xor     r8d, r8d; Reserved
0x18006b97a  mov     [rsp+1F0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18006b97f  mov     [rsp+1F0h+samDesired], r15d; samDesired
0x18006b984  mov     dword ptr [rsp+1F0h+phkResult], r14d; dwOptions
0x18006b989  call    cs:__imp_RegCreateKeyExA
0x18006b98f  mov     ebx, eax
0x18006b991  test    eax, eax
0x18006b993  jnz     short loc_18006B9E7
0x18006b995  mov     r9d, esi
0x18006b998  lea     r8, aLd0; "%ld.0"
0x18006b99f  mov     rdx, r12; unsigned __int64
0x18006b9a2  lea     rcx, [rbp+0F0h+SubKey]; char *
0x18006b9a6  lea     ebx, [rax+5]
0x18006b9a9  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18006b9ae  test    eax, eax
0x18006b9b0  js      short loc_18006B9E7
0x18006b9b2  lea     rax, [rbp+0F0h+SubKey]
0x18006b9b6  inc     rdi
0x18006b9b9  cmp     [rax+rdi], r14b
0x18006b9bd  jnz     short loc_18006B9B6
0x18006b9bf  mov     rcx, [rsp+1F0h+var_1A0]; hKey
0x18006b9c4  lea     eax, [rdi+1]
0x18006b9c7  mov     [rsp+1F0h+samDesired], eax; cbData
0x18006b9cb  mov     r9d, 1; dwType
0x18006b9d1  lea     rax, [rbp+0F0h+SubKey]
0x18006b9d5  xor     r8d, r8d; Reserved
0x18006b9d8  xor     edx, edx; lpValueName
0x18006b9da  mov     [rsp+1F0h+phkResult], rax; lpData
0x18006b9df  call    cs:__imp_RegSetValueExA
0x18006b9e5  mov     ebx, eax
0x18006b9e7  mov     rcx, [rsp+1F0h+hKey]; hKey
0x18006b9ec  test    rcx, rcx
0x18006b9ef  jz      short loc_18006B9F7
0x18006b9f1  call    cs:__imp_RegCloseKey
0x18006b9f7  mov     rcx, [rsp+1F0h+var_1A0]; hKey
0x18006b9fc  test    rcx, rcx
0x18006b9ff  jz      short loc_18006BA07
0x18006ba01  call    cs:__imp_RegCloseKey
0x18006ba07  test    ebx, ebx
0x18006ba09  mov     eax, r14d
0x18006ba0c  setz    al
0x18006ba0f  jmp     short loc_18006BA13
0x18006ba11  xor     eax, eax
0x18006ba13  mov     rcx, [rbp+0F0h+var_40]
0x18006ba1a  xor     rcx, rsp; StackCookie
0x18006ba1d  call    __security_check_cookie
0x18006ba22  mov     rbx, [rsp+1F0h+arg_0]
0x18006ba2a  add     rsp, 1C0h
0x18006ba31  pop     r15
0x18006ba33  pop     r14
0x18006ba35  pop     r13
0x18006ba37  pop     r12
0x18006ba39  pop     rdi
0x18006ba3a  pop     rsi
0x18006ba3b  pop     rbp
0x18006ba3c  retn
```
