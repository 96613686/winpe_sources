# CMDCOM::Restore(char *,STRAU *,STRAU *,char *,int)

- ea: `0x18001a584`
- end: `0x18001a933`
- name: `?Restore@CMDCOM@@AEAAJPEADPEAVSTRAU@@10H@Z`
- size: `943`
- prototype: `__int64 __fastcall(CMDCOM *this, char *, struct STRAU *, struct STRAU *, char *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180019454`
- `0x180019560`

## callees

- `0x18001a308`
- `0x18001a584`
- `0x18001a9b0`
- `0x18001fa58`
- `0x1800232cc`
- `0x180026cb8`
- `0x18003099a`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `KERNEL32!FindFirstFileA` at `0x18001a646`
- `KERNEL32!FindFirstFileA` at `0x18001a646`
- `KERNEL32!WaitForSingleObject` at `0x18001a605`
- `KERNEL32!WaitForSingleObject` at `0x18001a605`
- `KERNEL32!Sleep` at `0x18001a5de`
- `KERNEL32!Sleep` at `0x18001a5de`
- `KERNEL32!FindClose` at `0x18001a751`
- `KERNEL32!FindClose` at `0x18001a751`
- `KERNEL32!ReleaseSemaphore` at `0x18001a6c6`
- `KERNEL32!ReleaseSemaphore` at `0x18001a6c6`
- `KERNEL32!GetLastError` at `0x18001a65f`
- `KERNEL32!GetLastError` at `0x18001a65f`
- `IisRTL!??1STR@@QEAA@XZ` at `0x18001a6b3`
- `IisRTL!??1STR@@QEAA@XZ` at `0x18001a6b3`
- `IisRTL!??0STR@@QEAA@AEBV0@@Z` at `0x18001a62c`
- `IisRTL!??0STR@@QEAA@AEBV0@@Z` at `0x18001a62c`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x18001a845`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x18001a845`
- `IisRTL!?QueryStrA@STRAU@@QEAAPEADXZ` at `0x18001a635`
- `IisRTL!?QueryStrA@STRAU@@QEAAPEADXZ` at `0x18001a635`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x18001a7b8`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x18001a7c6`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x18001a853`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x18001a7b8`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x18001a7c6`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x18001a853`
- `IisRTL!PuDbgPrint` at `0x18001a6a1`
- `IisRTL!PuDbgPrint` at `0x18001a738`
- `IisRTL!PuDbgPrint` at `0x18001a82e`
- `IisRTL!PuDbgPrint` at `0x18001a907`
- `IisRTL!PuDbgPrint` at `0x18001a6a1`
- `IisRTL!PuDbgPrint` at `0x18001a738`
- `IisRTL!PuDbgPrint` at `0x18001a82e`
- `IisRTL!PuDbgPrint` at `0x18001a907`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001a889`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001a889`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001a75e`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001a75e`

## string_xrefs

- `0x18001a68f`: `inetsrv\iis\mb\metadata\comobj.cxx`
- `0x18001a726`: `inetsrv\iis\mb\metadata\comobj.cxx`
- `0x18001a81c`: `inetsrv\iis\mb\metadata\comobj.cxx`
- `0x18001a900`: `inetsrv\iis\mb\metadata\comobj.cxx`
- `0x18001a684`: `CMDCOM::Restore`
- `0x18001a71b`: `CMDCOM::Restore`
- `0x18001a811`: `CMDCOM::Restore`
- `0x18001a8ee`: `CMDCOM::Restore`
- `0x18001a6a7`: `[CMDCOM::Restore] InitWorker returned hr=0x%x\n`
- `0x18001a801`: `[CMDCOM::Restore] InitWorker returned hr=0x%x\n`
- `0x18001a867`: `[CMDCOM::Restore] InitWorker returned hr=0x%x\n`

## pseudocode

