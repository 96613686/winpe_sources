# LPA::EsimManager::OnStart(void)

- ea: `0x18008fb10`
- end: `0x18009024a`
- name: `?OnStart@EsimManager@LPA@@UEAAJXZ`
- size: `1850`
- prototype: `__int64 __fastcall(LPA::EsimManager *__hidden this)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800013ec`
- `0x1800017c8`
- `0x18000df90`
- `0x18006ba8c`
- `0x18006d8d0`
- `0x1800709e4`
- `0x180071344`
- `0x180071650`
- `0x180071a34`
- `0x180071a8c`
- `0x180076d0c`
- `0x180079550`
- `0x180079c60`
- `0x180081640`
- `0x1800816a0`
- `0x180085810`
- `0x18008c060`
- `0x18008c568`
- `0x18008fb10`
- `0x180101010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008fb7f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008fb7f`
- `wwapi!WwanQueryInterface` at `0x18008fe2e`
- `wwapi!WwanQueryInterface` at `0x18008fe9c`
- `wwapi!WwanQueryInterface` at `0x18008fe2e`
- `wwapi!WwanQueryInterface` at `0x18008fe9c`
- `wwapi!WwanEnumerateInterfaces` at `0x18008fd53`
- `wwapi!WwanEnumerateInterfaces` at `0x18008fd53`
- `wwapi!WwanQueryInterfaceEx` at `0x18008ff71`
- `wwapi!WwanQueryInterfaceEx` at `0x1800900d4`
- `wwapi!WwanQueryInterfaceEx` at `0x18008ff71`
- `wwapi!WwanQueryInterfaceEx` at `0x1800900d4`
- `wwapi!WwanFreeMemory` at `0x180090028`
- `wwapi!WwanFreeMemory` at `0x180090046`
- `wwapi!WwanFreeMemory` at `0x18009005a`
- `wwapi!WwanFreeMemory` at `0x180090082`
- `wwapi!WwanFreeMemory` at `0x180090141`
- `wwapi!WwanFreeMemory` at `0x180090028`
- `wwapi!WwanFreeMemory` at `0x180090046`
- `wwapi!WwanFreeMemory` at `0x18009005a`
- `wwapi!WwanFreeMemory` at `0x180090082`
- `wwapi!WwanFreeMemory` at `0x180090141`

## string_xrefs

