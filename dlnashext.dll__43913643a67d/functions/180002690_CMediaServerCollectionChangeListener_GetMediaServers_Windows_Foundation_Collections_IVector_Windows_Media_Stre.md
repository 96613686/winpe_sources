# CMediaServerCollectionChangeListener::GetMediaServers(Windows::Foundation::Collections::IVector<Windows::Media::Streaming::IBasicDevice *> * *)

- ea: `0x180002690`
- end: `0x180002a9e`
- name: `?GetMediaServers@CMediaServerCollectionChangeListener@@QEAAJPEAPEAU?$IVector@PEAUIBasicDevice@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@Z`
- size: `1038`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800024f0`
- `0x18000dcf8`

## callees

- `0x180001710`
- `0x180002690`
- `0x180009f50`
- `0x18000e214`
- `0x180011930`
- `0x180014a00`
- `0x180019b84`
- `0x180021fc0`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800026c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800026c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002a6e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002a6e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180002752`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180002794`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800027d6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180002893`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180002752`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180002794`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800027d6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180002893`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000273b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000277d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800027bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000287c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000273b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000277d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800027bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000287c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800028ae`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800028ae`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CMediaServerCollectionChangeListener::GetMediaServers(__int64 a1, _QWORD *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  HRESULT v5; // eax
  HRESULT v6; // eax
  HRESULT v7; // eax
  HRESULT v8; // eax
  int ActivationFactory; // edi
  __int64 v10; // rdi
  _QWORD *v11; // rcx
  __int64 v12; // rcx
  _QWORD *v13; // rax
  unsigned int i; // edx
  _QWORD *v15; // rax
  __int64 NextValue; // rax
  __int64 v17; // rcx
  _QWORD *v18; // rax
  unsigned int v19; // edx
  _QWORD *v20; // rcx
  _QWORD *v22; // [rsp+20h] [rbp-158h] BYREF
  __int64 v23; // [rsp+28h] [rbp-150h] BYREF
  _QWORD *v24; // [rsp+30h] [rbp-148h] BYREF
  struct _RTL_CRITICAL_SECTION *v25; // [rsp+38h] [rbp-140h]
  char v26; // [rsp+40h] [rbp-138h]
  _QWORD v27[3]; // [rsp+50h] [rbp-128h] BYREF
  GUID v28; // [rsp+68h] [rbp-110h]
  GUID v29; // [rsp+78h] [rbp-100h]
  GUID v30; // [rsp+88h] [rbp-F0h]
  GUID v31; // [rsp+98h] [rbp-E0h]
  GUID v32; // [rsp+A8h] [rbp-D0h]
  HSTRING_HEADER hstringHeader; // [rsp+C0h] [rbp-B8h] BYREF
  HSTRING string; // [rsp+D8h] [rbp-A0h] BYREF
  HSTRING_HEADER v35; // [rsp+E0h] [rbp-98h] BYREF
  HSTRING v36; // [rsp+F8h] [rbp-80h] BYREF
  HSTRING_HEADER v37; // [rsp+100h] [rbp-78h] BYREF
  HSTRING v38; // [rsp+118h] [rbp-60h] BYREF
  HSTRING_HEADER v39; // [rsp+120h] [rbp-58h] BYREF
  HSTRING v40; // [rsp+138h] [rbp-40h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 96);
  v25 = (struct _RTL_CRITICAL_SECTION *)(a1 + 96);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 96));
  v26 = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_843f9b73b5843d1b8d7c57834cd63f0f_Traceguids);
  v24 = 0;
  *a2 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v24);
  string = 0;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Media.Streaming.IBasicDevice>",
         0x4Eu,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v36 = 0;
  v6 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Media.Streaming.IBasicDevice>",
         0x52u,
         &v35,
         &v36);
  if ( v6 < 0 )
  {
    RaiseException(v6, 1u, 0, 0);
    __debugbreak();
  }
  v38 = 0;
  v7 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IIterator`1<Windows.Media.Streaming.IBasicDevice>",
         0x50u,
         &v37,
         &v38);
  if ( v7 < 0 )
  {
    RaiseException(v7, 1u, 0, 0);
    __debugbreak();
  }
  v27[0] = string;
  v27[1] = v36;
  v27[2] = v38;
  v28 = GUID_f4f26cbb_7962_48b7_80f7_c3a5d753bcb0;
  v29 = GUID_4c58be45_d16f_5b3a_840d_a6b4e20b7088;
  v30 = GUID_a55cf16b_71a2_5525_ac3b_2f5bc1eeec46;
  v31 = GUID_7d468b5e_763b_59cd_a086_ec6d8be0d858;
  v32 = GUID_84a8c766_4bc5_5757_9f1b_f61cfd9e5693;
  v23 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v23);
  v40 = 0;
  v8 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v39, &v40);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v40, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v23);
  if ( ActivationFactory >= 0 )
  {
    v22 = 0;
    v10 = v23;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v22);
    ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}(v10, v27, &v22);
    if ( ActivationFactory >= 0 )
    {
      v13 = v22;
      v22 = 0;
      v24 = v13;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v22);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v23);
      ActivationFactory = 0;
    }
    else
    {
      v11 = v22;
      if ( v22 )
      {
        v22 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v11 + 16LL))(v11);
      }
      v12 = v23;
      if ( v23 )
      {
        v23 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      }
    }
  }
  else
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v23);
  }
  if ( ActivationFactory >= 0 )
  {
    if ( *(_QWORD *)(a1 + 144) )
    {
      for ( i = 0; i < *(_DWORD *)(a1 + 152); ++i )
      {
        v15 = *(_QWORD **)(*(_QWORD *)(a1 + 136) + 8LL * i);
        if ( v15 )
          goto LABEL_28;
      }
    }
    v15 = 0;
LABEL_28:
    v22 = v15;
    try
    {
      while ( v22 )
      {
        NextValue = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CMediaServerCollectionChangeListener::ServerRegistrationState *,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<CMediaServerCollectionChangeListener::ServerRegistrationState *>>::GetNextValue(
                      a1 + 136,
                      &v22);
        v17 = *(_QWORD *)NextValue;
        if ( (*(_DWORD *)(*(_QWORD *)NextValue + 16LL) & 0xFFFFFFFD) == 0 )
        {
          v23 = 0;
          AgileGitPtr::CopyTo<Windows::Media::Streaming::IBasicDevice>(v17, &v23);
          if ( v23 )
            (*(void (__fastcall **)(_QWORD *))(*v24 + 104LL))(v24);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v23);
        }
      }
      v18 = v24;
      v24 = 0;
      *a2 = v18;
    }
    catch ( ... )
    {
      LODWORD(v22) = -2147024882;
      v4 = v25;
      ActivationFactory = -2147024882;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v19 = 2;
    if ( ActivationFactory >= 0 )
      v19 = 5;
    if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= v19 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        &WPP_843f9b73b5843d1b8d7c57834cd63f0f_Traceguids,
        (unsigned int)ActivationFactory);
  }
  v20 = v24;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(_QWORD *, _QWORD))(*v20 + 16LL))(v20, *v20);
  }
  LeaveCriticalSection(v4);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180002690  mov     [rsp+arg_10], rbx
