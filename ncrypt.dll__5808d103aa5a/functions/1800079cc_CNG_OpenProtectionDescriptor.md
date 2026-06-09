# CNG_OpenProtectionDescriptor

- ea: `0x1800079cc`
- end: `0x180007acf`
- name: `CNG_OpenProtectionDescriptor`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000962c`

## callees

- `0x1800079cc`
- `0x180008da0`
- `0x18000d02c`

## string_xrefs

- `0x180007aa0`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\descriptor.c`

## pseudocode

```c
__int64 __fastcall CNG_OpenProtectionDescriptor(unsigned int *a1, char a2)
{
  unsigned __int64 i; // rbx
  unsigned int v5; // edi
  unsigned __int64 v7; // r14
  __int64 j; // rsi
  __int64 v9; // rdx
  __int64 v10; // r15
  int v11; // edx
  int v12; // r8d
  __int64 v13; // [rsp+70h] [rbp+8h] BYREF

  v13 = 0;
  for ( i = 0; i < *a1; ++i )
  {
    v7 = 0;
    for ( j = 32 * i; ; *(_DWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 1) + j + 8) + v10 + 24) = 1 )
    {
      v9 = *((_QWORD *)a1 + 1);
      if ( v7 >= *(unsigned int *)(j + v9) )
        break;
      v10 = 32 * v7;
      v5 = NCryptOpenKeyProtector(&v13, *(const WCHAR **)(*(_QWORD *)(j + v9 + 8) + 32 * v7), 0);
      if ( v5 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v11,
            v12,
            (unsigned int)"Status",
            v5,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
            104);
        if ( (a2 & 1) == 0 )
          return v5;
      }
      ++v7;
      *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 1) + j + 8) + v10 + 16) = v13;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800079cc  mov     [rsp+arg_8], rbx
0x1800079d1  mov     [rsp+arg_10], rbp
0x1800079d6  push    rsi
0x1800079d7  push    rdi
0x1800079d8  push    r12
0x1800079da  push    r14
0x1800079dc  push    r15
0x1800079de  sub     rsp, 40h
0x1800079e2  mov     r12d, edx
0x1800079e5  mov     [rsp+68h+arg_0], 0
0x1800079ee  mov     rbp, rcx
0x1800079f1  xor     ebx, ebx
0x1800079f3  mov     eax, [rbp+0]
0x1800079f6  cmp     rbx, rax
0x1800079f9  jb      short loc_180007A18
0x1800079fb  xor     edi, edi
0x1800079fd  lea     r11, [rsp+68h+var_28]
0x180007a02  mov     eax, edi
0x180007a04  mov     rbx, [r11+38h]
0x180007a08  mov     rbp, [r11+40h]
0x180007a0c  mov     rsp, r11
0x180007a0f  pop     r15
0x180007a11  pop     r14
0x180007a13  pop     r12
0x180007a15  pop     rdi
0x180007a16  pop     rsi
0x180007a17  retn
0x180007a18  xor     r14d, r14d
0x180007a1b  mov     rsi, rbx
0x180007a1e  shl     rsi, 5
0x180007a22  mov     rdx, [rbp+8]
0x180007a26  mov     eax, [rsi+rdx]
0x180007a29  cmp     r14, rax
0x180007a2c  jnb     short loc_180007A7B
0x180007a2e  mov     rdx, [rsi+rdx+8]
0x180007a33  lea     rcx, [rsp+68h+arg_0]
0x180007a38  mov     r15, r14
0x180007a3b  xor     r8d, r8d
0x180007a3e  shl     r15, 5
0x180007a42  mov     rdx, [rdx+r15]
0x180007a46  call    NCryptOpenKeyProtector
0x180007a4b  mov     edi, eax
0x180007a4d  test    eax, eax
0x180007a4f  jnz     short loc_180007A83
0x180007a51  mov     rax, [rbp+8]
0x180007a55  inc     r14
0x180007a58  mov     rcx, [rax+rsi+8]
0x180007a5d  mov     rax, [rsp+68h+arg_0]
0x180007a62  mov     [rcx+r15+10h], rax
0x180007a67  mov     rax, [rbp+8]
0x180007a6b  mov     rcx, [rax+rsi+8]
0x180007a70  mov     dword ptr [rcx+r15+18h], 1
0x180007a79  jmp     short loc_180007A22
0x180007a7b  inc     rbx
0x180007a7e  jmp     loc_1800079F3
0x180007a83  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a8a  lea     rax, WPP_GLOBAL_Control
0x180007a91  cmp     rcx, rax
0x180007a94  jz      short loc_180007AC4
0x180007a96  test    byte ptr [rcx+1Ch], 1
0x180007a9a  jz      short loc_180007AC4
0x180007a9c  mov     rcx, [rcx+10h]
0x180007aa0  lea     rax, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007aa7  mov     [rsp+68h+var_38], 68h ; 'h'
0x180007aaf  lea     r9, aStatus; "Status"
0x180007ab6  mov     [rsp+68h+var_40], rax
0x180007abb  mov     [rsp+68h+var_48], edi
0x180007abf  call    WPP_SF_sDsd
0x180007ac4  test    r12b, 1
0x180007ac8  jnz     short loc_180007A51
0x180007aca  jmp     loc_1800079FD
```
