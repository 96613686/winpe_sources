# FTP_LOGGING::~FTP_LOGGING(void)

- ea: `0x180026e48`
- end: `0x180026f24`
- name: `??1FTP_LOGGING@@AEAA@XZ`
- size: `220`
- prototype: `void __fastcall(FTP_LOGGING *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180026fdc`

## callees

- `0x180001250`
- `0x180026e48`
- `0x180028628`
- `0x1800286a4`

## import_xrefs

- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180026e61`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180026e61`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180026ec9`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180026ec9`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x180026f04`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x180026f04`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180026f1d`
- `iisutil!PuDbgPrintError` at `0x180026ec0`
- `iisutil!PuDbgPrintError` at `0x180026ec0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180026edc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180026ee5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180026edc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180026ee5`

## pseudocode

```c
void __fastcall FTP_LOGGING::~FTP_LOGGING(FTP_LOGGING *this)
{
  CReaderWriterLock3 *v2; // rsi
  FTP_LOG_FILE *v3; // rcx
  int v4; // edi
  __int64 v5; // rdi

  v2 = (FTP_LOGGING *)((char *)this + 92);
  CReaderWriterLock3::WriteLock((FTP_LOGGING *)((char *)this + 92));
  v3 = (FTP_LOG_FILE *)*((_QWORD *)this + 2);
  if ( v3 )
  {
    v4 = FTP_LOG_FILE::Flush(v3);
    FTP_LOG_FILE::DereferenceLogFile(*((FTP_LOG_FILE **)this + 2));
    *((_QWORD *)this + 2) = 0;
    if ( v4 < 0 && (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_logging\\ftp_logging.cxx",
        69,
        "FTP_LOGGING::~FTP_LOGGING",
        v4,
        "Failed to close Ftp Logging.\n");
  }
  CReaderWriterLock3::WriteUnlock(v2);
  v5 = *((_QWORD *)this + 1);
  if ( v5 )
  {
    STRU::~STRU((void *)(v5 + 56));
    STRU::~STRU((void *)v5);
    operator delete((void *)v5);
    *((_QWORD *)this + 1) = 0;
  }
  *(_DWORD *)this = 1819505766;
  CReaderWriterLock3::~CReaderWriterLock3(v2);
  STRA::~STRA((FTP_LOGGING *)((char *)this + 24));
}

```

## disassembly

```asm
0x180026e48  mov     [rsp+arg_0], rbx
0x180026e4d  mov     [rsp+arg_8], rsi
0x180026e52  push    rdi
0x180026e53  sub     rsp, 30h
0x180026e57  mov     rbx, rcx
0x180026e5a  lea     rsi, [rcx+5Ch]
0x180026e5e  mov     rcx, rsi
0x180026e61  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180026e67  mov     rcx, [rbx+10h]; this
0x180026e6b  test    rcx, rcx
0x180026e6e  jz      short loc_180026EC6
0x180026e70  call    ?Flush@FTP_LOG_FILE@@QEAAJXZ; FTP_LOG_FILE::Flush(void)
0x180026e75  mov     edi, eax
0x180026e77  mov     rcx, [rbx+10h]; this
0x180026e7b  call    ?DereferenceLogFile@FTP_LOG_FILE@@QEAAXXZ; FTP_LOG_FILE::DereferenceLogFile(void)
0x180026e80  mov     qword ptr [rbx+10h], 0
0x180026e88  test    edi, edi
0x180026e8a  jns     short loc_180026EC6
0x180026e8c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180026e93  jz      short loc_180026EC6
0x180026e95  lea     rax, aFailedToCloseF; "Failed to close Ftp Logging.\n"
0x180026e9c  mov     [rsp+38h+var_10], rax
0x180026ea1  mov     [rsp+38h+var_18], edi
0x180026ea5  lea     r9, aFtpLoggingFtpL; "FTP_LOGGING::~FTP_LOGGING"
0x180026eac  mov     r8d, 45h ; 'E'
0x180026eb2  lea     rdx, aInetsrvIisIisr_27; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x180026eb9  mov     rcx, cs:g_pDebug
0x180026ec0  call    cs:__imp_PuDbgPrintError
0x180026ec6  mov     rcx, rsi
0x180026ec9  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180026ecf  mov     rdi, [rbx+8]
0x180026ed3  test    rdi, rdi
0x180026ed6  jz      short loc_180026EFB
0x180026ed8  lea     rcx, [rdi+38h]
0x180026edc  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180026ee2  mov     rcx, rdi
0x180026ee5  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180026eeb  mov     rcx, rdi; Block
0x180026eee  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026ef3  mov     qword ptr [rbx+8], 0
0x180026efb  mov     dword ptr [rbx], 6C737466h
0x180026f01  mov     rcx, rsi
0x180026f04  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x180026f0a  lea     rcx, [rbx+18h]
0x180026f0e  mov     rbx, [rsp+38h+arg_0]
0x180026f13  mov     rsi, [rsp+38h+arg_8]
0x180026f18  add     rsp, 30h
0x180026f1c  pop     rdi
0x180026f1d  jmp     cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
```
