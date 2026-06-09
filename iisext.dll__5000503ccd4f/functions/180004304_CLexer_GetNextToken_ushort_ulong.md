# CLexer::GetNextToken(ushort *,ulong *)

- ea: `0x180004304`
- end: `0x180004493`
- name: `?GetNextToken@CLexer@@QEAAJPEAGPEAK@Z`
- size: `399`
- prototype: `int(CLexer *__hidden this, unsigned __int16 *, unsigned int *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003fdc`
- `0x18000449c`
- `0x180004628`
- `0x180004790`

## callees

- `0x180004304`
- `0x1800111ae`

## pseudocode

```c
__int64 __fastcall CLexer::GetNextToken(CLexer *this, unsigned __int16 *a2, unsigned int *a3)
{
  unsigned __int16 *v3; // r14
  int v6; // esi
  unsigned __int16 *v7; // rcx
  unsigned __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // eax

  v3 = a2;
  v6 = 0;
  memset_0(a2, 0, 0x209u);
  *((_DWORD *)this + 4) = 0;
  while ( 1 )
  {
    v7 = *(unsigned __int16 **)this;
    if ( *(_QWORD *)this && (v8 = *v7, (_WORD)v8) )
    {
      *(_QWORD *)this = ++v7;
    }
    else
    {
      *((_DWORD *)this + 6) = 1;
      v8 = 0;
    }
    if ( v6 )
    {
      if ( (_WORD)v8 == 92 || (unsigned __int16)v8 <= 0x3Du && (v9 = 0x2400900000000001LL, _bittest64(&v9, v8)) )
      {
        if ( !*((_DWORD *)this + 6) )
          *(_QWORD *)this = v7 - 1;
LABEL_32:
        *a3 = 1;
        *((_DWORD *)this + 5) = 1;
        return 0;
      }
      if ( ((_WORD)v8 == 64 || (_WORD)v8 == 33) && !*((_DWORD *)this + 7) )
      {
        if ( !*((_DWORD *)this + 6) )
          *(_QWORD *)this -= 2LL;
        goto LABEL_32;
      }
      v10 = *((_DWORD *)this + 4);
      *((_DWORD *)this + 4) = v10 + 1;
      if ( v10 >= 0x105 )
        return 2147942523LL;
      *v3 = v8;
      goto LABEL_29;
    }
    v11 = *((_DWORD *)this + 4);
    *((_DWORD *)this + 4) = v11 + 1;
    if ( v11 >= 0x105 )
      return 2147942523LL;
    *v3 = v8;
    switch ( (_WORD)v8 )
    {
      case 0x5C:
        v12 = 3;
        goto LABEL_40;
      case 0x2F:
        v12 = 14;
        goto LABEL_40;
      case 0x2C:
        *a3 = 2;
        *((_DWORD *)this + 5) = 2;
        return 0;
      case 0x3D:
        v12 = 25;
        goto LABEL_40;
      case 0x3A:
        v12 = 13;
        goto LABEL_40;
      case 0:
        v12 = 4;
LABEL_40:
        *a3 = v12;
        *((_DWORD *)this + 5) = v12;
        return 0;
      case 0x40:
        if ( !*((_DWORD *)this + 7) )
        {
          v12 = 11;
          goto LABEL_40;
        }
        break;
      default:
        if ( (_WORD)v8 == 33 && !*((_DWORD *)this + 7) )
        {
          v12 = 12;
          goto LABEL_40;
        }
        break;
    }
LABEL_29:
    v6 = 1;
    ++v3;
  }
}

```

## disassembly

