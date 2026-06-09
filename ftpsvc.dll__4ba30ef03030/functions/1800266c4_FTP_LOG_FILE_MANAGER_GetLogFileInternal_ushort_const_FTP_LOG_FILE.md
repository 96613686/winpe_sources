# FTP_LOG_FILE_MANAGER::GetLogFileInternal(ushort const *,FTP_LOG_FILE * *)

- ea: `0x1800266c4`
- end: `0x18002680e`
- name: `?GetLogFileInternal@FTP_LOG_FILE_MANAGER@@AEAAJPEBGPEAPEAVFTP_LOG_FILE@@@Z`
- size: `330`
- prototype: `__int64 __fastcall(FTP_LOG_FILE_MANAGER *__hidden this, const unsigned __int16 *Src, struct FTP_LOG_FILE **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180026580`

## callees

- `0x180001210`
- `0x1800266c4`
- `0x180028628`
- `0x18002877c`

## import_xrefs

- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800266de`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800266de`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800267f9`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800267f9`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18002678c`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18002678c`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1800266f8`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1800266f8`
- `iisutil!PuDbgPrintError` at `0x1800267ce`
- `iisutil!PuDbgPrintError` at `0x1800267ce`

## pseudocode

```c
__int64 __fastcall FTP_LOG_FILE_MANAGER::GetLogFileInternal(
        FTP_LOG_FILE_MANAGER *this,
        const unsigned __int16 *Src,
        struct FTP_LOG_FILE **a3)
{
  __int64 v6; // rcx
  struct FTP_LOG_FILE *v7; // rax
  struct FTP_LOG_FILE *v8; // rbx
  int v9; // edi
  struct FTP_LOG_FILE *v11; // [rsp+70h] [rbp+8h] BYREF

  CReaderWriterLock3::WriteLock((FTP_LOG_FILE_MANAGER *)((char *)this + 48));
  v6 = *((_QWORD *)this + 1);
  v11 = 0;
  if ( !(unsigned int)CLKRHashTable::FindKey(v6, Src, &v11) )
  {
    v8 = v11;
    goto LABEL_11;
  }
  v7 = (struct FTP_LOG_FILE *)operator new(0x88u);
  v11 = v7;
  v8 = v7;
  if ( !v7 )
  {
    v9 = -2147024888;
    goto LABEL_12;
  }
  *((_QWORD *)v7 + 1) = 0;
  *((_QWORD *)v7 + 2) = -1;
  *((_DWORD *)v7 + 6) = 1;
  *((_QWORD *)v7 + 4) = 0;
  *((_QWORD *)v7 + 5) = 0;
  *((_DWORD *)v7 + 12) = 0;
  *((_QWORD *)v7 + 7) = 0;
  *((_QWORD *)v7 + 8) = 0;
  *((_QWORD *)v7 + 9) = 0;
  *((_QWORD *)v7 + 10) = 0;
  *((_DWORD *)v7 + 31) = 0;
  *((_DWORD *)v7 + 32) = 0;
  *((_QWORD *)v7 + 14) = 0;
  *((_QWORD *)v7 + 13) = 0;
  *(_DWORD *)v7 = 1179929670;
  v9 = FTP_LOG_FILE::Initialize(v7, Src, this);
  if ( v9 >= 0 )
  {
    if ( (unsigned int)CLKRHashTable::InsertRecord(*((_QWORD *)this + 1), v8, 0) )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_logging\\ftp_log_file_manager.cxx",
          574,
          "FTP_LOG_FILE_MANAGER::GetLogFileInternal",
          -2147467259,
          "Failed to add new \"log file\" entry to the hash table\n");
      v9 = -2147467259;
      goto LABEL_8;
    }
LABEL_11:
    v9 = 0;
    *a3 = v8;
    goto LABEL_12;
  }
LABEL_8:
  FTP_LOG_FILE::DereferenceLogFile(v8);
LABEL_12:
  CReaderWriterLock3::WriteUnlock((FTP_LOG_FILE_MANAGER *)((char *)this + 48));
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800266c4  push    rbx
0x1800266c6  push    rbp
0x1800266c7  push    rsi
0x1800266c8  push    rdi
0x1800266c9  push    r14
0x1800266cb  push    r15
0x1800266cd  sub     rsp, 38h
0x1800266d1  mov     rsi, rcx
0x1800266d4  mov     r14, r8
0x1800266d7  add     rcx, 30h ; '0'
0x1800266db  mov     rdi, rdx
0x1800266de  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800266e4  mov     rcx, [rsi+8]
0x1800266e8  lea     r8, [rsp+68h+arg_0]
0x1800266ed  xor     r15d, r15d
0x1800266f0  mov     rdx, rdi
0x1800266f3  mov     [rsp+68h+arg_0], r15
0x1800266f8  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x1800266fe  test    eax, eax
0x180026700  jz      loc_1800267EA
0x180026706  mov     ecx, 88h; Size
0x18002670b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026710  mov     [rsp+68h+arg_0], rax
0x180026715  mov     rbx, rax
0x180026718  test    rax, rax
0x18002671b  jz      loc_1800267E3
0x180026721  mov     [rax+8], r15
0x180026725  mov     qword ptr [rax+10h], 0FFFFFFFFFFFFFFFFh
0x18002672d  mov     dword ptr [rax+18h], 1
0x180026734  mov     [rax+20h], r15
0x180026738  mov     [rax+28h], r15
0x18002673c  mov     [rax+30h], r15d
0x180026740  mov     [rax+38h], r15
0x180026744  mov     [rax+40h], r15
0x180026748  mov     [rax+48h], r15
0x18002674c  mov     [rax+50h], r15
0x180026750  mov     [rax+7Ch], r15d
0x180026754  mov     [rax+80h], r15d
0x18002675b  mov     [rax+70h], r15
0x18002675f  mov     [rax+68h], r15
0x180026763  mov     dword ptr [rax], 46544C46h
0x180026769  test    rax, rax
0x18002676c  jz      short loc_1800267E3
0x18002676e  mov     r8, rsi; struct FTP_LOG_FILE_MANAGER *
0x180026771  mov     rdx, rdi; Src
0x180026774  mov     rcx, rax; this
0x180026777  call    ?Initialize@FTP_LOG_FILE@@QEAAJPEBGPEAVFTP_LOG_FILE_MANAGER@@@Z; FTP_LOG_FILE::Initialize(ushort const *,FTP_LOG_FILE_MANAGER *)
0x18002677c  mov     edi, eax
0x18002677e  test    eax, eax
0x180026780  js      short loc_1800267D9
0x180026782  mov     rcx, [rsi+8]
0x180026786  xor     r8d, r8d
0x180026789  mov     rdx, rbx
0x18002678c  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x180026792  test    eax, eax
0x180026794  jz      short loc_1800267EF
0x180026796  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002679d  jz      short loc_1800267D4
0x18002679f  mov     rcx, cs:g_pDebug
0x1800267a6  lea     rax, aFailedToAddNew_1; "Failed to add new \"log file\" entry to"...
0x1800267ad  mov     [rsp+68h+var_40], rax
0x1800267b2  lea     r9, aFtpLogFileMana_3; "FTP_LOG_FILE_MANAGER::GetLogFileInterna"...
0x1800267b9  mov     r8d, 23Eh
0x1800267bf  mov     [rsp+68h+var_48], 80004005h
0x1800267c7  lea     rdx, aInetsrvIisIisr_11; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x1800267ce  call    cs:__imp_PuDbgPrintError
0x1800267d4  mov     edi, 80004005h
0x1800267d9  mov     rcx, rbx; this
0x1800267dc  call    ?DereferenceLogFile@FTP_LOG_FILE@@QEAAXXZ; FTP_LOG_FILE::DereferenceLogFile(void)
0x1800267e1  jmp     short loc_1800267F5
0x1800267e3  mov     edi, 80070008h
0x1800267e8  jmp     short loc_1800267F5
0x1800267ea  mov     rbx, [rsp+68h+arg_0]
0x1800267ef  mov     edi, r15d
0x1800267f2  mov     [r14], rbx
0x1800267f5  lea     rcx, [rsi+30h]
0x1800267f9  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x1800267ff  mov     eax, edi
0x180026801  add     rsp, 38h
0x180026805  pop     r15
0x180026807  pop     r14
0x180026809  pop     rdi
0x18002680a  pop     rsi
0x18002680b  pop     rbp
0x18002680c  pop     rbx
0x18002680d  retn
```
