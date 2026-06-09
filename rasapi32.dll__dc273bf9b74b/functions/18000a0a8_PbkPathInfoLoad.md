# PbkPathInfoLoad

- ea: `0x18000a0a8`
- end: `0x18000a4a6`
- name: `PbkPathInfoLoad`
- size: `1022`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `5`
- callee_count: `8`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180009dd0`
- `0x18000b960`
- `0x18003b284`
- `0x1800cf300`
- `0x1800d0dec`

## callees

- `0x18000a0a8`
- `0x18000b0f4`
- `0x18000c190`
- `0x18000ce90`
- `0x18003b164`
- `0x18004e580`
- `0x18004e984`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a302`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a302`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a0d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a0d8`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000a113`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000a121`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000a12f`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000a113`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000a121`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000a12f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a335`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a355`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a3de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a335`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a355`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a3de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a186`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a19b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a1b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a186`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a19b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a1b0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a169`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a3cb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a169`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a3cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18000a244`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18000a244`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000a210`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000a22c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000a210`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000a22c`
- `rtutils!TracePrintfExA` at `0x18000a377`
- `rtutils!TracePrintfExA` at `0x18000a377`

## string_xrefs

- `0x18000a15d`: `api-ms-win-core-shlwapi-legacy-l1-1-0.dll`
- `0x18000a190`: `PathRemoveFileSpecW`
- `0x18000a1a5`: `PathFindFileNameW`
- `0x18000a17c`: `PathCanonicalizeW`
- `0x18000a296`: `\System32\Ras`
- `0x18000a3f5`: `PbkPathInfoLoad: LoadLibrary failed %d`
- `0x18000a3c2`: `shlwapi.dll`
- `0x18000a368`: `PbkPathInfoLoad: GetProcAddress failed %d`
- `0x18000a440`: `PbkPathInfoLoad: StringCchCatEx failed %d`
- `0x18000a408`: `PbkPathInfoLoad: GetSystemWindowsDirectory failed %d`

## pseudocode

