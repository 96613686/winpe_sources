# CFileListener::ProcessChanges(void)

- ea: `0x18000d374`
- end: `0x18000d678`
- name: `?ProcessChanges@CFileListener@@AEAAJXZ`
- size: `772`
- prototype: `__int64 __fastcall(LPCWSTR *this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1800085e0`

## callees

- `0x180008a08`
- `0x180009bd0`
- `0x18000a638`
- `0x18000aff8`
- `0x18000b3a0`
- `0x18000d374`
- `0x18000d680`
- `0x18000e104`
- `0x18003099a`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `KERNEL32!ReleaseSemaphore` at `0x18000d56a`
- `KERNEL32!ReleaseSemaphore` at `0x18000d56a`
- `KERNEL32!DeleteFileW` at `0x18000d522`
- `KERNEL32!DeleteFileW` at `0x18000d538`
- `KERNEL32!DeleteFileW` at `0x18000d551`
- `KERNEL32!DeleteFileW` at `0x18000d522`
- `KERNEL32!DeleteFileW` at `0x18000d538`
- `KERNEL32!DeleteFileW` at `0x18000d551`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x18000d64d`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x18000d64d`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d595`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d595`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d582`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d582`
- `IisRTL!??0STRU@@QEAA@PEAGK@Z` at `0x18000d3c4`
- `IisRTL!??0STRU@@QEAA@PEAGK@Z` at `0x18000d3c4`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d49e`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d548`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d49e`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d548`
- `IisRTL!PuDbgPrintW` at `0x18000d642`
- `IisRTL!PuDbgPrintW` at `0x18000d642`

## pseudocode

```c
__int64 __fastcall CFileListener::ProcessChanges(LPCWSTR *this)
{
  int v2; // ebx
  unsigned int v3; // r15d
  int v4; // r12d
  struct IIS_CRYPTO_STORAGE *v5; // rsi
  void *v6; // r14
  int v7; // r13d
  int HistoryFile; // eax
  unsigned int v9; // edx
  unsigned __int16 *Str; // rax
  const WCHAR *v11; // rax
  int v12; // esi
  struct IIS_CRYPTO_STORAGE **v14; // [rsp+28h] [rbp-D8h]
  int v15; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v16; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v17; // [rsp+48h] [rbp-B8h] BYREF
  int v18; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v19; // [rsp+50h] [rbp-B0h] BYREF
  IIS_CRYPTO_STORAGE *v20; // [rsp+58h] [rbp-A8h] BYREF
  void *Block; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v22[56]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v23[264]; // [rsp+A0h] [rbp-60h] BYREF

  memset_0(v23, 0, 0x208u);
  STRU::STRU((STRU *)v22, v23, 0x104u);
  v2 = 0;
  v16 = 0;
  v3 = 0;
  v19 = 0;
  v4 = 0;
  v15 = 0;
  v5 = 0;
  v18 = 0;
  v6 = 0;
  v17 = 0;
  v7 = 0;
  v20 = 0;
  Block = 0;
  if ( !(unsigned int)CFileListener::ProgrammaticMetabaseSaveNotification((CFileListener *)this) )
  {
    if ( dword_18004875C )
    {
      if ( dword_18004875C != 1 )
      {
        v2 = -2147418113;
LABEL_17:
        CFileListener::CopyErrorFile((CFileListener *)this, v2);
        goto LABEL_18;
      }
      HistoryFile = CFileListener::GetInMemoryFile(
                      (CFileListener *)this,
                      (struct STRU *)v22,
                      &v16,
                      &v18,
                      &v15,
                      &v20,
                      (struct _IIS_CRYPTO_BLOB **)&Block);
      v4 = v18;
      v7 = 1;
      v5 = v20;
      v6 = Block;
    }
    else
    {
      HistoryFile = CFileListener::GetHistoryFile((CFileListener *)this, (struct STRU *)v22, &v16, &v19, &v15);
      v3 = v19;
    }
    v2 = HistoryFile;
    if ( HistoryFile >= 0 )
    {
      Str = STRU::QueryStr((STRU *)v22);
      v2 = CFileListener::ProcessChangesFromFile((CFileListener *)this, Str, v16, v3, &v15, v5);
      if ( v2 >= 0 )
      {
        if ( !dword_180048764
          || (v2 = (*(__int64 (__fastcall **)(LPCWSTR))(*(_QWORD *)this[71] + 528LL))(this[71]), v2 >= 0) )
        {
          v2 = 0;
        }
      }
    }
    if ( v6 )
      operator delete(v6);
    if ( v5 )
      IIS_CRYPTO_STORAGE::`scalar deleting destructor'(v5, v9);
    if ( v2 < 0 )
      goto LABEL_17;
  }
