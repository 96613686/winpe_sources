# ProvisioningTask::StopDownloadThread(long &)

- ea: `0x180037890`
- end: `0x180037a0c`
- name: `?StopDownloadThread@ProvisioningTask@@AEAAJAEAJ@Z`
- size: `380`
- prototype: `HRESULT __fastcall(ProvisioningTask *this, HRESULT *ReturnCode)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800377a0`

## callees

- `0x180002790`
- `0x180012748`
- `0x180012770`
- `0x180037890`
- `0x1800677d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180037988`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180037988`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037992`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037992`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180037938`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180037938`

## pseudocode

```c
__int64 __fastcall ProvisioningTask::StopDownloadThread(ProvisioningTask *this, HRESULT *ReturnCode)
{
  WPP_PROJECT_CONTROL_BLOCK *v4; // rcx
  HRESULT v5; // ebx
  unsigned int handleIndex; // [rsp+30h] [rbp-28h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x2Cu, WPP_0ed40dcb6852371d76e9e4c46355112e_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( this->m_taskThread )
  {
    if ( v4 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v4->ReserveSpace[28] & 0x10) != 0 )
      WPP_SF_(v4->Control.Logger, 0x2Du, WPP_0ed40dcb6852371d76e9e4c46355112e_Traceguids);
    handleIndex = 0;
    v5 = CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, &this->m_taskThread, &handleIndex);
    if ( v5 >= 0 && handleIndex )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x2Eu, WPP_0ed40dcb6852371d76e9e4c46355112e_Traceguids, v5);
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
    WPP_SF_(v4->Control.Logger, 0x2Fu, WPP_0ed40dcb6852371d76e9e4c46355112e_Traceguids);
LABEL_19:
    v4 = WPP_GLOBAL_Control;
  }
LABEL_20:
  if ( v4 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v4->ReserveSpace[28] & 0x10) != 0 )
    WPP_SF_d(v4->Control.Logger, 0x30u, WPP_0ed40dcb6852371d76e9e4c46355112e_Traceguids, v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180037890  mov     [rsp+arg_10], rbx
0x180037895  mov     [rsp+arg_18], rsi
0x18003789a  push    rdi
0x18003789b  push    r12
0x18003789d  push    r15
0x18003789f  sub     rsp, 40h
0x1800378a3  mov     rax, cs:__security_cookie
0x1800378aa  xor     rax, rsp
0x1800378ad  mov     [rsp+58h+var_20], rax
0x1800378b2  mov     rsi, ReturnCode
0x1800378b5  mov     rdi, this
0x1800378b8  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800378bf  lea     r15, WPP_GLOBAL_Control
0x1800378c6  lea     r12, WPP_0ed40dcb6852371d76e9e4c46355112e_Traceguids
0x1800378cd  cmp     this, r15
0x1800378d0  jz      short loc_1800378F0
0x1800378d2  test    byte ptr [this+1Ch], 10h
0x1800378d6  jz      short loc_1800378F0
0x1800378d8  mov     this, [this+10h]; Logger
0x1800378dc  mov     edx, 2Ch ; ','; id
0x1800378e1  mov     r8, r12; TraceGuid
0x1800378e4  call    WPP_SF_
0x1800378e9  mov     this, cs:WPP_GLOBAL_Control
0x1800378f0  cmp     qword ptr [rdi+40h], 0
0x1800378f5  jz      loc_1800379A2
0x1800378fb  cmp     this, r15; __annotation("TMF:",
0x1800378fe  jz      short loc_180037917
0x180037900  test    byte ptr [this+1Ch], 10h
0x180037904  jz      short loc_180037917
0x180037906  mov     this, [this+10h]; Logger
0x18003790a  mov     edx, 2Dh ; '-'; id
0x18003790f  mov     r8, r12; TraceGuid
0x180037912  call    WPP_SF_
0x180037917  lea     rax, [rsp+58h+handleIndex]
0x18003791c  mov     [rsp+58h+handleIndex], 0
0x180037924  lea     r9, [rdi+40h]; pHandles
0x180037928  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x18003792d  mov     r8d, 1; cHandles
0x180037933  or      edx, 0FFFFFFFFh; dwTimeout
0x180037936  xor     ecx, ecx; dwFlags
0x180037938  call    cs:__imp_CoWaitForMultipleHandles
0x18003793e  mov     ebx, eax
0x180037940  test    eax, eax
0x180037942  js      short loc_180037950
0x180037944  cmp     [rsp+58h+handleIndex], 0
0x180037949  jz      short loc_180037950
0x18003794b  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "FAILED(hr) || handleIndex == 0")
0x180037950  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180037957  cmp     this, r15
0x18003795a  jz      short loc_18003797D
0x18003795c  test    byte ptr [this+1Ch], 10h
0x180037960  jz      short loc_18003797D
0x180037962  mov     this, [this+10h]; Logger
0x180037966  mov     edx, 2Eh ; '.'; id
0x18003796b  mov     r9d, ebx; _a1
0x18003796e  mov     r8, r12; TraceGuid
0x180037971  call    WPP_SF_d
0x180037976  mov     this, cs:WPP_GLOBAL_Control
0x18003797d  test    ebx, ebx
0x18003797f  js      short loc_1800379CA
0x180037981  mov     this, [rdi+40h]; hThread
0x180037985  mov     ReturnCode, rsi; lpExitCode
0x180037988  call    cs:__imp_GetExitCodeThread
0x18003798e  mov     this, [rdi+40h]; hObject
0x180037992  call    cs:__imp_CloseHandle
0x180037998  mov     qword ptr [rdi+40h], 0
0x1800379a0  jmp     short loc_1800379C3
0x1800379a2  mov     ebx, 8004130Bh
0x1800379a7  cmp     this, r15; __annotation("TMF:",
0x1800379aa  jz      short loc_1800379E9
0x1800379ac  test    byte ptr [this+1Ch], 10h
0x1800379b0  jz      short loc_1800379CA
0x1800379b2  mov     this, [this+10h]; Logger
0x1800379b6  mov     edx, 2Fh ; '/'; id
0x1800379bb  mov     r8, r12; TraceGuid
0x1800379be  call    WPP_SF_
0x1800379c3  mov     this, cs:WPP_GLOBAL_Control
0x1800379ca  cmp     this, r15; __annotation("TMF:",
0x1800379cd  jz      short loc_1800379E9
0x1800379cf  test    byte ptr [this+1Ch], 10h
0x1800379d3  jz      short loc_1800379E9
0x1800379d5  mov     this, [this+10h]; Logger
0x1800379d9  mov     edx, 30h ; '0'; id
0x1800379de  mov     r9d, ebx; _a1
0x1800379e1  mov     r8, r12; TraceGuid
0x1800379e4  call    WPP_SF_d
0x1800379e9  mov     eax, ebx
0x1800379eb  mov     this, [rsp+58h+var_20]
0x1800379f0  xor     this, rsp; StackCookie
0x1800379f3  call    __security_check_cookie
0x1800379f8  mov     rbx, [rsp+58h+arg_10]
0x1800379fd  mov     rsi, [rsp+58h+arg_18]
0x180037a02  add     rsp, 40h
0x180037a06  pop     r15
0x180037a08  pop     r12
0x180037a0a  pop     rdi
0x180037a0b  retn
```
