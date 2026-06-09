# FREB_SITE_META_STORED_CONTEXT::DeleteFrebLogFile(ushort const *,ushort const *)

- ea: `0x180006944`
- end: `0x180006ae5`
- name: `?DeleteFrebLogFile@FREB_SITE_META_STORED_CONTEXT@@CAJPEBG0@Z`
- size: `417`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006f98`

## callees

- `0x180006944`
- `0x18000a4dc`
- `0x18000ac52`
- `0x18000ac90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a32`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180006a24`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180006a24`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006ab8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006ab8`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180006996`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180006996`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800069a4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800069a4`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800069fb`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800069fb`
- `iisutil!PuDbgPrintError` at `0x1800069e8`
- `iisutil!PuDbgPrintError` at `0x180006a7b`
- `iisutil!PuDbgPrintError` at `0x1800069e8`
- `iisutil!PuDbgPrintError` at `0x180006a7b`

## string_xrefs

- `0x1800069dd`: `servercommon\inetsrv\iis\iisrearc\iis70\freb\freb_site_meta_context.cxx`
- `0x180006a74`: `servercommon\inetsrv\iis\iisrearc\iis70\freb\freb_site_meta_context.cxx`
- `0x1800069d1`: `FREB_SITE_META_STORED_CONTEXT::DeleteFrebLogFile`
- `0x180006a63`: `FREB_SITE_META_STORED_CONTEXT::DeleteFrebLogFile`
- `0x180006a57`: `Attempt to delete obsolete FREB log file failed\n`

## pseudocode

```c
__int64 __fastcall FREB_SITE_META_STORED_CONTEXT::DeleteFrebLogFile(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2)
{
  int v4; // ebx
  const char *v5; // rax
  __int64 v6; // r8
  signed int LastError; // eax
  unsigned __int16 *v9[3]; // [rsp+30h] [rbp-278h] BYREF
  _BYTE v10[32]; // [rsp+48h] [rbp-260h] BYREF
  LPCWSTR lpFileName; // [rsp+68h] [rbp-240h]
  unsigned __int16 v12[264]; // [rsp+80h] [rbp-228h] BYREF

  memset_0(v12, 0, 0x208u);
  STRU::STRU((STRU *)v10, v12, 0x104u);
  v4 = STRU::Copy((STRU *)v10, a1);
  if ( v4 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
    {
LABEL_14:
      v9[0] = 0;
      v9[1] = 0;
      v9[2] = (unsigned __int16 *)a1;
      FREB_LOG_NT_EVENT_TABLE::LogEvent(0x800008F1, 3u, (const unsigned __int16 **const)v9, v4);
      goto LABEL_15;
    }
    v5 = "Failed to build the full file name for deletion\n";
    v6 = 798;
LABEL_4:
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\freb\\freb_site_meta_context.cxx",
      v6,
      "FREB_SITE_META_STORED_CONTEXT::DeleteFrebLogFile",
      v4,
      v5);
    goto LABEL_14;
  }
  v4 = STRU::Append((STRU *)v10, a2);
  if ( v4 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_14;
    v5 = "building the full file name for deletion failed\n";
    v6 = 815;
    goto LABEL_4;
  }
  if ( !DeleteFileW(lpFileName) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\freb\\freb_site_meta_context.cxx",
        828,
        "FREB_SITE_META_STORED_CONTEXT::DeleteFrebLogFile",
        v4,
        "Attempt to delete obsolete FREB log file failed\n");
    if ( v4 < 0 )
      goto LABEL_14;
  }
LABEL_15:
  STRU::~STRU((STRU *)v10);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180006944  mov     [rsp+arg_10], rbx
