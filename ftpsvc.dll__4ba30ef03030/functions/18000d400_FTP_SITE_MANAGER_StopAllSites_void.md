# FTP_SITE_MANAGER::StopAllSites(void)

- ea: `0x18000d400`
- end: `0x18000d6da`
- name: `?StopAllSites@FTP_SITE_MANAGER@@QEAAXXZ`
- size: `730`
- prototype: `void __fastcall(FTP_SITE_MANAGER *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005ca0`

## callees

- `0x180001250`
- `0x180008f40`
- `0x18000ab1c`
- `0x18000d400`
- `0x180026b10`

## import_xrefs

- `KERNEL32!Sleep` at `0x18000d615`
- `KERNEL32!Sleep` at `0x18000d663`
- `KERNEL32!Sleep` at `0x18000d6bf`
- `KERNEL32!Sleep` at `0x18000d615`
- `KERNEL32!Sleep` at `0x18000d663`
- `KERNEL32!Sleep` at `0x18000d6bf`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d46f`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d486`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d53a`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d46f`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d486`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d53a`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d49c`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d4dc`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d550`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d49c`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d4dc`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d550`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x18000d45f`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x18000d45f`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x18000d527`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x18000d527`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18000d42a`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18000d42a`
- `iisutil!PuDbgPrint` at `0x18000d60d`
- `iisutil!PuDbgPrint` at `0x18000d65b`
- `iisutil!PuDbgPrint` at `0x18000d6b7`
- `iisutil!PuDbgPrint` at `0x18000d60d`
- `iisutil!PuDbgPrint` at `0x18000d65b`
- `iisutil!PuDbgPrint` at `0x18000d6b7`
- `iisutil!PuDbgPrintError` at `0x18000d5c0`
- `iisutil!PuDbgPrintError` at `0x18000d5c0`

## string_xrefs

- `0x18000d691`: `FTP_LOG_FILE_MANAGER::StartShutdownAndWaitForShutdownCompletion`
- `0x18000d637`: `FTP_ENDPOINT_MANAGER::WaitForShutdownCompletion`

## pseudocode

