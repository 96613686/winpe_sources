# CloudExperienceHostAPI::OobeRegionManagerStaticsCore::CommitRegionAsync(HSTRING__ *,CloudExperienceHostAPI::IOobeRegionCommitSideEffects * *,Windows::Foundation::IAsyncAction * *)

- ea: `0x18004ae30`
- end: `0x18004b06e`
- name: `?CommitRegionAsync@OobeRegionManagerStaticsCore@CloudExperienceHostAPI@@UEAAJPEAUHSTRING__@@PEAPEAUIOobeRegionCommitSideEffects@2@PEAPEAUIAsyncAction@Foundation@Windows@@@Z`
- size: `574`
- prototype: `__int64 __fastcall(CloudExperienceHostAPI::OobeRegionManagerStaticsCore *__hidden this, HSTRING, struct CloudExperienceHostAPI::IOobeRegionCommitSideEffects **, struct Windows::Foundation::IAsyncAction **)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800076d4`
- `0x18000b7f8`
- `0x18000b9b8`
- `0x18000bc70`
- `0x18000d664`
- `0x18001dd10`
- `0x1800291d0`
- `0x180029224`
- `0x18002e9a8`
- `0x1800365a4`
- `0x180049d80`
- `0x180049f48`
- `0x18004a024`
- `0x18004a624`
- `0x18004a858`
- `0x18004ae30`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004af0c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004af0c`

## string_xrefs

- `0x18004aeb5`: `shellcommon\shell\oobe\core\components\winrt\ooberegioncore.cpp`
- `0x18004aeeb`: `shellcommon\shell\oobe\core\components\winrt\ooberegioncore.cpp`
- `0x18004af4c`: `shellcommon\shell\oobe\core\components\winrt\ooberegioncore.cpp`
- `0x18004afea`: `shellcommon\shell\oobe\core\components\winrt\ooberegioncore.cpp`
- `0x18004ae67`: `CloudExperienceHostAPI::OobeRegionManagerStaticsCore::CommitRegionAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CloudExperienceHostAPI::OobeRegionManagerStaticsCore::CommitRegionAsync(
        CloudExperienceHostAPI::OobeRegionManagerStaticsCore *this,
        HSTRING a2,
        RTL_SRWLOCK **a3,
        struct Windows::Foundation::IAsyncAction **a4)
{
  __int64 v8; // rcx
  CloudExperienceHostCoreTelemetry *v9; // rcx
  RTL_SRWLOCK *v10; // rbx
  PVOID Ptr; // rcx
  int v12; // eax
  unsigned int v13; // ebx
  int v15; // eax
  unsigned int v16; // edi
  RTL_SRWLOCK *v17; // r15
  RTL_SRWLOCK *v18; // rdi
  __int64 v19; // rdi
  int v20; // eax
  int v21; // esi
  __int64 v22; // rax
  int v23; // r8d
  int v24; // r9d
  int v25; // ebx
  int v26; // [rsp+20h] [rbp-30h]
  int v27; // [rsp+20h] [rbp-30h]
  int v28; // [rsp+30h] [rbp-20h] BYREF
  __int64 v29; // [rsp+34h] [rbp-1Ch]
  RTL_SRWLOCK *v30; // [rsp+40h] [rbp-10h] BYREF
  __int64 v31; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  RTL_SRWLOCK *v33; // [rsp+90h] [rbp+40h] BYREF
  HSTRING v34; // [rsp+98h] [rbp+48h] BYREF
  RTL_SRWLOCK *v35; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v36; // [rsp+A8h] [rbp+58h] BYREF

