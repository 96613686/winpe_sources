# FsRtlCreateMidAtlas

- ea: `0x140035028`
- end: `0x1400351f9`
- name: `FsRtlCreateMidAtlas`
- size: `465`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001185c`

## callees

- `0x140035028`
- `0x140035230`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400350d7`
- `ntoskrnl!ExAllocatePool2` at `0x1400350d7`

## pseudocode

```c
__int64 __fastcall FsRtlCreateMidAtlas(unsigned __int16 a1, unsigned __int16 a2)
{
  unsigned __int16 v4; // bx
  char v5; // r14
  unsigned __int16 v6; // bp
  unsigned __int8 v7; // r12
  int v8; // ecx
  __int64 Pool2; // rax
  __int64 v10; // rdi
  __int64 v11; // rsi
  _QWORD *v12; // rbx
  _QWORD *v13; // rdx
  bool i; // zf
  __int64 *v15; // rax
  __int64 v16; // rcx
  __int64 *v17; // rax

  v4 = 256;
  v5 = 8;
  v6 = 256;
  v7 = 8;
  if ( a1 != 256 )
  {
    if ( a1 <= 0x100u )
    {
      do
      {
        v6 >>= 1;
        --v7;
      }
      while ( a1 < v6 );
      ++v7;
      v6 *= 2;
    }
    else
    {
      do
      {
        if ( a1 <= v6 )
          break;
        v6 *= 2;
        ++v7;
      }
      while ( v6 != 0x8000 );
    }
  }
  if ( a2 != 256 )
  {
    if ( a2 <= 0x100u )
    {
      do
      {
        v4 >>= 1;
        --v5;
      }
      while ( a2 < v4 );
      ++v5;
      v4 *= 2;
    }
    else
    {
      do
      {
        if ( a2 <= v4 )
          break;
        v4 *= 2;
        ++v5;
      }
      while ( v4 != 0x8000 );
    }
  }
  v8 = a2;
  if ( a1 != a2 )
    v8 = v4;
  Pool2 = ExAllocatePool2(66, (unsigned int)(8 * v8 + 96), 1632464211);
  v10 = Pool2;
  if ( Pool2 )
  {
    v11 = Pool2 + 56;
    *(_BYTE *)(Pool2 + 82) = 0;
    *(_DWORD *)(Pool2 + 4) = 0;
    *(_WORD *)Pool2 = a1;
    *(_WORD *)(Pool2 + 2) = a2;
    *(_WORD *)(Pool2 + 78) = v4 - 1;
    v12 = (_QWORD *)(Pool2 + 16);
    *(_DWORD *)(Pool2 + 74) = 0;
    *(_WORD *)(Pool2 + 72) = a2;
    *(_BYTE *)(Pool2 + 81) = v5;
    *(_WORD *)(Pool2 + 8) = v7;
    *(_BYTE *)(Pool2 + 80) = 0;
    *(_BYTE *)(Pool2 + 83) = 1;
    *(_QWORD *)(Pool2 + 24) = Pool2 + 16;
    *(_QWORD *)(Pool2 + 16) = Pool2 + 16;
    *(_QWORD *)(Pool2 + 40) = Pool2 + 32;
    *(_QWORD *)(Pool2 + 32) = Pool2 + 32;
    InitializeMidMapFreeList(Pool2 + 56);
    v13 = (_QWORD *)*v12;
    for ( i = *v12 == (_QWORD)v12; ; i = v13 == v12 )
    {
      if ( i )
        v13 = 0;
      if ( !v13 )
        goto LABEL_27;
      if ( *((_BYTE *)v13 + 27) >= *(_BYTE *)(v11 + 27) )
        break;
      v13 = (_QWORD *)*v13;
    }
    v15 = (__int64 *)v13[1];
    if ( v15 )
    {
      v16 = *v15;
      if ( *(__int64 **)(*v15 + 8) == v15 )
      {
        *(_QWORD *)v11 = v16;
        *(_QWORD *)(v11 + 8) = v15;
        *(_QWORD *)(v16 + 8) = v11;
        *v15 = v11;
        goto LABEL_29;
      }
    }
    else
    {
LABEL_27:
      v17 = *(__int64 **)(v10 + 24);
      if ( (_QWORD *)*v17 == v12 )
      {
        *(_QWORD *)v11 = v12;
        *(_QWORD *)(v11 + 8) = v17;
        *v17 = v11;
        *(_QWORD *)(v10 + 24) = v11;
LABEL_29:
        *(_QWORD *)(v10 + 48) = v11;
        if ( a1 <= a2 )
        {
          *(_WORD *)(v10 + 12) = 0;
          *(_BYTE *)(v10 + 15) = 1;
          *(_BYTE *)(v10 + 82) &= ~1u;
        }
        else
        {
          *(_BYTE *)(v10 + 82) |= 1u;
          *(_WORD *)(v10 + 12) = 32;
          *(_BYTE *)(v10 + 14) = 5;
          *(_BYTE *)(v10 + 15) = (v6 >> (*(_BYTE *)(v11 + 24) + 5) != 0) + 2;
        }
        return v10;
      }
    }
    __fastfail(3u);
  }
  return v10;
}

```

