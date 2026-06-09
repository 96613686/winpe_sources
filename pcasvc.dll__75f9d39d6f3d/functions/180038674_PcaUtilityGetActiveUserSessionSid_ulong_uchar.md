# PcaUtilityGetActiveUserSessionSid(ulong *,uchar *)

- ea: `0x180038674`
- end: `0x180038872`
- name: `?PcaUtilityGetActiveUserSessionSid@@YAKPEAKPEAE@Z`
- size: `510`
- prototype: `unsigned int(unsigned int *, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000acf0`
- `0x18003859c`
- `0x1800aef2c`
- `0x1800b1f44`
- `0x1800b2b50`

## callees

- `0x180012920`
- `0x180038674`
- `0x180056256`
- `0x18007a9cf`
- `0x1800f1f10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800386ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003876e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800387c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800386ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003876e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800387c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038843`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038843`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800387bb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800387bb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800387e2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800387e2`
- `WTSAPI32!WTSFreeMemory` at `0x180038833`
- `WTSAPI32!WTSFreeMemory` at `0x180038833`
- `WTSAPI32!WTSQueryUserToken` at `0x180038764`
- `WTSAPI32!WTSQueryUserToken` at `0x180038764`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x1800386f5`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x1800386f5`

## string_xrefs

- `0x180038712`: `PcaUtilityGetActiveUserSessionSid`
- `0x180038789`: `PcaUtilityGetActiveUserSessionSid`
- `0x1800387fa`: `PcaUtilityGetActiveUserSessionSid`
- `0x180038778`: `Failed to get user token information from Session=%d [%d]`
- `0x1800387cb`: `Failed to get token information [%d]`
- `0x1800387ed`: `Insufficent space for User SID storage in buffer`

## pseudocode

```c
__int64 __fastcall PcaUtilityGetActiveUserSessionSid(unsigned int *a1, unsigned __int8 *a2)
{
  DWORD LastError; // eax
  const char *v5; // r9
  int v6; // r8d
  DWORD v7; // ebx
  ULONG SessionId; // edi
  __int64 i; // rcx
  bool v10; // zf
  DWORD LengthSid; // eax
  DWORD pCount; // [rsp+30h] [rbp-D0h] BYREF
  DWORD ReturnLength; // [rsp+34h] [rbp-CCh] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+38h] [rbp-C8h] BYREF
  void *phToken; // [rsp+40h] [rbp-C0h] BYREF
  const void *TokenInformation[128]; // [rsp+50h] [rbp-B0h] BYREF

  ppSessionInfo = 0;
  pCount = 0;
  phToken = 0;
  ReturnLength = 1024;
  memset_0(TokenInformation, 0, sizeof(TokenInformation));
  if ( !WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount) )
  {
    LastError = GetLastError();
    v5 = "Failed to enumerate sessions [%d]";
    v6 = 1301;
LABEL_3:
    v7 = LastError;
    AslLogCallPrintf(1, (unsigned int)"PcaUtilityGetActiveUserSessionSid", v6, (_DWORD)v5);
    goto LABEL_20;
  }
  SessionId = 0;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v10 = (_DWORD)i == pCount;
    if ( (unsigned int)i >= pCount )
      break;
    if ( ppSessionInfo[i].State == WTSActive )
    {
      SessionId = ppSessionInfo[i].SessionId;
      v10 = (_DWORD)i == pCount;
      break;
    }
  }
  if ( v10 )
  {
    v7 = 1168;
  }
  else if ( WTSQueryUserToken(SessionId, &phToken) )
  {
    if ( !GetTokenInformation(phToken, TokenUser, TokenInformation, ReturnLength, &ReturnLength) )
    {
      LastError = GetLastError();
      v5 = "Failed to get token information [%d]";
      v6 = 1336;
      goto LABEL_3;
    }
    LengthSid = GetLengthSid((PSID)TokenInformation[0]);
    if ( LengthSid <= 0x44 )
    {
      memcpy_0(a2, TokenInformation[0], LengthSid);
      if ( a1 )
        *a1 = SessionId;
      v7 = 0;
    }
    else
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"PcaUtilityGetActiveUserSessionSid",
        1347,
        (unsigned int)"Insufficent space for User SID storage in buffer");
      v7 = 111;
    }
  }
  else
  {
    v7 = GetLastError();
    AslLogCallPrintf(
      1,
      (unsigned int)"PcaUtilityGetActiveUserSessionSid",
      1326,
      (unsigned int)"Failed to get user token information from Session=%d [%d]");
  }
LABEL_20:
  if ( ppSessionInfo )
    WTSFreeMemory(ppSessionInfo);
  if ( phToken )
    CloseHandle(phToken);
  return v7;
}

```

