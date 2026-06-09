# FwQueryRpcClientInfo

- ea: `0x180003b30`
- end: `0x18000401e`
- name: `FwQueryRpcClientInfo`
- size: `1262`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800039f0`

## callees

- `0x180003b30`
- `0x180004030`
- `0x180004100`
- `0x1800043a0`
- `0x180004750`
- `0x1800047e0`
- `0x180004840`
- `0x180004870`
- `0x1800048c0`
- `0x180014268`
- `0x180017b58`
- `0x180017d1c`
- `0x18001e1d0`
- `0x18002f38c`
- `0x18002f43c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ca8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003fd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ffb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ca8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003fd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ffb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003c9a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003ce6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003c9a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003ce6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003c51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003c51`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180003c6a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180003c6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003da0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003db4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003da0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003db4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003dd3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003dec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e05`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003dd3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003dec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e05`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003dc5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003dde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003df7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003dc5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003dde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003df7`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180003bac`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180003bac`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180003b8a`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180003b8a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180003cfe`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180003cfe`

## string_xrefs

- `0x180003ef9`: `FwGetTokenInformation`
- `0x180003fda`: `FwGetTokenInformation`
- `0x180003f54`: `mpssvc.dll`
- `0x180003fb3`: `GetTokenInformation`
- `0x180003fca`: `GetTokenInformation`
- `0x180003e61`: `OpenProcess`
- `0x180003f98`: `OpenThreadToken`
- `0x180004001`: `ConvertSidToStringSidW`

## pseudocode

```c
__int64 __fastcall FwQueryRpcClientInfo(void *a1, __int64 a2)
{
  wchar_t *v3; // rbp
  void *v4; // r14
  PSID *v5; // rsi
  int v6; // edx
  int v7; // ebx
  int v8; // r8d
  char *v9; // rax
  char *v10; // r15
  int ProcessImageInfo; // eax
  int v12; // eax
  int LongPathName; // eax
  HANDLE CurrentThread; // rax
  void *v15; // rbx
  DWORD v16; // eax
  __int64 v17; // rdx
  int v18; // edx
  int v19; // r8d
  HANDLE ProcessHeap; // rax
  HANDLE v22; // rax
  HANDLE v23; // rax
  _QWORD *v24; // rcx
  const char *v25; // rax
  DWORD LastError; // eax
  const char *v27; // rdx
  const char *v28; // rbx
  wchar_t *String2; // [rsp+30h] [rbp-68h] BYREF
  void *Src; // [rsp+38h] [rbp-60h]
  DWORD TokenInformationLength; // [rsp+40h] [rbp-58h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-50h] BYREF

  TokenInformationLength = 1;
  String2 = 0;
  Src = 0;
  v3 = 0;
  TokenHandle = 0;
  v4 = 0;
  if ( a2 )
  {
    v5 = 0;
    v7 = I_RpcBindingInqLocalClientPID(a1, (unsigned int *)(a2 + 4));
    if ( v7 )
    {
      v10 = 0;
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v25 = "I_RpcBindingInqLocalClientPID";
        goto LABEL_46;
      }
    }
    else
    {
      v9 = (char *)OpenProcess(0x1000u, 0, *(_DWORD *)(a2 + 4));
      v10 = v9;
      if ( v9 )
      {
        v7 = 0;
        if ( (*(_BYTE *)a2 & 4) != 0 )
        {
          ProcessImageInfo = FwGetProcessImageInfo(v9, ProcessImageFileName, &String2);
          v7 = ProcessImageInfo;
          if ( ProcessImageInfo < 0 )
          {
            FwReportReturnError("FwQueryRpcClientInfo", (unsigned int)ProcessImageInfo);
            v3 = String2;
            goto LABEL_20;
          }
          v3 = String2;
          v12 = FwSubstituteDeviceName(String2);
          v7 = v12;
          if ( v12 < 0 )
          {
            FwReportReturnError("FwQueryRpcClientInfo", (unsigned int)v12);
            v4 = Src;
            goto LABEL_20;
          }
          v4 = Src;
          LongPathName = FwGetLongPathName(Src);
          v7 = LongPathName;
          if ( LongPathName < 0 )
            goto LABEL_53;
          if ( !TokenInformationLength )
          {
            v7 = -2147467259;
            FwReportReturnError("FwQueryRpcClientInfo", 2147500037LL);
            goto LABEL_20;
          }
        }
        if ( (*(_BYTE *)a2 & 8) != 0 )
        {
          LongPathName = FwGetProcessImageInfo(
                           v10,
                           ProcessImageFileMapping|ProcessUserModeIOPL,
                           (unsigned __int16 **)(a2 + 24));
          v7 = LongPathName;
          if ( LongPathName < 0 )
            goto LABEL_53;
        }
        if ( (*(_BYTE *)a2 & 2) == 0 )
        {
LABEL_20:
          if ( v4 )
          {
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, v4);
          }
          if ( v3 )
          {
            v22 = GetProcessHeap();
            HeapFree(v22, 0, v3);
          }
          if ( v5 )
          {
            v23 = GetProcessHeap();
            HeapFree(v23, 0, v5);
          }
          if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL && !CloseHandle(TokenHandle) )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && !CloseHandle(v10) )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          if ( v7 < 0 )
          {
            FwFreeRpcCallersProcessInfo(a2);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, v19, (unsigned int)"FwQueryRpcClientInfo", v7);
          }
          return (unsigned int)v7;
        }
        CurrentThread = GetCurrentThread();
        if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
        {
          LastError = GetLastError();
          v27 = "OpenThreadToken";
          goto LABEL_67;
        }
        v15 = TokenHandle;
        TokenInformationLength = 0;
        if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        v16 = GetLastError();
        if ( v16 == 122 || !v16 )
        {
          v5 = (PSID *)FwAlloc(TokenInformationLength, v17);
          if ( v5 )
          {
            if ( GetTokenInformation(v15, TokenUser, v5, TokenInformationLength, &TokenInformationLength) )
            {
              v7 = 0;
              goto LABEL_19;
            }
            v28 = "GetTokenInformation";
            v16 = GetLastError();
          }
          else
          {
            v28 = "FwAlloc";
            v16 = 8;
          }
        }
        else
        {
          v28 = "GetTokenInformation";
        }
        v7 = FwReportErrorAsWinError("FwGetTokenInformation", v28, v16);
        if ( v7 >= 0 )
        {
          v5 = 0;
          goto LABEL_19;
        }
        FwFree(v5);
        LongPathName = FwReportReturnError("FwGetTokenInformation", (unsigned int)v7);
        v7 = LongPathName;
        v5 = 0;
        if ( LongPathName < 0 )
        {
LABEL_53:
          FwReportReturnError("FwQueryRpcClientInfo", (unsigned int)LongPathName);
          goto LABEL_20;
        }
