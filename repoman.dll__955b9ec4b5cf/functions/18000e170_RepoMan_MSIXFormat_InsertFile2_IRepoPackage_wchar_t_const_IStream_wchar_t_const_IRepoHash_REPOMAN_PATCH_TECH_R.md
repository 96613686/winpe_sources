# RepoMan::MSIXFormat::InsertFile2(IRepoPackage *,wchar_t const *,IStream *,wchar_t const *,IRepoHash *,_REPOMAN_PATCH_TECH,_REPOMAN_FILE_TAGS,_REPOMAN_PATH_TAGS,IRepoFile * *)

- ea: `0x18000e170`
- end: `0x18000e7a2`
- name: `?InsertFile2@MSIXFormat@RepoMan@@UEAAJPEAUIRepoPackage@@PEB_WPEAUIStream@@1PEAUIRepoHash@@W4_REPOMAN_PATCH_TECH@@W4_REPOMAN_FILE_TAGS@@W4_REPOMAN_PATH_TAGS@@PEAPEAUIRepoFile@@@Z`
- size: `1586`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180002010`
- `0x180003710`
- `0x1800038ac`
- `0x18000d5f4`
- `0x18000e170`
- `0x18000f164`
- `0x180013b14`
- `0x180016a6c`
- `0x180016af0`
- `0x180016f50`
- `0x18001b5b0`
- `0x18001b718`
- `0x18001b89c`
- `0x1800220e4`
- `0x18002f940`
- `0x18002f9b0`
- `0x18018aed8`
- `0x18018b53c`
- `0x18019a840`
- `0x18019f7a0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000e4ab`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000e66b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000e4ab`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000e66b`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000e4a4`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000e664`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000e4a4`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000e664`

## string_xrefs

- `0x18000e1d2`: `MSIXFormat.InsertFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall RepoMan::MSIXFormat::InsertFile2(
        _QWORD *a1,
        __int64 a2,
        const wchar_t *a3,
        struct IStream *a4,
        _WORD *a5,
        __int64 a6,
        int a7,
        int a8,
        int a9,
        _QWORD *a10)
{
  _QWORD *v13; // rdi
  _QWORD *v14; // rax
  __int64 v15; // r9
  __int64 v16; // rcx
  int v17; // ecx
  __int64 v18; // rcx
  unsigned int v19; // eax
  const char *v20; // r9
  __int64 v21; // rdi
  __int64 v22; // rcx
  unsigned int v23; // eax
  const char *v24; // r9
  __int64 v25; // rcx
  __int64 v26; // rsi
  void *v27; // rcx
  __int64 v28; // rsi
  __int64 v29; // r14
  unsigned int (__fastcall *v30)(__int64, _QWORD, const WCHAR *, __int64, __int64, _QWORD *, __int64 *); // r13
  _QWORD *v31; // rax
  RepoMan *v32; // rcx
  const char *v33; // r9
  unsigned int v34; // eax
  const char *v35; // r9
  unsigned int v36; // eax
  const char *v37; // r9
  __int64 v38; // rax
  __int64 v39; // rcx
  void *v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  int v45; // r8d
  __int64 result; // rax
  void *Reserved; // [rsp+20h] [rbp-188h]
  __int64 v48; // [rsp+60h] [rbp-148h] BYREF
  int v49[2]; // [rsp+68h] [rbp-140h] BYREF
  __int64 v50; // [rsp+70h] [rbp-138h] BYREF
  __int64 v51; // [rsp+78h] [rbp-130h] BYREF
  int v52[2]; // [rsp+80h] [rbp-128h] BYREF
  __int64 v53; // [rsp+88h] [rbp-120h] BYREF
  __int64 v54; // [rsp+90h] [rbp-118h] BYREF
  __int64 v55; // [rsp+98h] [rbp-110h] BYREF
  __int64 v56; // [rsp+A0h] [rbp-108h] BYREF
  _QWORD *v57; // [rsp+A8h] [rbp-100h]
  _BYTE v58[48]; // [rsp+B8h] [rbp-F0h] BYREF
  void *Block[2]; // [rsp+E8h] [rbp-C0h] BYREF
  __m128i v60; // [rsp+F8h] [rbp-B0h]
  WCHAR WideCharStr[8]; // [rsp+108h] [rbp-A0h] BYREF
  __m128i si128; // [rsp+118h] [rbp-90h]
  _BYTE v63[48]; // [rsp+130h] [rbp-78h] BYREF

  v55 = a2;
  v54 = a6;
  v57 = a10;
  RepoMan::Tracer::Tracer(v63, 1, "MSIXFormat.InsertFile");
  try
  {
    if ( !a3 || !*a3 )
      RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
        843,
        (unsigned int)"src\\repoman\\src\\inc\\PackageFormat.hpp",
        (unsigned int)"missing sourceName",
        -2147024809,
        8);
    if ( !a5 || !*a5 )
      RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
        844,
        (unsigned int)"src\\repoman\\src\\inc\\PackageFormat.hpp",
        (unsigned int)"missing targetName",
        -2147024809,
        8);
    RepoMan::MSIXFormat::GetMSIXSDKLogsOnDemandForScope(v58);
    v13 = a1 + 9;
    if ( !*v13 )
    {
      v14 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD *, __int64 *))(*(a1 - 1) + 80LL))(a1 - 1, &v48);
      ____4U__default_delete_V__RowType_U__Column_U__Key_USKU_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_USKUs_234_UNone_Alias_34__Meta_RepoMan___J_Meta_RepoMan__U__Column_U__Key_UBuild_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_UBuilds_234_UNone_Alias_34__Meta_RepoMan___J_23_U__Column_U__Key_UCulture_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_UCultures_234_UNone_Alias_34__Meta_RepoMan___J_23_U__Column_U__Value_UName_Text_Meta_RepoMan__UString_Types_34_UNotNull_Constraints_34__Meta_RepoMan__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___23_U__Column_U__Value_UBrandingName_Text_Meta_RepoMan__UString_Types_34_UNotNull_Constraints_34__Meta_RepoMan__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___23__Meta_RepoMan___std___0A____unique_ptr_V__RowType_U__Column_U__Key_USKU_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_USKUs_234_UNone_Alias_34__Meta_RepoMan___J_Meta_RepoMan__U__Column_U__Key_UBuild_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_UBuilds_234_UNone_Alias_34__Meta_RepoMan___J_23_U__Column_U__Key_UCulture_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_UCultures_234_UNone_Alias_34__Meta_RepoMan___J_23_U__Column_U__Value_UName_Text_Meta_RepoMan__UString_Types_34_UNotNull_Constraints_34__Meta_RepoMan__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___23_U__Column_U__Value_UBrandingName_Text_Meta_RepoMan__UString_Types_34_UNotNull_Constraints_34__Meta_RepoMan__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___23__Meta_RepoMan__U__default_delete_V__RowType_U__Column_U__Key_USKU_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_USKUs_234_UNone_Alias_34__Meta_RepoMan___J_Meta_RepoMan__U__Column_U__Key_UBuild_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_UBuilds_234_UNone_Alias_34__Meta_RepoMan___J_23_U__Column_U__Key_UCulture_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_UCultures_234_UNone_Alias_34__Meta_RepoMan___J_23_U__Column_U__Value_UName_Text_Meta_RepoMan__UString_Types_34_UNotNull_Constraints_34__Meta_RepoMan__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___23_U__Column_U__Value_UBrandingName_Text_Meta_RepoMan__UString_Types_34_UNotNull_Constraints_34__Meta_RepoMan__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___23__Meta_RepoMan___std___std__QEAAAEAV01___QEAV01__Z(
        (_QWORD **)a1 + 9,
        v14);
      __1__unique_ptr_V__RowType_U__Column_U__Key_USKU_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_USKUs_234_UNone_Alias_34__Meta_RepoMan___J_Meta_RepoMan__U__Column_U__Key_UBuild_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_UBuilds_234_UNone_Alias_34__Meta_RepoMan___J_23_U__Column_U__Key_UCulture_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_UCultures_234_UNone_Alias_34__Meta_RepoMan___J_23_U__Column_U__Value_UName_Text_Meta_RepoMan__UString_Types_34_UNotNull_Constraints_34__Meta_RepoMan__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___23_U__Column_U__Value_UBrandingName_Text_Meta_RepoMan__UString_Types_34_UNotNull_Constraints_34__Meta_RepoMan__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___23__Meta_RepoMan__U__default_delete_V__RowType_U__Column_U__Key_USKU_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_USKUs_234_UNone_Alias_34__Meta_RepoMan___J_Meta_RepoMan__U__Column_U__Key_UBuild_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_UBuilds_234_UNone_Alias_34__Meta_RepoMan___J_23_U__Column_U__Key_UCulture_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_UCultures_234_UNone_Alias_34__Meta_RepoMan___J_23_U__Column_U__Value_UName_Text_Meta_RepoMan__UString_Types_34_UNotNull_Constraints_34__Meta_RepoMan__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___23_U__Column_U__Value_UBrandingName_Text_Meta_RepoMan__UString_Types_34_UNotNull_Constraints_34__Meta_RepoMan__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___23__Meta_RepoMan___std___std__QEAA_XZ(&v48);
    }
    v15 = *v13 + 72LL;
    v48 = a1[5];
    v56 = a1[4];
    RepoMan::ComPtr<IRepoBuild>::Make<RepoMan::CRepoBuild,RepoMan::CRepoMan *,RepoMan::Schema *,__int64 &>(
      v49,
      &v56,
      &v48,
      v15);
    Reserved = (void *)_GetFileDigest___MediaBase_VMSIXFormat_RepoMan__V__unique_ptr_V__RowType_U__Column_U__Key_UMedia_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_UMedia_234_UNone_Alias_34__Meta_RepoMan___J_Meta_RepoMan__U__Column_U__Key_UBuild_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_UBuilds_234_UNone_Alias_34__Meta_RepoMan___J_23_U__Column_U__Value_UFormatType_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34__Meta_RepoMan__H_23_U__Column_U__Value_UName_Text_Meta_RepoMan__UString_Types_34_UCaseInsensitive_Constraints_34__Meta_RepoMan__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___23_U__Column_U__Value_UURI_Text_Meta_RepoMan__UString_Types_34_UNotNull_Constraints_34__Meta_RepoMan__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___23__Meta_RepoMan__U__default_delete_V__RowType_U__Column_U__Key_UMedia_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_UMedia_234_UNone_Alias_34__Meta_RepoMan___J_Meta_RepoMan__U__Column_U__Key_UBuild_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_UBuilds_234_UNone_Alias_34__Meta_RepoMan___J_23_U__Column_U__Value_UFormatType_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34__Meta_RepoMan__H_23_U__Column_U__Value_UName_Text_Meta_RepoMan__UString_Types_34_UCaseInsensitive_Constraints_34__Meta_RepoMan__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___23_U__Column_U__Value_UURI_Text_Meta_RepoMan__UString_Types_34_UNotNull_Constraints_34__Meta_RepoMan__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___23__Meta_RepoMan___std___std__UIRepoMedia__UIRepoMediaInternal__UIRepoMsixMedia__UIRangeAware___RepoMan__IEAA_AU__pair_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___K_std__PEAUIStream___Z(
                         v16,
                         WideCharStr,
                         a4);
    _CreateHashObject___MediaBase_VDatFormat_RepoMan__V__unique_ptr_V__RowType_U__Column_U__Key_UMedia_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_UMedia_234_UNone_Alias_34__Meta_RepoMan___J_Meta_RepoMan__U__Column_U__Key_UBuild_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_UBuilds_234_UNone_Alias_34__Meta_RepoMan___J_23_U__Column_U__Value_UFormatType_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34__Meta_RepoMan__H_23_U__Column_U__Value_UName_Text_Meta_RepoMan__UString_Types_34_UCaseInsensitive_Constraints_34__Meta_RepoMan__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___23_U__Column_U__Value_UURI_Text_Meta_RepoMan__UString_Types_34_UNotNull_Constraints_34__Meta_RepoMan__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___23__Meta_RepoMan__U__default_delete_V__RowType_U__Column_U__Key_UMedia_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_UMedia_234_UNone_Alias_34__Meta_RepoMan___J_Meta_RepoMan__U__Column_U__Key_UBuild_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_UBuilds_234_UNone_Alias_34__Meta_RepoMan___J_23_U__Column_U__Value_UFormatType_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34__Meta_RepoMan__H_23_U__Column_U__Value_UName_Text_Meta_RepoMan__UString_Types_34_UCaseInsensitive_Constraints_34__Meta_RepoMan__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___23_U__Column_U__Value_UURI_Text_Meta_RepoMan__UString_Types_34_UNotNull_Constraints_34__Meta_RepoMan__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___23__Meta_RepoMan___std___std__UIRepoMedia__UIRepoMediaInternal__UIRangeAware___RepoMan__IEAA_AV__ComPtr_UIRepoHash___2_PEAUIRepoBuild__PEAUIRepoWriter__AEBU__pair_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___K_std___Z(
      v17,
      (int)v52,
      v49[0],
      a1[7],
      Reserved);
    std::string::_Tidy_deallocate(WideCharStr);
    *(_QWORD *)WideCharStr = 19937;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    _CreateFileObject___MediaBase_VDatFormat_RepoMan__V__unique_ptr_V__RowType_U__Column_U__Key_UMedia_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_UMedia_234_UNone_Alias_34__Meta_RepoMan___J_Meta_RepoMan__U__Column_U__Key_UBuild_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_UBuilds_234_UNone_Alias_34__Meta_RepoMan___J_23_U__Column_U__Value_UFormatType_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34__Meta_RepoMan__H_23_U__Column_U__Value_UName_Text_Meta_RepoMan__UString_Types_34_UCaseInsensitive_Constraints_34__Meta_RepoMan__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___23_U__Column_U__Value_UURI_Text_Meta_RepoMan__UString_Types_34_UNotNull_Constraints_34__Meta_RepoMan__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___23__Meta_RepoMan__U__default_delete_V__RowType_U__Column_U__Key_UMedia_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_UMedia_234_UNone_Alias_34__Meta_RepoMan___J_Meta_RepoMan__U__Column_U__Key_UBuild_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_UBuilds_234_UNone_Alias_34__Meta_RepoMan___J_23_U__Column_U__Value_UFormatType_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34__Meta_RepoMan__H_23_U__Column_U__Value_UName_Text_Meta_RepoMan__UString_Types_34_UCaseInsensitive_Constraints_34__Meta_RepoMan__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___23_U__Column_U__Value_UURI_Text_Meta_RepoMan__UString_Types_34_UNotNull_Constraints_34__Meta_RepoMan__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___23__Meta_RepoMan___std___std__UIRepoMedia__UIRepoMediaInternal__UIRangeAware___RepoMan__IEAA_AV__ComPtr_UIRepoFile___2_PEAUIRepoPackage__PEAUIRepoWriter__PEAUIRepoBuild__PEAUIRepoHash__PEB_W4W4_REPOMAN_PATCH_TECH__W4_REPOMAN_FILE_TAGS__W4_REPOMAN_PATH_TAGS__3_Z(
      (_DWORD)a1 - 8,
      (unsigned int)&v50,
      v55,
      a1[7],
      *(__int64 *)v49,
      *(__int64 *)v52,
      (__int64)a3,
      (__int64)a5,
      a7,
      a8,
      a9,
      v54);
    if ( *a3 == 92 || *a3 == 47 )
      ++a3;
    v18 = a1[6];
    v48 = 0;
    v19 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v18 + 40LL))(v18, 0, 1, &v48);
    RepoMan::RaiseExceptionIfFailed((RepoMan *)v19, 353, (int)"src\\repoman\\src\\inc\\StreamBase.hpp", v20);
    v21 = v48;
    v54 = v48;
    RepoMan::MSIXFormat::AddPayloadFile((RepoMan::MSIXFormat *)(a1 - 1), a4, a3);
    v22 = a1[6];
    v48 = 0;
    v23 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v22 + 40LL))(v22, 0, 1, &v48);
    RepoMan::RaiseExceptionIfFailed((RepoMan *)v23, 353, (int)"src\\repoman\\src\\inc\\StreamBase.hpp", v24);
    v55 = v48 - v21;
    RepoMan::ComPtr<IStream>::Make<RepoMan::SubStream,unsigned __int64 &,unsigned __int64 &,RepoMan::ComPtr<IStream> &>(
      &v53,
      &v54,
      &v55,
      a1 + 6);
    *(_OWORD *)Block = 0;
    v60 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(Block[0]) = 0;
    v26 = _GetFileDigest___MediaBase_VMSIXFormat_RepoMan__V__unique_ptr_V__RowType_U__Column_U__Key_UMedia_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_UMedia_234_UNone_Alias_34__Meta_RepoMan___J_Meta_RepoMan__U__Column_U__Key_UBuild_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_UBuilds_234_UNone_Alias_34__Meta_RepoMan___J_23_U__Column_U__Value_UFormatType_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34__Meta_RepoMan__H_23_U__Column_U__Value_UName_Text_Meta_RepoMan__UString_Types_34_UCaseInsensitive_Constraints_34__Meta_RepoMan__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___23_U__Column_U__Value_UURI_Text_Meta_RepoMan__UString_Types_34_UNotNull_Constraints_34__Meta_RepoMan__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___23__Meta_RepoMan__U__default_delete_V__RowType_U__Column_U__Key_UMedia_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_UMedia_234_UNone_Alias_34__Meta_RepoMan___J_Meta_RepoMan__U__Column_U__Key_UBuild_Id_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34_UBuilds_234_UNone_Alias_34__Meta_RepoMan___J_23_U__Column_U__Value_UFormatType_Text_Meta_RepoMan__UInt_Types_34_UNotNull_Constraints_34__Meta_RepoMan__H_23_U__Column_U__Value_UName_Text_Meta_RepoMan__UString_Types_34_UCaseInsensitive_Constraints_34__Meta_RepoMan__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___23_U__Column_U__Value_UURI_Text_Meta_RepoMan__UString_Types_34_UNotNull_Constraints_34__Meta_RepoMan__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___23__Meta_RepoMan___std___std__UIRepoMedia__UIRepoMediaInternal__UIRepoMsixMedia__UIRangeAware___RepoMan__IEAA_AU__pair_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___K_std__PEAUIStream___Z(
            v25,
            WideCharStr,
            v53);
    if ( Block != (void **)v26 )
    {
      if ( v60.m128i_i64[1] > 0xFuLL )
      {
        v27 = Block[0];
        if ( (unsigned __int64)(v60.m128i_i64[1] + 1) >= 0x1000 )
        {
          v27 = (void *)*((_QWORD *)Block[0] - 1);
          if ( (unsigned __int64)((char *)Block[0] - (char *)v27 - 8) > 0x1F )
            _invoke_watson(0, 0, 0, 0, 0);
        }
        free(v27);
      }
      v60 = _mm_load_si128((const __m128i *)&_xmm);
      LOBYTE(Block[0]) = 0;
      *(_OWORD *)Block = *(_OWORD *)v26;
      v60 = *(__m128i *)(v26 + 16);
      *(_QWORD *)(v26 + 16) = 0;
      *(_QWORD *)(v26 + 24) = 15;
      *(_BYTE *)v26 = 0;
    }
    v28 = *(_QWORD *)(v26 + 32);
    std::string::_Tidy_deallocate(WideCharStr);
    v51 = 0;
    v29 = a1[7];
    v30 = *(unsigned int (__fastcall **)(__int64, _QWORD, const WCHAR *, __int64, __int64, _QWORD *, __int64 *))(*(_QWORD *)v29 + 96LL);
    v31 = (_QWORD *)RepoMan::utf8_to_wstring(WideCharStr, (LPCCH)Block);
    if ( v31[3] > 7u )
      v31 = (_QWORD *)*v31;
    v32 = (RepoMan *)v30(v29, *(_QWORD *)v49, L"SHA256", v21, v28, v31, &v51);
    RepoMan::RaiseExceptionIfFailed(v32, 874, (int)"src\\repoman\\src\\inc\\PackageFormat.hpp", v33);
    std::wstring::_Tidy_deallocate(WideCharStr);
    v34 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(*(_QWORD *)a1[6] + 40LL))(a1[6], v48, 0, 0);
    RepoMan::RaiseExceptionIfFailed((RepoMan *)v34, 361, (int)"src\\repoman\\src\\inc\\StreamBase.hpp", v35);
    v36 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD, __int64))(*(_QWORD *)a1[7] + 112LL))(
            a1[7],
            *(_QWORD *)v49,
            v50,
            *(_QWORD *)v52,
            v51);
    RepoMan::RaiseExceptionIfFailed((RepoMan *)v36, 877, (int)"src\\repoman\\src\\inc\\PackageFormat.hpp", v37);
    v38 = v50;
    v50 = 0;
    *v57 = v38;
    v39 = v51;
    if ( v51 )
    {
      v51 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    }
    if ( v60.m128i_i64[1] > 0xFuLL )
    {
      v40 = Block[0];
      if ( (unsigned __int64)(v60.m128i_i64[1] + 1) >= 0x1000 )
      {
        v40 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v40 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v40);
    }
    Block[0] = (void *)19937;
    v60 = _mm_load_si128((const __m128i *)&_xmm);
    v41 = v53;
    if ( v53 )
    {
      v53 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    }
    v42 = v50;
    if ( v50 )
    {
      v50 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    }
    v43 = *(_QWORD *)v52;
    if ( *(_QWORD *)v52 )
    {
      *(_QWORD *)v52 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    }
    v44 = *(_QWORD *)v49;
    if ( *(_QWORD *)v49 )
    {
      *(_QWORD *)v49 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    }
    RepoMan::Meta::ScopeGuard::~ScopeGuard((RepoMan::Meta::ScopeGuard *)v58);
    RepoMan::Tracer::~Tracer((RepoMan::Tracer *)v63);
    result = 0;
  }
  catch ( ... )
  {
    RepoMan::Lippincott((RepoMan *)"src\\repoman\\src\\inc\\PackageFormat.hpp", (const char *)0x372, v45);
  }
  return result;
}

