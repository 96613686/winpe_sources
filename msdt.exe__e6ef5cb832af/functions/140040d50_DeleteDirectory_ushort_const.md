# DeleteDirectory(ushort const *)

- ea: `0x140040d50`
- end: `0x14004101a`
- name: `?DeleteDirectory@@YAJPEBG@Z`
- size: `714`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x14003fde4`
- `0x140040d50`

## callees

- `0x1400039b1`
- `0x1400070b0`
- `0x140020420`
- `0x140040d50`
- `0x140061c90`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140040ec0`
- `KERNEL32!GetLastError` at `0x140040f10`
- `KERNEL32!GetLastError` at `0x140040f90`
- `KERNEL32!GetLastError` at `0x140040ec0`
- `KERNEL32!GetLastError` at `0x140040f10`
- `KERNEL32!GetLastError` at `0x140040f90`
- `KERNEL32!HeapAlloc` at `0x140040da1`
- `KERNEL32!HeapAlloc` at `0x140040da1`
- `KERNEL32!HeapFree` at `0x140040fe5`
- `KERNEL32!HeapFree` at `0x140040fe5`
- `KERNEL32!GetProcessHeap` at `0x140040d8a`
- `KERNEL32!GetProcessHeap` at `0x140040fd1`
- `KERNEL32!GetProcessHeap` at `0x140040d8a`
- `KERNEL32!GetProcessHeap` at `0x140040fd1`
- `KERNEL32!FindFirstFileW` at `0x140040e13`
- `KERNEL32!FindFirstFileW` at `0x140040e13`
- `KERNEL32!FindNextFileW` at `0x140040f56`
- `KERNEL32!FindNextFileW` at `0x140040f56`
- `KERNEL32!FindClose` at `0x140040f6d`
- `KERNEL32!FindClose` at `0x140040f6d`
- `KERNEL32!DeleteFileW` at `0x140040f00`
- `KERNEL32!DeleteFileW` at `0x140040f00`
- `KERNEL32!SetFileAttributesW` at `0x140040eb0`
- `KERNEL32!SetFileAttributesW` at `0x140040eb0`
- `KERNEL32!RemoveDirectoryW` at `0x140040f7c`
- `KERNEL32!RemoveDirectoryW` at `0x140040f7c`
- `msvcrt!_wcsicmp` at `0x140040e3c`
- `msvcrt!_wcsicmp` at `0x140040e5c`
- `msvcrt!_wcsicmp` at `0x140040e3c`
- `msvcrt!_wcsicmp` at `0x140040e5c`

## string_xrefs

- `0x140040dba`: `DeleteDirectory`
- `0x140040f32`: `DeleteDirectory`
- `0x140040fb9`: `DeleteDirectory`

## pseudocode

```c
__int64 __fastcall DeleteDirectory(const unsigned __int16 *a1)
{
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v3; // rax
  unsigned __int16 *v4; // rbp
  unsigned int v5; // ebx
  int v6; // eax
  char *FirstFileW; // rbx
  signed int v8; // eax
  int v9; // r9d
  char dwFileAttributes; // al
  bool v11; // sf
  bool v12; // sf
  signed int LastError; // eax
  HANDLE v14; // rax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-268h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  ProcessHeap = GetProcessHeap();
  v3 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x208u);
  v4 = v3;
  if ( v3 )
  {
    v6 = StringCchPrintfW(v3, 0x104u, L"%s\\*", a1);
    v5 = v6;
    if ( v6 < 0 )
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DeleteDirectory", 1258, v6);
LABEL_34:
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v4);
      return v5;
    }
    FirstFileW = (char *)FindFirstFileW(v4, &FindFileData);
    if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
LABEL_28:
      if ( RemoveDirectoryW(a1) )
      {
        v5 = 0;
      }
      else
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        if ( (v5 & 0x80000000) != 0 )
          SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DeleteDirectory", 1300, v5);
      }
      goto LABEL_34;
    }
    while ( 1 )
    {
      if ( !_wcsicmp(FindFileData.cFileName, L".") || !_wcsicmp(FindFileData.cFileName, L"..") )
        goto LABEL_26;
      v8 = StringCchPrintfW(v4, 0x104u, L"%s\\%s", a1, FindFileData.cFileName);
      if ( v8 < 0 )
        break;
      dwFileAttributes = FindFileData.dwFileAttributes;
      if ( (FindFileData.dwFileAttributes & 1) != 0 )
      {
        if ( !SetFileAttributesW(v4, 0x80u) )
        {
          v8 = GetLastError();
          v11 = v8 < 0;
          if ( v8 > 0 )
          {
            v8 = (unsigned __int16)v8 | 0x80070000;
            v11 = v8 < 0;
          }
          if ( v11 )
          {
            v9 = 1282;
            goto LABEL_25;
          }
        }
        dwFileAttributes = FindFileData.dwFileAttributes;
      }
      if ( (dwFileAttributes & 0x10) == 0 )
      {
        if ( DeleteFileW(v4) )
          goto LABEL_26;
        v8 = GetLastError();
        v12 = v8 < 0;
        if ( v8 > 0 )
        {
          v8 = (unsigned __int16)v8 | 0x80070000;
          v12 = v8 < 0;
        }
        if ( !v12 )
          goto LABEL_26;
        v9 = 1291;
        goto LABEL_25;
      }
      v8 = DeleteDirectory(v4);
      if ( v8 < 0 )
      {
        v9 = 1287;
        goto LABEL_25;
      }
LABEL_26:
      if ( !FindNextFileW(FirstFileW, &FindFileData) )
      {
        FindClose(FirstFileW);
        goto LABEL_28;
      }
    }
    v9 = 1275;
LABEL_25:
    SdpDebugPrint(1u, "Dwz WARNING: %s:%d - hr = 0x%08X\n", "DeleteDirectory", v9, v8);
    goto LABEL_26;
  }
  v5 = -2147024882;
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DeleteDirectory", 1255, -2147024882);
  return v5;
}

```

