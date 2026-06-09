# ReadStringDelimited

- ea: `0x180037f90`
- end: `0x180038119`
- name: `ReadStringDelimited`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800382f0`

## callees

- `0x180007f00`
- `0x18001d300`
- `0x18001d350`
- `0x180037d1c`
- `0x180037f90`
- `0x18007d030`

## pseudocode

```c
__int64 __fastcall ReadStringDelimited(
        char a1,
        unsigned __int16 **a2,
        wint_t *a3,
        _DWORD *a4,
        void **a5,
        int a6,
        FILE *Stream,
        unsigned __int64 a8,
        _DWORD *a9)
{
  _BYTE *v13; // rax
  _BYTE *v14; // rdi
  unsigned __int16 *v16; // rcx
  unsigned __int16 *v17; // r9
  unsigned __int16 v18; // ax
  unsigned __int16 *v19; // r9
  unsigned __int16 v20; // r8
  unsigned __int16 v21; // cx
  unsigned __int16 v22; // r10
  unsigned __int16 v23; // ax
  unsigned int String; // ebx

  v13 = malloc(0x2000u);
  v14 = v13;
  if ( v13 )
  {
    memset_thunk_772440563353939046(v13, 0, 0x2000u);
    v16 = *a2;
    v17 = *a2 + 1;
    *a2 = v17;
    if ( *v17 == 94 )
    {
      v18 = v17[1];
      a1 |= 8u;
    }
    else
    {
      v18 = *v17;
    }
    if ( *v17 != 94 )
      v17 = v16;
    v19 = v17 + 1;
    if ( v18 != 93 )
      goto LABEL_18;
    v20 = 93;
    v14[11] = 32;
    ++v19;
    while ( 1 )
    {
      v23 = *v19;
      if ( *v19 == 93 )
        break;
      ++v19;
      if ( v23 == 45 && v20 && (v21 = *v19, *v19 != 93) )
      {
        ++v19;
        v22 = v21;
        if ( v20 >= v21 )
        {
          v22 = v20;
          v20 = v21;
        }
        while ( v20 <= v22 )
        {
          v14[(unsigned __int64)v20 >> 3] |= 1 << (v20 & 7);
          ++v20;
        }
LABEL_18:
        v20 = 0;
      }
      else
      {
        v20 = v23;
        v14[(unsigned __int64)v23 >> 3] |= 1 << (v23 & 7);
      }
    }
    *a2 = v19;
    String = ReadString(a1, (__int64)v14, a3, a4, a5, a6, Stream, a8, a9);
    free(v14);
    return String;
  }
  else
  {
    *errno() = 12;
    return 12;
  }
}

