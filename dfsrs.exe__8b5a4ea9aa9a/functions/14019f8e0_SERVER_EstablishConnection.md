# SERVER_EstablishConnection

- ea: `0x14019f8e0`
- end: `0x1401a01e2`
- name: `SERVER_EstablishConnection`
- size: `2306`
- prototype: ``
- caller_count: `0`
- callee_count: `30`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1400036d0`
- `0x14000daa0`
- `0x14000e34c`
- `0x14000ee94`
- `0x140014df4`
- `0x14001bf80`
- `0x14001cfa0`
- `0x14001d0f8`
- `0x14002c2f4`
- `0x1400370bc`
- `0x140041cd0`
- `0x140047e14`
- `0x140047e4c`
- `0x140048b10`
- `0x140048bdc`
- `0x14005209c`
- `0x140052d28`
- `0x14007b760`
- `0x14012f8b0`
- `0x140131a08`
- `0x1401982c4`
- `0x140198924`
- `0x14019ac38`
- `0x14019b968`
- `0x14019ce58`
- `0x14019f8e0`
- `0x1401afedc`
- `0x1401b1230`
- `0x1401b9494`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14019f978`
- `KERNEL32!GetCurrentThreadId` at `0x14019fa36`
- `KERNEL32!GetCurrentThreadId` at `0x14019fc81`
- `KERNEL32!GetCurrentThreadId` at `0x14019fd3e`
- `KERNEL32!GetCurrentThreadId` at `0x14019fdfb`
- `KERNEL32!GetCurrentThreadId` at `0x14019fed2`
- `KERNEL32!GetCurrentThreadId` at `0x14019ffb0`
- `KERNEL32!GetCurrentThreadId` at `0x14019f978`
- `KERNEL32!GetCurrentThreadId` at `0x14019fa36`
- `KERNEL32!GetCurrentThreadId` at `0x14019fc81`
- `KERNEL32!GetCurrentThreadId` at `0x14019fd3e`
- `KERNEL32!GetCurrentThreadId` at `0x14019fdfb`
- `KERNEL32!GetCurrentThreadId` at `0x14019fed2`
- `KERNEL32!GetCurrentThreadId` at `0x14019ffb0`

## string_xrefs

- `0x14019fbc6`: `Created a dynamic connection for the SYSVOL replication group. connId:%? rgId:%?`

## pseudocode

