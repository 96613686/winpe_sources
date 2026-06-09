# HidLampArrayDevice::Initialize(PnpDevice *)

- ea: `0x180128e84`
- end: `0x180129780`
- name: `?Initialize@HidLampArrayDevice@@AEAAJPEAVPnpDevice@@@Z`
- size: `2300`
- prototype: `__int64 __fastcall(HidLampArrayDevice *__hidden this, struct PnpDevice *)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x180128ce0`

## callees

- `0x180004a34`
- `0x18002f9d0`
- `0x180064a30`
- `0x180073e90`
- `0x18007dc50`
- `0x18008044c`
- `0x18008e2b4`
- `0x18008ead4`
- `0x18008fbec`
- `0x18009fd34`
- `0x1800b0244`
- `0x1800f0990`
- `0x1800f0a90`
- `0x1800f2478`
- `0x18010c734`
- `0x180125288`
- `0x180127220`
- `0x180127290`
- `0x180127394`
- `0x180127410`
- `0x180128860`
- `0x180128bdc`
- `0x180128e84`
- `0x1801298f0`
- `0x180129a7c`
- `0x180129fb0`
- `0x18012a298`
- `0x18012b044`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180128f87`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180128f87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012901d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180129178`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012901d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180129178`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180128ecb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180129725`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180129750`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180128ecb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180129725`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180129750`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180128f08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180128f4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180128fcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012912c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801291d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012933a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801293b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801295ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180129633`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180128f08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180128f4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180128fcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012912c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801291d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012933a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801293b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801295ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180129633`
- `HID!HidD_GetAttributes` at `0x18012916e`
- `HID!HidD_GetAttributes` at `0x18012916e`
- `HID!HidD_GetPreparsedData` at `0x180129013`
- `HID!HidD_GetPreparsedData` at `0x180129013`

## string_xrefs

- `0x180128fd7`: `Extracting HID report descriptors`
- `0x180128f12`: `Attempting to initialize HidLampArrayDevice`

## pseudocode

```c
__int64 __fastcall HidLampArrayDevice::Initialize(HidLampArrayDevice *this, struct PnpDevice *a2)
{
  PnpDevice **v4; // rdi
  int InterfacePath; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  int v8; // r8d
  int v9; // r9d
  PCWSTR StringRawBuffer; // rax
  int v11; // r14d
  unsigned int v12; // eax
  int v13; // eax
  int v14; // r8d
  int v15; // r9d
  __int64 v16; // rcx
  signed int v17; // eax
  __int64 v18; // rdx
  int v19; // eax
  __int64 v20; // rdx
  int v21; // r8d
  int v22; // r9d
  signed int LastError; // eax
  LampArrayTelemetry *v24; // rcx
  int v25; // r8d
  int v26; // r9d
  unsigned __int64 v27; // rcx
  unsigned __int64 v28; // rax
  void *v29; // rax
  const struct std::nothrow_t *v30; // rdx
  void *v31; // rcx
  unsigned __int64 v32; // rcx
  unsigned __int64 v33; // rax
  void *v34; // rax
  const struct std::nothrow_t *v35; // rdx
  void *v36; // rcx
  int v37; // ebx
  int v38; // ecx
  int v39; // r8d
  int v40; // r9d
  int v41; // edi
  int v42; // ecx
  int v43; // r8d
  int v44; // r9d
  __int64 v45; // rdx
  unsigned int v46; // r8d
  int v47; // ecx
  __int16 v48; // bx
  __int16 v49; // di
  __int16 v50; // si
  int v51; // ecx
  __int64 v52; // rdx
  int v53; // r8d
  int v54; // r9d
  int v55; // r8d
  int v56; // r9d
  unsigned __int64 v57; // r9
  LampArrayTelemetry *v58; // rcx
  unsigned int v60; // [rsp+20h] [rbp-99h]
  __int16 v61; // [rsp+30h] [rbp-89h]
  struct ParsedHidReportDescriptor *v62; // [rsp+60h] [rbp-59h] BYREF
  unsigned int v63[2]; // [rsp+68h] [rbp-51h] BYREF
  HSTRING string; // [rsp+70h] [rbp-49h] BYREF
  PHIDP_PREPARSED_DATA PreparsedData; // [rsp+78h] [rbp-41h] BYREF
  const char *v66; // [rsp+80h] [rbp-39h] BYREF
  UINT32 length; // [rsp+88h] [rbp-31h] BYREF
  __int128 v68; // [rsp+90h] [rbp-29h] BYREF
  __int128 v69; // [rsp+A0h] [rbp-19h]
  int v70; // [rsp+B0h] [rbp-9h]
  int v71[4]; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v72; // [rsp+C8h] [rbp+Fh]
  _HIDD_ATTRIBUTES Attributes; // [rsp+D8h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v4 = (PnpDevice **)((char *)this + 16);
  Microsoft::WRL::ComPtr<HidLampArrayDevice>::operator=((char *)this + 16);
  WindowsDeleteString(0);
  string = 0;
  InterfacePath = PnpDevice::GetInterfacePath(a2, &string);
  v6 = InterfacePath;
  if ( InterfacePath < 0 )
  {
    v7 = 53;
LABEL_85:
    v57 = (unsigned int)InterfacePath;
LABEL_89:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\hidlamparraydevice.cpp",
      (const char *)v57,
      v60);
    goto LABEL_90;
  }
  if ( (unsigned int)dword_180241248 > 5 )
  {
    PreparsedData = (PHIDP_PREPARSED_DATA)WindowsGetStringRawBuffer(string, 0);
    v62 = (struct ParsedHidReportDescriptor *)"Attempting to initialize HidLampArrayDevice";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
      (unsigned int)&dword_180241248,
      (unsigned int)word_180208002,
      v8,
      v9,
      (__int64)&v62,
      (__int64)&PreparsedData);
  }
  length = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
  if ( !length || !*StringRawBuffer )
  {
    v6 = -2147024809;
    v7 = 59;
    goto LABEL_88;
  }
  if ( length > 0x100 )
  {
    v6 = -2147024774;
    v7 = 60;
    goto LABEL_88;
  }
  v11 = (_DWORD)this + 24;
  v12 = _o_wcscpy_s((char *)this + 24, 256, StringRawBuffer);
  if ( !v12 )
  {
    v13 = PnpDevice::OpenInterface(*v4);
    if ( v13 < 0 )
      goto LABEL_11;
    if ( (unsigned int)dword_180241248 > 5 )
    {
      v62 = (struct ParsedHidReportDescriptor *)WindowsGetStringRawBuffer(string, 0);
      *(_QWORD *)v63 = "Extracting HID report descriptors";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        (unsigned int)&dword_180241248,
        (unsigned int)&byte_180208047,
        v14,
        v15,
        (__int64)v63,
        (__int64)&v62);
    }
    PreparsedData = 0;
    if ( HidD_GetPreparsedData(*((HANDLE *)*v4 + 5), &PreparsedData) )
    {
      if ( *((_WORD *)PreparsedData + 5) == 89 )
      {
        if ( *((_WORD *)PreparsedData + 4) == 1 )
        {
          v62 = 0;
          v63[0] = 0;
          v19 = HidLampArrayDevice::ExtractReportDescriptorsFromPreparsedData(v16, PreparsedData, &v62, v63);
          v6 = v19;
          if ( v19 >= 0 )
          {
            v19 = HidLampArrayDevice::CacheReportSizes(this, v62, v63[0]);
            v6 = v19;
            if ( v19 >= 0 )
            {
              v19 = HidLampArrayDevice::ParseReportDescriptors(this, v62, v63[0]);
              v6 = v19;
              if ( v19 >= 0 )
              {
                std::unique_ptr<ParsedHidReportDescriptor [0]>::~unique_ptr<ParsedHidReportDescriptor [0]>(&v62);
                wil::details::unique_storage<wil::details::resource_policy<_HIDP_PREPARSED_DATA *,unsigned char (*)(_HIDP_PREPARSED_DATA *),&unsigned char HidD_FreePreparsedData(_HIDP_PREPARSED_DATA *),wistd::integral_constant<unsigned __int64,0>,_HIDP_PREPARSED_DATA *,_HIDP_PREPARSED_DATA *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_HIDP_PREPARSED_DATA *,unsigned char (*)(_HIDP_PREPARSED_DATA *),&unsigned char HidD_FreePreparsedData(_HIDP_PREPARSED_DATA *),wistd::integral_constant<unsigned __int64,0>,_HIDP_PREPARSED_DATA *,_HIDP_PREPARSED_DATA *,0,std::nullptr_t>>(&PreparsedData);
                *(_QWORD *)&Attributes.Size = 0;
                *(_DWORD *)&Attributes.VersionNumber = 0;
                if ( (unsigned int)dword_180241248 > 5 )
                {
                  v62 = (struct ParsedHidReportDescriptor *)WindowsGetStringRawBuffer(string, 0);
                  *(_QWORD *)v63 = "Querying HIDD_ATTRIBUTES";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
                    (unsigned int)&dword_180241248,
                    (unsigned int)&dword_18020808C,
                    v21,
                    v22,
                    (__int64)v63,
                    (__int64)&v62);
                }
                if ( !HidD_GetAttributes(*((HANDLE *)*v4 + 5), &Attributes) )
                {
                  LastError = GetLastError();
                  v6 = LastError;
                  if ( LastError > 0 )
                    v6 = (unsigned __int16)LastError | 0x80070000;
                  LampArrayTelemetry::GetInstance();
                  LampArrayTelemetry::LogLampArrayHidDeviceAttributesFailure(
                    v24,
                    v6,
                    (const unsigned __int16 *)this + 12);
                  goto LABEL_90;
                }
                *((_WORD *)this + 269) = Attributes.VendorID;
                *((_WORD *)this + 270) = Attributes.ProductID;
                *((_WORD *)this + 271) = Attributes.VersionNumber;
                if ( (unsigned int)dword_180241248 > 5 )
                {
                  v62 = (struct ParsedHidReportDescriptor *)WindowsGetStringRawBuffer(string, 0);
                  *(_QWORD *)v63 = "Querying LampArrayAttributesReport";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
                    (unsigned int)&dword_180241248,
                    (unsigned int)byte_180207F0D,
                    v25,
                    v26,
                    (__int64)v63,
                    (__int64)&v62);
                }
                *(_OWORD *)v71 = 0;
                v72 = 0;
                InterfacePath = HidLampArrayDevice::ReceiveLampArrayAttributesReport(
                                  this,
                                  (struct LampArrayAttributesDeviceReport *)v71);
                v6 = InterfacePath;
                if ( InterfacePath < 0 )
                {
                  v7 = 110;
                  goto LABEL_85;
                }
                v27 = v71[0];
                *((_DWORD *)this + 136) = v71[0];
                *((_DWORD *)this + 137) = v71[1];
                *((_DWORD *)this + 138) = v71[2];
                *((_DWORD *)this + 139) = v71[3];
                *((_QWORD *)this + 70) = v72;
                v28 = 36 * v27;
                if ( !is_mul_ok(v27, 0x24u) )
                  v28 = -1;
                v29 = operator new[](v28, (const struct std::nothrow_t *)&std::nothrow);
                v31 = (void *)*((_QWORD *)this + 71);
                *((_QWORD *)this + 71) = v29;
                if ( v31 )
                  operator delete(v31, v30);
                if ( *((_QWORD *)this + 71) )
                {
                  v32 = *((int *)this + 136);
                  v33 = 4 * v32;
                  if ( !is_mul_ok(v32, 4u) )
                    v33 = -1;
                  v34 = operator new[](v33, (const struct std::nothrow_t *)&std::nothrow);
                  v36 = (void *)*((_QWORD *)this + 72);
                  *((_QWORD *)this + 72) = v34;
                  if ( v36 )
                    operator delete(v36, v35);
                  if ( *((_QWORD *)this + 72) )
                  {
                    v37 = 0;
                    if ( *((int *)this + 136) > 0 )
                    {
                      while ( 1 )
                      {
                        if ( (unsigned int)dword_180241248 > 5 )
                        {
                          v63[0] = *((_DWORD *)this + 136);
                          LODWORD(v62) = v37;
                          v66 = (const char *)WindowsGetStringRawBuffer(string, 0);
                          *(_QWORD *)v71 = "Sending LampAttributesRequest";
                          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                            v38,
                            (unsigned int)word_180207F52,
                            v39,
                            v40,
                            (__int64)v71,
                            (__int64)&v66,
                            (__int64)&v62,
                            (__int64)v63);
                        }
                        v41 = HidLampArrayDevice::SendLampAttributesRequest(this, v37);
                        if ( v41 < 0 )
                          break;
                        if ( (unsigned int)dword_180241248 > 5 )
                        {
                          LODWORD(v62) = *((_DWORD *)this + 136);
                          v63[0] = v37;
                          *(_QWORD *)v71 = WindowsGetStringRawBuffer(string, 0);
                          v66 = "Requesting LampAttributesReport";
                          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                            v42,
                            (unsigned int)word_180207FAA,
                            v43,
                            v44,
                            (__int64)&v66,
                            (__int64)v71,
                            (__int64)v63,
                            (__int64)&v62);
                        }
                        v68 = 0;
                        v69 = 0;
                        v70 = 0;
                        v41 = HidLampArrayDevice::ReceiveLampAttributesReport(
                                this,
                                v37,
                                (struct LampAttributesResponseDeviceReport *)&v68);
                        if ( v41 < 0 )
                        {
                          v52 = 144;
                          goto LABEL_76;
                        }
                        if ( (_DWORD)v68 != v37 )
                        {
                          LampArrayTelemetry::GetInstance();
                          v48 = *((_WORD *)this + 271);
                          v49 = *((_WORD *)this + 270);
                          v50 = *((_WORD *)this + 269);
                          std::string::string(
                            v71,
                            "LampArrayAttributesReport: lamp ID does not match most recent request");
                          v61 = v48;
                          v6 = -2089418751;
                          LampArrayTelemetry::LogLampArrayHidReportFailure(
                            v51,
                            (unsigned int)v71,
                            -2089418751,
                            v11,
                            v50,
                            v49,
                            v61);
                          std::string::~string(v71);
                          v7 = 157;
                          goto LABEL_88;
                        }
                        v45 = 9LL * v37;
                        *(_OWORD *)(*((_QWORD *)this + 71) + 4 * v45) = v68;
                        *(_DWORD *)(*((_QWORD *)this + 71) + 4 * v45 + 16) = v69;
                        *(_DWORD *)(*((_QWORD *)this + 71) + 4 * v45 + 24) = v70;
                        *(_DWORD *)(*((_QWORD *)this + 71) + 4 * v45 + 28) = DWORD2(v69);
                        *(_DWORD *)(*((_QWORD *)this + 71) + 4 * v45 + 20) = DWORD1(v69);
                        v46 = 0;
                        v63[0] = 0;
                        if ( *((_DWORD *)this + 140) == 1 )
                        {
                          HidUsageConverter::KeyboardHidUsageToVKey(
                            WORD6(v69),
                            (struct LampAttributes *)(*((_QWORD *)this + 71) + 36LL * v37),
                            v63);
                          v46 = v63[0];
                        }
                        else if ( *((_DWORD *)this + 140) == 2 )
                        {
                          if ( WORD6(v69) >= 6u )
                            v47 = 0;
                          else
                            v47 = *((_DWORD *)qword_1801F9DF8 + WORD6(v69));
                          *(_DWORD *)(*((_QWORD *)this + 71) + 36LL * v37 + 32) = v47;
                        }
                        else
                        {
                          *(_DWORD *)(*((_QWORD *)this + 71) + 36LL * v37 + 32) = 0;
                        }
                        *(_DWORD *)(*((_QWORD *)this + 72) + 4LL * v37++) = v46;
                        if ( v37 >= *((_DWORD *)this + 136) )
                          goto LABEL_77;
                      }
                      v52 = 136;
LABEL_76:
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)v52,
                        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\hidla"
                                      "mparraydevice.cpp",
                        (const char *)(unsigned int)v41,
                        v60);
                      v6 = v41;
                      goto LABEL_90;
                    }
LABEL_77:
                    if ( (unsigned int)dword_180241248 > 5 )
                    {
                      *(_QWORD *)v71 = WindowsGetStringRawBuffer(string, 0);
                      v66 = "Successfully parsed device data";
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
                        (unsigned int)&dword_180241248,
                        (unsigned int)byte_180207E83,
                        v53,
                        v54,
                        (__int64)&v66,
                        (__int64)v71);
                    }
                    if ( (unsigned int)dword_180241248 > 5 )
                    {
                      *(_QWORD *)v71 = WindowsGetStringRawBuffer(string, 0);
                      v66 = "Setting device to known-good-state.";
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
                        (unsigned int)&dword_180241248,
                        (unsigned int)&unk_180207EC8,
                        v55,
                        v56,
                        (__int64)&v66,
                        (__int64)v71);
                    }
                    InterfacePath = HidLampArrayDevice::SetAutonomousMode(this, 1);
                    v6 = InterfacePath;
                    if ( InterfacePath >= 0 )
                    {
                      *(_OWORD *)v71 = 0;
                      v71[0] = 1;
                      v71[2] = *((_DWORD *)this + 136) - 1;
                      InterfacePath = HidLampArrayDevice::SendLampRangeUpdateReport(
                                        this,
                                        (const struct LampRangeUpdateDeviceReport *)v71);
                      v6 = InterfacePath;
                      if ( InterfacePath >= 0 )
                      {
                        LampArrayTelemetry::GetInstance();
                        LampArrayTelemetry::LogLampArrayDeviceAdded(
                          v58,
                          (const unsigned __int16 *)this + 12,
                          *((_WORD *)this + 269),
                          *((_WORD *)this + 270),
                          *((_WORD *)this + 271),
                          *((_DWORD *)this + 136),
                          *((_DWORD *)this + 137),
                          *((_DWORD *)this + 138),
                          *((_DWORD *)this + 139),
                          *((_DWORD *)this + 140),
                          *((_DWORD *)this + 141));
                        *((_BYTE *)this + 645) = 1;
                        WindowsDeleteString(string);
                        return 0;
                      }
                      v7 = 207;
                    }
                    else
                    {
                      v7 = 201;
                    }
                    goto LABEL_85;
                  }
                  v6 = -2147024882;
                  v7 = 127;
                }
                else
                {
                  v6 = -2147024882;
                  v7 = 124;
                }
