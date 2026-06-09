# InitializeFileTransferAsyncState::ProcessIoCompletion(void)

- ea: `0x14019e040`
- end: `0x14019e9dd`
- name: `?ProcessIoCompletion@InitializeFileTransferAsyncState@@UEAAXXZ`
- size: `2461`
- prototype: `void __fastcall(InitializeFileTransferAsyncState *__hidden this)`
- caller_count: `0`
- callee_count: `26`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1400036a0`
- `0x1400036d0`
- `0x1400046cc`
- `0x14000e34c`
- `0x14002a15c`
- `0x14002c2f4`
- `0x1400391c4`
- `0x1400888ac`
- `0x140088c6c`
- `0x140124344`
- `0x1401989a4`
- `0x140199414`
- `0x140199c84`
- `0x14019b164`
- `0x14019b2d4`
- `0x14019b3e4`
- `0x14019b4cc`
- `0x14019e040`
- `0x14019ef58`
- `0x1401a0f50`
- `0x1401b0928`
- `0x1401b12fc`
- `0x1401b30b0`
- `0x1401b3a04`
- `0x1401b9494`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14019e130`
- `KERNEL32!GetCurrentThreadId` at `0x14019e1c2`
- `KERNEL32!GetCurrentThreadId` at `0x14019e2c1`
- `KERNEL32!GetCurrentThreadId` at `0x14019e3aa`
- `KERNEL32!GetCurrentThreadId` at `0x14019e40d`
- `KERNEL32!GetCurrentThreadId` at `0x14019e47d`
- `KERNEL32!GetCurrentThreadId` at `0x14019e4ed`
- `KERNEL32!GetCurrentThreadId` at `0x14019e556`
- `KERNEL32!GetCurrentThreadId` at `0x14019e130`
- `KERNEL32!GetCurrentThreadId` at `0x14019e1c2`
- `KERNEL32!GetCurrentThreadId` at `0x14019e2c1`
- `KERNEL32!GetCurrentThreadId` at `0x14019e3aa`
- `KERNEL32!GetCurrentThreadId` at `0x14019e40d`
- `KERNEL32!GetCurrentThreadId` at `0x14019e47d`
- `KERNEL32!GetCurrentThreadId` at `0x14019e4ed`
- `KERNEL32!GetCurrentThreadId` at `0x14019e556`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14019e8c3`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14019e8f7`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14019e8c3`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14019e8f7`

## string_xrefs

