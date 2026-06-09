# CTSSession::AccessCheckEx(ulong,IUserName *,int)

- ea: `0x180007060`
- end: `0x1800076de`
- name: `?AccessCheckEx@CTSSession@@UEAAJKPEAUIUserName@@H@Z`
- size: `1662`
- prototype: `int(CTSSession *__hidden this, unsigned int, struct IUserName *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180007050`

## callees

- `0x180007060`
- `0x1800077a0`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007476`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000752a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007566`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007616`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000764c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007693`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007476`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000752a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007566`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007616`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000764c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007693`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180007386`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800073d5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180007386`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800073d5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800070cc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180007190`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800070cc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180007190`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800070b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180007172`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800070b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180007172`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180007303`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180007303`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007120`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007136`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800071e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800073a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800073b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007465`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007120`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007136`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800071e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800073a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800073b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007465`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074a5`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180007335`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180007335`
- `RPCRT4!RpcImpersonateClient` at `0x1800075ea`
- `RPCRT4!RpcImpersonateClient` at `0x1800075ea`
- `RPCRT4!RpcRevertToSelf` at `0x18000740a`
- `RPCRT4!RpcRevertToSelf` at `0x18000740a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800072e7`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800072e7`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180007095`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180007095`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000736c`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000736c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800071c0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800071c0`
- `api-ms-win-security-base-l1-1-0!AccessCheckAndAuditAlarmW` at `0x180007275`
- `api-ms-win-security-base-l1-1-0!AccessCheckAndAuditAlarmW` at `0x180007275`

## string_xrefs

