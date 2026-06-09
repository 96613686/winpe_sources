# Microsoft::Debuggers::CompressedPages::CompressedPageDataReaderImpl_Ver001<uint>::NoErrorCheckCacheSymbolData_Ver1and2(void)

- ea: `0x18038195c`
- end: `0x18038273b`
- name: `?NoErrorCheckCacheSymbolData_Ver1and2@?$CompressedPageDataReaderImpl_Ver001@I@CompressedPages@Debuggers@Microsoft@@AEAAJXZ`
- size: `3551`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180381680`
- `0x180381730`

## callees

- `0x180071a60`
- `0x1800b94c4`
- `0x1800f16fc`
- `0x18037dc7c`
- `0x18037df30`
- `0x18037dff8`
- `0x18037e4fc`
- `0x18037e7b0`
- `0x18037e7f8`
- `0x180380524`
- `0x1803806b8`
- `0x18038195c`
- `0x1804da4c0`

## string_xrefs

- `0x180381ec3`: `ActiveProcessLinks`
- `0x180381e9f`: `Flink`
- `0x180381a7b`: `CompressedPageDataReaderImpl_Ver001 warning: failed to get SmGlobals symbol.\n`
- `0x180381abb`: `CompressedPageDataReaderImpl_Ver001 warning: wrong _SM_PAGE_KEY size - actual:%d, expected:%d.\n`
- `0x180381b8b`: `AddRemoveLock`
- `0x180381d37`: `CompressionFormat`
- `0x180381e33`: `CompressedSize`
- `0x180381e7b`: `LazyRemoved`
- `0x180381fb6`: `CompressedPageDataReaderImpl_Ver001 warning: wrong %s bit-field size - actual:%d, expected:%d.\n`
- `0x180381f5f`: `CompressedPageDataReaderImpl_Ver001 warning: wrong %s size - actual:%d, expected:%d.\n`
- `0x180381f8e`: `CompressedPageDataReaderImpl_Ver001 warning: wrong %s bit-field position - actual:%d, expected:%d.\n`
- `0x18038200d`: `CompressedPageDataReaderImpl_Ver001 warning: wrong %s bit-field position - actual:%d, expected:%d.\n`
- `0x180382043`: `_ST_PAGE_ENTRY::CompressedSize`
- `0x18038205b`: `_ST_PAGE_ENTRY::CompressedSize`
- `0x18038207a`: `_ST_PAGE_ENTRY::CompressedSize`
- `0x180382092`: `_ST_PAGE_ENTRY_FLAGS::LazyRemoved`
- `0x1803820aa`: `_ST_PAGE_ENTRY_FLAGS::LazyRemoved`
- `0x1803820c3`: `_ST_PAGE_ENTRY_FLAGS::LazyRemoved`
- `0x180381fcf`: `CompressedPageDataReaderImpl_Ver001 warning: wrong %s offset - actual:%d, expected:%d.\n`
- `0x18038215e`: `nt!MiSystemPartition`
- `0x18038218d`: `MiSystemPartition`
- `0x180382170`: `CompressedPageDataReaderImpl_Ver001 warning: failed to get MiSystemPartition symbol.\n`
- `0x1803821b6`: `MiSystemPartition.Vp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Debuggers::CompressedPages::CompressedPageDataReaderImpl_Ver001<unsigned int>::NoErrorCheckCacheSymbolData_Ver1and2(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  struct _SYMBOL_INFOW *v5; // rax
  struct _SYMBOL_INFOW *v6; // r8
  struct _SYMBOL_INFOW *v7; // rsi
  int SymFromName; // ebx
  struct _SYMBOL_INFOW *v9; // r9
  __int64 Size; // rdx
  char *v11; // rax
  char *v12; // rdi
  struct _SYMBOL_INFOW *v13; // r8
  const wchar_t *v14; // rdx
  __int64 v15; // r9
  unsigned int v16; // eax
  const wchar_t *v17; // rdx
  __int64 v18; // r8
  const unsigned __int16 *v19; // rcx
  unsigned int v20; // eax
  const wchar_t *v21; // rdx
  __int64 v22; // r9
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  struct _SYMBOL_INFOW *v27; // r9
  struct _SYMBOL_INFOW *v28; // r9
  struct _SYMBOL_INFOW *v29; // r9
  int v30; // ecx
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // r9
  struct _FIELD_INFO_WIDE *v36; // [rsp+20h] [rbp-E0h]
  bool v37; // [rsp+28h] [rbp-D8h]
  char *v38; // [rsp+30h] [rbp-D0h] BYREF
  struct _SYMBOL_INFOW *v39; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v40[42]; // [rsp+40h] [rbp-C0h] BYREF
  struct _SYMBOL_INFOW *v41; // [rsp+1A0h] [rbp+A0h] BYREF
  int v42; // [rsp+1A8h] [rbp+A8h] BYREF
  int v43; // [rsp+1B0h] [rbp+B0h] BYREF
  int v44; // [rsp+1B8h] [rbp+B8h] BYREF

  v40[32] = -2;
  if ( (unsigned __int16)(*(_WORD *)(a1 + 50) - 1) > 1u )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2, a3, a4);
  v5 = (struct _SYMBOL_INFOW *)operator new(0x210u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v5;
  v41 = v5;
  if ( v5 )
  {
    memset(v5, 0, 0x210u);
    memset(v7, 0, sizeof(struct _SYMBOL_INFOW));
    v7->SizeOfStruct = 88;
    memset(&v7[1].TypeIndex, 0, 0x54u);
    v7[1].SizeOfStruct = 88;
    memset(&v7[2].TypeIndex, 0, 0x54u);
    v7[2].SizeOfStruct = 88;
    memset(&v7[3].TypeIndex, 0, 0x54u);
    v7[3].SizeOfStruct = 88;
    memset(&v7[4].TypeIndex, 0, 0x54u);
    v7[4].SizeOfStruct = 88;
    memset(&v7[5].TypeIndex, 0, 0x54u);
    v7[5].SizeOfStruct = 88;
  }
  else
  {
    v7 = 0;
  }
  v39 = v7;
  if ( !v7 )
    goto LABEL_18;
  SymFromName = Microsoft::Debuggers::CompressedPages::GetSymFromName(L"nt!SmGlobals", v7, v6);
  if ( SymFromName )
  {
    VerbOut(L"CompressedPageDataReaderImpl_Ver001 warning: failed to get SmGlobals symbol.\n");
    goto LABEL_109;
  }
  SymFromName = Microsoft::Debuggers::CompressedPages::InternalSymGetTypeFromName(
                  v7->ModBase,
                  L"_SM_PAGE_KEY",
                  v7 + 1,
                  v9);
  if ( SymFromName < 0 )
    goto LABEL_109;
  Size = v7[1].Size;
  if ( (_DWORD)Size != 4 )
  {
    VerbOut(
      L"CompressedPageDataReaderImpl_Ver001 warning: wrong _SM_PAGE_KEY size - actual:%d, expected:%d.\n",
      Size,
      4);
LABEL_12:
    SymFromName = -2147467259;
    goto LABEL_109;
  }
  v11 = (char *)operator new(0xB40u, (const struct std::nothrow_t *)&std::nothrow);
  v12 = v11;
  if ( v11 )
    memset(v11, 0, 0xB40u);
  else
    v12 = 0;
  v38 = v12;
  if ( !v12 )
  {
    __1__unique_ptr_UCacheSymbolDataFieldInfoInternals__1__NoErrorCheckCacheSymbolData_Ver1and2___CompressedPageDataReaderImpl_Ver001_I_CompressedPages_Debuggers_Microsoft__AEAAJXZ_U__default_delete_UCacheSymbolDataFieldInfoInternals__1__NoErrorCheckCacheSymbolData_Ver1and2___CompressedPageDataReaderImpl_Ver001_I_CompressedPages_Debuggers_Microsoft__AEAAJXZ__std___std__QEAA_XZ(&v38);
LABEL_18:
    SymFromName = -2147024882;
    goto LABEL_109;
  }
  SymFromName = Microsoft::Debuggers::CompressedPages::GetFieldInfo(L"nt!_EX_PUSH_LOCK", L"Locked", v12);
  if ( SymFromName < 0 )
    goto LABEL_20;
  SymFromName = Microsoft::Debuggers::CompressedPages::GetFieldInfo(L"nt!VLOCK", L"Lock", v12 + 72);
  if ( SymFromName < 0 )
    goto LABEL_20;
  SymFromName = Microsoft::Debuggers::CompressedPages::GetFieldInfo(L"nt!SMKM_STORE_REF", L"Store", v12 + 144);
  if ( SymFromName < 0 )
    goto LABEL_20;
  SymFromName = Microsoft::Debuggers::CompressedPages::GetFieldInfo(L"nt!SMKM_STORE_REF", L"AddRemoveLock", v12 + 216);
  if ( SymFromName < 0 )
    goto LABEL_20;
  SymFromName = Microsoft::Debuggers::CompressedPages::GetFieldInfo(
                  L"nt!SMKM_STORE<SM_TRAITS>",
                  L"RegionSize",
                  v12 + 288);
  if ( SymFromName < 0 )
    goto LABEL_20;
  SymFromName = Microsoft::Debuggers::CompressedPages::GetFieldInfo(
                  L"nt!SMKM_STORE<SM_TRAITS>",
                  L"RegionCountMax",
                  v12 + 360);
  if ( SymFromName < 0 )
    goto LABEL_20;
  SymFromName = Microsoft::Debuggers::CompressedPages::GetFieldInfo(L"nt!SMKM_STORE<SM_TRAITS>", L"Store", v12 + 432);
  if ( SymFromName < 0 )
    goto LABEL_20;
  SymFromName = Microsoft::Debuggers::CompressedPages::GetFieldInfo(
                  L"nt!SMKM_STORE<SM_TRAITS>",
                  L"VirtualRegions",
                  v12 + 504);
  if ( SymFromName < 0 )
    goto LABEL_20;
  SymFromName = Microsoft::Debuggers::CompressedPages::GetFieldInfo(
                  L"nt!SMKM_STORE<SM_TRAITS>",
                  L"StoreLock",
                  v12 + 576);
  if ( SymFromName < 0 )
    goto LABEL_20;
  SymFromName = Microsoft::Debuggers::CompressedPages::GetFieldInfo(L"nt!ST_STORE<SM_TRAITS>", L"UserData", v12 + 648);
  if ( SymFromName < 0 )
    goto LABEL_20;
  SymFromName = Microsoft::Debuggers::CompressedPages::GetFieldInfo(L"nt!ST_STORE<SM_TRAITS>", L"Properties", v12 + 720);
  if ( SymFromName < 0 )
    goto LABEL_20;
  SymFromName = Microsoft::Debuggers::CompressedPages::GetFieldInfo(
                  L"nt!SM_VIRTUAL_REGION",
                  L"VirtualAddress",
                  v12 + 792);
  if ( SymFromName < 0 )
    goto LABEL_20;
  SymFromName = Microsoft::Debuggers::CompressedPages::GetFieldInfo(L"nt!ST_PROPERTIES", L"Params", v12 + 864);
  if ( SymFromName < 0 )
    goto LABEL_20;
  SymFromName = Microsoft::Debuggers::CompressedPages::GetFieldInfo(L"nt!ST_PARAMETERS", L"Store", v12 + 936);
  if ( SymFromName < 0 )
    goto LABEL_20;
  SymFromName = Microsoft::Debuggers::CompressedPages::GetFieldInfo(
                  L"nt!SM_STORE_BASIC_PARAMS",
                  L"StoreType",
                  v12 + 1008);
  if ( SymFromName < 0 )
    goto LABEL_20;
  SymFromName = Microsoft::Debuggers::CompressedPages::GetFieldInfo(
                  L"nt!ST_STORE<SM_TRAITS>::_ST_DATA_MGR",
                  L"CompressionFormat",
                  v12 + 1080);
  if ( SymFromName < 0 )
    goto LABEL_20;
  SymFromName = Microsoft::Debuggers::CompressedPages::GetFieldInfo(L"nt!ST_PROPERTIES", L"OffsetMask", v12 + 1152);
  if ( SymFromName < 0 )
    goto LABEL_20;
  SymFromName = Microsoft::Debuggers::CompressedPages::GetFieldInfo(L"nt!ST_PROPERTIES", L"RegionShift", v12 + 1224);
  if ( SymFromName < 0 )
    goto LABEL_20;
  SymFromName = Microsoft::Debuggers::CompressedPages::GetFieldInfo(
                  L"nt!ST_STORE<SM_TRAITS>::_ST_DATA_MGR",
                  L"PageTree",
                  v12 + 1296);
  if ( SymFromName < 0 )
    goto LABEL_20;
  SymFromName = Microsoft::Debuggers::CompressedPages::GetFieldInfo(
                  L"nt!ST_STORE<SM_TRAITS>::_ST_DATA_MGR",
                  L"Store",
                  v12 + 1368);
  if ( SymFromName < 0 )
    goto LABEL_20;
  SymFromName = Microsoft::Debuggers::CompressedPages::GetFieldInfo(
                  L"nt!ST_STORE<SM_TRAITS>::_ST_PAGE_ENTRY",
                  L"Key",
                  v12 + 1440);
  if ( SymFromName < 0 )
    goto LABEL_20;
  SymFromName = Microsoft::Debuggers::CompressedPages::GetFieldInfo(
                  L"nt!ST_STORE<SM_TRAITS>::_ST_PAGE_ENTRY",
                  L"Offset",
                  v12 + 1512);
  if ( SymFromName < 0 )
    goto LABEL_20;
  SymFromName = Microsoft::Debuggers::CompressedPages::GetFieldInfo(
                  L"nt!ST_STORE<SM_TRAITS>::_ST_PAGE_ENTRY",
                  L"CompressedSize",
                  v12 + 1584);
  if ( SymFromName < 0
    || (SymFromName = Microsoft::Debuggers::CompressedPages::GetFieldInfo(
                        L"nt!ST_STORE<SM_TRAITS>::_ST_PAGE_ENTRY",
                        L"Flags",
                        v12 + 1656),
        SymFromName < 0)
    || (SymFromName = Microsoft::Debuggers::CompressedPages::GetFieldInfo(
                        L"nt!ST_STORE<SM_TRAITS>::_ST_PAGE_ENTRY_FLAGS",
                        L"LazyRemoved",
                        v12 + 1728),
        SymFromName < 0)
    || (SymFromName = Microsoft::Debuggers::CompressedPages::GetFieldInfo(L"nt!_LIST_ENTRY", L"Flink", v12 + 1800),
        SymFromName < 0)
    || (SymFromName = Microsoft::Debuggers::CompressedPages::GetFieldInfo(
                        L"nt!_EPROCESS",
                        L"ActiveProcessLinks",
                        v12 + 1872),
        SymFromName < 0)
    || (SymFromName = Microsoft::Debuggers::CompressedPages::GetFieldInfo(L"nt!_EPROCESS", L"ImageFileName", v12 + 1944),
        SymFromName < 0)
    || (SymFromName = Microsoft::Debuggers::CompressedPages::GetFieldInfo(
                        L"nt!B_TREE<_SM_PAGE_KEY,ST_STORE<SM_TRAITS>::_ST_PAGE_ENTRY,4096,NP_CONTEXT>",
                        L"Root",
                        v12 + 2016),
        SymFromName < 0)
    || (SymFromName = Microsoft::Debuggers::CompressedPages::GetFieldInfo(
                        L"nt!MMPAGING_FILE",
                        L"VirtualStorePagefile",
                        v12 + 2088),
        SymFromName < 0) )
  {
LABEL_20:
    __1__unique_ptr_UCacheSymbolDataFieldInfoInternals__1__NoErrorCheckCacheSymbolData_Ver1and2___CompressedPageDataReaderImpl_Ver001_I_CompressedPages_Debuggers_Microsoft__AEAAJXZ_U__default_delete_UCacheSymbolDataFieldInfoInternals__1__NoErrorCheckCacheSymbolData_Ver1and2___CompressedPageDataReaderImpl_Ver001_I_CompressedPages_Debuggers_Microsoft__AEAAJXZ__std___std__QEAA_XZ(&v38);
    goto LABEL_109;
  }
  v13 = (struct _SYMBOL_INFOW *)*((unsigned int *)v12 + 4);
  if ( (_DWORD)v13 != 1 )
  {
    v14 = L"_EX_PUSH_LOCK::Locked";
LABEL_52:
    v15 = 1;
LABEL_53:
    VerbOut(L"CompressedPageDataReaderImpl_Ver001 warning: wrong %s size - actual:%d, expected:%d.\n", v14, v13, v15);
LABEL_54:
    __1__unique_ptr_UCacheSymbolDataFieldInfoInternals__1__NoErrorCheckCacheSymbolData_Ver1and2___CompressedPageDataReaderImpl_Ver001_I_CompressedPages_Debuggers_Microsoft__AEAAJXZ_U__default_delete_UCacheSymbolDataFieldInfoInternals__1__NoErrorCheckCacheSymbolData_Ver1and2___CompressedPageDataReaderImpl_Ver001_I_CompressedPages_Debuggers_Microsoft__AEAAJXZ__std___std__QEAA_XZ(&v38);
    goto LABEL_12;
  }
  v16 = *((unsigned __int16 *)v12 + 26);
  if ( (_WORD)v16 )
  {
    v17 = L"_EX_PUSH_LOCK::Locked";
LABEL_57:
    v18 = v16;
    v19 = L"CompressedPageDataReaderImpl_Ver001 warning: wrong %s bit-field position - actual:%d, expected:%d.\n";
LABEL_58:
    VerbOut(v19, v17, v18, 0);
    goto LABEL_54;
  }
  v20 = *((unsigned __int16 *)v12 + 27);
  if ( (_WORD)v20 != 1 )
  {
    v21 = L"_EX_PUSH_LOCK::Locked";
LABEL_61:
    v22 = 1;
LABEL_62:
    VerbOut(
      L"CompressedPageDataReaderImpl_Ver001 warning: wrong %s bit-field size - actual:%d, expected:%d.\n",
      v21,
      v20,
      v22);
    goto LABEL_54;
  }
  v18 = *((unsigned int *)v12 + 29);
  if ( (_DWORD)v18 )
  {
    v17 = L"nt!VLOCK.Lock";
    v19 = L"CompressedPageDataReaderImpl_Ver001 warning: wrong %s offset - actual:%d, expected:%d.\n";
    goto LABEL_58;
  }
  v13 = (struct _SYMBOL_INFOW *)*((unsigned int *)v12 + 526);
  if ( (_DWORD)v13 != 1 )
  {
    v14 = L"MMPAGING_FILE::VirtualStorePagefile";
    goto LABEL_52;
  }
  if ( *((_WORD *)v12 + 1070) != 6 )
  {
    VerbOut(
      L"CompressedPageDataReaderImpl_Ver001 warning: wrong %s bit-field position - actual:%d, expected:%d.\n",
      L"MMPAGING_FILE::VirtualStorePagefile",
      *((unsigned __int16 *)v12 + 1070),
      6);
    goto LABEL_54;
  }
  v20 = *((unsigned __int16 *)v12 + 1071);
  if ( (_WORD)v20 != 1 )
  {
    v21 = L"MMPAGING_FILE::VirtualStorePagefile";
    goto LABEL_61;
  }
  v13 = (struct _SYMBOL_INFOW *)*((unsigned int *)v12 + 400);
  if ( (_DWORD)v13 != 2 )
  {
    v15 = 2;
    v14 = L"_ST_PAGE_ENTRY::CompressedSize";
    goto LABEL_53;
  }
  v16 = *((unsigned __int16 *)v12 + 818);
  if ( (_WORD)v16 )
  {
    v17 = L"_ST_PAGE_ENTRY::CompressedSize";
    goto LABEL_57;
  }
  v20 = *((unsigned __int16 *)v12 + 819);
  v22 = 12;
  if ( (_WORD)v20 != 12 )
  {
    v21 = L"_ST_PAGE_ENTRY::CompressedSize";
    goto LABEL_62;
  }
  v13 = (struct _SYMBOL_INFOW *)*((unsigned int *)v12 + 436);
  if ( (_DWORD)v13 != 1 )
  {
    v14 = L"_ST_PAGE_ENTRY_FLAGS::LazyRemoved";
    goto LABEL_52;
  }
  v16 = *((unsigned __int16 *)v12 + 890);
  if ( (_WORD)v16 )
  {
    v17 = L"_ST_PAGE_ENTRY_FLAGS::LazyRemoved";
    goto LABEL_57;
  }
  v20 = *((unsigned __int16 *)v12 + 891);
  if ( (_WORD)v20 != 1 )
  {
    v21 = L"_ST_PAGE_ENTRY_FLAGS::LazyRemoved";
    goto LABEL_61;
  }
  v13 = (struct _SYMBOL_INFOW *)*((unsigned int *)v12 + 76);
  if ( (_DWORD)v13 != 4 )
  {
    v15 = 4;
    v14 = L"SMKM_STORE::RegionSize";
    goto LABEL_53;
  }
  v13 = (struct _SYMBOL_INFOW *)*((unsigned int *)v12 + 94);
  if ( (_DWORD)v13 != 4 )
  {
    v15 = 4;
    v14 = L"SMKM_STORE::RegionCountMax";
    goto LABEL_53;
  }
  v13 = (struct _SYMBOL_INFOW *)*((unsigned int *)v12 + 256);
  if ( (_DWORD)v13 != 1 )
  {
    v14 = L"SM_STORE_BASIC_PARAMS::StoreType";
    goto LABEL_52;
  }
  v16 = *((unsigned __int16 *)v12 + 530);
  if ( (_WORD)v16 )
  {
    v17 = L"SM_STORE_BASIC_PARAMS::StoreType";
    goto LABEL_57;
  }
  v20 = *((unsigned __int16 *)v12 + 531);
  v22 = 8;
  if ( (_WORD)v20 != 8 )
  {
    v21 = L"SM_STORE_BASIC_PARAMS::StoreType";
    goto LABEL_62;
  }
  SymFromName = Microsoft::Debuggers::CompressedPages::GetSymFromName(L"nt!MiSystemPartition", v7 + 2, v13);
  if ( SymFromName )
  {
    VerbOut(L"CompressedPageDataReaderImpl_Ver001 warning: failed to get MiSystemPartition symbol.\n");
    goto LABEL_20;
  }
  v40[0] = L"nt";
  v40[1] = L"MiSystemPartition";
  v40[2] = L"Vp";
  v40[3] = v12 + 2160;
  v40[4] = L"nt";
  v40[5] = L"MiSystemPartition.Vp";
  v40[6] = L"PagingFile";
  v40[7] = v12 + 2232;
  v40[8] = L"nt";
  v40[9] = L"SmGlobals.StoreMgr";
  v40[10] = L"FrontEndLock";
  v40[11] = v12 + 2304;
  v40[12] = L"nt";
  v40[13] = L"SmGlobals.StoreMgr";
  v40[14] = L"FrontEnd";
  v40[15] = v12 + 2376;
  v40[16] = L"nt";
  v40[17] = L"SmGlobals.StoreMgr.FrontEnd";
  v40[18] = L"Root";
  v40[19] = v12 + 2448;
  v40[20] = L"nt";
  v40[21] = L"SmGlobals.StoreMgr";
  v40[22] = L"Mgr";
  v40[23] = v12 + 2520;
  v40[24] = L"nt";
  v40[25] = L"SmGlobals";
  v40[26] = L"StoreMgr";
  v40[27] = v12 + 2592;
  v40[28] = L"nt";
  v40[29] = L"SmGlobals.StoreMgr.Mgr";
  v40[30] = L"AllStoresLock";
  v40[31] = v12 + 2664;
  SymFromName = Microsoft::Debuggers::CompressedPages::GetFieldsInfoFromSymbol_Microsoft::Debuggers::CompressedPages::FieldInfoFromSymbolHelper_8_(v40);
  if ( SymFromName )
    goto LABEL_20;
  if ( *(_WORD *)(a1 + 50) == 1 )
  {
    LOBYTE(v36) = 0;
    SymFromName = Microsoft::Debuggers::CompressedPages::GetFieldInfoFromSymbolName(
                    (Microsoft::Debuggers::CompressedPages *)L"nt",
                    L"SmGlobals.StoreMgr.Mgr",
                    L"Stores",
                    (const unsigned __int16 *)v12 + 1368,
                    v36,
                    v37);
    if ( SymFromName )
      goto LABEL_20;
  }
  else
  {
    if ( *(_WORD *)(a1 + 50) != 2 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v24, v23, v25, v26);
    LOBYTE(v36) = 0;
    SymFromName = Microsoft::Debuggers::CompressedPages::GetFieldInfoFromSymbolName(
                    (Microsoft::Debuggers::CompressedPages *)L"nt",
                    L"SmGlobals.StoreMgr.Mgr",
                    L"StoresTable",
                    (const unsigned __int16 *)v12 + 1404,
                    v36,
                    v37);
    if ( SymFromName )
      goto LABEL_20;
    SymFromName = Microsoft::Debuggers::CompressedPages::InternalSymGetTypeFromName(
                    v7->ModBase,
                    L"SMKM_STORE_REF",
                    v7 + 3,
                    v28);
    if ( SymFromName < 0 )
      goto LABEL_20;
  }
  SymFromName = Microsoft::Debuggers::CompressedPages::InternalSymGetTypeFromName(
                  v7->ModBase,
                  L"SM_VIRTUAL_REGION",
                  v7 + 4,
                  v27);
  if ( SymFromName < 0 )
    goto LABEL_20;
  SymFromName = Microsoft::Debuggers::CompressedPages::InternalSymGetTypeFromName(
                  v7->ModBase,
                  L"ST_STORE<SM_TRAITS>::_ST_PAGE_ENTRY",
                  v7 + 5,
                  v29);
  if ( SymFromName < 0 )
    goto LABEL_20;
  v44 = 0;
  LODWORD(v41) = 0;
  v42 = 0;
  v43 = 0;
  SymFromName = Microsoft::Debuggers::CompressedPages::CompressedPageDataReaderImpl_Ver001<unsigned __int64>::GetSmkmFrontendEntryData(
                  v30,
                  v7->ModBase,
                  (unsigned int)&v44,
                  (unsigned int)&v41,
                  (__int64)&v42,
                  (__int64)&v43);
  if ( SymFromName )
    goto LABEL_20;
  *(_DWORD *)(a1 + 280) = *((_DWORD *)v12 + 551);
  *(_DWORD *)(a1 + 284) = *((_DWORD *)v12 + 569);
  *(_DWORD *)(a1 + 288) = *((_DWORD *)v12 + 533);
  *(_DWORD *)(a1 + 292) = *((_DWORD *)v12 + 587);
  *(_DWORD *)(a1 + 296) = *((_DWORD *)v12 + 605);
  *(_DWORD *)(a1 + 300) = *((_DWORD *)v12 + 623);
  *(_DWORD *)(a1 + 304) = *((_DWORD *)v12 + 641);
  *(_DWORD *)(a1 + 308) = *((_DWORD *)v12 + 695);
  *(_DWORD *)(a1 + 312) = *((_DWORD *)v12 + 713);
  *(_DWORD *)(a1 + 316) = *((_DWORD *)v12 + 659);
  *(_DWORD *)(a1 + 320) = *((_DWORD *)v12 + 677);
  *(_DWORD *)(a1 + 324) = *((_DWORD *)v12 + 47);
  *(_DWORD *)(a1 + 328) = *((_DWORD *)v12 + 65);
  *(_DWORD *)(a1 + 332) = *((_DWORD *)v12 + 83);
  *(_DWORD *)(a1 + 336) = *((_DWORD *)v12 + 101);
  *(_DWORD *)(a1 + 340) = *((_DWORD *)v12 + 119);
  *(_DWORD *)(a1 + 344) = *((_DWORD *)v12 + 137);
  *(_DWORD *)(a1 + 348) = *((_DWORD *)v12 + 155);
  *(_DWORD *)(a1 + 352) = *((_DWORD *)v12 + 173);
  *(_DWORD *)(a1 + 356) = *((_DWORD *)v12 + 191);
  *(_DWORD *)(a1 + 360) = *((_DWORD *)v12 + 209);
  *(_DWORD *)(a1 + 364) = *((_DWORD *)v12 + 227);
  *(_DWORD *)(a1 + 368) = *((_DWORD *)v12 + 245);
  *(_DWORD *)(a1 + 372) = *((_DWORD *)v12 + 263);
  *(_DWORD *)(a1 + 376) = *((_DWORD *)v12 + 281);
  *(_DWORD *)(a1 + 380) = *((_DWORD *)v12 + 299);
  *(_DWORD *)(a1 + 384) = *((_DWORD *)v12 + 317);
  *(_DWORD *)(a1 + 388) = *((_DWORD *)v12 + 335);
  *(_DWORD *)(a1 + 396) = *((_DWORD *)v12 + 353);
  *(_DWORD *)(a1 + 400) = *((_DWORD *)v12 + 371);
  *(_DWORD *)(a1 + 404) = *((_DWORD *)v12 + 389);
  *(_DWORD *)(a1 + 408) = *((_DWORD *)v12 + 407);
  *(_DWORD *)(a1 + 412) = *((_DWORD *)v12 + 425);
  *(_DWORD *)(a1 + 416) = *((_DWORD *)v12 + 443);
  *(_DWORD *)(a1 + 424) = *((_DWORD *)v12 + 461);
  *(_DWORD *)(a1 + 428) = *((_DWORD *)v12 + 479);
  *(_DWORD *)(a1 + 432) = *((_DWORD *)v12 + 497);
  *(_DWORD *)(a1 + 436) = *((_DWORD *)v12 + 515);
  *(_DWORD *)(a1 + 440) = (_DWORD)v41;
  *(_DWORD *)(a1 + 444) = v42;
  *(_DWORD *)(a1 + 448) = v43;
  *(_DWORD *)(a1 + 504) = v7[3].Size;
  *(_DWORD *)(a1 + 512) = v7[4].Size;
  *(_DWORD *)(a1 + 532) = v7[5].Size;
  *(_DWORD *)(a1 + 520) = *((_DWORD *)v12 + 382);
  *(_DWORD *)(a1 + 524) = *((_DWORD *)v12 + 400);
  *(_DWORD *)(a1 + 528) = *((_DWORD *)v12 + 436);
  *(_DWORD *)(a1 + 508) = *((_DWORD *)v12 + 40);
  *(_DWORD *)(a1 + 540) = v44;
  *(_OWORD *)(a1 + 192) = *(_OWORD *)&v7[2].SizeOfStruct;
  *(_OWORD *)(a1 + 208) = *(_OWORD *)&v7[2].Reserved[1];
  *(_OWORD *)(a1 + 224) = *(_OWORD *)&v7[2].ModBase;
  *(_OWORD *)(a1 + 240) = *(_OWORD *)&v7[2].Value;
  *(_OWORD *)(a1 + 256) = *(_OWORD *)&v7[2].Register;
  *(_QWORD *)(a1 + 272) = *(_QWORD *)&v7[2].MaxNameLen;
  *(_OWORD *)(a1 + 104) = *(_OWORD *)&v7->SizeOfStruct;
  *(_OWORD *)(a1 + 120) = *(_OWORD *)&v7->Reserved[1];
  *(_OWORD *)(a1 + 136) = *(_OWORD *)&v7->ModBase;
  *(_OWORD *)(a1 + 152) = *(_OWORD *)&v7->Value;
  *(_OWORD *)(a1 + 168) = *(_OWORD *)&v7->Register;
  *(_QWORD *)(a1 + 184) = *(_QWORD *)&v7->MaxNameLen;
  if ( !*(_QWORD *)(a1 + 160) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v32, v31, v33, v34);
  __1__unique_ptr_UCacheSymbolDataFieldInfoInternals__1__NoErrorCheckCacheSymbolData_Ver1and2___CompressedPageDataReaderImpl_Ver001_I_CompressedPages_Debuggers_Microsoft__AEAAJXZ_U__default_delete_UCacheSymbolDataFieldInfoInternals__1__NoErrorCheckCacheSymbolData_Ver1and2___CompressedPageDataReaderImpl_Ver001_I_CompressedPages_Debuggers_Microsoft__AEAAJXZ__std___std__QEAA_XZ(&v38);
  SymFromName = 0;
LABEL_109:
  __1__unique_ptr_UCacheSymbolDataSymbolInfoInternals__1__NoErrorCheckCacheSymbolData_Ver1and2___CompressedPageDataReaderImpl_Ver001__K_CompressedPages_Debuggers_Microsoft__AEAAJXZ_U__default_delete_UCacheSymbolDataSymbolInfoInternals__1__NoErrorCheckCacheSymbolData_Ver1and2___CompressedPageDataReaderImpl_Ver001__K_CompressedPages_Debuggers_Microsoft__AEAAJXZ__std___std__QEAA_XZ(&v39);
  return (unsigned int)SymFromName;
}

