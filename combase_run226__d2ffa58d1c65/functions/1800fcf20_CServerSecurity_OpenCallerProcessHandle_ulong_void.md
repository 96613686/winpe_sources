# CServerSecurity::OpenCallerProcessHandle(ulong,void * *)

- ea: `0x1800fcf20`
- end: `0x1800fd148`
- name: `?OpenCallerProcessHandle@CServerSecurity@@UEAAJKPEAPEAX@Z`
- size: `552`
- prototype: `HRESULT __fastcall(CServerSecurity *this, unsigned int desiredAccess, void **callerProcessHandle)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000712c`
- `0x180063660`
- `0x1800865f4`
- `0x180086714`
- `0x18008db2c`
- `0x1800fcf20`
- `0x1801999b0`

## import_xrefs

- `RPCRT4!I_RpcOpenClientProcess` at `0x1800fd074`
- `RPCRT4!I_RpcOpenClientProcess` at `0x1800fd074`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fd058`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fd058`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800fd036`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800fd036`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800fd009`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800fd009`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800fd043`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800fd043`
- `api-ms-win-core-processthreads-l1-1-1!GetProcessHandleCount` at `0x1800fd017`
- `api-ms-win-core-processthreads-l1-1-1!GetProcessHandleCount` at `0x1800fd017`

## string_xrefs

- `0x1800fcfaf`: `onecore\com\combase\dcomrem\security.cxx`
- `0x1800fd10a`: `onecore\com\combase\dcomrem\security.cxx`
- `0x1800fcfa2`: `CServerSecurity::OpenCallerProcessHandle`
- `0x1800fd0ff`: `CServerSecurity::OpenCallerProcessHandle`
- `0x1800fcfce`: `Opening caller process handle for inproc call, iid=%ls, procnum=%d`

## pseudocode

```c
__int64 __fastcall CServerSecurity::OpenCallerProcessHandle(
        CServerSecurity *this,
        unsigned int desiredAccess,
        void **callerProcessHandle)
{
  __int64 v6; // rax
  HANDLE CurrentProcess; // rax
  __int64 v8; // rcx
  DWORD CurrentProcessId; // eax
  HANDLE v10; // rax
  unsigned int v11; // ebx
  signed int LastError; // eax
  RPC_STATUS v13; // ebx
  ICallLocalityInfo_vtbl *v14; // rcx
  RPC_STATUS v15; // eax
  int v16; // edx
  wchar_t *format; // [rsp+28h] [rbp-B0h]
  __int64 v19; // [rsp+30h] [rbp-A8h]
  unsigned int currentProcessHandleCount; // [rsp+40h] [rbp-98h] BYREF
  _GUID guid; // [rsp+48h] [rbp-90h] BYREF
  GuidString iidString; // [rsp+60h] [rbp-78h] BYREF

  *callerProcessHandle = 0;
  if ( LODWORD(this->_hSaved) )
  {
    v14 = this->ICallLocalityInfo::IUnknown::__vftable;
    if ( !v14 )
    {
      v11 = -2147417833;
      goto LABEL_27;
    }
    v11 = 0;
    v15 = I_RpcOpenClientProcess(v14, desiredAccess, callerProcessHandle);
    if ( !v15 )
      goto LABEL_31;
    v13 = v15;
    goto LABEL_19;
  }
  v6 = *(_QWORD *)&this->_iRefCount;
  if ( v6 )
  {
    guid = *(_GUID *)(v6 + 120);
    GuidString::GuidString(&iidString, &guid);
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(WARNING) )
      ComTraceMessage(
        -1,
        "onecore\\com\\combase\\dcomrem\\security.cxx",
        "CServerSecurity::OpenCallerProcessHandle",
        4654,
        WARNING,
        L"Opening caller process handle for inproc call, iid=%ls, procnum=%d",
        &iidString,
        *(unsigned __int16 *)(*(_QWORD *)&this->_iRefCount + 140LL));
  }
  if ( ++openCallerProcessHandleInprocCallCount >= 0xC350 && !alreadyReportedSuspiciouslyLargeHandleCount )
  {
    currentProcessHandleCount = 0;
    CurrentProcess = GetCurrentProcess();
    if ( GetProcessHandleCount(CurrentProcess, &currentProcessHandleCount) )
    {
      if ( currentProcessHandleCount >= 0xC350 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v8);
        alreadyReportedSuspiciouslyLargeHandleCount = 1;
      }
    }
  }
  CurrentProcessId = GetCurrentProcessId();
  v10 = OpenProcess(desiredAccess, 0, CurrentProcessId);
  *callerProcessHandle = v10;
  if ( !v10 )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError <= 0 )
    {
LABEL_20:
      v16 = -2147024891;
      if ( v11 == -2147024891 )
      {
        if ( !gfEnableTracing )
          return v11;
        if ( IsWppLevelEnabled(VERBOSE) )
        {
LABEL_33:
          LODWORD(v19) = HIDWORD(this->ICallingProcessInfo::IUnknown::__vftable);
          LODWORD(format) = v11;
          ComTraceHr(
            v11,
            "onecore\\com\\combase\\dcomrem\\security.cxx",
            "CServerSecurity::OpenCallerProcessHandle",
            4702,
            L"%!HRESULT! Flags:%d",
            format,
            v19);
          return v11;
        }
      }
      if ( (v11 & 0x80000000) == 0 )
        goto LABEL_31;
      if ( v11 == v16 )
        return v11;
LABEL_27:
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
        goto LABEL_33;
      return v11;
    }
    v13 = (unsigned __int16)LastError;
LABEL_19:
    v11 = v13 | 0x80070000;
    goto LABEL_20;
  }
  v11 = 0;
LABEL_31:
  if ( gfEnableTracing && IsWppLevelEnabled(VERBOSE) )
    goto LABEL_33;
  return v11;
}

```

