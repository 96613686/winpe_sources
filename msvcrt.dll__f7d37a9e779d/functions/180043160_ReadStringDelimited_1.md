# ReadStringDelimited_1

- ea: `0x180043160`
- end: `0x1800432bd`
- name: `ReadStringDelimited_1`
- size: `349`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18004339c`

## callees

- `0x180042fa8`
- `0x180043160`

## pseudocode

```c
__int64 __fastcall ReadStringDelimited_1(
        char a1,
        unsigned __int8 **a2,
        int *a3,
        _DWORD *a4,
        _QWORD *SrcCh,
        int a6,
        __crt_locale_pointers *Locale,
        _DWORD *a8)
{
  unsigned __int8 *v8; // rax
  char v12; // bl
  unsigned __int8 *v13; // r8
  bool v14; // zf
  unsigned __int8 v15; // dl
  char v16; // al
  unsigned __int8 *v17; // rcx
  unsigned __int8 *v18; // r8
  unsigned __int8 v19; // al
  unsigned __int8 v20; // r9
  unsigned __int8 v21; // cl
  unsigned __int8 v22; // r10
  unsigned __int8 v23; // r11
  int v25[4]; // [rsp+40h] [rbp-48h] BYREF
  __int128 v26; // [rsp+50h] [rbp-38h]

  v8 = *a2;
  v12 = a1;
  v13 = *a2 + 1;
  *a2 = v13;
  v14 = *v13 == 94;
  *(_OWORD *)v25 = 0;
  v26 = 0;
  if ( v14 )
  {
    v15 = v13[1];
    v12 = a1 | 8;
  }
  else
  {
    v15 = *v13;
  }
  if ( *v13 != 94 )
    v13 = v8;
  v16 = HIBYTE(v25[2]);
  if ( v15 == 93 )
    v16 = 32;
  v17 = v13 + 1;
  HIBYTE(v25[2]) = v16;
  if ( v15 != 93 )
    v17 = v13;
  v18 = v17 + 1;
  v19 = v17[1];
  if ( v19 != 93 )
  {
    v20 = v15 != 93 ? 0 : 0x5D;
    do
    {
      ++v18;
      if ( v19 == 45 && v20 && (v21 = *v18, *v18 != 93) )
      {
        ++v18;
        v22 = v20;
        v23 = v21;
        if ( v20 >= v21 )
        {
          v23 = v20;
          v22 = v21;
        }
        while ( v22 <= v23 )
        {
          *((_BYTE *)v25 + ((unsigned __int64)v22 >> 3)) |= 1 << (v22 & 7);
          ++v22;
        }
        v20 = 0;
      }
      else
      {
        v20 = v19;
        *((_BYTE *)v25 + ((unsigned __int64)v19 >> 3)) |= 1 << (v19 & 7);
      }
      v19 = *v18;
    }
    while ( *v18 != 93 );
  }
  *a2 = v18;
  return ReadString_1(v12, (__int64)v25, a3, a4, SrcCh, a6, Locale, a8);
}

