# FTP_SITE_MANAGER::StartOrUpdateAllSites(ulong)

- ea: `0x18000cb74`
- end: `0x18000cfda`
- name: `?StartOrUpdateAllSites@FTP_SITE_MANAGER@@AEAAJK@Z`
- size: `1126`
- prototype: `__int64 __fastcall(FTP_SITE_MANAGER *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `16`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180004610`
- `0x180005b60`
- `0x1800136d0`

## callees

- `0x180001210`
- `0x180001250`
- `0x180008a8c`
- `0x180008f40`
- `0x180009d2c`
- `0x18000aa00`
- `0x18000ac28`
- `0x18000cb74`
- `0x18000cfe0`
- `0x18000d7e0`
- `0x18000d8e0`
- `0x18001908c`
- `0x18002b0c4`
- `0x18002b488`
- `0x18002b5bc`
- `0x180049010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000ceaf`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cf39`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ceaf`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cf39`
- `OLEAUT32!__imp_VariantInit` at `0x18000cbcc`
- `OLEAUT32!__imp_VariantInit` at `0x18000cbcc`
- `OLEAUT32!__imp_VariantClear` at `0x18000cf2a`
- `OLEAUT32!__imp_VariantClear` at `0x18000cf2a`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000cccc`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000cccc`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x18000cf1c`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x18000cf1c`
- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x18000ceee`
- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x18000ceee`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ccfa`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ccfa`
- `iisutil!PuDbgPrintError` at `0x18000cc83`
- `iisutil!PuDbgPrintError` at `0x18000cc83`

## string_xrefs

- `0x18000cc6a`: `FTP_SITE_MANAGER::StartOrUpdateAllSites`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FTP_SITE_MANAGER::StartOrUpdateAllSites(FTP_SITE **this, unsigned int a2)
{
  IRecordInfo *v2; // r15
  struct IAppHostAdminManager *v4; // r13
  struct IErrorInfo *v5; // r14
  int updated; // esi
  FTP_SITE *v7; // rax
  FTP_SITE *v8; // rax
  FTP_SITE *v9; // rax
  volatile signed __int32 *v10; // rbx
  FTP_LOG_NT_EVENT_TABLE *v11; // rax
  LONG v12; // ebx
  struct IAppHostElement *v14; // [rsp+30h] [rbp-49h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-41h] BYREF
  struct IAppHostElement *v16; // [rsp+40h] [rbp-39h] BYREF
  __int64 v17; // [rsp+48h] [rbp-31h] BYREF
  struct IErrorInfo *v18; // [rsp+50h] [rbp-29h] BYREF
  VARIANTARG v19; // [rsp+60h] [rbp-19h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp+7h] BYREF
  FTP_SITE *v21; // [rsp+98h] [rbp+1Fh]
  unsigned int v22; // [rsp+F0h] [rbp+77h] BYREF
  unsigned int v23; // [rsp+F8h] [rbp+7Fh] BYREF

  v2 = (IRecordInfo *)a2;
  v4 = 0;
  v16 = 0;
  v17 = 0;
  v14 = 0;
  v22 = 0;
  v5 = 0;
  v18 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v23 = 0;
  bstrString = 0;
  VariantInit(&pvarg);
  updated = FTP_SITE_MANAGER::UpdateProviderDefinitionTable((FTP_SITE_MANAGER *)this);
  if ( updated < 0 )
    goto LABEL_35;
  updated = FTP_SITE_MANAGER::UpdateGlobalLogging((FTP_SITE_MANAGER *)this);
  if ( updated < 0 )
    goto LABEL_35;
  if ( (_DWORD)v2 )
  {
    CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(this + 22));
    v9 = this[21];
    if ( v9 )
    {
      _InterlockedIncrement((volatile signed __int32 *)v9 + 44);
      v10 = (volatile signed __int32 *)this[21];
      updated = 0;
    }
    else
    {
      v10 = 0;
      updated = -2147023834;
    }
    CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)(this + 22));
    if ( updated < 0 )
      goto LABEL_35;
    FTP_SITE::Update((FTP_SITE *)v10, 0, (unsigned int)v2);
    if ( _InterlockedExchangeAdd(v10 + 44, 0xFFFFFFFF) == 1 && v10 )
    {
      FTP_SITE::~FTP_SITE((FTP_SITE *)v10);
      operator delete((void *)v10);
    }
  }
  else
  {
    v7 = (FTP_SITE *)operator new(0x140u);
    v21 = v7;
    if ( v7 )
      v8 = FTP_SITE::FTP_SITE(v7, (struct FTP_SITE_MANAGER *)this);
    else
      v8 = 0;
    this[21] = v8;
    if ( !v8 )
    {
      updated = -2147024888;
      goto LABEL_35;
    }
    updated = FTP_SITE::Initialize(v8, 0, 0);
    if ( updated < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_site_manager.cxx",
          231,
          "FTP_SITE_MANAGER::StartOrUpdateAllSites",
          updated,
          "Failed to initialize built-in site");
      goto LABEL_35;
    }
    updated = FTP_SITE::StartSite(this[21], 0);
    if ( updated < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_site_manager.cxx",
          242,
          "FTP_SITE_MANAGER::StartOrUpdateAllSites",
          updated,
          "Failed to start the built-in site\n");
      goto LABEL_35;
    }
  }
  v4 = (struct IAppHostAdminManager *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 24LL))(g_pFtpServer);
  updated = Config_GetSection(v4, L"system.applicationHost/sites", L"MACHINE/WEBROOT/APPHOST", &v16, &v18);
  if ( updated >= 0 )
  {
    updated = ((__int64 (__fastcall *)(struct IAppHostElement *, __int64 *))v16->lpVtbl->get_Collection)(v16, &v17);
    if ( updated >= 0 )
    {
      ((void (__fastcall *)(struct IAppHostElement *))v16->lpVtbl->Release)(v16);
      v16 = 0;
      updated = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v17 + 24LL))(v17, &v22);
      if ( updated >= 0 )
      {
        v12 = 0;
        if ( v22 )
        {
          while ( 1 )
          {
            pvarg.vt = 19;
            pvarg.lVal = v12;
            v19 = pvarg;
            updated = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, struct IAppHostElement **))(*(_QWORD *)v17 + 32LL))(
                        v17,
                        &v19,
                        &v14);
            if ( updated < 0 )
              break;
            updated = Config_GetDWORDProperty(v14, L"id", &v23);
            if ( updated < 0 )
              break;
            updated = Config_GetStringProperty(v14, L"name", &bstrString);
            if ( updated < 0 )
              break;
            FTP_SITE_MANAGER::StartOrUpdateOneSite((FTP_SITE_MANAGER *)this, v23, bstrString, v14, (unsigned int)v2);
            ((void (__fastcall *)(struct IAppHostElement *))v14->lpVtbl->Release)(v14);
            v14 = 0;
            SysFreeString(bstrString);
            bstrString = 0;
            if ( ++v12 >= v22 )
              goto LABEL_32;
          }
        }
        else
        {
LABEL_32:
          if ( (_DWORD)v2 )
          {
            *(_QWORD *)&v19.vt = FTP_SITE_MANAGER::StopRemovedSitesAndBindingsPredicate;
            v19.llVal = 0;
            v19.pRecInfo = v2;
            CLKRHashTable::DeleteIf(
              (CLKRHashTable *)(this + 1),
              (enum LK_PREDICATE (__high *)(const void *, void *))CTypedHashTable<TOKEN_CACHE,TOKEN_CACHE_ENTRY,TOKEN_CACHE_KEY *,CLKRHashTable>::_Pred,
              &v19);
            *(_QWORD *)&v19.vt = 0;
            v19.llVal = (LONGLONG)FTP_SITE_MANAGER::StartNewSitesAndBindingsAction;
            v19.pRecInfo = v2;
            CLKRHashTable::Apply(
              this + 1,
              CTypedHashTable<FTP_LOG_FILE_TABLE,FTP_LOG_FILE,unsigned short const *,CLKRHashTable>::_Action,
              &v19,
              2);
          }
        }
      }
    }
    v5 = v18;
  }
  else
  {
    v11 = (FTP_LOG_NT_EVENT_TABLE *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 40LL))(g_pFtpServer);
    v5 = v18;
    FTP_LOG_NT_EVENT_TABLE::LogEventConfigError(v11, v18, updated);
  }
LABEL_35:
  VariantClear(&pvarg);
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v16 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v16->lpVtbl->Release)(v16);
    v16 = 0;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v14 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v14->lpVtbl->Release)(v14);
    v14 = 0;
  }
  if ( v5 )
    ((void (__fastcall *)(struct IErrorInfo *))v5->lpVtbl->Release)(v5);
  if ( v4 )
    (*(void (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 208LL))(g_pFtpServer);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18000cb74  mov     [rsp-8+arg_0], rbx
0x18000cb79  push    rbp
0x18000cb7a  push    rsi
0x18000cb7b  push    rdi
0x18000cb7c  push    r12
0x18000cb7e  push    r13
0x18000cb80  push    r14
0x18000cb82  push    r15
0x18000cb84  lea     rbp, [rsp-27h]
0x18000cb89  sub     rsp, 0A0h
0x18000cb90  mov     r15d, edx
0x18000cb93  mov     rdi, rcx
0x18000cb96  xor     r12d, r12d
0x18000cb99  mov     r13d, r12d
0x18000cb9c  mov     [rbp+57h+var_90], r12
0x18000cba0  mov     [rbp+57h+var_88], r12
0x18000cba4  mov     [rbp+57h+var_A0], r12
0x18000cba8  mov     [rbp+57h+arg_10], r12d
0x18000cbac  mov     r14d, r12d
0x18000cbaf  mov     [rbp+57h+var_80], r12
0x18000cbb3  xorps   xmm0, xmm0
0x18000cbb6  xor     eax, eax
0x18000cbb8  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18000cbbc  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18000cbc0  mov     [rbp+57h+arg_18], r12d
0x18000cbc4  mov     [rbp+57h+bstrString], r12
0x18000cbc8  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000cbcc  call    cs:__imp_VariantInit
0x18000cbd2  mov     rcx, rdi; this
0x18000cbd5  call    ?UpdateProviderDefinitionTable@FTP_SITE_MANAGER@@AEAAJXZ; FTP_SITE_MANAGER::UpdateProviderDefinitionTable(void)
0x18000cbda  mov     esi, eax
0x18000cbdc  test    eax, eax
0x18000cbde  js      loc_18000CF26
0x18000cbe4  mov     rcx, rdi; this
0x18000cbe7  call    ?UpdateGlobalLogging@FTP_SITE_MANAGER@@AEAAJXZ; FTP_SITE_MANAGER::UpdateGlobalLogging(void)
0x18000cbec  mov     esi, eax
0x18000cbee  test    eax, eax
0x18000cbf0  js      loc_18000CF26
0x18000cbf6  test    r15d, r15d
0x18000cbf9  jnz     loc_18000CCC2
0x18000cbff  mov     ecx, 140h; Size
0x18000cc04  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cc09  mov     [rbp+57h+var_38], rax
0x18000cc0d  test    rax, rax
0x18000cc10  jz      short loc_18000CC1F
0x18000cc12  mov     rdx, rdi; struct FTP_SITE_MANAGER *
0x18000cc15  mov     rcx, rax; this
0x18000cc18  call    ??0FTP_SITE@@QEAA@PEAVFTP_SITE_MANAGER@@@Z; FTP_SITE::FTP_SITE(FTP_SITE_MANAGER *)
0x18000cc1d  jmp     short loc_18000CC22
0x18000cc1f  mov     rax, r12
0x18000cc22  mov     [rdi+0A8h], rax
0x18000cc29  test    rax, rax
0x18000cc2c  jnz     short loc_18000CC38
0x18000cc2e  mov     esi, 80070008h
0x18000cc33  jmp     loc_18000CF26
0x18000cc38  xor     r8d, r8d; unsigned int
0x18000cc3b  xor     edx, edx; struct IAppHostElement *
0x18000cc3d  mov     rcx, rax; this
0x18000cc40  call    ?Initialize@FTP_SITE@@QEAAJPEAUIAppHostElement@@K@Z; FTP_SITE::Initialize(IAppHostElement *,ulong)
0x18000cc45  mov     esi, eax
0x18000cc47  test    eax, eax
0x18000cc49  jns     short loc_18000CC8E
0x18000cc4b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000cc52  jz      loc_18000CF26
0x18000cc58  lea     rax, aFailedToInitia_10; "Failed to initialize built-in site"
0x18000cc5f  mov     r8d, 0E7h
0x18000cc65  mov     [rsp+0D0h+var_A8], rax
0x18000cc6a  lea     r9, aFtpSiteManager_0; "FTP_SITE_MANAGER::StartOrUpdateAllSites"
0x18000cc71  mov     dword ptr [rsp+0D0h+var_B0], esi
0x18000cc75  lea     rdx, aInetsrvIisIisr_18; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18000cc7c  mov     rcx, cs:g_pDebug
0x18000cc83  call    cs:__imp_PuDbgPrintError
0x18000cc89  jmp     loc_18000CF26
0x18000cc8e  xor     edx, edx; int
0x18000cc90  mov     rcx, [rdi+0A8h]; this
0x18000cc97  call    ?StartSite@FTP_SITE@@QEAAJH@Z; FTP_SITE::StartSite(int)
0x18000cc9c  mov     esi, eax
0x18000cc9e  test    eax, eax
0x18000cca0  jns     loc_18000CD3D
0x18000cca6  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000ccad  jz      loc_18000CF26
0x18000ccb3  lea     rax, aFailedToStartT; "Failed to start the built-in site\n"
0x18000ccba  mov     r8d, 0F2h
0x18000ccc0  jmp     short loc_18000CC65
0x18000ccc2  lea     r12, [rdi+0B0h]
0x18000ccc9  mov     rcx, r12
0x18000cccc  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18000ccd2  mov     rax, [rdi+0A8h]
0x18000ccd9  test    rax, rax
0x18000ccdc  jz      short loc_18000CCF0
0x18000ccde  lock inc dword ptr [rax+0B0h]
0x18000cce5  mov     rbx, [rdi+0A8h]
0x18000ccec  xor     esi, esi
0x18000ccee  jmp     short loc_18000CCF7
0x18000ccf0  xor     ebx, ebx
0x18000ccf2  mov     esi, 80070426h
0x18000ccf7  mov     rcx, r12
0x18000ccfa  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000cd00  xor     r12d, r12d
0x18000cd03  test    esi, esi
0x18000cd05  js      loc_18000CF26
0x18000cd0b  mov     r8d, r15d; unsigned int
0x18000cd0e  xor     edx, edx; struct IAppHostElement *
0x18000cd10  mov     rcx, rbx; this
0x18000cd13  call    ?Update@FTP_SITE@@QEAAJPEAUIAppHostElement@@K@Z; FTP_SITE::Update(IAppHostElement *,ulong)
0x18000cd18  or      eax, 0FFFFFFFFh
0x18000cd1b  lock xadd [rbx+0B0h], eax
0x18000cd23  cmp     eax, 1
0x18000cd26  jnz     short loc_18000CD3D
0x18000cd28  test    rbx, rbx
0x18000cd2b  jz      short loc_18000CD3D
0x18000cd2d  mov     rcx, rbx; this
0x18000cd30  call    ??1FTP_SITE@@AEAA@XZ; FTP_SITE::~FTP_SITE(void)
0x18000cd35  mov     rcx, rbx; Block
0x18000cd38  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cd3d  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18000cd44  mov     rax, [rcx]
0x18000cd47  mov     rax, [rax+18h]
0x18000cd4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd50  mov     r13, rax
0x18000cd53  lea     rax, [rbp+57h+var_80]
0x18000cd57  mov     [rsp+0D0h+var_B0], rax; struct IErrorInfo **
0x18000cd5c  lea     r9, [rbp+57h+var_90]; struct IAppHostElement **
0x18000cd60  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18000cd67  lea     rdx, aSystemApplicat; "system.applicationHost/sites"
0x18000cd6e  mov     rcx, r13; struct IAppHostAdminManager *
0x18000cd71  call    ?Config_GetSection@@YAJPEAUIAppHostAdminManager@@PEBG1PEAPEAUIAppHostElement@@PEAPEAUIErrorInfo@@@Z; Config_GetSection(IAppHostAdminManager *,ushort const *,ushort const *,IAppHostElement * *,IErrorInfo * *)
0x18000cd76  mov     esi, eax
0x18000cd78  test    eax, eax
0x18000cd7a  jns     short loc_18000CDA6
0x18000cd7c  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18000cd83  mov     rdx, [rcx]
0x18000cd86  mov     rax, [rdx+28h]
0x18000cd8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd8f  mov     r8d, esi; int
0x18000cd92  mov     r14, [rbp+57h+var_80]
0x18000cd96  mov     rdx, r14; struct IErrorInfo *
0x18000cd99  mov     rcx, rax; this
0x18000cd9c  call    ?LogEventConfigError@FTP_LOG_NT_EVENT_TABLE@@QEAAXPEAUIErrorInfo@@J@Z; FTP_LOG_NT_EVENT_TABLE::LogEventConfigError(IErrorInfo *,long)
0x18000cda1  jmp     loc_18000CF26
0x18000cda6  mov     rcx, [rbp+57h+var_90]
0x18000cdaa  mov     rax, [rcx]
0x18000cdad  lea     rdx, [rbp+57h+var_88]
0x18000cdb1  mov     rax, [rax+20h]
0x18000cdb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdba  mov     esi, eax
0x18000cdbc  test    eax, eax
0x18000cdbe  js      loc_18000CF22
0x18000cdc4  mov     rcx, [rbp+57h+var_90]
0x18000cdc8  mov     rax, [rcx]
0x18000cdcb  mov     rax, [rax+10h]
0x18000cdcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdd4  mov     [rbp+57h+var_90], r12
0x18000cdd8  mov     rcx, [rbp+57h+var_88]
0x18000cddc  mov     rax, [rcx]
0x18000cddf  lea     rdx, [rbp+57h+arg_10]
0x18000cde3  mov     rax, [rax+18h]
0x18000cde7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdec  mov     esi, eax
0x18000cdee  test    eax, eax
0x18000cdf0  js      loc_18000CF22
0x18000cdf6  mov     ebx, r12d
0x18000cdf9  cmp     [rbp+57h+arg_10], r12d
0x18000cdfd  jbe     loc_18000CEC4
0x18000ce03  mov     eax, 13h
0x18000ce08  mov     word ptr [rbp+57h+pvarg], ax
0x18000ce0c  mov     dword ptr [rbp+57h+pvarg+8], ebx
0x18000ce0f  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18000ce13  movaps  [rbp+57h+var_70], xmm0
0x18000ce17  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18000ce1c  movsd   [rbp+57h+var_60], xmm1
0x18000ce21  mov     rcx, [rbp+57h+var_88]
0x18000ce25  mov     rax, [rcx]
0x18000ce28  lea     r8, [rbp+57h+var_A0]
0x18000ce2c  lea     rdx, [rbp+57h+var_70]
0x18000ce30  mov     rax, [rax+20h]
0x18000ce34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce39  mov     esi, eax
0x18000ce3b  test    eax, eax
0x18000ce3d  js      loc_18000CF22
0x18000ce43  lea     r8, [rbp+57h+arg_18]; unsigned int *
0x18000ce47  lea     rdx, aId; "id"
0x18000ce4e  mov     rcx, [rbp+57h+var_A0]; struct IAppHostElement *
0x18000ce52  call    ?Config_GetDWORDProperty@@YAJPEAUIAppHostElement@@PEBGPEAK@Z; Config_GetDWORDProperty(IAppHostElement *,ushort const *,ulong *)
0x18000ce57  mov     esi, eax
0x18000ce59  test    eax, eax
0x18000ce5b  js      loc_18000CF22
0x18000ce61  lea     r8, [rbp+57h+bstrString]; unsigned __int16 **
0x18000ce65  lea     rdx, aName; "name"
0x18000ce6c  mov     rcx, [rbp+57h+var_A0]; struct IAppHostElement *
0x18000ce70  call    ?Config_GetStringProperty@@YAJPEAUIAppHostElement@@PEBGPEAPEAG@Z; Config_GetStringProperty(IAppHostElement *,ushort const *,ushort * *)
0x18000ce75  mov     esi, eax
0x18000ce77  test    eax, eax
0x18000ce79  js      loc_18000CF22
0x18000ce7f  mov     dword ptr [rsp+0D0h+var_B0], r15d; unsigned int
0x18000ce84  mov     r9, [rbp+57h+var_A0]; struct IAppHostElement *
0x18000ce88  mov     r8, [rbp+57h+bstrString]; unsigned __int16 *
0x18000ce8c  mov     edx, [rbp+57h+arg_18]; unsigned int
0x18000ce8f  mov     rcx, rdi; this
0x18000ce92  call    ?StartOrUpdateOneSite@FTP_SITE_MANAGER@@AEAAXKPEBGPEAUIAppHostElement@@K@Z; FTP_SITE_MANAGER::StartOrUpdateOneSite(ulong,ushort const *,IAppHostElement *,ulong)
0x18000ce97  mov     rcx, [rbp+57h+var_A0]
0x18000ce9b  mov     rax, [rcx]
0x18000ce9e  mov     rax, [rax+10h]
0x18000cea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cea7  mov     [rbp+57h+var_A0], r12
0x18000ceab  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18000ceaf  call    cs:__imp_SysFreeString
0x18000ceb5  mov     [rbp+57h+bstrString], r12
0x18000ceb9  inc     ebx
0x18000cebb  cmp     ebx, [rbp+57h+arg_10]
0x18000cebe  jb      loc_18000CE03
0x18000cec4  test    r15d, r15d
0x18000cec7  jz      short loc_18000CF22
0x18000cec9  mov     rbx, r15
0x18000cecc  lea     rax, ?StopRemovedSitesAndBindingsPredicate@FTP_SITE_MANAGER@@CA?AW4LK_PREDICATE@@PEAVFTP_SITE@@PEAX@Z; FTP_SITE_MANAGER::StopRemovedSitesAndBindingsPredicate(FTP_SITE *,void *)
0x18000ced3  mov     qword ptr [rbp+57h+var_70], rax
0x18000ced7  mov     qword ptr [rbp+57h+var_70+8], r12
0x18000cedb  mov     [rbp+57h+var_60], rbx
0x18000cedf  lea     r8, [rbp+57h+var_70]
0x18000cee3  lea     rdx, ?_Pred@?$CTypedHashTable@VTOKEN_CACHE@@VTOKEN_CACHE_ENTRY@@PEAVTOKEN_CACHE_KEY@@VCLKRHashTable@@@@CA?AW4LK_PREDICATE@@PEBXPEAX@Z; CTypedHashTable<TOKEN_CACHE,TOKEN_CACHE_ENTRY,TOKEN_CACHE_KEY *,CLKRHashTable>::_Pred(void const *,void *)
0x18000ceea  lea     rcx, [rdi+8]
0x18000ceee  call    cs:__imp_?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z; CLKRHashTable::DeleteIf(LK_PREDICATE (*)(void const *,void *),void *)
0x18000cef4  mov     qword ptr [rbp+57h+var_70], r12
0x18000cef8  lea     rax, ?StartNewSitesAndBindingsAction@FTP_SITE_MANAGER@@CA?AW4LK_ACTION@@PEAVFTP_SITE@@PEAX@Z; FTP_SITE_MANAGER::StartNewSitesAndBindingsAction(FTP_SITE *,void *)
0x18000ceff  mov     qword ptr [rbp+57h+var_70+8], rax
0x18000cf03  mov     [rbp+57h+var_60], rbx
0x18000cf07  mov     r9d, 2
0x18000cf0d  lea     r8, [rbp+57h+var_70]
0x18000cf11  lea     rdx, ?_Action@?$CTypedHashTable@VFTP_LOG_FILE_TABLE@@VFTP_LOG_FILE@@PEBGVCLKRHashTable@@@@CA?AW4LK_ACTION@@PEBXPEAX@Z; CTypedHashTable<FTP_LOG_FILE_TABLE,FTP_LOG_FILE,ushort const *,CLKRHashTable>::_Action(void const *,void *)
0x18000cf18  lea     rcx, [rdi+8]
0x18000cf1c  call    cs:__imp_?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z; CLKRHashTable::Apply(LK_ACTION (*)(void const *,void *),void *,LK_LOCKTYPE)
0x18000cf22  mov     r14, [rbp+57h+var_80]
0x18000cf26  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000cf2a  call    cs:__imp_VariantClear
0x18000cf30  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18000cf34  test    rcx, rcx
0x18000cf37  jz      short loc_18000CF43
0x18000cf39  call    cs:__imp_SysFreeString
0x18000cf3f  mov     [rbp+57h+bstrString], r12
0x18000cf43  mov     rcx, [rbp+57h+var_90]
0x18000cf47  test    rcx, rcx
0x18000cf4a  jz      short loc_18000CF5C
0x18000cf4c  mov     rax, [rcx]
0x18000cf4f  mov     rax, [rax+10h]
0x18000cf53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf58  mov     [rbp+57h+var_90], r12
0x18000cf5c  mov     rcx, [rbp+57h+var_88]
0x18000cf60  test    rcx, rcx
0x18000cf63  jz      short loc_18000CF75
0x18000cf65  mov     rax, [rcx]
0x18000cf68  mov     rax, [rax+10h]
0x18000cf6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf71  mov     [rbp+57h+var_88], r12
0x18000cf75  mov     rcx, [rbp+57h+var_A0]
0x18000cf79  test    rcx, rcx
0x18000cf7c  jz      short loc_18000CF8E
0x18000cf7e  mov     rax, [rcx]
0x18000cf81  mov     rax, [rax+10h]
0x18000cf85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf8a  mov     [rbp+57h+var_A0], r12
0x18000cf8e  test    r14, r14
0x18000cf91  jz      short loc_18000CFA2
0x18000cf93  mov     rax, [r14]
0x18000cf96  mov     rcx, r14
0x18000cf99  mov     rax, [rax+10h]
0x18000cf9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfa2  test    r13, r13
0x18000cfa5  jz      short loc_18000CFBD
0x18000cfa7  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18000cfae  mov     rax, [rcx]
0x18000cfb1  mov     rax, [rax+0D0h]
0x18000cfb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfbd  mov     eax, esi
0x18000cfbf  mov     rbx, [rsp+0D0h+arg_0]
0x18000cfc7  add     rsp, 0A0h
0x18000cfce  pop     r15
0x18000cfd0  pop     r14
0x18000cfd2  pop     r13
0x18000cfd4  pop     r12
0x18000cfd6  pop     rdi
0x18000cfd7  pop     rsi
0x18000cfd8  pop     rbp
0x18000cfd9  retn
```
