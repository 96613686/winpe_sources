# CReboundProgress::Initialize(CCbsSession *)

- ea: `0x1800b3004`
- end: `0x1800b323f`
- name: `?Initialize@CReboundProgress@@QEAAJPEAVCCbsSession@@@Z`
- size: `571`
- prototype: `__int64 __fastcall(CReboundProgress *__hidden this, struct CCbsSession *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800fcb34`

## callees

- `0x18001387c`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800a02ec`
- `0x1800a9034`
- `0x1800a95e4`
- `0x1800b3004`
- `0x1800eb920`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800b30b1`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800b30b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b30c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b312b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b30c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b312b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800b3100`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800b3100`

## string_xrefs

- `0x1800b314e`: `Failed to create progress thread.`
- `0x1800b318a`: `Failed to create done event.`

## pseudocode

```c
int __fastcall CReboundProgress::Initialize(CReboundProgress *this, struct CCbsSession *a2)
{
  unsigned int v3; // ebx
  int v4; // edx
  __int64 v5; // rdx
  wil::details *v7; // rcx
  HANDLE Event; // rbx
  HANDLE Thread; // rax
  signed int LastError; // ebx
  int v11; // edx
  unsigned int v12; // eax
  int LastErrorFailHr; // eax
  int v14; // edx
  int dwCreationFlags; // [rsp+20h] [rbp-30h]
  unsigned int dwCreationFlagsa; // [rsp+20h] [rbp-30h]
  unsigned int v17[2]; // [rsp+30h] [rbp-20h] BYREF
  int v18; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  if ( !a2 )
  {
    v3 = -2147024809;
    v18 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No session specified");
      *(_QWORD *)v17 = &v18;
      LOBYTE(v4) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v4,
        3,
        (unsigned int)": {}",
        (__int64)v17);
    }
    v5 = 1208;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\cbs\\core\\cbsprogressui.cpp",
      (const char *)v3,
      dwCreationFlags);
    return v3;
  }
  Windows::AutoComPtr<CCbsUpdate>::operator=((char *)this + 64, a2);
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      (char *)this + 48,
      Event);
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v7);
    v3 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      v18 = LastErrorFailHr;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to create done event.");
        *(_QWORD *)v17 = &v18;
        LOBYTE(v14) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v14,
          3,
          (unsigned int)": {}",
          (__int64)v17);
      }
      v5 = 1212;
      goto LABEL_5;
    }
  }
  Thread = CreateThread(0, 0, CReboundProgress::ProgressThreadProc, this, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 40,
    Thread);
  if ( ((*((_QWORD *)this + 5) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    return 0;
  LastError = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to create progress thread.");
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    else
      v12 = LastError;
    v18 = v12;
    LOBYTE(v11) = 1;
    *(_QWORD *)v17 = &v18;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v11,
      3,
      (unsigned int)": {0}",
      (__int64)v17);
  }
  if ( !LastError )
    return 0;
  else
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x4BF,
             (unsigned int)"onecore\\base\\cbs\\core\\cbsprogressui.cpp",
             (const char *)(unsigned int)LastError,
             dwCreationFlagsa);
}

```

## disassembly

