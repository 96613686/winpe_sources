# FvepComputeKeyFromPassphraseIterate

- ea: `0x14001b59c`
- end: `0x14001b689`
- name: `FvepComputeKeyFromPassphraseIterate`
- size: `237`
- prototype: `__int64 __fastcall(PUCHAR pbOutput)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140019120`

## callees

- `0x14001b59c`

## import_xrefs

- `ksecdd!BCryptDestroyHash` at `0x14001b662`
- `ksecdd!BCryptDestroyHash` at `0x14001b662`
- `ksecdd!BCryptFinishHash` at `0x14001b62e`
- `ksecdd!BCryptFinishHash` at `0x14001b62e`
- `ksecdd!BCryptHashData` at `0x14001b60d`
- `ksecdd!BCryptHashData` at `0x14001b60d`
- `ksecdd!BCryptCreateHash` at `0x14001b5e7`
- `ksecdd!BCryptCreateHash` at `0x14001b5e7`

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
0x14001b59c  mov     rax, rsp
0x14001b59f  mov     [rax+8], rbx
0x14001b5a3  mov     [rax+18h], rsi
0x14001b5a7  mov     [rax+20h], r9
0x14001b5ab  push    rdi
0x14001b5ac  sub     rsp, 40h
0x14001b5b0  mov     dword ptr [rax-18h], 0
0x14001b5b7  lea     rdx, [rax+20h]; phHash
0x14001b5bb  mov     rdi, rcx
0x14001b5be  mov     dword ptr [rax-20h], 0
0x14001b5c5  mov     rcx, cs:hAlgorithm; hAlgorithm
0x14001b5cc  xor     r9d, r9d; cbHashObject
0x14001b5cf  xor     r8d, r8d; pbHashObject
0x14001b5d2  mov     qword ptr [rax-28h], 0
0x14001b5da  mov     esi, 100000h
0x14001b5df  mov     qword ptr [rax+20h], 0
0x14001b5e7  call    cs:__imp_BCryptCreateHash
0x14001b5ee  nop     dword ptr [rax+rax+00h]
0x14001b5f3  mov     ebx, eax
0x14001b5f5  test    eax, eax
0x14001b5f7  js      short loc_14001B658
0x14001b5f9  test    rsi, rsi
0x14001b5fc  jz      short loc_14001B658
0x14001b5fe  mov     rcx, [rsp+48h+hHash]; hHash
0x14001b603  xor     r9d, r9d; dwFlags
0x14001b606  mov     rdx, rdi; pbInput
0x14001b609  lea     r8d, [r9+58h]; cbInput
0x14001b60d  call    cs:__imp_BCryptHashData
0x14001b614  nop     dword ptr [rax+rax+00h]
0x14001b619  mov     ebx, eax
0x14001b61b  test    eax, eax
0x14001b61d  js      short loc_14001B658
0x14001b61f  mov     rcx, [rsp+48h+hHash]; hHash
0x14001b624  xor     r9d, r9d; dwFlags
0x14001b627  mov     rdx, rdi; pbOutput
0x14001b62a  lea     r8d, [r9+20h]; cbOutput
0x14001b62e  call    cs:__imp_BCryptFinishHash
0x14001b635  nop     dword ptr [rax+rax+00h]
0x14001b63a  mov     ebx, eax
0x14001b63c  test    eax, eax
0x14001b63e  js      short loc_14001B658
0x14001b640  xor     ecx, ecx
0x14001b642  movsxd  rax, ecx
0x14001b645  add     byte ptr [rax+rdi+50h], 1
0x14001b64a  jnz     short loc_14001B681
0x14001b64c  inc     ecx
0x14001b64e  cmp     ecx, 8
0x14001b651  jl      short loc_14001B642
0x14001b653  mov     ebx, 0C000000Dh
0x14001b658  mov     rcx, [rsp+48h+hHash]; hHash
0x14001b65d  test    rcx, rcx
0x14001b660  jz      short loc_14001B66E
0x14001b662  call    cs:__imp_BCryptDestroyHash
0x14001b669  nop     dword ptr [rax+rax+00h]
0x14001b66e  mov     rsi, [rsp+48h+arg_10]
0x14001b673  mov     eax, ebx
0x14001b675  mov     rbx, [rsp+48h+arg_0]
0x14001b67a  add     rsp, 40h
0x14001b67e  pop     rdi
0x14001b67f  retn
0x14001b681  dec     rsi
0x14001b684  jmp     loc_14001B5F9
```
