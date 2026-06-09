# FTP_CONTROL_API::ControlSite(ulong,__MIDL_IFtpControl_0002)

- ea: `0x1800160a0`
- end: `0x180016254`
- name: `?ControlSite@FTP_CONTROL_API@@UEAAJKW4__MIDL_IFtpControl_0002@@@Z`
- size: `436`
- prototype: `__int64 __fastcall(__int64, unsigned int, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x180001250`
- `0x180008f40`
- `0x18000aa00`
- `0x18000ab1c`
- `0x18000c3c8`
- `0x1800160a0`
- `0x180049010`

## import_xrefs

- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800160d4`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800160d4`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001617e`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001617e`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180016196`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180016196`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001623f`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001623f`
- `iisutil!PuDbgPrintError` at `0x180016155`
- `iisutil!PuDbgPrintError` at `0x1800161fb`
- `iisutil!PuDbgPrintError` at `0x180016155`
- `iisutil!PuDbgPrintError` at `0x1800161fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FTP_CONTROL_API::ControlSite(__int64 a1, unsigned int a2, int a3)
{
  bool v3; // zf
  int v8; // ebp
  FTP_SITE_MANAGER *v9; // rax
  int started; // ebx
  int v11; // edi
  FTP_SITE *v12; // rbx
  CReaderWriterLock3 *v13; // rdi
  FTP_SITE *v14; // rdi
  void *Block; // [rsp+80h] [rbp+8h] BYREF

  v3 = *(_DWORD *)(a1 + 28) == 0;
  Block = 0;
  if ( !v3 )
    return 2147943462LL;
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(a1 + 16));
  if ( *(_DWORD *)(a1 + 28) )
  {
    v8 = 0;
    started = -2147023834;
    goto LABEL_15;
  }
  v8 = 1;
  _InterlockedAdd((volatile signed __int32 *)(a1 + 24), 1u);
  v9 = (FTP_SITE_MANAGER *)(**(__int64 (__fastcall ***)(FTP_SERVERP *))g_pFtpServer)(g_pFtpServer);
  started = FTP_SITE_MANAGER::LookupSiteBySiteId(v9, a2, (struct FTP_SITE **)&Block);
  if ( started >= 0 )
  {
    v11 = a3 - 1;
    if ( v11 )
    {
      if ( v11 != 1 )
      {
        started = -2147024809;
        goto LABEL_15;
      }
      v12 = (FTP_SITE *)Block;
      v13 = (CReaderWriterLock3 *)((char *)Block + 200);
      CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)((char *)Block + 200));
      started = FTP_SITE::StopSiteNoLock(v12, 0, 1);
      CReaderWriterLock3::WriteUnlock(v13);
      if ( started < 0 )
      {
LABEL_15:
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_control_api.cxx",
            266,
            "FTP_CONTROL_API::ControlSite",
            started,
            "Failed to control the Ftp Site %d\n",
            a2);
        goto LABEL_17;
      }
    }
    else
    {
      started = FTP_SITE::StartSite((FTP_SITE *)Block, 1);
      if ( started < 0 )
        goto LABEL_15;
    }
    started = 0;
    goto LABEL_17;
  }
  if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    PuDbgPrintError(
      g_pDebug,
      "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_control_api.cxx",
      226,
      "FTP_CONTROL_API::ControlSite",
      started,
      "Failed to look up the Ftp Site %d\n",
      a2);
    goto LABEL_15;
  }
LABEL_17:
  v14 = (FTP_SITE *)Block;
  if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 44, 0xFFFFFFFF) == 1 && v14 )
  {
    FTP_SITE::~FTP_SITE(v14);
    operator delete(v14);
  }
  if ( v8 )
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 24));
  CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)(a1 + 16));
  return (unsigned int)started;
}

```

## disassembly

