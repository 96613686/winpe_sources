# DevhlprGetReaderImageNameInternal(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800075d0`
- end: `0x18000854e`
- name: `?DevhlprGetReaderImageNameInternal@@YA?AV?$scoped_error@Utag@hresult_error@@@errorlib@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00AEAV34@@Z`
- size: `3966`
- prototype: `int *__fastcall(int *, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `45`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008e90`

## callees

- `0x1800066d8`
- `0x180006700`
- `0x1800075d0`
- `0x180008554`
- `0x1800085c4`
- `0x1800085dc`
- `0x1800085f4`
- `0x180008654`
- `0x1800086c4`
- `0x180008820`
- `0x1800090c8`
- `0x1800092f8`
- `0x1800093a0`
- `0x180009bc0`
- `0x18000d268`
- `0x18000d300`
- `0x18000dc40`
- `0x180010c58`
- `0x180010d5c`
- `0x180013dc4`
- `0x180013eb4`
- `0x180013fac`
- `0x180014034`
- `0x18001409c`
- `0x180014148`
- `0x180014178`
- `0x180014e88`
- `0x180015300`
- `0x180015368`
- `0x180015854`
- `0x180015894`
- `0x180015920`
- `0x18001597c`
- `0x180015a5c`
- `0x180015aa8`
- `0x180015b5c`
- `0x180015c04`
- `0x180016090`
- `0x180016114`
- `0x180016a66`
- `0x180016a72`
- `0x18001e054`
- `0x18001e064`
- `0x18001e074`
- `0x18001e250`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180007d49`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180007d49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180007d30`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180007d30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007b26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007da0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007b26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007da0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800080c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800081d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008373`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800080c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800081d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008373`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180007d96`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180007d96`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180007b1c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180007b1c`
- `WinSCard!SCardReleaseContext` at `0x180007745`
- `WinSCard!SCardReleaseContext` at `0x180007745`
- `WinSCard!SCardEstablishContext` at `0x1800076aa`
- `WinSCard!SCardEstablishContext` at `0x1800076aa`
- `WinSCard!SCardGetReaderIconW` at `0x180007779`
- `WinSCard!SCardGetReaderIconW` at `0x180007779`
- `bcrypt!BCryptHash` at `0x1800078cb`
- `bcrypt!BCryptHash` at `0x1800078cb`
- `gdiplus!GdipCreateBitmapFromHBITMAP` at `0x180007ec5`
- `gdiplus!GdipCreateBitmapFromHBITMAP` at `0x180007ec5`
- `gdiplus!GdipDisposeImage` at `0x1800080a2`
- `gdiplus!GdipDisposeImage` at `0x1800081b2`
- `gdiplus!GdipDisposeImage` at `0x180008321`
- `gdiplus!GdipDisposeImage` at `0x1800080a2`
- `gdiplus!GdipDisposeImage` at `0x1800081b2`
- `gdiplus!GdipDisposeImage` at `0x180008321`
- `gdiplus!GdipSaveImageToFile` at `0x180007f43`
- `gdiplus!GdipSaveImageToFile` at `0x180007f43`

## pseudocode

```c
int *__fastcall DevhlprGetReaderImageNameInternal(int *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  _QWORD *v9; // rdx
  LONG v10; // eax
  signed int v11; // ebx
  unsigned int v12; // edx
  int v13; // ecx
  __int128 *v14; // rdx
  signed int ReaderIconW; // eax
  int v16; // ebx
  int *v17; // rax
  int v18; // r15d
  LPWSTR v19; // r13
  WCHAR *v20; // rax
  size_t v21; // rbx
  const WCHAR *v22; // rcx
  DWORD v23; // eax
  __int64 v24; // rax
  __int64 v25; // rcx
  LPCWSTR *v26; // rdx
  int *v27; // rax
  int v28; // ecx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  __int64 v31; // rdx
  struct _SECURITY_ATTRIBUTES *v32; // rdx
  DWORD v33; // eax
  __int64 v34; // rdx
  const WCHAR *v35; // rcx
  int NestedDirectory; // ebx
  __int64 v37; // rdx
  int *EncoderClsidInternal; // rax
  int v39; // r13d
  unsigned int v40; // eax
  unsigned __int64 v41; // r15
  int v42; // ebx
  __int128 *p_Src; // rdx
  unsigned int v44; // eax
  int v45; // r13d
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rcx
  __m128i v50; // xmm6
  unsigned __int64 v51; // rdx
  __m128i v52; // xmm6
  unsigned int v53; // edx
  __m128i v54; // xmm6
  LPWSTR v55; // rcx
  unsigned __int64 v56; // rdx
  void *v57; // rcx
  unsigned __int64 v58; // rdx
  void *v59; // rcx
  unsigned __int64 v60; // rdx
  int v62; // [rsp+40h] [rbp-C0h] BYREF
  int v63; // [rsp+44h] [rbp-BCh]
  int v64; // [rsp+48h] [rbp-B8h] BYREF
  int v65; // [rsp+4Ch] [rbp-B4h]
  unsigned __int64 v66; // [rsp+50h] [rbp-B0h] BYREF
  SCARDCONTEXT phContext; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD v68[2]; // [rsp+60h] [rbp-A0h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp-98h] BYREF
  __int128 *p_pExceptionObject; // [rsp+70h] [rbp-90h]
  LPWSTR lpDst[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v72; // [rsp+88h] [rbp-78h]
  SCARDCONTEXT v73; // [rsp+90h] [rbp-70h] BYREF
  __int64 v74; // [rsp+98h] [rbp-68h] BYREF
  __int64 v75; // [rsp+A0h] [rbp-60h]
  int v76; // [rsp+A8h] [rbp-58h]
  unsigned int v77; // [rsp+ACh] [rbp-54h] BYREF
  __int128 v78; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v79; // [rsp+C0h] [rbp-40h]
  __int128 v80; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v81; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v82; // [rsp+E0h] [rbp-20h]
  __int128 pExceptionObject; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v84; // [rsp+F8h] [rbp-8h]
  __int64 v85; // [rsp+108h] [rbp+8h]
  __int64 v86; // [rsp+110h] [rbp+10h]
  __int64 v87; // [rsp+118h] [rbp+18h]
  __int64 v88; // [rsp+120h] [rbp+20h]
  __int128 v89; // [rsp+128h] [rbp+28h] BYREF
  __int64 v90; // [rsp+138h] [rbp+38h]
  unsigned __int64 v91; // [rsp+140h] [rbp+40h]
  LPCWSTR lpPathName[2]; // [rsp+148h] [rbp+48h] BYREF
  __int64 v93; // [rsp+158h] [rbp+58h]
  unsigned __int64 v94; // [rsp+160h] [rbp+60h]
  __int128 Src; // [rsp+168h] [rbp+68h] BYREF
  __m128i v96; // [rsp+178h] [rbp+78h]
  LPCWSTR lpSrc[2]; // [rsp+188h] [rbp+88h] BYREF
  __m128i si128; // [rsp+198h] [rbp+98h]
  __int128 v99; // [rsp+1A8h] [rbp+A8h] BYREF
  __m128i v100; // [rsp+1B8h] [rbp+B8h]
  __int128 v101; // [rsp+1C8h] [rbp+C8h] BYREF

  v86 = a2;
  v87 = a3;
  v88 = a4;
  v85 = a5;
  v76 = 0;
  v64 = 0;
  v65 = 1;
  std::vector<unsigned char>::vector<unsigned char>(&v73);
  *(_QWORD *)&v78 = &v62;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  if ( v9[3] > 7u )
    v9 = (_QWORD *)*v9;
  std::wstring::_Construct<2,unsigned short const *>(&v80, v9, *(_QWORD *)(a2 + 16));
  p_pExceptionObject = &v80;
  v62 = 0;
  v63 = 1;
  v76 = 2;
  phContext = 0;
  v10 = SCardEstablishContext(2u, 0, 0, &phContext);
  v11 = v10;
  if ( v10 > 0 )
    v11 = (unsigned __int16)v10 | 0x80070000;
  v68[0] = v11;
  v68[1] = 2;
  if ( v11 < 0 )
    errorlib::error_received<errorlib::scoped_error<hresult_error::tag>>();
  errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<hresult_error::tag> &>(v68);
  v13 = v63;
  if ( v63 != 1 && (unsigned int)(v63 - 3) > 3 )
  {
    metalib::FailFast((metalib *)0x80004004LL, v12);
    v13 = v63;
  }
  v62 = v11;
  v63 = 2;
  if ( v13 != 1 && (unsigned int)(v13 - 3) > 3 )
  {
    metalib::FailFast((metalib *)0x80004004LL, v12);
    v11 = v62;
  }
  v63 = 3;
  if ( v11 >= 0 )
  {
    v66 = 0;
    v77 = -1;
    v14 = &v80;
    if ( v82 > 7 )
      v14 = (__int128 *)v80;
    ReaderIconW = SCardGetReaderIconW(phContext, v14, &v66, &v77);
    if ( ReaderIconW > 0 )
      ReaderIconW = (unsigned __int16)ReaderIconW | 0x80070000;
    v68[0] = ReaderIconW;
    errorlib::scoped_error<hresult_error::tag>::receive<long>(&v62, v68);
    v63 = 3;
    if ( v62 >= 0 )
    {
      *(_QWORD *)&pExceptionObject = &phContext;
      *((_QWORD *)&pExceptionObject + 1) = &v66;
      LOWORD(v84) = 256;
      std::vector<unsigned char>::_Assign_counted_range<unsigned char *>(&v73, v66, v77);
      wil::details::ScopeExitFnGuard__lambda_ef7b62ae24276b172a03c6ede390e4c4___::operator()(&pExceptionObject);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long SCardReleaseContext(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long SCardReleaseContext(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phContext);
  }
  else
  {
    v76 = 0;
    if ( phContext )
      SCardReleaseContext(phContext);
  }
  std::wstring::_Tidy_deallocate(&v80);
  v64 = v62;
  v65 = 3;
  if ( v62 < 0 )
  {
    *a1 = v62;
    a1[1] = 2;
    v65 = 5;
    errorlib::scoped_error<hresult_error::tag>::report(a1, 3);
LABEL_25:
    std::vector<unsigned char>::_Tidy(&v73);
    errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v64);
    goto LABEL_127;
  }
  std::vector<unsigned char>::vector<unsigned char>(&v80);
  pExceptionObject = 0;
  v84 = 0;
  std::vector<unsigned char>::_Construct_n<unsigned char * const &,unsigned char * const &>(
    &pExceptionObject,
    v74 - v73,
    &v73,
    &v74);
  p_pExceptionObject = &pExceptionObject;
  phContext = 0x100000000LL;
  v78 = 0;
  v79 = 0;
  std::vector<unsigned char>::_Construct_n<>(&v78);
  v16 = BCryptHash(65, 0, 0);
  v62 = v16;
  v63 = 2;
  if ( ((unsigned int)v16 >> 30) - 1 <= 2 )
  {
    errorlib::error_received<errorlib::scoped_error<ntstatus_error::tag>>();
    errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<ntstatus_error::tag> &>(&v62);
    LODWORD(phContext) = v16;
    v62 = 0;
    v63 = 1;
    errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v62);
    HIDWORD(phContext) = 3;
    v68[0] = v16;
    errorlib::scoped_error<hresult_error::tag>::make_initiated<unsigned long>(&v66, v68);
    std::vector<unsigned char>::_Tidy(&v78);
    errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&phContext);
    v16 = v66;
  }
  else
  {
    errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<ntstatus_error::tag> &>(&v62);
    LODWORD(phContext) = v16;
    v62 = 0;
    v63 = 1;
    errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v62);
    HIDWORD(phContext) = 3;
    std::vector<unsigned char>::_Assign_counted_range<unsigned char *>(&v80, v78, *((_QWORD *)&v78 + 1) - v78);
    if ( v16 < 0 )
      errorlib::error_initiated<errorlib::scoped_error<hresult_error::tag>>();
    std::vector<unsigned char>::_Tidy(&v78);
  }
  std::vector<unsigned char>::_Tidy(&pExceptionObject);
  v64 = v16;
  v65 = 3;
  if ( v16 < 0 )
  {
    *a1 = v16;
    a1[1] = 2;
    v65 = 5;
    errorlib::scoped_error<hresult_error::tag>::report(a1, 3);
    std::vector<unsigned char>::_Tidy(&v80);
    goto LABEL_25;
  }
  v89 = 0;
  v90 = 0;
  v91 = 0;
  std::wstring::_Construct_empty(&v89);
  v17 = (int *)DevhlprConvertHashToStringInternal(&v66, &v80, &v89);
  v64 = *v17;
  v18 = v64;
  *v17 = v16;
  v17[1] = 3;
  v65 = 3;
  if ( v18 < 0 )
  {
    *a1 = v18;
    a1[1] = 2;
    v65 = 5;
    errorlib::scoped_error<hresult_error::tag>::report(a1, 3);
LABEL_35:
    std::wstring::_Tidy_deallocate(&v89);
    std::vector<unsigned char>::_Tidy(&v80);
    goto LABEL_25;
  }
  std::operator+<unsigned short>(lpSrc, a3, a4);
  std::vector<unsigned char>::vector<unsigned char>(lpDst);
  v19 = lpDst[1];
  if ( (LPWSTR)((char *)lpDst[1] - (char *)lpDst[0]) <= (LPWSTR)0x208 )
  {
    if ( (LPWSTR)((char *)lpDst[1] - (char *)lpDst[0]) >= (LPWSTR)0x208 )
      goto LABEL_43;
    if ( v72 - (unsigned __int64)lpDst[0] < 0x208 )
    {
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(lpDst, 520);
      goto LABEL_43;
    }
    v21 = 520 - (unsigned __int64)((char *)lpDst[1] - (char *)lpDst[0]);
    memset_0(lpDst[1], 0, v21);
    v20 = (LPWSTR)((char *)v19 + v21);
  }
  else
  {
    v20 = lpDst[0] + 260;
  }
  lpDst[1] = v20;
