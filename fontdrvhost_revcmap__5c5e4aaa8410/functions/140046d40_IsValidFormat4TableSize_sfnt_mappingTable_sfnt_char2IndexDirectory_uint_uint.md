# IsValidFormat4TableSize(sfnt_mappingTable *,sfnt_char2IndexDirectory *,uint,uint)

- ea: `0x140046d40`
- end: `0x140046ea4`
- name: `?IsValidFormat4TableSize@@YAHPEAUsfnt_mappingTable@@PEAUsfnt_char2IndexDirectory@@II@Z`
- size: `356`
- prototype: `__int64 __fastcall(struct sfnt_mappingTable *, struct sfnt_char2IndexDirectory *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140046b40`
- `0x140091ec8`

## callees

- `0x140046d40`

## pseudocode

```c
__int64 __fastcall IsValidFormat4TableSize(
        struct sfnt_mappingTable *a1,
        struct sfnt_char2IndexDirectory *a2,
        unsigned int a3,
        unsigned int a4)
{
  __int64 v5; // rbx
  unsigned __int16 v6; // cx
  __int64 v7; // r8
  int v8; // r14d
  unsigned __int8 *v9; // r11
  unsigned int v10; // ebp
  unsigned __int8 *v11; // r10
  unsigned __int16 *v12; // rbx
  unsigned __int16 v13; // r9
  int v14; // r15d
  unsigned __int16 v15; // si

  v5 = a3;
  if ( _byteswap_ushort(*(_WORD *)a1) != 4 )
    return 0;
  if ( a4 - a3 < 8 )
    return 0;
  v6 = _byteswap_ushort(*((_WORD *)a1 + 3));
  if ( !v6 )
    return 0;
  if ( (v6 & 1) != 0 )
    return 0;
  v7 = v6 >> 1;
  if ( (unsigned int)v5 > -17 - 8 * (int)v7 )
    return 0;
  v8 = 6 * v7 + v5 + 16;
  if ( 2 * (int)v7 + v8 > a4 )
    return 0;
  v9 = (unsigned __int8 *)a2 + v5 + 14;
  v10 = 0;
  v11 = (unsigned __int8 *)a2 + v5 + (unsigned int)(2 * v7) + 16;
  v12 = (unsigned __int16 *)((char *)a2 + (unsigned int)v5 + (unsigned int)(6 * v7) + 16);
  if ( *(_WORD *)&v11[2 * v7 - 2] == 0xFFFF && (unsigned __int16)v7 > 1u )
    LOWORD(v7) = v7 - 1;
  v13 = 0;
  while ( v13 < (unsigned __int16)v7 )
  {
    v14 = v10 + 1;
    v15 = _byteswap_ushort(*v12);
    if ( (v11[1] | (*v11 << 8)) >= v10 )
      v14 = v11[1] | (*v11 << 8);
    v10 = (*v9 << 8) | v9[1];
    if ( v15 && v8 + v15 + 2 + 2 * (v10 + v13 - v14) > a4 )
      return 0;
    ++v13;
    v11 += 2;
    v9 += 2;
    ++v12;
  }
  return 1;
}

```

## disassembly

