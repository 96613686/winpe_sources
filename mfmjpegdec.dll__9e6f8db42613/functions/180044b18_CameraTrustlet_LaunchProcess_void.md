# CameraTrustlet::LaunchProcess(void)

- ea: `0x180044b18`
- end: `0x180044d6f`
- name: `?LaunchProcess@CameraTrustlet@@AEAAJXZ`
- size: `599`
- prototype: `__int64 __fastcall(CameraTrustlet *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001ef40`

## callees

- `0x180024220`
- `0x180024bf4`
- `0x18003d510`
- `0x18003d58c`
- `0x180044b18`
- `0x180044d78`
- `0x180044f10`
- `0x180045060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044cad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044cad`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180044ca3`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180044ca3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044d03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044d0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044d03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044d0e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180044bbd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180044bbd`

## pseudocode

```c
__int64 __fastcall CameraTrustlet::LaunchProcess(CameraTrustlet *this)
{
  unsigned int v2; // ebx
  __int64 v3; // rdx
  int v4; // eax
  unsigned __int64 v5; // rdx
  __int64 v6; // rdx
  signed int LastError; // eax
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-B0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[264]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR CommandLine[264]; // [rsp+2F0h] [rbp+1F0h] BYREF

  if ( (unsigned __int8)byte_18009D825 >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 43, &WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids, this);
  memset_0(Buffer, 0, 0x208u);
  memset_0(CommandLine, 0, 0x208u);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 > 0x103 )
  {
    v2 = -2147418113;
    if ( !g_wppLevels )
      goto LABEL_20;
    v3 = 44;
    goto LABEL_19;
  }
  StartupInfo.cb = 104;
  v4 = StringCchPrintfW(CommandLine, 0x104u, L"%s\\FsIso.exe %s", Buffer, (char *)this + 32);
  v2 = v4;
  if ( v4 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_20;
    v6 = 45;
    goto LABEL_9;
  }
  v4 = StringCchCatW(Buffer, v5, L"\\FsIso.exe");
  v2 = v4;
  if ( v4 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_20;
    v6 = 46;
LABEL_9:
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids, this, v4);
    goto LABEL_20;
  }
  if ( !CreateProcessW(Buffer, CommandLine, 0, 0, 0, 0x400100u, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( (v2 & 0x80000000) != 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_20;
      v3 = 47;
LABEL_19:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v3, &WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids, this, v2);
LABEL_20:
      if ( byte_18009D825 )
        goto LABEL_23;
      return v2;
    }
  }
  CloseHandle(ProcessInformation.hProcess);
  CloseHandle(ProcessInformation.hThread);
  if ( (unsigned __int8)byte_18009D825 >= 8u )
LABEL_23:
    WPP_SF_qDSS(*((_QWORD *)WPP_GLOBAL_Control + 27), v2, (__int64)Buffer, (__int64)CommandLine);
  return v2;
}

```

## disassembly

