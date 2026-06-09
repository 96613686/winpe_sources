# RpcAsyncPipeState::Process(void)

- ea: `0x14019d558`
- end: `0x14019e02b`
- name: `?Process@RpcAsyncPipeState@@IEAAHXZ`
- size: `2771`
- prototype: `__int64 __fastcall(RpcAsyncPipeState *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14019e9f0`

## callees

- `0x14000d980`
- `0x14000dcc0`
- `0x14000e34c`
- `0x14002c2f4`
- `0x14002c548`
- `0x1400391c4`
- `0x1400c29b8`
- `0x1400c2fc4`
- `0x140175188`
- `0x1401985f8`
- `0x14019bcec`
- `0x14019c5d0`
- `0x14019d1d4`
- `0x14019d558`
- `0x14019ec50`
- `0x1401af7b0`
- `0x1401b0928`
- `0x1401b9494`
- `0x1401bda10`
- `0x140223010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14019d787`
- `KERNEL32!LeaveCriticalSection` at `0x14019d7cd`
- `KERNEL32!LeaveCriticalSection` at `0x14019d787`
- `KERNEL32!LeaveCriticalSection` at `0x14019d7cd`
- `KERNEL32!EnterCriticalSection` at `0x14019d7b7`
- `KERNEL32!EnterCriticalSection` at `0x14019d7b7`
- `KERNEL32!GetCurrentThreadId` at `0x14019dc30`
- `KERNEL32!GetCurrentThreadId` at `0x14019ddaf`
- `KERNEL32!GetCurrentThreadId` at `0x14019de5e`
- `KERNEL32!GetCurrentThreadId` at `0x14019dc30`
- `KERNEL32!GetCurrentThreadId` at `0x14019ddaf`
- `KERNEL32!GetCurrentThreadId` at `0x14019de5e`
- `RPCRT4!RpcAsyncAbortCall` at `0x14019da0d`
- `RPCRT4!RpcAsyncAbortCall` at `0x14019da96`
- `RPCRT4!RpcAsyncAbortCall` at `0x14019da0d`
- `RPCRT4!RpcAsyncAbortCall` at `0x14019da96`
- `RPCRT4!RpcServerTestCancel` at `0x14019d604`
- `RPCRT4!RpcServerTestCancel` at `0x14019d604`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14019d85f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14019d85f`

## string_xrefs

- `0x14019d82b`: `Completing this:%p`
- `0x14019d8cd`: `(Ignored) RpcAsyncComplete failed, this:%p RpcAsyncState:%p, status:%d`
- `0x14019d942`: `RpcAsyncComplete succeeded, this:%p reply:%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall RpcAsyncPipeState::Process(RpcAsyncPipeState *this)
{
  UpstreamTransport *v2; // rdi
  struct FrsStatus *DataPipe; // rsi
  unsigned __int8 *v4; // r8
  int v5; // r14d
  unsigned int v6; // r12d
  struct _RPC_ASYNC_STATE *v7; // r15
  const wchar_t *v8; // r9
  int v9; // r13d
  LPCRITICAL_SECTION v10; // rdx
  __int64 v11; // rcx
  RPC_STATUS v12; // eax
  int v13; // eax
  FRS_SERVER_CONTEXT *v14; // rdi
  struct _RPC_ASYNC_STATE **v15; // r9
  RpcAsyncPipeState **v16; // r8
  const wchar_t *v17; // rdx
  const wchar_t **v18; // rcx
  DWORD v19; // eax
  __int64 v20; // rcx
  unsigned __int64 v21; // r8
  unsigned __int64 v22; // rdx
  UpstreamTransport *v23; // rcx
  __int64 v24; // rdi
  DWORD CurrentThreadId; // eax
  unsigned int v26; // edi
  DWORD v27; // eax
  __int64 v28; // rcx
  unsigned int v29; // ecx
  const wchar_t *v31; // [rsp+50h] [rbp-B0h] BYREF
  int v32; // [rsp+58h] [rbp-A8h]
  int v33; // [rsp+5Ch] [rbp-A4h]
  const wchar_t *v34; // [rsp+60h] [rbp-A0h]
  unsigned __int8 *v35; // [rsp+68h] [rbp-98h] BYREF
  struct FrsStatus *v36; // [rsp+70h] [rbp-90h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+78h] [rbp-88h] BYREF
  int v38; // [rsp+80h] [rbp-80h]
  UpstreamTransport *v39; // [rsp+88h] [rbp-78h]
  RpcAsyncPipeState *v40; // [rsp+90h] [rbp-70h] BYREF
  struct _RPC_ASYNC_STATE *v41; // [rsp+98h] [rbp-68h] BYREF
  RpcAsyncPipeState *v42; // [rsp+A0h] [rbp-60h] BYREF
  RpcAsyncPipeState *v43; // [rsp+A8h] [rbp-58h] BYREF
  RpcAsyncPipeState *v44; // [rsp+B0h] [rbp-50h] BYREF
  struct _RPC_ASYNC_STATE *v45; // [rsp+B8h] [rbp-48h] BYREF
  RpcAsyncPipeState *v46; // [rsp+C0h] [rbp-40h] BYREF
  RpcAsyncPipeState *v47; // [rsp+C8h] [rbp-38h] BYREF
  RpcAsyncPipeState *v48; // [rsp+D0h] [rbp-30h] BYREF
  const wchar_t *v49; // [rsp+D8h] [rbp-28h] BYREF
  int v50; // [rsp+E0h] [rbp-20h]
  int v51; // [rsp+E4h] [rbp-1Ch]
  const wchar_t *v52; // [rsp+E8h] [rbp-18h]
  const wchar_t *v53; // [rsp+F0h] [rbp-10h] BYREF
  int v54; // [rsp+F8h] [rbp-8h]
  int v55; // [rsp+FCh] [rbp-4h]
  const wchar_t *v56; // [rsp+100h] [rbp+0h]
  const wchar_t *v57; // [rsp+108h] [rbp+8h] BYREF
  int v58; // [rsp+110h] [rbp+10h]
  int v59; // [rsp+114h] [rbp+14h]
  const wchar_t *v60; // [rsp+118h] [rbp+18h]
  const wchar_t *v61; // [rsp+120h] [rbp+20h] BYREF
  int v62; // [rsp+128h] [rbp+28h]
  int v63; // [rsp+12Ch] [rbp+2Ch]
  const wchar_t *v64; // [rsp+130h] [rbp+30h]
  const wchar_t *v65; // [rsp+138h] [rbp+38h] BYREF
  int v66; // [rsp+140h] [rbp+40h]
  int v67; // [rsp+144h] [rbp+44h]
  const wchar_t *v68; // [rsp+148h] [rbp+48h]
  const wchar_t *v69; // [rsp+150h] [rbp+50h] BYREF
  int v70; // [rsp+158h] [rbp+58h]
  int v71; // [rsp+15Ch] [rbp+5Ch]
  const wchar_t *v72; // [rsp+160h] [rbp+60h]
  const wchar_t *v73; // [rsp+168h] [rbp+68h] BYREF
  int v74; // [rsp+170h] [rbp+70h]
  int v75; // [rsp+174h] [rbp+74h]
  const wchar_t *v76; // [rsp+178h] [rbp+78h]
  _BYTE v77[80]; // [rsp+180h] [rbp+80h] BYREF
  unsigned int v78; // [rsp+1E0h] [rbp+E0h] BYREF
  RPC_STATUS v79; // [rsp+1E8h] [rbp+E8h] BYREF
  RpcAsyncPipeState *v80; // [rsp+1F0h] [rbp+F0h] BYREF
  unsigned int v81; // [rsp+1F8h] [rbp+F8h]

  v2 = *(UpstreamTransport **)(*((_QWORD *)this + 6) + 64LL);
  v39 = v2;
  ScopedLock::ScopedLock((ScopedLock *)&lpCriticalSection, (RpcAsyncPipeState *)((char *)this + 88));
  DataPipe = 0;
  v36 = 0;
  v78 = 0;
  v81 = Settings::GenericDwordSetting::operator()(&Settings::RpcFileBufferSize);
  v79 = 0;
  v4 = (unsigned __int8 *)operator_new(v81);
  v35 = v4;
  v5 = 0;
  v6 = 0;
  v7 = (struct _RPC_ASYNC_STATE *)*((_QWORD *)this + 5);
  v8 = L"RpcAsyncPipeState::Process";
  v9 = v38;
  v10 = g_DebugLog;
  do
  {
    if ( *((_DWORD *)this + 8) == 2 )
    {
      v11 = *((_QWORD *)this + 5);
      if ( v11 )
      {
        v12 = RpcServerTestCancel(*(RPC_BINDING_HANDLE *)(v11 + 32));
        v78 = v12;
        if ( v12 )
        {
          v13 = v12 - 1702;
          if ( v13 )
          {
            if ( v13 != 23 )
            {
              v10 = g_DebugLog;
LABEL_17:
              v8 = L"RpcAsyncPipeState::Process";
              v4 = v35;
              goto LABEL_18;
            }
            *((_DWORD *)this + 18) = 1725;
          }
          else
          {
            *((_DWORD *)this + 18) = 1702;
          }
          v10 = g_DebugLog;
        }
        else
        {
          v10 = g_DebugLog;
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
          {
            v49 = L"RpcAsyncPipeState::Process";
            v50 = 3588;
            v51 = 5;
            v52 = L"SRTR";
            v40 = this;
            dbgobj::DbgPrint<unsigned short,unsigned __int64>(&v49, L"this:%p. Call cancelled by client.", &v40);
            v10 = g_DebugLog;
          }
          *((_DWORD *)this + 18) = 1818;
        }
        *((_DWORD *)this + 8) = 5;
        goto LABEL_17;
      }
    }
LABEL_18:
    switch ( *((_DWORD *)this + 8) )
    {
      case 1:
        v5 = 1;
        break;
      case 2:
        LODWORD(v80) = 0;
        DataPipe = OutConnectionContentSetContext::SERVER_ReadDataPipe(
                     *(OutConnectionContentSetContext **)(*((_QWORD *)this + 6) + 304LL),
                     *((struct PipeReaderWriter **)this + 22),
                     v4,
                     v81,
                     (unsigned int *)&v80);
        v36 = DataPipe;
        if ( DataPipe )
        {
          *((_DWORD *)this + 8) = 5;
          ScopedLock::ScopedLock((ScopedLock *)v77, (RpcAsyncPipeState *)((char *)this + 200));
          if ( *((_DWORD *)DataPipe + 1) == 9033 && *((_QWORD *)this + 24) )
          {
            CLEAR_ERROR(&v36);
            v24 = *((_QWORD *)this + 24);
            if ( v24 )
            {
              CurrentThreadId = GetCurrentThreadId();
              DataPipe = (struct FrsStatus *)FrsStatusList::PushNewError(
                                               *((_QWORD *)this + 24),
                                               *(unsigned int *)(*((_QWORD *)this + 24) + 4LL),
                                               *(unsigned int *)(*((_QWORD *)this + 24) + 8LL),
                                               **((unsigned int **)this + 24),
                                               "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                               "RpcAsyncPipeState::Process",
                                               3644,
                                               CurrentThreadId,
                                               v24);
            }
            else
            {
              DataPipe = 0;
            }
            v36 = DataPipe;
            *((_QWORD *)this + 24) = 0;
          }
          *((_DWORD *)this + 18) = *((_DWORD *)DataPipe + 1);
          ScopedLock::~ScopedLock((ScopedLock *)v77);
          goto LABEL_35;
        }
        v26 = (unsigned int)v80;
        *((_QWORD *)this + 8) += (unsigned int)v80;
        if ( !v26 )
        {
          *((_DWORD *)this + 8) = 3;
          goto LABEL_121;
        }
        v78 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *, _QWORD))(*((_QWORD *)this + 7) + 8LL))(
                *(_QWORD *)(*((_QWORD *)this + 7) + 24LL),
                v35,
                v26);
        v27 = GetCurrentThreadId();
        DataPipe = (struct FrsStatus *)FrsStatusList::PushNewError(
                                         v28,
                                         v78,
                                         0,
                                         1,
                                         "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                         "RpcAsyncPipeState::Process",
                                         3661,
                                         v27,
                                         0);
        v36 = DataPipe;
        if ( v78 )
        {
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
          {
            v31 = L"RpcAsyncPipeState::Process";
            v32 = 3664;
            v33 = 5;
            v34 = L"SRTR";
            v80 = this;
            dbgobj::DbgPrint<unsigned short,unsigned __int64,unsigned long>(&v31, L"this:%p. Error:%d", &v80, &v78);
          }
          LogExtendedErrorInformation();
        }
        if ( DataPipe )
        {
          *((_DWORD *)this + 8) = 9;
          *((_DWORD *)this + 18) = *((_DWORD *)DataPipe + 1);
          *((_QWORD *)this + 5) = 0;
        }
        else
        {
          v5 = 1;
        }
        v29 = v26 + *((_DWORD *)this + 21);
        *((_DWORD *)this + 21) = v29;
        if ( v29 <= 0x100000 )
          goto LABEL_35;
        v22 = v29;
        v23 = v39;
