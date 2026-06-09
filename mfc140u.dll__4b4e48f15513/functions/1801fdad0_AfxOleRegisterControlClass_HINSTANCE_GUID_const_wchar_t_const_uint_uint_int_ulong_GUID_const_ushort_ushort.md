# AfxOleRegisterControlClass(HINSTANCE__ *,_GUID const &,wchar_t const *,uint,uint,int,ulong,_GUID const &,ushort,ushort)

- ea: `0x1801fdad0`
- end: `0x1801fdfa8`
- name: `?AfxOleRegisterControlClass@@YAHPEAUHINSTANCE__@@AEBU_GUID@@PEB_WIIHK1GG@Z`
- size: `1240`
- prototype: `int __fastcall(HINSTANCE__ *hInstance, const _GUID *clsid, const wchar_t *pszProgID, unsigned int idTypeName, unsigned int idBitmap, int nRegFlags, unsigned int dwMiscStatus, const _GUID *tlid, unsigned __int16 wVerMajor, unsigned __int16 wVerMinor)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002e40`
- `0x18000ddc0`
- `0x18000df50`
- `0x18000e0e0`
- `0x1801d8c48`
- `0x1801fdad0`
- `0x180231d10`
- `0x180231d70`
- `0x180233590`
- `0x18026f940`
- `0x1802700b0`
- `0x1802bbce0`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1801fdebe`
- `ADVAPI32!RegCloseKey` at `0x1801fdecd`
- `ADVAPI32!RegCloseKey` at `0x1801fdebe`
- `ADVAPI32!RegCloseKey` at `0x1801fdecd`
- `ADVAPI32!RegCreateKeyExW` at `0x1801fdd70`
- `ADVAPI32!RegCreateKeyExW` at `0x1801fddcd`
- `ADVAPI32!RegCreateKeyExW` at `0x1801fdd70`
- `ADVAPI32!RegCreateKeyExW` at `0x1801fddcd`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1801fde51`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1801fde51`
- `api-ms-win-crt-convert-l1-1-0!_itow_s` at `0x1801fdc24`
- `api-ms-win-crt-convert-l1-1-0!_itow_s` at `0x1801fdc24`
- `api-ms-win-crt-convert-l1-1-0!_ltow_s` at `0x1801fdc53`
- `api-ms-win-crt-convert-l1-1-0!_ltow_s` at `0x1801fdc53`
- `ole32!StringFromGUID2` at `0x1801fdb20`
- `ole32!StringFromGUID2` at `0x1801fdb78`
- `ole32!StringFromGUID2` at `0x1801fdb20`
- `ole32!StringFromGUID2` at `0x1801fdb78`

## string_xrefs

- `0x1801fdce6`: `%TsCLSID\%Ts`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall AfxOleRegisterControlClass(
        HINSTANCE__ *hInstance,
        const _GUID *clsid,
        const wchar_t *pszProgID,
        unsigned int idTypeName,
        int idBitmap,
        char nRegFlags,
        int dwMiscStatus,
        const _GUID *tlid,
        unsigned __int16 wVerMajor,
        unsigned __int16 wVerMinor)
{
  int v13; // ebx
  unsigned int v14; // r15d
  HINSTANCE__ *StringResourceHandle; // rax
  errno_t v16; // eax
  errno_t v17; // eax
  unsigned __int64 v18; // r12
  const wchar_t *v19; // r15
  HKEY__ *v20; // r14
  HKEY__ *v21; // rsi
  int v22; // eax
  wchar_t *m_pszData; // rbx
  LSTATUS v24; // edx
  LSTATUS v25; // edx
  int v26; // eax
  wchar_t *v27; // rdx
  wchar_t *v28; // rdx
  wchar_t *v29; // rdx
  HKEY__ *phkResult; // [rsp+50h] [rbp-B0h] BYREF
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strClassID; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition; // [rsp+60h] [rbp-A0h] BYREF
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strTypeName; // [rsp+68h] [rbp-98h] BYREF
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strPathName; // [rsp+70h] [rbp-90h] BYREF
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strTypeLibID; // [rsp+78h] [rbp-88h] BYREF
  ATL::CRegKey hkeyClassID; // [rsp+80h] [rbp-80h]
  ATL::CRegKey hkeyProgID; // [rsp+98h] [rbp-68h]
  const wchar_t *rglpszSymbols[7]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t szTypeLibID[40]; // [rsp+F0h] [rbp-10h] BYREF
  wchar_t szClassID[40]; // [rsp+140h] [rbp+40h] BYREF
  wchar_t szScratch[264]; // [rsp+190h] [rbp+90h] BYREF
  wchar_t szProgID[264]; // [rsp+3A0h] [rbp+2A0h] BYREF
  wchar_t szBitmapID[264]; // [rsp+5B0h] [rbp+4B0h] BYREF
  wchar_t szMiscStatus[264]; // [rsp+7C0h] [rbp+6C0h] BYREF
  wchar_t szVersion[264]; // [rsp+9D0h] [rbp+8D0h] BYREF

  v13 = StringFromGUID2(clsid, szClassID, 39);
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
    &strClassID,
    szClassID);
  if ( v13 != 39 )
  {
    v14 = 0;
    goto LABEL_38;
  }
  strTypeLibID.m_pszData = (wchar_t *)&afxStringManager.GetNilString(&afxStringManager)[1];
  if ( StringFromGUID2(tlid, szTypeLibID, 39) == 39 )
  {
    strPathName.m_pszData = (wchar_t *)&afxStringManager.GetNilString(&afxStringManager)[1];
    AfxGetModuleFileName(hInstance, &strPathName);
    strTypeName.m_pszData = (wchar_t *)&afxStringManager.GetNilString(&afxStringManager)[1];
    StringResourceHandle = AfxFindStringResourceHandle(idTypeName);
    if ( !StringResourceHandle
      || !ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::LoadStringW(
            &strTypeName,
            StringResourceHandle,
            idTypeName) )
    {
      ATL::CSimpleStringT<wchar_t,1>::operator=(&strTypeName, (const ATL::CSimpleStringT<wchar_t,0> *)&strClassID);
    }
    v16 = _itow_s(idBitmap, szBitmapID, 0x104u, 10);
    if ( v16 )
    {
      if ( v16 == 12 )
        goto LABEL_41;
      if ( v16 != 80 )
        goto LABEL_42;
    }
    v17 = _ltow_s(dwMiscStatus, szMiscStatus, 0x104u, 10);
    if ( !v17 )
    {
LABEL_14:
      swprintf_s(szVersion, 0x104u, L"%d.%d", wVerMajor, wVerMinor);
      v18 = 0xFFFFFFFF80000000uLL;
      v19 = &CmdLine;
      if ( _afxRedirectRegistration == 1 )
      {
        v19 = L"Software\\Classes\\";
        v18 = -2147483647;
      }
      v20 = 0;
      hkeyClassID.m_hKey = 0;
      hkeyClassID.m_samWOW64 = 0;
      hkeyClassID.m_pTM = 0;
      v21 = 0;
      hkeyProgID.m_hKey = 0;
      hkeyProgID.m_samWOW64 = 0;
      hkeyProgID.m_pTM = 0;
      v22 = swprintf_s(szScratch, 0x104u, L"%TsCLSID\\%Ts", v19, strClassID.m_pszData);
      m_pszData = strTypeName.m_pszData;
      if ( v22 == -1 || swprintf_s(szProgID, 0x104u, L"%Ts%Ts", v19, pszProgID) == -1 )
        goto LABEL_27;
      phkResult = 0;
      v24 = RegCreateKeyExW((HKEY)v18, szScratch, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
      if ( !v24 )
      {
        v20 = phkResult;
        hkeyClassID.m_hKey = phkResult;
        hkeyClassID.m_samWOW64 = 0;
      }
      if ( (v24 != 0 ? v24 : 0) != 0 )
        goto LABEL_27;
      phkResult = 0;
      v25 = RegCreateKeyExW((HKEY)v18, szProgID, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
      if ( !v25 )
      {
        v21 = phkResult;
        hkeyProgID.m_hKey = phkResult;
        hkeyProgID.m_samWOW64 = 0;
      }
      if ( (v25 != 0 ? v25 : 0) != 0 )
        goto LABEL_27;
      rglpszSymbols[0] = m_pszData;
      rglpszSymbols[1] = strClassID.m_pszData;
      if ( !AfxOleRegisterHelper(_afxCtrlProgID, rglpszSymbols, 2, 1, v21) )
        goto LABEL_27;
      rglpszSymbols[1] = pszProgID;
      rglpszSymbols[2] = strPathName.m_pszData;
      rglpszSymbols[3] = szBitmapID;
      rglpszSymbols[4] = szMiscStatus;
      v26 = wcslen(szTypeLibID);
      ATL::CSimpleStringT<wchar_t,1>::SetString(&strTypeLibID, szTypeLibID, v26);
      rglpszSymbols[5] = strTypeLibID.m_pszData;
      rglpszSymbols[6] = szVersion;
      if ( !AfxOleRegisterHelper(_afxCtrlClassID, rglpszSymbols, 7, 1, v20) )
LABEL_27:
        v14 = 0;
      else
        v14 = AfxOleInprocRegisterHelper(v21, v20, nRegFlags);
      if ( v21 )
        RegCloseKey(v21);
      if ( v20 )
        RegCloseKey(v20);
      if ( _InterlockedDecrement((volatile signed __int32 *)m_pszData - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)m_pszData - 3) + 8LL))(*((_QWORD *)m_pszData - 3));
      v27 = strPathName.m_pszData - 12;
      if ( _InterlockedDecrement((volatile signed __int32 *)strPathName.m_pszData - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v27 + 8LL))(*(_QWORD *)v27);
      goto LABEL_36;
    }
    if ( v17 != 12 )
    {
      if ( v17 == 80 )
        goto LABEL_14;
LABEL_42:
      AfxThrowInvalidArgException();
    }
LABEL_41:
    AfxThrowMemoryException();
  }
  v14 = 0;
LABEL_36:
  v28 = strTypeLibID.m_pszData - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)strTypeLibID.m_pszData - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v28 + 8LL))(*(_QWORD *)v28);
LABEL_38:
  v29 = strClassID.m_pszData - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)strClassID.m_pszData - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v29 + 8LL))(*(_QWORD *)v29);
  return v14;
}

```