## disassembly

```asm
0x1800fcf20  mov     [rsp+arg_18], rbx
0x1800fcf25  push    rbp
0x1800fcf26  push    rsi
0x1800fcf27  push    rdi
0x1800fcf28  sub     rsp, 0C0h
0x1800fcf2f  mov     rax, cs:__security_cookie
0x1800fcf36  xor     rax, rsp
0x1800fcf39  mov     [rsp+0D8h+var_28], rax
0x1800fcf41  mov     qword ptr [callerProcessHandle], 0
0x1800fcf48  mov     rsi, callerProcessHandle
0x1800fcf4b  cmp     dword ptr [this+50h], 0
0x1800fcf4f  mov     ebp, desiredAccess
0x1800fcf51  mov     rdi, this
0x1800fcf54  jnz     loc_1800FD069
0x1800fcf5a  mov     rax, [this+30h]
0x1800fcf5e  mov     ebx, 1
0x1800fcf63  test    rax, rax
0x1800fcf66  jz      short loc_1800FCFE3
0x1800fcf68  movups  xmm0, xmmword ptr [rax+78h]
0x1800fcf6c  lea     rdx, [rsp+0D8h+guid]; guid
0x1800fcf71  lea     this, [rsp+0D8h+iidString]; this
0x1800fcf76  movdqu  xmmword ptr [rsp+0D8h+guid.Data1], xmm0
0x1800fcf7c  call    ??0GuidString@@QEAA@AEBU_GUID@@@Z; GuidString::GuidString(_GUID const &)
0x1800fcf81  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x1800fcf87  test    eax, eax
0x1800fcf89  jnz     short loc_1800FCF9E
0x1800fcf8b  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800fcf91  jz      short loc_1800FCFE3
0x1800fcf93  mov     ecx, ebx; level
0x1800fcf95  call    IsWppLevelEnabled
0x1800fcf9a  test    al, al
0x1800fcf9c  jz      short loc_1800FCFE3
0x1800fcf9e  mov     rax, [rdi+30h]
0x1800fcfa2  lea     callerProcessHandle, aCserversecurit_0; "CServerSecurity::OpenCallerProcessHandl"...
0x1800fcfa9  mov     r9d, 122Eh; line
0x1800fcfaf  lea     rdx, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x1800fcfb6  movzx   ecx, word ptr [rax+8Ch]
0x1800fcfbd  lea     rax, [rsp+0D8h+iidString]
0x1800fcfc2  mov     [rsp+0D8h+var_A0], ecx
0x1800fcfc6  or      ecx, 0FFFFFFFFh; hr
0x1800fcfc9  mov     [rsp+0D8h+var_A8], rax
0x1800fcfce  lea     rax, aOpeningCallerP; "Opening caller process handle for inpro"...
0x1800fcfd5  mov     [rsp+0D8h+format], rax; format
0x1800fcfda  mov     [rsp+0D8h+level], ebx; level
0x1800fcfde  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x1800fcfe3  mov     eax, cs:openCallerProcessHandleInprocCallCount
0x1800fcfe9  add     eax, ebx
0x1800fcfeb  mov     cs:openCallerProcessHandleInprocCallCount, eax
0x1800fcff1  cmp     eax, 0C350h
0x1800fcff6  jb      short loc_1800FD036
0x1800fcff8  cmp     cs:alreadyReportedSuspiciouslyLargeHandleCount, 0
0x1800fcfff  jnz     short loc_1800FD036
0x1800fd001  mov     [rsp+0D8h+currentProcessHandleCount], 0
0x1800fd009  call    cs:__imp_GetCurrentProcess
0x1800fd00f  mov     this, rax; hProcess
0x1800fd012  lea     rdx, [rsp+0D8h+currentProcessHandleCount]; pdwHandleCount
0x1800fd017  call    cs:__imp_GetProcessHandleCount
0x1800fd01d  test    eax, eax
0x1800fd01f  jz      short loc_1800FD036
0x1800fd021  cmp     [rsp+0D8h+currentProcessHandleCount], 0C350h
0x1800fd029  jb      short loc_1800FD036
0x1800fd02b  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "currentProcessHandleCount < suspiciouslyLargeHandleCount")
0x1800fd030  mov     cs:alreadyReportedSuspiciouslyLargeHandleCount, bl
0x1800fd036  call    cs:__imp_GetCurrentProcessId
0x1800fd03c  xor     desiredAccess, desiredAccess; bInheritHandle
0x1800fd03e  mov     ecx, ebp; dwDesiredAccess
0x1800fd040  mov     r8d, eax; dwProcessId
0x1800fd043  call    cs:__imp_OpenProcess
0x1800fd049  mov     [rsi], rax
0x1800fd04c  test    rax, rax
0x1800fd04f  jz      short loc_1800FD058
0x1800fd051  xor     ebx, ebx
0x1800fd053  jmp     loc_1800FD0DA
0x1800fd058  call    cs:__imp_GetLastError
0x1800fd05e  mov     ebx, eax
0x1800fd060  test    eax, eax
0x1800fd062  jle     short loc_1800FD086
0x1800fd064  movzx   ebx, ax
0x1800fd067  jmp     short loc_1800FD080
0x1800fd069  mov     this, [this+28h]; Binding
0x1800fd06d  test    this, this
0x1800fd070  jz      short loc_1800FD0B4
0x1800fd072  xor     ebx, ebx
0x1800fd074  call    cs:__imp_I_RpcOpenClientProcess
0x1800fd07a  test    eax, eax
0x1800fd07c  jz      short loc_1800FD0DA
0x1800fd07e  mov     ebx, eax
0x1800fd080  or      ebx, 80070000h
0x1800fd086  mov     desiredAccess, 80070005h
0x1800fd08b  cmp     ebx, desiredAccess
0x1800fd08d  jnz     short loc_1800FD0AA
0x1800fd08f  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x1800fd096  jz      loc_1800FD123
0x1800fd09c  mov     ecx, 3; level
0x1800fd0a1  call    IsWppLevelEnabled
0x1800fd0a6  test    al, al
0x1800fd0a8  jnz     short loc_1800FD0F1
0x1800fd0aa  test    ebx, ebx
0x1800fd0ac  jns     short loc_1800FD0DA
0x1800fd0ae  cmp     ebx, desiredAccess
0x1800fd0b0  jz      short loc_1800FD123
0x1800fd0b2  jmp     short loc_1800FD0B9
0x1800fd0b4  mov     ebx, 80010117h
0x1800fd0b9  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x1800fd0bf  test    eax, eax
0x1800fd0c1  jnz     short loc_1800FD0F1
0x1800fd0c3  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800fd0c9  jz      short loc_1800FD0D6
0x1800fd0cb  xor     ecx, ecx; level
0x1800fd0cd  call    IsWppLevelEnabled
0x1800fd0d2  test    al, al
0x1800fd0d4  jnz     short loc_1800FD0F1
0x1800fd0d6  test    ebx, ebx
0x1800fd0d8  js      short loc_1800FD123
0x1800fd0da  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x1800fd0e1  jz      short loc_1800FD123
0x1800fd0e3  mov     ecx, 3; level
0x1800fd0e8  call    IsWppLevelEnabled
0x1800fd0ed  test    al, al
0x1800fd0ef  jz      short loc_1800FD123
0x1800fd0f1  mov     ecx, [rdi+1Ch]
0x1800fd0f4  lea     rax, aHresultFlagsD; "%!HRESULT! Flags:%d"
0x1800fd0fb  mov     dword ptr [rsp+0D8h+var_A8], ecx
0x1800fd0ff  lea     callerProcessHandle, aCserversecurit_0; "CServerSecurity::OpenCallerProcessHandl"...
0x1800fd106  mov     dword ptr [rsp+0D8h+format], ebx
0x1800fd10a  lea     rdx, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x1800fd111  mov     ecx, ebx; hr
0x1800fd113  mov     qword ptr [rsp+0D8h+level], rax; format
0x1800fd118  mov     r9d, 125Eh; line
0x1800fd11e  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x1800fd123  mov     eax, ebx
0x1800fd125  mov     this, [rsp+0D8h+var_28]
0x1800fd12d  xor     this, rsp; StackCookie
0x1800fd130  call    __security_check_cookie
0x1800fd135  mov     rbx, [rsp+0D8h+arg_18]
0x1800fd13d  add     rsp, 0C0h
0x1800fd144  pop     rdi
0x1800fd145  pop     rsi
0x1800fd146  pop     rbp
0x1800fd147  retn
```
