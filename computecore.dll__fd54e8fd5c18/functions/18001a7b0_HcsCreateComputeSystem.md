# HcsCreateComputeSystem

- ea: `0x18001a7b0`
- end: `0x18001ab64`
- name: `HcsCreateComputeSystem`
- size: `948`
- prototype: `HRESULT __stdcall(PCWSTR id, PCWSTR configuration, HCS_OPERATION operation, const SECURITY_DESCRIPTOR *securityDescriptor, HCS_SYSTEM *computeSystem)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800067c0`
- `0x180007438`
- `0x180009e8c`
- `0x180013de8`
- `0x180013f60`
- `0x180014184`
- `0x1800144a4`
- `0x180014f14`
- `0x180015150`
- `0x18001587c`
- `0x180016524`
- `0x18001a584`
- `0x18001a7b0`
- `0x180036764`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001a8a7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001a8a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001a95f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001a95f`

## string_xrefs

- `0x18001aae3`: `onecore\vm\compute\dll\core\src\system.cpp`
- `0x18001aaf9`: `onecore\vm\compute\dll\core\src\system.cpp`
- `0x18001ab0f`: `onecore\vm\compute\dll\core\src\system.cpp`
- `0x18001ab24`: `onecore\vm\compute\dll\core\src\system.cpp`
- `0x18001ab3c`: `onecore\vm\compute\dll\core\src\system.cpp`
- `0x18001ab51`: `onecore\vm\compute\dll\core\src\system.cpp`
- `0x18001a81e`: `HcsCreateComputeSystem`
- `0x18001a8d7`: `hcs:/VirtualMachine/HandleBrokerManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
HRESULT __stdcall HcsCreateComputeSystem(
        PCWSTR id,
        PCWSTR configuration,
        HCS_OPERATION operation,
        const SECURITY_DESCRIPTOR *securityDescriptor,
        HCS_SYSTEM *computeSystem)
{
  __int64 v9; // rax
  RTL_SRWLOCK *v10; // rdi
  _QWORD *Ptr; // rbx
  _QWORD *v12; // rsi
  const wchar_t *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  int v16; // eax
  volatile signed __int32 *v17; // rbx
  const char *v18; // r9
  HRESULT result; // eax
  unsigned int v20; // eax
  int v21; // edx
  int v22; // [rsp+20h] [rbp-238h]
  __int128 v23; // [rsp+40h] [rbp-218h] BYREF
  __int64 v24; // [rsp+50h] [rbp-208h] BYREF
  __int64 v25; // [rsp+58h] [rbp-200h]
  char v26; // [rsp+60h] [rbp-1F8h]
  _QWORD v27[3]; // [rsp+70h] [rbp-1E8h] BYREF
  __int128 v28; // [rsp+88h] [rbp-1D0h] BYREF
  __int64 v29; // [rsp+98h] [rbp-1C0h]
  _QWORD v30[34]; // [rsp+C0h] [rbp-198h] BYREF
  __int64 v31; // [rsp+1D0h] [rbp-88h]
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  memset_0(v30, 0, 0x150u);
  wil::ActivityBase<ComputeCore::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeCore::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>(v30);
  v30[0] = &ComputeCore::Diagnostics::TraceProvider::HcsClientApi::`vftable';
  try
  {
    ComputeCore::Diagnostics::TraceProvider::HcsClientApi::StartActivity(
      (ComputeCore::Diagnostics::TraceProvider::HcsClientApi *)v30,
      "HcsCreateComputeSystem",
      0);
    if ( !id )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x58,
        (unsigned int)"onecore\\vm\\compute\\dll\\core\\src\\system.cpp",
        (const char *)0x80070057LL,
        v22);
    if ( !configuration )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x59,
        (unsigned int)"onecore\\vm\\compute\\dll\\core\\src\\system.cpp",
        (const char *)0x80070057LL,
        v22);
    if ( !operation )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5A,
        (unsigned int)"onecore\\vm\\compute\\dll\\core\\src\\system.cpp",
        (const char *)0x80070057LL,
        v22);
    if ( securityDescriptor )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5B,
        (unsigned int)"onecore\\vm\\compute\\dll\\core\\src\\system.cpp",
        (const char *)0x80070057LL,
        v22);
    *computeSystem = 0;
    v23 = 0;
    v9 = *((_QWORD *)operation + 1);
    if ( v9 )
      _InterlockedIncrement((volatile signed __int32 *)(v9 + 8));
    v10 = *(RTL_SRWLOCK **)operation;
    *(_QWORD *)&v23 = v10;
    *((_QWORD *)&v23 + 1) = *((_QWORD *)operation + 1);
    AcquireSRWLockShared(v10);
    Ptr = v10[28].Ptr;
    v12 = v10[29].Ptr;
    while ( Ptr != v12 )
    {
      v13 = Ptr[3] <= 7u ? (const wchar_t *)Ptr : (const wchar_t *)*Ptr;
      if ( Ptr[2] == 39 && !wmemcmp(v13, L"hcs:/VirtualMachine/HandleBrokerManager", 0x27u) && *((_BYTE *)Ptr + 40) == 2 )
        break;
      Ptr += 9;
    }
    if ( Ptr == v10[29].Ptr )
    {
      v26 = 0;
    }
    else
    {
      ComputeService::Resources::ClientResource::ClientResource(v27, Ptr);
      if ( (_BYTE)v29 != 2 )
        std::_Throw_bad_variant_access();
      v14 = *((_QWORD *)&v28 + 1);
      *((_QWORD *)&v28 + 1) = 0;
      v25 = v14;
      v26 = 1;
      std::_Variant_destroy_layer_<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,wil::com_ptr_t<IUnknown,wil::err_exception_policy>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>>>::~_Variant_destroy_layer_<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,wil::com_ptr_t<IUnknown,wil::err_exception_policy>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>>>((char *)&v28 + 8);
      std::wstring::~wstring(v27);
    }
    if ( v10 )
      ReleaseSRWLockShared(v10);
    v15 = 0;
    v24 = 0;
    if ( v26 )
    {
      if ( !v25 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x69,
          (unsigned int)"onecore\\vm\\compute\\dll\\core\\src\\system.cpp",
          (const char *)0x80070057LL,
          v22);
      v24 = 0;
      v16 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v25)(
              v25,
              &GUID_3dbe3936_af72_4dbd_b314_f689784f692e,
              &v24);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6A,
          (unsigned int)"onecore\\vm\\compute\\dll\\core\\src\\system.cpp",
          (const char *)(unsigned int)v16,
          v22);
      v15 = v24;
    }
    v27[0] = 0x10000;
    v27[1] = 0;
    v27[2] = 0;
    v28 = 0;
    v29 = 0;
    *computeSystem = (HCS_SYSTEM)HcsClient::CreateComputeSystem(
                                   (int)v31 + 8,
                                   (unsigned int)&ClientCore::g_Server,
                                   (unsigned int)&v23,
                                   (_DWORD)id,
                                   (__int64)configuration,
                                   v15,
                                   0);
    wil::ActivityBase<ComputeCore::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
      v30,
      0);
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v26 && v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v17 = (volatile signed __int32 *)*((_QWORD *)&v23 + 1);
    if ( *((_QWORD *)&v23 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v23 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
        if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
      }
    }
    ComputeCore::Diagnostics::TraceProvider::HcsClientApi::~HcsClientApi((ComputeCore::Diagnostics::TraceProvider::HcsClientApi *)v30);
    result = 0;
  }
  catch ( ... )
  {
    v20 = wil::details::in1diag3::Log_CaughtException(
            retaddr,
            (void *)0x71,
            (unsigned int)"onecore\\vm\\compute\\dll\\core\\src\\system.cpp",
            v18);
    return ClientError::ToV2Result((ClientError *)v20, v21);
  }
  return result;
}

```

## disassembly

```asm
0x18001a7b0  push    rbx
0x18001a7b2  push    rsi
0x18001a7b3  push    rdi
0x18001a7b4  push    r12
0x18001a7b6  push    r13
0x18001a7b8  push    r14
0x18001a7ba  push    r15
0x18001a7bc  sub     rsp, 220h
0x18001a7c3  mov     rax, cs:__security_cookie
0x18001a7ca  xor     rax, rsp
0x18001a7cd  mov     [rsp+258h+var_48], rax
0x18001a7d5  mov     r12, r9
0x18001a7d8  mov     rbx, r8
0x18001a7db  mov     r15, rdx
0x18001a7de  mov     r13, rcx
0x18001a7e1  mov     r14, [rsp+258h+computeSystem]
0x18001a7e9  xor     edx, edx; Val
0x18001a7eb  mov     r8d, 150h; Size
0x18001a7f1  lea     rcx, [rsp+258h+var_198]; void *
0x18001a7f9  call    memset_0
0x18001a7fe  nop
0x18001a7ff  lea     rcx, [rsp+258h+var_198]
0x18001a807  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeCore@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeCore::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeCore::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001a80c  lea     rax, ??_7HcsClientApi@TraceProvider@Diagnostics@ComputeCore@@6B@; const ComputeCore::Diagnostics::TraceProvider::HcsClientApi::`vftable'
0x18001a813  mov     [rsp+258h+var_198], rax
0x18001a81b  xor     r8d, r8d; void *
0x18001a81e  lea     rdx, aHcscreatecompu_2; "HcsCreateComputeSystem"
0x18001a825  lea     rcx, [rsp+258h+var_198]; this
0x18001a82d  call    ?StartActivity@HcsClientApi@TraceProvider@Diagnostics@ComputeCore@@QEAAXPEBDPEAX@Z; ComputeCore::Diagnostics::TraceProvider::HcsClientApi::StartActivity(char const *,void *)
0x18001a832  nop
0x18001a833  mov     rcx, [rsp+258h]; this
0x18001a83b  test    r13, r13
0x18001a83e  jz      loc_18001AADD
0x18001a844  mov     rcx, [rsp+258h]; this
0x18001a84c  test    r15, r15
0x18001a84f  jz      loc_18001AAF3
0x18001a855  mov     rcx, [rsp+258h]; this
0x18001a85d  test    rbx, rbx
0x18001a860  jz      loc_18001AB09
0x18001a866  mov     rcx, [rsp+258h]; this
0x18001a86e  test    r12, r12
0x18001a871  jnz     loc_18001AB1E
0x18001a877  mov     qword ptr [r14], 0
0x18001a87e  xorps   xmm0, xmm0
0x18001a881  movups  [rsp+258h+var_218], xmm0
0x18001a886  mov     rax, [rbx+8]
0x18001a88a  test    rax, rax
0x18001a88d  jz      short loc_18001A893
0x18001a88f  lock inc dword ptr [rax+8]
0x18001a893  mov     rdi, [rbx]
0x18001a896  mov     qword ptr [rsp+258h+var_218], rdi
0x18001a89b  mov     rax, [rbx+8]
0x18001a89f  mov     qword ptr [rsp+258h+var_218+8], rax
0x18001a8a4  mov     rcx, rdi; SRWLock
0x18001a8a7  call    cs:__imp_AcquireSRWLockShared
0x18001a8ad  nop
0x18001a8ae  mov     rbx, [rdi+0E0h]
0x18001a8b5  mov     rsi, [rdi+0E8h]
0x18001a8bc  jmp     short loc_18001A8F1
0x18001a8be  mov     r8, [rbx+10h]; N
0x18001a8c2  cmp     qword ptr [rbx+18h], 7
0x18001a8c7  jbe     short loc_18001A8CE
0x18001a8c9  mov     rcx, [rbx]
0x18001a8cc  jmp     short loc_18001A8D1
0x18001a8ce  mov     rcx, rbx; S1
0x18001a8d1  cmp     r8, 27h ; '''
0x18001a8d5  jnz     short loc_18001A8ED
0x18001a8d7  lea     rdx, aHcsVirtualmach; "hcs:/VirtualMachine/HandleBrokerManager"
0x18001a8de  call    wmemcmp
0x18001a8e3  test    eax, eax
0x18001a8e5  jnz     short loc_18001A8ED
0x18001a8e7  cmp     byte ptr [rbx+28h], 2
0x18001a8eb  jz      short loc_18001A8F6
0x18001a8ed  add     rbx, 48h ; 'H'
0x18001a8f1  cmp     rbx, rsi
0x18001a8f4  jnz     short loc_18001A8BE
0x18001a8f6  cmp     rbx, [rdi+0E8h]
0x18001a8fd  jnz     short loc_18001A908
0x18001a8ff  xor     esi, esi
0x18001a901  mov     [rsp+258h+var_1F8], sil
0x18001a906  jmp     short loc_18001A957
0x18001a908  mov     rdx, rbx
0x18001a90b  lea     rcx, [rsp+258h+var_1E8]
0x18001a910  call    ??0ClientResource@Resources@ComputeService@@QEAA@$$QEAV012@@Z; ComputeService::Resources::ClientResource::ClientResource(ComputeService::Resources::ClientResource &&)
0x18001a915  cmp     byte ptr [rsp+258h+var_1C0], 2
0x18001a91d  jnz     loc_18001AAD7
0x18001a923  mov     rax, [rsp+258h+var_1C8]
0x18001a92b  xor     esi, esi
0x18001a92d  mov     [rsp+258h+var_1C8], rsi
0x18001a935  mov     [rsp+258h+var_200], rax
0x18001a93a  mov     [rsp+258h+var_1F8], 1
0x18001a93f  lea     rcx, [rsp+258h+var_1C8]
0x18001a947  call    ??1?$_Variant_destroy_layer_@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@2@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@2@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?closesocket@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0_K@details@wil@@@details@wil@@@2@@std@@QEAA@XZ; std::_Variant_destroy_layer_<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,wil::com_ptr_t<IUnknown,wil::err_exception_policy>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>>>::~_Variant_destroy_layer_<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,wil::com_ptr_t<IUnknown,wil::err_exception_policy>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>>>(void)
0x18001a94c  lea     rcx, [rsp+258h+var_1E8]
0x18001a951  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001a956  nop
0x18001a957  test    rdi, rdi
0x18001a95a  jz      short loc_18001A966
0x18001a95c  mov     rcx, rdi; SRWLock
0x18001a95f  call    cs:__imp_ReleaseSRWLockShared
0x18001a965  nop
0x18001a966  mov     rax, rsi
0x18001a969  mov     [rsp+258h+var_208], rax
0x18001a96e  cmp     [rsp+258h+var_1F8], sil
0x18001a973  jz      short loc_18001A9BC
0x18001a975  mov     rax, [rsp+258h]
0x18001a97d  mov     rcx, [rsp+258h+var_200]
0x18001a982  test    rcx, rcx
0x18001a985  jz      loc_18001AB36
0x18001a98b  mov     [rsp+258h+var_208], rsi
0x18001a990  mov     rax, [rcx]
0x18001a993  lea     r8, [rsp+258h+var_208]
0x18001a998  lea     rdx, _GUID_3dbe3936_af72_4dbd_b314_f689784f692e
0x18001a99f  mov     rax, [rax]
0x18001a9a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9a7  mov     rcx, [rsp+258h]; this
0x18001a9af  test    eax, eax
0x18001a9b1  js      loc_18001AB4E
0x18001a9b7  mov     rax, [rsp+258h+var_208]
0x18001a9bc  mov     [rsp+258h+var_1E8], 10000h
0x18001a9c5  mov     [rsp+258h+var_1E0], rsi
0x18001a9ca  mov     [rsp+258h+var_1D8], r12
0x18001a9d2  xorps   xmm0, xmm0
0x18001a9d5  xor     ecx, ecx
0x18001a9d7  movups  xmmword ptr [rsp+88h], xmm0
0x18001a9df  mov     [rsp+258h+var_1C0], rcx
0x18001a9e7  mov     rcx, [rsp+258h+var_88]
0x18001a9ef  add     rcx, 8
0x18001a9f3  mov     [rsp+258h+var_228], rsi
0x18001a9f8  mov     [rsp+258h+var_230], rax
0x18001a9fd  mov     [rsp+258h+var_238], r15
0x18001aa02  mov     r9, r13
0x18001aa05  lea     r8, [rsp+258h+var_218]
0x18001aa0a  lea     rdx, ?g_Server@ClientCore@@3V?$shared_ptr@VHcsServer@@@std@@A; std::shared_ptr<HcsServer> ClientCore::g_Server
0x18001aa11  call    ?CreateComputeSystem@HcsClient@@YAPEAUHCS_SYSTEM__@@AEBU_GUID@@AEBV?$shared_ptr@VHcsServer@@@std@@AEBV?$shared_ptr@VClientOperation@@@5@PEBG3PEAUIVmHandleBrokerManager@@PEAXPEBUHCS_CREATE_OPTIONS_1@@@Z; HcsClient::CreateComputeSystem(_GUID const &,std::shared_ptr<HcsServer> const &,std::shared_ptr<ClientOperation> const &,ushort const *,ushort const *,IVmHandleBrokerManager *,void *,HCS_CREATE_OPTIONS_1 const *)
0x18001aa16  mov     [r14], rax
0x18001aa19  xor     edx, edx
0x18001aa1b  lea     rcx, [rsp+258h+var_198]
0x18001aa23  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeCore@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeCore::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001aa28  nop
0x18001aa29  mov     rcx, [rsp+258h+var_208]
0x18001aa2e  test    rcx, rcx
0x18001aa31  jz      short loc_18001AA40
0x18001aa33  mov     rax, [rcx]
0x18001aa36  mov     rax, [rax+10h]
0x18001aa3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa3f  nop
0x18001aa40  cmp     [rsp+258h+var_1F8], sil
0x18001aa45  jz      short loc_18001AA5E
0x18001aa47  mov     rcx, [rsp+258h+var_200]
0x18001aa4c  test    rcx, rcx
0x18001aa4f  jz      short loc_18001AA5E
0x18001aa51  mov     rax, [rcx]
0x18001aa54  mov     rax, [rax+10h]
0x18001aa58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa5d  nop
0x18001aa5e  mov     rbx, qword ptr [rsp+258h+var_218+8]
0x18001aa63  test    rbx, rbx
0x18001aa66  jz      short loc_18001AA9F
0x18001aa68  or      edi, 0FFFFFFFFh
0x18001aa6b  mov     eax, edi
0x18001aa6d  lock xadd [rbx+8], eax
0x18001aa72  add     eax, edi
0x18001aa74  jnz     short loc_18001AA9F
0x18001aa76  mov     rax, [rbx]
0x18001aa79  mov     rcx, rbx
0x18001aa7c  mov     rax, [rax]
0x18001aa7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa84  mov     eax, edi
0x18001aa86  lock xadd [rbx+0Ch], eax
0x18001aa8b  add     eax, edi
0x18001aa8d  jnz     short loc_18001AA9F
0x18001aa8f  mov     rax, [rbx]
0x18001aa92  mov     rcx, rbx
0x18001aa95  mov     rax, [rax+8]
0x18001aa99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa9e  nop
0x18001aa9f  lea     rcx, [rsp+258h+var_198]; this
0x18001aaa7  call    ??1HcsClientApi@TraceProvider@Diagnostics@ComputeCore@@QEAA@XZ; ComputeCore::Diagnostics::TraceProvider::HcsClientApi::~HcsClientApi(void)
0x18001aaac  xor     eax, eax
0x18001aaae  jmp     short loc_18001AAB4
0x18001aab0  mov     eax, dword ptr [rsp+258h+var_208]
0x18001aab4  mov     rcx, [rsp+258h+var_48]
0x18001aabc  xor     rcx, rsp; StackCookie
0x18001aabf  call    __security_check_cookie
0x18001aac4  add     rsp, 220h
0x18001aacb  pop     r15
0x18001aacd  pop     r14
0x18001aacf  pop     r13
0x18001aad1  pop     r12
0x18001aad3  pop     rdi
0x18001aad4  pop     rsi
0x18001aad5  pop     rbx
0x18001aad6  retn
0x18001aad7  call    ?_Throw_bad_variant_access@std@@YAXXZ; std::_Throw_bad_variant_access(void)
0x18001aadd  mov     r9d, 80070057h; char *
0x18001aae3  lea     r8, aOnecoreVmCompu_5; "onecore\\vm\\compute\\dll\\core\\src\\s"...
0x18001aaea  lea     edx, [r13+58h]; void *
0x18001aaee  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001aaf3  mov     r9d, 80070057h; char *
0x18001aaf9  lea     r8, aOnecoreVmCompu_5; "onecore\\vm\\compute\\dll\\core\\src\\s"...
0x18001ab00  lea     edx, [r15+59h]; void *
0x18001ab04  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001ab09  mov     r9d, 80070057h; char *
0x18001ab0f  lea     r8, aOnecoreVmCompu_5; "onecore\\vm\\compute\\dll\\core\\src\\s"...
0x18001ab16  lea     edx, [rbx+5Ah]; void *
0x18001ab19  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001ab1e  mov     r9d, 80070057h; char *
0x18001ab24  lea     r8, aOnecoreVmCompu_5; "onecore\\vm\\compute\\dll\\core\\src\\s"...
0x18001ab2b  mov     edx, 5Bh ; '['; void *
0x18001ab30  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001ab36  mov     r9d, 80070057h; char *
0x18001ab3c  lea     r8, aOnecoreVmCompu_5; "onecore\\vm\\compute\\dll\\core\\src\\s"...
0x18001ab43  lea     edx, [rcx+69h]; void *
0x18001ab46  mov     rcx, rax; this
0x18001ab49  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001ab4e  mov     r9d, eax; char *
0x18001ab51  lea     r8, aOnecoreVmCompu_5; "onecore\\vm\\compute\\dll\\core\\src\\s"...
0x18001ab58  mov     edx, 6Ah ; 'j'; void *
0x18001ab5d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
