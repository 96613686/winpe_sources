# COleInsertDialog::DoModal(ulong)

- ea: `0x1802581f0`
- end: `0x18025868b`
- name: `?DoModal@COleInsertDialog@@QEAA_JK@Z`
- size: `1179`
- prototype: `__int64 __fastcall(COleInsertDialog *this, unsigned int dwFlags)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000dc50`
- `0x18000df50`
- `0x1801d7400`
- `0x180232ba0`
- `0x1802580d0`
- `0x1802581f0`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180258360`
- `ADVAPI32!RegCloseKey` at `0x1802583d5`
- `ADVAPI32!RegCloseKey` at `0x180258409`
- `ADVAPI32!RegCloseKey` at `0x180258440`
- `ADVAPI32!RegCloseKey` at `0x18025844b`
- `ADVAPI32!RegCloseKey` at `0x18025854f`
- `ADVAPI32!RegCloseKey` at `0x180258360`
- `ADVAPI32!RegCloseKey` at `0x1802583d5`
- `ADVAPI32!RegCloseKey` at `0x180258409`
- `ADVAPI32!RegCloseKey` at `0x180258440`
- `ADVAPI32!RegCloseKey` at `0x18025844b`
- `ADVAPI32!RegCloseKey` at `0x18025854f`
- `ADVAPI32!RegOpenKeyExW` at `0x180258289`
- `ADVAPI32!RegOpenKeyExW` at `0x1802582b4`
- `ADVAPI32!RegOpenKeyExW` at `0x1802582fd`
- `ADVAPI32!RegOpenKeyExW` at `0x180258327`
- `ADVAPI32!RegOpenKeyExW` at `0x18025834d`
- `ADVAPI32!RegOpenKeyExW` at `0x180258382`
- `ADVAPI32!RegOpenKeyExW` at `0x180258540`
- `ADVAPI32!RegOpenKeyExW` at `0x180258289`
- `ADVAPI32!RegOpenKeyExW` at `0x1802582b4`
- `ADVAPI32!RegOpenKeyExW` at `0x1802582fd`
- `ADVAPI32!RegOpenKeyExW` at `0x180258327`
- `ADVAPI32!RegOpenKeyExW` at `0x18025834d`
- `ADVAPI32!RegOpenKeyExW` at `0x180258382`
- `ADVAPI32!RegOpenKeyExW` at `0x180258540`
- `ADVAPI32!RegEnumKeyW` at `0x1802582d6`
- `ADVAPI32!RegEnumKeyW` at `0x180258424`
- `ADVAPI32!RegEnumKeyW` at `0x1802582d6`
- `ADVAPI32!RegEnumKeyW` at `0x180258424`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180258644`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180258644`
- `ole32!GetClassFile` at `0x1802584cf`
- `ole32!GetClassFile` at `0x1802584cf`
- `ole32!CLSIDFromString` at `0x1802583a5`
- `ole32!CLSIDFromString` at `0x1802583a5`

## string_xrefs

- `0x1802582a8`: `CLSID`
- `0x180258513`: `CLSID\%Ts\DocObject`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
// Hidden C++ exception states: #wind=5
__int64 __fastcall COleInsertDialog::DoModal(COleInsertDialog *this, unsigned int dwFlags)
{
  _GUID *v4; // rdi
  unsigned int m_pszData; // esi
  int v6; // r14d
  wchar_t *v7; // rdx
  DWORD v8; // edx
  unsigned int cClsidExclude; // r14d
  _GUID *lpClsidExclude; // r12
  __int64 v11; // rsi
  unsigned int v12; // eax
  int v13; // edi
  HKEY__ *v14; // rdx
  wchar_t *v15; // rdx
  wchar_t *v16; // rdx
  wchar_t *v17; // rdx
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strKey; // [rsp+38h] [rbp-D0h] BYREF
  HKEY__ *nNewExcludeCount; // [rsp+40h] [rbp-C8h] OVERLAPPED BYREF
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strCLSID; // [rsp+48h] [rbp-C0h] BYREF
  HKEY__ *hkItem; // [rsp+50h] [rbp-B8h] BYREF
  _GUID *lpNewExcludeList; // [rsp+58h] [rbp-B0h] BYREF
  HKEY__ *hKey; // [rsp+60h] [rbp-A8h] BYREF
  HKEY__ *nNewExcludeLen; // [rsp+68h] [rbp-A0h] OVERLAPPED BYREF
  _GUID clsidFile; // [rsp+70h] [rbp-98h] BYREF
  wchar_t szName[268]; // [rsp+80h] [rbp-88h] BYREF

  v4 = 0;
  hKey = 0;
  m_pszData = 0;
  LODWORD(strCLSID.m_pszData) = 0;
  clsidFile.Data1 = 0;
  if ( dwFlags == 2 )
  {
    this->m_io.dwFlags |= 0x3000u;
  }
  else if ( dwFlags == 1 )
  {
    this->m_io.dwFlags |= 0x500u;
    if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, 0, 0, 0x20019u, &hkItem) )
    {
      if ( !RegOpenKeyExW(hkItem, L"CLSID", 0, 8u, &nNewExcludeCount) )
      {
        v6 = 1;
        if ( !RegEnumKeyW(nNewExcludeCount, 0, &szName[4], 0x105u) )
        {
          do
          {
            if ( !RegOpenKeyExW(nNewExcludeCount, &szName[4], 0, 0x20019u, (PHKEY)&lpNewExcludeList)
              && (!RegOpenKeyExW((HKEY)lpNewExcludeList, L"Insertable", 0, 0x20019u, (PHKEY)&strKey)
               || !RegOpenKeyExW((HKEY)lpNewExcludeList, L"Ole1Class", 0, 0x20019u, (PHKEY)&strKey)) )
            {
              RegCloseKey((HKEY)strKey.m_pszData);
              if ( RegOpenKeyExW((HKEY)lpNewExcludeList, L"DocObject", 0, 0x20019u, (PHKEY)&strKey) )
              {
                ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
                  (ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *)&nNewExcludeLen,
                  &szName[4]);
                if ( !CLSIDFromString((LPCOLESTR)nNewExcludeLen, (LPCLSID)clsidFile.Data4) )
                  COleInsertDialog::AddClassIDToList(
                    this,
                    (_GUID **)&hKey,
                    (int *)&strCLSID,
                    (int *)&clsidFile,
                    (_GUID *)clsidFile.Data4);
                RegCloseKey((HKEY)lpNewExcludeList);
                v7 = (wchar_t *)(nNewExcludeLen - 6);
                if ( _InterlockedDecrement((volatile signed __int32 *)nNewExcludeLen - 2) <= 0 )
                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v7 + 8LL))(*(_QWORD *)v7);
              }
              RegCloseKey((HKEY)strKey.m_pszData);
            }
            v8 = v6++;
          }
          while ( !RegEnumKeyW(nNewExcludeCount, v8, &szName[4], 0x105u) );
          v4 = (_GUID *)hKey;
          m_pszData = (unsigned int)strCLSID.m_pszData;
        }
        RegCloseKey(nNewExcludeCount);
      }
      RegCloseKey(hkItem);
    }
  }
  cClsidExclude = this->m_io.cClsidExclude;
  lpClsidExclude = this->m_io.lpClsidExclude;
  if ( v4 )
  {
    this->m_io.lpClsidExclude = v4;
    this->m_io.cClsidExclude = m_pszData;
  }
  v11 = this->DoModal(this);
  if ( v11 == 1 )
  {
    do
    {
      v12 = this->m_io.dwFlags;
      if ( (v12 & 4) == 0 || (v12 & 8) != 0 || dwFlags != 1 )
        break;
      v13 = 0;
      ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
        &strKey,
        this->m_io.lpszFile);
      if ( !GetClassFile(strKey.m_pszData, (CLSID *)clsidFile.Data4) )
      {
        nNewExcludeCount = (HKEY__ *)&afxStringManager.GetNilString(&afxStringManager)[1];
        AfxStringFromCLSID(
          (ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *)&hkItem,
          (const _GUID *)clsidFile.Data4);
        ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Format(
          (ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *)&nNewExcludeCount,
          L"CLSID\\%Ts\\DocObject",
          hkItem);
        if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, (LPCWSTR)nNewExcludeCount, 0, 1u, &nNewExcludeLen) )
        {
          RegCloseKey(nNewExcludeLen);
          v13 = 1;
        }
        v14 = hkItem - 6;
        if ( _InterlockedDecrement((volatile signed __int32 *)hkItem - 2) <= 0 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v14 + 8LL))(*(_QWORD *)v14);
        v15 = (wchar_t *)(nNewExcludeCount - 6);
        if ( _InterlockedDecrement((volatile signed __int32 *)nNewExcludeCount - 2) <= 0 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v15 + 8LL))(*(_QWORD *)v15);
        if ( v13 )
          goto LABEL_40;
      }
      if ( AfxMessageBox(0xF184u, 0x15u, 0xFFFFFFFF) != 4 )
      {
        v11 = 2;
LABEL_40:
        v17 = strKey.m_pszData - 12;
        if ( _InterlockedDecrement((volatile signed __int32 *)strKey.m_pszData - 2) <= 0 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v17 + 8LL))(*(_QWORD *)v17);
        break;
      }
      v16 = strKey.m_pszData - 12;
      if ( _InterlockedDecrement((volatile signed __int32 *)strKey.m_pszData - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 8LL))(*(_QWORD *)v16);
      v11 = this->DoModal(this);
    }
    while ( v11 == 1 );
    v4 = (_GUID *)hKey;
  }
  free(v4);
  this->m_io.cClsidExclude = cClsidExclude;
  this->m_io.lpClsidExclude = lpClsidExclude;
  return v11;
}

```

