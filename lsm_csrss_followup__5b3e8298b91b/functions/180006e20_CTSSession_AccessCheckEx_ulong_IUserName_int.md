# CTSSession::AccessCheckEx(ulong,IUserName *,int)

- ea: `0x180006e20`
- end: `0x1800073fe`
- name: `?AccessCheckEx@CTSSession@@UEAAJKPEAUIUserName@@H@Z`
- size: `1502`
- prototype: `int(CTSSession *__hidden this, unsigned int, struct IUserName *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180006e10`

## callees

- `0x180006e20`
- `0x1800074c0`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000713c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007252`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007288`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800072f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000733e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007378`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000713c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007252`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007288`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800072f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000733e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007378`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073b9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800070f1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000712e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800070f1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000712e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006e80`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006f2b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006e80`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006f2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006e6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006f13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006e6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006f13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180007080`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180007080`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006ece`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006ede`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007108`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007118`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800071ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800071dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800072ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000736d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006ece`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006ede`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007108`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007118`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800071ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800071dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800072ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000736d`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800070ac`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800070ac`
- `RPCRT4!RpcImpersonateClient` at `0x180007318`
- `RPCRT4!RpcImpersonateClient` at `0x180007318`
- `RPCRT4!RpcRevertToSelf` at `0x180007157`
- `RPCRT4!RpcRevertToSelf` at `0x180007157`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000706a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000706a`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180006e55`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180006e55`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800070dd`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800070dd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006f55`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006f55`
- `api-ms-win-security-base-l1-1-0!AccessCheckAndAuditAlarmW` at `0x180006ffe`
- `api-ms-win-security-base-l1-1-0!AccessCheckAndAuditAlarmW` at `0x180006ffe`

## string_xrefs

- `0x1800072d3`: `AccessCheckAndAuditAlarm failed: %x.`
- `0x180007183`: `CTSSession::AccessCheckEx`
- `0x18000718d`: `GetOriginalToken failed: 0x%x in %s`
- `0x18000720a`: `CTSSessionSecurityDescriptor::IsSameSessionId`
- `0x180006eab`: `CTSSessionSecurityDescriptor::AccessCheck`
- `0x1800071f7`: `OpenProcess( %d ) : 0x%x`
- `0x180007353`: `SetThreadToken failed: 0x%x`
- `0x18000714e`: `SetThreadToken( NULL ) failed: 0x%x`
- `0x180007272`: `OpenThreadToken failed: 0x%x in %s`
- `0x1800073a3`: `GetTokenInformation failed: 0x%x in %s`
- `0x180007332`: `RpcImpersonateClient failed: 0x%x`
- `0x18000730a`: `OpenThreadToken failed with some other error: 0x%x`
- `0x18000701b`: `AccessCheck failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CTSSession::AccessCheckEx(CTSSession *this, DWORD a2, struct IUserName *a3, int a4)
{
  unsigned int v8; // ebx
  int v9; // edi
  int v10; // r13d
  HANDLE CurrentThread; // rax
  __int64 v12; // rax
  signed int v14; // r14d
  HANDLE v15; // rax
  const char *v16; // rdx
  int v17; // eax
  HANDLE v18; // rbx
  HANDLE CurrentProcess; // rax
  signed int v20; // eax
  unsigned int v21; // eax
  signed int v22; // eax
  signed int v23; // eax
  signed int v24; // eax
  signed int v25; // eax
  signed int LastError; // eax
  int v27; // eax
  bool v28; // sf
  signed int v29; // eax
  signed int v30; // eax
  signed int v31; // eax
  DWORD ReturnLength[2]; // [rsp+60h] [rbp-19h] BYREF
  HANDLE TargetHandle; // [rsp+68h] [rbp-11h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp-9h] BYREF
  HANDLE hSourceHandle; // [rsp+78h] [rbp-1h] BYREF
  void *TokenHandle; // [rsp+80h] [rbp+7h] BYREF
  DWORD TokenInformation; // [rsp+E0h] [rbp+67h] BYREF

  v8 = 0;
  TokenHandle = 0;
  hObject = 0;
  v9 = *((_DWORD *)this + 436);
  if ( v9 != (unsigned int)WTSGetServiceSessionId() || (a2 & 0xFFFFFCFF) != 0 )
  {
    if ( !a3 )
    {
      v10 = 0;
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
        goto LABEL_4;
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError != -2147023888 )
      {
        _DbgPrintMessage(8, "OpenThreadToken failed with some other error: 0x%x", (unsigned int)LastError);
LABEL_44:
        v8 = -2147024891;
        goto LABEL_10;
      }
      v27 = RpcImpersonateClient(0);
      v28 = v27 < 0;
      if ( v27 > 0 )
      {
        v27 = (unsigned __int16)v27 | 0x80070000;
        v28 = v27 < 0;
      }
      if ( v28 )
      {
        _DbgPrintMessage(8, "RpcImpersonateClient failed: 0x%x", (unsigned int)v27);
        goto LABEL_44;
      }
      v10 = 1;
LABEL_4:
      if ( a4 )
      {
        TargetHandle = 0;
        TokenInformation = 0;
        ReturnLength[0] = 0;
        v14 = 0;
        v15 = GetCurrentThread();
        if ( OpenThreadToken(v15, 8u, 1, &TargetHandle) )
          goto LABEL_77;
        v24 = GetLastError();
        v14 = v24;
        if ( v24 > 0 )
          v14 = (unsigned __int16)v24 | 0x80070000;
        if ( v14 >= 0 )
        {
LABEL_77:
          if ( GetTokenInformation(TargetHandle, TokenSessionId, &TokenInformation, 4u, ReturnLength) )
            goto LABEL_17;
          v30 = GetLastError();
          v14 = v30;
          if ( v30 > 0 )
            v14 = (unsigned __int16)v30 | 0x80070000;
          if ( v14 >= 0 )
LABEL_17:
            v8 = TokenInformation;
          else
            _DbgPrintMessage(8, "GetTokenInformation failed: 0x%x in %s", v14, "CUtils::GetUserSessionId");
        }
        else
        {
          _DbgPrintMessage(8, "OpenThreadToken failed: 0x%x in %s", v14, "CUtils::GetUserSessionId");
        }
        if ( TargetHandle )
          CloseHandle(TargetHandle);
        if ( v14 < 0 )
        {
          _DbgPrintMessage(
            8,
            "CUtils::GetUserSessionId() failed: 0x%x in %s",
            v14,
            "CTSSessionSecurityDescriptor::IsSameSessionId");
          v8 = -2147024891;
          _DbgPrintMessage(
            8,
            "IsSameSessionId failed: 0x%x in %s",
            (unsigned int)v14,
            "CTSSessionSecurityDescriptor::AccessCheck");
          goto LABEL_9;
        }
        if ( v8 == v9 )
        {
          if ( !*((_QWORD *)this + 736) )
          {
            v8 = -2147467259;
            v16 = "AppContainer SD is NOT initialized! failed: 0x%x in %s";
            goto LABEL_8;
          }
          v12 = 5888;
          v8 = 0;
LABEL_24:
          LODWORD(TargetHandle) = 0;
          TokenInformation = 0;
          ReturnLength[0] = 0;
          if ( AccessCheckAndAuditAlarmW(
                 L"Termsrv",
                 0,
                 (LPWSTR)L"Termsrv Session",
                 (LPWSTR)L"Termsrv Session",
                 *(PSECURITY_DESCRIPTOR *)((char *)this + v12),
                 a2,
                 (PGENERIC_MAPPING)&GenericMapping,
                 0,
                 (LPDWORD)&TargetHandle,
                 (LPBOOL)&TokenInformation,
                 (LPBOOL)ReturnLength) )
          {
            if ( !TokenInformation )
            {
              v8 = -2147024891;
LABEL_27:
              v16 = "AccessCheck failed: 0x%x in %s";
LABEL_8:
              _DbgPrintMessage(8, v16, v8, "CTSSessionSecurityDescriptor::AccessCheck");
            }
          }
          else
          {
            v31 = GetLastError();
            v8 = v31;
            if ( v31 > 0 )
              v8 = (unsigned __int16)v31 | 0x80070000;
            _DbgPrintMessage(4, "AccessCheckAndAuditAlarm failed: %x.", v8);
            if ( (v8 & 0x80000000) != 0 )
              goto LABEL_27;
          }
LABEL_9:
          if ( !v10 )
            goto LABEL_10;
          if ( a3 )
          {
            if ( SetThreadToken(0, 0) )
              goto LABEL_10;
            v20 = GetLastError();
            if ( v20 > 0 )
              v20 = (unsigned __int16)v20 | 0x80070000;
            _DbgPrintMessage(8, "SetThreadToken( NULL ) failed: 0x%x", (unsigned int)v20);
          }
          else
          {
            v21 = RpcRevertToSelf();
            if ( !v21 )
              goto LABEL_10;
            _DbgPrintMessage(8, "RpcRevertToSelf failed: 0x%x", v21);
          }
          goto LABEL_44;
        }
        v8 = 0;
      }
      v12 = 5912;
      goto LABEL_24;
    }
    TargetHandle = 0;
    *(_QWORD *)ReturnLength = 0;
    TokenInformation = 0;
    hSourceHandle = 0;
    v17 = (*(__int64 (__fastcall **)(struct IUserName *, HANDLE *, DWORD *))(*(_QWORD *)a3 + 88LL))(
            a3,
            &hSourceHandle,
            &TokenInformation);
    v8 = v17;
    if ( v17 < 0 )
    {
      _DbgPrintMessage(8, "GetOriginalToken failed: 0x%x in %s", v17, "CTSSession::AccessCheckEx");
    }
    else
    {
      v18 = OpenProcess(0x40u, 0, TokenInformation);
      *(_QWORD *)ReturnLength = v18;
      if ( v18 )
      {
        CurrentProcess = GetCurrentProcess();
        if ( DuplicateHandle(v18, hSourceHandle, CurrentProcess, &TargetHandle, 0, 0, 2u) )
        {
          if ( DuplicateTokenEx(TargetHandle, 0x2000000u, 0, SecurityImpersonation, TokenImpersonation, &hObject) )
          {
            if ( SetThreadToken(0, hObject) )
            {
              v10 = 1;
              CloseHandle(v18);
              if ( TargetHandle )
                CloseHandle(TargetHandle);
              v8 = 0;
              goto LABEL_4;
            }
            v29 = GetLastError();
            if ( v29 > 0 )
              v29 = (unsigned __int16)v29 | 0x80070000;
            _DbgPrintMessage(8, "SetThreadToken failed: 0x%x", v29);
            v8 = -2147024891;
            CloseHandle(*(HANDLE *)ReturnLength);
          }
          else
          {
            v22 = GetLastError();
            v8 = v22;
            if ( v22 > 0 )
              v8 = (unsigned __int16)v22 | 0x80070000;
            _DbgPrintMessage(8, "DuplicateHandleEx failed: 0x%x", v8);
            CloseHandle(*(HANDLE *)ReturnLength);
          }
        }
        else
        {
          v25 = GetLastError();
          v8 = v25;
          if ( v25 > 0 )
            v8 = (unsigned __int16)v25 | 0x80070000;
          _DbgPrintMessage(8, "DuplicateHandle failed: 0x%x", v8);
          CloseHandle(*(HANDLE *)ReturnLength);
        }
      }
      else
      {
        v23 = GetLastError();
        v8 = v23;
        if ( v23 > 0 )
          v8 = (unsigned __int16)v23 | 0x80070000;
        _DbgPrintMessage(8, "OpenProcess( %d ) : 0x%x", TokenInformation, v8);
      }
    }
    if ( TargetHandle )
      CloseHandle(TargetHandle);
  }
