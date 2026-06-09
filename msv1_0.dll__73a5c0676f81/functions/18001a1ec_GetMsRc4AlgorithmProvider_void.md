# GetMsRc4AlgorithmProvider(void)

- ea: `0x18001a1ec`
- end: `0x18001a250`
- name: `?GetMsRc4AlgorithmProvider@@YAPEAXXZ`
- size: `100`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18004b8e4`

## callees

- `0x18001a1ec`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001a225`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001a225`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001a248`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001a248`

## pseudocode

```c
BCRYPT_ALG_HANDLE GetMsRc4AlgorithmProvider(void)
{
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+30h] [rbp+8h] BYREF

  phAlgorithm = 0;
  if ( !hMsRc4AlgProvider
    && BCryptOpenAlgorithmProvider(&phAlgorithm, L"RC4", L"Microsoft Primitive Provider", 0) >= 0
    && _InterlockedCompareExchange64((volatile signed __int64 *)&hMsRc4AlgProvider, (signed __int64)phAlgorithm, 0) )
  {
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  }
  return hMsRc4AlgProvider;
}

```

## disassembly

```asm
0x18001a1ec  sub     rsp, 28h
0x18001a1f0  cmp     cs:?hMsRc4AlgProvider@@3PEAXEA, 0; void * hMsRc4AlgProvider
0x18001a1f8  mov     [rsp+28h+phAlgorithm], 0
0x18001a201  jz      short loc_18001A20F
0x18001a203  mov     rax, cs:?hMsRc4AlgProvider@@3PEAXEA; void * hMsRc4AlgProvider
0x18001a20a  add     rsp, 28h
0x18001a20e  retn
0x18001a20f  xor     r9d, r9d; dwFlags
0x18001a212  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18001a219  lea     rdx, pszAlgId; "RC4"
0x18001a220  lea     rcx, [rsp+28h+phAlgorithm]; phAlgorithm
0x18001a225  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18001a22b  test    eax, eax
0x18001a22d  js      short loc_18001A203
0x18001a22f  mov     rcx, [rsp+28h+phAlgorithm]
0x18001a234  xor     eax, eax
0x18001a236  lock cmpxchg cs:?hMsRc4AlgProvider@@3PEAXEA, rcx; void * hMsRc4AlgProvider
0x18001a23f  jz      short loc_18001A203
0x18001a241  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x18001a246  xor     edx, edx; dwFlags
0x18001a248  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18001a24e  jmp     short loc_18001A203
```
