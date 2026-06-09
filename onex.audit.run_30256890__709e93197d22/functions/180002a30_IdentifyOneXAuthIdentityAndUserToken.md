# IdentifyOneXAuthIdentityAndUserToken

- ea: `0x180002a30`
- end: `0x180002eb5`
- name: `IdentifyOneXAuthIdentityAndUserToken`
- size: `1157`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180002470`

## callees

- `0x180002a30`
- `0x180002ebc`
- `0x180004f40`
- `0x180005440`
- `0x180007f60`
- `0x180010ae0`
- `0x180019cd0`
- `0x18001d108`
- `0x18001d794`
- `0x180020ce0`
- `0x180020de4`
- `0x1800214f0`
- `0x180028ef0`
- `0x180029b74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002caf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002caf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002ca9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002ca9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002e53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002e53`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180002c16`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180002c16`

## pseudocode

```c
__int64 __fastcall IdentifyOneXAuthIdentityAndUserToken(__int64 *a1, int *a2, void **a3, ULONG *a4)
{
  __int64 v7; // rcx
  unsigned int v9; // r13d
  ULONG active; // ebp
  _QWORD *v11; // rcx
  unsigned int v12; // ebx
  bool v13; // zf
  int v14; // edi
  unsigned int UserTokenFromRuntimeState; // eax
  int v16; // ecx
  __int64 v17; // rbp
  int LoggedOnUserForSingleSessionDevice; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  DWORD LastError; // eax
  void *phToken; // [rsp+60h] [rbp+8h] BYREF

  v7 = *a1;
  v9 = *(_DWORD *)(v7 + 20);
  phToken = 0;
  active = OneXReadActiveConsoleSessionId(v7);
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids);
    v11 = WPP_GLOBAL_Control;
  }
  if ( !a2 || !a3 || !a4 )
  {
    v12 = 87;
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 68) & 1) != 0 )
    {
      WPP_SF_d(v11[7], 11, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids, v9);
      v11 = WPP_GLOBAL_Control;
    }
    goto LABEL_64;
  }
  v12 = 0;
  *a4 = -1;
  v13 = dword_18003DE08 == 0;
  v14 = 5;
  *a2 = 5;
  *a3 = 0;
  if ( !v13 )
  {
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 68) & 8) != 0 )
    {
      WPP_SF_d(v11[7], 12, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids, v9);
      v11 = WPP_GLOBAL_Control;
    }
    if ( (byte_18003DF42 & 0x10) != 0 )
    {
      McTemplateU0q_EtwEventWriteTransfer(v11, MachineAuthProposed, v9);
      v11 = WPP_GLOBAL_Control;
    }
    v14 = 1;
    goto LABEL_59;
  }
  if ( !a1[51] )
  {
LABEL_26:
    if ( phToken )
    {
      if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 68) & 8) != 0 )
      {
        WPP_SF_d(v11[7], 17, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids, v9);
        v11 = WPP_GLOBAL_Control;
      }
      if ( (byte_18003DF42 & 0x10) != 0 )
      {
        McTemplateU0qqq_EtwEventWriteTransfer((_DWORD)v11, (unsigned int)UserAuthProposed, v9, 3, active);
        v11 = WPP_GLOBAL_Control;
      }
      v14 = 2;
LABEL_59:
      *a3 = phToken;
      *a2 = v14;
      *a4 = active;
      if ( !v12 )
        goto LABEL_66;
      goto LABEL_64;
    }
    if ( (unsigned __int8)IsWTSQueryUserTokenPresent() )
    {
      LoggedOnUserForSingleSessionDevice = WTSQueryUserToken(active, &phToken);
    }
    else
    {
      if ( !(unsigned __int8)IsQueryUserTokenPresent() )
      {
        SetLastError(0x32u);
        goto LABEL_39;
      }
      LoggedOnUserForSingleSessionDevice = QueryLoggedOnUserForSingleSessionDevice(active, (__int64)&phToken);
    }
    if ( LoggedOnUserForSingleSessionDevice )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0 )
      {
        WPP_SF_dqd(*((_QWORD *)WPP_GLOBAL_Control + 7), v19, v20, v9, phToken, active);
        v11 = WPP_GLOBAL_Control;
      }
      if ( (byte_18003DF42 & 0x10) != 0 )
      {
        McTemplateU0qqq_EtwEventWriteTransfer((_DWORD)v11, (unsigned int)UserAuthProposed, v9, 4, active);
        v11 = WPP_GLOBAL_Control;
      }
      v14 = 2;
      goto LABEL_59;
    }