## disassembly

```asm
0x1802581f0  mov     rax, rsp
0x1802581f3  mov     [rax+10h], rbx
0x1802581f7  mov     [rax+18h], rsi
0x1802581fb  mov     [rax+20h], rdi
0x1802581ff  push    rbp
0x180258200  push    r12
0x180258202  push    r13
0x180258204  push    r14
0x180258206  push    r15
0x180258208  lea     rbp, [rax-1C8h]
0x18025820f  sub     rsp, 2A0h
0x180258216  mov     rax, cs:__security_cookie
0x18025821d  xor     rax, rsp
0x180258220  mov     [rbp+1C0h+var_30], rax
0x180258227  mov     r15d, dwFlags
0x18025822a  mov     rbx, this
0x18025822d  xor     edi, edi
0x18025822f  mov     [rsp+2C0h+hKey], rdi
0x180258234  xor     esi, esi
0x180258236  mov     dword ptr [rsp+2C0h+strCLSID.m_pszData], esi
0x18025823a  and     [rsp+2C0h+clsidFile.Data1], esi
0x18025823e  or      r13d, 0FFFFFFFFh
0x180258242  cmp     dwFlags, 2
0x180258245  jnz     short loc_180258256
0x180258247  or      dword ptr [this+13Ch], 3000h
0x180258251  jmp     loc_180258451
0x180258256  cmp     r15d, 1
0x18025825a  jnz     loc_180258451
0x180258260  or      dword ptr [this+13Ch], 500h
0x18025826a  lea     rax, [rsp+2C0h+hkItem]
0x18025826f  mov     [rsp+2C0h+phkResult], rax; phkResult
0x180258274  mov     r12d, 20019h
0x18025827a  mov     r9d, r12d; samDesired
0x18025827d  xor     r8d, r8d; ulOptions
0x180258280  xor     dwFlags, dwFlags; lpSubKey
0x180258282  mov     this, 0FFFFFFFF80000000h; hKey
0x180258289  call    cs:__imp_RegOpenKeyExW
0x18025828f  test    eax, eax
0x180258291  jnz     loc_180258451
0x180258297  lea     rax, [rsp+2C0h+nNewExcludeCount]
0x18025829c  mov     [rsp+2C0h+phkResult], rax; phkResult
0x1802582a1  lea     r9d, [r15+7]; samDesired
0x1802582a5  xor     r8d, r8d; ulOptions
0x1802582a8  lea     rdx, aClsid_0; "CLSID"
0x1802582af  mov     this, [rsp+2C0h+hkItem]; hKey
0x1802582b4  call    cs:__imp_RegOpenKeyExW
0x1802582ba  test    eax, eax
0x1802582bc  jnz     loc_180258446
0x1802582c2  mov     r14d, r15d
0x1802582c5  mov     r9d, 105h; cchName
0x1802582cb  lea     r8, [rbp+1C0h+szName+8]; lpName
0x1802582cf  xor     dwFlags, dwFlags; dwIndex
0x1802582d1  mov     this, [rsp+2C0h+nNewExcludeCount]; hKey
0x1802582d6  call    cs:__imp_RegEnumKeyW
0x1802582dc  test    eax, eax
0x1802582de  jnz     loc_18025843B
0x1802582e4  lea     rax, [rsp+2C0h+lpNewExcludeList]
0x1802582e9  mov     [rsp+2C0h+phkResult], rax; phkResult
0x1802582ee  mov     r9d, r12d; samDesired
0x1802582f1  xor     r8d, r8d; ulOptions
0x1802582f4  lea     rdx, [rbp+1C0h+szName+8]; lpSubKey
0x1802582f8  mov     this, [rsp+2C0h+nNewExcludeCount]; hKey
0x1802582fd  call    cs:__imp_RegOpenKeyExW
0x180258303  test    eax, eax
0x180258305  jnz     loc_18025840F
0x18025830b  lea     rax, [rsp+2C0h+strKey]
0x180258310  mov     [rsp+2C0h+phkResult], rax; phkResult
0x180258315  mov     r9d, r12d; samDesired
0x180258318  xor     r8d, r8d; ulOptions
0x18025831b  lea     rdx, aInsertable; "Insertable"
0x180258322  mov     this, [rsp+2C0h+lpNewExcludeList]; hKey
0x180258327  call    cs:__imp_RegOpenKeyExW
0x18025832d  test    eax, eax
0x18025832f  jz      short loc_18025835B
0x180258331  lea     rax, [rsp+2C0h+strKey]
0x180258336  mov     [rsp+2C0h+phkResult], rax; phkResult
0x18025833b  mov     r9d, r12d; samDesired
0x18025833e  xor     r8d, r8d; ulOptions
0x180258341  lea     rdx, aOle1class; "Ole1Class"
0x180258348  mov     this, [rsp+2C0h+lpNewExcludeList]; hKey
0x18025834d  call    cs:__imp_RegOpenKeyExW
0x180258353  test    eax, eax
0x180258355  jnz     loc_18025840F
0x18025835b  mov     this, [rsp+2C0h+strKey.m_pszData]; hKey
0x180258360  call    cs:__imp_RegCloseKey
0x180258366  lea     rax, [rsp+2C0h+strKey]
0x18025836b  mov     [rsp+2C0h+phkResult], rax; phkResult
0x180258370  mov     r9d, r12d; samDesired
0x180258373  xor     r8d, r8d; ulOptions
0x180258376  lea     rdx, aDocobject; "DocObject"
0x18025837d  mov     this, [rsp+2C0h+lpNewExcludeList]; hKey
0x180258382  call    cs:__imp_RegOpenKeyExW
0x180258388  test    eax, eax
0x18025838a  jz      short loc_180258404
0x18025838c  lea     rdx, [rbp+1C0h+szName+8]; pszSrc
0x180258390  lea     this, [rsp+2C0h+nNewExcludeLen]; this
0x180258395  call    ??0?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAA@PEB_W@Z; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(wchar_t const *)
0x18025839a  nop
0x18025839b  lea     rdx, [rsp+2C0h+clsidFile.Data4]; pclsid
0x1802583a0  mov     this, [rsp+2C0h+nNewExcludeLen]; lpsz
0x1802583a5  call    cs:__imp_CLSIDFromString
0x1802583ab  test    eax, eax
0x1802583ad  jnz     short loc_1802583D0
0x1802583af  lea     rax, [rsp+2C0h+clsidFile.Data4]
0x1802583b4  mov     [rsp+2C0h+phkResult], rax; lpNewID
0x1802583b9  lea     r9, [rsp+2C0h+clsidFile]; nBufferLen
0x1802583be  lea     r8, [rsp+2C0h+strCLSID]; nListCount
0x1802583c3  lea     rdx, [rsp+2C0h+hKey]; lpList
0x1802583c8  mov     this, rbx; this
0x1802583cb  call    ?AddClassIDToList@COleInsertDialog@@IEAAXAEAPEAU_GUID@@AEAH1PEAU2@@Z; COleInsertDialog::AddClassIDToList(_GUID * &,int &,int &,_GUID *)
0x1802583d0  mov     this, [rsp+2C0h+lpNewExcludeList]; hKey
0x1802583d5  call    cs:__imp_RegCloseKey
0x1802583db  nop
0x1802583dc  mov     rdx, [rsp+2C0h+nNewExcludeLen]
0x1802583e1  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1802583e5  mov     eax, r13d
0x1802583e8  lock xadd [rdx+10h], eax
0x1802583ed  add     eax, r13d
0x1802583f0  test    eax, eax
0x1802583f2  jg      short loc_180258404
0x1802583f4  mov     this, [rdx]
0x1802583f7  mov     rax, [this]
0x1802583fa  mov     rax, [rax+8]
0x1802583fe  call    cs:__guard_dispatch_icall_fptr
0x180258404  mov     this, [rsp+2C0h+strKey.m_pszData]; hKey
0x180258409  call    cs:__imp_RegCloseKey
0x18025840f  mov     dwFlags, r14d; dwIndex
0x180258412  inc     r14d
0x180258415  mov     r9d, 105h; cchName
0x18025841b  lea     r8, [rbp+1C0h+szName+8]; lpName
0x18025841f  mov     this, [rsp+2C0h+nNewExcludeCount]; hKey
0x180258424  call    cs:__imp_RegEnumKeyW
0x18025842a  test    eax, eax
0x18025842c  jz      loc_1802582E4
0x180258432  mov     rdi, [rsp+2C0h+hKey]
0x180258437  mov     esi, dword ptr [rsp+2C0h+strCLSID.m_pszData]
0x18025843b  mov     this, [rsp+2C0h+nNewExcludeCount]; hKey
0x180258440  call    cs:__imp_RegCloseKey
0x180258446  mov     this, [rsp+2C0h+hkItem]; hKey
0x18025844b  call    cs:__imp_RegCloseKey
0x180258451  mov     r14d, [rbx+194h]
0x180258458  mov     r12, [rbx+198h]
0x18025845f  test    rdi, rdi
0x180258462  jz      short loc_180258471
0x180258464  mov     [rbx+198h], rdi
0x18025846b  mov     [rbx+194h], esi
0x180258471  mov     rax, [rbx]
0x180258474  mov     this, rbx
0x180258477  mov     rax, [rax+2F8h]
0x18025847e  call    cs:__guard_dispatch_icall_fptr
0x180258484  mov     rsi, rax
0x180258487  cmp     rax, 1
0x18025848b  jnz     loc_180258641
0x180258491  mov     eax, [rbx+13Ch]
0x180258497  test    al, 4
0x180258499  jz      loc_18025863C
0x18025849f  test    al, 8
0x1802584a1  jnz     loc_18025863C
0x1802584a7  cmp     r15d, 1
0x1802584ab  jnz     loc_18025863C
0x1802584b1  xor     edi, edi
0x1802584b3  mov     rdx, [rbx+188h]; pszSrc
0x1802584ba  lea     this, [rsp+2C0h+strKey]; this
0x1802584bf  call    ??0?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAA@PEB_W@Z; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(wchar_t const *)
0x1802584c4  nop
0x1802584c5  lea     rdx, [rsp+2C0h+clsidFile.Data4]; pclsid
0x1802584ca  mov     this, [rsp+2C0h+strKey.m_pszData]; szFilename
0x1802584cf  call    cs:__imp_GetClassFile
0x1802584d5  test    eax, eax
0x1802584d7  jnz     loc_1802585AD
0x1802584dd  mov     rax, cs:?afxStringManager@@3VCAfxStringMgr@@A.__vftable; CAfxStringMgr afxStringManager ...
0x1802584e4  lea     this, ?afxStringManager@@3VCAfxStringMgr@@A; CAfxStringMgr afxStringManager
0x1802584eb  mov     rax, [rax+18h]
0x1802584ef  call    cs:__guard_dispatch_icall_fptr
0x1802584f5  add     rax, 18h
0x1802584f9  mov     [rsp+2C0h+nNewExcludeCount], rax
0x1802584fe  lea     rdx, [rsp+2C0h+clsidFile.Data4]; rclsid
0x180258503  lea     this, [rsp+2C0h+hkItem]; result
0x180258508  call    ?AfxStringFromCLSID@@YA?AV?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@AEBU_GUID@@@Z; AfxStringFromCLSID(_GUID const &)
0x18025850d  nop
0x18025850e  mov     r8, [rsp+2C0h+hkItem]
0x180258513  lea     rdx, aClsidTsDocobje; "CLSID\\%Ts\\DocObject"
0x18025851a  lea     this, [rsp+2C0h+nNewExcludeCount]; this
0x18025851f  call    ?Format@?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAAXPEB_WZZ; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Format(wchar_t const *,...)
0x180258524  lea     rax, [rsp+2C0h+nNewExcludeLen]
0x180258529  mov     [rsp+2C0h+phkResult], rax; phkResult
0x18025852e  mov     r9d, r15d; samDesired
0x180258531  xor     r8d, r8d; ulOptions
0x180258534  mov     rdx, [rsp+2C0h+nNewExcludeCount]; lpSubKey
0x180258539  mov     this, 0FFFFFFFF80000000h; hKey
0x180258540  call    cs:__imp_RegOpenKeyExW
0x180258546  test    eax, eax
0x180258548  jnz     short loc_180258558
0x18025854a  mov     this, [rsp+2C0h+nNewExcludeLen]; hKey
0x18025854f  call    cs:__imp_RegCloseKey
0x180258555  mov     edi, r15d
0x180258558  mov     rdx, [rsp+2C0h+hkItem]
0x18025855d  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180258561  mov     eax, r13d
0x180258564  lock xadd [rdx+10h], eax
0x180258569  add     eax, r13d
0x18025856c  test    eax, eax
0x18025856e  jg      short loc_180258581
0x180258570  mov     this, [rdx]
0x180258573  mov     rax, [this]
0x180258576  mov     rax, [rax+8]
0x18025857a  call    cs:__guard_dispatch_icall_fptr
0x180258580  nop
0x180258581  mov     rdx, [rsp+2C0h+nNewExcludeCount]
0x180258586  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18025858a  mov     eax, r13d
0x18025858d  lock xadd [rdx+10h], eax
0x180258592  add     eax, r13d
0x180258595  test    eax, eax
0x180258597  jg      short loc_1802585A9
0x180258599  mov     this, [rdx]
0x18025859c  mov     rax, [this]
0x18025859f  mov     rax, [rax+8]
0x1802585a3  call    cs:__guard_dispatch_icall_fptr
0x1802585a9  test    edi, edi
0x1802585ab  jnz     short loc_180258614
0x1802585ad  or      r8d, 0FFFFFFFFh; nIDHelp
0x1802585b1  mov     dwFlags, 15h; nType
0x1802585b6  mov     ecx, 0F184h; nIDPrompt
0x1802585bb  call    ?AfxMessageBox@@YAHIII@Z; AfxMessageBox(uint,uint,uint)
0x1802585c0  cmp     eax, 4
0x1802585c3  jnz     short loc_18025860F
0x1802585c5  mov     rdx, [rsp+2C0h+strKey.m_pszData]
0x1802585ca  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1802585ce  mov     eax, r13d
0x1802585d1  lock xadd [rdx+10h], eax
0x1802585d6  add     eax, r13d
0x1802585d9  test    eax, eax
0x1802585db  jg      short loc_1802585ED
0x1802585dd  mov     this, [rdx]
0x1802585e0  mov     rax, [this]
0x1802585e3  mov     rax, [rax+8]
0x1802585e7  call    cs:__guard_dispatch_icall_fptr
0x1802585ed  mov     rax, [rbx]
0x1802585f0  mov     this, rbx
0x1802585f3  mov     rax, [rax+2F8h]
0x1802585fa  call    cs:__guard_dispatch_icall_fptr
0x180258600  mov     rsi, rax
0x180258603  cmp     rax, 1
0x180258607  jz      $QueryAgain
0x18025860d  jmp     short loc_18025863C
0x18025860f  mov     esi, 2
0x180258614  mov     rdx, [rsp+2C0h+strKey.m_pszData]
0x180258619  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18025861d  mov     eax, r13d
0x180258620  lock xadd [rdx+10h], eax
0x180258625  add     eax, r13d
0x180258628  test    eax, eax
0x18025862a  jg      short loc_18025863C
0x18025862c  mov     this, [rdx]
0x18025862f  mov     rax, [this]
0x180258632  mov     rax, [rax+8]
0x180258636  call    cs:__guard_dispatch_icall_fptr
0x18025863c  mov     rdi, [rsp+2C0h+hKey]
0x180258641  mov     this, rdi; Block
0x180258644  call    cs:__imp_free
0x18025864a  mov     [rbx+194h], r14d
0x180258651  mov     [rbx+198h], r12
0x180258658  mov     rax, rsi
0x18025865b  mov     this, [rbp+1C0h+var_30]
0x180258662  xor     this, rsp; StackCookie
0x180258665  call    __security_check_cookie
0x18025866a  lea     r11, [rsp+2C0h+var_20]
0x180258672  mov     rbx, [r11+38h]
0x180258676  mov     rsi, [r11+40h]
0x18025867a  mov     rdi, [r11+48h]
0x18025867e  mov     rsp, r11
0x180258681  pop     r15
0x180258683  pop     r14
0x180258685  pop     r13
0x180258687  pop     r12
0x180258689  pop     rbp
0x18025868a  retn
```
