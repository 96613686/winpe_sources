# FTP_LOGGING::Log(_LOG_ENTRY_TYPE,char const *,sockaddr const *,sockaddr const *,char const *,char const *,char const *,unsigned __int64,unsigned __int64,char const *,char const *,char const *,char const *,char const *,ulong,long,ulong,ushort const *)

- ea: `0x18002747c`
- end: `0x180027703`
- name: `?Log@FTP_LOGGING@@QEAAJW4_LOG_ENTRY_TYPE@@PEBDPEBUsockaddr@@2111_K311111KJKPEBG@Z`
- size: `647`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000bf2c`
- `0x180034794`
- `0x180034cb4`

## callees

- `0x18002747c`
- `0x180027ccc`
- `0x1800282e8`
- `0x180047050`

## import_xrefs

- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18002754b`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18002754b`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180027599`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180027599`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800276c1`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800276c1`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800276d0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800276d0`
- `iisutil!PuDbgPrintError` at `0x1800275f9`
- `iisutil!PuDbgPrintError` at `0x1800275f9`

## string_xrefs

- `0x1800275ce`: `Failed to open log file %S`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FTP_LOGGING::Log(
        __int64 a1,
        int a2,
        const char *a3,
        const struct sockaddr *a4,
        struct sockaddr *a5,
        char *a6,
        const char *a7,
        const char *a8,
        unsigned __int64 a9,
        unsigned __int64 a10,
        const char *a11,
        const char *a12,
        const char *a13,
        const char *a14,
        char *a15,
        unsigned int a16,
        int a17,
        unsigned int a18,
        const unsigned __int16 *a19)
{
  int v23; // edi
  int v24; // ecx
  unsigned __int8 v25; // al
  _BYTE v27[56]; // [rsp+C8h] [rbp-A0h] BYREF
  char v28[32]; // [rsp+100h] [rbp-68h] BYREF

  v23 = 0;
  STRA::STRA((STRA *)v27, v28, 0x20u);
  if ( !*(_DWORD *)(a1 + 80) )
    goto LABEL_16;
  v24 = *(_DWORD *)(a1 + 88);
  if ( (v24 & 3) == 0 )
  {
    if ( (v24 & 1) != 0 )
    {
      v25 = *a15 - 50;
      goto LABEL_7;
    }
    if ( (v24 & 2) != 0 )
    {
      v25 = *a15 - 52;
LABEL_7:
      if ( v25 > 1u )
        goto LABEL_16;
    }
  }
  if ( (v24 & 4) != 0 || ((a2 - 3) & 0xFFFFFFFD) != 0 )
  {
    CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)(a1 + 92));
    if ( *(_QWORD *)(a1 + 16) || (v23 = FTP_LOGGING::OpenLogFile((FTP_LOGGING *)a1), v23 >= 0) )
    {
      v23 = FTP_LOGGING::LogW3CEx(
              (FTP_LOGGING *)a1,
              a3,
              a4,
              a5,
              a6,
              a7,
              a8,
              a9,
              a10,
              a11,
              a12,
              a13,
              a14,
              a15,
              a16,
              a17,
              a18,
              a19);
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_logging\\ftp_logging.cxx",
        493,
        "FTP_LOGGING::Log",
        v23,
        "Failed to open log file %S",
        *(const wchar_t **)(*(_QWORD *)(a1 + 8) + 88LL));
    }
    CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)(a1 + 92));
  }