0x180006949  mov     [rsp+arg_18], rsi
0x18000694e  push    rdi
0x18000694f  sub     rsp, 2A0h
0x180006956  mov     rax, cs:__security_cookie
0x18000695d  xor     rax, rsp
0x180006960  mov     [rsp+2A8h+var_18], rax
0x180006968  mov     rdi, rdx
0x18000696b  mov     rsi, rcx
0x18000696e  xor     edx, edx; Val
0x180006970  lea     rcx, [rsp+2A8h+var_228]; void *
0x180006978  mov     r8d, 208h; Size
0x18000697e  call    memset_0
0x180006983  mov     r8d, 104h
0x180006989  lea     rdx, [rsp+2A8h+var_228]
0x180006991  lea     rcx, [rsp+2A8h+var_260]
0x180006996  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000699c  mov     rdx, rsi
0x18000699f  lea     rcx, [rsp+2A8h+var_260]
0x1800069a4  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800069aa  mov     ebx, eax
0x1800069ac  test    eax, eax
0x1800069ae  jns     short loc_1800069F3
0x1800069b0  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800069b7  jz      loc_180006A85
0x1800069bd  lea     rax, aFailedToBuildT_0; "Failed to build the full file name for "...
0x1800069c4  mov     r8d, 31Eh
0x1800069ca  mov     rcx, cs:g_pDebug
0x1800069d1  lea     r9, aFrebSiteMetaSt; "FREB_SITE_META_STORED_CONTEXT::DeleteFr"...
0x1800069d8  mov     [rsp+2A8h+var_280], rax
0x1800069dd  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800069e4  mov     [rsp+2A8h+var_288], ebx
0x1800069e8  call    cs:__imp_PuDbgPrintError
0x1800069ee  jmp     loc_180006A85
0x1800069f3  mov     rdx, rdi
0x1800069f6  lea     rcx, [rsp+2A8h+var_260]
0x1800069fb  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180006a01  mov     ebx, eax
0x180006a03  test    eax, eax
0x180006a05  jns     short loc_180006A1F
0x180006a07  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180006a0e  jz      short loc_180006A85
0x180006a10  lea     rax, aBuildingTheFul; "building the full file name for deletio"...
0x180006a17  mov     r8d, 32Fh
0x180006a1d  jmp     short loc_1800069CA
0x180006a1f  mov     rcx, [rsp+2A8h+lpFileName]; lpFileName
0x180006a24  call    cs:__imp_DeleteFileW
0x180006a2a  test    eax, eax
0x180006a2c  jnz     loc_180006AB3
0x180006a32  call    cs:__imp_GetLastError
0x180006a38  mov     ebx, eax
0x180006a3a  test    eax, eax
0x180006a3c  jle     short loc_180006A47
0x180006a3e  movzx   ebx, ax
0x180006a41  or      ebx, 80070000h
0x180006a47  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180006a4e  jz      short loc_180006A81
0x180006a50  mov     rcx, cs:g_pDebug
0x180006a57  lea     rax, aAttemptToDelet; "Attempt to delete obsolete FREB log fil"...
0x180006a5e  mov     [rsp+2A8h+var_280], rax
0x180006a63  lea     r9, aFrebSiteMetaSt; "FREB_SITE_META_STORED_CONTEXT::DeleteFr"...
0x180006a6a  mov     r8d, 33Ch
0x180006a70  mov     [rsp+2A8h+var_288], ebx
0x180006a74  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180006a7b  call    cs:__imp_PuDbgPrintError
0x180006a81  test    ebx, ebx
0x180006a83  jns     short loc_180006AB3
0x180006a85  mov     edx, 3; unsigned __int16
0x180006a8a  mov     [rsp+2A8h+var_278], 0
0x180006a93  mov     r9d, ebx; unsigned int
0x180006a96  mov     [rsp+2A8h+var_270], 0
0x180006a9f  lea     r8, [rsp+2A8h+var_278]; unsigned __int16 **
0x180006aa4  mov     [rsp+2A8h+var_268], rsi
0x180006aa9  mov     ecx, 800008F1h; unsigned int
0x180006aae  call    ?LogEvent@FREB_LOG_NT_EVENT_TABLE@@SAXKGQEAPEBGK@Z; FREB_LOG_NT_EVENT_TABLE::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180006ab3  lea     rcx, [rsp+2A8h+var_260]
0x180006ab8  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180006abe  mov     eax, ebx
0x180006ac0  mov     rcx, [rsp+2A8h+var_18]
0x180006ac8  xor     rcx, rsp; StackCookie
0x180006acb  call    __security_check_cookie
0x180006ad0  lea     r11, [rsp+2A8h+var_8]
0x180006ad8  mov     rbx, [r11+20h]
0x180006adc  mov     rsi, [r11+28h]
0x180006ae0  mov     rsp, r11
0x180006ae3  pop     rdi
0x180006ae4  retn
```
