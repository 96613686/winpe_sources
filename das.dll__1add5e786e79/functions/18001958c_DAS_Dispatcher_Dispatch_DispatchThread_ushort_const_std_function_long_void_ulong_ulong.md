# DAS::Dispatcher::Dispatch::DispatchThread(ushort const *,std::function<long (void)>,ulong,ulong)

- ea: `0x18001958c`
- end: `0x180019ac4`
- name: `?DispatchThread@Dispatch@Dispatcher@DAS@@CAJPEBGV?$function@$$A6AJXZ@std@@KK@Z`
- size: `1336`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `18`
- callee_count: `26`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002be5c`
- `0x180033ad0`
- `0x18003602c`
- `0x1800480d0`
- `0x180048244`
- `0x1800482a4`
- `0x180048304`
- `0x180048364`
- `0x1800483c4`
- `0x180048424`
- `0x180048484`
- `0x1800484e4`
- `0x18004863c`
- `0x18004869c`
- `0x180048924`
- `0x1800489e4`
- `0x180048b60`
- `0x180048cec`

## callees

- `0x18001958c`
- `0x18001a268`
- `0x18001a350`
- `0x18001a3c0`
- `0x18001a55c`
- `0x18001a5e4`
- `0x18001a760`
- `0x18002148c`
- `0x180028810`
- `0x18002a948`
- `0x18002aa34`
- `0x1800339c0`
- `0x180033a98`
- `0x1800360f8`
- `0x18003bc80`
- `0x18003c9f8`
- `0x180045df0`
- `0x180047a9c`
- `0x180047b04`
- `0x180047e74`
- `0x180049450`
- `0x1800497c0`
- `0x1800499e0`
- `0x180049a58`
- `0x18004c204`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800197b2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800197b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180019706`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180019706`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800197a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800197bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800197d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800197a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800197bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800197d5`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180019799`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180019799`
- `faultrep!ReportCoreHang` at `0x180019a11`
- `faultrep!ReportCoreHang` at `0x180019a11`

## string_xrefs

