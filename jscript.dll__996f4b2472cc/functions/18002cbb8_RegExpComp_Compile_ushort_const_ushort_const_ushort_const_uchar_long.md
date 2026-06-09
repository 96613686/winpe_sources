# RegExpComp::Compile(ushort const *,ushort const * *,ushort const * *,uchar * *,long *)

- ea: `0x18002cbb8`
- end: `0x18002ceb2`
- name: `?Compile@RegExpComp@@IEAAJPEBGPEAPEBG1PEAPEAEPEAJ@Z`
- size: `762`
- prototype: `__int64 __fastcall(RegExpComp *__hidden this, const unsigned __int16 *, const unsigned __int16 **, const unsigned __int16 **, unsigned __int8 **, int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18002c884`
- `0x18002c99c`

## callees

- `0x18002c2a4`
- `0x18002cbb8`
- `0x18002ceb8`
- `0x18002cf1c`
- `0x18002d028`
- `0x18002d200`
- `0x18002db10`
- `0x18004ea48`
- `0x180096662`
- `0x180096692`

## import_xrefs

- `msvcrt!free` at `0x18002ce96`
- `msvcrt!free` at `0x18002ce96`
- `msvcrt!realloc` at `0x18002cda4`
- `msvcrt!realloc` at `0x18002cda4`

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
      RegExpBase::PushByte(this, 17);
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
0x18002cbb8  mov     rax, rsp
0x18002cbbb  mov     [rax+20h], r9
0x18002cbbf  mov     [rax+18h], r8
0x18002cbc3  mov     [rax+10h], rdx
0x18002cbc7  mov     [rax+8], rcx
0x18002cbcb  push    rbp
0x18002cbcc  push    rbx
0x18002cbcd  push    rsi
0x18002cbce  push    rdi
0x18002cbcf  push    r14
0x18002cbd1  push    r15
0x18002cbd3  mov     rbp, rsp
0x18002cbd6  sub     rsp, 28h
0x18002cbda  mov     rax, [rbp+arg_20]
0x18002cbde  xor     r15d, r15d
0x18002cbe1  mov     [rcx+120h], rdx
0x18002cbe8  mov     rdx, rsp
0x18002cbeb  mov     [rcx+138h], r15
0x18002cbf2  mov     [rcx+118h], r15d
0x18002cbf9  mov     [rcx+100h], r15d
0x18002cc00  mov     [rax], r15
0x18002cc03  mov     rax, [rbp+arg_28]
0x18002cc07  mov     [rax], r15d
0x18002cc0a  call    _setjmp_0
0x18002cc0f  test    eax, eax
0x18002cc11  jnz     loc_18002CE48
0x18002cc17  mov     rbx, [rbp+arg_0]
0x18002cc1b  mov     rcx, rbx; this
0x18002cc1e  call    ?PnodeParse@RegExpComp@@IEAAPEAUNode@1@XZ; RegExpComp::PnodeParse(void)
0x18002cc23  xor     r8d, r8d; int
0x18002cc26  mov     rdx, rax; struct Node *
0x18002cc29  mov     rcx, rbx; this
0x18002cc2c  mov     rsi, rax
0x18002cc2f  call    ?AssignRemLen@RegExpComp@@IEAAJPEAUNode@1@J@Z; RegExpComp::AssignRemLen(RegExpComp::Node *,long)
0x18002cc34  mov     r14d, eax
0x18002cc37  mov     rax, [rbp+arg_10]
0x18002cc3b  test    rax, rax
0x18002cc3e  jz      short loc_18002CC4A
0x18002cc40  mov     rcx, [rbx+120h]
0x18002cc47  mov     [rax], rcx
0x18002cc4a  mov     rcx, [rbx+120h]
0x18002cc51  mov     rdx, [rbp+arg_18]
0x18002cc55  mov     rdi, rcx
0x18002cc58  sub     rdi, [rbp+Src]
0x18002cc5c  sar     rdi, 1
0x18002cc5f  add     edi, edi
0x18002cc61  test    rdx, rdx
0x18002cc64  jnz     loc_18002CDFB
0x18002cc6a  mov     rcx, [rbx+130h]; Block
0x18002cc71  test    rcx, rcx
0x18002cc74  jnz     loc_18002CE96
0x18002cc7a  mov     rax, [rbx+108h]
0x18002cc81  mov     edx, 24h ; '$'; int
0x18002cc86  mov     rcx, rbx; this
0x18002cc89  mov     [rbx+130h], rax
0x18002cc90  mov     [rbx+108h], r15
0x18002cc97  mov     [rbx+110h], r15d
0x18002cc9e  mov     [rbx+118h], r15d
0x18002cca5  call    ?EnsureSpace@RegExpBase@@IEAAXJ@Z; RegExpBase::EnsureSpace(long)
0x18002ccaa  mov     rax, [rbx+108h]
0x18002ccb1  xorps   xmm0, xmm0
0x18002ccb4  mov     dword ptr [rbx+118h], 24h ; '$'
0x18002ccbe  xor     ecx, ecx
0x18002ccc0  mov     rdx, rsi; struct Node *
0x18002ccc3  movups  xmmword ptr [rax], xmm0
0x18002ccc6  movups  xmmword ptr [rax+10h], xmm0
0x18002ccca  mov     [rax+20h], ecx
0x18002cccd  mov     rcx, rbx; this
0x18002ccd0  mov     rax, [rbx+108h]
0x18002ccd7  mov     dword ptr [rax], 4B74614Eh
0x18002ccdd  call    ?GenCode@RegExpComp@@IEAAXPEAUNode@1@@Z; RegExpComp::GenCode(RegExpComp::Node *)
0x18002cce2  mov     dl, 11h; unsigned __int8
0x18002cce4  mov     rcx, rbx; this
0x18002cce7  call    ?PushByte@RegExpBase@@IEAAXE@Z; RegExpBase::PushByte(uchar)
0x18002ccec  mov     ecx, [rbx+118h]
0x18002ccf2  test    cl, 1
0x18002ccf5  jnz     short loc_18002CCE2
0x18002ccf7  mov     rax, [rbx+108h]
0x18002ccfe  mov     [rax+0Ch], ecx
0x18002cd01  test    edi, edi
0x18002cd03  jle     short loc_18002CD4C
0x18002cd05  mov     eax, [rbx+118h]
0x18002cd0b  mov     rcx, rbx; this
0x18002cd0e  lea     esi, [rax+rdi]
0x18002cd11  cmp     esi, eax
0x18002cd13  jl      loc_18002CEA7
0x18002cd19  mov     edx, esi; int
0x18002cd1b  call    ?EnsureSpace@RegExpBase@@IEAAXJ@Z; RegExpBase::EnsureSpace(long)
0x18002cd20  movsxd  rcx, dword ptr [rbx+118h]
0x18002cd27  add     rcx, [rbx+108h]; void *
0x18002cd2e  mov     rdx, [rbp+Src]; Src
0x18002cd32  movsxd  r8, edi; Size
0x18002cd35  call    memcpy_0
0x18002cd3a  mov     [rbx+118h], esi
0x18002cd40  jmp     short loc_18002CD4C
0x18002cd42  xor     edx, edx; unsigned __int8
0x18002cd44  mov     rcx, rbx; this
0x18002cd47  call    ?PushByte@RegExpBase@@IEAAXE@Z; RegExpBase::PushByte(uchar)
0x18002cd4c  mov     eax, [rbx+118h]
0x18002cd52  test    al, 3
0x18002cd54  jnz     short loc_18002CD42
0x18002cd56  mov     rcx, [rbx+108h]
0x18002cd5d  mov     [rcx+4], eax
0x18002cd60  mov     dword ptr [rcx+8], 24h ; '$'
0x18002cd67  mov     eax, [rbx+138h]
0x18002cd6d  inc     eax
0x18002cd6f  mov     [rcx+18h], eax
0x18002cd72  mov     eax, [rbx+13Ch]
0x18002cd78  mov     [rcx+1Ch], eax
0x18002cd7b  mov     [rcx+10h], edi
0x18002cd7e  mov     [rcx+14h], r14d
0x18002cd82  mov     eax, [rbx+140h]
0x18002cd88  mov     [rcx+20h], eax
0x18002cd8b  movsxd  rax, dword ptr [rbx+118h]
0x18002cd92  cmp     eax, [rbx+110h]
0x18002cd98  jge     short loc_18002CDBC
0x18002cd9a  mov     rcx, [rbx+108h]; Block
0x18002cda1  mov     rdx, rax; Size
0x18002cda4  call    cs:__imp_realloc
0x18002cdab  nop     dword ptr [rax+rax+00h]
0x18002cdb0  test    rax, rax
0x18002cdb3  jz      short loc_18002CDBC
0x18002cdb5  mov     [rbx+108h], rax
0x18002cdbc  mov     rcx, [rbx+108h]
0x18002cdc3  mov     rax, [rbp+arg_20]
0x18002cdc7  mov     [rax], rcx
0x18002cdca  mov     rax, [rbp+arg_28]
0x18002cdce  mov     ecx, [rbx+118h]
0x18002cdd4  mov     [rbx+108h], r15
0x18002cddb  mov     [rax], ecx
0x18002cddd  xor     eax, eax
0x18002cddf  mov     [rbx+118h], r15d
0x18002cde6  mov     [rbx+110h], r15d
0x18002cded  add     rsp, 28h
0x18002cdf1  pop     r15
0x18002cdf3  pop     r14
0x18002cdf5  pop     rdi
0x18002cdf6  pop     rsi
0x18002cdf7  pop     rbx
0x18002cdf8  pop     rbp
0x18002cdf9  retn
0x18002cdfb  cmp     word ptr [rcx], 2Fh ; '/'
0x18002cdff  jnz     loc_18002CE8B
0x18002ce05  lea     rax, [rcx+2]
0x18002ce09  cmp     word ptr [rax], 69h ; 'i'
0x18002ce0d  jnz     short loc_18002CE1C
0x18002ce0f  or      dword ptr [rbx+140h], 1
0x18002ce16  add     rax, 2
0x18002ce1a  jmp     short loc_18002CE09
0x18002ce1c  cmp     word ptr [rax], 67h ; 'g'
0x18002ce20  jz      short loc_18002CE82
0x18002ce22  cmp     word ptr [rax], 6Dh ; 'm'
0x18002ce26  jz      short loc_18002CE79
0x18002ce28  mov     [rdx], rax
0x18002ce2b  test    byte ptr [rbx+140h], 1
0x18002ce32  jz      loc_18002CC6A
0x18002ce38  mov     rdx, rsi; struct Node *
0x18002ce3b  mov     rcx, rbx; this
0x18002ce3e  call    ?MapToLowerCase@RegExpComp@@IEAAXPEAUNode@1@@Z; RegExpComp::MapToLowerCase(RegExpComp::Node *)
0x18002ce43  jmp     loc_18002CC6A
0x18002ce48  mov     rcx, [rbp+arg_0]
0x18002ce4c  mov     eax, [rcx+100h]
0x18002ce52  cmp     eax, 8007000Eh
0x18002ce57  jz      short loc_18002CE61
0x18002ce59  add     qword ptr [rcx+120h], 0FFFFFFFFFFFFFFFEh
0x18002ce61  mov     rdx, [rbp+arg_10]
0x18002ce65  test    rdx, rdx
0x18002ce68  jz      short loc_18002CDED
0x18002ce6a  mov     rcx, [rcx+120h]
0x18002ce71  mov     [rdx], rcx
0x18002ce74  jmp     loc_18002CDED
0x18002ce79  or      dword ptr [rbx+140h], 4
0x18002ce80  jmp     short loc_18002CE16
0x18002ce82  or      dword ptr [rbx+140h], 2
0x18002ce89  jmp     short loc_18002CE16
0x18002ce8b  mov     rax, [rax]
0x18002ce8e  mov     [rdx], rax
0x18002ce91  jmp     loc_18002CC6A
0x18002ce96  call    cs:__imp_free
0x18002ce9d  nop     dword ptr [rax+rax+00h]
0x18002cea2  jmp     loc_18002CC7A
0x18002cea7  mov     edx, 8007000Eh; int
0x18002ceac  call    ?Error@RegExpBase@@IEAAXJ@Z; RegExpBase::Error(long)
```
