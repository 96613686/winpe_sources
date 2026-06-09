# _CliThreadCryptKeyDerivationCallback

- ea: `0x180045580`
- end: `0x1800456fb`
- name: `_CliThreadCryptKeyDerivationCallback`
- size: `379`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000af80`
- `0x180035b28`
- `0x180045580`
- `0x180060f5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800455c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800456ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800455c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800456ab`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800455b4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800455b4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800456de`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800456de`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x18004559d`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x18004559d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004569b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004569b`
- `RPCRT4!I_RpcExceptionFilter` at `0x180062bce`
- `RPCRT4!I_RpcExceptionFilter` at `0x180062bce`

## string_xrefs

- `0x1800455d8`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x18004564d`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x180045676`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x1800456bf`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`

## pseudocode

```c
void __fastcall CliThreadCryptKeyDerivationCallback(PTP_CALLBACK_INSTANCE Instance, PVOID Context)
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
      DebugTraceError(LastError, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c", 3001);
      *((_DWORD *)Context + 25) = LastError;
    }
  }
  v6 = c_SrvRpcCryptKeyDerivation(
         *(_QWORD *)Context,
         *((_QWORD *)Context + 1),
         *((_QWORD *)Context + 2),
         *((_QWORD *)Context + 3),
         *((_QWORD *)Context + 16),
         *((_QWORD *)Context + 17),
         *((_DWORD *)Context + 36),
         *((_QWORD *)Context + 11),
         *((_DWORD *)Context + 24));
  v7 = v6;
  if ( v6 < 0 )
  {
    DebugTraceError((unsigned int)v6, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c", 3023);
    *((_DWORD *)Context + 25) = v7;
  }
  if ( v3 && !RevertToSelf() )
  {
    v8 = GetLastError();
    DebugTraceError(v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c", 3035);
    *((_DWORD *)Context + 25) = v8;
  }
  SetEvent(**((HANDLE **)Context + 13));
}

```

## disassembly

```asm
0x180045580  mov     [rsp+arg_0], rbx
0x180045585  mov     [rsp+arg_18], rsi
0x18004558a  mov     [rsp+arg_8], rdx
0x18004558f  push    rdi
0x180045590  sub     rsp, 50h
0x180045594  mov     rdi, rdx
0x180045597  xor     esi, esi
0x180045599  mov     [rsp+58h+arg_10], esi
0x18004559d  call    cs:__imp_CallbackMayRunLong
0x1800455a4  nop     dword ptr [rax+rax+00h]
0x1800455a9  mov     rdx, [rdi+70h]; Token
0x1800455ad  test    rdx, rdx
0x1800455b0  jz      short loc_1800455FB
0x1800455b2  xor     ecx, ecx; Thread
0x1800455b4  call    cs:__imp_SetThreadToken
0x1800455bb  nop     dword ptr [rax+rax+00h]
0x1800455c0  test    eax, eax
0x1800455c2  jnz     short loc_1800455F2
0x1800455c4  call    cs:__imp_GetLastError
0x1800455cb  nop     dword ptr [rax+rax+00h]
0x1800455d0  mov     ebx, eax
0x1800455d2  mov     r9d, 0BB9h
0x1800455d8  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800455df  lea     rdx, aStatus; "Status"
0x1800455e6  mov     ecx, eax
0x1800455e8  call    DebugTraceError
0x1800455ed  mov     [rdi+64h], ebx
0x1800455f0  jmp     short loc_1800455FB
0x1800455f2  mov     esi, 1
0x1800455f7  mov     [rsp+58h+arg_10], esi
0x1800455fb  mov     eax, [rdi+60h]
0x1800455fe  mov     [rsp+58h+var_18], eax
0x180045602  mov     rax, [rdi+58h]
0x180045606  mov     [rsp+58h+var_20], rax
0x18004560b  mov     eax, [rdi+90h]
0x180045611  mov     [rsp+58h+var_28], eax
0x180045615  mov     rax, [rdi+88h]
0x18004561c  mov     [rsp+58h+var_30], rax
0x180045621  mov     rax, [rdi+80h]
0x180045628  mov     [rsp+58h+var_38], rax
0x18004562d  mov     r9, [rdi+18h]
0x180045631  mov     r8, [rdi+10h]
0x180045635  mov     rdx, [rdi+8]
0x180045639  mov     rcx, [rdi]
0x18004563c  call    c_SrvRpcCryptKeyDerivation
0x180045641  mov     ebx, eax
0x180045643  test    eax, eax
0x180045645  jns     short loc_180045665
0x180045647  mov     r9d, 0BCFh
0x18004564d  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180045654  lea     rdx, aStatus; "Status"
0x18004565b  mov     ecx, eax
0x18004565d  call    DebugTraceError
0x180045662  mov     [rdi+64h], ebx
0x180045665  jmp     short loc_180045697
0x180045667  mov     ecx, eax
0x180045669  call    HResultFromRpcException
0x18004566e  mov     ebx, eax
0x180045670  mov     r9d, 0BD4h
0x180045676  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004567d  lea     rdx, aStatus; "Status"
0x180045684  mov     ecx, eax
0x180045686  call    DebugTraceError
0x18004568b  mov     rdi, [rsp+58h+arg_8]
0x180045690  mov     [rdi+64h], ebx
0x180045693  mov     esi, [rsp+58h+arg_10]
0x180045697  test    esi, esi
0x180045699  jz      short loc_1800456D7
0x18004569b  call    cs:__imp_RevertToSelf
0x1800456a2  nop     dword ptr [rax+rax+00h]
0x1800456a7  test    eax, eax
0x1800456a9  jnz     short loc_1800456D7
0x1800456ab  call    cs:__imp_GetLastError
0x1800456b2  nop     dword ptr [rax+rax+00h]
0x1800456b7  mov     ebx, eax
0x1800456b9  mov     r9d, 0BDBh
0x1800456bf  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800456c6  lea     rdx, aStatus; "Status"
0x1800456cd  mov     ecx, eax
0x1800456cf  call    DebugTraceError
0x1800456d4  mov     [rdi+64h], ebx
0x1800456d7  mov     rcx, [rdi+68h]
0x1800456db  mov     rcx, [rcx]; hEvent
0x1800456de  call    cs:__imp_SetEvent
0x1800456e5  nop     dword ptr [rax+rax+00h]
0x1800456ea  mov     rbx, [rsp+58h+arg_0]
0x1800456ef  mov     rsi, [rsp+58h+arg_18]
0x1800456f4  add     rsp, 50h
0x1800456f8  pop     rdi
0x1800456f9  retn
0x180062bc0  push    rbp
0x180062bc2  sub     rsp, 50h
0x180062bc6  mov     rbp, rdx
0x180062bc9  mov     rcx, [rcx]
0x180062bcc  mov     ecx, [rcx]; ExceptionCode
0x180062bce  call    cs:__imp_I_RpcExceptionFilter
0x180062bd5  nop     dword ptr [rax+rax+00h]
0x180062bda  nop
0x180062bdb  add     rsp, 50h
0x180062bdf  pop     rbp
0x180062be0  retn
```
