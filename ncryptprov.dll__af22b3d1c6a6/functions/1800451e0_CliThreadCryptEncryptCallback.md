# _CliThreadCryptEncryptCallback

- ea: `0x1800451e0`
- end: `0x18004540e`
- name: `_CliThreadCryptEncryptCallback`
- size: `558`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000af80`
- `0x18002469c`
- `0x1800451e0`
- `0x180045bb4`
- `0x180060f5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045224`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800453c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045224`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800453c3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180045214`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180045214`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800453f6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800453f6`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x1800451fd`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x1800451fd`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800453b3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800453b3`
- `RPCRT4!I_RpcExceptionFilter` at `0x180062cb6`
- `RPCRT4!I_RpcExceptionFilter` at `0x180062cd8`
- `RPCRT4!I_RpcExceptionFilter` at `0x180062cb6`
- `RPCRT4!I_RpcExceptionFilter` at `0x180062cd8`

## string_xrefs

- `0x180045238`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x1800452bf`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x1800452eb`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x180045363`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x18004538c`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x1800453d7`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`

## pseudocode

```c
void __fastcall CliThreadCryptEncryptCallback(PTP_CALLBACK_INSTANCE Instance, PVOID Context)
{
  void *v3; // rdx
  DWORD LastError; // ebx
  int v5; // ecx
  int v6; // eax
  int v7; // ebx
  int v8; // eax
  int v9; // ebx
  DWORD v10; // ebx
  int v11; // [rsp+80h] [rbp+18h]

  v11 = 0;
  CallbackMayRunLong(Instance);
  v3 = (void *)*((_QWORD *)Context + 14);
  if ( v3 )
  {
    if ( SetThreadToken(0, v3) )
    {
      v11 = 1;
    }
    else
    {
      LastError = GetLastError();
      DebugTraceError(LastError, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c", 957);
      *((_DWORD *)Context + 25) = LastError;
    }
  }
  v5 = *((_DWORD *)Context + 24);
  if ( (v5 & 0x10) != 0 )
  {
    v6 = c_SrvRpcCryptCipherEncrypt(
           *(_QWORD *)Context,
           *((_QWORD *)Context + 1),
           *((_QWORD *)Context + 2),
           *((_QWORD *)Context + 3),
           *((_QWORD *)Context + 6),
           *((_DWORD *)Context + 14),
           *((_QWORD *)Context + 8),
           *((_QWORD *)Context + 9),
           *((_DWORD *)Context + 20),
           *((_QWORD *)Context + 11),
           v5);
    v7 = v6;
    if ( v6 < 0 )
    {
      DebugTraceError(
        (unsigned int)v6,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
        985);
      *((_DWORD *)Context + 25) = v7;
    }
  }
  else
  {
    v8 = c_SrvRpcCryptEncrypt(
           *(_QWORD *)Context,
           *((_QWORD *)Context + 1),
           *((_QWORD *)Context + 2),
           *((_QWORD *)Context + 3),
           *((_QWORD *)Context + 6),
           *((_DWORD *)Context + 14),
           *((_QWORD *)Context + 5),
           *((_QWORD *)Context + 9),
           *((_DWORD *)Context + 20),
           *((_QWORD *)Context + 11),
           v5);
    v9 = v8;
    if ( v8 < 0 )
    {
      DebugTraceError(
        (unsigned int)v8,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
        1016);
      *((_DWORD *)Context + 25) = v9;
    }
  }
  if ( v11 && !RevertToSelf() )
  {
    v10 = GetLastError();
    DebugTraceError(v10, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c", 1032);
    *((_DWORD *)Context + 25) = v10;
  }
  SetEvent(**((HANDLE **)Context + 13));
}

```

## disassembly

