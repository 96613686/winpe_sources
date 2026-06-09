# CleanupFiles(void)

- ea: `0x14003fde4`
- end: `0x14004035a`
- name: `?CleanupFiles@@YAJXZ`
- size: `1398`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x14000859c`

## callees

- `0x1400039b1`
- `0x1400070b0`
- `0x140020420`
- `0x14003fde4`
- `0x140040d50`
- `0x1400413ac`
- `0x140061c90`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140040049`
- `KERNEL32!GetLastError` at `0x1400400e2`
- `KERNEL32!GetLastError` at `0x14004016d`
- `KERNEL32!GetLastError` at `0x1400401da`
- `KERNEL32!GetLastError` at `0x140040049`
- `KERNEL32!GetLastError` at `0x1400400e2`
- `KERNEL32!GetLastError` at `0x14004016d`
- `KERNEL32!GetLastError` at `0x1400401da`
- `KERNEL32!CloseHandle` at `0x14003fef1`
- `KERNEL32!CloseHandle` at `0x14004019f`
- `KERNEL32!CloseHandle` at `0x140040292`
- `KERNEL32!CloseHandle` at `0x1400402af`
- `KERNEL32!CloseHandle` at `0x14003fef1`
- `KERNEL32!CloseHandle` at `0x14004019f`
- `KERNEL32!CloseHandle` at `0x140040292`
- `KERNEL32!CloseHandle` at `0x1400402af`
- `KERNEL32!HeapAlloc` at `0x14003fe38`
- `KERNEL32!HeapAlloc` at `0x14003fe78`
- `KERNEL32!HeapAlloc` at `0x14003feb6`
- `KERNEL32!HeapAlloc` at `0x14003fe38`
- `KERNEL32!HeapAlloc` at `0x14003fe78`
- `KERNEL32!HeapAlloc` at `0x14003feb6`
- `KERNEL32!HeapFree` at `0x140040237`
- `KERNEL32!HeapFree` at `0x14004026e`
- `KERNEL32!HeapFree` at `0x1400402df`
- `KERNEL32!HeapFree` at `0x140040304`
- `KERNEL32!HeapFree` at `0x140040329`
- `KERNEL32!HeapFree` at `0x140040237`
- `KERNEL32!HeapFree` at `0x14004026e`
- `KERNEL32!HeapFree` at `0x1400402df`
- `KERNEL32!HeapFree` at `0x140040304`
- `KERNEL32!HeapFree` at `0x140040329`
- `KERNEL32!GetProcessHeap` at `0x14003fe1f`
- `KERNEL32!GetProcessHeap` at `0x14003fe64`
- `KERNEL32!GetProcessHeap` at `0x14003fea2`
- `KERNEL32!GetProcessHeap` at `0x140040223`
- `KERNEL32!GetProcessHeap` at `0x14004025a`
- `KERNEL32!GetProcessHeap` at `0x1400402cb`
- `KERNEL32!GetProcessHeap` at `0x1400402f0`
- `KERNEL32!GetProcessHeap` at `0x140040315`
- `KERNEL32!GetProcessHeap` at `0x14003fe1f`
- `KERNEL32!GetProcessHeap` at `0x14003fe64`
- `KERNEL32!GetProcessHeap` at `0x14003fea2`
- `KERNEL32!GetProcessHeap` at `0x140040223`
- `KERNEL32!GetProcessHeap` at `0x14004025a`
- `KERNEL32!GetProcessHeap` at `0x1400402cb`
- `KERNEL32!GetProcessHeap` at `0x1400402f0`
- `KERNEL32!GetProcessHeap` at `0x140040315`
- `KERNEL32!CreateFileW` at `0x140040158`
- `KERNEL32!CreateFileW` at `0x140040158`
- `KERNEL32!GetFileAttributesW` at `0x140040020`
- `KERNEL32!GetFileAttributesW` at `0x1400400b9`
- `KERNEL32!GetFileAttributesW` at `0x140040020`
- `KERNEL32!GetFileAttributesW` at `0x1400400b9`
- `KERNEL32!FindFirstFileW` at `0x14003ff5f`
- `KERNEL32!FindFirstFileW` at `0x14003ff5f`
- `KERNEL32!FindNextFileW` at `0x1400401b5`
- `KERNEL32!FindNextFileW` at `0x1400401b5`
- `KERNEL32!FindClose` at `0x1400401cc`
- `KERNEL32!FindClose` at `0x1400401cc`
- `KERNEL32!DeleteFileW` at `0x140040125`
- `KERNEL32!DeleteFileW` at `0x140040125`
- `KERNEL32!SetFileAttributesW` at `0x140040039`
- `KERNEL32!SetFileAttributesW` at `0x1400400d2`
- `KERNEL32!SetFileAttributesW` at `0x140040039`
- `KERNEL32!SetFileAttributesW` at `0x1400400d2`
- `msvcrt!_wcsicmp` at `0x14003ff97`
- `msvcrt!_wcsicmp` at `0x14003ffb7`
- `msvcrt!_wcsicmp` at `0x14003ff97`
- `msvcrt!_wcsicmp` at `0x14003ffb7`