## disassembly

```asm
0x140040d50  mov     [rsp+arg_8], rbx
0x140040d55  mov     [rsp+arg_10], rbp
0x140040d5a  push    r14
0x140040d5c  sub     rsp, 290h
0x140040d63  mov     rax, cs:__security_cookie
0x140040d6a  xor     rax, rsp
0x140040d6d  mov     [rsp+298h+var_18], rax
0x140040d75  mov     r14, rcx
0x140040d78  xor     edx, edx; Val
0x140040d7a  lea     rcx, [rsp+298h+FindFileData]; void *
0x140040d7f  mov     r8d, 250h; Size
0x140040d85  call    memset_0
0x140040d8a  call    cs:__imp_GetProcessHeap
0x140040d91  nop     dword ptr [rax+rax+00h]
0x140040d96  xor     edx, edx; dwFlags
0x140040d98  mov     r8d, 208h; dwBytes
0x140040d9e  mov     rcx, rax; hHeap
0x140040da1  call    cs:__imp_HeapAlloc
0x140040da8  nop     dword ptr [rax+rax+00h]
0x140040dad  mov     rbp, rax
0x140040db0  test    rax, rax
0x140040db3  jnz     short loc_140040DDF
0x140040db5  mov     ebx, 8007000Eh
0x140040dba  lea     r8, aDeletedirector; "DeleteDirectory"
0x140040dc1  mov     r9d, 4E7h
0x140040dc7  mov     dword ptr [rsp+298h+var_278], ebx
0x140040dcb  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140040dd2  lea     ecx, [rax+1]; Level
0x140040dd5  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140040dda  jmp     loc_140040FF1
0x140040ddf  mov     r9, r14
0x140040de2  lea     r8, aS; "%s\\*"
0x140040de9  mov     edx, 104h; unsigned __int64
0x140040dee  mov     rcx, rbp; unsigned __int16 *
0x140040df1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140040df6  mov     ebx, eax
0x140040df8  test    eax, eax
0x140040dfa  jns     short loc_140040E0B
0x140040dfc  mov     dword ptr [rsp+298h+var_278], eax
0x140040e00  mov     r9d, 4EAh
0x140040e06  jmp     loc_140040FB9
0x140040e0b  lea     rdx, [rsp+298h+FindFileData]; lpFindFileData
0x140040e10  mov     rcx, rbp; lpFileName
0x140040e13  call    cs:__imp_FindFirstFileW
0x140040e1a  nop     dword ptr [rax+rax+00h]
0x140040e1f  mov     rbx, rax
0x140040e22  lea     rcx, [rax-1]
0x140040e26  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140040e2a  ja      loc_140040F79
0x140040e30  lea     rdx, asc_1400707D8; "."
0x140040e37  lea     rcx, [rsp+298h+FindFileData.cFileName]; String1
0x140040e3c  call    cs:__imp__wcsicmp
0x140040e43  nop     dword ptr [rax+rax+00h]
0x140040e48  test    eax, eax
0x140040e4a  jz      loc_140040F4E
0x140040e50  lea     rdx, asc_140070B9C; ".."
0x140040e57  lea     rcx, [rsp+298h+FindFileData.cFileName]; String1
0x140040e5c  call    cs:__imp__wcsicmp
0x140040e63  nop     dword ptr [rax+rax+00h]
0x140040e68  test    eax, eax
0x140040e6a  jz      loc_140040F4E
0x140040e70  lea     rax, [rsp+298h+FindFileData.cFileName]
0x140040e75  mov     r9, r14
0x140040e78  lea     r8, aSS_1; "%s\\%s"
0x140040e7f  mov     [rsp+298h+var_278], rax
0x140040e84  mov     edx, 104h; unsigned __int64
0x140040e89  mov     rcx, rbp; unsigned __int16 *
0x140040e8c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140040e91  test    eax, eax
0x140040e93  jns     short loc_140040EA0
0x140040e95  mov     r9d, 4FBh
0x140040e9b  jmp     loc_140040F32
0x140040ea0  mov     eax, [rsp+298h+FindFileData.dwFileAttributes]
0x140040ea4  test    al, 1
0x140040ea6  jz      short loc_140040EE8
0x140040ea8  mov     edx, 80h; dwFileAttributes
0x140040ead  mov     rcx, rbp; lpFileName
0x140040eb0  call    cs:__imp_SetFileAttributesW
0x140040eb7  nop     dword ptr [rax+rax+00h]
0x140040ebc  test    eax, eax
0x140040ebe  jnz     short loc_140040EE4
0x140040ec0  call    cs:__imp_GetLastError
0x140040ec7  nop     dword ptr [rax+rax+00h]
0x140040ecc  test    eax, eax
0x140040ece  jle     short loc_140040EDA
0x140040ed0  movzx   eax, ax
0x140040ed3  or      eax, 80070000h
0x140040ed8  test    eax, eax
0x140040eda  jns     short loc_140040EE4
0x140040edc  mov     r9d, 502h
0x140040ee2  jmp     short loc_140040F32
0x140040ee4  mov     eax, [rsp+298h+FindFileData.dwFileAttributes]
0x140040ee8  mov     rcx, rbp; unsigned __int16 *
0x140040eeb  test    al, 10h
0x140040eed  jz      short loc_140040F00
0x140040eef  call    ?DeleteDirectory@@YAJPEBG@Z; DeleteDirectory(ushort const *)
0x140040ef4  test    eax, eax
0x140040ef6  jns     short loc_140040F4E
0x140040ef8  mov     r9d, 507h
0x140040efe  jmp     short loc_140040F32
0x140040f00  call    cs:__imp_DeleteFileW
0x140040f07  nop     dword ptr [rax+rax+00h]
0x140040f0c  test    eax, eax
0x140040f0e  jnz     short loc_140040F4E
0x140040f10  call    cs:__imp_GetLastError
0x140040f17  nop     dword ptr [rax+rax+00h]
0x140040f1c  test    eax, eax
0x140040f1e  jle     short loc_140040F2A
0x140040f20  movzx   eax, ax
0x140040f23  or      eax, 80070000h
0x140040f28  test    eax, eax
0x140040f2a  jns     short loc_140040F4E
0x140040f2c  mov     r9d, 50Bh
0x140040f32  lea     r8, aDeletedirector; "DeleteDirectory"
0x140040f39  mov     dword ptr [rsp+298h+var_278], eax
0x140040f3d  lea     rdx, aDwzWarningSDHr; "Dwz WARNING: %s:%d - hr = 0x%08X\n"
0x140040f44  mov     ecx, 1; Level
0x140040f49  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140040f4e  lea     rdx, [rsp+298h+FindFileData]; lpFindFileData
0x140040f53  mov     rcx, rbx; hFindFile
0x140040f56  call    cs:__imp_FindNextFileW
0x140040f5d  nop     dword ptr [rax+rax+00h]
0x140040f62  test    eax, eax
0x140040f64  jnz     loc_140040E30
0x140040f6a  mov     rcx, rbx; hFindFile
0x140040f6d  call    cs:__imp_FindClose
0x140040f74  nop     dword ptr [rax+rax+00h]
0x140040f79  mov     rcx, r14; lpPathName
0x140040f7c  call    cs:__imp_RemoveDirectoryW
0x140040f83  nop     dword ptr [rax+rax+00h]
0x140040f88  test    eax, eax
0x140040f8a  jz      short loc_140040F90
0x140040f8c  xor     ebx, ebx
0x140040f8e  jmp     short loc_140040FD1
0x140040f90  call    cs:__imp_GetLastError
0x140040f97  nop     dword ptr [rax+rax+00h]
0x140040f9c  mov     ebx, eax
0x140040f9e  test    eax, eax
0x140040fa0  jle     short loc_140040FAB
0x140040fa2  movzx   ebx, ax
0x140040fa5  or      ebx, 80070000h
0x140040fab  test    ebx, ebx
0x140040fad  jns     short loc_140040FD1
0x140040faf  mov     dword ptr [rsp+298h+var_278], ebx
0x140040fb3  mov     r9d, 514h
0x140040fb9  lea     r8, aDeletedirector; "DeleteDirectory"
0x140040fc0  mov     ecx, 1; Level
0x140040fc5  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140040fcc  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140040fd1  call    cs:__imp_GetProcessHeap
0x140040fd8  nop     dword ptr [rax+rax+00h]
0x140040fdd  mov     r8, rbp; lpMem
0x140040fe0  xor     edx, edx; dwFlags
0x140040fe2  mov     rcx, rax; hHeap
0x140040fe5  call    cs:__imp_HeapFree
0x140040fec  nop     dword ptr [rax+rax+00h]
0x140040ff1  mov     eax, ebx
0x140040ff3  mov     rcx, [rsp+298h+var_18]
0x140040ffb  xor     rcx, rsp; StackCookie
0x140040ffe  call    __security_check_cookie
0x140041003  lea     r11, [rsp+298h+var_8]
0x14004100b  mov     rbx, [r11+18h]
0x14004100f  mov     rbp, [r11+20h]
0x140041013  mov     rsp, r11
0x140041016  pop     r14
0x140041018  retn
```
