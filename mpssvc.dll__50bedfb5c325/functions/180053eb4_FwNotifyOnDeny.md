# FwNotifyOnDeny

- ea: `0x180053eb4`
- end: `0x18005466c`
- name: `FwNotifyOnDeny`
- size: `1976`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, int, int, int, int, int, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008e00`

## callees

- `0x1800089bc`
- `0x18000a710`
- `0x1800192e0`
- `0x18003e9f4`
- `0x180053eb4`
- `0x180054674`
- `0x18006ab84`
- `0x180072230`
- `0x1800729c0`
- `0x1800748c8`
- `0x18007c098`
- `0x18007c5c0`
- `0x18007c6a8`
- `0x18007ca50`
- `0x1800ad744`

## import_xrefs

- `ntdll!RtlGetActiveConsoleId` at `0x1800543f2`
- `ntdll!RtlGetActiveConsoleId` at `0x1800543f2`
- `ntdll!NtQueryInformationProcess` at `0x180054389`
- `ntdll!NtQueryInformationProcess` at `0x180054389`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054348`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054497`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054348`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054497`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18005428e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18005428e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180054338`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180054338`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005426b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005426b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800542cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800542cb`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180054616`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180054616`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18005442c`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18005442c`
- `fwbase!FwReportErrorAsWinError` at `0x1800544b4`
- `fwbase!FwReportErrorAsWinError` at `0x1800544b4`
- `fwbase!FwImageListHasImage` at `0x180054182`
- `fwbase!FwImageListHasImage` at `0x180054182`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180054054`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18005412b`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180054054`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18005412b`
- `fwbase!FwReportErrorAsNtStatus` at `0x1800543aa`
- `fwbase!FwReportErrorAsNtStatus` at `0x1800543aa`
- `fwbase!FwGetTokenInformation` at `0x18005424d`
- `fwbase!FwGetTokenInformation` at `0x18005424d`
- `fwbase!FwReportReturnError` at `0x180053fb9`
- `fwbase!FwReportReturnError` at `0x180054578`
- `fwbase!FwReportReturnError` at `0x18005462f`
- `fwbase!FwReportReturnError` at `0x180053fb9`
- `fwbase!FwReportReturnError` at `0x180054578`
- `fwbase!FwReportReturnError` at `0x18005462f`
- `fwbase!FwFree` at `0x1800545d8`
- `fwbase!FwFree` at `0x1800545d8`

## string_xrefs

