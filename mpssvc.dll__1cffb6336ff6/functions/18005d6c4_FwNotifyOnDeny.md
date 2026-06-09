# FwNotifyOnDeny

- ea: `0x18005d6c4`
- end: `0x18005dd85`
- name: `FwNotifyOnDeny`
- size: `1729`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, int, int, int, int, int, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800097b0`

## callees

- `0x1800093b0`
- `0x18000af3c`
- `0x180017110`
- `0x18003e55c`
- `0x180050440`
- `0x18005d6c4`
- `0x1800672c4`
- `0x18006edbc`
- `0x18006f520`
- `0x180071418`
- `0x1800787e0`
- `0x180078e8c`
- `0x1800a7af4`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x18005da3f`
- `ntdll!NtQueryInformationProcess` at `0x18005da3f`
- `ntdll!RtlGetActiveConsoleId` at `0x18005da9d`
- `ntdll!RtlGetActiveConsoleId` at `0x18005da9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005da05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005db2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005da05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005db2e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18005dc94`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18005dc94`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18005d9fb`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18005d9fb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005dc77`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005dc77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005dccb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005dccb`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18005dd3c`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18005dd3c`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18005dacd`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18005dacd`
- `fwbase!FwImageListHasImage` at `0x18005d96f`
- `fwbase!FwImageListHasImage` at `0x18005d96f`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18005d83d`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18005d90c`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18005d83d`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18005d90c`
- `fwbase!FwReportErrorAsNtStatus` at `0x18005da5a`
- `fwbase!FwReportErrorAsNtStatus` at `0x18005da5a`
- `fwbase!FwGetTokenInformation` at `0x18005dc63`
- `fwbase!FwGetTokenInformation` at `0x18005dc63`
- `fwbase!FwReportReturnError` at `0x18005dbdc`
- `fwbase!FwReportReturnError` at `0x18005dc14`
- `fwbase!FwReportReturnError` at `0x18005dd4f`
- `fwbase!FwReportReturnError` at `0x18005dbdc`
- `fwbase!FwReportReturnError` at `0x18005dc14`
- `fwbase!FwReportReturnError` at `0x18005dd4f`
- `fwbase!FwFree` at `0x18005dd05`
- `fwbase!FwFree` at `0x18005dd05`
- `fwbase!FwReportErrorAsWinError` at `0x18005db45`
- `fwbase!FwReportErrorAsWinError` at `0x18005db45`

## string_xrefs

- `0x18005da0b`: `CheckTokenMembership`

## pseudocode