```asm
0x1800160a0  mov     rax, rsp
0x1800160a3  push    rbx
0x1800160a4  push    rbp
0x1800160a5  push    rsi
0x1800160a6  push    rdi
0x1800160a7  push    r14
0x1800160a9  push    r15
0x1800160ab  sub     rsp, 48h
0x1800160af  cmp     dword ptr [rcx+1Ch], 0
0x1800160b3  mov     edi, r8d
0x1800160b6  mov     r14d, edx
0x1800160b9  mov     qword ptr [rax+8], 0
0x1800160c1  mov     rsi, rcx
0x1800160c4  jz      short loc_1800160D0
0x1800160c6  mov     eax, 80070426h
0x1800160cb  jmp     loc_180016247
0x1800160d0  add     rcx, 10h
0x1800160d4  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x1800160da  cmp     dword ptr [rsi+1Ch], 0
0x1800160de  jnz     loc_1800161BB
0x1800160e4  mov     ebp, 1
0x1800160e9  lock add [rsi+18h], ebp
0x1800160ed  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x1800160f4  mov     rax, [rcx]
0x1800160f7  mov     rax, [rax]
0x1800160fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160ff  lea     r8, [rsp+78h+Block]; struct FTP_SITE **
0x180016107  mov     edx, r14d; unsigned int
0x18001610a  mov     rcx, rax; this
0x18001610d  call    ?LookupSiteBySiteId@FTP_SITE_MANAGER@@QEAAJKPEAPEAVFTP_SITE@@@Z; FTP_SITE_MANAGER::LookupSiteBySiteId(ulong,FTP_SITE * *)
0x180016112  mov     ebx, eax
0x180016114  test    eax, eax
0x180016116  jns     short loc_18001615D
0x180016118  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001611f  jz      loc_180016201
0x180016125  mov     rcx, cs:g_pDebug
0x18001612c  lea     rax, aFailedToLookUp; "Failed to look up the Ftp Site %d\n"
0x180016133  mov     [rsp+78h+var_48], r14d
0x180016138  lea     r9, aFtpControlApiC; "FTP_CONTROL_API::ControlSite"
0x18001613f  mov     [rsp+78h+var_50], rax
0x180016144  lea     rdx, aInetsrvIisIisr_13; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18001614b  mov     r8d, 0E2h
0x180016151  mov     [rsp+78h+var_58], ebx
0x180016155  call    cs:__imp_PuDbgPrintError
0x18001615b  jmp     short loc_1800161C2
0x18001615d  sub     edi, ebp
0x18001615f  jz      short loc_1800161A2
0x180016161  cmp     edi, ebp
0x180016163  jz      short loc_18001616C
0x180016165  mov     ebx, 80070057h
0x18001616a  jmp     short loc_1800161C2
0x18001616c  mov     rbx, [rsp+78h+Block]
0x180016174  lea     rdi, [rbx+0C8h]
0x18001617b  mov     rcx, rdi
0x18001617e  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180016184  mov     r8d, ebp; int
0x180016187  xor     edx, edx; int
0x180016189  mov     rcx, rbx; this
0x18001618c  call    ?StopSiteNoLock@FTP_SITE@@QEAAJJH@Z; FTP_SITE::StopSiteNoLock(long,int)
0x180016191  mov     rcx, rdi
0x180016194  mov     ebx, eax
0x180016196  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18001619c  test    ebx, ebx
0x18001619e  jns     short loc_1800161B7
0x1800161a0  jmp     short loc_1800161C2
0x1800161a2  mov     rcx, [rsp+78h+Block]; this
0x1800161aa  mov     edx, ebp; int
0x1800161ac  call    ?StartSite@FTP_SITE@@QEAAJH@Z; FTP_SITE::StartSite(int)
0x1800161b1  mov     ebx, eax
0x1800161b3  test    eax, eax
0x1800161b5  js      short loc_1800161C2
0x1800161b7  xor     ebx, ebx
0x1800161b9  jmp     short loc_180016201
0x1800161bb  xor     ebp, ebp
0x1800161bd  mov     ebx, 80070426h
0x1800161c2  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800161c9  jz      short loc_180016201
0x1800161cb  mov     rcx, cs:g_pDebug
0x1800161d2  lea     rax, aFailedToContro; "Failed to control the Ftp Site %d\n"
0x1800161d9  mov     [rsp+78h+var_48], r14d
0x1800161de  lea     r9, aFtpControlApiC; "FTP_CONTROL_API::ControlSite"
0x1800161e5  mov     [rsp+78h+var_50], rax
0x1800161ea  lea     rdx, aInetsrvIisIisr_13; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x1800161f1  mov     r8d, 10Ah
0x1800161f7  mov     [rsp+78h+var_58], ebx
0x1800161fb  call    cs:__imp_PuDbgPrintError
0x180016201  mov     rdi, [rsp+78h+Block]
0x180016209  test    rdi, rdi
0x18001620c  jz      short loc_180016233
0x18001620e  or      eax, 0FFFFFFFFh
0x180016211  lock xadd [rdi+0B0h], eax
0x180016219  cmp     eax, 1
0x18001621c  jnz     short loc_180016233
0x18001621e  test    rdi, rdi
0x180016221  jz      short loc_180016233
0x180016223  mov     rcx, rdi; this
0x180016226  call    ??1FTP_SITE@@AEAA@XZ; FTP_SITE::~FTP_SITE(void)
0x18001622b  mov     rcx, rdi; Block
0x18001622e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016233  test    ebp, ebp
0x180016235  jz      short loc_18001623B
0x180016237  lock dec dword ptr [rsi+18h]
0x18001623b  lea     rcx, [rsi+10h]
0x18001623f  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180016245  mov     eax, ebx
0x180016247  add     rsp, 48h
0x18001624b  pop     r15
0x18001624d  pop     r14
0x18001624f  pop     rdi
0x180016250  pop     rsi
0x180016251  pop     rbp
0x180016252  pop     rbx
0x180016253  retn
```
