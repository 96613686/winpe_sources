# CCdsObjectMapper::MapContentDirectoryObject(Windows::Media::Streaming::Internal::IContentDirectoryObject *,_CDS_TYPE,IPropertyStore * *)

- ea: `0x18002d49c`
- end: `0x18002d931`
- name: `?MapContentDirectoryObject@CCdsObjectMapper@@QEAAJPEAUIContentDirectoryObject@Internal@Streaming@Media@Windows@@W4_CDS_TYPE@@PEAPEAUIPropertyStore@@@Z`
- size: `1173`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800270b0`
- `0x18002cfb4`

## callees

- `0x180001710`
- `0x1800097c0`
- `0x18000ae38`
- `0x18000d990`
- `0x180011930`
- `0x180014a00`
- `0x180016840`
- `0x180019b84`
- `0x18002b708`
- `0x18002c3bc`
- `0x18002d49c`
- `0x18002e13c`
- `0x18002ec60`
- `0x18002ee8c`
- `0x18002ef70`
- `0x18002f190`
- `0x18002f430`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d893`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d893`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18002d51f`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18002d51f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002d56d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002d825`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002d56d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002d825`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d544`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d544`

## string_xrefs

- `0x18002d5d3`: `xmlns:microsoft`

## pseudocode

```c
__int64 __fastcall CCdsObjectMapper::MapContentDirectoryObject(__int64 a1, __int64 *a2, unsigned int a3, void **a4)
{
  HRESULT v7; // ebx
  __int64 v8; // rax
  __int64 (__fastcall *v9)(__int64 *, HSTRING *); // rbx
  __int64 (__fastcall *v10)(__int64 *, __int64 *); // rbx
  __int64 v11; // rdi
  int (__fastcall *v12)(__int64, _QWORD, _BYTE *); // rbx
  _QWORD *v13; // rax
  __int64 v14; // rdi
  int (__fastcall *v15)(__int64, _QWORD, _BYTE *); // rbx
  _QWORD *v16; // rax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, DlnaUrlHelpers **); // rbx
  void *v19; // rbx
  unsigned int v20; // edi
  HRESULT v21; // eax
  __int64 v22; // rax
  __int64 (__fastcall *v23)(__int64 *, __int64 *); // rbx
  __int64 v24; // rdi
  int (__fastcall *v25)(__int64, _QWORD, DlnaUrlHelpers **); // rbx
  HSTRING *v26; // r8
  const unsigned __int16 *StringRawBuffer; // rax
  unsigned int v28; // eax
  _BYTE v30[8]; // [rsp+20h] [rbp-49h] BYREF
  __int64 v31; // [rsp+28h] [rbp-41h] BYREF
  void *ppv; // [rsp+30h] [rbp-39h] BYREF
  DlnaUrlHelpers *v33; // [rsp+38h] [rbp-31h] BYREF
  __int64 v34; // [rsp+40h] [rbp-29h] BYREF
  HSTRING string; // [rsp+48h] [rbp-21h] BYREF
  __int64 v36; // [rsp+50h] [rbp-19h] BYREF
  DlnaUrlHelpers *v37; // [rsp+58h] [rbp-11h] BYREF
  __int64 v38; // [rsp+60h] [rbp-9h] BYREF
  PROPVARIANT pvar; // [rsp+68h] [rbp-1h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_28f76f838e153eeeda4709e76ebe7f13_Traceguids);
  v38 = 0;
  *a4 = 0;
  ppv = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&ppv);
  v7 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
  if ( v7 >= 0 )
  {
    v8 = *a2;
    v31 = 0;
    v33 = 0;
    string = 0;
    v9 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(v8 + 48);
    WindowsDeleteString(0);
    string = 0;
    v7 = v9(a2, &string);
    if ( v7 >= 0 )
    {
      WindowsGetStringRawBuffer(string, 0);
      v7 = SetKeyValueInPropertyStore((struct IPropertyStore *)ppv, L"upnp:class");
      if ( v7 >= 0 )
      {
        v10 = *(__int64 (__fastcall **)(__int64 *, __int64 *))(*a2 + 104);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(&v31);
        v7 = v10(a2, &v31);
        if ( v7 >= 0 )
        {
          if ( !a3 )
          {
            v11 = v31;
            v30[0] = 0;
            v12 = *(int (__fastcall **)(__int64, _QWORD, _BYTE *))(*(_QWORD *)v31 + 64LL);
            v13 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                              (HSTRING *)&pvar,
                              L"xmlns:microsoft",
                              0xFu);
            if ( v12(v11, *v13, v30) >= 0 && v30[0] )
            {
              a3 = 1;
            }
            else
            {
              v14 = v31;
              v15 = *(int (__fastcall **)(__int64, _QWORD, _BYTE *))(*(_QWORD *)v31 + 64LL);
              v16 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                                (HSTRING *)&pvar,
                                L"microsoft:userEffectiveRating",
                                0x1Du);
              if ( v15(v14, *v16, v30) >= 0 && v30[0] )
                a3 = 1;
            }
          }
          v34 = 0;
          v7 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *>>::As<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>(
                 &v31,
                 &v34);
          if ( v7 >= 0 )
          {
            v17 = v34;
            v18 = *(__int64 (__fastcall **)(__int64, DlnaUrlHelpers **))(*(_QWORD *)v34 + 48LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(&v33);
            v7 = v18(v17, &v33);
            if ( v7 >= 0 )
            {
              v19 = ppv;
              v37 = v33;
              if ( v33 )
                (*(void (__fastcall **)(DlnaUrlHelpers *))(*(_QWORD *)v33 + 8LL))(v33);
              v7 = WalkItemProperties(&v37, v19);
            }
          }
          v20 = 0;
          do
          {
            if ( v7 < 0 )
              break;
            v21 = ((__int64 (__fastcall *)(__int64, _QWORD, void *))CCDSResultsParser::c_rgPropKeyHandlers[v20++])(
                    v31,
                    a3,
                    ppv);
            v7 = v21;
          }
          while ( v20 < 3 );
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(&v34);
        }
      }
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_28f76f838e153eeeda4709e76ebe7f13_Traceguids);
    }
    if ( v7 >= 0 )
    {
      v22 = *a2;
      v34 = 0;
      v23 = *(__int64 (__fastcall **)(__int64 *, __int64 *))(v22 + 112);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(&v34);
      v7 = v23(a2, &v34);
      if ( v7 >= 0 )
        v7 = CCDSResultsParser::ParseExtendedProperties(v34, ppv);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(&v34);
    }
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(&v33);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(&v31);
  }
  v36 = 0;
  if ( v7 >= 0 )
  {
    if ( (*(int (__fastcall **)(__int64 *, __int64 *))(*a2 + 144))(a2, &v36) >= 0 && v36 )
    {
      LODWORD(v31) = 0;
      v33 = 0;
      (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v36 + 56LL))(v36, &v31);
      if ( (_DWORD)v31 )
      {
        v24 = v36;
        v25 = *(int (__fastcall **)(__int64, _QWORD, DlnaUrlHelpers **))(*(_QWORD *)v36 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v33);
        if ( v25(v24, 0, &v33) >= 0 )
        {
          pvar.vt = 0;
          string = 0;
          if ( DlnaUrlHelpers::GetDecoratedUrlFromResElement(
                 v33,
                 (struct Windows::Media::Streaming::Internal::IResElement *)&string,
                 v26) >= 0 )
          {
            StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
            if ( (int)InitPropVariantFromString(StringRawBuffer, &pvar) >= 0 )
            {
              v28 = (*(__int64 (__fastcall **)(void *, const struct _tagpropertykey *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                      ppv,
                      &PKEY_AlbumArtURI,
                      &pvar);
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_28f76f838e153eeeda4709e76ebe7f13_Traceguids, v28);
              }
            }
          }
          Windows::Internal::String::~String((Windows::Internal::String *)&string);
          PropVariantClear(&pvar);
        }
      }
      v7 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v33);
    }
    *a4 = ppv;
    ppv = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v7 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      &WPP_28f76f838e153eeeda4709e76ebe7f13_Traceguids,
      (unsigned int)v7);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v36);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&ppv);
  Windows::Internal::String::~String((Windows::Internal::String *)&v38);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002d49c  mov     [rsp-8+arg_0], rbx
0x18002d4a1  push    rbp
0x18002d4a2  push    rsi
0x18002d4a3  push    rdi
0x18002d4a4  push    r12
0x18002d4a6  push    r13
0x18002d4a8  push    r14
0x18002d4aa  push    r15
0x18002d4ac  lea     rbp, [rsp-27h]
0x18002d4b1  sub     rsp, 90h
0x18002d4b8  mov     rax, cs:__security_cookie
0x18002d4bf  xor     rax, rsp
0x18002d4c2  mov     [rbp+57h+var_38], rax
0x18002d4c6  mov     r15, r9
0x18002d4c9  mov     esi, r8d
0x18002d4cc  mov     r14, rdx
0x18002d4cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d4d6  lea     r13, WPP_GLOBAL_Control
0x18002d4dd  cmp     rcx, r13
0x18002d4e0  jz      short loc_18002D4FD
0x18002d4e2  test    byte ptr [rcx+1Ch], 2
0x18002d4e6  jz      short loc_18002D4FD
0x18002d4e8  mov     rcx, [rcx+10h]
0x18002d4ec  lea     r8, WPP_28f76f838e153eeeda4709e76ebe7f13_Traceguids
0x18002d4f3  mov     edx, 0Bh
0x18002d4f8  call    WPP_SF_
0x18002d4fd  xor     r12d, r12d
0x18002d500  lea     rcx, [rbp+57h+ppv]
0x18002d504  mov     [rbp+57h+var_60], r12
0x18002d508  mov     [r15], r12
0x18002d50b  mov     [rbp+57h+ppv], r12
0x18002d50f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18002d514  lea     rdx, [rbp+57h+ppv]; ppv
0x18002d518  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18002d51f  call    cs:__imp_PSCreateMemoryPropertyStore
0x18002d525  mov     ebx, eax
0x18002d527  test    eax, eax
0x18002d529  js      loc_18002D77F
0x18002d52f  mov     rax, [r14]
0x18002d532  xor     ecx, ecx; string
0x18002d534  mov     [rbp+57h+var_98], r12
0x18002d538  mov     [rbp+57h+var_88], r12
0x18002d53c  mov     [rbp+57h+string], r12
0x18002d540  mov     rbx, [rax+30h]
0x18002d544  call    cs:__imp_WindowsDeleteString
0x18002d54a  lea     rdx, [rbp+57h+string]
0x18002d54e  mov     [rbp+57h+string], r12
0x18002d552  mov     rcx, r14
0x18002d555  mov     rax, rbx
0x18002d558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d55d  mov     ebx, eax
0x18002d55f  test    eax, eax
0x18002d561  js      loc_18002D6F2
0x18002d567  mov     rcx, [rbp+57h+string]; string
0x18002d56b  xor     edx, edx; length
0x18002d56d  call    cs:__imp_WindowsGetStringRawBuffer
0x18002d573  mov     rcx, [rbp+57h+ppv]; struct IPropertyStore *
0x18002d577  lea     rdx, aUpnpClass; "upnp:class"
0x18002d57e  mov     r8, rax
0x18002d581  call    SetKeyValueInPropertyStore
0x18002d586  mov     ebx, eax
0x18002d588  test    eax, eax
0x18002d58a  js      loc_18002D6F2
0x18002d590  mov     rax, [r14]
0x18002d593  lea     rcx, [rbp+57h+var_98]
0x18002d597  mov     rbx, [rax+68h]
0x18002d59b  call    ?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)
0x18002d5a0  lea     rdx, [rbp+57h+var_98]
0x18002d5a4  mov     rcx, r14
0x18002d5a7  mov     rax, rbx
0x18002d5aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d5af  mov     ebx, eax
0x18002d5b1  test    eax, eax
0x18002d5b3  js      loc_18002D6F2
0x18002d5b9  lea     r13d, [r12+1]
0x18002d5be  test    esi, esi
0x18002d5c0  jnz     loc_18002D64A
0x18002d5c6  mov     rdi, [rbp+57h+var_98]
0x18002d5ca  lea     r8d, [r12+0Fh]; length
0x18002d5cf  mov     [rbp+57h+var_A0], r12b
0x18002d5d3  lea     rdx, aXmlnsMicrosoft; "xmlns:microsoft"
0x18002d5da  lea     rcx, [rbp+57h+pvar]; string
0x18002d5de  mov     rax, [rdi]
0x18002d5e1  mov     rbx, [rax+40h]
0x18002d5e5  call    ??0StringReference@Internal@Windows@@QEAA@PEBGI@Z; Windows::Internal::StringReference::StringReference(ushort const *,uint)
0x18002d5ea  lea     r8, [rbp+57h+var_A0]
0x18002d5ee  mov     rcx, rdi
0x18002d5f1  mov     rdx, [rax]
0x18002d5f4  mov     rax, rbx
0x18002d5f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d5fc  test    eax, eax
0x18002d5fe  js      short loc_18002D60B
0x18002d600  cmp     [rbp+57h+var_A0], r12b
0x18002d604  jz      short loc_18002D60B
0x18002d606  mov     esi, r13d
0x18002d609  jmp     short loc_18002D64A
0x18002d60b  mov     rdi, [rbp+57h+var_98]
0x18002d60f  lea     rdx, aMicrosoftUsere_0; "microsoft:userEffectiveRating"
0x18002d616  mov     r8d, 1Dh; length
0x18002d61c  lea     rcx, [rbp+57h+pvar]; string
0x18002d620  mov     rax, [rdi]
0x18002d623  mov     rbx, [rax+40h]
0x18002d627  call    ??0StringReference@Internal@Windows@@QEAA@PEBGI@Z; Windows::Internal::StringReference::StringReference(ushort const *,uint)
0x18002d62c  lea     r8, [rbp+57h+var_A0]
0x18002d630  mov     rcx, rdi
0x18002d633  mov     rdx, [rax]
0x18002d636  mov     rax, rbx
0x18002d639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d63e  test    eax, eax
0x18002d640  js      short loc_18002D64A
0x18002d642  cmp     [rbp+57h+var_A0], r12b
0x18002d646  cmovnz  esi, r13d
0x18002d64a  lea     rdx, [rbp+57h+var_80]
0x18002d64e  mov     [rbp+57h+var_80], r12
0x18002d652  lea     rcx, [rbp+57h+var_98]
0x18002d656  call    ??$As@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@U?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *>>::As<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>>)
0x18002d65b  mov     ebx, eax
0x18002d65d  test    eax, eax
0x18002d65f  js      short loc_18002D6B5
0x18002d661  mov     rdi, [rbp+57h+var_80]
0x18002d665  lea     rcx, [rbp+57h+var_88]
0x18002d669  mov     rax, [rdi]
0x18002d66c  mov     rbx, [rax+30h]
0x18002d670  call    ?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)
0x18002d675  lea     rdx, [rbp+57h+var_88]
0x18002d679  mov     rcx, rdi
0x18002d67c  mov     rax, rbx
0x18002d67f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d684  mov     ebx, eax
0x18002d686  test    eax, eax
0x18002d688  js      short loc_18002D6B5
0x18002d68a  mov     rcx, [rbp+57h+var_88]
0x18002d68e  mov     rbx, [rbp+57h+ppv]
0x18002d692  mov     [rbp+57h+var_68], rcx
0x18002d696  test    rcx, rcx
0x18002d699  jz      short loc_18002D6A7
0x18002d69b  mov     rax, [rcx]
0x18002d69e  mov     rax, [rax+8]
0x18002d6a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d6a7  mov     rdx, rbx
0x18002d6aa  lea     rcx, [rbp+57h+var_68]
0x18002d6ae  call    WalkItemProperties
0x18002d6b3  mov     ebx, eax
0x18002d6b5  mov     edi, r12d
0x18002d6b8  test    ebx, ebx
0x18002d6ba  js      short loc_18002D6E2
0x18002d6bc  mov     r8, [rbp+57h+ppv]
0x18002d6c0  lea     r9, ?c_rgPropKeyHandlers@CCDSResultsParser@@2PAP6AJPEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@W4_CDS_TYPE@@PEAUIPropertyStore@@@ZA; long (*near * CCDSResultsParser::c_rgPropKeyHandlers)(Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *,_CDS_TYPE,IPropertyStore *)
0x18002d6c7  mov     rcx, [rbp+57h+var_98]
0x18002d6cb  mov     edx, esi
0x18002d6cd  mov     eax, edi
0x18002d6cf  mov     rax, ds:(?c_rgPropKeyHandlers@CCDSResultsParser@@2PAP6AJPEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@W4_CDS_TYPE@@PEAUIPropertyStore@@@ZA - 180038040h)[r9+rax*8]; long (*near * CCDSResultsParser::c_rgPropKeyHandlers)(Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *,_CDS_TYPE,IPropertyStore *)
0x18002d6d3  call    _guard_dispatch_icall$thunk$10345483385596137414; CCDSResultsParser::RatingHandler(Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *,_CDS_TYPE,IPropertyStore *)
0x18002d6d8  add     edi, r13d
0x18002d6db  mov     ebx, eax
0x18002d6dd  cmp     edi, 3
0x18002d6e0  jb      short loc_18002D6B8
0x18002d6e2  lea     rcx, [rbp+57h+var_80]
0x18002d6e6  call    ?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)
0x18002d6eb  lea     r13, WPP_GLOBAL_Control
0x18002d6f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d6f9  cmp     rcx, r13
0x18002d6fc  jz      short loc_18002D71F
0x18002d6fe  test    byte ptr [rcx+1Ch], 4
0x18002d702  jz      short loc_18002D71F
0x18002d704  cmp     byte ptr [rcx+19h], 4
0x18002d708  jb      short loc_18002D71F
0x18002d70a  mov     rcx, [rcx+10h]
0x18002d70e  lea     r8, WPP_28f76f838e153eeeda4709e76ebe7f13_Traceguids
0x18002d715  mov     edx, 0Ch
0x18002d71a  call    WPP_SF_
0x18002d71f  test    ebx, ebx
0x18002d721  js      short loc_18002D764
0x18002d723  mov     rax, [r14]
0x18002d726  lea     rcx, [rbp+57h+var_80]
0x18002d72a  mov     [rbp+57h+var_80], r12
0x18002d72e  mov     rbx, [rax+70h]
0x18002d732  call    ?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)
0x18002d737  lea     rdx, [rbp+57h+var_80]
0x18002d73b  mov     rcx, r14
0x18002d73e  mov     rax, rbx
0x18002d741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d746  mov     ebx, eax
0x18002d748  test    eax, eax
0x18002d74a  js      short loc_18002D75B
0x18002d74c  mov     rdx, [rbp+57h+ppv]
0x18002d750  mov     rcx, [rbp+57h+var_80]
0x18002d754  call    ?ParseExtendedProperties@CCDSResultsParser@@SAJPEAU?$IMapView@PEAUHSTRING__@@PEAU?$IVectorView@PEAUICDSPropertyValue@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@PEAUIPropertyStore@@@Z; CCDSResultsParser::ParseExtendedProperties(Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Foundation::Collections::IVectorView<Windows::Media::Streaming::Internal::ICDSPropertyValue *> *> *,IPropertyStore *)
0x18002d759  mov     ebx, eax
0x18002d75b  lea     rcx, [rbp+57h+var_80]
0x18002d75f  call    ?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)
0x18002d764  lea     rcx, [rbp+57h+string]; this
0x18002d768  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18002d76d  lea     rcx, [rbp+57h+var_88]
0x18002d771  call    ?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)
0x18002d776  lea     rcx, [rbp+57h+var_98]
0x18002d77a  call    ?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)
0x18002d77f  mov     [rbp+57h+var_70], r12
0x18002d783  test    ebx, ebx
0x18002d785  js      loc_18002D8B0
0x18002d78b  mov     rax, [r14]
0x18002d78e  lea     rdx, [rbp+57h+var_70]
0x18002d792  mov     rcx, r14
0x18002d795  mov     rax, [rax+90h]
0x18002d79c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d7a1  test    eax, eax
0x18002d7a3  js      loc_18002D8A5
0x18002d7a9  mov     rcx, [rbp+57h+var_70]
0x18002d7ad  test    rcx, rcx
0x18002d7b0  jz      loc_18002D8A5
0x18002d7b6  mov     dword ptr [rbp+57h+var_98], r12d
0x18002d7ba  lea     rdx, [rbp+57h+var_98]
0x18002d7be  mov     [rbp+57h+var_88], r12
0x18002d7c2  mov     rax, [rcx]
0x18002d7c5  mov     rax, [rax+38h]
0x18002d7c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d7ce  cmp     dword ptr [rbp+57h+var_98], r12d
0x18002d7d2  jbe     loc_18002D899
0x18002d7d8  mov     rdi, [rbp+57h+var_70]
0x18002d7dc  lea     rcx, [rbp+57h+var_88]
0x18002d7e0  mov     rax, [rdi]
0x18002d7e3  mov     rbx, [rax+30h]
0x18002d7e7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18002d7ec  lea     r8, [rbp+57h+var_88]
0x18002d7f0  xor     edx, edx
0x18002d7f2  mov     rcx, rdi
0x18002d7f5  mov     rax, rbx
0x18002d7f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d7fd  test    eax, eax
0x18002d7ff  js      loc_18002D899
0x18002d805  mov     rcx, [rbp+57h+var_88]; this
0x18002d809  lea     rdx, [rbp+57h+string]; struct Windows::Media::Streaming::Internal::IResElement *
0x18002d80d  mov     word ptr [rbp+57h+pvar], r12w
0x18002d812  mov     [rbp+57h+string], r12
0x18002d816  call    ?GetDecoratedUrlFromResElement@DlnaUrlHelpers@@YAJPEAUIResElement@Internal@Streaming@Media@Windows@@PEAPEAUHSTRING__@@@Z; DlnaUrlHelpers::GetDecoratedUrlFromResElement(Windows::Media::Streaming::Internal::IResElement *,HSTRING__ * *)
0x18002d81b  test    eax, eax
0x18002d81d  js      short loc_18002D886
0x18002d81f  mov     rcx, [rbp+57h+string]; string
0x18002d823  xor     edx, edx; length
0x18002d825  call    cs:__imp_WindowsGetStringRawBuffer
0x18002d82b  mov     rcx, rax; Source
0x18002d82e  lea     rdx, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x18002d832  call    ?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(ushort const *,tagPROPVARIANT *)
0x18002d837  test    eax, eax
0x18002d839  js      short loc_18002D886
0x18002d83b  mov     rcx, [rbp+57h+ppv]
0x18002d83f  lea     r8, [rbp+57h+pvar]
0x18002d843  lea     rdx, PKEY_AlbumArtURI
0x18002d84a  mov     rax, [rcx]
0x18002d84d  mov     rax, [rax+30h]
0x18002d851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d856  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d85d  cmp     rcx, r13
0x18002d860  jz      short loc_18002D886
0x18002d862  test    byte ptr [rcx+1Ch], 40h
0x18002d866  jz      short loc_18002D886
0x18002d868  cmp     byte ptr [rcx+19h], 4
0x18002d86c  jb      short loc_18002D886
0x18002d86e  mov     rcx, [rcx+10h]
0x18002d872  lea     r8, WPP_28f76f838e153eeeda4709e76ebe7f13_Traceguids
0x18002d879  mov     edx, 0Dh
0x18002d87e  mov     r9d, eax
0x18002d881  call    WPP_SF_d
0x18002d886  lea     rcx, [rbp+57h+string]; this
0x18002d88a  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18002d88f  lea     rcx, [rbp+57h+pvar]; pvar
0x18002d893  call    cs:__imp_PropVariantClear
0x18002d899  lea     rcx, [rbp+57h+var_88]
0x18002d89d  mov     ebx, r12d
0x18002d8a0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18002d8a5  mov     rax, [rbp+57h+ppv]
0x18002d8a9  mov     [r15], rax
0x18002d8ac  mov     [rbp+57h+ppv], r12
0x18002d8b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d8b7  cmp     rcx, r13
0x18002d8ba  jz      short loc_18002D8ED
0x18002d8bc  test    byte ptr [rcx+1Ch], 2
0x18002d8c0  jz      short loc_18002D8ED
0x18002d8c2  movzx   eax, byte ptr [rcx+19h]
0x18002d8c6  mov     edx, ebx
0x18002d8c8  sar     edx, 1Fh
0x18002d8cb  and     edx, 0FFFFFFFDh
0x18002d8ce  add     edx, 5
0x18002d8d1  cmp     eax, edx
0x18002d8d3  jb      short loc_18002D8ED
0x18002d8d5  mov     rcx, [rcx+10h]
0x18002d8d9  lea     r8, WPP_28f76f838e153eeeda4709e76ebe7f13_Traceguids
0x18002d8e0  mov     edx, 0Eh
0x18002d8e5  mov     r9d, ebx
0x18002d8e8  call    WPP_SF_d
0x18002d8ed  lea     rcx, [rbp+57h+var_70]
0x18002d8f1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18002d8f6  lea     rcx, [rbp+57h+ppv]
0x18002d8fa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18002d8ff  lea     rcx, [rbp+57h+var_60]; this
0x18002d903  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18002d908  mov     eax, ebx
0x18002d90a  mov     rcx, [rbp+57h+var_38]
0x18002d90e  xor     rcx, rsp; StackCookie
0x18002d911  call    __security_check_cookie
  ... truncated ...
```