```asm
0x1800b3004  mov     [rsp-8+arg_10], rbx
0x1800b3009  mov     [rsp-8+arg_18], rdi
0x1800b300e  push    rbp
0x1800b300f  mov     rbp, rsp
0x1800b3012  sub     rsp, 50h
0x1800b3016  mov     rax, cs:__security_cookie
0x1800b301d  xor     rax, rsp
0x1800b3020  mov     [rbp+var_10], rax
0x1800b3024  mov     rdi, rcx
0x1800b3027  test    rdx, rdx
0x1800b302a  jnz     short loc_1800B309A
0x1800b302c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b3033  mov     ebx, 80070057h
0x1800b3038  mov     [rbp+var_18], ebx
0x1800b303b  test    rcx, rcx
0x1800b303e  jz      short loc_1800B307B
0x1800b3040  lea     edi, [rdx+3]
0x1800b3043  mov     r8d, edi
0x1800b3046  lea     r9, aNoSessionSpeci_0; "No session specified"
0x1800b304d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800b3052  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b3059  lea     rax, [rbp+var_18]
0x1800b305d  mov     qword ptr [rbp+var_20], rax
0x1800b3061  lea     r9, asc_1802EE7AC; ": {}"
0x1800b3068  lea     rax, [rbp+var_20]
0x1800b306c  mov     r8d, edi
0x1800b306f  mov     dl, 1
0x1800b3071  mov     qword ptr [rsp+50h+dwCreationFlags], rax; int
0x1800b3076  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b307b  mov     edx, 4B8h; void *
0x1800b3080  mov     rcx, [rbp+8]; this
0x1800b3084  lea     r8, aOnecoreBaseCbs_128; "onecore\\base\\cbs\\core\\cbsprogressui"...
0x1800b308b  mov     r9d, ebx; char *
0x1800b308e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3093  mov     eax, ebx
0x1800b3095  jmp     loc_1800B3222
0x1800b309a  add     rcx, 40h ; '@'
0x1800b309e  call    ??4?$AutoComPtr@VCCbsUpdate@@@Windows@@QEAAAEAV01@PEAVCCbsUpdate@@@Z; Windows::AutoComPtr<CCbsUpdate>::operator=(CCbsUpdate *)
0x1800b30a3  xor     edx, edx; lpName
0x1800b30a5  xor     ecx, ecx; lpEventAttributes
0x1800b30a7  mov     r9d, 1F0003h; dwDesiredAccess
0x1800b30ad  lea     r8d, [rdx+1]; dwFlags
0x1800b30b1  call    cs:__imp_CreateEventExW
0x1800b30b8  nop     dword ptr [rax+rax+00h]
0x1800b30bd  mov     rbx, rax
0x1800b30c0  test    rax, rax
0x1800b30c3  jz      loc_1800B3167
0x1800b30c9  call    cs:__imp_GetLastError
0x1800b30d0  nop     dword ptr [rax+rax+00h]
0x1800b30d5  lea     rcx, [rdi+30h]
0x1800b30d9  mov     rdx, rbx
0x1800b30dc  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800b30e1  mov     [rsp+50h+lpThreadId], 0; lpThreadId
0x1800b30ea  lea     r8, ?ProgressThreadProc@CReboundProgress@@CAKPEAX@Z; lpStartAddress
0x1800b30f1  mov     r9, rdi; lpParameter
0x1800b30f4  mov     [rsp+50h+dwCreationFlags], 0; dwCreationFlags
0x1800b30fc  xor     edx, edx; dwStackSize
0x1800b30fe  xor     ecx, ecx; lpThreadAttributes
0x1800b3100  call    cs:__imp_CreateThread
0x1800b3107  nop     dword ptr [rax+rax+00h]
0x1800b310c  mov     rdx, rax
0x1800b310f  lea     rcx, [rdi+28h]
0x1800b3113  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800b3118  mov     rax, [rdi+28h]
0x1800b311c  inc     rax
0x1800b311f  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800b3125  jnz     loc_1800B3220
0x1800b312b  call    cs:__imp_GetLastError
0x1800b3132  nop     dword ptr [rax+rax+00h]
0x1800b3137  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b313e  mov     ebx, eax
0x1800b3140  test    rcx, rcx
0x1800b3143  jz      loc_1800B3202
0x1800b3149  mov     edi, 3
0x1800b314e  lea     r9, aFailedToCreate_52; "Failed to create progress thread."
0x1800b3155  mov     r8d, edi
0x1800b3158  xor     edx, edx
0x1800b315a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800b315f  test    ebx, ebx
0x1800b3161  jg      short loc_1800B31CE
0x1800b3163  mov     eax, ebx
0x1800b3165  jmp     short loc_1800B31D6
0x1800b3167  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800b316c  mov     ebx, eax
0x1800b316e  test    eax, eax
0x1800b3170  jns     loc_1800B30E1
0x1800b3176  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b317d  mov     [rbp+var_18], eax
0x1800b3180  test    rcx, rcx
0x1800b3183  jz      short loc_1800B31C4
0x1800b3185  mov     edi, 3
0x1800b318a  lea     r9, aFailedToCreate_87; "Failed to create done event."
0x1800b3191  mov     r8d, edi
0x1800b3194  xor     edx, edx
0x1800b3196  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800b319b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b31a2  lea     rax, [rbp+var_18]
0x1800b31a6  mov     qword ptr [rbp+var_20], rax
0x1800b31aa  lea     r9, asc_1802EE7AC; ": {}"
0x1800b31b1  lea     rax, [rbp+var_20]
0x1800b31b5  mov     r8d, edi
0x1800b31b8  mov     dl, 1
0x1800b31ba  mov     qword ptr [rsp+50h+dwCreationFlags], rax
0x1800b31bf  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b31c4  mov     edx, 4BCh
0x1800b31c9  jmp     loc_1800B3080
0x1800b31ce  movzx   eax, bx
0x1800b31d1  or      eax, 80070000h
0x1800b31d6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b31dd  lea     r9, a0; ": {0}"
0x1800b31e4  mov     [rbp+var_18], eax
0x1800b31e7  mov     r8d, edi
0x1800b31ea  lea     rax, [rbp+var_18]
0x1800b31ee  mov     dl, 1
0x1800b31f0  mov     qword ptr [rbp+var_20], rax
0x1800b31f4  lea     rax, [rbp+var_20]
0x1800b31f8  mov     qword ptr [rsp+50h+dwCreationFlags], rax; unsigned int
0x1800b31fd  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b3202  test    ebx, ebx
0x1800b3204  jz      short loc_1800B3220
0x1800b3206  mov     rcx, [rbp+8]; this
0x1800b320a  lea     r8, aOnecoreBaseCbs_128; "onecore\\base\\cbs\\core\\cbsprogressui"...
0x1800b3211  mov     r9d, ebx; char *
0x1800b3214  mov     edx, 4BFh; void *
0x1800b3219  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800b321e  jmp     short loc_1800B3222
0x1800b3220  xor     eax, eax
0x1800b3222  mov     rcx, [rbp+var_10]
0x1800b3226  xor     rcx, rsp; StackCookie
0x1800b3229  call    __security_check_cookie
0x1800b322e  mov     rbx, [rsp+50h+arg_10]
0x1800b3233  mov     rdi, [rsp+50h+arg_18]
0x1800b3238  add     rsp, 50h
0x1800b323c  pop     rbp
0x1800b323d  retn
```
