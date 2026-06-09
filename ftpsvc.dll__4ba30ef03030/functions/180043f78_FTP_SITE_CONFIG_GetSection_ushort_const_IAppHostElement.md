# FTP_SITE_CONFIG::GetSection(ushort const *,IAppHostElement * *)

- ea: `0x180043f78`
- end: `0x180044116`
- name: `?GetSection@FTP_SITE_CONFIG@@QEAAJPEBGPEAPEAUIAppHostElement@@@Z`
- size: `414`
- prototype: `__int64 __fastcall(FTP_SITE_CONFIG *this, const unsigned __int16 *, struct IAppHostElement **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x180045dac`

## callees

- `0x18001908c`
- `0x18002b488`
- `0x180043f78`
- `0x18004700f`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180043fe3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180043fe3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180043fc7`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180043fc7`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180044001`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180044001`
- `iisutil!PuDbgPrintError` at `0x1800440b0`
- `iisutil!PuDbgPrintError` at `0x1800440b0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800440eb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800440eb`

## string_xrefs

- `0x1800440a2`: `inetsrv\iis\iisrearc\ftp\server\ftp_config\ftp_site_config.cxx`
- `0x180044095`: `FTP_SITE_CONFIG::GetSection`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FTP_SITE_CONFIG::GetSection(
        FTP_SITE_CONFIG *this,
        const unsigned __int16 *a2,
        struct IAppHostElement **a3)
{
  int Section; // ebx
  const unsigned __int16 *v6; // rdx
  struct IAppHostAdminManager *v7; // rsi
  struct IErrorInfo *v8; // rdi
  FTP_LOG_NT_EVENT_TABLE *v9; // rax
  struct IErrorInfo *v11; // [rsp+40h] [rbp-278h] BYREF
  _BYTE v12[32]; // [rsp+48h] [rbp-270h] BYREF
  unsigned __int16 *v13; // [rsp+68h] [rbp-250h]
  unsigned __int16 v14[264]; // [rsp+80h] [rbp-238h] BYREF

  memset_0(v14, 0, 0x208u);
  STRU::STRU((STRU *)v12, v14, 0x104u);
  v11 = 0;
  Section = STRU::Copy((STRU *)v12, L"MACHINE/WEBROOT/APPHOST/");
  if ( Section >= 0 )
  {
    v6 = (const unsigned __int16 *)*((_QWORD *)this + 1);
    if ( !v6 || (Section = STRU::Append((STRU *)v12, v6), Section >= 0) )
    {
      v7 = (struct IAppHostAdminManager *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 24LL))(g_pFtpServer);
      Section = Config_GetSection(v7, L"system.applicationHost/sites", v13, a3, &v11);
      v8 = v11;
      if ( Section < 0 )
      {
        v9 = (FTP_LOG_NT_EVENT_TABLE *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 40LL))(g_pFtpServer);
        FTP_LOG_NT_EVENT_TABLE::LogEventConfigError(v9, v8, Section);
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_config\\ftp_site_config.cxx",
            3075,
            "FTP_SITE_CONFIG::GetSection",
            Section,
            " Failed to get section %S\n",
            L"system.applicationHost/sites");
      }
      if ( v8 )
        ((void (__fastcall *)(struct IErrorInfo *))v8->lpVtbl->Release)(v8);
      if ( v7 )
        (*(void (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 208LL))(g_pFtpServer);
    }
  }
  STRU::~STRU(v12);
  return (unsigned int)Section;
}

