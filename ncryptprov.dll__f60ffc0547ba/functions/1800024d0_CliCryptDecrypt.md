# CliCryptDecrypt

- ea: `0x1800024d0`
- end: `0x180002d9d`
- name: `CliCryptDecrypt`
- size: `2253`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800024d0`
- `0x180002da4`
- `0x180002e60`
- `0x180002f8c`
- `0x18000af80`
- `0x18000b250`
- `0x180035974`
- `0x180038970`
- `0x18003948c`
- `0x180045abc`
- `0x180060f5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002727`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002993`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002727`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002993`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c13`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180002a77`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180002a77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180002a57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180002a57`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002635`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002635`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800029f8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800029f8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000254c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000254c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800028c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002d8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800028c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002d8c`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180002713`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180002c03`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180002713`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180002c03`
- `RPCRT4!I_RpcExceptionFilter` at `0x180062488`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800624aa`
- `RPCRT4!I_RpcExceptionFilter` at `0x180062488`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800624aa`
- `RPCRT4!NdrClientCall3` at `0x18000281c`
- `RPCRT4!NdrClientCall3` at `0x18000281c`

## string_xrefs

- `0x1800025d1`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x18000289d`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x1800029ca`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x180002abe`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x180002b08`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x180002ccb`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x180002cfd`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x180002d33`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`

## pseudocode

