# HbEvtpDeleteEventLog

- ea: `0x140010a78`
- end: `0x140010c04`
- name: `HbEvtpDeleteEventLog`
- size: `396`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x14000f948`
- `0x140012170`
- `0x140014810`

## callees

- `0x140001230`
- `0x140001600`
- `0x1400020f8`
- `0x140002ae0`
- `0x140010a78`
- `0x140010c0c`
- `0x1400137b0`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140010bd8`
- `ntoskrnl!KeReleaseMutex` at `0x140010bd8`
- `ntoskrnl!KeWaitForSingleObject` at `0x140010acb`
- `ntoskrnl!KeWaitForSingleObject` at `0x140010acb`

## string_xrefs

- `0x140010aef`: `HbEvtpDeleteEventLog`
- `0x140010b47`: `HbEvtpDeleteEventLog`
- `0x140010b75`: `HbEvtpDeleteEventLog`
- `0x140010ba0`: `HbEvtpDeleteEventLog`

## pseudocode

```c
__int64 __fastcall HbEvtpDeleteEventLog(__int64 a1, unsigned int a2)
{
  struct _KMUTANT *v2; // rdi
  int LogConfiguration; // eax
  __int64 v6; // rcx
  int v7; // eax
  unsigned int v9; // [rsp+30h] [rbp-30h] BYREF
  __int64 v10; // [rsp+38h] [rbp-28h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+40h] [rbp-20h] BYREF

  v2 = (struct _KMUTANT *)(a1 + 208);
  v10 = 0;
  UserData = 0;
  KeWaitForSingleObject((PVOID)(a1 + 208), Executive, 0, 0, 0);
  HbpTraceEvent(3, "HbEvtpDeleteEventLog", 2768, "Deleting event log %d", a2);
  LogConfiguration = HbEvtpGetLogConfiguration(a2, &v10);
  v9 = LogConfiguration;
  if ( LogConfiguration < 0 )
    goto LABEL_10;
  if ( v10 && *(_DWORD *)(v10 + 8) && *(_QWORD *)(v10 + 32) )
  {
    v7 = HbEvtpWaitUntilAllBuffersAreFree(v6, a2);
    v9 = v7;
    if ( v7 < 0 )
      HbpTraceEvent(0, "HbEvtpDeleteEventLog", 2793, "Failed to wait until buffers are free (0x%x)", v7);
    HbEvtpDeleteEventLogWorker(a1, a2);
    LogConfiguration = v9;
  }
  else
  {
    HbpTraceEvent(3, "HbEvtpDeleteEventLog", 2785, "Nothing to clean up for event log %d ", a2);
    LogConfiguration = 0;
    v9 = 0;
  }
  if ( LogConfiguration < 0 )
  {
LABEL_10:
    HbpTraceEvent(0, "HbEvtpDeleteEventLog", 2808, "Failed with 0x%x ", LogConfiguration);
    *(_QWORD *)&UserData.Size = 4;
    UserData.Ptr = (ULONGLONG)&v9;
    HbEvtpWriteEventLog(&HV_EVENTLOG_DELETION_FAILED, 1u, &UserData);
  }
  KeReleaseMutex(v2, 0);
  return v9;
}

```

## disassembly

