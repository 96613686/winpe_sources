# MosHostGetDataAsync

- ea: `0x180007680`
- end: `0x180007925`
- name: `MosHostGetDataAsync`
- size: `677`
- prototype: `RPC_STATUS __fastcall(PRPC_ASYNC_STATE pAsync, __int64, unsigned int, unsigned int, unsigned int, int, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001d00`
- `0x18000210c`
- `0x180006e20`
- `0x180007680`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800078dc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800078dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800078ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800078ff`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x1800078b6`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x1800078b6`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800078c4`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800078c4`
- `RPCRT4!RpcServerSubscribeForNotification` at `0x18000776d`
- `RPCRT4!RpcServerSubscribeForNotification` at `0x18000776d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800078eb`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800078eb`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x1800076f6`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x1800076f6`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800077b7`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180007896`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800077b7`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180007896`

## pseudocode

```c
RPC_STATUS __fastcall MosHostGetDataAsync(
        PRPC_ASYNC_STATE pAsync,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        int a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11)
{
  unsigned int v11; // ebx
  int v13; // r8d
  unsigned int v14; // ecx
  RPC_STATUS result; // eax
  void *RuntimeInfo; // rcx
  RPC_STATUS v17; // eax
  int v18; // eax
  int v19; // ebx
  __int64 v20; // rdi
  __int64 v21; // rax
  __int64 (__fastcall *v22)(__int64, __int64, __int64, _QWORD, bool, PRPC_ASYNC_STATE, _BYTE *); // rbx
  _QWORD *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  _BYTE *v26; // rdx
  void *v27; // rcx
  HANDLE v28; // rcx
  unsigned int Reply; // [rsp+40h] [rbp-B1h] BYREF
  unsigned int NotificationsQueued; // [rsp+48h] [rbp-A9h] BYREF
  __int64 v31; // [rsp+50h] [rbp-A1h]
  char Context[16]; // [rsp+58h] [rbp-99h] BYREF
  HANDLE WaitHandle; // [rsp+68h] [rbp-89h]
  HANDLE hEvent; // [rsp+70h] [rbp-81h]
  RPC_ASYNC_NOTIFICATION_INFO NotificationInfo; // [rsp+78h] [rbp-79h] BYREF
  _BYTE v36[56]; // [rsp+A0h] [rbp-51h] BYREF
  _BYTE *v37; // [rsp+D8h] [rbp-19h]

  NotificationsQueued = a3;
  v11 = a2;
  v31 = a2;
  Reply = a4;
  memset(&NotificationInfo, 0, sizeof(NotificationInfo));
  ScopedWatchdogTimer::ScopedWatchdogTimer(
    Context,
    0x493E0u,
    (void (*)(void))ScopedWatchdogHandlers::MosHostDeleteDataAsync_CrashOnTimerExpired);
  if ( !a7 )
  {
    v13 = 263;
LABEL_3:
    v14 = -2147467261;
LABEL_4:
    result = ZTraceReportOriginationNoThis(v14, "MosHostGetDataAsync", v13);
    goto LABEL_17;
  }
  if ( !a8 )
  {
    v13 = 264;
    goto LABEL_3;
  }
  if ( !a9 )
  {
    v13 = 265;
    goto LABEL_3;
  }
  if ( !a10 )
  {
    v13 = 266;
    goto LABEL_3;
  }
  if ( !a11 )
  {
    v13 = 267;
    goto LABEL_3;
  }
  RuntimeInfo = pAsync->RuntimeInfo;
  NotificationInfo.APC.NotificationRoutine = (PFN_RPCNOTIFICATION_ROUTINE)MosHostGetDataAsyncCancel;
  v17 = RpcServerSubscribeForNotification(
          RuntimeInfo,
          RpcNotificationCallCancel,
          RpcNotificationTypeCallback,
          &NotificationInfo);
  if ( v17 )
  {
    v13 = 275;
    v14 = v17 | 0x80010000;
    goto LABEL_4;
  }
  v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)qword_1800185D0 + 256LL))(
          qword_1800185D0,
          v11,
          0);
  if ( v18 < 0 )
  {
    result = ZTraceReportPropagationNoThis(v18, "MosHostGetDataAsync", 277);
LABEL_17:
    v19 = result;
    if ( result >= 0 )
      goto LABEL_25;
    goto LABEL_24;
  }
  v20 = qword_1800185D0;
  v21 = *(_QWORD *)qword_1800185D0;
  v37 = 0;
  v22 = *(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, bool, PRPC_ASYNC_STATE, _BYTE *))(v21 + 128);
  v23 = operator new(0x48u);
  v24 = Reply;
  v25 = NotificationsQueued;
  *v23 = off_18000E0A8;
  v23[2] = v31;
  v23[4] = a7;
  v23[1] = pAsync;
  *((_DWORD *)v23 + 6) = v24;
  *((_DWORD *)v23 + 7) = v25;
  v23[5] = a8;
  v23[6] = a9;
  v23[7] = a10;
  v23[8] = a11;
  v37 = v23;
  result = v22(v20, v24, v25, a5, a6 != 0, pAsync, v36);
  v19 = result;
  if ( v37 )
  {
    v26 = v36;
    LOBYTE(v26) = v37 != v36;
    result = (*(__int64 (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v37 + 32LL))(v37, v26);
  }
  if ( v19 < 0 )
  {
    if ( v19 != -2147023673 )
      ZTraceReportPropagationNoThis(v19, "MosHostGetDataAsync", 310);
LABEL_24:
    v27 = pAsync->RuntimeInfo;
    Reply = v19;
    NotificationsQueued = 0;
    RpcServerUnsubscribeForNotification(v27, RpcNotificationCallCancel, &NotificationsQueued);
    result = RpcAsyncCompleteCall(pAsync, &Reply);
  }
LABEL_25:
  v28 = hEvent;
  if ( hEvent )
  {
    if ( WaitHandle )
    {
      SetEvent(hEvent);
      UnregisterWaitEx(WaitHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      v28 = hEvent;
      WaitHandle = 0;
    }
    return CloseHandle(v28);
  }
  return result;
}

```

