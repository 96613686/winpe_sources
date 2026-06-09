# IoPortManager::ThreadEntryProc(void)

- ea: `0x14019a5e0`
- end: `0x14019a94a`
- name: `?ThreadEntryProc@IoPortManager@@QEAAXXZ`
- size: `874`
- prototype: `void __fastcall(IoPortManager *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140198e80`

## callees

- `0x14000cb00`
- `0x14000cdc0`
- `0x14000e34c`
- `0x1400c2fc4`
- `0x14019a384`
- `0x14019a5e0`
- `0x1401a85d8`
- `0x1401b6868`
- `0x1401b68a0`
- `0x1401b9494`
- `0x1401bda10`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetQueuedCompletionStatus` at `0x14019a838`
- `KERNEL32!GetQueuedCompletionStatus` at `0x14019a838`
- `KERNEL32!GetLastError` at `0x14019a860`
- `KERNEL32!GetLastError` at `0x14019a8f0`
- `KERNEL32!GetLastError` at `0x14019a860`
- `KERNEL32!GetLastError` at `0x14019a8f0`
- `KERNEL32!GetCurrentThreadId` at `0x14019a6c2`
- `KERNEL32!GetCurrentThreadId` at `0x14019a6fc`
- `KERNEL32!GetCurrentThreadId` at `0x14019a6c2`
- `KERNEL32!GetCurrentThreadId` at `0x14019a6fc`

## string_xrefs

- `0x14019a5fa`: `IoPortManager::ThreadEntryProc`
- `0x14019a89c`: `IoPortManager::ThreadEntryProc`
- `0x14019a8d0`: `(Ignored) Failed to wait on completion port. Error:%d`
- `0x14019a7da`: `(Ignored) Failed IoCompletionProcessVvUp. Error:%?`
- `0x14019a71c`: `IoPortManager::ThreadEntryProc`

## pseudocode

```c
void __fastcall IoPortManager::ThreadEntryProc(IoPortManager *this)
{
  BOOL v2; // r14d
  DWORD CurrentThreadId; // eax
  __int64 v4; // rcx
  __int64 v5; // rax
  DWORD v6; // eax
  __int64 v7; // rcx
  struct FrsStatus **v8; // rcx
  DWORD dwMilliseconds; // eax
  BOOL QueuedCompletionStatus; // eax
  unsigned int v11; // esi
  BOOL v12; // ebx
  int Value; // eax
  __int64 v14; // [rsp+50h] [rbp-49h] BYREF
  struct FrsStatus *v15; // [rsp+58h] [rbp-41h] BYREF
  const wchar_t *v16; // [rsp+60h] [rbp-39h] BYREF
  int v17; // [rsp+68h] [rbp-31h]
  int v18; // [rsp+6Ch] [rbp-2Dh]
  const wchar_t *v19; // [rsp+70h] [rbp-29h]
  const wchar_t *v20; // [rsp+78h] [rbp-21h] BYREF
  int v21; // [rsp+80h] [rbp-19h]
  int v22; // [rsp+84h] [rbp-15h]
  const wchar_t *v23; // [rsp+88h] [rbp-11h]
  const wchar_t *v24; // [rsp+90h] [rbp-9h] BYREF
  int v25; // [rsp+98h] [rbp-1h]
  int v26; // [rsp+9Ch] [rbp+3h]
  const wchar_t *v27; // [rsp+A0h] [rbp+7h]
  const wchar_t *v28; // [rsp+A8h] [rbp+Fh] BYREF
  int v29; // [rsp+B0h] [rbp+17h]
  int v30; // [rsp+B4h] [rbp+1Bh]
  const wchar_t *v31; // [rsp+B8h] [rbp+1Fh]
  DWORD LastError; // [rsp+100h] [rbp+67h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+108h] [rbp+6Fh] BYREF
  unsigned __int64 CompletionKey; // [rsp+110h] [rbp+77h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+118h] [rbp+7Fh] BYREF

  NumberOfBytesTransferred = 0;
  Overlapped = 0;
  v2 = 0;
  LastError = 0;
  CompletionKey = 1;
  do
  {
    switch ( CompletionKey )
    {
      case 1uLL:
        LastError = 0;
        _InterlockedAdd((volatile signed __int32 *)this + 4, 1u);
        CompletionKey = 0;
        dwMilliseconds = Settings::GenericDwordSetting::operator()(&Settings::CompletionPortTimeoutMs);
        QueuedCompletionStatus = GetQueuedCompletionStatus(
                                   *((HANDLE *)this + 1),
                                   &NumberOfBytesTransferred,
                                   &CompletionKey,
                                   &Overlapped,
                                   dwMilliseconds);
        v11 = _InterlockedDecrement((volatile signed __int32 *)this + 4);
        if ( !QueuedCompletionStatus )
        {
          if ( !Overlapped )
          {
            LastError = GetLastError();
            if ( LastError == 258 )
            {
              v12 = v11 >= (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::CompletionPortWaitThreadsMaxCount);
              Value = TaskPool::ThreadCounterQueryValue();
              CompletionKey = 1;
              v2 = 0;
              if ( !Value )
                v2 = v12;
            }
            else if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
            {
              v28 = L"IoPortManager::ThreadEntryProc";
              v31 = L"RPCN";
              v29 = 1126;
              v30 = 2;
              dbgobj::DbgPrint<unsigned short,unsigned int>(
                &v28,
                L"(Ignored) Failed to wait on completion port. Error:%d",
                &LastError);
            }
            break;
          }
          LastError = GetLastError();
        }
        if ( CompletionKey == 2 )
          goto LABEL_46;
        if ( v11 < (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::CompletionPortWaitThreadsMinCount) )
          IoPortManager::SpinUpNewThread(this);
        break;
      case 3uLL:
      case 4uLL:
      case 5uLL:
      case 6uLL:
        v15 = AsyncRpcHandler::ProcessReceive((AsyncRpcHandler *)Overlapped);
        if ( v15 )
        {
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
          {
            v24 = L"IoPortManager::ThreadEntryProc";
            v25 = 1185;
            v26 = 2;
            v27 = L"RPCN";
            dbgobj::DbgPrint<unsigned short,FrsStatus>(&v24, L"(Ignored) Failed IoCompletionProcessVvUp. Error:%?", v15);
          }
          v8 = &v15;
LABEL_30:
          CLEAR_ERROR(v8);
        }
LABEL_23:
        CompletionKey = 1;
        break;
      case 7uLL:
        (*(void (__fastcall **)(LPOVERLAPPED))(Overlapped->Internal + 8))(Overlapped);
        goto LABEL_23;
      case 8uLL:
        if ( Settings::GhostingEnabled )
        {
          CurrentThreadId = GetCurrentThreadId();
          v5 = FrsStatusList::PushNewError(
                 v4,
                 50,
                 0,
                 1,
                 "base\\fs\\remotefs\\frs\\src\\ghosting\\frsfilterclient.cpp",
                 "FrsFilter::ProcessReceivedMessage",
                 153,
                 CurrentThreadId,
                 0);
        }
        else
        {
          v6 = GetCurrentThreadId();
          v5 = FrsStatusList::PushNewError(
                 v7,
                 9305,
                 0,
                 3,
                 "base\\fs\\remotefs\\frs\\src\\transport\\rpcnetwork.cpp",
                 "IoPortManager::ThreadEntryProc",
                 1209,
                 v6,
                 0);
        }
        v14 = v5;
        if ( v5 )
        {
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
          {
            v20 = L"IoPortManager::ThreadEntryProc";
            v21 = 1221;
            v22 = 2;
            v23 = L"RPCN";
            dbgobj::DbgPrint<unsigned short,FrsStatus>(&v20, L"Failed to process received message. Error:%?", v5);
          }
          v8 = (struct FrsStatus **)&v14;
          goto LABEL_30;
        }
        goto LABEL_23;
      default:
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
        {
          v16 = L"IoPortManager::ThreadEntryProc";
          v17 = 1231;
          v18 = 2;
          v19 = L"RPCN";
          dbgobj::DbgPrint<unsigned short,unsigned __int64,unsigned long>(
            &v16,
            L"(Ignored) Failed, unrecognised key:%d status:%?",
            &CompletionKey,
            &LastError);
        }
        break;
    }
  }
  while ( !v2 );
LABEL_46:
  _InterlockedDecrement((volatile signed __int32 *)this + 5);
  TaskPool::ThreadCounterRelease();
}

