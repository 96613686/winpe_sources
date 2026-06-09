# RPORDllRegisterServer

- ea: `0x18001fcac`
- end: `0x18001fe25`
- name: `RPORDllRegisterServer`
- size: `377`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001fbc0`

## callees

- `0x18001fcac`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fcdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fdc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fdd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fdff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fcdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fdc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fdd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fdff`
- `CRYPT32!CryptRegisterOIDFunction` at `0x18001fdbc`
- `CRYPT32!CryptRegisterOIDFunction` at `0x18001fdf5`
- `CRYPT32!CryptRegisterOIDFunction` at `0x18001fdbc`
- `CRYPT32!CryptRegisterOIDFunction` at `0x18001fdf5`
- `CRYPT32!CryptRegisterDefaultOIDFunction` at `0x18001fd50`
- `CRYPT32!CryptRegisterDefaultOIDFunction` at `0x18001fd7f`
- `CRYPT32!CryptRegisterDefaultOIDFunction` at `0x18001fd50`
- `CRYPT32!CryptRegisterDefaultOIDFunction` at `0x18001fd7f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001fd30`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001fd30`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x18001fcd2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x18001fcd2`
- `ntdll!strrchr` at `0x18001fd09`
- `ntdll!strrchr` at `0x18001fd09`

## string_xrefs

- `0x18001fd45`: `CertDllVerifyRevocation`
- `0x18001fd74`: `CertDllVerifyCTLUsage`
- `0x18001fd98`: `LdapProvOpenStore`
- `0x18001fdb5`: `CertDllOpenStoreProv`
- `0x18001fdec`: `CertDllOpenStoreProv`

## pseudocode

