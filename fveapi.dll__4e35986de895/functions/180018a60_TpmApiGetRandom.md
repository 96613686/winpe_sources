# TpmApiGetRandom

- ea: `0x180018a60`
- end: `0x180018b07`
- name: `TpmApiGetRandom`
- size: `167`
- prototype: `__int64 __fastcall(ULONG cbBuffer, PUCHAR pbBuffer)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180017c80`
- `0x1800dd8d8`

## callees

- `0x180018a60`
- `0x180018b10`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180018a95`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180018a95`
- `bcrypt!BCryptGenRandom` at `0x180018ad9`
- `bcrypt!BCryptGenRandom` at `0x180018ad9`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180018af2`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180018af2`

## pseudocode

```c
__int64 __fastcall TpmApiGetRandom(ULONG cbBuffer, PUCHAR pbBuffer)
{
  int v2; // ebx
  NTSTATUS v5; // eax
  NTSTATUS v7; // eax
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+40h] [rbp+18h] BYREF

  v2 = 0;
  hAlgorithm = 0;
  if ( cbBuffer )
  {
    if ( pbBuffer )
    {
      v5 = BCryptOpenAlgorithmProvider(&hAlgorithm, L"RNG", 0, 0);
      v2 = FromNtStatus(v5);
      if ( v2 >= 0 )
      {
        v7 = BCryptGenRandom(hAlgorithm, pbBuffer, cbBuffer, 0);
        v2 = FromNtStatus(v7);
      }
      if ( hAlgorithm )
        BCryptCloseAlgorithmProvider(hAlgorithm, 0);
    }
    else
    {
      return (unsigned int)-2144796413;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180018a60  mov     rax, rsp
0x180018a63  mov     [rax+8], rbx
0x180018a67  mov     [rax+10h], rsi
0x180018a6b  push    rdi
0x180018a6c  sub     rsp, 20h
0x180018a70  xor     ebx, ebx
0x180018a72  mov     rdi, rdx
0x180018a75  mov     [rax+18h], rbx
0x180018a79  mov     esi, ecx
0x180018a7b  test    ecx, ecx
0x180018a7d  jz      short loc_180018AB8
0x180018a7f  test    rdx, rdx
0x180018a82  jz      short loc_180018B00
0x180018a84  xor     r9d, r9d; dwFlags
0x180018a87  lea     rdx, aRng; "RNG"
0x180018a8e  xor     r8d, r8d; pszImplementation
0x180018a91  lea     rcx, [rax+18h]; phAlgorithm
0x180018a95  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180018a9c  nop     dword ptr [rax+rax+00h]
0x180018aa1  mov     ecx, eax; int
0x180018aa3  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180018aa8  mov     ebx, eax
0x180018aaa  test    eax, eax
0x180018aac  jns     short loc_180018ACB
0x180018aae  mov     rcx, [rsp+28h+hAlgorithm]; hAlgorithm
0x180018ab3  test    rcx, rcx
0x180018ab6  jnz     short loc_180018AF0
0x180018ab8  mov     rsi, [rsp+28h+arg_8]
0x180018abd  mov     eax, ebx
0x180018abf  mov     rbx, [rsp+28h+arg_0]
0x180018ac4  add     rsp, 20h
0x180018ac8  pop     rdi
0x180018ac9  retn
0x180018acb  mov     rcx, [rsp+28h+hAlgorithm]; hAlgorithm
0x180018ad0  xor     r9d, r9d; dwFlags
0x180018ad3  mov     r8d, esi; cbBuffer
0x180018ad6  mov     rdx, rdi; pbBuffer
0x180018ad9  call    cs:__imp_BCryptGenRandom
0x180018ae0  nop     dword ptr [rax+rax+00h]
0x180018ae5  mov     ecx, eax; int
0x180018ae7  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180018aec  mov     ebx, eax
0x180018aee  jmp     short loc_180018AAE
0x180018af0  xor     edx, edx; dwFlags
0x180018af2  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180018af9  nop     dword ptr [rax+rax+00h]
0x180018afe  jmp     short loc_180018AB8
0x180018b00  mov     ebx, 80290103h
0x180018b05  jmp     short loc_180018AB8
```