LABEL_16:
  STRA::~STRA((STRA *)v27);
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x18002747c  mov     r11, rsp
0x18002747f  mov     [r11+10h], rbx
0x180027483  push    rbp
0x180027484  push    rsi
0x180027485  push    rdi
0x180027486  push    r12
0x180027488  push    r13
0x18002748a  push    r14
0x18002748c  push    r15
0x18002748e  sub     rsp, 130h
0x180027495  mov     rax, cs:__security_cookie
0x18002749c  xor     rax, rsp
0x18002749f  mov     [rsp+168h+var_48], rax
0x1800274a7  mov     r15, r9
0x1800274aa  mov     rbp, r8
0x1800274ad  mov     esi, edx
0x1800274af  mov     rbx, rcx
0x1800274b2  mov     r12, [rsp+168h+arg_20]
0x1800274ba  mov     r13, [rsp+168h+arg_28]
0x1800274c2  mov     rax, [rsp+168h+arg_30]
0x1800274ca  mov     [rsp+168h+var_A8], rax
0x1800274d2  mov     rax, [rsp+168h+arg_38]
0x1800274da  mov     [rsp+168h+var_B0], rax
0x1800274e2  mov     rax, [rsp+168h+arg_50]
0x1800274ea  mov     [rsp+168h+var_B8], rax
0x1800274f2  mov     rax, [rsp+168h+arg_58]
0x1800274fa  mov     [rsp+168h+var_C0], rax
0x180027502  mov     rax, [rsp+168h+arg_60]
0x18002750a  mov     [rsp+168h+var_C8], rax
0x180027512  mov     rax, [rsp+168h+arg_68]
0x18002751a  mov     [rsp+168h+var_D0], rax
0x180027522  mov     r14, [rsp+168h+arg_70]
0x18002752a  mov     rax, [rsp+168h+arg_90]
0x180027532  mov     [rsp+168h+var_D8], rax
0x18002753a  xor     edi, edi
0x18002753c  lea     r8d, [rdi+20h]
0x180027540  lea     rdx, [r11-68h]
0x180027544  lea     rcx, [r11-0A0h]
0x18002754b  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180027551  nop
0x180027552  cmp     [rbx+50h], edi
0x180027555  jz      loc_1800276C8
0x18002755b  mov     ecx, [rbx+58h]
0x18002755e  test    cl, 3
0x180027561  jnz     short loc_180027582
0x180027563  mov     dl, 1
0x180027565  test    dl, cl
0x180027567  jz      short loc_180027570
0x180027569  mov     al, [r14]
0x18002756c  sub     al, 32h ; '2'
0x18002756e  jmp     short loc_18002757A
0x180027570  test    cl, 2
0x180027573  jz      short loc_180027582
0x180027575  mov     al, [r14]
0x180027578  sub     al, 34h ; '4'
0x18002757a  cmp     al, dl
0x18002757c  ja      loc_1800276C8
0x180027582  test    cl, 4
0x180027585  jnz     short loc_180027595
0x180027587  lea     eax, [rsi-3]
0x18002758a  test    eax, 0FFFFFFFDh
0x18002758f  jz      loc_1800276C8
0x180027595  lea     rcx, [rbx+5Ch]
0x180027599  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18002759f  cmp     qword ptr [rbx+10h], 0
0x1800275a4  jnz     short loc_180027604
0x1800275a6  mov     rcx, rbx; this
0x1800275a9  call    ?OpenLogFile@FTP_LOGGING@@AEAAJXZ; FTP_LOGGING::OpenLogFile(void)
0x1800275ae  mov     edi, eax
0x1800275b0  test    eax, eax
0x1800275b2  jns     short loc_180027604
0x1800275b4  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800275bb  jz      loc_1800276BD
0x1800275c1  mov     rcx, [rbx+8]
0x1800275c5  mov     rdx, [rcx+58h]
0x1800275c9  mov     [rsp+168h+var_138], rdx
0x1800275ce  lea     rax, aFailedToOpenLo; "Failed to open log file %S"
0x1800275d5  mov     [rsp+168h+var_140], rax
0x1800275da  mov     dword ptr [rsp+168h+var_148], edi
0x1800275de  lea     r9, aFtpLoggingLog; "FTP_LOGGING::Log"
0x1800275e5  mov     r8d, 1EDh
0x1800275eb  lea     rdx, aInetsrvIisIisr_27; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x1800275f2  mov     rcx, cs:g_pDebug
0x1800275f9  call    cs:__imp_PuDbgPrintError
0x1800275ff  jmp     loc_1800276BD
0x180027604  mov     rax, [rsp+168h+var_D8]
0x18002760c  mov     [rsp+168h+var_E0], rax; unsigned __int16 *
0x180027614  mov     eax, [rsp+168h+arg_88]
0x18002761b  mov     [rsp+168h+var_E8], eax; unsigned int
0x180027622  mov     eax, [rsp+168h+arg_80]
0x180027629  mov     [rsp+168h+var_F0], eax; int
0x18002762d  mov     eax, [rsp+168h+arg_78]
0x180027634  mov     [rsp+168h+var_F8], eax; unsigned int
0x180027638  mov     [rsp+168h+var_100], r14; char *
0x18002763d  mov     rax, [rsp+168h+var_D0]
0x180027645  mov     [rsp+168h+var_108], rax; char *
0x18002764a  mov     rax, [rsp+168h+var_C8]
0x180027652  mov     [rsp+168h+var_110], rax; char *
0x180027657  mov     rax, [rsp+168h+var_C0]
0x18002765f  mov     [rsp+168h+var_118], rax; char *
0x180027664  mov     rax, [rsp+168h+var_B8]
0x18002766c  mov     [rsp+168h+var_120], rax; char *
0x180027671  mov     rax, [rsp+168h+arg_48]
0x180027679  mov     [rsp+168h+var_128], rax; unsigned __int64
0x18002767e  mov     rax, [rsp+168h+arg_40]
0x180027686  mov     [rsp+168h+var_130], rax; unsigned __int64
0x18002768b  mov     rax, [rsp+168h+var_B0]
0x180027693  mov     [rsp+168h+var_138], rax; char *
0x180027698  mov     rax, [rsp+168h+var_A8]
0x1800276a0  mov     [rsp+168h+var_140], rax; char *
0x1800276a5  mov     [rsp+168h+var_148], r13; char *
0x1800276aa  mov     r9, r12; struct sockaddr *
0x1800276ad  mov     r8, r15; struct sockaddr *
0x1800276b0  mov     rdx, rbp; char *
0x1800276b3  mov     rcx, rbx; this
0x1800276b6  call    ?LogW3CEx@FTP_LOGGING@@AEAAJPEBDPEBUsockaddr@@1000_K200000KJKPEBG@Z; FTP_LOGGING::LogW3CEx(char const *,sockaddr const *,sockaddr const *,char const *,char const *,char const *,unsigned __int64,unsigned __int64,char const *,char const *,char const *,char const *,char const *,ulong,long,ulong,ushort const *)
0x1800276bb  mov     edi, eax
0x1800276bd  lea     rcx, [rbx+5Ch]
0x1800276c1  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x1800276c7  nop
0x1800276c8  lea     rcx, [rsp+168h+var_A0]
0x1800276d0  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800276d6  mov     eax, edi
0x1800276d8  mov     rcx, [rsp+168h+var_48]
0x1800276e0  xor     rcx, rsp; StackCookie
0x1800276e3  call    __security_check_cookie
0x1800276e8  mov     rbx, [rsp+168h+arg_8]
0x1800276f0  add     rsp, 130h
0x1800276f7  pop     r15
0x1800276f9  pop     r14
0x1800276fb  pop     r13
0x1800276fd  pop     r12
0x1800276ff  pop     rdi
0x180027700  pop     rsi
0x180027701  pop     rbp
0x180027702  retn
```
