# DAS::DevnodeManagment::DevnodeManager::MakeAndInitialize(ushort const *,ushort const *,ushort const *,DAS::DevnodeManagment::DevnodeManager * *)

- ea: `0x1800387a4`
- end: `0x180038acc`
- name: `?MakeAndInitialize@DevnodeManager@DevnodeManagment@DAS@@SAJPEBG00PEAPEAV123@@Z`
- size: `808`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct DAS::DevnodeManagment::DevnodeManager **)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180042f44`

## callees

- `0x180005798`
- `0x1800074c0`
- `0x180019c38`
- `0x180024888`
- `0x1800263f4`
- `0x18002a948`
- `0x18002aa34`
- `0x18002e0bc`
- `0x1800364e8`
- `0x1800387a4`
- `0x18003c79c`
- `0x18004e2f4`
- `0x18004e9c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800387e6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800387e6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180038940`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180038940`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038955`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038955`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180038a74`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180038a74`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x1800388f0`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x1800388f0`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18003889c`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18003889c`

## string_xrefs

- `0x180038809`: `onecore\base\devices\association\service\lib\devnodemanagement.cpp`
- `0x180038907`: `onecore\base\devices\association\service\lib\devnodemanagement.cpp`
- `0x180038979`: `onecore\base\devices\association\service\lib\devnodemanagement.cpp`
- `0x1800389b8`: `onecore\base\devices\association\service\lib\devnodemanagement.cpp`
- `0x1800389fa`: `onecore\base\devices\association\service\lib\devnodemanagement.cpp`

## pseudocode

