# SplPipeline::ConfigLoader::LoadFilterCreateSequence(PrnSharedState::SharedState *,void *)

- ea: `0x140014408`
- end: `0x140014aee`
- name: `?LoadFilterCreateSequence@ConfigLoader@SplPipeline@@QEAAPEAUIPrintFilterSequence@@PEAVSharedState@PrnSharedState@@PEAX@Z`
- size: `1766`
- prototype: `struct IPrintFilterSequence *__fastcall(SplPipeline::ConfigLoader *__hidden this, struct PrnSharedState::SharedState *, void *)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140012404`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x1400084a0`
- `0x14000fa68`
- `0x1400123d8`
- `0x140013170`
- `0x140013250`
- `0x1400132e0`
- `0x140013580`
- `0x140013ce4`
- `0x140013f2c`
- `0x140014148`
- `0x140014408`
- `0x14001bdb4`
- `0x1400457b8`
- `0x1400459a4`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x140046314`
- `0x14004650c`
- `0x140056264`
- `0x14005742c`
- `0x140063010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x140014788`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x14001479f`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1400147b6`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1400147db`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x140014788`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x14001479f`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1400147b6`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1400147db`

## string_xrefs

- `0x14001458c`: `clsid`

## pseudocode

```c
struct IPrintFilterSequence *__fastcall SplPipeline::ConfigLoader::LoadFilterCreateSequence(
        SplPipeline::ConfigLoader *this,
        struct PrnSharedState::SharedState *a2,
        void *a3)
{
  _DWORD *v4; // rax
  __int64 v5; // rdx
  __int64 v6; // r14
  const wchar_t *v7; // rdx
  const char *v8; // r8
  unsigned int v9; // r9d
  wchar_t *v10; // rax
  __int64 v11; // rbx
  int v12; // eax
  int v13; // edx
  const char *v14; // r8
  unsigned int v15; // r9d
  struct __MIDL___MIDL_itf_filterpipelinei_0000_0000_0003 *v16; // r8
  wchar_t *v17; // rdi
  wchar_t *v18; // rsi
  PVOID *v19; // rcx
  PrnSharedState::LoadedModule *Module; // rbx
  HRESULT v21; // eax
  int v22; // edx
  const char *v23; // r8
  unsigned int v24; // r9d
  HRESULT v25; // eax
  int v26; // edx
  const char *v27; // r8
  unsigned int v28; // r9d
  HRESULT v29; // eax
  int v30; // edx
  const char *v31; // r8
  unsigned int v32; // r9d
  HRESULT v33; // eax
  int v34; // edx
  const char *v35; // r8
  unsigned int v36; // r9d
  const wchar_t *v37; // r9
  const wchar_t *v38; // rdx
  const char *v39; // r8
  unsigned int v40; // r9d
  wchar_t *v41; // rbx
  int v42; // edx
  const char *v43; // r8
  unsigned int v44; // r9d
  NCoreLibrary::TString *v45; // rcx
  NCoreLibrary::TString *v46; // rcx
  NCoreLibrary::TString *v47; // rcx
  NCoreLibrary::TString *v48; // rcx
  NCoreLibrary::TString *v49; // rcx
  NCoreLibrary::TString *v50; // rcx
  const struct SplException::TSystemException *v51; // r8
  const struct _GUID *v52; // r9
  const struct SplException::TSystemException *v53; // r8
  const struct _GUID *v54; // r9
  unsigned int v56; // [rsp+20h] [rbp-E0h]
  struct NCoreLibrary::TString *lpVtbl; // [rsp+28h] [rbp-D8h]
  struct NCoreLibrary::TString *v58; // [rsp+28h] [rbp-D8h]
  const struct win_musl::TStringEllipseBase *v59; // [rsp+28h] [rbp-D8h]
  HINSTANCE v60; // [rsp+30h] [rbp-D0h]
  void *v61; // [rsp+40h] [rbp-C0h] BYREF
  SplPipeline *v62; // [rsp+48h] [rbp-B8h] BYREF
  SplPipeline *v63; // [rsp+50h] [rbp-B0h] BYREF
  void *v64; // [rsp+58h] [rbp-A8h] BYREF
  LPCOLESTR v65; // [rsp+60h] [rbp-A0h] BYREF
  LPCOLESTR v66; // [rsp+68h] [rbp-98h] BYREF
  LPCOLESTR v67; // [rsp+70h] [rbp-90h] BYREF
  LPCOLESTR lpsz; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *v69; // [rsp+80h] [rbp-80h] BYREF
  struct IXMLDOMNode v70; // [rsp+88h] [rbp-78h] BYREF
  void *v71; // [rsp+90h] [rbp-70h] BYREF
  PrnSharedState::LoadedModule *v72; // [rsp+98h] [rbp-68h] BYREF
  __int64 v73; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v74; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v75; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t *String; // [rsp+B8h] [rbp-48h] BYREF
  void *v77; // [rsp+C0h] [rbp-40h]
  struct PrnSharedState::SharedState *v78; // [rsp+C8h] [rbp-38h]
  GUID v79; // [rsp+D0h] [rbp-30h] BYREF
  GUID v80; // [rsp+E0h] [rbp-20h] BYREF
  GUID v81; // [rsp+F0h] [rbp-10h] BYREF
  GUID iid; // [rsp+100h] [rbp+0h] BYREF
  GUID v83; // [rsp+110h] [rbp+10h] BYREF
  GUID v84; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v85[160]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+1D0h] [rbp+D0h] BYREF
  wchar_t v87[264]; // [rsp+270h] [rbp+170h] BYREF

  v77 = a3;
  v78 = a2;
  v75 = 0;
  v74 = 0;
  v73 = 0;
  v4 = operator new(0x38u, (const char *)a2, (unsigned int)a3);
  *(_QWORD *)&v81.Data1 = v4;
  if ( v4 )
  {
    *(_QWORD *)v4 = &NCOMLibrary::TUnknown::`vftable';
    v4[2] = 1852534389;
    v4[3] = 1;
    _InterlockedIncrement(&NCOMLibrary::TUnknown::g_cOutStandingObjectCount);
    *(_QWORD *)v4 = &TImgFilterSequenceFactoryImpl::`vftable'{for `NCOMLibrary::TUnknown'};
    *((_QWORD *)v4 + 2) = &TImgFilterSequenceFactoryImpl::`vftable'{for `IPrintFilterSequenceFactoryX'};
    std::vector<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>>::vector<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>>(v4 + 6);
    *(_QWORD *)(v5 + 48) = 0;
  }
  else
  {
    v5 = 0;
  }
  v6 = (v5 + 16) & -(__int64)(v5 != 0);
  v69 = 0;
  v75 = v6;
  PrnExcept::SmartRelease<IPartResourceDictionary>(&v69);
  v10 = PrnExcept::SysAllocString((PrnExcept *)L"Filter", v7, v8, v9);
  NCoreLibrary::TAutoPtrBSTR::operator=(&v74, v10);
  (*(void (__fastcall **)(_QWORD, __int64, __int64 *))(**(_QWORD **)this + 288LL))(*(_QWORD *)this, v74, &v73);
  v63 = 0;
  v11 = v6;
  while ( !(*(unsigned int (__fastcall **)(__int64, SplPipeline **))(*(_QWORD *)v73 + 72LL))(v73, &v63) )
  {
    v62 = 0;
    v12 = (**(__int64 (__fastcall ***)(SplPipeline *, GUID *, SplPipeline **))v63)(v63, &IID_IXMLDOMElement, &v62);
    if ( v12 < 0 )
      SplException::RealThrowFromHR((SplException *)(unsigned int)v12, v13, v14, v15);
    v69 = (wchar_t *)&NCoreLibrary::TString::gszNullState;
    lpsz = (LPCOLESTR)&NCoreLibrary::TString::gszNullState;
    v67 = (LPCOLESTR)&NCoreLibrary::TString::gszNullState;
    v66 = (LPCOLESTR)&NCoreLibrary::TString::gszNullState;
    v65 = (LPCOLESTR)&NCoreLibrary::TString::gszNullState;
    String = (wchar_t *)&NCoreLibrary::TString::gszNullState;
    v70.lpVtbl = (struct IXMLDOMNodeVtbl *)1;
    PrnExcept::GetStringAttribute(v62, L"dll", &v69, 1);
    PrnExcept::GetStringAttribute(v62, L"clsid", &lpsz, 1);
    SplPipeline::GetGuid(v62, (struct IXMLDOMNode *)&stru_14006A540, (const wchar_t *)&v67, 0, 0, lpVtbl);
    SplPipeline::GetGuid(
      v62,
      (struct IXMLDOMNode *)&stru_14006A550,
      (const wchar_t *)&v66,
      (struct NCoreLibrary::TString *)&v65,
      (struct NCoreLibrary::TString *)&String,
      v58);
    SplPipeline::GetInterleavingOptions(v63, &v70, v16);
    v17 = String;
    v18 = v69;
    v19 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_8f5f884bfc9d36094d4d0e7d631e7b2c_Traceguids);
        v19 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v19 != &WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)v19 + 7) & 0x100) != 0 && *((_BYTE *)v19 + 25) )
        {
          WPP_SF_S(v19[2], 11, WPP_8f5f884bfc9d36094d4d0e7d631e7b2c_Traceguids);
          v19 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v19 != &WPP_GLOBAL_Control )
        {
          if ( (*((_DWORD *)v19 + 7) & 0x100) != 0 && *((_BYTE *)v19 + 25) )
          {
            WPP_SF_S(v19[2], 12, WPP_8f5f884bfc9d36094d4d0e7d631e7b2c_Traceguids);
            v19 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v19 != &WPP_GLOBAL_Control )
          {
            if ( (*((_DWORD *)v19 + 7) & 0x100) != 0 && *((_BYTE *)v19 + 25) )
            {
              WPP_SF_S(v19[2], 13, WPP_8f5f884bfc9d36094d4d0e7d631e7b2c_Traceguids);
              v19 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v19 != &WPP_GLOBAL_Control )
            {
              if ( (*((_DWORD *)v19 + 7) & 0x100) != 0 && *((_BYTE *)v19 + 25) )
              {
                WPP_SF_S(v19[2], 14, WPP_8f5f884bfc9d36094d4d0e7d631e7b2c_Traceguids);
                v19 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( v19 != &WPP_GLOBAL_Control && (*((_DWORD *)v19 + 7) & 0x100) != 0 && *((_BYTE *)v19 + 25) )
                WPP_SF_S(v19[2], 15, WPP_8f5f884bfc9d36094d4d0e7d631e7b2c_Traceguids);
            }
          }
        }
      }
    }
    v84 = 0;
    v83 = 0;
    iid = 0;
    Module = 0;
    v72 = 0;
    v71 = 0;
    v21 = IIDFromString(lpsz, &iid);
    if ( v21 < 0 )
      SplException::RealThrowFromHR((SplException *)(unsigned int)v21, v22, v23, v24);
    v25 = IIDFromString(v67, &v84);
    if ( v25 < 0 )
      SplException::RealThrowFromHR((SplException *)(unsigned int)v25, v26, v27, v28);
    v29 = IIDFromString(v66, &v83);
    if ( v29 < 0 )
      SplException::RealThrowFromHR((SplException *)(unsigned int)v29, v30, v31, v32);
    if ( *v17 )
    {
      v81 = 0;
      v33 = IIDFromString(v65, &v81);
      if ( v33 < 0 )
        SplException::RealThrowFromHR((SplException *)(unsigned int)v33, v34, v35, v36);
      if ( (int)GetFullPathFromFilename(v77, v17, v87) < 0 )
      {
        SplException::THResultException::THResultException((SplException::THResultException *)v85, "-", 0);
        SplException::TSystemException::InternalInit(
          (SplException::TSystemException *)v85,
          0x80004005,
          v53,
          v54,
          v56,
          v59,
          v60);
        SplException::TSystemException::Message(
          (SplException::TSystemException *)v85,
          "custom module not found in dependent files");
        SplException::THResultException::THResultException(
          (SplException::THResultException *)pExceptionObject,
          (const struct SplException::THResultException *)v85);
        throw (SplException::THResultException *)pExceptionObject;
      }
      Module = PrnSharedState::DllManager::LoadModule(*((PrnSharedState::DllManager **)v78 + 5), v87);
      v61 = 0;
      v72 = Module;
      PrnExcept::SmartRelease<PrnSharedState::LoadedModule>(&v61);
      PrnSharedState::LoadedModule::GetObjectW(Module, &v81, &IID_IUnknown, &v71);
    }
    if ( (int)GetFullPathFromFilename(v77, v18, v87) < 0 )
    {
      SplException::THResultException::THResultException((SplException::THResultException *)v85, "-", 0);
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)v85,
        0x80004005,
        v51,
        v52,
        v56,
        v59,
        v60);
      SplException::TSystemException::Message(
        (SplException::TSystemException *)v85,
        "filter module not found in dependent files");
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)v85);
      throw (SplException::THResultException *)pExceptionObject;
    }
    *(_QWORD *)&v81.Data1 = PrnSharedState::DllManager::LoadModule(*((PrnSharedState::DllManager **)v78 + 5), v87);
    v61 = Module;
    v72 = *(PrnSharedState::LoadedModule **)&v81.Data1;
    PrnExcept::SmartRelease<PrnSharedState::LoadedModule>(&v61);
    v64 = 0;
    PrnSharedState::LoadedModule::GetObjectW(
      *(PrnSharedState::LoadedModule **)&v81.Data1,
      &iid,
      &IID_IPrintPipelineFilter,
      &v64);
    fv::AttachFilterTestHook((fv *)&v64, (struct IPrintPipelineFilter **)&iid, (const struct _GUID *)v18, v37);
    v61 = 0;
    v41 = PrnExcept::SysAllocString((PrnExcept *)v18, v38, v39, v40);
    *(_QWORD *)&v81.Data1 = v41;
    NCoreLibrary::TGenericSP<wchar_t *,NCoreLibrary::TAutoPtrBSTR,wchar_t *,0,wchar_t * const *>::Reset(&v61);
    if ( !v41 )
    {
      v61 = 0;
      SplException::RealThrowFromHR((SplException *)0x8007000ELL, v42, v43, v44);
    }
    v61 = v41;
    v11 = v6;
    v79 = v83;
    v80 = v84;
    v60 = *(HINSTANCE *)&v81.Data1;
    lpVtbl = (struct NCoreLibrary::TString *)v70.lpVtbl;
    (*(void (__fastcall **)(__int64, void *, GUID *, GUID *, void *))(*(_QWORD *)v6 + 56LL))(v6, v64, &v80, &v79, v71);
    NCoreLibrary::TGenericSP<wchar_t *,NCoreLibrary::TAutoPtrBSTR,wchar_t *,0,wchar_t * const *>::Reset(&v61);
    PrnExcept::SmartRelease<IPartResourceDictionary>(&v64);
    PrnExcept::SmartRelease<IPartResourceDictionary>(&v71);
    PrnExcept::SmartRelease<PrnSharedState::LoadedModule>(&v72);
    NCoreLibrary::TString::vFree(v45, v17);
    NCoreLibrary::TString::vFree(v46, (void *)v65);
    NCoreLibrary::TString::vFree(v47, (void *)v66);
    NCoreLibrary::TString::vFree(v48, (void *)v67);
    NCoreLibrary::TString::vFree(v49, (void *)lpsz);
    NCoreLibrary::TString::vFree(v50, v18);
    PrnExcept::SmartRelease<IPartResourceDictionary>(&v62);
    PrnExcept::SmartRelease<IPartResourceDictionary>(&v63);
  }
  v75 = 0;
  PrnExcept::SmartRelease<IPartResourceDictionary>(&v63);
  PrnExcept::SmartRelease<IPartResourceDictionary>(&v73);
  NCoreLibrary::TGenericSP<wchar_t *,NCoreLibrary::TAutoPtrBSTR,wchar_t *,0,wchar_t * const *>::Reset(&v74);
  PrnExcept::SmartRelease<IPartResourceDictionary>(&v75);
  return (struct IPrintFilterSequence *)v11;
}

