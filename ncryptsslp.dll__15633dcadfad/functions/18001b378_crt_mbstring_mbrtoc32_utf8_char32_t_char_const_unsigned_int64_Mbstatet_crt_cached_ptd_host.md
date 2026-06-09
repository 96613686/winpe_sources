# __crt_mbstring::__mbrtoc32_utf8(char32_t *,char const *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)

- ea: `0x18001b378`
- end: `0x18001b510`
- name: `?__mbrtoc32_utf8@__crt_mbstring@@YA_KPEA_UPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z`
- size: `408`
- prototype: `unsigned __int64(__crt_mbstring *__hidden this, char32_t *, const char *, unsigned __int64, struct _Mbstatet *, struct __crt_cached_ptd_host *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18001b518`
- `0x18001b568`

## callees

- `0x18001b338`
- `0x18001b378`
- `0x18001b8dc`
- `0x18001b8f0`

## pseudocode

```c
unsigned __int64 __fastcall __crt_mbstring::__mbrtoc32_utf8(
        unsigned __int64 this,
        char32_t *a2,
        struct __crt_cached_ptd_host *a3,
        __int64 *a4,
        struct _Mbstatet *a5)
{
  __int64 *v5; // rbx
  __crt_mbstring *v6; // rdi
  unsigned __int64 v8; // rbp
  _DWORD *v9; // rsi
  __int64 v11; // rdx
  int v12; // eax
  unsigned __int8 v13; // r11
  unsigned int v14; // edx
  unsigned __int64 v15; // r9
  char v16; // cl
  _DWORD v17[20]; // [rsp+18h] [rbp-50h]

  v5 = &qword_18003E378;
  v6 = (__crt_mbstring *)&word_18002FB8E;
  if ( a4 )
    v5 = a4;
  v8 = 1;
  v9 = (_DWORD *)(this & -(__int64)(a2 != 0));
  if ( a2 )
  {
    v8 = (unsigned __int64)a3;
    v6 = (__crt_mbstring *)a2;
  }
  if ( !v8 )
    return -2;
  if ( *((_WORD *)v5 + 3) )
  {
    if ( (unsigned __int8)(*((_BYTE *)v5 + 4) - 2) > 2u )
      return __crt_mbstring::return_illegal_sequence((__crt_mbstring *)v5, a5, a3);
    LOBYTE(a3) = *((_BYTE *)v5 + 6);
    if ( !(_BYTE)a3 || (unsigned __int8)a3 >= *((_BYTE *)v5 + 4) )
      return __crt_mbstring::return_illegal_sequence((__crt_mbstring *)v5, a5, a3);
    v13 = *((_BYTE *)v5 + 4);
    v14 = *(_DWORD *)v5;
    goto LABEL_18;
  }
  v11 = (int)__crt_mbstring::__mblen_utf8(v6, (const char *)a2);
  v12 = *(unsigned __int8 *)v6;
  if ( (unsigned int)v11 > 1 )
  {
    if ( (unsigned int)(v11 - 2) > 2 )
      return __crt_mbstring::return_illegal_sequence((__crt_mbstring *)v5, a5, a3);
    v13 = v11;
    v6 = (__crt_mbstring *)((char *)v6 + 1);
    LOBYTE(a3) = v11;
    v14 = v12 & ((1 << (7 - v11)) - 1);
LABEL_18:
    v15 = (unsigned __int8)a3;
    if ( (unsigned __int8)a3 >= v8 )
      v15 = v8;
    while ( v6 - (__crt_mbstring *)a2 < v15 )
    {
      v16 = *(_BYTE *)v6;
      if ( (*(_BYTE *)v6 & 0xC0) != 0x80 )
        return __crt_mbstring::return_illegal_sequence((__crt_mbstring *)v5, a5, a3);
      v6 = (__crt_mbstring *)((char *)v6 + 1);
      v14 = (v14 << 6) | v16 & 0x3F;
    }
    if ( v15 < (unsigned __int8)a3 )
    {
      *((_WORD *)v5 + 2) = v13;
      *((_WORD *)v5 + 3) = (unsigned __int8)((_BYTE)a3 - v15);
      *(_DWORD *)v5 = v14;
      return -2;
    }
    if ( v14 - 55296 > 0x7FF && v14 < 0x110000 )
    {
      v17[2] = 128;
      v17[3] = 2048;
      v17[4] = 0x10000;
      if ( v14 >= v17[v13] )
      {
        if ( v9 )
          *v9 = v14;
        return __crt_mbstring::reset_and_return(
                 (__crt_mbstring *)((unsigned __int8)a3 & (unsigned __int64)-(__int64)(v14 != 0)),
                 (unsigned __int64)v5,
                 (struct _Mbstatet *)a3);
      }
    }
    return __crt_mbstring::return_illegal_sequence((__crt_mbstring *)v5, a5, a3);
  }
  if ( v9 )
    *v9 = v12;
  return v11;
}

```

## disassembly

