# Server_LockPolicySection

- ea: `0x18002ba90`
- end: `0x18002bebc`
- name: `Server_LockPolicySection`
- size: `1068`
- prototype: `__int64 __usercall@<rax>(PRPC_ASYNC_STATE pAsync@<rcx>, int, unsigned int NotificationsQueued)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18002ba90`
- `0x18002bec4`
- `0x18002bf4c`
- `0x18002bfa4`
- `0x180067934`
- `0x180075ec0`
- `0x18007d770`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002bb04`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002bb04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bc3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bc91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bc3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bc91`
- `RPCRT4!RpcAsyncAbortCall` at `0x18002bc7f`
- `RPCRT4!RpcAsyncAbortCall` at `0x18002bc7f`
- `RPCRT4!RpcServerSubscribeForNotification` at `0x18002bb3e`
- `RPCRT4!RpcServerSubscribeForNotification` at `0x18002bb3e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18002bc29`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18002bc29`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18002bc18`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18002bc74`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18002bc18`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18002bc74`

## string_xrefs

- `0x18002bd40`: `Creating a New Instance of CGPRPCService`
- `0x18002bd70`: `Creating a New Instance of CGPRPCService`
- `0x18002bdaa`: `Server_LockPolicySection: CreateEvent failed with %d`
- `0x18002bddd`: `Server_LockPolicySection: CreateEvent failed with %d`

## pseudocode

```c
__int64 __fastcall Server_LockPolicySection(
        PRPC_ASYNC_STATE pAsync,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        void *NotificationsQueued)
{
  struct CGPRPCServerBase *v6; // rbx
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  RPCNOTIFICATION_ROUTINE *v11; // rbp
  void *RuntimeInfo; // rcx
  unsigned int LastError; // esi
  bool v14; // zf
  __int64 result; // rax
  _QWORD *UserInfo; // rax
  void *v17; // rcx
  CGPRPCService *v18; // rax
  void *v19; // rdx
  const unsigned __int16 *v20; // r8
  CGPRPCService *v21; // rax
  struct CGPRPCServerBase *v22; // rsi
  void (*v23)(unsigned int, const unsigned __int16 *, ...); // rax
  __int64 v24; // [rsp+40h] [rbp-58h] BYREF
  RPC_ASYNC_NOTIFICATION_INFO NotificationInfo; // [rsp+48h] [rbp-50h] BYREF
  int Reply; // [rsp+A0h] [rbp+8h] BYREF

  v6 = CGPRPCServerBase::m_instance;
  v24 = 0;
  pAsync->UserInfo = NotificationsQueued;
  if ( !v6 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"Creating a New Instance of CGPRPCService");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"Creating a New Instance of CGPRPCService");
      }
    }
    v18 = (CGPRPCService *)operator new(0x98u, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v18 )
      goto LABEL_25;
    v21 = CGPRPCService::CGPRPCService(v18, v19, v20);
    v22 = v21;
    if ( !v21 )
      goto LABEL_25;
    if ( CGPRPCService::Initialize(v21) || CGPRPCServerBase::SetInstanceInternal(v22) )
      (**(void (__fastcall ***)(struct CGPRPCServerBase *, __int64))v22)(v22, 1);
    v6 = CGPRPCServerBase::m_instance;
    if ( !CGPRPCServerBase::m_instance )
    {
LABEL_25:
      v11 = (RPCNOTIFICATION_ROUTINE *)NotificationsQueued;
      LastError = 14;
      goto LABEL_8;
    }
  }
  _InterlockedIncrement((volatile signed __int32 *)v6 + 34);
  if ( *((_DWORD *)v6 + 8) )
  {
    LastError = 1722;
    goto LABEL_16;
  }
  if ( !*((_QWORD *)v6 + 8) )
  {
    LastError = 2;
LABEL_16:
    v11 = (RPCNOTIFICATION_ROUTINE *)NotificationsQueued;
    goto LABEL_8;
  }
  EventW = (RPCNOTIFICATION_ROUTINE *)CreateEventW(0, 1, 0, 0);
  v11 = EventW;
  if ( EventW )
  {
    RuntimeInfo = pAsync->RuntimeInfo;
    NotificationInfo.APC.NotificationRoutine = EventW;
    memset(&NotificationInfo.NotificationRoutine + 1, 0, 24);
    LastError = RpcServerSubscribeForNotification(
                  RuntimeInfo,
                  RpcNotificationCallCancel,
                  RpcNotificationTypeEvent,
                  &NotificationInfo);
    if ( !LastError )
    {
      LastError = (*(__int64 (__fastcall **)(_QWORD, PRPC_ASYNC_STATE, __int64, _QWORD, int, RPCNOTIFICATION_ROUTINE *, __int64 *))(**((_QWORD **)v6 + 8) + 32LL))(
                    *((_QWORD *)v6 + 8),
                    pAsync,
                    a3,
                    a4,
                    a5,
                    v11,
                    &v24);
      if ( !LastError )
        LastError = 0;
      goto LABEL_8;
    }
    v23 = g_lpDebugMsg;
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_8;
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(2u, L"Failed to subscribe for client changes with Status = 0x%x", LastError);
    }
    else
    {
      if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
      {
LABEL_47:
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( v23 )
          {
            v23(2u, L"Server_LockPolicySection: RegisterForLockClientChanges failed with %d", LastError);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"Server_LockPolicySection: RegisterForLockClientChanges failed with %d", LastError);
          }
        }
        goto LABEL_8;
      }
      RedirectDebugMsg(2u, L"Failed to subscribe for client changes with Status = 0x%x", LastError);
    }
    v23 = g_lpDebugMsg;
    goto LABEL_47;
  }
  LastError = GetLastError();
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(2u, L"Server_LockPolicySection: CreateEvent failed with %d", LastError);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(2u, L"Server_LockPolicySection: CreateEvent failed with %d", LastError);
    }
  }
