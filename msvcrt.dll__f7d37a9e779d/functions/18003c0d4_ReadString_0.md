# ReadString_0

- ea: `0x18003c0d4`
- end: `0x18003c2ed`
- name: `ReadString_0`
- size: `537`
- prototype: `__int64 __fastcall(int, int, int, int, char SrcCh, int, FILE *Stream, __int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18003c2f4`
- `0x18003c568`

## callees

- `0x1800034e0`
- `0x180003f70`
- `0x180007f00`
- `0x18003c0d4`
- `0x18003c53c`
- `0x18004da80`

## pseudocode

```c
__int64 __fastcall ReadString_0(
        char a1,
        __int64 a2,
        int *a3,
        _DWORD *a4,
        _WORD **SrcCh,
        int a6,
        FILE *Stream,
        __int64 a8,
        _DWORD *a9)
{
  _WORD **v9; // rsi
  _WORD *v13; // r14
  bool v14; // zf
  int v15; // ebx
  __int64 v16; // r13
  int v17; // eax
  FILE *v18; // rcx
  int v19; // eax
  int v20; // ecx
  int v21; // eax
  unsigned int v22; // edx
  int v23; // ecx
  int v24; // ecx
  _WORD *v26; // rcx
  wchar_t DstCh; // [rsp+60h] [rbp+8h] BYREF
  __int64 v28; // [rsp+68h] [rbp+10h]
  int v29; // [rsp+70h] [rbp+18h]
  int v30; // [rsp+78h] [rbp+20h]

  v28 = a2;
  v9 = SrcCh;
  DstCh = 0;
  v13 = *SrcCh;
  --*a4;
  v14 = *a3 == -1;
  v29 = -((a1 & 8) != 0);
  if ( !v14 )
    ungetc_nolock(*a3, Stream);
  v15 = a1 & 0x10;
  v30 = v15;
  v16 = a8 - 1;
  if ( (a1 & 0x10) != 0 )
    v16 = a8;
  v17 = a1 & 1;
  LODWORD(a8) = v17;
  while ( 1 )
  {
    if ( v17 )
    {
      if ( !a6 )
        goto LABEL_34;
      --a6;
    }
    v18 = Stream;
    ++*a4;
    v19 = inc(v18);
    *a3 = v19;
    v20 = v19;
    if ( v19 == -1 )
      break;
    if ( !v15 && ((a1 & 0x20) == 0 || (unsigned int)(v19 - 9) <= 4 || v19 == 32) )
    {
      if ( (a1 & 0x40) == 0 )
        break;
      if ( v19 < 0 )
        break;
      v21 = v19 >> 3;
      if ( v20 < v20 >> 3 )
        break;
      v22 = v20 & 7;
      v23 = v29 ^ *(char *)(v21 + v28);
      if ( !_bittest(&v23, v22) )
        break;
    }
    if ( (a1 & 4) != 0 )
    {
      v13 = (_WORD *)((char *)v13 + 1);
    }
    else
    {
      if ( !v16 )
      {
        *errno() = 12;
        if ( (a1 & 2) != 0 )
          *v13 = 0;
        else
          *(_BYTE *)v13 = 0;
        return 0xFFFFFFFFLL;
      }
      v24 = *(unsigned __int8 *)a3;
      if ( (a1 & 2) != 0 )
      {
        LOBYTE(SrcCh) = *(_BYTE *)a3;
        if ( isleadbyte(v24) )
        {
          ++*a4;
          BYTE1(SrcCh) = inc(Stream);
        }
        DstCh = 63;
        mbtowc(&DstCh, (const char *)&SrcCh, _mb_cur_max);
        *(*v9)++ = DstCh;
      }
      else
      {
        *(_BYTE *)*v9 = v24;
        *v9 = (_WORD *)((char *)*v9 + 1);
      }
      v15 = v30;
      --v16;
    }
    v17 = a8;
  }
  --*a4;
  if ( *a3 != -1 )
    ungetc_nolock(*a3, Stream);
LABEL_34:
  if ( v13 == *v9 )
    return 0xFFFFFFFFLL;
  if ( (a1 & 4) == 0 )
  {
    ++*a9;
    if ( !v15 )
    {
      v26 = *v9;
      if ( (a1 & 2) != 0 )
        *v26 = 0;
      else
        *(_BYTE *)v26 = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18003c0d4  mov     [rsp+arg_8], rdx
0x18003c0d9  push    rbx
0x18003c0da  push    rbp
0x18003c0db  push    rsi
0x18003c0dc  push    rdi
0x18003c0dd  push    r12
0x18003c0df  push    r13
0x18003c0e1  push    r14
0x18003c0e3  sub     rsp, 20h
0x18003c0e7  mov     rsi, [rsp+58h+SrcCh]
0x18003c0ef  xor     eax, eax
0x18003c0f1  mov     [rsp+58h+DstCh], ax
0x18003c0f6  mov     rbp, r9
0x18003c0f9  mov     eax, ecx
0x18003c0fb  mov     r12, r8
0x18003c0fe  and     al, 8
0x18003c100  mov     edi, ecx
0x18003c102  mov     r14, [rsi]
0x18003c105  neg     al
0x18003c107  sbb     eax, eax
0x18003c109  dec     dword ptr [r9]
0x18003c10c  cmp     dword ptr [r8], 0FFFFFFFFh
0x18003c110  mov     [rsp+58h+arg_10], eax
0x18003c114  jz      short loc_18003C126
0x18003c116  mov     rdx, [rsp+58h+Stream]; Stream
0x18003c11e  mov     ecx, [r8]; Character
0x18003c121  call    _ungetc_nolock
0x18003c126  mov     rax, [rsp+58h+arg_38]
0x18003c12e  mov     ebx, edi
0x18003c130  and     ebx, 10h
0x18003c133  mov     [rsp+58h+arg_18], ebx
0x18003c137  lea     r13, [rax-1]
0x18003c13b  cmovnz  r13, rax
0x18003c13f  mov     eax, edi
0x18003c141  and     eax, 1
0x18003c144  mov     dword ptr [rsp+58h+arg_38], eax
0x18003c14b  test    eax, eax
0x18003c14d  jz      short loc_18003C167
0x18003c14f  mov     eax, [rsp+58h+arg_28]
0x18003c156  test    eax, eax
0x18003c158  jz      loc_18003C2BD
0x18003c15e  dec     eax
0x18003c160  mov     [rsp+58h+arg_28], eax
0x18003c167  mov     rcx, [rsp+58h+Stream]
0x18003c16f  inc     dword ptr [rbp+0]
0x18003c172  call    _inc
0x18003c177  mov     [r12], eax
0x18003c17b  mov     ecx, eax
0x18003c17d  cmp     eax, 0FFFFFFFFh
0x18003c180  jz      loc_18003C2A2
0x18003c186  test    ebx, ebx
0x18003c188  jnz     short loc_18003C1D9
0x18003c18a  test    dil, 20h
0x18003c18e  jz      short loc_18003C19D
0x18003c190  add     eax, 0FFFFFFF7h
0x18003c193  cmp     eax, 4
0x18003c196  jbe     short loc_18003C19D
0x18003c198  cmp     ecx, 20h ; ' '
0x18003c19b  jnz     short loc_18003C1D9
0x18003c19d  test    dil, 40h
0x18003c1a1  jz      loc_18003C2A2
0x18003c1a7  test    ecx, ecx
0x18003c1a9  js      loc_18003C2A2
0x18003c1af  mov     eax, ecx
0x18003c1b1  sar     eax, 3
0x18003c1b4  cmp     ecx, eax
0x18003c1b6  jl      loc_18003C2A2
0x18003c1bc  and     ecx, 7
0x18003c1bf  cdqe
0x18003c1c1  mov     edx, ecx
0x18003c1c3  mov     rcx, [rsp+58h+arg_8]
0x18003c1c8  movsx   ecx, byte ptr [rax+rcx]
0x18003c1cc  xor     ecx, [rsp+58h+arg_10]
0x18003c1d0  bt      ecx, edx
0x18003c1d3  jnb     loc_18003C2A2
0x18003c1d9  test    dil, 4
0x18003c1dd  jnz     loc_18003C266
0x18003c1e3  mov     ebx, edi
0x18003c1e5  and     ebx, 2
0x18003c1e8  test    r13, r13
0x18003c1eb  jz      loc_18003C275
0x18003c1f1  movzx   ecx, byte ptr [r12]; C
0x18003c1f6  test    ebx, ebx
0x18003c1f8  jz      short loc_18003C255
0x18003c1fa  mov     byte ptr [rsp+58h+SrcCh], cl
0x18003c201  call    isleadbyte
0x18003c206  test    eax, eax
0x18003c208  jz      short loc_18003C221
0x18003c20a  inc     dword ptr [rbp+0]
0x18003c20d  mov     rcx, [rsp+58h+Stream]
0x18003c215  call    _inc
0x18003c21a  mov     byte ptr [rsp+58h+SrcCh+1], al
0x18003c221  movsxd  r8, cs:__mb_cur_max; SrcSizeInBytes
0x18003c228  lea     rdx, [rsp+58h+SrcCh]; SrcCh
0x18003c230  mov     eax, 3Fh ; '?'
0x18003c235  lea     rcx, [rsp+58h+DstCh]; DstCh
0x18003c23a  mov     [rsp+58h+DstCh], ax
0x18003c23f  call    mbtowc
0x18003c244  mov     rcx, [rsi]
0x18003c247  movzx   eax, [rsp+58h+DstCh]
0x18003c24c  mov     [rcx], ax
0x18003c24f  add     qword ptr [rsi], 2
0x18003c253  jmp     short loc_18003C25D
0x18003c255  mov     rax, [rsi]
0x18003c258  mov     [rax], cl
0x18003c25a  inc     qword ptr [rsi]
0x18003c25d  mov     ebx, [rsp+58h+arg_18]
0x18003c261  dec     r13
0x18003c264  jmp     short loc_18003C269
0x18003c266  inc     r14
0x18003c269  mov     eax, dword ptr [rsp+58h+arg_38]
0x18003c270  jmp     loc_18003C14B
0x18003c275  call    _errno
0x18003c27a  mov     dword ptr [rax], 0Ch
0x18003c280  test    ebx, ebx
0x18003c282  jz      short loc_18003C29C
0x18003c284  xor     eax, eax
0x18003c286  mov     [r14], ax
0x18003c28a  or      eax, 0FFFFFFFFh
0x18003c28d  add     rsp, 20h
0x18003c291  pop     r14
0x18003c293  pop     r13
0x18003c295  pop     r12
0x18003c297  pop     rdi
0x18003c298  pop     rsi
0x18003c299  pop     rbp
0x18003c29a  pop     rbx
0x18003c29b  retn
0x18003c29c  mov     byte ptr [r14], 0
0x18003c2a0  jmp     short loc_18003C28A
0x18003c2a2  dec     dword ptr [rbp+0]
0x18003c2a5  cmp     dword ptr [r12], 0FFFFFFFFh
0x18003c2aa  jz      short loc_18003C2BD
0x18003c2ac  mov     rdx, [rsp+58h+Stream]; Stream
0x18003c2b4  mov     ecx, [r12]; Character
0x18003c2b8  call    _ungetc_nolock
0x18003c2bd  cmp     r14, [rsi]
0x18003c2c0  jz      short loc_18003C28A
0x18003c2c2  test    dil, 4
0x18003c2c6  jnz     short loc_18003C2E9
0x18003c2c8  mov     rax, [rsp+58h+arg_40]
0x18003c2d0  inc     dword ptr [rax]
0x18003c2d2  test    ebx, ebx
0x18003c2d4  jnz     short loc_18003C2E9
0x18003c2d6  mov     rcx, [rsi]
0x18003c2d9  test    dil, 2
0x18003c2dd  jz      short loc_18003C2E6
0x18003c2df  xor     eax, eax
0x18003c2e1  mov     [rcx], ax
0x18003c2e4  jmp     short loc_18003C2E9
0x18003c2e6  mov     byte ptr [rcx], 0
0x18003c2e9  xor     eax, eax
0x18003c2eb  jmp     short loc_18003C28D
```
