# CancelContext::Cancel(ICancelContext::RequestState *)

- ea: `0x1401a59c0`
- end: `0x1401a5cfd`
- name: `?Cancel@CancelContext@@UEAAPEAVFrsStatus@@PEAW4RequestState@ICancelContext@@@Z`
- size: `829`
- prototype: `struct FrsStatus *__fastcall(CancelContext *__hidden this, enum ICancelContext::RequestState *)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1401a56e0`

## callees

- `0x14000d980`
- `0x14000dcc0`
- `0x140024964`
- `0x140024c84`
- `0x1400391c4`
- `0x14003abec`
- `0x14003ac00`
- `0x14007c9f0`
- `0x1401a59c0`
- `0x1401b30b0`
- `0x1401b3184`
- `0x1401b8a00`
- `0x1401b8a38`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1401a5b4d`
- `KERNEL32!WaitForSingleObject` at `0x1401a5b4d`
- `KERNEL32!CloseHandle` at `0x1401a5b60`
- `KERNEL32!CloseHandle` at `0x1401a5b60`
- `KERNEL32!GetCurrentThreadId` at `0x1401a5a89`
- `KERNEL32!GetCurrentThreadId` at `0x1401a5ab0`
- `KERNEL32!GetCurrentThreadId` at `0x1401a5af8`
- `KERNEL32!GetCurrentThreadId` at `0x1401a5b2d`
- `KERNEL32!GetCurrentThreadId` at `0x1401a5b73`
- `KERNEL32!GetCurrentThreadId` at `0x1401a5b93`
- `KERNEL32!GetCurrentThreadId` at `0x1401a5bba`
- `KERNEL32!GetCurrentThreadId` at `0x1401a5c52`
- `KERNEL32!GetCurrentThreadId` at `0x1401a5c9f`
- `KERNEL32!GetCurrentThreadId` at `0x1401a5a89`
- `KERNEL32!GetCurrentThreadId` at `0x1401a5ab0`
- `KERNEL32!GetCurrentThreadId` at `0x1401a5af8`
- `KERNEL32!GetCurrentThreadId` at `0x1401a5b2d`
- `KERNEL32!GetCurrentThreadId` at `0x1401a5b73`
- `KERNEL32!GetCurrentThreadId` at `0x1401a5b93`
- `KERNEL32!GetCurrentThreadId` at `0x1401a5bba`
- `KERNEL32!GetCurrentThreadId` at `0x1401a5c52`
- `KERNEL32!GetCurrentThreadId` at `0x1401a5c9f`
- `RPCRT4!RpcAsyncCancelCall` at `0x1401a5aea`
- `RPCRT4!RpcAsyncCancelCall` at `0x1401a5c44`
- `RPCRT4!RpcAsyncCancelCall` at `0x1401a5aea`
- `RPCRT4!RpcAsyncCancelCall` at `0x1401a5c44`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
Cancel *__fastcall CancelContext::Cancel(Cancel *this, enum ICancelContext::RequestState *a2)
{
  Cancel *v4; // rdi
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  unsigned int v13; // ebx
  __int64 v14; // rcx
  DWORD v15; // eax
  DWORD v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rbx
  __int64 v19; // rax
  unsigned int *v20; // rbx
  DWORD v21; // eax
  __int64 v22; // rcx
  int v24; // [rsp+30h] [rbp-19h]
  DWORD v25; // [rsp+38h] [rbp-11h]
  DWORD CurrentThreadId; // [rsp+38h] [rbp-11h]
  DWORD v27; // [rsp+38h] [rbp-11h]
  _BYTE v28[16]; // [rsp+50h] [rbp+7h] BYREF
  _BYTE v29[16]; // [rsp+60h] [rbp+17h] BYREF
  const wchar_t *v30; // [rsp+70h] [rbp+27h] BYREF
  int v31; // [rsp+78h] [rbp+2Fh]
  int v32; // [rsp+7Ch] [rbp+33h]
  const wchar_t *v33; // [rsp+80h] [rbp+37h]
  RefCountObject *v34; // [rsp+B0h] [rbp+67h] BYREF
  char v35; // [rsp+B8h] [rbp+6Fh] BYREF

  v4 = 0;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    v30 = L"CancelContext::Cancel";
    v31 = 1412;
    v32 = 5;
    v33 = L"DOWN";
    v34 = this;
    dbgobj::DbgPrint<unsigned short,unsigned __int64>(&v30, L"ptr:%p", &v34);
  }
  ScopedCrewLock::ScopedCrewLock(&v35, (char *)this + 176);
  if ( a2 )
    *(_DWORD *)a2 = *((_DWORD *)this + 70);
  v5 = *((_DWORD *)this + 70);
  if ( v5 )
  {
    v6 = v5 - 1;
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( v7 )
      {
        v8 = v7 - 1;
        if ( v8 )
        {
          v9 = v8 - 1;
          if ( v9 )
          {
            if ( v9 == 1 )
            {
              CurrentThreadId = GetCurrentThreadId();
              v11 = FrsStatusList::PushNewError(
                      v12,
                      2147549186LL,
                      0,
                      1,
                      "base\\fs\\remotefs\\frs\\src\\transport\\downstreamtransport.cpp",
                      "CancelContext::Cancel",
                      1484,
                      CurrentThreadId,
                      0);
            }
            else
            {
              v25 = GetCurrentThreadId();
              v11 = FrsStatusList::PushNewError(
                      v10,
                      13,
                      0,
                      1,
                      "base\\fs\\remotefs\\frs\\src\\transport\\downstreamtransport.cpp",
                      "CancelContext::Cancel",
                      1489,
                      v25,
                      0);
            }
LABEL_24:
            v20 = (unsigned int *)v11;
            if ( v11 )
            {
              v21 = GetCurrentThreadId();
              v4 = (Cancel *)FrsStatusList::PushNewError(
                               v22,
                               v20[1],
                               v20[2],
                               *v20,
                               "base\\fs\\remotefs\\frs\\src\\transport\\downstreamtransport.cpp",
                               "CancelContext::Cancel",
                               1493,
                               v21,
                               v20);
            }
            goto LABEL_26;
          }
          *((_DWORD *)this + 70) = 5;
          v13 = RpcAsyncCancelCall((PRPC_ASYNC_STATE)((char *)this + 48), 1);
          v27 = GetCurrentThreadId();
          v24 = 1450;
          goto LABEL_22;
        }
        *((_QWORD *)this + 36) = CreateSemaphoreOrDie(0, 0x7FFFFFFF);
        v15 = GetCurrentThreadId();
        CREWLock::Release((Cancel *)((char *)this + 176), v15);
        WaitForSingleObject(*((HANDLE *)this + 36), 0xFFFFFFFF);
        CloseHandle(*((HANDLE *)this + 36));
        *((_QWORD *)this + 36) = 0;
        v16 = GetCurrentThreadId();
        CREWLock::AcquireWriteLock((Cancel *)((char *)this + 176), v16);
        *((_DWORD *)this + 70) = 2;
        v27 = GetCurrentThreadId();
        v24 = 1472;
      }
      else
      {
        v27 = GetCurrentThreadId();
        v24 = 1480;
      }
      v17 = 2147549463LL;
LABEL_23:
      v11 = FrsStatusList::PushNewError(
              v14,
              v17,
              0,
              1,
              "base\\fs\\remotefs\\frs\\src\\transport\\downstreamtransport.cpp",
              "CancelContext::Cancel",
              v24,
              v27,
              0);
      goto LABEL_24;
    }
    v18 = *((_QWORD *)this + 4);
    ScopedLock::ScopedLock((ScopedLock *)v29, (struct ScopedCS *)(v18 + 360));
    v34 = this;
    std::pair<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,SlowSyncState>>>>,bool>::pair<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,SlowSyncState>>>>,bool>(v28);
    v19 = std::_Tree<std::_Tset_traits<IUpdateTask *,ComparePointers<IUpdateTask>,std::allocator<IUpdateTask *>,0>>::insert<0,0>(
            v18 + 456,
            &v30,
            &v34);
    std::pair<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<VolumeId const,std::pair<AutoFileHandle *,TimeoutCounter>>>>>,bool>::operator=<std::pair<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<VolumeId const,std::pair<AutoFileHandle *,TimeoutCounter>>>>>,bool>,0>(
      v28,
      v19);
    if ( v28[8] )
      RefCountObject::AddRef(v34);
    ScopedLock::~ScopedLock((ScopedLock *)v29);
    *((_DWORD *)this + 70) = 4;
    v13 = RpcAsyncCancelCall((PRPC_ASYNC_STATE)((char *)this + 48), 0);
    v27 = GetCurrentThreadId();
    v24 = 1437;
LABEL_22:
    v17 = v13;
    goto LABEL_23;
  }
LABEL_26:
  ScopedCrewLock::~ScopedCrewLock((ScopedCrewLock *)&v35);
  return v4;
}

```