```c
__int64 __fastcall CMDCOM::Restore(CMDCOM *this, char *a2, struct STRAU *a3, struct STRAU *a4, char *a5, int a6)
{
  int i; // ebx
  const CHAR *StrA; // rax
  HANDLE FirstFileA; // rax
  volatile unsigned int v13; // ebp
  signed int LastError; // eax
  int inited; // edi
  int v16; // ebx
  int v17; // ebx
  char *Str; // rbx
  char *v19; // rax
  char *v20; // rbx
  char *v21; // rax
  unsigned int v23; // [rsp+30h] [rbp-1E8h]
  _BYTE v24[56]; // [rsp+48h] [rbp-1D0h] BYREF
  struct _WIN32_FIND_DATAA FindFileData; // [rsp+80h] [rbp-198h] BYREF

  CMDCOM::SendShutdownNotifications(this);
  for ( i = 0; _InterlockedIncrement((volatile signed __int32 *)this + 12) > 3 && i < 7; ++i )
  {
    _InterlockedDecrement((volatile signed __int32 *)this + 12);
    Sleep(0x3E8u);
  }
  _InterlockedDecrement((volatile signed __int32 *)this + 12);
  WaitForSingleObject(g_hReadSaveSemaphore, 0xFFFFFFFF);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  STR::STR((STR *)v24, g_strRealFileName);
  StrA = STRAU::QueryStrA(a3);
  FirstFileA = FindFirstFileA(StrA, &FindFileData);
  if ( FirstFileA == (HANDLE)-1LL )
  {
    v13 = 0;
    LastError = GetLastError();
    inited = LastError;
    if ( LastError > 0 )
      inited = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\metadata\\comobj.cxx", 5459, "CMDCOM::Restore", "hr=0x%x\n", inited);
  }
  else
  {
    inited = 0;
    FindClose(FirstFileA);
    CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&g_LockMasterResource);
    v13 = 0;
    v17 = g_bSaveDisallowed;
    g_bSaveDisallowed = 1;
    if ( g_dwInitialized )
    {
      v13 = g_dwInitialized;
      while ( g_dwInitialized )
        TerminateWorker1(1);
    }
    g_bSaveDisallowed = v17;
    while ( g_dwInitialized < v13 )
    {
      Str = STRAU::QueryStr(a4, 0);
      v19 = STRAU::QueryStr(a3, 0);
      inited = InitWorker(1, a5, v19, Str, a6);
      if ( (inited & 0x1FFF0000) == 0x210000 )
      {
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\mb\\metadata\\comobj.cxx",
            5501,
            "CMDCOM::Restore",
            "[CMDCOM::Restore] InitWorker returned hr=0x%x\n",
            inited);
        inited = -2146645991;
        goto LABEL_32;
      }
      if ( inited < 0 )
        goto LABEL_32;
    }
    if ( a2 )
    {
      v20 = STR::QueryStr((STR *)v24);
      v21 = STRAU::QueryStr(a3, 0);
      RestoreCertificates((const unsigned __int16 *)a2, v21, v20);
    }
LABEL_32:
    ++*(_DWORD *)&g_dwSystemChangeNumber;
    ++g_dwSchemaChangeNumber;
    CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
    if ( inited >= 0 )
      CMDCOM::NotifySinks(this, 0, 0, 0, 1, 2u, v23);
  }
  STR::~STR((STR *)v24);
  ReleaseSemaphore(g_hReadSaveSemaphore, 1, 0);
  if ( inited >= 0 )
  {
    inited = (*(__int64 (__fastcall **)(CMDCOM *, _QWORD))(*(_QWORD *)this + 304LL))(this, 0);
  }
  else
  {
    do
    {
      if ( g_dwInitialized >= v13 )
        break;
      v16 = InitWorker(0, 0, 0, 0, 0);
      if ( (inited & 0x1FFF0000) == 0x210000 )
      {
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\mb\\metadata\\comobj.cxx",
            5551,
            "CMDCOM::Restore",
            "[CMDCOM::Restore] InitWorker returned hr=0x%x\n",
            inited);
        inited = -2146645991;
      }
    }
    while ( v16 >= 0 );
  }
  if ( inited < 0 && (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\metadata\\comobj.cxx", 5566, "CMDCOM::Restore", "hr=0x%x\n", inited);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18001a584  push    rbx
0x18001a586  push    rbp
0x18001a587  push    rsi
0x18001a588  push    rdi
0x18001a589  push    r12
0x18001a58b  push    r13
0x18001a58d  push    r14
0x18001a58f  push    r15
0x18001a591  sub     rsp, 1D8h
0x18001a598  mov     rax, cs:__security_cookie
0x18001a59f  xor     rax, rsp
0x18001a5a2  mov     [rsp+218h+var_58], rax
0x18001a5aa  mov     rax, [rsp+218h+arg_20]
0x18001a5b2  mov     r13, r9
0x18001a5b5  mov     [rsp+218h+var_1D8], rax
0x18001a5ba  mov     r12, r8
0x18001a5bd  mov     r15, rdx
0x18001a5c0  mov     rsi, rcx
0x18001a5c3  call    ?SendShutdownNotifications@CMDCOM@@AEAAXXZ; CMDCOM::SendShutdownNotifications(void)
0x18001a5c8  xor     ebx, ebx
0x18001a5ca  lea     r14d, [rbx+1]
0x18001a5ce  jmp     short loc_18001A5E7
0x18001a5d0  cmp     ebx, 7
0x18001a5d3  jge     short loc_18001A5F7
0x18001a5d5  lock dec dword ptr [rsi+30h]
0x18001a5d9  mov     ecx, 3E8h; dwMilliseconds
0x18001a5de  call    cs:__imp_Sleep
0x18001a5e4  add     ebx, r14d
0x18001a5e7  mov     eax, r14d
0x18001a5ea  lock xadd [rsi+30h], eax
0x18001a5ef  add     eax, r14d
0x18001a5f2  cmp     eax, 3
0x18001a5f5  jg      short loc_18001A5D0
0x18001a5f7  lock dec dword ptr [rsi+30h]
0x18001a5fb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001a5fe  mov     rcx, cs:?g_hReadSaveSemaphore@@3PEAXEA; hHandle
0x18001a605  call    cs:__imp_WaitForSingleObject
0x18001a60b  xor     edx, edx; Val
0x18001a60d  lea     rcx, [rsp+218h+FindFileData]; void *
0x18001a615  mov     r8d, 140h; Size
0x18001a61b  call    memset_0
0x18001a620  mov     rdx, cs:?g_strRealFileName@@3PEAVSTR@@EA; STR * g_strRealFileName
0x18001a627  lea     rcx, [rsp+218h+var_1D0]
0x18001a62c  call    cs:__imp_??0STR@@QEAA@AEBV0@@Z; STR::STR(STR const &)
0x18001a632  mov     rcx, r12
0x18001a635  call    cs:__imp_?QueryStrA@STRAU@@QEAAPEADXZ; STRAU::QueryStrA(void)
0x18001a63b  mov     rcx, rax; lpFileName
0x18001a63e  lea     rdx, [rsp+218h+FindFileData]; lpFindFileData
0x18001a646  call    cs:__imp_FindFirstFileA
0x18001a64c  lea     rbx, aHr0xX; "hr=0x%x\n"
0x18001a653  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001a657  jnz     loc_18001A74C
0x18001a65d  xor     ebp, ebp
0x18001a65f  call    cs:__imp_GetLastError
0x18001a665  mov     edi, eax
0x18001a667  test    eax, eax
0x18001a669  jle     short loc_18001A674
0x18001a66b  movzx   edi, ax
0x18001a66e  or      edi, 80070000h
0x18001a674  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001a67b  jz      short loc_18001A6A7
0x18001a67d  mov     rcx, cs:g_pDebug
0x18001a684  lea     r9, aCmdcomRestore; "CMDCOM::Restore"
0x18001a68b  mov     [rsp+218h+var_1F0], edi
0x18001a68f  lea     rdx, aInetsrvIisMbMe_2; "inetsrv\\iis\\mb\\metadata\\comobj.cxx"
0x18001a696  mov     r8d, 1553h
0x18001a69c  mov     qword ptr [rsp+218h+var_1F8], rbx
0x18001a6a1  call    cs:__imp_PuDbgPrint
0x18001a6a7  lea     r15, aCmdcomRestoreI; "[CMDCOM::Restore] InitWorker returned h"...
0x18001a6ae  lea     rcx, [rsp+218h+var_1D0]
0x18001a6b3  call    cs:__imp_??1STR@@QEAA@XZ; STR::~STR(void)
0x18001a6b9  mov     rcx, cs:?g_hReadSaveSemaphore@@3PEAXEA; hSemaphore
0x18001a6c0  xor     r8d, r8d; lpPreviousCount
0x18001a6c3  mov     edx, r14d; lReleaseCount
0x18001a6c6  call    cs:__imp_ReleaseSemaphore
0x18001a6cc  test    edi, edi
0x18001a6ce  jns     loc_18001A8B9
0x18001a6d4  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x18001a6da  cmp     eax, ebp
0x18001a6dc  jnb     loc_18001A8CF
0x18001a6e2  xor     r9d, r9d; char *
0x18001a6e5  mov     [rsp+218h+var_1F8], 0; int
0x18001a6ed  xor     r8d, r8d; char *
0x18001a6f0  xor     edx, edx; char *
0x18001a6f2  xor     ecx, ecx; int
0x18001a6f4  call    ?InitWorker@@YAJHPEAD00H@Z; InitWorker(int,char *,char *,char *,int)
0x18001a6f9  mov     ecx, edi
0x18001a6fb  mov     ebx, eax
0x18001a6fd  and     ecx, 1FFF0000h
0x18001a703  cmp     ecx, 210000h
0x18001a709  jnz     short loc_18001A743
0x18001a70b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001a712  jz      short loc_18001A73E
0x18001a714  mov     rcx, cs:g_pDebug
0x18001a71b  lea     r9, aCmdcomRestore; "CMDCOM::Restore"
0x18001a722  mov     [rsp+218h+var_1F0], edi
0x18001a726  lea     rdx, aInetsrvIisMbMe_2; "inetsrv\\iis\\mb\\metadata\\comobj.cxx"
0x18001a72d  mov     r8d, 15AFh
0x18001a733  mov     qword ptr [rsp+218h+var_1F8], r15
0x18001a738  call    cs:__imp_PuDbgPrint
0x18001a73e  mov     edi, 800CC819h
0x18001a743  test    ebx, ebx
0x18001a745  jns     short loc_18001A6D4
0x18001a747  jmp     loc_18001A8CF
0x18001a74c  mov     rcx, rax; hFindFile
0x18001a74f  xor     edi, edi
0x18001a751  call    cs:__imp_FindClose
0x18001a757  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x18001a75e  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18001a764  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x18001a76a  xor     ebp, ebp
0x18001a76c  mov     ebx, cs:?g_bSaveDisallowed@@3HA; int g_bSaveDisallowed
0x18001a772  mov     cs:?g_bSaveDisallowed@@3HA, r14d; int g_bSaveDisallowed
0x18001a779  test    eax, eax
0x18001a77b  jz      short loc_18001A797
0x18001a77d  mov     ebp, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x18001a783  jmp     short loc_18001A78D
0x18001a785  mov     ecx, r14d; int
0x18001a788  call    ?TerminateWorker1@@YAJH@Z; TerminateWorker1(int)
0x18001a78d  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x18001a793  test    eax, eax
0x18001a795  jnz     short loc_18001A785
0x18001a797  mov     r14d, [rsp+218h+arg_28]
0x18001a79f  mov     cs:?g_bSaveDisallowed@@3HA, ebx; int g_bSaveDisallowed
0x18001a7a5  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x18001a7ab  cmp     eax, ebp
0x18001a7ad  jnb     loc_18001A83B
0x18001a7b3  xor     edx, edx
0x18001a7b5  mov     rcx, r13
0x18001a7b8  call    cs:__imp_?QueryStr@STRAU@@QEAAPEADH@Z; STRAU::QueryStr(int)
0x18001a7be  xor     edx, edx
0x18001a7c0  mov     rcx, r12
0x18001a7c3  mov     rbx, rax
0x18001a7c6  call    cs:__imp_?QueryStr@STRAU@@QEAAPEADH@Z; STRAU::QueryStr(int)
0x18001a7cc  mov     rdx, [rsp+218h+var_1D8]; char *
0x18001a7d1  mov     r9, rbx; char *
0x18001a7d4  mov     r8, rax; char *
0x18001a7d7  mov     [rsp+218h+var_1F8], r14d; int
0x18001a7dc  mov     ecx, 1; int
0x18001a7e1  call    ?InitWorker@@YAJHPEAD00H@Z; InitWorker(int,char *,char *,char *,int)
0x18001a7e6  mov     edi, eax
0x18001a7e8  and     eax, 1FFF0000h
0x18001a7ed  cmp     eax, 210000h
0x18001a7f2  jz      short loc_18001A7FA
0x18001a7f4  test    edi, edi
0x18001a7f6  jns     short loc_18001A7A5
0x18001a7f8  jmp     short loc_18001A867
0x18001a7fa  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001a801  lea     r15, aCmdcomRestoreI; "[CMDCOM::Restore] InitWorker returned h"...
0x18001a808  jz      short loc_18001A834
0x18001a80a  mov     rcx, cs:g_pDebug
0x18001a811  lea     r9, aCmdcomRestore; "CMDCOM::Restore"
0x18001a818  mov     [rsp+218h+var_1F0], edi
0x18001a81c  lea     rdx, aInetsrvIisMbMe_2; "inetsrv\\iis\\mb\\metadata\\comobj.cxx"
0x18001a823  mov     r8d, 157Dh
0x18001a829  mov     qword ptr [rsp+218h+var_1F8], r15
0x18001a82e  call    cs:__imp_PuDbgPrint
0x18001a834  mov     edi, 800CC819h
0x18001a839  jmp     short loc_18001A86E
0x18001a83b  test    r15, r15
0x18001a83e  jz      short loc_18001A867
0x18001a840  lea     rcx, [rsp+218h+var_1D0]
0x18001a845  call    cs:__imp_?QueryStr@STR@@QEBAPEADXZ; STR::QueryStr(void)
0x18001a84b  xor     edx, edx
0x18001a84d  mov     rcx, r12
0x18001a850  mov     rbx, rax
0x18001a853  call    cs:__imp_?QueryStr@STRAU@@QEAAPEADH@Z; STRAU::QueryStr(int)
0x18001a859  mov     r8, rbx; char *
0x18001a85c  mov     rcx, r15; unsigned __int16 *
0x18001a85f  mov     rdx, rax; char *
0x18001a862  call    ?RestoreCertificates@@YAJPEBGPEAD1@Z; RestoreCertificates(ushort const *,char *,char *)
0x18001a867  lea     r15, aCmdcomRestoreI; "[CMDCOM::Restore] InitWorker returned h"...
0x18001a86e  mov     r14d, 1
0x18001a874  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x18001a87b  add     cs:?g_dwSystemChangeNumber@@3KA, r14d; ulong g_dwSystemChangeNumber
0x18001a882  add     cs:?g_dwSchemaChangeNumber@@3KA, r14d; ulong g_dwSchemaChangeNumber
0x18001a889  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18001a88f  test    edi, edi
0x18001a891  js      loc_18001A6AE
0x18001a897  mov     [rsp+218h+var_1F0], 2; unsigned int
0x18001a89f  xor     r9d, r9d; unsigned int
0x18001a8a2  xor     r8d, r8d; struct _MD_CHANGE_OBJECT_A *
0x18001a8a5  mov     [rsp+218h+var_1F8], r14d; int
0x18001a8aa  xor     edx, edx; unsigned int
0x18001a8ac  mov     rcx, rsi; this
0x18001a8af  call    ?NotifySinks@CMDCOM@@AEAAJKPEAU_MD_CHANGE_OBJECT_A@@KHKK@Z; CMDCOM::NotifySinks(ulong,_MD_CHANGE_OBJECT_A *,ulong,int,ulong,ulong)
0x18001a8b4  jmp     loc_18001A6AE
0x18001a8b9  mov     rax, [rsi]
0x18001a8bc  xor     edx, edx
0x18001a8be  mov     rcx, rsi
0x18001a8c1  mov     rax, [rax+130h]
0x18001a8c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8cd  mov     edi, eax
0x18001a8cf  test    edi, edi
0x18001a8d1  jns     short loc_18001A90D
0x18001a8d3  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001a8da  jz      short loc_18001A90D
0x18001a8dc  mov     rcx, cs:g_pDebug
0x18001a8e3  lea     rax, aHr0xX; "hr=0x%x\n"
0x18001a8ea  mov     [rsp+218h+var_1F0], edi
0x18001a8ee  lea     r9, aCmdcomRestore; "CMDCOM::Restore"
0x18001a8f5  mov     r8d, 15BEh
0x18001a8fb  mov     qword ptr [rsp+218h+var_1F8], rax
0x18001a900  lea     rdx, aInetsrvIisMbMe_2; "inetsrv\\iis\\mb\\metadata\\comobj.cxx"
0x18001a907  call    cs:__imp_PuDbgPrint
0x18001a90d  mov     eax, edi
0x18001a90f  mov     rcx, [rsp+218h+var_58]
0x18001a917  xor     rcx, rsp; StackCookie
0x18001a91a  call    __security_check_cookie
0x18001a91f  add     rsp, 1D8h
0x18001a926  pop     r15
0x18001a928  pop     r14
0x18001a92a  pop     r13
0x18001a92c  pop     r12
0x18001a92e  pop     rdi
0x18001a92f  pop     rsi
0x18001a930  pop     rbp
0x18001a931  pop     rbx
0x18001a932  retn
```