```

## disassembly

```asm
0x140014408  push    rbp
0x14001440a  push    rbx
0x14001440b  push    rsi
0x14001440c  push    rdi
0x14001440d  push    r14
0x14001440f  lea     rbp, [rsp-390h]
0x140014417  sub     rsp, 490h
0x14001441e  mov     rax, cs:__security_cookie
0x140014425  xor     rax, rsp
0x140014428  mov     [rbp+3B0h+var_30], rax
0x14001442f  mov     [rbp+3B0h+var_3F0], r8
0x140014433  mov     [rbp+3B0h+var_3E8], rdx
0x140014437  mov     rbx, rcx
0x14001443a  xor     edi, edi
0x14001443c  mov     [rbp+3B0h+var_400], rdi
0x140014440  mov     [rbp+3B0h+var_408], rdi
0x140014444  mov     [rbp+3B0h+var_410], rdi
0x140014448  lea     ecx, [rdi+38h]; unsigned __int64
0x14001444b  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x140014450  mov     rdx, rax
0x140014453  mov     qword ptr [rbp+3B0h+var_3C0.Data1], rax
0x140014457  test    rax, rax
0x14001445a  jz      short loc_14001449F
0x14001445c  lea     rax, ??_7TUnknown@NCOMLibrary@@6B@; const NCOMLibrary::TUnknown::`vftable'
0x140014463  mov     [rdx], rax
0x140014466  mov     dword ptr [rdx+8], 6E6B6E75h
0x14001446d  mov     dword ptr [rdx+0Ch], 1
0x140014474  lock inc cs:?g_cOutStandingObjectCount@TUnknown@NCOMLibrary@@0JA; long NCOMLibrary::TUnknown::g_cOutStandingObjectCount
0x14001447b  lea     rax, ??_7TImgFilterSequenceFactoryImpl@@6BTUnknown@NCOMLibrary@@@; const TImgFilterSequenceFactoryImpl::`vftable'{for `NCOMLibrary::TUnknown'}
0x140014482  mov     [rdx], rax
0x140014485  lea     rax, ??_7TImgFilterSequenceFactoryImpl@@6BIPrintFilterSequenceFactoryX@@@; const TImgFilterSequenceFactoryImpl::`vftable'{for `IPrintFilterSequenceFactoryX'}
0x14001448c  mov     [rdx+10h], rax
0x140014490  lea     rcx, [rdx+18h]
0x140014494  call    ??0?$vector@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>>::vector<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>>(void)
0x140014499  mov     [rdx+30h], rdi
0x14001449d  jmp     short loc_1400144A2
0x14001449f  mov     rdx, rdi
0x1400144a2  lea     rax, [rdx+10h]
0x1400144a6  neg     rdx
0x1400144a9  sbb     r14, r14
0x1400144ac  and     r14, rax
0x1400144af  mov     [rbp+3B0h+var_430], rdi
0x1400144b3  mov     [rbp+3B0h+var_400], r14
0x1400144b7  lea     rcx, [rbp+3B0h+var_430]
0x1400144bb  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x1400144c0  lea     rcx, aFilter; "Filter"
0x1400144c7  call    ?SysAllocString@PrnExcept@@YAPEA_WPEB_WPEBDK@Z; PrnExcept::SysAllocString(wchar_t const *,char const *,ulong)
0x1400144cc  mov     rdx, rax
0x1400144cf  lea     rcx, [rbp+3B0h+var_408]
0x1400144d3  call    ??4TAutoPtrBSTR@NCoreLibrary@@QEAAPEA_WPEA_W@Z; NCoreLibrary::TAutoPtrBSTR::operator=(wchar_t *)
0x1400144d8  mov     rcx, [rbx]
0x1400144db  mov     rax, [rcx]
0x1400144de  lea     r8, [rbp+3B0h+var_410]
0x1400144e2  mov     rdx, [rbp+3B0h+var_408]
0x1400144e6  mov     rax, [rax+120h]
0x1400144ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400144f2  mov     [rsp+4B0h+var_460], rdi
0x1400144f7  mov     rbx, r14
0x1400144fa  lea     rsi, ?gszNullState@TString@NCoreLibrary@@0PA_WA; wchar_t near * NCoreLibrary::TString::gszNullState
0x140014501  mov     rcx, [rbp+3B0h+var_410]
0x140014505  mov     rax, [rcx]
0x140014508  lea     rdx, [rsp+4B0h+var_460]
0x14001450d  mov     rax, [rax+48h]
0x140014511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014516  test    eax, eax
0x140014518  jnz     loc_140014AA2
0x14001451e  mov     [rsp+4B0h+var_468], rdi
0x140014523  mov     rcx, [rsp+4B0h+var_460]
0x140014528  mov     rax, [rcx]
0x14001452b  lea     r8, [rsp+4B0h+var_468]
0x140014530  lea     rdx, IID_IXMLDOMElement
0x140014537  mov     rax, [rax]
0x14001453a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001453f  test    eax, eax
0x140014541  js      loc_140014A9A
0x140014547  mov     [rbp+3B0h+var_430], rsi
0x14001454b  mov     [rsp+4B0h+lpsz], rsi
0x140014550  mov     [rsp+4B0h+var_440], rsi
0x140014555  mov     [rsp+4B0h+var_448], rsi
0x14001455a  mov     [rsp+4B0h+var_450], rsi
0x14001455f  mov     [rbp+3B0h+String], rsi
0x140014563  mov     ebx, 1
0x140014568  mov     [rbp+3B0h+var_428.lpVtbl], rbx
0x14001456c  mov     r9d, ebx
0x14001456f  lea     r8, [rbp+3B0h+var_430]
0x140014573  lea     rdx, aDll; "dll"
0x14001457a  mov     rcx, [rsp+4B0h+var_468]
0x14001457f  call    ?GetStringAttribute@PrnExcept@@YAXPEAUIXMLDOMElement@@PEB_WPEAVTString@NCoreLibrary@@W4EGetAttrOpt@1@@Z; PrnExcept::GetStringAttribute(IXMLDOMElement *,wchar_t const *,NCoreLibrary::TString *,PrnExcept::EGetAttrOpt)
0x140014584  mov     r9d, ebx
0x140014587  lea     r8, [rsp+4B0h+lpsz]
0x14001458c  lea     rdx, aClsid; "clsid"
0x140014593  mov     rcx, [rsp+4B0h+var_468]
0x140014598  call    ?GetStringAttribute@PrnExcept@@YAXPEAUIXMLDOMElement@@PEB_WPEAVTString@NCoreLibrary@@W4EGetAttrOpt@1@@Z; PrnExcept::GetStringAttribute(IXMLDOMElement *,wchar_t const *,NCoreLibrary::TString *,PrnExcept::EGetAttrOpt)
0x14001459d  mov     [rsp+4B0h+var_490], rdi; struct NCoreLibrary::TString *
0x1400145a2  xor     r9d, r9d; struct NCoreLibrary::TString *
0x1400145a5  lea     r8, [rsp+4B0h+var_440]; wchar_t *
0x1400145aa  lea     rdx, stru_14006A540; struct IXMLDOMNode *
0x1400145b1  mov     rcx, [rsp+4B0h+var_468]; this
0x1400145b6  call    ?GetGuid@SplPipeline@@YAKPEAUIXMLDOMNode@@PEB_WPEAVTString@NCoreLibrary@@22@Z; SplPipeline::GetGuid(IXMLDOMNode *,wchar_t const *,NCoreLibrary::TString *,NCoreLibrary::TString *,NCoreLibrary::TString *)
0x1400145bb  lea     rax, [rbp+3B0h+String]
0x1400145bf  mov     [rsp+4B0h+var_490], rax; unsigned int
0x1400145c4  lea     r9, [rsp+4B0h+var_450]; struct NCoreLibrary::TString *
0x1400145c9  lea     r8, [rsp+4B0h+var_448]; wchar_t *
0x1400145ce  lea     rdx, stru_14006A550; struct IXMLDOMNode *
0x1400145d5  mov     rcx, [rsp+4B0h+var_468]; this
0x1400145da  call    ?GetGuid@SplPipeline@@YAKPEAUIXMLDOMNode@@PEB_WPEAVTString@NCoreLibrary@@22@Z; SplPipeline::GetGuid(IXMLDOMNode *,wchar_t const *,NCoreLibrary::TString *,NCoreLibrary::TString *,NCoreLibrary::TString *)
0x1400145df  lea     rdx, [rbp+3B0h+var_428]; struct IXMLDOMNode *
0x1400145e3  mov     rcx, [rsp+4B0h+var_460]; this
0x1400145e8  call    ?GetInterleavingOptions@SplPipeline@@YAXPEAUIXMLDOMNode@@PEAU__MIDL___MIDL_itf_filterpipelinei_0000_0000_0003@@@Z; SplPipeline::GetInterleavingOptions(IXMLDOMNode *,__MIDL___MIDL_itf_filterpipelinei_0000_0000_0003 *)
0x1400145ed  mov     rdi, [rbp+3B0h+String]
0x1400145f1  mov     rsi, [rbp+3B0h+var_430]
0x1400145f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400145fc  lea     rax, WPP_GLOBAL_Control
0x140014603  cmp     rcx, rax
0x140014606  jz      loc_140014761
0x14001460c  test    dword ptr [rcx+1Ch], 100h
0x140014613  jz      short loc_14001463E
0x140014615  cmp     [rcx+19h], bl
0x140014618  jb      short loc_14001463E
0x14001461a  lea     edx, [rbx+9]
0x14001461d  mov     r9, rsi
0x140014620  lea     r8, WPP_8f5f884bfc9d36094d4d0e7d631e7b2c_Traceguids
0x140014627  mov     rcx, [rcx+10h]
0x14001462b  call    WPP_SF_S
0x140014630  mov     rcx, cs:WPP_GLOBAL_Control
0x140014637  lea     rax, WPP_GLOBAL_Control
0x14001463e  cmp     rcx, rax
0x140014641  jz      loc_140014761
0x140014647  test    dword ptr [rcx+1Ch], 100h
0x14001464e  jz      short loc_14001467D
0x140014650  cmp     [rcx+19h], bl
0x140014653  jb      short loc_14001467D
0x140014655  mov     edx, 0Bh
0x14001465a  mov     r9, [rsp+4B0h+lpsz]
0x14001465f  lea     r8, WPP_8f5f884bfc9d36094d4d0e7d631e7b2c_Traceguids
0x140014666  mov     rcx, [rcx+10h]
0x14001466a  call    WPP_SF_S
0x14001466f  mov     rcx, cs:WPP_GLOBAL_Control
0x140014676  lea     rax, WPP_GLOBAL_Control
0x14001467d  cmp     rcx, rax
0x140014680  jz      loc_140014761
0x140014686  test    dword ptr [rcx+1Ch], 100h
0x14001468d  jz      short loc_1400146BC
0x14001468f  cmp     [rcx+19h], bl
0x140014692  jb      short loc_1400146BC
0x140014694  mov     edx, 0Ch
0x140014699  mov     r9, [rsp+4B0h+var_440]
0x14001469e  lea     r8, WPP_8f5f884bfc9d36094d4d0e7d631e7b2c_Traceguids
0x1400146a5  mov     rcx, [rcx+10h]
0x1400146a9  call    WPP_SF_S
0x1400146ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400146b5  lea     rax, WPP_GLOBAL_Control
0x1400146bc  cmp     rcx, rax
0x1400146bf  jz      loc_140014761
0x1400146c5  test    dword ptr [rcx+1Ch], 100h
0x1400146cc  jz      short loc_1400146FB
0x1400146ce  cmp     [rcx+19h], bl
0x1400146d1  jb      short loc_1400146FB
0x1400146d3  mov     edx, 0Dh
0x1400146d8  mov     r9, [rsp+4B0h+var_448]
0x1400146dd  lea     r8, WPP_8f5f884bfc9d36094d4d0e7d631e7b2c_Traceguids
0x1400146e4  mov     rcx, [rcx+10h]
0x1400146e8  call    WPP_SF_S
0x1400146ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400146f4  lea     rax, WPP_GLOBAL_Control
0x1400146fb  cmp     rcx, rax
0x1400146fe  jz      short loc_140014761
0x140014700  test    dword ptr [rcx+1Ch], 100h
0x140014707  jz      short loc_140014736
0x140014709  cmp     [rcx+19h], bl
0x14001470c  jb      short loc_140014736
0x14001470e  mov     edx, 0Eh
0x140014713  mov     r9, [rsp+4B0h+var_450]
0x140014718  lea     r8, WPP_8f5f884bfc9d36094d4d0e7d631e7b2c_Traceguids
0x14001471f  mov     rcx, [rcx+10h]
0x140014723  call    WPP_SF_S
0x140014728  mov     rcx, cs:WPP_GLOBAL_Control
0x14001472f  lea     rax, WPP_GLOBAL_Control
0x140014736  cmp     rcx, rax
0x140014739  jz      short loc_140014761
0x14001473b  test    dword ptr [rcx+1Ch], 100h
0x140014742  jz      short loc_140014761
0x140014744  cmp     [rcx+19h], bl
0x140014747  jb      short loc_140014761
0x140014749  mov     edx, 0Fh
0x14001474e  mov     r9, rdi
0x140014751  lea     r8, WPP_8f5f884bfc9d36094d4d0e7d631e7b2c_Traceguids
0x140014758  mov     rcx, [rcx+10h]
0x14001475c  call    WPP_SF_S
0x140014761  xorps   xmm0, xmm0
0x140014764  movups  xmmword ptr [rbp+3B0h+var_390.Data1], xmm0
0x140014768  xorps   xmm1, xmm1
0x14001476b  movups  xmmword ptr [rbp+3B0h+var_3A0.Data1], xmm1
0x14001476f  movups  xmmword ptr [rbp+3B0h+iid.Data1], xmm0
0x140014773  xor     eax, eax
0x140014775  mov     ebx, eax
0x140014777  mov     [rbp+3B0h+var_418], rax
0x14001477b  mov     [rbp+3B0h+var_420], rax
0x14001477f  lea     rdx, [rbp+3B0h+iid]; lpiid
0x140014783  mov     rcx, [rsp+4B0h+lpsz]; lpsz
0x140014788  call    cs:__imp_IIDFromString
0x14001478e  test    eax, eax
0x140014790  js      loc_140014A92
0x140014796  lea     rdx, [rbp+3B0h+var_390]; lpiid
0x14001479a  mov     rcx, [rsp+4B0h+var_440]; lpsz
0x14001479f  call    cs:__imp_IIDFromString
0x1400147a5  test    eax, eax
0x1400147a7  js      loc_140014A8A
0x1400147ad  lea     rdx, [rbp+3B0h+var_3A0]; lpiid
0x1400147b1  mov     rcx, [rsp+4B0h+var_448]; lpsz
0x1400147b6  call    cs:__imp_IIDFromString
0x1400147bc  xor     ecx, ecx
0x1400147be  test    eax, eax
0x1400147c0  js      loc_140014A82
0x1400147c6  cmp     [rdi], cx
0x1400147c9  jz      short loc_140014849
0x1400147cb  xorps   xmm0, xmm0
0x1400147ce  movups  xmmword ptr [rbp+3B0h+var_3C0.Data1], xmm0
0x1400147d2  lea     rdx, [rbp+3B0h+var_3C0]; lpiid
0x1400147d6  mov     rcx, [rsp+4B0h+var_450]; lpsz
0x1400147db  call    cs:__imp_IIDFromString
0x1400147e1  test    eax, eax
0x1400147e3  js      loc_140014A7A
0x1400147e9  lea     r8, [rbp+3B0h+var_240]; wchar_t *
0x1400147f0  mov     rdx, rdi; String
0x1400147f3  mov     rcx, [rbp+3B0h+var_3F0]; void *
0x1400147f7  call    GetFullPathFromFilename
0x1400147fc  test    eax, eax
0x1400147fe  js      loc_140014A24
0x140014804  lea     rdx, [rbp+3B0h+var_240]; wchar_t *
0x14001480b  mov     rcx, [rbp+3B0h+var_3E8]
0x14001480f  mov     rcx, [rcx+28h]; this
0x140014813  call    ?LoadModule@DllManager@PrnSharedState@@QEAAPEAVLoadedModule@2@PEB_W@Z; PrnSharedState::DllManager::LoadModule(wchar_t const *)
0x140014818  mov     rbx, rax
0x14001481b  mov     [rsp+4B0h+var_470], 0
0x140014824  mov     [rbp+3B0h+var_418], rax
0x140014828  lea     rcx, [rsp+4B0h+var_470]
0x14001482d  call    ??$SmartRelease@VLoadedModule@PrnSharedState@@@PrnExcept@@YAXPEAPEAVLoadedModule@PrnSharedState@@@Z; PrnExcept::SmartRelease<PrnSharedState::LoadedModule>(PrnSharedState::LoadedModule * *)
0x140014832  lea     r9, [rbp+3B0h+var_420]; void **
0x140014836  lea     r8, IID_IUnknown; struct _GUID *
0x14001483d  lea     rdx, [rbp+3B0h+var_3C0]; struct _GUID *
0x140014841  mov     rcx, rbx; this
0x140014844  call    ?GetObjectW@LoadedModule@PrnSharedState@@QEAAXAEBU_GUID@@0PEAPEAX@Z; PrnSharedState::LoadedModule::GetObjectW(_GUID const &,_GUID const &,void * *)
0x140014849  lea     r8, [rbp+3B0h+var_240]; wchar_t *
0x140014850  mov     rdx, rsi; String
0x140014853  mov     rcx, [rbp+3B0h+var_3F0]; void *
0x140014857  call    GetFullPathFromFilename
0x14001485c  test    eax, eax
0x14001485e  js      loc_1400149CE
0x140014864  lea     rdx, [rbp+3B0h+var_240]; wchar_t *
0x14001486b  mov     rax, [rbp+3B0h+var_3E8]
0x14001486f  mov     rcx, [rax+28h]; this
0x140014873  call    ?LoadModule@DllManager@PrnSharedState@@QEAAPEAVLoadedModule@2@PEB_W@Z; PrnSharedState::DllManager::LoadModule(wchar_t const *)
0x140014878  mov     qword ptr [rbp+3B0h+var_3C0.Data1], rax
0x14001487c  mov     [rsp+4B0h+var_470], rbx
0x140014881  mov     [rbp+3B0h+var_418], rax
0x140014885  lea     rcx, [rsp+4B0h+var_470]
0x14001488a  call    ??$SmartRelease@VLoadedModule@PrnSharedState@@@PrnExcept@@YAXPEAPEAVLoadedModule@PrnSharedState@@@Z; PrnExcept::SmartRelease<PrnSharedState::LoadedModule>(PrnSharedState::LoadedModule * *)
0x14001488f  xor     ebx, ebx
0x140014891  mov     [rsp+4B0h+var_458], rbx
0x140014896  lea     r9, [rsp+4B0h+var_458]; void **
0x14001489b  lea     r8, IID_IPrintPipelineFilter; struct _GUID *
0x1400148a2  lea     rdx, [rbp+3B0h+iid]; struct _GUID *
0x1400148a6  mov     rcx, qword ptr [rbp+3B0h+var_3C0.Data1]; this
0x1400148aa  call    ?GetObjectW@LoadedModule@PrnSharedState@@QEAAXAEBU_GUID@@0PEAPEAX@Z; PrnSharedState::LoadedModule::GetObjectW(_GUID const &,_GUID const &,void * *)
0x1400148af  mov     r8, rsi; struct _GUID *
0x1400148b2  lea     rdx, [rbp+3B0h+iid]; struct IPrintPipelineFilter **
0x1400148b6  lea     rcx, [rsp+4B0h+var_458]; this
0x1400148bb  call    ?AttachFilterTestHook@fv@@YAXPEAPEAUIPrintPipelineFilter@@AEBU_GUID@@PEB_W@Z; fv::AttachFilterTestHook(IPrintPipelineFilter * *,_GUID const &,wchar_t const *)
0x1400148c0  mov     [rsp+4B0h+var_470], rbx
0x1400148c5  mov     rcx, rsi; this
0x1400148c8  call    ?SysAllocString@PrnExcept@@YAPEA_WPEB_WPEBDK@Z; PrnExcept::SysAllocString(wchar_t const *,char const *,ulong)
0x1400148cd  mov     rbx, rax
0x1400148d0  mov     qword ptr [rbp+3B0h+var_3C0.Data1], rax
0x1400148d4  lea     rcx, [rsp+4B0h+var_470]
0x1400148d9  call    ?Reset@?$TGenericSP@PEA_WVTAutoPtrBSTR@NCoreLibrary@@PEA_W$0A@PEBQEA_W@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<wchar_t *,NCoreLibrary::TAutoPtrBSTR,wchar_t *,0,wchar_t * const *>::Reset(void)
0x1400148de  xor     eax, eax
0x1400148e0  test    rbx, rbx
0x1400148e3  jz      loc_1400149BE
0x1400148e9  mov     [rsp+4B0h+var_470], rbx
0x1400148ee  mov     rbx, r14
0x1400148f1  movaps  xmm0, xmmword ptr [rbp+3B0h+var_3A0.Data1]
0x1400148f5  movdqa  [rbp+3B0h+var_3E0], xmm0
0x1400148fa  movaps  xmm1, xmmword ptr [rbp+3B0h+var_390.Data1]
0x1400148fe  movdqa  [rbp+3B0h+var_3D0], xmm1
0x140014903  mov     rcx, [r14]
0x140014906  mov     rax, [rcx+38h]
0x14001490a  mov     rcx, qword ptr [rbp+3B0h+var_3C0.Data1]
0x14001490e  mov     [rsp+4B0h+var_480], rcx
0x140014913  mov     rcx, [rbp+3B0h+var_428.lpVtbl]
0x140014917  mov     [rsp+4B0h+var_488], rcx
0x14001491c  mov     rcx, [rbp+3B0h+var_420]
0x140014920  mov     [rsp+4B0h+var_490], rcx
0x140014925  lea     r9, [rbp+3B0h+var_3E0]
0x140014929  lea     r8, [rbp+3B0h+var_3D0]
0x14001492d  mov     rdx, [rsp+4B0h+var_458]
0x140014932  mov     rcx, r14
0x140014935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001493a  nop
0x14001493b  lea     rcx, [rsp+4B0h+var_470]
  ... truncated ...
```
