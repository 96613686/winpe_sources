# CliCryptFinalizeKey

- ea: `0x1800233f0`
- end: `0x180023685`
- name: `CliCryptFinalizeKey`
- size: `661`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002da4`
- `0x180002f8c`
- `0x18000af80`
- `0x1800233f0`
- `0x18002368c`
- `0x180038970`
- `0x18003948c`
- `0x180060f5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023448`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023529`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023583`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023448`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023529`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023583`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180023519`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180023519`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800234fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800234fc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002342f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002342f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002364b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023669`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002364b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023669`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180023573`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180023573`
- `RPCRT4!I_RpcExceptionFilter` at `0x18006296a`
- `RPCRT4!I_RpcExceptionFilter` at `0x18006296a`

## string_xrefs

- `0x18002345c`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x18002353d`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x1800235fd`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x180023627`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`

## pseudocode

```c
__int64 __fastcall CliCryptFinalizeKey(__int64 *a1, __int64 *a2, int a3)
{
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  signed int v9; // eax
  __int64 v10; // r9
  unsigned int v11; // edi
  __int64 v12; // r9
  __int64 v13; // r8
  int v14; // eax
  void *TokenHandle; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD pv[2]; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v17; // [rsp+50h] [rbp-B8h]
  __int64 v18; // [rsp+58h] [rbp-B0h]
  int v19; // [rsp+A0h] [rbp-68h]
  HANDLE *p_hObject; // [rsp+A8h] [rbp-60h]
  void *v21; // [rsp+B0h] [rbp-58h]
  HANDLE hObject; // [rsp+128h] [rbp+20h] BYREF

  hObject = 0;
  memset_0(pv, 0, 0x98u);
  TokenHandle = 0;
  hObject = CreateEventW(0, 0, 0, 0);
  if ( !hObject )
  {
    LastError = GetLastError();
    DebugTraceError(LastError, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c", 1795);
    return LastError;
  }
  if ( !(unsigned __int8)IsGetMessageWPresent() || !(unsigned int)IsKeyProtected(a1, a2) )
  {
    if ( a2 )
      v12 = *a2;
    else
      LODWORD(v12) = 0;
    if ( a1 )
      v13 = *a1;
    else
      LODWORD(v13) = 0;
    v14 = c_SrvRpcCryptFinalizeKey((_DWORD)g_RpcBindingContext, qword_18007A5E0, v13, v12, a3);
    v11 = v14;
    if ( v14 < 0 )
      DebugTraceError(
        (unsigned int)v14,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
        1858);
    goto LABEL_29;
  }
  pv[0] = g_RpcBindingContext;
  pv[1] = qword_18007A5E0;
  if ( a1 )
    v17 = *a1;
  else
    v17 = 0;
  if ( a2 )
    v18 = *a2;
  else
    v18 = 0;
  v19 = a3;
  p_hObject = &hObject;
  if ( NtCurrentTeb()->IsImpersonating )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
    {
      v9 = GetLastError();
      v10 = 1827;
LABEL_14:
      v11 = v9;
      goto LABEL_15;
    }
    v21 = TokenHandle;
  }
  if ( !TrySubmitThreadpoolCallback(CliThreadCryptFinalizeKeyCallback, pv, 0) )
  {
    v9 = GetLastError();
    v10 = 1837;
    goto LABEL_14;
  }
  v9 = CliWaitForCallBackCompletion(hObject, pv);
  v11 = v9;
  if ( v9 >= 0 )
    goto LABEL_29;
  v10 = 1844;
LABEL_15:
  DebugTraceError((unsigned int)v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c", v10);
LABEL_29:
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v11;
}

```

## disassembly