```c
void __fastcall FTP_SITE_MANAGER::StopAllSites(FTP_SITE_MANAGER *this)
{
  char *v2; // r15
  __int64 v3; // rbx
  volatile signed __int32 *v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rcx
  volatile signed __int32 *v7; // rdi
  int v8; // r14d
  __int64 v9; // rbx
  int v10; // eax
  FTP_LOG_FILE_MANAGER *v11; // rbx
  int v12; // eax
  _QWORD v13[2]; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v14[5]; // [rsp+40h] [rbp-28h] BYREF

  v13[1] = v13;
  v2 = (char *)this + 8;
  v13[0] = v13;
  CLKRHashTable::Size((FTP_SITE_MANAGER *)((char *)this + 8));
  v14[0] = 0;
  v14[1] = FTP_SITE_MANAGER::BuildDeleteFtpSiteListAction;
  v14[2] = v13;
  CLKRHashTable::Apply(
    v2,
    CTypedHashTable<FTP_LOG_FILE_TABLE,FTP_LOG_FILE,unsigned short const *,CLKRHashTable>::_Action,
    v14,
    2);
  CReaderWriterLock3::WriteLock((FTP_SITE_MANAGER *)((char *)this + 176));
  v3 = *((_QWORD *)this + 21);
  CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)(v3 + 200));
  FTP_SITE::StopSiteNoLock((FTP_SITE *)v3, 0, 0);
  CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)(v3 + 200));
  v4 = (volatile signed __int32 *)*((_QWORD *)this + 21);
  if ( _InterlockedExchangeAdd(v4 + 44, 0xFFFFFFFF) == 1 && v4 )
  {
    FTP_SITE::~FTP_SITE((FTP_SITE *)v4);
    operator delete((void *)v4);
  }
  *((_QWORD *)this + 21) = 0;
  CReaderWriterLock3::WriteUnlock((FTP_SITE_MANAGER *)((char *)this + 176));
  while ( 1 )
  {
    v5 = v13[0];
    if ( (_QWORD *)v13[0] == v13 )
      break;
    if ( *(_QWORD **)(v13[0] + 8LL) != v13 || (v6 = *(_QWORD *)v13[0], *(_QWORD *)(*(_QWORD *)v13[0] + 8LL) != v13[0]) )
      __fastfail(3u);
    v13[0] = *(_QWORD *)v13[0];
    *(_QWORD *)(v6 + 8) = v13;
    v7 = (volatile signed __int32 *)(v5 - 264);
    v8 = CLKRHashTable::DeleteRecord(v2, v5 - 264);
    CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)(v7 + 50));
    FTP_SITE::StopSiteNoLock((FTP_SITE *)v7, 0, 0);
    CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)(v7 + 50));
    if ( _InterlockedExchangeAdd(v7 + 44, 0xFFFFFFFF) == 1 && v7 )
    {
      FTP_SITE::~FTP_SITE((FTP_SITE *)v7);
      operator delete((void *)v7);
    }
    if ( v8 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_site_manager.cxx",
          738,
          "FTP_SITE_MANAGER::StopAllSites",
          -2147467259,
          "Removing virtual site from hashtable failed\n");
    }
  }
  while ( *(_DWORD *)this )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_site_manager.cxx",
        755,
        "FTP_SITE_MANAGER::StopAllSites",
        "Waiting for %d sites to drain\n",
        *(_DWORD *)this);
    Sleep(0xC8u);
  }
  v9 = *((_QWORD *)this + 10);
  while ( 1 )
  {
    v10 = *(_DWORD *)(v9 + 4);
    if ( !v10 )
      break;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_endpoint_manager\\ftp_endpoint_manager.cxx",
        217,
        "FTP_ENDPOINT_MANAGER::WaitForShutdownCompletion",
        "Waiting for %d endpoints to drain\n",
        v10);
    Sleep(0xC8u);
  }
  v11 = (FTP_LOG_FILE_MANAGER *)*((_QWORD *)this + 23);
  FTP_LOG_FILE_MANAGER::StartShutdown(v11);
  while ( 1 )
  {
    v12 = *((_DWORD *)v11 + 1);
    if ( v12 == 1 )
      break;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_logging\\ftp_log_file_manager.cxx",
        675,
        "FTP_LOG_FILE_MANAGER::StartShutdownAndWaitForShutdownCompletion",
        "Waiting for %d log files to drain\n",
        v12 - 1);
    Sleep(0xC8u);
  }
}

```

## disassembly

