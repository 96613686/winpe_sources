# ReadString_1

- ea: `0x180042fa8`
- end: `0x180043158`
- name: `ReadString_1`
- size: `432`
- prototype: `__int64 __fastcall(int, int, int, int, char SrcCh, int, _locale_t Locale, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180043160`
- `0x18004339c`

## callees

- `0x1800034e0`
- `0x180003e40`
- `0x18001f240`
- `0x18001f574`
- `0x180042fa8`

## pseudocode

```c
__int64 __fastcall ReadString_1(
        char a1,
        __int64 a2,
        int *a3,
        _DWORD *a4,
        _QWORD *SrcCh,
        int a6,
        _locale_t Locale,
        _DWORD *a8)
{
  _WORD **v8; // rsi
  _WORD *v12; // r15
  bool v13; // zf
  int v14; // r12d
  int v15; // ebp
  int v16; // eax
  int v17; // ecx
  int v18; // eax
  unsigned int v19; // edx
  int v20; // ecx
  int v21; // ecx
  _WORD *v22; // rcx
  wchar_t DstCh; // [rsp+60h] [rbp+8h] BYREF
  __int64 v25; // [rsp+68h] [rbp+10h]
  int v26; // [rsp+70h] [rbp+18h]

  v25 = a2;
  v8 = (_WORD **)SrcCh;
  DstCh = 0;
  v12 = (_WORD *)*SrcCh;
  --*a4;
  v13 = *a3 == -1;
  v26 = -((a1 & 8) != 0);
  if ( !v13 )
    ungetch_nolock(*a3);
  v14 = a6;
  v15 = a1 & 0x10;
  while ( 1 )
  {
    if ( (a1 & 1) != 0 )
    {
      if ( !v14 )
        goto LABEL_24;
      --v14;
    }
    ++*a4;
    v16 = getche_nolock();
    *a3 = v16;
    v17 = v16;
    if ( (a1 & 0x10) == 0 && ((a1 & 0x20) == 0 || (unsigned int)(v16 - 9) <= 4 || v16 == 32) )
    {
      if ( (a1 & 0x40) == 0 )
        break;
      if ( v16 < 0 )
        break;
      v18 = v16 >> 3;
      if ( v17 < v17 >> 3 )
        break;
      v19 = v17 & 7;
      v20 = v26 ^ *(char *)(v18 + v25);
      if ( !_bittest(&v20, v19) )
        break;
    }
    if ( (a1 & 4) != 0 )
    {
      v12 = (_WORD *)((char *)v12 + 1);
    }
    else
    {
      v21 = *(unsigned __int8 *)a3;
      if ( (a1 & 2) != 0 )
      {
        LOBYTE(SrcCh) = *(_BYTE *)a3;
        if ( isleadbyte(v21) )
        {
          ++*a4;
          BYTE1(SrcCh) = getche_nolock();
        }
        DstCh = 63;
        mbtowc_l(&DstCh, (const char *)&SrcCh, *((int *)Locale->locinfo + 67), Locale);
        *(*v8)++ = DstCh;
      }
      else
      {
        *(_BYTE *)*v8 = v21;
        *v8 = (_WORD *)((char *)*v8 + 1);
      }
    }
  }
  --*a4;
  v15 = 0;
  if ( *a3 != -1 )
    ungetch_nolock(*a3);
LABEL_24:
  if ( v12 == *v8 )
    return 0xFFFFFFFFLL;
  if ( (a1 & 4) == 0 )
  {
    ++*a8;
    if ( !v15 )
    {
      v22 = *v8;
      if ( (a1 & 2) != 0 )
        *v22 = 0;
      else
        *(_BYTE *)v22 = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180042fa8  mov     [rsp+arg_18], rbx
0x180042fad  mov     [rsp+arg_8], rdx
0x180042fb2  push    rbp
0x180042fb3  push    rsi
0x180042fb4  push    rdi
0x180042fb5  push    r12
0x180042fb7  push    r13
0x180042fb9  push    r14
0x180042fbb  push    r15
0x180042fbd  sub     rsp, 20h
0x180042fc1  mov     rsi, [rsp+58h+SrcCh]
0x180042fc9  xor     eax, eax
0x180042fcb  mov     [rsp+58h+DstCh], ax
0x180042fd0  mov     rdi, r9
0x180042fd3  mov     eax, ecx
0x180042fd5  mov     r14, r8
0x180042fd8  and     al, 8
0x180042fda  mov     ebx, ecx
0x180042fdc  mov     r15, [rsi]
0x180042fdf  neg     al
0x180042fe1  sbb     eax, eax
0x180042fe3  dec     dword ptr [r9]
0x180042fe6  cmp     dword ptr [r8], 0FFFFFFFFh
0x180042fea  mov     [rsp+58h+arg_10], eax
0x180042fee  jz      short loc_180042FF8
0x180042ff0  mov     ecx, [r8]; Ch
0x180042ff3  call    _ungetch_nolock
0x180042ff8  mov     r12d, [rsp+58h+arg_28]
0x180043000  mov     ebp, ebx
0x180043002  and     ebp, 10h
0x180043005  mov     r13d, ebx
0x180043008  and     r13d, 1
0x18004300c  test    r13d, r13d
0x18004300f  jz      short loc_18004301D
0x180043011  test    r12d, r12d
0x180043014  jz      loc_180043112
0x18004301a  dec     r12d
0x18004301d  inc     dword ptr [rdi]
0x18004301f  call    _getche_nolock
0x180043024  mov     [r14], eax
0x180043027  mov     ecx, eax
0x180043029  test    ebp, ebp
0x18004302b  jnz     short loc_18004307A
0x18004302d  test    bl, 20h
0x180043030  jz      short loc_18004303F
0x180043032  add     eax, 0FFFFFFF7h
0x180043035  cmp     eax, 4
0x180043038  jbe     short loc_18004303F
0x18004303a  cmp     ecx, 20h ; ' '
0x18004303d  jnz     short loc_18004307A
0x18004303f  test    bl, 40h
0x180043042  jz      loc_180043100
0x180043048  test    ecx, ecx
0x18004304a  js      loc_180043100
0x180043050  mov     eax, ecx
0x180043052  sar     eax, 3
0x180043055  cmp     ecx, eax
0x180043057  jl      loc_180043100
0x18004305d  and     ecx, 7
0x180043060  cdqe
0x180043062  mov     edx, ecx
0x180043064  mov     rcx, [rsp+58h+arg_8]
0x180043069  movsx   ecx, byte ptr [rax+rcx]
0x18004306d  xor     ecx, [rsp+58h+arg_10]
0x180043071  bt      ecx, edx
0x180043074  jnb     loc_180043100
0x18004307a  test    bl, 4
0x18004307d  jnz     short loc_1800430F8
0x18004307f  movzx   ecx, byte ptr [r14]; C
0x180043083  test    bl, 2
0x180043086  jz      short loc_1800430EB
0x180043088  mov     byte ptr [rsp+58h+SrcCh], cl
0x18004308f  call    isleadbyte
0x180043094  test    eax, eax
0x180043096  jz      short loc_1800430A6
0x180043098  inc     dword ptr [rdi]
0x18004309a  call    _getche_nolock
0x18004309f  mov     byte ptr [rsp+58h+SrcCh+1], al
0x1800430a6  mov     rcx, [rsp+58h+Locale]
0x1800430ae  lea     rdx, [rsp+58h+SrcCh]; SrcCh
0x1800430b6  mov     eax, 3Fh ; '?'
0x1800430bb  mov     r9, rcx; Locale
0x1800430be  mov     [rsp+58h+DstCh], ax
0x1800430c3  mov     rax, [rcx]
0x1800430c6  lea     rcx, [rsp+58h+DstCh]; DstCh
0x1800430cb  movsxd  r8, dword ptr [rax+10Ch]; SrcSizeInBytes
0x1800430d2  call    _mbtowc_l
0x1800430d7  mov     rcx, [rsi]
0x1800430da  movzx   eax, [rsp+58h+DstCh]
0x1800430df  mov     [rcx], ax
0x1800430e2  add     qword ptr [rsi], 2
0x1800430e6  jmp     loc_18004300C
0x1800430eb  mov     rax, [rsi]
0x1800430ee  mov     [rax], cl
0x1800430f0  inc     qword ptr [rsi]
0x1800430f3  jmp     loc_18004300C
0x1800430f8  inc     r15
0x1800430fb  jmp     loc_18004300C
0x180043100  dec     dword ptr [rdi]
0x180043102  xor     ebp, ebp
0x180043104  cmp     dword ptr [r14], 0FFFFFFFFh
0x180043108  jz      short loc_180043112
0x18004310a  mov     ecx, [r14]; Ch
0x18004310d  call    _ungetch_nolock
0x180043112  cmp     r15, [rsi]
0x180043115  jz      short loc_180043140
0x180043117  test    bl, 4
0x18004311a  jnz     short loc_18004313C
0x18004311c  mov     rax, [rsp+58h+arg_38]
0x180043124  inc     dword ptr [rax]
0x180043126  test    ebp, ebp
0x180043128  jnz     short loc_18004313C
0x18004312a  mov     rcx, [rsi]
0x18004312d  test    bl, 2
0x180043130  jz      short loc_180043139
0x180043132  xor     eax, eax
0x180043134  mov     [rcx], ax
0x180043137  jmp     short loc_18004313C
0x180043139  mov     byte ptr [rcx], 0
0x18004313c  xor     eax, eax
0x18004313e  jmp     short loc_180043143
0x180043140  or      eax, 0FFFFFFFFh
0x180043143  mov     rbx, [rsp+58h+arg_18]
0x180043148  add     rsp, 20h
0x18004314c  pop     r15
0x18004314e  pop     r14
0x180043150  pop     r13
0x180043152  pop     r12
0x180043154  pop     rdi
0x180043155  pop     rsi
0x180043156  pop     rbp
0x180043157  retn
```