LABEL_39:
    LastError = GetLastError();
    v12 = LastError;
    if ( dword_18003DE90 )
    {
      if ( LastError )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          WPP_SF_ddd(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            14,
            WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids,
            v9,
            LastError,
            active);
          v11 = WPP_GLOBAL_Control;
        }
      }
      else
      {
        v11 = WPP_GLOBAL_Control;
      }
      goto LABEL_59;
    }
    if ( LastError )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_50;
      WPP_SF_ddd(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        15,
        WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids,
        v9,
        LastError,
        active);
    }
    v11 = WPP_GLOBAL_Control;
LABEL_50:
    if ( Microsoft_Windows_OneXEnableBits < 0 )
    {
      McTemplateU0qqq_EtwEventWriteTransfer((_DWORD)v11, (unsigned int)WTSQueryUserTokenFailed, v12, 92, v9);
      v11 = WPP_GLOBAL_Control;
    }
    v12 = 0;
    v14 = 1;
    goto LABEL_59;
  }
  UserTokenFromRuntimeState = SupplicantGetUserTokenFromRuntimeState(a1, &phToken);
  v12 = UserTokenFromRuntimeState;
  if ( !UserTokenFromRuntimeState )
  {
    v17 = a1[51];
    if ( v17 && (*(_BYTE *)v17 & 8) != 0 )
      active = *(_DWORD *)(v17 + 32);
    else
      active = -1;
    v11 = WPP_GLOBAL_Control;
    goto LABEL_26;
  }
  if ( Microsoft_Windows_OneXEnableBits < 0 )
    McTemplateU0qqq_EtwEventWriteTransfer(
      v16,
      (unsigned int)GetRuntimeUserTokenFailed,
      UserTokenFromRuntimeState,
      50,
      v9);
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 13, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids, v9, v12);
    v11 = WPP_GLOBAL_Control;
  }
LABEL_64:
  if ( phToken )
  {
    CloseHandle(phToken);
    v11 = WPP_GLOBAL_Control;
  }
LABEL_66:
  if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 17) & 0x800) != 0 )
    WPP_SF_D(v11[7], 18, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids, v12);
  return v12;
}

