# HrCheckLabelAccess(ulong,HWND__ * const,_SMIME_SECURITY_LABEL *,_CERT_CONTEXT const * const,_CERT_CONTEXT const * const,void * const)

- ea: `0x18005b1f0`
- end: `0x18005b53f`
- name: `?HrCheckLabelAccess@@YAJKQEAUHWND__@@PEAU_SMIME_SECURITY_LABEL@@QEBU_CERT_CONTEXT@@2QEAX@Z`
- size: `847`
- prototype: `__int64 __fastcall(unsigned int, HWND, struct _SMIME_SECURITY_LABEL *, const struct _CERT_CONTEXT *const, const struct _CERT_CONTEXT *const, void *const)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005be40`

## callees

- `0x180012cd0`
- `0x18005b1f0`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `SHLWAPI!PathFindFileNameA` at `0x18005b35d`
- `SHLWAPI!PathFindFileNameA` at `0x18005b38c`
- `SHLWAPI!PathFindFileNameA` at `0x18005b35d`
- `SHLWAPI!PathFindFileNameA` at `0x18005b38c`
- `ADVAPI32!RegOpenKeyExA` at `0x18005b28a`
- `ADVAPI32!RegOpenKeyExA` at `0x18005b2bc`
- `ADVAPI32!RegOpenKeyExA` at `0x18005b301`
- `ADVAPI32!RegOpenKeyExA` at `0x18005b28a`
- `ADVAPI32!RegOpenKeyExA` at `0x18005b2bc`
- `ADVAPI32!RegOpenKeyExA` at `0x18005b301`
- `ADVAPI32!RegQueryValueExA` at `0x18005b34a`
- `ADVAPI32!RegQueryValueExA` at `0x18005b440`
- `ADVAPI32!RegQueryValueExA` at `0x18005b34a`
- `ADVAPI32!RegQueryValueExA` at `0x18005b440`
- `ADVAPI32!RegCloseKey` at `0x18005b2d7`
- `ADVAPI32!RegCloseKey` at `0x18005b504`
- `ADVAPI32!RegCloseKey` at `0x18005b514`
- `ADVAPI32!RegCloseKey` at `0x18005b2d7`
- `ADVAPI32!RegCloseKey` at `0x18005b504`
- `ADVAPI32!RegCloseKey` at `0x18005b514`
- `KERNEL32!LoadLibraryExA` at `0x18005b3f6`
- `KERNEL32!LoadLibraryExA` at `0x18005b3f6`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x18005b3cb`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x18005b3cb`
- `KERNEL32!GetProcAddress` at `0x18005b458`
- `KERNEL32!GetProcAddress` at `0x18005b458`
- `KERNEL32!GetACP` at `0x18005b466`
- `KERNEL32!GetACP` at `0x18005b466`
- `KERNEL32!FreeLibrary` at `0x18005b4f4`
- `KERNEL32!FreeLibrary` at `0x18005b4f4`

## string_xrefs

- `0x18005b343`: `DllPath`
- `0x18005b27c`: `Software\Microsoft\Cryptography\OID\EncodingType 1\SMIMESecurityLabel`

## pseudocode