```asm
0x140010a78  mov     [rsp-18h+arg_10], rbx
0x140010a7d  push    rbp
0x140010a7e  push    rsi
0x140010a7f  push    rdi
0x140010a80  mov     rbp, rsp
0x140010a83  sub     rsp, 60h
0x140010a87  mov     rax, cs:__security_cookie
0x140010a8e  xor     rax, rsp
0x140010a91  mov     [rbp+var_10], rax
0x140010a95  lea     rdi, [rcx+0D0h]
0x140010a9c  mov     [rbp+var_30], 0
0x140010aa3  mov     ebx, edx
0x140010aa5  mov     [rbp+var_28], 0
0x140010aad  mov     rsi, rcx
0x140010ab0  mov     [rsp+60h+Timeout], 0; Timeout
0x140010ab9  xorps   xmm0, xmm0
0x140010abc  mov     rcx, rdi; Object
0x140010abf  xor     r9d, r9d; Alertable
0x140010ac2  xor     r8d, r8d; WaitMode
0x140010ac5  xor     edx, edx; WaitReason
0x140010ac7  movups  xmmword ptr [rbp+UserData.Ptr], xmm0
0x140010acb  call    cs:__imp_KeWaitForSingleObject
0x140010ad2  nop     dword ptr [rax+rax+00h]
0x140010ad7  mov     [rbp+var_30], 0
0x140010ade  lea     r9, aDeletingEventL; "Deleting event log %d"
0x140010ae5  mov     dword ptr [rsp+60h+Timeout], ebx
0x140010ae9  mov     r8d, 0AD0h
0x140010aef  lea     rdx, aHbevtpdeleteev; "HbEvtpDeleteEventLog"
0x140010af6  mov     ecx, 3
0x140010afb  call    HbpTraceEvent
0x140010b00  lea     rdx, [rbp+var_28]
0x140010b04  mov     ecx, ebx
0x140010b06  call    HbEvtpGetLogConfiguration
0x140010b0b  mov     [rbp+var_30], eax
0x140010b0e  test    eax, eax
0x140010b10  js      short loc_140010B8F
0x140010b12  mov     rax, [rbp+var_28]
0x140010b16  test    rax, rax
0x140010b19  jz      short loc_140010B64
0x140010b1b  cmp     dword ptr [rax+8], 0
0x140010b1f  jz      short loc_140010B64
0x140010b21  cmp     qword ptr [rax+20h], 0
0x140010b26  jz      short loc_140010B64
0x140010b28  mov     edx, ebx
0x140010b2a  call    HbEvtpWaitUntilAllBuffersAreFree
0x140010b2f  mov     [rbp+var_30], eax
0x140010b32  test    eax, eax
0x140010b34  jns     short loc_140010B55
0x140010b36  lea     r9, aFailedToWaitUn; "Failed to wait until buffers are free ("...
0x140010b3d  mov     dword ptr [rsp+60h+Timeout], eax
0x140010b41  mov     r8d, 0AE9h
0x140010b47  lea     rdx, aHbevtpdeleteev; "HbEvtpDeleteEventLog"
0x140010b4e  xor     ecx, ecx
0x140010b50  call    HbpTraceEvent
0x140010b55  mov     edx, ebx
0x140010b57  mov     rcx, rsi
0x140010b5a  call    HbEvtpDeleteEventLogWorker
0x140010b5f  mov     eax, [rbp+var_30]
0x140010b62  jmp     short loc_140010B8B
0x140010b64  lea     r9, aNothingToClean; "Nothing to clean up for event log %d "
0x140010b6b  mov     dword ptr [rsp+60h+Timeout], ebx
0x140010b6f  mov     r8d, 0AE1h
0x140010b75  lea     rdx, aHbevtpdeleteev; "HbEvtpDeleteEventLog"
0x140010b7c  mov     ecx, 3
0x140010b81  call    HbpTraceEvent
0x140010b86  xor     eax, eax
0x140010b88  mov     [rbp+var_30], eax
0x140010b8b  test    eax, eax
0x140010b8d  jns     short loc_140010BD3
0x140010b8f  lea     r9, aFailedWith0xX; "Failed with 0x%x "
0x140010b96  mov     dword ptr [rsp+60h+Timeout], eax
0x140010b9a  mov     r8d, 0AF8h
0x140010ba0  lea     rdx, aHbevtpdeleteev; "HbEvtpDeleteEventLog"
0x140010ba7  xor     ecx, ecx
0x140010ba9  call    HbpTraceEvent
0x140010bae  lea     rax, [rbp+var_30]
0x140010bb2  mov     qword ptr [rbp+UserData.Size], 4
0x140010bba  lea     r8, [rbp+UserData]; UserData
0x140010bbe  mov     [rbp+UserData.Ptr], rax
0x140010bc2  mov     edx, 1; UserDataCount
0x140010bc7  lea     rcx, HV_EVENTLOG_DELETION_FAILED; EventDescriptor
0x140010bce  call    HbEvtpWriteEventLog
0x140010bd3  xor     edx, edx; Wait
0x140010bd5  mov     rcx, rdi; Mutex
0x140010bd8  call    cs:__imp_KeReleaseMutex
0x140010bdf  nop     dword ptr [rax+rax+00h]
0x140010be4  mov     eax, [rbp+var_30]
0x140010be7  mov     rcx, [rbp+var_10]
0x140010beb  xor     rcx, rsp; StackCookie
0x140010bee  call    __security_check_cookie
0x140010bf3  mov     rbx, [rsp+60h+arg_10]
0x140010bfb  add     rsp, 60h
0x140010bff  pop     rdi
0x140010c00  pop     rsi
0x140010c01  pop     rbp
0x140010c02  retn
```
