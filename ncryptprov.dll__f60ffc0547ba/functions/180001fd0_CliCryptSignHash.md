# CliCryptSignHash

- ea: `0x180001fd0`
- end: `0x1800024c6`
- name: `CliCryptSignHash`
- size: `1270`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001fd0`
- `0x180002da4`
- `0x180002f8c`
- `0x18000af80`
- `0x18000b250`
- `0x180038970`
- `0x18003948c`
- `0x180060f5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002275`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000241f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002433`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002275`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000241f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002433`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000240f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000240f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800023ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800023ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002015`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002015`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800022d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800024b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800022d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800024b5`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180002487`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180002487`
- `RPCRT4!I_RpcExceptionFilter` at `0x180062460`
- `RPCRT4!I_RpcExceptionFilter` at `0x180062460`
- `RPCRT4!NdrClientCall3` at `0x180002107`
- `RPCRT4!NdrClientCall3` at `0x180002107`

## string_xrefs

- `0x180002065`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x180002169`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x1800021b6`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x1800022ac`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x180002320`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`

## pseudocode

```c
__int64 __fastcall CliCryptSignHash(
        __int64 *a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int a7,
        __int64 a8,
        int a9)
{
  __int64 v9; // r14
  int v13; // r8d
  __int128 *v14; // r13
  __int64 v15; // r8
  __int64 v16; // rdx
  CLIENT_CALL_RETURN v17; // rax
  DWORD Pointer; // ebx
  int v20; // r14d
  DWORD v21; // eax
  int v22; // r8d
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  __int64 v25; // r9
  HANDLE hObject; // [rsp+70h] [rbp-108h] BYREF
  __int128 v27; // [rsp+78h] [rbp-100h] BYREF
  int v28; // [rsp+88h] [rbp-F0h]
  void *TokenHandle; // [rsp+90h] [rbp-E8h] BYREF
  CLIENT_CALL_RETURN v30; // [rsp+98h] [rbp-E0h]
  _QWORD pv[2]; // [rsp+A0h] [rbp-D8h] BYREF
  __int64 v32; // [rsp+B0h] [rbp-C8h]
  __int64 v33; // [rsp+B8h] [rbp-C0h]
  __int128 *v34; // [rsp+C8h] [rbp-B0h]
  __int64 v35; // [rsp+D0h] [rbp-A8h]
  int v36; // [rsp+D8h] [rbp-A0h]
  __int64 v37; // [rsp+E8h] [rbp-90h]
  int v38; // [rsp+F0h] [rbp-88h]
  __int64 v39; // [rsp+F8h] [rbp-80h]
  int v40; // [rsp+100h] [rbp-78h]
  HANDLE *p_hObject; // [rsp+108h] [rbp-70h]
  void *v42; // [rsp+110h] [rbp-68h]

  v9 = a4;
  DWORD2(v27) = 0;
  *(_QWORD *)&v27 = 0;
  TokenHandle = 0;
  hObject = CreateEventW(0, 0, 0, 0);
  if ( hObject )
  {
    if ( a3 )
    {
      v14 = &v27;
      v27 = 0;
      if ( (a9 & 2) != 0 )
      {
        LODWORD(v27) = 2;
LABEL_5:
        *((_QWORD *)&v27 + 1) = a3;
        goto LABEL_6;
      }
      if ( (a9 & 0xC) == 0 )
      {
        if ( (a9 & 1) != 0 )
        {
          LODWORD(v27) = 1;
          goto LABEL_6;
        }
        if ( (a9 & 0x20) != 0 )
        {
          LODWORD(v27) = 5;
          goto LABEL_5;
        }
        v20 = -2146893815;
        DebugTraceError(2148073481LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c", 384);
LABEL_22:
        if ( v20 )
        {
          Pointer = v20;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (unsigned int)&WPP_GLOBAL_Control,
              v13,
              (unsigned int)"Status",
              v20,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
              91);
          goto LABEL_15;
        }
        v9 = a4;
LABEL_6:
        if ( !(unsigned __int8)IsGetMessageWPresent() || !(unsigned int)IsKeyProtected(a1, a2) )
        {
          if ( a2 )
            v15 = *a2;
          else
            v15 = 0;
          if ( a1 )
            v16 = *a1;
          else
            v16 = 0;
          v30.Simple = 0;
          v17.Pointer = NdrClientCall3(
                          (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                          0x14u,
                          0,
                          g_RpcBindingContext,
                          qword_18007A5E0,
                          v16,
                          v15,
                          v14,
                          v9,
                          a5,
                          a6,
                          a7,
                          a8,
                          a9).Pointer;
          Pointer = (DWORD)v17.Pointer;
          v30.Pointer = v17.Pointer;
          v28 = (int)v17.Pointer;
          if ( SLODWORD(v17.Simple) < 0 )
            DebugTraceError(
              LODWORD(v17.Pointer),
              "Status",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
              2897);
          goto LABEL_15;
        }
        memset_0(pv, 0, 0x98u);
        pv[0] = g_RpcBindingContext;
        pv[1] = qword_18007A5E0;
        if ( a1 )
          v32 = *a1;
        else
          v32 = 0;
        if ( a2 )
          v33 = *a2;
        else
          v33 = 0;
        v34 = v14;
        v35 = v9;
        v36 = a5;
        v37 = a6;
        v38 = a7;
        v39 = a8;
        v40 = a9;
        p_hObject = &hObject;
        if ( NtCurrentTeb()->IsImpersonating )
        {
          CurrentThread = GetCurrentThread();
          if ( !OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
          {
            LastError = GetLastError();
            v25 = 2859;
            goto LABEL_48;
          }
          v42 = TokenHandle;
        }
        if ( TrySubmitThreadpoolCallback(CliThreadCryptSignHashCallback, pv, 0) )
        {
          LastError = CliWaitForCallBackCompletion(hObject, pv);
          Pointer = LastError;
          if ( LastError >= 0 )
            goto LABEL_15;
          v25 = 2876;
LABEL_49:
          DebugTraceError(
            (unsigned int)LastError,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
            v25);
LABEL_15:
          if ( hObject )
          {
            CloseHandle(hObject);
            hObject = 0;
          }
          if ( TokenHandle )
            CloseHandle(TokenHandle);
          return Pointer;
        }
        LastError = GetLastError();
        v25 = 2869;
LABEL_48:
        Pointer = LastError;
        goto LABEL_49;
      }
      LODWORD(v27) = 4;
      *((_QWORD *)&v27 + 1) = a3;
    }
    else
    {
      v14 = 0;
    }
    v20 = 0;
    goto LABEL_22;
  }
  v21 = GetLastError();
  Pointer = v21;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (unsigned int)&WPP_GLOBAL_Control,
      v22,
      (unsigned int)"Status",
      v21,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
      252);
  return Pointer;
}

```