```asm
0x18000d400  push    rbp
0x18000d402  push    rbx
0x18000d403  push    rsi
0x18000d404  push    rdi
0x18000d405  push    r14
0x18000d407  push    r15
0x18000d409  mov     rbp, rsp
0x18000d40c  sub     rsp, 68h
0x18000d410  lea     rax, [rbp+var_38]
0x18000d414  mov     rsi, rcx
0x18000d417  mov     [rbp+var_30], rax
0x18000d41b  lea     r15, [rcx+8]
0x18000d41f  lea     rax, [rbp+var_38]
0x18000d423  mov     rcx, r15
0x18000d426  mov     [rbp+var_38], rax
0x18000d42a  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x18000d430  lea     rax, ?BuildDeleteFtpSiteListAction@FTP_SITE_MANAGER@@CA?AW4LK_ACTION@@PEAVFTP_SITE@@PEAX@Z; FTP_SITE_MANAGER::BuildDeleteFtpSiteListAction(FTP_SITE *,void *)
0x18000d437  mov     [rbp+var_28], 0
0x18000d43f  mov     [rbp+var_20], rax
0x18000d443  lea     r8, [rbp+var_28]
0x18000d447  lea     rax, [rbp+var_38]
0x18000d44b  mov     r9d, 2
0x18000d451  lea     rdx, ?_Action@?$CTypedHashTable@VFTP_LOG_FILE_TABLE@@VFTP_LOG_FILE@@PEBGVCLKRHashTable@@@@CA?AW4LK_ACTION@@PEBXPEAX@Z; CTypedHashTable<FTP_LOG_FILE_TABLE,FTP_LOG_FILE,ushort const *,CLKRHashTable>::_Action(void const *,void *)
0x18000d458  mov     [rbp+var_18], rax
0x18000d45c  mov     rcx, r15
0x18000d45f  call    cs:__imp_?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z; CLKRHashTable::Apply(LK_ACTION (*)(void const *,void *),void *,LK_LOCKTYPE)
0x18000d465  lea     r14, [rsi+0B0h]
0x18000d46c  mov     rcx, r14
0x18000d46f  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000d475  mov     rbx, [rsi+0A8h]
0x18000d47c  lea     rdi, [rbx+0C8h]
0x18000d483  mov     rcx, rdi
0x18000d486  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000d48c  xor     r8d, r8d; int
0x18000d48f  xor     edx, edx; int
0x18000d491  mov     rcx, rbx; this
0x18000d494  call    ?StopSiteNoLock@FTP_SITE@@QEAAJJH@Z; FTP_SITE::StopSiteNoLock(long,int)
0x18000d499  mov     rcx, rdi
0x18000d49c  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000d4a2  mov     rbx, [rsi+0A8h]
0x18000d4a9  or      eax, 0FFFFFFFFh
0x18000d4ac  lock xadd [rbx+0B0h], eax
0x18000d4b4  cmp     eax, 1
0x18000d4b7  jnz     short loc_18000D4CE
0x18000d4b9  test    rbx, rbx
0x18000d4bc  jz      short loc_18000D4CE
0x18000d4be  mov     rcx, rbx; this
0x18000d4c1  call    ??1FTP_SITE@@AEAA@XZ; FTP_SITE::~FTP_SITE(void)
0x18000d4c6  mov     rcx, rbx; Block
0x18000d4c9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d4ce  mov     rcx, r14
0x18000d4d1  mov     qword ptr [rsi+0A8h], 0
0x18000d4dc  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000d4e2  mov     rax, [rbp+var_38]
0x18000d4e6  lea     rcx, [rbp+var_38]
0x18000d4ea  cmp     rax, rcx
0x18000d4ed  jz      loc_18000D5D2
0x18000d4f3  lea     rcx, [rbp+var_38]
0x18000d4f7  cmp     [rax+8], rcx
0x18000d4fb  jnz     loc_18000D5CB
0x18000d501  mov     rcx, [rax]
0x18000d504  cmp     [rcx+8], rax
0x18000d508  jnz     loc_18000D5CB
0x18000d50e  mov     [rbp+var_38], rcx
0x18000d512  lea     rdx, [rbp+var_38]
0x18000d516  mov     [rcx+8], rdx
0x18000d51a  lea     rdi, [rax-108h]
0x18000d521  mov     rdx, rdi
0x18000d524  mov     rcx, r15
0x18000d527  call    cs:__imp_?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z; CLKRHashTable::DeleteRecord(void const *)
0x18000d52d  lea     rbx, [rdi+0C8h]
0x18000d534  mov     r14d, eax
0x18000d537  mov     rcx, rbx
0x18000d53a  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000d540  xor     r8d, r8d; int
0x18000d543  xor     edx, edx; int
0x18000d545  mov     rcx, rdi; this
0x18000d548  call    ?StopSiteNoLock@FTP_SITE@@QEAAJJH@Z; FTP_SITE::StopSiteNoLock(long,int)
0x18000d54d  mov     rcx, rbx
0x18000d550  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000d556  or      edx, 0FFFFFFFFh
0x18000d559  lock xadd [rdi+0B0h], edx
0x18000d561  cmp     edx, 1
0x18000d564  jnz     short loc_18000D57B
0x18000d566  test    rdi, rdi
0x18000d569  jz      short loc_18000D57B
0x18000d56b  mov     rcx, rdi; this
0x18000d56e  call    ??1FTP_SITE@@AEAA@XZ; FTP_SITE::~FTP_SITE(void)
0x18000d573  mov     rcx, rdi; Block
0x18000d576  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d57b  test    r14d, r14d
0x18000d57e  jz      loc_18000D4E2
0x18000d584  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000d58b  jz      loc_18000D4E2
0x18000d591  mov     rcx, cs:g_pDebug
0x18000d598  lea     rax, aRemovingVirtua; "Removing virtual site from hashtable fa"...
0x18000d59f  mov     [rsp+68h+var_40], rax
0x18000d5a4  lea     r9, aFtpSiteManager_2; "FTP_SITE_MANAGER::StopAllSites"
0x18000d5ab  mov     r8d, 2E2h
0x18000d5b1  mov     dword ptr [rsp+68h+var_48], 80004005h
0x18000d5b9  lea     rdx, aInetsrvIisIisr_18; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18000d5c0  call    cs:__imp_PuDbgPrintError
0x18000d5c6  jmp     loc_18000D4E2
0x18000d5cb  mov     ecx, 3
0x18000d5d0  int     29h; Win8: RtlFailFast(ecx)
0x18000d5d2  mov     edi, 0C8h
0x18000d5d7  jmp     short loc_18000D61B
0x18000d5d9  test    byte ptr cs:g_dwDebugFlags, 3
0x18000d5e0  jz      short loc_18000D613
0x18000d5e2  mov     rcx, cs:g_pDebug
0x18000d5e9  lea     r9, aFtpSiteManager_2; "FTP_SITE_MANAGER::StopAllSites"
0x18000d5f0  mov     dword ptr [rsp+68h+var_40], eax
0x18000d5f4  lea     rdx, aInetsrvIisIisr_18; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18000d5fb  lea     rax, aWaitingForDSit; "Waiting for %d sites to drain\n"
0x18000d602  mov     r8d, 2F3h
0x18000d608  mov     [rsp+68h+var_48], rax
0x18000d60d  call    cs:__imp_PuDbgPrint
0x18000d613  mov     ecx, edi; dwMilliseconds
0x18000d615  call    cs:__imp_Sleep
0x18000d61b  mov     eax, [rsi]
0x18000d61d  test    eax, eax
0x18000d61f  jnz     short loc_18000D5D9
0x18000d621  mov     rbx, [rsi+50h]
0x18000d625  jmp     short loc_18000D669
0x18000d627  test    byte ptr cs:g_dwDebugFlags, 3
0x18000d62e  jz      short loc_18000D661
0x18000d630  mov     rcx, cs:g_pDebug
0x18000d637  lea     r9, aFtpEndpointMan_0; "FTP_ENDPOINT_MANAGER::WaitForShutdownCo"...
0x18000d63e  mov     dword ptr [rsp+68h+var_40], eax
0x18000d642  lea     rdx, aInetsrvIisIisr_9; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x18000d649  lea     rax, aWaitingForDEnd; "Waiting for %d endpoints to drain\n"
0x18000d650  mov     r8d, 0D9h
0x18000d656  mov     [rsp+68h+var_48], rax
0x18000d65b  call    cs:__imp_PuDbgPrint
0x18000d661  mov     ecx, edi; dwMilliseconds
0x18000d663  call    cs:__imp_Sleep
0x18000d669  mov     eax, [rbx+4]
0x18000d66c  test    eax, eax
0x18000d66e  jnz     short loc_18000D627
0x18000d670  mov     rbx, [rsi+0B8h]
0x18000d677  mov     rcx, rbx; this
0x18000d67a  call    ?StartShutdown@FTP_LOG_FILE_MANAGER@@AEAAXXZ; FTP_LOG_FILE_MANAGER::StartShutdown(void)
0x18000d67f  jmp     short loc_18000D6C5
0x18000d681  test    byte ptr cs:g_dwDebugFlags, 3
0x18000d688  jz      short loc_18000D6BD
0x18000d68a  mov     rcx, cs:g_pDebug
0x18000d691  lea     r9, aFtpLogFileMana; "FTP_LOG_FILE_MANAGER::StartShutdownAndW"...
0x18000d698  dec     eax
0x18000d69a  lea     rdx, aInetsrvIisIisr_11; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x18000d6a1  mov     dword ptr [rsp+68h+var_40], eax
0x18000d6a5  mov     r8d, 2A3h
0x18000d6ab  lea     rax, aWaitingForDLog; "Waiting for %d log files to drain\n"
0x18000d6b2  mov     [rsp+68h+var_48], rax
0x18000d6b7  call    cs:__imp_PuDbgPrint
0x18000d6bd  mov     ecx, edi; dwMilliseconds
0x18000d6bf  call    cs:__imp_Sleep
0x18000d6c5  mov     eax, [rbx+4]
0x18000d6c8  cmp     eax, 1
0x18000d6cb  jnz     short loc_18000D681
0x18000d6cd  add     rsp, 68h
0x18000d6d1  pop     r15
0x18000d6d3  pop     r14
0x18000d6d5  pop     rdi
0x18000d6d6  pop     rsi
0x18000d6d7  pop     rbx
0x18000d6d8  pop     rbp
0x18000d6d9  retn
```