```c
__int64 __fastcall FwNotifyOnDeny(
        void *a1,
        void *a2,
        __int64 a3,
        int a4,
        int a5,
        unsigned int a6,
        unsigned int a7,
        int a8,
        int a9,
        __int64 a10)
{
  unsigned __int16 **v10; // rbx
  int v11; // r15d
  unsigned int v14; // r14d
  __int64 v15; // rcx
  signed int IsFirstTimeForProcess; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  DWORD v20; // esi
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rsi
  unsigned int v24; // r13d
  __int64 v25; // rdi
  int v26; // eax
  __int64 v27; // rdx
  HANDLE v28; // r12
  int v29; // eax
  DWORD LastError; // eax
  const char *v31; // rdx
  WINBOOL v32; // eax
  NTSTATUS v33; // eax
  int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // r8
  __int64 v38; // r9
  int v39; // edi
  HLOCAL v40; // rax
  void *v41; // rdi
  int v43; // [rsp+30h] [rbp-A1h]
  int v44; // [rsp+58h] [rbp-79h] BYREF
  int v45; // [rsp+5Ch] [rbp-75h]
  HANDLE TokenHandle; // [rsp+60h] [rbp-71h]
  __int64 v47; // [rsp+68h] [rbp-69h]
  int v48; // [rsp+70h] [rbp-61h]
  unsigned __int16 **v49; // [rsp+80h] [rbp-51h]
  HANDLE ProcessHandle; // [rsp+88h] [rbp-49h]
  DWORD cbSid; // [rsp+90h] [rbp-41h] BYREF
  __int64 v52; // [rsp+98h] [rbp-39h] BYREF
  LPWSTR ppBuffer; // [rsp+A0h] [rbp-31h] BYREF
  WINBOOL IsMember; // [rsp+A8h] [rbp-29h] BYREF
  DWORD ProcessInformation; // [rsp+ACh] [rbp-25h] BYREF
  DWORD pBytesReturned; // [rsp+B0h] [rbp-21h] BYREF

  v10 = (unsigned __int16 **)a10;
  v11 = 0;
  v52 = a3;
  v47 = 0;
  v48 = 0;
  TokenHandle = a2;
  ProcessHandle = a1;
  v14 = 0;
  v49 = (unsigned __int16 **)a10;
  v44 = 0;
  IsMember = 0;
  ProcessInformation = 0;
  ppBuffer = 0;
  pBytesReturned = 0;
  v45 = 1;
  v15 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_3ec461e273913f4b05610a2e2629c131_Traceguids);
      v15 = WPP_GLOBAL_Control;
    }
    if ( (_UNKNOWN *)v15 != &WPP_GLOBAL_Control && (*(_BYTE *)(v15 + 28) & 4) != 0 )
      WPP_SF_SdH(
        *(_QWORD *)(v15 + 16),
        (_DWORD)a2,
        a3,
        *(_QWORD *)(a10 + 16),
        *(_DWORD *)(a10 + 36),
        *(_WORD *)(a10 + 32));
  }
  IsFirstTimeForProcess = FwNotifyIsFirstTimeForProcess(*(_DWORD *)(a10 + 8), a1, &v44);
  cbSid = IsFirstTimeForProcess;
  v20 = IsFirstTimeForProcess;
  if ( IsFirstTimeForProcess < 0 )
  {
LABEL_85:
    FwReportReturnError("FwNotifyOnDeny", (unsigned int)IsFirstTimeForProcess, v18);
LABEL_86:
    if ( v10[2] )
      v14 = 32;
    goto LABEL_88;
  }
  if ( !v44 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
      goto LABEL_90;
    v22 = 12;
    goto LABEL_12;
  }
  if ( !a4 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_3ec461e273913f4b05610a2e2629c131_Traceguids);
    goto LABEL_91;
  }
  v23 = v52;
  v24 = 0;
  v25 = 0;
  do
  {
    v26 = dword_18012F89C & FwGetProfileTypeFromProfileIndex((unsigned int)v25);
    v18 = 1;
    if ( (*(_BYTE *)(v23 + 72) & 1) != 0 || (v21 = 160 * v25, LODWORD(gFwProfileMgr[20 * v25 + 648]) != 1) )
    {
      v21 = 160 * v25;
      if ( LODWORD(gFwProfileMgr[20 * v25 + 643]) )
      {
        if ( *(_DWORD *)((char *)&gFwProfileMgr[644] + v21) != 1 )
        {
          if ( v26 )
            v11 = 1;
          v24 |= FwGetProfileTypeFromProfileIndex((unsigned int)v25);
          goto LABEL_38;
        }
        if ( v26 )
        {
          v14 |= 0x80u;
          v21 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
          {
            v27 = 16;
LABEL_24:
            WPP_SF_(*(_QWORD *)(v21 + 16), v27, WPP_3ec461e273913f4b05610a2e2629c131_Traceguids);
LABEL_38:
            v18 = 1;
          }
        }
      }
      else if ( v26 )
      {
        *((_DWORD *)&v47 + v25) = 1;
        v21 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        {
          v27 = 15;
          goto LABEL_24;
        }
      }
    }
    else if ( v26 )
    {
      v14 |= 0x40u;
      v21 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      {
        v27 = 14;
        goto LABEL_24;
      }
    }
    v25 = (unsigned int)(v25 + 1);
  }
  while ( (unsigned int)v25 < 3 );
  v10 = v49;
  v20 = cbSid;
  v28 = ProcessHandle;
  if ( !v11 )
  {
    if ( (_DWORD)v47 && HIDWORD(v47) && v48 )
    {
      v14 = 4;
      v29 = 0;
      goto LABEL_89;
    }
    goto LABEL_90;
  }
  if ( (unsigned int)FwImageListHasImage(&gFwAuthApps, v49[2]) )
  {
    v14 = 8;
    v21 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
      goto LABEL_90;
    v22 = 17;
    goto LABEL_12;
  }
  if ( *((_DWORD *)v10 + 6) )
  {
    v14 = 1;
    v21 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
      goto LABEL_90;
    v22 = 18;
    goto LABEL_12;
  }
  v14 = 0;
  if ( v52 )
  {
    if ( (*(_BYTE *)(v52 + 72) & 0x10) == 0 )
    {
      v32 = 0;
      IsMember = 0;
      goto LABEL_62;
    }
    IsMember = 1;
  }
  else
  {
    if ( !CheckTokenMembership(TokenHandle, SidToCheck, &IsMember) )
    {
      LastError = GetLastError();
      v31 = "CheckTokenMembership";
      goto LABEL_76;
    }
    v32 = IsMember;
LABEL_62:
    if ( !v32 )
    {
      v14 = 2;
      v21 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
        goto LABEL_90;
      v22 = 19;
LABEL_12:
      WPP_SF_(*(_QWORD *)(v21 + 16), v22, WPP_3ec461e273913f4b05610a2e2629c131_Traceguids);
      goto LABEL_90;
    }
  }
  v33 = NtQueryInformationProcess(v28, ProcessSessionInformation, &ProcessInformation, 4u, 0);
  if ( v33 < 0 )
  {
    v34 = FwReportErrorAsNtStatus("FwNotifyOnDeny", "NtQueryInformationProcess", (unsigned int)v33);
    goto LABEL_77;
  }
  if ( ProcessInformation == (unsigned int)RtlGetActiveConsoleId() )
  {
LABEL_79:
    v39 = 0;
    if ( !(unsigned int)FwIsMachineJoinedToDomain() )
      v24 &= ~1u;
    if ( v24 != (a8 | a7) )
      v39 = v24 & dword_18012F89C & ~(a8 | a7 | a6);
    IsFirstTimeForProcess = FwNotifyCreateNotifierModern(
                              TokenHandle,
                              v52,
                              v24,
                              a6,
                              a5,
                              a7,
                              a8,
                              a9,
                              (__int64)v10[2],
                              v39);
    v20 = IsFirstTimeForProcess;
    if ( IsFirstTimeForProcess >= 0 )
    {
      IsFirstTimeForProcess = FwNotifyAddImageToAuthorizedApps(v24, a6, a8 | a7, v10[2], v39, v10);
      v20 = IsFirstTimeForProcess;
      if ( IsFirstTimeForProcess >= 0 )
        goto LABEL_90;
    }
    goto LABEL_85;
  }
  if ( (unsigned __int8)IsWTSFreeMemoryPresent()
    && WTSQuerySessionInformationW(0, ProcessInformation, WTSConnectState, &ppBuffer, &pBytesReturned) )
  {
    if ( pBytesReturned != 4 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v36, v35, v37, v38);
    if ( *(_DWORD *)ppBuffer > 1u )
    {
      v14 = 16;
      v21 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          20,
          WPP_3ec461e273913f4b05610a2e2629c131_Traceguids,
          *(unsigned int *)ppBuffer);
      goto LABEL_90;
    }
    goto LABEL_79;
  }
  LastError = GetLastError();
  v31 = "WTSQuerySessionInformation";
LABEL_76:
  v34 = FwReportErrorAsWinError("FwNotifyOnDeny", v31, LastError);
LABEL_77:
  v20 = v34;
  if ( v34 < 0 )
    goto LABEL_86;
LABEL_88:
  v29 = v45;
LABEL_89:
  if ( v29 )
LABEL_90:
    FwAuditLogAppBlockedFromListening(v21, (unsigned int)dword_18012F89C, v10[2]);
LABEL_91:
  if ( v14 && v10[2] )
  {
    v52 = 0;
    if ( (int)FwGetTokenInformation(TokenHandle, 1, &v52, 0) >= 0 )
    {
      LOWORD(v43) = *((_WORD *)v10 + 16);
      FwEventQueryUserNotDisplayed(
        v14,
        v10[2],
        *(_QWORD *)v52,
        *((unsigned int *)v10 + 7),
        *((_DWORD *)v10 + 9),
        v43,
        *((_DWORD *)v10 + 2));
      FwFree(v52);
    }
    else
    {
      cbSid = 68;
      v40 = LocalAlloc(0, 0x44u);
      v41 = v40;
      if ( v40 )
      {
        if ( CreateWellKnownSid(WinNullSid, 0, v40, &cbSid) )
        {
          LOWORD(v43) = *((_WORD *)v10 + 16);
          FwEventQueryUserNotDisplayed(
            v14,
            v10[2],
            v41,
            *((unsigned int *)v10 + 7),
            *((_DWORD *)v10 + 9),
            v43,
            *((_DWORD *)v10 + 2));
        }
        LocalFree(v41);
      }
    }
  }
  if ( _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0] )
    MicrosoftTelemetryAssertTriggeredNoArgs(v21, v17, v18, v19);
  if ( ppBuffer && (unsigned __int8)IsWTSFreeMemoryPresent() )
    WTSFreeMemory(ppBuffer);
  if ( (v20 & 0x80000000) != 0 )
    return (unsigned int)FwReportReturnError("FwNotifyOnDeny", v20, v18);
  return v20;
}

```

