# _CopyTokenBinding(uchar *,ulong *,ulong,TOKENBINDING_IDENTIFIER *,ulong *,TOKENBINDING_TYPE *,uchar *)

- ea: `0x18000ffa4`
- end: `0x1800100bf`
- name: `?_CopyTokenBinding@@YAJPEAEPEAKKPEAUTOKENBINDING_IDENTIFIER@@1PEAW4TOKENBINDING_TYPE@@0@Z`
- size: `283`
- prototype: `int(unsigned __int8 *, unsigned int *, unsigned int, struct TOKENBINDING_IDENTIFIER *, unsigned int *, enum TOKENBINDING_TYPE *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800237b0`

## callees

- `0x18000ffa4`
- `0x180010a00`

## pseudocode

```c
__int64 __fastcall _CopyTokenBinding(
        unsigned __int8 *a1,
        unsigned int *a2,
        __int64 a3,
        struct TOKENBINDING_IDENTIFIER *a4,
        unsigned int *a5,
        enum TOKENBINDING_TYPE *a6,
        unsigned __int8 *a7)
{
  __int64 v7; // rax
  unsigned int v8; // esi
  int v11; // r10d
  unsigned __int8 *v12; // rbp
  int v13; // ecx
  __int64 v14; // rdx
  int v15; // ecx
  int v16; // ebx
  __int64 v17; // rbx
  int v18; // ebx
  int v19; // r8d
  size_t v20; // r8
  int v21; // r9d

  v7 = *a2;
  v8 = 0;
  v11 = a1[v7];
  v12 = &a1[(unsigned int)(v7 + 1)];
  *a7 = 0;
  v13 = *v12;
  v14 = (unsigned int)(v7 + 4);
  *a2 = v14;
  if ( !v13 || (v15 = v13 - 1) == 0 )
  {
    v19 = (unsigned __int16)(*(_WORD *)&a1[v14] << 8) | a1[v14 + 1];
    v18 = v19 + a1[(unsigned int)(v19 + v7 + 6)] + 3;
    goto LABEL_9;
  }
  if ( v15 == 1 )
  {
    v18 = a1[v14] + 1;
LABEL_9:
    v17 = (unsigned int)(v14 + v18);
    v20 = (unsigned int)(v17 - (v7 + 1));
    *(_DWORD *)a6 = v11;
    *a5 = v20;
    memmove(a4, v12, v20);
    goto LABEL_10;
  }
  if ( (_BYTE)v11 == 1 )
  {
    v16 = (unsigned __int16)(*(_WORD *)&a1[(unsigned int)(v7 + 2)] << 8) | a1[(unsigned int)(v7 + 2) + 1];
    *a7 = 1;
    v17 = (unsigned int)(v14 + v16);
LABEL_10:
    v21 = a1[v17 + 1] | (unsigned __int16)(*(_WORD *)&a1[v17] << 8);
    *a2 = v17
        + v21
        + ((unsigned __int16)(*(_WORD *)&a1[(unsigned int)(v21 + v17 + 2)] << 8) | a1[(unsigned int)(v21 + v17 + 2) + 1])
        + 4;
    return v8;
  }
  return (unsigned int)-2146893816;
}

```

## disassembly

```asm
0x18000ffa4  push    rbx
0x18000ffa6  push    rbp
0x18000ffa7  push    rsi
0x18000ffa8  push    rdi
0x18000ffa9  push    r14
0x18000ffab  push    r15
0x18000ffad  sub     rsp, 28h
0x18000ffb1  mov     eax, [rdx]
0x18000ffb3  xor     esi, esi
0x18000ffb5  mov     r11, [rsp+58h+arg_30]
0x18000ffbd  mov     r14, rdx
0x18000ffc0  mov     rdi, rcx
0x18000ffc3  movzx   r10d, byte ptr [rax+rcx]
0x18000ffc8  lea     r8d, [rax+1]
0x18000ffcc  mov     ebp, r8d
0x18000ffcf  mov     r15d, r8d
0x18000ffd2  add     rbp, rcx
0x18000ffd5  mov     [r11], sil
0x18000ffd8  inc     r8d
0x18000ffdb  movzx   ecx, byte ptr [rbp+0]
0x18000ffdf  lea     edx, [r8+2]
0x18000ffe3  mov     [r14], edx
0x18000ffe6  test    ecx, ecx
0x18000ffe8  jz      short loc_180010027
0x18000ffea  sub     ecx, 1
0x18000ffed  jz      short loc_180010027
0x18000ffef  cmp     ecx, 1
0x18000fff2  jz      short loc_18001001F
0x18000fff4  cmp     r10b, 1
0x18000fff8  jnz     short loc_180010015
0x18000fffa  movzx   eax, word ptr [r8+rdi]
0x18000ffff  movzx   ebx, byte ptr [r8+rdi+1]
0x180010005  shl     ax, 8
0x180010009  movzx   eax, ax
0x18001000c  or      ebx, eax
0x18001000e  mov     [r11], r10b
0x180010011  add     ebx, edx
0x180010013  jmp     short loc_180010074
0x180010015  mov     esi, 80090008h
0x18001001a  jmp     loc_1800100AF
0x18001001f  movzx   ebx, byte ptr [rdx+rdi]
0x180010023  inc     ebx
0x180010025  jmp     short loc_18001004B
0x180010027  movzx   eax, word ptr [rdx+rdi]
0x18001002b  movzx   r8d, byte ptr [rdx+rdi+1]
0x180010031  shl     ax, 8
0x180010035  movzx   eax, ax
0x180010038  or      r8d, eax
0x18001003b  lea     eax, [rdx+2]
0x18001003e  add     eax, r8d
0x180010041  movzx   ebx, byte ptr [rax+rdi]
0x180010045  add     ebx, 3
0x180010048  add     ebx, r8d
0x18001004b  mov     rax, [rsp+58h+arg_28]
0x180010053  add     ebx, edx
0x180010055  mov     r8d, ebx
0x180010058  mov     rdx, rbp; Src
0x18001005b  sub     r8d, r15d; Size
0x18001005e  mov     rcx, r9; void *
0x180010061  mov     [rax], r10d
0x180010064  mov     rax, [rsp+58h+arg_20]
0x18001006c  mov     [rax], r8d
0x18001006f  call    memmove
0x180010074  movzx   eax, word ptr [rbx+rdi]
0x180010078  lea     ecx, [rbx+2]
0x18001007b  shl     ax, 8
0x18001007f  movzx   r9d, ax
0x180010083  movzx   eax, byte ptr [rbx+rdi+1]
0x180010088  or      r9d, eax
0x18001008b  add     ecx, r9d
0x18001008e  mov     edx, ecx
0x180010090  movzx   ecx, word ptr [rcx+rdi]
0x180010094  shl     cx, 8
0x180010098  movzx   r8d, cx
0x18001009c  movzx   ecx, byte ptr [rdx+rdi+1]
0x1800100a1  or      ecx, r8d
0x1800100a4  add     ecx, 4
0x1800100a7  add     ecx, r9d
0x1800100aa  add     ecx, ebx
0x1800100ac  mov     [r14], ecx
0x1800100af  mov     eax, esi
0x1800100b1  add     rsp, 28h
0x1800100b5  pop     r15
0x1800100b7  pop     r14
0x1800100b9  pop     rdi
0x1800100ba  pop     rsi
0x1800100bb  pop     rbp
0x1800100bc  pop     rbx
0x1800100bd  retn
```
