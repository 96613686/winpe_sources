# _bidLdrReadProfile

- ea: `0x10054609c`
- end: `0x10054633d`
- name: `_bidLdrReadProfile`
- size: `673`
- prototype: `__int64 __fastcall(LPCWSTR lpRootPathName)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x100545740`

## callees

- `0x100545f84`
- `0x10054609c`
- `0x100546344`
- `0x100548210`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x1005461c1`
- `KERNEL32!GetModuleFileNameW` at `0x1005461c1`
- `KERNEL32!OutputDebugStringW` at `0x1005462c3`
- `KERNEL32!OutputDebugStringW` at `0x1005462ce`
- `KERNEL32!OutputDebugStringW` at `0x1005462db`
- `KERNEL32!OutputDebugStringW` at `0x1005462e6`
- `KERNEL32!OutputDebugStringW` at `0x1005462f3`
- `KERNEL32!OutputDebugStringW` at `0x1005462fc`
- `KERNEL32!OutputDebugStringW` at `0x100546309`
- `KERNEL32!OutputDebugStringW` at `0x1005462c3`
- `KERNEL32!OutputDebugStringW` at `0x1005462ce`
- `KERNEL32!OutputDebugStringW` at `0x1005462db`
- `KERNEL32!OutputDebugStringW` at `0x1005462e6`
- `KERNEL32!OutputDebugStringW` at `0x1005462f3`
- `KERNEL32!OutputDebugStringW` at `0x1005462fc`
- `KERNEL32!OutputDebugStringW` at `0x100546309`
- `KERNEL32!lstrlenW` at `0x1005461fd`
- `KERNEL32!lstrlenW` at `0x1005461fd`
- `ADVAPI32!RegQueryValueExW` at `0x10054618d`
- `ADVAPI32!RegQueryValueExW` at `0x10054618d`
- `ADVAPI32!RegOpenKeyExW` at `0x100546122`
- `ADVAPI32!RegOpenKeyExW` at `0x100546122`
- `ADVAPI32!RegCloseKey` at `0x10054628c`
- `ADVAPI32!RegCloseKey` at `0x10054628c`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x10054613c`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x100546281`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x10054613c`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x100546281`

## string_xrefs

- `0x10054624d`: `:Path`

## pseudocode

```c
__int64 __fastcall bidLdrReadProfile(wchar_t *lpRootPathName, int a2, _DWORD *a3, _DWORD *a4)
{
  __int64 v4; // rdi
  int IsPathLocal; // ecx
  WCHAR *i; // rax
  int *v10; // rax
  __int64 result; // rax
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpOutputString; // [rsp+40h] [rbp-C0h]
  LPCWSTR v16; // [rsp+48h] [rbp-B8h]
  wchar_t *v17; // [rsp+50h] [rbp-B0h]
  int v18; // [rsp+58h] [rbp-A8h]
  __int64 v19; // [rsp+5Ch] [rbp-A4h]
  DWORD cbData[2]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Filename[269]; // [rsp+70h] [rbp-90h] BYREF
  int v22; // [rsp+28Ah] [rbp+18Ah] BYREF

  v4 = a2;
  v17 = lpRootPathName;
  v16 = L"<NotFound>";
  lpOutputString = L"SOFTWARE\\Microsoft\\BidInterface\\Loader";
  v18 = 2 * a2 - 2;
  hKey = 0;
  v19 = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\BidInterface\\Loader", 0, 0x20019u, &hKey) )
  {
    wcsncpy_s(lpRootPathName, (int)v4 - 1, L"<NotFound>", 0xFFFFFFFFFFFFFFFFuLL);
    IsPathLocal = 0;
    v19 = 0;
  }
  else
  {
    *(_DWORD *)Data = 0;
    cbData[0] = 4;
    Type = 0;
    HIDWORD(v19) = !RegQueryValueExW(hKey, L":LdrMsg", 0, &Type, Data, cbData) && Type == 4 && *(_DWORD *)Data != 0;
    if ( GetModuleFileNameW(0, Filename, 0x10Du) - 1 <= 0x10B )
    {
      LOWORD(v22) = 0;
      v16 = Filename;
      if ( !(unsigned int)bidLdrReadStr(&hKey) )
      {
        for ( i = (WCHAR *)&cbData[1] + lstrlenW(Filename) + 1; i >= Filename; --i )
        {
          if ( *i == 92 || *i == 47 )
          {
            v10 = (int *)(i + 1);
            if ( v10 < &v22 )
            {
              *v10 = 42;
              if ( (unsigned int)bidLdrReadStr(&hKey) )
                goto LABEL_19;
            }
            break;
          }
        }
        v16 = L":Path";
        if ( !(unsigned int)bidLdrReadStr(&hKey) )
        {
          v16 = L"<NotFound>";
          LODWORD(v19) = 0;
          wcsncpy_s(lpRootPathName, (int)v4 - 1, L"<NotFound>", 0xFFFFFFFFFFFFFFFFuLL);
        }
      }
    }
LABEL_19:
    RegCloseKey(hKey);
    IsPathLocal = v19;
    hKey = 0;
  }
  lpRootPathName[v4 - 1] = 0;
  if ( IsPathLocal )
  {
    IsPathLocal = bidLdrIsPathLocal(lpRootPathName, v4);
    LODWORD(v19) = IsPathLocal;
  }
  if ( HIDWORD(v19) )
  {
    OutputDebugStringW(L"*** [HKLM\\");
    OutputDebugStringW(lpOutputString);
    OutputDebugStringW(L"\\\"");
    OutputDebugStringW(v16);
    OutputDebugStringW(L"\"] \n*** \"");
    OutputDebugStringW(lpRootPathName);
    OutputDebugStringW(L"\"\n");
    IsPathLocal = v19;
  }
  result = HIDWORD(v19);
  *a4 = HIDWORD(v19);
  *a3 = IsPathLocal;
  return result;
}

