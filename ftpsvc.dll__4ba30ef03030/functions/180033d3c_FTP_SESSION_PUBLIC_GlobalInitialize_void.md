# FTP_SESSION_PUBLIC::GlobalInitialize(void)

- ea: `0x180033d3c`
- end: `0x180033ebb`
- name: `?GlobalInitialize@FTP_SESSION_PUBLIC@@SAJXZ`
- size: `383`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800029fc`

## callees

- `0x180001210`
- `0x180033d3c`
- `0x180033ec4`
- `0x18003e17c`
- `0x18003ec20`
- `0x180047050`

## import_xrefs

- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x180033d90`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x180033dec`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x180033d90`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x180033dec`
- `iisutil!PuDbgPrintError` at `0x180033e49`
- `iisutil!PuDbgPrintError` at `0x180033e9b`
- `iisutil!PuDbgPrintError` at `0x180033e49`
- `iisutil!PuDbgPrintError` at `0x180033e9b`

## string_xrefs

- `0x180033e3b`: `inetsrv\iis\iisrearc\ftp\server\ftp_protocol\ftp_session.cxx`
- `0x180033e8d`: `inetsrv\iis\iisrearc\ftp\server\ftp_protocol\ftp_session.cxx`
- `0x180033e1e`: `Failed to initialize FTP_COMMAND\n`
- `0x180033de2`: `FTP_COMMAND`

## pseudocode

```c
__int64 FTP_SESSION_PUBLIC::GlobalInitialize(void)
{
  ALLOC_CACHE_HANDLER *v0; // rax
  ALLOC_CACHE_HANDLER *v1; // rax
  int HostNameSupportConfig; // ebx
  ALLOC_CACHE_HANDLER *v4; // [rsp+30h] [rbp-28h]
  ALLOC_CACHE_HANDLER *v5; // [rsp+30h] [rbp-28h]
  __int64 v6; // [rsp+38h] [rbp-20h] BYREF
  __int64 v7; // [rsp+40h] [rbp-18h]

  v6 = 0x6400000001LL;
  LODWORD(v7) = 5896;
  v0 = (ALLOC_CACHE_HANDLER *)operator new(0x100u);
  v4 = v0;
  if ( v0 )
    v0 = ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(v0, "FTP_SESSION", (const struct ALLOC_CACHE_CONFIGURATION *)&v6, 1);
  FTP_SESSION::sm_pAllocHandler = v0;
  if ( !v0 )
  {
    HostNameSupportConfig = -2147024888;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_protocol\\ftp_session.cxx",
        77,
        "FTP_SESSION_PUBLIC::GlobalInitialize",
        -2147024888,
        "Failed to initialize FTP_SESSION\n",
        v4,
        v6,
        v7);
    goto LABEL_16;
  }
  FTP_SESSION::sm_pRefTraceLog = 0;
  v6 = 0x6400000001LL;
  LODWORD(v7) = 1760;
  v1 = (ALLOC_CACHE_HANDLER *)operator new(0x100u);
  v5 = v1;
  if ( v1 )
    v1 = ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(v1, "FTP_COMMAND", (const struct ALLOC_CACHE_CONFIGURATION *)&v6, 1);
  FTP_COMMAND::sm_pAllocHandler = v1;
  if ( v1 )
  {
    HostNameSupportConfig = FTP_COMMAND::ReadHostNameSupportConfig();
    if ( HostNameSupportConfig >= 0 )
    {
      HostNameSupportConfig = FTP_COMMAND_TABLE::GlobalInitialize();
      goto LABEL_12;
    }
  }
  else
  {
    HostNameSupportConfig = -2147024888;
  }
  if ( (g_dwDebugFlags & 0xF) == 0 )
  {
LABEL_16:
    FTP_SESSION_PUBLIC::GlobalTerminate();
    return (unsigned int)HostNameSupportConfig;
  }
  PuDbgPrintError(
    g_pDebug,
    "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_protocol\\ftp_session.cxx",
    88,
    "FTP_SESSION_PUBLIC::GlobalInitialize",
    HostNameSupportConfig,
    "Failed to initialize FTP_COMMAND\n",
    v5);
LABEL_12:
  if ( HostNameSupportConfig < 0 )
    goto LABEL_16;
  return (unsigned int)HostNameSupportConfig;
}

