# CWin32BIOS::LoadPropertyValues(CInstance *)

- ea: `0x180025f64`
- end: `0x180026d2d`
- name: `?LoadPropertyValues@CWin32BIOS@@QEAAJPEAVCInstance@@@Z`
- size: `3529`
- prototype: `int(CWin32BIOS *__hidden this, struct CInstance *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180027ce0`
- `0x1800953a0`

## callees

- `0x180014c58`
- `0x18002540c`
- `0x180025f64`
- `0x180026d40`
- `0x180026db0`
- `0x18003a82c`
- `0x18008bb9c`
- `0x1800fc902`
- `0x1800fc980`

## import_xrefs

- `msvcrt!malloc` at `0x1800269b8`
- `msvcrt!malloc` at `0x1800269b8`
- `msvcrt!wcschr` at `0x180026b6e`
- `msvcrt!wcschr` at `0x180026b6e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002609f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002609f`
- `framedynos!?captainsLog@@3VProviderLog@@A` at `0x180026c1c`
- `framedynos!?captainsLog@@3VProviderLog@@A` at `0x180026c47`
- `framedynos!?captainsLog@@3VProviderLog@@A` at `0x180026c7b`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBG0HW4LogLevel@1@@Z` at `0x180026c23`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBG0HW4LogLevel@1@@Z` at `0x180026c4e`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBG0HW4LogLevel@1@@Z` at `0x180026c82`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBG0HW4LogLevel@1@@Z` at `0x180026c23`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBG0HW4LogLevel@1@@Z` at `0x180026c4e`
- `framedynos!?LocalLogMessage@ProviderLog@@QEAAXPEBG0HW4LogLevel@1@@Z` at `0x180026c82`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180026002`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800260ed`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800261b5`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180026002`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800260ed`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800261b5`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x180026103`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x180026103`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800261e6`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800261fa`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18002686e`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800261e6`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800261fa`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18002686e`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800260ce`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x18002611c`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180026131`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180026146`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180026309`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800260ce`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x18002611c`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180026131`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180026146`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180026309`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180026193`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800261cf`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180026d04`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180026193`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800261cf`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180026d04`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x180026262`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x18002641f`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x180026262`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x18002641f`
- `framedynos!?ReleaseBuffer@CHString@@QEAAXH@Z` at `0x1800262e5`
- `framedynos!?ReleaseBuffer@CHString@@QEAAXH@Z` at `0x1800264b3`
- `framedynos!?ReleaseBuffer@CHString@@QEAAXH@Z` at `0x180026bd2`
- `framedynos!?ReleaseBuffer@CHString@@QEAAXH@Z` at `0x1800262e5`
- `framedynos!?ReleaseBuffer@CHString@@QEAAXH@Z` at `0x1800264b3`
- `framedynos!?ReleaseBuffer@CHString@@QEAAXH@Z` at `0x180026bd2`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x180025fc9`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x180025fc9`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x180026827`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x180026d20`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x180026827`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x180026d20`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x180025fec`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x180025fec`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180025fbb`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180025fbb`
- `framedynos!?GethKey@CRegistry@@QEAAPEAUHKEY__@@XZ` at `0x18002604e`
- `framedynos!?GethKey@CRegistry@@QEAAPEAUHKEY__@@XZ` at `0x18002604e`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800262f0`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x180026bdd`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800262f0`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x180026bdd`
- `framedynos!??4CHString@@QEAAAEBV0@PEBD@Z` at `0x180026033`
- `framedynos!??4CHString@@QEAAAEBV0@PEBD@Z` at `0x180026033`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x1800260b9`
- `framedynos!??4CHString@@QEAAAEBV0@PEBG@Z` at `0x1800260b9`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180025fa4`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x18002640b`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180026564`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800268fc`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180026a74`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180026b98`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180025fa4`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x18002640b`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180026564`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800268fc`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180026a74`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180026b98`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x180026165`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x180026180`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x180026165`
- `framedynos!?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z` at `0x180026180`
- `framedynos!?SetVariant@CInstance@@QEAA_NPEBGAEBUtagVARIANT@@@Z` at `0x180026736`
- `framedynos!?SetVariant@CInstance@@QEAA_NPEBGAEBUtagVARIANT@@@Z` at `0x180026736`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x18002601d`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x18002601d`
- `framedynos!?SetStringArray@CInstance@@QEAA_NPEBGAEBUtagSAFEARRAY@@@Z` at `0x180026a3f`
- `framedynos!?SetStringArray@CInstance@@QEAA_NPEBGAEBUtagSAFEARRAY@@@Z` at `0x180026b54`
- `framedynos!?SetStringArray@CInstance@@QEAA_NPEBGAEBUtagSAFEARRAY@@@Z` at `0x180026a3f`
- `framedynos!?SetStringArray@CInstance@@QEAA_NPEBGAEBUtagSAFEARRAY@@@Z` at `0x180026b54`
- `framedynos!?Empty@CHString@@QEAAXXZ` at `0x1800264be`
- `framedynos!?Empty@CHString@@QEAAXXZ` at `0x1800264be`
- `framedynos!?SetByte@CInstance@@QEAA_NPEBGE@Z` at `0x18002675b`
- `framedynos!?SetByte@CInstance@@QEAA_NPEBGE@Z` at `0x18002676f`
- `framedynos!?SetByte@CInstance@@QEAA_NPEBGE@Z` at `0x180026783`
- `framedynos!?SetByte@CInstance@@QEAA_NPEBGE@Z` at `0x180026797`
- `framedynos!?SetByte@CInstance@@QEAA_NPEBGE@Z` at `0x18002675b`
- `framedynos!?SetByte@CInstance@@QEAA_NPEBGE@Z` at `0x18002676f`
- `framedynos!?SetByte@CInstance@@QEAA_NPEBGE@Z` at `0x180026783`
- `framedynos!?SetByte@CInstance@@QEAA_NPEBGE@Z` at `0x180026797`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800260e2`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18002680c`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180026818`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800260e2`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18002680c`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180026818`
- `OLEAUT32!__imp_SysAllocString` at `0x1800269e3`
- `OLEAUT32!__imp_SysAllocString` at `0x180026b11`
- `OLEAUT32!__imp_SysAllocString` at `0x1800269e3`
- `OLEAUT32!__imp_SysAllocString` at `0x180026b11`
- `OLEAUT32!__imp_VariantInit` at `0x1800265ef`
- `OLEAUT32!__imp_VariantInit` at `0x1800265ef`
- `OLEAUT32!__imp_VariantClear` at `0x1800267a6`
- `OLEAUT32!__imp_VariantClear` at `0x1800267a6`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180026602`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002691c`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180026ad8`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180026602`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002691c`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180026ad8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180026a48`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180026b5e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180026a48`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180026b5e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180026af3`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180026af3`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180026b41`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180026b41`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180026683`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800266e6`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180026a05`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180026683`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800266e6`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180026a05`

