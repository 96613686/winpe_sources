# I_OpenBCryptAlgHandle

- ea: `0x180024018`
- end: `0x1800240eb`
- name: `I_OpenBCryptAlgHandle`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000bf20`

## callees

- `0x18000b250`
- `0x180024018`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800240dd`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800240dd`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002404b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002404b`

## string_xrefs

- `0x1800240b5`: `onecore\ds\security\cryptoapi\ncrypt\common\provider.c`

## pseudocode

```c
__int64 __fastcall I_OpenBCryptAlgHandle(unsigned int a1)
{
  __int64 v1; // rdi
  int v2; // edx
  unsigned int v3; // ebx
  int v4; // r8d
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+58h] [rbp+10h] BYREF

  v1 = a1;
  hAlgorithm = 0;
  v3 = BCryptOpenAlgorithmProvider(&hAlgorithm, off_180065210[a1], 0, 0);
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v2,
        v4,
        (unsigned int)"Status",
        v3,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\provider.c",
        45);
  }
  else
  {
    if ( !_InterlockedCompareExchange64(&qword_180079F90[v1], (signed __int64)hAlgorithm, 0) )
      hAlgorithm = 0;
    v3 = 0;
  }
  if ( hAlgorithm )
    BCryptCloseAlgorithmProvider(hAlgorithm, 0);
  return v3;
}

```

## disassembly

```asm
0x180024018  mov     rax, rsp
0x18002401b  mov     [rax+8], rbx
0x18002401f  mov     [rax+20h], rsi
0x180024023  push    rdi
0x180024024  sub     rsp, 40h
0x180024028  mov     edi, ecx
0x18002402a  lea     rsi, __ImageBase
0x180024031  xor     r9d, r9d; dwFlags
0x180024034  mov     qword ptr [rax+10h], 0
0x18002403c  xor     r8d, r8d; pszImplementation
0x18002403f  lea     rcx, [rax+10h]; phAlgorithm
0x180024043  mov     rdx, ds:rva off_180065210[rsi+rdi*8]; pszAlgId
0x18002404b  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180024052  nop     dword ptr [rax+rax+00h]
0x180024057  mov     ebx, eax
0x180024059  test    eax, eax
0x18002405b  jnz     short loc_180024098
0x18002405d  mov     rcx, [rsp+48h+hAlgorithm]
0x180024062  xor     eax, eax
0x180024064  lock cmpxchg rva qword_180079F90[rsi+rdi*8], rcx
0x18002406e  jnz     short loc_180024079
0x180024070  mov     [rsp+48h+hAlgorithm], 0
0x180024079  xor     ebx, ebx
0x18002407b  mov     rcx, [rsp+48h+hAlgorithm]; hAlgorithm
0x180024080  test    rcx, rcx
0x180024083  jnz     short loc_1800240DB
0x180024085  mov     rsi, [rsp+48h+arg_18]
0x18002408a  mov     eax, ebx
0x18002408c  mov     rbx, [rsp+48h+arg_0]
0x180024091  add     rsp, 40h
0x180024095  pop     rdi
0x180024096  retn
0x180024098  mov     rcx, cs:WPP_GLOBAL_Control
0x18002409f  lea     rax, WPP_GLOBAL_Control
0x1800240a6  cmp     rcx, rax
0x1800240a9  jz      short loc_18002407B
0x1800240ab  test    byte ptr [rcx+1Ch], 1
0x1800240af  jz      short loc_18002407B
0x1800240b1  mov     rcx, [rcx+10h]
0x1800240b5  lea     rax, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800240bc  mov     [rsp+48h+var_18], 2Dh ; '-'
0x1800240c4  lea     r9, aStatus; "Status"
0x1800240cb  mov     [rsp+48h+var_20], rax
0x1800240d0  mov     [rsp+48h+var_28], ebx
0x1800240d4  call    WPP_SF_sDsd
0x1800240d9  jmp     short loc_18002407B
0x1800240db  xor     edx, edx; dwFlags
0x1800240dd  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800240e4  nop     dword ptr [rax+rax+00h]
0x1800240e9  jmp     short loc_180024085
```
