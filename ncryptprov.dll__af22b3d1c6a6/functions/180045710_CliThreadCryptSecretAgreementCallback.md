# _CliThreadCryptSecretAgreementCallback

- ea: `0x180045710`
- end: `0x180045872`
- name: `_CliThreadCryptSecretAgreementCallback`
- size: `354`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000af80`
- `0x180045710`
- `0x180045c44`
- `0x180060f5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045754`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045822`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045754`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045822`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180045744`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180045744`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180045855`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180045855`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x18004572d`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x18004572d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180045812`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180045812`
- `RPCRT4!I_RpcExceptionFilter` at `0x180062c46`
- `RPCRT4!I_RpcExceptionFilter` at `0x180062c46`

## string_xrefs

- `0x180045768`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x1800457c4`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x1800457ed`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x180045836`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`

## pseudocode

```c
void __fastcall CliThreadCryptSecretAgreementCallback(PTP_CALLBACK_INSTANCE Instance, PVOID Context)
{
  int v3; // esi
  void *v4; // rdx
  DWORD LastError; // ebx
  int v6; // eax
  int v7; // ebx
  DWORD v8; // ebx

  v3 = 0;
  CallbackMayRunLong(Instance);
  v4 = (void *)*((_QWORD *)Context + 14);
  if ( v4 )
  {
    if ( SetThreadToken(0, v4) )
    {
      v3 = 1;
    }
    else
    {
      LastError = GetLastError();
      DebugTraceError(LastError, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c", 2466);
      *((_DWORD *)Context + 25) = LastError;
    }
  }
  v6 = c_SrvRpcCryptSecretAgreement(
         *(_QWORD *)Context,
         *((_QWORD *)Context + 1),
         *((_QWORD *)Context + 2),
         *((_QWORD *)Context + 3),
         *((_QWORD *)Context + 4),
         *((_QWORD *)Context + 15),
         *((_DWORD *)Context + 24));
  v7 = v6;
  if ( v6 < 0 )
  {
    DebugTraceError((unsigned int)v6, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c", 2486);
    *((_DWORD *)Context + 25) = v7;
  }
  if ( v3 && !RevertToSelf() )
  {
    v8 = GetLastError();
    DebugTraceError(v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c", 2498);
    *((_DWORD *)Context + 25) = v8;
  }
  SetEvent(**((HANDLE **)Context + 13));
}

```

## disassembly

```asm
0x180045710  mov     [rsp+arg_0], rbx
0x180045715  mov     [rsp+arg_18], rsi
0x18004571a  mov     [rsp+arg_8], rdx
0x18004571f  push    rdi
0x180045720  sub     rsp, 40h
0x180045724  mov     rdi, rdx
0x180045727  xor     esi, esi
0x180045729  mov     [rsp+48h+arg_10], esi
0x18004572d  call    cs:__imp_CallbackMayRunLong
0x180045734  nop     dword ptr [rax+rax+00h]
0x180045739  mov     rdx, [rdi+70h]; Token
0x18004573d  test    rdx, rdx
0x180045740  jz      short loc_18004578B
0x180045742  xor     ecx, ecx; Thread
0x180045744  call    cs:__imp_SetThreadToken
0x18004574b  nop     dword ptr [rax+rax+00h]
0x180045750  test    eax, eax
0x180045752  jnz     short loc_180045782
0x180045754  call    cs:__imp_GetLastError
0x18004575b  nop     dword ptr [rax+rax+00h]
0x180045760  mov     ebx, eax
0x180045762  mov     r9d, 9A2h
0x180045768  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004576f  lea     rdx, aStatus; "Status"
0x180045776  mov     ecx, eax
0x180045778  call    DebugTraceError
0x18004577d  mov     [rdi+64h], ebx
0x180045780  jmp     short loc_18004578B
0x180045782  mov     esi, 1
0x180045787  mov     [rsp+48h+arg_10], esi
0x18004578b  mov     eax, [rdi+60h]
0x18004578e  mov     [rsp+48h+var_18], eax
0x180045792  mov     rax, [rdi+78h]
0x180045796  mov     [rsp+48h+var_20], rax
0x18004579b  mov     rax, [rdi+20h]
0x18004579f  mov     [rsp+48h+var_28], rax
0x1800457a4  mov     r9, [rdi+18h]
0x1800457a8  mov     r8, [rdi+10h]
0x1800457ac  mov     rdx, [rdi+8]
0x1800457b0  mov     rcx, [rdi]
0x1800457b3  call    c_SrvRpcCryptSecretAgreement
0x1800457b8  mov     ebx, eax
0x1800457ba  test    eax, eax
0x1800457bc  jns     short loc_1800457DC
0x1800457be  mov     r9d, 9B6h
0x1800457c4  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800457cb  lea     rdx, aStatus; "Status"
0x1800457d2  mov     ecx, eax
0x1800457d4  call    DebugTraceError
0x1800457d9  mov     [rdi+64h], ebx
0x1800457dc  jmp     short loc_18004580E
0x1800457de  mov     ecx, eax
0x1800457e0  call    HResultFromRpcException
0x1800457e5  mov     ebx, eax
0x1800457e7  mov     r9d, 9BBh
0x1800457ed  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800457f4  lea     rdx, aStatus; "Status"
0x1800457fb  mov     ecx, eax
0x1800457fd  call    DebugTraceError
0x180045802  mov     rdi, [rsp+48h+arg_8]
0x180045807  mov     [rdi+64h], ebx
0x18004580a  mov     esi, [rsp+48h+arg_10]
0x18004580e  test    esi, esi
0x180045810  jz      short loc_18004584E
0x180045812  call    cs:__imp_RevertToSelf
0x180045819  nop     dword ptr [rax+rax+00h]
0x18004581e  test    eax, eax
0x180045820  jnz     short loc_18004584E
0x180045822  call    cs:__imp_GetLastError
0x180045829  nop     dword ptr [rax+rax+00h]
0x18004582e  mov     ebx, eax
0x180045830  mov     r9d, 9C2h
0x180045836  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004583d  lea     rdx, aStatus; "Status"
0x180045844  mov     ecx, eax
0x180045846  call    DebugTraceError
0x18004584b  mov     [rdi+64h], ebx
0x18004584e  mov     rcx, [rdi+68h]
0x180045852  mov     rcx, [rcx]; hEvent
0x180045855  call    cs:__imp_SetEvent
0x18004585c  nop     dword ptr [rax+rax+00h]
0x180045861  mov     rbx, [rsp+48h+arg_0]
0x180045866  mov     rsi, [rsp+48h+arg_18]
0x18004586b  add     rsp, 40h
0x18004586f  pop     rdi
0x180045870  retn
0x180062c38  push    rbp
0x180062c3a  sub     rsp, 40h
0x180062c3e  mov     rbp, rdx
0x180062c41  mov     rcx, [rcx]
0x180062c44  mov     ecx, [rcx]; ExceptionCode
0x180062c46  call    cs:__imp_I_RpcExceptionFilter
0x180062c4d  nop     dword ptr [rax+rax+00h]
0x180062c52  nop
0x180062c53  add     rsp, 40h
0x180062c57  pop     rbp
0x180062c58  retn
```
