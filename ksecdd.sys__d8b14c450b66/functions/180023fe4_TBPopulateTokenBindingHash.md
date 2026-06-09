# TBPopulateTokenBindingHash

- ea: `0x180023fe4`
- end: `0x1800240cf`
- name: `TBPopulateTokenBindingHash`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180023a28`

## callees

- `0x1800026d0`
- `0x180002710`
- `0x180002930`
- `0x180002970`
- `0x180023fe4`

## pseudocode

```c
__int64 __fastcall TBPopulateTokenBindingHash(UCHAR a1, UCHAR a2, UCHAR *a3, ULONG a4, PUCHAR pbOutput)
{
  NTSTATUS v7; // ebx
  unsigned int v8; // ebx
  NTSTATUS v9; // eax
  BCRYPT_HASH_HANDLE hHash; // [rsp+40h] [rbp-18h] BYREF
  UCHAR pbInput; // [rsp+60h] [rbp+8h] BYREF
  UCHAR v13; // [rsp+68h] [rbp+10h] BYREF

  v13 = a2;
  pbInput = a1;
  hHash = 0;
  v7 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, &hHash, 0, 0, 0, 0, 0);
  if ( v7 >= 0 )
  {
    v7 = BCryptHashData(hHash, &pbInput, 1u, 0);
    if ( v7 >= 0 )
    {
      v7 = BCryptHashData(hHash, &v13, 1u, 0);
      if ( v7 >= 0 )
      {
        v7 = BCryptHashData(hHash, a3, a4, 0);
        if ( v7 >= 0 )
        {
          v8 = 0;
          v9 = BCryptFinishHash(hHash, pbOutput, 0x20u, 0);
          if ( v9 >= 0 )
            goto LABEL_8;
          v7 = v9;
        }
      }
    }
  }
  v8 = v7 | 0x10000000;
LABEL_8:
  if ( hHash )
    BCryptDestroyHash(hHash);
  return v8;
}

```

## disassembly

```asm
0x180023fe4  mov     rax, rsp
0x180023fe7  mov     [rax+18h], rbx
0x180023feb  mov     [rax+20h], rsi
0x180023fef  mov     [rax+10h], dl
0x180023ff2  mov     [rax+8], cl
0x180023ff5  push    rdi
0x180023ff6  sub     rsp, 50h
0x180023ffa  mov     dword ptr [rax-28h], 0
0x180024001  lea     rdx, [rax-18h]; phHash
0x180024005  mov     edi, r9d
0x180024008  mov     dword ptr [rax-30h], 0
0x18002400f  xor     r9d, r9d; cbHashObject
0x180024012  mov     qword ptr [rax-18h], 0
0x18002401a  mov     rsi, r8
0x18002401d  mov     qword ptr [rax-38h], 0
0x180024025  xor     r8d, r8d; pbHashObject
0x180024028  lea     ecx, [r9+41h]; hAlgorithm
0x18002402c  call    BCryptCreateHash
0x180024031  mov     ebx, eax
0x180024033  test    eax, eax
0x180024035  js      short loc_1800240A9
0x180024037  mov     rcx, [rsp+58h+hHash]; hHash
0x18002403c  lea     rdx, [rsp+58h+pbInput]; pbInput
0x180024041  xor     r9d, r9d; dwFlags
0x180024044  lea     r8d, [r9+1]; cbInput
0x180024048  call    BCryptHashData
0x18002404d  mov     ebx, eax
0x18002404f  test    eax, eax
0x180024051  js      short loc_1800240A9
0x180024053  mov     rcx, [rsp+58h+hHash]; hHash
0x180024058  lea     rdx, [rsp+58h+arg_8]; pbInput
0x18002405d  xor     r9d, r9d; dwFlags
0x180024060  lea     r8d, [r9+1]; cbInput
0x180024064  call    BCryptHashData
0x180024069  mov     ebx, eax
0x18002406b  test    eax, eax
0x18002406d  js      short loc_1800240A9
0x18002406f  mov     rcx, [rsp+58h+hHash]; hHash
0x180024074  xor     r9d, r9d; dwFlags
0x180024077  mov     r8d, edi; cbInput
0x18002407a  mov     rdx, rsi; pbInput
0x18002407d  call    BCryptHashData
0x180024082  mov     ebx, eax
0x180024084  test    eax, eax
0x180024086  js      short loc_1800240A9
0x180024088  mov     rdx, [rsp+58h+pbOutput]; pbOutput
0x180024090  xor     ebx, ebx
0x180024092  mov     rcx, [rsp+58h+hHash]; hHash
0x180024097  xor     r9d, r9d; dwFlags
0x18002409a  lea     r8d, [rbx+20h]; cbOutput
0x18002409e  call    BCryptFinishHash
0x1800240a3  test    eax, eax
0x1800240a5  jns     short loc_1800240AD
0x1800240a7  mov     ebx, eax
0x1800240a9  bts     ebx, 1Ch
0x1800240ad  mov     rcx, [rsp+58h+hHash]; hHash
0x1800240b2  test    rcx, rcx
0x1800240b5  jz      short loc_1800240BC
0x1800240b7  call    BCryptDestroyHash
0x1800240bc  mov     rsi, [rsp+58h+arg_18]
0x1800240c1  mov     eax, ebx
0x1800240c3  mov     rbx, [rsp+58h+arg_10]
0x1800240c8  add     rsp, 50h
0x1800240cc  pop     rdi
0x1800240cd  retn
```
