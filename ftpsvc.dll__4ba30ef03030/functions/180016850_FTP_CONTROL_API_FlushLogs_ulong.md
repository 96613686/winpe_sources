# FTP_CONTROL_API::FlushLogs(ulong)

- ea: `0x180016850`
- end: `0x180016a80`
- name: `?FlushLogs@FTP_CONTROL_API@@UEAAJK@Z`
- size: `560`
- prototype: `__int64 __fastcall(FTP_CONTROL_API *this, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x180001250`
- `0x180008f40`
- `0x18000c3c8`
- `0x180016850`
- `0x180026acc`
- `0x180026fdc`
- `0x1800286a4`
- `0x180049010`

## import_xrefs

- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180016886`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800168ba`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180016966`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180016886`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800168ba`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180016966`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800169ae`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800169ae`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800169c8`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800169c8`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800168cb`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180016982`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180016a5f`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800168cb`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180016982`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180016a5f`
- `iisutil!PuDbgPrintError` at `0x180016947`
- `iisutil!PuDbgPrintError` at `0x180016a0b`
- `iisutil!PuDbgPrintError` at `0x180016947`
- `iisutil!PuDbgPrintError` at `0x180016a0b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FTP_CONTROL_API::FlushLogs(FTP_CONTROL_API *this, unsigned int a2)
{
  volatile signed __int32 *v2; // rbx
  int v6; // r14d
  _QWORD *v7; // rbp
  int v8; // ebx
  struct FTP_LOGGING *ReferencedGlobalFtpLogging; // rbp
  FTP_SITE_MANAGER *v10; // rax
  int v11; // edi
  void *v12; // rdi
  CReaderWriterLock3 *v13; // rbx
  FTP_LOG_FILE *v14; // rcx
  void *Block; // [rsp+70h] [rbp+8h] BYREF

  v2 = 0;
  Block = 0;
  if ( *((_DWORD *)this + 7) )
    return 2147943462LL;
  CReaderWriterLock3::ReadLock((FTP_CONTROL_API *)((char *)this + 16));
  if ( *((_DWORD *)this + 7) )
  {
    v6 = 0;
    v11 = -2147023834;
    goto LABEL_20;
  }
  v6 = 1;
  _InterlockedAdd((volatile signed __int32 *)this + 6, 1u);
  v7 = (_QWORD *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 16LL))(g_pFtpServer);
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v7 + 6));
  v8 = *(_DWORD *)(v7[2] + 8LL);
  CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)(v7 + 6));
  if ( v8 != 1 )
  {
    v10 = (FTP_SITE_MANAGER *)(**(__int64 (__fastcall ***)(FTP_SERVERP *))g_pFtpServer)(g_pFtpServer);
    v11 = FTP_SITE_MANAGER::LookupSiteBySiteId(v10, a2, (struct FTP_SITE **)&Block);
    if ( v11 >= 0 )
    {
      v12 = Block;
      v13 = (CReaderWriterLock3 *)((char *)Block + 216);
      CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)((char *)Block + 216));
      _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)v12 + 23) + 4LL), 1u);
      ReferencedGlobalFtpLogging = (struct FTP_LOGGING *)*((_QWORD *)v12 + 23);
      CReaderWriterLock3::ReadUnlock(v13);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 + 44, 0xFFFFFFFF) == 1 )
      {
        FTP_SITE::~FTP_SITE((FTP_SITE *)v12);
        operator delete(v12);
      }
      goto LABEL_12;
    }
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_control_api.cxx",
        536,
        "FTP_CONTROL_API::FlushLogs",
        v11,
        "Failed to look up the Ftp Site %d\n",
        a2);
    v2 = (volatile signed __int32 *)Block;
LABEL_20:
    if ( v2 && _InterlockedExchangeAdd(v2 + 44, 0xFFFFFFFF) == 1 )
    {
      FTP_SITE::~FTP_SITE((FTP_SITE *)v2);
      operator delete((void *)v2);
    }
    goto LABEL_23;
  }
  ReferencedGlobalFtpLogging = FTP_LOG_FILE_MANAGER::QueryReferencedGlobalFtpLogging((FTP_LOG_FILE_MANAGER *)v7);
LABEL_12:
  v11 = 0;
  CReaderWriterLock3::WriteLock((struct FTP_LOGGING *)((char *)ReferencedGlobalFtpLogging + 92));
  v14 = (FTP_LOG_FILE *)*((_QWORD *)ReferencedGlobalFtpLogging + 2);
  if ( v14 )
    v11 = FTP_LOG_FILE::Flush(v14);
  CReaderWriterLock3::WriteUnlock((struct FTP_LOGGING *)((char *)ReferencedGlobalFtpLogging + 92));
  if ( v11 < 0 && (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_control_api.cxx",
      558,
      "FTP_CONTROL_API::FlushLogs",
      v11,
      "Failed to flush logs of the Ftp Site %d\n",
      a2);
  if ( ReferencedGlobalFtpLogging )
    FTP_LOGGING::DereferenceFtpLogging(ReferencedGlobalFtpLogging);
LABEL_23:
  if ( v6 )
    _InterlockedDecrement((volatile signed __int32 *)this + 6);
  CReaderWriterLock3::ReadUnlock((FTP_CONTROL_API *)((char *)this + 16));
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180016850  mov     [rsp+arg_8], rbx
0x180016855  mov     [rsp+arg_10], rbp
0x18001685a  push    rsi
0x18001685b  push    rdi
0x18001685c  push    r12
0x18001685e  push    r14
0x180016860  push    r15
0x180016862  sub     rsp, 40h
0x180016866  xor     ebx, ebx
0x180016868  mov     r15d, edx
0x18001686b  mov     rsi, rcx
0x18001686e  mov     [rsp+68h+Block], rbx
0x180016873  cmp     [rcx+1Ch], ebx
0x180016876  jz      short loc_180016882
0x180016878  mov     eax, 80070426h
0x18001687d  jmp     loc_180016A67
0x180016882  add     rcx, 10h
0x180016886  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18001688c  cmp     [rsi+1Ch], ebx
0x18001688f  jnz     loc_180016A20
0x180016895  mov     r14d, 1
0x18001689b  lock add [rsi+18h], r14d
0x1800168a0  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x1800168a7  mov     rax, [rcx]
0x1800168aa  mov     rax, [rax+10h]
0x1800168ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168b3  mov     rbp, rax
0x1800168b6  lea     rcx, [rax+30h]
0x1800168ba  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x1800168c0  mov     rdx, [rbp+10h]
0x1800168c4  lea     rcx, [rbp+30h]
0x1800168c8  mov     ebx, [rdx+8]
0x1800168cb  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x1800168d1  cmp     ebx, r14d
0x1800168d4  jnz     short loc_1800168E6
0x1800168d6  mov     rcx, rbp; this
0x1800168d9  call    ?QueryReferencedGlobalFtpLogging@FTP_LOG_FILE_MANAGER@@QEAAPEAVFTP_LOGGING@@XZ; FTP_LOG_FILE_MANAGER::QueryReferencedGlobalFtpLogging(void)
0x1800168de  mov     rbp, rax
0x1800168e1  jmp     loc_1800169A8
0x1800168e6  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x1800168ed  mov     rax, [rcx]
0x1800168f0  mov     rax, [rax]
0x1800168f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168f8  lea     r8, [rsp+68h+Block]; struct FTP_SITE **
0x1800168fd  mov     edx, r15d; unsigned int
0x180016900  mov     rcx, rax; this
0x180016903  call    ?LookupSiteBySiteId@FTP_SITE_MANAGER@@QEAAJKPEAPEAVFTP_SITE@@@Z; FTP_SITE_MANAGER::LookupSiteBySiteId(ulong,FTP_SITE * *)
0x180016908  mov     edi, eax
0x18001690a  test    eax, eax
0x18001690c  jns     short loc_180016957
0x18001690e  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180016915  jz      short loc_18001694D
0x180016917  mov     rcx, cs:g_pDebug
0x18001691e  lea     rax, aFailedToLookUp; "Failed to look up the Ftp Site %d\n"
0x180016925  mov     [rsp+68h+var_38], r15d
0x18001692a  lea     r9, aFtpControlApiF; "FTP_CONTROL_API::FlushLogs"
0x180016931  mov     [rsp+68h+var_40], rax
0x180016936  lea     rdx, aInetsrvIisIisr_13; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18001693d  mov     r8d, 218h
0x180016943  mov     [rsp+68h+var_48], edi
0x180016947  call    cs:__imp_PuDbgPrintError
0x18001694d  mov     rbx, [rsp+68h+Block]
0x180016952  jmp     loc_180016A28
0x180016957  mov     rdi, [rsp+68h+Block]
0x18001695c  lea     rbx, [rdi+0D8h]
0x180016963  mov     rcx, rbx
0x180016966  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18001696c  mov     rax, [rdi+0B8h]
0x180016973  lock add [rax+4], r14d
0x180016978  mov     rbp, [rdi+0B8h]
0x18001697f  mov     rcx, rbx
0x180016982  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180016988  or      eax, 0FFFFFFFFh
0x18001698b  lock xadd [rdi+0B0h], eax
0x180016993  cmp     eax, r14d
0x180016996  jnz     short loc_1800169A8
0x180016998  mov     rcx, rdi; this
0x18001699b  call    ??1FTP_SITE@@AEAA@XZ; FTP_SITE::~FTP_SITE(void)
0x1800169a0  mov     rcx, rdi; Block
0x1800169a3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800169a8  lea     rcx, [rbp+5Ch]
0x1800169ac  xor     edi, edi
0x1800169ae  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800169b4  mov     rcx, [rbp+10h]; this
0x1800169b8  test    rcx, rcx
0x1800169bb  jz      short loc_1800169C4
0x1800169bd  call    ?Flush@FTP_LOG_FILE@@QEAAJXZ; FTP_LOG_FILE::Flush(void)
0x1800169c2  mov     edi, eax
0x1800169c4  lea     rcx, [rbp+5Ch]
0x1800169c8  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x1800169ce  test    edi, edi
0x1800169d0  jns     short loc_180016A11
0x1800169d2  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800169d9  jz      short loc_180016A11
0x1800169db  mov     rcx, cs:g_pDebug
0x1800169e2  lea     rax, aFailedToFlushL; "Failed to flush logs of the Ftp Site %d"...
0x1800169e9  mov     [rsp+68h+var_38], r15d
0x1800169ee  lea     r9, aFtpControlApiF; "FTP_CONTROL_API::FlushLogs"
0x1800169f5  mov     [rsp+68h+var_40], rax
0x1800169fa  lea     rdx, aInetsrvIisIisr_13; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x180016a01  mov     r8d, 22Eh
0x180016a07  mov     [rsp+68h+var_48], edi
0x180016a0b  call    cs:__imp_PuDbgPrintError
0x180016a11  test    rbp, rbp
0x180016a14  jz      short loc_180016A52
0x180016a16  mov     rcx, rbp; this
0x180016a19  call    ?DereferenceFtpLogging@FTP_LOGGING@@QEAAXXZ; FTP_LOGGING::DereferenceFtpLogging(void)
0x180016a1e  jmp     short loc_180016A52
0x180016a20  xor     r14d, r14d
0x180016a23  mov     edi, 80070426h
0x180016a28  test    rbx, rbx
0x180016a2b  jz      short loc_180016A52
0x180016a2d  or      eax, 0FFFFFFFFh
0x180016a30  lock xadd [rbx+0B0h], eax
0x180016a38  cmp     eax, 1
0x180016a3b  jnz     short loc_180016A52
0x180016a3d  test    rbx, rbx
0x180016a40  jz      short loc_180016A52
0x180016a42  mov     rcx, rbx; this
0x180016a45  call    ??1FTP_SITE@@AEAA@XZ; FTP_SITE::~FTP_SITE(void)
0x180016a4a  mov     rcx, rbx; Block
0x180016a4d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016a52  test    r14d, r14d
0x180016a55  jz      short loc_180016A5B
0x180016a57  lock dec dword ptr [rsi+18h]
0x180016a5b  lea     rcx, [rsi+10h]
0x180016a5f  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180016a65  mov     eax, edi
0x180016a67  lea     r11, [rsp+68h+var_28]
0x180016a6c  mov     rbx, [r11+38h]
0x180016a70  mov     rbp, [r11+40h]
0x180016a74  mov     rsp, r11
0x180016a77  pop     r15
0x180016a79  pop     r14
0x180016a7b  pop     r12
0x180016a7d  pop     rdi
0x180016a7e  pop     rsi
0x180016a7f  retn
```
