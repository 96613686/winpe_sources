# TBPopulateTokenBindingHash

- ea: `0x180024034`
- end: `0x18002411f`
- name: `TBPopulateTokenBindingHash`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180023a78`

## callees

- `0x1800026d0`
- `0x180002710`
- `0x180002930`
- `0x180002970`
- `0x180024034`

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
0x180024034  mov     rax, rsp
0x180024037  mov     [rax+18h], rbx
0x18002403b  mov     [rax+20h], rsi
0x18002403f  mov     [rax+10h], dl
0x180024042  mov     [rax+8], cl
0x180024045  push    rdi
0x180024046  sub     rsp, 50h
0x18002404a  mov     dword ptr [rax-28h], 0
0x180024051  lea     rdx, [rax-18h]; phHash
0x180024055  mov     edi, r9d
0x180024058  mov     dword ptr [rax-30h], 0
0x18002405f  xor     r9d, r9d; cbHashObject
0x180024062  mov     qword ptr [rax-18h], 0
0x18002406a  mov     rsi, r8
0x18002406d  mov     qword ptr [rax-38h], 0
0x180024075  xor     r8d, r8d; pbHashObject
0x180024078  lea     ecx, [r9+41h]; hAlgorithm
0x18002407c  call    BCryptCreateHash
0x180024081  mov     ebx, eax
0x180024083  test    eax, eax
0x180024085  js      short loc_1800240F9
0x180024087  mov     rcx, [rsp+58h+hHash]; hHash
0x18002408c  lea     rdx, [rsp+58h+pbInput]; pbInput
0x180024091  xor     r9d, r9d; dwFlags
0x180024094  lea     r8d, [r9+1]; cbInput
0x180024098  call    BCryptHashData
0x18002409d  mov     ebx, eax
0x18002409f  test    eax, eax
0x1800240a1  js      short loc_1800240F9
0x1800240a3  mov     rcx, [rsp+58h+hHash]; hHash
0x1800240a8  lea     rdx, [rsp+58h+arg_8]; pbInput
0x1800240ad  xor     r9d, r9d; dwFlags
0x1800240b0  lea     r8d, [r9+1]; cbInput
0x1800240b4  call    BCryptHashData
0x1800240b9  mov     ebx, eax
0x1800240bb  test    eax, eax
0x1800240bd  js      short loc_1800240F9
0x1800240bf  mov     rcx, [rsp+58h+hHash]; hHash
0x1800240c4  xor     r9d, r9d; dwFlags
0x1800240c7  mov     r8d, edi; cbInput
0x1800240ca  mov     rdx, rsi; pbInput
0x1800240cd  call    BCryptHashData
0x1800240d2  mov     ebx, eax
0x1800240d4  test    eax, eax
0x1800240d6  js      short loc_1800240F9
0x1800240d8  mov     rdx, [rsp+58h+pbOutput]; pbOutput
0x1800240e0  xor     ebx, ebx
0x1800240e2  mov     rcx, [rsp+58h+hHash]; hHash
0x1800240e7  xor     r9d, r9d; dwFlags
0x1800240ea  lea     r8d, [rbx+20h]; cbOutput
0x1800240ee  call    BCryptFinishHash
0x1800240f3  test    eax, eax
0x1800240f5  jns     short loc_1800240FD
0x1800240f7  mov     ebx, eax
0x1800240f9  bts     ebx, 1Ch
0x1800240fd  mov     rcx, [rsp+58h+hHash]; hHash
0x180024102  test    rcx, rcx
0x180024105  jz      short loc_18002410C
0x180024107  call    BCryptDestroyHash
0x18002410c  mov     rsi, [rsp+58h+arg_18]
0x180024111  mov     eax, ebx
0x180024113  mov     rbx, [rsp+58h+arg_10]
0x180024118  add     rsp, 50h
0x18002411c  pop     rdi
0x18002411d  retn
```