- `0x180054354`: `CheckTokenMembership`

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
        unsigned int a8,
        unsigned int a9,
        __int64 a10)
{
  unsigned __int16 **v10; // rbx
  unsigned int v11; // r14d
  int v12; // r15d
  __int64 v15; // rcx
  signed int IsFirstTimeForProcess; // eax
  DWORD v17; // esi
  __int64 v18; // rcx
  __int64 v19; // rsi
  unsigned int v20; // r13d
  __int64 v21; // rdi
  int v22; // eax
  __int64 *v23; // r8
  __int64 v24; // rdx
  HANDLE v25; // r12
  int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // rdi
  HLOCAL v29; // rax
  void *v30; // rdi
  DWORD LastError; // eax
  const char *v32; // rdx
  WINBOOL v33; // eax
  NTSTATUS v34; // eax
  int v35; // eax
  __int64 v36; // rcx
  int v37; // edi
  int NotifierModern; // eax
  int v40; // [rsp+30h] [rbp-A1h]
  int v41; // [rsp+58h] [rbp-79h] BYREF
  int v42; // [rsp+5Ch] [rbp-75h]
  HANDLE TokenHandle; // [rsp+60h] [rbp-71h]
  __int64 v44; // [rsp+68h] [rbp-69h]
  int v45; // [rsp+70h] [rbp-61h]
  unsigned __int16 **v46; // [rsp+80h] [rbp-51h]
  HANDLE ProcessHandle; // [rsp+88h] [rbp-49h]
  __int64 v48; // [rsp+90h] [rbp-41h] BYREF
  DWORD cbSid; // [rsp+98h] [rbp-39h] BYREF
  LPWSTR ppBuffer; // [rsp+A0h] [rbp-31h] BYREF
  WINBOOL IsMember; // [rsp+A8h] [rbp-29h] BYREF
  DWORD ProcessInformation; // [rsp+ACh] [rbp-25h] BYREF
  DWORD pBytesReturned; // [rsp+B0h] [rbp-21h] BYREF

  v10 = (unsigned __int16 **)a10;
  v11 = 0;
  v46 = (unsigned __int16 **)a10;
  v44 = 0;
  v12 = 0;
  v45 = 0;
  v48 = a3;
  TokenHandle = a2;
  ProcessHandle = a1;
  v41 = 0;
  IsMember = 0;
  ProcessInformation = 0;
  ppBuffer = 0;
  pBytesReturned = 0;
  v42 = 1;
  v15 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_eb6086348bf630e9999f0bc45492fc6e_Traceguids);
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
  IsFirstTimeForProcess = FwNotifyIsFirstTimeForProcess(*(_DWORD *)(a10 + 8), a1, &v41);
  cbSid = IsFirstTimeForProcess;
  v17 = IsFirstTimeForProcess;
  if ( IsFirstTimeForProcess < 0 )
  {
    FwReportReturnError("FwNotifyOnDeny", (unsigned int)IsFirstTimeForProcess);
LABEL_99:
    if ( v10[2] )
      v11 = 32;
    v26 = v42;
LABEL_102:
    if ( v26 )
      goto LABEL_50;
    goto LABEL_51;
  }
  if ( !v41 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_eb6086348bf630e9999f0bc45492fc6e_Traceguids);
    goto LABEL_50;
  }
  if ( !a4 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_eb6086348bf630e9999f0bc45492fc6e_Traceguids);
    goto LABEL_51;
  }
  v19 = v48;
  v20 = 0;
  v21 = 0;
  v41 = 1;
  do
  {
    v22 = dword_180135A5C & FwGetProfileTypeFromProfileIndex((unsigned int)v21);
    v23 = gFwProfileMgr;
    if ( (*(_BYTE *)(v19 + 72) & 1) != 0 || (v18 = 160 * v21, LODWORD(gFwProfileMgr[20 * v21 + 648]) != 1) )
    {
      v18 = 160 * v21;
      if ( LODWORD(gFwProfileMgr[20 * v21 + 643]) )
      {
        if ( *(_DWORD *)((char *)&gFwProfileMgr[644] + v18) == 1 )
        {
          if ( v22 )
          {
            v11 |= 0x80u;
            v18 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
            {
              v24 = 16;
              goto LABEL_24;
            }
          }
        }
        else
        {
          if ( v22 )
            v12 = 1;
          v20 |= FwGetProfileTypeFromProfileIndex((unsigned int)v21);
        }
      }
      else if ( v22 )
      {
        *((_DWORD *)&v44 + v21) = 1;
        v18 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        {
          v24 = 15;
          goto LABEL_24;
        }
      }
    }
    else if ( v22 )
    {
      v11 |= 0x40u;
      v18 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      {
        v24 = 14;
LABEL_24:
        WPP_SF_(*(_QWORD *)(v18 + 16), v24, WPP_eb6086348bf630e9999f0bc45492fc6e_Traceguids);
      }
    }
    v21 = (unsigned int)(v21 + 1);
  }
  while ( (unsigned int)v21 < 3 );
  v10 = v46;
  v17 = cbSid;
  v25 = ProcessHandle;
  if ( v12 )
  {
    if ( (unsigned int)FwImageListHasImage(&gFwAuthApps, v46[2], v23) )
    {
      v11 = 8;
      v18 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
        goto LABEL_49;
      v27 = 17;
      goto LABEL_48;
    }
    if ( *((_DWORD *)v10 + 6) )
    {
      v11 = 1;
      v18 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 18, WPP_eb6086348bf630e9999f0bc45492fc6e_Traceguids);
      v12 = 1;
      goto LABEL_50;
    }
    v11 = 0;
    if ( v48 )
    {
      if ( (*(_BYTE *)(v48 + 72) & 0x10) != 0 )
      {
        IsMember = 1;
        goto LABEL_71;
      }
      v33 = 0;
      IsMember = 0;
    }
    else
    {
      if ( !CheckTokenMembership(TokenHandle, SidToCheck, &IsMember) )
      {
        LastError = GetLastError();
        v32 = "CheckTokenMembership";
LABEL_88:
        v35 = FwReportErrorAsWinError("FwNotifyOnDeny", v32, LastError);
LABEL_89:
        v17 = v35;
        if ( v35 >= 0 )
        {
          v26 = v42;
          v12 = v42;
          goto LABEL_102;
        }
        goto LABEL_98;
      }
      v33 = IsMember;
    }
    if ( !v33 )
    {
      v11 = 2;
      v18 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
        goto LABEL_49;
      v27 = 19;
LABEL_48:
      WPP_SF_(*(_QWORD *)(v18 + 16), v27, WPP_eb6086348bf630e9999f0bc45492fc6e_Traceguids);
LABEL_49:
      v12 = v41;
      goto LABEL_50;
    }
