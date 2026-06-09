# CGroupPolicySession::QueueItemForPolicyApplication(ushort *,ulong,int,void *,IPolicyApplier *,void *,void *,int,int)

- ea: `0x180011ee0`
- end: `0x180012535`
- name: `?QueueItemForPolicyApplication@CGroupPolicySession@@QEAAKPEAGKHPEAXPEAVIPolicyApplier@@11HH@Z`
- size: `1621`
- prototype: `unsigned int __usercall@<eax>(CGroupPolicySession *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned int@<r8d>, int@<r9d>, void *, struct IPolicyApplier *, void *, void *, int, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180010760`
- `0x18004a260`

## callees

- `0x180011ca0`
- `0x180011ee0`
- `0x180014080`
- `0x1800183d4`
- `0x180075ec0`
- `0x18008a1c0`
- `0x18008a2c8`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011fa7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011fa7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011fca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011fca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012174`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800124c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012174`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800124c1`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180012032`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180012032`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011fdf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011fdf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001213d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012181`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001213d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012181`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180011f38`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001207e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180011f38`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001207e`
- `ntdll!EtwEventWrite` at `0x180012127`
- `ntdll!EtwEventWrite` at `0x180012127`
- `ntdll!EtwEventActivityIdControl` at `0x180012199`
- `ntdll!EtwEventActivityIdControl` at `0x180012199`

## string_xrefs

- `0x1800124e2`: `CGroupPolicySession::QueueItemForPolicyApplication::-- (Status: %ld, Thread: %p)`
- `0x18001251e`: `CGroupPolicySession::QueueItemForPolicyApplication::-- (Status: %ld, Thread: %p)`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CGroupPolicySession::QueueItemForPolicyApplication(
        CGroupPolicySession *this,
        unsigned __int16 *a2,
        unsigned int a3,
        int a4,
        void *a5,
        struct IPolicyApplier *a6,
        void *a7,
        void *a8,
        unsigned int a9,
        unsigned int a10)
{
  unsigned int v11; // r13d
  unsigned int v12; // r12d
  DWORD TickCount; // edi
  __int64 v14; // rcx
  __int64 v15; // r8
  struct _RTL_CRITICAL_SECTION *v16; // rsi
  int v17; // r15d
  _QWORD *v18; // rax
  void *v19; // rsi
  HANDLE Thread; // rax
  int v21; // ecx
  void (*v22)(unsigned int, const unsigned __int16 *, ...); // r9
  int v23; // edx
  DWORD LastError; // r15d
  int v25; // edx
  __int64 v26; // rcx
  _QWORD *v27; // rax
  unsigned int EventDataDescriptorStorage; // eax
  _QWORD *v29; // rsi
  unsigned int v30; // edi
  __int64 v31; // rax
  unsigned __int64 v32; // r14
  __int64 v33; // r8
  unsigned int v35; // eax
  CStatusMessage *Instance; // rsi
  const wchar_t *v37; // r8
  const wchar_t *v38; // r8
  DWORD v39; // [rsp+50h] [rbp-28h] BYREF
  CGroupPolicySession *v40; // [rsp+58h] [rbp-20h]
  HLOCAL hMem; // [rsp+60h] [rbp-18h] BYREF
  __int64 v42; // [rsp+68h] [rbp-10h]
  int v43; // [rsp+C0h] [rbp+48h] BYREF
  unsigned __int16 *v44; // [rsp+C8h] [rbp+50h]
  unsigned int v45; // [rsp+D0h] [rbp+58h]
  int v46; // [rsp+D8h] [rbp+60h]

  v46 = a4;
  v45 = a3;
  v44 = a2;
  v11 = a10;
  v12 = a9;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(
        4u,
        L"CGroupPolicySession::QueueItemForPolicyApplication::++ (bTriggered: %ld, bConsole: %ld)",
        a9,
        a10);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(
        4u,
        L"CGroupPolicySession::QueueItemForPolicyApplication::++ (bTriggered: %ld, bConsole: %ld)",
        a9,
        a10);
    }
  }
  v40 = this;
  if ( this )
    (**(void (__fastcall ***)(CGroupPolicySession *))this)(this);
  TickCount = GetTickCount();
  if ( this )
    (**(void (__fastcall ***)(CGroupPolicySession *))this)(this);
  v14 = *((_QWORD *)this + 26);
  if ( v14 && *(_QWORD *)(v14 + 8) )
  {
    LastError = 0;
    (*(void (__fastcall **)(CGroupPolicySession *))(*(_QWORD *)this + 8LL))(this);
    goto LABEL_19;
  }
  (*(void (__fastcall **)(CGroupPolicySession *))(*(_QWORD *)this + 8LL))(this);
  if ( !(unsigned int)CGroupPolicySession::IsPolicyApplicationInProgress(this) )
  {
    v16 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 34);
    if ( v16 )
    {
      v17 = 0;
      a6 = (struct IPolicyApplier *)*((_QWORD *)this + 34);
      EnterCriticalSection(v16);
      if ( !(unsigned int)CGroupPolicySession::IsPolicyApplicationInProgress(this) )
      {
        v17 = 1;
        *((_DWORD *)this + 56) = 1;
      }
      LeaveCriticalSection(v16);
      if ( v17 )
      {
        v18 = LocalAlloc(0x40u, 0x28u);
        v19 = v18;
        if ( v18 )
        {
          v18[1] = a5;
          v18[2] = a7;
          v18[3] = a8;
          *v18 = this;
          *((_DWORD *)v18 + 8) = v12;
          *((_DWORD *)v18 + 9) = v11;
          *((_QWORD *)this + 41) = 0;
          Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CGroupPolicySession::ApplyGroupPolicyThread, v18, 0, 0);
          *((_QWORD *)this + 45) = Thread;
          if ( !Thread )
          {
            LastError = GetLastError();
            LocalFree(v19);
            goto LABEL_19;
          }
        }
      }
    }
    else
    {
      v21 = *(_DWORD *)&g_dwDebugLevel;
      v22 = g_lpDebugMsg;
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_16;
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"Policy Applier Critical Section is NULL");
      }
      else
      {
        if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
          goto LABEL_16;
        RedirectDebugMsg(2u, L"Policy Applier Critical Section is NULL", v15, 0);
      }
    }
  }
  v21 = *(_DWORD *)&g_dwDebugLevel;
  v22 = g_lpDebugMsg;
