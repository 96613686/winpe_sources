# FTP_SERVERP::ResetAppHostAdminMgrThreadProc(void *)

- ea: `0x180004610`
- end: `0x1800047c6`
- name: `?ResetAppHostAdminMgrThreadProc@FTP_SERVERP@@CAKPEAX@Z`
- size: `438`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callees

- `0x180001250`
- `0x180003bd8`
- `0x180004610`
- `0x180004980`
- `0x18000cb74`
- `0x180049010`

## import_xrefs

- `KERNEL32!Sleep` at `0x180004661`
- `KERNEL32!Sleep` at `0x180004661`
- `KERNEL32!CloseHandle` at `0x180004772`
- `KERNEL32!CloseHandle` at `0x180004772`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800046b9`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800046b9`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180004708`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000475b`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180004708`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000475b`
- `iisutil!PuDbgPrint` at `0x1800046a0`
- `iisutil!PuDbgPrint` at `0x1800046a0`

## string_xrefs

- `0x18000467c`: `InitializeAppHostConfiguration() failed.  hr = %x\n`
- `0x180004687`: `FTP_SERVERP::ResetAppHostAdminMgrThreadProc`

## pseudocode

```c
__int64 __fastcall FTP_SERVERP::ResetAppHostAdminMgrThreadProc(CReaderWriterLock3 **Parameter)
{
  unsigned int v1; // ebx
  DWORD v2; // edi
  int v4; // ebp
  struct IAppHostAdminManager *v5; // r15
  struct FTP_CONFIG_CHANGE_NOTIFICATION *v6; // r14
  FTP_SITE_MANAGER *v7; // rdi
  unsigned int v8; // ebx
  FTP_SERVERP *v9; // rax
  __int64 v10; // rcx
  void *v11; // rcx
  struct IAppHostAdminManager *v13; // [rsp+60h] [rbp+8h] BYREF
  struct FTP_CONFIG_CHANGE_NOTIFICATION *v14; // [rsp+68h] [rbp+10h] BYREF

  v1 = 0;
  v13 = 0;
  v2 = 0;
  v14 = 0;
  do
  {
    v4 = FTP_SERVERP::InitializeAppHostConfiguration(g_pFtpServer, 0, &v13, (struct IAppHostChangeHandler **)&v14);
    if ( v4 >= 0 )
    {
      CReaderWriterLock3::WriteLock(Parameter[2]);
      FTP_SERVERP::StopProcessingChangeNotifications(g_pFtpServer);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)*Parameter + 16LL))(*(_QWORD *)*Parameter);
      v5 = 0;
      v6 = 0;
      *(_QWORD *)*Parameter = 0;
      *(_QWORD *)*Parameter = v13;
      *(_QWORD *)Parameter[1] = v14;
      CReaderWriterLock3::WriteUnlock(Parameter[2]);
      v7 = (FTP_SITE_MANAGER *)(**(__int64 (__fastcall ***)(FTP_SERVERP *))g_pFtpServer)(g_pFtpServer);
      v8 = *((_DWORD *)v7 + 40) + 2 - (*((_DWORD *)v7 + 40) != -1);
      FTP_SITE_MANAGER::StartOrUpdateAllSites(v7, v8);
      v9 = g_pFtpServer;
      *((_DWORD *)v7 + 40) = v8;
      v10 = *((_QWORD *)v9 + 13);
      *(_DWORD *)(v10 + 16) = 0;
      CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)(v10 + 20));
      goto LABEL_8;
    }
    v2 += 1000;
    ++v1;
    Sleep(v2);
  }
  while ( v1 < 5 );
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_serverp.cxx",
      2182,
      "FTP_SERVERP::ResetAppHostAdminMgrThreadProc",
      "InitializeAppHostConfiguration() failed.  hr = %x\n",
      v4);
  v5 = v13;
  v6 = v14;
LABEL_8:
  if ( Parameter )
  {
    v11 = *(void **)Parameter[3];
    if ( v11 )
    {
      CloseHandle(v11);
      *(_QWORD *)Parameter[3] = 0;
    }
    operator delete(Parameter);
  }
  if ( v5 )
    ((void (__fastcall *)(struct IAppHostAdminManager *))v5->lpVtbl->Release)(v5);
  if ( v6 )
    (*(void (__fastcall **)(struct FTP_CONFIG_CHANGE_NOTIFICATION *))(*(_QWORD *)v6 + 16LL))(v6);
  return 0;
}

```

## disassembly