## string_xrefs

- `0x180026864`: `InstallableLanguages`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CWin32BIOS::LoadPropertyValues(CWin32BIOS *this, struct CInstance *a2)
{
  int v3; // eax
  ULONG v4; // r14d
  CWin32BIOS *v5; // rcx
  HKEY v6; // rbx
  __int64 v7; // r12
  int v8; // edx
  unsigned int v9; // ebx
  _QWORD *v10; // rdx
  unsigned __int64 v11; // r8
  _BYTE **v12; // rax
  int v13; // eax
  int v14; // eax
  __int64 *v15; // rbx
  __int64 v16; // rbx
  unsigned int v17; // esi
  unsigned __int16 *Buffer; // r9
  char *v19; // rcx
  char *v20; // rdx
  unsigned int i; // r8d
  int j; // r8d
  unsigned __int16 v23; // ax
  _BYTE **v24; // rdx
  unsigned __int64 v25; // r8
  int v26; // ecx
  int v27; // ecx
  SAFEARRAYBOUND *v28; // rcx
  SAFEARRAYBOUND v29; // rsi
  char *v30; // rcx
  char *v31; // rdx
  unsigned __int16 *v32; // r9
  unsigned int k; // eax
  int m; // r8d
  unsigned __int16 v35; // ax
  __int64 v36; // rax
  unsigned int v37; // ebx
  unsigned __int16 *v38; // r10
  char *v39; // rcx
  char *v40; // r8
  unsigned __int16 *v41; // r9
  unsigned int n; // edx
  int ii; // edx
  unsigned __int16 v44; // ax
  __int64 v45; // rax
  char *v46; // rcx
  char *v47; // rdx
  unsigned __int16 *v48; // r9
  unsigned int jj; // eax
  int kk; // r8d
  unsigned __int16 v51; // ax
  ULONG v52; // ecx
  unsigned int v53; // eax
  ULONG v54; // edx
  __int64 v55; // rax
  unsigned int v56; // r8d
  SAFEARRAY *parray; // rcx
  unsigned int v58; // ebx
  ULONG v59; // eax
  unsigned int v60; // edx
  int v61; // r15d
  __int64 mm; // rax
  unsigned int v63; // ebx
  unsigned int nn; // esi
  unsigned __int8 *v65; // rbx
  HRESULT v66; // eax
  _QWORD *v67; // rdx
  unsigned __int64 v68; // r8
  _BYTE **v69; // rax
  int v70; // eax
  int v71; // eax
  unsigned __int8 **v72; // rax
  unsigned __int8 *v74; // r14
  unsigned __int8 *v75; // rcx
  unsigned __int8 *v76; // rdx
  OLECHAR *v77; // r9
  unsigned int i1; // eax
  int i2; // r8d
  OLECHAR v80; // ax
  SAFEARRAY *v81; // rsi
  unsigned int v82; // ecx
  unsigned int v83; // r8d
  unsigned __int8 *v84; // rcx
  unsigned __int8 *v85; // rdx
  OLECHAR *v86; // r9
  unsigned int i3; // eax
  int i4; // r8d
  OLECHAR v89; // ax
  _QWORD *v90; // rbx
  BSTR v91; // rax
  BYTE *v92; // rax
  signed int v93; // ebx
  __int64 v94; // rcx
  SAFEARRAY *v95; // rax
  SAFEARRAY *v96; // rsi
  BSTR v97; // rax
  __int64 v98; // rax
  BYTE *v99; // r15
  wchar_t *v100; // rax
  CWin32BIOS *v101; // rcx
  unsigned int v102; // ebx
  LONG rgIndices[2]; // [rsp+30h] [rbp-B38h] BYREF
  ULONG pv; // [rsp+38h] [rbp-B30h] BYREF
  char v105[8]; // [rsp+40h] [rbp-B28h] BYREF
  SAFEARRAYBOUND v106; // [rsp+48h] [rbp-B20h] BYREF
  SAFEARRAYBOUND v107; // [rsp+50h] [rbp-B18h] BYREF
  char v108[8]; // [rsp+58h] [rbp-B10h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+60h] [rbp-B08h] BYREF
  char v110[8]; // [rsp+68h] [rbp-B00h] BYREF
  DWORD cbData; // [rsp+70h] [rbp-AF8h] BYREF
  DWORD Type[2]; // [rsp+74h] [rbp-AF4h] BYREF
  int v113; // [rsp+7Ch] [rbp-AECh] BYREF
  int v114; // [rsp+80h] [rbp-AE8h] BYREF
  int pExceptionObject; // [rsp+84h] [rbp-AE4h] BYREF
  int v116; // [rsp+88h] [rbp-AE0h] BYREF
  int v117; // [rsp+8Ch] [rbp-ADCh] BYREF
  VARIANTARG pvarg; // [rsp+90h] [rbp-AD8h] BYREF
  _QWORD *v119; // [rsp+A8h] [rbp-AC0h]
  _BYTE v120[608]; // [rsp+B0h] [rbp-AB8h] BYREF
  unsigned __int16 v121[256]; // [rsp+310h] [rbp-858h] BYREF
  OLECHAR psz[264]; // [rsp+510h] [rbp-658h] BYREF
  BYTE Data[2]; // [rsp+720h] [rbp-448h] BYREF

  CInstance::SetCHString(a2, L"Name", L"Default System BIOS");
  CInstance::SetCharSplat(a2, L"Status", L"OK");
  CRegistry::CRegistry((CRegistry *)v120);
  v3 = CRegistry::Open((CRegistry *)v120, HKEY_LOCAL_MACHINE, L"HARDWARE\\Description\\System", 0x20019u);
  v4 = 0;
  if ( v3 )
  {
    v102 = WinErrorToWBEMhResult(v3);
    CRegistry::~CRegistry((CRegistry *)v120);
    return v102;
  }
  CHString::CHString((CHString *)v108);
  if ( CRegistry::GetCurrentKeyValue((CRegistry *)v120, L"SystemBiosDate", (struct CHString *)v108) )
    CHString::operator=(v108, &word_180128816);
  CWin32BIOS::SetBiosDate(v5, a2, (struct CHString *)v108);
  v6 = CRegistry::GethKey((CRegistry *)v120);
  Type[0] = 0;
  cbData = 1040;
  memset_0(Data, 0, 0x410u);
  if ( RegQueryValueExW(v6, L"SystemBiosVersion", 0, Type, Data, &cbData) || !*(_WORD *)Data )
  {
    CHString::operator=(v108, L"UNKNOWN");
    CInstance::SetCHString(a2, L"Version", (const struct CHString *)v108);
    v7 = -1;
  }
  else
  {
    CInstance::SetCHString(a2, L"Version", (const unsigned __int16 *)Data);
    v92 = Data;
    v93 = 0;
    v7 = -1;
    if ( *(_WORD *)Data )
    {
      do
      {
        ++v4;
        v94 = -1;
        do
          ++v94;
        while ( *(_WORD *)&v92[2 * v94] );
        v92 += 2 * v94 + 2;
      }
      while ( *(_WORD *)v92 );
      if ( v4 )
      {
        *(_QWORD *)rgIndices = 0;
        v106.lLbound = 0;
        v106.cElements = v4;
        v95 = SafeArrayCreate(8u, 1u, &v106);
        v96 = v95;
        v107 = (SAFEARRAYBOUND)v95;
        try
        {
          if ( v95 && SafeArrayAccessData(v95, (void **)rgIndices) >= 0 )
          {
            try
            {
              v99 = Data;
              while ( 1 )
              {
                Type[1] = v93;
                if ( v93 >= (int)v4 )
                  break;
                v97 = SysAllocString((const OLECHAR *)v99);
                *(_QWORD *)(*(_QWORD *)rgIndices + 8LL * v93) = v97;
                v98 = -1;
                do
                  ++v98;
                while ( *(_WORD *)&v99[2 * v98] );
                v99 += 2 * v98 + 2;
                ++v93;
              }
            }
            catch ( ... )
            {
              SafeArrayUnaccessData(*(SAFEARRAY **)&v107);
              throw;
            }
            SafeArrayUnaccessData(v96);
            CInstance::SetStringArray(a2, L"BIOSVersion", v96);
          }
        }
        catch ( ... )
        {
          SafeArrayDestroy(*(SAFEARRAY **)&v107);
          throw;
        }
        SafeArrayDestroy(v96);
      }
    }
    v100 = wcschr((const wchar_t *)Data, 0);
    v4 = 0;
    if ( v100 && v100[1] )
      CInstance::SetCHString(a2, L"Name", v100 + 1);
  }
  CHString::~CHString((CHString *)v108);
  CHString::CHString((CHString *)v105);
  if ( CInstance::GetCHString(a2, L"Name", (struct CHString *)v105) )
  {
    CInstance::SetCHString(a2, L"Caption", (const struct CHString *)v105);
    CInstance::SetCHString(a2, L"SoftwareElementID", (const struct CHString *)v105);
    CInstance::SetCHString(a2, L"Description", (const struct CHString *)v105);
  }
  LOWORD(rgIndices[0]) = 3;
  CInstance::SetWBEMINT16(a2, L"SoftwareElementState", (const __int16 *)rgIndices);
  LOWORD(rgIndices[0]) = 0;
  CInstance::SetWBEMINT16(a2, L"TargetOperatingSystem", (const __int16 *)rgIndices);
  CInstance::Setbool(a2, L"PrimaryBIOS", 1);
  v106.cElements = 0;
  if ( !(unsigned int)CSMBios::Init((CSMBios *)&v106, v8) )
  {
    CInstance::Setbool(a2, L"SMBIOSPresent", 0);
    goto LABEL_150;
  }
  CHString::CHString((CHString *)v110);
  v9 = CSMBios::m_Version;
  CInstance::Setbool(a2, L"SMBIOSPresent", 1);
  CInstance::SetDWORD(a2, L"SMBIOSMajorVersion", HIWORD(v9));
  CInstance::SetDWORD(a2, L"SMBIOSMinorVersion", (unsigned __int16)v9);
  v10 = CSMBios::m_pSTTree;
  if ( !CSMBios::m_pSTTree )
    goto LABEL_207;
  while ( 1 )
  {
    v11 = (unsigned __int64)v10;
    v12 = (_BYTE **)v10[2];
    if ( **v12 )
      break;
    v10 = (_QWORD *)v10[1];
LABEL_12:
    v13 = 0;
    if ( !v10 )
      goto LABEL_17;
  }
  if ( **v12 > 1u )
  {
    v10 = (_QWORD *)*v10;
    goto LABEL_12;
  }
  v13 = 1;
LABEL_17:
  v14 = -v13;
  if ( (v11 & -(__int64)(v14 != 0)) != 0 )
  {
    v15 = *(__int64 **)((v11 & -(__int64)(v14 != 0)) + 0x10);
    if ( v15 )
    {
      v16 = *v15;
      v17 = *(unsigned __int8 *)(v16 + 7);
      Buffer = CHString::GetBuffer((CHString *)v110, 256);
      v19 = (char *)(v16 + *(unsigned __int8 *)(v16 + 1));
      v20 = (char *)CSMBios::m_pTable + CSMBios::m_Size;
      for ( i = 1; v19 < v20 && v17 > i && *v19; ++i )
      {
        do
        {
          if ( !*v19 )
            break;
          ++v19;
        }
        while ( v19 < v20 );
        ++v19;
      }
      if ( v17 )
      {
        for ( j = 64; v19 < v20; --j )
        {
          v23 = (unsigned __int8)*v19;
          if ( (unsigned __int8)v23 <= 0xFu )
            break;
          if ( !j )
            break;
          ++v19;
          *Buffer++ = v23;
        }
      }
      *Buffer = 0;
      CHString::ReleaseBuffer((CHString *)v110, -1);
      if ( !CHString::IsEmpty((CHString *)v110) )
        CInstance::SetCHString(a2, L"SerialNumber", (const struct CHString *)v110);
    }
    goto LABEL_34;
  }
LABEL_207:
  ProviderLog::LocalLogMessage(
    captainsLog,
    L"SMBios Structure not found",
    L"onecore\\admin\\wmi\\wbem\\providers\\win32provider\\providers\\smbstruc.cpp",
    571,
    2);
LABEL_34:
  v24 = (_BYTE **)CSMBios::m_pSTTree;
  if ( !CSMBios::m_pSTTree )
    goto LABEL_208;
  while ( 1 )
  {
    v25 = (unsigned __int64)v24;
    if ( !**(_BYTE **)v24[2] )
      break;
    v24 = (_BYTE **)*v24;
    v26 = 0;
    if ( !v24 )
      goto LABEL_39;
  }
  v26 = 1;
LABEL_39:
  v27 = -v26;
  if ( (v25 & -(__int64)(v27 != 0)) != 0 )
  {
    v28 = *(SAFEARRAYBOUND **)((v25 & -(__int64)(v27 != 0)) + 0x10);
  }
  else
  {
LABEL_208:
    ProviderLog::LocalLogMessage(
      captainsLog,
      L"SMBios Structure not found",
      L"onecore\\admin\\wmi\\wbem\\providers\\win32provider\\providers\\smbstruc.cpp",
      571,
      2);
    v28 = 0;
  }
  if ( v28 )
  {
    v29 = *v28;
    v107 = v29;
    v30 = (char *)(*(_QWORD *)&v29 + *(unsigned __int8 *)(*(_QWORD *)&v29 + 1LL));
    v31 = (char *)CSMBios::m_pTable + CSMBios::m_Size;
    v32 = v121;
    for ( k = 1; v30 < v31 && *(unsigned __int8 *)(*(_QWORD *)&v29 + 4LL) > k && *v30; ++k )
    {
      do
      {
        if ( !*v30 )
          break;
        ++v30;
      }
      while ( v30 < v31 );
      ++v30;
    }
    if ( *(_BYTE *)(*(_QWORD *)&v29 + 4LL) )
    {
      for ( m = 64; v30 < v31; --m )
      {
        v35 = (unsigned __int8)*v30;
        if ( (unsigned __int8)v35 <= 0xFu || !m )
          break;
        ++v30;
        *v32++ = v35;
      }
    }
    *v32 = 0;
    v36 = -1;
    do
      ++v36;
    while ( v121[v36] );
    if ( (_DWORD)v36 )
      CInstance::SetCHString(a2, L"Manufacturer", v121);
    v37 = *(unsigned __int8 *)(*(_QWORD *)&v29 + 8LL);
    v38 = CHString::GetBuffer((CHString *)v105, 256);
    v39 = (char *)(*(_QWORD *)&v29 + *(unsigned __int8 *)(*(_QWORD *)&v29 + 1LL));
    v40 = (char *)CSMBios::m_pTable + CSMBios::m_Size;
    v41 = v38;
    for ( n = 1; v39 < v40 && v37 > n && *v39; ++n )
    {
      do
      {
        if ( !*v39 )
          break;
        ++v39;
      }
      while ( v39 < v40 );
      ++v39;
    }
    if ( v37 )
    {
      for ( ii = 64; v39 < v40; --ii )
      {
        v44 = (unsigned __int8)*v39;
        if ( (unsigned __int8)v44 <= 0xFu || !ii )
          break;
        ++v39;
        *v41++ = v44;
      }
    }
    *v41 = 0;
    if ( !v38 )
      goto LABEL_78;
    v45 = -1;
    do
      ++v45;
    while ( v38[v45] );
    if ( (_DWORD)v45 )
    {
      CHString::ReleaseBuffer((CHString *)v105, -1);
      if ( !CHString::IsEmpty((CHString *)v105) )
        CWin32BIOS::SetBiosDate(v101, a2, (struct CHString *)v105);
    }
    else
    {
LABEL_78:
      CHString::ReleaseBuffer((CHString *)v105, -1);
      CHString::Empty((CHString *)v105);
    }
    v46 = (char *)(*(_QWORD *)&v29 + *(unsigned __int8 *)(*(_QWORD *)&v29 + 1LL));
    v47 = (char *)CSMBios::m_pTable + CSMBios::m_Size;
    v48 = v121;
    for ( jj = 1; v46 < v47 && *(unsigned __int8 *)(*(_QWORD *)&v29 + 5LL) > jj && *v46; ++jj )
    {
      do
      {
        if ( !*v46 )
          break;
        ++v46;
      }
      while ( v46 < v47 );
      ++v46;
    }
    if ( *(_BYTE *)(*(_QWORD *)&v29 + 5LL) )
    {
      for ( kk = 64; v46 < v47; --kk )
      {
        v51 = (unsigned __int8)*v46;
        if ( (unsigned __int8)v51 <= 0xFu || !kk )
          break;
        ++v46;
        *v48++ = v51;
      }
    }
    *v48 = 0;
    do
      ++v7;
    while ( v121[v7] );
    if ( (_DWORD)v7 )
      CInstance::SetCHString(a2, L"SMBIOSBIOSVersion", v121);
    v52 = 0;
    rgsabound = 0;
    v53 = *(_DWORD *)(*(_QWORD *)&v29 + 10LL);
    if ( CSMBios::m_Version > 0x20000 )
      v4 = *(unsigned __int8 *)(*(_QWORD *)&v29 + 1LL) - 18;
    if ( CSMBios::m_Version >= 0x20004 )
      v4 = 2;
    if ( v53 )
    {
      do
      {
        if ( (v53 & 1) != 0 )
          ++v52;
        v53 >>= 1;
      }
      while ( v53 );
      rgsabound.cElements = v52;
    }
    v54 = 0;
    pv = 0;
    if ( v4 )
    {
      v55 = 0;
      do
      {
        v56 = *(unsigned __int8 *)(v55 + *(_QWORD *)&v29 + 18);
        if ( *(_BYTE *)(v55 + *(_QWORD *)&v29 + 18) )
        {
          do
          {
            if ( (v56 & 1) != 0 )
              ++v52;
            v56 >>= 1;
          }
          while ( v56 );
          rgsabound.cElements = v52;
        }
        pv = ++v54;
        v55 = v54;
      }
      while ( v54 < v4 );
    }
    VariantInit(&pvarg);
    parray = SafeArrayCreate(3u, 1u, &rgsabound);
    pvarg.llVal = (LONGLONG)parray;
    if ( !parray )
    {
      pExceptionObject = 0;
      throw (CHeap_Exception *)&pExceptionObject;
    }
    pvarg.vt = 8195;
    v58 = *(_DWORD *)(*(_QWORD *)&v29 + 10LL);
    rgIndices[0] = 0;
    v59 = 0;
    v60 = 0;
    v61 = 32;
    while ( 1 )
    {
      pv = v59;
      if ( v60 >= 0x20 || !v58 )
        break;
      if ( (v58 & 1) != 0 )
      {
        if ( SafeArrayPutElement(parray, rgIndices, &pv) == -2147024882 )
        {
          v113 = 0;
          throw (CHeap_Exception *)&v113;
        }
        ++rgIndices[0];
        v59 = pv;
        parray = pvarg.parray;
      }
      v58 >>= 1;
      v60 = ++v59;
    }
    v106.cElements = 0;
    pv = 0;
    for ( mm = 0; (unsigned int)mm < v4; mm = ++pv )
    {
      v63 = *(unsigned __int8 *)(mm + *(_QWORD *)&v107 + 18);
      for ( nn = 0; nn < 8 && v63; ++nn )
      {
        if ( (v63 & 1) != 0 )
        {
          v106.cElements = nn + v61;
          if ( SafeArrayPutElement(parray, rgIndices, &v106) == -2147024882 )
          {
            v114 = 0;
            throw (CHeap_Exception *)&v114;
          }
          ++rgIndices[0];
          parray = pvarg.parray;
        }
        v63 >>= 1;
      }
      v61 += 8;
    }
    if ( rgsabound.cElements )
      CInstance::SetVariant(a2, L"BiosCharacteristics", &pvarg);
    if ( CSMBios::m_Version >= 0x20004 )
    {
      v65 = (unsigned __int8 *)v107;
      CInstance::SetByte(a2, L"SystemBiosMajorVersion", *(_BYTE *)(*(_QWORD *)&v107 + 20LL));
      CInstance::SetByte(a2, L"SystemBiosMinorVersion", v65[21]);
      CInstance::SetByte(a2, L"EmbeddedControllerMajorVersion", v65[22]);
      CInstance::SetByte(a2, L"EmbeddedControllerMinorVersion", v65[23]);
    }
    v66 = VariantClear(&pvarg);
    if ( v66 < 0 )
      _com_issue_error(v66);
  }
  v67 = CSMBios::m_pSTTree;
  if ( !CSMBios::m_pSTTree )
    goto LABEL_209;
  while ( 2 )
  {
    v68 = (unsigned __int64)v67;
    v69 = (_BYTE **)v67[2];
    if ( **v69 < 0xDu )
    {
      v67 = (_QWORD *)v67[1];
      goto LABEL_141;
    }
    if ( **v69 > 0xDu )
    {
      v67 = (_QWORD *)*v67;
LABEL_141:
      v70 = 0;
      if ( !v67 )
        goto LABEL_146;
      continue;
    }
    break;
  }
  v70 = 1;
LABEL_146:
  v71 = -v70;
  if ( (v68 & -(__int64)(v71 != 0)) != 0 )
  {
    v72 = *(unsigned __int8 ***)((v68 & -(__int64)(v71 != 0)) + 0x10);
    goto LABEL_148;
  }
LABEL_209:
  ProviderLog::LocalLogMessage(
    captainsLog,
    L"SMBios Structure not found",
    L"onecore\\admin\\wmi\\wbem\\providers\\win32provider\\providers\\smbstruc.cpp",
    571,
    2);
  v72 = 0;
LABEL_148:
  if ( v72 )
  {
    v74 = *v72;
    CInstance::SetDWORD(a2, L"InstallableLanguages", (*v72)[4]);
    v75 = &v74[v74[1]];
    v76 = (unsigned __int8 *)CSMBios::m_pTable + CSMBios::m_Size;
    v77 = psz;
    for ( i1 = 1; v75 < v76 && v74[21] > i1 && *v75; ++i1 )
    {
      do
      {
        if ( !*v75 )
          break;
        ++v75;
      }
      while ( v75 < v76 );
      ++v75;
    }
    if ( v74[21] )
    {
      for ( i2 = 64; v75 < v76; --i2 )
      {
        v80 = *v75;
        if ( (unsigned __int8)v80 <= 0xFu || !i2 )
          break;
        ++v75;
        *v77++ = v80;
      }
    }
    *v77 = 0;
    CInstance::SetCHString(a2, L"CurrentLanguage", psz);
    v107 = 0;
    v107.cElements = v74[4];
    v81 = SafeArrayCreate(8u, 1u, &v107);
    if ( !v81 )
    {
      v117 = 0;
      throw (CHeap_Exception *)&v117;
    }
    rgIndices[0] = 0;
    if ( v74[4] )
    {
      v82 = 0;
      do
      {
        v83 = v82 + 1;
        v84 = &v74[v74[1]];
        v85 = (unsigned __int8 *)CSMBios::m_pTable + CSMBios::m_Size;
        v86 = psz;
        for ( i3 = 1; v84 < v85 && v83 > i3 && *v84; ++i3 )
        {
          do
          {
            if ( !*v84 )
              break;
            ++v84;
          }
          while ( v84 < v85 );
          ++v84;
        }
        if ( v83 )
        {
          for ( i4 = 64; v84 < v85; --i4 )
          {
            v89 = *v84;
            if ( (unsigned __int8)v89 <= 0xFu || !i4 )
              break;
            ++v84;
            *v86++ = v89;
          }
        }
        *v86 = 0;
        v90 = malloc(0x18u);
        if ( !v90 )
        {
          v116 = 0;
          throw (CHeap_Exception *)&v116;
        }
        v119 = v90;
        v90[1] = 0;
        *((_DWORD *)v90 + 4) = 1;
        v91 = SysAllocString(psz);
        *v90 = v91;
        if ( !v91 )
          _com_issue_error(-2147024882);
        v106 = (SAFEARRAYBOUND)v90;
        SafeArrayPutElement(v81, rgIndices, (void *)*v90);
        _bstr_t::Data_t::Release((_bstr_t::Data_t *)v90);
        v106 = 0;
        v82 = rgIndices[0] + 1;
        rgIndices[0] = v82;
      }
      while ( v82 < v74[4] );
    }
    CInstance::SetStringArray(a2, L"ListOfLanguages", v81);
    SafeArrayDestroy(v81);
  }
  CHString::~CHString((CHString *)v110);
LABEL_150:
  CHString::~CHString((CHString *)v105);
  CRegistry::~CRegistry((CRegistry *)v120);
  return 0;
}

