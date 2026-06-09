# NGENService::ControllerInit(void)

- ea: `0x1800046c4`
- end: `0x180004af2`
- name: `?ControllerInit@NGENService@@YAJXZ`
- size: `1070`
- prototype: `__int64 __fastcall(NGENService *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18001a9d8`

## callees

- `0x180002e24`
- `0x18000352c`
- `0x1800035bc`
- `0x180003874`
- `0x1800039ac`
- `0x180004580`
- `0x1800046c4`
- `0x180004af4`
- `0x180006328`
- `0x18002e1d0`
- `0x180037340`
- `0x18003dc30`
- `0x18003e73c`
- `0x18003f280`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1800047be`
- `KERNEL32!LoadLibraryExW` at `0x18000482e`
- `KERNEL32!LoadLibraryExW` at `0x1800047be`
- `KERNEL32!LoadLibraryExW` at `0x18000482e`
- `KERNEL32!EnterCriticalSection` at `0x18000476c`
- `KERNEL32!EnterCriticalSection` at `0x18000476c`
- `KERNEL32!LeaveCriticalSection` at `0x180004887`
- `KERNEL32!LeaveCriticalSection` at `0x180004887`
- `KERNEL32!CreateEventW` at `0x1800048aa`
- `KERNEL32!CreateEventW` at `0x1800048d2`
- `KERNEL32!CreateEventW` at `0x1800048fa`
- `KERNEL32!CreateEventW` at `0x180004922`
- `KERNEL32!CreateEventW` at `0x18000494a`
- `KERNEL32!CreateEventW` at `0x180004972`
- `KERNEL32!CreateEventW` at `0x1800048aa`
- `KERNEL32!CreateEventW` at `0x1800048d2`
- `KERNEL32!CreateEventW` at `0x1800048fa`
- `KERNEL32!CreateEventW` at `0x180004922`
- `KERNEL32!CreateEventW` at `0x18000494a`
- `KERNEL32!CreateEventW` at `0x180004972`
- `KERNEL32!GetLastError` at `0x180004a44`
- `KERNEL32!GetLastError` at `0x180004a44`
- `KERNEL32!CreateThread` at `0x180004a26`
- `KERNEL32!CreateThread` at `0x180004a26`
- `KERNEL32!GetProcAddress` at `0x1800047d3`
- `KERNEL32!GetProcAddress` at `0x180004843`
- `KERNEL32!GetProcAddress` at `0x1800047d3`
- `KERNEL32!GetProcAddress` at `0x180004843`
- `KERNEL32!HeapFree` at `0x180004abd`
- `KERNEL32!HeapFree` at `0x180004abd`
- `KERNEL32!GetProcessHeap` at `0x180004aa8`
- `KERNEL32!GetProcessHeap` at `0x180004aa8`

## string_xrefs

- `0x18000473c`: `InitController(): Service running with server policy\n`
- `0x180004743`: `InitController(): Service running with client policy\n`
- `0x1800048bc`: `InitController(): Failed to create interrupt event\n`
- `0x1800048e4`: `InitController(): Failed to create controller state change event\n`
- `0x18000490c`: `InitController(): Failed to create resume listener event\n`
- `0x180004934`: `InitController(): Failed to create dirty root store event\n`
- `0x18000495c`: `InitController(): Failed to create SCM event\n`
- `0x180004984`: `InitController(): Failed to create Listener shutdown\n`
- `0x1800049a2`: `InitController(): Failed to get NGENService state registry key\n`
- `0x1800049c5`: `InitController(): Failed to get NGENService idle state registry key\n`
- `0x180004a38`: `InitController(): Failed to create listener thread\n`
- `0x1800047b7`: `kernel32.dll`
- `0x180004827`: `kernel32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=403
__int64 __fastcall NGENService::ControllerInit(NGENService *this)
{
  int v1; // eax
  wchar_t *v2; // rcx
  __int64 v3; // r8
  FARPROC ProcAddress; // rax
  HMODULE Library; // rax
  __int64 v6; // rbx
  FARPROC v7; // rax
  HMODULE v8; // rax
  int v9; // eax
  unsigned __int16 **v10; // rdx
  NGENService *v11; // rcx
  NGENService *v12; // rcx
  signed int RandomName; // ebx
  unsigned __int16 *v14; // rdx
  wchar_t *v15; // rcx
  const unsigned __int16 *v16; // rdx
  wchar_t *v17; // rcx
  const unsigned __int16 *v18; // r8
  NGENService *v19; // rcx
  signed int LastError; // eax
  const unsigned __int16 *v21; // rdx
  const unsigned __int16 *v22; // rdx
  _DWORD v24[70]; // [rsp+278h] [rbp+170h] BYREF
  __int16 v25; // [rsp+390h] [rbp+288h]

  NGENService::g_bStopEventListener = 0;
  v1 = NGENService::ConfigServicePolicy();
  v2 = L"InitController(): Service running with server policy\n";
  if ( v1 != 1 )
    v2 = L"InitController(): Service running with client policy\n";
  NGENService::DebugLog((NGENService *)v2, L"InitController(): Service running with client policy\n");
  EnterCriticalSection(&NGENService::g_IdleCS);
  memset_0(v24, 0, 0x11Cu);
  v24[0] = 284;
  v25 = 272;
  ProcAddress = (FARPROC)qword_18006FFC0;
  if ( qword_18006FFC0
    || !bVerSetConditionMaskProbed
    && ((Library = LoadLibraryExW(L"kernel32.dll", 0, 0)) == 0
      ? (ProcAddress = (FARPROC)qword_18006FFC0)
      : (FARPROC)(ProcAddress = GetProcAddress(Library, "VerSetConditionMask"), qword_18006FFC0 = (__int64)ProcAddress),
        bVerSetConditionMaskProbed = 1,
        ProcAddress) )
  {
    LOBYTE(v3) = 7;
    v6 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64))ProcAddress)(0, 64, v3);
  }
  else
  {
    v6 = 0;
  }
  v7 = (FARPROC)qword_18006FFB8;
  if ( qword_18006FFB8
    || !bVerifyVersionInfoProbed
    && ((v8 = LoadLibraryExW(L"kernel32.dll", 0, 0)) == 0
      ? (v7 = (FARPROC)qword_18006FFB8)
      : (FARPROC)(v7 = GetProcAddress(v8, "VerifyVersionInfoW"), qword_18006FFB8 = (__int64)v7),
        bVerifyVersionInfoProbed = 1,
        v7) )
  {
    v9 = ((__int64 (__fastcall *)(_DWORD *, __int64, __int64))v7)(v24, 64, v6);
  }
  else
  {
    v9 = 0;
  }
  NGENService::g_fRunningOnTS = v9;
  LeaveCriticalSection(&NGENService::g_IdleCS);
  RandomName = NGENService::GenerateRandomName(v11, v10);
  if ( RandomName < 0 )
    goto LABEL_46;
  NGENService::g_hInterruptEvent = CreateEventW(0, 1, 0, NGENService::g_bstrInterruptEventName);
  if ( !NGENService::g_hInterruptEvent )
  {
    v15 = L"InitController(): Failed to create interrupt event\n";
    goto LABEL_44;
  }
  NGENService::g_hControllerStateChange = CreateEventW(0, 1, 0, 0);
  if ( !NGENService::g_hControllerStateChange )
  {
    v15 = L"InitController(): Failed to create controller state change event\n";
    goto LABEL_44;
  }
  NGENService::g_hInterruptProcessedEvent = CreateEventW(0, 1, 1, 0);
  if ( !NGENService::g_hInterruptProcessedEvent )
  {
    v15 = L"InitController(): Failed to create resume listener event\n";
    goto LABEL_44;
  }
  NGENService::g_hRootStoreDirtyEvent = CreateEventW(0, 1, 0, 0);
  if ( !NGENService::g_hRootStoreDirtyEvent )
  {
    v15 = L"InitController(): Failed to create dirty root store event\n";
    goto LABEL_44;
  }
  NGENService::g_hSCMRequestEvent = CreateEventW(0, 1, 0, 0);
  if ( !NGENService::g_hSCMRequestEvent )
  {
    v15 = L"InitController(): Failed to create SCM event\n";
    goto LABEL_44;
  }
  NGENService::g_hListenerShutdownEvent = CreateEventW(0, 1, 0, 0);
  if ( !NGENService::g_hListenerShutdownEvent )
  {
    v15 = L"InitController(): Failed to create Listener shutdown\n";
LABEL_44:
    NGENService::DebugLog((NGENService *)v15, v14);
    LastError = GetLastError();
    RandomName = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      RandomName = LastError;
    goto LABEL_46;
  }
  RandomName = NGENService::NGENServiceDirtyStateKey(&NGENService::g_hkNGENServiceListenedState, (HKEY *)v14);
  if ( RandomName >= 0 )
  {
    RandomName = NGENServicePersistentStateKey(&NGENService::g_hkNGENServicePersistentState);
    if ( RandomName >= 0 )
    {
      if ( (unsigned int)REGUTIL::GetLong(L"RootstoreDirty", (int)v16, v18, NGENService::g_hkNGENServiceListenedState)
        && (RandomName = NGENService::ControllerState::SetAccumulatedWaitIdleTime(0), RandomName < 0) )
      {
        v17 = L"InitController(): Failed to reset idle timeout\n";
      }
      else
      {
        RandomName = NGENService::ResetDirtyRootStore(v19);
        if ( RandomName >= 0 )
        {
          NGENService::g_hListenerThread = CreateThread(0, 0, NGENService::Listener, 0, 0, 0);
          if ( NGENService::g_hListenerThread )
          {
            NGENService::ControllerState::Set(0, 7u);
            NGENService::g_InterruptMask = 0;
            NGENService::DebugLog((NGENService *)L"InitController(): Success\n", v22);
            return 0;
          }
          v15 = L"InitController(): Failed to create listener thread\n";
          goto LABEL_44;
        }
        v17 = L"InitController(): Failed to register root store notifier\n";
      }
    }
    else
    {
      v17 = L"InitController(): Failed to get NGENService idle state registry key\n";
    }
  }
  else
  {
    v17 = L"InitController(): Failed to get NGENService state registry key\n";
  }
  NGENService::DebugLog((NGENService *)v17, v16);
