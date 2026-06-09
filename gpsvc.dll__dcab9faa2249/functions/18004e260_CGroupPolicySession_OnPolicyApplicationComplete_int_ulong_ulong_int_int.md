# CGroupPolicySession::OnPolicyApplicationComplete(int,ulong,ulong,int,int)

- ea: `0x18004e260`
- end: `0x18004e851`
- name: `?OnPolicyApplicationComplete@CGroupPolicySession@@UEAAKHKKHH@Z`
- size: `1521`
- prototype: `unsigned int __fastcall(CGroupPolicySession *__hidden this, int, unsigned int, unsigned int, int, int)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180008a9c`
- `0x18001d6e8`
- `0x180045660`
- `0x18004dc40`
- `0x18004df78`
- `0x18004e260`
- `0x18004e858`
- `0x18004f240`
- `0x180056334`
- `0x180057bbc`
- `0x18005ce24`
- `0x180067f24`
- `0x180075ec0`
- `0x180076658`
- `0x18007ccc4`
- `0x18007cde4`
- `0x18007d320`
- `0x18008a644`
- `0x1800918e8`
- `0x180093b4c`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e4dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e4dd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004e5b6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004e5b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e517`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e710`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e720`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e517`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e710`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e720`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004e7cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004e7cd`
- `ntdll!EtwEventActivityIdControl` at `0x18004e476`
- `ntdll!EtwEventActivityIdControl` at `0x18004e476`

## string_xrefs

- `0x18004e2e2`: `OnPolicyApplicationComplete: Application complete with bConnectivityFailure = %d.`
- `0x18004e308`: `OnPolicyApplicationComplete: Application complete with bConnectivityFailure = %d.`
- `0x18004e35c`: `OnPolicyApplicationComplete: Registering for Connectivity notification.`
- `0x18004e37f`: `OnPolicyApplicationComplete: Registering for Connectivity notification.`
- `0x18004e498`: `OnPolicyApplicationComplete: Failed to get the activity id with error 0x%x`
- `0x18004e4bd`: `OnPolicyApplicationComplete: Failed to get the activity id with error 0x%x`
- `0x18004e54c`: `OnPolicyApplicationComplete: Signalling %d Refresh Policy callers`
- `0x18004e580`: `OnPolicyApplicationComplete: Signalling %d Refresh Policy callers`
- `0x18004e6bf`: `OnPolicyApplicationComplete: User logged in on active session`
- `0x18004e6e4`: `OnPolicyApplicationComplete: User logged in on active session`
- `0x18004e755`: `OnPolicyApplicationComplete: Notifying %d callers`
- `0x18004e78d`: `OnPolicyApplicationComplete: Notifying %d callers`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CGroupPolicySession::OnPolicyApplicationComplete(
        CGroupPolicySession *this,
        unsigned int a2,
        int a3,
        unsigned int a4,
        int a5,
        int a6)
{
  char v6; // si
  CGroupPolicySession *v10; // rdi
  unsigned int PrimarySession; // ebx
  unsigned int Instance; // ebx
  unsigned int v13; // eax
  struct _RTL_CRITICAL_SECTION *v14; // rbx
  void *v15; // rsi
  __int64 v16; // r8
  __int64 v17; // r8
  _QWORD *v18; // rax
  struct CConnectivityManager *v19; // rbx
  CGroupPolicySession *v20; // rcx
  int v21; // r12d
  unsigned int v22; // r15d
  void *v23; // rsi
  __int64 v24; // r8
  __int64 v25; // r9
  _QWORD *v26; // rbx
  unsigned int v27; // r15d
  LPCRITICAL_SECTION v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r8
  _QWORD *v31; // rax
  struct _RPC_ASYNC_STATE **v32; // rbx
  struct CConnectivityManager *v34; // [rsp+30h] [rbp-49h] BYREF
  unsigned int v35; // [rsp+38h] [rbp-41h]
  unsigned int v36; // [rsp+3Ch] [rbp-3Dh] BYREF
  unsigned int v37; // [rsp+40h] [rbp-39h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+48h] [rbp-31h] BYREF
  LPCRITICAL_SECTION v39; // [rsp+50h] [rbp-29h] BYREF
  _QWORD *v40; // [rsp+58h] [rbp-21h] BYREF
  char v41; // [rsp+60h] [rbp-19h]
  char *v42; // [rsp+68h] [rbp-11h]
  __int128 v43; // [rsp+70h] [rbp-9h] BYREF

  v6 = a4;
  v35 = a4;
  v10 = (CGroupPolicySession *)((char *)this - 8);
  v42 = (char *)this - 8;
  if ( this != (CGroupPolicySession *)8 )
    (**(void (__fastcall ***)(char *))v10)((char *)this - 8);
  v43 = xmmword_1800C6A80;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"OnPolicyApplicationComplete: Application complete with bConnectivityFailure = %d.", a2);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"OnPolicyApplicationComplete: Application complete with bConnectivityFailure = %d.", a2);
    }
  }
  *((_DWORD *)this + 78) = a2;
  if ( !*((_QWORD *)this + 33) )
  {
    PrimarySession = 14;
    goto LABEL_105;
  }
  if ( a6 )
  {
    if ( a2 )
    {
      v34 = 0;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"OnPolicyApplicationComplete: Registering for Connectivity notification.");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"OnPolicyApplicationComplete: Registering for Connectivity notification.");
        }
      }
      Instance = CConnectivityManager::GetInstance(&v34);
      if ( Instance || (Instance = CConnectivityManager::RegisterForNotificationIfRequired(v34)) != 0 )
      {
        if ( Instance == 1230 )
        {
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(4u, L"RegisterForNotificationIfRequired returned ERROR_CONNECTION_ACTIVE so continuing...");
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(
                4u,
                L"RegisterForNotificationIfRequired returned ERROR_CONNECTION_ACTIVE so continuing...");
            }
          }
        }
        else
        {
          CGPOperationalTraceEvent::ReportOperationalEvent(0x101Du, Instance);
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(4u, L"RegisterForNotificationIfRequired returned Status = 0x%x but continuing...", Instance);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(
                4u,
                L"RegisterForNotificationIfRequired returned Status = 0x%x but continuing...",
                Instance);
            }
          }
        }
      }
    }
    CGroupPolicySession::PersistOverdueState(v10, *((_DWORD *)this + 78));
    v13 = EtwEventActivityIdControl(1, &v43);
    if ( v13 && *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"OnPolicyApplicationComplete: Failed to get the activity id with error 0x%x", v13);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"OnPolicyApplicationComplete: Failed to get the activity id with error 0x%x", v13);
      }
    }
    v14 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 33);
    if ( v14 )
      EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 33));
    v15 = (void *)*((_QWORD *)this + 55);
    *((_QWORD *)this + 55) = 0;
    *((_OWORD *)this + 28) = v43;
    *((_DWORD *)this + 116) = a5;
    *((_DWORD *)this + 117) = a3;
    if ( v14 )
      LeaveCriticalSection(v14);
    if ( v15 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          if ( *(_QWORD *)v15 )
            v16 = *(unsigned int *)(*(_QWORD *)v15 + 8LL);
          else
            v16 = 0;
          g_lpDebugMsg(4u, L"OnPolicyApplicationComplete: Signalling %d Refresh Policy callers", v16);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          if ( *(_QWORD *)v15 )
            v17 = *(unsigned int *)(*(_QWORD *)v15 + 8LL);
          else
            v17 = 0;
          RedirectDebugMsg(4u, L"OnPolicyApplicationComplete: Signalling %d Refresh Policy callers", v17);
        }
      }
      while ( 1 )
      {
        v18 = *(_QWORD **)v15;
        if ( !*(_QWORD *)v15 || !v18[1] )
          break;
        v34 = *(struct CConnectivityManager **)(*(_QWORD *)*v18 + 16LL);
        v19 = v34;
        STLWrap_List<_NOTIFY_CALLER_INFO *>::pop_front(v15);
        SetEvent(v19);
        CGroupPolicySession::SafeCloseHandle(v10, (void **)&v34);
      }
      STLWrap_List<_NOTIFY_CALLER_INFO *>::`scalar deleting destructor'(v15);
    }
    v6 = v35;
  }
  if ( !a3 && (v6 & 1) != 0 )
  {
    STLWrap_List<unsigned long>::STLWrap_List<unsigned long>(&v34);
    v36 = 0;
    PrimarySession = CGroupPolicySession::GetPrimarySession(v20, &v36);
    if ( PrimarySession )
    {
      STLWrap_List<unsigned long>::~STLWrap_List<unsigned long>(&v34);
      goto LABEL_105;
    }
    v21 = 0;
    XEnterCritSec::XEnterCritSec((XEnterCritSec *)&v39, *((struct _RTL_CRITICAL_SECTION **)this + 33));
    v22 = ++*((_DWORD *)this + 90);
    v37 = v22;
    v23 = (void *)*((_QWORD *)this + 43);
    *((_QWORD *)this + 43) = 0;
    XEnterCritSec::XEnterCritSec((XEnterCritSec *)&lpCriticalSection, *((struct _RTL_CRITICAL_SECTION **)this + 18));
    STLWrap_List<_POLICY_SECTION_CONTEXT *>::begin((char *)this + 152, &v40);
    if ( v41 )
    {
      v26 = v40;
      v27 = v36;
      while ( v26 != *(_QWORD **)STLWrap_List<_UserSessionToken *>::end((char *)this + 152, &v40, v24, v25) )
      {
        STLWrap_List<unsigned long>::push_front(&v34, v26[2] + 8LL);
        if ( v27 == *(_DWORD *)(v26[2] + 8LL) )
        {
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(4u, L"OnPolicyApplicationComplete: User logged in on active session");
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(4u, L"OnPolicyApplicationComplete: User logged in on active session");
            }
          }
          v21 = 1;
        }
        v26 = (_QWORD *)*v26;
      }
      v22 = v37;
    }
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    v28 = v39;
    if ( v39 )
      LeaveCriticalSection(v39);
    if ( v23 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          if ( *(_QWORD *)v23 )
            v29 = *(unsigned int *)(*(_QWORD *)v23 + 8LL);
          else
            v29 = 0;
          g_lpDebugMsg(4u, L"OnPolicyApplicationComplete: Notifying %d callers", v29);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          if ( *(_QWORD *)v23 )
            v30 = *(unsigned int *)(*(_QWORD *)v23 + 8LL);
          else
            v30 = 0;
          RedirectDebugMsg(4u, L"OnPolicyApplicationComplete: Notifying %d callers", v30);
        }
      }
      while ( 1 )
      {
        v31 = *(_QWORD **)v23;
        if ( !*(_QWORD *)v23 || !v31[1] )
          break;
        v32 = *(struct _RPC_ASYNC_STATE ***)(*(_QWORD *)*v31 + 16LL);
        STLWrap_List<_NOTIFY_CALLER_INFO *>::pop_front(v23);
        Server_NotifyCompleteCall(*v32, v22);
        LocalFree(v32);
      }
      STLWrap_List<_NOTIFY_CALLER_INFO *>::`scalar deleting destructor'(v23);
    }
    if ( v21 )
      CGPApplicationService::NotifyConsoleSessionSubscribers(*((CGPApplicationService **)this + 41), 0, v35);
    CGPNotification::Notify((__int64)v28, (__int64)this + 152, (__int64)this + 176, v25);
    STLWrap_List<unsigned long>::~STLWrap_List<unsigned long>(&v34);
  }
  PrimarySession = 0;
LABEL_105:
  if ( v10 )
    (*(void (__fastcall **)(CGroupPolicySession *))(*(_QWORD *)v10 + 8LL))(v10);
  return PrimarySession;
}

```

