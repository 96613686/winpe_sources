# PbkPathInfoLoad

- ea: `0x1800845b0`
- end: `0x1800848e8`
- name: `PbkPathInfoLoad`
- size: `824`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x18007e5ac`
- `0x18007fdec`
- `0x1800803c0`
- `0x180083b18`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18005fe20`
- `0x18006d4c4`
- `0x1800845b0`
- `0x1800848f0`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084822`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084822`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800845f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800845f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008489f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008489f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800846be`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800846df`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800846be`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800846df`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180084702`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008471d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180084738`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180084702`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008471d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180084738`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180084616`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180084633`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180084836`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180084853`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008486f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180084890`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180084616`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180084633`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180084836`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180084853`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008486f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180084890`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180084655`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180084669`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18008467d`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180084655`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180084669`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18008467d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800847e1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800847e1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800847a0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800847c2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800847a0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800847c2`

## string_xrefs

- `0x1800846b2`: `api-ms-win-core-shlwapi-legacy-l1-1-0.dll`
- `0x1800846d6`: `shlwapi.dll`
- `0x180084712`: `PathRemoveFileSpecW`
- `0x1800846f8`: `PathCanonicalizeW`
- `0x18008472d`: `PathFindFileNameW`
- `0x1800847f5`: `\System32\Ras`

## pseudocode