LABEL_16:
  v23 = *((_DWORD *)this + 99);
  if ( (unsigned int)(v23 - 1) <= 1 )
  {
    if ( v21 )
    {
      if ( v22 )
      {
        v37 = L"Async";
        if ( v23 != 1 )
          v37 = L"Background";
        v22(4u, L"CGroupPolicySession::QueueItemForPolicyApplication::Applying policy in %s.", v37);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v38 = L"Async";
        if ( v23 != 1 )
          v38 = L"Background";
        RedirectDebugMsg(4u, L"CGroupPolicySession::QueueItemForPolicyApplication::Applying policy in %s.", v38);
      }
    }
LABEL_18:
    LastError = 0;
    goto LABEL_19;
  }
  if ( v12 )
  {
    if ( v21 )
    {
      if ( v22 )
      {
        v22(4u, L"CGroupPolicySession::QueueItemForPolicyApplication::Applying policy via a triggered start.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(
          4u,
          L"CGroupPolicySession::QueueItemForPolicyApplication::Applying policy via a triggered start.");
      }
    }
    goto LABEL_18;
  }
  if ( v21 )
  {
    if ( v22 )
    {
      v22(4u, L"CGroupPolicySession::QueueItemForPolicyApplication::Applying policy in Sync");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"CGroupPolicySession::QueueItemForPolicyApplication::Applying policy in Sync");
    }
  }
  Instance = CStatusMessage::GetInstance();
  v43 = 0;
  LastError = (*(__int64 (__fastcall **)(char *, int *))(*((_QWORD *)this + 23) + 16LL))((char *)this + 184, &v43);
  if ( !LastError && Instance )
  {
    LastError = CStatusMessage::UpdateWinlogonStatusMessage(
                  Instance,
                  *((void **)this + 35),
                  *((void **)this + 36),
                  *((void **)this + 39),
                  (int *)this + 76,
                  v43,
                  v44,
                  v45,
                  v46);
    hMem = 0;
    v42 = 0;
    COperationalBaseEvent::ReportOperationalEvent(
      (COperationalBaseEvent *)&hMem,
      &CSE_WINLOGON_STATUS_REPORTING_COMPLETED);
  }
