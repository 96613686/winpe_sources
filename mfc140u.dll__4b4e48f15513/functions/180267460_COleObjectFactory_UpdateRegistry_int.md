# COleObjectFactory::UpdateRegistry(int)

- ea: `0x180267460`
- end: `0x18026782c`
- name: `?UpdateRegistry@COleObjectFactory@@MEAAHH@Z`
- size: `972`
- prototype: `int __fastcall(COleObjectFactory *this, int bRegister)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003230`
- `0x1800033dc`
- `0x180003450`
- `0x18000ddc0`
- `0x1801d62b0`
- `0x1801fe650`
- `0x180267460`
- `0x18026f500`
- `0x18026f660`
- `0x1802700b0`
- `0x1802bbce0`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180267755`
- `ADVAPI32!RegCloseKey` at `0x180267755`
- `VCRUNTIME140!memmove` at `0x18026761e`
- `VCRUNTIME140!memmove` at `0x18026761e`
- `VCRUNTIME140!memset` at `0x18026764a`
- `VCRUNTIME140!memset` at `0x18026764a`
- `VCRUNTIME140!memcpy` at `0x180267640`
- `VCRUNTIME140!memcpy` at `0x180267640`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1802675f6`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18026765c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1802675f6`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18026765c`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1802675ea`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18026760a`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180267650`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18026768e`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180267696`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1802676c0`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1802676cb`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1802676fc`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1802675ea`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18026760a`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180267650`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18026768e`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180267696`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1802676c0`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1802676cb`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1802676fc`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180267580`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180267580`
- `ole32!CoTaskMemFree` at `0x180267760`
- `ole32!CoTaskMemFree` at `0x180267760`
- `ole32!StringFromCLSID` at `0x18026750a`
- `ole32!StringFromCLSID` at `0x18026750a`

## string_xrefs

