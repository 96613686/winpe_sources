# CSrApiViewerAxHost::GetShadowInvitation(ushort const *,ulong,ushort *,ulong,CSrApiViewerAxHost::EShadowClientThreadState *)

- ea: `0x1400af6e8`
- end: `0x1400afe01`
- name: `?GetShadowInvitation@CSrApiViewerAxHost@@AEAAJPEBGKPEAGKPEAW4EShadowClientThreadState@1@@Z`
- size: `1817`
- prototype: `__int64 __usercall@<rax>(CSrApiViewerAxHost *__hidden this@<rcx>, LPWSTR pServerName@<rdx>, DWORD SessionId@<r8d>, unsigned __int16 *@<r9>, unsigned int, enum CSrApiViewerAxHost::EShadowClientThreadState *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400b1c08`

## callees

- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x1400af6e8`
- `0x1400b2084`
- `0x1400b2974`
- `0x1400b2cd0`
- `0x1400b30dc`
- `0x1400b3130`

## import_xrefs

- `WTSAPI32!WTSFreeMemory` at `0x1400afdc8`
- `WTSAPI32!WTSFreeMemory` at `0x1400afdc8`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x1400af958`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x1400af958`
- `WTSAPI32!WTSOpenServerW` at `0x1400af8b2`
- `WTSAPI32!WTSOpenServerW` at `0x1400af8b2`
- `KERNEL32!ProcessIdToSessionId` at `0x1400af762`
- `KERNEL32!ProcessIdToSessionId` at `0x1400af762`
- `KERNEL32!GetCurrentProcessId` at `0x1400af752`
- `KERNEL32!GetCurrentProcessId` at `0x1400af752`
- `KERNEL32!GetLastError` at `0x1400af76c`
- `KERNEL32!GetLastError` at `0x1400af8dc`
- `KERNEL32!GetLastError` at `0x1400af919`
- `KERNEL32!GetLastError` at `0x1400af962`
- `KERNEL32!GetLastError` at `0x1400af968`
- `KERNEL32!GetLastError` at `0x1400af76c`
- `KERNEL32!GetLastError` at `0x1400af8dc`
- `KERNEL32!GetLastError` at `0x1400af919`
- `KERNEL32!GetLastError` at `0x1400af962`
- `KERNEL32!GetLastError` at `0x1400af968`
- `RPCRT4!RpcBindingFree` at `0x1400afde9`
- `RPCRT4!RpcBindingFree` at `0x1400afde9`
- `RPCRT4!I_RpcExceptionFilter` at `0x140113600`
- `RPCRT4!I_RpcExceptionFilter` at `0x140113600`

## pseudocode

```c
__int64 __fastcall CSrApiViewerAxHost::GetShadowInvitation(
        CSrApiViewerAxHost *this,
        LPWSTR pServerName,
        DWORD SessionId,
        unsigned __int16 *a4,
        unsigned int a5,
        enum CSrApiViewerAxHost::EShadowClientThreadState *a6)
{
  unsigned int IsLocalServer; // eax
  DWORD CurrentProcessId; // eax
  signed int LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v13; // rdx
  unsigned int v14; // r12d
  DWORD v15; // ecx
  PVOID *v16; // rax
  unsigned int v17; // eax
  unsigned int v18; // eax
  HANDLE v19; // rax
  signed int v20; // eax
  unsigned int v21; // ebx
  unsigned int v22; // eax
  signed int v23; // eax
  unsigned int v24; // eax
  __int64 v25; // rdx
  struct _WTSINFOW *v26; // r13
  PVOID *v27; // rax
  WTS_CONNECTSTATE_CLASS State; // ebx
  unsigned int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r8
  unsigned int v32; // eax
  unsigned int v33; // eax
  int v34; // edx
  unsigned __int16 *v35; // r13
  unsigned int v36; // eax
  unsigned int v37; // eax
  int v38; // ecx
  unsigned int v39; // eax
  __int64 v41; // [rsp+28h] [rbp-70h]
  __int64 v42; // [rsp+28h] [rbp-70h]
  DWORD pBytesReturned; // [rsp+40h] [rbp-58h] BYREF
  unsigned int v44; // [rsp+44h] [rbp-54h]
  signed int v45; // [rsp+48h] [rbp-50h]
  int v46; // [rsp+4Ch] [rbp-4Ch] BYREF
  LPWSTR ppBuffer; // [rsp+50h] [rbp-48h] BYREF
  RPC_BINDING_HANDLE Binding[8]; // [rsp+58h] [rbp-40h] BYREF
  DWORD pSessionId; // [rsp+A8h] [rbp+10h] BYREF
  DWORD v50; // [rsp+B0h] [rbp+18h]
  unsigned __int16 *v51; // [rsp+B8h] [rbp+20h]