```

## disassembly

```asm
0x180043f78  mov     [rsp+arg_8], rbx
0x180043f7d  push    rbp
0x180043f7e  push    rsi
0x180043f7f  push    rdi
0x180043f80  sub     rsp, 2A0h
0x180043f87  mov     rax, cs:__security_cookie
0x180043f8e  xor     rax, rsp
0x180043f91  mov     [rsp+2B8h+var_28], rax
0x180043f99  mov     rbp, r8
0x180043f9c  mov     rdi, rcx
0x180043f9f  xor     edx, edx; Val
0x180043fa1  mov     r8d, 208h; Size
0x180043fa7  lea     rcx, [rsp+2B8h+var_238]; void *
0x180043faf  call    memset_0
0x180043fb4  mov     r8d, 104h
0x180043fba  lea     rdx, [rsp+2B8h+var_238]
0x180043fc2  lea     rcx, [rsp+2B8h+var_270]
0x180043fc7  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180043fcd  nop
0x180043fce  mov     [rsp+2B8h+var_278], 0
0x180043fd7  lea     rdx, aMachineWebroot_0; "MACHINE/WEBROOT/APPHOST/"
0x180043fde  lea     rcx, [rsp+2B8h+var_270]
0x180043fe3  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180043fe9  mov     ebx, eax
0x180043feb  test    eax, eax
0x180043fed  js      loc_1800440E6
0x180043ff3  mov     rdx, [rdi+8]
0x180043ff7  test    rdx, rdx
0x180043ffa  jz      short loc_180044011
0x180043ffc  lea     rcx, [rsp+2B8h+var_270]
0x180044001  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180044007  mov     ebx, eax
0x180044009  test    eax, eax
0x18004400b  js      loc_1800440E6
0x180044011  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180044018  mov     rax, [rcx]
0x18004401b  mov     rax, [rax+18h]
0x18004401f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044024  mov     rsi, rax
0x180044027  lea     rax, [rsp+2B8h+var_278]
0x18004402c  mov     [rsp+2B8h+var_298], rax; struct IErrorInfo **
0x180044031  mov     r9, rbp; struct IAppHostElement **
0x180044034  mov     r8, [rsp+2B8h+var_250]; unsigned __int16 *
0x180044039  lea     rbp, aSystemApplicat; "system.applicationHost/sites"
0x180044040  mov     rdx, rbp; unsigned __int16 *
0x180044043  mov     rcx, rsi; struct IAppHostAdminManager *
0x180044046  call    ?Config_GetSection@@YAJPEAUIAppHostAdminManager@@PEBG1PEAPEAUIAppHostElement@@PEAPEAUIErrorInfo@@@Z; Config_GetSection(IAppHostAdminManager *,ushort const *,ushort const *,IAppHostElement * *,IErrorInfo * *)
0x18004404b  mov     ebx, eax
0x18004404d  mov     rdi, [rsp+2B8h+var_278]
0x180044052  test    eax, eax
0x180044054  jns     short loc_1800440B6
0x180044056  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18004405d  mov     rax, [rcx]
0x180044060  mov     rax, [rax+28h]
0x180044064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044069  mov     r8d, ebx; int
0x18004406c  mov     rdx, rdi; struct IErrorInfo *
0x18004406f  mov     rcx, rax; this
0x180044072  call    ?LogEventConfigError@FTP_LOG_NT_EVENT_TABLE@@QEAAXPEAUIErrorInfo@@J@Z; FTP_LOG_NT_EVENT_TABLE::LogEventConfigError(IErrorInfo *,long)
0x180044077  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18004407e  jz      short loc_1800440B6
0x180044080  mov     [rsp+2B8h+var_288], rbp
0x180044085  lea     rax, aFailedToGetSec; " Failed to get section %S\n"
0x18004408c  mov     [rsp+2B8h+var_290], rax
0x180044091  mov     dword ptr [rsp+2B8h+var_298], ebx
0x180044095  lea     r9, aFtpSiteConfigG; "FTP_SITE_CONFIG::GetSection"
0x18004409c  mov     r8d, 0C03h
0x1800440a2  lea     rdx, aInetsrvIisIisr_28; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x1800440a9  mov     rcx, cs:g_pDebug
0x1800440b0  call    cs:__imp_PuDbgPrintError
0x1800440b6  test    rdi, rdi
0x1800440b9  jz      short loc_1800440CA
0x1800440bb  mov     rax, [rdi]
0x1800440be  mov     rcx, rdi
0x1800440c1  mov     rax, [rax+10h]
0x1800440c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800440ca  test    rsi, rsi
0x1800440cd  jz      short loc_1800440E6
0x1800440cf  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x1800440d6  mov     rax, [rcx]
0x1800440d9  mov     rax, [rax+0D0h]
0x1800440e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800440e5  nop
0x1800440e6  lea     rcx, [rsp+2B8h+var_270]
0x1800440eb  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800440f1  mov     eax, ebx
0x1800440f3  mov     rcx, [rsp+2B8h+var_28]
0x1800440fb  xor     rcx, rsp; StackCookie
0x1800440fe  call    __security_check_cookie
0x180044103  mov     rbx, [rsp+2B8h+arg_8]
0x18004410b  add     rsp, 2A0h
0x180044112  pop     rdi
0x180044113  pop     rsi
0x180044114  pop     rbp
0x180044115  retn
```