LABEL_71:
    v34 = NtQueryInformationProcess(v25, ProcessSessionInformation, &ProcessInformation, 4u, 0);
    if ( v34 < 0 )
    {
      v35 = FwReportErrorAsNtStatus("FwNotifyOnDeny", "NtQueryInformationProcess", (unsigned int)v34);
      goto LABEL_89;
    }
    if ( ProcessInformation != (unsigned int)RtlGetActiveConsoleId() )
    {
      if ( !(unsigned __int8)IsWTSFreeMemoryPresent()
        || !WTSQuerySessionInformationW(0, ProcessInformation, WTSConnectState, &ppBuffer, &pBytesReturned) )
      {
        LastError = GetLastError();
        v32 = "WTSQuerySessionInformation";
        goto LABEL_88;
      }
      if ( pBytesReturned != 4 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v36);
      if ( *(_DWORD *)ppBuffer > 1u )
      {
        v11 = 16;
        v18 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            20,
            WPP_eb6086348bf630e9999f0bc45492fc6e_Traceguids,
            *(unsigned int *)ppBuffer);
        goto LABEL_49;
      }
    }
    v37 = 0;
    if ( !(unsigned int)FwIsMachineJoinedToDomain() )
      v20 &= ~1u;
    if ( v20 != (a8 | a7) )
      v37 = v20 & dword_180135A5C & ~(a8 | a7 | a6);
    NotifierModern = FwNotifyCreateNotifierModern(
                       TokenHandle,
                       v48,
                       v20,
                       a6,
                       a5,
                       a7,
                       a8,
                       a9,
                       (unsigned __int64)v10[2],
                       v37);
    v17 = NotifierModern;
    if ( NotifierModern >= 0 )
    {
      NotifierModern = FwNotifyAddImageToAuthorizedApps(v20, a6, a8 | a7, v10[2], v37, v10);
      v17 = NotifierModern;
      if ( NotifierModern >= 0 )
        goto LABEL_49;
    }
    FwReportReturnError("FwNotifyOnDeny", (unsigned int)NotifierModern);
LABEL_98:
    v12 = v41;
    goto LABEL_99;
  }
  if ( !(_DWORD)v44 || !HIDWORD(v44) )
    goto LABEL_49;
  v12 = v41;
  if ( v45 )
  {
    v26 = 0;
    v11 = 4;
    goto LABEL_102;
  }
LABEL_50:
  FwAuditLogAppBlockedFromListening(v18, (unsigned int)dword_180135A5C, v10[2]);
