# CryCreateSignature(unsigned __int64,ulong,ulong *)

- ea: `0x18001e988`
- end: `0x18001e9d9`
- name: `?CryCreateSignature@@YAPEAE_KKPEAK@Z`
- size: `81`
- prototype: `unsigned __int8 *__fastcall(HCRYPTHASH hHash, DWORD dwKeySpec, DWORD *pdwSigLen)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180019de4`

## callees

- `0x18001ea68`
- `0x18001eafc`
- `0x180021010`

## import_xrefs

- `msvcrt!free` at `0x18001e9c5`
- `msvcrt!free` at `0x18001e9c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int8 *__fastcall CryCreateSignature(HCRYPTHASH hHash, DWORD dwKeySpec, DWORD *pdwSigLen)
{
  DWORD v6; // eax
  BYTE *v8; // [rsp+60h] [rbp+18h]

  v6 = CrypSignatureLength(hHash, dwKeySpec);
  *pdwSigLen = v6;
  v8 = (BYTE *)MmAllocate(v6);
  CrypSignHashData(v8, pdwSigLen, hHash, dwKeySpec);
  free(0);
  return v8;
}

```

## disassembly

```asm
0x18001e988  push    rbx
0x18001e98a  push    rsi
0x18001e98b  push    rdi
0x18001e98c  push    r14
0x18001e98e  sub     rsp, 28h
0x18001e992  mov     r14, r8
0x18001e995  mov     edi, edx
0x18001e997  mov     rsi, rcx
0x18001e99a  call    ?CrypSignatureLength@@YAK_KK@Z; CrypSignatureLength(unsigned __int64,ulong)
0x18001e99f  mov     ecx, eax; unsigned __int64
0x18001e9a1  mov     [r14], ecx
0x18001e9a4  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18001e9a9  mov     rbx, rax
0x18001e9ac  mov     [rsp+48h+arg_10], rax
0x18001e9b1  mov     r9d, edi; dwKeySpec
0x18001e9b4  mov     r8, rsi; hHash
0x18001e9b7  mov     rdx, r14; pdwSigLen
0x18001e9ba  mov     rcx, rax; pbSignature
0x18001e9bd  call    ?CrypSignHashData@@YAXPEAEPEAK_KK@Z; CrypSignHashData(uchar *,ulong *,unsigned __int64,ulong)
0x18001e9c2  nop
0x18001e9c3  xor     ecx, ecx; Block
0x18001e9c5  call    cs:__imp_free
0x18001e9cb  nop
0x18001e9cc  mov     rax, rbx
0x18001e9cf  add     rsp, 28h
0x18001e9d3  pop     r14
0x18001e9d5  pop     rdi
0x18001e9d6  pop     rsi
0x18001e9d7  pop     rbx
0x18001e9d8  retn
```
