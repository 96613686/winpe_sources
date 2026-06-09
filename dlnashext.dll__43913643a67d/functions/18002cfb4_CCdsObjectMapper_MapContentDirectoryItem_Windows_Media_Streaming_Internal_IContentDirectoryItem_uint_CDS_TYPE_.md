# CCdsObjectMapper::MapContentDirectoryItem(Windows::Media::Streaming::Internal::IContentDirectoryItem *,uint,_CDS_TYPE,IPropertyStore * *)

- ea: `0x18002cfb4`
- end: `0x18002d494`
- name: `?MapContentDirectoryItem@CCdsObjectMapper@@QEAAJPEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@IW4_CDS_TYPE@@PEAPEAUIPropertyStore@@@Z`
- size: `1248`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180027260`

## callees

- `0x180001710`
- `0x1800097c0`
- `0x18000ae38`
- `0x18000cfd4`
- `0x18000d990`
- `0x18000f740`
- `0x180011930`
- `0x180022b74`
- `0x18002c3bc`
- `0x18002cc70`
- `0x18002cfb4`
- `0x18002d49c`
- `0x18002f430`
- `0x18002fb7c`
- `0x18002fe28`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d414`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d414`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002d2d7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002d2d7`
- `PROPSYS!InitPropVariantFromStringAsVector` at `0x18002d3ec`
- `PROPSYS!InitPropVariantFromStringAsVector` at `0x18002d3ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002d17c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002d2be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002d309`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002d339`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002d3df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002d17c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002d2be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002d309`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002d339`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002d3df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d281`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d281`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18002d2a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18002d2a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18002d250`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18002d250`

## pseudocode

```c
__int64 __fastcall CCdsObjectMapper::MapContentDirectoryItem(
        __int64 a1,
        __int64 (__fastcall ***a2)(__int64, GUID *, __int64 **),
        __int64 a3,
        unsigned int a4,
        void **a5)
{
  __int64 (__fastcall **v5)(__int64, GUID *, __int64 **); // rax
  __int64 (__fastcall *v8)(__int64, GUID *, __int64 **); // rbx
  __int64 v9; // rcx
  int v10; // esi
  int (__fastcall *v11)(__int64, __int64 *); // rbx
  __int64 v12; // rdi
  int (__fastcall *v13)(__int64, _QWORD, __int64 *); // rbx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64 *); // rbx
  struct Windows::Media::Streaming::Internal::IProtocolInfo *v16; // rdi
  __int64 (__fastcall *v17)(struct Windows::Media::Streaming::Internal::IProtocolInfo *, HSTRING *); // rbx
  void *v18; // rbx
  PCWSTR StringRawBuffer; // rax
  void *v20; // rcx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, struct Windows::Media::Streaming::Internal::IProtocolInfo **); // rbx
  void *v23; // rcx
  const struct Windows::Internal::String *v24; // rax
  struct IPropertyStore *v25; // r8
  CCdsObjectMapper *v26; // rcx
  CCdsObjectMapper *v27; // rcx
  const WCHAR *v28; // rax
  PCWSTR v29; // rax
  void *v30; // rcx
  const unsigned __int16 *v31; // rax
  CCdsObjectMapper *v32; // rcx
  CCdsObjectMapper *v33; // rcx
  struct Windows::Media::Streaming::Internal::IProtocolInfo *v34; // rdi
  int (__fastcall *v35)(struct Windows::Media::Streaming::Internal::IProtocolInfo *, HSTRING *); // rbx
  HSTRING v36; // rdi
  int (__fastcall *v37)(HSTRING, _QWORD, HSTRING *); // rbx
  _QWORD *v38; // rax
  const WCHAR *v39; // rax
  HSTRING v41; // [rsp+30h] [rbp-51h] BYREF
  struct Windows::Media::Streaming::Internal::IProtocolInfo *v42; // [rsp+38h] [rbp-49h] BYREF
  __int64 v43; // [rsp+40h] [rbp-41h] BYREF
  HSTRING v44; // [rsp+48h] [rbp-39h] BYREF
  HSTRING string; // [rsp+50h] [rbp-31h] BYREF
  HSTRING v46; // [rsp+58h] [rbp-29h] BYREF
  __int64 v47; // [rsp+60h] [rbp-21h] BYREF
  __int64 v48; // [rsp+68h] [rbp-19h] BYREF
  __int64 *v49; // [rsp+70h] [rbp-11h] BYREF
  PROPVARIANT ppropvar; // [rsp+78h] [rbp-9h] BYREF

  v5 = *a2;
  v49 = 0;
  v8 = *v5;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v49);
  v10 = v8((__int64)a2, &GUID_7855c6f6_b22c_4c2d_83dd_c45004979937, &v49);
  if ( v10 >= 0 )
    v10 = CCdsObjectMapper::MapContentDirectoryObject(v9, v49, a4, a5);
  v48 = 0;
  v43 = 0;
  if ( v10 >= 0 )
  {
    v11 = (int (__fastcall *)(__int64, __int64 *))(*a2)[6];
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v48);
    if ( v11((__int64)a2, &v48) >= 0 )
    {
      v12 = v48;
      v13 = *(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v48 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v43);
      if ( v13(v12, 0, &v43) >= 0 )
      {
        v14 = v43;
        v47 = 0;
        v46 = 0;
        v15 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v43 + 176LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(&v47);
        v10 = v15(v14, &v47);
        if ( v10 >= 0 )
        {
          v42 = 0;
          v10 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *>>::As<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>(
                  &v47,
                  &v42);
          if ( v10 >= 0 )
          {
            v16 = v42;
            v17 = *(__int64 (__fastcall **)(struct Windows::Media::Streaming::Internal::IProtocolInfo *, HSTRING *))(*(_QWORD *)v42 + 48LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(&v46);
            v10 = v17(v16, &v46);
            if ( v10 >= 0 )
            {
              v18 = *a5;
              v44 = v46;
              if ( v46 )
                (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v46 + 8LL))(v46);
              v10 = WalkItemProperties(&v44, v18);
            }
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(&v42);
        }
        string = 0;
        if ( v10 >= 0 )
        {
          v10 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v43 + 48LL))(v43, &string);
          if ( v10 >= 0 )
          {
            memset(&ppropvar, 0, sizeof(ppropvar));
            ppropvar.vt = 31;
            StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
            v20 = *a5;
            ppropvar.hVal.QuadPart = (LONGLONG)StringRawBuffer;
            v10 = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v20 + 48LL))(
                    v20,
                    &PKEY_ItemUrl,
                    &ppropvar);
            if ( v10 >= 0 )
            {
              v21 = v43;
              v42 = 0;
              v22 = *(__int64 (__fastcall **)(__int64, struct Windows::Media::Streaming::Internal::IProtocolInfo **))(*(_QWORD *)v43 + 64LL);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(&v42);
              v10 = v22(v21, &v42);
              if ( v10 >= 0 )
              {
                if ( !CCDSResultsParser::IsProtocolInfoProtected(v42)
                  || (v23 = *a5,
                      memset(&ppropvar, 0, sizeof(ppropvar)),
                      ppropvar.iVal = -1,
                      ppropvar.vt = 11,
                      v10 = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v23 + 48LL))(
                              v23,
                              &PKEY_DRM_IsProtected,
                              &ppropvar),
                      v10 >= 0) )
                {
                  v41 = 0;
                  v10 = (*(__int64 (__fastcall **)(struct Windows::Media::Streaming::Internal::IProtocolInfo *, HSTRING *))(*(_QWORD *)v42 + 88LL))(
                          v42,
                          &v41);
                  if ( v10 >= 0
                    && !WindowsIsStringEmpty(v41)
                    && (v24 = (const struct Windows::Internal::String *)Windows::Internal::StringReference::StringReference(
                                                                          (HSTRING *)&ppropvar,
                                                                          L"*",
                                                                          1u),
                        (unsigned int)Windows::Internal::String::CompareOrdinal((Windows::Internal::String *)&v41, v24))
                    || (WindowsDeleteString(v41),
                        v25 = (struct IPropertyStore *)*a5,
                        v41 = 0,
                        v10 = CCdsObjectMapper::_ComputeMimeType(v26, (const unsigned __int16 *)string, v25, &v41),
                        v10 >= 0) )
                  {
                    if ( WindowsGetStringLen(v41) < 0x1C
                      || (v28 = WindowsGetStringRawBuffer(v41, 0),
                          CompareStringOrdinal(v28, 28, L"application/vnd.ms-playtoapp", 28, 1) != 2) )
                    {
                      v10 = CCdsObjectMapper::_RemoveParametersFromMimeType(
                              v27,
                              (struct Windows::Internal::String *)&v41);
                    }
                    if ( v10 >= 0 )
                    {
                      memset(&ppropvar, 0, sizeof(ppropvar));
                      ppropvar.vt = 31;
                      v29 = WindowsGetStringRawBuffer(v41, 0);
                      v30 = *a5;
                      ppropvar.hVal.QuadPart = (LONGLONG)v29;
                      v10 = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v30 + 48LL))(
                              v30,
                              &PKEY_MIMEType,
                              &ppropvar);
                      if ( v10 >= 0 )
                      {
                        v31 = WindowsGetStringRawBuffer(v41, 0);
                        v10 = CCdsObjectMapper::_SetFileExtensionProperty(v32, (struct IPropertyStore *)*a5, v31);
                      }
                    }
                  }
                  Windows::Internal::String::~String((Windows::Internal::String *)&v41);
                  if ( v10 >= 0 )
                  {
                    CCdsObjectMapper::_SetFileNameProperty(v33, (struct IPropertyStore *)*a5);
                    v34 = v42;
                    v41 = 0;
                    v35 = *(int (__fastcall **)(struct Windows::Media::Streaming::Internal::IProtocolInfo *, HSTRING *))(*(_QWORD *)v42 + 120LL);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(&v41);
                    if ( v35(v34, &v41) >= 0 )
                    {
                      v36 = v41;
                      v44 = 0;
                      v37 = *(int (__fastcall **)(HSTRING, _QWORD, HSTRING *))(*(_QWORD *)v41 + 48LL);
                      v38 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                                        (HSTRING *)&ppropvar,
                                        L"DLNA.ORG_PN",
                                        0xBu);
                      if ( v37(v36, *v38, &v44) >= 0 )
                      {
                        memset(&ppropvar, 0, sizeof(ppropvar));
                        v39 = WindowsGetStringRawBuffer(v44, 0);
                        if ( InitPropVariantFromStringAsVector(v39, &ppropvar) >= 0 )
                        {
                          (*(void (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)*a5 + 48LL))(
                            *a5,
                            &PKEY_Media_DlnaProfileID,
                            &ppropvar);
                          PropVariantClear(&ppropvar);
                        }
                      }
                      Windows::Internal::String::~String((Windows::Internal::String *)&v44);
                    }
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(&v41);
                  }
                }
              }
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(&v42);
            }
          }
        }
        Windows::Internal::String::~String((Windows::Internal::String *)&string);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(&v46);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(&v47);
      }
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v43);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v48);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v49);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002cfb4  mov     [rsp-8+arg_0], rbx
0x18002cfb9  push    rbp
0x18002cfba  push    rsi
0x18002cfbb  push    rdi
0x18002cfbc  push    r12
0x18002cfbe  push    r13
0x18002cfc0  push    r14
0x18002cfc2  push    r15
0x18002cfc4  lea     rbp, [rsp-1Fh]
0x18002cfc9  sub     rsp, 0A0h
0x18002cfd0  mov     rax, cs:__security_cookie
0x18002cfd7  xor     rax, rsp
0x18002cfda  mov     [rbp+4Fh+var_38], rax
0x18002cfde  mov     rax, [rdx]
0x18002cfe1  lea     rcx, [rbp+4Fh+var_60]
0x18002cfe5  mov     r14, [rbp+4Fh+arg_20]
0x18002cfe9  xor     r12d, r12d
0x18002cfec  mov     r15d, r9d
0x18002cfef  mov     [rbp+4Fh+var_60], r12
0x18002cff3  mov     rdi, rdx
0x18002cff6  mov     rbx, [rax]
0x18002cff9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18002cffe  lea     r8, [rbp+4Fh+var_60]
0x18002d002  mov     rcx, rdi
0x18002d005  lea     rdx, _GUID_7855c6f6_b22c_4c2d_83dd_c45004979937
0x18002d00c  mov     rax, rbx
0x18002d00f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d014  mov     esi, eax
0x18002d016  test    eax, eax
0x18002d018  js      short loc_18002D02B
0x18002d01a  mov     rdx, [rbp+4Fh+var_60]
0x18002d01e  mov     r9, r14
0x18002d021  mov     r8d, r15d
0x18002d024  call    ?MapContentDirectoryObject@CCdsObjectMapper@@QEAAJPEAUIContentDirectoryObject@Internal@Streaming@Media@Windows@@W4_CDS_TYPE@@PEAPEAUIPropertyStore@@@Z; CCdsObjectMapper::MapContentDirectoryObject(Windows::Media::Streaming::Internal::IContentDirectoryObject *,_CDS_TYPE,IPropertyStore * *)
0x18002d029  mov     esi, eax
0x18002d02b  mov     [rbp+4Fh+var_68], r12
0x18002d02f  mov     [rbp+4Fh+var_90], r12
0x18002d033  test    esi, esi
0x18002d035  js      loc_18002D450
0x18002d03b  mov     rax, [rdi]
0x18002d03e  lea     rcx, [rbp+4Fh+var_68]
0x18002d042  mov     rbx, [rax+30h]
0x18002d046  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18002d04b  lea     rdx, [rbp+4Fh+var_68]
0x18002d04f  mov     rcx, rdi
0x18002d052  mov     rax, rbx
0x18002d055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d05a  test    eax, eax
0x18002d05c  js      loc_18002D450
0x18002d062  mov     rdi, [rbp+4Fh+var_68]
0x18002d066  lea     rcx, [rbp+4Fh+var_90]
0x18002d06a  mov     rax, [rdi]
0x18002d06d  mov     rbx, [rax+30h]
0x18002d071  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18002d076  lea     r8, [rbp+4Fh+var_90]
0x18002d07a  xor     edx, edx
0x18002d07c  mov     rcx, rdi
0x18002d07f  mov     rax, rbx
0x18002d082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d087  test    eax, eax
0x18002d089  js      loc_18002D450
0x18002d08f  mov     rdi, [rbp+4Fh+var_90]
0x18002d093  lea     rcx, [rbp+4Fh+var_70]
0x18002d097  mov     [rbp+4Fh+var_70], r12
0x18002d09b  mov     [rbp+4Fh+var_78], r12
0x18002d09f  mov     rax, [rdi]
0x18002d0a2  mov     rbx, [rax+0B0h]
0x18002d0a9  call    ?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)
0x18002d0ae  lea     rdx, [rbp+4Fh+var_70]
0x18002d0b2  mov     rcx, rdi
0x18002d0b5  mov     rax, rbx
0x18002d0b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0bd  mov     esi, eax
0x18002d0bf  test    eax, eax
0x18002d0c1  js      short loc_18002D136
0x18002d0c3  lea     rdx, [rbp+4Fh+var_98]
0x18002d0c7  mov     [rbp+4Fh+var_98], r12
0x18002d0cb  lea     rcx, [rbp+4Fh+var_70]
0x18002d0cf  call    ??$As@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@U?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *>>::As<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>>)
0x18002d0d4  mov     esi, eax
0x18002d0d6  test    eax, eax
0x18002d0d8  js      short loc_18002D12D
0x18002d0da  mov     rdi, [rbp+4Fh+var_98]
0x18002d0de  lea     rcx, [rbp+4Fh+var_78]
0x18002d0e2  mov     rax, [rdi]
0x18002d0e5  mov     rbx, [rax+30h]
0x18002d0e9  call    ?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)
0x18002d0ee  lea     rdx, [rbp+4Fh+var_78]
0x18002d0f2  mov     rcx, rdi
0x18002d0f5  mov     rax, rbx
0x18002d0f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0fd  mov     esi, eax
0x18002d0ff  test    eax, eax
0x18002d101  js      short loc_18002D12D
0x18002d103  mov     rcx, [rbp+4Fh+var_78]
0x18002d107  mov     rbx, [r14]
0x18002d10a  mov     [rbp+4Fh+var_88], rcx
0x18002d10e  test    rcx, rcx
0x18002d111  jz      short loc_18002D11F
0x18002d113  mov     rax, [rcx]
0x18002d116  mov     rax, [rax+8]
0x18002d11a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d11f  mov     rdx, rbx
0x18002d122  lea     rcx, [rbp+4Fh+var_88]
0x18002d126  call    WalkItemProperties
0x18002d12b  mov     esi, eax
0x18002d12d  lea     rcx, [rbp+4Fh+var_98]
0x18002d131  call    ?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)
0x18002d136  mov     [rbp+4Fh+string], r12
0x18002d13a  test    esi, esi
0x18002d13c  js      loc_18002D435
0x18002d142  mov     rcx, [rbp+4Fh+var_90]
0x18002d146  lea     rdx, [rbp+4Fh+string]
0x18002d14a  mov     rax, [rcx]
0x18002d14d  mov     rax, [rax+30h]
0x18002d151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d156  mov     esi, eax
0x18002d158  test    eax, eax
0x18002d15a  js      loc_18002D435
0x18002d160  mov     rcx, [rbp+4Fh+string]; string
0x18002d164  xor     eax, eax
0x18002d166  xorps   xmm0, xmm0
0x18002d169  mov     qword ptr [rbp+4Fh+ppropvar+10h], rax
0x18002d16d  movups  xmmword ptr [rbp+4Fh+ppropvar], xmm0
0x18002d171  xor     edx, edx; length
0x18002d173  lea     r13d, [rax+1Fh]
0x18002d177  mov     word ptr [rbp+4Fh+ppropvar], r13w
0x18002d17c  call    cs:__imp_WindowsGetStringRawBuffer
0x18002d182  mov     rcx, [r14]
0x18002d185  lea     r8, [rbp+4Fh+ppropvar]
0x18002d189  mov     qword ptr [rbp+4Fh+ppropvar+8], rax
0x18002d18d  lea     rdx, PKEY_ItemUrl
0x18002d194  mov     rax, [rcx]
0x18002d197  mov     rax, [rax+30h]
0x18002d19b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d1a0  mov     esi, eax
0x18002d1a2  test    eax, eax
0x18002d1a4  js      loc_18002D435
0x18002d1aa  mov     rdi, [rbp+4Fh+var_90]
0x18002d1ae  lea     rcx, [rbp+4Fh+var_98]
0x18002d1b2  mov     [rbp+4Fh+var_98], r12
0x18002d1b6  mov     rax, [rdi]
0x18002d1b9  mov     rbx, [rax+40h]
0x18002d1bd  call    ?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)
0x18002d1c2  lea     rdx, [rbp+4Fh+var_98]
0x18002d1c6  mov     rcx, rdi
0x18002d1c9  mov     rax, rbx
0x18002d1cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d1d1  mov     esi, eax
0x18002d1d3  test    eax, eax
0x18002d1d5  js      loc_18002D42C
0x18002d1db  mov     rcx, [rbp+4Fh+var_98]; struct Windows::Media::Streaming::Internal::IProtocolInfo *
0x18002d1df  call    ?IsProtocolInfoProtected@CCDSResultsParser@@SA_NPEAUIProtocolInfo@Internal@Streaming@Media@Windows@@@Z; CCDSResultsParser::IsProtocolInfoProtected(Windows::Media::Streaming::Internal::IProtocolInfo *)
0x18002d1e4  lea     r15d, [r13-14h]
0x18002d1e8  test    al, al
0x18002d1ea  jz      short loc_18002D229
0x18002d1ec  mov     rcx, [r14]
0x18002d1ef  lea     r8, [rbp+4Fh+ppropvar]
0x18002d1f3  xor     eax, eax
0x18002d1f5  lea     rdx, PKEY_DRM_IsProtected
0x18002d1fc  mov     qword ptr [rbp+4Fh+ppropvar+10h], rax
0x18002d200  xorps   xmm0, xmm0
0x18002d203  or      eax, 0FFFFFFFFh
0x18002d206  movups  xmmword ptr [rbp+4Fh+ppropvar], xmm0
0x18002d20a  mov     word ptr [rbp+4Fh+ppropvar+8], ax
0x18002d20e  mov     word ptr [rbp+4Fh+ppropvar], r15w
0x18002d213  mov     rax, [rcx]
0x18002d216  mov     rax, [rax+30h]
0x18002d21a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d21f  mov     esi, eax
0x18002d221  test    eax, eax
0x18002d223  js      loc_18002D42C
0x18002d229  mov     rcx, [rbp+4Fh+var_98]
0x18002d22d  lea     rdx, [rbp+4Fh+var_A0]
0x18002d231  mov     [rbp+4Fh+var_A0], r12
0x18002d235  mov     rax, [rcx]
0x18002d238  mov     rax, [rax+58h]
0x18002d23c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d241  mov     esi, eax
0x18002d243  mov     edi, 1
0x18002d248  test    eax, eax
0x18002d24a  js      short loc_18002D27D
0x18002d24c  mov     rcx, [rbp+4Fh+var_A0]; string
0x18002d250  call    cs:__imp_WindowsIsStringEmpty
0x18002d256  test    eax, eax
0x18002d258  jnz     short loc_18002D27D
0x18002d25a  mov     r8d, edi; length
0x18002d25d  lea     rdx, Src; "*"
0x18002d264  lea     rcx, [rbp+4Fh+ppropvar]; string
0x18002d268  call    ??0StringReference@Internal@Windows@@QEAA@PEBGI@Z; Windows::Internal::StringReference::StringReference(ushort const *,uint)
0x18002d26d  mov     rdx, rax; struct Windows::Internal::String *
0x18002d270  lea     rcx, [rbp+4Fh+var_A0]; this
0x18002d274  call    ?CompareOrdinal@String@Internal@Windows@@QEBAHAEBV123@@Z; Windows::Internal::String::CompareOrdinal(Windows::Internal::String const &)
0x18002d279  test    eax, eax
0x18002d27b  jnz     short loc_18002D2A5
0x18002d27d  mov     rcx, [rbp+4Fh+var_A0]; string
0x18002d281  call    cs:__imp_WindowsDeleteString
0x18002d287  mov     r8, [r14]; struct IPropertyStore *
0x18002d28a  lea     r9, [rbp+4Fh+var_A0]; HSTRING *
0x18002d28e  mov     rdx, [rbp+4Fh+string]; HSTRING
0x18002d292  mov     [rbp+4Fh+var_A0], r12
0x18002d296  call    ?_ComputeMimeType@CCdsObjectMapper@@AEAAJPEAUHSTRING__@@PEAUIPropertyStore@@PEAPEAU2@@Z; CCdsObjectMapper::_ComputeMimeType(HSTRING__ *,IPropertyStore *,HSTRING__ * *)
0x18002d29b  mov     esi, eax
0x18002d29d  test    eax, eax
0x18002d29f  js      loc_18002D34C
0x18002d2a5  mov     rcx, [rbp+4Fh+var_A0]; string
0x18002d2a9  call    cs:__imp_WindowsGetStringLen
0x18002d2af  mov     ebx, 1Ch
0x18002d2b4  cmp     eax, ebx
0x18002d2b6  jb      short loc_18002D2E2
0x18002d2b8  mov     rcx, [rbp+4Fh+var_A0]; string
0x18002d2bc  xor     edx, edx; length
0x18002d2be  call    cs:__imp_WindowsGetStringRawBuffer
0x18002d2c4  mov     r9d, ebx; cchCount2
0x18002d2c7  mov     [rsp+0D0h+bIgnoreCase], edi; bIgnoreCase
0x18002d2cb  mov     rcx, rax; lpString1
0x18002d2ce  lea     r8, aApplicationVnd; "application/vnd.ms-playtoapp"
0x18002d2d5  mov     edx, ebx; cchCount1
0x18002d2d7  call    cs:__imp_CompareStringOrdinal
0x18002d2dd  cmp     eax, 2
0x18002d2e0  jz      short loc_18002D2ED
0x18002d2e2  lea     rdx, [rbp+4Fh+var_A0]; struct Windows::Internal::String *
0x18002d2e6  call    ?_RemoveParametersFromMimeType@CCdsObjectMapper@@AEAAJAEAVString@Internal@Windows@@@Z; CCdsObjectMapper::_RemoveParametersFromMimeType(Windows::Internal::String &)
0x18002d2eb  mov     esi, eax
0x18002d2ed  test    esi, esi
0x18002d2ef  js      short loc_18002D34C
0x18002d2f1  mov     rcx, [rbp+4Fh+var_A0]; string
0x18002d2f5  xorps   xmm0, xmm0
0x18002d2f8  xor     eax, eax
0x18002d2fa  xor     edx, edx; length
0x18002d2fc  movups  xmmword ptr [rbp+4Fh+ppropvar], xmm0
0x18002d300  mov     word ptr [rbp+4Fh+ppropvar], r13w
0x18002d305  mov     qword ptr [rbp+4Fh+ppropvar+10h], rax
0x18002d309  call    cs:__imp_WindowsGetStringRawBuffer
0x18002d30f  mov     rcx, [r14]
0x18002d312  lea     r8, [rbp+4Fh+ppropvar]
0x18002d316  mov     qword ptr [rbp+4Fh+ppropvar+8], rax
0x18002d31a  lea     rdx, PKEY_MIMEType
0x18002d321  mov     rax, [rcx]
0x18002d324  mov     rax, [rax+30h]
0x18002d328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d32d  mov     esi, eax
0x18002d32f  test    eax, eax
0x18002d331  js      short loc_18002D34C
0x18002d333  mov     rcx, [rbp+4Fh+var_A0]; string
0x18002d337  xor     edx, edx; length
0x18002d339  call    cs:__imp_WindowsGetStringRawBuffer
0x18002d33f  mov     rdx, [r14]; struct IPropertyStore *
0x18002d342  mov     r8, rax; unsigned __int16 *
0x18002d345  call    ?_SetFileExtensionProperty@CCdsObjectMapper@@AEAAJPEAUIPropertyStore@@PEBG@Z; CCdsObjectMapper::_SetFileExtensionProperty(IPropertyStore *,ushort const *)
0x18002d34a  mov     esi, eax
0x18002d34c  lea     rcx, [rbp+4Fh+var_A0]; this
0x18002d350  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18002d355  test    esi, esi
0x18002d357  js      loc_18002D42C
0x18002d35d  mov     rdx, [r14]; struct IPropertyStore *
0x18002d360  call    ?_SetFileNameProperty@CCdsObjectMapper@@AEAAJPEAUIPropertyStore@@@Z; CCdsObjectMapper::_SetFileNameProperty(IPropertyStore *)
0x18002d365  mov     rdi, [rbp+4Fh+var_98]
0x18002d369  lea     rcx, [rbp+4Fh+var_A0]
0x18002d36d  mov     [rbp+4Fh+var_A0], r12
0x18002d371  mov     rax, [rdi]
0x18002d374  mov     rbx, [rax+78h]
0x18002d378  call    ?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)
0x18002d37d  lea     rdx, [rbp+4Fh+var_A0]
0x18002d381  mov     rcx, rdi
0x18002d384  mov     rax, rbx
0x18002d387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d38c  test    eax, eax
0x18002d38e  js      loc_18002D423
0x18002d394  mov     rdi, [rbp+4Fh+var_A0]
0x18002d398  lea     rdx, aDlnaOrgPn; "DLNA.ORG_PN"
0x18002d39f  mov     [rbp+4Fh+var_88], r12
0x18002d3a3  lea     rcx, [rbp+4Fh+ppropvar]; string
0x18002d3a7  mov     r8d, r15d; length
0x18002d3aa  mov     rax, [rdi]
0x18002d3ad  mov     rbx, [rax+30h]
0x18002d3b1  call    ??0StringReference@Internal@Windows@@QEAA@PEBGI@Z; Windows::Internal::StringReference::StringReference(ushort const *,uint)
0x18002d3b6  lea     r8, [rbp+4Fh+var_88]
0x18002d3ba  mov     rcx, rdi
0x18002d3bd  mov     rdx, [rax]
0x18002d3c0  mov     rax, rbx
0x18002d3c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3c8  test    eax, eax
0x18002d3ca  js      short loc_18002D41A
0x18002d3cc  mov     rcx, [rbp+4Fh+var_88]; string
0x18002d3d0  xorps   xmm0, xmm0
0x18002d3d3  xor     eax, eax
0x18002d3d5  xor     edx, edx; length
0x18002d3d7  movups  xmmword ptr [rbp+4Fh+ppropvar], xmm0
0x18002d3db  mov     qword ptr [rbp+4Fh+ppropvar+10h], rax
0x18002d3df  call    cs:__imp_WindowsGetStringRawBuffer
0x18002d3e5  mov     rcx, rax; psz
0x18002d3e8  lea     rdx, [rbp+4Fh+ppropvar]; ppropvar
0x18002d3ec  call    cs:__imp_InitPropVariantFromStringAsVector
0x18002d3f2  test    eax, eax
0x18002d3f4  js      short loc_18002D41A
0x18002d3f6  mov     rcx, [r14]
0x18002d3f9  lea     r8, [rbp+4Fh+ppropvar]
0x18002d3fd  lea     rdx, PKEY_Media_DlnaProfileID
0x18002d404  mov     rax, [rcx]
  ... truncated ...
```
