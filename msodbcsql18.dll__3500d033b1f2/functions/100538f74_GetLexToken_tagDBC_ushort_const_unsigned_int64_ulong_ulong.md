# GetLexToken(tagDBC *,ushort const *,unsigned __int64,ulong *,ulong *)

- ea: `0x100538f74`
- end: `0x10053915c`
- name: `?GetLexToken@@YAGPEAUtagDBC@@PEBG_KPEAK3@Z`
- size: `488`
- prototype: `unsigned __int16 __fastcall(struct tagDBC *, const unsigned __int16 *, unsigned __int64, unsigned int *, unsigned int *)`
- caller_count: `21`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1004b9060`
- `0x1004bd184`
- `0x1004beb04`
- `0x1004bee2c`
- `0x1004befbc`
- `0x1004c4c24`
- `0x1004dbcc8`
- `0x1004de0ac`
- `0x1004e2028`
- `0x1004efbb8`
- `0x1005024a8`
- `0x10050562c`
- `0x10050a1bc`
- `0x10050b8b8`
- `0x10050ba40`
- `0x10052b000`
- `0x10052be88`
- `0x10052c118`
- `0x10052d124`
- `0x100539fc0`
- `0x10053a224`

## callees

- `0x100406ddc`
- `0x100533878`
- `0x100538f74`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!iswxdigit` at `0x100539020`
- `api-ms-win-crt-string-l1-1-0!iswxdigit` at `0x100539020`
- `api-ms-win-crt-string-l1-1-0!iswdigit` at `0x100538fe2`
- `api-ms-win-crt-string-l1-1-0!iswdigit` at `0x10053904c`
- `api-ms-win-crt-string-l1-1-0!iswdigit` at `0x100538fe2`
- `api-ms-win-crt-string-l1-1-0!iswdigit` at `0x10053904c`
- `api-ms-win-crt-string-l1-1-0!towupper` at `0x100539000`
- `api-ms-win-crt-string-l1-1-0!towupper` at `0x100539000`

## pseudocode

```c
__int64 __fastcall GetLexToken(
        struct tagDBC *a1,
        unsigned __int16 *a2,
        unsigned __int64 a3,
        unsigned int *a4,
        unsigned int *a5)
{
  unsigned int *v5; // r12
  unsigned __int16 *v9; // rsi
  signed __int64 v10; // rcx
  unsigned __int64 v11; // rbx
  __int64 result; // rax
  unsigned __int16 v13; // di
  wint_t *v14; // rsi
  wint_t *v15; // rbp
  unsigned __int16 *v16; // rsi
  const unsigned __int16 *v17; // rbp
  unsigned __int64 v18; // rcx
  unsigned __int16 v19; // dx
  unsigned __int16 *v20; // rax
  unsigned __int16 *v21; // rcx
  unsigned __int16 *v22; // [rsp+68h] [rbp+10h] BYREF
  unsigned int v23; // [rsp+70h] [rbp+18h] BYREF
  unsigned __int64 v24; // [rsp+78h] [rbp+20h] BYREF

  v22 = a2;
  v5 = a5;
  v24 = a3;
  v23 = 0;
  *a5 = 0;
  SkipWSComments((const unsigned __int16 **)&v22, &v24);
  v9 = v22;
  v10 = (char *)v22 - (char *)a2;
  v11 = v24;
  *a4 = v10 >> 1;
  if ( !v11 )
    return 0;
  v13 = 1;
  if ( iswdigit(*v9) )
  {
    if ( v11 > 1 && *v9 == 48 && towupper(v9[1]) == 88 )
    {
      v14 = v9 + 2;
      v11 -= 2LL;
      if ( v11 )
      {
        v15 = v14;
        do
        {
          if ( !iswxdigit(*v14) )
            break;
          v14 = ++v15;
          --v11;
        }
        while ( v11 );
      }
    }
    else
    {
      do
      {
        if ( !iswdigit(*v9) )
          break;
        ++v9;
        --v11;
      }
      while ( v11 );
      v13 = 2;
    }
  }
  else
  {
    do
    {
      if ( *v9 != 46 )
        break;
      --v11;
      ++v9;
    }
    while ( v11 );
    if ( (unsigned int)GetIdentifier(v9, v11, &v23) )
    {
      v11 -= v23;
      v16 = &v9[v23];
      if ( v11 )
      {
        v17 = v16;
        do
        {
          if ( *v16 != 46 )
            break;
          v16 = (unsigned __int16 *)(v17 + 1);
          if ( (unsigned int)GetIdentifier(++v17, --v11, &v23) )
          {
            v11 -= v23;
            v17 = &v16[v23];
            v16 = (unsigned __int16 *)v17;
          }
        }
        while ( v11 );
      }
    }
    else
    {
      v18 = v11 + *a4 - a3;
      v11 = a3 - *a4;
      v19 = v9[v18];
      if ( v19 == 39 || v19 == 34 )
      {
        v20 = &v9[v18 + 1];
        if ( --v11 )
        {
          v21 = &v9[v18 + 1];
          while ( *v20 != v19 )
          {
            v20 = ++v21;
            if ( !--v11 )
              goto LABEL_34;
          }
          LODWORD(v11) = v11 - 1;
        }
      }
      else
      {
        LODWORD(v11) = v11 - 1;
        v13 = 3;
      }
    }
  }
LABEL_34:
  result = v13;
  *v5 = a3 - *a4 - v11;
  return result;
}

```