```asm
0x180004610  mov     [rsp+arg_10], rbx
0x180004615  push    rbp
0x180004616  push    rsi
0x180004617  push    rdi
0x180004618  push    r14
0x18000461a  push    r15
0x18000461c  sub     rsp, 30h
0x180004620  xor     ebx, ebx
0x180004622  mov     [rsp+58h+arg_0], 0
0x18000462b  xor     edi, edi
0x18000462d  mov     [rsp+58h+arg_8], 0
0x180004636  mov     rsi, rcx
0x180004639  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; this
0x180004640  lea     r9, [rsp+58h+arg_8]; struct FTP_CONFIG_CHANGE_NOTIFICATION **
0x180004645  lea     r8, [rsp+58h+arg_0]; struct IAppHostAdminManager **
0x18000464a  xor     edx, edx; int
0x18000464c  call    ?InitializeAppHostConfiguration@FTP_SERVERP@@AEAAJHPEAPEAUIAppHostAdminManager@@PEAPEAVFTP_CONFIG_CHANGE_NOTIFICATION@@@Z; FTP_SERVERP::InitializeAppHostConfiguration(int,IAppHostAdminManager * *,FTP_CONFIG_CHANGE_NOTIFICATION * *)
0x180004651  mov     ebp, eax
0x180004653  test    eax, eax
0x180004655  jns     short loc_1800046B5
0x180004657  add     edi, 3E8h
0x18000465d  inc     ebx
0x18000465f  mov     ecx, edi; dwMilliseconds
0x180004661  call    cs:__imp_Sleep
0x180004667  cmp     ebx, 5
0x18000466a  jb      short loc_180004639
0x18000466c  test    byte ptr cs:g_dwDebugFlags, 3
0x180004673  jz      short loc_1800046A6
0x180004675  mov     rcx, cs:g_pDebug
0x18000467c  lea     rax, aInitializeapph; "InitializeAppHostConfiguration() failed"...
0x180004683  mov     [rsp+58h+var_30], ebp
0x180004687  lea     r9, aFtpServerpRese; "FTP_SERVERP::ResetAppHostAdminMgrThread"...
0x18000468e  mov     r8d, 886h
0x180004694  mov     [rsp+58h+var_38], rax
0x180004699  lea     rdx, aInetsrvIisIisr_23; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x1800046a0  call    cs:__imp_PuDbgPrint
0x1800046a6  mov     r15, [rsp+58h+arg_0]
0x1800046ab  mov     r14, [rsp+58h+arg_8]
0x1800046b0  jmp     loc_180004761
0x1800046b5  mov     rcx, [rsi+10h]
0x1800046b9  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800046bf  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; this
0x1800046c6  call    ?StopProcessingChangeNotifications@FTP_SERVERP@@AEAAXXZ; FTP_SERVERP::StopProcessingChangeNotifications(void)
0x1800046cb  mov     rax, [rsi]
0x1800046ce  mov     rcx, [rax]
0x1800046d1  mov     rax, [rcx]
0x1800046d4  mov     rax, [rax+10h]
0x1800046d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046dd  mov     rax, [rsi]
0x1800046e0  xor     r15d, r15d
0x1800046e3  xor     r14d, r14d
0x1800046e6  mov     qword ptr [rax], 0
0x1800046ed  mov     rcx, [rsi]
0x1800046f0  mov     rax, [rsp+58h+arg_0]
0x1800046f5  mov     [rcx], rax
0x1800046f8  mov     rcx, [rsi+8]
0x1800046fc  mov     rax, [rsp+58h+arg_8]
0x180004701  mov     [rcx], rax
0x180004704  mov     rcx, [rsi+10h]
0x180004708  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000470e  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180004715  mov     rax, [rcx]
0x180004718  mov     rax, [rax]
0x18000471b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004720  mov     rdi, rax
0x180004723  mov     r8d, [rax+0A0h]
0x18000472a  lea     ecx, [r8+1]
0x18000472e  neg     ecx
0x180004730  mov     rcx, rax; this
0x180004733  sbb     edx, edx
0x180004735  lea     ebx, [rdx+2]
0x180004738  add     ebx, r8d
0x18000473b  mov     edx, ebx; unsigned int
0x18000473d  call    ?StartOrUpdateAllSites@FTP_SITE_MANAGER@@AEAAJK@Z; FTP_SITE_MANAGER::StartOrUpdateAllSites(ulong)
0x180004742  mov     rax, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180004749  mov     [rdi+0A0h], ebx
0x18000474f  mov     rcx, [rax+68h]
0x180004753  mov     [rcx+10h], r14d
0x180004757  add     rcx, 14h
0x18000475b  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180004761  test    rsi, rsi
0x180004764  jz      short loc_18000478B
0x180004766  mov     rax, [rsi+18h]
0x18000476a  mov     rcx, [rax]; hObject
0x18000476d  test    rcx, rcx
0x180004770  jz      short loc_180004783
0x180004772  call    cs:__imp_CloseHandle
0x180004778  mov     rax, [rsi+18h]
0x18000477c  mov     qword ptr [rax], 0
0x180004783  mov     rcx, rsi; Block
0x180004786  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000478b  test    r15, r15
0x18000478e  jz      short loc_18000479F
0x180004790  mov     rax, [r15]
0x180004793  mov     rcx, r15
0x180004796  mov     rax, [rax+10h]
0x18000479a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000479f  test    r14, r14
0x1800047a2  jz      short loc_1800047B3
0x1800047a4  mov     rax, [r14]
0x1800047a7  mov     rcx, r14
0x1800047aa  mov     rax, [rax+10h]
0x1800047ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047b3  mov     rbx, [rsp+58h+arg_10]
0x1800047b8  xor     eax, eax
0x1800047ba  add     rsp, 30h
0x1800047be  pop     r15
0x1800047c0  pop     r14
0x1800047c2  pop     rdi
0x1800047c3  pop     rsi
0x1800047c4  pop     rbp
0x1800047c5  retn
```
