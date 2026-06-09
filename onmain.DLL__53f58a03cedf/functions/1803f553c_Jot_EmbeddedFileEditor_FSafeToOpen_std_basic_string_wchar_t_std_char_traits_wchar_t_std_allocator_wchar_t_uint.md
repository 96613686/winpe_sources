# Jot::EmbeddedFileEditor::FSafeToOpen(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,uint,uint,uint,uint,_msoreg const *,_msoreg const *,bool)

- ea: `0x1803f553c`
- end: `0x1803f5b12`
- name: `?FSafeToOpen@EmbeddedFileEditor@Jot@@YA_NV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@IIIIPEBU_msoreg@@1_N@Z`
- size: `1494`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, int, int, __int64, char)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1803f54b4`
- `0x180b77df8`

## callees

- `0x18002f770`
- `0x18002fa9c`
- `0x180057140`
- `0x1800581b0`
- `0x18005b344`
- `0x18005b408`
- `0x180066ff0`
- `0x18008e7b8`
- `0x18013f684`
- `0x180145f40`
- `0x18029ced0`
- `0x1802e0c78`
- `0x1802e2190`
- `0x1802e5170`
- `0x1803f553c`
- `0x1803f5de0`
- `0x1803f5f50`
- `0x180a583c4`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x1803f55c9`
- `KERNEL32!GetFullPathNameW` at `0x1803f55c9`
- `SHLWAPI!PathIsDirectoryW` at `0x1803f5989`
- `SHLWAPI!PathIsDirectoryW` at `0x1803f5989`
- `Mso30Win32Client!__imp_?CheckExtensionSafetyFromService@Security@Mso@@YA?AW4ExtensionSafetyLevel@12@PEB_W@Z` at `0x1803f5715`
- `Mso30Win32Client!__imp_?CheckExtensionSafetyFromService@Security@Mso@@YA?AW4ExtensionSafetyLevel@12@PEB_W@Z` at `0x1803f5715`
- `Mso30Win32Client!__imp_?IsExtensionInList@Security@Mso@@YA_NPEB_W0@Z` at `0x1803f563d`
- `Mso30Win32Client!__imp_?IsExtensionInList@Security@Mso@@YA_NPEB_W0@Z` at `0x1803f5709`
- `Mso30Win32Client!__imp_?IsExtensionInList@Security@Mso@@YA_NPEB_W0@Z` at `0x1803f563d`
- `Mso30Win32Client!__imp_?IsExtensionInList@Security@Mso@@YA_NPEB_W0@Z` at `0x1803f5709`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1803f58d3`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1803f58d3`
- `Mso20Win32Client!__imp_?InitForValue@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_KW4RegValueType@@@Z` at `0x1803f58f4`
- `Mso20Win32Client!__imp_?InitForValue@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_KW4RegValueType@@@Z` at `0x1803f58f4`
- `Mso20Win32Client!__imp_?Read@Orapi@Mso@@YA_NAEBU_msoreg@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x1803f5626`
- `Mso20Win32Client!__imp_?Read@Orapi@Mso@@YA_NAEBU_msoreg@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x1803f56f2`
- `Mso20Win32Client!__imp_?Read@Orapi@Mso@@YA_NAEBU_msoreg@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x1803f5626`
- `Mso20Win32Client!__imp_?Read@Orapi@Mso@@YA_NAEBU_msoreg@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x1803f56f2`
- `Mso20Win32Client!__imp_?MsoFRegGetDw@@YAHPEBU_msoreg@@PEAK@Z` at `0x1803f590f`
- `Mso20Win32Client!__imp_?MsoFRegGetDw@@YAHPEBU_msoreg@@PEAK@Z` at `0x1803f590f`
- `Mso20Win32Client!__imp_?MsoPathFindExtension@Path@Mso@@YAPEA_WPEB_W@Z` at `0x1803f55e7`
- `Mso20Win32Client!__imp_?MsoPathFindExtension@Path@Mso@@YAPEA_WPEB_W@Z` at `0x1803f55e7`

## string_xrefs

- `0x1803f57bc`: `Extension`
- `0x1803f5a0c`: `Extension`
- `0x1803f569e`: `EmbeddedFileBlockedByRegistryBlockList`
- `0x1803f5a48`: `EmbeddedFileBlockedByRegistryBlockList`

## pseudocode

