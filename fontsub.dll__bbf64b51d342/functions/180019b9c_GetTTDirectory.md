# GetTTDirectory

- ea: `0x180019b9c`
- end: `0x180019bf9`
- name: `GetTTDirectory`
- size: `93`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x1800087e8`
- `0x18000e34c`
- `0x180013ee0`
- `0x1800198f8`
- `0x180019e04`
- `0x180019e64`
- `0x180019ec0`
- `0x180019f90`

## callees

- `0x180019b9c`
- `0x180019d28`
- `0x18001a3bc`

## pseudocode

```c
__int64 __fastcall GetTTDirectory(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // ebx
  __int16 v7; // [rsp+78h] [rbp+20h] BYREF

  v7 = 0;
  v5 = TTDirectoryEntryOffset();
  if ( v5 - 1 > 0xFFFFFFFD
    || (unsigned __int16)ReadGeneric(a1, a3, 0x10u, (unsigned __int8 *)&DIRECTORY_CONTROL, v5, &v7) )
  {
    return 0;
  }
  else
  {
    return v5;
  }
}

```

## disassembly

```asm
0x180019b9c  push    rbx
0x180019b9e  push    rbp
0x180019b9f  push    rsi
0x180019ba0  push    rdi
0x180019ba1  sub     rsp, 38h
0x180019ba5  xor     ebp, ebp
0x180019ba7  mov     rsi, r8
0x180019baa  mov     [rsp+58h+arg_18], bp
0x180019baf  mov     rdi, rcx
0x180019bb2  call    TTDirectoryEntryOffset
0x180019bb7  mov     ebx, eax
0x180019bb9  lea     edx, [rax-1]
0x180019bbc  cmp     edx, 0FFFFFFFDh
0x180019bbf  ja      short loc_180019BEE
0x180019bc1  lea     rax, [rsp+58h+arg_18]
0x180019bc6  mov     rdx, rsi
0x180019bc9  mov     [rsp+58h+var_30], rax
0x180019bce  lea     r8d, [rbp+10h]
0x180019bd2  lea     r9, DIRECTORY_CONTROL
0x180019bd9  mov     [rsp+58h+var_38], ebx
0x180019bdd  mov     rcx, rdi
0x180019be0  call    ReadGeneric
0x180019be5  test    ax, ax
0x180019be8  jnz     short loc_180019BEE
0x180019bea  mov     eax, ebx
0x180019bec  jmp     short loc_180019BF0
0x180019bee  xor     eax, eax
0x180019bf0  add     rsp, 38h
0x180019bf4  pop     rdi
0x180019bf5  pop     rsi
0x180019bf6  pop     rbp
0x180019bf7  pop     rbx
0x180019bf8  retn
```
