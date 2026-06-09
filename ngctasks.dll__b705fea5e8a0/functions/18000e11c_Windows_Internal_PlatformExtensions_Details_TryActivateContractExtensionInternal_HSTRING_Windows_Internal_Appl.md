# Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &,void * *)

- ea: `0x18000e11c`
- end: `0x18000e492`
- name: `?TryActivateContractExtensionInternal@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@34@AEBU_GUID@@PEAPEAX@Z`
- size: `886`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f0f4`

## callees

- `0x180006330`
- `0x1800076a4`
- `0x180007f50`
- `0x180008ab0`
- `0x180009088`
- `0x180009698`
- `0x180009894`
- `0x18000c470`
- `0x18000cc34`
- `0x18000d4b8`
- `0x18000e11c`
- `0x18000e750`
- `0x18000e90c`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000e244`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000e244`

## string_xrefs

- `0x18000e19a`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x18000e25e`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x18000e2e1`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x18000e397`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(
        HSTRING a1,
        unsigned int a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned __int16 *v5; // r8
  int v6; // eax
  unsigned int v7; // ebx
  char v8; // di
  unsigned __int64 v9; // rcx
  int v10; // eax
  int v11; // edx
  unsigned int v12; // r8d
  UINT32 v13; // eax
  int ActivationFactory; // eax
  int v15; // eax
  __int64 v16; // rdx
  __int64 (__fastcall *v17)(__int64, HSTRING, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *)); // rdi
  int v18; // eax
  __int64 v19; // rdx
  __int64 (__fastcall *v21)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *)); // rsi
  const struct _GUID *v22; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+20h] [rbp-E0h]
  __int64 (__fastcall ***v24)(_QWORD, GUID *, _QWORD *); // [rsp+30h] [rbp-D0h] BYREF
  __int64 v25; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v26; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v27; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v28; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v29; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING v30[2]; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-90h] BYREF
  __int64 v32; // [rsp+88h] [rbp-78h]
  _QWORD v33[42]; // [rsp+90h] [rbp-70h] BYREF
  HSTRING__ sourceString; // [rsp+1E0h] [rbp+E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  v30[0] = a1;
  v29 = a2;
  Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Start<HSTRING__ * &,Windows::Internal::ApplicationModel::WindowManagement::WindowId &,_GUID const &>(
    v33,
    v30,
    &v29);
  *a4 = 0;
  v6 = Windows::Internal::PlatformExtensions::Details::TryLookupExtensionPointImplementationAcid(
         v30[0],
         &sourceString,
         v5,
         v33[34] + 8LL,
         v22);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23E,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)(unsigned int)v6,
      v23);
LABEL_23:
    Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::~TryActivateContractExtension((Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *)v33);
    return v7;
  }
  v8 = 0;
  if ( LOWORD(sourceString.unused) )
  {
    v25 = 0;
    v27 = 0;
    v9 = -1;
    do
      ++v9;
    while ( *((_WORD *)&sourceString.unused + v9) );
    v10 = ULongLongToUInt(v9, &v27);
    if ( v10 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v10, v11, v12);
      __debugbreak();
    }
    v13 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v27);
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, (PCWSTR)&sourceString, v13, v27);
    ActivationFactory = RoGetActivationFactory(v32, &GUID_00000035_0000_0000_c000_000000000046, &v25);
    v7 = ActivationFactory;
    v32 = 0;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x242,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
        (const char *)(unsigned int)ActivationFactory,
        v23);
LABEL_22:
      ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v25);
      goto LABEL_23;
    }
    v24 = 0;
    v26 = 0;
    if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v25)(
           v25,
           &GUID_da805a35_961f_4194_a4bb_e9e86347d589,
           &v26) < 0 )
    {
      v21 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *)))(*(_QWORD *)v25 + 48LL);
      v24 = 0;
      v18 = v21(v25, &v24);
      v7 = v18;
      if ( v18 < 0 )
      {
        v19 = 592;
        goto LABEL_20;
      }
    }
    else
    {
      v28 = 0;
      v15 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Windows::Internal::ApplicationModel::WindowManagement::WindowId &>(
              &v28,
              &v29);
      v7 = v15;
      if ( v15 < 0 )
      {
        v16 = 587;
LABEL_13:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v16,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
          (const char *)(unsigned int)v15,
          v23);
        ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v28);
