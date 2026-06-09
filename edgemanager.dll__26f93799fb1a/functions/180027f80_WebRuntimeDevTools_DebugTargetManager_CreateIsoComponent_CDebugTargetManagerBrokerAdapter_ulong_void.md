# WebRuntimeDevTools::DebugTargetManager::CreateIsoComponent(CDebugTargetManagerBrokerAdapter *,ulong *,void * *)

- ea: `0x180027f80`
- end: `0x180028159`
- name: `?CreateIsoComponent@DebugTargetManager@WebRuntimeDevTools@@SAJPEAVCDebugTargetManagerBrokerAdapter@@PEAKPEAPEAX@Z`
- size: `473`
- prototype: `__int64 __fastcall(struct CDebugTargetManagerBrokerAdapter *, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180072b98`

## callees

- `0x180018b30`
- `0x180027f80`
- `0x180028160`
- `0x1800283d8`
- `0x18002b530`
- `0x18002c5b0`
- `0x180037b5c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180027fd0`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180027fd0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800280dd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800280dd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180028050`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180028050`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028106`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028106`
- `edgeIso!__imp_?IsoFreeSharedMemory@@YAJK@Z` at `0x1800280c4`
- `edgeIso!__imp_?IsoFreeSharedMemory@@YAJK@Z` at `0x1800280c4`
- `edgeIso!__imp_?IsoCreateComponentByCreDat@@YAJKPEAU_IsoCreationComponentData@@PEBGPEAK22PEAU_IsoWindowsContainer@@PEA_KW4IsoCreationFailureTreatment@@@Z` at `0x1800280b1`
- `edgeIso!__imp_?IsoCreateComponentByCreDat@@YAJKPEAU_IsoCreationComponentData@@PEBGPEAK22PEAU_IsoWindowsContainer@@PEA_KW4IsoCreationFailureTreatment@@@Z` at `0x1800280b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WebRuntimeDevTools::DebugTargetManager::CreateIsoComponent(
        struct CDebugTargetManagerBrokerAdapter *a1,
        unsigned int *a2,
        void **a3)
{
  const char *v6; // r9
  const char *v7; // r9
  unsigned int v8; // ebx
  const char *v9; // r9
  unsigned int v10; // ecx
  void *v11; // rdx
  unsigned int v13; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v14; // [rsp+58h] [rbp-A8h] BYREF
  char v15; // [rsp+60h] [rbp-A0h]
  void *v16; // [rsp+68h] [rbp-98h]
  __int64 v17; // [rsp+70h] [rbp-90h]
  __int64 v18; // [rsp+78h] [rbp-88h]
  _BYTE v19[2]; // [rsp+80h] [rbp-80h] BYREF
  __int16 v20; // [rsp+82h] [rbp-7Eh]
  int v21; // [rsp+90h] [rbp-70h]
  int v22; // [rsp+1ECh] [rbp+ECh]
  unsigned int v23; // [rsp+21Ch] [rbp+11Ch]
  int v24; // [rsp+220h] [rbp+120h]
  struct CDebugTargetManagerBrokerAdapter *v25; // [rsp+238h] [rbp+138h]
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+238h]

  if ( !InitOnceExecuteOnce(
          &WebRuntimeDevTools::DebugTargetManager::s_initOnce,
          WebRuntimeDevTools::DebugTargetManager::InitializeOnce,
          0,
          0) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\debugtargetmanager.cpp",
      v6);
  v13 = 0;
  v14 = 0;
  v16 = 0;
  v15 = 0;
  v17 = 0;
  v18 = 0;
  memset_0(v19, 0, 0x278u);
  v19[0] = 1;
  v20 = 632;
  v24 = 139;
  v22 = 2;
  v21 = 105;
  WebRuntimeDevTools::DebugTargetManager::s_isoCompCreatedEvent = CreateEventW(0, 0, 0, 0);
  if ( !WebRuntimeDevTools::DebugTargetManager::s_isoCompCreatedEvent )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x198,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\debugtargetmanager.cpp",
      v7);
  v25 = a1;
  v8 = IsoCreateComponentByCreDat(0x2000, v19, 0, &v13);
  if ( v8 <= 1 )
  {
    if ( WaitForSingleObject(WebRuntimeDevTools::DebugTargetManager::s_isoCompCreatedEvent, 0xFFFFFFFF) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x1AC,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\debugtargetmanager.cpp",
        v9);
    v8 = 0;
    CloseHandle(WebRuntimeDevTools::DebugTargetManager::s_isoCompCreatedEvent);
    WebRuntimeDevTools::DebugTargetManager::s_isoCompCreatedEvent = 0;
    v10 = v13;
    *a2 = v13;
    v11 = v16;
    *a3 = v16;
    WebRuntimeDiagnostics::LCIEDiagnosticsSession::AddIsoThreadHandle(v10, v11);
  }
  else
  {
    IsoFreeSharedMemory(v23);
  }
  _IsoWindowsContainer::~_IsoWindowsContainer((_IsoWindowsContainer *)&v14);
  return v8;
}

```

