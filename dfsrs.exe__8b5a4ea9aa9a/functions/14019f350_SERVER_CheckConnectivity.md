# SERVER_CheckConnectivity

- ea: `0x14019f350`
- end: `0x14019f8d4`
- name: `SERVER_CheckConnectivity`
- size: `1412`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task`

## callees

- `0x14000daa0`
- `0x14000e34c`
- `0x14002c2f4`
- `0x1400370bc`
- `0x140041cd0`
- `0x140047e14`
- `0x140052d28`
- `0x14007b760`
- `0x140139858`
- `0x140198924`
- `0x14019f350`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14019f3a6`
- `KERNEL32!GetCurrentThreadId` at `0x14019f471`
- `KERNEL32!GetCurrentThreadId` at `0x14019f53f`
- `KERNEL32!GetCurrentThreadId` at `0x14019f5f9`
- `KERNEL32!GetCurrentThreadId` at `0x14019f6b3`
- `KERNEL32!GetCurrentThreadId` at `0x14019f824`
- `KERNEL32!GetCurrentThreadId` at `0x14019f3a6`
- `KERNEL32!GetCurrentThreadId` at `0x14019f471`
- `KERNEL32!GetCurrentThreadId` at `0x14019f53f`
- `KERNEL32!GetCurrentThreadId` at `0x14019f5f9`
- `KERNEL32!GetCurrentThreadId` at `0x14019f6b3`
- `KERNEL32!GetCurrentThreadId` at `0x14019f824`

## string_xrefs

- `0x14019f8aa`: `Ready to establish connection. connId:%? rgId:%?`
- `0x14019f734`: `Not ready to establish connection. connId:%? rgId:%? Error:%?`

## pseudocode