LABEL_92:
        UpstreamTransport::CountBytes(v23, v22, v21);
        *((_DWORD *)this + 21) = 0;
LABEL_35:
        v10 = g_DebugLog;
        break;
      case 3:
        if ( v10 && LODWORD(v10[1].LockSemaphore) && SLODWORD(v10[1].OwningThread) >= 5 )
        {
          v31 = L"RpcAsyncPipeState::Process";
          v32 = 3761;
          v33 = 5;
          v34 = L"SRTR";
          v80 = this;
          dbgobj::DbgPrint<unsigned short,unsigned __int64>(&v31, L"Push eof this:%p", &v80);
        }
        *((_DWORD *)this + 8) = 4;
        v78 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, const wchar_t *))(*((_QWORD *)this + 7) + 8LL))(
                *(_QWORD *)(*((_QWORD *)this + 7) + 24LL),
                0,
                0,
                v8);
        v19 = GetCurrentThreadId();
        DataPipe = (struct FrsStatus *)FrsStatusList::PushNewError(
                                         v20,
                                         v78,
                                         0,
                                         1,
                                         "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                         "RpcAsyncPipeState::Process",
                                         3766,
                                         v19,
                                         0);
        v36 = DataPipe;
        if ( v78 )
        {
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
          {
            v31 = L"RpcAsyncPipeState::Process";
            v32 = 3769;
            v33 = 5;
            v34 = L"SRTR";
            v80 = this;
            dbgobj::DbgPrint<unsigned short,unsigned __int64,unsigned long>(&v31, L"this:%p Error:%d", &v80, &v78);
          }
          LogExtendedErrorInformation();
        }
        if ( DataPipe )
        {
          *((_DWORD *)this + 18) = *((_DWORD *)DataPipe + 1);
          *((_DWORD *)this + 8) = 9;
          *((_QWORD *)this + 5) = 0;
        }
        else
        {
          v5 = 1;
        }
        v22 = *((unsigned int *)this + 21);
        v23 = v2;
        goto LABEL_92;
      case 4:
        if ( v10 && LODWORD(v10[1].LockSemaphore) && SLODWORD(v10[1].OwningThread) >= 5 )
        {
          v73 = L"RpcAsyncPipeState::Process";
          v74 = 3794;
          v75 = 5;
          v76 = L"SRTR";
          v48 = this;
          dbgobj::DbgPrint<unsigned short,unsigned __int64>(&v73, L"Wait null push this:%p", &v48);
          v10 = g_DebugLog;
        }
        *((_DWORD *)this + 8) = 8;
        break;
      case 5:
        if ( v10 && LODWORD(v10[1].LockSemaphore) && SLODWORD(v10[1].OwningThread) >= 5 )
        {
          v31 = L"RpcAsyncPipeState::Process";
          v32 = 3698;
          v33 = 5;
          v34 = L"SRTR";
          v80 = this;
          dbgobj::DbgPrint<unsigned short,unsigned __int64>(&v31, L"Abort before push this:%p", &v80);
        }
        RpcAsyncPipeState::SetIdle(this);
        *((_DWORD *)this + 8) = 9;
        *((_QWORD *)this + 5) = 0;
        RpcAsyncPipeState::CloseDataPipe(this);
        v79 = RpcAsyncAbortCall(v7, *((_DWORD *)this + 18));
        v10 = g_DebugLog;
        if ( !v79 )
        {
          if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 5 )
            break;
          v69 = L"RpcAsyncPipeState::Process";
          v70 = 3724;
          v71 = 5;
          v72 = L"SRTR";
          v47 = this;
          dbgobj::DbgPrint<unsigned short,unsigned __int64,unsigned long>(
            &v69,
            L"RpcAsyncAbortCall succeeded, this:%p abortStatus:%d",
            &v47,
            (char *)this + 72);
          goto LABEL_35;
        }
        if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 3 )
          break;
        v65 = L"RpcAsyncPipeState::Process";
        v66 = 3718;
        v67 = 3;
        v68 = L"SRTR";
        v45 = v7;
        v46 = this;
        v15 = &v45;
        v16 = &v46;
        v17 = L"(Ignored) RpcAsyncAbortCall failed, this:%p RpcAsyncState:%p, status:%d";
        v18 = &v65;