```c
__int64 __fastcall PbkPathInfoLoad(LPCRITICAL_SECTION lpCriticalSection)
{
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  __int64 v3; // rcx
  WCHAR *v4; // rax
  PRTL_CRITICAL_SECTION_DEBUG v5; // rcx
  WCHAR *v6; // rbp
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  HMODULE v9; // rcx
  FARPROC v10; // rax
  HMODULE v11; // rcx
  FARPROC v12; // rax
  PRTL_CRITICAL_SECTION_DEBUG v13; // rbx
  PRTL_CRITICAL_SECTION_DEBUG v14; // rbx
  const wchar_t *v15; // r11
  HRESULT v16; // eax
  __int64 v17; // r11
  signed int v18; // r8d
  size_t v19; // rsi
  __int64 v20; // rax
  const wchar_t *v21; // rcx
  _WORD *v22; // rdx
  _WORD *v23; // rcx
  unsigned int v24; // ebx
  DWORD LastError; // eax
  DWORD v27; // ecx
  const CHAR *v28; // r8
  __int64 v29; // rcx
  size_t pcchLength; // [rsp+60h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_38cda081c674317ed40163d707084d83_Traceguids);
  }
  EnterCriticalSection(lpCriticalSection);
  if ( HIDWORD(lpCriticalSection[1].DebugInfo) )
  {
    v6 = 0;
    v24 = 0;
    goto LABEL_31;
  }
  DebugInfo = lpCriticalSection[2].DebugInfo;
  if ( DebugInfo )
  {
    Free0(DebugInfo);
    lpCriticalSection[2].DebugInfo = 0;
  }
  v3 = *(_QWORD *)&lpCriticalSection[2].LockCount;
  if ( v3 )
  {
    Free0(v3);
    *(_QWORD *)&lpCriticalSection[2].LockCount = 0;
  }
  lpCriticalSection[2].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)GlobalAlloc(0x40u, 0x20Au);
  *(_QWORD *)&lpCriticalSection[2].LockCount = GlobalAlloc(0x40u, 0x20Au);
  v4 = (WCHAR *)GlobalAlloc(0x40u, 0x20Au);
  v5 = lpCriticalSection[2].DebugInfo;
  v6 = v4;
  if ( !v5 || !*(_QWORD *)&lpCriticalSection[2].LockCount || !v4 )
  {
    Free0(v5);
    v29 = *(_QWORD *)&lpCriticalSection[2].LockCount;
    lpCriticalSection[2].DebugInfo = 0;
    Free0(v29);
    *(_QWORD *)&lpCriticalSection[2].LockCount = 0;
    Free0(v6);
    v6 = 0;
    v24 = 8;
    goto LABEL_55;
  }
  Library = LoadLibraryExW(L"api-ms-win-core-shlwapi-legacy-l1-1-0.dll", 0, 0x800u);
  *(_QWORD *)&lpCriticalSection[1].LockCount = Library;
  if ( Library
    || (Library = LoadLibraryExW(L"shlwapi.dll", 0, 0x800u), (*(_QWORD *)&lpCriticalSection[1].LockCount = Library) != 0) )
  {
    ProcAddress = GetProcAddress(Library, "PathCanonicalizeW");
    v9 = *(HMODULE *)&lpCriticalSection[1].LockCount;
    lpCriticalSection[1].OwningThread = ProcAddress;
    v10 = GetProcAddress(v9, "PathRemoveFileSpecW");
    v11 = *(HMODULE *)&lpCriticalSection[1].LockCount;
    lpCriticalSection[1].LockSemaphore = v10;
    v12 = GetProcAddress(v11, "PathFindFileNameW");
    lpCriticalSection[1].SpinCount = (ULONG_PTR)v12;
    if ( !lpCriticalSection[1].OwningThread || !lpCriticalSection[1].LockSemaphore || !v12 )
    {
      LastError = GetLastError();
      v27 = g_dwTraceId;
      v24 = LastError;
      if ( g_dwTraceId == -1 )
        goto LABEL_36;
      v28 = "PbkPathInfoLoad: GetProcAddress failed %d";
      goto LABEL_40;
    }
    if ( (unsigned int)GetPhonebookDirectory(0, v6, 0x105u)
      && ((unsigned int (__fastcall *)(PRTL_CRITICAL_SECTION_DEBUG, WCHAR *))lpCriticalSection[1].OwningThread)(
           lpCriticalSection[2].DebugInfo,
           v6) )
    {
      v13 = lpCriticalSection[2].DebugInfo;
      if ( *((_WORD *)v13 + lstrlenW(&v13->Type) - 1) == 92 )
      {
        v14 = lpCriticalSection[2].DebugInfo;
        *((_WORD *)v14 + lstrlenW(&v14->Type) - 1) = 0;
      }
      if ( !GetSystemWindowsDirectoryW(*(LPWSTR *)&lpCriticalSection[2].LockCount, 0xF6u) )
      {
        LastError = GetLastError();
        v27 = g_dwTraceId;
        v24 = LastError;
        if ( g_dwTraceId == -1 )
          goto LABEL_36;
        v28 = "PbkPathInfoLoad: GetSystemWindowsDirectory failed %d";
        goto LABEL_40;
      }
      v15 = *(const wchar_t **)&lpCriticalSection[2].LockCount;
      pcchLength = 0;
      if ( v15 )
      {
        v16 = StringLengthWorkerW(v15, 0x105u, &pcchLength);
        LOWORD(v18) = v16;
        if ( v16 >= 0 )
        {
          v19 = 261 - pcchLength;
          if ( pcchLength == 261 || pcchLength == 260 )
          {
            v18 = -2147024774;
          }
          else
          {
            v20 = 2147483646;
            v21 = L"\\System32\\Ras";
            v22 = (_WORD *)(v17 + 2 * pcchLength);
            do
            {
              if ( !v20 )
                break;
              if ( !*v21 )
                break;
              *v22++ = *v21++;
              --v20;
              --v19;
            }
            while ( v19 );
            v18 = v19 == 0 ? 0x8007007A : 0;
            v23 = v22 - 1;
            if ( v19 )
              v23 = v22;
            *v23 = 0;
            if ( v19 )
              goto LABEL_30;
          }
          if ( v18 >= 0 )
          {
LABEL_30:
            v24 = 0;
            HIDWORD(lpCriticalSection[1].DebugInfo) = 1;
            goto LABEL_31;
          }
        }
      }
      else
      {
        LOWORD(v18) = 87;
      }
      v24 = (unsigned __int16)v18;
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "PbkPathInfoLoad: StringCchCatEx failed %d", (unsigned __int16)v18);
      goto LABEL_36;
    }
    v24 = 1003;
LABEL_55:
    PbkPathInfoReset(lpCriticalSection);
    goto LABEL_31;
  }
  LastError = GetLastError();
  v27 = g_dwTraceId;
  v24 = LastError;
  if ( g_dwTraceId != -1 )
  {
    v28 = "PbkPathInfoLoad: LoadLibrary failed %d";
LABEL_40:
    TracePrintfExA(v27, 0xCu, v28, LastError);
  }
LABEL_36:
  if ( v24 )
    goto LABEL_55;
LABEL_31:
  Free0(v6);
  LeaveCriticalSection(lpCriticalSection);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, WPP_38cda081c674317ed40163d707084d83_Traceguids, v24);
  }
  return v24;
}

```

