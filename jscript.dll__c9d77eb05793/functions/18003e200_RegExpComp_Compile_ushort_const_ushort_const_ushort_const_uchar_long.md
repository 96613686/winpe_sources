# RegExpComp::Compile(ushort const *,ushort const * *,ushort const * *,uchar * *,long *)

- ea: `0x18003e200`
- end: `0x18003e4ed`
- name: `?Compile@RegExpComp@@IEAAJPEBGPEAPEBG1PEAPEAEPEAJ@Z`
- size: `749`
- prototype: `__int64 __fastcall(RegExpComp *__hidden this, const unsigned __int16 *, const unsigned __int16 **, const unsigned __int16 **, unsigned __int8 **, int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18003dee4`
- `0x18003dff4`

## callees

- `0x18002eff4`
- `0x18003e200`
- `0x18003e4f4`
- `0x18003e554`
- `0x18003e640`
- `0x18003e814`
- `0x18003f118`
- `0x18004dbc4`
- `0x180094252`
- `0x180094282`

## import_xrefs

- `msvcrt!free` at `0x18003e4d7`
- `msvcrt!free` at `0x18003e4d7`
- `msvcrt!realloc` at `0x18003e3ec`
- `msvcrt!realloc` at `0x18003e3ec`

## pseudocode

```c
__int64 __fastcall RegExpComp::Compile(
        RegExpComp *this,
        const unsigned __int16 *a2,
        const unsigned __int16 **a3,
        const unsigned __int16 **a4,
        unsigned __int8 **a5,
        int *a6)
{
  struct Node *v6; // rsi
  int v7; // r14d
  _WORD *v8; // rcx
  int v9; // edi
  void *v10; // rcx
  __int64 v11; // rax
  int v12; // ecx
  int v13; // eax
  int v14; // esi
  int v15; // eax
  _DWORD *v16; // rcx
  void *v17; // rax
  int v18; // ecx
  __int64 result; // rax
  const unsigned __int16 *i; // rax

  *((_QWORD *)this + 36) = a2;
  *((_QWORD *)this + 39) = 0;
  *((_DWORD *)this + 70) = 0;
  *((_DWORD *)this + 64) = 0;
  *a5 = 0;
  *a6 = 0;
  if ( setjmp_0((_JBTYPE *)this) )
  {
    result = *((unsigned int *)this + 64);
    if ( (_DWORD)result != -2147024882 )
      *((_QWORD *)this + 36) -= 2LL;
    if ( a3 )
      *a3 = (const unsigned __int16 *)*((_QWORD *)this + 36);
  }
  else
  {
    v6 = RegExpComp::PnodeParse(this);
    v7 = RegExpComp::AssignRemLen(this, v6, 0);
    if ( a3 )
      *a3 = (const unsigned __int16 *)*((_QWORD *)this + 36);
    v8 = (_WORD *)*((_QWORD *)this + 36);
    v9 = 2 * (v8 - a2);
    if ( a4 )
    {
      if ( *v8 != 47 )
      {
        *a4 = *a3;
        goto LABEL_5;
      }
      for ( i = v8 + 1; ; ++i )
      {
        switch ( *i )
        {
          case 'i':
            *((_DWORD *)this + 80) |= 1u;
            break;
          case 'g':
            *((_DWORD *)this + 80) |= 2u;
            break;
          case 'm':
            *((_DWORD *)this + 80) |= 4u;
            break;
          default:
            *a4 = i;
            if ( (*((_BYTE *)this + 320) & 1) != 0 )
              RegExpComp::MapToLowerCase(this, v6);
            goto LABEL_5;
        }
      }
    }
LABEL_5:
    v10 = (void *)*((_QWORD *)this + 38);
    if ( v10 )
      free(v10);
    *((_QWORD *)this + 38) = *((_QWORD *)this + 33);
    *((_QWORD *)this + 33) = 0;
    *((_DWORD *)this + 68) = 0;
    *((_DWORD *)this + 70) = 0;
    RegExpBase::EnsureSpace(this, 36);
    v11 = *((_QWORD *)this + 33);
    *((_DWORD *)this + 70) = 36;
    *(_OWORD *)v11 = 0;
    *(_OWORD *)(v11 + 16) = 0;
    *(_DWORD *)(v11 + 32) = 0;
    **((_DWORD **)this + 33) = 1265918286;
    RegExpComp::GenCode(this, v6);
    do
    {
      RegExpBase::PushByte(this, 0x11u);
      v12 = *((_DWORD *)this + 70);
    }
    while ( (v12 & 1) != 0 );
    *(_DWORD *)(*((_QWORD *)this + 33) + 12LL) = v12;
    if ( v9 > 0 )
    {
      v13 = *((_DWORD *)this + 70);
      v14 = v13 + v9;
      if ( v13 + v9 < v13 )
        RegExpBase::Error(this, -2147024882);
      RegExpBase::EnsureSpace(this, v14);
      memcpy_0((void *)(*((_QWORD *)this + 33) + *((int *)this + 70)), a2, v9);
      *((_DWORD *)this + 70) = v14;
    }
    while ( 1 )
    {
      v15 = *((_DWORD *)this + 70);
      if ( (v15 & 3) == 0 )
        break;
      RegExpBase::PushByte(this, 0);
    }
    v16 = (_DWORD *)*((_QWORD *)this + 33);
    v16[1] = v15;
    v16[2] = 36;
    v16[6] = *((_DWORD *)this + 78) + 1;
    v16[7] = *((_DWORD *)this + 79);
    v16[4] = v9;
    v16[5] = v7;
    v16[8] = *((_DWORD *)this + 80);
    if ( *((_DWORD *)this + 70) < *((_DWORD *)this + 68) )
    {
      v17 = realloc(*((void **)this + 33), *((int *)this + 70));
      if ( v17 )
        *((_QWORD *)this + 33) = v17;
    }
    *a5 = (unsigned __int8 *)*((_QWORD *)this + 33);
    v18 = *((_DWORD *)this + 70);
    *((_QWORD *)this + 33) = 0;
    *a6 = v18;
    result = 0;
    *((_DWORD *)this + 70) = 0;
    *((_DWORD *)this + 68) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18003e200  mov     rax, rsp
0x18003e203  mov     [rax+20h], r9
0x18003e207  mov     [rax+18h], r8
0x18003e20b  mov     [rax+10h], rdx
0x18003e20f  mov     [rax+8], rcx
0x18003e213  push    rbp
0x18003e214  push    rbx
0x18003e215  push    rsi
0x18003e216  push    rdi
0x18003e217  push    r14
0x18003e219  push    r15
0x18003e21b  mov     rbp, rsp
0x18003e21e  sub     rsp, 28h
0x18003e222  mov     rax, [rbp+arg_20]
0x18003e226  xor     r15d, r15d
0x18003e229  mov     [rcx+120h], rdx
0x18003e230  mov     rdx, rsp
0x18003e233  mov     [rcx+138h], r15
0x18003e23a  mov     [rcx+118h], r15d
0x18003e241  mov     [rcx+100h], r15d
0x18003e248  mov     [rax], r15
0x18003e24b  mov     rax, [rbp+arg_28]
0x18003e24f  mov     [rax], r15d
0x18003e252  call    _setjmp_0
0x18003e257  test    eax, eax
0x18003e259  jnz     loc_18003E489
0x18003e25f  mov     rbx, [rbp+arg_0]
0x18003e263  mov     rcx, rbx; this
0x18003e266  call    ?PnodeParse@RegExpComp@@IEAAPEAUNode@1@XZ; RegExpComp::PnodeParse(void)
0x18003e26b  xor     r8d, r8d; int
0x18003e26e  mov     rdx, rax; struct Node *
0x18003e271  mov     rcx, rbx; this
0x18003e274  mov     rsi, rax
0x18003e277  call    ?AssignRemLen@RegExpComp@@IEAAJPEAUNode@1@J@Z; RegExpComp::AssignRemLen(RegExpComp::Node *,long)
0x18003e27c  mov     r14d, eax
0x18003e27f  mov     rax, [rbp+arg_10]
0x18003e283  test    rax, rax
0x18003e286  jz      short loc_18003E292
0x18003e288  mov     rcx, [rbx+120h]
0x18003e28f  mov     [rax], rcx
0x18003e292  mov     rcx, [rbx+120h]
0x18003e299  mov     rdx, [rbp+arg_18]
0x18003e29d  mov     rdi, rcx
0x18003e2a0  sub     rdi, [rbp+Src]
0x18003e2a4  sar     rdi, 1
0x18003e2a7  add     edi, edi
0x18003e2a9  test    rdx, rdx
0x18003e2ac  jnz     loc_18003E43C
0x18003e2b2  mov     rcx, [rbx+130h]; Block
0x18003e2b9  test    rcx, rcx
0x18003e2bc  jnz     loc_18003E4D7
0x18003e2c2  mov     rax, [rbx+108h]
0x18003e2c9  mov     edx, 24h ; '$'; int
0x18003e2ce  mov     rcx, rbx; this
0x18003e2d1  mov     [rbx+130h], rax
0x18003e2d8  mov     [rbx+108h], r15
0x18003e2df  mov     [rbx+110h], r15d
0x18003e2e6  mov     [rbx+118h], r15d
0x18003e2ed  call    ?EnsureSpace@RegExpBase@@IEAAXJ@Z; RegExpBase::EnsureSpace(long)
0x18003e2f2  mov     rax, [rbx+108h]
0x18003e2f9  xorps   xmm0, xmm0
0x18003e2fc  mov     dword ptr [rbx+118h], 24h ; '$'
0x18003e306  xor     ecx, ecx
0x18003e308  mov     rdx, rsi; struct Node *
0x18003e30b  movups  xmmword ptr [rax], xmm0
0x18003e30e  movups  xmmword ptr [rax+10h], xmm0
0x18003e312  mov     [rax+20h], ecx
0x18003e315  mov     rcx, rbx; this
0x18003e318  mov     rax, [rbx+108h]
0x18003e31f  mov     dword ptr [rax], 4B74614Eh
0x18003e325  call    ?GenCode@RegExpComp@@IEAAXPEAUNode@1@@Z; RegExpComp::GenCode(RegExpComp::Node *)
0x18003e32a  mov     dl, 11h; unsigned __int8
0x18003e32c  mov     rcx, rbx; this
0x18003e32f  call    ?PushByte@RegExpBase@@IEAAXE@Z; RegExpBase::PushByte(uchar)
0x18003e334  mov     ecx, [rbx+118h]
0x18003e33a  test    cl, 1
0x18003e33d  jnz     short loc_18003E32A
0x18003e33f  mov     rax, [rbx+108h]
0x18003e346  mov     [rax+0Ch], ecx
0x18003e349  test    edi, edi
0x18003e34b  jle     short loc_18003E394
0x18003e34d  mov     eax, [rbx+118h]
0x18003e353  mov     rcx, rbx; this
0x18003e356  lea     esi, [rax+rdi]
0x18003e359  cmp     esi, eax
0x18003e35b  jl      loc_18003E4E2
0x18003e361  mov     edx, esi; int
0x18003e363  call    ?EnsureSpace@RegExpBase@@IEAAXJ@Z; RegExpBase::EnsureSpace(long)
0x18003e368  movsxd  rcx, dword ptr [rbx+118h]
0x18003e36f  add     rcx, [rbx+108h]; void *
0x18003e376  mov     rdx, [rbp+Src]; Src
0x18003e37a  movsxd  r8, edi; Size
0x18003e37d  call    memcpy_0
0x18003e382  mov     [rbx+118h], esi
0x18003e388  jmp     short loc_18003E394
0x18003e38a  xor     edx, edx; unsigned __int8
0x18003e38c  mov     rcx, rbx; this
0x18003e38f  call    ?PushByte@RegExpBase@@IEAAXE@Z; RegExpBase::PushByte(uchar)
0x18003e394  mov     eax, [rbx+118h]
0x18003e39a  test    al, 3
0x18003e39c  jnz     short loc_18003E38A
0x18003e39e  mov     rcx, [rbx+108h]
0x18003e3a5  mov     [rcx+4], eax
0x18003e3a8  mov     dword ptr [rcx+8], 24h ; '$'
0x18003e3af  mov     eax, [rbx+138h]
0x18003e3b5  inc     eax
0x18003e3b7  mov     [rcx+18h], eax
0x18003e3ba  mov     eax, [rbx+13Ch]
0x18003e3c0  mov     [rcx+1Ch], eax
0x18003e3c3  mov     [rcx+10h], edi
0x18003e3c6  mov     [rcx+14h], r14d
0x18003e3ca  mov     eax, [rbx+140h]
0x18003e3d0  mov     [rcx+20h], eax
0x18003e3d3  movsxd  rax, dword ptr [rbx+118h]
0x18003e3da  cmp     eax, [rbx+110h]
0x18003e3e0  jge     short loc_18003E3FE
0x18003e3e2  mov     rcx, [rbx+108h]; Block
0x18003e3e9  mov     rdx, rax; Size
0x18003e3ec  call    cs:__imp_realloc
0x18003e3f2  test    rax, rax
0x18003e3f5  jz      short loc_18003E3FE
0x18003e3f7  mov     [rbx+108h], rax
0x18003e3fe  mov     rcx, [rbx+108h]
0x18003e405  mov     rax, [rbp+arg_20]
0x18003e409  mov     [rax], rcx
0x18003e40c  mov     rax, [rbp+arg_28]
0x18003e410  mov     ecx, [rbx+118h]
0x18003e416  mov     [rbx+108h], r15
0x18003e41d  mov     [rax], ecx
0x18003e41f  xor     eax, eax
0x18003e421  mov     [rbx+118h], r15d
0x18003e428  mov     [rbx+110h], r15d
0x18003e42f  add     rsp, 28h
0x18003e433  pop     r15
0x18003e435  pop     r14
0x18003e437  pop     rdi
0x18003e438  pop     rsi
0x18003e439  pop     rbx
0x18003e43a  pop     rbp
0x18003e43b  retn
0x18003e43c  cmp     word ptr [rcx], 2Fh ; '/'
0x18003e440  jnz     loc_18003E4CC
0x18003e446  lea     rax, [rcx+2]
0x18003e44a  cmp     word ptr [rax], 69h ; 'i'
0x18003e44e  jnz     short loc_18003E45D
0x18003e450  or      dword ptr [rbx+140h], 1
0x18003e457  add     rax, 2
0x18003e45b  jmp     short loc_18003E44A
0x18003e45d  cmp     word ptr [rax], 67h ; 'g'
0x18003e461  jz      short loc_18003E4C3
0x18003e463  cmp     word ptr [rax], 6Dh ; 'm'
0x18003e467  jz      short loc_18003E4BA
0x18003e469  mov     [rdx], rax
0x18003e46c  test    byte ptr [rbx+140h], 1
0x18003e473  jz      loc_18003E2B2
0x18003e479  mov     rdx, rsi; struct Node *
0x18003e47c  mov     rcx, rbx; this
0x18003e47f  call    ?MapToLowerCase@RegExpComp@@IEAAXPEAUNode@1@@Z; RegExpComp::MapToLowerCase(RegExpComp::Node *)
0x18003e484  jmp     loc_18003E2B2
0x18003e489  mov     rcx, [rbp+arg_0]
0x18003e48d  mov     eax, [rcx+100h]
0x18003e493  cmp     eax, 8007000Eh
0x18003e498  jz      short loc_18003E4A2
0x18003e49a  add     qword ptr [rcx+120h], 0FFFFFFFFFFFFFFFEh
0x18003e4a2  mov     rdx, [rbp+arg_10]
0x18003e4a6  test    rdx, rdx
0x18003e4a9  jz      short loc_18003E42F
0x18003e4ab  mov     rcx, [rcx+120h]
0x18003e4b2  mov     [rdx], rcx
0x18003e4b5  jmp     loc_18003E42F
0x18003e4ba  or      dword ptr [rbx+140h], 4
0x18003e4c1  jmp     short loc_18003E457
0x18003e4c3  or      dword ptr [rbx+140h], 2
0x18003e4ca  jmp     short loc_18003E457
0x18003e4cc  mov     rax, [rax]
0x18003e4cf  mov     [rdx], rax
0x18003e4d2  jmp     loc_18003E2B2
0x18003e4d7  call    cs:__imp_free
0x18003e4dd  jmp     loc_18003E2C2
0x18003e4e2  mov     edx, 8007000Eh; int
0x18003e4e7  call    ?Error@RegExpBase@@IEAAXJ@Z; RegExpBase::Error(long)
```
