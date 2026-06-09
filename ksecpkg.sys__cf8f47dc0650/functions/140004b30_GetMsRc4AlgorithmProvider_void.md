# GetMsRc4AlgorithmProvider(void)

- ea: `0x140004b30`
- end: `0x140004ba8`
- name: `?GetMsRc4AlgorithmProvider@@YAPEAXXZ`
- size: `120`
- prototype: `void *(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140020d50`
- `0x140030020`

## callees

- `0x140004b30`

## import_xrefs

- `cng!BCryptOpenAlgorithmProvider` at `0x140004b68`
- `cng!BCryptOpenAlgorithmProvider` at `0x140004b68`
- `cng!BCryptCloseAlgorithmProvider` at `0x140004b9a`
- `cng!BCryptCloseAlgorithmProvider` at `0x140004b9a`

## pseudocode

```c
void *GetMsRc4AlgorithmProvider(void)
{
  void *result; // rax
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+30h] [rbp+8h] BYREF

  result = hMsRc4AlgProvider;
  phAlgorithm = 0;
  if ( !hMsRc4AlgProvider )
  {
    if ( BCryptOpenAlgorithmProvider(&phAlgorithm, L"RC4", L"Microsoft Primitive Provider", 1u) >= 0 )
    {
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)&hMsRc4AlgProvider, (signed __int64)phAlgorithm, 0) )
        BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    }
    return hMsRc4AlgProvider;
  }
  return result;
}

```

## disassembly

```asm
0x140004b30  sub     rsp, 28h
0x140004b34  mov     rax, cs:?hMsRc4AlgProvider@@3PEAXEA; void * hMsRc4AlgProvider
0x140004b3b  mov     [rsp+28h+phAlgorithm], 0
0x140004b44  test    rax, rax
0x140004b47  jz      short loc_140004B4F
0x140004b49  add     rsp, 28h
0x140004b4d  retn
0x140004b4f  mov     r9d, 1; dwFlags
0x140004b55  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x140004b5c  lea     rdx, pszAlgId; "RC4"
0x140004b63  lea     rcx, [rsp+28h+phAlgorithm]; phAlgorithm
0x140004b68  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140004b6f  nop     dword ptr [rax+rax+00h]
0x140004b74  test    eax, eax
0x140004b76  js      short loc_140004B8A
0x140004b78  mov     rcx, [rsp+28h+phAlgorithm]
0x140004b7d  xor     eax, eax
0x140004b7f  lock cmpxchg cs:?hMsRc4AlgProvider@@3PEAXEA, rcx; void * hMsRc4AlgProvider
0x140004b88  jnz     short loc_140004B93
0x140004b8a  mov     rax, cs:?hMsRc4AlgProvider@@3PEAXEA; void * hMsRc4AlgProvider
0x140004b91  jmp     short loc_140004B49
0x140004b93  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x140004b98  xor     edx, edx; dwFlags
0x140004b9a  call    cs:__imp_BCryptCloseAlgorithmProvider
0x140004ba1  nop     dword ptr [rax+rax+00h]
0x140004ba6  jmp     short loc_140004B8A
```