```asm
0x1800451e0  mov     [rsp+arg_0], rbx
0x1800451e5  mov     [rsp+arg_8], rdx
0x1800451ea  push    rdi
0x1800451eb  sub     rsp, 60h
0x1800451ef  mov     rdi, rdx
0x1800451f2  mov     [rsp+68h+arg_10], 0
0x1800451fd  call    cs:__imp_CallbackMayRunLong
0x180045204  nop     dword ptr [rax+rax+00h]
0x180045209  mov     rdx, [rdi+70h]; Token
0x18004520d  test    rdx, rdx
0x180045210  jz      short loc_18004525D
0x180045212  xor     ecx, ecx; Thread
0x180045214  call    cs:__imp_SetThreadToken
0x18004521b  nop     dword ptr [rax+rax+00h]
0x180045220  test    eax, eax
0x180045222  jnz     short loc_180045252
0x180045224  call    cs:__imp_GetLastError
0x18004522b  nop     dword ptr [rax+rax+00h]
0x180045230  mov     ebx, eax
0x180045232  mov     r9d, 3BDh
0x180045238  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004523f  lea     rdx, aStatus; "Status"
0x180045246  mov     ecx, eax
0x180045248  call    DebugTraceError
0x18004524d  mov     [rdi+64h], ebx
0x180045250  jmp     short loc_18004525D
0x180045252  mov     [rsp+68h+arg_10], 1
0x18004525d  mov     ecx, [rdi+60h]
0x180045260  test    cl, 10h
0x180045263  jz      loc_18004530D
0x180045269  mov     [rsp+68h+var_18], ecx
0x18004526d  mov     rax, [rdi+58h]
0x180045271  mov     [rsp+68h+var_20], rax
0x180045276  mov     eax, [rdi+50h]
0x180045279  mov     [rsp+68h+var_28], eax
0x18004527d  mov     rax, [rdi+48h]
0x180045281  mov     [rsp+68h+var_30], rax
0x180045286  mov     rax, [rdi+40h]
0x18004528a  mov     [rsp+68h+var_38], rax
0x18004528f  mov     eax, [rdi+38h]
0x180045292  mov     [rsp+68h+var_40], eax
0x180045296  mov     rax, [rdi+30h]
0x18004529a  mov     [rsp+68h+var_48], rax
0x18004529f  mov     r9, [rdi+18h]
0x1800452a3  mov     r8, [rdi+10h]
0x1800452a7  mov     rdx, [rdi+8]
0x1800452ab  mov     rcx, [rdi]
0x1800452ae  call    c_SrvRpcCryptCipherEncrypt
0x1800452b3  mov     ebx, eax
0x1800452b5  test    eax, eax
0x1800452b7  jns     short loc_1800452D7
0x1800452b9  mov     r9d, 3D9h
0x1800452bf  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800452c6  lea     rdx, aStatus; "Status"
0x1800452cd  mov     ecx, eax
0x1800452cf  call    DebugTraceError
0x1800452d4  mov     [rdi+64h], ebx
0x1800452d7  jmp     loc_1800453A9
0x1800452dc  mov     ecx, eax
0x1800452de  call    HResultFromRpcException
0x1800452e3  mov     ebx, eax
0x1800452e5  mov     r9d, 3E0h
0x1800452eb  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800452f2  lea     rdx, aStatus; "Status"
0x1800452f9  mov     ecx, eax
0x1800452fb  call    DebugTraceError
0x180045300  mov     rdi, [rsp+68h+arg_8]
0x180045305  mov     [rdi+64h], ebx
0x180045308  jmp     loc_1800453A9
0x18004530d  mov     [rsp+68h+var_18], ecx
0x180045311  mov     rax, [rdi+58h]
0x180045315  mov     [rsp+68h+var_20], rax
0x18004531a  mov     eax, [rdi+50h]
0x18004531d  mov     [rsp+68h+var_28], eax
0x180045321  mov     rax, [rdi+48h]
0x180045325  mov     [rsp+68h+var_30], rax
0x18004532a  mov     rax, [rdi+28h]
0x18004532e  mov     [rsp+68h+var_38], rax
0x180045333  mov     eax, [rdi+38h]
0x180045336  mov     [rsp+68h+var_40], eax
0x18004533a  mov     rax, [rdi+30h]
0x18004533e  mov     [rsp+68h+var_48], rax
0x180045343  mov     r9, [rdi+18h]
0x180045347  mov     r8, [rdi+10h]
0x18004534b  mov     rdx, [rdi+8]
0x18004534f  mov     rcx, [rdi]
0x180045352  call    c_SrvRpcCryptEncrypt
0x180045357  mov     ebx, eax
0x180045359  test    eax, eax
0x18004535b  jns     short loc_18004537B
0x18004535d  mov     r9d, 3F8h
0x180045363  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004536a  lea     rdx, aStatus; "Status"
0x180045371  mov     ecx, eax
0x180045373  call    DebugTraceError
0x180045378  mov     [rdi+64h], ebx
0x18004537b  jmp     short loc_1800453A9
0x18004537d  mov     ecx, eax
0x18004537f  call    HResultFromRpcException
0x180045384  mov     ebx, eax
0x180045386  mov     r9d, 3FFh
0x18004538c  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180045393  lea     rdx, aStatus; "Status"
0x18004539a  mov     ecx, eax
0x18004539c  call    DebugTraceError
0x1800453a1  mov     rdi, [rsp+68h+arg_8]
0x1800453a6  mov     [rdi+64h], ebx
0x1800453a9  cmp     [rsp+68h+arg_10], 0
0x1800453b1  jz      short loc_1800453EF
0x1800453b3  call    cs:__imp_RevertToSelf
0x1800453ba  nop     dword ptr [rax+rax+00h]
0x1800453bf  test    eax, eax
0x1800453c1  jnz     short loc_1800453EF
0x1800453c3  call    cs:__imp_GetLastError
0x1800453ca  nop     dword ptr [rax+rax+00h]
0x1800453cf  mov     ebx, eax
0x1800453d1  mov     r9d, 408h
0x1800453d7  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800453de  lea     rdx, aStatus; "Status"
0x1800453e5  mov     ecx, eax
0x1800453e7  call    DebugTraceError
0x1800453ec  mov     [rdi+64h], ebx
0x1800453ef  mov     rcx, [rdi+68h]
0x1800453f3  mov     rcx, [rcx]; hEvent
0x1800453f6  call    cs:__imp_SetEvent
0x1800453fd  nop     dword ptr [rax+rax+00h]
0x180045402  mov     rbx, [rsp+68h+arg_0]
0x180045407  add     rsp, 60h
0x18004540b  pop     rdi
0x18004540c  retn
0x180062ca8  push    rbp
0x180062caa  sub     rsp, 60h
0x180062cae  mov     rbp, rdx
0x180062cb1  mov     rcx, [rcx]
0x180062cb4  mov     ecx, [rcx]; ExceptionCode
0x180062cb6  call    cs:__imp_I_RpcExceptionFilter
0x180062cbd  nop     dword ptr [rax+rax+00h]
0x180062cc2  nop
0x180062cc3  add     rsp, 60h
0x180062cc7  pop     rbp
0x180062cc8  retn
0x180062cca  push    rbp
0x180062ccc  sub     rsp, 60h
0x180062cd0  mov     rbp, rdx
0x180062cd3  mov     rcx, [rcx]
0x180062cd6  mov     ecx, [rcx]; ExceptionCode
0x180062cd8  call    cs:__imp_I_RpcExceptionFilter
0x180062cdf  nop     dword ptr [rax+rax+00h]
0x180062ce4  nop
0x180062ce5  add     rsp, 60h
0x180062ce9  pop     rbp
0x180062cea  retn
```