LABEL_19:
        if ( ConvertSidToStringSidW(*v5, (LPWSTR *)(a2 + 8)) )
          goto LABEL_20;
        LastError = GetLastError();
        v27 = "ConvertSidToStringSidW";
LABEL_67:
        v7 = FwReportErrorAsWinError("FwQueryRpcClientInfo", v27, LastError);
        goto LABEL_20;
      }
      v7 = GetLastError();
      if ( !v7 )
        MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", 0, 0);
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v25 = "OpenProcess";
LABEL_46:
        WPP_SF_ssL(v24[2], v6, v8, (unsigned int)"FwQueryRpcClientInfo", (__int64)v25, v7);
      }
    }
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    goto LABEL_20;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_7f5bde6595ff3eb51821de83b63f4275_Traceguids);
  return FwReportReturnError("FwQueryRpcClientInfo", 2147942487LL);
}

```

## disassembly

```asm
0x180003b30  mov     r11, rsp
0x180003b33  push    rbp
0x180003b34  push    rdi
0x180003b35  push    r12
0x180003b37  push    r13
0x180003b39  push    r14
0x180003b3b  sub     rsp, 70h
0x180003b3f  mov     rax, cs:__security_cookie
0x180003b46  xor     rax, rsp
0x180003b49  mov     [rsp+98h+var_48], rax
0x180003b4e  xor     r13d, r13d
0x180003b51  mov     [rsp+98h+TokenInformationLength], 1
0x180003b59  mov     [r11-68h], r13
0x180003b5d  mov     rdi, rdx
0x180003b60  mov     [r11-60h], r13
0x180003b64  mov     ebp, r13d
0x180003b67  mov     [r11-50h], r13
0x180003b6b  mov     r14d, r13d
0x180003b6e  test    rdx, rdx
0x180003b71  jz      loc_180003E9B
0x180003b77  mov     [r11+18h], rbx
0x180003b7b  add     rdx, 4; Pid
0x180003b7f  mov     [r11-30h], rsi
0x180003b83  mov     esi, r13d
0x180003b86  mov     [r11-38h], r15
0x180003b8a  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180003b90  lea     r12, WPP_GLOBAL_Control
0x180003b97  mov     ebx, eax
0x180003b99  test    eax, eax
0x180003b9b  jnz     loc_180003E10
0x180003ba1  mov     r8d, [rdi+4]; dwProcessId
0x180003ba5  xor     edx, edx; bInheritHandle
0x180003ba7  mov     ecx, 1000h; dwDesiredAccess
0x180003bac  call    cs:__imp_OpenProcess
0x180003bb2  mov     r15, rax
0x180003bb5  test    rax, rax
0x180003bb8  jz      loc_180003E3F
0x180003bbe  test    byte ptr [rdi], 4
0x180003bc1  mov     ebx, r13d
0x180003bc4  jz      short loc_180003C28
0x180003bc6  lea     r8, [rsp+98h+String2]; unsigned __int16 **
0x180003bcb  mov     edx, 1Bh; ProcessInformationClass
0x180003bd0  mov     rcx, rax; ProcessHandle
0x180003bd3  call    ?FwGetProcessImageInfo@@YAJPEAXW4_PROCESSINFOCLASS@@PEAPEAG@Z; FwGetProcessImageInfo(void *,_PROCESSINFOCLASS,ushort * *)
0x180003bd8  mov     ebx, eax
0x180003bda  test    eax, eax
0x180003bdc  js      loc_180003EC4
0x180003be2  mov     rbp, [rsp+98h+String2]
0x180003be7  lea     rdx, [rsp+98h+Src]
0x180003bec  mov     rcx, rbp; String2
0x180003bef  call    FwSubstituteDeviceName
0x180003bf4  mov     ebx, eax
0x180003bf6  test    eax, eax
0x180003bf8  js      loc_180003E83
0x180003bfe  mov     r14, [rsp+98h+Src]
0x180003c03  lea     rdx, [rdi+10h]
0x180003c07  mov     rcx, r14; Src
0x180003c0a  lea     r8, [rsp+98h+TokenInformationLength]
0x180003c0f  call    FwGetLongPathName
0x180003c14  mov     ebx, eax
0x180003c16  test    eax, eax
0x180003c18  js      loc_180003EDC
0x180003c1e  cmp     [rsp+98h+TokenInformationLength], esi
0x180003c22  jz      loc_180003F67
0x180003c28  test    byte ptr [rdi], 8
0x180003c2b  jz      short loc_180003C48
0x180003c2d  lea     r8, [rdi+18h]; unsigned __int16 **
0x180003c31  mov     edx, 3Ch ; '<'; ProcessInformationClass
0x180003c36  mov     rcx, r15; ProcessHandle
0x180003c39  call    ?FwGetProcessImageInfo@@YAJPEAXW4_PROCESSINFOCLASS@@PEAPEAG@Z; FwGetProcessImageInfo(void *,_PROCESSINFOCLASS,ushort * *)
0x180003c3e  mov     ebx, eax
0x180003c40  test    eax, eax
0x180003c42  js      loc_180003F7F
0x180003c48  test    byte ptr [rdi], 2
0x180003c4b  jz      loc_180003D0C
0x180003c51  call    cs:__imp_GetCurrentThread
0x180003c57  lea     r9, [rsp+98h+TokenHandle]; TokenHandle
0x180003c5c  mov     edx, 8; DesiredAccess
0x180003c61  mov     rcx, rax; ThreadHandle
0x180003c64  mov     r8d, 1; OpenAsSelf
0x180003c6a  call    cs:__imp_OpenThreadToken
0x180003c70  test    eax, eax
0x180003c72  jz      loc_180003F92
0x180003c78  mov     rbx, [rsp+98h+TokenHandle]
0x180003c7d  lea     rax, [rsp+98h+TokenInformationLength]
0x180003c82  mov     rcx, rbx; TokenHandle
0x180003c85  mov     [rsp+98h+TokenInformationLength], r13d
0x180003c8a  xor     r9d, r9d; TokenInformationLength
0x180003c8d  mov     [rsp+98h+ReturnLength], rax; ReturnLength
0x180003c92  xor     r8d, r8d; TokenInformation
0x180003c95  mov     edx, 1; TokenInformationClass
0x180003c9a  call    cs:__imp_GetTokenInformation
0x180003ca0  test    eax, eax
0x180003ca2  jnz     loc_180003FA1
0x180003ca8  call    cs:__imp_GetLastError
0x180003cae  cmp     eax, 7Ah ; 'z'
0x180003cb1  jnz     loc_180003FAB
0x180003cb7  mov     ecx, [rsp+98h+TokenInformationLength]
0x180003cbb  call    FwAlloc
0x180003cc0  mov     rsi, rax
0x180003cc3  test    rax, rax
0x180003cc6  jz      loc_180003FBC
0x180003ccc  mov     r9d, [rsp+98h+TokenInformationLength]; TokenInformationLength
0x180003cd1  lea     rax, [rsp+98h+TokenInformationLength]
0x180003cd6  mov     r8, rsi; TokenInformation
0x180003cd9  mov     [rsp+98h+ReturnLength], rax; ReturnLength
0x180003cde  mov     edx, 1; TokenInformationClass
0x180003ce3  mov     rcx, rbx; TokenHandle
0x180003ce6  call    cs:__imp_GetTokenInformation
0x180003cec  test    eax, eax
0x180003cee  jz      loc_180003FCA
0x180003cf4  mov     ebx, r13d
0x180003cf7  mov     rcx, [rsi]; Sid
0x180003cfa  lea     rdx, [rdi+8]; StringSid
0x180003cfe  call    cs:__imp_ConvertSidToStringSidW
0x180003d04  test    eax, eax
0x180003d06  jz      loc_180003FFB
0x180003d0c  test    r14, r14
0x180003d0f  jnz     loc_180003DC5
0x180003d15  test    rbp, rbp
0x180003d18  jnz     loc_180003DDE
0x180003d1e  test    rsi, rsi
0x180003d21  jnz     loc_180003DF7
0x180003d27  mov     rcx, [rsp+98h+TokenHandle]; hObject
0x180003d2c  mov     rsi, [rsp+98h+var_30]
0x180003d31  lea     rax, [rcx-1]
0x180003d35  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003d39  jbe     short loc_180003DA0
0x180003d3b  lea     rax, [r15-1]
0x180003d3f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003d43  jbe     short loc_180003DB1
0x180003d45  mov     r15, [rsp+98h+var_38]
0x180003d4a  test    ebx, ebx
0x180003d4c  jns     short loc_180003D7C
0x180003d4e  mov     rcx, rdi
0x180003d51  call    FwFreeRpcCallersProcessInfo
0x180003d56  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d5d  cmp     rcx, r12
0x180003d60  jz      short loc_180003D7C
0x180003d62  test    byte ptr [rcx+1Ch], 1
0x180003d66  jz      short loc_180003D7C
0x180003d68  mov     rcx, [rcx+10h]
0x180003d6c  lea     r9, aFwqueryrpcclie; "FwQueryRpcClientInfo"
0x180003d73  mov     dword ptr [rsp+98h+ReturnLength], ebx
0x180003d77  call    WPP_SF_sD
0x180003d7c  mov     eax, ebx
0x180003d7e  mov     rbx, [rsp+98h+arg_10]
0x180003d86  mov     rcx, [rsp+98h+var_48]
0x180003d8b  xor     rcx, rsp; StackCookie
0x180003d8e  call    __security_check_cookie
0x180003d93  add     rsp, 70h
0x180003d97  pop     r14
0x180003d99  pop     r13
0x180003d9b  pop     r12
0x180003d9d  pop     rdi
0x180003d9e  pop     rbp
0x180003d9f  retn
0x180003da0  call    cs:__imp_CloseHandle
0x180003da6  test    eax, eax
0x180003da8  jnz     short loc_180003D3B
0x180003daa  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "success")
0x180003daf  jmp     short loc_180003D3B
0x180003db1  mov     rcx, r15; hObject
0x180003db4  call    cs:__imp_CloseHandle
0x180003dba  test    eax, eax
0x180003dbc  jnz     short loc_180003D45
0x180003dbe  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "success")
0x180003dc3  jmp     short loc_180003D45
0x180003dc5  call    cs:__imp_GetProcessHeap
0x180003dcb  mov     r8, r14; lpMem
0x180003dce  xor     edx, edx; dwFlags
0x180003dd0  mov     rcx, rax; hHeap
0x180003dd3  call    cs:__imp_HeapFree
0x180003dd9  jmp     loc_180003D15
0x180003dde  call    cs:__imp_GetProcessHeap
0x180003de4  mov     r8, rbp; lpMem
0x180003de7  xor     edx, edx; dwFlags
0x180003de9  mov     rcx, rax; hHeap
0x180003dec  call    cs:__imp_HeapFree
0x180003df2  jmp     loc_180003D1E
0x180003df7  call    cs:__imp_GetProcessHeap
0x180003dfd  mov     r8, rsi; lpMem
0x180003e00  xor     edx, edx; dwFlags
0x180003e02  mov     rcx, rax; hHeap
0x180003e05  call    cs:__imp_HeapFree
0x180003e0b  jmp     loc_180003D27
0x180003e10  mov     r15, r13
0x180003e13  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e1a  cmp     rcx, r12
0x180003e1d  jz      short loc_180003E29
0x180003e1f  test    byte ptr [rcx+1Ch], 1
0x180003e23  jnz     loc_180003F45
0x180003e29  test    ebx, ebx
0x180003e2b  jle     loc_180003D0C
0x180003e31  movzx   ebx, bx
0x180003e34  or      ebx, 80070000h
0x180003e3a  jmp     loc_180003D0C
0x180003e3f  call    cs:__imp_GetLastError
0x180003e45  mov     ebx, eax
0x180003e47  test    eax, eax
0x180003e49  jz      loc_180003F51
0x180003e4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e56  cmp     rcx, r12
0x180003e59  jz      short loc_180003E29
0x180003e5b  test    byte ptr [rcx+1Ch], 1
0x180003e5f  jz      short loc_180003E29
0x180003e61  lea     rax, aOpenprocess; "OpenProcess"
0x180003e68  mov     rcx, [rcx+10h]
0x180003e6c  lea     r9, aFwqueryrpcclie; "FwQueryRpcClientInfo"
0x180003e73  mov     [rsp+98h+var_70], ebx
0x180003e77  mov     [rsp+98h+ReturnLength], rax
0x180003e7c  call    WPP_SF_ssL
0x180003e81  jmp     short loc_180003E29
0x180003e83  mov     edx, eax
0x180003e85  lea     rcx, aFwqueryrpcclie; "FwQueryRpcClientInfo"
0x180003e8c  call    FwReportReturnError
0x180003e91  mov     r14, [rsp+98h+Src]
0x180003e96  jmp     loc_180003D0C
0x180003e9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ea2  lea     r12, WPP_GLOBAL_Control
0x180003ea9  cmp     rcx, r12
0x180003eac  jnz     short loc_180003F25
0x180003eae  mov     edx, 80070057h
0x180003eb3  lea     rcx, aFwqueryrpcclie; "FwQueryRpcClientInfo"
0x180003eba  call    FwReportReturnError
0x180003ebf  jmp     loc_180003D86
0x180003ec4  mov     edx, eax
0x180003ec6  lea     rcx, aFwqueryrpcclie; "FwQueryRpcClientInfo"
0x180003ecd  call    FwReportReturnError
0x180003ed2  mov     rbp, [rsp+98h+String2]
0x180003ed7  jmp     loc_180003D0C
0x180003edc  mov     edx, eax
0x180003ede  lea     rcx, aFwqueryrpcclie; "FwQueryRpcClientInfo"
0x180003ee5  call    FwReportReturnError
0x180003eea  jmp     loc_180003D0C
0x180003eef  mov     rcx, rsi
0x180003ef2  call    FwFree
0x180003ef7  mov     edx, ebx
0x180003ef9  lea     rcx, aFwgettokeninfo_0; "FwGetTokenInformation"
0x180003f00  call    FwReportReturnError
0x180003f05  mov     ebx, eax
0x180003f07  mov     rsi, r13
0x180003f0a  test    eax, eax
0x180003f0c  jns     loc_180003CF7
0x180003f12  mov     edx, eax
0x180003f14  lea     rcx, aFwqueryrpcclie; "FwQueryRpcClientInfo"
0x180003f1b  call    FwReportReturnError
0x180003f20  jmp     loc_180003D0C
0x180003f25  test    byte ptr [rcx+1Ch], 1
0x180003f29  jz      short loc_180003EAE
0x180003f2b  mov     rcx, [rcx+10h]
0x180003f2f  lea     r8, WPP_7f5bde6595ff3eb51821de83b63f4275_Traceguids
0x180003f36  mov     edx, 0Ah
0x180003f3b  call    WPP_SF_
0x180003f40  jmp     loc_180003EAE
0x180003f45  lea     rax, aIRpcbindinginq_0; "I_RpcBindingInqLocalClientPID"
0x180003f4c  jmp     loc_180003E68
0x180003f51  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "error != NO_ERROR", "Function failure")
0x180003f54  lea     rcx, aMpssvcDll_0; "mpssvc.dll"
0x180003f5b  xor     edx, edx
0x180003f5d  call    MicrosoftTelemetryAssertTriggeredArgs
0x180003f62  jmp     loc_180003E4F
0x180003f67  mov     ebx, 80004005h
0x180003f6c  lea     rcx, aFwqueryrpcclie; "FwQueryRpcClientInfo"
0x180003f73  mov     edx, ebx
0x180003f75  call    FwReportReturnError
0x180003f7a  jmp     loc_180003D0C
0x180003f7f  mov     edx, eax
0x180003f81  lea     rcx, aFwqueryrpcclie; "FwQueryRpcClientInfo"
0x180003f88  call    FwReportReturnError
0x180003f8d  jmp     loc_180003D0C
0x180003f92  call    cs:__imp_GetLastError
0x180003f98  lea     rdx, aOpenthreadtoke; "OpenThreadToken"
0x180003f9f  jmp     short loc_180004008
0x180003fa1  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "!success")
0x180003fa6  jmp     loc_180003CA8
0x180003fab  test    eax, eax
0x180003fad  jz      loc_180003CB7
0x180003fb3  lea     rbx, aGettokeninform; "GetTokenInformation"
0x180003fba  jmp     short loc_180003FD7
0x180003fbc  lea     rbx, aFwalloc_0; "FwAlloc"
0x180003fc3  mov     eax, 8
0x180003fc8  jmp     short loc_180003FD7
0x180003fca  lea     rbx, aGettokeninform; "GetTokenInformation"
0x180003fd1  call    cs:__imp_GetLastError
0x180003fd7  mov     r8d, eax
0x180003fda  lea     rcx, aFwgettokeninfo_0; "FwGetTokenInformation"
0x180003fe1  mov     rdx, rbx
0x180003fe4  call    FwReportErrorAsWinError
0x180003fe9  mov     ebx, eax
0x180003feb  test    eax, eax
0x180003fed  js      loc_180003EEF
0x180003ff3  mov     rsi, r13
0x180003ff6  jmp     loc_180003CF7
0x180003ffb  call    cs:__imp_GetLastError
0x180004001  lea     rdx, aConvertsidtost_0; "ConvertSidToStringSidW"
0x180004008  mov     r8d, eax
0x18000400b  lea     rcx, aFwqueryrpcclie; "FwQueryRpcClientInfo"
0x180004012  call    FwReportErrorAsWinError
0x180004017  mov     ebx, eax
  ... truncated ...
```