LABEL_51:
  if ( v12 )
  {
    v28 = v48;
    FwNotifyTelemetryEventWriteQueryUser(v10, v11, (*(_DWORD *)(v48 + 72) >> 8) & 1);
    FwNotifySqmQueryUser(
      v10[2],
      v11,
      *((unsigned int *)v10 + 9),
      *((unsigned __int16 *)v10 + 16),
      (*(_DWORD *)(v28 + 72) >> 8) & 1);
  }
  if ( v11 && v10[2] )
  {
    v48 = 0;
    if ( (int)FwGetTokenInformation(TokenHandle, 1, &v48, 0) >= 0 )
    {
      LOWORD(v40) = *((_WORD *)v10 + 16);
      FwEventQueryUserNotDisplayed(
        v11,
        v10[2],
        *(_QWORD *)v48,
        *((unsigned int *)v10 + 7),
        *((_DWORD *)v10 + 9),
        v40,
        *((_DWORD *)v10 + 2));
      FwFree(v48);
    }
    else
    {
      cbSid = 68;
      v29 = LocalAlloc(0, 0x44u);
      v30 = v29;
      if ( v29 )
      {
        if ( CreateWellKnownSid(WinNullSid, 0, v29, &cbSid) )
        {
          LOWORD(v40) = *((_WORD *)v10 + 16);
          FwEventQueryUserNotDisplayed(
            v11,
            v10[2],
            v30,
            *((unsigned int *)v10 + 7),
            *((_DWORD *)v10 + 9),
            v40,
            *((_DWORD *)v10 + 2));
        }
        LocalFree(v30);
      }
    }
  }
  if ( _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0] )
    MicrosoftTelemetryAssertTriggeredNoArgs(v18);
  if ( ppBuffer && (unsigned __int8)IsWTSFreeMemoryPresent() )
    WTSFreeMemory(ppBuffer);
  if ( (v17 & 0x80000000) != 0 )
    return (unsigned int)FwReportReturnError("FwNotifyOnDeny", v17);
  return v17;
}