```

## disassembly

```asm
0x180025f64  mov     [rsp+arg_0], rbx
0x180025f69  mov     [rsp+arg_10], rsi
0x180025f6e  push    rdi
0x180025f6f  push    r12
0x180025f71  push    r13
0x180025f73  push    r14
0x180025f75  push    r15
0x180025f77  sub     rsp, 0B40h
0x180025f7e  mov     rax, cs:__security_cookie
0x180025f85  xor     rax, rsp
0x180025f88  mov     [rsp+0B68h+var_38], rax
0x180025f90  mov     r13, rdx
0x180025f93  lea     r8, aDefaultSystemB; "Default System BIOS"
0x180025f9a  lea     rdx, aName; "Name"
0x180025fa1  mov     rcx, r13
0x180025fa4  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCHString(ushort const *,ushort const *)
0x180025faa  lea     r8, aOk; "OK"
0x180025fb1  lea     rdx, aStatus; "Status"
0x180025fb8  mov     rcx, r13
0x180025fbb  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x180025fc1  lea     rcx, [rsp+0B68h+var_AB8]
0x180025fc9  call    cs:__imp_??0CRegistry@@QEAA@XZ; CRegistry::CRegistry(void)
0x180025fcf  nop
0x180025fd0  mov     r9d, 20019h
0x180025fd6  lea     r8, aHardwareDescri; "HARDWARE\\Description\\System"
0x180025fdd  mov     rdx, 0FFFFFFFF80000002h
0x180025fe4  lea     rcx, [rsp+0B68h+var_AB8]
0x180025fec  call    cs:__imp_?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong)
0x180025ff2  xor     r14d, r14d
0x180025ff5  test    eax, eax
0x180025ff7  jnz     loc_180026D0F
0x180025ffd  lea     rcx, [rsp+0B68h+var_B10]
0x180026002  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180026008  nop
0x180026009  lea     r8, [rsp+0B68h+var_B10]
0x18002600e  lea     rdx, aSystembiosdate; "SystemBiosDate"
0x180026015  lea     rcx, [rsp+0B68h+var_AB8]
0x18002601d  call    cs:__imp_?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z; CRegistry::GetCurrentKeyValue(ushort const *,CHString &)
0x180026023  test    eax, eax
0x180026025  jz      short loc_180026039
0x180026027  lea     rdx, word_180128816
0x18002602e  lea     rcx, [rsp+0B68h+var_B10]
0x180026033  call    cs:__imp_??4CHString@@QEAAAEBV0@PEBD@Z; CHString::operator=(char const *)
0x180026039  lea     r8, [rsp+0B68h+var_B10]; struct CHString *
0x18002603e  mov     rdx, r13; struct CInstance *
0x180026041  call    ?SetBiosDate@CWin32BIOS@@QEAAXPEAVCInstance@@AEAVCHString@@@Z; CWin32BIOS::SetBiosDate(CInstance *,CHString &)
0x180026046  lea     rcx, [rsp+0B68h+var_AB8]
0x18002604e  call    cs:__imp_?GethKey@CRegistry@@QEAAPEAUHKEY__@@XZ; CRegistry::GethKey(void)
0x180026054  mov     rbx, rax
0x180026057  mov     [rsp+0B68h+Type], r14d
0x18002605c  mov     r8d, 410h; Size
0x180026062  mov     [rsp+0B68h+cbData], r8d
0x180026067  xor     edx, edx; Val
0x180026069  lea     rcx, [rsp+0B68h+Data]; void *
0x180026071  call    memset_0
0x180026076  lea     rax, [rsp+0B68h+cbData]
0x18002607b  mov     [rsp+0B68h+lpcbData], rax; lpcbData
0x180026080  lea     rax, [rsp+0B68h+Data]
0x180026088  mov     [rsp+0B68h+lpData], rax; lpData
0x18002608d  lea     r9, [rsp+0B68h+Type]; lpType
0x180026092  xor     r8d, r8d; lpReserved
0x180026095  lea     rdx, aSystembiosvers; "SystemBiosVersion"
0x18002609c  mov     rcx, rbx; hKey
0x18002609f  call    cs:__imp_RegQueryValueExW
0x1800260a5  test    eax, eax
0x1800260a7  jz      loc_180026A53
0x1800260ad  lea     rdx, aUnknown_1; "UNKNOWN"
0x1800260b4  lea     rcx, [rsp+0B68h+var_B10]
0x1800260b9  call    cs:__imp_??4CHString@@QEAAAEBV0@PEBG@Z; CHString::operator=(ushort const *)
0x1800260bf  lea     r8, [rsp+0B68h+var_B10]
0x1800260c4  lea     rdx, aVersion; "Version"
0x1800260cb  mov     rcx, r13
0x1800260ce  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x1800260d4  mov     edi, 1
0x1800260d9  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800260dd  lea     rcx, [rsp+0B68h+var_B10]
0x1800260e2  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800260e8  lea     rcx, [rsp+0B68h+var_B28]
0x1800260ed  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800260f3  nop
0x1800260f4  lea     r8, [rsp+0B68h+var_B28]
0x1800260f9  lea     rdx, aName; "Name"
0x180026100  mov     rcx, r13
0x180026103  call    cs:__imp_?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z; CInstance::GetCHString(ushort const *,CHString &)
0x180026109  test    al, al
0x18002610b  jz      short loc_18002614C
0x18002610d  lea     r8, [rsp+0B68h+var_B28]
0x180026112  lea     rdx, aCaption; "Caption"
0x180026119  mov     rcx, r13
0x18002611c  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x180026122  lea     r8, [rsp+0B68h+var_B28]
0x180026127  lea     rdx, aSoftwareelemen; "SoftwareElementID"
0x18002612e  mov     rcx, r13
0x180026131  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x180026137  lea     r8, [rsp+0B68h+var_B28]
0x18002613c  lea     rdx, aDescription; "Description"
0x180026143  mov     rcx, r13
0x180026146  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x18002614c  mov     eax, 3
0x180026151  mov     word ptr [rsp+0B68h+rgIndices], ax
0x180026156  lea     r8, [rsp+0B68h+rgIndices]
0x18002615b  lea     rdx, aSoftwareelemen_0; "SoftwareElementState"
0x180026162  mov     rcx, r13
0x180026165  call    cs:__imp_?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z; CInstance::SetWBEMINT16(ushort const *,short const &)
0x18002616b  mov     word ptr [rsp+0B68h+rgIndices], r14w
0x180026171  lea     r8, [rsp+0B68h+rgIndices]
0x180026176  lea     rdx, aTargetoperatin; "TargetOperatingSystem"
0x18002617d  mov     rcx, r13
0x180026180  call    cs:__imp_?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z; CInstance::SetWBEMINT16(ushort const *,short const &)
0x180026186  mov     r8b, dil
0x180026189  lea     rdx, aPrimarybios; "PrimaryBIOS"
0x180026190  mov     rcx, r13
0x180026193  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x180026199  mov     [rsp+0B68h+var_B20.cElements], r14d
0x18002619e  lea     rcx, [rsp+0B68h+var_B20]; this
0x1800261a3  call    ?Init@CSMBios@@QEAAHH@Z; CSMBios::Init(int)
0x1800261a8  test    eax, eax
0x1800261aa  jz      loc_180026CF7
0x1800261b0  lea     rcx, [rsp+0B68h+var_B00]
0x1800261b5  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800261bb  nop
0x1800261bc  mov     ebx, cs:?m_Version@CSMBios@@0KA; ulong CSMBios::m_Version
0x1800261c2  mov     r8b, dil
0x1800261c5  lea     rdx, aSmbiospresent; "SMBIOSPresent"
0x1800261cc  mov     rcx, r13
0x1800261cf  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x1800261d5  mov     r8d, ebx
0x1800261d8  shr     r8d, 10h
0x1800261dc  lea     rdx, aSmbiosmajorver; "SMBIOSMajorVersion"
0x1800261e3  mov     rcx, r13
0x1800261e6  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x1800261ec  movzx   r8d, bx
0x1800261f0  lea     rdx, aSmbiosminorver; "SMBIOSMinorVersion"
0x1800261f7  mov     rcx, r13
0x1800261fa  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x180026200  mov     rdx, cs:?m_pSTTree@CSMBios@@0PEAXEA; void * CSMBios::m_pSTTree
0x180026207  test    rdx, rdx
0x18002620a  jz      loc_180026BFD
0x180026210  mov     r8, rdx
0x180026213  mov     rax, [rdx+10h]
0x180026217  mov     rcx, [rax]
0x18002621a  cmp     [rcx], dil
0x18002621d  jnb     short loc_18002622D
0x18002621f  mov     rdx, [rdx+8]
0x180026223  mov     eax, r14d
0x180026226  test    rdx, rdx
0x180026229  jnz     short loc_180026210
0x18002622b  jmp     short loc_180026236
0x18002622d  jbe     short loc_180026234
0x18002622f  mov     rdx, [rdx]
0x180026232  jmp     short loc_180026223
0x180026234  mov     eax, edi
0x180026236  neg     eax
0x180026238  sbb     rcx, rcx
0x18002623b  and     rcx, r8
0x18002623e  jz      loc_180026BFD
0x180026244  mov     rbx, [rcx+10h]
0x180026248  test    rbx, rbx
0x18002624b  jz      loc_18002630F
0x180026251  mov     rbx, [rbx]
0x180026254  movzx   esi, byte ptr [rbx+7]
0x180026258  mov     edx, 100h
0x18002625d  lea     rcx, [rsp+0B68h+var_B00]
0x180026262  call    cs:__imp_?GetBuffer@CHString@@QEAAPEAGH@Z; CHString::GetBuffer(int)
0x180026268  mov     r9, rax
0x18002626b  movzx   ecx, byte ptr [rbx+1]
0x18002626f  add     rcx, rbx
0x180026272  mov     edx, cs:?m_Size@CSMBios@@0KA; ulong CSMBios::m_Size
0x180026278  add     rdx, cs:?m_pTable@CSMBios@@0PEAU_tagSHF@@EA; _tagSHF * CSMBios::m_pTable
0x18002627f  mov     r8d, edi
0x180026282  jmp     short loc_18002628A
0x180026284  add     r8d, edi
0x180026287  add     rcx, rdi
0x18002628a  cmp     rcx, rdx
0x18002628d  jnb     short loc_1800262A8
0x18002628f  cmp     esi, r8d
0x180026292  jbe     short loc_1800262A8
0x180026294  cmp     [rcx], r14b
0x180026297  jz      short loc_1800262A8
0x180026299  cmp     [rcx], r14b
0x18002629c  jz      short loc_180026284
0x18002629e  add     rcx, rdi
0x1800262a1  cmp     rcx, rdx
0x1800262a4  jb      short loc_180026299
0x1800262a6  jmp     short loc_180026284
0x1800262a8  test    esi, esi
0x1800262aa  jz      short loc_1800262D9
0x1800262ac  mov     r8d, 40h ; '@'
0x1800262b2  cmp     rcx, rdx
0x1800262b5  jnb     short loc_1800262D9
0x1800262b7  lea     r15d, [r8-3Eh]
0x1800262bb  movzx   eax, byte ptr [rcx]
0x1800262be  cmp     al, 0Fh
0x1800262c0  jbe     short loc_1800262D9
0x1800262c2  test    r8d, r8d
0x1800262c5  jz      short loc_1800262D9
0x1800262c7  add     rcx, rdi
0x1800262ca  mov     [r9], ax
0x1800262ce  add     r9, r15
0x1800262d1  sub     r8d, edi
0x1800262d4  cmp     rcx, rdx
0x1800262d7  jb      short loc_1800262BB
0x1800262d9  mov     [r9], r14w
0x1800262dd  mov     edx, r12d
0x1800262e0  lea     rcx, [rsp+0B68h+var_B00]
0x1800262e5  call    cs:__imp_?ReleaseBuffer@CHString@@QEAAXH@Z; CHString::ReleaseBuffer(int)
0x1800262eb  lea     rcx, [rsp+0B68h+var_B00]
0x1800262f0  call    cs:__imp_?IsEmpty@CHString@@QEBAHXZ; CHString::IsEmpty(void)
0x1800262f6  test    eax, eax
0x1800262f8  jnz     short loc_18002630F
0x1800262fa  lea     r8, [rsp+0B68h+var_B00]
0x1800262ff  lea     rdx, aSerialnumber; "SerialNumber"
0x180026306  mov     rcx, r13
0x180026309  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x18002630f  mov     r15d, 2
0x180026315  mov     rdx, cs:?m_pSTTree@CSMBios@@0PEAXEA; void * CSMBios::m_pSTTree
0x18002631c  test    rdx, rdx
0x18002631f  jz      loc_180026C2E
0x180026325  mov     r8, rdx
0x180026328  mov     rax, [rdx+10h]
0x18002632c  mov     rcx, [rax]
0x18002632f  cmp     [rcx], r14b
0x180026332  jbe     short loc_180026344
0x180026334  mov     rax, [rdx]
0x180026337  mov     rdx, rax
0x18002633a  mov     ecx, r14d
0x18002633d  test    rax, rax
0x180026340  jnz     short loc_180026325
0x180026342  jmp     short loc_180026346
0x180026344  mov     ecx, edi
0x180026346  neg     ecx
0x180026348  sbb     rax, rax
0x18002634b  and     rax, r8
0x18002634e  jz      loc_180026C2E
0x180026354  mov     rcx, [rax+10h]
0x180026358  test    rcx, rcx
0x18002635b  jz      loc_180026BA3
0x180026361  mov     rsi, [rcx]
0x180026364  mov     qword ptr [rsp+0B68h+var_B18.cElements], rsi
0x180026369  movzx   r8d, byte ptr [rsi+4]
0x18002636e  movzx   ecx, byte ptr [rsi+1]
0x180026372  add     rcx, rsi
0x180026375  mov     edx, cs:?m_Size@CSMBios@@0KA; ulong CSMBios::m_Size
0x18002637b  add     rdx, cs:?m_pTable@CSMBios@@0PEAU_tagSHF@@EA; _tagSHF * CSMBios::m_pTable
0x180026382  lea     r9, [rsp+0B68h+var_858]
0x18002638a  mov     eax, edi
0x18002638c  jmp     short loc_180026393
0x18002638e  add     eax, edi
0x180026390  add     rcx, rdi
0x180026393  cmp     rcx, rdx
0x180026396  jnb     short loc_1800263B1
0x180026398  cmp     r8d, eax
0x18002639b  jbe     short loc_1800263B1
0x18002639d  cmp     [rcx], r14b
0x1800263a0  jz      short loc_1800263B1
0x1800263a2  cmp     [rcx], r14b
0x1800263a5  jz      short loc_18002638E
0x1800263a7  add     rcx, rdi
0x1800263aa  cmp     rcx, rdx
0x1800263ad  jb      short loc_1800263A2
0x1800263af  jmp     short loc_18002638E
0x1800263b1  test    r8d, r8d
0x1800263b4  jz      short loc_1800263DC
0x1800263b6  mov     r8d, 40h ; '@'
0x1800263bc  cmp     rcx, rdx
0x1800263bf  jnb     short loc_1800263DC
0x1800263c1  movzx   eax, byte ptr [rcx]
0x1800263c4  cmp     al, 0Fh
0x1800263c6  jbe     short loc_1800263DC
0x1800263c8  test    r8d, r8d
0x1800263cb  jz      short loc_1800263DC
0x1800263cd  add     rcx, rdi
0x1800263d0  mov     [r9], ax
0x1800263d4  add     r9, r15
0x1800263d7  sub     r8d, edi
0x1800263da  jmp     short loc_1800263BC
0x1800263dc  mov     [r9], r14w
0x1800263e0  lea     rcx, [rsp+0B68h+var_858]
0x1800263e8  mov     rax, r12
0x1800263eb  inc     rax
0x1800263ee  cmp     [rcx+rax*2], r14w
0x1800263f3  jnz     short loc_1800263EB
0x1800263f5  test    eax, eax
0x1800263f7  jz      short loc_180026411
0x1800263f9  lea     r8, [rsp+0B68h+var_858]
0x180026401  lea     rdx, aManufacturer; "Manufacturer"
0x180026408  mov     rcx, r13
0x18002640b  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCHString(ushort const *,ushort const *)
0x180026411  movzx   ebx, byte ptr [rsi+8]
0x180026415  mov     edx, 100h
0x18002641a  lea     rcx, [rsp+0B68h+var_B28]
0x18002641f  call    cs:__imp_?GetBuffer@CHString@@QEAAPEAGH@Z; CHString::GetBuffer(int)
0x180026425  mov     r10, rax
0x180026428  movzx   ecx, byte ptr [rsi+1]
0x18002642c  add     rcx, rsi
0x18002642f  mov     r8d, cs:?m_Size@CSMBios@@0KA; ulong CSMBios::m_Size
0x180026436  add     r8, cs:?m_pTable@CSMBios@@0PEAU_tagSHF@@EA; _tagSHF * CSMBios::m_pTable
0x18002643d  mov     r9, rax
0x180026440  mov     edx, edi
0x180026442  jmp     short loc_180026449
  ... truncated ...
```
