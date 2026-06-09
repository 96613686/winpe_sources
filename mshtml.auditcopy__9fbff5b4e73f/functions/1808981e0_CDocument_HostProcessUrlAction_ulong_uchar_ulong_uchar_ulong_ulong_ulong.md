# CDocument::HostProcessUrlAction(ulong,uchar *,ulong,uchar *,ulong,ulong,ulong)

- ea: `0x1808981e0`
- end: `0x180898b8a`
- name: `?HostProcessUrlAction@CDocument@@QEAAJKPEAEK0KKK@Z`
- size: `2474`
- prototype: `__int64 __fastcall(CDocument *__hidden this, unsigned int, unsigned __int8 *, unsigned int, GUID *rguid, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `35`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1808981e0`

## callees

- `0x180051c00`
- `0x1800ea428`
- `0x1800f9604`
- `0x1801086ac`
- `0x1801297b8`
- `0x180138ce4`
- `0x180139080`
- `0x180149610`
- `0x1802a08ec`
- `0x1803ddae0`
- `0x1803e1034`
- `0x1803e13d4`
- `0x1803e41f0`
- `0x1803e706c`
- `0x180411f40`
- `0x180571708`
- `0x180712534`
- `0x18077b900`
- `0x1807e2190`
- `0x18084e01c`
- `0x180850f20`
- `0x18087594c`
- `0x1808981e0`
- `0x180898c38`
- `0x1808fc784`
- `0x180e5a0c4`
- `0x180e5a53c`
- `0x180e5a8a8`
- `0x180e5aa04`
- `0x18108be78`
- `0x181096438`
- `0x1810c6cb0`
- `0x1810f6516`
- `0x1810f65c0`
- `0x181104010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180898404`
- `KERNEL32!GetLastError` at `0x180898412`
- `KERNEL32!GetLastError` at `0x180898404`
- `KERNEL32!GetLastError` at `0x180898412`
- `iertutil!__imp_?IECompatLogLMZL1@@YAXPEBGK@Z` at `0x180898aca`
- `iertutil!__imp_?IECompatLogLMZL1@@YAXPEBGK@Z` at `0x180898aca`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1808986b1`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1808986b1`
- `iertutil!__imp_?EDL_GetDomainFromUri@@YAJPEAUIUri@@PEAPEAG@Z` at `0x18089862c`
- `iertutil!__imp_?EDL_GetDomainFromUri@@YAJPEAUIUri@@PEAPEAG@Z` at `0x18089862c`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1808987c0`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1808987c0`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromGUID2` at `0x180898513`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromGUID2` at `0x180898513`
- `urlmon!__imp_CoInternetIsExtensionsOff` at `0x180898949`
- `urlmon!__imp_CoInternetIsExtensionsOff` at `0x180898949`
- `urlmon!__imp_CoInternetExtensionCollectStats` at `0x18089873b`
- `urlmon!__imp_CoInternetExtensionCollectStats` at `0x18089873b`
- `urlmon!__imp_?IECompatLogUIPIBlockedExtension@@YAXKAEBU_GUID@@PEBG@Z` at `0x18089871f`
- `urlmon!__imp_?IECompatLogUIPIBlockedExtension@@YAXKAEBU_GUID@@PEBG@Z` at `0x18089871f`
- `urlmon!__imp_CoInternetExtensionAllowedForUri` at `0x1808983f2`
- `urlmon!__imp_CoInternetExtensionAllowedForUri` at `0x1808983f2`
- `urlmon!__imp_GetVersionManager` at `0x1808984f2`
- `urlmon!__imp_GetVersionManager` at `0x1808984f2`
- `OLEAUT32!__imp_SysFreeString` at `0x1808982d6`
- `OLEAUT32!__imp_SysFreeString` at `0x1808982ec`
- `OLEAUT32!__imp_SysFreeString` at `0x180898306`
- `OLEAUT32!__imp_SysFreeString` at `0x180898856`
- `OLEAUT32!__imp_SysFreeString` at `0x18089886a`
- `OLEAUT32!__imp_SysFreeString` at `0x1808988d8`
- `OLEAUT32!__imp_SysFreeString` at `0x1808988ee`
- `OLEAUT32!__imp_SysFreeString` at `0x18089898f`
- `OLEAUT32!__imp_SysFreeString` at `0x1808989a5`
- `OLEAUT32!__imp_SysFreeString` at `0x1808982d6`
- `OLEAUT32!__imp_SysFreeString` at `0x1808982ec`
- `OLEAUT32!__imp_SysFreeString` at `0x180898306`
- `OLEAUT32!__imp_SysFreeString` at `0x180898856`
- `OLEAUT32!__imp_SysFreeString` at `0x18089886a`
- `OLEAUT32!__imp_SysFreeString` at `0x1808988d8`
- `OLEAUT32!__imp_SysFreeString` at `0x1808988ee`
- `OLEAUT32!__imp_SysFreeString` at `0x18089898f`
- `OLEAUT32!__imp_SysFreeString` at `0x1808989a5`

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
  struct CDoc *v15; // rax
  int v16; // r13d
  CClassTable *v17; // rbx
  OLECHAR *v18; // rcx
  int v19; // edi
  unsigned int v20; // r14d
  void *v21; // rbx
  struct INSTANTCLASSINFO *InstantClassInfo; // rax
  __int64 v23; // rdx
  struct IUri *v24; // rax
  int v25; // edi
  DWORD LastError; // ebx
  __int64 v27; // r8
  struct CMarkup **v28; // rax
  CDoc *v29; // rcx
  struct IUri *v30; // rax
  int (__fastcall *v31)(_QWORD, OLECHAR *, _QWORD, _QWORD); // rbx
  __int64 v32; // rdx
  int v33; // r12d
  struct IUri *v34; // rax
  int v35; // eax
  char v36; // r12
  bool IsPendingRoot; // al
  __int64 v38; // rdx
  int v39; // r9d
  int v40; // r8d
  struct IHTMLDocument2 *v41; // r9
  unsigned int v42; // r8d
  OLECHAR *v43; // rdi
  OLECHAR *v44; // rbx
  struct _GUID v45; // xmm0
  struct _GUID v46; // xmm0
  OLECHAR *v47; // rcx
  struct BLOCKED_ACTION_DETAILS *v48; // r9
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
  struct _EVENT_DATA_DESCRIPTOR v85; // [rsp+120h] [rbp+20h] BYREF
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
  if ( !v13 || (v15 = CMarkup::Doc(v13), (v12 = (__int64)v15) == 0) )
  {
    v20 = Size;
    v19 = -2147024891;
    goto LABEL_15;
  }
  if ( v10 == 4608 )
  {
    v16 = 0;
    v69 = 0;
    bstrString = 0;
    Size_4 = 0;
    if ( !rguid || a6 < 0x10 )
    {
      v19 = -2147467261;
      v18 = 0;
      goto LABEL_10;
    }
    v17 = (struct CDoc *)((char *)v15 + 5424);
    if ( (unsigned int)CClassTable::AssignClsidID((struct CDoc *)((char *)v15 + 5424), v15, rguid, &Size_4) )
    {
LABEL_9:
      v18 = bstrString;
      v19 = -2147024891;
LABEL_10:
      SysFreeString(v18);
      bstrString = 0;
      SysFreeString(v69);
      goto LABEL_11;
    }
    InstantClassInfo = CClassTable::GetInstantClassInfo(v17, Size_4);
    if ( InstantClassInfo && (*((_DWORD *)InstantClassInfo + 1) & 0x400) != 0 )
    {
      if ( g_cmptlgs != 1 && (unsigned int)IECompatLoggingEnabled() )
        LogControlBlock(7, v23, (__int64)rguid, v13);
      goto LABEL_9;
    }
    v72 = 0;
    v24 = CMarkup::Uri(v13);
    v25 = CoInternetExtensionAllowedForUri(rguid, 1, v24);
    if ( v25 )
    {
      v25 = IsSafeToInstantiate(v13, rguid);
      if ( !v25 )
        goto LABEL_125;
      v28 = (struct CMarkup **)(CMarkup::IsPendingRoot(v13)
                              ? CDoc::PendingPrimaryMarkup((CDoc *)v12)
                              : CDoc::PrimaryMarkup((CDoc *)v12));
      if ( !(unsigned int)CDoc::IsPageActionAllowed(v29, v28, 64) )
      {
        *(_QWORD *)&v85.Size = 0;
        LODWORD(v86) = 11;
        v85.Ptr = (ULONGLONG)&CUString::`vftable';
        v87 = 0;
        v88 = 0;
        v30 = CMarkup::Uri(v13);
        if ( v30 )
          CUString::Set((CUString *)&v85, v30, 0);
        *(_QWORD *)v70 = 0;
        if ( (int)GetVersionManager(v70) >= 0 )
        {
          if ( StringFromGUID2(rguid, sz, 39) )
          {
            Size_4 = 1;
            v31 = *(int (__fastcall **)(_QWORD, OLECHAR *, _QWORD, _QWORD))(**(_QWORD **)v70 + 24LL);
            p_Size_4 = &Size_4;
            p_bstrString = &bstrString;
            v61 = &v69;
            LODWORD(v60) = IsOs_Wow6432();
            if ( v31(*(_QWORD *)v70, sz, 0, *((_QWORD *)&v87 + 1)) >= 0 )
            {
              v25 = Size_4;
              v72 = Size_4 == 0;
            }
          }
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v70 + 16LL))(*(_QWORD *)v70);
          *(_QWORD *)v70 = 0;
        }
        v85.Ptr = (ULONGLONG)&CUString::`vftable';
        CUString::Set((CUString *)&v85, 0, 0xBu);
        if ( !v25 )
        {
LABEL_125:
          if ( g_cmptlgs != 1 && (unsigned int)IECompatLoggingEnabled() )
            LogControlBlock(8, v32, (__int64)rguid, v13);
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
          (REGHANDLE *)&BERP_IE_Context,
          (const EVENT_DESCRIPTOR *)MSHTML_URLACTION_ACTIVEX_IMMERSIVE_INCOMPATIBLE,
          v27,
          2u,
          &v85);
      }
    }
    Size_4 = 1;
    v33 = 0;
    v68 = 0;
    v70[0] = 0;
    v71 = 0;
    if ( (v25 || LastError == 8) && !v72 )
    {
      v34 = CMarkup::Uri(v13);
      if ( v34 )
        EDL_GetDomainFromUri(v34, &v75);
      v35 = IsPendingApproval(rguid, v13, v75, (enum TYPE_APPROVAL_NEEDED *)&v71, (enum FLAG_CONTENTFILTERSTATE *)&v68);
      v36 = v68;
      v16 = v35;
      if ( v68 )
      {
        IsPendingRoot = CMarkup::IsPendingRoot(v13);
        CDoc::SetActiveXFilterUI(v12, v36, IsPendingRoot);
      }
      if ( v16 && g_cmptlgs != 1 && (unsigned int)IECompatLoggingEnabled() )
        LogControlBlock(16, v38, (__int64)rguid, v13);
      v33 = v71;
      if ( v25 )
        v25 = v16 == 0;
    }
    v68 = IsProtectedModeProcess();
    if ( !v68 && v25 )
    {
      if ( (unsigned int)Ext_IsIEExtCompatible(rguid, v70, 0, v39) == 1 )
      {
        v25 = 0;
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
        v25 = 1;
      }
    }
    CoInternetExtensionCollectStats(rguid, v25 != 0, 1);
    if ( *(char *)(v12 + 4868) >= 0
      || CDXDependentSurfacePresenterFlip::IsIndependent((CDXDependentSurfacePresenterFlip *)*(unsigned int *)(v12 + 5040)) )
    {
      IEFrameHelper::NotifyExtensionCreation(
        (IEFrameHelper *)rguid,
        v25 == 0 ? (const struct _GUID *)0x80004005LL : 0,
        v40);
    }
    if ( !v25 )
    {
      if ( v33 != 3 )
      {
        if ( LastError == 8 )
        {
          memset_0(sz, 0, 0x58u);
          v79 = *rguid;
          if ( !(unsigned __int8)IEConfiguration_GetBool(268435477) )
          {
            v42 = 0x1000000;
LABEL_92:
            v48 = (struct BLOCKED_ACTION_DETAILS *)sz;
LABEL_93:
            NotifyHaveProtectedUserFromUnsafeContent(v13, 0, v42, v48);
          }
        }
        else if ( v72 && !v74 && (v43 = v69) != 0 && (v44 = bstrString) != 0 )
        {
          memset_0(sz, 0, 0x58u);
          v45 = *rguid;
          v83 = v43;
          v69 = 0;
          bstrString = 0;
          v84 = v44;
          v82 = 64;
          v79 = v45;
          NotifyHaveProtectedUserFromUnsafeContent(v13, 0, 0x40000000u, (struct BLOCKED_ACTION_DETAILS *)sz);
          SysFreeString(v83);
          v83 = 0;
          SysFreeString(v84);
        }
        else
        {
          if ( v16 )
          {
            if ( (*((_DWORD *)CMarkup::Doc(v13) + 1224) & 0x40000) == 0 )
            {
              memset_0(sz, 0, 0x58u);
              v46 = *rguid;
              v81 = v33;
              v80 = v75;
              v79 = v46;
              NotifyHaveProtectedUserFromUnsafeContent(v13, 0, 0x40000u, (struct BLOCKED_ACTION_DETAILS *)sz);
            }
            goto LABEL_86;
          }
          if ( v68 || Size_4 )
          {
            if ( (unsigned int)CoInternetIsExtensionsOff() )
              goto LABEL_86;
            v48 = 0;
            v42 = 8;
            goto LABEL_93;
          }
          if ( (v70[0] & 2) != 0 )
          {
            memset_0(sz, 0, 0x58u);
            v42 = 0x10000000;
            v79 = *rguid;
            goto LABEL_92;
          }
        }
      }
LABEL_86:
      v47 = bstrString;
      v19 = -2147024891;
LABEL_87:
      SysFreeString(v47);
      bstrString = 0;
      SysFreeString(v69);
      v10 = v67;
      goto LABEL_11;
    }
    v49 = CMarkup::OnExtensionLoading(v13, rguid, ExtensionValidationContextDynamic, v41, (struct CMarkup *)v60, 0);
    v47 = bstrString;
    v19 = v49;
    if ( v49 == -2147024891 )
      goto LABEL_87;
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
    v19 = CDocument::HostProcessUrlAction(*(CDocument **)(v51 + 120), v10, v8, v9, rguid, a6, a7, a8);
  }
  else
  {
    v19 = CDoc::EnsureSecurityManager((CDoc *)v12, (struct IInternetSecurityManagerEx2 **)&v76, 0);
    if ( v19 >= 0 )
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
      v20 = Size;
      v19 = ((__int64 (__fastcall *)(struct IUnknown *, const unsigned __int16 *, _QWORD, unsigned __int8 *, unsigned int, GUID *, BSTR *, BSTR *, int *))AddRef)(
              v76,
              v58,
              v67,
              v8,
              Size,
              rguid,
              v61,
              p_bstrString,
              p_Size_4);
      goto LABEL_12;
    }
  }