```c
__int64 __fastcall SERVER_EstablishConnection(
        __int64 a1,
        const struct _GUID *a2,
        struct _GUID *a3,
        unsigned int a4,
        __int64 a5,
        _DWORD *a6,
        wchar_t *a7)
{
  unsigned int v7; // edi
  struct Connection *Connection; // r13
  struct FrsStatus *v11; // rsi
  DWORD CurrentThreadId; // eax
  __int64 v13; // rcx
  struct Config::ReplicaSet *v14; // rbx
  DWORD v15; // eax
  __int64 v16; // rcx
  struct Member *v17; // r12
  Config::Connection *v18; // rax
  const unsigned __int16 *v19; // rax
  __int64 v20; // r9
  DWORD v21; // eax
  __int64 v22; // rcx
  DWORD v23; // eax
  __int64 v24; // rcx
  DWORD v25; // eax
  __int64 v26; // rcx
  Config::StringParam *v27; // rcx
  const unsigned __int16 *v28; // rax
  DWORD v29; // eax
  __int64 v30; // rcx
  struct ReplicaSetManager *ReplicaSetManager; // rax
  DWORD v32; // eax
  __int64 v33; // rcx
  UpstreamTransport *v34; // rax
  UpstreamTransport *v35; // r12
  const unsigned __int16 *v36; // rax
  const unsigned __int16 *v37; // rax
  int v38; // edx
  Config::StringParam *v39; // rcx
  const wchar_t *v40; // rax
  const wchar_t *v42; // [rsp+50h] [rbp-71h] BYREF
  int v43; // [rsp+58h] [rbp-69h]
  int v44; // [rsp+5Ch] [rbp-65h]
  const wchar_t *v45; // [rsp+60h] [rbp-61h]
  struct FrsStatus *v46; // [rsp+68h] [rbp-59h] BYREF
  int v47; // [rsp+70h] [rbp-51h]
  ReplicaSetManager *v48; // [rsp+78h] [rbp-49h] BYREF
  unsigned int v49; // [rsp+80h] [rbp-41h]
  struct Member *v50; // [rsp+88h] [rbp-39h] BYREF
  char v51[8]; // [rsp+90h] [rbp-31h] BYREF
  wchar_t *v52; // [rsp+98h] [rbp-29h] BYREF
  struct Config::ReplicaSet *ReplicaSet; // [rsp+A0h] [rbp-21h] BYREF
  UpstreamTransport *v54; // [rsp+A8h] [rbp-19h] BYREF
  struct _GUID v55; // [rsp+B0h] [rbp-11h] BYREF

  v7 = 0;
  *(_QWORD *)&v55.Data1 = a1;
  v49 = a4;
  *a6 = 327684;
  Connection = 0;
  v52 = a7;
  *(_DWORD *)a7 = 0;
  v54 = 0;
  v48 = 0;
  ReplicaSet = 0;
  v50 = 0;
  v47 = 0;
  if ( a4 != 327684 )
  {
    v46 = RpcNetwork::CheckVersionCompatibility(0x50004u, a4);
    v11 = v46;
    if ( v46 )
      goto LABEL_66;
  }
  if ( isInBackupRestore )
  {
    if ( *isInBackupRestore )
    {
      CurrentThreadId = GetCurrentThreadId();
      v46 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                  v13,
                                  9036,
                                  0,
                                  3,
                                  "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                  "SERVER_EstablishConnection",
                                  649,
                                  CurrentThreadId,
                                  0);
      v11 = v46;
      if ( v46 )
        goto LABEL_66;
    }
  }
  ReplicaSet = ConfigContext::GetReplicaSet(g_ConfigContext, a2);
  v14 = ReplicaSet;
  if ( !ReplicaSet )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v43 = 660;
      v42 = L"SERVER_EstablishConnection";
      v44 = 4;
      v45 = L"SRTR";
      dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(&v42, L"Replication group not found. connId:%? rgId:%?", a3, a2);
    }
    v15 = GetCurrentThreadId();
    v46 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                v16,
                                9026,
                                0,
                                3,
                                "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                "SERVER_EstablishConnection",
                                662,
                                v15,
                                0);
    v11 = v46;
    if ( v46 )
      goto LABEL_66;
  }
  Connection = Config::MemberList::FindConnection((struct Config::ReplicaSet *)((char *)v14 + 904), a3, &v50);
  if ( Connection )
  {
    v17 = v50;
LABEL_30:
    if ( v17 )
    {
LABEL_36:
      if ( (unsigned int)Config::BoolParam::Get((struct Connection *)((char *)Connection + 600)) )
        goto LABEL_85;
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v43 = 763;
        v42 = L"SERVER_EstablishConnection";
        v44 = 4;
        v45 = L"SRTR";
        dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(&v42, L"Connection is disabled. connId:%? rgId:%?", a3, a2);
      }
      v23 = GetCurrentThreadId();
      v46 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                  v24,
                                  9026,
                                  0,
                                  3,
                                  "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                  "SERVER_EstablishConnection",
                                  765,
                                  v23,
                                  0);
      v11 = v46;
      if ( !v46 )
      {
LABEL_85:
        if ( !(unsigned int)Config::BoolParam::Get((struct Connection *)((char *)Connection + 640)) )
          goto LABEL_86;
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
        {
          v43 = 772;
          v42 = L"SERVER_EstablishConnection";
          v44 = 4;
          v45 = L"SRTR";
          dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(
            &v42,
            L"Server is not connection's outbound partner. connId:%? rgId:%?",
            a3,
            a2);
        }
        v25 = GetCurrentThreadId();
        v46 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                    v26,
                                    9026,
                                    0,
                                    3,
                                    "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                    "SERVER_EstablishConnection",
                                    776,
                                    v25,
                                    0);
        v11 = v46;
        if ( !v46 )
        {
LABEL_86:
          if ( !Config::StringParam::Get((struct Connection *)((char *)Connection + 560)) )
            goto LABEL_55;
          v28 = Config::StringParam::Get(v27);
          if ( (unsigned int)NetworkGlobals::ValidateBindingHandle(*(RPC_BINDING_HANDLE *)&v55.Data1, v28) )
            goto LABEL_55;
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
          {
            v43 = 789;
            v42 = L"SERVER_EstablishConnection";
            v44 = 4;
            v45 = L"SRTR";
            dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(
              &v42,
              L"Caller is not the connection's inbound partner. connId:%? rgId:%?",
              a3,
              a2);
          }
          v29 = GetCurrentThreadId();
          v46 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                      v30,
                                      9026,
                                      0,
                                      3,
                                      "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                      "SERVER_EstablishConnection",
                                      793,
                                      v29,
                                      0);
          v11 = v46;
          if ( !v46 )
          {
LABEL_55:
            v55 = *(struct _GUID *)&v17[17].lpVtbl;
            ReplicaSetManager = NetworkGlobals::FindReplicaSetManager(v27, a2, &v55);
            ScopedRef<VolumeManager::ShutdownRestartTask>::Set(&v48, ReplicaSetManager);
            if ( v48 )
              goto LABEL_87;
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
            {
              v43 = 808;
              v42 = L"SERVER_EstablishConnection";
              v44 = 4;
              v45 = L"SRTR";
              dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(
                &v42,
                L"No ReplicaSetManager registered to handle this connection. connId:%? rgId:%?",
                a3,
                a2);
            }
            v32 = GetCurrentThreadId();
            v46 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                        v33,
                                        9026,
                                        0,
                                        3,
                                        "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                        "SERVER_EstablishConnection",
                                        813,
                                        v32,
                                        0);
            v11 = v46;
            if ( !v46 )
            {
LABEL_87:
              if ( !(unsigned int)Config::BoolParam::Get((struct Connection *)((char *)Connection + 800)) )
                *(_DWORD *)v52 = 1;
              v34 = (UpstreamTransport *)operator new(0x128u);
              v54 = UpstreamTransport::UpstreamTransport(v34, *((void *const *)g_NetworkGlobals + 8));
              v35 = v54;
              v36 = Config::StringParam::Get((struct Connection *)((char *)Connection + 560));
              v46 = UpstreamTransport::Initialize(v35, a3, &v55, v36, v49);
              v11 = v46;
              if ( !v46 )
              {
                v11 = ReplicaSetManager::EstablishConnection(v48, v35, a3, (const struct _GUID *)Connection + 19, v47);
                v46 = v11;
              }
            }
          }
        }
      }
      goto LABEL_65;
    }
    goto LABEL_31;
  }
  if ( (unsigned int)Config::BoolParam::Get((struct Config::ReplicaSet *)((char *)v14 + 528)) != 1
    || !(*(unsigned int (__fastcall **)(__int64))(*((_QWORD *)v14 + 113) + 40LL))((__int64)v14 + 904) )
  {
    v17 = v50;
    goto LABEL_31;
  }
  if ( !(unsigned int)IsClientSameDomainDc() )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v43 = 697;
      v42 = L"SERVER_EstablishConnection";
      v44 = 4;
      v45 = L"SRTR";
      dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(
        &v42,
        L"Cannot establish a connection for the SYSVOL replication group with a member that is not a DC in the same domain"
         " as the server. connId:%? rgId:%?",
        a3,
        a2);
    }
    v7 = 5;
    goto LABEL_82;
  }
  v17 = *(struct Member **)std::vector<ShutdownObject *>::at((char *)v14 + 952, 0);
  if ( v17 )
  {
    v18 = (Config::Connection *)operator new(0x3F8u);
    Connection = (struct Connection *)Config::Connection::Connection(v18);
    Config::GuidParam::Set((struct Connection *)((char *)Connection + 104), a3);
    Config::BoolParam::Set((struct Connection *)((char *)Connection + 600), 1);
    Config::BoolParam::Set((struct Connection *)((char *)Connection + 640), 0);
    Config::Member::AddConnection(v17, Connection);
    v47 = 1;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v43 = 727;
      v42 = L"SERVER_EstablishConnection";
      v44 = 4;
      v45 = L"SRTR";
      dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(
        &v42,
        L"Created a dynamic connection for the SYSVOL replication group. connId:%? rgId:%?",
        a3,
        a2);
    }
    v19 = Config::StringParam::Get((struct Config::ReplicaSet *)((char *)v14 + 448));
    FrsEvent::Log(1073748630, (char *)v14 + 368, v19, v20);
    if ( Connection )
      goto LABEL_30;
  }
LABEL_31:
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v43 = 753;
    v42 = L"SERVER_EstablishConnection";
    v44 = 4;
    v45 = L"SRTR";
    dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(&v42, L"Connection not found. connId:%? rgId:%?", a3, a2);
  }
  v21 = GetCurrentThreadId();
  v46 = (struct FrsStatus *)FrsStatusList::PushNewError(
                              v22,
                              9026,
                              0,
                              3,
                              "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                              "SERVER_EstablishConnection",
                              755,
                              v21,
                              0);
  v11 = v46;
  if ( !v46 )
    goto LABEL_36;
LABEL_65:
  if ( v14 )
  {
    v37 = Config::StringParam::Get((struct Config::ReplicaSet *)((char *)v14 + 448));
    goto LABEL_68;
  }
LABEL_66:
  v37 = 0;
LABEL_68:
  FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v51, v37);
  if ( v11 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v42 = L"SERVER_EstablishConnection";
      v43 = 855;
      v45 = L"SRTR";
      v44 = 3;
      dbgobj::DbgPrint<unsigned short,_GUID,_GUID,FrsStringImpl<unsigned short,char>,FrsStatus>(
        (unsigned int)&v42,
        (unsigned int)L"Failed to establish an outbound connection. connId:%? rgId:%? rgName:%? Error:%?",
        (_DWORD)a3,
        (_DWORD)a2,
        (__int64)v51,
        (__int64)v11);
    }
    v7 = *((_DWORD *)v11 + 1);
    CLEAR_ERROR(&v46);
  }
  else if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v43 = 865;
    v42 = L"SERVER_EstablishConnection";
    v44 = 4;
    v45 = L"SRTR";
    if ( Config::StringParam::Get((struct Connection *)((char *)Connection + 480)) )
      v40 = Config::StringParam::Get(v39);
    else
      v40 = L"<null>";
    v52 = (wchar_t *)v40;
    dbgobj::DbgPrint<unsigned short,_GUID,_GUID,FrsStringImpl<unsigned short,char>,unsigned short const *>(
      (unsigned int)&v42,
      v38,
      (_DWORD)a3,
      (_DWORD)a2,
      (__int64)v51,
      (__int64)&v52);
  }
  FrsStringImpl<char,unsigned short>::ReleaseBody(v51);
LABEL_82:
  ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&ReplicaSet);
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v48);
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v54);
  return v7;
}

```