LABEL_43:
  v22 = (const WCHAR *)lpSrc;
  if ( si128.m128i_i64[1] > 7uLL )
    v22 = lpSrc[0];
  v23 = ExpandEnvironmentStringsW(v22, lpDst[0], 0x104u);
  if ( !v23 )
  {
    v68[0] = GetLastError();
    errorlib::scoped_error<hresult_error::tag>::make_initiated<unsigned long>(a1, v68);
LABEL_47:
    std::vector<unsigned char>::_Tidy(lpDst);
    std::wstring::_Tidy_deallocate(lpSrc);
    goto LABEL_35;
  }
  if ( v23 > 0x104 )
  {
    *a1 = -2146435064;
    a1[1] = 1;
    errorlib::error_initiated<errorlib::scoped_error<hresult_error::tag>>();
    std::vector<unsigned char>::_Tidy(lpDst);
    if ( si128.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(lpSrc[0], 2 * si128.m128i_i64[1] + 2);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(lpSrc[0]) = 0;
    if ( v91 > 7 )
      std::_Deallocate<16>(v89, 2 * v91 + 2);
    v90 = 0;
    v91 = 7;
    LOWORD(v89) = 0;
    std::vector<unsigned char>::_Tidy(&v80);
    std::vector<unsigned char>::_Tidy(&v73);
    goto LABEL_127;
  }
  *(_OWORD *)lpPathName = 0;
  v93 = 0;
  v94 = 0;
  v24 = std::_WChar_traits<unsigned short>::length(lpDst[0]);
  std::wstring::_Construct<1,unsigned short const *>(lpPathName, v25, v24);
  Src = 0;
  v96 = 0;
  v26 = lpPathName;
  if ( v94 > 7 )
    v26 = (LPCWSTR *)lpPathName[0];
  std::wstring::_Construct<2,unsigned short const *>(&Src, v26, v93);
  std::_WChar_traits<unsigned short>::length(L"\\");
  std::wstring::_Append<unsigned short>(&Src);
  std::wstring::_Append<unsigned short>(&Src);
  std::_WChar_traits<unsigned short>::length(L".bmp");
  std::wstring::_Append<unsigned short>(&Src);
  phContext = 0;
  v27 = (int *)DevhlprGenerateBitmapFromImageBlobInternal(&v66, &v73, &phContext);
  v64 = *v27;
  v28 = v64;
  *v27 = v18;
  v27[1] = 3;
  v65 = 3;
  if ( v28 < 0 )
  {
    *a1 = v28;
    a1[1] = 2;
    v65 = 5;
    errorlib::scoped_error<hresult_error::tag>::report(a1, 3);
LABEL_58:
    std::wstring::_Tidy_deallocate(&Src);
    std::wstring::_Tidy_deallocate(lpPathName);
    goto LABEL_47;
  }
  TokenHandle = (void *)-1LL;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    v68[0] = LastError;
    errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(&v66, v31, v68);
    errorlib::specific_error_exception<winerror_error::tag>::specific_error_exception<winerror_error::tag>(
      &pExceptionObject,
      &v66);
    throw (errorlib::specific_error_exception<winerror_error::tag> *)&pExceptionObject;
  }
  if ( !RevertToSelf() )
  {
    v33 = GetLastError();
    if ( !v33 )
      v33 = 1287;
    v68[0] = v33;
    errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(&v66, v34, v68);
    errorlib::specific_error_exception<winerror_error::tag>::specific_error_exception<winerror_error::tag>(
      &pExceptionObject,
      &v66);
    throw (errorlib::specific_error_exception<winerror_error::tag> *)&pExceptionObject;
  }
  *(_QWORD *)&v78 = &TokenHandle;
  WORD4(v78) = 256;
  v35 = (const WCHAR *)lpPathName;
  if ( v94 > 7 )
    v35 = lpPathName[0];
  NestedDirectory = CreateNestedDirectory(v35, v32);
  v66 = (unsigned int)NestedDirectory | 0x200000000LL;
  if ( NestedDirectory >= 0 )
  {
    errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<hresult_error::tag> &>(&v66);
    v64 = NestedDirectory;
    v65 = 3;
    v101 = 0;
    EncoderClsidInternal = (int *)DevhlprGetEncoderClsidInternal(&v66, v37, &v101);
    v64 = *EncoderClsidInternal;
    v39 = v64;
    *EncoderClsidInternal = NestedDirectory;
    EncoderClsidInternal[1] = 3;
    errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(EncoderClsidInternal);
    v65 = 3;
    if ( v39 < 0 )
    {
      *a1 = v39;
      a1[1] = 2;
      v65 = 5;
      errorlib::scoped_error<hresult_error::tag>::report(a1, 3);
LABEL_72:
      wil::details::ScopeExitFnGuard__lambda_650b069bedae799f787ef4ee3bedeed8___::operator()(&v78);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      goto LABEL_58;
    }
    *(_QWORD *)&pExceptionObject = &Gdiplus::Image::`vftable';
    v66 = 0;
    v40 = GdipCreateBitmapFromHBITMAP(phContext, 0, &v66);
    v41 = v66;
    *((_QWORD *)&pExceptionObject + 1) = v66;
    LODWORD(v84) = 0;
    v42 = HRESULT_FROM_GDIPLUS(v40);
    v62 = v42;
    v63 = 2;
    if ( v42 < 0 )
    {
      errorlib::error_received<errorlib::scoped_error<hresult_error::tag>>();
      errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<hresult_error::tag> &>(&v62);
      v64 = v42;
      v62 = v39;
      v63 = 3;
      errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v62);
      *a1 = v42;
      a1[1] = 2;
      v65 = 5;
      errorlib::scoped_error<hresult_error::tag>::report(a1, 3);
      GdipDisposeImage(v41);
      goto LABEL_72;
    }
    errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<hresult_error::tag> &>(&v62);
    v64 = v42;
    v62 = v39;
    v63 = 3;
    errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v62);
    v65 = 3;
    p_Src = &Src;
    if ( v96.m128i_i64[1] > 7uLL )
      p_Src = (__int128 *)Src;
    v44 = GdipSaveImageToFile(v41, p_Src, &v101, 0);
    if ( v44 )
      LODWORD(v84) = v44;
    else
      v44 = 0;
    v45 = HRESULT_FROM_GDIPLUS(v44);
    v62 = v45;
    v63 = 2;
    if ( v45 < 0 )
    {
      errorlib::error_received<errorlib::scoped_error<hresult_error::tag>>();
      errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<hresult_error::tag> &>(&v62);
      v64 = v45;
      v62 = v42;
      v63 = 3;
      errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v62);
      *a1 = v45;
      a1[1] = 2;
      v65 = 5;
      errorlib::error_propagated<errorlib::scoped_error<hresult_error::tag>>();
      GdipDisposeImage(v41);
      wil::details::ScopeExitFnGuard__lambda_650b069bedae799f787ef4ee3bedeed8___::operator()(&v78);
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(TokenHandle);
      if ( v96.m128i_i64[1] > 7uLL )
        std::_Deallocate<16>(Src, 2 * v96.m128i_i64[1] + 2);
      v52 = _mm_load_si128((const __m128i *)&_xmm);
      v96 = v52;
      LOWORD(Src) = 0;
      if ( v94 > 7 )
        std::_Deallocate<16>(lpPathName[0], 2 * v94 + 2);
      v93 = 0;
      v94 = 7;
      LOWORD(lpPathName[0]) = 0;
      std::vector<unsigned char>::_Tidy(lpDst);
      if ( si128.m128i_i64[1] > 7uLL )
        std::_Deallocate<16>(lpSrc[0], 2 * si128.m128i_i64[1] + 2);
      si128 = v52;
      LOWORD(lpSrc[0]) = 0;
      v51 = v91;
      if ( v91 <= 7 )
        goto LABEL_102;
    }
    else
    {
      errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<hresult_error::tag> &>(&v62);
      v64 = v45;
      v62 = v42;
      v63 = 3;
      errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v62);
      v65 = 3;
      v99 = 0;
      v100 = 0;
      v46 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
      std::wstring::_Construct<2,unsigned short const *>(&v99, v46, *(_QWORD *)(a4 + 16));
      std::_WChar_traits<unsigned short>::length(L"\\");
      std::wstring::_Append<unsigned short>(&v99);
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v89);
      std::wstring::_Append<unsigned short>(&v99);
      std::_WChar_traits<unsigned short>::length(L".bmp");
      std::wstring::_Append<unsigned short>(&v99);
      v47 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v99);
      v48 = std::_WChar_traits<unsigned short>::length(v47);
      std::wstring::_Assign<unsigned short>(v85, v49, v48);
      *a1 = v45;
      a1[1] = 2;
      v65 = 5;
      if ( v100.m128i_i64[1] > 7uLL )
        std::_Deallocate<16>(v99, 2 * v100.m128i_i64[1] + 2);
      v50 = _mm_load_si128((const __m128i *)&_xmm);
      v100 = v50;
      LOWORD(v99) = 0;
      GdipDisposeImage(v41);
      wil::details::ScopeExitFnGuard__lambda_650b069bedae799f787ef4ee3bedeed8___::operator()(&v78);
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(TokenHandle);
      if ( v96.m128i_i64[1] > 7uLL )
        std::_Deallocate<16>(Src, 2 * v96.m128i_i64[1] + 2);
      v96 = v50;
      LOWORD(Src) = 0;
      if ( v94 > 7 )
        std::_Deallocate<16>(lpPathName[0], 2 * v94 + 2);
      v93 = 0;
      v94 = 7;
      LOWORD(lpPathName[0]) = 0;
      std::vector<unsigned char>::_Tidy(lpDst);
      if ( si128.m128i_i64[1] > 7uLL )
        std::_Deallocate<16>(lpSrc[0], 2 * si128.m128i_i64[1] + 2);
      si128 = v50;
      LOWORD(lpSrc[0]) = 0;
      v51 = v91;
      if ( v91 <= 7 )
        goto LABEL_102;
    }
    std::_Deallocate<16>(v89, 2 * v51 + 2);
LABEL_102:
    LOWORD(v89) = 0;
    v91 = 7;
    v90 = 0;
    std::vector<unsigned char>::_Tidy(&v80);
    std::vector<unsigned char>::_Tidy(&v73);
    if ( !(unsigned __int8)errorlib::ErrorDisposition::safe(5) )
      metalib::FailFast((metalib *)0x80004004LL, v53);
    goto LABEL_127;
  }
  errorlib::error_received<errorlib::scoped_error<hresult_error::tag>>();
  errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<hresult_error::tag> &>(&v66);
  v64 = NestedDirectory;
  *a1 = NestedDirectory;
  a1[1] = 2;
  v65 = 5;
  errorlib::error_propagated<errorlib::scoped_error<hresult_error::tag>>();
  wil::details::ScopeExitFnGuard__lambda_650b069bedae799f787ef4ee3bedeed8___::operator()(&v78);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  if ( v96.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(Src, 2 * v96.m128i_i64[1] + 2);
  v54 = _mm_load_si128((const __m128i *)&_xmm);
  v96 = v54;
  LOWORD(Src) = 0;
  if ( v94 > 7 )
    std::_Deallocate<16>(lpPathName[0], 2 * v94 + 2);
  v93 = 0;
  v94 = 7;
  LOWORD(lpPathName[0]) = 0;
  v55 = lpDst[0];
  if ( lpDst[0] )
  {
    v56 = v72 - (unsigned __int64)lpDst[0];
    v66 = v72 - (unsigned __int64)lpDst[0];
    phContext = (SCARDCONTEXT)lpDst[0];
    if ( v72 - (unsigned __int64)lpDst[0] >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned((void **)&phContext, &v66);
      v56 = v66;
      v55 = (LPWSTR)phContext;
    }
    operator delete(v55, v56);
    *(_OWORD *)lpDst = 0;
    v72 = 0;
  }
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(lpSrc[0], 2 * si128.m128i_i64[1] + 2);
  si128 = v54;
  LOWORD(lpSrc[0]) = 0;
  if ( v91 > 7 )
    std::_Deallocate<16>(v89, 2 * v91 + 2);
  v90 = 0;
  v91 = 7;
  LOWORD(v89) = 0;
  v57 = (void *)v80;
  if ( (_QWORD)v80 )
  {
    v58 = v81 - v80;
    v66 = v81 - v80;
    phContext = v80;
    if ( (unsigned __int64)(v81 - v80) >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned((void **)&phContext, &v66);
      v58 = v66;
      v57 = (void *)phContext;
    }
    operator delete(v57, v58);
  }
  v59 = (void *)v73;
  if ( v73 )
  {
    v60 = v75 - v73;
    v66 = v75 - v73;
    phContext = v73;
    if ( v75 - v73 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned((void **)&phContext, &v66);
      v60 = v66;
      v59 = (void *)phContext;
    }
    operator delete(v59, v60);
  }
LABEL_127:
  std::wstring::_Tidy_deallocate(a2);
  std::wstring::_Tidy_deallocate(a3);
  std::wstring::_Tidy_deallocate(a4);
  return a1;
}

```

## disassembly

```asm
0x1800075d0  push    rbp
0x1800075d2  push    rbx
0x1800075d3  push    rsi
0x1800075d4  push    rdi
0x1800075d5  push    r12
0x1800075d7  push    r13
0x1800075d9  push    r14
0x1800075db  push    r15
0x1800075dd  lea     rbp, [rsp-0F8h]
0x1800075e5  sub     rsp, 1F8h
0x1800075ec  movaps  [rsp+230h+var_50], xmm6
0x1800075f4  mov     rax, cs:__security_cookie
0x1800075fb  xor     rax, rsp
0x1800075fe  mov     [rbp+130h+var_58], rax
0x180007605  mov     rsi, r9
0x180007608  mov     r14, r8
0x18000760b  mov     rdi, rdx
0x18000760e  mov     r12, rcx
0x180007611  mov     [rbp+130h+var_128], rcx
0x180007615  mov     [rbp+130h+var_120], rdx
0x180007619  mov     [rbp+130h+var_118], r8
0x18000761d  mov     [rbp+130h+var_110], r9
0x180007621  mov     rax, [rbp+130h+arg_20]
0x180007628  mov     [rbp+130h+var_128], rax
0x18000762c  xor     r13d, r13d
0x18000762f  mov     [rbp+130h+var_188], r13d
0x180007633  mov     [rsp+230h+var_1E8], r13d
0x180007638  mov     [rsp+230h+var_1E4], 1
0x180007640  lea     rcx, [rbp+130h+var_1A0]
0x180007644  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::vector<uchar>(void)
0x180007649  nop
0x18000764a  lea     rax, [rsp+230h+var_1F0]
0x18000764f  mov     qword ptr [rbp+130h+var_180], rax
0x180007653  xorps   xmm0, xmm0
0x180007656  movups  [rbp+130h+var_168], xmm0
0x18000765a  mov     [rbp+130h+var_158], r13
0x18000765e  mov     [rbp+130h+var_150], r13
0x180007662  cmp     qword ptr [rdx+18h], 7
0x180007667  jbe     short loc_18000766C
0x180007669  mov     rdx, [rdx]
0x18000766c  mov     r8, [rdi+10h]
0x180007670  lea     rcx, [rbp+130h+var_168]
0x180007674  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180007679  lea     rax, [rbp+130h+var_168]
0x18000767d  mov     [rsp+230h+var_1C0], rax
0x180007682  mov     [rsp+230h+var_1F0], r13d
0x180007687  mov     [rsp+230h+var_1EC], 1
0x18000768f  mov     [rbp+130h+var_188], 2
0x180007696  mov     [rsp+230h+phContext], r13
0x18000769b  lea     r9, [rsp+230h+phContext]; phContext
0x1800076a0  xor     r8d, r8d; pvReserved2
0x1800076a3  xor     edx, edx; pvReserved1
0x1800076a5  mov     ecx, 2; dwScope
0x1800076aa  call    cs:__imp_SCardEstablishContext
0x1800076b0  mov     ebx, eax
0x1800076b2  test    eax, eax
0x1800076b4  jle     short loc_1800076BF
0x1800076b6  movzx   ebx, ax
0x1800076b9  or      ebx, 80070000h
0x1800076bf  mov     [rsp+230h+var_1D0], ebx
0x1800076c3  mov     [rsp+230h+var_1CC], 2
0x1800076cb  test    ebx, ebx
0x1800076cd  jns     short loc_1800076D4
0x1800076cf  call    ??$error_received@V?$scoped_error@Utag@hresult_error@@@errorlib@@@errorlib@@YAXAEBV?$scoped_error@Utag@hresult_error@@@0@AEBUtag@hresult_error@@@Z; errorlib::error_received<errorlib::scoped_error<hresult_error::tag>>(errorlib::scoped_error<hresult_error::tag> const &,hresult_error::tag const &)
0x1800076d4  lea     rcx, [rsp+230h+var_1D0]
0x1800076d9  call    ??$optionalFailFastCheck@AEAV?$scoped_error@Utag@hresult_error@@@errorlib@@@detail@errorlib@@YA_NAEAV?$scoped_error@Utag@hresult_error@@@1@@Z; errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<hresult_error::tag> &>(errorlib::scoped_error<hresult_error::tag> &)
0x1800076de  mov     ecx, [rsp+230h+var_1EC]
0x1800076e2  cmp     ecx, 1
0x1800076e5  jz      short loc_1800076FD
0x1800076e7  lea     eax, [rcx-3]
0x1800076ea  cmp     eax, 3
0x1800076ed  jbe     short loc_1800076FD
0x1800076ef  mov     ecx, 80004004h; this
0x1800076f4  call    ?FailFast@metalib@@YAXK@Z; metalib::FailFast(ulong)
0x1800076f9  mov     ecx, [rsp+230h+var_1EC]
0x1800076fd  mov     [rsp+230h+var_1F0], ebx
0x180007701  mov     [rsp+230h+var_1EC], 2
0x180007709  cmp     ecx, 1
0x18000770c  jz      short loc_180007724
0x18000770e  lea     eax, [rcx-3]
0x180007711  cmp     eax, 3
0x180007714  jbe     short loc_180007724
0x180007716  mov     ecx, 80004004h; this
0x18000771b  call    ?FailFast@metalib@@YAXK@Z; metalib::FailFast(ulong)
0x180007720  mov     ebx, [rsp+230h+var_1F0]
0x180007724  mov     r15d, 3
0x18000772a  mov     [rsp+230h+var_1EC], r15d
0x18000772f  test    ebx, ebx
0x180007731  jns     short loc_180007751
0x180007733  mov     [rbp+130h+var_188], r13d
0x180007737  mov     rcx, [rsp+230h+phContext]; hContext
0x18000773c  test    rcx, rcx
0x18000773f  jz      loc_1800077F2
0x180007745  call    cs:__imp_SCardReleaseContext
0x18000774b  nop
0x18000774c  jmp     loc_1800077F2
0x180007751  mov     [rsp+230h+var_1E0], r13
0x180007756  mov     [rbp+130h+var_184], 0FFFFFFFFh
0x18000775d  lea     rdx, [rbp+130h+var_168]
0x180007761  cmp     [rbp+130h+var_150], 7
0x180007766  cmova   rdx, qword ptr [rbp+130h+var_168]
0x18000776b  lea     r9, [rbp+130h+var_184]
0x18000776f  lea     r8, [rsp+230h+var_1E0]
0x180007774  mov     rcx, [rsp+230h+phContext]
0x180007779  call    cs:__imp_SCardGetReaderIconW
0x18000777f  test    eax, eax
0x180007781  jle     short loc_18000778B
0x180007783  movzx   eax, ax
0x180007786  or      eax, 80070000h
0x18000778b  mov     [rsp+230h+var_1D0], eax
0x18000778f  lea     rdx, [rsp+230h+var_1D0]
0x180007794  lea     rcx, [rsp+230h+var_1F0]
0x180007799  call    ??$receive@J@?$scoped_error@Utag@hresult_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<hresult_error::tag>::receive<long>(long &&)
0x18000779e  mov     [rsp+230h+var_1EC], r15d
0x1800077a3  cmp     [rsp+230h+var_1F0], 0
0x1800077a8  jl      short loc_1800077E7
0x1800077aa  lea     rax, [rsp+230h+phContext]
0x1800077af  mov     qword ptr [rbp+130h+pExceptionObject], rax
0x1800077b3  lea     rax, [rsp+230h+var_1E0]
0x1800077b8  mov     qword ptr [rbp+130h+pExceptionObject+8], rax
0x1800077bc  mov     word ptr [rbp+130h+var_138], 100h
0x1800077c2  mov     rdx, [rsp+230h+var_1E0]
0x1800077c7  mov     r8, rdx
0x1800077ca  sub     r8, rdx
0x1800077cd  mov     eax, [rbp+130h+var_184]
0x1800077d0  add     r8, rax
0x1800077d3  lea     rcx, [rbp+130h+var_1A0]
0x1800077d7  call    ??$_Assign_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXPEAE_K@Z; std::vector<uchar>::_Assign_counted_range<uchar *>(uchar *,unsigned __int64)
0x1800077dc  nop
0x1800077dd  lea     rcx, [rbp+130h+pExceptionObject]
0x1800077e1  call    wil__details__ScopeExitFnGuard__lambda_ef7b62ae24276b172a03c6ede390e4c4_____operator__
0x1800077e6  nop
0x1800077e7  lea     rcx, [rsp+230h+phContext]
0x1800077ec  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?SCardReleaseContext@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&SCardReleaseContext(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&SCardReleaseContext(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800077f1  nop
0x1800077f2  lea     rcx, [rbp+130h+var_168]
0x1800077f6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800077fb  mov     eax, [rsp+230h+var_1F0]
0x1800077ff  mov     [rsp+230h+var_1E8], eax
0x180007803  mov     [rsp+230h+var_1E4], r15d
0x180007808  test    eax, eax
0x18000780a  jns     short loc_180007846
0x18000780c  mov     [r12], eax
0x180007810  mov     dword ptr [r12+4], 2
0x180007819  mov     [rsp+230h+var_1E4], 5
0x180007821  mov     edx, r15d
0x180007824  mov     rcx, r12
0x180007827  call    ?report@?$scoped_error@Utag@hresult_error@@@errorlib@@AEAAXW4type@ErrorSource@2@@Z; errorlib::scoped_error<hresult_error::tag>::report(errorlib::ErrorSource::type)
0x18000782c  nop
0x18000782d  lea     rcx, [rbp+130h+var_1A0]
0x180007831  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180007836  nop
0x180007837  lea     rcx, [rsp+230h+var_1E8]
0x18000783c  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x180007841  jmp     loc_180008506
0x180007846  lea     rcx, [rbp+130h+var_168]
0x18000784a  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::vector<uchar>(void)
0x18000784f  nop
0x180007850  xorps   xmm0, xmm0
0x180007853  movdqu  [rbp+130h+pExceptionObject], xmm0
0x180007858  mov     [rbp+130h+var_138], r13
0x18000785c  mov     rdx, [rbp+130h+var_198]
0x180007860  sub     rdx, [rbp+130h+var_1A0]
0x180007864  lea     r9, [rbp+130h+var_198]
0x180007868  lea     r8, [rbp+130h+var_1A0]
0x18000786c  lea     rcx, [rbp+130h+pExceptionObject]
0x180007870  call    ??$_Construct_n@AEBQEAEAEBQEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBQEAE1@Z; std::vector<uchar>::_Construct_n<uchar * const &,uchar * const &>(unsigned __int64,uchar * const &,uchar * const &)
0x180007875  lea     rax, [rbp+130h+pExceptionObject]
0x180007879  mov     [rsp+230h+var_1C0], rax
0x18000787e  mov     dword ptr [rsp+230h+phContext], r13d
0x180007883  mov     dword ptr [rsp+230h+phContext+4], 1
0x18000788b  xorps   xmm0, xmm0
0x18000788e  movdqu  [rbp+130h+var_180], xmm0
0x180007893  mov     [rbp+130h+var_170], r13
0x180007897  lea     rcx, [rbp+130h+var_180]
0x18000789b  call    ??$_Construct_n@$$V@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Construct_n<>(unsigned __int64)
0x1800078a0  nop
0x1800078a1  mov     rdx, qword ptr [rbp+130h+var_180]
0x1800078a5  mov     r9, qword ptr [rbp+130h+pExceptionObject]
0x1800078a9  mov     ecx, dword ptr [rbp+130h+var_180+8]
0x1800078ac  sub     ecx, edx
0x1800078ae  mov     eax, dword ptr [rbp+130h+pExceptionObject+8]
0x1800078b1  sub     eax, r9d
0x1800078b4  mov     [rsp+230h+var_200], ecx
0x1800078b8  mov     [rsp+230h+var_208], rdx
0x1800078bd  mov     [rsp+230h+var_210], eax
0x1800078c1  xor     r8d, r8d
0x1800078c4  xor     edx, edx
0x1800078c6  mov     ecx, 41h ; 'A'
0x1800078cb  call    cs:__imp_BCryptHash
0x1800078d1  mov     ebx, eax
0x1800078d3  mov     [rsp+230h+var_1F0], eax
0x1800078d7  mov     [rsp+230h+var_1EC], 2
0x1800078df  mov     r15d, eax
0x1800078e2  shr     r15d, 1Eh
0x1800078e6  lea     eax, [r15-1]
0x1800078ea  cmp     eax, 2
0x1800078ed  jbe     loc_180007996
0x1800078f3  lea     rcx, [rsp+230h+var_1F0]
0x1800078f8  call    ??$optionalFailFastCheck@AEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@@detail@errorlib@@YA_NAEAV?$scoped_error@Utag@ntstatus_error@@@1@@Z; errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<ntstatus_error::tag> &>(errorlib::scoped_error<ntstatus_error::tag> &)
0x1800078fd  mov     dword ptr [rsp+230h+phContext], ebx
0x180007901  mov     [rsp+230h+var_1F0], r13d
0x180007906  mov     [rsp+230h+var_1EC], 1
0x18000790e  lea     rcx, [rsp+230h+var_1F0]
0x180007913  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x180007918  mov     dword ptr [rsp+230h+phContext+4], 3
0x180007920  mov     rdx, qword ptr [rbp+130h+var_180]
0x180007924  mov     r8, qword ptr [rbp+130h+var_180+8]
0x180007928  sub     r8, rdx
0x18000792b  lea     rcx, [rbp+130h+var_168]
0x18000792f  call    ??$_Assign_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXPEAE_K@Z; std::vector<uchar>::_Assign_counted_range<uchar *>(uchar *,unsigned __int64)
0x180007934  test    ebx, ebx
0x180007936  jns     short loc_18000793E
0x180007938  call    ??$error_initiated@V?$scoped_error@Utag@hresult_error@@@errorlib@@@errorlib@@YAXAEBV?$scoped_error@Utag@hresult_error@@@0@AEBUtag@hresult_error@@@Z; errorlib::error_initiated<errorlib::scoped_error<hresult_error::tag>>(errorlib::scoped_error<hresult_error::tag> const &,hresult_error::tag const &)
0x18000793d  nop
0x18000793e  lea     rcx, [rbp+130h+var_180]
0x180007942  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180007947  nop
0x180007948  lea     rcx, [rbp+130h+pExceptionObject]
0x18000794c  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180007951  mov     [rsp+230h+var_1E8], ebx
0x180007955  mov     [rsp+230h+var_1E4], 3
0x18000795d  test    ebx, ebx
0x18000795f  jns     loc_180007A07
0x180007965  mov     [r12], ebx
0x180007969  mov     dword ptr [r12+4], 2
0x180007972  mov     [rsp+230h+var_1E4], 5
0x18000797a  mov     edx, 3
0x18000797f  mov     rcx, r12
0x180007982  call    ?report@?$scoped_error@Utag@hresult_error@@@errorlib@@AEAAXW4type@ErrorSource@2@@Z; errorlib::scoped_error<hresult_error::tag>::report(errorlib::ErrorSource::type)
0x180007987  nop
0x180007988  lea     rcx, [rbp+130h+var_168]
0x18000798c  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180007991  jmp     loc_18000782D
0x180007996  call    ??$error_received@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@@errorlib@@YAXAEBV?$scoped_error@Utag@ntstatus_error@@@0@AEBUtag@ntstatus_error@@@Z; errorlib::error_received<errorlib::scoped_error<ntstatus_error::tag>>(errorlib::scoped_error<ntstatus_error::tag> const &,ntstatus_error::tag const &)
0x18000799b  lea     rcx, [rsp+230h+var_1F0]
0x1800079a0  call    ??$optionalFailFastCheck@AEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@@detail@errorlib@@YA_NAEAV?$scoped_error@Utag@ntstatus_error@@@1@@Z; errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<ntstatus_error::tag> &>(errorlib::scoped_error<ntstatus_error::tag> &)
0x1800079a5  mov     dword ptr [rsp+230h+phContext], ebx
0x1800079a9  mov     [rsp+230h+var_1F0], r13d
0x1800079ae  mov     [rsp+230h+var_1EC], 1
0x1800079b6  lea     rcx, [rsp+230h+var_1F0]
0x1800079bb  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x1800079c0  mov     dword ptr [rsp+230h+phContext+4], 3
0x1800079c8  lea     eax, [r15-1]
0x1800079cc  cmp     eax, 2
0x1800079cf  ja      loc_180007920
0x1800079d5  mov     [rsp+230h+var_1D0], ebx
0x1800079d9  lea     rdx, [rsp+230h+var_1D0]
0x1800079de  lea     rcx, [rsp+230h+var_1E0]
0x1800079e3  call    ??$make_initiated@K@?$scoped_error@Utag@hresult_error@@@errorlib@@SA?AV01@$$QEAK@Z; errorlib::scoped_error<hresult_error::tag>::make_initiated<ulong>(ulong &&)
0x1800079e8  nop
0x1800079e9  lea     rcx, [rbp+130h+var_180]
0x1800079ed  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800079f2  nop
0x1800079f3  lea     rcx, [rsp+230h+phContext]
0x1800079f8  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x1800079fd  nop
0x1800079fe  mov     ebx, dword ptr [rsp+230h+var_1E0]
0x180007a02  jmp     loc_180007948
0x180007a07  xorps   xmm0, xmm0
0x180007a0a  movups  [rbp+130h+var_108], xmm0
0x180007a0e  mov     [rbp+130h+var_F8], r13
0x180007a12  mov     [rbp+130h+var_F0], r13
0x180007a16  lea     rcx, [rbp+130h+var_108]
0x180007a1a  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180007a1f  nop
0x180007a20  lea     r8, [rbp+130h+var_108]
0x180007a24  lea     rdx, [rbp+130h+var_168]
0x180007a28  lea     rcx, [rsp+230h+var_1E0]
0x180007a2d  call    ?DevhlprConvertHashToStringInternal@@YA?AV?$scoped_error@Utag@hresult_error@@@errorlib@@AEAV?$vector@EV?$allocator@E@std@@@std@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; DevhlprConvertHashToStringInternal(std::vector<uchar> &,std::wstring &)
0x180007a32  mov     r15d, [rax]
0x180007a35  mov     [rsp+230h+var_1E8], r15d
0x180007a3a  mov     [rax], ebx
0x180007a3c  mov     ecx, 3
0x180007a41  mov     [rax+4], ecx
0x180007a44  mov     [rsp+230h+var_1E4], ecx
0x180007a48  test    r15d, r15d
0x180007a4b  jns     short loc_180007A85
0x180007a4d  mov     [r12], r15d
0x180007a51  mov     dword ptr [r12+4], 2
0x180007a5a  mov     [rsp+230h+var_1E4], 5
0x180007a62  mov     edx, ecx
0x180007a64  mov     rcx, r12
0x180007a67  call    ?report@?$scoped_error@Utag@hresult_error@@@errorlib@@AEAAXW4type@ErrorSource@2@@Z; errorlib::scoped_error<hresult_error::tag>::report(errorlib::ErrorSource::type)
0x180007a6c  nop
0x180007a6d  lea     rcx, [rbp+130h+var_108]
0x180007a71  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180007a76  nop
0x180007a77  lea     rcx, [rbp+130h+var_168]
0x180007a7b  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180007a80  jmp     loc_18000782D
0x180007a85  mov     r8, rsi
0x180007a88  mov     rdx, r14
0x180007a8b  lea     rcx, [rbp+130h+lpSrc]
0x180007a92  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@0@Z; std::operator+<ushort>(std::wstring const &,std::wstring const &)
0x180007a97  nop
0x180007a98  lea     rcx, [rsp+230h+lpDst]
0x180007a9d  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::vector<uchar>(void)
0x180007aa2  nop
0x180007aa3  mov     rdx, [rsp+230h+lpDst]
  ... truncated ...
```
