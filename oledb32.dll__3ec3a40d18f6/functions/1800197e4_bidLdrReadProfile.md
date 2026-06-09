# _bidLdrReadProfile

- ea: `0x1800197e4`
- end: `0x180019b75`
- name: `_bidLdrReadProfile`
- size: `913`
- prototype: `__int64 __fastcall(LPCWSTR lpRootPathName)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180011844`

## callees

- `0x1800197e4`
- `0x18002e848`
- `0x18003af88`
- `0x18003b418`
- `0x18003b534`
- `0x18007e700`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180019888`
- `msvcrt!wcsncpy_s` at `0x180019b4f`
- `msvcrt!wcsncpy_s` at `0x180019888`
- `msvcrt!wcsncpy_s` at `0x180019b4f`
- `msvcrt!_ultow_s` at `0x180019986`
- `msvcrt!_ultow_s` at `0x180019986`
- `KERNEL32!OutputDebugStringW` at `0x180019a7d`
- `KERNEL32!OutputDebugStringW` at `0x180019a88`
- `KERNEL32!OutputDebugStringW` at `0x180019a95`
- `KERNEL32!OutputDebugStringW` at `0x180019aa0`
- `KERNEL32!OutputDebugStringW` at `0x180019aad`
- `KERNEL32!OutputDebugStringW` at `0x180019ab6`
- `KERNEL32!OutputDebugStringW` at `0x180019ac3`
- `KERNEL32!OutputDebugStringW` at `0x180019a7d`
- `KERNEL32!OutputDebugStringW` at `0x180019a88`
- `KERNEL32!OutputDebugStringW` at `0x180019a95`
- `KERNEL32!OutputDebugStringW` at `0x180019aa0`
- `KERNEL32!OutputDebugStringW` at `0x180019aad`
- `KERNEL32!OutputDebugStringW` at `0x180019ab6`
- `KERNEL32!OutputDebugStringW` at `0x180019ac3`
- `KERNEL32!GetCurrentProcessId` at `0x18001996e`
- `KERNEL32!GetCurrentProcessId` at `0x18001996e`
- `KERNEL32!GetModuleFileNameW` at `0x180019918`
- `KERNEL32!GetModuleFileNameW` at `0x180019918`
- `ADVAPI32!RegQueryValueExW` at `0x1800198da`
- `ADVAPI32!RegQueryValueExW` at `0x1800198da`
- `ADVAPI32!RegOpenKeyExW` at `0x18001986f`
- `ADVAPI32!RegOpenKeyExW` at `0x18001986f`
- `ADVAPI32!RegCloseKey` at `0x180019a42`
- `ADVAPI32!RegCloseKey` at `0x180019b5a`
- `ADVAPI32!RegCloseKey` at `0x180019a42`
- `ADVAPI32!RegCloseKey` at `0x180019b5a`

## string_xrefs

- `0x180019b15`: `:Path`

## pseudocode

```c
__int64 __fastcall bidLdrReadProfile(wchar_t *lpRootPathName, __int64 a2, __int64 a3, _DWORD *a4)
{
  int IsPathLocal; // eax
  int v7; // ecx
  unsigned int v8; // r14d
  DWORD ModuleFileNameW; // eax
  unsigned __int64 v10; // r15
  WCHAR *v11; // rsi
  DWORD CurrentProcessId; // eax
  __int64 v13; // rbx
  WCHAR *v14; // rax
  WCHAR *v15; // rcx
  unsigned __int64 v16; // rbx
  unsigned int lpcbData; // [rsp+28h] [rbp-D8h]
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpOutputString; // [rsp+40h] [rbp-C0h]
  LPCWSTR v23; // [rsp+48h] [rbp-B8h]
  wchar_t *v24; // [rsp+50h] [rbp-B0h]
  __int64 v25; // [rsp+58h] [rbp-A8h]
  __int64 v26; // [rsp+60h] [rbp-A0h]
  DWORD cbData; // [rsp+68h] [rbp-98h] BYREF
  size_t BufferCount; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *Buffer; // [rsp+78h] [rbp-88h] BYREF
  WCHAR Filename[280]; // [rsp+80h] [rbp-80h] BYREF

  v24 = lpRootPathName;
  *lpRootPathName = 0;
  hKey = 0;
  v26 = 0;
  v23 = L"<NotFound>";
  v25 = 538;
  lpOutputString = L"SOFTWARE\\Microsoft\\BidInterface\\Loader";
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\BidInterface\\Loader", 0, 0x20019u, &hKey) )
  {
    wcsncpy_s(lpRootPathName, 0x10Du, L"<NotFound>", 0xFFFFFFFFFFFFFFFFuLL);
    IsPathLocal = 0;
    v7 = 0;
    v8 = 0;
    goto LABEL_26;
  }
  *(_DWORD *)Data = 0;
  cbData = 4;
  Type = 0;
  v8 = 1;
  if ( RegQueryValueExW(hKey, L":LdrMsg", 0, &Type, Data, &cbData) || Type != 4 || (LODWORD(v26) = 1, !*(_DWORD *)Data) )
    LODWORD(v26) = 0;
  Filename[0] = 0;
  ModuleFileNameW = GetModuleFileNameW(0, Filename, 0x112u);
  if ( ModuleFileNameW - 1 > 0x110
    || (BufferCount = 274 - ModuleFileNameW,
        v10 = ModuleFileNameW,
        v11 = &Filename[v10],
        Buffer = &Filename[v10],
        StringCchCopyExW(&Filename[v10], BufferCount, L":", &Buffer, &BufferCount, lpcbData) < 0)
    || (CurrentProcessId = GetCurrentProcessId(), _ultow_s(CurrentProcessId, Buffer, BufferCount, 10)) )
  {
    Filename[0] = 0;
    goto LABEL_29;
  }
  v13 = 0;
  v14 = &Filename[v10];
  while ( 1 )
  {
    v15 = v14--;
    if ( v14 < Filename )
      break;
    if ( *v14 == 92 || *v14 == 47 )
    {
      if ( v15 < v11 )
        v13 = v15 - Filename;
      break;
    }
  }
  v23 = Filename;
  if ( (unsigned int)bidLdrReadStr(&hKey) )
    goto LABEL_22;
  if ( v10 >= 274 )
    goto LABEL_27;
  *v11 = 0;
  if ( (unsigned int)bidLdrReadStr(&hKey) )
    goto LABEL_22;
  if ( !v13 )
    goto LABEL_29;
  Filename[v13] = 42;
  v16 = 2 * v13 + 2;
  if ( v16 >= 0x224 )
LABEL_27:
    _report_rangecheckfailure();
  *(WCHAR *)((char *)Filename + v16) = 0;
  if ( (unsigned int)bidLdrReadStr(&hKey) )
    goto LABEL_22;
LABEL_29:
  v23 = L":Path";
  if ( (unsigned int)bidLdrReadStr(&hKey) )
  {
LABEL_22:
    RegCloseKey(hKey);
    hKey = 0;
    lpRootPathName[269] = 0;
    IsPathLocal = HIDWORD(v25);
    if ( HIDWORD(v25) )
    {
      IsPathLocal = bidLdrIsPathLocal(lpRootPathName);
      HIDWORD(v25) = IsPathLocal;
    }
    goto LABEL_24;
  }
  HIDWORD(v25) = 0;
  v23 = L"<NotFound>";
  wcsncpy_s(lpRootPathName, 0x10Du, L"<NotFound>", 0xFFFFFFFFFFFFFFFFuLL);
  RegCloseKey(hKey);
  IsPathLocal = HIDWORD(v25);
  v8 = 0;
  hKey = 0;
LABEL_24:
  v7 = v26;
  if ( (_DWORD)v26 )
  {
    OutputDebugStringW(L"*** [HKLM\\");
    OutputDebugStringW(lpOutputString);
    OutputDebugStringW(L"\\\"");
    OutputDebugStringW(v23);
    OutputDebugStringW(L"\"] \n*** \"");
    OutputDebugStringW(lpRootPathName);
    OutputDebugStringW(L"\"\n");
    v7 = v26;
    IsPathLocal = HIDWORD(v25);
  }
LABEL_26:
  *a4 = v7;
  dword_1800BFCA4 = IsPathLocal;
  return v8;
}