```c
__int64 __fastcall DAS::DevnodeManagment::DevnodeManager::MakeAndInitialize(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        PVOID **a4)
{
  HANDLE EventW; // rax
  const char *v6; // r9
  unsigned int v7; // ebx
  const char *v8; // r9
  __int64 result; // rax
  PVOID *v10; // rdi
  _QWORD *v11; // rbx
  __int64 v12; // rsi
  int v13; // eax
  unsigned int v14; // ebx
  DWORD v15; // eax
  signed int LastError; // eax
  unsigned int v17; // ebx
  unsigned int v18; // ebx
  PTP_WORK ThreadpoolWork; // rax
  HANDLE hHandle; // [rsp+40h] [rbp-88h] BYREF
  char *v21; // [rsp+48h] [rbp-80h]
  _QWORD v22[2]; // [rsp+50h] [rbp-78h] BYREF
  int v23; // [rsp+60h] [rbp-68h] BYREF
  const wchar_t *v24; // [rsp+68h] [rbp-60h]
  int v25; // [rsp+88h] [rbp-40h]
  const wchar_t *v26; // [rsp+90h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  const unsigned __int16 *v28; // [rsp+D8h] [rbp+10h] BYREF
  PVOID pv; // [rsp+E0h] [rbp+18h] BYREF

  pv = a3;
  v28 = a2;
  try
  {
    std::make_unique<DAS::DevnodeManagment::DevnodeManager,,0>(&pv);
    hHandle = 0;
    v22[0] = 0;
    EventW = CreateEventW(0, 0, 0, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hHandle,
      EventW);
    if ( hHandle )
    {
      memset_0(&v23, 0, 0x48u);
      v23 = 72;
      v25 = 2;
      v24 = L"{ce958e9a-424f-4c88-86f4-11314821e75a}";
      v26 = L"Microsoft Device Association Root Enumerator";
      v10 = (PVOID *)pv;
      v11 = (char *)pv + 24;
      v12 = *((_QWORD *)pv + 3);
      if ( v12 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v28);
        SwDeviceClose(v12);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v28);
      }
      *v11 = 0;
      v13 = SwDeviceCreate(L"MSDAS", L"HTREE\\ROOT\\0", &v23, 0);
      v14 = v13;
      if ( v13 >= 0 )
      {
        v15 = WaitForSingleObject(hHandle, 0xEA60u);
        if ( v15 )
        {
          if ( v15 == 258 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x50,
              (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodemanagement.cpp",
              (const char *)0x800705B4LL,
              0);
            DAS::DevnodeManagment::_swd_callback_data::~_swd_callback_data((DAS::DevnodeManagment::_swd_callback_data *)&hHandle);
            std::unique_ptr<DAS::DevnodeManagment::DevnodeManager>::~unique_ptr<DAS::DevnodeManagment::DevnodeManager>(&pv);
            result = 2147943860LL;
          }
          else
          {
            LastError = GetLastError();
            v17 = LastError;
            if ( LastError > 0 )
              v17 = (unsigned __int16)LastError | 0x80070000;
            if ( (v17 & 0x80000000) != 0 )
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x54,
                (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodemanagement.cpp",
                (const char *)v17,
                0);
            DAS::DevnodeManagment::_swd_callback_data::~_swd_callback_data((DAS::DevnodeManagment::_swd_callback_data *)&hHandle);
            std::unique_ptr<DAS::DevnodeManagment::DevnodeManager>::~unique_ptr<DAS::DevnodeManagment::DevnodeManager>(&pv);
            result = v17;
          }
        }
        else
        {
          v18 = (unsigned int)v21;
          if ( (int)v21 >= 0 )
          {
            pv = *v10;
            *v10 = 0;
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
              v10,
              v22);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
              v22,
              &pv);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
            ThreadpoolWork = CreateThreadpoolWork(
                               (PTP_WORK_CALLBACK)DAS::DevnodeManagment::DevnodeManager::CreatePersistedAepsDevnodesWork,
                               v10,
                               0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(
              v10 + 12,
              ThreadpoolWork);
            pv = 0;
            *a4 = v10;
            DAS::DevnodeManagment::_swd_callback_data::~_swd_callback_data((DAS::DevnodeManagment::_swd_callback_data *)&hHandle);
            std::unique_ptr<DAS::DevnodeManagment::DevnodeManager>::~unique_ptr<DAS::DevnodeManagment::DevnodeManager>(&pv);
            result = 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4C,
              (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodemanagement.cpp",
              (const char *)(unsigned int)v21,
              0);
            DAS::DevnodeManagment::_swd_callback_data::~_swd_callback_data((DAS::DevnodeManagment::_swd_callback_data *)&hHandle);
            std::unique_ptr<DAS::DevnodeManagment::DevnodeManager>::~unique_ptr<DAS::DevnodeManagment::DevnodeManager>(&pv);
            result = v18;
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x46,
          (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodemanagement.cpp",
          (const char *)(unsigned int)v13,
          0);
        DAS::DevnodeManagment::_swd_callback_data::~_swd_callback_data((DAS::DevnodeManagment::_swd_callback_data *)&hHandle);
        std::unique_ptr<DAS::DevnodeManagment::DevnodeManager>::~unique_ptr<DAS::DevnodeManagment::DevnodeManager>(&pv);
        result = v14;
      }
    }
    else
    {
      v7 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x37,
             (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodemanagement.cpp",
             v6);
      DAS::DevnodeManagment::_swd_callback_data::~_swd_callback_data((DAS::DevnodeManagment::_swd_callback_data *)&hHandle);
      std::unique_ptr<DAS::DevnodeManagment::DevnodeManager>::~unique_ptr<DAS::DevnodeManagment::DevnodeManager>(&pv);
      result = v7;
    }
  }
  catch ( ... )
  {
    LODWORD(pv) = wil::details::in1diag3::Return_CaughtException(
                    retaddr,
                    (void *)0x5E,
                    (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodemanagement.cpp",
                    v8);
    return (unsigned int)pv;
  }
  return result;
}

```

## disassembly