- `0x1800196fd`: `das.dll`
- `0x1800195e8`: `onecore\base\devices\association\service\lib\dispatcher.cpp`
- `0x180019718`: `onecore\base\devices\association\service\lib\dispatcher.cpp`
- `0x1800197fa`: `onecore\base\devices\association\service\lib\dispatcher.cpp`
- `0x180019869`: `onecore\base\devices\association\service\lib\dispatcher.cpp`
- `0x1800199da`: `onecore\base\devices\association\service\lib\dispatcher.cpp`
- `0x180019a40`: `onecore\base\devices\association\service\lib\dispatcher.cpp`
- `0x1800197eb`: `failed to dispatch thread (error = 0x%08x), and failed to FreeLibary (error = 0x%08x)`
- `0x18001985a`: `failed to dispatch thread (error = 0x%08x)`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall DAS::Dispatcher::Dispatch::DispatchThread(__int64 a1, __int64 a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  __int64 v8; // r8
  DAS::Dispatcher::DispatchedArgs *v9; // rbx
  __int64 v10; // r14
  __int64 v11; // rcx
  HMODULE *v12; // rbx
  HMODULE *v13; // r15
  int v14; // edx
  int v15; // r8d
  const char *v16; // r9
  signed int LastError; // ebx
  signed int v18; // esi
  signed int v19; // eax
  int v20; // edx
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  unsigned int v24; // ebx
  int HostPids; // eax
  int v26; // eax
  unsigned int v27; // r8d
  int MessageGuid; // [rsp+20h] [rbp-108h]
  char *v29; // [rsp+28h] [rbp-100h]
  DWORD v30; // [rsp+30h] [rbp-F8h]
  unsigned int v31; // [rsp+50h] [rbp-D8h] BYREF
  char v32; // [rsp+54h] [rbp-D4h] BYREF
  DAS::Dispatcher::DispatchedArgs *v33; // [rsp+58h] [rbp-D0h] BYREF
  unsigned int *v34; // [rsp+60h] [rbp-C8h] BYREF
  std::_Ref_count_base *v35; // [rsp+68h] [rbp-C0h]
  _QWORD v36[4]; // [rsp+70h] [rbp-B8h] BYREF
  _BYTE v37[56]; // [rsp+90h] [rbp-98h] BYREF
  __int64 v38; // [rsp+C8h] [rbp-60h]
  __int64 v39; // [rsp+D0h] [rbp-58h]
  __int128 v40; // [rsp+D8h] [rbp-50h] BYREF
  __int64 v41; // [rsp+E8h] [rbp-40h]
  __int64 v42; // [rsp+F0h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  try
  {
    v39 = a2;
    if ( DAS::Dispatcher::g_dispatchingDisabled )
    {
      v4 = std::_Func_class<long,>::operator()(a2);
      v5 = v4;
      if ( v4 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x11C,
          (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\dispatcher.cpp",
          (const char *)(unsigned int)v4,
          MessageGuid);
      std::_Func_class<long,>::_Tidy(a2);
      return v5;
    }
    std::make_shared<DAS::Dispatcher::SharedArgs,>(&v34);
    v34[4] = 300000;
    v40 = 0;
    v41 = 0;
    v42 = 0;
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(a1 + 2 * v8) );
    std::wstring::_Construct<1,unsigned short const *>(&v40, a1);
    v9 = (DAS::Dispatcher::DispatchedArgs *)operator new(0x78u);
    v33 = v9;
    v10 = std::wstring::wstring(v36, &v40);
    v38 = 0;
    v11 = *(_QWORD *)(a2 + 56);
    if ( v11 )
    {
      if ( v11 == a2 )
      {
        v38 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v11 + 8LL))(v11, v37);
        std::_Func_class<long,>::_Tidy(a2);
      }
      else
      {
        v38 = *(_QWORD *)(a2 + 56);
        *(_QWORD *)(a2 + 56) = 0;
      }
    }
    v12 = (HMODULE *)DAS::Dispatcher::DispatchedArgs::DispatchedArgs(v9, &v34, v37, v10);
    v33 = (DAS::Dispatcher::DispatchedArgs *)v12;
    std::wstring::_Tidy_deallocate((__int64)&v40);
    v13 = v12 + 14;
    if ( !GetModuleHandleExW(0, L"das.dll", v12 + 14) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x122,
                    (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\dispatcher.cpp",
                    v16);
      std::unique_ptr<DAS::Dispatcher::DispatchedArgs>::~unique_ptr<DAS::Dispatcher::DispatchedArgs>(&v33);
      if ( v35 )
        std::_Ref_count_base::_Decref(v35);
LABEL_34:
      std::_Func_class<long,>::_Tidy(a2);
      return (unsigned int)LastError;
    }
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v14,
        v15,
        14,
        &WPP_58cdcff8f7813eb890224e87d5cdb596_Traceguids,
        a1);
    if ( !TrySubmitThreadpoolCallback(DAS::Dispatcher::Dispatch::DispatchWorkCallback, v12, 0) )
    {
      v18 = GetLastError();
      if ( FreeLibrary(*v13) )
      {
        *v13 = 0;
        if ( v18 > 0 )
          LastError = (unsigned __int16)v18 | 0x80070000;
        else
          LastError = v18;
        if ( LastError < 0 )
        {
          LODWORD(v29) = v18;
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x133,
            (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\dispatcher.cpp",
            (const char *)(unsigned int)LastError,
            (int)"failed to dispatch thread (error = 0x%08x)",
            v29);
        }
        std::unique_ptr<DAS::Dispatcher::DispatchedArgs>::~unique_ptr<DAS::Dispatcher::DispatchedArgs>(&v33);
        if ( v35 )
          std::_Ref_count_base::_Decref(v35);
      }
      else
      {
        v19 = GetLastError();
        LastError = v19;
        if ( v19 > 0 )
          LastError = (unsigned __int16)v19 | 0x80070000;
        if ( LastError < 0 )
        {
          v30 = GetLastError();
          LODWORD(v29) = v18;
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x12C,
            (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\dispatcher.cpp",
            (const char *)(unsigned int)LastError,
            (int)"failed to dispatch thread (error = 0x%08x), and failed to FreeLibary (error = 0x%08x)",
            v29,
            v30);
        }
        std::unique_ptr<DAS::Dispatcher::DispatchedArgs>::~unique_ptr<DAS::Dispatcher::DispatchedArgs>(&v33);
        if ( v35 )
          std::_Ref_count_base::_Decref(v35);
      }
      goto LABEL_34;
    }
    v33 = 0;
    if ( (unsigned __int8)wil::slim_event_t<0>::wait(v34 + 5, v34[4]) )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v20,
          v22,
          15,
          &WPP_58cdcff8f7813eb890224e87d5cdb596_Traceguids,
          a1);
      v24 = *v34;
      if ( v35 )
        std::_Ref_count_base::_Decref(v35);
      std::_Func_class<long,>::_Tidy(a2);
      result = v24;
    }
    else
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_Sddd(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v34[4] / 0x3E8,
          v22,
          v23,
          MessageGuid,
          a1,
          v34[1],
          v34[3],
          v34[4] / 0x3E8);
      if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 4) != 0 )
        McTemplateU0qqq_EventWriteTransfer(v21, (unsigned int)DISPATCHER_TIMEOUT, v34[1], v34[3], v34[4] / 0x3E8);
      DAS::Dispatcher::Watchdog::CheckForStuckThreads(g_watchdog);
      v31 = v34[1];
      v36[0] = &v31;
      v36[1] = &v32;
      std::vector<unsigned long>::vector<unsigned long>(&v40, v36);
      HostPids = CHostContext::GetHostPids(&v40);
      if ( HostPids < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x142,
          (int)"onecore\\base\\devices\\association\\service\\lib\\dispatcher.cpp",
          (const char *)(unsigned int)HostPids);
      v26 = ReportCoreHang(v40, (__int64)(*((_QWORD *)&v40 + 1) - v40) >> 2, v34[3], 40);
      if ( v26 < 0 )
        wil::details::in1diag3::_Log_NtStatus(retaddr, (void *)0x143, v27, (const char *)(unsigned int)v26, MessageGuid);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x144,
        (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\dispatcher.cpp",
        (const char *)0x800705B4LL,
        MessageGuid);
      std::vector<unsigned long>::_Tidy(&v40);
      std::unique_ptr<DAS::Dispatcher::DispatchedArgs>::~unique_ptr<DAS::Dispatcher::DispatchedArgs>(&v33);
      if ( v35 )
        std::_Ref_count_base::_Decref(v35);
      std::_Func_class<long,>::_Tidy(a2);
      result = 2147943860LL;
    }
  }
  catch ( ... )
  {
    v31 = wil::details::in1diag3::Return_CaughtException(
            retaddr,
            (void *)0x149,
            (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\dispatcher.cpp",
            v6);
    std::_Func_class<long,>::_Tidy(v39);
    return v31;
  }
  return result;
}

