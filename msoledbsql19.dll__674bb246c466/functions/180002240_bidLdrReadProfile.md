# _bidLdrReadProfile

- ea: `0x180002240`
- end: `0x180002616`
- name: `_bidLdrReadProfile`
- size: `982`
- prototype: `__int64 __fastcall(LPCWSTR lpOutputString)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001610`

## callees

- `0x180002240`
- `0x180002620`
- `0x180003d80`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x1800022eb`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180002438`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180002551`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x1800022eb`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180002438`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180002551`
- `KERNEL32!OutputDebugStringW` at `0x18000258d`
- `KERNEL32!OutputDebugStringW` at `0x180002598`
- `KERNEL32!OutputDebugStringW` at `0x1800025a5`
- `KERNEL32!OutputDebugStringW` at `0x1800025b0`
- `KERNEL32!OutputDebugStringW` at `0x1800025bd`
- `KERNEL32!OutputDebugStringW` at `0x1800025c6`
- `KERNEL32!OutputDebugStringW` at `0x1800025d3`
- `KERNEL32!OutputDebugStringW` at `0x18000258d`
- `KERNEL32!OutputDebugStringW` at `0x180002598`
- `KERNEL32!OutputDebugStringW` at `0x1800025a5`
- `KERNEL32!OutputDebugStringW` at `0x1800025b0`
- `KERNEL32!OutputDebugStringW` at `0x1800025bd`
- `KERNEL32!OutputDebugStringW` at `0x1800025c6`
- `KERNEL32!OutputDebugStringW` at `0x1800025d3`
- `KERNEL32!GetFullPathNameW` at `0x1800024f7`
- `KERNEL32!GetFullPathNameW` at `0x1800024f7`
- `KERNEL32!GetDriveTypeW` at `0x180002563`
- `KERNEL32!GetDriveTypeW` at `0x180002563`
- `KERNEL32!GetModuleFileNameW` at `0x180002370`
- `KERNEL32!GetModuleFileNameW` at `0x180002370`
- `KERNEL32!SearchPathW` at `0x180002523`
- `KERNEL32!SearchPathW` at `0x180002523`
- `ADVAPI32!RegOpenKeyExW` at `0x1800022cd`
- `ADVAPI32!RegOpenKeyExW` at `0x1800022cd`
- `ADVAPI32!RegQueryValueExW` at `0x18000233c`
- `ADVAPI32!RegQueryValueExW` at `0x18000233c`
- `ADVAPI32!RegCloseKey` at `0x180002443`
- `ADVAPI32!RegCloseKey` at `0x180002443`

## string_xrefs

- `0x180002403`: `:Path`

## pseudocode

