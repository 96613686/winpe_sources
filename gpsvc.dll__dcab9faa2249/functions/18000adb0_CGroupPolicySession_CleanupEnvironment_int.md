# CGroupPolicySession::CleanupEnvironment(int)

- ea: `0x18000adb0`
- end: `0x18000b62c`
- name: `?CleanupEnvironment@CGroupPolicySession@@QEAAXH@Z`
- size: `2172`
- prototype: `void __fastcall(CGroupPolicySession *this)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180009d2c`
- `0x18000c398`

## callees

- `0x18000adb0`
- `0x180045660`
- `0x18004df78`
- `0x180055098`
- `0x18005ce24`
- `0x180075ec0`
- `0x18007cde4`
- `0x18007d320`
- `0x18008f4b0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ae48`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000af50`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000afc3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ae48`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000af50`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000afc3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b136`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b16b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b2ed`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b136`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b16b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b2ed`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000af19`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000af19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ae97`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000af77`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000afea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b1d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ae97`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000af77`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000afea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b1d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b569`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b569`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000af62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000afd5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000af62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000afd5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b115`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b331`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b115`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b331`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000affc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000affc`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000b047`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000b047`
- `ntdll!EtwEventActivityIdControl` at `0x18000b187`
- `ntdll!EtwEventActivityIdControl` at `0x18000b187`
- `SAMLIB!SamUnregisterObjectChangeNotification` at `0x18000b0b6`
- `SAMLIB!SamUnregisterObjectChangeNotification` at `0x18000b0b6`

## string_xrefs

- `0x18000b355`: `Waiting for user group policy thread to terminate.`
- `0x18000b38a`: `Waiting for user group policy thread to terminate.`
- `0x18000b39f`: `Waiting for machine group policy thread to terminate.`
- `0x18000b3d4`: `Waiting for machine group policy thread to terminate.`
- `0x18000b44d`: `CGroupPolicySession::CleanupEnvironment: Completed WaitForSingleObject.`
- `0x18000b482`: `CGroupPolicySession::CleanupEnvironment: Completed WaitForSingleObject.`
- `0x18000b4a4`: `User group policy thread has terminated.`
- `0x18000b4d9`: `User group policy thread has terminated.`
- `0x18000b07e`: `machine group policy thread has terminated.`
- `0x18000b4fe`: `machine group policy thread has terminated.`
- `0x18000b579`: `UnregisterWaitEx() for DeleteStaleLGPOsCallback handle=%p failed due to error=%d.`
- `0x18000b5be`: `UnregisterWaitEx() for DeleteStaleLGPOsCallback handle=%p failed due to error=%d.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CGroupPolicySession::CleanupEnvironment(CGroupPolicySession *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  _QWORD *v3; // r14
  void *v4; // rcx
  __int64 v5; // rax
  void *v6; // rcx
  struct _RTL_CRITICAL_SECTION *v7; // rdi
  void *v8; // rcx
  __int64 v9; // rax
  void *v10; // rcx
  struct _RTL_CRITICAL_SECTION *v11; // rdi
  void *v12; // rcx
  HKEY v13; // rcx
  int v14; // eax
  _QWORD *v15; // rax
  void *v16; // r15
  __int64 v17; // r8
  void *v18; // rcx
  __int64 v19; // r8
  _QWORD *v20; // rax
  LPCRITICAL_SECTION v21; // rdi
  struct _RPC_ASYNC_STATE **v22; // rdi
  void (*v23)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD LastError; // eax
  DWORD v25; // eax
  int v26; // [rsp+30h] [rbp-78h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[4]; // [rsp+38h] [rbp-70h] BYREF
  __int128 v28; // [rsp+58h] [rbp-50h] BYREF

  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"CGroupPolicySession::CleanupEnvironment:++");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"CGroupPolicySession::CleanupEnvironment:++");
    }
  }
  lpCriticalSection[1] = (LPCRITICAL_SECTION)this;
  if ( this )
    (**(void (__fastcall ***)(CGroupPolicySession *))this)(this);
  v26 = 0;
  if ( (*(unsigned int (__fastcall **)(char *, int *))(*((_QWORD *)this + 23) + 16LL))((char *)this + 184, &v26) )
  {
    if ( this )
      (*(void (__fastcall **)(CGroupPolicySession *))(*(_QWORD *)this + 8LL))(this);
  }
  else
  {
    lpCriticalSection[2] = (LPCRITICAL_SECTION)this;
    if ( this )
      (**(void (__fastcall ***)(CGroupPolicySession *))this)(this);
    v2 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 34);
    lpCriticalSection[3] = v2;
    if ( v2 )
      EnterCriticalSection(v2);
    v3 = (_QWORD *)*((_QWORD *)this + 44);
    *((_QWORD *)this + 44) = 0;
    *((_DWORD *)this + 81) = 1;
    if ( !*((_QWORD *)this + 26) )
    {
      v18 = (void *)*((_QWORD *)this + 27);
      if ( v18 )
      {
        SetEvent(v18);
        v28 = xmmword_1800C6A80;
        EtwEventActivityIdControl(1, &v28);
        XEnterCritSec::XEnterCritSec((XEnterCritSec *)lpCriticalSection, *((struct _RTL_CRITICAL_SECTION **)this + 34));
        v16 = (void *)*((_QWORD *)this + 56);
        *((_QWORD *)this + 56) = 0;
        *(_OWORD *)((char *)this + 456) = v28;
        *((_DWORD *)this + 118) = 0;
        *((_DWORD *)this + 119) = 1115;
        if ( lpCriticalSection[0] )
          LeaveCriticalSection(lpCriticalSection[0]);
        if ( v16 )
        {
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              if ( *(_QWORD *)v16 )
                v17 = *(unsigned int *)(*(_QWORD *)v16 + 8LL);
              else
                v17 = 0;
              g_lpDebugMsg(4u, L"AbortSubscriptions: Signalling %d Refresh Policy callers", v17);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              if ( *(_QWORD *)v16 )
                v19 = *(unsigned int *)(*(_QWORD *)v16 + 8LL);
              else
                v19 = 0;
              RedirectDebugMsg(4u, L"AbortSubscriptions: Signalling %d Refresh Policy callers", v19);
            }
          }
          while ( 1 )
          {
            v20 = *(_QWORD **)v16;
            if ( !*(_QWORD *)v16 || !v20[1] )
              break;
            lpCriticalSection[0] = *(LPCRITICAL_SECTION *)(*(_QWORD *)*v20 + 16LL);
            v21 = lpCriticalSection[0];
            STLWrap_List<_NOTIFY_CALLER_INFO *>::pop_front(v16);
            SetEvent(v21);
            CGroupPolicySession::SafeCloseHandle(this, (void **)lpCriticalSection);
          }
          STLWrap_List<_NOTIFY_CALLER_INFO *>::`scalar deleting destructor'(v16);
        }
      }
    }
    if ( !*((_QWORD *)this + 45) )
    {
      v4 = (void *)*((_QWORD *)this + 36);
      if ( v4 )
        SetEvent(v4);
    }
    if ( v2 )
      LeaveCriticalSection(v2);
    if ( v3 )
    {
      while ( 1 )
      {
        v15 = (_QWORD *)*v3;
        if ( !*v3 || !v15[1] )
          break;
        v22 = *(struct _RPC_ASYNC_STATE ***)(*(_QWORD *)*v15 + 16LL);
        STLWrap_List<_NOTIFY_CALLER_INFO *>::pop_front(v3);
        Server_NotifyAbortCall(*v22, 0x525u);
        LocalFree(v22);
      }
      STLWrap_List<_NOTIFY_CALLER_INFO *>::`scalar deleting destructor'(v3);
    }
    (*(void (__fastcall **)(CGroupPolicySession *))(*(_QWORD *)this + 8LL))(this);
    if ( *((_QWORD *)this + 22) )
    {
      if ( v26 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"Waiting for machine group policy thread to terminate.");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"Waiting for machine group policy thread to terminate.");
          }
        }
      }
      else if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"Waiting for user group policy thread to terminate.");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"Waiting for user group policy thread to terminate.");
        }
      }
      v5 = *((_QWORD *)this + 26);
      if ( v5 )
      {
        v6 = *(void **)(v5 + 8);
        if ( v6 )
        {
          if ( v26 )
          {
            CGPService::KeepServiceAlive(v6, 0xFFFFFFFF);
          }
          else
          {
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(4u, L"CGroupPolicySession::CleanupEnvironment: Beginning WaitForSingleObject.");
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(4u, L"CGroupPolicySession::CleanupEnvironment: Beginning WaitForSingleObject.");
              }
            }
            WaitForSingleObject(*(HANDLE *)(*((_QWORD *)this + 26) + 8LL), 0xFFFFFFFF);
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(4u, L"CGroupPolicySession::CleanupEnvironment: Completed WaitForSingleObject.");
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(4u, L"CGroupPolicySession::CleanupEnvironment: Completed WaitForSingleObject.");
              }
            }
          }
        }
      }
      if ( v26 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"machine group policy thread has terminated.");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"machine group policy thread has terminated.");
          }
        }
      }
      else if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"User group policy thread has terminated.");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"User group policy thread has terminated.");
        }
      }
      v7 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 13);
      if ( v7 )
        EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 13));
      v8 = (void *)*((_QWORD *)this + 22);
      if ( v8 )
      {
        CloseHandle(v8);
        *((_QWORD *)this + 22) = 0;
      }
      if ( v7 )
        LeaveCriticalSection(v7);
      v9 = *((_QWORD *)this + 26);
      if ( v9 )
      {
        if ( *(_QWORD *)(v9 + 8) )
          CGroupPolicySession::SafeCloseHandle(this, (void **)(v9 + 8));
        LocalFree(*((HLOCAL *)this + 26));
        *((_QWORD *)this + 26) = 0;
      }
    }
    if ( *((_QWORD *)this + 47) )
    {
      v14 = SamUnregisterObjectChangeNotification(2);
      if ( v14 < 0 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(
              2u,
              L"SamUnregisterObjectChangeNotification() for m_hLocalUserAccountChangeEvent handle=%p failed due to error=%d.",
              *((_QWORD *)this + 47),
              (unsigned int)v14);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(
              2u,
              L"SamUnregisterObjectChangeNotification() for m_hLocalUserAccountChangeEvent handle=%p failed due to error=%d.",
              *((_QWORD *)this + 47),
              (unsigned int)v14);
          }
        }
      }
    }
    v10 = (void *)*((_QWORD *)this + 48);
    if ( v10 )
    {
      if ( !UnregisterWaitEx(v10, (HANDLE)0xFFFFFFFFFFFFFFFFLL) && *(_DWORD *)&g_dwDebugLevel )
      {
        v23 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          LastError = GetLastError();
          v23(
            2u,
            L"UnregisterWaitEx() for DeleteStaleLGPOsCallback handle=%p failed due to error=%d.",
            *((_QWORD *)this + 48),
            LastError);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v25 = GetLastError();
          RedirectDebugMsg(
            2u,
            L"UnregisterWaitEx() for DeleteStaleLGPOsCallback handle=%p failed due to error=%d.",
            *((_QWORD *)this + 48),
            v25);
        }
      }
      *((_QWORD *)this + 48) = 0;
    }
    if ( *((_QWORD *)this + 47) )
    {
      v11 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 13);
      if ( v11 )
        EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 13));
      v12 = (void *)*((_QWORD *)this + 47);
      if ( v12 )
      {
        CloseHandle(v12);
        *((_QWORD *)this + 47) = 0;
      }
      if ( v11 )
        LeaveCriticalSection(v11);
    }
    v13 = (HKEY)*((_QWORD *)this + 21);
    if ( v13 )
    {
      RegCloseKey(v13);
      *((_QWORD *)this + 21) = 0;
    }
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"CGroupPolicySession::CleanupEnvironment:--");
      }
      else if ( g_lpDebugMsgContextInstance )
      {
        if ( g_lpDebugMsgContext )
          RedirectDebugMsg(4u, L"CGroupPolicySession::CleanupEnvironment:--");
      }
    }
    (*(void (__fastcall **)(CGroupPolicySession *))(*(_QWORD *)this + 8LL))(this);
  }
}

