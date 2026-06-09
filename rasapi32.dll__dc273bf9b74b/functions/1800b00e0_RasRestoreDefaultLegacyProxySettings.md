# RasRestoreDefaultLegacyProxySettings

- ea: `0x1800b00e0`
- end: `0x1800b0366`
- name: `RasRestoreDefaultLegacyProxySettings`
- size: `646`
- prototype: `__int64 __fastcall(ULONG SessionId)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180010d10`
- `0x18004e580`
- `0x18004e984`
- `0x18006ae64`
- `0x1800b00e0`
- `0x1800ded06`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800b0338`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800b0338`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800b01bf`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800b01bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0142`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b01cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0232`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0142`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b01cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0232`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b0347`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b0347`
- `WINHTTP!WinHttpCloseHandle` at `0x1800b032e`
- `WINHTTP!WinHttpCloseHandle` at `0x1800b032e`
- `WINHTTP!WinHttpOpen` at `0x1800b0224`
- `WINHTTP!WinHttpOpen` at `0x1800b0224`
- `WINHTTP!WinHttpWriteProxySettings` at `0x1800b02e0`
- `WINHTTP!WinHttpWriteProxySettings` at `0x1800b02e0`
- `WINHTTP!WinHttpFreeProxySettings` at `0x1800b0320`
- `WINHTTP!WinHttpFreeProxySettings` at `0x1800b0320`
- `WINHTTP!WinHttpReadProxySettings` at `0x1800b02a9`
- `WINHTTP!WinHttpReadProxySettings` at `0x1800b02a9`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800b011e`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800b011e`

## pseudocode

```c
__int64 __fastcall RasRestoreDefaultLegacyProxySettings(ULONG SessionId)
{
  BOOL v2; // esi
  int v3; // ecx
  DWORD LastError; // eax
  void *v5; // rdi
  DWORD v6; // eax
  DWORD v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  WINHTTP_PROXY_SETTINGS pWinHttpProxySettings; // [rsp+40h] [rbp-39h] BYREF
  BOOL pfDefaultSettingsAreReturned; // [rsp+E8h] [rbp+6Fh] BYREF
  DWORD pdwSettingsVersion; // [rsp+F0h] [rbp+77h] BYREF
  void *phToken; // [rsp+F8h] [rbp+7Fh] BYREF

  phToken = 0;
  v2 = 0;
  memset_0(&pWinHttpProxySettings, 0, sizeof(pWinHttpProxySettings));
  DebugInit();
  if ( !WTSQueryUserToken(SessionId, &phToken) && !(unsigned int)QueryLoggedOnUserForSingleSessionDevice(v3, &phToken) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_9388769838ad322ee42cf89a8fb551ff_Traceguids, LastError);
      }
    }
  }
  if ( !phToken || NtCurrentTeb()->IsImpersonating )
    goto LABEL_20;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_9388769838ad322ee42cf89a8fb551ff_Traceguids);
  }
  v2 = ImpersonateLoggedOnUser(phToken);
  if ( v2 )
  {
LABEL_20:
    v5 = WinHttpOpen(L"rasapi32", 1u, 0, 0, 0);
    if ( v5 )
    {
      pdwSettingsVersion = 0;
      pfDefaultSettingsAreReturned = 0;
      pWinHttpProxySettings.dwStructSize = 112;
      v6 = WinHttpReadProxySettings(
             v5,
             0,
             1,
             1,
             &pdwSettingsVersion,
             &pfDefaultSettingsAreReturned,
             &pWinHttpProxySettings);
      v7 = v6;
      if ( v6 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v9 = 21;
          goto LABEL_36;
        }
      }
      else
      {
        v6 = WinHttpWriteProxySettings(v5, 1, &pWinHttpProxySettings);
        v7 = v6;
        if ( v6 )
        {
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v9 = 22;
            goto LABEL_36;
          }
        }
      }
    }
    else
    {
      v6 = GetLastError();
      v7 = v6;
      if ( v6 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v9 = 20;
          goto LABEL_36;
        }
      }
    }
  }
  else
  {
    v5 = 0;
    v6 = GetLastError();
    v7 = v6;
    if ( v6 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = 19;
LABEL_36:
        WPP_SF_d(v8[2], v9, WPP_9388769838ad322ee42cf89a8fb551ff_Traceguids, v6);
      }
    }
  }
  WinHttpFreeProxySettings(&pWinHttpProxySettings);
  if ( v5 )
    WinHttpCloseHandle(v5);
  if ( v2 )
    RevertToSelf();
  if ( phToken )
    CloseHandle(phToken);
  return v7;
}