## disassembly

```asm
0x180007680  push    rbp
0x180007682  push    rbx
0x180007683  push    rsi
0x180007684  push    rdi
0x180007685  push    r12
0x180007687  push    r13
0x180007689  push    r14
0x18000768b  push    r15
0x18000768d  lea     rbp, [rsp-7]
0x180007692  sub     rsp, 0F8h
0x180007699  mov     rax, cs:__security_cookie
0x1800076a0  xor     rax, rsp
0x1800076a3  mov     [rbp+3Fh+var_50], rax
0x1800076a7  xorps   xmm0, xmm0
0x1800076aa  mov     [rsp+130h+NotificationsQueued], r8d
0x1800076af  mov     rbx, rdx
0x1800076b2  mov     [rsp+130h+var_E0], rdx
0x1800076b7  mov     rsi, rcx
0x1800076ba  mov     [rsp+130h+Reply], r9d
0x1800076bf  lea     r8, ?MosHostDeleteDataAsync_CrashOnTimerExpired@ScopedWatchdogHandlers@@YAXXZ; void (*)(void)
0x1800076c6  mov     edx, 493E0h; unsigned int
0x1800076cb  lea     rcx, [rsp+130h+Context]; Context
0x1800076d0  movups  xmmword ptr [rbp+3Fh+NotificationInfo], xmm0
0x1800076d4  movups  xmmword ptr [rbp+3Fh+NotificationInfo+10h], xmm0
0x1800076d8  call    ??0ScopedWatchdogTimer@@QEAA@KP6AXXZ@Z; ScopedWatchdogTimer::ScopedWatchdogTimer(ulong,void (*)(void))
0x1800076dd  cmp     [rbp+3Fh+arg_30], 0
0x1800076e2  jnz     short loc_180007701
0x1800076e4  mov     r8d, 107h
0x1800076ea  mov     ecx, 80004003h
0x1800076ef  lea     rdx, aMoshostgetdata_0; "MosHostGetDataAsync"
0x1800076f6  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x1800076fc  jmp     loc_1800077BD
0x180007701  mov     r14, [rbp+3Fh+arg_38]
0x180007708  test    r14, r14
0x18000770b  jnz     short loc_180007715
0x18000770d  mov     r8d, 108h
0x180007713  jmp     short loc_1800076EA
0x180007715  mov     r15, [rbp+3Fh+arg_40]
0x18000771c  test    r15, r15
0x18000771f  jnz     short loc_180007729
0x180007721  mov     r8d, 109h
0x180007727  jmp     short loc_1800076EA
0x180007729  mov     r12, [rbp+3Fh+arg_48]
0x180007730  test    r12, r12
0x180007733  jnz     short loc_18000773D
0x180007735  mov     r8d, 10Ah
0x18000773b  jmp     short loc_1800076EA
0x18000773d  mov     r13, [rbp+3Fh+arg_50]
0x180007744  test    r13, r13
0x180007747  jnz     short loc_180007751
0x180007749  mov     r8d, 10Bh
0x18000774f  jmp     short loc_1800076EA
0x180007751  mov     rcx, [rsi+20h]; Binding
0x180007755  lea     rax, MosHostGetDataAsyncCancel
0x18000775c  mov     edx, 2; Notification
0x180007761  mov     qword ptr [rbp+3Fh+NotificationInfo], rax
0x180007765  lea     r9, [rbp+3Fh+NotificationInfo]; NotificationInfo
0x180007769  lea     r8d, [rdx+3]; NotificationType
0x18000776d  call    cs:__imp_RpcServerSubscribeForNotification
0x180007773  test    eax, eax
0x180007775  jz      short loc_180007789
0x180007777  or      eax, 80010000h
0x18000777c  mov     r8d, 113h
0x180007782  mov     ecx, eax
0x180007784  jmp     loc_1800076EF
0x180007789  mov     rcx, cs:qword_1800185D0
0x180007790  mov     edx, ebx
0x180007792  xor     r8d, r8d
0x180007795  mov     rax, [rcx]
0x180007798  mov     rax, [rax+100h]
0x18000779f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077a4  test    eax, eax
0x1800077a6  jns     short loc_1800077CC
0x1800077a8  mov     r8d, 115h
0x1800077ae  lea     rdx, aMoshostgetdata_0; "MosHostGetDataAsync"
0x1800077b5  mov     ecx, eax
0x1800077b7  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x1800077bd  mov     ebx, eax
0x1800077bf  test    eax, eax
0x1800077c1  jns     loc_1800078CA
0x1800077c7  jmp     loc_18000789C
0x1800077cc  mov     rdi, cs:qword_1800185D0
0x1800077d3  mov     ecx, 48h ; 'H'; Size
0x1800077d8  mov     rax, [rdi]
0x1800077db  mov     [rbp+3Fh+var_58], 0
0x1800077e3  mov     rbx, [rax+80h]
0x1800077ea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800077ef  mov     edx, [rsp+130h+Reply]
0x1800077f3  lea     rcx, off_18000E0A8
0x1800077fa  mov     r8d, [rsp+130h+NotificationsQueued]
0x1800077ff  cmp     [rbp+3Fh+arg_28], 0
0x180007803  mov     r9d, [rbp+3Fh+arg_20]
0x180007807  mov     [rax], rcx
0x18000780a  mov     rcx, [rsp+130h+var_E0]
0x18000780f  mov     [rax+10h], rcx
0x180007813  mov     rcx, [rbp+3Fh+arg_30]
0x180007817  mov     [rax+20h], rcx
0x18000781b  setnz   cl
0x18000781e  mov     [rax+8], rsi
0x180007822  mov     [rax+18h], edx
0x180007825  mov     [rax+1Ch], r8d
0x180007829  mov     [rax+28h], r14
0x18000782d  mov     [rax+30h], r15
0x180007831  mov     [rax+38h], r12
0x180007835  mov     [rax+40h], r13
0x180007839  mov     [rbp+3Fh+var_58], rax
0x18000783d  lea     rax, [rbp+3Fh+var_90]
0x180007841  mov     [rsp+130h+var_100], rax
0x180007846  mov     rax, rbx
0x180007849  mov     [rsp+130h+var_108], rsi
0x18000784e  mov     [rsp+130h+var_110], cl
0x180007852  mov     rcx, rdi
0x180007855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000785a  mov     rcx, [rbp+3Fh+var_58]
0x18000785e  mov     ebx, eax
0x180007860  test    rcx, rcx
0x180007863  jz      short loc_18000787B
0x180007865  mov     rax, [rcx]
0x180007868  lea     rdx, [rbp+3Fh+var_90]
0x18000786c  cmp     rcx, rdx
0x18000786f  setnz   dl
0x180007872  mov     rax, [rax+20h]
0x180007876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000787b  test    ebx, ebx
0x18000787d  jns     short loc_1800078CA
0x18000787f  cmp     ebx, 800704C7h
0x180007885  jz      short loc_18000789C
0x180007887  mov     r8d, 136h
0x18000788d  lea     rdx, aMoshostgetdata_0; "MosHostGetDataAsync"
0x180007894  mov     ecx, ebx
0x180007896  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000789c  mov     rcx, [rsi+20h]; Binding
0x1800078a0  lea     r8, [rsp+130h+NotificationsQueued]; NotificationsQueued
0x1800078a5  mov     edx, 2; Notification
0x1800078aa  mov     [rsp+130h+Reply], ebx
0x1800078ae  mov     [rsp+130h+NotificationsQueued], 0
0x1800078b6  call    cs:__imp_RpcServerUnsubscribeForNotification
0x1800078bc  lea     rdx, [rsp+130h+Reply]; Reply
0x1800078c1  mov     rcx, rsi; pAsync
0x1800078c4  call    cs:__imp_RpcAsyncCompleteCall
0x1800078ca  mov     rcx, [rsp+130h+hEvent]; hEvent
0x1800078cf  test    rcx, rcx
0x1800078d2  jz      short loc_180007905
0x1800078d4  cmp     [rsp+130h+WaitHandle], 0
0x1800078da  jz      short loc_1800078FF
0x1800078dc  call    cs:__imp_SetEvent
0x1800078e2  mov     rcx, [rsp+130h+WaitHandle]; WaitHandle
0x1800078e7  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800078eb  call    cs:__imp_UnregisterWaitEx
0x1800078f1  mov     rcx, [rsp+130h+hEvent]; hObject
0x1800078f6  mov     [rsp+130h+WaitHandle], 0
0x1800078ff  call    cs:__imp_CloseHandle
0x180007905  mov     rcx, [rbp+3Fh+var_50]
0x180007909  xor     rcx, rsp; StackCookie
0x18000790c  call    __security_check_cookie
0x180007911  add     rsp, 0F8h
0x180007918  pop     r15
0x18000791a  pop     r14
0x18000791c  pop     r13
0x18000791e  pop     r12
0x180007920  pop     rdi
0x180007921  pop     rsi
0x180007922  pop     rbx
0x180007923  pop     rbp
0x180007924  retn
```