```asm
0x1800233f0  mov     rax, rsp
0x1800233f3  push    rbx
0x1800233f4  push    rsi
0x1800233f5  push    rdi
0x1800233f6  push    r14
0x1800233f8  sub     rsp, 0E8h
0x1800233ff  mov     r14d, r8d
0x180023402  mov     rdi, rdx
0x180023405  mov     rsi, rcx
0x180023408  xor     ebx, ebx
0x18002340a  mov     [rax+20h], rbx
0x18002340e  xor     edx, edx; Val
0x180023410  mov     r8d, 98h; Size
0x180023416  lea     rcx, [rsp+108h+pv]; void *
0x18002341b  call    memset_0
0x180023420  mov     [rsp+108h+TokenHandle], rbx
0x180023425  xor     r9d, r9d; lpName
0x180023428  xor     r8d, r8d; bInitialState
0x18002342b  xor     edx, edx; bManualReset
0x18002342d  xor     ecx, ecx; lpEventAttributes
0x18002342f  call    cs:__imp_CreateEventW
0x180023436  nop     dword ptr [rax+rax+00h]
0x18002343b  mov     [rsp+108h+hObject], rax
0x180023443  test    rax, rax
0x180023446  jnz     short loc_180023478
0x180023448  call    cs:__imp_GetLastError
0x18002344f  nop     dword ptr [rax+rax+00h]
0x180023454  mov     ebx, eax
0x180023456  mov     r9d, 703h
0x18002345c  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180023463  lea     rdx, aStatus; "Status"
0x18002346a  mov     ecx, eax
0x18002346c  call    DebugTraceError
0x180023471  mov     eax, ebx
0x180023473  jmp     loc_180023677
0x180023478  call    IsGetMessageWPresent
0x18002347d  test    al, al
0x18002347f  jz      loc_1800235BB
0x180023485  mov     rdx, rdi
0x180023488  mov     rcx, rsi
0x18002348b  call    IsKeyProtected
0x180023490  test    eax, eax
0x180023492  jz      loc_1800235BB
0x180023498  mov     rax, cs:g_RpcBindingContext
0x18002349f  mov     [rsp+108h+pv], rax
0x1800234a4  mov     rax, cs:qword_18007A5E0
0x1800234ab  mov     [rsp+108h+var_C0], rax
0x1800234b0  test    rsi, rsi
0x1800234b3  jz      short loc_1800234BF
0x1800234b5  mov     rax, [rsi]
0x1800234b8  mov     [rsp+108h+var_B8], rax
0x1800234bd  jmp     short loc_1800234C4
0x1800234bf  mov     [rsp+108h+var_B8], rbx
0x1800234c4  test    rdi, rdi
0x1800234c7  jz      short loc_1800234D3
0x1800234c9  mov     rax, [rdi]
0x1800234cc  mov     [rsp+108h+var_B0], rax
0x1800234d1  jmp     short loc_1800234D8
0x1800234d3  mov     [rsp+108h+var_B0], rbx
0x1800234d8  mov     [rsp+108h+var_68], r14d
0x1800234e0  lea     rax, [rsp+108h+hObject]
0x1800234e8  mov     [rsp+108h+var_60], rax
0x1800234f0  mov     eax, gs:179Ch
0x1800234f8  test    eax, eax
0x1800234fa  jz      short loc_180023564
0x1800234fc  call    cs:__imp_GetCurrentThread
0x180023503  nop     dword ptr [rax+rax+00h]
0x180023508  mov     rcx, rax; ThreadHandle
0x18002350b  lea     r9, [rsp+108h+TokenHandle]; TokenHandle
0x180023510  mov     edx, 0Ch; DesiredAccess
0x180023515  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x180023519  call    cs:__imp_OpenThreadToken
0x180023520  nop     dword ptr [rax+rax+00h]
0x180023525  test    eax, eax
0x180023527  jnz     short loc_180023557
0x180023529  call    cs:__imp_GetLastError
0x180023530  nop     dword ptr [rax+rax+00h]
0x180023535  mov     r9d, 723h
0x18002353b  mov     edi, eax
0x18002353d  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180023544  lea     rdx, aStatus; "Status"
0x18002354b  mov     ecx, eax
0x18002354d  call    DebugTraceError
0x180023552  jmp     loc_18002363E
0x180023557  mov     rax, [rsp+108h+TokenHandle]
0x18002355c  mov     [rsp+108h+var_58], rax
0x180023564  xor     r8d, r8d; pcbe
0x180023567  lea     rdx, [rsp+108h+pv]; pv
0x18002356c  lea     rcx, _CliThreadCryptFinalizeKeyCallback; pfns
0x180023573  call    cs:__imp_TrySubmitThreadpoolCallback
0x18002357a  nop     dword ptr [rax+rax+00h]
0x18002357f  test    eax, eax
0x180023581  jnz     short loc_180023597
0x180023583  call    cs:__imp_GetLastError
0x18002358a  nop     dword ptr [rax+rax+00h]
0x18002358f  mov     r9d, 72Dh
0x180023595  jmp     short loc_18002353B
0x180023597  lea     rdx, [rsp+108h+pv]
0x18002359c  mov     rcx, [rsp+108h+hObject]
0x1800235a4  call    _CliWaitForCallBackCompletion
0x1800235a9  mov     edi, eax
0x1800235ab  test    eax, eax
0x1800235ad  jns     loc_18002363E
0x1800235b3  mov     r9d, 734h
0x1800235b9  jmp     short loc_18002353D
0x1800235bb  test    rdi, rdi
0x1800235be  jz      short loc_1800235C5
0x1800235c0  mov     r9, [rdi]
0x1800235c3  jmp     short loc_1800235C8
0x1800235c5  mov     r9, rbx
0x1800235c8  test    rsi, rsi
0x1800235cb  jz      short loc_1800235D2
0x1800235cd  mov     r8, [rsi]
0x1800235d0  jmp     short loc_1800235D5
0x1800235d2  mov     r8, rbx
0x1800235d5  mov     [rsp+108h+var_E8], r14d
0x1800235da  mov     rdx, cs:qword_18007A5E0
0x1800235e1  mov     rcx, cs:g_RpcBindingContext
0x1800235e8  call    c_SrvRpcCryptFinalizeKey
0x1800235ed  mov     edi, eax
0x1800235ef  mov     [rsp+108h+var_D8], eax
0x1800235f3  test    eax, eax
0x1800235f5  jns     short loc_180023612
0x1800235f7  mov     r9d, 742h
0x1800235fd  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180023604  lea     rdx, aStatus; "Status"
0x18002360b  mov     ecx, eax
0x18002360d  call    DebugTraceError
0x180023612  jmp     short loc_18002363E
0x180023614  mov     ecx, eax
0x180023616  call    HResultFromRpcException
0x18002361b  mov     edi, eax
0x18002361d  mov     [rsp+108h+var_D8], eax
0x180023621  mov     r9d, 746h
0x180023627  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002362e  lea     rdx, aStatus; "Status"
0x180023635  mov     ecx, eax
0x180023637  call    DebugTraceError
0x18002363c  xor     ebx, ebx
0x18002363e  mov     rcx, [rsp+108h+hObject]; hObject
0x180023646  test    rcx, rcx
0x180023649  jz      short loc_18002365F
0x18002364b  call    cs:__imp_CloseHandle
0x180023652  nop     dword ptr [rax+rax+00h]
0x180023657  mov     [rsp+108h+hObject], rbx
0x18002365f  mov     rcx, [rsp+108h+TokenHandle]; hObject
0x180023664  test    rcx, rcx
0x180023667  jz      short loc_180023675
0x180023669  call    cs:__imp_CloseHandle
0x180023670  nop     dword ptr [rax+rax+00h]
0x180023675  mov     eax, edi
0x180023677  add     rsp, 0E8h
0x18002367e  pop     r14
0x180023680  pop     rdi
0x180023681  pop     rsi
0x180023682  pop     rbx
0x180023683  retn
0x18006295c  push    rbp
0x18006295e  sub     rsp, 30h
0x180062962  mov     rbp, rdx
0x180062965  mov     rcx, [rcx]
0x180062968  mov     ecx, [rcx]; ExceptionCode
0x18006296a  call    cs:__imp_I_RpcExceptionFilter
0x180062971  nop     dword ptr [rax+rax+00h]
0x180062976  nop
0x180062977  add     rsp, 30h
0x18006297b  pop     rbp
0x18006297c  retn
```
