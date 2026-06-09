# CDocument::HostProcessUrlAction(ulong,uchar *,ulong,uchar *,ulong,ulong,ulong)

- ea: `0x18088fee0`
- end: `0x1808907f8`
- name: `?HostProcessUrlAction@CDocument@@QEAAJKPEAEK0KKK@Z`
- size: `2328`
- prototype: `__int64 __fastcall(CDocument *__hidden this, unsigned int, unsigned __int8 *, unsigned int, GUID *rguid, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `34`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18088fee0`

## callees

- `0x18000700c`
- `0x1800148b0`
- `0x1800cafdc`
- `0x1800e45d8`
- `0x1800e4964`
- `0x1800f5454`
- `0x180135278`
- `0x18021f9bc`
- `0x180223a8c`
- `0x1802fd8ec`
- `0x18034a080`
- `0x1803a8834`
- `0x18043c328`
- `0x180492440`
- `0x1804e223c`
- `0x1806f45d8`
- `0x180771400`
- `0x1807d6afc`
- `0x18084af10`
- `0x18084da10`
- `0x18086f73c`
- `0x18088fee0`
- `0x1808908a4`
- `0x1808f022c`
- `0x180e35340`
- `0x180e3579c`
- `0x180e35af8`
- `0x180e35be4`
- `0x18105c03c`
- `0x181065a94`
- `0x18109475c`
- `0x1810c2cb6`
- `0x1810c2d60`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1808900f1`
- `KERNEL32!GetLastError` at `0x1808900f9`
- `KERNEL32!GetLastError` at `0x1808900f1`
- `KERNEL32!GetLastError` at `0x1808900f9`
- `iertutil!__imp_?IECompatLogLMZL1@@YAXPEBGK@Z` at `0x18089073f`
- `iertutil!__imp_?IECompatLogLMZL1@@YAXPEBGK@Z` at `0x18089073f`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x180890380`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x180890380`
- `iertutil!__imp_?EDL_GetDomainFromUri@@YAJPEAUIUri@@PEAPEAG@Z` at `0x180890301`
- `iertutil!__imp_?EDL_GetDomainFromUri@@YAJPEAUIUri@@PEAPEAG@Z` at `0x180890301`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18089047d`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18089047d`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromGUID2` at `0x1808901ee`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromGUID2` at `0x1808901ee`
- `urlmon!__imp_CoInternetIsExtensionsOff` at `0x1808905ab`
- `urlmon!__imp_CoInternetIsExtensionsOff` at `0x1808905ab`
- `urlmon!__imp_CoInternetExtensionCollectStats` at `0x1808903fe`
- `urlmon!__imp_CoInternetExtensionCollectStats` at `0x1808903fe`
- `urlmon!__imp_?IECompatLogUIPIBlockedExtension@@YAXKAEBU_GUID@@PEBG@Z` at `0x1808903e8`
- `urlmon!__imp_?IECompatLogUIPIBlockedExtension@@YAXKAEBU_GUID@@PEBG@Z` at `0x1808903e8`
- `urlmon!__imp_CoInternetExtensionAllowedForUri` at `0x1808900e5`
- `urlmon!__imp_CoInternetExtensionAllowedForUri` at `0x1808900e5`
- `urlmon!__imp_GetVersionManager` at `0x1808901d3`
- `urlmon!__imp_GetVersionManager` at `0x1808901d3`
- `OLEAUT32!__imp_SysFreeString` at `0x18088ffdb`
- `OLEAUT32!__imp_SysFreeString` at `0x18088ffeb`
- `OLEAUT32!__imp_SysFreeString` at `0x18088ffff`
- `OLEAUT32!__imp_SysFreeString` at `0x180890505`
- `OLEAUT32!__imp_SysFreeString` at `0x180890513`
- `OLEAUT32!__imp_SysFreeString` at `0x1808905cb`
- `OLEAUT32!__imp_SysFreeString` at `0x1808905db`
- `OLEAUT32!__imp_SysFreeString` at `0x180890610`
- `OLEAUT32!__imp_SysFreeString` at `0x180890620`
- `OLEAUT32!__imp_SysFreeString` at `0x18088ffdb`
- `OLEAUT32!__imp_SysFreeString` at `0x18088ffeb`
- `OLEAUT32!__imp_SysFreeString` at `0x18088ffff`
- `OLEAUT32!__imp_SysFreeString` at `0x180890505`
- `OLEAUT32!__imp_SysFreeString` at `0x180890513`
- `OLEAUT32!__imp_SysFreeString` at `0x1808905cb`
- `OLEAUT32!__imp_SysFreeString` at `0x1808905db`
- `OLEAUT32!__imp_SysFreeString` at `0x180890610`
- `OLEAUT32!__imp_SysFreeString` at `0x180890620`

## pseudocode

```c
__int64 __fastcall CDocument::HostProcessUrlAction(
        CDocument *this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int a4,
        GUID *rguid,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8)
{
  unsigned __int8 *v8; // r13
  unsigned int v9; // edi
  unsigned int v10; // r12d
  CDocument *v11; // rbx
  __int64 v12; // r15
  struct CMarkup *v13; // rsi
  __int64 v14; // r8
  __int64 v15; // rax
  int v16; // r13d
  OLECHAR *v17; // rcx
  int v18; // edi
  unsigned int v19; // r14d
  void *v20; // rbx
  struct INSTANTCLASSINFO *InstantClassInfo; // rax
  __int64 v22; // rdx
  struct IUri *v23; // rax
  int v24; // edi
  DWORD LastError; // ebx
  __int64 v26; // r8
  struct CMarkup *v27; // rax
  CDoc *v28; // rcx
  struct IUri *v29; // rax
  int (__fastcall *v30)(_QWORD, OLECHAR *, _QWORD, _QWORD); // rbx
  __int64 v31; // rdx
  int v32; // r12d
  struct IUri *v33; // rax
  int v34; // eax
  unsigned int v35; // r12d
  bool IsPendingRoot; // al
  __int64 v37; // rdx
  int v38; // r9d
  int v39; // r8d
  struct IHTMLDocument2 *v40; // r9
  unsigned int v41; // r8d
  OLECHAR *v42; // rdi
  OLECHAR *v43; // rbx
  struct _GUID v44; // xmm0
  __int64 v45; // rcx
  __int64 v46; // rax
  struct BLOCKED_ACTION_DETAILS *v47; // r9
  OLECHAR *v48; // rcx
  int v49; // eax
  __int64 v50; // rax
  __int64 v51; // rcx
  __int64 v52; // rax
  CMarkup *v53; // rcx
  unsigned int v54; // edi
  const unsigned __int16 *Url; // rax
  int v56; // r12d
  ULONG (__stdcall *AddRef)(IUnknown *); // rbx
  const unsigned __int16 *v58; // rax
  GUID *v60; // [rsp+20h] [rbp-E0h]
  BSTR *v61; // [rsp+30h] [rbp-D0h]
  BSTR *p_bstrString; // [rsp+38h] [rbp-C8h]
  int *p_Size_4; // [rsp+40h] [rbp-C0h]
  unsigned int Size; // [rsp+60h] [rbp-A0h]
  int Size_4; // [rsp+64h] [rbp-9Ch] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v67; // [rsp+70h] [rbp-90h]
  int v68; // [rsp+74h] [rbp-8Ch] BYREF
  BSTR v69; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v70[2]; // [rsp+80h] [rbp-80h] BYREF
  int v71; // [rsp+88h] [rbp-78h] BYREF
  BOOL v72; // [rsp+8Ch] [rbp-74h]
  void *v73; // [rsp+90h] [rbp-70h] BYREF
  int v74; // [rsp+98h] [rbp-68h]
  BSTR v75; // [rsp+A0h] [rbp-60h] BYREF
  struct IUnknown *v76; // [rsp+A8h] [rbp-58h] BYREF
  CDocument *v77; // [rsp+B0h] [rbp-50h]
  OLECHAR sz[8]; // [rsp+C0h] [rbp-40h] BYREF
  struct _GUID v79; // [rsp+D0h] [rbp-30h]
  BSTR v80; // [rsp+F8h] [rbp-8h]
  int v81; // [rsp+100h] [rbp+0h]
  int v82; // [rsp+104h] [rbp+4h]
  BSTR v83; // [rsp+108h] [rbp+8h]
  BSTR v84; // [rsp+110h] [rbp+10h]
  _QWORD v85[2]; // [rsp+120h] [rbp+20h] BYREF
  GUID *v86; // [rsp+130h] [rbp+30h]
  __int128 v87; // [rsp+138h] [rbp+38h]
  int v88; // [rsp+148h] [rbp+48h]

  v8 = a3;
  v9 = a4;
  v10 = a2;
  Size = a4;
  v11 = this;
  v73 = a3;
  v12 = 0;
  v67 = a2;
  v77 = this;
  v75 = 0;
  v13 = CDocument::Markup(this);
  v76 = 0;
  v74 = 0;
  if ( v14 )
  {
    memset_0(v8, 0, v9);
    *v8 = 3;
  }
  if ( !v13 )
    goto LABEL_124;
  v15 = *((_QWORD *)v13 + 40);
  if ( v15 )
    v12 = *(_QWORD *)(v15 + 16);
  if ( !v12 )
  {
LABEL_124:
    v19 = Size;
    v18 = -2147024891;
    goto LABEL_17;
  }
  if ( v10 == 4608 )
  {
    v16 = 0;
    v69 = 0;
    bstrString = 0;
    Size_4 = 0;
    if ( !rguid || a6 < 0x10 )
    {
      v18 = -2147467261;
      v17 = 0;
      goto LABEL_12;
    }
    if ( (unsigned int)CClassTable::AssignClsidID((CClassTable *)(v12 + 5424), (struct CDoc *)v12, rguid, &Size_4) )
    {
LABEL_11:
      v17 = bstrString;
      v18 = -2147024891;
LABEL_12:
      SysFreeString(v17);
      bstrString = 0;
      SysFreeString(v69);
      goto LABEL_13;
    }
    InstantClassInfo = CClassTable::GetInstantClassInfo((CClassTable *)(v12 + 5424), Size_4);
    if ( InstantClassInfo && (*((_DWORD *)InstantClassInfo + 1) & 0x400) != 0 )
    {
      if ( g_cmptlgs != 1 && (unsigned int)IECompatLoggingEnabled() )
        LogControlBlock(7, v22, rguid, v13);
      goto LABEL_11;
    }
    v72 = 0;
    v23 = CMarkup::Uri(v13);
    v24 = CoInternetExtensionAllowedForUri(rguid, 1, v23);
    if ( v24 )
    {
      v24 = IsSafeToInstantiate(v13, rguid);
      if ( !v24 )
        goto LABEL_130;
      v27 = CMarkup::IsPendingRoot(v13) ? CDoc::PendingPrimaryMarkup((CDoc *)v12) : CDoc::PrimaryMarkup((CDoc *)v12);
      if ( !CDoc::IsPageActionAllowed(v28, v27, 0x40u) )
      {
        v85[1] = 0;
        LODWORD(v86) = 11;
        v85[0] = &CUString::`vftable';
        v87 = 0;
        v88 = 0;
        v29 = CMarkup::Uri(v13);
        if ( v29 )
          CUString::Set((CUString *)v85, v29, Uri_PROPERTY_ABSOLUTE_URI);
        *(_QWORD *)v70 = 0;
        if ( (int)GetVersionManager(v70) >= 0 )
        {
          if ( StringFromGUID2(rguid, sz, 39) )
          {
            Size_4 = 1;
            v30 = *(int (__fastcall **)(_QWORD, OLECHAR *, _QWORD, _QWORD))(**(_QWORD **)v70 + 24LL);
            p_Size_4 = &Size_4;
            p_bstrString = &bstrString;
            v61 = &v69;
            LODWORD(v60) = IsOs_Wow6432();
            if ( v30(*(_QWORD *)v70, sz, 0, *((_QWORD *)&v87 + 1)) >= 0 )
            {
              v24 = Size_4;
              v72 = Size_4 == 0;
            }
          }
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v70 + 16LL))(*(_QWORD *)v70);
          *(_QWORD *)v70 = 0;
        }
        v85[0] = &CUString::`vftable';
        CUString::Set((CUString *)v85, 0, Uri_PROPERTY_RAW_URI);
        if ( !v24 )
        {
LABEL_130:
          if ( g_cmptlgs != 1 && (unsigned int)IECompatLoggingEnabled() )
            LogControlBlock(8, v31, rguid, v13);
        }
      }
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( GetLastError() == 7 && (Microsoft_IEEnableBits & 8) != 0 )
      {
        v86 = rguid;
        *(_QWORD *)&v87 = 16;
        McGenEventWrite_EventWriteTransfer(
          &BERP_IE_Context,
          &MSHTML_URLACTION_ACTIVEX_IMMERSIVE_INCOMPATIBLE,
          v26,
          2,
          v85);
      }
    }
    Size_4 = 1;
    v32 = 0;
    v68 = 0;
    v70[0] = 0;
    v71 = 0;
    if ( (v24 || LastError == 8) && !v72 )
    {
      v33 = CMarkup::Uri(v13);
      if ( v33 )
        EDL_GetDomainFromUri(v33, &v75);
      v34 = IsPendingApproval(rguid, v13, v75, (enum TYPE_APPROVAL_NEEDED *)&v71, (enum FLAG_CONTENTFILTERSTATE *)&v68);
      v35 = v68;
      v16 = v34;
      if ( v68 )
      {
        IsPendingRoot = CMarkup::IsPendingRoot(v13);
        CDoc::SetActiveXFilterUI(v12, v35, IsPendingRoot);
      }
      if ( v16 && g_cmptlgs != 1 && (unsigned int)IECompatLoggingEnabled() )
        LogControlBlock(16, v37, rguid, v13);
      v32 = v71;
      if ( v24 )
        v24 = v16 == 0;
    }
    v68 = IsProtectedModeProcess();
    if ( !v68 && v24 )
    {
      if ( (unsigned int)Ext_IsIEExtCompatible(rguid, v70, 0, v38) == 1 )
      {
        v24 = 0;
        Size_4 = 0;
        if ( g_cmptlgs != 1
          && (unsigned int)IECompatLoggingEnabled()
          && g_cmptlgs != 1
          && (unsigned int)IECompatLoggingEnabled() )
        {
          IECompatLogUIPIBlockedExtension(1u, rguid, 0);
        }
      }
      else
      {
        Size_4 = 1;
        v24 = 1;
      }
    }
    CoInternetExtensionCollectStats(rguid, v24 != 0, 1);
    if ( *(char *)(v12 + 4868) >= 0
      || CDXDependentSurfacePresenterFlip::IsIndependent((CDXDependentSurfacePresenterFlip *)*(unsigned int *)(v12 + 5040)) )
    {
      IEFrameHelper::NotifyExtensionCreation(
        (IEFrameHelper *)rguid,
        v24 == 0 ? (const struct _GUID *)0x80004005LL : 0,
        v39);
    }
    if ( !v24 )
    {
      if ( v32 == 3 )
        goto LABEL_99;
      if ( LastError == 8 )
      {
        memset_0(sz, 0, 0x58u);
        v79 = *rguid;
        if ( !(unsigned __int8)IEConfiguration_GetBool(268435477) )
        {
          v41 = 0x1000000;
LABEL_95:
          v47 = (struct BLOCKED_ACTION_DETAILS *)sz;
LABEL_96:
          NotifyHaveProtectedUserFromUnsafeContent(v13, 0, v41, v47);
        }
LABEL_99:
        v48 = bstrString;
        v18 = -2147024891;
LABEL_100:
        SysFreeString(v48);
        bstrString = 0;
        SysFreeString(v69);
        v10 = v67;
        goto LABEL_13;
      }
      if ( v72 )
      {
        if ( !v74 )
        {
          v42 = v69;
          if ( v69 )
          {
            v43 = bstrString;
            if ( bstrString )
            {
              memset_0(sz, 0, 0x58u);
              v44 = *rguid;
              v83 = v42;
              v69 = 0;
              bstrString = 0;
              v84 = v43;
              v82 = 64;
              v79 = v44;
              NotifyHaveProtectedUserFromUnsafeContent(v13, 0, 0x40000000u, (struct BLOCKED_ACTION_DETAILS *)sz);
              SysFreeString(v83);
              v83 = 0;
              SysFreeString(v84);
              goto LABEL_99;
            }
          }
        }
      }
      if ( v16 )
      {
        v45 = *((_QWORD *)v13 + 40);
        v46 = 0;
        if ( v45 )
          v46 = *(_QWORD *)(v45 + 16);
        if ( (*(_DWORD *)(v46 + 4896) & 0x40000) != 0 )
          goto LABEL_99;
        memset_0(sz, 0, 0x58u);
        v41 = 0x40000;
        v80 = v75;
        v81 = v32;
      }
      else
      {
        if ( v68 || Size_4 )
        {
          if ( (unsigned int)CoInternetIsExtensionsOff() )
            goto LABEL_99;
          v47 = 0;
          v41 = 8;
          goto LABEL_96;
        }
        if ( (v70[0] & 2) == 0 )
          goto LABEL_99;
        memset_0(sz, 0, 0x58u);
        v41 = 0x10000000;
      }
      v79 = *rguid;
      goto LABEL_95;
    }
    v49 = CMarkup::OnExtensionLoading(v13, rguid, ExtensionValidationContextDynamic, v40, (struct CMarkup *)v60, 0);
    v48 = bstrString;
    v18 = v49;
    if ( v49 == -2147024891 )
      goto LABEL_100;
    SysFreeString(bstrString);
    bstrString = 0;
    SysFreeString(v69);
    v8 = (unsigned __int8 *)v73;
    v11 = v77;
    v10 = v67;
    v9 = Size;
  }
  v50 = *((_QWORD *)v11 + 7);
  if ( v50 && *(_QWORD *)(v50 + 344) && (v51 = *(_QWORD *)(v50 + 136)) != 0 )
  {
    v18 = CDocument::HostProcessUrlAction(*(CDocument **)(v51 + 120), v10, v8, v9, rguid, a6, a7, a8);
  }
  else
  {
    v18 = CDoc::EnsureSecurityManager((CDoc *)v12, (struct IInternetSecurityManagerEx2 **)&v76, 0);
    if ( v18 >= 0 )
    {
      v52 = *((_QWORD *)v11 + 7);
      if ( v52 && (*(_BYTE *)(v52 + 224) & 0x40) != 0
        || (v53 = (CMarkup *)*((_QWORD *)v13 + 18)) != 0
        && (*((_DWORD *)v53 + 187) & 0x4000000) != 0
        && (*(_BYTE *)(*((_QWORD *)CMarkup::Window(v53) + 15) + 224LL) & 0x40) != 0 )
      {
        v54 = a7 | 0x100;
      }
      else
      {
        v54 = a7;
        if ( (*((_DWORD *)v13 + 187) & 0x2000000) != 0 )
          v54 = a7 | 0x40;
      }
      if ( (*(_BYTE *)(v12 + 4872) & 2) != 0 )
      {
        if ( g_cmptlgs != 1 && (unsigned int)IECompatLoggingEnabled() )
        {
          Url = CMarkup::GetUrl(v13);
          IECompatLogLMZL1(Url, v10);
        }
        v56 = 0x10000;
      }
      else
      {
        v56 = 0x20000;
      }
      AddRef = v76->lpVtbl[2].AddRef;
      v58 = CMarkup::GetUrl(v13);
      LODWORD(p_Size_4) = a8;
      LODWORD(p_bstrString) = v54 | v56;
      v10 = v67;
      LODWORD(v61) = a6;
      v19 = Size;
      v18 = ((__int64 (__fastcall *)(struct IUnknown *, const unsigned __int16 *, _QWORD, unsigned __int8 *, unsigned int, GUID *, BSTR *, BSTR *, int *))AddRef)(
              v76,
              v58,
              v67,
              v8,
              Size,
              rguid,
              v61,
              p_bstrString,
              p_Size_4);
      goto LABEL_14;
    }
  }
LABEL_13:
  v19 = Size;
LABEL_14:
  if ( v75 )
    SysFreeString(v75);
  v8 = (unsigned __int8 *)v73;
LABEL_17:
  ReleaseInterface(v76);
  if ( v18 >= 0 && v10 == 4608 && CDoc::IsPrerendered((CDoc *)v12) )
  {
    CPreloadManagerLock::CPreloadManagerLock((CPreloadManagerLock *)&v73, v13);
    v20 = v73;
    if ( v73 )
    {
      if ( CDoc::IsReadingModePrerendered((CDoc *)v12) )
      {
        if ( v8 )
        {
          memset_0(v8, 0, v19);
          *v8 = 3;
        }
      }
      else
      {
        v18 = CPreloadManager::SuspendDuringPrerender(v20, 0);
      }
    }
    TSmartPointer<CPreloadManager>::~TSmartPointer<CPreloadManager>(&v73);
  }
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18088fee0  push    rbp
0x18088fee2  push    rbx
0x18088fee3  push    rsi
0x18088fee4  push    rdi
0x18088fee5  push    r12
0x18088fee7  push    r13
0x18088fee9  push    r14
0x18088feeb  push    r15
0x18088feed  lea     rbp, [rsp-68h]
0x18088fef2  sub     rsp, 168h
0x18088fef9  mov     rax, cs:__security_cookie
0x18088ff00  xor     rax, rsp
0x18088ff03  mov     [rbp+0A0h+var_50], rax
0x18088ff07  mov     r14, [rbp+0A0h+rguid]
0x18088ff0e  mov     r13, r8
0x18088ff11  mov     edi, r9d
0x18088ff14  mov     r12d, edx
0x18088ff17  mov     dword ptr [rsp+1A0h+Size], edi
0x18088ff1b  mov     rbx, rcx
0x18088ff1e  mov     [rbp+0A0h+var_110], r8
0x18088ff22  xor     r15d, r15d
0x18088ff25  mov     [rsp+1A0h+var_130], edx
0x18088ff29  mov     [rbp+0A0h+var_F0], rcx
0x18088ff2d  call    ?Markup@CDocument@@QEBAPEAVCMarkup@@XZ; CDocument::Markup(void)
0x18088ff32  mov     [rbp+0A0h+var_100], r15
0x18088ff36  mov     rsi, rax
0x18088ff39  mov     [rbp+0A0h+var_F8], r15
0x18088ff3d  mov     [rbp+0A0h+var_108], r15d
0x18088ff41  test    r8, r8
0x18088ff44  jz      short loc_18088FF58
0x18088ff46  mov     r8d, edi; Size
0x18088ff49  xor     edx, edx; Val
0x18088ff4b  mov     rcx, r13; void *
0x18088ff4e  call    memset_0
0x18088ff53  mov     byte ptr [r13+0], 3
0x18088ff58  test    rsi, rsi
0x18088ff5b  jz      loc_1808907B2
0x18088ff61  mov     rax, [rsi+140h]
0x18088ff68  test    rax, rax
0x18088ff6b  jz      short loc_18088FF71
0x18088ff6d  mov     r15, [rax+10h]
0x18088ff71  test    r15, r15
0x18088ff74  jz      loc_1808907B2
0x18088ff7a  cmp     r12d, 1200h
0x18088ff81  jnz     loc_180890637
0x18088ff87  xor     r13d, r13d
0x18088ff8a  mov     [rsp+1A0h+var_128], r13
0x18088ff8f  mov     [rsp+1A0h+bstrString], r13
0x18088ff94  mov     dword ptr [rsp+1A0h+Size+4], r13d
0x18088ff99  test    r14, r14
0x18088ff9c  jz      loc_180890692
0x18088ffa2  cmp     [rbp+0A0h+arg_28], 10h
0x18088ffa9  jb      loc_180890692
0x18088ffaf  lea     rbx, [r15+1530h]
0x18088ffb6  mov     r8, r14; struct _GUID *
0x18088ffb9  mov     rcx, rbx; this
0x18088ffbc  lea     r9, [rsp+1A0h+Size+4]; int *
0x18088ffc1  mov     rdx, r15; struct CDoc *
0x18088ffc4  call    ?AssignClsidID@CClassTable@@QEAAJPEAVCDoc@@AEBU_GUID@@PEAJ@Z; CClassTable::AssignClsidID(CDoc *,_GUID const &,long *)
0x18088ffc9  test    eax, eax
0x18088ffcb  jz      loc_180890080
0x18088ffd1  mov     rcx, [rsp+1A0h+bstrString]; bstrString
0x18088ffd6  mov     edi, 80070005h
0x18088ffdb  call    cs:__imp_SysFreeString
0x18088ffe1  mov     rcx, [rsp+1A0h+var_128]; bstrString
0x18088ffe6  mov     [rsp+1A0h+bstrString], r13
0x18088ffeb  call    cs:__imp_SysFreeString
0x18088fff1  mov     r14d, dword ptr [rsp+1A0h+Size]
0x18088fff6  mov     rcx, [rbp+0A0h+var_100]; bstrString
0x18088fffa  test    rcx, rcx
0x18088fffd  jz      short loc_180890005
0x18088ffff  call    cs:__imp_SysFreeString
0x180890005  mov     r13, [rbp+0A0h+var_110]
0x180890009  mov     rcx, [rbp+0A0h+var_F8]; struct IUnknown *
0x18089000d  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x180890012  test    edi, edi
0x180890014  js      loc_1808907D6
0x18089001a  cmp     r12d, 1200h
0x180890021  jnz     loc_1808907D6
0x180890027  mov     rcx, r15; this
0x18089002a  call    ?IsPrerendered@CDoc@@QEBA_NXZ; CDoc::IsPrerendered(void)
0x18089002f  test    al, al
0x180890031  jz      loc_1808907D6
0x180890037  mov     rdx, rsi; struct CMarkup *
0x18089003a  lea     rcx, [rbp+0A0h+var_110]; this
0x18089003e  call    ??0CPreloadManagerLock@@QEAA@PEAVCMarkup@@@Z; CPreloadManagerLock::CPreloadManagerLock(CMarkup *)
0x180890043  mov     rbx, [rbp+0A0h+var_110]
0x180890047  test    rbx, rbx
0x18089004a  jz      loc_1808907CD
0x180890050  mov     rcx, r15; this
0x180890053  call    ?IsReadingModePrerendered@CDoc@@QEBA_NXZ; CDoc::IsReadingModePrerendered(void)
0x180890058  test    al, al
0x18089005a  jz      loc_1808907C1
0x180890060  test    r13, r13
0x180890063  jz      loc_1808907CD
0x180890069  mov     r8d, r14d; Size
0x18089006c  xor     edx, edx; Val
0x18089006e  mov     rcx, r13; void *
0x180890071  call    memset_0
0x180890076  mov     byte ptr [r13+0], 3
0x18089007b  jmp     loc_1808907CD
0x180890080  mov     edx, dword ptr [rsp+1A0h+Size+4]; int
0x180890084  mov     rcx, rbx; this
0x180890087  call    ?GetInstantClassInfo@CClassTable@@QEAAPEAUINSTANTCLASSINFO@@J@Z; CClassTable::GetInstantClassInfo(long)
0x18089008c  test    rax, rax
0x18089008f  jz      short loc_1808900C9
0x180890091  test    dword ptr [rax+4], 400h
0x180890098  jz      short loc_1808900C9
0x18089009a  cmp     cs:?g_cmptlgs@@3W4CMPTLGS@@A, 1; CMPTLGS g_cmptlgs
0x1808900a1  jz      loc_18088FFD1
0x1808900a7  call    ?IECompatLoggingEnabled@@YAHXZ; IECompatLoggingEnabled(void)
0x1808900ac  test    eax, eax
0x1808900ae  jz      loc_18088FFD1
0x1808900b4  mov     r9, rsi
0x1808900b7  mov     r8, r14
0x1808900ba  mov     ecx, 7
0x1808900bf  call    ?LogControlBlock@@YAXW4CtrlLoggingEvent@ControlLogging@@_NAEBU_GUID@@PEAVCMarkup@@@Z; LogControlBlock(ControlLogging::CtrlLoggingEvent,bool,_GUID const &,CMarkup *)
0x1808900c4  jmp     loc_18088FFD1
0x1808900c9  mov     rcx, rsi; this
0x1808900cc  mov     [rbp+0A0h+var_114], r13d
0x1808900d0  call    ?Uri@CMarkup@@QEAAPEAUIUri@@XZ; CMarkup::Uri(void)
0x1808900d5  xor     r9d, r9d
0x1808900d8  mov     r8, rax
0x1808900db  mov     rcx, r14
0x1808900de  lea     r12d, [r9+1]
0x1808900e2  mov     edx, r12d
0x1808900e5  call    cs:__imp_CoInternetExtensionAllowedForUri
0x1808900eb  mov     edi, eax
0x1808900ed  test    eax, eax
0x1808900ef  jnz     short loc_180890147
0x1808900f1  call    cs:__imp_GetLastError
0x1808900f7  mov     ebx, eax
0x1808900f9  call    cs:__imp_GetLastError
0x1808900ff  cmp     eax, 7
0x180890102  jnz     loc_1808902C1
0x180890108  test    byte ptr cs:Microsoft_IEEnableBits, 8
0x18089010f  jz      loc_1808902C1
0x180890115  lea     rax, [rbp+0A0h+var_80]
0x180890119  mov     [rbp+0A0h+var_70], r14
0x18089011d  lea     r9d, [r12+1]
0x180890122  mov     [rsp+1A0h+var_180], rax
0x180890127  lea     rdx, MSHTML_URLACTION_ACTIVEX_IMMERSIVE_INCOMPATIBLE
0x18089012e  mov     qword ptr [rbp+0A0h+var_68], 10h
0x180890136  lea     rcx, BERP_IE_Context
0x18089013d  call    McGenEventWrite_EventWriteTransfer
0x180890142  jmp     loc_1808902C1
0x180890147  mov     rdx, r14; struct _GUID *
0x18089014a  mov     rcx, rsi; struct CMarkup *
0x18089014d  call    ?IsSafeToInstantiate@@YAHPEAVCMarkup@@AEBU_GUID@@@Z; IsSafeToInstantiate(CMarkup *,_GUID const &)
0x180890152  mov     edi, eax
0x180890154  test    eax, eax
0x180890156  jz      loc_18089029C
0x18089015c  mov     rcx, rsi; this
0x18089015f  call    ?IsPendingRoot@CMarkup@@QEAA_NXZ; CMarkup::IsPendingRoot(void)
0x180890164  mov     rcx, r15; this
0x180890167  test    al, al
0x180890169  jz      short loc_180890172
0x18089016b  call    ?PendingPrimaryMarkup@CDoc@@QEBAPEAVCMarkup@@XZ; CDoc::PendingPrimaryMarkup(void)
0x180890170  jmp     short loc_180890177
0x180890172  call    ?PrimaryMarkup@CDoc@@QEBAPEAVCMarkup@@XZ; CDoc::PrimaryMarkup(void)
0x180890177  mov     r8d, 40h ; '@'; unsigned int
0x18089017d  mov     rdx, rax; struct CMarkup *
0x180890180  call    ?IsPageActionAllowed@CDoc@@QEAAHPEAVCMarkup@@K@Z; CDoc::IsPageActionAllowed(CMarkup *,ulong)
0x180890185  test    eax, eax
0x180890187  jnz     loc_1808902BE
0x18089018d  xorps   xmm0, xmm0
0x180890190  mov     [rbp+0A0h+var_78], r13
0x180890194  lea     rbx, ??_7CUString@@6B@; const CUString::`vftable'
0x18089019b  mov     dword ptr [rbp+0A0h+var_70], 0Bh
0x1808901a2  mov     rcx, rsi; this
0x1808901a5  mov     [rbp+0A0h+var_80], rbx
0x1808901a9  movdqu  [rbp+0A0h+var_68], xmm0
0x1808901ae  mov     [rbp+0A0h+var_58], r13d
0x1808901b2  call    ?Uri@CMarkup@@QEAAPEAUIUri@@XZ; CMarkup::Uri(void)
0x1808901b7  test    rax, rax
0x1808901ba  jz      short loc_1808901CB
0x1808901bc  xor     r8d, r8d; enum __MIDL_IUri_0001
0x1808901bf  lea     rcx, [rbp+0A0h+var_80]; this
0x1808901c3  mov     rdx, rax; struct IUri *
0x1808901c6  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x1808901cb  lea     rcx, [rbp+0A0h+var_120]
0x1808901cf  mov     qword ptr [rbp+0A0h+var_120], r13
0x1808901d3  call    cs:__imp_GetVersionManager
0x1808901d9  test    eax, eax
0x1808901db  js      loc_180890285
0x1808901e1  mov     r8d, 27h ; '''; cchMax
0x1808901e7  lea     rdx, [rbp+0A0h+sz]; lpsz
0x1808901eb  mov     rcx, r14; rguid
0x1808901ee  call    cs:__imp_StringFromGUID2
0x1808901f4  test    eax, eax
0x1808901f6  jz      short loc_180890271
0x1808901f8  mov     rax, qword ptr [rbp+0A0h+var_120]
0x1808901fc  mov     dword ptr [rsp+1A0h+Size+4], r12d
0x180890201  mov     rcx, [rax]
0x180890204  mov     rbx, [rcx+18h]
0x180890208  call    ?IsOs_Wow6432@@YA_NXZ; IsOs_Wow6432(void)
0x18089020d  mov     r9, qword ptr [rbp+0A0h+var_68+8]
0x180890211  lea     rdx, [rbp+0A0h+sz]
0x180890215  movzx   ecx, al
0x180890218  xor     r8d, r8d
0x18089021b  lea     rax, [rbp+0A0h+var_108]
0x18089021f  mov     [rsp+1A0h+var_158], rax
0x180890224  lea     rax, [rsp+1A0h+Size+4]
0x180890229  mov     [rsp+1A0h+var_160], rax
0x18089022e  lea     rax, [rsp+1A0h+bstrString]
0x180890233  mov     qword ptr [rsp+1A0h+var_168], rax
0x180890238  lea     rax, [rsp+1A0h+var_128]
0x18089023d  mov     qword ptr [rsp+1A0h+var_170], rax
0x180890242  mov     rax, rbx
0x180890245  mov     dword ptr [rsp+1A0h+var_178], r13d
0x18089024a  mov     dword ptr [rsp+1A0h+var_180], ecx
0x18089024e  mov     rcx, qword ptr [rbp+0A0h+var_120]
0x180890252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180890257  test    eax, eax
0x180890259  js      short loc_18089026A
0x18089025b  mov     edi, dword ptr [rsp+1A0h+Size+4]
0x18089025f  mov     ebx, r13d
0x180890262  test    edi, edi
0x180890264  setz    bl
0x180890267  mov     [rbp+0A0h+var_114], ebx
0x18089026a  lea     rbx, ??_7CUString@@6B@; const CUString::`vftable'
0x180890271  mov     rcx, qword ptr [rbp+0A0h+var_120]
0x180890275  mov     rax, [rcx]
0x180890278  mov     rax, [rax+10h]
0x18089027c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180890281  mov     qword ptr [rbp+0A0h+var_120], r13
0x180890285  xor     edx, edx; struct IUri *
0x180890287  mov     [rbp+0A0h+var_80], rbx
0x18089028b  lea     rcx, [rbp+0A0h+var_80]; this
0x18089028f  lea     r8d, [rdx+0Bh]; enum __MIDL_IUri_0001
0x180890293  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x180890298  test    edi, edi
0x18089029a  jnz     short loc_1808902BE
0x18089029c  cmp     cs:?g_cmptlgs@@3W4CMPTLGS@@A, r12d; CMPTLGS g_cmptlgs
0x1808902a3  jz      short loc_1808902BE
0x1808902a5  call    ?IECompatLoggingEnabled@@YAHXZ; IECompatLoggingEnabled(void)
0x1808902aa  test    eax, eax
0x1808902ac  jz      short loc_1808902BE
0x1808902ae  mov     r9, rsi
0x1808902b1  mov     r8, r14
0x1808902b4  mov     ecx, 8
0x1808902b9  call    ?LogControlBlock@@YAXW4CtrlLoggingEvent@ControlLogging@@_NAEBU_GUID@@PEAVCMarkup@@@Z; LogControlBlock(ControlLogging::CtrlLoggingEvent,bool,_GUID const &,CMarkup *)
0x1808902be  mov     ebx, r13d
0x1808902c1  mov     dword ptr [rsp+1A0h+Size+4], r12d
0x1808902c6  xor     r12d, r12d
0x1808902c9  mov     [rsp+1A0h+var_12C], r13d
0x1808902ce  mov     [rbp+0A0h+var_120], r13d
0x1808902d2  mov     [rbp+0A0h+var_118], r12d
0x1808902d6  test    edi, edi
0x1808902d8  jnz     short loc_1808902E3
0x1808902da  cmp     ebx, 8
0x1808902dd  jnz     loc_180890380
0x1808902e3  cmp     [rbp+0A0h+var_114], r12d
0x1808902e7  jnz     loc_180890380
0x1808902ed  mov     rcx, rsi; this
0x1808902f0  call    ?Uri@CMarkup@@QEAAPEAUIUri@@XZ; CMarkup::Uri(void)
0x1808902f5  test    rax, rax
0x1808902f8  jz      short loc_180890307
0x1808902fa  lea     rdx, [rbp+0A0h+var_100]
0x1808902fe  mov     rcx, rax
0x180890301  call    cs:__imp_?EDL_GetDomainFromUri@@YAJPEAUIUri@@PEAPEAG@Z; EDL_GetDomainFromUri(IUri *,ushort * *)
0x180890307  mov     r8, [rbp+0A0h+var_100]; unsigned __int16 *
0x18089030b  lea     rax, [rsp+1A0h+var_12C]
0x180890310  lea     r9, [rbp+0A0h+var_118]; enum TYPE_APPROVAL_NEEDED *
0x180890314  mov     [rsp+1A0h+var_180], rax; struct CMarkup *
0x180890319  mov     rdx, rsi; struct CMarkup *
0x18089031c  mov     rcx, r14; struct _GUID *
0x18089031f  call    ?IsPendingApproval@@YAHAEBU_GUID@@PEAVCMarkup@@PEBGPEAW4TYPE_APPROVAL_NEEDED@@PEAW4FLAG_CONTENTFILTERSTATE@@@Z; IsPendingApproval(_GUID const &,CMarkup *,ushort const *,TYPE_APPROVAL_NEEDED *,FLAG_CONTENTFILTERSTATE *)
0x180890324  mov     r12d, [rsp+1A0h+var_12C]
0x180890329  mov     r13d, eax
0x18089032c  test    r12d, r12d
0x18089032f  jz      short loc_180890348
0x180890331  mov     rcx, rsi; this
0x180890334  call    ?IsPendingRoot@CMarkup@@QEAA_NXZ; CMarkup::IsPendingRoot(void)
0x180890339  movzx   r8d, al
0x18089033d  mov     edx, r12d
0x180890340  mov     rcx, r15
0x180890343  call    ?SetActiveXFilterUI@CDoc@@QEAAXW4FLAG_CONTENTFILTERSTATE@@H@Z; CDoc::SetActiveXFilterUI(FLAG_CONTENTFILTERSTATE,int)
0x180890348  test    r13d, r13d
0x18089034b  jz      short loc_18089036F
0x18089034d  cmp     cs:?g_cmptlgs@@3W4CMPTLGS@@A, 1; CMPTLGS g_cmptlgs
0x180890354  jz      short loc_18089036F
0x180890356  call    ?IECompatLoggingEnabled@@YAHXZ; IECompatLoggingEnabled(void)
0x18089035b  test    eax, eax
0x18089035d  jz      short loc_18089036F
0x18089035f  mov     r9, rsi
0x180890362  mov     r8, r14
0x180890365  mov     ecx, 10h
0x18089036a  call    ?LogControlBlock@@YAXW4CtrlLoggingEvent@ControlLogging@@_NAEBU_GUID@@PEAVCMarkup@@@Z; LogControlBlock(ControlLogging::CtrlLoggingEvent,bool,_GUID const &,CMarkup *)
0x18089036f  mov     r12d, [rbp+0A0h+var_118]
0x180890373  test    edi, edi
0x180890375  jz      short loc_180890380
0x180890377  xor     edi, edi
0x180890379  test    r13d, r13d
0x18089037c  setz    dil
0x180890380  call    cs:__imp_?IsProtectedModeProcess@@YAJXZ; IsProtectedModeProcess(void)
0x180890386  mov     [rsp+1A0h+var_12C], eax
0x18089038a  test    eax, eax
0x18089038c  jnz     short loc_1808903EE
0x18089038e  test    edi, edi
  ... truncated ...
```
