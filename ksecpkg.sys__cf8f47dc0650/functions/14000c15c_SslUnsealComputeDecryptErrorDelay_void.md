# SslUnsealComputeDecryptErrorDelay(void)

- ea: `0x14000c15c`
- end: `0x14000c220`
- name: `?SslUnsealComputeDecryptErrorDelay@@YAKXZ`
- size: `196`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000c228`

## callees

- `0x14000c15c`

## import_xrefs

- `cng!BCryptGenRandom` at `0x14000c191`
- `cng!BCryptGenRandom` at `0x14000c1aa`
- `cng!BCryptGenRandom` at `0x14000c1ce`
- `cng!BCryptGenRandom` at `0x14000c1ff`
- `cng!BCryptGenRandom` at `0x14000c191`
- `cng!BCryptGenRandom` at `0x14000c1aa`
- `cng!BCryptGenRandom` at `0x14000c1ce`
- `cng!BCryptGenRandom` at `0x14000c1ff`

## pseudocode

```c
__int64 SslUnsealComputeDecryptErrorDelay(void)
{
  UCHAR v1; // [rsp+40h] [rbp+18h] BYREF
  int v2; // [rsp+48h] [rbp+20h] BYREF
  int v3; // [rsp+50h] [rbp+28h] BYREF
  int pbBuffer; // [rsp+58h] [rbp+30h] BYREF

  pbBuffer = 0;
  v3 = 0;
  v2 = 0;
  v1 = 0;
  BCryptGenRandom(0, (PUCHAR)&pbBuffer, 4u, 2u);
  BCryptGenRandom(0, (PUCHAR)&v3, 4u, 2u);
  pbBuffer &= 0x3FFFFFu;
  v3 &= 0x3FFFFFu;
  BCryptGenRandom(0, (PUCHAR)&v2, 4u, 2u);
  v2 &= 0x1FFFu;
  while ( BCryptGenRandom(0, &v1, 1u, 2u) >= 0 && v1 )
    v2 += 0x2000;
  return (unsigned int)(pbBuffer + v3 + v2);
}

```

## disassembly

```asm
0x14000c15c  push    rbp
0x14000c15e  push    rsi
0x14000c15f  mov     rbp, rsp
0x14000c162  sub     rsp, 28h
0x14000c166  mov     esi, 2
0x14000c16b  mov     [rbp+pbBuffer], 0
0x14000c172  mov     r9d, esi; dwFlags
0x14000c175  mov     [rbp+arg_10], 0
0x14000c17c  lea     rdx, [rbp+pbBuffer]; pbBuffer
0x14000c180  mov     [rbp+arg_8], 0
0x14000c187  xor     ecx, ecx; hAlgorithm
0x14000c189  mov     [rbp+arg_0], 0
0x14000c18d  lea     r8d, [rsi+2]; cbBuffer
0x14000c191  call    cs:__imp_BCryptGenRandom
0x14000c198  nop     dword ptr [rax+rax+00h]
0x14000c19d  mov     r9d, esi; dwFlags
0x14000c1a0  lea     r8d, [rsi+2]; cbBuffer
0x14000c1a4  lea     rdx, [rbp+arg_10]; pbBuffer
0x14000c1a8  xor     ecx, ecx; hAlgorithm
0x14000c1aa  call    cs:__imp_BCryptGenRandom
0x14000c1b1  nop     dword ptr [rax+rax+00h]
0x14000c1b6  mov     eax, 3FFFFFh
0x14000c1bb  lea     r8d, [rsi+2]; cbBuffer
0x14000c1bf  and     [rbp+pbBuffer], eax
0x14000c1c2  lea     rdx, [rbp+arg_8]; pbBuffer
0x14000c1c6  and     [rbp+arg_10], eax
0x14000c1c9  mov     r9d, esi; dwFlags
0x14000c1cc  xor     ecx, ecx; hAlgorithm
0x14000c1ce  call    cs:__imp_BCryptGenRandom
0x14000c1d5  nop     dword ptr [rax+rax+00h]
0x14000c1da  and     [rbp+arg_8], 1FFFh
0x14000c1e1  jmp     short loc_14000C1F0
0x14000c1e3  cmp     [rbp+arg_0], 0
0x14000c1e7  jz      short loc_14000C20F
0x14000c1e9  add     [rbp+arg_8], 2000h
0x14000c1f0  mov     r9d, esi; dwFlags
0x14000c1f3  lea     rdx, [rbp+arg_0]; pbBuffer
0x14000c1f7  mov     r8d, 1; cbBuffer
0x14000c1fd  xor     ecx, ecx; hAlgorithm
0x14000c1ff  call    cs:__imp_BCryptGenRandom
0x14000c206  nop     dword ptr [rax+rax+00h]
0x14000c20b  test    eax, eax
0x14000c20d  jns     short loc_14000C1E3
0x14000c20f  mov     eax, [rbp+arg_8]
0x14000c212  add     eax, [rbp+arg_10]
0x14000c215  add     eax, [rbp+pbBuffer]
0x14000c218  add     rsp, 28h
0x14000c21c  pop     rsi
0x14000c21d  pop     rbp
0x14000c21e  retn
```