```c
char __fastcall Jot::EmbeddedFileEditor::FSafeToOpen(
        _QWORD *a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7,
        char a8)
{
  char v10; // bl
  _QWORD *v11; // rax
  WCHAR *v12; // rax
  const WCHAR *v13; // rcx
  const wchar_t *v14; // rdx
  LPCWSTR *v15; // rcx
  wchar_t *Extension; // rax
  Mso::Security *v17; // rsi
  const wchar_t *v18; // r8
  const wchar_t *v19; // rdx
  __int64 v20; // rax
  __int128 *v21; // rcx
  const wchar_t *v22; // r8
  const wchar_t *v23; // rdx
  bool IsExtensionInList; // r14
  void *v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  const WCHAR *v29; // rcx
  __int64 v30; // rax
  unsigned int v31; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int8 v32; // [rsp+34h] [rbp-CCh]
  _QWORD v33[3]; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v34; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v35; // [rsp+60h] [rbp-A0h]
  __int128 v36; // [rsp+68h] [rbp-98h] BYREF
  __int128 v37; // [rsp+78h] [rbp-88h] BYREF
  char v38; // [rsp+88h] [rbp-78h]
  _OWORD v39[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v40; // [rsp+B0h] [rbp-50h] BYREF
  void **v41; // [rsp+C0h] [rbp-40h] BYREF
  void **v42; // [rsp+C8h] [rbp-38h]
  const wchar_t *v43; // [rsp+D0h] [rbp-30h]
  __int64 v44; // [rsp+D8h] [rbp-28h]
  _QWORD *v45; // [rsp+E0h] [rbp-20h]
  __int16 v46; // [rsp+E8h] [rbp-18h]
  _QWORD *v47; // [rsp+F0h] [rbp-10h] BYREF
  LPCWSTR pszPath[2]; // [rsp+F8h] [rbp-8h] BYREF
  __m128i si128; // [rsp+108h] [rbp+8h]
  __int128 v50; // [rsp+118h] [rbp+18h] BYREF
  __m128i v51; // [rsp+128h] [rbp+28h]
  _OWORD v52[2]; // [rsp+138h] [rbp+38h] BYREF
  __int128 v53; // [rsp+158h] [rbp+58h] BYREF
  __m128i v54; // [rsp+168h] [rbp+68h]

  v47 = a1;
  *(_OWORD *)pszPath = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v10 = 0;
  LOWORD(pszPath[0]) = 0;
  v11 = (_QWORD *)Jot::basic_strbuffer<std::wstring>::basic_strbuffer<std::wstring>(v33, pszPath, 260);
  v12 = (WCHAR *)std::wstring::operator[](*v11, 0);
  v13 = (const WCHAR *)a1;
  if ( a1[3] > 7u )
    v13 = (const WCHAR *)*a1;
  GetFullPathNameW(v13, 0x104u, v12, 0);
  Jot::basic_strbuffer<std::wstring>::~basic_strbuffer<std::wstring>(v33);
  v15 = pszPath;
  if ( si128.m128i_i64[1] > 7uLL )
    v15 = (LPCWSTR *)pszPath[0];
  Extension = Mso::Path::MsoPathFindExtension((Mso::Path *)v15, v14);
  v17 = (Mso::Security *)Extension;
  if ( Extension && *Extension == 46 )
  {
    v53 = 0;
    v54 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v53) = 0;
    Mso::Orapi::Read(&vmsoridSecurityBlockedExtensions, &v53);
    v19 = (const wchar_t *)&v53;
    if ( v54.m128i_i64[1] > 7uLL )
      v19 = (const wchar_t *)v53;
    if ( Mso::Security::IsExtensionInList(v17, v19, v18) )
    {
      v39[0] = *(_OWORD *)Jot::CDialogButtonSet::CDialogButtonSet(v52, 1, 0);
      Jot::DisplayErrorDialog(a2, v39, 0, 0, 0, 3);
      v20 = Mso::Telemetry::EventFlags::EventFlags(&v47, 2);
      v33[0] = &off_18107D820;
      v33[1] = "EmbeddedFileBlockedByRegistryBlockList";
      Mso::Telemetry::SendTelemetryEvent<>(v33, v20);
      v21 = &v53;
LABEL_11:
      std::wstring::~wstring(v21);
LABEL_35:
      std::wstring::~wstring(pszPath);
      std::wstring::~wstring(a1);
      return v10;
    }
    std::wstring::~wstring(&v53);
    v50 = 0;
    v51 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v50) = 0;
    Mso::Orapi::Read(&vmsoridSecurityAllowedExtensions, &v50);
    v23 = (const wchar_t *)&v50;
    if ( v51.m128i_i64[1] > 7uLL )
      v23 = (const wchar_t *)v50;
    IsExtensionInList = Mso::Security::IsExtensionInList(v17, v23, v22);
    if ( (unsigned int)Mso::Security::CheckExtensionSafetyFromService(v17) )
    {
      v31 = 0;
      v34 = 0;
      v35 = 0;
      v36 = 0;
      v38 = 0;
      v37 = (unsigned __int64)&v34;
      v27 = -1;
      do
        ++v27;
      while ( *((_WORD *)v17 + v27) );
      if ( a7 )
      {
        DynamicMsorid::InitForValue(&v34, a7, v17, v27, 4);
        MsoFRegGetDw((const struct _msoreg *)((unsigned __int64)&v36 & -(__int64)(v38 != 0)), &v31);
      }
      else
      {
        MsoShipAssertTagProc(508048472);
      }
      DynamicMsorid::~DynamicMsorid((DynamicMsorid *)&v34);
      if ( (v31 & 3) != 1 )
      {
        if ( !a8 )
        {
          std::wstring::~wstring(&v50);
          std::wstring::~wstring(pszPath);
          std::wstring::~wstring(a1);
          return 1;
        }
        v25 = (void *)std::wstring::wstring(v52, a1);
        goto LABEL_18;
      }
    }
    else
    {
      if ( !IsExtensionInList )
      {
        v39[0] = *(_OWORD *)Jot::CDialogButtonSet::CDialogButtonSet(v52, 1, 0);
        Jot::DisplayErrorDialog(a2, v39, 0, 0, 0, 3);
        v33[0] = v17;
        v41 = &Jot::Logging::details::StructuredTraceImplementation<Jot::Logging::NonPiiWz>::`vftable'{for `Mso::Logging::IStructuredTrace'};
        v42 = &Jot::Logging::details::StructuredTraceImplementation<Jot::Logging::NonPiiWz>::`vftable'{for `Mso::Telemetry::IDataField'};
        v43 = L"Extension";
        v44 = -1;
        v45 = v33;
        v46 = 4;
        v26 = Mso::Telemetry::EventFlags::EventFlags(&v47, 2);
        *(_QWORD *)&v40 = &off_18107D820;
        *((_QWORD *)&v40 + 1) = "EmbeddedFileBlockedByServerBlockList";
        v39[0] = 0;
        v52[0] = 0;
        *(_QWORD *)&v34 = &v40;
        *((_QWORD *)&v34 + 1) = v26;
        LOWORD(v35) = (unsigned __int8)v31;
        *(_DWORD *)((char *)&v35 + 2) = v31;
        HIWORD(v35) = v32;
        std::shared_ptr<Microsoft::Office::AugLoop::ISerializable>::shared_ptr<Microsoft::Office::AugLoop::ISerializable>(
          &v36,
          v52);
        std::shared_ptr<Mso::Telemetry::EventContract>::shared_ptr<Mso::Telemetry::EventContract>(&v37, v39);
        ___CreateAndUseCompositeDataField_V_lambda_1___1____SendTelemetryEvent_VErrorData_Logging_Jot___Details_Telemetry_Mso__YAXAEBUEventName_34_AEBV__shared_ptr_VEvent_System_Office___std__AEBV__shared_ptr_UEventContract_Telemetry_Mso___7_AEBUEventFlags_34___QEAV__optional_VEventExportability_Telemetry_Mso___7___QEAV__optional_VEventSamplingMetadata_Telemetry_Mso___7___QEAVErrorData_Logging_Jot___Z_VErrorData_Logging_Jot___Details_Telemetry_Mso__YAX__QEAV_lambda_1___1____SendTelemetryEvent_VErrorData_Logging_Jot___012_YAXAEBUEventName_12_AEBV__shared_ptr_VEvent_System_Office___std__AEBV__shared_ptr_UEventContract_Telemetry_Mso___6_AEBUEventFlags_12___QEAV__optional_VEventExportability_Telemetry_Mso___6___QEAV__optional_VEventSamplingMetadata_Telemetry_Mso___6___QEAVErrorData_Logging_Jot___Z_6_Z(
          &v34,
          &v41);
        `Mso::Telemetry::Details::SendTelemetryEvent<Jot::Logging::details::StructuredTraceImplementation<_GUID>,Jot::Logging::ErrorData>'::`2'::_lambda_1_::~_lambda_1_(&v34);
        std::shared_ptr<xpsrdr::SourceColorBitmap>::~shared_ptr<xpsrdr::SourceColorBitmap>(v52);
        std::shared_ptr<xpsrdr::SourceColorBitmap>::~shared_ptr<xpsrdr::SourceColorBitmap>(v39);
        goto LABEL_19;
      }
      if ( a8 )
      {
        v25 = (void *)std::wstring::wstring(v39, a1);
LABEL_18:
        v10 = Jot::FSafeToOpenShowPrompt(v25, a7);
LABEL_19:
        v21 = &v50;
        goto LABEL_11;
      }
    }
    std::wstring::~wstring(&v50);
