# Microsoft::Diagnostics::UtcDecoderHostApiWrapper::Initialize(bool)

- ea: `0x1801cd360`
- end: `0x1801cd844`
- name: `?Initialize@UtcDecoderHostApiWrapper@Diagnostics@Microsoft@@QEAAJ_N@Z`
- size: `1252`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::UtcDecoderHostApiWrapper *__hidden this, bool)`
- caller_count: `2`
- callee_count: `24`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180136cac`
- `0x180193cf4`

## callees

- `0x18002110c`
- `0x18002b7c0`
- `0x18002df00`
- `0x1800346b0`
- `0x1800346dc`
- `0x180034c78`
- `0x180034e50`
- `0x180064e34`
- `0x180064e6c`
- `0x180064e8c`
- `0x18008a4ec`
- `0x1800be80c`
- `0x1800d13c8`
- `0x1800d1484`
- `0x18010fde8`
- `0x18014c8b0`
- `0x1801b5df0`
- `0x1801cd360`
- `0x1801cd84c`
- `0x1801e2d68`
- `0x1801ffb10`
- `0x18020aac0`
- `0x18020bab8`
- `0x18033bbe4`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@_K@Z` at `0x1801cd57c`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@_K@Z` at `0x1801cd595`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@_K@Z` at `0x1801cd57c`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@_K@Z` at `0x1801cd595`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z` at `0x1801cd5e0`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z` at `0x1801cd5e0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801cd397`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801cd397`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1801cd3e5`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1801cd785`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1801cd3e5`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1801cd785`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801cd711`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801cd711`
- `api-ms-win-security-isolationapi-l1-2-0!CreateIsolatedProcess` at `0x1801cd698`
- `api-ms-win-security-isolationapi-l1-2-0!CreateIsolatedProcess` at `0x1801cd698`

## string_xrefs

- `0x1801cd3c1`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\client\utcdecoderhostapiwrapper.cpp`
- `0x1801cd3f7`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\client\utcdecoderhostapiwrapper.cpp`
- `0x1801cd41d`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\client\utcdecoderhostapiwrapper.cpp`
- `0x1801cd4d8`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\client\utcdecoderhostapiwrapper.cpp`
- `0x1801cd6b9`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\client\utcdecoderhostapiwrapper.cpp`
- `0x1801cd71b`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\client\utcdecoderhostapiwrapper.cpp`
- `0x1801cd76c`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\client\utcdecoderhostapiwrapper.cpp`
- `0x1801cd797`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\client\utcdecoderhostapiwrapper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::UtcDecoderHostApiWrapper::Initialize(
        Microsoft::Diagnostics::UtcDecoderHostApiWrapper *this,
        char a2)
{
  HANDLE *v4; // rsi
  void *v5; // rcx
  bool v6; // al
  const char *v8; // r9
  int v9; // eax
  void *v10; // rdx
  void **v11; // r9
  int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  _QWORD *v19; // rax
  WCHAR *v20; // rcx
  int IsolatedProcess; // ebx
  const char *v22; // r9
  unsigned int LastError; // ebx
  const char *v24; // r9
  __int64 v25; // rdx
  const char *v26; // r9
  int v27; // [rsp+20h] [rbp-2B8h]
  int v28; // [rsp+20h] [rbp-2B8h]
  unsigned int v29; // [rsp+40h] [rbp-298h] BYREF
  unsigned int v30[2]; // [rsp+48h] [rbp-290h] BYREF
  __int64 v31; // [rsp+50h] [rbp-288h] BYREF
  __int64 v32; // [rsp+58h] [rbp-280h] BYREF
  __int64 v33; // [rsp+60h] [rbp-278h]
  __int64 v34; // [rsp+68h] [rbp-270h]
  HANDLE hObject[2]; // [rsp+70h] [rbp-268h]
  __int64 v36; // [rsp+80h] [rbp-258h]
  int v37[4]; // [rsp+88h] [rbp-250h] BYREF
  __int128 v38; // [rsp+98h] [rbp-240h]
  __int64 v39; // [rsp+A8h] [rbp-230h]
  _BYTE v40[16]; // [rsp+B0h] [rbp-228h] BYREF
  _BYTE v41[240]; // [rsp+C0h] [rbp-218h] BYREF
  WCHAR Src[4]; // [rsp+1B0h] [rbp-128h] BYREF
  unsigned __int64 v43; // [rsp+1C8h] [rbp-110h]
  _OWORD v44[2]; // [rsp+1D0h] [rbp-108h] BYREF
  _BYTE v45[72]; // [rsp+1F0h] [rbp-E8h] BYREF
  int v46; // [rsp+238h] [rbp-A0h]
  int v47; // [rsp+23Ch] [rbp-9Ch]
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  v4 = (HANDLE *)((char *)this + 16);
  v5 = (void *)*((_QWORD *)this + 2);
  if ( v5 )
    v6 = WaitForSingleObject(v5, 0) == 258;
  else
    v6 = 0;
  if ( a2 )
  {
    if ( v6 && !TerminateProcess(*v4, 1u) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x66,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\client\\utcdecoderhostapiwrapper.cpp",
        v8);
    v9 = Microsoft::Diagnostics::UtcDecoderHostApiWrapper::Unbind(this);
    if ( v9 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x68,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\client\\utcdecoderhostapiwrapper.cpp",
        (const char *)(unsigned int)v9,
        v27);
  }
  else if ( v6 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x60,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\client\\utcdecoderhostapiwrapper.cpp",
      (const char *)0x8000FFFFLL,
      v27);
    return 2147549183LL;
  }
  v32 = 24;
  v33 = 0;
  v34 = 1;
  v31 = 0;
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    (unsigned int)&v31,
    0,
    0,
    (unsigned int)&v32,
    0);
  v33 = 0;
  LODWORD(v34) = 0;
  if ( !*((_QWORD *)this + 1) )
    _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
      (_DWORD)this + 8,
      0,
      0,
      (unsigned int)&v32,
      0);
  *(_QWORD *)v30 = 0;
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    v30,
    0);
  v12 = Microsoft::Diagnostics::DuplicateInheritable(*((HANDLE *)this + 1), v10, (unsigned int)v30, v11);
  v13 = v12;
  if ( v12 >= 0 )
  {
    *(_OWORD *)hObject = 0;
    v36 = 0;
    std::wstring::wstring(Src);
    Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(Src, 1, 0);
    std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v40);
    v14 = std::operator<<<wchar_t>(v41, Src);
    v15 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v14, L" ");
    v16 = std::wostream::operator<<(v15, v31);
    v17 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v16, L" ");
    std::wostream::operator<<(v17, *(_QWORD *)v30);
    v29 = 0;
    v44[0] = *(_OWORD *)&off_18038C630;
    if ( (unsigned __int8)Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(v44, &v29) )
    {
      v18 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v41, L" ");
      std::wostream::operator<<(v18, v29);
    }
    *(_OWORD *)v37 = 0;
    v38 = 0;
    v39 = 0;
    memset_0(v45, 0, 0xD0u);
    v47 = 134218752;
    v46 = 1;
    v19 = (_QWORD *)std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(v40, v44);
    if ( v19[3] > 7u )
      v19 = (_QWORD *)*v19;
    v20 = Src;
    if ( v43 > 7 )
      v20 = *(WCHAR **)Src;
    IsolatedProcess = CreateIsolatedProcess(
                        v20,
                        Microsoft::Diagnostics::UtcDecoderHostApiWrapper::k_utcDecoderHostIsolationContainerName,
                        Microsoft::Diagnostics::UtcDecoderHostApiWrapper::k_utcDecoderHostIsolationContainerName,
                        v19);
    std::wstring::_Tidy_deallocate(v44);
    if ( IsolatedProcess )
    {
      if ( !CloseHandle(hObject[1]) )
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0xA4,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\client\\utcdecoderhostapiwrapper.cpp",
          v24);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        v4,
        hObject[0]);
      v25 = 2000;
      if ( v29 )
        v25 = v29;
      if ( (unsigned __int8)_wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_NKH_Z(
                              &v31,
                              v25) )
      {
        std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbase destructor'(v40);
        std::wstring::_Tidy_deallocate(Src);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v30);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v31);
        return Microsoft::Diagnostics::UtcDecoderHostApiWrapper::Bind((RPC_BINDING_HANDLE *)this);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAD,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\client\\utcdecoderhostapiwrapper.cpp",
          (const char *)0x8000FFFFLL,
          (int)v37);
        if ( !TerminateProcess(*v4, 1u) )
          wil::details::in1diag3::_Log_GetLastError(
            retaddr,
            (void *)0xA9,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\client\\utcdecoderhostapiwrapper.cpp",
            v26);
        std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbase destructor'(v40);
        std::wstring::_Tidy_deallocate(Src);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v30);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v31);
        return 2147549183LL;
      }
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xA2,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\client\\utcdecoderhostapiwrapper.cpp",
                    v22);
      std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbase destructor'(v40);
      std::wstring::_Tidy_deallocate(Src);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v30);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v31);
      return LastError;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x80,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\client\\utcdecoderhostapiwrapper.cpp",
      (const char *)(unsigned int)v12,
      v28);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v30);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v31);
    return v13;
  }
}

