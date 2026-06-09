# CCodeLoad::OnProgress(ulong,ulong,ulong,ushort const *)

- ea: `0x180e43d10`
- end: `0x180e4459a`
- name: `?OnProgress@CCodeLoad@@UEAAJKKKPEBG@Z`
- size: `2186`
- prototype: `__int64 __fastcall(CCodeLoad *__hidden this, unsigned int, unsigned int, unsigned int, LPCOLESTR lpsz)`
- caller_count: `0`
- callee_count: `27`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000700c`
- `0x18006f7c8`
- `0x1800ad370`
- `0x1800e45d8`
- `0x1800e4964`
- `0x1800e4c70`
- `0x1800f5454`
- `0x18021f9bc`
- `0x18034a080`
- `0x180369bc0`
- `0x1804e223c`
- `0x180771400`
- `0x1808393c4`
- `0x18084da10`
- `0x18086f73c`
- `0x180e35340`
- `0x180e35af8`
- `0x180e35be4`
- `0x180e43d10`
- `0x180e4525c`
- `0x180e45318`
- `0x18105c03c`
- `0x181065a94`
- `0x181067124`
- `0x1810c2cb6`
- `0x1810c2d60`
- `0x1810d1010`

## import_xrefs

- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x180e4425d`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x180e4425d`
- `iertutil!__imp_?EDL_GetDomainFromUri@@YAJPEAUIUri@@PEAPEAG@Z` at `0x180e442e7`
- `iertutil!__imp_?EDL_GetDomainFromUri@@YAJPEAUIUri@@PEAPEAG@Z` at `0x180e442e7`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromGUID2` at `0x180e440df`
- `api-ms-win-downlevel-ole32-l1-1-0!StringFromGUID2` at `0x180e440df`
- `api-ms-win-downlevel-ole32-l1-1-0!CLSIDFromString` at `0x180e43dfa`
- `api-ms-win-downlevel-ole32-l1-1-0!CLSIDFromString` at `0x180e43f24`
- `api-ms-win-downlevel-ole32-l1-1-0!CLSIDFromString` at `0x180e43dfa`
- `api-ms-win-downlevel-ole32-l1-1-0!CLSIDFromString` at `0x180e43f24`
- `urlmon!__imp_?IECompatLogUIPIBlockedExtension@@YAXKAEBU_GUID@@PEBG@Z` at `0x180e442bc`
- `urlmon!__imp_?IECompatLogUIPIBlockedExtension@@YAXKAEBU_GUID@@PEBG@Z` at `0x180e442bc`
- `urlmon!__imp_CoInternetExtensionAllowedForUri` at `0x180e44031`
- `urlmon!__imp_CoInternetExtensionAllowedForUri` at `0x180e44031`
- `urlmon!__imp_GetVersionManager` at `0x180e44081`
- `urlmon!__imp_GetVersionManager` at `0x180e44081`
- `OLEAUT32!__imp_SysAllocString` at `0x180e43ea6`
- `OLEAUT32!__imp_SysAllocString` at `0x180e43ec8`
- `OLEAUT32!__imp_SysAllocString` at `0x180e44540`
- `OLEAUT32!__imp_SysAllocString` at `0x180e43ea6`
- `OLEAUT32!__imp_SysAllocString` at `0x180e43ec8`
- `OLEAUT32!__imp_SysAllocString` at `0x180e44540`
- `OLEAUT32!__imp_SysFreeString` at `0x180e43e9d`
- `OLEAUT32!__imp_SysFreeString` at `0x180e43ebf`
- `OLEAUT32!__imp_SysFreeString` at `0x180e441d9`
- `OLEAUT32!__imp_SysFreeString` at `0x180e441eb`
- `OLEAUT32!__imp_SysFreeString` at `0x180e441f9`
- `OLEAUT32!__imp_SysFreeString` at `0x180e4420d`
- `OLEAUT32!__imp_SysFreeString` at `0x180e443c1`
- `OLEAUT32!__imp_SysFreeString` at `0x180e44529`
- `OLEAUT32!__imp_SysFreeString` at `0x180e43e9d`
- `OLEAUT32!__imp_SysFreeString` at `0x180e43ebf`
- `OLEAUT32!__imp_SysFreeString` at `0x180e441d9`
- `OLEAUT32!__imp_SysFreeString` at `0x180e441eb`
- `OLEAUT32!__imp_SysFreeString` at `0x180e441f9`
- `OLEAUT32!__imp_SysFreeString` at `0x180e4420d`
- `OLEAUT32!__imp_SysFreeString` at `0x180e443c1`
- `OLEAUT32!__imp_SysFreeString` at `0x180e44529`

## pseudocode

