# ReadStringDelimited_2

- ea: `0x180044234`
- end: `0x18004439e`
- name: `ReadStringDelimited_2`
- size: `362`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800443a4`

## callees

- `0x180044020`
- `0x180044234`

## pseudocode

```c
__int64 __fastcall ReadStringDelimited_2(
        char a1,
        unsigned __int8 **a2,
        int *a3,
        _DWORD *a4,
        _WORD **SrcCh,
        int a6,
        __int64 a7,
        __crt_locale_pointers *Locale,
        _DWORD *a9)
{
  unsigned __int8 *v9; // rax
  char v13; // bl
  unsigned __int8 *v14; // rdx
  bool v15; // zf
  unsigned __int8 v16; // r9
  char v17; // al
  unsigned __int8 *v18; // rcx
  unsigned __int8 *v19; // r8
  unsigned __int8 v20; // al
  unsigned __int8 v21; // r9
  unsigned __int8 v22; // cl
  unsigned __int8 v23; // r10
  unsigned __int8 v24; // r11
  int v26[4]; // [rsp+50h] [rbp-48h] BYREF
  __int128 v27; // [rsp+60h] [rbp-38h]

  v9 = *a2;
  v13 = a1;
  v14 = *a2 + 1;
  *a2 = v14;
  v15 = *v14 == 94;
  *(_OWORD *)v26 = 0;
  v27 = 0;
  if ( v15 )
  {
    v16 = v14[1];
    v13 = a1 | 8;
  }
  else
  {
    v16 = *v14;
  }
  if ( *v14 != 94 )
    v14 = v9;
  v17 = HIBYTE(v26[2]);
  if ( v16 == 93 )
    v17 = 32;
  v18 = v14 + 1;
  HIBYTE(v26[2]) = v17;
  if ( v16 != 93 )
    v18 = v14;
  v19 = v18 + 1;
  v20 = v18[1];
  if ( v20 != 93 )
  {
    v21 = v16 != 93 ? 0 : 0x5D;
    do
    {
      ++v19;
      if ( v20 == 45 && v21 && (v22 = *v19, *v19 != 93) )
      {
        ++v19;
        v23 = v21;
        v24 = v22;
        if ( v21 >= v22 )
        {
          v24 = v21;
          v23 = v22;
        }
        while ( v23 <= v24 )
        {
          *((_BYTE *)v26 + ((unsigned __int64)v23 >> 3)) |= 1 << (v23 & 7);
          ++v23;
        }
        v21 = 0;
      }
      else
      {
        v21 = v20;
        *((_BYTE *)v26 + ((unsigned __int64)v20 >> 3)) |= 1 << (v20 & 7);
      }
      v20 = *v19;
    }
    while ( *v19 != 93 );
  }
  *a2 = v19;
  return ReadString_2(v13, (__int64)v26, a3, a4, SrcCh, a6, a7, Locale, a9);
}