```c
__int64 __fastcall CliCryptDecrypt(
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
  int v9; // r13d
  int v13; // edx
  int v14; // r8d
  DWORD LastError; // ebx
  _BYTE *v16; // rbx
  int v17; // r13d
  int v18; // edx
  int v19; // r8d
  __int64 v20; // r8
  __int64 v21; // rdx
  CLIENT_CALL_RETURN v22; // rax
  int v23; // edx
  int v24; // r8d
  signed int v26; // eax
  __int64 v27; // r9
  DWORD v28; // eax
  int v29; // r8d
  HANDLE CurrentThread; // rax
  int v31; // edx
  int v32; // r8d
  __int64 v33; // r9
  __int64 v34; // r8
  int v35; // eax
  HANDLE hObject; // [rsp+78h] [rbp-170h] BYREF
  SIZE_T uBytes; // [rsp+80h] [rbp-168h] BYREF
  __int128 v38; // [rsp+88h] [rbp-160h] BYREF
  __int128 *v39; // [rsp+98h] [rbp-150h]
  void *TokenHandle; // [rsp+A0h] [rbp-148h] BYREF
  RPC_BINDING_HANDLE pv; // [rsp+B0h] [rbp-138h] BYREF
  __int64 v42; // [rsp+B8h] [rbp-130h]
  __int64 v43; // [rsp+C0h] [rbp-128h]
  __int64 v44; // [rsp+C8h] [rbp-120h]
  __int128 *v45; // [rsp+D8h] [rbp-110h]
  __int64 v46; // [rsp+E0h] [rbp-108h]
  int v47; // [rsp+E8h] [rbp-100h]
  _BYTE *v48; // [rsp+F0h] [rbp-F8h]
  __int64 v49; // [rsp+F8h] [rbp-F0h]
  int v50; // [rsp+100h] [rbp-E8h]
  __int64 v51; // [rsp+108h] [rbp-E0h]
  int v52; // [rsp+110h] [rbp-D8h]
  HANDLE *p_hObject; // [rsp+118h] [rbp-D0h]
  void *v54; // [rsp+120h] [rbp-C8h]
  _BYTE v55[152]; // [rsp+150h] [rbp-98h] BYREF

  v9 = a4;
  memset_0(v55, 0, 0x70u);
  v38 = 0;
  memset_0(&pv, 0, 0x98u);
  TokenHandle = 0;
  hObject = CreateEventW(0, 0, 0, 0);
  if ( hObject )
  {
    if ( NtCurrentTeb()->IsImpersonating )
    {
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v31,
            v32,
            (unsigned int)"Status",
            LastError,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
            202);
        goto LABEL_35;
      }
      v54 = TokenHandle;
    }
    if ( (a9 & 0x10) != 0 )
    {
      v26 = PackCipherPaddingInfo(a5, v55);
      LastError = v26;
      if ( v26 )
      {
        v27 = 728;
        goto LABEL_48;
      }
      if ( (unsigned __int8)IsGetMessageWPresent() && (unsigned int)IsKeyProtected(a1, a2) )
      {
        pv = g_RpcBindingContext;
        v42 = qword_18007A5E0;
        if ( a1 )
          v43 = *a1;
        else
          v43 = 0;
        if ( a2 )
          v44 = *a2;
        else
          v44 = 0;
        v46 = a3;
        v47 = v9;
        v48 = v55;
        v49 = a6;
        v50 = a7;
        v51 = a8;
        v52 = a9;
        p_hObject = &hObject;
        if ( !TrySubmitThreadpoolCallback(CliThreadCryptDecryptCallback, &pv, 0) )
        {
          v26 = GetLastError();
          LastError = v26;
          v27 = 757;
          goto LABEL_48;
        }
        v26 = CliWaitForCallBackCompletion(hObject, &pv);
        LastError = v26;
        if ( v26 < 0 )
        {
          v27 = 764;
          goto LABEL_48;
        }
      }
      else
      {
        if ( a2 )
          v33 = *a2;
        else
          LODWORD(v33) = 0;
        if ( a1 )
          v34 = *a1;
        else
          LODWORD(v34) = 0;
        v35 = c_SrvRpcCryptCipherDecrypt(
                (_DWORD)g_RpcBindingContext,
                qword_18007A5E0,
                v34,
                v33,
                a3,
                v9,
                (__int64)v55,
                a6,
                a7,
                a8,
                a9);
        LastError = v35;
        if ( v35 < 0 )
        {
          DebugTraceError(
            (unsigned int)v35,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
            786);
          goto LABEL_35;
        }
      }
LABEL_34:
      LastError = 0;
LABEL_35:
      if ( hObject )
      {
        CloseHandle(hObject);
        hObject = 0;
      }
      if ( TokenHandle )
        CloseHandle(TokenHandle);
      return LastError;
    }
    if ( !a5 )
    {
      v39 = 0;
      goto LABEL_8;
    }
    v39 = &v38;
    v38 = 0;
    if ( (a9 & 2) != 0 )
    {
      LODWORD(v38) = 2;
    }
    else
    {
      if ( (a9 & 0xC) == 0 )
      {
        if ( (a9 & 1) != 0 )
        {
          LODWORD(v38) = 1;
        }
        else
        {
          if ( (a9 & 0x20) == 0 )
          {
            LastError = -2146893815;
            DebugTraceError(
              2148073481LL,
              "Status",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
              384);
LABEL_9:
            if ( LastError )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v13,
                  v14,
                  (unsigned int)"Status",
                  LastError,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
                  41);
              goto LABEL_35;
            }
            if ( (unsigned __int8)IsGetMessageWPresent() )
            {
              v16 = 0;
              LODWORD(uBytes) = 0;
              v17 = 0;
              if ( a2 )
              {
                if ( !(unsigned int)CliCryptGetKeyProperty(
                                      (_DWORD)a1,
                                      (_DWORD)a2,
                                      (unsigned int)L"UI Policy",
                                      0,
                                      0,
                                      (__int64)&uBytes,
                                      0) )
                {
                  v16 = LocalAlloc(0, (unsigned int)uBytes);
                  if ( v16 )
                  {
                    if ( !(unsigned int)CliCryptGetKeyProperty(
                                          (_DWORD)a1,
                                          (_DWORD)a2,
                                          (unsigned int)L"UI Policy",
                                          (_DWORD)v16,
                                          uBytes,
                                          (__int64)&uBytes,
                                          0) )
                      LOBYTE(v17) = (v16[4] & 7) != 0;
                  }
                }
              }
              LocalFree(v16);
              if ( v17 )
              {
                pv = g_RpcBindingContext;
                v42 = qword_18007A5E0;
                if ( a1 )
                  v43 = *a1;
                else
                  v43 = 0;
                if ( a2 )
                  v44 = *a2;
                else
                  v44 = 0;
                v45 = v39;
                v46 = a3;
                v47 = a4;
                v49 = a6;
                v50 = a7;
                v51 = a8;
                v52 = a9;
                p_hObject = &hObject;
                if ( !TrySubmitThreadpoolCallback(CliThreadCryptDecryptCallback, &pv, 0) )
                {
                  LastError = GetLastError();
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    WPP_SF_sDsd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      v18,
                      v19,
                      (unsigned int)"Status",
                      LastError,
                      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
                      70);
                  goto LABEL_35;
                }
                v26 = CliWaitForCallBackCompletion(hObject, &pv);
                LastError = v26;
                if ( v26 < 0 )
                {
                  v27 = 845;
LABEL_48:
                  DebugTraceError(
                    (unsigned int)v26,
                    "Status",
                    "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
                    v27);
                  goto LABEL_35;
                }
                goto LABEL_34;
              }
              v9 = a4;
            }
            if ( a2 )
              v20 = *a2;
            else
              v20 = 0;
            if ( a1 )
              v21 = *a1;
            else
              v21 = 0;
            uBytes = 0;
            v22.Pointer = NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                            0x11u,
                            0,
                            g_RpcBindingContext,
                            qword_18007A5E0,
                            v21,
                            v20,
                            a3,
                            v9,
                            v39,
                            a6,
                            a7,
                            a8,
                            a9).Pointer;
            LastError = (DWORD)v22.Pointer;
            uBytes = v22.Simple;
            if ( SLODWORD(v22.Simple) < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v23,
                  v24,
                  (unsigned int)"Status",
                  v22.Simple,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
                  99);
              goto LABEL_35;
            }
            goto LABEL_34;
          }
          LODWORD(v38) = 5;
          *((_QWORD *)&v38 + 1) = a5;
        }
LABEL_8:
        LastError = 0;
        goto LABEL_9;
      }
      LODWORD(v38) = 3;
    }
    *((_QWORD *)&v38 + 1) = a5;
    goto LABEL_8;
  }
  v28 = GetLastError();
  LastError = v28;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)WPP_GLOBAL_Control,
      v29,
      (unsigned int)"Status",
      v28,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
      185);
  return LastError;
}

```

