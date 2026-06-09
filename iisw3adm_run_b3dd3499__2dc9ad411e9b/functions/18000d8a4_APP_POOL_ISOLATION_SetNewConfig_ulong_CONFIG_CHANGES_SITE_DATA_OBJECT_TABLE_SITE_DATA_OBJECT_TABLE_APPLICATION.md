# APP_POOL_ISOLATION::SetNewConfig(ulong,CONFIG_CHANGES *,SITE_DATA_OBJECT_TABLE *,SITE_DATA_OBJECT_TABLE *,APPLICATION_DATA_OBJECT_TABLE *,APPLICATION_DATA_OBJECT_TABLE *,INativeConfigurationSystem *,APP_POOL_CHANGED_LIST * *)

- ea: `0x18000d8a4`
- end: `0x18000dc7a`
- name: `?SetNewConfig@APP_POOL_ISOLATION@@QEAAJKPEAUCONFIG_CHANGES@@PEAVSITE_DATA_OBJECT_TABLE@@1PEAVAPPLICATION_DATA_OBJECT_TABLE@@2PEAVINativeConfigurationSystem@@PEAPEAVAPP_POOL_CHANGED_LIST@@@Z`
- size: `982`
- prototype: `__int64 __usercall@<rax>(APP_POOL_ISOLATION *__hidden this@<rcx>, unsigned int@<edx>, struct CONFIG_CHANGES *@<r8>, struct SITE_DATA_OBJECT_TABLE *@<r9>, struct SITE_DATA_OBJECT_TABLE *, struct APPLICATION_DATA_OBJECT_TABLE *, struct APPLICATION_DATA_OBJECT_TABLE *, struct INativeConfigurationSystem *, struct APP_POOL_CHANGED_LIST **)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002e84c`
- `0x18002fad4`

## callees

- `0x180001234`
- `0x180001274`
- `0x180005878`
- `0x180008cb4`
- `0x18000a58c`
- `0x18000bd60`
- `0x18000beb4`
- `0x18000c000`
- `0x18000c0dc`
- `0x18000cf28`
- `0x18000d084`
- `0x18000d8a4`
- `0x180061060`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000daee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000daee`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000db3c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000db3c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000db05`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000db05`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x18000dbc0`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x18000dbe3`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x18000dbc0`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x18000dbe3`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x18000d9d3`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x18000d9d3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000dc52`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000dc52`
- `iisutil!PuDbgPrint` at `0x18000d958`
- `iisutil!PuDbgPrint` at `0x18000d958`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000d8ff`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000d8ff`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x18000da2b`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x18000da2b`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18000d911`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18000d911`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18000dc48`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18000dc48`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000da01`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000da01`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000db86`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000db86`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000db9d`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000db9d`

## string_xrefs

- `0x18000d934`: `SetNewConfig (ChangeNumber: %d)\n`
- `0x18000d93f`: `APP_POOL_ISOLATION::SetNewConfig`
- `0x18000d951`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool_isolation.cxx`

## pseudocode

```c
__int64 __fastcall APP_POOL_ISOLATION::SetNewConfig(
        LPCWSTR *this,
        int a2,
        struct CONFIG_CHANGES *a3,
        struct SITE_DATA_OBJECT_TABLE *a4,
        struct SITE_DATA_OBJECT_TABLE *a5,
        struct APPLICATION_DATA_OBJECT_TABLE *a6,
        struct APPLICATION_DATA_OBJECT_TABLE *a7,
        struct INativeConfigurationSystem *a8,
        struct APP_POOL_CHANGED_LIST **a9)
{
  AUTO_GROWING_BUFFER *v11; // r12
  int FinalExcludedSectionsInCorrectCase; // ebx
  CLKRHashTable *v13; // rax
  struct SITEAPP_HASH *v14; // r14
  struct SITEAPP_HASH *v15; // r15
  struct STRING_TO_STRING_SET_TABLE *v16; // r8
  int v17; // eax
  AUTO_GROWING_BUFFER *v18; // rcx
  struct CONFIG_CHANGES *v19; // rdx
  struct SITEAPP_HASH *v20; // rdi
  WCHAR *v21; // rcx
  const WCHAR *FileW; // rax
  signed int LastError; // eax
  struct SITE_DATA_OBJECT_TABLE *dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  struct SITE_DATA_OBJECT_TABLE *dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  struct APPLICATION_DATA_OBJECT_TABLE *hTemplateFile; // [rsp+30h] [rbp-D0h]
  struct APPLICATION_DATA_OBJECT_TABLE *v28; // [rsp+38h] [rbp-C8h]
  struct APP_POOL_CHANGED_LIST **v29; // [rsp+40h] [rbp-C0h]
  struct AUTO_GROWING_BUFFER *v31; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v32[2]; // [rsp+60h] [rbp-A0h] BYREF
  struct APP_POOL_CHANGED_LIST **v33; // [rsp+70h] [rbp-90h]
  struct SITE_DATA_OBJECT_TABLE *v34; // [rsp+78h] [rbp-88h]
  struct SITE_DATA_OBJECT_TABLE *v35; // [rsp+80h] [rbp-80h]
  struct CONFIG_CHANGES *v36; // [rsp+88h] [rbp-78h]
  _BYTE v37[32]; // [rsp+90h] [rbp-70h] BYREF
  LPCWSTR lpFileName; // [rsp+B0h] [rbp-50h]
  _BYTE v39[56]; // [rsp+C8h] [rbp-38h] BYREF

