# ReadStringDelimited_7

- ea: `0x18005aa28`
- end: `0x18005abb1`
- name: `ReadStringDelimited_7`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18005abc0`

## callees

- `0x180007f00`
- `0x18001d300`
- `0x18001d568`
- `0x18005a838`
- `0x18005aa28`
- `0x18007d030`

## pseudocode

```c
__int64 __fastcall ReadStringDelimited_7(
        char a1,
        unsigned __int16 **a2,
        wint_t *a3,
        _DWORD *a4,
        char **SizeConverted,
        int a6,
        FILE *Stream,
        int a8,
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
  unsigned int String_7; // ebx

  v13 = (_BYTE *)malloc_crt(0x2000u);
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
    String_7 = ReadString_7(a1, (__int64)v14, a3, a4, SizeConverted, a6, Stream, a8, a9);
    free(v14);
    return String_7;
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
0x18005aa28  push    rbx
0x18005aa2a  push    rbp
0x18005aa2b  push    rsi
0x18005aa2c  push    rdi
0x18005aa2d  push    r14
0x18005aa2f  push    r15
0x18005aa31  sub     rsp, 58h
0x18005aa35  mov     ebx, ecx
0x18005aa37  mov     rbp, r9
0x18005aa3a  mov     ecx, 2000h; Size
0x18005aa3f  mov     r14, r8
0x18005aa42  mov     rsi, rdx
0x18005aa45  call    _malloc_crt
0x18005aa4a  xor     r15d, r15d
0x18005aa4d  mov     rdi, rax
0x18005aa50  test    rax, rax
0x18005aa53  jnz     short loc_18005AA66
0x18005aa55  call    _errno
0x18005aa5a  lea     ecx, [rdi+0Ch]
0x18005aa5d  mov     [rax], ecx
0x18005aa5f  mov     eax, ecx
0x18005aa61  jmp     loc_18005ABA4
0x18005aa66  xor     edx, edx; Val
0x18005aa68  mov     r8d, 2000h; Size
0x18005aa6e  mov     rcx, rdi; void *
0x18005aa71  call    memset$thunk$772440563353939046
0x18005aa76  mov     rcx, [rsi]
0x18005aa79  mov     edx, 5Eh ; '^'
0x18005aa7e  lea     r9, [rcx+2]
0x18005aa82  mov     [rsi], r9
0x18005aa85  cmp     dx, [r9]
0x18005aa89  jnz     short loc_18005AA95
0x18005aa8b  movzx   eax, word ptr [r9+2]
0x18005aa90  or      ebx, 8
0x18005aa93  jmp     short loc_18005AA99
0x18005aa95  movzx   eax, word ptr [r9]
0x18005aa99  cmp     dx, [r9]
0x18005aa9d  mov     r11d, 5Dh ; ']'
0x18005aaa3  cmovnz  r9, rcx
0x18005aaa7  add     r9, 2
0x18005aaab  cmp     r11w, ax
0x18005aaaf  jnz     short loc_18005AB18
0x18005aab1  movzx   r8d, r11w
0x18005aab5  mov     byte ptr [rdi+0Bh], 20h ; ' '
0x18005aab9  add     r9, 2
0x18005aabd  jmp     short loc_18005AB38
0x18005aabf  add     r9, 2
0x18005aac3  mov     ecx, 2Dh ; '-'
0x18005aac8  cmp     cx, ax
0x18005aacb  jnz     short loc_18005AB1D
0x18005aacd  test    r8w, r8w
0x18005aad1  jz      short loc_18005AB1D
0x18005aad3  movzx   ecx, word ptr [r9]
0x18005aad7  cmp     r11w, cx
0x18005aadb  jz      short loc_18005AB1D
0x18005aadd  add     r9, 2
0x18005aae1  movzx   r10d, cx
0x18005aae5  cmp     r8w, cx
0x18005aae9  cmovnb  r10w, r8w
0x18005aaee  cmovnb  r8w, cx
0x18005aaf3  jmp     short loc_18005AB12
0x18005aaf5  movzx   edx, r8w
0x18005aaf9  shr     rdx, 3
0x18005aafd  movzx   eax, r8w
0x18005ab01  and     eax, 7
0x18005ab04  movsx   ecx, byte ptr [rdx+rdi]
0x18005ab08  bts     ecx, eax
0x18005ab0b  mov     [rdx+rdi], cl
0x18005ab0e  inc     r8w
0x18005ab12  cmp     r8w, r10w
0x18005ab16  jbe     short loc_18005AAF5
0x18005ab18  mov     r8d, r15d
0x18005ab1b  jmp     short loc_18005AB38
0x18005ab1d  movzx   edx, ax
0x18005ab20  movzx   r8d, ax
0x18005ab24  shr     rdx, 3
0x18005ab28  movzx   eax, ax
0x18005ab2b  and     eax, 7
0x18005ab2e  movsx   ecx, byte ptr [rdx+rdi]
0x18005ab32  bts     ecx, eax
0x18005ab35  mov     [rdx+rdi], cl
0x18005ab38  movzx   eax, word ptr [r9]
0x18005ab3c  cmp     r11w, ax
0x18005ab40  jnz     loc_18005AABF
0x18005ab46  mov     rax, [rsp+88h+arg_40]
0x18005ab4e  mov     r8, r14; int
0x18005ab51  mov     [rsp+88h+var_48], rax; __int64
0x18005ab56  mov     rdx, rdi; int
0x18005ab59  mov     rax, qword ptr [rsp+88h+arg_38]
0x18005ab61  mov     ecx, ebx; int
0x18005ab63  mov     qword ptr [rsp+88h+var_50], rax; int
0x18005ab68  mov     rax, [rsp+88h+arg_30]
0x18005ab70  mov     [rsp+88h+Stream], rax; Stream
0x18005ab75  mov     eax, [rsp+88h+arg_28]
0x18005ab7c  mov     [rsp+88h+var_60], eax; int
0x18005ab80  mov     rax, [rsp+88h+arg_20]
0x18005ab88  mov     [rsi], r9
0x18005ab8b  mov     r9, rbp; int
0x18005ab8e  mov     qword ptr [rsp+88h+SizeConverted], rax; SizeConverted
0x18005ab93  call    ReadString_7
0x18005ab98  mov     rcx, rdi; Block
0x18005ab9b  mov     ebx, eax
0x18005ab9d  call    free
0x18005aba2  mov     eax, ebx
0x18005aba4  add     rsp, 58h
0x18005aba8  pop     r15
0x18005abaa  pop     r14
0x18005abac  pop     rdi
0x18005abad  pop     rsi
0x18005abae  pop     rbp
0x18005abaf  pop     rbx
0x18005abb0  retn
```
