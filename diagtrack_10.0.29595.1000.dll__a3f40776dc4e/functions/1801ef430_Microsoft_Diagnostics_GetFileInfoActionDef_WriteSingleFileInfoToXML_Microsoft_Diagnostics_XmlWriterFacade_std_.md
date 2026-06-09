# Microsoft::Diagnostics::GetFileInfoActionDef::WriteSingleFileInfoToXML(Microsoft::Diagnostics::XmlWriterFacade &,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,bool,unsigned __int64,unsigned __int64,ulong,Microsoft::Diagnostics::GetFileInfoActionDef::FileInfoQueryState const &)

- ea: `0x1801ef430`
- end: `0x1801eff40`
- name: `?WriteSingleFileInfoToXML@GetFileInfoActionDef@Diagnostics@Microsoft@@CAXAEAVXmlWriterFacade@23@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_N_K3KAEBUFileInfoQueryState@123@@Z`
- size: `2832`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801ee3c0`
- `0x18032e768`

## callees

- `0x18001b010`
- `0x180025430`
- `0x180027c28`
- `0x18002ac10`
- `0x18002b318`
- `0x18002cae0`
- `0x18002df00`
- `0x180035088`
- `0x1800f7f64`
- `0x1801e206c`
- `0x1801ef430`
- `0x18020aac0`
- `0x180312b68`
- `0x180312c78`
- `0x18031321c`
- `0x18031b008`
- `0x18032dd5c`
- `0x18032e0b8`
- `0x18032e2fc`

## import_xrefs

- `ext-ms-win-appcompat-aepic-l1-1-0!PicFreeFileInfo` at `0x1801eff09`
- `ext-ms-win-appcompat-aepic-l1-1-0!PicFreeFileInfo` at `0x1801eff09`
- `ext-ms-win-appcompat-aepic-l1-1-0!PicRetrieveFileInfo` at `0x1801efb4f`
- `ext-ms-win-appcompat-aepic-l1-1-0!PicRetrieveFileInfo` at `0x1801efb72`
- `ext-ms-win-appcompat-aepic-l1-1-0!PicRetrieveFileInfo` at `0x1801efb4f`
- `ext-ms-win-appcompat-aepic-l1-1-0!PicRetrieveFileInfo` at `0x1801efb72`

## string_xrefs

- `0x1801ef588`: `Compressed`
- `0x1801ef8a3`: `ReparsePointTag`
- `0x1801ef867`: `ReparsePointQueryInfoError`
- `0x1801ef943`: `ReparsePointPrintName`
- `0x1801ef8f1`: `ReparsePointSubstituteName`
- `0x1801ef7d8`: `ReparsePoint`
- `0x1801ef78b`: `ReadOnly`
- `0x1801efcd0`: `CompanyName`
- `0x1801ef9e9`: `SecurityDescriptor`
- `0x1801ef994`: `ReparsePointSecurityDescriptor`
- `0x1801efab8`: `Temporary`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::Diagnostics::GetFileInfoActionDef::WriteSingleFileInfoToXML(
        __int64 a1,
        _QWORD *a2,
        char a3,
        _QWORD *a4,
        __int64 a5,
        int a6,
        _BYTE *a7)
{
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r8
  __int64 v19; // r8
  _QWORD *v20; // rax
  _QWORD *v21; // rax
  int v22; // r9d
  int v23; // r9d
  __int64 v24; // rdx
  _QWORD *v25; // rcx
  _QWORD *v26; // rcx
  __int64 v27; // rax
  void *v28; // rax
  _QWORD *v29; // rdx
  _BYTE v31[16]; // [rsp+30h] [rbp-C1h] BYREF
  __int128 v32; // [rsp+40h] [rbp-B1h] BYREF
  __int128 v33; // [rsp+50h] [rbp-A1h] BYREF
  _QWORD v34[2]; // [rsp+60h] [rbp-91h] BYREF
  _QWORD *v35; // [rsp+70h] [rbp-81h] BYREF
  __int64 v36; // [rsp+78h] [rbp-79h]
  int v37; // [rsp+80h] [rbp-71h] BYREF
  _QWORD v38[3]; // [rsp+88h] [rbp-69h] BYREF
  unsigned __int64 v39; // [rsp+A0h] [rbp-51h]
  _QWORD Src[6]; // [rsp+A8h] [rbp-49h] BYREF
  _QWORD v41[4]; // [rsp+D8h] [rbp-19h] BYREF

  v35 = a4;
  std::wstring::wstring(v38, *a2, a2[1]);
  *(_QWORD *)&v33 = L"FileSize";
  *((_QWORD *)&v33 + 1) = std::_WChar_traits<wchar_t>::length(L"FileSize");
  *(_QWORD *)&v32 = L"info";
  *((_QWORD *)&v32 + 1) = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v32,
    (unsigned int)&v33,
    (unsigned int)&v35,
    0);
  v10 = Microsoft::Diagnostics::Utils::Time::FileTimeToPrecise8601((STRSAFE_LPWSTR)Src);
  *(_QWORD *)&v32 = L"LastModifiedTime";
  *((_QWORD *)&v32 + 1) = std::_WChar_traits<wchar_t>::length(L"LastModifiedTime", v11, v12, v10);
  *(_QWORD *)&v33 = L"info";
  *((_QWORD *)&v33 + 1) = std::_WChar_traits<wchar_t>::length(L"info");
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<std::wstring>(a1, &v33, &v32, v13);
  std::wstring::_Tidy_deallocate(Src);
  v14 = std::_WChar_traits<wchar_t>::length(L"info");
  if ( a6 == -1 )
  {
    v31[0] = 1;
    *(_QWORD *)&v32 = L"InvalidFileAttributes";
    *((_QWORD *)&v32 + 1) = std::_WChar_traits<wchar_t>::length(L"InvalidFileAttributes", v14);
    *(_QWORD *)&v33 = L"info";
    *((_QWORD *)&v33 + 1) = v24;
  }
  else
  {
    v31[0] = (a6 & 0x20) != 0;
    *(_QWORD *)&v32 = L"Archive";
    *((_QWORD *)&v32 + 1) = std::_WChar_traits<wchar_t>::length(L"Archive", v14);
    *(_QWORD *)&v33 = L"info";
    *((_QWORD *)&v33 + 1) = v15;
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v33, &v32, v31);
    v31[0] = (a6 & 0x800) != 0;
    *(_QWORD *)&v32 = L"Compressed";
    *((_QWORD *)&v32 + 1) = std::_WChar_traits<wchar_t>::length(L"Compressed");
    *(_QWORD *)&v33 = L"info";
    *((_QWORD *)&v33 + 1) = std::_WChar_traits<wchar_t>::length(L"info");
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v33, &v32, v31);
    v31[0] = (a6 & 0x40) != 0;
    *(_QWORD *)&v32 = L"Device";
    *((_QWORD *)&v32 + 1) = std::_WChar_traits<wchar_t>::length(L"Device");
    *(_QWORD *)&v33 = L"info";
    *((_QWORD *)&v33 + 1) = std::_WChar_traits<wchar_t>::length(L"info");
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v33, &v32, v31);
    v31[0] = (a6 & 0x4000) != 0;
    *(_QWORD *)&v32 = L"Encrypted";
    *((_QWORD *)&v32 + 1) = std::_WChar_traits<wchar_t>::length(L"Encrypted");
    *(_QWORD *)&v33 = L"info";
    *((_QWORD *)&v33 + 1) = std::_WChar_traits<wchar_t>::length(L"info");
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v33, &v32, v31);
    v31[0] = (a6 & 2) != 0;
    *(_QWORD *)&v32 = L"Hidden";
    *((_QWORD *)&v32 + 1) = std::_WChar_traits<wchar_t>::length(L"Hidden");
    *(_QWORD *)&v33 = L"info";
    *((_QWORD *)&v33 + 1) = std::_WChar_traits<wchar_t>::length(L"info");
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v33, &v32, v31);
    v31[0] = (a6 & 0x80) != 0;
    *(_QWORD *)&v32 = L"Normal";
    *((_QWORD *)&v32 + 1) = std::_WChar_traits<wchar_t>::length(L"Normal");
    *(_QWORD *)&v33 = L"info";
    *((_QWORD *)&v33 + 1) = std::_WChar_traits<wchar_t>::length(L"info");
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v33, &v32, v31);
    v31[0] = (a6 & 0x2000) != 0;
    *(_QWORD *)&v32 = L"NotContentIndexed";
    *((_QWORD *)&v32 + 1) = std::_WChar_traits<wchar_t>::length(L"NotContentIndexed");
    *(_QWORD *)&v33 = L"info";
    *((_QWORD *)&v33 + 1) = std::_WChar_traits<wchar_t>::length(L"info");
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v33, &v32, v31);
    v31[0] = (a6 & 0x1000) != 0;
    *(_QWORD *)&v32 = L"Offline";
    *((_QWORD *)&v32 + 1) = std::_WChar_traits<wchar_t>::length(L"Offline");
    *(_QWORD *)&v33 = L"info";
    *((_QWORD *)&v33 + 1) = std::_WChar_traits<wchar_t>::length(L"info");
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v33, &v32, v31);
    v31[0] = a6 & 1;
    *(_QWORD *)&v32 = L"ReadOnly";
    *((_QWORD *)&v32 + 1) = std::_WChar_traits<wchar_t>::length(L"ReadOnly");
    *(_QWORD *)&v33 = L"info";
    *((_QWORD *)&v33 + 1) = std::_WChar_traits<wchar_t>::length(L"info");
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v33, &v32, v31);
    if ( (a6 & 0x400) != 0 )
    {
      v31[0] = 1;
      *(_QWORD *)&v32 = L"ReparsePoint";
      *((_QWORD *)&v32 + 1) = std::_WChar_traits<wchar_t>::length(L"ReparsePoint");
      *(_QWORD *)&v33 = L"info";
      *((_QWORD *)&v33 + 1) = std::_WChar_traits<wchar_t>::length(L"info");
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v33, &v32, v31);
      v37 = 0;
      std::wstring::wstring(Src);
      std::wstring::wstring(v41);
      v32 = *(_OWORD *)a2;
      LODWORD(v35) = Microsoft::Diagnostics::Utils::FileSystem::GetReparsePointInfo(&v32, &v37, Src, v41);
      v17 = std::_WChar_traits<wchar_t>::length(L"info", (unsigned int)v35);
      if ( (int)v16 >= 0 )
      {
        *(_QWORD *)&v32 = L"ReparsePointTag";
        *((_QWORD *)&v32 + 1) = std::_WChar_traits<wchar_t>::length(L"ReparsePointTag", v16, v17);
        *(_QWORD *)&v33 = L"info";
        *((_QWORD *)&v33 + 1) = v19;
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
          a1,
          (unsigned int)&v33,
          (unsigned int)&v32,
          (unsigned int)&v37,
          0);
        v20 = Src;
        if ( Src[3] > 7u )
          v20 = (_QWORD *)Src[0];
        v35 = v20;
        *(_QWORD *)&v32 = L"ReparsePointSubstituteName";
        *((_QWORD *)&v32 + 1) = std::_WChar_traits<wchar_t>::length(L"ReparsePointSubstituteName");
        *(_QWORD *)&v33 = L"info";
        *((_QWORD *)&v33 + 1) = std::_WChar_traits<wchar_t>::length(L"info");
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v33, &v32);
        v21 = v41;
        if ( v41[3] > 7u )
          v21 = (_QWORD *)v41[0];
        v35 = v21;
        *(_QWORD *)&v32 = L"ReparsePointPrintName";
        *((_QWORD *)&v32 + 1) = std::_WChar_traits<wchar_t>::length(L"ReparsePointPrintName");
        *(_QWORD *)&v33 = L"info";
        *((_QWORD *)&v33 + 1) = std::_WChar_traits<wchar_t>::length(L"info");
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v33, &v32);
        if ( a7[2] )
        {
          v33 = *(_OWORD *)a2;
          *(_QWORD *)&v32 = L"ReparsePointSecurityDescriptor";
          *((_QWORD *)&v32 + 1) = std::_WChar_traits<wchar_t>::length(L"ReparsePointSecurityDescriptor");
          LOBYTE(v22) = a3;
          Microsoft::Diagnostics::GetFileInfoActionDef::QuerySecurity(
            a1,
            (unsigned int)&v32,
            (unsigned int)&v33,
            v22,
            1);
        }
      }
      else
      {
        *(_QWORD *)&v32 = L"ReparsePointQueryInfoError";
        *((_QWORD *)&v32 + 1) = std::_WChar_traits<wchar_t>::length(L"ReparsePointQueryInfoError", v16, v17);
        *(_QWORD *)&v33 = L"info";
        *((_QWORD *)&v33 + 1) = v18;
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<long>(a1, &v33, &v32, &v35);
      }
      std::wstring::_Tidy_deallocate(v41);
      std::wstring::_Tidy_deallocate(Src);
    }
    if ( a7[2] )
    {
      v33 = *(_OWORD *)a2;
      *(_QWORD *)&v32 = L"SecurityDescriptor";
      *((_QWORD *)&v32 + 1) = std::_WChar_traits<wchar_t>::length(L"SecurityDescriptor");
      LOBYTE(v23) = a3;
      Microsoft::Diagnostics::GetFileInfoActionDef::QuerySecurity(a1, (unsigned int)&v32, (unsigned int)&v33, v23, 0);
    }
    v31[0] = (a6 & 0x200) != 0;
    *(_QWORD *)&v32 = L"SparseFile";
    *((_QWORD *)&v32 + 1) = std::_WChar_traits<wchar_t>::length(L"SparseFile");
    *(_QWORD *)&v33 = L"info";
    *((_QWORD *)&v33 + 1) = std::_WChar_traits<wchar_t>::length(L"info");
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v33, &v32, v31);
    v31[0] = (a6 & 4) != 0;
    *(_QWORD *)&v32 = L"System";
    *((_QWORD *)&v32 + 1) = std::_WChar_traits<wchar_t>::length(L"System");
    *(_QWORD *)&v33 = L"info";
    *((_QWORD *)&v33 + 1) = std::_WChar_traits<wchar_t>::length(L"info");
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v33, &v32, v31);
    v31[0] = BYTE1(a6) & 1;
    *(_QWORD *)&v32 = L"Temporary";
    *((_QWORD *)&v32 + 1) = std::_WChar_traits<wchar_t>::length(L"Temporary");
    *(_QWORD *)&v33 = L"info";
    *((_QWORD *)&v33 + 1) = std::_WChar_traits<wchar_t>::length(L"info");
  }
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v33, &v32, v31);
  if ( !a3 && !*a7 )
  {
    v34[0] = 0;
    v25 = v38;
    if ( v39 > 7 )
      v25 = (_QWORD *)v38[0];
    if ( (int)PicRetrieveFileInfo(v25, 16, v34) >= 0 )
      goto LABEL_25;
    v26 = v38;
    if ( v39 > 7 )
      v26 = (_QWORD *)v38[0];
    if ( (int)PicRetrieveFileInfo(v26, 0, v34) >= 0 )
    {
LABEL_25:
      v35 = v34;
      LOBYTE(v36) = 1;
      v29 = (_QWORD *)v34[0];
      if ( *(_QWORD *)(v34[0] + 72LL) )
      {
        *(_QWORD *)&v32 = L"Architecture";
        *((_QWORD *)&v32 + 1) = std::_WChar_traits<wchar_t>::length(L"Architecture");
        *(_QWORD *)&v33 = L"info";
        *((_QWORD *)&v33 + 1) = std::_WChar_traits<wchar_t>::length(L"info");
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v33, &v32);
        v29 = (_QWORD *)v34[0];
      }
      if ( v29[4] )
      {
        *(_QWORD *)&v32 = L"BinFileVersion";
        *((_QWORD *)&v32 + 1) = std::_WChar_traits<wchar_t>::length(L"BinFileVersion");
        *(_QWORD *)&v33 = L"info";
        *((_QWORD *)&v33 + 1) = std::_WChar_traits<wchar_t>::length(L"info");
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v33, &v32);
        v29 = (_QWORD *)v34[0];
      }
      if ( v29[7] )
      {
        *(_QWORD *)&v32 = L"CompanyName";
        *((_QWORD *)&v32 + 1) = std::_WChar_traits<wchar_t>::length(L"CompanyName");
        *(_QWORD *)&v33 = L"info";
        *((_QWORD *)&v33 + 1) = std::_WChar_traits<wchar_t>::length(L"info");
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v33, &v32);
        v29 = (_QWORD *)v34[0];
      }
      if ( v29[2] )
      {
        *(_QWORD *)&v32 = L"FileDescription";
        *((_QWORD *)&v32 + 1) = std::_WChar_traits<wchar_t>::length(L"FileDescription");
        *(_QWORD *)&v33 = L"info";
        *((_QWORD *)&v33 + 1) = std::_WChar_traits<wchar_t>::length(L"info");
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v33, &v32);
        v29 = (_QWORD *)v34[0];
      }
      if ( *v29 )
      {
        *(_QWORD *)&v32 = L"FileID";
        *((_QWORD *)&v32 + 1) = std::_WChar_traits<wchar_t>::length(L"FileID");
        *(_QWORD *)&v33 = L"info";
        *((_QWORD *)&v33 + 1) = std::_WChar_traits<wchar_t>::length(L"info");
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v33, &v32);
        v29 = (_QWORD *)v34[0];
      }
      if ( v29[3] )
      {
        *(_QWORD *)&v32 = L"FileVersion";
        *((_QWORD *)&v32 + 1) = std::_WChar_traits<wchar_t>::length(L"FileVersion");
        *(_QWORD *)&v33 = L"info";
        *((_QWORD *)&v33 + 1) = std::_WChar_traits<wchar_t>::length(L"info");
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v33, &v32);
        v29 = (_QWORD *)v34[0];
      }
      if ( v29[6] )
      {
        *(_QWORD *)&v32 = L"ProductName";
        *((_QWORD *)&v32 + 1) = std::_WChar_traits<wchar_t>::length(L"ProductName");
        *(_QWORD *)&v33 = L"info";
        *((_QWORD *)&v33 + 1) = std::_WChar_traits<wchar_t>::length(L"info");
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v33, &v32);
        v29 = (_QWORD *)v34[0];
      }
      if ( v29[8] )
      {
        *(_QWORD *)&v32 = L"ProductVersion";
        *((_QWORD *)&v32 + 1) = std::_WChar_traits<wchar_t>::length(L"ProductVersion");
        *(_QWORD *)&v33 = L"info";
        *((_QWORD *)&v33 + 1) = std::_WChar_traits<wchar_t>::length(L"info");
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v33, &v32);
        v29 = (_QWORD *)v34[0];
      }
      if ( v29[1] )
      {
        *(_QWORD *)&v32 = L"ProgramID";
        *((_QWORD *)&v32 + 1) = std::_WChar_traits<wchar_t>::length(L"ProgramID");
        *(_QWORD *)&v33 = L"info";
        *((_QWORD *)&v33 + 1) = std::_WChar_traits<wchar_t>::length(L"info");
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v33, &v32);
        v29 = (_QWORD *)v34[0];
      }
      if ( v29[5] )
      {
        *(_QWORD *)&v32 = L"VerLanguage";
        *((_QWORD *)&v32 + 1) = std::_WChar_traits<wchar_t>::length(L"VerLanguage");
        *(_QWORD *)&v33 = L"info";
        *((_QWORD *)&v33 + 1) = std::_WChar_traits<wchar_t>::length(L"info");
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v33, &v32);
        v29 = (_QWORD *)v34[0];
      }
      PicFreeFileInfo(v29);
    }
    else
    {
      Microsoft::Diagnostics::WideStringStream::WideStringStream((Microsoft::Diagnostics::WideStringStream *)Src);
      v27 = Microsoft::Diagnostics::WideStringStream::operator<<(Src);
      WORD1(v32) = 0;
      LOBYTE(v35) = 1;
      *(_WORD *)((char *)&v35 + 1) = BYTE1(v32);
      BYTE3(v35) = 0;
      HIDWORD(v35) = 2097153;
      v36 = 0;
      v28 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v27, &v35);
      Microsoft::Diagnostics::WideStringStream::operator<<(v28);
      *(_QWORD *)&v32 = L"Error";
      *((_QWORD *)&v32 + 1) = std::_WChar_traits<wchar_t>::length(L"Error");
      *(_QWORD *)&v33 = L"info";
      *((_QWORD *)&v33 + 1) = std::_WChar_traits<wchar_t>::length(L"info");
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<std::wstring>(a1, &v33, &v32, Src);
      std::wstring::_Tidy_deallocate(Src);
    }
  }
  return std::wstring::_Tidy_deallocate(v38);
}

```

