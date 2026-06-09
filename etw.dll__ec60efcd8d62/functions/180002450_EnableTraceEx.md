# EnableTraceEx

- ea: `0x180002450`
- end: `0x18000251c`
- name: `EnableTraceEx`
- size: `204`
- prototype: `ULONG __stdcall(LPCGUID ProviderId, LPCGUID SourceId, TRACEHANDLE TraceHandle, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, ULONG EnableProperty, PEVENT_FILTER_DESCRIPTOR EnableFilterDesc)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002410`

## callees

- `0x180001560`
- `0x180002450`
- `0x18000ad70`

## pseudocode

```c
ULONG __stdcall EnableTraceEx(
        LPCGUID ProviderId,
        LPCGUID SourceId,
        TRACEHANDLE TraceHandle,
        ULONG IsEnabled,
        UCHAR Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        ULONG EnableProperty,
        PEVENT_FILTER_DESCRIPTOR EnableFilterDesc)
{
  struct _ENABLE_TRACE_PARAMETERS EnableParameters; // [rsp+40h] [rbp-48h] BYREF

  EnableParameters.EnableProperty = EnableProperty;
  *(&EnableParameters.FilterDescCount + 1) = 0;
  EnableParameters.Version = 2;
  memset(&EnableParameters.ControlFlags, 0, 24);
  EnableParameters.EnableFilterDesc = EnableFilterDesc;
  EnableParameters.FilterDescCount = EnableFilterDesc != 0;
  if ( SourceId )
    EnableParameters.SourceId = *SourceId;
  return EnableTraceEx2(
           TraceHandle,
           ProviderId,
           IsEnabled,
           Level,
           MatchAnyKeyword,
           MatchAllKeyword,
           0,
           &EnableParameters);
}

```

## disassembly

```asm
0x180002450  push    rbx
0x180002452  sub     rsp, 80h
0x180002459  mov     rax, cs:__security_cookie
0x180002460  xor     rax, rsp
0x180002463  mov     [rsp+88h+var_18], rax
0x180002468  mov     eax, [rsp+88h+EnableProperty]
0x18000246f  mov     r11, r8
0x180002472  xor     r8d, r8d
0x180002475  mov     [rsp+88h+var_48.EnableProperty], eax
0x180002479  mov     eax, r8d
0x18000247c  mov     dword ptr [rsp+88h+var_48+1Ch], r8d
0x180002481  mov     r10, rcx
0x180002484  mov     dword ptr [rsp+88h+var_48+2Ch], r8d
0x180002489  mov     rcx, [rsp+88h+EnableFilterDesc]
0x180002491  xorps   xmm0, xmm0
0x180002494  test    rcx, rcx
0x180002497  mov     [rsp+88h+var_48.Version], 2
0x18000249f  mov     ebx, r9d
0x1800024a2  mov     [rsp+88h+var_48.ControlFlags], r8d
0x1800024a7  setnz   al
0x1800024aa  mov     [rsp+88h+var_48.EnableFilterDesc], rcx
0x1800024af  mov     [rsp+88h+var_48.FilterDescCount], eax
0x1800024b3  movdqu  xmmword ptr [rsp+88h+var_48.SourceId.Data1], xmm0
0x1800024b9  test    rdx, rdx
0x1800024bc  jz      short loc_1800024C7
0x1800024be  movups  xmm0, xmmword ptr [rdx]
0x1800024c1  movdqu  xmmword ptr [rsp+88h+var_48.SourceId.Data1], xmm0
0x1800024c7  mov     r9b, [rsp+88h+Level]; Level
0x1800024cf  lea     rax, [rsp+88h+var_48]
0x1800024d4  mov     [rsp+88h+EnableParameters], rax; EnableParameters
0x1800024d9  mov     rdx, r10; ProviderId
0x1800024dc  mov     rax, [rsp+88h+MatchAllKeyword]
0x1800024e4  mov     rcx, r11; TraceHandle
0x1800024e7  mov     [rsp+88h+Timeout], r8d; Timeout
0x1800024ec  mov     r8d, ebx; ControlCode
0x1800024ef  mov     [rsp+88h+var_60], rax; MatchAllKeyword
0x1800024f4  mov     rax, [rsp+88h+MatchAnyKeyword]
0x1800024fc  mov     [rsp+88h+var_68], rax; MatchAnyKeyword
0x180002501  call    EnableTraceEx2
0x180002506  mov     rcx, [rsp+88h+var_18]
0x18000250b  xor     rcx, rsp; StackCookie
0x18000250e  call    __security_check_cookie
0x180002513  add     rsp, 80h
0x18000251a  pop     rbx
0x18000251b  retn
```