## disassembly

```asm
0x100538f74  mov     rax, rsp
0x100538f77  mov     [rax+8], rbx
0x100538f7b  mov     [rax+10h], rdx
0x100538f7f  push    rbp
0x100538f80  push    rsi
0x100538f81  push    rdi
0x100538f82  push    r12
0x100538f84  push    r13
0x100538f86  push    r14
0x100538f88  push    r15
0x100538f8a  sub     rsp, 20h
0x100538f8e  mov     r12, [rsp+58h+arg_20]
0x100538f96  lea     rcx, [rax+10h]; unsigned __int16 **
0x100538f9a  mov     rbx, rdx
0x100538f9d  mov     [rax+20h], r8
0x100538fa1  xor     r13d, r13d
0x100538fa4  lea     rdx, [rax+20h]; unsigned __int64 *
0x100538fa8  mov     r15, r9
0x100538fab  mov     [rax+18h], r13d
0x100538faf  mov     [r12], r13d
0x100538fb3  mov     r14, r8
0x100538fb6  call    ?SkipWSComments@@YAXAEAPEBGAEA_K@Z; SkipWSComments(ushort const * &,unsigned __int64 &)
0x100538fbb  mov     rsi, [rsp+58h+arg_8]
0x100538fc0  mov     rcx, rsi
0x100538fc3  sub     rcx, rbx
0x100538fc6  mov     rbx, [rsp+58h+arg_18]
0x100538fcb  sar     rcx, 1
0x100538fce  mov     [r15], ecx
0x100538fd1  test    rbx, rbx
0x100538fd4  jnz     short loc_100538FDF
0x100538fd6  movzx   eax, r13w
0x100538fda  jmp     loc_100539147
0x100538fdf  movzx   ecx, word ptr [rsi]; C
0x100538fe2  call    cs:__imp_iswdigit
0x100538fe8  mov     edi, 1
0x100538fed  test    eax, eax
0x100538fef  jz      short loc_100539066
0x100538ff1  cmp     rbx, rdi
0x100538ff4  jbe     short loc_10053903F
0x100538ff6  cmp     word ptr [rsi], 30h ; '0'
0x100538ffa  jnz     short loc_10053903F
0x100538ffc  movzx   ecx, word ptr [rsi+2]; C
0x100539000  call    cs:__imp_towupper
0x100539006  cmp     ax, 58h ; 'X'
0x10053900a  jnz     short loc_10053903F
0x10053900c  add     rsi, 4
0x100539010  sub     rbx, 2
0x100539014  jz      loc_10053913A
0x10053901a  mov     rbp, rsi
0x10053901d  movzx   ecx, word ptr [rsi]; C
0x100539020  call    cs:__imp_iswxdigit
0x100539026  test    eax, eax
0x100539028  jz      loc_10053913A
0x10053902e  lea     rsi, [rbp+2]
0x100539032  mov     rbp, rsi
0x100539035  sub     rbx, rdi
0x100539038  jnz     short loc_10053901D
0x10053903a  jmp     loc_10053913A
0x10053903f  mov     ebp, 2
0x100539044  test    rbx, rbx
0x100539047  jz      short loc_10053905E
0x100539049  movzx   ecx, word ptr [rsi]; C
0x10053904c  call    cs:__imp_iswdigit
0x100539052  test    eax, eax
0x100539054  jz      short loc_10053905E
0x100539056  add     rsi, rbp
0x100539059  sub     rbx, rdi
0x10053905c  jnz     short loc_100539049
0x10053905e  movzx   edi, bp
0x100539061  jmp     loc_10053913A
0x100539066  cmp     rbx, rdi
0x100539069  jb      short loc_100539081
0x10053906b  mov     ebp, 2
0x100539070  cmp     word ptr [rsi], 2Eh ; '.'
0x100539074  jnz     short loc_100539081
0x100539076  sub     rbx, rdi
0x100539079  add     rsi, rbp
0x10053907c  cmp     rbx, rdi
0x10053907f  jnb     short loc_100539070
0x100539081  lea     r8, [rsp+58h+arg_10]; unsigned int *
0x100539086  mov     rdx, rbx; unsigned __int64
0x100539089  mov     rcx, rsi; unsigned __int16 *
0x10053908c  call    ?GetIdentifier@@YAHPEBG_KPEAK@Z; GetIdentifier(ushort const *,unsigned __int64,ulong *)
0x100539091  test    eax, eax
0x100539093  jz      short loc_1005390E9
0x100539095  mov     eax, [rsp+58h+arg_10]
0x100539099  sub     rbx, rax
0x10053909c  lea     rsi, [rsi+rax*2]
0x1005390a0  cmp     rbx, rdi
0x1005390a3  jb      loc_10053913A
0x1005390a9  mov     rbp, rsi
0x1005390ac  cmp     word ptr [rsi], 2Eh ; '.'
0x1005390b0  jnz     loc_10053913A
0x1005390b6  lea     rsi, [rbp+2]
0x1005390ba  sub     rbx, rdi
0x1005390bd  mov     rdx, rbx; unsigned __int64
0x1005390c0  lea     r8, [rsp+58h+arg_10]; unsigned int *
0x1005390c5  mov     rcx, rsi; unsigned __int16 *
0x1005390c8  mov     rbp, rsi
0x1005390cb  call    ?GetIdentifier@@YAHPEBG_KPEAK@Z; GetIdentifier(ushort const *,unsigned __int64,ulong *)
0x1005390d0  test    eax, eax
0x1005390d2  jz      short loc_1005390E2
0x1005390d4  mov     eax, [rsp+58h+arg_10]
0x1005390d8  sub     rbx, rax
0x1005390db  lea     rbp, [rsi+rax*2]
0x1005390df  mov     rsi, rbp
0x1005390e2  cmp     rbx, rdi
0x1005390e5  jnb     short loc_1005390AC
0x1005390e7  jmp     short loc_10053913A
0x1005390e9  mov     eax, [r15]
0x1005390ec  mov     ecx, eax
0x1005390ee  sub     rcx, r14
0x1005390f1  add     rcx, rbx
0x1005390f4  mov     rbx, r14
0x1005390f7  sub     rbx, rax
0x1005390fa  movzx   edx, word ptr [rsi+rcx*2]
0x1005390fe  cmp     dx, 27h ; '''
0x100539102  jz      short loc_100539114
0x100539104  cmp     dx, 22h ; '"'
0x100539108  jz      short loc_100539114
0x10053910a  sub     rbx, rdi
0x10053910d  mov     edi, 3
0x100539112  jmp     short loc_10053913A
0x100539114  lea     rax, [rcx+1]
0x100539118  lea     rax, [rsi+rax*2]
0x10053911c  sub     rbx, rdi
0x10053911f  jz      short loc_10053913A
0x100539121  mov     rcx, rax
0x100539124  cmp     [rax], dx
0x100539127  jz      short loc_100539137
0x100539129  lea     rax, [rcx+2]
0x10053912d  mov     rcx, rax
0x100539130  sub     rbx, rdi
0x100539133  jnz     short loc_100539124
0x100539135  jmp     short loc_10053913A
0x100539137  sub     rbx, rdi
0x10053913a  sub     r14d, [r15]
0x10053913d  movzx   eax, di
0x100539140  sub     r14d, ebx
0x100539143  mov     [r12], r14d
0x100539147  mov     rbx, [rsp+58h+arg_0]
0x10053914c  add     rsp, 20h
0x100539150  pop     r15
0x100539152  pop     r14
0x100539154  pop     r13
0x100539156  pop     r12
0x100539158  pop     rdi
0x100539159  pop     rsi
0x10053915a  pop     rbp
0x10053915b  retn
```