LABEL_10:
  if ( hObject )
    CloseHandle(hObject);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v8;
}

```

## disassembly

```asm
0x180006e20  push    rbp
0x180006e22  push    rbx
0x180006e23  push    rsi
0x180006e24  push    rdi
0x180006e25  push    r12
0x180006e27  push    r13
0x180006e29  push    r14
0x180006e2b  push    r15
0x180006e2d  lea     rbp, [rsp-1Fh]
0x180006e32  sub     rsp, 98h
0x180006e39  mov     r14d, r9d
0x180006e3c  mov     r12, r8
0x180006e3f  mov     r15d, edx
0x180006e42  mov     rsi, rcx
0x180006e45  xor     ebx, ebx
0x180006e47  mov     [rbp+57h+TokenHandle], rbx
0x180006e4b  mov     [rbp+57h+hObject], rbx
0x180006e4f  mov     edi, [rcx+6D0h]
0x180006e55  call    cs:__imp_WTSGetServiceSessionId
0x180006e5b  cmp     edi, eax
0x180006e5d  jz      short loc_180006E9D
0x180006e5f  test    r12, r12
0x180006e62  jnz     loc_18000702E
0x180006e68  mov     r13d, ebx
0x180006e6b  call    cs:__imp_GetCurrentThread
0x180006e71  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180006e75  xor     r8d, r8d; OpenAsSelf
0x180006e78  mov     edx, 8; DesiredAccess
0x180006e7d  mov     rcx, rax; ThreadHandle
0x180006e80  call    cs:__imp_OpenThreadToken
0x180006e86  test    eax, eax
0x180006e88  jz      loc_1800072F1
0x180006e8e  test    r14d, r14d
0x180006e91  jnz     short loc_180006EFA
0x180006e93  mov     eax, 1718h
0x180006e98  jmp     loc_180006FA5
0x180006e9d  test    r15d, 0FFFFFCFFh
0x180006ea4  jz      short loc_180006EC5
0x180006ea6  jmp     short loc_180006E5F
0x180006ea8  mov     r8d, ebx
0x180006eab  lea     r9, aCtssessionsecu_2; "CTSSessionSecurityDescriptor::AccessChe"...
0x180006eb2  mov     ecx, 8; int
0x180006eb7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180006ebc  test    r13d, r13d
0x180006ebf  jnz     loc_180007125
0x180006ec5  mov     rcx, [rbp+57h+hObject]; hObject
0x180006ec9  test    rcx, rcx
0x180006ecc  jz      short loc_180006ED5
0x180006ece  call    cs:__imp_CloseHandle
0x180006ed4  nop
0x180006ed5  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180006ed9  test    rcx, rcx
0x180006edc  jz      short loc_180006EE4
0x180006ede  call    cs:__imp_CloseHandle
0x180006ee4  mov     eax, ebx
0x180006ee6  add     rsp, 98h
0x180006eed  pop     r15
0x180006eef  pop     r14
0x180006ef1  pop     r13
0x180006ef3  pop     r12
0x180006ef5  pop     rdi
0x180006ef6  pop     rsi
0x180006ef7  pop     rbx
0x180006ef8  pop     rbp
0x180006ef9  retn
0x180006efa  mov     [rbp+57h+TargetHandle], 0
0x180006f02  mov     [rbp+57h+TokenInformation], 0
0x180006f09  mov     [rbp+57h+var_70], 0
0x180006f10  xor     r14d, r14d
0x180006f13  call    cs:__imp_GetCurrentThread
0x180006f19  lea     r9, [rbp+57h+TargetHandle]; TokenHandle
0x180006f1d  mov     edx, 8; DesiredAccess
0x180006f22  mov     r8d, 1; OpenAsSelf
0x180006f28  mov     rcx, rax; ThreadHandle
0x180006f2b  call    cs:__imp_OpenThreadToken
0x180006f31  test    eax, eax
0x180006f33  jz      loc_180007252
0x180006f39  lea     rax, [rbp+57h+var_70]
0x180006f3d  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x180006f42  mov     r9d, 4; TokenInformationLength
0x180006f48  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180006f4c  mov     edx, 0Ch; TokenInformationClass
0x180006f51  mov     rcx, [rbp+57h+TargetHandle]; TokenHandle
0x180006f55  call    cs:__imp_GetTokenInformation
0x180006f5b  test    eax, eax
0x180006f5d  jz      loc_180007378
0x180006f63  mov     ebx, [rbp+57h+TokenInformation]
0x180006f66  mov     rcx, [rbp+57h+TargetHandle]; hObject
0x180006f6a  test    rcx, rcx
0x180006f6d  jz      short loc_180006F75
0x180006f6f  call    cs:__imp_CloseHandle
0x180006f75  test    r14d, r14d
0x180006f78  js      loc_18000720A
0x180006f7e  xor     eax, eax
0x180006f80  cmp     ebx, edi
0x180006f82  jz      loc_1800073E2
0x180006f88  test    eax, eax
0x180006f8a  jz      loc_180007027
0x180006f90  cmp     qword ptr [rsi+1700h], 0
0x180006f98  jz      loc_1800073EC
0x180006f9e  mov     eax, 1700h
0x180006fa3  xor     ebx, ebx
0x180006fa5  mov     dword ptr [rbp+57h+TargetHandle], ebx
0x180006fa8  mov     [rbp+57h+TokenInformation], ebx
0x180006fab  mov     [rbp+57h+var_70], ebx
0x180006fae  lea     rcx, [rbp+57h+var_70]
0x180006fb2  mov     [rsp+0D0h+pfGenerateOnClose], rcx; pfGenerateOnClose
0x180006fb7  lea     rcx, [rbp+57h+TokenInformation]
0x180006fbb  mov     [rsp+0D0h+AccessStatus], rcx; AccessStatus
0x180006fc0  lea     rcx, [rbp+57h+TargetHandle]
0x180006fc4  mov     [rsp+0D0h+GrantedAccess], rcx; GrantedAccess
0x180006fc9  mov     [rsp+0D0h+ObjectCreation], ebx; ObjectCreation
0x180006fcd  lea     rcx, GenericMapping
0x180006fd4  mov     [rsp+0D0h+GenericMapping], rcx; GenericMapping
0x180006fd9  mov     [rsp+0D0h+DesiredAccess], r15d; DesiredAccess
0x180006fde  mov     rax, [rax+rsi]
0x180006fe2  mov     [rsp+0D0h+ReturnLength], rax; SecurityDescriptor
0x180006fe7  lea     r9, ObjectName; "Termsrv Session"
0x180006fee  lea     r8, ObjectName; "Termsrv Session"
0x180006ff5  xor     edx, edx; HandleId
0x180006ff7  lea     rcx, SubsystemName; "Termsrv"
0x180006ffe  call    cs:__imp_AccessCheckAndAuditAlarmW
0x180007004  test    eax, eax
0x180007006  jz      loc_1800073B9
0x18000700c  cmp     [rbp+57h+TokenInformation], 0
0x180007010  jnz     loc_180006EBC
0x180007016  mov     ebx, 80070005h
0x18000701b  lea     rdx, aAccesscheckFai; "AccessCheck failed: 0x%x in %s"
0x180007022  jmp     loc_180006EA8
0x180007027  xor     ebx, ebx
0x180007029  jmp     loc_180006E93
0x18000702e  mov     [rbp+57h+TargetHandle], rbx
0x180007032  mov     qword ptr [rbp+57h+var_70], rbx
0x180007036  mov     [rbp+57h+TokenInformation], ebx
0x180007039  mov     [rbp+57h+hSourceHandle], rbx
0x18000703d  mov     rax, [r12]
0x180007041  lea     r8, [rbp+57h+TokenInformation]
0x180007045  lea     rdx, [rbp+57h+hSourceHandle]
0x180007049  mov     rcx, r12
0x18000704c  mov     rax, [rax+58h]
0x180007050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007055  mov     ebx, eax
0x180007057  test    eax, eax
0x180007059  js      loc_180007183
0x18000705f  mov     r8d, [rbp+57h+TokenInformation]; dwProcessId
0x180007063  xor     edx, edx; bInheritHandle
0x180007065  mov     ecx, 40h ; '@'; dwDesiredAccess
0x18000706a  call    cs:__imp_OpenProcess
0x180007070  mov     rbx, rax
0x180007073  mov     qword ptr [rbp+57h+var_70], rax
0x180007077  test    rax, rax
0x18000707a  jz      loc_1800071E4
0x180007080  call    cs:__imp_GetCurrentProcess
0x180007086  mov     dword ptr [rsp+0D0h+GenericMapping], 2; dwOptions
0x18000708e  mov     [rsp+0D0h+DesiredAccess], 0; bInheritHandle
0x180007096  mov     dword ptr [rsp+0D0h+ReturnLength], 0; dwDesiredAccess
0x18000709e  lea     r9, [rbp+57h+TargetHandle]; lpTargetHandle
0x1800070a2  mov     r8, rax; hTargetProcessHandle
0x1800070a5  mov     rdx, [rbp+57h+hSourceHandle]; hSourceHandle
0x1800070a9  mov     rcx, rbx; hSourceProcessHandle
0x1800070ac  call    cs:__imp_DuplicateHandle
0x1800070b2  test    eax, eax
0x1800070b4  jz      loc_180007288
0x1800070ba  lea     rax, [rbp+57h+hObject]
0x1800070be  mov     qword ptr [rsp+0D0h+DesiredAccess], rax; phNewToken
0x1800070c3  mov     dword ptr [rsp+0D0h+ReturnLength], 2; TokenType
0x1800070cb  mov     r9d, 2; ImpersonationLevel
0x1800070d1  xor     r8d, r8d; lpTokenAttributes
0x1800070d4  mov     edx, 2000000h; dwDesiredAccess
0x1800070d9  mov     rcx, [rbp+57h+TargetHandle]; hExistingToken
0x1800070dd  call    cs:__imp_DuplicateTokenEx
0x1800070e3  test    eax, eax
0x1800070e5  jz      loc_1800071B7
0x1800070eb  mov     rdx, [rbp+57h+hObject]; Token
0x1800070ef  xor     ecx, ecx; Thread
0x1800070f1  call    cs:__imp_SetThreadToken
0x1800070f7  test    eax, eax
0x1800070f9  jz      loc_18000733E
0x1800070ff  mov     r13d, 1
0x180007105  mov     rcx, rbx; hObject
0x180007108  call    cs:__imp_CloseHandle
0x18000710e  nop
0x18000710f  mov     rcx, [rbp+57h+TargetHandle]; hObject
0x180007113  test    rcx, rcx
0x180007116  jz      short loc_18000711E
0x180007118  call    cs:__imp_CloseHandle
0x18000711e  xor     ebx, ebx
0x180007120  jmp     loc_180006E8E
0x180007125  test    r12, r12
0x180007128  jz      short loc_180007157
0x18000712a  xor     edx, edx; Token
0x18000712c  xor     ecx, ecx; Thread
0x18000712e  call    cs:__imp_SetThreadToken
0x180007134  test    eax, eax
0x180007136  jnz     loc_180006EC5
0x18000713c  call    cs:__imp_GetLastError
0x180007142  test    eax, eax
0x180007144  jle     short loc_18000714E
0x180007146  movzx   eax, ax
0x180007149  or      eax, 80070000h
0x18000714e  lea     rdx, aSetthreadtoken; "SetThreadToken( NULL ) failed: 0x%x"
0x180007155  jmp     short loc_18000716C
0x180007157  call    cs:__imp_RpcRevertToSelf
0x18000715d  test    eax, eax
0x18000715f  jz      loc_180006EC5
0x180007165  lea     rdx, aRpcreverttosel; "RpcRevertToSelf failed: 0x%x"
0x18000716c  mov     r8d, eax
0x18000716f  mov     ecx, 8; int
0x180007174  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180007179  mov     ebx, 80070005h
0x18000717e  jmp     loc_180006EC5
0x180007183  lea     r9, aCtssessionAcce; "CTSSession::AccessCheckEx"
0x18000718a  mov     r8d, eax
0x18000718d  lea     rdx, aGetoriginaltok; "GetOriginalToken failed: 0x%x in %s"
0x180007194  mov     ecx, 8; int
0x180007199  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000719e  nop
0x18000719f  mov     rcx, [rbp+57h+TargetHandle]; hObject
0x1800071a3  test    rcx, rcx
0x1800071a6  jz      loc_180006EC5
0x1800071ac  call    cs:__imp_CloseHandle
0x1800071b2  jmp     loc_180006EC5
0x1800071b7  call    cs:__imp_GetLastError
0x1800071bd  mov     ebx, eax
0x1800071bf  test    eax, eax
0x1800071c1  jg      short loc_180007239
0x1800071c3  mov     r8d, ebx
0x1800071c6  lea     rdx, aDuplicatehandl_2; "DuplicateHandleEx failed: 0x%x"
0x1800071cd  mov     ecx, 8; int
0x1800071d2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800071d7  nop
0x1800071d8  mov     rcx, qword ptr [rbp+57h+var_70]; hObject
0x1800071dc  call    cs:__imp_CloseHandle
0x1800071e2  jmp     short loc_18000719F
0x1800071e4  call    cs:__imp_GetLastError
0x1800071ea  mov     ebx, eax
0x1800071ec  test    eax, eax
0x1800071ee  jg      short loc_180007247
0x1800071f0  mov     r9d, ebx
0x1800071f3  mov     r8d, [rbp+57h+TokenInformation]
0x1800071f7  lea     rdx, aOpenprocessD0x; "OpenProcess( %d ) : 0x%x"
0x1800071fe  mov     ecx, 8; int
0x180007203  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180007208  jmp     short loc_18000719F
0x18000720a  lea     r9, aCtssessionsecu_1; "CTSSessionSecurityDescriptor::IsSameSes"...
0x180007211  mov     r8d, r14d
0x180007214  lea     rdx, aCutilsGetusers; "CUtils::GetUserSessionId() failed: 0x%x"...
0x18000721b  mov     ecx, 8; int
0x180007220  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180007225  mov     ebx, 80070005h
0x18000722a  mov     r8d, r14d
0x18000722d  lea     rdx, aIssamesessioni; "IsSameSessionId failed: 0x%x in %s"
0x180007234  jmp     loc_180006EAB
0x180007239  movzx   ebx, ax
0x18000723c  or      ebx, 80070000h
0x180007242  jmp     loc_1800071C3
0x180007247  movzx   ebx, ax
0x18000724a  or      ebx, 80070000h
0x180007250  jmp     short loc_1800071F0
0x180007252  call    cs:__imp_GetLastError
0x180007258  mov     r14d, eax
0x18000725b  test    eax, eax
0x18000725d  jg      short loc_1800072B8
0x18000725f  test    r14d, r14d
0x180007262  jns     loc_180006F39
0x180007268  lea     r9, aCutilsGetusers_0; "CUtils::GetUserSessionId"
0x18000726f  mov     r8d, r14d
0x180007272  lea     rdx, aOpenthreadtoke_0; "OpenThreadToken failed: 0x%x in %s"
0x180007279  mov     ecx, 8; int
0x18000727e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180007283  jmp     loc_180006F66
0x180007288  call    cs:__imp_GetLastError
0x18000728e  mov     ebx, eax
0x180007290  test    eax, eax
0x180007292  jg      short loc_1800072C5
0x180007294  mov     r8d, ebx
0x180007297  lea     rdx, aDuplicatehandl_3; "DuplicateHandle failed: 0x%x"
0x18000729e  mov     ecx, 8; int
0x1800072a3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800072a8  nop
0x1800072a9  mov     rcx, qword ptr [rbp+57h+var_70]; hObject
0x1800072ad  call    cs:__imp_CloseHandle
0x1800072b3  jmp     loc_18000719F
0x1800072b8  movzx   r14d, ax
0x1800072bc  or      r14d, 80070000h
0x1800072c3  jmp     short loc_18000725F
0x1800072c5  movzx   ebx, ax
0x1800072c8  or      ebx, 80070000h
0x1800072ce  jmp     short loc_180007294
0x1800072d0  mov     r8d, ebx
0x1800072d3  lea     rdx, aAccesscheckand_0; "AccessCheckAndAuditAlarm failed: %x."
0x1800072da  mov     ecx, 4; int
0x1800072df  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800072e4  test    ebx, ebx
0x1800072e6  jns     loc_180006EBC
0x1800072ec  jmp     loc_18000701B
0x1800072f1  call    cs:__imp_GetLastError
0x1800072f7  test    eax, eax
0x1800072f9  jle     short loc_180007303
0x1800072fb  movzx   eax, ax
  ... truncated ...
```
