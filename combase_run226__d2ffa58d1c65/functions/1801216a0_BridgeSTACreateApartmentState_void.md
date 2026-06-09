# BridgeSTACreateApartmentState(void * *)

- ea: `0x1801216a0`
- end: `0x180121a09`
- name: `?BridgeSTACreateApartmentState@@YAJPEAPEAX@Z`
- size: `873`
- prototype: `HRESULT __fastcall(void **state)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180037370`
- `0x18003a8bc`
- `0x18003cf8c`
- `0x18005ce9c`
- `0x1801216a0`
- `0x180122110`
- `0x1801221ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180121766`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180121933`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012199d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801219c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801219e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180121766`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180121933`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012199d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801219c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801219e5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180121783`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180121950`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801219ba`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801219de`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180121a02`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180121783`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180121950`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801219ba`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801219de`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180121a02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801218db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801218e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801218db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801218e6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180121853`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180121853`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180121700`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180121700`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimerEx` at `0x180121836`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimerEx` at `0x180121836`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801216d5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801216d5`

## string_xrefs

- `0x180121720`: `onecore\com\combase\dcomrem\apartmenttypespecific.cpp`
- `0x18012178e`: `onecore\com\combase\dcomrem\apartmenttypespecific.cpp`
- `0x1801217ab`: `onecore\com\combase\dcomrem\apartmenttypespecific.cpp`
- `0x1801218f5`: `onecore\com\combase\dcomrem\apartmenttypespecific.cpp`
- `0x18012195b`: `onecore\com\combase\dcomrem\apartmenttypespecific.cpp`

## pseudocode

```c
__int64 __fastcall BridgeSTACreateApartmentState(ModernSTAState **state)
{
  char *WaitableTimer; // rbx
  int LastError; // eax
  ModernSTAState *v5; // rax
  ModernSTAState *v6; // rdi
  char *m_ptr; // rcx
  unsigned int v8; // ebx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  Microsoft::WRL::Wrappers::Event wakeEvent; // [rsp+40h] [rbp-10h] BYREF
  void *retaddr; // [rsp+68h] [rbp+18h]
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > > freeUnusedDllsTimer; // [rsp+78h] [rbp+28h] BYREF
  _LARGE_INTEGER liDueTime; // [rsp+80h] [rbp+30h] BYREF

  if ( !TLSGetLogicalThread() )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x6Au,
      "onecore\\com\\combase\\dcomrem\\apartmenttypespecific.cpp",
      -2147024882);
    return 2147942414LL;
  }
  wakeEvent.handle_ = CreateEventW(0, 1, 0, 0);
  wakeEvent.__vftable = (Microsoft::WRL::Wrappers::Event_vtbl *)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  if ( !wakeEvent.handle_ )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x6Du,
      "onecore\\com\\combase\\dcomrem\\apartmenttypespecific.cpp",
      -2147024882);
    wakeEvent.__vftable = (Microsoft::WRL::Wrappers::Event_vtbl *)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    return 2147942414LL;
  }
  WaitableTimer = (char *)CreateWaitableTimerExW(0, 0, 0, 0x100002u);
  freeUnusedDllsTimer.m_ptr = WaitableTimer;
  if ( ((unsigned __int64)(WaitableTimer + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x70u,
      "onecore\\com\\combase\\dcomrem\\apartmenttypespecific.cpp",
      -2147024882);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (__cdecl*)(void *),&CloseHandle> > *)&freeUnusedDllsTimer);
    wakeEvent.__vftable = (Microsoft::WRL::Wrappers::Event_vtbl *)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    if ( wakeEvent.handle_
      && !Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose((Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> *)&wakeEvent) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      RaiseException(LastError, 1u, 0, 0);
      __debugbreak();
    }
    return 2147942414LL;
  }
  liDueTime.QuadPart = -600000000;
  if ( SetWaitableTimerEx(WaitableTimer, &liDueTime, 60000, 0, 0, 0, 0x7530u) )
  {
    v5 = (ModernSTAState *)HeapAlloc(g_hHeap, 0, 0xF0u);
    v6 = v5;
    if ( !v5 )
    {
      *state = 0;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        0x7Fu,
        "onecore\\com\\combase\\dcomrem\\apartmenttypespecific.cpp",
        -2147024882);
      if ( (unsigned __int64)(WaitableTimer - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(WaitableTimer);
      wakeEvent.__vftable = (Microsoft::WRL::Wrappers::Event_vtbl *)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
      if ( wakeEvent.handle_
        && !Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose((Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> *)&wakeEvent) )
      {
        v11 = GetLastError();
        if ( v11 > 0 )
          v11 = (unsigned __int16)v11 | 0x80070000;
        RaiseException(v11, 1u, 0, 0);
        JUMPOUT(0x180121A08LL);
      }
      return 2147942414LL;
    }
    ModernSTAState::ModernSTAState(v5, &wakeEvent, &freeUnusedDllsTimer);
    m_ptr = (char *)freeUnusedDllsTimer.m_ptr;
    LOBYTE(v6[1].__vftable) = 0;
    HIDWORD(v6[1].__vftable) = 0;
    v6->__vftable = (ModernSTAState_vtbl *)BridgeSTAState::`vftable';
    *state = v6;
    if ( (unsigned __int64)(m_ptr - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(m_ptr);
    wakeEvent.__vftable = (Microsoft::WRL::Wrappers::Event_vtbl *)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    if ( wakeEvent.handle_
      && !Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose((Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> *)&wakeEvent) )
    {
      v10 = GetLastError();
      if ( v10 > 0 )
        v10 = (unsigned __int16)v10 | 0x80070000;
      RaiseException(v10, 1u, 0, 0);
      __debugbreak();
    }
    return 0;
  }
  else
  {
    v8 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           0x7Bu,
           "onecore\\com\\combase\\dcomrem\\apartmenttypespecific.cpp");
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (__cdecl*)(void *),&CloseHandle> > *)&freeUnusedDllsTimer);
    wakeEvent.__vftable = (Microsoft::WRL::Wrappers::Event_vtbl *)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    if ( wakeEvent.handle_
      && !Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose((Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> *)&wakeEvent) )
    {
      v9 = GetLastError();
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      RaiseException(v9, 1u, 0, 0);
      __debugbreak();
    }
    return v8;
  }
}

```

## disassembly

```asm
0x1801216a0  mov     [rsp-18h+arg_0], rbx
0x1801216a5  mov     [rsp-18h+arg_18], rsi
0x1801216aa  push    rbp
0x1801216ab  push    rdi
0x1801216ac  push    r15
0x1801216ae  mov     rbp, rsp
0x1801216b1  sub     rsp, 50h
0x1801216b5  mov     rsi, state
0x1801216b8  call    ?TLSGetLogicalThread@@YAPEBU_GUID@@XZ; TLSGetLogicalThread(void)
0x1801216bd  test    rax, rax
0x1801216c0  jz      loc_18012178A
0x1801216c6  xor     r9d, r9d; lpName
0x1801216c9  xor     r8d, r8d; bInitialState
0x1801216cc  xor     ecx, ecx; lpEventAttributes
0x1801216ce  lea     r15d, [r9+1]
0x1801216d2  mov     edx, r15d; bManualReset
0x1801216d5  call    cs:__imp_CreateEventW
0x1801216db  mov     [rbp+wakeEvent.handle_], rax
0x1801216df  lea     state, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x1801216e6  mov     [rbp+wakeEvent.__vftable], state
0x1801216ea  test    rax, rax
0x1801216ed  jz      loc_1801218F1
0x1801216f3  mov     r9d, 100002h; dwDesiredAccess
0x1801216f9  xor     r8d, r8d; dwFlags
0x1801216fc  xor     edx, edx; lpTimerName
0x1801216fe  xor     ecx, ecx; lpTimerAttributes
0x180121700  call    cs:__imp_CreateWaitableTimerExW
0x180121706  mov     rbx, rax
0x180121709  mov     [rbp+freeUnusedDllsTimer.m_ptr], rax
0x18012170d  inc     rax
0x180121710  test    rax, 0FFFFFFFFFFFFFFFEh
0x180121716  jnz     loc_180121804
0x18012171c  mov     state, [rbp+18h]; callerReturnAddress
0x180121720  lea     r8, aOnecoreComComb_16; "onecore\\com\\combase\\dcomrem\\apartme"...
0x180121727  mov     r9d, 8007000Eh; hr
0x18012172d  lea     edx, [r15+6Fh]; lineNumber
0x180121731  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180121736  lea     state, [rbp+freeUnusedDllsTimer]; this
0x18012173a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18012173f  cmp     [rbp+wakeEvent.handle_], 0
0x180121744  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x18012174b  mov     [rbp+wakeEvent.__vftable], rax
0x18012174f  jz      loc_1801217FA
0x180121755  lea     state, [rbp+wakeEvent]; this
0x180121759  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x18012175e  test    al, al
0x180121760  jnz     loc_1801217FA
0x180121766  call    cs:__imp_GetLastError
0x18012176c  test    eax, eax
0x18012176e  jle     short loc_180121778
0x180121770  movzx   eax, ax
0x180121773  or      eax, 80070000h
0x180121778  xor     r9d, r9d; lpArguments
0x18012177b  xor     r8d, r8d; nNumberOfArguments
0x18012177e  mov     edx, r15d; dwExceptionFlags
0x180121781  mov     ecx, eax; dwExceptionCode
0x180121783  call    cs:__imp_RaiseException
0x180121789  int     3; Trap to Debugger
0x18012178a  mov     state, [rbp+18h]; callerReturnAddress
0x18012178e  lea     r8, aOnecoreComComb_16; "onecore\\com\\combase\\dcomrem\\apartme"...
0x180121795  mov     r9d, 8007000Eh; hr
0x18012179b  mov     edx, 6Ah ; 'j'; lineNumber
0x1801217a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801217a5  jmp     short loc_1801217FA
0x1801217a7  mov     state, [rbp+18h]; callerReturnAddress
0x1801217ab  lea     r8, aOnecoreComComb_16; "onecore\\com\\combase\\dcomrem\\apartme"...
0x1801217b2  mov     r9d, 8007000Eh; hr
0x1801217b8  mov     qword ptr [rsi], 0
0x1801217bf  mov     edx, 7Fh; lineNumber
0x1801217c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801217c9  lea     rax, [rbx-1]
0x1801217cd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801217d1  jbe     loc_1801218E3
0x1801217d7  cmp     [rbp+wakeEvent.handle_], 0
0x1801217dc  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x1801217e3  mov     [rbp+wakeEvent.__vftable], rax
0x1801217e7  jz      short loc_1801217FA
0x1801217e9  lea     state, [rbp+wakeEvent]; this
0x1801217ed  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x1801217f2  test    al, al
0x1801217f4  jz      loc_1801219E5
0x1801217fa  mov     eax, 8007000Eh
0x1801217ff  jmp     loc_1801218C6
0x180121804  mov     [rsp+50h+TolerableDelay], 7530h; TolerableDelay
0x18012180c  lea     rdx, [rbp+liDueTime]; lpDueTime
0x180121810  mov     [rsp+50h+WakeContext], 0; WakeContext
0x180121819  xor     r9d, r9d; pfnCompletionRoutine
0x18012181c  mov     r8d, 0EA60h; lPeriod
0x180121822  mov     [rsp+50h+lpArgToCompletionRoutine], 0; lpArgToCompletionRoutine
0x18012182b  mov     state, rbx; hTimer
0x18012182e  mov     qword ptr [rbp+liDueTime], 0FFFFFFFFDC3CBA00h
0x180121836  call    cs:__imp_SetWaitableTimerEx
0x18012183c  test    eax, eax
0x18012183e  jz      loc_180121957
0x180121844  mov     state, cs:?g_hHeap@@3QEAXEA; hHeap
0x18012184b  xor     edx, edx; dwFlags
0x18012184d  mov     r8d, 0F0h; dwBytes
0x180121853  call    cs:__imp_HeapAlloc
0x180121859  mov     rdi, rax
0x18012185c  test    rax, rax
0x18012185f  jz      loc_1801217A7
0x180121865  lea     r8, [rbp+freeUnusedDllsTimer]; freeUnusedDllsTimer
0x180121869  mov     state, rax; this
0x18012186c  lea     rdx, [rbp+wakeEvent]; wakeEvent
0x180121870  call    ??0ModernSTAState@@IEAA@$$QEAVEvent@Wrappers@WRL@Microsoft@@$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; ModernSTAState::ModernSTAState(Microsoft::WRL::Wrappers::Event &&,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180121875  mov     state, [rbp+freeUnusedDllsTimer.m_ptr]; hObject
0x180121879  lea     rax, ??_7BridgeSTAState@@6B@; const BridgeSTAState::`vftable'
0x180121880  mov     byte ptr [rdi+0E8h], 0
0x180121887  mov     dword ptr [rdi+0ECh], 0
0x180121891  mov     [rdi], rax
0x180121894  lea     rax, [state-1]
0x180121898  mov     [rsi], rdi
0x18012189b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18012189f  jbe     short loc_1801218DB
0x1801218a1  cmp     [rbp+wakeEvent.handle_], 0
0x1801218a6  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x1801218ad  mov     [rbp+wakeEvent.__vftable], rax
0x1801218b1  jz      short loc_1801218C4
0x1801218b3  lea     state, [rbp+wakeEvent]; this
0x1801218b7  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x1801218bc  test    al, al
0x1801218be  jz      loc_1801219C1
0x1801218c4  xor     eax, eax
0x1801218c6  lea     r11, [rsp+50h+var_s0]
0x1801218cb  mov     rbx, [r11+20h]
0x1801218cf  mov     rsi, [r11+38h]
0x1801218d3  mov     rsp, r11
0x1801218d6  pop     r15
0x1801218d8  pop     rdi
0x1801218d9  pop     rbp
0x1801218da  retn
0x1801218db  call    cs:__imp_CloseHandle
0x1801218e1  jmp     short loc_1801218A1
0x1801218e3  mov     state, rbx; hObject
0x1801218e6  call    cs:__imp_CloseHandle
0x1801218ec  jmp     loc_1801217D7
0x1801218f1  mov     state, [rbp+18h]; callerReturnAddress
0x1801218f5  lea     r8, aOnecoreComComb_16; "onecore\\com\\combase\\dcomrem\\apartme"...
0x1801218fc  mov     r9d, 8007000Eh; hr
0x180121902  mov     edx, 6Dh ; 'm'; lineNumber
0x180121907  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012190c  cmp     [rbp+wakeEvent.handle_], 0
0x180121911  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180121918  mov     [rbp+wakeEvent.__vftable], rax
0x18012191c  jz      loc_1801217FA
0x180121922  lea     state, [rbp+wakeEvent]; this
0x180121926  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x18012192b  test    al, al
0x18012192d  jnz     loc_1801217FA
0x180121933  call    cs:__imp_GetLastError
0x180121939  test    eax, eax
0x18012193b  jle     short loc_180121945
0x18012193d  movzx   eax, ax
0x180121940  or      eax, 80070000h
0x180121945  xor     r9d, r9d; lpArguments
0x180121948  xor     r8d, r8d; nNumberOfArguments
0x18012194b  mov     edx, r15d; dwExceptionFlags
0x18012194e  mov     ecx, eax; dwExceptionCode
0x180121950  call    cs:__imp_RaiseException
0x180121956  int     3; Trap to Debugger
0x180121957  mov     state, [rbp+18h]; callerReturnAddress
0x18012195b  lea     r8, aOnecoreComComb_16; "onecore\\com\\combase\\dcomrem\\apartme"...
0x180121962  mov     edx, 7Bh ; '{'; lineNumber
0x180121967  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18012196c  lea     state, [rbp+freeUnusedDllsTimer]; this
0x180121970  mov     ebx, eax
0x180121972  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180121977  cmp     [rbp+wakeEvent.handle_], 0
0x18012197c  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180121983  mov     [rbp+wakeEvent.__vftable], rax
0x180121987  jz      short loc_180121996
0x180121989  lea     state, [rbp+wakeEvent]; this
0x18012198d  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x180121992  test    al, al
0x180121994  jz      short loc_18012199D
0x180121996  mov     eax, ebx
0x180121998  jmp     loc_1801218C6
0x18012199d  call    cs:__imp_GetLastError
0x1801219a3  test    eax, eax
0x1801219a5  jle     short loc_1801219AF
0x1801219a7  movzx   eax, ax
0x1801219aa  or      eax, 80070000h
0x1801219af  xor     r9d, r9d; lpArguments
0x1801219b2  xor     r8d, r8d; nNumberOfArguments
0x1801219b5  mov     edx, r15d; dwExceptionFlags
0x1801219b8  mov     ecx, eax; dwExceptionCode
0x1801219ba  call    cs:__imp_RaiseException
0x1801219c0  int     3; Trap to Debugger
0x1801219c1  call    cs:__imp_GetLastError
0x1801219c7  test    eax, eax
0x1801219c9  jle     short loc_1801219D3
0x1801219cb  movzx   eax, ax
0x1801219ce  or      eax, 80070000h
0x1801219d3  xor     r9d, r9d; lpArguments
0x1801219d6  xor     r8d, r8d; nNumberOfArguments
0x1801219d9  mov     edx, r15d; dwExceptionFlags
0x1801219dc  mov     ecx, eax; dwExceptionCode
0x1801219de  call    cs:__imp_RaiseException
0x1801219e4  int     3; Trap to Debugger
0x1801219e5  call    cs:__imp_GetLastError
0x1801219eb  test    eax, eax
0x1801219ed  jle     short loc_1801219F7
0x1801219ef  movzx   eax, ax
0x1801219f2  or      eax, 80070000h
0x1801219f7  xor     r9d, r9d; lpArguments
0x1801219fa  xor     r8d, r8d; nNumberOfArguments
0x1801219fd  mov     edx, r15d; dwExceptionFlags
0x180121a00  mov     ecx, eax; dwExceptionCode
0x180121a02  call    cs:__imp_RaiseException
```
