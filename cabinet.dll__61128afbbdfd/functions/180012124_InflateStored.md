# InflateStored

- ea: `0x180012124`
- end: `0x1800122b5`
- name: `InflateStored`
- size: `401`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800058e4`
- `0x180006c2c`

## callees

- `0x180012124`
- `0x18001b625`

## pseudocode

```c
__int64 __fastcall InflateStored(__int64 a1, int a2)
{
  unsigned int *v2; // r10
  unsigned int *v4; // r8
  int v5; // edx
  unsigned int v6; // r9d
  unsigned int i; // edx
  __int64 v8; // r11
  unsigned __int8 v9; // cl
  size_t v10; // rbx
  unsigned int v11; // edx
  unsigned int v12; // r9d
  __int64 v13; // r11
  unsigned __int8 v14; // cl
  int v15; // eax
  unsigned int v16; // eax
  __int64 v17; // rsi
  char *v18; // rsi
  unsigned int v19; // ecx
  unsigned int v20; // eax
  unsigned int v21; // edx
  __int64 v23; // rax

  v2 = (unsigned int *)(a1 + 32);
  v4 = (unsigned int *)(a1 + 36);
  if ( a2 )
  {
    v18 = *(char **)(a1 + 64);
    v10 = *(unsigned int *)(a1 + 60);
    *(_DWORD *)(a1 + 56) = 0;
  }
  else
  {
    v5 = *(_DWORD *)(a1 + 52);
    v6 = *(_DWORD *)(a1 + 48) >> (v5 & 7);
    for ( i = v5 - (v5 & 7); i < 0x10; i += 8 )
    {
      v8 = *v4;
      if ( (unsigned int)v8 >= *v2 )
      {
        if ( (_DWORD)v8 != *v2 )
          *(_DWORD *)(a1 + 4) = 1;
        v9 = 0;
      }
      else
      {
        v9 = *(_BYTE *)(v8 + *(_QWORD *)(a1 + 8));
        *v4 = v8 + 1;
      }
      v6 |= v9 << i;
    }
    v10 = (unsigned __int16)v6;
    v11 = i - 16;
    v12 = HIWORD(v6);
    if ( v11 < 0x10 )
    {
      v4 = (unsigned int *)(a1 + 36);
      do
      {
        v13 = *v4;
        if ( (unsigned int)v13 >= *v2 )
        {
          if ( (_DWORD)v13 != *v2 )
            *(_DWORD *)(a1 + 4) = 1;
          v14 = 0;
        }
        else
        {
          v14 = *(_BYTE *)(v13 + *(_QWORD *)(a1 + 8));
          *v4 = v13 + 1;
        }
        v15 = v14 << v11;
        v11 += 8;
        LOWORD(v12) = v15 | v12;
      }
      while ( v11 < 0x10 );
    }
    if ( (_DWORD)v10 != (unsigned __int16)~(_WORD)v12 || *(_DWORD *)(a1 + 4) || v11 != 16 )
      return 1;
    v16 = *v4;
    v17 = *v4;
    *(_QWORD *)(a1 + 48) = 0;
    v18 = (char *)(*(_QWORD *)(a1 + 8) + v17);
    *v4 = v10 + v16;
  }
  v19 = *(_DWORD *)(a1 + 40);
  v20 = *v4;
  v21 = *v2;
  if ( (unsigned int)v10 > v19 )
  {
    if ( v19 + v20 - (_DWORD)v10 <= v21 )
    {
      memcpy_0(*(void **)(a1 + 16), v18, *(unsigned int *)(a1 + 40));
      v23 = *(unsigned int *)(a1 + 40);
      *(_QWORD *)(a1 + 16) += v23;
      *(_DWORD *)(a1 + 56) = 1;
      *(_QWORD *)(a1 + 64) = &v18[v23];
      *(_DWORD *)(a1 + 60) = v10 - v23;
      *(_DWORD *)(a1 + 40) = 0;
      return 0;
    }
  }
  else if ( v20 <= v21 )
  {
    *(_DWORD *)(a1 + 40) = v19 - v10;
    memcpy_0(*(void **)(a1 + 16), v18, v10);
    *(_QWORD *)(a1 + 16) += v10;
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180012124  mov     [rsp+arg_0], rbx
0x180012129  mov     [rsp+arg_8], rsi
0x18001212e  push    rdi
0x18001212f  sub     rsp, 20h
0x180012133  lea     r10, [rcx+20h]
0x180012137  mov     rdi, rcx
0x18001213a  lea     r8, [rcx+24h]
0x18001213e  test    edx, edx
0x180012140  jnz     loc_180012241
0x180012146  mov     edx, [rcx+34h]
0x180012149  movzx   ecx, dx
0x18001214c  mov     r9d, [rdi+30h]
0x180012150  and     ecx, 7
0x180012153  shr     r9d, cl
0x180012156  sub     edx, ecx
0x180012158  cmp     edx, 10h
0x18001215b  jnb     short loc_180012187
0x18001215d  mov     r11d, [r8]
0x180012160  cmp     r11d, [r10]
0x180012163  jnb     loc_180012251
0x180012169  mov     rax, [rdi+8]
0x18001216d  mov     cl, [r11+rax]
0x180012171  lea     eax, [r11+1]
0x180012175  mov     [r8], eax
0x180012178  movzx   eax, cl
0x18001217b  mov     ecx, edx
0x18001217d  shl     eax, cl
0x18001217f  or      r9d, eax
0x180012182  add     edx, 8
0x180012185  jmp     short loc_180012158
0x180012187  movzx   ebx, r9w
0x18001218b  add     edx, 0FFFFFFF0h
0x18001218e  shr     r9d, 10h
0x180012192  cmp     edx, 10h
0x180012195  jnb     short loc_1800121C8
0x180012197  lea     r8, [rdi+24h]
0x18001219b  mov     r11d, [r8]
0x18001219e  cmp     r11d, [r10]
0x1800121a1  jnb     loc_180012261
0x1800121a7  mov     rax, [rdi+8]
0x1800121ab  mov     cl, [r11+rax]
0x1800121af  lea     eax, [r11+1]
0x1800121b3  mov     [r8], eax
0x1800121b6  movzx   eax, cl
0x1800121b9  mov     ecx, edx
0x1800121bb  shl     eax, cl
0x1800121bd  add     edx, 8
0x1800121c0  or      r9d, eax
0x1800121c3  cmp     edx, 10h
0x1800121c6  jb      short loc_18001219B
0x1800121c8  not     r9d
0x1800121cb  movzx   eax, r9w
0x1800121cf  cmp     ebx, eax
0x1800121d1  jnz     loc_1800122AB
0x1800121d7  cmp     dword ptr [rdi+4], 0
0x1800121db  jnz     loc_1800122AB
0x1800121e1  lea     eax, [rdx-10h]
0x1800121e4  test    eax, eax
0x1800121e6  jnz     loc_1800122AB
0x1800121ec  mov     eax, [r8]
0x1800121ef  mov     esi, eax
0x1800121f1  mov     qword ptr [rdi+30h], 0
0x1800121f9  add     rsi, [rdi+8]
0x1800121fd  add     eax, ebx
0x1800121ff  mov     [r8], eax
0x180012202  mov     ecx, [rdi+28h]
0x180012205  mov     eax, [r8]
0x180012208  mov     edx, [r10]
0x18001220b  cmp     ebx, ecx
0x18001220d  ja      short loc_180012271
0x18001220f  cmp     eax, edx
0x180012211  ja      loc_1800122AB
0x180012217  sub     ecx, ebx
0x180012219  mov     r8, rbx; Size
0x18001221c  mov     [rdi+28h], ecx
0x18001221f  mov     rdx, rsi; Src
0x180012222  mov     rcx, [rdi+10h]; void *
0x180012226  call    memcpy_0
0x18001222b  add     [rdi+10h], rbx
0x18001222f  xor     eax, eax
0x180012231  mov     rbx, [rsp+28h+arg_0]
0x180012236  mov     rsi, [rsp+28h+arg_8]
0x18001223b  add     rsp, 20h
0x18001223f  pop     rdi
0x180012240  retn
0x180012241  mov     rsi, [rcx+40h]
0x180012245  mov     ebx, [rcx+3Ch]
0x180012248  mov     dword ptr [rcx+38h], 0
0x18001224f  jmp     short loc_180012202
0x180012251  jz      short loc_18001225A
0x180012253  mov     dword ptr [rdi+4], 1
0x18001225a  xor     cl, cl
0x18001225c  jmp     loc_180012178
0x180012261  jz      short loc_18001226A
0x180012263  mov     dword ptr [rdi+4], 1
0x18001226a  xor     cl, cl
0x18001226c  jmp     loc_1800121B6
0x180012271  sub     eax, ebx
0x180012273  add     eax, ecx
0x180012275  cmp     eax, edx
0x180012277  ja      short loc_1800122AB
0x180012279  mov     r8, rcx; Size
0x18001227c  mov     rdx, rsi; Src
0x18001227f  mov     rcx, [rdi+10h]; void *
0x180012283  call    memcpy_0
0x180012288  mov     eax, [rdi+28h]
0x18001228b  add     [rdi+10h], rax
0x18001228f  sub     ebx, eax
0x180012291  add     rax, rsi
0x180012294  mov     dword ptr [rdi+38h], 1
0x18001229b  mov     [rdi+40h], rax
0x18001229f  mov     [rdi+3Ch], ebx
0x1800122a2  mov     dword ptr [rdi+28h], 0
0x1800122a9  jmp     short loc_18001222F
0x1800122ab  mov     eax, 1
0x1800122b0  jmp     loc_180012231
```
