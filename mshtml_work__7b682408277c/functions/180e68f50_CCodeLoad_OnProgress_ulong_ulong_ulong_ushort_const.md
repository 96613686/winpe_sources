# CCodeLoad::OnProgress(ulong,ulong,ulong,ushort const *)

- ea: `0x180e68f50`
- end: `0x180e6984d`
- name: `?OnProgress@CCodeLoad@@UEAAJKKKPEBG@Z`
- size: `2301`
- prototype: `__int64 __fastcall(CCodeLoad *__hidden this, unsigned int, unsigned int, unsigned int, LPCOLESTR lpsz)`
- caller_count: `0`
- callee_count: `28`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800151f0`
- `0x180066940`
- `0x1800f9604`
- `0x180138ce4`
- `0x180139080`
- `0x1801393a8`
- `0x180149610`
- `0x1803ddae0`
- `0x1803e13d4`
- `0x1803e41f0`
- `0x180422abc`
- `0x180571708`
- `0x18077b900`
- `0x18083bed4`
- `0x180850f20`
- `0x18087594c`
- `0x180e5a0c4`
- `0x180e5a8a8`
- `0x180e5aa04`
- `0x180e68f50`
- `0x180e6a56c`
- `0x180e6a628`
- `0x18108be78`
- `0x181096438`
- `0x181097d14`
- `0x1810f6516`
- `0x1810f65c0`
- `0x181104010`

## import_xrefs

- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x180e694ef`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x180e694ef`
- `iertutil!__imp_?EDL_GetDomainFromUri@@YAJPEAUIUri@@PEAPEAG@Z` at `0x180e69585`
- `iertutil!__imp_?EDL_GetDomainFromUri@@YAJPEAUIUri@@PEAPEAG@Z` at `0x180e69585`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromGUID2` at `0x180e6934f`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromGUID2` at `0x180e6934f`
- `api-ms-win-downlevel-ole32-l1-1-0!CLSIDFromString` at `0x180e6903a`
- `api-ms-win-downlevel-ole32-l1-1-0!CLSIDFromString` at `0x180e69182`
- `api-ms-win-downlevel-ole32-l1-1-0!CLSIDFromString` at `0x180e6903a`
- `api-ms-win-downlevel-ole32-l1-1-0!CLSIDFromString` at `0x180e69182`
- `urlmon!__imp_?IECompatLogUIPIBlockedExtension@@YAXKAEBU_GUID@@PEBG@Z` at `0x180e69554`
- `urlmon!__imp_?IECompatLogUIPIBlockedExtension@@YAXKAEBU_GUID@@PEBG@Z` at `0x180e69554`
- `urlmon!__imp_CoInternetExtensionAllowedForUri` at `0x180e69295`
- `urlmon!__imp_CoInternetExtensionAllowedForUri` at `0x180e69295`
- `urlmon!__imp_GetVersionManager` at `0x180e692eb`
- `urlmon!__imp_GetVersionManager` at `0x180e692eb`
- `OLEAUT32!__imp_SysAllocString` at `0x180e690f2`
- `OLEAUT32!__imp_SysAllocString` at `0x180e69120`
- `OLEAUT32!__imp_SysAllocString` at `0x180e697e9`
- `OLEAUT32!__imp_SysAllocString` at `0x180e690f2`
- `OLEAUT32!__imp_SysAllocString` at `0x180e69120`
- `OLEAUT32!__imp_SysAllocString` at `0x180e697e9`
- `OLEAUT32!__imp_SysFreeString` at `0x180e690e3`
- `OLEAUT32!__imp_SysFreeString` at `0x180e69111`
- `OLEAUT32!__imp_SysFreeString` at `0x180e69453`
- `OLEAUT32!__imp_SysFreeString` at `0x180e6946b`
- `OLEAUT32!__imp_SysFreeString` at `0x180e6947f`
- `OLEAUT32!__imp_SysFreeString` at `0x180e69499`
- `OLEAUT32!__imp_SysFreeString` at `0x180e69656`
- `OLEAUT32!__imp_SysFreeString` at `0x180e697cc`
- `OLEAUT32!__imp_SysFreeString` at `0x180e690e3`
- `OLEAUT32!__imp_SysFreeString` at `0x180e69111`
- `OLEAUT32!__imp_SysFreeString` at `0x180e69453`
- `OLEAUT32!__imp_SysFreeString` at `0x180e6946b`
- `OLEAUT32!__imp_SysFreeString` at `0x180e6947f`
- `OLEAUT32!__imp_SysFreeString` at `0x180e69499`
- `OLEAUT32!__imp_SysFreeString` at `0x180e69656`
- `OLEAUT32!__imp_SysFreeString` at `0x180e697cc`

## pseudocode

```c
__int64 __fastcall CCodeLoad::OnProgress(CCodeLoad *this, __int64 a2, __int64 a3, int a4, LPCOLESTR lpsz)
{
  HRESULT v6; // r14d
  __int64 v7; // r9
  CElement *v8; // rcx
  CMarkup *WindowedMarkupContext; // rsi
  __int64 v10; // rdx
  __int64 v11; // rcx
  struct IHTMLDocument2 *v12; // r9
  void (*v13)(void); // rax
  CElement *v14; // rcx
  struct CDoc *v15; // r13
  struct CMarkup *MarkupPtr; // rax
  CMarkup *v17; // r15
  __int128 *v18; // r12
  struct INSTANTCLASSINFO *InstantClassInfo; // rax
  struct INSTANTCLASSINFO *v20; // rbx
  __int64 v21; // rcx
  struct IHTMLDocument2 *v22; // r9
  int v23; // eax
  int v24; // ecx
  struct IUri *v25; // rax
  int v26; // ebx
  struct CMarkup *v27; // rax
  CDoc *v28; // rcx
  int VersionManager; // r13d
  struct IUri *v30; // rax
  __int64 (__fastcall *v31)(_QWORD, OLECHAR *, _QWORD, _QWORD, bool, _DWORD, BSTR *, OLECHAR **, int *, int *); // rbx
  bool v32; // al
  OLECHAR *v33; // r13
  OLECHAR *v34; // rbx
  __int128 v35; // xmm0
  struct IUri *v36; // rax
  int v37; // eax
  unsigned int v38; // esi
  int v39; // r13d
  CMarkup *v40; // rcx
  struct CDoc *v41; // rbx
  CMarkup *v42; // rcx
  bool IsPendingRoot; // al
  int v44; // ebx
  __int128 v45; // xmm0
  __int64 v46; // rcx
  __int64 v47; // r10
  __int64 v48; // rax
  const OLECHAR *v49; // rcx
  const OLECHAR *v50; // rax
  __int64 v51; // r8
  int v52; // edx
  CCodeLoad *v53; // rcx
  int v54; // eax
  __int64 v55; // rcx
  int v56; // ecx
  int v57; // eax
  struct CMarkup *v59; // [rsp+28h] [rbp-E0h]
  BSTR v60; // [rsp+68h] [rbp-A0h] BYREF
  int v61; // [rsp+70h] [rbp-98h] BYREF
  int v62; // [rsp+74h] [rbp-94h] BYREF
  __int64 v63; // [rsp+78h] [rbp-90h] BYREF
  OLECHAR *v64; // [rsp+80h] [rbp-88h] BYREF
  int v65; // [rsp+88h] [rbp-80h]
  _QWORD v66[2]; // [rsp+90h] [rbp-78h] BYREF
  int v67; // [rsp+A0h] [rbp-68h]
  __int128 v68; // [rsp+A8h] [rbp-60h]
  int v69; // [rsp+B8h] [rbp-50h]
  _BYTE v70[16]; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v71; // [rsp+D8h] [rbp-30h]
  BSTR v72; // [rsp+100h] [rbp-8h]
  int v73; // [rsp+108h] [rbp+0h]
  int v74; // [rsp+10Ch] [rbp+4h]
  BSTR bstrString; // [rsp+110h] [rbp+8h]
  BSTR v76; // [rsp+118h] [rbp+10h]
  GUID pclsid; // [rsp+128h] [rbp+20h] BYREF
  OLECHAR sz[40]; // [rsp+138h] [rbp+30h] BYREF

  v6 = 0;
  a2 = (unsigned int)a2;
  v7 = (unsigned int)a3;
  if ( a4 == 3 )
  {
    v56 = *((_DWORD *)this + 126);
    if ( (v56 & 0x10) != 0 )
      return (unsigned int)v6;
    v57 = *((_DWORD *)this + 116);
    switch ( v57 )
    {
      case 0:
        return (unsigned int)v6;
      case 2:
        if ( (int)CURSProcessor::CancelPendingRequests(*((CURSProcessor **)this + 56)) < 0 )
        {
          v57 = *((_DWORD *)this + 116);
        }
        else
        {
          *((_DWORD *)this + 116) = 1;
          v57 = 1;
        }
        break;
      case 3:
        *((_DWORD *)this + 116) = 1;
        *((_DWORD *)this + 126) = v56 & 0xFFFFFFF7;
        goto LABEL_99;
    }
    if ( v57 != 1 )
      return (unsigned int)v6;
LABEL_99:
    SysFreeString(*((BSTR *)this + 60));
    *((_QWORD *)this + 60) = *((_QWORD *)this + 59);
    *((_QWORD *)this + 59) = SysAllocString(lpsz);
    CCodeLoad::_SubmitCodeUrlForMalwareEvaluation((CCodeLoad *)((char *)this - 24));
    return (unsigned int)v6;
  }
  if ( a4 != 4 )
  {
    if ( a4 == 5 || a4 == 7 || a4 == 8 )
    {
      v47 = *((_QWORD *)this + 51);
      if ( v47 )
      {
        if ( lpsz )
        {
          v48 = -1;
          do
            ++v48;
          while ( lpsz[v48] );
          v49 = &lpsz[v48];
          if ( v49 > lpsz )
          {
            do
            {
              v50 = v49 - 1;
              if ( *(v49 - 1) == 47 )
                break;
              if ( *v50 == 92 )
                break;
              --v49;
            }
            while ( v50 > lpsz );
          }
          v51 = 31;
        }
        else
        {
          v49 = 0;
          v51 = 29;
        }
        (*(void (__fastcall **)(__int64, _QWORD, __int64, __int64, const OLECHAR *, int, _DWORD, _DWORD))(*(_QWORD *)v47 + 32LL))(
          v47,
          *((unsigned int *)this + 104),
          v51,
          3,
          v49,
          8160,
          a2,
          v7);
      }
      return (unsigned int)v6;
    }
    if ( a4 != 12 )
    {
      switch ( a4 )
      {
        case '3':
          SysFreeString(*((BSTR *)this + 53));
          *((_QWORD *)this + 53) = SysAllocString(lpsz);
          return (unsigned int)v6;
        case '4':
          SysFreeString(*((BSTR *)this + 54));
          *((_QWORD *)this + 54) = SysAllocString(lpsz);
          return (unsigned int)v6;
        case 'D':
          v8 = (CElement *)*((_QWORD *)this + 30);
          if ( !v8 || (WindowedMarkupContext = CElement::GetWindowedMarkupContext(v8)) == 0 )
            return (unsigned int)-2147024891;
          pclsid = 0;
          v6 = CLSIDFromString(lpsz, &pclsid);
          if ( v6 >= 0 )
          {
            v11 = *((_QWORD *)this + 30);
            v60 = 0;
            if ( *(__int64 (__fastcall **)())(*(_QWORD *)v11 + 1624LL) != _vtguard )
              _report_securityfailure(1, v10);
            v6 = (*(__int64 (__fastcall **)(__int64, GUID *, BSTR *))(*(_QWORD *)v11 + 1536LL))(
                   v11,
                   &GUID_3050f1ff_98b5_11cf_bb82_00aa00bdce0b,
                   &v60);
            if ( v6 >= 0 )
            {
              v6 = CMarkup::OnExtensionLoading(
                     WindowedMarkupContext,
                     &pclsid,
                     ExtensionValidationContextParsed,
                     v12,
                     v59,
                     (struct IHTMLElement *)v60);
              v13 = *(void (**)(void))(*(_QWORD *)v60 + 16LL);
LABEL_16:
              v13();
              return (unsigned int)v6;
            }
          }
          break;
      }
      return (unsigned int)v6;
    }
    v14 = (CElement *)*((_QWORD *)this + 30);
    v61 = 0;
    if ( !v14 )
      goto LABEL_73;
    v15 = CElement::Doc(v14);
    MarkupPtr = CElement::GetMarkupPtr(*((CElement **)this + 30));
    v17 = MarkupPtr;
    if ( !v15 )
      goto LABEL_73;
    if ( !MarkupPtr )
      goto LABEL_73;
    v18 = (__int128 *)((char *)this + 264);
    CLSIDFromString(lpsz, (LPCLSID)((char *)this + 264));
    v6 = CClassTable::AssignClsidID(
           (struct CDoc *)((char *)v15 + 5424),
           v15,
           (const struct _GUID *)((char *)this + 264),
           &v61);
    if ( v6 < 0 )
      goto LABEL_73;
    InstantClassInfo = CClassTable::GetInstantClassInfo((struct CDoc *)((char *)v15 + 5424), v61);
    v20 = InstantClassInfo;
    if ( !InstantClassInfo || (*((_DWORD *)InstantClassInfo + 1) & 0x400) != 0 )
      goto LABEL_73;
    v21 = *((_QWORD *)this + 30);
    v60 = 0;
    if ( *(__int64 (__fastcall **)())(*(_QWORD *)v21 + 1624LL) != _vtguard )
      _report_securityfailure(1, a2);
    if ( (*(int (__fastcall **)(__int64, GUID *, BSTR *))(*(_QWORD *)v21 + 1536LL))(
           v21,
           &GUID_3050f1ff_98b5_11cf_bb82_00aa00bdce0b,
           &v60) >= 0 )
    {
      v23 = CMarkup::OnExtensionLoading(
              v17,
              (const struct _GUID *)((char *)v20 + 12),
              ExtensionValidationContextParsed,
              v22,
              v59,
              (struct IHTMLElement *)v60);
      v24 = v6;
      if ( v23 == -2147024891 )
        v24 = -2147467260;
      v6 = v24;
      (*(void (__fastcall **)(BSTR))(*(_QWORD *)v60 + 16LL))(v60);
      if ( v6 < 0 )
        goto LABEL_73;
    }
    v25 = CMarkup::Uri(v17);
    LODWORD(v63) = CoInternetExtensionAllowedForUri((char *)this + 264, 1, v25);
    v26 = v63;
    if ( !(_DWORD)v63 )
      goto LABEL_73;
    if ( CMarkup::IsPendingRoot(v17) )
      v27 = CDoc::PendingPrimaryMarkup(v15);
    else
      v27 = CDoc::PrimaryMarkup(v15);
    if ( CDoc::IsPageActionAllowed(v28, v27, 0x40u)
      || (*(_QWORD *)&pclsid.Data1 = 0, VersionManager = GetVersionManager(&pclsid), VersionManager < 0) )
    {
LABEL_51:
      if ( !IsProtectedModeProcess()
        && v26
        && (unsigned int)Ext_IsIEExtCompatible((const struct _GUID *)((char *)this + 264), 0, 0, v7) == 1 )
      {
        if ( g_cmptlgs == 1
          || !(unsigned int)IECompatLoggingEnabled()
          || g_cmptlgs == 1
          || !(unsigned int)IECompatLoggingEnabled() )
        {
          goto LABEL_73;
        }
        v6 = -2147467260;
        IECompatLogUIPIBlockedExtension(1u, (const struct _GUID *)((char *)this + 264), 0);
      }
      if ( v6 >= 0 )
      {
        v60 = 0;
        v36 = CMarkup::Uri(v17);
        if ( v36 )
          EDL_GetDomainFromUri(v36, &v60);
        LODWORD(v63) = 0;
        v62 = 0;
        v37 = IsPendingApproval(
                (const struct _GUID *)((char *)this + 264),
                v17,
                v60,
                (enum TYPE_APPROVAL_NEEDED *)&v62,
                (enum FLAG_CONTENTFILTERSTATE *)&v63);
        v38 = v63;
        v39 = v37;
        if ( (_DWORD)v63 && CMarkup::Doc(v17) )
        {
          v41 = CMarkup::Doc(v40);
          IsPendingRoot = CMarkup::IsPendingRoot(v42);
          CDoc::SetActiveXFilterUI(v41, v38, IsPendingRoot);
        }
        if ( v39 )
        {
          v44 = v62;
          if ( v62 != 3 && (*((_DWORD *)CMarkup::Doc(v17) + 1224) & 0x40000) == 0 )
          {
            memset_0(v70, 0, 0x58u);
            v45 = *v18;
            v73 = v44;
            v72 = v60;
            v71 = v45;
            NotifyHaveProtectedUserFromUnsafeContent(v17, 0, 0x40000u, (struct BLOCKED_ACTION_DETAILS *)v70);
          }
          v6 = -2147467260;
        }
        if ( v60 )
          SysFreeString(v60);
        if ( v6 >= 0 )
          return (unsigned int)v6;
      }
LABEL_73:
      v46 = *((_QWORD *)this + 28);
      v6 = -2147467260;
      if ( v46 )
      {
        (*(void (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v46 + 24LL))(v46, a2, a3, v7);
        TSmartPointer<CTransitionClient>::~TSmartPointer<CTransitionClient>((char *)this + 224);
      }
      return (unsigned int)v6;
    }
    v66[1] = 0;
    v66[0] = &CUString::`vftable';
    v67 = 11;
    v68 = 0;
    v69 = 0;
    v30 = CMarkup::Uri(v17);
    if ( v30 )
      CUString::Set((CUString *)v66, v30, Uri_PROPERTY_ABSOLUTE_URI);
    if ( !StringFromGUID2((const GUID *const)((char *)this + 264), sz, 39) )
    {
LABEL_48:
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&pclsid.Data1 + 16LL))(*(_QWORD *)&pclsid.Data1);
      *(_QWORD *)&pclsid.Data1 = 0;
      v66[0] = &CUString::`vftable';
      CUString::Set((CUString *)v66, 0, Uri_PROPERTY_RAW_URI);
      if ( VersionManager >= 0 && !v26 )
        v6 = -2147467260;
      goto LABEL_51;
    }
    v60 = 0;
    v64 = 0;
    v61 = 0;
    v62 = 0;
    v31 = *(__int64 (__fastcall **)(_QWORD, OLECHAR *, _QWORD, _QWORD, bool, _DWORD, BSTR *, OLECHAR **, int *, int *))(**(_QWORD **)&pclsid.Data1 + 24LL);
    v32 = IsOs_Wow6432();
    v65 = v31(*(_QWORD *)&pclsid.Data1, sz, 0, *((_QWORD *)&v68 + 1), v32, 0, &v60, &v64, &v61, &v62);
    if ( v65 >= 0 )
    {
      LODWORD(v63) = v61;
      if ( !v62 )
      {
        v33 = v60;
        if ( v60 )
        {
          v34 = v64;
          if ( !v64 )
          {
LABEL_47:
            SysFreeString(v34);
            v64 = 0;
            SysFreeString(v60);
            v26 = v63;
            VersionManager = v65;
            goto LABEL_48;
          }
          memset_0(v70, 0, 0x58u);
          v35 = *v18;
          bstrString = v33;
          v60 = 0;
          v64 = 0;
          v76 = v34;
          v74 = 64;
          v71 = v35;
          NotifyHaveProtectedUserFromUnsafeContent(v17, 0, 0x40000000u, (struct BLOCKED_ACTION_DETAILS *)v70);
          SysFreeString(bstrString);
          bstrString = 0;
          SysFreeString(v76);
        }
      }
    }
    v34 = v64;
    goto LABEL_47;
  }
  v52 = *((_DWORD *)this + 116);
  v53 = (CCodeLoad *)((char *)this - 24);
  v54 = *((_DWORD *)this + 126) | 4;
  *((_DWORD *)this + 126) = v54;
  if ( v52 == 3 )
  {
    if ( (v54 & 8) != 0 )
    {
      v55 = *((_QWORD *)this + 28);
      if ( v55 )
      {
        v13 = *(void (**)(void))(*(_QWORD *)v55 + 24LL);
        goto LABEL_16;
      }
    }
  }
  else if ( v52 == 1 )
  {
    CCodeLoad::_ReleaseMalwareObjects(v53);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180e68f50  mov     rax, rsp
0x180e68f53  mov     [rax+20h], r9d
0x180e68f57  mov     [rax+18h], r8d
0x180e68f5b  mov     [rax+10h], edx
0x180e68f5e  mov     [rax+8], rcx
0x180e68f62  push    rbp
0x180e68f63  push    rbx
0x180e68f64  push    rsi
0x180e68f65  push    rdi
0x180e68f66  push    r12
0x180e68f68  push    r13
0x180e68f6a  push    r14
0x180e68f6c  push    r15
0x180e68f6e  lea     rbp, [rax-0D8h]
0x180e68f75  sub     rsp, 198h
0x180e68f7c  mov     rax, cs:__security_cookie
0x180e68f83  xor     rax, rsp
0x180e68f86  mov     [rbp+0D0h+var_50], rax
0x180e68f8d  mov     eax, [rbp+0D0h+arg_18]
0x180e68f93  xor     esi, esi
0x180e68f95  mov     rdi, [rbp+0D0h+arg_0]
0x180e68f9c  mov     r14d, esi
0x180e68f9f  mov     edx, [rbp+0D0h+arg_8]
0x180e68fa5  mov     r9d, [rbp+0D0h+arg_10]
0x180e68fac  mov     rbx, [rbp+0D0h+lpsz]
0x180e68fb3  lea     r11d, [rsi+3]
0x180e68fb7  sub     eax, r11d
0x180e68fba  jz      loc_180E69786
0x180e68fc0  sub     eax, 1
0x180e68fc3  jz      loc_180E69730
0x180e68fc9  sub     eax, 1
0x180e68fcc  jz      loc_180E696A9
0x180e68fd2  sub     eax, 2
0x180e68fd5  jz      loc_180E696A9
0x180e68fdb  sub     eax, 1
0x180e68fde  jz      loc_180E696A9
0x180e68fe4  sub     eax, 4
0x180e68fe7  jz      loc_180E69138
0x180e68fed  sub     eax, 27h ; '''
0x180e68ff0  jz      loc_180E6910A
0x180e68ff6  sub     eax, 1
0x180e68ff9  jz      loc_180E690DC
0x180e68fff  cmp     eax, 10h
0x180e69002  jnz     loc_180E69805
0x180e69008  mov     rcx, [rdi+0F0h]; this
0x180e6900f  test    rcx, rcx
0x180e69012  jz      loc_180E690D1
0x180e69018  call    ?GetWindowedMarkupContext@CElement@@UEBAPEAVCMarkup@@XZ; CElement::GetWindowedMarkupContext(void)
0x180e6901d  xor     r15d, r15d
0x180e69020  mov     rsi, rax
0x180e69023  test    rax, rax
0x180e69026  jz      loc_180E690D1
0x180e6902c  xorps   xmm0, xmm0
0x180e6902f  lea     rdx, [rbp+0D0h+pclsid]; pclsid
0x180e69033  mov     rcx, rbx; lpsz
0x180e69036  movups  xmmword ptr [rbp+0D0h+pclsid.Data1], xmm0
0x180e6903a  call    cs:__imp_CLSIDFromString
0x180e69041  nop     dword ptr [rax+rax+00h]
0x180e69046  mov     r14d, eax
0x180e69049  test    eax, eax
0x180e6904b  js      loc_180E69805
0x180e69051  mov     rcx, [rdi+0F0h]
0x180e69058  lea     rax, __vtguard
0x180e6905f  mov     [rsp+1D0h+var_170], r15
0x180e69064  mov     r9, [rcx]
0x180e69067  cmp     [r9+658h], rax
0x180e6906e  jnz     short loc_180E690C6
0x180e69070  mov     rax, [r9+600h]
0x180e69077  lea     r8, [rsp+1D0h+var_170]
0x180e6907c  lea     rdx, _GUID_3050f1ff_98b5_11cf_bb82_00aa00bdce0b
0x180e69083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180e69088  mov     r14d, eax
0x180e6908b  test    eax, eax
0x180e6908d  js      loc_180E69805
0x180e69093  mov     rax, [rsp+1D0h+var_170]
0x180e69098  lea     r8d, [r15+2]; enum ExtensionValidationContexts
0x180e6909c  lea     rdx, [rbp+0D0h+pclsid]; struct _GUID *
0x180e690a0  mov     [rsp+1D0h+var_1A8], rax; struct IHTMLElement *
0x180e690a5  mov     rcx, rsi; this
0x180e690a8  call    ?OnExtensionLoading@CMarkup@@QEAAJAEBU_GUID@@W4ExtensionValidationContexts@@PEAUIHTMLDocument2@@PEAV1@PEAUIHTMLElement@@@Z; CMarkup::OnExtensionLoading(_GUID const &,ExtensionValidationContexts,IHTMLDocument2 *,CMarkup *,IHTMLElement *)
0x180e690ad  mov     rcx, [rsp+1D0h+var_170]
0x180e690b2  mov     r14d, eax
0x180e690b5  mov     rax, [rcx]
0x180e690b8  mov     rax, [rax+10h]
0x180e690bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180e690c1  jmp     loc_180E69805
0x180e690c6  mov     ecx, 1
0x180e690cb  call    __report_securityfailure
0x180e690d1  mov     r14d, 80070005h
0x180e690d7  jmp     loc_180E69805
0x180e690dc  mov     rcx, [rdi+1B0h]; bstrString
0x180e690e3  call    cs:__imp_SysFreeString
0x180e690ea  nop     dword ptr [rax+rax+00h]
0x180e690ef  mov     rcx, rbx; psz
0x180e690f2  call    cs:__imp_SysAllocString
0x180e690f9  nop     dword ptr [rax+rax+00h]
0x180e690fe  mov     [rdi+1B0h], rax
0x180e69105  jmp     loc_180E69805
0x180e6910a  mov     rcx, [rdi+1A8h]; bstrString
0x180e69111  call    cs:__imp_SysFreeString
0x180e69118  nop     dword ptr [rax+rax+00h]
0x180e6911d  mov     rcx, rbx; psz
0x180e69120  call    cs:__imp_SysAllocString
0x180e69127  nop     dword ptr [rax+rax+00h]
0x180e6912c  mov     [rdi+1A8h], rax
0x180e69133  jmp     loc_180E69805
0x180e69138  mov     rcx, [rdi+0F0h]; this
0x180e6913f  mov     [rsp+1D0h+var_168], esi
0x180e69143  test    rcx, rcx
0x180e69146  jz      loc_180E6966B
0x180e6914c  call    ?Doc@CElement@@QEBAPEAVCDoc@@XZ; CElement::Doc(void)
0x180e69151  mov     rcx, [rdi+0F0h]; this
0x180e69158  mov     r13, rax
0x180e6915b  call    ?GetMarkupPtr@CElement@@QEBAPEAVCMarkup@@XZ; CElement::GetMarkupPtr(void)
0x180e69160  mov     r15, rax
0x180e69163  test    r13, r13
0x180e69166  jz      loc_180E6966B
0x180e6916c  test    rax, rax
0x180e6916f  jz      loc_180E6966B
0x180e69175  lea     r12, [rdi+108h]
0x180e6917c  mov     rcx, rbx; lpsz
0x180e6917f  mov     rdx, r12; pclsid
0x180e69182  call    cs:__imp_CLSIDFromString
0x180e69189  nop     dword ptr [rax+rax+00h]
0x180e6918e  lea     rbx, [r13+1530h]
0x180e69195  mov     r8, r12; struct _GUID *
0x180e69198  mov     rcx, rbx; this
0x180e6919b  lea     r9, [rsp+1D0h+var_168]; int *
0x180e691a0  mov     rdx, r13; struct CDoc *
0x180e691a3  call    ?AssignClsidID@CClassTable@@QEAAJPEAVCDoc@@AEBU_GUID@@PEAJ@Z; CClassTable::AssignClsidID(CDoc *,_GUID const &,long *)
0x180e691a8  mov     r14d, eax
0x180e691ab  test    eax, eax
0x180e691ad  js      loc_180E6966B
0x180e691b3  mov     edx, [rsp+1D0h+var_168]; int
0x180e691b7  mov     rcx, rbx; this
0x180e691ba  call    ?GetInstantClassInfo@CClassTable@@QEAAPEAUINSTANTCLASSINFO@@J@Z; CClassTable::GetInstantClassInfo(long)
0x180e691bf  mov     rbx, rax
0x180e691c2  test    rax, rax
0x180e691c5  jz      loc_180E6966B
0x180e691cb  test    dword ptr [rax+4], 400h
0x180e691d2  jnz     loc_180E6966B
0x180e691d8  mov     rcx, [rdi+0F0h]
0x180e691df  lea     rax, __vtguard
0x180e691e6  mov     [rsp+1D0h+var_170], rsi
0x180e691eb  mov     r9, [rcx]
0x180e691ee  cmp     [r9+658h], rax
0x180e691f5  jnz     loc_180E6969E
0x180e691fb  mov     rax, [r9+600h]
0x180e69202  lea     r8, [rsp+1D0h+var_170]
0x180e69207  lea     rdx, _GUID_3050f1ff_98b5_11cf_bb82_00aa00bdce0b
0x180e6920e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180e69213  test    eax, eax
0x180e69215  js      short loc_180E69264
0x180e69217  mov     rax, [rsp+1D0h+var_170]
0x180e6921c  lea     rdx, [rbx+0Ch]; struct _GUID *
0x180e69220  mov     r8d, 2; enum ExtensionValidationContexts
0x180e69226  mov     [rsp+1D0h+var_1A8], rax; struct IHTMLElement *
0x180e6922b  mov     rcx, r15; this
0x180e6922e  call    ?OnExtensionLoading@CMarkup@@QEAAJAEBU_GUID@@W4ExtensionValidationContexts@@PEAUIHTMLDocument2@@PEAV1@PEAUIHTMLElement@@@Z; CMarkup::OnExtensionLoading(_GUID const &,ExtensionValidationContexts,IHTMLDocument2 *,CMarkup *,IHTMLElement *)
0x180e69233  mov     ecx, r14d
0x180e69236  mov     r14d, 80070005h
0x180e6923c  cmp     eax, r14d
0x180e6923f  mov     eax, 80004004h
0x180e69244  cmovz   ecx, eax
0x180e69247  mov     r14d, ecx
0x180e6924a  mov     rcx, [rsp+1D0h+var_170]
0x180e6924f  mov     rax, [rcx]
0x180e69252  mov     rax, [rax+10h]
0x180e69256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180e6925b  test    r14d, r14d
0x180e6925e  js      loc_180E6966B
0x180e69264  mov     rax, [rdi+0F0h]
0x180e6926b  mov     ebx, esi
0x180e6926d  mov     esi, 1
0x180e69272  test    rax, rax
0x180e69275  jz      short loc_180E69282
0x180e69277  mov     ebx, [rax+1B0h]
0x180e6927d  shr     ebx, 19h
0x180e69280  and     ebx, esi
0x180e69282  mov     rcx, r15; this
0x180e69285  call    ?Uri@CMarkup@@QEAAPEAUIUri@@XZ; CMarkup::Uri(void)
0x180e6928a  mov     r8, rax
0x180e6928d  mov     r9d, ebx
0x180e69290  mov     edx, esi
0x180e69292  mov     rcx, r12
0x180e69295  call    cs:__imp_CoInternetExtensionAllowedForUri
0x180e6929c  nop     dword ptr [rax+rax+00h]
0x180e692a1  mov     dword ptr [rsp+1D0h+var_160], eax
0x180e692a5  mov     ebx, eax
0x180e692a7  test    eax, eax
0x180e692a9  jz      loc_180E6966B
0x180e692af  mov     rcx, r15; this
0x180e692b2  call    ?IsPendingRoot@CMarkup@@QEAA_NXZ; CMarkup::IsPendingRoot(void)
0x180e692b7  mov     rcx, r13; this
0x180e692ba  test    al, al
0x180e692bc  jz      short loc_180E692C5
0x180e692be  call    ?PendingPrimaryMarkup@CDoc@@QEBAPEAVCMarkup@@XZ; CDoc::PendingPrimaryMarkup(void)
0x180e692c3  jmp     short loc_180E692CA
0x180e692c5  call    ?PrimaryMarkup@CDoc@@QEBAPEAVCMarkup@@XZ; CDoc::PrimaryMarkup(void)
0x180e692ca  mov     r8d, 40h ; '@'; unsigned int
0x180e692d0  mov     rdx, rax; struct CMarkup *
0x180e692d3  call    ?IsPageActionAllowed@CDoc@@QEAAHPEAVCMarkup@@K@Z; CDoc::IsPageActionAllowed(CMarkup *,ulong)
0x180e692d8  xor     r13d, r13d
0x180e692db  test    eax, eax
0x180e692dd  jnz     loc_180E694EF
0x180e692e3  lea     rcx, [rbp+0D0h+pclsid]
0x180e692e7  mov     qword ptr [rbp+0D0h+pclsid.Data1], r13
0x180e692eb  call    cs:__imp_GetVersionManager
0x180e692f2  nop     dword ptr [rax+rax+00h]
0x180e692f7  mov     r13d, eax
0x180e692fa  xor     eax, eax
0x180e692fc  test    r13d, r13d
0x180e692ff  js      loc_180E694EF
0x180e69305  lea     rcx, ??_7CUString@@6B@; const CUString::`vftable'
0x180e6930c  mov     [rbp+0D0h+var_140], rax
0x180e69310  mov     [rbp+0D0h+var_148], rcx
0x180e69314  xorps   xmm0, xmm0
0x180e69317  mov     rcx, r15; this
0x180e6931a  mov     [rbp+0D0h+var_138], 0Bh
0x180e69321  movdqu  [rbp+0D0h+var_130], xmm0
0x180e69326  mov     [rbp+0D0h+var_120], eax
0x180e69329  call    ?Uri@CMarkup@@QEAAPEAUIUri@@XZ; CMarkup::Uri(void)
0x180e6932e  test    rax, rax
0x180e69331  jz      short loc_180E69342
0x180e69333  xor     r8d, r8d; enum __MIDL_IUri_0001
0x180e69336  lea     rcx, [rbp+0D0h+var_148]; this
0x180e6933a  mov     rdx, rax; struct IUri *
0x180e6933d  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x180e69342  mov     r8d, 27h ; '''; cchMax
0x180e69348  lea     rdx, [rbp+0D0h+sz]; lpsz
0x180e6934c  mov     rcx, r12; rguid
0x180e6934f  call    cs:__imp_StringFromGUID2
0x180e69356  nop     dword ptr [rax+rax+00h]
0x180e6935b  test    eax, eax
0x180e6935d  jz      loc_180E694AD
0x180e69363  mov     rax, qword ptr [rbp+0D0h+pclsid.Data1]
0x180e69367  xor     r13d, r13d
0x180e6936a  mov     [rsp+1D0h+var_170], r13
0x180e6936f  mov     [rsp+1D0h+var_158], r13
0x180e69374  mov     [rsp+1D0h+var_168], r13d
0x180e69379  mov     [rsp+1D0h+var_164], r13d
0x180e6937e  mov     rcx, [rax]
0x180e69381  mov     rbx, [rcx+18h]
0x180e69385  call    ?IsOs_Wow6432@@YA_NXZ; IsOs_Wow6432(void)
0x180e6938a  mov     r9, qword ptr [rbp+0D0h+var_130+8]
0x180e6938e  lea     rdx, [rbp+0D0h+sz]
0x180e69392  movzx   ecx, al
0x180e69395  xor     r8d, r8d
0x180e69398  lea     rax, [rsp+1D0h+var_164]
0x180e6939d  mov     [rsp+48h], rax
0x180e693a2  lea     rax, [rsp+1D0h+var_168]
0x180e693a7  mov     [rsp+1D0h+var_190], rax
0x180e693ac  lea     rax, [rsp+1D0h+var_158]
0x180e693b1  mov     [rsp+1D0h+var_198], rax
0x180e693b6  lea     rax, [rsp+1D0h+var_170]
0x180e693bb  mov     [rsp+1D0h+var_1A0], rax
0x180e693c0  mov     rax, rbx
0x180e693c3  mov     dword ptr [rsp+1D0h+var_1A8], r13d
0x180e693c8  mov     dword ptr [rsp+1D0h+var_1B0], ecx
0x180e693cc  mov     rcx, qword ptr [rbp+0D0h+pclsid.Data1]
0x180e693d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180e693d5  mov     [rbp+0D0h+var_150], eax
0x180e693d8  test    eax, eax
0x180e693da  js      loc_180E69477
0x180e693e0  mov     eax, [rsp+1D0h+var_168]
0x180e693e4  mov     dword ptr [rsp+1D0h+var_160], eax
0x180e693e8  cmp     [rsp+1D0h+var_164], r13d
0x180e693ed  jnz     loc_180E69477
0x180e693f3  mov     r13, [rsp+1D0h+var_170]
0x180e693f8  test    r13, r13
0x180e693fb  jz      short loc_180E69477
0x180e693fd  mov     rbx, [rsp+1D0h+var_158]
0x180e69402  test    rbx, rbx
0x180e69405  jz      short loc_180E6947C
0x180e69407  xor     edx, edx; Val
0x180e69409  lea     rcx, [rbp+0D0h+var_110]; void *
0x180e6940d  lea     r8d, [rdx+58h]; Size
0x180e69411  call    memset_0
0x180e69416  movups  xmm0, xmmword ptr [r12]
0x180e6941b  xor     eax, eax
0x180e6941d  mov     [rbp+0D0h+bstrString], r13
0x180e69421  lea     r9, [rbp+0D0h+var_110]; struct BLOCKED_ACTION_DETAILS *
0x180e69425  mov     [rsp+1D0h+var_170], rax
0x180e6942a  xor     edx, edx; unsigned int
0x180e6942c  mov     [rsp+1D0h+var_158], rax
0x180e69431  mov     r8d, 40000000h; unsigned int
0x180e69437  mov     [rbp+0D0h+var_C0], rbx
0x180e6943b  mov     rcx, r15; this
0x180e6943e  mov     [rbp+0D0h+var_CC], 40h ; '@'
0x180e69445  movdqu  [rbp+0D0h+var_100], xmm0
0x180e6944a  call    ?NotifyHaveProtectedUserFromUnsafeContent@@YAXPEAVCMarkup@@IKPEAUBLOCKED_ACTION_DETAILS@@@Z; NotifyHaveProtectedUserFromUnsafeContent(CMarkup *,uint,ulong,BLOCKED_ACTION_DETAILS *)
0x180e6944f  mov     rcx, [rbp+0D0h+bstrString]; bstrString
0x180e69453  call    cs:__imp_SysFreeString
0x180e6945a  nop     dword ptr [rax+rax+00h]
0x180e6945f  mov     rcx, [rbp+0D0h+var_C0]; bstrString
0x180e69463  mov     [rbp+0D0h+bstrString], 0
0x180e6946b  call    cs:__imp_SysFreeString
0x180e69472  nop     dword ptr [rax+rax+00h]
0x180e69477  mov     rbx, [rsp+1D0h+var_158]
0x180e6947c  mov     rcx, rbx; bstrString
  ... truncated ...
```
