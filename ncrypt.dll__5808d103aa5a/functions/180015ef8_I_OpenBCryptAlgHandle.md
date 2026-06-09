# I_OpenBCryptAlgHandle

- ea: `0x180015ef8`
- end: `0x180015fbe`
- name: `I_OpenBCryptAlgHandle`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005fa0`

## callees

- `0x18000d02c`
- `0x180015ef8`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180015fb6`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180015fb6`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180015f2b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180015f2b`

## string_xrefs

- `0x180015f54`: `onecore\ds\security\cryptoapi\ncrypt\common\provider.c`

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
  v3 = BCryptOpenAlgorithmProvider(&hAlgorithm, off_1800210A0[a1], 0, 0);
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
    if ( !_InterlockedCompareExchange64(&qword_18002ADC0[v1], (signed __int64)hAlgorithm, 0) )
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
0x180015ef8  mov     rax, rsp
0x180015efb  mov     [rax+8], rbx
0x180015eff  mov     [rax+20h], rsi
0x180015f03  push    rdi
0x180015f04  sub     rsp, 40h
0x180015f08  mov     edi, ecx
0x180015f0a  lea     rsi, __ImageBase
0x180015f11  xor     r9d, r9d; dwFlags
0x180015f14  mov     qword ptr [rax+10h], 0
0x180015f1c  xor     r8d, r8d; pszImplementation
0x180015f1f  lea     rcx, [rax+10h]; phAlgorithm
0x180015f23  mov     rdx, ds:rva off_1800210A0[rsi+rdi*8]; pszAlgId
0x180015f2b  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180015f31  mov     ebx, eax
0x180015f33  test    eax, eax
0x180015f35  jz      short loc_180015F94
0x180015f37  mov     rcx, cs:WPP_GLOBAL_Control
0x180015f3e  lea     rax, WPP_GLOBAL_Control
0x180015f45  cmp     rcx, rax
0x180015f48  jz      short loc_180015F78
0x180015f4a  test    byte ptr [rcx+1Ch], 1
0x180015f4e  jz      short loc_180015F78
0x180015f50  mov     rcx, [rcx+10h]
0x180015f54  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180015f5b  mov     [rsp+48h+var_18], 2Dh ; '-'
0x180015f63  lea     r9, aStatus; "Status"
0x180015f6a  mov     [rsp+48h+var_20], rax
0x180015f6f  mov     [rsp+48h+var_28], ebx
0x180015f73  call    WPP_SF_sDsd
0x180015f78  mov     rcx, [rsp+48h+hAlgorithm]; hAlgorithm
0x180015f7d  test    rcx, rcx
0x180015f80  jnz     short loc_180015FB4
0x180015f82  mov     rsi, [rsp+48h+arg_18]
0x180015f87  mov     eax, ebx
0x180015f89  mov     rbx, [rsp+48h+arg_0]
0x180015f8e  add     rsp, 40h
0x180015f92  pop     rdi
0x180015f93  retn
0x180015f94  mov     rcx, [rsp+48h+hAlgorithm]
0x180015f99  xor     eax, eax
0x180015f9b  lock cmpxchg rva qword_18002ADC0[rsi+rdi*8], rcx
0x180015fa5  jnz     short loc_180015FB0
0x180015fa7  mov     [rsp+48h+hAlgorithm], 0
0x180015fb0  xor     ebx, ebx
0x180015fb2  jmp     short loc_180015F78
0x180015fb4  xor     edx, edx; dwFlags
0x180015fb6  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180015fbc  jmp     short loc_180015F82
```