```asm
0x1800387a4  mov     rax, rsp
0x1800387a7  mov     [rax+8], rbx
0x1800387ab  mov     [rax+18h], r8
0x1800387af  mov     [rax+10h], rdx
0x1800387b3  push    rsi
0x1800387b4  push    rdi
0x1800387b5  push    r14
0x1800387b7  sub     rsp, 0B0h
0x1800387be  mov     r14, r9
0x1800387c1  lea     rcx, [rax+18h]
0x1800387c5  call    ??$make_unique@VDevnodeManager@DevnodeManagment@DAS@@$$V$0A@@std@@YA?AV?$unique_ptr@VDevnodeManager@DevnodeManagment@DAS@@U?$default_delete@VDevnodeManager@DevnodeManagment@DAS@@@std@@@0@XZ; std::make_unique<DAS::DevnodeManagment::DevnodeManager,,0>(void)
0x1800387ca  mov     [rsp+0C8h+hHandle], 0
0x1800387d3  mov     [rsp+0C8h+var_78], 0
0x1800387dc  xor     r9d, r9d; lpName
0x1800387df  xor     r8d, r8d; bInitialState
0x1800387e2  xor     edx, edx; bManualReset
0x1800387e4  xor     ecx, ecx; lpEventAttributes
0x1800387e6  call    cs:__imp_CreateEventW
0x1800387ec  mov     rdx, rax
0x1800387ef  lea     rcx, [rsp+0C8h+hHandle]
0x1800387f4  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800387f9  cmp     [rsp+0C8h+hHandle], 0
0x1800387ff  jnz     short loc_18003883A
0x180038801  mov     rcx, [rsp+0C8h]; this
0x180038809  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\association\\se"...
0x180038810  mov     edx, 37h ; '7'; void *
0x180038815  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003881a  mov     ebx, eax
0x18003881c  lea     rcx, [rsp+0C8h+hHandle]; this
0x180038821  call    ??1_swd_callback_data@DevnodeManagment@DAS@@QEAA@XZ; DAS::DevnodeManagment::_swd_callback_data::~_swd_callback_data(void)
0x180038826  lea     rcx, [rsp+0C8h+pv]
0x18003882e  call    ??1?$unique_ptr@VDevnodeManager@DevnodeManagment@DAS@@U?$default_delete@VDevnodeManager@DevnodeManagment@DAS@@@std@@@std@@QEAA@XZ; std::unique_ptr<DAS::DevnodeManagment::DevnodeManager>::~unique_ptr<DAS::DevnodeManagment::DevnodeManager>(void)
0x180038833  mov     eax, ebx
0x180038835  jmp     loc_180038AB7
0x18003883a  mov     ebx, 48h ; 'H'
0x18003883f  mov     r8d, ebx; Size
0x180038842  xor     edx, edx; Val
0x180038844  lea     rcx, [rsp+0C8h+var_68]; void *
0x180038849  call    memset_0
0x18003884e  mov     [rsp+0C8h+var_68], ebx
0x180038852  mov     [rsp+0C8h+var_40], 2
0x18003885d  lea     rax, aCe958e9a424f4c; "{ce958e9a-424f-4c88-86f4-11314821e75a}"
0x180038864  mov     [rsp+0C8h+var_60], rax
0x180038869  lea     rax, aMicrosoftDevic; "Microsoft Device Association Root Enume"...
0x180038870  mov     [rsp+0C8h+var_38], rax
0x180038878  mov     rdi, [rsp+0C8h+pv]
0x180038880  lea     rbx, [rdi+18h]
0x180038884  mov     rsi, [rbx]
0x180038887  test    rsi, rsi
0x18003888a  jz      short loc_1800388AF
0x18003888c  lea     rcx, [rsp+0C8h+arg_8]; this
0x180038894  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180038899  mov     rcx, rsi
0x18003889c  call    cs:__imp_SwDeviceClose
0x1800388a2  lea     rcx, [rsp+0C8h+arg_8]; this
0x1800388aa  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800388af  mov     qword ptr [rbx], 0
0x1800388b6  mov     [rsp+0C8h+var_90], rbx
0x1800388bb  lea     rax, [rsp+0C8h+hHandle]
0x1800388c0  mov     [rsp+0C8h+var_98], rax
0x1800388c5  lea     rax, ?SwdCallback@DevnodeManagment@DAS@@YAXPEAUHSWDEVICE__@@JPEAXPEBG@Z; DAS::DevnodeManagment::SwdCallback(HSWDEVICE__ *,long,void *,ushort const *)
0x1800388cc  mov     [rsp+0C8h+var_A0], rax
0x1800388d1  mov     qword ptr [rsp+0C8h+var_A8], 0; int
0x1800388da  xor     r9d, r9d
0x1800388dd  lea     r8, [rsp+0C8h+var_68]
0x1800388e2  lea     rdx, aHtreeRoot0; "HTREE\\ROOT\\0"
0x1800388e9  lea     rcx, aMsdas; "MSDAS"
0x1800388f0  call    cs:__imp_SwDeviceCreate
0x1800388f6  mov     ebx, eax
0x1800388f8  test    eax, eax
0x1800388fa  jns     short loc_180038936
0x1800388fc  mov     rcx, [rsp+0C8h]; this
0x180038904  mov     r9d, eax; char *
0x180038907  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\association\\se"...
0x18003890e  mov     edx, 46h ; 'F'; void *
0x180038913  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038918  lea     rcx, [rsp+0C8h+hHandle]; this
0x18003891d  call    ??1_swd_callback_data@DevnodeManagment@DAS@@QEAA@XZ; DAS::DevnodeManagment::_swd_callback_data::~_swd_callback_data(void)
0x180038922  lea     rcx, [rsp+0C8h+pv]
0x18003892a  call    ??1?$unique_ptr@VDevnodeManager@DevnodeManagment@DAS@@U?$default_delete@VDevnodeManager@DevnodeManagment@DAS@@@std@@@std@@QEAA@XZ; std::unique_ptr<DAS::DevnodeManagment::DevnodeManager>::~unique_ptr<DAS::DevnodeManagment::DevnodeManager>(void)
0x18003892f  mov     eax, ebx
0x180038931  jmp     loc_180038AB7
0x180038936  mov     edx, 0EA60h; dwMilliseconds
0x18003893b  mov     rcx, [rsp+0C8h+hHandle]; hHandle
0x180038940  call    cs:__imp_WaitForSingleObject
0x180038946  test    eax, eax
0x180038948  jz      loc_1800389E7
0x18003894e  cmp     eax, 102h
0x180038953  jz      short loc_1800389A8
0x180038955  call    cs:__imp_GetLastError
0x18003895b  mov     ebx, eax
0x18003895d  test    eax, eax
0x18003895f  jle     short loc_18003896A
0x180038961  movzx   ebx, ax
0x180038964  or      ebx, 80070000h
0x18003896a  test    ebx, ebx
0x18003896c  jns     short loc_18003898A
0x18003896e  mov     rcx, [rsp+0C8h]; this
0x180038976  mov     r9d, ebx; char *
0x180038979  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\association\\se"...
0x180038980  mov     edx, 54h ; 'T'; void *
0x180038985  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003898a  lea     rcx, [rsp+0C8h+hHandle]; this
0x18003898f  call    ??1_swd_callback_data@DevnodeManagment@DAS@@QEAA@XZ; DAS::DevnodeManagment::_swd_callback_data::~_swd_callback_data(void)
0x180038994  lea     rcx, [rsp+0C8h+pv]
0x18003899c  call    ??1?$unique_ptr@VDevnodeManager@DevnodeManagment@DAS@@U?$default_delete@VDevnodeManager@DevnodeManagment@DAS@@@std@@@std@@QEAA@XZ; std::unique_ptr<DAS::DevnodeManagment::DevnodeManager>::~unique_ptr<DAS::DevnodeManagment::DevnodeManager>(void)
0x1800389a1  mov     eax, ebx
0x1800389a3  jmp     loc_180038AB7
0x1800389a8  mov     rcx, [rsp+0C8h]; this
0x1800389b0  mov     ebx, 800705B4h
0x1800389b5  mov     r9d, ebx; char *
0x1800389b8  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\association\\se"...
0x1800389bf  mov     edx, 50h ; 'P'; void *
0x1800389c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800389c9  lea     rcx, [rsp+0C8h+hHandle]; this
0x1800389ce  call    ??1_swd_callback_data@DevnodeManagment@DAS@@QEAA@XZ; DAS::DevnodeManagment::_swd_callback_data::~_swd_callback_data(void)
0x1800389d3  lea     rcx, [rsp+0C8h+pv]
0x1800389db  call    ??1?$unique_ptr@VDevnodeManager@DevnodeManagment@DAS@@U?$default_delete@VDevnodeManager@DevnodeManagment@DAS@@@std@@@std@@QEAA@XZ; std::unique_ptr<DAS::DevnodeManagment::DevnodeManager>::~unique_ptr<DAS::DevnodeManagment::DevnodeManager>(void)
0x1800389e0  mov     eax, ebx
0x1800389e2  jmp     loc_180038AB7
0x1800389e7  mov     ebx, dword ptr [rsp+0C8h+var_80]
0x1800389eb  test    ebx, ebx
0x1800389ed  jns     short loc_180038A29
0x1800389ef  mov     rcx, [rsp+0C8h]; this
0x1800389f7  mov     r9d, ebx; char *
0x1800389fa  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\association\\se"...
0x180038a01  mov     edx, 4Ch ; 'L'; void *
0x180038a06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038a0b  lea     rcx, [rsp+0C8h+hHandle]; this
0x180038a10  call    ??1_swd_callback_data@DevnodeManagment@DAS@@QEAA@XZ; DAS::DevnodeManagment::_swd_callback_data::~_swd_callback_data(void)
0x180038a15  lea     rcx, [rsp+0C8h+pv]
0x180038a1d  call    ??1?$unique_ptr@VDevnodeManager@DevnodeManagment@DAS@@U?$default_delete@VDevnodeManager@DevnodeManagment@DAS@@@std@@@std@@QEAA@XZ; std::unique_ptr<DAS::DevnodeManagment::DevnodeManager>::~unique_ptr<DAS::DevnodeManagment::DevnodeManager>(void)
0x180038a22  mov     eax, ebx
0x180038a24  jmp     loc_180038AB7
0x180038a29  mov     rax, [rdi]
0x180038a2c  mov     [rsp+0C8h+pv], rax
0x180038a34  mov     qword ptr [rdi], 0
0x180038a3b  lea     rdx, [rsp+0C8h+var_78]
0x180038a40  mov     rcx, rdi
0x180038a43  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180038a48  lea     rdx, [rsp+0C8h+pv]
0x180038a50  lea     rcx, [rsp+0C8h+var_78]
0x180038a55  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180038a5a  lea     rcx, [rsp+0C8h+pv]
0x180038a62  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180038a67  xor     r8d, r8d; pcbe
0x180038a6a  mov     rdx, rdi; pv
0x180038a6d  lea     rcx, ?CreatePersistedAepsDevnodesWork@DevnodeManager@DevnodeManagment@DAS@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180038a74  call    cs:__imp_CreateThreadpoolWork
0x180038a7a  lea     rcx, [rdi+60h]
0x180038a7e  mov     rdx, rax
0x180038a81  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)
0x180038a86  mov     [rsp+0C8h+pv], 0
0x180038a92  mov     [r14], rdi
0x180038a95  lea     rcx, [rsp+0C8h+hHandle]; this
0x180038a9a  call    ??1_swd_callback_data@DevnodeManagment@DAS@@QEAA@XZ; DAS::DevnodeManagment::_swd_callback_data::~_swd_callback_data(void)
0x180038a9f  lea     rcx, [rsp+0C8h+pv]
0x180038aa7  call    ??1?$unique_ptr@VDevnodeManager@DevnodeManagment@DAS@@U?$default_delete@VDevnodeManager@DevnodeManagment@DAS@@@std@@@std@@QEAA@XZ; std::unique_ptr<DAS::DevnodeManagment::DevnodeManager>::~unique_ptr<DAS::DevnodeManagment::DevnodeManager>(void)
0x180038aac  xor     eax, eax
0x180038aae  jmp     short loc_180038AB7
0x180038ab0  mov     eax, dword ptr [rsp+0C8h+pv]
0x180038ab7  mov     rbx, [rsp+0C8h+arg_0]
0x180038abf  add     rsp, 0B0h
0x180038ac6  pop     r14
0x180038ac8  pop     rdi
0x180038ac9  pop     rsi
0x180038aca  retn
```