```

## disassembly

```asm
0x18000adb0  push    rbx
0x18000adb2  push    rbp
0x18000adb3  push    rsi
0x18000adb4  push    rdi
0x18000adb5  push    r14
0x18000adb7  push    r15
0x18000adb9  sub     rsp, 78h
0x18000adbd  mov     rax, cs:__security_cookie
0x18000adc4  xor     rax, rsp
0x18000adc7  mov     [rsp+0A8h+var_40], rax
0x18000adcc  mov     rbx, rcx
0x18000adcf  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18000add6  jnz     loc_18000B20C
0x18000addc  mov     [rsp+0A8h+var_68], rbx
0x18000ade1  test    rbx, rbx
0x18000ade4  jz      short loc_18000ADF5
0x18000ade6  mov     rax, [rbx]
0x18000ade9  mov     rcx, rbx
0x18000adec  mov     rax, [rax]
0x18000adef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adf4  nop
0x18000adf5  xor     ebp, ebp
0x18000adf7  mov     [rsp+0A8h+var_78], ebp
0x18000adfb  lea     rcx, [rbx+0B8h]
0x18000ae02  mov     rax, [rcx]
0x18000ae05  lea     rdx, [rsp+0A8h+var_78]
0x18000ae0a  mov     rax, [rax+10h]
0x18000ae0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae13  test    eax, eax
0x18000ae15  jnz     loc_18000B097
0x18000ae1b  mov     [rsp+0A8h+var_60], rbx
0x18000ae20  test    rbx, rbx
0x18000ae23  jz      short loc_18000AE34
0x18000ae25  mov     rax, [rbx]
0x18000ae28  mov     rcx, rbx
0x18000ae2b  mov     rax, [rax]
0x18000ae2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae33  nop
0x18000ae34  mov     rsi, [rbx+110h]
0x18000ae3b  mov     [rsp+0A8h+var_58], rsi
0x18000ae40  test    rsi, rsi
0x18000ae43  jz      short loc_18000AE4F
0x18000ae45  mov     rcx, rsi; lpCriticalSection
0x18000ae48  call    cs:__imp_EnterCriticalSection
0x18000ae4e  nop
0x18000ae4f  mov     r14, [rbx+160h]
0x18000ae56  mov     [rbx+160h], rbp
0x18000ae5d  mov     dword ptr [rbx+144h], 1
0x18000ae67  cmp     qword ptr [rbx+0D0h], 0
0x18000ae6f  jz      loc_18000B260
0x18000ae75  cmp     qword ptr [rbx+168h], 0
0x18000ae7d  jnz     short loc_18000AE8F
0x18000ae7f  mov     rcx, [rbx+120h]; hEvent
0x18000ae86  test    rcx, rcx
0x18000ae89  jnz     loc_18000B136
0x18000ae8f  test    rsi, rsi
0x18000ae92  jz      short loc_18000AE9D
0x18000ae94  mov     rcx, rsi; lpCriticalSection
0x18000ae97  call    cs:__imp_LeaveCriticalSection
0x18000ae9d  test    r14, r14
0x18000aea0  jnz     loc_18000B14B
0x18000aea6  mov     rax, [rbx]
0x18000aea9  mov     rcx, rbx
0x18000aeac  mov     rax, [rax+8]
0x18000aeb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aeb5  nop
0x18000aeb6  cmp     qword ptr [rbx+0B0h], 0
0x18000aebe  jz      loc_18000AF8D
0x18000aec4  cmp     [rsp+0A8h+var_78], 0
0x18000aec9  jz      loc_18000B33C
0x18000aecf  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18000aed6  jnz     loc_18000B393
0x18000aedc  mov     rax, [rbx+0D0h]
0x18000aee3  test    rax, rax
0x18000aee6  jz      short loc_18000AF2C
0x18000aee8  mov     rcx, [rax+8]; hHandle
0x18000aeec  test    rcx, rcx
0x18000aeef  jz      short loc_18000AF2C
0x18000aef1  cmp     [rsp+0A8h+var_78], 0
0x18000aef6  jnz     loc_18000B127
0x18000aefc  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18000af03  jnz     loc_18000B3EA
0x18000af09  mov     rcx, [rbx+0D0h]
0x18000af10  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000af15  mov     rcx, [rcx+8]; hHandle
0x18000af19  call    cs:__imp_WaitForSingleObject
0x18000af1f  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18000af26  jnz     loc_18000B441
0x18000af2c  cmp     [rsp+0A8h+var_78], 0
0x18000af31  jnz     loc_18000B061
0x18000af37  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18000af3e  jnz     loc_18000B498
0x18000af44  mov     rdi, [rbx+68h]
0x18000af48  test    rdi, rdi
0x18000af4b  jz      short loc_18000AF56
0x18000af4d  mov     rcx, rdi; lpCriticalSection
0x18000af50  call    cs:__imp_EnterCriticalSection
0x18000af56  mov     rcx, [rbx+0B0h]; hObject
0x18000af5d  test    rcx, rcx
0x18000af60  jz      short loc_18000AF6F
0x18000af62  call    cs:__imp_CloseHandle
0x18000af68  mov     [rbx+0B0h], rbp
0x18000af6f  test    rdi, rdi
0x18000af72  jz      short loc_18000AF7D
0x18000af74  mov     rcx, rdi; lpCriticalSection
0x18000af77  call    cs:__imp_LeaveCriticalSection
0x18000af7d  mov     rax, [rbx+0D0h]
0x18000af84  test    rax, rax
0x18000af87  jnz     loc_18000B104
0x18000af8d  mov     rdx, [rbx+178h]
0x18000af94  test    rdx, rdx
0x18000af97  jnz     loc_18000B0B1
0x18000af9d  mov     rcx, [rbx+180h]; WaitHandle
0x18000afa4  test    rcx, rcx
0x18000afa7  jnz     loc_18000B040
0x18000afad  cmp     qword ptr [rbx+178h], 0
0x18000afb5  jz      short loc_18000AFF0
0x18000afb7  mov     rdi, [rbx+68h]
0x18000afbb  test    rdi, rdi
0x18000afbe  jz      short loc_18000AFC9
0x18000afc0  mov     rcx, rdi; lpCriticalSection
0x18000afc3  call    cs:__imp_EnterCriticalSection
0x18000afc9  mov     rcx, [rbx+178h]; hObject
0x18000afd0  test    rcx, rcx
0x18000afd3  jz      short loc_18000AFE2
0x18000afd5  call    cs:__imp_CloseHandle
0x18000afdb  mov     [rbx+178h], rbp
0x18000afe2  test    rdi, rdi
0x18000afe5  jz      short loc_18000AFF0
0x18000afe7  mov     rcx, rdi; lpCriticalSection
0x18000afea  call    cs:__imp_LeaveCriticalSection
0x18000aff0  mov     rcx, [rbx+0A8h]; hKey
0x18000aff7  test    rcx, rcx
0x18000affa  jz      short loc_18000B009
0x18000affc  call    cs:__imp_RegCloseKey
0x18000b002  mov     [rbx+0A8h], rbp
0x18000b009  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18000b010  jnz     loc_18000B5D4
0x18000b016  mov     rax, [rbx]
0x18000b019  mov     rcx, rbx
0x18000b01c  mov     rax, [rax+8]
0x18000b020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b025  nop
0x18000b026  mov     rcx, [rsp+0A8h+var_40]
0x18000b02b  xor     rcx, rsp; StackCookie
0x18000b02e  call    __security_check_cookie
0x18000b033  add     rsp, 78h
0x18000b037  pop     r15
0x18000b039  pop     r14
0x18000b03b  pop     rdi
0x18000b03c  pop     rsi
0x18000b03d  pop     rbp
0x18000b03e  pop     rbx
0x18000b03f  retn
0x18000b040  mov     rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18000b047  call    cs:__imp_UnregisterWaitEx
0x18000b04d  test    eax, eax
0x18000b04f  jz      loc_18000B550
0x18000b055  mov     [rbx+180h], rbp
0x18000b05c  jmp     loc_18000AFAD
0x18000b061  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18000b068  jz      loc_18000AF44
0x18000b06e  mov     rdi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18000b075  test    rdi, rdi
0x18000b078  jz      loc_18000B4E2
0x18000b07e  lea     rdx, aMachineGroupPo; "machine group policy thread has termina"...
0x18000b085  mov     ecx, 4
0x18000b08a  mov     rax, rdi
0x18000b08d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b092  jmp     loc_18000AF44
0x18000b097  test    rbx, rbx
0x18000b09a  jz      short loc_18000B0AC
0x18000b09c  mov     rax, [rbx]
0x18000b09f  mov     rcx, rbx
0x18000b0a2  mov     rax, [rax+8]
0x18000b0a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0ab  nop
0x18000b0ac  jmp     loc_18000B026
0x18000b0b1  mov     ecx, 2
0x18000b0b6  call    cs:__imp_SamUnregisterObjectChangeNotification
0x18000b0bc  test    eax, eax
0x18000b0be  jns     loc_18000AF9D
0x18000b0c4  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18000b0cb  jz      loc_18000AF9D
0x18000b0d1  mov     rdi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18000b0d8  test    rdi, rdi
0x18000b0db  jz      loc_18000B514
0x18000b0e1  mov     r9d, eax
0x18000b0e4  mov     r8, [rbx+178h]
0x18000b0eb  lea     rdx, aSamunregistero_0; "SamUnregisterObjectChangeNotification()"...
0x18000b0f2  mov     ecx, 2
0x18000b0f7  mov     rax, rdi
0x18000b0fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0ff  jmp     loc_18000AF9D
0x18000b104  lea     rdx, [rax+8]; void **
0x18000b108  cmp     qword ptr [rdx], 0
0x18000b10c  jnz     short loc_18000B141
0x18000b10e  mov     rcx, [rbx+0D0h]; hMem
0x18000b115  call    cs:__imp_LocalFree
0x18000b11b  mov     [rbx+0D0h], rbp
0x18000b122  jmp     loc_18000AF8D
0x18000b127  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000b12c  call    ?KeepServiceAlive@CGPService@@SAKPEAXK@Z; CGPService::KeepServiceAlive(void *,ulong)
0x18000b131  jmp     loc_18000AF2C
0x18000b136  call    cs:__imp_SetEvent
0x18000b13c  jmp     loc_18000AE8F
0x18000b141  mov     rcx, rbx; this
0x18000b144  call    ?SafeCloseHandle@CGroupPolicySession@@AEAAXAEAPEAX@Z; CGroupPolicySession::SafeCloseHandle(void * &)
0x18000b149  jmp     short loc_18000B10E
0x18000b14b  mov     rax, [r14]
0x18000b14e  test    rax, rax
0x18000b151  jz      short loc_18000B15E
0x18000b153  cmp     qword ptr [rax+8], 0
0x18000b158  jnz     loc_18000B30F
0x18000b15e  mov     rcx, r14; Block
0x18000b161  call    ??_G?$STLWrap_List@PEAU_NOTIFY_CALLER_INFO@@@@QEAAPEAXI@Z; STLWrap_List<_NOTIFY_CALLER_INFO *>::`scalar deleting destructor'(uint)
0x18000b166  jmp     loc_18000AEA6
0x18000b16b  call    cs:__imp_SetEvent
0x18000b171  movups  xmm0, cs:xmmword_1800C6A80
0x18000b178  movups  [rsp+0A8h+var_50], xmm0
0x18000b17d  lea     rdx, [rsp+0A8h+var_50]
0x18000b182  mov     ecx, 1
0x18000b187  call    cs:__imp_EtwEventActivityIdControl
0x18000b18d  mov     rdx, [rbx+110h]; struct _RTL_CRITICAL_SECTION *
0x18000b194  lea     rcx, [rsp+0A8h+lpCriticalSection]; this
0x18000b199  call    ??0XEnterCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; XEnterCritSec::XEnterCritSec(_RTL_CRITICAL_SECTION *)
0x18000b19e  mov     r15, [rbx+1C0h]
0x18000b1a5  mov     [rbx+1C0h], rbp
0x18000b1ac  movups  xmm0, [rsp+0A8h+var_50]
0x18000b1b1  movups  xmmword ptr [rbx+1C8h], xmm0
0x18000b1b8  mov     [rbx+1D8h], ebp
0x18000b1be  mov     dword ptr [rbx+1DCh], 45Bh
0x18000b1c8  mov     rcx, [rsp+0A8h+lpCriticalSection]; lpCriticalSection
0x18000b1cd  test    rcx, rcx
0x18000b1d0  jz      short loc_18000B1D8
0x18000b1d2  call    cs:__imp_LeaveCriticalSection
0x18000b1d8  test    r15, r15
0x18000b1db  jz      loc_18000AE75
0x18000b1e1  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18000b1e8  jz      loc_18000B2C4
0x18000b1ee  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18000b1f5  test    r9, r9
0x18000b1f8  jz      loc_18000B28E
0x18000b1fe  mov     rax, [r15]
0x18000b201  test    rax, rax
0x18000b204  jz      short loc_18000B275
0x18000b206  mov     r8d, [rax+8]
0x18000b20a  jmp     short loc_18000B278
0x18000b20c  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18000b213  test    rax, rax
0x18000b216  jz      short loc_18000B22E
0x18000b218  lea     rdx, aCgrouppolicyse_6; "CGroupPolicySession::CleanupEnvironment"...
0x18000b21f  mov     ecx, 4
0x18000b224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b229  jmp     loc_18000ADDC
0x18000b22e  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x18000b236  jz      loc_18000ADDC
0x18000b23c  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18000b244  jz      loc_18000ADDC
0x18000b24a  lea     rdx, aCgrouppolicyse_6; "CGroupPolicySession::CleanupEnvironment"...
0x18000b251  mov     ecx, 4; unsigned int
0x18000b256  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18000b25b  jmp     loc_18000ADDC
0x18000b260  mov     rcx, [rbx+0D8h]; hEvent
0x18000b267  test    rcx, rcx
0x18000b26a  jz      loc_18000AE75
0x18000b270  jmp     loc_18000B16B
0x18000b275  mov     r8d, ebp
0x18000b278  lea     rdx, aAbortsubscript; "AbortSubscriptions: Signalling %d Refre"...
0x18000b27f  mov     ecx, 4
0x18000b284  mov     rax, r9
0x18000b287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b28c  jmp     short loc_18000B2C4
0x18000b28e  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x18000b296  jz      short loc_18000B2C4
0x18000b298  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18000b2a0  jz      short loc_18000B2C4
0x18000b2a2  mov     rax, [r15]
0x18000b2a5  test    rax, rax
0x18000b2a8  jz      short loc_18000B2B0
0x18000b2aa  mov     r8d, [rax+8]
0x18000b2ae  jmp     short loc_18000B2B3
0x18000b2b0  mov     r8d, ebp
0x18000b2b3  lea     rdx, aAbortsubscript; "AbortSubscriptions: Signalling %d Refre"...
0x18000b2ba  mov     ecx, 4; unsigned int
0x18000b2bf  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18000b2c4  mov     rax, [r15]
0x18000b2c7  test    rax, rax
0x18000b2ca  jz      short loc_18000B302
0x18000b2cc  cmp     qword ptr [rax+8], 0
0x18000b2d1  jz      short loc_18000B302
0x18000b2d3  mov     rax, [rax]
0x18000b2d6  mov     rcx, [rax]
0x18000b2d9  mov     rdi, [rcx+10h]
0x18000b2dd  mov     [rsp+0A8h+lpCriticalSection], rdi
0x18000b2e2  mov     rcx, r15
0x18000b2e5  call    ?pop_front@?$STLWrap_List@PEAU_NOTIFY_CALLER_INFO@@@@QEAAXXZ; STLWrap_List<_NOTIFY_CALLER_INFO *>::pop_front(void)
0x18000b2ea  mov     rcx, rdi; hEvent
0x18000b2ed  call    cs:__imp_SetEvent
0x18000b2f3  lea     rdx, [rsp+0A8h+lpCriticalSection]; void **
  ... truncated ...
```