- `0x18008fb56`: `LpaServiceEsimManager`
- `0x18008fd8b`: `LpaServiceEsimManager`
- `0x180090078`: `LpaServiceEsimManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall LPA::EsimManager::OnStart(LPA::EsimManager *this)
{
  char *v2; // r15
  unsigned int v3; // edi
  int LastErrorToHResultAndForceFailure; // r13d
  HANDLE EventW; // rax
  CommonUtil *v6; // rcx
  __int64 v7; // rdx
  int LpasvcPersistentSettingsKey; // ecx
  int v9; // r8d
  unsigned int *v10; // r9
  unsigned int *v11; // r9
  const WCHAR *v12; // rax
  unsigned int *v13; // r9
  int DwordFromRegistry; // ecx
  int v15; // r8d
  int v16; // r9d
  int v17; // eax
  int v18; // r8d
  int v19; // r9d
  signed int v20; // ecx
  const char *v21; // rdx
  unsigned int v22; // r15d
  const unsigned __int16 *v23; // r12
  const struct _GUID *v24; // r14
  const char *v25; // rcx
  int Interface; // ebx
  int v27; // r8d
  int v28; // r9d
  int v29; // ebx
  int v30; // ecx
  int v31; // r8d
  int v32; // r9d
  enum _WWAN_READY_STATE *v33; // rcx
  unsigned int *v34; // rcx
  int v35; // ebx
  enum _WWAN_READY_STATE *v36; // rcx
  __int64 v37; // rdi
  void (__fastcall *v38)(__int64, __int64); // rbx
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rdi
  void (__fastcall *v42)(__int64, __int64); // rbx
  __int64 v43; // rax
  __int64 v44; // rax
  BYTE Data[8]; // [rsp+40h] [rbp-79h] BYREF
  enum _WWAN_READY_STATE *v47; // [rsp+48h] [rbp-71h] BYREF
  int v48; // [rsp+50h] [rbp-69h] BYREF
  const char *v49; // [rsp+58h] [rbp-61h] BYREF
  const char *v50; // [rsp+60h] [rbp-59h] BYREF
  const char *v51; // [rsp+68h] [rbp-51h] BYREF
  unsigned int *v52; // [rsp+70h] [rbp-49h] BYREF
  int v53; // [rsp+78h] [rbp-41h]
  int v54; // [rsp+7Ch] [rbp-3Dh] BYREF
  int v55; // [rsp+80h] [rbp-39h] BYREF
  unsigned int v56; // [rsp+84h] [rbp-35h] BYREF
  const char *v57; // [rsp+88h] [rbp-31h] BYREF
  const char *v58; // [rsp+90h] [rbp-29h] BYREF
  std::_Ref_count_base *v59; // [rsp+98h] [rbp-21h]
  __int128 v60; // [rsp+A0h] [rbp-19h] BYREF
  __m128i si128; // [rsp+B0h] [rbp-9h]

  v2 = (char *)this + 64;
  v3 = 0;
  if ( *((_DWORD *)this + 16) )
    return (unsigned int)-2147019873;
  LastErrorToHResultAndForceFailure = 0;
  v53 = 0;
  LPA::Util::SetRunningState((char *)this + 64, 1, "LpaServiceEsimManager");
  EventW = CreateEventW(0, 0, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 72,
    EventW);
  if ( !*((_QWORD *)this + 9) )
  {
    LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v6);
    v53 = LastErrorToHResultAndForceFailure;
    if ( LastErrorToHResultAndForceFailure < 0 )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        (char *)this + 72,
        0);
      v7 = 0;
      goto LABEL_73;
    }
  }
  v60 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v60) = 0;
  LpasvcPersistentSettingsKey = CommonUtil::GetLpasvcPersistentSettingsKey((__int64)v6, (__int64)&v60);
  if ( LpasvcPersistentSettingsKey < 0 )
  {
    if ( (unsigned int)CallbackContext > 3 )
    {
      v48 = LpasvcPersistentSettingsKey;
      v51 = "LPA::EsimManager::OnStart";
      v49 = "LpaServiceEsimManager";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        LpasvcPersistentSettingsKey,
        (unsigned int)byte_18012F521,
        v9,
        (_DWORD)v10,
        (__int64)&v49,
        (__int64)&v51,
        (__int64)&v48);
    }
  }
  else
  {
    std::wstring::operator=((char *)this + 264, &v60);
  }
  *(_DWORD *)Data = 0;
  if ( (int)CommonUtil::GetDwordFromRegistry(L"Software\\Microsoft\\Wlpasvc", L"testmode", Data, v10) >= 0 )
    *((_BYTE *)this + 262) = *(_DWORD *)Data != 0;
  if ( (int)CommonUtil::GetDwordFromRegistry(L"Software\\Microsoft\\Wlpasvc", L"uarequired", Data, v11) >= 0 )
    *((_BYTE *)this + 260) = *(_DWORD *)Data != 0;
  v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 264);
  DwordFromRegistry = CommonUtil::GetDwordFromRegistry(v12, L"uamode", Data, v13);
  if ( DwordFromRegistry < 0 )
  {
    if ( (unsigned int)CallbackContext > 3 )
    {
      v48 = DwordFromRegistry;
      v51 = "LPA::EsimManager::OnStart";
      v49 = "LpaServiceEsimManager";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        DwordFromRegistry,
        (unsigned int)&word_18012F4E6,
        v15,
        v16,
        (__int64)&v49,
        (__int64)&v51,
        (__int64)&v48);
    }
  }
  else if ( *(_DWORD *)Data )
  {
    if ( *(_DWORD *)Data == 1 )
    {
      *((_DWORD *)this + 64) = 1;
    }
    else if ( *(_DWORD *)Data == 2 )
    {
      *((_DWORD *)this + 64) = 2;
    }
  }
  else
  {
    *((_DWORD *)this + 64) = 0;
  }
  if ( *((_BYTE *)this + 260) && *((_DWORD *)this + 64) == 2 )
    *((_DWORD *)this + 64) = 1;
  std::wstring::_Tidy_deallocate(&v60);
  v49 = 0;
  v54 = 1;
  v17 = WwanEnumerateInterfaces(*((_QWORD *)this + 10), &v54, &v49);
  v20 = v17;
  if ( v17 > 0 )
    v20 = (unsigned __int16)v17 | 0x80070000;
  if ( v20 < 0 || (v21 = v49) == 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v50) = v20;
      *(_QWORD *)&v60 = "LPA::EsimManager::OnStart";
      v58 = "LpaServiceEsimManager";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v20,
        (unsigned int)&unk_18012F4A8,
        v18,
        v19,
        (__int64)&v58,
        (__int64)&v60,
        (__int64)&v50);
    }
    goto LABEL_68;
  }
  v22 = 0;
  v48 = 0;
  if ( !*(_DWORD *)v49 )
    goto LABEL_57;
  do
  {
    *(_DWORD *)Data = 0;
    v51 = 0;
    v23 = 0;
    v24 = (const struct _GUID *)&v21[588 * v22 + 4];
    if ( (unsigned int)CallbackContext > 4 )
    {
      v55 = *(_DWORD *)v49;
      v47 = (enum _WWAN_READY_STATE *)&v21[588 * v22 + 4];
      v50 = "LPA::EsimManager::OnStart";
      v57 = "LpaServiceEsimManager";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
        v55,
        (unsigned int)word_18012F44A,
        v18,
        v19,
        (__int64)&v57,
        (__int64)&v50,
        (__int64)&v47,
        (__int64)&v55);
    }
    if ( !(unsigned int)WwanQueryInterface(*((_QWORD *)this + 10), v24, 7) )
    {
      v25 = v51;
      if ( v51 )
      {
        *((_WORD *)v51 + 496) = 0;
        if ( !*((_DWORD *)v25 + 226) )
        {
          *((_WORD *)v25 + 343) = 0;
          v23 = (const unsigned __int16 *)(v25 + 652);
        }
      }
    }
    v52 = 0;
    *(_QWORD *)&v60 = &v52;
    *((_QWORD *)&v60 + 1) = 0;
    si128.m128i_i8[0] = 1;
    Interface = WwanQueryInterface(*((_QWORD *)this + 10), v24, 46);
    wil::details::out_param_ptr_t<unsigned char * *,wistd::unique_ptr<_WWAN_MULTI_SIM_SLOT_MAPPING_STATUS,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>::~out_param_ptr_t<unsigned char * *,wistd::unique_ptr<_WWAN_MULTI_SIM_SLOT_MAPPING_STATUS,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>(&v60);
    if ( !Interface )
    {
      if ( *(_DWORD *)Data >= 8u )
      {
        if ( (unsigned int)CallbackContext > 4 )
        {
          v56 = *v52;
          v47 = (enum _WWAN_READY_STATE *)"LPA::EsimManager::OnStart";
          v50 = "LpaServiceEsimManager";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v56,
            (unsigned int)byte_18012F409,
            v27,
            v28,
            (__int64)&v50,
            (__int64)&v47,
            (__int64)&v56);
        }
        if ( *v52 )
        {
          do
          {
            LODWORD(v57) = v3;
            v47 = 0;
            v60 = (unsigned __int64)&v47;
            si128.m128i_i8[0] = 1;
            v29 = WwanQueryInterfaceEx(*((_QWORD *)this + 10), v24, 36, 4, &v57, 0, Data, (char *)&v60 + 8);
            wil::details::out_param_ptr_t<unsigned char * *,wistd::unique_ptr<_WWAN_MULTI_SIM_SLOT_MAPPING_STATUS,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>::~out_param_ptr_t<unsigned char * *,wistd::unique_ptr<_WWAN_MULTI_SIM_SLOT_MAPPING_STATUS,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>(&v60);
            if ( !v29 && v47 )
            {
              if ( (unsigned int)CallbackContext > 4 )
              {
                LODWORD(v50) = v3;
                v58 = "LPA::EsimManager::OnStart";
                *(_QWORD *)&v60 = "LpaServiceEsimManager";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                  v30,
                  (unsigned int)byte_18012F3C9,
                  v31,
                  v32,
                  (__int64)&v60,
                  (__int64)&v58,
                  (__int64)&v50);
              }
              if ( LPA::EsimManager::IsEsimInterface(
                     (LPA::EsimManager *)((char *)this - 40),
                     v24,
                     (const unsigned int *)v47 + 21) )
              {
                *((_WORD *)v47 + 40) = 0;
                LPA::EsimManager::HandleNewEsimDetected(
                  (LPA::EsimManager *)((char *)this - 40),
                  v24,
                  (const unsigned int *)v47 + 21,
                  v47,
                  v23,
                  (const unsigned __int16 (*)[21])((char *)v47 + 40));
              }
            }
            v33 = v47;
            v47 = 0;
            if ( v33 )
              ((void (*)(void))WwanFreeMemory)();
            ++v3;
          }
          while ( v3 < *v52 );
          v22 = v48;
        }
        v3 = 0;
      }
      goto LABEL_53;
    }
    if ( Interface != 50 )
      goto LABEL_53;
    v47 = 0;
    *(_QWORD *)&v60 = &v47;
    *((_QWORD *)&v60 + 1) = 0;
    si128.m128i_i8[0] = 1;
    v35 = WwanQueryInterfaceEx(*((_QWORD *)this + 10), v24, 36, 0, 0, 0, Data, (char *)&v60 + 8);
    wil::details::out_param_ptr_t<unsigned char * *,wistd::unique_ptr<_WWAN_MULTI_SIM_SLOT_MAPPING_STATUS,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>::~out_param_ptr_t<unsigned char * *,wistd::unique_ptr<_WWAN_MULTI_SIM_SLOT_MAPPING_STATUS,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>(&v60);
    if ( !v35 )
    {
      v36 = v47;
      if ( !v47 )
        goto LABEL_64;
      if ( LPA::EsimManager::IsEsimInterface(
             (LPA::EsimManager *)((char *)this - 40),
             v24,
             (const unsigned int *)v47 + 21) )
      {
        *((_WORD *)v47 + 40) = 0;
        LPA::EsimManager::HandleNewEsimDetected(
          (LPA::EsimManager *)((char *)this - 40),
          v24,
          (const unsigned int *)v47 + 21,
          v47,
          v23,
          (const unsigned __int16 (*)[21])((char *)v47 + 40));
      }
    }
    v36 = v47;
LABEL_64:
    v47 = 0;
    if ( v36 )
      ((void (*)(void))WwanFreeMemory)();
LABEL_53:
    WwanFreeMemory(v51);
    v34 = v52;
    v52 = 0;
    if ( v34 )
      WwanFreeMemory(v34);
    v48 = ++v22;
    v21 = v49;
  }
  while ( v22 < *(_DWORD *)v49 );
  LastErrorToHResultAndForceFailure = v53;
LABEL_57:
  WwanFreeMemory(v21);
  v2 = (char *)this + 64;
LABEL_68:
  v37 = *((_QWORD *)this + 15);
  v38 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v37 + 32LL);
  v39 = std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this((char *)this + 48, &v58);
  v40 = std::weak_ptr<LPA::LpdNotificationHandler>::weak_ptr<LPA::LpdNotificationHandler>(&v60, v39);
  v38(v37, v40);
  if ( v59 )
    std::_Ref_count_base::_Decref(v59);
  v41 = *((_QWORD *)this + 17);
  v42 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v41 + 104LL);
  v43 = std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this((char *)this + 48, &v58);
  v44 = std::weak_ptr<LPA::EnterpriseManagerNotificationHandler>::weak_ptr<LPA::EnterpriseManagerNotificationHandler>(
          &v60,
          v43);
  v42(v41, v44);
  if ( v59 )
    std::_Ref_count_base::_Decref(v59);
  v7 = 2;
LABEL_73:
  LPA::Util::SetRunningState(v2, v7, "LpaServiceEsimManager");
  return (unsigned int)LastErrorToHResultAndForceFailure;
}

```