```

## disassembly

```asm
0x180033d3c  push    rbx
0x180033d3e  sub     rsp, 50h
0x180033d42  mov     rax, cs:__security_cookie
0x180033d49  xor     rax, rsp
0x180033d4c  mov     [rsp+58h+var_10], rax
0x180033d51  mov     ebx, 1
0x180033d56  mov     [rsp+58h+var_20], ebx
0x180033d5a  mov     [rsp+58h+var_1C], 64h ; 'd'
0x180033d62  mov     dword ptr [rsp+58h+var_18], 1708h
0x180033d6a  mov     ecx, 100h; Size
0x180033d6f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180033d74  mov     [rsp+58h+var_28], rax
0x180033d79  test    rax, rax
0x180033d7c  jz      short loc_180033D97
0x180033d7e  mov     r9d, ebx
0x180033d81  lea     r8, [rsp+58h+var_20]
0x180033d86  lea     rdx, aFtpSession; "FTP_SESSION"
0x180033d8d  mov     rcx, rax
0x180033d90  call    cs:__imp_??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x180033d96  nop
0x180033d97  mov     cs:?sm_pAllocHandler@FTP_SESSION@@0PEAVALLOC_CACHE_HANDLER@@EA, rax; ALLOC_CACHE_HANDLER * FTP_SESSION::sm_pAllocHandler
0x180033d9e  test    rax, rax
0x180033da1  jz      loc_180033E5E
0x180033da7  mov     cs:?sm_pRefTraceLog@FTP_SESSION@@0PEAU_TRACE_LOG@@EA, 0; _TRACE_LOG * FTP_SESSION::sm_pRefTraceLog
0x180033db2  mov     [rsp+58h+var_20], ebx
0x180033db6  mov     [rsp+58h+var_1C], 64h ; 'd'
0x180033dbe  mov     dword ptr [rsp+58h+var_18], 6E0h
0x180033dc6  mov     ecx, 100h; Size
0x180033dcb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180033dd0  mov     [rsp+58h+var_28], rax
0x180033dd5  test    rax, rax
0x180033dd8  jz      short loc_180033DF3
0x180033dda  mov     r9d, ebx
0x180033ddd  lea     r8, [rsp+58h+var_20]
0x180033de2  lea     rdx, aFtpCommand; "FTP_COMMAND"
0x180033de9  mov     rcx, rax
0x180033dec  call    cs:__imp_??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x180033df2  nop
0x180033df3  mov     cs:?sm_pAllocHandler@FTP_COMMAND@@0PEAVALLOC_CACHE_HANDLER@@EA, rax; ALLOC_CACHE_HANDLER * FTP_COMMAND::sm_pAllocHandler
0x180033dfa  test    rax, rax
0x180033dfd  jnz     short loc_180033E06
0x180033dff  mov     ebx, 80070008h
0x180033e04  jmp     short loc_180033E11
0x180033e06  call    ?ReadHostNameSupportConfig@FTP_COMMAND@@SAJXZ; FTP_COMMAND::ReadHostNameSupportConfig(void)
0x180033e0b  mov     ebx, eax
0x180033e0d  test    eax, eax
0x180033e0f  jns     short loc_180033E51
0x180033e11  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180033e18  jz      loc_180033EA1
0x180033e1e  lea     rax, aFailedToInitia_13; "Failed to initialize FTP_COMMAND\n"
0x180033e25  mov     [rsp+58h+var_30], rax
0x180033e2a  mov     [rsp+58h+var_38], ebx
0x180033e2e  lea     r9, aFtpSessionPubl; "FTP_SESSION_PUBLIC::GlobalInitialize"
0x180033e35  mov     r8d, 58h ; 'X'
0x180033e3b  lea     rdx, aInetsrvIisIisr_30; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x180033e42  mov     rcx, cs:g_pDebug
0x180033e49  call    cs:__imp_PuDbgPrintError
0x180033e4f  jmp     short loc_180033E58
0x180033e51  call    ?GlobalInitialize@FTP_COMMAND_TABLE@@SAJXZ; FTP_COMMAND_TABLE::GlobalInitialize(void)
0x180033e56  mov     ebx, eax
0x180033e58  test    ebx, ebx
0x180033e5a  jns     short loc_180033EA6
0x180033e5c  jmp     short loc_180033EA1
0x180033e5e  mov     ebx, 80070008h
0x180033e63  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180033e6a  jz      short loc_180033EA1
0x180033e6c  lea     rax, aFailedToInitia_7; "Failed to initialize FTP_SESSION\n"
0x180033e73  mov     [rsp+58h+var_30], rax
0x180033e78  mov     [rsp+58h+var_38], 80070008h
0x180033e80  lea     r9, aFtpSessionPubl; "FTP_SESSION_PUBLIC::GlobalInitialize"
0x180033e87  mov     r8d, 4Dh ; 'M'
0x180033e8d  lea     rdx, aInetsrvIisIisr_30; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x180033e94  mov     rcx, cs:g_pDebug
0x180033e9b  call    cs:__imp_PuDbgPrintError
0x180033ea1  call    ?GlobalTerminate@FTP_SESSION_PUBLIC@@SAXXZ; FTP_SESSION_PUBLIC::GlobalTerminate(void)
0x180033ea6  mov     eax, ebx
0x180033ea8  mov     rcx, [rsp+58h+var_10]
0x180033ead  xor     rcx, rsp; StackCookie
0x180033eb0  call    __security_check_cookie
0x180033eb5  add     rsp, 50h
0x180033eb9  pop     rbx
0x180033eba  retn
```