```asm
0x180004304  push    rbx
0x180004306  push    rbp
0x180004307  push    rsi
0x180004308  push    rdi
0x180004309  push    r14
0x18000430b  sub     rsp, 20h
0x18000430f  mov     r14, rdx
0x180004312  mov     rdi, r8
0x180004315  mov     rbx, rcx
0x180004318  xor     ebp, ebp
0x18000431a  mov     rcx, r14; void *
0x18000431d  xor     edx, edx; Val
0x18000431f  mov     r8d, 209h; Size
0x180004325  mov     esi, ebp
0x180004327  call    memset_0
0x18000432c  lea     r9d, [rbp+1]
0x180004330  mov     [rbx+10h], ebp
0x180004333  mov     r10d, 105h
0x180004339  mov     rcx, [rbx]
0x18000433c  test    rcx, rcx
0x18000433f  jz      short loc_180004352
0x180004341  movzx   edx, word ptr [rcx]
0x180004344  test    dx, dx
0x180004347  jz      short loc_180004352
0x180004349  add     rcx, 2
0x18000434d  mov     [rbx], rcx
0x180004350  jmp     short loc_180004358
0x180004352  mov     [rbx+18h], r9d
0x180004356  mov     edx, ebp
0x180004358  test    esi, esi
0x18000435a  jz      short loc_1800043BD
0x18000435c  cmp     esi, r9d
0x18000435f  jnz     loc_18000443C
0x180004365  cmp     dx, 5Ch ; '\'
0x180004369  jz      loc_180004427
0x18000436f  cmp     dx, 3Dh ; '='
0x180004373  ja      short loc_180004389
0x180004375  mov     r8, 2400900000000001h
0x18000437f  bt      r8, rdx
0x180004383  jb      loc_180004427
0x180004389  cmp     dx, 40h ; '@'
0x18000438d  jz      short loc_1800043AD
0x18000438f  cmp     dx, 21h ; '!'
0x180004393  jz      short loc_1800043AD
0x180004395  mov     ecx, [rbx+10h]
0x180004398  lea     eax, [rcx+1]
0x18000439b  mov     [rbx+10h], eax
0x18000439e  cmp     ecx, r10d
0x1800043a1  jnb     loc_180004483
0x1800043a7  mov     [r14], dx
0x1800043ab  jmp     short loc_18000441B
0x1800043ad  cmp     [rbx+1Ch], ebp
0x1800043b0  jnz     short loc_180004395
0x1800043b2  cmp     [rbx+18h], ebp
0x1800043b5  jnz     short loc_180004433
0x1800043b7  add     qword ptr [rbx], 0FFFFFFFFFFFFFFFEh
0x1800043bb  jmp     short loc_180004433
0x1800043bd  mov     ecx, [rbx+10h]
0x1800043c0  lea     eax, [rcx+1]
0x1800043c3  mov     [rbx+10h], eax
0x1800043c6  cmp     ecx, r10d
0x1800043c9  jnb     loc_180004483
0x1800043cf  mov     [r14], dx
0x1800043d3  cmp     dx, 5Ch ; '\'
0x1800043d7  jz      loc_180004475
0x1800043dd  cmp     dx, 2Fh ; '/'
0x1800043e1  jz      loc_18000446E
0x1800043e7  cmp     dx, 2Ch ; ','
0x1800043eb  jz      short loc_18000445F
0x1800043ed  cmp     dx, 3Dh ; '='
0x1800043f1  jz      short loc_180004458
0x1800043f3  cmp     dx, 3Ah ; ':'
0x1800043f7  jz      short loc_180004451
0x1800043f9  test    dx, dx
0x1800043fc  jz      short loc_18000444A
0x1800043fe  cmp     dx, 40h ; '@'
0x180004402  jnz     short loc_180004410
0x180004404  cmp     [rbx+1Ch], ebp
0x180004407  jnz     short loc_18000441B
0x180004409  mov     eax, 0Bh
0x18000440e  jmp     short loc_18000447A
0x180004410  cmp     dx, 21h ; '!'
0x180004414  jnz     short loc_18000441B
0x180004416  cmp     [rbx+1Ch], ebp
0x180004419  jz      short loc_180004443
0x18000441b  mov     esi, r9d
0x18000441e  add     r14, 2
0x180004422  jmp     loc_180004339
0x180004427  cmp     [rbx+18h], ebp
0x18000442a  jnz     short loc_180004433
0x18000442c  lea     rax, [rcx-2]
0x180004430  mov     [rbx], rax
0x180004433  mov     [rdi], r9d
0x180004436  mov     [rbx+14h], r9d
0x18000443a  jmp     short loc_18000447F
0x18000443c  mov     eax, 80004005h
0x180004441  jmp     short loc_180004488
0x180004443  mov     eax, 0Ch
0x180004448  jmp     short loc_18000447A
0x18000444a  mov     eax, 4
0x18000444f  jmp     short loc_18000447A
0x180004451  mov     eax, 0Dh
0x180004456  jmp     short loc_18000447A
0x180004458  mov     eax, 19h
0x18000445d  jmp     short loc_18000447A
0x18000445f  mov     dword ptr [rdi], 2
0x180004465  mov     dword ptr [rbx+14h], 2
0x18000446c  jmp     short loc_18000447F
0x18000446e  mov     eax, 0Eh
0x180004473  jmp     short loc_18000447A
0x180004475  mov     eax, 3
0x18000447a  mov     [rdi], eax
0x18000447c  mov     [rbx+14h], eax
0x18000447f  xor     eax, eax
0x180004481  jmp     short loc_180004488
0x180004483  mov     eax, 8007007Bh
0x180004488  add     rsp, 20h
0x18000448c  pop     r14
0x18000448e  pop     rdi
0x18000448f  pop     rsi
0x180004490  pop     rbp
0x180004491  pop     rbx
0x180004492  retn
```
