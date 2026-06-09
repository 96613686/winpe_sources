# NegpAsyncUpdateWorker(void *)

- ea: `0x18005b9d0`
- end: `0x18005c13f`
- name: `?NegpAsyncUpdateWorker@@YAKPEAX@Z`
- size: `1903`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800093b0`
- `0x180009410`
- `0x180009838`
- `0x18000c300`
- `0x180011278`
- `0x1800268d8`
- `0x1800284d4`
- `0x18005b9d0`
- `0x18005c150`
- `0x1800ada18`
- `0x1800b86d0`
- `0x1800c6eac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005ba53`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005ba53`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005c0ad`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005c0ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c0d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c0d9`
- `ntdll!RtlNtStatusToDosError` at `0x18005bb0e`
- `ntdll!RtlNtStatusToDosError` at `0x18005bb0e`
- `ntdll!NtClose` at `0x18005baef`
- `ntdll!NtClose` at `0x18005c0c8`
- `ntdll!NtClose` at `0x18005baef`
- `ntdll!NtClose` at `0x18005c0c8`
- `ntdll!NtSetInformationThread` at `0x18005bb73`
- `ntdll!NtSetInformationThread` at `0x18005bc69`
- `ntdll!NtSetInformationThread` at `0x18005c121`
- `ntdll!NtSetInformationThread` at `0x18005bb73`
- `ntdll!NtSetInformationThread` at `0x18005bc69`
- `ntdll!NtSetInformationThread` at `0x18005c121`
- `SspiCli!SeciFreeCallContext` at `0x18005c0fb`
- `SspiCli!SeciFreeCallContext` at `0x18005c0fb`
- `SspiCli!SeciAllocateAndSetCallFlags` at `0x18005bb9b`
- `SspiCli!SeciAllocateAndSetCallFlags` at `0x18005bb9b`
- `SspiCli!LsaConnectUntrusted` at `0x18005ba74`
- `SspiCli!LsaConnectUntrusted` at `0x18005ba74`
- `SspiCli!LsaLogonUser` at `0x18005bc30`
- `SspiCli!LsaLogonUser` at `0x18005bc30`
- `SspiCli!LsaFreeReturnBuffer` at `0x18005bf18`
- `SspiCli!LsaFreeReturnBuffer` at `0x18005c00c`
- `SspiCli!LsaFreeReturnBuffer` at `0x18005c0ea`
- `SspiCli!LsaFreeReturnBuffer` at `0x18005bf18`
- `SspiCli!LsaFreeReturnBuffer` at `0x18005c00c`
- `SspiCli!LsaFreeReturnBuffer` at `0x18005c0ea`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18005bf77`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18005bf77`
- `SspiCli!LsaCallAuthenticationPackage` at `0x18005bd41`
- `SspiCli!LsaCallAuthenticationPackage` at `0x18005bee9`
- `SspiCli!LsaCallAuthenticationPackage` at `0x18005bd41`
- `SspiCli!LsaCallAuthenticationPackage` at `0x18005bee9`

## pseudocode