```

## disassembly

```asm
0x180002a30  mov     rax, rsp
0x180002a33  sub     rsp, 58h
0x180002a37  mov     [rax+18h], rbp
0x180002a3b  mov     [rax+20h], rsi
0x180002a3f  mov     rsi, rdx
0x180002a42  mov     [rax-10h], r12
0x180002a46  mov     r12, r8
0x180002a49  mov     [rax-18h], r13
0x180002a4d  mov     [rax-20h], r14
0x180002a51  mov     r14, rcx
0x180002a54  mov     rcx, [rcx]
0x180002a57  mov     [rax-28h], r15
0x180002a5b  mov     r15, r9
0x180002a5e  mov     r13d, [rcx+14h]
0x180002a62  mov     qword ptr [rax+8], 0
0x180002a6a  call    OneXReadActiveConsoleSessionId
0x180002a6f  mov     ebp, eax
0x180002a71  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a78  lea     rax, WPP_GLOBAL_Control
0x180002a7f  cmp     rcx, rax
0x180002a82  jz      short loc_180002AB0
0x180002a84  test    dword ptr [rcx+44h], 800h
0x180002a8b  jz      short loc_180002AB0
0x180002a8d  mov     rcx, [rcx+38h]
0x180002a91  lea     r8, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids
0x180002a98  mov     edx, 0Ah
0x180002a9d  call    WPP_SF_
0x180002aa2  mov     rcx, cs:WPP_GLOBAL_Control
0x180002aa9  lea     rax, WPP_GLOBAL_Control
0x180002ab0  mov     [rsp+58h+arg_8], rbx
0x180002ab5  mov     [rsp+58h+var_8], rdi
0x180002aba  test    rsi, rsi
0x180002abd  jz      loc_180002E10
0x180002ac3  test    r12, r12
0x180002ac6  jz      loc_180002E10
0x180002acc  test    r15, r15
0x180002acf  jz      loc_180002E10
0x180002ad5  xor     ebx, ebx
0x180002ad7  mov     dword ptr [r15], 0FFFFFFFFh
0x180002ade  cmp     cs:dword_18003DE08, ebx
0x180002ae4  mov     edi, 5
0x180002ae9  mov     [rsi], edi
0x180002aeb  mov     [r12], rbx
0x180002aef  jz      short loc_180002B44
0x180002af1  cmp     rcx, rax
0x180002af4  jz      short loc_180002B1B
0x180002af6  test    byte ptr [rcx+44h], 8
0x180002afa  jz      short loc_180002B1B
0x180002afc  mov     rcx, [rcx+38h]
0x180002b00  lea     r8, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids
0x180002b07  mov     edx, 0Ch
0x180002b0c  mov     r9d, r13d
0x180002b0f  call    WPP_SF_d
0x180002b14  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b1b  test    cs:byte_18003DF42, 10h
0x180002b22  jz      short loc_180002B3A
0x180002b24  mov     r8d, r13d
0x180002b27  lea     rdx, MachineAuthProposed
0x180002b2e  call    McTemplateU0q_EtwEventWriteTransfer
0x180002b33  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b3a  mov     edi, 1
0x180002b3f  jmp     loc_180002DF5
0x180002b44  cmp     [r14+198h], rbx
0x180002b4b  jz      loc_180002BFA
0x180002b51  lea     rdx, [rsp+58h+phToken]
0x180002b56  mov     rcx, r14
0x180002b59  call    SupplicantGetUserTokenFromRuntimeState
0x180002b5e  mov     ebx, eax
0x180002b60  test    eax, eax
0x180002b62  jz      short loc_180002BD0
0x180002b64  cmp     cs:Microsoft_Windows_OneXEnableBits, 0
0x180002b6b  jge     short loc_180002B87
0x180002b6d  mov     r9d, 32h ; '2'
0x180002b73  mov     dword ptr [rsp+58h+var_38], r13d
0x180002b78  mov     r8d, eax
0x180002b7b  lea     rdx, GetRuntimeUserTokenFailed
0x180002b82  call    McTemplateU0qqq_EtwEventWriteTransfer
0x180002b87  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b8e  lea     r14, WPP_GLOBAL_Control
0x180002b95  cmp     rcx, r14
0x180002b98  jz      loc_180002E46
0x180002b9e  test    byte ptr [rcx+44h], 1
0x180002ba2  jz      loc_180002E46
0x180002ba8  mov     rcx, [rcx+38h]
0x180002bac  lea     r8, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids
0x180002bb3  mov     edx, 0Dh
0x180002bb8  mov     dword ptr [rsp+58h+var_38], ebx
0x180002bbc  mov     r9d, r13d
0x180002bbf  call    WPP_SF_dd
0x180002bc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180002bcb  jmp     loc_180002E46
0x180002bd0  mov     rbp, [r14+198h]
0x180002bd7  test    rbp, rbp
0x180002bda  jz      short loc_180002BE7
0x180002bdc  test    byte ptr [rbp+0], 8
0x180002be0  jz      short loc_180002BE7
0x180002be2  mov     ebp, [rbp+20h]
0x180002be5  jmp     short loc_180002BEC
0x180002be7  mov     ebp, 0FFFFFFFFh
0x180002bec  mov     rcx, cs:WPP_GLOBAL_Control
0x180002bf3  lea     rax, WPP_GLOBAL_Control
0x180002bfa  cmp     [rsp+58h+phToken], 0
0x180002c00  jnz     loc_180002D9D
0x180002c06  call    IsWTSQueryUserTokenPresent
0x180002c0b  test    al, al
0x180002c0d  jz      short loc_180002C1E
0x180002c0f  lea     rdx, [rsp+58h+phToken]; phToken
0x180002c14  mov     ecx, ebp; SessionId
0x180002c16  call    cs:__imp_WTSQueryUserToken
0x180002c1c  jmp     short loc_180002C33
0x180002c1e  call    IsQueryUserTokenPresent
0x180002c23  test    al, al
0x180002c25  jz      short loc_180002CA4
0x180002c27  lea     rdx, [rsp+58h+phToken]
0x180002c2c  mov     ecx, ebp
0x180002c2e  call    QueryLoggedOnUserForSingleSessionDevice
0x180002c33  test    eax, eax
0x180002c35  jz      short loc_180002CAF
0x180002c37  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c3e  lea     r14, WPP_GLOBAL_Control
0x180002c45  cmp     rcx, r14
0x180002c48  jz      short loc_180002C71
0x180002c4a  test    byte ptr [rcx+44h], 8
0x180002c4e  jz      short loc_180002C71
0x180002c50  mov     rax, [rsp+58h+phToken]
0x180002c55  mov     r9d, r13d
0x180002c58  mov     rcx, [rcx+38h]
0x180002c5c  mov     [rsp+58h+var_30], ebp
0x180002c60  mov     [rsp+58h+var_38], rax
0x180002c65  call    WPP_SF_dqd
0x180002c6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c71  test    cs:byte_18003DF42, 10h
0x180002c78  jz      short loc_180002C9A
0x180002c7a  mov     r9d, 4
0x180002c80  mov     dword ptr [rsp+58h+var_38], ebp
0x180002c84  mov     r8d, r13d
0x180002c87  lea     rdx, UserAuthProposed
0x180002c8e  call    McTemplateU0qqq_EtwEventWriteTransfer
0x180002c93  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c9a  mov     edi, 2
0x180002c9f  jmp     loc_180002DFC
0x180002ca4  mov     ecx, 32h ; '2'; dwErrCode
0x180002ca9  call    cs:__imp_SetLastError
0x180002caf  call    cs:__imp_GetLastError
0x180002cb5  cmp     cs:dword_18003DE90, 0
0x180002cbc  mov     ebx, eax
0x180002cbe  jz      short loc_180002D1D
0x180002cc0  test    eax, eax
0x180002cc2  jz      short loc_180002D11
0x180002cc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ccb  lea     r14, WPP_GLOBAL_Control
0x180002cd2  cmp     rcx, r14
0x180002cd5  jz      loc_180002DFC
0x180002cdb  test    byte ptr [rcx+44h], 1
0x180002cdf  jz      loc_180002DFC
0x180002ce5  mov     rcx, [rcx+38h]
0x180002ce9  lea     r8, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids
0x180002cf0  mov     edx, 0Eh
0x180002cf5  mov     [rsp+58h+var_30], ebp
0x180002cf9  mov     r9d, r13d
0x180002cfc  mov     dword ptr [rsp+58h+var_38], eax
0x180002d00  call    WPP_SF_ddd
0x180002d05  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d0c  jmp     loc_180002DFC
0x180002d11  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d18  jmp     loc_180002DF5
0x180002d1d  test    ebx, ebx
0x180002d1f  jz      short loc_180002D5C
0x180002d21  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d28  lea     r14, WPP_GLOBAL_Control
0x180002d2f  cmp     rcx, r14
0x180002d32  jz      short loc_180002D6A
0x180002d34  test    byte ptr [rcx+44h], 1
0x180002d38  jz      short loc_180002D6A
0x180002d3a  mov     rcx, [rcx+38h]
0x180002d3e  lea     r8, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids
0x180002d45  mov     edx, 0Fh
0x180002d4a  mov     [rsp+58h+var_30], ebp
0x180002d4e  mov     r9d, r13d
0x180002d51  mov     dword ptr [rsp+58h+var_38], ebx
0x180002d55  call    WPP_SF_ddd
0x180002d5a  jmp     short loc_180002D63
0x180002d5c  lea     r14, WPP_GLOBAL_Control
0x180002d63  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d6a  cmp     cs:Microsoft_Windows_OneXEnableBits, 0
0x180002d71  jge     short loc_180002D94
0x180002d73  mov     r9d, 5Ch ; '\'
0x180002d79  mov     dword ptr [rsp+58h+var_38], r13d
0x180002d7e  mov     r8d, ebx
0x180002d81  lea     rdx, WTSQueryUserTokenFailed
0x180002d88  call    McTemplateU0qqq_EtwEventWriteTransfer
0x180002d8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d94  xor     ebx, ebx
0x180002d96  mov     edi, 1
0x180002d9b  jmp     short loc_180002DFC
0x180002d9d  cmp     rcx, rax
0x180002da0  jz      short loc_180002DC7
0x180002da2  test    byte ptr [rcx+44h], 8
0x180002da6  jz      short loc_180002DC7
0x180002da8  mov     rcx, [rcx+38h]
0x180002dac  lea     r8, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids
0x180002db3  mov     edx, 11h
0x180002db8  mov     r9d, r13d
0x180002dbb  call    WPP_SF_d
0x180002dc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180002dc7  test    cs:byte_18003DF42, 10h
0x180002dce  jz      short loc_180002DF0
0x180002dd0  mov     r9d, 3
0x180002dd6  mov     dword ptr [rsp+58h+var_38], ebp
0x180002dda  mov     r8d, r13d
0x180002ddd  lea     rdx, UserAuthProposed
0x180002de4  call    McTemplateU0qqq_EtwEventWriteTransfer
0x180002de9  mov     rcx, cs:WPP_GLOBAL_Control
0x180002df0  mov     edi, 2
0x180002df5  lea     r14, WPP_GLOBAL_Control
0x180002dfc  mov     rax, [rsp+58h+phToken]
0x180002e01  mov     [r12], rax
0x180002e05  mov     [rsi], edi
0x180002e07  mov     [r15], ebp
0x180002e0a  test    ebx, ebx
0x180002e0c  jnz     short loc_180002E46
0x180002e0e  jmp     short loc_180002E60
0x180002e10  mov     ebx, 57h ; 'W'
0x180002e15  cmp     rcx, rax
0x180002e18  jz      short loc_180002E3F
0x180002e1a  test    byte ptr [rcx+44h], 1
0x180002e1e  jz      short loc_180002E3F
0x180002e20  mov     rcx, [rcx+38h]
0x180002e24  lea     r8, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids
0x180002e2b  mov     edx, 0Bh
0x180002e30  mov     r9d, r13d
0x180002e33  call    WPP_SF_d
0x180002e38  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e3f  lea     r14, WPP_GLOBAL_Control
0x180002e46  mov     rax, [rsp+58h+phToken]
0x180002e4b  test    rax, rax
0x180002e4e  jz      short loc_180002E60
0x180002e50  mov     rcx, rax; hObject
0x180002e53  call    cs:__imp_CloseHandle
0x180002e59  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e60  mov     r15, [rsp+58h+var_28]
0x180002e65  cmp     rcx, r14
0x180002e68  mov     r14, [rsp+58h+var_20]
0x180002e6d  mov     r13, [rsp+58h+var_18]
0x180002e72  mov     r12, [rsp+58h+var_10]
0x180002e77  mov     rdi, [rsp+58h+var_8]
0x180002e7c  mov     rsi, [rsp+58h+arg_18]
0x180002e81  mov     rbp, [rsp+58h+arg_10]
0x180002e86  jz      short loc_180002EA9
0x180002e88  test    dword ptr [rcx+44h], 800h
0x180002e8f  jz      short loc_180002EA9
0x180002e91  mov     rcx, [rcx+38h]
0x180002e95  lea     r8, WPP_30abecad6c4537c4a52c6bbfc8e1058a_Traceguids
0x180002e9c  mov     edx, 12h
0x180002ea1  mov     r9d, ebx
0x180002ea4  call    WPP_SF_D
0x180002ea9  mov     eax, ebx
0x180002eab  mov     rbx, [rsp+58h+arg_8]
0x180002eb0  add     rsp, 58h
0x180002eb4  retn
```
