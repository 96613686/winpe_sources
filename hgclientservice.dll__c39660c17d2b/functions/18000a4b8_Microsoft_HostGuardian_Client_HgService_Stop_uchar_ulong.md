# Microsoft::HostGuardian::Client::HgService::Stop(uchar,ulong)

- ea: `0x18000a4b8`
- end: `0x18000a69c`
- name: `?Stop@HgService@Client@HostGuardian@Microsoft@@QEAAXEK@Z`
- size: `484`
- prototype: `void __fastcall(wil::details::in1diag3 **this, __int64, __int64)`
- caller_count: `3`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009ca0`
- `0x180009f30`
- `0x1800156f5`

## callees

- `0x180001770`
- `0x18000734c`
- `0x1800077a0`
- `0x180008760`
- `0x180009fc8`
- `0x18000a4b8`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a5ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a5ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a619`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a5ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a5ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a619`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a598`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a5c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a606`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a598`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a5c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a606`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000a52c`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000a52c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5d1`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x18000a5a3`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x18000a5a3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18000a611`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18000a611`

## string_xrefs

- `0x18000a67f`: `servercommon\base\securehostingservice\common\service\lib\hgservice.cpp`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::HgService::Stop(wil::details::in1diag3 **this, __int64 a2, __int64 a3)
{
  int v3; // r15d
  REGHANDLE v5; // rcx
  __int64 v6; // r8
  wil::details::in1diag3 *v7; // rcx
  int v8; // eax
  wil::details::in1diag3 *v9; // r14
  DWORD LastError; // ebx
  wil::details::in1diag3 *v11; // rbx
  DWORD v12; // r14d
  __int64 v13; // r8
  const char *v14; // r9
  wil::details::in1diag3 *v15; // r14
  DWORD v16; // ebx
  const char *v17; // r9
  _QWORD v18[4]; // [rsp+40h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v3 = a3;
  if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 2) != 0 )
  {
    v18[2] = L"Unregistering HGS quality provider";
    v18[3] = 70;
    McGenEventWrite_EventWriteTransfer(this, ServiceDebugInformational, a3, 2, v18);
  }
  v5 = RegHandle;
  dword_180020048 = 0;
  RegHandle = 0;
  EventUnregister(v5);
  try
  {
    v7 = this[23];
    if ( v7 )
    {
      v18[0] = 0;
      v18[1] = this;
      v8 = (*(__int64 (__fastcall **)(wil::details::in1diag3 *, __int64 (__fastcall *)(), _QWORD *, GUID *))(*(_QWORD *)v7 + 24LL))(
             v7,
             lambda_454cee33be369b2b1b95f88549ed974a_::_lambda_invoker_cdecl_,
             v18,
             &IID_IContextCallback);
      v7 = retaddr;
      if ( v8 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x113,
          (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservice.cpp",
          (const char *)(unsigned int)v8,
          5);
    }
    v9 = this[22];
    if ( v9 )
    {
      LastError = GetLastError();
      CoDecrementMTAUsage(v9);
      SetLastError(LastError);
      this[22] = 0;
    }
    v11 = this[11];
    if ( v11 )
    {
      v12 = GetLastError();
      if ( !CloseHandle(v11) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
      SetLastError(v12);
    }
    this[11] = 0;
    v15 = this[10];
    if ( (unsigned __int64)v15 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v16 = GetLastError();
      UnregisterWait(v15);
      SetLastError(v16);
    }
    this[10] = 0;
    this[9] = 0;
    if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(v7, ServiceStop, v6, 1, v18);
    *((_DWORD *)this + 13) = v3;
    Microsoft::HostGuardian::Client::HgService::SetStatus((Microsoft::HostGuardian::Client::HgService *)this, 1);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xCA,
      (int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservice.cpp",
      v17);
  }
}

```

## disassembly

```asm
0x18000a4b8  mov     r11, rsp
0x18000a4bb  push    rbx
0x18000a4bc  push    rsi
0x18000a4bd  push    r14
0x18000a4bf  push    r15
0x18000a4c1  sub     rsp, 78h
0x18000a4c5  mov     rax, cs:__security_cookie
0x18000a4cc  xor     rax, rsp
0x18000a4cf  mov     [rsp+98h+var_38], rax
0x18000a4d4  mov     r15d, r8d
0x18000a4d7  mov     rsi, rcx
0x18000a4da  mov     r9d, 2
0x18000a4e0  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, r9b
0x18000a4e7  jz      short loc_18000A510
0x18000a4e9  lea     rax, aUnregisteringH; "Unregistering HGS quality provider"
0x18000a4f0  mov     [r11-48h], rax
0x18000a4f4  mov     qword ptr [r11-40h], 46h ; 'F'
0x18000a4fc  lea     rax, [r11-58h]
0x18000a500  mov     [r11-78h], rax
0x18000a504  lea     rdx, ServiceDebugInformational
0x18000a50b  call    McGenEventWrite_EventWriteTransfer
0x18000a510  mov     rcx, cs:RegHandle; RegHandle
0x18000a517  mov     cs:dword_180020048, 0
0x18000a521  mov     cs:RegHandle, 0
0x18000a52c  call    cs:__imp_EventUnregister
0x18000a532  mov     rcx, [rsi+0B8h]
0x18000a539  test    rcx, rcx
0x18000a53c  jz      short loc_18000A58C
0x18000a53e  mov     [rsp+98h+var_58], 0
0x18000a547  mov     [rsp+98h+var_50], rsi
0x18000a54c  mov     rax, [rcx]
0x18000a54f  mov     [rsp+98h+var_70], 0
0x18000a558  mov     [rsp+98h+var_78], 5; int
0x18000a560  lea     r9, IID_IContextCallback
0x18000a567  lea     r8, [rsp+98h+var_58]
0x18000a56c  lea     rdx, _lambda_454cee33be369b2b1b95f88549ed974a____lambda_invoker_cdecl_
0x18000a573  mov     rax, [rax+18h]
0x18000a577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a57c  mov     rcx, [rsp+98h]; this
0x18000a584  test    eax, eax
0x18000a586  js      loc_18000A67C
0x18000a58c  mov     r14, [rsi+0B0h]
0x18000a593  test    r14, r14
0x18000a596  jz      short loc_18000A5BC
0x18000a598  call    cs:__imp_GetLastError
0x18000a59e  mov     ebx, eax
0x18000a5a0  mov     rcx, r14
0x18000a5a3  call    cs:__imp_CoDecrementMTAUsage
0x18000a5a9  mov     ecx, ebx; dwErrCode
0x18000a5ab  call    cs:__imp_SetLastError
0x18000a5b1  mov     qword ptr [rsi+0B0h], 0
0x18000a5bc  mov     rbx, [rsi+58h]
0x18000a5c0  test    rbx, rbx
0x18000a5c3  jz      short loc_18000A5F0
0x18000a5c5  call    cs:__imp_GetLastError
0x18000a5cb  mov     r14d, eax
0x18000a5ce  mov     rcx, rbx; hObject
0x18000a5d1  call    cs:__imp_CloseHandle
0x18000a5d7  mov     rcx, [rsp+98h]; this
0x18000a5df  test    eax, eax
0x18000a5e1  jz      loc_18000A690
0x18000a5e7  mov     ecx, r14d; dwErrCode
0x18000a5ea  call    cs:__imp_SetLastError
0x18000a5f0  mov     qword ptr [rsi+58h], 0
0x18000a5f8  mov     r14, [rsi+50h]
0x18000a5fc  lea     rax, [r14-1]
0x18000a600  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a604  ja      short loc_18000A61F
0x18000a606  call    cs:__imp_GetLastError
0x18000a60c  mov     ebx, eax
0x18000a60e  mov     rcx, r14; WaitHandle
0x18000a611  call    cs:__imp_UnregisterWait
0x18000a617  mov     ecx, ebx; dwErrCode
0x18000a619  call    cs:__imp_SetLastError
0x18000a61f  mov     qword ptr [rsi+50h], 0
0x18000a627  mov     qword ptr [rsi+48h], 0
0x18000a62f  mov     ebx, 1
0x18000a634  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, bl
0x18000a63a  jz      short loc_18000A655
0x18000a63c  lea     rax, [rsp+98h+var_58]
0x18000a641  mov     qword ptr [rsp+98h+var_78], rax
0x18000a646  mov     r9d, ebx
0x18000a649  lea     rdx, ServiceStop
0x18000a650  call    McGenEventWrite_EventWriteTransfer
0x18000a655  mov     [rsi+34h], r15d
0x18000a659  mov     edx, ebx; unsigned int
0x18000a65b  mov     rcx, rsi; this
0x18000a65e  call    ?SetStatus@HgService@Client@HostGuardian@Microsoft@@IEAAXK@Z; Microsoft::HostGuardian::Client::HgService::SetStatus(ulong)
0x18000a663  nop
0x18000a664  mov     rcx, [rsp+98h+var_38]
0x18000a669  xor     rcx, rsp; StackCookie
0x18000a66c  call    __security_check_cookie
0x18000a671  add     rsp, 78h
0x18000a675  pop     r15
0x18000a677  pop     r14
0x18000a679  pop     rsi
0x18000a67a  pop     rbx
0x18000a67b  retn
0x18000a67c  mov     r9d, eax; char *
0x18000a67f  lea     r8, aServercommonBa_0; "servercommon\\base\\securehostingservic"...
0x18000a686  mov     edx, 113h; void *
0x18000a68b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000a690  mov     edx, 0A0Bh; void *
0x18000a695  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
