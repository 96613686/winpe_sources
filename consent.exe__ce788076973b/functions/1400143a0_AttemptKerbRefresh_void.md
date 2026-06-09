# AttemptKerbRefresh(void *)

- ea: `0x1400143a0`
- end: `0x14001475c`
- name: `?AttemptKerbRefresh@@YAKPEAX@Z`
- size: `956`
- prototype: `__int64 __fastcall(__int64 *Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x140010ad3`
- `0x140013928`
- `0x1400143a0`
- `0x140017a1c`
- `0x140018200`
- `0x14001e012`
- `0x14001e050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400146cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400146cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014728`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140014728`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140014731`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140014731`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140014446`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140014446`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400146f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400146f2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001465f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140014680`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001465f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140014680`
- `SspiCli!LsaLogonUser` at `0x1400145ec`
- `SspiCli!LsaLogonUser` at `0x1400145ec`
- `SspiCli!LsaFreeReturnBuffer` at `0x1400146e3`
- `SspiCli!LsaFreeReturnBuffer` at `0x1400146e3`
- `SspiCli!LsaDeregisterLogonProcess` at `0x140014701`
- `SspiCli!LsaDeregisterLogonProcess` at `0x140014701`
- `SspiCli!LsaRegisterLogonProcess` at `0x14001452d`
- `SspiCli!LsaRegisterLogonProcess` at `0x14001452d`
- `SspiCli!SeciAllocateAndSetCallFlags` at `0x14001450a`
- `SspiCli!SeciAllocateAndSetCallFlags` at `0x14001450a`
- `ntdll!RtlNtStatusToDosError` at `0x140014539`
- `ntdll!RtlNtStatusToDosError` at `0x140014539`
- `ntdll!RtlEqualSid` at `0x140014692`
- `ntdll!RtlEqualSid` at `0x140014692`
- `ntdll!RtlInitString` at `0x14001451b`
- `ntdll!RtlInitString` at `0x14001451b`
- `ntdll!NtAllocateLocallyUniqueId` at `0x140014551`
- `ntdll!NtAllocateLocallyUniqueId` at `0x140014551`

## pseudocode

```c
__int64 __fastcall AttemptKerbRefresh(__int64 *Parameter)
{
  __int64 v1; // rdi
  int v2; // ebx
  __int64 v3; // r14
  ULONG v4; // r13d
  _DWORD *v5; // rax
  _DWORD *AuthenticationInformation; // rsi
  unsigned int v7; // ebx
  NTSTATUS v8; // eax
  unsigned __int64 v9; // rdx
  const char *v10; // r8
  NTSTATUS v11; // ecx
  ULONG LastError; // eax
  unsigned int v13; // eax
  int v14; // ebx
  _BYTE *v15; // rax
  __int64 v16; // rcx
  int SubStatus; // [rsp+70h] [rbp-90h] BYREF
  int v19; // [rsp+74h] [rbp-8Ch]
  int v20; // [rsp+78h] [rbp-88h]
  int v21; // [rsp+7Ch] [rbp-84h] BYREF
  ULONG SecurityMode; // [rsp+80h] [rbp-80h] BYREF
  ULONG ProfileBufferLength; // [rsp+84h] [rbp-7Ch] BYREF
  DWORD ReturnLength; // [rsp+88h] [rbp-78h] BYREF
  DWORD v25; // [rsp+8Ch] [rbp-74h] BYREF
  HANDLE TokenHandle; // [rsp+90h] [rbp-70h] BYREF
  void *LsaHandle; // [rsp+98h] [rbp-68h] BYREF
  struct _LUID LogonId; // [rsp+A0h] [rbp-60h] BYREF
  PVOID Buffer; // [rsp+A8h] [rbp-58h] BYREF
  HANDLE v30; // [rsp+B0h] [rbp-50h]
  unsigned int *v31; // [rsp+B8h] [rbp-48h]
  struct _STRING DestinationString; // [rsp+C0h] [rbp-40h] BYREF
  LUID LocallyUniqueId[2]; // [rsp+D0h] [rbp-30h] BYREF
  struct _QUOTA_LIMITS Quotas; // [rsp+E0h] [rbp-20h] BYREF
  PSID TokenInformation[12]; // [rsp+110h] [rbp+10h] BYREF
  PSID Sid1[12]; // [rsp+170h] [rbp+70h] BYREF

  v1 = *Parameter;
  v19 = *((_DWORD *)Parameter + 2);
  v20 = *((_DWORD *)Parameter + 3);
  v2 = *(_DWORD *)(v1 + 8);
  v3 = *(_QWORD *)(v1 + 16);
  v4 = *(_DWORD *)(v1 + 4);
  v30 = (HANDLE)Parameter[2];
  v31 = (unsigned int *)Parameter[3];
  SubStatus = 0;
  LogonId = 0;
  LsaHandle = 0;
  DestinationString = 0;
  SecurityMode = 0;
  *(_OWORD *)&LocallyUniqueId[0].LowPart = 0;
  Buffer = 0;
  TokenHandle = 0;
  memset(&Quotas, 0, sizeof(Quotas));
  ProfileBufferLength = 0;
  v21 = 0;
  ReturnLength = 0;
  v25 = 0;
  v5 = LocalAlloc(0x40u, (unsigned int)(v2 + 8));
  AuthenticationInformation = v5;
  if ( !v5 )
  {
    v7 = 8;
    goto LABEL_26;
  }
  memset_0(v5, 0, (unsigned int)(v2 + 8));
  AuthenticationInformation[19] = v19;
  AuthenticationInformation[18] = v20;
  *AuthenticationInformation = 15;
  memcpy_0(AuthenticationInformation + 20, (const void *)(v3 + 72), (unsigned int)(v2 - 72));
  *((_QWORD *)AuthenticationInformation + 2) = *(_QWORD *)(v3 + 16) + 8LL;
  *((_QWORD *)AuthenticationInformation + 4) = *(_QWORD *)(v3 + 32) + 8LL;
  *((_QWORD *)AuthenticationInformation + 6) = *(_QWORD *)(v3 + 48) + 8LL;
  *((_QWORD *)AuthenticationInformation + 8) = *(_QWORD *)(v3 + 64) + 8LL;
  *((_WORD *)AuthenticationInformation + 4) = *(_WORD *)(v3 + 8);
  *((_WORD *)AuthenticationInformation + 5) = *(_WORD *)(v3 + 10);
  *((_WORD *)AuthenticationInformation + 12) = *(_WORD *)(v3 + 24);
  *((_WORD *)AuthenticationInformation + 13) = *(_WORD *)(v3 + 26);
  *((_WORD *)AuthenticationInformation + 20) = *(_WORD *)(v3 + 40);
  *((_WORD *)AuthenticationInformation + 21) = *(_WORD *)(v3 + 42);
  AuthenticationInformation[14] = *(_DWORD *)(v3 + 56);
  AuthenticationInformation[15] = *(_DWORD *)(v3 + 60);
  SeciAllocateAndSetCallFlags(0, &v21);
  RtlInitString(&DestinationString, "Winlogon");
  v8 = LsaRegisterLogonProcess((PLSA_STRING)&DestinationString, &LsaHandle, &SecurityMode);
  if ( v8 < 0 )
  {
    v11 = v8;
LABEL_5:
    LastError = RtlNtStatusToDosError(v11);
LABEL_25:
    v7 = LastError;
    goto LABEL_26;
  }
  StringCbCopyA((char *)LocallyUniqueId, v9, v10);
  NtAllocateLocallyUniqueId(&LocallyUniqueId[1]);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 23, WPP_dfa7687bdc833f88b236fff3fe8ed34e_Traceguids);
  v13 = LsaLogonUser(
          LsaHandle,
          (PLSA_STRING)&DestinationString,
          Unlock,
          v4,
          AuthenticationInformation,
          v2 + 8,
          0,
          (PTOKEN_SOURCE)LocallyUniqueId,
          &Buffer,
          &ProfileBufferLength,
          &LogonId,
          &TokenHandle,
          &Quotas,
          &SubStatus);
  v14 = v13;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    WPP_SF_DD(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 24, (unsigned int)SubStatus, v13, SubStatus);
  if ( v14 < 0 )
  {
    if ( (unsigned int)(v14 + 1073741715) > 1 || (v11 = SubStatus) == 0 )
      v11 = v14;
    goto LABEL_5;
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x58u, &ReturnLength)
    || !GetTokenInformation(v30, TokenUser, Sid1, 0x58u, &v25) )
  {
    LastError = GetLastError();
    goto LABEL_25;
  }
  if ( RtlEqualSid(Sid1[0], TokenInformation[0]) )
  {
    v7 = 0;
  }
  else
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 25, WPP_dfa7687bdc833f88b236fff3fe8ed34e_Traceguids);
    v7 = 1326;
  }