LABEL_8:
  if ( v24 )
  {
    UserInfo = pAsync->UserInfo;
    Reply = 0;
    LODWORD(NotificationsQueued) = 0;
    *UserInfo = v24;
    RpcServerUnsubscribeForNotification(
      pAsync->RuntimeInfo,
      RpcNotificationCallCancel,
      (unsigned int *)&NotificationsQueued);
    RpcAsyncCompleteCall(pAsync, &Reply);
    if ( v11 )
    {
      CloseHandle(v11);
      v11 = 0;
    }
  }
  if ( LastError )
  {
    v17 = pAsync->RuntimeInfo;
    LODWORD(NotificationsQueued) = 0;
    RpcServerUnsubscribeForNotification(v17, RpcNotificationCallCancel, (unsigned int *)&NotificationsQueued);
    RpcAsyncAbortCall(pAsync, LastError);
    if ( v11 )
      CloseHandle(v11);
  }
  if ( !v6 )
    return LastError;
  _InterlockedDecrement((volatile signed __int32 *)v6 + 34);
  v14 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_GpsvcRaceCondition>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_GpsvcRaceCondition>::GetImpl'::`2'::impl) == 0;
  result = LastError;
  if ( v14 )
    *((_DWORD *)v6 + 35) = 1;
  else
    *((_BYTE *)v6 + 144) = 1;
  return result;
}

