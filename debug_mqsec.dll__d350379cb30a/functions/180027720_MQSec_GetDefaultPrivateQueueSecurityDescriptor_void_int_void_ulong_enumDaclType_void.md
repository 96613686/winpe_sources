# MQSec_GetDefaultPrivateQueueSecurityDescriptor(void * *,int,void *,ulong,enumDaclType,void *)

- ea: `0x180027720`
- end: `0x1800277f7`
- name: `?MQSec_GetDefaultPrivateQueueSecurityDescriptor@@YAJPEAPEAXHPEAXKW4enumDaclType@@1@Z`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004074`
- `0x180017430`
- `0x180025eac`
- `0x180027720`

## pseudocode

```c
__int64 __fastcall MQSec_GetDefaultPrivateQueueSecurityDescriptor(
        void **a1,
        unsigned int a2,
        __int64 a3,
        int a4,
        unsigned int a5,
        void *a6)
{
  int DefaultSecurityDescriptor; // ebx
  unsigned int v7; // eax
  __int16 v9; // [rsp+60h] [rbp-18h] BYREF
  int v10[4]; // [rsp+68h] [rbp-10h] BYREF

  DefaultSecurityDescriptor = InternalGetDefaultSecurityDescriptor(1u, a1, a2, a3, a4, a5, a6, 1);
  if ( DefaultSecurityDescriptor < 0 )
  {
    v9 = 620;
    v10[0] = DefaultSecurityDescriptor;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v7 = mqwcslen(L"acssctrl/secdscrp");
      CMSMQTrace::MSMQTraceEvent(
        g_pMSMQErrorLoggingTrace,
        1,
        1,
        2LL * (v7 + 1),
        L"acssctrl/secdscrp",
        2,
        &v9,
        4,
        v10,
        0,
        0);
    }
  }
  return (unsigned int)DefaultSecurityDescriptor;
}

```

## disassembly

```asm
0x180027720  mov     [rsp+arg_0], rbx
0x180027725  push    rdi
0x180027726  sub     rsp, 70h
0x18002772a  mov     rax, [rsp+78h+arg_28]
0x180027732  mov     dword ptr [rsp+78h+var_40], 1
0x18002773a  mov     [rsp+78h+var_48], rax
0x18002773f  mov     eax, [rsp+78h+arg_20]
0x180027746  mov     dword ptr [rsp+78h+var_50], eax
0x18002774a  mov     dword ptr [rsp+78h+var_58], r9d
0x18002774f  mov     r9, r8
0x180027752  mov     r8d, edx
0x180027755  mov     rdx, rcx
0x180027758  mov     ecx, 1
0x18002775d  call    ?InternalGetDefaultSecurityDescriptor@@YAJKPEAPEAXHPEAXKW4enumDaclType@@1H@Z; InternalGetDefaultSecurityDescriptor(ulong,void * *,int,void *,ulong,enumDaclType,void *,int)
0x180027762  mov     ebx, eax
0x180027764  test    eax, eax
0x180027766  jns     short loc_1800277E7
0x180027768  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180027770  mov     eax, 26Ch
0x180027775  mov     [rsp+78h+var_18], ax
0x18002777a  mov     [rsp+78h+var_10], ebx
0x18002777e  jz      short loc_1800277E7
0x180027780  lea     rdi, aAcssctrlSecdsc; "acssctrl/secdscrp"
0x180027787  mov     rcx, rdi; wchar_t *
0x18002778a  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18002778f  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180027796  mov     edx, 1
0x18002779b  mov     [rsp+78h+var_28], 0
0x1800277a4  mov     r8d, edx
0x1800277a7  mov     [rsp+78h+var_30], 0
0x1800277b0  lea     r9d, [rax+1]
0x1800277b4  lea     rax, [rsp+78h+var_10]
0x1800277b9  add     r9, r9
0x1800277bc  mov     [rsp+78h+var_38], rax
0x1800277c1  lea     rax, [rsp+78h+var_18]
0x1800277c6  mov     [rsp+78h+var_40], 4
0x1800277cf  mov     [rsp+78h+var_48], rax
0x1800277d4  mov     [rsp+78h+var_50], 2
0x1800277dd  mov     [rsp+78h+var_58], rdi
0x1800277e2  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x1800277e7  mov     eax, ebx
0x1800277e9  mov     rbx, [rsp+78h+arg_0]
0x1800277f1  add     rsp, 70h
0x1800277f5  pop     rdi
0x1800277f6  retn
```