LABEL_26:
  *v31 = v7;
  if ( Buffer )
    LsaFreeReturnBuffer(Buffer);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( LsaHandle )
    LsaDeregisterLogonProcess(LsaHandle);
  v15 = *(_BYTE **)(v1 + 16);
  if ( v15 )
  {
    v16 = *(unsigned int *)(v1 + 8);
    if ( *(_DWORD *)(v1 + 8) )
    {
      do
      {
        *v15++ = 0;
        --v16;
      }
      while ( v16 );
    }
    CoTaskMemFree(*(LPVOID *)(v1 + 16));
  }
  LocalFree((HLOCAL)v1);
  return v7;
}

```

## disassembly

```asm
0x1400143a0  push    rbp
0x1400143a2  push    rbx
0x1400143a3  push    rsi
0x1400143a4  push    rdi
0x1400143a5  push    r12
0x1400143a7  push    r13
0x1400143a9  push    r14
0x1400143ab  push    r15
0x1400143ad  lea     rbp, [rsp-0E8h]
0x1400143b5  sub     rsp, 1E8h
0x1400143bc  mov     rax, cs:__security_cookie
0x1400143c3  xor     rax, rsp
0x1400143c6  mov     [rbp+120h+var_50], rax
0x1400143cd  mov     eax, [rcx+8]
0x1400143d0  xorps   xmm0, xmm0
0x1400143d3  mov     rdi, [rcx]
0x1400143d6  xorps   xmm1, xmm1
0x1400143d9  mov     [rsp+220h+var_1AC], eax
0x1400143dd  mov     eax, [rcx+0Ch]
0x1400143e0  mov     [rsp+220h+var_1A8], eax
0x1400143e4  mov     ebx, [rdi+8]
0x1400143e7  mov     r14, [rdi+10h]
0x1400143eb  mov     r13d, [rdi+4]
0x1400143ef  mov     rax, [rcx+10h]
0x1400143f3  mov     [rbp+120h+var_170], rax
0x1400143f7  lea     r15d, [rbx+8]
0x1400143fb  mov     rax, [rcx+18h]
0x1400143ff  mov     [rbp+120h+var_168], rax
0x140014403  xor     eax, eax
0x140014405  mov     edx, r15d; uBytes
0x140014408  mov     [rsp+220h+var_1B0], eax
0x14001440c  mov     qword ptr [rbp+120h+var_180.LowPart], rax
0x140014410  lea     ecx, [rax+40h]; uFlags
0x140014413  mov     [rbp+120h+LsaHandle], rax
0x140014417  movups  xmmword ptr [rbp+120h+DestinationString.Length], xmm0
0x14001441b  mov     [rbp+120h+SecurityMode], eax
0x14001441e  movups  xmmword ptr [rbp+120h+LocallyUniqueId.LowPart], xmm1
0x140014422  mov     [rbp+120h+Buffer], rax
0x140014426  mov     [rbp+120h+TokenHandle], rax
0x14001442a  movups  xmmword ptr [rbp+120h+var_140.PagedPoolLimit], xmm0
0x14001442e  mov     [rbp+120h+var_19C], eax
0x140014431  movups  xmmword ptr [rbp+120h+var_140.MinimumWorkingSetSize], xmm0
0x140014435  mov     [rsp+220h+var_1A4], eax
0x140014439  movups  xmmword ptr [rbp+120h+var_140.PagefileLimit], xmm0
0x14001443d  mov     [rbp+120h+ReturnLength], eax
0x140014440  mov     [rbp+120h+var_194], eax
0x140014443  mov     r12d, r15d
0x140014446  call    cs:__imp_LocalAlloc
0x14001444c  mov     rsi, rax
0x14001444f  test    rax, rax
0x140014452  jnz     short loc_14001445C
0x140014454  lea     ebx, [rax+8]
0x140014457  jmp     loc_1400146D4
0x14001445c  mov     r8, r12; Size
0x14001445f  xor     edx, edx; Val
0x140014461  mov     rcx, rsi; void *
0x140014464  call    memset_0
0x140014469  mov     eax, [rsp+220h+var_1AC]
0x14001446d  lea     r8d, [rbx-48h]; Size
0x140014471  mov     [rsi+4Ch], eax
0x140014474  lea     rdx, [r14+48h]; Src
0x140014478  mov     eax, [rsp+220h+var_1A8]
0x14001447c  lea     rcx, [rsi+50h]; void *
0x140014480  mov     [rsi+48h], eax
0x140014483  mov     dword ptr [rsi], 0Fh
0x140014489  call    memcpy_0
0x14001448e  mov     rax, [r14+10h]
0x140014492  lea     rdx, [rsp+220h+var_1A4]
0x140014497  mov     ebx, 8
0x14001449c  xor     ecx, ecx
0x14001449e  add     rax, rbx
0x1400144a1  mov     [rsi+10h], rax
0x1400144a5  mov     rax, [r14+20h]
0x1400144a9  add     rax, rbx
0x1400144ac  mov     [rsi+20h], rax
0x1400144b0  mov     rax, [r14+30h]
0x1400144b4  add     rax, rbx
0x1400144b7  mov     [rsi+30h], rax
0x1400144bb  mov     rax, [r14+40h]
0x1400144bf  add     rax, rbx
0x1400144c2  mov     [rsi+40h], rax
0x1400144c6  movzx   eax, word ptr [r14+8]
0x1400144cb  mov     [rsi+8], ax
0x1400144cf  movzx   eax, word ptr [r14+0Ah]
0x1400144d4  mov     [rsi+0Ah], ax
0x1400144d8  movzx   eax, word ptr [r14+18h]
0x1400144dd  mov     [rsi+18h], ax
0x1400144e1  movzx   eax, word ptr [r14+1Ah]
0x1400144e6  mov     [rsi+1Ah], ax
0x1400144ea  movzx   eax, word ptr [r14+28h]
0x1400144ef  mov     [rsi+28h], ax
0x1400144f3  movzx   eax, word ptr [r14+2Ah]
0x1400144f8  mov     [rsi+2Ah], ax
0x1400144fc  mov     eax, [r14+38h]
0x140014500  mov     [rsi+38h], eax
0x140014503  mov     eax, [r14+3Ch]
0x140014507  mov     [rsi+3Ch], eax
0x14001450a  call    cs:__imp_SeciAllocateAndSetCallFlags
0x140014510  lea     rdx, aWinlogon; "Winlogon"
0x140014517  lea     rcx, [rbp+120h+DestinationString]; DestinationString
0x14001451b  call    cs:__imp_RtlInitString
0x140014521  lea     r8, [rbp+120h+SecurityMode]; SecurityMode
0x140014525  lea     rdx, [rbp+120h+LsaHandle]; LsaHandle
0x140014529  lea     rcx, [rbp+120h+DestinationString]; LogonProcessName
0x14001452d  call    cs:__imp_LsaRegisterLogonProcess
0x140014533  test    eax, eax
0x140014535  jns     short loc_140014544
0x140014537  mov     ecx, eax; Status
0x140014539  call    cs:__imp_RtlNtStatusToDosError
0x14001453f  jmp     loc_1400146D2
0x140014544  lea     rcx, [rbp+120h+LocallyUniqueId]; char *
0x140014548  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x14001454d  lea     rcx, [rbp+120h+LocallyUniqueId.LowPart+8]; LocallyUniqueId
0x140014551  call    cs:__imp_NtAllocateLocallyUniqueId
0x140014557  mov     rcx, cs:WPP_GLOBAL_Control
0x14001455e  lea     r12, WPP_GLOBAL_Control
0x140014565  mov     r14b, 2
0x140014568  cmp     rcx, r12
0x14001456b  jz      short loc_140014588
0x14001456d  test    [rcx+1Ch], r14b
0x140014571  jz      short loc_140014588
0x140014573  mov     rcx, [rcx+10h]
0x140014577  lea     r8, WPP_dfa7687bdc833f88b236fff3fe8ed34e_Traceguids
0x14001457e  mov     edx, 17h
0x140014583  call    WPP_SF_
0x140014588  mov     rcx, [rbp+120h+LsaHandle]; LsaHandle
0x14001458c  lea     rax, [rsp+220h+var_1B0]
0x140014591  mov     [rsp+220h+SubStatus], rax; SubStatus
0x140014596  lea     rdx, [rbp+120h+DestinationString]; OriginName
0x14001459a  lea     rax, [rbp+120h+var_140]
0x14001459e  mov     r9d, r13d; AuthenticationPackage
0x1400145a1  mov     [rsp+220h+Quotas], rax; Quotas
0x1400145a6  mov     r8d, 7; LogonType
0x1400145ac  lea     rax, [rbp+120h+TokenHandle]
0x1400145b0  mov     [rsp+220h+Token], rax; Token
0x1400145b5  lea     rax, [rbp+120h+var_180]
0x1400145b9  mov     [rsp+220h+LogonId], rax; LogonId
0x1400145be  lea     rax, [rbp+120h+var_19C]
0x1400145c2  mov     [rsp+220h+ProfileBufferLength], rax; ProfileBufferLength
0x1400145c7  lea     rax, [rbp+120h+Buffer]
0x1400145cb  mov     [rsp+220h+ProfileBuffer], rax; ProfileBuffer
0x1400145d0  lea     rax, [rbp+120h+LocallyUniqueId]
0x1400145d4  mov     [rsp+220h+SourceContext], rax; SourceContext
0x1400145d9  mov     [rsp+220h+LocalGroups], 0; LocalGroups
0x1400145e2  mov     [rsp+220h+AuthenticationInformationLength], r15d; AuthenticationInformationLength
0x1400145e7  mov     [rsp+220h+AuthenticationInformation], rsi; AuthenticationInformation
0x1400145ec  call    cs:__imp_LsaLogonUser
0x1400145f2  mov     ebx, eax
0x1400145f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400145fb  cmp     rcx, r12
0x1400145fe  jz      short loc_140014621
0x140014600  test    [rcx+1Ch], r14b
0x140014604  jz      short loc_140014621
0x140014606  mov     r8d, [rsp+220h+var_1B0]
0x14001460b  mov     edx, 18h
0x140014610  mov     rcx, [rcx+10h]
0x140014614  mov     r9d, eax
0x140014617  mov     dword ptr [rsp+220h+AuthenticationInformation], r8d
0x14001461c  call    WPP_SF_DD
0x140014621  test    ebx, ebx
0x140014623  jns     short loc_140014643
0x140014625  lea     eax, [rbx+3FFFFF93h]
0x14001462b  cmp     eax, 1
0x14001462e  ja      short loc_14001463C
0x140014630  mov     ecx, [rsp+220h+var_1B0]
0x140014634  test    ecx, ecx
0x140014636  jnz     loc_140014539
0x14001463c  mov     ecx, ebx
0x14001463e  jmp     loc_140014539
0x140014643  mov     rcx, [rbp+120h+TokenHandle]; TokenHandle
0x140014647  lea     rax, [rbp+120h+ReturnLength]
0x14001464b  mov     ebx, 58h ; 'X'
0x140014650  mov     [rsp+220h+AuthenticationInformation], rax; ReturnLength
0x140014655  mov     r9d, ebx; TokenInformationLength
0x140014658  lea     r8, [rbp+120h+TokenInformation]; TokenInformation
0x14001465c  lea     edx, [rbx-57h]; TokenInformationClass
0x14001465f  call    cs:__imp_GetTokenInformation
0x140014665  test    eax, eax
0x140014667  jz      short loc_1400146CC
0x140014669  mov     rcx, [rbp+120h+var_170]; TokenHandle
0x14001466d  lea     rax, [rbp+120h+var_194]
0x140014671  mov     r9d, ebx; TokenInformationLength
0x140014674  mov     [rsp+220h+AuthenticationInformation], rax; ReturnLength
0x140014679  lea     r8, [rbp+120h+Sid1]; TokenInformation
0x14001467d  lea     edx, [rbx-57h]; TokenInformationClass
0x140014680  call    cs:__imp_GetTokenInformation
0x140014686  test    eax, eax
0x140014688  jz      short loc_1400146CC
0x14001468a  mov     rdx, [rbp+120h+TokenInformation]; Sid2
0x14001468e  mov     rcx, [rbp+120h+Sid1]; Sid1
0x140014692  call    cs:__imp_RtlEqualSid
0x140014698  test    al, al
0x14001469a  jnz     short loc_1400146C8
0x14001469c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400146a3  cmp     rcx, r12
0x1400146a6  jz      short loc_1400146C1
0x1400146a8  test    [rcx+1Ch], r14b
0x1400146ac  jz      short loc_1400146C1
0x1400146ae  mov     rcx, [rcx+10h]
0x1400146b2  lea     edx, [rbx-3Fh]
0x1400146b5  lea     r8, WPP_dfa7687bdc833f88b236fff3fe8ed34e_Traceguids
0x1400146bc  call    WPP_SF_
0x1400146c1  mov     ebx, 52Eh
0x1400146c6  jmp     short loc_1400146D4
0x1400146c8  xor     ebx, ebx
0x1400146ca  jmp     short loc_1400146D4
0x1400146cc  call    cs:__imp_GetLastError
0x1400146d2  mov     ebx, eax
0x1400146d4  mov     rax, [rbp+120h+var_168]
0x1400146d8  mov     [rax], ebx
0x1400146da  mov     rcx, [rbp+120h+Buffer]; Buffer
0x1400146de  test    rcx, rcx
0x1400146e1  jz      short loc_1400146E9
0x1400146e3  call    cs:__imp_LsaFreeReturnBuffer
0x1400146e9  mov     rcx, [rbp+120h+TokenHandle]; hObject
0x1400146ed  test    rcx, rcx
0x1400146f0  jz      short loc_1400146F8
0x1400146f2  call    cs:__imp_CloseHandle
0x1400146f8  mov     rcx, [rbp+120h+LsaHandle]; LsaHandle
0x1400146fc  test    rcx, rcx
0x1400146ff  jz      short loc_140014707
0x140014701  call    cs:__imp_LsaDeregisterLogonProcess
0x140014707  mov     rax, [rdi+10h]
0x14001470b  test    rax, rax
0x14001470e  jz      short loc_14001472E
0x140014710  mov     ecx, [rdi+8]
0x140014713  test    rcx, rcx
0x140014716  jz      short loc_140014724
0x140014718  mov     byte ptr [rax], 0
0x14001471b  inc     rax
0x14001471e  sub     rcx, 1
0x140014722  jnz     short loc_140014718
0x140014724  mov     rcx, [rdi+10h]; pv
0x140014728  call    cs:__imp_CoTaskMemFree
0x14001472e  mov     rcx, rdi; hMem
0x140014731  call    cs:__imp_LocalFree
0x140014737  mov     eax, ebx
0x140014739  mov     rcx, [rbp+120h+var_50]
0x140014740  xor     rcx, rsp; StackCookie
0x140014743  call    __security_check_cookie
0x140014748  add     rsp, 1E8h
0x14001474f  pop     r15
0x140014751  pop     r14
0x140014753  pop     r13
0x140014755  pop     r12
0x140014757  pop     rdi
0x140014758  pop     rsi
0x140014759  pop     rbx
0x14001475a  pop     rbp
0x14001475b  retn
```
