# DAS::DevnodeManagment::Devnode::Create(ushort const *,ushort const *,_SW_DEVICE_CREATE_INFO const *,ulong,_DEVPROPERTY *,DAS::DevnodeManagment::Devnode * *)

- ea: `0x18005d7b0`
- end: `0x18005db84`
- name: `?Create@Devnode@DevnodeManagment@DAS@@SAJPEBG0PEBU_SW_DEVICE_CREATE_INFO@@KPEAU_DEVPROPERTY@@PEAPEAV123@@Z`
- size: `980`
- prototype: `__int64 __fastcall(unsigned __int16 *, const unsigned __int16 *, const struct _SW_DEVICE_CREATE_INFO *, unsigned int, struct _DEVPROPERTY *, struct DAS::DevnodeManagment::Devnode **)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800292d0`

## callees

- `0x180005798`
- `0x1800074c0`
- `0x180015b64`
- `0x1800186ac`
- `0x180018ed4`
- `0x180019c38`
- `0x18001aa8c`
- `0x18001eae0`
- `0x1800263f4`
- `0x180028810`
- `0x18002a948`
- `0x18002aa34`
- `0x18002e0bc`
- `0x18005d6b8`
- `0x18005d7b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005d82c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005d82c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005d9f9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005d9f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005da0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005da0e`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18005d9a2`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18005d9a2`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18005d955`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18005d955`

## string_xrefs

- `0x18005d84f`: `onecore\base\devices\association\service\lib\devnode.cpp`
- `0x18005d8a7`: `onecore\base\devices\association\service\lib\devnode.cpp`
- `0x18005d906`: `onecore\base\devices\association\service\lib\devnode.cpp`
- `0x18005d9b9`: `onecore\base\devices\association\service\lib\devnode.cpp`
- `0x18005da42`: `onecore\base\devices\association\service\lib\devnode.cpp`
- `0x18005da94`: `onecore\base\devices\association\service\lib\devnode.cpp`
- `0x18005dae9`: `onecore\base\devices\association\service\lib\devnode.cpp`

## pseudocode

