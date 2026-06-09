# CWin32ComputerSystem::GetOEMInfo(CInstance *)

- ea: `0x180025564`
- end: `0x180025f5d`
- name: `?GetOEMInfo@CWin32ComputerSystem@@AEAAXPEAVCInstance@@@Z`
- size: `2553`
- prototype: `void __fastcall(CWin32ComputerSystem *__hidden this, struct CInstance *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180024dd4`

## callees

- `0x1800127e0`
- `0x180013ae0`
- `0x180014c58`
- `0x180025564`
- `0x18002e964`
- `0x180045604`
- `0x1800459a4`
- `0x180045ae0`
- `0x180045b58`
- `0x18008bb9c`
- `0x1800f4370`
- `0x1800fc902`
- `0x1800fc980`

## import_xrefs

- `msvcrt!_itow` at `0x180025895`
- `msvcrt!_itow` at `0x180025d94`
- `msvcrt!_itow` at `0x180025895`
- `msvcrt!_itow` at `0x180025d94`
- `ntdll!RtlInitUnicodeString` at `0x1800258f7`
- `ntdll!RtlInitUnicodeString` at `0x18002590d`
- `ntdll!RtlInitUnicodeString` at `0x1800258f7`
- `ntdll!RtlInitUnicodeString` at `0x18002590d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180025634`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180025634`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025b50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025b50`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025c72`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025c72`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180025c06`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180025c06`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180025b30`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180025b30`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180025ba1`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180025ba1`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180025e23`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180025e7f`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180025e23`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180025e7f`
- `framedynos!?IsNull@CInstance@@QEBA_NPEBG@Z` at `0x1800257c6`
- `framedynos!?IsNull@CInstance@@QEBA_NPEBG@Z` at `0x1800257de`
- `framedynos!?IsNull@CInstance@@QEBA_NPEBG@Z` at `0x1800257c6`
- `framedynos!?IsNull@CInstance@@QEBA_NPEBG@Z` at `0x1800257de`
- `framedynos!?SetVariant@CInstance@@QEAA_NPEBGAEBUtagVARIANT@@@Z` at `0x180025c27`
- `framedynos!?SetVariant@CInstance@@QEAA_NPEBGAEBUtagVARIANT@@@Z` at `0x180025f16`
- `framedynos!?SetVariant@CInstance@@QEAA_NPEBGAEBUtagVARIANT@@@Z` at `0x180025c27`
- `framedynos!?SetVariant@CInstance@@QEAA_NPEBGAEBUtagVARIANT@@@Z` at `0x180025f16`
- `OLEAUT32!__imp_SysAllocString` at `0x180025cee`
- `OLEAUT32!__imp_SysAllocString` at `0x180025cee`
- `OLEAUT32!__imp_VariantInit` at `0x1800257f6`
- `OLEAUT32!__imp_VariantInit` at `0x1800257f6`
- `OLEAUT32!__imp_VariantClear` at `0x180025a3f`
- `OLEAUT32!__imp_VariantClear` at `0x180025b5c`
- `OLEAUT32!__imp_VariantClear` at `0x180025a3f`
- `OLEAUT32!__imp_VariantClear` at `0x180025b5c`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180025809`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180025bbc`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180025809`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180025bbc`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180025be5`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180025be5`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180025c12`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180025c12`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180025d1e`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180025d1e`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x180025ca3`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x180025ca3`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CWin32ComputerSystem::GetOEMInfo(CWin32ComputerSystem *this, struct CInstance *a2)
{
  __int64 v3; // rax
  __int64 v4; // rdx
  WCHAR *p_Buffer; // rax
  __int64 v6; // r8
  __int64 v7; // r15
  __int64 v8; // rcx
  const OLECHAR *v9; // r9
  __int64 v10; // rax
  WCHAR *v11; // rdx
  OLECHAR v12; // r8
  WCHAR *v13; // rcx
  __int64 v14; // rcx
  WCHAR *v15; // r8
  __int64 v16; // rdx
  WCHAR *p_FileName; // rax
  WCHAR v18; // r9
  WCHAR *v19; // rcx
  __int64 v20; // rdx
  WCHAR *v21; // rax
  __int64 v22; // r8
  __int64 v23; // rcx
  const wchar_t *v24; // r9
  __int64 v25; // rax
  wchar_t *v26; // rdx
  wchar_t v27; // r8
  wchar_t *v28; // rcx
  __int64 v29; // rcx
  const wchar_t *v30; // r8
  __int64 v31; // rdx
  WCHAR *p_SourceString; // rax
  wchar_t v33; // r9
  WCHAR *v34; // rcx
  wchar_t *v35; // rax
  int v36; // r14d
  int v37; // eax
  int v38; // r12d
  unsigned int v39; // edx
  int v40; // r8d
  const wchar_t *v41; // r9
  __int64 v42; // rcx
  __int64 v43; // r8
  wchar_t *v44; // rax
  wchar_t v45; // r10
  wchar_t *v46; // rcx
  CInstance *v47; // r14
  HRESULT v48; // eax
  __int64 v49; // rcx
  WCHAR *v50; // r8
  __int64 v51; // rdx
  WCHAR *v52; // rax
  WCHAR v53; // r9
  WCHAR *v54; // rcx
  __int64 v55; // rdx
  WCHAR *v56; // rax
  __int64 v57; // r8
  const wchar_t *v58; // rcx
  __int64 v59; // rsi
  wchar_t *v60; // rax
  wchar_t v61; // dx
  wchar_t *v62; // rcx
  CInstance *v63; // rax
  CInstance *v64; // rdi
  HRESULT v65; // eax
  SAFEARRAY *v66; // rax
  BSTR *v67; // rax
  BSTR *v68; // r14
  BSTR v69; // rax
  BSTR v70; // r8
  __int64 v71; // rcx
  const wchar_t *v72; // r8
  __int64 v73; // rdx
  WCHAR *v74; // rax
  wchar_t v75; // r9
  WCHAR *v76; // rcx
  wchar_t *v77; // rax
  SAFEARRAYBOUND rgsabound; // [rsp+40h] [rbp-888h] BYREF
  unsigned int v79; // [rsp+48h] [rbp-880h]
  VARIANTARG pvarg; // [rsp+50h] [rbp-878h] BYREF
  DWORD NumberOfBytesRead; // [rsp+68h] [rbp-860h] BYREF
  int v82; // [rsp+6Ch] [rbp-85Ch] BYREF
  int v83; // [rsp+70h] [rbp-858h] BYREF
  LONG rgIndices; // [rsp+74h] [rbp-854h] BYREF
  int v85; // [rsp+78h] [rbp-850h] BYREF
  int pExceptionObject; // [rsp+7Ch] [rbp-84Ch] BYREF
  BSTR *v87; // [rsp+80h] [rbp-848h] BYREF
  CInstance *v88; // [rsp+88h] [rbp-840h]
  void *ppvData[2]; // [rsp+90h] [rbp-838h] BYREF
  _QWORD v90[18]; // [rsp+A0h] [rbp-828h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+130h] [rbp-798h] BYREF
  struct _UNICODE_STRING v92; // [rsp+140h] [rbp-788h] BYREF
  int v93; // [rsp+150h] [rbp-778h]
  __int64 v94; // [rsp+158h] [rbp-770h]
  int v95; // [rsp+160h] [rbp-768h]
  wchar_t *p_psz; // [rsp+168h] [rbp-760h]
  int v97; // [rsp+170h] [rbp-758h]
  int v98; // [rsp+174h] [rbp-754h]
  int v99; // [rsp+178h] [rbp-750h]
  wchar_t *v100; // [rsp+180h] [rbp-748h]
  WCHAR SourceString; // [rsp+230h] [rbp-698h] BYREF
  __int128 v102; // [rsp+232h] [rbp-696h]
  _BYTE v103[26]; // [rsp+242h] [rbp-686h] BYREF
  wchar_t psz; // [rsp+260h] [rbp-668h] BYREF
  char v105[508]; // [rsp+262h] [rbp-666h] BYREF
  __int16 v106; // [rsp+45Eh] [rbp-46Ah]
  WCHAR FileName; // [rsp+460h] [rbp-468h] BYREF
  _BYTE v108[526]; // [rsp+462h] [rbp-466h] BYREF
  WCHAR Buffer; // [rsp+670h] [rbp-258h] BYREF
  char v110[526]; // [rsp+672h] [rbp-256h] BYREF

  v88 = a2;
  Buffer = 0;
  memset_0(v110, 0, 0x208u);
  FileName = 0;
  memset_0(v108, 0, 0x208u);
  psz = 0;
  memset_0(v105, 0, 0x1FEu);
  SourceString = 0;
  v102 = 0;
  memset(v103, 0, sizeof(v103));
  NumberOfBytesRead = 0;
  ppvData[0] = 0;
  v87 = 0;
  if ( GetSystemDirectoryW(&Buffer, 0x105u) - 1 > 0x103 )
    goto LABEL_89;
  v3 = -1;
  do
    ++v3;
  while ( *(_WORD *)&v110[2 * v3 - 2] );
  if ( *(_WORD *)&v108[2 * v3 + 524] == 92 )
  {
    v7 = 2147483646;
  }
  else
  {
    v4 = 261;
    p_Buffer = &Buffer;
    do
    {
      if ( !*p_Buffer )
        break;
      ++p_Buffer;
      --v4;
    }
    while ( v4 );
    v6 = (261 - v4) & -(__int64)(v4 != 0);
    v7 = 2147483646;
    if ( v4 )
    {
      v8 = 2147483646;
      v9 = L"\\";
      v10 = 261 - v6;
      v11 = (WCHAR *)&v110[2 * v6 - 2];
      if ( v6 != 261 )
      {
        do
        {
          if ( !v8 )
            break;
          v12 = *v9;
          if ( !*v9 )
            break;
          ++v9;
          *v11++ = v12;
          --v8;
          --v10;
        }
        while ( v10 );
      }
      v13 = v11 - 1;
      if ( v10 )
        v13 = v11;
      *v13 = 0;
    }
  }
  v14 = 2147483646;
  v15 = &Buffer;
  v16 = 261;
  p_FileName = &FileName;
  do
  {
    if ( !v14 )
      break;
    v18 = *v15;
    if ( !*v15 )
      break;
    ++v15;
    *p_FileName++ = v18;
    --v14;
    --v16;
  }
  while ( v16 );
  v19 = p_FileName - 1;
  if ( v16 )
    v19 = p_FileName;
  *v19 = 0;
  v20 = 261;
  v21 = &FileName;
  do
  {
    if ( !*v21 )
      break;
    ++v21;
    --v20;
  }
  while ( v20 );
  v22 = (261 - v20) & -(__int64)(v20 != 0);
  if ( v20 )
  {
    v23 = 2147483646;
    v24 = L"OemInfo.Ini";
    v25 = 261 - v22;
    v26 = (wchar_t *)&v108[2 * v22 - 2];
    if ( v22 != 261 )
    {
      do
      {
        if ( !v23 )
          break;
        v27 = *v24;
        if ( !*v24 )
          break;
        ++v24;
        *v26++ = v27;
        --v23;
        --v25;
      }
      while ( v25 );
    }
    v28 = v26 - 1;
    if ( v25 )
      v28 = v26;
    *v28 = 0;
  }
  if ( CInstance::IsNull(a2, L"Manufacturer")
    && WMI_FILE_GetPrivateProfileStringW(
         L"General",
         L"Manufacturer",
         (const unsigned __int16 *)&Data,
         &psz,
         0x100u,
         &FileName) )
  {
    CInstance::SetCharSplat(a2, L"Manufacturer", &psz);
  }
  if ( CInstance::IsNull(a2, L"Model")
    && WMI_FILE_GetPrivateProfileStringW(L"General", L"Model", (const unsigned __int16 *)&Data, &psz, 0x100u, &FileName) )
  {
    CInstance::SetCharSplat(a2, L"Model", &psz);
  }
  rgsabound = 0;
  VariantInit(&pvarg);
  pvarg.llVal = (LONGLONG)SafeArrayCreate(8u, 1u, &rgsabound);
  if ( !pvarg.llVal )
  {
    pExceptionObject = 0;
    throw (CHeap_Exception *)&pExceptionObject;
  }
  pvarg.vt = 8200;
  v79 = 1;
  v29 = 2147483646;
  v30 = L"Line";
  v31 = 22;
  p_SourceString = &SourceString;
  do
  {
    if ( !v29 )
      break;
    v33 = *v30;
    if ( !*v30 )
      break;
    ++v30;
    *p_SourceString++ = v33;
    --v29;
    --v31;
  }
  while ( v31 );
  v34 = p_SourceString - 1;
  if ( v31 )
    v34 = p_SourceString;
  *v34 = 0;
  v35 = _itow(1, &psz, 10);
  StringCbCatW(&SourceString, 0x2Cu, v35);
  while ( 1 )
  {
    v36 = 256;
    CWMI_FILE_IniFile::CWMI_FILE_IniFile((CWMI_FILE_IniFile *)v90);
    v90[0] = 0;
    v93 = 0;
    v90[13] = &FileName;
    RtlInitUnicodeString(&DestinationString, L"Support Information");
    RtlInitUnicodeString(&v92, &SourceString);
    if ( HIDWORD(v90[0]) )
    {
      p_psz = &psz;
      v97 = 0;
      v94 = 0;
      v95 = 0;
    }
    else
    {
      v99 = 256;
      v98 = 0;
      v100 = &psz;
    }
    v37 = CWMI_FILE_IniFile::ReadWriteIniFileOnDisk((CWMI_FILE_IniFile *)v90);
    v38 = v37;
    if ( v37 >= 0 )
    {
      if ( (unsigned int)(LODWORD(v90[0]) - 2) <= 2 )
        CWMI_FILE_IniFile::AppendBufferToResultBuffer((CWMI_FILE_IniFile *)v90, 0, 0, 0, 1);
    }
    else if ( v37 != -2147483643 )
    {
      goto LABEL_48;
    }
    if ( !HIDWORD(v90[0]) )
      v36 = v98;
LABEL_48:
    CWMI_FILE_IniFile::~CWMI_FILE_IniFile((CWMI_FILE_IniFile *)v90);
    if ( v38 >= 0 )
    {
      SetLastError(0);
      v39 = v36 - 1;
      if ( !v36 )
        v39 = 0;
    }
    else
    {
      if ( v38 == -2147483643 )
      {
        v39 = 255;
        goto LABEL_63;
      }
      v39 = 1;
      v40 = 1;
      v41 = L"@";
      do
      {
        if ( asc_180128984[v39 - 1] != 32 )
          break;
        v39 = v40 - 1;
        v40 = v39;
      }
      while ( v39 );
      if ( v39 >= 0x100 )
        v39 = 255;
      v42 = v39;
      if ( v39 > 0x7FFFFFFEuLL )
      {
        psz = 0;
      }
      else
      {
        v43 = 256;
        v44 = &psz;
        do
        {
          if ( !v42 )
            break;
          v45 = *v41;
          if ( !*v41 )
            break;
          ++v41;
          *v44++ = v45;
          --v42;
          --v43;
        }
        while ( v43 );
        v46 = v44 - 1;
        if ( v43 )
          v46 = v44;
        *v46 = 0;
      }
    }
    if ( v39 >= 0x100 )
    {
      v106 = 0;
      goto LABEL_101;
    }
LABEL_63:
    *(_WORD *)&v105[2 * v39 - 2] = 0;
    if ( v39 <= 1 && psz == 64 )
      break;
LABEL_101:
    rgIndices = rgsabound.cElements++;
    if ( SafeArrayRedim(pvarg.parray, &rgsabound) == -2147024882 )
    {
      v83 = 0;
      throw (CHeap_Exception *)&v83;
    }
    _bstr_t::_Free((_bstr_t *)&v87);
    v67 = (BSTR *)operator new(0x18u);
    v68 = v67;
    ppvData[1] = v67;
    if ( v67 )
    {
      v67[1] = 0;
      *((_DWORD *)v67 + 4) = 1;
      v69 = SysAllocString(&psz);
      *v68 = v69;
      if ( !v69 )
        _com_issue_error(-2147024882);
    }
    else
    {
      v68 = 0;
    }
    v87 = v68;
    if ( v68 )
      v70 = *v68;
    else
      v70 = 0;
    if ( SafeArrayPutElement(pvarg.parray, &rgIndices, v70) == -2147024882 )
    {
      v85 = 0;
      throw (CHeap_Exception *)&v85;
    }
    v71 = 2147483646;
    v72 = L"Line";
    v73 = 22;
    v74 = &SourceString;
    do
    {
      if ( !v71 )
        break;
      v75 = *v72;
      if ( !*v72 )
        break;
      ++v72;
      *v74++ = v75;
      --v71;
      --v73;
    }
    while ( v73 );
    v76 = v74 - 1;
    if ( v73 )
      v76 = v74;
    *v76 = 0;
    v77 = _itow(++v79, &psz, 10);
    StringCbCatW(&SourceString, 0x2Cu, v77);
  }
  v47 = v88;
  if ( v79 > 1 )
    CInstance::SetVariant(v88, L"SupportContactDescription", &pvarg);
  v48 = VariantClear(&pvarg);
  if ( v48 < 0 )
    _com_issue_error(v48);
  v49 = 2147483646;
  v50 = &Buffer;
  v51 = 261;
  v52 = &FileName;
  do
  {
    if ( !v49 )
      break;
    v53 = *v50;
    if ( !*v50 )
      break;
    ++v50;
    *v52++ = v53;
    --v49;
    --v51;
  }
  while ( v51 );
  v54 = v52 - 1;
  if ( v51 )
    v54 = v52;
  *v54 = 0;
  v55 = 261;
  v56 = &FileName;
  do
  {
    if ( !*v56 )
      break;
    ++v56;
    --v55;
  }
  while ( v55 );
  v57 = (261 - v55) & -(__int64)(v55 != 0);
  if ( v55 )
  {
    v58 = L"OemLogo.Bmp";
    v59 = 261 - v57;
    v60 = (wchar_t *)&v108[2 * v57 - 2];
    if ( 261 != v57 )
    {
      do
      {
        if ( !v7 )
          break;
        v61 = *v58;
        if ( !*v58 )
          break;
        ++v58;
        *v60++ = v61;
        --v7;
        --v59;
      }
      while ( v59 );
    }
    v62 = v60 - 1;
    if ( v59 )
      v62 = v60;
    *v62 = 0;
  }
  v63 = (CInstance *)CreateFileW(&FileName, 0x80000000, 1u, 0, 3u, 0x8000080u, 0);
  v64 = v63;
  v88 = v63;
  if ( v63 != (CInstance *)-1LL )
  {
    rgsabound.cElements = GetFileSize(v63, 0);
    rgsabound.lLbound = 0;
    v66 = SafeArrayCreate(0x11u, 1u, &rgsabound);
    pvarg.llVal = (LONGLONG)v66;
    if ( !v66 )
    {
      v82 = 0;
      throw (CHeap_Exception *)&v82;
    }
    pvarg.vt = 8209;
    SafeArrayAccessData(v66, ppvData);
    try
    {
      ReadFile(v64, ppvData[0], rgsabound.cElements, &NumberOfBytesRead, 0);
    }
    catch ( ... )
    {
      SafeArrayUnaccessData(pvarg.parray);
      throw;
    }
    SafeArrayUnaccessData(pvarg.parray);
    CInstance::SetVariant(v47, L"OEMLogoBitmap", &pvarg);
  }
  if ( v64 != (CInstance *)-1LL )
    CloseHandle(v64);
  v65 = VariantClear(&pvarg);
  if ( v65 < 0 )
    _com_issue_error(v65);
LABEL_89:
  _bstr_t::_Free((_bstr_t *)&v87);
}