LABEL_19:
  hMem = 0;
  v42 = 0;
  v39 = GetTickCount() - TickCount;
  LODWORD(a6) = v43;
  if ( !COperationalBaseEvent::VerifyAndAllocateEventDataDescriptorStorage((COperationalBaseEvent *)&hMem) )
  {
    v25 = HIDWORD(v42);
    v26 = 2LL * HIDWORD(v42);
    v27 = hMem;
    *((_QWORD *)hMem + v26) = &a6;
    v27[v26 + 1] = 4;
    HIDWORD(v42) = v25 + 1;
  }
  EventDataDescriptorStorage = COperationalBaseEvent::VerifyAndAllocateEventDataDescriptorStorage((COperationalBaseEvent *)&hMem);
  v29 = hMem;
  v30 = HIDWORD(v42);
  if ( !EventDataDescriptorStorage )
  {
    v31 = 2LL * HIDWORD(v42);
    *((_QWORD *)hMem + v31) = &v39;
    v29[v31 + 1] = 4;
    HIDWORD(v42) = ++v30;
  }
  v32 = CGPServiceEventReporting::s_pEventProviderHandle;
  v33 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( *(_BYTE *)(v33 + 8) == 1 )
  {
    v35 = EtwEventActivityIdControl(2, v33 + 16);
    if ( v35 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(
            2u,
            L"COperationalBaseEvent::ReportOperationalEvent: Failed to set the activity id with error 0x%x",
            v35);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(
            2u,
            L"COperationalBaseEvent::ReportOperationalEvent: Failed to set the activity id with error 0x%x",
            v35);
        }
      }
    }
  }
  if ( (unsigned int)EtwEventWrite(v32, gpEvent_GP_SESSION_RETURN_WINLOGON_CALL, v30, v29) )
    GetLastError();
  if ( v29 )
    LocalFree(v29);
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(
        4u,
        L"CGroupPolicySession::QueueItemForPolicyApplication::-- (Status: %ld, Thread: %p)",
        LastError,
        *((_QWORD *)this + 45));
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(
        4u,
        L"CGroupPolicySession::QueueItemForPolicyApplication::-- (Status: %ld, Thread: %p)",
        LastError,
        *((_QWORD *)this + 45));
    }
  }
  (*(void (__fastcall **)(CGroupPolicySession *))(*(_QWORD *)this + 8LL))(this);
  return LastError;
}