```

## disassembly

```asm
0x18038195c  push    rbp
0x18038195e  push    rbx
0x18038195f  push    rsi
0x180381960  push    rdi
0x180381961  push    r12
0x180381963  push    r13
0x180381965  push    r14
0x180381967  push    r15
0x180381969  lea     rbp, [rsp-58h]
0x18038196e  sub     rsp, 158h
0x180381975  mov     [rbp+90h+var_50], 0FFFFFFFFFFFFFFFEh
0x18038197d  mov     r14, rcx
0x180381980  movzx   eax, word ptr [rcx+32h]
0x180381984  mov     r13d, 1
0x18038198a  sub     ax, r13w
0x18038198e  cmp     ax, r13w
0x180381992  jbe     short loc_180381999
0x180381994  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180381999  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1803819a0  mov     ebx, 210h
0x1803819a5  mov     ecx, ebx; unsigned __int64
0x1803819a7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1803819ac  mov     rsi, rax
0x1803819af  mov     [rbp+90h+arg_0], rax
0x1803819b6  xor     r12d, r12d
0x1803819b9  test    rax, rax
0x1803819bc  jz      loc_180381A55
0x1803819c2  mov     r8d, ebx; Size
0x1803819c5  xor     edx, edx; Val
0x1803819c7  mov     rcx, rax; void *
0x1803819ca  call    memset
0x1803819cf  lea     edi, [r12+58h]
0x1803819d4  mov     r8d, edi; Size
0x1803819d7  xor     edx, edx; Val
0x1803819d9  mov     rcx, rsi; void *
0x1803819dc  call    memset
0x1803819e1  mov     [rsi], edi
0x1803819e3  lea     rcx, [rsi+5Ch]; void *
0x1803819e7  lea     ebx, [rdi-4]
0x1803819ea  mov     r8d, ebx; Size
0x1803819ed  xor     edx, edx; Val
0x1803819ef  call    memset
0x1803819f4  mov     [rsi+58h], edi
0x1803819f7  lea     rcx, [rsi+0B4h]; void *
0x1803819fe  mov     r8d, ebx; Size
0x180381a01  xor     edx, edx; Val
0x180381a03  call    memset
0x180381a08  mov     [rsi+0B0h], edi
0x180381a0e  lea     rcx, [rsi+10Ch]; void *
0x180381a15  mov     r8d, ebx; Size
0x180381a18  xor     edx, edx; Val
0x180381a1a  call    memset
0x180381a1f  mov     [rsi+108h], edi
0x180381a25  lea     rcx, [rsi+164h]; void *
0x180381a2c  mov     r8d, ebx; Size
0x180381a2f  xor     edx, edx; Val
0x180381a31  call    memset
0x180381a36  mov     [rsi+160h], edi
0x180381a3c  lea     rcx, [rsi+1BCh]; void *
0x180381a43  mov     r8d, ebx; Size
0x180381a46  xor     edx, edx; Val
0x180381a48  call    memset
0x180381a4d  mov     [rsi+1B8h], edi
0x180381a53  jmp     short loc_180381A58
0x180381a55  mov     rsi, r12
0x180381a58  mov     [rsp+190h+var_158], rsi
0x180381a5d  test    rsi, rsi
0x180381a60  jz      loc_180381B12
0x180381a66  mov     rdx, rsi; Symbol
0x180381a69  lea     rcx, aNtSmglobals; "nt!SmGlobals"
0x180381a70  call    ?GetSymFromName@CompressedPages@Debuggers@Microsoft@@YAJPEBGPEAU_SYMBOL_INFOW@@@Z; Microsoft::Debuggers::CompressedPages::GetSymFromName(ushort const *,_SYMBOL_INFOW *)
0x180381a75  mov     ebx, eax
0x180381a77  test    eax, eax
0x180381a79  jz      short loc_180381A8C
0x180381a7b  lea     rcx, aCompressedpage_25; "CompressedPageDataReaderImpl_Ver001 war"...
0x180381a82  call    ?VerbOut@@YAXPEBGZZ; VerbOut(ushort const *,...)
0x180381a87  jmp     loc_18038271A
0x180381a8c  lea     r8, [rsi+58h]; Symbol
0x180381a90  lea     rdx, aSmPageKey; "_SM_PAGE_KEY"
0x180381a97  mov     rcx, [rsi+20h]; BaseOfDll
0x180381a9b  call    ?InternalSymGetTypeFromName@CompressedPages@Debuggers@Microsoft@@YAJ_KPEBGPEAU_SYMBOL_INFOW@@@Z; Microsoft::Debuggers::CompressedPages::InternalSymGetTypeFromName(unsigned __int64,ushort const *,_SYMBOL_INFOW *)
0x180381aa0  mov     ebx, eax
0x180381aa2  test    eax, eax
0x180381aa4  js      loc_18038271A
0x180381aaa  mov     edx, [rsi+74h]
0x180381aad  mov     r15d, 4
0x180381ab3  cmp     edx, r15d
0x180381ab6  jz      short loc_180381AD1
0x180381ab8  mov     r8d, r15d
0x180381abb  lea     rcx, aCompressedpage_58; "CompressedPageDataReaderImpl_Ver001 war"...
0x180381ac2  call    ?VerbOut@@YAXPEBGZZ; VerbOut(ushort const *,...)
0x180381ac7  mov     ebx, 80004005h
0x180381acc  jmp     loc_18038271A
0x180381ad1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180381ad8  mov     ebx, 0B40h
0x180381add  mov     ecx, ebx; unsigned __int64
0x180381adf  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180381ae4  mov     rdi, rax
0x180381ae7  test    rax, rax
0x180381aea  jz      short loc_180381AFB
0x180381aec  mov     r8d, ebx; Size
0x180381aef  xor     edx, edx; Val
0x180381af1  mov     rcx, rax; void *
0x180381af4  call    memset
0x180381af9  jmp     short loc_180381AFE
0x180381afb  mov     rdi, r12
0x180381afe  mov     [rsp+190h+var_160], rdi
0x180381b03  test    rdi, rdi
0x180381b06  jnz     short loc_180381B1C
0x180381b08  lea     rcx, [rsp+190h+var_160]
0x180381b0d  call    ??1?$unique_ptr@UCacheSymbolDataFieldInfoInternals@?1??NoErrorCheckCacheSymbolData_Ver1and2@?$CompressedPageDataReaderImpl_Ver001@I@CompressedPages@Debuggers@Microsoft@@AEAAJXZ@U?$default_delete@UCacheSymbolDataFieldInfoInternals@?1??NoErrorCheckCacheSymbolData_Ver1and2@?$CompressedPageDataReaderImpl_Ver001@I@CompressedPages@Debuggers@Microsoft@@AEAAJXZ@@std@@@std@@QEAA@XZ; std::unique_ptr<`Microsoft::Debuggers::CompressedPages::CompressedPageDataReaderImpl_Ver001<uint>::NoErrorCheckCacheSymbolData_Ver1and2(void)'::`2'::CacheSymbolDataFieldInfoInternals,std::default_delete<`Microsoft::Debuggers::CompressedPages::CompressedPageDataReaderImpl_Ver001<uint>::NoErrorCheckCacheSymbolData_Ver1and2(void)'::`2'::CacheSymbolDataFieldInfoInternals>>::~unique_ptr<`Microsoft::Debuggers::CompressedPages::CompressedPageDataReaderImpl_Ver001<uint>::NoErrorCheckCacheSymbolData_Ver1and2(void)'::`2'::CacheSymbolDataFieldInfoInternals,std::default_delete<`Microsoft::Debuggers::CompressedPages::CompressedPageDataReaderImpl_Ver001<uint>::NoErrorCheckCacheSymbolData_Ver1and2(void)'::`2'::CacheSymbolDataFieldInfoInternals>>(void)
0x180381b12  mov     ebx, 8007000Eh
0x180381b17  jmp     loc_18038271A
0x180381b1c  mov     r8, rdi
0x180381b1f  lea     rdx, aLocked; "Locked"
0x180381b26  lea     rcx, aNtExPushLock; "nt!_EX_PUSH_LOCK"
0x180381b2d  call    Microsoft__Debuggers__CompressedPages__GetFieldInfo
0x180381b32  mov     ebx, eax
0x180381b34  test    eax, eax
0x180381b36  jns     short loc_180381B47
0x180381b38  lea     rcx, [rsp+190h+var_160]
0x180381b3d  call    ??1?$unique_ptr@UCacheSymbolDataFieldInfoInternals@?1??NoErrorCheckCacheSymbolData_Ver1and2@?$CompressedPageDataReaderImpl_Ver001@I@CompressedPages@Debuggers@Microsoft@@AEAAJXZ@U?$default_delete@UCacheSymbolDataFieldInfoInternals@?1??NoErrorCheckCacheSymbolData_Ver1and2@?$CompressedPageDataReaderImpl_Ver001@I@CompressedPages@Debuggers@Microsoft@@AEAAJXZ@@std@@@std@@QEAA@XZ; std::unique_ptr<`Microsoft::Debuggers::CompressedPages::CompressedPageDataReaderImpl_Ver001<uint>::NoErrorCheckCacheSymbolData_Ver1and2(void)'::`2'::CacheSymbolDataFieldInfoInternals,std::default_delete<`Microsoft::Debuggers::CompressedPages::CompressedPageDataReaderImpl_Ver001<uint>::NoErrorCheckCacheSymbolData_Ver1and2(void)'::`2'::CacheSymbolDataFieldInfoInternals>>::~unique_ptr<`Microsoft::Debuggers::CompressedPages::CompressedPageDataReaderImpl_Ver001<uint>::NoErrorCheckCacheSymbolData_Ver1and2(void)'::`2'::CacheSymbolDataFieldInfoInternals,std::default_delete<`Microsoft::Debuggers::CompressedPages::CompressedPageDataReaderImpl_Ver001<uint>::NoErrorCheckCacheSymbolData_Ver1and2(void)'::`2'::CacheSymbolDataFieldInfoInternals>>(void)
0x180381b42  jmp     loc_18038271A
0x180381b47  lea     r8, [rdi+48h]
0x180381b4b  lea     rdx, aLock; "Lock"
0x180381b52  lea     rcx, aNtVlock; "nt!VLOCK"
0x180381b59  call    Microsoft__Debuggers__CompressedPages__GetFieldInfo
0x180381b5e  mov     ebx, eax
0x180381b60  test    eax, eax
0x180381b62  js      short loc_180381B38
0x180381b64  lea     r8, [rdi+90h]
0x180381b6b  lea     rdx, aStore_0; "Store"
0x180381b72  lea     rcx, aNtSmkmStoreRef; "nt!SMKM_STORE_REF"
0x180381b79  call    Microsoft__Debuggers__CompressedPages__GetFieldInfo
0x180381b7e  mov     ebx, eax
0x180381b80  test    eax, eax
0x180381b82  js      short loc_180381B38
0x180381b84  lea     r8, [rdi+0D8h]
0x180381b8b  lea     rdx, aAddremovelock; "AddRemoveLock"
0x180381b92  lea     rcx, aNtSmkmStoreRef; "nt!SMKM_STORE_REF"
0x180381b99  call    Microsoft__Debuggers__CompressedPages__GetFieldInfo
0x180381b9e  mov     ebx, eax
0x180381ba0  test    eax, eax
0x180381ba2  js      short loc_180381B38
0x180381ba4  lea     r8, [rdi+120h]
0x180381bab  lea     rdx, aRegionsize; "RegionSize"
0x180381bb2  lea     rcx, aNtSmkmStoreSmT; "nt!SMKM_STORE<SM_TRAITS>"
0x180381bb9  call    Microsoft__Debuggers__CompressedPages__GetFieldInfo
0x180381bbe  mov     ebx, eax
0x180381bc0  test    eax, eax
0x180381bc2  js      loc_180381B38
0x180381bc8  lea     r8, [rdi+168h]
0x180381bcf  lea     rdx, aRegioncountmax; "RegionCountMax"
0x180381bd6  lea     rcx, aNtSmkmStoreSmT; "nt!SMKM_STORE<SM_TRAITS>"
0x180381bdd  call    Microsoft__Debuggers__CompressedPages__GetFieldInfo
0x180381be2  mov     ebx, eax
0x180381be4  test    eax, eax
0x180381be6  js      loc_180381B38
0x180381bec  lea     r8, [rdi+1B0h]
0x180381bf3  lea     rdx, aStore_0; "Store"
0x180381bfa  lea     rcx, aNtSmkmStoreSmT; "nt!SMKM_STORE<SM_TRAITS>"
0x180381c01  call    Microsoft__Debuggers__CompressedPages__GetFieldInfo
0x180381c06  mov     ebx, eax
0x180381c08  test    eax, eax
0x180381c0a  js      loc_180381B38
0x180381c10  lea     r8, [rdi+1F8h]
0x180381c17  lea     rdx, aVirtualregions; "VirtualRegions"
0x180381c1e  lea     rcx, aNtSmkmStoreSmT; "nt!SMKM_STORE<SM_TRAITS>"
0x180381c25  call    Microsoft__Debuggers__CompressedPages__GetFieldInfo
0x180381c2a  mov     ebx, eax
0x180381c2c  test    eax, eax
0x180381c2e  js      loc_180381B38
0x180381c34  lea     r8, [rdi+240h]
0x180381c3b  lea     rdx, aStorelock; "StoreLock"
0x180381c42  lea     rcx, aNtSmkmStoreSmT; "nt!SMKM_STORE<SM_TRAITS>"
0x180381c49  call    Microsoft__Debuggers__CompressedPages__GetFieldInfo
0x180381c4e  mov     ebx, eax
0x180381c50  test    eax, eax
0x180381c52  js      loc_180381B38
0x180381c58  lea     r8, [rdi+288h]
0x180381c5f  lea     rdx, aUserdata; "UserData"
0x180381c66  lea     rcx, aNtStStoreSmTra_3; "nt!ST_STORE<SM_TRAITS>"
0x180381c6d  call    Microsoft__Debuggers__CompressedPages__GetFieldInfo
0x180381c72  mov     ebx, eax
0x180381c74  test    eax, eax
0x180381c76  js      loc_180381B38
0x180381c7c  lea     r8, [rdi+2D0h]
0x180381c83  lea     rdx, aProperties; "Properties"
0x180381c8a  lea     rcx, aNtStStoreSmTra_3; "nt!ST_STORE<SM_TRAITS>"
0x180381c91  call    Microsoft__Debuggers__CompressedPages__GetFieldInfo
0x180381c96  mov     ebx, eax
0x180381c98  test    eax, eax
0x180381c9a  js      loc_180381B38
0x180381ca0  lea     r8, [rdi+318h]
0x180381ca7  lea     rdx, aVirtualaddress; "VirtualAddress"
0x180381cae  lea     rcx, aNtSmVirtualReg; "nt!SM_VIRTUAL_REGION"
0x180381cb5  call    Microsoft__Debuggers__CompressedPages__GetFieldInfo
0x180381cba  mov     ebx, eax
0x180381cbc  test    eax, eax
0x180381cbe  js      loc_180381B38
0x180381cc4  lea     r8, [rdi+360h]
0x180381ccb  lea     rdx, aParams; "Params"
0x180381cd2  lea     rcx, aNtStProperties; "nt!ST_PROPERTIES"
0x180381cd9  call    Microsoft__Debuggers__CompressedPages__GetFieldInfo
0x180381cde  mov     ebx, eax
0x180381ce0  test    eax, eax
0x180381ce2  js      loc_180381B38
0x180381ce8  lea     r8, [rdi+3A8h]
0x180381cef  lea     rdx, aStore_0; "Store"
0x180381cf6  lea     rcx, aNtStParameters; "nt!ST_PARAMETERS"
0x180381cfd  call    Microsoft__Debuggers__CompressedPages__GetFieldInfo
0x180381d02  mov     ebx, eax
0x180381d04  test    eax, eax
0x180381d06  js      loc_180381B38
0x180381d0c  lea     r8, [rdi+3F0h]
0x180381d13  lea     rdx, aStoretype; "StoreType"
0x180381d1a  lea     rcx, aNtSmStoreBasic; "nt!SM_STORE_BASIC_PARAMS"
0x180381d21  call    Microsoft__Debuggers__CompressedPages__GetFieldInfo
0x180381d26  mov     ebx, eax
0x180381d28  test    eax, eax
0x180381d2a  js      loc_180381B38
0x180381d30  lea     r8, [rdi+438h]
0x180381d37  lea     rdx, aCompressionfor; "CompressionFormat"
0x180381d3e  lea     rcx, aNtStStoreSmTra; "nt!ST_STORE<SM_TRAITS>::_ST_DATA_MGR"
0x180381d45  call    Microsoft__Debuggers__CompressedPages__GetFieldInfo
0x180381d4a  mov     ebx, eax
0x180381d4c  test    eax, eax
0x180381d4e  js      loc_180381B38
0x180381d54  lea     r8, [rdi+480h]
0x180381d5b  lea     rdx, aOffsetmask; "OffsetMask"
0x180381d62  lea     rcx, aNtStProperties; "nt!ST_PROPERTIES"
0x180381d69  call    Microsoft__Debuggers__CompressedPages__GetFieldInfo
0x180381d6e  mov     ebx, eax
0x180381d70  test    eax, eax
0x180381d72  js      loc_180381B38
0x180381d78  lea     r8, [rdi+4C8h]
0x180381d7f  lea     rdx, aRegionshift; "RegionShift"
0x180381d86  lea     rcx, aNtStProperties; "nt!ST_PROPERTIES"
0x180381d8d  call    Microsoft__Debuggers__CompressedPages__GetFieldInfo
0x180381d92  mov     ebx, eax
0x180381d94  test    eax, eax
0x180381d96  js      loc_180381B38
0x180381d9c  lea     r8, [rdi+510h]
0x180381da3  lea     rdx, aPagetree; "PageTree"
0x180381daa  lea     rcx, aNtStStoreSmTra; "nt!ST_STORE<SM_TRAITS>::_ST_DATA_MGR"
0x180381db1  call    Microsoft__Debuggers__CompressedPages__GetFieldInfo
0x180381db6  mov     ebx, eax
0x180381db8  test    eax, eax
0x180381dba  js      loc_180381B38
0x180381dc0  lea     r8, [rdi+558h]
0x180381dc7  lea     rdx, aStore_0; "Store"
0x180381dce  lea     rcx, aNtStStoreSmTra; "nt!ST_STORE<SM_TRAITS>::_ST_DATA_MGR"
0x180381dd5  call    Microsoft__Debuggers__CompressedPages__GetFieldInfo
0x180381dda  mov     ebx, eax
0x180381ddc  test    eax, eax
0x180381dde  js      loc_180381B38
0x180381de4  lea     r8, [rdi+5A0h]
0x180381deb  lea     rdx, aKey; "Key"
0x180381df2  lea     rcx, aNtStStoreSmTra_2; "nt!ST_STORE<SM_TRAITS>::_ST_PAGE_ENTRY"
0x180381df9  call    Microsoft__Debuggers__CompressedPages__GetFieldInfo
0x180381dfe  mov     ebx, eax
0x180381e00  test    eax, eax
0x180381e02  js      loc_180381B38
0x180381e08  lea     r8, [rdi+5E8h]
0x180381e0f  lea     rdx, aOffset; "Offset"
0x180381e16  lea     rcx, aNtStStoreSmTra_2; "nt!ST_STORE<SM_TRAITS>::_ST_PAGE_ENTRY"
0x180381e1d  call    Microsoft__Debuggers__CompressedPages__GetFieldInfo
0x180381e22  mov     ebx, eax
0x180381e24  test    eax, eax
0x180381e26  js      loc_180381B38
0x180381e2c  lea     r8, [rdi+630h]
0x180381e33  lea     rdx, aCompressedsize; "CompressedSize"
0x180381e3a  lea     rcx, aNtStStoreSmTra_2; "nt!ST_STORE<SM_TRAITS>::_ST_PAGE_ENTRY"
0x180381e41  call    Microsoft__Debuggers__CompressedPages__GetFieldInfo
0x180381e46  mov     ebx, eax
0x180381e48  test    eax, eax
0x180381e4a  js      loc_180381B38
0x180381e50  lea     r8, [rdi+678h]
0x180381e57  lea     rdx, aFlags; "Flags"
0x180381e5e  lea     rcx, aNtStStoreSmTra_2; "nt!ST_STORE<SM_TRAITS>::_ST_PAGE_ENTRY"
0x180381e65  call    Microsoft__Debuggers__CompressedPages__GetFieldInfo
0x180381e6a  mov     ebx, eax
0x180381e6c  test    eax, eax
0x180381e6e  js      loc_180381B38
0x180381e74  lea     r8, [rdi+6C0h]
0x180381e7b  lea     rdx, aLazyremoved; "LazyRemoved"
0x180381e82  lea     rcx, aNtStStoreSmTra_0; "nt!ST_STORE<SM_TRAITS>::_ST_PAGE_ENTRY_"...
0x180381e89  call    Microsoft__Debuggers__CompressedPages__GetFieldInfo
0x180381e8e  mov     ebx, eax
0x180381e90  test    eax, eax
0x180381e92  js      loc_180381B38
0x180381e98  lea     r8, [rdi+708h]
0x180381e9f  lea     rdx, aFlink; "Flink"
0x180381ea6  lea     rcx, aNtListEntry; "nt!_LIST_ENTRY"
0x180381ead  call    Microsoft__Debuggers__CompressedPages__GetFieldInfo
0x180381eb2  mov     ebx, eax
0x180381eb4  test    eax, eax
0x180381eb6  js      loc_180381B38
0x180381ebc  lea     r8, [rdi+750h]
0x180381ec3  lea     rdx, aActiveprocessl; "ActiveProcessLinks"
  ... truncated ...
```
