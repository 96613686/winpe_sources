# DirectUI::CallstackTracker::InitializeDllInfo(void)

- ea: `0x18018c0d0`
- end: `0x18018c267`
- name: `?InitializeDllInfo@CallstackTracker@DirectUI@@CAHXZ`
- size: `407`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, loader_planting`

## callers

- `0x18018c080`

## callees

- `0x1800ee134`
- `0x180114520`
- `0x180114ac0`
- `0x180114ebc`
- `0x18018c0d0`
- `0x18018c270`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18018c195`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18018c227`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18018c195`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18018c227`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18018c0f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18018c0f1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18018c11c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18018c11c`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18018c169`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18018c20b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18018c169`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18018c20b`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18018c156`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18018c1fc`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18018c156`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18018c1fc`

## string_xrefs

- `0x18018c1e8`: `\ntdll.dll`
- `0x18018c148`: `\imagehlp.dll`

## pseudocode

```c
__int64 DirectUI::CallstackTracker::InitializeDllInfo(void)
{
  unsigned int IsCorrectImageHlpVersion; // ebx
  HMODULE LibraryW; // rax
  int v2; // edi
  HMODULE v3; // rax
  unsigned __int64 v5; // [rsp+20h] [rbp-258h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-248h] BYREF

  IsCorrectImageHlpVersion = 0;
  DirectUI::CallstackTracker::s_hProcess = GetCurrentProcess();
  memset_0(Buffer, 0, 0x208u);
  if ( GetSystemDirectoryW(Buffer, 0x104u) )
  {
    v5 = 0;
    if ( (int)StringCchLengthW(Buffer, 0x104u, &v5) >= 0 && PathCchAppend(Buffer, 0x104u, L"\\imagehlp.dll") >= 0 )
    {
      LibraryW = LoadLibraryW(Buffer);
      DirectUI::CallstackTracker::s_hinstImageHlp = LibraryW;
      if ( LibraryW )
      {
        v2 = 0;
        while ( 1 )
        {
          *(_QWORD *)*(&DirectUI::CallstackTracker::s_ImageHlpFuncList + 2 * v2 + 1) = GetProcAddress(
                                                                                         LibraryW,
                                                                                         (LPCSTR)*(&DirectUI::CallstackTracker::s_ImageHlpFuncList
                                                                                                 + 2 * v2));
          if ( !*(_QWORD *)*(&DirectUI::CallstackTracker::s_ImageHlpFuncList + 2 * v2 + 1) )
            return 0;
          if ( (unsigned int)++v2 >= 6 )
            break;
          LibraryW = DirectUI::CallstackTracker::s_hinstImageHlp;
        }
        IsCorrectImageHlpVersion = DirectUI::CallstackTracker::IsCorrectImageHlpVersion();
        if ( IsCorrectImageHlpVersion )
        {
          IsCorrectImageHlpVersion = 0;
          if ( v5 )
          {
            if ( 2 * v5 >= 0x208 )
              _report_rangecheckfailure();
            Buffer[v5] = 0;
            if ( PathCchAppend(Buffer, 0x104u, L"\\ntdll.dll") >= 0 )
            {
              v3 = LoadLibraryW(Buffer);
              DirectUI::CallstackTracker::s_hinstNtDll = v3;
              if ( v3 )
              {
                DirectUI::CallstackTracker::s_pfnRtlCaptureStackBackTrace = (unsigned __int16 (*)(unsigned int, unsigned int, void **, unsigned int *))GetProcAddress(v3, "RtlCaptureStackBackTrace");
                return DirectUI::CallstackTracker::s_pfnRtlCaptureStackBackTrace != 0;
              }
            }
          }
        }
      }
    }
  }
  return IsCorrectImageHlpVersion;
}