  v51 = a4;
  v50 = SessionId;
  v46 = 0;
  a5 = 2;
  pBytesReturned = 0;
  ppBuffer = 0;
  pSessionId = 0;
  Binding[0] = 0;
  IsLocalServer = 0;
  v44 = 0;
  if ( pServerName && *pServerName )
  {
    IsLocalServer = CSrApiViewerAxHost::s_IsLocalServer(pServerName);
    v44 = IsLocalServer;
  }
  if ( !IsLocalServer )
  {
    CurrentProcessId = GetCurrentProcessId();
    if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_11;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v13 = 19;
LABEL_10:
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        &WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids,
        CurrentThreadActivityIdPrefix,
        LastError);
LABEL_11:
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError >= 0 )
        LastError = -2147467259;
      goto LABEL_15;
    }
    v15 = pSessionId;
    if ( SessionId == pSessionId )
    {
      *((_DWORD *)this + 56) = 13;
      v16 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids, v17, 0);
        v15 = pSessionId;
        v16 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( SessionId == v15 )
      {
        if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 8) != 0 && *((_BYTE *)v16 + 25) >= 2u )
        {
          v18 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            &WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids,
            v18,
            -2147467259);
        }
        LastError = -2147467259;
        goto LABEL_15;
      }
    }
  }
  if ( pServerName )
  {
    if ( *pServerName )
    {
      v19 = WTSOpenServerW(pServerName);
      *((_QWORD *)this + 27) = v19;
      if ( !v19 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v20 = GetLastError();
          v21 = v20;
          if ( v20 > 0 )
            v21 = (unsigned __int16)v20 | 0x80070000;
          v22 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids, v22, v21);
        }
        v23 = GetLastError();
        LastError = v23;
        if ( v23 > 0 )
          LastError = (unsigned __int16)v23 | 0x80070000;
        goto LABEL_15;
      }
    }
  }
  if ( !WTSQuerySessionInformationW(*((HANDLE *)this + 27), SessionId, WTSSessionInfo, &ppBuffer, &pBytesReturned) )
  {
    GetLastError();
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_11;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v13 = 23;
    goto LABEL_10;
  }
  if ( !ppBuffer )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_49;
    }
    v24 = RdpWppGetCurrentThreadActivityIdPrefix();
    v25 = 24;
LABEL_48:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v25,
      &WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids,
      v24,
      -2147418113);
LABEL_49:
    LastError = -2147418113;
LABEL_15:
    v14 = 2;
    goto LABEL_100;
  }
  if ( pBytesReturned != 216 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_49;
    }
    v24 = RdpWppGetCurrentThreadActivityIdPrefix();
    v25 = 25;
    goto LABEL_48;
  }
  v26 = (struct _WTSINFOW *)ppBuffer;
  if ( !*(_DWORD *)ppBuffer )
    goto LABEL_60;
  *((_DWORD *)this + 56) = 14;
  v27 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    State = v26->State;
    v29 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DLLD(*((_QWORD *)WPP_GLOBAL_Control + 2), v30, v31, v29, v50, State, 0);