```

## disassembly

```asm
0x1800b00e0  mov     [rsp-8+arg_0], rbx
0x1800b00e5  push    rbp
0x1800b00e6  push    rsi
0x1800b00e7  push    rdi
0x1800b00e8  push    r12
0x1800b00ea  push    r15
0x1800b00ec  lea     rbp, [rsp-37h]
0x1800b00f1  sub     rsp, 0B0h
0x1800b00f8  mov     ebx, ecx
0x1800b00fa  mov     [rbp+57h+phToken], 0
0x1800b0102  xor     esi, esi
0x1800b0104  lea     rcx, [rbp+57h+var_90]; void *
0x1800b0108  xor     edx, edx; Val
0x1800b010a  lea     r8d, [rsi+70h]; Size
0x1800b010e  call    memset_0
0x1800b0113  call    DebugInit
0x1800b0118  lea     rdx, [rbp+57h+phToken]; phToken
0x1800b011c  mov     ecx, ebx; SessionId
0x1800b011e  call    cs:__imp_WTSQueryUserToken
0x1800b0124  mov     r12d, 800h
0x1800b012a  lea     r15, WPP_GLOBAL_Control
0x1800b0131  test    eax, eax
0x1800b0133  jnz     short loc_1800B017A
0x1800b0135  lea     rdx, [rbp+57h+phToken]; void **
0x1800b0139  call    ?QueryLoggedOnUserForSingleSessionDevice@@YAHKPEAPEAX@Z; QueryLoggedOnUserForSingleSessionDevice(ulong,void * *)
0x1800b013e  test    eax, eax
0x1800b0140  jnz     short loc_1800B017A
0x1800b0142  call    cs:__imp_GetLastError
0x1800b0148  test    eax, eax
0x1800b014a  jz      short loc_1800B017A
0x1800b014c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0153  cmp     rcx, r15
0x1800b0156  jz      short loc_1800B017A
0x1800b0158  test    [rcx+1Ch], r12d
0x1800b015c  jz      short loc_1800B017A
0x1800b015e  cmp     byte ptr [rcx+19h], 2
0x1800b0162  jb      short loc_1800B017A
0x1800b0164  mov     rcx, [rcx+10h]
0x1800b0168  lea     edx, [rsi+11h]
0x1800b016b  mov     r9d, eax
0x1800b016e  lea     r8, WPP_9388769838ad322ee42cf89a8fb551ff_Traceguids
0x1800b0175  call    WPP_SF_d
0x1800b017a  cmp     [rbp+57h+phToken], rsi
0x1800b017e  jz      loc_1800B0209
0x1800b0184  mov     eax, gs:179Ch
0x1800b018c  test    eax, eax
0x1800b018e  jnz     short loc_1800B0209
0x1800b0190  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0197  cmp     rcx, r15
0x1800b019a  jz      short loc_1800B01BB
0x1800b019c  test    [rcx+1Ch], r12d
0x1800b01a0  jz      short loc_1800B01BB
0x1800b01a2  cmp     byte ptr [rcx+19h], 4
0x1800b01a6  jb      short loc_1800B01BB
0x1800b01a8  mov     rcx, [rcx+10h]
0x1800b01ac  lea     edx, [rax+12h]
0x1800b01af  lea     r8, WPP_9388769838ad322ee42cf89a8fb551ff_Traceguids
0x1800b01b6  call    WPP_SF_
0x1800b01bb  mov     rcx, [rbp+57h+phToken]; hToken
0x1800b01bf  call    cs:__imp_ImpersonateLoggedOnUser
0x1800b01c5  mov     esi, eax
0x1800b01c7  test    eax, eax
0x1800b01c9  jnz     short loc_1800B0209
0x1800b01cb  xor     edi, edi
0x1800b01cd  call    cs:__imp_GetLastError
0x1800b01d3  mov     ebx, eax
0x1800b01d5  test    eax, eax
0x1800b01d7  jz      loc_1800B031C
0x1800b01dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b01e4  cmp     rcx, r15
0x1800b01e7  jz      loc_1800B031C
0x1800b01ed  test    [rcx+1Ch], r12d
0x1800b01f1  jz      loc_1800B031C
0x1800b01f7  cmp     byte ptr [rcx+19h], 2
0x1800b01fb  jb      loc_1800B031C
0x1800b0201  lea     edx, [rsi+13h]
0x1800b0204  jmp     loc_1800B0309
0x1800b0209  xor     r9d, r9d; pszProxyBypassW
0x1800b020c  mov     [rsp+0D0h+dwFlags], 0; dwFlags
0x1800b0214  xor     r8d, r8d; pszProxyW
0x1800b0217  lea     rcx, pszAgentW; "rasapi32"
0x1800b021e  lea     ebx, [r9+1]
0x1800b0222  mov     edx, ebx; dwAccessType
0x1800b0224  call    cs:__imp_WinHttpOpen
0x1800b022a  mov     rdi, rax
0x1800b022d  test    rax, rax
0x1800b0230  jnz     short loc_1800B026E
0x1800b0232  call    cs:__imp_GetLastError
0x1800b0238  mov     ebx, eax
0x1800b023a  test    eax, eax
0x1800b023c  jz      loc_1800B031C
0x1800b0242  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0249  cmp     rcx, r15
0x1800b024c  jz      loc_1800B031C
0x1800b0252  test    [rcx+1Ch], r12d
0x1800b0256  jz      loc_1800B031C
0x1800b025c  cmp     byte ptr [rcx+19h], 2
0x1800b0260  jb      loc_1800B031C
0x1800b0266  lea     edx, [rdi+14h]
0x1800b0269  jmp     loc_1800B0309
0x1800b026e  lea     rax, [rbp+57h+var_90]
0x1800b0272  mov     [rbp+57h+pdwSettingsVersion], 0
0x1800b0279  mov     [rsp+0D0h+pWinHttpProxySettings], rax; pWinHttpProxySettings
0x1800b027e  mov     r9d, ebx; fSetAutoDiscoverForDefaultSettings
0x1800b0281  lea     rax, [rbp+57h+arg_8]
0x1800b0285  mov     [rbp+57h+arg_8], 0
0x1800b028c  mov     [rsp+0D0h+pfDefaultSettingsAreReturned], rax; pfDefaultSettingsAreReturned
0x1800b0291  mov     r8d, ebx; fFallBackToDefaultSettings
0x1800b0294  lea     rax, [rbp+57h+pdwSettingsVersion]
0x1800b0298  mov     [rbp+57h+var_90.dwStructSize], 70h ; 'p'
0x1800b029f  xor     edx, edx; pcwszConnectionName
0x1800b02a1  mov     qword ptr [rsp+0D0h+dwFlags], rax; pdwSettingsVersion
0x1800b02a6  mov     rcx, rdi; hSession
0x1800b02a9  call    cs:__imp_WinHttpReadProxySettings
0x1800b02af  mov     ebx, eax
0x1800b02b1  test    eax, eax
0x1800b02b3  jz      short loc_1800B02D4
0x1800b02b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b02bc  cmp     rcx, r15
0x1800b02bf  jz      short loc_1800B031C
0x1800b02c1  test    [rcx+1Ch], r12d
0x1800b02c5  jz      short loc_1800B031C
0x1800b02c7  cmp     byte ptr [rcx+19h], 2
0x1800b02cb  jb      short loc_1800B031C
0x1800b02cd  mov     edx, 15h
0x1800b02d2  jmp     short loc_1800B0309
0x1800b02d4  lea     r8, [rbp+57h+var_90]; pWinHttpProxySettings
0x1800b02d8  mov     edx, 1; fForceUpdate
0x1800b02dd  mov     rcx, rdi; hSession
0x1800b02e0  call    cs:__imp_WinHttpWriteProxySettings
0x1800b02e6  mov     ebx, eax
0x1800b02e8  test    eax, eax
0x1800b02ea  jz      short loc_1800B031C
0x1800b02ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b02f3  cmp     rcx, r15
0x1800b02f6  jz      short loc_1800B031C
0x1800b02f8  test    [rcx+1Ch], r12d
0x1800b02fc  jz      short loc_1800B031C
0x1800b02fe  cmp     byte ptr [rcx+19h], 2
0x1800b0302  jb      short loc_1800B031C
0x1800b0304  mov     edx, 16h
0x1800b0309  mov     rcx, [rcx+10h]
0x1800b030d  lea     r8, WPP_9388769838ad322ee42cf89a8fb551ff_Traceguids
0x1800b0314  mov     r9d, eax
0x1800b0317  call    WPP_SF_d
0x1800b031c  lea     rcx, [rbp+57h+var_90]; pWinHttpProxySettings
0x1800b0320  call    cs:__imp_WinHttpFreeProxySettings
0x1800b0326  test    rdi, rdi
0x1800b0329  jz      short loc_1800B0334
0x1800b032b  mov     rcx, rdi; hInternet
0x1800b032e  call    cs:__imp_WinHttpCloseHandle
0x1800b0334  test    esi, esi
0x1800b0336  jz      short loc_1800B033E
0x1800b0338  call    cs:__imp_RevertToSelf
0x1800b033e  mov     rcx, [rbp+57h+phToken]; hObject
0x1800b0342  test    rcx, rcx
0x1800b0345  jz      short loc_1800B034D
0x1800b0347  call    cs:__imp_CloseHandle
0x1800b034d  mov     eax, ebx
0x1800b034f  mov     rbx, [rsp+0D0h+arg_0]
0x1800b0357  add     rsp, 0B0h
0x1800b035e  pop     r15
0x1800b0360  pop     r12
0x1800b0362  pop     rdi
0x1800b0363  pop     rsi
0x1800b0364  pop     rbp
0x1800b0365  retn
```
