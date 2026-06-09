# _CliThreadCryptFinalizeKeyCallback

- ea: `0x180045420`
- end: `0x180045570`
- name: `_CliThreadCryptFinalizeKeyCallback`
- size: `336`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000af80`
- `0x18002368c`
- `0x180045420`
- `0x180060f5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045464`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045520`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045464`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045520`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180045454`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180045454`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180045553`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180045553`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x18004543d`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x18004543d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180045510`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180045510`
- `RPCRT4!I_RpcExceptionFilter` at `0x180062ba6`
- `RPCRT4!I_RpcExceptionFilter` at `0x180062ba6`

## string_xrefs

- `0x180045478`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x1800454c2`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x1800454eb`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x180045534`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`

## pseudocode

```c
void __fastcall CliThreadCryptFinalizeKeyCallback(PTP_CALLBACK_INSTANCE Instance, PVOID Context)
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
      DebugTraceError(LastError, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c", 1740);
      *((_DWORD *)Context + 25) = LastError;
    }
  }
  v6 = c_SrvRpcCryptFinalizeKey(
         *(_QWORD *)Context,
         *((_QWORD *)Context + 1),
         *((_QWORD *)Context + 2),
         *((_QWORD *)Context + 3),
         *((_DWORD *)Context + 24));
  v7 = v6;
  if ( v6 < 0 )
  {
    DebugTraceError((unsigned int)v6, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c", 1758);
    *((_DWORD *)Context + 25) = v7;
  }
  if ( v3 && !RevertToSelf() )
  {
    v8 = GetLastError();
    DebugTraceError(v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c", 1770);
    *((_DWORD *)Context + 25) = v8;
  }
  SetEvent(**((HANDLE **)Context + 13));
}

```

## disassembly

```asm
0x180045420  mov     [rsp+arg_0], rbx
0x180045425  mov     [rsp+arg_18], rsi
0x18004542a  mov     [rsp+arg_8], rdx
0x18004542f  push    rdi
0x180045430  sub     rsp, 30h
0x180045434  mov     rdi, rdx
0x180045437  xor     esi, esi
0x180045439  mov     [rsp+38h+arg_10], esi
0x18004543d  call    cs:__imp_CallbackMayRunLong
0x180045444  nop     dword ptr [rax+rax+00h]
0x180045449  mov     rdx, [rdi+70h]; Token
0x18004544d  test    rdx, rdx
0x180045450  jz      short loc_18004549B
0x180045452  xor     ecx, ecx; Thread
0x180045454  call    cs:__imp_SetThreadToken
0x18004545b  nop     dword ptr [rax+rax+00h]
0x180045460  test    eax, eax
0x180045462  jnz     short loc_180045492
0x180045464  call    cs:__imp_GetLastError
0x18004546b  nop     dword ptr [rax+rax+00h]
0x180045470  mov     ebx, eax
0x180045472  mov     r9d, 6CCh
0x180045478  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004547f  lea     rdx, aStatus; "Status"
0x180045486  mov     ecx, eax
0x180045488  call    DebugTraceError
0x18004548d  mov     [rdi+64h], ebx
0x180045490  jmp     short loc_18004549B
0x180045492  mov     esi, 1
0x180045497  mov     [rsp+38h+arg_10], esi
0x18004549b  mov     eax, [rdi+60h]
0x18004549e  mov     [rsp+38h+var_18], eax
0x1800454a2  mov     r9, [rdi+18h]
0x1800454a6  mov     r8, [rdi+10h]
0x1800454aa  mov     rdx, [rdi+8]
0x1800454ae  mov     rcx, [rdi]
0x1800454b1  call    c_SrvRpcCryptFinalizeKey
0x1800454b6  mov     ebx, eax
0x1800454b8  test    eax, eax
0x1800454ba  jns     short loc_1800454DA
0x1800454bc  mov     r9d, 6DEh
0x1800454c2  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800454c9  lea     rdx, aStatus; "Status"
0x1800454d0  mov     ecx, eax
0x1800454d2  call    DebugTraceError
0x1800454d7  mov     [rdi+64h], ebx
0x1800454da  jmp     short loc_18004550C
0x1800454dc  mov     ecx, eax
0x1800454de  call    HResultFromRpcException
0x1800454e3  mov     ebx, eax
0x1800454e5  mov     r9d, 6E3h
0x1800454eb  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800454f2  lea     rdx, aStatus; "Status"
0x1800454f9  mov     ecx, eax
0x1800454fb  call    DebugTraceError
0x180045500  mov     rdi, [rsp+38h+arg_8]
0x180045505  mov     [rdi+64h], ebx
0x180045508  mov     esi, [rsp+38h+arg_10]
0x18004550c  test    esi, esi
0x18004550e  jz      short loc_18004554C
0x180045510  call    cs:__imp_RevertToSelf
0x180045517  nop     dword ptr [rax+rax+00h]
0x18004551c  test    eax, eax
0x18004551e  jnz     short loc_18004554C
0x180045520  call    cs:__imp_GetLastError
0x180045527  nop     dword ptr [rax+rax+00h]
0x18004552c  mov     ebx, eax
0x18004552e  mov     r9d, 6EAh
0x180045534  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004553b  lea     rdx, aStatus; "Status"
0x180045542  mov     ecx, eax
0x180045544  call    DebugTraceError
0x180045549  mov     [rdi+64h], ebx
0x18004554c  mov     rcx, [rdi+68h]
0x180045550  mov     rcx, [rcx]; hEvent
0x180045553  call    cs:__imp_SetEvent
0x18004555a  nop     dword ptr [rax+rax+00h]
0x18004555f  mov     rbx, [rsp+38h+arg_0]
0x180045564  mov     rsi, [rsp+38h+arg_18]
0x180045569  add     rsp, 30h
0x18004556d  pop     rdi
0x18004556e  retn
0x180062b98  push    rbp
0x180062b9a  sub     rsp, 30h
0x180062b9e  mov     rbp, rdx
0x180062ba1  mov     rcx, [rcx]
0x180062ba4  mov     ecx, [rcx]; ExceptionCode
0x180062ba6  call    cs:__imp_I_RpcExceptionFilter
0x180062bad  nop     dword ptr [rax+rax+00h]
0x180062bb2  nop
0x180062bb3  add     rsp, 30h
0x180062bb7  pop     rbp
0x180062bb8  retn
```
