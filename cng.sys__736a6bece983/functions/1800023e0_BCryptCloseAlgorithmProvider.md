# BCryptCloseAlgorithmProvider

- ea: `0x1800023e0`
- end: `0x180002529`
- name: `BCryptCloseAlgorithmProvider`
- size: `329`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE hAlgorithm, ULONG dwFlags)`
- caller_count: `13`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800016b0`
- `0x180001770`
- `0x1800028c0`
- `0x1800040e4`
- `0x180038230`
- `0x18005afcc`
- `0x180068200`
- `0x180068390`
- `0x1800684b8`
- `0x180082598`
- `0x180082664`
- `0x180085568`
- `0x1800859f8`

## callees

- `0x1800023e0`
- `0x1800039d0`
- `0x1800041f0`
- `0x18000743c`
- `0x1800082b0`
- `0x18005bb9c`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1800023f4`
- `ntoskrnl!KeGetCurrentIrql` at `0x1800023f4`

## string_xrefs

- `0x180002481`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800024c7`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800024ed`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptCloseAlgorithmProvider(BCRYPT_ALG_HANDLE hAlgorithm, ULONG dwFlags)
{
  int v4; // edx
  __int64 v5; // r8
  int *v6; // rax
  int v7; // edx
  int v8; // r8d
  NTSTATUS v9; // ebx

  if ( KeGetCurrentIrql() >= 2u )
  {
    v9 = -1073741637;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v4,
        v5,
        (unsigned int)"Status",
        187,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        131);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 3), 14, v5, hAlgorithm, dwFlags);
    v6 = (int *)ValidateBaseAlgHandle(hAlgorithm);
    v9 = 0;
    if ( v6 && v6[2] >= 0 )
    {
      if ( v6[8] && (unsigned int)v6[4] > 1 )
      {
        v9 = -1073741816;
        DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 2482);
      }
      else
      {
        DecrementReferenceCount(v6);
      }
    }
    else
    {
      v9 = -1073741816;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v7,
          v8,
          (unsigned int)"Status",
          8,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
          144);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x1800023e0  mov     [rsp+arg_0], rbx
0x1800023e5  mov     [rsp+arg_8], rsi
0x1800023ea  push    rdi
0x1800023eb  sub     rsp, 40h
0x1800023ef  mov     esi, edx
0x1800023f1  mov     rbx, rcx
0x1800023f4  call    cs:__imp_KeGetCurrentIrql
0x1800023fb  nop     dword ptr [rax+rax+00h]
0x180002400  cmp     al, 2
0x180002402  jnb     short loc_18000245A
0x180002404  mov     rcx, cs:WPP_GLOBAL_Control
0x18000240b  lea     rdi, WPP_GLOBAL_Control
0x180002412  cmp     rcx, rdi
0x180002415  jz      short loc_180002422
0x180002417  mov     eax, [rcx+2Ch]
0x18000241a  test    al, 4
0x18000241c  jnz     loc_18000250F
0x180002422  mov     rcx, rbx
0x180002425  call    ValidateBaseAlgHandle
0x18000242a  xor     ebx, ebx
0x18000242c  test    rax, rax
0x18000242f  jz      short loc_1800024A7
0x180002431  cmp     [rax+8], ebx
0x180002434  jl      short loc_1800024A7
0x180002436  cmp     [rax+20h], ebx
0x180002439  jnz     loc_1800024DD
0x18000243f  mov     rcx, rax
0x180002442  call    DecrementReferenceCount
0x180002447  mov     rsi, [rsp+48h+arg_8]
0x18000244c  mov     eax, ebx
0x18000244e  mov     rbx, [rsp+48h+arg_0]
0x180002453  add     rsp, 40h
0x180002457  pop     rdi
0x180002458  retn
0x18000245a  mov     ebx, 0C00000BBh
0x18000245f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002466  lea     rdi, WPP_GLOBAL_Control
0x18000246d  cmp     rcx, rdi
0x180002470  jz      short loc_180002447
0x180002472  mov     eax, [rcx+2Ch]
0x180002475  test    al, 1
0x180002477  jz      short loc_180002447
0x180002479  mov     [rsp+48h+var_18], 983h
0x180002481  lea     rax, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002488  mov     [rsp+48h+var_20], rax
0x18000248d  mov     [rsp+48h+var_28], 0C00000BBh
0x180002495  mov     rcx, [rcx+18h]
0x180002499  lea     r9, aStatus; "Status"
0x1800024a0  call    WPP_SF_sDsd
0x1800024a5  jmp     short loc_180002447
0x1800024a7  mov     ebx, 0C0000008h
0x1800024ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800024b3  cmp     rcx, rdi
0x1800024b6  jz      short loc_180002447
0x1800024b8  mov     eax, [rcx+2Ch]
0x1800024bb  test    al, 1
0x1800024bd  jz      short loc_180002447
0x1800024bf  mov     [rsp+48h+var_18], 990h
0x1800024c7  lea     rax, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800024ce  mov     [rsp+48h+var_20], rax
0x1800024d3  mov     [rsp+48h+var_28], 0C0000008h
0x1800024db  jmp     short loc_180002495
0x1800024dd  cmp     dword ptr [rax+10h], 1
0x1800024e1  jbe     loc_18000243F
0x1800024e7  mov     r9d, 9B2h
0x1800024ed  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800024f4  lea     rdx, aStatus; "Status"
0x1800024fb  mov     ecx, 0C0000008h
0x180002500  mov     ebx, 0C0000008h
0x180002505  call    DebugTraceError
0x18000250a  jmp     loc_180002447
0x18000250f  mov     rcx, [rcx+18h]
0x180002513  mov     edx, 0Eh
0x180002518  mov     r9, rbx
0x18000251b  mov     [rsp+48h+var_28], esi
0x18000251f  call    WPP_SF_qD
0x180002524  jmp     loc_180002422
```
