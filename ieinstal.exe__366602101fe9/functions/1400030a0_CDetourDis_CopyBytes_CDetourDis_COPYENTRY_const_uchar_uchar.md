# CDetourDis::CopyBytes(CDetourDis::COPYENTRY const *,uchar *,uchar *)

- ea: `0x1400030a0`
- end: `0x1400032e1`
- name: `?CopyBytes@CDetourDis@@IEAAPEAEPEBUCOPYENTRY@1@PEAE1@Z`
- size: `577`
- prototype: `unsigned __int8 *(CDetourDis *__hidden this, const struct CDetourDis::COPYENTRY *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400035c0`
- `0x1400035f0`
- `0x140003620`

## callees

- `0x1400030a0`
- `0x140003965`

## pseudocode

```c
unsigned __int8 *__fastcall CDetourDis::CopyBytes(
        CDetourDis *this,
        const struct CDetourDis::COPYENTRY *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  unsigned int v4; // r11d
  int v6; // r12d
  __int64 v7; // r8
  int v8; // r10d
  bool v12; // zf
  unsigned int v13; // r10d
  int v14; // esi
  int v15; // ebx
  __int64 v16; // rdx
  char v17; // cl
  char v18; // dl
  int v19; // r11d
  __int64 v20; // r15
  unsigned __int8 *v21; // rdx
  __int64 v22; // rcx
  unsigned __int8 *v23; // rax
  int v24; // ebx
  int v25; // ebx
  int v26; // ebx

  v4 = *(_DWORD *)a2;
  v6 = *(_DWORD *)a2 >> 28;
  v7 = HIWORD(*(_DWORD *)a2) & 0xF;
  v8 = *(_DWORD *)a2 >> 8;
  if ( (v6 & 2) != 0 )
  {
    v12 = *((_DWORD *)this + 1) == 0;
  }
  else
  {
    if ( *((_DWORD *)this + 2) )
    {
      v13 = ((*(_DWORD *)a2 >> 29) & 4) + (v8 & 0xF);
      goto LABEL_9;
    }
    v12 = *(_DWORD *)this == 0;
  }
  if ( !v12 )
    LOBYTE(v8) = *(_DWORD *)a2 >> 12;
  v13 = v8 & 0xF;
LABEL_9:
  v14 = (v4 >> 20) & 0xF;
  v15 = v13 - v14;
  if ( !(_DWORD)v7 )
    goto LABEL_24;
  v16 = a4[v7];
  v17 = *((_BYTE *)&CDetourDis::s_rbModRm + v16);
  v13 += v17 & 0xF;
  if ( (v17 & 0x10) != 0 )
  {
    if ( (a4[(unsigned int)(v7 + 1)] & 7) == 5 )
    {
      v18 = v16 & 0xC0;
      switch ( v18 )
      {
        case 0:
          goto LABEL_16;
        case 0x40:
          v15 = ++v13 - v14;
          goto LABEL_24;
        case 0x80:
LABEL_16:
          v13 += 4;
          break;
      }
    }
    v15 = v13 - v14;
  }
  else if ( (v17 & 0x20) != 0 )
  {
    v19 = HIBYTE(v4) & 0xF;
    if ( v19 == 4 && *(_DWORD *)this && !*((_DWORD *)this + 2) )
      v19 = 2;
    v15 = 4;
    v14 = v13 - v19 - 4;
  }
LABEL_24:
  v20 = v13;
  memcpy_0(a3, a4, v13);
  if ( !v14 )
    goto LABEL_47;
  v21 = &a3[v14];
  switch ( v15 )
  {
    case 1:
      v22 = (char)*v21;
      v23 = &a4[v22 - (_QWORD)a3];
      goto LABEL_43;
    case 2:
      v22 = *(__int16 *)v21;
      v23 = &a4[v22 - (_QWORD)a3];
LABEL_40:
      *(_WORD *)v21 = (_WORD)v23;
      if ( (unsigned __int64)(v23 + 0x8000) > 0xFFFF )
        **((_DWORD **)this + 5) = 2;
      goto LABEL_45;
    case 4:
      v22 = *(int *)v21;
      v23 = &a4[v22 - (_QWORD)a3];
LABEL_37:
      *(_DWORD *)v21 = (_DWORD)v23;
      if ( (unsigned __int64)(v23 + 0x80000000LL) > 0xFFFFFFFF )
        **((_DWORD **)this + 5) = 0;
      goto LABEL_45;
    case 8:
      v22 = *(_QWORD *)v21;
      v23 = &a4[*(_QWORD *)v21 - (_QWORD)a3];
      goto LABEL_35;
  }
  v22 = 0;
  v23 = (unsigned __int8 *)(a4 - a3);
  v24 = v15 - 1;
  if ( !v24 )
  {
LABEL_43:
    *v21 = (unsigned __int8)v23;
    if ( (unsigned __int64)(v23 + 128) > 0xFF )
      **((_DWORD **)this + 5) = 3;
    goto LABEL_45;
  }
  v25 = v24 - 1;
  if ( !v25 )
    goto LABEL_40;
  v26 = v25 - 2;
  if ( !v26 )
    goto LABEL_37;
  if ( v26 == 4 )
LABEL_35:
    *(_QWORD *)v21 = v23;
LABEL_45:
  **((_QWORD **)this + 4) = &a4[v20 + v22];
  if ( (*(_DWORD *)a2 & 0xF00000) == 0 )
    **((_QWORD **)this + 4) = 0;
LABEL_47:
  if ( (v6 & 4) != 0 )
    **((_DWORD **)this + 5) = -**((_DWORD **)this + 5);
  if ( (v6 & 1) != 0 )
    **((_QWORD **)this + 4) = -1;
  return &a4[v20];
}

```