## disassembly

```asm
0x18000a0a8  push    rbx
0x18000a0aa  push    rbp
0x18000a0ab  push    rsi
0x18000a0ac  push    rdi
0x18000a0ad  push    r14
0x18000a0af  push    r15
0x18000a0b1  sub     rsp, 28h
0x18000a0b5  mov     rdi, rcx
0x18000a0b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a0bf  lea     r15, WPP_GLOBAL_Control
0x18000a0c6  cmp     rcx, r15
0x18000a0c9  jz      short loc_18000A0D5
0x18000a0cb  test    byte ptr [rcx+1Ch], 80h
0x18000a0cf  jnz     loc_18000A37F
0x18000a0d5  mov     rcx, rdi; lpCriticalSection
0x18000a0d8  call    cs:__imp_EnterCriticalSection
0x18000a0de  xor     r14d, r14d
0x18000a0e1  cmp     [rdi+2Ch], r14d
0x18000a0e5  jnz     loc_18000A32D
0x18000a0eb  mov     rcx, [rdi+50h]
0x18000a0ef  test    rcx, rcx
0x18000a0f2  jnz     loc_18000A3A3
0x18000a0f8  mov     rcx, [rdi+58h]
0x18000a0fc  test    rcx, rcx
0x18000a0ff  jnz     loc_18000A3B1
0x18000a105  mov     esi, 20Ah
0x18000a10a  mov     ebx, 40h ; '@'
0x18000a10f  mov     edx, esi; dwBytes
0x18000a111  mov     ecx, ebx; uFlags
0x18000a113  call    cs:__imp_GlobalAlloc
0x18000a119  mov     edx, esi; dwBytes
0x18000a11b  mov     ecx, ebx; uFlags
0x18000a11d  mov     [rdi+50h], rax
0x18000a121  call    cs:__imp_GlobalAlloc
0x18000a127  mov     edx, esi; dwBytes
0x18000a129  mov     ecx, ebx; uFlags
0x18000a12b  mov     [rdi+58h], rax
0x18000a12f  call    cs:__imp_GlobalAlloc
0x18000a135  mov     rcx, [rdi+50h]
0x18000a139  mov     rbp, rax
0x18000a13c  test    rcx, rcx
0x18000a13f  jz      loc_18000A44C
0x18000a145  cmp     [rdi+58h], r14
0x18000a149  jz      loc_18000A44C
0x18000a14f  test    rax, rax
0x18000a152  jz      loc_18000A44C
0x18000a158  mov     ebx, 800h
0x18000a15d  lea     rcx, LibFileName; "api-ms-win-core-shlwapi-legacy-l1-1-0.d"...
0x18000a164  mov     r8d, ebx; dwFlags
0x18000a167  xor     edx, edx; hFile
0x18000a169  call    cs:__imp_LoadLibraryExW
0x18000a16f  mov     [rdi+30h], rax
0x18000a173  test    rax, rax
0x18000a176  jz      loc_18000A3BF
0x18000a17c  lea     rdx, ProcName; "PathCanonicalizeW"
0x18000a183  mov     rcx, rax; hModule
0x18000a186  call    cs:__imp_GetProcAddress
0x18000a18c  mov     rcx, [rdi+30h]; hModule
0x18000a190  lea     rdx, aPathremovefile; "PathRemoveFileSpecW"
0x18000a197  mov     [rdi+38h], rax
0x18000a19b  call    cs:__imp_GetProcAddress
0x18000a1a1  mov     rcx, [rdi+30h]; hModule
0x18000a1a5  lea     rdx, aPathfindfilena; "PathFindFileNameW"
0x18000a1ac  mov     [rdi+40h], rax
0x18000a1b0  call    cs:__imp_GetProcAddress
0x18000a1b6  mov     [rdi+48h], rax
0x18000a1ba  cmp     [rdi+38h], r14
0x18000a1be  jz      loc_18000A355
0x18000a1c4  cmp     [rdi+40h], r14
0x18000a1c8  jz      loc_18000A355
0x18000a1ce  test    rax, rax
0x18000a1d1  jz      loc_18000A355
0x18000a1d7  mov     esi, 105h
0x18000a1dc  mov     rdx, rbp
0x18000a1df  mov     r8d, esi
0x18000a1e2  xor     ecx, ecx
0x18000a1e4  call    GetPhonebookDirectory
0x18000a1e9  test    eax, eax
0x18000a1eb  jz      loc_18000A401
0x18000a1f1  mov     rcx, [rdi+50h]
0x18000a1f5  mov     rdx, rbp
0x18000a1f8  mov     rax, [rdi+38h]
0x18000a1fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a201  test    eax, eax
0x18000a203  jz      loc_18000A401
0x18000a209  mov     rbx, [rdi+50h]
0x18000a20d  mov     rcx, rbx; lpString
0x18000a210  call    cs:__imp_lstrlenW
0x18000a216  movsxd  rcx, eax
0x18000a219  mov     eax, 5Ch ; '\'
0x18000a21e  cmp     ax, [rbx+rcx*2-2]
0x18000a223  jnz     short loc_18000A23B
0x18000a225  mov     rbx, [rdi+50h]
0x18000a229  mov     rcx, rbx; lpString
0x18000a22c  call    cs:__imp_lstrlenW
0x18000a232  movsxd  rcx, eax
0x18000a235  mov     [rbx+rcx*2-2], r14w
0x18000a23b  mov     rcx, [rdi+58h]; lpBuffer
0x18000a23f  mov     edx, 0F6h; uSize
0x18000a244  call    cs:__imp_GetSystemWindowsDirectoryW
0x18000a24a  test    eax, eax
0x18000a24c  jz      loc_18000A335
0x18000a252  mov     r11, [rdi+58h]
0x18000a256  mov     [rsp+58h+pcchLength], r14
0x18000a25b  test    r11, r11
0x18000a25e  jz      loc_18000A424
0x18000a264  lea     r8, [rsp+58h+pcchLength]; pcchLength
0x18000a269  mov     rdx, rsi; cchMax
0x18000a26c  mov     rcx, r11; psz
0x18000a26f  call    StringLengthWorkerW
0x18000a274  mov     r8d, eax
0x18000a277  test    eax, eax
0x18000a279  js      loc_18000A42A
0x18000a27f  mov     rdx, [rsp+58h+pcchLength]
0x18000a284  sub     rsi, rdx
0x18000a287  cmp     rsi, 1
0x18000a28b  jbe     loc_18000A414
0x18000a291  mov     eax, 7FFFFFFEh
0x18000a296  lea     rcx, aSystem32Ras; "\\System32\\Ras"
0x18000a29d  lea     rdx, [r11+rdx*2]
0x18000a2a1  test    rax, rax
0x18000a2a4  jz      short loc_18000A2C5
0x18000a2a6  movzx   r8d, word ptr [rcx]
0x18000a2aa  test    r8w, r8w
0x18000a2ae  jz      short loc_18000A2C5
0x18000a2b0  mov     [rdx], r8w
0x18000a2b4  add     rcx, 2
0x18000a2b8  add     rdx, 2
0x18000a2bc  dec     rax
0x18000a2bf  sub     rsi, 1
0x18000a2c3  jnz     short loc_18000A2A1
0x18000a2c5  mov     rax, rsi
0x18000a2c8  mov     r8d, 8007007Ah
0x18000a2ce  neg     rax
0x18000a2d1  sbb     ecx, ecx
0x18000a2d3  not     ecx
0x18000a2d5  and     r8d, ecx
0x18000a2d8  lea     rcx, [rdx-2]
0x18000a2dc  test    rsi, rsi
0x18000a2df  cmovnz  rcx, rdx
0x18000a2e3  mov     [rcx], r14w
0x18000a2e7  jz      loc_18000A41A
0x18000a2ed  mov     ebx, r14d
0x18000a2f0  mov     dword ptr [rdi+2Ch], 1
0x18000a2f7  mov     rcx, rbp
0x18000a2fa  call    Free0
0x18000a2ff  mov     rcx, rdi; lpCriticalSection
0x18000a302  call    cs:__imp_LeaveCriticalSection
0x18000a308  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a30f  cmp     rcx, r15
0x18000a312  jz      short loc_18000A31E
0x18000a314  test    byte ptr [rcx+1Ch], 80h
0x18000a318  jnz     loc_18000A47F
0x18000a31e  mov     eax, ebx
0x18000a320  add     rsp, 28h
0x18000a324  pop     r15
0x18000a326  pop     r14
0x18000a328  pop     rdi
0x18000a329  pop     rsi
0x18000a32a  pop     rbp
0x18000a32b  pop     rbx
0x18000a32c  retn
0x18000a32d  mov     rbp, r14
0x18000a330  mov     ebx, r14d
0x18000a333  jmp     short loc_18000A2F7
0x18000a335  call    cs:__imp_GetLastError
0x18000a33b  mov     ecx, cs:g_dwTraceId
0x18000a341  mov     ebx, eax
0x18000a343  cmp     ecx, 0FFFFFFFFh
0x18000a346  jnz     loc_18000A408
0x18000a34c  test    ebx, ebx
0x18000a34e  jz      short loc_18000A2F7
0x18000a350  jmp     loc_18000A472
0x18000a355  call    cs:__imp_GetLastError
0x18000a35b  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000a361  mov     ebx, eax
0x18000a363  cmp     ecx, 0FFFFFFFFh
0x18000a366  jz      short loc_18000A34C
0x18000a368  lea     r8, aPbkpathinfoloa_2; "PbkPathInfoLoad: GetProcAddress failed "...
0x18000a36f  mov     r9d, eax
0x18000a372  mov     edx, 0Ch; dwFlags
0x18000a377  call    cs:__imp_TracePrintfExA
0x18000a37d  jmp     short loc_18000A34C
0x18000a37f  cmp     byte ptr [rcx+19h], 6
0x18000a383  jb      loc_18000A0D5
0x18000a389  mov     rcx, [rcx+10h]
0x18000a38d  lea     r8, WPP_38cda081c674317ed40163d707084d83_Traceguids
0x18000a394  mov     edx, 52h ; 'R'
0x18000a399  call    WPP_SF_
0x18000a39e  jmp     loc_18000A0D5
0x18000a3a3  call    Free0
0x18000a3a8  mov     [rdi+50h], r14
0x18000a3ac  jmp     loc_18000A0F8
0x18000a3b1  call    Free0
0x18000a3b6  mov     [rdi+58h], r14
0x18000a3ba  jmp     loc_18000A105
0x18000a3bf  mov     r8d, ebx; dwFlags
0x18000a3c2  lea     rcx, aShlwapiDll; "shlwapi.dll"
0x18000a3c9  xor     edx, edx; hFile
0x18000a3cb  call    cs:__imp_LoadLibraryExW
0x18000a3d1  mov     [rdi+30h], rax
0x18000a3d5  test    rax, rax
0x18000a3d8  jnz     loc_18000A17C
0x18000a3de  call    cs:__imp_GetLastError
0x18000a3e4  mov     ecx, cs:g_dwTraceId
0x18000a3ea  mov     ebx, eax
0x18000a3ec  cmp     ecx, 0FFFFFFFFh
0x18000a3ef  jz      loc_18000A34C
0x18000a3f5  lea     r8, aPbkpathinfoloa_0; "PbkPathInfoLoad: LoadLibrary failed %d"
0x18000a3fc  jmp     loc_18000A36F
0x18000a401  mov     ebx, 3EBh
0x18000a406  jmp     short loc_18000A472
0x18000a408  lea     r8, aPbkpathinfoloa_1; "PbkPathInfoLoad: GetSystemWindowsDirect"...
0x18000a40f  jmp     loc_18000A36F
0x18000a414  mov     r8d, 8007007Ah
0x18000a41a  test    r8d, r8d
0x18000a41d  js      short loc_18000A42A
0x18000a41f  jmp     loc_18000A2ED
0x18000a424  mov     r8d, 80070057h
0x18000a42a  mov     ecx, cs:g_dwTraceId
0x18000a430  movzx   ebx, r8w
0x18000a434  cmp     ecx, 0FFFFFFFFh
0x18000a437  jz      loc_18000A34C
0x18000a43d  mov     r9d, ebx
0x18000a440  lea     r8, aPbkpathinfoloa; "PbkPathInfoLoad: StringCchCatEx failed "...
0x18000a447  jmp     loc_18000A372
0x18000a44c  call    Free0
0x18000a451  mov     rcx, [rdi+58h]
0x18000a455  mov     [rdi+50h], r14
0x18000a459  call    Free0
0x18000a45e  mov     rcx, rbp
0x18000a461  mov     [rdi+58h], r14
0x18000a465  call    Free0
0x18000a46a  mov     rbp, r14
0x18000a46d  mov     ebx, 8
0x18000a472  mov     rcx, rdi
0x18000a475  call    PbkPathInfoReset
0x18000a47a  jmp     loc_18000A2F7
0x18000a47f  cmp     byte ptr [rcx+19h], 6
0x18000a483  jb      loc_18000A31E
0x18000a489  mov     rcx, [rcx+10h]
0x18000a48d  lea     r8, WPP_38cda081c674317ed40163d707084d83_Traceguids
0x18000a494  mov     edx, 53h ; 'S'
0x18000a499  mov     r9d, ebx
0x18000a49c  call    WPP_SF_d
0x18000a4a1  jmp     loc_18000A31E
```
