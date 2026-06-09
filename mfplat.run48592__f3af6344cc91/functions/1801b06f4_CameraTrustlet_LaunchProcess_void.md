# CameraTrustlet::LaunchProcess(void)

- ea: `0x1801b06f4`
- end: `0x1801b0950`
- name: `?LaunchProcess@CameraTrustlet@@AEAAJXZ`
- size: `604`
- prototype: `__int64 __fastcall(CameraTrustlet *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801b022c`

## callees

- `0x1800214fc`
- `0x1800572d0`
- `0x18006f464`
- `0x1801200d0`
- `0x180120ecc`
- `0x1801250c8`
- `0x1801b06f4`
- `0x1801b0a54`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1801b0884`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1801b0884`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1801b0799`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1801b0799`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b088e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b088e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801b08e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801b08ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801b08e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801b08ef`

## pseudocode

```c
__int64 __fastcall CameraTrustlet::LaunchProcess(CameraTrustlet *this)
{
  unsigned int v2; // ebx
  __int64 v3; // rdx
  int v4; // eax
  __int64 v5; // rdx
  signed int LastError; // eax
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-B0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[264]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR CommandLine[264]; // [rsp+2F0h] [rbp+1F0h] BYREF

  if ( (unsigned __int8)byte_1801FD28D >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 43, &WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids, this);
  memset_0(Buffer, 0, 0x208u);
  memset_0(CommandLine, 0, 0x208u);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 > 0x103 )
  {
    v2 = -2147418113;
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_20;
    v3 = 44;
    goto LABEL_19;
  }
  StartupInfo.cb = 104;
  v4 = StringCchPrintfW(CommandLine, 0x104u, L"%s\\FsIso.exe %s", Buffer, (char *)this + 32);
  v2 = v4;
  if ( v4 < 0 )
  {
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_20;
    v5 = 45;
    goto LABEL_9;
  }
  v4 = StringCchCatW(Buffer, 0x104u, L"\\FsIso.exe");
  v2 = v4;
  if ( v4 < 0 )
  {
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_20;
    v5 = 46;
LABEL_9:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, &WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids, this, v4);
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
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_20;
      v3 = 47;
LABEL_19:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v3, &WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids, this, v2);
LABEL_20:
      if ( byte_1801FD28D )
        goto LABEL_23;
      return v2;
    }
  }
  CloseHandle(ProcessInformation.hProcess);
  CloseHandle(ProcessInformation.hThread);
  if ( (unsigned __int8)byte_1801FD28D >= 8u )
LABEL_23:
    WPP_SF_qDSS(*((_QWORD *)WPP_GLOBAL_Control + 27), v2, (__int64)Buffer, (__int64)CommandLine);
  return v2;
}

