# Smb1QueryProtocolInformation

- ea: `0x14000e778`
- end: `0x14000e81f`
- name: `Smb1QueryProtocolInformation`
- size: `167`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000e580`
- `0x140048b30`

## callees

- `0x14000e778`
- `0x1400169c0`

## pseudocode

```c
__int64 __fastcall Smb1QueryProtocolInformation(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  _WORD *v9; // rbx
  int *v10; // rdx
  int v11; // ecx

  if ( *a4 < 0x74u )
    return 3221225476LL;
  v9 = *(_WORD **)(a1 + 64);
  memset((void *)(a3 + 8), 0, 0x6Cu);
  *(_DWORD *)a3 = 7602178;
  v10 = (int *)(a3 + 16);
  *(_DWORD *)(a3 + 4) = 0x20000;
  v11 = 0;
  *(_WORD *)(a3 + 8) = *v9;
  *(_WORD *)(a3 + 10) = v9[1];
  *(_WORD *)(a3 + 12) = v9[2];
  if ( *(_BYTE *)(a1 + 505) )
  {
    v11 = 1;
    *v10 = 1;
  }
  if ( *(_BYTE *)(a2 + 253) )
  {
    v11 |= 0x20u;
    *v10 = v11;
  }
  if ( (*(_BYTE *)(a1 + 672) & 8) != 0 )
    *v10 = v11 | 0x10;
  *a4 = 116;
  return 0;
}

```

## disassembly

```asm
0x14000e778  push    rbx
0x14000e77a  push    rbp
0x14000e77b  push    rsi
0x14000e77c  push    rdi
0x14000e77d  push    r14
0x14000e77f  push    r15
0x14000e781  sub     rsp, 28h
0x14000e785  mov     r15d, 74h ; 't'
0x14000e78b  mov     rsi, r9
0x14000e78e  mov     rdi, r8
0x14000e791  mov     r14, rdx
0x14000e794  mov     rbp, rcx
0x14000e797  cmp     [r9], r15d
0x14000e79a  jnb     short loc_14000E7A3
0x14000e79c  mov     eax, 0C0000004h
0x14000e7a1  jmp     short loc_14000E811
0x14000e7a3  mov     rbx, [rcx+40h]
0x14000e7a7  xor     edx, edx; Val
0x14000e7a9  lea     rcx, [r8+8]; void *
0x14000e7ad  lea     r8d, [rdx+6Ch]; Size
0x14000e7b1  call    memset
0x14000e7b6  mov     dword ptr [rdi], 740002h
0x14000e7bc  lea     rdx, [rdi+10h]
0x14000e7c0  mov     dword ptr [rdi+4], 20000h
0x14000e7c7  xor     ecx, ecx
0x14000e7c9  movzx   eax, word ptr [rbx]
0x14000e7cc  mov     [rdi+8], ax
0x14000e7d0  movzx   eax, word ptr [rbx+2]
0x14000e7d4  mov     [rdi+0Ah], ax
0x14000e7d8  movzx   eax, word ptr [rbx+4]
0x14000e7dc  mov     [rdi+0Ch], ax
0x14000e7e0  cmp     [rbp+1F9h], cl
0x14000e7e6  jz      short loc_14000E7EF
0x14000e7e8  mov     ecx, 1
0x14000e7ed  mov     [rdx], ecx
0x14000e7ef  cmp     byte ptr [r14+0FDh], 0
0x14000e7f7  jz      short loc_14000E7FE
0x14000e7f9  or      ecx, 20h
0x14000e7fc  mov     [rdx], ecx
0x14000e7fe  test    byte ptr [rbp+2A0h], 8
0x14000e805  jz      short loc_14000E80C
0x14000e807  or      ecx, 10h
0x14000e80a  mov     [rdx], ecx
0x14000e80c  mov     [rsi], r15d
0x14000e80f  xor     eax, eax
0x14000e811  add     rsp, 28h
0x14000e815  pop     r15
0x14000e817  pop     r14
0x14000e819  pop     rdi
0x14000e81a  pop     rsi
0x14000e81b  pop     rbp
0x14000e81c  pop     rbx
0x14000e81d  retn
```