- `0x14019e0f5`: `InitializeFileTransferAsyncState::ProcessIoCompletion`
- `0x14019e2de`: `InitializeFileTransferAsyncState::ProcessIoCompletion`
- `0x14019e318`: `InitializeFileTransferAsyncState::ProcessIoCompletion`
- `0x14019e50a`: `InitializeFileTransferAsyncState::ProcessIoCompletion`
- `0x14019e573`: `InitializeFileTransferAsyncState::ProcessIoCompletion`
- `0x14019e2b0`: `Invalid Boolean argument value detected in frsUpdate. connId:%? rdc:%d uid:%? gsvn:%? ptr:%p`
- `0x14019e0a1`: `InitializeFileTransferAsyncState::ProcessIoCompletion`
- `0x14019e25b`: `InitializeFileTransferAsyncState::ProcessIoCompletion`
- `0x14019e344`: `InitializeFileTransferAsyncState::ProcessIoCompletion`
- `0x14019e6e8`: `InitializeFileTransferAsyncState::ProcessIoCompletion`
- `0x14019e749`: `InitializeFileTransferAsyncState::ProcessIoCompletion`
- `0x14019e7f7`: `InitializeFileTransferAsyncState::ProcessIoCompletion`
- `0x14019e922`: `InitializeFileTransferAsyncState::ProcessIoCompletion`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall InitializeFileTransferAsyncState::ProcessIoCompletion(InitializeFileTransferAsyncState *this)
{
  struct UpstreamTransport *v2; // rbx
  DWORD v3; // eax
  __int64 v4; // rcx
  struct FrsStatus *v5; // rax
  NetworkGlobals *v6; // rcx
  struct FrsStatus *v7; // rsi
  struct FrsStatus *v8; // r14
  DWORD CurrentThreadId; // eax
  __int64 v10; // rcx
  const struct _FRS_UPDATE *v11; // rdx
  _DWORD *v12; // rax
  DWORD v13; // eax
  __int64 v14; // rcx
  DWORD v15; // eax
  __int64 v16; // rcx
  DWORD v17; // eax
  __int64 v18; // rcx
  UpstreamTransport *UpstreamTransport; // rax
  unsigned __int64 v20; // r8
  DWORD v21; // eax
  __int64 v22; // rcx
  struct FRS_SERVER_CONTEXT *v23; // r14
  DWORD v24; // eax
  __int64 v25; // rcx
  void *v26; // r15
  DWORD v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rdx
  unsigned __int64 v31; // r8
  int v32; // edx
  __int64 v33; // rax
  _QWORD *v34; // rcx
  int v35; // edx
  struct FrsStatus *v36; // [rsp+68h] [rbp-A0h] BYREF
  struct FRS_SERVER_CONTEXT *v37; // [rsp+70h] [rbp-98h] BYREF
  const wchar_t *v38; // [rsp+78h] [rbp-90h] BYREF
  int v39; // [rsp+80h] [rbp-88h]
  int v40; // [rsp+84h] [rbp-84h]
  const wchar_t *v41; // [rsp+88h] [rbp-80h]
  int Reply; // [rsp+90h] [rbp-78h] BYREF
  RPC_STATUS v43; // [rsp+94h] [rbp-74h] BYREF
  InitializeFileTransferAsyncState *v44; // [rsp+98h] [rbp-70h] BYREF
  InitializeFileTransferAsyncState *v45; // [rsp+A0h] [rbp-68h] BYREF
  UpstreamTransport *v46; // [rsp+A8h] [rbp-60h] BYREF
  InitializeFileTransferAsyncState *v47; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v48; // [rsp+B8h] [rbp-50h] BYREF
  const wchar_t *v49; // [rsp+C0h] [rbp-48h] BYREF
  int v50; // [rsp+C8h] [rbp-40h]
  int v51; // [rsp+CCh] [rbp-3Ch]
  const wchar_t *v52; // [rsp+D0h] [rbp-38h]
  __int128 v53; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v54; // [rsp+E8h] [rbp-20h]
  __int128 v55; // [rsp+F0h] [rbp-18h] BYREF
  __int64 v56; // [rsp+100h] [rbp-8h]
  __int128 v57; // [rsp+120h] [rbp+18h]
  __int64 v58; // [rsp+154h] [rbp+4Ch]
  char v59; // [rsp+170h] [rbp+68h]
  _BYTE v60[532]; // [rsp+174h] [rbp+6Ch] BYREF

  memset_0(&v53, 0, 0x2A8u);
  v58 = 3;
  Reply = 0;
  v2 = 0;
  v46 = 0;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    v49 = L"InitializeFileTransferAsyncState::ProcessIoCompletion";
    v50 = 2774;
    v51 = 5;
    v52 = L"SRTR";
    v44 = this;
    dbgobj::DbgPrint<unsigned short,unsigned __int64>(&v49, L"%p", &v44);
  }
  if ( *((_QWORD *)this + 8)
    && *((_QWORD *)this + 11)
    && *((_QWORD *)this + 12)
    && *((_QWORD *)this + 13)
    && *((_QWORD *)this + 15)
    && *((_QWORD *)this + 16)
    || (v3 = GetCurrentThreadId(),
        v5 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                   v4,
                                   87,
                                   0,
                                   1,
                                   "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                   "InitializeFileTransferAsyncState::ProcessIoCompletion",
                                   2785,
                                   v3,
                                   0),
        v7 = v5,
        v36 = v5,
        (v8 = v5) == 0) )
  {
    **((_QWORD **)this + 11) = 0;
    **((_QWORD **)this + 12) = 0;
    **((_DWORD **)this + 15) = 0;
    **((_DWORD **)this + 16) = 0;
    v5 = InitializeFileTransferAsyncState::TestCancel(this);
    v7 = v5;
    v36 = v5;
    v8 = v5;
    if ( !v5 )
    {
      v6 = (NetworkGlobals *)isInBackupRestore;
      if ( isInBackupRestore )
      {
        if ( *isInBackupRestore )
        {
          CurrentThreadId = GetCurrentThreadId();
          v5 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                     v10,
                                     9036,
                                     0,
                                     3,
                                     "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                     "InitializeFileTransferAsyncState::ProcessIoCompletion",
                                     2805,
                                     CurrentThreadId,
                                     0);
          v7 = v5;
          v36 = v5;
          v8 = v5;
        }
      }
    }
  }
  v11 = (const struct _FRS_UPDATE *)*((_QWORD *)this + 8);
  if ( v11 )
  {
    ID_UPDATE::Set((ID_UPDATE *)&v53, v11);
    v5 = v8;
  }
  if ( !v5 )
  {
    v12 = (_DWORD *)*((_QWORD *)this + 8);
    if ( *v12 <= 1u && v12[1] <= 1u )
      goto LABEL_82;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v38 = L"InitializeFileTransferAsyncState::ProcessIoCompletion";
      v39 = 2822;
      v40 = 4;
      v41 = L"SRTR";
      v36 = this;
      LODWORD(v37) = *((_DWORD *)this + 18);
      dbgobj::DbgPrint<unsigned short,_GUID,unsigned long,UID,GVSN,unsigned __int64>(
        (unsigned int)&v38,
        (unsigned int)L"Invalid Boolean argument value detected in frsUpdate. connId:%? rdc:%d uid:%? gsvn:%? ptr:%p",
        (_DWORD)this + 48,
        (unsigned int)&v37,
        (__int64)&v53,
        (__int64)&v55,
        (__int64)&v36);
    }
    v13 = GetCurrentThreadId();
    v7 = (struct FrsStatus *)FrsStatusList::PushNewError(
                               v14,
                               87,
                               0,
                               1,
                               "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                               "InitializeFileTransferAsyncState::ProcessIoCompletion",
                               2830,
                               v13,
                               0);
    v36 = v7;
    if ( !v7 )
    {
LABEL_82:
      if ( **((_DWORD **)this + 10) <= 2u )
        goto LABEL_83;
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v38 = L"InitializeFileTransferAsyncState::ProcessIoCompletion";
        v39 = 2840;
        v40 = 4;
        v41 = L"SRTR";
        v36 = this;
        LODWORD(v37) = *((_DWORD *)this + 18);
        dbgobj::DbgPrint<unsigned short,_GUID,unsigned long,UID,GVSN,unsigned __int64>(
          (unsigned int)&v38,
          (unsigned int)L"Invalid staging policy. connId:%? rdc:%d uid:%? gsvn:%? ptr:%p",
          (_DWORD)this + 48,
          (unsigned int)&v37,
          (__int64)&v53,
          (__int64)&v55,
          (__int64)&v36);
      }
      v15 = GetCurrentThreadId();
      v7 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v16,
                                 87,
                                 0,
                                 1,
                                 "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                 "InitializeFileTransferAsyncState::ProcessIoCompletion",
                                 2847,
                                 v15,
                                 0);
      v36 = v7;
      if ( !v7 )
      {
LABEL_83:
        if ( Settings::GhostingEnabled
          || (v59 & 8) == 0 && (v59 & 4) == 0
          || (v17 = GetCurrentThreadId(),
              v7 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                         v18,
                                         9305,
                                         0,
                                         3,
                                         "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                         "InitializeFileTransferAsyncState::ProcessIoCompletion",
                                         2856,
                                         v17,
                                         0),
              (v36 = v7) == 0) )
        {
          UpstreamTransport = NetworkGlobals::FindUpstreamTransport(
                                v6,
                                *((void **)this + 4),
                                (const struct _GUID *)this + 3);
          v2 = UpstreamTransport;
          v46 = UpstreamTransport;
          if ( UpstreamTransport )
          {
            UpstreamTransport::CountBytes(UpstreamTransport, 0x2C8u, v20);
          }
          else
          {
            v21 = GetCurrentThreadId();
            v7 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                       v22,
                                       9026,
                                       0,
                                       3,
                                       "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                       "InitializeFileTransferAsyncState::ProcessIoCompletion",
                                       2869,
                                       v21,
                                       0);
            v36 = v7;
          }
        }
      }
    }
  }
  if ( v7 )
    goto LABEL_72;
  v23 = NetworkGlobals::ReserveFileTransfer(v6, (const struct _GUID *)this + 3, v2, (struct ID_UPDATE *)&v53);
  if ( !v23 )
  {
    v24 = GetCurrentThreadId();
    v7 = (struct FrsStatus *)FrsStatusList::PushNewError(
                               v25,
                               9078,
                               0,
                               3,
                               "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                               "InitializeFileTransferAsyncState::ProcessIoCompletion",
                               2886,
                               v24,
                               0);
    v36 = v7;
    if ( v7 )
      goto LABEL_72;
  }
  v26 = operator new(0x240u);
  if ( !v26 )
  {
    v27 = GetCurrentThreadId();
    v7 = (struct FrsStatus *)FrsStatusList::PushNewError(
                               v28,
                               14,
                               0,
                               1,
                               "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                               "InitializeFileTransferAsyncState::ProcessIoCompletion",
                               2895,
                               v27,
                               0);
    v36 = v7;
    if ( v7 )
      goto LABEL_72;
  }
  memset_0(v26, 0, 0x240u);
  Rdc::MyFRS_RDC_FILEINFO::Reset((Rdc::MyFRS_RDC_FILEINFO *)v26);
  *((_OWORD *)v23 + 6) = v55;
  *((_QWORD *)v23 + 14) = v56;
  *(_OWORD *)((char *)v23 + 72) = v53;
  *((_QWORD *)v23 + 11) = v54;
  *((_OWORD *)v23 + 2) = v57;
  **((_QWORD **)this + 11) = v23;
  **((_QWORD **)this + 12) = v26;
  v37 = v23;
  RefCountObject::AddRef(v23);
  v7 = (struct FrsStatus *)UpstreamTransport::OpenFile(
                             (_DWORD)v2,
                             *((_DWORD *)this + 18),
                             (unsigned int)&v53,
                             *((_QWORD *)this + 10),
                             (__int64)v26,
                             (__int64)&v37,
                             0,
                             0);
  v36 = v7;
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v37);
  ID_UPDATE::Get((ID_UPDATE *)&v53, *((struct _FRS_UPDATE **)this + 8));
  if ( v7 )
    goto LABEL_72;
  v7 = InitializeFileTransferAsyncState::TestCancel(this);
  v36 = v7;
  if ( v7 )
    goto LABEL_72;
  v29 = *((_QWORD *)v23 + 40);
  if ( v29 )
  {
    if ( (v59 & 1) != 0 )
    {
      v7 = (struct FrsStatus *)(*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v29 + 8LL))(
                                 v29,
                                 *((_QWORD *)this + 13),
                                 *((unsigned int *)this + 28),
                                 *((_QWORD *)this + 15));
      v36 = v7;
      **((_DWORD **)this + 16) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v23 + 40) + 24LL))(*((_QWORD *)v23 + 40));
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        v38 = L"InitializeFileTransferAsyncState::ProcessIoCompletion";
        v39 = 2960;
        v40 = 5;
        v41 = L"SRTR";
        dbgobj::DbgPrint<unsigned short,unsigned short [261],unsigned long>(&v38, v30, v60, *((_QWORD *)this + 15));
      }
      UpstreamTransport::CountBytes(v2, **((unsigned int **)this + 15), v31);
    }
    else
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        v38 = L"InitializeFileTransferAsyncState::ProcessIoCompletion";
        v39 = 2972;
        v40 = 5;
        v41 = L"SRTR";
        dbgobj::DbgPrint<unsigned short,GVSN>(&v38, L"Tombstone %?", &v53);
      }
      **((_DWORD **)this + 16) = 1;
      **((_DWORD **)this + 15) = 0;
    }
    if ( **((_DWORD **)this + 16) )
    {
      SERVER_RdcClose(*((_QWORD *)this + 11));
      v23 = 0;
    }
    if ( v7 )
      goto LABEL_72;
  }
  v7 = InitializeFileTransferAsyncState::TestCancel(this);
  v36 = v7;
  if ( v7 )
  {
LABEL_72:
    v34 = (_QWORD *)*((_QWORD *)this + 11);
    if ( *v34 )
      SERVER_RdcClose(v34);
    Reply = *((_DWORD *)v7 + 1);
    v43 = RpcAsyncCompleteCall(*((PRPC_ASYNC_STATE *)this + 5), &Reply);
    *((_QWORD *)this + 5) = 0;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v38 = L"InitializeFileTransferAsyncState::ProcessIoCompletion";
      v39 = 3013;
      v40 = 3;
      v41 = L"SRTR";
      v45 = this;
      LODWORD(v37) = *((_DWORD *)this + 18);
      dbgobj::DbgPrint<unsigned short,_GUID,unsigned long,UID,GVSN,unsigned long,unsigned __int64,FrsStatus>(
        (unsigned int)&v38,
        v35,
        (_DWORD)this + 48,
        (unsigned int)&v37,
        (__int64)&v53,
        (__int64)&v55,
        (__int64)&v43,
        (__int64)&v45,
        (__int64)v7);
    }
    CLEAR_ERROR(&v36);
  }
  else
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v38 = L"InitializeFileTransferAsyncState::ProcessIoCompletion";
      v39 = 3027;
      v40 = 4;
      v41 = L"SRTR";
      v44 = (InitializeFileTransferAsyncState *)**((_QWORD **)this + 11);
      v47 = this;
      if ( v23 )
      {
        v36 = (struct FrsStatus *)*((_QWORD *)v23 + 40);
        v33 = *((_QWORD *)v23 + 39);
      }
      else
      {
        v36 = 0;
        v33 = 0;
      }
      v48 = v33;
      v45 = v23;
      LODWORD(v37) = *((_DWORD *)this + 18);
      dbgobj::DbgPrint<unsigned short,_GUID,unsigned long,unsigned __int64,unsigned __int64,unsigned __int64,UID,GVSN,unsigned __int64,unsigned __int64>(
        (unsigned int)&v38,
        v32,
        (_DWORD)this + 48,
        (unsigned int)&v37,
        (__int64)&v45,
        (__int64)&v48,
        (__int64)&v36,
        (__int64)&v53,
        (__int64)&v55,
        (__int64)&v47,
        (__int64)&v44);
    }
    if ( v23 )
      FRS_SERVER_CONTEXT::SetIdle(v23);
    v43 = RpcAsyncCompleteCall(*((PRPC_ASYNC_STATE *)this + 5), &Reply);
    *((_QWORD *)this + 5) = 0;
  }
  RefCountObject::Release(this);
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v46);
}