LABEL_18:
  DeleteFileW(this[27]);
  if ( *((_DWORD *)this + 138) )
    DeleteFileW(this[29]);
  if ( v7 )
  {
    v11 = STRU::QueryStr((STRU *)v22);
    DeleteFileW(v11);
  }
  if ( v4 )
    ReleaseSemaphore(g_hReadSaveSemaphore, 1, 0);
  if ( v15 )
  {
    CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&g_LockMasterResource);
    ++*(_DWORD *)&g_dwSystemChangeNumber;
    CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
    v12 = (*(__int64 (__fastcall **)(LPCWSTR, _QWORD, _QWORD, __int64, int, unsigned int *))(*(_QWORD *)this[71] + 280LL))(
            this[71],
            0,
            0,
            1,
            100,
            &v17);
    if ( v12 < 0
      || (v12 = (*(__int64 (__fastcall **)(LPCWSTR, _QWORD))(*(_QWORD *)this[71] + 304LL))(this[71], v17),
          (*(void (__fastcall **)(LPCWSTR, _QWORD))(*(_QWORD *)this[71] + 288LL))(this[71], v17),
          v12 < 0) )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        LODWORD(v14) = v12;
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\listener.cpp",
          1386,
          "CFileListener::ProcessChanges",
          L"[CFileListener::ProcessChanges] SaveData failed with hr = 0x%x\n",
          v14);
      }
    }
  }
  STRU::~STRU((STRU *)v22);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000d374  push    rbp
