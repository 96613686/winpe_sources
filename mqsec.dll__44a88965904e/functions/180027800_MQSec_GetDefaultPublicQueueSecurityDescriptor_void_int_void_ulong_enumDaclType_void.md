# MQSec_GetDefaultPublicQueueSecurityDescriptor(void * *,int,void *,ulong,enumDaclType,void *)

- ea: `0x180027800`
- end: `0x1800278d7`
- name: `?MQSec_GetDefaultPublicQueueSecurityDescriptor@@YAJPEAPEAXHPEAXKW4enumDaclType@@1@Z`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180027ca0`

## callees

- `0x180004074`
- `0x180017430`
- `0x180025eac`
- `0x180027800`

## pseudocode

```c
__int64 __fastcall MQSec_GetDefaultPublicQueueSecurityDescriptor(
        void **a1,
        unsigned int a2,
        void *a3,
        int a4,
        unsigned int a5,
        void *a6)
{
  int DefaultSecurityDescriptor; // ebx
  unsigned int v7; // eax
  __int16 v9; // [rsp+60h] [rbp-18h] BYREF
  int v10[4]; // [rsp+68h] [rbp-10h] BYREF

  DefaultSecurityDescriptor = InternalGetDefaultSecurityDescriptor(1u, a1, a2, a3, a4, a5, a6, 0);
  if ( DefaultSecurityDescriptor < 0 )
  {
    v9 = 610;
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
0x180027800  mov     [rsp+arg_0], rbx
0x180027805  push    rdi
0x180027806  sub     rsp, 70h
0x18002780a  mov     rax, [rsp+78h+arg_28]
0x180027812  mov     dword ptr [rsp+78h+var_40], 0
0x18002781a  mov     [rsp+78h+var_48], rax
0x18002781f  mov     eax, [rsp+78h+arg_20]
0x180027826  mov     dword ptr [rsp+78h+var_50], eax
0x18002782a  mov     dword ptr [rsp+78h+var_58], r9d
0x18002782f  mov     r9, r8
0x180027832  mov     r8d, edx
0x180027835  mov     rdx, rcx
0x180027838  mov     ecx, 1
0x18002783d  call    ?InternalGetDefaultSecurityDescriptor@@YAJKPEAPEAXHPEAXKW4enumDaclType@@1H@Z; InternalGetDefaultSecurityDescriptor(ulong,void * *,int,void *,ulong,enumDaclType,void *,int)
0x180027842  mov     ebx, eax
0x180027844  test    eax, eax
0x180027846  jns     short loc_1800278C7
0x180027848  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180027850  mov     eax, 262h
0x180027855  mov     [rsp+78h+var_18], ax
0x18002785a  mov     [rsp+78h+var_10], ebx
0x18002785e  jz      short loc_1800278C7
0x180027860  lea     rdi, aAcssctrlSecdsc; "acssctrl/secdscrp"
0x180027867  mov     rcx, rdi; wchar_t *
0x18002786a  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18002786f  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180027876  mov     edx, 1
0x18002787b  mov     [rsp+78h+var_28], 0
0x180027884  mov     r8d, edx
0x180027887  mov     [rsp+78h+var_30], 0
0x180027890  lea     r9d, [rax+1]
0x180027894  lea     rax, [rsp+78h+var_10]
0x180027899  add     r9, r9
0x18002789c  mov     [rsp+78h+var_38], rax
0x1800278a1  lea     rax, [rsp+78h+var_18]
0x1800278a6  mov     [rsp+78h+var_40], 4
0x1800278af  mov     [rsp+78h+var_48], rax
0x1800278b4  mov     [rsp+78h+var_50], 2
0x1800278bd  mov     [rsp+78h+var_58], rdi
0x1800278c2  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x1800278c7  mov     eax, ebx
0x1800278c9  mov     rbx, [rsp+78h+arg_0]
0x1800278d1  add     rsp, 70h
0x1800278d5  pop     rdi
0x1800278d6  retn
```