```c
ULONG __fastcall NegpAsyncUpdateWorker(char *Parameter)
{
  void *v2; // rcx
  int v3; // r13d
  struct _LSAP_LOGON_SESSION *v4; // rsi
  NTSTATUS v5; // eax
  int v6; // ebx
  LsaHandleCache *v7; // rcx
  void *v8; // rcx
  void *v9; // rdx
  _DWORD *v11; // r12
  SECURITY_LOGON_TYPE v12; // r8d
  int v13; // eax
  struct _LSAP_LOGON_SESSION *v14; // rax
  __int64 v15; // rax
  struct _LSAP_LOGON_SESSION *LogonSession; // rax
  __int64 v17; // rdx
  unsigned __int64 v18; // r9
  struct _NEG_LOGON_SESSION *v19; // rax
  struct _RTL_BALANCED_NODE *v20; // rdi
  void *v21; // rcx
  struct _LUID LogonId; // [rsp+70h] [rbp-90h] BYREF
  int ProtocolStatus; // [rsp+78h] [rbp-88h] BYREF
  int SubStatus; // [rsp+7Ch] [rbp-84h] BYREF
  ULONG ReturnBufferLength; // [rsp+80h] [rbp-80h] BYREF
  int v26; // [rsp+84h] [rbp-7Ch] BYREF
  PVOID ProtocolReturnBuffer; // [rsp+88h] [rbp-78h] BYREF
  ULONG ProfileBufferLength; // [rsp+90h] [rbp-70h] BYREF
  void *LsaHandle; // [rsp+98h] [rbp-68h] BYREF
  HANDLE hObject; // [rsp+A0h] [rbp-60h] BYREF
  PVOID Buffer; // [rsp+A8h] [rbp-58h] BYREF
  __int64 ThreadInformation; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE ProtocolSubmitBuffer[24]; // [rsp+B8h] [rbp-48h] BYREF
  struct _QUOTA_LIMITS Quotas; // [rsp+D0h] [rbp-30h] BYREF

  Buffer = 0;
  ProfileBufferLength = 0;
  v2 = (void *)*((_QWORD *)Parameter + 5);
  v3 = 0;
  LogonId = 0;
  v4 = 0;
  hObject = 0;
  SubStatus = 0;
  ThreadInformation = 0;
  v26 = 0;
  ProtocolStatus = 0;
  ReturnBufferLength = 0;
  ProtocolReturnBuffer = 0;
  memset(&Quotas, 0, sizeof(Quotas));
  memset(ProtocolSubmitBuffer, 0, sizeof(ProtocolSubmitBuffer));
  if ( v2 )
    WaitForSingleObject(v2, 0xFFFFFFFF);
  if ( !NegpGlobalLsaHandle )
  {
    LsaHandle = 0;
    v5 = LsaConnectUntrusted(&LsaHandle);
    v6 = v5;
    if ( v5 < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v17 = 74;
        goto LABEL_55;
      }
      goto LABEL_6;
    }
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&NegpGlobalLsaHandle, (signed __int64)LsaHandle, 0) )
      LsaDeregisterLogonProcess(LsaHandle);
  }
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids);
  v5 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, Parameter + 24, 8u);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v17 = 76;
LABEL_55:
      WPP_SF_d(*((_QWORD *)v7 + 2), v17, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids, (unsigned int)v5);
    }
  }
  else
  {
    v5 = SeciAllocateAndSetCallFlags(((*((_DWORD *)Parameter + 1) & 1) << 17) | 0x800u, &v26);
    v6 = v5;
    if ( v5 < 0 )
    {
      v3 = 1;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v17 = 77;
        goto LABEL_55;
      }
    }
    else
    {
      v11 = Parameter + 32;
      v12 = *(_DWORD *)Parameter;
      LogonId = (struct _LUID)*((_QWORD *)Parameter + 4);
      v6 = LsaLogonUser(
             NegpGlobalLsaHandle,
             &NegpGlboalOriginName,
             v12,
             NegPackageId,
             *((PVOID *)Parameter + 1),
             *((_DWORD *)Parameter + 4),
             0,
             &NegpGlobalSourceContext,
             &Buffer,
             &ProfileBufferLength,
             &LogonId,
             &hObject,
             &Quotas,
             &SubStatus);
      v13 = SubStatus;
      if ( v6 >= 0 && SubStatus >= 0 )
        goto LABEL_27;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          78,
          WPP_ba8e463a02353fcee7069faa518abd92_Traceguids,
          (unsigned int)v6,
          SubStatus);
        v13 = SubStatus;
      }
      if ( v6 >= 0 )
LABEL_27:
        v6 = v13;
      NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
      if ( v6 >= 0 )
      {
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_DDDD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            79,
            WPP_ba8e463a02353fcee7069faa518abd92_Traceguids,
            *((unsigned int *)Parameter + 9),
            *v11,
            LogonId.HighPart,
            LogonId.LowPart);
        }
        LsaIUpdateLogonSession((struct _LUID *)Parameter + 4, &LogonId);
        if ( (Parameter[4] & 2) == 0 )
        {
          *(struct _LUID *)&ProtocolSubmitBuffer[4] = LogonId;
          *(_QWORD *)&ProtocolSubmitBuffer[12] = *(_QWORD *)v11;
          *(_DWORD *)ProtocolSubmitBuffer = 1026;
          *(_DWORD *)&ProtocolSubmitBuffer[20] = 1;
          v14 = LsapLocateLogonSession(&LogonId);
          v4 = v14;
          if ( v14 )
          {
            if ( !*((_QWORD *)v14 + 15)
              || *((_DWORD *)v14 + 30) == LogonId.LowPart && *((_DWORD *)v14 + 31) == LogonId.HighPart )
            {
              HIDWORD(v15) = *(_DWORD *)&ProtocolSubmitBuffer[8];
            }
            else
            {
              v15 = *((_QWORD *)v14 + 15);
              *(_QWORD *)&ProtocolSubmitBuffer[4] = *((_QWORD *)v4 + 15);
            }
            if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_DDDD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                80,
                WPP_ba8e463a02353fcee7069faa518abd92_Traceguids,
                *(unsigned int *)&ProtocolSubmitBuffer[16],
                *(_DWORD *)&ProtocolSubmitBuffer[12],
                HIDWORD(v15),
                *(_DWORD *)&ProtocolSubmitBuffer[4]);
            }
            v6 = LsaCallAuthenticationPackage(
                   NegpGlobalLsaHandle,
                   NegPackageId,
                   ProtocolSubmitBuffer,
                   0x18u,
                   &ProtocolReturnBuffer,
                   &ReturnBufferLength,
                   &ProtocolStatus);
            if ( (v6 < 0 || ProtocolStatus < 0)
              && WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                81,
                WPP_ba8e463a02353fcee7069faa518abd92_Traceguids,
                (unsigned int)v6,
                ProtocolStatus);
            }
            if ( ProtocolReturnBuffer )
            {
              LsaFreeReturnBuffer(ProtocolReturnBuffer);
              ProtocolReturnBuffer = 0;
            }
            ReturnBufferLength = 0;
            if ( *(_QWORD *)&ProtocolSubmitBuffer[4] != LogonId )
            {
              LsapReleaseLogonSession(v4);
              LogonSession = LsapLocateLogonSession((struct _LUID *)Parameter + 4);
              v4 = LogonSession;
              if ( LogonSession )
              {
                if ( *((_QWORD *)LogonSession + 15) )
                {
                  v18 = *((_QWORD *)LogonSession + 15);
                  *(_QWORD *)&ProtocolSubmitBuffer[12] = v18;
                  *(struct _LUID *)&ProtocolSubmitBuffer[4] = LogonId;
                  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    WPP_SF_DDDD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      82,
                      WPP_ba8e463a02353fcee7069faa518abd92_Traceguids,
                      HIDWORD(v18),
                      *(_DWORD *)&ProtocolSubmitBuffer[12],
                      LogonId.HighPart,
                      LogonId.LowPart);
                  }
                  v6 = LsaCallAuthenticationPackage(
                         NegpGlobalLsaHandle,
                         NegPackageId,
                         ProtocolSubmitBuffer,
                         0x18u,
                         &ProtocolReturnBuffer,
                         &ReturnBufferLength,
                         &ProtocolStatus);
                  if ( (v6 < 0 || ProtocolStatus < 0)
                    && WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    WPP_SF_Dd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      83,
                      WPP_ba8e463a02353fcee7069faa518abd92_Traceguids,
                      (unsigned int)v6,
                      ProtocolStatus);
                  }
                  if ( ProtocolReturnBuffer )
                    LsaFreeReturnBuffer(ProtocolReturnBuffer);
                }
              }
              else
              {
                v6 = -1073741729;
              }
            }
          }
          else
          {
            v6 = -1073741729;
          }
        }
      }
    }
  }
LABEL_6:
  if ( *((_QWORD *)Parameter + 4) )
  {
    v19 = NegpLocateLogonSession((struct _LUID *)Parameter + 4);
    v20 = (struct _RTL_BALANCED_NODE *)v19;
    if ( v19 )
    {
      v21 = (void *)*((_QWORD *)v19 + 12);
      if ( v21 )
        SetEvent(v21);
      NegpDerefLogonSession(v20, 0);
    }
  }
  v8 = (void *)*((_QWORD *)Parameter + 5);
  if ( v8 )
    NtClose(v8);
  if ( hObject )
    CloseHandle(hObject);
  if ( Buffer )
    LsaFreeReturnBuffer(Buffer);
  if ( v26 )
    SeciFreeCallContext();
  if ( v3 )
    NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
  NtClose(*((HANDLE *)Parameter + 3));
  LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)Parameter, v9);
  if ( v4 )
    LsapReleaseLogonSession(v4);
  return RtlNtStatusToDosError(v6);
}

```

