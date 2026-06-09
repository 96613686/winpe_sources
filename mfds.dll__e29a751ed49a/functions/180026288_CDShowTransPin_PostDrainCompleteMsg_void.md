# CDShowTransPin::PostDrainCompleteMsg(void)

- ea: `0x180026288`
- end: `0x180026515`
- name: `?PostDrainCompleteMsg@CDShowTransPin@@QEAAJXZ`
- size: `653`
- prototype: `__int64 __fastcall(CDShowTransPin *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180025c40`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x180026288`
- `0x18002e8a0`
- `0x18002ecc0`
- `0x180032a50`
- `0x180051ce4`
- `0x180053dc0`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800264f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800264f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800264d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800264d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026363`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026406`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026363`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026406`
- `MFPlat!MFCreateMediaEvent` at `0x1800262e5`
- `MFPlat!MFCreateMediaEvent` at `0x1800262e5`

## string_xrefs

- `0x1800262ad`: `CDShowTransPin::PostDrainCompleteMsg`
- `0x1800263cd`: `CDShowTransPin::PostDrainCompleteMsg`
- `0x180026470`: `CDShowTransPin::PostDrainCompleteMsg`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDShowTransPin::PostDrainCompleteMsg(CDShowTransPin *this)
{
  struct CDShowTransRoot *v2; // rbx
  struct CDShowTransRoot *RootObj; // rax
  CallStackTracing *v4; // rcx
  CallStackTracing *v5; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v7; // rdx
  CallStackTracing *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rbx
  DWORD CurrentThreadId; // eax
  CMFSRWLock *v13; // rcx
  unsigned int v14; // ebx
  char v16; // [rsp+68h] [rbp+28h] BYREF
  int v17; // [rsp+70h] [rbp+30h]
  IMFMediaEvent *ppEvent; // [rsp+78h] [rbp+38h] BYREF

  v17 = 0;
  ppEvent = 0;
  v2 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v16, "CDShowTransPin::PostDrainCompleteMsg", 1141);
  v17 = MFCreateMediaEvent(0x25Bu, &GUID_00000000_0000_0000_0000_000000000000, 0, 0, &ppEvent);
  if ( v17 >= 0 )
  {
    v17 = ((__int64 (__fastcall *)(IMFMediaEvent *, const GUID *, _QWORD))ppEvent->lpVtbl->SetUINT32)(
            ppEvent,
            &MF_EVENT_MFT_INPUT_STREAM_ID,
            0);
    if ( v17 >= 0 )
    {
      RootObj = CDShowTransPin::GetRootObj(this, 1);
      v2 = RootObj;
      if ( RootObj )
      {
        v17 = CMediaEventGenerator::QueueEvent((CMediaEventGenerator *)(*((_QWORD *)RootObj + 3) + 88LL), ppEvent);
        if ( v17 < 0 )
        {
          v4 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v5 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
            CallStackTracing::s_wpInstance = v5;
            if ( v5 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v5 + 8LL))(v5, 2032) )
            {
              v4 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v4 = (CallStackTracing *)&qword_1800EB130;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
            }
          }
          if ( *((_BYTE *)v4 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v4);
            if ( v17 < 0 && *((_DWORD *)ThreadRelativeContext + 499) != v17 )
              CallStackContext::TraceFailure(ThreadRelativeContext, "CDShowTransPin::PostDrainCompleteMsg", 1159, v17);
          }
          if ( g_wppLevels )
          {
            v7 = 35;
LABEL_27:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v7,
              &WPP_e67ca36682193615575df34b6326caef_Traceguids,
              this,
              v17);
          }
        }
      }
      else
      {
        v17 = -2147418113;
        v8 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v9;
          if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
          {
            v8 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v8 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v8 + 8) )
        {
          v10 = CallStackTracing::GetThreadRelativeContext(v8);
          if ( v17 < 0 && *((_DWORD *)v10 + 499) != v17 )
            CallStackContext::TraceFailure(v10, "CDShowTransPin::PostDrainCompleteMsg", 1163, v17);
        }
        if ( g_wppLevels )
        {
          v7 = 36;
          goto LABEL_27;
        }
      }
    }
  }
  if ( ppEvent )
  {
    ((void (__fastcall *)(IMFMediaEvent *))ppEvent->lpVtbl->Release)(ppEvent);
    ppEvent = 0;
  }
  if ( v2 )
  {
    v11 = *((_QWORD *)this + 6);
    CurrentThreadId = GetCurrentThreadId();
    v13 = (CMFSRWLock *)(v11 + 80);
    if ( *(_DWORD *)(v11 + 88) == CurrentThreadId )
      CMFSRWLock::UnlockExclusive(v13);
    else
      ReleaseSRWLockShared((PSRWLOCK)v13);
  }
  v14 = v17;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v16);
  return v14;
}

```