  v34 = a5;
  v33 = a9;
  v35 = a4;
  v36 = a3;
  STRU::STRU((STRU *)v37);
  v11 = 0;
  v31 = 0;
  MULTISZ::MULTISZ((MULTISZ *)v39);
  if ( (g_dwDebugFlags & 3) != 0 && g_dwDebugFlags < 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool_isolation.cxx",
      358,
      "APP_POOL_ISOLATION::SetNewConfig",
      "SetNewConfig (ChangeNumber: %d)\n",
      a2);
  if ( !a8 )
  {
    FinalExcludedSectionsInCorrectCase = -2147024809;
LABEL_38:
    v32[0] = L"*";
    v32[1] = L"0";
    WEB_ADMIN_SERVICE::LogEvent(
      g_pWebAdminService,
      0xC0001445,
      2u,
      (const unsigned __int16 **const)v32,
      FinalExcludedSectionsInCorrectCase);
    goto LABEL_39;
  }
  v13 = (CLKRHashTable *)operator new(0x48u);
  v14 = v13;
  if ( !v13 )
  {
    FinalExcludedSectionsInCorrectCase = -2147024882;
    goto LABEL_37;
  }
  CLKRHashTable::CLKRHashTable(
    v13,
    "SITEAPP_HASH",
    (unsigned __int64 (*)(const void *))CTypedHashTable<SITEAPP_HASH,SITEAPP_ENTRY,unsigned short const *,CLKRHashTable>::_ExtractKey,
    (unsigned int (*)(unsigned __int64))POOL_HASH_HASH::CalcKeyHash,
    (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<POOL_HASH_HASH,POOL_HASH_ENTRY,unsigned short const *,CLKRHashTable>::_EqualKeys,
    (void (*)(const void *, int))CTypedHashTable<SITEAPP_HASH,SITEAPP_ENTRY,unsigned short const *,CLKRHashTable>::_AddRefRecord,
    4.0,
    1u,
    0,
    0);
  FinalExcludedSectionsInCorrectCase = APP_POOL_ISOLATION::GetFinalExcludedSectionsInCorrectCase(
                                         (APP_POOL_ISOLATION *)this,
                                         a8,
                                         (struct MULTISZ *)v39);
  if ( FinalExcludedSectionsInCorrectCase < 0 )
  {
    v20 = v14;
LABEL_35:
    SITEAPP_HASH::ClearSiteAppHash(v20);
    CLKRHashTable::~CLKRHashTable(v20);
    operator delete(v20);
    goto LABEL_37;
  }
  v15 = 0;
  v32[0] = (unsigned __int16 *)(this + 2);
  CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)(this + 2));
  FinalExcludedSectionsInCorrectCase = APP_POOL_ISOLATION::CopyAppHostConfigToTemp(
                                         (APP_POOL_ISOLATION *)this,
                                         a8,
                                         (struct STRU *)v37);
  if ( FinalExcludedSectionsInCorrectCase < 0 )
    goto LABEL_27;
  CLKRHashTable::Clear((CLKRHashTable *)(this + 20));
  v16 = (struct STRING_TO_STRING_SET_TABLE *)(this + 19);
  v17 = (*((_BYTE *)g_pWebAdminService + 952) & 2) != 0
      ? APP_POOL_ISOLATION::CalculateConfigurationDataAppHost(lpFileName, v14, v16)
      : APP_POOL_ISOLATION::CalculateConfigurationDataCS(lpFileName, v14, v16);
  FinalExcludedSectionsInCorrectCase = v17;
  if ( v17 < 0 )
    goto LABEL_27;
  FinalExcludedSectionsInCorrectCase = APP_POOL_ISOLATION::GetTemplateFileBuffer(
                                         (struct MULTISZ *)v39,
                                         lpFileName,
                                         &v31);
  if ( FinalExcludedSectionsInCorrectCase < 0 )
  {
    v11 = v31;
LABEL_27:
    v20 = v14;
    goto LABEL_28;
  }
  v18 = (AUTO_GROWING_BUFFER *)this[29];
  if ( v18 )
    AUTO_GROWING_BUFFER::DereferenceBuffer(v18);
  v15 = (struct SITEAPP_HASH *)this[31];
  v19 = v36;
  v20 = 0;
  this[29] = (LPCWSTR)v31;
  v29 = v33;
  dwFlagsAndAttributes = v34;
  dwCreationDisposition = v35;
  this[31] = (LPCWSTR)v14;
  FinalExcludedSectionsInCorrectCase = APP_POOL_ISOLATION::CalculateAppPoolChangedList(
                                         v18,
                                         v19,
                                         v15,
                                         v14,
                                         dwCreationDisposition,
                                         dwFlagsAndAttributes,
                                         hTemplateFile,
                                         v28,
                                         v29);
  if ( FinalExcludedSectionsInCorrectCase >= 0 )
  {
    v21 = (WCHAR *)this[11];
    *((_DWORD *)this + 6) = a2;
    if ( v21 != (WCHAR *)-1LL )
    {
      CloseHandle(v21);
      this[11] = (LPCWSTR)-1LL;
    }
    if ( *((_DWORD *)this + 20) )
    {
      DeleteFileW(this[8]);
      *this[8] = 0;
      *((_DWORD *)this + 20) = 0;
    }
    FileW = (const WCHAR *)CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    this[11] = FileW;
    if ( FileW == (const WCHAR *)-1LL )
    {
      if ( GetLastError() )
      {
        LastError = GetLastError();
        FinalExcludedSectionsInCorrectCase = LastError;
        if ( LastError > 0 )
          FinalExcludedSectionsInCorrectCase = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        FinalExcludedSectionsInCorrectCase = -2147467259;
      }
    }
    else
    {
      FinalExcludedSectionsInCorrectCase = STRU::Copy((STRU *)(this + 4), (const struct STRU *)v37);
    }
  }