LABEL_34:
    v10 = 1;
    goto LABEL_35;
  }
  v29 = (const WCHAR *)pszPath;
  if ( si128.m128i_i64[1] > 7uLL )
    v29 = pszPath[0];
  if ( PathIsDirectoryW(v29) )
    goto LABEL_34;
  v39[0] = *(_OWORD *)Jot::CDialogButtonSet::CDialogButtonSet(v52, 1, 0);
  Jot::DisplayErrorDialog(a2, v39, 0, 0, 0, 3);
  v33[0] = &WindowName;
  v41 = &Jot::Logging::details::StructuredTraceImplementation<Jot::Logging::NonPiiWz>::`vftable'{for `Mso::Logging::IStructuredTrace'};
  v42 = &Jot::Logging::details::StructuredTraceImplementation<Jot::Logging::NonPiiWz>::`vftable'{for `Mso::Telemetry::IDataField'};
  v43 = L"Extension";
  v44 = -1;
  v45 = v33;
  v46 = 4;
  v30 = Mso::Telemetry::EventFlags::EventFlags(&v47, 2);
  *(_QWORD *)&v39[0] = &off_18107D820;
  *((_QWORD *)&v39[0] + 1) = "EmbeddedFileBlockedByRegistryBlockList";
  v40 = 0;
  v52[0] = 0;
  *(_QWORD *)&v34 = v39;
  *((_QWORD *)&v34 + 1) = v30;
  LOWORD(v35) = (unsigned __int8)v31;
  *(_DWORD *)((char *)&v35 + 2) = v31;
  HIWORD(v35) = v32;
  std::shared_ptr<Microsoft::Office::AugLoop::ISerializable>::shared_ptr<Microsoft::Office::AugLoop::ISerializable>(
    &v36,
    v52);
  std::shared_ptr<Mso::Telemetry::EventContract>::shared_ptr<Mso::Telemetry::EventContract>(&v37, &v40);
  ___CreateAndUseCompositeDataField_V_lambda_1___1____SendTelemetryEvent_VErrorData_Logging_Jot___Details_Telemetry_Mso__YAXAEBUEventName_34_AEBV__shared_ptr_VEvent_System_Office___std__AEBV__shared_ptr_UEventContract_Telemetry_Mso___7_AEBUEventFlags_34___QEAV__optional_VEventExportability_Telemetry_Mso___7___QEAV__optional_VEventSamplingMetadata_Telemetry_Mso___7___QEAVErrorData_Logging_Jot___Z_VErrorData_Logging_Jot___Details_Telemetry_Mso__YAX__QEAV_lambda_1___1____SendTelemetryEvent_VErrorData_Logging_Jot___012_YAXAEBUEventName_12_AEBV__shared_ptr_VEvent_System_Office___std__AEBV__shared_ptr_UEventContract_Telemetry_Mso___6_AEBUEventFlags_12___QEAV__optional_VEventExportability_Telemetry_Mso___6___QEAV__optional_VEventSamplingMetadata_Telemetry_Mso___6___QEAVErrorData_Logging_Jot___Z_6_Z(
    &v34,
    &v41);
  `Mso::Telemetry::Details::SendTelemetryEvent<Jot::Logging::details::StructuredTraceImplementation<_GUID>,Jot::Logging::ErrorData>'::`2'::_lambda_1_::~_lambda_1_(&v34);
  std::shared_ptr<xpsrdr::SourceColorBitmap>::~shared_ptr<xpsrdr::SourceColorBitmap>(v52);
  std::shared_ptr<xpsrdr::SourceColorBitmap>::~shared_ptr<xpsrdr::SourceColorBitmap>(&v40);
  std::wstring::~wstring(pszPath);
  std::wstring::~wstring(a1);
  return 0;
}

