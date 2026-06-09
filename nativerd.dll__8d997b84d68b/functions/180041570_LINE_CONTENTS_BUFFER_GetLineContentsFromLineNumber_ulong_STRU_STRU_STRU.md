# LINE_CONTENTS_BUFFER::GetLineContentsFromLineNumber(ulong,STRU *,STRU *,STRU *)

- ea: `0x180041570`
- end: `0x18004172f`
- name: `?GetLineContentsFromLineNumber@LINE_CONTENTS_BUFFER@@QEAAJKPEAVSTRU@@00@Z`
- size: `447`
- prototype: `__int64 __fastcall(LINE_CONTENTS_BUFFER *__hidden this, unsigned int, struct STRU *, struct STRU *, struct STRU *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180021130`
- `0x180026a50`

## callees

- `0x180041570`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180041664`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800416a3`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800416c3`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180041712`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180041664`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800416a3`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800416c3`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180041712`

## pseudocode

```c
int __fastcall LINE_CONTENTS_BUFFER::GetLineContentsFromLineNumber(
        LINE_CONTENTS_BUFFER *this,
        unsigned int a2,
        struct STRU *a3,
        struct STRU *a4,
        struct STRU *a5)
{
  int result; // eax
  const unsigned __int16 *v9; // rdx
  const unsigned __int16 *v10; // rdi
  unsigned int v11; // eax
  const unsigned __int16 **v12; // r8
  unsigned int v13; // r10d
  const unsigned __int16 *v14; // rcx
  unsigned int v15; // edx
  const unsigned __int16 *v16; // rbx
  const unsigned __int16 *v17; // rdx
  unsigned int v18; // r8d
  __int64 i; // rax
  const unsigned __int16 *v20; // rbx
  __int64 v21; // r8
  __int64 j; // rax
  _WORD *v23; // r8
  __int64 k; // rax
  STRU *v25; // rcx

  if ( !a3 || !a4 || !a5 )
    return -2147024809;
  result = 0;
  if ( !a2 )
    return result;
  v9 = (const unsigned __int16 *)*((_QWORD *)this + 1);
  v10 = &v9[*((unsigned int *)this + 1)];
  if ( a2 > 1 )
  {
    v11 = *(_DWORD *)this;
    v12 = (const unsigned __int16 **)((char *)this + 16);
    v13 = a2 - 1;
    if ( v13 < *(_DWORD *)this )
    {
      *(_DWORD *)this = 1;
      v11 = 1;
      *v12 = v9;
    }
    v14 = *v12;
    if ( *v12 >= v10 )
    {
      v16 = *v12;
      v15 = v11;
    }
    else
    {
      do
      {
        v15 = v11;
        v16 = v14;
        if ( v11 >= v13 )
          break;
        if ( *v14 == 10 )
          *(_DWORD *)this = ++v11;
        ++v14;
        v15 = v11;
        *v12 = v14;
        v16 = v14;
      }
      while ( v14 < v10 );
    }
    if ( v15 != v13 )
      v16 = 0;
    if ( !v16 )
      return -2147024894;
    v17 = v16;
    v18 = v10 - v16;
    for ( i = v18; ; --i )
    {
      if ( !i )
        goto LABEL_31;
      if ( *v16 == 10 )
        break;
      ++v16;
    }
    if ( !v16 )
    {
LABEL_31:
      result = STRU::Copy(a4, v17, v18);
      if ( result < 0 )
        return result;
      return -2147024894;
    }
    result = STRU::Copy(a4, v17, v16 - v17);
    if ( result < 0 )
      return result;
    v9 = v16 + 1;
  }
  if ( !v9 )
    return -2147024894;
  v20 = v9;
  LODWORD(v21) = v10 - v9;
  for ( j = (unsigned int)v21; ; --j )
  {
    if ( !j )
      goto LABEL_44;
    if ( *v20 == 10 )
      break;
    ++v20;
  }
  if ( !v20 )
  {
LABEL_44:
    v25 = a3;
    return STRU::Copy(v25, v9, v21);
  }
  result = STRU::Copy(a3, v9, v20 - v9);
  if ( result >= 0 )
  {
    v9 = v20 + 1;
    if ( v20 != (const unsigned __int16 *)-2LL )
    {
      v23 = v20 + 1;
      for ( k = (unsigned int)(v10 - v9); k; --k )
      {
        if ( *v23 == 10 )
        {
          if ( v23 )
          {
            v21 = v23 - v9;
            goto LABEL_43;
          }
          break;
        }
        ++v23;
      }
      LODWORD(v21) = v10 - v9;
LABEL_43:
      v25 = a5;
      return STRU::Copy(v25, v9, v21);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180041570  mov     [rsp+arg_0], rbx
0x180041575  mov     [rsp+arg_8], rbp
0x18004157a  push    rdi
0x18004157b  sub     rsp, 20h
0x18004157f  mov     rbp, r8
0x180041582  mov     r10d, edx
0x180041585  mov     r11, rcx
0x180041588  test    r8, r8
0x18004158b  jz      loc_18004171A
0x180041591  test    r9, r9
0x180041594  jz      loc_18004171A
0x18004159a  cmp     [rsp+28h+arg_20], 0
0x1800415a0  jz      loc_18004171A
0x1800415a6  xor     eax, eax
0x1800415a8  test    edx, edx
0x1800415aa  jz      loc_18004171F
0x1800415b0  mov     rdx, [rcx+8]
0x1800415b4  mov     eax, [rcx+4]
0x1800415b7  lea     rdi, [rdx+rax*2]
0x1800415bb  cmp     r10d, 1
0x1800415bf  jbe     loc_180041676
0x1800415c5  mov     eax, [rcx]
0x1800415c7  lea     r8, [rcx+10h]
0x1800415cb  dec     r10d
0x1800415ce  cmp     r10d, eax
0x1800415d1  jnb     short loc_1800415E1
0x1800415d3  mov     dword ptr [rcx], 1
0x1800415d9  mov     eax, 1
0x1800415de  mov     [r8], rdx
0x1800415e1  mov     rcx, [r8]
0x1800415e4  cmp     rcx, rdi
0x1800415e7  jnb     short loc_180041611
0x1800415e9  mov     edx, eax
0x1800415eb  mov     rbx, rcx
0x1800415ee  cmp     eax, r10d
0x1800415f1  jnb     short loc_180041616
0x1800415f3  cmp     word ptr [rcx], 0Ah
0x1800415f7  jnz     short loc_1800415FE
0x1800415f9  inc     eax
0x1800415fb  mov     [r11], eax
0x1800415fe  add     rcx, 2
0x180041602  mov     edx, eax
0x180041604  mov     [r8], rcx
0x180041607  mov     rbx, rcx
0x18004160a  cmp     rcx, rdi
0x18004160d  jb      short loc_1800415E9
0x18004160f  jmp     short loc_180041616
0x180041611  mov     rbx, rcx
0x180041614  mov     edx, eax
0x180041616  xor     eax, eax
0x180041618  cmp     edx, r10d
0x18004161b  cmovnz  rbx, rax
0x18004161f  test    rbx, rbx
0x180041622  jnz     short loc_18004162E
0x180041624  mov     eax, 80070002h
0x180041629  jmp     loc_18004171F
0x18004162e  mov     rax, rdi
0x180041631  mov     rdx, rbx
0x180041634  sub     rax, rbx
0x180041637  sar     rax, 1
0x18004163a  mov     r8d, eax
0x18004163d  mov     eax, eax
0x18004163f  test    rax, rax
0x180041642  jz      short loc_1800416A0
0x180041644  cmp     word ptr [rbx], 0Ah
0x180041648  jz      short loc_180041653
0x18004164a  add     rbx, 2
0x18004164e  dec     rax
0x180041651  jmp     short loc_18004163F
0x180041653  test    rbx, rbx
0x180041656  jz      short loc_1800416A0
0x180041658  mov     r8, rbx
0x18004165b  mov     rcx, r9
0x18004165e  sub     r8, rdx
0x180041661  sar     r8, 1
0x180041664  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18004166a  test    eax, eax
0x18004166c  js      loc_18004171F
0x180041672  lea     rdx, [rbx+2]
0x180041676  test    rdx, rdx
0x180041679  jz      short loc_180041624
0x18004167b  mov     rax, rdi
0x18004167e  mov     rbx, rdx
0x180041681  sub     rax, rdx
0x180041684  sar     rax, 1
0x180041687  mov     r8d, eax
0x18004168a  mov     eax, eax
0x18004168c  test    rax, rax
0x18004168f  jz      short loc_18004170F
0x180041691  cmp     word ptr [rbx], 0Ah
0x180041695  jz      short loc_1800416B2
0x180041697  add     rbx, 2
0x18004169b  dec     rax
0x18004169e  jmp     short loc_18004168C
0x1800416a0  mov     rcx, r9
0x1800416a3  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x1800416a9  test    eax, eax
0x1800416ab  js      short loc_18004171F
0x1800416ad  jmp     loc_180041624
0x1800416b2  test    rbx, rbx
0x1800416b5  jz      short loc_18004170F
0x1800416b7  mov     r8, rbx
0x1800416ba  mov     rcx, rbp
0x1800416bd  sub     r8, rdx
0x1800416c0  sar     r8, 1
0x1800416c3  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x1800416c9  test    eax, eax
0x1800416cb  js      short loc_18004171F
0x1800416cd  lea     rdx, [rbx+2]
0x1800416d1  test    rdx, rdx
0x1800416d4  jz      short loc_18004171F
0x1800416d6  sub     rdi, rdx
0x1800416d9  mov     r8, rdx
0x1800416dc  sar     rdi, 1
0x1800416df  mov     ecx, edi
0x1800416e1  mov     eax, edi
0x1800416e3  test    rax, rax
0x1800416e6  jz      short loc_180041705
0x1800416e8  cmp     word ptr [r8], 0Ah
0x1800416ed  jz      short loc_1800416F8
0x1800416ef  add     r8, 2
0x1800416f3  dec     rax
0x1800416f6  jmp     short loc_1800416E3
0x1800416f8  test    r8, r8
0x1800416fb  jz      short loc_180041705
0x1800416fd  sub     r8, rdx
0x180041700  sar     r8, 1
0x180041703  jmp     short loc_180041708
0x180041705  mov     r8d, ecx
0x180041708  mov     rcx, [rsp+28h+arg_20]
0x18004170d  jmp     short loc_180041712
0x18004170f  mov     rcx, rbp
0x180041712  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180041718  jmp     short loc_18004171F
0x18004171a  mov     eax, 80070057h
0x18004171f  mov     rbx, [rsp+28h+arg_0]
0x180041724  mov     rbp, [rsp+28h+arg_8]
0x180041729  add     rsp, 20h
0x18004172d  pop     rdi
0x18004172e  retn
```