## disassembly

```asm
0x180038674  mov     [rsp-8+arg_10], rbx
0x180038679  mov     [rsp-8+arg_18], rsi
0x18003867e  push    rbp
0x18003867f  push    rdi
0x180038680  push    r15
0x180038682  lea     rbp, [rsp-360h]
0x18003868a  sub     rsp, 460h
0x180038691  mov     rax, cs:__security_cookie
0x180038698  xor     rax, rsp
0x18003869b  mov     [rbp+370h+var_20], rax
0x1800386a2  mov     rsi, rdx
0x1800386a5  mov     [rsp+470h+ppSessionInfo], 0
0x1800386ae  mov     rbx, rcx
0x1800386b1  mov     [rsp+470h+var_440], 0
0x1800386b9  mov     r8d, 400h; Size
0x1800386bf  mov     [rsp+470h+phToken], 0
0x1800386c8  xor     edx, edx; Val
0x1800386ca  mov     [rsp+470h+ReturnLength], r8d
0x1800386cf  lea     rcx, [rsp+470h+TokenInformation]; void *
0x1800386d4  call    memset_0
0x1800386d9  lea     rax, [rsp+470h+var_440]
0x1800386de  mov     r15d, 1
0x1800386e4  mov     r8d, r15d; Version
0x1800386e7  mov     [rsp+470h+pCount], rax; pCount
0x1800386ec  lea     r9, [rsp+470h+ppSessionInfo]; ppSessionInfo
0x1800386f1  xor     edx, edx; Reserved
0x1800386f3  xor     ecx, ecx; hServer
0x1800386f5  call    cs:__imp_WTSEnumerateSessionsW
0x1800386fb  test    eax, eax
0x1800386fd  jnz     short loc_18003872C
0x1800386ff  call    cs:__imp_GetLastError
0x180038705  lea     r9, aFailedToEnumer_2; "Failed to enumerate sessions [%d]"
0x18003870c  mov     r8d, 515h
0x180038712  lea     rdx, aPcautilitygeta_0; "PcaUtilityGetActiveUserSessionSid"
0x180038719  mov     dword ptr [rsp+470h+pCount], eax
0x18003871d  mov     ecx, r15d
0x180038720  mov     ebx, eax
0x180038722  call    AslLogCallPrintf
0x180038727  jmp     loc_180038829
0x18003872c  xor     edi, edi
0x18003872e  xor     ecx, ecx
0x180038730  cmp     ecx, [rsp+470h+var_440]
0x180038734  jnb     short loc_180038751
0x180038736  mov     rax, [rsp+470h+ppSessionInfo]
0x18003873b  lea     rdx, [rcx+rcx*2]
0x18003873f  cmp     [rax+rdx*8+10h], edi
0x180038743  jz      short loc_18003874A
0x180038745  add     ecx, r15d
0x180038748  jmp     short loc_180038730
0x18003874a  mov     edi, [rax+rdx*8]
0x18003874d  cmp     ecx, [rsp+470h+var_440]
0x180038751  jnz     short loc_18003875D
0x180038753  mov     ebx, 490h
0x180038758  jmp     loc_180038829
0x18003875d  lea     rdx, [rsp+470h+phToken]; phToken
0x180038762  mov     ecx, edi; SessionId
0x180038764  call    cs:__imp_WTSQueryUserToken
0x18003876a  test    eax, eax
0x18003876c  jnz     short loc_18003879F
0x18003876e  call    cs:__imp_GetLastError
0x180038774  mov     [rsp+470h+var_448], eax
0x180038778  lea     r9, aFailedToGetUse; "Failed to get user token information fr"...
0x18003877f  mov     r8d, 52Eh
0x180038785  mov     dword ptr [rsp+470h+pCount], edi
0x180038789  lea     rdx, aPcautilitygeta_0; "PcaUtilityGetActiveUserSessionSid"
0x180038790  mov     ecx, r15d
0x180038793  mov     ebx, eax
0x180038795  call    AslLogCallPrintf
0x18003879a  jmp     loc_180038829
0x18003879f  mov     r9d, [rsp+470h+ReturnLength]; TokenInformationLength
0x1800387a4  lea     rax, [rsp+470h+ReturnLength]
0x1800387a9  mov     rcx, [rsp+470h+phToken]; TokenHandle
0x1800387ae  lea     r8, [rsp+470h+TokenInformation]; TokenInformation
0x1800387b3  mov     edx, r15d; TokenInformationClass
0x1800387b6  mov     [rsp+470h+pCount], rax; ReturnLength
0x1800387bb  call    cs:__imp_GetTokenInformation
0x1800387c1  test    eax, eax
0x1800387c3  jnz     short loc_1800387DD
0x1800387c5  call    cs:__imp_GetLastError
0x1800387cb  lea     r9, aFailedToGetTok; "Failed to get token information [%d]"
0x1800387d2  mov     r8d, 538h
0x1800387d8  jmp     loc_180038712
0x1800387dd  mov     rcx, [rsp+470h+TokenInformation]; pSid
0x1800387e2  call    cs:__imp_GetLengthSid
0x1800387e8  cmp     eax, 44h ; 'D'
0x1800387eb  jbe     short loc_180038810
0x1800387ed  lea     r9, aInsufficentSpa; "Insufficent space for User SID storage "...
0x1800387f4  mov     r8d, 543h
0x1800387fa  lea     rdx, aPcautilitygeta_0; "PcaUtilityGetActiveUserSessionSid"
0x180038801  mov     ecx, r15d
0x180038804  call    AslLogCallPrintf
0x180038809  mov     ebx, 6Fh ; 'o'
0x18003880e  jmp     short loc_180038829
0x180038810  mov     rdx, [rsp+470h+TokenInformation]; Src
0x180038815  mov     rcx, rsi; void *
0x180038818  mov     r8d, eax; Size
0x18003881b  call    memcpy_0
0x180038820  test    rbx, rbx
0x180038823  jz      short loc_180038827
0x180038825  mov     [rbx], edi
0x180038827  xor     ebx, ebx
0x180038829  mov     rcx, [rsp+470h+ppSessionInfo]; pMemory
0x18003882e  test    rcx, rcx
0x180038831  jz      short loc_180038839
0x180038833  call    cs:__imp_WTSFreeMemory
0x180038839  mov     rcx, [rsp+470h+phToken]; hObject
0x18003883e  test    rcx, rcx
0x180038841  jz      short loc_180038849
0x180038843  call    cs:__imp_CloseHandle
0x180038849  mov     eax, ebx
0x18003884b  mov     rcx, [rbp+370h+var_20]
0x180038852  xor     rcx, rsp; StackCookie
0x180038855  call    __security_check_cookie
0x18003885a  lea     r11, [rsp+470h+var_10]
0x180038862  mov     rbx, [r11+30h]
0x180038866  mov     rsi, [r11+38h]
0x18003886a  mov     rsp, r11
0x18003886d  pop     r15
0x18003886f  pop     rdi
0x180038870  pop     rbp
0x180038871  retn
```