```asm
0x18001b378  push    rbx
0x18001b37a  push    rbp
0x18001b37b  push    rsi
0x18001b37c  push    rdi
0x18001b37d  push    r14
0x18001b37f  push    r15
0x18001b381  sub     rsp, 38h
0x18001b385  xor     r15d, r15d
0x18001b388  lea     rbx, qword_18003E378
0x18001b38f  test    r9, r9
0x18001b392  lea     rdi, word_18002FB8E
0x18001b399  mov     rax, rdx
0x18001b39c  mov     r14, rdx
0x18001b39f  cmovnz  rbx, r9
0x18001b3a3  neg     rax
0x18001b3a6  lea     ebp, [r15+1]
0x18001b3aa  sbb     rsi, rsi
0x18001b3ad  and     rsi, rcx
0x18001b3b0  test    rdx, rdx
0x18001b3b3  cmovnz  rbp, r8
0x18001b3b7  cmovnz  rdi, rdx
0x18001b3bb  test    rbp, rbp
0x18001b3be  jnz     short loc_18001B3CC
0x18001b3c0  mov     rax, 0FFFFFFFFFFFFFFFEh
0x18001b3c7  jmp     loc_18001B503
0x18001b3cc  cmp     [rbx+6], r15w
0x18001b3d1  jnz     short loc_18001B420
0x18001b3d3  mov     rcx, rdi; this
0x18001b3d6  call    ?__mblen_utf8@__crt_mbstring@@YAHPEBD@Z; __crt_mbstring::__mblen_utf8(char const *)
0x18001b3db  movsxd  rdx, eax
0x18001b3de  movzx   eax, byte ptr [rdi]
0x18001b3e1  cmp     edx, 1
0x18001b3e4  jbe     short loc_18001B411
0x18001b3e6  lea     ecx, [rdx-2]
0x18001b3e9  cmp     ecx, 2
0x18001b3ec  ja      loc_18001B4F3
0x18001b3f2  movzx   r11d, dl
0x18001b3f6  mov     ecx, 7
0x18001b3fb  sub     ecx, r11d
0x18001b3fe  mov     edx, 1
0x18001b403  shl     edx, cl
0x18001b405  inc     rdi
0x18001b408  dec     edx
0x18001b40a  mov     r8b, r11b
0x18001b40d  and     edx, eax
0x18001b40f  jmp     short loc_18001B44B
0x18001b411  test    rsi, rsi
0x18001b414  jz      short loc_18001B418
0x18001b416  mov     [rsi], eax
0x18001b418  mov     rax, rdx
0x18001b41b  jmp     loc_18001B503
0x18001b420  mov     al, [rbx+4]
0x18001b423  sub     al, 2
0x18001b425  cmp     al, 2
0x18001b427  ja      loc_18001B4F3
0x18001b42d  mov     r8b, [rbx+6]
0x18001b431  cmp     r8b, 1
0x18001b435  jb      loc_18001B4F3
0x18001b43b  cmp     r8b, [rbx+4]
0x18001b43f  jnb     loc_18001B4F3
0x18001b445  mov     r11b, [rbx+4]
0x18001b449  mov     edx, [rbx]
0x18001b44b  movzx   r10d, r8b
0x18001b44f  cmp     r10, rbp
0x18001b452  mov     r9d, r10d
0x18001b455  cmovnb  r9, rbp
0x18001b459  jmp     short loc_18001B479
0x18001b45b  movzx   ecx, byte ptr [rdi]
0x18001b45e  mov     al, cl
0x18001b460  and     al, 0C0h
0x18001b462  cmp     al, 80h
0x18001b464  jnz     loc_18001B4F3
0x18001b46a  mov     eax, edx
0x18001b46c  and     ecx, 3Fh
0x18001b46f  shl     eax, 6
0x18001b472  mov     edx, ecx
0x18001b474  inc     rdi
0x18001b477  or      edx, eax
0x18001b479  mov     rax, rdi
0x18001b47c  sub     rax, r14
0x18001b47f  cmp     rax, r9
0x18001b482  jb      short loc_18001B45B
0x18001b484  cmp     r9, r10
0x18001b487  jnb     short loc_18001B4A3
0x18001b489  movzx   eax, r11b
0x18001b48d  sub     r8b, r9b; struct _Mbstatet *
0x18001b490  mov     [rbx+4], ax
0x18001b494  movzx   eax, r8b
0x18001b498  mov     [rbx+6], ax
0x18001b49c  mov     [rbx], edx
0x18001b49e  jmp     loc_18001B3C0
0x18001b4a3  lea     eax, [rdx-0D800h]
0x18001b4a9  cmp     eax, 7FFh
0x18001b4ae  jbe     short loc_18001B4F3
0x18001b4b0  cmp     edx, 110000h
0x18001b4b6  jnb     short loc_18001B4F3
0x18001b4b8  movzx   eax, r11b
0x18001b4bc  mov     [rsp+68h+var_48], 80h
0x18001b4c4  mov     [rsp+68h+var_44], 800h
0x18001b4cc  mov     [rsp+68h+var_40], 10000h
0x18001b4d4  cmp     edx, [rsp+rax*4+68h+var_50]
0x18001b4d8  jb      short loc_18001B4F3
0x18001b4da  test    rsi, rsi
0x18001b4dd  jz      short loc_18001B4E1
0x18001b4df  mov     [rsi], edx
0x18001b4e1  neg     edx
0x18001b4e3  mov     rdx, rbx; unsigned __int64
0x18001b4e6  sbb     rcx, rcx
0x18001b4e9  and     rcx, r10; this
0x18001b4ec  call    ?reset_and_return@__crt_mbstring@@YA_K_KPEAU_Mbstatet@@@Z; __crt_mbstring::reset_and_return(unsigned __int64,_Mbstatet *)
0x18001b4f1  jmp     short loc_18001B503
0x18001b4f3  mov     rdx, [rsp+68h+arg_20]; struct _Mbstatet *
0x18001b4fb  mov     rcx, rbx; this
0x18001b4fe  call    ?return_illegal_sequence@__crt_mbstring@@YA_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::return_illegal_sequence(_Mbstatet *,__crt_cached_ptd_host &)
0x18001b503  add     rsp, 38h
0x18001b507  pop     r15
0x18001b509  pop     r14
0x18001b50b  pop     rdi
0x18001b50c  pop     rsi
0x18001b50d  pop     rbp
0x18001b50e  pop     rbx
0x18001b50f  retn
```