```c
__int64 __fastcall DAS::DevnodeManagment::Devnode::Create(
        unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const struct _SW_DEVICE_CREATE_INFO *a3,
        unsigned int a4,
        struct _DEVPROPERTY *a5,
        struct DAS::DevnodeManagment::Devnode **a6)
{
  HANDLE EventW; // rax
  const char *v11; // r9
  unsigned int LastError; // ebx
  struct DAS::DevnodeManagment::Devnode *v14; // rbx
  int ProviderNameFromAepId_0; // eax
  unsigned int v16; // edi
  __int64 v17; // rdi
  int v18; // eax
  unsigned int v19; // edi
  DWORD v20; // eax
  signed int v21; // eax
  unsigned int v22; // edi
  unsigned int v23; // edi
  __int64 v24; // rdx
  int v25; // [rsp+20h] [rbp-78h]
  int v26; // [rsp+20h] [rbp-78h]
  void *v27; // [rsp+40h] [rbp-58h] BYREF
  struct DAS::DevnodeManagment::Devnode *v28; // [rsp+48h] [rbp-50h] BYREF
  char v29[8]; // [rsp+50h] [rbp-48h] BYREF
  HANDLE hHandle; // [rsp+58h] [rbp-40h] BYREF
  char *v31; // [rsp+60h] [rbp-38h]
  __int64 v32; // [rsp+68h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  unsigned __int16 *v34; // [rsp+A0h] [rbp+8h] BYREF
  const unsigned __int16 *v35; // [rsp+A8h] [rbp+10h] BYREF

  v35 = a2;
  v34 = a1;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (int)a2,
      (int)a3,
      10,
      &WPP_6145e26e73fa3a77c35312157a275b6e_Traceguids,
      (__int64)a1,
      (__int64)a2);
  hHandle = 0;
  v32 = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &hHandle,
    EventW);
  if ( !hHandle )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x75,
                  (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnode.cpp",
                  v11);
    DAS::DevnodeManagment::_swd_callback_data::~_swd_callback_data((DAS::DevnodeManagment::_swd_callback_data *)&hHandle);
    return LastError;
  }
  Microsoft::WRL::Details::Make<DAS::DevnodeManagment::Devnode,unsigned short const * &,unsigned short const * &>(
    &v28,
    (__int64 *)&v34,
    (__int64 *)&v35);
  v14 = v28;
  if ( !v28 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x77,
      (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnode.cpp",
      (const char *)0x8007000ELL,
      v25);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
    DAS::DevnodeManagment::_swd_callback_data::~_swd_callback_data((DAS::DevnodeManagment::_swd_callback_data *)&hHandle);
    return 2147942414LL;
  }
  v27 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v27,
    0);
  ProviderNameFromAepId_0 = DafGetProviderNameFromAepId_0(a1);
  v16 = ProviderNameFromAepId_0;
  if ( ProviderNameFromAepId_0 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnode.cpp",
      (const char *)(unsigned int)ProviderNameFromAepId_0,
      v25);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
    DAS::DevnodeManagment::_swd_callback_data::~_swd_callback_data((DAS::DevnodeManagment::_swd_callback_data *)&hHandle);
    return v16;
  }
  v17 = *((_QWORD *)v14 + 11);
  if ( v17 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v29);
    SwDeviceClose(v17);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v29);
  }
  *((_QWORD *)v14 + 11) = 0;
  v26 = (int)a5;
  v18 = SwDeviceCreate(v27, a2, a3, a4);
  v19 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x82,
      (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnode.cpp",
      (const char *)(unsigned int)v18,
      v26);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
    DAS::DevnodeManagment::_swd_callback_data::~_swd_callback_data((DAS::DevnodeManagment::_swd_callback_data *)&hHandle);
    return v19;
  }
  v20 = WaitForSingleObject(hHandle, 0xEA60u);
  if ( v20 )
  {
    if ( v20 == 258 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x8C,
        (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnode.cpp",
        (const char *)0x800705B4LL,
        (int)"waiting for device creation timed out",
        (const char *)DAS::DevnodeManagment::SwdCallback);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
      DAS::DevnodeManagment::_swd_callback_data::~_swd_callback_data((DAS::DevnodeManagment::_swd_callback_data *)&hHandle);
      return 2147943860LL;
    }
    v21 = GetLastError();
    v22 = v21;
    if ( v21 > 0 )
      v22 = (unsigned __int16)v21 | 0x80070000;
    if ( (v22 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x90,
        (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnode.cpp",
        (const char *)v22,
        (int)"waiting for device creation failed for some unexpected reason",
        (const char *)DAS::DevnodeManagment::SwdCallback);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
      DAS::DevnodeManagment::_swd_callback_data::~_swd_callback_data((DAS::DevnodeManagment::_swd_callback_data *)&hHandle);
      return v22;
    }
  }
  else
  {
    v23 = (unsigned int)v31;
    if ( (int)v31 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x87,
        (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnode.cpp",
        (const char *)(unsigned int)v31,
        (int)"device creation was unsuccessful",
        (const char *)DAS::DevnodeManagment::SwdCallback);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
      DAS::DevnodeManagment::_swd_callback_data::~_swd_callback_data((DAS::DevnodeManagment::_swd_callback_data *)&hHandle);
      return v23;
    }
    v24 = v32;
    v32 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      (char *)v14 + 16,
      v24);
  }
  Microsoft::WRL::ComPtr<DAS::DevnodeManagment::DevnodeFactory>::InternalAddRef(&v28);
  *a6 = v14;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
  DAS::DevnodeManagment::_swd_callback_data::~_swd_callback_data((DAS::DevnodeManagment::_swd_callback_data *)&hHandle);
  return 0;
}

```

## disassembly

