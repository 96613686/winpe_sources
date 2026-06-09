# _bidLdrReadProfile

- ea: `0x18001a0fc`
- end: `0x18001a41d`
- name: `_bidLdrReadProfile`
- size: `801`
- prototype: `__int64 __fastcall(LPCWSTR lpRootPathName)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a9ac`

## callees

- `0x180001858`
- `0x1800194ec`
- `0x180019fbc`
- `0x18001a0fc`
- `0x18001a424`
- `0x18002f0e0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18001a19e`
- `msvcrt!wcsncpy_s` at `0x18001a2f8`
- `msvcrt!wcsncpy_s` at `0x18001a19e`
- `msvcrt!wcsncpy_s` at `0x18001a2f8`
- `KERNEL32!OutputDebugStringW` at `0x18001a36e`
- `KERNEL32!OutputDebugStringW` at `0x18001a37f`
- `KERNEL32!OutputDebugStringW` at `0x18001a392`
- `KERNEL32!OutputDebugStringW` at `0x18001a3a3`
- `KERNEL32!OutputDebugStringW` at `0x18001a3b6`
- `KERNEL32!OutputDebugStringW` at `0x18001a3c5`
- `KERNEL32!OutputDebugStringW` at `0x18001a3d8`
- `KERNEL32!OutputDebugStringW` at `0x18001a36e`
- `KERNEL32!OutputDebugStringW` at `0x18001a37f`
- `KERNEL32!OutputDebugStringW` at `0x18001a392`
- `KERNEL32!OutputDebugStringW` at `0x18001a3a3`
- `KERNEL32!OutputDebugStringW` at `0x18001a3b6`
- `KERNEL32!OutputDebugStringW` at `0x18001a3c5`
- `KERNEL32!OutputDebugStringW` at `0x18001a3d8`
- `ADVAPI32!RegOpenKeyExW` at `0x18001a17f`
- `ADVAPI32!RegOpenKeyExW` at `0x18001a17f`
- `ADVAPI32!RegQueryValueExW` at `0x18001a1fc`
- `ADVAPI32!RegQueryValueExW` at `0x18001a1fc`
- `ADVAPI32!RegCloseKey` at `0x18001a309`
- `ADVAPI32!RegCloseKey` at `0x18001a32e`
- `ADVAPI32!RegCloseKey` at `0x18001a309`
- `ADVAPI32!RegCloseKey` at `0x18001a32e`

## string_xrefs

- `0x18001a2c5`: `:Path`

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
  dword_180046794 = IsPathLocal;
  return v8;
}

