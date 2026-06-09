# _CliThreadCryptSignHashCallback

- ea: `0x180045880`
- end: `0x180045a0d`
- name: `_CliThreadCryptSignHashCallback`
- size: `397`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000af80`
- `0x1800238a4`
- `0x180045880`
- `0x180060f5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800458c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800459bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800458c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800459bb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800458b7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800458b7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800459ee`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800459ee`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x1800458a0`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x1800458a0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800459ab`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800459ab`
- `RPCRT4!I_RpcExceptionFilter` at `0x180062bf6`
- `RPCRT4!I_RpcExceptionFilter` at `0x180062bf6`

## string_xrefs

- `0x1800458db`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x18004595a`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x180045983`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x1800459cf`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`

## pseudocode

```c
void __fastcall CliThreadCryptSignHashCallback(PTP_CALLBACK_INSTANCE Instance, PVOID Context)
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
      DebugTraceError(LastError, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c", 2744);
      *((_DWORD *)Context + 25) = LastError;
    }
  }
  v6 = c_SrvRpcCryptSignHash(
         *(_QWORD *)Context,
         *((_QWORD *)Context + 1),
         *((_QWORD *)Context + 2),
         *((_QWORD *)Context + 3),
         *((_QWORD *)Context + 5),
         *((_QWORD *)Context + 6),
         *((_DWORD *)Context + 14),
         *((_QWORD *)Context + 9),
         *((_DWORD *)Context + 20),
         *((_QWORD *)Context + 11),
         *((_DWORD *)Context + 24));
  v7 = v6;
  if ( v6 < 0 )
  {
    DebugTraceError((unsigned int)v6, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c", 2768);
    *((_DWORD *)Context + 25) = v7;
  }
  if ( v3 && !RevertToSelf() )
  {
    v8 = GetLastError();
    DebugTraceError(v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c", 2780);
    *((_DWORD *)Context + 25) = v8;
  }
  SetEvent(**((HANDLE **)Context + 13));
}

```

## disassembly

```asm
0x180045880  mov     [rsp+arg_0], rbx
0x180045885  mov     [rsp+arg_18], rsi
0x18004588a  mov     [rsp+arg_8], rdx
0x18004588f  push    rdi
0x180045890  sub     rsp, 60h
0x180045894  mov     rdi, rdx
0x180045897  xor     esi, esi
0x180045899  mov     [rsp+68h+arg_10], esi
0x1800458a0  call    cs:__imp_CallbackMayRunLong
0x1800458a7  nop     dword ptr [rax+rax+00h]
0x1800458ac  mov     rdx, [rdi+70h]; Token
0x1800458b0  test    rdx, rdx
0x1800458b3  jz      short loc_180045901
0x1800458b5  xor     ecx, ecx; Thread
0x1800458b7  call    cs:__imp_SetThreadToken
0x1800458be  nop     dword ptr [rax+rax+00h]
0x1800458c3  test    eax, eax
0x1800458c5  jnz     short loc_1800458F5
0x1800458c7  call    cs:__imp_GetLastError
0x1800458ce  nop     dword ptr [rax+rax+00h]
0x1800458d3  mov     ebx, eax
0x1800458d5  mov     r9d, 0AB8h
0x1800458db  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800458e2  lea     rdx, aStatus; "Status"
0x1800458e9  mov     ecx, eax
0x1800458eb  call    DebugTraceError
0x1800458f0  mov     [rdi+64h], ebx
0x1800458f3  jmp     short loc_180045901
0x1800458f5  mov     esi, 1
0x1800458fa  mov     [rsp+68h+arg_10], esi
0x180045901  mov     eax, [rdi+60h]
0x180045904  mov     [rsp+68h+var_18], eax
0x180045908  mov     rax, [rdi+58h]
0x18004590c  mov     [rsp+68h+var_20], rax
0x180045911  mov     eax, [rdi+50h]
0x180045914  mov     [rsp+68h+var_28], eax
0x180045918  mov     rax, [rdi+48h]
0x18004591c  mov     [rsp+68h+var_30], rax
0x180045921  mov     eax, [rdi+38h]
0x180045924  mov     [rsp+68h+var_38], eax
0x180045928  mov     rax, [rdi+30h]
0x18004592c  mov     [rsp+68h+var_40], rax
0x180045931  mov     rax, [rdi+28h]
0x180045935  mov     [rsp+68h+var_48], rax
0x18004593a  mov     r9, [rdi+18h]
0x18004593e  mov     r8, [rdi+10h]
0x180045942  mov     rdx, [rdi+8]
0x180045946  mov     rcx, [rdi]
0x180045949  call    c_SrvRpcCryptSignHash
0x18004594e  mov     ebx, eax
0x180045950  test    eax, eax
0x180045952  jns     short loc_180045972
0x180045954  mov     r9d, 0AD0h
0x18004595a  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180045961  lea     rdx, aStatus; "Status"
0x180045968  mov     ecx, eax
0x18004596a  call    DebugTraceError
0x18004596f  mov     [rdi+64h], ebx
0x180045972  jmp     short loc_1800459A7
0x180045974  mov     ecx, eax
0x180045976  call    HResultFromRpcException
0x18004597b  mov     ebx, eax
0x18004597d  mov     r9d, 0AD5h
0x180045983  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004598a  lea     rdx, aStatus; "Status"
0x180045991  mov     ecx, eax
0x180045993  call    DebugTraceError
0x180045998  mov     rdi, [rsp+68h+arg_8]
0x18004599d  mov     [rdi+64h], ebx
0x1800459a0  mov     esi, [rsp+68h+arg_10]
0x1800459a7  test    esi, esi
0x1800459a9  jz      short loc_1800459E7
0x1800459ab  call    cs:__imp_RevertToSelf
0x1800459b2  nop     dword ptr [rax+rax+00h]
0x1800459b7  test    eax, eax
0x1800459b9  jnz     short loc_1800459E7
0x1800459bb  call    cs:__imp_GetLastError
0x1800459c2  nop     dword ptr [rax+rax+00h]
0x1800459c7  mov     ebx, eax
0x1800459c9  mov     r9d, 0ADCh
0x1800459cf  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800459d6  lea     rdx, aStatus; "Status"
0x1800459dd  mov     ecx, eax
0x1800459df  call    DebugTraceError
0x1800459e4  mov     [rdi+64h], ebx
0x1800459e7  mov     rcx, [rdi+68h]
0x1800459eb  mov     rcx, [rcx]; hEvent
0x1800459ee  call    cs:__imp_SetEvent
0x1800459f5  nop     dword ptr [rax+rax+00h]
0x1800459fa  lea     r11, [rsp+68h+var_8]
0x1800459ff  mov     rbx, [r11+10h]
0x180045a03  mov     rsi, [r11+28h]
0x180045a07  mov     rsp, r11
0x180045a0a  pop     rdi
0x180045a0b  retn
0x180062be8  push    rbp
0x180062bea  sub     rsp, 60h
0x180062bee  mov     rbp, rdx
0x180062bf1  mov     rcx, [rcx]
0x180062bf4  mov     ecx, [rcx]; ExceptionCode
0x180062bf6  call    cs:__imp_I_RpcExceptionFilter
0x180062bfd  nop     dword ptr [rax+rax+00h]
0x180062c02  nop
0x180062c03  add     rsp, 60h
0x180062c07  pop     rbp
0x180062c08  retn
```
