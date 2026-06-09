# ActivationTask::StopActivationThread(long &)

- ea: `0x180019b70`
- end: `0x180019cfc`
- name: `?StopActivationThread@ActivationTask@@AEAAJAEAJ@Z`
- size: `396`
- prototype: `HRESULT __fastcall(ActivationTask *this, HRESULT *ReturnCode)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019a80`

## callees

- `0x180002790`
- `0x180012748`
- `0x180012770`
- `0x180019b70`
- `0x1800677d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180019be2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180019be2`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180019c7a`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180019c7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019c83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019c83`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180019c2b`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180019c2b`

## pseudocode

```c
__int64 __fastcall ActivationTask::StopActivationThread(ActivationTask *this, HRESULT *ReturnCode)
{
  WPP_PROJECT_CONTROL_BLOCK *v4; // rcx
  void **p_m_taskThread; // rdi
  HRESULT v6; // ebx
  unsigned int handleIndex; // [rsp+30h] [rbp-28h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x3Au, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  p_m_taskThread = &this->m_taskThread;
  if ( this->m_taskThread )
  {
    SetEvent(this->m_cancelEvent);
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x3Bu, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids);
    }
    handleIndex = 0;
    v6 = CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, &this->m_taskThread, &handleIndex);
    if ( v6 >= 0 && handleIndex )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x3Cu, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids, v6);
      v4 = WPP_GLOBAL_Control;
    }
    if ( v6 < 0 )
      goto LABEL_20;
    GetExitCodeThread(*p_m_taskThread, (LPDWORD)ReturnCode);
    CloseHandle(*p_m_taskThread);
    *p_m_taskThread = 0;
    goto LABEL_19;
  }
  v6 = -2147216629;
  if ( v4 == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    return (unsigned int)v6;
  if ( (v4->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(v4->Control.Logger, 0x3Du, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids);
LABEL_19:
    v4 = WPP_GLOBAL_Control;
  }
LABEL_20:
  if ( v4 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v4->ReserveSpace[28] & 0x10) != 0 )
    WPP_SF_d(v4->Control.Logger, 0x3Eu, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids, v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180019b70  mov     [rsp+arg_10], rbx
0x180019b75  mov     [rsp+arg_18], rsi
0x180019b7a  push    rdi
0x180019b7b  push    r12
0x180019b7d  push    r15
0x180019b7f  sub     rsp, 40h
0x180019b83  mov     rax, cs:__security_cookie
0x180019b8a  xor     rax, rsp
0x180019b8d  mov     [rsp+58h+var_20], rax
0x180019b92  mov     rsi, ReturnCode
0x180019b95  mov     rbx, this
0x180019b98  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180019b9f  lea     r15, WPP_GLOBAL_Control
0x180019ba6  lea     r12, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids
0x180019bad  cmp     this, r15
0x180019bb0  jz      short loc_180019BD0
0x180019bb2  test    byte ptr [this+1Ch], 10h
0x180019bb6  jz      short loc_180019BD0
0x180019bb8  mov     this, [this+10h]; Logger
0x180019bbc  mov     edx, 3Ah ; ':'; id
0x180019bc1  mov     r8, r12; TraceGuid
0x180019bc4  call    WPP_SF_
0x180019bc9  mov     this, cs:WPP_GLOBAL_Control
0x180019bd0  lea     rdi, [rbx+48h]
0x180019bd4  cmp     qword ptr [rdi], 0
0x180019bd8  jz      loc_180019C92
0x180019bde  mov     this, [rbx+40h]; hEvent
0x180019be2  call    cs:__imp_SetEvent
0x180019be8  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180019bef  cmp     this, r15
0x180019bf2  jz      short loc_180019C0B
0x180019bf4  test    byte ptr [this+1Ch], 10h
0x180019bf8  jz      short loc_180019C0B
0x180019bfa  mov     this, [this+10h]; Logger
0x180019bfe  mov     edx, 3Bh ; ';'; id
0x180019c03  mov     r8, r12; TraceGuid
0x180019c06  call    WPP_SF_
0x180019c0b  lea     rax, [rsp+58h+handleIndex]
0x180019c10  mov     [rsp+58h+handleIndex], 0
0x180019c18  mov     r9, rdi; pHandles
0x180019c1b  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x180019c20  mov     r8d, 1; cHandles
0x180019c26  or      edx, 0FFFFFFFFh; dwTimeout
0x180019c29  xor     ecx, ecx; dwFlags
0x180019c2b  call    cs:__imp_CoWaitForMultipleHandles
0x180019c31  mov     ebx, eax
0x180019c33  test    eax, eax
0x180019c35  js      short loc_180019C43
0x180019c37  cmp     [rsp+58h+handleIndex], 0
0x180019c3c  jz      short loc_180019C43
0x180019c3e  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "FAILED(hr) || handleIndex == 0")
0x180019c43  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180019c4a  cmp     this, r15
0x180019c4d  jz      short loc_180019C70
0x180019c4f  test    byte ptr [this+1Ch], 10h
0x180019c53  jz      short loc_180019C70
0x180019c55  mov     this, [this+10h]; Logger
0x180019c59  mov     edx, 3Ch ; '<'; id
0x180019c5e  mov     r9d, ebx; _a1
0x180019c61  mov     r8, r12; TraceGuid
0x180019c64  call    WPP_SF_d
0x180019c69  mov     this, cs:WPP_GLOBAL_Control
0x180019c70  test    ebx, ebx
0x180019c72  js      short loc_180019CBA
0x180019c74  mov     this, [rdi]; hThread
0x180019c77  mov     ReturnCode, rsi; lpExitCode
0x180019c7a  call    cs:__imp_GetExitCodeThread
0x180019c80  mov     this, [rdi]; hObject
0x180019c83  call    cs:__imp_CloseHandle
0x180019c89  mov     qword ptr [rdi], 0
0x180019c90  jmp     short loc_180019CB3
0x180019c92  mov     ebx, 8004130Bh
0x180019c97  cmp     this, r15; __annotation("TMF:",
0x180019c9a  jz      short loc_180019CD9
0x180019c9c  test    byte ptr [this+1Ch], 10h
0x180019ca0  jz      short loc_180019CBA
0x180019ca2  mov     this, [this+10h]; Logger
0x180019ca6  mov     edx, 3Dh ; '='; id
0x180019cab  mov     r8, r12; TraceGuid
0x180019cae  call    WPP_SF_
0x180019cb3  mov     this, cs:WPP_GLOBAL_Control
0x180019cba  cmp     this, r15; __annotation("TMF:",
0x180019cbd  jz      short loc_180019CD9
0x180019cbf  test    byte ptr [this+1Ch], 10h
0x180019cc3  jz      short loc_180019CD9
0x180019cc5  mov     this, [this+10h]; Logger
0x180019cc9  mov     edx, 3Eh ; '>'; id
0x180019cce  mov     r9d, ebx; _a1
0x180019cd1  mov     r8, r12; TraceGuid
0x180019cd4  call    WPP_SF_d
0x180019cd9  mov     eax, ebx
0x180019cdb  mov     this, [rsp+58h+var_20]
0x180019ce0  xor     this, rsp; StackCookie
0x180019ce3  call    __security_check_cookie
0x180019ce8  mov     rbx, [rsp+58h+arg_10]
0x180019ced  mov     rsi, [rsp+58h+arg_18]
0x180019cf2  add     rsp, 40h
0x180019cf6  pop     r15
0x180019cf8  pop     r12
0x180019cfa  pop     rdi
0x180019cfb  retn
```
