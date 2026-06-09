# Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile::Merge(HKEY__ *,ushort const *,ushort const *,ushort const *,bool,bool,ushort *,int)

- ea: `0x1400222b0`
- end: `0x140022d03`
- name: `?Merge@CMergeConfigFile@BindingRedirects@PkgDef@VisualStudio@Microsoft@@QEAAJPEAUHKEY__@@PEBG11_N2PEAGH@Z`
- size: `2643`
- prototype: `__int64 __usercall@<rax>(Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile *__hidden this@<rcx>, HKEY@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, bool, bool, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140021f90`

## callees

- `0x140001020`
- `0x140002c10`
- `0x140002f00`
- `0x140003070`
- `0x140003160`
- `0x140004950`
- `0x1400095f4`
- `0x140009b10`
- `0x140009d80`
- `0x1400102a0`
- `0x1400144d8`
- `0x1400222b0`
- `0x140022d04`
- `0x140022db0`
- `0x14002fa90`
- `0x140033ab0`
- `0x1400464b0`
- `0x140046514`
- `0x14004d378`
- `0x14004d948`
- `0x14004dabc`
- `0x14004ddf4`
- `0x14004dea4`
- `0x14004df90`
- `0x14004e0f0`
- `0x14004f388`
- `0x140053724`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x140022bdd`
- `KERNEL32!CreateFileW` at `0x140022bdd`
- `OLEAUT32!__imp_SysFreeString` at `0x140022591`
- `OLEAUT32!__imp_SysFreeString` at `0x1400225a0`
- `OLEAUT32!__imp_SysFreeString` at `0x140022591`
- `OLEAUT32!__imp_SysFreeString` at `0x1400225a0`
- `OLEAUT32!__imp_VariantClear` at `0x14002293e`
- `OLEAUT32!__imp_VariantClear` at `0x140022991`
- `OLEAUT32!__imp_VariantClear` at `0x140022a4c`
- `OLEAUT32!__imp_VariantClear` at `0x140022a67`
- `OLEAUT32!__imp_VariantClear` at `0x140022b25`
- `OLEAUT32!__imp_VariantClear` at `0x140022b45`
- `OLEAUT32!__imp_VariantClear` at `0x14002293e`
- `OLEAUT32!__imp_VariantClear` at `0x140022991`
- `OLEAUT32!__imp_VariantClear` at `0x140022a4c`
- `OLEAUT32!__imp_VariantClear` at `0x140022a67`
- `OLEAUT32!__imp_VariantClear` at `0x140022b25`
- `OLEAUT32!__imp_VariantClear` at `0x140022b45`
- `SHLWAPI!PathFindFileNameW` at `0x140022391`
- `SHLWAPI!PathFindFileNameW` at `0x140022391`
- `SHLWAPI!PathIsRelativeW` at `0x14002284b`
- `SHLWAPI!PathIsRelativeW` at `0x14002284b`
- `SHLWAPI!PathFileExistsW` at `0x14002236c`
- `SHLWAPI!PathFileExistsW` at `0x1400225fc`
- `SHLWAPI!PathFileExistsW` at `0x14002285a`
- `SHLWAPI!PathFileExistsW` at `0x14002236c`
- `SHLWAPI!PathFileExistsW` at `0x1400225fc`
- `SHLWAPI!PathFileExistsW` at `0x14002285a`
- `SHLWAPI!PathIsDirectoryW` at `0x14002237d`
- `SHLWAPI!PathIsDirectoryW` at `0x14002237d`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x1400228d5`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x14002296c`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x1400228d5`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x14002296c`
- `SHELL32!SHCreateDirectoryExW` at `0x14002286e`
- `SHELL32!SHCreateDirectoryExW` at `0x14002286e`

## string_xrefs

- `0x1400223d9`: `.config`
- `0x140022c04`: `Configuration file to be used for CLR initialization`
- `0x1400224f8`: `Configuration is Volatile.`
- `0x140022adf`: `Error merging configuration file`
- `0x140022bf3`: `Failed to acquire lock on application config file`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile::Merge(
        Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        bool a6,
        bool a7,
        unsigned __int16 *a8)
{
  Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile *v10; // r13
  unsigned __int16 *v11; // r12
  LPCWSTR *v12; // rbx
  _QWORD *v13; // rdx
  LPCWSTR v14; // rdi
  LPWSTR FileNameW; // r8
  __int64 v16; // r8
  int v17; // eax
  __int64 v18; // rdi
  signed int TempConfigFilePath; // r14d
  volatile signed __int32 *v20; // rbx
  __int64 v21; // r8
  struct ATL::IAtlStringMgr *Instance; // rax
  const WCHAR *v23; // rbx
  IStream *v24; // rdx
  BSTR v25; // rdx
  int v26; // r15d
  Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile *v27; // rcx
  union _ULARGE_INTEGER *v28; // r8
  union _ULARGE_INTEGER *v29; // r9
  Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile *v30; // rcx
  union _ULARGE_INTEGER *v31; // r8
  union _ULARGE_INTEGER *v32; // r9
  int RegistryEntries; // eax
  Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile *v34; // rcx
  int inited; // esi
  LPCWSTR *v36; // r12
  Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile *v37; // rcx
  struct ISAXErrorHandler *v38; // r8
  union _ULARGE_INTEGER v39; // r15
  int v40; // r9d
  LPCWSTR v41; // rdx
  int v42; // eax
  LPCWSTR v43; // rdx
  LPCWSTR v44; // rdx
  LPCWSTR v45; // rdx
  LPCWSTR v46; // rdx
  HANDLE FileW; // rax
  unsigned __int64 v48; // r8
  __int64 v49; // rcx
  signed __int64 v50; // rdx
  unsigned __int16 v51; // ax
  unsigned __int16 *v52; // rax
  IStream *pstmTemplate; // [rsp+20h] [rbp-D9h]
  LPCWSTR v55; // [rsp+40h] [rbp-B9h] BYREF
  Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile *v56; // [rsp+48h] [rbp-B1h]
  LPCWSTR pszPath; // [rsp+50h] [rbp-A9h] BYREF
  LPCWSTR *v58; // [rsp+58h] [rbp-A1h]
  __int64 v59; // [rsp+60h] [rbp-99h] BYREF
  union _ULARGE_INTEGER v60; // [rsp+68h] [rbp-91h] BYREF
  unsigned __int16 *v61; // [rsp+70h] [rbp-89h]
  VARIANTARG pvarg; // [rsp+78h] [rbp-81h] BYREF
  VARIANTARG v63; // [rsp+90h] [rbp-69h] BYREF
  VARIANTARG v64; // [rsp+B0h] [rbp-49h] BYREF
  BSTR bstrString; // [rsp+D0h] [rbp-29h] BYREF
  struct IMXWriter *v66; // [rsp+D8h] [rbp-21h] BYREF
  struct ISAXContentHandler *v67; // [rsp+E0h] [rbp-19h] BYREF
  struct ISAXXMLReader *v68; // [rsp+E8h] [rbp-11h] BYREF
  IStream *ppstm; // [rsp+F0h] [rbp-9h] BYREF

  v10 = this;
  v56 = this;
  v11 = a8;
  v61 = a8;
  if ( !a2 || !a3 || !a4 || !a5 || !a8 )
    return 2147500035LL;
  *a8 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v59,
    a4);
  v12 = (LPCWSTR *)((char *)v10 + 16);
  ATL::CSimpleStringT<unsigned short,0>::operator=((char *)v10 + 16, &v59);
  v13 = (_QWORD *)(v59 - 24);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v59 - 24 + 16), 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 8LL))(*v13);
  }
  if ( !PathFileExistsW(*v12) )
    return 2147942487LL;
  if ( PathIsDirectoryW(*v12) )
    return 2147942487LL;
  v14 = *v12;
  FileNameW = PathFindFileNameW(*v12);
  if ( !*FileNameW )
    return 2147942487LL;
  v16 = FileNameW - v14;
  if ( (_DWORD)v16 == -1 )
    return 2147942487LL;
  v59 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
    (char *)v10 + 16,
    &v59,
    v16,
    (unsigned int)(*((_DWORD *)*v12 - 4) - v16));
  ATL::CSimpleStringT<unsigned short,0>::Append(&v59, L".config", 7);
  v58 = (LPCWSTR *)((char *)v10 + 24);
  ATL::CSimpleStringT<unsigned short,0>::operator=((char *)v10 + 24, (char *)v10 + 16);
  v17 = ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::RemoveFileSpec((char *)v10 + 24);
  v18 = v59;
  if ( !v17 )
  {
    TempConfigFilePath = -2147418113;
    goto LABEL_157;
  }
  v20 = (volatile signed __int32 *)ATL::CSimpleStringT<unsigned short,0>::CloneData(*((_QWORD *)v10 + 3) - 24LL);
  v60.QuadPart = (ULONGLONG)(v20 + 6);
  ATL::CSimpleStringT<unsigned short,0>::operator=(
    &Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase::s_strApplicationDirectory,
    &v60);
  if ( _InterlockedExchangeAdd(v20 + 4, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v20 + 8LL))(*(_QWORD *)v20, v20);
  }
  if ( !(unsigned int)ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Append(
                        (char *)v10 + 24,
                        v18) )
  {
    TempConfigFilePath = -2147024882;
    goto LABEL_157;
  }
  *(_QWORD *)v10 = a2;
  *((_BYTE *)v10 + 40) = a6;
  *((_BYTE *)v10 + 41) = a7;
  v21 = -1;
  do
    ++v21;
  while ( a5[v21] );
  ATL::CSimpleStringT<unsigned short,0>::SetString((char *)v10 + 8, a5);
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  v23 = (const WCHAR *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                      + 24);
  pszPath = v23;
  if ( *((_BYTE *)v10 + 41) )
  {
    TempConfigFilePath = Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile::GetTempConfigFilePath(
                           v10,
                           v18,
                           &pszPath);
    if ( TempConfigFilePath < 0 )
    {
      v23 = pszPath;
      goto LABEL_155;
    }
    CLogger::LogInfo(L"Configuration is Volatile.", 0, 0);
    goto LABEL_32;
  }
  bstrString = 0;
  TempConfigFilePath = util_CalculateAppDataFolder(28, a3, &bstrString);
  if ( TempConfigFilePath < 0 )
  {
LABEL_30:
    SysFreeString(bstrString);
    goto LABEL_155;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &ppstm,
    bstrString);
  ATL::CSimpleStringT<unsigned short,0>::operator=(&pszPath, &ppstm);
  v24 = ppstm - 3;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)&ppstm[-1], 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*((void (__fastcall **)(struct IStreamVtbl *))v24->lpVtbl->QueryInterface + 1))(v24->lpVtbl);
  }
  if ( !(unsigned int)ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Append(
                        &pszPath,
                        v18) )
  {
    TempConfigFilePath = -2147024882;
    v23 = pszPath;
    goto LABEL_30;
  }
  SysFreeString(bstrString);
LABEL_32:
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &bstrString,
    L"\\");
  EnsureThatStringEndWith((char *)v10 + 8, &bstrString);
  v25 = bstrString - 12;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)bstrString - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v25 + 8LL))(*(_QWORD *)v25);
  }
  v26 = 0;
  v23 = pszPath;
  if ( pszPath
    && PathFileExistsW(pszPath)
    && !*((_BYTE *)v10 + 40)
    && (!Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile::GetFileTime(
           v27,
           v23,
           v28,
           v29,
           (union _ULARGE_INTEGER *)&bstrString)
     || !Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile::GetFileTime(
           v30,
           *((const unsigned __int16 **)v10 + 3),
           v31,
           v32,
           &v60)
     || (unsigned __int64)bstrString >= v60.QuadPart) )
  {
    goto LABEL_143;
  }
  RegistryEntries = Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile::ReadRegistryEntries(v10);
  if ( RegistryEntries < 0
    || (_mm_lfence(),
        RegistryEntries = Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile::CoalesceBindingRedirects(v10),
        RegistryEntries < 0)
    || (_mm_lfence(),
        RegistryEntries = Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile::CoalesceCodeBases(v10),
        RegistryEntries < 0)
    || (_mm_lfence(),
        RegistryEntries = Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile::CoalesceBindingRedirectsCodeBases(v10),
        RegistryEntries < 0) )
  {
    TempConfigFilePath = RegistryEntries;
    goto LABEL_155;
  }
  _mm_lfence();
  while ( 1 )
  {
    if ( !v23 )
    {
      inited = -2147024809;
      goto LABEL_48;
    }
    v66 = 0;
    inited = Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile::CreateAndInitSAXWriter(v34, &v66);
    if ( inited < 0 )
      goto LABEL_50;
    v67 = 0;
    v60.QuadPart = 0;
    inited = ATL::CComObject<Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeSAXEventsHandler>::CreateInstance(&v60);
    if ( inited < 0 )
    {
      v10 = v56;
    }
    else
    {
      v39 = v60;
      if ( !v60.QuadPart )
        goto LABEL_62;
      (*(void (__fastcall **)(union _ULARGE_INTEGER))(*(_QWORD *)v60.QuadPart + 8LL))(v60);
      pstmTemplate = (IStream *)((char *)v10 + 144);
      v40 = (_DWORD)v10 + 96;
      v10 = v56;
      inited = Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeSAXEventsHandler::Init(
                 v39.LowPart,
                 (_DWORD)v66,
                 (int)v56 + 48,
                 v40,
                 (__int64)pstmTemplate);
      if ( inited >= 0 )
      {
        inited = (**(__int64 (__fastcall ***)(union _ULARGE_INTEGER, GUID *, struct ISAXContentHandler **))v39.QuadPart)(
                   v39,
                   &GUID_1545cdfa_9e4e_4497_a8a4_2bf7d0112c44,
                   &v67);
        if ( inited < 0 )
          v67 = 0;
      }
      (*(void (__fastcall **)(union _ULARGE_INTEGER))(*(_QWORD *)v39.QuadPart + 16LL))(v39);
    }
    if ( inited < 0 )
    {
      if ( v67 )
        ((void (__fastcall *)(struct ISAXContentHandler *))v67->lpVtbl->Release)(v67);
LABEL_50:
      if ( v66 )
        ((void (__fastcall *)(struct IMXWriter *))v66->lpVtbl->Release)(v66);
LABEL_48:
      v26 = inited;
      v36 = (LPCWSTR *)((char *)v10 + 24);
      goto LABEL_126;
    }
LABEL_62:
    v68 = 0;
    inited = Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile::CreateAndInitSAXReader(
               v37,
               &v68,
               v38,
               v67);
    if ( inited >= 0 )
      break;
LABEL_63:
    if ( v68 )
      ((void (__fastcall *)(struct ISAXXMLReader *))v68->lpVtbl->Release)(v68);
    if ( v67 )
      ((void (__fastcall *)(struct ISAXContentHandler *))v67->lpVtbl->Release)(v67);
    if ( v66 )
      ((void (__fastcall *)(struct IMXWriter *))v66->lpVtbl->Release)(v66);
    v26 = inited;
LABEL_70:
    v36 = v58;
LABEL_125:
    v10 = v56;
LABEL_126:
    _mm_lfence();
    CLogger::LogError(L"Error merging configuration file", inited, v23);
    if ( (int)Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile::GetTempConfigFilePath(
                v10,
                v18,
                &pszPath) < 0 )
    {
      _mm_lfence();
      ATL::CSimpleStringT<unsigned short,0>::operator=(&pszPath, v36);
      v23 = pszPath;
      goto LABEL_142;
    }
    v23 = pszPath;
  }
  v55 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v55,
    v23);
  if ( !(unsigned int)ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::RemoveFileSpec(&v55)
    || PathIsRelativeW(v55) )
  {
    v41 = v55 - 12;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v55 - 2, 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v41 + 8LL))(*(_QWORD *)v41);
    }
    if ( v68 )
      ((void (__fastcall *)(struct ISAXXMLReader *))v68->lpVtbl->Release)(v68);
    if ( v67 )
      ((void (__fastcall *)(struct ISAXContentHandler *))v67->lpVtbl->Release)(v67);
    if ( v66 )
      ((void (__fastcall *)(struct IMXWriter *))v66->lpVtbl->Release)(v66);
    inited = -2147418113;
    v26 = -2147418113;
    goto LABEL_70;
  }
  if ( !PathFileExistsW(v55) )
  {
    v42 = SHCreateDirectoryExW(0, v55, 0);
    inited = (unsigned __int16)v42 | 0x80070000;
    if ( v42 <= 0 )
      inited = v42;
    if ( inited < 0 )
      goto LABEL_86;
  }
  ppstm = 0;
  inited = SHCreateStreamOnFileEx(v23, 0x1022u, 0x80u, 1, 0, &ppstm);
  if ( inited < 0 )
  {
LABEL_89:
    if ( ppstm )
      ((void (__fastcall *)(IStream *))ppstm->lpVtbl->Release)(ppstm);
LABEL_86:
    v43 = v55 - 12;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v55 - 2, 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v43 + 8LL))(*(_QWORD *)v43);
    }
    goto LABEL_63;
  }
  pvarg.vt = 13;
  pvarg.llVal = (LONGLONG)ppstm;
  if ( ppstm )
    ((void (__fastcall *)(IStream *))ppstm->lpVtbl->AddRef)(ppstm);
  v64 = pvarg;
  inited = ((__int64 (__fastcall *)(struct IMXWriter *, VARIANTARG *))v66->lpVtbl->put_output)(v66, &v64);
  if ( inited < 0 )
  {
    VariantClear(&pvarg);
    goto LABEL_89;
  }
  _mm_lfence();
  bstrString = 0;
  v36 = v58;
  inited = SHCreateStreamOnFileEx(*v58, 0, 0, 0, 0, (IStream **)&bstrString);
  if ( inited < 0 )
  {
    if ( bstrString )
      (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 16LL))(bstrString);
    VariantClear(&pvarg);
    if ( ppstm )
      ((void (__fastcall *)(IStream *))ppstm->lpVtbl->Release)(ppstm);
    v44 = v55 - 12;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v55 - 2, 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v44 + 8LL))(*(_QWORD *)v44);
    }
    if ( v68 )
      ((void (__fastcall *)(struct ISAXXMLReader *))v68->lpVtbl->Release)(v68);
    if ( v67 )
      ((void (__fastcall *)(struct ISAXContentHandler *))v67->lpVtbl->Release)(v67);
    if ( v66 )
      ((void (__fastcall *)(struct IMXWriter *))v66->lpVtbl->Release)(v66);
    v26 = inited;
    goto LABEL_125;
  }
  v63.vt = 13;
  v63.llVal = (LONGLONG)bstrString;
  if ( bstrString )
    (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 8LL))(bstrString);
  v64 = v63;
  v26 = ((__int64 (__fastcall *)(struct ISAXXMLReader *, VARIANTARG *))v68->lpVtbl->parse)(v68, &v64);
  if ( v26 < 0 )
  {
    VariantClear(&v63);
    if ( bstrString )
      (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 16LL))(bstrString);
    VariantClear(&pvarg);
    if ( ppstm )
      ((void (__fastcall *)(IStream *))ppstm->lpVtbl->Release)(ppstm);
    v45 = v55 - 12;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v55 - 2, 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v45 + 8LL))(*(_QWORD *)v45);
    }
    if ( v68 )
      ((void (__fastcall *)(struct ISAXXMLReader *))v68->lpVtbl->Release)(v68);
    if ( v67 )
      ((void (__fastcall *)(struct ISAXContentHandler *))v67->lpVtbl->Release)(v67);
    if ( v66 )
      ((void (__fastcall *)(struct IMXWriter *))v66->lpVtbl->Release)(v66);
    inited = v26;
    goto LABEL_125;
  }
  VariantClear(&v63);
  if ( bstrString )
    (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 16LL))(bstrString);
  VariantClear(&pvarg);
  if ( ppstm )
    ((void (__fastcall *)(IStream *))ppstm->lpVtbl->Release)(ppstm);
  v46 = v55 - 12;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v55 - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v46 + 8LL))(*(_QWORD *)v46);
  }
  if ( v68 )
    ((void (__fastcall *)(struct ISAXXMLReader *))v68->lpVtbl->Release)(v68);
  if ( v67 )
    ((void (__fastcall *)(struct ISAXContentHandler *))v67->lpVtbl->Release)(v67);
  if ( v66 )
    ((void (__fastcall *)(struct IMXWriter *))v66->lpVtbl->Release)(v66);
  v10 = v56;
LABEL_142:
  v11 = v61;
LABEL_143:
  FileW = CreateFileW(v23, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  *((_QWORD *)v10 + 4) = FileW;
  if ( FileW == (HANDLE)-1LL )
    CLogger::LogWarn(L"Failed to acquire lock on application config file", -2147418113, 0);
  CLogger::LogInfo(L"Configuration file to be used for CLR initialization", 0, v23);
  v48 = *((int *)v23 - 4);
  if ( v48 <= 0x7FFFFFFE )
  {
    v49 = 260;
    v50 = (char *)v23 - (char *)v11;
    do
    {
      if ( !(v48 + v49 - 260) )
        break;
      v51 = *(unsigned __int16 *)((char *)v11 + v50);
      if ( !v51 )
        break;
      *v11++ = v51;
      --v49;
    }
    while ( v49 );
    v52 = v11 - 1;
    if ( v49 )
      v52 = v11;
    *v52 = 0;
    TempConfigFilePath = v49 == 0 ? 0x8007007A : 0;
    if ( v49 )
      TempConfigFilePath = v26;
  }
  else
  {
    TempConfigFilePath = -2147024809;
    *v11 = 0;
  }
LABEL_155:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v23 - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v23 - 3) + 8LL))(*((_QWORD *)v23 - 3));
  }
LABEL_157:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v18 - 24 + 16), 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v18 - 24) + 8LL))(*(_QWORD *)(v18 - 24));
  }
  return (unsigned int)TempConfigFilePath;
}

```