```

## disassembly

```asm
0x180053eb4  mov     rax, rsp
0x180053eb7  mov     [rax+20h], rbx
0x180053ebb  push    rbp
0x180053ebc  push    rsi
0x180053ebd  push    rdi
0x180053ebe  push    r12
0x180053ec0  push    r13
0x180053ec2  push    r14
0x180053ec4  push    r15
0x180053ec6  lea     rbp, [rax-3Fh]
0x180053eca  sub     rsp, 0D0h
0x180053ed1  movaps  xmmword ptr [rax-48h], xmm6
0x180053ed5  mov     rax, cs:__security_cookie
0x180053edc  xor     rax, rsp
0x180053edf  mov     [rbp+37h+var_50], rax
0x180053ee3  mov     rbx, [rbp+37h+arg_48]
0x180053eea  xor     eax, eax
0x180053eec  xor     r14d, r14d
0x180053eef  mov     [rbp+37h+var_88], rbx
0x180053ef3  mov     [rbp+37h+var_A0], rax
0x180053ef7  xor     r15d, r15d
0x180053efa  mov     [rbp+37h+var_98], eax
0x180053efd  mov     edi, r9d
0x180053f00  mov     [rbp+37h+var_78], r8
0x180053f04  mov     r12, rcx
0x180053f07  mov     [rbp+37h+TokenHandle], rdx
0x180053f0b  xorps   xmm6, xmm6
0x180053f0e  mov     [rbp+37h+ProcessHandle], rcx
0x180053f12  mov     [rbp+37h+var_B0], 0
0x180053f19  mov     [rbp+37h+IsMember], 0
0x180053f20  mov     [rbp+37h+ProcessInformation], 0
0x180053f27  mov     [rbp+37h+ppBuffer], 0
0x180053f2f  mov     [rbp+37h+pBytesReturned], 0
0x180053f36  mov     [rbp+37h+var_AC], 1
0x180053f3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180053f44  lea     r13, WPP_GLOBAL_Control
0x180053f4b  cmp     rcx, r13
0x180053f4e  jz      short loc_180053F98
0x180053f50  test    byte ptr [rcx+1Ch], 8
0x180053f54  jz      short loc_180053F70
0x180053f56  mov     rcx, [rcx+10h]
0x180053f5a  lea     edx, [rax+0Ah]
0x180053f5d  lea     r8, WPP_eb6086348bf630e9999f0bc45492fc6e_Traceguids
0x180053f64  call    WPP_SF_
0x180053f69  mov     rcx, cs:WPP_GLOBAL_Control
0x180053f70  cmp     rcx, r13
0x180053f73  jz      short loc_180053F98
0x180053f75  test    byte ptr [rcx+1Ch], 4
0x180053f79  jz      short loc_180053F98
0x180053f7b  movzx   eax, word ptr [rbx+20h]
0x180053f7f  mov     r9, [rbx+10h]
0x180053f83  mov     rcx, [rcx+10h]
0x180053f87  mov     word ptr [rsp+100h+var_D8], ax
0x180053f8c  mov     eax, [rbx+24h]
0x180053f8f  mov     dword ptr [rsp+100h+ReturnLength], eax
0x180053f93  call    WPP_SF_SdH
0x180053f98  mov     ecx, [rbx+8]; unsigned int
0x180053f9b  lea     r8, [rbp+37h+var_B0]; int *
0x180053f9f  mov     rdx, r12; void *
0x180053fa2  call    ?FwNotifyIsFirstTimeForProcess@@YAJKPEAXPEAH@Z; FwNotifyIsFirstTimeForProcess(ulong,void *,int *)
0x180053fa7  mov     [rbp+37h+cbSid], eax
0x180053faa  mov     esi, eax
0x180053fac  test    eax, eax
0x180053fae  jns     short loc_180053FCA
0x180053fb0  mov     edx, eax
0x180053fb2  lea     rcx, aFwnotifyondeny; "FwNotifyOnDeny"
0x180053fb9  call    cs:__imp_FwReportReturnError
0x180053fc0  nop     dword ptr [rax+rax+00h]
0x180053fc5  jmp     loc_180054588
0x180053fca  cmp     [rbp+37h+var_B0], r14d
0x180053fce  jnz     short loc_180054004
0x180053fd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180053fd7  cmp     rcx, r13
0x180053fda  jz      loc_1800541CD
0x180053fe0  test    byte ptr [rcx+1Ch], 4
0x180053fe4  jz      loc_1800541CD
0x180053fea  mov     rcx, [rcx+10h]
0x180053fee  lea     r8, WPP_eb6086348bf630e9999f0bc45492fc6e_Traceguids
0x180053ff5  mov     edx, 0Ch
0x180053ffa  call    WPP_SF_
0x180053fff  jmp     loc_1800541CD
0x180054004  test    edi, edi
0x180054006  jnz     short loc_18005403A
0x180054008  mov     rcx, cs:WPP_GLOBAL_Control
0x18005400f  cmp     rcx, r13
0x180054012  jz      loc_1800541DC
0x180054018  test    byte ptr [rcx+1Ch], 4
0x18005401c  jz      loc_1800541DC
0x180054022  mov     rcx, [rcx+10h]
0x180054026  lea     edx, [rdi+0Dh]
0x180054029  lea     r8, WPP_eb6086348bf630e9999f0bc45492fc6e_Traceguids
0x180054030  call    WPP_SF_
0x180054035  jmp     loc_1800541DC
0x18005403a  mov     rsi, [rbp+37h+var_78]
0x18005403e  lea     rbx, WPP_GLOBAL_Control
0x180054045  xor     r13d, r13d
0x180054048  xor     edi, edi
0x18005404a  lea     r12d, [r13+1]
0x18005404e  mov     [rbp+37h+var_B0], r12d
0x180054052  mov     ecx, edi
0x180054054  call    cs:__imp_FwGetProfileTypeFromProfileIndex
0x18005405b  nop     dword ptr [rax+rax+00h]
0x180054060  and     eax, cs:dword_180135A5C
0x180054066  lea     r8, gFwProfileMgr
0x18005406d  test    [rsi+48h], r12b
0x180054071  jnz     short loc_1800540C2
0x180054073  lea     rcx, [rdi+rdi*4]
0x180054077  shl     rcx, 5
0x18005407b  cmp     [rcx+r8+1440h], r12d
0x180054083  jnz     short loc_1800540C2
0x180054085  test    eax, eax
0x180054087  jz      loc_18005413A
0x18005408d  or      r14d, 40h
0x180054091  mov     rcx, cs:WPP_GLOBAL_Control
0x180054098  cmp     rcx, rbx
0x18005409b  jz      loc_18005413A
0x1800540a1  test    byte ptr [rcx+1Ch], 4
0x1800540a5  jz      loc_18005413A
0x1800540ab  mov     edx, 0Eh
0x1800540b0  mov     rcx, [rcx+10h]
0x1800540b4  lea     r8, WPP_eb6086348bf630e9999f0bc45492fc6e_Traceguids
0x1800540bb  call    WPP_SF_
0x1800540c0  jmp     short loc_18005413A
0x1800540c2  lea     rcx, [rdi+rdi*4]
0x1800540c6  shl     rcx, 5
0x1800540ca  cmp     dword ptr [rcx+r8+1418h], 0
0x1800540d3  jnz     short loc_1800540F7
0x1800540d5  test    eax, eax
0x1800540d7  jz      short loc_18005413A
0x1800540d9  mov     dword ptr [rbp+rdi*4+37h+var_A0], r12d
0x1800540de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800540e5  cmp     rcx, rbx
0x1800540e8  jz      short loc_18005413A
0x1800540ea  test    byte ptr [rcx+1Ch], 4
0x1800540ee  jz      short loc_18005413A
0x1800540f0  mov     edx, 0Fh
0x1800540f5  jmp     short loc_1800540B0
0x1800540f7  cmp     [rcx+r8+1420h], r12d
0x1800540ff  jnz     short loc_180054123
0x180054101  test    eax, eax
0x180054103  jz      short loc_18005413A
0x180054105  bts     r14d, 7
0x18005410a  mov     rcx, cs:WPP_GLOBAL_Control
0x180054111  cmp     rcx, rbx
0x180054114  jz      short loc_18005413A
0x180054116  test    byte ptr [rcx+1Ch], 4
0x18005411a  jz      short loc_18005413A
0x18005411c  mov     edx, 10h
0x180054121  jmp     short loc_1800540B0
0x180054123  test    eax, eax
0x180054125  mov     ecx, edi
0x180054127  cmovnz  r15d, r12d
0x18005412b  call    cs:__imp_FwGetProfileTypeFromProfileIndex
0x180054132  nop     dword ptr [rax+rax+00h]
0x180054137  or      r13d, eax
0x18005413a  add     edi, r12d
0x18005413d  cmp     edi, 3
0x180054140  jb      loc_180054052
0x180054146  mov     rbx, [rbp+37h+var_88]
0x18005414a  mov     esi, [rbp+37h+cbSid]
0x18005414d  mov     r12, [rbp+37h+ProcessHandle]
0x180054151  test    r15d, r15d
0x180054154  jnz     short loc_180054177
0x180054156  cmp     dword ptr [rbp+37h+var_A0], 0
0x18005415a  jz      short loc_1800541C9
0x18005415c  cmp     dword ptr [rbp+37h+var_A0+4], 0
0x180054160  jz      short loc_1800541C9
0x180054162  cmp     [rbp+37h+var_98], 0
0x180054166  mov     r15d, [rbp+37h+var_B0]
0x18005416a  jz      short loc_1800541CD
0x18005416c  xor     eax, eax
0x18005416e  lea     r14d, [rax+4]
0x180054172  jmp     loc_180054599
0x180054177  mov     rdx, [rbx+10h]
0x18005417b  lea     rcx, ?gFwAuthApps@@3UFW_AUTHORIZED_APPS_COMPONENT_@@A; FW_AUTHORIZED_APPS_COMPONENT_ gFwAuthApps
0x180054182  call    cs:__imp_FwImageListHasImage
0x180054189  nop     dword ptr [rax+rax+00h]
0x18005418e  test    eax, eax
0x180054190  jz      loc_1800542DC
0x180054196  mov     r14d, 8
0x18005419c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800541a3  lea     rax, WPP_GLOBAL_Control
0x1800541aa  cmp     rcx, rax
0x1800541ad  jz      short loc_1800541C9
0x1800541af  test    byte ptr [rcx+1Ch], 4
0x1800541b3  jz      short loc_1800541C9
0x1800541b5  lea     edx, [r14+9]
0x1800541b9  mov     rcx, [rcx+10h]
0x1800541bd  lea     r8, WPP_eb6086348bf630e9999f0bc45492fc6e_Traceguids
0x1800541c4  call    WPP_SF_
0x1800541c9  mov     r15d, [rbp+37h+var_B0]
0x1800541cd  mov     r8, [rbx+10h]
0x1800541d1  mov     edx, cs:dword_180135A5C
0x1800541d7  call    FwAuditLogAppBlockedFromListening
0x1800541dc  test    r15d, r15d
0x1800541df  mov     r15d, 1
0x1800541e5  jz      short loc_180054223
0x1800541e7  mov     rdi, [rbp+37h+var_78]
0x1800541eb  mov     edx, r14d
0x1800541ee  mov     rcx, rbx
0x1800541f1  mov     r8d, [rdi+48h]
0x1800541f5  shr     r8d, 8
0x1800541f9  and     r8d, r15d
0x1800541fc  call    ?FwNotifyTelemetryEventWriteQueryUser@@YAXPEAUICF_DYNAMIC_FW_PORT_@@W4_tag_QU_NOT_SHOWN_REASON@@H@Z; FwNotifyTelemetryEventWriteQueryUser(ICF_DYNAMIC_FW_PORT_ *,_tag_QU_NOT_SHOWN_REASON,int)
0x180054201  mov     eax, [rdi+48h]
0x180054204  mov     edx, r14d
0x180054207  movzx   r9d, word ptr [rbx+20h]
0x18005420c  mov     r8d, [rbx+24h]
0x180054210  mov     rcx, [rbx+10h]
0x180054214  shr     eax, 8
0x180054217  and     eax, r15d
0x18005421a  mov     dword ptr [rsp+100h+ReturnLength], eax
0x18005421e  call    ?FwNotifySqmQueryUser@@YAXPEBGW4_tag_QU_NOT_SHOWN_REASON@@KKH@Z; FwNotifySqmQueryUser(ushort const *,_tag_QU_NOT_SHOWN_REASON,ulong,ulong,int)
0x180054223  test    r14d, r14d
0x180054226  jz      loc_1800545E4
0x18005422c  cmp     qword ptr [rbx+10h], 0
0x180054231  jz      loc_1800545E4
0x180054237  mov     rcx, [rbp+37h+TokenHandle]
0x18005423b  lea     r8, [rbp+37h+var_78]
0x18005423f  xor     r9d, r9d
0x180054242  mov     [rbp+37h+var_78], 0
0x18005424a  mov     edx, r15d
0x18005424d  call    cs:__imp_FwGetTokenInformation
0x180054254  nop     dword ptr [rax+rax+00h]
0x180054259  test    eax, eax
0x18005425b  jns     loc_1800545A6
0x180054261  mov     edx, 44h ; 'D'; uBytes
0x180054266  xor     ecx, ecx; uFlags
0x180054268  mov     [rbp+37h+cbSid], edx
0x18005426b  call    cs:__imp_LocalAlloc
0x180054272  nop     dword ptr [rax+rax+00h]
0x180054277  mov     rdi, rax
0x18005427a  test    rax, rax
0x18005427d  jz      loc_1800545E4
0x180054283  lea     r9, [rbp+37h+cbSid]; cbSid
0x180054287  mov     r8, rax; pSid
0x18005428a  xor     edx, edx; DomainSid
0x18005428c  xor     ecx, ecx; WellKnownSidType
0x18005428e  call    cs:__imp_CreateWellKnownSid
0x180054295  nop     dword ptr [rax+rax+00h]
0x18005429a  test    eax, eax
0x18005429c  jz      short loc_1800542C8
0x18005429e  mov     edx, [rbx+8]
0x1800542a1  mov     r8, rdi
0x1800542a4  movzx   eax, word ptr [rbx+20h]
0x1800542a8  mov     ecx, r14d
0x1800542ab  mov     r9d, [rbx+1Ch]
0x1800542af  mov     [rsp+100h+var_D0], edx
0x1800542b3  mov     rdx, [rbx+10h]
0x1800542b7  mov     word ptr [rsp+100h+var_D8], ax
0x1800542bc  mov     eax, [rbx+24h]
0x1800542bf  mov     dword ptr [rsp+100h+ReturnLength], eax
0x1800542c3  call    FwEventQueryUserNotDisplayed
0x1800542c8  mov     rcx, rdi; hMem
0x1800542cb  call    cs:__imp_LocalFree
0x1800542d2  nop     dword ptr [rax+rax+00h]
0x1800542d7  jmp     loc_1800545E4
0x1800542dc  cmp     dword ptr [rbx+18h], 0
0x1800542e0  jz      short loc_18005431D
0x1800542e2  mov     r14d, 1
0x1800542e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800542ef  lea     rax, WPP_GLOBAL_Control
0x1800542f6  cmp     rcx, rax
0x1800542f9  jz      short loc_180054315
0x1800542fb  test    byte ptr [rcx+1Ch], 4
0x1800542ff  jz      short loc_180054315
0x180054301  mov     rcx, [rcx+10h]
0x180054305  lea     edx, [r14+11h]
0x180054309  lea     r8, WPP_eb6086348bf630e9999f0bc45492fc6e_Traceguids
0x180054310  call    WPP_SF_
0x180054315  mov     r15d, r14d
0x180054318  jmp     loc_1800541CD
0x18005431d  mov     r15, [rbp+37h+var_78]
0x180054321  xor     r14d, r14d
0x180054324  test    r15, r15
0x180054327  jnz     short loc_180054365
0x180054329  mov     rdx, qword ptr cs:SidToCheck; SidToCheck
0x180054330  lea     r8, [rbp+37h+IsMember]; IsMember
0x180054334  mov     rcx, [rbp+37h+TokenHandle]; TokenHandle
0x180054338  call    cs:__imp_CheckTokenMembership
0x18005433f  nop     dword ptr [rax+rax+00h]
0x180054344  test    eax, eax
0x180054346  jnz     short loc_180054360
0x180054348  call    cs:__imp_GetLastError
0x18005434f  nop     dword ptr [rax+rax+00h]
0x180054354  lea     rdx, aChecktokenmemb; "CheckTokenMembership"
0x18005435b  jmp     loc_1800544AA
0x180054360  mov     eax, [rbp+37h+IsMember]
0x180054363  jmp     short loc_1800543C0
0x180054365  test    byte ptr [r15+48h], 10h
0x18005436a  jz      short loc_1800543BB
0x18005436c  mov     [rbp+37h+IsMember], 1
0x180054373  mov     r9d, 4; ProcessInformationLength
0x180054379  mov     [rsp+100h+ReturnLength], r14; ReturnLength
0x18005437e  lea     r8, [rbp+37h+ProcessInformation]; ProcessInformation
0x180054382  mov     rcx, r12; ProcessHandle
0x180054385  lea     edx, [r9+14h]; ProcessInformationClass
0x180054389  call    cs:__imp_NtQueryInformationProcess
0x180054390  nop     dword ptr [rax+rax+00h]
0x180054395  test    eax, eax
  ... truncated ...
```