```c
__int64 __fastcall SERVER_CheckConnectivity(__int64 a1, const struct _GUID *a2, const struct _GUID *a3)
{
  unsigned int v3; // edi
  struct Config::ReplicaSet *ReplicaSet; // rbx
  struct FrsStatus *v7; // rsi
  struct FrsStatus *v8; // rcx
  struct FrsStatus *v9; // r12
  struct FrsStatus *v10; // rax
  DWORD CurrentThreadId; // eax
  __int64 v12; // rcx
  DWORD v13; // eax
  __int64 v14; // rcx
  struct Connection *Connection; // rax
  __int64 v16; // r12
  struct Connection *v17; // rbx
  DWORD v18; // eax
  __int64 v19; // rcx
  DWORD v20; // eax
  __int64 v21; // rcx
  NetworkGlobals *v22; // rcx
  DWORD v23; // eax
  __int64 v24; // rcx
  struct ReplicaSetManager *ReplicaSetManager; // rax
  DWORD v27; // eax
  __int64 v28; // rcx
  const wchar_t *v29; // [rsp+50h] [rbp-19h] BYREF
  int v30; // [rsp+58h] [rbp-11h]
  int v31; // [rsp+5Ch] [rbp-Dh]
  const wchar_t *v32; // [rsp+60h] [rbp-9h]
  struct FrsStatus *v33; // [rsp+68h] [rbp-1h] BYREF
  __int64 v34; // [rsp+70h] [rbp+7h] BYREF
  struct Config::ReplicaSet *v35; // [rsp+78h] [rbp+Fh] BYREF
  struct _GUID v36; // [rsp+80h] [rbp+17h] BYREF

  v3 = 0;
  v34 = 0;
  ReplicaSet = 0;
  v35 = 0;
  *(_QWORD *)&v36.Data1 = 0;
  v7 = 0;
  v33 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  if ( isInBackupRestore && *isInBackupRestore )
  {
    CurrentThreadId = GetCurrentThreadId();
    v10 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                v12,
                                9036,
                                0,
                                3,
                                "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                "SERVER_CheckConnectivity",
                                451,
                                CurrentThreadId,
                                0);
    v7 = v10;
    v33 = v10;
    v9 = v10;
    v8 = v10;
  }
  if ( !v8 )
  {
    ReplicaSet = ConfigContext::GetReplicaSet(g_ConfigContext, a2);
    v35 = ReplicaSet;
    v10 = v9;
    if ( !ReplicaSet )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v30 = 462;
        v29 = L"SERVER_CheckConnectivity";
        v31 = 4;
        v32 = L"SRTR";
        dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(&v29, L"Replication group not found. connId:%? rgId:%?", a3, a2);
      }
      v13 = GetCurrentThreadId();
      v10 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                  v14,
                                  9026,
                                  0,
                                  3,
                                  "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                  "SERVER_CheckConnectivity",
                                  466,
                                  v13,
                                  0);
      v7 = v10;
      v33 = v10;
    }
  }
  if ( v10 )
    goto LABEL_33;
  Connection = Config::MemberList::FindConnection(
                 (struct Config::ReplicaSet *)((char *)ReplicaSet + 904),
                 a3,
                 (struct Member **)&v36);
  v16 = *(_QWORD *)&v36.Data1;
  v17 = Connection;
  if ( !Connection || !*(_QWORD *)&v36.Data1 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v30 = 479;
      v29 = L"SERVER_CheckConnectivity";
      v31 = 4;
      v32 = L"SRTR";
      dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(&v29, L"Connection not found. connId:%? rgId:%?", a3, a2);
    }
    v18 = GetCurrentThreadId();
    v33 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                v19,
                                9026,
                                0,
                                3,
                                "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                "SERVER_CheckConnectivity",
                                483,
                                v18,
                                0);
    v7 = v33;
    if ( v33 )
      goto LABEL_33;
  }
  if ( (unsigned int)Config::BoolParam::Get((struct Connection *)((char *)v17 + 640)) )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v30 = 491;
      v29 = L"SERVER_CheckConnectivity";
      v31 = 4;
      v32 = L"SRTR";
      dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(
        &v29,
        L"Server is not connection's outbound partner. connId:%? rgId:%?",
        a3,
        a2);
    }
    v20 = GetCurrentThreadId();
    v33 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                v21,
                                9026,
                                0,
                                3,
                                "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                "SERVER_CheckConnectivity",
                                495,
                                v20,
                                0);
    v7 = v33;
    if ( v33 )
      goto LABEL_33;
  }
  if ( !(unsigned int)Config::BoolParam::Get((struct Connection *)((char *)v17 + 600)) )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v30 = 502;
      v29 = L"SERVER_CheckConnectivity";
      v31 = 4;
      v32 = L"SRTR";
      dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(&v29, L"Connection is disabled. connId:%? rgd:%?", a3, a2);
    }
    v23 = GetCurrentThreadId();
    v33 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                v24,
                                9026,
                                0,
                                3,
                                "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                "SERVER_CheckConnectivity",
                                504,
                                v23,
                                0);
    v7 = v33;
    if ( v33 )
      goto LABEL_33;
  }
  v36 = *(struct _GUID *)(v16 + 136);
  ReplicaSetManager = NetworkGlobals::FindReplicaSetManager(v22, a2, &v36);
  ScopedRef<VolumeManager::ShutdownRestartTask>::Set(&v34, ReplicaSetManager);
  if ( v34 )
    goto LABEL_45;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v30 = 524;
    v29 = L"SERVER_CheckConnectivity";
    v31 = 4;
    v32 = L"SRTR";
    dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(
      &v29,
      L"No ReplicaSetManager registered to handle this connection. connId:%? rgId:%?",
      a3,
      a2);
  }
  v27 = GetCurrentThreadId();
  v33 = (struct FrsStatus *)FrsStatusList::PushNewError(
                              v28,
                              9026,
                              0,
                              3,
                              "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                              "SERVER_CheckConnectivity",
                              529,
                              v27,
                              0);
  v7 = v33;
  if ( v33 )
  {
LABEL_33:
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v30 = 542;
      v29 = L"SERVER_CheckConnectivity";
      v31 = 4;
      v32 = L"SRTR";
      dbgobj::DbgPrint<unsigned short,_GUID,_GUID,FrsStatus>(
        (unsigned int)&v29,
        (unsigned int)L"Not ready to establish connection. connId:%? rgId:%? Error:%?",
        (_DWORD)a3,
        (_DWORD)a2,
        (__int64)v7);
    }
    v3 = *((_DWORD *)v7 + 1);
    CLEAR_ERROR(&v33);
  }
  else
  {
LABEL_45:
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v30 = 537;
      v29 = L"SERVER_CheckConnectivity";
      v31 = 4;
      v32 = L"SRTR";
      dbgobj::DbgPrint<unsigned short,_GUID,_GUID>(&v29, L"Ready to establish connection. connId:%? rgId:%?", a3, a2);
    }
  }
  ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v35);
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v34);
  return v3;
}

```

