# FTP_SITE_MANAGER::StartOrUpdateOneSite(ulong,ushort const *,IAppHostElement *,ulong)

- ea: `0x18000cfe0`
- end: `0x18000d3fa`
- name: `?StartOrUpdateOneSite@FTP_SITE_MANAGER@@AEAAXKPEBGPEAUIAppHostElement@@K@Z`
- size: `1050`
- prototype: `void __usercall(FTP_SITE_MANAGER *__hidden this@<rcx>, unsigned int@<edx>, const unsigned __int16 *@<r8>, struct IAppHostElement *@<r9>, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callers

- `0x18000cb74`

## callees

- `0x180001210`
- `0x180001250`
- `0x180008a8c`
- `0x180008f40`
- `0x180009090`
- `0x180009d2c`
- `0x18000aa00`
- `0x18000aab0`
- `0x18000ab1c`
- `0x18000ac28`
- `0x18000cfe0`
- `0x180045730`
- `0x180047050`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000d0b3`
- `msvcrt!_wcsicmp` at `0x18000d0b3`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d333`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d333`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d0cb`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d3d8`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d0cb`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d3d8`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d0f4`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d3ee`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d0f4`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d3ee`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000d3b6`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000d3b6`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18000d2eb`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18000d2eb`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x18000d100`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x18000d100`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000d08d`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000d08d`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d368`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d368`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18000d022`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18000d022`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x18000d02e`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x18000d02e`
- `iisutil!WriteRefTraceLog` at `0x18000d358`
- `iisutil!WriteRefTraceLog` at `0x18000d399`
- `iisutil!WriteRefTraceLog` at `0x18000d358`
- `iisutil!WriteRefTraceLog` at `0x18000d399`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18000d2b8`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18000d2b8`
- `iisutil!PuDbgPrintError` at `0x18000d1da`
- `iisutil!PuDbgPrintError` at `0x18000d22d`
- `iisutil!PuDbgPrintError` at `0x18000d28c`
- `iisutil!PuDbgPrintError` at `0x18000d1da`
- `iisutil!PuDbgPrintError` at `0x18000d22d`
- `iisutil!PuDbgPrintError` at `0x18000d28c`

## string_xrefs

- `0x18000d1c1`: `FTP_SITE_MANAGER::StartOrUpdateOneSite`
- `0x18000d212`: `FTP_SITE_MANAGER::StartOrUpdateOneSite`
- `0x18000d277`: `FTP_SITE_MANAGER::StartOrUpdateOneSite`
- `0x18000d180`: `Failed to update site %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall FTP_SITE_MANAGER::StartOrUpdateOneSite(
        FTP_SITE_MANAGER *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        struct IAppHostElement *a4,
        unsigned int a5)
{
  int Key; // eax
  FTP_SITE *v10; // rdi
  const wchar_t *v11; // rcx
  _QWORD *i; // rbx
  void *v13; // rax
  unsigned int v14; // ebx
  int v15; // esi
  const char *v16; // rax
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // rbp
  unsigned __int32 v20; // ebx
  void *Block; // [rsp+40h] [rbp-A8h] BYREF
  void **v22; // [rsp+50h] [rbp-98h] BYREF
  _BYTE v23[32]; // [rsp+58h] [rbp-90h] BYREF
  unsigned __int64 v24; // [rsp+78h] [rbp-70h]

  v22 = &FTP_BINDINGS_CONFIG::`vftable';
  MULTISZ::MULTISZ((MULTISZ *)v23);
  MULTISZ::Reset((MULTISZ *)v23);
  if ( FTP_BINDINGS_CONFIG::Initialize((FTP_BINDINGS_CONFIG *)&v22, a4) < 0
    || (-(__int64)(*(_WORD *)v24 != 0) & v24) == 0
    || !*(_WORD *)(v24 & -(__int64)(*(_WORD *)v24 != 0)) )
  {
    goto LABEL_31;
  }
  Block = 0;
  Key = CLKRHashTable::FindKey((char *)this + 8, a2, &Block);
  v10 = (FTP_SITE *)Block;
  if ( Key )
  {
    if ( Key == 2 )
      goto LABEL_13;
    v15 = Key != 0 ? 0x80004005 : 0;
    if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      v16 = "Failed the hash table lookup for site %d\n";
      v17 = 522;
      goto LABEL_21;
    }