## disassembly

```asm
0x140035028  push    rbx
0x14003502a  push    rbp
0x14003502b  push    rsi
0x14003502c  push    rdi
0x14003502d  push    r12
0x14003502f  push    r13
0x140035031  push    r14
0x140035033  push    r15
0x140035035  sub     rsp, 28h
0x140035039  movzx   r13d, cx
0x14003503d  movzx   r15d, dx
0x140035041  mov     ebx, 100h
0x140035046  mov     r14b, 8
0x140035049  movzx   ebp, bx
0x14003504c  mov     r12b, r14b
0x14003504f  mov     ax, 1
0x140035053  mov     ecx, 8000h
0x140035058  cmp     bx, r13w
0x14003505c  jz      short loc_140035088
0x14003505e  jnb     short loc_140035073
0x140035060  cmp     r13w, bp
0x140035064  jbe     short loc_140035088
0x140035066  add     bp, bp
0x140035069  add     r12b, al
0x14003506c  cmp     bp, cx
0x14003506f  jnz     short loc_140035060
0x140035071  jmp     short loc_140035088
0x140035073  jbe     short loc_140035082
0x140035075  shr     bp, 1
0x140035078  add     r12b, 0FFh
0x14003507c  cmp     r13w, bp
0x140035080  jb      short loc_140035075
0x140035082  add     r12b, al
0x140035085  add     bp, bp
0x140035088  cmp     bx, r15w
0x14003508c  jz      short loc_1400350B8
0x14003508e  jnb     short loc_1400350A3
0x140035090  cmp     r15w, bx
0x140035094  jbe     short loc_1400350B8
0x140035096  add     bx, bx
0x140035099  add     r14b, al
0x14003509c  cmp     bx, cx
0x14003509f  jnz     short loc_140035090
0x1400350a1  jmp     short loc_1400350B8
0x1400350a3  jbe     short loc_1400350B2
0x1400350a5  shr     bx, 1
0x1400350a8  add     r14b, 0FFh
0x1400350ac  cmp     r15w, bx
0x1400350b0  jb      short loc_1400350A5
0x1400350b2  add     r14b, al
0x1400350b5  add     bx, bx
0x1400350b8  movzx   eax, bx
0x1400350bb  mov     ecx, r15d
0x1400350be  cmp     r13w, r15w
0x1400350c2  mov     r8d, 614D6D53h
0x1400350c8  cmovnz  ecx, eax
0x1400350cb  lea     edx, ds:60h[rcx*8]
0x1400350d2  mov     ecx, 42h ; 'B'
0x1400350d7  call    cs:__imp_ExAllocatePool2
0x1400350de  nop     dword ptr [rax+rax+00h]
0x1400350e3  xor     ecx, ecx
0x1400350e5  mov     rdi, rax
0x1400350e8  test    rax, rax
0x1400350eb  jz      loc_1400351CE
0x1400350f1  lea     rsi, [rax+38h]
0x1400350f5  dec     bx
0x1400350f8  mov     [rsi+1Ah], cl
0x1400350fb  mov     [rax+4], ecx
0x1400350fe  mov     [rax], r13w
0x140035102  mov     [rax+2], r15w
0x140035107  mov     [rsi+16h], bx
0x14003510b  lea     rbx, [rdi+10h]
0x14003510f  mov     [rsi+12h], ecx
0x140035112  mov     [rsi+10h], r15w
0x140035117  mov     [rsi+19h], r14b
0x14003511b  movzx   eax, r12b
0x14003511f  mov     [rdi+8], ax
0x140035123  lea     rax, [rdi+20h]
0x140035127  mov     [rsi+18h], cl
0x14003512a  mov     rcx, rsi
0x14003512d  mov     byte ptr [rsi+1Bh], 1
0x140035131  mov     [rbx+8], rbx
0x140035135  mov     [rbx], rbx
0x140035138  mov     [rax+8], rax
0x14003513c  mov     [rax], rax
0x14003513f  call    _InitializeMidMapFreeList
0x140035144  mov     rdx, [rbx]
0x140035147  xor     r8d, r8d
0x14003514a  cmp     rdx, rbx
0x14003514d  cmovz   rdx, r8
0x140035151  test    rdx, rdx
0x140035154  jz      short loc_14003518B
0x140035156  mov     al, [rsi+1Bh]
0x140035159  cmp     [rdx+1Bh], al
0x14003515c  jnb     short loc_140035169
0x14003515e  mov     rcx, [rdx]
0x140035161  mov     rdx, rcx
0x140035164  cmp     rcx, rbx
0x140035167  jmp     short loc_14003514D
0x140035169  mov     rax, [rdx+8]
0x14003516d  test    rax, rax
0x140035170  jz      short loc_14003518B
0x140035172  mov     rcx, [rax]
0x140035175  cmp     [rcx+8], rax
0x140035179  jnz     short loc_1400351F2
0x14003517b  mov     [rsi], rcx
0x14003517e  mov     [rsi+8], rax
0x140035182  mov     [rcx+8], rsi
0x140035186  mov     [rax], rsi
0x140035189  jmp     short loc_1400351A2
0x14003518b  mov     rax, [rbx+8]
0x14003518f  cmp     [rax], rbx
0x140035192  jnz     short loc_1400351F2
0x140035194  mov     [rsi], rbx
0x140035197  mov     [rsi+8], rax
0x14003519b  mov     [rax], rsi
0x14003519e  mov     [rbx+8], rsi
0x1400351a2  mov     [rdi+30h], rsi
0x1400351a6  cmp     r13w, r15w
0x1400351aa  jbe     short loc_1400351E3
0x1400351ac  or      byte ptr [rdi+52h], 1
0x1400351b0  mov     word ptr [rdi+0Ch], 20h ; ' '
0x1400351b6  mov     byte ptr [rdi+0Eh], 5
0x1400351ba  mov     cl, [rsi+18h]
0x1400351bd  add     cl, 5
0x1400351c0  shr     bp, cl
0x1400351c3  test    bp, bp
0x1400351c6  setnz   al
0x1400351c9  add     al, 2
0x1400351cb  mov     [rdi+0Fh], al
0x1400351ce  mov     rax, rdi
0x1400351d1  add     rsp, 28h
0x1400351d5  pop     r15
0x1400351d7  pop     r14
0x1400351d9  pop     r13
0x1400351db  pop     r12
0x1400351dd  pop     rdi
0x1400351de  pop     rsi
0x1400351df  pop     rbp
0x1400351e0  pop     rbx
0x1400351e1  retn
0x1400351e3  mov     [rdi+0Ch], r8w
0x1400351e8  mov     byte ptr [rdi+0Fh], 1
0x1400351ec  and     byte ptr [rdi+52h], 0FEh
0x1400351f0  jmp     short loc_1400351CE
0x1400351f2  mov     ecx, 3
0x1400351f7  int     29h; Win8: RtlFailFast(ecx)
```
