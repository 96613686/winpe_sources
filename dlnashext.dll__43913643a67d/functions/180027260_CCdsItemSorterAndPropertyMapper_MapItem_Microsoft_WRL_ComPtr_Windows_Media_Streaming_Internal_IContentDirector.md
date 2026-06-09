# CCdsItemSorterAndPropertyMapper::MapItem(Microsoft::WRL::ComPtr<Windows::Media::Streaming::Internal::IContentDirectoryItem>,uchar,IPropertyStore * *)

- ea: `0x180027260`
- end: `0x1800276f6`
- name: `?MapItem@CCdsItemSorterAndPropertyMapper@@QEAAJV?$ComPtr@UIContentDirectoryItem@Internal@Streaming@Media@Windows@@@WRL@Microsoft@@EPEAPEAUIPropertyStore@@@Z`
- size: `1174`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18001dd80`
- `0x180027d0c`

## callees

- `0x180001710`
- `0x1800097c0`
- `0x18000ae38`
- `0x180011930`
- `0x180014a00`
- `0x180016840`
- `0x180019b84`
- `0x180025f04`
- `0x180025f50`
- `0x180025ff0`
- `0x180026090`
- `0x180027260`
- `0x18002b708`
- `0x18002cfb4`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800275cd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800275cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002758b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180027613`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002758b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180027613`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180027366`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180027366`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CCdsItemSorterAndPropertyMapper::MapItem(__int64 a1, unsigned __int16 *a2, char a3, _QWORD *a4)
{
  void *v6; // r14
  int ActivationFactory; // esi
  HSTRING *v8; // rax
  HSTRING v9; // rbx
  __int64 v10; // rdx
  __int64 v11; // rsi
  __int64 (__fastcall *v12)(__int64, HSTRING, __int64, char *); // rdi
  __int64 v13; // rbx
  HSTRING *v14; // rax
  __int64 v15; // rsi
  __int64 (__fastcall *v16)(__int64, HSTRING, __int64, char *); // rdi
  __int64 v17; // rbx
  HSTRING *v18; // rax
  __int64 v19; // rsi
  __int64 (__fastcall *v20)(__int64, HSTRING, __int64, char *); // rdi
  __int64 v21; // rbx
  HSTRING *v22; // rax
  HSTRING *v23; // rax
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, _QWORD, _QWORD, __int64 (__fastcall ****)(__int64, GUID *, __int64 **)); // rbx
  __int64 v26; // rcx
  __int64 v27; // r8
  bool v28; // cf
  __int64 (__fastcall ***v29)(__int64, GUID *, __int64 **); // rdi
  __int64 (__fastcall *v30)(__int64, GUID *, __int64 **); // rbx
  __int64 v31; // rdi
  int (__fastcall *v32)(__int64, _QWORD, DlnaUrlHelpers **); // rbx
  HSTRING *v33; // r8
  const unsigned __int16 *StringRawBuffer; // rax
  char v36; // [rsp+30h] [rbp-59h] BYREF
  char v37; // [rsp+31h] [rbp-58h]
  HSTRING string; // [rsp+38h] [rbp-51h] BYREF
  __int64 v39; // [rsp+40h] [rbp-49h] BYREF
  __int64 v40; // [rsp+48h] [rbp-41h] BYREF
  __int64 (__fastcall ***v41)(__int64, GUID *, __int64 **); // [rsp+50h] [rbp-39h] BYREF
  DlnaUrlHelpers *v42; // [rsp+58h] [rbp-31h] BYREF
  __int64 v43; // [rsp+60h] [rbp-29h] BYREF
  void *v44; // [rsp+68h] [rbp-21h] BYREF
  HSTRING v45; // [rsp+70h] [rbp-19h] BYREF
  _QWORD *v46; // [rsp+78h] [rbp-11h]
  unsigned __int16 *v47; // [rsp+80h] [rbp-9h]
  PROPVARIANT pvar; // [rsp+88h] [rbp-1h] BYREF

  v46 = a4;
  v37 = a3;
  v47 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_2c46815e90c93d4060bd1f828fac3da7_Traceguids);
  v6 = 0;
  v44 = 0;
  v41 = 0;
  if ( *(_QWORD *)(a1 + 8) )
  {
    ActivationFactory = 0;
LABEL_14:
    if ( !*(_QWORD *)(a1 + 16) )
    {
      v23 = Windows::Internal::StringReference::StringReference(
              (HSTRING *)&pvar,
              L"Windows.Media.Streaming.Internal.ResElementSorter",
              0x31u);
      ActivationFactory = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Media::Streaming::Internal::IResElementSorter>>(
                            *v23,
                            a1 + 16);
    }
    if ( ActivationFactory >= 0 )
    {
      v24 = *(_QWORD *)(a1 + 16);
      v25 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 (__fastcall ****)(__int64, GUID *, __int64 **)))(*(_QWORD *)v24 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&v41);
      ActivationFactory = v25(v24, *(_QWORD *)a2, *(_QWORD *)(a1 + 8), &v41);
      if ( ActivationFactory >= 0 )
      {
        v28 = v37 != 0;
        v37 = -v37;
        ActivationFactory = CCdsObjectMapper::MapContentDirectoryItem(v26, v41, v27, 2 - (unsigned int)v28, &v44);
        v6 = v44;
      }
    }
    goto LABEL_19;
  }
  v40 = 0;
  string = 0;
  v39 = 0;
  v36 = 0;
  v8 = Windows::Internal::StringReference::StringReference((HSTRING *)&pvar, (const unsigned __int16 (*)[43])a2);
  ActivationFactory = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
                        *v8,
                        a1 + 8);
  if ( ActivationFactory >= 0 )
  {
    ActivationFactory = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
                          a1 + 8,
                          &v40);
    if ( ActivationFactory >= 0 )
    {
      v9 = *Windows::Internal::StringReference::StringReference(
              (HSTRING *)&pvar,
              L"Windows.Foundation.PropertyValue",
              0x20u);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&string);
      ActivationFactory = RoGetActivationFactory(v9, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &string);
      if ( ActivationFactory >= 0 )
      {
        LOBYTE(v10) = 1;
        ActivationFactory = (*(__int64 (__fastcall **)(HSTRING, __int64, __int64 *))(*(_QWORD *)string + 136LL))(
                              string,
                              v10,
                              &v39);
        if ( ActivationFactory >= 0 )
        {
          v11 = v40;
          v12 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, char *))(*(_QWORD *)v40 + 80LL);
          v13 = v39;
          v14 = Windows::Internal::StringReference::StringReference((HSTRING *)&pvar, L"HTTP Only", 9u);
          ActivationFactory = v12(v11, *v14, v13, &v36);
          if ( ActivationFactory >= 0 )
          {
            v15 = v40;
            v16 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, char *))(*(_QWORD *)v40 + 80LL);
            v17 = v39;
            v18 = Windows::Internal::StringReference::StringReference((HSTRING *)&pvar, L"Prefer No Transcoding", 0x15u);
            ActivationFactory = v16(v15, *v18, v17, &v36);
            if ( ActivationFactory >= 0 )
            {
              v19 = v40;
              v20 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, char *))(*(_QWORD *)v40 + 80LL);
              v21 = v39;
              v22 = Windows::Internal::StringReference::StringReference((HSTRING *)&pvar, L"Best Url Only", 0xDu);
              ActivationFactory = v20(v19, *v22, v21, &v36);
            }
          }
        }
      }
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v39);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&string);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v40);
  if ( ActivationFactory >= 0 )
    goto LABEL_14;
LABEL_19:
  v43 = 0;
  v42 = 0;
  if ( ActivationFactory >= 0 )
  {
    v29 = v41;
    v30 = (*v41)[6];
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v43);
    if ( ((int (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 **), __int64 *))v30)(v29, &v43) >= 0 )
    {
      v31 = v43;
      v32 = *(int (__fastcall **)(__int64, _QWORD, DlnaUrlHelpers **))(*(_QWORD *)v43 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&v42);
      if ( v32(v31, 0, &v42) >= 0 )
      {
        pvar.vt = 0;
        string = 0;
        ActivationFactory = DlnaUrlHelpers::GetDecoratedUrlFromResElement(
                              v42,
                              (struct Windows::Media::Streaming::Internal::IResElement *)&string,
                              v33);
        if ( ActivationFactory >= 0 )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          ActivationFactory = InitPropVariantFromString(StringRawBuffer, &pvar);
          if ( ActivationFactory >= 0 )
            ActivationFactory = (*(__int64 (__fastcall **)(void *, const struct _tagpropertykey *, PROPVARIANT *))(*(_QWORD *)v6 + 48LL))(
                                  v6,
                                  &PKEY_DLNA_NativeResUrl,
                                  &pvar);
        }
        Windows::Internal::String::~String(&string);
        PropVariantClear(&pvar);
      }
    }
  }
  v45 = 0;
  if ( ActivationFactory >= 0 )
  {
    if ( (*(int (__fastcall **)(_QWORD, HSTRING *))(**(_QWORD **)a2 + 56LL))(*(_QWORD *)a2, &v45) < 0
      || (memset(&pvar, 0, sizeof(pvar)),
          pvar.vt = 31,
          pvar.hVal.QuadPart = (LONGLONG)WindowsGetStringRawBuffer(v45, 0),
          ActivationFactory = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v6 + 48LL))(
                                v6,
                                &PKEY_ItemUrl,
                                &pvar),
          ActivationFactory >= 0) )
    {
      v44 = 0;
      *v46 = v6;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((ActivationFactory >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      &WPP_2c46815e90c93d4060bd1f828fac3da7_Traceguids,
      (unsigned int)ActivationFactory);
  }
  Windows::Internal::String::~String(&v45);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&v42);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v43);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&v41);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&v44);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)a2);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180027260  mov     [rsp-8+arg_10], rbx
0x180027265  push    rbp
0x180027266  push    rsi
0x180027267  push    rdi
0x180027268  push    r12
0x18002726a  push    r13
0x18002726c  push    r14
0x18002726e  push    r15
0x180027270  lea     rbp, [rsp-27h]
0x180027275  sub     rsp, 0B0h
0x18002727c  mov     rax, cs:__security_cookie
0x180027283  xor     rax, rsp
0x180027286  mov     [rbp+57h+var_38], rax
0x18002728a  mov     [rbp+57h+var_68], r9
0x18002728e  mov     [rbp+57h+var_AF], r8b
0x180027292  mov     r12, rdx
0x180027295  mov     r13, rcx
0x180027298  mov     [rbp+57h+var_60], rdx
0x18002729c  lea     rax, WPP_GLOBAL_Control
0x1800272a3  mov     r10, cs:WPP_GLOBAL_Control
0x1800272aa  cmp     r10, rax
0x1800272ad  jz      short loc_1800272CB
0x1800272af  test    byte ptr [r10+1Ch], 2
0x1800272b4  jz      short loc_1800272CB
0x1800272b6  mov     edx, 11h
0x1800272bb  lea     r8, WPP_2c46815e90c93d4060bd1f828fac3da7_Traceguids
0x1800272c2  mov     rcx, [r10+10h]
0x1800272c6  call    WPP_SF_
0x1800272cb  xor     r14d, r14d
0x1800272ce  mov     [rbp+57h+var_78], r14
0x1800272d2  mov     [rbp+57h+var_90], r14
0x1800272d6  lea     r15, [r13+8]
0x1800272da  cmp     [r15], r14
0x1800272dd  jz      short loc_1800272E6
0x1800272df  xor     esi, esi
0x1800272e1  jmp     loc_18002747A
0x1800272e6  mov     [rbp+57h+var_98], 0
0x1800272ee  mov     [rbp+57h+string], 0
0x1800272f6  mov     [rbp+57h+var_A0], 0
0x1800272fe  mov     [rbp+57h+var_B0], 0
0x180027302  lea     rcx, [rbp+57h+pvar]; string
0x180027306  call    ??$?0$0CL@@StringReference@Internal@Windows@@QEAA@AEAY0CL@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[43])
0x18002730b  mov     rdx, r15
0x18002730e  mov     rcx, [rax]
0x180027311  call    ??$ActivateInstance@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>)
0x180027316  mov     esi, eax
0x180027318  test    eax, eax
0x18002731a  js      loc_180027455
0x180027320  lea     rdx, [rbp+57h+var_98]
0x180027324  mov     rcx, r15
0x180027327  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x18002732c  mov     esi, eax
0x18002732e  test    eax, eax
0x180027330  js      loc_180027455
0x180027336  mov     r8d, 20h ; ' '; length
0x18002733c  lea     rdx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x180027343  lea     rcx, [rbp+57h+pvar]; string
0x180027347  call    ??0StringReference@Internal@Windows@@QEAA@PEBGI@Z; Windows::Internal::StringReference::StringReference(ushort const *,uint)
0x18002734c  mov     rbx, [rax]
0x18002734f  lea     rcx, [rbp+57h+string]
0x180027353  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180027358  lea     r8, [rbp+57h+string]
0x18002735c  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x180027363  mov     rcx, rbx
0x180027366  call    cs:__imp_RoGetActivationFactory
0x18002736c  mov     esi, eax
0x18002736e  test    eax, eax
0x180027370  js      loc_180027455
0x180027376  mov     rcx, [rbp+57h+string]
0x18002737a  mov     rax, [rcx]
0x18002737d  lea     r8, [rbp+57h+var_A0]
0x180027381  mov     dl, 1
0x180027383  mov     rax, [rax+88h]
0x18002738a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002738f  mov     esi, eax
0x180027391  test    eax, eax
0x180027393  js      loc_180027455
0x180027399  mov     rsi, [rbp+57h+var_98]
0x18002739d  mov     rax, [rsi]
0x1800273a0  mov     rdi, [rax+50h]
0x1800273a4  mov     rbx, [rbp+57h+var_A0]
0x1800273a8  mov     r8d, 9; length
0x1800273ae  lea     rdx, aHttpOnly; "HTTP Only"
0x1800273b5  lea     rcx, [rbp+57h+pvar]; string
0x1800273b9  call    ??0StringReference@Internal@Windows@@QEAA@PEBGI@Z; Windows::Internal::StringReference::StringReference(ushort const *,uint)
0x1800273be  lea     r9, [rbp+57h+var_B0]
0x1800273c2  mov     r8, rbx
0x1800273c5  mov     rdx, [rax]
0x1800273c8  mov     rcx, rsi
0x1800273cb  mov     rax, rdi
0x1800273ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800273d3  mov     esi, eax
0x1800273d5  test    eax, eax
0x1800273d7  js      short loc_180027455
0x1800273d9  mov     rsi, [rbp+57h+var_98]
0x1800273dd  mov     rax, [rsi]
0x1800273e0  mov     rdi, [rax+50h]
0x1800273e4  mov     rbx, [rbp+57h+var_A0]
0x1800273e8  mov     r8d, 15h; length
0x1800273ee  lea     rdx, aPreferNoTransc; "Prefer No Transcoding"
0x1800273f5  lea     rcx, [rbp+57h+pvar]; string
0x1800273f9  call    ??0StringReference@Internal@Windows@@QEAA@PEBGI@Z; Windows::Internal::StringReference::StringReference(ushort const *,uint)
0x1800273fe  lea     r9, [rbp+57h+var_B0]
0x180027402  mov     r8, rbx
0x180027405  mov     rdx, [rax]
0x180027408  mov     rcx, rsi
0x18002740b  mov     rax, rdi
0x18002740e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027413  mov     esi, eax
0x180027415  test    eax, eax
0x180027417  js      short loc_180027455
0x180027419  mov     rsi, [rbp+57h+var_98]
0x18002741d  mov     rax, [rsi]
0x180027420  mov     rdi, [rax+50h]
0x180027424  mov     rbx, [rbp+57h+var_A0]
0x180027428  mov     r8d, 0Dh; length
0x18002742e  lea     rdx, aBestUrlOnly; "Best Url Only"
0x180027435  lea     rcx, [rbp+57h+pvar]; string
0x180027439  call    ??0StringReference@Internal@Windows@@QEAA@PEBGI@Z; Windows::Internal::StringReference::StringReference(ushort const *,uint)
0x18002743e  lea     r9, [rbp+57h+var_B0]
0x180027442  mov     r8, rbx
0x180027445  mov     rdx, [rax]
0x180027448  mov     rcx, rsi
0x18002744b  mov     rax, rdi
0x18002744e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027453  mov     esi, eax
0x180027455  lea     rcx, [rbp+57h+var_A0]
0x180027459  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18002745e  nop
0x18002745f  lea     rcx, [rbp+57h+string]
0x180027463  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180027468  nop
0x180027469  lea     rcx, [rbp+57h+var_98]
0x18002746d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180027472  test    esi, esi
0x180027474  js      loc_1800274FC
0x18002747a  lea     rdi, [r13+10h]
0x18002747e  cmp     qword ptr [rdi], 0
0x180027482  jnz     short loc_1800274A7
0x180027484  mov     r8d, 31h ; '1'; length
0x18002748a  lea     rdx, ?RuntimeClass_Windows_Media_Streaming_Internal_ResElementSorter@@3QBGB; "Windows.Media.Streaming.Internal.ResEle"...
0x180027491  lea     rcx, [rbp+57h+pvar]; string
0x180027495  call    ??0StringReference@Internal@Windows@@QEAA@PEBGI@Z; Windows::Internal::StringReference::StringReference(ushort const *,uint)
0x18002749a  mov     rdx, rdi
0x18002749d  mov     rcx, [rax]
0x1800274a0  call    ??$ActivateInstance@V?$ComPtr@UIResElementSorter@Internal@Streaming@Media@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIResElementSorter@Internal@Streaming@Media@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Media::Streaming::Internal::IResElementSorter>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Media::Streaming::Internal::IResElementSorter>>)
0x1800274a5  mov     esi, eax
0x1800274a7  test    esi, esi
0x1800274a9  js      short loc_1800274FC
0x1800274ab  mov     rdi, [rdi]
0x1800274ae  mov     rax, [rdi]
0x1800274b1  mov     rbx, [rax+30h]
0x1800274b5  lea     rcx, [rbp+57h+var_90]
0x1800274b9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800274be  lea     r9, [rbp+57h+var_90]
0x1800274c2  mov     r8, [r15]
0x1800274c5  mov     rdx, [r12]
0x1800274c9  mov     rcx, rdi
0x1800274cc  mov     rax, rbx
0x1800274cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800274d4  mov     esi, eax
0x1800274d6  test    eax, eax
0x1800274d8  js      short loc_1800274FC
0x1800274da  neg     [rbp+57h+var_AF]
0x1800274dd  sbb     r9d, r9d
0x1800274e0  add     r9d, 2
0x1800274e4  lea     rax, [rbp+57h+var_78]
0x1800274e8  mov     [rsp+0E0h+var_C0], rax
0x1800274ed  mov     rdx, [rbp+57h+var_90]
0x1800274f1  call    ?MapContentDirectoryItem@CCdsObjectMapper@@QEAAJPEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@IW4_CDS_TYPE@@PEAPEAUIPropertyStore@@@Z; CCdsObjectMapper::MapContentDirectoryItem(Windows::Media::Streaming::Internal::IContentDirectoryItem *,uint,_CDS_TYPE,IPropertyStore * *)
0x1800274f6  mov     esi, eax
0x1800274f8  mov     r14, [rbp+57h+var_78]
0x1800274fc  mov     [rbp+57h+var_80], 0
0x180027504  mov     [rbp+57h+var_88], 0
0x18002750c  test    esi, esi
0x18002750e  js      loc_1800275D3
0x180027514  mov     rdi, [rbp+57h+var_90]
0x180027518  mov     rax, [rdi]
0x18002751b  mov     rbx, [rax+30h]
0x18002751f  lea     rcx, [rbp+57h+var_80]
0x180027523  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180027528  lea     rdx, [rbp+57h+var_80]
0x18002752c  mov     rcx, rdi
0x18002752f  mov     rax, rbx
0x180027532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027537  test    eax, eax
0x180027539  js      loc_1800275D3
0x18002753f  mov     rdi, [rbp+57h+var_80]
0x180027543  mov     rax, [rdi]
0x180027546  mov     rbx, [rax+30h]
0x18002754a  lea     rcx, [rbp+57h+var_88]
0x18002754e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180027553  lea     r8, [rbp+57h+var_88]
0x180027557  xor     edx, edx
0x180027559  mov     rcx, rdi
0x18002755c  mov     rax, rbx
0x18002755f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027564  test    eax, eax
0x180027566  js      short loc_1800275D3
0x180027568  xor     eax, eax
0x18002756a  mov     word ptr [rbp+57h+pvar], ax
0x18002756e  mov     [rbp+57h+string], rax
0x180027572  lea     rdx, [rbp+57h+string]; struct Windows::Media::Streaming::Internal::IResElement *
0x180027576  mov     rcx, [rbp+57h+var_88]; this
0x18002757a  call    ?GetDecoratedUrlFromResElement@DlnaUrlHelpers@@YAJPEAUIResElement@Internal@Streaming@Media@Windows@@PEAPEAUHSTRING__@@@Z; DlnaUrlHelpers::GetDecoratedUrlFromResElement(Windows::Media::Streaming::Internal::IResElement *,HSTRING__ * *)
0x18002757f  mov     esi, eax
0x180027581  test    eax, eax
0x180027583  js      short loc_1800275BF
0x180027585  xor     edx, edx; length
0x180027587  mov     rcx, [rbp+57h+string]; string
0x18002758b  call    cs:__imp_WindowsGetStringRawBuffer
0x180027591  lea     rdx, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x180027595  mov     rcx, rax; Source
0x180027598  call    ?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(ushort const *,tagPROPVARIANT *)
0x18002759d  mov     esi, eax
0x18002759f  test    eax, eax
0x1800275a1  js      short loc_1800275BF
0x1800275a3  mov     rax, [r14]
0x1800275a6  lea     r8, [rbp+57h+pvar]
0x1800275aa  lea     rdx, PKEY_DLNA_NativeResUrl
0x1800275b1  mov     rcx, r14
0x1800275b4  mov     rax, [rax+30h]
0x1800275b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275bd  mov     esi, eax
0x1800275bf  lea     rcx, [rbp+57h+string]; this
0x1800275c3  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800275c8  nop
0x1800275c9  lea     rcx, [rbp+57h+pvar]; pvar
0x1800275cd  call    cs:__imp_PropVariantClear
0x1800275d3  mov     [rbp+57h+var_70], 0
0x1800275db  test    esi, esi
0x1800275dd  js      short loc_18002764C
0x1800275df  mov     rcx, [r12]
0x1800275e3  mov     rax, [rcx]
0x1800275e6  lea     rdx, [rbp+57h+var_70]
0x1800275ea  mov     rax, [rax+38h]
0x1800275ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275f3  test    eax, eax
0x1800275f5  js      short loc_18002763D
0x1800275f7  xorps   xmm0, xmm0
0x1800275fa  xor     eax, eax
0x1800275fc  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180027600  mov     qword ptr [rbp+57h+pvar+10h], rax
0x180027604  mov     eax, 1Fh
0x180027609  mov     word ptr [rbp+57h+pvar], ax
0x18002760d  xor     edx, edx; length
0x18002760f  mov     rcx, [rbp+57h+var_70]; string
0x180027613  call    cs:__imp_WindowsGetStringRawBuffer
0x180027619  mov     qword ptr [rbp+57h+pvar+8], rax
0x18002761d  mov     rax, [r14]
0x180027620  lea     r8, [rbp+57h+pvar]
0x180027624  lea     rdx, PKEY_ItemUrl
0x18002762b  mov     rcx, r14
0x18002762e  mov     rax, [rax+30h]
0x180027632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027637  mov     esi, eax
0x180027639  test    eax, eax
0x18002763b  js      short loc_18002764C
0x18002763d  mov     [rbp+57h+var_78], 0
0x180027645  mov     rax, [rbp+57h+var_68]
0x180027649  mov     [rax], r14
0x18002764c  mov     r10, cs:WPP_GLOBAL_Control
0x180027653  lea     rax, WPP_GLOBAL_Control
0x18002765a  cmp     r10, rax
0x18002765d  jz      short loc_180027693
0x18002765f  test    byte ptr [r10+1Ch], 2
0x180027664  jz      short loc_180027693
0x180027666  mov     ecx, esi
0x180027668  sar     ecx, 1Fh
0x18002766b  and     ecx, 0FFFFFFFDh
0x18002766e  add     ecx, 5
0x180027671  movzx   eax, byte ptr [r10+19h]
0x180027676  cmp     eax, ecx
0x180027678  jb      short loc_180027693
0x18002767a  mov     edx, 12h
0x18002767f  mov     r9d, esi
0x180027682  lea     r8, WPP_2c46815e90c93d4060bd1f828fac3da7_Traceguids
0x180027689  mov     rcx, [r10+10h]
0x18002768d  call    WPP_SF_d
0x180027692  nop
0x180027693  lea     rcx, [rbp+57h+var_70]; this
0x180027697  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18002769c  nop
0x18002769d  lea     rcx, [rbp+57h+var_88]
0x1800276a1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800276a6  nop
0x1800276a7  lea     rcx, [rbp+57h+var_80]
0x1800276ab  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800276b0  nop
0x1800276b1  lea     rcx, [rbp+57h+var_90]
0x1800276b5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800276ba  nop
0x1800276bb  lea     rcx, [rbp+57h+var_78]
0x1800276bf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800276c4  nop
0x1800276c5  mov     rcx, r12
0x1800276c8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800276cd  mov     eax, esi
0x1800276cf  mov     rcx, [rbp+57h+var_38]
0x1800276d3  xor     rcx, rsp; StackCookie
  ... truncated ...
```
