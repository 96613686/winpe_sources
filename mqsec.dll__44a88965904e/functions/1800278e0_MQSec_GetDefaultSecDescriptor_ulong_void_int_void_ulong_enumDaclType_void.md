# MQSec_GetDefaultSecDescriptor(ulong,void * *,int,void *,ulong,enumDaclType,void *)

- ea: `0x1800278e0`
- end: `0x180027a44`
- name: `?MQSec_GetDefaultSecDescriptor@@YAJKPEAPEAXHPEAXKW4enumDaclType@@1@Z`
- size: `356`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004074`
- `0x180017430`
- `0x180025eac`
- `0x1800278e0`

## pseudocode

```c
__int64 __fastcall MQSec_GetDefaultSecDescriptor(
        unsigned __int64 a1,
        void **a2,
        __int64 a3,
        void *a4,
        int a5,
        unsigned int a6,
        PSID a7)
{
  __int64 v7; // r10
  int DefaultSecurityDescriptor; // edi
  unsigned int v9; // eax
  int v11[6]; // [rsp+60h] [rbp-18h] BYREF
  __int16 v12; // [rsp+80h] [rbp+8h] BYREF

  if ( (unsigned int)a1 <= 0x34 && (v7 = 0x10000000000102LL, _bittest64(&v7, a1)) )
  {
    DefaultSecurityDescriptor = -1072824314;
    v12 = 600;
    v11[0] = -1072824314;
    if ( g_pMSMQErrorLoggingTrace )
    {
LABEL_7:
      v9 = mqwcslen(L"acssctrl/secdscrp");
      CMSMQTrace::MSMQTraceEvent(
        g_pMSMQErrorLoggingTrace,
        1,
        1,
        2LL * (v9 + 1),
        L"acssctrl/secdscrp",
        2,
        &v12,
        4,
        v11,
        0,
        0);
    }
  }
  else
  {
    DefaultSecurityDescriptor = InternalGetDefaultSecurityDescriptor(a1, a2, a3, a4, a5, a6, a7, 0);
    if ( DefaultSecurityDescriptor < 0 )
    {
      v12 = 601;
      v11[0] = DefaultSecurityDescriptor;
      if ( g_pMSMQErrorLoggingTrace )
        goto LABEL_7;
    }
  }
  return (unsigned int)DefaultSecurityDescriptor;
}

```

## disassembly

```asm
0x1800278e0  mov     r11, rsp
0x1800278e3  mov     [r11+10h], rsi
0x1800278e7  push    rdi
0x1800278e8  sub     rsp, 70h
0x1800278ec  cmp     ecx, 34h ; '4'
0x1800278ef  ja      loc_180027975
0x1800278f5  mov     r10, 10000000000102h
0x1800278ff  bt      r10, rcx
0x180027903  jnb     short loc_180027975
0x180027905  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18002790d  mov     eax, 258h
0x180027912  mov     edi, 0C00E0006h
0x180027917  mov     [r11+8], ax
0x18002791c  mov     [rsp+78h+var_18], edi
0x180027920  jz      loc_180027A34
0x180027926  lea     rsi, aAcssctrlSecdsc; "acssctrl/secdscrp"
0x18002792d  mov     rcx, rsi; wchar_t *
0x180027930  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180027935  mov     [rsp+78h+var_28], 0
0x18002793e  lea     rcx, [rsp+78h+arg_0]
0x180027946  mov     [rsp+78h+var_30], 0
0x18002794f  mov     edx, 1
0x180027954  lea     r9d, [rdx+rax]
0x180027958  lea     rax, [rsp+78h+var_18]
0x18002795d  mov     [rsp+78h+var_38], rax
0x180027962  mov     [rsp+78h+var_40], 4
0x18002796b  mov     [rsp+78h+var_48], rcx
0x180027970  jmp     loc_180027A14
0x180027975  mov     rax, [rsp+78h+arg_30]
0x18002797d  mov     dword ptr [rsp+78h+var_40], 0
0x180027985  mov     [rsp+78h+var_48], rax
0x18002798a  mov     eax, [rsp+78h+arg_28]
0x180027991  mov     dword ptr [rsp+78h+var_50], eax
0x180027995  mov     eax, [rsp+78h+arg_20]
0x18002799c  mov     dword ptr [rsp+78h+var_58], eax
0x1800279a0  call    ?InternalGetDefaultSecurityDescriptor@@YAJKPEAPEAXHPEAXKW4enumDaclType@@1H@Z; InternalGetDefaultSecurityDescriptor(ulong,void * *,int,void *,ulong,enumDaclType,void *,int)
0x1800279a5  mov     edi, eax
0x1800279a7  test    eax, eax
0x1800279a9  jns     loc_180027A34
0x1800279af  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800279b7  mov     eax, 259h
0x1800279bc  mov     [rsp+78h+arg_0], ax
0x1800279c4  mov     [rsp+78h+var_18], edi
0x1800279c8  jz      short loc_180027A34
0x1800279ca  lea     rsi, aAcssctrlSecdsc; "acssctrl/secdscrp"
0x1800279d1  mov     rcx, rsi; wchar_t *
0x1800279d4  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x1800279d9  mov     [rsp+78h+var_28], 0
0x1800279e2  mov     edx, 1
0x1800279e7  mov     [rsp+78h+var_30], 0
0x1800279f0  lea     r9d, [rdx+rax]
0x1800279f4  lea     rax, [rsp+78h+var_18]
0x1800279f9  mov     [rsp+78h+var_38], rax
0x1800279fe  lea     rax, [rsp+78h+arg_0]
0x180027a06  mov     [rsp+78h+var_40], 4
0x180027a0f  mov     [rsp+78h+var_48], rax
0x180027a14  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180027a1b  add     r9, r9
0x180027a1e  mov     [rsp+78h+var_50], 2
0x180027a27  mov     r8d, edx
0x180027a2a  mov     [rsp+78h+var_58], rsi
0x180027a2f  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x180027a34  mov     rsi, [rsp+78h+arg_8]
0x180027a3c  mov     eax, edi
0x180027a3e  add     rsp, 70h
0x180027a42  pop     rdi
0x180027a43  retn
```