```asm
0x140046d40  push    rbx
0x140046d42  push    rbp
0x140046d43  push    rsi
0x140046d44  push    rdi
0x140046d45  push    r12
0x140046d47  push    r13
0x140046d49  push    r14
0x140046d4b  push    r15
0x140046d4d  movzx   r10d, byte ptr [rcx]
0x140046d51  mov     edi, r9d
0x140046d54  movzx   eax, byte ptr [rcx+1]
0x140046d58  mov     rsi, rdx
0x140046d5b  shl     r10w, 8
0x140046d60  mov     r11, rcx
0x140046d63  or      r10w, ax
0x140046d67  mov     ebx, r8d
0x140046d6a  cmp     r10w, 4
0x140046d6f  jnz     loc_140046E90
0x140046d75  mov     eax, r9d
0x140046d78  sub     eax, ebx
0x140046d7a  cmp     eax, 8
0x140046d7d  jb      loc_140046E90
0x140046d83  movzx   eax, byte ptr [r11+6]
0x140046d88  movzx   ecx, byte ptr [rcx+7]
0x140046d8c  shl     ax, 8
0x140046d90  or      cx, ax
0x140046d93  jz      loc_140046E90
0x140046d99  mov     r12d, 1
0x140046d9f  test    r12b, cl
0x140046da2  jnz     loc_140046E90
0x140046da8  shr     cx, 1
0x140046dab  movzx   r8d, cx
0x140046daf  mov     ecx, 0FFFFFFEFh
0x140046db4  lea     eax, ds:0[r8*8]
0x140046dbc  sub     ecx, eax
0x140046dbe  cmp     ebx, ecx
0x140046dc0  ja      loc_140046E90
0x140046dc6  lea     eax, [r8+r8*2]
0x140046dca  lea     edx, [rax+rax]
0x140046dcd  lea     r14d, [rbx+10h]
0x140046dd1  add     r14d, edx
0x140046dd4  lea     r9d, [r8+r8]
0x140046dd8  lea     eax, [r9+r14]
0x140046ddc  cmp     eax, edi
0x140046dde  ja      loc_140046E90
0x140046de4  mov     ecx, ebx
0x140046de6  mov     r10d, r9d
0x140046de9  add     rcx, 10h
0x140046ded  lea     r11, [rsi+0Eh]
0x140046df1  add     r11, rbx
0x140046df4  xor     r13d, r13d
0x140046df7  add     rbx, 10h
0x140046dfb  mov     ebp, r13d
0x140046dfe  add     r10, rbx
0x140046e01  mov     ebx, edx
0x140046e03  add     rbx, rcx
0x140046e06  add     r10, rsi
0x140046e09  add     rbx, rsi
0x140046e0c  mov     ecx, 0FFFFh
0x140046e11  cmp     [r10+r8*2-2], cx
0x140046e17  jnz     short loc_140046E23
0x140046e19  cmp     r8w, r12w
0x140046e1d  jbe     short loc_140046E23
0x140046e1f  sub     r8w, r12w
0x140046e23  mov     r9d, r13d
0x140046e26  cmp     r9w, r8w
0x140046e2a  jnb     short loc_140046E94
0x140046e2c  movzx   eax, byte ptr [r10+1]
0x140046e31  lea     r15d, [rbp+1]
0x140046e35  movzx   ecx, byte ptr [r10]
0x140046e39  movzx   esi, byte ptr [rbx]
0x140046e3c  shl     ecx, 8
0x140046e3f  or      ecx, eax
0x140046e41  shl     si, 8
0x140046e45  movzx   eax, byte ptr [rbx+1]
0x140046e49  or      si, ax
0x140046e4c  movzx   eax, byte ptr [r11]
0x140046e50  cmp     ecx, ebp
0x140046e52  movzx   ebp, byte ptr [r11+1]
0x140046e57  cmovnb  r15d, ecx
0x140046e5b  shl     eax, 8
0x140046e5e  or      ebp, eax
0x140046e60  test    si, si
0x140046e63  jnz     short loc_140046E77
0x140046e65  add     r9w, r12w
0x140046e69  add     r10, 2
0x140046e6d  add     r11, 2
0x140046e71  add     rbx, 2
0x140046e75  jmp     short loc_140046E26
0x140046e77  movzx   edx, r9w
0x140046e7b  sub     edx, r15d
0x140046e7e  movzx   eax, si
0x140046e81  add     eax, 2
0x140046e84  add     edx, ebp
0x140046e86  add     eax, r14d
0x140046e89  lea     eax, [rax+rdx*2]
0x140046e8c  cmp     eax, edi
0x140046e8e  jbe     short loc_140046E65
0x140046e90  xor     eax, eax
0x140046e92  jmp     short loc_140046E97
0x140046e94  mov     eax, r12d
0x140046e97  pop     r15
0x140046e99  pop     r14
0x140046e9b  pop     r13
0x140046e9d  pop     r12
0x140046e9f  pop     rdi
0x140046ea0  pop     rsi
0x140046ea1  pop     rbp
0x140046ea2  pop     rbx
0x140046ea3  retn
```