LABEL_44:
    if ( !v10 )
      goto LABEL_31;
    if ( v15 < 0 )
    {
      CReaderWriterLock3::WriteLock((FTP_SITE *)((char *)v10 + 200));
      FTP_SITE::StopSiteNoLock(v10, v15, 0);
      CReaderWriterLock3::WriteUnlock((FTP_SITE *)((char *)v10 + 200));
    }
    goto LABEL_29;
  }
  v11 = (const wchar_t *)&dword_18004D454;
  if ( *((_QWORD *)Block + 1) )
    v11 = (const wchar_t *)*((_QWORD *)Block + 1);
  if ( !_wcsicmp(v11, a3) )
  {
    v14 = a5;
    v15 = FTP_SITE::Update(v10, a4, a5);
    if ( v15 >= 0 )
    {
LABEL_35:
      if ( !v14 )
      {
        CReaderWriterLock3::ReadLock((FTP_SITE *)((char *)v10 + 208));
        v18 = (unsigned int)_InterlockedIncrement(*((volatile signed __int32 **)v10 + 24));
        if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
          WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v18);
        v19 = *((_QWORD *)v10 + 24);
        CReaderWriterLock3::ReadUnlock((FTP_SITE *)((char *)v10 + 208));
        if ( *(_DWORD *)(v19 + 72) )
          FTP_SITE::StartSite(v10, 0);
        v20 = _InterlockedDecrement((volatile signed __int32 *)v19);
        if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
          WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v20);
        if ( !v20 )
        {
          FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v19);
          ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, (void *)v19);
        }
      }
      goto LABEL_44;
    }
    if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      v16 = "Failed to update site %d\n";
      v17 = 599;
LABEL_21:
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_site_manager.cxx",
        v17,
        "FTP_SITE_MANAGER::StartOrUpdateOneSite",
        v15,
        v16,
        a2);
      goto LABEL_44;
    }
    goto LABEL_44;
  }
  CReaderWriterLock3::WriteLock((FTP_SITE *)((char *)v10 + 200));
  for ( i = (_QWORD *)*((_QWORD *)v10 + 28); i != (_QWORD *)((char *)v10 + 224); i = (_QWORD *)*i )
    FTP_SITE_ENDPOINT_ENTRY::StopEndpoint((FTP_SITE_ENDPOINT_ENTRY *)(i - 25));
  CReaderWriterLock3::WriteUnlock((FTP_SITE *)((char *)v10 + 200));
  CLKRHashTable::DeleteRecord((char *)this + 8, v10);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10 + 44, 0xFFFFFFFF) == 1 )
  {
    FTP_SITE::~FTP_SITE(v10);
    operator delete(v10);
  }
LABEL_13:
  v13 = operator new(0x140u);
  Block = v13;
  if ( v13 )
    v10 = FTP_SITE::FTP_SITE((FTP_SITE *)v13, this);
  else
    v10 = 0;
  if ( !v10 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_site_manager.cxx",
        538,
        "FTP_SITE_MANAGER::StartOrUpdateOneSite",
        -2147024888,
        "Failed to allocate new site %d\n",
        a2);
    goto LABEL_31;
  }
  v14 = a5;
  v15 = FTP_SITE::Initialize(v10, a4, a5);
  if ( v15 >= 0 )
  {
    if ( (unsigned int)CLKRHashTable::InsertRecord((char *)this + 8, v10, 0) )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_site_manager.cxx",
          573,
          "FTP_SITE_MANAGER::StartOrUpdateOneSite",
          -2147467259,
          "Failed to add new site %d to the hash table\n",
          a2);
      goto LABEL_29;
    }
    goto LABEL_35;
  }
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_site_manager.cxx",
      550,
      "FTP_SITE_MANAGER::StartOrUpdateOneSite",
      v15,
      "Failed to initialize site %d\n",
      a2);
LABEL_29:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10 + 44, 0xFFFFFFFF) == 1 )
  {
    FTP_SITE::~FTP_SITE(v10);
    operator delete(v10);
  }
LABEL_31:
  MULTISZ::~MULTISZ((MULTISZ *)v23);
}

