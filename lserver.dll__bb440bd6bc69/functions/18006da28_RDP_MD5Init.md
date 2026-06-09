# RDP_MD5Init

- ea: `0x18006da28`
- end: `0x18006dacb`
- name: `RDP_MD5Init`
- size: `163`
- prototype: `__int64 __fastcall(BCRYPT_HASH_HANDLE *phHash)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180062b44`
- `0x180065af0`

## callees

- `0x18006da28`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18006da7c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18006da7c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18006da53`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18006da53`
- `bcrypt!BCryptCreateHash` at `0x18006dab8`
- `bcrypt!BCryptCreateHash` at `0x18006dab8`

## pseudocode

```c
void __fastcall RDP_MD5Init(BCRYPT_HASH_HANDLE *phHash)
{
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+58h] [rbp+10h] BYREF

  if ( !g_hMD5Alg )
  {
    phAlgorithm = 0;
    if ( BCryptOpenAlgorithmProvider(&phAlgorithm, L"MD5", 0, 0) < 0 )
      return;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_hMD5Alg, (signed __int64)phAlgorithm, 0) )
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  }
  if ( phHash )
  {
    *phHash = 0;
    *(_OWORD *)(phHash + 1) = 0;
    BCryptCreateHash(g_hMD5Alg, phHash, 0, 0, 0, 0, 0);
  }
}

```

## disassembly

```asm
0x18006da28  push    rbx
0x18006da2a  sub     rsp, 40h
0x18006da2e  cmp     cs:?g_hMD5Alg@@3PEAXEA, 0; void * g_hMD5Alg
0x18006da36  mov     rbx, rcx
0x18006da39  jnz     short loc_18006DA88
0x18006da3b  and     [rsp+48h+phAlgorithm], 0
0x18006da41  lea     rdx, aMd5; "MD5"
0x18006da48  xor     r9d, r9d; dwFlags
0x18006da4b  lea     rcx, [rsp+48h+phAlgorithm]; phAlgorithm
0x18006da50  xor     r8d, r8d; pszImplementation
0x18006da53  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18006da5a  nop     dword ptr [rax+rax+00h]
0x18006da5f  test    eax, eax
0x18006da61  js      short loc_18006DAC4
0x18006da63  mov     rcx, [rsp+48h+phAlgorithm]
0x18006da68  xor     eax, eax
0x18006da6a  lock cmpxchg cs:?g_hMD5Alg@@3PEAXEA, rcx; void * g_hMD5Alg
0x18006da73  jz      short loc_18006DA88
0x18006da75  mov     rcx, [rsp+48h+phAlgorithm]; hAlgorithm
0x18006da7a  xor     edx, edx; dwFlags
0x18006da7c  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18006da83  nop     dword ptr [rax+rax+00h]
0x18006da88  test    rbx, rbx
0x18006da8b  jz      short loc_18006DAC4
0x18006da8d  and     qword ptr [rbx], 0
0x18006da91  xorps   xmm0, xmm0
0x18006da94  and     [rsp+48h+var_18], 0
0x18006da99  xor     r9d, r9d; cbHashObject
0x18006da9c  and     [rsp+48h+var_20], 0
0x18006daa1  xor     r8d, r8d; pbHashObject
0x18006daa4  and     [rsp+48h+var_28], 0
0x18006daaa  mov     rdx, rbx; phHash
0x18006daad  movups  xmmword ptr [rbx+8], xmm0
0x18006dab1  mov     rcx, cs:?g_hMD5Alg@@3PEAXEA; hAlgorithm
0x18006dab8  call    cs:__imp_BCryptCreateHash
0x18006dabf  nop     dword ptr [rax+rax+00h]
0x18006dac4  add     rsp, 40h
0x18006dac8  pop     rbx
0x18006dac9  retn
```