- `0x18000759f`: `AccessCheckAndAuditAlarm failed: %x.`
- `0x18000743c`: `CTSSession::AccessCheckEx`
- `0x180007446`: `GetOriginalToken failed: 0x%x in %s`
- `0x1800074e2`: `CTSSessionSecurityDescriptor::IsSameSessionId`
- `0x1800070fd`: `CTSSessionSecurityDescriptor::AccessCheck`
- `0x1800074cc`: `OpenProcess( %d ) : 0x%x`
- `0x180007631`: `SetThreadToken failed: 0x%x`
- `0x180007401`: `SetThreadToken( NULL ) failed: 0x%x`
- `0x180007550`: `OpenThreadToken failed: 0x%x in %s`
- `0x18000767d`: `GetTokenInformation failed: 0x%x in %s`
- `0x18000760a`: `RpcImpersonateClient failed: 0x%x`
- `0x1800075dc`: `OpenThreadToken failed with some other error: 0x%x`
- `0x180007298`: `AccessCheck failed: 0x%x in %s`

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
          goto LABEL_78;
        v24 = GetLastError();
        v14 = v24;
        if ( v24 > 0 )
          v14 = (unsigned __int16)v24 | 0x80070000;
        if ( v14 >= 0 )
        {
LABEL_78:
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
          }
          else
          {
            v22 = GetLastError();
            v8 = v22;
            if ( v22 > 0 )
              v8 = (unsigned __int16)v22 | 0x80070000;
            _DbgPrintMessage(8, "DuplicateHandleEx failed: 0x%x", v8);
          }
        }
        else
        {
          v25 = GetLastError();
          v8 = v25;
          if ( v25 > 0 )
            v8 = (unsigned __int16)v25 | 0x80070000;
          _DbgPrintMessage(8, "DuplicateHandle failed: 0x%x", v8);
        }
        CloseHandle(*(HANDLE *)ReturnLength);
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
0x180007060  push    rbp
0x180007062  push    rbx
0x180007063  push    rsi
0x180007064  push    rdi
0x180007065  push    r12
0x180007067  push    r13
0x180007069  push    r14
0x18000706b  push    r15
0x18000706d  lea     rbp, [rsp-1Fh]
0x180007072  sub     rsp, 98h
0x180007079  mov     r14d, r9d
0x18000707c  mov     r12, r8
0x18000707f  mov     r15d, edx
0x180007082  mov     rsi, rcx
0x180007085  xor     ebx, ebx
0x180007087  mov     [rbp+57h+TokenHandle], rbx
0x18000708b  mov     [rbp+57h+hObject], rbx
0x18000708f  mov     edi, [rcx+6D0h]
0x180007095  call    cs:__imp_WTSGetServiceSessionId
0x18000709c  nop     dword ptr [rax+rax+00h]
0x1800070a1  cmp     edi, eax
0x1800070a3  jz      short loc_1800070EF
0x1800070a5  test    r12, r12
0x1800070a8  jnz     loc_1800072AB
0x1800070ae  mov     r13d, ebx
0x1800070b1  call    cs:__imp_GetCurrentThread
0x1800070b8  nop     dword ptr [rax+rax+00h]
0x1800070bd  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800070c1  xor     r8d, r8d; OpenAsSelf
0x1800070c4  mov     edx, 8; DesiredAccess
0x1800070c9  mov     rcx, rax; ThreadHandle
0x1800070cc  call    cs:__imp_OpenThreadToken
0x1800070d3  nop     dword ptr [rax+rax+00h]
0x1800070d8  test    eax, eax
0x1800070da  jz      loc_1800075BD
0x1800070e0  test    r14d, r14d
0x1800070e3  jnz     short loc_180007159
0x1800070e5  mov     eax, 1718h
0x1800070ea  jmp     loc_18000721C
0x1800070ef  test    r15d, 0FFFFFCFFh
0x1800070f6  jz      short loc_180007117
0x1800070f8  jmp     short loc_1800070A5
0x1800070fa  mov     r8d, ebx
0x1800070fd  lea     r9, aCtssessionsecu_2; "CTSSessionSecurityDescriptor::AccessChe"...
0x180007104  mov     ecx, 8; int
0x180007109  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000710e  test    r13d, r13d
0x180007111  jnz     loc_1800073CC
0x180007117  mov     rcx, [rbp+57h+hObject]; hObject
0x18000711b  test    rcx, rcx
0x18000711e  jz      short loc_18000712D
0x180007120  call    cs:__imp_CloseHandle
0x180007127  nop     dword ptr [rax+rax+00h]
0x18000712c  nop
0x18000712d  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180007131  test    rcx, rcx
0x180007134  jz      short loc_180007142
0x180007136  call    cs:__imp_CloseHandle
0x18000713d  nop     dword ptr [rax+rax+00h]
0x180007142  mov     eax, ebx
0x180007144  add     rsp, 98h
0x18000714b  pop     r15
0x18000714d  pop     r14
0x18000714f  pop     r13
0x180007151  pop     r12
0x180007153  pop     rdi
0x180007154  pop     rsi
0x180007155  pop     rbx
0x180007156  pop     rbp
0x180007157  retn
0x180007159  mov     [rbp+57h+TargetHandle], 0
0x180007161  mov     [rbp+57h+TokenInformation], 0
0x180007168  mov     [rbp+57h+var_70], 0
0x18000716f  xor     r14d, r14d
0x180007172  call    cs:__imp_GetCurrentThread
0x180007179  nop     dword ptr [rax+rax+00h]
0x18000717e  lea     r9, [rbp+57h+TargetHandle]; TokenHandle
0x180007182  mov     edx, 8; DesiredAccess
0x180007187  mov     r8d, 1; OpenAsSelf
0x18000718d  mov     rcx, rax; ThreadHandle
0x180007190  call    cs:__imp_OpenThreadToken
0x180007197  nop     dword ptr [rax+rax+00h]
0x18000719c  test    eax, eax
0x18000719e  jz      loc_18000752A
0x1800071a4  lea     rax, [rbp+57h+var_70]
0x1800071a8  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x1800071ad  mov     r9d, 4; TokenInformationLength
0x1800071b3  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800071b7  mov     edx, 0Ch; TokenInformationClass
0x1800071bc  mov     rcx, [rbp+57h+TargetHandle]; TokenHandle
0x1800071c0  call    cs:__imp_GetTokenInformation
0x1800071c7  nop     dword ptr [rax+rax+00h]
0x1800071cc  test    eax, eax
0x1800071ce  jz      loc_18000764C
0x1800071d4  mov     ebx, [rbp+57h+TokenInformation]
0x1800071d7  mov     rcx, [rbp+57h+TargetHandle]; hObject
0x1800071db  test    rcx, rcx
0x1800071de  jz      short loc_1800071EC
0x1800071e0  call    cs:__imp_CloseHandle
0x1800071e7  nop     dword ptr [rax+rax+00h]
0x1800071ec  test    r14d, r14d
0x1800071ef  js      loc_1800074E2
0x1800071f5  xor     eax, eax
0x1800071f7  cmp     ebx, edi
0x1800071f9  jz      loc_1800076C2
0x1800071ff  test    eax, eax
0x180007201  jz      loc_1800072A4
0x180007207  cmp     qword ptr [rsi+1700h], 0
0x18000720f  jz      loc_1800076CC
0x180007215  mov     eax, 1700h
0x18000721a  xor     ebx, ebx
0x18000721c  mov     dword ptr [rbp+57h+TargetHandle], ebx
0x18000721f  mov     [rbp+57h+TokenInformation], ebx
0x180007222  mov     [rbp+57h+var_70], ebx
0x180007225  lea     rcx, [rbp+57h+var_70]
0x180007229  mov     [rsp+0D0h+pfGenerateOnClose], rcx; pfGenerateOnClose
0x18000722e  lea     rcx, [rbp+57h+TokenInformation]
0x180007232  mov     [rsp+0D0h+AccessStatus], rcx; AccessStatus
0x180007237  lea     rcx, [rbp+57h+TargetHandle]
0x18000723b  mov     [rsp+0D0h+GrantedAccess], rcx; GrantedAccess
0x180007240  mov     [rsp+0D0h+ObjectCreation], ebx; ObjectCreation
0x180007244  lea     rcx, GenericMapping
0x18000724b  mov     [rsp+0D0h+GenericMapping], rcx; GenericMapping
0x180007250  mov     [rsp+0D0h+DesiredAccess], r15d; DesiredAccess
0x180007255  mov     rax, [rax+rsi]
0x180007259  mov     [rsp+0D0h+ReturnLength], rax; SecurityDescriptor
0x18000725e  lea     r9, ObjectName; "Termsrv Session"
0x180007265  lea     r8, ObjectName; "Termsrv Session"
0x18000726c  xor     edx, edx; HandleId
0x18000726e  lea     rcx, SubsystemName; "Termsrv"
0x180007275  call    cs:__imp_AccessCheckAndAuditAlarmW
0x18000727c  nop     dword ptr [rax+rax+00h]
0x180007281  test    eax, eax
0x180007283  jz      loc_180007693
0x180007289  cmp     [rbp+57h+TokenInformation], 0
0x18000728d  jnz     loc_18000710E
0x180007293  mov     ebx, 80070005h
0x180007298  lea     rdx, aAccesscheckFai; "AccessCheck failed: 0x%x in %s"
0x18000729f  jmp     loc_1800070FA
0x1800072a4  xor     ebx, ebx
0x1800072a6  jmp     loc_1800070E5
0x1800072ab  mov     [rbp+57h+TargetHandle], rbx
0x1800072af  mov     qword ptr [rbp+57h+var_70], rbx
0x1800072b3  mov     [rbp+57h+TokenInformation], ebx
0x1800072b6  mov     [rbp+57h+hSourceHandle], rbx
0x1800072ba  mov     rax, [r12]
0x1800072be  lea     r8, [rbp+57h+TokenInformation]
0x1800072c2  lea     rdx, [rbp+57h+hSourceHandle]
0x1800072c6  mov     rcx, r12
0x1800072c9  mov     rax, [rax+58h]
0x1800072cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072d2  mov     ebx, eax
0x1800072d4  test    eax, eax
0x1800072d6  js      loc_18000743C
0x1800072dc  mov     r8d, [rbp+57h+TokenInformation]; dwProcessId
0x1800072e0  xor     edx, edx; bInheritHandle
0x1800072e2  mov     ecx, 40h ; '@'; dwDesiredAccess
0x1800072e7  call    cs:__imp_OpenProcess
0x1800072ee  nop     dword ptr [rax+rax+00h]
0x1800072f3  mov     rbx, rax
0x1800072f6  mov     qword ptr [rbp+57h+var_70], rax
0x1800072fa  test    rax, rax
0x1800072fd  jz      loc_1800074B3
0x180007303  call    cs:__imp_GetCurrentProcess
0x18000730a  nop     dword ptr [rax+rax+00h]
0x18000730f  mov     dword ptr [rsp+0D0h+GenericMapping], 2; dwOptions
0x180007317  mov     [rsp+0D0h+DesiredAccess], 0; bInheritHandle
0x18000731f  mov     dword ptr [rsp+0D0h+ReturnLength], 0; dwDesiredAccess
0x180007327  lea     r9, [rbp+57h+TargetHandle]; lpTargetHandle
0x18000732b  mov     r8, rax; hTargetProcessHandle
0x18000732e  mov     rdx, [rbp+57h+hSourceHandle]; hSourceHandle
0x180007332  mov     rcx, rbx; hSourceProcessHandle
0x180007335  call    cs:__imp_DuplicateHandle
0x18000733c  nop     dword ptr [rax+rax+00h]
0x180007341  test    eax, eax
0x180007343  jz      loc_180007566
0x180007349  lea     rax, [rbp+57h+hObject]
0x18000734d  mov     qword ptr [rsp+0D0h+DesiredAccess], rax; phNewToken
0x180007352  mov     dword ptr [rsp+0D0h+ReturnLength], 2; TokenType
0x18000735a  mov     r9d, 2; ImpersonationLevel
0x180007360  xor     r8d, r8d; lpTokenAttributes
0x180007363  mov     edx, 2000000h; dwDesiredAccess
0x180007368  mov     rcx, [rbp+57h+TargetHandle]; hExistingToken
0x18000736c  call    cs:__imp_DuplicateTokenEx
0x180007373  nop     dword ptr [rax+rax+00h]
0x180007378  test    eax, eax
0x18000737a  jz      loc_180007476
0x180007380  mov     rdx, [rbp+57h+hObject]; Token
0x180007384  xor     ecx, ecx; Thread
0x180007386  call    cs:__imp_SetThreadToken
0x18000738d  nop     dword ptr [rax+rax+00h]
0x180007392  test    eax, eax
0x180007394  jz      loc_180007616
0x18000739a  mov     r13d, 1
0x1800073a0  mov     rcx, rbx; hObject
0x1800073a3  call    cs:__imp_CloseHandle
0x1800073aa  nop     dword ptr [rax+rax+00h]
0x1800073af  nop
0x1800073b0  mov     rcx, [rbp+57h+TargetHandle]; hObject
0x1800073b4  test    rcx, rcx
0x1800073b7  jz      short loc_1800073C5
0x1800073b9  call    cs:__imp_CloseHandle
0x1800073c0  nop     dword ptr [rax+rax+00h]
0x1800073c5  xor     ebx, ebx
0x1800073c7  jmp     loc_1800070E0
0x1800073cc  test    r12, r12
0x1800073cf  jz      short loc_18000740A
0x1800073d1  xor     edx, edx; Token
0x1800073d3  xor     ecx, ecx; Thread
0x1800073d5  call    cs:__imp_SetThreadToken
0x1800073dc  nop     dword ptr [rax+rax+00h]
0x1800073e1  test    eax, eax
0x1800073e3  jnz     loc_180007117
0x1800073e9  call    cs:__imp_GetLastError
0x1800073f0  nop     dword ptr [rax+rax+00h]
0x1800073f5  test    eax, eax
0x1800073f7  jle     short loc_180007401
0x1800073f9  movzx   eax, ax
0x1800073fc  or      eax, 80070000h
0x180007401  lea     rdx, aSetthreadtoken; "SetThreadToken( NULL ) failed: 0x%x"
0x180007408  jmp     short loc_180007425
0x18000740a  call    cs:__imp_RpcRevertToSelf
0x180007411  nop     dword ptr [rax+rax+00h]
0x180007416  test    eax, eax
0x180007418  jz      loc_180007117
0x18000741e  lea     rdx, aRpcreverttosel; "RpcRevertToSelf failed: 0x%x"
0x180007425  mov     r8d, eax
0x180007428  mov     ecx, 8; int
0x18000742d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180007432  mov     ebx, 80070005h
0x180007437  jmp     loc_180007117
0x18000743c  lea     r9, aCtssessionAcce; "CTSSession::AccessCheckEx"
0x180007443  mov     r8d, eax
0x180007446  lea     rdx, aGetoriginaltok; "GetOriginalToken failed: 0x%x in %s"
0x18000744d  mov     ecx, 8; int
0x180007452  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180007457  nop
0x180007458  mov     rcx, [rbp+57h+TargetHandle]; hObject
0x18000745c  test    rcx, rcx
0x18000745f  jz      loc_180007117
0x180007465  call    cs:__imp_CloseHandle
0x18000746c  nop     dword ptr [rax+rax+00h]
0x180007471  jmp     loc_180007117
0x180007476  call    cs:__imp_GetLastError
0x18000747d  nop     dword ptr [rax+rax+00h]
0x180007482  mov     ebx, eax
0x180007484  test    eax, eax
0x180007486  jg      loc_180007511
0x18000748c  lea     rdx, aDuplicatehandl_2; "DuplicateHandleEx failed: 0x%x"
0x180007493  mov     r8d, ebx
0x180007496  mov     ecx, 8; int
0x18000749b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800074a0  nop
0x1800074a1  mov     rcx, qword ptr [rbp+57h+var_70]; hObject
0x1800074a5  call    cs:__imp_CloseHandle
0x1800074ac  nop     dword ptr [rax+rax+00h]
0x1800074b1  jmp     short loc_180007458
0x1800074b3  call    cs:__imp_GetLastError
0x1800074ba  nop     dword ptr [rax+rax+00h]
0x1800074bf  mov     ebx, eax
0x1800074c1  test    eax, eax
0x1800074c3  jg      short loc_18000751F
0x1800074c5  mov     r9d, ebx
0x1800074c8  mov     r8d, [rbp+57h+TokenInformation]
0x1800074cc  lea     rdx, aOpenprocessD0x; "OpenProcess( %d ) : 0x%x"
0x1800074d3  mov     ecx, 8; int
0x1800074d8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800074dd  jmp     loc_180007458
0x1800074e2  lea     r9, aCtssessionsecu_1; "CTSSessionSecurityDescriptor::IsSameSes"...
0x1800074e9  mov     r8d, r14d
0x1800074ec  lea     rdx, aCutilsGetusers; "CUtils::GetUserSessionId() failed: 0x%x"...
0x1800074f3  mov     ecx, 8; int
0x1800074f8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800074fd  mov     ebx, 80070005h
0x180007502  mov     r8d, r14d
0x180007505  lea     rdx, aIssamesessioni; "IsSameSessionId failed: 0x%x in %s"
0x18000750c  jmp     loc_1800070FD
0x180007511  movzx   ebx, ax
0x180007514  or      ebx, 80070000h
0x18000751a  jmp     loc_18000748C
0x18000751f  movzx   ebx, ax
0x180007522  or      ebx, 80070000h
0x180007528  jmp     short loc_1800074C5
0x18000752a  call    cs:__imp_GetLastError
0x180007531  nop     dword ptr [rax+rax+00h]
0x180007536  mov     r14d, eax
0x180007539  test    eax, eax
0x18000753b  jg      short loc_180007584
0x18000753d  test    r14d, r14d
0x180007540  jns     loc_1800071A4
0x180007546  lea     r9, aCutilsGetusers_0; "CUtils::GetUserSessionId"
0x18000754d  mov     r8d, r14d
0x180007550  lea     rdx, aOpenthreadtoke_0; "OpenThreadToken failed: 0x%x in %s"
0x180007557  mov     ecx, 8; int
0x18000755c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180007561  jmp     loc_1800071D7
0x180007566  call    cs:__imp_GetLastError
0x18000756d  nop     dword ptr [rax+rax+00h]
0x180007572  mov     ebx, eax
0x180007574  test    eax, eax
  ... truncated ...
```