LABEL_88:
                v57 = v6;
                goto LABEL_89;
              }
              v20 = 84;
            }
            else
            {
              v20 = 81;
            }
          }
          else
          {
            v20 = 78;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v20,
            (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\hidlamparraydevice.cpp",
            (const char *)(unsigned int)v19,
            v60);
          std::unique_ptr<ParsedHidReportDescriptor [0]>::~unique_ptr<ParsedHidReportDescriptor [0]>(&v62);
          goto LABEL_21;
        }
        v6 = -2147024890;
        v18 = 73;
      }
      else
      {
        v6 = -2147024890;
        v18 = 72;
      }
    }
    else
    {
      v17 = GetLastError();
      v6 = v17;
      if ( v17 > 0 )
        v6 = (unsigned __int16)v17 | 0x80070000;
      if ( (v6 & 0x80000000) == 0 )
        goto LABEL_21;
      v18 = 71;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\hidlamparraydevice.cpp",
      (const char *)v6,
      v60);
LABEL_21:
    wil::details::unique_storage<wil::details::resource_policy<_HIDP_PREPARSED_DATA *,unsigned char (*)(_HIDP_PREPARSED_DATA *),&unsigned char HidD_FreePreparsedData(_HIDP_PREPARSED_DATA *),wistd::integral_constant<unsigned __int64,0>,_HIDP_PREPARSED_DATA *,_HIDP_PREPARSED_DATA *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_HIDP_PREPARSED_DATA *,unsigned char (*)(_HIDP_PREPARSED_DATA *),&unsigned char HidD_FreePreparsedData(_HIDP_PREPARSED_DATA *),wistd::integral_constant<unsigned __int64,0>,_HIDP_PREPARSED_DATA *,_HIDP_PREPARSED_DATA *,0,std::nullptr_t>>(&PreparsedData);
    goto LABEL_90;
  }
  v13 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x3D,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\hidlamparraydevice.cpp",
          (const char *)v12,
          v60);
