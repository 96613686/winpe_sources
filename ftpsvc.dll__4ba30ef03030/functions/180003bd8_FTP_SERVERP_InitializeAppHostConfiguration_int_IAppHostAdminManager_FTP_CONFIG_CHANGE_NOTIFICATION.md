# FTP_SERVERP::InitializeAppHostConfiguration(int,IAppHostAdminManager * *,FTP_CONFIG_CHANGE_NOTIFICATION * *)

- ea: `0x180003bd8`
- end: `0x180003f70`
- name: `?InitializeAppHostConfiguration@FTP_SERVERP@@AEAAJHPEAPEAUIAppHostAdminManager@@PEAPEAVFTP_CONFIG_CHANGE_NOTIFICATION@@@Z`
- size: `920`
- prototype: `__int64 __fastcall(FTP_SERVERP *__hidden this, int, struct IAppHostAdminManager **, struct FTP_CONFIG_CHANGE_NOTIFICATION **)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800029fc`
- `0x180004610`

## callees

- `0x180001210`
- `0x180003bd8`
- `0x18002b6c4`
- `0x18002b788`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x180003d1a`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180003d63`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180003d1a`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180003d63`
- `KERNEL32!GetLastError` at `0x180003d3a`
- `KERNEL32!GetLastError` at `0x180003d3a`
- `ole32!CoCreateInstance` at `0x180003c2c`
- `ole32!CoCreateInstance` at `0x180003c2c`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180003c9d`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180003c9d`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180003e8c`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180003e8c`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180003eef`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180003eef`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003d81`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003d81`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003d75`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003d75`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003d30`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003d30`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003cd3`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003cd3`
- `iisutil!PuDbgPrintError` at `0x180003c6c`
- `iisutil!PuDbgPrintError` at `0x180003dbf`
- `iisutil!PuDbgPrintError` at `0x180003ed8`
- `iisutil!PuDbgPrintError` at `0x180003f4a`
- `iisutil!PuDbgPrintError` at `0x180003c6c`
- `iisutil!PuDbgPrintError` at `0x180003dbf`
- `iisutil!PuDbgPrintError` at `0x180003ed8`
- `iisutil!PuDbgPrintError` at `0x180003f4a`

## string_xrefs

- `0x180003c41`: `Could not initialize app host config reader\n`
- `0x180003c51`: `FTP_SERVERP::InitializeAppHostConfiguration`
- `0x180003da6`: `FTP_SERVERP::InitializeAppHostConfiguration`
- `0x180003ebd`: `FTP_SERVERP::InitializeAppHostConfiguration`
- `0x180003f2f`: `FTP_SERVERP::InitializeAppHostConfiguration`
- `0x180003d94`: `Config reader path mapper initialization failed\n`
- `0x180003e04`: `Could not configure app host config reader path mapper\n`
- `0x180003d13`: `%windir%\system32\inetsrv\ftp_config\ftp.config`
- `0x180003d5c`: `%windir%\system32\inetsrv\ftp_config\ftp.config`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FTP_SERVERP::InitializeAppHostConfiguration(
        FTP_SERVERP *this,
        int a2,
        struct IAppHostAdminManager **a3,
        struct IAppHostChangeHandler **a4)
{
  int Instance; // ebx
  unsigned int v9; // edx
  struct IAppHostPathMapper *v10; // rdi
  DWORD v11; // eax
  signed int LastError; // eax
  struct IAppHostAdminManagerVtbl *lpVtbl; // rax
  struct IAppHostPathMapper *v14; // rax
  struct IAppHostChangeHandler *v15; // rdi
  struct IAppHostAdminManager *ppv; // [rsp+30h] [rbp-50h] BYREF
  struct IAppHostPathMapper *v18; // [rsp+38h] [rbp-48h]
  WCHAR Dst[16]; // [rsp+40h] [rbp-40h] BYREF
  LPWSTR lpDst; // [rsp+60h] [rbp-20h]
  unsigned int v21; // [rsp+68h] [rbp-18h]
  __int16 v22; // [rsp+6Ch] [rbp-14h]