```

## disassembly

```asm
0x18000e170  mov     r11, rsp
0x18000e173  push    rbx
0x18000e174  push    rsi
0x18000e175  push    rdi
0x18000e176  push    r12
0x18000e178  push    r13
0x18000e17a  push    r14
0x18000e17c  push    r15
0x18000e17e  sub     rsp, 170h
0x18000e185  mov     rax, cs:__security_cookie
0x18000e18c  xor     rax, rsp
0x18000e18f  mov     [rsp+1A8h+var_48], rax
0x18000e197  mov     r13, r9
0x18000e19a  mov     rsi, r8
0x18000e19d  mov     [rsp+1A8h+var_110], rdx
0x18000e1a5  mov     r15, rcx
0x18000e1a8  mov     r12, [rsp+1A8h+arg_20]
0x18000e1b0  mov     rax, [rsp+1A8h+arg_28]
0x18000e1b8  mov     [rsp+1A8h+var_118], rax
0x18000e1c0  mov     rax, [rsp+1A8h+arg_48]
0x18000e1c8  mov     [rsp+1A8h+var_100], rax
0x18000e1d0  xor     ebx, ebx
0x18000e1d2  lea     r8, aMsixformatInse; "MSIXFormat.InsertFile"
0x18000e1d9  lea     edx, [rbx+1]
0x18000e1dc  lea     rcx, [r11-78h]
0x18000e1e0  call    ??0Tracer@RepoMan@@QEAA@W4Verbosity@ILogger@1@QEBD@Z; RepoMan::Tracer::Tracer(RepoMan::ILogger::Verbosity,char const * const)
0x18000e1e5  nop
0x18000e1e6  test    rsi, rsi
0x18000e1e9  jz      loc_18000E77A
0x18000e1ef  cmp     [rsi], bx
0x18000e1f2  jz      loc_18000E77A
0x18000e1f8  test    r12, r12
0x18000e1fb  jz      loc_18000E754
0x18000e201  cmp     [r12], bx
0x18000e206  jz      loc_18000E754
0x18000e20c  lea     rcx, [rsp+1A8h+var_F0]
0x18000e214  call    ?GetMSIXSDKLogsOnDemandForScope@MSIXFormat@RepoMan@@CA?AVScopeGuard@Meta@2@XZ; RepoMan::MSIXFormat::GetMSIXSDKLogsOnDemandForScope(void)
0x18000e219  nop
0x18000e21a  lea     r14, [r15-8]
0x18000e21e  lea     rdi, [r14+50h]
0x18000e222  cmp     [rdi], rbx
0x18000e225  jnz     short loc_18000E252
0x18000e227  mov     rax, [r14]
0x18000e22a  lea     rdx, [rsp+1A8h+var_148]
0x18000e22f  mov     rcx, r14
0x18000e232  mov     rax, [rax+50h]
0x18000e236  call    cs:__guard_dispatch_icall_fptr
0x18000e23c  mov     rdx, rax
0x18000e23f  mov     rcx, rdi
0x18000e242  call    ??$?4U?$default_delete@V?$RowType@U?$Column@U?$Key@USKU_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@USKUs@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Key@UCulture_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UCultures@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@U?$Column@U?$Value@UBrandingName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@Meta@RepoMan@@@std@@$0A@@?$unique_ptr@V?$RowType@U?$Column@U?$Key@USKU_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@USKUs@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Key@UCulture_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UCultures@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@U?$Column@U?$Value@UBrandingName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@Meta@RepoMan@@U?$default_delete@V?$RowType@U?$Column@U?$Key@USKU_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@USKUs@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Key@UCulture_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UCultures@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@U?$Column@U?$Value@UBrandingName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@Meta@RepoMan@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z
0x18000e247  lea     rcx, [rsp+1A8h+var_148]
0x18000e24c  call    ??1?$unique_ptr@V?$RowType@U?$Column@U?$Key@USKU_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@USKUs@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Key@UCulture_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UCultures@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@U?$Column@U?$Value@UBrandingName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@Meta@RepoMan@@U?$default_delete@V?$RowType@U?$Column@U?$Key@USKU_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@USKUs@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Key@UCulture_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UCultures@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@U?$Column@U?$Value@UBrandingName@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@Meta@RepoMan@@@std@@@std@@QEAA@XZ
0x18000e251  nop
0x18000e252  mov     r9, [rdi]
0x18000e255  add     r9, 48h ; 'H'
0x18000e259  mov     rax, [r15+28h]
0x18000e25d  mov     [rsp+1A8h+var_148], rax
0x18000e262  mov     rax, [r15+20h]
0x18000e266  mov     [rsp+1A8h+var_108], rax
0x18000e26e  lea     r8, [rsp+1A8h+var_148]
0x18000e273  lea     rdx, [rsp+1A8h+var_108]
0x18000e27b  lea     rcx, [rsp+1A8h+var_140]
0x18000e280  call    ??$Make@VCRepoBuild@RepoMan@@PEAVCRepoMan@2@PEAVSchema@2@AEA_J@?$ComPtr@UIRepoBuild@@@RepoMan@@SA?AV01@$$QEAPEAVCRepoMan@1@$$QEAPEAVSchema@1@AEA_J@Z; RepoMan::ComPtr<IRepoBuild>::Make<RepoMan::CRepoBuild,RepoMan::CRepoMan *,RepoMan::Schema *,__int64 &>(RepoMan::CRepoMan * &&,RepoMan::Schema * &&,__int64 &)
0x18000e285  nop
0x18000e286  mov     r8, r13
0x18000e289  lea     rdx, [rsp+1A8h+WideCharStr]
0x18000e291  call    ?GetFileDigest@?$MediaBase@VMSIXFormat@RepoMan@@V?$unique_ptr@V?$RowType@U?$Column@U?$Key@UMedia_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UMedia@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Value@UFormatType@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@H@23@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UCaseInsensitive@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@U?$Column@U?$Value@UURI@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@Meta@RepoMan@@U?$default_delete@V?$RowType@U?$Column@U?$Key@UMedia_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UMedia@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Value@UFormatType@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@H@23@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UCaseInsensitive@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@U?$Column@U?$Value@UURI@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@Meta@RepoMan@@@std@@@std@@UIRepoMedia@@UIRepoMediaInternal@@UIRepoMsixMedia@@UIRangeAware@@@RepoMan@@IEAA?AU?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K@std@@PEAUIStream@@@Z
0x18000e296  nop
0x18000e297  mov     [rsp+1A8h+Reserved], rax; Src
0x18000e29c  mov     r9, [r15+38h]; int
0x18000e2a0  mov     r8, qword ptr [rsp+1A8h+var_140]; int
0x18000e2a5  lea     rdx, [rsp+1A8h+var_128]; int
0x18000e2ad  call    ?CreateHashObject@?$MediaBase@VDatFormat@RepoMan@@V?$unique_ptr@V?$RowType@U?$Column@U?$Key@UMedia_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UMedia@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Value@UFormatType@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@H@23@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UCaseInsensitive@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@U?$Column@U?$Value@UURI@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@Meta@RepoMan@@U?$default_delete@V?$RowType@U?$Column@U?$Key@UMedia_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UMedia@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Value@UFormatType@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@H@23@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UCaseInsensitive@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@U?$Column@U?$Value@UURI@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@Meta@RepoMan@@@std@@@std@@UIRepoMedia@@UIRepoMediaInternal@@UIRangeAware@@@RepoMan@@IEAA?AV?$ComPtr@UIRepoHash@@@2@PEAUIRepoBuild@@PEAUIRepoWriter@@AEBU?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K@std@@@Z
0x18000e2b2  nop
0x18000e2b3  lea     rcx, [rsp+1A8h+WideCharStr]
0x18000e2bb  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18000e2c0  mov     qword ptr [rsp+1A8h+WideCharStr], 4DE1h
0x18000e2cc  movdqa  xmm0, cs:__xmm@000000000000001f0000000000000000
0x18000e2d4  movdqu  [rsp+1A8h+var_90], xmm0
0x18000e2dd  mov     rax, [rsp+1A8h+var_118]
0x18000e2e5  mov     [rsp+1A8h+var_150], rax
0x18000e2ea  mov     eax, [rsp+1A8h+arg_40]
0x18000e2f1  mov     [rsp+1A8h+var_158], eax
0x18000e2f5  mov     eax, [rsp+1A8h+arg_38]
0x18000e2fc  mov     [rsp+1A8h+var_160], eax
0x18000e300  mov     eax, [rsp+1A8h+arg_30]
0x18000e307  mov     [rsp+1A8h+var_168], eax
0x18000e30b  mov     [rsp+1A8h+var_170], r12
0x18000e310  mov     [rsp+1A8h+var_178], rsi
0x18000e315  mov     rax, qword ptr [rsp+1A8h+var_128]
0x18000e31d  mov     [rsp+1A8h+var_180], rax
0x18000e322  mov     rax, qword ptr [rsp+1A8h+var_140]
0x18000e327  mov     [rsp+1A8h+Reserved], rax
0x18000e32c  mov     r9, [r15+38h]
0x18000e330  mov     r8, [rsp+1A8h+var_110]
0x18000e338  lea     rdx, [rsp+1A8h+var_138]
0x18000e33d  mov     rcx, r14
0x18000e340  call    ?CreateFileObject@?$MediaBase@VDatFormat@RepoMan@@V?$unique_ptr@V?$RowType@U?$Column@U?$Key@UMedia_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UMedia@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Value@UFormatType@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@H@23@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UCaseInsensitive@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@U?$Column@U?$Value@UURI@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@Meta@RepoMan@@U?$default_delete@V?$RowType@U?$Column@U?$Key@UMedia_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UMedia@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Value@UFormatType@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@H@23@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UCaseInsensitive@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@U?$Column@U?$Value@UURI@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@Meta@RepoMan@@@std@@@std@@UIRepoMedia@@UIRepoMediaInternal@@UIRangeAware@@@RepoMan@@IEAA?AV?$ComPtr@UIRepoFile@@@2@PEAUIRepoPackage@@PEAUIRepoWriter@@PEAUIRepoBuild@@PEAUIRepoHash@@PEB_W4W4_REPOMAN_PATCH_TECH@@W4_REPOMAN_FILE_TAGS@@W4_REPOMAN_PATH_TAGS@@3@Z
0x18000e345  nop
0x18000e346  cmp     word ptr [rsi], 5Ch ; '\'
0x18000e34a  jz      short loc_18000E352
0x18000e34c  cmp     word ptr [rsi], 2Fh ; '/'
0x18000e350  jnz     short loc_18000E356
0x18000e352  add     rsi, 2
0x18000e356  lea     r12, [r15+30h]
0x18000e35a  mov     rcx, [r12]
0x18000e35e  mov     [rsp+1A8h+var_148], rbx
0x18000e363  mov     rax, [rcx]
0x18000e366  lea     r9, [rsp+1A8h+var_148]
0x18000e36b  mov     r8d, 1
0x18000e371  mov     rdx, rbx
0x18000e374  mov     rax, [rax+28h]
0x18000e378  call    cs:__guard_dispatch_icall_fptr
0x18000e37e  lea     r8, aSrcRepomanSrcI; "src\\repoman\\src\\inc\\StreamBase.hpp"
0x18000e385  mov     edx, 161h; int
0x18000e38a  mov     ecx, eax; this
0x18000e38c  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x18000e391  mov     rdi, [rsp+1A8h+var_148]
0x18000e396  mov     [rsp+1A8h+var_118], rdi
0x18000e39e  mov     r8, rsi; wchar_t *
0x18000e3a1  mov     rdx, r13; struct IStream *
0x18000e3a4  mov     rcx, r14; this
0x18000e3a7  call    ?AddPayloadFile@MSIXFormat@RepoMan@@AEAAXPEAUIStream@@PEB_W@Z; RepoMan::MSIXFormat::AddPayloadFile(IStream *,wchar_t const *)
0x18000e3ac  mov     rcx, [r12]
0x18000e3b0  mov     [rsp+1A8h+var_148], rbx
0x18000e3b5  mov     rax, [rcx]
0x18000e3b8  lea     r9, [rsp+1A8h+var_148]
0x18000e3bd  mov     r8d, 1
0x18000e3c3  mov     rdx, rbx
0x18000e3c6  mov     rax, [rax+28h]
0x18000e3ca  call    cs:__guard_dispatch_icall_fptr
0x18000e3d0  lea     r8, aSrcRepomanSrcI; "src\\repoman\\src\\inc\\StreamBase.hpp"
0x18000e3d7  mov     edx, 161h; int
0x18000e3dc  mov     ecx, eax; this
0x18000e3de  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x18000e3e3  mov     rax, [rsp+1A8h+var_148]
0x18000e3e8  sub     rax, rdi
0x18000e3eb  mov     [rsp+1A8h+var_110], rax
0x18000e3f3  mov     r9, r12
0x18000e3f6  lea     r8, [rsp+1A8h+var_110]
0x18000e3fe  lea     rdx, [rsp+1A8h+var_118]
0x18000e406  lea     rcx, [rsp+1A8h+var_120]
0x18000e40e  call    ??$Make@VSubStream@RepoMan@@AEA_KAEA_KAEAV?$ComPtr@UIStream@@@2@@?$ComPtr@UIStream@@@RepoMan@@SA?AV01@AEA_K0AEAV01@@Z; RepoMan::ComPtr<IStream>::Make<RepoMan::SubStream,unsigned __int64 &,unsigned __int64 &,RepoMan::ComPtr<IStream> &>(unsigned __int64 &,unsigned __int64 &,RepoMan::ComPtr<IStream> &)
0x18000e413  nop
0x18000e414  xorps   xmm0, xmm0
0x18000e417  movups  xmmword ptr [rsp+1A8h+Block], xmm0
0x18000e41f  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18000e427  movdqu  [rsp+1A8h+var_B0], xmm1
0x18000e430  mov     byte ptr [rsp+1A8h+Block], bl
0x18000e437  mov     r8, [rsp+1A8h+var_120]
0x18000e43f  lea     rdx, [rsp+1A8h+WideCharStr]
0x18000e447  call    ?GetFileDigest@?$MediaBase@VMSIXFormat@RepoMan@@V?$unique_ptr@V?$RowType@U?$Column@U?$Key@UMedia_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UMedia@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Value@UFormatType@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@H@23@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UCaseInsensitive@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@U?$Column@U?$Value@UURI@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@Meta@RepoMan@@U?$default_delete@V?$RowType@U?$Column@U?$Key@UMedia_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UMedia@234@UNone@Alias@34@@Meta@RepoMan@@_J@Meta@RepoMan@@U?$Column@U?$Key@UBuild_Id@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@UBuilds@234@UNone@Alias@34@@Meta@RepoMan@@_J@23@U?$Column@U?$Value@UFormatType@Text@Meta@RepoMan@@UInt@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@H@23@U?$Column@U?$Value@UName@Text@Meta@RepoMan@@UString@Types@34@UCaseInsensitive@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@U?$Column@U?$Value@UURI@Text@Meta@RepoMan@@UString@Types@34@UNotNull@Constraints@34@@Meta@RepoMan@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@23@@Meta@RepoMan@@@std@@@std@@UIRepoMedia@@UIRepoMediaInternal@@UIRepoMsixMedia@@UIRangeAware@@@RepoMan@@IEAA?AU?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K@std@@PEAUIStream@@@Z
0x18000e44c  mov     rsi, rax
0x18000e44f  lea     rax, [rsp+1A8h+Block]
0x18000e457  cmp     rax, rsi
0x18000e45a  jz      loc_18000E4EE
0x18000e460  mov     rax, qword ptr [rsp+1A8h+var_B0+8]
0x18000e468  cmp     rax, 0Fh
0x18000e46c  jbe     short loc_18000E4B1
0x18000e46e  mov     rcx, [rsp+1A8h+Block]; Block
0x18000e476  mov     rdx, rcx
0x18000e479  inc     rax
0x18000e47c  cmp     rax, 1000h
0x18000e482  jb      short loc_18000E4AB
0x18000e484  mov     rcx, [rcx-8]
0x18000e488  sub     rdx, rcx
0x18000e48b  lea     rax, [rdx-8]
0x18000e48f  cmp     rax, 1Fh
0x18000e493  jbe     short loc_18000E4AB
0x18000e495  mov     [rsp+1A8h+Reserved], rbx; Reserved
0x18000e49a  xor     r9d, r9d; LineNo
0x18000e49d  xor     r8d, r8d; FileName
0x18000e4a0  xor     edx, edx; FunctionName
0x18000e4a2  xor     ecx, ecx; Expression
0x18000e4a4  call    cs:__imp__invoke_watson
0x18000e4ab  call    cs:__imp_free
0x18000e4b1  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x18000e4b9  movdqu  [rsp+1A8h+var_B0], xmm0
0x18000e4c2  mov     byte ptr [rsp+1A8h+Block], bl
0x18000e4c9  movups  xmm0, xmmword ptr [rsi]
0x18000e4cc  movups  xmmword ptr [rsp+1A8h+Block], xmm0
0x18000e4d4  movups  xmm1, xmmword ptr [rsi+10h]
0x18000e4d8  movups  [rsp+1A8h+var_B0], xmm1
0x18000e4e0  mov     [rsi+10h], rbx
0x18000e4e4  mov     qword ptr [rsi+18h], 0Fh
0x18000e4ec  mov     [rsi], bl
0x18000e4ee  mov     rsi, [rsi+20h]
0x18000e4f2  lea     rcx, [rsp+1A8h+WideCharStr]
0x18000e4fa  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18000e4ff  mov     [rsp+1A8h+var_130], rbx
0x18000e504  mov     r14, [r15+38h]
0x18000e508  mov     rax, [r14]
0x18000e50b  mov     r13, [rax+60h]
0x18000e50f  lea     rdx, [rsp+1A8h+Block]; lpMultiByteStr
0x18000e517  lea     rcx, [rsp+1A8h+WideCharStr]; lpWideCharStr
0x18000e51f  call    ?utf8_to_wstring@RepoMan@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; RepoMan::utf8_to_wstring(std::string const &)
0x18000e524  nop
0x18000e525  cmp     qword ptr [rax+18h], 7
0x18000e52a  jbe     short loc_18000E52F
0x18000e52c  mov     rax, [rax]
0x18000e52f  lea     rcx, [rsp+1A8h+var_130]
0x18000e534  mov     [rsp+1A8h+var_178], rcx
0x18000e539  mov     [rsp+1A8h+var_180], rax
0x18000e53e  mov     [rsp+1A8h+Reserved], rsi
0x18000e543  mov     r9, rdi
0x18000e546  lea     r8, pszAlgId; "SHA256"
0x18000e54d  mov     rdx, qword ptr [rsp+1A8h+var_140]
0x18000e552  mov     rcx, r14
0x18000e555  mov     rax, r13
0x18000e558  call    cs:__guard_dispatch_icall_fptr
0x18000e55e  mov     ecx, eax; this
0x18000e560  lea     r8, aSrcRepomanSrcI_7; "src\\repoman\\src\\inc\\PackageFormat.h"...
0x18000e567  mov     edx, 36Ah; int
0x18000e56c  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x18000e571  nop
0x18000e572  lea     rcx, [rsp+1A8h+WideCharStr]
0x18000e57a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000e57f  mov     rcx, [r12]
0x18000e583  mov     rax, [rcx]
0x18000e586  xor     r9d, r9d
0x18000e589  xor     r8d, r8d
0x18000e58c  mov     rdx, [rsp+1A8h+var_148]
0x18000e591  mov     rax, [rax+28h]
0x18000e595  call    cs:__guard_dispatch_icall_fptr
0x18000e59b  lea     r8, aSrcRepomanSrcI; "src\\repoman\\src\\inc\\StreamBase.hpp"
0x18000e5a2  mov     edx, 169h; int
0x18000e5a7  mov     ecx, eax; this
0x18000e5a9  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x18000e5ae  mov     rcx, [r15+38h]
0x18000e5b2  mov     rax, [rcx]
0x18000e5b5  mov     r10, [rsp+1A8h+var_130]
0x18000e5ba  mov     [rsp+1A8h+Reserved], r10
0x18000e5bf  mov     r9, qword ptr [rsp+1A8h+var_128]
0x18000e5c7  mov     r8, [rsp+1A8h+var_138]
0x18000e5cc  mov     rdx, qword ptr [rsp+1A8h+var_140]
0x18000e5d1  mov     rax, [rax+70h]
0x18000e5d5  call    cs:__guard_dispatch_icall_fptr
0x18000e5db  mov     ecx, eax; this
0x18000e5dd  lea     r8, aSrcRepomanSrcI_7; "src\\repoman\\src\\inc\\PackageFormat.h"...
0x18000e5e4  mov     edx, 36Dh; int
0x18000e5e9  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x18000e5ee  mov     rax, [rsp+1A8h+var_138]
0x18000e5f3  mov     [rsp+1A8h+var_138], rbx
0x18000e5f8  mov     rcx, [rsp+1A8h+var_100]
0x18000e600  mov     [rcx], rax
0x18000e603  mov     rcx, [rsp+1A8h+var_130]
0x18000e608  test    rcx, rcx
0x18000e60b  jz      short loc_18000E620
0x18000e60d  mov     [rsp+1A8h+var_130], rbx
0x18000e612  mov     rax, [rcx]
0x18000e615  mov     rax, [rax+10h]
0x18000e619  call    cs:__guard_dispatch_icall_fptr
0x18000e61f  nop
0x18000e620  mov     rax, qword ptr [rsp+1A8h+var_B0+8]
0x18000e628  cmp     rax, 0Fh
0x18000e62c  jbe     short loc_18000E671
0x18000e62e  mov     rcx, [rsp+1A8h+Block]; Block
0x18000e636  mov     rdx, rcx
0x18000e639  inc     rax
0x18000e63c  cmp     rax, 1000h
0x18000e642  jb      short loc_18000E66B
0x18000e644  mov     rcx, [rcx-8]
0x18000e648  sub     rdx, rcx
0x18000e64b  lea     rax, [rdx-8]
0x18000e64f  cmp     rax, 1Fh
0x18000e653  jbe     short loc_18000E66B
0x18000e655  mov     [rsp+1A8h+Reserved], rbx; Reserved
0x18000e65a  xor     r9d, r9d; LineNo
0x18000e65d  xor     r8d, r8d; FileName
0x18000e660  xor     edx, edx; FunctionName
0x18000e662  xor     ecx, ecx; Expression
0x18000e664  call    cs:__imp__invoke_watson
0x18000e66b  call    cs:__imp_free
0x18000e671  mov     [rsp+1A8h+Block], 4DE1h
0x18000e67d  movdqa  xmm0, cs:__xmm@000000000000001f0000000000000000
0x18000e685  movdqu  [rsp+1A8h+var_B0], xmm0
0x18000e68e  mov     rcx, [rsp+1A8h+var_120]
0x18000e696  test    rcx, rcx
0x18000e699  jz      short loc_18000E6B1
0x18000e69b  mov     [rsp+1A8h+var_120], rbx
0x18000e6a3  mov     rax, [rcx]
0x18000e6a6  mov     rax, [rax+10h]
0x18000e6aa  call    cs:__guard_dispatch_icall_fptr
0x18000e6b0  nop
0x18000e6b1  mov     rcx, [rsp+1A8h+var_138]
0x18000e6b6  test    rcx, rcx
0x18000e6b9  jz      short loc_18000E6CE
0x18000e6bb  mov     [rsp+1A8h+var_138], rbx
0x18000e6c0  mov     rax, [rcx]
0x18000e6c3  mov     rax, [rax+10h]
0x18000e6c7  call    cs:__guard_dispatch_icall_fptr
0x18000e6cd  nop
0x18000e6ce  mov     rcx, qword ptr [rsp+1A8h+var_128]
0x18000e6d6  test    rcx, rcx
0x18000e6d9  jz      short loc_18000E6F1
0x18000e6db  mov     qword ptr [rsp+1A8h+var_128], rbx
0x18000e6e3  mov     rax, [rcx]
0x18000e6e6  mov     rax, [rax+10h]
0x18000e6ea  call    cs:__guard_dispatch_icall_fptr
0x18000e6f0  nop
  ... truncated ...
```