0x18000d376  push    rbx
0x18000d377  push    rsi
0x18000d378  push    rdi
0x18000d379  push    r12
0x18000d37b  push    r13
0x18000d37d  push    r14
0x18000d37f  push    r15
0x18000d381  lea     rbp, [rsp-1C8h]
0x18000d389  sub     rsp, 2C8h
0x18000d390  mov     rax, cs:__security_cookie
0x18000d397  xor     rax, rsp
0x18000d39a  mov     [rbp+200h+var_50], rax
0x18000d3a1  mov     rdi, rcx
0x18000d3a4  xor     edx, edx; Val
0x18000d3a6  lea     rcx, [rbp+200h+var_260]; void *
0x18000d3aa  mov     r8d, 208h; Size
0x18000d3b0  call    memset_0
0x18000d3b5  mov     r8d, 104h
0x18000d3bb  lea     rdx, [rbp+200h+var_260]
0x18000d3bf  lea     rcx, [rsp+300h+var_298]
0x18000d3c4  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000d3ca  xor     ebx, ebx
0x18000d3cc  mov     rcx, rdi; this
0x18000d3cf  mov     [rsp+300h+var_2BC], ebx
0x18000d3d3  mov     r15d, ebx
0x18000d3d6  mov     [rsp+300h+var_2B0], ebx
0x18000d3da  mov     r12d, ebx
0x18000d3dd  mov     [rsp+300h+var_2C0], ebx
0x18000d3e1  mov     esi, ebx
0x18000d3e3  mov     [rsp+300h+var_2B4], ebx
0x18000d3e7  mov     r14d, ebx
0x18000d3ea  mov     [rsp+300h+var_2B8], ebx
0x18000d3ee  mov     r13d, ebx
0x18000d3f1  mov     [rsp+300h+var_2A8], rbx
0x18000d3f6  mov     [rsp+300h+Block], rbx
0x18000d3fb  call    ?ProgrammaticMetabaseSaveNotification@CFileListener@@AEAAHXZ; CFileListener::ProgrammaticMetabaseSaveNotification(void)
0x18000d400  test    eax, eax
0x18000d402  jnz     loc_18000D51B
0x18000d408  mov     ecx, cs:dword_18004875C
0x18000d40e  test    ecx, ecx
0x18000d410  jz      short loc_18000D46D
0x18000d412  cmp     ecx, 1
0x18000d415  jz      short loc_18000D421
0x18000d417  mov     ebx, 8000FFFFh
0x18000d41c  jmp     loc_18000D511
0x18000d421  lea     rax, [rsp+300h+Block]
0x18000d426  mov     rcx, rdi; this
0x18000d429  mov     [rsp+300h+var_2D0], rax; struct _IIS_CRYPTO_BLOB **
0x18000d42e  lea     r9, [rsp+300h+var_2B4]; int *
0x18000d433  lea     rax, [rsp+300h+var_2A8]
0x18000d438  mov     [rsp+300h+var_2D8], rax; struct IIS_CRYPTO_STORAGE **
0x18000d43d  lea     r8, [rsp+300h+var_2BC]; unsigned int *
0x18000d442  lea     rax, [rsp+300h+var_2C0]
0x18000d447  lea     rdx, [rsp+300h+var_298]; struct STRU *
0x18000d44c  mov     [rsp+300h+var_2E0], rax; int *
0x18000d451  call    ?GetInMemoryFile@CFileListener@@AEAAJPEAVSTRU@@PEAKPEAH2PEAPEAVIIS_CRYPTO_STORAGE@@PEAPEFAU_IIS_CRYPTO_BLOB@@@Z; CFileListener::GetInMemoryFile(STRU *,ulong *,int *,int *,IIS_CRYPTO_STORAGE * *,_IIS_CRYPTO_BLOB * *)
0x18000d456  mov     r12d, [rsp+300h+var_2B4]
0x18000d45b  mov     r13d, 1
0x18000d461  mov     rsi, [rsp+300h+var_2A8]
0x18000d466  mov     r14, [rsp+300h+Block]
0x18000d46b  jmp     short loc_18000D493
0x18000d46d  lea     rax, [rsp+300h+var_2C0]
0x18000d472  mov     rcx, rdi; this
0x18000d475  lea     r9, [rsp+300h+var_2B0]; unsigned int *
0x18000d47a  mov     [rsp+300h+var_2E0], rax; int *
0x18000d47f  lea     r8, [rsp+300h+var_2BC]; unsigned int *
0x18000d484  lea     rdx, [rsp+300h+var_298]; struct STRU *
0x18000d489  call    ?GetHistoryFile@CFileListener@@AEAAJPEAVSTRU@@PEAK1PEAH@Z; CFileListener::GetHistoryFile(STRU *,ulong *,ulong *,int *)
0x18000d48e  mov     r15d, [rsp+300h+var_2B0]
0x18000d493  mov     ebx, eax
0x18000d495  test    eax, eax
0x18000d497  js      short loc_18000D4F3
0x18000d499  lea     rcx, [rsp+300h+var_298]
0x18000d49e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000d4a4  mov     r8d, [rsp+300h+var_2BC]; unsigned int
0x18000d4a9  lea     rcx, [rsp+300h+var_2C0]
0x18000d4ae  mov     [rsp+300h+var_2D8], rsi; struct IIS_CRYPTO_STORAGE *
0x18000d4b3  mov     r9d, r15d; unsigned int
0x18000d4b6  mov     [rsp+300h+var_2E0], rcx; int *
0x18000d4bb  mov     rdx, rax; unsigned __int16 *
0x18000d4be  mov     rcx, rdi; this
0x18000d4c1  call    ?ProcessChangesFromFile@CFileListener@@AEAAJPEAGKKPEAHPEAVIIS_CRYPTO_STORAGE@@@Z; CFileListener::ProcessChangesFromFile(ushort *,ulong,ulong,int *,IIS_CRYPTO_STORAGE *)
0x18000d4c6  mov     ebx, eax
0x18000d4c8  test    eax, eax
0x18000d4ca  js      short loc_18000D4F3
0x18000d4cc  cmp     cs:dword_180048764, 0
0x18000d4d3  jz      short loc_18000D4F1
0x18000d4d5  mov     rcx, [rdi+238h]
0x18000d4dc  mov     rax, [rcx]
0x18000d4df  mov     rax, [rax+210h]
0x18000d4e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4eb  mov     ebx, eax
0x18000d4ed  test    eax, eax
0x18000d4ef  js      short loc_18000D4F3
0x18000d4f1  xor     ebx, ebx
0x18000d4f3  test    r14, r14
0x18000d4f6  jz      short loc_18000D500
0x18000d4f8  mov     rcx, r14; Block
0x18000d4fb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d500  test    rsi, rsi
0x18000d503  jz      short loc_18000D50D
0x18000d505  mov     rcx, rsi; this
0x18000d508  call    ??_GIIS_CRYPTO_STORAGE@@QEAAPEAXI@Z; IIS_CRYPTO_STORAGE::`scalar deleting destructor'(uint)
0x18000d50d  test    ebx, ebx
0x18000d50f  jns     short loc_18000D51B
0x18000d511  mov     edx, ebx; int
0x18000d513  mov     rcx, rdi; this
0x18000d516  call    ?CopyErrorFile@CFileListener@@AEAAJJ@Z; CFileListener::CopyErrorFile(long)
0x18000d51b  mov     rcx, [rdi+0D8h]; lpFileName
0x18000d522  call    cs:__imp_DeleteFileW
0x18000d528  cmp     dword ptr [rdi+228h], 0
0x18000d52f  jz      short loc_18000D53E
0x18000d531  mov     rcx, [rdi+0E8h]; lpFileName
0x18000d538  call    cs:__imp_DeleteFileW
0x18000d53e  test    r13d, r13d
0x18000d541  jz      short loc_18000D557
0x18000d543  lea     rcx, [rsp+300h+var_298]
0x18000d548  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000d54e  mov     rcx, rax; lpFileName
0x18000d551  call    cs:__imp_DeleteFileW
0x18000d557  test    r12d, r12d
0x18000d55a  jz      short loc_18000D570
0x18000d55c  mov     rcx, cs:?g_hReadSaveSemaphore@@3PEAXEA; hSemaphore
0x18000d563  xor     r8d, r8d; lpPreviousCount
0x18000d566  lea     edx, [r8+1]; lReleaseCount
0x18000d56a  call    cs:__imp_ReleaseSemaphore
0x18000d570  cmp     [rsp+300h+var_2C0], 0
0x18000d575  jz      loc_18000D648
0x18000d57b  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x18000d582  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000d588  inc     cs:?g_dwSystemChangeNumber@@3KA; ulong g_dwSystemChangeNumber
0x18000d58e  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x18000d595  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000d59b  mov     rcx, [rdi+238h]
0x18000d5a2  lea     rdx, [rsp+300h+var_2B8]
0x18000d5a7  mov     [rsp+300h+var_2D8], rdx
0x18000d5ac  mov     r9d, 1
0x18000d5b2  xor     r8d, r8d
0x18000d5b5  mov     dword ptr [rsp+300h+var_2E0], 64h ; 'd'
0x18000d5bd  xor     edx, edx
0x18000d5bf  mov     rax, [rcx]
0x18000d5c2  mov     rax, [rax+118h]
0x18000d5c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5ce  mov     esi, eax
0x18000d5d0  test    eax, eax
0x18000d5d2  js      short loc_18000D60E
0x18000d5d4  mov     rcx, [rdi+238h]
0x18000d5db  mov     edx, [rsp+300h+var_2B8]
0x18000d5df  mov     rax, [rcx]
0x18000d5e2  mov     rax, [rax+130h]
0x18000d5e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5ee  mov     rcx, [rdi+238h]
0x18000d5f5  mov     esi, eax
0x18000d5f7  mov     edx, [rsp+300h+var_2B8]
0x18000d5fb  mov     rax, [rcx]
0x18000d5fe  mov     rax, [rax+120h]
0x18000d605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d60a  test    esi, esi
0x18000d60c  jns     short loc_18000D648
0x18000d60e  test    byte ptr cs:g_dwDebugFlags, 3
0x18000d615  jz      short loc_18000D648
0x18000d617  mov     rcx, cs:g_pDebug
0x18000d61e  lea     rax, aCfilelistenerP_13; "[CFileListener::ProcessChanges] SaveDat"...
0x18000d625  mov     dword ptr [rsp+300h+var_2D8], esi
0x18000d629  lea     r9, aCfilelistenerP_17; "CFileListener::ProcessChanges"
0x18000d630  mov     r8d, 56Ah
0x18000d636  mov     [rsp+300h+var_2E0], rax
0x18000d63b  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000d642  call    cs:__imp_PuDbgPrintW
0x18000d648  lea     rcx, [rsp+300h+var_298]
0x18000d64d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000d653  mov     eax, ebx
0x18000d655  mov     rcx, [rbp+200h+var_50]
0x18000d65c  xor     rcx, rsp; StackCookie
0x18000d65f  call    __security_check_cookie
0x18000d664  add     rsp, 2C8h
0x18000d66b  pop     r15
0x18000d66d  pop     r14
0x18000d66f  pop     r13
0x18000d671  pop     r12
0x18000d673  pop     rdi
0x18000d674  pop     rsi
0x18000d675  pop     rbx
0x18000d676  pop     rbp
0x18000d677  retn
```