  v34 = a2;
  if ( CloudExperienceHostCoreTelemetry::IsEnabled((unsigned __int8)this, (unsigned __int64)a2) )
  {
    wil::details::static_lazy<CloudExperienceHostCoreTelemetry>::get(
      v8,
      _lambda_5eb5719585a1dfff1c0403c1b5c6f80a_::_lambda_invoker_cdecl_);
    CloudExperienceHostCoreTelemetry::GlobalizationState_(
      v9,
      "CloudExperienceHostAPI::OobeRegionManagerStaticsCore::CommitRegionAsync");
  }
  *a3 = 0;
  *a4 = 0;
  v10 = (RTL_SRWLOCK *)((char *)this - 40);
  Ptr = v10[14].Ptr;
  if ( Ptr )
  {
    v12 = (*(__int64 (__fastcall **)(PVOID, HSTRING, RTL_SRWLOCK **, struct Windows::Foundation::IAsyncAction **))(*(_QWORD *)Ptr + 64LL))(
            Ptr,
            a2,
            a3,
            a4);
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7A,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\ooberegioncore.cpp",
        (const char *)(unsigned int)v12,
        v26);
      return v13;
    }
    return 0;
  }
  v33 = 0;
  v15 = Microsoft::WRL::Details::MakeAndInitialize<CloudExperienceHostAPI::OobeRegionCommitSideEffectsCore,CloudExperienceHostAPI::OobeRegionCommitSideEffectsCore,>(&v33);
  v16 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7F,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\ooberegioncore.cpp",
      (const char *)(unsigned int)v15,
      v26);
LABEL_20:
    wil::com_ptr_t<CloudExperienceHostAPI::OobeLanguageCommitSideEffectsCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::OobeLanguageCommitSideEffectsCore,wil::err_exception_policy>(&v33);
    return v16;
  }
  v17 = v33;
  v18 = v33 + 8;
  AcquireSRWLockExclusive(v33 + 8);
  v35 = v18;
  LOBYTE(v17[9].Ptr) = 0;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v35);
  CreateRefCountedObj<Windows::Internal::String,>(&v36);
  v19 = v36;
  v20 = Windows::Internal::String::Initialize((Windows::Internal::String *)(v36 + 8), &v34);
  v21 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x85,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\ooberegioncore.cpp",
      (const char *)(unsigned int)v20,
      v26);
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v16 = v21;
    goto LABEL_20;
  }
  v35 = v10;
  if ( v10 )
    Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,CloudExperienceHostAPI::IOobeKeyboardStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef(v10);
  v30 = v10;
  if ( v10 )
    Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,CloudExperienceHostAPI::IOobeKeyboardStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef(v10);
  v31 = v19;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v31);
  v28 = 3;
  v29 = 128;
  v22 = Windows::Internal::MakeOpLambda<0,Windows::Internal::CNoResult,_lambda_6658699827db7a0337740138d9b84c42_,>(&v30);
  v25 = Windows::Internal::MakeAsyncHelper<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,Windows::Internal::CNoResult,Windows::Internal::ComTaskPoolHandler,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CloudExperienceHostAPI::CommitRegionAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(
          (_DWORD)a4,
          (unsigned int)&v28,
          v23,
          v24,
          v22);
  _lambda_6658699827db7a0337740138d9b84c42_::~_lambda_6658699827db7a0337740138d9b84c42_((_lambda_6658699827db7a0337740138d9b84c42_ *)&v30);
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBF,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\ooberegioncore.cpp",
      (const char *)(unsigned int)v25,
      v27);
    wil::com_ptr_t<CloudExperienceHostAPI::OobeRegionManagerStaticsCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::OobeRegionManagerStaticsCore,wil::err_exception_policy>(&v35);
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v16 = v25;
    goto LABEL_20;
  }
  v33 = 0;
  *a3 = v17;
  wil::com_ptr_t<CloudExperienceHostAPI::OobeRegionManagerStaticsCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::OobeRegionManagerStaticsCore,wil::err_exception_policy>(&v35);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  wil::com_ptr_t<CloudExperienceHostAPI::OobeLanguageCommitSideEffectsCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::OobeLanguageCommitSideEffectsCore,wil::err_exception_policy>(&v33);
  return 0;
}