## disassembly

```asm
0x14019f350  mov     [rsp-8+arg_0], rbx
0x14019f355  push    rbp
0x14019f356  push    rsi
0x14019f357  push    rdi
0x14019f358  push    r12
0x14019f35a  push    r13
0x14019f35c  push    r14
0x14019f35e  push    r15
0x14019f360  lea     rbp, [rsp-27h]
0x14019f365  sub     rsp, 90h
0x14019f36c  xor     edi, edi
0x14019f36e  lea     r13, aServerCheckcon_0; "SERVER_CheckConnectivity"
0x14019f375  mov     r14, rdx
0x14019f378  mov     [rbp+57h+var_50], rdi
0x14019f37c  mov     rdx, cs:?isInBackupRestore@@3PEAHEA; int * isInBackupRestore
0x14019f383  mov     ebx, edi
0x14019f385  mov     [rbp+57h+var_48], rbx
0x14019f389  mov     r15, r8
0x14019f38c  mov     qword ptr [rbp+57h+var_40.Data1], rdi
0x14019f390  mov     esi, edi
0x14019f392  mov     [rbp+57h+var_58], rdi
0x14019f396  mov     ecx, edi
0x14019f398  mov     r12d, edi
0x14019f39b  mov     eax, edi
0x14019f39d  test    rdx, rdx
0x14019f3a0  jz      short loc_14019F3F2
0x14019f3a2  cmp     [rdx], edi
0x14019f3a4  jz      short loc_14019F3F2
0x14019f3a6  call    cs:__imp_GetCurrentThreadId
0x14019f3ad  nop     dword ptr [rax+rax+00h]
0x14019f3b2  mov     [rsp+0C0h+var_80], rdi
0x14019f3b7  lea     r9d, [rdi+3]
0x14019f3bb  mov     [rsp+0C0h+var_88], eax
0x14019f3bf  xor     r8d, r8d
0x14019f3c2  mov     [rsp+0C0h+var_90], 1C3h
0x14019f3ca  lea     rax, aBaseFsRemotefs_11; "base\\fs\\remotefs\\frs\\src\\transport"...
0x14019f3d1  mov     [rsp+0C0h+var_98], r13
0x14019f3d6  mov     edx, 234Ch
0x14019f3db  mov     [rsp+0C0h+var_A0], rax
0x14019f3e0  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14019f3e5  mov     rsi, rax
0x14019f3e8  mov     [rbp+57h+var_58], rax
0x14019f3ec  mov     r12, rax
0x14019f3ef  mov     rcx, rax
0x14019f3f2  mov     r13d, 4
0x14019f3f8  test    rcx, rcx
0x14019f3fb  jnz     loc_14019F4C0
0x14019f401  mov     rcx, cs:?g_ConfigContext@@3PEAVConfigContext@@EA; this
0x14019f408  mov     rdx, r14; struct _GUID *
0x14019f40b  call    ?GetReplicaSet@ConfigContext@@QEAAPEAVReplicaSet@Config@@PEBU_GUID@@@Z; ConfigContext::GetReplicaSet(_GUID const *)
0x14019f410  mov     rbx, rax
0x14019f413  mov     [rbp+57h+var_48], rax
0x14019f417  mov     rax, r12
0x14019f41a  test    rbx, rbx
0x14019f41d  jnz     loc_14019F4C0
0x14019f423  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14019f42a  test    rax, rax
0x14019f42d  jz      short loc_14019F471
0x14019f42f  cmp     [rax+40h], edi
0x14019f432  jz      short loc_14019F471
0x14019f434  cmp     [rax+38h], r13d
0x14019f438  jl      short loc_14019F471
0x14019f43a  lea     rax, aServerCheckcon; "SERVER_CheckConnectivity"
0x14019f441  mov     [rbp+57h+var_68], 1CEh
0x14019f448  mov     [rbp+57h+var_70], rax
0x14019f44c  lea     rdx, aReplicationGro_9; "Replication group not found. connId:%? "...
0x14019f453  lea     rax, aSrtr; "SRTR"
0x14019f45a  mov     [rbp+57h+var_64], r13d
0x14019f45e  mov     r9, r14
0x14019f461  mov     [rbp+57h+var_60], rax
0x14019f465  mov     r8, r15
0x14019f468  lea     rcx, [rbp+57h+var_70]
0x14019f46c  call    ??$DbgPrint@GU_GUID@@U1@@dbgobj@@QEAA_KPEBGAEBU_GUID@@1@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID>(ushort const *,_GUID const &,_GUID const &)
0x14019f471  call    cs:__imp_GetCurrentThreadId
0x14019f478  nop     dword ptr [rax+rax+00h]
0x14019f47d  mov     [rsp+0C0h+var_80], rdi
0x14019f482  mov     r9d, 3
0x14019f488  mov     [rsp+0C0h+var_88], eax
0x14019f48c  xor     r8d, r8d
0x14019f48f  lea     rax, aServerCheckcon_0; "SERVER_CheckConnectivity"
0x14019f496  mov     [rsp+0C0h+var_90], 1D2h
0x14019f49e  mov     [rsp+0C0h+var_98], rax
0x14019f4a3  mov     edx, 2342h
0x14019f4a8  lea     rax, aBaseFsRemotefs_11; "base\\fs\\remotefs\\frs\\src\\transport"...
0x14019f4af  mov     [rsp+0C0h+var_A0], rax
0x14019f4b4  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14019f4b9  mov     rsi, rax
0x14019f4bc  mov     [rbp+57h+var_58], rax
0x14019f4c0  test    rax, rax
0x14019f4c3  jnz     loc_14019F70B
0x14019f4c9  lea     rcx, [rbx+388h]; this
0x14019f4d0  mov     rdx, r15; struct _GUID *
0x14019f4d3  lea     r8, [rbp+57h+var_40]; struct Member **
0x14019f4d7  call    ?FindConnection@MemberList@Config@@QEBAPEAVConnection@2@PEBU_GUID@@PEAPEAVMember@2@@Z; Config::MemberList::FindConnection(_GUID const *,Config::Member * *)
0x14019f4dc  mov     r12, qword ptr [rbp+57h+var_40.Data1]
0x14019f4e0  mov     rbx, rax
0x14019f4e3  test    rax, rax
0x14019f4e6  jz      short loc_14019F4F1
0x14019f4e8  test    r12, r12
0x14019f4eb  jnz     loc_14019F597
0x14019f4f1  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14019f4f8  test    rcx, rcx
0x14019f4fb  jz      short loc_14019F53F
0x14019f4fd  cmp     [rcx+40h], edi
0x14019f500  jz      short loc_14019F53F
0x14019f502  cmp     [rcx+38h], r13d
0x14019f506  jl      short loc_14019F53F
0x14019f508  lea     rax, aServerCheckcon; "SERVER_CheckConnectivity"
0x14019f50f  mov     [rbp+57h+var_68], 1DFh
0x14019f516  mov     [rbp+57h+var_70], rax
0x14019f51a  lea     rdx, aConnectionNotF; "Connection not found. connId:%? rgId:%?"
0x14019f521  lea     rax, aSrtr; "SRTR"
0x14019f528  mov     [rbp+57h+var_64], r13d
0x14019f52c  mov     r9, r14
0x14019f52f  mov     [rbp+57h+var_60], rax
0x14019f533  mov     r8, r15
0x14019f536  lea     rcx, [rbp+57h+var_70]
0x14019f53a  call    ??$DbgPrint@GU_GUID@@U1@@dbgobj@@QEAA_KPEBGAEBU_GUID@@1@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID>(ushort const *,_GUID const &,_GUID const &)
0x14019f53f  call    cs:__imp_GetCurrentThreadId
0x14019f546  nop     dword ptr [rax+rax+00h]
0x14019f54b  mov     [rsp+0C0h+var_80], rdi
0x14019f550  mov     r9d, 3
0x14019f556  mov     [rsp+0C0h+var_88], eax
0x14019f55a  xor     r8d, r8d
0x14019f55d  lea     rax, aServerCheckcon_0; "SERVER_CheckConnectivity"
0x14019f564  mov     [rsp+0C0h+var_90], 1E3h
0x14019f56c  mov     [rsp+0C0h+var_98], rax
0x14019f571  mov     edx, 2342h
0x14019f576  lea     rax, aBaseFsRemotefs_11; "base\\fs\\remotefs\\frs\\src\\transport"...
0x14019f57d  mov     [rsp+0C0h+var_A0], rax
0x14019f582  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14019f587  mov     [rbp+57h+var_58], rax
0x14019f58b  mov     rsi, rax
0x14019f58e  test    rax, rax
0x14019f591  jnz     loc_14019F70B
0x14019f597  lea     rcx, [rbx+280h]; this
0x14019f59e  call    ?Get@BoolParam@Config@@QEBA?BHXZ; Config::BoolParam::Get(void)
0x14019f5a3  test    eax, eax
0x14019f5a5  jz      loc_14019F651
0x14019f5ab  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14019f5b2  test    rax, rax
0x14019f5b5  jz      short loc_14019F5F9
0x14019f5b7  cmp     [rax+40h], edi
0x14019f5ba  jz      short loc_14019F5F9
0x14019f5bc  cmp     [rax+38h], r13d
0x14019f5c0  jl      short loc_14019F5F9
0x14019f5c2  lea     rax, aServerCheckcon; "SERVER_CheckConnectivity"
0x14019f5c9  mov     [rbp+57h+var_68], 1EBh
0x14019f5d0  mov     [rbp+57h+var_70], rax
0x14019f5d4  lea     rdx, aServerIsNotCon; "Server is not connection's outbound par"...
0x14019f5db  lea     rax, aSrtr; "SRTR"
0x14019f5e2  mov     [rbp+57h+var_64], r13d
0x14019f5e6  mov     r9, r14
0x14019f5e9  mov     [rbp+57h+var_60], rax
0x14019f5ed  mov     r8, r15
0x14019f5f0  lea     rcx, [rbp+57h+var_70]
0x14019f5f4  call    ??$DbgPrint@GU_GUID@@U1@@dbgobj@@QEAA_KPEBGAEBU_GUID@@1@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID>(ushort const *,_GUID const &,_GUID const &)
0x14019f5f9  call    cs:__imp_GetCurrentThreadId
0x14019f600  nop     dword ptr [rax+rax+00h]
0x14019f605  mov     [rsp+0C0h+var_80], rdi
0x14019f60a  mov     r9d, 3
0x14019f610  mov     [rsp+0C0h+var_88], eax
0x14019f614  xor     r8d, r8d
0x14019f617  lea     rax, aServerCheckcon_0; "SERVER_CheckConnectivity"
0x14019f61e  mov     [rsp+0C0h+var_90], 1EFh
0x14019f626  mov     [rsp+0C0h+var_98], rax
0x14019f62b  mov     edx, 2342h
0x14019f630  lea     rax, aBaseFsRemotefs_11; "base\\fs\\remotefs\\frs\\src\\transport"...
0x14019f637  mov     [rsp+0C0h+var_A0], rax
0x14019f63c  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14019f641  mov     [rbp+57h+var_58], rax
0x14019f645  mov     rsi, rax
0x14019f648  test    rax, rax
0x14019f64b  jnz     loc_14019F70B
0x14019f651  lea     rcx, [rbx+258h]; this
0x14019f658  call    ?Get@BoolParam@Config@@QEBA?BHXZ; Config::BoolParam::Get(void)
0x14019f65d  test    eax, eax
0x14019f65f  jnz     loc_14019F79A
0x14019f665  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14019f66c  test    rax, rax
0x14019f66f  jz      short loc_14019F6B3
0x14019f671  cmp     [rax+40h], edi
0x14019f674  jz      short loc_14019F6B3
0x14019f676  cmp     [rax+38h], r13d
0x14019f67a  jl      short loc_14019F6B3
0x14019f67c  lea     rax, aServerCheckcon; "SERVER_CheckConnectivity"
0x14019f683  mov     [rbp+57h+var_68], 1F6h
0x14019f68a  mov     [rbp+57h+var_70], rax
0x14019f68e  lea     rdx, aConnectionIsDi; "Connection is disabled. connId:%? rgd:%"...
0x14019f695  lea     rax, aSrtr; "SRTR"
0x14019f69c  mov     [rbp+57h+var_64], r13d
0x14019f6a0  mov     r9, r14
0x14019f6a3  mov     [rbp+57h+var_60], rax
0x14019f6a7  mov     r8, r15
0x14019f6aa  lea     rcx, [rbp+57h+var_70]
0x14019f6ae  call    ??$DbgPrint@GU_GUID@@U1@@dbgobj@@QEAA_KPEBGAEBU_GUID@@1@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID>(ushort const *,_GUID const &,_GUID const &)
0x14019f6b3  call    cs:__imp_GetCurrentThreadId
0x14019f6ba  nop     dword ptr [rax+rax+00h]
0x14019f6bf  mov     [rsp+0C0h+var_80], rdi
0x14019f6c4  lea     rbx, aServerCheckcon_0; "SERVER_CheckConnectivity"
0x14019f6cb  mov     [rsp+0C0h+var_88], eax
0x14019f6cf  mov     r9d, 3
0x14019f6d5  mov     [rsp+0C0h+var_90], 1F8h
0x14019f6dd  lea     rax, aBaseFsRemotefs_11; "base\\fs\\remotefs\\frs\\src\\transport"...
0x14019f6e4  mov     [rsp+0C0h+var_98], rbx
0x14019f6e9  xor     r8d, r8d
0x14019f6ec  mov     edx, 2342h
0x14019f6f1  mov     [rsp+0C0h+var_A0], rax
0x14019f6f6  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14019f6fb  mov     [rbp+57h+var_58], rax
0x14019f6ff  mov     rsi, rax
0x14019f702  test    rax, rax
0x14019f705  jz      loc_14019F7A1
0x14019f70b  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14019f712  test    rax, rax
0x14019f715  jz      short loc_14019F75E
0x14019f717  cmp     [rax+40h], edi
0x14019f71a  jz      short loc_14019F75E
0x14019f71c  cmp     [rax+38h], r13d
0x14019f720  jl      short loc_14019F75E
0x14019f722  lea     rax, aServerCheckcon; "SERVER_CheckConnectivity"
0x14019f729  mov     [rbp+57h+var_68], 21Eh
0x14019f730  mov     [rbp+57h+var_70], rax
0x14019f734  lea     rdx, aNotReadyToEsta; "Not ready to establish connection. conn"...
0x14019f73b  lea     rax, aSrtr; "SRTR"
0x14019f742  mov     [rbp+57h+var_64], r13d
0x14019f746  mov     r9, r14
0x14019f749  mov     [rbp+57h+var_60], rax
0x14019f74d  mov     r8, r15
0x14019f750  mov     [rsp+0C0h+var_A0], rsi
0x14019f755  lea     rcx, [rbp+57h+var_70]
0x14019f759  call    ??$DbgPrint@GU_GUID@@U1@VFrsStatus@@@dbgobj@@QEAA_KPEBGAEBU_GUID@@1AEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID,FrsStatus>(ushort const *,_GUID const &,_GUID const &,FrsStatus const &)
0x14019f75e  mov     edi, [rsi+4]
0x14019f761  lea     rcx, [rbp+57h+var_58]; struct FrsStatus **
0x14019f765  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x14019f76a  lea     rcx, [rbp+57h+var_48]
0x14019f76e  call    ??1?$ScopedRef@VReplicaSet@Config@@@@QEAA@XZ; ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(void)
0x14019f773  lea     rcx, [rbp+57h+var_50]
0x14019f777  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x14019f77c  mov     rbx, [rsp+0C0h+arg_0]
0x14019f784  mov     eax, edi
0x14019f786  add     rsp, 90h
0x14019f78d  pop     r15
0x14019f78f  pop     r14
0x14019f791  pop     r13
0x14019f793  pop     r12
0x14019f795  pop     rdi
0x14019f796  pop     rsi
0x14019f797  pop     rbp
0x14019f798  retn
0x14019f79a  lea     rbx, aServerCheckcon_0; "SERVER_CheckConnectivity"
0x14019f7a1  movups  xmm0, xmmword ptr [r12+88h]
0x14019f7aa  lea     r8, [rbp+57h+var_40]; struct _GUID *
0x14019f7ae  mov     rdx, r14; struct _GUID *
0x14019f7b1  movdqu  xmmword ptr [rbp+57h+var_40.Data1], xmm0
0x14019f7b6  call    ?FindReplicaSetManager@NetworkGlobals@@QEAAPEAVReplicaSetManager@@AEBU_GUID@@0@Z; NetworkGlobals::FindReplicaSetManager(_GUID const &,_GUID const &)
0x14019f7bb  mov     rdx, rax
0x14019f7be  lea     rcx, [rbp+57h+var_50]
0x14019f7c2  call    ?Set@?$ScopedRef@VShutdownRestartTask@VolumeManager@@@@AEAAXPEAVShutdownRestartTask@VolumeManager@@@Z; ScopedRef<VolumeManager::ShutdownRestartTask>::Set(VolumeManager::ShutdownRestartTask *)
0x14019f7c7  cmp     [rbp+57h+var_50], rdi
0x14019f7cb  setnz   al
0x14019f7ce  test    al, al
0x14019f7d0  jnz     loc_14019F875
0x14019f7d6  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14019f7dd  test    rax, rax
0x14019f7e0  jz      short loc_14019F824
0x14019f7e2  cmp     [rax+40h], edi
0x14019f7e5  jz      short loc_14019F824
0x14019f7e7  cmp     [rax+38h], r13d
0x14019f7eb  jl      short loc_14019F824
0x14019f7ed  lea     rax, aServerCheckcon; "SERVER_CheckConnectivity"
0x14019f7f4  mov     [rbp+57h+var_68], 20Ch
0x14019f7fb  mov     [rbp+57h+var_70], rax
0x14019f7ff  lea     rdx, aNoReplicasetma; "No ReplicaSetManager registered to hand"...
0x14019f806  lea     rax, aSrtr; "SRTR"
0x14019f80d  mov     [rbp+57h+var_64], r13d
0x14019f811  mov     r9, r14
0x14019f814  mov     [rbp+57h+var_60], rax
0x14019f818  mov     r8, r15
0x14019f81b  lea     rcx, [rbp+57h+var_70]
0x14019f81f  call    ??$DbgPrint@GU_GUID@@U1@@dbgobj@@QEAA_KPEBGAEBU_GUID@@1@Z; dbgobj::DbgPrint<ushort,_GUID,_GUID>(ushort const *,_GUID const &,_GUID const &)
0x14019f824  call    cs:__imp_GetCurrentThreadId
0x14019f82b  nop     dword ptr [rax+rax+00h]
0x14019f830  mov     [rsp+0C0h+var_80], rdi
0x14019f835  mov     r9d, 3
0x14019f83b  mov     [rsp+0C0h+var_88], eax
0x14019f83f  xor     r8d, r8d
0x14019f842  mov     [rsp+0C0h+var_90], 211h
0x14019f84a  lea     rax, aBaseFsRemotefs_11; "base\\fs\\remotefs\\frs\\src\\transport"...
0x14019f851  mov     [rsp+0C0h+var_98], rbx
0x14019f856  mov     edx, 2342h
0x14019f85b  mov     [rsp+0C0h+var_A0], rax
0x14019f860  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14019f865  mov     [rbp+57h+var_58], rax
0x14019f869  mov     rsi, rax
0x14019f86c  test    rax, rax
0x14019f86f  jnz     loc_14019F70B
0x14019f875  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14019f87c  test    rax, rax
0x14019f87f  jz      loc_14019F76A
  ... truncated ...
```
