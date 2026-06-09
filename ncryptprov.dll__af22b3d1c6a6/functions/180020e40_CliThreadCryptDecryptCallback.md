# _CliThreadCryptDecryptCallback

- ea: `0x180020e40`
- end: `0x180021118`
- name: `_CliThreadCryptDecryptCallback`
- size: `728`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, _QWORD *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000af80`
- `0x180020e40`
- `0x180060f5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021090`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800210e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021090`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800210e6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180021080`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180021080`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180020f7a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180020f7a`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180020e60`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180020e60`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800210d2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800210d2`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800628a8`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800628ca`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800628a8`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800628ca`
- `RPCRT4!NdrClientCall3` at `0x180020ef9`
- `RPCRT4!NdrClientCall3` at `0x18002100a`
- `RPCRT4!NdrClientCall3` at `0x180020ef9`
- `RPCRT4!NdrClientCall3` at `0x18002100a`

## string_xrefs

- `0x180020f1a`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x180020f44`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x18002102b`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x180021058`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x1800210a4`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x1800210fa`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`

## pseudocode

```c
void __fastcall CliThreadCryptDecryptCallback(PTP_CALLBACK_INSTANCE Instance, _QWORD *Context)
{
  void *v3; // rdx
  int v4; // eax
  int v5; // ebx
  int Pointer; // eax
  int v7; // ebx
  DWORD LastError; // ebx
  DWORD v9; // ebx
  int v10; // [rsp+40h] [rbp-48h]
  int v11; // [rsp+40h] [rbp-48h]
  int v12; // [rsp+58h] [rbp-30h]
  int v13; // [rsp+58h] [rbp-30h]
  int v14; // [rsp+68h] [rbp-20h]
  int v15; // [rsp+68h] [rbp-20h]
  int v16; // [rsp+A0h] [rbp+18h]

  v16 = 0;
  CallbackMayRunLong(Instance);
  v3 = (void *)Context[14];
  if ( v3 )
  {
    if ( SetThreadToken(0, v3) )
    {
      v16 = 1;
    }
    else
    {
      LastError = GetLastError();
      DebugTraceError(LastError, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c", 597);
      *((_DWORD *)Context + 25) = LastError;
    }
  }
  if ( (Context[12] & 0x10) != 0 )
  {
    v15 = *((_DWORD *)Context + 24);
    v13 = *((_DWORD *)Context + 20);
    v11 = *((_DWORD *)Context + 14);
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0x1Cu,
                              0,
                              *Context,
                              Context[1],
                              Context[2],
                              Context[3],
                              Context[6],
                              v11,
                              Context[8],
                              Context[9],
                              v13,
                              Context[11],
                              v15).Pointer;
    v7 = Pointer;
    if ( Pointer < 0 )
    {
      DebugTraceError(
        (unsigned int)Pointer,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
        623);
      *((_DWORD *)Context + 25) = v7;
    }
  }
  else
  {
    v14 = *((_DWORD *)Context + 24);
    v12 = *((_DWORD *)Context + 20);
    v10 = *((_DWORD *)Context + 14);
    v4 = (unsigned int)NdrClientCall3(
                         (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                         0x11u,
                         0,
                         *Context,
                         Context[1],
                         Context[2],
                         Context[3],
                         Context[6],
                         v10,
                         Context[5],
                         Context[9],
                         v12,
                         Context[11],
                         v14).Pointer;
    v5 = v4;
    if ( v4 < 0 )
    {
      DebugTraceError(
        (unsigned int)v4,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
        649);
      *((_DWORD *)Context + 25) = v5;
    }
  }
  if ( v16 && !RevertToSelf() )
  {
    v9 = GetLastError();
    DebugTraceError(v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c", 663);
    *((_DWORD *)Context + 25) = v9;
  }
  SetEvent(*(HANDLE *)Context[13]);
}

```

## disassembly

