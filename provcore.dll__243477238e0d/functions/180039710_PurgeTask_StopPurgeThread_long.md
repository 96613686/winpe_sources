# PurgeTask::StopPurgeThread(long &)

- ea: `0x180039710`
- end: `0x18003988c`
- name: `?StopPurgeThread@PurgeTask@@AEAAJAEAJ@Z`
- size: `380`
- prototype: `HRESULT __fastcall(PurgeTask *this, HRESULT *ReturnCode)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180039620`

## callees

- `0x180002790`
- `0x180012748`
- `0x180012770`
- `0x180039710`
- `0x1800677d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180039808`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180039808`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039812`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039812`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800397b8`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800397b8`

## pseudocode

```c
__int64 __fastcall PurgeTask::StopPurgeThread(PurgeTask *this, HRESULT *ReturnCode)
{
  WPP_PROJECT_CONTROL_BLOCK *v4; // rcx
  HRESULT v5; // ebx
  unsigned int handleIndex; // [rsp+30h] [rbp-28h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x34u, WPP_22f7751ad0f63f57b41be0e929348283_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( this->m_taskThread )
  {
    if ( v4 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v4->ReserveSpace[28] & 0x10) != 0 )
      WPP_SF_(v4->Control.Logger, 0x35u, WPP_22f7751ad0f63f57b41be0e929348283_Traceguids);
    handleIndex = 0;
    v5 = CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, &this->m_taskThread, &handleIndex);
    if ( v5 >= 0 && handleIndex )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x36u, WPP_22f7751ad0f63f57b41be0e929348283_Traceguids, v5);
      v4 = WPP_GLOBAL_Control;
    }
    if ( v5 < 0 )
      goto LABEL_20;
    GetExitCodeThread(this->m_taskThread, (LPDWORD)ReturnCode);
    CloseHandle(this->m_taskThread);
    this->m_taskThread = 0;
    goto LABEL_19;
  }
  v5 = -2147216629;
  if ( v4 == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    return (unsigned int)v5;
  if ( (v4->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(v4->Control.Logger, 0x37u, WPP_22f7751ad0f63f57b41be0e929348283_Traceguids);
LABEL_19:
    v4 = WPP_GLOBAL_Control;
  }
LABEL_20:
  if ( v4 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v4->ReserveSpace[28] & 0x10) != 0 )
    WPP_SF_d(v4->Control.Logger, 0x38u, WPP_22f7751ad0f63f57b41be0e929348283_Traceguids, v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180039710  mov     [rsp+arg_10], rbx
0x180039715  mov     [rsp+arg_18], rsi
0x18003971a  push    rdi
0x18003971b  push    r12
0x18003971d  push    r15
0x18003971f  sub     rsp, 40h
0x180039723  mov     rax, cs:__security_cookie
0x18003972a  xor     rax, rsp
0x18003972d  mov     [rsp+58h+var_20], rax
0x180039732  mov     rsi, ReturnCode
0x180039735  mov     rdi, this
0x180039738  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003973f  lea     r15, WPP_GLOBAL_Control
0x180039746  lea     r12, WPP_22f7751ad0f63f57b41be0e929348283_Traceguids
0x18003974d  cmp     this, r15
0x180039750  jz      short loc_180039770
0x180039752  test    byte ptr [this+1Ch], 10h
0x180039756  jz      short loc_180039770
0x180039758  mov     this, [this+10h]; Logger
0x18003975c  mov     edx, 34h ; '4'; id
0x180039761  mov     r8, r12; TraceGuid
0x180039764  call    WPP_SF_
0x180039769  mov     this, cs:WPP_GLOBAL_Control
0x180039770  cmp     qword ptr [rdi+40h], 0
0x180039775  jz      loc_180039822
0x18003977b  cmp     this, r15; __annotation("TMF:",
0x18003977e  jz      short loc_180039797
0x180039780  test    byte ptr [this+1Ch], 10h
0x180039784  jz      short loc_180039797
0x180039786  mov     this, [this+10h]; Logger
0x18003978a  mov     edx, 35h ; '5'; id
0x18003978f  mov     r8, r12; TraceGuid
0x180039792  call    WPP_SF_
0x180039797  lea     rax, [rsp+58h+handleIndex]
0x18003979c  mov     [rsp+58h+handleIndex], 0
0x1800397a4  lea     r9, [rdi+40h]; pHandles
0x1800397a8  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x1800397ad  mov     r8d, 1; cHandles
0x1800397b3  or      edx, 0FFFFFFFFh; dwTimeout
0x1800397b6  xor     ecx, ecx; dwFlags
0x1800397b8  call    cs:__imp_CoWaitForMultipleHandles
0x1800397be  mov     ebx, eax
0x1800397c0  test    eax, eax
0x1800397c2  js      short loc_1800397D0
0x1800397c4  cmp     [rsp+58h+handleIndex], 0
0x1800397c9  jz      short loc_1800397D0
0x1800397cb  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "FAILED(hr) || handleIndex == 0")
0x1800397d0  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800397d7  cmp     this, r15
0x1800397da  jz      short loc_1800397FD
0x1800397dc  test    byte ptr [this+1Ch], 10h
0x1800397e0  jz      short loc_1800397FD
0x1800397e2  mov     this, [this+10h]; Logger
0x1800397e6  mov     edx, 36h ; '6'; id
0x1800397eb  mov     r9d, ebx; _a1
0x1800397ee  mov     r8, r12; TraceGuid
0x1800397f1  call    WPP_SF_d
0x1800397f6  mov     this, cs:WPP_GLOBAL_Control
0x1800397fd  test    ebx, ebx
0x1800397ff  js      short loc_18003984A
0x180039801  mov     this, [rdi+40h]; hThread
0x180039805  mov     ReturnCode, rsi; lpExitCode
0x180039808  call    cs:__imp_GetExitCodeThread
0x18003980e  mov     this, [rdi+40h]; hObject
0x180039812  call    cs:__imp_CloseHandle
0x180039818  mov     qword ptr [rdi+40h], 0
0x180039820  jmp     short loc_180039843
0x180039822  mov     ebx, 8004130Bh
0x180039827  cmp     this, r15; __annotation("TMF:",
0x18003982a  jz      short loc_180039869
0x18003982c  test    byte ptr [this+1Ch], 10h
0x180039830  jz      short loc_18003984A
0x180039832  mov     this, [this+10h]; Logger
0x180039836  mov     edx, 37h ; '7'; id
0x18003983b  mov     r8, r12; TraceGuid
0x18003983e  call    WPP_SF_
0x180039843  mov     this, cs:WPP_GLOBAL_Control
0x18003984a  cmp     this, r15; __annotation("TMF:",
0x18003984d  jz      short loc_180039869
0x18003984f  test    byte ptr [this+1Ch], 10h
0x180039853  jz      short loc_180039869
0x180039855  mov     this, [this+10h]; Logger
0x180039859  mov     edx, 38h ; '8'; id
0x18003985e  mov     r9d, ebx; _a1
0x180039861  mov     r8, r12; TraceGuid
0x180039864  call    WPP_SF_d
0x180039869  mov     eax, ebx
0x18003986b  mov     this, [rsp+58h+var_20]
0x180039870  xor     this, rsp; StackCookie
0x180039873  call    __security_check_cookie
0x180039878  mov     rbx, [rsp+58h+arg_10]
0x18003987d  mov     rsi, [rsp+58h+arg_18]
0x180039882  add     rsp, 40h
0x180039886  pop     r15
0x180039888  pop     r12
0x18003988a  pop     rdi
0x18003988b  retn
```
