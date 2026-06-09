# WinPlatformGetRandom(uchar *,uint)

- ea: `0x180148c40`
- end: `0x180148ce2`
- name: `?WinPlatformGetRandom@@YAJPEAEI@Z`
- size: `162`
- prototype: `__int64 __fastcall(PUCHAR pbBuffer, ULONG cbBuffer)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180148c40`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180148c89`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180148c89`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180148cc3`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180148cc3`
- `bcrypt!BCryptGenRandom` at `0x180148ca9`
- `bcrypt!BCryptGenRandom` at `0x180148ca9`

## pseudocode

```c
__int64 __fastcall WinPlatformGetRandom(PUCHAR pbBuffer, ULONG cbBuffer)
{
  NTSTATUS v5; // ebx
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp+18h] BYREF

  phAlgorithm = 0;
  if ( cbBuffer && !pbBuffer )
    return 3221225485LL;
  v5 = 0;
  if ( cbBuffer )
  {
    v5 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"RNG", L"Microsoft Primitive Provider", 0);
    if ( v5 >= 0 )
      v5 = BCryptGenRandom(phAlgorithm, pbBuffer, cbBuffer, 0);
    if ( phAlgorithm )
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180148c40  mov     [rsp+arg_0], rbx
0x180148c45  mov     [rsp+arg_8], rsi
0x180148c4a  push    rdi
0x180148c4b  sub     rsp, 20h
0x180148c4f  mov     [rsp+28h+phAlgorithm], 0
0x180148c58  mov     edi, edx
0x180148c5a  mov     rsi, rcx
0x180148c5d  test    edx, edx
0x180148c5f  jz      short loc_180148C6D
0x180148c61  test    rcx, rcx
0x180148c64  jnz     short loc_180148C6D
0x180148c66  mov     eax, 0C000000Dh
0x180148c6b  jmp     short loc_180148CD1
0x180148c6d  xor     ebx, ebx
0x180148c6f  test    edi, edi
0x180148c71  jz      short loc_180148CCF
0x180148c73  xor     r9d, r9d; dwFlags
0x180148c76  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x180148c7d  lea     rdx, aRng; "RNG"
0x180148c84  lea     rcx, [rsp+28h+phAlgorithm]; phAlgorithm
0x180148c89  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180148c90  nop     dword ptr [rax+rax+00h]
0x180148c95  mov     ebx, eax
0x180148c97  test    eax, eax
0x180148c99  js      short loc_180148CB7
0x180148c9b  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x180148ca0  xor     r9d, r9d; dwFlags
0x180148ca3  mov     r8d, edi; cbBuffer
0x180148ca6  mov     rdx, rsi; pbBuffer
0x180148ca9  call    cs:__imp_BCryptGenRandom
0x180148cb0  nop     dword ptr [rax+rax+00h]
0x180148cb5  mov     ebx, eax
0x180148cb7  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x180148cbc  test    rcx, rcx
0x180148cbf  jz      short loc_180148CCF
0x180148cc1  xor     edx, edx; dwFlags
0x180148cc3  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180148cca  nop     dword ptr [rax+rax+00h]
0x180148ccf  mov     eax, ebx
0x180148cd1  mov     rbx, [rsp+28h+arg_0]
0x180148cd6  mov     rsi, [rsp+28h+arg_8]
0x180148cdb  add     rsp, 20h
0x180148cdf  pop     rdi
0x180148ce0  retn
```