LABEL_11:
  v6 = v13;
LABEL_90:
  WindowsDeleteString(string);
  return v6;
}

```

## disassembly

```asm
0x180128e84  mov     [rsp-8+arg_10], rbx
0x180128e89  mov     [rsp-8+arg_18], rsi
0x180128e8e  push    rbp
0x180128e8f  push    rdi
0x180128e90  push    r13
0x180128e92  push    r14
0x180128e94  push    r15
0x180128e96  lea     rbp, [rsp-37h]
0x180128e9b  sub     rsp, 0F0h
0x180128ea2  mov     rax, cs:__security_cookie
0x180128ea9  xor     rax, rsp
0x180128eac  mov     [rbp+57h+var_28], rax
0x180128eb0  mov     rbx, rdx
0x180128eb3  mov     rsi, rcx
0x180128eb6  lea     rdi, [rcx+10h]
0x180128eba  mov     rcx, rdi
0x180128ebd  call    ??4?$ComPtr@VHidLampArrayDevice@@@WRL@Microsoft@@QEAAAEAV012@PEAVHidLampArrayDevice@@@Z; Microsoft::WRL::ComPtr<HidLampArrayDevice>::operator=(HidLampArrayDevice *)
0x180128ec2  xor     r15d, r15d
0x180128ec5  mov     [rbp+57h+string], r15
0x180128ec9  xor     ecx, ecx; string
0x180128ecb  call    cs:__imp_WindowsDeleteString
0x180128ed1  mov     [rbp+57h+string], r15
0x180128ed5  lea     rdx, [rbp+57h+string]; HSTRING *
0x180128ed9  mov     rcx, rbx; this
0x180128edc  call    ?GetInterfacePath@PnpDevice@@QEAAJPEAPEAUHSTRING__@@@Z; PnpDevice::GetInterfacePath(HSTRING__ * *)
0x180128ee1  mov     ebx, eax
0x180128ee3  test    eax, eax
0x180128ee5  jns     short loc_180128EF0
0x180128ee7  lea     edx, [r15+35h]
0x180128eeb  jmp     loc_1801296AD
0x180128ef0  mov     eax, cs:dword_180241248
0x180128ef6  lea     r13, dword_180241248
0x180128efd  cmp     eax, 5
0x180128f00  jbe     short loc_180128F3E
0x180128f02  xor     edx, edx; length
0x180128f04  mov     rcx, [rbp+57h+string]; string
0x180128f08  call    cs:__imp_WindowsGetStringRawBuffer
0x180128f0e  mov     [rbp+57h+PreparsedData], rax
0x180128f12  lea     rax, aAttemptingToIn; "Attempting to initialize HidLampArrayDe"...
0x180128f19  mov     [rbp+57h+var_B0], rax
0x180128f1d  lea     rax, [rbp+57h+PreparsedData]
0x180128f21  mov     qword ptr [rsp+110h+var_E8], rax
0x180128f26  lea     rax, [rbp+57h+var_B0]
0x180128f2a  mov     qword ptr [rsp+110h+var_F0], rax; int
0x180128f2f  lea     rdx, word_180208002
0x180128f36  mov     rcx, r13
0x180128f39  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180128f3e  mov     [rbp+57h+length], r15d
0x180128f42  lea     rdx, [rbp+57h+length]; length
0x180128f46  mov     rcx, [rbp+57h+string]; string
0x180128f4a  call    cs:__imp_WindowsGetStringRawBuffer
0x180128f50  mov     ecx, [rbp+57h+length]
0x180128f53  test    ecx, ecx
0x180128f55  jz      loc_18012972F
0x180128f5b  cmp     [rax], r15w
0x180128f5f  jz      loc_18012972F
0x180128f65  mov     edx, 100h
0x180128f6a  cmp     ecx, edx
0x180128f6c  jbe     short loc_180128F7D
0x180128f6e  mov     ebx, 8007007Ah
0x180128f73  mov     edx, 3Ch ; '<'
0x180128f78  jmp     loc_180129739
0x180128f7d  lea     r14, [rsi+18h]
0x180128f81  mov     r8, rax
0x180128f84  mov     rcx, r14
0x180128f87  call    cs:__imp__o_wcscpy_s
0x180128f8d  test    eax, eax
0x180128f8f  jz      short loc_180128FB0
0x180128f91  mov     rcx, [rbp+5Fh]; this
0x180128f95  mov     r9d, eax; char *
0x180128f98  lea     r8, aOnecoreuapWind_174; "onecoreuap\\windows\\moderncore\\inputv"...
0x180128f9f  mov     edx, 3Dh ; '='; void *
0x180128fa4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180128fa9  mov     ebx, eax
0x180128fab  jmp     loc_18012974C
0x180128fb0  mov     rcx, [rdi]; this
0x180128fb3  call    ?OpenInterface@PnpDevice@@QEAAJXZ; PnpDevice::OpenInterface(void)
0x180128fb8  test    eax, eax
0x180128fba  js      short loc_180128FA9
0x180128fbc  mov     eax, cs:dword_180241248
0x180128fc2  cmp     eax, 5
0x180128fc5  jbe     short loc_180129003
0x180128fc7  xor     edx, edx; length
0x180128fc9  mov     rcx, [rbp+57h+string]; string
0x180128fcd  call    cs:__imp_WindowsGetStringRawBuffer
0x180128fd3  mov     [rbp+57h+var_B0], rax
0x180128fd7  lea     rax, aExtractingHidR; "Extracting HID report descriptors"
0x180128fde  mov     qword ptr [rbp+57h+var_A8], rax
0x180128fe2  lea     rax, [rbp+57h+var_B0]
0x180128fe6  mov     qword ptr [rsp+110h+var_E8], rax
0x180128feb  lea     rax, [rbp+57h+var_A8]
0x180128fef  mov     qword ptr [rsp+110h+var_F0], rax; int
0x180128ff4  lea     rdx, byte_180208047
0x180128ffb  mov     rcx, r13
0x180128ffe  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180129003  mov     [rbp+57h+PreparsedData], r15
0x180129007  mov     rax, [rdi]
0x18012900a  mov     rcx, [rax+28h]; HidDeviceObject
0x18012900e  nop
0x18012900f  lea     rdx, [rbp+57h+PreparsedData]; PreparsedData
0x180129013  call    cs:__imp_HidD_GetPreparsedData
0x180129019  test    al, al
0x18012901b  jnz     short loc_18012905C
0x18012901d  call    cs:__imp_GetLastError
0x180129023  mov     ebx, eax
0x180129025  test    eax, eax
0x180129027  jle     short loc_180129032
0x180129029  movzx   ebx, ax
0x18012902c  or      ebx, 80070000h
0x180129032  test    ebx, ebx
0x180129034  jns     short loc_18012904E
0x180129036  mov     edx, 47h ; 'G'; void *
0x18012903b  mov     rcx, [rbp+5Fh]; this
0x18012903f  mov     r9d, ebx; char *
0x180129042  lea     r8, aOnecoreuapWind_174; "onecoreuap\\windows\\moderncore\\inputv"...
0x180129049  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012904e  lea     rcx, [rbp+57h+PreparsedData]
0x180129052  call    ??1?$unique_storage@U?$resource_policy@PEAU_HIDP_PREPARSED_DATA@@P6AEPEAU1@@Z$1?HidD_FreePreparsedData@@YAE0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_HIDP_PREPARSED_DATA *,uchar (*)(_HIDP_PREPARSED_DATA *),&HidD_FreePreparsedData(_HIDP_PREPARSED_DATA *),wistd::integral_constant<unsigned __int64,0>,_HIDP_PREPARSED_DATA *,_HIDP_PREPARSED_DATA *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_HIDP_PREPARSED_DATA *,uchar (*)(_HIDP_PREPARSED_DATA *),&HidD_FreePreparsedData(_HIDP_PREPARSED_DATA *),wistd::integral_constant<unsigned __int64,0>,_HIDP_PREPARSED_DATA *,_HIDP_PREPARSED_DATA *,0,std::nullptr_t>>(void)
0x180129057  jmp     loc_18012974C
0x18012905c  mov     rdx, [rbp+57h+PreparsedData]
0x180129060  cmp     word ptr [rdx+0Ah], 59h ; 'Y'
0x180129065  jz      short loc_180129073
0x180129067  mov     ebx, 80070006h
0x18012906c  mov     edx, 48h ; 'H'
0x180129071  jmp     short loc_18012903B
0x180129073  mov     eax, 1
0x180129078  cmp     [rdx+8], ax
0x18012907c  jz      short loc_180129088
0x18012907e  mov     ebx, 80070006h
0x180129083  lea     edx, [rax+48h]
0x180129086  jmp     short loc_18012903B
0x180129088  mov     [rbp+57h+var_B0], r15
0x18012908c  mov     [rbp+57h+var_A8], r15d
0x180129090  lea     r9, [rbp+57h+var_A8]
0x180129094  lea     r8, [rbp+57h+var_B0]
0x180129098  call    ?ExtractReportDescriptorsFromPreparsedData@HidLampArrayDevice@@AEAAJQEAU_HIDP_PREPARSED_DATA@@AEAV?$unique_ptr@$$BY0A@UParsedHidReportDescriptor@@U?$default_delete@$$BY0A@UParsedHidReportDescriptor@@@std@@@std@@PEAI@Z; HidLampArrayDevice::ExtractReportDescriptorsFromPreparsedData(_HIDP_PREPARSED_DATA * const,std::unique_ptr<ParsedHidReportDescriptor [0]> &,uint *)
0x18012909d  mov     ebx, eax
0x18012909f  test    eax, eax
0x1801290a1  jns     short loc_1801290C6
0x1801290a3  mov     edx, 4Eh ; 'N'; void *
0x1801290a8  mov     rcx, [rbp+5Fh]; this
0x1801290ac  mov     r9d, eax; char *
0x1801290af  lea     r8, aOnecoreuapWind_174; "onecoreuap\\windows\\moderncore\\inputv"...
0x1801290b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801290bb  lea     rcx, [rbp+57h+var_B0]
0x1801290bf  call    ??1?$unique_ptr@$$BY0A@UParsedHidReportDescriptor@@U?$default_delete@$$BY0A@UParsedHidReportDescriptor@@@std@@@std@@QEAA@XZ; std::unique_ptr<ParsedHidReportDescriptor [0]>::~unique_ptr<ParsedHidReportDescriptor [0]>(void)
0x1801290c4  jmp     short loc_18012904E
0x1801290c6  mov     r8d, [rbp+57h+var_A8]; unsigned int
0x1801290ca  mov     rdx, [rbp+57h+var_B0]; struct ParsedHidReportDescriptor *
0x1801290ce  mov     rcx, rsi; this
0x1801290d1  call    ?CacheReportSizes@HidLampArrayDevice@@AEAAJPEAUParsedHidReportDescriptor@@I@Z; HidLampArrayDevice::CacheReportSizes(ParsedHidReportDescriptor *,uint)
0x1801290d6  mov     ebx, eax
0x1801290d8  test    eax, eax
0x1801290da  jns     short loc_1801290E3
0x1801290dc  mov     edx, 51h ; 'Q'
0x1801290e1  jmp     short loc_1801290A8
0x1801290e3  mov     r8d, [rbp+57h+var_A8]; unsigned int
0x1801290e7  mov     rdx, [rbp+57h+var_B0]; struct ParsedHidReportDescriptor *
0x1801290eb  mov     rcx, rsi; this
0x1801290ee  call    ?ParseReportDescriptors@HidLampArrayDevice@@AEAAJPEAUParsedHidReportDescriptor@@I@Z; HidLampArrayDevice::ParseReportDescriptors(ParsedHidReportDescriptor *,uint)
0x1801290f3  mov     ebx, eax
0x1801290f5  test    eax, eax
0x1801290f7  jns     short loc_180129100
0x1801290f9  mov     edx, 54h ; 'T'
0x1801290fe  jmp     short loc_1801290A8
0x180129100  lea     rcx, [rbp+57h+var_B0]
0x180129104  call    ??1?$unique_ptr@$$BY0A@UParsedHidReportDescriptor@@U?$default_delete@$$BY0A@UParsedHidReportDescriptor@@@std@@@std@@QEAA@XZ; std::unique_ptr<ParsedHidReportDescriptor [0]>::~unique_ptr<ParsedHidReportDescriptor [0]>(void)
0x180129109  lea     rcx, [rbp+57h+PreparsedData]
0x18012910d  call    ??1?$unique_storage@U?$resource_policy@PEAU_HIDP_PREPARSED_DATA@@P6AEPEAU1@@Z$1?HidD_FreePreparsedData@@YAE0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_HIDP_PREPARSED_DATA *,uchar (*)(_HIDP_PREPARSED_DATA *),&HidD_FreePreparsedData(_HIDP_PREPARSED_DATA *),wistd::integral_constant<unsigned __int64,0>,_HIDP_PREPARSED_DATA *,_HIDP_PREPARSED_DATA *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_HIDP_PREPARSED_DATA *,uchar (*)(_HIDP_PREPARSED_DATA *),&HidD_FreePreparsedData(_HIDP_PREPARSED_DATA *),wistd::integral_constant<unsigned __int64,0>,_HIDP_PREPARSED_DATA *,_HIDP_PREPARSED_DATA *,0,std::nullptr_t>>(void)
0x180129112  xor     eax, eax
0x180129114  mov     qword ptr [rbp+57h+Attributes.Size], rax
0x180129118  mov     dword ptr [rbp+57h+Attributes.VersionNumber], eax
0x18012911b  mov     eax, cs:dword_180241248
0x180129121  cmp     eax, 5
0x180129124  jbe     short loc_180129162
0x180129126  xor     edx, edx; length
0x180129128  mov     rcx, [rbp+57h+string]; string
0x18012912c  call    cs:__imp_WindowsGetStringRawBuffer
0x180129132  mov     [rbp+57h+var_B0], rax
0x180129136  lea     rax, aQueryingHiddAt; "Querying HIDD_ATTRIBUTES"
0x18012913d  mov     qword ptr [rbp+57h+var_A8], rax
0x180129141  lea     rax, [rbp+57h+var_B0]
0x180129145  mov     qword ptr [rsp+110h+var_E8], rax
0x18012914a  lea     rax, [rbp+57h+var_A8]
0x18012914e  mov     qword ptr [rsp+110h+var_F0], rax
0x180129153  lea     rdx, dword_18020808C
0x18012915a  mov     rcx, r13
0x18012915d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180129162  mov     rax, [rdi]
0x180129165  mov     rcx, [rax+28h]; HidDeviceObject
0x180129169  nop
0x18012916a  lea     rdx, [rbp+57h+Attributes]; Attributes
0x18012916e  call    cs:__imp_HidD_GetAttributes
0x180129174  test    al, al
0x180129176  jnz     short loc_1801291A1
0x180129178  call    cs:__imp_GetLastError
0x18012917e  mov     ebx, eax
0x180129180  test    eax, eax
0x180129182  jle     short loc_18012918D
0x180129184  movzx   ebx, ax
0x180129187  or      ebx, 80070000h
0x18012918d  call    ?GetInstance@LampArrayTelemetry@@SAPEAV1@XZ; LampArrayTelemetry::GetInstance(void)
0x180129192  mov     r8, r14; unsigned __int16 *
0x180129195  mov     edx, ebx; int
0x180129197  call    ?LogLampArrayHidDeviceAttributesFailure@LampArrayTelemetry@@QEAAXJPEBG@Z; LampArrayTelemetry::LogLampArrayHidDeviceAttributesFailure(long,ushort const *)
0x18012919c  jmp     loc_18012974C
0x1801291a1  movzx   eax, [rbp+57h+Attributes.VendorID]
0x1801291a5  mov     [rsi+21Ah], ax
0x1801291ac  movzx   eax, [rbp+57h+Attributes.ProductID]
0x1801291b0  mov     [rsi+21Ch], ax
0x1801291b7  movzx   eax, [rbp+57h+Attributes.VersionNumber]
0x1801291bb  mov     [rsi+21Eh], ax
0x1801291c2  mov     eax, cs:dword_180241248
0x1801291c8  cmp     eax, 5
0x1801291cb  jbe     short loc_180129209
0x1801291cd  xor     edx, edx; length
0x1801291cf  mov     rcx, [rbp+57h+string]; string
0x1801291d3  call    cs:__imp_WindowsGetStringRawBuffer
0x1801291d9  mov     [rbp+57h+var_B0], rax
0x1801291dd  lea     rax, aQueryingLampar; "Querying LampArrayAttributesReport"
0x1801291e4  mov     qword ptr [rbp+57h+var_A8], rax
0x1801291e8  lea     rax, [rbp+57h+var_B0]
0x1801291ec  mov     qword ptr [rsp+110h+var_E8], rax
0x1801291f1  lea     rax, [rbp+57h+var_A8]
0x1801291f5  mov     qword ptr [rsp+110h+var_F0], rax
0x1801291fa  lea     rdx, byte_180207F0D
0x180129201  mov     rcx, r13
0x180129204  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180129209  xorps   xmm0, xmm0
0x18012920c  xor     eax, eax
0x18012920e  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x180129212  mov     [rbp+57h+var_48], rax
0x180129216  lea     rdx, [rbp+57h+var_58]; struct LampArrayAttributesDeviceReport *
0x18012921a  mov     rcx, rsi; this
0x18012921d  call    ?ReceiveLampArrayAttributesReport@HidLampArrayDevice@@AEAAJPEAULampArrayAttributesDeviceReport@@@Z; HidLampArrayDevice::ReceiveLampArrayAttributesReport(LampArrayAttributesDeviceReport *)
0x180129222  mov     ebx, eax
0x180129224  test    eax, eax
0x180129226  jns     short loc_180129232
0x180129228  mov     edx, 6Eh ; 'n'
0x18012922d  jmp     loc_1801296AD
0x180129232  movsxd  rcx, [rbp+57h+var_58]
0x180129236  mov     [rsi+220h], ecx
0x18012923c  mov     eax, [rbp+57h+var_58+4]
0x18012923f  mov     [rsi+224h], eax
0x180129245  mov     eax, [rbp+57h+var_58+8]
0x180129248  mov     [rsi+228h], eax
0x18012924e  mov     eax, [rbp+57h+var_58+0Ch]
0x180129251  mov     [rsi+22Ch], eax
0x180129257  mov     eax, dword ptr [rbp+57h+var_48+4]
0x18012925a  mov     [rsi+234h], eax
0x180129260  mov     eax, dword ptr [rbp+57h+var_48]
0x180129263  mov     [rsi+230h], eax
0x180129269  mov     eax, 24h ; '$'
0x18012926e  mul     rcx
0x180129271  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180129278  cmovb   rax, rbx
0x18012927c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180129283  mov     rcx, rax; unsigned __int64
0x180129286  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18012928b  mov     rcx, [rsi+238h]; void *
0x180129292  mov     [rsi+238h], rax
0x180129299  test    rcx, rcx
0x18012929c  jz      short loc_1801292A3
0x18012929e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801292a3  cmp     [rsi+238h], r15
0x1801292aa  jnz     short loc_1801292BB
0x1801292ac  mov     ebx, 8007000Eh
0x1801292b1  mov     edx, 7Ch ; '|'
0x1801292b6  jmp     loc_180129739
0x1801292bb  movsxd  rcx, dword ptr [rsi+220h]
0x1801292c2  mov     eax, 4
0x1801292c7  mul     rcx
0x1801292ca  cmovb   rax, rbx
0x1801292ce  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801292d5  mov     rcx, rax; unsigned __int64
0x1801292d8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1801292dd  mov     rcx, [rsi+240h]; void *
0x1801292e4  mov     [rsi+240h], rax
0x1801292eb  test    rcx, rcx
0x1801292ee  jz      short loc_1801292F5
0x1801292f0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801292f5  cmp     [rsi+240h], r15
0x1801292fc  jnz     short loc_18012930D
0x1801292fe  mov     ebx, 8007000Eh
0x180129303  mov     edx, 7Fh
0x180129308  jmp     loc_180129739
0x18012930d  mov     ebx, r15d
0x180129310  cmp     [rsi+220h], r15d
0x180129317  jle     loc_1801295D6
0x18012931d  mov     eax, cs:dword_180241248
0x180129323  cmp     eax, 5
0x180129326  jbe     short loc_18012937F
0x180129328  mov     eax, [rsi+220h]
0x18012932e  mov     [rbp+57h+var_A8], eax
0x180129331  mov     dword ptr [rbp+57h+var_B0], ebx
0x180129334  xor     edx, edx; length
0x180129336  mov     rcx, [rbp+57h+string]; string
0x18012933a  call    cs:__imp_WindowsGetStringRawBuffer
0x180129340  mov     [rbp+57h+var_90], rax
0x180129344  lea     rax, aSendingLampatt; "Sending LampAttributesRequest"
  ... truncated ...
```