LABEL_60:
    v27 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v26->State )
  {
    if ( v27 != &WPP_GLOBAL_Control && (*((_BYTE *)v27 + 28) & 8) != 0 && *((_BYTE *)v27 + 25) >= 2u )
    {
      v32 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        &WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids,
        v32,
        -2147024875);
    }
    LastError = -2147024875;
    goto LABEL_15;
  }
  LastError = CSrApiViewerAxHost::SetTitle(this, v26);
  if ( LastError < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v33 = RdpWppGetCurrentThreadActivityIdPrefix();
      v34 = 28;
LABEL_72:
      LODWORD(v41) = LastError;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v34,
        (unsigned int)&WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids,
        v33,
        (__int64)"SetTitle failed",
        v41);
      goto LABEL_15;
    }
LABEL_83:
    v14 = a5;
    goto LABEL_100;
  }
  LastError = CSrApiViewerAxHost::s_GetSessEnvPublicBinding(v44, pServerName, Binding);
  if ( LastError < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v33 = RdpWppGetCurrentThreadActivityIdPrefix();
      v34 = 29;
      goto LABEL_72;
    }
    goto LABEL_83;
  }
  v35 = v51;
  LastError = RpcShadow2(Binding[0], v50, *((_DWORD *)this + 34), *((_DWORD *)this + 35), (__int64)&v46, (__int64)v51);
  v45 = LastError;
  v14 = 2;
  if ( LastError < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v36 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(v42) = LastError;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        (unsigned int)&WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids,
        v36,
        (__int64)"RpcShadow2 failed",
        v42);
      goto LABEL_100;
    }
    goto LABEL_83;
  }
  if ( _InterlockedExchange((volatile __int32 *)&CSrApiViewerAxHost::s_eShadowClientThreadState, 1) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v37 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids, v37, 0);
    }
    LastError = 0;
  }
  else
  {
    v14 = 1;
    v38 = v46;
    if ( !v46 )
      goto LABEL_99;
    if ( (unsigned __int64)v46 < 7 )
      *((_DWORD *)this + 56) = *((_DWORD *)qword_140135570 + v46);
    if ( v38 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v39 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          33,
          &WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids,
          v39,
          -2147024891);
      }
      LastError = -2147024891;
    }
    else
    {
LABEL_99:
      v35[0x1FFF] = 0;
    }
  }
LABEL_100:
  if ( ppBuffer )
    WTSFreeMemory(ppBuffer);
  if ( LastError >= 0 )
    *(_DWORD *)a6 = v14;
  if ( Binding[0] )
    RpcBindingFree(Binding);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1400af6e8  mov     rax, rsp