- `0x1802676a4`: `CLSID\%Ts`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall COleObjectFactory::UpdateRegistry(COleObjectFactory *this, int bRegister)
{
  const wchar_t *m_lpszProgID; // rdx
  _GUID *p_m_clsid; // r14
  const wchar_t *v7; // r9
  _GUID *v8; // rcx
  unsigned int v9; // r12d
  HKEY__ *v10; // r15
  wchar_t *m_pszData; // rbx
  HINSTANCE__ *StringResourceHandle; // rax
  int v13; // edi
  unsigned __int64 v14; // r14
  unsigned __int64 v15; // rsi
  wchar_t *v16; // rdx
  size_t v17; // r8
  int v18; // esi
  unsigned int v19; // edi
  int *v20; // rax
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > v21; // [rsp+58h] [rbp-B0h] BYREF
  wchar_t *lpszClassID; // [rsp+60h] [rbp-A8h]
  HKEY__ *hkeyClassID; // [rsp+68h] [rbp-A0h] BYREF
  wchar_t szScratch[1024]; // [rsp+70h] [rbp-98h] BYREF

  m_lpszProgID = this->m_lpszProgID;
  if ( !m_lpszProgID )
    return 0;
  p_m_clsid = &this->m_clsid;
  v7 = this->m_lpszProgID;
  v8 = &this->m_clsid;
  if ( !bRegister )
    return (unsigned int)AfxOleUnregisterServerClass(v8, m_lpszProgID, v7, v7, OAT_DISPATCH_OBJECT, 0, 0);
  v9 = AfxOleRegisterServerClass(v8, m_lpszProgID, v7, v7, OAT_DISPATCH_OBJECT, 0, 0, 0, 0, 0);
  if ( v9 == 1 )
  {
    v9 = 0;
    hkeyClassID = 0;
    if ( StringFromCLSID(p_m_clsid, (LPOLESTR *)&hkeyClassID) < 0 )
    {
LABEL_44:
      AfxOleUnregisterServerClass(
        p_m_clsid,
        this->m_lpszProgID,
        this->m_lpszProgID,
        this->m_lpszProgID,
        OAT_DISPATCH_OBJECT,
        0,
        0);
      return v9;
    }
    v10 = hkeyClassID;
    m_pszData = (wchar_t *)&afxStringManager.GetNilString(&afxStringManager)[1];
    v21.m_pszData = m_pszData;
    if ( !v10 )
      goto LABEL_28;
    if ( (unsigned __int64)v10 < 0x10000 )
    {
      StringResourceHandle = AfxFindStringResourceHandle((unsigned __int16)v10);
      if ( !StringResourceHandle )
        goto LABEL_30;
      ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::LoadStringW(
        &v21,
        StringResourceHandle,
        (unsigned __int16)v10);
      goto LABEL_29;
    }
    v13 = wcslen((const wchar_t *)v10);
    if ( !v13 )
    {
LABEL_28:
      ATL::CSimpleStringT<wchar_t,1>::Empty(&v21);
LABEL_29:
      m_pszData = v21.m_pszData;
LABEL_30:
      v18 = *_errno();
      *_errno() = 0;
      v19 = snwprintf_s(&szScratch[4], 0x400u, 0x3FFu, L"CLSID\\%Ts", m_pszData);
      if ( *_errno() )
      {
        v20 = _errno();
        if ( *v20 )
        {
          if ( *v20 == 12 )
            ATL::AtlThrowImpl(-2147024882);
          if ( *v20 == 22 || *v20 == 34 )
            ATL::AtlThrowImpl(-2147024809);
          if ( *v20 != 80 )
            ATL::AtlThrowImpl(-2147467259);
        }
      }
      else
      {
        *_errno() = v18;
      }
      if ( v19 < 0x400
        && !AfxRegOpenKeyEx((HKEY__ *)0xFFFFFFFF80000000LL, &szScratch[4], 0, 0x2001Fu, (HKEY__ **)szScratch, 0) )
      {
        v9 = AfxOleInprocRegisterHelper(0, *(HKEY *)szScratch, this->m_nFlags);
        RegCloseKey(*(HKEY *)szScratch);
      }
      CoTaskMemFree(hkeyClassID);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)m_pszData - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)m_pszData - 3) + 8LL))(*((_QWORD *)m_pszData - 3));
      if ( v9 )
        return v9;
      goto LABEL_44;
    }
    LODWORD(lpszClassID) = *((_DWORD *)m_pszData - 4);
    v14 = ((char *)v10 - (char *)m_pszData) >> 1;
    if ( v13 < 0 )
LABEL_49:
      ATL::AtlThrowImpl(-2147024809);
    if ( ((1 - *((_DWORD *)m_pszData - 2)) | (*((_DWORD *)m_pszData - 3) - v13)) < 0 )
    {
      ATL::CSimpleStringT<wchar_t,1>::PrepareWrite2(&v21, v13);
      m_pszData = v21.m_pszData;
    }
    v15 = 2LL * v13;
    if ( v14 > (unsigned int)lpszClassID )
    {
      v17 = 2LL * *((int *)m_pszData - 3);
      if ( v15 )
      {
        if ( v17 < v15 )
        {
          memset(m_pszData, 0, v17);
          *_errno() = 34;
          _invalid_parameter_noinfo();
        }
        else
        {
          memcpy(m_pszData, v10, 2LL * v13);
        }
      }
    }
    else
    {
      v16 = &m_pszData[v14];
      if ( !v15 )
        goto LABEL_26;
      if ( !v16 )
      {
        *_errno() = 22;
LABEL_18:
        _invalid_parameter_noinfo();
        goto LABEL_26;
      }
      if ( 2LL * *((int *)m_pszData - 3) < v15 )
      {
        *_errno() = 34;
        goto LABEL_18;
      }
      memmove(m_pszData, v16, 2LL * v13);
    }