```asm
0x18005d7b0  mov     r11, rsp
0x18005d7b3  mov     [r11+18h], rbx
0x18005d7b7  mov     [r11+10h], rdx
0x18005d7bb  mov     [r11+8], rcx
0x18005d7bf  push    rsi
0x18005d7c0  push    rdi
0x18005d7c1  push    r12
0x18005d7c3  push    r14
0x18005d7c5  push    r15
0x18005d7c7  sub     rsp, 70h
0x18005d7cb  mov     r15d, r9d
0x18005d7ce  mov     r12, r8
0x18005d7d1  mov     r14, rdx
0x18005d7d4  mov     rdi, rcx
0x18005d7d7  lea     rax, WPP_RECORDER_INITIALIZED
0x18005d7de  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005d7e5  jz      short loc_18005D810
0x18005d7e7  mov     r9d, 0Ah; int
0x18005d7ed  mov     [r11-68h], rdx
0x18005d7f1  mov     [r11-70h], rcx
0x18005d7f5  lea     rax, WPP_6145e26e73fa3a77c35312157a275b6e_Traceguids
0x18005d7fc  mov     [r11-78h], rax
0x18005d800  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d807  mov     rcx, [rcx+28h]; int
0x18005d80b  call    WPP_RECORDER_SF_SS
0x18005d810  mov     [rsp+98h+hHandle], 0
0x18005d819  mov     [rsp+98h+var_30], 0
0x18005d822  xor     r9d, r9d; lpName
0x18005d825  xor     r8d, r8d; bInitialState
0x18005d828  xor     edx, edx; bManualReset
0x18005d82a  xor     ecx, ecx; lpEventAttributes
0x18005d82c  call    cs:__imp_CreateEventW
0x18005d832  mov     rdx, rax
0x18005d835  lea     rcx, [rsp+98h+hHandle]
0x18005d83a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18005d83f  cmp     [rsp+98h+hHandle], 0
0x18005d845  jnz     short loc_18005D873
0x18005d847  mov     rcx, [rsp+98h]; this
0x18005d84f  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\association\\se"...
0x18005d856  mov     edx, 75h ; 'u'; void *
0x18005d85b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005d860  mov     ebx, eax
0x18005d862  lea     rcx, [rsp+98h+hHandle]; this
0x18005d867  call    ??1_swd_callback_data@DevnodeManagment@DAS@@QEAA@XZ; DAS::DevnodeManagment::_swd_callback_data::~_swd_callback_data(void)
0x18005d86c  mov     eax, ebx
0x18005d86e  jmp     loc_18005DB6E
0x18005d873  lea     r8, [rsp+98h+arg_8]
0x18005d87b  lea     rdx, [rsp+98h+arg_0]
0x18005d883  lea     rcx, [rsp+98h+var_50]
0x18005d888  call    ??$Make@VDevnode@DevnodeManagment@DAS@@AEAPEBGAEAPEBG@Details@WRL@Microsoft@@YA?AV?$ComPtr@VDevnode@DevnodeManagment@DAS@@@12@AEAPEBG0@Z; Microsoft::WRL::Details::Make<DAS::DevnodeManagment::Devnode,ushort const * &,ushort const * &>(ushort const * &,ushort const * &)
0x18005d88d  mov     rbx, [rsp+98h+var_50]
0x18005d892  test    rbx, rbx
0x18005d895  jnz     short loc_18005D8D3
0x18005d897  mov     rcx, [rsp+98h]; this
0x18005d89f  mov     ebx, 8007000Eh
0x18005d8a4  mov     r9d, ebx; char *
0x18005d8a7  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\association\\se"...
0x18005d8ae  mov     edx, 77h ; 'w'; void *
0x18005d8b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d8b8  lea     rcx, [rsp+98h+var_50]
0x18005d8bd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005d8c2  lea     rcx, [rsp+98h+hHandle]; this
0x18005d8c7  call    ??1_swd_callback_data@DevnodeManagment@DAS@@QEAA@XZ; DAS::DevnodeManagment::_swd_callback_data::~_swd_callback_data(void)
0x18005d8cc  mov     eax, ebx
0x18005d8ce  jmp     loc_18005DB6E
0x18005d8d3  mov     [rsp+98h+var_58], 0
0x18005d8dc  xor     edx, edx
0x18005d8de  lea     rcx, [rsp+98h+var_58]
0x18005d8e3  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18005d8e8  lea     rdx, [rsp+98h+var_58]
0x18005d8ed  mov     rcx, rdi; unsigned __int16 *
0x18005d8f0  call    DafGetProviderNameFromAepId_0
0x18005d8f5  mov     edi, eax
0x18005d8f7  test    eax, eax
0x18005d8f9  jns     short loc_18005D93C
0x18005d8fb  mov     rcx, [rsp+98h]; this
0x18005d903  mov     r9d, eax; char *
0x18005d906  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\association\\se"...
0x18005d90d  mov     edx, 79h ; 'y'; void *
0x18005d912  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d917  lea     rcx, [rsp+98h+var_58]
0x18005d91c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005d921  lea     rcx, [rsp+98h+var_50]
0x18005d926  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005d92b  lea     rcx, [rsp+98h+hHandle]; this
0x18005d930  call    ??1_swd_callback_data@DevnodeManagment@DAS@@QEAA@XZ; DAS::DevnodeManagment::_swd_callback_data::~_swd_callback_data(void)
0x18005d935  mov     eax, edi
0x18005d937  jmp     loc_18005DB6E
0x18005d93c  lea     rsi, [rbx+58h]
0x18005d940  mov     rdi, [rsi]
0x18005d943  test    rdi, rdi
0x18005d946  jz      short loc_18005D965
0x18005d948  lea     rcx, [rsp+98h+var_48]; this
0x18005d94d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18005d952  mov     rcx, rdi
0x18005d955  call    cs:__imp_SwDeviceClose
0x18005d95b  lea     rcx, [rsp+98h+var_48]; this
0x18005d960  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18005d965  mov     qword ptr [rsi], 0
0x18005d96c  mov     [rsp+98h+var_60], rsi
0x18005d971  lea     rax, [rsp+98h+hHandle]
0x18005d976  mov     [rsp+98h+var_68], rax
0x18005d97b  lea     rax, ?SwdCallback@DevnodeManagment@DAS@@YAXPEAUHSWDEVICE__@@JPEAXPEBG@Z; DAS::DevnodeManagment::SwdCallback(HSWDEVICE__ *,long,void *,ushort const *)
0x18005d982  mov     [rsp+98h+var_70], rax; char *
0x18005d987  mov     rax, [rsp+98h+arg_20]
0x18005d98f  mov     qword ptr [rsp+98h+var_78], rax; int
0x18005d994  mov     r9d, r15d
0x18005d997  mov     r8, r12
0x18005d99a  mov     rdx, r14
0x18005d99d  mov     rcx, [rsp+98h+var_58]
0x18005d9a2  call    cs:__imp_SwDeviceCreate
0x18005d9a8  mov     edi, eax
0x18005d9aa  test    eax, eax
0x18005d9ac  jns     short loc_18005D9EF
0x18005d9ae  mov     rcx, [rsp+98h]; this
0x18005d9b6  mov     r9d, eax; char *
0x18005d9b9  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\association\\se"...
0x18005d9c0  mov     edx, 82h; void *
0x18005d9c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d9ca  lea     rcx, [rsp+98h+var_58]
0x18005d9cf  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005d9d4  lea     rcx, [rsp+98h+var_50]
0x18005d9d9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005d9de  lea     rcx, [rsp+98h+hHandle]; this
0x18005d9e3  call    ??1_swd_callback_data@DevnodeManagment@DAS@@QEAA@XZ; DAS::DevnodeManagment::_swd_callback_data::~_swd_callback_data(void)
0x18005d9e8  mov     eax, edi
0x18005d9ea  jmp     loc_18005DB6E
0x18005d9ef  mov     edx, 0EA60h; dwMilliseconds
0x18005d9f4  mov     rcx, [rsp+98h+hHandle]; hHandle
0x18005d9f9  call    cs:__imp_WaitForSingleObject
0x18005d9ff  test    eax, eax
0x18005da01  jz      loc_18005DACA
0x18005da07  cmp     eax, 102h
0x18005da0c  jz      short loc_18005DA78
0x18005da0e  call    cs:__imp_GetLastError
0x18005da14  mov     edi, eax
0x18005da16  test    eax, eax
0x18005da18  jle     short loc_18005DA23
0x18005da1a  movzx   edi, ax
0x18005da1d  or      edi, 80070000h
0x18005da23  test    edi, edi
0x18005da25  jns     loc_18005DB33
0x18005da2b  mov     rcx, [rsp+98h]; this
0x18005da33  lea     rax, aWaitingForDevi_0; "waiting for device creation failed for "...
0x18005da3a  mov     qword ptr [rsp+98h+var_78], rax; int
0x18005da3f  mov     r9d, edi; char *
0x18005da42  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\association\\se"...
0x18005da49  mov     edx, 90h; void *
0x18005da4e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005da53  lea     rcx, [rsp+98h+var_58]
0x18005da58  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005da5d  lea     rcx, [rsp+98h+var_50]
0x18005da62  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005da67  lea     rcx, [rsp+98h+hHandle]; this
0x18005da6c  call    ??1_swd_callback_data@DevnodeManagment@DAS@@QEAA@XZ; DAS::DevnodeManagment::_swd_callback_data::~_swd_callback_data(void)
0x18005da71  mov     eax, edi
0x18005da73  jmp     loc_18005DB6E
0x18005da78  mov     rcx, [rsp+98h]; this
0x18005da80  lea     rax, aWaitingForDevi; "waiting for device creation timed out"
0x18005da87  mov     qword ptr [rsp+98h+var_78], rax; int
0x18005da8c  mov     ebx, 800705B4h
0x18005da91  mov     r9d, ebx; char *
0x18005da94  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\association\\se"...
0x18005da9b  mov     edx, 8Ch; void *
0x18005daa0  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005daa5  lea     rcx, [rsp+98h+var_58]
0x18005daaa  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005daaf  lea     rcx, [rsp+98h+var_50]
0x18005dab4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005dab9  lea     rcx, [rsp+98h+hHandle]; this
0x18005dabe  call    ??1_swd_callback_data@DevnodeManagment@DAS@@QEAA@XZ; DAS::DevnodeManagment::_swd_callback_data::~_swd_callback_data(void)
0x18005dac3  mov     eax, ebx
0x18005dac5  jmp     loc_18005DB6E
0x18005daca  mov     edi, dword ptr [rsp+98h+var_38]
0x18005dace  test    edi, edi
0x18005dad0  jns     short loc_18005DB1C
0x18005dad2  mov     rcx, [rsp+98h]; this
0x18005dada  lea     rax, aDeviceCreation; "device creation was unsuccessful"
0x18005dae1  mov     qword ptr [rsp+98h+var_78], rax; int
0x18005dae6  mov     r9d, edi; char *
0x18005dae9  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\association\\se"...
0x18005daf0  mov     edx, 87h; void *
0x18005daf5  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005dafa  lea     rcx, [rsp+98h+var_58]
0x18005daff  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005db04  lea     rcx, [rsp+98h+var_50]
0x18005db09  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005db0e  lea     rcx, [rsp+98h+hHandle]; this
0x18005db13  call    ??1_swd_callback_data@DevnodeManagment@DAS@@QEAA@XZ; DAS::DevnodeManagment::_swd_callback_data::~_swd_callback_data(void)
0x18005db18  mov     eax, edi
0x18005db1a  jmp     short loc_18005DB6E
0x18005db1c  mov     rdx, [rsp+98h+var_30]
0x18005db21  mov     [rsp+98h+var_30], 0
0x18005db2a  lea     rcx, [rbx+10h]
0x18005db2e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18005db33  lea     rcx, [rsp+98h+var_50]
0x18005db38  call    ?InternalAddRef@?$ComPtr@VDevnodeFactory@DevnodeManagment@DAS@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<DAS::DevnodeManagment::DevnodeFactory>::InternalAddRef(void)
0x18005db3d  mov     rax, [rsp+98h+arg_28]
0x18005db45  mov     [rax], rbx
0x18005db48  lea     rcx, [rsp+98h+var_58]
0x18005db4d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005db52  lea     rcx, [rsp+98h+var_50]
0x18005db57  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005db5c  lea     rcx, [rsp+98h+hHandle]; this
0x18005db61  call    ??1_swd_callback_data@DevnodeManagment@DAS@@QEAA@XZ; DAS::DevnodeManagment::_swd_callback_data::~_swd_callback_data(void)
0x18005db66  xor     eax, eax
0x18005db68  jmp     short loc_18005DB6E
0x18005db6a  mov     eax, dword ptr [rsp+98h+var_58]
0x18005db6e  mov     rbx, [rsp+98h+arg_10]
0x18005db76  add     rsp, 70h
0x18005db7a  pop     r15
0x18005db7c  pop     r14
0x18005db7e  pop     r12
0x18005db80  pop     rdi
0x18005db81  pop     rsi
0x18005db82  retn
```