```c
__int64 __fastcall HrCheckLabelAccess(
        unsigned int a1,
        HWND a2,
        LPCSTR *a3,
        const struct _CERT_CONTEXT *const a4,
        const struct _CERT_CONTEXT *const a5,
        void *const a6)
{
  int v6; // ebx
  HMODULE Library; // rdi
  const char *FileNameA; // rax
  FARPROC ProcAddress; // rbx
  UINT ACP; // eax
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  DWORD Type; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v20; // [rsp+60h] [rbp-A0h] BYREF
  void *v21; // [rsp+68h] [rbp-98h]
  BYTE Data[272]; // [rsp+70h] [rbp-90h] BYREF
  CHAR Dst[272]; // [rsp+180h] [rbp+80h] BYREF
  BYTE v24[272]; // [rsp+290h] [rbp+190h] BYREF
  CHAR pszPath[272]; // [rsp+3A0h] [rbp+2A0h] BYREF

  v6 = 0;
  v21 = a6;
  hKey = 0;
  phkResult = 0;
  v20 = 0;
  Library = 0;
  Type = 0;
  cbData = 0;
  if ( a3 && *a3 )
  {
    if ( RegOpenKeyExA(
           HKEY_LOCAL_MACHINE,
           "Software\\Microsoft\\Cryptography\\OID\\EncodingType 1\\SMIMESecurityLabel",
           0,
           0x20019u,
           &hKey)
      || !hKey )
    {
      goto LABEL_23;
    }
    if ( RegOpenKeyExA(hKey, *a3, 0, 0x20019u, &phkResult) || !phkResult )
    {
      if ( phkResult )
      {
        RegCloseKey(phkResult);
        phkResult = 0;
      }
      if ( RegOpenKeyExA(hKey, "default", 0, 0x20019u, &phkResult) || !phkResult )
        goto LABEL_23;
    }
    cbData = 260;
    if ( RegQueryValueExA(phkResult, "DllPath", 0, &Type, Data, &cbData) )
      goto LABEL_23;
    if ( Data != (BYTE *)PathFindFileNameA((LPCSTR)Data) )
    {
      StringCchCopyA(pszPath, 0x104u, (const char *)Data);
      FileNameA = PathFindFileNameA(pszPath);
      StringCchCopyA((char *)Data, 0x104u, FileNameA);
    }
    Data[259] = 0;
    if ( Type == 2 )
    {
      memset_0(Dst, 0, 0x104u);
      ExpandEnvironmentStringsA((LPCSTR)Data, Dst, 0x104u);
      Dst[259] = 0;
      StringCchCopyA((char *)Data, 0x104u, Dst);
    }
    Library = LoadLibraryExA((LPCSTR)Data, 0, 8u);
    if ( !Library
      || (cbData = 260, v24[260] = 0, RegQueryValueExA(phkResult, "FuncName", 0, &Type, v24, &cbData))
      || (ProcAddress = GetProcAddress(Library, (LPCSTR)v24)) == 0 )
    {
LABEL_23:
      v6 = -2146644237;
    }
    else
    {
      ACP = GetACP();
      v6 = ((__int64 (__fastcall *)(_QWORD, LPCSTR, _QWORD, GUID *, __int64 *))ProcAddress)(
             0,
             *a3,
             ACP,
             &IID_ISMimePolicyCheckAccess,
             &v20);
      if ( v6 >= 0 )
      {
        if ( v20 )
          v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, HWND, LPCSTR *, const struct _CERT_CONTEXT *const, const struct _CERT_CONTEXT *const, void *))(*(_QWORD *)v20 + 24LL))(
                 v20,
                 a1,
                 a2,
                 a3,
                 a4,
                 a5,
                 v21);
        else
          v6 = -2147467259;
      }
    }
  }
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  if ( Library )
    FreeLibrary(Library);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18005b1f0  push    rbp
0x18005b1f2  push    rbx
0x18005b1f3  push    rsi
0x18005b1f4  push    rdi
0x18005b1f5  push    r12
0x18005b1f7  push    r13
0x18005b1f9  push    r14
0x18005b1fb  push    r15
0x18005b1fd  lea     rbp, [rsp-3C8h]
0x18005b205  sub     rsp, 4C8h
0x18005b20c  mov     rax, cs:__security_cookie
0x18005b213  xor     rax, rsp
0x18005b216  mov     [rbp+400h+var_50], rax
0x18005b21d  mov     rax, [rbp+400h+arg_28]
0x18005b224  xor     ebx, ebx
0x18005b226  mov     r13, [rbp+400h+arg_20]
0x18005b22d  mov     r12, r9
0x18005b230  mov     [rsp+500h+var_498], rax
0x18005b235  mov     rsi, r8
0x18005b238  mov     [rsp+500h+hKey], rbx
0x18005b23d  mov     r15, rdx
0x18005b240  mov     [rsp+500h+var_4B8], rbx
0x18005b245  mov     r14d, ecx
0x18005b248  mov     [rsp+500h+var_4A0], rbx
0x18005b24d  mov     edi, ebx
0x18005b24f  mov     [rsp+500h+Type], ebx
0x18005b253  mov     [rsp+500h+cbData], ebx
0x18005b257  test    r8, r8
0x18005b25a  jz      loc_18005B4D6
0x18005b260  cmp     [r8], rbx
0x18005b263  jz      loc_18005B4D6
0x18005b269  lea     rax, [rsp+500h+hKey]
0x18005b26e  mov     r9d, 20019h; samDesired
0x18005b274  xor     r8d, r8d; ulOptions
0x18005b277  mov     [rsp+500h+phkResult], rax; phkResult
0x18005b27c  lea     rdx, c_szSecLabelPoliciesRegKey; "Software\\Microsoft\\Cryptography\\OID"...
0x18005b283  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005b28a  call    cs:__imp_RegOpenKeyExA
0x18005b290  test    eax, eax
0x18005b292  jnz     loc_18005B4D1
0x18005b298  mov     rcx, [rsp+500h+hKey]; hKey
0x18005b29d  test    rcx, rcx
0x18005b2a0  jz      loc_18005B4D1
0x18005b2a6  mov     rdx, [rsi]; lpSubKey
0x18005b2a9  lea     rax, [rsp+500h+var_4B8]
0x18005b2ae  mov     r9d, 20019h; samDesired
0x18005b2b4  mov     [rsp+500h+phkResult], rax; phkResult
0x18005b2b9  xor     r8d, r8d; ulOptions
0x18005b2bc  call    cs:__imp_RegOpenKeyExA
0x18005b2c2  test    eax, eax
0x18005b2c4  jnz     short loc_18005B2CD
0x18005b2c6  cmp     [rsp+500h+var_4B8], rbx
0x18005b2cb  jnz     short loc_18005B31A
0x18005b2cd  mov     rcx, [rsp+500h+var_4B8]; hKey
0x18005b2d2  test    rcx, rcx
0x18005b2d5  jz      short loc_18005B2E2
0x18005b2d7  call    cs:__imp_RegCloseKey
0x18005b2dd  mov     [rsp+500h+var_4B8], rbx
0x18005b2e2  mov     rcx, [rsp+500h+hKey]; hKey
0x18005b2e7  lea     rax, [rsp+500h+var_4B8]
0x18005b2ec  mov     r9d, 20019h; samDesired
0x18005b2f2  mov     [rsp+500h+phkResult], rax; phkResult
0x18005b2f7  xor     r8d, r8d; ulOptions
0x18005b2fa  lea     rdx, c_szDefaultPolicyOid; "default"
0x18005b301  call    cs:__imp_RegOpenKeyExA
0x18005b307  test    eax, eax
0x18005b309  jnz     loc_18005B4D1
0x18005b30f  cmp     [rsp+500h+var_4B8], rbx
0x18005b314  jz      loc_18005B4D1
0x18005b31a  mov     rcx, [rsp+500h+var_4B8]; hKey
0x18005b31f  lea     rax, [rsp+500h+cbData]
0x18005b324  mov     [rsp+500h+lpcbData], rax; lpcbData
0x18005b329  lea     r9, [rsp+500h+Type]; lpType
0x18005b32e  lea     rax, [rsp+500h+Data]
0x18005b333  mov     [rsp+500h+cbData], 104h
0x18005b33b  xor     r8d, r8d; lpReserved
0x18005b33e  mov     [rsp+500h+phkResult], rax; lpData
0x18005b343  lea     rdx, c_szSecurityPolicyDllPath; "DllPath"
0x18005b34a  call    cs:__imp_RegQueryValueExA
0x18005b350  test    eax, eax
0x18005b352  jnz     loc_18005B4D1
0x18005b358  lea     rcx, [rsp+500h+Data]; pszPath
0x18005b35d  call    cs:__imp_PathFindFileNameA
0x18005b363  lea     rcx, [rsp+500h+Data]
0x18005b368  mov     edi, 104h
0x18005b36d  cmp     rcx, rax
0x18005b370  jz      short loc_18005B3A1
0x18005b372  lea     r8, [rsp+500h+Data]; char *
0x18005b377  mov     edx, edi; unsigned __int64
0x18005b379  lea     rcx, [rbp+400h+pszPath]; char *
0x18005b380  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18005b385  lea     rcx, [rbp+400h+pszPath]; pszPath
0x18005b38c  call    cs:__imp_PathFindFileNameA
0x18005b392  mov     edx, edi; unsigned __int64
0x18005b394  lea     rcx, [rsp+500h+Data]; char *
0x18005b399  mov     r8, rax; char *
0x18005b39c  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18005b3a1  cmp     [rsp+500h+Type], 2
0x18005b3a6  mov     [rbp+400h+var_38D], bl
0x18005b3a9  jnz     short loc_18005B3EB
0x18005b3ab  mov     r8, rdi; Size
0x18005b3ae  lea     rcx, [rbp+400h+Dst]; void *
0x18005b3b5  xor     edx, edx; Val
0x18005b3b7  call    memset_0
0x18005b3bc  mov     r8d, edi; nSize
0x18005b3bf  lea     rdx, [rbp+400h+Dst]; lpDst
0x18005b3c6  lea     rcx, [rsp+500h+Data]; lpSrc
0x18005b3cb  call    cs:__imp_ExpandEnvironmentStringsA
0x18005b3d1  lea     r8, [rbp+400h+Dst]; char *
0x18005b3d8  mov     [rbp+400h+var_27D], bl
0x18005b3de  mov     rdx, rdi; unsigned __int64
0x18005b3e1  lea     rcx, [rsp+500h+Data]; char *
0x18005b3e6  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18005b3eb  xor     edx, edx; hFile
0x18005b3ed  lea     rcx, [rsp+500h+Data]; lpLibFileName
0x18005b3f2  lea     r8d, [rdx+8]; dwFlags
0x18005b3f6  call    cs:__imp_LoadLibraryExA
0x18005b3fc  mov     rdi, rax
0x18005b3ff  test    rax, rax
0x18005b402  jz      loc_18005B4D1
0x18005b408  mov     rcx, [rsp+500h+var_4B8]; hKey
0x18005b40d  lea     rax, [rsp+500h+cbData]
0x18005b412  mov     [rsp+500h+lpcbData], rax; lpcbData
0x18005b417  lea     r9, [rsp+500h+Type]; lpType
0x18005b41c  lea     rax, [rbp+400h+var_270]
0x18005b423  mov     [rsp+500h+cbData], 104h
0x18005b42b  xor     r8d, r8d; lpReserved
0x18005b42e  mov     [rsp+500h+phkResult], rax; lpData
0x18005b433  lea     rdx, c_szSecurityPolicyFuncName; "FuncName"
0x18005b43a  mov     [rbp+400h+var_16C], bl
0x18005b440  call    cs:__imp_RegQueryValueExA
0x18005b446  test    eax, eax
0x18005b448  jnz     loc_18005B4D1
0x18005b44e  lea     rdx, [rbp+400h+var_270]; lpProcName
0x18005b455  mov     rcx, rdi; hModule
0x18005b458  call    cs:__imp_GetProcAddress
0x18005b45e  mov     rbx, rax
0x18005b461  test    rax, rax
0x18005b464  jz      short loc_18005B4D1
0x18005b466  call    cs:__imp_GetACP
0x18005b46c  mov     rdx, [rsi]
0x18005b46f  lea     rcx, [rsp+500h+var_4A0]
0x18005b474  mov     [rsp+500h+phkResult], rcx
0x18005b479  lea     r9, IID_ISMimePolicyCheckAccess
0x18005b480  mov     r8d, eax
0x18005b483  xor     ecx, ecx
0x18005b485  mov     rax, rbx
0x18005b488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b48d  mov     ebx, eax
0x18005b48f  test    eax, eax
0x18005b491  js      short loc_18005B4D6
0x18005b493  mov     rcx, [rsp+500h+var_4A0]
0x18005b498  test    rcx, rcx
0x18005b49b  jz      short loc_18005B4CA
0x18005b49d  mov     rdx, [rsp+500h+var_498]
0x18005b4a2  mov     r9, rsi
0x18005b4a5  mov     rax, [rcx]
0x18005b4a8  mov     r8, r15
0x18005b4ab  mov     [rsp+500h+var_4D0], rdx
0x18005b4b0  mov     edx, r14d
0x18005b4b3  mov     [rsp+500h+lpcbData], r13
0x18005b4b8  mov     [rsp+500h+phkResult], r12
0x18005b4bd  mov     rax, [rax+18h]
0x18005b4c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b4c6  mov     ebx, eax
0x18005b4c8  jmp     short loc_18005B4D6
0x18005b4ca  mov     ebx, 80004005h
0x18005b4cf  jmp     short loc_18005B4D6
0x18005b4d1  mov     ebx, 800CCEF3h
0x18005b4d6  mov     rcx, [rsp+500h+var_4A0]
0x18005b4db  test    rcx, rcx
0x18005b4de  jz      short loc_18005B4EC
0x18005b4e0  mov     rax, [rcx]
0x18005b4e3  mov     rax, [rax+10h]
0x18005b4e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b4ec  test    rdi, rdi
0x18005b4ef  jz      short loc_18005B4FA
0x18005b4f1  mov     rcx, rdi; hLibModule
0x18005b4f4  call    cs:__imp_FreeLibrary
0x18005b4fa  mov     rcx, [rsp+500h+var_4B8]; hKey
0x18005b4ff  test    rcx, rcx
0x18005b502  jz      short loc_18005B50A
0x18005b504  call    cs:__imp_RegCloseKey
0x18005b50a  mov     rcx, [rsp+500h+hKey]; hKey
0x18005b50f  test    rcx, rcx
0x18005b512  jz      short loc_18005B51A
0x18005b514  call    cs:__imp_RegCloseKey
0x18005b51a  mov     eax, ebx
0x18005b51c  mov     rcx, [rbp+400h+var_50]
0x18005b523  xor     rcx, rsp; StackCookie
0x18005b526  call    __security_check_cookie
0x18005b52b  add     rsp, 4C8h
0x18005b532  pop     r15
0x18005b534  pop     r14
0x18005b536  pop     r13
0x18005b538  pop     r12
0x18005b53a  pop     rdi
0x18005b53b  pop     rsi
0x18005b53c  pop     rbx
0x18005b53d  pop     rbp
0x18005b53e  retn
```