## disassembly

```asm
0x1401a59c0  mov     [rsp-8+arg_10], rbx
0x1401a59c5  mov     [rsp-8+arg_18], rsi
0x1401a59ca  push    rbp
0x1401a59cb  push    rdi
0x1401a59cc  push    r14
0x1401a59ce  lea     rbp, [rsp-47h]
0x1401a59d3  sub     rsp, 90h
0x1401a59da  mov     rbx, rdx
0x1401a59dd  mov     rsi, rcx
0x1401a59e0  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401a59e7  xor     edi, edi
0x1401a59e9  test    rax, rax
0x1401a59ec  jz      short loc_1401A5A35
0x1401a59ee  cmp     [rax+40h], edi
0x1401a59f1  jz      short loc_1401A5A35
0x1401a59f3  cmp     dword ptr [rax+38h], 5
0x1401a59f7  jl      short loc_1401A5A35
0x1401a59f9  lea     rax, aCancelcontextC; "CancelContext::Cancel"
0x1401a5a00  mov     [rbp+57h+var_30], rax
0x1401a5a04  mov     [rbp+57h+var_28], 584h
0x1401a5a0b  mov     [rbp+57h+var_24], 5
0x1401a5a12  lea     rax, aDown; "DOWN"
0x1401a5a19  mov     [rbp+57h+var_20], rax
0x1401a5a1d  mov     [rbp+57h+arg_0], rcx
0x1401a5a21  lea     r8, [rbp+57h+arg_0]
0x1401a5a25  lea     rdx, aPtrP; "ptr:%p"
0x1401a5a2c  lea     rcx, [rbp+57h+var_30]
0x1401a5a30  call    ??$DbgPrint@G_K@dbgobj@@QEAA_KPEBGAEB_K@Z; dbgobj::DbgPrint<ushort,unsigned __int64>(ushort const *,unsigned __int64 const &)
0x1401a5a35  lea     r14, [rsi+0B0h]
0x1401a5a3c  mov     rdx, r14
0x1401a5a3f  lea     rcx, [rbp+57h+arg_8]
0x1401a5a43  call    ??0ScopedCrewLock@@QEAA@AEAVCREWLock@@UWrite@0@@Z; ScopedCrewLock::ScopedCrewLock(CREWLock &,ScopedCrewLock::Write)
0x1401a5a48  nop
0x1401a5a49  test    rbx, rbx
0x1401a5a4c  jz      short loc_1401A5A56
0x1401a5a4e  mov     eax, [rsi+118h]
0x1401a5a54  mov     [rbx], eax
0x1401a5a56  mov     ecx, [rsi+118h]
0x1401a5a5c  test    ecx, ecx
0x1401a5a5e  jz      loc_1401A5CD8
0x1401a5a64  sub     ecx, 1
0x1401a5a67  jz      loc_1401A5BD9
0x1401a5a6d  sub     ecx, 1
0x1401a5a70  jz      loc_1401A5BBA
0x1401a5a76  sub     ecx, 1
0x1401a5a79  jz      loc_1401A5B1A
0x1401a5a7f  sub     ecx, 1
0x1401a5a82  jz      short loc_1401A5AD7
0x1401a5a84  cmp     ecx, 1
0x1401a5a87  jz      short loc_1401A5AB0
0x1401a5a89  call    cs:__imp_GetCurrentThreadId
0x1401a5a90  nop     dword ptr [rax+rax+00h]
0x1401a5a95  mov     [rsp+0A0h+var_60], rdi
0x1401a5a9a  mov     [rsp+0A0h+var_68], eax
0x1401a5a9e  mov     [rsp+0A0h+var_70], 5D1h
0x1401a5aa6  mov     edx, 0Dh
0x1401a5aab  jmp     loc_1401A5C71
0x1401a5ab0  call    cs:__imp_GetCurrentThreadId
0x1401a5ab7  nop     dword ptr [rax+rax+00h]
0x1401a5abc  mov     [rsp+0A0h+var_60], rdi
0x1401a5ac1  mov     [rsp+0A0h+var_68], eax
0x1401a5ac5  mov     [rsp+0A0h+var_70], 5CCh
0x1401a5acd  mov     edx, 80010002h
0x1401a5ad2  jmp     loc_1401A5C71
0x1401a5ad7  mov     dword ptr [rsi+118h], 5
0x1401a5ae1  lea     rcx, [rsi+30h]; pAsync
0x1401a5ae5  mov     edx, 1; fAbort
0x1401a5aea  call    cs:__imp_RpcAsyncCancelCall
0x1401a5af1  nop     dword ptr [rax+rax+00h]
0x1401a5af6  mov     ebx, eax
0x1401a5af8  call    cs:__imp_GetCurrentThreadId
0x1401a5aff  nop     dword ptr [rax+rax+00h]
0x1401a5b04  mov     [rsp+0A0h+var_60], rdi
0x1401a5b09  mov     [rsp+0A0h+var_68], eax
0x1401a5b0d  mov     [rsp+0A0h+var_70], 5AAh
0x1401a5b15  jmp     loc_1401A5C6F
0x1401a5b1a  mov     edx, 7FFFFFFFh; lMaximumCount
0x1401a5b1f  xor     ecx, ecx; lInitialCount
0x1401a5b21  call    ?CreateSemaphoreOrDie@@YAPEAXJJ@Z; CreateSemaphoreOrDie(long,long)
0x1401a5b26  mov     [rsi+120h], rax
0x1401a5b2d  call    cs:__imp_GetCurrentThreadId
0x1401a5b34  nop     dword ptr [rax+rax+00h]
0x1401a5b39  mov     edx, eax; unsigned __int64
0x1401a5b3b  mov     rcx, r14; this
0x1401a5b3e  call    ?Release@CREWLock@@QEAAX_K@Z; CREWLock::Release(unsigned __int64)
0x1401a5b43  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1401a5b46  mov     rcx, [rsi+120h]; hHandle
0x1401a5b4d  call    cs:__imp_WaitForSingleObject
0x1401a5b54  nop     dword ptr [rax+rax+00h]
0x1401a5b59  mov     rcx, [rsi+120h]; hObject
0x1401a5b60  call    cs:__imp_CloseHandle
0x1401a5b67  nop     dword ptr [rax+rax+00h]
0x1401a5b6c  mov     [rsi+120h], rdi
0x1401a5b73  call    cs:__imp_GetCurrentThreadId
0x1401a5b7a  nop     dword ptr [rax+rax+00h]
0x1401a5b7f  mov     edx, eax; unsigned __int64
0x1401a5b81  mov     rcx, r14; this
0x1401a5b84  call    ?AcquireWriteLock@CREWLock@@QEAAX_K@Z; CREWLock::AcquireWriteLock(unsigned __int64)
0x1401a5b89  mov     dword ptr [rsi+118h], 2
0x1401a5b93  call    cs:__imp_GetCurrentThreadId
0x1401a5b9a  nop     dword ptr [rax+rax+00h]
0x1401a5b9f  mov     [rsp+0A0h+var_60], rdi
0x1401a5ba4  mov     [rsp+0A0h+var_68], eax
0x1401a5ba8  mov     [rsp+0A0h+var_70], 5C0h
0x1401a5bb0  mov     edx, 80010117h
0x1401a5bb5  jmp     loc_1401A5C71
0x1401a5bba  call    cs:__imp_GetCurrentThreadId
0x1401a5bc1  nop     dword ptr [rax+rax+00h]
0x1401a5bc6  mov     [rsp+0A0h+var_60], rdi
0x1401a5bcb  mov     [rsp+0A0h+var_68], eax
0x1401a5bcf  mov     [rsp+0A0h+var_70], 5C8h
0x1401a5bd7  jmp     short loc_1401A5BB0
0x1401a5bd9  mov     rbx, [rsi+20h]
0x1401a5bdd  lea     rdx, [rbx+168h]; struct ScopedCS *
0x1401a5be4  lea     rcx, [rbp+57h+var_40]; this
0x1401a5be8  call    ??0ScopedLock@@QEAA@AEAVScopedCS@@@Z; ScopedLock::ScopedLock(ScopedCS &)
0x1401a5bed  nop
0x1401a5bee  mov     [rbp+57h+arg_0], rsi
0x1401a5bf2  lea     rcx, [rbp+57h+var_50]
0x1401a5bf6  call    ??$?0V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@VSlowSyncState@@@std@@@std@@@std@@@std@@_N$0A@@?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@VSlowSyncState@@@std@@@std@@@std@@@std@@_N@std@@QEAA@XZ; std::pair<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,SlowSyncState>>>>,bool>::pair<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,SlowSyncState>>>>,bool>(void)
0x1401a5bfb  lea     rcx, [rbx+1C8h]
0x1401a5c02  lea     r8, [rbp+57h+arg_0]
0x1401a5c06  lea     rdx, [rbp+57h+var_30]
0x1401a5c0a  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@PEAVIUpdateTask@@U?$ComparePointers@VIUpdateTask@@@@V?$allocator@PEAVIUpdateTask@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEAVIUpdateTask@@@std@@@std@@@std@@_N@1@AEBQEAVIUpdateTask@@@Z; std::_Tree<std::_Tset_traits<IUpdateTask *,ComparePointers<IUpdateTask>,std::allocator<IUpdateTask *>,0>>::insert<0,0>(IUpdateTask * const &)
0x1401a5c0f  mov     rdx, rax
0x1401a5c12  lea     rcx, [rbp+57h+var_50]
0x1401a5c16  call    ??$?4U?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVVolumeId@@U?$pair@PEAVAutoFileHandle@@VTimeoutCounter@@@std@@@std@@@std@@@std@@@std@@_N@std@@$0A@@?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVVolumeId@@U?$pair@PEAVAutoFileHandle@@VTimeoutCounter@@@std@@@std@@@std@@@std@@@std@@_N@std@@QEAAAEAU01@$$QEAU01@@Z; std::pair<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<VolumeId const,std::pair<AutoFileHandle *,TimeoutCounter>>>>>,bool>::operator=<std::pair<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<VolumeId const,std::pair<AutoFileHandle *,TimeoutCounter>>>>>,bool>,0>(std::pair<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<VolumeId const,std::pair<AutoFileHandle *,TimeoutCounter>>>>>,bool> &&)
0x1401a5c1b  cmp     [rbp+57h+var_48], dil
0x1401a5c1f  jz      short loc_1401A5C2B
0x1401a5c21  mov     rcx, [rbp+57h+arg_0]; this
0x1401a5c25  call    ?AddRef@RefCountObject@@QEAAJXZ; RefCountObject::AddRef(void)
0x1401a5c2a  nop
0x1401a5c2b  lea     rcx, [rbp+57h+var_40]; this
0x1401a5c2f  call    ??1ScopedLock@@QEAA@XZ; ScopedLock::~ScopedLock(void)
0x1401a5c34  mov     dword ptr [rsi+118h], 4
0x1401a5c3e  lea     rcx, [rsi+30h]; pAsync
0x1401a5c42  xor     edx, edx; fAbort
0x1401a5c44  call    cs:__imp_RpcAsyncCancelCall
0x1401a5c4b  nop     dword ptr [rax+rax+00h]
0x1401a5c50  mov     ebx, eax
0x1401a5c52  call    cs:__imp_GetCurrentThreadId
0x1401a5c59  nop     dword ptr [rax+rax+00h]
0x1401a5c5e  mov     [rsp+0A0h+var_60], rdi
0x1401a5c63  mov     [rsp+0A0h+var_68], eax
0x1401a5c67  mov     [rsp+0A0h+var_70], 59Dh
0x1401a5c6f  mov     edx, ebx
0x1401a5c71  lea     rsi, aCancelcontextC_0; "CancelContext::Cancel"
0x1401a5c78  mov     [rsp+0A0h+var_78], rsi
0x1401a5c7d  lea     r14, aBaseFsRemotefs_70; "base\\fs\\remotefs\\frs\\src\\transport"...
0x1401a5c84  mov     [rsp+0A0h+var_80], r14
0x1401a5c89  mov     r9d, 1
0x1401a5c8f  xor     r8d, r8d
0x1401a5c92  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401a5c97  mov     rbx, rax
0x1401a5c9a  test    rax, rax
0x1401a5c9d  jz      short loc_1401A5CD8
0x1401a5c9f  call    cs:__imp_GetCurrentThreadId
0x1401a5ca6  nop     dword ptr [rax+rax+00h]
0x1401a5cab  mov     [rsp+0A0h+var_60], rbx
0x1401a5cb0  mov     [rsp+0A0h+var_68], eax
0x1401a5cb4  mov     [rsp+0A0h+var_70], 5D5h
0x1401a5cbc  mov     [rsp+0A0h+var_78], rsi
0x1401a5cc1  mov     [rsp+0A0h+var_80], r14
0x1401a5cc6  mov     r9d, [rbx]
0x1401a5cc9  mov     r8d, [rbx+8]
0x1401a5ccd  mov     edx, [rbx+4]
0x1401a5cd0  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401a5cd5  mov     rdi, rax
0x1401a5cd8  lea     rcx, [rbp+57h+arg_8]; this
0x1401a5cdc  call    ??1ScopedCrewLock@@QEAA@XZ; ScopedCrewLock::~ScopedCrewLock(void)
0x1401a5ce1  mov     rax, rdi
0x1401a5ce4  lea     r11, [rsp+0A0h+var_10]
0x1401a5cec  mov     rbx, [r11+30h]
0x1401a5cf0  mov     rsi, [r11+38h]
0x1401a5cf4  mov     rsp, r11
0x1401a5cf7  pop     r14
0x1401a5cf9  pop     rdi
0x1401a5cfa  pop     rbp
0x1401a5cfb  retn
```