## disassembly

```asm
0x1800024d0  mov     rax, rsp
0x1800024d3  mov     [rax+8], rbx
0x1800024d7  mov     [rax+20h], r9d
0x1800024db  mov     [rax+18h], r8
0x1800024df  push    rsi
0x1800024e0  push    r12
0x1800024e2  push    r13
0x1800024e4  push    r14
0x1800024e6  push    r15
0x1800024e8  sub     rsp, 1C0h
0x1800024ef  mov     r13d, r9d
0x1800024f2  mov     rsi, r8
0x1800024f5  mov     r14, rdx
0x1800024f8  mov     r15, rcx
0x1800024fb  xor     edx, edx; Val
0x1800024fd  lea     r8d, [rdx+70h]; Size
0x180002501  lea     rcx, [rax-98h]; void *
0x180002508  call    memset_0
0x18000250d  xorps   xmm0, xmm0
0x180002510  movups  [rsp+1E8h+var_160], xmm0
0x180002518  xor     edx, edx; Val
0x18000251a  mov     r8d, 98h; Size
0x180002520  lea     rcx, [rsp+1E8h+pv]; void *
0x180002528  call    memset_0
0x18000252d  mov     [rsp+1E8h+TokenHandle], 0
0x180002539  mov     [rsp+1E8h+hObject], 0
0x180002542  xor     r9d, r9d; lpName
0x180002545  xor     r8d, r8d; bInitialState
0x180002548  xor     edx, edx; bManualReset
0x18000254a  xor     ecx, ecx; lpEventAttributes
0x18000254c  call    cs:__imp_CreateEventW
0x180002553  nop     dword ptr [rax+rax+00h]
0x180002558  mov     [rsp+1E8h+hObject], rax
0x18000255d  test    rax, rax
0x180002560  jz      loc_180002993
0x180002566  mov     eax, gs:179Ch
0x18000256e  test    eax, eax
0x180002570  jnz     loc_180002A57
0x180002576  mov     r12d, [rsp+1E8h+arg_40]
0x18000257e  test    r12b, 10h
0x180002582  jnz     loc_180002ADF
0x180002588  mov     rax, [rsp+1E8h+arg_20]
0x180002590  test    rax, rax
0x180002593  jz      loc_180002902
0x180002599  lea     rcx, [rsp+1E8h+var_160]
0x1800025a1  mov     [rsp+1E8h+var_150], rcx
0x1800025a9  xorps   xmm0, xmm0
0x1800025ac  movups  [rsp+1E8h+var_160], xmm0
0x1800025b4  test    r12b, 2
0x1800025b8  jz      loc_180002D17
0x1800025be  mov     dword ptr [rsp+1E8h+var_160], 2
0x1800025c9  mov     qword ptr [rsp+1E8h+var_160+8], rax
0x1800025d1  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800025d8  xor     ebx, ebx
0x1800025da  test    ebx, ebx
0x1800025dc  jnz     loc_180002913
0x1800025e2  call    IsGetMessageWPresent
0x1800025e7  test    al, al
0x1800025e9  jz      loc_180002784
0x1800025ef  xor     ebx, ebx
0x1800025f1  mov     dword ptr [rsp+1E8h+uBytes], ebx
0x1800025f8  xor     r13d, r13d
0x1800025fb  test    r14, r14
0x1800025fe  jz      short loc_180002632
0x180002600  mov     dword ptr [rsp+1E8h+var_1B8], ebx
0x180002604  lea     rax, [rsp+1E8h+uBytes]
0x18000260c  mov     [rsp+1E8h+var_1C0], rax
0x180002611  mov     dword ptr [rsp+1E8h+var_1C8], ebx
0x180002615  xor     r9d, r9d
0x180002618  lea     r8, aUiPolicy; "UI Policy"
0x18000261f  mov     rdx, r14
0x180002622  mov     rcx, r15
0x180002625  call    CliCryptGetKeyProperty
0x18000262a  test    eax, eax
0x18000262c  jz      loc_1800029EF
0x180002632  mov     rcx, rbx; hMem
0x180002635  call    cs:__imp_LocalFree
0x18000263c  nop     dword ptr [rax+rax+00h]
0x180002641  test    r13d, r13d
0x180002644  jz      loc_18000277C
0x18000264a  mov     rax, cs:g_RpcBindingContext
0x180002651  mov     [rsp+1E8h+pv], rax
0x180002659  mov     rax, cs:qword_18007A5E0
0x180002660  mov     [rsp+1E8h+var_130], rax
0x180002668  test    r15, r15
0x18000266b  jz      loc_180002939
0x180002671  mov     rax, [r15]
0x180002674  mov     [rsp+1E8h+var_128], rax
0x18000267c  test    r14, r14
0x18000267f  jz      loc_18000294A
0x180002685  mov     rax, [r14]
0x180002688  mov     [rsp+1E8h+var_120], rax
0x180002690  mov     rax, [rsp+1E8h+var_150]
0x180002698  mov     [rsp+1E8h+var_110], rax
0x1800026a0  mov     rax, [rsp+1E8h+arg_10]
0x1800026a8  mov     [rsp+1E8h+var_108], rax
0x1800026b0  mov     eax, [rsp+1E8h+arg_18]
0x1800026b7  mov     [rsp+1E8h+var_100], eax
0x1800026be  mov     rax, [rsp+1E8h+arg_28]
0x1800026c6  mov     [rsp+1E8h+var_F0], rax
0x1800026ce  mov     eax, [rsp+1E8h+arg_30]
0x1800026d5  mov     [rsp+1E8h+var_E8], eax
0x1800026dc  mov     rax, [rsp+1E8h+arg_38]
0x1800026e4  mov     [rsp+1E8h+var_E0], rax
0x1800026ec  mov     [rsp+1E8h+var_D8], r12d
0x1800026f4  lea     rax, [rsp+1E8h+hObject]
0x1800026f9  mov     [rsp+1E8h+var_D0], rax
0x180002701  xor     r8d, r8d; pcbe
0x180002704  lea     rdx, [rsp+1E8h+pv]; pv
0x18000270c  lea     rcx, _CliThreadCryptDecryptCallback; pfns
0x180002713  call    cs:__imp_TrySubmitThreadpoolCallback
0x18000271a  nop     dword ptr [rax+rax+00h]
0x18000271f  test    eax, eax
0x180002721  jnz     loc_18000295B
0x180002727  call    cs:__imp_GetLastError
0x18000272e  nop     dword ptr [rax+rax+00h]
0x180002733  mov     ebx, eax
0x180002735  lea     rcx, WPP_GLOBAL_Control
0x18000273c  mov     rax, cs:WPP_GLOBAL_Control
0x180002743  cmp     rax, rcx
0x180002746  jz      loc_1800028B6
0x18000274c  test    byte ptr [rax+1Ch], 1
0x180002750  jz      loc_1800028B6
0x180002756  mov     dword ptr [rsp+1E8h+var_1B8], 346h
0x18000275e  mov     [rsp+1E8h+var_1C0], rsi
0x180002763  mov     dword ptr [rsp+1E8h+var_1C8], ebx
0x180002767  lea     r9, aStatus; "Status"
0x18000276e  mov     rcx, [rax+10h]
0x180002772  call    WPP_SF_sDsd
0x180002777  jmp     loc_1800028B6
0x18000277c  mov     r13d, [rsp+1E8h+arg_18]
0x180002784  test    r14, r14
0x180002787  jz      loc_180002880
0x18000278d  mov     r8, [r14]
0x180002790  test    r15, r15
0x180002793  jz      loc_180002856
0x180002799  mov     rdx, [r15]
0x18000279c  mov     rcx, cs:qword_18007A5E0
0x1800027a3  mov     [rsp+1E8h+uBytes], 0
0x1800027af  mov     [rsp+1E8h+var_180], r12d
0x1800027b4  mov     rax, [rsp+1E8h+arg_38]
0x1800027bc  mov     [rsp+1E8h+var_188], rax
0x1800027c1  mov     eax, [rsp+1E8h+arg_30]
0x1800027c8  mov     [rsp+1E8h+var_190], eax
0x1800027cc  mov     rax, [rsp+1E8h+arg_28]
0x1800027d4  mov     [rsp+1E8h+var_198], rax
0x1800027d9  mov     rax, [rsp+1E8h+var_150]
0x1800027e1  mov     [rsp+1E8h+var_1A0], rax
0x1800027e6  mov     [rsp+1E8h+var_1A8], r13d
0x1800027eb  mov     rax, [rsp+1E8h+arg_10]
0x1800027f3  mov     [rsp+1E8h+var_1B0], rax
0x1800027f8  mov     [rsp+1E8h+var_1B8], r8
0x1800027fd  mov     [rsp+1E8h+var_1C0], rdx
0x180002802  mov     [rsp+1E8h+var_1C8], rcx
0x180002807  mov     r9, cs:g_RpcBindingContext
0x18000280e  xor     r8d, r8d; pReturnValue
0x180002811  lea     edx, [r8+11h]; nProcNum
0x180002815  lea     rcx, pProxyInfo; pProxyInfo
0x18000281c  call    cs:__imp_NdrClientCall3
0x180002823  nop     dword ptr [rax+rax+00h]
0x180002828  mov     rbx, rax
0x18000282b  mov     [rsp+1E8h+uBytes], rax
0x180002833  mov     [rsp+1E8h+var_178], ebx
0x180002837  test    eax, eax
0x180002839  jns     short loc_180002888
0x18000283b  lea     rcx, WPP_GLOBAL_Control
0x180002842  mov     rax, cs:WPP_GLOBAL_Control
0x180002849  cmp     rax, rcx
0x18000284c  jz      short loc_180002854
0x18000284e  test    byte ptr [rax+1Ch], 1
0x180002852  jnz     short loc_18000285D
0x180002854  jmp     short loc_1800028B6
0x180002856  xor     edx, edx
0x180002858  jmp     loc_18000279C
0x18000285d  mov     dword ptr [rsp+1E8h+var_1B8], 363h
0x180002865  mov     [rsp+1E8h+var_1C0], rsi
0x18000286a  mov     dword ptr [rsp+1E8h+var_1C8], ebx
0x18000286e  lea     r9, aStatus; "Status"
0x180002875  mov     rcx, [rax+10h]
0x180002879  call    WPP_SF_sDsd
0x18000287e  jmp     short loc_180002854
0x180002880  xor     r8d, r8d
0x180002883  jmp     loc_180002790
0x180002888  jmp     short loc_1800028B4
0x18000288a  mov     ecx, eax
0x18000288c  call    HResultFromRpcException
0x180002891  mov     ebx, eax
0x180002893  mov     [rsp+1E8h+var_178], eax
0x180002897  mov     r9d, 36Ah
0x18000289d  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800028a4  lea     rdx, aStatus; "Status"
0x1800028ab  mov     ecx, eax
0x1800028ad  call    DebugTraceError
0x1800028b2  jmp     short loc_1800028B6
0x1800028b4  xor     ebx, ebx
0x1800028b6  mov     rcx, [rsp+1E8h+hObject]; hObject
0x1800028bb  test    rcx, rcx
0x1800028be  jz      short loc_1800028D5
0x1800028c0  call    cs:__imp_CloseHandle
0x1800028c7  nop     dword ptr [rax+rax+00h]
0x1800028cc  mov     [rsp+1E8h+hObject], 0
0x1800028d5  mov     rcx, [rsp+1E8h+TokenHandle]; hObject
0x1800028dd  test    rcx, rcx
0x1800028e0  jnz     loc_180002D8C
0x1800028e6  mov     eax, ebx
0x1800028e8  mov     rbx, [rsp+1E8h+arg_0]
0x1800028f0  add     rsp, 1C0h
0x1800028f7  pop     r15
0x1800028f9  pop     r14
0x1800028fb  pop     r13
0x1800028fd  pop     r12
0x1800028ff  pop     rsi
0x180002900  retn
0x180002902  mov     [rsp+1E8h+var_150], 0
0x18000290e  jmp     loc_1800025D1
0x180002913  lea     rcx, WPP_GLOBAL_Control
0x18000291a  mov     rax, cs:WPP_GLOBAL_Control
0x180002921  cmp     rax, rcx
0x180002924  jz      short loc_1800028B6
0x180002926  test    byte ptr [rax+1Ch], 1
0x18000292a  jz      short loc_1800028B6
0x18000292c  mov     dword ptr [rsp+1E8h+var_1B8], 329h
0x180002934  jmp     loc_18000275E
0x180002939  mov     [rsp+1E8h+var_128], 0
0x180002945  jmp     loc_18000267C
0x18000294a  mov     [rsp+1E8h+var_120], 0
0x180002956  jmp     loc_180002690
0x18000295b  lea     rdx, [rsp+1E8h+pv]
0x180002963  mov     rcx, [rsp+1E8h+hObject]
0x180002968  call    _CliWaitForCallBackCompletion
0x18000296d  mov     ebx, eax
0x18000296f  test    eax, eax
0x180002971  jns     loc_1800028B4
0x180002977  mov     r9d, 34Dh
0x18000297d  mov     r8, rsi
0x180002980  lea     rdx, aStatus; "Status"
0x180002987  mov     ecx, eax
0x180002989  call    DebugTraceError
0x18000298e  jmp     loc_1800028B6
0x180002993  call    cs:__imp_GetLastError
0x18000299a  nop     dword ptr [rax+rax+00h]
0x18000299f  mov     ebx, eax
0x1800029a1  lea     rcx, WPP_GLOBAL_Control
0x1800029a8  mov     rdx, cs:WPP_GLOBAL_Control
0x1800029af  cmp     rdx, rcx
0x1800029b2  jz      loc_1800028E6
0x1800029b8  test    byte ptr [rdx+1Ch], 1
0x1800029bc  jz      loc_1800028E6
0x1800029c2  mov     dword ptr [rsp+1E8h+var_1B8], 2B9h
0x1800029ca  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800029d1  mov     [rsp+1E8h+var_1C0], rsi
0x1800029d6  mov     dword ptr [rsp+1E8h+var_1C8], eax
0x1800029da  lea     r9, aStatus; "Status"
0x1800029e1  mov     rcx, [rdx+10h]
0x1800029e5  call    WPP_SF_sDsd
0x1800029ea  jmp     loc_1800028E6
0x1800029ef  mov     edx, dword ptr [rsp+1E8h+uBytes]; uBytes
0x1800029f6  xor     ecx, ecx; uFlags
0x1800029f8  call    cs:__imp_LocalAlloc
0x1800029ff  nop     dword ptr [rax+rax+00h]
0x180002a04  mov     rbx, rax
0x180002a07  test    rax, rax
0x180002a0a  jz      loc_180002632
0x180002a10  mov     dword ptr [rsp+1E8h+var_1B8], r13d
0x180002a15  lea     rax, [rsp+1E8h+uBytes]
0x180002a1d  mov     [rsp+1E8h+var_1C0], rax
0x180002a22  mov     ecx, dword ptr [rsp+1E8h+uBytes]
0x180002a29  mov     dword ptr [rsp+1E8h+var_1C8], ecx
0x180002a2d  mov     r9, rbx
0x180002a30  lea     r8, aUiPolicy; "UI Policy"
0x180002a37  mov     rdx, r14
0x180002a3a  mov     rcx, r15
0x180002a3d  call    CliCryptGetKeyProperty
0x180002a42  test    eax, eax
0x180002a44  jnz     loc_180002632
0x180002a4a  test    byte ptr [rbx+4], 7
0x180002a4e  setnz   r13b
0x180002a52  jmp     loc_180002632
0x180002a57  call    cs:__imp_GetCurrentThread
0x180002a5e  nop     dword ptr [rax+rax+00h]
0x180002a63  mov     rcx, rax; ThreadHandle
0x180002a66  lea     r9, [rsp+1E8h+TokenHandle]; TokenHandle
0x180002a6e  mov     edx, 0Ch; DesiredAccess
0x180002a73  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x180002a77  call    cs:__imp_OpenThreadToken
0x180002a7e  nop     dword ptr [rax+rax+00h]
0x180002a83  test    eax, eax
0x180002a85  jnz     short loc_180002ACA
0x180002a87  call    cs:__imp_GetLastError
0x180002a8e  nop     dword ptr [rax+rax+00h]
0x180002a93  mov     ebx, eax
0x180002a95  lea     rcx, WPP_GLOBAL_Control
0x180002a9c  mov     rax, cs:WPP_GLOBAL_Control
0x180002aa3  cmp     rax, rcx
0x180002aa6  jz      loc_1800028B6
0x180002aac  test    byte ptr [rax+1Ch], 1
0x180002ab0  jz      loc_1800028B6
0x180002ab6  mov     dword ptr [rsp+1E8h+var_1B8], 2CAh
0x180002abe  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002ac5  jmp     loc_18000275E
  ... truncated ...
```
