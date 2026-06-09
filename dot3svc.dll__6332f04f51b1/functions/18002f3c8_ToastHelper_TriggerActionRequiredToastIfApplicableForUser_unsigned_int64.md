# ToastHelper::_TriggerActionRequiredToastIfApplicableForUser(unsigned __int64)

- ea: `0x18002f3c8`
- end: `0x18002f8ff`
- name: `?_TriggerActionRequiredToastIfApplicableForUser@ToastHelper@@AEAAJ_K@Z`
- size: `1335`
- prototype: `__int64 __fastcall(ToastHelper *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002f908`

## callees

- `0x180002a34`
- `0x1800084ec`
- `0x18000a9c0`
- `0x18000c230`
- `0x18001bca0`
- `0x18001bd4c`
- `0x180028758`
- `0x180029268`
- `0x1800292fc`
- `0x1800293ec`
- `0x180029d14`
- `0x18002a1e8`
- `0x18002a230`
- `0x18002b2ac`
- `0x18002b484`
- `0x18002b6f8`
- `0x18002b848`
- `0x18002bc00`
- `0x18002bdf0`
- `0x18002c7d8`
- `0x18002cdec`
- `0x18002d5a0`
- `0x18002dfd0`
- `0x18002e024`
- `0x18002e668`
- `0x18002e7a4`
- `0x18002ede0`
- `0x18002f0e8`
- `0x18002f3c8`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x18002f6a6`
- `msvcp_win!_Xtime_get_ticks` at `0x18002f6d9`
- `msvcp_win!_Xtime_get_ticks` at `0x18002f769`
- `msvcp_win!_Xtime_get_ticks` at `0x18002f79b`
- `msvcp_win!_Xtime_get_ticks` at `0x18002f84d`
- `msvcp_win!_Xtime_get_ticks` at `0x18002f866`
- `msvcp_win!_Xtime_get_ticks` at `0x18002f6a6`
- `msvcp_win!_Xtime_get_ticks` at `0x18002f6d9`
- `msvcp_win!_Xtime_get_ticks` at `0x18002f769`
- `msvcp_win!_Xtime_get_ticks` at `0x18002f79b`
- `msvcp_win!_Xtime_get_ticks` at `0x18002f84d`
- `msvcp_win!_Xtime_get_ticks` at `0x18002f866`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18002f3fa`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18002f3fa`

## pseudocode

```c
__int64 __fastcall ToastHelper::_TriggerActionRequiredToastIfApplicableForUser(ToastHelper *this, unsigned __int64 a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 result; // rax
  int v7; // eax
  unsigned int v8; // ebx
  struct ToastNotifierForUser *v9; // rbx
  void (__fastcall ***v10)(_QWORD, __int64 *, __int64 **); // rcx
  __int64 *v11; // rsi
  __int64 v12; // rcx
  unsigned int v13; // eax
  __int64 *v14; // rdx
  unsigned int *v15; // rax
  char v16; // si
  unsigned int *v17; // rax
  int v18; // eax
  __int64 ticks; // rax
  wil *v20; // rcx
  int v21; // eax
  const char *v22; // r9
  struct ToastNotifierForUser *v23; // [rsp+20h] [rbp-E8h] BYREF
  std::_Ref_count_base *v24; // [rsp+28h] [rbp-E0h]
  unsigned __int64 *v25; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v26; // [rsp+38h] [rbp-D0h] BYREF
  unsigned __int64 v27; // [rsp+40h] [rbp-C8h] BYREF
  __int64 *v28; // [rsp+48h] [rbp-C0h] BYREF
  std::_Ref_count_base *v29; // [rsp+50h] [rbp-B8h]
  _BYTE v30[40]; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v31[17]; // [rsp+80h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]
  __int64 v34; // [rsp+118h] [rbp+10h] BYREF
  __int64 v35; // [rsp+120h] [rbp+18h] BYREF
  __int64 v36; // [rsp+128h] [rbp+20h] BYREF

  v34 = a2;
  v35 = 0;
  v4 = UMgrQueryUserToken(a2, &v35);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecoreuap\\net\\dot3\\ac\\server\\toasthelper.cpp",
      (const char *)(unsigned int)v4,
      (int)v23);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v35);
    return v5;
  }
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA6,
      (unsigned int)"onecoreuap\\net\\dot3\\ac\\server\\toasthelper.cpp",
      (const char *)0x8000FFFFLL,
      (int)v23);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v35);
    return 2147549183LL;
  }
  v7 = ToastHelper::RegisterToastApplicationForUser(a2);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA8,
      (unsigned int)"onecoreuap\\net\\dot3\\ac\\server\\toasthelper.cpp",
      (const char *)(unsigned int)v7,
      (int)v23);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v35);
    return v8;
  }
  ToastHelper::_GetToastNotifierForUser(this, &v23, a2);
  try
  {
    v9 = v23;
    if ( !v23 )
    {
      winrt::Windows::System::Internal::UserManager::GetUserForContext((unsigned __int64)&v27);
      v25 = &v27;
      v28 = &qword_180052B38;
      _InterlockedIncrement64(&qword_180052B38);
      if ( winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics4> )
      {
        _lambda_51cb1c784431ef1021794bfebdc3ae41_::operator()(
          &v25,
          &v36,
          &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics4>);
        _InterlockedDecrement64(&qword_180052B38);
      }
      else
      {
        _InterlockedDecrement64(&qword_180052B38);
        winrt::impl::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics4>::call<_lambda_51cb1c784431ef1021794bfebdc3ae41_ &>(
          v10,
          (__int64)&v36,
          (__int64)&v25);
      }
      winrt::param::hstring::hstring((winrt::param::hstring *)v30, L"Windows.SystemToast.Ethernet");
      winrt::impl::consume_Windows_UI_Notifications_IToastNotificationManagerForUser<winrt::Windows::UI::Notifications::IToastNotificationManagerForUser>::CreateToastNotifier(
        &v36,
        &v26,
        v30);
      v11 = (__int64 *)operator new(0x60u);
      *((_DWORD *)v11 + 2) = 1;
      *((_DWORD *)v11 + 3) = 1;
      *v11 = (__int64)&std::_Ref_count_obj2<ToastNotifierForUser>::`vftable';
      std::_Construct_in_place<ToastNotifierForUser,unsigned __int64 const &,winrt::Windows::UI::Notifications::ToastNotifier const &>(
        v11 + 2,
        &v34,
        &v26);
      v28 = v11 + 2;
      v29 = (std::_Ref_count_base *)v11;
      std::shared_ptr<ToastNotifierForUser>::operator=(&v23, &v28);
      if ( v29 )
        std::_Ref_count_base::_Decref(v29);
      v12 = *((_QWORD *)this + 6);
      if ( v12 == *((_QWORD *)this + 7) )
      {
        std::vector<std::shared_ptr<ToastNotifierForUser>>::_Emplace_reallocate<std::shared_ptr<ToastNotifierForUser> const &>(
          (char *)this + 40,
          *((_QWORD *)this + 6),
          &v23);
      }
      else
      {
        std::_Construct_in_place<std::shared_ptr<ToastNotifierForUser>,std::shared_ptr<ToastNotifierForUser> const &>(
          v12,
          &v23);
        *((_QWORD *)this + 6) += 16LL;
      }
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v26);
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v36);
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v27);
      v9 = v23;
    }
    if ( (unsigned int)winrt::impl::consume_Windows_UI_Notifications_IToastNotifier<winrt::Windows::UI::Notifications::IToastNotifier>::Setting((char *)v9 + 8) )
    {
      v13 = winrt::impl::consume_Windows_UI_Notifications_IToastNotifier<winrt::Windows::UI::Notifications::IToastNotifier>::Setting((char *)v9 + 8);
      ToastHelper::_LogSendingToast(this, v13, -2147023673);
      if ( !v24 )
      {
LABEL_50:
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v35);
        return 0;
      }
    }
    else
    {
      if ( !*((_BYTE *)v9 + 56) )
        goto LABEL_31;
      v14 = &ToastHelper::ToastLongerCooldown;
      if ( !*((_BYTE *)v9 + 40) )
        v14 = (__int64 *)&ToastHelper::ToastCooldown;
      std::chrono::operator+<int,std::ratio<3600,1>,std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>(
        &v34,
        v14,
        (char *)v9 + 48);
      if ( _Xtime_get_ticks() < v34 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          v36 = _Xtime_get_ticks() - *((_QWORD *)v9 + 6);
          v15 = (unsigned int *)std::chrono::duration_cast<std::chrono::duration<int,std::ratio<60,1>>,__int64,std::ratio<1,10000000>,0>(
                                  &v34,
                                  &v36);
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 19, WPP_9b988db5ce2f34186259e8bb867b7549_Traceguids, *v15);
        }
        if ( !v24 )
          goto LABEL_50;
      }
      else
      {
LABEL_31:
        v16 = 1;
        if ( *((_BYTE *)v9 + 72) )
        {
          std::chrono::operator+<int,std::ratio<3600,1>,std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>(
            &v34,
            ToastHelper::PriorityToastCooldown,
            (char *)v9 + 64);
          if ( v34 >= _Xtime_get_ticks() )
          {
            v16 = 0;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              v36 = _Xtime_get_ticks() - *((_QWORD *)v9 + 8);
              v17 = (unsigned int *)std::chrono::duration_cast<std::chrono::duration<int,std::ratio<60,1>>,__int64,std::ratio<1,10000000>,0>(
                                      &v34,
                                      &v36);
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 20, WPP_9b988db5ce2f34186259e8bb867b7549_Traceguids, *v17);
            }
          }
        }
        v18 = ToastHelper::_ClearAllExistingToastsForUser(this, v9);
        if ( v18 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xDC,
            (int)"onecoreuap\\net\\dot3\\ac\\server\\toasthelper.cpp",
            (const char *)(unsigned int)v18);
        ToastHelper::_CreateToast((__int64)this, v31, v16, a2);
        winrt::impl::consume_Windows_UI_Notifications_IToastNotifier<winrt::Windows::UI::Notifications::IToastNotifier>::Show(
          (char *)v9 + 8,
          v31);
        std::vector<Toast>::emplace_back<Toast>((char *)v9 + 16, v31);
        ticks = _Xtime_get_ticks();
        if ( !*((_BYTE *)v9 + 56) )
          *((_BYTE *)v9 + 56) = 1;
        *((_QWORD *)v9 + 6) = ticks;
        if ( v16 )
        {
          *((_QWORD *)v9 + 8) = _Xtime_get_ticks();
          if ( !*((_BYTE *)v9 + 72) )
            *((_BYTE *)v9 + 72) = 1;
        }
        ToastHelper::_LogSendingToast(this, 0, 0);
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control[1].Flink, 21, WPP_9b988db5ce2f34186259e8bb867b7549_Traceguids);
        }
        Toast::~Toast((Toast *)v31);
        if ( !v24 )
          goto LABEL_50;
      }
    }
    std::_Ref_count_base::_Decref(v24);
    goto LABEL_50;
  }
  catch ( ... )
  {
    v21 = wil::ResultFromCaughtException(v20);
    ToastHelper::_LogSendingToast(this, 0, v21);
    LODWORD(v34) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0xF2,
                     (unsigned int)"onecoreuap\\net\\dot3\\ac\\server\\toasthelper.cpp",
                     v22);
    return (unsigned int)v34;
  }
  return result;
}

```

## disassembly

```asm
0x18002f3c8  mov     rax, rsp
0x18002f3cb  mov     [rax+10h], rdx
0x18002f3cf  mov     [rax+8], rcx
0x18002f3d3  push    rbx
0x18002f3d4  push    rsi
0x18002f3d5  push    rdi
0x18002f3d6  push    r12
0x18002f3d8  push    r13
0x18002f3da  push    r14
0x18002f3dc  push    r15
0x18002f3de  sub     rsp, 0D0h
0x18002f3e5  mov     rdi, rdx
0x18002f3e8  mov     r15, rcx
0x18002f3eb  mov     qword ptr [rax+18h], 0
0x18002f3f3  lea     rdx, [rax+18h]
0x18002f3f7  mov     rcx, rdi
0x18002f3fa  call    cs:__imp_UMgrQueryUserToken
0x18002f400  mov     ebx, eax
0x18002f402  test    eax, eax
0x18002f404  jns     short loc_18002F437
0x18002f406  mov     rcx, [rsp+108h]; this
0x18002f40e  mov     r9d, eax; char *
0x18002f411  lea     r8, aOnecoreuapNetD_1; "onecoreuap\\net\\dot3\\ac\\server\\toas"...
0x18002f418  mov     edx, 0A5h; void *
0x18002f41d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f422  nop
0x18002f423  lea     rcx, [rsp+108h+arg_10]
0x18002f42b  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002f430  mov     eax, ebx
0x18002f432  jmp     loc_18002F8EB
0x18002f437  test    rdi, rdi
0x18002f43a  jnz     short loc_18002F472
0x18002f43c  mov     rcx, [rsp+108h]; this
0x18002f444  mov     ebx, 8000FFFFh
0x18002f449  mov     r9d, ebx; char *
0x18002f44c  lea     r8, aOnecoreuapNetD_1; "onecoreuap\\net\\dot3\\ac\\server\\toas"...
0x18002f453  mov     edx, 0A6h; void *
0x18002f458  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f45d  nop
0x18002f45e  lea     rcx, [rsp+108h+arg_10]
0x18002f466  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002f46b  mov     eax, ebx
0x18002f46d  jmp     loc_18002F8EB
0x18002f472  mov     rcx, rdi; unsigned __int64
0x18002f475  call    ?RegisterToastApplicationForUser@ToastHelper@@CAJ_K@Z; ToastHelper::RegisterToastApplicationForUser(unsigned __int64)
0x18002f47a  mov     ebx, eax
0x18002f47c  test    eax, eax
0x18002f47e  jns     short loc_18002F4B1
0x18002f480  mov     rcx, [rsp+108h]; this
0x18002f488  mov     r9d, eax; char *
0x18002f48b  lea     r8, aOnecoreuapNetD_1; "onecoreuap\\net\\dot3\\ac\\server\\toas"...
0x18002f492  mov     edx, 0A8h; void *
0x18002f497  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f49c  nop
0x18002f49d  lea     rcx, [rsp+108h+arg_10]
0x18002f4a5  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002f4aa  mov     eax, ebx
0x18002f4ac  jmp     loc_18002F8EB
0x18002f4b1  mov     r8, rdi
0x18002f4b4  lea     rdx, [rsp+108h+var_E8]
0x18002f4b9  mov     rcx, r15
0x18002f4bc  call    ?_GetToastNotifierForUser@ToastHelper@@AEAA?AV?$shared_ptr@UToastNotifierForUser@@@std@@_K@Z; ToastHelper::_GetToastNotifierForUser(unsigned __int64)
0x18002f4c1  nop
0x18002f4c2  mov     rbx, [rsp+108h+var_E8]
0x18002f4c7  test    rbx, rbx
0x18002f4ca  jnz     loc_18002F628
0x18002f4d0  mov     rdx, rdi
0x18002f4d3  lea     rcx, [rsp+108h+var_C8]; unsigned __int64
0x18002f4d8  call    ?GetUserForContext@UserManager@Internal@System@Windows@winrt@@SA@_K@Z; winrt::Windows::System::Internal::UserManager::GetUserForContext(unsigned __int64)
0x18002f4dd  nop
0x18002f4de  lea     rax, [rsp+108h+var_C8]
0x18002f4e3  mov     [rsp+108h+var_D8], rax
0x18002f4e8  lea     rax, qword_180052B38
0x18002f4ef  mov     [rsp+108h+var_C0], rax
0x18002f4f4  lock inc cs:qword_180052B38
0x18002f4fc  cmp     cs:??$factory_cache_entry_v@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics4@2345@@impl@winrt@@3U?$factory_cache_entry@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics4@2345@@12@A, rbx; factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics4>::winrt::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics4> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics4>
0x18002f503  jz      short loc_18002F529
0x18002f505  lea     r8, ??$factory_cache_entry_v@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics4@2345@@impl@winrt@@3U?$factory_cache_entry@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics4@2345@@12@A; factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics4>::winrt::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics4> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics4>
0x18002f50c  lea     rdx, [rsp+108h+arg_18]
0x18002f514  lea     rcx, [rsp+108h+var_D8]
0x18002f519  call    ??R_lambda_51cb1c784431ef1021794bfebdc3ae41_@@QEBA@AEBUIToastNotificationManagerStatics4@Notifications@UI@Windows@winrt@@@Z; _lambda_51cb1c784431ef1021794bfebdc3ae41_::operator()(winrt::Windows::UI::Notifications::IToastNotificationManagerStatics4 const &)
0x18002f51e  nop
0x18002f51f  lock dec cs:qword_180052B38
0x18002f527  jmp     short loc_18002F544
0x18002f529  lock dec cs:qword_180052B38
0x18002f531  lea     r8, [rsp+108h+var_D8]
0x18002f536  lea     rdx, [rsp+108h+arg_18]
0x18002f53e  call    ??$call@AEAV_lambda_51cb1c784431ef1021794bfebdc3ae41_@@@?$factory_cache_entry@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics4@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_51cb1c784431ef1021794bfebdc3ae41_@@@Z
0x18002f543  nop
0x18002f544  lea     rdx, aWindowsSystemt; "Windows.SystemToast.Ethernet"
0x18002f54b  lea     rcx, [rsp+108h+var_B0]; this
0x18002f550  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18002f555  lea     r8, [rsp+108h+var_B0]
0x18002f55a  lea     rdx, [rsp+108h+var_D0]
0x18002f55f  lea     rcx, [rsp+108h+arg_18]
0x18002f567  call    ?CreateToastNotifier@?$consume_Windows_UI_Notifications_IToastNotificationManagerForUser@UIToastNotificationManagerForUser@Notifications@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_UI_Notifications_IToastNotificationManagerForUser<winrt::Windows::UI::Notifications::IToastNotificationManagerForUser>::CreateToastNotifier(winrt::param::hstring const &)
0x18002f56c  nop
0x18002f56d  mov     ecx, 60h ; '`'; Size
0x18002f572  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f577  mov     rsi, rax
0x18002f57a  mov     dword ptr [rax+8], 1
0x18002f581  mov     dword ptr [rax+0Ch], 1
0x18002f588  lea     rax, ??_7?$_Ref_count_obj2@UToastNotifierForUser@@@std@@6B@; const std::_Ref_count_obj2<ToastNotifierForUser>::`vftable'
0x18002f58f  mov     [rsi], rax
0x18002f592  lea     rbx, [rsi+10h]
0x18002f596  lea     r8, [rsp+108h+var_D0]
0x18002f59b  lea     rdx, [rsp+108h+arg_8]
0x18002f5a3  mov     rcx, rbx
0x18002f5a6  call    ??$_Construct_in_place@UToastNotifierForUser@@AEB_KAEBUToastNotifier@Notifications@UI@Windows@winrt@@@std@@YAXAEAUToastNotifierForUser@@AEB_KAEBUToastNotifier@Notifications@UI@Windows@winrt@@@Z; std::_Construct_in_place<ToastNotifierForUser,unsigned __int64 const &,winrt::Windows::UI::Notifications::ToastNotifier const &>(ToastNotifierForUser &,unsigned __int64 const &,winrt::Windows::UI::Notifications::ToastNotifier const &)
0x18002f5ab  mov     [rsp+108h+var_C0], rbx
0x18002f5b0  mov     [rsp+108h+var_B8], rsi
0x18002f5b5  lea     rdx, [rsp+108h+var_C0]
0x18002f5ba  lea     rcx, [rsp+108h+var_E8]
0x18002f5bf  call    ??4?$shared_ptr@UToastNotifierForUser@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ToastNotifierForUser>::operator=(std::shared_ptr<ToastNotifierForUser> &&)
0x18002f5c4  mov     rcx, [rsp+108h+var_B8]; this
0x18002f5c9  test    rcx, rcx
0x18002f5cc  jz      short loc_18002F5D3
0x18002f5ce  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002f5d3  mov     rcx, [r15+30h]
0x18002f5d7  cmp     rcx, [r15+38h]
0x18002f5db  jz      short loc_18002F5EE
0x18002f5dd  lea     rdx, [rsp+108h+var_E8]
0x18002f5e2  call    ??$_Construct_in_place@V?$shared_ptr@UToastNotifierForUser@@@std@@AEBV12@@std@@YAXAEAV?$shared_ptr@UToastNotifierForUser@@@0@AEBV10@@Z; std::_Construct_in_place<std::shared_ptr<ToastNotifierForUser>,std::shared_ptr<ToastNotifierForUser> const &>(std::shared_ptr<ToastNotifierForUser> &,std::shared_ptr<ToastNotifierForUser> const &)
0x18002f5e7  add     qword ptr [r15+30h], 10h
0x18002f5ec  jmp     short loc_18002F600
0x18002f5ee  lea     r8, [rsp+108h+var_E8]
0x18002f5f3  mov     rdx, rcx
0x18002f5f6  lea     rcx, [r15+28h]
0x18002f5fa  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@UToastNotifierForUser@@@std@@@?$vector@V?$shared_ptr@UToastNotifierForUser@@@std@@V?$allocator@V?$shared_ptr@UToastNotifierForUser@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@UToastNotifierForUser@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<ToastNotifierForUser>>::_Emplace_reallocate<std::shared_ptr<ToastNotifierForUser> const &>(std::shared_ptr<ToastNotifierForUser> * const,std::shared_ptr<ToastNotifierForUser> const &)
0x18002f5ff  nop
0x18002f600  lea     rcx, [rsp+108h+var_D0]
0x18002f605  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x18002f60a  nop
0x18002f60b  lea     rcx, [rsp+108h+arg_18]
0x18002f613  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x18002f618  nop
0x18002f619  lea     rcx, [rsp+108h+var_C8]
0x18002f61e  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x18002f623  mov     rbx, [rsp+108h+var_E8]
0x18002f628  lea     r12, [rbx+8]
0x18002f62c  mov     rcx, r12
0x18002f62f  call    ?Setting@?$consume_Windows_UI_Notifications_IToastNotifier@UIToastNotifier@Notifications@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Notifications_IToastNotifier<winrt::Windows::UI::Notifications::IToastNotifier>::Setting(void)
0x18002f634  test    eax, eax
0x18002f636  jz      short loc_18002F675
0x18002f638  mov     rcx, r12
0x18002f63b  call    ?Setting@?$consume_Windows_UI_Notifications_IToastNotifier@UIToastNotifier@Notifications@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Notifications_IToastNotifier<winrt::Windows::UI::Notifications::IToastNotifier>::Setting(void)
0x18002f640  mov     r8d, 800704C7h; int
0x18002f646  mov     edx, eax; unsigned int
0x18002f648  mov     rcx, r15; this
0x18002f64b  call    ?_LogSendingToast@ToastHelper@@AEAAXKJ@Z; ToastHelper::_LogSendingToast(ulong,long)
0x18002f650  nop
0x18002f651  mov     rcx, [rsp+108h+var_E0]; this
0x18002f656  test    rcx, rcx
0x18002f659  jz      short loc_18002F661
0x18002f65b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002f660  nop
0x18002f661  lea     rcx, [rsp+108h+arg_10]
0x18002f669  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002f66e  xor     eax, eax
0x18002f670  jmp     loc_18002F8EB
0x18002f675  cmp     byte ptr [rbx+38h], 0
0x18002f679  jz      loc_18002F744
0x18002f67f  lea     rax, ?ToastCooldown@ToastHelper@@2V?$duration@HU?$ratio@$0OBA@$00@std@@@chrono@std@@B; std::chrono::duration<int,std::ratio<3600,1>> const ToastHelper::ToastCooldown
0x18002f686  lea     rdx, ?ToastLongerCooldown@ToastHelper@@2V?$duration@HU?$ratio@$0OBA@$00@std@@@chrono@std@@B; std::chrono::duration<int,std::ratio<3600,1>> const ToastHelper::ToastLongerCooldown
0x18002f68d  cmp     byte ptr [rbx+28h], 0
0x18002f691  cmovz   rdx, rax
0x18002f695  lea     r8, [rbx+30h]
0x18002f699  lea     rcx, [rsp+108h+arg_8]
0x18002f6a1  call    ??$?HHU?$ratio@$0OBA@$00@std@@Usystem_clock@chrono@1@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@31@@chrono@std@@YA?AV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@01@AEBV?$duration@HU?$ratio@$0OBA@$00@std@@@01@AEBV201@@Z; std::chrono::operator+<int,std::ratio<3600,1>,std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>(std::chrono::duration<int,std::ratio<3600,1>> const &,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x18002f6a6  call    cs:__imp__Xtime_get_ticks
0x18002f6ac  cmp     rax, [rsp+108h+arg_8]
0x18002f6b4  jge     loc_18002F744
0x18002f6ba  lea     r14, WPP_GLOBAL_Control
0x18002f6c1  mov     rax, cs:WPP_GLOBAL_Control
0x18002f6c8  cmp     rax, r14
0x18002f6cb  jz      short loc_18002F720
0x18002f6cd  cmp     byte ptr [rax+19h], 4
0x18002f6d1  jb      short loc_18002F720
0x18002f6d3  test    byte ptr [rax+1Ch], 1
0x18002f6d7  jz      short loc_18002F720
0x18002f6d9  call    cs:__imp__Xtime_get_ticks
0x18002f6df  sub     rax, [rbx+30h]
0x18002f6e3  mov     [rsp+108h+arg_18], rax
0x18002f6eb  lea     rdx, [rsp+108h+arg_18]
0x18002f6f3  lea     rcx, [rsp+108h+arg_8]
0x18002f6fb  call    ??$duration_cast@V?$duration@HU?$ratio@$0DM@$00@std@@@chrono@std@@_JU?$ratio@$00$0JIJGIA@@3@$0A@@chrono@std@@YA?AV?$duration@HU?$ratio@$0DM@$00@std@@@01@AEBV?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@01@@Z; std::chrono::duration_cast<std::chrono::duration<int,std::ratio<60,1>>,__int64,std::ratio<1,10000000>,0>(std::chrono::duration<__int64,std::ratio<1,10000000>> const &)
0x18002f700  mov     edx, 13h
0x18002f705  mov     r9d, [rax]
0x18002f708  lea     r8, WPP_9b988db5ce2f34186259e8bb867b7549_Traceguids
0x18002f70f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f716  mov     rcx, [rcx+10h]
0x18002f71a  call    WPP_SF_d
0x18002f71f  nop
0x18002f720  mov     rcx, [rsp+108h+var_E0]; this
0x18002f725  test    rcx, rcx
0x18002f728  jz      short loc_18002F730
0x18002f72a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002f72f  nop
0x18002f730  lea     rcx, [rsp+108h+arg_10]
0x18002f738  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002f73d  xor     eax, eax
0x18002f73f  jmp     loc_18002F8EB
0x18002f744  mov     sil, 1
0x18002f747  cmp     byte ptr [rbx+48h], 0
0x18002f74b  jz      loc_18002F7E3
0x18002f751  lea     r8, [rbx+40h]
0x18002f755  lea     rdx, ?PriorityToastCooldown@ToastHelper@@2V?$duration@HU?$ratio@$0OBA@$00@std@@@chrono@std@@B; std::chrono::duration<int,std::ratio<3600,1>> const ToastHelper::PriorityToastCooldown
0x18002f75c  lea     rcx, [rsp+108h+arg_8]
0x18002f764  call    ??$?HHU?$ratio@$0OBA@$00@std@@Usystem_clock@chrono@1@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@31@@chrono@std@@YA?AV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@01@AEBV?$duration@HU?$ratio@$0OBA@$00@std@@@01@AEBV201@@Z; std::chrono::operator+<int,std::ratio<3600,1>,std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>(std::chrono::duration<int,std::ratio<3600,1>> const &,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x18002f769  call    cs:__imp__Xtime_get_ticks
0x18002f76f  cmp     [rsp+108h+arg_8], rax
0x18002f777  jl      short loc_18002F7E3
0x18002f779  xor     sil, sil
0x18002f77c  lea     r14, WPP_GLOBAL_Control
0x18002f783  mov     rax, cs:WPP_GLOBAL_Control
0x18002f78a  cmp     rax, r14
0x18002f78d  jz      short loc_18002F7EA
0x18002f78f  cmp     byte ptr [rax+19h], 4
0x18002f793  jb      short loc_18002F7EA
0x18002f795  test    byte ptr [rax+1Ch], 1
0x18002f799  jz      short loc_18002F7EA
0x18002f79b  call    cs:__imp__Xtime_get_ticks
0x18002f7a1  sub     rax, [rbx+40h]
0x18002f7a5  mov     [rsp+108h+arg_18], rax
0x18002f7ad  lea     rdx, [rsp+108h+arg_18]
0x18002f7b5  lea     rcx, [rsp+108h+arg_8]
0x18002f7bd  call    ??$duration_cast@V?$duration@HU?$ratio@$0DM@$00@std@@@chrono@std@@_JU?$ratio@$00$0JIJGIA@@3@$0A@@chrono@std@@YA?AV?$duration@HU?$ratio@$0DM@$00@std@@@01@AEBV?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@01@@Z; std::chrono::duration_cast<std::chrono::duration<int,std::ratio<60,1>>,__int64,std::ratio<1,10000000>,0>(std::chrono::duration<__int64,std::ratio<1,10000000>> const &)
0x18002f7c2  mov     edx, 14h
0x18002f7c7  mov     r9d, [rax]
0x18002f7ca  lea     r8, WPP_9b988db5ce2f34186259e8bb867b7549_Traceguids
0x18002f7d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f7d8  mov     rcx, [rcx+10h]
0x18002f7dc  call    WPP_SF_d
0x18002f7e1  jmp     short loc_18002F7EA
0x18002f7e3  lea     r14, WPP_GLOBAL_Control
0x18002f7ea  mov     rdx, rbx; struct ToastNotifierForUser *
0x18002f7ed  mov     rcx, r15; this
0x18002f7f0  call    ?_ClearAllExistingToastsForUser@ToastHelper@@AEAAJPEAUToastNotifierForUser@@@Z; ToastHelper::_ClearAllExistingToastsForUser(ToastNotifierForUser *)
0x18002f7f5  mov     rcx, [rsp+108h]; this
0x18002f7fd  test    eax, eax
0x18002f7ff  jns     short loc_18002F815
0x18002f801  mov     r9d, eax; char *
0x18002f804  lea     r8, aOnecoreuapNetD_1; "onecoreuap\\net\\dot3\\ac\\server\\toas"...
0x18002f80b  mov     edx, 0DCh; void *
0x18002f810  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002f815  mov     r9, rdi
0x18002f818  mov     r8b, sil
0x18002f81b  lea     rdx, [rsp+108h+var_88]
0x18002f823  mov     rcx, r15
0x18002f826  call    ?_CreateToast@ToastHelper@@AEAA?AUToast@@_N_K@Z; ToastHelper::_CreateToast(bool,unsigned __int64)
0x18002f82b  nop
0x18002f82c  lea     rdx, [rsp+108h+var_88]
0x18002f834  mov     rcx, r12
0x18002f837  call    ?Show@?$consume_Windows_UI_Notifications_IToastNotifier@UIToastNotifier@Notifications@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUToastNotification@Notifications@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Notifications_IToastNotifier<winrt::Windows::UI::Notifications::IToastNotifier>::Show(winrt::Windows::UI::Notifications::ToastNotification const &)
0x18002f83c  lea     rcx, [rbx+10h]
0x18002f840  lea     rdx, [rsp+108h+var_88]
0x18002f848  call    ??$emplace_back@UToast@@@?$vector@UToast@@V?$allocator@UToast@@@std@@@std@@QEAAAEAUToast@@$$QEAU2@@Z; std::vector<Toast>::emplace_back<Toast>(Toast &&)
0x18002f84d  call    cs:__imp__Xtime_get_ticks
0x18002f853  cmp     byte ptr [rbx+38h], 0
0x18002f857  jnz     short loc_18002F85D
0x18002f859  mov     byte ptr [rbx+38h], 1
0x18002f85d  mov     [rbx+30h], rax
0x18002f861  test    sil, sil
0x18002f864  jz      short loc_18002F87A
0x18002f866  call    cs:__imp__Xtime_get_ticks
0x18002f86c  mov     [rbx+40h], rax
0x18002f870  cmp     byte ptr [rbx+48h], 0
0x18002f874  jnz     short loc_18002F87A
0x18002f876  mov     byte ptr [rbx+48h], 1
0x18002f87a  xor     r8d, r8d; int
0x18002f87d  xor     edx, edx; unsigned int
0x18002f87f  mov     rcx, r15; this
0x18002f882  call    ?_LogSendingToast@ToastHelper@@AEAAXKJ@Z; ToastHelper::_LogSendingToast(ulong,long)
0x18002f887  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f88e  cmp     rcx, r14
0x18002f891  jz      short loc_18002F8B5
0x18002f893  cmp     byte ptr [rcx+19h], 4
0x18002f897  jb      short loc_18002F8B5
0x18002f899  test    byte ptr [rcx+1Ch], 1
0x18002f89d  jz      short loc_18002F8B5
0x18002f89f  mov     edx, 15h
0x18002f8a4  lea     r8, WPP_9b988db5ce2f34186259e8bb867b7549_Traceguids
0x18002f8ab  mov     rcx, [rcx+10h]
0x18002f8af  call    WPP_SF_
0x18002f8b4  nop
0x18002f8b5  lea     rcx, [rsp+108h+var_88]; this
0x18002f8bd  call    ??1Toast@@QEAA@XZ; Toast::~Toast(void)
0x18002f8c2  nop
0x18002f8c3  mov     rcx, [rsp+108h+var_E0]; this
0x18002f8c8  test    rcx, rcx
0x18002f8cb  jz      short loc_18002F8D3
0x18002f8cd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002f8d2  nop
0x18002f8d3  lea     rcx, [rsp+108h+arg_10]
0x18002f8db  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002f8e0  xor     eax, eax
0x18002f8e2  jmp     short loc_18002F8EB
0x18002f8e4  mov     eax, dword ptr [rsp+108h+arg_8]
0x18002f8eb  add     rsp, 0D0h
0x18002f8f2  pop     r15
  ... truncated ...
```
