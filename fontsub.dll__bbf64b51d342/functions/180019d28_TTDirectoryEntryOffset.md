# TTDirectoryEntryOffset

- ea: `0x180019d28`
- end: `0x180019dfe`
- name: `TTDirectoryEntryOffset`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180019b9c`

## callees

- `0x180019d28`
- `0x18001a3bc`
- `0x18001ac90`

## pseudocode

```c
__int64 __fastcall TTDirectoryEntryOffset(__int64 a1, _DWORD *a2)
{
  unsigned int v2; // edi
  unsigned int v5; // ebx
  unsigned __int16 i; // di
  unsigned __int16 v8; // [rsp+30h] [rbp-38h] BYREF
  __int64 v9; // [rsp+38h] [rbp-30h] BYREF
  int v10; // [rsp+40h] [rbp-28h]
  __int128 v11; // [rsp+48h] [rbp-20h] BYREF

  v2 = *(_DWORD *)(a1 + 12);
  v9 = 0;
  v10 = 0;
  v8 = 0;
  v11 = 0;
  if ( (unsigned __int16)ReadGeneric(a1, (__int64)&v9, 0xCu, (unsigned __int8 *)&OFFSET_TABLE_CONTROL, v2, &v8) )
    return 0xFFFFFFFFLL;
  v5 = v2 + v8;
  for ( i = 0; i < WORD2(v9); ++i )
  {
    if ( (unsigned __int16)ReadGeneric(
                             a1,
                             (__int64)&v11,
                             0x10u,
                             (unsigned __int8 *)&DIRECTORY_NO_XLATE_CONTROL,
                             v5,
                             &v8) )
      return 0xFFFFFFFFLL;
    if ( *a2 == (_DWORD)v11 )
      return v5;
    v5 += v8;
  }
  return 0;
}

```

## disassembly

```asm
0x180019d28  push    rbp
0x180019d2a  push    rbx
0x180019d2b  push    rsi
0x180019d2c  push    rdi
0x180019d2d  push    r14
0x180019d2f  push    r15
0x180019d31  mov     rbp, rsp
0x180019d34  sub     rsp, 68h
0x180019d38  mov     rax, cs:__security_cookie
0x180019d3f  xor     rax, rsp
0x180019d42  mov     [rbp+var_10], rax
0x180019d46  mov     edi, [rcx+0Ch]
0x180019d49  lea     r9, OFFSET_TABLE_CONTROL
0x180019d50  xor     eax, eax
0x180019d52  xor     r15d, r15d
0x180019d55  mov     [rbp+var_30], rax
0x180019d59  mov     r14, rdx
0x180019d5c  mov     [rbp+var_28], eax
0x180019d5f  lea     rdx, [rbp+var_30]
0x180019d63  lea     rax, [rbp+var_38]
0x180019d67  mov     [rbp+var_38], r15w
0x180019d6c  xorps   xmm0, xmm0
0x180019d6f  mov     [rsp+68h+var_40], rax
0x180019d74  lea     r8d, [r15+0Ch]
0x180019d78  mov     [rsp+68h+var_48], edi
0x180019d7c  mov     rsi, rcx
0x180019d7f  movups  [rbp+var_20], xmm0
0x180019d83  call    ReadGeneric
0x180019d88  test    ax, ax
0x180019d8b  jnz     short loc_180019DE2
0x180019d8d  movzx   ebx, [rbp+var_38]
0x180019d91  add     ebx, edi
0x180019d93  mov     edi, r15d
0x180019d96  cmp     di, word ptr [rbp+var_30+4]
0x180019d9a  jnb     short loc_180019DDE
0x180019d9c  lea     rax, [rbp+var_38]
0x180019da0  mov     r8d, 10h
0x180019da6  mov     [rsp+68h+var_40], rax
0x180019dab  lea     r9, DIRECTORY_NO_XLATE_CONTROL
0x180019db2  lea     rdx, [rbp+var_20]
0x180019db6  mov     [rsp+68h+var_48], ebx
0x180019dba  mov     rcx, rsi
0x180019dbd  call    ReadGeneric
0x180019dc2  test    ax, ax
0x180019dc5  jnz     short loc_180019DE2
0x180019dc7  mov     eax, dword ptr [rbp+var_20]
0x180019dca  cmp     [r14], eax
0x180019dcd  jz      short loc_180019DDA
0x180019dcf  movzx   eax, [rbp+var_38]
0x180019dd3  add     ebx, eax
0x180019dd5  inc     di
0x180019dd8  jmp     short loc_180019D96
0x180019dda  mov     eax, ebx
0x180019ddc  jmp     short loc_180019DE5
0x180019dde  xor     eax, eax
0x180019de0  jmp     short loc_180019DE5
0x180019de2  or      eax, 0FFFFFFFFh
0x180019de5  mov     rcx, [rbp+var_10]
0x180019de9  xor     rcx, rsp; StackCookie
0x180019dec  call    __security_check_cookie
0x180019df1  add     rsp, 68h
0x180019df5  pop     r15
0x180019df7  pop     r14
0x180019df9  pop     rdi
0x180019dfa  pop     rsi
0x180019dfb  pop     rbx
0x180019dfc  pop     rbp
0x180019dfd  retn
```
