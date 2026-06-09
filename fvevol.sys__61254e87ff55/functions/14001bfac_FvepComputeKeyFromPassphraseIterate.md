# FvepComputeKeyFromPassphraseIterate

- ea: `0x14001bfac`
- end: `0x14001c099`
- name: `FvepComputeKeyFromPassphraseIterate`
- size: `237`
- prototype: `__int64 __fastcall(PUCHAR pbOutput)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140019b30`

## callees

- `0x14001bfac`

## import_xrefs

- `ksecdd!BCryptDestroyHash` at `0x14001c072`
- `ksecdd!BCryptDestroyHash` at `0x14001c072`
- `ksecdd!BCryptFinishHash` at `0x14001c03e`
- `ksecdd!BCryptFinishHash` at `0x14001c03e`
- `ksecdd!BCryptHashData` at `0x14001c01d`
- `ksecdd!BCryptHashData` at `0x14001c01d`
- `ksecdd!BCryptCreateHash` at `0x14001bff7`
- `ksecdd!BCryptCreateHash` at `0x14001bff7`

## pseudocode

```c
__int64 __fastcall FvepComputeKeyFromPassphraseIterate(PUCHAR pbOutput)
{
  __int64 v2; // rsi
  NTSTATUS v3; // ebx
  int v4; // ecx
  BCRYPT_HASH_HANDLE hHash; // [rsp+68h] [rbp+20h] BYREF

  v2 = 0x100000;
  hHash = 0;
  v3 = BCryptCreateHash(hAlgorithm, &hHash, 0, 0, 0, 0, 0);
  if ( v3 >= 0 )
  {
    while ( v2 )
    {
      v3 = BCryptHashData(hHash, pbOutput, 0x58u, 0);
      if ( v3 < 0 )
        break;
      v3 = BCryptFinishHash(hHash, pbOutput, 0x20u, 0);
      if ( v3 < 0 )
        break;
      v4 = 0;
      while ( pbOutput[v4 + 80]++ == 0xFF )
      {
        if ( ++v4 >= 8 )
        {
          v3 = -1073741811;
          goto LABEL_9;
        }
      }
      --v2;
    }
  }
LABEL_9:
  if ( hHash )
    BCryptDestroyHash(hHash);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14001bfac  mov     rax, rsp
0x14001bfaf  mov     [rax+8], rbx
0x14001bfb3  mov     [rax+18h], rsi
0x14001bfb7  mov     [rax+20h], r9
0x14001bfbb  push    rdi
0x14001bfbc  sub     rsp, 40h
0x14001bfc0  mov     dword ptr [rax-18h], 0
0x14001bfc7  lea     rdx, [rax+20h]; phHash
0x14001bfcb  mov     rdi, rcx
0x14001bfce  mov     dword ptr [rax-20h], 0
0x14001bfd5  mov     rcx, cs:hAlgorithm; hAlgorithm
0x14001bfdc  xor     r9d, r9d; cbHashObject
0x14001bfdf  xor     r8d, r8d; pbHashObject
0x14001bfe2  mov     qword ptr [rax-28h], 0
0x14001bfea  mov     esi, 100000h
0x14001bfef  mov     qword ptr [rax+20h], 0
0x14001bff7  call    cs:__imp_BCryptCreateHash
0x14001bffe  nop     dword ptr [rax+rax+00h]
0x14001c003  mov     ebx, eax
0x14001c005  test    eax, eax
0x14001c007  js      short loc_14001C068
0x14001c009  test    rsi, rsi
0x14001c00c  jz      short loc_14001C068
0x14001c00e  mov     rcx, [rsp+48h+hHash]; hHash
0x14001c013  xor     r9d, r9d; dwFlags
0x14001c016  mov     rdx, rdi; pbInput
0x14001c019  lea     r8d, [r9+58h]; cbInput
0x14001c01d  call    cs:__imp_BCryptHashData
0x14001c024  nop     dword ptr [rax+rax+00h]
0x14001c029  mov     ebx, eax
0x14001c02b  test    eax, eax
0x14001c02d  js      short loc_14001C068
0x14001c02f  mov     rcx, [rsp+48h+hHash]; hHash
0x14001c034  xor     r9d, r9d; dwFlags
0x14001c037  mov     rdx, rdi; pbOutput
0x14001c03a  lea     r8d, [r9+20h]; cbOutput
0x14001c03e  call    cs:__imp_BCryptFinishHash
0x14001c045  nop     dword ptr [rax+rax+00h]
0x14001c04a  mov     ebx, eax
0x14001c04c  test    eax, eax
0x14001c04e  js      short loc_14001C068
0x14001c050  xor     ecx, ecx
0x14001c052  movsxd  rax, ecx
0x14001c055  add     byte ptr [rax+rdi+50h], 1
0x14001c05a  jnz     short loc_14001C091
0x14001c05c  inc     ecx
0x14001c05e  cmp     ecx, 8
0x14001c061  jl      short loc_14001C052
0x14001c063  mov     ebx, 0C000000Dh
0x14001c068  mov     rcx, [rsp+48h+hHash]; hHash
0x14001c06d  test    rcx, rcx
0x14001c070  jz      short loc_14001C07E
0x14001c072  call    cs:__imp_BCryptDestroyHash
0x14001c079  nop     dword ptr [rax+rax+00h]
0x14001c07e  mov     rsi, [rsp+48h+arg_10]
0x14001c083  mov     eax, ebx
0x14001c085  mov     rbx, [rsp+48h+arg_0]
0x14001c08a  add     rsp, 40h
0x14001c08e  pop     rdi
0x14001c08f  retn
0x14001c091  dec     rsi
0x14001c094  jmp     loc_14001C009
```