```

## disassembly

```asm
0x10054609c  push    rbp
0x10054609e  push    rbx
0x10054609f  push    rsi
0x1005460a0  push    rdi
0x1005460a1  push    r12
0x1005460a3  push    r14
0x1005460a5  push    r15
0x1005460a7  lea     rbp, [rsp-1A0h]
0x1005460af  sub     rsp, 2A0h
0x1005460b6  mov     rax, cs:__security_cookie
0x1005460bd  xor     rax, rsp
0x1005460c0  mov     [rbp+1D0h+var_40], rax
0x1005460c7  movsxd  rdi, edx
0x1005460ca  lea     r12, aNotfound; "<NotFound>"
0x1005460d1  mov     r14, r9
0x1005460d4  mov     [rsp+2D0h+var_280], rcx
0x1005460d9  mov     rsi, r8
0x1005460dc  mov     [rsp+2D0h+var_288], r12
0x1005460e1  mov     rbx, rcx
0x1005460e4  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\BidInterface\\Load"...
0x1005460eb  lea     eax, ds:0FFFFFFFFFFFFFFFEh[rdi*2]
0x1005460f2  mov     [rsp+2D0h+lpOutputString], rdx
0x1005460f7  mov     [rsp+2D0h+var_278], eax
0x1005460fb  xor     r15d, r15d
0x1005460fe  lea     rax, [rsp+2D0h+hKey]
0x100546103  mov     [rsp+2D0h+hKey], r15
0x100546108  mov     r9d, 20019h; samDesired
0x10054610e  mov     [rsp+2D0h+phkResult], rax; phkResult
0x100546113  xor     r8d, r8d; ulOptions
0x100546116  mov     [rsp+2D0h+var_274], r15
0x10054611b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x100546122  call    cs:__imp_RegOpenKeyExW
0x100546128  test    eax, eax
0x10054612a  jz      short loc_100546153
0x10054612c  lea     eax, [rdi-1]
0x10054612f  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x100546133  movsxd  rdx, eax; SizeInWords
0x100546136  mov     r8, r12; Source
0x100546139  mov     rcx, rbx; Destination
0x10054613c  call    cs:__imp_wcsncpy_s
0x100546142  mov     ecx, r15d
0x100546145  mov     dword ptr [rsp+2D0h+var_274+4], r15d
0x10054614a  mov     dword ptr [rsp+2D0h+var_274], ecx
0x10054614e  jmp     loc_10054629B
0x100546153  mov     rcx, [rsp+2D0h+hKey]; hKey
0x100546158  lea     rax, [rsp+2D0h+cbData]
0x10054615d  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x100546162  lea     r9, [rsp+2D0h+Type]; lpType
0x100546167  lea     rax, [rsp+2D0h+Data]
0x10054616c  mov     dword ptr [rsp+2D0h+Data], r15d
0x100546171  xor     r8d, r8d; lpReserved
0x100546174  mov     [rsp+2D0h+phkResult], rax; lpData
0x100546179  lea     rdx, aLdrmsg; ":LdrMsg"
0x100546180  mov     [rsp+2D0h+cbData], 4
0x100546188  mov     [rsp+2D0h+Type], r15d
0x10054618d  call    cs:__imp_RegQueryValueExW
0x100546193  test    eax, eax
0x100546195  jnz     short loc_1005461AF
0x100546197  cmp     [rsp+2D0h+Type], 4
0x10054619c  jnz     short loc_1005461AF
0x10054619e  cmp     dword ptr [rsp+2D0h+Data], r15d
0x1005461a3  mov     eax, r15d
0x1005461a6  setnz   al
0x1005461a9  mov     dword ptr [rsp+2D0h+var_274+4], eax
0x1005461ad  jmp     short loc_1005461B4
0x1005461af  mov     dword ptr [rsp+2D0h+var_274+4], r15d
0x1005461b4  mov     r8d, 10Dh; nSize
0x1005461ba  lea     rdx, [rsp+2D0h+Filename]; lpFilename
0x1005461bf  xor     ecx, ecx; hModule
0x1005461c1  call    cs:__imp_GetModuleFileNameW
0x1005461c7  dec     eax
0x1005461c9  cmp     eax, 10Bh
0x1005461ce  ja      loc_100546287
0x1005461d4  lea     rax, [rsp+2D0h+Filename]
0x1005461d9  mov     word ptr [rbp+1D0h+var_46], r15w
0x1005461e1  lea     rcx, [rsp+2D0h+hKey]
0x1005461e6  mov     [rsp+2D0h+var_288], rax
0x1005461eb  call    _bidLdrReadStr
0x1005461f0  test    eax, eax
0x1005461f2  jnz     loc_100546287
0x1005461f8  lea     rcx, [rsp+2D0h+Filename]; lpString
0x1005461fd  call    cs:__imp_lstrlenW
0x100546203  movsxd  rcx, eax
0x100546206  lea     rax, [rsp+rcx*2+2D0h+var_262]
0x10054620b  jmp     short loc_10054621D
0x10054620d  cmp     word ptr [rax], 5Ch ; '\'
0x100546211  jz      short loc_100546229
0x100546213  cmp     word ptr [rax], 2Fh ; '/'
0x100546217  jz      short loc_100546229
0x100546219  sub     rax, 2
0x10054621d  lea     rcx, [rsp+2D0h+Filename]
0x100546222  cmp     rax, rcx
0x100546225  jnb     short loc_10054620D
0x100546227  jmp     short loc_10054624D
0x100546229  add     rax, 2
0x10054622d  lea     rcx, [rbp+1D0h+var_46]
0x100546234  cmp     rax, rcx
0x100546237  jnb     short loc_10054624D
0x100546239  lea     rcx, [rsp+2D0h+hKey]
0x10054623e  mov     dword ptr [rax], 2Ah ; '*'
0x100546244  call    _bidLdrReadStr
0x100546249  test    eax, eax
0x10054624b  jnz     short loc_100546287
0x10054624d  lea     rax, aPath; ":Path"
0x100546254  lea     rcx, [rsp+2D0h+hKey]
0x100546259  mov     [rsp+2D0h+var_288], rax
0x10054625e  call    _bidLdrReadStr
0x100546263  test    eax, eax
0x100546265  jnz     short loc_100546287
0x100546267  lea     eax, [rdi-1]
0x10054626a  mov     [rsp+2D0h+var_288], r12
0x10054626f  movsxd  rdx, eax; SizeInWords
0x100546272  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x100546276  mov     r8, r12; Source
0x100546279  mov     dword ptr [rsp+2D0h+var_274], r15d
0x10054627e  mov     rcx, rbx; Destination
0x100546281  call    cs:__imp_wcsncpy_s
0x100546287  mov     rcx, [rsp+2D0h+hKey]; hKey
0x10054628c  call    cs:__imp_RegCloseKey
0x100546292  mov     ecx, dword ptr [rsp+2D0h+var_274]
0x100546296  mov     [rsp+2D0h+hKey], r15
0x10054629b  mov     [rbx+rdi*2-2], r15w
0x1005462a1  test    ecx, ecx
0x1005462a3  jz      short loc_1005462B5
0x1005462a5  mov     edx, edi
0x1005462a7  mov     rcx, rbx; lpRootPathName
0x1005462aa  call    _bidLdrIsPathLocal
0x1005462af  mov     ecx, eax
0x1005462b1  mov     dword ptr [rsp+2D0h+var_274], eax
0x1005462b5  cmp     dword ptr [rsp+2D0h+var_274+4], r15d
0x1005462ba  jz      short loc_100546313
0x1005462bc  lea     rcx, aHklm; "*** [HKLM\\"
0x1005462c3  call    cs:__imp_OutputDebugStringW
0x1005462c9  mov     rcx, [rsp+2D0h+lpOutputString]; lpOutputString
0x1005462ce  call    cs:__imp_OutputDebugStringW
0x1005462d4  lea     rcx, asc_1005B2D08; "\\\""
0x1005462db  call    cs:__imp_OutputDebugStringW
0x1005462e1  mov     rcx, [rsp+2D0h+var_288]; lpOutputString
0x1005462e6  call    cs:__imp_OutputDebugStringW
0x1005462ec  lea     rcx, asc_1005B2D10; "\"] \n*** \""
0x1005462f3  call    cs:__imp_OutputDebugStringW
0x1005462f9  mov     rcx, rbx; lpOutputString
0x1005462fc  call    cs:__imp_OutputDebugStringW
0x100546302  lea     rcx, asc_1005B2D24; "\"\n"
0x100546309  call    cs:__imp_OutputDebugStringW
0x10054630f  mov     ecx, dword ptr [rsp+2D0h+var_274]
0x100546313  mov     eax, dword ptr [rsp+2D0h+var_274+4]
0x100546317  mov     [r14], eax
0x10054631a  mov     [rsi], ecx
0x10054631c  mov     rcx, [rbp+1D0h+var_40]
0x100546323  xor     rcx, rsp; StackCookie
0x100546326  call    __security_check_cookie
0x10054632b  add     rsp, 2A0h
0x100546332  pop     r15
0x100546334  pop     r14
0x100546336  pop     r12
0x100546338  pop     rdi
0x100546339  pop     rsi
0x10054633a  pop     rbx
0x10054633b  pop     rbp
0x10054633c  retn
```