  ppv = 0;
  Instance = CoCreateInstance(&CLSID_AppHostAdminManager, 0, 1u, &IID_IAppHostAdminManager, (LPVOID *)&ppv);
  if ( Instance < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_serverp.cxx",
        1938,
        "FTP_SERVERP::InitializeAppHostConfiguration",
        Instance,
        "Could not initialize app host config reader\n");
    if ( Instance == -2147221231 || (v9 = -1073741785, Instance == -2147221164) )
      v9 = -1073741786;
    EVENT_LOG::LogEvent((EVENT_LOG *)FTP_LOG_NT_EVENT::sm_pEventLog, v9, 0, 0, Instance);
    return (unsigned int)Instance;
  }
  v10 = (struct IAppHostPathMapper *)operator new(0x48u);
  v18 = v10;
  if ( v10 )
  {
    v10->lpVtbl = (struct IAppHostPathMapperVtbl *)&FTP_CONFIG_PATH_MAPPER::`vftable';
    LODWORD(v10[1].lpVtbl) = 1;
    STRU::STRU(&v10[2]);
  }
  else
  {
    v10 = 0;
  }
  if ( !v10 )
    return (unsigned int)-2147024888;
  *(_QWORD *)Dst = 0;
  lpDst = Dst;
  v21 = 32;
  v22 = 256;
  v11 = ExpandEnvironmentStringsW(L"%windir%\\system32\\inetsrv\\ftp_config\\ftp.config", Dst, 0x10u);
  if ( v11 > v21 >> 1 )
  {
    if ( !BUFFER::Resize((BUFFER *)Dst, 2 * v11) )
      goto LABEL_15;
    v11 = ExpandEnvironmentStringsW(L"%windir%\\system32\\inetsrv\\ftp_config\\ftp.config", lpDst, v21 >> 1);
  }
  if ( v11 )
  {
    Instance = STRU::Copy((STRU *)&v10[2], lpDst);
    goto LABEL_20;
  }
LABEL_15:
  LastError = GetLastError();
  Instance = LastError;
  if ( LastError > 0 )
    Instance = (unsigned __int16)LastError | 0x80070000;
LABEL_20:
  BUFFER::~BUFFER((BUFFER *)Dst);
  if ( Instance < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_serverp.cxx",
        1987,
        "FTP_SERVERP::InitializeAppHostConfiguration",
        Instance,
        "Config reader path mapper initialization failed\n");
LABEL_23:
    ((void (__fastcall *)(struct IAppHostPathMapper *))v10->lpVtbl->Release)(v10);
    lpVtbl = ppv->lpVtbl;
LABEL_24:
    ((void (*)(void))lpVtbl->Release)();
    return (unsigned int)Instance;
  }
  Instance = Config_SetPathMapper(ppv, v10);
  if ( Instance < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_serverp.cxx",
        2006,
        "FTP_SERVERP::InitializeAppHostConfiguration",
        Instance,
        "Could not configure app host config reader path mapper\n");
    goto LABEL_23;
  }
  ((void (__fastcall *)(struct IAppHostPathMapper *))v10->lpVtbl->Release)(v10);
  if ( a2 )
    *((_DWORD *)this + 2) = 17;
  v14 = (struct IAppHostPathMapper *)operator new(0x20u);
  v15 = (struct IAppHostChangeHandler *)v14;
  v18 = v14;
  if ( v14 )
  {
    v14->lpVtbl = (struct IAppHostPathMapperVtbl *)&FTP_CONFIG_CHANGE_NOTIFICATION::`vftable';
    v14[1].lpVtbl = (struct IAppHostPathMapperVtbl *)1;
    LODWORD(v14[2].lpVtbl) = 0;
    HIDWORD(v14[2].lpVtbl) = 0;
    LODWORD(v14[3].lpVtbl) = 0;
    if ( a2 )
      *((_DWORD *)this + 2) = 18;
    LODWORD(v14[2].lpVtbl) = 1;
    CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)((char *)&v14[2].lpVtbl + 4));
    Instance = Config_SetChangeHandler(ppv, v15);
    if ( Instance >= 0 )
    {
      *a3 = ppv;
      *a4 = v15;
      return (unsigned int)Instance;
    }
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_serverp.cxx",
        2060,
        "FTP_SERVERP::InitializeAppHostConfiguration",
        Instance,
        "Failed to register change listener");
    if ( LODWORD(v15[2].lpVtbl) )
    {
      LODWORD(v15[2].lpVtbl) = 0;
      CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)((char *)&v15[2].lpVtbl + 4));
    }
    lpVtbl = (struct IAppHostAdminManagerVtbl *)v15->lpVtbl;
    goto LABEL_24;
  }
  Instance = -2147024888;
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_serverp.cxx",
      2037,
      "FTP_SERVERP::InitializeAppHostConfiguration",
      -2147024888,
      "Failed to allocate memory for change listener\n");
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180003bd8  push    rbp
0x180003bda  push    rbx
0x180003bdb  push    rsi
0x180003bdc  push    rdi
0x180003bdd  push    r12
0x180003bdf  push    r14
0x180003be1  push    r15
0x180003be3  mov     rbp, rsp
0x180003be6  sub     rsp, 80h
0x180003bed  mov     rax, cs:__security_cookie
0x180003bf4  xor     rax, rsp
0x180003bf7  mov     [rbp+var_10], rax
0x180003bfb  mov     r12, r9
0x180003bfe  mov     r15, r8
0x180003c01  mov     r14d, edx
0x180003c04  mov     rsi, rcx
0x180003c07  mov     [rbp+var_50], 0
0x180003c0f  lea     rax, [rbp+var_50]
0x180003c13  mov     [rsp+80h+ppv], rax; ppv
0x180003c18  lea     r9, IID_IAppHostAdminManager; riid
0x180003c1f  xor     edx, edx; pUnkOuter
0x180003c21  lea     r8d, [rdx+1]; dwClsContext
0x180003c25  lea     rcx, CLSID_AppHostAdminManager; rclsid
0x180003c2c  call    cs:__imp_CoCreateInstance
0x180003c32  mov     ebx, eax
0x180003c34  test    eax, eax
0x180003c36  jns     short loc_180003CA8
0x180003c38  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003c3f  jz      short loc_180003C72
0x180003c41  lea     rax, aCouldNotInitia_0; "Could not initialize app host config re"...
0x180003c48  mov     [rsp+80h+var_58], rax
0x180003c4d  mov     dword ptr [rsp+80h+ppv], ebx
0x180003c51  lea     r9, aFtpServerpInit_0; "FTP_SERVERP::InitializeAppHostConfigura"...
0x180003c58  mov     r8d, 792h
0x180003c5e  lea     rdx, aInetsrvIisIisr_23; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x180003c65  mov     rcx, cs:g_pDebug
0x180003c6c  call    cs:__imp_PuDbgPrintError
0x180003c72  cmp     ebx, 80040111h
0x180003c78  jz      short loc_180003C87
0x180003c7a  cmp     ebx, 80040154h
0x180003c80  mov     edx, 0C0000027h
0x180003c85  jnz     short loc_180003C8C
0x180003c87  mov     edx, 0C0000026h
0x180003c8c  xor     r8d, r8d
0x180003c8f  xor     r9d, r9d
0x180003c92  mov     dword ptr [rsp+80h+ppv], ebx
0x180003c96  mov     rcx, cs:?sm_pEventLog@FTP_LOG_NT_EVENT@@0PEAVEVENT_LOG@@EA; EVENT_LOG * FTP_LOG_NT_EVENT::sm_pEventLog
0x180003c9d  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180003ca3  jmp     loc_180003F50
0x180003ca8  mov     ecx, 48h ; 'H'; Size
0x180003cad  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003cb2  mov     rdi, rax
0x180003cb5  mov     [rbp+var_48], rax
0x180003cb9  test    rax, rax
0x180003cbc  jz      short loc_180003CDB
0x180003cbe  lea     rax, ??_7FTP_CONFIG_PATH_MAPPER@@6B@; const FTP_CONFIG_PATH_MAPPER::`vftable'
0x180003cc5  mov     [rdi], rax
0x180003cc8  mov     dword ptr [rdi+8], 1
0x180003ccf  lea     rcx, [rdi+10h]
0x180003cd3  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180003cd9  jmp     short loc_180003CDD
0x180003cdb  xor     edi, edi
0x180003cdd  test    rdi, rdi
0x180003ce0  jnz     short loc_180003CEC
0x180003ce2  mov     ebx, 80070008h
0x180003ce7  jmp     loc_180003F50
0x180003cec  mov     qword ptr [rbp+Dst], 0
0x180003cf4  lea     rax, [rbp+Dst]
0x180003cf8  mov     [rbp+lpDst], rax
0x180003cfc  mov     [rbp+var_18], 20h ; ' '
0x180003d03  mov     [rbp+var_14], 100h
0x180003d09  mov     r8d, 10h; nSize
0x180003d0f  lea     rdx, [rbp+Dst]; lpDst
0x180003d13  lea     rcx, Src; "%windir%\\system32\\inetsrv\\ftp_config"...
0x180003d1a  call    cs:__imp_ExpandEnvironmentStringsW
0x180003d20  mov     ecx, [rbp+var_18]
0x180003d23  shr     ecx, 1
0x180003d25  cmp     eax, ecx
0x180003d27  jbe     short loc_180003D69
0x180003d29  lea     edx, [rax+rax]
0x180003d2c  lea     rcx, [rbp+Dst]
0x180003d30  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180003d36  test    al, al
0x180003d38  jnz     short loc_180003D51
0x180003d3a  call    cs:__imp_GetLastError
0x180003d40  mov     ebx, eax
0x180003d42  test    eax, eax
0x180003d44  jle     short loc_180003D7D
0x180003d46  movzx   ebx, ax
0x180003d49  or      ebx, 80070000h
0x180003d4f  jmp     short loc_180003D7D
0x180003d51  mov     r8d, [rbp+var_18]
0x180003d55  shr     r8d, 1; nSize
0x180003d58  mov     rdx, [rbp+lpDst]; lpDst
0x180003d5c  lea     rcx, Src; "%windir%\\system32\\inetsrv\\ftp_config"...
0x180003d63  call    cs:__imp_ExpandEnvironmentStringsW
0x180003d69  test    eax, eax
0x180003d6b  jz      short loc_180003D3A
0x180003d6d  lea     rcx, [rdi+10h]
0x180003d71  mov     rdx, [rbp+lpDst]
0x180003d75  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180003d7b  mov     ebx, eax
0x180003d7d  lea     rcx, [rbp+Dst]
0x180003d81  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180003d87  test    ebx, ebx
0x180003d89  jns     short loc_180003DE9
0x180003d8b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003d92  jz      short loc_180003DC5
0x180003d94  lea     rax, aConfigReaderPa; "Config reader path mapper initializatio"...
0x180003d9b  mov     r8d, 7C3h
0x180003da1  mov     [rsp+80h+var_58], rax
0x180003da6  lea     r9, aFtpServerpInit_0; "FTP_SERVERP::InitializeAppHostConfigura"...
0x180003dad  mov     dword ptr [rsp+80h+ppv], ebx
0x180003db1  lea     rdx, aInetsrvIisIisr_23; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x180003db8  mov     rcx, cs:g_pDebug
0x180003dbf  call    cs:__imp_PuDbgPrintError
0x180003dc5  mov     rax, [rdi]
0x180003dc8  mov     rcx, rdi
0x180003dcb  mov     rax, [rax+10h]
0x180003dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dd4  mov     rcx, [rbp+var_50]
0x180003dd8  mov     rax, [rcx]
0x180003ddb  mov     rax, [rax+10h]
0x180003ddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003de4  jmp     loc_180003F50
0x180003de9  mov     rdx, rdi; struct IAppHostPathMapper *
0x180003dec  mov     rcx, [rbp+var_50]; struct IAppHostAdminManager *
0x180003df0  call    ?Config_SetPathMapper@@YAJPEAUIAppHostAdminManager@@PEAUIAppHostPathMapper@@@Z; Config_SetPathMapper(IAppHostAdminManager *,IAppHostPathMapper *)
0x180003df5  mov     ebx, eax
0x180003df7  test    eax, eax
0x180003df9  jns     short loc_180003E13
0x180003dfb  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003e02  jz      short loc_180003DC5
0x180003e04  lea     rax, aCouldNotConfig; "Could not configure app host config rea"...
0x180003e0b  mov     r8d, 7D6h
0x180003e11  jmp     short loc_180003DA1
0x180003e13  mov     rax, [rdi]
0x180003e16  mov     rcx, rdi
0x180003e19  mov     rax, [rax+10h]
0x180003e1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e22  test    r14d, r14d
0x180003e25  jz      short loc_180003E2E
0x180003e27  mov     dword ptr [rsi+8], 11h
0x180003e2e  mov     ecx, 20h ; ' '; Size
0x180003e33  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003e38  mov     rdi, rax
0x180003e3b  mov     [rbp+var_48], rax
0x180003e3f  test    rax, rax
0x180003e42  jz      loc_180003F0D
0x180003e48  lea     rax, ??_7FTP_CONFIG_CHANGE_NOTIFICATION@@6B@; const FTP_CONFIG_CHANGE_NOTIFICATION::`vftable'
0x180003e4f  mov     [rdi], rax
0x180003e52  mov     eax, 1
0x180003e57  mov     [rdi+8], rax
0x180003e5b  mov     dword ptr [rdi+10h], 0
0x180003e62  mov     dword ptr [rdi+14h], 0
0x180003e69  mov     dword ptr [rdi+18h], 0
0x180003e70  test    rdi, rdi
0x180003e73  jz      loc_180003F0D
0x180003e79  test    r14d, r14d
0x180003e7c  jz      short loc_180003E85
0x180003e7e  mov     dword ptr [rsi+8], 12h
0x180003e85  mov     [rdi+10h], eax
0x180003e88  lea     rcx, [rdi+14h]
0x180003e8c  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180003e92  mov     rdx, rdi; struct IAppHostChangeHandler *
0x180003e95  mov     rcx, [rbp+var_50]; struct IAppHostAdminManager *
0x180003e99  call    ?Config_SetChangeHandler@@YAJPEAUIAppHostAdminManager@@PEAUIAppHostChangeHandler@@@Z; Config_SetChangeHandler(IAppHostAdminManager *,IAppHostChangeHandler *)
0x180003e9e  mov     ebx, eax
0x180003ea0  test    eax, eax
0x180003ea2  jns     short loc_180003F00
0x180003ea4  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003eab  jz      short loc_180003EDE
0x180003ead  lea     rax, aFailedToRegist; "Failed to register change listener"
0x180003eb4  mov     [rsp+80h+var_58], rax
0x180003eb9  mov     dword ptr [rsp+80h+ppv], ebx
0x180003ebd  lea     r9, aFtpServerpInit_0; "FTP_SERVERP::InitializeAppHostConfigura"...
0x180003ec4  mov     r8d, 80Ch
0x180003eca  lea     rdx, aInetsrvIisIisr_23; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x180003ed1  mov     rcx, cs:g_pDebug
0x180003ed8  call    cs:__imp_PuDbgPrintError
0x180003ede  cmp     dword ptr [rdi+10h], 0
0x180003ee2  jz      short loc_180003EF5
0x180003ee4  mov     dword ptr [rdi+10h], 0
0x180003eeb  lea     rcx, [rdi+14h]
0x180003eef  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180003ef5  mov     rax, [rdi]
0x180003ef8  mov     rcx, rdi
0x180003efb  jmp     loc_180003DDB
0x180003f00  mov     rax, [rbp+var_50]
0x180003f04  mov     [r15], rax
0x180003f07  mov     [r12], rdi
0x180003f0b  jmp     short loc_180003F50
0x180003f0d  mov     ebx, 80070008h
0x180003f12  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180003f19  jz      short loc_180003F50
0x180003f1b  lea     rax, aFailedToAlloca_4; "Failed to allocate memory for change li"...
0x180003f22  mov     [rsp+80h+var_58], rax
0x180003f27  mov     dword ptr [rsp+80h+ppv], 80070008h
0x180003f2f  lea     r9, aFtpServerpInit_0; "FTP_SERVERP::InitializeAppHostConfigura"...
0x180003f36  mov     r8d, 7F5h
0x180003f3c  lea     rdx, aInetsrvIisIisr_23; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x180003f43  mov     rcx, cs:g_pDebug
0x180003f4a  call    cs:__imp_PuDbgPrintError
0x180003f50  mov     eax, ebx
0x180003f52  mov     rcx, [rbp+var_10]
0x180003f56  xor     rcx, rsp; StackCookie
0x180003f59  call    __security_check_cookie
0x180003f5e  add     rsp, 80h
0x180003f65  pop     r15
0x180003f67  pop     r14
0x180003f69  pop     r12
0x180003f6b  pop     rdi
0x180003f6c  pop     rsi
0x180003f6d  pop     rbx
0x180003f6e  pop     rbp
0x180003f6f  retn
```