```

## disassembly

```asm
0x18004ae30  mov     [rsp-38h+arg_8], rdx
0x18004ae35  push    rbp
0x18004ae36  push    rbx
0x18004ae37  push    rsi
0x18004ae38  push    rdi
0x18004ae39  push    r12
0x18004ae3b  push    r14
0x18004ae3d  push    r15
0x18004ae3f  mov     rbp, rsp
0x18004ae42  sub     rsp, 50h
0x18004ae46  mov     r12, r9
0x18004ae49  mov     r14, r8
0x18004ae4c  mov     rdi, rdx
0x18004ae4f  mov     rbx, rcx
0x18004ae52  call    ?IsEnabled@CloudExperienceHostCoreTelemetry@@SA_NE_K@Z; CloudExperienceHostCoreTelemetry::IsEnabled(uchar,unsigned __int64)
0x18004ae57  test    al, al
0x18004ae59  jz      short loc_18004AE73
0x18004ae5b  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5eb5719585a1dfff1c0403c1b5c6f80a_@@CA@XZ; _lambda_5eb5719585a1dfff1c0403c1b5c6f80a_::_lambda_invoker_cdecl_(void)
0x18004ae62  call    ?get@?$static_lazy@VCloudExperienceHostCoreTelemetry@@@details@wil@@QEAAPEAVCloudExperienceHostCoreTelemetry@@P6AXXZ@Z; wil::details::static_lazy<CloudExperienceHostCoreTelemetry>::get(void (*)(void))
0x18004ae67  lea     rdx, aCloudexperienc_31; "CloudExperienceHostAPI::OobeRegionManag"...
0x18004ae6e  call    ?GlobalizationState_@CloudExperienceHostCoreTelemetry@@QEAAXPEBD@Z; CloudExperienceHostCoreTelemetry::GlobalizationState_(char const *)
0x18004ae73  mov     qword ptr [r14], 0
0x18004ae7a  mov     qword ptr [r12], 0
0x18004ae82  add     rbx, 0FFFFFFFFFFFFFFD8h
0x18004ae86  mov     rcx, [rbx+70h]
0x18004ae8a  test    rcx, rcx
0x18004ae8d  jz      short loc_18004AECD
0x18004ae8f  mov     rax, [rcx]
0x18004ae92  mov     r9, r12
0x18004ae95  mov     r8, r14
0x18004ae98  mov     rdx, rdi
0x18004ae9b  mov     rax, [rax+40h]
0x18004ae9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aea4  mov     ebx, eax
0x18004aea6  test    eax, eax
0x18004aea8  jns     loc_18004B05D
0x18004aeae  mov     rcx, [rbp+38h]; this
0x18004aeb2  mov     r9d, eax; char *
0x18004aeb5  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\oobe\\core\\compone"...
0x18004aebc  mov     edx, 7Ah ; 'z'; void *
0x18004aec1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004aec6  mov     eax, ebx
0x18004aec8  jmp     loc_18004B05F
0x18004aecd  mov     [rbp+arg_0], 0
0x18004aed5  lea     rcx, [rbp+arg_0]
0x18004aed9  call    ??$MakeAndInitialize@VOobeRegionCommitSideEffectsCore@CloudExperienceHostAPI@@V12@$$V@Details@WRL@Microsoft@@YAJPEAPEAVOobeRegionCommitSideEffectsCore@CloudExperienceHostAPI@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CloudExperienceHostAPI::OobeRegionCommitSideEffectsCore,CloudExperienceHostAPI::OobeRegionCommitSideEffectsCore,>(CloudExperienceHostAPI::OobeRegionCommitSideEffectsCore * *)
0x18004aede  mov     edi, eax
0x18004aee0  test    eax, eax
0x18004aee2  jns     short loc_18004AF01
0x18004aee4  mov     rcx, [rbp+38h]; this
0x18004aee8  mov     r9d, eax; char *
0x18004aeeb  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\oobe\\core\\compone"...
0x18004aef2  mov     edx, 7Fh; void *
0x18004aef7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004aefc  jmp     loc_18004B01D
0x18004af01  mov     r15, [rbp+arg_0]
0x18004af05  lea     rdi, [r15+40h]
0x18004af09  mov     rcx, rdi; SRWLock
0x18004af0c  call    cs:__imp_AcquireSRWLockExclusive
0x18004af12  mov     [rbp+arg_10], rdi
0x18004af16  mov     byte ptr [r15+48h], 0
0x18004af1b  lea     rcx, [rbp+arg_10]
0x18004af1f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18004af24  lea     rcx, [rbp+arg_18]
0x18004af28  call    ??$CreateRefCountedObj@VString@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VString@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::String,>(void)
0x18004af2d  nop
0x18004af2e  mov     rdi, [rbp+arg_18]
0x18004af32  lea     rcx, [rdi+8]; this
0x18004af36  lea     rdx, [rbp+arg_8]; HSTRING *
0x18004af3a  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x18004af3f  mov     esi, eax
0x18004af41  test    eax, eax
0x18004af43  jns     short loc_18004AF7A
0x18004af45  mov     rcx, [rbp+38h]; this
0x18004af49  mov     r9d, eax; char *
0x18004af4c  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\oobe\\core\\compone"...
0x18004af53  mov     edx, 85h; void *
0x18004af58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004af5d  nop
0x18004af5e  test    rdi, rdi
0x18004af61  jz      short loc_18004AF73
0x18004af63  mov     rax, [rdi]
0x18004af66  mov     rcx, rdi
0x18004af69  mov     rax, [rax+10h]
0x18004af6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004af72  nop
0x18004af73  mov     edi, esi
0x18004af75  jmp     loc_18004B01D
0x18004af7a  mov     [rbp+arg_10], rbx
0x18004af7e  test    rbx, rbx
0x18004af81  jz      short loc_18004AF8C
0x18004af83  mov     rcx, rbx
0x18004af86  call    ?AddRef@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIOobeKeyboardStatics@CloudExperienceHostAPI@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,CloudExperienceHostAPI::IOobeKeyboardStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef(void)
0x18004af8b  nop
0x18004af8c  mov     [rbp+var_10], rbx
0x18004af90  test    rbx, rbx
0x18004af93  jz      short loc_18004AF9D
0x18004af95  mov     rcx, rbx
0x18004af98  call    ?AddRef@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIOobeKeyboardStatics@CloudExperienceHostAPI@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,CloudExperienceHostAPI::IOobeKeyboardStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef(void)
0x18004af9d  mov     [rbp+var_8], rdi
0x18004afa1  lea     rcx, [rbp+var_8]
0x18004afa5  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x18004afaa  nop
0x18004afab  mov     [rbp+var_20], 3
0x18004afb2  mov     [rbp+var_1C], 80h
0x18004afba  lea     rcx, [rbp+var_10]
0x18004afbe  call    ??$MakeOpLambda@$0A@VCNoResult@Internal@Windows@@V_lambda_6658699827db7a0337740138d9b84c42_@@$$V@Internal@Windows@@YAPEAV?$AsyncCallbackBase@VCNoResult@Internal@Windows@@@01@$$QEAV_lambda_6658699827db7a0337740138d9b84c42_@@@Z; Windows::Internal::MakeOpLambda<0,Windows::Internal::CNoResult,_lambda_6658699827db7a0337740138d9b84c42_,>(_lambda_6658699827db7a0337740138d9b84c42_ &&)
0x18004afc3  mov     qword ptr [rsp+50h+var_30], rax; int
0x18004afc8  lea     rdx, [rbp+var_20]
0x18004afcc  mov     rcx, r12
0x18004afcf  call    ??$MakeAsyncHelper@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@UINilDelegate@Internal@3@VCNoResult@63@VComTaskPoolHandler@63@U?$AsyncCausalityOptions@$1?CommitRegionAsyncActionName@CloudExperienceHostAPI@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@YAJPEAPEAUIAsyncAction@Foundation@1@$$QEAVComTaskPoolHandler@01@QEBGW4TrustLevel@@PEAV?$AsyncCallbackBase@VCNoResult@Internal@Windows@@@01@@Z; Windows::Internal::MakeAsyncHelper<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,Windows::Internal::CNoResult,Windows::Internal::ComTaskPoolHandler,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostAPI::CommitRegionAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(Windows::Foundation::IAsyncAction * *,Windows::Internal::ComTaskPoolHandler &&,ushort const * const,TrustLevel,Windows::Internal::AsyncCallbackBase<Windows::Internal::CNoResult> *)
0x18004afd4  mov     ebx, eax
0x18004afd6  lea     rcx, [rbp+var_10]; this
0x18004afda  call    ??1_lambda_6658699827db7a0337740138d9b84c42_@@QEAA@XZ; _lambda_6658699827db7a0337740138d9b84c42_::~_lambda_6658699827db7a0337740138d9b84c42_(void)
0x18004afdf  test    ebx, ebx
0x18004afe1  jns     short loc_18004B02A
0x18004afe3  mov     rcx, [rbp+38h]; this
0x18004afe7  mov     r9d, ebx; char *
0x18004afea  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\oobe\\core\\compone"...
0x18004aff1  mov     edx, 0BFh; void *
0x18004aff6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004affb  nop
0x18004affc  lea     rcx, [rbp+arg_10]
0x18004b000  call    ??1?$com_ptr_t@VOobeRegionManagerStaticsCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::OobeRegionManagerStaticsCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::OobeRegionManagerStaticsCore,wil::err_exception_policy>(void)
0x18004b005  nop
0x18004b006  test    rdi, rdi
0x18004b009  jz      short loc_18004B01B
0x18004b00b  mov     rax, [rdi]
0x18004b00e  mov     rcx, rdi
0x18004b011  mov     rax, [rax+10h]
0x18004b015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b01a  nop
0x18004b01b  mov     edi, ebx
0x18004b01d  lea     rcx, [rbp+arg_0]
0x18004b021  call    ??1?$com_ptr_t@VOobeLanguageCommitSideEffectsCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::OobeLanguageCommitSideEffectsCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::OobeLanguageCommitSideEffectsCore,wil::err_exception_policy>(void)
0x18004b026  mov     eax, edi
0x18004b028  jmp     short loc_18004B05F
0x18004b02a  mov     [rbp+arg_0], 0
0x18004b032  mov     [r14], r15
0x18004b035  lea     rcx, [rbp+arg_10]
0x18004b039  call    ??1?$com_ptr_t@VOobeRegionManagerStaticsCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::OobeRegionManagerStaticsCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::OobeRegionManagerStaticsCore,wil::err_exception_policy>(void)
0x18004b03e  nop
0x18004b03f  test    rdi, rdi
0x18004b042  jz      short loc_18004B054
0x18004b044  mov     rax, [rdi]
0x18004b047  mov     rcx, rdi
0x18004b04a  mov     rax, [rax+10h]
0x18004b04e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b053  nop
0x18004b054  lea     rcx, [rbp+arg_0]
0x18004b058  call    ??1?$com_ptr_t@VOobeLanguageCommitSideEffectsCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::OobeLanguageCommitSideEffectsCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::OobeLanguageCommitSideEffectsCore,wil::err_exception_policy>(void)
0x18004b05d  xor     eax, eax
0x18004b05f  add     rsp, 50h
0x18004b063  pop     r15
0x18004b065  pop     r14
0x18004b067  pop     r12
0x18004b069  pop     rdi
0x18004b06a  pop     rsi
0x18004b06b  pop     rbx
0x18004b06c  pop     rbp
0x18004b06d  retn
```