## disassembly

```asm
0x18005d6c4  mov     rax, rsp
0x18005d6c7  mov     [rax+20h], rbx
0x18005d6cb  push    rbp
0x18005d6cc  push    rsi
0x18005d6cd  push    rdi
0x18005d6ce  push    r12
0x18005d6d0  push    r13
0x18005d6d2  push    r14
0x18005d6d4  push    r15
0x18005d6d6  lea     rbp, [rax-3Fh]
0x18005d6da  sub     rsp, 0D0h
0x18005d6e1  movaps  xmmword ptr [rax-48h], xmm6
0x18005d6e5  mov     rax, cs:__security_cookie
0x18005d6ec  xor     rax, rsp
0x18005d6ef  mov     [rbp+37h+var_50], rax
0x18005d6f3  mov     rbx, [rbp+37h+arg_48]
0x18005d6fa  xor     r15d, r15d
0x18005d6fd  xor     eax, eax
0x18005d6ff  mov     [rbp+37h+var_70], r8
0x18005d703  mov     [rbp+37h+var_A0], rax
0x18005d707  mov     edi, r9d
0x18005d70a  mov     [rbp+37h+var_98], eax
0x18005d70d  mov     r12, rcx
0x18005d710  mov     [rbp+37h+TokenHandle], rdx
0x18005d714  xorps   xmm6, xmm6
0x18005d717  mov     [rbp+37h+ProcessHandle], rcx
0x18005d71b  mov     r14d, r15d
0x18005d71e  mov     [rbp+37h+var_88], rbx
0x18005d722  mov     [rbp+37h+var_B0], r15d
0x18005d726  mov     [rbp+37h+IsMember], r15d
0x18005d72a  mov     [rbp+37h+ProcessInformation], r15d
0x18005d72e  mov     [rbp+37h+ppBuffer], r15
0x18005d732  mov     [rbp+37h+pBytesReturned], r15d
0x18005d736  mov     [rbp+37h+var_AC], 1
0x18005d73d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d744  lea     r13, WPP_GLOBAL_Control
0x18005d74b  cmp     rcx, r13
0x18005d74e  jz      short loc_18005D798
0x18005d750  test    byte ptr [rcx+1Ch], 8
0x18005d754  jz      short loc_18005D770
0x18005d756  mov     rcx, [rcx+10h]
0x18005d75a  lea     edx, [rax+0Ah]
0x18005d75d  lea     r8, WPP_3ec461e273913f4b05610a2e2629c131_Traceguids
0x18005d764  call    WPP_SF_
0x18005d769  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d770  cmp     rcx, r13
0x18005d773  jz      short loc_18005D798
0x18005d775  test    byte ptr [rcx+1Ch], 4
0x18005d779  jz      short loc_18005D798
0x18005d77b  movzx   eax, word ptr [rbx+20h]
0x18005d77f  mov     r9, [rbx+10h]
0x18005d783  mov     rcx, [rcx+10h]
0x18005d787  mov     word ptr [rsp+100h+var_D8], ax
0x18005d78c  mov     eax, [rbx+24h]
0x18005d78f  mov     dword ptr [rsp+100h+ReturnLength], eax
0x18005d793  call    WPP_SF_SdH
0x18005d798  mov     ecx, [rbx+8]; unsigned int
0x18005d79b  lea     r8, [rbp+37h+var_B0]; int *
0x18005d79f  mov     rdx, r12; void *
0x18005d7a2  call    ?FwNotifyIsFirstTimeForProcess@@YAJKPEAXPEAH@Z; FwNotifyIsFirstTimeForProcess(ulong,void *,int *)
0x18005d7a7  mov     [rbp+37h+cbSid], eax
0x18005d7aa  mov     esi, eax
0x18005d7ac  test    eax, eax
0x18005d7ae  js      loc_18005DC0B
0x18005d7b4  cmp     [rbp+37h+var_B0], r15d
0x18005d7b8  jnz     short loc_18005D7EE
0x18005d7ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d7c1  cmp     rcx, r13
0x18005d7c4  jz      loc_18005DC2E
0x18005d7ca  test    byte ptr [rcx+1Ch], 4
0x18005d7ce  jz      loc_18005DC2E
0x18005d7d4  mov     edx, 0Ch
0x18005d7d9  mov     rcx, [rcx+10h]
0x18005d7dd  lea     r8, WPP_3ec461e273913f4b05610a2e2629c131_Traceguids
0x18005d7e4  call    WPP_SF_
0x18005d7e9  jmp     loc_18005DC2E
0x18005d7ee  test    edi, edi
0x18005d7f0  jnz     short loc_18005D824
0x18005d7f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d7f9  cmp     rcx, r13
0x18005d7fc  jz      loc_18005DC3D
0x18005d802  test    byte ptr [rcx+1Ch], 4
0x18005d806  jz      loc_18005DC3D
0x18005d80c  mov     rcx, [rcx+10h]
0x18005d810  lea     edx, [rdi+0Dh]
0x18005d813  lea     r8, WPP_3ec461e273913f4b05610a2e2629c131_Traceguids
0x18005d81a  call    WPP_SF_
0x18005d81f  jmp     loc_18005DC3D
0x18005d824  mov     rsi, [rbp+37h+var_70]
0x18005d828  lea     rbx, WPP_GLOBAL_Control
0x18005d82f  xor     r13d, r13d
0x18005d832  lea     r12, gFwProfileMgr
0x18005d839  xor     edi, edi
0x18005d83b  mov     ecx, edi
0x18005d83d  call    cs:__imp_FwGetProfileTypeFromProfileIndex
0x18005d843  and     eax, cs:dword_18012F89C
0x18005d849  mov     r8d, 1
0x18005d84f  test    [rsi+48h], r8b
0x18005d853  jnz     short loc_18005D8A3
0x18005d855  lea     rcx, [rdi+rdi*4]
0x18005d859  shl     rcx, 5
0x18005d85d  cmp     [rcx+r12+1440h], r8d
0x18005d865  jnz     short loc_18005D8A3
0x18005d867  test    eax, eax
0x18005d869  jz      loc_18005D91B
0x18005d86f  or      r14d, 40h
0x18005d873  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d87a  cmp     rcx, rbx
0x18005d87d  jz      loc_18005D91B
0x18005d883  test    byte ptr [rcx+1Ch], 4
0x18005d887  jz      loc_18005D91B
0x18005d88d  lea     edx, [r8+0Dh]
0x18005d891  mov     rcx, [rcx+10h]
0x18005d895  lea     r8, WPP_3ec461e273913f4b05610a2e2629c131_Traceguids
0x18005d89c  call    WPP_SF_
0x18005d8a1  jmp     short loc_18005D915
0x18005d8a3  lea     rcx, [rdi+rdi*4]
0x18005d8a7  shl     rcx, 5
0x18005d8ab  cmp     dword ptr [rcx+r12+1418h], 0
0x18005d8b4  jnz     short loc_18005D8D8
0x18005d8b6  test    eax, eax
0x18005d8b8  jz      short loc_18005D91B
0x18005d8ba  mov     dword ptr [rbp+rdi*4+37h+var_A0], r8d
0x18005d8bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d8c6  cmp     rcx, rbx
0x18005d8c9  jz      short loc_18005D91B
0x18005d8cb  test    byte ptr [rcx+1Ch], 4
0x18005d8cf  jz      short loc_18005D91B
0x18005d8d1  mov     edx, 0Fh
0x18005d8d6  jmp     short loc_18005D891
0x18005d8d8  cmp     [rcx+r12+1420h], r8d
0x18005d8e0  jnz     short loc_18005D904
0x18005d8e2  test    eax, eax
0x18005d8e4  jz      short loc_18005D91B
0x18005d8e6  bts     r14d, 7
0x18005d8eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d8f2  cmp     rcx, rbx
0x18005d8f5  jz      short loc_18005D91B
0x18005d8f7  test    byte ptr [rcx+1Ch], 4
0x18005d8fb  jz      short loc_18005D91B
0x18005d8fd  mov     edx, 10h
0x18005d902  jmp     short loc_18005D891
0x18005d904  test    eax, eax
0x18005d906  mov     ecx, edi
0x18005d908  cmovnz  r15d, r8d
0x18005d90c  call    cs:__imp_FwGetProfileTypeFromProfileIndex
0x18005d912  or      r13d, eax
0x18005d915  mov     r8d, 1
0x18005d91b  add     edi, r8d
0x18005d91e  cmp     edi, 3
0x18005d921  jb      loc_18005D83B
0x18005d927  mov     rbx, [rbp+37h+var_88]
0x18005d92b  mov     esi, [rbp+37h+cbSid]
0x18005d92e  mov     r12, [rbp+37h+ProcessHandle]
0x18005d932  test    r15d, r15d
0x18005d935  jnz     short loc_18005D964
0x18005d937  xor     r15d, r15d
0x18005d93a  cmp     dword ptr [rbp+37h+var_A0], r15d
0x18005d93e  jz      loc_18005DC2E
0x18005d944  cmp     dword ptr [rbp+37h+var_A0+4], r15d
0x18005d948  jz      loc_18005DC2E
0x18005d94e  cmp     [rbp+37h+var_98], r15d
0x18005d952  jz      loc_18005DC2E
0x18005d958  lea     r14d, [r15+4]
0x18005d95c  mov     eax, r15d
0x18005d95f  jmp     loc_18005DC2A
0x18005d964  mov     rdx, [rbx+10h]
0x18005d968  lea     rcx, ?gFwAuthApps@@3UFW_AUTHORIZED_APPS_COMPONENT_@@A; FW_AUTHORIZED_APPS_COMPONENT_ gFwAuthApps
0x18005d96f  call    cs:__imp_FwImageListHasImage
0x18005d975  xor     r15d, r15d
0x18005d978  test    eax, eax
0x18005d97a  jz      short loc_18005D9AA
0x18005d97c  lea     r14d, [r15+8]
0x18005d980  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d987  lea     rax, WPP_GLOBAL_Control
0x18005d98e  cmp     rcx, rax
0x18005d991  jz      loc_18005DC2E
0x18005d997  test    byte ptr [rcx+1Ch], 4
0x18005d99b  jz      loc_18005DC2E
0x18005d9a1  lea     edx, [r15+11h]
0x18005d9a5  jmp     loc_18005D7D9
0x18005d9aa  cmp     [rbx+18h], r15d
0x18005d9ae  jz      short loc_18005D9E0
0x18005d9b0  mov     r14d, 1
0x18005d9b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d9bd  lea     rax, WPP_GLOBAL_Control
0x18005d9c4  cmp     rcx, rax
0x18005d9c7  jz      loc_18005DC2E
0x18005d9cd  test    byte ptr [rcx+1Ch], 4
0x18005d9d1  jz      loc_18005DC2E
0x18005d9d7  lea     edx, [r14+11h]
0x18005d9db  jmp     loc_18005D7D9
0x18005d9e0  mov     rax, [rbp+37h+var_70]
0x18005d9e4  mov     r14d, r15d
0x18005d9e7  test    rax, rax
0x18005d9ea  jnz     short loc_18005DA1C
0x18005d9ec  mov     rdx, qword ptr cs:SidToCheck; SidToCheck
0x18005d9f3  lea     r8, [rbp+37h+IsMember]; IsMember
0x18005d9f7  mov     rcx, [rbp+37h+TokenHandle]; TokenHandle
0x18005d9fb  call    cs:__imp_CheckTokenMembership
0x18005da01  test    eax, eax
0x18005da03  jnz     short loc_18005DA17
0x18005da05  call    cs:__imp_GetLastError
0x18005da0b  lea     rdx, aChecktokenmemb; "CheckTokenMembership"
0x18005da12  jmp     loc_18005DB3B
0x18005da17  mov     eax, [rbp+37h+IsMember]
0x18005da1a  jmp     short loc_18005DA6B
0x18005da1c  test    byte ptr [rax+48h], 10h
0x18005da20  jz      short loc_18005DA65
0x18005da22  mov     [rbp+37h+IsMember], 1
0x18005da29  mov     r9d, 4; ProcessInformationLength
0x18005da2f  mov     [rsp+100h+ReturnLength], r15; ReturnLength
0x18005da34  lea     r8, [rbp+37h+ProcessInformation]; ProcessInformation
0x18005da38  mov     rcx, r12; ProcessHandle
0x18005da3b  lea     edx, [r9+14h]; ProcessInformationClass
0x18005da3f  call    cs:__imp_NtQueryInformationProcess
0x18005da45  test    eax, eax
0x18005da47  jns     short loc_18005DA9D
0x18005da49  mov     r8d, eax
0x18005da4c  lea     rdx, aNtqueryinforma; "NtQueryInformationProcess"
0x18005da53  lea     rcx, aFwnotifyondeny; "FwNotifyOnDeny"
0x18005da5a  call    cs:__imp_FwReportErrorAsNtStatus
0x18005da60  jmp     loc_18005DB4B
0x18005da65  mov     eax, r15d
0x18005da68  mov     [rbp+37h+IsMember], eax
0x18005da6b  test    eax, eax
0x18005da6d  jnz     short loc_18005DA29
0x18005da6f  lea     r14d, [rax+2]
0x18005da73  mov     rcx, cs:WPP_GLOBAL_Control
0x18005da7a  lea     rax, WPP_GLOBAL_Control
0x18005da81  cmp     rcx, rax
0x18005da84  jz      loc_18005DC2E
0x18005da8a  test    byte ptr [rcx+1Ch], 4
0x18005da8e  jz      loc_18005DC2E
0x18005da94  lea     edx, [r14+11h]
0x18005da98  jmp     loc_18005D7D9
0x18005da9d  call    cs:__imp_RtlGetActiveConsoleId
0x18005daa3  cmp     [rbp+37h+ProcessInformation], eax
0x18005daa6  jz      loc_18005DB5A
0x18005daac  call    IsWTSFreeMemoryPresent
0x18005dab1  test    al, al
0x18005dab3  jz      short loc_18005DB2E
0x18005dab5  mov     edx, [rbp+37h+ProcessInformation]; SessionId
0x18005dab8  lea     rax, [rbp+37h+pBytesReturned]
0x18005dabc  lea     r9, [rbp+37h+ppBuffer]; ppBuffer
0x18005dac0  mov     [rsp+100h+ReturnLength], rax; pBytesReturned
0x18005dac5  mov     r8d, 8; WTSInfoClass
0x18005dacb  xor     ecx, ecx; hServer
0x18005dacd  call    cs:__imp_WTSQuerySessionInformationW
0x18005dad3  test    eax, eax
0x18005dad5  jz      short loc_18005DB2E
0x18005dad7  cmp     [rbp+37h+pBytesReturned], 4
0x18005dadb  jz      short loc_18005DAE2
0x18005dadd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005dae2  mov     rax, [rbp+37h+ppBuffer]
0x18005dae6  cmp     dword ptr [rax], 1
0x18005dae9  jbe     short loc_18005DB5A
0x18005daeb  mov     r14d, 10h
0x18005daf1  mov     rcx, cs:WPP_GLOBAL_Control
0x18005daf8  lea     rdx, WPP_GLOBAL_Control
0x18005daff  cmp     rcx, rdx
0x18005db02  jz      loc_18005DC2E
0x18005db08  test    byte ptr [rcx+1Ch], 4
0x18005db0c  jz      loc_18005DC2E
0x18005db12  mov     r9d, [rax]
0x18005db15  lea     edx, [r14+4]
0x18005db19  mov     rcx, [rcx+10h]
0x18005db1d  lea     r8, WPP_3ec461e273913f4b05610a2e2629c131_Traceguids
0x18005db24  call    WPP_SF_d
0x18005db29  jmp     loc_18005DC2E
0x18005db2e  call    cs:__imp_GetLastError
0x18005db34  lea     rdx, aWtsquerysessio_0; "WTSQuerySessionInformation"
0x18005db3b  mov     r8d, eax
0x18005db3e  lea     rcx, aFwnotifyondeny; "FwNotifyOnDeny"
0x18005db45  call    cs:__imp_FwReportErrorAsWinError
0x18005db4b  mov     esi, eax
0x18005db4d  test    eax, eax
0x18005db4f  js      loc_18005DC1A
0x18005db55  jmp     loc_18005DC27
0x18005db5a  mov     edi, r15d
0x18005db5d  call    ?FwIsMachineJoinedToDomain@@YAHXZ; FwIsMachineJoinedToDomain(void)
0x18005db62  test    eax, eax
0x18005db64  jnz     short loc_18005DB6A
0x18005db66  and     r13d, 0FFFFFFFEh
0x18005db6a  mov     ecx, [rbp+37h+arg_30]
0x18005db6d  mov     r15d, ecx
0x18005db70  mov     r8d, [rbp+37h+arg_38]
0x18005db74  or      r15d, r8d
0x18005db77  mov     r12d, [rbp+37h+arg_28]
0x18005db7b  cmp     r13d, r15d
0x18005db7e  jz      short loc_18005DB93
0x18005db80  mov     edi, r12d
0x18005db83  or      edi, ecx
0x18005db85  or      edi, r8d
0x18005db88  not     edi
0x18005db8a  and     edi, cs:dword_18012F89C
0x18005db90  and     edi, r13d
0x18005db93  mov     rax, [rbx+10h]
0x18005db97  mov     r9d, r12d
0x18005db9a  mov     rdx, [rbp+37h+var_70]
  ... truncated ...
```