```

## disassembly

```asm
0x18002ba90  mov     rax, rsp
0x18002ba93  push    rbx
0x18002ba94  push    rsi
0x18002ba95  sub     rsp, 88h
0x18002ba9c  mov     rbx, cs:?m_instance@CGPRPCServerBase@@1PEAV1@EA; CGPRPCServerBase * CGPRPCServerBase::m_instance
0x18002baa3  mov     [rax+10h], rbp
0x18002baa7  mov     [rax+18h], rdi
0x18002baab  mov     rdi, rcx
0x18002baae  mov     [rax-18h], r12
0x18002bab2  xor     r12d, r12d
0x18002bab5  mov     [rax-20h], r14
0x18002bab9  mov     r14d, r9d
0x18002babc  mov     [rax-28h], r15
0x18002bac0  mov     r15, r8
0x18002bac3  mov     [rax-58h], r12
0x18002bac7  mov     rax, [rsp+98h+NotificationsQueued]
0x18002bacf  mov     [rcx+18h], rax
0x18002bad3  test    rbx, rbx
0x18002bad6  jz      loc_18002BC9C
0x18002badc  lock inc dword ptr [rbx+88h]
0x18002bae3  cmp     [rbx+20h], r12d
0x18002bae7  jnz     loc_18002BD15
0x18002baed  cmp     [rbx+40h], r12
0x18002baf1  jz      loc_18002BC49
0x18002baf7  xor     r9d, r9d; lpName
0x18002bafa  xor     r8d, r8d; bInitialState
0x18002bafd  mov     edx, 1; bManualReset
0x18002bb02  xor     ecx, ecx; lpEventAttributes
0x18002bb04  call    cs:__imp_CreateEventW
0x18002bb0a  mov     rbp, rax
0x18002bb0d  test    rax, rax
0x18002bb10  jz      loc_18002BD86
0x18002bb16  mov     rcx, [rdi+20h]; Binding
0x18002bb1a  lea     r9, [rsp+98h+NotificationInfo]; NotificationInfo
0x18002bb1f  xorps   xmm0, xmm0
0x18002bb22  mov     qword ptr [rsp+98h+NotificationInfo], rbp
0x18002bb27  xor     eax, eax
0x18002bb29  mov     edx, 2; Notification
0x18002bb2e  mov     r8d, 1; NotificationType
0x18002bb34  mov     qword ptr [rsp+98h+NotificationInfo+18h], rax
0x18002bb39  movups  xmmword ptr [rsp+98h+NotificationInfo+8], xmm0
0x18002bb3e  call    cs:__imp_RpcServerSubscribeForNotification
0x18002bb44  mov     esi, eax
0x18002bb46  test    eax, eax
0x18002bb48  jnz     loc_18002BDF3
0x18002bb4e  mov     rcx, [rbx+40h]
0x18002bb52  lea     rdx, [rsp+98h+var_58]
0x18002bb57  mov     [rsp+98h+var_68], rdx
0x18002bb5c  mov     r9d, r14d
0x18002bb5f  mov     edx, [rsp+98h+arg_20]
0x18002bb66  mov     r8, r15
0x18002bb69  mov     [rsp+98h+var_70], rbp
0x18002bb6e  mov     rax, [rcx]
0x18002bb71  mov     [rsp+98h+var_78], edx
0x18002bb75  mov     rdx, rdi
0x18002bb78  mov     rax, [rax+20h]
0x18002bb7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb81  mov     esi, eax
0x18002bb83  test    eax, eax
0x18002bb85  jnz     short loc_18002BB8A
0x18002bb87  mov     esi, r12d
0x18002bb8a  mov     rcx, [rsp+98h+var_58]
0x18002bb8f  mov     r15, [rsp+98h+var_28]
0x18002bb94  mov     r14, [rsp+98h+var_20]
0x18002bb99  test    rcx, rcx
0x18002bb9c  jnz     short loc_18002BBF0
0x18002bb9e  test    esi, esi
0x18002bba0  jnz     loc_18002BC5B
0x18002bba6  mov     r12, [rsp+98h+var_18]
0x18002bbae  mov     rdi, [rsp+98h+arg_10]
0x18002bbb6  mov     rbp, [rsp+98h+arg_8]
0x18002bbbe  test    rbx, rbx
0x18002bbc1  jz      loc_18002BD09
0x18002bbc7  lock dec dword ptr [rbx+88h]
0x18002bbce  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_GpsvcRaceCondition@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_GpsvcRaceCondition@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_GpsvcRaceCondition> `wil::Feature<__WilFeatureTraits_Feature_Servicing_GpsvcRaceCondition>::GetImpl(void)'::`2'::impl
0x18002bbd5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_GpsvcRaceCondition@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_GpsvcRaceCondition>::__private_IsEnabled(void)
0x18002bbda  test    al, al
0x18002bbdc  mov     eax, esi
0x18002bbde  jz      loc_18002BEAD
0x18002bbe4  mov     byte ptr [rbx+90h], 1
0x18002bbeb  jmp     loc_18002BD0B
0x18002bbf0  mov     rax, [rdi+18h]
0x18002bbf4  lea     r8, [rsp+98h+NotificationsQueued]; NotificationsQueued
0x18002bbfc  mov     [rsp+98h+Reply], r12d
0x18002bc04  mov     edx, 2; Notification
0x18002bc09  mov     dword ptr [rsp+98h+NotificationsQueued], r12d
0x18002bc11  mov     [rax], rcx
0x18002bc14  mov     rcx, [rdi+20h]; Binding
0x18002bc18  call    cs:__imp_RpcServerUnsubscribeForNotification
0x18002bc1e  lea     rdx, [rsp+98h+Reply]; Reply
0x18002bc26  mov     rcx, rdi; pAsync
0x18002bc29  call    cs:__imp_RpcAsyncCompleteCall
0x18002bc2f  test    rbp, rbp
0x18002bc32  jz      loc_18002BB9E
0x18002bc38  mov     rcx, rbp; hObject
0x18002bc3b  call    cs:__imp_CloseHandle
0x18002bc41  mov     rbp, r12
0x18002bc44  jmp     loc_18002BB9E
0x18002bc49  mov     esi, 2
0x18002bc4e  mov     rbp, [rsp+98h+NotificationsQueued]
0x18002bc56  jmp     loc_18002BB8A
0x18002bc5b  mov     rcx, [rdi+20h]; Binding
0x18002bc5f  lea     r8, [rsp+98h+NotificationsQueued]; NotificationsQueued
0x18002bc67  mov     edx, 2; Notification
0x18002bc6c  mov     dword ptr [rsp+98h+NotificationsQueued], r12d
0x18002bc74  call    cs:__imp_RpcServerUnsubscribeForNotification
0x18002bc7a  mov     edx, esi; ExceptionCode
0x18002bc7c  mov     rcx, rdi; pAsync
0x18002bc7f  call    cs:__imp_RpcAsyncAbortCall
0x18002bc85  test    rbp, rbp
0x18002bc88  jz      loc_18002BBA6
0x18002bc8e  mov     rcx, rbp; hObject
0x18002bc91  call    cs:__imp_CloseHandle
0x18002bc97  jmp     loc_18002BBA6
0x18002bc9c  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18002bca3  jnz     loc_18002BD34
0x18002bca9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002bcb0  mov     ecx, 98h; unsigned __int64
0x18002bcb5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002bcba  test    rax, rax
0x18002bcbd  jz      short loc_18002BCF7
0x18002bcbf  mov     rcx, rax; this
0x18002bcc2  call    ??0CGPRPCService@@IEAA@XZ; CGPRPCService::CGPRPCService(void)
0x18002bcc7  mov     rsi, rax
0x18002bcca  test    rax, rax
0x18002bccd  jz      short loc_18002BCF7
0x18002bccf  mov     rcx, rax; this
0x18002bcd2  call    ?Initialize@CGPRPCService@@QEAAKXZ; CGPRPCService::Initialize(void)
0x18002bcd7  test    eax, eax
0x18002bcd9  jnz     short loc_18002BD1F
0x18002bcdb  mov     rcx, rsi; struct CGPRPCServerBase *
0x18002bcde  call    ?SetInstanceInternal@CGPRPCServerBase@@KAKPEAV1@@Z; CGPRPCServerBase::SetInstanceInternal(CGPRPCServerBase *)
0x18002bce3  test    eax, eax
0x18002bce5  jnz     short loc_18002BD1F
0x18002bce7  mov     rbx, cs:?m_instance@CGPRPCServerBase@@1PEAV1@EA; CGPRPCServerBase * CGPRPCServerBase::m_instance
0x18002bcee  test    rbx, rbx
0x18002bcf1  jnz     loc_18002BADC
0x18002bcf7  mov     rbp, [rsp+98h+NotificationsQueued]
0x18002bcff  mov     esi, 0Eh
0x18002bd04  jmp     loc_18002BB8A
0x18002bd09  mov     eax, esi
0x18002bd0b  add     rsp, 88h
0x18002bd12  pop     rsi
0x18002bd13  pop     rbx
0x18002bd14  retn
0x18002bd15  mov     esi, 6BAh
0x18002bd1a  jmp     loc_18002BC4E
0x18002bd1f  mov     rax, [rsi]
0x18002bd22  mov     edx, 1
0x18002bd27  mov     rcx, rsi
0x18002bd2a  mov     rax, [rax]
0x18002bd2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd32  jmp     short loc_18002BCE7
0x18002bd34  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18002bd3b  test    rax, rax
0x18002bd3e  jz      short loc_18002BD56
0x18002bd40  lea     rdx, aCreatingANewIn; "Creating a New Instance of CGPRPCServic"...
0x18002bd47  mov     ecx, 4
0x18002bd4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd51  jmp     loc_18002BCA9
0x18002bd56  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18002bd5d  jz      loc_18002BCA9
0x18002bd63  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18002bd6a  jz      loc_18002BCA9
0x18002bd70  lea     rdx, aCreatingANewIn; "Creating a New Instance of CGPRPCServic"...
0x18002bd77  mov     ecx, 4; unsigned int
0x18002bd7c  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18002bd81  jmp     loc_18002BCA9
0x18002bd86  call    cs:__imp_GetLastError
0x18002bd8c  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18002bd93  mov     esi, eax
0x18002bd95  jz      loc_18002BB8A
0x18002bd9b  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18002bda2  test    rax, rax
0x18002bda5  jz      short loc_18002BDC0
0x18002bda7  mov     r8d, esi
0x18002bdaa  lea     rdx, aServerLockpoli_0; "Server_LockPolicySection: CreateEvent f"...
0x18002bdb1  mov     ecx, 2
0x18002bdb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bdbb  jmp     loc_18002BB8A
0x18002bdc0  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18002bdc7  jz      loc_18002BB8A
0x18002bdcd  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18002bdd4  jz      loc_18002BB8A
0x18002bdda  mov     r8d, esi
0x18002bddd  lea     rdx, aServerLockpoli_0; "Server_LockPolicySection: CreateEvent f"...
0x18002bde4  mov     ecx, 2; unsigned int
0x18002bde9  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18002bdee  jmp     loc_18002BB8A
0x18002bdf3  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18002bdfa  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18002be01  jz      loc_18002BB8A
0x18002be07  test    rax, rax
0x18002be0a  jz      short loc_18002BE22
0x18002be0c  mov     r8d, esi
0x18002be0f  lea     rdx, aFailedToSubscr; "Failed to subscribe for client changes "...
0x18002be16  mov     ecx, 2
0x18002be1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be20  jmp     short loc_18002BE48
0x18002be22  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18002be29  jz      short loc_18002BE4F
0x18002be2b  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18002be32  jz      short loc_18002BE4F
0x18002be34  mov     r8d, esi
0x18002be37  lea     rdx, aFailedToSubscr; "Failed to subscribe for client changes "...
0x18002be3e  mov     ecx, 2; unsigned int
0x18002be43  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18002be48  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18002be4f  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18002be56  jz      loc_18002BB8A
0x18002be5c  test    rax, rax
0x18002be5f  jz      short loc_18002BE7A
0x18002be61  mov     r8d, esi
0x18002be64  lea     rdx, aServerLockpoli; "Server_LockPolicySection: RegisterForLo"...
0x18002be6b  mov     ecx, 2
0x18002be70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be75  jmp     loc_18002BB8A
0x18002be7a  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18002be81  jz      loc_18002BB8A
0x18002be87  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18002be8e  jz      loc_18002BB8A
0x18002be94  mov     r8d, esi
0x18002be97  lea     rdx, aServerLockpoli; "Server_LockPolicySection: RegisterForLo"...
0x18002be9e  mov     ecx, 2; unsigned int
0x18002bea3  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18002bea8  jmp     loc_18002BB8A
0x18002bead  mov     dword ptr [rbx+8Ch], 1
0x18002beb7  jmp     loc_18002BD0B
```