```

## disassembly

```asm
0x18000cfe0  push    rbx
0x18000cfe2  push    rbp
0x18000cfe3  push    rsi
0x18000cfe4  push    rdi
0x18000cfe5  push    r12
0x18000cfe7  push    r13
0x18000cfe9  push    r14
0x18000cfeb  push    r15
0x18000cfed  sub     rsp, 0A8h
0x18000cff4  mov     rax, cs:__security_cookie
0x18000cffb  xor     rax, rsp
0x18000cffe  mov     [rsp+0E8h+var_58], rax
0x18000d006  mov     r12, r9
0x18000d009  mov     rbx, r8
0x18000d00c  mov     ebp, edx
0x18000d00e  mov     r13, rcx
0x18000d011  lea     rax, ??_7FTP_BINDINGS_CONFIG@@6B@; const FTP_BINDINGS_CONFIG::`vftable'
0x18000d018  mov     [rsp+0E8h+var_98], rax
0x18000d01d  lea     rcx, [rsp+0E8h+var_90]
0x18000d022  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x18000d028  nop
0x18000d029  lea     rcx, [rsp+0E8h+var_90]
0x18000d02e  call    cs:__imp_?Reset@MULTISZ@@QEAAXXZ; MULTISZ::Reset(void)
0x18000d034  nop
0x18000d035  mov     rdx, r12; struct IAppHostElement *
0x18000d038  lea     rcx, [rsp+0E8h+var_98]; this
0x18000d03d  call    ?Initialize@FTP_BINDINGS_CONFIG@@UEAAJPEAUIAppHostElement@@@Z; FTP_BINDINGS_CONFIG::Initialize(IAppHostElement *)
0x18000d042  xor     r14d, r14d
0x18000d045  test    eax, eax
0x18000d047  js      loc_18000D2B3
0x18000d04d  mov     rdx, [rsp+0E8h+var_70]
0x18000d052  movzx   ecx, word ptr [rdx]
0x18000d055  movzx   eax, cx
0x18000d058  neg     ax
0x18000d05b  sbb     rax, rax
0x18000d05e  test    rdx, rax
0x18000d061  jz      loc_18000D2B3
0x18000d067  neg     cx
0x18000d06a  sbb     rax, rax
0x18000d06d  and     rax, rdx
0x18000d070  cmp     [rax], r14w
0x18000d074  jz      loc_18000D2B3
0x18000d07a  lea     r15, [r13+8]
0x18000d07e  mov     [rsp+0E8h+Block], r14
0x18000d083  mov     edx, ebp
0x18000d085  lea     r8, [rsp+0E8h+Block]
0x18000d08a  mov     rcx, r15
0x18000d08d  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x18000d093  mov     rdi, [rsp+0E8h+Block]
0x18000d098  test    eax, eax
0x18000d09a  jnz     loc_18000D18F
0x18000d0a0  lea     rcx, dword_18004D454
0x18000d0a7  cmp     [rdi+8], r14
0x18000d0ab  cmovnz  rcx, [rdi+8]; String1
0x18000d0b0  mov     rdx, rbx; String2
0x18000d0b3  call    cs:__imp__wcsicmp
0x18000d0b9  test    eax, eax
0x18000d0bb  jz      loc_18000D154
0x18000d0c1  lea     r14, [rdi+0C8h]
0x18000d0c8  mov     rcx, r14
0x18000d0cb  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000d0d1  lea     rsi, [rdi+0E0h]
0x18000d0d8  mov     rbx, [rsi]
0x18000d0db  jmp     short loc_18000D0EC
0x18000d0dd  lea     rcx, [rbx-0C8h]; this
0x18000d0e4  call    ?StopEndpoint@FTP_SITE_ENDPOINT_ENTRY@@QEAAXXZ; FTP_SITE_ENDPOINT_ENTRY::StopEndpoint(void)
0x18000d0e9  mov     rbx, [rbx]
0x18000d0ec  cmp     rbx, rsi
0x18000d0ef  jnz     short loc_18000D0DD
0x18000d0f1  mov     rcx, r14
0x18000d0f4  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000d0fa  mov     rdx, rdi
0x18000d0fd  mov     rcx, r15
0x18000d100  call    cs:__imp_?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z; CLKRHashTable::DeleteRecord(void const *)
0x18000d106  or      eax, 0FFFFFFFFh
0x18000d109  lock xadd [rdi+0B0h], eax
0x18000d111  cmp     eax, 1
0x18000d114  jnz     short loc_18000D126
0x18000d116  mov     rcx, rdi; this
0x18000d119  call    ??1FTP_SITE@@AEAA@XZ; FTP_SITE::~FTP_SITE(void)
0x18000d11e  mov     rcx, rdi; Block
0x18000d121  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d126  xor     r14d, r14d
0x18000d129  mov     ecx, 140h; Size
0x18000d12e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d133  mov     [rsp+0E8h+Block], rax
0x18000d138  test    rax, rax
0x18000d13b  jz      loc_18000D1E5
0x18000d141  mov     rdx, r13; struct FTP_SITE_MANAGER *
0x18000d144  mov     rcx, rax; this
0x18000d147  call    ??0FTP_SITE@@QEAA@PEAVFTP_SITE_MANAGER@@@Z; FTP_SITE::FTP_SITE(FTP_SITE_MANAGER *)
0x18000d14c  mov     rdi, rax
0x18000d14f  jmp     loc_18000D1E8
0x18000d154  mov     ebx, [rsp+0E8h+arg_20]
0x18000d15b  mov     r8d, ebx; unsigned int
0x18000d15e  mov     rdx, r12; struct IAppHostElement *
0x18000d161  mov     rcx, rdi; this
0x18000d164  call    ?Update@FTP_SITE@@QEAAJPEAUIAppHostElement@@K@Z; FTP_SITE::Update(IAppHostElement *,ulong)
0x18000d169  mov     esi, eax
0x18000d16b  test    eax, eax
0x18000d16d  jns     loc_18000D321
0x18000d173  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000d17a  jz      loc_18000D3BD
0x18000d180  lea     rax, aFailedToUpdate; "Failed to update site %d\n"
0x18000d187  mov     r8d, 257h
0x18000d18d  jmp     short loc_18000D1B8
0x18000d18f  cmp     eax, 2
0x18000d192  jz      short loc_18000D129
0x18000d194  neg     eax
0x18000d196  sbb     esi, esi
0x18000d198  and     esi, 80004005h
0x18000d19e  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000d1a5  jz      loc_18000D3BD
0x18000d1ab  lea     rax, aFailedTheHashT; "Failed the hash table lookup for site %"...
0x18000d1b2  mov     r8d, 20Ah
0x18000d1b8  mov     [rsp+0E8h+var_B8], ebp
0x18000d1bc  mov     [rsp+0E8h+var_C0], rax
0x18000d1c1  lea     r9, aFtpSiteManager_3; "FTP_SITE_MANAGER::StartOrUpdateOneSite"
0x18000d1c8  mov     [rsp+0E8h+var_C8], esi
0x18000d1cc  lea     rdx, aInetsrvIisIisr_18; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18000d1d3  mov     rcx, cs:g_pDebug
0x18000d1da  call    cs:__imp_PuDbgPrintError
0x18000d1e0  jmp     loc_18000D3BD
0x18000d1e5  mov     rdi, r14
0x18000d1e8  test    rdi, rdi
0x18000d1eb  jnz     short loc_18000D235
0x18000d1ed  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000d1f4  jz      loc_18000D2B3
0x18000d1fa  mov     [rsp+0E8h+var_B8], ebp
0x18000d1fe  lea     rax, aFailedToAlloca_1; "Failed to allocate new site %d\n"
0x18000d205  mov     [rsp+0E8h+var_C0], rax
0x18000d20a  mov     [rsp+0E8h+var_C8], 80070008h
0x18000d212  lea     r9, aFtpSiteManager_3; "FTP_SITE_MANAGER::StartOrUpdateOneSite"
0x18000d219  mov     r8d, 21Ah
0x18000d21f  lea     rdx, aInetsrvIisIisr_18; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18000d226  mov     rcx, cs:g_pDebug
0x18000d22d  call    cs:__imp_PuDbgPrintError
0x18000d233  jmp     short loc_18000D2B3
0x18000d235  mov     ebx, [rsp+0E8h+arg_20]
0x18000d23c  mov     r8d, ebx; unsigned int
0x18000d23f  mov     rdx, r12; struct IAppHostElement *
0x18000d242  mov     rcx, rdi; this
0x18000d245  call    ?Initialize@FTP_SITE@@QEAAJPEAUIAppHostElement@@K@Z; FTP_SITE::Initialize(IAppHostElement *,ulong)
0x18000d24a  mov     esi, eax
0x18000d24c  test    eax, eax
0x18000d24e  jns     loc_18000D2E2
0x18000d254  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000d25b  jz      short loc_18000D292
0x18000d25d  mov     [rsp+0E8h+var_B8], ebp
0x18000d261  lea     rax, aFailedToInitia_5; "Failed to initialize site %d\n"
0x18000d268  mov     [rsp+0E8h+var_C0], rax
0x18000d26d  mov     [rsp+0E8h+var_C8], esi
0x18000d271  mov     r8d, 226h
0x18000d277  lea     r9, aFtpSiteManager_3; "FTP_SITE_MANAGER::StartOrUpdateOneSite"
0x18000d27e  lea     rdx, aInetsrvIisIisr_18; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18000d285  mov     rcx, cs:g_pDebug
0x18000d28c  call    cs:__imp_PuDbgPrintError
0x18000d292  or      eax, 0FFFFFFFFh
0x18000d295  lock xadd [rdi+0B0h], eax
0x18000d29d  cmp     eax, 1
0x18000d2a0  jnz     short loc_18000D2B3
0x18000d2a2  mov     rcx, rdi; this
0x18000d2a5  call    ??1FTP_SITE@@AEAA@XZ; FTP_SITE::~FTP_SITE(void)
0x18000d2aa  mov     rcx, rdi; Block
0x18000d2ad  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d2b2  nop
0x18000d2b3  lea     rcx, [rsp+0E8h+var_90]
0x18000d2b8  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x18000d2be  mov     rcx, [rsp+0E8h+var_58]
0x18000d2c6  xor     rcx, rsp; StackCookie
0x18000d2c9  call    __security_check_cookie
0x18000d2ce  add     rsp, 0A8h
0x18000d2d5  pop     r15
0x18000d2d7  pop     r14
0x18000d2d9  pop     r13
0x18000d2db  pop     r12
0x18000d2dd  pop     rdi
0x18000d2de  pop     rsi
0x18000d2df  pop     rbp
0x18000d2e0  pop     rbx
0x18000d2e1  retn
0x18000d2e2  xor     r8d, r8d
0x18000d2e5  mov     rdx, rdi
0x18000d2e8  mov     rcx, r15
0x18000d2eb  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x18000d2f1  test    eax, eax
0x18000d2f3  jz      short loc_18000D321
0x18000d2f5  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000d2fc  jz      short loc_18000D292
0x18000d2fe  mov     [rsp+0E8h+var_B8], ebp
0x18000d302  lea     rax, aFailedToAddNew_2; "Failed to add new site %d to the hash t"...
0x18000d309  mov     [rsp+0E8h+var_C0], rax
0x18000d30e  mov     [rsp+0E8h+var_C8], 80004005h
0x18000d316  mov     r8d, 23Dh
0x18000d31c  jmp     loc_18000D277
0x18000d321  test    ebx, ebx
0x18000d323  jnz     loc_18000D3BD
0x18000d329  lea     rbx, [rdi+0D0h]
0x18000d330  mov     rcx, rbx
0x18000d333  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18000d339  mov     r8, [rdi+0C0h]
0x18000d340  mov     edx, 1
0x18000d345  lock xadd [r8], edx
0x18000d34a  inc     edx
0x18000d34c  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18000d353  test    rcx, rcx
0x18000d356  jz      short loc_18000D35E
0x18000d358  call    cs:__imp_WriteRefTraceLog
0x18000d35e  mov     rbp, [rdi+0C0h]
0x18000d365  mov     rcx, rbx
0x18000d368  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000d36e  cmp     [rbp+48h], r14d
0x18000d372  jz      short loc_18000D37E
0x18000d374  xor     edx, edx; int
0x18000d376  mov     rcx, rdi; this
0x18000d379  call    ?StartSite@FTP_SITE@@QEAAJH@Z; FTP_SITE::StartSite(int)
0x18000d37e  or      ebx, 0FFFFFFFFh
0x18000d381  lock xadd [rbp+0], ebx
0x18000d386  dec     ebx
0x18000d388  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18000d38f  test    rcx, rcx
0x18000d392  jz      short loc_18000D39F
0x18000d394  mov     r8, rbp
0x18000d397  mov     edx, ebx
0x18000d399  call    cs:__imp_WriteRefTraceLog
0x18000d39f  test    ebx, ebx
0x18000d3a1  jnz     short loc_18000D3BD
0x18000d3a3  mov     rcx, rbp; this
0x18000d3a6  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x18000d3ab  nop
0x18000d3ac  mov     rdx, rbp
0x18000d3af  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x18000d3b6  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18000d3bc  nop
0x18000d3bd  test    rdi, rdi
0x18000d3c0  jz      loc_18000D2B3
0x18000d3c6  test    esi, esi
0x18000d3c8  jns     loc_18000D292
0x18000d3ce  lea     rbx, [rdi+0C8h]
0x18000d3d5  mov     rcx, rbx
0x18000d3d8  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000d3de  xor     r8d, r8d; int
0x18000d3e1  mov     edx, esi; int
0x18000d3e3  mov     rcx, rdi; this
0x18000d3e6  call    ?StopSiteNoLock@FTP_SITE@@QEAAJJH@Z; FTP_SITE::StopSiteNoLock(long,int)
0x18000d3eb  mov     rcx, rbx
0x18000d3ee  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000d3f4  jmp     loc_18000D292
```