```

## disassembly

```asm
0x180037f90  push    rbx
0x180037f92  push    rbp
0x180037f93  push    rsi
0x180037f94  push    rdi
0x180037f95  push    r14
0x180037f97  push    r15
0x180037f99  sub     rsp, 58h
0x180037f9d  mov     ebx, ecx
0x180037f9f  mov     rbp, r9
0x180037fa2  mov     ecx, 2000h; Size
0x180037fa7  mov     r14, r8
0x180037faa  mov     rsi, rdx
0x180037fad  call    malloc
0x180037fb2  xor     r15d, r15d
0x180037fb5  mov     rdi, rax
0x180037fb8  test    rax, rax
0x180037fbb  jnz     short loc_180037FCE
0x180037fbd  call    _errno
0x180037fc2  lea     ecx, [rdi+0Ch]
0x180037fc5  mov     [rax], ecx
0x180037fc7  mov     eax, ecx
0x180037fc9  jmp     loc_18003810C
0x180037fce  xor     edx, edx; Val
0x180037fd0  mov     r8d, 2000h; Size
0x180037fd6  mov     rcx, rdi; void *
0x180037fd9  call    memset$thunk$772440563353939046
0x180037fde  mov     rcx, [rsi]
0x180037fe1  mov     edx, 5Eh ; '^'
0x180037fe6  lea     r9, [rcx+2]
0x180037fea  mov     [rsi], r9
0x180037fed  cmp     dx, [r9]
0x180037ff1  jnz     short loc_180037FFD
0x180037ff3  movzx   eax, word ptr [r9+2]
0x180037ff8  or      ebx, 8
0x180037ffb  jmp     short loc_180038001
0x180037ffd  movzx   eax, word ptr [r9]
0x180038001  cmp     dx, [r9]
0x180038005  mov     r11d, 5Dh ; ']'
0x18003800b  cmovnz  r9, rcx
0x18003800f  add     r9, 2
0x180038013  cmp     r11w, ax
0x180038017  jnz     short loc_180038080
0x180038019  movzx   r8d, r11w
0x18003801d  mov     byte ptr [rdi+0Bh], 20h ; ' '
0x180038021  add     r9, 2
0x180038025  jmp     short loc_1800380A0
0x180038027  add     r9, 2
0x18003802b  mov     ecx, 2Dh ; '-'
0x180038030  cmp     cx, ax
0x180038033  jnz     short loc_180038085
0x180038035  test    r8w, r8w
0x180038039  jz      short loc_180038085
0x18003803b  movzx   ecx, word ptr [r9]
0x18003803f  cmp     r11w, cx
0x180038043  jz      short loc_180038085
0x180038045  add     r9, 2
0x180038049  movzx   r10d, cx
0x18003804d  cmp     r8w, cx
0x180038051  cmovnb  r10w, r8w
0x180038056  cmovnb  r8w, cx
0x18003805b  jmp     short loc_18003807A
0x18003805d  movzx   edx, r8w
0x180038061  shr     rdx, 3
0x180038065  movzx   eax, r8w
0x180038069  and     eax, 7
0x18003806c  movsx   ecx, byte ptr [rdx+rdi]
0x180038070  bts     ecx, eax
0x180038073  mov     [rdx+rdi], cl
0x180038076  inc     r8w
0x18003807a  cmp     r8w, r10w
0x18003807e  jbe     short loc_18003805D
0x180038080  mov     r8d, r15d
0x180038083  jmp     short loc_1800380A0
0x180038085  movzx   edx, ax
0x180038088  movzx   r8d, ax
0x18003808c  shr     rdx, 3
0x180038090  movzx   eax, ax
0x180038093  and     eax, 7
0x180038096  movsx   ecx, byte ptr [rdx+rdi]
0x18003809a  bts     ecx, eax
0x18003809d  mov     [rdx+rdi], cl
0x1800380a0  movzx   eax, word ptr [r9]
0x1800380a4  cmp     r11w, ax
0x1800380a8  jnz     loc_180038027
0x1800380ae  mov     rax, [rsp+88h+arg_40]
0x1800380b6  mov     r8, r14; int
0x1800380b9  mov     [rsp+88h+var_48], rax; __int64
0x1800380be  mov     rdx, rdi; int
0x1800380c1  mov     rax, [rsp+88h+arg_38]
0x1800380c9  mov     ecx, ebx; int
0x1800380cb  mov     [rsp+88h+var_50], rax; __int64
0x1800380d0  mov     rax, [rsp+88h+arg_30]
0x1800380d8  mov     [rsp+88h+Stream], rax; Stream
0x1800380dd  mov     eax, [rsp+88h+arg_28]
0x1800380e4  mov     [rsp+88h+var_60], eax; int
0x1800380e8  mov     rax, [rsp+88h+arg_20]
0x1800380f0  mov     [rsi], r9
0x1800380f3  mov     r9, rbp; int
0x1800380f6  mov     [rsp+88h+var_68], rax; __int64
0x1800380fb  call    ReadString
0x180038100  mov     rcx, rdi; Block
0x180038103  mov     ebx, eax
0x180038105  call    free
0x18003810a  mov     eax, ebx
0x18003810c  add     rsp, 58h
0x180038110  pop     r15
0x180038112  pop     r14
0x180038114  pop     rdi
0x180038115  pop     rsi
0x180038116  pop     rbp
0x180038117  pop     rbx
0x180038118  retn
```