## disassembly

```asm
0x180026288  push    rbp
0x18002628a  push    rbx
0x18002628b  push    rdi
0x18002628c  mov     rbp, rsp
0x18002628f  sub     rsp, 40h
0x180026293  mov     rdi, rcx
0x180026296  mov     [rbp+arg_10], 0
0x18002629d  mov     [rbp+arg_18], 0
0x1800262a5  xor     ebx, ebx
0x1800262a7  mov     r8d, 475h; int
0x1800262ad  lea     rdx, aCdshowtranspin_4; "CDShowTransPin::PostDrainCompleteMsg"
0x1800262b4  lea     rcx, [rbp+arg_8]; this
0x1800262b8  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800262bd  nop
0x1800262be  mov     [rbp+var_10], rbx
0x1800262c2  lea     rax, [rbp+arg_10]
0x1800262c6  mov     [rbp+var_8], rax
0x1800262ca  lea     rax, [rbp+arg_18]
0x1800262ce  mov     [rsp+40h+ppEvent], rax; ppEvent
0x1800262d3  xor     r9d, r9d; pvValue
0x1800262d6  xor     r8d, r8d; hrStatus
0x1800262d9  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; guidExtendedType
0x1800262e0  mov     ecx, 25Bh; met
0x1800262e5  call    cs:__imp_MFCreateMediaEvent
0x1800262ec  nop     dword ptr [rax+rax+00h]
0x1800262f1  mov     [rbp+arg_10], eax
0x1800262f4  test    eax, eax
0x1800262f6  js      loc_1800264AE
0x1800262fc  mov     rcx, [rbp+arg_18]
0x180026300  mov     rax, [rcx]
0x180026303  xor     r8d, r8d
0x180026306  lea     rdx, MF_EVENT_MFT_INPUT_STREAM_ID
0x18002630d  mov     rax, [rax+0A8h]
0x180026314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026319  mov     [rbp+arg_10], eax
0x18002631c  test    eax, eax
0x18002631e  js      loc_1800264AE
0x180026324  lea     edx, [rbx+1]; int
0x180026327  mov     rcx, rdi; this
0x18002632a  call    ?GetRootObj@CDShowTransPin@@QEAAPEAVCDShowTransRoot@@H@Z; CDShowTransPin::GetRootObj(int)
0x18002632f  mov     rbx, rax
0x180026332  test    rax, rax
0x180026335  jz      loc_1800263F3
0x18002633b  mov     rcx, [rax+18h]
0x18002633f  add     rcx, 58h ; 'X'; this
0x180026343  mov     rdx, [rbp+arg_18]; struct IMFMediaEvent *
0x180026347  call    ?QueueEvent@CMediaEventGenerator@@UEAAJPEAUIMFMediaEvent@@@Z; CMediaEventGenerator::QueueEvent(IMFMediaEvent *)
0x18002634c  mov     [rbp+arg_10], eax
0x18002634f  test    eax, eax
0x180026351  jns     loc_1800264AE
0x180026357  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002635e  test    rcx, rcx
0x180026361  jnz     short loc_1800263AA
0x180026363  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002636a  nop     dword ptr [rax+rax+00h]
0x18002636f  mov     rcx, rax
0x180026372  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180026379  test    rax, rax
0x18002637c  jz      short loc_18002639C
0x18002637e  mov     rax, [rax]
0x180026381  mov     edx, 7F0h
0x180026386  mov     rax, [rax+8]
0x18002638a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002638f  test    eax, eax
0x180026391  jz      short loc_18002639C
0x180026393  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002639a  jmp     short loc_1800263AA
0x18002639c  lea     rcx, qword_1800EB130; this
0x1800263a3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800263aa  cmp     byte ptr [rcx+8], 0
0x1800263ae  jz      short loc_1800263DC
0x1800263b0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800263b5  mov     r9d, [rbp+arg_10]; int
0x1800263b9  test    r9d, r9d
0x1800263bc  jns     short loc_1800263DC
0x1800263be  cmp     [rax+7CCh], r9d
0x1800263c5  jz      short loc_1800263DC
0x1800263c7  mov     r8d, 487h; int
0x1800263cd  lea     rdx, aCdshowtranspin_4; "CDShowTransPin::PostDrainCompleteMsg"
0x1800263d4  mov     rcx, rax; this
0x1800263d7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800263dc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800263e3  jb      loc_1800264AE
0x1800263e9  mov     edx, 23h ; '#'
0x1800263ee  jmp     loc_18002648D
0x1800263f3  mov     [rbp+arg_10], 8000FFFFh
0x1800263fa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026401  test    rcx, rcx
0x180026404  jnz     short loc_18002644D
0x180026406  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002640d  nop     dword ptr [rax+rax+00h]
0x180026412  mov     rcx, rax
0x180026415  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002641c  test    rax, rax
0x18002641f  jz      short loc_18002643F
0x180026421  mov     rax, [rax]
0x180026424  mov     edx, 7F0h
0x180026429  mov     rax, [rax+8]
0x18002642d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026432  test    eax, eax
0x180026434  jz      short loc_18002643F
0x180026436  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002643d  jmp     short loc_18002644D
0x18002643f  lea     rcx, qword_1800EB130; this
0x180026446  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002644d  cmp     byte ptr [rcx+8], 0
0x180026451  jz      short loc_18002647F
0x180026453  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180026458  mov     r9d, [rbp+arg_10]; int
0x18002645c  test    r9d, r9d
0x18002645f  jns     short loc_18002647F
0x180026461  cmp     [rax+7CCh], r9d
0x180026468  jz      short loc_18002647F
0x18002646a  mov     r8d, 48Bh; int
0x180026470  lea     rdx, aCdshowtranspin_4; "CDShowTransPin::PostDrainCompleteMsg"
0x180026477  mov     rcx, rax; this
0x18002647a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002647f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180026486  jb      short loc_1800264AE
0x180026488  mov     edx, 24h ; '$'
0x18002648d  mov     eax, [rbp+arg_10]
0x180026490  mov     rcx, cs:WPP_GLOBAL_Control
0x180026497  mov     dword ptr [rsp+40h+ppEvent], eax
0x18002649b  mov     r9, rdi
0x18002649e  lea     r8, WPP_e67ca36682193615575df34b6326caef_Traceguids
0x1800264a5  mov     rcx, [rcx+10h]
0x1800264a9  call    WPP_SF_qD
0x1800264ae  mov     rcx, [rbp+arg_18]
0x1800264b2  test    rcx, rcx
0x1800264b5  jz      short loc_1800264CB
0x1800264b7  mov     rax, [rcx]
0x1800264ba  mov     rax, [rax+10h]
0x1800264be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264c3  mov     [rbp+arg_18], 0
0x1800264cb  test    rbx, rbx
0x1800264ce  jz      short loc_1800264FE
0x1800264d0  mov     rbx, [rdi+30h]
0x1800264d4  call    cs:__imp_GetCurrentThreadId
0x1800264db  nop     dword ptr [rax+rax+00h]
0x1800264e0  mov     edx, [rbx+58h]
0x1800264e3  lea     rcx, [rbx+50h]; this
0x1800264e7  cmp     edx, eax
0x1800264e9  jnz     short loc_1800264F2
0x1800264eb  call    ?UnlockExclusive@CMFSRWLock@@QEAAXXZ; CMFSRWLock::UnlockExclusive(void)
0x1800264f0  jmp     short loc_1800264FE
0x1800264f2  call    cs:__imp_ReleaseSRWLockShared
0x1800264f9  nop     dword ptr [rax+rax+00h]
0x1800264fe  mov     ebx, [rbp+arg_10]
0x180026501  lea     rcx, [rbp+arg_8]; this
0x180026505  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18002650a  mov     eax, ebx
0x18002650c  add     rsp, 40h
0x180026510  pop     rdi
0x180026511  pop     rbx
0x180026512  pop     rbp
0x180026513  retn
```