## disassembly

```asm
0x18008fb10  push    rbp
0x18008fb12  push    rbx
0x18008fb13  push    rsi
0x18008fb14  push    rdi
0x18008fb15  push    r12
0x18008fb17  push    r13
0x18008fb19  push    r14
0x18008fb1b  push    r15
0x18008fb1d  lea     rbp, [rsp-1Fh]
0x18008fb22  sub     rsp, 0D8h
0x18008fb29  mov     rax, cs:__security_cookie
0x18008fb30  xor     rax, rsp
0x18008fb33  mov     [rbp+57h+var_50], rax
0x18008fb37  mov     rsi, rcx
0x18008fb3a  lea     r15, [rcx+40h]
0x18008fb3e  xor     edi, edi
0x18008fb40  cmp     [r15], edi
0x18008fb43  jz      short loc_18008FB50
0x18008fb45  mov     r13d, 8007139Fh
0x18008fb4b  jmp     loc_180090227
0x18008fb50  mov     r13d, edi
0x18008fb53  mov     [rbp+57h+var_98], edi
0x18008fb56  lea     r12, aLpaserviceesim; "LpaServiceEsimManager"
0x18008fb5d  mov     r8, r12
0x18008fb60  mov     r14d, 1
0x18008fb66  mov     edx, r14d
0x18008fb69  mov     rcx, r15
0x18008fb6c  call    ?SetRunningState@Util@LPA@@YAXAEAW4RUNNING_STATE@@W43@PEBD@Z; LPA::Util::SetRunningState(RUNNING_STATE &,RUNNING_STATE,char const *)
0x18008fb71  lea     rbx, [rsi+48h]
0x18008fb75  xor     r9d, r9d; lpName
0x18008fb78  xor     r8d, r8d; bInitialState
0x18008fb7b  xor     edx, edx; bManualReset
0x18008fb7d  xor     ecx, ecx; lpEventAttributes
0x18008fb7f  call    cs:__imp_CreateEventW
0x18008fb85  mov     rdx, rax
0x18008fb88  mov     rcx, rbx
0x18008fb8b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18008fb90  cmp     [rbx], rdi
0x18008fb93  jnz     short loc_18008FBB5
0x18008fb95  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x18008fb9a  mov     r13d, eax
0x18008fb9d  mov     [rbp+57h+var_98], eax
0x18008fba0  test    eax, eax
0x18008fba2  jns     short loc_18008FBB5
0x18008fba4  xor     edx, edx
0x18008fba6  mov     rcx, rbx
0x18008fba9  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18008fbae  xor     edx, edx
0x18008fbb0  jmp     loc_18009021C
0x18008fbb5  xorps   xmm0, xmm0
0x18008fbb8  movups  [rbp+57h+var_70], xmm0
0x18008fbbc  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18008fbc4  movdqu  [rbp+57h+var_60], xmm1
0x18008fbc9  mov     word ptr [rbp+57h+var_70], di
0x18008fbcd  lea     rdx, [rbp+57h+var_70]
0x18008fbd1  call    ?GetLpasvcPersistentSettingsKey@CommonUtil@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CommonUtil::GetLpasvcPersistentSettingsKey(ushort const *,std::wstring &)
0x18008fbd6  mov     ecx, eax
0x18008fbd8  lea     rdx, aLpaEsimmanager_47; "LPA::EsimManager::OnStart"
0x18008fbdf  test    eax, eax
0x18008fbe1  js      short loc_18008FBF5
0x18008fbe3  lea     rcx, [rsi+108h]
0x18008fbea  lea     rdx, [rbp+57h+var_70]
0x18008fbee  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18008fbf3  jmp     short loc_18008FC32
0x18008fbf5  mov     eax, cs:CallbackContext
0x18008fbfb  cmp     eax, 3
0x18008fbfe  jbe     short loc_18008FC32
0x18008fc00  mov     [rbp+57h+var_C0], ecx
0x18008fc03  mov     [rbp+57h+var_A8], rdx
0x18008fc07  mov     [rbp+57h+var_B8], r12
0x18008fc0b  lea     rax, [rbp+57h+var_C0]
0x18008fc0f  mov     [rsp+110h+var_E0], rax
0x18008fc14  lea     rax, [rbp+57h+var_A8]
0x18008fc18  mov     [rsp+110h+var_E8], rax
0x18008fc1d  lea     rax, [rbp+57h+var_B8]
0x18008fc21  mov     [rsp+110h+var_F0], rax
0x18008fc26  lea     rdx, byte_18012F521
0x18008fc2d  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18008fc32  mov     rbx, rsi
0x18008fc35  mov     dword ptr [rbp+57h+Data], edi
0x18008fc38  lea     r8, [rbp+57h+Data]; lpData
0x18008fc3c  lea     rdx, aTestmode; "testmode"
0x18008fc43  lea     rcx, SubKey; "Software\\Microsoft\\Wlpasvc"
0x18008fc4a  call    ?GetDwordFromRegistry@CommonUtil@@YAJPEBG0AEAK@Z; CommonUtil::GetDwordFromRegistry(ushort const *,ushort const *,ulong &)
0x18008fc4f  test    eax, eax
0x18008fc51  js      short loc_18008FC5F
0x18008fc53  cmp     dword ptr [rbp+57h+Data], edi
0x18008fc56  setnz   al
0x18008fc59  mov     [rsi+106h], al
0x18008fc5f  lea     r8, [rbp+57h+Data]; lpData
0x18008fc63  lea     rdx, aUarequired; "uarequired"
0x18008fc6a  lea     rcx, SubKey; "Software\\Microsoft\\Wlpasvc"
0x18008fc71  call    ?GetDwordFromRegistry@CommonUtil@@YAJPEBG0AEAK@Z; CommonUtil::GetDwordFromRegistry(ushort const *,ushort const *,ulong &)
0x18008fc76  test    eax, eax
0x18008fc78  js      short loc_18008FC86
0x18008fc7a  cmp     dword ptr [rbp+57h+Data], edi
0x18008fc7d  setnz   al
0x18008fc80  mov     [rsi+104h], al
0x18008fc86  lea     rcx, [rbx+108h]
0x18008fc8d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008fc92  lea     r8, [rbp+57h+Data]; lpData
0x18008fc96  lea     rdx, aUamode; "uamode"
0x18008fc9d  mov     rcx, rax; lpSubKey
0x18008fca0  call    ?GetDwordFromRegistry@CommonUtil@@YAJPEBG0AEAK@Z; CommonUtil::GetDwordFromRegistry(ushort const *,ushort const *,ulong &)
0x18008fca5  mov     ecx, eax
0x18008fca7  test    eax, eax
0x18008fca9  js      short loc_18008FCD9
0x18008fcab  mov     eax, dword ptr [rbp+57h+Data]
0x18008fcae  test    eax, eax
0x18008fcb0  jz      short loc_18008FCD1
0x18008fcb2  sub     eax, 1
0x18008fcb5  jz      short loc_18008FCC8
0x18008fcb7  cmp     eax, 1
0x18008fcba  jnz     short loc_18008FD1D
0x18008fcbc  mov     dword ptr [rsi+100h], 2
0x18008fcc6  jmp     short loc_18008FD1D
0x18008fcc8  mov     [rsi+100h], r14d
0x18008fccf  jmp     short loc_18008FD1D
0x18008fcd1  mov     [rsi+100h], edi
0x18008fcd7  jmp     short loc_18008FD1D
0x18008fcd9  mov     eax, cs:CallbackContext
0x18008fcdf  cmp     eax, 3
0x18008fce2  jbe     short loc_18008FD1D
0x18008fce4  mov     [rbp+57h+var_C0], ecx
0x18008fce7  lea     rax, aLpaEsimmanager_47; "LPA::EsimManager::OnStart"
0x18008fcee  mov     [rbp+57h+var_A8], rax
0x18008fcf2  mov     [rbp+57h+var_B8], r12
0x18008fcf6  lea     rax, [rbp+57h+var_C0]
0x18008fcfa  mov     [rsp+110h+var_E0], rax
0x18008fcff  lea     rax, [rbp+57h+var_A8]
0x18008fd03  mov     [rsp+110h+var_E8], rax
0x18008fd08  lea     rax, [rbp+57h+var_B8]
0x18008fd0c  mov     [rsp+110h+var_F0], rax
0x18008fd11  lea     rdx, word_18012F4E6
0x18008fd18  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18008fd1d  cmp     [rsi+104h], dil
0x18008fd24  jz      short loc_18008FD36
0x18008fd26  cmp     dword ptr [rsi+100h], 2
0x18008fd2d  jnz     short loc_18008FD36
0x18008fd2f  mov     [rsi+100h], r14d
0x18008fd36  lea     rcx, [rbp+57h+var_70]
0x18008fd3a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008fd3f  mov     [rbp+57h+var_B8], rdi
0x18008fd43  mov     [rbp+57h+var_94], r14d
0x18008fd47  lea     r8, [rbp+57h+var_B8]
0x18008fd4b  lea     rdx, [rbp+57h+var_94]
0x18008fd4f  mov     rcx, [rsi+50h]
0x18008fd53  call    cs:__imp_WwanEnumerateInterfaces
0x18008fd59  mov     ecx, eax
0x18008fd5b  test    eax, eax
0x18008fd5d  jle     short loc_18008FD68
0x18008fd5f  movzx   ecx, ax
0x18008fd62  or      ecx, 80070000h
0x18008fd68  test    ecx, ecx
0x18008fd6a  js      loc_18009014C
0x18008fd70  mov     rdx, [rbp+57h+var_B8]
0x18008fd74  test    rdx, rdx
0x18008fd77  jz      loc_18009014C
0x18008fd7d  mov     r15d, edi
0x18008fd80  mov     [rbp+57h+var_C0], edi
0x18008fd83  cmp     [rdx], edi
0x18008fd85  jbe     loc_18009007F
0x18008fd8b  lea     r13, aLpaserviceesim; "LpaServiceEsimManager"
0x18008fd92  mov     dword ptr [rbp+57h+Data], edi
0x18008fd95  mov     [rbp+57h+var_A8], rdi
0x18008fd99  mov     r12, rdi
0x18008fd9c  mov     eax, r15d
0x18008fd9f  imul    rcx, rax, 24Ch
0x18008fda6  lea     r14, [rdx+4]
0x18008fdaa  add     r14, rcx
0x18008fdad  mov     eax, cs:CallbackContext
0x18008fdb3  cmp     eax, 4
0x18008fdb6  jbe     short loc_18008FE04
0x18008fdb8  mov     rax, [rbp+57h+var_B8]
0x18008fdbc  mov     ecx, [rax]
0x18008fdbe  mov     [rbp+57h+var_90], ecx
0x18008fdc1  mov     [rbp+57h+var_C8], r14
0x18008fdc5  lea     rax, aLpaEsimmanager_47; "LPA::EsimManager::OnStart"
0x18008fdcc  mov     [rbp+57h+var_B0], rax
0x18008fdd0  mov     [rbp+57h+var_88], r13
0x18008fdd4  lea     rax, [rbp+57h+var_90]
0x18008fdd8  mov     [rsp+110h+var_D8], rax
0x18008fddd  lea     rax, [rbp+57h+var_C8]
0x18008fde1  mov     [rsp+110h+var_E0], rax
0x18008fde6  lea     rax, [rbp+57h+var_B0]
0x18008fdea  mov     [rsp+110h+var_E8], rax
0x18008fdef  lea     rax, [rbp+57h+var_88]
0x18008fdf3  mov     [rsp+110h+var_F0], rax
0x18008fdf8  lea     rdx, word_18012F44A
0x18008fdff  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18008fe04  mov     [rsp+110h+var_D8], rdi
0x18008fe09  mov     [rsp+110h+var_E0], rdi
0x18008fe0e  lea     rax, [rbp+57h+var_A8]
0x18008fe12  mov     [rsp+110h+var_E8], rax
0x18008fe17  lea     rax, [rbp+57h+Data]
0x18008fe1b  mov     [rsp+110h+var_F0], rax
0x18008fe20  xor     r9d, r9d
0x18008fe23  lea     r8d, [r9+7]
0x18008fe27  mov     rdx, r14
0x18008fe2a  mov     rcx, [rsi+50h]
0x18008fe2e  call    cs:__imp_WwanQueryInterface
0x18008fe34  test    eax, eax
0x18008fe36  jnz     short loc_18008FE5E
0x18008fe38  mov     rcx, [rbp+57h+var_A8]
0x18008fe3c  test    rcx, rcx
0x18008fe3f  jz      short loc_18008FE5E
0x18008fe41  mov     [rcx+3E0h], di
0x18008fe48  cmp     [rcx+388h], edi
0x18008fe4e  jnz     short loc_18008FE5E
0x18008fe50  mov     [rcx+2AEh], di
0x18008fe57  lea     r12, [rcx+28Ch]
0x18008fe5e  mov     [rbp+57h+var_A0], rdi
0x18008fe62  lea     rax, [rbp+57h+var_A0]
0x18008fe66  mov     qword ptr [rbp+57h+var_70], rax
0x18008fe6a  mov     qword ptr [rbp+57h+var_70+8], rdi
0x18008fe6e  mov     byte ptr [rbp+57h+var_60], 1
0x18008fe72  mov     [rsp+110h+var_D8], rdi
0x18008fe77  mov     [rsp+110h+var_E0], rdi
0x18008fe7c  lea     rax, [rbp+57h+var_70+8]
0x18008fe80  mov     [rsp+110h+var_E8], rax
0x18008fe85  lea     rax, [rbp+57h+Data]
0x18008fe89  mov     [rsp+110h+var_F0], rax
0x18008fe8e  xor     r9d, r9d
0x18008fe91  lea     r8d, [r9+2Eh]
0x18008fe95  mov     rdx, r14
0x18008fe98  mov     rcx, [rsi+50h]
0x18008fe9c  call    cs:__imp_WwanQueryInterface
0x18008fea2  mov     ebx, eax
0x18008fea4  lea     rcx, [rbp+57h+var_70]
0x18008fea8  call    ??1?$out_param_ptr_t@PEAPEAEV?$unique_ptr@U_WWAN_MULTI_SIM_SLOT_MAPPING_STATUS@@U?$function_deleter@P6AXPEAX@Z$1?WwanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<uchar * *,wistd::unique_ptr<_WWAN_MULTI_SIM_SLOT_MAPPING_STATUS,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>>::~out_param_ptr_t<uchar * *,wistd::unique_ptr<_WWAN_MULTI_SIM_SLOT_MAPPING_STATUS,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>>(void)
0x18008fead  test    ebx, ebx
0x18008feaf  jnz     loc_180090091
0x18008feb5  cmp     dword ptr [rbp+57h+Data], 8
0x18008feb9  jb      loc_180090042
0x18008febf  mov     eax, cs:CallbackContext
0x18008fec5  cmp     eax, 4
0x18008fec8  jbe     short loc_18008FF09
0x18008feca  mov     rax, [rbp+57h+var_A0]
0x18008fece  mov     ecx, [rax]
0x18008fed0  mov     [rbp+57h+var_8C], ecx
0x18008fed3  lea     rax, aLpaEsimmanager_47; "LPA::EsimManager::OnStart"
0x18008feda  mov     [rbp+57h+var_C8], rax
0x18008fede  mov     [rbp+57h+var_B0], r13
0x18008fee2  lea     rax, [rbp+57h+var_8C]
0x18008fee6  mov     [rsp+110h+var_E0], rax
0x18008feeb  lea     rax, [rbp+57h+var_C8]
0x18008feef  mov     [rsp+110h+var_E8], rax
0x18008fef4  lea     rax, [rbp+57h+var_B0]
0x18008fef8  mov     [rsp+110h+var_F0], rax
0x18008fefd  lea     rdx, byte_18012F409
0x18008ff04  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18008ff09  mov     rax, [rbp+57h+var_A0]
0x18008ff0d  cmp     dword ptr [rax], 0
0x18008ff10  jbe     loc_180090040
0x18008ff16  lea     r15, aLpaEsimmanager_47; "LPA::EsimManager::OnStart"
0x18008ff1d  mov     dword ptr [rbp+57h+var_88], edi
0x18008ff20  mov     [rbp+57h+var_C8], 0
0x18008ff28  lea     rax, [rbp+57h+var_C8]
0x18008ff2c  mov     qword ptr [rbp+57h+var_70], rax
0x18008ff30  mov     qword ptr [rbp+57h+var_70+8], 0
0x18008ff38  mov     byte ptr [rbp+57h+var_60], 1
0x18008ff3c  lea     rax, [rbp+57h+var_70+8]
0x18008ff40  mov     [rsp+110h+var_D8], rax
0x18008ff45  lea     rax, [rbp+57h+Data]
0x18008ff49  mov     [rsp+110h+var_E0], rax
0x18008ff4e  mov     [rsp+110h+var_E8], 0
0x18008ff57  lea     rax, [rbp+57h+var_88]
0x18008ff5b  mov     [rsp+110h+var_F0], rax
0x18008ff60  mov     r9d, 4
0x18008ff66  lea     r8d, [r9+20h]
0x18008ff6a  mov     rdx, r14
0x18008ff6d  mov     rcx, [rsi+50h]
0x18008ff71  call    cs:__imp_WwanQueryInterfaceEx
0x18008ff77  mov     ebx, eax
0x18008ff79  lea     rcx, [rbp+57h+var_70]
0x18008ff7d  call    ??1?$out_param_ptr_t@PEAPEAEV?$unique_ptr@U_WWAN_MULTI_SIM_SLOT_MAPPING_STATUS@@U?$function_deleter@P6AXPEAX@Z$1?WwanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<uchar * *,wistd::unique_ptr<_WWAN_MULTI_SIM_SLOT_MAPPING_STATUS,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>>::~out_param_ptr_t<uchar * *,wistd::unique_ptr<_WWAN_MULTI_SIM_SLOT_MAPPING_STATUS,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>>(void)
0x18008ff82  test    ebx, ebx
0x18008ff84  jnz     loc_180090017
0x18008ff8a  cmp     [rbp+57h+var_C8], 0
0x18008ff8f  jz      loc_180090017
0x18008ff95  mov     eax, cs:CallbackContext
0x18008ff9b  cmp     eax, 4
0x18008ff9e  jbe     short loc_18008FFD2
0x18008ffa0  mov     dword ptr [rbp+57h+var_B0], edi
0x18008ffa3  mov     [rbp+57h+var_80], r15
0x18008ffa7  mov     qword ptr [rbp+57h+var_70], r13
0x18008ffab  lea     rax, [rbp+57h+var_B0]
0x18008ffaf  mov     [rsp+110h+var_E0], rax
0x18008ffb4  lea     rax, [rbp+57h+var_80]
0x18008ffb8  mov     [rsp+110h+var_E8], rax
0x18008ffbd  lea     rax, [rbp+57h+var_70]
0x18008ffc1  mov     [rsp+110h+var_F0], rax
0x18008ffc6  lea     rdx, byte_18012F3C9
0x18008ffcd  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18008ffd2  mov     r8, [rbp+57h+var_C8]
0x18008ffd6  add     r8, 54h ; 'T'; unsigned int *
0x18008ffda  mov     rdx, r14; struct _GUID *
0x18008ffdd  lea     rcx, [rsi-28h]; this
0x18008ffe1  call    ?IsEsimInterface@EsimManager@LPA@@AEAA_NAEBU_GUID@@AEBK@Z; LPA::EsimManager::IsEsimInterface(_GUID const &,ulong const &)
0x18008ffe6  test    al, al
  ... truncated ...
```