## disassembly

```asm
0x180001fd0  mov     [rsp+arg_18], r9
0x180001fd5  push    rbx
0x180001fd6  push    rsi
0x180001fd7  push    r12
0x180001fd9  push    r13
0x180001fdb  push    r14
0x180001fdd  push    r15
0x180001fdf  sub     rsp, 148h
0x180001fe6  mov     r14, r9
0x180001fe9  mov     rsi, r8
0x180001fec  mov     r15, rdx
0x180001fef  mov     r12, rcx
0x180001ff2  xor     eax, eax
0x180001ff4  mov     qword ptr [rsp+178h+var_100+4], rax
0x180001ff9  mov     qword ptr [rsp+178h+var_100], rax
0x180001ffe  mov     [rsp+178h+hObject], rax
0x180002003  mov     [rsp+178h+TokenHandle], rax
0x18000200b  xor     r9d, r9d; lpName
0x18000200e  xor     r8d, r8d; bInitialState
0x180002011  xor     edx, edx; bManualReset
0x180002013  xor     ecx, ecx; lpEventAttributes
0x180002015  call    cs:__imp_CreateEventW
0x18000201c  nop     dword ptr [rax+rax+00h]
0x180002021  mov     [rsp+178h+hObject], rax
0x180002026  test    rax, rax
0x180002029  jz      loc_180002275
0x18000202f  mov     ebx, [rsp+178h+arg_40]
0x180002036  test    rsi, rsi
0x180002039  jz      loc_1800021B3
0x18000203f  lea     r13, [rsp+178h+var_100]
0x180002044  xorps   xmm0, xmm0
0x180002047  movups  [rsp+178h+var_100], xmm0
0x18000204c  test    bl, 2
0x18000204f  jz      loc_1800022EB
0x180002055  mov     dword ptr [rsp+178h+var_100], 2
0x18000205d  mov     qword ptr [rsp+178h+var_100+8], rsi
0x180002065  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000206c  call    IsGetMessageWPresent
0x180002071  test    al, al
0x180002073  jnz     loc_180002215
0x180002079  test    r15, r15
0x18000207c  jz      loc_180002149
0x180002082  mov     r8, [r15]
0x180002085  test    r12, r12
0x180002088  jz      loc_180002142
0x18000208e  mov     rdx, [r12]
0x180002092  mov     rcx, cs:qword_18007A5E0
0x180002099  mov     [rsp+178h+var_E0], 0
0x1800020a5  mov     [rsp+178h+var_110], ebx
0x1800020a9  mov     rax, [rsp+178h+arg_38]
0x1800020b1  mov     [rsp+178h+var_118], rax
0x1800020b6  mov     eax, [rsp+178h+arg_30]
0x1800020bd  mov     [rsp+178h+var_120], eax
0x1800020c1  mov     rax, [rsp+178h+arg_28]
0x1800020c9  mov     [rsp+178h+var_128], rax
0x1800020ce  mov     eax, [rsp+178h+arg_20]
0x1800020d5  mov     [rsp+178h+var_130], eax
0x1800020d9  mov     [rsp+178h+var_138], r14
0x1800020de  mov     [rsp+178h+var_140], r13
0x1800020e3  mov     [rsp+178h+var_148], r8
0x1800020e8  mov     [rsp+178h+var_150], rdx
0x1800020ed  mov     [rsp+178h+var_158], rcx
0x1800020f2  mov     r9, cs:g_RpcBindingContext
0x1800020f9  xor     r8d, r8d; pReturnValue
0x1800020fc  lea     edx, [r8+14h]; nProcNum
0x180002100  lea     rcx, pProxyInfo; pProxyInfo
0x180002107  call    cs:__imp_NdrClientCall3
0x18000210e  nop     dword ptr [rax+rax+00h]
0x180002113  mov     rbx, rax
0x180002116  mov     [rsp+178h+var_E0], rax
0x18000211e  mov     [rsp+178h+var_F0], eax
0x180002125  test    eax, eax
0x180002127  jns     short loc_180002151
0x180002129  mov     r9d, 0B51h
0x18000212f  mov     r8, rsi
0x180002132  lea     rdx, aStatus; "Status"
0x180002139  mov     ecx, eax
0x18000213b  call    DebugTraceError
0x180002140  jmp     short loc_180002151
0x180002142  xor     edx, edx
0x180002144  jmp     loc_180002092
0x180002149  xor     r8d, r8d
0x18000214c  jmp     loc_180002085
0x180002151  jmp     short loc_18000217F
0x180002153  mov     ecx, eax
0x180002155  call    HResultFromRpcException
0x18000215a  mov     ebx, eax
0x18000215c  mov     [rsp+178h+var_F0], eax
0x180002163  mov     r9d, 0B55h
0x180002169  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002170  lea     rdx, aStatus; "Status"
0x180002177  mov     ecx, eax
0x180002179  call    DebugTraceError
0x18000217e  nop
0x18000217f  mov     rcx, [rsp+178h+hObject]; hObject
0x180002184  test    rcx, rcx
0x180002187  jnz     loc_1800022D1
0x18000218d  mov     rcx, [rsp+178h+TokenHandle]; hObject
0x180002195  test    rcx, rcx
0x180002198  jnz     loc_1800024B5
0x18000219e  mov     eax, ebx
0x1800021a0  add     rsp, 148h
0x1800021a7  pop     r15
0x1800021a9  pop     r14
0x1800021ab  pop     r13
0x1800021ad  pop     r12
0x1800021af  pop     rsi
0x1800021b0  pop     rbx
0x1800021b1  retn
0x1800021b3  xor     r13d, r13d
0x1800021b6  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800021bd  xor     r14d, r14d
0x1800021c0  test    r14d, r14d
0x1800021c3  jnz     short loc_1800021D2
0x1800021c5  mov     r14, [rsp+178h+arg_18]
0x1800021cd  jmp     loc_18000206C
0x1800021d2  mov     ebx, r14d
0x1800021d5  lea     rdx, WPP_GLOBAL_Control
0x1800021dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800021e3  cmp     rcx, rdx
0x1800021e6  jz      short loc_18000217F
0x1800021e8  test    byte ptr [rcx+1Ch], 1
0x1800021ec  jz      short loc_18000217F
0x1800021ee  mov     dword ptr [rsp+178h+var_148], 0B5Bh
0x1800021f6  mov     [rsp+178h+var_150], rsi
0x1800021fb  mov     dword ptr [rsp+178h+var_158], r14d
0x180002200  lea     r9, aStatus; "Status"
0x180002207  mov     rcx, [rcx+10h]
0x18000220b  call    WPP_SF_sDsd
0x180002210  jmp     loc_18000217F
0x180002215  mov     rdx, r15
0x180002218  mov     rcx, r12
0x18000221b  call    IsKeyProtected
0x180002220  test    eax, eax
0x180002222  jz      loc_180002079
0x180002228  xor     edx, edx; Val
0x18000222a  mov     r8d, 98h; Size
0x180002230  lea     rcx, [rsp+178h+pv]; void *
0x180002238  call    memset_0
0x18000223d  mov     rax, cs:g_RpcBindingContext
0x180002244  mov     [rsp+178h+pv], rax
0x18000224c  mov     rax, cs:qword_18007A5E0
0x180002253  mov     [rsp+178h+var_D0], rax
0x18000225b  test    r12, r12
0x18000225e  jz      loc_180002355
0x180002264  mov     rax, [r12]
0x180002268  mov     [rsp+178h+var_C8], rax
0x180002270  jmp     loc_180002361
0x180002275  call    cs:__imp_GetLastError
0x18000227c  nop     dword ptr [rax+rax+00h]
0x180002281  mov     ebx, eax
0x180002283  lea     rdx, WPP_GLOBAL_Control
0x18000228a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002291  cmp     rcx, rdx
0x180002294  jz      loc_18000219E
0x18000229a  test    byte ptr [rcx+1Ch], 1
0x18000229e  jz      loc_18000219E
0x1800022a4  mov     dword ptr [rsp+178h+var_148], 0AFCh
0x1800022ac  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800022b3  mov     [rsp+178h+var_150], rsi
0x1800022b8  mov     dword ptr [rsp+178h+var_158], eax
0x1800022bc  lea     r9, aStatus; "Status"
0x1800022c3  mov     rcx, [rcx+10h]
0x1800022c7  call    WPP_SF_sDsd
0x1800022cc  jmp     loc_18000219E
0x1800022d1  call    cs:__imp_CloseHandle
0x1800022d8  nop     dword ptr [rax+rax+00h]
0x1800022dd  mov     [rsp+178h+hObject], 0
0x1800022e6  jmp     loc_18000218D
0x1800022eb  test    bl, 0Ch
0x1800022ee  jnz     short loc_180002340
0x1800022f0  test    bl, 1
0x1800022f3  jz      short loc_180002302
0x1800022f5  mov     dword ptr [rsp+178h+var_100], 1
0x1800022fd  jmp     loc_180002065
0x180002302  test    bl, 20h
0x180002305  jz      short loc_180002314
0x180002307  mov     dword ptr [rsp+178h+var_100], 5
0x18000230f  jmp     loc_18000205D
0x180002314  mov     r14d, 80090009h
0x18000231a  mov     r9d, 180h
0x180002320  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002327  mov     r8, rsi
0x18000232a  lea     rdx, aStatus; "Status"
0x180002331  mov     ecx, 80090009h
0x180002336  call    DebugTraceError
0x18000233b  jmp     loc_1800021C0
0x180002340  mov     dword ptr [rsp+178h+var_100], 4
0x180002348  mov     qword ptr [rsp+178h+var_100+8], rsi
0x180002350  jmp     loc_1800021B6
0x180002355  mov     [rsp+178h+var_C8], 0
0x180002361  test    r15, r15
0x180002364  jz      short loc_180002373
0x180002366  mov     rax, [r15]
0x180002369  mov     [rsp+178h+var_C0], rax
0x180002371  jmp     short loc_18000237F
0x180002373  mov     [rsp+178h+var_C0], 0
0x18000237f  mov     [rsp+178h+var_B0], r13
0x180002387  mov     [rsp+178h+var_A8], r14
0x18000238f  mov     eax, [rsp+178h+arg_20]
0x180002396  mov     [rsp+178h+var_A0], eax
0x18000239d  mov     rax, [rsp+178h+arg_28]
0x1800023a5  mov     [rsp+178h+var_90], rax
0x1800023ad  mov     eax, [rsp+178h+arg_30]
0x1800023b4  mov     [rsp+178h+var_88], eax
0x1800023bb  mov     rax, [rsp+178h+arg_38]
0x1800023c3  mov     [rsp+178h+var_80], rax
0x1800023cb  mov     [rsp+178h+var_78], ebx
0x1800023d2  lea     rax, [rsp+178h+hObject]
0x1800023d7  mov     [rsp+178h+var_70], rax
0x1800023df  mov     eax, gs:179Ch
0x1800023e7  test    eax, eax
0x1800023e9  jz      loc_180002475
0x1800023ef  call    cs:__imp_GetCurrentThread
0x1800023f6  nop     dword ptr [rax+rax+00h]
0x1800023fb  mov     rcx, rax; ThreadHandle
0x1800023fe  lea     r9, [rsp+178h+TokenHandle]; TokenHandle
0x180002406  mov     edx, 0Ch; DesiredAccess
0x18000240b  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x18000240f  call    cs:__imp_OpenThreadToken
0x180002416  nop     dword ptr [rax+rax+00h]
0x18000241b  test    eax, eax
0x18000241d  jnz     short loc_180002465
0x18000241f  call    cs:__imp_GetLastError
0x180002426  nop     dword ptr [rax+rax+00h]
0x18000242b  mov     r9d, 0B2Bh
0x180002431  jmp     short loc_180002445
0x180002433  call    cs:__imp_GetLastError
0x18000243a  nop     dword ptr [rax+rax+00h]
0x18000243f  mov     r9d, 0B35h
0x180002445  mov     ebx, eax
0x180002447  jmp     short loc_18000244F
0x180002449  mov     r9d, 0B3Ch
0x18000244f  mov     r8, rsi
0x180002452  lea     rdx, aStatus; "Status"
0x180002459  mov     ecx, eax
0x18000245b  call    DebugTraceError
0x180002460  jmp     loc_18000217F
0x180002465  mov     rax, [rsp+178h+TokenHandle]
0x18000246d  mov     [rsp+178h+var_68], rax
0x180002475  xor     r8d, r8d; pcbe
0x180002478  lea     rdx, [rsp+178h+pv]; pv
0x180002480  lea     rcx, _CliThreadCryptSignHashCallback; pfns
0x180002487  call    cs:__imp_TrySubmitThreadpoolCallback
0x18000248e  nop     dword ptr [rax+rax+00h]
0x180002493  test    eax, eax
0x180002495  jz      short loc_180002433
0x180002497  lea     rdx, [rsp+178h+pv]
0x18000249f  mov     rcx, [rsp+178h+hObject]
0x1800024a4  call    _CliWaitForCallBackCompletion
0x1800024a9  mov     ebx, eax
0x1800024ab  test    eax, eax
0x1800024ad  jns     loc_18000217F
0x1800024b3  jmp     short loc_180002449
0x1800024b5  call    cs:__imp_CloseHandle
0x1800024bc  nop     dword ptr [rax+rax+00h]
0x1800024c1  jmp     loc_18000219E
0x180062452  push    rbp
0x180062454  sub     rsp, 70h
0x180062458  mov     rbp, rdx
0x18006245b  mov     rcx, [rcx]
0x18006245e  mov     ecx, [rcx]; ExceptionCode
0x180062460  call    cs:__imp_I_RpcExceptionFilter
0x180062467  nop     dword ptr [rax+rax+00h]
0x18006246c  nop
0x18006246d  add     rsp, 70h
0x180062471  pop     rbp
0x180062472  retn
```
