# DwGetCustomDllEntryPoint

- ea: `0x1800d0300`
- end: `0x1800d058a`
- name: `DwGetCustomDllEntryPoint`
- size: `650`
- prototype: `__int64 __fastcall(PCNZWCH lpString2, __int64, _DWORD *, FARPROC *, HMODULE *, int, WCHAR *hMem)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180096fa4`
- `0x1800d023c`

## callees

- `0x18000ada0`
- `0x1800289e0`
- `0x1800c09d0`
- `0x1800d0300`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800d0439`
- `msvcrt!wcscpy_s` at `0x1800d0439`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800d0414`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800d0414`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d0535`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d0544`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d0535`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d0544`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d04ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d04e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d04ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d04e6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800d0522`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800d0522`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d04d7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d04d7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d0498`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d0498`
- `rtutils!TracePrintfExA` at `0x1800d0375`
- `rtutils!TracePrintfExA` at `0x1800d050c`
- `rtutils!TracePrintfExA` at `0x1800d0571`
- `rtutils!TracePrintfExA` at `0x1800d0375`
- `rtutils!TracePrintfExA` at `0x1800d050c`
- `rtutils!TracePrintfExA` at `0x1800d0571`
- `rasman!RasIsTrustedCustomDll` at `0x1800d0457`
- `rasman!RasIsTrustedCustomDll` at `0x1800d0457`

## string_xrefs

- `0x1800d04c3`: `LoadLibrary %ws failed. %d`
- `0x1800d036a`: `DwGetCustomDllEntryPoints..`
- `0x1800d0347`: `RasCustomDeleteEntryNotify`
- `0x1800d0565`: `DwGetCustomDllEntryPoints done. %d`

## pseudocode

```c
__int64 __fastcall DwGetCustomDllEntryPoint(
        PCNZWCH lpString2,
        __int64 a2,
        _DWORD *a3,
        FARPROC *a4,
        HMODULE *a5,
        int a6,
        WCHAR *hMem)
{
  WCHAR *v10; // r15
  __int64 v11; // r14
  WCHAR *v13; // rax
  WCHAR *v14; // rdi
  unsigned int EntryFromSystem; // eax
  unsigned int v16; // ebx
  __int64 v17; // rbx
  _WORD *v18; // rcx
  __int64 v19; // rax
  rsize_t v20; // r12
  wchar_t *v21; // rax
  unsigned int ExpandedDllPath; // eax
  HMODULE Library; // rcx
  DWORD LastError; // eax
  DWORD v25; // ecx
  void *v26; // r9
  const CHAR *v27; // r8
  const CHAR *v28; // rsi
  FARPROC ProcAddress; // rax
  HMODULE *v30; // rsi
  __int64 v31; // [rsp+20h] [rbp-48h]
  __int64 v32; // [rsp+30h] [rbp-38h] BYREF
  LPCWSTR lpLibFileName; // [rsp+38h] [rbp-30h]
  LPCSTR lpProcName[5]; // [rsp+40h] [rbp-28h]
  int v35; // [rsp+C8h] [rbp+60h] BYREF

  lpProcName[0] = "RasCustomDialDlg";
  lpLibFileName = 0;
  lpProcName[1] = "RasCustomEntryDlg";
  lpProcName[2] = "RasCustomDial";
  lpProcName[3] = "RasCustomDeleteEntryNotify";
  v35 = 0;
  v32 = 0;
  v10 = 0;
  v11 = 0;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "DwGetCustomDllEntryPoints..");
  if ( !a4 )
    return 87;
  v13 = hMem;
  *a4 = 0;
  v14 = v13;
  if ( a3 )
    *a3 = 0;
  if ( !v13 )
  {
    EntryFromSystem = ReadEntryFromSystem(lpString2, (__int64)&v32, 0);
    v11 = v32;
    v16 = EntryFromSystem;
    if ( EntryFromSystem )
      goto LABEL_32;
    v17 = *(_QWORD *)(v32 + 16);
    if ( !v17 )
    {
      v16 = 623;
      goto LABEL_32;
    }
    v18 = *(_WORD **)(v17 + 448);
    if ( !v18 || !*v18 )
    {
      v16 = 13;
      goto LABEL_32;
    }
    v19 = -1;
    do
      ++v19;
    while ( v18[v19] );
    v20 = v19 + 1;
    v21 = (wchar_t *)LocalAlloc(0x40u, 2 * (v19 + 1));
    v14 = v21;
    if ( !v21 || wcscpy_s(v21, v20, *(const wchar_t **)(v17 + 448)) )
    {
      v16 = 8;
      goto LABEL_32;
    }
  }
  if ( a3 )
    *a3 = 1;
  RasIsTrustedCustomDll(0, v14, &v35);
  if ( !v35 )
  {
    v16 = 5;
    goto LABEL_32;
  }
  ExpandedDllPath = DwGetExpandedDllPath(v14);
  v10 = (WCHAR *)lpLibFileName;
  v16 = ExpandedDllPath;
  if ( ExpandedDllPath )
  {
LABEL_32:
    v30 = a5;
    if ( *a5 )
    {
      FreeLibrary(*a5);
      *v30 = 0;
    }
    goto LABEL_34;
  }
  Library = LoadLibraryExW(lpLibFileName, 0, 0);
  *a5 = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    v25 = g_dwTraceId;
    v16 = LastError;
    if ( g_dwTraceId == -1 )
      goto LABEL_31;
    v26 = v14;
    v27 = "LoadLibrary %ws failed. %d";
    goto LABEL_30;
  }
  v28 = lpProcName[a6];
  ProcAddress = GetProcAddress(Library, v28);
  *a4 = ProcAddress;
  if ( ProcAddress )
    goto LABEL_34;
  LastError = GetLastError();
  v25 = g_dwTraceId;
  v16 = LastError;
  if ( g_dwTraceId != -1 )
  {
    v26 = (void *)v28;
    v27 = "GetProcAddress %s failed. %d";
LABEL_30:
    LODWORD(v31) = LastError;
    TracePrintfExA(v25, 0xCu, v27, v26, v31);
  }