## pseudocode

```c
__int64 CleanupFiles(void)
{
  char *v0; // rbp
  unsigned __int16 *v1; // r14
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v3; // r15
  unsigned __int16 *v4; // rsi
  signed int v5; // ebx
  HANDLE v6; // rax
  HANDLE v7; // rax
  unsigned __int64 v8; // rdx
  int MsdtTempPath; // eax
  int v10; // eax
  char *FirstFileW; // r13
  int v12; // eax
  int v13; // r9d
  signed int LastError; // eax
  bool v15; // sf
  signed int v16; // eax
  char *FileW; // rax
  signed int v18; // eax
  unsigned __int16 *v19; // rdi
  HANDLE v20; // rax
  WCHAR *v21; // rdi
  HANDLE v22; // rax
  HANDLE v23; // rax
  HANDLE v24; // rax
  HANDLE v25; // rax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-4A8h] BYREF
  unsigned __int16 v28[264]; // [rsp+290h] [rbp-258h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v0 = 0;
  v1 = 0;
  ProcessHeap = GetProcessHeap();
  v3 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x208u);
  if ( !v3 )
  {
    v4 = 0;
    v5 = -2147024882;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CleanupFiles", 1124, -2147024882);
    goto LABEL_46;
  }
  v6 = GetProcessHeap();
  v4 = (unsigned __int16 *)HeapAlloc(v6, 0, 0x208u);
  if ( !v4 )
  {
    v5 = -2147024882;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CleanupFiles", 1125, -2147024882);
    goto LABEL_46;
  }
  v7 = GetProcessHeap();
  v1 = (unsigned __int16 *)HeapAlloc(v7, 0, 0x208u);
  if ( !v1 )
  {
    v5 = -2147024882;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CleanupFiles", 1126, -2147024882);
    goto LABEL_46;
  }
  if ( (char *)g_FileHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(g_FileHandle);
    g_FileHandle = 0;
  }
  MsdtTempPath = GetMsdtTempPath(v28, v8);
  v5 = MsdtTempPath;
  if ( MsdtTempPath < 0 )
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CleanupFiles", 1136, MsdtTempPath);
    goto LABEL_46;
  }
  v10 = StringCchPrintfW(v1, 0x104u, L"%s*", v28);
  v5 = v10;
  if ( v10 < 0 )
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CleanupFiles", 1139, v10);
    goto LABEL_46;
  }
  FirstFileW = (char *)FindFirstFileW(v1, &FindFileData);
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    while ( 1 )
    {
      if ( (FindFileData.dwFileAttributes & 0x10) == 0
        || !_wcsicmp(FindFileData.cFileName, L".")
        || !_wcsicmp(FindFileData.cFileName, L"..") )
      {
        goto LABEL_41;
      }
      v12 = StringCchPrintfW(v3, 0x104u, L"%s%s", v28, FindFileData.cFileName);
      if ( v12 < 0 )
      {
        v13 = 1161;
LABEL_19:
        SdpDebugPrint(1u, "Dwz WARNING: %s:%d - hr = 0x%08X\n", "CleanupFiles", v13, v12);
        v5 = 0;
        goto LABEL_41;
      }
      if ( (GetFileAttributesW(v3) & 1) != 0 && !SetFileAttributesW(v3, 0x80u) )
      {
        LastError = GetLastError();
        v15 = LastError < 0;
        if ( LastError > 0 )
        {
          LastError = (unsigned __int16)LastError | 0x80070000;
          v15 = LastError < 0;
        }
        if ( v15 )
          SdpDebugPrint(1u, "Dwz IGNORED: %s:%d - hr = 0x%08X\n", "CleanupFiles", 1168, LastError);
      }
      v12 = StringCchPrintfW(v4, 0x104u, L"%s\\%s", v3, L"inuse");
      v5 = v12;
      if ( v12 < 0 )
      {
        v13 = 1172;
        goto LABEL_19;
      }
      if ( (GetFileAttributesW(v4) & 1) != 0 )
      {
        if ( SetFileAttributesW(v4, 0x80u) )
          goto LABEL_34;
        v16 = GetLastError();
        v5 = v16;
        if ( v16 > 0 )
          v5 = (unsigned __int16)v16 | 0x80070000;
        if ( v5 < 0 )
          break;
      }
LABEL_35:
      DeleteFileW(v4);
      FileW = (char *)CreateFileW(v4, 0x80000000, 1u, 0, 3u, 0x80u, 0);
      v0 = FileW;
      if ( FileW != (char *)-1LL )
      {
        if ( FileW )
        {
          CloseHandle(FileW);
          v0 = 0;
        }
        goto LABEL_41;
      }
      if ( GetLastError() == 2 )
      {
        v12 = DeleteDirectory(v3);
        v5 = v12;
        if ( v12 < 0 )
        {
          v13 = 1203;
          goto LABEL_19;
        }
      }
LABEL_41:
      if ( !FindNextFileW(FirstFileW, &FindFileData) )
      {
        FindClose(FirstFileW);
        goto LABEL_46;
      }
    }
    SdpDebugPrint(1u, "Dwz IGNORED: %s:%d - hr = 0x%08X\n", "CleanupFiles", 1179, v5);
LABEL_34:
    v5 = 0;
    goto LABEL_35;
  }
  v18 = GetLastError();
  v5 = v18;
  if ( v18 > 0 )
    v5 = (unsigned __int16)v18 | 0x80070000;
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CleanupFiles", 1142, v5);
LABEL_46:
  v19 = g_TempDirectoryPath;
  if ( g_TempDirectoryPath )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v19);
    g_TempDirectoryPath = 0;
  }
  v21 = (WCHAR *)g_HistoryDirectory;
  if ( g_HistoryDirectory )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v21);
    g_HistoryDirectory = 0;
  }
  if ( (unsigned __int64)(v0 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v0);
  if ( (char *)g_FileHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(g_FileHandle);
    g_FileHandle = 0;
  }
  if ( v4 )
  {
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v4);
  }
  if ( v3 )
  {
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v3);
  }
  if ( v1 )
  {
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v1);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14003fde4  push    rbx
0x14003fde6  push    rbp
0x14003fde7  push    rsi
0x14003fde8  push    rdi
0x14003fde9  push    r13
0x14003fdeb  push    r14
0x14003fded  push    r15
0x14003fdef  sub     rsp, 4B0h
0x14003fdf6  mov     rax, cs:__security_cookie
0x14003fdfd  xor     rax, rsp
0x14003fe00  mov     [rsp+4E8h+var_48], rax
0x14003fe08  xor     edx, edx; Val
0x14003fe0a  lea     rcx, [rsp+4E8h+FindFileData]; void *
0x14003fe0f  mov     r8d, 250h; Size
0x14003fe15  call    memset_0
0x14003fe1a  xor     ebp, ebp
0x14003fe1c  xor     r14d, r14d
0x14003fe1f  call    cs:__imp_GetProcessHeap
0x14003fe26  nop     dword ptr [rax+rax+00h]
0x14003fe2b  mov     ebx, 208h
0x14003fe30  xor     edx, edx; dwFlags
0x14003fe32  mov     rcx, rax; hHeap
0x14003fe35  mov     r8d, ebx; dwBytes
0x14003fe38  call    cs:__imp_HeapAlloc
0x14003fe3f  nop     dword ptr [rax+rax+00h]
0x14003fe44  mov     r15, rax
0x14003fe47  test    rax, rax
0x14003fe4a  jnz     short loc_14003FE64
0x14003fe4c  mov     eax, 8007000Eh
0x14003fe51  xor     esi, esi
0x14003fe53  mov     ebx, eax
0x14003fe55  mov     [rsp+4E8h+dwCreationDisposition], eax
0x14003fe59  mov     r9d, 464h
0x14003fe5f  jmp     loc_1400401FF
0x14003fe64  call    cs:__imp_GetProcessHeap
0x14003fe6b  nop     dword ptr [rax+rax+00h]
0x14003fe70  mov     r8, rbx; dwBytes
0x14003fe73  xor     edx, edx; dwFlags
0x14003fe75  mov     rcx, rax; hHeap
0x14003fe78  call    cs:__imp_HeapAlloc
0x14003fe7f  nop     dword ptr [rax+rax+00h]
0x14003fe84  mov     rsi, rax
0x14003fe87  test    rax, rax
0x14003fe8a  jnz     short loc_14003FEA2
0x14003fe8c  mov     eax, 8007000Eh
0x14003fe91  mov     r9d, 465h
0x14003fe97  mov     ebx, eax
0x14003fe99  mov     [rsp+4E8h+dwCreationDisposition], eax
0x14003fe9d  jmp     loc_1400401FF
0x14003fea2  call    cs:__imp_GetProcessHeap
0x14003fea9  nop     dword ptr [rax+rax+00h]
0x14003feae  mov     r8, rbx; dwBytes
0x14003feb1  xor     edx, edx; dwFlags
0x14003feb3  mov     rcx, rax; hHeap
0x14003feb6  call    cs:__imp_HeapAlloc
0x14003febd  nop     dword ptr [rax+rax+00h]
0x14003fec2  mov     r14, rax
0x14003fec5  test    rax, rax
0x14003fec8  jnz     short loc_14003FEE0
0x14003feca  mov     eax, 8007000Eh
0x14003fecf  mov     r9d, 466h
0x14003fed5  mov     ebx, eax
0x14003fed7  mov     [rsp+4E8h+dwCreationDisposition], eax
0x14003fedb  jmp     loc_1400401FF
0x14003fee0  mov     rcx, cs:?g_FileHandle@@3PEAXEA; hObject
0x14003fee7  lea     rax, [rcx-1]
0x14003feeb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14003feef  ja      short loc_14003FF04
0x14003fef1  call    cs:__imp_CloseHandle
0x14003fef8  nop     dword ptr [rax+rax+00h]
0x14003fefd  mov     cs:?g_FileHandle@@3PEAXEA, rbp; void * g_FileHandle
0x14003ff04  lea     rcx, [rsp+4E8h+var_258]; unsigned __int16 *
0x14003ff0c  call    ?GetMsdtTempPath@@YAJPEAG_K@Z; GetMsdtTempPath(ushort *,unsigned __int64)
0x14003ff11  mov     ebx, eax
0x14003ff13  test    eax, eax
0x14003ff15  jns     short loc_14003FF26
0x14003ff17  mov     [rsp+4E8h+dwCreationDisposition], eax
0x14003ff1b  mov     r9d, 470h
0x14003ff21  jmp     loc_1400401FF
0x14003ff26  lea     r9, [rsp+4E8h+var_258]
0x14003ff2e  mov     edx, 104h; unsigned __int64
0x14003ff33  lea     r8, aS_2; "%s*"
0x14003ff3a  mov     rcx, r14; unsigned __int16 *
0x14003ff3d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14003ff42  mov     ebx, eax
0x14003ff44  test    eax, eax
0x14003ff46  jns     short loc_14003FF57
0x14003ff48  mov     [rsp+4E8h+dwCreationDisposition], eax
0x14003ff4c  mov     r9d, 473h
0x14003ff52  jmp     loc_1400401FF
0x14003ff57  lea     rdx, [rsp+4E8h+FindFileData]; lpFindFileData
0x14003ff5c  mov     rcx, r14; lpFileName
0x14003ff5f  call    cs:__imp_FindFirstFileW
0x14003ff66  nop     dword ptr [rax+rax+00h]
0x14003ff6b  mov     r13, rax
0x14003ff6e  dec     rax
0x14003ff71  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14003ff75  ja      loc_1400401DA
0x14003ff7b  mov     edi, 1
0x14003ff80  test    byte ptr [rsp+4E8h+FindFileData.dwFileAttributes], 10h
0x14003ff85  jz      loc_1400401AD
0x14003ff8b  lea     rdx, asc_1400707D8; "."
0x14003ff92  lea     rcx, [rsp+4E8h+FindFileData.cFileName]; String1
0x14003ff97  call    cs:__imp__wcsicmp
0x14003ff9e  nop     dword ptr [rax+rax+00h]
0x14003ffa3  test    eax, eax
0x14003ffa5  jz      loc_1400401AD
0x14003ffab  lea     rdx, asc_140070B9C; ".."
0x14003ffb2  lea     rcx, [rsp+4E8h+FindFileData.cFileName]; String1
0x14003ffb7  call    cs:__imp__wcsicmp
0x14003ffbe  nop     dword ptr [rax+rax+00h]
0x14003ffc3  test    eax, eax
0x14003ffc5  jz      loc_1400401AD
0x14003ffcb  lea     rax, [rsp+4E8h+FindFileData.cFileName]
0x14003ffd0  mov     ebx, 104h
0x14003ffd5  mov     edx, ebx; unsigned __int64
0x14003ffd7  mov     qword ptr [rsp+4E8h+dwCreationDisposition], rax
0x14003ffdc  lea     r9, [rsp+4E8h+var_258]
0x14003ffe4  mov     rcx, r15; unsigned __int16 *
0x14003ffe7  lea     r8, aSS_2; "%s%s"
0x14003ffee  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14003fff3  test    eax, eax
0x14003fff5  jns     short loc_14004001D
0x14003fff7  mov     r9d, 489h
0x14003fffd  lea     r8, aCleanupfiles; "CleanupFiles"
0x140040004  mov     [rsp+4E8h+dwCreationDisposition], eax
0x140040008  lea     rdx, aDwzWarningSDHr; "Dwz WARNING: %s:%d - hr = 0x%08X\n"
0x14004000f  mov     ecx, edi; Level
0x140040011  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140040016  xor     ebx, ebx
0x140040018  jmp     loc_1400401AD
0x14004001d  mov     rcx, r15; lpFileName
0x140040020  call    cs:__imp_GetFileAttributesW
0x140040027  nop     dword ptr [rax+rax+00h]
0x14004002c  test    dil, al
0x14004002f  jz      short loc_140040084
0x140040031  mov     edx, 80h; dwFileAttributes
0x140040036  mov     rcx, r15; lpFileName
0x140040039  call    cs:__imp_SetFileAttributesW
0x140040040  nop     dword ptr [rax+rax+00h]
0x140040045  test    eax, eax
0x140040047  jnz     short loc_140040084
0x140040049  call    cs:__imp_GetLastError
0x140040050  nop     dword ptr [rax+rax+00h]
0x140040055  test    eax, eax
0x140040057  jle     short loc_140040063
0x140040059  movzx   eax, ax
0x14004005c  or      eax, 80070000h
0x140040061  test    eax, eax
0x140040063  jns     short loc_140040084
0x140040065  mov     r9d, 490h
0x14004006b  mov     [rsp+4E8h+dwCreationDisposition], eax
0x14004006f  lea     r8, aCleanupfiles; "CleanupFiles"
0x140040076  mov     ecx, edi; Level
0x140040078  lea     rdx, aDwzIgnoredSDHr; "Dwz IGNORED: %s:%d - hr = 0x%08X\n"
0x14004007f  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140040084  lea     rax, aInuse; "inuse"
0x14004008b  mov     r9, r15
0x14004008e  lea     r8, aSS_1; "%s\\%s"
0x140040095  mov     qword ptr [rsp+4E8h+dwCreationDisposition], rax
0x14004009a  mov     rdx, rbx; unsigned __int64
0x14004009d  mov     rcx, rsi; unsigned __int16 *
0x1400400a0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400400a5  mov     ebx, eax
0x1400400a7  test    eax, eax
0x1400400a9  jns     short loc_1400400B6
0x1400400ab  mov     r9d, 494h
0x1400400b1  jmp     loc_14003FFFD
0x1400400b6  mov     rcx, rsi; lpFileName
0x1400400b9  call    cs:__imp_GetFileAttributesW
0x1400400c0  nop     dword ptr [rax+rax+00h]
0x1400400c5  test    dil, al
0x1400400c8  jz      short loc_140040122
0x1400400ca  mov     edx, 80h; dwFileAttributes
0x1400400cf  mov     rcx, rsi; lpFileName
0x1400400d2  call    cs:__imp_SetFileAttributesW
0x1400400d9  nop     dword ptr [rax+rax+00h]
0x1400400de  test    eax, eax
0x1400400e0  jnz     short loc_140040120
0x1400400e2  call    cs:__imp_GetLastError
0x1400400e9  nop     dword ptr [rax+rax+00h]
0x1400400ee  mov     ebx, eax
0x1400400f0  test    eax, eax
0x1400400f2  jle     short loc_1400400FD
0x1400400f4  movzx   ebx, ax
0x1400400f7  or      ebx, 80070000h
0x1400400fd  test    ebx, ebx
0x1400400ff  jns     short loc_140040122
0x140040101  mov     r9d, 49Bh
0x140040107  mov     [rsp+4E8h+dwCreationDisposition], ebx
0x14004010b  lea     r8, aCleanupfiles; "CleanupFiles"
0x140040112  mov     ecx, edi; Level
0x140040114  lea     rdx, aDwzIgnoredSDHr; "Dwz IGNORED: %s:%d - hr = 0x%08X\n"
0x14004011b  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140040120  xor     ebx, ebx
0x140040122  mov     rcx, rsi; lpFileName
0x140040125  call    cs:__imp_DeleteFileW
0x14004012c  nop     dword ptr [rax+rax+00h]
0x140040131  mov     [rsp+4E8h+hTemplateFile], 0; hTemplateFile
0x14004013a  xor     r9d, r9d; lpSecurityAttributes
0x14004013d  mov     [rsp+4E8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140040145  mov     r8d, edi; dwShareMode
0x140040148  mov     edx, 80000000h; dwDesiredAccess
0x14004014d  mov     [rsp+4E8h+dwCreationDisposition], 3; dwCreationDisposition
0x140040155  mov     rcx, rsi; lpFileName
0x140040158  call    cs:__imp_CreateFileW
0x14004015f  nop     dword ptr [rax+rax+00h]
0x140040164  mov     rbp, rax
0x140040167  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14004016b  jnz     short loc_140040197
0x14004016d  call    cs:__imp_GetLastError
0x140040174  nop     dword ptr [rax+rax+00h]
0x140040179  cmp     eax, 2
0x14004017c  jnz     short loc_1400401AD
0x14004017e  mov     rcx, r15; unsigned __int16 *
0x140040181  call    ?DeleteDirectory@@YAJPEBG@Z; DeleteDirectory(ushort const *)
0x140040186  mov     ebx, eax
0x140040188  test    eax, eax
0x14004018a  jns     short loc_1400401AD
0x14004018c  mov     r9d, 4B3h
0x140040192  jmp     loc_14003FFFD
0x140040197  test    rax, rax
0x14004019a  jz      short loc_1400401AD
0x14004019c  mov     rcx, rax; hObject
0x14004019f  call    cs:__imp_CloseHandle
0x1400401a6  nop     dword ptr [rax+rax+00h]
0x1400401ab  xor     ebp, ebp
0x1400401ad  lea     rdx, [rsp+4E8h+FindFileData]; lpFindFileData
0x1400401b2  mov     rcx, r13; hFindFile
0x1400401b5  call    cs:__imp_FindNextFileW
0x1400401bc  nop     dword ptr [rax+rax+00h]
0x1400401c1  test    eax, eax
0x1400401c3  jnz     loc_14003FF80
0x1400401c9  mov     rcx, r13; hFindFile
0x1400401cc  call    cs:__imp_FindClose
0x1400401d3  nop     dword ptr [rax+rax+00h]
0x1400401d8  jmp     short loc_140040217
0x1400401da  call    cs:__imp_GetLastError
0x1400401e1  nop     dword ptr [rax+rax+00h]
0x1400401e6  mov     ebx, eax
0x1400401e8  test    eax, eax
0x1400401ea  jle     short loc_1400401F5
0x1400401ec  movzx   ebx, ax
0x1400401ef  or      ebx, 80070000h
0x1400401f5  mov     [rsp+4E8h+dwCreationDisposition], ebx
0x1400401f9  mov     r9d, 476h
0x1400401ff  lea     r8, aCleanupfiles; "CleanupFiles"
0x140040206  mov     ecx, 1; Level
0x14004020b  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140040212  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140040217  mov     rdi, cs:?g_TempDirectoryPath@@3PEAGEA; ushort * g_TempDirectoryPath
0x14004021e  test    rdi, rdi
0x140040221  jz      short loc_14004024E
0x140040223  call    cs:__imp_GetProcessHeap
0x14004022a  nop     dword ptr [rax+rax+00h]
0x14004022f  mov     r8, rdi; lpMem
0x140040232  xor     edx, edx; dwFlags
0x140040234  mov     rcx, rax; hHeap
0x140040237  call    cs:__imp_HeapFree
0x14004023e  nop     dword ptr [rax+rax+00h]
0x140040243  mov     cs:?g_TempDirectoryPath@@3PEAGEA, 0; ushort * g_TempDirectoryPath
0x14004024e  mov     rdi, cs:?g_HistoryDirectory@@3PEAGEA; ushort * g_HistoryDirectory
0x140040255  test    rdi, rdi
0x140040258  jz      short loc_140040285
0x14004025a  call    cs:__imp_GetProcessHeap
0x140040261  nop     dword ptr [rax+rax+00h]
0x140040266  mov     r8, rdi; lpMem
0x140040269  xor     edx, edx; dwFlags
0x14004026b  mov     rcx, rax; hHeap
0x14004026e  call    cs:__imp_HeapFree
0x140040275  nop     dword ptr [rax+rax+00h]
0x14004027a  mov     cs:?g_HistoryDirectory@@3PEAGEA, 0; ushort * g_HistoryDirectory
0x140040285  lea     rax, [rbp-1]
0x140040289  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14004028d  ja      short loc_14004029E
0x14004028f  mov     rcx, rbp; hObject
0x140040292  call    cs:__imp_CloseHandle
0x140040299  nop     dword ptr [rax+rax+00h]
0x14004029e  mov     rcx, cs:?g_FileHandle@@3PEAXEA; hObject
0x1400402a5  lea     rax, [rcx-1]
0x1400402a9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400402ad  ja      short loc_1400402C6
0x1400402af  call    cs:__imp_CloseHandle
0x1400402b6  nop     dword ptr [rax+rax+00h]
0x1400402bb  mov     cs:?g_FileHandle@@3PEAXEA, 0; void * g_FileHandle
0x1400402c6  test    rsi, rsi
0x1400402c9  jz      short loc_1400402EB
0x1400402cb  call    cs:__imp_GetProcessHeap
0x1400402d2  nop     dword ptr [rax+rax+00h]
0x1400402d7  mov     r8, rsi; lpMem
0x1400402da  xor     edx, edx; dwFlags
0x1400402dc  mov     rcx, rax; hHeap
0x1400402df  call    cs:__imp_HeapFree
0x1400402e6  nop     dword ptr [rax+rax+00h]
0x1400402eb  test    r15, r15
0x1400402ee  jz      short loc_140040310
0x1400402f0  call    cs:__imp_GetProcessHeap
0x1400402f7  nop     dword ptr [rax+rax+00h]
0x1400402fc  mov     r8, r15; lpMem
0x1400402ff  xor     edx, edx; dwFlags
  ... truncated ...
```