```

## disassembly

```asm
0x1803f553c  mov     [rsp-8+arg_10], rbx
0x1803f5541  push    rbp
0x1803f5542  push    rsi
0x1803f5543  push    rdi
0x1803f5544  push    r12
0x1803f5546  push    r13
0x1803f5548  push    r14
0x1803f554a  push    r15
0x1803f554c  lea     rbp, [rsp-80h]
0x1803f5551  sub     rsp, 180h
0x1803f5558  mov     rax, cs:__security_cookie
0x1803f555f  xor     rax, rsp
0x1803f5562  mov     [rbp+0B0h+var_38], rax
0x1803f5566  mov     r12d, r9d
0x1803f5569  mov     r13d, edx
0x1803f556c  mov     rdi, rcx
0x1803f556f  mov     [rbp+0B0h+var_C0], rcx
0x1803f5573  mov     r15, [rbp+0B0h+arg_30]
0x1803f557a  xorps   xmm0, xmm0
0x1803f557d  movups  xmmword ptr [rbp+0B0h+pszPath], xmm0
0x1803f5581  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1803f5589  movdqu  [rbp+0B0h+var_A8], xmm1
0x1803f558e  xor     ebx, ebx
0x1803f5590  mov     word ptr [rbp+0B0h+pszPath], bx
0x1803f5594  mov     esi, 104h
0x1803f5599  mov     r8d, esi
0x1803f559c  lea     rdx, [rbp+0B0h+pszPath]
0x1803f55a0  lea     rcx, [rsp+1B0h+var_178]
0x1803f55a5  call    ??0?$basic_strbuffer@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Jot@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@Z; Jot::basic_strbuffer<std::wstring>::basic_strbuffer<std::wstring>(std::wstring &,unsigned __int64)
0x1803f55aa  xor     edx, edx
0x1803f55ac  mov     rcx, [rax]
0x1803f55af  call    ??A?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEA_W_K@Z; std::wstring::operator[](unsigned __int64)
0x1803f55b4  mov     rcx, rdi
0x1803f55b7  cmp     qword ptr [rdi+18h], 7
0x1803f55bc  jbe     short loc_1803F55C1
0x1803f55be  mov     rcx, [rdi]; lpFileName
0x1803f55c1  xor     r9d, r9d; lpFilePart
0x1803f55c4  mov     r8, rax; lpBuffer
0x1803f55c7  mov     edx, esi; nBufferLength
0x1803f55c9  call    cs:__imp_GetFullPathNameW
0x1803f55cf  lea     rcx, [rsp+1B0h+var_178]
0x1803f55d4  call    ??1?$basic_strbuffer@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Jot@@QEAA@XZ; Jot::basic_strbuffer<std::wstring>::~basic_strbuffer<std::wstring>(void)
0x1803f55d9  lea     rcx, [rbp+0B0h+pszPath]
0x1803f55dd  cmp     qword ptr [rbp+0B0h+var_A8+8], 7
0x1803f55e2  cmova   rcx, [rbp+0B0h+pszPath]
0x1803f55e7  call    cs:__imp_?MsoPathFindExtension@Path@Mso@@YAPEA_WPEB_W@Z; Mso::Path::MsoPathFindExtension(wchar_t const *)
0x1803f55ed  mov     rsi, rax
0x1803f55f0  test    rax, rax
0x1803f55f3  jz      loc_1803F597B
0x1803f55f9  cmp     word ptr [rax], 2Eh ; '.'
0x1803f55fd  jnz     loc_1803F597B
0x1803f5603  xorps   xmm0, xmm0
0x1803f5606  movups  [rbp+0B0h+var_58], xmm0
0x1803f560a  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1803f5612  movdqu  [rbp+0B0h+var_48], xmm1
0x1803f5617  mov     word ptr [rbp+0B0h+var_58], bx
0x1803f561b  lea     rdx, [rbp+0B0h+var_58]
0x1803f561f  lea     rcx, ?vmsoridSecurityBlockedExtensions@@3U_msoreg@@B; _msoreg const vmsoridSecurityBlockedExtensions
0x1803f5626  call    cs:__imp_?Read@Orapi@Mso@@YA_NAEBU_msoreg@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::Orapi::Read(_msoreg const &,std::wstring &)
0x1803f562c  lea     rdx, [rbp+0B0h+var_58]
0x1803f5630  cmp     qword ptr [rbp+0B0h+var_48+8], 7
0x1803f5635  cmova   rdx, qword ptr [rbp+0B0h+var_58]
0x1803f563a  mov     rcx, rsi
0x1803f563d  call    cs:__imp_?IsExtensionInList@Security@Mso@@YA_NPEB_W0@Z; Mso::Security::IsExtensionInList(wchar_t const *,wchar_t const *)
0x1803f5643  test    al, al
0x1803f5645  jz      short loc_1803F56C6
0x1803f5647  mov     dword ptr [rsp+1B0h+var_190], ebx
0x1803f564b  xor     r9d, r9d
0x1803f564e  xor     r8d, r8d
0x1803f5651  lea     edx, [r9+1]
0x1803f5655  lea     rcx, [rbp+0B0h+var_78]
0x1803f5659  call    ??0CDialogButtonSet@Jot@@QEAA@W4DisplayErrorResponse@1@000@Z; Jot::CDialogButtonSet::CDialogButtonSet(Jot::DisplayErrorResponse,Jot::DisplayErrorResponse,Jot::DisplayErrorResponse,Jot::DisplayErrorResponse)
0x1803f565e  movups  xmm0, xmmword ptr [rax]
0x1803f5661  movdqu  [rbp+0B0h+var_120], xmm0
0x1803f5666  mov     [rsp+1B0h+var_188], 3
0x1803f566e  mov     byte ptr [rsp+1B0h+var_190], bl
0x1803f5672  xor     r9d, r9d
0x1803f5675  xor     r8d, r8d
0x1803f5678  lea     rdx, [rbp+0B0h+var_120]
0x1803f567c  mov     ecx, r13d
0x1803f567f  call    ?DisplayErrorDialog@Jot@@YA?AW4DisplayErrorResponse@1@HVCDialogButtonSet@1@W421@1_NH@Z; Jot::DisplayErrorDialog(int,Jot::CDialogButtonSet,Jot::DisplayErrorResponse,Jot::DisplayErrorResponse,bool,int)
0x1803f5684  mov     edx, 2
0x1803f5689  lea     rcx, [rbp+0B0h+var_C0]
0x1803f568d  call    ??0EventFlags@Telemetry@Mso@@QEAA@W4DataCategories@12@@Z; Mso::Telemetry::EventFlags::EventFlags(Mso::Telemetry::DataCategories)
0x1803f5692  lea     rcx, off_18107D820
0x1803f5699  mov     [rsp+1B0h+var_178], rcx
0x1803f569e  lea     rcx, aEmbeddedfilebl_0; "EmbeddedFileBlockedByRegistryBlockList"
0x1803f56a5  mov     [rsp+1B0h+var_170], rcx
0x1803f56aa  mov     rdx, rax
0x1803f56ad  lea     rcx, [rsp+1B0h+var_178]
0x1803f56b2  call    ??$SendTelemetryEvent@$$V@Telemetry@Mso@@YAXAEBUEventName@01@AEBUEventFlags@01@@Z; Mso::Telemetry::SendTelemetryEvent<>(Mso::Telemetry::EventName const &,Mso::Telemetry::EventFlags const &)
0x1803f56b7  nop
0x1803f56b8  lea     rcx, [rbp+0B0h+var_58]; void *
0x1803f56bc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1803f56c1  jmp     loc_1803F5995
0x1803f56c6  lea     rcx, [rbp+0B0h+var_58]; void *
0x1803f56ca  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1803f56cf  xorps   xmm0, xmm0
0x1803f56d2  movups  [rbp+0B0h+var_98], xmm0
0x1803f56d6  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1803f56de  movdqu  [rbp+0B0h+var_88], xmm1
0x1803f56e3  mov     word ptr [rbp+0B0h+var_98], bx
0x1803f56e7  lea     rdx, [rbp+0B0h+var_98]
0x1803f56eb  lea     rcx, ?vmsoridSecurityAllowedExtensions@@3U_msoreg@@B; _msoreg const vmsoridSecurityAllowedExtensions
0x1803f56f2  call    cs:__imp_?Read@Orapi@Mso@@YA_NAEBU_msoreg@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::Orapi::Read(_msoreg const &,std::wstring &)
0x1803f56f8  lea     rdx, [rbp+0B0h+var_98]
0x1803f56fc  cmp     qword ptr [rbp+0B0h+var_88+8], 7
0x1803f5701  cmova   rdx, qword ptr [rbp+0B0h+var_98]
0x1803f5706  mov     rcx, rsi
0x1803f5709  call    cs:__imp_?IsExtensionInList@Security@Mso@@YA_NPEB_W0@Z; Mso::Security::IsExtensionInList(wchar_t const *,wchar_t const *)
0x1803f570f  mov     r14b, al
0x1803f5712  mov     rcx, rsi
0x1803f5715  call    cs:__imp_?CheckExtensionSafetyFromService@Security@Mso@@YA?AW4ExtensionSafetyLevel@12@PEB_W@Z; Mso::Security::CheckExtensionSafetyFromService(wchar_t const *)
0x1803f571b  test    eax, eax
0x1803f571d  jnz     loc_1803F588C
0x1803f5723  test    r14b, r14b
0x1803f5726  jz      short loc_1803F5764
0x1803f5728  cmp     [rbp+0B0h+arg_38], bl
0x1803f572e  jz      loc_1803F594F
0x1803f5734  mov     rdx, rdi
0x1803f5737  lea     rcx, [rbp+0B0h+var_120]
0x1803f573b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1803f5740  xor     edx, edx
0x1803f5742  mov     r8d, r12d
0x1803f5745  mov     r9d, [rbp+0B0h+arg_20]
0x1803f574c  mov     [rsp+1B0h+var_190], r15; __int64
0x1803f5751  mov     rcx, rax; void *
0x1803f5754  call    ?FSafeToOpenShowPrompt@Jot@@YA_NV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NIIPEBU_msoreg@@@Z; Jot::FSafeToOpenShowPrompt(std::wstring,bool,uint,uint,_msoreg const *)
0x1803f5759  mov     bl, al
0x1803f575b  lea     rcx, [rbp+0B0h+var_98]
0x1803f575f  jmp     loc_1803F56BC
0x1803f5764  mov     dword ptr [rsp+1B0h+var_190], ebx
0x1803f5768  xor     r9d, r9d
0x1803f576b  xor     r8d, r8d
0x1803f576e  lea     edx, [r9+1]
0x1803f5772  lea     rcx, [rbp+0B0h+var_78]
0x1803f5776  call    ??0CDialogButtonSet@Jot@@QEAA@W4DisplayErrorResponse@1@000@Z; Jot::CDialogButtonSet::CDialogButtonSet(Jot::DisplayErrorResponse,Jot::DisplayErrorResponse,Jot::DisplayErrorResponse,Jot::DisplayErrorResponse)
0x1803f577b  movups  xmm0, xmmword ptr [rax]
0x1803f577e  movdqu  [rbp+0B0h+var_120], xmm0
0x1803f5783  mov     [rsp+1B0h+var_188], 3
0x1803f578b  mov     byte ptr [rsp+1B0h+var_190], bl
0x1803f578f  xor     r9d, r9d
0x1803f5792  xor     r8d, r8d
0x1803f5795  lea     rdx, [rbp+0B0h+var_120]
0x1803f5799  mov     ecx, r13d
0x1803f579c  call    ?DisplayErrorDialog@Jot@@YA?AW4DisplayErrorResponse@1@HVCDialogButtonSet@1@W421@1_NH@Z; Jot::DisplayErrorDialog(int,Jot::CDialogButtonSet,Jot::DisplayErrorResponse,Jot::DisplayErrorResponse,bool,int)
0x1803f57a1  mov     [rsp+1B0h+var_178], rsi
0x1803f57a6  lea     rax, ??_7?$StructuredTraceImplementation@UNonPiiWz@Logging@Jot@@@details@Logging@Jot@@6BIStructuredTrace@2Mso@@@; const Jot::Logging::details::StructuredTraceImplementation<Jot::Logging::NonPiiWz>::`vftable'{for `Mso::Logging::IStructuredTrace'}
0x1803f57ad  mov     [rbp+0B0h+var_F0], rax
0x1803f57b1  lea     rax, ??_7?$StructuredTraceImplementation@UNonPiiWz@Logging@Jot@@@details@Logging@Jot@@6BIDataField@Telemetry@Mso@@@; const Jot::Logging::details::StructuredTraceImplementation<Jot::Logging::NonPiiWz>::`vftable'{for `Mso::Telemetry::IDataField'}
0x1803f57b8  mov     [rbp+0B0h+var_E8], rax
0x1803f57bc  lea     rax, aExtension; "Extension"
0x1803f57c3  mov     [rbp+0B0h+var_E0], rax
0x1803f57c7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1803f57cb  mov     [rbp+0B0h+var_D8], rax
0x1803f57cf  lea     rax, [rsp+1B0h+var_178]
0x1803f57d4  mov     [rbp+0B0h+var_D0], rax
0x1803f57d8  mov     ecx, 4
0x1803f57dd  mov     [rbp+0B0h+var_C8], cx
0x1803f57e1  lea     edx, [rcx-2]
0x1803f57e4  lea     rcx, [rbp+0B0h+var_C0]
0x1803f57e8  call    ??0EventFlags@Telemetry@Mso@@QEAA@W4DataCategories@12@@Z; Mso::Telemetry::EventFlags::EventFlags(Mso::Telemetry::DataCategories)
0x1803f57ed  lea     rcx, off_18107D820
0x1803f57f4  mov     qword ptr [rbp+0B0h+var_100], rcx
0x1803f57f8  lea     rcx, aEmbeddedfilebl; "EmbeddedFileBlockedByServerBlockList"
0x1803f57ff  mov     qword ptr [rbp+0B0h+var_100+8], rcx
0x1803f5803  xorps   xmm0, xmm0
0x1803f5806  movdqu  [rbp+0B0h+var_120], xmm0
0x1803f580b  xorps   xmm1, xmm1
0x1803f580e  movdqu  [rbp+0B0h+var_78], xmm1
0x1803f5813  lea     rcx, [rbp+0B0h+var_100]
0x1803f5817  mov     qword ptr [rsp+1B0h+var_160], rcx
0x1803f581c  mov     qword ptr [rsp+1B0h+var_160+8], rax
0x1803f5821  mov     al, byte ptr [rsp+1B0h+var_180]
0x1803f5825  mov     byte ptr [rsp+1B0h+var_150], al
0x1803f5829  mov     byte ptr [rsp+1B0h+var_150+1], bl
0x1803f582d  mov     eax, [rsp+1B0h+var_180]
0x1803f5831  mov     dword ptr [rsp+1B0h+var_150+2], eax
0x1803f5835  mov     al, [rsp+1B0h+var_17C]
0x1803f5839  mov     byte ptr [rsp+1B0h+var_150+6], al
0x1803f583d  mov     byte ptr [rsp+1B0h+var_150+7], bl
0x1803f5841  lea     rdx, [rbp+0B0h+var_78]
0x1803f5845  lea     rcx, [rsp+1B0h+var_148]
0x1803f584a  call    ??$?0VItem@AugLoop@Office@Microsoft@@$0A@@?$shared_ptr@UISerializable@AugLoop@Office@Microsoft@@@std@@QEAA@AEBV?$shared_ptr@VItem@AugLoop@Office@Microsoft@@@1@@Z; std::shared_ptr<Microsoft::Office::AugLoop::ISerializable>::shared_ptr<Microsoft::Office::AugLoop::ISerializable>(std::shared_ptr<Microsoft::Office::AugLoop::Item> const &)
0x1803f584f  lea     rdx, [rbp+0B0h+var_120]
0x1803f5853  lea     rcx, [rsp+1B0h+var_138]
0x1803f5858  call    ??0?$shared_ptr@UEventContract@Telemetry@Mso@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Mso::Telemetry::EventContract>::shared_ptr<Mso::Telemetry::EventContract>(std::shared_ptr<Mso::Telemetry::EventContract> const &)
0x1803f585d  lea     rdx, [rbp+0B0h+var_F0]
0x1803f5861  lea     rcx, [rsp+1B0h+var_160]
0x1803f5866  call    ??$CreateAndUseCompositeDataField@V_lambda_1_@?1???$SendTelemetryEvent@VErrorData@Logging@Jot@@@Details@Telemetry@Mso@@YAXAEBUEventName@34@AEBV?$shared_ptr@VEvent@System@Office@@@std@@AEBV?$shared_ptr@UEventContract@Telemetry@Mso@@@7@AEBUEventFlags@34@$$QEAV?$optional@VEventExportability@Telemetry@Mso@@@7@$$QEAV?$optional@VEventSamplingMetadata@Telemetry@Mso@@@7@$$QEAVErrorData@Logging@Jot@@@Z@VErrorData@Logging@Jot@@@Details@Telemetry@Mso@@YAX$$QEAV_lambda_1_@?1???$SendTelemetryEvent@VErrorData@Logging@Jot@@@012@YAXAEBUEventName@12@AEBV?$shared_ptr@VEvent@System@Office@@@std@@AEBV?$shared_ptr@UEventContract@Telemetry@Mso@@@6@AEBUEventFlags@12@$$QEAV?$optional@VEventExportability@Telemetry@Mso@@@6@$$QEAV?$optional@VEventSamplingMetadata@Telemetry@Mso@@@6@$$QEAVErrorData@Logging@Jot@@@Z@6@Z; Mso::Telemetry::Details::CreateAndUseCompositeDataField<`Mso::Telemetry::Details::SendTelemetryEvent<Jot::Logging::ErrorData>(Mso::Telemetry::EventName const &,std::shared_ptr<Office::System::Event> const &,std::shared_ptr<Mso::Telemetry::EventContract> const &,Mso::Telemetry::EventFlags const &,std::optional<Mso::Telemetry::EventExportability> &&,std::optional<Mso::Telemetry::EventSamplingMetadata> &&,Jot::Logging::ErrorData &&)'::`2'::_lambda_1_,Jot::Logging::ErrorData>(`Mso::Telemetry::Details::SendTelemetryEvent<Jot::Logging::ErrorData>(Mso::Telemetry::EventName const &,std::shared_ptr<Office::System::Event> const &,std::shared_ptr<Mso::Telemetry::EventContract> const &,Mso::Telemetry::EventFlags const &,std::optional<Mso::Telemetry::EventExportability> &&,std::optional<Mso::Telemetry::EventSamplingMetadata> &&,Jot::Logging::ErrorData &&)'::`2'::_lambda_1_ &&,Jot::Logging::ErrorData &&)
0x1803f586b  lea     rcx, [rsp+1B0h+var_160]
0x1803f5870  call    ??1_lambda_1_@?1???$SendTelemetryEvent@U?$StructuredTraceImplementation@U_GUID@@@details@Logging@Jot@@VErrorData@34@@Details@Telemetry@Mso@@YAXAEBUEventName@23@AEBV?$shared_ptr@VEvent@System@Office@@@std@@AEBV?$shared_ptr@UEventContract@Telemetry@Mso@@@6@AEBUEventFlags@23@$$QEAV?$optional@VEventExportability@Telemetry@Mso@@@6@$$QEAV?$optional@VEventSamplingMetadata@Telemetry@Mso@@@6@$$QEAU?$StructuredTraceImplementation@U_GUID@@@details@Logging@Jot@@$$QEAVErrorData@Logging@Jot@@@Z@QEAA@XZ; `Mso::Telemetry::Details::SendTelemetryEvent<Jot::Logging::details::StructuredTraceImplementation<_GUID>,Jot::Logging::ErrorData>(Mso::Telemetry::EventName const &,std::shared_ptr<Office::System::Event> const &,std::shared_ptr<Mso::Telemetry::EventContract> const &,Mso::Telemetry::EventFlags const &,std::optional<Mso::Telemetry::EventExportability> &&,std::optional<Mso::Telemetry::EventSamplingMetadata> &&,Jot::Logging::details::StructuredTraceImplementation<_GUID> &&,Jot::Logging::ErrorData &&)'::`2'::_lambda_1_::~_lambda_1_(void)
0x1803f5875  lea     rcx, [rbp+0B0h+var_78]; void *
0x1803f5879  call    ??1?$shared_ptr@USourceColorBitmap@xpsrdr@@@std@@QEAA@XZ; std::shared_ptr<xpsrdr::SourceColorBitmap>::~shared_ptr<xpsrdr::SourceColorBitmap>(void)
0x1803f587e  lea     rcx, [rbp+0B0h+var_120]; void *
0x1803f5882  call    ??1?$shared_ptr@USourceColorBitmap@xpsrdr@@@std@@QEAA@XZ; std::shared_ptr<xpsrdr::SourceColorBitmap>::~shared_ptr<xpsrdr::SourceColorBitmap>(void)
0x1803f5887  jmp     loc_1803F575B
0x1803f588c  mov     r14b, 1
0x1803f588f  mov     [rsp+1B0h+var_180], ebx
0x1803f5893  xorps   xmm0, xmm0
0x1803f5896  xor     eax, eax
0x1803f5898  movups  [rsp+1B0h+var_160], xmm0
0x1803f589d  mov     [rsp+1B0h+var_150], rax
0x1803f58a2  xorps   xmm1, xmm1
0x1803f58a5  movups  [rsp+1B0h+var_148], xmm1
0x1803f58aa  movups  [rsp+1B0h+var_138], xmm1
0x1803f58af  mov     [rbp+0B0h+var_128], bl
0x1803f58b2  lea     rax, [rsp+1B0h+var_160]
0x1803f58b7  mov     qword ptr [rsp+1B0h+var_138], rax
0x1803f58bc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1803f58c0  inc     rax
0x1803f58c3  cmp     [rsi+rax*2], bx
0x1803f58c7  jnz     short loc_1803F58C0
0x1803f58c9  test    r15, r15
0x1803f58cc  jnz     short loc_1803F58DE
0x1803f58ce  mov     ecx, 1E483458h
0x1803f58d3  call    cs:__imp_MsoShipAssertTagProc
0x1803f58d9  mov     r14b, bl
0x1803f58dc  jmp     short loc_1803F5915
0x1803f58de  mov     dword ptr [rsp+1B0h+var_190], 4
0x1803f58e6  mov     r9, rax
0x1803f58e9  mov     r8, rsi
0x1803f58ec  mov     rdx, r15
0x1803f58ef  lea     rcx, [rsp+1B0h+var_160]
0x1803f58f4  call    cs:__imp_?InitForValue@DynamicMsorid@@QEAAXAEBU_msoreg@@PEB_W_KW4RegValueType@@@Z; DynamicMsorid::InitForValue(_msoreg const &,wchar_t const *,unsigned __int64,RegValueType)
0x1803f58fa  mov     al, [rbp+0B0h+var_128]
0x1803f58fd  neg     al
0x1803f58ff  sbb     rcx, rcx
0x1803f5902  lea     rax, [rsp+1B0h+var_148]
0x1803f5907  and     rcx, rax
0x1803f590a  lea     rdx, [rsp+1B0h+var_180]
0x1803f590f  call    cs:__imp_?MsoFRegGetDw@@YAHPEBU_msoreg@@PEAK@Z; MsoFRegGetDw(_msoreg const *,ulong *)
0x1803f5915  lea     rcx, [rsp+1B0h+var_160]; this
0x1803f591a  call    ??1DynamicMsorid@@QEAA@XZ; DynamicMsorid::~DynamicMsorid(void)
0x1803f591f  mov     eax, [rsp+1B0h+var_180]
0x1803f5923  and     eax, 3
0x1803f5926  cmp     eax, 2
0x1803f5929  jnz     short loc_1803F594A
0x1803f592b  mov     r14b, bl
0x1803f592e  cmp     [rbp+0B0h+arg_38], bl
0x1803f5934  jz      short loc_1803F595A
0x1803f5936  mov     rdx, rdi
0x1803f5939  lea     rcx, [rbp+0B0h+var_78]
0x1803f593d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1803f5942  mov     dl, r14b
0x1803f5945  jmp     loc_1803F5742
0x1803f594a  cmp     eax, 1
0x1803f594d  jnz     short loc_1803F592E
0x1803f594f  lea     rcx, [rbp+0B0h+var_98]; void *
0x1803f5953  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1803f5958  jmp     short loc_1803F5993
0x1803f595a  lea     rcx, [rbp+0B0h+var_98]; void *
0x1803f595e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1803f5963  lea     rcx, [rbp+0B0h+pszPath]; void *
0x1803f5967  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1803f596c  mov     rcx, rdi; void *
0x1803f596f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1803f5974  mov     al, 1
0x1803f5976  jmp     loc_1803F5AEB
0x1803f597b  lea     rcx, [rbp+0B0h+pszPath]
0x1803f597f  cmp     qword ptr [rbp+0B0h+var_A8+8], 7
0x1803f5984  cmova   rcx, [rbp+0B0h+pszPath]; pszPath
0x1803f5989  call    cs:__imp_PathIsDirectoryW
0x1803f598f  test    eax, eax
0x1803f5991  jz      short loc_1803F59AD
0x1803f5993  mov     bl, 1
0x1803f5995  lea     rcx, [rbp+0B0h+pszPath]; void *
0x1803f5999  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1803f599e  mov     rcx, rdi; void *
0x1803f59a1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1803f59a6  mov     al, bl
0x1803f59a8  jmp     loc_1803F5AEB
0x1803f59ad  mov     dword ptr [rsp+1B0h+var_190], ebx
0x1803f59b1  xor     r9d, r9d
0x1803f59b4  xor     r8d, r8d
0x1803f59b7  lea     edx, [r9+1]
0x1803f59bb  lea     rcx, [rbp+0B0h+var_78]
0x1803f59bf  call    ??0CDialogButtonSet@Jot@@QEAA@W4DisplayErrorResponse@1@000@Z; Jot::CDialogButtonSet::CDialogButtonSet(Jot::DisplayErrorResponse,Jot::DisplayErrorResponse,Jot::DisplayErrorResponse,Jot::DisplayErrorResponse)
0x1803f59c4  movups  xmm0, xmmword ptr [rax]
0x1803f59c7  movdqu  [rbp+0B0h+var_120], xmm0
0x1803f59cc  mov     [rsp+1B0h+var_188], 3
0x1803f59d4  mov     byte ptr [rsp+1B0h+var_190], bl
0x1803f59d8  xor     r9d, r9d
0x1803f59db  xor     r8d, r8d
0x1803f59de  lea     rdx, [rbp+0B0h+var_120]
0x1803f59e2  mov     ecx, r13d
0x1803f59e5  call    ?DisplayErrorDialog@Jot@@YA?AW4DisplayErrorResponse@1@HVCDialogButtonSet@1@W421@1_NH@Z; Jot::DisplayErrorDialog(int,Jot::CDialogButtonSet,Jot::DisplayErrorResponse,Jot::DisplayErrorResponse,bool,int)
0x1803f59ea  lea     rax, WindowName
0x1803f59f1  mov     [rsp+1B0h+var_178], rax
0x1803f59f6  lea     rax, ??_7?$StructuredTraceImplementation@UNonPiiWz@Logging@Jot@@@details@Logging@Jot@@6BIStructuredTrace@2Mso@@@; const Jot::Logging::details::StructuredTraceImplementation<Jot::Logging::NonPiiWz>::`vftable'{for `Mso::Logging::IStructuredTrace'}
0x1803f59fd  mov     [rbp+0B0h+var_F0], rax
0x1803f5a01  lea     rax, ??_7?$StructuredTraceImplementation@UNonPiiWz@Logging@Jot@@@details@Logging@Jot@@6BIDataField@Telemetry@Mso@@@; const Jot::Logging::details::StructuredTraceImplementation<Jot::Logging::NonPiiWz>::`vftable'{for `Mso::Telemetry::IDataField'}
0x1803f5a08  mov     [rbp+0B0h+var_E8], rax
0x1803f5a0c  lea     rax, aExtension; "Extension"
0x1803f5a13  mov     [rbp+0B0h+var_E0], rax
0x1803f5a17  or      rax, 0FFFFFFFFFFFFFFFFh
0x1803f5a1b  mov     [rbp+0B0h+var_D8], rax
0x1803f5a1f  lea     rax, [rsp+1B0h+var_178]
0x1803f5a24  mov     [rbp+0B0h+var_D0], rax
0x1803f5a28  mov     ecx, 4
  ... truncated ...
```
