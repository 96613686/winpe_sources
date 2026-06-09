# DllRegisterServer

- ea: `0x1800052c0`
- end: `0x1800053cd`
- name: `DllRegisterServer`
- size: `269`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800052c0`
- `0x1800054ae`
- `0x1800054f0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800053a3`
- `KERNEL32!GetLastError` at `0x1800053a3`
- `KERNEL32!GetModuleFileNameW` at `0x180005303`
- `KERNEL32!GetModuleFileNameW` at `0x180005303`
- `CRYPT32!CryptSIPAddProvider` at `0x180005395`
- `CRYPT32!CryptSIPAddProvider` at `0x180005395`

## string_xrefs

- `0x18000535c`: `PsCreateHash`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  HRESULT result; // eax
  SIP_ADD_NEWPROVIDER psNewProv; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v2; // [rsp+78h] [rbp-88h]
  WCHAR Filename[264]; // [rsp+80h] [rbp-80h] BYREF

  memset_0(&psNewProv, 0, 0x60u);
  if ( GetModuleFileNameW((HMODULE)0x180000000LL, Filename, 0x104u) )
  {
    *(_QWORD *)&psNewProv.cbStruct = 96;
    v2 = 0;
    psNewProv.pwszMagicNumber = 0;
    psNewProv.pgSubject = (GUID *)&guidPsSip;
    psNewProv.pwszDLLFileName = Filename;
    psNewProv.pwszGetFuncName = L"PsGetSignature";
    psNewProv.pwszPutFuncName = L"PsPutSignature";
    psNewProv.pwszCreateFuncName = L"PsCreateHash";
    psNewProv.pwszVerifyFuncName = L"PsVerifyHash";
    psNewProv.pwszRemoveFuncName = L"PsDelSignature";
    psNewProv.pwszIsFunctionNameFmt2 = L"PsIsMyFileType";
    psNewProv.pwszIsFunctionName = 0;
    if ( CryptSIPAddProvider(&psNewProv) )
      return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800052c0  push    rbp
0x1800052c2  lea     rbp, [rsp-1A0h]
0x1800052ca  sub     rsp, 2A0h
0x1800052d1  mov     rax, cs:__security_cookie
0x1800052d8  xor     rax, rsp
0x1800052db  mov     [rbp+1A0h+var_10], rax
0x1800052e2  xor     edx, edx; Val
0x1800052e4  lea     rcx, [rsp+2A0h+psNewProv]; void *
0x1800052e9  lea     r8d, [rdx+60h]; Size
0x1800052ed  call    memset_0
0x1800052f2  mov     r8d, 104h; nSize
0x1800052f8  lea     rdx, [rbp+1A0h+Filename]; lpFilename
0x1800052fc  lea     rcx, cs:180000000h; hModule
0x180005303  call    cs:__imp_GetModuleFileNameW
0x180005309  test    eax, eax
0x18000530b  jz      loc_1800053A3
0x180005311  xor     eax, eax
0x180005313  mov     qword ptr [rsp+2A0h+psNewProv.cbStruct], 60h ; '`'
0x18000531c  mov     [rsp+2A0h+var_228], rax
0x180005321  lea     rcx, [rsp+2A0h+psNewProv]; psNewProv
0x180005326  lea     rax, guidPsSip
0x18000532d  mov     [rsp+2A0h+psNewProv.pwszMagicNumber], 0
0x180005336  mov     [rsp+2A0h+psNewProv.pgSubject], rax
0x18000533b  lea     rax, [rbp+1A0h+Filename]
0x18000533f  mov     [rsp+2A0h+psNewProv.pwszDLLFileName], rax
0x180005344  lea     rax, aPsgetsignature_0; "PsGetSignature"
0x18000534b  mov     [rsp+2A0h+psNewProv.pwszGetFuncName], rax
0x180005350  lea     rax, aPsputsignature_0; "PsPutSignature"
0x180005357  mov     [rsp+2A0h+psNewProv.pwszPutFuncName], rax
0x18000535c  lea     rax, aPscreatehash_0; "PsCreateHash"
0x180005363  mov     [rsp+2A0h+psNewProv.pwszCreateFuncName], rax
0x180005368  lea     rax, aPsverifyhash_0; "PsVerifyHash"
0x18000536f  mov     [rsp+2A0h+psNewProv.pwszVerifyFuncName], rax
0x180005374  lea     rax, aPsdelsignature_0; "PsDelSignature"
0x18000537b  mov     [rsp+2A0h+psNewProv.pwszRemoveFuncName], rax
0x180005380  lea     rax, aPsismyfiletype_0; "PsIsMyFileType"
0x180005387  mov     [rsp+2A0h+psNewProv.pwszIsFunctionNameFmt2], rax
0x18000538c  mov     [rsp+2A0h+psNewProv.pwszIsFunctionName], 0
0x180005395  call    cs:__imp_CryptSIPAddProvider
0x18000539b  test    eax, eax
0x18000539d  jz      short loc_1800053A3
0x18000539f  xor     eax, eax
0x1800053a1  jmp     short loc_1800053B5
0x1800053a3  call    cs:__imp_GetLastError
0x1800053a9  test    eax, eax
0x1800053ab  jle     short loc_1800053B5
0x1800053ad  movzx   eax, ax
0x1800053b0  or      eax, 80070000h
0x1800053b5  mov     rcx, [rbp+1A0h+var_10]
0x1800053bc  xor     rcx, rsp; StackCookie
0x1800053bf  call    __security_check_cookie
0x1800053c4  add     rsp, 2A0h
0x1800053cb  pop     rbp
0x1800053cc  retn
```
