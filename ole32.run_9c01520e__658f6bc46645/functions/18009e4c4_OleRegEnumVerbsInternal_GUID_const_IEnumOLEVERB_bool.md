# OleRegEnumVerbsInternal(_GUID const &,IEnumOLEVERB * *,bool)

- ea: `0x18009e4c4`
- end: `0x18009e994`
- name: `?OleRegEnumVerbsInternal@@YAJAEBU_GUID@@PEAPEAUIEnumOLEVERB@@_N@Z`
- size: `1232`
- prototype: `HRESULT __fastcall(const _GUID *clsid, IEnumOLEVERB **ppenum, bool clsid)`
- caller_count: `3`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800977d0`
- `0x18009eb60`
- `0x1800a36b0`

## callees

- `0x18000f358`
- `0x18000fc2c`
- `0x18001217c`
- `0x18001a630`
- `0x18001d110`
- `0x18002d698`
- `0x180033bb0`
- `0x180046460`
- `0x180046c08`
- `0x180047484`
- `0x18004cbb8`
- `0x18009dddc`
- `0x18009dec4`
- `0x18009e4c4`
- `0x18009eac8`
- `0x18009eb34`
- `0x1800c9adc`
- `0x1800cb184`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009e942`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009e942`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009e8cc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009e8cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009e828`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009e861`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009e89e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009e828`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009e861`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009e89e`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x18009e643`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x18009e643`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18009e73d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18009e73d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009e690`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009e6d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009e6e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009e690`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009e6d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009e6e4`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x18009e61f`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x18009e61f`

## string_xrefs

- `0x18009e6fa`: `CLSID\`
- `0x18009e71c`: `com\ole32\ole232\stdimpl\oregverb.cpp`
- `0x18009e7ae`: `com\ole32\ole232\stdimpl\oregverb.cpp`

## pseudocode

```c
__int64 __fastcall OleRegEnumVerbsInternal(const _GUID *clsid, IEnumOLEVERB **ppenum, bool a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rax
  struct IUnknownVtbl *lpVtbl; // rax
  __int64 v10; // rcx
  IOleClassInfo *m_ptr; // rcx
  IMrtResourceManager *v12; // r8
  IResourceContext *v13; // r9
  HRESULT OleClassInfoVerbIterator; // eax
  unsigned int v15; // edx
  BOOL IsOle1Class; // r12d
  HRESULT VerbList; // eax
  HRESULT v18; // esi
  unsigned __int64 v19; // rsi
  int v20; // r15d
  unsigned int v21; // edx
  unsigned int v22; // edx
  unsigned __int64 v23; // rsi
  CEnumVerb *v24; // rax
  IEnumOLEVERB *v25; // rax
  __int64 v26; // rbx
  unsigned int v28; // [rsp+28h] [rbp-D8h]
  RegistryKey classKey; // [rsp+30h] [rbp-D0h] BYREF
  wil::com_ptr_t<IOleVerbIterator,wil::err_returncode_policy> verbIterator; // [rsp+38h] [rbp-C8h] BYREF
  wil::com_ptr_t<IOleClassInfo,wil::err_returncode_policy> oleClassInfo; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *psz; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 cchBase; // [rsp+50h] [rbp-B0h] BYREF
  VerbList *pVerbList; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 cchRemain; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *pwszBase; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *v37; // [rsp+70h] [rbp-90h] BYREF
  OLECHAR szClsid[40]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t szKey[256]; // [rsp+D0h] [rbp-30h] BYREF
  void *retaddr; // [rsp+318h] [rbp+218h]

  pVerbList = 0;
  memset_0(szKey, 0, sizeof(szKey));
  cchBase = 0;
  oleClassInfo.m_ptr = 0;
  verbIterator.m_ptr = 0;
  if ( !IsValidPtrOut(ppenum, 8u) )
  {
    v5 = -2147024809;
    goto $errSafeRtn_0;
  }
  *ppenum = 0;
  v6 = _InterlockedExchange64((volatile __int64 *)&g_EnumCache, 0);
  if ( v6 )
  {
    v7 = *(_QWORD *)(v6 + 16);
    v8 = *(_QWORD *)&clsid->Data1 - *(_QWORD *)(v7 + 4);
    if ( *(_QWORD *)&clsid->Data1 == *(_QWORD *)(v7 + 4) )
      v8 = *(_QWORD *)clsid->Data4 - *(_QWORD *)(v7 + 12);
    if ( !v8 )
    {
      if ( *(_DWORD *)(v6 + 8) == 1 )
      {
        *ppenum = (IEnumOLEVERB *)v6;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
        lpVtbl = *(struct IUnknownVtbl **)v6;
        v10 = v6;
      }
      else
      {
        if ( (*(unsigned int (__fastcall **)(__int64, IEnumOLEVERB **))(*(_QWORD *)v6 + 48LL))(v6, ppenum) )
        {
LABEL_55:
          v26 = _InterlockedExchange64((volatile __int64 *)&g_EnumCache, v6);
          if ( v26 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
          v5 = *ppenum == 0 ? 0x8007000E : 0;
          goto $errSafeRtn_0;
        }
        v10 = (__int64)*ppenum;
        lpVtbl = (*ppenum)->lpVtbl;
      }
      ((void (__fastcall *)(__int64))lpVtbl[1].Release)(v10);
      goto LABEL_55;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  m_ptr = oleClassInfo.m_ptr;
  oleClassInfo.m_ptr = 0;
  if ( m_ptr )
    ((void (__fastcall *)(IOleClassInfo *))m_ptr->lpVtbl->Release)(m_ptr);
  if ( GetClassInfoWithInprocOrLocalServer(
         clsid,
         0,
         &GUID_e942fe11_d674_da46_8c4f_c9568fc9d593,
         (void **)&oleClassInfo.m_ptr) >= 0 )
  {
    wil::com_ptr_t<IOleVerbIterator,wil::err_returncode_policy>::reset(&verbIterator);
    OleClassInfoVerbIterator = GetOleClassInfoVerbIterator(oleClassInfo.m_ptr, &verbIterator.m_ptr, v12, v13);
    v5 = OleClassInfoVerbIterator;
    if ( OleClassInfoVerbIterator < 0 )
    {
      v15 = 264;
LABEL_36:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        v15,
        "com\\ole32\\ole232\\stdimpl\\oregverb.cpp",
        OleClassInfoVerbIterator);
      goto $errSafeRtn_0;
    }
    goto LABEL_46;
  }
  IsOle1Class = CoIsOle1Class(clsid);
  if ( !IsOle1Class )
  {
    v18 = StringCchCopyW(szKey, 0x100u, L"CLSID\\");
    if ( v18 >= 0 )
    {
      StringFromGUID2(clsid, szClsid, 39);
      v18 = StringCchCatW(szKey, 0x100u, szClsid);
      if ( v18 >= 0 )
      {
        v18 = StringCchLengthW(szKey, 0x100u, &cchBase);
        if ( v18 >= 0 )
        {
          v19 = cchBase;
          goto LABEL_34;
        }
        v21 = 311;
      }
      else
      {
        v21 = 310;
      }
    }
    else
    {
      v21 = 305;
    }
    wil::details::in1diag3::Return_Hr(retaddr, v21, "com\\ole32\\ole232\\stdimpl\\oregverb.cpp", v18);
    goto LABEL_22;
  }
  psz = 0;
  VerbList = ProgIDFromCLSID(clsid, &psz);
  if ( VerbList )
    goto LABEL_47;
  cchRemain = 0;
  pwszBase = 0;
  v18 = StringCchCopyExW(szKey, 0x100u, psz, &pwszBase, &cchRemain, v28);
  if ( v18 < 0 )
  {
    CoTaskMemFree(psz);
LABEL_22:
    v5 = v18;
    goto $errSafeRtn_0;
  }
  v19 = 256 - cchRemain;
  cchBase = 256 - cchRemain;
  v20 = StringCchCopyW(pwszBase, cchRemain, STDFILE);
  if ( v20 < 0 )
  {
    CoTaskMemFree(psz);
    v5 = v20;
    goto $errSafeRtn_0;
  }
  CoTaskMemFree(psz);
LABEL_34:
  OleClassInfoVerbIterator = StringCchCatW(szKey, 0x100u, VERB);
  v5 = OleClassInfoVerbIterator;
  if ( OleClassInfoVerbIterator < 0 )
  {
    v15 = 315;
    goto LABEL_36;
  }
  wil::com_ptr_t<IOleVerbIterator,wil::err_returncode_policy>::reset(&verbIterator);
  v37 = szKey;
  if ( Microsoft::WRL::Details::MakeAndInitialize<RegistryVerbIterator,IOleVerbIterator,unsigned short const * &>(
         &verbIterator.m_ptr,
         (const wchar_t **)&v37) >= 0 )
    goto LABEL_46;
  v23 = v19;
  if ( v23 >= 256 )
    _report_rangecheckfailure();
  szKey[v23] = 0;
  classKey._hkey = 0;
  if ( RegistryKey::StaticOpenFromClassesRoot(szKey, v22, (HKEY__ **)&classKey._hkey) >= 0 )
  {
    if ( IsOle1Class )
    {
      wil::com_ptr_t<IOleVerbIterator,wil::err_returncode_policy>::reset(&verbIterator);
      if ( classKey._hkey )
      {
        RegCloseKey(classKey._hkey);
        classKey._hkey = 0;
      }
LABEL_46:
      VerbList = MakeVerbList(verbIterator.m_ptr, clsid, &pVerbList);
      if ( !VerbList )
      {
        v24 = (CEnumVerb *)HeapAlloc(g_hHeap, 0, 0x18u);
        if ( !v24 || (CEnumVerb::CEnumVerb(v24, pVerbList, 0), (v6 = (__int64)v25) == 0) )
        {
          HeapFree(g_hHeap, 0, pVerbList);
          v5 = -2147024882;
          goto $errSafeRtn_0;
        }
        *ppenum = v25;
        ((void (__fastcall *)(IEnumOLEVERB *))v25->lpVtbl->AddRef)(v25);
        goto LABEL_55;
      }
LABEL_47:
      v5 = VerbList;
      goto $errSafeRtn_0;
    }
    if ( classKey._hkey )
    {
      RegCloseKey(classKey._hkey);
      classKey._hkey = 0;
    }
    v5 = -2147221120;
  }
  else
  {
    if ( classKey._hkey )
    {
      RegCloseKey(classKey._hkey);
      classKey._hkey = 0;
    }
    v5 = -2147221164;
  }
$errSafeRtn_0:
  wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&verbIterator);
  wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&oleClassInfo);
  return v5;
}