```

## disassembly

```asm
0x1801b06f4  push    rbp
0x1801b06f6  push    rbx
0x1801b06f7  push    rdi
0x1801b06f8  push    r14
0x1801b06fa  lea     rbp, [rsp-418h]
0x1801b0702  sub     rsp, 518h
0x1801b0709  mov     rax, cs:__security_cookie
0x1801b0710  xor     rax, rsp
0x1801b0713  mov     [rbp+430h+var_30], rax
0x1801b071a  mov     rdi, rcx
0x1801b071d  cmp     cs:byte_1801FD28D, 8
0x1801b0724  lea     r14, WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids
0x1801b072b  jb      short loc_1801B074B
0x1801b072d  mov     r9, rcx
0x1801b0730  mov     edx, 2Bh ; '+'
0x1801b0735  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b073c  mov     r8, r14
0x1801b073f  mov     rcx, [rcx+0D8h]
0x1801b0746  call    WPP_SF_q
0x1801b074b  mov     ebx, 208h
0x1801b0750  lea     rcx, [rbp+430h+Buffer]; void *
0x1801b0754  mov     r8d, ebx; Size
0x1801b0757  xor     edx, edx; Val
0x1801b0759  call    memset_0
0x1801b075e  mov     r8d, ebx; Size
0x1801b0761  lea     rcx, [rbp+430h+CommandLine]; void *
0x1801b0768  xor     edx, edx; Val
0x1801b076a  call    memset_0
0x1801b076f  xor     eax, eax
0x1801b0771  lea     rcx, [rsp+530h+StartupInfo]; void *
0x1801b0776  xorps   xmm0, xmm0
0x1801b0779  mov     qword ptr [rsp+530h+ProcessInformation.dwProcessId], rax
0x1801b077e  xor     edx, edx; Val
0x1801b0780  movups  xmmword ptr [rsp+530h+ProcessInformation.hProcess], xmm0
0x1801b0785  lea     ebx, [rax+68h]
0x1801b0788  mov     r8d, ebx; Size
0x1801b078b  call    memset_0
0x1801b0790  mov     edx, 104h; uSize
0x1801b0795  lea     rcx, [rbp+430h+Buffer]; lpBuffer
0x1801b0799  call    cs:__imp_GetSystemDirectoryW
0x1801b079f  dec     eax
0x1801b07a1  cmp     eax, 103h
0x1801b07a6  jbe     short loc_1801B07C4
0x1801b07a8  mov     ebx, 8000FFFFh
0x1801b07ad  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801b07b4  jb      loc_1801B08CF
0x1801b07ba  mov     edx, 2Ch ; ','
0x1801b07bf  jmp     loc_1801B08B5
0x1801b07c4  lea     rax, [rdi+20h]
0x1801b07c8  mov     [rsp+530h+StartupInfo.cb], ebx
0x1801b07cc  lea     r9, [rbp+430h+Buffer]
0x1801b07d0  mov     qword ptr [rsp+530h+bInheritHandles], rax
0x1801b07d5  lea     r8, aSFsisoExeS; "%s\\FsIso.exe %s"
0x1801b07dc  mov     edx, 104h; unsigned __int64
0x1801b07e1  lea     rcx, [rbp+430h+CommandLine]; unsigned __int16 *
0x1801b07e8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801b07ed  mov     ebx, eax
0x1801b07ef  test    eax, eax
0x1801b07f1  jns     short loc_1801B080E
0x1801b07f3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801b07fa  jb      loc_1801B08CF
0x1801b0800  mov     edx, 2Dh ; '-'
0x1801b0805  mov     [rsp+530h+bInheritHandles], eax
0x1801b0809  jmp     loc_1801B08B9
0x1801b080e  lea     r8, aFsisoExe; "\\FsIso.exe"
0x1801b0815  mov     edx, 104h; unsigned __int64
0x1801b081a  lea     rcx, [rbp+430h+Buffer]; unsigned __int16 *
0x1801b081e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801b0823  mov     ebx, eax
0x1801b0825  test    eax, eax
0x1801b0827  jns     short loc_1801B083D
0x1801b0829  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801b0830  jb      loc_1801B08CF
0x1801b0836  mov     edx, 2Eh ; '.'
0x1801b083b  jmp     short loc_1801B0805
0x1801b083d  lea     rax, [rsp+530h+ProcessInformation]
0x1801b0842  xor     r9d, r9d; lpThreadAttributes
0x1801b0845  mov     [rsp+530h+lpProcessInformation], rax; lpProcessInformation
0x1801b084a  lea     rdx, [rbp+430h+CommandLine]; lpCommandLine
0x1801b0851  lea     rax, [rsp+530h+StartupInfo]
0x1801b0856  xor     r8d, r8d; lpProcessAttributes
0x1801b0859  mov     [rsp+530h+lpStartupInfo], rax; lpStartupInfo
0x1801b085e  lea     rcx, [rbp+430h+Buffer]; lpApplicationName
0x1801b0862  mov     [rsp+530h+lpCurrentDirectory], 0; lpCurrentDirectory
0x1801b086b  mov     [rsp+530h+lpEnvironment], 0; lpEnvironment
0x1801b0874  mov     [rsp+530h+dwCreationFlags], 400100h; dwCreationFlags
0x1801b087c  mov     [rsp+530h+bInheritHandles], 0; bInheritHandles
0x1801b0884  call    cs:__imp_CreateProcessW
0x1801b088a  test    eax, eax
0x1801b088c  jnz     short loc_1801B08DF
0x1801b088e  call    cs:__imp_GetLastError
0x1801b0894  mov     ebx, eax
0x1801b0896  test    eax, eax
0x1801b0898  jle     short loc_1801B08A3
0x1801b089a  movzx   ebx, ax
0x1801b089d  or      ebx, 80070000h
0x1801b08a3  test    ebx, ebx
0x1801b08a5  jns     short loc_1801B08DF
0x1801b08a7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801b08ae  jb      short loc_1801B08CF
0x1801b08b0  mov     edx, 2Fh ; '/'
0x1801b08b5  mov     [rsp+530h+bInheritHandles], ebx
0x1801b08b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b08c0  mov     r9, rdi
0x1801b08c3  mov     r8, r14
0x1801b08c6  mov     rcx, [rcx+10h]
0x1801b08ca  call    WPP_SF_qD
0x1801b08cf  cmp     cs:byte_1801FD28D, 1
0x1801b08d6  jb      short loc_1801B0932
0x1801b08d8  mov     edx, 30h ; '0'
0x1801b08dd  jmp     short loc_1801B0903
0x1801b08df  mov     rcx, [rsp+530h+ProcessInformation.hProcess]; hObject
0x1801b08e4  call    cs:__imp_CloseHandle
0x1801b08ea  mov     rcx, [rsp+530h+ProcessInformation.hThread]; hObject
0x1801b08ef  call    cs:__imp_CloseHandle
0x1801b08f5  cmp     cs:byte_1801FD28D, 8
0x1801b08fc  jb      short loc_1801B0932
0x1801b08fe  mov     edx, 31h ; '1'
0x1801b0903  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b090a  lea     rax, [rbp+430h+CommandLine]
0x1801b0911  mov     [rsp+530h+lpEnvironment], rax; __int64
0x1801b0916  mov     r9, rdi
0x1801b0919  lea     rax, [rbp+430h+Buffer]
0x1801b091d  mov     qword ptr [rsp+530h+dwCreationFlags], rax; __int64
0x1801b0922  mov     rcx, [rcx+0D8h]; LoggerHandle
0x1801b0929  mov     [rsp+530h+bInheritHandles], ebx; char
0x1801b092d  call    WPP_SF_qDSS
0x1801b0932  mov     eax, ebx
0x1801b0934  mov     rcx, [rbp+430h+var_30]
0x1801b093b  xor     rcx, rsp; StackCookie
0x1801b093e  call    __security_check_cookie
0x1801b0943  add     rsp, 518h
0x1801b094a  pop     r14
0x1801b094c  pop     rdi
0x1801b094d  pop     rbx
0x1801b094e  pop     rbp
0x1801b094f  retn
```