```asm
0x180044b18  push    rbp
0x180044b1a  push    rbx
0x180044b1b  push    rdi
0x180044b1c  push    r14
0x180044b1e  lea     rbp, [rsp-418h]
0x180044b26  sub     rsp, 518h
0x180044b2d  mov     rax, cs:__security_cookie
0x180044b34  xor     rax, rsp
0x180044b37  mov     [rbp+430h+var_30], rax
0x180044b3e  mov     rdi, rcx
0x180044b41  cmp     cs:byte_18009D825, 8
0x180044b48  lea     r14, WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids
0x180044b4f  jb      short loc_180044B6F
0x180044b51  mov     r9, rcx
0x180044b54  mov     edx, 2Bh ; '+'
0x180044b59  mov     rcx, cs:WPP_GLOBAL_Control
0x180044b60  mov     r8, r14
0x180044b63  mov     rcx, [rcx+0D8h]
0x180044b6a  call    WPP_SF_q
0x180044b6f  mov     ebx, 208h
0x180044b74  lea     rcx, [rbp+430h+Buffer]; void *
0x180044b78  mov     r8d, ebx; Size
0x180044b7b  xor     edx, edx; Val
0x180044b7d  call    memset_0
0x180044b82  mov     r8d, ebx; Size
0x180044b85  lea     rcx, [rbp+430h+CommandLine]; void *
0x180044b8c  xor     edx, edx; Val
0x180044b8e  call    memset_0
0x180044b93  xor     eax, eax
0x180044b95  lea     rcx, [rsp+530h+StartupInfo]; void *
0x180044b9a  xorps   xmm0, xmm0
0x180044b9d  mov     qword ptr [rsp+530h+ProcessInformation.dwProcessId], rax
0x180044ba2  xor     edx, edx; Val
0x180044ba4  movups  xmmword ptr [rsp+530h+ProcessInformation.hProcess], xmm0
0x180044ba9  lea     ebx, [rax+68h]
0x180044bac  mov     r8d, ebx; Size
0x180044baf  call    memset_0
0x180044bb4  mov     edx, 104h; uSize
0x180044bb9  lea     rcx, [rbp+430h+Buffer]; lpBuffer
0x180044bbd  call    cs:__imp_GetSystemDirectoryW
0x180044bc3  dec     eax
0x180044bc5  cmp     eax, 103h
0x180044bca  jbe     short loc_180044BE8
0x180044bcc  mov     ebx, 8000FFFFh
0x180044bd1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180044bd8  jb      loc_180044CEE
0x180044bde  mov     edx, 2Ch ; ','
0x180044be3  jmp     loc_180044CD4
0x180044be8  lea     rax, [rdi+20h]
0x180044bec  mov     [rsp+530h+StartupInfo.cb], ebx
0x180044bf0  lea     r9, [rbp+430h+Buffer]
0x180044bf4  mov     qword ptr [rsp+530h+bInheritHandles], rax
0x180044bf9  lea     r8, aSFsisoExeS; "%s\\FsIso.exe %s"
0x180044c00  mov     edx, 104h; unsigned __int64
0x180044c05  lea     rcx, [rbp+430h+CommandLine]; unsigned __int16 *
0x180044c0c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180044c11  mov     ebx, eax
0x180044c13  test    eax, eax
0x180044c15  jns     short loc_180044C32
0x180044c17  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180044c1e  jb      loc_180044CEE
0x180044c24  mov     edx, 2Dh ; '-'
0x180044c29  mov     [rsp+530h+bInheritHandles], eax
0x180044c2d  jmp     loc_180044CD8
0x180044c32  lea     r8, aFsisoExe; "\\FsIso.exe"
0x180044c39  lea     rcx, [rbp+430h+Buffer]; unsigned __int16 *
0x180044c3d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180044c42  mov     ebx, eax
0x180044c44  test    eax, eax
0x180044c46  jns     short loc_180044C5C
0x180044c48  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180044c4f  jb      loc_180044CEE
0x180044c55  mov     edx, 2Eh ; '.'
0x180044c5a  jmp     short loc_180044C29
0x180044c5c  lea     rax, [rsp+530h+ProcessInformation]
0x180044c61  xor     r9d, r9d; lpThreadAttributes
0x180044c64  mov     [rsp+530h+lpProcessInformation], rax; lpProcessInformation
0x180044c69  lea     rdx, [rbp+430h+CommandLine]; lpCommandLine
0x180044c70  lea     rax, [rsp+530h+StartupInfo]
0x180044c75  xor     r8d, r8d; lpProcessAttributes
0x180044c78  mov     [rsp+530h+lpStartupInfo], rax; lpStartupInfo
0x180044c7d  lea     rcx, [rbp+430h+Buffer]; lpApplicationName
0x180044c81  mov     [rsp+530h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180044c8a  mov     [rsp+530h+lpEnvironment], 0; lpEnvironment
0x180044c93  mov     [rsp+530h+dwCreationFlags], 400100h; dwCreationFlags
0x180044c9b  mov     [rsp+530h+bInheritHandles], 0; bInheritHandles
0x180044ca3  call    cs:__imp_CreateProcessW
0x180044ca9  test    eax, eax
0x180044cab  jnz     short loc_180044CFE
0x180044cad  call    cs:__imp_GetLastError
0x180044cb3  mov     ebx, eax
0x180044cb5  test    eax, eax
0x180044cb7  jle     short loc_180044CC2
0x180044cb9  movzx   ebx, ax
0x180044cbc  or      ebx, 80070000h
0x180044cc2  test    ebx, ebx
0x180044cc4  jns     short loc_180044CFE
0x180044cc6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180044ccd  jb      short loc_180044CEE
0x180044ccf  mov     edx, 2Fh ; '/'
0x180044cd4  mov     [rsp+530h+bInheritHandles], ebx
0x180044cd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180044cdf  mov     r9, rdi
0x180044ce2  mov     r8, r14
0x180044ce5  mov     rcx, [rcx+10h]
0x180044ce9  call    WPP_SF_qd
0x180044cee  cmp     cs:byte_18009D825, 1
0x180044cf5  jb      short loc_180044D51
0x180044cf7  mov     edx, 30h ; '0'
0x180044cfc  jmp     short loc_180044D22
0x180044cfe  mov     rcx, [rsp+530h+ProcessInformation.hProcess]; hObject
0x180044d03  call    cs:__imp_CloseHandle
0x180044d09  mov     rcx, [rsp+530h+ProcessInformation.hThread]; hObject
0x180044d0e  call    cs:__imp_CloseHandle
0x180044d14  cmp     cs:byte_18009D825, 8
0x180044d1b  jb      short loc_180044D51
0x180044d1d  mov     edx, 31h ; '1'
0x180044d22  mov     rcx, cs:WPP_GLOBAL_Control
0x180044d29  lea     rax, [rbp+430h+CommandLine]
0x180044d30  mov     [rsp+530h+lpEnvironment], rax; __int64
0x180044d35  mov     r9, rdi
0x180044d38  lea     rax, [rbp+430h+Buffer]
0x180044d3c  mov     qword ptr [rsp+530h+dwCreationFlags], rax; __int64
0x180044d41  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180044d48  mov     [rsp+530h+bInheritHandles], ebx; char
0x180044d4c  call    WPP_SF_qDSS
0x180044d51  mov     eax, ebx
0x180044d53  mov     rcx, [rbp+430h+var_30]
0x180044d5a  xor     rcx, rsp; StackCookie
0x180044d5d  call    __security_check_cookie
0x180044d62  add     rsp, 518h
0x180044d69  pop     r14
0x180044d6b  pop     rdi
0x180044d6c  pop     rbx
0x180044d6d  pop     rbp
0x180044d6e  retn
```
