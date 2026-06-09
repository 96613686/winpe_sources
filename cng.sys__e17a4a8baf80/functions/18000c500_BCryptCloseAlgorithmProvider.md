# BCryptCloseAlgorithmProvider

- ea: `0x18000c500`
- end: `0x18000c649`
- name: `BCryptCloseAlgorithmProvider`
- size: `329`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE hAlgorithm, ULONG dwFlags)`
- caller_count: `13`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000b7d8`
- `0x18000b898`
- `0x18000c9e0`
- `0x18000e204`
- `0x1800417a0`
- `0x1800648ac`
- `0x1800719a0`
- `0x180071b30`
- `0x180071c58`
- `0x18008b798`
- `0x18008b864`
- `0x18008e740`
- `0x18008ebd0`

## callees

- `0x18000c500`
- `0x18000daf0`
- `0x18000e310`
- `0x18001155c`
- `0x1800123d0`
- `0x18006547c`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x18000c514`
- `ntoskrnl!KeGetCurrentIrql` at `0x18000c514`

## string_xrefs

- `0x18000c5a1`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000c5e7`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000c60d`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

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
0x18000c500  mov     [rsp+arg_0], rbx
0x18000c505  mov     [rsp+arg_8], rsi
0x18000c50a  push    rdi
0x18000c50b  sub     rsp, 40h
0x18000c50f  mov     esi, edx
0x18000c511  mov     rbx, rcx
0x18000c514  call    cs:__imp_KeGetCurrentIrql
0x18000c51b  nop     dword ptr [rax+rax+00h]
0x18000c520  cmp     al, 2
0x18000c522  jnb     short loc_18000C57A
0x18000c524  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c52b  lea     rdi, WPP_GLOBAL_Control
0x18000c532  cmp     rcx, rdi
0x18000c535  jz      short loc_18000C542
0x18000c537  mov     eax, [rcx+2Ch]
0x18000c53a  test    al, 4
0x18000c53c  jnz     loc_18000C62F
0x18000c542  mov     rcx, rbx
0x18000c545  call    ValidateBaseAlgHandle
0x18000c54a  xor     ebx, ebx
0x18000c54c  test    rax, rax
0x18000c54f  jz      short loc_18000C5C7
0x18000c551  cmp     [rax+8], ebx
0x18000c554  jl      short loc_18000C5C7
0x18000c556  cmp     [rax+20h], ebx
0x18000c559  jnz     loc_18000C5FD
0x18000c55f  mov     rcx, rax
0x18000c562  call    DecrementReferenceCount
0x18000c567  mov     rsi, [rsp+48h+arg_8]
0x18000c56c  mov     eax, ebx
0x18000c56e  mov     rbx, [rsp+48h+arg_0]
0x18000c573  add     rsp, 40h
0x18000c577  pop     rdi
0x18000c578  retn
0x18000c57a  mov     ebx, 0C00000BBh
0x18000c57f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c586  lea     rdi, WPP_GLOBAL_Control
0x18000c58d  cmp     rcx, rdi
0x18000c590  jz      short loc_18000C567
0x18000c592  mov     eax, [rcx+2Ch]
0x18000c595  test    al, 1
0x18000c597  jz      short loc_18000C567
0x18000c599  mov     [rsp+48h+var_18], 983h
0x18000c5a1  lea     rax, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c5a8  mov     [rsp+48h+var_20], rax
0x18000c5ad  mov     [rsp+48h+var_28], 0C00000BBh
0x18000c5b5  mov     rcx, [rcx+18h]
0x18000c5b9  lea     r9, aStatus; "Status"
0x18000c5c0  call    WPP_SF_sDsd
0x18000c5c5  jmp     short loc_18000C567
0x18000c5c7  mov     ebx, 0C0000008h
0x18000c5cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c5d3  cmp     rcx, rdi
0x18000c5d6  jz      short loc_18000C567
0x18000c5d8  mov     eax, [rcx+2Ch]
0x18000c5db  test    al, 1
0x18000c5dd  jz      short loc_18000C567
0x18000c5df  mov     [rsp+48h+var_18], 990h
0x18000c5e7  lea     rax, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c5ee  mov     [rsp+48h+var_20], rax
0x18000c5f3  mov     [rsp+48h+var_28], 0C0000008h
0x18000c5fb  jmp     short loc_18000C5B5
0x18000c5fd  cmp     dword ptr [rax+10h], 1
0x18000c601  jbe     loc_18000C55F
0x18000c607  mov     r9d, 9B2h
0x18000c60d  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c614  lea     rdx, aStatus; "Status"
0x18000c61b  mov     ecx, 0C0000008h
0x18000c620  mov     ebx, 0C0000008h
0x18000c625  call    DebugTraceError
0x18000c62a  jmp     loc_18000C567
0x18000c62f  mov     rcx, [rcx+18h]
0x18000c633  mov     edx, 0Eh
0x18000c638  mov     r9, rbx
0x18000c63b  mov     [rsp+48h+var_28], esi
0x18000c63f  call    WPP_SF_qD
0x18000c644  jmp     loc_18000C542
```