```

## disassembly

```asm
0x180043160  mov     [rsp+arg_0], rbx
0x180043165  push    rbp
0x180043166  push    rsi
0x180043167  push    rdi
0x180043168  push    r14
0x18004316a  push    r15
0x18004316c  sub     rsp, 60h
0x180043170  mov     rax, [rdx]
0x180043173  xorps   xmm0, xmm0
0x180043176  mov     r14, [rsp+88h+arg_20]
0x18004317e  mov     rbp, r8
0x180043181  mov     r15, [rsp+88h+arg_30]
0x180043189  mov     rsi, r9
0x18004318c  mov     rdi, rdx
0x18004318f  mov     ebx, ecx
0x180043191  lea     r8, [rax+1]
0x180043195  mov     [rdx], r8
0x180043198  cmp     byte ptr [r8], 5Eh ; '^'
0x18004319c  movups  xmmword ptr [rsp+88h+var_48], xmm0
0x1800431a1  movups  [rsp+88h+var_38], xmm0
0x1800431a6  jnz     short loc_1800431B1
0x1800431a8  mov     dl, [r8+1]
0x1800431ac  or      ebx, 8
0x1800431af  jmp     short loc_1800431B4
0x1800431b1  mov     dl, [r8]
0x1800431b4  cmp     byte ptr [r8], 5Eh ; '^'
0x1800431b8  mov     r9d, 20h ; ' '
0x1800431be  cmovnz  r8, rax
0x1800431c2  movzx   eax, byte ptr [rsp+88h+var_48+0Bh]
0x1800431c7  cmp     dl, 5Dh ; ']'
0x1800431ca  cmovz   eax, r9d
0x1800431ce  lea     rcx, [r8+1]
0x1800431d2  mov     byte ptr [rsp+88h+var_48+0Bh], al
0x1800431d6  cmovnz  rcx, r8
0x1800431da  lea     r8, [rcx+1]
0x1800431de  mov     al, [r8]
0x1800431e1  cmp     al, 5Dh ; ']'
0x1800431e3  jz      loc_180043272
0x1800431e9  cmp     dl, 5Dh ; ']'
0x1800431ec  setnz   r9b
0x1800431f0  dec     r9b
0x1800431f3  and     r9b, 5Dh
0x1800431f7  inc     r8
0x1800431fa  cmp     al, 2Dh ; '-'
0x1800431fc  jnz     short loc_18004324F
0x1800431fe  test    r9b, r9b
0x180043201  jz      short loc_18004324F
0x180043203  movzx   ecx, byte ptr [r8]
0x180043207  cmp     cl, 5Dh ; ']'
0x18004320a  jz      short loc_18004324F
0x18004320c  inc     r8
0x18004320f  movzx   eax, r9b
0x180043213  cmp     r9b, cl
0x180043216  movzx   r10d, r9b
0x18004321a  mov     r11d, ecx
0x18004321d  cmovnb  r11d, eax
0x180043221  cmovnb  r10d, ecx
0x180043225  jmp     short loc_180043245
0x180043227  movzx   edx, r10b
0x18004322b  shr     rdx, 3
0x18004322f  movzx   eax, r10b
0x180043233  and     eax, 7
0x180043236  movsx   ecx, byte ptr [rsp+rdx+88h+var_48]
0x18004323b  bts     ecx, eax
0x18004323e  mov     byte ptr [rsp+rdx+88h+var_48], cl
0x180043242  inc     r10b
0x180043245  cmp     r10b, r11b
0x180043248  jbe     short loc_180043227
0x18004324a  xor     r9b, r9b
0x18004324d  jmp     short loc_18004326B
0x18004324f  movzx   edx, al
0x180043252  mov     r9b, al
0x180043255  shr     rdx, 3
0x180043259  movzx   eax, al
0x18004325c  and     eax, 7
0x18004325f  movsx   ecx, byte ptr [rsp+rdx+88h+var_48]
0x180043264  bts     ecx, eax
0x180043267  mov     byte ptr [rsp+rdx+88h+var_48], cl
0x18004326b  mov     al, [r8]
0x18004326e  cmp     al, 5Dh ; ']'
0x180043270  jnz     short loc_1800431F7
0x180043272  mov     rax, [rsp+88h+arg_38]
0x18004327a  lea     rdx, [rsp+88h+var_48]; int
0x18004327f  mov     [rsp+88h+var_50], rax; __int64
0x180043284  mov     r9, rsi; int
0x180043287  mov     eax, [rsp+88h+arg_28]
0x18004328e  mov     ecx, ebx; int
0x180043290  mov     [rsp+88h+Locale], r15; Locale
0x180043295  mov     [rdi], r8
0x180043298  mov     r8, rbp; int
0x18004329b  mov     [rsp+88h+var_60], eax; int
0x18004329f  mov     qword ptr [rsp+88h+SrcCh], r14; SrcCh
0x1800432a4  call    ReadString_1
0x1800432a9  mov     rbx, [rsp+88h+arg_0]
0x1800432b1  add     rsp, 60h
0x1800432b5  pop     r15
0x1800432b7  pop     r14
0x1800432b9  pop     rdi
0x1800432ba  pop     rsi
0x1800432bb  pop     rbp
0x1800432bc  retn
```