## disassembly

```asm
0x18004e260  mov     [rsp-8+arg_10], rbx
0x18004e265  push    rbp
0x18004e266  push    rsi
0x18004e267  push    rdi
0x18004e268  push    r12
0x18004e26a  push    r13
0x18004e26c  push    r14
0x18004e26e  push    r15
0x18004e270  lea     rbp, [rsp-17h]
0x18004e275  sub     rsp, 90h
0x18004e27c  mov     rax, cs:__security_cookie
0x18004e283  xor     rax, rsp
0x18004e286  mov     [rbp+47h+var_40], rax
0x18004e28a  mov     esi, r9d
0x18004e28d  mov     [rbp+47h+var_88], r9d
0x18004e291  mov     r15d, r8d
0x18004e294  mov     ebx, edx
0x18004e296  mov     r14, rcx
0x18004e299  lea     rdi, [rcx-8]
0x18004e29d  mov     [rbp+47h+var_58], rdi
0x18004e2a1  xor     r13d, r13d
0x18004e2a4  test    rdi, rdi
0x18004e2a7  jz      short loc_18004E2B8
0x18004e2a9  mov     rax, [rdi]
0x18004e2ac  mov     rcx, rdi
0x18004e2af  mov     rax, [rax]
0x18004e2b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e2b7  nop
0x18004e2b8  movups  xmm0, cs:xmmword_1800C6A80
0x18004e2bf  movdqu  [rbp+47h+var_50], xmm0
0x18004e2c4  mov     r12d, 4
0x18004e2ca  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18004e2d1  jz      short loc_18004E317
0x18004e2d3  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004e2da  test    rax, rax
0x18004e2dd  jz      short loc_18004E2F3
0x18004e2df  mov     r8d, ebx
0x18004e2e2  lea     rdx, aOnpolicyapplic_3; "OnPolicyApplicationComplete: Applicatio"...
0x18004e2e9  mov     ecx, r12d
0x18004e2ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e2f1  jmp     short loc_18004E317
0x18004e2f3  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18004e2fa  jz      short loc_18004E317
0x18004e2fc  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18004e303  jz      short loc_18004E317
0x18004e305  mov     r8d, ebx
0x18004e308  lea     rdx, aOnpolicyapplic_3; "OnPolicyApplicationComplete: Applicatio"...
0x18004e30f  mov     ecx, r12d; unsigned int
0x18004e312  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18004e317  mov     [r14+138h], ebx
0x18004e31e  cmp     [r14+108h], r13
0x18004e325  jnz     short loc_18004E331
0x18004e327  mov     ebx, 0Eh
0x18004e32c  jmp     loc_18004E813
0x18004e331  cmp     [rbp+47h+arg_28], r13d
0x18004e335  jz      loc_18004E5D5
0x18004e33b  test    ebx, ebx
0x18004e33d  jz      loc_18004E45E
0x18004e343  mov     [rbp+47h+var_90], r13
0x18004e347  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18004e34e  jz      short loc_18004E38E
0x18004e350  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004e357  test    rax, rax
0x18004e35a  jz      short loc_18004E36D
0x18004e35c  lea     rdx, aOnpolicyapplic_1; "OnPolicyApplicationComplete: Registerin"...
0x18004e363  mov     ecx, r12d
0x18004e366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e36b  jmp     short loc_18004E38E
0x18004e36d  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18004e374  jz      short loc_18004E38E
0x18004e376  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18004e37d  jz      short loc_18004E38E
0x18004e37f  lea     rdx, aOnpolicyapplic_1; "OnPolicyApplicationComplete: Registerin"...
0x18004e386  mov     ecx, r12d; unsigned int
0x18004e389  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18004e38e  lea     rcx, [rbp+47h+var_90]; struct CConnectivityManager **
0x18004e392  call    ?GetInstance@CConnectivityManager@@SAKPEAPEAV1@@Z; CConnectivityManager::GetInstance(CConnectivityManager * *)
0x18004e397  mov     ebx, eax
0x18004e399  test    eax, eax
0x18004e39b  jnz     short loc_18004E3B0
0x18004e39d  mov     rcx, [rbp+47h+var_90]; this
0x18004e3a1  call    ?RegisterForNotificationIfRequired@CConnectivityManager@@QEAAKXZ; CConnectivityManager::RegisterForNotificationIfRequired(void)
0x18004e3a6  mov     ebx, eax
0x18004e3a8  test    eax, eax
0x18004e3aa  jz      loc_18004E45E
0x18004e3b0  cmp     ebx, 4CEh
0x18004e3b6  jz      short loc_18004E417
0x18004e3b8  mov     edx, ebx; unsigned int
0x18004e3ba  mov     ecx, 101Dh; unsigned int
0x18004e3bf  call    ?ReportOperationalEvent@CGPOperationalTraceEvent@@SAKKK@Z; CGPOperationalTraceEvent::ReportOperationalEvent(ulong,ulong)
0x18004e3c4  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18004e3cb  jz      loc_18004E45E
0x18004e3d1  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004e3d8  test    rax, rax
0x18004e3db  jz      short loc_18004E3F1
0x18004e3dd  mov     r8d, ebx
0x18004e3e0  lea     rdx, aRegisterfornot; "RegisterForNotificationIfRequired retur"...
0x18004e3e7  mov     ecx, r12d
0x18004e3ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e3ef  jmp     short loc_18004E45E
0x18004e3f1  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18004e3f8  jz      short loc_18004E45E
0x18004e3fa  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18004e401  jz      short loc_18004E45E
0x18004e403  mov     r8d, ebx
0x18004e406  lea     rdx, aRegisterfornot; "RegisterForNotificationIfRequired retur"...
0x18004e40d  mov     ecx, r12d; unsigned int
0x18004e410  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18004e415  jmp     short loc_18004E45E
0x18004e417  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18004e41e  jz      short loc_18004E45E
0x18004e420  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004e427  test    rax, rax
0x18004e42a  jz      short loc_18004E43D
0x18004e42c  lea     rdx, aRegisterfornot_0; "RegisterForNotificationIfRequired retur"...
0x18004e433  mov     ecx, r12d
0x18004e436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e43b  jmp     short loc_18004E45E
0x18004e43d  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18004e444  jz      short loc_18004E45E
0x18004e446  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18004e44d  jz      short loc_18004E45E
0x18004e44f  lea     rdx, aRegisterfornot_0; "RegisterForNotificationIfRequired retur"...
0x18004e456  mov     ecx, r12d; unsigned int
0x18004e459  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18004e45e  mov     edx, [r14+138h]; int
0x18004e465  mov     rcx, rdi; this
0x18004e468  call    ?PersistOverdueState@CGroupPolicySession@@AEAAXH@Z; CGroupPolicySession::PersistOverdueState(int)
0x18004e46d  lea     rdx, [rbp+47h+var_50]
0x18004e471  mov     ecx, 1
0x18004e476  call    cs:__imp_EtwEventActivityIdControl
0x18004e47c  mov     r8d, eax
0x18004e47f  test    eax, eax
0x18004e481  jz      short loc_18004E4CE
0x18004e483  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18004e48a  jz      short loc_18004E4CE
0x18004e48c  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004e493  test    rax, rax
0x18004e496  jz      short loc_18004E4AB
0x18004e498  lea     rdx, aOnpolicyapplic_2; "OnPolicyApplicationComplete: Failed to "...
0x18004e49f  mov     ecx, 2
0x18004e4a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e4a9  jmp     short loc_18004E4CE
0x18004e4ab  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18004e4b2  jz      short loc_18004E4CE
0x18004e4b4  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18004e4bb  jz      short loc_18004E4CE
0x18004e4bd  lea     rdx, aOnpolicyapplic_2; "OnPolicyApplicationComplete: Failed to "...
0x18004e4c4  mov     ecx, 2; unsigned int
0x18004e4c9  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18004e4ce  mov     rbx, [r14+108h]
0x18004e4d5  test    rbx, rbx
0x18004e4d8  jz      short loc_18004E4E3
0x18004e4da  mov     rcx, rbx; lpCriticalSection
0x18004e4dd  call    cs:__imp_EnterCriticalSection
0x18004e4e3  mov     rsi, [r14+1B8h]
0x18004e4ea  mov     [r14+1B8h], r13
0x18004e4f1  movups  xmm0, [rbp+47h+var_50]
0x18004e4f5  movdqu  xmmword ptr [r14+1C0h], xmm0
0x18004e4fe  mov     eax, [rbp+47h+arg_20]
0x18004e501  mov     [r14+1D0h], eax
0x18004e508  mov     [r14+1D4h], r15d
0x18004e50f  test    rbx, rbx
0x18004e512  jz      short loc_18004E51D
0x18004e514  mov     rcx, rbx; lpCriticalSection
0x18004e517  call    cs:__imp_LeaveCriticalSection
0x18004e51d  test    rsi, rsi
0x18004e520  jz      loc_18004E5D2
0x18004e526  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18004e52d  jz      short loc_18004E58F
0x18004e52f  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004e536  test    rax, rax
0x18004e539  jz      short loc_18004E55D
0x18004e53b  mov     rcx, [rsi]
0x18004e53e  test    rcx, rcx
0x18004e541  jz      short loc_18004E549
0x18004e543  mov     r8d, [rcx+8]
0x18004e547  jmp     short loc_18004E54C
0x18004e549  mov     r8d, r13d
0x18004e54c  lea     rdx, aOnpolicyapplic_4; "OnPolicyApplicationComplete: Signalling"...
0x18004e553  mov     ecx, r12d
0x18004e556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e55b  jmp     short loc_18004E58F
0x18004e55d  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18004e564  jz      short loc_18004E58F
0x18004e566  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18004e56d  jz      short loc_18004E58F
0x18004e56f  mov     rax, [rsi]
0x18004e572  test    rax, rax
0x18004e575  jz      short loc_18004E57D
0x18004e577  mov     r8d, [rax+8]
0x18004e57b  jmp     short loc_18004E580
0x18004e57d  mov     r8d, r13d
0x18004e580  lea     rdx, aOnpolicyapplic_4; "OnPolicyApplicationComplete: Signalling"...
0x18004e587  mov     ecx, r12d; unsigned int
0x18004e58a  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18004e58f  mov     rax, [rsi]
0x18004e592  test    rax, rax
0x18004e595  jz      short loc_18004E5CA
0x18004e597  cmp     [rax+8], r13
0x18004e59b  jz      short loc_18004E5CA
0x18004e59d  mov     rax, [rax]
0x18004e5a0  mov     rcx, [rax]
0x18004e5a3  mov     rbx, [rcx+10h]
0x18004e5a7  mov     [rbp+47h+var_90], rbx
0x18004e5ab  mov     rcx, rsi
0x18004e5ae  call    ?pop_front@?$STLWrap_List@PEAU_NOTIFY_CALLER_INFO@@@@QEAAXXZ; STLWrap_List<_NOTIFY_CALLER_INFO *>::pop_front(void)
0x18004e5b3  mov     rcx, rbx; hEvent
0x18004e5b6  call    cs:__imp_SetEvent
0x18004e5bc  lea     rdx, [rbp+47h+var_90]; void **
0x18004e5c0  mov     rcx, rdi; this
0x18004e5c3  call    ?SafeCloseHandle@CGroupPolicySession@@AEAAXAEAPEAX@Z; CGroupPolicySession::SafeCloseHandle(void * &)
0x18004e5c8  jmp     short loc_18004E58F
0x18004e5ca  mov     rcx, rsi; Block
0x18004e5cd  call    ??_G?$STLWrap_List@PEAU_NOTIFY_CALLER_INFO@@@@QEAAPEAXI@Z; STLWrap_List<_NOTIFY_CALLER_INFO *>::`scalar deleting destructor'(uint)
0x18004e5d2  mov     esi, [rbp+47h+var_88]
0x18004e5d5  test    r15d, r15d
0x18004e5d8  jnz     loc_18004E810
0x18004e5de  test    sil, 1
0x18004e5e2  jz      loc_18004E810
0x18004e5e8  lea     rcx, [rbp+47h+var_90]
0x18004e5ec  call    ??0?$STLWrap_List@K@@QEAA@XZ; STLWrap_List<ulong>::STLWrap_List<ulong>(void)
0x18004e5f1  nop
0x18004e5f2  mov     [rbp+47h+var_84], r13d
0x18004e5f6  lea     rdx, [rbp+47h+var_84]; unsigned int *
0x18004e5fa  call    ?GetPrimarySession@CGroupPolicySession@@AEAAKPEAK@Z; CGroupPolicySession::GetPrimarySession(ulong *)
0x18004e5ff  mov     ebx, eax
0x18004e601  test    eax, eax
0x18004e603  jz      short loc_18004E613
0x18004e605  lea     rcx, [rbp+47h+var_90]
0x18004e609  call    ??1?$STLWrap_List@K@@QEAA@XZ; STLWrap_List<ulong>::~STLWrap_List<ulong>(void)
0x18004e60e  jmp     loc_18004E813
0x18004e613  mov     r12d, r13d
0x18004e616  mov     rdx, [r14+108h]; struct _RTL_CRITICAL_SECTION *
0x18004e61d  lea     rcx, [rbp+47h+var_70]; this
0x18004e621  call    ??0XEnterCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; XEnterCritSec::XEnterCritSec(_RTL_CRITICAL_SECTION *)
0x18004e626  nop
0x18004e627  inc     dword ptr [r14+168h]
0x18004e62e  mov     r15d, [r14+168h]
0x18004e635  mov     [rbp+47h+var_80], r15d
0x18004e639  mov     rsi, [r14+158h]
0x18004e640  mov     [r14+158h], r13
0x18004e647  mov     rdx, [r14+90h]; struct _RTL_CRITICAL_SECTION *
0x18004e64e  lea     rcx, [rbp+47h+lpCriticalSection]; this
0x18004e652  call    ??0XEnterCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; XEnterCritSec::XEnterCritSec(_RTL_CRITICAL_SECTION *)
0x18004e657  nop
0x18004e658  lea     r13, [r14+98h]
0x18004e65f  lea     rdx, [rbp+47h+var_68]
0x18004e663  mov     rcx, r13
0x18004e666  call    ?begin@?$STLWrap_List@PEAU_POLICY_SECTION_CONTEXT@@@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@PEAU_POLICY_SECTION_CONTEXT@@@std@@@std@@@std@@_N@std@@XZ; STLWrap_List<_POLICY_SECTION_CONTEXT *>::begin(void)
0x18004e66b  cmp     [rbp+47h+var_60], 0
0x18004e66f  jz      loc_18004E707
0x18004e675  mov     rbx, [rbp+47h+var_68]
0x18004e679  mov     r15d, [rbp+47h+var_84]
0x18004e67d  lea     rdx, [rbp+47h+var_68]
0x18004e681  mov     rcx, r13
0x18004e684  call    ?end@?$STLWrap_List@PEAU_UserSessionToken@@@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@PEAU_UserSessionToken@@@std@@@std@@@std@@_N@std@@XZ; STLWrap_List<_UserSessionToken *>::end(void)
0x18004e689  cmp     rbx, [rax]
0x18004e68c  jz      short loc_18004E703
0x18004e68e  mov     rdx, [rbx+10h]
0x18004e692  add     rdx, 8
0x18004e696  lea     rcx, [rbp+47h+var_90]
0x18004e69a  call    ?push_front@?$STLWrap_List@K@@QEAAKAEBK@Z; STLWrap_List<ulong>::push_front(ulong const &)
0x18004e69f  mov     rax, [rbx+10h]
0x18004e6a3  cmp     r15d, [rax+8]
0x18004e6a7  jnz     short loc_18004E6FB
0x18004e6a9  xor     ecx, ecx
0x18004e6ab  cmp     cs:?g_dwDebugLevel@@3KA, ecx; ulong g_dwDebugLevel
0x18004e6b1  jz      short loc_18004E6F5
0x18004e6b3  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004e6ba  test    rax, rax
0x18004e6bd  jz      short loc_18004E6D2
0x18004e6bf  lea     rdx, aOnpolicyapplic_0; "OnPolicyApplicationComplete: User logge"...
0x18004e6c6  mov     ecx, 4
0x18004e6cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e6d0  jmp     short loc_18004E6F5
0x18004e6d2  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rcx; void * g_lpDebugMsgContextInstance
0x18004e6d9  jz      short loc_18004E6F5
0x18004e6db  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rcx; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18004e6e2  jz      short loc_18004E6F5
0x18004e6e4  lea     rdx, aOnpolicyapplic_0; "OnPolicyApplicationComplete: User logge"...
0x18004e6eb  mov     ecx, 4; unsigned int
0x18004e6f0  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18004e6f5  mov     r12d, 1
0x18004e6fb  mov     rbx, [rbx]
0x18004e6fe  jmp     loc_18004E67D
0x18004e703  mov     r15d, [rbp+47h+var_80]
0x18004e707  mov     rcx, [rbp+47h+lpCriticalSection]; lpCriticalSection
0x18004e70b  test    rcx, rcx
0x18004e70e  jz      short loc_18004E717
0x18004e710  call    cs:__imp_LeaveCriticalSection
0x18004e716  nop
0x18004e717  mov     rcx, [rbp+47h+var_70]; lpCriticalSection
0x18004e71b  test    rcx, rcx
0x18004e71e  jz      short loc_18004E726
0x18004e720  call    cs:__imp_LeaveCriticalSection
0x18004e726  test    rsi, rsi
0x18004e729  jz      loc_18004E7DD
0x18004e72f  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18004e736  jz      short loc_18004E79E
  ... truncated ...
```