LABEL_45:
        dbgobj::DbgPrint<unsigned short,unsigned __int64,unsigned __int64,unsigned long>(
          (_DWORD)v18,
          (_DWORD)v17,
          (_DWORD)v16,
          (_DWORD)v15,
          (__int64)&v79);
        v10 = g_DebugLog;
        break;
      case 6:
        if ( v10 && LODWORD(v10[1].LockSemaphore) && SLODWORD(v10[1].OwningThread) >= 5 )
        {
          v31 = L"RpcAsyncPipeState::Process";
          v32 = 3734;
          v33 = 5;
          v34 = L"SRTR";
          v80 = this;
          dbgobj::DbgPrint<unsigned short,unsigned __int64>(&v31, L"Abort after push this:%p", &v80);
        }
        RpcAsyncPipeState::SetIdle(this);
        *((_DWORD *)this + 8) = 7;
        *((_QWORD *)this + 5) = 0;
        v79 = RpcAsyncAbortCall(v7, *((_DWORD *)this + 18));
        v5 = 1;
        goto LABEL_35;
      case 7:
        if ( v10 && LODWORD(v10[1].LockSemaphore) && SLODWORD(v10[1].OwningThread) >= 5 )
        {
          v61 = L"RpcAsyncPipeState::Process";
          v62 = 3750;
          v63 = 5;
          v64 = L"SRTR";
          v44 = this;
          dbgobj::DbgPrint<unsigned short,unsigned __int64>(&v61, L"Wait push abort this:%p", &v44);
          v10 = g_DebugLog;
        }
        *((_DWORD *)this + 8) = 9;
        break;
      case 8:
        if ( v10 && LODWORD(v10[1].LockSemaphore) && SLODWORD(v10[1].OwningThread) >= 5 )
        {
          v31 = L"RpcAsyncPipeState::Process";
          v32 = 3806;
          v33 = 5;
          v34 = L"SRTR";
          v80 = this;
          dbgobj::DbgPrint<unsigned short,unsigned __int64>(&v31, L"Completing this:%p", &v80);
        }
        RpcAsyncPipeState::SetIdle(this);
        *((_QWORD *)this + 5) = 0;
        *((_DWORD *)this + 8) = 9;
        RpcAsyncPipeState::CloseDataPipe(this);
        v79 = RpcAsyncCompleteCall(v7, (char *)this + 76);
        v10 = g_DebugLog;
        if ( !v79 )
        {
          if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 5 )
            break;
          v57 = L"RpcAsyncPipeState::Process";
          v58 = 3840;
          v59 = 5;
          v60 = L"SRTR";
          v43 = this;
          dbgobj::DbgPrint<unsigned short,unsigned __int64,unsigned long>(
            &v57,
            L"RpcAsyncComplete succeeded, this:%p reply:%d",
            &v43,
            (char *)this + 76);
          goto LABEL_35;
        }
        if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 3 )
          break;
        v53 = L"RpcAsyncPipeState::Process";
        v54 = 3834;
        v55 = 3;
        v56 = L"SRTR";
        v41 = v7;
        v42 = this;
        v15 = &v41;
        v16 = &v42;
        v17 = L"(Ignored) RpcAsyncComplete failed, this:%p RpcAsyncState:%p, status:%d";
        v18 = &v53;
        goto LABEL_45;
      case 9:
        if ( v10 && LODWORD(v10[1].LockSemaphore) && SLODWORD(v10[1].OwningThread) >= 5 )
        {
          v31 = L"RpcAsyncPipeState::Process";
          v32 = 3851;
          v33 = 5;
          v34 = L"SRTR";
          v80 = this;
          dbgobj::DbgPrint<unsigned short,unsigned __int64>(&v31, L"End this:%p", &v80);
        }
        v6 = 1;
        v5 = 1;
        v14 = (FRS_SERVER_CONTEXT *)*((_QWORD *)this + 6);
        v80 = v14;
        v38 = --v9;
        LeaveCriticalSection(lpCriticalSection);
        if ( *((_DWORD *)this + 36) || *((_DWORD *)this + 18) )
          FRS_SERVER_CONTEXT::FinalizeServerContext(v14);
        RpcAsyncPipeState::CloseDataPipe(this);
        EnterCriticalSection(lpCriticalSection);
        *((_QWORD *)this + 6) = 0;
        LeaveCriticalSection(lpCriticalSection);
        ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v80);
        goto LABEL_35;
    }
    if ( !DataPipe )
      goto LABEL_122;
    if ( v10 && LODWORD(v10[1].LockSemaphore) && SLODWORD(v10[1].OwningThread) >= 3 )
    {
      v31 = L"RpcAsyncPipeState::Process";
      v32 = 3904;
      v33 = 3;
      v34 = L"SRTR";
      v80 = this;
      dbgobj::DbgPrint<unsigned short,unsigned __int64,FrsStatus>(&v31, L"this:%p Error:%?", &v80, DataPipe);
    }
    CLEAR_ERROR(&v36);
    DataPipe = v36;