## disassembly

```asm
0x14019f8e0  push    rbp
0x14019f8e2  push    rbx
0x14019f8e3  push    rsi
0x14019f8e4  push    rdi
0x14019f8e5  push    r12
0x14019f8e7  push    r13
0x14019f8e9  push    r14
0x14019f8eb  push    r15
0x14019f8ed  lea     rbp, [rsp-7]
0x14019f8f2  sub     rsp, 0C8h
0x14019f8f9  mov     rax, [rbp+3Fh+arg_28]
0x14019f8fd  xor     edi, edi
0x14019f8ff  mov     qword ptr [rbp+3Fh+var_50.Data1], rcx
0x14019f903  mov     r14, r8
0x14019f906  mov     rcx, [rbp+3Fh+arg_30]
0x14019f90a  mov     r8d, 50004h
0x14019f910  mov     [rbp+3Fh+var_80], r9d
0x14019f914  mov     r15, rdx
0x14019f917  mov     [rax], r8d
0x14019f91a  mov     r13d, edi
0x14019f91d  mov     [rbp+3Fh+var_68], rcx
0x14019f921  lea     r12d, [rdi+4]
0x14019f925  mov     [rcx], edi
0x14019f927  mov     [rbp+3Fh+var_58], rdi
0x14019f92b  mov     [rbp+3Fh+var_88], rdi
0x14019f92f  mov     [rbp+3Fh+var_60], rdi
0x14019f933  mov     [rbp+3Fh+var_78], rdi
0x14019f937  mov     [rbp+3Fh+var_90], edi
0x14019f93a  cmp     r9d, r8d
0x14019f93d  jz      short loc_14019F95A
0x14019f93f  mov     edx, r9d; unsigned int
0x14019f942  mov     ecx, r8d; unsigned int
0x14019f945  call    ?CheckVersionCompatibility@RpcNetwork@@SAPEAVFrsStatus@@KK@Z; RpcNetwork::CheckVersionCompatibility(ulong,ulong)
0x14019f94a  mov     [rbp+3Fh+var_98], rax
0x14019f94e  mov     rsi, rax
0x14019f951  test    rax, rax
0x14019f954  jnz     loc_1401A00A0
0x14019f95a  mov     rax, cs:?isInBackupRestore@@3PEAHEA; int * isInBackupRestore
0x14019f961  lea     rsi, aServerEstablis_0; "SERVER_EstablishConnection"
0x14019f968  lea     rbx, aBaseFsRemotefs_11; "base\\fs\\remotefs\\frs\\src\\transport"...
0x14019f96f  test    rax, rax
0x14019f972  jz      short loc_14019F9C9
0x14019f974  cmp     [rax], edi
0x14019f976  jz      short loc_14019F9C9
0x14019f978  call    cs:__imp_GetCurrentThreadId
0x14019f97f  nop     dword ptr [rax+rax+00h]
0x14019f984  mov     [rsp+100h+var_C0], rdi
0x14019f989  mov     r9d, 3
0x14019f98f  mov     [rsp+100h+var_C8], eax
0x14019f993  xor     r8d, r8d
0x14019f996  mov     [rsp+100h+var_D0], 289h
0x14019f99e  mov     edx, 234Ch
0x14019f9a3  mov     [rsp+100h+var_D8], rsi
0x14019f9a8  mov     qword ptr [rsp+100h+var_E0], rbx
0x14019f9ad  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14019f9b2  mov     [rbp+3Fh+var_98], rax
0x14019f9b6  mov     rsi, rax
0x14019f9b9  test    rax, rax
0x14019f9bc  jnz     loc_1401A00A0
0x14019f9c2  lea     rsi, aServerEstablis_0; "SERVER_EstablishConnection"
0x14019f9c9  mov     rcx, cs:?g_ConfigContext@@3PEAVConfigContext@@EA; this
0x14019f9d0  mov     rdx, r15; struct _GUID *
0x14019f9d3  call    ?GetReplicaSet@ConfigContext@@QEAAPEAVReplicaSet@Config@@PEBU_GUID@@@Z; ConfigContext::GetReplicaSet(_GUID const *)
0x14019f9d8  mov     [rbp+3Fh+var_60], rax
0x14019f9dc  mov     rbx, rax
0x14019f9df  test    rax, rax
0x14019f9e2  jnz     loc_14019FA87
0x14019f9e8  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14019f9ef  test    rax, rax
0x14019f9f2  jz      short loc_14019FA36
0x14019f9f4  cmp     [rax+40h], edi
0x14019f9f7  jz      short loc_14019FA36
0x14019f9f9  cmp     [rax+38h], r12d
0x14019f9fd  jl      short loc_14019FA36
0x14019f9ff  lea     rax, aServerEstablis; "SERVER_EstablishConnection"
0x14019fa06  mov     [rbp+3Fh+var_A8], 294h
0x14019fa0d  mov     [rbp+3Fh+var_B0], rax
0x14019fa11  lea     rdx, aReplicationGro_9; "Replication group not found. connId:%? "...
0x14019fa18  lea     rax, aSrtr; "SRTR"
0x14019fa1f  mov     [rbp+3Fh+var_A4], r12d
0x14019fa23  mov     r9, r15
0x14019fa26  mov     [rbp+3Fh+var_A0], rax
0x14019fa2a  mov     r8, r14
0x14019fa2d  lea     rcx, [rbp+3Fh+var_B0]
0x14019fa31  call    ??$DbgPrint@GU_GUID@@U1@@dbgobj@@QEAA_KPEBGAEBU_GUID@@1@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID>(ushort const *,_GUID const &,_GUID const &)
0x14019fa36  call    cs:__imp_GetCurrentThreadId
0x14019fa3d  nop     dword ptr [rax+rax+00h]
0x14019fa42  mov     [rsp+100h+var_C0], rdi
0x14019fa47  mov     r9d, 3
0x14019fa4d  mov     [rsp+100h+var_C8], eax
0x14019fa51  xor     r8d, r8d
0x14019fa54  mov     [rsp+100h+var_D0], 296h
0x14019fa5c  lea     rax, aBaseFsRemotefs_11; "base\\fs\\remotefs\\frs\\src\\transport"...
0x14019fa63  mov     [rsp+100h+var_D8], rsi
0x14019fa68  mov     edx, 2342h
0x14019fa6d  mov     qword ptr [rsp+100h+var_E0], rax
0x14019fa72  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14019fa77  mov     [rbp+3Fh+var_98], rax
0x14019fa7b  mov     rsi, rax
0x14019fa7e  test    rax, rax
0x14019fa81  jnz     loc_1401A00A0
0x14019fa87  lea     rsi, [rbx+388h]
0x14019fa8e  mov     rdx, r14; struct _GUID *
0x14019fa91  mov     rcx, rsi; this
0x14019fa94  lea     r8, [rbp+3Fh+var_78]; struct Member **
0x14019fa98  call    ?FindConnection@MemberList@Config@@QEBAPEAVConnection@2@PEBU_GUID@@PEAPEAVMember@2@@Z; Config::MemberList::FindConnection(_GUID const *,Config::Member * *)
0x14019fa9d  mov     r13, rax
0x14019faa0  test    rax, rax
0x14019faa3  jnz     loc_14019FC23
0x14019faa9  lea     rcx, [rbx+210h]; this
0x14019fab0  call    ?Get@BoolParam@Config@@QEBA?BHXZ; Config::BoolParam::Get(void)
0x14019fab5  cmp     eax, 1
0x14019fab8  jnz     loc_14019FC1D
0x14019fabe  mov     rax, [rsi]
0x14019fac1  mov     rcx, rsi
0x14019fac4  mov     rax, [rax+28h]
0x14019fac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14019facd  test    eax, eax
0x14019facf  jz      loc_14019FC1D
0x14019fad5  call    IsClientSameDomainDc
0x14019fada  test    eax, eax
0x14019fadc  jnz     short loc_14019FB36
0x14019fade  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14019fae5  test    rax, rax
0x14019fae8  jz      short loc_14019FB2C
0x14019faea  cmp     [rax+40h], edi
0x14019faed  jz      short loc_14019FB2C
0x14019faef  cmp     [rax+38h], r12d
0x14019faf3  jl      short loc_14019FB2C
0x14019faf5  lea     rax, aServerEstablis; "SERVER_EstablishConnection"
0x14019fafc  mov     [rbp+3Fh+var_A8], 2B9h
0x14019fb03  mov     [rbp+3Fh+var_B0], rax
0x14019fb07  lea     rdx, aCannotEstablis_0; "Cannot establish a connection for the S"...
0x14019fb0e  lea     rax, aSrtr; "SRTR"
0x14019fb15  mov     [rbp+3Fh+var_A4], r12d
0x14019fb19  mov     r9, r15
0x14019fb1c  mov     [rbp+3Fh+var_A0], rax
0x14019fb20  mov     r8, r14
0x14019fb23  lea     rcx, [rbp+3Fh+var_B0]
0x14019fb27  call    ??$DbgPrint@GU_GUID@@U1@@dbgobj@@QEAA_KPEBGAEBU_GUID@@1@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID>(ushort const *,_GUID const &,_GUID const &)
0x14019fb2c  mov     edi, 5
0x14019fb31  jmp     loc_1401A01B0
0x14019fb36  lea     rcx, [rsi+30h]
0x14019fb3a  xor     edx, edx
0x14019fb3c  call    ?at@?$vector@PEAVShutdownObject@@V?$allocator@PEAVShutdownObject@@@std@@@std@@QEAAAEAPEAVShutdownObject@@_K@Z; std::vector<ShutdownObject *>::at(unsigned __int64)
0x14019fb41  mov     r12, [rax]
0x14019fb44  test    r12, r12
0x14019fb47  jz      loc_14019FC30
0x14019fb4d  mov     ecx, 3F8h; Size
0x14019fb52  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14019fb57  mov     rcx, rax; this
0x14019fb5a  call    ??0Connection@Config@@QEAA@XZ; Config::Connection::Connection(void)
0x14019fb5f  mov     rdx, r14; struct _GUID *
0x14019fb62  mov     r13, rax
0x14019fb65  lea     rcx, [rax+68h]; this
0x14019fb69  call    ?Set@GuidParam@Config@@QEAAXPEBU_GUID@@@Z; Config::GuidParam::Set(_GUID const *)
0x14019fb6e  mov     esi, 1
0x14019fb73  lea     rcx, [r13+258h]; this
0x14019fb7a  mov     edx, esi; int
0x14019fb7c  call    ?Set@BoolParam@Config@@QEAAHH@Z; Config::BoolParam::Set(int)
0x14019fb81  lea     rcx, [r13+280h]; this
0x14019fb88  xor     edx, edx; int
0x14019fb8a  call    ?Set@BoolParam@Config@@QEAAHH@Z; Config::BoolParam::Set(int)
0x14019fb8f  mov     rdx, r13; struct Connection *
0x14019fb92  mov     rcx, r12; this
0x14019fb95  call    ?AddConnection@Member@Config@@QEAAHPEAVConnection@2@@Z; Config::Member::AddConnection(Config::Connection *)
0x14019fb9a  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14019fba1  mov     [rbp+3Fh+var_90], esi
0x14019fba4  test    rax, rax
0x14019fba7  jz      short loc_14019FBEE
0x14019fba9  cmp     [rax+40h], edi
0x14019fbac  jz      short loc_14019FBEE
0x14019fbae  cmp     dword ptr [rax+38h], 4
0x14019fbb2  jl      short loc_14019FBEE
0x14019fbb4  lea     rax, aServerEstablis; "SERVER_EstablishConnection"
0x14019fbbb  mov     [rbp+3Fh+var_A8], 2D7h
0x14019fbc2  mov     [rbp+3Fh+var_B0], rax
0x14019fbc6  lea     rdx, aCreatedADynami; "Created a dynamic connection for the SY"...
0x14019fbcd  lea     rax, aSrtr; "SRTR"
0x14019fbd4  mov     [rbp+3Fh+var_A4], 4
0x14019fbdb  mov     r9, r15
0x14019fbde  mov     [rbp+3Fh+var_A0], rax
0x14019fbe2  mov     r8, r14
0x14019fbe5  lea     rcx, [rbp+3Fh+var_B0]
0x14019fbe9  call    ??$DbgPrint@GU_GUID@@U1@@dbgobj@@QEAA_KPEBGAEBU_GUID@@1@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID>(ushort const *,_GUID const &,_GUID const &)
0x14019fbee  lea     rcx, [rbx+1C0h]; this
0x14019fbf5  lea     r9, [r12+98h]
0x14019fbfd  call    ?Get@StringParam@Config@@QEBAPEBGXZ; Config::StringParam::Get(void)
0x14019fc02  mov     r8, rax
0x14019fc05  lea     rdx, [rbx+170h]
0x14019fc0c  mov     ecx, 40001A96h
0x14019fc11  call    ?Log@FrsEvent@@SAXW4FrsEventsEnum3@@PEBG11@Z; FrsEvent::Log(FrsEventsEnum3,ushort const *,ushort const *,ushort const *)
0x14019fc16  test    r13, r13
0x14019fc19  jz      short loc_14019FC30
0x14019fc1b  jmp     short loc_14019FC27
0x14019fc1d  mov     r12, [rbp+3Fh+var_78]
0x14019fc21  jmp     short loc_14019FC30
0x14019fc23  mov     r12, [rbp+3Fh+var_78]
0x14019fc27  test    r12, r12
0x14019fc2a  jnz     loc_14019FCD9
0x14019fc30  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14019fc37  test    rax, rax
0x14019fc3a  jz      short loc_14019FC81
0x14019fc3c  cmp     [rax+40h], edi
0x14019fc3f  jz      short loc_14019FC81
0x14019fc41  cmp     dword ptr [rax+38h], 4
0x14019fc45  jl      short loc_14019FC81
0x14019fc47  lea     rax, aServerEstablis; "SERVER_EstablishConnection"
0x14019fc4e  mov     [rbp+3Fh+var_A8], 2F1h
0x14019fc55  mov     [rbp+3Fh+var_B0], rax
0x14019fc59  lea     rdx, aConnectionNotF; "Connection not found. connId:%? rgId:%?"
0x14019fc60  lea     rax, aSrtr; "SRTR"
0x14019fc67  mov     [rbp+3Fh+var_A4], 4
0x14019fc6e  mov     r9, r15
0x14019fc71  mov     [rbp+3Fh+var_A0], rax
0x14019fc75  mov     r8, r14
0x14019fc78  lea     rcx, [rbp+3Fh+var_B0]
0x14019fc7c  call    ??$DbgPrint@GU_GUID@@U1@@dbgobj@@QEAA_KPEBGAEBU_GUID@@1@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID>(ushort const *,_GUID const &,_GUID const &)
0x14019fc81  call    cs:__imp_GetCurrentThreadId
0x14019fc88  nop     dword ptr [rax+rax+00h]
0x14019fc8d  mov     [rsp+100h+var_C0], rdi
0x14019fc92  mov     r9d, 3
0x14019fc98  mov     [rsp+100h+var_C8], eax
0x14019fc9c  xor     r8d, r8d
0x14019fc9f  lea     rax, aServerEstablis_0; "SERVER_EstablishConnection"
0x14019fca6  mov     [rsp+100h+var_D0], 2F3h
0x14019fcae  mov     [rsp+100h+var_D8], rax
0x14019fcb3  mov     edx, 2342h
0x14019fcb8  lea     rax, aBaseFsRemotefs_11; "base\\fs\\remotefs\\frs\\src\\transport"...
0x14019fcbf  mov     qword ptr [rsp+100h+var_E0], rax
0x14019fcc4  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14019fcc9  mov     [rbp+3Fh+var_98], rax
0x14019fccd  mov     rsi, rax
0x14019fcd0  test    rax, rax
0x14019fcd3  jnz     loc_1401A009B
0x14019fcd9  lea     rcx, [r13+258h]; this
0x14019fce0  call    ?Get@BoolParam@Config@@QEBA?BHXZ; Config::BoolParam::Get(void)
0x14019fce5  test    eax, eax
0x14019fce7  jnz     loc_14019FD96
0x14019fced  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14019fcf4  test    rax, rax
0x14019fcf7  jz      short loc_14019FD3E
0x14019fcf9  cmp     [rax+40h], edi
0x14019fcfc  jz      short loc_14019FD3E
0x14019fcfe  cmp     dword ptr [rax+38h], 4
0x14019fd02  jl      short loc_14019FD3E
0x14019fd04  lea     rax, aServerEstablis; "SERVER_EstablishConnection"
0x14019fd0b  mov     [rbp+3Fh+var_A8], 2FBh
0x14019fd12  mov     [rbp+3Fh+var_B0], rax
0x14019fd16  lea     rdx, aConnectionIsDi_0; "Connection is disabled. connId:%? rgId:"...
0x14019fd1d  lea     rax, aSrtr; "SRTR"
0x14019fd24  mov     [rbp+3Fh+var_A4], 4
0x14019fd2b  mov     r9, r15
0x14019fd2e  mov     [rbp+3Fh+var_A0], rax
0x14019fd32  mov     r8, r14
0x14019fd35  lea     rcx, [rbp+3Fh+var_B0]
0x14019fd39  call    ??$DbgPrint@GU_GUID@@U1@@dbgobj@@QEAA_KPEBGAEBU_GUID@@1@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID>(ushort const *,_GUID const &,_GUID const &)
0x14019fd3e  call    cs:__imp_GetCurrentThreadId
0x14019fd45  nop     dword ptr [rax+rax+00h]
0x14019fd4a  mov     [rsp+100h+var_C0], rdi
0x14019fd4f  mov     r9d, 3
0x14019fd55  mov     [rsp+100h+var_C8], eax
0x14019fd59  xor     r8d, r8d
0x14019fd5c  lea     rax, aServerEstablis_0; "SERVER_EstablishConnection"
0x14019fd63  mov     [rsp+100h+var_D0], 2FDh
0x14019fd6b  mov     [rsp+100h+var_D8], rax
0x14019fd70  mov     edx, 2342h
0x14019fd75  lea     rax, aBaseFsRemotefs_11; "base\\fs\\remotefs\\frs\\src\\transport"...
0x14019fd7c  mov     qword ptr [rsp+100h+var_E0], rax
0x14019fd81  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14019fd86  mov     [rbp+3Fh+var_98], rax
0x14019fd8a  mov     rsi, rax
0x14019fd8d  test    rax, rax
0x14019fd90  jnz     loc_1401A009B
0x14019fd96  lea     rcx, [r13+280h]; this
0x14019fd9d  call    ?Get@BoolParam@Config@@QEBA?BHXZ; Config::BoolParam::Get(void)
0x14019fda2  test    eax, eax
0x14019fda4  jz      loc_14019FE53
0x14019fdaa  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14019fdb1  test    rax, rax
0x14019fdb4  jz      short loc_14019FDFB
0x14019fdb6  cmp     [rax+40h], edi
0x14019fdb9  jz      short loc_14019FDFB
0x14019fdbb  cmp     dword ptr [rax+38h], 4
0x14019fdbf  jl      short loc_14019FDFB
0x14019fdc1  lea     rax, aServerEstablis; "SERVER_EstablishConnection"
0x14019fdc8  mov     [rbp+3Fh+var_A8], 304h
0x14019fdcf  mov     [rbp+3Fh+var_B0], rax
0x14019fdd3  lea     rdx, aServerIsNotCon; "Server is not connection's outbound par"...
0x14019fdda  lea     rax, aSrtr; "SRTR"
0x14019fde1  mov     [rbp+3Fh+var_A4], 4
0x14019fde8  mov     r9, r15
0x14019fdeb  mov     [rbp+3Fh+var_A0], rax
0x14019fdef  mov     r8, r14
0x14019fdf2  lea     rcx, [rbp+3Fh+var_B0]
0x14019fdf6  call    ??$DbgPrint@GU_GUID@@U1@@dbgobj@@QEAA_KPEBGAEBU_GUID@@1@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID>(ushort const *,_GUID const &,_GUID const &)
0x14019fdfb  call    cs:__imp_GetCurrentThreadId
0x14019fe02  nop     dword ptr [rax+rax+00h]
0x14019fe07  mov     [rsp+100h+var_C0], rdi
0x14019fe0c  mov     r9d, 3
  ... truncated ...
```
