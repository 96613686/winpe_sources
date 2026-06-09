# _bidLdrReadProfile

- ea: `0x1800c7f40`
- end: `0x1800c8261`
- name: `_bidLdrReadProfile`
- size: `801`
- prototype: `__int64 __fastcall(LPCWSTR lpRootPathName)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c87ec`

## callees

- `0x180063ed8`
- `0x1800c5a3c`
- `0x1800c7e00`
- `0x1800c7f40`
- `0x1800c8268`
- `0x1800cdb20`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800c7fe2`
- `msvcrt!wcsncpy_s` at `0x1800c813c`
- `msvcrt!wcsncpy_s` at `0x1800c7fe2`
- `msvcrt!wcsncpy_s` at `0x1800c813c`
- `KERNEL32!OutputDebugStringW` at `0x1800c81b2`
- `KERNEL32!OutputDebugStringW` at `0x1800c81c3`
- `KERNEL32!OutputDebugStringW` at `0x1800c81d6`
- `KERNEL32!OutputDebugStringW` at `0x1800c81e7`
- `KERNEL32!OutputDebugStringW` at `0x1800c81fa`
- `KERNEL32!OutputDebugStringW` at `0x1800c8209`
- `KERNEL32!OutputDebugStringW` at `0x1800c821c`
- `KERNEL32!OutputDebugStringW` at `0x1800c81b2`
- `KERNEL32!OutputDebugStringW` at `0x1800c81c3`
- `KERNEL32!OutputDebugStringW` at `0x1800c81d6`
- `KERNEL32!OutputDebugStringW` at `0x1800c81e7`
- `KERNEL32!OutputDebugStringW` at `0x1800c81fa`
- `KERNEL32!OutputDebugStringW` at `0x1800c8209`
- `KERNEL32!OutputDebugStringW` at `0x1800c821c`
- `ADVAPI32!RegCloseKey` at `0x1800c814d`
- `ADVAPI32!RegCloseKey` at `0x1800c8172`
- `ADVAPI32!RegCloseKey` at `0x1800c814d`
- `ADVAPI32!RegCloseKey` at `0x1800c8172`
- `ADVAPI32!RegQueryValueExW` at `0x1800c8040`
- `ADVAPI32!RegQueryValueExW` at `0x1800c8040`
- `ADVAPI32!RegOpenKeyExW` at `0x1800c7fc3`
- `ADVAPI32!RegOpenKeyExW` at `0x1800c7fc3`

## string_xrefs

- `0x1800c8109`: `:Path`

## pseudocode

```c
__int64 __fastcall bidLdrReadProfile(wchar_t *lpRootPathName, __int64 a2, __int64 a3, _DWORD *a4)
{
  int IsPathLocal; // eax
  int v7; // ecx
  unsigned int v8; // edi
  __int64 v9; // rax
  unsigned __int64 v10; // rcx
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpOutputString; // [rsp+40h] [rbp-C0h]
  LPCWSTR v16; // [rsp+48h] [rbp-B8h]
  wchar_t *v17; // [rsp+50h] [rbp-B0h]
  __int64 v18; // [rsp+58h] [rbp-A8h]
  __int64 v19; // [rsp+60h] [rbp-A0h]
  DWORD cbData; // [rsp+68h] [rbp-98h] BYREF
  __int64 v21; // [rsp+70h] [rbp-90h]
  __int64 v22; // [rsp+78h] [rbp-88h]
  WCHAR Filename[280]; // [rsp+80h] [rbp-80h] BYREF

  v17 = lpRootPathName;
  *lpRootPathName = 0;
  v19 = 0;
  hKey = 0;
  v18 = 538;
  lpOutputString = L"SOFTWARE\\Microsoft\\BidInterface\\Loader";
  v16 = L"<NotFound>";
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\BidInterface\\Loader", 0, 0x20019u, &hKey) )
  {
    wcsncpy_s(lpRootPathName, 0x10Du, L"<NotFound>", 0xFFFFFFFFFFFFFFFFuLL);
    IsPathLocal = 0;
    v7 = 0;
    v8 = 0;
    goto LABEL_21;
  }
  v22 = 0;
  v21 = 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  Type = 0;
  v8 = 1;
  if ( RegQueryValueExW(hKey, L":LdrMsg", 0, &Type, Data, &cbData) || Type != 4 || (LODWORD(v19) = 1, !*(_DWORD *)Data) )
    LODWORD(v19) = 0;
  if ( !(unsigned int)BuildApplicationPid(Filename) )
    goto LABEL_14;
  v16 = Filename;
  if ( (unsigned int)bidLdrReadStr(&hKey) )
    goto LABEL_17;
  if ( (unsigned __int64)(2 * v21) >= 0x224 )
    goto LABEL_16;
  Filename[v21] = 0;
  if ( (unsigned int)bidLdrReadStr(&hKey) )
    goto LABEL_17;
  v9 = v22;
  if ( !v22 )
    goto LABEL_14;
  Filename[v22] = 42;
  v10 = 2 * v9 + 2;
  if ( v10 >= 0x224 )
LABEL_16:
    _report_rangecheckfailure();
  *(WCHAR *)((char *)Filename + v10) = 0;
  if ( (unsigned int)bidLdrReadStr(&hKey) )
    goto LABEL_17;
LABEL_14:
  v16 = L":Path";
  if ( (unsigned int)bidLdrReadStr(&hKey) )
  {
LABEL_17:
    RegCloseKey(hKey);
    IsPathLocal = HIDWORD(v18);
    hKey = 0;
    lpRootPathName[269] = 0;
    if ( IsPathLocal )
    {
      IsPathLocal = bidLdrIsPathLocal(lpRootPathName);
      HIDWORD(v18) = IsPathLocal;
    }
    goto LABEL_19;
  }
  v16 = L"<NotFound>";
  HIDWORD(v18) = 0;
  wcsncpy_s(lpRootPathName, 0x10Du, L"<NotFound>", 0xFFFFFFFFFFFFFFFFuLL);
  RegCloseKey(hKey);
  IsPathLocal = HIDWORD(v18);
  v8 = 0;
  hKey = 0;
LABEL_19:
  v7 = v19;
  if ( (_DWORD)v19 )
  {
    OutputDebugStringW(L"*** [HKLM\\");
    OutputDebugStringW(lpOutputString);
    OutputDebugStringW(L"\\\"");
    OutputDebugStringW(v16);
    OutputDebugStringW(L"\"] \n*** \"");
    OutputDebugStringW(lpRootPathName);
    OutputDebugStringW(L"\"\n");
    v7 = v19;
    IsPathLocal = HIDWORD(v18);
  }
LABEL_21:
  *a4 = v7;
  dword_180122C38 = IsPathLocal;
  return v8;
}