## disassembly

```asm
0x18005b9d0  push    rbp
0x18005b9d2  push    rbx
0x18005b9d3  push    rsi
0x18005b9d4  push    rdi
0x18005b9d5  push    r12
0x18005b9d7  push    r13
0x18005b9d9  push    r14
0x18005b9db  push    r15
0x18005b9dd  lea     rbp, [rsp-18h]
0x18005b9e2  sub     rsp, 118h
0x18005b9e9  mov     rax, cs:__security_cookie
0x18005b9f0  xor     rax, rsp
0x18005b9f3  mov     [rbp+50h+var_50], rax
0x18005b9f7  xor     r12d, r12d
0x18005b9fa  xorps   xmm0, xmm0
0x18005b9fd  xor     eax, eax
0x18005b9ff  mov     [rbp+50h+Buffer], r12
0x18005ba03  mov     r14, rcx
0x18005ba06  mov     [rbp+50h+var_C0], r12d
0x18005ba0a  mov     rcx, [rcx+28h]; hHandle
0x18005ba0e  mov     r13d, r12d
0x18005ba11  mov     qword ptr [rsp+150h+var_E0.LowPart], r12
0x18005ba16  mov     esi, r12d
0x18005ba19  mov     [rbp+50h+hObject], r12
0x18005ba1d  mov     [rsp+150h+var_D4], r12d
0x18005ba22  mov     [rbp+50h+ThreadInformation], r12
0x18005ba26  mov     [rbp+50h+var_CC], r12d
0x18005ba2a  mov     [rbp+50h+var_88], rax
0x18005ba2e  mov     [rsp+150h+ProtocolStatus], r12d
0x18005ba33  mov     [rbp+50h+ReturnBufferLength], r12d
0x18005ba37  mov     [rbp+50h+ProtocolReturnBuffer], r12
0x18005ba3b  movups  xmmword ptr [rbp+50h+var_80.PagedPoolLimit], xmm0
0x18005ba3f  movups  xmmword ptr [rbp+50h+var_80.MinimumWorkingSetSize], xmm0
0x18005ba43  movups  xmmword ptr [rbp+50h+var_80.PagefileLimit], xmm0
0x18005ba47  movups  [rbp+50h+ProtocolSubmitBuffer], xmm0
0x18005ba4b  test    rcx, rcx
0x18005ba4e  jz      short loc_18005BA5F
0x18005ba50  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18005ba53  call    cs:__imp_WaitForSingleObject
0x18005ba5a  nop     dword ptr [rax+rax+00h]
0x18005ba5f  cmp     cs:?NegpGlobalLsaHandle@@3PEAXEA, r12; void * NegpGlobalLsaHandle
0x18005ba66  jnz     loc_18005BB3B
0x18005ba6c  lea     rcx, [rbp+50h+LsaHandle]; LsaHandle
0x18005ba70  mov     [rbp+50h+LsaHandle], r12
0x18005ba74  call    cs:__imp_LsaConnectUntrusted
0x18005ba7b  nop     dword ptr [rax+rax+00h]
0x18005ba80  mov     ebx, eax
0x18005ba82  test    eax, eax
0x18005ba84  jns     loc_18005BF5E
0x18005ba8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ba91  lea     rdi, WPP_GLOBAL_Control
0x18005ba98  cmp     rcx, rdi
0x18005ba9b  jnz     loc_18005BF43
0x18005baa1  mov     eax, [r14+24h]
0x18005baa5  lea     rcx, [r14+20h]; struct _LUID *
0x18005baa9  or      eax, [rcx]
0x18005baab  jnz     loc_18005C093
0x18005bab1  mov     rcx, [r14+28h]; Handle
0x18005bab5  test    rcx, rcx
0x18005bab8  jnz     loc_18005C0C8
0x18005babe  mov     rcx, [rbp+50h+hObject]; hObject
0x18005bac2  test    rcx, rcx
0x18005bac5  jnz     loc_18005C0D9
0x18005bacb  mov     rcx, [rbp+50h+Buffer]; Buffer
0x18005bacf  test    rcx, rcx
0x18005bad2  jnz     loc_18005C0EA
0x18005bad8  cmp     [rbp+50h+var_CC], r12d
0x18005badc  jnz     loc_18005C0FB
0x18005bae2  test    r13d, r13d
0x18005bae5  jnz     loc_18005C10C
0x18005baeb  mov     rcx, [r14+18h]; Handle
0x18005baef  call    cs:__imp_NtClose
0x18005baf6  nop     dword ptr [rax+rax+00h]
0x18005bafb  mov     rcx, r14; struct _RTL_BALANCED_NODE *
0x18005bafe  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x18005bb03  test    rsi, rsi
0x18005bb06  jnz     loc_18005C132
0x18005bb0c  mov     ecx, ebx; Status
0x18005bb0e  call    cs:__imp_RtlNtStatusToDosError
0x18005bb15  nop     dword ptr [rax+rax+00h]
0x18005bb1a  mov     rcx, [rbp+50h+var_50]
0x18005bb1e  xor     rcx, rsp; StackCookie
0x18005bb21  call    __security_check_cookie
0x18005bb26  add     rsp, 118h
0x18005bb2d  pop     r15
0x18005bb2f  pop     r14
0x18005bb31  pop     r13
0x18005bb33  pop     r12
0x18005bb35  pop     rdi
0x18005bb36  pop     rsi
0x18005bb37  pop     rbx
0x18005bb38  pop     rbp
0x18005bb39  retn
0x18005bb3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bb42  lea     rdi, WPP_GLOBAL_Control
0x18005bb49  lea     r15, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids
0x18005bb50  cmp     rcx, rdi
0x18005bb53  jz      short loc_18005BB5F
0x18005bb55  test    byte ptr [rcx+1Ch], 2
0x18005bb59  jnz     loc_18005BF88
0x18005bb5f  mov     edx, 5; ThreadInformationClass
0x18005bb64  lea     r8, [r14+18h]; ThreadInformation
0x18005bb68  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18005bb6f  lea     r9d, [rdx+3]; ThreadInformationLength
0x18005bb73  call    cs:__imp_NtSetInformationThread
0x18005bb7a  nop     dword ptr [rax+rax+00h]
0x18005bb7f  mov     ebx, eax
0x18005bb81  test    eax, eax
0x18005bb83  js      loc_18005BE56
0x18005bb89  mov     ecx, [r14+4]
0x18005bb8d  lea     rdx, [rbp+50h+var_CC]
0x18005bb91  and     ecx, 1
0x18005bb94  shl     ecx, 11h
0x18005bb97  bts     ecx, 0Bh
0x18005bb9b  call    cs:__imp_SeciAllocateAndSetCallFlags
0x18005bba2  nop     dword ptr [rax+rax+00h]
0x18005bba7  mov     ebx, eax
0x18005bba9  test    eax, eax
0x18005bbab  js      loc_18005BF9E
0x18005bbb1  mov     r9d, dword ptr cs:?NegPackageId@@3_KA; AuthenticationPackage
0x18005bbb8  lea     r12, [r14+20h]
0x18005bbbc  mov     rax, [r12]
0x18005bbc0  lea     rdx, ?NegpGlboalOriginName@@3U_STRING@@A; OriginName
0x18005bbc7  mov     r8d, [r14]; LogonType
0x18005bbca  mov     rcx, cs:?NegpGlobalLsaHandle@@3PEAXEA; LsaHandle
0x18005bbd1  mov     qword ptr [rsp+150h+var_E0.LowPart], rax
0x18005bbd6  lea     rax, [rsp+150h+var_D4]
0x18005bbdb  mov     [rsp+150h+SubStatus], rax; SubStatus
0x18005bbe0  lea     rax, [rbp+50h+var_80]
0x18005bbe4  mov     [rsp+150h+Quotas], rax; Quotas
0x18005bbe9  lea     rax, [rbp+50h+hObject]
0x18005bbed  mov     [rsp+150h+Token], rax; Token
0x18005bbf2  lea     rax, [rsp+150h+var_E0]
0x18005bbf7  mov     [rsp+150h+LogonId], rax; LogonId
0x18005bbfc  lea     rax, [rbp+50h+var_C0]
0x18005bc00  mov     [rsp+150h+ProfileBufferLength], rax; ProfileBufferLength
0x18005bc05  lea     rax, [rbp+50h+Buffer]
0x18005bc09  mov     [rsp+150h+ProfileBuffer], rax; ProfileBuffer
0x18005bc0e  lea     rax, ?NegpGlobalSourceContext@@3U_TOKEN_SOURCE@@A; _TOKEN_SOURCE NegpGlobalSourceContext
0x18005bc15  mov     [rsp+150h+SourceContext], rax; SourceContext
0x18005bc1a  mov     eax, [r14+10h]
0x18005bc1e  mov     [rsp+150h+LocalGroups], rsi; LocalGroups
0x18005bc23  mov     [rsp+150h+AuthenticationInformationLength], eax; AuthenticationInformationLength
0x18005bc27  mov     rax, [r14+8]
0x18005bc2b  mov     [rsp+150h+AuthenticationInformation], rax; AuthenticationInformation
0x18005bc30  call    cs:__imp_LsaLogonUser
0x18005bc37  nop     dword ptr [rax+rax+00h]
0x18005bc3c  mov     ebx, eax
0x18005bc3e  mov     eax, [rsp+150h+var_D4]
0x18005bc42  test    ebx, ebx
0x18005bc44  js      loc_18005BFC7
0x18005bc4a  test    eax, eax
0x18005bc4c  js      loc_18005BFC7
0x18005bc52  mov     ebx, eax
0x18005bc54  mov     r9d, 8; ThreadInformationLength
0x18005bc5a  lea     r8, [rbp+50h+ThreadInformation]; ThreadInformation
0x18005bc5e  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18005bc65  lea     edx, [r9-3]; ThreadInformationClass
0x18005bc69  call    cs:__imp_NtSetInformationThread
0x18005bc70  nop     dword ptr [rax+rax+00h]
0x18005bc75  test    ebx, ebx
0x18005bc77  js      loc_18005BD86
0x18005bc7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bc84  cmp     rcx, rdi
0x18005bc87  jnz     loc_18005BDBA
0x18005bc8d  lea     rdx, [rsp+150h+var_E0]; struct _LUID *
0x18005bc92  mov     rcx, r12; struct _LUID *
0x18005bc95  call    LsaIUpdateLogonSession
0x18005bc9a  test    byte ptr [r14+4], 2
0x18005bc9f  jnz     loc_18005BD86
0x18005bca5  mov     rax, qword ptr [rsp+150h+var_E0.LowPart]
0x18005bcaa  lea     rcx, [rsp+150h+var_E0]; struct _LUID *
0x18005bcaf  mov     qword ptr [rbp+50h+ProtocolSubmitBuffer+4], rax
0x18005bcb3  mov     rax, [r12]
0x18005bcb7  mov     qword ptr [rbp+50h+ProtocolSubmitBuffer+0Ch], rax
0x18005bcbb  mov     dword ptr [rbp+50h+ProtocolSubmitBuffer], 402h
0x18005bcc2  mov     dword ptr [rbp+50h+var_88+4], 1
0x18005bcc9  call    ?LsapLocateLogonSession@@YAPEAU_LSAP_LOGON_SESSION@@PEAU_LUID@@@Z; LsapLocateLogonSession(_LUID *)
0x18005bcce  mov     rsi, rax
0x18005bcd1  test    rax, rax
0x18005bcd4  jz      loc_18005C002
0x18005bcda  mov     ecx, [rax+78h]
0x18005bcdd  mov     edx, [rax+7Ch]
0x18005bce0  mov     eax, edx
0x18005bce2  or      eax, ecx
0x18005bce4  jz      short loc_18005BCFA
0x18005bce6  cmp     ecx, [rsp+150h+var_E0.LowPart]
0x18005bcea  jnz     loc_18005BF29
0x18005bcf0  cmp     edx, [rsp+150h+var_E0.HighPart]
0x18005bcf4  jnz     loc_18005BF29
0x18005bcfa  mov     rax, qword ptr [rbp+50h+ProtocolSubmitBuffer+4]
0x18005bcfe  mov     r10, cs:WPP_GLOBAL_Control
0x18005bd05  cmp     r10, rdi
0x18005bd08  jnz     loc_18005BDF6
0x18005bd0e  mov     edx, dword ptr cs:?NegPackageId@@3_KA; AuthenticationPackage
0x18005bd14  lea     rax, [rsp+150h+ProtocolStatus]
0x18005bd19  mov     rcx, cs:?NegpGlobalLsaHandle@@3PEAXEA; LsaHandle
0x18005bd20  lea     r8, [rbp+50h+ProtocolSubmitBuffer]; ProtocolSubmitBuffer
0x18005bd24  mov     [rsp+150h+LocalGroups], rax; ProtocolStatus
0x18005bd29  mov     r9d, 18h; SubmitBufferLength
0x18005bd2f  lea     rax, [rbp+50h+ReturnBufferLength]
0x18005bd33  mov     qword ptr [rsp+150h+AuthenticationInformationLength], rax; ReturnBufferLength
0x18005bd38  lea     rax, [rbp+50h+ProtocolReturnBuffer]
0x18005bd3c  mov     [rsp+150h+AuthenticationInformation], rax; ProtocolReturnBuffer
0x18005bd41  call    cs:__imp_LsaCallAuthenticationPackage
0x18005bd48  nop     dword ptr [rax+rax+00h]
0x18005bd4d  mov     ebx, eax
0x18005bd4f  mov     eax, [rsp+150h+ProtocolStatus]
0x18005bd53  test    ebx, ebx
0x18005bd55  js      short loc_18005BD8E
0x18005bd57  test    eax, eax
0x18005bd59  js      short loc_18005BD8E
0x18005bd5b  mov     rcx, [rbp+50h+ProtocolReturnBuffer]; Buffer
0x18005bd5f  test    rcx, rcx
0x18005bd62  jnz     loc_18005C00C
0x18005bd68  mov     eax, [rsp+150h+var_E0.LowPart]
0x18005bd6c  mov     [rbp+50h+ReturnBufferLength], r13d
0x18005bd70  cmp     dword ptr [rbp+50h+ProtocolSubmitBuffer+4], eax
0x18005bd73  jnz     loc_18005BE31
0x18005bd79  mov     eax, [rsp+150h+var_E0.HighPart]
0x18005bd7d  cmp     dword ptr [rbp+50h+ProtocolSubmitBuffer+8], eax
0x18005bd80  jnz     loc_18005BE31
0x18005bd86  xor     r12d, r12d
0x18005bd89  jmp     loc_18005BAA1
0x18005bd8e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bd95  cmp     rcx, rdi
0x18005bd98  jz      short loc_18005BD5B
0x18005bd9a  test    byte ptr [rcx+1Ch], 2
0x18005bd9e  jz      short loc_18005BD5B
0x18005bda0  mov     rcx, [rcx+10h]
0x18005bda4  mov     edx, 51h ; 'Q'
0x18005bda9  mov     r9d, ebx
0x18005bdac  mov     dword ptr [rsp+150h+AuthenticationInformation], eax
0x18005bdb0  mov     r8, r15
0x18005bdb3  call    WPP_SF_Dd
0x18005bdb8  jmp     short loc_18005BD5B
0x18005bdba  test    byte ptr [rcx+1Ch], 2
0x18005bdbe  jz      loc_18005BC8D
0x18005bdc4  mov     eax, [rsp+150h+var_E0.LowPart]
0x18005bdc8  mov     edx, 4Fh ; 'O'
0x18005bdcd  mov     r9d, [r14+24h]
0x18005bdd1  mov     r8, r15
0x18005bdd4  mov     rcx, [rcx+10h]
0x18005bdd8  mov     dword ptr [rsp+150h+LocalGroups], eax
0x18005bddc  mov     eax, [rsp+150h+var_E0.HighPart]
0x18005bde0  mov     [rsp+150h+AuthenticationInformationLength], eax
0x18005bde4  mov     eax, [r12]
0x18005bde8  mov     dword ptr [rsp+150h+AuthenticationInformation], eax
0x18005bdec  call    WPP_SF_DDDD
0x18005bdf1  jmp     loc_18005BC8D
0x18005bdf6  test    byte ptr [r10+1Ch], 2
0x18005bdfb  jz      loc_18005BD0E
0x18005be01  mov     ecx, dword ptr [rbp+50h+ProtocolSubmitBuffer+4]
0x18005be04  mov     edx, 50h ; 'P'
0x18005be09  mov     r9d, dword ptr [rbp+50h+var_88]
0x18005be0d  mov     r8, r15
0x18005be10  mov     dword ptr [rsp+150h+LocalGroups], ecx
0x18005be14  mov     rcx, [r10+10h]
0x18005be18  shr     rax, 20h
0x18005be1c  mov     [rsp+150h+AuthenticationInformationLength], eax
0x18005be20  mov     eax, dword ptr [rbp+50h+ProtocolSubmitBuffer+0Ch]
0x18005be23  mov     dword ptr [rsp+150h+AuthenticationInformation], eax
0x18005be27  call    WPP_SF_DDDD
0x18005be2c  jmp     loc_18005BD0E
0x18005be31  mov     rcx, rsi; struct _LSAP_LOGON_SESSION *
0x18005be34  call    ?LsapReleaseLogonSession@@YAXPEAU_LSAP_LOGON_SESSION@@@Z; LsapReleaseLogonSession(_LSAP_LOGON_SESSION *)
0x18005be39  mov     rcx, r12; struct _LUID *
0x18005be3c  call    ?LsapLocateLogonSession@@YAPEAU_LSAP_LOGON_SESSION@@PEAU_LUID@@@Z; LsapLocateLogonSession(_LUID *)
0x18005be41  xor     r12d, r12d
0x18005be44  mov     rsi, rax
0x18005be47  test    rax, rax
0x18005be4a  jnz     short loc_18005BE89
0x18005be4c  mov     ebx, 0C000005Fh
0x18005be51  jmp     loc_18005BAA1
0x18005be56  mov     rcx, cs:WPP_GLOBAL_Control
0x18005be5d  cmp     rcx, rdi
0x18005be60  jz      loc_18005BAA1
0x18005be66  test    byte ptr [rcx+1Ch], 2
0x18005be6a  jz      loc_18005BAA1
0x18005be70  mov     edx, 4Ch ; 'L'
0x18005be75  mov     r8, r15
0x18005be78  mov     rcx, [rcx+10h]
0x18005be7c  mov     r9d, eax
0x18005be7f  call    WPP_SF_d
0x18005be84  jmp     loc_18005BAA1
0x18005be89  mov     eax, [rax+7Ch]
0x18005be8c  or      eax, [rsi+78h]
0x18005be8f  jz      loc_18005BAA1
0x18005be95  mov     r9, [rsi+78h]
0x18005be99  mov     rax, qword ptr [rsp+150h+var_E0.LowPart]
0x18005be9e  mov     qword ptr [rbp+50h+ProtocolSubmitBuffer+0Ch], r9
0x18005bea2  mov     qword ptr [rbp+50h+ProtocolSubmitBuffer+4], rax
0x18005bea6  mov     r10, cs:WPP_GLOBAL_Control
0x18005bead  cmp     r10, rdi
0x18005beb0  jnz     loc_18005C021
0x18005beb6  mov     edx, dword ptr cs:?NegPackageId@@3_KA; AuthenticationPackage
0x18005bebc  lea     rax, [rsp+150h+ProtocolStatus]
0x18005bec1  mov     rcx, cs:?NegpGlobalLsaHandle@@3PEAXEA; LsaHandle
0x18005bec8  lea     r8, [rbp+50h+ProtocolSubmitBuffer]; ProtocolSubmitBuffer
0x18005becc  mov     [rsp+150h+LocalGroups], rax; ProtocolStatus
  ... truncated ...
```