LABEL_26:
    if ( v13 <= *((_DWORD *)m_pszData - 3) )
    {
      *((_DWORD *)m_pszData - 4) = v13;
      m_pszData[v15 / 2] = 0;
      p_m_clsid = &this->m_clsid;
      goto LABEL_30;
    }
    goto LABEL_49;
  }
  return v9;
}

```

## disassembly

```asm
0x180267460  mov     rax, rsp
0x180267463  mov     [rax+10h], rbx
0x180267467  mov     [rax+18h], rsi
0x18026746b  mov     [rax+20h], rdi
0x18026746f  push    rbp
0x180267470  push    r12
0x180267472  push    r13
0x180267474  push    r14
0x180267476  push    r15
0x180267478  lea     rbp, [rax-7A8h]
0x18026747f  sub     rsp, 880h
0x180267486  mov     rax, cs:__security_cookie
0x18026748d  xor     rax, rsp
0x180267490  mov     [rbp+7A0h+var_30], rax
0x180267497  mov     eax, bRegister
0x180267499  mov     r13, this
0x18026749c  mov     rdx, [this+70h]; lpszClassName
0x1802674a0  xor     r15d, r15d
0x1802674a3  test    rdx, rdx
0x1802674a6  jnz     short loc_1802674AF
0x1802674a8  xor     eax, eax
0x1802674aa  jmp     loc_1802677D0
0x1802674af  lea     r14, [this+4Ch]
0x1802674b3  mov     r9, rdx; lpszLongTypeName
0x1802674b6  mov     r8, rdx; lpszShortTypeName
0x1802674b9  mov     this, r14; clsid
0x1802674bc  test    eax, eax
0x1802674be  jz      loc_1802677B3
0x1802674c4  mov     [rsp+8A0h+strClassID.m_pszData], r15; lpszFilterExt
0x1802674c9  mov     [rsp+8A0h+lpszFilterName], r15; lpszFilterName
0x1802674ce  mov     [rsp+8A0h+nIconIndex], r15d; nIconIndex
0x1802674d3  mov     [rsp+8A0h+rglpszOverwrite], r15; rglpszOverwrite
0x1802674d8  mov     [rsp+8A0h+rglpszRegister], r15; rglpszRegister
0x1802674dd  mov     [rsp+8A0h+nAppType], 3; nAppType
0x1802674e5  call    ?AfxOleRegisterServerClass@@YAHAEBU_GUID@@PEB_W11W4OLE_APPTYPE@@PEAPEB_W3H11@Z; AfxOleRegisterServerClass(_GUID const &,wchar_t const *,wchar_t const *,wchar_t const *,OLE_APPTYPE,wchar_t const * *,wchar_t const * *,int,wchar_t const *,wchar_t const *)
0x1802674ea  mov     r12d, eax
0x1802674ed  mov     esi, 1
0x1802674f2  cmp     eax, esi
0x1802674f4  jnz     loc_1802677CD
0x1802674fa  mov     r12d, r15d
0x1802674fd  mov     [rsp+8A0h+hkeyClassID], r15
0x180267502  lea     rdx, [rsp+8A0h+hkeyClassID]; lplpsz
0x180267507  mov     this, r14; rclsid
0x18026750a  call    cs:__imp_StringFromCLSID
0x180267510  test    eax, eax
0x180267512  js      loc_18026778D
0x180267518  mov     r15, [rsp+8A0h+hkeyClassID]
0x18026751d  mov     rax, cs:?afxStringManager@@3VCAfxStringMgr@@A.__vftable; CAfxStringMgr afxStringManager ...
0x180267524  lea     this, ?afxStringManager@@3VCAfxStringMgr@@A; CAfxStringMgr afxStringManager
0x18026752b  mov     rax, [rax+18h]
0x18026752f  call    cs:__guard_dispatch_icall_fptr
0x180267535  lea     rbx, [rax+18h]
0x180267539  mov     [rsp+8A0h+var_850.m_pszData], rbx
0x18026753e  test    r15, r15
0x180267541  jz      loc_18026767C
0x180267547  cmp     r15, 10000h
0x18026754e  jnb     short loc_18026757D
0x180267550  movzx   edi, r15w
0x180267554  mov     ecx, edi; nID
0x180267556  call    ?AfxFindStringResourceHandle@@YAPEAUHINSTANCE__@@I@Z; AfxFindStringResourceHandle(uint)
0x18026755b  nop
0x18026755c  xor     r15d, r15d
0x18026755f  test    rax, rax
0x180267562  jz      loc_18026768E
0x180267568  mov     r8d, edi; nID
0x18026756b  mov     rdx, rax; hInstance
0x18026756e  lea     this, [rsp+8A0h+var_850]; this
0x180267573  call    ?LoadStringW@?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAAHPEAUHINSTANCE__@@I@Z; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::LoadStringW(HINSTANCE__ *,uint)
0x180267578  jmp     loc_180267689
0x18026757d  mov     this, r15; String
0x180267580  call    cs:__imp_wcslen
0x180267586  mov     rdi, rax
0x180267589  test    eax, eax
0x18026758b  jz      loc_18026767C
0x180267591  mov     eax, [rbx-10h]
0x180267594  mov     dword ptr [rsp+8A0h+lpszClassID], eax
0x180267598  mov     r14, r15
0x18026759b  sub     r14, rbx
0x18026759e  sar     r14, 1
0x1802675a1  test    edi, edi
0x1802675a3  js      loc_180267816
0x1802675a9  sub     esi, [rbx-8]
0x1802675ac  mov     eax, [rbx-0Ch]
0x1802675af  sub     eax, edi
0x1802675b1  or      eax, esi
0x1802675b3  jge     short loc_1802675C6
0x1802675b5  mov     bRegister, edi; nLength
0x1802675b7  lea     this, [rsp+8A0h+var_850]; this
0x1802675bc  call    ?PrepareWrite2@?$CSimpleStringT@_W$00@ATL@@AEAAXH@Z; ATL::CSimpleStringT<wchar_t,1>::PrepareWrite2(int)
0x1802675c1  mov     rbx, [rsp+8A0h+var_850.m_pszData]
0x1802675c6  movsxd  rsi, edi
0x1802675c9  add     rsi, rsi
0x1802675cc  mov     eax, dword ptr [rsp+8A0h+lpszClassID]
0x1802675d0  cmp     r14, rax
0x1802675d3  ja      short loc_180267626
0x1802675d5  lea     rdx, [rbx+r14*2]; Src
0x1802675d9  xor     r15d, r15d
0x1802675dc  test    rsi, rsi
0x1802675df  jz      loc_180267665
0x1802675e5  test    rdx, rdx
0x1802675e8  jnz     short loc_1802675FE
0x1802675ea  call    cs:__imp__errno
0x1802675f0  mov     dword ptr [rax], 16h
0x1802675f6  call    cs:__imp__invalid_parameter_noinfo
0x1802675fc  jmp     short loc_180267665
0x1802675fe  movsxd  rax, dword ptr [rbx-0Ch]
0x180267602  add     rax, rax
0x180267605  cmp     rax, rsi
0x180267608  jnb     short loc_180267618
0x18026760a  call    cs:__imp__errno
0x180267610  mov     dword ptr [rax], 22h ; '"'
0x180267616  jmp     short loc_1802675F6
0x180267618  mov     r8, rsi; Size
0x18026761b  mov     this, rbx; void *
0x18026761e  call    cs:__imp_memmove
0x180267624  jmp     short loc_180267665
0x180267626  movsxd  r8, dword ptr [rbx-0Ch]
0x18026762a  add     r8, r8; Size
0x18026762d  test    rsi, rsi
0x180267630  jz      short loc_180267662
0x180267632  mov     this, rbx; void *
0x180267635  cmp     r8, rsi
0x180267638  jb      short loc_180267648
0x18026763a  mov     r8, rsi; Size
0x18026763d  mov     rdx, r15; Src
0x180267640  call    cs:__imp_memcpy
0x180267646  jmp     short loc_180267662
0x180267648  xor     bRegister, bRegister; Val
0x18026764a  call    cs:__imp_memset
0x180267650  call    cs:__imp__errno
0x180267656  mov     dword ptr [rax], 22h ; '"'
0x18026765c  call    cs:__imp__invalid_parameter_noinfo
0x180267662  xor     r15d, r15d
0x180267665  cmp     edi, [rbx-0Ch]
0x180267668  jg      loc_180267816
0x18026766e  mov     [rbx-10h], edi
0x180267671  mov     [rsi+rbx], r15w
0x180267676  lea     r14, [r13+4Ch]
0x18026767a  jmp     short loc_18026768E
0x18026767c  lea     this, [rsp+8A0h+var_850]; this
0x180267681  call    ?Empty@?$CSimpleStringT@_W$00@ATL@@QEAAXXZ; ATL::CSimpleStringT<wchar_t,1>::Empty(void)
0x180267686  xor     r15d, r15d
0x180267689  mov     rbx, [rsp+8A0h+var_850.m_pszData]
0x18026768e  call    cs:__imp__errno
0x180267694  mov     esi, [rax]
0x180267696  call    cs:__imp__errno
0x18026769c  mov     [rax], r15d
0x18026769f  mov     qword ptr [rsp+8A0h+nAppType], rbx
0x1802676a4  lea     r9, aClsidTs; "CLSID\\%Ts"
0x1802676ab  mov     bRegister, 400h; _BufferCount
0x1802676b0  lea     r8d, [rdx-1]; _MaxCount
0x1802676b4  lea     this, [rsp+8A0h+szScratch+8]; _Buffer
0x1802676b9  call    _snwprintf_s
0x1802676be  mov     edi, eax
0x1802676c0  call    cs:__imp__errno
0x1802676c6  cmp     [rax], r15d
0x1802676c9  jz      short loc_1802676FC
0x1802676cb  call    cs:__imp__errno
0x1802676d1  cmp     [rax], r15d
0x1802676d4  jz      short loc_180267704
0x1802676d6  cmp     dword ptr [rax], 0Ch
0x1802676d9  jz      loc_180267800
0x1802676df  cmp     dword ptr [rax], 16h
0x1802676e2  jz      loc_180267821
0x1802676e8  cmp     dword ptr [rax], 22h ; '"'
0x1802676eb  jz      loc_180267821
0x1802676f1  cmp     dword ptr [rax], 50h ; 'P'
0x1802676f4  jnz     loc_18026780B
0x1802676fa  jmp     short loc_180267704
0x1802676fc  call    cs:__imp__errno
0x180267702  mov     [rax], esi
0x180267704  test    edi, edi
0x180267706  js      short loc_18026775B
0x180267708  cmp     edi, 400h
0x18026770e  jnb     short loc_18026775B
0x180267710  mov     [rsp+8A0h+rglpszRegister], r15; pTM
0x180267715  lea     rax, [rsp+8A0h+szScratch]
0x18026771a  mov     qword ptr [rsp+8A0h+nAppType], rax; phkResult
0x18026771f  mov     r9d, 2001Fh; samDesired
0x180267725  xor     r8d, r8d; ulOptions
0x180267728  lea     rdx, [rsp+8A0h+szScratch+8]; lpSubKey
0x18026772d  mov     this, 0FFFFFFFF80000000h; hKey
0x180267734  call    ?AfxRegOpenKeyEx@@YAJPEAUHKEY__@@PEB_WKKPEAPEAU1@PEAVCAtlTransactionManager@ATL@@@Z; AfxRegOpenKeyEx(HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *,ATL::CAtlTransactionManager *)
0x180267739  test    eax, eax
0x18026773b  jnz     short loc_18026775B
0x18026773d  mov     r8d, [r13+6Ch]; nRegFlags
0x180267741  mov     rdx, qword ptr [rsp+8A0h+szScratch]; hkeyClassID
0x180267746  xor     ecx, ecx; hkeyProgID
0x180267748  call    ?AfxOleInprocRegisterHelper@@YAHPEAUHKEY__@@0H@Z; AfxOleInprocRegisterHelper(HKEY__ *,HKEY__ *,int)
0x18026774d  mov     r12d, eax
0x180267750  mov     this, qword ptr [rsp+8A0h+szScratch]; hKey
0x180267755  call    cs:__imp_RegCloseKey
0x18026775b  mov     this, [rsp+8A0h+hkeyClassID]; pv
0x180267760  call    cs:__imp_CoTaskMemFree
0x180267766  nop
0x180267767  lea     rdx, [rbx-18h]
0x18026776b  or      eax, 0FFFFFFFFh
0x18026776e  lock xadd [rdx+10h], eax
0x180267773  sub     eax, 1
0x180267776  jg      short loc_180267788
0x180267778  mov     this, [rdx]
0x18026777b  mov     rax, [this]
0x18026777e  mov     rax, [rax+8]
0x180267782  call    cs:__guard_dispatch_icall_fptr
0x180267788  test    r12d, r12d
0x18026778b  jnz     short loc_1802677CD
0x18026778d  mov     rdx, [r13+70h]; lpszClassName
0x180267791  mov     [rsp+8A0h+rglpszOverwrite], r15; rglpszOverwrite
0x180267796  mov     [rsp+8A0h+rglpszRegister], r15; rglpszRegister
0x18026779b  mov     [rsp+8A0h+nAppType], 3; nAppType
0x1802677a3  mov     r9, rdx; lpszLongTypeName
0x1802677a6  mov     r8, rdx; lpszShortTypeName
0x1802677a9  mov     this, r14; clsid
0x1802677ac  call    ?AfxOleUnregisterServerClass@@YAHAEBU_GUID@@PEB_W11W4OLE_APPTYPE@@PEAPEB_W3@Z; AfxOleUnregisterServerClass(_GUID const &,wchar_t const *,wchar_t const *,wchar_t const *,OLE_APPTYPE,wchar_t const * *,wchar_t const * *)
0x1802677b1  jmp     short loc_1802677CD
0x1802677b3  mov     [rsp+8A0h+rglpszOverwrite], r15; rglpszOverwrite
0x1802677b8  mov     [rsp+8A0h+rglpszRegister], r15; rglpszRegister
0x1802677bd  mov     [rsp+8A0h+nAppType], 3; nAppType
0x1802677c5  call    ?AfxOleUnregisterServerClass@@YAHAEBU_GUID@@PEB_W11W4OLE_APPTYPE@@PEAPEB_W3@Z; AfxOleUnregisterServerClass(_GUID const &,wchar_t const *,wchar_t const *,wchar_t const *,OLE_APPTYPE,wchar_t const * *,wchar_t const * *)
0x1802677ca  mov     r12d, eax
0x1802677cd  mov     eax, r12d
0x1802677d0  mov     this, [rbp+7A0h+var_30]
0x1802677d7  xor     this, rsp; StackCookie
0x1802677da  call    __security_check_cookie
0x1802677df  lea     r11, [rsp+8A0h+var_20]
0x1802677e7  mov     rbx, [r11+38h]
0x1802677eb  mov     rsi, [r11+40h]
0x1802677ef  mov     rdi, [r11+48h]
0x1802677f3  mov     rsp, r11
0x1802677f6  pop     r15
0x1802677f8  pop     r14
0x1802677fa  pop     r13
0x1802677fc  pop     r12
0x1802677fe  pop     rbp
0x1802677ff  retn
0x180267800  mov     ecx, 8007000Eh; hr
0x180267805  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18026780b  mov     ecx, 80004005h; hr
0x180267810  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180267816  mov     ecx, 80070057h; hr
0x18026781b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180267821  mov     ecx, 80070057h; hr
0x180267826  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
