# RPORDllUnregisterServer

- ea: `0x18001fe2c`
- end: `0x18001ff7d`
- name: `RPORDllUnregisterServer`
- size: `337`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001fbc0`

## callees

- `0x18001fe2c`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fed6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fed6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff58`
- `CRYPT32!CryptUnregisterOIDFunction` at `0x18001ff22`
- `CRYPT32!CryptUnregisterOIDFunction` at `0x18001ff4e`
- `CRYPT32!CryptUnregisterOIDFunction` at `0x18001ff22`
- `CRYPT32!CryptUnregisterOIDFunction` at `0x18001ff4e`
- `CRYPT32!CryptUnregisterDefaultOIDFunction` at `0x18001fecc`
- `CRYPT32!CryptUnregisterDefaultOIDFunction` at `0x18001fef9`
- `CRYPT32!CryptUnregisterDefaultOIDFunction` at `0x18001fecc`
- `CRYPT32!CryptUnregisterDefaultOIDFunction` at `0x18001fef9`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001feae`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001feae`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x18001fe50`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x18001fe50`
- `ntdll!strrchr` at `0x18001fe87`
- `ntdll!strrchr` at `0x18001fe87`

## string_xrefs

- `0x18001fec5`: `CertDllVerifyRevocation`
- `0x18001fef2`: `CertDllVerifyCTLUsage`
- `0x18001ff1b`: `CertDllOpenStoreProv`
- `0x18001ff45`: `CertDllOpenStoreProv`

## pseudocode

```c
signed int __fastcall RPORDllUnregisterServer(HMODULE a1)
{
  signed int result; // eax
  char *v2; // rax
  CHAR Filename[272]; // [rsp+30h] [rbp-338h] BYREF
  WCHAR WideCharStr[264]; // [rsp+140h] [rbp-228h] BYREF

  if ( GetModuleFileNameA(a1, Filename, 0x104u)
    && (Filename[260] = 0, v2 = strrchr(Filename, 92), MultiByteToWideChar(0, 0, v2 + 1, -1, WideCharStr, 261))
    && (CryptUnregisterDefaultOIDFunction(1u, "CertDllVerifyRevocation", WideCharStr) || GetLastError() == 2)
    && (CryptUnregisterDefaultOIDFunction(1u, "CertDllVerifyCTLUsage", WideCharStr) || GetLastError() == 2) )
  {
    if ( (CryptUnregisterOIDFunction(0, "CertDllOpenStoreProv", "Ldap") || GetLastError() == 2)
      && (CryptUnregisterOIDFunction(0, "CertDllOpenStoreProv", (LPCSTR)0x10) || GetLastError() == 2) )
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
0x18001fe2c  sub     rsp, 368h
0x18001fe33  mov     rax, cs:__security_cookie
0x18001fe3a  xor     rax, rsp
0x18001fe3d  mov     [rsp+368h+var_18], rax
0x18001fe45  mov     r8d, 104h; nSize
0x18001fe4b  lea     rdx, [rsp+368h+Filename]; lpFilename
0x18001fe50  call    cs:__imp_GetModuleFileNameA
0x18001fe56  test    eax, eax
0x18001fe58  jnz     short loc_18001FE75
0x18001fe5a  call    cs:__imp_GetLastError
0x18001fe60  test    eax, eax
0x18001fe62  jle     loc_18001FF65
0x18001fe68  movzx   eax, ax
0x18001fe6b  or      eax, 80070000h
0x18001fe70  jmp     loc_18001FF65
0x18001fe75  mov     edx, 5Ch ; '\'; Ch
0x18001fe7a  mov     [rsp+368h+var_234], 0
0x18001fe82  lea     rcx, [rsp+368h+Filename]; Str
0x18001fe87  call    cs:__imp_strrchr
0x18001fe8d  lea     rcx, [rsp+368h+WideCharStr]
0x18001fe95  mov     [rsp+368h+cchWideChar], 105h; cchWideChar
0x18001fe9d  mov     [rsp+368h+lpWideCharStr], rcx; lpWideCharStr
0x18001fea2  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18001fea6  xor     edx, edx; dwFlags
0x18001fea8  xor     ecx, ecx; CodePage
0x18001feaa  lea     r8, [rax+1]; lpMultiByteStr
0x18001feae  call    cs:__imp_MultiByteToWideChar
0x18001feb4  test    eax, eax
0x18001feb6  jz      short loc_18001FE5A
0x18001feb8  lea     r8, [rsp+368h+WideCharStr]; pwszDll
0x18001fec0  mov     ecx, 1; dwEncodingType
0x18001fec5  lea     rdx, aCertdllverifyr_0; "CertDllVerifyRevocation"
0x18001fecc  call    cs:__imp_CryptUnregisterDefaultOIDFunction
0x18001fed2  test    eax, eax
0x18001fed4  jnz     short loc_18001FEE5
0x18001fed6  call    cs:__imp_GetLastError
0x18001fedc  cmp     eax, 2
0x18001fedf  jnz     loc_18001FE5A
0x18001fee5  lea     r8, [rsp+368h+WideCharStr]; pwszDll
0x18001feed  mov     ecx, 1; dwEncodingType
0x18001fef2  lea     rdx, aCertdllverifyc_0; "CertDllVerifyCTLUsage"
0x18001fef9  call    cs:__imp_CryptUnregisterDefaultOIDFunction
0x18001feff  test    eax, eax
0x18001ff01  jnz     short loc_18001FF12
0x18001ff03  call    cs:__imp_GetLastError
0x18001ff09  cmp     eax, 2
0x18001ff0c  jnz     loc_18001FE5A
0x18001ff12  lea     r8, pszOID; "Ldap"
0x18001ff19  xor     ecx, ecx; dwEncodingType
0x18001ff1b  lea     rdx, aCertdllopensto; "CertDllOpenStoreProv"
0x18001ff22  call    cs:__imp_CryptUnregisterOIDFunction
0x18001ff28  test    eax, eax
0x18001ff2a  jnz     short loc_18001FF3F
0x18001ff2c  call    cs:__imp_GetLastError
0x18001ff32  cmp     eax, 2
0x18001ff35  jz      short loc_18001FF3F
0x18001ff37  call    cs:__imp_GetLastError
0x18001ff3d  jmp     short loc_18001FF65
0x18001ff3f  mov     r8d, 10h; pszOID
0x18001ff45  lea     rdx, aCertdllopensto; "CertDllOpenStoreProv"
0x18001ff4c  xor     ecx, ecx; dwEncodingType
0x18001ff4e  call    cs:__imp_CryptUnregisterOIDFunction
0x18001ff54  test    eax, eax
0x18001ff56  jnz     short loc_18001FF63
0x18001ff58  call    cs:__imp_GetLastError
0x18001ff5e  cmp     eax, 2
0x18001ff61  jnz     short loc_18001FF37
0x18001ff63  xor     eax, eax
0x18001ff65  mov     rcx, [rsp+368h+var_18]
0x18001ff6d  xor     rcx, rsp; StackCookie
0x18001ff70  call    __security_check_cookie
0x18001ff75  add     rsp, 368h
0x18001ff7c  retn
```