```

## disassembly

```asm
0x1800197e4  mov     [rsp-8+arg_8], rbx
0x1800197e9  mov     [rsp-8+arg_10], rsi
0x1800197ee  push    rbp
0x1800197ef  push    rdi
0x1800197f0  push    r12
0x1800197f2  push    r14
0x1800197f4  push    r15
0x1800197f6  lea     rbp, [rsp-1C0h]
0x1800197fe  sub     rsp, 2C0h
0x180019805  mov     rax, cs:__security_cookie
0x18001980c  xor     rax, rsp
0x18001980f  mov     [rbp+1E0h+var_30], rax
0x180019816  xor     eax, eax
0x180019818  mov     [rsp+2E0h+var_290], rcx
0x18001981d  mov     [rcx], ax
0x180019820  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\BidInterface\\Load"...
0x180019827  mov     [rsp+2E0h+hKey], rax
0x18001982c  lea     rbx, aNotfound; "<NotFound>"
0x180019833  lea     rax, [rsp+2E0h+hKey]
0x180019838  mov     [rsp+2E0h+var_280], 0
0x180019841  mov     r12, r9
0x180019844  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180019849  mov     rdi, rcx
0x18001984c  mov     [rsp+2E0h+var_298], rbx
0x180019851  mov     r9d, 20019h; samDesired
0x180019857  mov     [rsp+2E0h+var_288], 21Ah
0x180019860  xor     r8d, r8d; ulOptions
0x180019863  mov     [rsp+2E0h+lpOutputString], rdx
0x180019868  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001986f  call    cs:__imp_RegOpenKeyExW
0x180019875  test    eax, eax
0x180019877  jz      short loc_18001989A
0x180019879  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18001987d  mov     r8, rbx; Source
0x180019880  mov     edx, 10Dh; SizeInWords
0x180019885  mov     rcx, rdi; Destination
0x180019888  call    cs:__imp_wcsncpy_s
0x18001988e  xor     eax, eax
0x180019890  xor     ecx, ecx
0x180019892  xor     r14d, r14d
0x180019895  jmp     loc_180019AD1
0x18001989a  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18001989f  lea     rax, [rsp+2E0h+cbData]
0x1800198a4  mov     [rsp+2E0h+lpcbData], rax; unsigned int
0x1800198a9  lea     r9, [rsp+2E0h+Type]; lpType
0x1800198ae  lea     rax, [rsp+2E0h+Data]
0x1800198b3  mov     dword ptr [rsp+2E0h+Data], 0
0x1800198bb  xor     r8d, r8d; lpReserved
0x1800198be  mov     [rsp+2E0h+phkResult], rax; lpData
0x1800198c3  lea     rdx, ValueName; ":LdrMsg"
0x1800198ca  mov     [rsp+2E0h+cbData], 4
0x1800198d2  mov     [rsp+2E0h+Type], 0
0x1800198da  call    cs:__imp_RegQueryValueExW
0x1800198e0  mov     r14d, 1
0x1800198e6  test    eax, eax
0x1800198e8  jnz     short loc_1800198FC
0x1800198ea  cmp     [rsp+2E0h+Type], 4
0x1800198ef  jnz     short loc_1800198FC
0x1800198f1  mov     dword ptr [rsp+2E0h+var_280], r14d
0x1800198f6  cmp     dword ptr [rsp+2E0h+Data], eax
0x1800198fa  jnz     short loc_180019904
0x1800198fc  mov     dword ptr [rsp+2E0h+var_280], 0
0x180019904  xor     eax, eax
0x180019906  lea     rdx, [rbp+1E0h+Filename]; lpFilename
0x18001990a  mov     ebx, 112h
0x18001990f  mov     [rbp+1E0h+Filename], ax
0x180019913  mov     r8d, ebx; nSize
0x180019916  xor     ecx, ecx; hModule
0x180019918  call    cs:__imp_GetModuleFileNameW
0x18001991e  lea     ecx, [rax-1]
0x180019921  cmp     ecx, 110h
0x180019927  ja      loc_180019B0F
0x18001992d  mov     ecx, eax
0x18001992f  lea     rsi, [rbp+1E0h+Filename]
0x180019933  sub     ebx, eax
0x180019935  lea     r9, [rsp+2E0h+Buffer]; unsigned __int16 **
0x18001993a  mov     edx, ebx; unsigned __int64
0x18001993c  lea     rax, [rsp+2E0h+BufferCount]
0x180019941  lea     r8, asc_1800915AC; ":"
0x180019948  mov     [rsp+2E0h+BufferCount], rdx
0x18001994d  lea     r15, [rcx+rcx]
0x180019951  mov     [rsp+2E0h+phkResult], rax; unsigned __int64 *
0x180019956  add     rsi, r15
0x180019959  mov     rcx, rsi; unsigned __int16 *
0x18001995c  mov     [rsp+2E0h+Buffer], rsi
0x180019961  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180019966  test    eax, eax
0x180019968  js      loc_180019B0F
0x18001996e  call    cs:__imp_GetCurrentProcessId
0x180019974  mov     r8, [rsp+2E0h+BufferCount]; BufferCount
0x180019979  mov     r9d, 0Ah; Radix
0x18001997f  mov     rdx, [rsp+2E0h+Buffer]; Buffer
0x180019984  mov     ecx, eax; Value
0x180019986  call    cs:__imp__ultow_s
0x18001998c  test    eax, eax
0x18001998e  jnz     loc_180019B0F
0x180019994  xor     ebx, ebx
0x180019996  mov     rax, rsi
0x180019999  mov     rcx, rax
0x18001999c  lea     rdx, [rbp+1E0h+Filename]
0x1800199a0  sub     rax, 2
0x1800199a4  cmp     rax, rdx
0x1800199a7  jb      short loc_1800199C7
0x1800199a9  cmp     word ptr [rax], 5Ch ; '\'
0x1800199ad  jz      short loc_1800199B5
0x1800199af  cmp     word ptr [rax], 2Fh ; '/'
0x1800199b3  jnz     short loc_180019999
0x1800199b5  cmp     rcx, rsi
0x1800199b8  jnb     short loc_1800199C7
0x1800199ba  lea     rax, [rbp+1E0h+Filename]
0x1800199be  mov     rbx, rcx
0x1800199c1  sub     rbx, rax
0x1800199c4  sar     rbx, 1
0x1800199c7  lea     rax, [rbp+1E0h+Filename]
0x1800199cb  lea     rcx, [rsp+2E0h+hKey]
0x1800199d0  mov     [rsp+2E0h+var_298], rax
0x1800199d5  call    _bidLdrReadStr
0x1800199da  test    eax, eax
0x1800199dc  jnz     short loc_180019A3D
0x1800199de  cmp     r15, 224h
0x1800199e5  jnb     loc_180019B09
0x1800199eb  lea     rcx, [rsp+2E0h+hKey]
0x1800199f0  mov     [rsi], ax
0x1800199f3  call    _bidLdrReadStr
0x1800199f8  test    eax, eax
0x1800199fa  jnz     short loc_180019A3D
0x1800199fc  test    rbx, rbx
0x1800199ff  jz      loc_180019B15
0x180019a05  mov     eax, 2Ah ; '*'
0x180019a0a  mov     [rbp+rbx*2+1E0h+Filename], ax
0x180019a0f  lea     rbx, ds:2[rbx*2]
0x180019a17  cmp     rbx, 224h
0x180019a1e  jnb     loc_180019B09
0x180019a24  xor     eax, eax
0x180019a26  lea     rcx, [rsp+2E0h+hKey]
0x180019a2b  mov     [rbp+rbx+1E0h+Filename], ax
0x180019a30  call    _bidLdrReadStr
0x180019a35  test    eax, eax
0x180019a37  jz      loc_180019B15
0x180019a3d  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180019a42  call    cs:__imp_RegCloseKey
0x180019a48  xor     eax, eax
0x180019a4a  mov     [rsp+2E0h+hKey], 0
0x180019a53  mov     [rdi+21Ah], ax
0x180019a5a  mov     eax, dword ptr [rsp+2E0h+var_288+4]
0x180019a5e  test    eax, eax
0x180019a60  jz      short loc_180019A6E
0x180019a62  mov     rcx, rdi; lpRootPathName
0x180019a65  call    _bidLdrIsPathLocal
0x180019a6a  mov     dword ptr [rsp+2E0h+var_288+4], eax
0x180019a6e  mov     ecx, dword ptr [rsp+2E0h+var_280]
0x180019a72  test    ecx, ecx
0x180019a74  jz      short loc_180019AD1
0x180019a76  lea     rcx, aHklm; "*** [HKLM\\"
0x180019a7d  call    cs:__imp_OutputDebugStringW
0x180019a83  mov     rcx, [rsp+2E0h+lpOutputString]; lpOutputString
0x180019a88  call    cs:__imp_OutputDebugStringW
0x180019a8e  lea     rcx, asc_1800915F8; "\\\""
0x180019a95  call    cs:__imp_OutputDebugStringW
0x180019a9b  mov     rcx, [rsp+2E0h+var_298]; lpOutputString
0x180019aa0  call    cs:__imp_OutputDebugStringW
0x180019aa6  lea     rcx, asc_180091600; "\"] \n*** \""
0x180019aad  call    cs:__imp_OutputDebugStringW
0x180019ab3  mov     rcx, rdi; lpOutputString
0x180019ab6  call    cs:__imp_OutputDebugStringW
0x180019abc  lea     rcx, asc_180091614; "\"\n"
0x180019ac3  call    cs:__imp_OutputDebugStringW
0x180019ac9  mov     ecx, dword ptr [rsp+2E0h+var_280]
0x180019acd  mov     eax, dword ptr [rsp+2E0h+var_288+4]
0x180019ad1  mov     [r12], ecx
0x180019ad5  mov     cs:dword_1800BFCA4, eax
0x180019adb  mov     eax, r14d
0x180019ade  mov     rcx, [rbp+1E0h+var_30]
0x180019ae5  xor     rcx, rsp; StackCookie
0x180019ae8  call    __security_check_cookie
0x180019aed  lea     r11, [rsp+2E0h+var_20]
0x180019af5  mov     rbx, [r11+38h]
0x180019af9  mov     rsi, [r11+40h]
0x180019afd  mov     rsp, r11
0x180019b00  pop     r15
0x180019b02  pop     r14
0x180019b04  pop     r12
0x180019b06  pop     rdi
0x180019b07  pop     rbp
0x180019b08  retn
0x180019b09  call    __report_rangecheckfailure
0x180019b0f  xor     eax, eax
0x180019b11  mov     [rbp+1E0h+Filename], ax
0x180019b15  lea     rax, aPath; ":Path"
0x180019b1c  lea     rcx, [rsp+2E0h+hKey]
0x180019b21  mov     [rsp+2E0h+var_298], rax
0x180019b26  call    _bidLdrReadStr
0x180019b2b  test    eax, eax
0x180019b2d  jnz     loc_180019A3D
0x180019b33  lea     r8, aNotfound; "<NotFound>"
0x180019b3a  mov     dword ptr [rsp+2E0h+var_288+4], eax
0x180019b3e  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180019b42  mov     [rsp+2E0h+var_298], r8
0x180019b47  mov     edx, 10Dh; SizeInWords
0x180019b4c  mov     rcx, rdi; Destination
0x180019b4f  call    cs:__imp_wcsncpy_s
0x180019b55  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180019b5a  call    cs:__imp_RegCloseKey
0x180019b60  mov     eax, dword ptr [rsp+2E0h+var_288+4]
0x180019b64  xor     r14d, r14d
0x180019b67  mov     [rsp+2E0h+hKey], 0
0x180019b70  jmp     loc_180019A6E
```
