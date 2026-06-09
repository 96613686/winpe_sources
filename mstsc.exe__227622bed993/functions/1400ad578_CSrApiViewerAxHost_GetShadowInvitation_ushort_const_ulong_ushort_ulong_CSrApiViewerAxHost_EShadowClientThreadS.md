# CSrApiViewerAxHost::GetShadowInvitation(ushort const *,ulong,ushort *,ulong,CSrApiViewerAxHost::EShadowClientThreadState *)

- ea: `0x1400ad578`
- end: `0x1400adc91`
- name: `?GetShadowInvitation@CSrApiViewerAxHost@@AEAAJPEBGKPEAGKPEAW4EShadowClientThreadState@1@@Z`
- size: `1817`
- prototype: `__int64 __usercall@<rax>(CSrApiViewerAxHost *__hidden this@<rcx>, LPWSTR pServerName@<rdx>, DWORD SessionId@<r8d>, unsigned __int16 *@<r9>, unsigned int, enum CSrApiViewerAxHost::EShadowClientThreadState *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400afa98`

## callees

- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x1400ad578`
- `0x1400aff14`
- `0x1400b0804`
- `0x1400b0b60`
- `0x1400b0f6c`
- `0x1400b0fc0`

## import_xrefs

- `WTSAPI32!WTSFreeMemory` at `0x1400adc58`
- `WTSAPI32!WTSFreeMemory` at `0x1400adc58`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x1400ad7e8`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x1400ad7e8`
- `WTSAPI32!WTSOpenServerW` at `0x1400ad742`
- `WTSAPI32!WTSOpenServerW` at `0x1400ad742`
- `KERNEL32!ProcessIdToSessionId` at `0x1400ad5f2`
- `KERNEL32!ProcessIdToSessionId` at `0x1400ad5f2`
- `KERNEL32!GetCurrentProcessId` at `0x1400ad5e2`
- `KERNEL32!GetCurrentProcessId` at `0x1400ad5e2`
- `KERNEL32!GetLastError` at `0x1400ad5fc`
- `KERNEL32!GetLastError` at `0x1400ad76c`
- `KERNEL32!GetLastError` at `0x1400ad7a9`
- `KERNEL32!GetLastError` at `0x1400ad7f2`
- `KERNEL32!GetLastError` at `0x1400ad7f8`
- `KERNEL32!GetLastError` at `0x1400ad5fc`
- `KERNEL32!GetLastError` at `0x1400ad76c`
- `KERNEL32!GetLastError` at `0x1400ad7a9`
- `KERNEL32!GetLastError` at `0x1400ad7f2`
- `KERNEL32!GetLastError` at `0x1400ad7f8`
- `RPCRT4!RpcBindingFree` at `0x1400adc79`
- `RPCRT4!RpcBindingFree` at `0x1400adc79`
- `RPCRT4!I_RpcExceptionFilter` at `0x140111490`
- `RPCRT4!I_RpcExceptionFilter` at `0x140111490`

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
  DWORD pBytesReturned; // [rsp+40h] [rbp-58h] BYREF
  unsigned int v42; // [rsp+44h] [rbp-54h]
  signed int v43; // [rsp+48h] [rbp-50h]
  int v44; // [rsp+4Ch] [rbp-4Ch] BYREF
  LPWSTR ppBuffer; // [rsp+50h] [rbp-48h] BYREF
  RPC_BINDING_HANDLE Binding[8]; // [rsp+58h] [rbp-40h] BYREF
  DWORD pSessionId; // [rsp+A8h] [rbp+10h] BYREF
  DWORD v48; // [rsp+B0h] [rbp+18h]
  unsigned __int16 *v49; // [rsp+B8h] [rbp+20h]

  v49 = a4;
  v48 = SessionId;
  v44 = 0;
  a5 = 2;
  pBytesReturned = 0;
  ppBuffer = 0;
  pSessionId = 0;
  Binding[0] = 0;
  IsLocalServer = 0;
  v42 = 0;
  if ( pServerName && *pServerName )
  {
    IsLocalServer = CSrApiViewerAxHost::s_IsLocalServer(pServerName);
    v42 = IsLocalServer;
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
    WPP_SF_DLLD(*((_QWORD *)WPP_GLOBAL_Control + 2), v30, v31, v29, v48, State, 0);
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
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v34,
        (unsigned int)&WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids,
        v33,
        (__int64)"SetTitle failed",
        LastError);
      goto LABEL_15;
    }
LABEL_83:
    v14 = a5;
    goto LABEL_100;
  }
  LastError = CSrApiViewerAxHost::s_GetSessEnvPublicBinding(v42, pServerName, Binding);
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
  v35 = v49;
  LastError = RpcShadow2(Binding[0], v48, *((_DWORD *)this + 34), *((_DWORD *)this + 35), (__int64)&v44, (__int64)v49);
  v43 = LastError;
  v14 = 2;
  if ( LastError < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v36 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        (unsigned int)&WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids,
        v36,
        (__int64)"RpcShadow2 failed",
        LastError);
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
    v38 = v44;
    if ( !v44 )
      goto LABEL_99;
    if ( (unsigned __int64)v44 < 7 )
      *((_DWORD *)this + 56) = *((_DWORD *)qword_140133598 + v44);
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
0x1400ad578  mov     rax, rsp
0x1400ad57b  mov     [rax+20h], r9
0x1400ad57f  mov     [rax+18h], r8d
0x1400ad583  mov     [rax+8], rcx
0x1400ad587  push    rbx
0x1400ad588  push    rsi
0x1400ad589  push    rdi
0x1400ad58a  push    r12
0x1400ad58c  push    r13
0x1400ad58e  push    r14
0x1400ad590  push    r15
0x1400ad592  sub     rsp, 60h
0x1400ad596  mov     ebx, r8d
0x1400ad599  mov     r12, rdx
0x1400ad59c  mov     r15, rcx
0x1400ad59f  xor     edi, edi
0x1400ad5a1  mov     [rax-4Ch], edi
0x1400ad5a4  lea     r14d, [rdi+2]
0x1400ad5a8  mov     [rsp+98h+arg_20], r14d
0x1400ad5b0  mov     [rax-58h], edi
0x1400ad5b3  mov     [rax-48h], rdi
0x1400ad5b7  mov     [rax+10h], edi
0x1400ad5ba  mov     [rax-40h], rdi
0x1400ad5be  mov     eax, edi
0x1400ad5c0  mov     [rsp+98h+var_54], eax
0x1400ad5c4  test    rdx, rdx
0x1400ad5c7  jz      short loc_1400AD5DA
0x1400ad5c9  cmp     [rdx], di
0x1400ad5cc  jz      short loc_1400AD5DA
0x1400ad5ce  mov     rcx, rdx
0x1400ad5d1  call    ?s_IsLocalServer@CSrApiViewerAxHost@@CA?AW4EServerLocality@1@PEBG@Z; CSrApiViewerAxHost::s_IsLocalServer(ushort const *)
0x1400ad5d6  mov     [rsp+98h+var_54], eax
0x1400ad5da  test    eax, eax
0x1400ad5dc  jnz     loc_1400AD724
0x1400ad5e2  call    cs:__imp_GetCurrentProcessId
0x1400ad5e8  mov     ecx, eax; dwProcessId
0x1400ad5ea  lea     rdx, [rsp+98h+pSessionId]; pSessionId
0x1400ad5f2  call    cs:__imp_ProcessIdToSessionId
0x1400ad5f8  test    eax, eax
0x1400ad5fa  jnz     short loc_1400AD66A
0x1400ad5fc  call    cs:__imp_GetLastError
0x1400ad602  mov     ebx, eax
0x1400ad604  lea     rsi, WPP_GLOBAL_Control
0x1400ad60b  mov     rax, cs:WPP_GLOBAL_Control
0x1400ad612  cmp     rax, rsi
0x1400ad615  jz      short loc_1400AD64B
0x1400ad617  test    byte ptr [rax+1Ch], 8
0x1400ad61b  jz      short loc_1400AD64B
0x1400ad61d  cmp     [rax+19h], r14b
0x1400ad621  jb      short loc_1400AD64B
0x1400ad623  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ad628  mov     edx, 13h
0x1400ad62d  mov     dword ptr [rsp+98h+pBytesReturned], ebx
0x1400ad631  mov     r9d, eax
0x1400ad634  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400ad63b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ad642  mov     rcx, [rcx+10h]
0x1400ad646  call    WPP_SF_Dd
0x1400ad64b  test    ebx, ebx
0x1400ad64d  jle     short loc_1400AD658
0x1400ad64f  movzx   ebx, bx
0x1400ad652  or      ebx, 80070000h
0x1400ad658  mov     eax, 80004005h
0x1400ad65d  test    ebx, ebx
0x1400ad65f  cmovns  ebx, eax
0x1400ad662  mov     r12d, r14d
0x1400ad665  jmp     loc_1400ADC4E
0x1400ad66a  mov     ecx, [rsp+98h+pSessionId]
0x1400ad671  cmp     ebx, ecx
0x1400ad673  jnz     loc_1400AD724
0x1400ad679  mov     dword ptr [r15+0E0h], 0Dh
0x1400ad684  lea     rsi, WPP_GLOBAL_Control
0x1400ad68b  mov     rax, cs:WPP_GLOBAL_Control
0x1400ad692  cmp     rax, rsi
0x1400ad695  jz      short loc_1400AD6D9
0x1400ad697  test    byte ptr [rax+1Ch], 1
0x1400ad69b  jz      short loc_1400AD6D9
0x1400ad69d  cmp     [rax+19h], r14b
0x1400ad6a1  jb      short loc_1400AD6D9
0x1400ad6a3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ad6a8  mov     edx, 14h
0x1400ad6ad  mov     dword ptr [rsp+98h+pBytesReturned], edi
0x1400ad6b1  mov     r9d, eax
0x1400ad6b4  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400ad6bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ad6c2  mov     rcx, [rcx+10h]
0x1400ad6c6  call    WPP_SF_Dd
0x1400ad6cb  mov     ecx, [rsp+98h+pSessionId]
0x1400ad6d2  mov     rax, cs:WPP_GLOBAL_Control
0x1400ad6d9  cmp     ebx, ecx
0x1400ad6db  jnz     short loc_1400AD72B
0x1400ad6dd  cmp     rax, rsi
0x1400ad6e0  jz      short loc_1400AD71A
0x1400ad6e2  test    byte ptr [rax+1Ch], 8
0x1400ad6e6  jz      short loc_1400AD71A
0x1400ad6e8  cmp     [rax+19h], r14b
0x1400ad6ec  jb      short loc_1400AD71A
0x1400ad6ee  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ad6f3  mov     edx, 15h
0x1400ad6f8  mov     dword ptr [rsp+98h+pBytesReturned], 80004005h
0x1400ad700  mov     r9d, eax
0x1400ad703  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400ad70a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ad711  mov     rcx, [rcx+10h]
0x1400ad715  call    WPP_SF_Dd
0x1400ad71a  mov     ebx, 80004005h
0x1400ad71f  jmp     loc_1400AD662
0x1400ad724  lea     rsi, WPP_GLOBAL_Control
0x1400ad72b  test    r12, r12
0x1400ad72e  jz      loc_1400AD7C7
0x1400ad734  cmp     [r12], di
0x1400ad739  jz      loc_1400AD7C7
0x1400ad73f  mov     rcx, r12; pServerName
0x1400ad742  call    cs:__imp_WTSOpenServerW
0x1400ad748  mov     [r15+0D8h], rax
0x1400ad74f  test    rax, rax
0x1400ad752  jnz     short loc_1400AD7C7
0x1400ad754  mov     rax, cs:WPP_GLOBAL_Control
0x1400ad75b  cmp     rax, rsi
0x1400ad75e  jz      short loc_1400AD7A9
0x1400ad760  test    byte ptr [rax+1Ch], 8
0x1400ad764  jz      short loc_1400AD7A9
0x1400ad766  cmp     [rax+19h], r14b
0x1400ad76a  jb      short loc_1400AD7A9
0x1400ad76c  call    cs:__imp_GetLastError
0x1400ad772  mov     ebx, eax
0x1400ad774  test    eax, eax
0x1400ad776  jle     short loc_1400AD781
0x1400ad778  movzx   ebx, ax
0x1400ad77b  or      ebx, 80070000h
0x1400ad781  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ad786  mov     edx, 16h
0x1400ad78b  mov     dword ptr [rsp+98h+pBytesReturned], ebx
0x1400ad78f  mov     r9d, eax
0x1400ad792  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400ad799  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ad7a0  mov     rcx, [rcx+10h]
0x1400ad7a4  call    WPP_SF_Dd
0x1400ad7a9  call    cs:__imp_GetLastError
0x1400ad7af  mov     ebx, eax
0x1400ad7b1  test    eax, eax
0x1400ad7b3  jle     loc_1400AD662
0x1400ad7b9  movzx   ebx, ax
0x1400ad7bc  or      ebx, 80070000h
0x1400ad7c2  jmp     loc_1400AD662
0x1400ad7c7  lea     rax, [rsp+98h+var_58]
0x1400ad7cc  mov     [rsp+98h+pBytesReturned], rax; pBytesReturned
0x1400ad7d1  lea     r9, [rsp+98h+ppBuffer]; ppBuffer
0x1400ad7d6  mov     r13d, 18h
0x1400ad7dc  mov     r8d, r13d; WTSInfoClass
0x1400ad7df  mov     edx, ebx; SessionId
0x1400ad7e1  mov     rcx, [r15+0D8h]; hServer
0x1400ad7e8  call    cs:__imp_WTSQuerySessionInformationW
0x1400ad7ee  test    eax, eax
0x1400ad7f0  jnz     short loc_1400AD832
0x1400ad7f2  call    cs:__imp_GetLastError
0x1400ad7f8  call    cs:__imp_GetLastError
0x1400ad7fe  mov     ebx, eax
0x1400ad800  mov     rax, cs:WPP_GLOBAL_Control
0x1400ad807  cmp     rax, rsi
0x1400ad80a  jz      loc_1400AD64B
0x1400ad810  test    byte ptr [rax+1Ch], 8
0x1400ad814  jz      loc_1400AD64B
0x1400ad81a  cmp     [rax+19h], r14b
0x1400ad81e  jb      loc_1400AD64B
0x1400ad824  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ad829  lea     edx, [r13-1]
0x1400ad82d  jmp     loc_1400AD62D
0x1400ad832  cmp     [rsp+98h+ppBuffer], rdi
0x1400ad837  jnz     short loc_1400AD885
0x1400ad839  mov     rax, cs:WPP_GLOBAL_Control
0x1400ad840  cmp     rax, rsi
0x1400ad843  jz      short loc_1400AD87B
0x1400ad845  test    byte ptr [rax+1Ch], 8
0x1400ad849  jz      short loc_1400AD87B
0x1400ad84b  cmp     [rax+19h], r14b
0x1400ad84f  jb      short loc_1400AD87B
0x1400ad851  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ad856  mov     edx, r13d
0x1400ad859  mov     dword ptr [rsp+98h+pBytesReturned], 8000FFFFh
0x1400ad861  mov     r9d, eax
0x1400ad864  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400ad86b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ad872  mov     rcx, [rcx+10h]
0x1400ad876  call    WPP_SF_Dd
0x1400ad87b  mov     ebx, 8000FFFFh
0x1400ad880  jmp     loc_1400AD662
0x1400ad885  cmp     [rsp+98h+var_58], 0D8h
0x1400ad88d  jz      short loc_1400AD8B3
0x1400ad88f  mov     rax, cs:WPP_GLOBAL_Control
0x1400ad896  cmp     rax, rsi
0x1400ad899  jz      short loc_1400AD87B
0x1400ad89b  test    byte ptr [rax+1Ch], 8
0x1400ad89f  jz      short loc_1400AD87B
0x1400ad8a1  cmp     [rax+19h], r14b
0x1400ad8a5  jb      short loc_1400AD87B
0x1400ad8a7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ad8ac  mov     edx, 19h
0x1400ad8b1  jmp     short loc_1400AD859
0x1400ad8b3  mov     r13, [rsp+98h+ppBuffer]
0x1400ad8b8  cmp     [r13+0], edi
0x1400ad8bc  jz      short loc_1400AD910
0x1400ad8be  mov     dword ptr [r15+0E0h], 0Eh
0x1400ad8c9  mov     rax, cs:WPP_GLOBAL_Control
0x1400ad8d0  cmp     rax, rsi
0x1400ad8d3  jz      short loc_1400AD917
0x1400ad8d5  test    byte ptr [rax+1Ch], 1
0x1400ad8d9  jz      short loc_1400AD917
0x1400ad8db  cmp     [rax+19h], r14b
0x1400ad8df  jb      short loc_1400AD917
0x1400ad8e1  mov     ebx, [r13+0]
0x1400ad8e5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ad8ea  mov     [rsp+98h+var_68], edi
0x1400ad8ee  mov     dword ptr [rsp+98h+var_70], ebx
0x1400ad8f2  mov     ecx, [rsp+98h+arg_10]
0x1400ad8f9  mov     dword ptr [rsp+98h+pBytesReturned], ecx
0x1400ad8fd  mov     r9d, eax
0x1400ad900  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ad907  mov     rcx, [rcx+10h]
0x1400ad90b  call    WPP_SF_DLLD
0x1400ad910  mov     rax, cs:WPP_GLOBAL_Control
0x1400ad917  cmp     [r13+0], edi
0x1400ad91b  jz      short loc_1400AD964
0x1400ad91d  cmp     rax, rsi
0x1400ad920  jz      short loc_1400AD95A
0x1400ad922  test    byte ptr [rax+1Ch], 8
0x1400ad926  jz      short loc_1400AD95A
0x1400ad928  cmp     [rax+19h], r14b
0x1400ad92c  jb      short loc_1400AD95A
0x1400ad92e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ad933  mov     edx, 1Bh
0x1400ad938  mov     dword ptr [rsp+98h+pBytesReturned], 80070015h
0x1400ad940  mov     r9d, eax
0x1400ad943  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400ad94a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ad951  mov     rcx, [rcx+10h]
0x1400ad955  call    WPP_SF_Dd
0x1400ad95a  mov     ebx, 80070015h
0x1400ad95f  jmp     loc_1400AD662
0x1400ad964  mov     rdx, r13; struct _WTSINFOW *
0x1400ad967  mov     rcx, r15; this
0x1400ad96a  call    ?SetTitle@CSrApiViewerAxHost@@AEAAJPEAU_WTSINFOW@@@Z; CSrApiViewerAxHost::SetTitle(_WTSINFOW *)
0x1400ad96f  mov     ebx, eax
0x1400ad971  test    eax, eax
0x1400ad973  jns     short loc_1400AD9D2
0x1400ad975  mov     rax, cs:WPP_GLOBAL_Control
0x1400ad97c  cmp     rax, rsi
0x1400ad97f  jz      loc_1400ADB71
0x1400ad985  test    byte ptr [rax+1Ch], 8
0x1400ad989  jz      loc_1400ADB71
0x1400ad98f  cmp     [rax+19h], r14b
0x1400ad993  jb      loc_1400ADB71
0x1400ad999  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ad99e  mov     edx, 1Ch
0x1400ad9a3  mov     dword ptr [rsp+98h+var_70], ebx
0x1400ad9a7  lea     rcx, aSettitleFailed; "SetTitle failed"
0x1400ad9ae  mov     [rsp+98h+pBytesReturned], rcx
0x1400ad9b3  mov     r9d, eax
0x1400ad9b6  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400ad9bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ad9c4  mov     rcx, [rcx+10h]
0x1400ad9c8  call    WPP_SF_DsD
0x1400ad9cd  jmp     loc_1400AD662
0x1400ad9d2  lea     r8, [rsp+98h+Binding]
0x1400ad9d7  mov     rdx, r12
0x1400ad9da  mov     ecx, [rsp+98h+var_54]
0x1400ad9de  call    ?s_GetSessEnvPublicBinding@CSrApiViewerAxHost@@CAJW4EServerLocality@1@PEBGPEAPEAX@Z; CSrApiViewerAxHost::s_GetSessEnvPublicBinding(CSrApiViewerAxHost::EServerLocality,ushort const *,void * *)
0x1400ad9e3  mov     ebx, eax
0x1400ad9e5  test    eax, eax
0x1400ad9e7  jns     short loc_1400ADA19
0x1400ad9e9  mov     rax, cs:WPP_GLOBAL_Control
0x1400ad9f0  cmp     rax, rsi
0x1400ad9f3  jz      loc_1400ADB71
0x1400ad9f9  test    byte ptr [rax+1Ch], 8
0x1400ad9fd  jz      loc_1400ADB71
0x1400ada03  cmp     [rax+19h], r14b
0x1400ada07  jb      loc_1400ADB71
0x1400ada0d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ada12  mov     edx, 1Dh
0x1400ada17  jmp     short loc_1400AD9A3
0x1400ada19  mov     r13, [rsp+98h+arg_18]
0x1400ada21  mov     [rsp+98h+var_70], r13
0x1400ada26  lea     rax, [rsp+98h+var_4C]
0x1400ada2b  mov     [rsp+98h+pBytesReturned], rax
0x1400ada30  mov     r9d, [r15+8Ch]
0x1400ada37  mov     r8d, [r15+88h]
0x1400ada3e  mov     edx, [rsp+98h+arg_10]
0x1400ada45  mov     rcx, [rsp+98h+Binding]
0x1400ada4a  call    RpcShadow2
0x1400ada4f  mov     ebx, eax
0x1400ada51  mov     [rsp+98h+var_50], eax
0x1400ada55  mov     r12d, r14d
0x1400ada58  jmp     loc_1400ADB1C
0x1400ada5d  mov     ebx, eax
0x1400ada5f  test    eax, eax
0x1400ada61  jle     short loc_1400ADA6C
0x1400ada63  movzx   ebx, ax
0x1400ada66  or      ebx, 80070000h
0x1400ada6c  mov     [rsp+98h+var_50], ebx
0x1400ada70  cmp     ebx, 800706BAh
  ... truncated ...
```