```c
__int64 __fastcall CCodeLoad::OnProgress(CCodeLoad *this, __int64 a2, __int64 a3, int a4, LPCOLESTR lpsz)
{
  HRESULT v6; // r14d
  __int64 v7; // r9
  CElement *v8; // rcx
  CMarkup *WindowedMarkupContext; // rsi
  __int64 v10; // rcx
  struct IHTMLDocument2 *v11; // r9
  void (*v12)(void); // rax
  CElement *v13; // rcx
  struct CDoc *v14; // r13
  struct CMarkup *MarkupPtr; // rax
  CMarkup *v16; // r15
  __int128 *v17; // r12
  struct INSTANTCLASSINFO *InstantClassInfo; // rax
  struct INSTANTCLASSINFO *v19; // rbx
  __int64 v20; // rcx
  struct IHTMLDocument2 *v21; // r9
  int v22; // eax
  int v23; // ecx
  __int64 v24; // rax
  unsigned int v25; // ebx
  struct IUri *v26; // rax
  int v27; // ebx
  struct CMarkup *v28; // rax
  CDoc *v29; // rcx
  int VersionManager; // r13d
  struct IUri *v31; // rax
  __int64 (__fastcall *v32)(_QWORD, OLECHAR *, _QWORD, _QWORD, bool, _DWORD, BSTR *, OLECHAR **, int *, int *); // rbx
  bool v33; // al
  OLECHAR *v34; // r13
  OLECHAR *v35; // rbx
  __int128 v36; // xmm0
  struct IUri *v37; // rax
  int v38; // eax
  unsigned int v39; // esi
  int v40; // r13d
  __int64 v41; // rcx
  __int64 v42; // rbx
  bool IsPendingRoot; // al
  int v44; // ebx
  __int64 v45; // rax
  __int64 v46; // rcx
  __int128 v47; // xmm0
  __int64 v48; // rcx
  __int64 v49; // r10
  __int64 v50; // rax
  const OLECHAR *v51; // rcx
  const OLECHAR *v52; // rax
  __int64 v53; // r8
  int v54; // edx
  CCodeLoad *v55; // rcx
  int v56; // eax
  __int64 v57; // rcx
  int v58; // ecx
  int v59; // eax
  struct CMarkup *v61; // [rsp+28h] [rbp-E0h]
  BSTR v62; // [rsp+68h] [rbp-A0h] BYREF
  int v63; // [rsp+70h] [rbp-98h] BYREF
  int v64; // [rsp+74h] [rbp-94h] BYREF
  __int64 v65; // [rsp+78h] [rbp-90h] BYREF
  OLECHAR *v66; // [rsp+80h] [rbp-88h] BYREF
  int v67; // [rsp+88h] [rbp-80h]
  _QWORD v68[2]; // [rsp+90h] [rbp-78h] BYREF
  int v69; // [rsp+A0h] [rbp-68h]
  __int128 v70; // [rsp+A8h] [rbp-60h]
  int v71; // [rsp+B8h] [rbp-50h]
  _BYTE v72[16]; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v73; // [rsp+D8h] [rbp-30h]
  BSTR v74; // [rsp+100h] [rbp-8h]
  int v75; // [rsp+108h] [rbp+0h]
  int v76; // [rsp+10Ch] [rbp+4h]
  BSTR bstrString; // [rsp+110h] [rbp+8h]
  BSTR v78; // [rsp+118h] [rbp+10h]
  GUID pclsid; // [rsp+128h] [rbp+20h] BYREF
  OLECHAR sz[40]; // [rsp+138h] [rbp+30h] BYREF

  v6 = 0;
  a2 = (unsigned int)a2;
  v7 = (unsigned int)a3;
  if ( a4 == 3 )
  {
    v58 = *((_DWORD *)this + 126);
    if ( (v58 & 0x10) != 0 )
      return (unsigned int)v6;
    v59 = *((_DWORD *)this + 116);
    switch ( v59 )
    {
      case 0:
        return (unsigned int)v6;
      case 2:
        if ( (int)CURSProcessor::CancelPendingRequests(*((CURSProcessor **)this + 56)) < 0 )
        {
          v59 = *((_DWORD *)this + 116);
        }
        else
        {
          *((_DWORD *)this + 116) = 1;
          v59 = 1;
        }
        break;
      case 3:
        *((_DWORD *)this + 116) = 1;
        *((_DWORD *)this + 126) = v58 & 0xFFFFFFF7;
        goto LABEL_104;
    }
    if ( v59 != 1 )
      return (unsigned int)v6;
LABEL_104:
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
      v49 = *((_QWORD *)this + 51);
      if ( v49 )
      {
        if ( lpsz )
        {
          v50 = -1;
          do
            ++v50;
          while ( lpsz[v50] );
          v51 = &lpsz[v50];
          if ( v51 > lpsz )
          {
            do
            {
              v52 = v51 - 1;
              if ( *(v51 - 1) == 47 )
                break;
              if ( *v52 == 92 )
                break;
              --v51;
            }
            while ( v52 > lpsz );
          }
          v53 = 31;
        }
        else
        {
          v51 = 0;
          v53 = 29;
        }
        (*(void (__fastcall **)(__int64, _QWORD, __int64, __int64, const OLECHAR *, int, _DWORD, _DWORD))(*(_QWORD *)v49 + 32LL))(
          v49,
          *((unsigned int *)this + 104),
          v53,
          3,
          v51,
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
            v10 = *((_QWORD *)this + 30);
            v62 = 0;
            if ( *(__int64 (__fastcall **)())(*(_QWORD *)v10 + 1624LL) != _vtguard )
              _report_securityfailure(1);
            v6 = (*(__int64 (__fastcall **)(__int64, GUID *, BSTR *))(*(_QWORD *)v10 + 1536LL))(
                   v10,
                   &GUID_3050f1ff_98b5_11cf_bb82_00aa00bdce0b,
                   &v62);
            if ( v6 >= 0 )
            {
              v6 = CMarkup::OnExtensionLoading(
                     WindowedMarkupContext,
                     &pclsid,
                     ExtensionValidationContextParsed,
                     v11,
                     v61,
                     (struct IHTMLElement *)v62);
              v12 = *(void (**)(void))(*(_QWORD *)v62 + 16LL);
LABEL_16:
              v12();
              return (unsigned int)v6;
            }
          }
          break;
      }
      return (unsigned int)v6;
    }
    v13 = (CElement *)*((_QWORD *)this + 30);
    v63 = 0;
    if ( !v13 )
      goto LABEL_78;
    v14 = CElement::Doc(v13);
    MarkupPtr = CElement::GetMarkupPtr(*((CElement **)this + 30));
    v16 = MarkupPtr;
    if ( !v14 )
      goto LABEL_78;
    if ( !MarkupPtr )
      goto LABEL_78;
    v17 = (__int128 *)((char *)this + 264);
    CLSIDFromString(lpsz, (LPCLSID)((char *)this + 264));
    v6 = CClassTable::AssignClsidID(
           (struct CDoc *)((char *)v14 + 5424),
           v14,
           (const struct _GUID *)((char *)this + 264),
           &v63);
    if ( v6 < 0 )
      goto LABEL_78;
    InstantClassInfo = CClassTable::GetInstantClassInfo((struct CDoc *)((char *)v14 + 5424), v63);
    v19 = InstantClassInfo;
    if ( !InstantClassInfo || (*((_DWORD *)InstantClassInfo + 1) & 0x400) != 0 )
      goto LABEL_78;
    v20 = *((_QWORD *)this + 30);
    v62 = 0;
    if ( *(__int64 (__fastcall **)())(*(_QWORD *)v20 + 1624LL) != _vtguard )
      _report_securityfailure(1);
    if ( (*(int (__fastcall **)(__int64, GUID *, BSTR *))(*(_QWORD *)v20 + 1536LL))(
           v20,
           &GUID_3050f1ff_98b5_11cf_bb82_00aa00bdce0b,
           &v62) >= 0 )
    {
      v22 = CMarkup::OnExtensionLoading(
              v16,
              (const struct _GUID *)((char *)v19 + 12),
              ExtensionValidationContextParsed,
              v21,
              v61,
              (struct IHTMLElement *)v62);
      v23 = v6;
      if ( v22 == -2147024891 )
        v23 = -2147467260;
      v6 = v23;
      (*(void (__fastcall **)(BSTR))(*(_QWORD *)v62 + 16LL))(v62);
      if ( v6 < 0 )
        goto LABEL_78;
    }
    v24 = *((_QWORD *)this + 30);
    v25 = 0;
    if ( v24 )
      v25 = (*(_DWORD *)(v24 + 432) >> 25) & 1;
    v26 = CMarkup::Uri(v16);
    LODWORD(v65) = CoInternetExtensionAllowedForUri((char *)this + 264, 1, v26, v25);
    v27 = v65;
    if ( !(_DWORD)v65 )
      goto LABEL_78;
    if ( CMarkup::IsPendingRoot(v16) )
      v28 = CDoc::PendingPrimaryMarkup(v14);
    else
      v28 = CDoc::PrimaryMarkup(v14);
    if ( CDoc::IsPageActionAllowed(v29, v28, 0x40u)
      || (*(_QWORD *)&pclsid.Data1 = 0, VersionManager = GetVersionManager(&pclsid), VersionManager < 0) )
    {
LABEL_53:
      if ( !IsProtectedModeProcess()
        && v27
        && (unsigned int)Ext_IsIEExtCompatible((const struct _GUID *)((char *)this + 264), 0, 0, v7) == 1 )
      {
        if ( g_cmptlgs == 1
          || !(unsigned int)IECompatLoggingEnabled()
          || g_cmptlgs == 1
          || !(unsigned int)IECompatLoggingEnabled() )
        {
          goto LABEL_78;
        }
        v6 = -2147467260;
        IECompatLogUIPIBlockedExtension(1u, (const struct _GUID *)((char *)this + 264), 0);
      }
      if ( v6 >= 0 )
      {
        v62 = 0;
        v37 = CMarkup::Uri(v16);
        if ( v37 )
          EDL_GetDomainFromUri(v37, &v62);
        LODWORD(v65) = 0;
        v64 = 0;
        v38 = IsPendingApproval(
                (const struct _GUID *)((char *)this + 264),
                v16,
                v62,
                (enum TYPE_APPROVAL_NEEDED *)&v64,
                (enum FLAG_CONTENTFILTERSTATE *)&v65);
        v39 = v65;
        v40 = v38;
        if ( (_DWORD)v65 )
        {
          v41 = *((_QWORD *)v16 + 40);
          if ( v41 )
          {
            v42 = *(_QWORD *)(v41 + 16);
            if ( v42 )
            {
              IsPendingRoot = CMarkup::IsPendingRoot(v16);
              CDoc::SetActiveXFilterUI(v42, v39, IsPendingRoot);
            }
          }
        }
        if ( v40 )
        {
          v44 = v64;
          if ( v64 != 3 )
          {
            v45 = *((_QWORD *)v16 + 40);
            v46 = 0;
            if ( v45 )
              v46 = *(_QWORD *)(v45 + 16);
            if ( (*(_DWORD *)(v46 + 4896) & 0x40000) == 0 )
            {
              memset_0(v72, 0, 0x58u);
              v47 = *v17;
              v75 = v44;
              v74 = v62;
              v73 = v47;
              NotifyHaveProtectedUserFromUnsafeContent(v16, 0, 0x40000u, (struct BLOCKED_ACTION_DETAILS *)v72);
            }
          }
          v6 = -2147467260;
        }
        if ( v62 )
          SysFreeString(v62);
        if ( v6 >= 0 )
          return (unsigned int)v6;
      }
LABEL_78:
      v48 = *((_QWORD *)this + 28);
      v6 = -2147467260;
      if ( v48 )
      {
        (*(void (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v48 + 24LL))(v48, a2, a3, v7);
        TSmartPointer<CTransitionClient>::~TSmartPointer<CTransitionClient>((char *)this + 224);
      }
      return (unsigned int)v6;
    }
    v68[1] = 0;
    v68[0] = &CUString::`vftable';
    v69 = 11;
    v70 = 0;
    v71 = 0;
    v31 = CMarkup::Uri(v16);
    if ( v31 )
      CUString::Set((CUString *)v68, v31, Uri_PROPERTY_ABSOLUTE_URI);
    if ( !StringFromGUID2((const GUID *const)((char *)this + 264), sz, 39) )
    {
LABEL_50:
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&pclsid.Data1 + 16LL))(*(_QWORD *)&pclsid.Data1);
      *(_QWORD *)&pclsid.Data1 = 0;
      v68[0] = &CUString::`vftable';
      CUString::Set((CUString *)v68, 0, Uri_PROPERTY_RAW_URI);
      if ( VersionManager >= 0 && !v27 )
        v6 = -2147467260;
      goto LABEL_53;
    }
    v62 = 0;
    v66 = 0;
    v63 = 0;
    v64 = 0;
    v32 = *(__int64 (__fastcall **)(_QWORD, OLECHAR *, _QWORD, _QWORD, bool, _DWORD, BSTR *, OLECHAR **, int *, int *))(**(_QWORD **)&pclsid.Data1 + 24LL);
    v33 = IsOs_Wow6432();
    v67 = v32(*(_QWORD *)&pclsid.Data1, sz, 0, *((_QWORD *)&v70 + 1), v33, 0, &v62, &v66, &v63, &v64);
    if ( v67 >= 0 )
    {
      LODWORD(v65) = v63;
      if ( !v64 )
      {
        v34 = v62;
        if ( v62 )
        {
          v35 = v66;
          if ( !v66 )
          {
LABEL_49:
            SysFreeString(v35);
            v66 = 0;
            SysFreeString(v62);
            v27 = v65;
            VersionManager = v67;
            goto LABEL_50;
          }
          memset_0(v72, 0, 0x58u);
          v36 = *v17;
          bstrString = v34;
          v62 = 0;
          v66 = 0;
          v78 = v35;
          v76 = 64;
          v73 = v36;
          NotifyHaveProtectedUserFromUnsafeContent(v16, 0, 0x40000000u, (struct BLOCKED_ACTION_DETAILS *)v72);
          SysFreeString(bstrString);
          bstrString = 0;
          SysFreeString(v78);
        }
      }
    }
    v35 = v66;
    goto LABEL_49;
  }
  v54 = *((_DWORD *)this + 116);
  v55 = (CCodeLoad *)((char *)this - 24);
  v56 = *((_DWORD *)this + 126) | 4;
  *((_DWORD *)this + 126) = v56;
  if ( v54 == 3 )
  {
    if ( (v56 & 8) != 0 )
    {
      v57 = *((_QWORD *)this + 28);
      if ( v57 )
      {
        v12 = *(void (**)(void))(*(_QWORD *)v57 + 24LL);
        goto LABEL_16;
      }
    }
  }
  else if ( v54 == 1 )
  {
    CCodeLoad::_ReleaseMalwareObjects(v55);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180e43d10  mov     rax, rsp
0x180e43d13  mov     [rax+20h], r9d
0x180e43d17  mov     [rax+18h], r8d
0x180e43d1b  mov     [rax+10h], edx
0x180e43d1e  mov     [rax+8], rcx
0x180e43d22  push    rbp
0x180e43d23  push    rbx
0x180e43d24  push    rsi
0x180e43d25  push    rdi
0x180e43d26  push    r12
0x180e43d28  push    r13
0x180e43d2a  push    r14
0x180e43d2c  push    r15
0x180e43d2e  lea     rbp, [rax-0D8h]
0x180e43d35  sub     rsp, 198h
0x180e43d3c  mov     rax, cs:__security_cookie
0x180e43d43  xor     rax, rsp
0x180e43d46  mov     [rbp+0D0h+var_50], rax
0x180e43d4d  mov     eax, [rbp+0D0h+arg_18]
0x180e43d53  xor     esi, esi
0x180e43d55  mov     rdi, [rbp+0D0h+arg_0]
0x180e43d5c  mov     r14d, esi
0x180e43d5f  mov     edx, [rbp+0D0h+arg_8]
0x180e43d65  mov     r9d, [rbp+0D0h+arg_10]
0x180e43d6c  mov     rbx, [rbp+0D0h+lpsz]
0x180e43d73  lea     r11d, [rsi+3]
0x180e43d77  sub     eax, r11d
0x180e43d7a  jz      loc_180E444E7
0x180e43d80  sub     eax, 1
0x180e43d83  jz      loc_180E44495
0x180e43d89  sub     eax, 1
0x180e43d8c  jz      loc_180E4440E
0x180e43d92  sub     eax, 2
0x180e43d95  jz      loc_180E4440E
0x180e43d9b  sub     eax, 1
0x180e43d9e  jz      loc_180E4440E
0x180e43da4  sub     eax, 4
0x180e43da7  jz      loc_180E43EDA
0x180e43dad  sub     eax, 27h ; '''
0x180e43db0  jz      loc_180E43EB8
0x180e43db6  sub     eax, 1
0x180e43db9  jz      loc_180E43E96
0x180e43dbf  cmp     eax, 10h
0x180e43dc2  jnz     loc_180E44556
0x180e43dc8  mov     rcx, [rdi+0F0h]; this
0x180e43dcf  test    rcx, rcx
0x180e43dd2  jz      loc_180E43E8B
0x180e43dd8  call    ?GetWindowedMarkupContext@CElement@@UEBAPEAVCMarkup@@XZ; CElement::GetWindowedMarkupContext(void)
0x180e43ddd  xor     r15d, r15d
0x180e43de0  mov     rsi, rax
0x180e43de3  test    rax, rax
0x180e43de6  jz      loc_180E43E8B
0x180e43dec  xorps   xmm0, xmm0
0x180e43def  lea     rdx, [rbp+0D0h+pclsid]; pclsid
0x180e43df3  mov     rcx, rbx; lpsz
0x180e43df6  movups  xmmword ptr [rbp+0D0h+pclsid.Data1], xmm0
0x180e43dfa  call    cs:__imp_CLSIDFromString
0x180e43e00  mov     r14d, eax
0x180e43e03  test    eax, eax
0x180e43e05  js      loc_180E44556
0x180e43e0b  mov     rcx, [rdi+0F0h]
0x180e43e12  lea     rax, __vtguard
0x180e43e19  mov     [rsp+1D0h+var_170], r15
0x180e43e1e  mov     r9, [rcx]
0x180e43e21  cmp     [r9+658h], rax
0x180e43e28  jnz     short loc_180E43E80
0x180e43e2a  mov     rax, [r9+600h]
0x180e43e31  lea     r8, [rsp+1D0h+var_170]
0x180e43e36  lea     rdx, _GUID_3050f1ff_98b5_11cf_bb82_00aa00bdce0b
0x180e43e3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180e43e42  mov     r14d, eax
0x180e43e45  test    eax, eax
0x180e43e47  js      loc_180E44556
0x180e43e4d  mov     rax, [rsp+1D0h+var_170]
0x180e43e52  lea     r8d, [r15+2]; enum ExtensionValidationContexts
0x180e43e56  lea     rdx, [rbp+0D0h+pclsid]; struct _GUID *
0x180e43e5a  mov     [rsp+1D0h+var_1A8], rax; struct IHTMLElement *
0x180e43e5f  mov     rcx, rsi; this
0x180e43e62  call    ?OnExtensionLoading@CMarkup@@QEAAJAEBU_GUID@@W4ExtensionValidationContexts@@PEAUIHTMLDocument2@@PEAV1@PEAUIHTMLElement@@@Z; CMarkup::OnExtensionLoading(_GUID const &,ExtensionValidationContexts,IHTMLDocument2 *,CMarkup *,IHTMLElement *)
0x180e43e67  mov     rcx, [rsp+1D0h+var_170]
0x180e43e6c  mov     r14d, eax
0x180e43e6f  mov     rax, [rcx]
0x180e43e72  mov     rax, [rax+10h]
0x180e43e76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180e43e7b  jmp     loc_180E44556
0x180e43e80  mov     ecx, 1
0x180e43e85  call    __report_securityfailure
0x180e43e8b  mov     r14d, 80070005h
0x180e43e91  jmp     loc_180E44556
0x180e43e96  mov     rcx, [rdi+1B0h]; bstrString
0x180e43e9d  call    cs:__imp_SysFreeString
0x180e43ea3  mov     rcx, rbx; psz
0x180e43ea6  call    cs:__imp_SysAllocString
0x180e43eac  mov     [rdi+1B0h], rax
0x180e43eb3  jmp     loc_180E44556
0x180e43eb8  mov     rcx, [rdi+1A8h]; bstrString
0x180e43ebf  call    cs:__imp_SysFreeString
0x180e43ec5  mov     rcx, rbx; psz
0x180e43ec8  call    cs:__imp_SysAllocString
0x180e43ece  mov     [rdi+1A8h], rax
0x180e43ed5  jmp     loc_180E44556
0x180e43eda  mov     rcx, [rdi+0F0h]; this
0x180e43ee1  mov     [rsp+1D0h+var_168], esi
0x180e43ee5  test    rcx, rcx
0x180e43ee8  jz      loc_180E443D0
0x180e43eee  call    ?Doc@CElement@@QEBAPEAVCDoc@@XZ; CElement::Doc(void)
0x180e43ef3  mov     rcx, [rdi+0F0h]; this
0x180e43efa  mov     r13, rax
0x180e43efd  call    ?GetMarkupPtr@CElement@@QEBAPEAVCMarkup@@XZ; CElement::GetMarkupPtr(void)
0x180e43f02  mov     r15, rax
0x180e43f05  test    r13, r13
0x180e43f08  jz      loc_180E443D0
0x180e43f0e  test    rax, rax
0x180e43f11  jz      loc_180E443D0
0x180e43f17  lea     r12, [rdi+108h]
0x180e43f1e  mov     rcx, rbx; lpsz
0x180e43f21  mov     rdx, r12; pclsid
0x180e43f24  call    cs:__imp_CLSIDFromString
0x180e43f2a  lea     rbx, [r13+1530h]
0x180e43f31  mov     r8, r12; struct _GUID *
0x180e43f34  mov     rcx, rbx; this
0x180e43f37  lea     r9, [rsp+1D0h+var_168]; int *
0x180e43f3c  mov     rdx, r13; struct CDoc *
0x180e43f3f  call    ?AssignClsidID@CClassTable@@QEAAJPEAVCDoc@@AEBU_GUID@@PEAJ@Z; CClassTable::AssignClsidID(CDoc *,_GUID const &,long *)
0x180e43f44  mov     r14d, eax
0x180e43f47  test    eax, eax
0x180e43f49  js      loc_180E443D0
0x180e43f4f  mov     edx, [rsp+1D0h+var_168]; int
0x180e43f53  mov     rcx, rbx; this
0x180e43f56  call    ?GetInstantClassInfo@CClassTable@@QEAAPEAUINSTANTCLASSINFO@@J@Z; CClassTable::GetInstantClassInfo(long)
0x180e43f5b  mov     rbx, rax
0x180e43f5e  test    rax, rax
0x180e43f61  jz      loc_180E443D0
0x180e43f67  test    dword ptr [rax+4], 400h
0x180e43f6e  jnz     loc_180E443D0
0x180e43f74  mov     rcx, [rdi+0F0h]
0x180e43f7b  lea     rax, __vtguard
0x180e43f82  mov     [rsp+1D0h+var_170], rsi
0x180e43f87  mov     r9, [rcx]
0x180e43f8a  cmp     [r9+658h], rax
0x180e43f91  jnz     loc_180E44403
0x180e43f97  mov     rax, [r9+600h]
0x180e43f9e  lea     r8, [rsp+1D0h+var_170]
0x180e43fa3  lea     rdx, _GUID_3050f1ff_98b5_11cf_bb82_00aa00bdce0b
0x180e43faa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180e43faf  test    eax, eax
0x180e43fb1  js      short loc_180E44000
0x180e43fb3  mov     rax, [rsp+1D0h+var_170]
0x180e43fb8  lea     rdx, [rbx+0Ch]; struct _GUID *
0x180e43fbc  mov     r8d, 2; enum ExtensionValidationContexts
0x180e43fc2  mov     [rsp+1D0h+var_1A8], rax; struct IHTMLElement *
0x180e43fc7  mov     rcx, r15; this
0x180e43fca  call    ?OnExtensionLoading@CMarkup@@QEAAJAEBU_GUID@@W4ExtensionValidationContexts@@PEAUIHTMLDocument2@@PEAV1@PEAUIHTMLElement@@@Z; CMarkup::OnExtensionLoading(_GUID const &,ExtensionValidationContexts,IHTMLDocument2 *,CMarkup *,IHTMLElement *)
0x180e43fcf  mov     ecx, r14d
0x180e43fd2  mov     r14d, 80070005h
0x180e43fd8  cmp     eax, r14d
0x180e43fdb  mov     eax, 80004004h
0x180e43fe0  cmovz   ecx, eax
0x180e43fe3  mov     r14d, ecx
0x180e43fe6  mov     rcx, [rsp+1D0h+var_170]
0x180e43feb  mov     rax, [rcx]
0x180e43fee  mov     rax, [rax+10h]
0x180e43ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180e43ff7  test    r14d, r14d
0x180e43ffa  js      loc_180E443D0
0x180e44000  mov     rax, [rdi+0F0h]
0x180e44007  mov     ebx, esi
0x180e44009  mov     esi, 1
0x180e4400e  test    rax, rax
0x180e44011  jz      short loc_180E4401E
0x180e44013  mov     ebx, [rax+1B0h]
0x180e44019  shr     ebx, 19h
0x180e4401c  and     ebx, esi
0x180e4401e  mov     rcx, r15; this
0x180e44021  call    ?Uri@CMarkup@@QEAAPEAUIUri@@XZ; CMarkup::Uri(void)
0x180e44026  mov     r8, rax
0x180e44029  mov     r9d, ebx
0x180e4402c  mov     edx, esi
0x180e4402e  mov     rcx, r12
0x180e44031  call    cs:__imp_CoInternetExtensionAllowedForUri
0x180e44037  mov     dword ptr [rsp+1D0h+var_160], eax
0x180e4403b  mov     ebx, eax
0x180e4403d  test    eax, eax
0x180e4403f  jz      loc_180E443D0
0x180e44045  mov     rcx, r15; this
0x180e44048  call    ?IsPendingRoot@CMarkup@@QEAA_NXZ; CMarkup::IsPendingRoot(void)
0x180e4404d  mov     rcx, r13; this
0x180e44050  test    al, al
0x180e44052  jz      short loc_180E4405B
0x180e44054  call    ?PendingPrimaryMarkup@CDoc@@QEBAPEAVCMarkup@@XZ; CDoc::PendingPrimaryMarkup(void)
0x180e44059  jmp     short loc_180E44060
0x180e4405b  call    ?PrimaryMarkup@CDoc@@QEBAPEAVCMarkup@@XZ; CDoc::PrimaryMarkup(void)
0x180e44060  mov     r8d, 40h ; '@'; unsigned int
0x180e44066  mov     rdx, rax; struct CMarkup *
0x180e44069  call    ?IsPageActionAllowed@CDoc@@QEAAHPEAVCMarkup@@K@Z; CDoc::IsPageActionAllowed(CMarkup *,ulong)
0x180e4406e  xor     r13d, r13d
0x180e44071  test    eax, eax
0x180e44073  jnz     loc_180E4425D
0x180e44079  lea     rcx, [rbp+0D0h+pclsid]
0x180e4407d  mov     qword ptr [rbp+0D0h+pclsid.Data1], r13
0x180e44081  call    cs:__imp_GetVersionManager
0x180e44087  mov     r13d, eax
0x180e4408a  xor     eax, eax
0x180e4408c  test    r13d, r13d
0x180e4408f  js      loc_180E4425D
0x180e44095  lea     rcx, ??_7CUString@@6B@; const CUString::`vftable'
0x180e4409c  mov     [rbp+0D0h+var_140], rax
0x180e440a0  mov     [rbp+0D0h+var_148], rcx
0x180e440a4  xorps   xmm0, xmm0
0x180e440a7  mov     rcx, r15; this
0x180e440aa  mov     [rbp+0D0h+var_138], 0Bh
0x180e440b1  movdqu  [rbp+0D0h+var_130], xmm0
0x180e440b6  mov     [rbp+0D0h+var_120], eax
0x180e440b9  call    ?Uri@CMarkup@@QEAAPEAUIUri@@XZ; CMarkup::Uri(void)
0x180e440be  test    rax, rax
0x180e440c1  jz      short loc_180E440D2
0x180e440c3  xor     r8d, r8d; enum __MIDL_IUri_0001
0x180e440c6  lea     rcx, [rbp+0D0h+var_148]; this
0x180e440ca  mov     rdx, rax; struct IUri *
0x180e440cd  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x180e440d2  mov     r8d, 27h ; '''; cchMax
0x180e440d8  lea     rdx, [rbp+0D0h+sz]; lpsz
0x180e440dc  mov     rcx, r12; rguid
0x180e440df  call    cs:__imp_StringFromGUID2
0x180e440e5  test    eax, eax
0x180e440e7  jz      loc_180E4421B
0x180e440ed  mov     rax, qword ptr [rbp+0D0h+pclsid.Data1]
0x180e440f1  xor     r13d, r13d
0x180e440f4  mov     [rsp+1D0h+var_170], r13
0x180e440f9  mov     [rsp+1D0h+var_158], r13
0x180e440fe  mov     [rsp+1D0h+var_168], r13d
0x180e44103  mov     [rsp+1D0h+var_164], r13d
0x180e44108  mov     rcx, [rax]
0x180e4410b  mov     rbx, [rcx+18h]
0x180e4410f  call    ?IsOs_Wow6432@@YA_NXZ; IsOs_Wow6432(void)
0x180e44114  mov     r9, qword ptr [rbp+0D0h+var_130+8]
0x180e44118  lea     rdx, [rbp+0D0h+sz]
0x180e4411c  movzx   ecx, al
0x180e4411f  xor     r8d, r8d
0x180e44122  lea     rax, [rsp+1D0h+var_164]
0x180e44127  mov     [rsp+48h], rax
0x180e4412c  lea     rax, [rsp+1D0h+var_168]
0x180e44131  mov     [rsp+1D0h+var_190], rax
0x180e44136  lea     rax, [rsp+1D0h+var_158]
0x180e4413b  mov     [rsp+1D0h+var_198], rax
0x180e44140  lea     rax, [rsp+1D0h+var_170]
0x180e44145  mov     [rsp+1D0h+var_1A0], rax
0x180e4414a  mov     rax, rbx
0x180e4414d  mov     dword ptr [rsp+1D0h+var_1A8], r13d
0x180e44152  mov     dword ptr [rsp+1D0h+var_1B0], ecx
0x180e44156  mov     rcx, qword ptr [rbp+0D0h+pclsid.Data1]
0x180e4415a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180e4415f  mov     [rbp+0D0h+var_150], eax
0x180e44162  test    eax, eax
0x180e44164  js      loc_180E441F1
0x180e4416a  mov     eax, [rsp+1D0h+var_168]
0x180e4416e  mov     dword ptr [rsp+1D0h+var_160], eax
0x180e44172  cmp     [rsp+1D0h+var_164], r13d
0x180e44177  jnz     short loc_180E441F1
0x180e44179  mov     r13, [rsp+1D0h+var_170]
0x180e4417e  test    r13, r13
0x180e44181  jz      short loc_180E441F1
0x180e44183  mov     rbx, [rsp+1D0h+var_158]
0x180e44188  test    rbx, rbx
0x180e4418b  jz      short loc_180E441F6
0x180e4418d  xor     edx, edx; Val
0x180e4418f  lea     rcx, [rbp+0D0h+var_110]; void *
0x180e44193  lea     r8d, [rdx+58h]; Size
0x180e44197  call    memset_0
0x180e4419c  movups  xmm0, xmmword ptr [r12]
0x180e441a1  xor     eax, eax
0x180e441a3  mov     [rbp+0D0h+bstrString], r13
0x180e441a7  lea     r9, [rbp+0D0h+var_110]; struct BLOCKED_ACTION_DETAILS *
0x180e441ab  mov     [rsp+1D0h+var_170], rax
0x180e441b0  xor     edx, edx; unsigned int
0x180e441b2  mov     [rsp+1D0h+var_158], rax
0x180e441b7  mov     r8d, 40000000h; unsigned int
0x180e441bd  mov     [rbp+0D0h+var_C0], rbx
0x180e441c1  mov     rcx, r15; this
0x180e441c4  mov     [rbp+0D0h+var_CC], 40h ; '@'
0x180e441cb  movdqu  [rbp+0D0h+var_100], xmm0
0x180e441d0  call    ?NotifyHaveProtectedUserFromUnsafeContent@@YAXPEAVCMarkup@@IKPEAUBLOCKED_ACTION_DETAILS@@@Z; NotifyHaveProtectedUserFromUnsafeContent(CMarkup *,uint,ulong,BLOCKED_ACTION_DETAILS *)
0x180e441d5  mov     rcx, [rbp+0D0h+bstrString]; bstrString
0x180e441d9  call    cs:__imp_SysFreeString
0x180e441df  mov     rcx, [rbp+0D0h+var_C0]; bstrString
0x180e441e3  mov     [rbp+0D0h+bstrString], 0
0x180e441eb  call    cs:__imp_SysFreeString
0x180e441f1  mov     rbx, [rsp+1D0h+var_158]
0x180e441f6  mov     rcx, rbx; bstrString
0x180e441f9  call    cs:__imp_SysFreeString
0x180e441ff  mov     rcx, [rsp+1D0h+var_170]; bstrString
0x180e44204  mov     [rsp+1D0h+var_158], 0
0x180e4420d  call    cs:__imp_SysFreeString
0x180e44213  mov     ebx, dword ptr [rsp+1D0h+var_160]
0x180e44217  mov     r13d, [rbp+0D0h+var_150]
0x180e4421b  mov     rcx, qword ptr [rbp+0D0h+pclsid.Data1]
0x180e4421f  mov     rax, [rcx]
0x180e44222  mov     rax, [rax+10h]
0x180e44226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180e4422b  xor     edx, edx; struct IUri *
  ... truncated ...
```