```c
__int64 __fastcall bidLdrReadProfile(wchar_t *lpOutputString, int a2, BOOL *a3, _DWORD *a4)
{
  rsize_t v4; // rsi
  rsize_t v8; // rbx
  BOOL v9; // ecx
  DWORD ModuleFileNameW; // eax
  __int64 v11; // rbx
  BYTE *v12; // rcx
  int *v13; // rcx
  rsize_t v14; // rcx
  wchar_t *i; // rax
  wchar_t v16; // ax
  DWORD FullPathNameW; // eax
  WCHAR v18; // bx
  UINT DriveTypeW; // eax
  __int64 result; // rax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpOutputStringa; // [rsp+38h] [rbp-C8h]
  LPCWSTR v23; // [rsp+40h] [rbp-C0h]
  wchar_t *v24; // [rsp+48h] [rbp-B8h]
  int v25; // [rsp+50h] [rbp-B0h]
  unsigned int v26; // [rsp+54h] [rbp-ACh]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  DWORD cbData[2]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD Type; // [rsp+68h] [rbp-98h] BYREF
  BYTE Data[4]; // [rsp+6Ch] [rbp-94h] BYREF
  WCHAR Filename[269]; // [rsp+70h] [rbp-90h] BYREF
  int v32; // [rsp+28Ah] [rbp+18Ah] BYREF
  WCHAR Buffer[272]; // [rsp+290h] [rbp+190h] BYREF

  v4 = a2;
  v24 = lpOutputString;
  v27 = 0;
  hKey = 0;
  v23 = L"<NotFound>";
  v25 = 2 * a2 - 2;
  v26 = 0;
  lpOutputStringa = L"SOFTWARE\\Microsoft\\BidInterface\\Loader";
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\BidInterface\\Loader", 0, 0x20019u, &hKey) )
  {
    v8 = v4;
    wcsncpy_s(lpOutputString, v4 - 1, L"<NotFound>", 0xFFFFFFFFFFFFFFFFuLL);
    v9 = 0;
    LODWORD(v27) = 0;
    v26 = 0;
  }
  else
  {
    *(_DWORD *)Data = 0;
    cbData[0] = 4;
    Type = 0;
    LODWORD(v27) = !RegQueryValueExW(hKey, L":LdrMsg", 0, &Type, Data, cbData) && Type == 4 && *(_DWORD *)Data != 0;
    ModuleFileNameW = GetModuleFileNameW(0, Filename, 0x10Du);
    v11 = ModuleFileNameW;
    if ( ModuleFileNameW - 1 <= 0x10B )
    {
      LOWORD(v32) = 0;
      v23 = Filename;
      if ( !(unsigned int)bidLdrReadStr(&hKey) )
      {
        v12 = &Data[2 * v11 + 2];
        if ( v12 < (BYTE *)Filename )
          goto LABEL_16;
        while ( *(_WORD *)v12 != 92 && *(_WORD *)v12 != 47 )
        {
          v12 -= 2;
          if ( v12 < (BYTE *)Filename )
            goto LABEL_16;
        }
        v13 = (int *)(v12 + 2);
        if ( v13 >= &v32 || (*v13 = 42, !(unsigned int)bidLdrReadStr(&hKey)) )
        {
LABEL_16:
          v23 = L":Path";
          if ( !(unsigned int)bidLdrReadStr(&hKey) )
          {
            v23 = L"<NotFound>";
            v26 = 0;
            wcsncpy_s(lpOutputString, v4 - 1, L"<NotFound>", 0xFFFFFFFFFFFFFFFFuLL);
          }
        }
      }
    }
    RegCloseKey(hKey);
    v9 = v26;
    v8 = v4;
    hKey = 0;
  }
  lpOutputString[v8 - 1] = 0;
  if ( v9 )
  {
    if ( lpOutputString && v8 <= 0x7FFFFFFF )
    {
      v14 = v8;
      for ( i = lpOutputString; v14; --v14 )
      {
        if ( !*i )
          break;
        ++i;
      }
      if ( v14 && v8 - v14 >= 3 )
      {
        v16 = *lpOutputString;
        if ( *lpOutputString != 46 && (v16 == 92 || v16 == 47 || lpOutputString[1] == 58) )
          goto LABEL_36;
        *(_QWORD *)cbData = 0;
        if ( v16 == 46 )
          FullPathNameW = GetFullPathNameW(lpOutputString, 0x10Eu, Buffer, (LPWSTR *)cbData);
        else
          FullPathNameW = SearchPathW(0, lpOutputString, 0, 0x10Eu, Buffer, (LPWSTR *)cbData);
        if ( FullPathNameW - 1 <= 0x10C )
        {
          _mm_lfence();
          Buffer[269] = 0;
          wcsncpy_s(lpOutputString, v8, Buffer, 0xFFFFFFFFFFFFFFFFuLL);
LABEL_36:
          v18 = lpOutputString[3];
          lpOutputString[3] = 0;
          DriveTypeW = GetDriveTypeW(lpOutputString);
          lpOutputString[3] = v18;
          v9 = DriveTypeW == 3;
LABEL_38:
          v26 = v9;
          goto LABEL_39;
        }
      }
    }
    v9 = 0;
    goto LABEL_38;
  }
LABEL_39:
  if ( (_DWORD)v27 )
  {
    OutputDebugStringW(L"*** [HKLM\\");
    OutputDebugStringW(lpOutputStringa);
    OutputDebugStringW(L"\\\"");
    OutputDebugStringW(v23);
    OutputDebugStringW(L"\"] \n*** \"");
    OutputDebugStringW(lpOutputString);
    OutputDebugStringW(L"\"\n");
    *a4 = v27;
    result = v26;
    *a3 = v26;
  }
  else
  {
    result = 0;
    *a4 = 0;
    *a3 = v9;
  }
  return result;
}

```

## disassembly