```

## disassembly

```asm
0x180011ee0  mov     [rsp-40h+arg_18], r9d
0x180011ee5  mov     [rsp-40h+arg_10], r8d
0x180011eea  mov     [rsp-40h+arg_8], rdx
0x180011eef  push    rbp
0x180011ef0  push    rbx
0x180011ef1  push    rsi
0x180011ef2  push    rdi
0x180011ef3  push    r12
0x180011ef5  push    r13
0x180011ef7  push    r14
0x180011ef9  push    r15
0x180011efb  mov     rbp, rsp
0x180011efe  sub     rsp, 78h
0x180011f02  mov     rbx, rcx
0x180011f05  mov     r13d, [rbp+arg_48]
0x180011f0c  mov     r12d, [rbp+arg_40]
0x180011f13  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x180011f1a  jnz     loc_18001224A
0x180011f20  mov     [rbp+var_20], rbx
0x180011f24  test    rbx, rbx
0x180011f27  jz      short loc_180011F38
0x180011f29  mov     rax, [rbx]
0x180011f2c  mov     rcx, rbx
0x180011f2f  mov     rax, [rax]
0x180011f32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f37  nop
0x180011f38  call    cs:__imp_GetTickCount
0x180011f3e  mov     edi, eax
0x180011f40  test    rbx, rbx
0x180011f43  jz      short loc_180011F53
0x180011f45  mov     rcx, [rbx]
0x180011f48  mov     rax, [rcx]
0x180011f4b  mov     rcx, rbx
0x180011f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f53  mov     rcx, [rbx+0D0h]
0x180011f5a  test    rcx, rcx
0x180011f5d  jz      short loc_180011F6A
0x180011f5f  cmp     qword ptr [rcx+8], 0
0x180011f64  jnz     loc_1800122AA
0x180011f6a  mov     rax, [rbx]
0x180011f6d  mov     rcx, rbx
0x180011f70  mov     rax, [rax+8]
0x180011f74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f79  nop
0x180011f7a  mov     rcx, rbx; this
0x180011f7d  call    ?IsPolicyApplicationInProgress@CGroupPolicySession@@QEAAHXZ; CGroupPolicySession::IsPolicyApplicationInProgress(void)
0x180011f82  xor     r14d, r14d
0x180011f85  test    eax, eax
0x180011f87  jnz     loc_180012048
0x180011f8d  mov     rsi, [rbx+110h]
0x180011f94  test    rsi, rsi
0x180011f97  jz      loc_180012213
0x180011f9d  mov     r15d, r14d
0x180011fa0  mov     [rbp+arg_28], rsi
0x180011fa4  mov     rcx, rsi; lpCriticalSection
0x180011fa7  call    cs:__imp_EnterCriticalSection
0x180011fad  nop
0x180011fae  mov     rcx, rbx; this
0x180011fb1  call    ?IsPolicyApplicationInProgress@CGroupPolicySession@@QEAAHXZ; CGroupPolicySession::IsPolicyApplicationInProgress(void)
0x180011fb6  test    eax, eax
0x180011fb8  jnz     short loc_180011FC7
0x180011fba  mov     r15d, 1
0x180011fc0  mov     [rbx+0E0h], r15d
0x180011fc7  mov     rcx, rsi; lpCriticalSection
0x180011fca  call    cs:__imp_LeaveCriticalSection
0x180011fd0  test    r15d, r15d
0x180011fd3  jz      short loc_180012048
0x180011fd5  mov     edx, 28h ; '('; uBytes
0x180011fda  mov     ecx, 40h ; '@'; uFlags
0x180011fdf  call    cs:__imp_LocalAlloc
0x180011fe5  mov     rsi, rax
0x180011fe8  test    rax, rax
0x180011feb  jz      short loc_180012048
0x180011fed  mov     rcx, [rbp+arg_20]
0x180011ff1  mov     [rax+8], rcx
0x180011ff5  mov     rcx, [rbp+arg_30]
0x180011ff9  mov     [rax+10h], rcx
0x180011ffd  mov     rcx, [rbp+arg_38]
0x180012004  mov     [rax+18h], rcx
0x180012008  mov     [rax], rbx
0x18001200b  mov     [rax+20h], r12d
0x18001200f  mov     [rax+24h], r13d
0x180012013  mov     [rbx+148h], r14
0x18001201a  mov     [rsp+78h+lpThreadId], r14; lpThreadId
0x18001201f  mov     [rsp+78h+dwCreationFlags], r14d; dwCreationFlags
0x180012024  mov     r9, rax; lpParameter
0x180012027  lea     r8, ?ApplyGroupPolicyThread@CGroupPolicySession@@CAKPEAX@Z; lpStartAddress
0x18001202e  xor     edx, edx; dwStackSize
0x180012030  xor     ecx, ecx; lpThreadAttributes
0x180012032  call    cs:__imp_CreateThread
0x180012038  mov     [rbx+168h], rax
0x18001203f  test    rax, rax
0x180012042  jz      loc_180012174
0x180012048  mov     ecx, cs:?g_dwDebugLevel@@3KA; ulong g_dwDebugLevel
0x18001204e  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180012055  mov     edx, [rbx+18Ch]
0x18001205b  lea     eax, [rdx-1]
0x18001205e  cmp     eax, 1
0x180012061  ja      loc_1800121E0
0x180012067  test    ecx, ecx
0x180012069  jnz     loc_18001240A
0x18001206f  mov     r15d, r14d
0x180012072  mov     [rbp+hMem], r14
0x180012076  mov     [rbp+var_10], 0
0x18001207e  call    cs:__imp_GetTickCount
0x180012084  sub     eax, edi
0x180012086  mov     [rbp+var_28], eax
0x180012089  mov     eax, [rbp+arg_0]
0x18001208c  mov     dword ptr [rbp+arg_28], eax
0x18001208f  lea     rcx, [rbp+hMem]; this
0x180012093  call    ?VerifyAndAllocateEventDataDescriptorStorage@COperationalBaseEvent@@AEAAKXZ; COperationalBaseEvent::VerifyAndAllocateEventDataDescriptorStorage(void)
0x180012098  test    eax, eax
0x18001209a  jnz     short loc_1800120BE
0x18001209c  mov     edx, dword ptr [rbp+var_10+4]
0x18001209f  mov     ecx, edx
0x1800120a1  add     rcx, rcx
0x1800120a4  mov     rax, [rbp+hMem]
0x1800120a8  lea     r8, [rbp+arg_28]
0x1800120ac  mov     [rax+rcx*8], r8
0x1800120b0  mov     qword ptr [rax+rcx*8+8], 4
0x1800120b9  inc     edx
0x1800120bb  mov     dword ptr [rbp+var_10+4], edx
0x1800120be  lea     rcx, [rbp+hMem]; this
0x1800120c2  call    ?VerifyAndAllocateEventDataDescriptorStorage@COperationalBaseEvent@@AEAAKXZ; COperationalBaseEvent::VerifyAndAllocateEventDataDescriptorStorage(void)
0x1800120c7  mov     rsi, [rbp+hMem]
0x1800120cb  test    eax, eax
0x1800120cd  jnz     loc_180012484
0x1800120d3  mov     edi, dword ptr [rbp+var_10+4]
0x1800120d6  mov     eax, edi
0x1800120d8  add     rax, rax
0x1800120db  lea     rcx, [rbp+var_28]
0x1800120df  mov     [rsi+rax*8], rcx
0x1800120e3  mov     qword ptr [rsi+rax*8+8], 4
0x1800120ec  inc     edi
0x1800120ee  mov     dword ptr [rbp+var_10+4], edi
0x1800120f1  mov     r14, cs:?s_pEventProviderHandle@CGPServiceEventReporting@@0_KA; unsigned __int64 CGPServiceEventReporting::s_pEventProviderHandle
0x1800120f8  mov     ecx, cs:_tls_index
0x1800120fe  mov     rax, gs:58h
0x180012107  mov     r8, [rax+rcx*8]
0x18001210b  mov     eax, 8
0x180012110  cmp     byte ptr [rax+r8], 1
0x180012115  jz      short loc_18001218C
0x180012117  mov     r9, rsi
0x18001211a  mov     r8d, edi
0x18001211d  lea     rdx, gpEvent_GP_SESSION_RETURN_WINLOGON_CALL
0x180012124  mov     rcx, r14
0x180012127  call    cs:__imp_EtwEventWrite
0x18001212d  test    eax, eax
0x18001212f  jnz     loc_1800124C1
0x180012135  test    rsi, rsi
0x180012138  jz      short loc_180012143
0x18001213a  mov     rcx, rsi; hMem
0x18001213d  call    cs:__imp_LocalFree
0x180012143  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18001214a  jnz     loc_1800124CC
0x180012150  mov     rax, [rbx]
0x180012153  mov     rcx, rbx
0x180012156  mov     rax, [rax+8]
0x18001215a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001215f  nop
0x180012160  mov     eax, r15d
0x180012163  add     rsp, 78h
0x180012167  pop     r15
0x180012169  pop     r14
0x18001216b  pop     r13
0x18001216d  pop     r12
0x18001216f  pop     rdi
0x180012170  pop     rsi
0x180012171  pop     rbx
0x180012172  pop     rbp
0x180012173  retn
0x180012174  call    cs:__imp_GetLastError
0x18001217a  nop
0x18001217b  mov     r15d, eax
0x18001217e  mov     rcx, rsi; hMem
0x180012181  call    cs:__imp_LocalFree
0x180012187  jmp     loc_180012072
0x18001218c  mov     edx, 10h
0x180012191  add     rdx, r8
0x180012194  mov     ecx, 2
0x180012199  call    cs:__imp_EtwEventActivityIdControl
0x18001219f  test    eax, eax
0x1800121a1  jz      loc_180012117
0x1800121a7  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x1800121ae  jz      loc_180012117
0x1800121b4  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800121bb  test    r9, r9
0x1800121be  jz      loc_18001248C
0x1800121c4  mov     r8d, eax
0x1800121c7  lea     rdx, aCoperationalba; "COperationalBaseEvent::ReportOperationa"...
0x1800121ce  mov     ecx, 2
0x1800121d3  mov     rax, r9
0x1800121d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121db  jmp     loc_180012117
0x1800121e0  test    r12d, r12d
0x1800121e3  jz      loc_180012327
0x1800121e9  test    ecx, ecx
0x1800121eb  jz      loc_18001206F
0x1800121f1  test    r9, r9
0x1800121f4  jz      loc_1800122F5
0x1800121fa  lea     rdx, aCgrouppolicyse_13; "CGroupPolicySession::QueueItemForPolicy"...
0x180012201  mov     ecx, 4
0x180012206  mov     rax, r9
0x180012209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001220e  jmp     loc_18001206F
0x180012213  mov     ecx, cs:?g_dwDebugLevel@@3KA; ulong g_dwDebugLevel
0x180012219  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180012220  test    ecx, ecx
0x180012222  jz      loc_180012055
0x180012228  test    r9, r9
0x18001222b  jz      loc_1800122C5
0x180012231  lea     rdx, aPolicyApplierC; "Policy Applier Critical Section is NULL"
0x180012238  mov     ecx, 2
0x18001223d  mov     rax, r9
0x180012240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012245  jmp     loc_180012048
0x18001224a  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180012251  test    rax, rax
0x180012254  jz      short loc_180012272
0x180012256  mov     r9d, r13d
0x180012259  mov     r8d, r12d
0x18001225c  lea     rdx, aCgrouppolicyse_75; "CGroupPolicySession::QueueItemForPolicy"...
0x180012263  mov     ecx, 4
0x180012268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001226d  jmp     loc_180011F20
0x180012272  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x18001227a  jz      loc_180011F20
0x180012280  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180012288  jz      loc_180011F20
0x18001228e  mov     r9d, r13d
0x180012291  mov     r8d, r12d
0x180012294  lea     rdx, aCgrouppolicyse_75; "CGroupPolicySession::QueueItemForPolicy"...
0x18001229b  mov     ecx, 4; unsigned int
0x1800122a0  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800122a5  jmp     loc_180011F20
0x1800122aa  xor     r14d, r14d
0x1800122ad  mov     r15d, r14d
0x1800122b0  mov     rax, [rbx]
0x1800122b3  mov     rcx, rbx
0x1800122b6  mov     rax, [rax+8]
0x1800122ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122bf  nop
0x1800122c0  jmp     loc_180012072
0x1800122c5  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x1800122cc  jz      loc_180012055
0x1800122d2  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800122d9  jz      loc_180012055
0x1800122df  lea     rdx, aPolicyApplierC; "Policy Applier Critical Section is NULL"
0x1800122e6  mov     ecx, 2; unsigned int
0x1800122eb  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800122f0  jmp     loc_180012048
0x1800122f5  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x1800122fd  jz      loc_18001206F
0x180012303  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18001230b  jz      loc_18001206F
0x180012311  lea     rdx, aCgrouppolicyse_13; "CGroupPolicySession::QueueItemForPolicy"...
0x180012318  mov     ecx, 4; unsigned int
0x18001231d  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180012322  jmp     loc_18001206F
0x180012327  test    ecx, ecx
0x180012329  jz      short loc_18001236B
0x18001232b  test    r9, r9
0x18001232e  jz      short loc_180012346
0x180012330  lea     rdx, aCgrouppolicyse_63; "CGroupPolicySession::QueueItemForPolicy"...
0x180012337  mov     ecx, 4
0x18001233c  mov     rax, r9
0x18001233f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012344  jmp     short loc_18001236B
0x180012346  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x18001234e  jz      short loc_18001236B
0x180012350  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180012358  jz      short loc_18001236B
0x18001235a  lea     rdx, aCgrouppolicyse_63; "CGroupPolicySession::QueueItemForPolicy"...
0x180012361  mov     ecx, 4; unsigned int
0x180012366  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18001236b  call    ?GetInstance@CStatusMessage@@SAPEAV1@XZ; CStatusMessage::GetInstance(void)
0x180012370  mov     rsi, rax
0x180012373  mov     [rbp+arg_0], r14d
0x180012377  lea     rcx, [rbx+0B8h]
0x18001237e  mov     rdx, [rcx]
0x180012381  mov     rax, [rdx+10h]
0x180012385  lea     rdx, [rbp+arg_0]
0x180012389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001238e  mov     r15d, eax
0x180012391  test    eax, eax
0x180012393  jnz     loc_180012072
0x180012399  test    rsi, rsi
0x18001239c  jz      loc_180012072
0x1800123a2  lea     rcx, [rbx+130h]
0x1800123a9  mov     eax, [rbp+arg_18]
0x1800123ac  mov     [rsp+78h+var_38], eax; int
0x1800123b0  mov     eax, [rbp+arg_10]
0x1800123b3  mov     [rsp+78h+var_40], eax; unsigned int
0x1800123b7  mov     rax, [rbp+arg_8]
0x1800123bb  mov     [rsp+78h+var_48], rax; unsigned __int16 *
0x1800123c0  mov     eax, [rbp+arg_0]
0x1800123c3  mov     dword ptr [rsp+78h+lpThreadId], eax; int
0x1800123c7  mov     qword ptr [rsp+78h+dwCreationFlags], rcx; int *
0x1800123cc  mov     r9, [rbx+138h]; void *
0x1800123d3  mov     r8, [rbx+120h]; void *
  ... truncated ...
```
