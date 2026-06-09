# MsiUIMessageContext::Initialize(bool,iuiEnum,CEngineMainThreadData const *,bool)

- ea: `0x18004d644`
- end: `0x18004dbd5`
- name: `?Initialize@MsiUIMessageContext@@QEAAI_NW4iuiEnum@@PEBUCEngineMainThreadData@@_N@Z`
- size: `1425`
- prototype: ``
- caller_count: `10`
- callee_count: `24`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180009268`
- `0x18016f43c`
- `0x18017a750`
- `0x18017a810`
- `0x18019a634`
- `0x18019b520`
- `0x18019b6c0`
- `0x1801a87d8`
- `0x1801c9070`
- `0x1801d0c00`

## callees

- `0x18000b8bc`
- `0x18000c4bc`
- `0x18000ca3c`
- `0x18000d6d8`
- `0x180014288`
- `0x180018ee0`
- `0x1800200a4`
- `0x18004d644`
- `0x18004dc10`
- `0x18004dcac`
- `0x18004e85c`
- `0x180086264`
- `0x180092314`
- `0x1800b988c`
- `0x18012f908`
- `0x180158c04`
- `0x18015c964`
- `0x18015cb2c`
- `0x1801c86ac`
- `0x1801cb3d8`
- `0x1802222a4`
- `0x18022255c`
- `0x180222928`
- `0x180266010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18004d861`
- `KERNEL32!InitializeCriticalSection` at `0x18004d899`
- `KERNEL32!InitializeCriticalSection` at `0x18004d861`
- `KERNEL32!InitializeCriticalSection` at `0x18004d899`
- `KERNEL32!GetCurrentThreadId` at `0x18004d9e4`
- `KERNEL32!GetCurrentThreadId` at `0x18004da54`
- `KERNEL32!GetCurrentThreadId` at `0x18004d9e4`
- `KERNEL32!GetCurrentThreadId` at `0x18004da54`
- `KERNEL32!CreateEventW` at `0x18004d820`
- `KERNEL32!CreateEventW` at `0x18004d83a`
- `KERNEL32!CreateEventW` at `0x18004d820`
- `KERNEL32!CreateEventW` at `0x18004d83a`
- `KERNEL32!CreateThread` at `0x18004da1a`
- `KERNEL32!CreateThread` at `0x18004da1a`

## string_xrefs

- `0x18004d73a`: `Message context already initialized, returning ERROR_INSTALL_ALREADY_RUNNING`

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
  __int64 v21; // r8
  char *v22; // rax
  CMsiSQMSession *v23; // rcx
  unsigned int v24; // edx
  CMsiSQMSession *v25; // rcx
  DWORD *v26; // rdi
  CBasicUI *v27; // rcx
  HANDLE Thread; // rax
  int v29; // eax
  bool v30; // r8
  _BYTE v31[88]; // [rsp+60h] [rbp-58h] BYREF

  Services = LoadServices();
  if ( !Services )
    return 1631;
  v10 = 0;
  if ( (g_scServerContext & 0xFFFFFFFD) == 0 && dword_180310D20 )
  {
    v11 = (unsigned int (*)(void))qword_180314820;
    if ( !qword_180314820 )
    {
      Proc = _WinSqmGetProc("WinSqmIsOptedIn");
      if ( !Proc )
      {
        dword_180310D20 = 0;
        goto LABEL_14;
      }
      _InterlockedCompareExchange64(&qword_180314820, (signed __int64)Proc, 0);
      v11 = (unsigned int (*)(void))qword_180314820;
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
  v31[0] = a5;
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
    MsiUIMessageContext::Initialize_::_2_::CTerminate::_CTerminate(v31);
    return v19;
  }
  *(_QWORD *)(a1 + 72) = CreateEventW(0, 0, 0, 0);
  EventW = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(a1 + 88) = EventW;
  if ( !*(_QWORD *)(a1 + 72) || !EventW )
    goto LABEL_58;
  InitializeCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  g_cWaitTimeout = 20 * GetIntegerPolicyValue(v19 + 7, v19 + 1, v21);
  if ( g_scServerContext == 2 && !a5 )
  {
    InitializeCriticalSection(&CProductContextCache::g_csCacheCriticalSection);
    CAPITempBuffer<sProductContext,20>::Destroy(&CProductContextCache::g_rgProductContext);
    CProductContextCache::g_cProductCacheCount = 0;
    CProductContextCache::g_fInitialized = 1;
    if ( !qword_180313730 )
    {
      v22 = (char *)operator new(v19 + 32);
      if ( v22 )
      {
        *(_DWORD *)(v22 + 1) = 0;
        *((_WORD *)v22 + 3) = 0;
        *((_QWORD *)v22 + 1) = &MsiString::s_NullString;
        *((_QWORD *)v22 + 2) = 5;
        *((_QWORD *)v22 + 3) = 0;
        qword_180313730 = (CMsiSystemChange *)v22;
      }
      else
      {
        qword_180313730 = 0;
      }
    }
  }
  if ( !MsiUIMessageContext::InitializeLog((MsiUIMessageContext *)a1, 0, a4) )
  {
    v19 = 1622;
    if ( !g_scServerContext )
    {
      v23 = *(CMsiSQMSession **)(a1 + 240);
      if ( v23 )
      {
        CMsiSQMSession::RecordDWORD(v23, 0xE27u, 0x656u);
        v25 = *(CMsiSQMSession **)(a1 + 240);
        if ( v25 )
          CMsiSQMSession::`scalar deleting destructor'(v25, v24);
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
    v26 = (DWORD *)(a1 + 104);
    if ( a2 )
    {
      if ( GetTestFlag(84) )
      {
        *v26 = GetCurrentThreadId();
        *(_QWORD *)(a1 + 96) = -1;
        goto LABEL_69;
      }
      Thread = CreateThread(0, 0xA000u, MsiUIMessageContext::ChildUIThread, (LPVOID)a1, 0, (LPDWORD)(a1 + 104));
      *(_QWORD *)(a1 + 96) = Thread;
      if ( Thread )
      {
LABEL_69:
        if ( (dword_180313928 & 0x1000) == 0
          || !(unsigned int)CMsiAPIMessageRec::Message(g_messageRec, 201326592, &off_18030FDB0) )
        {
          if ( (dword_180313768 & 0x1000) != 0 )
            CMsiAPIMessage::Message(g_message, 201326592, 0);
          if ( g_pEmbeddedUI && (*((_DWORD *)g_pEmbeddedUI + 272) & 0x1000) != 0 )
            CMsiEmbeddedUIManager::Message(v27, 201326592, &off_18030FDB0);
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
    *v26 = GetCurrentThreadId();
    v29 = *(_DWORD *)(a1 + 188);
    if ( v29 == 5 )
    {
      *(_DWORD *)(a1 + 188) = 0;
LABEL_66:
      if ( !*(_BYTE *)(a1 + 228) && (int)((__int64 (__fastcall *)(_QWORD))OLE32::CoInitialize)(0) >= 0 )
        *(_BYTE *)(a1 + 228) = 1;
      goto LABEL_69;
    }
    if ( v29 == 3 || (v30 = 0, v29 == 0x2000) )
      v30 = 1;
    if ( CBasicUI::Initialize(
           v27,
           qword_1803138F8,
           v30,
           *(_BYTE *)(a1 + 204),
           *(_BYTE *)(a1 + 313),
           *(_BYTE *)(a1 + 224),
           *(_BYTE *)(a1 + 225),
           *(_BYTE *)(a1 + 226)) )
    {
      goto LABEL_66;
    }
LABEL_58:
    MsiUIMessageContext::Initialize_::_2_::CTerminate::_CTerminate(v31);
    return 1631;
  }
LABEL_77:
  MsiUIMessageContext::FCreateHiddenWindow((MsiUIMessageContext *)a1);
  if ( *(_QWORD *)(a1 + 280) == -1 )
    *(_QWORD *)(a1 + 280) = 0;
  CAPITempBuffer<unsigned short,1>::SetSize(&g_rgchFatalOutOfMemory, 256, 0);
  *(_BYTE *)(a1 + 149) = 1;
  MsiUIMessageContext::Initialize_::_2_::CTerminate::_CTerminate(v31);
  return 0;
}

```

## disassembly

```asm
0x18004d644  push    rbx
0x18004d646  push    rbp
0x18004d647  push    rsi
0x18004d648  push    rdi
0x18004d649  push    r12
0x18004d64b  push    r13
0x18004d64d  push    r14
0x18004d64f  push    r15
0x18004d651  sub     rsp, 78h
0x18004d655  mov     r15, r9
0x18004d658  mov     edi, r8d
0x18004d65b  mov     r12b, dl
0x18004d65e  mov     rbx, rcx
0x18004d661  call    ?LoadServices@@YAPEAVIMsiServices@@XZ; LoadServices(void)
0x18004d666  xor     r13d, r13d
0x18004d669  mov     r14, rax
0x18004d66c  test    rax, rax
0x18004d66f  jz      loc_18004DA3D
0x18004d675  test    cs:?g_scServerContext@@3W4scEnum@@A, 0FFFFFFFDh; scEnum g_scServerContext
0x18004d67f  mov     esi, r13d
0x18004d682  jnz     short loc_18004D701
0x18004d684  cmp     cs:dword_180310D20, r13d
0x18004d68b  jz      short loc_18004D701
0x18004d68d  mov     rax, cs:qword_180314820
0x18004d694  test    rax, rax
0x18004d697  jnz     short loc_18004D6C8
0x18004d699  lea     rcx, aWinsqmisoptedi; "WinSqmIsOptedIn"
0x18004d6a0  call    ?_WinSqmGetProc@@YAP6A_JXZPEBD@Z; _WinSqmGetProc(char const *)
0x18004d6a5  mov     rcx, rax
0x18004d6a8  test    rax, rax
0x18004d6ab  jnz     short loc_18004D6B6
0x18004d6ad  mov     cs:dword_180310D20, r13d
0x18004d6b4  jmp     short loc_18004D701
0x18004d6b6  xor     eax, eax
0x18004d6b8  lock cmpxchg cs:qword_180314820, rcx
0x18004d6c1  mov     rax, cs:qword_180314820
0x18004d6c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d6cd  test    eax, eax
0x18004d6cf  jz      short loc_18004D701
0x18004d6d1  mov     ecx, 58h ; 'X'; unsigned __int64
0x18004d6d6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004d6db  test    rax, rax
0x18004d6de  jz      short loc_18004D6EB
0x18004d6e0  mov     rcx, rax; this
0x18004d6e3  call    ??0CMsiSQMSession@@QEAA@XZ; CMsiSQMSession::CMsiSQMSession(void)
0x18004d6e8  mov     rsi, rax
0x18004d6eb  cmp     cs:?g_scServerContext@@3W4scEnum@@A, r13d; scEnum g_scServerContext
0x18004d6f2  jnz     short loc_18004D701
0x18004d6f4  test    rsi, rsi
0x18004d6f7  jz      short loc_18004D701
0x18004d6f9  mov     rcx, rsi; this
0x18004d6fc  call    ?RecordSecurityContext@CMsiSQMSession@@QEAAXXZ; CMsiSQMSession::RecordSecurityContext(void)
0x18004d701  lea     rcx, [rbx+0A0h]; this
0x18004d708  mov     dl, 1; bool
0x18004d70a  call    ?SetState@CMessageContextState@@QEAAI_N@Z; CMessageContextState::SetState(bool)
0x18004d70f  mov     ebp, eax
0x18004d711  test    eax, eax
0x18004d713  jz      loc_18004D79E
0x18004d719  cmp     eax, 652h
0x18004d71e  jnz     short loc_18004D76C
0x18004d720  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x18004d727  jz      short loc_18004D76C
0x18004d729  mov     [rsp+0B8h+var_60], r13; void *
0x18004d72e  lea     rax, aNull; "(NULL)"
0x18004d735  mov     [rsp+0B8h+var_68], r13d; unsigned int
0x18004d73a  lea     r9, aMessageContext; "Message context already initialized, re"...
0x18004d741  mov     [rsp+0B8h+var_70], rax; unsigned __int16 *
0x18004d746  xor     edx, edx; unsigned __int16
0x18004d748  mov     [rsp+0B8h+var_78], rax; unsigned __int16 *
0x18004d74d  xor     r8d, r8d; int
0x18004d750  mov     [rsp+0B8h+var_80], rax; unsigned __int16 *
0x18004d755  mov     [rsp+0B8h+var_88], rax; unsigned __int16 *
0x18004d75a  mov     [rsp+0B8h+lpThreadId], rax; unsigned __int16 *
0x18004d75f  lea     ecx, [rdx+9]; int
0x18004d762  mov     qword ptr [rsp+0B8h+dwCreationFlags], rax; unsigned __int16 *
0x18004d767  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18004d76c  test    rsi, rsi
0x18004d76f  jz      short loc_18004D792
0x18004d771  cmp     cs:?g_scServerContext@@3W4scEnum@@A, r13d; scEnum g_scServerContext
0x18004d778  jnz     short loc_18004D78A
0x18004d77a  mov     r8d, ebp; unsigned int
0x18004d77d  mov     edx, 0E27h; unsigned int
0x18004d782  mov     rcx, rsi; this
0x18004d785  call    ?RecordDWORD@CMsiSQMSession@@QEAAXKK@Z; CMsiSQMSession::RecordDWORD(ulong,ulong)
0x18004d78a  mov     rcx, rsi; this
0x18004d78d  call    ??_GCMsiSQMSession@@QEAAPEAXI@Z; CMsiSQMSession::`scalar deleting destructor'(uint)
0x18004d792  call    ?FreeServices@@YAHXZ; FreeServices(void)
0x18004d797  mov     eax, ebp
0x18004d799  jmp     loc_18004DA42
0x18004d79e  mov     rcx, [rbx+0F0h]; this
0x18004d7a5  mov     bpl, [rsp+0B8h+arg_20]
0x18004d7ad  mov     [rsp+0B8h+var_58], bpl
0x18004d7b2  mov     [rbx+0D8h], r14
0x18004d7b9  test    rcx, rcx
0x18004d7bc  jz      short loc_18004D7C3
0x18004d7be  call    ??_GCMsiSQMSession@@QEAAPEAXI@Z; CMsiSQMSession::`scalar deleting destructor'(uint)
0x18004d7c3  mov     [rbx+0F0h], rsi
0x18004d7ca  mov     r14d, 3
0x18004d7d0  mov     cs:?g_iUITicksStep@@3HA, r14d; int g_iUITicksStep
0x18004d7d7  mov     cs:?g_iUIWaitTick@@3HA, 96h; int g_iUIWaitTick
0x18004d7e1  mov     [rbx+131h], r13b
0x18004d7e8  mov     [rbx+0E6h], r13b
0x18004d7ef  test    bpl, bpl
0x18004d7f2  jnz     short loc_18004D802
0x18004d7f4  mov     [rbx+134h], r14d
0x18004d7fb  mov     [rbx+139h], r13b
0x18004d802  xor     edx, edx; bool
0x18004d804  mov     rcx, rbx; this
0x18004d807  call    ?SetUserToken@MsiUIMessageContext@@QEAAI_N@Z; MsiUIMessageContext::SetUserToken(bool)
0x18004d80c  mov     esi, eax
0x18004d80e  test    eax, eax
0x18004d810  jnz     loc_18004D955
0x18004d816  xor     r9d, r9d; lpName
0x18004d819  xor     r8d, r8d; bInitialState
0x18004d81c  xor     edx, edx; bManualReset
0x18004d81e  xor     ecx, ecx; lpEventAttributes
0x18004d820  call    cs:__imp_CreateEventW
0x18004d827  nop     dword ptr [rax+rax+00h]
0x18004d82c  xor     r9d, r9d; lpName
0x18004d82f  xor     r8d, r8d; bInitialState
0x18004d832  xor     edx, edx; bManualReset
0x18004d834  mov     [rbx+48h], rax
0x18004d838  xor     ecx, ecx; lpEventAttributes
0x18004d83a  call    cs:__imp_CreateEventW
0x18004d841  nop     dword ptr [rax+rax+00h]
0x18004d846  mov     [rbx+58h], rax
0x18004d84a  cmp     [rbx+48h], r13
0x18004d84e  jz      loc_18004DA33
0x18004d854  test    rax, rax
0x18004d857  jz      loc_18004DA33
0x18004d85d  lea     rcx, [rbx+10h]; lpCriticalSection
0x18004d861  call    cs:__imp_InitializeCriticalSection
0x18004d868  nop     dword ptr [rax+rax+00h]
0x18004d86d  lea     edx, [rsi+1]
0x18004d870  lea     ecx, [rsi+7]
0x18004d873  call    ?GetIntegerPolicyValue@@YAIW4iePolicyIndex@@W4Bool@@PEAW42@@Z; GetIntegerPolicyValue(iePolicyIndex,Bool,Bool *)
0x18004d878  lea     ecx, [rax+rax*4]
0x18004d87b  shl     ecx, 2
0x18004d87e  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x18004d885  mov     cs:?g_cWaitTimeout@@3HA, ecx; int g_cWaitTimeout
0x18004d88b  jnz     short loc_18004D905
0x18004d88d  test    bpl, bpl
0x18004d890  jnz     short loc_18004D905
0x18004d892  lea     rcx, ?g_csCacheCriticalSection@CProductContextCache@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004d899  call    cs:__imp_InitializeCriticalSection
0x18004d8a0  nop     dword ptr [rax+rax+00h]
0x18004d8a5  lea     rcx, ?g_rgProductContext@CProductContextCache@@2V?$CAPITempBuffer@UsProductContext@@$0BE@@@A; CAPITempBuffer<sProductContext,20> CProductContextCache::g_rgProductContext
0x18004d8ac  call    ?Destroy@?$CAPITempBuffer@UsProductContext@@$0BE@@@QEAAXXZ; CAPITempBuffer<sProductContext,20>::Destroy(void)
0x18004d8b1  cmp     cs:qword_180313730, r13
0x18004d8b8  mov     cs:?g_cProductCacheCount@CProductContextCache@@2HA, r13d; int CProductContextCache::g_cProductCacheCount
0x18004d8bf  mov     cs:?g_fInitialized@CProductContextCache@@2_NA, 1; bool CProductContextCache::g_fInitialized
0x18004d8c6  jnz     short loc_18004D905
0x18004d8c8  lea     ecx, [rsi+20h]; unsigned __int64
0x18004d8cb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004d8d0  test    rax, rax
0x18004d8d3  jz      short loc_18004D8FE
0x18004d8d5  mov     [rax+1], r13d
0x18004d8d9  lea     rcx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18004d8e0  mov     [rax+6], r13w
0x18004d8e5  mov     [rax+8], rcx
0x18004d8e9  mov     qword ptr [rax+10h], 5
0x18004d8f1  mov     [rax+18h], r13
0x18004d8f5  mov     cs:qword_180313730, rax
0x18004d8fc  jmp     short loc_18004D905
0x18004d8fe  mov     cs:qword_180313730, r13
0x18004d905  mov     r8, r15; struct CEngineMainThreadData *
0x18004d908  xor     edx, edx; bool
0x18004d90a  mov     rcx, rbx; this
0x18004d90d  call    ?InitializeLog@MsiUIMessageContext@@AEAA_N_NPEBUCEngineMainThreadData@@@Z; MsiUIMessageContext::InitializeLog(bool,CEngineMainThreadData const *)
0x18004d912  test    al, al
0x18004d914  jnz     short loc_18004D966
0x18004d916  cmp     cs:?g_scServerContext@@3W4scEnum@@A, r13d; scEnum g_scServerContext
0x18004d91d  mov     esi, 656h
0x18004d922  jnz     short loc_18004D955
0x18004d924  mov     rcx, [rbx+0F0h]; this
0x18004d92b  test    rcx, rcx
0x18004d92e  jz      short loc_18004D955
0x18004d930  mov     r8d, esi; unsigned int
0x18004d933  mov     edx, 0E27h; unsigned int
0x18004d938  call    ?RecordDWORD@CMsiSQMSession@@QEAAXKK@Z; CMsiSQMSession::RecordDWORD(ulong,ulong)
0x18004d93d  mov     rcx, [rbx+0F0h]; this
0x18004d944  test    rcx, rcx
0x18004d947  jz      short loc_18004D94E
0x18004d949  call    ??_GCMsiSQMSession@@QEAAPEAXI@Z; CMsiSQMSession::`scalar deleting destructor'(uint)
0x18004d94e  mov     [rbx+0F0h], r13
0x18004d955  lea     rcx, [rsp+0B8h+var_58]
0x18004d95a  call    _MsiUIMessageContext__Initialize____2___CTerminate___CTerminate
0x18004d95f  mov     eax, esi
0x18004d961  jmp     loc_18004DA42
0x18004d966  test    bpl, bpl
0x18004d969  jnz     loc_18004DB90
0x18004d96f  mov     esi, 1000h
0x18004d974  test    esi, edi
0x18004d976  jz      short loc_18004D983
0x18004d978  mov     byte ptr [rbx+0CCh], 1
0x18004d97f  btr     edi, 0Ch
0x18004d983  bt      edi, 0Eh
0x18004d987  jnb     short loc_18004D994
0x18004d989  mov     byte ptr [rbx+139h], 1
0x18004d990  btr     edi, 0Eh
0x18004d994  bt      edi, 0Ah
0x18004d998  jnb     short loc_18004D9A5
0x18004d99a  mov     byte ptr [rbx+0E2h], 1
0x18004d9a1  btr     edi, 0Ah
0x18004d9a5  bt      edi, 0Fh
0x18004d9a9  jnb     short loc_18004D9B6
0x18004d9ab  mov     byte ptr [rbx+0E1h], 1
0x18004d9b2  btr     edi, 0Fh
0x18004d9b6  bt      edi, 0Bh
0x18004d9ba  jnb     short loc_18004D9C7
0x18004d9bc  mov     byte ptr [rbx+0E0h], 1
0x18004d9c3  btr     edi, 0Bh
0x18004d9c7  mov     [rbx+0BCh], edi
0x18004d9cd  lea     rdi, [rbx+68h]
0x18004d9d1  test    r12b, r12b
0x18004d9d4  jz      short loc_18004DA54
0x18004d9d6  mov     ecx, 54h ; 'T'; int
0x18004d9db  call    ?GetTestFlag@@YA_NH@Z; GetTestFlag(int)
0x18004d9e0  test    al, al
0x18004d9e2  jz      short loc_18004D9FF
0x18004d9e4  call    cs:__imp_GetCurrentThreadId
0x18004d9eb  nop     dword ptr [rax+rax+00h]
0x18004d9f0  mov     [rdi], eax
0x18004d9f2  mov     qword ptr [rbx+60h], 0FFFFFFFFFFFFFFFFh
0x18004d9fa  jmp     loc_18004DAED
0x18004d9ff  mov     [rsp+0B8h+lpThreadId], rdi; lpThreadId
0x18004da04  lea     r8, ?ChildUIThread@MsiUIMessageContext@@CAKPEAU1@@Z; lpStartAddress
0x18004da0b  mov     r9, rbx; lpParameter
0x18004da0e  mov     [rsp+0B8h+dwCreationFlags], r13d; dwCreationFlags
0x18004da13  mov     edx, 0A000h; dwStackSize
0x18004da18  xor     ecx, ecx; lpThreadAttributes
0x18004da1a  call    cs:__imp_CreateThread
0x18004da21  nop     dword ptr [rax+rax+00h]
0x18004da26  mov     [rbx+60h], rax
0x18004da2a  test    rax, rax
0x18004da2d  jnz     loc_18004DAED
0x18004da33  lea     rcx, [rsp+0B8h+var_58]
0x18004da38  call    _MsiUIMessageContext__Initialize____2___CTerminate___CTerminate
0x18004da3d  mov     eax, 65Fh
0x18004da42  add     rsp, 78h
0x18004da46  pop     r15
0x18004da48  pop     r14
0x18004da4a  pop     r13
0x18004da4c  pop     r12
0x18004da4e  pop     rdi
0x18004da4f  pop     rsi
0x18004da50  pop     rbp
0x18004da51  pop     rbx
0x18004da52  retn
0x18004da54  call    cs:__imp_GetCurrentThreadId
0x18004da5b  nop     dword ptr [rax+rax+00h]
0x18004da60  mov     [rdi], eax
0x18004da62  mov     eax, [rbx+0BCh]
0x18004da68  cmp     eax, 5
0x18004da6b  jnz     short loc_18004DA76
0x18004da6d  mov     [rbx+0BCh], r13d
0x18004da74  jmp     short loc_18004DACB
0x18004da76  cmp     eax, r14d
0x18004da79  jz      short loc_18004DA85
0x18004da7b  mov     r8b, r13b
0x18004da7e  cmp     eax, 2000h
0x18004da83  jnz     short loc_18004DA88
0x18004da85  mov     r8b, 1; bool
0x18004da88  mov     al, [rbx+0E2h]
0x18004da8e  mov     r9b, [rbx+0CCh]; bool
0x18004da95  mov     rdx, cs:qword_1803138F8; HWND
0x18004da9c  mov     byte ptr [rsp+0B8h+var_80], al; bool
0x18004daa0  mov     al, [rbx+0E1h]
0x18004daa6  mov     byte ptr [rsp+0B8h+var_88], al; bool
0x18004daaa  mov     al, [rbx+0E0h]
0x18004dab0  mov     byte ptr [rsp+0B8h+lpThreadId], al; bool
0x18004dab4  mov     al, [rbx+139h]
0x18004daba  mov     byte ptr [rsp+0B8h+dwCreationFlags], al; bool
0x18004dabe  call    ?Initialize@CBasicUI@@QEAA_NPEAUHWND__@@_N11111@Z; CBasicUI::Initialize(HWND__ *,bool,bool,bool,bool,bool,bool)
0x18004dac3  test    al, al
0x18004dac5  jz      loc_18004DA33
0x18004dacb  cmp     [rbx+0E4h], r13b
0x18004dad2  jnz     short loc_18004DAED
0x18004dad4  mov     rax, cs:?CoInitialize@OLE32@@3P6AJPEAX@ZEA; long (*OLE32::CoInitialize)(void *)
0x18004dadb  xor     ecx, ecx
0x18004dadd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dae2  test    eax, eax
0x18004dae4  js      short loc_18004DAED
0x18004dae6  mov     byte ptr [rbx+0E4h], 1
0x18004daed  test    cs:dword_180313928, esi
0x18004daf3  mov     edi, 0C000000h
0x18004daf8  jz      short loc_18004DB13
0x18004dafa  lea     r8, off_18030FDB0
0x18004db01  mov     edx, edi
0x18004db03  lea     rcx, ?g_messageRec@@3VCMsiAPIMessageRec@@A; CMsiAPIMessageRec g_messageRec
0x18004db0a  call    ?Message@CMsiAPIMessageRec@@QEBA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiAPIMessageRec::Message(imtEnum,IMsiRecord &)
0x18004db0f  test    eax, eax
0x18004db11  jnz     short loc_18004DB4E
0x18004db13  test    cs:dword_180313768, esi
0x18004db19  jz      short loc_18004DB2C
0x18004db1b  xor     r8d, r8d
0x18004db1e  lea     rcx, ?g_message@@3VCMsiAPIMessage@@A; CMsiAPIMessage g_message
0x18004db25  mov     edx, edi
0x18004db27  call    ?Message@CMsiAPIMessage@@QEBA?AW4imsEnum@@W4imtEnum@@PEBG@Z; CMsiAPIMessage::Message(imtEnum,ushort const *)
0x18004db2c  mov     rax, cs:?g_pEmbeddedUI@@3PEAVCMsiEmbeddedUIManager@@EA; CMsiEmbeddedUIManager * g_pEmbeddedUI
  ... truncated ...
```
