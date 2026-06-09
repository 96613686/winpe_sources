# GetGeneric

- ea: `0x180019a40`
- end: `0x180019abc`
- name: `GetGeneric`
- size: `124`
- prototype: ``
- caller_count: `20`
- callee_count: `3`
- tags: ``

## callers

- `0x1800075f4`
- `0x1800089c8`
- `0x18000b334`
- `0x18000b498`
- `0x18000bad4`
- `0x18000bc9c`
- `0x18000bdd4`
- `0x18000c588`
- `0x18000c874`
- `0x18000e214`
- `0x18000fd08`
- `0x180010284`
- `0x180010454`
- `0x1800108e4`
- `0x180010fd4`
- `0x180013ee0`
- `0x1800143f0`
- `0x1800175f4`
- `0x180019ac4`
- `0x180019b18`

## callees

- `0x180019a40`
- `0x180019e64`
- `0x18001a3bc`

## pseudocode

```c
__int64 __fastcall GetGeneric(__int64 a1, __int64 a2, unsigned __int16 a3)
{
  __int64 v5; // rdi
  unsigned int v6; // ebx
  __int16 v8; // [rsp+80h] [rbp+18h] BYREF

  v8 = 0;
  v5 = 3LL * a3;
  v6 = TTTableOffset(a1, (__int64)(&off_180021040)[3 * a3]);
  if ( !v6 )
    return 0;
  if ( (unsigned __int16)ReadGeneric(
                           a1,
                           a2,
                           (unsigned __int16)(&off_180021040)[v5 + 1],
                           (unsigned __int8 *)(&off_180021040)[v5 + 2],
                           v6,
                           &v8) )
    return 0;
  return v6;
}

```

## disassembly

```asm
0x180019a40  mov     rax, rsp
0x180019a43  push    rbx
0x180019a44  push    rbp
0x180019a45  push    rsi
0x180019a46  push    rdi
0x180019a47  push    r14
0x180019a49  push    r15
0x180019a4b  sub     rsp, 38h
0x180019a4f  mov     rbp, rdx
0x180019a52  lea     r15, off_180021040; "head"
0x180019a59  xor     r14d, r14d
0x180019a5c  mov     rsi, rcx
0x180019a5f  mov     [rax+18h], r14w
0x180019a64  movzx   eax, r8w
0x180019a68  lea     rdi, [rax+rax*2]
0x180019a6c  mov     rdx, [r15+rdi*8]
0x180019a70  call    TTTableOffset
0x180019a75  mov     ebx, eax
0x180019a77  test    eax, eax
0x180019a79  jz      short loc_180019AAD
0x180019a7b  mov     r9, [r15+rdi*8+10h]
0x180019a80  lea     rax, [rsp+68h+arg_10]
0x180019a88  movzx   r8d, word ptr [r15+rdi*8+8]
0x180019a8e  mov     rdx, rbp
0x180019a91  mov     [rsp+68h+var_40], rax
0x180019a96  mov     rcx, rsi
0x180019a99  mov     [rsp+68h+var_48], ebx
0x180019a9d  call    ReadGeneric
0x180019aa2  test    ax, ax
0x180019aa5  cmovnz  ebx, r14d
0x180019aa9  mov     eax, ebx
0x180019aab  jmp     short loc_180019AAF
0x180019aad  xor     eax, eax
0x180019aaf  add     rsp, 38h
0x180019ab3  pop     r15
0x180019ab5  pop     r14
0x180019ab7  pop     rdi
0x180019ab8  pop     rsi
0x180019ab9  pop     rbp
0x180019aba  pop     rbx
0x180019abb  retn
```