```asm
0x180002240  push    rbp
0x180002242  push    rbx
0x180002243  push    rsi
0x180002244  push    rdi
0x180002245  push    r12
0x180002247  push    r13
0x180002249  push    r14
0x18000224b  push    r15
0x18000224d  lea     rbp, [rsp-3C8h]
0x180002255  sub     rsp, 4C8h
0x18000225c  mov     rax, cs:__security_cookie
0x180002263  xor     rax, rsp
0x180002266  mov     [rbp+400h+var_50], rax
0x18000226d  movsxd  rsi, edx
0x180002270  lea     r13, aNotfound; "<NotFound>"
0x180002277  xor     r12d, r12d
0x18000227a  mov     [rsp+500h+var_4B8], rcx
0x18000227f  mov     r15, r9
0x180002282  mov     [rsp+500h+var_4A8], r12
0x180002287  mov     r14, r8
0x18000228a  mov     [rsp+500h+hKey], r12
0x18000228f  lea     eax, ds:0FFFFFFFFFFFFFFFEh[rsi*2]
0x180002296  mov     [rsp+500h+var_4C0], r13
0x18000229b  mov     [rsp+500h+var_4B0], eax
0x18000229f  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\BidInterface\\Load"...
0x1800022a6  lea     rax, [rsp+500h+hKey]
0x1800022ab  mov     [rsp+500h+var_4AC], r12d
0x1800022b0  mov     rdi, rcx
0x1800022b3  mov     [rsp+500h+phkResult], rax; phkResult
0x1800022b8  mov     r9d, 20019h; samDesired
0x1800022be  mov     [rsp+500h+lpOutputString], rdx
0x1800022c3  xor     r8d, r8d; ulOptions
0x1800022c6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800022cd  call    cs:__imp_RegOpenKeyExW
0x1800022d3  test    eax, eax
0x1800022d5  jz      short loc_180002302
0x1800022d7  lea     rdx, [rsi-1]; SizeInWords
0x1800022db  mov     r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800022e2  mov     r8, r13; Source
0x1800022e5  mov     rcx, rdi; Destination
0x1800022e8  mov     rbx, rsi
0x1800022eb  call    cs:__imp_wcsncpy_s
0x1800022f1  mov     ecx, r12d
0x1800022f4  mov     dword ptr [rsp+500h+var_4A8], r12d
0x1800022f9  mov     [rsp+500h+var_4AC], ecx
0x1800022fd  jmp     loc_180002455
0x180002302  mov     rcx, [rsp+500h+hKey]; hKey
0x180002307  lea     rax, [rsp+500h+cbData]
0x18000230c  mov     [rsp+500h+lpcbData], rax; lpcbData
0x180002311  lea     r9, [rsp+500h+Type]; lpType
0x180002316  lea     rax, [rsp+500h+Data]
0x18000231b  mov     dword ptr [rsp+500h+Data], r12d
0x180002320  xor     r8d, r8d; lpReserved
0x180002323  mov     [rsp+500h+phkResult], rax; lpData
0x180002328  lea     rdx, ValueName; ":LdrMsg"
0x18000232f  mov     [rsp+500h+cbData], 4
0x180002337  mov     [rsp+500h+Type], r12d
0x18000233c  call    cs:__imp_RegQueryValueExW
0x180002342  test    eax, eax
0x180002344  jnz     short loc_18000235E
0x180002346  cmp     [rsp+500h+Type], 4
0x18000234b  jnz     short loc_18000235E
0x18000234d  cmp     dword ptr [rsp+500h+Data], r12d
0x180002352  mov     eax, r12d
0x180002355  setnz   al
0x180002358  mov     dword ptr [rsp+500h+var_4A8], eax
0x18000235c  jmp     short loc_180002363
0x18000235e  mov     dword ptr [rsp+500h+var_4A8], r12d
0x180002363  mov     r8d, 10Dh; nSize
0x180002369  lea     rdx, [rsp+500h+Filename]; lpFilename
0x18000236e  xor     ecx, ecx; hModule
0x180002370  call    cs:__imp_GetModuleFileNameW
0x180002376  mov     ebx, eax
0x180002378  lea     ecx, [rbx-1]
0x18000237b  cmp     ecx, 10Bh
0x180002381  ja      loc_18000243E
0x180002387  lea     rax, [rsp+500h+Filename]
0x18000238c  mov     word ptr [rbp+400h+var_276], r12w
0x180002394  lea     rcx, [rsp+500h+hKey]
0x180002399  mov     [rsp+500h+var_4C0], rax
0x18000239e  call    _bidLdrReadStr
0x1800023a3  test    eax, eax
0x1800023a5  jnz     loc_18000243E
0x1800023ab  lea     rcx, [rsp+rbx*2+500h+Data+2]
0x1800023b0  lea     rax, [rsp+500h+Filename]
0x1800023b5  cmp     rcx, rax
0x1800023b8  jb      short loc_180002403
0x1800023ba  nop     word ptr [rax+rax+00h]
0x1800023c0  movzx   eax, word ptr [rcx]
0x1800023c3  cmp     ax, 5Ch ; '\'
0x1800023c7  jz      short loc_1800023DF
0x1800023c9  cmp     ax, 2Fh ; '/'
0x1800023cd  jz      short loc_1800023DF
0x1800023cf  sub     rcx, 2
0x1800023d3  lea     rax, [rsp+500h+Filename]
0x1800023d8  cmp     rcx, rax
0x1800023db  jnb     short loc_1800023C0
0x1800023dd  jmp     short loc_180002403
0x1800023df  add     rcx, 2
0x1800023e3  lea     rax, [rbp+400h+var_276]
0x1800023ea  cmp     rcx, rax
0x1800023ed  jnb     short loc_180002403
0x1800023ef  mov     dword ptr [rcx], 2Ah ; '*'
0x1800023f5  lea     rcx, [rsp+500h+hKey]
0x1800023fa  call    _bidLdrReadStr
0x1800023ff  test    eax, eax
0x180002401  jnz     short loc_18000243E
0x180002403  lea     rax, aPath; ":Path"
0x18000240a  lea     rcx, [rsp+500h+hKey]
0x18000240f  mov     [rsp+500h+var_4C0], rax
0x180002414  call    _bidLdrReadStr
0x180002419  test    eax, eax
0x18000241b  jnz     short loc_18000243E
0x18000241d  lea     rdx, [rsi-1]; SizeInWords
0x180002421  mov     [rsp+500h+var_4C0], r13
0x180002426  mov     r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18000242d  mov     [rsp+500h+var_4AC], r12d
0x180002432  mov     r8, r13; Source
0x180002435  mov     rcx, rdi; Destination
0x180002438  call    cs:__imp_wcsncpy_s
0x18000243e  mov     rcx, [rsp+500h+hKey]; hKey
0x180002443  call    cs:__imp_RegCloseKey
0x180002449  mov     ecx, [rsp+500h+var_4AC]
0x18000244d  mov     rbx, rsi
0x180002450  mov     [rsp+500h+hKey], r12
0x180002455  mov     [rdi+rbx*2-2], r12w
0x18000245b  test    ecx, ecx
0x18000245d  jz      loc_18000257F
0x180002463  test    rdi, rdi
0x180002466  jz      loc_180002578
0x18000246c  cmp     rbx, 7FFFFFFFh
0x180002473  ja      loc_180002578
0x180002479  mov     rcx, rbx
0x18000247c  mov     rax, rdi
0x18000247f  test    rbx, rbx
0x180002482  jz      short loc_180002494
0x180002484  cmp     [rax], r12w
0x180002488  jz      short loc_180002494
0x18000248a  add     rax, 2
0x18000248e  sub     rcx, 1
0x180002492  jnz     short loc_180002484
0x180002494  mov     rax, rbx
0x180002497  mov     rdx, r12
0x18000249a  sub     rax, rcx
0x18000249d  test    rcx, rcx
0x1800024a0  cmovnz  rdx, rax
0x1800024a4  jz      loc_180002578
0x1800024aa  cmp     rdx, 3
0x1800024ae  jb      loc_180002578
0x1800024b4  movzx   eax, word ptr [rdi]
0x1800024b7  cmp     ax, 2Eh ; '.'
0x1800024bb  jz      short loc_1800024D8
0x1800024bd  cmp     ax, 5Ch ; '\'
0x1800024c1  jz      loc_180002557
0x1800024c7  cmp     ax, 2Fh ; '/'
0x1800024cb  jz      loc_180002557
0x1800024d1  cmp     word ptr [rdi+2], 3Ah ; ':'
0x1800024d6  jz      short loc_180002557
0x1800024d8  mov     qword ptr [rsp+500h+cbData], r12
0x1800024dd  cmp     ax, 2Eh ; '.'
0x1800024e1  jnz     short loc_1800024FF
0x1800024e3  lea     r9, [rsp+500h+cbData]; lpFilePart
0x1800024e8  mov     edx, 10Eh; nBufferLength
0x1800024ed  lea     r8, [rbp+400h+Buffer]; lpBuffer
0x1800024f4  mov     rcx, rdi; lpFileName
0x1800024f7  call    cs:__imp_GetFullPathNameW
0x1800024fd  jmp     short loc_180002529
0x1800024ff  lea     rax, [rsp+500h+cbData]
0x180002504  mov     r9d, 10Eh; nBufferLength
0x18000250a  mov     [rsp+500h+lpcbData], rax; lpFilePart
0x18000250f  xor     r8d, r8d; lpExtension
0x180002512  lea     rax, [rbp+400h+Buffer]
0x180002519  mov     rdx, rdi; lpFileName
0x18000251c  xor     ecx, ecx; lpPath
0x18000251e  mov     [rsp+500h+phkResult], rax; lpBuffer
0x180002523  call    cs:__imp_SearchPathW
0x180002529  dec     eax
0x18000252b  cmp     eax, 10Ch
0x180002530  ja      short loc_180002578
0x180002532  lfence
0x180002535  mov     r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18000253c  mov     [rbp+400h+var_56], r12w
0x180002544  lea     r8, [rbp+400h+Buffer]; Source
0x18000254b  mov     rdx, rbx; SizeInWords
0x18000254e  mov     rcx, rdi; Destination
0x180002551  call    cs:__imp_wcsncpy_s
0x180002557  movzx   ebx, word ptr [rdi+6]
0x18000255b  mov     rcx, rdi; lpRootPathName
0x18000255e  mov     [rdi+6], r12w
0x180002563  call    cs:__imp_GetDriveTypeW
0x180002569  mov     ecx, r12d
0x18000256c  mov     [rdi+6], bx
0x180002570  cmp     eax, 3
0x180002573  setz    cl
0x180002576  jmp     short loc_18000257B
0x180002578  mov     ecx, r12d
0x18000257b  mov     [rsp+500h+var_4AC], ecx
0x18000257f  cmp     dword ptr [rsp+500h+var_4A8], r12d
0x180002584  jz      short loc_1800025E9
0x180002586  lea     rcx, aHklm; "*** [HKLM\\"
0x18000258d  call    cs:__imp_OutputDebugStringW
0x180002593  mov     rcx, [rsp+500h+lpOutputString]; lpOutputString
0x180002598  call    cs:__imp_OutputDebugStringW
0x18000259e  lea     rcx, asc_1801B8698; "\\\""
0x1800025a5  call    cs:__imp_OutputDebugStringW
0x1800025ab  mov     rcx, [rsp+500h+var_4C0]; lpOutputString
0x1800025b0  call    cs:__imp_OutputDebugStringW
0x1800025b6  lea     rcx, asc_1801B86A0; "\"] \n*** \""
0x1800025bd  call    cs:__imp_OutputDebugStringW
0x1800025c3  mov     rcx, rdi; lpOutputString
0x1800025c6  call    cs:__imp_OutputDebugStringW
0x1800025cc  lea     rcx, asc_1801B86B4; "\"\n"
0x1800025d3  call    cs:__imp_OutputDebugStringW
0x1800025d9  mov     eax, dword ptr [rsp+500h+var_4A8]
0x1800025dd  mov     [r15], eax
0x1800025e0  mov     eax, [rsp+500h+var_4AC]
0x1800025e4  mov     [r14], eax
0x1800025e7  jmp     short loc_1800025F3
0x1800025e9  mov     eax, dword ptr [rsp+500h+var_4A8]
0x1800025ed  mov     [r15], eax
0x1800025f0  mov     [r14], ecx
0x1800025f3  mov     rcx, [rbp+400h+var_50]
0x1800025fa  xor     rcx, rsp; StackCookie
0x1800025fd  call    __security_check_cookie
0x180002602  add     rsp, 4C8h
0x180002609  pop     r15
0x18000260b  pop     r14
0x18000260d  pop     r13
0x18000260f  pop     r12
0x180002611  pop     rdi
0x180002612  pop     rsi
0x180002613  pop     rbx
0x180002614  pop     rbp
0x180002615  retn
```
