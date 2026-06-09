# SplPipeline::SplFilterPipelineCallObject::SetupPipeline(ulong,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,int,unsigned __int64)

- ea: `0x140012404`
- end: `0x140013148`
- name: `?SetupPipeline@SplFilterPipelineCallObject@SplPipeline@@AEAAXKPEB_W00000H_K@Z`
- size: `3396`
- prototype: `void __fastcall(SplPipeline::SplFilterPipelineCallObject *this, const wchar_t *, wchar_t *, wchar_t *, WCHAR *, LPWSTR pPrinterName, wchar_t *, wchar_t *, unsigned int, unsigned __int64)`
- caller_count: `1`
- callee_count: `48`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140010630`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x140005358`
- `0x140005470`
- `0x1400071e8`
- `0x140007ce0`
- `0x1400086f8`
- `0x140009848`
- `0x14000d494`
- `0x14000ea50`
- `0x14000f9fc`
- `0x14000fa1c`
- `0x14000fa68`
- `0x14000fa98`
- `0x14000fac4`
- `0x14000fb28`
- `0x14000fb90`
- `0x140010148`
- `0x140010460`
- `0x1400109d8`
- `0x140010f4c`
- `0x1400111f8`
- `0x140011310`
- `0x140011574`
- `0x140011844`
- `0x140011a00`
- `0x140012404`
- `0x1400132e0`
- `0x140013a40`
- `0x140014408`
- `0x140014af4`
- `0x140014e8c`
- `0x14001528c`
- `0x140015dcc`
- `0x140016714`
- `0x140016a50`
- `0x14001782c`
- `0x14001a1a8`
- `0x14001aa2c`
- `0x14001d254`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x140046314`
- `0x14004650c`
- `0x14005c024`
- `0x140063010`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x140012842`
- `ADVAPI32!OpenThreadToken` at `0x140012863`
- `ADVAPI32!OpenThreadToken` at `0x140012842`
- `ADVAPI32!OpenThreadToken` at `0x140012863`
- `KERNEL32!CreateEventW` at `0x140012716`
- `KERNEL32!CreateEventW` at `0x140012716`
- `KERNEL32!GetCurrentThread` at `0x1400127ea`
- `KERNEL32!GetCurrentThread` at `0x14001280a`
- `KERNEL32!GetCurrentThread` at `0x14001282b`
- `KERNEL32!GetCurrentThread` at `0x140012850`
- `KERNEL32!GetCurrentThread` at `0x1400127ea`
- `KERNEL32!GetCurrentThread` at `0x14001280a`
- `KERNEL32!GetCurrentThread` at `0x14001282b`
- `KERNEL32!GetCurrentThread` at `0x140012850`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1400128b9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140012c4f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1400128b9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140012c4f`
- `WINSPOOL!OpenPrinterW` at `0x140012763`
- `WINSPOOL!OpenPrinterW` at `0x1400127ae`
- `WINSPOOL!OpenPrinterW` at `0x1400127c8`
- `WINSPOOL!OpenPrinterW` at `0x140012763`
- `WINSPOOL!OpenPrinterW` at `0x1400127ae`
- `WINSPOOL!OpenPrinterW` at `0x1400127c8`
- `WINSPOOL!StartDocPrinterW` at `0x140012c3d`
- `WINSPOOL!StartDocPrinterW` at `0x140012c3d`

## string_xrefs

- `0x140012de0`: `CreateEvent failed`
- `0x140012e38`: `OpenPrinter m_hPrinterForFilters failed`
- `0x140012e90`: `OpenPrinter port failed`
- `0x140012ee8`: `OpenPrinter read failed`
- `0x140012d88`: `OpenThreadToken failed`
- `0x140012f48`: `OpenThreadToken failed`
- `0x140012fa0`: `OpenThreadToken failed`
- `0x140012ff8`: `OpenThreadToken failed`
- `0x140013085`: `Unsupported OpenXPS Conversion.`
- `0x140012b5e`: `OpenXPS`

## pseudocode

```c
void __fastcall SplPipeline::SplFilterPipelineCallObject::SetupPipeline(
        SplPipeline::SplFilterPipelineCallObject *this,
        const wchar_t *a2,
        wchar_t *a3,
        wchar_t *a4,
        WCHAR *a5,
        LPWSTR pPrinterName,
        wchar_t *a7,
        wchar_t *a8,
        unsigned int a9,
        unsigned __int64 a10)
{
  int v12; // r14d
  PVOID *v14; // rcx
  wchar_t *v15; // rax
  const char *v16; // rdx
  unsigned int v17; // r8d
  PrnExcept::TPropertyBag *v18; // rax
  __int64 v19; // rcx
  const wchar_t *v20; // rdx
  const wchar_t *v21; // r8
  struct IXMLDOMNode *RootNode; // rax
  SplPipeline *v23; // rcx
  wchar_t *FilePoolDirectory; // rax
  const char *v25; // rdx
  unsigned int v26; // r8d
  _DWORD *v27; // rax
  _DWORD *v28; // rsi
  struct PrnSharedState::SharedState *v29; // rbx
  const char *v30; // rdx
  unsigned int v31; // r8d
  PrnComps::TImgFilePool *v32; // rax
  const wchar_t *v33; // r9
  PrnComps *v34; // rax
  PrnComps *v35; // rcx
  HANDLE EventW; // rax
  const wchar_t **v37; // r14
  const wchar_t *v38; // rdx
  const char *v39; // r8
  unsigned int v40; // r9d
  wchar_t *v41; // rax
  void **v42; // r15
  HANDLE CurrentThread; // rax
  void **v44; // r9
  int v45; // ebx
  HANDLE v46; // rax
  void **v47; // r9
  int v48; // ebx
  HANDLE v49; // rax
  HANDLE v50; // rax
  void *v51; // rcx
  void *v52; // rdx
  bool IsPrinterSpooled; // bl
  const char *v54; // rdx
  unsigned int v55; // r8d
  _DWORD *v56; // rax
  _DWORD *v57; // r14
  __int64 v58; // rbx
  const char *v59; // rdx
  unsigned int v60; // r8d
  WCHAR *v61; // rax
  void *v62; // r9
  __int64 v63; // r13
  const char *v64; // rdx
  unsigned int v65; // r8d
  WCHAR *v66; // rax
  __int64 v67; // rdx
  void *v68; // r9
  __int64 InputXpsPackageType; // r12
  __int64 v70; // rcx
  SplPipeline::SplFilterPipelineCallObject *v71; // rcx
  __int64 NewPipelineManager; // r15
  void *v73; // rax
  SplPipeline *v74; // rcx
  __int64 v75; // rdx
  const wchar_t *v76; // rax
  int v77; // r13d
  struct IPrintFilterSequence *v78; // rbx
  int v79; // eax
  int v80; // edx
  const char *v81; // r8
  unsigned int v82; // r9d
  const struct SplException::TSystemException *v83; // r8
  const struct _GUID *v84; // r9
  NCoreLibrary *v85; // rcx
  unsigned int LastErrorAsHResult; // eax
  const struct SplException::TSystemException *v87; // r8
  const struct _GUID *v88; // r9
  NCoreLibrary *v89; // rcx
  unsigned int v90; // eax
  const struct SplException::TSystemException *v91; // r8
  const struct _GUID *v92; // r9
  NCoreLibrary *v93; // rcx
  unsigned int v94; // eax
  const struct SplException::TSystemException *v95; // r8
  const struct _GUID *v96; // r9
  NCoreLibrary *v97; // rcx
  unsigned int v98; // eax
  const struct SplException::TSystemException *v99; // r8
  const struct _GUID *v100; // r9
  const struct SplException::TSystemException *v101; // r8
  const struct _GUID *v102; // r9
  NCoreLibrary *v103; // rcx
  unsigned int v104; // eax
  const struct SplException::TSystemException *v105; // r8
  const struct _GUID *v106; // r9
  NCoreLibrary *v107; // rcx
  unsigned int v108; // eax
  const struct SplException::TSystemException *v109; // r8
  const struct _GUID *v110; // r9
  const struct SplException::TSystemException *v111; // r8
  const struct _GUID *v112; // r9
  NCoreLibrary *v113; // rcx
  unsigned int v114; // eax
  const struct SplException::TSystemException *v115; // r8
  const struct _GUID *v116; // r9
  struct IPrintReadStreamFactory *v117; // [rsp+20h] [rbp-E0h]
  unsigned int v118; // [rsp+20h] [rbp-E0h]
  unsigned int v119; // [rsp+20h] [rbp-E0h]
  const struct win_musl::TStringEllipseBase *hPrinter; // [rsp+28h] [rbp-D8h]
  const struct win_musl::TStringEllipseBase *hPrintera; // [rsp+28h] [rbp-D8h]
  const struct win_musl::TStringEllipseBase *hPrinterb; // [rsp+28h] [rbp-D8h]
  HINSTANCE v123; // [rsp+30h] [rbp-D0h]
  HINSTANCE v124; // [rsp+30h] [rbp-D0h]
  HINSTANCE v125; // [rsp+30h] [rbp-D0h]
  unsigned int v126; // [rsp+38h] [rbp-C8h]
  bool IsRandomAccessMode; // [rsp+70h] [rbp-90h] BYREF
  bool v128; // [rsp+71h] [rbp-8Fh] BYREF
  LPWSTR v129; // [rsp+78h] [rbp-88h] BYREF
  struct IPrintFilterSequence *v130; // [rsp+80h] [rbp-80h] BYREF
  void *v131; // [rsp+88h] [rbp-78h]
  _DWORD *v132; // [rsp+90h] [rbp-70h] BYREF
  void *TokenHandle; // [rsp+98h] [rbp-68h] BYREF
  __int64 v134; // [rsp+A0h] [rbp-60h] BYREF
  struct IPrintFilterSequence *Sequence; // [rsp+A8h] [rbp-58h] BYREF
  int v136[2]; // [rsp+B0h] [rbp-50h] BYREF
  struct IImgFilePool *MemoryPool; // [rsp+B8h] [rbp-48h] BYREF
  PrnComps *v138; // [rsp+C0h] [rbp-40h]
  wchar_t *v139; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v140; // [rsp+D0h] [rbp-30h] BYREF
  void *v141; // [rsp+D8h] [rbp-28h]
  wchar_t *v142; // [rsp+E0h] [rbp-20h]
  __int64 v143; // [rsp+E8h] [rbp-18h] BYREF
  struct IPrintReadStreamFactory *v144; // [rsp+F0h] [rbp-10h] BYREF
  _DWORD *v145; // [rsp+F8h] [rbp-8h] BYREF
  struct IImgFilePool *v146; // [rsp+100h] [rbp+0h] BYREF
  PrnComps *v147; // [rsp+108h] [rbp+8h] BYREF
  wchar_t *v148; // [rsp+110h] [rbp+10h] BYREF
  int v149; // [rsp+11Ch] [rbp+1Ch]
  struct IPrintReadStreamFactory *UnlockedStreamBuffer; // [rsp+120h] [rbp+20h]
  BYTE pDocInfo[8]; // [rsp+128h] [rbp+28h] BYREF
  wchar_t *v152; // [rsp+130h] [rbp+30h]
  wchar_t near **v153; // [rsp+138h] [rbp+38h]
  _BYTE v154[160]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+1E0h] [rbp+E0h] BYREF

  v141 = a4;
  v12 = (int)a2;
  LODWORD(v131) = (_DWORD)a2;
  v129 = a5;
  v148 = a7;
  v142 = a8;
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_a2cda53fd4003733db4e66a2523c8202_Traceguids);
      v14 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v14 != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)v14 + 7) & 0x100) != 0 && *((_BYTE *)v14 + 25) )
      {
        WPP_SF_S(v14[2], 17, &WPP_a2cda53fd4003733db4e66a2523c8202_Traceguids);
        v14 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v14 != &WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)v14 + 7) & 0x100) != 0 && *((_BYTE *)v14 + 25) )
        {
          WPP_SF_S(v14[2], 18, &WPP_a2cda53fd4003733db4e66a2523c8202_Traceguids);
          v14 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v14 != &WPP_GLOBAL_Control )
        {
          if ( (*((_DWORD *)v14 + 7) & 0x100) != 0 && *((_BYTE *)v14 + 25) )
          {
            WPP_SF_S(v14[2], 19, &WPP_a2cda53fd4003733db4e66a2523c8202_Traceguids);
            v14 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v14 != &WPP_GLOBAL_Control && (*((_DWORD *)v14 + 7) & 0x100) != 0 && *((_BYTE *)v14 + 25) )
            WPP_SF_d(v14[2], 20, &WPP_a2cda53fd4003733db4e66a2523c8202_Traceguids, a9);
        }
      }
    }
  }
  *((_DWORD *)this + 40) = v12;
  v15 = PrnExcept::CopyString((PrnExcept *)a7, a2, (const char *)a3, (unsigned int)a4);
  NCoreLibrary::TAutoPtrArray<wchar_t>::operator=((char *)this + 144, v15);
  v18 = (PrnExcept::TPropertyBag *)operator new(0x78u, v16, v17);
  Sequence = v18;
  if ( v18 )
    v19 = PrnExcept::TPropertyBag::TPropertyBag(v18);
  else
    v19 = 0;
  v132 = (_DWORD *)*((_QWORD *)this + 15);
  *((_QWORD *)this + 15) = v19;
  PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(&v132);
  *(_QWORD *)v136 = 0;
  RootNode = PrnExcept::LoadXmlAndGetRootNode(a3, v20, v21);
  v132 = 0;
  *(_QWORD *)v136 = RootNode;
  PrnExcept::SmartRelease<IPartResourceDictionary>(&v132);
  v132 = 0;
  v147 = 0;
  v146 = 0;
  v145 = 0;
  v140 = 0;
  v139 = 0;
  v144 = 0;
  FilePoolDirectory = SplPipeline::GetFilePoolDirectory(v23);
  NCoreLibrary::TAutoPtrArray<wchar_t>::operator=(&v139, FilePoolDirectory);
  v27 = operator new(0x30u, v25, v26);
  v28 = v27;
  if ( v27 )
  {
    *(_QWORD *)v27 = &NCOMLibrary::TUnknown::`vftable';
    v27[2] = 1852534389;
    v27[3] = 1;
    _InterlockedAdd(&NCOMLibrary::TUnknown::g_cOutStandingObjectCount, 1u);
    *(_QWORD *)v27 = &SplPipeline::SplFilterPipelineCallObject::TDoneNotifier::`vftable'{for `NCOMLibrary::TUnknown'};
    *((_QWORD *)v27 + 2) = &SplPipeline::SplFilterPipelineCallObject::TDoneNotifier::`vftable'{for `IPrintPipelineDoneNotify'};
    *((_QWORD *)v27 + 3) = this;
    PrnExcept::SmartAddRef<SplPipeline::SplFilterPipelineCallObject>(this);
    *((_QWORD *)v28 + 4) = SplPipeline::SplFilterPipelineCallObject::PipelineDone;
    v28[10] = 0;
    v28[11] = v149;
  }
  else
  {
    v28 = 0;
  }
  v130 = 0;
  v145 = v28;
  PrnExcept::SmartRelease<SplReadWrite::SequentialSpoolReaderWriter>(&v130);
  v29 = *(struct PrnSharedState::SharedState **)(*((_QWORD *)this + 19) + 16LL);
  v32 = (PrnComps::TImgFilePool *)operator new(0x108u, v30, v31);
  Sequence = v32;
  if ( v32 )
    v34 = (PrnComps *)PrnComps::TImgFilePool::TImgFilePool(
                        v32,
                        v29,
                        v139,
                        v33,
                        (const wchar_t *)v117,
                        (unsigned int)hPrinter,
                        (bool)v123,
                        v126);
  else
    v34 = 0;
  v138 = v34;
  v130 = 0;
  v147 = v34;
  PrnExcept::SmartRelease<IPartResourceDictionary>(&v130);
  MemoryPool = PrnComps::CreateMemoryPool(v35);
  v130 = 0;
  v146 = MemoryPool;
  PrnExcept::SmartRelease<IPartResourceDictionary>(&v130);
  EventW = CreateEventW(0, 1, 1, 0);
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Attach(
    (char *)this + 72,
    EventW);
  if ( *((_QWORD *)this + 9) == -1 )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v154, "-", 0);
    LastErrorAsHResult = NCoreLibrary::GetLastErrorAsHResult(v85);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v154,
      LastErrorAsHResult,
      v87,
      v88,
      (unsigned int)v117,
      hPrinter,
      v123);
    SplException::TSystemException::Message((SplException::TSystemException *)v154, "CreateEvent failed");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v154);
    throw (SplException::THResultException *)pExceptionObject;
  }
  *((_DWORD *)this + 17) = 1;
  TokenHandle = (void *)-1LL;
  PrnExcept::ImpersonateClientThroughScope::ImpersonateClientThroughScope((PrnExcept::ImpersonateClientThroughScope *)&IsRandomAccessMode);
  SplPipeline::CPipelineCallObjectLockRAII::CPipelineCallObjectLockRAII(
    (SplPipeline::CPipelineCallObjectLockRAII *)&Sequence,
    this);
  v37 = (const wchar_t **)((char *)this + 40);
  if ( !OpenPrinterW(a4, (LPHANDLE)this + 5, 0) )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v154, "-", 0);
    v90 = NCoreLibrary::GetLastErrorAsHResult(v89);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v154,
      v90,
      v91,
      v92,
      (unsigned int)v117,
      hPrinter,
      v123);
    SplException::TSystemException::Message(
      (SplException::TSystemException *)v154,
      "OpenPrinter m_hPrinterForFilters failed");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v154);
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( !*((_QWORD *)this + 17) )
  {
    v41 = PrnExcept::CopyString((PrnExcept *)a4, v38, v39, v40);
    NCoreLibrary::TAutoPtrArray<wchar_t>::operator=((char *)this + 136, v41);
  }
  SplPipeline::SplFilterPipelineCallObject::GetDriverDirectory(this);
  SplPipeline::CPipelineCallObjectLockRAII::CPipelineCallObjectLockRAII(
    (SplPipeline::CPipelineCallObjectLockRAII *)&Sequence,
    this);
  if ( !OpenPrinterW(pPrinterName, (LPHANDLE)this + 7, 0) )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v154, "-", 0);
    v94 = NCoreLibrary::GetLastErrorAsHResult(v93);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v154,
      v94,
      v95,
      v96,
      (unsigned int)v117,
      hPrinter,
      v123);
    SplException::TSystemException::Message((SplException::TSystemException *)v154, "OpenPrinter port failed");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v154);
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( !OpenPrinterW(v129, (LPHANDLE)this + 6, 0) )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v154, "-", 0);
    v98 = NCoreLibrary::GetLastErrorAsHResult(v97);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v154,
      v98,
      v99,
      v100,
      (unsigned int)v117,
      hPrinter,
      v123);
    SplException::TSystemException::Message((SplException::TSystemException *)v154, "OpenPrinter read failed");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v154);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v42 = (void **)((char *)this + 80);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
  {
    CurrentThread = GetCurrentThread();
    v45 = SecurityHelper::OpenThreadToken(CurrentThread, 0xFu, (PHANDLE)this + 10, v44);
    if ( v45 )
    {
      SplException::THResultException::THResultException((SplException::THResultException *)v154, "-", 0);
      if ( v45 > 0 )
        v45 = (unsigned __int16)v45 | 0x80070000;
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)v154,
        v45,
        v101,
        v102,
        (unsigned int)v117,
        hPrinter,
        v123);
      SplException::TSystemException::Message((SplException::TSystemException *)v154, "OpenThreadToken failed");
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)v154);
      throw (SplException::THResultException *)pExceptionObject;
    }
    v46 = GetCurrentThread();
    v48 = SecurityHelper::OpenThreadToken(v46, 0xCu, &TokenHandle, v47);
    if ( v48 )
    {
      SplException::THResultException::THResultException((SplException::THResultException *)v154, "-", 0);
      if ( v48 > 0 )
        v48 = (unsigned __int16)v48 | 0x80070000;
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)v154,
        v48,
        v83,
        v84,
        (unsigned int)v117,
        hPrinter,
        v123);
      SplException::TSystemException::Message((SplException::TSystemException *)v154, "OpenThreadToken failed");
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)v154);
      throw (SplException::THResultException *)pExceptionObject;
    }
  }
  else
  {
    v49 = GetCurrentThread();
    if ( !OpenThreadToken(v49, 0xFu, 1, (PHANDLE)this + 10) )
    {
      SplException::THResultException::THResultException((SplException::THResultException *)v154, "-", 0);
      v104 = NCoreLibrary::GetLastErrorAsHResult(v103);
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)v154,
        v104,
        v105,
        v106,
        (unsigned int)v117,
        hPrinter,
        v123);
      SplException::TSystemException::Message((SplException::TSystemException *)v154, "OpenThreadToken failed");
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)v154);
      throw (SplException::THResultException *)pExceptionObject;
    }
    v50 = GetCurrentThread();
    if ( !OpenThreadToken(v50, 0xCu, 1, &TokenHandle) )
    {
      SplException::THResultException::THResultException((SplException::THResultException *)v154, "-", 0);
      v108 = NCoreLibrary::GetLastErrorAsHResult(v107);
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)v154,
        v108,
        v109,
        v110,
        (unsigned int)v117,
        hPrinter,
        v123);
      SplException::TSystemException::Message((SplException::TSystemException *)v154, "OpenThreadToken failed");
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)v154);
      throw (SplException::THResultException *)pExceptionObject;
    }
  }
  v51 = *v42;
  if ( *v42 == (void *)-1LL )
    v51 = 0;
  UnlockedStreamBuffer = PrnComps::CreateUnlockedStreamBuffer(v138, MemoryPool, a4, *v37, v51, hPrinter);
  v130 = 0;
  v144 = UnlockedStreamBuffer;
  PrnExcept::SmartRelease<IPartResourceDictionary>(&v130);
  IsPrinterSpooled = SplPipeline::IsPrinterSpooled((HANDLE)*v37, v52);
  CoRevertToSelf();
  v130 = 0;
  Sequence = SplPipeline::ConfigLoader::LoadFilterCreateSequence(
               (SplPipeline::ConfigLoader *)v136,
               *(struct PrnSharedState::SharedState **)(*((_QWORD *)this + 19) + 16LL),
               (void *)*v37);
  v134 = 0;
  v130 = Sequence;
  PrnExcept::SmartRelease<IPartResourceDictionary>(&v134);
  v128 = 0;
  IsRandomAccessMode = SplPipeline::SplFilterPipelineCallObject::IsRandomAccessMode(
                         this,
                         a10,
                         (unsigned int)v131,
                         !IsPrinterSpooled,
                         &v128);
  v56 = operator new(0x18u, v54, v55);
  v57 = v56;
  v132 = v56;
  if ( v56 )
  {
    v56[2] = 1;
    *(_QWORD *)v56 = &PrnExcept::SharedWindowsHandle::`vftable';
    *((_BYTE *)v56 + 16) = a9 != 0;
    *((_BYTE *)v56 + 17) = IsRandomAccessMode;
    *((_BYTE *)v56 + 18) = IsPrinterSpooled;
    v58 = 0;
  }
  else
  {
    v58 = 0;
    v57 = 0;
  }
  v134 = 0;
  v132 = v57;
  PrnExcept::SmartRelease<FrameState::TFrameGlobalState>(&v134);
  v134 = 0;
  v143 = 0;
  v61 = (WCHAR *)operator new(0x78u, v59, v60);
  v129 = v61;
  if ( v61 )
  {
    v62 = *v42;
    if ( *v42 == (void *)-1LL )
      v62 = 0;
    v123 = (HINSTANCE)a4;
    hPrintera = (const struct win_musl::TStringEllipseBase *)&a10;
    v118 = 0;
    v63 = SplReadWrite::SequentialSpoolReaderWriter::SequentialSpoolReaderWriter(v61, *((_QWORD *)this + 6), 0, v62);
  }
  else
  {
    v63 = 0;
  }
  v129 = 0;
  v134 = v63;
  PrnExcept::SmartRelease<SplReadWrite::SequentialSpoolReaderWriter>(&v129);
  v66 = (WCHAR *)operator new(0x78u, v64, v65);
  v129 = v66;
  if ( v66 )
  {
    v67 = *((_QWORD *)this + 11);
    if ( v67 == -1 )
      LODWORD(v67) = 0;
    v68 = *v42;
    if ( *v42 == (void *)-1LL )
      v68 = 0;
    v123 = 0;
    hPrintera = 0;
    v118 = v67;
    v58 = SplReadWrite::SequentialSpoolReaderWriter::SequentialSpoolReaderWriter(v66, *((_QWORD *)this + 7), 1, v68);
  }
  v129 = 0;
  v143 = v58;
  PrnExcept::SmartRelease<SplReadWrite::SequentialSpoolReaderWriter>(&v129);
  InputXpsPackageType = (unsigned int)SplPipeline::SplFilterPipelineCallObject::GetInputXpsPackageType(
                                        this,
                                        (unsigned int)v131);
  LODWORD(v129) = SplPipeline::ConfigLoader::LoadXpsDriverType(v70, *((_QWORD *)this + 5), InputXpsPackageType);
  if ( !(_DWORD)v129 && (_DWORD)InputXpsPackageType == 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_a2cda53fd4003733db4e66a2523c8202_Traceguids);
    }
    SplException::THResultException::THResultException((SplException::THResultException *)v154, "-", 0);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v154,
      0x80004005,
      v111,
      v112,
      v118,
      hPrintera,
      v123);
    SplException::TSystemException::Message((SplException::TSystemException *)v154, "Unsupported OpenXPS Conversion.");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v154);
    throw (SplException::THResultException *)pExceptionObject;
  }
  SplPipeline::SplFilterPipelineCallObject::GetDriverVersion(v71, *((void **)this + 5));
  if ( v58 )
    v58 += 24;
  v124 = (HINSTANCE)v141;
  NewPipelineManager = PrnComps::CreateNewPipelineManager(
                         *(_QWORD *)(*((_QWORD *)this + 19) + 16LL),
                         v138,
                         MemoryPool,
                         (unsigned __int64)(v28 + 4) & -(__int64)(v28 != 0),
                         (v63 + 16) & -(__int64)(v63 != 0),
                         v58);
  MemoryPool = 0;
  v140 = NewPipelineManager;
  PrnExcept::SmartRelease<IPartResourceDictionary>(&MemoryPool);
  v73 = (void *)*((_QWORD *)this + 11);
  if ( v73 == (void *)-1LL )
    v73 = 0;
  v74 = (SplPipeline *)*((_QWORD *)this + 7);
  v75 = -1;
  if ( TokenHandle != (void *)-1LL )
  {
    v75 = (__int64)TokenHandle;
    TokenHandle = (void *)-1LL;
  }
  SplPipeline::AddNotifyInformation(
    v74,
    (const wchar_t *)v75,
    (void *)(unsigned int)v131,
    *((_QWORD *)this + 15),
    v74,
    v73,
    v124);
  v76 = L"OpenXPS";
  v77 = (int)v129;
  if ( (_DWORD)v129 != 1 )
    v76 = L"XPS";
  SplPipeline::SplFilterPipelineCallObject::AddPrinterInfoToBag(
    this,
    *((const wchar_t **)this + 17),
    v142,
    (unsigned int)v131,
    UnlockedStreamBuffer,
    v76);
  SplPipeline::ConfigLoader::CreateFilterServiceProviders(
    (int)v136,
    *((_QWORD *)this + 15) != 0 ? *((_DWORD *)this + 30) + 16 : 0,
    (int)v141,
    *(_QWORD *)(*((_QWORD *)this + 19) + 16LL),
    *((_QWORD *)this + 16),
    *((HANDLE *)this + 5),
    (__int64)this + 232);
  v78 = Sequence;
  if ( !(*(unsigned int (__fastcall **)(struct IPrintFilterSequence *))(*(_QWORD *)Sequence + 40LL))(Sequence)
    || v77 == 1 && (_DWORD)InputXpsPackageType != 1
    || *((_BYTE *)v57 + 16) )
  {
    PrnExcept::ImpersonateClientThroughScope::ImpersonateClientThroughScope((PrnExcept::ImpersonateClientThroughScope *)&IsRandomAccessMode);
    *(_QWORD *)pDocInfo = v148;
    v152 = v142;
    v153 = &g_szOutputData;
    if ( !StartDocPrinterW(*((HANDLE *)this + 7), 0x64u, pDocInfo) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_a2cda53fd4003733db4e66a2523c8202_Traceguids);
      }
      SplException::THResultException::THResultException((SplException::THResultException *)v154, "-", 0);
      v114 = NCoreLibrary::GetLastErrorAsHResult(v113);
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)v154,
        v114,
        v115,
        v116,
        v119,
        hPrinterb,
        v125);
      SplException::TSystemException::Message((SplException::TSystemException *)v154, "StartDocPrinter port failed");
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)v154);
      throw (SplException::THResultException *)pExceptionObject;
    }
    *((_BYTE *)this + 64) = 1;
    CoRevertToSelf();
  }
  v79 = (*(__int64 (__fastcall **)(__int64, struct IPrintFilterSequence *, __int64))(*(_QWORD *)NewPipelineManager + 24LL))(
          NewPipelineManager,
          v78,
          (*((_QWORD *)this + 15) + 16LL) & -(__int64)(*((_QWORD *)this + 15) != 0));
  if ( v79 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v79, v80, v81, v82);
  PrnExcept::TRefSmartPtr<IUnknown>::operator=((char *)this + 104, &v140);
  v148 = (wchar_t *)*((_QWORD *)this + 12);
  *((_QWORD *)this + 12) = v28;
  PrnExcept::SmartAddRef<SplPipeline::SplFilterPipelineCallObject::TDoneNotifier>(v28);
  PrnExcept::SmartRelease<SplReadWrite::SequentialSpoolReaderWriter>(&v148);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)NewPipelineManager + 56LL))(NewPipelineManager);
  PrnExcept::SmartRelease<SplReadWrite::SequentialSpoolReaderWriter>(&v143);
  PrnExcept::SmartRelease<SplReadWrite::SequentialSpoolReaderWriter>(&v134);
  PrnExcept::SmartRelease<IPartResourceDictionary>(&v130);
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(&TokenHandle);
  PrnExcept::SmartRelease<IPartResourceDictionary>(&v144);
  NCoreLibrary::TGenericSP<unsigned char,NCoreLibrary::TAutoPtrArray<unsigned char>,unsigned char *,0,unsigned char const *>::Reset(&v139);
  PrnExcept::SmartRelease<IPartResourceDictionary>(&v140);
  PrnExcept::SmartRelease<SplReadWrite::SequentialSpoolReaderWriter>(&v145);
  PrnExcept::SmartRelease<IPartResourceDictionary>(&v146);
  PrnExcept::SmartRelease<IPartResourceDictionary>(&v147);
  PrnExcept::SmartRelease<FrameState::TFrameGlobalState>(&v132);
  PrnExcept::SmartRelease<IPartResourceDictionary>(v136);
}

```

## disassembly

```asm
0x140012404  push    rbp
0x140012406  push    rbx
0x140012407  push    rsi
0x140012408  push    rdi
0x140012409  push    r12
0x14001240b  push    r13
0x14001240d  push    r14
0x14001240f  push    r15
0x140012411  lea     rbp, [rsp-198h]
0x140012419  sub     rsp, 298h
0x140012420  mov     rax, cs:__security_cookie
0x140012427  xor     rax, rsp
0x14001242a  mov     [rbp+1D0h+var_50], rax
0x140012431  mov     r13, r9
0x140012434  mov     [rbp+1D0h+var_1F8], r9
0x140012438  mov     rbx, r8
0x14001243b  mov     r14d, edx
0x14001243e  mov     dword ptr [rbp+1D0h+var_248], edx
0x140012441  mov     rdi, rcx
0x140012444  mov     rax, [rbp+1D0h+arg_20]
0x14001244b  mov     [rsp+2D0h+var_258], rax
0x140012450  mov     r15, [rbp+1D0h+pPrinterName]
0x140012457  mov     rsi, [rbp+1D0h+arg_30]
0x14001245e  mov     [rbp+1D0h+var_1C0], rsi
0x140012462  mov     rcx, [rbp+1D0h+arg_38]
0x140012469  mov     [rbp+1D0h+var_1F0], rcx
0x14001246d  lea     r12, WPP_GLOBAL_Control
0x140012474  mov     rcx, cs:WPP_GLOBAL_Control
0x14001247b  cmp     rcx, r12
0x14001247e  jz      loc_140012585
0x140012484  test    dword ptr [rcx+1Ch], 100h
0x14001248b  jz      short loc_1400124B4
0x14001248d  cmp     byte ptr [rcx+19h], 1
0x140012491  jb      short loc_1400124B4
0x140012493  mov     edx, 10h
0x140012498  lea     r8, WPP_a2cda53fd4003733db4e66a2523c8202_Traceguids
0x14001249f  mov     rcx, [rcx+10h]
0x1400124a3  call    WPP_SF_S
0x1400124a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400124af  mov     rax, [rsp+2D0h+var_258]
0x1400124b4  cmp     rcx, r12
0x1400124b7  jz      loc_140012585
0x1400124bd  test    dword ptr [rcx+1Ch], 100h
0x1400124c4  jz      short loc_1400124EB
0x1400124c6  cmp     byte ptr [rcx+19h], 1
0x1400124ca  jb      short loc_1400124EB
0x1400124cc  mov     edx, 11h
0x1400124d1  mov     r9, rax
0x1400124d4  lea     r8, WPP_a2cda53fd4003733db4e66a2523c8202_Traceguids
0x1400124db  mov     rcx, [rcx+10h]
0x1400124df  call    WPP_SF_S
0x1400124e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400124eb  cmp     rcx, r12
0x1400124ee  jz      loc_140012585
0x1400124f4  test    dword ptr [rcx+1Ch], 100h
0x1400124fb  jz      short loc_140012522
0x1400124fd  cmp     byte ptr [rcx+19h], 1
0x140012501  jb      short loc_140012522
0x140012503  mov     edx, 12h
0x140012508  mov     r9, r15
0x14001250b  lea     r8, WPP_a2cda53fd4003733db4e66a2523c8202_Traceguids
0x140012512  mov     rcx, [rcx+10h]
0x140012516  call    WPP_SF_S
0x14001251b  mov     rcx, cs:WPP_GLOBAL_Control
0x140012522  cmp     rcx, r12
0x140012525  jz      short loc_140012585
0x140012527  test    dword ptr [rcx+1Ch], 100h
0x14001252e  jz      short loc_140012555
0x140012530  cmp     byte ptr [rcx+19h], 1
0x140012534  jb      short loc_140012555
0x140012536  mov     edx, 13h
0x14001253b  mov     r9, rsi
0x14001253e  lea     r8, WPP_a2cda53fd4003733db4e66a2523c8202_Traceguids
0x140012545  mov     rcx, [rcx+10h]
0x140012549  call    WPP_SF_S
0x14001254e  mov     rcx, cs:WPP_GLOBAL_Control
0x140012555  cmp     rcx, r12
0x140012558  jz      short loc_140012585
0x14001255a  test    dword ptr [rcx+1Ch], 100h
0x140012561  jz      short loc_140012585
0x140012563  cmp     byte ptr [rcx+19h], 1
0x140012567  jb      short loc_140012585
0x140012569  mov     edx, 14h
0x14001256e  mov     r9d, [rbp+1D0h+arg_40]
0x140012575  lea     r8, WPP_a2cda53fd4003733db4e66a2523c8202_Traceguids
0x14001257c  mov     rcx, [rcx+10h]
0x140012580  call    WPP_SF_d
0x140012585  mov     [rdi+0A0h], r14d
0x14001258c  mov     rcx, rsi; this
0x14001258f  call    ?CopyString@PrnExcept@@YAPEA_WPEB_WPEBDK@Z; PrnExcept::CopyString(wchar_t const *,char const *,ulong)
0x140012594  mov     rdx, rax
0x140012597  lea     rcx, [rdi+90h]
0x14001259e  call    ??4?$TAutoPtrArray@_W@NCoreLibrary@@QEAAPEA_WPEA_W@Z; NCoreLibrary::TAutoPtrArray<wchar_t>::operator=(wchar_t *)
0x1400125a3  mov     ecx, 78h ; 'x'; unsigned __int64
0x1400125a8  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x1400125ad  mov     [rbp+1D0h+var_228], rax
0x1400125b1  xor     r12d, r12d
0x1400125b4  test    rax, rax
0x1400125b7  jz      short loc_1400125C6
0x1400125b9  mov     rcx, rax; this
0x1400125bc  call    ??0TPropertyBag@PrnExcept@@QEAA@XZ; PrnExcept::TPropertyBag::TPropertyBag(void)
0x1400125c1  mov     rcx, rax
0x1400125c4  jmp     short loc_1400125C9
0x1400125c6  mov     rcx, r12
0x1400125c9  mov     rax, [rdi+78h]
0x1400125cd  mov     [rbp+1D0h+var_240], rax
0x1400125d1  mov     [rdi+78h], rcx
0x1400125d5  lea     rcx, [rbp+1D0h+var_240]
0x1400125d9  call    ??$SmartRelease@V?$PiboThumbnail@VSpillBufferStream@@@@@PrnExcept@@YAXPEAPEAV?$PiboThumbnail@VSpillBufferStream@@@@@Z; PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(PiboThumbnail<SpillBufferStream> * *)
0x1400125de  mov     qword ptr [rbp+1D0h+var_220], r12
0x1400125e2  mov     rcx, rbx; this
0x1400125e5  call    ?LoadXmlAndGetRootNode@PrnExcept@@YAPEAUIXMLDOMNode@@PEB_W0@Z; PrnExcept::LoadXmlAndGetRootNode(wchar_t const *,wchar_t const *)
0x1400125ea  mov     [rbp+1D0h+var_240], r12
0x1400125ee  mov     qword ptr [rbp+1D0h+var_220], rax
0x1400125f2  lea     rcx, [rbp+1D0h+var_240]
0x1400125f6  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x1400125fb  nop
0x1400125fc  mov     [rbp+1D0h+var_240], r12
0x140012600  mov     [rbp+1D0h+var_1C8], r12
0x140012604  mov     [rbp+1D0h+var_1D0], r12
0x140012608  mov     [rbp+1D0h+var_1D8], r12
0x14001260c  mov     [rbp+1D0h+var_200], r12
0x140012610  mov     [rbp+1D0h+var_208], r12
0x140012614  mov     [rbp+1D0h+var_1E0], r12
0x140012618  call    ?GetFilePoolDirectory@SplPipeline@@YAPEA_WXZ; SplPipeline::GetFilePoolDirectory(void)
0x14001261d  mov     rdx, rax
0x140012620  lea     rcx, [rbp+1D0h+var_208]
0x140012624  call    ??4?$TAutoPtrArray@_W@NCoreLibrary@@QEAAPEA_WPEA_W@Z; NCoreLibrary::TAutoPtrArray<wchar_t>::operator=(wchar_t *)
0x140012629  mov     ecx, 30h ; '0'; unsigned __int64
0x14001262e  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x140012633  mov     rsi, rax
0x140012636  mov     r14d, 1
0x14001263c  test    rax, rax
0x14001263f  jz      short loc_140012696
0x140012641  lea     rax, ??_7TUnknown@NCOMLibrary@@6B@; const NCOMLibrary::TUnknown::`vftable'
0x140012648  mov     [rsi], rax
0x14001264b  mov     dword ptr [rsi+8], 6E6B6E75h
0x140012652  mov     [rsi+0Ch], r14d
0x140012656  lock add cs:?g_cOutStandingObjectCount@TUnknown@NCOMLibrary@@0JA, r14d; long NCOMLibrary::TUnknown::g_cOutStandingObjectCount
0x14001265e  lea     rax, ??_7TDoneNotifier@SplFilterPipelineCallObject@SplPipeline@@6BTUnknown@NCOMLibrary@@@; const SplPipeline::SplFilterPipelineCallObject::TDoneNotifier::`vftable'{for `NCOMLibrary::TUnknown'}
0x140012665  mov     [rsi], rax
0x140012668  lea     rax, ??_7TDoneNotifier@SplFilterPipelineCallObject@SplPipeline@@6BIPrintPipelineDoneNotify@@@; const SplPipeline::SplFilterPipelineCallObject::TDoneNotifier::`vftable'{for `IPrintPipelineDoneNotify'}
0x14001266f  mov     [rsi+10h], rax
0x140012673  mov     [rsi+18h], rdi
0x140012677  mov     rcx, rdi
0x14001267a  call    ??$SmartAddRef@VSplFilterPipelineCallObject@SplPipeline@@@PrnExcept@@YAXPEAVSplFilterPipelineCallObject@SplPipeline@@@Z; PrnExcept::SmartAddRef<SplPipeline::SplFilterPipelineCallObject>(SplPipeline::SplFilterPipelineCallObject *)
0x14001267f  lea     rax, ?PipelineDone@SplFilterPipelineCallObject@SplPipeline@@QEAAXJPEAUIImgErrorInfo@@@Z; SplPipeline::SplFilterPipelineCallObject::PipelineDone(long,IImgErrorInfo *)
0x140012686  mov     [rsi+20h], rax
0x14001268a  mov     [rsi+28h], r12d
0x14001268e  mov     eax, [rbp+1D0h+var_1B4]
0x140012691  mov     [rsi+2Ch], eax
0x140012694  jmp     short loc_140012699
0x140012696  mov     rsi, r12
0x140012699  mov     [rbp+1D0h+var_250], r12
0x14001269d  mov     [rbp+1D0h+var_1D8], rsi
0x1400126a1  lea     rcx, [rbp+1D0h+var_250]
0x1400126a5  call    ??$SmartRelease@VSequentialSpoolReaderWriter@SplReadWrite@@@PrnExcept@@YAXPEAPEAVSequentialSpoolReaderWriter@SplReadWrite@@@Z; PrnExcept::SmartRelease<SplReadWrite::SequentialSpoolReaderWriter>(SplReadWrite::SequentialSpoolReaderWriter * *)
0x1400126aa  mov     rax, [rdi+98h]
0x1400126b1  mov     rbx, [rax+10h]
0x1400126b5  mov     ecx, 108h; unsigned __int64
0x1400126ba  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x1400126bf  mov     [rbp+1D0h+var_228], rax
0x1400126c3  test    rax, rax
0x1400126c6  jz      short loc_1400126D9
0x1400126c8  mov     r8, [rbp+1D0h+var_208]; wchar_t *
0x1400126cc  mov     rdx, rbx; struct PrnSharedState::SharedState *
0x1400126cf  mov     rcx, rax; this
0x1400126d2  call    ??0TImgFilePool@PrnComps@@QEAA@PEAVSharedState@PrnSharedState@@PEB_W11K_NK@Z; PrnComps::TImgFilePool::TImgFilePool(PrnSharedState::SharedState *,wchar_t const *,wchar_t const *,wchar_t const *,ulong,bool,ulong)
0x1400126d7  jmp     short loc_1400126DC
0x1400126d9  mov     rax, r12
0x1400126dc  mov     [rbp+1D0h+var_210], rax
0x1400126e0  mov     [rbp+1D0h+var_250], r12
0x1400126e4  mov     [rbp+1D0h+var_1C8], rax
0x1400126e8  lea     rcx, [rbp+1D0h+var_250]
0x1400126ec  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x1400126f1  call    ?CreateMemoryPool@PrnComps@@YAPEAUIMemoryPool@@XZ; PrnComps::CreateMemoryPool(void)
0x1400126f6  mov     [rbp+1D0h+var_218], rax
0x1400126fa  mov     [rbp+1D0h+var_250], r12
0x1400126fe  mov     [rbp+1D0h+var_1D0], rax
0x140012702  lea     rcx, [rbp+1D0h+var_250]
0x140012706  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14001270b  xor     r9d, r9d; lpName
0x14001270e  mov     r8d, r14d; bInitialState
0x140012711  mov     edx, r14d; bManualReset
0x140012714  xor     ecx, ecx; lpEventAttributes
0x140012716  call    cs:__imp_CreateEventW
0x14001271c  mov     rdx, rax
0x14001271f  lea     rcx, [rdi+48h]
0x140012723  call    ?Attach@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXPEAX@Z; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Attach(void *)
0x140012728  cmp     qword ptr [rdi+48h], 0FFFFFFFFFFFFFFFFh
0x14001272d  jz      loc_140012DBC
0x140012733  mov     [rdi+44h], r14d
0x140012737  mov     [rbp+1D0h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x14001273f  lea     rcx, [rsp+2D0h+var_260]; this
0x140012744  call    ??0ImpersonateClientThroughScope@PrnExcept@@QEAA@XZ; PrnExcept::ImpersonateClientThroughScope::ImpersonateClientThroughScope(void)
0x140012749  nop
0x14001274a  mov     rdx, rdi; struct SplPipeline::SplFilterPipelineCallObject *
0x14001274d  lea     rcx, [rbp+1D0h+var_228]; this
0x140012751  call    ??0CPipelineCallObjectLockRAII@SplPipeline@@QEAA@PEAVSplFilterPipelineCallObject@1@@Z; SplPipeline::CPipelineCallObjectLockRAII::CPipelineCallObjectLockRAII(SplPipeline::SplFilterPipelineCallObject *)
0x140012756  lea     r14, [rdi+28h]
0x14001275a  xor     r8d, r8d; pDefault
0x14001275d  mov     rdx, r14; phPrinter
0x140012760  mov     rcx, r13; pPrinterName
0x140012763  call    cs:__imp_OpenPrinterW
0x140012769  test    eax, eax
0x14001276b  jz      loc_140012E14
0x140012771  lea     rbx, [rdi+88h]
0x140012778  cmp     [rbx], r12
0x14001277b  jnz     short loc_140012790
0x14001277d  mov     rcx, r13; this
0x140012780  call    ?CopyString@PrnExcept@@YAPEA_WPEB_WPEBDK@Z; PrnExcept::CopyString(wchar_t const *,char const *,ulong)
0x140012785  mov     rdx, rax
0x140012788  mov     rcx, rbx
0x14001278b  call    ??4?$TAutoPtrArray@_W@NCoreLibrary@@QEAAPEA_WPEA_W@Z; NCoreLibrary::TAutoPtrArray<wchar_t>::operator=(wchar_t *)
0x140012790  mov     rcx, rdi; this
0x140012793  call    ?GetDriverDirectory@SplFilterPipelineCallObject@SplPipeline@@AEAAXXZ; SplPipeline::SplFilterPipelineCallObject::GetDriverDirectory(void)
0x140012798  mov     rdx, rdi; struct SplPipeline::SplFilterPipelineCallObject *
0x14001279b  lea     rcx, [rbp+1D0h+var_228]; this
0x14001279f  call    ??0CPipelineCallObjectLockRAII@SplPipeline@@QEAA@PEAVSplFilterPipelineCallObject@1@@Z; SplPipeline::CPipelineCallObjectLockRAII::CPipelineCallObjectLockRAII(SplPipeline::SplFilterPipelineCallObject *)
0x1400127a4  lea     rdx, [rdi+38h]; phPrinter
0x1400127a8  xor     r8d, r8d; pDefault
0x1400127ab  mov     rcx, r15; pPrinterName
0x1400127ae  call    cs:__imp_OpenPrinterW
0x1400127b4  test    eax, eax
0x1400127b6  jz      loc_140012E6C
0x1400127bc  xor     r8d, r8d; pDefault
0x1400127bf  lea     rdx, [rdi+30h]; phPrinter
0x1400127c3  mov     rcx, [rsp+2D0h+var_258]; pPrinterName
0x1400127c8  call    cs:__imp_OpenPrinterW
0x1400127ce  test    eax, eax
0x1400127d0  jz      loc_140012EC4
0x1400127d6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x1400127dd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x1400127e2  lea     r15, [rdi+50h]
0x1400127e6  test    al, al
0x1400127e8  jz      short loc_14001282B
0x1400127ea  call    cs:__imp_GetCurrentThread
0x1400127f0  mov     r8, r15; TokenHandle
0x1400127f3  mov     edx, 0Fh; DesiredAccess
0x1400127f8  mov     rcx, rax; ThreadHandle
0x1400127fb  call    ?OpenThreadToken@SecurityHelper@@YAKPEAXKPEAPEAX@Z; SecurityHelper::OpenThreadToken(void *,ulong,void * *)
0x140012800  mov     ebx, eax
0x140012802  test    eax, eax
0x140012804  jnz     loc_140012F1C
0x14001280a  call    cs:__imp_GetCurrentThread
0x140012810  lea     r8, [rbp+1D0h+TokenHandle]; TokenHandle
0x140012814  lea     edx, [rbx+0Ch]; DesiredAccess
0x140012817  mov     rcx, rax; ThreadHandle
0x14001281a  call    ?OpenThreadToken@SecurityHelper@@YAKPEAXKPEAPEAX@Z; SecurityHelper::OpenThreadToken(void *,ulong,void * *)
0x14001281f  mov     ebx, eax
0x140012821  test    eax, eax
0x140012823  jnz     loc_140012D5C
0x140012829  jmp     short loc_140012871
0x14001282b  call    cs:__imp_GetCurrentThread
0x140012831  mov     r9, r15; TokenHandle
0x140012834  mov     ebx, 1
0x140012839  mov     r8d, ebx; OpenAsSelf
0x14001283c  lea     edx, [rbx+0Eh]; DesiredAccess
0x14001283f  mov     rcx, rax; ThreadHandle
0x140012842  call    cs:__imp_OpenThreadToken
0x140012848  test    eax, eax
0x14001284a  jz      loc_140012F7C
0x140012850  call    cs:__imp_GetCurrentThread
0x140012856  lea     r9, [rbp+1D0h+TokenHandle]; TokenHandle
0x14001285a  mov     r8d, ebx; OpenAsSelf
0x14001285d  lea     edx, [rbx+0Bh]; DesiredAccess
0x140012860  mov     rcx, rax; ThreadHandle
0x140012863  call    cs:__imp_OpenThreadToken
0x140012869  test    eax, eax
0x14001286b  jz      loc_140012FD4
0x140012871  mov     rcx, [r15]
0x140012874  xor     eax, eax
0x140012876  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14001287a  cmovz   rcx, rax
0x14001287e  mov     [rsp+2D0h+var_2B0], rcx; void *
0x140012883  mov     r9, [r14]; wchar_t *
0x140012886  mov     r8, r13; wchar_t *
0x140012889  mov     rdx, [rbp+1D0h+var_218]; struct IImgFilePool *
0x14001288d  mov     rcx, [rbp+1D0h+var_210]; this
0x140012891  call    ?CreateUnlockedStreamBuffer@PrnComps@@YAPEAUIPrintReadStreamFactory@@PEAUIImgFilePool@@PEAUIMemoryPool@@PEB_WPEAX3@Z; PrnComps::CreateUnlockedStreamBuffer(IImgFilePool *,IMemoryPool *,wchar_t const *,void *,void *)
0x140012896  mov     [rbp+1D0h+var_1B0], rax
0x14001289a  mov     [rbp+1D0h+var_250], 0
0x1400128a2  mov     [rbp+1D0h+var_1E0], rax
0x1400128a6  lea     rcx, [rbp+1D0h+var_250]
0x1400128aa  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x1400128af  mov     rcx, [r14]; hPrinter
0x1400128b2  call    ?IsPrinterSpooled@SplPipeline@@YA_NPEAX@Z; SplPipeline::IsPrinterSpooled(void *)
0x1400128b7  mov     bl, al
0x1400128b9  call    cs:__imp_CoRevertToSelf
0x1400128bf  mov     [rbp+1D0h+var_250], 0
0x1400128c7  mov     rdx, [rdi+98h]
0x1400128ce  mov     r8, [r14]; void *
0x1400128d1  mov     rdx, [rdx+10h]; struct PrnSharedState::SharedState *
0x1400128d5  lea     rcx, [rbp+1D0h+var_220]; this
0x1400128d9  call    ?LoadFilterCreateSequence@ConfigLoader@SplPipeline@@QEAAPEAUIPrintFilterSequence@@PEAVSharedState@PrnSharedState@@PEAX@Z; SplPipeline::ConfigLoader::LoadFilterCreateSequence(PrnSharedState::SharedState *,void *)
0x1400128de  mov     [rbp+1D0h+var_228], rax
0x1400128e2  mov     [rbp+1D0h+var_230], 0
0x1400128ea  mov     [rbp+1D0h+var_250], rax
0x1400128ee  lea     rcx, [rbp+1D0h+var_230]
0x1400128f2  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
  ... truncated ...
```