LABEL_31:
  if ( v16 )
    goto LABEL_32;
LABEL_34:
  if ( v10 )
    LocalFree(v10);
  if ( v14 != hMem )
    LocalFree(v14);
  if ( v11 )
    DestroyEntryNode(v11);
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "DwGetCustomDllEntryPoints done. %d", v16);
  return v16;
}

```

## disassembly

```asm
0x1800d0300  push    rbp
0x1800d0302  push    rbx
0x1800d0303  push    rsi
0x1800d0304  push    rdi
0x1800d0305  push    r12
0x1800d0307  push    r13
0x1800d0309  push    r14
0x1800d030b  push    r15
0x1800d030d  mov     rbp, rsp
0x1800d0310  sub     rsp, 68h
0x1800d0314  lea     rax, aRascustomdiald; "RasCustomDialDlg"
0x1800d031b  mov     rbx, rdx
0x1800d031e  xor     edx, edx
0x1800d0320  mov     [rbp+lpProcName], rax
0x1800d0324  lea     rax, aRascustomentry; "RasCustomEntryDlg"
0x1800d032b  mov     [rbp+lpLibFileName], rdx
0x1800d032f  mov     [rbp+var_20], rax
0x1800d0333  mov     r12, rcx
0x1800d0336  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800d033c  lea     rax, aRascustomdial; "RasCustomDial"
0x1800d0343  mov     [rbp+var_18], rax
0x1800d0347  lea     rax, aRascustomdelet; "RasCustomDeleteEntryNotify"
0x1800d034e  mov     [rbp+var_10], rax
0x1800d0352  mov     r13, r9
0x1800d0355  mov     [rbp+arg_18], edx
0x1800d0358  mov     rsi, r8
0x1800d035b  mov     [rbp+var_38], rdx
0x1800d035f  mov     r15d, edx
0x1800d0362  mov     r14d, edx
0x1800d0365  cmp     ecx, 0FFFFFFFFh
0x1800d0368  jz      short loc_1800D037D
0x1800d036a  lea     r8, aDwgetcustomdll_0; "DwGetCustomDllEntryPoints.."
0x1800d0371  lea     edx, [r14+0Ch]; dwFlags
0x1800d0375  call    cs:__imp_TracePrintfExA
0x1800d037b  xor     edx, edx
0x1800d037d  test    r13, r13
0x1800d0380  jnz     short loc_1800D038B
0x1800d0382  lea     eax, [r13+57h]
0x1800d0386  jmp     loc_1800D0579
0x1800d038b  mov     rax, [rbp+hMem]
0x1800d038f  mov     [r13+0], rdx
0x1800d0393  mov     rdi, rax
0x1800d0396  test    rsi, rsi
0x1800d0399  jz      short loc_1800D039D
0x1800d039b  mov     [rsi], edx
0x1800d039d  test    rax, rax
0x1800d03a0  jnz     loc_1800D0443
0x1800d03a6  mov     [rsp+68h+var_40], rdx; __int64
0x1800d03ab  lea     rax, [rbp+var_38]
0x1800d03af  xor     r9d, r9d
0x1800d03b2  mov     [rsp+68h+var_48], rax; __int64
0x1800d03b7  mov     rdx, rbx
0x1800d03ba  mov     rcx, r12; lpString2
0x1800d03bd  lea     r8d, [r9+8]
0x1800d03c1  call    ReadEntryFromSystem
0x1800d03c6  mov     r14, [rbp+var_38]
0x1800d03ca  xor     edx, edx
0x1800d03cc  mov     ebx, eax
0x1800d03ce  test    eax, eax
0x1800d03d0  jnz     loc_1800D0516
0x1800d03d6  mov     rbx, [r14+10h]
0x1800d03da  test    rbx, rbx
0x1800d03dd  jnz     short loc_1800D03E9
0x1800d03df  mov     ebx, 26Fh
0x1800d03e4  jmp     loc_1800D0516
0x1800d03e9  mov     rcx, [rbx+1C0h]
0x1800d03f0  test    rcx, rcx
0x1800d03f3  jz      short loc_1800D046C
0x1800d03f5  cmp     dx, [rcx]
0x1800d03f8  jz      short loc_1800D046C
0x1800d03fa  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d03fe  inc     rax
0x1800d0401  cmp     [rcx+rax*2], dx
0x1800d0405  jnz     short loc_1800D03FE
0x1800d0407  lea     r12, [rax+1]
0x1800d040b  mov     ecx, 40h ; '@'; uFlags
0x1800d0410  lea     rdx, [r12+r12]; uBytes
0x1800d0414  call    cs:__imp_LocalAlloc
0x1800d041a  mov     rdi, rax
0x1800d041d  test    rax, rax
0x1800d0420  jnz     short loc_1800D042C
0x1800d0422  mov     ebx, 8
0x1800d0427  jmp     loc_1800D0516
0x1800d042c  mov     r8, [rbx+1C0h]; Source
0x1800d0433  mov     rdx, r12; SizeInWords
0x1800d0436  mov     rcx, rax; Destination
0x1800d0439  call    cs:__imp_wcscpy_s
0x1800d043f  test    eax, eax
0x1800d0441  jnz     short loc_1800D0422
0x1800d0443  test    rsi, rsi
0x1800d0446  jz      short loc_1800D044E
0x1800d0448  mov     dword ptr [rsi], 1
0x1800d044e  lea     r8, [rbp+arg_18]
0x1800d0452  mov     rdx, rdi
0x1800d0455  xor     ecx, ecx
0x1800d0457  call    cs:__imp_RasIsTrustedCustomDll
0x1800d045d  xor     edx, edx
0x1800d045f  cmp     [rbp+arg_18], edx
0x1800d0462  jnz     short loc_1800D0476
0x1800d0464  lea     ebx, [rdx+5]
0x1800d0467  jmp     loc_1800D0516
0x1800d046c  mov     ebx, 0Dh
0x1800d0471  jmp     loc_1800D0516
0x1800d0476  lea     rdx, [rbp+lpLibFileName]
0x1800d047a  mov     rcx, rdi; lpSrc
0x1800d047d  call    DwGetExpandedDllPath
0x1800d0482  mov     r15, [rbp+lpLibFileName]
0x1800d0486  xor     edx, edx; hFile
0x1800d0488  mov     ebx, eax
0x1800d048a  test    eax, eax
0x1800d048c  jnz     loc_1800D0516
0x1800d0492  xor     r8d, r8d; dwFlags
0x1800d0495  mov     rcx, r15; lpLibFileName
0x1800d0498  call    cs:__imp_LoadLibraryExW
0x1800d049e  mov     rcx, rax; hModule
0x1800d04a1  mov     rax, [rbp+arg_20]
0x1800d04a5  mov     [rax], rcx
0x1800d04a8  test    rcx, rcx
0x1800d04ab  jnz     short loc_1800D04CC
0x1800d04ad  call    cs:__imp_GetLastError
0x1800d04b3  mov     ecx, cs:g_dwTraceId
0x1800d04b9  mov     ebx, eax
0x1800d04bb  cmp     ecx, 0FFFFFFFFh
0x1800d04be  jz      short loc_1800D0512
0x1800d04c0  mov     r9, rdi
0x1800d04c3  lea     r8, aLoadlibraryWsF; "LoadLibrary %ws failed. %d"
0x1800d04ca  jmp     short loc_1800D0503
0x1800d04cc  mov     eax, [rbp+arg_28]
0x1800d04cf  mov     rsi, [rbp+rax*8+lpProcName]
0x1800d04d4  mov     rdx, rsi; lpProcName
0x1800d04d7  call    cs:__imp_GetProcAddress
0x1800d04dd  mov     [r13+0], rax
0x1800d04e1  test    rax, rax
0x1800d04e4  jnz     short loc_1800D052D
0x1800d04e6  call    cs:__imp_GetLastError
0x1800d04ec  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800d04f2  mov     ebx, eax
0x1800d04f4  cmp     ecx, 0FFFFFFFFh
0x1800d04f7  jz      short loc_1800D0512
0x1800d04f9  mov     r9, rsi
0x1800d04fc  lea     r8, aGetprocaddress; "GetProcAddress %s failed. %d"
0x1800d0503  mov     edx, 0Ch; dwFlags
0x1800d0508  mov     dword ptr [rsp+68h+var_48], eax
0x1800d050c  call    cs:__imp_TracePrintfExA
0x1800d0512  test    ebx, ebx
0x1800d0514  jz      short loc_1800D052D
0x1800d0516  mov     rsi, [rbp+arg_20]
0x1800d051a  mov     rcx, [rsi]; hLibModule
0x1800d051d  test    rcx, rcx
0x1800d0520  jz      short loc_1800D052D
0x1800d0522  call    cs:__imp_FreeLibrary
0x1800d0528  xor     edx, edx
0x1800d052a  mov     [rsi], rdx
0x1800d052d  test    r15, r15
0x1800d0530  jz      short loc_1800D053B
0x1800d0532  mov     rcx, r15; hMem
0x1800d0535  call    cs:__imp_LocalFree
0x1800d053b  cmp     rdi, [rbp+hMem]
0x1800d053f  jz      short loc_1800D054A
0x1800d0541  mov     rcx, rdi; hMem
0x1800d0544  call    cs:__imp_LocalFree
0x1800d054a  test    r14, r14
0x1800d054d  jz      short loc_1800D0557
0x1800d054f  mov     rcx, r14
0x1800d0552  call    DestroyEntryNode
0x1800d0557  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800d055d  cmp     ecx, 0FFFFFFFFh
0x1800d0560  jz      short loc_1800D0577
0x1800d0562  mov     r9d, ebx
0x1800d0565  lea     r8, aDwgetcustomdll_1; "DwGetCustomDllEntryPoints done. %d"
0x1800d056c  mov     edx, 0Ch; dwFlags
0x1800d0571  call    cs:__imp_TracePrintfExA
0x1800d0577  mov     eax, ebx
0x1800d0579  add     rsp, 68h
0x1800d057d  pop     r15
0x1800d057f  pop     r14
0x1800d0581  pop     r13
0x1800d0583  pop     r12
0x1800d0585  pop     rdi
0x1800d0586  pop     rsi
0x1800d0587  pop     rbx
0x1800d0588  pop     rbp
0x1800d0589  retn
```