## disassembly

```asm
0x1801fdad0  push    rbp
0x1801fdad2  push    rbx
0x1801fdad3  push    rsi
0x1801fdad4  push    rdi
0x1801fdad5  push    r12
0x1801fdad7  push    r13
0x1801fdad9  push    r14
0x1801fdadb  push    r15
0x1801fdadd  lea     rbp, [rsp-0AF8h]
0x1801fdae5  sub     rsp, 0BF8h
0x1801fdaec  mov     rax, cs:__security_cookie
0x1801fdaf3  xor     rax, rsp
0x1801fdaf6  mov     [rbp+0B30h+var_50], rax
0x1801fdafd  mov     esi, idTypeName
0x1801fdb00  mov     r13, pszProgID
0x1801fdb03  mov     rax, clsid
0x1801fdb06  mov     r14, hInstance
0x1801fdb09  mov     rdi, [rbp+0B30h+rguid]
0x1801fdb10  mov     r15d, 27h ; '''
0x1801fdb16  mov     r8d, r15d; cchMax
0x1801fdb19  lea     clsid, [rbp+0B30h+szClassID]; lpsz
0x1801fdb1d  mov     hInstance, rax; rguid
0x1801fdb20  call    cs:__imp_StringFromGUID2
0x1801fdb26  mov     ebx, eax
0x1801fdb28  lea     clsid, [rbp+0B30h+szClassID]; pszSrc
0x1801fdb2c  lea     hInstance, [rsp+0C30h+strClassID]; this
0x1801fdb31  call    ??0?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAA@PEB_W@Z; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(wchar_t const *)
0x1801fdb36  nop
0x1801fdb37  or      r12d, 0FFFFFFFFh
0x1801fdb3b  cmp     ebx, r15d
0x1801fdb3e  jz      short loc_1801FDB4A
0x1801fdb40  xor     edi, edi
0x1801fdb42  mov     r15d, edi
0x1801fdb45  jmp     loc_1801FDF4E
0x1801fdb4a  mov     rax, cs:?afxStringManager@@3VCAfxStringMgr@@A.__vftable; CAfxStringMgr afxStringManager ...
0x1801fdb51  lea     rbx, ?afxStringManager@@3VCAfxStringMgr@@A; CAfxStringMgr afxStringManager
0x1801fdb58  mov     hInstance, rbx
0x1801fdb5b  mov     rax, [rax+18h]
0x1801fdb5f  call    cs:__guard_dispatch_icall_fptr
0x1801fdb65  add     rax, 18h
0x1801fdb69  mov     [rsp+0C30h+strTypeLibID.m_pszData], rax
0x1801fdb6e  mov     r8d, r15d; cchMax
0x1801fdb71  lea     clsid, [rbp+0B30h+szTypeLibID]; lpsz
0x1801fdb75  mov     hInstance, rdi; rguid
0x1801fdb78  call    cs:__imp_StringFromGUID2
0x1801fdb7e  cmp     eax, r15d
0x1801fdb81  jz      short loc_1801FDB8D
0x1801fdb83  xor     edi, edi
0x1801fdb85  mov     r15d, edi
0x1801fdb88  jmp     loc_1801FDF25
0x1801fdb8d  mov     rax, cs:?afxStringManager@@3VCAfxStringMgr@@A.__vftable; CAfxStringMgr afxStringManager ...
0x1801fdb94  mov     hInstance, rbx
0x1801fdb97  mov     rax, [rax+18h]
0x1801fdb9b  call    cs:__guard_dispatch_icall_fptr
0x1801fdba1  add     rax, 18h
0x1801fdba5  mov     [rsp+0C30h+strPathName.m_pszData], rax
0x1801fdbaa  lea     clsid, [rsp+0C30h+strPathName]; strFileName
0x1801fdbaf  mov     hInstance, r14; hInst
0x1801fdbb2  call    ?AfxGetModuleFileName@@YAXPEAUHINSTANCE__@@AEAV?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@@Z; AfxGetModuleFileName(HINSTANCE__ *,ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x1801fdbb7  nop
0x1801fdbb8  mov     rax, cs:?afxStringManager@@3VCAfxStringMgr@@A.__vftable; CAfxStringMgr afxStringManager ...
0x1801fdbbf  mov     hInstance, rbx
0x1801fdbc2  mov     rax, [rax+18h]
0x1801fdbc6  call    cs:__guard_dispatch_icall_fptr
0x1801fdbcc  add     rax, 18h
0x1801fdbd0  mov     [rsp+0C30h+strTypeName.m_pszData], rax
0x1801fdbd5  mov     ecx, esi; nID
0x1801fdbd7  call    ?AfxFindStringResourceHandle@@YAPEAUHINSTANCE__@@I@Z; AfxFindStringResourceHandle(uint)
0x1801fdbdc  nop
0x1801fdbdd  xor     edi, edi
0x1801fdbdf  test    rax, rax
0x1801fdbe2  jz      short loc_1801FDBF8
0x1801fdbe4  mov     r8d, esi; nID
0x1801fdbe7  mov     clsid, rax; hInstance
0x1801fdbea  lea     hInstance, [rsp+0C30h+strTypeName]; this
0x1801fdbef  call    ?LoadStringW@?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAAHPEAUHINSTANCE__@@I@Z; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::LoadStringW(HINSTANCE__ *,uint)
0x1801fdbf4  test    eax, eax
0x1801fdbf6  jnz     short loc_1801FDC07
0x1801fdbf8  lea     clsid, [rsp+0C30h+strClassID]; strSrc
0x1801fdbfd  lea     hInstance, [rsp+0C30h+strTypeName]; this
0x1801fdc02  call    ??4?$CSimpleStringT@_W$00@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<wchar_t,1>::operator=(ATL::CSimpleStringT<wchar_t,1> const &)
0x1801fdc07  mov     esi, 0Ah
0x1801fdc0c  mov     idTypeName, esi; Radix
0x1801fdc0f  mov     ebx, 104h
0x1801fdc14  mov     r8d, ebx; BufferCount
0x1801fdc17  lea     clsid, [rbp+0B30h+szBitmapID]; Buffer
0x1801fdc1e  mov     ecx, [rbp+0B30h+Value]; Value
0x1801fdc24  call    cs:__imp__itow_s
0x1801fdc2a  test    eax, eax
0x1801fdc2c  jz      short loc_1801FDC40
0x1801fdc2e  cmp     eax, 0Ch
0x1801fdc31  jz      loc_1801FDF9C
0x1801fdc37  cmp     eax, 50h ; 'P'
0x1801fdc3a  jnz     loc_1801FDFA2
0x1801fdc40  mov     idTypeName, esi; Radix
0x1801fdc43  mov     pszProgID, rbx; BufferCount
0x1801fdc46  lea     clsid, [rbp+0B30h+szMiscStatus]; Buffer
0x1801fdc4d  mov     ecx, [rbp+0B30h+arg_30]; Value
0x1801fdc53  call    cs:__imp__ltow_s
0x1801fdc59  test    eax, eax
0x1801fdc5b  jz      short loc_1801FDC6F
0x1801fdc5d  cmp     eax, 0Ch
0x1801fdc60  jz      loc_1801FDF9C
0x1801fdc66  cmp     eax, 50h ; 'P'
0x1801fdc69  jnz     loc_1801FDFA2
0x1801fdc6f  movzx   eax, [rbp+0B30h+arg_48]
0x1801fdc76  movzx   idTypeName, [rbp+0B30h+arg_40]
0x1801fdc7e  mov     [rsp+0C30h+dwOptions], eax
0x1801fdc82  lea     pszProgID, aDD; "%d.%d"
0x1801fdc89  mov     clsid, rbx; _BufferCount
0x1801fdc8c  lea     hInstance, [rbp+0B30h+szVersion]; _Buffer
0x1801fdc93  call    swprintf_s
0x1801fdc98  mov     r12, 0FFFFFFFF80000000h
0x1801fdc9f  lea     r15, CmdLine
0x1801fdca6  cmp     cs:?_afxRedirectRegistration@@3HA, 1; int _afxRedirectRegistration
0x1801fdcad  jnz     short loc_1801FDCBD
0x1801fdcaf  lea     r15, aSoftwareClasse; "Software\\Classes\\"
0x1801fdcb6  mov     r12, 0FFFFFFFF80000001h
0x1801fdcbd  mov     r14, rdi
0x1801fdcc0  mov     [rbp+0B30h+hkeyClassID.m_hKey], rdi
0x1801fdcc4  mov     [rbp+0B30h+hkeyClassID.m_samWOW64], edi
0x1801fdcc7  mov     [rbp+0B30h+hkeyClassID.m_pTM], rdi
0x1801fdccb  mov     rsi, rdi
0x1801fdcce  mov     [rbp+0B30h+hkeyProgID.m_hKey], rdi
0x1801fdcd2  mov     [rbp+0B30h+hkeyProgID.m_samWOW64], edi
0x1801fdcd5  mov     [rbp+0B30h+hkeyProgID.m_pTM], rdi
0x1801fdcd9  mov     rax, [rsp+0C30h+strClassID.m_pszData]
0x1801fdcde  mov     qword ptr [rsp+0C30h+dwOptions], rax
0x1801fdce3  mov     r9, r15
0x1801fdce6  lea     pszProgID, aTsclsidTs; "%TsCLSID\\%Ts"
0x1801fdced  mov     clsid, rbx; _BufferCount
0x1801fdcf0  lea     hInstance, [rbp+0B30h+szScratch]; _Buffer
0x1801fdcf7  call    swprintf_s
0x1801fdcfc  mov     rbx, [rsp+0C30h+strTypeName.m_pszData]
0x1801fdd01  cmp     eax, 0FFFFFFFFh
0x1801fdd04  jz      loc_1801FDEB3
0x1801fdd0a  mov     qword ptr [rsp+0C30h+dwOptions], r13
0x1801fdd0f  mov     r9, r15
0x1801fdd12  lea     pszProgID, aTsTs_0; "%Ts%Ts"
0x1801fdd19  mov     edx, 104h; _BufferCount
0x1801fdd1e  lea     hInstance, [rbp+0B30h+szProgID]; _Buffer
0x1801fdd25  call    swprintf_s
0x1801fdd2a  cmp     eax, 0FFFFFFFFh
0x1801fdd2d  jz      loc_1801FDEB3
0x1801fdd33  mov     [rsp+0C30h+var_BE0], rdi
0x1801fdd38  lea     rax, [rsp+0C30h+dwDisposition]
0x1801fdd3d  mov     [rsp+0C30h+lpdwDisposition], rax; lpdwDisposition
0x1801fdd42  lea     rax, [rsp+0C30h+var_BE0]
0x1801fdd47  mov     [rsp+0C30h+phkResult], rax; phkResult
0x1801fdd4c  mov     [rsp+0C30h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1801fdd51  mov     r15d, 2001Fh
0x1801fdd57  mov     [rsp+0C30h+samDesired], r15d; samDesired
0x1801fdd5c  mov     [rsp+0C30h+dwOptions], edi; dwOptions
0x1801fdd60  xor     idTypeName, idTypeName; lpClass
0x1801fdd63  xor     r8d, r8d; Reserved
0x1801fdd66  lea     clsid, [rbp+0B30h+szScratch]; lpSubKey
0x1801fdd6d  mov     hInstance, r12; hKey
0x1801fdd70  call    cs:__imp_RegCreateKeyExW
0x1801fdd76  mov     edx, eax
0x1801fdd78  test    eax, eax
0x1801fdd7a  jnz     short loc_1801FDD88
0x1801fdd7c  mov     r14, [rsp+0C30h+var_BE0]
0x1801fdd81  mov     [rbp+0B30h+hkeyClassID.m_hKey], r14
0x1801fdd85  mov     [rbp+0B30h+hkeyClassID.m_samWOW64], edi
0x1801fdd88  mov     ecx, edx
0x1801fdd8a  neg     ecx
0x1801fdd8c  sbb     eax, eax
0x1801fdd8e  test    edx, eax
0x1801fdd90  jnz     loc_1801FDEB3
0x1801fdd96  mov     [rsp+0C30h+var_BE0], rdi
0x1801fdd9b  lea     rax, [rsp+0C30h+dwDisposition]
0x1801fdda0  mov     [rsp+0C30h+lpdwDisposition], rax; lpdwDisposition
0x1801fdda5  lea     rax, [rsp+0C30h+var_BE0]
0x1801fddaa  mov     [rsp+0C30h+phkResult], rax; phkResult
0x1801fddaf  mov     [rsp+0C30h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1801fddb4  mov     [rsp+0C30h+samDesired], r15d; samDesired
0x1801fddb9  mov     [rsp+0C30h+dwOptions], edi; dwOptions
0x1801fddbd  xor     idTypeName, idTypeName; lpClass
0x1801fddc0  xor     r8d, r8d; Reserved
0x1801fddc3  lea     clsid, [rbp+0B30h+szProgID]; lpSubKey
0x1801fddca  mov     hInstance, r12; hKey
0x1801fddcd  call    cs:__imp_RegCreateKeyExW
0x1801fddd3  mov     edx, eax
0x1801fddd5  test    eax, eax
0x1801fddd7  jnz     short loc_1801FDDE5
0x1801fddd9  mov     rsi, [rsp+0C30h+var_BE0]
0x1801fddde  mov     [rbp+0B30h+hkeyProgID.m_hKey], rsi
0x1801fdde2  mov     [rbp+0B30h+hkeyProgID.m_samWOW64], edi
0x1801fdde5  mov     ecx, edx
0x1801fdde7  neg     ecx
0x1801fdde9  sbb     eax, eax
0x1801fddeb  test    edx, eax
0x1801fdded  jnz     loc_1801FDEB3
0x1801fddf3  mov     [rbp+0B30h+rglpszSymbols], rbx
0x1801fddf7  mov     rax, [rsp+0C30h+strClassID.m_pszData]
0x1801fddfc  mov     [rbp+0B30h+rglpszSymbols+8], rax
0x1801fde00  mov     qword ptr [rsp+0C30h+dwOptions], rsi; hKeyRoot
0x1801fde05  mov     r15d, 1
0x1801fde0b  mov     idTypeName, r15d; bReplace
0x1801fde0e  lea     r8d, [r15+1]; nSymbols
0x1801fde12  lea     clsid, [rbp+0B30h+rglpszSymbols]; rglpszSymbols
0x1801fde16  lea     hInstance, ?_afxCtrlProgID@@3QBQEB_WB; rglpszRegister
0x1801fde1d  call    ?AfxOleRegisterHelper@@YAHPEBQEB_W0HHPEAUHKEY__@@@Z; AfxOleRegisterHelper(wchar_t const * const *,wchar_t const * const *,int,int,HKEY__ *)
0x1801fde22  test    eax, eax
0x1801fde24  jz      loc_1801FDEB3
0x1801fde2a  mov     [rbp+0B30h+rglpszSymbols+8], r13
0x1801fde2e  mov     rax, [rsp+0C30h+strPathName.m_pszData]
0x1801fde33  mov     [rbp+0B30h+rglpszSymbols+10h], rax
0x1801fde37  lea     rax, [rbp+0B30h+szBitmapID]
0x1801fde3e  mov     [rbp+0B30h+rglpszSymbols+18h], rax
0x1801fde42  lea     rax, [rbp+0B30h+szMiscStatus]
0x1801fde49  mov     [rbp+0B30h+rglpszSymbols+20h], rax
0x1801fde4d  lea     hInstance, [rbp+0B30h+szTypeLibID]; String
0x1801fde51  call    cs:__imp_wcslen
0x1801fde57  mov     r8d, eax; nLength
0x1801fde5a  lea     clsid, [rbp+0B30h+szTypeLibID]; pszSrc
0x1801fde5e  lea     hInstance, [rsp+0C30h+strTypeLibID]; this
0x1801fde63  call    ?SetString@?$CSimpleStringT@_W$00@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,1>::SetString(wchar_t const *,int)
0x1801fde68  mov     rax, [rsp+0C30h+strTypeLibID.m_pszData]
0x1801fde6d  mov     [rbp+0B30h+rglpszSymbols+28h], rax
0x1801fde71  lea     rax, [rbp+0B30h+szVersion]
0x1801fde78  mov     [rbp+0B30h+rglpszSymbols+30h], rax
0x1801fde7c  mov     qword ptr [rsp+0C30h+dwOptions], r14; hKeyRoot
0x1801fde81  mov     idTypeName, r15d; bReplace
0x1801fde84  lea     r8d, [r15+6]; nSymbols
0x1801fde88  lea     clsid, [rbp+0B30h+rglpszSymbols]; rglpszSymbols
0x1801fde8c  lea     hInstance, ?_afxCtrlClassID@@3QBQEB_WB; rglpszRegister
0x1801fde93  call    ?AfxOleRegisterHelper@@YAHPEBQEB_W0HHPEAUHKEY__@@@Z; AfxOleRegisterHelper(wchar_t const * const *,wchar_t const * const *,int,int,HKEY__ *)
0x1801fde98  test    eax, eax
0x1801fde9a  jz      short loc_1801FDEB3
0x1801fde9c  mov     r8d, dword ptr [rbp+0B30h+arg_28]; nRegFlags
0x1801fdea3  mov     clsid, r14; hkeyClassID
0x1801fdea6  mov     hInstance, rsi; hkeyProgID
0x1801fdea9  call    ?AfxOleInprocRegisterHelper@@YAHPEAUHKEY__@@0H@Z; AfxOleInprocRegisterHelper(HKEY__ *,HKEY__ *,int)
0x1801fdeae  mov     r15d, eax
0x1801fdeb1  jmp     short loc_1801FDEB6
0x1801fdeb3  mov     r15d, edi
0x1801fdeb6  test    rsi, rsi
0x1801fdeb9  jz      short loc_1801FDEC5
0x1801fdebb  mov     hInstance, rsi; hKey
0x1801fdebe  call    cs:__imp_RegCloseKey
0x1801fdec4  nop
0x1801fdec5  test    r14, r14
0x1801fdec8  jz      short loc_1801FDED4
0x1801fdeca  mov     hInstance, r14; hKey
0x1801fdecd  call    cs:__imp_RegCloseKey
0x1801fded3  nop
0x1801fded4  lea     clsid, [rbx-18h]
0x1801fded8  or      r12d, 0FFFFFFFFh
0x1801fdedc  mov     eax, r12d
0x1801fdedf  lock xadd [clsid+10h], eax
0x1801fdee4  add     eax, r12d
0x1801fdee7  test    eax, eax
0x1801fdee9  jg      short loc_1801FDEFC
0x1801fdeeb  mov     hInstance, [clsid]
0x1801fdeee  mov     rax, [hInstance]
0x1801fdef1  mov     rax, [rax+8]
0x1801fdef5  call    cs:__guard_dispatch_icall_fptr
0x1801fdefb  nop
0x1801fdefc  mov     clsid, [rsp+0C30h+strPathName.m_pszData]
0x1801fdf01  add     clsid, 0FFFFFFFFFFFFFFE8h
0x1801fdf05  mov     eax, r12d
0x1801fdf08  lock xadd [clsid+10h], eax
0x1801fdf0d  add     eax, r12d
0x1801fdf10  test    eax, eax
0x1801fdf12  jg      short loc_1801FDF25
0x1801fdf14  mov     hInstance, [clsid]
0x1801fdf17  mov     rax, [hInstance]
0x1801fdf1a  mov     rax, [rax+8]
0x1801fdf1e  call    cs:__guard_dispatch_icall_fptr
0x1801fdf24  nop
0x1801fdf25  mov     clsid, [rsp+0C30h+strTypeLibID.m_pszData]
0x1801fdf2a  add     clsid, 0FFFFFFFFFFFFFFE8h
0x1801fdf2e  mov     eax, r12d
0x1801fdf31  lock xadd [clsid+10h], eax
0x1801fdf36  add     eax, r12d
0x1801fdf39  test    eax, eax
0x1801fdf3b  jg      short loc_1801FDF4E
0x1801fdf3d  mov     hInstance, [clsid]
0x1801fdf40  mov     rax, [hInstance]
0x1801fdf43  mov     rax, [rax+8]
0x1801fdf47  call    cs:__guard_dispatch_icall_fptr
0x1801fdf4d  nop
0x1801fdf4e  mov     clsid, [rsp+0C30h+strClassID.m_pszData]
0x1801fdf53  add     clsid, 0FFFFFFFFFFFFFFE8h
0x1801fdf57  mov     eax, r12d
0x1801fdf5a  lock xadd [clsid+10h], eax
0x1801fdf5f  add     eax, r12d
0x1801fdf62  test    eax, eax
0x1801fdf64  jg      short loc_1801FDF76
0x1801fdf66  mov     hInstance, [clsid]
0x1801fdf69  mov     rax, [hInstance]
0x1801fdf6c  mov     rax, [rax+8]
0x1801fdf70  call    cs:__guard_dispatch_icall_fptr
0x1801fdf76  mov     eax, r15d
0x1801fdf79  mov     hInstance, [rbp+0B30h+var_50]
0x1801fdf80  xor     hInstance, rsp; StackCookie
0x1801fdf83  call    __security_check_cookie
0x1801fdf88  add     rsp, 0BF8h
0x1801fdf8f  pop     r15
  ... truncated ...
```
