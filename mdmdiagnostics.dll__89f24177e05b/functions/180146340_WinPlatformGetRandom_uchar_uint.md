# WinPlatformGetRandom(uchar *,uint)

- ea: `0x180146340`
- end: `0x1801463cf`
- name: `?WinPlatformGetRandom@@YAJPEAEI@Z`
- size: `143`
- prototype: `__int64 __fastcall(PUCHAR pbBuffer, ULONG cbBuffer)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180146340`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180146389`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180146389`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1801463b7`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1801463b7`
- `bcrypt!BCryptGenRandom` at `0x1801463a3`
- `bcrypt!BCryptGenRandom` at `0x1801463a3`

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
0x180146340  mov     [rsp+arg_0], rbx
0x180146345  mov     [rsp+arg_8], rsi
0x18014634a  push    rdi
0x18014634b  sub     rsp, 20h
0x18014634f  mov     [rsp+28h+phAlgorithm], 0
0x180146358  mov     edi, edx
0x18014635a  mov     rsi, rcx
0x18014635d  test    edx, edx
0x18014635f  jz      short loc_18014636D
0x180146361  test    rcx, rcx
0x180146364  jnz     short loc_18014636D
0x180146366  mov     eax, 0C000000Dh
0x18014636b  jmp     short loc_1801463BF
0x18014636d  xor     ebx, ebx
0x18014636f  test    edi, edi
0x180146371  jz      short loc_1801463BD
0x180146373  xor     r9d, r9d; dwFlags
0x180146376  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18014637d  lea     rdx, aRng; "RNG"
0x180146384  lea     rcx, [rsp+28h+phAlgorithm]; phAlgorithm
0x180146389  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18014638f  mov     ebx, eax
0x180146391  test    eax, eax
0x180146393  js      short loc_1801463AB
0x180146395  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x18014639a  xor     r9d, r9d; dwFlags
0x18014639d  mov     r8d, edi; cbBuffer
0x1801463a0  mov     rdx, rsi; pbBuffer
0x1801463a3  call    cs:__imp_BCryptGenRandom
0x1801463a9  mov     ebx, eax
0x1801463ab  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x1801463b0  test    rcx, rcx
0x1801463b3  jz      short loc_1801463BD
0x1801463b5  xor     edx, edx; dwFlags
0x1801463b7  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1801463bd  mov     eax, ebx
0x1801463bf  mov     rbx, [rsp+28h+arg_0]
0x1801463c4  mov     rsi, [rsp+28h+arg_8]
0x1801463c9  add     rsp, 20h
0x1801463cd  pop     rdi
0x1801463ce  retn
```