LABEL_121:
    v10 = g_DebugLog;
LABEL_122:
    v2 = v39;
    v4 = v35;
    v8 = L"RpcAsyncPipeState::Process";
  }
  while ( !v5 );
  scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(&v35);
  ScopedLock::~ScopedLock((ScopedLock *)&lpCriticalSection);
  return v6;
}

```

## disassembly

```asm
0x14019d558  push    rbp
0x14019d55a  push    rbx
0x14019d55b  push    rsi
0x14019d55c  push    rdi
0x14019d55d  push    r12
0x14019d55f  push    r13
0x14019d561  push    r14
0x14019d563  push    r15
0x14019d565  lea     rbp, [rsp-98h]
0x14019d56d  sub     rsp, 198h
0x14019d574  mov     rbx, rcx
0x14019d577  mov     rax, [rcx+30h]
0x14019d57b  mov     rdi, [rax+40h]
0x14019d57f  mov     [rbp+0D0h+var_148], rdi
0x14019d583  lea     rdx, [rcx+58h]; struct ScopedCS *
0x14019d587  lea     rcx, [rsp+1D0h+lpCriticalSection]; this
0x14019d58c  call    ??0ScopedLock@@QEAA@AEAVScopedCS@@@Z; ScopedLock::ScopedLock(ScopedCS &)
0x14019d591  nop
0x14019d592  xor     esi, esi
0x14019d594  mov     [rsp+1D0h+var_160], rsi
0x14019d599  and     [rbp+0D0h+arg_0], esi
0x14019d59f  lea     rcx, ?RpcFileBufferSize@Settings@@3VCRpcFileBufferSize@1@A; Settings::CRpcFileBufferSize Settings::RpcFileBufferSize
0x14019d5a6  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x14019d5ab  mov     [rbp+0D0h+arg_18], eax
0x14019d5b1  and     [rbp+0D0h+arg_8], esi
0x14019d5b7  mov     ecx, eax; unsigned __int64
0x14019d5b9  call    ?operator_new@@YAPEAX_K@Z; operator_new(unsigned __int64)
0x14019d5be  mov     r8, rax
0x14019d5c1  mov     [rsp+1D0h+var_168], rax
0x14019d5c6  xor     r14d, r14d
0x14019d5c9  xor     r12d, r12d
0x14019d5cc  mov     r15, [rbx+28h]
0x14019d5d0  lea     r9, aRpcasyncpipest_7; "RpcAsyncPipeState::Process"
0x14019d5d7  lea     r10, aSrtr; "SRTR"
0x14019d5de  mov     r13d, [rbp+0D0h+var_150]
0x14019d5e2  mov     rdx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14019d5e9  cmp     dword ptr [rbx+20h], 2
0x14019d5ed  jnz     loc_14019D6C7
0x14019d5f3  mov     rcx, [rbx+28h]
0x14019d5f7  test    rcx, rcx
0x14019d5fa  jz      loc_14019D6C7
0x14019d600  mov     rcx, [rcx+20h]; BindingHandle
0x14019d604  call    cs:__imp_RpcServerTestCancel
0x14019d60b  nop     dword ptr [rax+rax+00h]
0x14019d610  mov     [rbp+0D0h+arg_0], eax
0x14019d616  test    eax, eax
0x14019d618  jz      short loc_14019D64B
0x14019d61a  sub     eax, 6A6h
0x14019d61f  jz      short loc_14019D642
0x14019d621  sub     eax, 17h
0x14019d624  jz      short loc_14019D632
0x14019d626  mov     rdx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14019d62d  jmp     loc_14019D6B4
0x14019d632  mov     dword ptr [rbx+48h], 6BDh
0x14019d639  mov     rdx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14019d640  jmp     short loc_14019D6AD
0x14019d642  mov     dword ptr [rbx+48h], 6A6h
0x14019d649  jmp     short loc_14019D639
0x14019d64b  mov     rdx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14019d652  test    rdx, rdx
0x14019d655  jz      short loc_14019D6A6
0x14019d657  cmp     dword ptr [rdx+40h], 0
0x14019d65b  jz      short loc_14019D6A6
0x14019d65d  cmp     dword ptr [rdx+38h], 5
0x14019d661  jl      short loc_14019D6A6
0x14019d663  lea     rax, aRpcasyncpipest_7; "RpcAsyncPipeState::Process"
0x14019d66a  mov     [rbp+0D0h+var_F8], rax
0x14019d66e  mov     [rbp+0D0h+var_F0], 0E04h
0x14019d675  mov     [rbp+0D0h+var_EC], 5
0x14019d67c  lea     rax, aSrtr; "SRTR"
0x14019d683  mov     [rbp+0D0h+var_E8], rax
0x14019d687  mov     [rbp+0D0h+var_140], rbx
0x14019d68b  lea     r8, [rbp+0D0h+var_140]
0x14019d68f  lea     rdx, aThisPCallCance; "this:%p. Call cancelled by client."
0x14019d696  lea     rcx, [rbp+0D0h+var_F8]
0x14019d69a  call    ??$DbgPrint@G_K@dbgobj@@QEAA_KPEBGAEB_K@Z; dbgobj::DbgPrint<ushort,unsigned __int64>(ushort const *,unsigned __int64 const &)
0x14019d69f  mov     rdx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14019d6a6  mov     dword ptr [rbx+48h], 71Ah
0x14019d6ad  mov     dword ptr [rbx+20h], 5
0x14019d6b4  lea     r10, aSrtr; "SRTR"
0x14019d6bb  lea     r9, aRpcasyncpipest_7; "RpcAsyncPipeState::Process"
0x14019d6c2  mov     r8, [rsp+1D0h+var_168]; unsigned __int8 *
0x14019d6c7  mov     ecx, [rbx+20h]
0x14019d6ca  sub     ecx, 1
0x14019d6cd  jz      loc_14019DF62
0x14019d6d3  sub     ecx, 1
0x14019d6d6  jz      loc_14019DD29
0x14019d6dc  sub     ecx, 1
0x14019d6df  jz      loc_14019DBC3
0x14019d6e5  sub     ecx, 1
0x14019d6e8  jz      loc_14019DB71
0x14019d6ee  sub     ecx, 1
0x14019d6f1  jz      loc_14019DA2A
0x14019d6f7  sub     ecx, 1
0x14019d6fa  jz      loc_14019D9A9
0x14019d700  sub     ecx, 1
0x14019d703  jz      loc_14019D957
0x14019d709  sub     ecx, 1
0x14019d70c  jz      loc_14019D7F2
0x14019d712  cmp     ecx, 1
0x14019d715  jnz     loc_14019DF68
0x14019d71b  test    rdx, rdx
0x14019d71e  jz      short loc_14019D765
0x14019d720  cmp     dword ptr [rdx+40h], 0
0x14019d724  jz      short loc_14019D765
0x14019d726  cmp     dword ptr [rdx+38h], 5
0x14019d72a  jl      short loc_14019D765
0x14019d72c  mov     [rsp+1D0h+var_180], r9
0x14019d731  mov     [rsp+1D0h+var_178], 0F0Bh
0x14019d739  mov     [rsp+1D0h+var_174], 5
0x14019d741  mov     [rsp+1D0h+var_170], r10
0x14019d746  mov     [rbp+0D0h+arg_10], rbx
0x14019d74d  lea     r8, [rbp+0D0h+arg_10]
0x14019d754  lea     rdx, aEndThisP; "End this:%p"
0x14019d75b  lea     rcx, [rsp+1D0h+var_180]
0x14019d760  call    ??$DbgPrint@G_K@dbgobj@@QEAA_KPEBGAEB_K@Z; dbgobj::DbgPrint<ushort,unsigned __int64>(ushort const *,unsigned __int64 const &)
0x14019d765  mov     eax, 1
0x14019d76a  mov     r12d, eax
0x14019d76d  mov     r14d, eax
0x14019d770  mov     rdi, [rbx+30h]
0x14019d774  mov     [rbp+0D0h+arg_10], rdi
0x14019d77b  dec     r13d
0x14019d77e  mov     [rbp+0D0h+var_150], r13d
0x14019d782  mov     rcx, [rsp+1D0h+lpCriticalSection]; lpCriticalSection
0x14019d787  call    cs:__imp_LeaveCriticalSection
0x14019d78e  nop     dword ptr [rax+rax+00h]
0x14019d793  cmp     dword ptr [rbx+90h], 0
0x14019d79a  jnz     short loc_14019D7A2
0x14019d79c  cmp     dword ptr [rbx+48h], 0
0x14019d7a0  jz      short loc_14019D7AA
0x14019d7a2  mov     rcx, rdi; this
0x14019d7a5  call    ?FinalizeServerContext@FRS_SERVER_CONTEXT@@QEAAXXZ; FRS_SERVER_CONTEXT::FinalizeServerContext(void)
0x14019d7aa  mov     rcx, rbx; this
0x14019d7ad  call    ?CloseDataPipe@RpcAsyncPipeState@@QEAAXXZ; RpcAsyncPipeState::CloseDataPipe(void)
0x14019d7b2  mov     rcx, [rsp+1D0h+lpCriticalSection]; lpCriticalSection
0x14019d7b7  call    cs:__imp_EnterCriticalSection
0x14019d7be  nop     dword ptr [rax+rax+00h]
0x14019d7c3  and     qword ptr [rbx+30h], 0
0x14019d7c8  mov     rcx, [rsp+1D0h+lpCriticalSection]; lpCriticalSection
0x14019d7cd  call    cs:__imp_LeaveCriticalSection
0x14019d7d4  nop     dword ptr [rax+rax+00h]
0x14019d7d9  nop
0x14019d7da  lea     rcx, [rbp+0D0h+arg_10]
0x14019d7e1  call    ??1?$ScopedRef@VVvUpData@@@@QEAA@XZ; ScopedRef<VvUpData>::~ScopedRef<VvUpData>(void)
0x14019d7e6  mov     rdx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14019d7ed  jmp     loc_14019DF68
0x14019d7f2  test    rdx, rdx
0x14019d7f5  jz      short loc_14019D83C
0x14019d7f7  cmp     dword ptr [rdx+40h], 0
0x14019d7fb  jz      short loc_14019D83C
0x14019d7fd  cmp     dword ptr [rdx+38h], 5
0x14019d801  jl      short loc_14019D83C
0x14019d803  mov     [rsp+1D0h+var_180], r9
0x14019d808  mov     [rsp+1D0h+var_178], 0EDEh
0x14019d810  mov     [rsp+1D0h+var_174], 5
0x14019d818  mov     [rsp+1D0h+var_170], r10
0x14019d81d  mov     [rbp+0D0h+arg_10], rbx
0x14019d824  lea     r8, [rbp+0D0h+arg_10]
0x14019d82b  lea     rdx, aCompletingThis; "Completing this:%p"
0x14019d832  lea     rcx, [rsp+1D0h+var_180]
0x14019d837  call    ??$DbgPrint@G_K@dbgobj@@QEAA_KPEBGAEB_K@Z; dbgobj::DbgPrint<ushort,unsigned __int64>(ushort const *,unsigned __int64 const &)
0x14019d83c  mov     rcx, rbx; this
0x14019d83f  call    ?SetIdle@RpcAsyncPipeState@@IEAAXXZ; RpcAsyncPipeState::SetIdle(void)
0x14019d844  and     qword ptr [rbx+28h], 0
0x14019d849  mov     dword ptr [rbx+20h], 9
0x14019d850  mov     rcx, rbx; this
0x14019d853  call    ?CloseDataPipe@RpcAsyncPipeState@@QEAAXXZ; RpcAsyncPipeState::CloseDataPipe(void)
0x14019d858  lea     rdx, [rbx+4Ch]; Reply
0x14019d85c  mov     rcx, r15; pAsync
0x14019d85f  call    cs:__imp_RpcAsyncCompleteCall
0x14019d866  nop     dword ptr [rax+rax+00h]
0x14019d86b  mov     [rbp+0D0h+arg_8], eax
0x14019d871  mov     rdx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14019d878  test    eax, eax
0x14019d87a  jz      short loc_14019D8F5
0x14019d87c  lea     rdi, aRpcasyncpipest_7; "RpcAsyncPipeState::Process"
0x14019d883  test    rdx, rdx
0x14019d886  jz      loc_14019DF6F
0x14019d88c  cmp     dword ptr [rdx+40h], 0
0x14019d890  jz      loc_14019DF6F
0x14019d896  cmp     dword ptr [rdx+38h], 3
0x14019d89a  jl      loc_14019DF6F
0x14019d8a0  mov     [rbp+0D0h+var_E0], rdi
0x14019d8a4  mov     [rbp+0D0h+var_D8], 0EFAh
0x14019d8ab  mov     [rbp+0D0h+var_D4], 3
0x14019d8b2  lea     rax, aSrtr; "SRTR"
0x14019d8b9  mov     [rbp+0D0h+var_D0], rax
0x14019d8bd  mov     [rbp+0D0h+var_138], r15
0x14019d8c1  mov     [rbp+0D0h+var_130], rbx
0x14019d8c5  lea     r9, [rbp+0D0h+var_138]
0x14019d8c9  lea     r8, [rbp+0D0h+var_130]
0x14019d8cd  lea     rdx, aIgnoredRpcasyn_0; "(Ignored) RpcAsyncComplete failed, this"...
0x14019d8d4  lea     rcx, [rbp+0D0h+var_E0]
0x14019d8d8  lea     rax, [rbp+0D0h+arg_8]
0x14019d8df  mov     [rsp+1D0h+var_1B0], rax
0x14019d8e4  call    ??$DbgPrint@G_K_KK@dbgobj@@QEAA_KPEBGAEB_K1AEBK@Z; dbgobj::DbgPrint<ushort,unsigned __int64,unsigned __int64,ulong>(ushort const *,unsigned __int64 const &,unsigned __int64 const &,ulong const &)
0x14019d8e9  mov     rdx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14019d8f0  jmp     loc_14019DF6F
0x14019d8f5  test    rdx, rdx
0x14019d8f8  jz      loc_14019DF68
0x14019d8fe  cmp     dword ptr [rdx+40h], 0
0x14019d902  jz      loc_14019DF68
0x14019d908  cmp     dword ptr [rdx+38h], 5
0x14019d90c  jl      loc_14019DF68
0x14019d912  lea     rax, aRpcasyncpipest_7; "RpcAsyncPipeState::Process"
0x14019d919  mov     [rbp+0D0h+var_C8], rax
0x14019d91d  mov     [rbp+0D0h+var_C0], 0F00h
0x14019d924  mov     [rbp+0D0h+var_BC], 5
0x14019d92b  lea     rax, aSrtr; "SRTR"
0x14019d932  mov     [rbp+0D0h+var_B8], rax
0x14019d936  mov     [rbp+0D0h+var_128], rbx
0x14019d93a  lea     r9, [rbx+4Ch]
0x14019d93e  lea     r8, [rbp+0D0h+var_128]
0x14019d942  lea     rdx, aRpcasynccomple_0; "RpcAsyncComplete succeeded, this:%p rep"...
0x14019d949  lea     rcx, [rbp+0D0h+var_C8]
0x14019d94d  call    ??$DbgPrint@G_KK@dbgobj@@QEAA_KPEBGAEB_KAEBK@Z; dbgobj::DbgPrint<ushort,unsigned __int64,ulong>(ushort const *,unsigned __int64 const &,ulong const &)
0x14019d952  jmp     loc_14019D7E6
0x14019d957  test    rdx, rdx
0x14019d95a  jz      short loc_14019D99D
0x14019d95c  cmp     dword ptr [rdx+40h], 0
0x14019d960  jz      short loc_14019D99D
0x14019d962  cmp     dword ptr [rdx+38h], 5
0x14019d966  jl      short loc_14019D99D
0x14019d968  mov     [rbp+0D0h+var_B0], r9
0x14019d96c  mov     [rbp+0D0h+var_A8], 0EA6h
0x14019d973  mov     [rbp+0D0h+var_A4], 5
0x14019d97a  mov     [rbp+0D0h+var_A0], r10
0x14019d97e  mov     [rbp+0D0h+var_120], rbx
0x14019d982  lea     r8, [rbp+0D0h+var_120]
0x14019d986  lea     rdx, aWaitPushAbortT; "Wait push abort this:%p"
0x14019d98d  lea     rcx, [rbp+0D0h+var_B0]
0x14019d991  call    ??$DbgPrint@G_K@dbgobj@@QEAA_KPEBGAEB_K@Z; dbgobj::DbgPrint<ushort,unsigned __int64>(ushort const *,unsigned __int64 const &)
0x14019d996  mov     rdx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14019d99d  mov     dword ptr [rbx+20h], 9
0x14019d9a4  jmp     loc_14019DF68
0x14019d9a9  test    rdx, rdx
0x14019d9ac  jz      short loc_14019D9F3
0x14019d9ae  cmp     dword ptr [rdx+40h], 0
0x14019d9b2  jz      short loc_14019D9F3
0x14019d9b4  cmp     dword ptr [rdx+38h], 5
0x14019d9b8  jl      short loc_14019D9F3
0x14019d9ba  mov     [rsp+1D0h+var_180], r9
0x14019d9bf  mov     [rsp+1D0h+var_178], 0E96h
0x14019d9c7  mov     [rsp+1D0h+var_174], 5
0x14019d9cf  mov     [rsp+1D0h+var_170], r10
0x14019d9d4  mov     [rbp+0D0h+arg_10], rbx
0x14019d9db  lea     r8, [rbp+0D0h+arg_10]
0x14019d9e2  lea     rdx, aAbortAfterPush; "Abort after push this:%p"
0x14019d9e9  lea     rcx, [rsp+1D0h+var_180]
0x14019d9ee  call    ??$DbgPrint@G_K@dbgobj@@QEAA_KPEBGAEB_K@Z; dbgobj::DbgPrint<ushort,unsigned __int64>(ushort const *,unsigned __int64 const &)
0x14019d9f3  mov     rcx, rbx; this
0x14019d9f6  call    ?SetIdle@RpcAsyncPipeState@@IEAAXXZ; RpcAsyncPipeState::SetIdle(void)
0x14019d9fb  mov     dword ptr [rbx+20h], 7
0x14019da02  and     qword ptr [rbx+28h], 0
0x14019da07  mov     edx, [rbx+48h]; ExceptionCode
0x14019da0a  mov     rcx, r15; pAsync
0x14019da0d  call    cs:__imp_RpcAsyncAbortCall
0x14019da14  nop     dword ptr [rax+rax+00h]
0x14019da19  mov     [rbp+0D0h+arg_8], eax
0x14019da1f  mov     r14d, 1
0x14019da25  jmp     loc_14019D7E6
0x14019da2a  test    rdx, rdx
0x14019da2d  jz      short loc_14019DA74
0x14019da2f  cmp     dword ptr [rdx+40h], 0
0x14019da33  jz      short loc_14019DA74
0x14019da35  cmp     dword ptr [rdx+38h], 5
0x14019da39  jl      short loc_14019DA74
0x14019da3b  mov     [rsp+1D0h+var_180], r9
0x14019da40  mov     [rsp+1D0h+var_178], 0E72h
0x14019da48  mov     [rsp+1D0h+var_174], 5
0x14019da50  mov     [rsp+1D0h+var_170], r10
0x14019da55  mov     [rbp+0D0h+arg_10], rbx
0x14019da5c  lea     r8, [rbp+0D0h+arg_10]
0x14019da63  lea     rdx, aAbortBeforePus; "Abort before push this:%p"
0x14019da6a  lea     rcx, [rsp+1D0h+var_180]
0x14019da6f  call    ??$DbgPrint@G_K@dbgobj@@QEAA_KPEBGAEB_K@Z; dbgobj::DbgPrint<ushort,unsigned __int64>(ushort const *,unsigned __int64 const &)
0x14019da74  mov     rcx, rbx; this
0x14019da77  call    ?SetIdle@RpcAsyncPipeState@@IEAAXXZ; RpcAsyncPipeState::SetIdle(void)
0x14019da7c  mov     dword ptr [rbx+20h], 9
0x14019da83  and     qword ptr [rbx+28h], 0
0x14019da88  mov     rcx, rbx; this
0x14019da8b  call    ?CloseDataPipe@RpcAsyncPipeState@@QEAAXXZ; RpcAsyncPipeState::CloseDataPipe(void)
0x14019da90  mov     edx, [rbx+48h]; ExceptionCode
0x14019da93  mov     rcx, r15; pAsync
0x14019da96  call    cs:__imp_RpcAsyncAbortCall
0x14019da9d  nop     dword ptr [rax+rax+00h]
0x14019daa2  mov     [rbp+0D0h+arg_8], eax
0x14019daa8  mov     rdx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14019daaf  test    eax, eax
0x14019dab1  jz      short loc_14019DB14
0x14019dab3  lea     rdi, aRpcasyncpipest_7; "RpcAsyncPipeState::Process"
0x14019daba  test    rdx, rdx
0x14019dabd  jz      loc_14019DF6F
0x14019dac3  cmp     dword ptr [rdx+40h], 0
0x14019dac7  jz      loc_14019DF6F
0x14019dacd  cmp     dword ptr [rdx+38h], 3
0x14019dad1  jl      loc_14019DF6F
0x14019dad7  mov     [rbp+0D0h+var_98], rdi
0x14019dadb  mov     [rbp+0D0h+var_90], 0E86h
0x14019dae2  mov     [rbp+0D0h+var_8C], 3
  ... truncated ...
```
