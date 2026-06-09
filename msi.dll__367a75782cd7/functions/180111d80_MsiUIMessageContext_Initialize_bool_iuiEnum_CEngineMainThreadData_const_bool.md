# MsiUIMessageContext::Initialize(bool,iuiEnum,CEngineMainThreadData const *,bool)

- ea: `0x180111d80`
- end: `0x1801122e6`
- name: `?Initialize@MsiUIMessageContext@@QEAAI_NW4iuiEnum@@PEBUCEngineMainThreadData@@_N@Z`
- size: `1382`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `24`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18009b280`
- `0x18016941c`
- `0x180174400`
- `0x1801744b8`
- `0x180193a84`
- `0x1801948c0`
- `0x180194a60`
- `0x1801a17b8`
- `0x1801c0b00`
- `0x1801c83dc`

## callees

- `0x18001de18`
- `0x18001e9f8`
- `0x180025688`
- `0x180025a18`
- `0x18003c7e0`
- `0x180061334`
- `0x18008f3e8`
- `0x18009d810`
- `0x18009e43c`
- `0x180111d80`
- `0x180112320`
- `0x1801123bc`
- `0x180112f24`
- `0x18012a5d8`
- `0x18012f1d0`
- `0x1801532b4`
- `0x180156e60`
- `0x18015701c`
- `0x1801c01f0`
- `0x1801c2d0c`
- `0x1802186c8`
- `0x18021896c`
- `0x180218d38`
- `0x18025c010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180111f91`
- `KERNEL32!InitializeCriticalSection` at `0x180111fc3`
- `KERNEL32!InitializeCriticalSection` at `0x180111f91`
- `KERNEL32!InitializeCriticalSection` at `0x180111fc3`
- `KERNEL32!GetCurrentThreadId` at `0x180112108`
- `KERNEL32!GetCurrentThreadId` at `0x18011216b`
- `KERNEL32!GetCurrentThreadId` at `0x180112108`
- `KERNEL32!GetCurrentThreadId` at `0x18011216b`
- `KERNEL32!CreateEventW` at `0x180111f5c`
- `KERNEL32!CreateEventW` at `0x180111f70`
- `KERNEL32!CreateEventW` at `0x180111f5c`
- `KERNEL32!CreateEventW` at `0x180111f70`
- `KERNEL32!CreateThread` at `0x180112138`
- `KERNEL32!CreateThread` at `0x180112138`

## string_xrefs

- `0x180111e76`: `Message context already initialized, returning ERROR_INSTALL_ALREADY_RUNNING`

## pseudocode

```c
__int64 __fastcall MsiUIMessageContext::Initialize(
        __int64 a1,
        char a2,
        int a3,
        const struct CEngineMainThreadData *a4,
        char a5)
{
  struct IMsiServices *Services; // r14
  CMsiSQMSession *v10; // rsi
  unsigned int (*v11)(void); // rax
  __int64 (*Proc)(void); // rax
  CMsiSQMSession *v13; // rax
  unsigned int v14; // eax
  unsigned int v15; // edx
  unsigned int v16; // ebp
  CMsiSQMSession *v18; // rcx
  unsigned int v19; // esi
  HANDLE EventW; // rax
  __int64 v21; // rax
  CMsiSQMSession *v22; // rcx
  unsigned int v23; // edx
  CMsiSQMSession *v24; // rcx
  DWORD *v25; // rdi
  CBasicUI *v26; // rcx
  HANDLE Thread; // rax
  int v28; // eax
  bool v29; // r8
  _BYTE v30[88]; // [rsp+60h] [rbp-58h] BYREF

  Services = LoadServices();
  if ( !Services )
    return 1631;
  v10 = 0;
  if ( (g_scServerContext & 0xFFFFFFFD) == 0 && dword_180306D60 )
  {
    v11 = (unsigned int (*)(void))qword_18030A850;
    if ( !qword_18030A850 )
    {
      Proc = _WinSqmGetProc("WinSqmIsOptedIn");
      if ( !Proc )
      {
        dword_180306D60 = 0;
        goto LABEL_14;
      }
      _InterlockedCompareExchange64(&qword_18030A850, (signed __int64)Proc, 0);
      v11 = (unsigned int (*)(void))qword_18030A850;
    }
    if ( v11() )
    {
      v13 = (CMsiSQMSession *)operator new(0x58u);
      if ( v13 )
        v10 = CMsiSQMSession::CMsiSQMSession(v13);
      if ( !g_scServerContext && v10 )
        CMsiSQMSession::RecordSecurityContext(v10);
    }
  }
LABEL_14:
  v14 = CMessageContextState::SetState((CMessageContextState *)(a1 + 160), 1);
  v16 = v14;
  if ( v14 )
  {
    if ( v14 == 1618 && g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"Message context already initialized, returning ERROR_INSTALL_ALREADY_RUNNING",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    if ( v10 )
    {
      if ( !g_scServerContext )
        CMsiSQMSession::RecordDWORD(v10, 0xE27u, v16);
      CMsiSQMSession::`scalar deleting destructor'(v10, v15);
    }
    FreeServices();
    return v16;
  }
  v18 = *(CMsiSQMSession **)(a1 + 240);
  v30[0] = a5;
  *(_QWORD *)(a1 + 216) = Services;
  if ( v18 )
    CMsiSQMSession::`scalar deleting destructor'(v18, v15);
  *(_QWORD *)(a1 + 240) = v10;
  g_iUITicksStep = 3;
  g_iUIWaitTick = 150;
  *(_BYTE *)(a1 + 305) = 0;
  *(_BYTE *)(a1 + 230) = 0;
  if ( !a5 )
  {
    *(_DWORD *)(a1 + 308) = 3;
    *(_BYTE *)(a1 + 313) = 0;
  }
  v19 = MsiUIMessageContext::SetUserToken((MsiUIMessageContext *)a1, 0);
  if ( v19 )
  {
LABEL_42:
    MsiUIMessageContext::Initialize_::_2_::CTerminate::_CTerminate(v30);
    return v19;
  }
  *(_QWORD *)(a1 + 72) = CreateEventW(0, 0, 0, 0);
  EventW = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(a1 + 88) = EventW;
  if ( !*(_QWORD *)(a1 + 72) || !EventW )
    goto LABEL_58;
  InitializeCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  g_cWaitTimeout = 20 * GetIntegerPolicyValue(v19 + 7);
  if ( g_scServerContext == 2 && !a5 )
  {
    InitializeCriticalSection(&CProductContextCache::g_csCacheCriticalSection);
    CAPITempBuffer<sProductContext,20>::Destroy(&CProductContextCache::g_rgProductContext);
    CProductContextCache::g_cProductCacheCount = 0;
    CProductContextCache::g_fInitialized = 1;
    if ( !qword_180309780 )
    {
      v21 = operator new(v19 + 32);
      if ( v21 )
      {
        *(_DWORD *)(v21 + 1) = 0;
        *(_WORD *)(v21 + 6) = 0;
        *(_QWORD *)(v21 + 8) = &MsiString::s_NullString;
        *(_QWORD *)(v21 + 16) = 5;
        *(_QWORD *)(v21 + 24) = 0;
        qword_180309780 = (CMsiSystemChange *)v21;
      }
      else
      {
        qword_180309780 = 0;
      }
    }
  }
  if ( !MsiUIMessageContext::InitializeLog((MsiUIMessageContext *)a1, 0, a4) )
  {
    v19 = 1622;
    if ( !g_scServerContext )
    {
      v22 = *(CMsiSQMSession **)(a1 + 240);
      if ( v22 )
      {
        CMsiSQMSession::RecordDWORD(v22, 0xE27u, 0x656u);
        v24 = *(CMsiSQMSession **)(a1 + 240);
        if ( v24 )
          CMsiSQMSession::`scalar deleting destructor'(v24, v23);
        *(_QWORD *)(a1 + 240) = 0;
      }
    }
    goto LABEL_42;
  }
  if ( !a5 )
  {
    if ( (a3 & 0x1000) != 0 )
    {
      *(_BYTE *)(a1 + 204) = 1;
      a3 &= ~0x1000u;
    }
    if ( (a3 & 0x4000) != 0 )
    {
      *(_BYTE *)(a1 + 313) = 1;
      a3 &= ~0x4000u;
    }
    if ( (a3 & 0x400) != 0 )
    {
      *(_BYTE *)(a1 + 226) = 1;
      a3 &= ~0x400u;
    }
    if ( (a3 & 0x8000) != 0 )
    {
      *(_BYTE *)(a1 + 225) = 1;
      a3 &= ~0x8000u;
    }
    if ( (a3 & 0x800) != 0 )
    {
      *(_BYTE *)(a1 + 224) = 1;
      a3 &= ~0x800u;
    }
    *(_DWORD *)(a1 + 188) = a3;
    v25 = (DWORD *)(a1 + 104);
    if ( a2 )
    {
      if ( GetTestFlag(84) )
      {
        *v25 = GetCurrentThreadId();
        *(_QWORD *)(a1 + 96) = -1;
        goto LABEL_69;
      }
      Thread = CreateThread(0, 0xA000u, MsiUIMessageContext::ChildUIThread, (LPVOID)a1, 0, (LPDWORD)(a1 + 104));
      *(_QWORD *)(a1 + 96) = Thread;
      if ( Thread )
      {
LABEL_69:
        if ( (dword_180309978 & 0x1000) == 0
          || !(unsigned int)CMsiAPIMessageRec::Message(g_messageRec, 201326592, &off_180305DB0) )
        {
          if ( (dword_1803097B8 & 0x1000) != 0 )
            CMsiAPIMessage::Message(g_message, 201326592, 0);
          if ( g_pEmbeddedUI && (*((_DWORD *)g_pEmbeddedUI + 272) & 0x1000) != 0 )
            CMsiEmbeddedUIManager::Message(v26, 201326592, &off_180305DB0);
        }
        *g_rgchScriptInProgress = 0;
        *g_rgchTimeRemaining = 0;
        *g_rgchFatalOutOfMemory = 0;
        *g_rgchFatalTimedOut = 0;
        *g_rgchFatalException = 0;
        *g_rgchBannerText = 0;
        goto LABEL_77;
      }
      goto LABEL_58;
    }
    *v25 = GetCurrentThreadId();
    v28 = *(_DWORD *)(a1 + 188);
    if ( v28 == 5 )
    {
      *(_DWORD *)(a1 + 188) = 0;
LABEL_66:
      if ( !*(_BYTE *)(a1 + 228) && (int)((__int64 (__fastcall *)(_QWORD))OLE32::CoInitialize)(0) >= 0 )
        *(_BYTE *)(a1 + 228) = 1;
      goto LABEL_69;
    }
    if ( v28 == 3 || (v29 = 0, v28 == 0x2000) )
      v29 = 1;
    if ( CBasicUI::Initialize(
           v26,
           qword_180309948,
           v29,
           *(_BYTE *)(a1 + 204),
           *(_BYTE *)(a1 + 313),
           *(_BYTE *)(a1 + 224),
           *(_BYTE *)(a1 + 225),
           *(_BYTE *)(a1 + 226)) )
    {
      goto LABEL_66;
    }
LABEL_58:
    MsiUIMessageContext::Initialize_::_2_::CTerminate::_CTerminate(v30);
    return 1631;
  }
LABEL_77:
  MsiUIMessageContext::FCreateHiddenWindow((MsiUIMessageContext *)a1);
  if ( *(_QWORD *)(a1 + 280) == -1 )
    *(_QWORD *)(a1 + 280) = 0;
  CAPITempBuffer<unsigned short,1>::SetSize(&g_rgchFatalOutOfMemory, 256, 0);
  *(_BYTE *)(a1 + 149) = 1;
  MsiUIMessageContext::Initialize_::_2_::CTerminate::_CTerminate(v30);
  return 0;
}

```

## disassembly

```asm
0x180111d80  push    rbx
0x180111d82  push    rbp
0x180111d83  push    rsi
0x180111d84  push    rdi
0x180111d85  push    r12
0x180111d87  push    r13
0x180111d89  push    r14
0x180111d8b  push    r15
0x180111d8d  sub     rsp, 78h
0x180111d91  mov     r15, r9
0x180111d94  mov     edi, r8d
0x180111d97  mov     r12b, dl
0x180111d9a  mov     rbx, rcx
0x180111d9d  call    ?LoadServices@@YAPEAVIMsiServices@@XZ; LoadServices(void)
0x180111da2  xor     r13d, r13d
0x180111da5  mov     r14, rax
0x180111da8  test    rax, rax
0x180111dab  jz      loc_180112155
0x180111db1  test    cs:?g_scServerContext@@3W4scEnum@@A, 0FFFFFFFDh; scEnum g_scServerContext
0x180111dbb  mov     esi, r13d
0x180111dbe  jnz     short loc_180111E3D
0x180111dc0  cmp     cs:dword_180306D60, r13d
0x180111dc7  jz      short loc_180111E3D
0x180111dc9  mov     rax, cs:qword_18030A850
0x180111dd0  test    rax, rax
0x180111dd3  jnz     short loc_180111E04
0x180111dd5  lea     rcx, aWinsqmisoptedi; "WinSqmIsOptedIn"
0x180111ddc  call    ?_WinSqmGetProc@@YAP6A_JXZPEBD@Z; _WinSqmGetProc(char const *)
0x180111de1  mov     rcx, rax
0x180111de4  test    rax, rax
0x180111de7  jnz     short loc_180111DF2
0x180111de9  mov     cs:dword_180306D60, r13d
0x180111df0  jmp     short loc_180111E3D
0x180111df2  xor     eax, eax
0x180111df4  lock cmpxchg cs:qword_18030A850, rcx
0x180111dfd  mov     rax, cs:qword_18030A850
0x180111e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180111e09  test    eax, eax
0x180111e0b  jz      short loc_180111E3D
0x180111e0d  mov     ecx, 58h ; 'X'; unsigned __int64
0x180111e12  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180111e17  test    rax, rax
0x180111e1a  jz      short loc_180111E27
0x180111e1c  mov     rcx, rax; this
0x180111e1f  call    ??0CMsiSQMSession@@QEAA@XZ; CMsiSQMSession::CMsiSQMSession(void)
0x180111e24  mov     rsi, rax
0x180111e27  cmp     cs:?g_scServerContext@@3W4scEnum@@A, r13d; scEnum g_scServerContext
0x180111e2e  jnz     short loc_180111E3D
0x180111e30  test    rsi, rsi
0x180111e33  jz      short loc_180111E3D
0x180111e35  mov     rcx, rsi; this
0x180111e38  call    ?RecordSecurityContext@CMsiSQMSession@@QEAAXXZ; CMsiSQMSession::RecordSecurityContext(void)
0x180111e3d  lea     rcx, [rbx+0A0h]; this
0x180111e44  mov     dl, 1; bool
0x180111e46  call    ?SetState@CMessageContextState@@QEAAI_N@Z; CMessageContextState::SetState(bool)
0x180111e4b  mov     ebp, eax
0x180111e4d  test    eax, eax
0x180111e4f  jz      loc_180111EDA
0x180111e55  cmp     eax, 652h
0x180111e5a  jnz     short loc_180111EA8
0x180111e5c  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x180111e63  jz      short loc_180111EA8
0x180111e65  mov     [rsp+0B8h+var_60], r13; void *
0x180111e6a  lea     rax, aNull; "(NULL)"
0x180111e71  mov     [rsp+0B8h+var_68], r13d; unsigned int
0x180111e76  lea     r9, aMessageContext; "Message context already initialized, re"...
0x180111e7d  mov     [rsp+0B8h+var_70], rax; unsigned __int16 *
0x180111e82  xor     edx, edx; unsigned __int16
0x180111e84  mov     [rsp+0B8h+var_78], rax; unsigned __int16 *
0x180111e89  xor     r8d, r8d; int
0x180111e8c  mov     [rsp+0B8h+var_80], rax; unsigned __int16 *
0x180111e91  mov     [rsp+0B8h+var_88], rax; unsigned __int16 *
0x180111e96  mov     [rsp+0B8h+lpThreadId], rax; unsigned __int16 *
0x180111e9b  lea     ecx, [rdx+9]; int
0x180111e9e  mov     qword ptr [rsp+0B8h+dwCreationFlags], rax; unsigned __int16 *
0x180111ea3  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180111ea8  test    rsi, rsi
0x180111eab  jz      short loc_180111ECE
0x180111ead  cmp     cs:?g_scServerContext@@3W4scEnum@@A, r13d; scEnum g_scServerContext
0x180111eb4  jnz     short loc_180111EC6
0x180111eb6  mov     r8d, ebp; unsigned int
0x180111eb9  mov     edx, 0E27h; unsigned int
0x180111ebe  mov     rcx, rsi; this
0x180111ec1  call    ?RecordDWORD@CMsiSQMSession@@QEAAXKK@Z; CMsiSQMSession::RecordDWORD(ulong,ulong)
0x180111ec6  mov     rcx, rsi; this
0x180111ec9  call    ??_GCMsiSQMSession@@QEAAPEAXI@Z; CMsiSQMSession::`scalar deleting destructor'(uint)
0x180111ece  call    ?FreeServices@@YAHXZ; FreeServices(void)
0x180111ed3  mov     eax, ebp
0x180111ed5  jmp     loc_18011215A
0x180111eda  mov     rcx, [rbx+0F0h]; this
0x180111ee1  mov     bpl, [rsp+0B8h+arg_20]
0x180111ee9  mov     [rsp+0B8h+var_58], bpl
0x180111eee  mov     [rbx+0D8h], r14
0x180111ef5  test    rcx, rcx
0x180111ef8  jz      short loc_180111EFF
0x180111efa  call    ??_GCMsiSQMSession@@QEAAPEAXI@Z; CMsiSQMSession::`scalar deleting destructor'(uint)
0x180111eff  mov     [rbx+0F0h], rsi
0x180111f06  mov     r14d, 3
0x180111f0c  mov     cs:?g_iUITicksStep@@3HA, r14d; int g_iUITicksStep
0x180111f13  mov     cs:?g_iUIWaitTick@@3HA, 96h; int g_iUIWaitTick
0x180111f1d  mov     [rbx+131h], r13b
0x180111f24  mov     [rbx+0E6h], r13b
0x180111f2b  test    bpl, bpl
0x180111f2e  jnz     short loc_180111F3E
0x180111f30  mov     [rbx+134h], r14d
0x180111f37  mov     [rbx+139h], r13b
0x180111f3e  xor     edx, edx; bool
0x180111f40  mov     rcx, rbx; this
0x180111f43  call    ?SetUserToken@MsiUIMessageContext@@QEAAI_N@Z; MsiUIMessageContext::SetUserToken(bool)
0x180111f48  mov     esi, eax
0x180111f4a  test    eax, eax
0x180111f4c  jnz     loc_180112079
0x180111f52  xor     r9d, r9d; lpName
0x180111f55  xor     r8d, r8d; bInitialState
0x180111f58  xor     edx, edx; bManualReset
0x180111f5a  xor     ecx, ecx; lpEventAttributes
0x180111f5c  call    cs:__imp_CreateEventW
0x180111f62  xor     r9d, r9d; lpName
0x180111f65  xor     r8d, r8d; bInitialState
0x180111f68  xor     edx, edx; bManualReset
0x180111f6a  mov     [rbx+48h], rax
0x180111f6e  xor     ecx, ecx; lpEventAttributes
0x180111f70  call    cs:__imp_CreateEventW
0x180111f76  mov     [rbx+58h], rax
0x180111f7a  cmp     [rbx+48h], r13
0x180111f7e  jz      loc_18011214B
0x180111f84  test    rax, rax
0x180111f87  jz      loc_18011214B
0x180111f8d  lea     rcx, [rbx+10h]; lpCriticalSection
0x180111f91  call    cs:__imp_InitializeCriticalSection
0x180111f97  lea     edx, [rsi+1]
0x180111f9a  lea     ecx, [rsi+7]
0x180111f9d  call    ?GetIntegerPolicyValue@@YAIW4iePolicyIndex@@W4Bool@@PEAW42@@Z; GetIntegerPolicyValue(iePolicyIndex,Bool,Bool *)
0x180111fa2  lea     ecx, [rax+rax*4]
0x180111fa5  shl     ecx, 2
0x180111fa8  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x180111faf  mov     cs:?g_cWaitTimeout@@3HA, ecx; int g_cWaitTimeout
0x180111fb5  jnz     short loc_180112029
0x180111fb7  test    bpl, bpl
0x180111fba  jnz     short loc_180112029
0x180111fbc  lea     rcx, ?g_csCacheCriticalSection@CProductContextCache@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180111fc3  call    cs:__imp_InitializeCriticalSection
0x180111fc9  lea     rcx, ?g_rgProductContext@CProductContextCache@@2V?$CAPITempBuffer@UsProductContext@@$0BE@@@A; CAPITempBuffer<sProductContext,20> CProductContextCache::g_rgProductContext
0x180111fd0  call    ?Destroy@?$CAPITempBuffer@UsProductContext@@$0BE@@@QEAAXXZ; CAPITempBuffer<sProductContext,20>::Destroy(void)
0x180111fd5  cmp     cs:qword_180309780, r13
0x180111fdc  mov     cs:?g_cProductCacheCount@CProductContextCache@@2HA, r13d; int CProductContextCache::g_cProductCacheCount
0x180111fe3  mov     cs:?g_fInitialized@CProductContextCache@@2_NA, 1; bool CProductContextCache::g_fInitialized
0x180111fea  jnz     short loc_180112029
0x180111fec  lea     ecx, [rsi+20h]; unsigned __int64
0x180111fef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180111ff4  test    rax, rax
0x180111ff7  jz      short loc_180112022
0x180111ff9  mov     [rax+1], r13d
0x180111ffd  lea     rcx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180112004  mov     [rax+6], r13w
0x180112009  mov     [rax+8], rcx
0x18011200d  mov     qword ptr [rax+10h], 5
0x180112015  mov     [rax+18h], r13
0x180112019  mov     cs:qword_180309780, rax
0x180112020  jmp     short loc_180112029
0x180112022  mov     cs:qword_180309780, r13
0x180112029  mov     r8, r15; struct CEngineMainThreadData *
0x18011202c  xor     edx, edx; bool
0x18011202e  mov     rcx, rbx; this
0x180112031  call    ?InitializeLog@MsiUIMessageContext@@AEAA_N_NPEBUCEngineMainThreadData@@@Z; MsiUIMessageContext::InitializeLog(bool,CEngineMainThreadData const *)
0x180112036  test    al, al
0x180112038  jnz     short loc_18011208A
0x18011203a  cmp     cs:?g_scServerContext@@3W4scEnum@@A, r13d; scEnum g_scServerContext
0x180112041  mov     esi, 656h
0x180112046  jnz     short loc_180112079
0x180112048  mov     rcx, [rbx+0F0h]; this
0x18011204f  test    rcx, rcx
0x180112052  jz      short loc_180112079
0x180112054  mov     r8d, esi; unsigned int
0x180112057  mov     edx, 0E27h; unsigned int
0x18011205c  call    ?RecordDWORD@CMsiSQMSession@@QEAAXKK@Z; CMsiSQMSession::RecordDWORD(ulong,ulong)
0x180112061  mov     rcx, [rbx+0F0h]; this
0x180112068  test    rcx, rcx
0x18011206b  jz      short loc_180112072
0x18011206d  call    ??_GCMsiSQMSession@@QEAAPEAXI@Z; CMsiSQMSession::`scalar deleting destructor'(uint)
0x180112072  mov     [rbx+0F0h], r13
0x180112079  lea     rcx, [rsp+0B8h+var_58]
0x18011207e  call    _MsiUIMessageContext__Initialize____2___CTerminate___CTerminate
0x180112083  mov     eax, esi
0x180112085  jmp     loc_18011215A
0x18011208a  test    bpl, bpl
0x18011208d  jnz     loc_1801122A1
0x180112093  mov     esi, 1000h
0x180112098  test    esi, edi
0x18011209a  jz      short loc_1801120A7
0x18011209c  mov     byte ptr [rbx+0CCh], 1
0x1801120a3  btr     edi, 0Ch
0x1801120a7  bt      edi, 0Eh
0x1801120ab  jnb     short loc_1801120B8
0x1801120ad  mov     byte ptr [rbx+139h], 1
0x1801120b4  btr     edi, 0Eh
0x1801120b8  bt      edi, 0Ah
0x1801120bc  jnb     short loc_1801120C9
0x1801120be  mov     byte ptr [rbx+0E2h], 1
0x1801120c5  btr     edi, 0Ah
0x1801120c9  bt      edi, 0Fh
0x1801120cd  jnb     short loc_1801120DA
0x1801120cf  mov     byte ptr [rbx+0E1h], 1
0x1801120d6  btr     edi, 0Fh
0x1801120da  bt      edi, 0Bh
0x1801120de  jnb     short loc_1801120EB
0x1801120e0  mov     byte ptr [rbx+0E0h], 1
0x1801120e7  btr     edi, 0Bh
0x1801120eb  mov     [rbx+0BCh], edi
0x1801120f1  lea     rdi, [rbx+68h]
0x1801120f5  test    r12b, r12b
0x1801120f8  jz      short loc_18011216B
0x1801120fa  mov     ecx, 54h ; 'T'; int
0x1801120ff  call    ?GetTestFlag@@YA_NH@Z; GetTestFlag(int)
0x180112104  test    al, al
0x180112106  jz      short loc_18011211D
0x180112108  call    cs:__imp_GetCurrentThreadId
0x18011210e  mov     [rdi], eax
0x180112110  mov     qword ptr [rbx+60h], 0FFFFFFFFFFFFFFFFh
0x180112118  jmp     loc_1801121FE
0x18011211d  mov     [rsp+0B8h+lpThreadId], rdi; lpThreadId
0x180112122  lea     r8, ?ChildUIThread@MsiUIMessageContext@@CAKPEAU1@@Z; lpStartAddress
0x180112129  mov     r9, rbx; lpParameter
0x18011212c  mov     [rsp+0B8h+dwCreationFlags], r13d; dwCreationFlags
0x180112131  mov     edx, 0A000h; dwStackSize
0x180112136  xor     ecx, ecx; lpThreadAttributes
0x180112138  call    cs:__imp_CreateThread
0x18011213e  mov     [rbx+60h], rax
0x180112142  test    rax, rax
0x180112145  jnz     loc_1801121FE
0x18011214b  lea     rcx, [rsp+0B8h+var_58]
0x180112150  call    _MsiUIMessageContext__Initialize____2___CTerminate___CTerminate
0x180112155  mov     eax, 65Fh
0x18011215a  add     rsp, 78h
0x18011215e  pop     r15
0x180112160  pop     r14
0x180112162  pop     r13
0x180112164  pop     r12
0x180112166  pop     rdi
0x180112167  pop     rsi
0x180112168  pop     rbp
0x180112169  pop     rbx
0x18011216a  retn
0x18011216b  call    cs:__imp_GetCurrentThreadId
0x180112171  mov     [rdi], eax
0x180112173  mov     eax, [rbx+0BCh]
0x180112179  cmp     eax, 5
0x18011217c  jnz     short loc_180112187
0x18011217e  mov     [rbx+0BCh], r13d
0x180112185  jmp     short loc_1801121DC
0x180112187  cmp     eax, r14d
0x18011218a  jz      short loc_180112196
0x18011218c  mov     r8b, r13b
0x18011218f  cmp     eax, 2000h
0x180112194  jnz     short loc_180112199
0x180112196  mov     r8b, 1; bool
0x180112199  mov     al, [rbx+0E2h]
0x18011219f  mov     r9b, [rbx+0CCh]; bool
0x1801121a6  mov     rdx, cs:qword_180309948; HWND
0x1801121ad  mov     byte ptr [rsp+0B8h+var_80], al; bool
0x1801121b1  mov     al, [rbx+0E1h]
0x1801121b7  mov     byte ptr [rsp+0B8h+var_88], al; bool
0x1801121bb  mov     al, [rbx+0E0h]
0x1801121c1  mov     byte ptr [rsp+0B8h+lpThreadId], al; bool
0x1801121c5  mov     al, [rbx+139h]
0x1801121cb  mov     byte ptr [rsp+0B8h+dwCreationFlags], al; bool
0x1801121cf  call    ?Initialize@CBasicUI@@QEAA_NPEAUHWND__@@_N11111@Z; CBasicUI::Initialize(HWND__ *,bool,bool,bool,bool,bool,bool)
0x1801121d4  test    al, al
0x1801121d6  jz      loc_18011214B
0x1801121dc  cmp     [rbx+0E4h], r13b
0x1801121e3  jnz     short loc_1801121FE
0x1801121e5  mov     rax, cs:?CoInitialize@OLE32@@3P6AJPEAX@ZEA; long (*OLE32::CoInitialize)(void *)
0x1801121ec  xor     ecx, ecx
0x1801121ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801121f3  test    eax, eax
0x1801121f5  js      short loc_1801121FE
0x1801121f7  mov     byte ptr [rbx+0E4h], 1
0x1801121fe  test    cs:dword_180309978, esi
0x180112204  mov     edi, 0C000000h
0x180112209  jz      short loc_180112224
0x18011220b  lea     r8, off_180305DB0
0x180112212  mov     edx, edi
0x180112214  lea     rcx, ?g_messageRec@@3VCMsiAPIMessageRec@@A; CMsiAPIMessageRec g_messageRec
0x18011221b  call    ?Message@CMsiAPIMessageRec@@QEBA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiAPIMessageRec::Message(imtEnum,IMsiRecord &)
0x180112220  test    eax, eax
0x180112222  jnz     short loc_18011225F
0x180112224  test    cs:dword_1803097B8, esi
0x18011222a  jz      short loc_18011223D
0x18011222c  xor     r8d, r8d
0x18011222f  lea     rcx, ?g_message@@3VCMsiAPIMessage@@A; CMsiAPIMessage g_message
0x180112236  mov     edx, edi
0x180112238  call    ?Message@CMsiAPIMessage@@QEBA?AW4imsEnum@@W4imtEnum@@PEBG@Z; CMsiAPIMessage::Message(imtEnum,ushort const *)
0x18011223d  mov     rax, cs:?g_pEmbeddedUI@@3PEAVCMsiEmbeddedUIManager@@EA; CMsiEmbeddedUIManager * g_pEmbeddedUI
0x180112244  test    rax, rax
0x180112247  jz      short loc_18011225F
0x180112249  test    [rax+440h], esi
0x18011224f  jz      short loc_18011225F
0x180112251  lea     r8, off_180305DB0
0x180112258  mov     edx, edi
0x18011225a  call    ?Message@CMsiEmbeddedUIManager@@QEAA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiEmbeddedUIManager::Message(imtEnum,IMsiRecord &)
  ... truncated ...
```