```c
signed int __fastcall RPORDllRegisterServer(HMODULE a1)
{
  signed int result; // eax
  char *v2; // rax
  CHAR Filename[272]; // [rsp+30h] [rbp-338h] BYREF
  WCHAR WideCharStr[264]; // [rsp+140h] [rbp-228h] BYREF

  if ( GetModuleFileNameA(a1, Filename, 0x104u)
    && (Filename[260] = 0, v2 = strrchr(Filename, 92), MultiByteToWideChar(0, 0, v2 + 1, -1, WideCharStr, 261))
    && (CryptRegisterDefaultOIDFunction(1u, "CertDllVerifyRevocation", 0, WideCharStr) || GetLastError() == 80)
    && (CryptRegisterDefaultOIDFunction(1u, "CertDllVerifyCTLUsage", 0, WideCharStr) || GetLastError() == 80) )
  {
    if ( (CryptRegisterOIDFunction(0, "CertDllOpenStoreProv", "Ldap", WideCharStr, "LdapProvOpenStore")
       || GetLastError() == 80)
      && (CryptRegisterOIDFunction(0, "CertDllOpenStoreProv", (LPCSTR)0x10, WideCharStr, "LdapProvOpenStore")
       || GetLastError() == 80) )
    {
      return 0;
    }
    else
    {
      return GetLastError();
    }
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18001fcac  push    rbx
0x18001fcae  sub     rsp, 360h
0x18001fcb5  mov     rax, cs:__security_cookie
0x18001fcbc  xor     rax, rsp
0x18001fcbf  mov     [rsp+368h+var_18], rax
0x18001fcc7  mov     r8d, 104h; nSize
0x18001fccd  lea     rdx, [rsp+368h+Filename]; lpFilename
0x18001fcd2  call    cs:__imp_GetModuleFileNameA
0x18001fcd8  test    eax, eax
0x18001fcda  jnz     short loc_18001FCF7
0x18001fcdc  call    cs:__imp_GetLastError
0x18001fce2  test    eax, eax
0x18001fce4  jle     loc_18001FE0C
0x18001fcea  movzx   eax, ax
0x18001fced  or      eax, 80070000h
0x18001fcf2  jmp     loc_18001FE0C
0x18001fcf7  mov     edx, 5Ch ; '\'; Ch
0x18001fcfc  mov     [rsp+368h+var_234], 0
0x18001fd04  lea     rcx, [rsp+368h+Filename]; Str
0x18001fd09  call    cs:__imp_strrchr
0x18001fd0f  lea     rcx, [rsp+368h+WideCharStr]
0x18001fd17  mov     [rsp+368h+cchWideChar], 105h; cchWideChar
0x18001fd1f  mov     [rsp+368h+lpWideCharStr], rcx; lpWideCharStr
0x18001fd24  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18001fd28  xor     edx, edx; dwFlags
0x18001fd2a  xor     ecx, ecx; CodePage
0x18001fd2c  lea     r8, [rax+1]; lpMultiByteStr
0x18001fd30  call    cs:__imp_MultiByteToWideChar
0x18001fd36  test    eax, eax
0x18001fd38  jz      short loc_18001FCDC
0x18001fd3a  xor     r8d, r8d; dwIndex
0x18001fd3d  lea     r9, [rsp+368h+WideCharStr]; pwszDll
0x18001fd45  lea     rdx, aCertdllverifyr_0; "CertDllVerifyRevocation"
0x18001fd4c  lea     ecx, [r8+1]; dwEncodingType
0x18001fd50  call    cs:__imp_CryptRegisterDefaultOIDFunction
0x18001fd56  test    eax, eax
0x18001fd58  jnz     short loc_18001FD69
0x18001fd5a  call    cs:__imp_GetLastError
0x18001fd60  cmp     eax, 50h ; 'P'
0x18001fd63  jnz     loc_18001FCDC
0x18001fd69  xor     r8d, r8d; dwIndex
0x18001fd6c  lea     r9, [rsp+368h+WideCharStr]; pwszDll
0x18001fd74  lea     rdx, aCertdllverifyc_0; "CertDllVerifyCTLUsage"
0x18001fd7b  lea     ecx, [r8+1]; dwEncodingType
0x18001fd7f  call    cs:__imp_CryptRegisterDefaultOIDFunction
0x18001fd85  test    eax, eax
0x18001fd87  jnz     short loc_18001FD98
0x18001fd89  call    cs:__imp_GetLastError
0x18001fd8f  cmp     eax, 50h ; 'P'
0x18001fd92  jnz     loc_18001FCDC
0x18001fd98  lea     rbx, pszOverrideFuncName; "LdapProvOpenStore"
0x18001fd9f  xor     ecx, ecx; dwEncodingType
0x18001fda1  lea     r9, [rsp+368h+WideCharStr]; pwszDll
0x18001fda9  mov     [rsp+368h+lpWideCharStr], rbx; pszOverrideFuncName
0x18001fdae  lea     r8, pszOID; "Ldap"
0x18001fdb5  lea     rdx, aCertdllopensto; "CertDllOpenStoreProv"
0x18001fdbc  call    cs:__imp_CryptRegisterOIDFunction
0x18001fdc2  test    eax, eax
0x18001fdc4  jnz     short loc_18001FDD9
0x18001fdc6  call    cs:__imp_GetLastError
0x18001fdcc  cmp     eax, 50h ; 'P'
0x18001fdcf  jz      short loc_18001FDD9
0x18001fdd1  call    cs:__imp_GetLastError
0x18001fdd7  jmp     short loc_18001FE0C
0x18001fdd9  lea     r9, [rsp+368h+WideCharStr]; pwszDll
0x18001fde1  mov     [rsp+368h+lpWideCharStr], rbx; pszOverrideFuncName
0x18001fde6  mov     r8d, 10h; pszOID
0x18001fdec  lea     rdx, aCertdllopensto; "CertDllOpenStoreProv"
0x18001fdf3  xor     ecx, ecx; dwEncodingType
0x18001fdf5  call    cs:__imp_CryptRegisterOIDFunction
0x18001fdfb  test    eax, eax
0x18001fdfd  jnz     short loc_18001FE0A
0x18001fdff  call    cs:__imp_GetLastError
0x18001fe05  cmp     eax, 50h ; 'P'
0x18001fe08  jnz     short loc_18001FDD1
0x18001fe0a  xor     eax, eax
0x18001fe0c  mov     rcx, [rsp+368h+var_18]
0x18001fe14  xor     rcx, rsp; StackCookie
0x18001fe17  call    __security_check_cookie
0x18001fe1c  add     rsp, 360h
0x18001fe23  pop     rbx
0x18001fe24  retn
```
