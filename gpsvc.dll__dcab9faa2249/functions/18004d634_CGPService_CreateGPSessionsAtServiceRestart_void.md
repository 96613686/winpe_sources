# CGPService::CreateGPSessionsAtServiceRestart(void)

- ea: `0x18004d634`
- end: `0x18004dbf9`
- name: `?CreateGPSessionsAtServiceRestart@CGPService@@AEAAKXZ`
- size: `1477`
- prototype: `__int64 __fastcall(CGPService *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180034c34`

## callees

- `0x180039148`
- `0x18004d634`
- `0x180075ec0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d865`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d8a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004db9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dbcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d865`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d8a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004db9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dbcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004db53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004db69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004db53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004db69`
- `ntdll!NtDuplicateToken` at `0x18004d99f`
- `ntdll!NtDuplicateToken` at `0x18004d99f`
- `ntdll!NtQueryInformationToken` at `0x18004d91e`
- `ntdll!NtQueryInformationToken` at `0x18004d953`
- `ntdll!NtQueryInformationToken` at `0x18004d9e2`
- `ntdll!NtQueryInformationToken` at `0x18004d91e`
- `ntdll!NtQueryInformationToken` at `0x18004d953`
- `ntdll!NtQueryInformationToken` at `0x18004d9e2`
- `WTSAPI32!WTSFreeMemory` at `0x18004db7f`
- `WTSAPI32!WTSFreeMemory` at `0x18004db7f`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x18004d79f`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x18004d79f`
- `WTSAPI32!WTSQueryUserToken` at `0x18004d82f`
- `WTSAPI32!WTSQueryUserToken` at `0x18004d82f`

## string_xrefs

- `0x18004d66e`: `CGPService::CreateGPSessionsAtServiceRestart()`
- `0x18004d691`: `CGPService::CreateGPSessionsAtServiceRestart()`
- `0x18004d707`: `Machine session at service restart failed with 0x%x`
- `0x18004d72a`: `Machine session at service restart failed with 0x%x`
- `0x18004d877`: `Error querying user token for session id %d = 0x%x`
- `0x18004d8ba`: `Error querying user token for session id %d = 0x%x`
- `0x18004d9c2`: `CreateGPSessionsAtServiceRestart: LUAGetElevatedToken failed with 0x%x. Using original user token.`
- `0x18004da0d`: `CreateGPSessionsAtServiceRestart: LUAGetElevatedToken failed with 0x%x. Using original user token.`
- `0x18004db0d`: `User session at service restart failed with 0x%x`
- `0x18004db30`: `User session at service restart failed with 0x%x`

## pseudocode