## disassembly

```asm
0x1400222b0  mov     [rsp-8+arg_8], rbx
0x1400222b5  push    rbp
0x1400222b6  push    rsi
0x1400222b7  push    rdi
0x1400222b8  push    r12
0x1400222ba  push    r13
0x1400222bc  push    r14
0x1400222be  push    r15
0x1400222c0  lea     rbp, [rsp-7]
0x1400222c5  sub     rsp, 100h
0x1400222cc  mov     rax, cs:__security_cookie
0x1400222d3  xor     rax, rsp
0x1400222d6  mov     [rbp+37h+var_38], rax
0x1400222da  mov     r14, r8
0x1400222dd  mov     r15, rdx
0x1400222e0  mov     r13, rcx
0x1400222e3  mov     [rsp+130h+var_E8], rcx
0x1400222e8  mov     rsi, [rbp+37h+arg_20]
0x1400222ec  mov     r12, [rbp+37h+arg_38]
0x1400222f0  mov     [rsp+130h+var_C0], r12
0x1400222f5  xor     edi, edi
0x1400222f7  test    rdx, rdx
0x1400222fa  jz      loc_140022CCC
0x140022300  test    r8, r8
0x140022303  jz      loc_140022CCC
0x140022309  test    r9, r9
0x14002230c  jz      loc_140022CCC
0x140022312  test    rsi, rsi
0x140022315  jz      loc_140022CCC
0x14002231b  test    r12, r12
0x14002231e  jz      loc_140022CCC
0x140022324  mov     [r12], di
0x140022329  mov     rdx, r9
0x14002232c  lea     rcx, [rsp+130h+var_D0]
0x140022331  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140022336  lea     rbx, [r13+10h]
0x14002233a  lea     rdx, [rsp+130h+var_D0]
0x14002233f  mov     rcx, rbx
0x140022342  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140022347  mov     rdx, [rsp+130h+var_D0]
0x14002234c  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140022350  or      eax, 0FFFFFFFFh
0x140022353  lock xadd [rdx+10h], eax
0x140022358  sub     eax, 1
0x14002235b  jg      short loc_140022369
0x14002235d  lfence
0x140022360  mov     rcx, [rdx]
0x140022363  mov     rax, [rcx]
0x140022366  call    qword ptr [rax+8]
0x140022369  mov     rcx, [rbx]; pszPath
0x14002236c  call    cs:__imp_PathFileExistsW
0x140022372  test    eax, eax
0x140022374  jz      loc_140022CC5
0x14002237a  mov     rcx, [rbx]; pszPath
0x14002237d  call    cs:__imp_PathIsDirectoryW
0x140022383  test    eax, eax
0x140022385  jnz     loc_140022CC5
0x14002238b  mov     rdi, [rbx]
0x14002238e  mov     rcx, rdi; pszPath
0x140022391  call    cs:__imp_PathFindFileNameW
0x140022397  mov     r8, rax
0x14002239a  xor     eax, eax
0x14002239c  cmp     [r8], ax
0x1400223a0  jz      loc_140022CC5
0x1400223a6  sub     r8, rdi
0x1400223a9  sar     r8, 1
0x1400223ac  cmp     r8d, 0FFFFFFFFh
0x1400223b0  jz      loc_140022CC5
0x1400223b6  mov     [rsp+130h+var_D0], rax
0x1400223bb  mov     rax, [rbx]
0x1400223be  mov     r9d, [rax-10h]
0x1400223c2  sub     r9d, r8d
0x1400223c5  lea     rdx, [rsp+130h+var_D0]
0x1400223ca  mov     rcx, rbx
0x1400223cd  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x1400223d2  nop
0x1400223d3  mov     r8d, 7
0x1400223d9  lea     rdx, aConfig_0; ".config"
0x1400223e0  lea     rcx, [rsp+130h+var_D0]
0x1400223e5  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1400223ea  lea     rdi, [r13+18h]
0x1400223ee  mov     [rsp+130h+var_D8], rdi
0x1400223f3  mov     rdx, rbx
0x1400223f6  mov     rcx, rdi
0x1400223f9  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x1400223fe  mov     rcx, rdi
0x140022401  call    ?RemoveFileSpec@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAHXZ; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::RemoveFileSpec(void)
0x140022406  mov     rdi, [rsp+130h+var_D0]
0x14002240b  test    eax, eax
0x14002240d  jnz     short loc_14002241A
0x14002240f  mov     r14d, 8000FFFFh
0x140022415  jmp     loc_140022CA2
0x14002241a  mov     rcx, [r13+18h]
0x14002241e  sub     rcx, 18h
0x140022422  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x140022427  mov     rbx, rax
0x14002242a  add     rax, 18h
0x14002242e  mov     qword ptr [rsp+130h+var_C8], rax
0x140022433  lea     rdx, [rsp+130h+var_C8]
0x140022438  lea     rcx, ?s_strApplicationDirectory@CCodeBase@BindingRedirects@PkgDef@VisualStudio@Microsoft@@2V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@A; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase::s_strApplicationDirectory
0x14002243f  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140022444  nop
0x140022445  or      eax, 0FFFFFFFFh
0x140022448  lock xadd [rbx+10h], eax
0x14002244d  sub     eax, 1
0x140022450  jg      short loc_140022461
0x140022452  lfence
0x140022455  mov     rcx, [rbx]
0x140022458  mov     rax, [rcx]
0x14002245b  mov     rdx, rbx
0x14002245e  call    qword ptr [rax+8]
0x140022461  mov     rdx, rdi
0x140022464  lea     rcx, [r13+18h]
0x140022468  call    ?Append@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::Append(ushort const *)
0x14002246d  xor     ecx, ecx
0x14002246f  test    eax, eax
0x140022471  jnz     short loc_14002247E
0x140022473  mov     r14d, 8007000Eh
0x140022479  jmp     loc_140022CA2
0x14002247e  mov     [r13+0], r15
0x140022482  mov     al, [rbp+37h+arg_28]
0x140022485  mov     [r13+28h], al
0x140022489  mov     al, [rbp+37h+arg_30]
0x14002248c  mov     [r13+29h], al
0x140022490  or      r8, 0FFFFFFFFFFFFFFFFh
0x140022494  inc     r8
0x140022497  cmp     [rsi+r8*2], cx
0x14002249c  jnz     short loc_140022494
0x14002249e  mov     rdx, rsi
0x1400224a1  lea     rcx, [r13+8]
0x1400224a5  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1400224aa  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x1400224af  mov     rcx, rax
0x1400224b2  xor     esi, esi
0x1400224b4  test    rax, rax
0x1400224b7  jz      loc_140022CF8
0x1400224bd  mov     rax, [rax]
0x1400224c0  call    qword ptr [rax+18h]
0x1400224c3  lea     rbx, [rax+18h]
0x1400224c7  mov     [rsp+130h+pszPath], rbx
0x1400224cc  cmp     [r13+29h], sil
0x1400224d0  jz      short loc_140022509
0x1400224d2  lea     r8, [rsp+130h+pszPath]
0x1400224d7  mov     rdx, rdi
0x1400224da  mov     rcx, r13
0x1400224dd  call    ?GetTempConfigFilePath@CMergeConfigFile@BindingRedirects@PkgDef@VisualStudio@Microsoft@@AEAAJPEBGAEAV?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@@Z; Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile::GetTempConfigFilePath(ushort const *,ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &)
0x1400224e2  mov     r14d, eax
0x1400224e5  test    eax, eax
0x1400224e7  jns     short loc_1400224F3
0x1400224e9  mov     rbx, [rsp+130h+pszPath]
0x1400224ee  jmp     loc_140022C84
0x1400224f3  xor     r8d, r8d; unsigned __int16 *
0x1400224f6  xor     edx, edx; int
0x1400224f8  lea     rcx, aConfigurationI; "Configuration is Volatile."
0x1400224ff  call    ?LogInfo@CLogger@@SAXPEBGJ0@Z; CLogger::LogInfo(ushort const *,long,ushort const *)
0x140022504  jmp     loc_1400225A6
0x140022509  mov     [rbp+37h+bstrString], rsi
0x14002250d  lea     r8, [rbp+37h+bstrString]; unsigned __int16 **
0x140022511  mov     rdx, r14; unsigned __int16 *
0x140022514  mov     ecx, 1Ch; int
0x140022519  call    ?util_CalculateAppDataFolder@@YAJHPEBGPEAPEAG@Z; util_CalculateAppDataFolder(int,ushort const *,ushort * *)
0x14002251e  mov     r14d, eax
0x140022521  test    eax, eax
0x140022523  js      short loc_14002258D
0x140022525  mov     rdx, [rbp+37h+bstrString]
0x140022529  lea     rcx, [rbp+37h+var_40]
0x14002252d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140022532  nop
0x140022533  lea     rdx, [rbp+37h+var_40]
0x140022537  lea     rcx, [rsp+130h+pszPath]
0x14002253c  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140022541  nop
0x140022542  nop     dword ptr [rax+00h]
0x140022546  nop     word ptr [rax+rax+00000000h]
0x140022550  mov     rdx, [rbp+37h+var_40]
0x140022554  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140022558  or      eax, 0FFFFFFFFh
0x14002255b  lock xadd [rdx+10h], eax
0x140022560  sub     eax, 1
0x140022563  jg      short loc_140022571
0x140022565  lfence
0x140022568  mov     rcx, [rdx]
0x14002256b  mov     rax, [rcx]
0x14002256e  call    qword ptr [rax+8]
0x140022571  mov     rdx, rdi
0x140022574  lea     rcx, [rsp+130h+pszPath]
0x140022579  call    ?Append@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::Append(ushort const *)
0x14002257e  test    eax, eax
0x140022580  jnz     short loc_14002259C
0x140022582  mov     r14d, 8007000Eh
0x140022588  mov     rbx, [rsp+130h+pszPath]
0x14002258d  mov     rcx, [rbp+37h+bstrString]; bstrString
0x140022591  call    cs:__imp_SysFreeString
0x140022597  jmp     loc_140022C84
0x14002259c  mov     rcx, [rbp+37h+bstrString]; bstrString
0x1400225a0  call    cs:__imp_SysFreeString
0x1400225a6  lea     rdx, SubBlock; "\\"
0x1400225ad  lea     rcx, [rbp+37h+bstrString]
0x1400225b1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400225b6  nop
0x1400225b7  lea     rdx, [rbp+37h+bstrString]
0x1400225bb  lea     rcx, [r13+8]
0x1400225bf  call    ?EnsureThatStringEndWith@@YAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV12@@Z; EnsureThatStringEndWith(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400225c4  nop
0x1400225c5  mov     rdx, [rbp+37h+bstrString]
0x1400225c9  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400225cd  or      eax, 0FFFFFFFFh
0x1400225d0  lock xadd [rdx+10h], eax
0x1400225d5  sub     eax, 1
0x1400225d8  jg      short loc_1400225E6
0x1400225da  lfence
0x1400225dd  mov     rcx, [rdx]
0x1400225e0  mov     rax, [rcx]
0x1400225e3  call    qword ptr [rax+8]
0x1400225e6  mov     r15d, esi
0x1400225e9  mov     r14d, 8000FFFFh
0x1400225ef  mov     rbx, [rsp+130h+pszPath]
0x1400225f4  test    rbx, rbx
0x1400225f7  jz      short loc_14002264F
0x1400225f9  mov     rcx, rbx; pszPath
0x1400225fc  call    cs:__imp_PathFileExistsW
0x140022602  test    eax, eax
0x140022604  jz      short loc_14002264F
0x140022606  cmp     [r13+28h], sil
0x14002260a  jnz     short loc_14002264F
0x14002260c  lea     rax, [rbp+37h+bstrString]
0x140022610  mov     [rsp+130h+pstmTemplate], rax; union _ULARGE_INTEGER *
0x140022615  mov     rdx, rbx; unsigned __int16 *
0x140022618  call    ?GetFileTime@CMergeConfigFile@BindingRedirects@PkgDef@VisualStudio@Microsoft@@AEBA_NPEBGPEAT_ULARGE_INTEGER@@11@Z; Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile::GetFileTime(ushort const *,_ULARGE_INTEGER *,_ULARGE_INTEGER *,_ULARGE_INTEGER *)
0x14002261d  test    al, al
0x14002261f  jz      loc_140022BB9
0x140022625  lea     rax, [rsp+130h+var_C8]
0x14002262a  mov     [rsp+130h+pstmTemplate], rax; union _ULARGE_INTEGER *
0x14002262f  mov     rdx, [r13+18h]; unsigned __int16 *
0x140022633  call    ?GetFileTime@CMergeConfigFile@BindingRedirects@PkgDef@VisualStudio@Microsoft@@AEBA_NPEBGPEAT_ULARGE_INTEGER@@11@Z; Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile::GetFileTime(ushort const *,_ULARGE_INTEGER *,_ULARGE_INTEGER *,_ULARGE_INTEGER *)
0x140022638  test    al, al
0x14002263a  jz      loc_140022BB9
0x140022640  mov     rax, qword ptr [rsp+130h+var_C8]
0x140022645  cmp     [rbp+37h+bstrString], rax
0x140022649  jnb     loc_140022BB9
0x14002264f  mov     rcx, r13; this
0x140022652  call    ?ReadRegistryEntries@CMergeConfigFile@BindingRedirects@PkgDef@VisualStudio@Microsoft@@AEAAJXZ; Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile::ReadRegistryEntries(void)
0x140022657  test    eax, eax
0x140022659  js      short loc_140022688
0x14002265b  lfence
0x14002265e  mov     rcx, r13; this
0x140022661  call    ?CoalesceBindingRedirects@CMergeConfigFile@BindingRedirects@PkgDef@VisualStudio@Microsoft@@AEAAJXZ; Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile::CoalesceBindingRedirects(void)
0x140022666  test    eax, eax
0x140022668  js      short loc_140022688
0x14002266a  lfence
0x14002266d  mov     rcx, r13; this
0x140022670  call    ?CoalesceCodeBases@CMergeConfigFile@BindingRedirects@PkgDef@VisualStudio@Microsoft@@AEAAJXZ; Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile::CoalesceCodeBases(void)
0x140022675  test    eax, eax
0x140022677  js      short loc_140022688
0x140022679  lfence
0x14002267c  mov     rcx, r13; this
0x14002267f  call    ?CoalesceBindingRedirectsCodeBases@CMergeConfigFile@BindingRedirects@PkgDef@VisualStudio@Microsoft@@AEAAJXZ; Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile::CoalesceBindingRedirectsCodeBases(void)
0x140022684  test    eax, eax
0x140022686  jns     short loc_140022690
0x140022688  mov     r14d, eax
0x14002268b  jmp     loc_140022C84
0x140022690  lfence
0x140022693  test    rbx, rbx
0x140022696  jnz     short loc_1400226A9
0x140022698  mov     esi, 80070057h
0x14002269d  mov     r15d, esi
0x1400226a0  lea     r12, [r13+18h]
0x1400226a4  jmp     loc_140022AD7
0x1400226a9  mov     [rbp+37h+var_58], rsi
0x1400226ad  lea     rdx, [rbp+37h+var_58]; struct IMXWriter **
0x1400226b1  call    ?CreateAndInitSAXWriter@CMergeConfigFile@BindingRedirects@PkgDef@VisualStudio@Microsoft@@AEBAJPEAPEAUIMXWriter@@@Z; Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile::CreateAndInitSAXWriter(IMXWriter * *)
0x1400226b6  mov     esi, eax
0x1400226b8  xor     r15d, r15d
0x1400226bb  test    eax, eax
0x1400226bd  jns     short loc_1400226D0
0x1400226bf  mov     rcx, [rbp+37h+var_58]
0x1400226c3  test    rcx, rcx
0x1400226c6  jz      short loc_14002269D
0x1400226c8  mov     rax, [rcx]
0x1400226cb  call    qword ptr [rax+10h]
0x1400226ce  jmp     short loc_14002269D
0x1400226d0  mov     [rbp+37h+var_50], r15
0x1400226d4  lea     r12, [r13+90h]
0x1400226db  mov     qword ptr [rsp+130h+var_C8], r15
0x1400226e0  lea     rcx, [rsp+130h+var_C8]
0x1400226e5  call    ?CreateInstance@?$CComObject@VCMergeSAXEventsHandler@BindingRedirects@PkgDef@VisualStudio@Microsoft@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeSAXEventsHandler>::CreateInstance(ATL::CComObject<Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeSAXEventsHandler> * *)
0x1400226ea  mov     esi, eax
0x1400226ec  test    eax, eax
0x1400226ee  js      short loc_140022752
0x1400226f0  mov     r15, qword ptr [rsp+130h+var_C8]
0x1400226f5  test    r15, r15
0x1400226f8  jz      short loc_140022773
0x1400226fa  mov     rax, [r15]
0x1400226fd  mov     rcx, r15
0x140022700  call    qword ptr [rax+8]
0x140022703  mov     [rsp+130h+pstmTemplate], r12
0x140022708  lea     r9, [r13+60h]
0x14002270c  mov     r13, [rsp+130h+var_E8]
0x140022711  lea     r8, [r13+30h]
0x140022715  mov     rdx, [rbp+37h+var_58]
  ... truncated ...
```