```

## disassembly

```asm
0x14019e040  mov     rax, rsp
0x14019e043  mov     [rax+10h], rbx
0x14019e047  mov     [rax+18h], rsi
0x14019e04b  mov     [rax+20h], rdi
0x14019e04f  push    rbp
0x14019e050  push    r12
0x14019e052  push    r13
0x14019e054  push    r14
0x14019e056  push    r15
0x14019e058  lea     rbp, [rax-2B8h]
0x14019e05f  sub     rsp, 390h
0x14019e066  mov     rax, cs:__security_cookie
0x14019e06d  xor     rax, rsp
0x14019e070  mov     [rbp+2B0h+var_30], rax
0x14019e077  mov     rdi, rcx
0x14019e07a  xor     edx, edx; Val
0x14019e07c  mov     r8d, 2A8h; Size
0x14019e082  lea     rcx, [rbp+2B0h+var_2E0]; void *
0x14019e086  call    memset_0
0x14019e08b  mov     [rbp+2B0h+var_264], 3
0x14019e093  xor     r12d, r12d
0x14019e096  mov     [rbp+2B0h+Reply], r12d
0x14019e09a  mov     ebx, r12d
0x14019e09d  mov     [rbp+2B0h+var_310], rbx
0x14019e0a1  lea     rcx, aInitializefile_2; "InitializeFileTransferAsyncState::Proce"...
0x14019e0a8  lea     rdx, aSrtr; "SRTR"
0x14019e0af  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14019e0b6  test    rax, rax
0x14019e0b9  jz      short loc_14019E0F5
0x14019e0bb  cmp     [rax+40h], r12d
0x14019e0bf  jz      short loc_14019E0F5
0x14019e0c1  cmp     dword ptr [rax+38h], 5
0x14019e0c5  jl      short loc_14019E0F5
0x14019e0c7  mov     [rbp+2B0h+var_2F8], rcx
0x14019e0cb  mov     [rbp+2B0h+var_2F0], 0AD6h
0x14019e0d2  mov     [rbp+2B0h+var_2EC], 5
0x14019e0d9  mov     [rbp+2B0h+var_2E8], rdx
0x14019e0dd  mov     [rbp+2B0h+var_320], rdi
0x14019e0e1  lea     r8, [rbp+2B0h+var_320]
0x14019e0e5  lea     rdx, aP; "%p"
0x14019e0ec  lea     rcx, [rbp+2B0h+var_2F8]
0x14019e0f0  call    ??$DbgPrint@G_K@dbgobj@@QEAA_KPEBGAEB_K@Z; dbgobj::DbgPrint<ushort,unsigned __int64>(ushort const *,unsigned __int64 const &)
0x14019e0f5  lea     r13, aInitializefile_3; "InitializeFileTransferAsyncState::Proce"...
0x14019e0fc  lea     rsi, aBaseFsRemotefs_11; "base\\fs\\remotefs\\frs\\src\\transport"...
0x14019e103  mov     r15d, 1
0x14019e109  cmp     [rdi+40h], r12
0x14019e10d  jz      short loc_14019E130
0x14019e10f  cmp     [rdi+58h], r12
0x14019e113  jz      short loc_14019E130
0x14019e115  cmp     [rdi+60h], r12
0x14019e119  jz      short loc_14019E130
0x14019e11b  cmp     [rdi+68h], r12
0x14019e11f  jz      short loc_14019E130
0x14019e121  cmp     [rdi+78h], r12
0x14019e125  jz      short loc_14019E130
0x14019e127  cmp     [rdi+80h], r12
0x14019e12e  jnz     short loc_14019E17A
0x14019e130  call    cs:__imp_GetCurrentThreadId
0x14019e137  nop     dword ptr [rax+rax+00h]
0x14019e13c  mov     [rsp+3B0h+var_370], r12
0x14019e141  mov     dword ptr [rsp+3B0h+var_378], eax
0x14019e145  mov     dword ptr [rsp+3B0h+var_380], 0AE1h
0x14019e14d  mov     [rsp+3B0h+var_388], r13
0x14019e152  mov     [rsp+3B0h+var_390], rsi
0x14019e157  mov     r9d, r15d
0x14019e15a  xor     r8d, r8d
0x14019e15d  lea     edx, [r8+57h]
0x14019e161  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14019e166  mov     rsi, rax
0x14019e169  mov     [rsp+3B0h+var_350], rax
0x14019e16e  mov     r14, rax
0x14019e171  test    rax, rax
0x14019e174  jnz     loc_14019E20C
0x14019e17a  mov     rax, [rdi+58h]
0x14019e17e  mov     [rax], r12
0x14019e181  mov     rax, [rdi+60h]
0x14019e185  mov     [rax], r12
0x14019e188  mov     rax, [rdi+78h]
0x14019e18c  mov     [rax], r12d
0x14019e18f  mov     rax, [rdi+80h]
0x14019e196  mov     [rax], r12d
0x14019e199  mov     rcx, rdi; this
0x14019e19c  call    ?TestCancel@InitializeFileTransferAsyncState@@AEAAPEAVFrsStatus@@XZ; InitializeFileTransferAsyncState::TestCancel(void)
0x14019e1a1  mov     rsi, rax
0x14019e1a4  mov     [rsp+3B0h+var_350], rax
0x14019e1a9  mov     r14, rax
0x14019e1ac  test    rax, rax
0x14019e1af  jnz     short loc_14019E20C
0x14019e1b1  mov     rcx, cs:?isInBackupRestore@@3PEAHEA; int * isInBackupRestore
0x14019e1b8  test    rcx, rcx
0x14019e1bb  jz      short loc_14019E20C
0x14019e1bd  cmp     [rcx], r12d
0x14019e1c0  jz      short loc_14019E20C
0x14019e1c2  call    cs:__imp_GetCurrentThreadId
0x14019e1c9  nop     dword ptr [rax+rax+00h]
0x14019e1ce  mov     [rsp+3B0h+var_370], r12
0x14019e1d3  mov     dword ptr [rsp+3B0h+var_378], eax
0x14019e1d7  mov     dword ptr [rsp+3B0h+var_380], 0AF5h
0x14019e1df  mov     [rsp+3B0h+var_388], r13
0x14019e1e4  lea     rax, aBaseFsRemotefs_11; "base\\fs\\remotefs\\frs\\src\\transport"...
0x14019e1eb  mov     [rsp+3B0h+var_390], rax
0x14019e1f0  lea     r9d, [r14+3]
0x14019e1f4  xor     r8d, r8d
0x14019e1f7  mov     edx, 234Ch
0x14019e1fc  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14019e201  mov     rsi, rax
0x14019e204  mov     [rsp+3B0h+var_350], rax
0x14019e209  mov     r14, rax
0x14019e20c  mov     rdx, [rdi+40h]; struct _FRS_UPDATE *
0x14019e210  test    rdx, rdx
0x14019e213  jz      short loc_14019E221
0x14019e215  lea     rcx, [rbp+2B0h+var_2E0]; this
0x14019e219  call    ?Set@ID_UPDATE@@QEAAXAEBU_FRS_UPDATE@@@Z; ID_UPDATE::Set(_FRS_UPDATE const &)
0x14019e21e  mov     rax, r14
0x14019e221  mov     r13d, 4
0x14019e227  test    rax, rax
0x14019e22a  jnz     loc_14019E4CC
0x14019e230  mov     rax, [rdi+40h]
0x14019e234  cmp     [rax], r15d
0x14019e237  ja      short loc_14019E243
0x14019e239  cmp     [rax+4], r15d
0x14019e23d  jbe     loc_14019E318
0x14019e243  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14019e24a  test    rax, rax
0x14019e24d  jz      short loc_14019E2C1
0x14019e24f  cmp     [rax+40h], r12d
0x14019e253  jz      short loc_14019E2C1
0x14019e255  cmp     [rax+38h], r13d
0x14019e259  jl      short loc_14019E2C1
0x14019e25b  lea     rax, aInitializefile_2; "InitializeFileTransferAsyncState::Proce"...
0x14019e262  mov     [rsp+3B0h+var_340], rax
0x14019e267  mov     [rsp+3B0h+var_338], 0B06h
0x14019e26f  mov     [rsp+3B0h+var_334], r13d
0x14019e274  lea     rax, aSrtr; "SRTR"
0x14019e27b  mov     [rbp+2B0h+var_330], rax
0x14019e27f  mov     [rsp+3B0h+var_350], rdi
0x14019e284  mov     eax, [rdi+48h]
0x14019e287  mov     dword ptr [rsp+3B0h+var_348], eax
0x14019e28b  lea     r8, [rdi+30h]
0x14019e28f  lea     rax, [rsp+3B0h+var_350]
0x14019e294  mov     [rsp+3B0h+var_380], rax
0x14019e299  lea     rax, [rbp+2B0h+var_2C8]
0x14019e29d  mov     [rsp+3B0h+var_388], rax
0x14019e2a2  lea     rax, [rbp+2B0h+var_2E0]
0x14019e2a6  mov     [rsp+3B0h+var_390], rax
0x14019e2ab  lea     r9, [rsp+3B0h+var_348]
0x14019e2b0  lea     rdx, aInvalidBoolean; "Invalid Boolean argument value detected"...
0x14019e2b7  lea     rcx, [rsp+3B0h+var_340]
0x14019e2bc  call    ??$DbgPrint@GU_GUID@@KVUID@@VGVSN@@_K@dbgobj@@QEAA_KPEBGAEBU_GUID@@AEBKAEBVUID@@AEBVGVSN@@AEB_K@Z; dbgobj::DbgPrint<ushort,_GUID,ulong,UID,GVSN,unsigned __int64>(ushort const *,_GUID const &,ulong const &,UID const &,GVSN const &,unsigned __int64 const &)
0x14019e2c1  call    cs:__imp_GetCurrentThreadId
0x14019e2c8  nop     dword ptr [rax+rax+00h]
0x14019e2cd  mov     [rsp+3B0h+var_370], r12
0x14019e2d2  mov     dword ptr [rsp+3B0h+var_378], eax
0x14019e2d6  mov     dword ptr [rsp+3B0h+var_380], 0B0Eh
0x14019e2de  lea     r14, aInitializefile_3; "InitializeFileTransferAsyncState::Proce"...
0x14019e2e5  mov     [rsp+3B0h+var_388], r14
0x14019e2ea  lea     rax, aBaseFsRemotefs_11; "base\\fs\\remotefs\\frs\\src\\transport"...
0x14019e2f1  mov     [rsp+3B0h+var_390], rax
0x14019e2f6  mov     r9d, r15d
0x14019e2f9  xor     r8d, r8d
0x14019e2fc  lea     edx, [r8+57h]
0x14019e300  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14019e305  mov     rsi, rax
0x14019e308  mov     [rsp+3B0h+var_350], rax
0x14019e30d  test    rax, rax
0x14019e310  jnz     loc_14019E4CC
0x14019e316  jmp     short loc_14019E31F
0x14019e318  lea     r14, aInitializefile_3; "InitializeFileTransferAsyncState::Proce"...
0x14019e31f  mov     rax, [rdi+50h]
0x14019e323  cmp     dword ptr [rax], 2
0x14019e326  jbe     loc_14019E3F8
0x14019e32c  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14019e333  test    rax, rax
0x14019e336  jz      short loc_14019E3AA
0x14019e338  cmp     [rax+40h], r12d
0x14019e33c  jz      short loc_14019E3AA
0x14019e33e  cmp     [rax+38h], r13d
0x14019e342  jl      short loc_14019E3AA
0x14019e344  lea     rax, aInitializefile_2; "InitializeFileTransferAsyncState::Proce"...
0x14019e34b  mov     [rsp+3B0h+var_340], rax
0x14019e350  mov     [rsp+3B0h+var_338], 0B18h
0x14019e358  mov     [rsp+3B0h+var_334], r13d
0x14019e35d  lea     rax, aSrtr; "SRTR"
0x14019e364  mov     [rbp+2B0h+var_330], rax
0x14019e368  mov     [rsp+3B0h+var_350], rdi
0x14019e36d  mov     eax, [rdi+48h]
0x14019e370  mov     dword ptr [rsp+3B0h+var_348], eax
0x14019e374  lea     r8, [rdi+30h]
0x14019e378  lea     rax, [rsp+3B0h+var_350]
0x14019e37d  mov     [rsp+3B0h+var_380], rax
0x14019e382  lea     rax, [rbp+2B0h+var_2C8]
0x14019e386  mov     [rsp+3B0h+var_388], rax
0x14019e38b  lea     rax, [rbp+2B0h+var_2E0]
0x14019e38f  mov     [rsp+3B0h+var_390], rax
0x14019e394  lea     r9, [rsp+3B0h+var_348]
0x14019e399  lea     rdx, aInvalidStaging; "Invalid staging policy. connId:%? rdc:%"...
0x14019e3a0  lea     rcx, [rsp+3B0h+var_340]
0x14019e3a5  call    ??$DbgPrint@GU_GUID@@KVUID@@VGVSN@@_K@dbgobj@@QEAA_KPEBGAEBU_GUID@@AEBKAEBVUID@@AEBVGVSN@@AEB_K@Z; dbgobj::DbgPrint<ushort,_GUID,ulong,UID,GVSN,unsigned __int64>(ushort const *,_GUID const &,ulong const &,UID const &,GVSN const &,unsigned __int64 const &)
0x14019e3aa  call    cs:__imp_GetCurrentThreadId
0x14019e3b1  nop     dword ptr [rax+rax+00h]
0x14019e3b6  mov     [rsp+3B0h+var_370], r12
0x14019e3bb  mov     dword ptr [rsp+3B0h+var_378], eax
0x14019e3bf  mov     dword ptr [rsp+3B0h+var_380], 0B1Fh
0x14019e3c7  mov     [rsp+3B0h+var_388], r14
0x14019e3cc  lea     rax, aBaseFsRemotefs_11; "base\\fs\\remotefs\\frs\\src\\transport"...
0x14019e3d3  mov     [rsp+3B0h+var_390], rax
0x14019e3d8  mov     r9d, r15d
0x14019e3db  xor     r8d, r8d
0x14019e3de  lea     edx, [r8+57h]
0x14019e3e2  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14019e3e7  mov     rsi, rax
0x14019e3ea  mov     [rsp+3B0h+var_350], rax
0x14019e3ef  test    rax, rax
0x14019e3f2  jnz     loc_14019E4CC
0x14019e3f8  cmp     cs:?GhostingEnabled@Settings@@3VGenericBoolSetting@1@A, r12d; Settings::GenericBoolSetting Settings::GhostingEnabled
0x14019e3ff  jnz     short loc_14019E45D
0x14019e401  test    [rbp+2B0h+var_248], 8
0x14019e405  jnz     short loc_14019E40D
0x14019e407  test    [rbp+2B0h+var_248], r13b
0x14019e40b  jz      short loc_14019E45D
0x14019e40d  call    cs:__imp_GetCurrentThreadId
0x14019e414  nop     dword ptr [rax+rax+00h]
0x14019e419  mov     [rsp+3B0h+var_370], r12
0x14019e41e  mov     dword ptr [rsp+3B0h+var_378], eax
0x14019e422  mov     dword ptr [rsp+3B0h+var_380], 0B28h
0x14019e42a  mov     [rsp+3B0h+var_388], r14
0x14019e42f  lea     r15, aBaseFsRemotefs_11; "base\\fs\\remotefs\\frs\\src\\transport"...
0x14019e436  mov     [rsp+3B0h+var_390], r15
0x14019e43b  mov     r9d, 3
0x14019e441  xor     r8d, r8d
0x14019e444  mov     edx, 2459h
0x14019e449  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14019e44e  mov     rsi, rax
0x14019e451  mov     [rsp+3B0h+var_350], rax
0x14019e456  test    rax, rax
0x14019e459  jnz     short loc_14019E4CC
0x14019e45b  jmp     short loc_14019E464
0x14019e45d  lea     r15, aBaseFsRemotefs_11; "base\\fs\\remotefs\\frs\\src\\transport"...
0x14019e464  lea     r8, [rdi+30h]; struct _GUID *
0x14019e468  mov     rdx, [rdi+20h]; void *
0x14019e46c  call    ?FindUpstreamTransport@NetworkGlobals@@QEAAPEAVUpstreamTransport@@PEAXAEBU_GUID@@@Z; NetworkGlobals::FindUpstreamTransport(void *,_GUID const &)
0x14019e471  mov     rbx, rax
0x14019e474  mov     [rbp+2B0h+var_310], rax
0x14019e478  test    rax, rax
0x14019e47b  jnz     short loc_14019E4BF
0x14019e47d  call    cs:__imp_GetCurrentThreadId
0x14019e484  nop     dword ptr [rax+rax+00h]
0x14019e489  mov     [rsp+3B0h+var_370], r12
0x14019e48e  mov     dword ptr [rsp+3B0h+var_378], eax
0x14019e492  mov     dword ptr [rsp+3B0h+var_380], 0B35h
0x14019e49a  mov     [rsp+3B0h+var_388], r14
0x14019e49f  mov     [rsp+3B0h+var_390], r15
0x14019e4a4  lea     r9d, [rbx+3]
0x14019e4a8  xor     r8d, r8d
0x14019e4ab  mov     edx, 2342h
0x14019e4b0  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14019e4b5  mov     rsi, rax
0x14019e4b8  mov     [rsp+3B0h+var_350], rax
0x14019e4bd  jmp     short loc_14019E4CC
0x14019e4bf  mov     edx, 2C8h; unsigned __int64
0x14019e4c4  mov     rcx, rax; this
0x14019e4c7  call    ?CountBytes@UpstreamTransport@@QEAAX_K0@Z; UpstreamTransport::CountBytes(unsigned __int64,unsigned __int64)
0x14019e4cc  test    rsi, rsi
0x14019e4cf  jnz     loc_14019E8DB
0x14019e4d5  lea     rdx, [rdi+30h]; struct _GUID *
0x14019e4d9  lea     r9, [rbp+2B0h+var_2E0]; struct ID_UPDATE *
0x14019e4dd  mov     r8, rbx; struct UpstreamTransport *
0x14019e4e0  call    ?ReserveFileTransfer@NetworkGlobals@@QEAAPEAVFRS_SERVER_CONTEXT@@AEBU_GUID@@PEAVUpstreamTransport@@AEAVID_UPDATE@@@Z; NetworkGlobals::ReserveFileTransfer(_GUID const &,UpstreamTransport *,ID_UPDATE &)
0x14019e4e5  mov     r14, rax
0x14019e4e8  test    rax, rax
0x14019e4eb  jnz     short loc_14019E544
0x14019e4ed  call    cs:__imp_GetCurrentThreadId
0x14019e4f4  nop     dword ptr [rax+rax+00h]
0x14019e4f9  mov     [rsp+3B0h+var_370], r12
0x14019e4fe  mov     dword ptr [rsp+3B0h+var_378], eax
0x14019e502  mov     dword ptr [rsp+3B0h+var_380], 0B46h
0x14019e50a  lea     rax, aInitializefile_3; "InitializeFileTransferAsyncState::Proce"...
0x14019e511  mov     [rsp+3B0h+var_388], rax
0x14019e516  lea     rax, aBaseFsRemotefs_11; "base\\fs\\remotefs\\frs\\src\\transport"...
0x14019e51d  mov     [rsp+3B0h+var_390], rax
0x14019e522  lea     r9d, [rsi+3]
0x14019e526  xor     r8d, r8d
0x14019e529  mov     edx, 2376h
0x14019e52e  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14019e533  mov     rsi, rax
0x14019e536  mov     [rsp+3B0h+var_350], rax
0x14019e53b  test    rax, rax
0x14019e53e  jnz     loc_14019E8DB
0x14019e544  mov     ecx, 240h; Size
0x14019e549  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14019e54e  mov     r15, rax
0x14019e551  test    rax, rax
0x14019e554  jnz     short loc_14019E5AC
0x14019e556  call    cs:__imp_GetCurrentThreadId
0x14019e55d  nop     dword ptr [rax+rax+00h]
0x14019e562  mov     [rsp+3B0h+var_370], r12
0x14019e567  mov     dword ptr [rsp+3B0h+var_378], eax
0x14019e56b  mov     dword ptr [rsp+3B0h+var_380], 0B4Fh
0x14019e573  lea     rax, aInitializefile_3; "InitializeFileTransferAsyncState::Proce"...
0x14019e57a  mov     [rsp+3B0h+var_388], rax
  ... truncated ...
```
