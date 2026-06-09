# CliCryptEncrypt

- ea: `0x1800018d0`
- end: `0x180001fc2`
- name: `CliCryptEncrypt`
- size: `1778`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800018d0`
- `0x180002da4`
- `0x180002f8c`
- `0x18000af80`
- `0x18000b250`
- `0x180038970`
- `0x18003948c`
- `0x180045abc`
- `0x180045bb4`
- `0x180060f5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001962`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800019cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001b3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001962`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800019cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001b3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e11`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800019bc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800019bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000199c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000199c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000194c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000194c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001f78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001f9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001f78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001f9a`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180001b2d`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180001e01`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180001b2d`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180001e01`
- `RPCRT4!I_RpcExceptionFilter` at `0x180062416`
- `RPCRT4!I_RpcExceptionFilter` at `0x180062438`
- `RPCRT4!I_RpcExceptionFilter` at `0x180062416`
- `RPCRT4!I_RpcExceptionFilter` at `0x180062438`
- `RPCRT4!NdrClientCall3` at `0x180001ee8`
- `RPCRT4!NdrClientCall3` at `0x180001ee8`

## string_xrefs

- `0x180001976`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x1800019e0`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x180001bf8`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x180001c2a`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x180001c9c`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x180001cef`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x180001f58`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`

## pseudocode

```c
__int64 __fastcall CliCryptEncrypt(
        __int64 *a1,
        __int64 *a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        int a7,
        __int64 a8,
        int a9)
{
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  int v15; // eax
  __int64 v16; // r9
  __int64 v17; // rcx
  __int64 v18; // r9
  __int64 v19; // r8
  int v20; // eax
  __int128 *v21; // r13
  __int64 v22; // r8
  __int64 v23; // rdx
  CLIENT_CALL_RETURN v24; // rax
  int v25; // edx
  int v26; // r8d
  HANDLE hObject; // [rsp+78h] [rbp-160h] BYREF
  __int128 v29; // [rsp+80h] [rbp-158h] BYREF
  void *TokenHandle; // [rsp+90h] [rbp-148h] BYREF
  CLIENT_CALL_RETURN v31; // [rsp+98h] [rbp-140h]
  RPC_BINDING_HANDLE pv; // [rsp+A0h] [rbp-138h] BYREF
  __int64 v33; // [rsp+A8h] [rbp-130h]
  __int64 v34; // [rsp+B0h] [rbp-128h]
  __int64 v35; // [rsp+B8h] [rbp-120h]
  __int128 *v36; // [rsp+C8h] [rbp-110h]
  __int64 v37; // [rsp+D0h] [rbp-108h]
  int v38; // [rsp+D8h] [rbp-100h]
  _DWORD *v39; // [rsp+E0h] [rbp-F8h]
  __int64 v40; // [rsp+E8h] [rbp-F0h]
  int v41; // [rsp+F0h] [rbp-E8h]
  __int64 v42; // [rsp+F8h] [rbp-E0h]
  int v43; // [rsp+100h] [rbp-D8h]
  HANDLE *p_hObject; // [rsp+108h] [rbp-D0h]
  void *v45; // [rsp+110h] [rbp-C8h]
  _DWORD v46[38]; // [rsp+140h] [rbp-98h] BYREF

  memset_0(v46, 0, 0x70u);
  v29 = 0;
  memset_0(&pv, 0, 0x98u);
  TokenHandle = 0;
  hObject = CreateEventW(0, 0, 0, 0);
  if ( !hObject )
  {
    LastError = GetLastError();
    DebugTraceError(LastError, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c", 1065);
    return LastError;
  }
  if ( NtCurrentTeb()->IsImpersonating )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
    {
      v15 = GetLastError();
      v16 = 1081;
LABEL_6:
      LastError = v15;
      goto LABEL_7;
    }
    v45 = TokenHandle;
  }
  if ( (a9 & 0x10) != 0 )
  {
    v15 = PackCipherPaddingInfo(a5, v46);
    LastError = v15;
    if ( v15 )
    {
      v16 = 1095;
      goto LABEL_7;
    }
    if ( !(unsigned __int8)IsGetMessageWPresent() || !(unsigned int)IsKeyProtected((int)a1, (__int64)a2) )
    {
      if ( a2 )
        v18 = *a2;
      else
        LODWORD(v18) = 0;
      if ( a1 )
        v19 = *a1;
      else
        LODWORD(v19) = 0;
      v20 = c_SrvRpcCryptCipherEncrypt(
              (_DWORD)g_RpcBindingContext,
              qword_18007A5E0,
              v19,
              v18,
              a3,
              a4,
              (__int64)v46,
              a6,
              a7,
              a8,
              a9);
      LastError = v20;
      if ( v20 < 0 )
        DebugTraceError(
          (unsigned int)v20,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
          1155);
      goto LABEL_71;
    }
    pv = g_RpcBindingContext;
    v33 = qword_18007A5E0;
    if ( a1 )
      v34 = *a1;
    else
      v34 = 0;
    if ( a2 )
      v35 = *a2;
    else
      v35 = 0;
    v37 = a3;
    v38 = a4;
    v39 = v46;
    v40 = a6;
    v41 = a7;
    v42 = a8;
    v43 = a9;
    p_hObject = &hObject;
    if ( TrySubmitThreadpoolCallback((PTP_SIMPLE_CALLBACK)CliThreadCryptEncryptCallback, &pv, 0) )
    {
      v15 = CliWaitForCallBackCompletion(hObject, (__int64)&pv);
      LastError = v15;
      if ( v15 >= 0 )
        goto LABEL_71;
      v16 = 1132;
      goto LABEL_7;
    }
    v15 = GetLastError();
    v16 = 1125;
    goto LABEL_6;
  }
  if ( !a5 )
  {
    v21 = 0;
    goto LABEL_46;
  }
  v21 = &v29;
  v29 = 0;
  if ( (a9 & 2) != 0 )
  {
    LODWORD(v29) = 2;
LABEL_37:
    *((_QWORD *)&v29 + 1) = a5;
LABEL_46:
    LastError = 0;
    goto LABEL_47;
  }
  if ( (a9 & 0xC) != 0 )
  {
    LODWORD(v29) = 3;
    goto LABEL_37;
  }
  if ( (a9 & 1) != 0 )
  {
    LODWORD(v29) = 1;
    goto LABEL_46;
  }
  if ( (a9 & 0x20) != 0 )
  {
    LODWORD(v29) = 5;
    *((_QWORD *)&v29 + 1) = a5;
    goto LABEL_46;
  }
  LastError = -2146893815;
  DebugTraceError(2148073481LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c", 384);
LABEL_47:
  if ( LastError )
  {
    v16 = 1178;
    v17 = LastError;
    goto LABEL_8;
  }
  if ( !(unsigned __int8)IsGetMessageWPresent() || !(unsigned int)IsKeyProtected((int)a1, (__int64)a2) )
  {
    if ( a2 )
      v22 = *a2;
    else
      v22 = 0;
    if ( a1 )
      v23 = *a1;
    else
      v23 = 0;
    v31.Simple = 0;
    v24.Pointer = NdrClientCall3(
                    (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                    0x10u,
                    0,
                    g_RpcBindingContext,
                    qword_18007A5E0,
                    v23,
                    v22,
                    a3,
                    a4,
                    v21,
                    a6,
                    a7,
                    a8,
                    a9).Pointer;
    LastError = (DWORD)v24.Pointer;
    v31.Pointer = v24.Pointer;
    if ( SLODWORD(v24.Simple) < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v25,
        v26,
        (unsigned int)"Status",
        v24.Simple,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
        213);
    }
    goto LABEL_71;
  }
  pv = g_RpcBindingContext;
  v33 = qword_18007A5E0;
  if ( a1 )
    v34 = *a1;
  else
    v34 = 0;
  if ( a2 )
    v35 = *a2;
  else
    v35 = 0;
  v37 = a3;
  v38 = a4;
  v36 = v21;
  v40 = a6;
  v41 = a7;
  v42 = a8;
  v43 = a9;
  p_hObject = &hObject;
  if ( TrySubmitThreadpoolCallback((PTP_SIMPLE_CALLBACK)CliThreadCryptEncryptCallback, &pv, 0) )
  {
    v15 = CliWaitForCallBackCompletion(hObject, (__int64)&pv);
    LastError = v15;
    if ( v15 >= 0 )
      goto LABEL_71;
    v16 = 1214;
  }
  else
  {
    v15 = GetLastError();
    LastError = v15;
    v16 = 1207;
  }
LABEL_7:
  v17 = (unsigned int)v15;
LABEL_8:
  DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c", v16);
LABEL_71:
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x1800018d0  mov     rax, rsp
0x1800018d3  mov     [rax+8], rbx
0x1800018d7  mov     [rax+20h], r9d
0x1800018db  mov     [rax+18h], r8
0x1800018df  push    rsi
0x1800018e0  push    r12
0x1800018e2  push    r13
0x1800018e4  push    r14
0x1800018e6  push    r15
0x1800018e8  sub     rsp, 1B0h
0x1800018ef  mov     esi, r9d
0x1800018f2  mov     r13, r8
0x1800018f5  mov     r14, rdx
0x1800018f8  mov     r15, rcx
0x1800018fb  xor     edx, edx; Val
0x1800018fd  lea     r8d, [rdx+70h]; Size
0x180001901  lea     rcx, [rax-98h]; void *
0x180001908  call    memset_0
0x18000190d  xorps   xmm0, xmm0
0x180001910  movups  [rsp+1D8h+var_158], xmm0
0x180001918  xor     edx, edx; Val
0x18000191a  mov     r8d, 98h; Size
0x180001920  lea     rcx, [rsp+1D8h+pv]; void *
0x180001928  call    memset_0
0x18000192d  mov     [rsp+1D8h+hObject], 0
0x180001936  mov     [rsp+1D8h+TokenHandle], 0
0x180001942  xor     r9d, r9d; lpName
0x180001945  xor     r8d, r8d; bInitialState
0x180001948  xor     edx, edx; bManualReset
0x18000194a  xor     ecx, ecx; lpEventAttributes
0x18000194c  call    cs:__imp_CreateEventW
0x180001953  nop     dword ptr [rax+rax+00h]
0x180001958  mov     [rsp+1D8h+hObject], rax
0x18000195d  test    rax, rax
0x180001960  jnz     short loc_180001990
0x180001962  call    cs:__imp_GetLastError
0x180001969  nop     dword ptr [rax+rax+00h]
0x18000196e  mov     ebx, eax
0x180001970  mov     r9d, 429h
0x180001976  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000197d  lea     rdx, aStatus; "Status"
0x180001984  mov     ecx, eax
0x180001986  call    DebugTraceError
0x18000198b  jmp     loc_180001FA6
0x180001990  mov     eax, gs:179Ch
0x180001998  test    eax, eax
0x18000199a  jz      short loc_180001A0A
0x18000199c  call    cs:__imp_GetCurrentThread
0x1800019a3  nop     dword ptr [rax+rax+00h]
0x1800019a8  mov     rcx, rax; ThreadHandle
0x1800019ab  lea     r9, [rsp+1D8h+TokenHandle]; TokenHandle
0x1800019b3  mov     edx, 0Ch; DesiredAccess
0x1800019b8  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x1800019bc  call    cs:__imp_OpenThreadToken
0x1800019c3  nop     dword ptr [rax+rax+00h]
0x1800019c8  test    eax, eax
0x1800019ca  jnz     short loc_1800019FA
0x1800019cc  call    cs:__imp_GetLastError
0x1800019d3  nop     dword ptr [rax+rax+00h]
0x1800019d8  mov     r9d, 439h
0x1800019de  mov     ebx, eax
0x1800019e0  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800019e7  mov     ecx, eax
0x1800019e9  lea     rdx, aStatus; "Status"
0x1800019f0  call    DebugTraceError
0x1800019f5  jmp     loc_180001F6E
0x1800019fa  mov     rax, [rsp+1D8h+TokenHandle]
0x180001a02  mov     [rsp+1D8h+var_C8], rax
0x180001a0a  mov     r12d, [rsp+1D8h+arg_40]
0x180001a12  test    r12b, 10h
0x180001a16  jz      loc_180001C44
0x180001a1c  lea     rdx, [rsp+1D8h+var_98]
0x180001a24  mov     rcx, [rsp+1D8h+arg_20]
0x180001a2c  call    _PackCipherPaddingInfo
0x180001a31  mov     ebx, eax
0x180001a33  test    eax, eax
0x180001a35  jz      short loc_180001A3F
0x180001a37  mov     r9d, 447h
0x180001a3d  jmp     short loc_1800019E0
0x180001a3f  call    IsGetMessageWPresent
0x180001a44  test    al, al
0x180001a46  jz      loc_180001B7B
0x180001a4c  mov     rdx, r14
0x180001a4f  mov     rcx, r15
0x180001a52  call    IsKeyProtected
0x180001a57  test    eax, eax
0x180001a59  jz      loc_180001B7B
0x180001a5f  mov     rax, cs:g_RpcBindingContext
0x180001a66  mov     [rsp+1D8h+pv], rax
0x180001a6e  mov     rax, cs:qword_18007A5E0
0x180001a75  mov     [rsp+1D8h+var_130], rax
0x180001a7d  test    r15, r15
0x180001a80  jz      short loc_180001A8F
0x180001a82  mov     rax, [r15]
0x180001a85  mov     [rsp+1D8h+var_128], rax
0x180001a8d  jmp     short loc_180001A9B
0x180001a8f  mov     [rsp+1D8h+var_128], 0
0x180001a9b  test    r14, r14
0x180001a9e  jz      short loc_180001AAD
0x180001aa0  mov     rax, [r14]
0x180001aa3  mov     [rsp+1D8h+var_120], rax
0x180001aab  jmp     short loc_180001AB9
0x180001aad  mov     [rsp+1D8h+var_120], 0
0x180001ab9  mov     [rsp+1D8h+var_108], r13
0x180001ac1  mov     [rsp+1D8h+var_100], esi
0x180001ac8  lea     rax, [rsp+1D8h+var_98]
0x180001ad0  mov     [rsp+1D8h+var_F8], rax
0x180001ad8  mov     rax, [rsp+1D8h+arg_28]
0x180001ae0  mov     [rsp+1D8h+var_F0], rax
0x180001ae8  mov     eax, [rsp+1D8h+arg_30]
0x180001aef  mov     [rsp+1D8h+var_E8], eax
0x180001af6  mov     rax, [rsp+1D8h+arg_38]
0x180001afe  mov     [rsp+1D8h+var_E0], rax
0x180001b06  mov     [rsp+1D8h+var_D8], r12d
0x180001b0e  lea     rax, [rsp+1D8h+hObject]
0x180001b13  mov     [rsp+1D8h+var_D0], rax
0x180001b1b  xor     r8d, r8d; pcbe
0x180001b1e  lea     rdx, [rsp+1D8h+pv]; pv
0x180001b26  lea     rcx, _CliThreadCryptEncryptCallback; pfns
0x180001b2d  call    cs:__imp_TrySubmitThreadpoolCallback
0x180001b34  nop     dword ptr [rax+rax+00h]
0x180001b39  test    eax, eax
0x180001b3b  jnz     short loc_180001B54
0x180001b3d  call    cs:__imp_GetLastError
0x180001b44  nop     dword ptr [rax+rax+00h]
0x180001b49  mov     r9d, 465h
0x180001b4f  jmp     loc_1800019DE
0x180001b54  lea     rdx, [rsp+1D8h+pv]
0x180001b5c  mov     rcx, [rsp+1D8h+hObject]
0x180001b61  call    _CliWaitForCallBackCompletion
0x180001b66  mov     ebx, eax
0x180001b68  test    eax, eax
0x180001b6a  jns     loc_180001C12
0x180001b70  mov     r9d, 46Ch
0x180001b76  jmp     loc_1800019E0
0x180001b7b  test    r14, r14
0x180001b7e  jz      short loc_180001B85
0x180001b80  mov     r9, [r14]
0x180001b83  jmp     short loc_180001B88
0x180001b85  xor     r9d, r9d
0x180001b88  test    r15, r15
0x180001b8b  jz      short loc_180001B92
0x180001b8d  mov     r8, [r15]
0x180001b90  jmp     short loc_180001B95
0x180001b92  xor     r8d, r8d
0x180001b95  mov     dword ptr [rsp+1D8h+var_188], r12d
0x180001b9a  mov     rax, [rsp+1D8h+arg_38]
0x180001ba2  mov     [rsp+1D8h+var_190], rax
0x180001ba7  mov     eax, [rsp+1D8h+arg_30]
0x180001bae  mov     [rsp+1D8h+var_198], eax
0x180001bb2  mov     rax, [rsp+1D8h+arg_28]
0x180001bba  mov     [rsp+1D8h+var_1A0], rax
0x180001bbf  lea     rax, [rsp+1D8h+var_98]
0x180001bc7  mov     [rsp+1D8h+var_1A8], rax
0x180001bcc  mov     dword ptr [rsp+1D8h+var_1B0], esi
0x180001bd0  mov     [rsp+1D8h+var_1B8], r13
0x180001bd5  mov     rdx, cs:qword_18007A5E0
0x180001bdc  mov     rcx, cs:g_RpcBindingContext
0x180001be3  call    c_SrvRpcCryptCipherEncrypt
0x180001be8  mov     ebx, eax
0x180001bea  mov     [rsp+1D8h+var_168], eax
0x180001bee  test    eax, eax
0x180001bf0  jns     short loc_180001C12
0x180001bf2  mov     r9d, 483h
0x180001bf8  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001bff  lea     rdx, aStatus; "Status"
0x180001c06  mov     ecx, eax
0x180001c08  call    DebugTraceError
0x180001c0d  jmp     loc_180001F6E
0x180001c12  jmp     loc_180001F6E
0x180001c17  mov     ecx, eax
0x180001c19  call    HResultFromRpcException
0x180001c1e  mov     ebx, eax
0x180001c20  mov     [rsp+1D8h+var_168], eax
0x180001c24  mov     r9d, 48Ah
0x180001c2a  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001c31  lea     rdx, aStatus; "Status"
0x180001c38  mov     ecx, eax
0x180001c3a  call    DebugTraceError
0x180001c3f  jmp     loc_180001F6E
0x180001c44  mov     rax, [rsp+1D8h+arg_20]
0x180001c4c  test    rax, rax
0x180001c4f  jz      loc_180001CEC
0x180001c55  lea     r13, [rsp+1D8h+var_158]
0x180001c5d  xorps   xmm0, xmm0
0x180001c60  movups  [rsp+1D8h+var_158], xmm0
0x180001c68  test    r12b, 2
0x180001c6c  jz      short loc_180001C83
0x180001c6e  mov     dword ptr [rsp+1D8h+var_158], 2
0x180001c79  mov     qword ptr [rsp+1D8h+var_158+8], rax
0x180001c81  jmp     short loc_180001CEF
0x180001c83  test    r12b, 0Ch
0x180001c87  jnz     short loc_180001CDF
0x180001c89  test    r12b, 1
0x180001c8d  jz      short loc_180001C9C
0x180001c8f  mov     dword ptr [rsp+1D8h+var_158], 1
0x180001c9a  jmp     short loc_180001CEF
0x180001c9c  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001ca3  test    r12b, 20h
0x180001ca7  jz      short loc_180001CBE
0x180001ca9  mov     dword ptr [rsp+1D8h+var_158], 5
0x180001cb4  mov     qword ptr [rsp+1D8h+var_158+8], rax
0x180001cbc  jmp     short loc_180001CF6
0x180001cbe  mov     ebx, 80090009h
0x180001cc3  mov     r9d, 180h
0x180001cc9  mov     r8, rsi
0x180001ccc  lea     rdx, aStatus; "Status"
0x180001cd3  mov     ecx, 80090009h
0x180001cd8  call    DebugTraceError
0x180001cdd  jmp     short loc_180001CF8
0x180001cdf  mov     dword ptr [rsp+1D8h+var_158], 3
0x180001cea  jmp     short loc_180001C79
0x180001cec  xor     r13d, r13d
0x180001cef  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001cf6  xor     ebx, ebx
0x180001cf8  test    ebx, ebx
0x180001cfa  jz      short loc_180001D0C
0x180001cfc  mov     r9d, 49Ah
0x180001d02  mov     r8, rsi
0x180001d05  mov     ecx, ebx
0x180001d07  jmp     loc_1800019E9
0x180001d0c  call    IsGetMessageWPresent
0x180001d11  test    al, al
0x180001d13  jz      loc_180001E51
0x180001d19  mov     rdx, r14
0x180001d1c  mov     rcx, r15
0x180001d1f  call    IsKeyProtected
0x180001d24  test    eax, eax
0x180001d26  jz      loc_180001E51
0x180001d2c  mov     rax, cs:g_RpcBindingContext
0x180001d33  mov     [rsp+1D8h+pv], rax
0x180001d3b  mov     rax, cs:qword_18007A5E0
0x180001d42  mov     [rsp+1D8h+var_130], rax
0x180001d4a  test    r15, r15
0x180001d4d  jz      short loc_180001D5C
0x180001d4f  mov     rax, [r15]
0x180001d52  mov     [rsp+1D8h+var_128], rax
0x180001d5a  jmp     short loc_180001D68
0x180001d5c  mov     [rsp+1D8h+var_128], 0
0x180001d68  test    r14, r14
0x180001d6b  jz      short loc_180001D7A
0x180001d6d  mov     rax, [r14]
0x180001d70  mov     [rsp+1D8h+var_120], rax
0x180001d78  jmp     short loc_180001D86
0x180001d7a  mov     [rsp+1D8h+var_120], 0
0x180001d86  mov     rax, [rsp+1D8h+arg_10]
0x180001d8e  mov     [rsp+1D8h+var_108], rax
0x180001d96  mov     eax, [rsp+1D8h+arg_18]
0x180001d9d  mov     [rsp+1D8h+var_100], eax
0x180001da4  mov     [rsp+1D8h+var_110], r13
0x180001dac  mov     rax, [rsp+1D8h+arg_28]
0x180001db4  mov     [rsp+1D8h+var_F0], rax
0x180001dbc  mov     eax, [rsp+1D8h+arg_30]
0x180001dc3  mov     [rsp+1D8h+var_E8], eax
0x180001dca  mov     rax, [rsp+1D8h+arg_38]
0x180001dd2  mov     [rsp+1D8h+var_E0], rax
0x180001dda  mov     [rsp+1D8h+var_D8], r12d
0x180001de2  lea     rax, [rsp+1D8h+hObject]
0x180001de7  mov     [rsp+1D8h+var_D0], rax
0x180001def  xor     r8d, r8d; pcbe
0x180001df2  lea     rdx, [rsp+1D8h+pv]; pv
0x180001dfa  lea     rcx, _CliThreadCryptEncryptCallback; pfns
0x180001e01  call    cs:__imp_TrySubmitThreadpoolCallback
0x180001e08  nop     dword ptr [rax+rax+00h]
0x180001e0d  test    eax, eax
0x180001e0f  jnz     short loc_180001E2D
0x180001e11  call    cs:__imp_GetLastError
0x180001e18  nop     dword ptr [rax+rax+00h]
0x180001e1d  mov     ebx, eax
0x180001e1f  mov     r9d, 4B7h
0x180001e25  mov     r8, rsi
0x180001e28  jmp     loc_1800019E7
0x180001e2d  lea     rdx, [rsp+1D8h+pv]
0x180001e35  mov     rcx, [rsp+1D8h+hObject]
0x180001e3a  call    _CliWaitForCallBackCompletion
0x180001e3f  mov     ebx, eax
0x180001e41  test    eax, eax
0x180001e43  jns     loc_180001F6E
0x180001e49  mov     r9d, 4BEh
0x180001e4f  jmp     short loc_180001E25
0x180001e51  test    r14, r14
0x180001e54  jz      short loc_180001E5B
0x180001e56  mov     r8, [r14]
0x180001e59  jmp     short loc_180001E5E
0x180001e5b  xor     r8d, r8d
0x180001e5e  test    r15, r15
0x180001e61  jz      short loc_180001E68
0x180001e63  mov     rdx, [r15]
0x180001e66  jmp     short loc_180001E6A
0x180001e68  xor     edx, edx
0x180001e6a  mov     rcx, cs:qword_18007A5E0
0x180001e71  mov     [rsp+1D8h+var_140], 0
0x180001e7d  mov     [rsp+1D8h+var_170], r12d
0x180001e82  mov     rax, [rsp+1D8h+arg_38]
0x180001e8a  mov     [rsp+1D8h+var_178], rax
0x180001e8f  mov     eax, [rsp+1D8h+arg_30]
0x180001e96  mov     [rsp+1D8h+var_180], eax
0x180001e9a  mov     rax, [rsp+1D8h+arg_28]
0x180001ea2  mov     [rsp+1D8h+var_188], rax
0x180001ea7  mov     [rsp+1D8h+var_190], r13
  ... truncated ...
```