```c
__int64 __fastcall PbkPathInfoLoad(LPCRITICAL_SECTION lpCriticalSection)
{
  DWORD LastError; // ebx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  void *v4; // rcx
  wchar_t *v5; // rax
  PRTL_CRITICAL_SECTION_DEBUG v6; // rcx
  wchar_t *v7; // rsi
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  HMODULE v10; // rcx
  FARPROC v11; // rax
  HMODULE v12; // rcx
  FARPROC v13; // rax
  bool v14; // zf
  PRTL_CRITICAL_SECTION_DEBUG v15; // rbx
  PRTL_CRITICAL_SECTION_DEBUG v16; // rbx
  STRSAFE_LPWSTR *v17; // r9
  HRESULT v18; // eax
  void *v19; // rcx
  size_t *v21; // [rsp+20h] [rbp-38h]

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 82, WPP_38cda081c674317ed40163d707084d83_Traceguids);
  }
  EnterCriticalSection(lpCriticalSection);
  if ( !HIDWORD(lpCriticalSection[1].DebugInfo) )
  {
    DebugInfo = lpCriticalSection[2].DebugInfo;
    if ( DebugInfo )
    {
      GlobalFree(DebugInfo);
      lpCriticalSection[2].DebugInfo = 0;
    }
    v4 = *(void **)&lpCriticalSection[2].LockCount;
    if ( v4 )
    {
      GlobalFree(v4);
      *(_QWORD *)&lpCriticalSection[2].LockCount = 0;
    }
    lpCriticalSection[2].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)GlobalAlloc(0x40u, 0x20Au);
    *(_QWORD *)&lpCriticalSection[2].LockCount = GlobalAlloc(0x40u, 0x20Au);
    v5 = (wchar_t *)GlobalAlloc(0x40u, 0x20Au);
    v6 = lpCriticalSection[2].DebugInfo;
    v7 = v5;
    if ( v6 )
    {
      if ( *(_QWORD *)&lpCriticalSection[2].LockCount && v5 )
      {
        Library = LoadLibraryExW(L"api-ms-win-core-shlwapi-legacy-l1-1-0.dll", 0, 0x800u);
        *(_QWORD *)&lpCriticalSection[1].LockCount = Library;
        if ( !Library )
        {
          Library = LoadLibraryExW(L"shlwapi.dll", 0, 0x800u);
          *(_QWORD *)&lpCriticalSection[1].LockCount = Library;
          if ( !Library )
            goto LABEL_28;
        }
        ProcAddress = GetProcAddress(Library, "PathCanonicalizeW");
        v10 = *(HMODULE *)&lpCriticalSection[1].LockCount;
        lpCriticalSection[1].OwningThread = ProcAddress;
        v11 = GetProcAddress(v10, "PathRemoveFileSpecW");
        v12 = *(HMODULE *)&lpCriticalSection[1].LockCount;
        lpCriticalSection[1].LockSemaphore = v11;
        v13 = GetProcAddress(v12, "PathFindFileNameW");
        v14 = lpCriticalSection[1].OwningThread == 0;
        lpCriticalSection[1].SpinCount = (ULONG_PTR)v13;
        if ( v14 || !lpCriticalSection[1].LockSemaphore || !v13 )
          goto LABEL_28;
        if ( (unsigned int)GetPhonebookDirectory(0, v7)
          && ((unsigned int (__fastcall *)(PRTL_CRITICAL_SECTION_DEBUG, wchar_t *))lpCriticalSection[1].OwningThread)(
               lpCriticalSection[2].DebugInfo,
               v7) )
        {
          v15 = lpCriticalSection[2].DebugInfo;
          if ( *((_WORD *)v15 + lstrlenW(&v15->Type) - 1) == 92 )
          {
            v16 = lpCriticalSection[2].DebugInfo;
            *((_WORD *)v16 + lstrlenW(&v16->Type) - 1) = 0;
          }
          if ( GetSystemWindowsDirectoryW(*(LPWSTR *)&lpCriticalSection[2].LockCount, 0xF6u) )
          {
            v18 = StringCchCatExW(
                    *(STRSAFE_LPWSTR *)&lpCriticalSection[2].LockCount,
                    0x105u,
                    L"\\System32\\Ras",
                    v17,
                    v21,
                    0x100u);
            if ( v18 >= 0 )
            {
              LastError = 0;
              HIDWORD(lpCriticalSection[1].DebugInfo) = 1;
              goto LABEL_38;
            }
            LastError = (unsigned __int16)v18;
            goto LABEL_29;
          }
LABEL_28:
          LastError = GetLastError();
LABEL_29:
          if ( !LastError )
            goto LABEL_38;
          goto LABEL_37;
        }
        LastError = 1003;
LABEL_37:
        PbkPathInfoReset(lpCriticalSection);
        if ( !v7 )
          goto LABEL_39;
LABEL_38:
        GlobalFree(v7);
        goto LABEL_39;
      }
      GlobalFree(v6);
    }
    v19 = *(void **)&lpCriticalSection[2].LockCount;
    lpCriticalSection[2].DebugInfo = 0;
    if ( v19 )
      GlobalFree(v19);
    *(_QWORD *)&lpCriticalSection[2].LockCount = 0;
    if ( v7 )
      GlobalFree(v7);
    v7 = 0;
    LastError = 8;
    goto LABEL_37;
  }
  LastError = 0;
LABEL_39:
  LeaveCriticalSection(lpCriticalSection);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 83, WPP_38cda081c674317ed40163d707084d83_Traceguids, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800845b0  push    rbx
0x1800845b2  push    rsi
0x1800845b3  push    rdi
0x1800845b4  push    r15
0x1800845b6  sub     rsp, 38h
0x1800845ba  mov     rdi, rcx
0x1800845bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800845c4  lea     r15, WPP_GLOBAL_Control
0x1800845cb  cmp     rcx, r15
0x1800845ce  jz      short loc_1800845F1
0x1800845d0  test    byte ptr [rcx+1Ch], 80h
0x1800845d4  jz      short loc_1800845F1
0x1800845d6  cmp     byte ptr [rcx+19h], 6
0x1800845da  jb      short loc_1800845F1
0x1800845dc  mov     rcx, [rcx+10h]
0x1800845e0  lea     r8, WPP_38cda081c674317ed40163d707084d83_Traceguids
0x1800845e7  mov     edx, 52h ; 'R'
0x1800845ec  call    WPP_SF_
0x1800845f1  mov     rcx, rdi; lpCriticalSection
0x1800845f4  call    cs:__imp_EnterCriticalSection
0x1800845fb  nop     dword ptr [rax+rax+00h]
0x180084600  cmp     dword ptr [rdi+2Ch], 0
0x180084604  jz      short loc_18008460D
0x180084606  xor     ebx, ebx
0x180084608  jmp     loc_18008489C
0x18008460d  mov     rcx, [rdi+50h]; hMem
0x180084611  test    rcx, rcx
0x180084614  jz      short loc_18008462A
0x180084616  call    cs:__imp_GlobalFree
0x18008461d  nop     dword ptr [rax+rax+00h]
0x180084622  mov     qword ptr [rdi+50h], 0
0x18008462a  mov     rcx, [rdi+58h]; hMem
0x18008462e  test    rcx, rcx
0x180084631  jz      short loc_180084647
0x180084633  call    cs:__imp_GlobalFree
0x18008463a  nop     dword ptr [rax+rax+00h]
0x18008463f  mov     qword ptr [rdi+58h], 0
0x180084647  mov     esi, 20Ah
0x18008464c  mov     ebx, 40h ; '@'
0x180084651  mov     edx, esi; dwBytes
0x180084653  mov     ecx, ebx; uFlags
0x180084655  call    cs:__imp_GlobalAlloc
0x18008465c  nop     dword ptr [rax+rax+00h]
0x180084661  mov     edx, esi; dwBytes
0x180084663  mov     ecx, ebx; uFlags
0x180084665  mov     [rdi+50h], rax
0x180084669  call    cs:__imp_GlobalAlloc
0x180084670  nop     dword ptr [rax+rax+00h]
0x180084675  mov     edx, esi; dwBytes
0x180084677  mov     ecx, ebx; uFlags
0x180084679  mov     [rdi+58h], rax
0x18008467d  call    cs:__imp_GlobalAlloc
0x180084684  nop     dword ptr [rax+rax+00h]
0x180084689  mov     rcx, [rdi+50h]; hMem
0x18008468d  mov     rsi, rax
0x180084690  test    rcx, rcx
0x180084693  jz      loc_180084842
0x180084699  cmp     qword ptr [rdi+58h], 0
0x18008469e  jz      loc_180084836
0x1800846a4  test    rax, rax
0x1800846a7  jz      loc_180084836
0x1800846ad  mov     ebx, 800h
0x1800846b2  lea     rcx, aApiMsWinCoreSh_0; "api-ms-win-core-shlwapi-legacy-l1-1-0.d"...
0x1800846b9  mov     r8d, ebx; dwFlags
0x1800846bc  xor     edx, edx; hFile
0x1800846be  call    cs:__imp_LoadLibraryExW
0x1800846c5  nop     dword ptr [rax+rax+00h]
0x1800846ca  mov     [rdi+30h], rax
0x1800846ce  test    rax, rax
0x1800846d1  jnz     short loc_1800846F8
0x1800846d3  mov     r8d, ebx; dwFlags
0x1800846d6  lea     rcx, aShlwapiDll; "shlwapi.dll"
0x1800846dd  xor     edx, edx; hFile
0x1800846df  call    cs:__imp_LoadLibraryExW
0x1800846e6  nop     dword ptr [rax+rax+00h]
0x1800846eb  mov     [rdi+30h], rax
0x1800846ef  test    rax, rax
0x1800846f2  jz      loc_180084822
0x1800846f8  lea     rdx, aPathcanonicali; "PathCanonicalizeW"
0x1800846ff  mov     rcx, rax; hModule
0x180084702  call    cs:__imp_GetProcAddress
0x180084709  nop     dword ptr [rax+rax+00h]
0x18008470e  mov     rcx, [rdi+30h]; hModule
0x180084712  lea     rdx, aPathremovefile; "PathRemoveFileSpecW"
0x180084719  mov     [rdi+38h], rax
0x18008471d  call    cs:__imp_GetProcAddress
0x180084724  nop     dword ptr [rax+rax+00h]
0x180084729  mov     rcx, [rdi+30h]; hModule
0x18008472d  lea     rdx, aPathfindfilena; "PathFindFileNameW"
0x180084734  mov     [rdi+40h], rax
0x180084738  call    cs:__imp_GetProcAddress
0x18008473f  nop     dword ptr [rax+rax+00h]
0x180084744  cmp     qword ptr [rdi+38h], 0
0x180084749  mov     [rdi+48h], rax
0x18008474d  jz      loc_180084822
0x180084753  cmp     qword ptr [rdi+40h], 0
0x180084758  jz      loc_180084822
0x18008475e  test    rax, rax
0x180084761  jz      loc_180084822
0x180084767  mov     r8d, 105h
0x18008476d  mov     rdx, rsi
0x180084770  xor     ecx, ecx
0x180084772  call    GetPhonebookDirectory
0x180084777  test    eax, eax
0x180084779  jnz     short loc_180084785
0x18008477b  mov     ebx, 3EBh
0x180084780  jmp     loc_180084880
0x180084785  mov     rcx, [rdi+50h]
0x180084789  mov     rdx, rsi
0x18008478c  mov     rax, [rdi+38h]
0x180084790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084795  test    eax, eax
0x180084797  jz      short loc_18008477B
0x180084799  mov     rbx, [rdi+50h]
0x18008479d  mov     rcx, rbx; lpString
0x1800847a0  call    cs:__imp_lstrlenW
0x1800847a7  nop     dword ptr [rax+rax+00h]
0x1800847ac  movsxd  rcx, eax
0x1800847af  mov     eax, 5Ch ; '\'
0x1800847b4  cmp     ax, [rbx+rcx*2-2]
0x1800847b9  jnz     short loc_1800847D8
0x1800847bb  mov     rbx, [rdi+50h]
0x1800847bf  mov     rcx, rbx; lpString
0x1800847c2  call    cs:__imp_lstrlenW
0x1800847c9  nop     dword ptr [rax+rax+00h]
0x1800847ce  movsxd  rcx, eax
0x1800847d1  xor     eax, eax
0x1800847d3  mov     [rbx+rcx*2-2], ax
0x1800847d8  mov     rcx, [rdi+58h]; lpBuffer
0x1800847dc  mov     edx, 0F6h; uSize
0x1800847e1  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800847e8  nop     dword ptr [rax+rax+00h]
0x1800847ed  test    eax, eax
0x1800847ef  jz      short loc_180084822
0x1800847f1  mov     rcx, [rdi+58h]; pszDest
0x1800847f5  lea     r8, aSystem32Ras; "\\System32\\Ras"
0x1800847fc  mov     edx, 105h; cchDest
0x180084801  mov     [rsp+58h+dwFlags], 100h; dwFlags
0x180084809  call    StringCchCatExW
0x18008480e  test    eax, eax
0x180084810  jns     short loc_180084817
0x180084812  movzx   ebx, ax
0x180084815  jmp     short loc_180084830
0x180084817  xor     ebx, ebx
0x180084819  mov     dword ptr [rdi+2Ch], 1
0x180084820  jmp     short loc_18008488D
0x180084822  call    cs:__imp_GetLastError
0x180084829  nop     dword ptr [rax+rax+00h]
0x18008482e  mov     ebx, eax
0x180084830  test    ebx, ebx
0x180084832  jz      short loc_18008488D
0x180084834  jmp     short loc_180084880
0x180084836  call    cs:__imp_GlobalFree
0x18008483d  nop     dword ptr [rax+rax+00h]
0x180084842  mov     rcx, [rdi+58h]; hMem
0x180084846  mov     qword ptr [rdi+50h], 0
0x18008484e  test    rcx, rcx
0x180084851  jz      short loc_18008485F
0x180084853  call    cs:__imp_GlobalFree
0x18008485a  nop     dword ptr [rax+rax+00h]
0x18008485f  mov     qword ptr [rdi+58h], 0
0x180084867  test    rsi, rsi
0x18008486a  jz      short loc_18008487B
0x18008486c  mov     rcx, rsi; hMem
0x18008486f  call    cs:__imp_GlobalFree
0x180084876  nop     dword ptr [rax+rax+00h]
0x18008487b  xor     esi, esi
0x18008487d  lea     ebx, [rsi+8]
0x180084880  mov     rcx, rdi
0x180084883  call    PbkPathInfoReset
0x180084888  test    rsi, rsi
0x18008488b  jz      short loc_18008489C
0x18008488d  mov     rcx, rsi; hMem
0x180084890  call    cs:__imp_GlobalFree
0x180084897  nop     dword ptr [rax+rax+00h]
0x18008489c  mov     rcx, rdi; lpCriticalSection
0x18008489f  call    cs:__imp_LeaveCriticalSection
0x1800848a6  nop     dword ptr [rax+rax+00h]
0x1800848ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800848b2  cmp     rcx, r15
0x1800848b5  jz      short loc_1800848DB
0x1800848b7  test    byte ptr [rcx+1Ch], 80h
0x1800848bb  jz      short loc_1800848DB
0x1800848bd  cmp     byte ptr [rcx+19h], 6
0x1800848c1  jb      short loc_1800848DB
0x1800848c3  mov     rcx, [rcx+10h]
0x1800848c7  lea     r8, WPP_38cda081c674317ed40163d707084d83_Traceguids
0x1800848ce  mov     edx, 53h ; 'S'
0x1800848d3  mov     r9d, ebx
0x1800848d6  call    WPP_SF_d
0x1800848db  mov     eax, ebx
0x1800848dd  add     rsp, 38h
0x1800848e1  pop     r15
0x1800848e3  pop     rdi
0x1800848e4  pop     rsi
0x1800848e5  pop     rbx
0x1800848e6  retn
```