LABEL_28:
  CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)v32[0]);
  if ( v11 )
    AUTO_GROWING_BUFFER::DereferenceBuffer(v11);
  if ( v15 )
  {
    SITEAPP_HASH::ClearSiteAppHash(v15);
    CLKRHashTable::~CLKRHashTable(v15);
    operator delete(v15);
  }
  if ( v20 )
    goto LABEL_35;
LABEL_37:
  (*(void (__fastcall **)(struct INativeConfigurationSystem *))(*(_QWORD *)a8 + 16LL))(a8);
  if ( FinalExcludedSectionsInCorrectCase < 0 )
    goto LABEL_38;
LABEL_39:
  MULTISZ::~MULTISZ((MULTISZ *)v39);
  STRU::~STRU((STRU *)v37);
  return (unsigned int)FinalExcludedSectionsInCorrectCase;
}

```

## disassembly

```asm
0x18000d8a4  push    rbp
0x18000d8a6  push    rbx
0x18000d8a7  push    rsi
0x18000d8a8  push    rdi
0x18000d8a9  push    r12
0x18000d8ab  push    r13
0x18000d8ad  push    r14
0x18000d8af  push    r15
0x18000d8b1  lea     rbp, [rsp-18h]
0x18000d8b6  sub     rsp, 118h
0x18000d8bd  mov     rax, cs:__security_cookie
0x18000d8c4  xor     rax, rsp
0x18000d8c7  mov     [rbp+50h+var_50], rax
0x18000d8cb  mov     rax, [rbp+50h+arg_20]
0x18000d8d2  mov     rsi, rcx
0x18000d8d5  mov     r13, [rbp+50h+arg_38]
0x18000d8dc  lea     rcx, [rbp+50h+var_C0]
0x18000d8e0  mov     [rsp+150h+var_D8], rax
0x18000d8e5  mov     ebx, edx
0x18000d8e7  mov     rax, [rbp+50h+arg_40]
0x18000d8ee  mov     [rsp+150h+var_E0], rax
0x18000d8f3  mov     [rbp+50h+var_D0], r9
0x18000d8f7  mov     [rbp+50h+var_C8], r8
0x18000d8fb  mov     [rsp+150h+var_100], edx
0x18000d8ff  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000d905  xor     r12d, r12d
0x18000d908  lea     rcx, [rbp+50h+var_88]
0x18000d90c  mov     [rsp+150h+var_F8], r12
0x18000d911  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x18000d917  mov     eax, cs:g_dwDebugFlags
0x18000d91d  test    al, 3
0x18000d91f  setnz   cl
0x18000d922  bt      eax, 1Fh
0x18000d926  setb    al
0x18000d929  test    al, cl
0x18000d92b  jz      short loc_18000D95E
0x18000d92d  mov     rcx, cs:g_pDebug
0x18000d934  lea     rax, aSetnewconfigCh; "SetNewConfig (ChangeNumber: %d)\n"
0x18000d93b  mov     [rsp+150h+dwFlagsAndAttributes], ebx
0x18000d93f  lea     r9, aAppPoolIsolati_4; "APP_POOL_ISOLATION::SetNewConfig"
0x18000d946  mov     r8d, 166h
0x18000d94c  mov     qword ptr [rsp+150h+dwCreationDisposition], rax
0x18000d951  lea     rdx, aServercommonIn_28; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000d958  call    cs:__imp_PuDbgPrint
0x18000d95e  test    r13, r13
0x18000d961  jnz     short loc_18000D96D
0x18000d963  mov     ebx, 80070057h
0x18000d968  jmp     loc_18000DC0C
0x18000d96d  mov     ecx, 48h ; 'H'; Size
0x18000d972  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d977  mov     r14, rax
0x18000d97a  test    rax, rax
0x18000d97d  jz      loc_18000DBF3
0x18000d983  movsd   xmm0, cs:__real@4010000000000000
0x18000d98b  lea     rax, ?_AddRefRecord@?$CTypedHashTable@VSITEAPP_HASH@@VSITEAPP_ENTRY@@PEBGVCLKRHashTable@@@@CAXPEBXH@Z; CTypedHashTable<SITEAPP_HASH,SITEAPP_ENTRY,ushort const *,CLKRHashTable>::_AddRefRecord(void const *,int)
0x18000d992  mov     [rsp+150h+var_108], r12b
0x18000d997  lea     r9, ?CalcKeyHash@POOL_HASH_HASH@@SAKPEBG@Z; POOL_HASH_HASH::CalcKeyHash(ushort const *)
0x18000d99e  mov     dword ptr [rsp+150h+var_110], r12d
0x18000d9a3  lea     r8, ?_ExtractKey@?$CTypedHashTable@VSITEAPP_HASH@@VSITEAPP_ENTRY@@PEBGVCLKRHashTable@@@@CA?B_KPEBX@Z; CTypedHashTable<SITEAPP_HASH,SITEAPP_ENTRY,ushort const *,CLKRHashTable>::_ExtractKey(void const *)
0x18000d9aa  mov     dword ptr [rsp+150h+var_118], 1; struct APPLICATION_DATA_OBJECT_TABLE *
0x18000d9b2  lea     rdx, aSiteappHash; "SITEAPP_HASH"
0x18000d9b9  movsd   [rsp+150h+hTemplateFile], xmm0; struct APPLICATION_DATA_OBJECT_TABLE *
0x18000d9bf  mov     rcx, r14
0x18000d9c2  mov     qword ptr [rsp+150h+dwFlagsAndAttributes], rax
0x18000d9c7  lea     rax, ?_EqualKeys@?$CTypedHashTable@VPOOL_HASH_HASH@@VPOOL_HASH_ENTRY@@PEBGVCLKRHashTable@@@@CA_N_K0@Z; CTypedHashTable<POOL_HASH_HASH,POOL_HASH_ENTRY,ushort const *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x18000d9ce  mov     qword ptr [rsp+150h+dwCreationDisposition], rax
0x18000d9d3  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x18000d9d9  lea     r8, [rbp+50h+var_88]; struct MULTISZ *
0x18000d9dd  mov     rdx, r13; struct INativeConfigurationSystem *
0x18000d9e0  mov     rcx, rsi; this
0x18000d9e3  call    ?GetFinalExcludedSectionsInCorrectCase@APP_POOL_ISOLATION@@AEAAJPEAVINativeConfigurationSystem@@PEAVMULTISZ@@@Z; APP_POOL_ISOLATION::GetFinalExcludedSectionsInCorrectCase(INativeConfigurationSystem *,MULTISZ *)
0x18000d9e8  mov     ebx, eax
0x18000d9ea  test    eax, eax
0x18000d9ec  js      loc_18000DBD5
0x18000d9f2  lea     rax, [rsi+10h]
0x18000d9f6  xor     r15d, r15d
0x18000d9f9  mov     rcx, rax
0x18000d9fc  mov     [rsp+150h+var_F0], rax
0x18000da01  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000da07  lea     r8, [rbp+50h+var_C0]; struct STRU *
0x18000da0b  mov     rdx, r13; struct INativeConfigurationSystem *
0x18000da0e  mov     rcx, rsi; this
0x18000da11  call    ?CopyAppHostConfigToTemp@APP_POOL_ISOLATION@@AEAAJPEAVINativeConfigurationSystem@@PEAVSTRU@@@Z; APP_POOL_ISOLATION::CopyAppHostConfigToTemp(INativeConfigurationSystem *,STRU *)
0x18000da16  mov     ebx, eax
0x18000da18  test    eax, eax
0x18000da1a  js      loc_18000DB95
0x18000da20  lea     rbx, [rsi+98h]
0x18000da27  lea     rcx, [rbx+8]
0x18000da2b  call    cs:__imp_?Clear@CLKRHashTable@@QEAAXXZ; CLKRHashTable::Clear(void)
0x18000da31  mov     rax, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x18000da38  mov     r8, rbx; struct STRING_TO_STRING_SET_TABLE *
0x18000da3b  mov     rcx, [rbp+50h+lpFileName]; unsigned __int16 *
0x18000da3f  mov     rdx, r14; struct SITEAPP_HASH *
0x18000da42  test    byte ptr [rax+3B8h], 2
0x18000da49  jz      loc_18000DB6D
0x18000da4f  call    ?CalculateConfigurationDataAppHost@APP_POOL_ISOLATION@@CAJPEBGPEAVSITEAPP_HASH@@PEAVSTRING_TO_STRING_SET_TABLE@@@Z; APP_POOL_ISOLATION::CalculateConfigurationDataAppHost(ushort const *,SITEAPP_HASH *,STRING_TO_STRING_SET_TABLE *)
0x18000da54  mov     ebx, eax
0x18000da56  test    eax, eax
0x18000da58  js      loc_18000DB95
0x18000da5e  mov     rdx, [rbp+50h+lpFileName]; lpFileName
0x18000da62  lea     r8, [rsp+150h+var_F8]; struct AUTO_GROWING_BUFFER **
0x18000da67  lea     rcx, [rbp+50h+var_88]; struct MULTISZ *
0x18000da6b  call    ?GetTemplateFileBuffer@APP_POOL_ISOLATION@@CAJPEAVMULTISZ@@PEBGPEAPEAVAUTO_GROWING_BUFFER@@@Z; APP_POOL_ISOLATION::GetTemplateFileBuffer(MULTISZ *,ushort const *,AUTO_GROWING_BUFFER * *)
0x18000da70  mov     ebx, eax
0x18000da72  test    eax, eax
0x18000da74  js      loc_18000DB90
0x18000da7a  mov     rcx, [rsi+0E8h]; this
0x18000da81  test    rcx, rcx
0x18000da84  jz      short loc_18000DA8B
0x18000da86  call    ?DereferenceBuffer@AUTO_GROWING_BUFFER@@QEAAXXZ; AUTO_GROWING_BUFFER::DereferenceBuffer(void)
0x18000da8b  mov     r15, [rsi+0F8h]
0x18000da92  mov     r9, r14; struct SITEAPP_HASH *
0x18000da95  mov     rax, [rsp+150h+var_F8]
0x18000da9a  mov     r8, r15; struct SITEAPP_HASH *
0x18000da9d  mov     rdx, [rbp+50h+var_C8]; struct CONFIG_CHANGES *
0x18000daa1  xor     edi, edi
0x18000daa3  mov     [rsi+0E8h], rax
0x18000daaa  mov     rax, [rsp+150h+var_E0]
0x18000daaf  mov     [rsp+150h+var_110], rax; struct APP_POOL_CHANGED_LIST **
0x18000dab4  mov     rax, [rsp+150h+var_D8]
0x18000dab9  mov     qword ptr [rsp+150h+dwFlagsAndAttributes], rax; struct SITE_DATA_OBJECT_TABLE *
0x18000dabe  mov     rax, [rbp+50h+var_D0]
0x18000dac2  mov     qword ptr [rsp+150h+dwCreationDisposition], rax; struct SITE_DATA_OBJECT_TABLE *
0x18000dac7  mov     [rsi+0F8h], r14
0x18000dace  call    ?CalculateAppPoolChangedList@APP_POOL_ISOLATION@@AEAAJPEAUCONFIG_CHANGES@@PEAVSITEAPP_HASH@@1PEAVSITE_DATA_OBJECT_TABLE@@2PEAVAPPLICATION_DATA_OBJECT_TABLE@@3PEAPEAVAPP_POOL_CHANGED_LIST@@@Z; APP_POOL_ISOLATION::CalculateAppPoolChangedList(CONFIG_CHANGES *,SITEAPP_HASH *,SITEAPP_HASH *,SITE_DATA_OBJECT_TABLE *,SITE_DATA_OBJECT_TABLE *,APPLICATION_DATA_OBJECT_TABLE *,APPLICATION_DATA_OBJECT_TABLE *,APP_POOL_CHANGED_LIST * *)
0x18000dad3  mov     ebx, eax
0x18000dad5  test    eax, eax
0x18000dad7  js      loc_18000DB98
0x18000dadd  mov     rcx, [rsi+58h]; hObject
0x18000dae1  mov     eax, [rsp+150h+var_100]
0x18000dae5  mov     [rsi+18h], eax
0x18000dae8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000daec  jz      short loc_18000DAFC
0x18000daee  call    cs:__imp_CloseHandle
0x18000daf4  mov     qword ptr [rsi+58h], 0FFFFFFFFFFFFFFFFh
0x18000dafc  cmp     [rsi+50h], edi
0x18000daff  jz      short loc_18000DB17
0x18000db01  mov     rcx, [rsi+40h]; lpFileName
0x18000db05  call    cs:__imp_DeleteFileW
0x18000db0b  mov     rcx, [rsi+40h]
0x18000db0f  xor     eax, eax
0x18000db11  mov     [rcx], ax
0x18000db14  mov     [rsi+50h], eax
0x18000db17  mov     rcx, [rbp+50h+lpFileName]; lpFileName
0x18000db1b  xor     r9d, r9d; lpSecurityAttributes
0x18000db1e  mov     [rsp+150h+hTemplateFile], rdi; hTemplateFile
0x18000db23  mov     edx, 80000000h; dwDesiredAccess
0x18000db28  mov     [rsp+150h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000db30  mov     [rsp+150h+dwCreationDisposition], 3; dwCreationDisposition
0x18000db38  lea     r8d, [r9+1]; dwShareMode
0x18000db3c  call    cs:__imp_CreateFileW
0x18000db42  mov     [rsi+58h], rax
0x18000db46  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000db4a  jnz     short loc_18000DB7E
0x18000db4c  call    cs:__imp_GetLastError
0x18000db52  test    eax, eax
0x18000db54  jz      short loc_18000DB77
0x18000db56  call    cs:__imp_GetLastError
0x18000db5c  mov     ebx, eax
0x18000db5e  test    eax, eax
0x18000db60  jle     short loc_18000DB98
0x18000db62  movzx   ebx, ax
0x18000db65  or      ebx, 80070000h
0x18000db6b  jmp     short loc_18000DB98
0x18000db6d  call    ?CalculateConfigurationDataCS@APP_POOL_ISOLATION@@CAJPEBGPEAVSITEAPP_HASH@@PEAVSTRING_TO_STRING_SET_TABLE@@@Z; APP_POOL_ISOLATION::CalculateConfigurationDataCS(ushort const *,SITEAPP_HASH *,STRING_TO_STRING_SET_TABLE *)
0x18000db72  jmp     loc_18000DA54
0x18000db77  mov     ebx, 80004005h
0x18000db7c  jmp     short loc_18000DB98
0x18000db7e  lea     rdx, [rbp+50h+var_C0]
0x18000db82  lea     rcx, [rsi+20h]
0x18000db86  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x18000db8c  mov     ebx, eax
0x18000db8e  jmp     short loc_18000DB98
0x18000db90  mov     r12, [rsp+150h+var_F8]
0x18000db95  mov     rdi, r14
0x18000db98  mov     rcx, [rsp+150h+var_F0]
0x18000db9d  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000dba3  test    r12, r12
0x18000dba6  jz      short loc_18000DBB0
0x18000dba8  mov     rcx, r12; this
0x18000dbab  call    ?DereferenceBuffer@AUTO_GROWING_BUFFER@@QEAAXXZ; AUTO_GROWING_BUFFER::DereferenceBuffer(void)
0x18000dbb0  test    r15, r15
0x18000dbb3  jz      short loc_18000DBCE
0x18000dbb5  mov     rcx, r15; struct SITEAPP_HASH *
0x18000dbb8  call    ?ClearSiteAppHash@SITEAPP_HASH@@SAXPEAV1@@Z; SITEAPP_HASH::ClearSiteAppHash(SITEAPP_HASH *)
0x18000dbbd  mov     rcx, r15
0x18000dbc0  call    cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
0x18000dbc6  mov     rcx, r15; Block
0x18000dbc9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000dbce  test    rdi, rdi
0x18000dbd1  jz      short loc_18000DBF8
0x18000dbd3  jmp     short loc_18000DBD8
0x18000dbd5  mov     rdi, r14
0x18000dbd8  mov     rcx, rdi; struct SITEAPP_HASH *
0x18000dbdb  call    ?ClearSiteAppHash@SITEAPP_HASH@@SAXPEAV1@@Z; SITEAPP_HASH::ClearSiteAppHash(SITEAPP_HASH *)
0x18000dbe0  mov     rcx, rdi
0x18000dbe3  call    cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
0x18000dbe9  mov     rcx, rdi; Block
0x18000dbec  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000dbf1  jmp     short loc_18000DBF8
0x18000dbf3  mov     ebx, 8007000Eh
0x18000dbf8  mov     rax, [r13+0]
0x18000dbfc  mov     rcx, r13
0x18000dbff  mov     rax, [rax+10h]
0x18000dc03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc08  test    ebx, ebx
0x18000dc0a  jns     short loc_18000DC44
0x18000dc0c  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; this
0x18000dc13  lea     rax, asc_180067B9C; "*"
0x18000dc1a  mov     [rsp+150h+var_F0], rax
0x18000dc1f  lea     r9, [rsp+150h+var_F0]; unsigned __int16 **
0x18000dc24  lea     rax, a0; "0"
0x18000dc2b  mov     [rsp+150h+dwCreationDisposition], ebx; unsigned int
0x18000dc2f  mov     r8d, 2; unsigned __int16
0x18000dc35  mov     [rsp+150h+var_E8], rax
0x18000dc3a  mov     edx, 0C0001445h; unsigned int
0x18000dc3f  call    ?LogEvent@WEB_ADMIN_SERVICE@@QEAAXKGQEAPEBGK@Z; WEB_ADMIN_SERVICE::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18000dc44  lea     rcx, [rbp+50h+var_88]
0x18000dc48  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x18000dc4e  lea     rcx, [rbp+50h+var_C0]
0x18000dc52  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000dc58  mov     eax, ebx
0x18000dc5a  mov     rcx, [rbp+50h+var_50]
0x18000dc5e  xor     rcx, rsp; StackCookie
0x18000dc61  call    __security_check_cookie
0x18000dc66  add     rsp, 118h
0x18000dc6d  pop     r15
0x18000dc6f  pop     r14
0x18000dc71  pop     r13
0x18000dc73  pop     r12
0x18000dc75  pop     rdi
0x18000dc76  pop     rsi
0x18000dc77  pop     rbx
0x18000dc78  pop     rbp
0x18000dc79  retn
```