```

## disassembly

```asm
0x18001958c  mov     r11, rsp
0x18001958f  mov     [r11+18h], rbx
0x180019593  mov     [r11+20h], rsi
0x180019597  push    rdi
0x180019598  push    r12
0x18001959a  push    r13
0x18001959c  push    r14
0x18001959e  push    r15
0x1800195a0  sub     rsp, 100h
0x1800195a7  mov     rax, cs:__security_cookie
0x1800195ae  xor     rax, rsp
0x1800195b1  mov     [rsp+128h+var_30], rax
0x1800195b9  mov     rdi, rdx
0x1800195bc  mov     rsi, rcx
0x1800195bf  mov     [r11-58h], rdx
0x1800195c3  xor     r12d, r12d
0x1800195c6  cmp     cs:?g_dispatchingDisabled@Dispatcher@DAS@@3_NA, r12b; bool DAS::Dispatcher::g_dispatchingDisabled
0x1800195cd  jz      short loc_180019609
0x1800195cf  mov     rcx, rdx
0x1800195d2  call    ??R?$_Func_class@J$$V@std@@QEBAJXZ; std::_Func_class<long,>::operator()(void)
0x1800195d7  mov     ebx, eax
0x1800195d9  test    eax, eax
0x1800195db  jns     short loc_1800195FA
0x1800195dd  mov     rcx, [rsp+128h]; this
0x1800195e5  mov     r9d, eax; char *
0x1800195e8  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\association\\se"...
0x1800195ef  mov     edx, 11Ch; void *
0x1800195f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800195f9  nop
0x1800195fa  mov     rcx, rdi
0x1800195fd  call    ?_Tidy@?$_Func_class@J$$V@std@@IEAAXXZ; std::_Func_class<long,>::_Tidy(void)
0x180019602  mov     eax, ebx
0x180019604  jmp     loc_180019A97
0x180019609  lea     rcx, [rsp+128h+var_C8]
0x18001960e  call    ??$make_shared@USharedArgs@Dispatcher@DAS@@$$V@std@@YA?AV?$shared_ptr@USharedArgs@Dispatcher@DAS@@@0@XZ; std::make_shared<DAS::Dispatcher::SharedArgs,>(void)
0x180019613  nop
0x180019614  mov     rax, [rsp+128h+var_C8]
0x180019619  mov     dword ptr [rax+10h], 493E0h
0x180019620  xorps   xmm0, xmm0
0x180019623  movups  [rsp+128h+var_50], xmm0
0x18001962b  mov     [rsp+128h+var_40], r12
0x180019633  mov     [rsp+128h+var_38], r12
0x18001963b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001963f  inc     r8
0x180019642  cmp     [rsi+r8*2], r12w
0x180019647  jnz     short loc_18001963F
0x180019649  mov     rdx, rsi
0x18001964c  lea     rcx, [rsp+128h+var_50]
0x180019654  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180019659  nop
0x18001965a  mov     ecx, 78h ; 'x'; Size
0x18001965f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019664  mov     rbx, rax
0x180019667  mov     [rsp+128h+var_D0], rax
0x18001966c  lea     rdx, [rsp+128h+var_50]
0x180019674  lea     rcx, [rsp+128h+var_B8]
0x180019679  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18001967e  mov     r14, rax
0x180019681  mov     [rsp+128h+var_60], r12
0x180019689  mov     rcx, [rdi+38h]
0x18001968d  test    rcx, rcx
0x180019690  jz      short loc_1800196C9
0x180019692  cmp     rcx, rdi
0x180019695  jnz     short loc_1800196BD
0x180019697  mov     rdx, [rcx]
0x18001969a  mov     rax, [rdx+8]
0x18001969e  lea     rdx, [rsp+128h+var_98]
0x1800196a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196ab  mov     [rsp+128h+var_60], rax
0x1800196b3  mov     rcx, rdi
0x1800196b6  call    ?_Tidy@?$_Func_class@J$$V@std@@IEAAXXZ; std::_Func_class<long,>::_Tidy(void)
0x1800196bb  jmp     short loc_1800196C9
0x1800196bd  mov     [rsp+128h+var_60], rcx
0x1800196c5  mov     [rdi+38h], r12
0x1800196c9  mov     r9, r14
0x1800196cc  lea     r8, [rsp+128h+var_98]
0x1800196d4  lea     rdx, [rsp+128h+var_C8]
0x1800196d9  mov     rcx, rbx
0x1800196dc  call    ??0DispatchedArgs@Dispatcher@DAS@@QEAA@AEAV?$shared_ptr@USharedArgs@Dispatcher@DAS@@@std@@V?$function@$$A6AJXZ@4@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; DAS::Dispatcher::DispatchedArgs::DispatchedArgs(std::shared_ptr<DAS::Dispatcher::SharedArgs> &,std::function<long (void)>,std::wstring)
0x1800196e1  mov     rbx, rax
0x1800196e4  mov     [rsp+128h+var_D0], rax
0x1800196e9  lea     rcx, [rsp+128h+var_50]
0x1800196f1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800196f6  lea     r15, [rbx+70h]
0x1800196fa  mov     r8, r15; phModule
0x1800196fd  lea     rdx, ModuleName; "das.dll"
0x180019704  xor     ecx, ecx; dwFlags
0x180019706  call    cs:__imp_GetModuleHandleExW
0x18001970c  test    eax, eax
0x18001970e  jnz     short loc_180019755
0x180019710  mov     rcx, [rsp+128h]; this
0x180019718  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\association\\se"...
0x18001971f  mov     edx, 122h; void *
0x180019724  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180019729  mov     ebx, eax
0x18001972b  lea     rcx, [rsp+128h+var_D0]
0x180019730  call    ??1?$unique_ptr@UDispatchedArgs@Dispatcher@DAS@@U?$default_delete@UDispatchedArgs@Dispatcher@DAS@@@std@@@std@@QEAA@XZ; std::unique_ptr<DAS::Dispatcher::DispatchedArgs>::~unique_ptr<DAS::Dispatcher::DispatchedArgs>(void)
0x180019735  nop
0x180019736  mov     rcx, [rsp+128h+var_C0]; this
0x18001973b  test    rcx, rcx
0x18001973e  jz      short loc_180019746
0x180019740  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180019745  nop
0x180019746  mov     rcx, rdi
0x180019749  call    ?_Tidy@?$_Func_class@J$$V@std@@IEAAXXZ; std::_Func_class<long,>::_Tidy(void)
0x18001974e  mov     eax, ebx
0x180019750  jmp     loc_180019A97
0x180019755  lea     r13, WPP_RECORDER_INITIALIZED
0x18001975c  lea     r14, WPP_58cdcff8f7813eb890224e87d5cdb596_Traceguids
0x180019763  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18001976a  jz      short loc_18001978C
0x18001976c  mov     r9d, 0Eh; int
0x180019772  mov     [rsp+128h+var_100], rsi; __int64
0x180019777  mov     [rsp+128h+MessageGuid], r14; MessageGuid
0x18001977c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019783  mov     rcx, [rcx+28h]; int
0x180019787  call    WPP_RECORDER_SF_S
0x18001978c  xor     r8d, r8d; pcbe
0x18001978f  mov     rdx, rbx; pv
0x180019792  lea     rcx, ?DispatchWorkCallback@Dispatch@Dispatcher@DAS@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x180019799  call    cs:__imp_TrySubmitThreadpoolCallback
0x18001979f  test    eax, eax
0x1800197a1  jnz     loc_1800198A5
0x1800197a7  call    cs:__imp_GetLastError
0x1800197ad  mov     esi, eax
0x1800197af  mov     rcx, [r15]; hLibModule
0x1800197b2  call    cs:__imp_FreeLibrary
0x1800197b8  test    eax, eax
0x1800197ba  jnz     short loc_180019836
0x1800197bc  call    cs:__imp_GetLastError
0x1800197c2  mov     ebx, eax
0x1800197c4  test    eax, eax
0x1800197c6  jle     short loc_1800197D1
0x1800197c8  movzx   ebx, ax
0x1800197cb  or      ebx, 80070000h
0x1800197d1  test    ebx, ebx
0x1800197d3  jns     short loc_18001980C
0x1800197d5  call    cs:__imp_GetLastError
0x1800197db  mov     rcx, [rsp+128h]; this
0x1800197e3  mov     [rsp+128h+var_F8], eax
0x1800197e7  mov     dword ptr [rsp+128h+var_100], esi; char *
0x1800197eb  lea     rax, aFailedToDispat; "failed to dispatch thread (error = 0x%0"...
0x1800197f2  mov     [rsp+128h+MessageGuid], rax; int
0x1800197f7  mov     r9d, ebx; char *
0x1800197fa  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\association\\se"...
0x180019801  mov     edx, 12Ch; void *
0x180019806  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001980b  nop
0x18001980c  lea     rcx, [rsp+128h+var_D0]
0x180019811  call    ??1?$unique_ptr@UDispatchedArgs@Dispatcher@DAS@@U?$default_delete@UDispatchedArgs@Dispatcher@DAS@@@std@@@std@@QEAA@XZ; std::unique_ptr<DAS::Dispatcher::DispatchedArgs>::~unique_ptr<DAS::Dispatcher::DispatchedArgs>(void)
0x180019816  nop
0x180019817  mov     rcx, [rsp+128h+var_C0]; this
0x18001981c  test    rcx, rcx
0x18001981f  jz      short loc_180019827
0x180019821  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180019826  nop
0x180019827  mov     rcx, rdi
0x18001982a  call    ?_Tidy@?$_Func_class@J$$V@std@@IEAAXXZ; std::_Func_class<long,>::_Tidy(void)
0x18001982f  mov     eax, ebx
0x180019831  jmp     loc_180019A97
0x180019836  mov     [r15], r12
0x180019839  test    esi, esi
0x18001983b  jg      short loc_180019841
0x18001983d  mov     ebx, esi
0x18001983f  jmp     short loc_18001984A
0x180019841  movzx   ebx, si
0x180019844  or      ebx, 80070000h
0x18001984a  test    ebx, ebx
0x18001984c  jns     short loc_18001987B
0x18001984e  mov     rcx, [rsp+128h]; this
0x180019856  mov     dword ptr [rsp+128h+var_100], esi; char *
0x18001985a  lea     rax, aFailedToDispat_0; "failed to dispatch thread (error = 0x%0"...
0x180019861  mov     [rsp+128h+MessageGuid], rax; int
0x180019866  mov     r9d, ebx; char *
0x180019869  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\association\\se"...
0x180019870  mov     edx, 133h; void *
0x180019875  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001987a  nop
0x18001987b  lea     rcx, [rsp+128h+var_D0]
0x180019880  call    ??1?$unique_ptr@UDispatchedArgs@Dispatcher@DAS@@U?$default_delete@UDispatchedArgs@Dispatcher@DAS@@@std@@@std@@QEAA@XZ; std::unique_ptr<DAS::Dispatcher::DispatchedArgs>::~unique_ptr<DAS::Dispatcher::DispatchedArgs>(void)
0x180019885  nop
0x180019886  mov     rcx, [rsp+128h+var_C0]; this
0x18001988b  test    rcx, rcx
0x18001988e  jz      short loc_180019896
0x180019890  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180019895  nop
0x180019896  mov     rcx, rdi
0x180019899  call    ?_Tidy@?$_Func_class@J$$V@std@@IEAAXXZ; std::_Func_class<long,>::_Tidy(void)
0x18001989e  mov     eax, ebx
0x1800198a0  jmp     loc_180019A97
0x1800198a5  mov     [rsp+128h+var_D0], r12
0x1800198aa  mov     rdx, [rsp+128h+var_C8]
0x1800198af  lea     rcx, [rdx+14h]
0x1800198b3  mov     edx, [rdx+10h]
0x1800198b6  call    ?wait@?$slim_event_t@$0A@@wil@@QEAA_NK@Z; wil::slim_event_t<0>::wait(ulong)
0x1800198bb  test    al, al
0x1800198bd  jz      short loc_18001990E
0x1800198bf  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1800198c6  jz      short loc_1800198E8
0x1800198c8  mov     r9d, 0Fh; int
0x1800198ce  mov     [rsp+128h+var_100], rsi; __int64
0x1800198d3  mov     [rsp+128h+MessageGuid], r14; MessageGuid
0x1800198d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800198df  mov     rcx, [rcx+28h]; int
0x1800198e3  call    WPP_RECORDER_SF_S
0x1800198e8  mov     rax, [rsp+128h+var_C8]
0x1800198ed  mov     ebx, [rax]
0x1800198ef  mov     rcx, [rsp+128h+var_C0]; this
0x1800198f4  test    rcx, rcx
0x1800198f7  jz      short loc_1800198FF
0x1800198f9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800198fe  nop
0x1800198ff  mov     rcx, rdi
0x180019902  call    ?_Tidy@?$_Func_class@J$$V@std@@IEAAXXZ; std::_Func_class<long,>::_Tidy(void)
0x180019907  mov     eax, ebx
0x180019909  jmp     loc_180019A97
0x18001990e  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180019915  jz      short loc_18001994E
0x180019917  mov     eax, 10624DD3h
0x18001991c  mov     rcx, [rsp+128h+var_C8]
0x180019921  mul     dword ptr [rcx+10h]
0x180019924  shr     edx, 6
0x180019927  mov     [rsp+128h+var_E8], edx
0x18001992b  mov     eax, [rcx+0Ch]
0x18001992e  mov     [rsp+128h+var_F0], eax
0x180019932  mov     eax, [rcx+4]
0x180019935  mov     [rsp+128h+var_F8], eax
0x180019939  mov     [rsp+128h+var_100], rsi
0x18001993e  mov     rcx, cs:WPP_GLOBAL_Control
0x180019945  mov     rcx, [rcx+28h]
0x180019949  call    WPP_RECORDER_SF_Sddd
0x18001994e  test    byte ptr cs:Microsoft_Windows_DeviceAssociationServiceEnableBits, 4
0x180019955  jz      short loc_180019980
0x180019957  mov     eax, 10624DD3h
0x18001995c  mov     r8, [rsp+128h+var_C8]
0x180019961  mul     dword ptr [r8+10h]
0x180019965  shr     edx, 6
0x180019968  mov     dword ptr [rsp+128h+MessageGuid], edx; int
0x18001996c  mov     r9d, [r8+0Ch]
0x180019970  mov     r8d, [r8+4]
0x180019974  lea     rdx, DISPATCHER_TIMEOUT
0x18001997b  call    McTemplateU0qqq_EventWriteTransfer
0x180019980  mov     rcx, cs:?g_watchdog@@3V?$unique_ptr@VWatchdog@Dispatcher@DAS@@U?$default_delete@VWatchdog@Dispatcher@DAS@@@std@@@std@@A; this
0x180019987  call    ?CheckForStuckThreads@Watchdog@Dispatcher@DAS@@QEAAXK@Z; DAS::Dispatcher::Watchdog::CheckForStuckThreads(ulong)
0x18001998c  mov     rax, [rsp+128h+var_C8]
0x180019991  mov     ecx, [rax+4]
0x180019994  mov     [rsp+128h+var_D8], ecx
0x180019998  lea     rax, [rsp+128h+var_D8]
0x18001999d  mov     [rsp+128h+var_B8], rax
0x1800199a2  lea     rax, [rsp+128h+var_D4]
0x1800199a7  mov     [rsp+128h+var_B0], rax
0x1800199ac  lea     rdx, [rsp+128h+var_B8]
0x1800199b1  lea     rcx, [rsp+128h+var_50]
0x1800199b9  call    ??0?$vector@KV?$allocator@K@std@@@std@@QEAA@V?$initializer_list@K@1@AEBV?$allocator@K@1@@Z; std::vector<ulong>::vector<ulong>(std::initializer_list<ulong>,std::allocator<ulong> const &)
0x1800199be  lea     rcx, [rsp+128h+var_50]
0x1800199c6  call    ?GetHostPids@CHostContext@@SAJAEAV?$vector@KV?$allocator@K@std@@@std@@@Z; CHostContext::GetHostPids(std::vector<ulong> &)
0x1800199cb  mov     rcx, [rsp+128h]; this
0x1800199d3  test    eax, eax
0x1800199d5  jns     short loc_1800199EB
0x1800199d7  mov     r9d, eax; char *
0x1800199da  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\association\\se"...
0x1800199e1  mov     edx, 142h; void *
0x1800199e6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800199eb  mov     rcx, qword ptr [rsp+128h+var_50]
0x1800199f3  mov     rdx, qword ptr [rsp+128h+var_50+8]
0x1800199fb  sub     rdx, rcx
0x1800199fe  sar     rdx, 2
0x180019a02  mov     r9d, 28h ; '('
0x180019a08  mov     r8, [rsp+128h+var_C8]
0x180019a0d  mov     r8d, [r8+0Ch]
0x180019a11  call    cs:__imp_ReportCoreHang
0x180019a17  mov     rcx, [rsp+128h]; this
0x180019a1f  test    eax, eax
0x180019a21  jns     short loc_180019A30
0x180019a23  mov     r9d, eax; char *
0x180019a26  mov     edx, 143h; void *
0x180019a2b  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x180019a30  mov     rcx, [rsp+128h]; this
0x180019a38  mov     ebx, 800705B4h
0x180019a3d  mov     r9d, ebx; char *
0x180019a40  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\association\\se"...
0x180019a47  mov     edx, 144h; void *
0x180019a4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019a51  lea     rcx, [rsp+128h+var_50]
0x180019a59  call    ?_Tidy@?$vector@KV?$allocator@K@std@@@std@@AEAAXXZ; std::vector<ulong>::_Tidy(void)
0x180019a5e  nop
0x180019a5f  lea     rcx, [rsp+128h+var_D0]
0x180019a64  call    ??1?$unique_ptr@UDispatchedArgs@Dispatcher@DAS@@U?$default_delete@UDispatchedArgs@Dispatcher@DAS@@@std@@@std@@QEAA@XZ; std::unique_ptr<DAS::Dispatcher::DispatchedArgs>::~unique_ptr<DAS::Dispatcher::DispatchedArgs>(void)
0x180019a69  nop
0x180019a6a  mov     rcx, [rsp+128h+var_C0]; this
0x180019a6f  test    rcx, rcx
0x180019a72  jz      short loc_180019A7A
0x180019a74  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180019a79  nop
0x180019a7a  mov     rcx, rdi
0x180019a7d  call    ?_Tidy@?$_Func_class@J$$V@std@@IEAAXXZ; std::_Func_class<long,>::_Tidy(void)
0x180019a82  mov     eax, ebx
0x180019a84  jmp     short loc_180019A97
0x180019a86  mov     rcx, [rsp+128h+var_58]
0x180019a8e  call    ?_Tidy@?$_Func_class@J$$V@std@@IEAAXXZ; std::_Func_class<long,>::_Tidy(void)
  ... truncated ...
```
