# GetActiveTokenAndSessionId

- ea: `0x1800c6be8`
- end: `0x1800c7137`
- name: `GetActiveTokenAndSessionId`
- size: `1359`
- prototype: `__int64 __fastcall(void *Buf2)`
- caller_count: `5`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800cea20`
- `0x1800d04b0`
- `0x1800d9a60`
- `0x1800dacd8`
- `0x1800e0e34`

## callees

- `0x180003154`
- `0x1800032e4`
- `0x180005bcc`
- `0x180005bfc`
- `0x18003372c`
- `0x1800ab634`
- `0x1800c6be8`
- `0x1800e2ffc`
- `0x1800e3e60`
- `0x1800e8e72`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x1800c6da0`
- `ntdll!RtlLengthSid` at `0x1800c6dc9`
- `ntdll!RtlLengthSid` at `0x1800c6da0`
- `ntdll!RtlLengthSid` at `0x1800c6dc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c6dfd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c70c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c6dfd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c70c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6e0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6f0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6e0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6f0b`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x1800c6cba`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x1800c6cba`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1800c70da`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1800c70da`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800c6d5e`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800c6d5e`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x1800c700b`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x1800c700b`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800c6ff2`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800c6ff2`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x1800c6fda`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x1800c6fda`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x1800c6fb9`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x1800c6fb9`

## pseudocode