```c
__int64 __fastcall CGPService::CreateGPSessionsAtServiceRestart(CGPService *this)
{
  unsigned int v2; // eax
  __int64 v3; // r8
  int v4; // esi
  void (*v5)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD LastError; // eax
  DWORD v7; // eax
  void *v8; // rbx
  NTSTATUS v9; // r8d
  void *v10; // rcx
  unsigned int v11; // eax
  void (*v12)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD v13; // eax
  DWORD v14; // eax
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+30h] [rbp-99h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-91h] BYREF
  void *phToken; // [rsp+40h] [rbp-89h] BYREF
  void *v19; // [rsp+48h] [rbp-81h] BYREF
  __int128 v20; // [rsp+50h] [rbp-79h] BYREF
  __int128 v21; // [rsp+60h] [rbp-69h]
  __int64 v22; // [rsp+70h] [rbp-59h]
  _QWORD v23[2]; // [rsp+78h] [rbp-51h] BYREF
  const wchar_t *v24; // [rsp+88h] [rbp-41h]
  __int64 v25; // [rsp+90h] [rbp-39h]
  _QWORD v26[2]; // [rsp+98h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-21h] BYREF
  DWORD pCount; // [rsp+130h] [rbp+67h] BYREF
  int TokenInformation; // [rsp+138h] [rbp+6Fh] BYREF
  ULONG ReturnLength; // [rsp+140h] [rbp+77h] BYREF
  int v31; // [rsp+148h] [rbp+7Fh] BYREF

  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"CGPService::CreateGPSessionsAtServiceRestart()");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"CGPService::CreateGPSessionsAtServiceRestart()");
    }
  }
  v23[0] = 0;
  v23[1] = 0;
  v25 = 0;
  v24 = 0;
  if ( *((_DWORD *)this + 11) )
  {
    v24 = L"TriggerStarted";
    LODWORD(v25) = 30;
  }
  v2 = (***((__int64 (__fastcall ****)(_QWORD, _QWORD *, _QWORD, __int64))this + 11))(
         *((_QWORD *)this + 11),
         v23,
         *((_QWORD *)this + 14),
         1);
  v3 = v2;
  if ( v2 && *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(2u, L"Machine session at service restart failed with 0x%x", v2);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(2u, L"Machine session at service restart failed with 0x%x", v2);
    }
  }
  ppSessionInfo = 0;
  pCount = 0;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"Creating Logged on User Sessions", v3);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"Creating Logged on User Sessions", v3);
    }
  }
  if ( WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount) )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"Sessions found %d", pCount);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"Sessions found %d", pCount);
      }
    }
    v4 = 0;
    if ( pCount )
    {
      while ( (ppSessionInfo[v4].State & 0xFFFFFFFB) != 0 )
      {
LABEL_76:
        if ( ++v4 >= pCount )
          goto LABEL_77;
      }
      phToken = 0;
      if ( !WTSQueryUserToken(ppSessionInfo[v4].SessionId, &phToken) )
      {
        if ( ppSessionInfo[v4].SessionId && *(_DWORD *)&g_dwDebugLevel )
        {
          v5 = g_lpDebugMsg;
          if ( g_lpDebugMsg )
          {
            LastError = GetLastError();
            v5(2u, L"Error querying user token for session id %d = 0x%x", ppSessionInfo[v4].SessionId, LastError);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            v7 = GetLastError();
            RedirectDebugMsg(2u, L"Error querying user token for session id %d = 0x%x", ppSessionInfo[v4].SessionId, v7);
          }
        }
LABEL_74:
        if ( (char *)phToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(phToken);
        goto LABEL_76;
      }
      v20 = 0;
      v21 = 0;
      v22 = 0;
      v8 = phToken;
      ReturnLength = 0;
      v31 = 0;
      TokenInformation = 0;
      v19 = 0;
      memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
      hObject = 0;
      v9 = NtQueryInformationToken(phToken, TokenElevationType, &TokenInformation, 4u, &ReturnLength);
      if ( v9 >= 0 )
      {
        if ( TokenInformation == 2 )
          goto LABEL_44;
        if ( TokenInformation != 1 )
        {
          v9 = NtQueryInformationToken(v8, TokenLinkedToken, &v19, 8u, &ReturnLength);
          if ( v9 >= 0 )
            hObject = v19;
          goto LABEL_45;
        }
        v9 = NtQueryInformationToken(v8, TokenElevation, &v31, 4u, &ReturnLength);
        if ( v9 >= 0 )
        {
          if ( v31 )
          {
LABEL_44:
            ObjectAttributes.Length = 48;
            memset(&ObjectAttributes.RootDirectory, 0, 20);
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            v9 = NtDuplicateToken(v8, 0, &ObjectAttributes, 0, TokenPrimary, &hObject);
          }
        }
      }
LABEL_45:
      if ( v9 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(
              2u,
              L"CreateGPSessionsAtServiceRestart: LUAGetElevatedToken failed with 0x%x. Using original user token.");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(
              2u,
              L"CreateGPSessionsAtServiceRestart: LUAGetElevatedToken failed with 0x%x. Using original user token.");
          }
        }
        XHandle::operator=(&hObject, 0);
      }
      v10 = phToken;
      if ( hObject )
        v10 = hObject;
      v26[0] = &CToken::`vftable';
      v26[1] = v10;
      v20 = 0;
      v21 = 0;
      v22 = 0;
      DWORD2(v20) = ppSessionInfo[v4].SessionId;
      *(_QWORD *)&v21 = 0;
      DWORD2(v21) = 0;
      if ( *((_DWORD *)this + 11) )
      {
        *(_QWORD *)&v21 = L"TriggerStarted";
        DWORD2(v21) = 30;
      }
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"Creating User Session for session %d");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"Creating User Session for session %d");
        }
      }
      v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, __int128 *, _QWORD, int))(**((_QWORD **)this + 11) + 8LL))(
              *((_QWORD *)this + 11),
              v26,
              &v20,
              *((_QWORD *)this + 14),
              1);
      if ( v11 && *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"User session at service restart failed with 0x%x", v11);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"User session at service restart failed with 0x%x", v11);
        }
      }
      v26[0] = &CToken::`vftable';
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      goto LABEL_74;
    }
LABEL_77:
    WTSFreeMemory(ppSessionInfo);
  }
  else if ( *(_DWORD *)&g_dwDebugLevel )
  {
    v12 = g_lpDebugMsg;
    if ( g_lpDebugMsg )
    {
      v13 = GetLastError();
      v12(2u, L"WTSEnumerateSessions failed with 0x%x", v13);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      v14 = GetLastError();
      RedirectDebugMsg(2u, L"WTSEnumerateSessions failed with 0x%x", v14);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18004d634  push    rbp
0x18004d636  push    rbx
0x18004d637  push    rsi
0x18004d638  push    rdi
0x18004d639  push    r12
0x18004d63b  push    r13
0x18004d63d  push    r14
0x18004d63f  push    r15
0x18004d641  lea     rbp, [rsp-1Fh]
0x18004d646  sub     rsp, 0E8h
0x18004d64d  mov     r14, rcx
0x18004d650  mov     r12d, 4
0x18004d656  xor     r15d, r15d
0x18004d659  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x18004d660  jz      short loc_18004D6A0
0x18004d662  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004d669  test    rax, rax
0x18004d66c  jz      short loc_18004D67F
0x18004d66e  lea     rdx, aCgpserviceCrea; "CGPService::CreateGPSessionsAtServiceRe"...
0x18004d675  mov     ecx, r12d
0x18004d678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d67d  jmp     short loc_18004D6A0
0x18004d67f  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x18004d686  jz      short loc_18004D6A0
0x18004d688  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18004d68f  jz      short loc_18004D6A0
0x18004d691  lea     rdx, aCgpserviceCrea; "CGPService::CreateGPSessionsAtServiceRe"...
0x18004d698  mov     ecx, r12d; unsigned int
0x18004d69b  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18004d6a0  mov     [rbp+57h+var_A8], r15
0x18004d6a4  mov     [rbp+57h+var_A0], r15
0x18004d6a8  mov     [rbp+57h+var_90], r15
0x18004d6ac  mov     [rbp+57h+var_98], r15
0x18004d6b0  lea     rax, aTriggerstarted; "TriggerStarted"
0x18004d6b7  cmp     [r14+2Ch], r15d
0x18004d6bb  jz      short loc_18004D6C8
0x18004d6bd  mov     [rbp+57h+var_98], rax
0x18004d6c1  mov     dword ptr [rbp+57h+var_90], 1Eh
0x18004d6c8  mov     rcx, [r14+58h]
0x18004d6cc  mov     rax, [rcx]
0x18004d6cf  mov     r9d, 1
0x18004d6d5  mov     r8, [r14+70h]
0x18004d6d9  lea     rdx, [rbp+57h+var_A8]
0x18004d6dd  mov     rax, [rax]
0x18004d6e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d6e5  mov     r8d, eax
0x18004d6e8  mov     r13d, 2
0x18004d6ee  test    eax, eax
0x18004d6f0  jz      short loc_18004D739
0x18004d6f2  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x18004d6f9  jz      short loc_18004D739
0x18004d6fb  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004d702  test    rax, rax
0x18004d705  jz      short loc_18004D718
0x18004d707  lea     rdx, aMachineSession; "Machine session at service restart fail"...
0x18004d70e  mov     ecx, r13d
0x18004d711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d716  jmp     short loc_18004D739
0x18004d718  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x18004d71f  jz      short loc_18004D739
0x18004d721  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18004d728  jz      short loc_18004D739
0x18004d72a  lea     rdx, aMachineSession; "Machine session at service restart fail"...
0x18004d731  mov     ecx, r13d; unsigned int
0x18004d734  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18004d739  mov     [rsp+120h+ppSessionInfo], r15
0x18004d73e  mov     [rbp+57h+arg_0], r15d
0x18004d742  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x18004d749  jz      short loc_18004D789
0x18004d74b  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004d752  test    rax, rax
0x18004d755  jz      short loc_18004D768
0x18004d757  lea     rdx, aCreatingLogged; "Creating Logged on User Sessions"
0x18004d75e  mov     ecx, r12d
0x18004d761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d766  jmp     short loc_18004D789
0x18004d768  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x18004d76f  jz      short loc_18004D789
0x18004d771  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18004d778  jz      short loc_18004D789
0x18004d77a  lea     rdx, aCreatingLogged; "Creating Logged on User Sessions"
0x18004d781  mov     ecx, r12d; unsigned int
0x18004d784  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18004d789  lea     rax, [rbp+57h+arg_0]
0x18004d78d  mov     [rsp+120h+pCount], rax; pCount
0x18004d792  lea     r9, [rsp+120h+ppSessionInfo]; ppSessionInfo
0x18004d797  xor     edx, edx; Reserved
0x18004d799  xor     ecx, ecx; hServer
0x18004d79b  lea     r8d, [rdx+1]; Version
0x18004d79f  call    cs:__imp_WTSEnumerateSessionsW
0x18004d7a5  test    eax, eax
0x18004d7a7  jz      loc_18004DB87
0x18004d7ad  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x18004d7b4  jz      short loc_18004D7FC
0x18004d7b6  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004d7bd  test    rax, rax
0x18004d7c0  jz      short loc_18004D7D7
0x18004d7c2  mov     r8d, [rbp+57h+arg_0]
0x18004d7c6  lea     rdx, aSessionsFoundD; "Sessions found %d"
0x18004d7cd  mov     ecx, r12d
0x18004d7d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d7d5  jmp     short loc_18004D7FC
0x18004d7d7  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x18004d7de  jz      short loc_18004D7FC
0x18004d7e0  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18004d7e7  jz      short loc_18004D7FC
0x18004d7e9  mov     r8d, [rbp+57h+arg_0]
0x18004d7ed  lea     rdx, aSessionsFoundD; "Sessions found %d"
0x18004d7f4  mov     ecx, r12d; unsigned int
0x18004d7f7  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18004d7fc  mov     esi, r15d
0x18004d7ff  cmp     [rbp+57h+arg_0], r15d
0x18004d803  jbe     loc_18004DB7A
0x18004d809  mov     eax, esi
0x18004d80b  lea     rdi, [rax+rax*2]
0x18004d80f  mov     rcx, [rsp+120h+ppSessionInfo]
0x18004d814  test    dword ptr [rcx+rdi*8+10h], 0FFFFFFFBh
0x18004d81c  jnz     loc_18004DB6F
0x18004d822  mov     [rsp+120h+phToken], r15
0x18004d827  lea     rdx, [rsp+120h+phToken]; phToken
0x18004d82c  mov     ecx, [rcx+rdi*8]; SessionId
0x18004d82f  call    cs:__imp_WTSQueryUserToken
0x18004d835  test    eax, eax
0x18004d837  jnz     loc_18004D8CE
0x18004d83d  mov     rax, [rsp+120h+ppSessionInfo]
0x18004d842  cmp     [rax+rdi*8], r15d
0x18004d846  jz      loc_18004DB5A
0x18004d84c  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x18004d853  jz      loc_18004DB5A
0x18004d859  mov     rbx, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004d860  test    rbx, rbx
0x18004d863  jz      short loc_18004D88E
0x18004d865  call    cs:__imp_GetLastError
0x18004d86b  mov     r9d, eax
0x18004d86e  mov     r8, [rsp+120h+ppSessionInfo]
0x18004d873  mov     r8d, [r8+rdi*8]
0x18004d877  lea     rdx, aErrorQueryingU; "Error querying user token for session i"...
0x18004d87e  mov     ecx, r13d
0x18004d881  mov     rax, rbx
0x18004d884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d889  jmp     loc_18004DB5A
0x18004d88e  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x18004d895  jz      loc_18004DB5A
0x18004d89b  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18004d8a2  jz      loc_18004DB5A
0x18004d8a8  call    cs:__imp_GetLastError
0x18004d8ae  mov     r9d, eax
0x18004d8b1  mov     r8, [rsp+120h+ppSessionInfo]
0x18004d8b6  mov     r8d, [r8+rdi*8]
0x18004d8ba  lea     rdx, aErrorQueryingU; "Error querying user token for session i"...
0x18004d8c1  mov     ecx, r13d; unsigned int
0x18004d8c4  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18004d8c9  jmp     loc_18004DB5A
0x18004d8ce  xorps   xmm0, xmm0
0x18004d8d1  xor     eax, eax
0x18004d8d3  movups  [rbp+57h+var_D0], xmm0
0x18004d8d7  movups  [rbp+57h+var_C0], xmm0
0x18004d8db  mov     [rbp+57h+var_B0], rax
0x18004d8df  mov     rbx, [rsp+120h+phToken]
0x18004d8e4  mov     [rbp+57h+ReturnLength], r15d
0x18004d8e8  mov     [rbp+57h+arg_18], r15d
0x18004d8ec  mov     [rbp+57h+TokenInformation], r15d
0x18004d8f0  mov     [rsp+120h+var_D8], r15
0x18004d8f5  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18004d8f9  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18004d8fd  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004d901  mov     [rsp+120h+hObject], r15
0x18004d906  lea     rax, [rbp+57h+ReturnLength]
0x18004d90a  mov     [rsp+120h+pCount], rax; ReturnLength
0x18004d90f  mov     r9d, r12d; TokenInformationLength
0x18004d912  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18004d916  mov     edx, 12h; TokenInformationClass
0x18004d91b  mov     rcx, rbx; TokenHandle
0x18004d91e  call    cs:__imp_NtQueryInformationToken
0x18004d924  mov     r8d, eax
0x18004d927  test    eax, eax
0x18004d929  js      short loc_18004D9A8
0x18004d92b  cmp     [rbp+57h+TokenInformation], r13d
0x18004d92f  jz      short loc_18004D966
0x18004d931  lea     rax, [rbp+57h+ReturnLength]
0x18004d935  mov     rcx, rbx; TokenHandle
0x18004d938  mov     [rsp+120h+pCount], rax; ReturnLength
0x18004d93d  cmp     [rbp+57h+TokenInformation], 1
0x18004d941  jnz     loc_18004D9D3
0x18004d947  mov     r9d, r12d; TokenInformationLength
0x18004d94a  lea     r8, [rbp+57h+arg_18]; TokenInformation
0x18004d94e  mov     edx, 14h; TokenInformationClass
0x18004d953  call    cs:__imp_NtQueryInformationToken
0x18004d959  mov     r8d, eax
0x18004d95c  test    eax, eax
0x18004d95e  js      short loc_18004D9A8
0x18004d960  cmp     [rbp+57h+arg_18], r15d
0x18004d964  jz      short loc_18004D9A8
0x18004d966  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18004d96d  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x18004d971  mov     [rbp+57h+ObjectAttributes.Attributes], r15d
0x18004d975  mov     [rbp+57h+ObjectAttributes.ObjectName], r15
0x18004d979  xorps   xmm0, xmm0
0x18004d97c  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004d981  lea     rax, [rsp+120h+hObject]
0x18004d986  mov     [rsp+120h+NewTokenHandle], rax; NewTokenHandle
0x18004d98b  mov     dword ptr [rsp+120h+pCount], 1; TokenType
0x18004d993  xor     r9d, r9d; EffectiveOnly
0x18004d996  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18004d99a  xor     edx, edx; DesiredAccess
0x18004d99c  mov     rcx, rbx; ExistingTokenHandle
0x18004d99f  call    cs:__imp_NtDuplicateToken
0x18004d9a5  mov     r8d, eax
0x18004d9a8  test    r8d, r8d
0x18004d9ab  jz      short loc_18004DA28
0x18004d9ad  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x18004d9b4  jz      short loc_18004DA1C
0x18004d9b6  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004d9bd  test    rax, rax
0x18004d9c0  jz      short loc_18004D9FB
0x18004d9c2  lea     rdx, aCreategpsessio; "CreateGPSessionsAtServiceRestart: LUAGe"...
0x18004d9c9  mov     ecx, r13d
0x18004d9cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d9d1  jmp     short loc_18004DA1C
0x18004d9d3  mov     r9d, 8; TokenInformationLength
0x18004d9d9  lea     r8, [rsp+120h+var_D8]; TokenInformation
0x18004d9de  lea     edx, [r9+0Bh]; TokenInformationClass
0x18004d9e2  call    cs:__imp_NtQueryInformationToken
0x18004d9e8  mov     r8d, eax
0x18004d9eb  test    eax, eax
0x18004d9ed  js      short loc_18004D9A8
0x18004d9ef  mov     rax, [rsp+120h+var_D8]
0x18004d9f4  mov     [rsp+120h+hObject], rax
0x18004d9f9  jmp     short loc_18004D9A8
0x18004d9fb  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x18004da02  jz      short loc_18004DA1C
0x18004da04  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18004da0b  jz      short loc_18004DA1C
0x18004da0d  lea     rdx, aCreategpsessio; "CreateGPSessionsAtServiceRestart: LUAGe"...
0x18004da14  mov     ecx, r13d; unsigned int
0x18004da17  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18004da1c  xor     edx, edx
0x18004da1e  lea     rcx, [rsp+120h+hObject]
0x18004da23  call    ??4XHandle@@QEAAXPEAX@Z; XHandle::operator=(void *)
0x18004da28  mov     rcx, [rsp+120h+phToken]
0x18004da2d  mov     rax, [rsp+120h+hObject]
0x18004da32  test    rax, rax
0x18004da35  cmovnz  rcx, rax
0x18004da39  lea     rbx, ??_7CToken@@6B@; const CToken::`vftable'
0x18004da40  mov     [rbp+57h+var_88], rbx
0x18004da44  mov     [rbp+57h+var_80], rcx
0x18004da48  xorps   xmm0, xmm0
0x18004da4b  xor     eax, eax
0x18004da4d  movups  [rbp+57h+var_D0], xmm0
0x18004da51  movups  [rbp+57h+var_C0], xmm0
0x18004da55  mov     [rbp+57h+var_B0], rax
0x18004da59  mov     rax, [rsp+120h+ppSessionInfo]
0x18004da5e  mov     r8d, [rax+rdi*8]
0x18004da62  mov     dword ptr [rbp+57h+var_D0+8], r8d
0x18004da66  mov     qword ptr [rbp+57h+var_C0], r15
0x18004da6a  mov     dword ptr [rbp+57h+var_C0+8], r15d
0x18004da6e  cmp     [r14+2Ch], r15d
0x18004da72  jz      short loc_18004DA86
0x18004da74  lea     rax, aTriggerstarted; "TriggerStarted"
0x18004da7b  mov     qword ptr [rbp+57h+var_C0], rax
0x18004da7f  mov     dword ptr [rbp+57h+var_C0+8], 1Eh
0x18004da86  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x18004da8d  jz      short loc_18004DACD
0x18004da8f  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004da96  test    rax, rax
0x18004da99  jz      short loc_18004DAAC
0x18004da9b  lea     rdx, aCreatingUserSe; "Creating User Session for session %d"
0x18004daa2  mov     ecx, r12d
0x18004daa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004daaa  jmp     short loc_18004DACD
0x18004daac  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x18004dab3  jz      short loc_18004DACD
0x18004dab5  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18004dabc  jz      short loc_18004DACD
0x18004dabe  lea     rdx, aCreatingUserSe; "Creating User Session for session %d"
0x18004dac5  mov     ecx, r12d; unsigned int
0x18004dac8  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18004dacd  mov     rcx, [r14+58h]
0x18004dad1  mov     rax, [rcx]
0x18004dad4  mov     dword ptr [rsp+120h+pCount], 1
0x18004dadc  mov     r9, [r14+70h]
0x18004dae0  lea     r8, [rbp+57h+var_D0]
0x18004dae4  lea     rdx, [rbp+57h+var_88]
0x18004dae8  mov     rax, [rax+8]
0x18004daec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004daf1  mov     r8d, eax
0x18004daf4  test    eax, eax
0x18004daf6  jz      short loc_18004DB40
0x18004daf8  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x18004daff  jz      short loc_18004DB40
0x18004db01  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18004db08  test    rax, rax
0x18004db0b  jz      short loc_18004DB1E
0x18004db0d  lea     rdx, aUserSessionAtS; "User session at service restart failed "...
0x18004db14  mov     ecx, r13d
0x18004db17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004db1c  jmp     short loc_18004DB40
0x18004db1e  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x18004db25  jz      short loc_18004DB40
0x18004db27  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
  ... truncated ...
```