## disassembly

```asm
0x1801ef430  mov     [rsp-8+arg_10], rbx
0x1801ef435  push    rbp
0x1801ef436  push    rsi
0x1801ef437  push    rdi
0x1801ef438  push    r12
0x1801ef43a  push    r13
0x1801ef43c  push    r14
0x1801ef43e  push    r15
0x1801ef440  lea     rbp, [rsp-0Fh]
0x1801ef445  sub     rsp, 100h
0x1801ef44c  mov     rax, cs:__security_cookie
0x1801ef453  xor     rax, rsp
0x1801ef456  mov     [rbp+3Fh+var_38], rax
0x1801ef45a  mov     r15b, r8b
0x1801ef45d  mov     r14, rdx
0x1801ef460  mov     rdi, rcx
0x1801ef463  mov     [rsp+130h+var_C0], r9
0x1801ef468  mov     rbx, [rbp+3Fh+arg_20]
0x1801ef46c  mov     r8, [rdx+8]
0x1801ef470  mov     rdx, [rdx]
0x1801ef473  lea     rcx, [rbp+3Fh+var_A8]
0x1801ef477  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W_K@Z; std::wstring::wstring(wchar_t const * const,unsigned __int64)
0x1801ef47c  nop
0x1801ef47d  lea     rcx, aFilesize; "FileSize"
0x1801ef484  mov     qword ptr [rsp+130h+var_E0], rcx
0x1801ef489  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef48e  mov     qword ptr [rsp+130h+var_E0+8], rax
0x1801ef493  lea     r13, aInfo_0; "info"
0x1801ef49a  mov     qword ptr [rsp+130h+var_F0], r13
0x1801ef49f  mov     rcx, r13
0x1801ef4a2  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef4a7  mov     qword ptr [rsp+130h+var_F0+8], rax
0x1801ef4ac  mov     [rsp+130h+var_110], 0
0x1801ef4b1  lea     r9, [rsp+130h+var_C0]
0x1801ef4b6  lea     r8, [rsp+130h+var_E0]
0x1801ef4bb  lea     rdx, [rsp+130h+var_F0]
0x1801ef4c0  mov     rcx, rdi
0x1801ef4c3  call    ??$WriteInfoElement@_K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_K_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(std::wstring_view,std::wstring_view,unsigned __int64 const &,bool)
0x1801ef4c8  mov     rdx, rbx
0x1801ef4cb  lea     rcx, [rbp+3Fh+Src]; pszDest
0x1801ef4cf  call    ?FileTimeToPrecise8601@Time@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@Z; Microsoft::Diagnostics::Utils::Time::FileTimeToPrecise8601(unsigned __int64)
0x1801ef4d4  mov     r9, rax
0x1801ef4d7  lea     rcx, aLastmodifiedti; "LastModifiedTime"
0x1801ef4de  mov     qword ptr [rsp+130h+var_F0], rcx
0x1801ef4e3  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef4e8  mov     qword ptr [rsp+130h+var_F0+8], rax
0x1801ef4ed  mov     qword ptr [rsp+130h+var_E0], r13
0x1801ef4f2  mov     rcx, r13
0x1801ef4f5  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef4fa  mov     qword ptr [rsp+130h+var_E0+8], rax
0x1801ef4ff  lea     r8, [rsp+130h+var_F0]
0x1801ef504  lea     rdx, [rsp+130h+var_E0]
0x1801ef509  mov     rcx, rdi
0x1801ef50c  call    ??$WriteInfoElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<std::wstring>(std::wstring_view,std::wstring_view,std::wstring const &,bool)
0x1801ef511  nop
0x1801ef512  lea     rcx, [rbp+3Fh+Src]
0x1801ef516  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801ef51b  mov     rcx, r13
0x1801ef51e  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef523  mov     rdx, rax
0x1801ef526  mov     r12, [rbp+3Fh+arg_30]
0x1801ef52a  mov     esi, [rbp+3Fh+arg_28]
0x1801ef52d  mov     ebx, 1
0x1801ef532  cmp     esi, 0FFFFFFFFh
0x1801ef535  jz      loc_1801EFAE2
0x1801ef53b  mov     ecx, esi
0x1801ef53d  shr     ecx, 5
0x1801ef540  and     cl, bl
0x1801ef542  mov     [rsp+130h+var_100], cl
0x1801ef546  lea     rcx, aArchive; "Archive"
0x1801ef54d  mov     qword ptr [rsp+130h+var_F0], rcx
0x1801ef552  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef557  mov     qword ptr [rsp+130h+var_F0+8], rax
0x1801ef55c  mov     qword ptr [rsp+130h+var_E0], r13
0x1801ef561  mov     qword ptr [rsp+130h+var_E0+8], rdx
0x1801ef566  lea     r9, [rsp+130h+var_100]
0x1801ef56b  lea     r8, [rsp+130h+var_F0]
0x1801ef570  lea     rdx, [rsp+130h+var_E0]
0x1801ef575  mov     rcx, rdi
0x1801ef578  call    ??$WriteInfoElement@_N@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_N_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(std::wstring_view,std::wstring_view,bool const &,bool)
0x1801ef57d  mov     eax, esi
0x1801ef57f  shr     eax, 0Bh
0x1801ef582  and     al, bl
0x1801ef584  mov     [rsp+130h+var_100], al
0x1801ef588  lea     rcx, aCompressed; "Compressed"
0x1801ef58f  mov     qword ptr [rsp+130h+var_F0], rcx
0x1801ef594  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef599  mov     qword ptr [rsp+130h+var_F0+8], rax
0x1801ef59e  mov     qword ptr [rsp+130h+var_E0], r13
0x1801ef5a3  mov     rcx, r13
0x1801ef5a6  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef5ab  mov     qword ptr [rsp+130h+var_E0+8], rax
0x1801ef5b0  lea     r9, [rsp+130h+var_100]
0x1801ef5b5  lea     r8, [rsp+130h+var_F0]
0x1801ef5ba  lea     rdx, [rsp+130h+var_E0]
0x1801ef5bf  mov     rcx, rdi
0x1801ef5c2  call    ??$WriteInfoElement@_N@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_N_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(std::wstring_view,std::wstring_view,bool const &,bool)
0x1801ef5c7  mov     eax, esi
0x1801ef5c9  shr     eax, 6
0x1801ef5cc  and     al, bl
0x1801ef5ce  mov     [rsp+130h+var_100], al
0x1801ef5d2  lea     rcx, aDevice_0; "Device"
0x1801ef5d9  mov     qword ptr [rsp+130h+var_F0], rcx
0x1801ef5de  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef5e3  mov     qword ptr [rsp+130h+var_F0+8], rax
0x1801ef5e8  mov     qword ptr [rsp+130h+var_E0], r13
0x1801ef5ed  mov     rcx, r13
0x1801ef5f0  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef5f5  mov     qword ptr [rsp+130h+var_E0+8], rax
0x1801ef5fa  lea     r9, [rsp+130h+var_100]
0x1801ef5ff  lea     r8, [rsp+130h+var_F0]
0x1801ef604  lea     rdx, [rsp+130h+var_E0]
0x1801ef609  mov     rcx, rdi
0x1801ef60c  call    ??$WriteInfoElement@_N@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_N_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(std::wstring_view,std::wstring_view,bool const &,bool)
0x1801ef611  mov     eax, esi
0x1801ef613  shr     eax, 0Eh
0x1801ef616  and     al, bl
0x1801ef618  mov     [rsp+130h+var_100], al
0x1801ef61c  lea     rcx, aEncrypted; "Encrypted"
0x1801ef623  mov     qword ptr [rsp+130h+var_F0], rcx
0x1801ef628  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef62d  mov     qword ptr [rsp+130h+var_F0+8], rax
0x1801ef632  mov     qword ptr [rsp+130h+var_E0], r13
0x1801ef637  mov     rcx, r13
0x1801ef63a  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef63f  mov     qword ptr [rsp+130h+var_E0+8], rax
0x1801ef644  lea     r9, [rsp+130h+var_100]
0x1801ef649  lea     r8, [rsp+130h+var_F0]
0x1801ef64e  lea     rdx, [rsp+130h+var_E0]
0x1801ef653  mov     rcx, rdi
0x1801ef656  call    ??$WriteInfoElement@_N@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_N_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(std::wstring_view,std::wstring_view,bool const &,bool)
0x1801ef65b  mov     eax, esi
0x1801ef65d  shr     eax, 1
0x1801ef65f  and     al, bl
0x1801ef661  mov     [rsp+130h+var_100], al
0x1801ef665  lea     rcx, aHidden; "Hidden"
0x1801ef66c  mov     qword ptr [rsp+130h+var_F0], rcx
0x1801ef671  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef676  mov     qword ptr [rsp+130h+var_F0+8], rax
0x1801ef67b  mov     qword ptr [rsp+130h+var_E0], r13
0x1801ef680  mov     rcx, r13
0x1801ef683  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef688  mov     qword ptr [rsp+130h+var_E0+8], rax
0x1801ef68d  lea     r9, [rsp+130h+var_100]
0x1801ef692  lea     r8, [rsp+130h+var_F0]
0x1801ef697  lea     rdx, [rsp+130h+var_E0]
0x1801ef69c  mov     rcx, rdi
0x1801ef69f  call    ??$WriteInfoElement@_N@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_N_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(std::wstring_view,std::wstring_view,bool const &,bool)
0x1801ef6a4  mov     eax, esi
0x1801ef6a6  shr     eax, 7
0x1801ef6a9  and     al, bl
0x1801ef6ab  mov     [rsp+130h+var_100], al
0x1801ef6af  lea     rcx, aNormal; "Normal"
0x1801ef6b6  mov     qword ptr [rsp+130h+var_F0], rcx
0x1801ef6bb  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef6c0  mov     qword ptr [rsp+130h+var_F0+8], rax
0x1801ef6c5  mov     qword ptr [rsp+130h+var_E0], r13
0x1801ef6ca  mov     rcx, r13
0x1801ef6cd  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef6d2  mov     qword ptr [rsp+130h+var_E0+8], rax
0x1801ef6d7  lea     r9, [rsp+130h+var_100]
0x1801ef6dc  lea     r8, [rsp+130h+var_F0]
0x1801ef6e1  lea     rdx, [rsp+130h+var_E0]
0x1801ef6e6  mov     rcx, rdi
0x1801ef6e9  call    ??$WriteInfoElement@_N@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_N_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(std::wstring_view,std::wstring_view,bool const &,bool)
0x1801ef6ee  mov     eax, esi
0x1801ef6f0  shr     eax, 0Dh
0x1801ef6f3  and     al, bl
0x1801ef6f5  mov     [rsp+130h+var_100], al
0x1801ef6f9  lea     rcx, aNotcontentinde; "NotContentIndexed"
0x1801ef700  mov     qword ptr [rsp+130h+var_F0], rcx
0x1801ef705  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef70a  mov     qword ptr [rsp+130h+var_F0+8], rax
0x1801ef70f  mov     qword ptr [rsp+130h+var_E0], r13
0x1801ef714  mov     rcx, r13
0x1801ef717  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef71c  mov     qword ptr [rsp+130h+var_E0+8], rax
0x1801ef721  lea     r9, [rsp+130h+var_100]
0x1801ef726  lea     r8, [rsp+130h+var_F0]
0x1801ef72b  lea     rdx, [rsp+130h+var_E0]
0x1801ef730  mov     rcx, rdi
0x1801ef733  call    ??$WriteInfoElement@_N@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_N_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(std::wstring_view,std::wstring_view,bool const &,bool)
0x1801ef738  mov     eax, esi
0x1801ef73a  shr     eax, 0Ch
0x1801ef73d  and     al, bl
0x1801ef73f  mov     [rsp+130h+var_100], al
0x1801ef743  lea     rcx, aOffline; "Offline"
0x1801ef74a  mov     qword ptr [rsp+130h+var_F0], rcx
0x1801ef74f  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef754  mov     qword ptr [rsp+130h+var_F0+8], rax
0x1801ef759  mov     qword ptr [rsp+130h+var_E0], r13
0x1801ef75e  mov     rcx, r13
0x1801ef761  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef766  mov     qword ptr [rsp+130h+var_E0+8], rax
0x1801ef76b  lea     r9, [rsp+130h+var_100]
0x1801ef770  lea     r8, [rsp+130h+var_F0]
0x1801ef775  lea     rdx, [rsp+130h+var_E0]
0x1801ef77a  mov     rcx, rdi
0x1801ef77d  call    ??$WriteInfoElement@_N@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_N_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(std::wstring_view,std::wstring_view,bool const &,bool)
0x1801ef782  mov     al, sil
0x1801ef785  and     al, bl
0x1801ef787  mov     [rsp+130h+var_100], al
0x1801ef78b  lea     rcx, aReadonly; "ReadOnly"
0x1801ef792  mov     qword ptr [rsp+130h+var_F0], rcx
0x1801ef797  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef79c  mov     qword ptr [rsp+130h+var_F0+8], rax
0x1801ef7a1  mov     qword ptr [rsp+130h+var_E0], r13
0x1801ef7a6  mov     rcx, r13
0x1801ef7a9  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef7ae  mov     qword ptr [rsp+130h+var_E0+8], rax
0x1801ef7b3  lea     r9, [rsp+130h+var_100]
0x1801ef7b8  lea     r8, [rsp+130h+var_F0]
0x1801ef7bd  lea     rdx, [rsp+130h+var_E0]
0x1801ef7c2  mov     rcx, rdi
0x1801ef7c5  call    ??$WriteInfoElement@_N@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_N_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(std::wstring_view,std::wstring_view,bool const &,bool)
0x1801ef7ca  bt      esi, 0Ah
0x1801ef7ce  jnb     loc_1801EF9D7
0x1801ef7d4  mov     [rsp+130h+var_100], bl
0x1801ef7d8  lea     rcx, aReparsepoint; "ReparsePoint"
0x1801ef7df  mov     qword ptr [rsp+130h+var_F0], rcx
0x1801ef7e4  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef7e9  mov     qword ptr [rsp+130h+var_F0+8], rax
0x1801ef7ee  mov     qword ptr [rsp+130h+var_E0], r13
0x1801ef7f3  mov     rcx, r13
0x1801ef7f6  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef7fb  mov     qword ptr [rsp+130h+var_E0+8], rax
0x1801ef800  lea     r9, [rsp+130h+var_100]
0x1801ef805  lea     r8, [rsp+130h+var_F0]
0x1801ef80a  lea     rdx, [rsp+130h+var_E0]
0x1801ef80f  mov     rcx, rdi
0x1801ef812  call    ??$WriteInfoElement@_N@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_N_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(std::wstring_view,std::wstring_view,bool const &,bool)
0x1801ef817  mov     [rbp+3Fh+var_B0], 0
0x1801ef81e  lea     rcx, [rbp+3Fh+Src]; void *
0x1801ef822  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1801ef827  nop
0x1801ef828  lea     rcx, [rbp+3Fh+var_58]; void *
0x1801ef82c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1801ef831  nop
0x1801ef832  movaps  xmm0, xmmword ptr [r14]
0x1801ef836  movdqa  [rsp+130h+var_F0], xmm0
0x1801ef83c  lea     r9, [rbp+3Fh+var_58]
0x1801ef840  lea     r8, [rbp+3Fh+Src]
0x1801ef844  lea     rdx, [rbp+3Fh+var_B0]
0x1801ef848  lea     rcx, [rsp+130h+var_F0]
0x1801ef84d  call    ?GetReparsePointInfo@FileSystem@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAKAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@6@2@Z; Microsoft::Diagnostics::Utils::FileSystem::GetReparsePointInfo(std::wstring_view,ulong &,std::wstring &,std::wstring &)
0x1801ef852  mov     edx, eax
0x1801ef854  mov     dword ptr [rsp+130h+var_C0], eax
0x1801ef858  mov     rcx, r13
0x1801ef85b  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef860  mov     r8, rax
0x1801ef863  test    edx, edx
0x1801ef865  jns     short loc_1801EF8A3
0x1801ef867  lea     rcx, aReparsepointqu; "ReparsePointQueryInfoError"
0x1801ef86e  mov     qword ptr [rsp+130h+var_F0], rcx
0x1801ef873  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef878  mov     qword ptr [rsp+130h+var_F0+8], rax
0x1801ef87d  mov     qword ptr [rsp+130h+var_E0], r13
0x1801ef882  mov     qword ptr [rsp+130h+var_E0+8], r8
0x1801ef887  lea     r9, [rsp+130h+var_C0]
0x1801ef88c  lea     r8, [rsp+130h+var_F0]
0x1801ef891  lea     rdx, [rsp+130h+var_E0]
0x1801ef896  mov     rcx, rdi
0x1801ef899  call    ??$WriteInfoElement@J@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBJ_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<long>(std::wstring_view,std::wstring_view,long const &,bool)
0x1801ef89e  jmp     loc_1801EF9C4
0x1801ef8a3  lea     rcx, aReparsepointta; "ReparsePointTag"
0x1801ef8aa  mov     qword ptr [rsp+130h+var_F0], rcx
0x1801ef8af  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef8b4  mov     qword ptr [rsp+130h+var_F0+8], rax
0x1801ef8b9  mov     qword ptr [rsp+130h+var_E0], r13
0x1801ef8be  mov     qword ptr [rsp+130h+var_E0+8], r8
0x1801ef8c3  mov     [rsp+130h+var_110], 0
0x1801ef8c8  lea     r9, [rbp+3Fh+var_B0]
0x1801ef8cc  lea     r8, [rsp+130h+var_F0]
0x1801ef8d1  lea     rdx, [rsp+130h+var_E0]
0x1801ef8d6  mov     rcx, rdi
0x1801ef8d9  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x1801ef8de  lea     rax, [rbp+3Fh+Src]
0x1801ef8e2  cmp     [rbp+3Fh+var_70], 7
0x1801ef8e7  cmova   rax, [rbp+3Fh+Src]
0x1801ef8ec  mov     [rsp+130h+var_C0], rax
0x1801ef8f1  lea     rcx, aReparsepointsu; "ReparsePointSubstituteName"
0x1801ef8f8  mov     qword ptr [rsp+130h+var_F0], rcx
0x1801ef8fd  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef902  mov     qword ptr [rsp+130h+var_F0+8], rax
0x1801ef907  mov     qword ptr [rsp+130h+var_E0], r13
0x1801ef90c  mov     rcx, r13
0x1801ef90f  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef914  mov     qword ptr [rsp+130h+var_E0+8], rax
0x1801ef919  lea     r9, [rsp+130h+var_C0]
0x1801ef91e  lea     r8, [rsp+130h+var_F0]
0x1801ef923  lea     rdx, [rsp+130h+var_E0]
0x1801ef928  mov     rcx, rdi
0x1801ef92b  call    ??$WriteInfoElement@PEA_W@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBQEA_W_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(std::wstring_view,std::wstring_view,wchar_t * const &,bool)
0x1801ef930  lea     rax, [rbp+3Fh+var_58]
0x1801ef934  cmp     [rbp+3Fh+var_40], 7
0x1801ef939  cmova   rax, [rbp+3Fh+var_58]
0x1801ef93e  mov     [rsp+130h+var_C0], rax
0x1801ef943  lea     rcx, aReparsepointpr; "ReparsePointPrintName"
0x1801ef94a  mov     qword ptr [rsp+130h+var_F0], rcx
0x1801ef94f  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
  ... truncated ...
```