```c
__int64 __fastcall GetActiveTokenAndSessionId(void *Buf2, DWORD *a2, void **a3)
{
  void **v3; // r14
  struct _LIST_ENTRY *v6; // rcx
  void *v7; // rsi
  DWORD v8; // ebx
  int v9; // r15d
  DWORD SessionId; // r12d
  int v11; // r8d
  struct _LIST_ENTRY *v12; // r10
  __int64 v13; // rdi
  int TokenInformation; // eax
  ULONG v15; // eax
  ULONG v16; // eax
  DWORD LastError; // eax
  __int64 v18; // rbx
  int v19; // eax
  LPVOID lpMem; // [rsp+30h] [rbp-20h] BYREF
  void *phToken; // [rsp+38h] [rbp-18h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+40h] [rbp-10h] BYREF
  __int64 *v24; // [rsp+48h] [rbp-8h] BYREF
  DWORD pCount; // [rsp+A8h] [rbp+58h] BYREF

  v3 = a3;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 180, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  v7 = 0;
  phToken = 0;
  ppSessionInfo = 0;
  pCount = 0;
  lpMem = 0;
  if ( !a2 && !v3 )
  {
    v8 = 87;
    if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v6[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(v6[1].Flink, 181, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, 87);
      goto LABEL_76;
    }
    goto LABEL_80;
  }
  v9 = 0;
  SessionId = 0;
  if ( !WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
      {
LABEL_44:
        if ( v8 == 1626 || v8 == 127 )
        {
          if ( v12 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v12[1].Blink) & 4) != 0 )
            WPP_SF_(v12[1].Flink, 188, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
          if ( !(unsigned __int8)IsQueryUserTokenPresent() )
            goto LABEL_70;
          if ( !(unsigned __int8)IsUMgrEnumerateSessionUsersPresent() )
            goto LABEL_60;
          LODWORD(lpMem) = 0;
          v24 = 0;
          v18 = 0;
          if ( (int)UMgrEnumerateSessionUsers(&lpMem, &v24) >= 0 && (_DWORD)lpMem )
            v18 = *v24;
          if ( v24 )
            UMgrFreeSessionUsers(v24);
          if ( v18 )
            v19 = (int)UMgrQueryUserToken(v18, &phToken) >= 0;
          else
LABEL_60:
            v19 = QueryUserToken(0, &phToken);
          if ( !v19 )
          {
LABEL_70:
            v8 = 1008;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 189, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, 1008);
            }
LABEL_73:
            if ( v9 < 0 )
              goto LABEL_74;
            goto LABEL_76;
          }
          v12 = WPP_GLOBAL_Control;
          SessionId = 0;
          v8 = 0;
        }
        else if ( v8 )
        {
          goto LABEL_73;
        }
LABEL_63:
        if ( v12 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v12[1].Blink) & 4) != 0 )
          WPP_SF_qD(v12[1].Flink, 190, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, phToken, SessionId);
        if ( a2 )
          *a2 = SessionId;
        if ( v3 )
        {
          *v3 = phToken;
          phToken = 0;
        }
        goto LABEL_73;
      }
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 187, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, LastError);
    }
    v12 = WPP_GLOBAL_Control;
    goto LABEL_44;
  }
  v8 = 0;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 182, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, pCount);
    v12 = WPP_GLOBAL_Control;
  }
  v13 = 0;
  if ( !pCount )
    goto LABEL_63;
  while ( 1 )
  {
    if ( v12 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v12[1].Blink) & 4) != 0 )
      WPP_SF_ddS(
        v12[1].Flink,
        183,
        v11,
        ppSessionInfo[v13].SessionId,
        ppSessionInfo[v13].State,
        (__int64)ppSessionInfo[v13].pWinStationName);
    if ( WTSQueryUserToken(ppSessionInfo[v13].SessionId, &phToken) )
      break;
    v8 = GetLastError();
    if ( v8 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
      {
        goto LABEL_28;
      }
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 186, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v8);
    }
LABEL_27:
    v12 = WPP_GLOBAL_Control;
LABEL_28:
    v13 = (unsigned int)(v13 + 1);
    if ( (unsigned int)v13 >= pCount )
    {
      v3 = a3;
      goto LABEL_44;
    }
  }
  TokenInformation = VpnGetTokenInformation(phToken);
  v9 = TokenInformation;
  if ( TokenInformation >= 0 )
  {
    v7 = lpMem;
    if ( ppSessionInfo[v13].State == WTSActive && (v15 = RtlLengthSid(&g_WorldSid), !memcmp_0(&g_WorldSid, Buf2, v15))
      || (v16 = RtlLengthSid(Buf2), !memcmp_0(*(const void **)lpMem, Buf2, v16)) )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 185, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
        v12 = WPP_GLOBAL_Control;
      }
      v8 = 0;
      SessionId = ppSessionInfo[v13].SessionId;
      v3 = a3;
      goto LABEL_44;
    }
    MprCommonFree(lpMem);
    v7 = 0;
    lpMem = 0;
    CloseHandle(phToken);
    phToken = 0;
    goto LABEL_27;
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    WPP_SF_d(
      WPP_GLOBAL_Control[1].Flink,
      184,
      &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
      (unsigned int)TokenInformation);
  v7 = lpMem;
LABEL_74:
  v8 = (unsigned __int16)v9;
  if ( (v9 & 0x1FFF0000) != 0x70000 )
    v8 = v9;
LABEL_76:
  if ( phToken )
    CloseHandle(phToken);
  if ( ppSessionInfo )
    WTSFreeMemory(ppSessionInfo);
LABEL_80:
  MprCommonFree(v7);
  if ( (v8 & 0x80000000) != 0
    && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 191, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x1800c6be8  mov     [rsp-38h+arg_0], rbx
0x1800c6bed  mov     [rsp-38h+arg_10], r8
0x1800c6bf2  mov     [rsp-38h+arg_8], rdx
0x1800c6bf7  push    rbp
0x1800c6bf8  push    rsi
0x1800c6bf9  push    rdi
0x1800c6bfa  push    r12
0x1800c6bfc  push    r13
0x1800c6bfe  push    r14
0x1800c6c00  push    r15
0x1800c6c02  mov     rbp, rsp
0x1800c6c05  sub     rsp, 50h
0x1800c6c09  mov     r14, r8
0x1800c6c0c  mov     rbx, rdx
0x1800c6c0f  mov     r13, rcx
0x1800c6c12  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6c19  lea     rdi, WPP_GLOBAL_Control
0x1800c6c20  cmp     rcx, rdi
0x1800c6c23  jz      short loc_1800C6C47
0x1800c6c25  test    byte ptr [rcx+1Ch], 8
0x1800c6c29  jz      short loc_1800C6C47
0x1800c6c2b  mov     rcx, [rcx+10h]
0x1800c6c2f  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800c6c36  mov     edx, 0B4h
0x1800c6c3b  call    WPP_SF_
0x1800c6c40  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6c47  xor     esi, esi
0x1800c6c49  mov     [rbp+phToken], 0
0x1800c6c51  mov     [rbp+ppSessionInfo], 0
0x1800c6c59  mov     [rbp+arg_18], 0
0x1800c6c60  mov     [rbp+lpMem], rsi
0x1800c6c64  test    rbx, rbx
0x1800c6c67  jnz     short loc_1800C6C9F
0x1800c6c69  test    r14, r14
0x1800c6c6c  jnz     short loc_1800C6C9F
0x1800c6c6e  lea     ebx, [rsi+57h]
0x1800c6c71  cmp     rcx, rdi
0x1800c6c74  jz      loc_1800C70E6
0x1800c6c7a  test    byte ptr [rcx+1Ch], 1
0x1800c6c7e  jz      loc_1800C70E6
0x1800c6c84  mov     rcx, [rcx+10h]
0x1800c6c88  lea     edx, [rbx+5Eh]
0x1800c6c8b  mov     r9d, ebx
0x1800c6c8e  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800c6c95  call    WPP_SF_d
0x1800c6c9a  jmp     loc_1800C70BC
0x1800c6c9f  lea     rax, [rbp+arg_18]
0x1800c6ca3  xor     r15d, r15d
0x1800c6ca6  lea     r9, [rbp+ppSessionInfo]; ppSessionInfo
0x1800c6caa  mov     [rsp+50h+pCount], rax; pCount
0x1800c6caf  xor     edx, edx; Reserved
0x1800c6cb1  xor     ecx, ecx; hServer
0x1800c6cb3  xor     r12d, r12d
0x1800c6cb6  lea     r8d, [r15+1]; Version
0x1800c6cba  call    cs:__imp_WTSEnumerateSessionsW
0x1800c6cc1  nop     dword ptr [rax+rax+00h]
0x1800c6cc6  test    eax, eax
0x1800c6cc8  jz      loc_1800C6F0B
0x1800c6cce  xor     ebx, ebx
0x1800c6cd0  mov     r10, cs:WPP_GLOBAL_Control
0x1800c6cd7  cmp     r10, rdi
0x1800c6cda  jz      short loc_1800C6D03
0x1800c6cdc  test    byte ptr [r10+1Ch], 4
0x1800c6ce1  jz      short loc_1800C6D03
0x1800c6ce3  mov     r9d, [rbp+arg_18]
0x1800c6ce7  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800c6cee  mov     rcx, [r10+10h]
0x1800c6cf2  mov     edx, 0B6h
0x1800c6cf7  call    WPP_SF_d
0x1800c6cfc  mov     r10, cs:WPP_GLOBAL_Control
0x1800c6d03  xor     edi, edi
0x1800c6d05  cmp     [rbp+arg_18], ebx
0x1800c6d08  jbe     loc_1800C6EFF
0x1800c6d0e  lea     rax, WPP_GLOBAL_Control
0x1800c6d15  cmp     r10, rax
0x1800c6d18  jz      short loc_1800C6D4E
0x1800c6d1a  test    byte ptr [r10+1Ch], 4
0x1800c6d1f  jz      short loc_1800C6D4E
0x1800c6d21  mov     r9, [rbp+ppSessionInfo]
0x1800c6d25  lea     rcx, [rdi+rdi*2]
0x1800c6d29  mov     edx, 0B7h
0x1800c6d2e  mov     rax, [r9+rcx*8+8]
0x1800c6d33  mov     [rsp+50h+var_28], rax
0x1800c6d38  mov     eax, [r9+rcx*8+10h]
0x1800c6d3d  mov     r9d, [r9+rcx*8]
0x1800c6d41  mov     rcx, [r10+10h]
0x1800c6d45  mov     dword ptr [rsp+50h+pCount], eax
0x1800c6d49  call    WPP_SF_ddS
0x1800c6d4e  mov     rcx, [rbp+ppSessionInfo]
0x1800c6d52  lea     r14, [rdi+rdi*2]
0x1800c6d56  lea     rdx, [rbp+phToken]; phToken
0x1800c6d5a  mov     ecx, [rcx+r14*8]; SessionId
0x1800c6d5e  call    cs:__imp_WTSQueryUserToken
0x1800c6d65  nop     dword ptr [rax+rax+00h]
0x1800c6d6a  test    eax, eax
0x1800c6d6c  jz      loc_1800C6E0F
0x1800c6d72  mov     rcx, [rbp+phToken]; TokenHandle
0x1800c6d76  lea     r8, [rbp+lpMem]
0x1800c6d7a  call    VpnGetTokenInformation
0x1800c6d7f  mov     r15d, eax
0x1800c6d82  test    eax, eax
0x1800c6d84  js      loc_1800C6EC5
0x1800c6d8a  mov     rax, [rbp+ppSessionInfo]
0x1800c6d8e  mov     rsi, [rbp+lpMem]
0x1800c6d92  cmp     [rax+r14*8+10h], r12d
0x1800c6d97  jnz     short loc_1800C6DC6
0x1800c6d99  lea     rcx, ?g_WorldSid@@3U_SID@@A; Sid
0x1800c6da0  call    cs:__imp_RtlLengthSid
0x1800c6da7  nop     dword ptr [rax+rax+00h]
0x1800c6dac  mov     r8d, eax; Size
0x1800c6daf  mov     rdx, r13; Buf2
0x1800c6db2  lea     rcx, ?g_WorldSid@@3U_SID@@A; Buf1
0x1800c6db9  call    memcmp_0
0x1800c6dbe  test    eax, eax
0x1800c6dc0  jz      loc_1800C6E7C
0x1800c6dc6  mov     rcx, r13; Sid
0x1800c6dc9  call    cs:__imp_RtlLengthSid
0x1800c6dd0  nop     dword ptr [rax+rax+00h]
0x1800c6dd5  mov     rcx, [rsi]; Buf1
0x1800c6dd8  mov     rdx, r13; Buf2
0x1800c6ddb  mov     r8d, eax; Size
0x1800c6dde  call    memcmp_0
0x1800c6de3  test    eax, eax
0x1800c6de5  jz      loc_1800C6E7C
0x1800c6deb  mov     rcx, rsi; lpMem
0x1800c6dee  call    MprCommonFree
0x1800c6df3  mov     rcx, [rbp+phToken]; hObject
0x1800c6df7  xor     esi, esi
0x1800c6df9  mov     [rbp+lpMem], rsi
0x1800c6dfd  call    cs:__imp_CloseHandle
0x1800c6e04  nop     dword ptr [rax+rax+00h]
0x1800c6e09  mov     [rbp+phToken], rsi
0x1800c6e0d  jmp     short loc_1800C6E53
0x1800c6e0f  call    cs:__imp_GetLastError
0x1800c6e16  nop     dword ptr [rax+rax+00h]
0x1800c6e1b  mov     ebx, eax
0x1800c6e1d  test    eax, eax
0x1800c6e1f  jz      short loc_1800C6E53
0x1800c6e21  mov     r10, cs:WPP_GLOBAL_Control
0x1800c6e28  lea     rax, WPP_GLOBAL_Control
0x1800c6e2f  cmp     r10, rax
0x1800c6e32  jz      short loc_1800C6E61
0x1800c6e34  test    byte ptr [r10+1Ch], 1
0x1800c6e39  jz      short loc_1800C6E61
0x1800c6e3b  mov     rcx, [r10+10h]
0x1800c6e3f  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800c6e46  mov     edx, 0BAh
0x1800c6e4b  mov     r9d, ebx
0x1800c6e4e  call    WPP_SF_d
0x1800c6e53  mov     r10, cs:WPP_GLOBAL_Control
0x1800c6e5a  lea     rax, WPP_GLOBAL_Control
0x1800c6e61  inc     edi
0x1800c6e63  cmp     edi, [rbp+arg_18]
0x1800c6e66  jb      loc_1800C6D15
0x1800c6e6c  mov     r14, [rbp+arg_10]
0x1800c6e70  lea     rdi, WPP_GLOBAL_Control
0x1800c6e77  jmp     loc_1800C6F4F
0x1800c6e7c  mov     r10, cs:WPP_GLOBAL_Control
0x1800c6e83  lea     rdi, WPP_GLOBAL_Control
0x1800c6e8a  cmp     r10, rdi
0x1800c6e8d  jz      short loc_1800C6EB2
0x1800c6e8f  test    byte ptr [r10+1Ch], 4
0x1800c6e94  jz      short loc_1800C6EB2
0x1800c6e96  mov     rcx, [r10+10h]
0x1800c6e9a  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800c6ea1  mov     edx, 0B9h
0x1800c6ea6  call    WPP_SF_
0x1800c6eab  mov     r10, cs:WPP_GLOBAL_Control
0x1800c6eb2  mov     rax, [rbp+ppSessionInfo]
0x1800c6eb6  xor     ebx, ebx
0x1800c6eb8  mov     r12d, [rax+r14*8]
0x1800c6ebc  mov     r14, [rbp+arg_10]
0x1800c6ec0  jmp     loc_1800C6F4F
0x1800c6ec5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6ecc  lea     rdi, WPP_GLOBAL_Control
0x1800c6ed3  cmp     rcx, rdi
0x1800c6ed6  jz      short loc_1800C6EF6
0x1800c6ed8  test    byte ptr [rcx+1Ch], 1
0x1800c6edc  jz      short loc_1800C6EF6
0x1800c6ede  mov     rcx, [rcx+10h]
0x1800c6ee2  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800c6ee9  mov     edx, 0B8h
0x1800c6eee  mov     r9d, eax
0x1800c6ef1  call    WPP_SF_d
0x1800c6ef6  mov     rsi, [rbp+lpMem]
0x1800c6efa  jmp     loc_1800C70A7
0x1800c6eff  lea     rdi, WPP_GLOBAL_Control
0x1800c6f06  jmp     loc_1800C7027
0x1800c6f0b  call    cs:__imp_GetLastError
0x1800c6f12  nop     dword ptr [rax+rax+00h]
0x1800c6f17  mov     ebx, eax
0x1800c6f19  test    eax, eax
0x1800c6f1b  jz      short loc_1800C6F48
0x1800c6f1d  mov     r10, cs:WPP_GLOBAL_Control
0x1800c6f24  cmp     r10, rdi
0x1800c6f27  jz      short loc_1800C6F4F
0x1800c6f29  test    byte ptr [r10+1Ch], 1
0x1800c6f2e  jz      short loc_1800C6F4F
0x1800c6f30  mov     rcx, [r10+10h]
0x1800c6f34  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800c6f3b  mov     edx, 0BBh
0x1800c6f40  mov     r9d, eax
0x1800c6f43  call    WPP_SF_d
0x1800c6f48  mov     r10, cs:WPP_GLOBAL_Control
0x1800c6f4f  cmp     ebx, 65Ah
0x1800c6f55  jz      short loc_1800C6F69
0x1800c6f57  cmp     ebx, 7Fh
0x1800c6f5a  jz      short loc_1800C6F69
0x1800c6f5c  test    ebx, ebx
0x1800c6f5e  jnz     loc_1800C70A2
0x1800c6f64  jmp     loc_1800C7027
0x1800c6f69  cmp     r10, rdi
0x1800c6f6c  jz      short loc_1800C6F8A
0x1800c6f6e  test    byte ptr [r10+1Ch], 4
0x1800c6f73  jz      short loc_1800C6F8A
0x1800c6f75  mov     rcx, [r10+10h]
0x1800c6f79  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800c6f80  mov     edx, 0BCh
0x1800c6f85  call    WPP_SF_
0x1800c6f8a  call    IsQueryUserTokenPresent
0x1800c6f8f  test    al, al
0x1800c6f91  jz      loc_1800C7073
0x1800c6f97  call    IsUMgrEnumerateSessionUsersPresent
0x1800c6f9c  test    al, al
0x1800c6f9e  jz      short loc_1800C7005
0x1800c6fa0  lea     rdx, [rbp+var_8]
0x1800c6fa4  mov     dword ptr [rbp+lpMem], 0
0x1800c6fab  lea     rcx, [rbp+lpMem]
0x1800c6faf  mov     [rbp+var_8], 0
0x1800c6fb7  xor     ebx, ebx
0x1800c6fb9  call    cs:__imp_UMgrEnumerateSessionUsers
0x1800c6fc0  nop     dword ptr [rax+rax+00h]
0x1800c6fc5  mov     rcx, [rbp+var_8]
0x1800c6fc9  test    eax, eax
0x1800c6fcb  js      short loc_1800C6FD5
0x1800c6fcd  cmp     dword ptr [rbp+lpMem], ebx
0x1800c6fd0  jbe     short loc_1800C6FD5
0x1800c6fd2  mov     rbx, [rcx]
0x1800c6fd5  test    rcx, rcx
0x1800c6fd8  jz      short loc_1800C6FE6
0x1800c6fda  call    cs:__imp_UMgrFreeSessionUsers
0x1800c6fe1  nop     dword ptr [rax+rax+00h]
0x1800c6fe6  lea     rdx, [rbp+phToken]
0x1800c6fea  test    rbx, rbx
0x1800c6fed  jz      short loc_1800C7009
0x1800c6fef  mov     rcx, rbx
0x1800c6ff2  call    cs:__imp_UMgrQueryUserToken
0x1800c6ff9  nop     dword ptr [rax+rax+00h]
0x1800c6ffe  not     eax
0x1800c7000  shr     eax, 1Fh
0x1800c7003  jmp     short loc_1800C7017
0x1800c7005  lea     rdx, [rbp+phToken]
0x1800c7009  xor     ecx, ecx
0x1800c700b  call    cs:__imp_QueryUserToken
0x1800c7012  nop     dword ptr [rax+rax+00h]
0x1800c7017  test    eax, eax
0x1800c7019  jz      short loc_1800C7073
0x1800c701b  mov     r10, cs:WPP_GLOBAL_Control
0x1800c7022  xor     r12d, r12d
0x1800c7025  xor     ebx, ebx
0x1800c7027  cmp     r10, rdi
0x1800c702a  jz      short loc_1800C7051
0x1800c702c  test    byte ptr [r10+1Ch], 4
0x1800c7031  jz      short loc_1800C7051
0x1800c7033  mov     r9, [rbp+phToken]
0x1800c7037  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800c703e  mov     rcx, [r10+10h]
0x1800c7042  mov     edx, 0BEh
0x1800c7047  mov     dword ptr [rsp+50h+pCount], r12d
0x1800c704c  call    WPP_SF_qD
0x1800c7051  mov     rax, [rbp+arg_8]
0x1800c7055  test    rax, rax
0x1800c7058  jz      short loc_1800C705D
0x1800c705a  mov     [rax], r12d
0x1800c705d  test    r14, r14
0x1800c7060  jz      short loc_1800C70A2
0x1800c7062  mov     rax, [rbp+phToken]
0x1800c7066  mov     [r14], rax
0x1800c7069  mov     [rbp+phToken], 0
0x1800c7071  jmp     short loc_1800C70A2
0x1800c7073  mov     ebx, 3F0h
0x1800c7078  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c707f  cmp     rcx, rdi
0x1800c7082  jz      short loc_1800C70A2
0x1800c7084  test    byte ptr [rcx+1Ch], 1
0x1800c7088  jz      short loc_1800C70A2
0x1800c708a  mov     rcx, [rcx+10h]
0x1800c708e  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800c7095  mov     edx, 0BDh
0x1800c709a  mov     r9d, ebx
0x1800c709d  call    WPP_SF_d
0x1800c70a2  test    r15d, r15d
0x1800c70a5  jns     short loc_1800C70BC
0x1800c70a7  mov     eax, r15d
0x1800c70aa  movzx   ebx, r15w
0x1800c70ae  and     eax, 1FFF0000h
0x1800c70b3  cmp     eax, 70000h
0x1800c70b8  cmovnz  ebx, r15d
0x1800c70bc  mov     rcx, [rbp+phToken]; hObject
0x1800c70c0  test    rcx, rcx
  ... truncated ...
```