0x1400af6eb  mov     [rax+20h], r9
0x1400af6ef  mov     [rax+18h], r8d
0x1400af6f3  mov     [rax+8], rcx
0x1400af6f7  push    rbx
0x1400af6f8  push    rsi
0x1400af6f9  push    rdi
0x1400af6fa  push    r12
0x1400af6fc  push    r13
0x1400af6fe  push    r14
0x1400af700  push    r15
0x1400af702  sub     rsp, 60h
0x1400af706  mov     ebx, r8d
0x1400af709  mov     r12, rdx
0x1400af70c  mov     r15, rcx
0x1400af70f  xor     edi, edi
0x1400af711  mov     [rax-4Ch], edi
0x1400af714  lea     r14d, [rdi+2]
0x1400af718  mov     [rsp+98h+arg_20], r14d
0x1400af720  mov     [rax-58h], edi
0x1400af723  mov     [rax-48h], rdi
0x1400af727  mov     [rax+10h], edi
0x1400af72a  mov     [rax-40h], rdi
0x1400af72e  mov     eax, edi
0x1400af730  mov     [rsp+98h+var_54], eax
0x1400af734  test    rdx, rdx
0x1400af737  jz      short loc_1400AF74A
0x1400af739  cmp     [rdx], di
0x1400af73c  jz      short loc_1400AF74A
0x1400af73e  mov     rcx, rdx
0x1400af741  call    ?s_IsLocalServer@CSrApiViewerAxHost@@CA?AW4EServerLocality@1@PEBG@Z; CSrApiViewerAxHost::s_IsLocalServer(ushort const *)
0x1400af746  mov     [rsp+98h+var_54], eax
0x1400af74a  test    eax, eax
0x1400af74c  jnz     loc_1400AF894
0x1400af752  call    cs:__imp_GetCurrentProcessId
0x1400af758  mov     ecx, eax; dwProcessId
0x1400af75a  lea     rdx, [rsp+98h+pSessionId]; pSessionId
0x1400af762  call    cs:__imp_ProcessIdToSessionId
0x1400af768  test    eax, eax
0x1400af76a  jnz     short loc_1400AF7DA
0x1400af76c  call    cs:__imp_GetLastError
0x1400af772  mov     ebx, eax
0x1400af774  lea     rsi, WPP_GLOBAL_Control
0x1400af77b  mov     rax, cs:WPP_GLOBAL_Control
0x1400af782  cmp     rax, rsi
0x1400af785  jz      short loc_1400AF7BB
0x1400af787  test    byte ptr [rax+1Ch], 8
0x1400af78b  jz      short loc_1400AF7BB
0x1400af78d  cmp     [rax+19h], r14b
0x1400af791  jb      short loc_1400AF7BB
0x1400af793  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400af798  mov     edx, 13h
0x1400af79d  mov     dword ptr [rsp+98h+pBytesReturned], ebx
0x1400af7a1  mov     r9d, eax
0x1400af7a4  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400af7ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400af7b2  mov     rcx, [rcx+10h]
0x1400af7b6  call    WPP_SF_Dd
0x1400af7bb  test    ebx, ebx
0x1400af7bd  jle     short loc_1400AF7C8
0x1400af7bf  movzx   ebx, bx
0x1400af7c2  or      ebx, 80070000h
0x1400af7c8  mov     eax, 80004005h
0x1400af7cd  test    ebx, ebx
0x1400af7cf  cmovns  ebx, eax
0x1400af7d2  mov     r12d, r14d
0x1400af7d5  jmp     loc_1400AFDBE
0x1400af7da  mov     ecx, [rsp+98h+pSessionId]
0x1400af7e1  cmp     ebx, ecx
0x1400af7e3  jnz     loc_1400AF894
0x1400af7e9  mov     dword ptr [r15+0E0h], 0Dh
0x1400af7f4  lea     rsi, WPP_GLOBAL_Control
0x1400af7fb  mov     rax, cs:WPP_GLOBAL_Control
0x1400af802  cmp     rax, rsi
0x1400af805  jz      short loc_1400AF849
0x1400af807  test    byte ptr [rax+1Ch], 1
0x1400af80b  jz      short loc_1400AF849
0x1400af80d  cmp     [rax+19h], r14b
0x1400af811  jb      short loc_1400AF849
0x1400af813  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400af818  mov     edx, 14h
0x1400af81d  mov     dword ptr [rsp+98h+pBytesReturned], edi
0x1400af821  mov     r9d, eax
0x1400af824  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400af82b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400af832  mov     rcx, [rcx+10h]
0x1400af836  call    WPP_SF_Dd
0x1400af83b  mov     ecx, [rsp+98h+pSessionId]
0x1400af842  mov     rax, cs:WPP_GLOBAL_Control
0x1400af849  cmp     ebx, ecx
0x1400af84b  jnz     short loc_1400AF89B
0x1400af84d  cmp     rax, rsi
0x1400af850  jz      short loc_1400AF88A
0x1400af852  test    byte ptr [rax+1Ch], 8
0x1400af856  jz      short loc_1400AF88A
0x1400af858  cmp     [rax+19h], r14b
0x1400af85c  jb      short loc_1400AF88A
0x1400af85e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400af863  mov     edx, 15h
0x1400af868  mov     dword ptr [rsp+98h+pBytesReturned], 80004005h
0x1400af870  mov     r9d, eax
0x1400af873  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400af87a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400af881  mov     rcx, [rcx+10h]
0x1400af885  call    WPP_SF_Dd
0x1400af88a  mov     ebx, 80004005h
0x1400af88f  jmp     loc_1400AF7D2
0x1400af894  lea     rsi, WPP_GLOBAL_Control
0x1400af89b  test    r12, r12
0x1400af89e  jz      loc_1400AF937
0x1400af8a4  cmp     [r12], di
0x1400af8a9  jz      loc_1400AF937
0x1400af8af  mov     rcx, r12; pServerName
0x1400af8b2  call    cs:__imp_WTSOpenServerW
0x1400af8b8  mov     [r15+0D8h], rax
0x1400af8bf  test    rax, rax
0x1400af8c2  jnz     short loc_1400AF937
0x1400af8c4  mov     rax, cs:WPP_GLOBAL_Control
0x1400af8cb  cmp     rax, rsi
0x1400af8ce  jz      short loc_1400AF919
0x1400af8d0  test    byte ptr [rax+1Ch], 8
0x1400af8d4  jz      short loc_1400AF919
0x1400af8d6  cmp     [rax+19h], r14b
0x1400af8da  jb      short loc_1400AF919
0x1400af8dc  call    cs:__imp_GetLastError
0x1400af8e2  mov     ebx, eax
0x1400af8e4  test    eax, eax
0x1400af8e6  jle     short loc_1400AF8F1
0x1400af8e8  movzx   ebx, ax
0x1400af8eb  or      ebx, 80070000h
0x1400af8f1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400af8f6  mov     edx, 16h
0x1400af8fb  mov     dword ptr [rsp+98h+pBytesReturned], ebx
0x1400af8ff  mov     r9d, eax
0x1400af902  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400af909  mov     rcx, cs:WPP_GLOBAL_Control
0x1400af910  mov     rcx, [rcx+10h]
0x1400af914  call    WPP_SF_Dd
0x1400af919  call    cs:__imp_GetLastError
0x1400af91f  mov     ebx, eax
0x1400af921  test    eax, eax
0x1400af923  jle     loc_1400AF7D2
0x1400af929  movzx   ebx, ax
0x1400af92c  or      ebx, 80070000h
0x1400af932  jmp     loc_1400AF7D2
0x1400af937  lea     rax, [rsp+98h+var_58]
0x1400af93c  mov     [rsp+98h+pBytesReturned], rax; pBytesReturned
0x1400af941  lea     r9, [rsp+98h+ppBuffer]; ppBuffer
0x1400af946  mov     r13d, 18h
0x1400af94c  mov     r8d, r13d; WTSInfoClass
0x1400af94f  mov     edx, ebx; SessionId
0x1400af951  mov     rcx, [r15+0D8h]; hServer
0x1400af958  call    cs:__imp_WTSQuerySessionInformationW
0x1400af95e  test    eax, eax
0x1400af960  jnz     short loc_1400AF9A2
0x1400af962  call    cs:__imp_GetLastError
0x1400af968  call    cs:__imp_GetLastError
0x1400af96e  mov     ebx, eax
0x1400af970  mov     rax, cs:WPP_GLOBAL_Control
0x1400af977  cmp     rax, rsi
0x1400af97a  jz      loc_1400AF7BB
0x1400af980  test    byte ptr [rax+1Ch], 8
0x1400af984  jz      loc_1400AF7BB
0x1400af98a  cmp     [rax+19h], r14b
0x1400af98e  jb      loc_1400AF7BB
0x1400af994  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400af999  lea     edx, [r13-1]
0x1400af99d  jmp     loc_1400AF79D
0x1400af9a2  cmp     [rsp+98h+ppBuffer], rdi
0x1400af9a7  jnz     short loc_1400AF9F5
0x1400af9a9  mov     rax, cs:WPP_GLOBAL_Control
0x1400af9b0  cmp     rax, rsi
0x1400af9b3  jz      short loc_1400AF9EB
0x1400af9b5  test    byte ptr [rax+1Ch], 8
0x1400af9b9  jz      short loc_1400AF9EB
0x1400af9bb  cmp     [rax+19h], r14b
0x1400af9bf  jb      short loc_1400AF9EB
0x1400af9c1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400af9c6  mov     edx, r13d
0x1400af9c9  mov     dword ptr [rsp+98h+pBytesReturned], 8000FFFFh
0x1400af9d1  mov     r9d, eax
0x1400af9d4  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400af9db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400af9e2  mov     rcx, [rcx+10h]
0x1400af9e6  call    WPP_SF_Dd
0x1400af9eb  mov     ebx, 8000FFFFh
0x1400af9f0  jmp     loc_1400AF7D2
0x1400af9f5  cmp     [rsp+98h+var_58], 0D8h
0x1400af9fd  jz      short loc_1400AFA23
0x1400af9ff  mov     rax, cs:WPP_GLOBAL_Control
0x1400afa06  cmp     rax, rsi
0x1400afa09  jz      short loc_1400AF9EB
0x1400afa0b  test    byte ptr [rax+1Ch], 8
0x1400afa0f  jz      short loc_1400AF9EB
0x1400afa11  cmp     [rax+19h], r14b
0x1400afa15  jb      short loc_1400AF9EB
0x1400afa17  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400afa1c  mov     edx, 19h
0x1400afa21  jmp     short loc_1400AF9C9
0x1400afa23  mov     r13, [rsp+98h+ppBuffer]
0x1400afa28  cmp     [r13+0], edi
0x1400afa2c  jz      short loc_1400AFA80
0x1400afa2e  mov     dword ptr [r15+0E0h], 0Eh
0x1400afa39  mov     rax, cs:WPP_GLOBAL_Control
0x1400afa40  cmp     rax, rsi
0x1400afa43  jz      short loc_1400AFA87
0x1400afa45  test    byte ptr [rax+1Ch], 1
0x1400afa49  jz      short loc_1400AFA87
0x1400afa4b  cmp     [rax+19h], r14b
0x1400afa4f  jb      short loc_1400AFA87
0x1400afa51  mov     ebx, [r13+0]
0x1400afa55  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400afa5a  mov     [rsp+98h+var_68], edi
0x1400afa5e  mov     dword ptr [rsp+98h+var_70], ebx
0x1400afa62  mov     ecx, [rsp+98h+arg_10]
0x1400afa69  mov     dword ptr [rsp+98h+pBytesReturned], ecx
0x1400afa6d  mov     r9d, eax
0x1400afa70  mov     rcx, cs:WPP_GLOBAL_Control
0x1400afa77  mov     rcx, [rcx+10h]
0x1400afa7b  call    WPP_SF_DLLD
0x1400afa80  mov     rax, cs:WPP_GLOBAL_Control
0x1400afa87  cmp     [r13+0], edi
0x1400afa8b  jz      short loc_1400AFAD4
0x1400afa8d  cmp     rax, rsi
0x1400afa90  jz      short loc_1400AFACA
0x1400afa92  test    byte ptr [rax+1Ch], 8
0x1400afa96  jz      short loc_1400AFACA
0x1400afa98  cmp     [rax+19h], r14b
0x1400afa9c  jb      short loc_1400AFACA
0x1400afa9e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400afaa3  mov     edx, 1Bh
0x1400afaa8  mov     dword ptr [rsp+98h+pBytesReturned], 80070015h
0x1400afab0  mov     r9d, eax
0x1400afab3  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400afaba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400afac1  mov     rcx, [rcx+10h]
0x1400afac5  call    WPP_SF_Dd
0x1400afaca  mov     ebx, 80070015h
0x1400afacf  jmp     loc_1400AF7D2
0x1400afad4  mov     rdx, r13; struct _WTSINFOW *
0x1400afad7  mov     rcx, r15; this
0x1400afada  call    ?SetTitle@CSrApiViewerAxHost@@AEAAJPEAU_WTSINFOW@@@Z; CSrApiViewerAxHost::SetTitle(_WTSINFOW *)
0x1400afadf  mov     ebx, eax
0x1400afae1  test    eax, eax
0x1400afae3  jns     short loc_1400AFB42
0x1400afae5  mov     rax, cs:WPP_GLOBAL_Control
0x1400afaec  cmp     rax, rsi
0x1400afaef  jz      loc_1400AFCE1
0x1400afaf5  test    byte ptr [rax+1Ch], 8
0x1400afaf9  jz      loc_1400AFCE1
0x1400afaff  cmp     [rax+19h], r14b
0x1400afb03  jb      loc_1400AFCE1
0x1400afb09  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400afb0e  mov     edx, 1Ch
0x1400afb13  mov     dword ptr [rsp+98h+var_70], ebx
0x1400afb17  lea     rcx, aSettitleFailed; "SetTitle failed"
0x1400afb1e  mov     [rsp+98h+pBytesReturned], rcx
0x1400afb23  mov     r9d, eax
0x1400afb26  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400afb2d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400afb34  mov     rcx, [rcx+10h]
0x1400afb38  call    WPP_SF_DsD
0x1400afb3d  jmp     loc_1400AF7D2
0x1400afb42  lea     r8, [rsp+98h+Binding]
0x1400afb47  mov     rdx, r12
0x1400afb4a  mov     ecx, [rsp+98h+var_54]
0x1400afb4e  call    ?s_GetSessEnvPublicBinding@CSrApiViewerAxHost@@CAJW4EServerLocality@1@PEBGPEAPEAX@Z; CSrApiViewerAxHost::s_GetSessEnvPublicBinding(CSrApiViewerAxHost::EServerLocality,ushort const *,void * *)
0x1400afb53  mov     ebx, eax
0x1400afb55  test    eax, eax
0x1400afb57  jns     short loc_1400AFB89
0x1400afb59  mov     rax, cs:WPP_GLOBAL_Control
0x1400afb60  cmp     rax, rsi
0x1400afb63  jz      loc_1400AFCE1
0x1400afb69  test    byte ptr [rax+1Ch], 8
0x1400afb6d  jz      loc_1400AFCE1
0x1400afb73  cmp     [rax+19h], r14b
0x1400afb77  jb      loc_1400AFCE1
0x1400afb7d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400afb82  mov     edx, 1Dh
0x1400afb87  jmp     short loc_1400AFB13
0x1400afb89  mov     r13, [rsp+98h+arg_18]
0x1400afb91  mov     [rsp+98h+var_70], r13
0x1400afb96  lea     rax, [rsp+98h+var_4C]
0x1400afb9b  mov     [rsp+98h+pBytesReturned], rax
0x1400afba0  mov     r9d, [r15+8Ch]
0x1400afba7  mov     r8d, [r15+88h]
0x1400afbae  mov     edx, [rsp+98h+arg_10]
0x1400afbb5  mov     rcx, [rsp+98h+Binding]
0x1400afbba  call    RpcShadow2
0x1400afbbf  mov     ebx, eax
0x1400afbc1  mov     [rsp+98h+var_50], eax
0x1400afbc5  mov     r12d, r14d
0x1400afbc8  jmp     loc_1400AFC8C
0x1400afbcd  mov     ebx, eax
0x1400afbcf  test    eax, eax
0x1400afbd1  jle     short loc_1400AFBDC
0x1400afbd3  movzx   ebx, ax
0x1400afbd6  or      ebx, 80070000h
0x1400afbdc  mov     [rsp+98h+var_50], ebx
0x1400afbe0  cmp     ebx, 800706BAh
  ... truncated ...
```