```

## disassembly

```asm
0x14019a5e0  push    rbp
0x14019a5e2  push    rbx
0x14019a5e3  push    rsi
0x14019a5e4  push    rdi
0x14019a5e5  push    r13
0x14019a5e7  push    r14
0x14019a5e9  push    r15
0x14019a5eb  lea     rbp, [rsp-27h]
0x14019a5f0  sub     rsp, 0C0h
0x14019a5f7  xor     r15d, r15d
0x14019a5fa  lea     rbx, aIoportmanagerT; "IoPortManager::ThreadEntryProc"
0x14019a601  mov     rdi, rcx
0x14019a604  mov     [rbp+57h+NumberOfBytesTransferred], r15d
0x14019a608  mov     [rbp+57h+Overlapped], r15
0x14019a60c  lea     rsi, aRpcn; "RPCN"
0x14019a613  mov     r14d, r15d
0x14019a616  mov     [rbp+57h+arg_0], r15d
0x14019a61a  lea     r13d, [r15+1]
0x14019a61e  mov     [rbp+57h+CompletionKey], r13
0x14019a622  mov     rax, [rbp+57h+CompletionKey]
0x14019a626  sub     rax, r13
0x14019a629  jz      loc_14019A80B
0x14019a62f  sub     rax, 2
0x14019a633  jz      loc_14019A7AD
0x14019a639  sub     rax, r13
0x14019a63c  jz      loc_14019A7AD
0x14019a642  sub     rax, r13
0x14019a645  jz      loc_14019A7AD
0x14019a64b  sub     rax, r13
0x14019a64e  jz      loc_14019A7AD
0x14019a654  sub     rax, r13
0x14019a657  jz      loc_14019A794
0x14019a65d  cmp     rax, r13
0x14019a660  jz      short loc_14019A6B9
0x14019a662  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14019a669  test    rax, rax
0x14019a66c  jz      loc_14019A925
0x14019a672  cmp     [rax+40h], r15d
0x14019a676  jz      loc_14019A925
0x14019a67c  cmp     dword ptr [rax+38h], 2
0x14019a680  jl      loc_14019A925
0x14019a686  lea     r9, [rbp+57h+arg_0]
0x14019a68a  mov     [rbp+57h+var_90], rbx
0x14019a68e  lea     r8, [rbp+57h+CompletionKey]
0x14019a692  mov     [rbp+57h+var_88], 4CFh
0x14019a699  lea     rdx, aIgnoredFailedU_1; "(Ignored) Failed, unrecognised key:%d s"...
0x14019a6a0  mov     [rbp+57h+var_84], 2
0x14019a6a7  lea     rcx, [rbp+57h+var_90]
0x14019a6ab  mov     [rbp+57h+var_80], rsi
0x14019a6af  call    ??$DbgPrint@G_KK@dbgobj@@QEAA_KPEBGAEB_KAEBK@Z; dbgobj::DbgPrint<ushort,unsigned __int64,ulong>(ushort const *,unsigned __int64 const &,ulong const &)
0x14019a6b4  jmp     loc_14019A925
0x14019a6b9  cmp     cs:?GhostingEnabled@Settings@@3VGenericBoolSetting@1@A, r15d; Settings::GenericBoolSetting Settings::GhostingEnabled
0x14019a6c0  jz      short loc_14019A6FC
0x14019a6c2  call    cs:__imp_GetCurrentThreadId
0x14019a6c9  nop     dword ptr [rax+rax+00h]
0x14019a6ce  mov     [rsp+0F0h+var_B0], r15
0x14019a6d3  mov     r9d, r13d
0x14019a6d6  mov     [rsp+0F0h+var_B8], eax
0x14019a6da  mov     edx, 32h ; '2'
0x14019a6df  lea     rax, aFrsfilterProce; "FrsFilter::ProcessReceivedMessage"
0x14019a6e6  mov     [rsp+0F0h+var_C0], 99h
0x14019a6ee  mov     [rsp+0F0h+var_C8], rax
0x14019a6f3  lea     rax, aBaseFsRemotefs_88; "base\\fs\\remotefs\\frs\\src\\ghosting"...
0x14019a6fa  jmp     short loc_14019A737
0x14019a6fc  call    cs:__imp_GetCurrentThreadId
0x14019a703  nop     dword ptr [rax+rax+00h]
0x14019a708  mov     [rsp+0F0h+var_B0], r15
0x14019a70d  mov     r9d, 3
0x14019a713  mov     [rsp+0F0h+var_B8], eax
0x14019a717  mov     edx, 2459h
0x14019a71c  lea     rax, aIoportmanagerT_0; "IoPortManager::ThreadEntryProc"
0x14019a723  mov     [rsp+0F0h+var_C0], 4B9h
0x14019a72b  mov     [rsp+0F0h+var_C8], rax
0x14019a730  lea     rax, aBaseFsRemotefs_16; "base\\fs\\remotefs\\frs\\src\\transport"...
0x14019a737  xor     r8d, r8d
0x14019a73a  mov     qword ptr [rsp+0F0h+dwMilliseconds], rax
0x14019a73f  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14019a744  mov     [rbp+57h+var_A0], rax
0x14019a748  mov     r8, rax
0x14019a74b  test    rax, rax
0x14019a74e  jz      short loc_14019A7A4
0x14019a750  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14019a757  test    rax, rax
0x14019a75a  jz      short loc_14019A78E
0x14019a75c  cmp     [rax+40h], r15d
0x14019a760  jz      short loc_14019A78E
0x14019a762  cmp     dword ptr [rax+38h], 2
0x14019a766  jl      short loc_14019A78E
0x14019a768  lea     rdx, aFailedToProces_13; "Failed to process received message. Err"...
0x14019a76f  mov     [rbp+57h+var_78], rbx
0x14019a773  lea     rcx, [rbp+57h+var_78]
0x14019a777  mov     [rbp+57h+var_70], 4C5h
0x14019a77e  mov     [rbp+57h+var_6C], 2
0x14019a785  mov     [rbp+57h+var_68], rsi
0x14019a789  call    ??$DbgPrint@GVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,FrsStatus>(ushort const *,FrsStatus const &)
0x14019a78e  lea     rcx, [rbp+57h+var_A0]
0x14019a792  jmp     short loc_14019A804
0x14019a794  mov     rcx, [rbp+57h+Overlapped]
0x14019a798  mov     rax, [rcx]
0x14019a79b  mov     rax, [rax+8]
0x14019a79f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14019a7a4  mov     [rbp+57h+CompletionKey], r13
0x14019a7a8  jmp     loc_14019A925
0x14019a7ad  mov     rcx, [rbp+57h+Overlapped]; this
0x14019a7b1  call    ?ProcessReceive@AsyncRpcHandler@@QEAAPEAVFrsStatus@@XZ; AsyncRpcHandler::ProcessReceive(void)
0x14019a7b6  mov     [rbp+57h+var_98], rax
0x14019a7ba  mov     r8, rax
0x14019a7bd  test    rax, rax
0x14019a7c0  jz      short loc_14019A7A4
0x14019a7c2  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14019a7c9  test    rax, rax
0x14019a7cc  jz      short loc_14019A800
0x14019a7ce  cmp     [rax+40h], r15d
0x14019a7d2  jz      short loc_14019A800
0x14019a7d4  cmp     dword ptr [rax+38h], 2
0x14019a7d8  jl      short loc_14019A800
0x14019a7da  lea     rdx, aIgnoredFailedI; "(Ignored) Failed IoCompletionProcessVvU"...
0x14019a7e1  mov     [rbp+57h+var_60], rbx
0x14019a7e5  lea     rcx, [rbp+57h+var_60]
0x14019a7e9  mov     [rbp+57h+var_58], 4A1h
0x14019a7f0  mov     [rbp+57h+var_54], 2
0x14019a7f7  mov     [rbp+57h+var_50], rsi
0x14019a7fb  call    ??$DbgPrint@GVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,FrsStatus>(ushort const *,FrsStatus const &)
0x14019a800  lea     rcx, [rbp+57h+var_98]; struct FrsStatus **
0x14019a804  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x14019a809  jmp     short loc_14019A7A4
0x14019a80b  mov     [rbp+57h+arg_0], r15d
0x14019a80f  lock add [rdi+10h], r13d
0x14019a814  lea     rcx, ?CompletionPortTimeoutMs@Settings@@3VCCompletionPortTimeoutMs@1@A; Settings::CCompletionPortTimeoutMs Settings::CompletionPortTimeoutMs
0x14019a81b  mov     [rbp+57h+CompletionKey], r15
0x14019a81f  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x14019a824  mov     rcx, [rdi+8]; CompletionPort
0x14019a828  lea     r9, [rbp+57h+Overlapped]; lpOverlapped
0x14019a82c  lea     r8, [rbp+57h+CompletionKey]; lpCompletionKey
0x14019a830  mov     [rsp+0F0h+dwMilliseconds], eax; dwMilliseconds
0x14019a834  lea     rdx, [rbp+57h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x14019a838  call    cs:__imp_GetQueuedCompletionStatus
0x14019a83f  nop     dword ptr [rax+rax+00h]
0x14019a844  or      esi, 0FFFFFFFFh
0x14019a847  lock xadd [rdi+10h], esi
0x14019a84c  dec     esi
0x14019a84e  test    eax, eax
0x14019a850  jnz     loc_14019A8FF
0x14019a856  cmp     [rbp+57h+Overlapped], r15
0x14019a85a  jnz     loc_14019A8F0
0x14019a860  call    cs:__imp_GetLastError
0x14019a867  nop     dword ptr [rax+rax+00h]
0x14019a86c  mov     [rbp+57h+arg_0], eax
0x14019a86f  cmp     eax, 102h
0x14019a874  jnz     short loc_14019A8A5
0x14019a876  lea     rcx, ?CompletionPortWaitThreadsMaxCount@Settings@@3VCCompletionPortWaitThreadsMaxCount@1@A; Settings::CCompletionPortWaitThreadsMaxCount Settings::CompletionPortWaitThreadsMaxCount
0x14019a87d  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x14019a882  cmp     esi, eax
0x14019a884  mov     ebx, r15d
0x14019a887  setnb   bl
0x14019a88a  call    ?ThreadCounterQueryValue@TaskPool@@SAJXZ; TaskPool::ThreadCounterQueryValue(void)
0x14019a88f  test    eax, eax
0x14019a891  mov     [rbp+57h+CompletionKey], r13
0x14019a895  mov     r14d, r15d
0x14019a898  cmovz   r14d, ebx
0x14019a89c  lea     rbx, aIoportmanagerT; "IoPortManager::ThreadEntryProc"
0x14019a8a3  jmp     short loc_14019A91E
0x14019a8a5  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14019a8ac  test    rax, rax
0x14019a8af  jz      short loc_14019A91E
0x14019a8b1  cmp     [rax+40h], r15d
0x14019a8b5  jz      short loc_14019A91E
0x14019a8b7  cmp     dword ptr [rax+38h], 2
0x14019a8bb  jl      short loc_14019A91E
0x14019a8bd  lea     rsi, aRpcn; "RPCN"
0x14019a8c4  mov     [rbp+57h+var_48], rbx
0x14019a8c8  lea     r8, [rbp+57h+arg_0]
0x14019a8cc  mov     [rbp+57h+var_38], rsi
0x14019a8d0  lea     rdx, aIgnoredFailedT_85; "(Ignored) Failed to wait on completion "...
0x14019a8d7  mov     [rbp+57h+var_40], 466h
0x14019a8de  lea     rcx, [rbp+57h+var_48]
0x14019a8e2  mov     [rbp+57h+var_3C], 2
0x14019a8e9  call    ??$DbgPrint@GI@dbgobj@@QEAA_KPEBGAEBI@Z; dbgobj::DbgPrint<ushort,uint>(ushort const *,uint const &)
0x14019a8ee  jmp     short loc_14019A925
0x14019a8f0  call    cs:__imp_GetLastError
0x14019a8f7  nop     dword ptr [rax+rax+00h]
0x14019a8fc  mov     [rbp+57h+arg_0], eax
0x14019a8ff  cmp     [rbp+57h+CompletionKey], 2
0x14019a904  jz      short loc_14019A92E
0x14019a906  lea     rcx, ?CompletionPortWaitThreadsMinCount@Settings@@3VCCompletionPortWaitThreadsMinCount@1@A; Settings::CCompletionPortWaitThreadsMinCount Settings::CompletionPortWaitThreadsMinCount
0x14019a90d  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x14019a912  cmp     esi, eax
0x14019a914  jnb     short loc_14019A91E
0x14019a916  mov     rcx, rdi; this
0x14019a919  call    ?SpinUpNewThread@IoPortManager@@QEAAKXZ; IoPortManager::SpinUpNewThread(void)
0x14019a91e  lea     rsi, aRpcn; "RPCN"
0x14019a925  test    r14d, r14d
0x14019a928  jz      loc_14019A622
0x14019a92e  lock dec dword ptr [rdi+14h]
0x14019a932  call    ?ThreadCounterRelease@TaskPool@@SAXXZ; TaskPool::ThreadCounterRelease(void)
0x14019a937  add     rsp, 0C0h
0x14019a93e  pop     r15
0x14019a940  pop     r14
0x14019a942  pop     r13
0x14019a944  pop     rdi
0x14019a945  pop     rsi
0x14019a946  pop     rbx
0x14019a947  pop     rbp
0x14019a948  retn
```