```

## disassembly

```asm
0x180044234  mov     [rsp+arg_18], rbx
0x180044239  push    rbp
0x18004423a  push    rsi
0x18004423b  push    rdi
0x18004423c  push    r14
0x18004423e  push    r15
0x180044240  sub     rsp, 70h
0x180044244  mov     rax, [rdx]
0x180044247  mov     rdi, rdx
0x18004424a  mov     r14, [rsp+98h+arg_20]
0x180044252  xorps   xmm0, xmm0
0x180044255  mov     r15, [rsp+98h+arg_38]
0x18004425d  mov     rsi, r9
0x180044260  mov     rbp, r8
0x180044263  mov     ebx, ecx
0x180044265  lea     rdx, [rax+1]
0x180044269  mov     [rdi], rdx
0x18004426c  cmp     byte ptr [rdx], 5Eh ; '^'
0x18004426f  movups  xmmword ptr [rsp+98h+var_48], xmm0
0x180044274  movups  [rsp+98h+var_38], xmm0
0x180044279  jnz     short loc_180044284
0x18004427b  mov     r9b, [rdx+1]
0x18004427f  or      ebx, 8
0x180044282  jmp     short loc_180044287
0x180044284  mov     r9b, [rdx]
0x180044287  cmp     byte ptr [rdx], 5Eh ; '^'
0x18004428a  mov     r8d, 20h ; ' '
0x180044290  cmovnz  rdx, rax
0x180044294  movzx   eax, byte ptr [rsp+98h+var_48+0Bh]
0x180044299  cmp     r9b, 5Dh ; ']'
0x18004429d  cmovz   eax, r8d
0x1800442a1  lea     rcx, [rdx+1]
0x1800442a5  mov     byte ptr [rsp+98h+var_48+0Bh], al
0x1800442a9  cmovnz  rcx, rdx
0x1800442ad  lea     r8, [rcx+1]
0x1800442b1  mov     al, [r8]
0x1800442b4  cmp     al, 5Dh ; ']'
0x1800442b6  jz      loc_180044346
0x1800442bc  cmp     r9b, 5Dh ; ']'
0x1800442c0  setnz   r9b
0x1800442c4  dec     r9b
0x1800442c7  and     r9b, 5Dh
0x1800442cb  inc     r8
0x1800442ce  cmp     al, 2Dh ; '-'
0x1800442d0  jnz     short loc_180044323
0x1800442d2  test    r9b, r9b
0x1800442d5  jz      short loc_180044323
0x1800442d7  movzx   ecx, byte ptr [r8]
0x1800442db  cmp     cl, 5Dh ; ']'
0x1800442de  jz      short loc_180044323
0x1800442e0  inc     r8
0x1800442e3  movzx   eax, r9b
0x1800442e7  cmp     r9b, cl
0x1800442ea  movzx   r10d, r9b
0x1800442ee  mov     r11d, ecx
0x1800442f1  cmovnb  r11d, eax
0x1800442f5  cmovnb  r10d, ecx
0x1800442f9  jmp     short loc_180044319
0x1800442fb  movzx   edx, r10b
0x1800442ff  shr     rdx, 3
0x180044303  movzx   eax, r10b
0x180044307  and     eax, 7
0x18004430a  movsx   ecx, byte ptr [rsp+rdx+98h+var_48]
0x18004430f  bts     ecx, eax
0x180044312  mov     byte ptr [rsp+rdx+98h+var_48], cl
0x180044316  inc     r10b
0x180044319  cmp     r10b, r11b
0x18004431c  jbe     short loc_1800442FB
0x18004431e  xor     r9b, r9b
0x180044321  jmp     short loc_18004433F
0x180044323  movzx   edx, al
0x180044326  mov     r9b, al
0x180044329  shr     rdx, 3
0x18004432d  movzx   eax, al
0x180044330  and     eax, 7
0x180044333  movsx   ecx, byte ptr [rsp+rdx+98h+var_48]
0x180044338  bts     ecx, eax
0x18004433b  mov     byte ptr [rsp+rdx+98h+var_48], cl
0x18004433f  mov     al, [r8]
0x180044342  cmp     al, 5Dh ; ']'
0x180044344  jnz     short loc_1800442CB
0x180044346  mov     rax, [rsp+98h+arg_40]
0x18004434e  lea     rdx, [rsp+98h+var_48]; int
0x180044353  mov     [rsp+98h+var_58], rax; __int64
0x180044358  mov     r9, rsi; int
0x18004435b  mov     rax, [rsp+98h+arg_30]
0x180044363  mov     ecx, ebx; int
0x180044365  mov     [rsp+98h+Locale], r15; Locale
0x18004436a  mov     [rsp+98h+var_68], rax; __int64
0x18004436f  mov     eax, [rsp+98h+arg_28]
0x180044376  mov     [rdi], r8
0x180044379  mov     r8, rbp; int
0x18004437c  mov     [rsp+98h+var_70], eax; int
0x180044380  mov     qword ptr [rsp+98h+SrcCh], r14; SrcCh
0x180044385  call    ReadString_2
0x18004438a  mov     rbx, [rsp+98h+arg_18]
0x180044392  add     rsp, 70h
0x180044396  pop     r15
0x180044398  pop     r14
0x18004439a  pop     rdi
0x18004439b  pop     rsi
0x18004439c  pop     rbp
0x18004439d  retn
```