```

## disassembly

```asm
0x180025564  push    rbx
0x180025566  push    rsi
0x180025567  push    rdi
0x180025568  push    r12
0x18002556a  push    r14
0x18002556c  push    r15
0x18002556e  sub     rsp, 898h
0x180025575  mov     rax, cs:__security_cookie
0x18002557c  xor     rax, rsp
0x18002557f  mov     [rsp+8C8h+var_48], rax
0x180025587  mov     r14, rdx
0x18002558a  mov     [rsp+8C8h+var_840], rdx
0x180025592  xor     r12d, r12d
0x180025595  mov     [rsp+8C8h+Buffer], r12w
0x18002559e  mov     ebx, 208h
0x1800255a3  mov     r8d, ebx; Size
0x1800255a6  xor     edx, edx; Val
0x1800255a8  lea     rcx, [rsp+8C8h+var_256]; void *
0x1800255b0  call    memset_0
0x1800255b5  mov     [rsp+8C8h+FileName], r12w
0x1800255be  mov     r8d, ebx; Size
0x1800255c1  xor     edx, edx; Val
0x1800255c3  lea     rcx, [rsp+8C8h+var_466]; void *
0x1800255cb  call    memset_0
0x1800255d0  mov     [rsp+8C8h+psz], r12w
0x1800255d9  xor     edx, edx; Val
0x1800255db  lea     r8d, [rbx-0Ah]; Size
0x1800255df  lea     rcx, [rsp+8C8h+var_666]; void *
0x1800255e7  call    memset_0
0x1800255ec  mov     [rsp+8C8h+SourceString], r12w
0x1800255f5  xorps   xmm0, xmm0
0x1800255f8  movups  [rsp+8C8h+var_696], xmm0
0x180025600  movups  xmmword ptr [rsp+8C8h+var_686], xmm0
0x180025608  movups  xmmword ptr [rsp+8C8h+var_686+0Ah], xmm0
0x180025610  mov     [rsp+8C8h+NumberOfBytesRead], r12d
0x180025615  mov     [rsp+8C8h+ppvData], r12
0x18002561d  mov     [rsp+8C8h+var_848], r12
0x180025625  mov     esi, 105h
0x18002562a  mov     edx, esi; uSize
0x18002562c  lea     rcx, [rsp+8C8h+Buffer]; lpBuffer
0x180025634  call    cs:__imp_GetSystemDirectoryW
0x18002563a  dec     eax
0x18002563c  cmp     eax, 103h
0x180025641  ja      loc_180025B66
0x180025647  lea     rcx, [rsp+8C8h+Buffer]
0x18002564f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180025653  inc     rax
0x180025656  cmp     [rcx+rax*2], r12w
0x18002565b  jnz     short loc_180025653
0x18002565d  mov     edi, 2
0x180025662  lea     ebx, [rdi-1]
0x180025665  cmp     [rsp+rax*2+8C8h+var_25A], 5Ch ; '\'
0x18002566e  jz      loc_180025C32
0x180025674  mov     rdx, rsi
0x180025677  lea     rax, [rsp+8C8h+Buffer]
0x18002567f  cmp     [rax], r12w
0x180025683  jz      short loc_18002568D
0x180025685  add     rax, rdi
0x180025688  sub     rdx, rbx
0x18002568b  jnz     short loc_18002567F
0x18002568d  mov     rax, rdx
0x180025690  mov     rcx, rsi
0x180025693  sub     rcx, rdx
0x180025696  neg     rax
0x180025699  sbb     r8, r8
0x18002569c  and     r8, rcx
0x18002569f  mov     r15d, 7FFFFFFEh
0x1800256a5  test    rdx, rdx
0x1800256a8  jz      short loc_1800256F8
0x1800256aa  mov     ecx, r15d
0x1800256ad  lea     r9, SubBlock; "\\"
0x1800256b4  mov     rax, rsi
0x1800256b7  sub     rax, r8
0x1800256ba  lea     rdx, [rsp+8C8h+Buffer]
0x1800256c2  lea     rdx, [rdx+r8*2]
0x1800256c6  jz      short loc_1800256E9
0x1800256c8  test    rcx, rcx
0x1800256cb  jz      short loc_1800256E9
0x1800256cd  movzx   r8d, word ptr [r9]
0x1800256d1  test    r8w, r8w
0x1800256d5  jz      short loc_1800256E9
0x1800256d7  add     r9, rdi
0x1800256da  mov     [rdx], r8w
0x1800256de  add     rdx, rdi
0x1800256e1  sub     rcx, rbx
0x1800256e4  sub     rax, rbx
0x1800256e7  jnz     short loc_1800256C8
0x1800256e9  lea     rcx, [rdx-2]
0x1800256ed  test    rax, rax
0x1800256f0  cmovnz  rcx, rdx
0x1800256f4  mov     [rcx], r12w
0x1800256f8  mov     rcx, r15
0x1800256fb  lea     r8, [rsp+8C8h+Buffer]
0x180025703  mov     rdx, rsi
0x180025706  lea     rax, [rsp+8C8h+FileName]
0x18002570e  test    rcx, rcx
0x180025711  jz      short loc_18002572F
0x180025713  movzx   r9d, word ptr [r8]
0x180025717  test    r9w, r9w
0x18002571b  jz      short loc_18002572F
0x18002571d  add     r8, rdi
0x180025720  mov     [rax], r9w
0x180025724  add     rax, rdi
0x180025727  sub     rcx, rbx
0x18002572a  sub     rdx, rbx
0x18002572d  jnz     short loc_18002570E
0x18002572f  lea     rcx, [rax-2]
0x180025733  test    rdx, rdx
0x180025736  cmovnz  rcx, rax
0x18002573a  mov     [rcx], r12w
0x18002573e  mov     rdx, rsi
0x180025741  lea     rax, [rsp+8C8h+FileName]
0x180025749  cmp     [rax], r12w
0x18002574d  jz      short loc_180025757
0x18002574f  add     rax, rdi
0x180025752  sub     rdx, rbx
0x180025755  jnz     short loc_180025749
0x180025757  mov     rax, rdx
0x18002575a  mov     rcx, rsi
0x18002575d  sub     rcx, rdx
0x180025760  neg     rax
0x180025763  sbb     r8, r8
0x180025766  and     r8, rcx
0x180025769  test    rdx, rdx
0x18002576c  jz      short loc_1800257BC
0x18002576e  mov     rcx, r15
0x180025771  lea     r9, aOeminfoIni; "OemInfo.Ini"
0x180025778  mov     rax, rsi
0x18002577b  sub     rax, r8
0x18002577e  lea     rdx, [rsp+8C8h+FileName]
0x180025786  lea     rdx, [rdx+r8*2]
0x18002578a  jz      short loc_1800257AD
0x18002578c  test    rcx, rcx
0x18002578f  jz      short loc_1800257AD
0x180025791  movzx   r8d, word ptr [r9]
0x180025795  test    r8w, r8w
0x180025799  jz      short loc_1800257AD
0x18002579b  add     r9, rdi
0x18002579e  mov     [rdx], r8w
0x1800257a2  add     rdx, rdi
0x1800257a5  sub     rcx, rbx
0x1800257a8  sub     rax, rbx
0x1800257ab  jnz     short loc_18002578C
0x1800257ad  lea     rcx, [rdx-2]
0x1800257b1  test    rax, rax
0x1800257b4  cmovnz  rcx, rdx
0x1800257b8  mov     [rcx], r12w
0x1800257bc  lea     rdx, aManufacturer; "Manufacturer"
0x1800257c3  mov     rcx, r14
0x1800257c6  call    cs:__imp_?IsNull@CInstance@@QEBA_NPEBG@Z; CInstance::IsNull(ushort const *)
0x1800257cc  test    al, al
0x1800257ce  jnz     loc_180025DD2
0x1800257d4  lea     rdx, aModel; "Model"
0x1800257db  mov     rcx, r14
0x1800257de  call    cs:__imp_?IsNull@CInstance@@QEBA_NPEBG@Z; CInstance::IsNull(ushort const *)
0x1800257e4  test    al, al
0x1800257e6  jnz     loc_180025E2E
0x1800257ec  mov     qword ptr [rsp+8C8h+rgsabound.cElements], r12
0x1800257f1  lea     rcx, [rsp+8C8h+pvarg]; pvarg
0x1800257f6  call    cs:__imp_VariantInit
0x1800257fc  nop
0x1800257fd  mov     ecx, 8; vt
0x180025802  lea     r8, [rsp+8C8h+rgsabound]; rgsabound
0x180025807  mov     edx, ebx; cDims
0x180025809  call    cs:__imp_SafeArrayCreate
0x18002580f  mov     qword ptr [rsp+8C8h+pvarg+8], rax
0x180025814  test    rax, rax
0x180025817  jnz     short loc_180025830
0x180025819  mov     [rsp+8C8h+pExceptionObject], r12d
0x18002581e  lea     rdx, _TI1?AVCHeap_Exception@@; pThrowInfo
0x180025825  lea     rcx, [rsp+8C8h+pExceptionObject]; pExceptionObject
0x18002582a  call    _CxxThrowException_0
0x180025830  mov     eax, 2008h
0x180025835  mov     word ptr [rsp+8C8h+pvarg], ax
0x18002583a  mov     [rsp+8C8h+var_880], ebx
0x18002583e  mov     rcx, r15
0x180025841  lea     r8, aLine; "Line"
0x180025848  mov     edx, 16h
0x18002584d  lea     rax, [rsp+8C8h+SourceString]
0x180025855  test    rcx, rcx
0x180025858  jz      short loc_180025876
0x18002585a  movzx   r9d, word ptr [r8]
0x18002585e  test    r9w, r9w
0x180025862  jz      short loc_180025876
0x180025864  add     r8, rdi
0x180025867  mov     [rax], r9w
0x18002586b  add     rax, rdi
0x18002586e  sub     rcx, rbx
0x180025871  sub     rdx, rbx
0x180025874  jnz     short loc_180025855
0x180025876  lea     rcx, [rax-2]
0x18002587a  test    rdx, rdx
0x18002587d  cmovnz  rcx, rax
0x180025881  mov     [rcx], r12w
0x180025885  mov     r8d, 0Ah; Radix
0x18002588b  lea     rdx, [rsp+8C8h+psz]; Buffer
0x180025893  mov     ecx, ebx; Value
0x180025895  call    cs:__imp__itow
0x18002589b  mov     r8, rax; unsigned __int16 *
0x18002589e  mov     edx, 2Ch ; ','; unsigned __int64
0x1800258a3  lea     rcx, [rsp+8C8h+SourceString]; unsigned __int16 *
0x1800258ab  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x1800258b0  mov     r14d, 100h
0x1800258b6  lea     rcx, [rsp+8C8h+var_828]; this
0x1800258be  call    ??0CWMI_FILE_IniFile@@QEAA@XZ; CWMI_FILE_IniFile::CWMI_FILE_IniFile(void)
0x1800258c3  nop
0x1800258c4  mov     [rsp+8C8h+var_828], 0
0x1800258d0  mov     [rsp+8C8h+var_778], r12d
0x1800258d8  lea     rax, [rsp+8C8h+FileName]
0x1800258e0  mov     [rsp+8C8h+var_7C0], rax
0x1800258e8  lea     rdx, SourceString; "Support Information"
0x1800258ef  lea     rcx, [rsp+8C8h+DestinationString]; DestinationString
0x1800258f7  call    cs:__imp_RtlInitUnicodeString
0x1800258fd  lea     rdx, [rsp+8C8h+SourceString]; SourceString
0x180025905  lea     rcx, [rsp+8C8h+var_788]; DestinationString
0x18002590d  call    cs:__imp_RtlInitUnicodeString
0x180025913  lea     rax, [rsp+8C8h+psz]
0x18002591b  cmp     dword ptr [rsp+8C8h+var_828+4], r12d
0x180025923  jnz     loc_180025E8A
0x180025929  mov     [rsp+8C8h+var_750], r14d
0x180025931  mov     [rsp+8C8h+var_754], r12d
0x180025939  mov     [rsp+8C8h+var_748], rax
0x180025941  lea     rcx, [rsp+8C8h+var_828]; this
0x180025949  call    ?ReadWriteIniFileOnDisk@CWMI_FILE_IniFile@@QEAAJXZ; CWMI_FILE_IniFile::ReadWriteIniFileOnDisk(void)
0x18002594e  mov     r12d, eax
0x180025951  test    eax, eax
0x180025953  jns     loc_180025EAF
0x180025959  cmp     eax, 80000005h
0x18002595e  jz      loc_180025ED6
0x180025964  lea     rcx, [rsp+8C8h+var_828]; this
0x18002596c  call    ??1CWMI_FILE_IniFile@@QEAA@XZ; CWMI_FILE_IniFile::~CWMI_FILE_IniFile(void)
0x180025971  test    r12d, r12d
0x180025974  jns     loc_180025C70
0x18002597a  cmp     r12d, 80000005h
0x180025981  jz      loc_180025EFA
0x180025987  mov     edx, ebx
0x180025989  mov     r8d, ebx
0x18002598c  xor     r12d, r12d
0x18002598f  lea     r9, asc_180128984; "@"
0x180025996  lea     eax, [rdx-1]
0x180025999  cmp     word ptr [r9+rax*2], 20h ; ' '
0x18002599f  jz      loc_180025C45
0x1800259a5  cmp     edx, 100h
0x1800259ab  mov     eax, 0FFh
0x1800259b0  cmovnb  edx, eax
0x1800259b3  mov     ecx, edx
0x1800259b5  cmp     rcx, r15
0x1800259b8  ja      loc_180025EEC
0x1800259be  lea     r8d, [rax+1]
0x1800259c2  lea     rax, [rsp+8C8h+psz]
0x1800259ca  test    rcx, rcx
0x1800259cd  jz      short loc_1800259EB
0x1800259cf  movzx   r10d, word ptr [r9]
0x1800259d3  test    r10w, r10w
0x1800259d7  jz      short loc_1800259EB
0x1800259d9  add     r9, rdi
0x1800259dc  mov     [rax], r10w
0x1800259e0  add     rax, rdi
0x1800259e3  sub     rcx, rbx
0x1800259e6  sub     r8, rbx
0x1800259e9  jnz     short loc_1800259CA
0x1800259eb  lea     rcx, [rax-2]
0x1800259ef  test    r8, r8
0x1800259f2  cmovnz  rcx, rax
0x1800259f6  mov     [rcx], r12w
0x1800259fa  cmp     edx, 100h
0x180025a00  jnb     loc_180025F21
0x180025a06  mov     ecx, edx
0x180025a08  mov     [rsp+rcx*2+8C8h+psz], r12w
0x180025a11  cmp     edx, ebx
0x180025a13  ja      loc_180025C8B
0x180025a19  cmp     [rsp+8C8h+psz], 40h ; '@'
0x180025a22  jnz     loc_180025C8B
0x180025a28  mov     r14, [rsp+8C8h+var_840]
0x180025a30  cmp     [rsp+8C8h+var_880], ebx
0x180025a34  ja      loc_180025F07
0x180025a3a  lea     rcx, [rsp+8C8h+pvarg]; pvarg
0x180025a3f  call    cs:__imp_VariantClear
0x180025a45  test    eax, eax
0x180025a47  js      loc_180025C3D
0x180025a4d  mov     rcx, r15
0x180025a50  lea     r8, [rsp+8C8h+Buffer]
0x180025a58  mov     rdx, rsi
0x180025a5b  lea     rax, [rsp+8C8h+FileName]
0x180025a63  test    rcx, rcx
0x180025a66  jz      short loc_180025A84
0x180025a68  movzx   r9d, word ptr [r8]
0x180025a6c  test    r9w, r9w
0x180025a70  jz      short loc_180025A84
0x180025a72  add     r8, rdi
0x180025a75  mov     [rax], r9w
0x180025a79  add     rax, rdi
0x180025a7c  sub     rcx, rbx
0x180025a7f  sub     rdx, rbx
0x180025a82  jnz     short loc_180025A63
0x180025a84  lea     rcx, [rax-2]
0x180025a88  test    rdx, rdx
0x180025a8b  cmovnz  rcx, rax
0x180025a8f  mov     [rcx], r12w
0x180025a93  mov     rdx, rsi
  ... truncated ...
```
