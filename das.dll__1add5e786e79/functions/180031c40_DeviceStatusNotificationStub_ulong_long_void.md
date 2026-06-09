# DeviceStatusNotificationStub(ulong,long,void *)

- ea: `0x180031c40`
- end: `0x180031f1b`
- name: `?DeviceStatusNotificationStub@@YAJKJPEAX@Z`
- size: `731`
- prototype: `__int64 __fastcall(int, int, char *)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800549f4`
- `0x180056ca0`
- `0x180063a20`

## callees

- `0x180031c40`
- `0x180031f24`
- `0x180033470`
- `0x1800335bc`
- `0x1800345f0`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031d7d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031dd7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031e51`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031d7d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031dd7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031e51`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180031c8d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180031c8d`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180031e46`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180031e46`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x180031e1e`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x180031e1e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180031c68`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180031c68`

## pseudocode

```c
__int64 __fastcall DeviceStatusNotificationStub(int a1, int a2, char *a3)
{
  __int64 v5; // rcx
  int v6; // r8d
  int v7; // edx
  bool v8; // zf
  __int64 v9; // rax
  const wchar_t **v10; // rax
  const wchar_t *v11; // rax
  int v12; // edi
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rcx
  struct _RPC_ASYNC_STATE *v16; // rcx
  int v17; // edx
  int v18; // r8d
  int Reply; // [rsp+78h] [rbp+10h] BYREF
  unsigned int NotificationsQueued; // [rsp+80h] [rbp+18h] BYREF

  Reply = a2;
  EventActivityIdControl(2u, (LPGUID)(a3 + 348));
  if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 0x10) != 0 )
    McTemplateU0p_EventWriteTransfer(v5, ASSOC_READ_PROVIDER_STOP, a3);
  AcquireSRWLockExclusive((PSRWLOCK)a3 + 6);
  v7 = Reply;
  v8 = Reply == 0;
  if ( Reply < 0 )
  {
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v9 = *((_QWORD *)a3 + 46);
      if ( !v9 || (v10 = *(const wchar_t ***)(v9 + 24)) == 0 || (v11 = *v10) == 0 )
        v11 = L"unknown";
      WPP_RECORDER_SF_SSqD(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        Reply,
        v6,
        169,
        &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
        *((_QWORD *)a3 + 1),
        (__int64)v11,
        (char)a3,
        0);
      v7 = Reply;
    }
    v8 = v7 == 0;
  }
  if ( v8 && !*((_DWORD *)a3 + 9) )
  {
    **((_DWORD **)a3 + 23) = a1;
    v7 = Reply;
  }
  if ( *((_DWORD *)a3 + 10) )
  {
    *((_DWORD *)a3 + 7) = -1;
    v12 = -2147416294;
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_SqD(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v7,
        v6,
        170,
        &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
        *((_QWORD *)a3 + 1),
        (char)a3,
        26);
    *((_DWORD *)a3 + 10) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)a3 + 6);
LABEL_34:
    if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 0x10) != 0 )
      McTemplateU0p_EventWriteTransfer(v13, ASSOC_DEVICE_STATUS_STOP, a3);
    (*(void (__fastcall **)(char *))(*(_QWORD *)a3 + 16LL))(a3);
    return (unsigned int)v12;
  }
  if ( !*((_DWORD *)a3 + 9) )
  {
    v14 = 7;
    if ( v7 )
      v14 = -1;
    *((_DWORD *)a3 + 7) = v14;
    if ( *((_DWORD *)a3 + 94) )
    {
      v15 = *((_QWORD *)a3 + 25);
      NotificationsQueued = 0;
      RpcServerUnsubscribeForNotification(
        *(RPC_BINDING_HANDLE *)(v15 + 32),
        RpcNotificationCallCancel,
        &NotificationsQueued);
      (*(void (__fastcall **)(char *))(*(_QWORD *)a3 + 16LL))(a3);
    }
    v16 = (struct _RPC_ASYNC_STATE *)*((_QWORD *)a3 + 25);
    *((_DWORD *)a3 + 9) = 1;
    v12 = RpcAsyncCompleteCall(v16, &Reply);
    ReleaseSRWLockExclusive((PSRWLOCK)a3 + 6);
    if ( !v12 || v12 == 1818 )
    {
      v12 = 0;
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_Sq(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v17,
          v18,
          173,
          &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
          *((_QWORD *)a3 + 1),
          (char)a3);
    }
    else
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_SqD(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v17,
          v18,
          172,
          &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
          *((_QWORD *)a3 + 1),
          (char)a3,
          v12);
      if ( v12 >= 0 )
        v12 = (unsigned __int16)v12 | 0x80010000;
    }
    goto LABEL_34;
  }
  v12 = -2147418113;
  *((_DWORD *)a3 + 7) = -1;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_SqD(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v7,
      v6,
      171,
      &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
      *((_QWORD *)a3 + 1),
      (char)a3,
      255);
  ReleaseSRWLockExclusive((PSRWLOCK)a3 + 6);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180031c40  mov     [rsp+arg_0], rbx
0x180031c45  mov     [rsp+arg_18], rsi
0x180031c4a  mov     [rsp+Reply], edx
0x180031c4e  push    rdi
0x180031c4f  push    r14
0x180031c51  push    r15
0x180031c53  sub     rsp, 50h
0x180031c57  mov     edi, ecx
0x180031c59  lea     rdx, [r8+15Ch]; ActivityId
0x180031c60  mov     ecx, 2; ControlCode
0x180031c65  mov     rbx, r8
0x180031c68  call    cs:__imp_EventActivityIdControl
0x180031c6e  test    byte ptr cs:Microsoft_Windows_DeviceAssociationServiceEnableBits, 10h
0x180031c75  jz      short loc_180031C86
0x180031c77  mov     r8, rbx
0x180031c7a  lea     rdx, ASSOC_READ_PROVIDER_STOP
0x180031c81  call    McTemplateU0p_EventWriteTransfer
0x180031c86  lea     rsi, [rbx+30h]
0x180031c8a  mov     rcx, rsi; SRWLock
0x180031c8d  call    cs:__imp_AcquireSRWLockExclusive
0x180031c93  mov     edx, [rsp+68h+Reply]; int
0x180031c97  lea     r15, WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids
0x180031c9e  lea     r14, WPP_RECORDER_INITIALIZED
0x180031ca5  test    edx, edx
0x180031ca7  jns     short loc_180031D12
0x180031ca9  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180031cb0  jz      short loc_180031D10
0x180031cb2  mov     rax, [rbx+170h]
0x180031cb9  test    rax, rax
0x180031cbc  jz      short loc_180031CCF
0x180031cbe  mov     rax, [rax+18h]
0x180031cc2  test    rax, rax
0x180031cc5  jz      short loc_180031CCF
0x180031cc7  mov     rax, [rax]
0x180031cca  test    rax, rax
0x180031ccd  jnz     short loc_180031CD6
0x180031ccf  lea     rax, aUnknown_0; "unknown"
0x180031cd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180031cdd  mov     r9d, 0A9h; int
0x180031ce3  mov     dword ptr [rsp+68h+var_28], 0; char
0x180031ceb  mov     qword ptr [rsp+68h+var_30], rbx; char
0x180031cf0  mov     qword ptr [rsp+68h+var_38], rax; __int64
0x180031cf5  mov     rax, [rbx+8]
0x180031cf9  mov     rcx, [rcx+28h]; int
0x180031cfd  mov     [rsp+68h+var_40], rax; __int64
0x180031d02  mov     [rsp+68h+MessageGuid], r15; MessageGuid
0x180031d07  call    WPP_RECORDER_SF_SSqD
0x180031d0c  mov     edx, [rsp+68h+Reply]
0x180031d10  test    edx, edx
0x180031d12  jnz     short loc_180031D27
0x180031d14  cmp     dword ptr [rbx+24h], 0
0x180031d18  jnz     short loc_180031D27
0x180031d1a  mov     rax, [rbx+0B8h]
0x180031d21  mov     [rax], edi
0x180031d23  mov     edx, [rsp+68h+Reply]; int
0x180031d27  cmp     dword ptr [rbx+28h], 0
0x180031d2b  jz      short loc_180031D88
0x180031d2d  mov     dword ptr [rbx+1Ch], 0FFFFFFFFh
0x180031d34  mov     edi, 8001071Ah
0x180031d39  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180031d40  jz      short loc_180031D73
0x180031d42  mov     rcx, cs:WPP_GLOBAL_Control
0x180031d49  mov     r9d, 0AAh; int
0x180031d4f  mov     rax, [rbx+8]
0x180031d53  mov     dword ptr [rsp+68h+var_30], 8001071Ah; char
0x180031d5b  mov     qword ptr [rsp+68h+var_38], rbx; char
0x180031d60  mov     rcx, [rcx+28h]; int
0x180031d64  mov     [rsp+68h+var_40], rax; __int64
0x180031d69  mov     [rsp+68h+MessageGuid], r15; MessageGuid
0x180031d6e  call    WPP_RECORDER_SF_SqD
0x180031d73  mov     rcx, rsi; SRWLock
0x180031d76  mov     dword ptr [rbx+28h], 0
0x180031d7d  call    cs:__imp_ReleaseSRWLockExclusive
0x180031d83  jmp     loc_180031EDC
0x180031d88  cmp     dword ptr [rbx+24h], 0
0x180031d8c  jz      short loc_180031DE2
0x180031d8e  mov     edi, 8000FFFFh
0x180031d93  mov     dword ptr [rbx+1Ch], 0FFFFFFFFh
0x180031d9a  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180031da1  jz      short loc_180031DD4
0x180031da3  mov     rcx, cs:WPP_GLOBAL_Control
0x180031daa  mov     r9d, 0ABh; int
0x180031db0  mov     rax, [rbx+8]
0x180031db4  mov     dword ptr [rsp+68h+var_30], 8000FFFFh; char
0x180031dbc  mov     qword ptr [rsp+68h+var_38], rbx; char
0x180031dc1  mov     rcx, [rcx+28h]; int
0x180031dc5  mov     [rsp+68h+var_40], rax; __int64
0x180031dca  mov     [rsp+68h+MessageGuid], r15; MessageGuid
0x180031dcf  call    WPP_RECORDER_SF_SqD
0x180031dd4  mov     rcx, rsi; SRWLock
0x180031dd7  call    cs:__imp_ReleaseSRWLockExclusive
0x180031ddd  jmp     loc_180031F03
0x180031de2  or      ecx, 0FFFFFFFFh
0x180031de5  mov     eax, 7
0x180031dea  test    edx, edx
0x180031dec  cmovnz  eax, ecx
0x180031def  mov     [rbx+1Ch], eax
0x180031df2  cmp     dword ptr [rbx+178h], 0
0x180031df9  jz      short loc_180031E33
0x180031dfb  mov     rcx, [rbx+0C8h]
0x180031e02  lea     r8, [rsp+68h+NotificationsQueued]; NotificationsQueued
0x180031e0a  mov     edx, 2; Notification
0x180031e0f  mov     [rsp+68h+NotificationsQueued], 0
0x180031e1a  mov     rcx, [rcx+20h]; Binding
0x180031e1e  call    cs:__imp_RpcServerUnsubscribeForNotification
0x180031e24  mov     rax, [rbx]
0x180031e27  mov     rcx, rbx
0x180031e2a  mov     rax, [rax+10h]
0x180031e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e33  mov     rcx, [rbx+0C8h]; pAsync
0x180031e3a  lea     rdx, [rsp+68h+Reply]; Reply
0x180031e3f  mov     dword ptr [rbx+24h], 1
0x180031e46  call    cs:__imp_RpcAsyncCompleteCall
0x180031e4c  mov     rcx, rsi; SRWLock
0x180031e4f  mov     edi, eax
0x180031e51  call    cs:__imp_ReleaseSRWLockExclusive
0x180031e57  test    edi, edi
0x180031e59  jz      short loc_180031EA8
0x180031e5b  cmp     edi, 71Ah
0x180031e61  jz      short loc_180031EA8
0x180031e63  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180031e6a  jz      short loc_180031E99
0x180031e6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180031e73  mov     r9d, 0ACh; int
0x180031e79  mov     rax, [rbx+8]
0x180031e7d  mov     dword ptr [rsp+68h+var_30], edi; char
0x180031e81  mov     qword ptr [rsp+68h+var_38], rbx; char
0x180031e86  mov     rcx, [rcx+28h]; int
0x180031e8a  mov     [rsp+68h+var_40], rax; __int64
0x180031e8f  mov     [rsp+68h+MessageGuid], r15; MessageGuid
0x180031e94  call    WPP_RECORDER_SF_SqD
0x180031e99  test    edi, edi
0x180031e9b  js      short loc_180031EDC
0x180031e9d  movzx   edi, di
0x180031ea0  or      edi, 80010000h
0x180031ea6  jmp     short loc_180031EDC
0x180031ea8  xor     edi, edi
0x180031eaa  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180031eb1  jz      short loc_180031EDC
0x180031eb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180031eba  mov     r9d, 0ADh; int
0x180031ec0  mov     rax, [rbx+8]
0x180031ec4  mov     qword ptr [rsp+68h+var_38], rbx; char
0x180031ec9  mov     [rsp+68h+var_40], rax; __int64
0x180031ece  mov     rcx, [rcx+28h]; int
0x180031ed2  mov     [rsp+68h+MessageGuid], r15; MessageGuid
0x180031ed7  call    WPP_RECORDER_SF_Sq
0x180031edc  test    byte ptr cs:Microsoft_Windows_DeviceAssociationServiceEnableBits, 10h
0x180031ee3  jz      short loc_180031EF4
0x180031ee5  mov     r8, rbx
0x180031ee8  lea     rdx, ASSOC_DEVICE_STATUS_STOP
0x180031eef  call    McTemplateU0p_EventWriteTransfer
0x180031ef4  mov     rcx, [rbx]
0x180031ef7  mov     rax, [rcx+10h]
0x180031efb  mov     rcx, rbx
0x180031efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f03  lea     r11, [rsp+68h+var_18]
0x180031f08  mov     eax, edi
0x180031f0a  mov     rbx, [r11+20h]
0x180031f0e  mov     rsi, [r11+38h]
0x180031f12  mov     rsp, r11
0x180031f15  pop     r15
0x180031f17  pop     r14
0x180031f19  pop     rdi
0x180031f1a  retn
```