```asm
0x180020e40  mov     [rsp+arg_0], rbx
0x180020e45  mov     [rsp+arg_8], rdx
0x180020e4a  push    rsi
0x180020e4b  push    rdi
0x180020e4c  push    r14
0x180020e4e  sub     rsp, 70h
0x180020e52  mov     r14, rdx
0x180020e55  mov     [rsp+88h+arg_10], 0
0x180020e60  call    cs:__imp_CallbackMayRunLong
0x180020e67  nop     dword ptr [rax+rax+00h]
0x180020e6c  mov     rdx, [r14+70h]; Token
0x180020e70  test    rdx, rdx
0x180020e73  jnz     loc_18002107E
0x180020e79  mov     r9d, [r14+60h]
0x180020e7d  test    r9b, 10h
0x180020e81  jnz     loc_180020F98
0x180020e87  mov     rax, [r14+58h]
0x180020e8b  mov     ecx, [r14+50h]
0x180020e8f  mov     rdx, [r14+48h]
0x180020e93  mov     r8, [r14+28h]
0x180020e97  mov     r10d, [r14+38h]
0x180020e9b  mov     r11, [r14+30h]
0x180020e9f  mov     rbx, [r14+18h]
0x180020ea3  mov     rdi, [r14+10h]
0x180020ea7  mov     rsi, [r14+8]
0x180020eab  mov     [rsp+88h+arg_18], 0
0x180020eb7  mov     [rsp+88h+var_20], r9d
0x180020ebc  mov     [rsp+88h+var_28], rax
0x180020ec1  mov     [rsp+88h+var_30], ecx
0x180020ec5  mov     [rsp+88h+var_38], rdx
0x180020eca  mov     [rsp+88h+var_40], r8
0x180020ecf  mov     [rsp+88h+var_48], r10d
0x180020ed4  mov     [rsp+88h+var_50], r11
0x180020ed9  mov     [rsp+88h+var_58], rbx
0x180020ede  mov     [rsp+88h+var_60], rdi
0x180020ee3  mov     [rsp+88h+var_68], rsi
0x180020ee8  mov     r9, [r14]
0x180020eeb  xor     r8d, r8d; pReturnValue
0x180020eee  lea     edx, [r8+11h]; nProcNum
0x180020ef2  lea     rcx, pProxyInfo; pProxyInfo
0x180020ef9  call    cs:__imp_NdrClientCall3
0x180020f00  nop     dword ptr [rax+rax+00h]
0x180020f05  mov     rbx, rax
0x180020f08  mov     [rsp+88h+arg_18], rax
0x180020f10  test    eax, eax
0x180020f12  jns     short loc_180020F33
0x180020f14  mov     r9d, 289h
0x180020f1a  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180020f21  lea     rdx, aStatus; "Status"
0x180020f28  mov     ecx, ebx
0x180020f2a  call    DebugTraceError
0x180020f2f  mov     [r14+64h], ebx
0x180020f33  jmp     short loc_180020F65
0x180020f35  mov     ecx, eax
0x180020f37  call    HResultFromRpcException
0x180020f3c  mov     ebx, eax
0x180020f3e  mov     r9d, 28Eh
0x180020f44  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180020f4b  lea     rdx, aStatus; "Status"
0x180020f52  mov     ecx, eax
0x180020f54  call    DebugTraceError
0x180020f59  mov     r14, [rsp+88h+arg_8]
0x180020f61  mov     [r14+64h], ebx
0x180020f65  cmp     [rsp+88h+arg_10], 0
0x180020f6d  jnz     loc_1800210D2
0x180020f73  mov     rcx, [r14+68h]
0x180020f77  mov     rcx, [rcx]; hEvent
0x180020f7a  call    cs:__imp_SetEvent
0x180020f81  nop     dword ptr [rax+rax+00h]
0x180020f86  mov     rbx, [rsp+88h+arg_0]
0x180020f8e  add     rsp, 70h
0x180020f92  pop     r14
0x180020f94  pop     rdi
0x180020f95  pop     rsi
0x180020f96  retn
0x180020f98  mov     rax, [r14+58h]
0x180020f9c  mov     ecx, [r14+50h]
0x180020fa0  mov     rdx, [r14+48h]
0x180020fa4  mov     r8, [r14+40h]
0x180020fa8  mov     r10d, [r14+38h]
0x180020fac  mov     r11, [r14+30h]
0x180020fb0  mov     rbx, [r14+18h]
0x180020fb4  mov     rdi, [r14+10h]
0x180020fb8  mov     rsi, [r14+8]
0x180020fbc  mov     [rsp+88h+arg_18], 0
0x180020fc8  mov     [rsp+88h+var_20], r9d
0x180020fcd  mov     [rsp+88h+var_28], rax
0x180020fd2  mov     [rsp+88h+var_30], ecx
0x180020fd6  mov     [rsp+88h+var_38], rdx
0x180020fdb  mov     [rsp+88h+var_40], r8
0x180020fe0  mov     [rsp+88h+var_48], r10d
0x180020fe5  mov     [rsp+88h+var_50], r11
0x180020fea  mov     [rsp+88h+var_58], rbx
0x180020fef  mov     [rsp+88h+var_60], rdi
0x180020ff4  mov     [rsp+88h+var_68], rsi
0x180020ff9  mov     r9, [r14]
0x180020ffc  xor     r8d, r8d; pReturnValue
0x180020fff  lea     edx, [r8+1Ch]; nProcNum
0x180021003  lea     rcx, pProxyInfo; pProxyInfo
0x18002100a  call    cs:__imp_NdrClientCall3
0x180021011  nop     dword ptr [rax+rax+00h]
0x180021016  mov     rbx, rax
0x180021019  mov     [rsp+88h+arg_18], rax
0x180021021  test    eax, eax
0x180021023  jns     short loc_180021044
0x180021025  mov     r9d, 26Fh
0x18002102b  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021032  lea     rdx, aStatus; "Status"
0x180021039  mov     ecx, ebx
0x18002103b  call    DebugTraceError
0x180021040  mov     [r14+64h], ebx
0x180021044  jmp     loc_180020F65
0x180021049  mov     ecx, eax
0x18002104b  call    HResultFromRpcException
0x180021050  mov     ebx, eax
0x180021052  mov     r9d, 274h
0x180021058  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002105f  lea     rdx, aStatus; "Status"
0x180021066  mov     ecx, eax
0x180021068  call    DebugTraceError
0x18002106d  mov     r14, [rsp+88h+arg_8]
0x180021075  mov     [r14+64h], ebx
0x180021079  jmp     loc_180020F65
0x18002107e  xor     ecx, ecx; Thread
0x180021080  call    cs:__imp_SetThreadToken
0x180021087  nop     dword ptr [rax+rax+00h]
0x18002108c  test    eax, eax
0x18002108e  jnz     short loc_1800210C2
0x180021090  call    cs:__imp_GetLastError
0x180021097  nop     dword ptr [rax+rax+00h]
0x18002109c  mov     ebx, eax
0x18002109e  mov     r9d, 255h
0x1800210a4  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800210ab  lea     rdx, aStatus; "Status"
0x1800210b2  mov     ecx, eax
0x1800210b4  call    DebugTraceError
0x1800210b9  mov     [r14+64h], ebx
0x1800210bd  jmp     loc_180020E79
0x1800210c2  mov     [rsp+88h+arg_10], 1
0x1800210cd  jmp     loc_180020E79
0x1800210d2  call    cs:__imp_RevertToSelf
0x1800210d9  nop     dword ptr [rax+rax+00h]
0x1800210de  test    eax, eax
0x1800210e0  jnz     loc_180020F73
0x1800210e6  call    cs:__imp_GetLastError
0x1800210ed  nop     dword ptr [rax+rax+00h]
0x1800210f2  mov     ebx, eax
0x1800210f4  mov     r9d, 297h
0x1800210fa  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021101  lea     rdx, aStatus; "Status"
0x180021108  mov     ecx, eax
0x18002110a  call    DebugTraceError
0x18002110f  mov     [r14+64h], ebx
0x180021113  jmp     loc_180020F73
0x18006289a  push    rbp
0x18006289c  sub     rsp, 70h
0x1800628a0  mov     rbp, rdx
0x1800628a3  mov     rcx, [rcx]
0x1800628a6  mov     ecx, [rcx]; ExceptionCode
0x1800628a8  call    cs:__imp_I_RpcExceptionFilter
0x1800628af  nop     dword ptr [rax+rax+00h]
0x1800628b4  nop
0x1800628b5  add     rsp, 70h
0x1800628b9  pop     rbp
0x1800628ba  retn
0x1800628bc  push    rbp
0x1800628be  sub     rsp, 70h
0x1800628c2  mov     rbp, rdx
0x1800628c5  mov     rcx, [rcx]
0x1800628c8  mov     ecx, [rcx]; ExceptionCode
0x1800628ca  call    cs:__imp_I_RpcExceptionFilter
0x1800628d1  nop     dword ptr [rax+rax+00h]
0x1800628d6  nop
0x1800628d7  add     rsp, 70h
0x1800628db  pop     rbp
0x1800628dc  retn
```