```

## disassembly

```asm
0x1800c7f40  mov     [rsp-8+arg_8], rbx
0x1800c7f45  push    rbp
0x1800c7f46  push    rsi
0x1800c7f47  push    rdi
0x1800c7f48  push    r12
0x1800c7f4a  push    r14
0x1800c7f4c  lea     rbp, [rsp-1C0h]
0x1800c7f54  sub     rsp, 2C0h
0x1800c7f5b  mov     rax, cs:__security_cookie
0x1800c7f62  xor     rax, rsp
0x1800c7f65  mov     [rbp+1E0h+var_30], rax
0x1800c7f6c  xor     r14d, r14d
0x1800c7f6f  mov     [rsp+2E0h+var_290], rcx
0x1800c7f74  mov     [rcx], r14w
0x1800c7f78  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\BidInterface\\Load"...
0x1800c7f7f  mov     rsi, r9
0x1800c7f82  mov     [rsp+2E0h+var_280], r14
0x1800c7f87  mov     rbx, rcx
0x1800c7f8a  mov     [rsp+2E0h+hKey], r14
0x1800c7f8f  lea     rax, [rsp+2E0h+hKey]
0x1800c7f94  mov     [rsp+2E0h+var_288], 21Ah
0x1800c7f9d  lea     r12, aNotfound; "<NotFound>"
0x1800c7fa4  mov     [rsp+2E0h+lpOutputString], rdx
0x1800c7fa9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c7fb0  mov     [rsp+2E0h+var_298], r12
0x1800c7fb5  mov     r9d, 20019h; samDesired
0x1800c7fbb  mov     [rsp+2E0h+phkResult], rax; phkResult
0x1800c7fc0  xor     r8d, r8d; ulOptions
0x1800c7fc3  call    cs:__imp_RegOpenKeyExW
0x1800c7fca  nop     dword ptr [rax+rax+00h]
0x1800c7fcf  test    eax, eax
0x1800c7fd1  jz      short loc_1800C7FFC
0x1800c7fd3  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800c7fd7  mov     r8, r12; Source
0x1800c7fda  mov     edx, 10Dh; SizeInWords
0x1800c7fdf  mov     rcx, rbx; Destination
0x1800c7fe2  call    cs:__imp_wcsncpy_s
0x1800c7fe9  nop     dword ptr [rax+rax+00h]
0x1800c7fee  mov     eax, r14d
0x1800c7ff1  mov     ecx, r14d
0x1800c7ff4  mov     edi, r14d
0x1800c7ff7  jmp     loc_1800C8230
0x1800c7ffc  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1800c8001  lea     rax, [rsp+2E0h+cbData]
0x1800c8006  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x1800c800b  lea     r9, [rsp+2E0h+Type]; lpType
0x1800c8010  lea     rax, [rsp+2E0h+Data]
0x1800c8015  mov     [rsp+2E0h+var_268], r14
0x1800c801a  xor     r8d, r8d; lpReserved
0x1800c801d  mov     [rsp+2E0h+phkResult], rax; lpData
0x1800c8022  lea     rdx, ValueName; ":LdrMsg"
0x1800c8029  mov     [rsp+2E0h+var_270], r14
0x1800c802e  mov     dword ptr [rsp+2E0h+Data], r14d
0x1800c8033  mov     [rsp+2E0h+cbData], 4
0x1800c803b  mov     [rsp+2E0h+Type], r14d
0x1800c8040  call    cs:__imp_RegQueryValueExW
0x1800c8047  nop     dword ptr [rax+rax+00h]
0x1800c804c  mov     edi, 1
0x1800c8051  test    eax, eax
0x1800c8053  jnz     short loc_1800C8067
0x1800c8055  cmp     [rsp+2E0h+Type], 4
0x1800c805a  jnz     short loc_1800C8067
0x1800c805c  mov     dword ptr [rsp+2E0h+var_280], edi
0x1800c8060  cmp     dword ptr [rsp+2E0h+Data], r14d
0x1800c8065  jnz     short loc_1800C806C
0x1800c8067  mov     dword ptr [rsp+2E0h+var_280], r14d
0x1800c806c  lea     r9, [rsp+2E0h+var_270]
0x1800c8071  lea     r8, [rsp+2E0h+var_268]
0x1800c8076  lea     rcx, [rbp+1E0h+Filename]; lpFilename
0x1800c807a  call    BuildApplicationPid
0x1800c807f  test    eax, eax
0x1800c8081  jz      loc_1800C8109
0x1800c8087  lea     rax, [rbp+1E0h+Filename]
0x1800c808b  lea     rcx, [rsp+2E0h+hKey]
0x1800c8090  mov     [rsp+2E0h+var_298], rax
0x1800c8095  call    _bidLdrReadStr
0x1800c809a  test    eax, eax
0x1800c809c  jnz     loc_1800C816D
0x1800c80a2  mov     rax, [rsp+2E0h+var_270]
0x1800c80a7  lea     rcx, [rax+rax]
0x1800c80ab  cmp     rcx, 224h
0x1800c80b2  jnb     loc_1800C8167
0x1800c80b8  mov     [rbp+rcx+1E0h+Filename], r14w
0x1800c80be  lea     rcx, [rsp+2E0h+hKey]
0x1800c80c3  call    _bidLdrReadStr
0x1800c80c8  test    eax, eax
0x1800c80ca  jnz     loc_1800C816D
0x1800c80d0  mov     rax, [rsp+2E0h+var_268]
0x1800c80d5  test    rax, rax
0x1800c80d8  jz      short loc_1800C8109
0x1800c80da  mov     ecx, 2Ah ; '*'
0x1800c80df  mov     [rbp+rax*2+1E0h+Filename], cx
0x1800c80e4  lea     rcx, ds:2[rax*2]
0x1800c80ec  cmp     rcx, 224h
0x1800c80f3  jnb     short loc_1800C8167
0x1800c80f5  mov     [rbp+rcx+1E0h+Filename], r14w
0x1800c80fb  lea     rcx, [rsp+2E0h+hKey]
0x1800c8100  call    _bidLdrReadStr
0x1800c8105  test    eax, eax
0x1800c8107  jnz     short loc_1800C816D
0x1800c8109  lea     rax, aPath; ":Path"
0x1800c8110  lea     rcx, [rsp+2E0h+hKey]
0x1800c8115  mov     [rsp+2E0h+var_298], rax
0x1800c811a  call    _bidLdrReadStr
0x1800c811f  test    eax, eax
0x1800c8121  jnz     short loc_1800C816D
0x1800c8123  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800c8127  mov     [rsp+2E0h+var_298], r12
0x1800c812c  mov     r8, r12; Source
0x1800c812f  mov     dword ptr [rsp+2E0h+var_288+4], r14d
0x1800c8134  mov     edx, 10Dh; SizeInWords
0x1800c8139  mov     rcx, rbx; Destination
0x1800c813c  call    cs:__imp_wcsncpy_s
0x1800c8143  nop     dword ptr [rax+rax+00h]
0x1800c8148  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1800c814d  call    cs:__imp_RegCloseKey
0x1800c8154  nop     dword ptr [rax+rax+00h]
0x1800c8159  mov     eax, dword ptr [rsp+2E0h+var_288+4]
0x1800c815d  mov     edi, r14d
0x1800c8160  mov     [rsp+2E0h+hKey], r14
0x1800c8165  jmp     short loc_1800C819F
0x1800c8167  call    __report_rangecheckfailure
0x1800c816d  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1800c8172  call    cs:__imp_RegCloseKey
0x1800c8179  nop     dword ptr [rax+rax+00h]
0x1800c817e  mov     eax, dword ptr [rsp+2E0h+var_288+4]
0x1800c8182  mov     [rsp+2E0h+hKey], r14
0x1800c8187  mov     [rbx+21Ah], r14w
0x1800c818f  test    eax, eax
0x1800c8191  jz      short loc_1800C819F
0x1800c8193  mov     rcx, rbx; lpRootPathName
0x1800c8196  call    _bidLdrIsPathLocal
0x1800c819b  mov     dword ptr [rsp+2E0h+var_288+4], eax
0x1800c819f  mov     ecx, dword ptr [rsp+2E0h+var_280]
0x1800c81a3  test    ecx, ecx
0x1800c81a5  jz      loc_1800C8230
0x1800c81ab  lea     rcx, OutputString; "*** [HKLM\\"
0x1800c81b2  call    cs:__imp_OutputDebugStringW
0x1800c81b9  nop     dword ptr [rax+rax+00h]
0x1800c81be  mov     rcx, [rsp+2E0h+lpOutputString]; lpOutputString
0x1800c81c3  call    cs:__imp_OutputDebugStringW
0x1800c81ca  nop     dword ptr [rax+rax+00h]
0x1800c81cf  lea     rcx, asc_1801101F8; "\\\""
0x1800c81d6  call    cs:__imp_OutputDebugStringW
0x1800c81dd  nop     dword ptr [rax+rax+00h]
0x1800c81e2  mov     rcx, [rsp+2E0h+var_298]; lpOutputString
0x1800c81e7  call    cs:__imp_OutputDebugStringW
0x1800c81ee  nop     dword ptr [rax+rax+00h]
0x1800c81f3  lea     rcx, asc_180110200; "\"] \n*** \""
0x1800c81fa  call    cs:__imp_OutputDebugStringW
0x1800c8201  nop     dword ptr [rax+rax+00h]
0x1800c8206  mov     rcx, rbx; lpOutputString
0x1800c8209  call    cs:__imp_OutputDebugStringW
0x1800c8210  nop     dword ptr [rax+rax+00h]
0x1800c8215  lea     rcx, asc_180110214; "\"\n"
0x1800c821c  call    cs:__imp_OutputDebugStringW
0x1800c8223  nop     dword ptr [rax+rax+00h]
0x1800c8228  mov     ecx, dword ptr [rsp+2E0h+var_280]
0x1800c822c  mov     eax, dword ptr [rsp+2E0h+var_288+4]
0x1800c8230  mov     [rsi], ecx
0x1800c8232  mov     cs:dword_180122C38, eax
0x1800c8238  mov     eax, edi
0x1800c823a  mov     rcx, [rbp+1E0h+var_30]
0x1800c8241  xor     rcx, rsp; StackCookie
0x1800c8244  call    __security_check_cookie
0x1800c8249  mov     rbx, [rsp+2E0h+arg_8]
0x1800c8251  add     rsp, 2C0h
0x1800c8258  pop     r14
0x1800c825a  pop     r12
0x1800c825c  pop     rdi
0x1800c825d  pop     rsi
0x1800c825e  pop     rbp
0x1800c825f  retn
```
