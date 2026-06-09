# ReadStringDelimited_8

- ea: `0x18005bc64`
- end: `0x18005bdfa`
- name: `ReadStringDelimited_8`
- size: `406`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18005be00`

## callees

- `0x180007f00`
- `0x18001d300`
- `0x18001d568`
- `0x18005ba5c`
- `0x18005bc64`
- `0x18007d030`

## pseudocode

```c
__int64 __fastcall ReadStringDelimited_8(
        char a1,
        unsigned __int16 **a2,
        wint_t *a3,
        _DWORD *a4,
        char **SizeConverted,
        int a6,
        FILE *Stream,
        rsize_t SizeInBytes,
        int a9,
        _DWORD *a10)
{
  _BYTE *v14; // rax
  _BYTE *v15; // rdi
  unsigned __int16 *v17; // rcx
  unsigned __int16 *v18; // r9
  unsigned __int16 v19; // ax
  unsigned __int16 *v20; // r9
  unsigned __int16 v21; // r8
  unsigned __int16 v22; // cx
  unsigned __int16 v23; // r10
  unsigned __int16 v24; // ax
  unsigned int String_8; // ebx

  v14 = (_BYTE *)malloc_crt(0x2000u);
  v15 = v14;
  if ( v14 )
  {
    memset_thunk_772440563353939046(v14, 0, 0x2000u);
    v17 = *a2;
    v18 = *a2 + 1;
    *a2 = v18;
    if ( *v18 == 94 )
    {
      v19 = v18[1];
      a1 |= 8u;
    }
    else
    {
      v19 = *v18;
    }
    if ( *v18 != 94 )
      v18 = v17;
    v20 = v18 + 1;
    if ( v19 != 93 )
      goto LABEL_18;
    v21 = 93;
    v15[11] = 32;
    ++v20;
    while ( 1 )
    {
      v24 = *v20;
      if ( *v20 == 93 )
        break;
      ++v20;
      if ( v24 == 45 && v21 && (v22 = *v20, *v20 != 93) )
      {
        ++v20;
        v23 = v22;
        if ( v21 >= v22 )
        {
          v23 = v21;
          v21 = v22;
        }
        while ( v21 <= v23 )
        {
          v15[(unsigned __int64)v21 >> 3] |= 1 << (v21 & 7);
          ++v21;
        }
LABEL_18:
        v21 = 0;
      }
      else
      {
        v21 = v24;
        v15[(unsigned __int64)v24 >> 3] |= 1 << (v24 & 7);
      }
    }
    *a2 = v20;
    String_8 = ReadString_8(a1, (__int64)v15, a3, a4, SizeConverted, a6, Stream, SizeInBytes, a9, a10);
    free(v15);
    return String_8;
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
0x18005bc64  push    rbx
0x18005bc66  push    rbp
0x18005bc67  push    rsi
0x18005bc68  push    rdi
0x18005bc69  push    r14
0x18005bc6b  push    r15
0x18005bc6d  sub     rsp, 58h
0x18005bc71  mov     ebx, ecx
0x18005bc73  mov     rbp, r9
0x18005bc76  mov     ecx, 2000h; Size
0x18005bc7b  mov     r14, r8
0x18005bc7e  mov     rsi, rdx
0x18005bc81  call    _malloc_crt
0x18005bc86  xor     r15d, r15d
0x18005bc89  mov     rdi, rax
0x18005bc8c  test    rax, rax
0x18005bc8f  jnz     short loc_18005BCA2
0x18005bc91  call    _errno
0x18005bc96  lea     ecx, [rdi+0Ch]
0x18005bc99  mov     [rax], ecx
0x18005bc9b  mov     eax, ecx
0x18005bc9d  jmp     loc_18005BDED
0x18005bca2  xor     edx, edx; Val
0x18005bca4  mov     r8d, 2000h; Size
0x18005bcaa  mov     rcx, rdi; void *
0x18005bcad  call    memset$thunk$772440563353939046
0x18005bcb2  mov     rcx, [rsi]
0x18005bcb5  mov     edx, 5Eh ; '^'
0x18005bcba  lea     r9, [rcx+2]
0x18005bcbe  mov     [rsi], r9
0x18005bcc1  cmp     dx, [r9]
0x18005bcc5  jnz     short loc_18005BCD1
0x18005bcc7  movzx   eax, word ptr [r9+2]
0x18005bccc  or      ebx, 8
0x18005bccf  jmp     short loc_18005BCD5
0x18005bcd1  movzx   eax, word ptr [r9]
0x18005bcd5  cmp     dx, [r9]
0x18005bcd9  mov     r11d, 5Dh ; ']'
0x18005bcdf  cmovnz  r9, rcx
0x18005bce3  add     r9, 2
0x18005bce7  cmp     r11w, ax
0x18005bceb  jnz     short loc_18005BD54
0x18005bced  movzx   r8d, r11w
0x18005bcf1  mov     byte ptr [rdi+0Bh], 20h ; ' '
0x18005bcf5  add     r9, 2
0x18005bcf9  jmp     short loc_18005BD74
0x18005bcfb  add     r9, 2
0x18005bcff  mov     ecx, 2Dh ; '-'
0x18005bd04  cmp     cx, ax
0x18005bd07  jnz     short loc_18005BD59
0x18005bd09  test    r8w, r8w
0x18005bd0d  jz      short loc_18005BD59
0x18005bd0f  movzx   ecx, word ptr [r9]
0x18005bd13  cmp     r11w, cx
0x18005bd17  jz      short loc_18005BD59
0x18005bd19  add     r9, 2
0x18005bd1d  movzx   r10d, cx
0x18005bd21  cmp     r8w, cx
0x18005bd25  cmovnb  r10w, r8w
0x18005bd2a  cmovnb  r8w, cx
0x18005bd2f  jmp     short loc_18005BD4E
0x18005bd31  movzx   edx, r8w
0x18005bd35  shr     rdx, 3
0x18005bd39  movzx   eax, r8w
0x18005bd3d  and     eax, 7
0x18005bd40  movsx   ecx, byte ptr [rdx+rdi]
0x18005bd44  bts     ecx, eax
0x18005bd47  mov     [rdx+rdi], cl
0x18005bd4a  inc     r8w
0x18005bd4e  cmp     r8w, r10w
0x18005bd52  jbe     short loc_18005BD31
0x18005bd54  mov     r8d, r15d
0x18005bd57  jmp     short loc_18005BD74
0x18005bd59  movzx   edx, ax
0x18005bd5c  movzx   r8d, ax
0x18005bd60  shr     rdx, 3
0x18005bd64  movzx   eax, ax
0x18005bd67  and     eax, 7
0x18005bd6a  movsx   ecx, byte ptr [rdx+rdi]
0x18005bd6e  bts     ecx, eax
0x18005bd71  mov     [rdx+rdi], cl
0x18005bd74  movzx   eax, word ptr [r9]
0x18005bd78  cmp     r11w, ax
0x18005bd7c  jnz     loc_18005BCFB
0x18005bd82  mov     rax, [rsp+88h+arg_48]
0x18005bd8a  mov     r8, r14; int
0x18005bd8d  mov     [rsp+88h+var_40], rax; __int64
0x18005bd92  mov     rdx, rdi; int
0x18005bd95  mov     rax, qword ptr [rsp+88h+arg_40]
0x18005bd9d  mov     ecx, ebx; int
0x18005bd9f  mov     qword ptr [rsp+88h+var_48], rax; int
0x18005bda4  mov     rax, [rsp+88h+arg_38]
0x18005bdac  mov     [rsp+88h+SizeInBytes], rax; SizeInBytes
0x18005bdb1  mov     rax, [rsp+88h+arg_30]
0x18005bdb9  mov     [rsp+88h+Stream], rax; Stream
0x18005bdbe  mov     eax, [rsp+88h+arg_28]
0x18005bdc5  mov     [rsp+88h+var_60], eax; int
0x18005bdc9  mov     rax, [rsp+88h+arg_20]
0x18005bdd1  mov     [rsi], r9
0x18005bdd4  mov     r9, rbp; int
0x18005bdd7  mov     qword ptr [rsp+88h+SizeConverted], rax; SizeConverted
0x18005bddc  call    ReadString_8
0x18005bde1  mov     rcx, rdi; Block
0x18005bde4  mov     ebx, eax
0x18005bde6  call    free
0x18005bdeb  mov     eax, ebx
0x18005bded  add     rsp, 58h
0x18005bdf1  pop     r15
0x18005bdf3  pop     r14
0x18005bdf5  pop     rdi
0x18005bdf6  pop     rsi
0x18005bdf7  pop     rbp
0x18005bdf8  pop     rbx
0x18005bdf9  retn
```