## disassembly

```asm
0x1400030a0  push    rbx
0x1400030a2  push    rbp
0x1400030a3  push    rsi
0x1400030a4  push    rdi
0x1400030a5  push    r12
0x1400030a7  push    r13
0x1400030a9  push    r14
0x1400030ab  push    r15
0x1400030ad  sub     rsp, 28h
0x1400030b1  mov     r11d, [rdx]
0x1400030b4  mov     r14, r8
0x1400030b7  mov     r8d, r11d
0x1400030ba  mov     r12d, r11d
0x1400030bd  shr     r8d, 10h
0x1400030c1  mov     r10d, r11d
0x1400030c4  mov     eax, r11d
0x1400030c7  shr     r12d, 1Ch
0x1400030cb  and     r8d, 0Fh
0x1400030cf  shr     r10d, 8
0x1400030d3  shr     eax, 0Ch
0x1400030d6  mov     rbp, r9
0x1400030d9  mov     r13, rdx
0x1400030dc  mov     rdi, rcx
0x1400030df  test    r12b, 2
0x1400030e3  jz      short loc_1400030EB
0x1400030e5  cmp     dword ptr [rcx+4], 0
0x1400030e9  jmp     short loc_140003105
0x1400030eb  cmp     dword ptr [rcx+8], 0
0x1400030ef  jz      short loc_140003102
0x1400030f1  mov     ecx, r12d
0x1400030f4  and     r10d, 0Fh
0x1400030f8  shr     ecx, 1
0x1400030fa  and     ecx, 4
0x1400030fd  add     r10d, ecx
0x140003100  jmp     short loc_14000310D
0x140003102  cmp     dword ptr [rcx], 0
0x140003105  cmovnz  r10d, eax
0x140003109  and     r10d, 0Fh
0x14000310d  mov     esi, r11d
0x140003110  mov     ebx, r10d
0x140003113  shr     esi, 14h
0x140003116  mov     r9d, 2
0x14000311c  and     esi, 0Fh
0x14000311f  sub     ebx, esi
0x140003121  test    r8d, r8d
0x140003124  jz      short loc_1400031A3
0x140003126  movzx   edx, byte ptr [r8+rbp]
0x14000312b  lea     rax, ?s_rbModRm@CDetourDis@@1QBEB; uchar const near * const CDetourDis::s_rbModRm
0x140003132  movzx   ecx, byte ptr [rdx+rax]
0x140003136  mov     eax, ecx
0x140003138  and     eax, 0Fh
0x14000313b  add     r10d, eax
0x14000313e  test    cl, 10h
0x140003141  jz      short loc_140003175
0x140003143  lea     eax, [r8+1]
0x140003147  movzx   eax, byte ptr [rax+rbp]
0x14000314b  and     al, 7
0x14000314d  cmp     al, 5
0x14000314f  jnz     short loc_14000316E
0x140003151  and     dl, 0C0h
0x140003154  jz      short loc_14000316A
0x140003156  cmp     dl, 40h ; '@'
0x140003159  jnz     short loc_140003165
0x14000315b  inc     r10d
0x14000315e  mov     ebx, r10d
0x140003161  sub     ebx, esi
0x140003163  jmp     short loc_1400031A3
0x140003165  cmp     dl, 80h
0x140003168  jnz     short loc_14000316E
0x14000316a  add     r10d, 4
0x14000316e  mov     ebx, r10d
0x140003171  sub     ebx, esi
0x140003173  jmp     short loc_1400031A3
0x140003175  test    cl, 20h
0x140003178  jz      short loc_1400031A3
0x14000317a  shr     r11d, 18h
0x14000317e  and     r11d, 0Fh
0x140003182  cmp     r11d, 4
0x140003186  jnz     short loc_140003195
0x140003188  cmp     dword ptr [rdi], 0
0x14000318b  jz      short loc_140003195
0x14000318d  cmp     dword ptr [rdi+8], 0
0x140003191  cmovz   r11d, r9d
0x140003195  mov     esi, r10d
0x140003198  mov     ebx, 4
0x14000319d  sub     esi, r11d
0x1400031a0  sub     esi, 4
0x1400031a3  mov     r8d, r10d; Size
0x1400031a6  mov     rdx, rbp; Src
0x1400031a9  mov     rcx, r14; void *
0x1400031ac  mov     r15d, r10d
0x1400031af  call    memcpy_0
0x1400031b4  test    esi, esi
0x1400031b6  jz      loc_1400032AB
0x1400031bc  mov     edx, esi
0x1400031be  mov     eax, ebx
0x1400031c0  add     rdx, r14
0x1400031c3  xor     r8d, r8d
0x1400031c6  sub     eax, 1
0x1400031c9  jz      loc_140003268
0x1400031cf  sub     eax, 1
0x1400031d2  jz      short loc_14000323E
0x1400031d4  sub     eax, 2
0x1400031d7  jz      short loc_140003215
0x1400031d9  cmp     eax, 4
0x1400031dc  jz      short loc_140003204
0x1400031de  mov     rax, rbp
0x1400031e1  mov     ecx, r8d
0x1400031e4  sub     rax, r14
0x1400031e7  sub     ebx, 1
0x1400031ea  jz      loc_140003275
0x1400031f0  sub     ebx, 1
0x1400031f3  jz      short loc_14000324B
0x1400031f5  sub     ebx, 2
0x1400031f8  jz      short loc_140003221
0x1400031fa  cmp     ebx, 4
0x1400031fd  jz      short loc_140003210
0x1400031ff  jmp     loc_14000328D
0x140003204  mov     rcx, [rdx]
0x140003207  mov     rax, rcx
0x14000320a  sub     rax, r14
0x14000320d  add     rax, rbp
0x140003210  mov     [rdx], rax
0x140003213  jmp     short loc_14000328D
0x140003215  movsxd  rcx, dword ptr [rdx]
0x140003218  mov     rax, rcx
0x14000321b  sub     rax, r14
0x14000321e  add     rax, rbp
0x140003221  mov     [rdx], eax
0x140003223  mov     edx, 80000000h
0x140003228  add     rax, rdx
0x14000322b  mov     edx, 0FFFFFFFFh
0x140003230  cmp     rax, rdx
0x140003233  jbe     short loc_14000328D
0x140003235  mov     rax, [rdi+28h]
0x140003239  mov     [rax], r8d
0x14000323c  jmp     short loc_14000328D
0x14000323e  movsx   rcx, word ptr [rdx]
0x140003242  mov     rax, rcx
0x140003245  sub     rax, r14
0x140003248  add     rax, rbp
0x14000324b  mov     [rdx], ax
0x14000324e  add     rax, 8000h
0x140003254  cmp     rax, 0FFFFh
0x14000325a  jbe     short loc_14000328D
0x14000325c  mov     rax, [rdi+28h]
0x140003260  mov     dword ptr [rax], 2
0x140003266  jmp     short loc_14000328D
0x140003268  movsx   rcx, byte ptr [rdx]
0x14000326c  mov     rax, rcx
0x14000326f  sub     rax, r14
0x140003272  add     rax, rbp
0x140003275  mov     [rdx], al
0x140003277  sub     rax, 0FFFFFFFFFFFFFF80h
0x14000327b  cmp     rax, 0FFh
0x140003281  jbe     short loc_14000328D
0x140003283  mov     rax, [rdi+28h]
0x140003287  mov     dword ptr [rax], 3
0x14000328d  mov     rax, [rdi+20h]
0x140003291  add     rcx, r15
0x140003294  add     rcx, rbp
0x140003297  mov     [rax], rcx
0x14000329a  test    dword ptr [r13+0], 0F00000h
0x1400032a2  jnz     short loc_1400032AB
0x1400032a4  mov     rax, [rdi+20h]
0x1400032a8  mov     [rax], r8
0x1400032ab  test    r12b, 4
0x1400032af  jz      short loc_1400032BB
0x1400032b1  mov     rcx, [rdi+28h]
0x1400032b5  mov     eax, [rcx]
0x1400032b7  neg     eax
0x1400032b9  mov     [rcx], eax
0x1400032bb  test    r12b, 1
0x1400032bf  jz      short loc_1400032CC
0x1400032c1  mov     rax, [rdi+20h]
0x1400032c5  mov     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x1400032cc  lea     rax, [r15+rbp]
0x1400032d0  add     rsp, 28h
0x1400032d4  pop     r15
0x1400032d6  pop     r14
0x1400032d8  pop     r13
0x1400032da  pop     r12
0x1400032dc  pop     rdi
0x1400032dd  pop     rsi
0x1400032de  pop     rbp
0x1400032df  pop     rbx
0x1400032e0  retn
```