LABEL_11:
  v20 = Size;
LABEL_12:
  if ( v75 )
    SysFreeString(v75);
  v8 = (unsigned __int8 *)v73;
LABEL_15:
  ReleaseInterface(v76);
  if ( v19 >= 0 && v10 == 4608 && CDoc::IsPrerendered((CDoc *)v12) )
  {
    CPreloadManagerLock::CPreloadManagerLock((CPreloadManagerLock *)&v73, v13);
    v21 = v73;
    if ( v73 )
    {
      if ( CDoc::IsReadingModePrerendered((CDoc *)v12) )
      {
        if ( v8 )
        {
          memset_0(v8, 0, v20);
          *v8 = 3;
        }
      }
      else
      {
        v19 = CPreloadManager::SuspendDuringPrerender((__int64)v21, 0);
      }
    }
    TSmartPointer<CPreloadManager>::~TSmartPointer<CPreloadManager>((CPreloadManager **)&v73);
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x1808981e0  push    rbp
0x1808981e2  push    rbx
0x1808981e3  push    rsi
0x1808981e4  push    rdi
0x1808981e5  push    r12
0x1808981e7  push    r13
0x1808981e9  push    r14
0x1808981eb  push    r15
0x1808981ed  lea     rbp, [rsp-68h]
0x1808981f2  sub     rsp, 168h
0x1808981f9  mov     rax, cs:__security_cookie
0x180898200  xor     rax, rsp
0x180898203  mov     [rbp+0A0h+var_50], rax
0x180898207  mov     r14, [rbp+0A0h+rguid]
0x18089820e  mov     r13, r8
0x180898211  mov     edi, r9d
0x180898214  mov     r12d, edx
0x180898217  mov     dword ptr [rsp+1A0h+Size], edi
0x18089821b  mov     rbx, rcx
0x18089821e  mov     [rbp+0A0h+var_110], r8
0x180898222  xor     r15d, r15d
0x180898225  mov     [rsp+1A0h+var_130], edx
0x180898229  mov     [rbp+0A0h+var_F0], rcx
0x18089822d  call    ?Markup@CDocument@@QEBAPEAVCMarkup@@XZ; CDocument::Markup(void)
0x180898232  mov     [rbp+0A0h+var_100], r15
0x180898236  mov     rsi, rax
0x180898239  mov     [rbp+0A0h+var_F8], r15
0x18089823d  mov     [rbp+0A0h+var_108], r15d
0x180898241  test    r8, r8
0x180898244  jz      short loc_180898258
0x180898246  mov     r8d, edi; Size
0x180898249  xor     edx, edx; Val
0x18089824b  mov     rcx, r13; void *
0x18089824e  call    memset_0
0x180898253  mov     byte ptr [r13+0], 3
0x180898258  test    rsi, rsi
0x18089825b  jz      loc_180898B43
0x180898261  mov     rcx, rsi; this
0x180898264  call    ?Doc@CMarkup@@QEBAPEAVCDoc@@XZ; CMarkup::Doc(void)
0x180898269  mov     r15, rax
0x18089826c  test    rax, rax
0x18089826f  jz      loc_180898B43
0x180898275  cmp     r12d, 1200h
0x18089827c  jnz     loc_1808989C2
0x180898282  xor     r13d, r13d
0x180898285  mov     [rsp+1A0h+var_128], r13
0x18089828a  mov     [rsp+1A0h+bstrString], r13
0x18089828f  mov     dword ptr [rsp+1A0h+Size+4], r13d
0x180898294  test    r14, r14
0x180898297  jz      loc_180898A1D
0x18089829d  cmp     [rbp+0A0h+arg_28], 10h
0x1808982a4  jb      loc_180898A1D
0x1808982aa  lea     rbx, [rax+1530h]
0x1808982b1  mov     r8, r14; struct _GUID *
0x1808982b4  mov     rcx, rbx; this
0x1808982b7  lea     r9, [rsp+1A0h+Size+4]; int *
0x1808982bc  mov     rdx, rax; struct CDoc *
0x1808982bf  call    ?AssignClsidID@CClassTable@@QEAAJPEAVCDoc@@AEBU_GUID@@PEAJ@Z; CClassTable::AssignClsidID(CDoc *,_GUID const &,long *)
0x1808982c4  test    eax, eax
0x1808982c6  jz      loc_18089838D
0x1808982cc  mov     rcx, [rsp+1A0h+bstrString]; bstrString
0x1808982d1  mov     edi, 80070005h
0x1808982d6  call    cs:__imp_SysFreeString
0x1808982dd  nop     dword ptr [rax+rax+00h]
0x1808982e2  mov     rcx, [rsp+1A0h+var_128]; bstrString
0x1808982e7  mov     [rsp+1A0h+bstrString], r13
0x1808982ec  call    cs:__imp_SysFreeString
0x1808982f3  nop     dword ptr [rax+rax+00h]
0x1808982f8  mov     r14d, dword ptr [rsp+1A0h+Size]
0x1808982fd  mov     rcx, [rbp+0A0h+var_100]; bstrString
0x180898301  test    rcx, rcx
0x180898304  jz      short loc_180898312
0x180898306  call    cs:__imp_SysFreeString
0x18089830d  nop     dword ptr [rax+rax+00h]
0x180898312  mov     r13, [rbp+0A0h+var_110]
0x180898316  mov     rcx, [rbp+0A0h+var_F8]; struct IUnknown *
0x18089831a  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x18089831f  test    edi, edi
0x180898321  js      loc_180898B67
0x180898327  cmp     r12d, 1200h
0x18089832e  jnz     loc_180898B67
0x180898334  mov     rcx, r15; this
0x180898337  call    ?IsPrerendered@CDoc@@QEBA_NXZ; CDoc::IsPrerendered(void)
0x18089833c  test    al, al
0x18089833e  jz      loc_180898B67
0x180898344  mov     rdx, rsi; struct CMarkup *
0x180898347  lea     rcx, [rbp+0A0h+var_110]; this
0x18089834b  call    ??0CPreloadManagerLock@@QEAA@PEAVCMarkup@@@Z; CPreloadManagerLock::CPreloadManagerLock(CMarkup *)
0x180898350  mov     rbx, [rbp+0A0h+var_110]
0x180898354  test    rbx, rbx
0x180898357  jz      loc_180898B5E
0x18089835d  mov     rcx, r15; this
0x180898360  call    ?IsReadingModePrerendered@CDoc@@QEBA_NXZ; CDoc::IsReadingModePrerendered(void)
0x180898365  test    al, al
0x180898367  jz      loc_180898B52
0x18089836d  test    r13, r13
0x180898370  jz      loc_180898B5E
0x180898376  mov     r8d, r14d; Size
0x180898379  xor     edx, edx; Val
0x18089837b  mov     rcx, r13; void *
0x18089837e  call    memset_0
0x180898383  mov     byte ptr [r13+0], 3
0x180898388  jmp     loc_180898B5E
0x18089838d  mov     edx, dword ptr [rsp+1A0h+Size+4]; int
0x180898391  mov     rcx, rbx; this
0x180898394  call    ?GetInstantClassInfo@CClassTable@@QEAAPEAUINSTANTCLASSINFO@@J@Z; CClassTable::GetInstantClassInfo(long)
0x180898399  test    rax, rax
0x18089839c  jz      short loc_1808983D6
0x18089839e  test    dword ptr [rax+4], 400h
0x1808983a5  jz      short loc_1808983D6
0x1808983a7  cmp     cs:?g_cmptlgs@@3W4CMPTLGS@@A, 1; CMPTLGS g_cmptlgs
0x1808983ae  jz      loc_1808982CC
0x1808983b4  call    ?IECompatLoggingEnabled@@YAHXZ; IECompatLoggingEnabled(void)
0x1808983b9  test    eax, eax
0x1808983bb  jz      loc_1808982CC
0x1808983c1  mov     r9, rsi
0x1808983c4  mov     r8, r14
0x1808983c7  mov     ecx, 7
0x1808983cc  call    ?LogControlBlock@@YAXW4CtrlLoggingEvent@ControlLogging@@_NAEBU_GUID@@PEAVCMarkup@@@Z; LogControlBlock(ControlLogging::CtrlLoggingEvent,bool,_GUID const &,CMarkup *)
0x1808983d1  jmp     loc_1808982CC
0x1808983d6  mov     rcx, rsi; this
0x1808983d9  mov     [rbp+0A0h+var_114], r13d
0x1808983dd  call    ?Uri@CMarkup@@QEAAPEAUIUri@@XZ; CMarkup::Uri(void)
0x1808983e2  xor     r9d, r9d
0x1808983e5  mov     r8, rax
0x1808983e8  mov     rcx, r14
0x1808983eb  lea     r12d, [r9+1]
0x1808983ef  mov     edx, r12d
0x1808983f2  call    cs:__imp_CoInternetExtensionAllowedForUri
0x1808983f9  nop     dword ptr [rax+rax+00h]
0x1808983fe  mov     edi, eax
0x180898400  test    eax, eax
0x180898402  jnz     short loc_180898466
0x180898404  call    cs:__imp_GetLastError
0x18089840b  nop     dword ptr [rax+rax+00h]
0x180898410  mov     ebx, eax
0x180898412  call    cs:__imp_GetLastError
0x180898419  nop     dword ptr [rax+rax+00h]
0x18089841e  cmp     eax, 7
0x180898421  jnz     loc_1808985EC
0x180898427  test    byte ptr cs:Microsoft_IEEnableBits, 8
0x18089842e  jz      loc_1808985EC
0x180898434  lea     rax, [rbp+0A0h+var_80]
0x180898438  mov     [rbp+0A0h+var_70], r14
0x18089843c  lea     r9d, [r12+1]
0x180898441  mov     [rsp+1A0h+var_180], rax
0x180898446  lea     rdx, MSHTML_URLACTION_ACTIVEX_IMMERSIVE_INCOMPATIBLE
0x18089844d  mov     qword ptr [rbp+0A0h+var_68], 10h
0x180898455  lea     rcx, BERP_IE_Context
0x18089845c  call    McGenEventWrite_EventWriteTransfer
0x180898461  jmp     loc_1808985EC
0x180898466  mov     rdx, r14; struct _GUID *
0x180898469  mov     rcx, rsi; struct CMarkup *
0x18089846c  call    ?IsSafeToInstantiate@@YAHPEAVCMarkup@@AEBU_GUID@@@Z; IsSafeToInstantiate(CMarkup *,_GUID const &)
0x180898471  mov     edi, eax
0x180898473  test    eax, eax
0x180898475  jz      loc_1808985C7
0x18089847b  mov     rcx, rsi; this
0x18089847e  call    ?IsPendingRoot@CMarkup@@QEAA_NXZ; CMarkup::IsPendingRoot(void)
0x180898483  mov     rcx, r15; this
0x180898486  test    al, al
0x180898488  jz      short loc_180898491
0x18089848a  call    ?PendingPrimaryMarkup@CDoc@@QEBAPEAVCMarkup@@XZ; CDoc::PendingPrimaryMarkup(void)
0x18089848f  jmp     short loc_180898496
0x180898491  call    ?PrimaryMarkup@CDoc@@QEBAPEAVCMarkup@@XZ; CDoc::PrimaryMarkup(void)
0x180898496  mov     r8d, 40h ; '@'; unsigned int
0x18089849c  mov     rdx, rax; struct CMarkup *
0x18089849f  call    ?IsPageActionAllowed@CDoc@@QEAAHPEAVCMarkup@@K@Z; CDoc::IsPageActionAllowed(CMarkup *,ulong)
0x1808984a4  test    eax, eax
0x1808984a6  jnz     loc_1808985E9
0x1808984ac  xorps   xmm0, xmm0
0x1808984af  mov     [rbp+0A0h+var_78], r13
0x1808984b3  lea     rbx, ??_7CUString@@6B@; const CUString::`vftable'
0x1808984ba  mov     dword ptr [rbp+0A0h+var_70], 0Bh
0x1808984c1  mov     rcx, rsi; this
0x1808984c4  mov     [rbp+0A0h+var_80], rbx
0x1808984c8  movdqu  [rbp+0A0h+var_68], xmm0
0x1808984cd  mov     [rbp+0A0h+var_58], r13d
0x1808984d1  call    ?Uri@CMarkup@@QEAAPEAUIUri@@XZ; CMarkup::Uri(void)
0x1808984d6  test    rax, rax
0x1808984d9  jz      short loc_1808984EA
0x1808984db  xor     r8d, r8d; enum __MIDL_IUri_0001
0x1808984de  lea     rcx, [rbp+0A0h+var_80]; this
0x1808984e2  mov     rdx, rax; struct IUri *
0x1808984e5  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x1808984ea  lea     rcx, [rbp+0A0h+var_120]
0x1808984ee  mov     qword ptr [rbp+0A0h+var_120], r13
0x1808984f2  call    cs:__imp_GetVersionManager
0x1808984f9  nop     dword ptr [rax+rax+00h]
0x1808984fe  test    eax, eax
0x180898500  js      loc_1808985B0
0x180898506  mov     r8d, 27h ; '''; cchMax
0x18089850c  lea     rdx, [rbp+0A0h+sz]; lpsz
0x180898510  mov     rcx, r14; rguid
0x180898513  call    cs:__imp_StringFromGUID2
0x18089851a  nop     dword ptr [rax+rax+00h]
0x18089851f  test    eax, eax
0x180898521  jz      short loc_18089859C
0x180898523  mov     rax, qword ptr [rbp+0A0h+var_120]
0x180898527  mov     dword ptr [rsp+1A0h+Size+4], r12d
0x18089852c  mov     rcx, [rax]
0x18089852f  mov     rbx, [rcx+18h]
0x180898533  call    ?IsOs_Wow6432@@YA_NXZ; IsOs_Wow6432(void)
0x180898538  mov     r9, qword ptr [rbp+0A0h+var_68+8]
0x18089853c  lea     rdx, [rbp+0A0h+sz]
0x180898540  movzx   ecx, al
0x180898543  xor     r8d, r8d
0x180898546  lea     rax, [rbp+0A0h+var_108]
0x18089854a  mov     [rsp+1A0h+var_158], rax
0x18089854f  lea     rax, [rsp+1A0h+Size+4]
0x180898554  mov     [rsp+1A0h+var_160], rax
0x180898559  lea     rax, [rsp+1A0h+bstrString]
0x18089855e  mov     qword ptr [rsp+1A0h+var_168], rax
0x180898563  lea     rax, [rsp+1A0h+var_128]
0x180898568  mov     qword ptr [rsp+1A0h+var_170], rax
0x18089856d  mov     rax, rbx
0x180898570  mov     dword ptr [rsp+1A0h+var_178], r13d
0x180898575  mov     dword ptr [rsp+1A0h+var_180], ecx
0x180898579  mov     rcx, qword ptr [rbp+0A0h+var_120]
0x18089857d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180898582  test    eax, eax
0x180898584  js      short loc_180898595
0x180898586  mov     edi, dword ptr [rsp+1A0h+Size+4]
0x18089858a  mov     ebx, r13d
0x18089858d  test    edi, edi
0x18089858f  setz    bl
0x180898592  mov     [rbp+0A0h+var_114], ebx
0x180898595  lea     rbx, ??_7CUString@@6B@; const CUString::`vftable'
0x18089859c  mov     rcx, qword ptr [rbp+0A0h+var_120]
0x1808985a0  mov     rax, [rcx]
0x1808985a3  mov     rax, [rax+10h]
0x1808985a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808985ac  mov     qword ptr [rbp+0A0h+var_120], r13
0x1808985b0  xor     edx, edx; struct IUri *
0x1808985b2  mov     [rbp+0A0h+var_80], rbx
0x1808985b6  lea     rcx, [rbp+0A0h+var_80]; this
0x1808985ba  lea     r8d, [rdx+0Bh]; enum __MIDL_IUri_0001
0x1808985be  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x1808985c3  test    edi, edi
0x1808985c5  jnz     short loc_1808985E9
0x1808985c7  cmp     cs:?g_cmptlgs@@3W4CMPTLGS@@A, r12d; CMPTLGS g_cmptlgs
0x1808985ce  jz      short loc_1808985E9
0x1808985d0  call    ?IECompatLoggingEnabled@@YAHXZ; IECompatLoggingEnabled(void)
0x1808985d5  test    eax, eax
0x1808985d7  jz      short loc_1808985E9
0x1808985d9  mov     r9, rsi
0x1808985dc  mov     r8, r14
0x1808985df  mov     ecx, 8
0x1808985e4  call    ?LogControlBlock@@YAXW4CtrlLoggingEvent@ControlLogging@@_NAEBU_GUID@@PEAVCMarkup@@@Z; LogControlBlock(ControlLogging::CtrlLoggingEvent,bool,_GUID const &,CMarkup *)
0x1808985e9  mov     ebx, r13d
0x1808985ec  mov     dword ptr [rsp+1A0h+Size+4], r12d
0x1808985f1  xor     r12d, r12d
0x1808985f4  mov     [rsp+1A0h+var_12C], r13d
0x1808985f9  mov     [rbp+0A0h+var_120], r13d
0x1808985fd  mov     [rbp+0A0h+var_118], r12d
0x180898601  test    edi, edi
0x180898603  jnz     short loc_18089860E
0x180898605  cmp     ebx, 8
0x180898608  jnz     loc_1808986B1
0x18089860e  cmp     [rbp+0A0h+var_114], r12d
0x180898612  jnz     loc_1808986B1
0x180898618  mov     rcx, rsi; this
0x18089861b  call    ?Uri@CMarkup@@QEAAPEAUIUri@@XZ; CMarkup::Uri(void)
0x180898620  test    rax, rax
0x180898623  jz      short loc_180898638
0x180898625  lea     rdx, [rbp+0A0h+var_100]
0x180898629  mov     rcx, rax
0x18089862c  call    cs:__imp_?EDL_GetDomainFromUri@@YAJPEAUIUri@@PEAPEAG@Z; EDL_GetDomainFromUri(IUri *,ushort * *)
0x180898633  nop     dword ptr [rax+rax+00h]
0x180898638  mov     r8, [rbp+0A0h+var_100]; unsigned __int16 *
0x18089863c  lea     rax, [rsp+1A0h+var_12C]
0x180898641  lea     r9, [rbp+0A0h+var_118]; enum TYPE_APPROVAL_NEEDED *
0x180898645  mov     [rsp+1A0h+var_180], rax; struct CMarkup *
0x18089864a  mov     rdx, rsi; struct CMarkup *
0x18089864d  mov     rcx, r14; struct _GUID *
0x180898650  call    ?IsPendingApproval@@YAHAEBU_GUID@@PEAVCMarkup@@PEBGPEAW4TYPE_APPROVAL_NEEDED@@PEAW4FLAG_CONTENTFILTERSTATE@@@Z; IsPendingApproval(_GUID const &,CMarkup *,ushort const *,TYPE_APPROVAL_NEEDED *,FLAG_CONTENTFILTERSTATE *)
0x180898655  mov     r12d, [rsp+1A0h+var_12C]
0x18089865a  mov     r13d, eax
0x18089865d  test    r12d, r12d
0x180898660  jz      short loc_180898679
0x180898662  mov     rcx, rsi; this
0x180898665  call    ?IsPendingRoot@CMarkup@@QEAA_NXZ; CMarkup::IsPendingRoot(void)
0x18089866a  movzx   r8d, al
0x18089866e  mov     edx, r12d
0x180898671  mov     rcx, r15
0x180898674  call    ?SetActiveXFilterUI@CDoc@@QEAAXW4FLAG_CONTENTFILTERSTATE@@H@Z; CDoc::SetActiveXFilterUI(FLAG_CONTENTFILTERSTATE,int)
0x180898679  test    r13d, r13d
0x18089867c  jz      short loc_1808986A0
0x18089867e  cmp     cs:?g_cmptlgs@@3W4CMPTLGS@@A, 1; CMPTLGS g_cmptlgs
0x180898685  jz      short loc_1808986A0
0x180898687  call    ?IECompatLoggingEnabled@@YAHXZ; IECompatLoggingEnabled(void)
0x18089868c  test    eax, eax
0x18089868e  jz      short loc_1808986A0
0x180898690  mov     r9, rsi
0x180898693  mov     r8, r14
0x180898696  mov     ecx, 10h
0x18089869b  call    ?LogControlBlock@@YAXW4CtrlLoggingEvent@ControlLogging@@_NAEBU_GUID@@PEAVCMarkup@@@Z; LogControlBlock(ControlLogging::CtrlLoggingEvent,bool,_GUID const &,CMarkup *)
0x1808986a0  mov     r12d, [rbp+0A0h+var_118]
0x1808986a4  test    edi, edi
0x1808986a6  jz      short loc_1808986B1
  ... truncated ...
```