```

## disassembly

```asm
0x18018c0d0  push    rbx
0x18018c0d2  push    rsi
0x18018c0d3  push    rdi
0x18018c0d4  push    r14
0x18018c0d6  sub     rsp, 258h
0x18018c0dd  mov     rax, cs:__security_cookie
0x18018c0e4  xor     rax, rsp
0x18018c0e7  mov     [rsp+278h+var_38], rax
0x18018c0ef  xor     ebx, ebx
0x18018c0f1  call    cs:__imp_GetCurrentProcess
0x18018c0f7  xor     edx, edx; Val
0x18018c0f9  lea     rcx, [rsp+278h+Buffer]; void *
0x18018c0fe  mov     r8d, 208h; Size
0x18018c104  mov     cs:?s_hProcess@CallstackTracker@DirectUI@@0PEAXEA, rax; void * DirectUI::CallstackTracker::s_hProcess
0x18018c10b  call    memset_0
0x18018c110  mov     esi, 104h
0x18018c115  lea     rcx, [rsp+278h+Buffer]; lpBuffer
0x18018c11a  mov     edx, esi; uSize
0x18018c11c  call    cs:__imp_GetSystemDirectoryW
0x18018c122  test    eax, eax
0x18018c124  jz      loc_18018C242
0x18018c12a  lea     r8, [rsp+278h+var_258]; unsigned __int64 *
0x18018c12f  mov     [rsp+278h+var_258], rbx
0x18018c134  mov     edx, esi; unsigned __int64
0x18018c136  lea     rcx, [rsp+278h+Buffer]; unsigned __int16 *
0x18018c13b  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18018c140  test    eax, eax
0x18018c142  js      loc_18018C242
0x18018c148  lea     r8, aImagehlpDll; "\\imagehlp.dll"
0x18018c14f  mov     edx, esi; cchPath
0x18018c151  lea     rcx, [rsp+278h+Buffer]; pszPath
0x18018c156  call    cs:__imp_PathCchAppend
0x18018c15c  test    eax, eax
0x18018c15e  js      loc_18018C242
0x18018c164  lea     rcx, [rsp+278h+Buffer]; lpLibFileName
0x18018c169  call    cs:__imp_LoadLibraryW
0x18018c16f  mov     cs:?s_hinstImageHlp@CallstackTracker@DirectUI@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * DirectUI::CallstackTracker::s_hinstImageHlp
0x18018c176  test    rax, rax
0x18018c179  jz      loc_18018C242
0x18018c17f  xor     edi, edi
0x18018c181  lea     r14, ?s_ImageHlpFuncList@CallstackTracker@DirectUI@@0PAUIMGHLPFN_LOAD@12@A; DirectUI::CallstackTracker::IMGHLPFN_LOAD near * DirectUI::CallstackTracker::s_ImageHlpFuncList
0x18018c188  movsxd  rbx, edi
0x18018c18b  mov     rcx, rax; hModule
0x18018c18e  add     rbx, rbx
0x18018c191  mov     rdx, [r14+rbx*8]; lpProcName
0x18018c195  call    cs:__imp_GetProcAddress
0x18018c19b  mov     rcx, [r14+rbx*8+8]
0x18018c1a0  mov     [rcx], rax
0x18018c1a3  mov     rax, [r14+rbx*8+8]
0x18018c1a8  cmp     qword ptr [rax], 0
0x18018c1ac  jz      loc_18018C240
0x18018c1b2  inc     edi
0x18018c1b4  cmp     edi, 6
0x18018c1b7  jnb     short loc_18018C1C2
0x18018c1b9  mov     rax, cs:?s_hinstImageHlp@CallstackTracker@DirectUI@@0PEAUHINSTANCE__@@EA; HINSTANCE__ * DirectUI::CallstackTracker::s_hinstImageHlp
0x18018c1c0  jmp     short loc_18018C188
0x18018c1c2  call    ?IsCorrectImageHlpVersion@CallstackTracker@DirectUI@@CAHXZ; DirectUI::CallstackTracker::IsCorrectImageHlpVersion(void)
0x18018c1c7  mov     ebx, eax
0x18018c1c9  test    eax, eax
0x18018c1cb  jz      short loc_18018C242
0x18018c1cd  mov     rax, [rsp+278h+var_258]
0x18018c1d2  xor     ebx, ebx
0x18018c1d4  test    rax, rax
0x18018c1d7  jz      short loc_18018C242
0x18018c1d9  lea     rcx, [rax+rax]
0x18018c1dd  cmp     rcx, 208h
0x18018c1e4  jnb     short loc_18018C261
0x18018c1e6  xor     eax, eax
0x18018c1e8  lea     r8, aNtdllDll_0; "\\ntdll.dll"
0x18018c1ef  mov     [rsp+rcx+278h+Buffer], ax
0x18018c1f4  mov     rdx, rsi; cchPath
0x18018c1f7  lea     rcx, [rsp+278h+Buffer]; pszPath
0x18018c1fc  call    cs:__imp_PathCchAppend
0x18018c202  test    eax, eax
0x18018c204  js      short loc_18018C242
0x18018c206  lea     rcx, [rsp+278h+Buffer]; lpLibFileName
0x18018c20b  call    cs:__imp_LoadLibraryW
0x18018c211  mov     cs:?s_hinstNtDll@CallstackTracker@DirectUI@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * DirectUI::CallstackTracker::s_hinstNtDll
0x18018c218  test    rax, rax
0x18018c21b  jz      short loc_18018C242
0x18018c21d  lea     rdx, aRtlcapturestac; "RtlCaptureStackBackTrace"
0x18018c224  mov     rcx, rax; hModule
0x18018c227  call    cs:__imp_GetProcAddress
0x18018c22d  mov     cs:?s_pfnRtlCaptureStackBackTrace@CallstackTracker@DirectUI@@0P6AGKKPEAPEAXPEAK@ZEA, rax; ushort (*DirectUI::CallstackTracker::s_pfnRtlCaptureStackBackTrace)(ulong,ulong,void * *,ulong *)
0x18018c234  test    rax, rax
0x18018c237  jz      short loc_18018C242
0x18018c239  mov     ebx, 1
0x18018c23e  jmp     short loc_18018C242
0x18018c240  xor     ebx, ebx
0x18018c242  mov     eax, ebx
0x18018c244  mov     rcx, [rsp+278h+var_38]
0x18018c24c  xor     rcx, rsp; StackCookie
0x18018c24f  call    __security_check_cookie
0x18018c254  add     rsp, 258h
0x18018c25b  pop     r14
0x18018c25d  pop     rdi
0x18018c25e  pop     rsi
0x18018c25f  pop     rbx
0x18018c260  retn
0x18018c261  call    __report_rangecheckfailure
```