LABEL_21:
        ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v26);
        ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>((__int64 *)&v24);
        goto LABEL_22;
      }
      v17 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *)))(*(_QWORD *)v26 + 48LL);
      v24 = 0;
      v15 = v17(v26, v30[0], v28, &v24);
      v7 = v15;
      if ( v15 < 0 )
      {
        v16 = 588;
        goto LABEL_13;
      }
      v8 = 1;
      ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v28);
    }
    if ( v24 )
    {
      v18 = (**v24)(v24, &GUID_dff85587_911b_4c34_abfe_9c21380107da, a4);
      v7 = v18;
      if ( v18 < 0 )
      {
        v19 = 600;
LABEL_20:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v19,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
          (const char *)(unsigned int)v18,
          v23);
        goto LABEL_21;
      }
    }
    ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v26);
    ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>((__int64 *)&v24);
    ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v25);
  }
  Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Stop(
    (Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *)v33,
    *a4 != 0,
    v8,
    (const unsigned __int16 *)&sourceString);
  Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::~TryActivateContractExtension((Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *)v33);
  return 0;
}

```

## disassembly

```asm
0x18000e11c  mov     [rsp-8+arg_10], rbx
0x18000e121  push    rbp
0x18000e122  push    rsi
0x18000e123  push    rdi
0x18000e124  push    r14
0x18000e126  push    r15
0x18000e128  lea     rbp, [rsp-1F0h]
0x18000e130  sub     rsp, 2F0h
0x18000e137  mov     rax, cs:__security_cookie
0x18000e13e  xor     rax, rsp
0x18000e141  mov     [rbp+210h+var_30], rax
0x18000e148  mov     r14, r9
0x18000e14b  mov     [rsp+310h+var_2B0], rcx
0x18000e150  mov     [rsp+310h+var_2B8], edx
0x18000e154  xor     r15d, r15d
0x18000e157  lea     r8, [rsp+310h+var_2B8]
0x18000e15c  lea     rdx, [rsp+310h+var_2B0]
0x18000e161  lea     rcx, [rbp+210h+var_280]
0x18000e165  call    ??$Start@AEAPEAUHSTRING__@@AEAUWindowId@WindowManagement@ApplicationModel@Internal@Windows@@AEBU_GUID@@@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SA?AV012345@AEAPEAUHSTRING__@@AEAUWindowId@WindowManagement@ApplicationModel@45@AEBU_GUID@@@Z; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Start<HSTRING__ * &,Windows::Internal::ApplicationModel::WindowManagement::WindowId &,_GUID const &>(HSTRING__ * &,Windows::Internal::ApplicationModel::WindowManagement::WindowId &,_GUID const &)
0x18000e16a  nop
0x18000e16b  mov     [r14], r15
0x18000e16e  mov     r9, [rbp+210h+var_170]
0x18000e175  add     r9, 8; unsigned __int64
0x18000e179  lea     rdx, [rbp+210h+sourceString]; HSTRING
0x18000e180  mov     rcx, [rsp+310h+var_2B0]; this
0x18000e185  call    ?TryLookupExtensionPointImplementationAcid@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@PEAG_KPEBU_GUID@@@Z; Windows::Internal::PlatformExtensions::Details::TryLookupExtensionPointImplementationAcid(HSTRING__ *,ushort *,unsigned __int64,_GUID const *)
0x18000e18a  mov     ebx, eax
0x18000e18c  test    eax, eax
0x18000e18e  jns     short loc_18000E1B0
0x18000e190  mov     rcx, [rbp+218h]; this
0x18000e197  mov     r9d, eax; char *
0x18000e19a  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18000e1a1  mov     edx, 23Eh; void *
0x18000e1a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e1ab  jmp     loc_18000E3CC
0x18000e1b0  mov     dil, r15b
0x18000e1b3  cmp     word ptr [rbp+210h+sourceString.unused], r15w
0x18000e1bb  jz      loc_18000E447
0x18000e1c1  mov     [rsp+310h+var_2D8], r15
0x18000e1c6  mov     rcx, [rsp+310h+var_2D8]
0x18000e1cb  mov     [rsp+310h+var_2D8], r15
0x18000e1d0  test    rcx, rcx
0x18000e1d3  jz      short loc_18000E1E1
0x18000e1d5  mov     rax, [rcx]
0x18000e1d8  mov     rax, [rax+10h]
0x18000e1dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1e1  mov     [rsp+310h+var_2C8], r15d
0x18000e1e6  lea     rax, [rbp+210h+sourceString]
0x18000e1ed  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000e1f1  inc     rcx; unsigned __int64
0x18000e1f4  cmp     [rax+rcx*2], r15w
0x18000e1f9  jnz     short loc_18000E1F1
0x18000e1fb  lea     rdx, [rsp+310h+var_2C8]; unsigned int *
0x18000e200  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18000e205  test    eax, eax
0x18000e207  jns     short loc_18000E211
0x18000e209  mov     ecx, eax; this
0x18000e20b  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000e210  int     3; Trap to Debugger
0x18000e211  mov     ecx, [rsp+310h+var_2C8]; unsigned int
0x18000e215  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18000e21a  mov     r9d, [rsp+310h+var_2C8]; unsigned int
0x18000e21f  mov     r8d, eax; unsigned int
0x18000e222  lea     rdx, [rbp+210h+sourceString]; sourceString
0x18000e229  lea     rcx, [rsp+310h+hstringHeader]; hstringHeader
0x18000e22e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18000e233  nop
0x18000e234  lea     r8, [rsp+310h+var_2D8]
0x18000e239  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x18000e240  mov     rcx, [rbp+210h+var_288]
0x18000e244  call    cs:__imp_RoGetActivationFactory
0x18000e24a  mov     ebx, eax
0x18000e24c  mov     [rbp+210h+var_288], r15
0x18000e250  test    eax, eax
0x18000e252  jns     short loc_18000E274
0x18000e254  mov     rcx, [rbp+218h]; this
0x18000e25b  mov     r9d, eax; char *
0x18000e25e  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18000e265  mov     edx, 242h; void *
0x18000e26a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e26f  jmp     loc_18000E3C1
0x18000e274  mov     [rsp+310h+var_2E0], r15
0x18000e279  mov     [rsp+310h+var_2D0], r15
0x18000e27e  mov     rcx, [rsp+310h+var_2D0]
0x18000e283  mov     [rsp+310h+var_2D0], r15
0x18000e288  test    rcx, rcx
0x18000e28b  jz      short loc_18000E299
0x18000e28d  mov     rax, [rcx]
0x18000e290  mov     rax, [rax+10h]
0x18000e294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e299  mov     rcx, [rsp+310h+var_2D8]
0x18000e29e  mov     rax, [rcx]
0x18000e2a1  lea     r8, [rsp+310h+var_2D0]
0x18000e2a6  lea     rdx, _GUID_da805a35_961f_4194_a4bb_e9e86347d589
0x18000e2ad  mov     rax, [rax]
0x18000e2b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2b5  test    eax, eax
0x18000e2b7  js      loc_18000E3DC
0x18000e2bd  mov     [rsp+310h+var_2C0], r15
0x18000e2c2  mov     [rsp+310h+var_2C0], r15
0x18000e2c7  lea     rdx, [rsp+310h+var_2B8]
0x18000e2cc  lea     rcx, [rsp+310h+var_2C0]
0x18000e2d1  call    ??$MakeAndInitialize@VActivationFactoryContractRedirectorContext@Details@PlatformExtensions@Internal@Windows@@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@45@AEAUWindowId@WindowManagement@ApplicationModel@45@@Details@WRL@Microsoft@@YAJPEAPEAUIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@AEAUWindowId@WindowManagement@ApplicationModel@67@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Windows::Internal::ApplicationModel::WindowManagement::WindowId &>(Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext * *,Windows::Internal::ApplicationModel::WindowManagement::WindowId &)
0x18000e2d6  mov     ebx, eax
0x18000e2d8  test    eax, eax
0x18000e2da  jns     short loc_18000E307
0x18000e2dc  mov     edx, 24Bh; void *
0x18000e2e1  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18000e2e8  mov     r9d, eax; char *
0x18000e2eb  mov     rcx, [rbp+218h]; this
0x18000e2f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e2f7  nop
0x18000e2f8  lea     rcx, [rsp+310h+var_2C0]
0x18000e2fd  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x18000e302  jmp     loc_18000E3AB
0x18000e307  mov     rbx, [rsp+310h+var_2D0]
0x18000e30c  mov     rax, [rbx]
0x18000e30f  mov     rdi, [rax+30h]
0x18000e313  mov     rcx, [rsp+310h+var_2E0]
0x18000e318  mov     [rsp+310h+var_2E0], r15
0x18000e31d  test    rcx, rcx
0x18000e320  jz      short loc_18000E32E
0x18000e322  mov     r8, [rcx]
0x18000e325  mov     rax, [r8+10h]
0x18000e329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e32e  lea     r9, [rsp+310h+var_2E0]
0x18000e333  mov     r8, [rsp+310h+var_2C0]
0x18000e338  mov     rdx, [rsp+310h+var_2B0]
0x18000e33d  mov     rcx, rbx
0x18000e340  mov     rax, rdi
0x18000e343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e348  mov     ebx, eax
0x18000e34a  test    eax, eax
0x18000e34c  jns     short loc_18000E355
0x18000e34e  mov     edx, 24Ch
0x18000e353  jmp     short loc_18000E2E1
0x18000e355  mov     dil, 1
0x18000e358  lea     rcx, [rsp+310h+var_2C0]
0x18000e35d  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x18000e362  mov     rcx, [rsp+310h+var_2E0]
0x18000e367  test    rcx, rcx
0x18000e36a  jz      loc_18000E427
0x18000e370  mov     rax, [rcx]
0x18000e373  mov     r8, r14
0x18000e376  lea     rdx, _GUID_dff85587_911b_4c34_abfe_9c21380107da
0x18000e37d  mov     rax, [rax]
0x18000e380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e385  mov     ebx, eax
0x18000e387  test    eax, eax
0x18000e389  jns     loc_18000E427
0x18000e38f  mov     edx, 258h; void *
0x18000e394  mov     r9d, eax; char *
0x18000e397  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18000e39e  mov     rcx, [rbp+218h]; this
0x18000e3a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e3aa  nop
0x18000e3ab  lea     rcx, [rsp+310h+var_2D0]
0x18000e3b0  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x18000e3b5  nop
0x18000e3b6  lea     rcx, [rsp+310h+var_2E0]
0x18000e3bb  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x18000e3c0  nop
0x18000e3c1  lea     rcx, [rsp+310h+var_2D8]
0x18000e3c6  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x18000e3cb  nop
0x18000e3cc  lea     rcx, [rbp+210h+var_280]; this
0x18000e3d0  call    ??1TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAA@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::~TryActivateContractExtension(void)
0x18000e3d5  mov     eax, ebx
0x18000e3d7  jmp     loc_18000E46C
0x18000e3dc  mov     rbx, [rsp+310h+var_2D8]
0x18000e3e1  mov     rax, [rbx]
0x18000e3e4  mov     rsi, [rax+30h]
0x18000e3e8  mov     rcx, [rsp+310h+var_2E0]
0x18000e3ed  mov     [rsp+310h+var_2E0], r15
0x18000e3f2  test    rcx, rcx
0x18000e3f5  jz      short loc_18000E403
0x18000e3f7  mov     rdx, [rcx]
0x18000e3fa  mov     rax, [rdx+10h]
0x18000e3fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e403  lea     rdx, [rsp+310h+var_2E0]
0x18000e408  mov     rcx, rbx
0x18000e40b  mov     rax, rsi
0x18000e40e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e413  mov     ebx, eax
0x18000e415  test    eax, eax
0x18000e417  jns     loc_18000E362
0x18000e41d  mov     edx, 250h
0x18000e422  jmp     loc_18000E394
0x18000e427  lea     rcx, [rsp+310h+var_2D0]
0x18000e42c  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x18000e431  nop
0x18000e432  lea     rcx, [rsp+310h+var_2E0]
0x18000e437  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x18000e43c  nop
0x18000e43d  lea     rcx, [rsp+310h+var_2D8]
0x18000e442  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x18000e447  cmp     [r14], r15
0x18000e44a  setnz   dl; bool
0x18000e44d  lea     r9, [rbp+210h+sourceString]; unsigned __int16 *
0x18000e454  mov     r8b, dil; bool
0x18000e457  lea     rcx, [rbp+210h+var_280]; this
0x18000e45b  call    ?Stop@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAX_N0PEBG@Z; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Stop(bool,bool,ushort const *)
0x18000e460  nop
0x18000e461  lea     rcx, [rbp+210h+var_280]; this
0x18000e465  call    ??1TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAA@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::~TryActivateContractExtension(void)
0x18000e46a  xor     eax, eax
0x18000e46c  mov     rcx, [rbp+210h+var_30]
0x18000e473  xor     rcx, rsp; StackCookie
0x18000e476  call    __security_check_cookie
0x18000e47b  mov     rbx, [rsp+310h+arg_10]
0x18000e483  add     rsp, 2F0h
0x18000e48a  pop     r15
0x18000e48c  pop     r14
0x18000e48e  pop     rdi
0x18000e48f  pop     rsi
0x18000e490  pop     rbp
0x18000e491  retn
```