```

## disassembly

```asm
0x1801cd360  mov     [rsp+arg_8], rbx
0x1801cd365  mov     [rsp+arg_10], rsi
0x1801cd36a  push    rdi
0x1801cd36b  sub     rsp, 2D0h
0x1801cd372  mov     rax, cs:__security_cookie
0x1801cd379  xor     rax, rsp
0x1801cd37c  mov     [rsp+2D8h+var_18], rax
0x1801cd384  mov     bl, dl
0x1801cd386  mov     rdi, rcx
0x1801cd389  lea     rsi, [rcx+10h]
0x1801cd38d  mov     rcx, [rsi]; hHandle
0x1801cd390  test    rcx, rcx
0x1801cd393  jz      short loc_1801CD3A7
0x1801cd395  xor     edx, edx; dwMilliseconds
0x1801cd397  call    cs:__imp_WaitForSingleObject
0x1801cd39d  cmp     eax, 102h
0x1801cd3a2  setz    al
0x1801cd3a5  jmp     short loc_1801CD3A9
0x1801cd3a7  xor     al, al
0x1801cd3a9  test    bl, bl
0x1801cd3ab  jnz     short loc_1801CD3D9
0x1801cd3ad  test    al, al
0x1801cd3af  jz      short loc_1801CD42E
0x1801cd3b1  mov     rcx, [rsp+2D8h]; this
0x1801cd3b9  mov     ebx, 8000FFFFh
0x1801cd3be  mov     r9d, ebx; char *
0x1801cd3c1  lea     r8, aOnecoreBaseTel_218; "onecore\\base\\telemetry\\utc\\service"...
0x1801cd3c8  mov     edx, 60h ; '`'; void *
0x1801cd3cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801cd3d2  mov     eax, ebx
0x1801cd3d4  jmp     loc_1801CD81E
0x1801cd3d9  test    al, al
0x1801cd3db  jz      short loc_1801CD406
0x1801cd3dd  mov     edx, 1; uExitCode
0x1801cd3e2  mov     rcx, [rsi]; hProcess
0x1801cd3e5  call    cs:__imp_TerminateProcess
0x1801cd3eb  mov     rcx, [rsp+2D8h]; this
0x1801cd3f3  test    eax, eax
0x1801cd3f5  jnz     short loc_1801CD406
0x1801cd3f7  lea     r8, aOnecoreBaseTel_218; "onecore\\base\\telemetry\\utc\\service"...
0x1801cd3fe  lea     edx, [rax+66h]; void *
0x1801cd401  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1801cd406  mov     rcx, rdi; this
0x1801cd409  call    ?Unbind@UtcDecoderHostApiWrapper@Diagnostics@Microsoft@@AEAAJXZ; Microsoft::Diagnostics::UtcDecoderHostApiWrapper::Unbind(void)
0x1801cd40e  mov     rcx, [rsp+2D8h]; this
0x1801cd416  test    eax, eax
0x1801cd418  jns     short loc_1801CD42E
0x1801cd41a  mov     r9d, eax; char *
0x1801cd41d  lea     r8, aOnecoreBaseTel_218; "onecore\\base\\telemetry\\utc\\service"...
0x1801cd424  mov     edx, 68h ; 'h'; void *
0x1801cd429  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801cd42e  mov     [rsp+2D8h+var_280], 18h
0x1801cd437  mov     [rsp+2D8h+var_278], 0
0x1801cd440  mov     [rsp+2D8h+var_270], 1
0x1801cd449  mov     [rsp+2D8h+var_288], 0
0x1801cd452  mov     qword ptr [rsp+2D8h+var_2B8], 0
0x1801cd45b  lea     r9, [rsp+2D8h+var_280]
0x1801cd460  xor     r8d, r8d
0x1801cd463  xor     edx, edx
0x1801cd465  lea     rcx, [rsp+2D8h+var_288]
0x1801cd46a  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1801cd46f  mov     [rsp+2D8h+var_278], 0
0x1801cd478  mov     dword ptr [rsp+2D8h+var_270], 0
0x1801cd480  lea     rbx, [rdi+8]
0x1801cd484  cmp     qword ptr [rbx], 0
0x1801cd488  jnz     short loc_1801CD4A5
0x1801cd48a  mov     qword ptr [rsp+2D8h+var_2B8], 0; int
0x1801cd493  lea     r9, [rsp+2D8h+var_280]
0x1801cd498  xor     r8d, r8d
0x1801cd49b  xor     edx, edx
0x1801cd49d  mov     rcx, rbx
0x1801cd4a0  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1801cd4a5  mov     qword ptr [rsp+2D8h+var_290], 0
0x1801cd4ae  xor     edx, edx
0x1801cd4b0  lea     rcx, [rsp+2D8h+var_290]
0x1801cd4b5  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1801cd4ba  lea     r8, [rsp+2D8h+var_290]; unsigned int
0x1801cd4bf  mov     rcx, [rbx]; hSourceHandle
0x1801cd4c2  call    ?DuplicateInheritable@Diagnostics@Microsoft@@YAJPEAXKPEAPEAX@Z; Microsoft::Diagnostics::DuplicateInheritable(void *,ulong,void * *)
0x1801cd4c7  mov     ebx, eax
0x1801cd4c9  test    eax, eax
0x1801cd4cb  jns     short loc_1801CD506
0x1801cd4cd  mov     rcx, [rsp+2D8h]; this
0x1801cd4d5  mov     r9d, eax; char *
0x1801cd4d8  lea     r8, aOnecoreBaseTel_218; "onecore\\base\\telemetry\\utc\\service"...
0x1801cd4df  mov     edx, 80h; void *
0x1801cd4e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801cd4e9  nop
0x1801cd4ea  lea     rcx, [rsp+2D8h+var_290]
0x1801cd4ef  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801cd4f4  nop
0x1801cd4f5  lea     rcx, [rsp+2D8h+var_288]
0x1801cd4fa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801cd4ff  mov     eax, ebx
0x1801cd501  jmp     loc_1801CD81E
0x1801cd506  xorps   xmm0, xmm0
0x1801cd509  xor     eax, eax
0x1801cd50b  movups  xmmword ptr [rsp+2D8h+hObject], xmm0
0x1801cd510  mov     [rsp+2D8h+var_258], rax
0x1801cd518  lea     rdx, ?k_utcDecoderHostBinaryPath@UtcDecoderHostApiWrapper@Diagnostics@Microsoft@@0V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::UtcDecoderHostApiWrapper::k_utcDecoderHostBinaryPath
0x1801cd51f  lea     rcx, [rsp+2D8h+Src]
0x1801cd527  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x1801cd52c  nop
0x1801cd52d  xor     r8d, r8d
0x1801cd530  mov     dl, 1
0x1801cd532  lea     rcx, [rsp+2D8h+Src]; lpSrc
0x1801cd53a  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x1801cd53f  lea     rcx, [rsp+2D8h+var_228]
0x1801cd547  call    ??0?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)
0x1801cd54c  nop
0x1801cd54d  lea     rdx, [rsp+2D8h+Src]
0x1801cd555  lea     rcx, [rsp+2D8h+var_218]
0x1801cd55d  call    ??$?6_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@@Z; std::operator<<<wchar_t>(std::wostream &,std::wstring const &)
0x1801cd562  lea     rbx, asc_1803933B4; " "
0x1801cd569  mov     rdx, rbx
0x1801cd56c  mov     rcx, rax
0x1801cd56f  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x1801cd574  mov     rdx, [rsp+2D8h+var_288]
0x1801cd579  mov     rcx, rax
0x1801cd57c  call    cs:__imp_??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@_K@Z; std::wostream::operator<<(unsigned __int64)
0x1801cd582  mov     rdx, rbx
0x1801cd585  mov     rcx, rax
0x1801cd588  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x1801cd58d  mov     rdx, qword ptr [rsp+2D8h+var_290]
0x1801cd592  mov     rcx, rax
0x1801cd595  call    cs:__imp_??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@_K@Z; std::wostream::operator<<(unsigned __int64)
0x1801cd59b  mov     [rsp+2D8h+var_298], 0
0x1801cd5a3  movups  xmm0, xmmword ptr cs:off_18038C630; "DecoderHostStartupDelay"
0x1801cd5aa  movdqu  [rsp+2D8h+var_108], xmm0
0x1801cd5b3  lea     rdx, [rsp+2D8h+var_298]
0x1801cd5b8  lea     rcx, [rsp+2D8h+var_108]
0x1801cd5c0  call    ?IsTestHookEnabled@General@Utils@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAK@Z; Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(std::wstring_view,ulong &)
0x1801cd5c5  test    al, al
0x1801cd5c7  jz      short loc_1801CD5E6
0x1801cd5c9  mov     rdx, rbx
0x1801cd5cc  lea     rcx, [rsp+2D8h+var_218]
0x1801cd5d4  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x1801cd5d9  mov     edx, [rsp+2D8h+var_298]
0x1801cd5dd  mov     rcx, rax
0x1801cd5e0  call    cs:__imp_??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z; std::wostream::operator<<(ulong)
0x1801cd5e6  xorps   xmm0, xmm0
0x1801cd5e9  xor     eax, eax
0x1801cd5eb  movups  xmmword ptr [rsp+2D8h+var_250], xmm0
0x1801cd5f3  movups  [rsp+2D8h+var_240], xmm0
0x1801cd5fb  mov     [rsp+2D8h+var_230], rax
0x1801cd603  xor     edx, edx; Val
0x1801cd605  mov     r8d, 0D0h; Size
0x1801cd60b  lea     rcx, [rsp+2D8h+var_E8]; void *
0x1801cd613  call    memset_0
0x1801cd618  mov     [rsp+2D8h+var_9C], 8000400h
0x1801cd623  mov     [rsp+2D8h+var_A0], 1
0x1801cd62e  lea     rdx, [rsp+2D8h+var_108]
0x1801cd636  lea     rcx, [rsp+2D8h+var_228]
0x1801cd63e  call    ?str@?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(void)
0x1801cd643  cmp     qword ptr [rax+18h], 7
0x1801cd648  jbe     short loc_1801CD64D
0x1801cd64a  mov     rax, [rax]
0x1801cd64d  mov     rdx, cs:?k_utcDecoderHostIsolationContainerName@UtcDecoderHostApiWrapper@Diagnostics@Microsoft@@0V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::UtcDecoderHostApiWrapper::k_utcDecoderHostIsolationContainerName
0x1801cd654  lea     rcx, [rsp+2D8h+Src]
0x1801cd65c  cmp     [rsp+2D8h+var_110], 7
0x1801cd665  cmova   rcx, qword ptr [rsp+2D8h+Src]
0x1801cd66e  lea     r8, [rsp+2D8h+hObject]
0x1801cd673  mov     [rsp+2D8h+var_2A8], r8
0x1801cd678  lea     r8, [rsp+2D8h+var_E8]
0x1801cd680  mov     [rsp+2D8h+var_2B0], r8
0x1801cd685  lea     r8, [rsp+2D8h+var_250]
0x1801cd68d  mov     qword ptr [rsp+2D8h+var_2B8], r8; int
0x1801cd692  mov     r9, rax
0x1801cd695  mov     r8, rdx
0x1801cd698  call    cs:__imp_CreateIsolatedProcess
0x1801cd69e  mov     ebx, eax
0x1801cd6a0  lea     rcx, [rsp+2D8h+var_108]
0x1801cd6a8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801cd6ad  test    ebx, ebx
0x1801cd6af  jnz     short loc_1801CD704
0x1801cd6b1  mov     rcx, [rsp+2D8h]; this
0x1801cd6b9  lea     r8, aOnecoreBaseTel_218; "onecore\\base\\telemetry\\utc\\service"...
0x1801cd6c0  mov     edx, 0A2h; void *
0x1801cd6c5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801cd6ca  mov     ebx, eax
0x1801cd6cc  lea     rcx, [rsp+2D8h+var_228]
0x1801cd6d4  call    ??_D?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAXXZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbase destructor'(void)
0x1801cd6d9  nop
0x1801cd6da  lea     rcx, [rsp+2D8h+Src]
0x1801cd6e2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801cd6e7  nop
0x1801cd6e8  lea     rcx, [rsp+2D8h+var_290]
0x1801cd6ed  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801cd6f2  nop
0x1801cd6f3  lea     rcx, [rsp+2D8h+var_288]
0x1801cd6f8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801cd6fd  mov     eax, ebx
0x1801cd6ff  jmp     loc_1801CD81E
0x1801cd704  mov     rbx, [rsp+2D8h]
0x1801cd70c  mov     rcx, [rsp+2D8h+hObject+8]; hObject
0x1801cd711  call    cs:__imp_CloseHandle
0x1801cd717  test    eax, eax
0x1801cd719  jnz     short loc_1801CD72F
0x1801cd71b  lea     r8, aOnecoreBaseTel_218; "onecore\\base\\telemetry\\utc\\service"...
0x1801cd722  mov     edx, 0A4h; void *
0x1801cd727  mov     rcx, rbx; this
0x1801cd72a  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1801cd72f  mov     rdx, [rsp+2D8h+hObject]
0x1801cd734  mov     rcx, rsi
0x1801cd737  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1801cd73c  mov     edx, 7D0h
0x1801cd741  mov     eax, [rsp+2D8h+var_298]
0x1801cd745  test    eax, eax
0x1801cd747  cmovnz  edx, eax
0x1801cd74a  lea     rcx, [rsp+2D8h+var_288]
0x1801cd74f  call    ?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA_NKH@Z
0x1801cd754  test    al, al
0x1801cd756  jnz     loc_1801CD7DE
0x1801cd75c  mov     rcx, [rsp+2D8h]; this
0x1801cd764  mov     ebx, 8000FFFFh
0x1801cd769  mov     r9d, ebx; char *
0x1801cd76c  lea     r8, aOnecoreBaseTel_218; "onecore\\base\\telemetry\\utc\\service"...
0x1801cd773  mov     edx, 0ADh; void *
0x1801cd778  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801cd77d  mov     edx, 1; uExitCode
0x1801cd782  mov     rcx, [rsi]; hProcess
0x1801cd785  call    cs:__imp_TerminateProcess
0x1801cd78b  mov     rcx, [rsp+2D8h]; this
0x1801cd793  test    eax, eax
0x1801cd795  jnz     short loc_1801CD7A9
0x1801cd797  lea     r8, aOnecoreBaseTel_218; "onecore\\base\\telemetry\\utc\\service"...
0x1801cd79e  mov     edx, 0A9h; void *
0x1801cd7a3  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1801cd7a8  nop
0x1801cd7a9  lea     rcx, [rsp+2D8h+var_228]
0x1801cd7b1  call    ??_D?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAXXZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbase destructor'(void)
0x1801cd7b6  nop
0x1801cd7b7  lea     rcx, [rsp+2D8h+Src]
0x1801cd7bf  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801cd7c4  nop
0x1801cd7c5  lea     rcx, [rsp+2D8h+var_290]
0x1801cd7ca  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801cd7cf  nop
0x1801cd7d0  lea     rcx, [rsp+2D8h+var_288]
0x1801cd7d5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801cd7da  mov     eax, ebx
0x1801cd7dc  jmp     short loc_1801CD81E
0x1801cd7de  lea     rcx, [rsp+2D8h+var_228]
0x1801cd7e6  call    ??_D?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAXXZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbase destructor'(void)
0x1801cd7eb  nop
0x1801cd7ec  lea     rcx, [rsp+2D8h+Src]
0x1801cd7f4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801cd7f9  nop
0x1801cd7fa  lea     rcx, [rsp+2D8h+var_290]
0x1801cd7ff  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801cd804  nop
0x1801cd805  lea     rcx, [rsp+2D8h+var_288]
0x1801cd80a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801cd80f  nop
0x1801cd810  mov     rcx, rdi; Binding
0x1801cd813  call    ?Bind@UtcDecoderHostApiWrapper@Diagnostics@Microsoft@@AEAAJXZ; Microsoft::Diagnostics::UtcDecoderHostApiWrapper::Bind(void)
0x1801cd818  jmp     short loc_1801CD81E
0x1801cd81a  mov     eax, [rsp+2D8h+var_298]
0x1801cd81e  mov     rcx, [rsp+2D8h+var_18]
0x1801cd826  xor     rcx, rsp; StackCookie
0x1801cd829  call    __security_check_cookie
0x1801cd82e  lea     r11, [rsp+2D8h+var_8]
0x1801cd836  mov     rbx, [r11+18h]
0x1801cd83a  mov     rsi, [r11+20h]
0x1801cd83e  mov     rsp, r11
0x1801cd841  pop     rdi
0x1801cd842  retn
```