```

## disassembly

```asm
0x18001a0fc  mov     [rsp-8+arg_8], rbx
0x18001a101  push    rbp
0x18001a102  push    rsi
0x18001a103  push    rdi
0x18001a104  push    r12
0x18001a106  push    r14
0x18001a108  lea     rbp, [rsp-1C0h]
0x18001a110  sub     rsp, 2C0h
0x18001a117  mov     rax, cs:__security_cookie
0x18001a11e  xor     rax, rsp
0x18001a121  mov     [rbp+1E0h+var_30], rax
0x18001a128  xor     r14d, r14d
0x18001a12b  mov     [rsp+2E0h+var_290], rcx
0x18001a130  mov     [rcx], r14w
0x18001a134  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\BidInterface\\Load"...
0x18001a13b  mov     rsi, r9
0x18001a13e  mov     [rsp+2E0h+var_280], r14
0x18001a143  mov     rbx, rcx
0x18001a146  mov     [rsp+2E0h+hKey], r14
0x18001a14b  lea     rax, [rsp+2E0h+hKey]
0x18001a150  mov     [rsp+2E0h+var_288], 21Ah
0x18001a159  lea     r12, aNotfound; "<NotFound>"
0x18001a160  mov     [rsp+2E0h+lpOutputString], rdx
0x18001a165  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001a16c  mov     [rsp+2E0h+var_298], r12
0x18001a171  mov     r9d, 20019h; samDesired
0x18001a177  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18001a17c  xor     r8d, r8d; ulOptions
0x18001a17f  call    cs:__imp_RegOpenKeyExW
0x18001a186  nop     dword ptr [rax+rax+00h]
0x18001a18b  test    eax, eax
0x18001a18d  jz      short loc_18001A1B8
0x18001a18f  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18001a193  mov     r8, r12; Source
0x18001a196  mov     edx, 10Dh; SizeInWords
0x18001a19b  mov     rcx, rbx; Destination
0x18001a19e  call    cs:__imp_wcsncpy_s
0x18001a1a5  nop     dword ptr [rax+rax+00h]
0x18001a1aa  mov     eax, r14d
0x18001a1ad  mov     ecx, r14d
0x18001a1b0  mov     edi, r14d
0x18001a1b3  jmp     loc_18001A3EC
0x18001a1b8  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18001a1bd  lea     rax, [rsp+2E0h+cbData]
0x18001a1c2  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x18001a1c7  lea     r9, [rsp+2E0h+Type]; lpType
0x18001a1cc  lea     rax, [rsp+2E0h+Data]
0x18001a1d1  mov     [rsp+2E0h+var_268], r14
0x18001a1d6  xor     r8d, r8d; lpReserved
0x18001a1d9  mov     [rsp+2E0h+phkResult], rax; lpData
0x18001a1de  lea     rdx, ValueName; ":LdrMsg"
0x18001a1e5  mov     [rsp+2E0h+var_270], r14
0x18001a1ea  mov     dword ptr [rsp+2E0h+Data], r14d
0x18001a1ef  mov     [rsp+2E0h+cbData], 4
0x18001a1f7  mov     [rsp+2E0h+Type], r14d
0x18001a1fc  call    cs:__imp_RegQueryValueExW
0x18001a203  nop     dword ptr [rax+rax+00h]
0x18001a208  mov     edi, 1
0x18001a20d  test    eax, eax
0x18001a20f  jnz     short loc_18001A223
0x18001a211  cmp     [rsp+2E0h+Type], 4
0x18001a216  jnz     short loc_18001A223
0x18001a218  mov     dword ptr [rsp+2E0h+var_280], edi
0x18001a21c  cmp     dword ptr [rsp+2E0h+Data], r14d
0x18001a221  jnz     short loc_18001A228
0x18001a223  mov     dword ptr [rsp+2E0h+var_280], r14d
0x18001a228  lea     r9, [rsp+2E0h+var_270]
0x18001a22d  lea     r8, [rsp+2E0h+var_268]
0x18001a232  lea     rcx, [rbp+1E0h+Filename]; lpFilename
0x18001a236  call    BuildApplicationPid
0x18001a23b  test    eax, eax
0x18001a23d  jz      loc_18001A2C5
0x18001a243  lea     rax, [rbp+1E0h+Filename]
0x18001a247  lea     rcx, [rsp+2E0h+hKey]
0x18001a24c  mov     [rsp+2E0h+var_298], rax
0x18001a251  call    _bidLdrReadStr
0x18001a256  test    eax, eax
0x18001a258  jnz     loc_18001A329
0x18001a25e  mov     rax, [rsp+2E0h+var_270]
0x18001a263  lea     rcx, [rax+rax]
0x18001a267  cmp     rcx, 224h
0x18001a26e  jnb     loc_18001A323
0x18001a274  mov     [rbp+rcx+1E0h+Filename], r14w
0x18001a27a  lea     rcx, [rsp+2E0h+hKey]
0x18001a27f  call    _bidLdrReadStr
0x18001a284  test    eax, eax
0x18001a286  jnz     loc_18001A329
0x18001a28c  mov     rax, [rsp+2E0h+var_268]
0x18001a291  test    rax, rax
0x18001a294  jz      short loc_18001A2C5
0x18001a296  mov     ecx, 2Ah ; '*'
0x18001a29b  mov     [rbp+rax*2+1E0h+Filename], cx
0x18001a2a0  lea     rcx, ds:2[rax*2]
0x18001a2a8  cmp     rcx, 224h
0x18001a2af  jnb     short loc_18001A323
0x18001a2b1  mov     [rbp+rcx+1E0h+Filename], r14w
0x18001a2b7  lea     rcx, [rsp+2E0h+hKey]
0x18001a2bc  call    _bidLdrReadStr
0x18001a2c1  test    eax, eax
0x18001a2c3  jnz     short loc_18001A329
0x18001a2c5  lea     rax, aPath; ":Path"
0x18001a2cc  lea     rcx, [rsp+2E0h+hKey]
0x18001a2d1  mov     [rsp+2E0h+var_298], rax
0x18001a2d6  call    _bidLdrReadStr
0x18001a2db  test    eax, eax
0x18001a2dd  jnz     short loc_18001A329
0x18001a2df  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18001a2e3  mov     [rsp+2E0h+var_298], r12
0x18001a2e8  mov     r8, r12; Source
0x18001a2eb  mov     dword ptr [rsp+2E0h+var_288+4], r14d
0x18001a2f0  mov     edx, 10Dh; SizeInWords
0x18001a2f5  mov     rcx, rbx; Destination
0x18001a2f8  call    cs:__imp_wcsncpy_s
0x18001a2ff  nop     dword ptr [rax+rax+00h]
0x18001a304  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18001a309  call    cs:__imp_RegCloseKey
0x18001a310  nop     dword ptr [rax+rax+00h]
0x18001a315  mov     eax, dword ptr [rsp+2E0h+var_288+4]
0x18001a319  mov     edi, r14d
0x18001a31c  mov     [rsp+2E0h+hKey], r14
0x18001a321  jmp     short loc_18001A35B
0x18001a323  call    __report_rangecheckfailure
0x18001a329  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18001a32e  call    cs:__imp_RegCloseKey
0x18001a335  nop     dword ptr [rax+rax+00h]
0x18001a33a  mov     eax, dword ptr [rsp+2E0h+var_288+4]
0x18001a33e  mov     [rsp+2E0h+hKey], r14
0x18001a343  mov     [rbx+21Ah], r14w
0x18001a34b  test    eax, eax
0x18001a34d  jz      short loc_18001A35B
0x18001a34f  mov     rcx, rbx; lpRootPathName
0x18001a352  call    _bidLdrIsPathLocal
0x18001a357  mov     dword ptr [rsp+2E0h+var_288+4], eax
0x18001a35b  mov     ecx, dword ptr [rsp+2E0h+var_280]
0x18001a35f  test    ecx, ecx
0x18001a361  jz      loc_18001A3EC
0x18001a367  lea     rcx, OutputString; "*** [HKLM\\"
0x18001a36e  call    cs:__imp_OutputDebugStringW
0x18001a375  nop     dword ptr [rax+rax+00h]
0x18001a37a  mov     rcx, [rsp+2E0h+lpOutputString]; lpOutputString
0x18001a37f  call    cs:__imp_OutputDebugStringW
0x18001a386  nop     dword ptr [rax+rax+00h]
0x18001a38b  lea     rcx, asc_18003A458; "\\\""
0x18001a392  call    cs:__imp_OutputDebugStringW
0x18001a399  nop     dword ptr [rax+rax+00h]
0x18001a39e  mov     rcx, [rsp+2E0h+var_298]; lpOutputString
0x18001a3a3  call    cs:__imp_OutputDebugStringW
0x18001a3aa  nop     dword ptr [rax+rax+00h]
0x18001a3af  lea     rcx, asc_18003A460; "\"] \n*** \""
0x18001a3b6  call    cs:__imp_OutputDebugStringW
0x18001a3bd  nop     dword ptr [rax+rax+00h]
0x18001a3c2  mov     rcx, rbx; lpOutputString
0x18001a3c5  call    cs:__imp_OutputDebugStringW
0x18001a3cc  nop     dword ptr [rax+rax+00h]
0x18001a3d1  lea     rcx, asc_18003A474; "\"\n"
0x18001a3d8  call    cs:__imp_OutputDebugStringW
0x18001a3df  nop     dword ptr [rax+rax+00h]
0x18001a3e4  mov     ecx, dword ptr [rsp+2E0h+var_280]
0x18001a3e8  mov     eax, dword ptr [rsp+2E0h+var_288+4]
0x18001a3ec  mov     [rsi], ecx
0x18001a3ee  mov     cs:dword_180046794, eax
0x18001a3f4  mov     eax, edi
0x18001a3f6  mov     rcx, [rbp+1E0h+var_30]
0x18001a3fd  xor     rcx, rsp; StackCookie
0x18001a400  call    __security_check_cookie
0x18001a405  mov     rbx, [rsp+2E0h+arg_8]
0x18001a40d  add     rsp, 2C0h
0x18001a414  pop     r14
0x18001a416  pop     r12
0x18001a418  pop     rdi
0x18001a419  pop     rsi
0x18001a41a  pop     rbp
0x18001a41b  retn
```