0x180002695  push    rsi
0x180002696  push    rdi
0x180002697  push    r12
0x180002699  push    r14
0x18000269b  push    r15
0x18000269d  sub     rsp, 150h
0x1800026a4  mov     rax, cs:__security_cookie
0x1800026ab  xor     rax, rsp
0x1800026ae  mov     [rsp+178h+var_38], rax
0x1800026b6  mov     r12, rdx
0x1800026b9  mov     r15, rcx
0x1800026bc  lea     rsi, [rcx+60h]
0x1800026c0  mov     [rsp+178h+var_140], rsi
0x1800026c5  mov     rcx, rsi; lpCriticalSection
0x1800026c8  call    cs:__imp_EnterCriticalSection
0x1800026ce  mov     [rsp+178h+var_138], 1
0x1800026d3  lea     r14, WPP_GLOBAL_Control
0x1800026da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800026e1  cmp     rcx, r14
0x1800026e4  jz      short loc_180002701
0x1800026e6  test    byte ptr [rcx+1Ch], 2
0x1800026ea  jz      short loc_180002701
0x1800026ec  mov     edx, 0Bh
0x1800026f1  lea     r8, WPP_843f9b73b5843d1b8d7c57834cd63f0f_Traceguids
0x1800026f8  mov     rcx, [rcx+10h]
0x1800026fc  call    WPP_SF_
0x180002701  xor     ebx, ebx
0x180002703  mov     [rsp+178h+var_148], rbx
0x180002708  mov     [r12], rbx
0x18000270c  lea     rcx, [rsp+178h+var_148]
0x180002711  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180002716  nop
0x180002717  mov     [rsp+178h+string], rbx
0x18000271f  lea     r9, [rsp+178h+string]; string
0x180002727  lea     r8, [rsp+178h+hstringHeader]; hstringHeader
0x18000272f  mov     edx, 4Eh ; 'N'; length
0x180002734  lea     rcx, sourceString; "Windows.Foundation.Collections.IVector`"...
0x18000273b  call    cs:__imp_WindowsCreateStringReference
0x180002741  test    eax, eax
0x180002743  jns     short loc_180002759
0x180002745  xor     r9d, r9d; lpArguments
0x180002748  xor     r8d, r8d; nNumberOfArguments
0x18000274b  mov     edx, 1; dwExceptionFlags
0x180002750  mov     ecx, eax; dwExceptionCode
0x180002752  call    cs:__imp_RaiseException
0x180002758  int     3; Trap to Debugger
0x180002759  mov     [rsp+178h+var_80], rbx
0x180002761  lea     r9, [rsp+178h+var_80]; string
0x180002769  lea     r8, [rsp+178h+var_98]; hstringHeader
0x180002771  mov     edx, 52h ; 'R'; length
0x180002776  lea     rcx, aWindowsFoundat_0; "Windows.Foundation.Collections.IVectorV"...
0x18000277d  call    cs:__imp_WindowsCreateStringReference
0x180002783  test    eax, eax
0x180002785  jns     short loc_18000279B
0x180002787  xor     r9d, r9d; lpArguments
0x18000278a  xor     r8d, r8d; nNumberOfArguments
0x18000278d  mov     edx, 1; dwExceptionFlags
0x180002792  mov     ecx, eax; dwExceptionCode
0x180002794  call    cs:__imp_RaiseException
0x18000279a  int     3; Trap to Debugger
0x18000279b  mov     [rsp+178h+var_60], rbx
0x1800027a3  lea     r9, [rsp+178h+var_60]; string
0x1800027ab  lea     r8, [rsp+178h+var_78]; hstringHeader
0x1800027b3  mov     edx, 50h ; 'P'; length
0x1800027b8  lea     rcx, aWindowsFoundat; "Windows.Foundation.Collections.IIterato"...
0x1800027bf  call    cs:__imp_WindowsCreateStringReference
0x1800027c5  test    eax, eax
0x1800027c7  jns     short loc_1800027DD
0x1800027c9  xor     r9d, r9d; lpArguments
0x1800027cc  xor     r8d, r8d; nNumberOfArguments
0x1800027cf  mov     edx, 1; dwExceptionFlags
0x1800027d4  mov     ecx, eax; dwExceptionCode
0x1800027d6  call    cs:__imp_RaiseException
0x1800027dc  int     3; Trap to Debugger
0x1800027dd  mov     rax, [rsp+178h+string]
0x1800027e5  mov     [rsp+178h+var_128], rax
0x1800027ea  mov     rax, [rsp+178h+var_80]
0x1800027f2  mov     [rsp+178h+var_120], rax
0x1800027f7  mov     rax, [rsp+178h+var_60]
0x1800027ff  mov     [rsp+178h+var_118], rax
0x180002804  movups  xmm0, xmmword ptr cs:_GUID_f4f26cbb_7962_48b7_80f7_c3a5d753bcb0.Data1
0x18000280b  movups  [rsp+178h+var_110], xmm0
0x180002810  movups  xmm1, xmmword ptr cs:_GUID_4c58be45_d16f_5b3a_840d_a6b4e20b7088.Data1
0x180002817  movups  [rsp+178h+var_100], xmm1
0x18000281c  movups  xmm0, xmmword ptr cs:_GUID_a55cf16b_71a2_5525_ac3b_2f5bc1eeec46.Data1
0x180002823  movups  [rsp+178h+var_F0], xmm0
0x18000282b  movups  xmm1, xmmword ptr cs:_GUID_7d468b5e_763b_59cd_a086_ec6d8be0d858.Data1
0x180002832  movups  [rsp+178h+var_E0], xmm1
0x18000283a  movups  xmm0, xmmword ptr cs:_GUID_84a8c766_4bc5_5757_9f1b_f61cfd9e5693.Data1
0x180002841  movups  [rsp+178h+var_D0], xmm0
0x180002849  mov     [rsp+178h+var_150], rbx
0x18000284e  lea     rcx, [rsp+178h+var_150]
0x180002853  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180002858  mov     [rsp+178h+var_40], rbx
0x180002860  lea     r9, [rsp+178h+var_40]; string
0x180002868  lea     r8, [rsp+178h+var_58]; hstringHeader
0x180002870  mov     edx, 2Ch ; ','; length
0x180002875  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x18000287c  call    cs:__imp_WindowsCreateStringReference
0x180002882  test    eax, eax
0x180002884  jns     short loc_18000289A
0x180002886  xor     r9d, r9d; lpArguments
0x180002889  xor     r8d, r8d; nNumberOfArguments
0x18000288c  mov     edx, 1; dwExceptionFlags
0x180002891  mov     ecx, eax; dwExceptionCode
0x180002893  call    cs:__imp_RaiseException
0x180002899  int     3; Trap to Debugger
0x18000289a  lea     r8, [rsp+178h+var_150]
0x18000289f  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x1800028a6  mov     rcx, [rsp+178h+var_40]
0x1800028ae  call    cs:__imp_RoGetActivationFactory
0x1800028b4  mov     edi, eax
0x1800028b6  test    eax, eax
0x1800028b8  jns     short loc_1800028C9
0x1800028ba  lea     rcx, [rsp+178h+var_150]
0x1800028bf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800028c4  jmp     loc_180002954
0x1800028c9  mov     [rsp+178h+var_158], rbx
0x1800028ce  mov     rdi, [rsp+178h+var_150]
0x1800028d3  lea     rcx, [rsp+178h+var_158]
0x1800028d8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800028dd  lea     r8, [rsp+178h+var_158]
0x1800028e2  lea     rdx, [rsp+178h+var_128]
0x1800028e7  mov     rcx, rdi
0x1800028ea  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPA@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}
0x1800028ef  mov     edi, eax
0x1800028f1  test    eax, eax
0x1800028f3  jns     short loc_18000292F
0x1800028f5  mov     rcx, [rsp+178h+var_158]
0x1800028fa  test    rcx, rcx
0x1800028fd  jz      short loc_180002911
0x1800028ff  mov     [rsp+178h+var_158], rbx
0x180002904  mov     rax, [rcx]
0x180002907  mov     rax, [rax+10h]
0x18000290b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002910  nop
0x180002911  mov     rcx, [rsp+178h+var_150]
0x180002916  test    rcx, rcx
0x180002919  jz      short loc_18000292D
0x18000291b  mov     [rsp+178h+var_150], rbx
0x180002920  mov     rax, [rcx]
0x180002923  mov     rax, [rax+10h]
0x180002927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000292c  nop
0x18000292d  jmp     short loc_180002954
0x18000292f  mov     rax, [rsp+178h+var_158]
0x180002934  mov     [rsp+178h+var_158], rbx
0x180002939  mov     [rsp+178h+var_148], rax
0x18000293e  lea     rcx, [rsp+178h+var_158]
0x180002943  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180002948  lea     rcx, [rsp+178h+var_150]
0x18000294d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180002952  mov     edi, ebx
0x180002954  test    edi, edi
0x180002956  js      loc_180002A0D
0x18000295c  cmp     qword ptr [r15+90h], 0
0x180002964  jz      short loc_180002987
0x180002966  mov     edx, ebx
0x180002968  cmp     edx, [r15+98h]
0x18000296f  jnb     short loc_180002987
0x180002971  mov     ecx, edx
0x180002973  mov     rax, [r15+88h]
0x18000297a  mov     rax, [rax+rcx*8]
0x18000297e  test    rax, rax
0x180002981  jnz     short loc_18000298A
0x180002983  inc     edx
0x180002985  jmp     short loc_180002968
0x180002987  mov     rax, rbx
0x18000298a  mov     [rsp+178h+var_158], rax
0x18000298f  cmp     [rsp+178h+var_158], 0
0x180002995  jz      short loc_1800029EB
0x180002997  lea     rdx, [rsp+178h+var_158]
0x18000299c  lea     rcx, [r15+88h]
0x1800029a3  call    ?GetNextValue@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAUServerRegistrationState@CMediaServerCollectionChangeListener@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@PEAUServerRegistrationState@CMediaServerCollectionChangeListener@@@2@@ATL@@QEAAAEAPEAUServerRegistrationState@CMediaServerCollectionChangeListener@@AEAPEAU__POSITION@@@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CMediaServerCollectionChangeListener::ServerRegistrationState *,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CMediaServerCollectionChangeListener::ServerRegistrationState *>>::GetNextValue(__POSITION * &)
0x1800029a8  mov     rcx, [rax]
0x1800029ab  test    dword ptr [rcx+10h], 0FFFFFFFDh
0x1800029b2  jnz     short loc_18000298F
0x1800029b4  mov     [rsp+178h+var_150], rbx
0x1800029b9  lea     rdx, [rsp+178h+var_150]
0x1800029be  call    ??$CopyTo@UIBasicDevice@Streaming@Media@Windows@@@AgileGitPtr@@QEBAJPEAPEAUIBasicDevice@Streaming@Media@Windows@@@Z; AgileGitPtr::CopyTo<Windows::Media::Streaming::IBasicDevice>(Windows::Media::Streaming::IBasicDevice * *)
0x1800029c3  mov     rdx, [rsp+178h+var_150]
0x1800029c8  test    rdx, rdx
0x1800029cb  jz      short loc_1800029DF
0x1800029cd  mov     rcx, [rsp+178h+var_148]
0x1800029d2  mov     rax, [rcx]
0x1800029d5  mov     rax, [rax+68h]
0x1800029d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029de  nop
0x1800029df  lea     rcx, [rsp+178h+var_150]
0x1800029e4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800029e9  jmp     short loc_18000298F
0x1800029eb  mov     rax, [rsp+178h+var_148]
0x1800029f0  mov     [rsp+178h+var_148], rbx
0x1800029f5  mov     [r12], rax
0x1800029f9  jmp     short loc_180002A0D
0x1800029fb  lea     r14, WPP_GLOBAL_Control
0x180002a02  xor     ebx, ebx
0x180002a04  mov     rsi, [rsp+178h+var_140]
0x180002a09  mov     edi, dword ptr [rsp+178h+var_158]
0x180002a0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a14  cmp     rcx, r14
0x180002a17  jz      short loc_180002A4F
0x180002a19  test    byte ptr [rcx+1Ch], 2
0x180002a1d  jz      short loc_180002A4F
0x180002a1f  mov     edx, 2
0x180002a24  mov     eax, 5
0x180002a29  test    edi, edi
0x180002a2b  cmovns  edx, eax
0x180002a2e  movzx   eax, byte ptr [rcx+19h]
0x180002a32  cmp     eax, edx
0x180002a34  jb      short loc_180002A4F
0x180002a36  mov     edx, 0Ch
0x180002a3b  mov     r9d, edi
0x180002a3e  lea     r8, WPP_843f9b73b5843d1b8d7c57834cd63f0f_Traceguids
0x180002a45  mov     rcx, [rcx+10h]
0x180002a49  call    WPP_SF_d
0x180002a4e  nop
0x180002a4f  mov     rcx, [rsp+178h+var_148]
0x180002a54  test    rcx, rcx
0x180002a57  jz      short loc_180002A6B
0x180002a59  mov     [rsp+178h+var_148], rbx
0x180002a5e  mov     rdx, [rcx]
0x180002a61  mov     rax, [rdx+10h]
0x180002a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a6a  nop
0x180002a6b  mov     rcx, rsi; lpCriticalSection
0x180002a6e  call    cs:__imp_LeaveCriticalSection
0x180002a74  mov     eax, edi
0x180002a76  mov     rcx, [rsp+178h+var_38]
0x180002a7e  xor     rcx, rsp; StackCookie
0x180002a81  call    __security_check_cookie
0x180002a86  mov     rbx, [rsp+178h+arg_10]
0x180002a8e  add     rsp, 150h
0x180002a95  pop     r15
0x180002a97  pop     r14
0x180002a99  pop     r12
0x180002a9b  pop     rdi
0x180002a9c  pop     rsi
0x180002a9d  retn
```