## disassembly

```asm
0x180027f80  mov     [rsp-8+arg_0], rbx
0x180027f85  push    rbp
0x180027f86  push    rsi
0x180027f87  push    rdi
0x180027f88  push    r14
0x180027f8a  push    r15
0x180027f8c  lea     rbp, [rsp-210h]
0x180027f94  sub     rsp, 310h
0x180027f9b  mov     rax, cs:__security_cookie
0x180027fa2  xor     rax, rsp
0x180027fa5  mov     [rbp+230h+var_30], rax
0x180027fac  mov     rsi, r8
0x180027faf  mov     rdi, rdx
0x180027fb2  mov     r14, rcx
0x180027fb5  mov     rbx, [rbp+238h]
0x180027fbc  xor     r9d, r9d; Context
0x180027fbf  xor     r8d, r8d; Parameter
0x180027fc2  lea     rdx, ?InitializeOnce@DebugTargetManager@WebRuntimeDevTools@@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180027fc9  lea     rcx, ?s_initOnce@DebugTargetManager@WebRuntimeDevTools@@0T_RTL_RUN_ONCE@@A; InitOnce
0x180027fd0  call    cs:__imp_InitOnceExecuteOnce
0x180027fd6  xor     r15d, r15d
0x180027fd9  test    eax, eax
0x180027fdb  jnz     short loc_180027FF2
0x180027fdd  lea     r8, aOnecoreuapInet_2; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x180027fe4  mov     edx, 18Ch; void *
0x180027fe9  mov     rcx, rbx; this
0x180027fec  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180027ff2  mov     [rsp+330h+var_2E0], r15d
0x180027ff7  mov     [rsp+330h+var_2D8], r15
0x180027ffc  mov     [rsp+330h+var_2C8], r15
0x180028001  mov     [rsp+330h+var_2D0], r15b
0x180028006  mov     [rsp+330h+var_2C0], r15
0x18002800b  mov     [rsp+330h+var_2B8], r15
0x180028010  mov     ebx, 278h
0x180028015  mov     r8d, ebx; Size
0x180028018  xor     edx, edx; Val
0x18002801a  lea     rcx, [rbp+230h+var_2B0]; void *
0x18002801e  call    memset_0
0x180028023  mov     [rbp+230h+var_2B0], 1
0x180028027  mov     [rbp+230h+var_2AE], bx
0x18002802b  mov     [rbp+230h+var_110], 8Bh
0x180028035  mov     [rbp+230h+var_144], 2
0x18002803f  mov     [rbp+230h+var_2A0], 69h ; 'i'
0x180028046  xor     r9d, r9d; lpName
0x180028049  xor     r8d, r8d; bInitialState
0x18002804c  xor     edx, edx; bManualReset
0x18002804e  xor     ecx, ecx; lpEventAttributes
0x180028050  call    cs:__imp_CreateEventW
0x180028056  mov     cs:?s_isoCompCreatedEvent@DebugTargetManager@WebRuntimeDevTools@@0PEAXEA, rax; void * WebRuntimeDevTools::DebugTargetManager::s_isoCompCreatedEvent
0x18002805d  mov     rcx, [rbp+238h]; this
0x180028064  test    rax, rax
0x180028067  jnz     short loc_18002807B
0x180028069  lea     r8, aOnecoreuapInet_2; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x180028070  mov     edx, 198h; void *
0x180028075  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002807b  mov     [rbp+230h+var_F8], r14
0x180028082  mov     [rsp+330h+var_2F0], r15d
0x180028087  mov     [rsp+330h+var_2F8], r15
0x18002808c  lea     rax, [rsp+330h+var_2D8]
0x180028091  mov     [rsp+330h+var_300], rax
0x180028096  mov     [rsp+330h+var_308], r15
0x18002809b  mov     [rsp+330h+var_310], r15
0x1800280a0  lea     r9, [rsp+330h+var_2E0]
0x1800280a5  xor     r8d, r8d
0x1800280a8  lea     rdx, [rbp+230h+var_2B0]
0x1800280ac  mov     ecx, 2000h
0x1800280b1  call    cs:__imp_?IsoCreateComponentByCreDat@@YAJKPEAU_IsoCreationComponentData@@PEBGPEAK22PEAU_IsoWindowsContainer@@PEA_KW4IsoCreationFailureTreatment@@@Z; IsoCreateComponentByCreDat(ulong,_IsoCreationComponentData *,ushort const *,ulong *,ulong *,ulong *,_IsoWindowsContainer *,unsigned __int64 *,IsoCreationFailureTreatment)
0x1800280b7  mov     ebx, eax
0x1800280b9  cmp     eax, 1
0x1800280bc  jbe     short loc_1800280CC
0x1800280be  mov     ecx, [rbp+230h+var_114]
0x1800280c4  call    cs:__imp_?IsoFreeSharedMemory@@YAJK@Z; IsoFreeSharedMemory(ulong)
0x1800280ca  jmp     short loc_180028127
0x1800280cc  mov     rbx, [rbp+238h]
0x1800280d3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800280d6  mov     rcx, cs:?s_isoCompCreatedEvent@DebugTargetManager@WebRuntimeDevTools@@0PEAXEA; hHandle
0x1800280dd  call    cs:__imp_WaitForSingleObject
0x1800280e3  test    eax, eax
0x1800280e5  jz      short loc_1800280FC
0x1800280e7  lea     r8, aOnecoreuapInet_2; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x1800280ee  mov     edx, 1ACh; void *
0x1800280f3  mov     rcx, rbx; this
0x1800280f6  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800280fc  mov     ebx, r15d
0x1800280ff  mov     rcx, cs:?s_isoCompCreatedEvent@DebugTargetManager@WebRuntimeDevTools@@0PEAXEA; hObject
0x180028106  call    cs:__imp_CloseHandle
0x18002810c  mov     cs:?s_isoCompCreatedEvent@DebugTargetManager@WebRuntimeDevTools@@0PEAXEA, r15; void * WebRuntimeDevTools::DebugTargetManager::s_isoCompCreatedEvent
0x180028113  mov     ecx, [rsp+330h+var_2E0]; unsigned int
0x180028117  mov     [rdi], ecx
0x180028119  mov     rdx, [rsp+330h+var_2C8]; void *
0x18002811e  mov     [rsi], rdx
0x180028121  call    ?AddIsoThreadHandle@LCIEDiagnosticsSession@WebRuntimeDiagnostics@@SAXKPEAX@Z; WebRuntimeDiagnostics::LCIEDiagnosticsSession::AddIsoThreadHandle(ulong,void *)
0x180028126  nop
0x180028127  lea     rcx, [rsp+330h+var_2D8]; this
0x18002812c  call    ??1_IsoWindowsContainer@@QEAA@XZ; _IsoWindowsContainer::~_IsoWindowsContainer(void)
0x180028131  mov     eax, ebx
0x180028133  mov     rcx, [rbp+230h+var_30]
0x18002813a  xor     rcx, rsp; StackCookie
0x18002813d  call    __security_check_cookie
0x180028142  mov     rbx, [rsp+330h+arg_0]
0x18002814a  add     rsp, 310h
0x180028151  pop     r15
0x180028153  pop     r14
0x180028155  pop     rdi
0x180028156  pop     rsi
0x180028157  pop     rbp
0x180028158  retn
```