```

## disassembly

```asm
0x18009e4c4  mov     [rsp-8+arg_10], rbx
0x18009e4c9  push    rbp
0x18009e4ca  push    rsi
0x18009e4cb  push    rdi
0x18009e4cc  push    r12
0x18009e4ce  push    r13
0x18009e4d0  push    r14
0x18009e4d2  push    r15
0x18009e4d4  lea     rbp, [rsp-1E0h]
0x18009e4dc  sub     rsp, 2E0h
0x18009e4e3  mov     rax, cs:__security_cookie
0x18009e4ea  xor     rax, rsp
0x18009e4ed  mov     [rbp+210h+var_40], rax
0x18009e4f4  mov     r14, ppenum
0x18009e4f7  mov     rdi, clsid
0x18009e4fa  xor     r13d, r13d
0x18009e4fd  lea     clsid, [rbp+210h+szKey]; void *
0x18009e501  xor     edx, edx; Val
0x18009e503  mov     [rsp+310h+pVerbList], r13
0x18009e508  mov     r8d, 200h; Size
0x18009e50e  call    memset_0
0x18009e513  lea     edx, [r13+8]; cb
0x18009e517  mov     [rsp+310h+cchBase], r13
0x18009e51c  mov     clsid, r14; pv
0x18009e51f  mov     [rsp+310h+oleClassInfo.m_ptr], r13
0x18009e524  mov     [rsp+310h+verbIterator.m_ptr], r13
0x18009e529  call    ?IsValidPtrOut@@YAHPEAX_K@Z; IsValidPtrOut(void *,unsigned __int64)
0x18009e52e  test    eax, eax
0x18009e530  jnz     short loc_18009E53C
0x18009e532  mov     ebx, 80070057h
0x18009e537  jmp     $errSafeRtn_0
0x18009e53c  mov     rbx, r13
0x18009e53f  mov     [r14], r13
0x18009e542  xchg    rbx, cs:?g_EnumCache@@3UEnumVerbCache@@A.pEnum; EnumVerbCache g_EnumCache ...
0x18009e549  test    rbx, rbx
0x18009e54c  jz      short loc_18009E5BA
0x18009e54e  mov     clsid, [rbx+10h]
0x18009e552  mov     rax, [rdi]
0x18009e555  sub     rax, [clsid+4]
0x18009e559  jnz     short loc_18009E563
0x18009e55b  mov     rax, [rdi+8]
0x18009e55f  sub     rax, [clsid+0Ch]
0x18009e563  mov     clsid, rbx
0x18009e566  test    rax, rax
0x18009e569  jnz     short loc_18009E5AE
0x18009e56b  cmp     dword ptr [rbx+8], 1
0x18009e56f  jnz     short loc_18009E588
0x18009e571  mov     [r14], rbx
0x18009e574  mov     rax, [rbx]
0x18009e577  mov     rax, [rax+8]
0x18009e57b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e580  mov     rax, [rbx]
0x18009e583  mov     clsid, rbx
0x18009e586  jmp     short loc_18009E5A5
0x18009e588  mov     rax, [rbx]
0x18009e58b  mov     ppenum, r14
0x18009e58e  mov     rax, [rax+30h]
0x18009e592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e597  test    eax, eax
0x18009e599  jnz     loc_18009E907
0x18009e59f  mov     clsid, [r14]
0x18009e5a2  mov     rax, [clsid]
0x18009e5a5  mov     rax, [rax+28h]
0x18009e5a9  jmp     loc_18009E902
0x18009e5ae  mov     rax, [rbx]
0x18009e5b1  mov     rax, [rax+10h]
0x18009e5b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e5ba  mov     clsid, [rsp+310h+oleClassInfo.m_ptr]
0x18009e5bf  mov     [rsp+310h+oleClassInfo.m_ptr], r13
0x18009e5c4  test    clsid, clsid
0x18009e5c7  jz      short loc_18009E5D5
0x18009e5c9  mov     rax, [clsid]
0x18009e5cc  mov     rax, [rax+10h]
0x18009e5d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e5d5  lea     r9, [rsp+310h+oleClassInfo]; ppv
0x18009e5da  xor     edx, edx; pComCatalog
0x18009e5dc  lea     r8, _GUID_e942fe11_d674_da46_8c4f_c9568fc9d593; riid
0x18009e5e3  mov     clsid, rdi; clsid
0x18009e5e6  call    ?GetClassInfoWithInprocOrLocalServer@@YAJAEBU_GUID@@PEAUIComCatalogSCM@@0PEAPEAX@Z; GetClassInfoWithInprocOrLocalServer(_GUID const &,IComCatalogSCM *,_GUID const &,void * *)
0x18009e5eb  test    eax, eax
0x18009e5ed  js      short loc_18009E61C
0x18009e5ef  lea     clsid, [rsp+310h+verbIterator]; this
0x18009e5f4  call    ?reset@?$com_ptr_t@UIOleVerbIterator@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IOleVerbIterator,wil::err_returncode_policy>::reset(void)
0x18009e5f9  mov     clsid, [rsp+310h+oleClassInfo.m_ptr]; oleClassInfo
0x18009e5fe  lea     ppenum, [rsp+310h+verbIterator]; verbIterator
0x18009e603  call    ?GetOleClassInfoVerbIterator@@YAJPEAUIOleClassInfo@@PEAPEAUIOleVerbIterator@@PEAUIMrtResourceManager@@PEAUIResourceContext@@@Z; GetOleClassInfoVerbIterator(IOleClassInfo *,IOleVerbIterator * *,IMrtResourceManager *,IResourceContext *)
0x18009e608  mov     ebx, eax
0x18009e60a  test    eax, eax
0x18009e60c  jns     loc_18009E872
0x18009e612  mov     edx, 108h
0x18009e617  jmp     loc_18009E7A7
0x18009e61c  mov     clsid, rdi; rclsid
0x18009e61f  call    cs:__imp_CoIsOle1Class
0x18009e626  nop     dword ptr [rax+rax+00h]
0x18009e62b  mov     r12d, eax
0x18009e62e  test    eax, eax
0x18009e630  jz      loc_18009E6F5
0x18009e636  lea     ppenum, [rsp+310h+psz]; lplpszProgID
0x18009e63b  mov     [rsp+310h+psz], r13
0x18009e640  mov     clsid, rdi; clsid
0x18009e643  call    cs:__imp_ProgIDFromCLSID
0x18009e64a  nop     dword ptr [rax+rax+00h]
0x18009e64f  test    eax, eax
0x18009e651  jnz     loc_18009E888
0x18009e657  mov     r8, [rsp+310h+psz]; pszSrc
0x18009e65c  lea     rax, [rsp+310h+cchRemain]
0x18009e661  mov     ebx, 100h
0x18009e666  mov     [rsp+310h+cchRemain], r13
0x18009e66b  mov     edx, ebx; cchDest
0x18009e66d  mov     [rsp+310h+pwszBase], r13
0x18009e672  lea     r9, [rsp+310h+pwszBase]; ppszDestEnd
0x18009e677  mov     [rsp+310h+pcchRemaining], rax; pcchRemaining
0x18009e67c  lea     clsid, [rbp+210h+szKey]; pszDest
0x18009e680  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18009e685  mov     esi, eax
0x18009e687  test    eax, eax
0x18009e689  jns     short loc_18009E6A3
0x18009e68b  mov     clsid, [rsp+310h+psz]; pv
0x18009e690  call    cs:__imp_CoTaskMemFree
0x18009e697  nop     dword ptr [rax+rax+00h]
0x18009e69c  mov     ebx, esi
0x18009e69e  jmp     $errSafeRtn_0
0x18009e6a3  mov     ppenum, [rsp+310h+cchRemain]; cchDest
0x18009e6a8  lea     r8, STDFILE; pszSrc
0x18009e6af  mov     clsid, [rsp+310h+pwszBase]; pszDest
0x18009e6b4  mov     rsi, rbx
0x18009e6b7  sub     rsi, ppenum
0x18009e6ba  mov     [rsp+310h+cchBase], rsi
0x18009e6bf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009e6c4  mov     clsid, [rsp+310h+psz]; pv
0x18009e6c9  mov     r15d, eax
0x18009e6cc  test    eax, eax
0x18009e6ce  jns     short loc_18009E6E4
0x18009e6d0  call    cs:__imp_CoTaskMemFree
0x18009e6d7  nop     dword ptr [rax+rax+00h]
0x18009e6dc  mov     ebx, r15d
0x18009e6df  jmp     $errSafeRtn_0
0x18009e6e4  call    cs:__imp_CoTaskMemFree
0x18009e6eb  nop     dword ptr [rax+rax+00h]
0x18009e6f0  jmp     loc_18009E789
0x18009e6f5  mov     ebx, 100h
0x18009e6fa  lea     r8, aClsid_0; "CLSID\\"
0x18009e701  mov     edx, ebx; cchDest
0x18009e703  lea     clsid, [rbp+210h+szKey]; pszDest
0x18009e707  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009e70c  mov     esi, eax
0x18009e70e  test    eax, eax
0x18009e710  jns     short loc_18009E730
0x18009e712  lea     edx, [rbx+31h]; lineNumber
0x18009e715  mov     clsid, [rbp+218h]; callerReturnAddress
0x18009e71c  lea     r8, aComOle32Ole232_10; "com\\ole32\\ole232\\stdimpl\\oregverb.c"...
0x18009e723  mov     r9d, esi; hr
0x18009e726  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009e72b  jmp     loc_18009E69C
0x18009e730  mov     r8d, 27h ; '''; cchMax
0x18009e736  lea     ppenum, [rbp+210h+szClsid]; lpsz
0x18009e73a  mov     clsid, rdi; rguid
0x18009e73d  call    cs:__imp_StringFromGUID2
0x18009e744  nop     dword ptr [rax+rax+00h]
0x18009e749  lea     r8, [rbp+210h+szClsid]; pszSrc
0x18009e74d  mov     ppenum, rbx; cchDest
0x18009e750  lea     clsid, [rbp+210h+szKey]; pszDest
0x18009e754  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18009e759  mov     esi, eax
0x18009e75b  test    eax, eax
0x18009e75d  jns     short loc_18009E766
0x18009e75f  mov     edx, 136h
0x18009e764  jmp     short loc_18009E715
0x18009e766  lea     r8, [rsp+310h+cchBase]; pcchLength
0x18009e76b  mov     ppenum, rbx; cchMax
0x18009e76e  lea     clsid, [rbp+210h+szKey]; psz
0x18009e772  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18009e777  mov     esi, eax
0x18009e779  test    eax, eax
0x18009e77b  jns     short loc_18009E784
0x18009e77d  mov     edx, 137h
0x18009e782  jmp     short loc_18009E715
0x18009e784  mov     rsi, [rsp+310h+cchBase]
0x18009e789  lea     r8, VERB; pszSrc
0x18009e790  mov     ppenum, rbx; cchDest
0x18009e793  lea     clsid, [rbp+210h+szKey]; pszDest
0x18009e797  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18009e79c  mov     ebx, eax
0x18009e79e  test    eax, eax
0x18009e7a0  jns     short loc_18009E7C2
0x18009e7a2  mov     edx, 13Bh; lineNumber
0x18009e7a7  mov     clsid, [rbp+218h]; callerReturnAddress
0x18009e7ae  lea     r8, aComOle32Ole232_10; "com\\ole32\\ole232\\stdimpl\\oregverb.c"...
0x18009e7b5  mov     r9d, eax; hr
0x18009e7b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009e7bd  jmp     $errSafeRtn_0
0x18009e7c2  lea     clsid, [rsp+310h+verbIterator]; this
0x18009e7c7  call    ?reset@?$com_ptr_t@UIOleVerbIterator@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IOleVerbIterator,wil::err_returncode_policy>::reset(void)
0x18009e7cc  lea     rax, [rbp+210h+szKey]
0x18009e7d0  lea     ppenum, [rsp+310h+var_2A0]; <args_0>
0x18009e7d5  mov     [rsp+310h+var_2A0], rax
0x18009e7da  lea     clsid, [rsp+310h+verbIterator]; result
0x18009e7df  call    ??$MakeAndInitialize@VRegistryVerbIterator@@UIOleVerbIterator@@AEAPEBG@Details@WRL@Microsoft@@YAJPEAPEAUIOleVerbIterator@@AEAPEBG@Z; Microsoft::WRL::Details::MakeAndInitialize<RegistryVerbIterator,IOleVerbIterator,ushort const * &>(IOleVerbIterator * *,ushort const * &)
0x18009e7e4  test    eax, eax
0x18009e7e6  jns     loc_18009E872
0x18009e7ec  add     rsi, rsi
0x18009e7ef  cmp     rsi, 200h
0x18009e7f6  jnb     loc_18009E8B9
0x18009e7fc  mov     [rbp+rsi+210h+szKey], r13w
0x18009e802  lea     r8, [rsp+310h+classKey]; pszSubKeyPath
0x18009e807  lea     clsid, [rbp+210h+szKey]; pszSubKeyPath
0x18009e80b  mov     [rsp+310h+classKey._hkey], r13
0x18009e810  call    ?StaticOpenFromClassesRoot@RegistryKey@@CAJPEBGKPEAPEAUHKEY__@@@Z; RegistryKey::StaticOpenFromClassesRoot(ushort const *,ulong,HKEY__ * *)
0x18009e815  test    eax, eax
0x18009e817  jns     short loc_18009E843
0x18009e819  mov     rax, [rsp+310h+classKey._hkey]
0x18009e81e  test    rax, rax
0x18009e821  jz      short loc_18009E839
0x18009e823  mov     clsid, [rsp+310h+classKey._hkey]; hKey
0x18009e828  call    cs:__imp_RegCloseKey
0x18009e82f  nop     dword ptr [rax+rax+00h]
0x18009e834  mov     [rsp+310h+classKey._hkey], r13
0x18009e839  mov     ebx, 80040154h
0x18009e83e  jmp     $errSafeRtn_0
0x18009e843  test    r12d, r12d
0x18009e846  jz      short loc_18009E88F
0x18009e848  lea     clsid, [rsp+310h+verbIterator]; this
0x18009e84d  call    ?reset@?$com_ptr_t@UIOleVerbIterator@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IOleVerbIterator,wil::err_returncode_policy>::reset(void)
0x18009e852  mov     rax, [rsp+310h+classKey._hkey]
0x18009e857  test    rax, rax
0x18009e85a  jz      short loc_18009E872
0x18009e85c  mov     clsid, [rsp+310h+classKey._hkey]; hKey
0x18009e861  call    cs:__imp_RegCloseKey
0x18009e868  nop     dword ptr [rax+rax+00h]
0x18009e86d  mov     [rsp+310h+classKey._hkey], r13
0x18009e872  mov     clsid, [rsp+310h+verbIterator.m_ptr]; verbIterator
0x18009e877  lea     r8, [rsp+310h+pVerbList]; verbList
0x18009e87c  mov     ppenum, rdi; clsid
0x18009e87f  call    ?MakeVerbList@@YAJPEAUIOleVerbIterator@@AEBU_GUID@@PEAPEAUVerbList@@@Z; MakeVerbList(IOleVerbIterator *,_GUID const &,VerbList * *)
0x18009e884  test    eax, eax
0x18009e886  jz      short loc_18009E8BF
0x18009e888  mov     ebx, eax
0x18009e88a  jmp     $errSafeRtn_0
0x18009e88f  mov     rax, [rsp+310h+classKey._hkey]
0x18009e894  test    rax, rax
0x18009e897  jz      short loc_18009E8AF
0x18009e899  mov     clsid, [rsp+310h+classKey._hkey]; hKey
0x18009e89e  call    cs:__imp_RegCloseKey
0x18009e8a5  nop     dword ptr [rax+rax+00h]
0x18009e8aa  mov     [rsp+310h+classKey._hkey], r13
0x18009e8af  mov     ebx, 80040180h
0x18009e8b4  jmp     $errSafeRtn_0
0x18009e8b9  call    __report_rangecheckfailure
0x18009e8bf  mov     clsid, cs:?g_hHeap@@3QEAXEA; hHeap
0x18009e8c6  xor     edx, edx; dwFlags
0x18009e8c8  lea     r8d, [ppenum+18h]; dwBytes
0x18009e8cc  call    cs:__imp_HeapAlloc
0x18009e8d3  nop     dword ptr [rax+rax+00h]
0x18009e8d8  test    rax, rax
0x18009e8db  jz      short loc_18009E934
0x18009e8dd  mov     ppenum, [rsp+310h+pVerbList]; pVerbs
0x18009e8e2  xor     r8d, r8d; iVerb
0x18009e8e5  mov     clsid, rax; this
0x18009e8e8  call    ??0CEnumVerb@@AEAA@PEAUVerbList@@J@Z; CEnumVerb::CEnumVerb(VerbList *,long)
0x18009e8ed  mov     rbx, rax
0x18009e8f0  test    rax, rax
0x18009e8f3  jz      short loc_18009E934
0x18009e8f5  mov     [r14], rax
0x18009e8f8  mov     clsid, rbx
0x18009e8fb  mov     rax, [rax]
0x18009e8fe  mov     rax, [rax+8]
0x18009e902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e907  xchg    rbx, cs:?g_EnumCache@@3UEnumVerbCache@@A.pEnum; EnumVerbCache g_EnumCache ...
0x18009e90e  test    rbx, rbx
0x18009e911  jz      short $errRtn_134
0x18009e913  mov     rax, [rbx]
0x18009e916  mov     clsid, rbx
0x18009e919  mov     rax, [rax+10h]
0x18009e91d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e922  mov     rax, [r14]
0x18009e925  neg     rax
0x18009e928  sbb     ebx, ebx
0x18009e92a  not     ebx
0x18009e92c  and     ebx, 8007000Eh
0x18009e932  jmp     short $errSafeRtn_0
0x18009e934  mov     r8, [rsp+310h+pVerbList]; lpMem
0x18009e939  xor     edx, edx; dwFlags
0x18009e93b  mov     clsid, cs:?g_hHeap@@3QEAXEA; hHeap
0x18009e942  call    cs:__imp_HeapFree
0x18009e949  nop     dword ptr [rax+rax+00h]
0x18009e94e  mov     ebx, 8007000Eh
0x18009e953  lea     clsid, [rsp+310h+verbIterator]; this
0x18009e958  call    ??1?$com_ptr_t@UICallFrameEvents@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>(void)
0x18009e95d  lea     clsid, [rsp+310h+oleClassInfo]; this
0x18009e962  call    ??1?$com_ptr_t@UICallFrameEvents@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>(void)
0x18009e967  mov     eax, ebx
0x18009e969  mov     clsid, [rbp+210h+var_40]
0x18009e970  xor     clsid, rsp; StackCookie
0x18009e973  call    __security_check_cookie
0x18009e978  mov     rbx, [rsp+310h+arg_10]
0x18009e980  add     rsp, 2E0h
0x18009e987  pop     r15
0x18009e989  pop     r14
0x18009e98b  pop     r13
0x18009e98d  pop     r12
  ... truncated ...
```