LABEL_46:
  NGENService::ControllerShutdown(v12);
  NGENService::DebugLog((NGENService *)L"InitController(): Failed\nr", v21);
  return (unsigned int)RandomName;
}

```

## disassembly

```asm
0x1800046c4  mov     rax, rsp
0x1800046c7  mov     [rax+8], rbx
0x1800046cb  mov     [rax+10h], rsi
0x1800046cf  mov     [rax+18h], rdi
0x1800046d3  mov     [rax+20h], r15
0x1800046d7  push    rbp
0x1800046d8  lea     rbp, [rax-2A8h]
0x1800046df  sub     rsp, 3A0h
0x1800046e6  mov     rax, cs:__security_cookie
0x1800046ed  xor     rax, rsp
0x1800046f0  mov     [rbp+2A0h+var_10], rax
0x1800046f7  or      qword ptr [rsp+3A0h+var_360], 0FFFFFFFFFFFFFFFFh
0x1800046fd  xor     esi, esi
0x1800046ff  mov     dword ptr [rsp+3A0h+var_358], esi
0x180004703  mov     qword ptr [rsp+3A0h+var_350], rsi
0x180004708  mov     qword ptr [rsp+54h], 200h
0x180004711  mov     [rsp+3A0h+lpMem], rsi
0x180004716  lea     rax, [rsp+3A0h+var_338]
0x18000471b  mov     [rsp+3A0h+lpMem], rax
0x180004720  mov     dword ptr [rsp+3A0h+var_350], 2
0x180004728  mov     rax, [rsp+3A0h+lpMem]
0x18000472d  mov     [rax], si
0x180004730  mov     cs:?g_bStopEventListener@NGENService@@3V?$Volatile@_N@@A, sil; Volatile<bool> NGENService::g_bStopEventListener
0x180004737  call    ?ConfigServicePolicy@NGENService@@YA?AW4Policy@1@XZ; NGENService::ConfigServicePolicy(void)
0x18000473c  lea     rcx, aInitcontroller_3; "InitController(): Service running with "...
0x180004743  lea     rdx, aInitcontroller_2; "InitController(): Service running with "...
0x18000474a  lea     edi, [rsi+1]
0x18000474d  cmp     eax, edi
0x18000474f  cmovnz  rcx, rdx; this
0x180004753  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x180004758  lea     r15, ?g_IdleCS@NGENService@@3VCriticalSection@@A; CriticalSection NGENService::g_IdleCS
0x18000475f  mov     qword ptr [rsp+3A0h+var_370], r15
0x180004764  mov     byte ptr [rsp+3A0h+var_368], sil
0x180004769  mov     rcx, r15; lpCriticalSection
0x18000476c  call    cs:__imp_EnterCriticalSection
0x180004772  mov     byte ptr [rsp+3A0h+var_368], dil
0x180004777  mov     ebx, 11Ch
0x18000477c  mov     r8d, ebx; Size
0x18000477f  xor     edx, edx; Val
0x180004781  lea     rcx, [rbp+2A0h+var_130]; void *
0x180004788  call    memset_0
0x18000478d  mov     [rbp+2A0h+var_130], ebx
0x180004793  lea     eax, [rbx-0Ch]
0x180004796  mov     [rbp+2A0h+var_18], ax
0x18000479d  mov     rax, cs:qword_18006FFC0
0x1800047a4  test    rax, rax
0x1800047a7  jnz     short loc_1800047FA
0x1800047a9  cmp     cs:?bVerSetConditionMaskProbed@@3_NA, sil; bool bVerSetConditionMaskProbed
0x1800047b0  jnz     short loc_1800047F5
0x1800047b2  xor     r8d, r8d; dwFlags
0x1800047b5  xor     edx, edx; hFile
0x1800047b7  lea     rcx, LibFileName; "kernel32.dll"
0x1800047be  call    cs:__imp_LoadLibraryExW
0x1800047c4  test    rax, rax
0x1800047c7  jz      short loc_1800047E2
0x1800047c9  lea     rdx, ProcName; "VerSetConditionMask"
0x1800047d0  mov     rcx, rax; hModule
0x1800047d3  call    cs:__imp_GetProcAddress
0x1800047d9  mov     cs:qword_18006FFC0, rax
0x1800047e0  jmp     short loc_1800047E9
0x1800047e2  mov     rax, cs:qword_18006FFC0
0x1800047e9  mov     cs:?bVerSetConditionMaskProbed@@3_NA, dil; bool bVerSetConditionMaskProbed
0x1800047f0  test    rax, rax
0x1800047f3  jnz     short loc_1800047FA
0x1800047f5  mov     rbx, rsi
0x1800047f8  jmp     short loc_18000480D
0x1800047fa  mov     r8b, 7
0x1800047fd  mov     edx, 40h ; '@'
0x180004802  xor     ecx, ecx
0x180004804  call    cs:__guard_dispatch_icall_fptr
0x18000480a  mov     rbx, rax
0x18000480d  mov     rax, cs:qword_18006FFB8
0x180004814  test    rax, rax
0x180004817  jnz     short loc_180004869
0x180004819  cmp     cs:?bVerifyVersionInfoProbed@@3_NA, sil; bool bVerifyVersionInfoProbed
0x180004820  jnz     short loc_180004865
0x180004822  xor     r8d, r8d; dwFlags
0x180004825  xor     edx, edx; hFile
0x180004827  lea     rcx, LibFileName; "kernel32.dll"
0x18000482e  call    cs:__imp_LoadLibraryExW
0x180004834  test    rax, rax
0x180004837  jz      short loc_180004852
0x180004839  lea     rdx, aVerifyversioni; "VerifyVersionInfoW"
0x180004840  mov     rcx, rax; hModule
0x180004843  call    cs:__imp_GetProcAddress
0x180004849  mov     cs:qword_18006FFB8, rax
0x180004850  jmp     short loc_180004859
0x180004852  mov     rax, cs:qword_18006FFB8
0x180004859  mov     cs:?bVerifyVersionInfoProbed@@3_NA, dil; bool bVerifyVersionInfoProbed
0x180004860  test    rax, rax
0x180004863  jnz     short loc_180004869
0x180004865  mov     eax, esi
0x180004867  jmp     short loc_18000487E
0x180004869  mov     r8, rbx
0x18000486c  mov     edx, 40h ; '@'
0x180004871  lea     rcx, [rbp+2A0h+var_130]
0x180004878  call    cs:__guard_dispatch_icall_fptr
0x18000487e  mov     cs:?g_fRunningOnTS@NGENService@@3HA, eax; int NGENService::g_fRunningOnTS
0x180004884  mov     rcx, r15; lpCriticalSection
0x180004887  call    cs:__imp_LeaveCriticalSection
0x18000488d  call    ?GenerateRandomName@NGENService@@YAJPEAPEAG@Z; NGENService::GenerateRandomName(ushort * *)
0x180004892  mov     ebx, eax
0x180004894  test    eax, eax
0x180004896  js      loc_180004A58
0x18000489c  mov     r9, cs:?g_bstrInterruptEventName@NGENService@@3PEAGEA; lpName
0x1800048a3  xor     r8d, r8d; bInitialState
0x1800048a6  mov     edx, edi; bManualReset
0x1800048a8  xor     ecx, ecx; lpEventAttributes
0x1800048aa  call    cs:__imp_CreateEventW
0x1800048b0  mov     cs:?g_hInterruptEvent@NGENService@@3PEAXEA, rax; void * NGENService::g_hInterruptEvent
0x1800048b7  test    rax, rax
0x1800048ba  jnz     short loc_1800048C8
0x1800048bc  lea     rcx, aInitcontroller_1; "InitController(): Failed to create inte"...
0x1800048c3  jmp     loc_180004A3F
0x1800048c8  xor     r9d, r9d; lpName
0x1800048cb  xor     r8d, r8d; bInitialState
0x1800048ce  mov     edx, edi; bManualReset
0x1800048d0  xor     ecx, ecx; lpEventAttributes
0x1800048d2  call    cs:__imp_CreateEventW
0x1800048d8  mov     cs:?g_hControllerStateChange@NGENService@@3PEAXEA, rax; void * NGENService::g_hControllerStateChange
0x1800048df  test    rax, rax
0x1800048e2  jnz     short loc_1800048F0
0x1800048e4  lea     rcx, aInitcontroller_13; "InitController(): Failed to create cont"...
0x1800048eb  jmp     loc_180004A3F
0x1800048f0  xor     r9d, r9d; lpName
0x1800048f3  mov     r8d, edi; bInitialState
0x1800048f6  mov     edx, edi; bManualReset
0x1800048f8  xor     ecx, ecx; lpEventAttributes
0x1800048fa  call    cs:__imp_CreateEventW
0x180004900  mov     cs:?g_hInterruptProcessedEvent@NGENService@@3PEAXEA, rax; void * NGENService::g_hInterruptProcessedEvent
0x180004907  test    rax, rax
0x18000490a  jnz     short loc_180004918
0x18000490c  lea     rcx, aInitcontroller_8; "InitController(): Failed to create resu"...
0x180004913  jmp     loc_180004A3F
0x180004918  xor     r9d, r9d; lpName
0x18000491b  xor     r8d, r8d; bInitialState
0x18000491e  mov     edx, edi; bManualReset
0x180004920  xor     ecx, ecx; lpEventAttributes
0x180004922  call    cs:__imp_CreateEventW
0x180004928  mov     cs:?g_hRootStoreDirtyEvent@NGENService@@3PEAXEA, rax; void * NGENService::g_hRootStoreDirtyEvent
0x18000492f  test    rax, rax
0x180004932  jnz     short loc_180004940
0x180004934  lea     rcx, aInitcontroller_6; "InitController(): Failed to create dirt"...
0x18000493b  jmp     loc_180004A3F
0x180004940  xor     r9d, r9d; lpName
0x180004943  xor     r8d, r8d; bInitialState
0x180004946  mov     edx, edi; bManualReset
0x180004948  xor     ecx, ecx; lpEventAttributes
0x18000494a  call    cs:__imp_CreateEventW
0x180004950  mov     cs:?g_hSCMRequestEvent@NGENService@@3PEAXEA, rax; void * NGENService::g_hSCMRequestEvent
0x180004957  test    rax, rax
0x18000495a  jnz     short loc_180004968
0x18000495c  lea     rcx, aInitcontroller_7; "InitController(): Failed to create SCM "...
0x180004963  jmp     loc_180004A3F
0x180004968  xor     r9d, r9d; lpName
0x18000496b  xor     r8d, r8d; bInitialState
0x18000496e  mov     edx, edi; bManualReset
0x180004970  xor     ecx, ecx; lpEventAttributes
0x180004972  call    cs:__imp_CreateEventW
0x180004978  mov     cs:?g_hListenerShutdownEvent@NGENService@@3PEAXEA, rax; void * NGENService::g_hListenerShutdownEvent
0x18000497f  test    rax, rax
0x180004982  jnz     short loc_180004990
0x180004984  lea     rcx, aInitcontroller_5; "InitController(): Failed to create List"...
0x18000498b  jmp     loc_180004A3F
0x180004990  lea     rcx, ?g_hkNGENServiceListenedState@NGENService@@3PEAUHKEY__@@EA; this
0x180004997  call    ?NGENServiceDirtyStateKey@NGENService@@YAJPEAPEAUHKEY__@@@Z; NGENService::NGENServiceDirtyStateKey(HKEY__ * *)
0x18000499c  mov     ebx, eax
0x18000499e  test    eax, eax
0x1800049a0  jns     short loc_1800049B3
0x1800049a2  lea     rcx, aInitcontroller_4; "InitController(): Failed to get NGENSer"...
0x1800049a9  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x1800049ae  jmp     loc_180004A58
0x1800049b3  lea     rcx, ?g_hkNGENServicePersistentState@NGENService@@3PEAUHKEY__@@EA; HKEY *
0x1800049ba  call    NGENServicePersistentStateKey
0x1800049bf  mov     ebx, eax
0x1800049c1  test    eax, eax
0x1800049c3  jns     short loc_1800049CE
0x1800049c5  lea     rcx, aInitcontroller_9; "InitController(): Failed to get NGENSer"...
0x1800049cc  jmp     short loc_1800049A9
0x1800049ce  mov     r9, cs:?g_hkNGENServiceListenedState@NGENService@@3PEAUHKEY__@@EA; HKEY
0x1800049d5  lea     rcx, aRootstoredirty; "RootstoreDirty"
0x1800049dc  call    ?GetLong@REGUTIL@@SAJPEBGJ0PEAUHKEY__@@@Z; REGUTIL::GetLong(ushort const *,long,ushort const *,HKEY__ *)
0x1800049e1  test    eax, eax
0x1800049e3  jz      short loc_1800049FB
0x1800049e5  xor     ecx, ecx; unsigned int
0x1800049e7  call    ?SetAccumulatedWaitIdleTime@ControllerState@NGENService@@SAJK@Z; NGENService::ControllerState::SetAccumulatedWaitIdleTime(ulong)
0x1800049ec  mov     ebx, eax
0x1800049ee  test    eax, eax
0x1800049f0  jns     short loc_1800049FB
0x1800049f2  lea     rcx, aInitcontroller_0; "InitController(): Failed to reset idle "...
0x1800049f9  jmp     short loc_1800049A9
0x1800049fb  call    ?ResetDirtyRootStore@NGENService@@YAJXZ; NGENService::ResetDirtyRootStore(void)
0x180004a00  mov     ebx, eax
0x180004a02  test    eax, eax
0x180004a04  jns     short loc_180004A0F
0x180004a06  lea     rcx, aInitcontroller_10; "InitController(): Failed to register ro"...
0x180004a0d  jmp     short loc_1800049A9
0x180004a0f  mov     [rsp+3A0h+lpThreadId], rsi; lpThreadId
0x180004a14  mov     [rsp+3A0h+dwCreationFlags], esi; dwCreationFlags
0x180004a18  xor     r9d, r9d; lpParameter
0x180004a1b  lea     r8, ?Listener@NGENService@@YAKPEAX@Z; lpStartAddress
0x180004a22  xor     edx, edx; dwStackSize
0x180004a24  xor     ecx, ecx; lpThreadAttributes
0x180004a26  call    cs:__imp_CreateThread
0x180004a2c  mov     cs:?g_hListenerThread@NGENService@@3PEAXEA, rax; void * NGENService::g_hListenerThread
0x180004a33  test    rax, rax
0x180004a36  jnz     short loc_180004A6B
0x180004a38  lea     rcx, aInitcontroller_12; "InitController(): Failed to create list"...
0x180004a3f  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x180004a44  call    cs:__imp_GetLastError
0x180004a4a  movzx   ebx, ax
0x180004a4d  or      ebx, 80070000h
0x180004a53  test    eax, eax
0x180004a55  cmovle  ebx, eax
0x180004a58  call    ?ControllerShutdown@NGENService@@YAXXZ; NGENService::ControllerShutdown(void)
0x180004a5d  lea     rcx, aInitcontroller; "InitController(): Failed\nr"
0x180004a64  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x180004a69  jmp     short loc_180004A8B
0x180004a6b  mov     edx, 7; unsigned int
0x180004a70  xor     ecx, ecx; unsigned int
0x180004a72  call    ?Set@ControllerState@NGENService@@SAXKK@Z; NGENService::ControllerState::Set(ulong,ulong)
0x180004a77  mov     cs:?g_InterruptMask@NGENService@@3KA, esi; ulong NGENService::g_InterruptMask
0x180004a7d  lea     rcx, aInitcontroller_11; "InitController(): Success\n"
0x180004a84  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x180004a89  mov     ebx, esi
0x180004a8b  test    byte ptr [rsp+3A0h+var_348], 8
0x180004a90  jz      short loc_180004AC4
0x180004a92  mov     rdi, [rsp+3A0h+lpMem]
0x180004a97  test    rdi, rdi
0x180004a9a  jz      short loc_180004AC4
0x180004a9c  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180004aa3  test    rax, rax
0x180004aa6  jnz     short loc_180004AB5
0x180004aa8  call    cs:__imp_GetProcessHeap
0x180004aae  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180004ab5  mov     r8, rdi; lpMem
0x180004ab8  xor     edx, edx; dwFlags
0x180004aba  mov     rcx, rax; hHeap
0x180004abd  call    cs:__imp_HeapFree
0x180004ac3  nop
0x180004ac4  mov     eax, ebx
0x180004ac6  mov     rcx, [rbp+2A0h+var_10]
0x180004acd  xor     rcx, rsp; StackCookie
0x180004ad0  call    __security_check_cookie
0x180004ad5  lea     r11, [rsp+3A0h+var_s0]
0x180004add  mov     rbx, [r11+10h]
0x180004ae1  mov     rsi, [r11+18h]
0x180004ae5  mov     rdi, [r11+20h]
0x180004ae9  mov     r15, [r11+28h]
0x180004aed  mov     rsp, r11
0x180004af0  pop     rbp
0x180004af1  retn
```
