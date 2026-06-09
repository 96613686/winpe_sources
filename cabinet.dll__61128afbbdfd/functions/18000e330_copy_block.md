# copy_block

- ea: `0x18000e330`
- end: `0x18000e49a`
- name: `copy_block`
- size: `362`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cd6c`

## callees

- `0x18000deb4`
- `0x18000e330`

## pseudocode

```c
char __fastcall copy_block(__int64 a1, _BYTE *a2, __int16 a3)
{
  __int64 v5; // r10
  unsigned int v6; // r8d
  __int64 *v7; // r9
  __int64 v8; // rcx
  _DWORD *v9; // r11
  unsigned __int16 v10; // di
  __int64 v11; // rax
  unsigned int v12; // edx

  bi_windup();
  v6 = *(_DWORD *)(v5 + 28);
  v7 = (__int64 *)(v5 + 8);
  v8 = *(unsigned __int16 *)(v5 + 24);
  v9 = (_DWORD *)(v5 + 64);
  if ( (unsigned int)v8 < v6 - 2 )
  {
    *(_BYTE *)(v8 + *v7) = a3;
    *(_BYTE *)((unsigned __int16)++*(_WORD *)(v5 + 24) + *v7) = HIBYTE(a3);
  }
  else
  {
    if ( (unsigned int)v8 < v6 )
    {
      *(_BYTE *)(v8 + *v7) = a3;
      v10 = ++*(_WORD *)(v5 + 24);
      LOWORD(v8) = v10;
    }
    else
    {
      *v9 = 1;
      v10 = v8;
    }
    if ( (unsigned int)v10 >= *(_DWORD *)(v5 + 28) )
    {
      *v9 = 1;
      goto LABEL_16;
    }
    *(_BYTE *)(v10 + *v7) = HIBYTE(a3);
  }
  v10 = ++*(_WORD *)(v5 + 24);
  LOWORD(v8) = v10;
LABEL_16:
  v12 = *(_DWORD *)(v5 + 28);
  if ( v10 >= v12 - 2 )
  {
    if ( v10 < v12 )
    {
      *(_BYTE *)(v10 + *v7) = ~(_BYTE)a3;
      v10 = ++*(_WORD *)(v5 + 24);
      LOWORD(v8) = v10;
    }
    else
    {
      *v9 = 1;
    }
    LOBYTE(v11) = v10;
    if ( (unsigned int)v10 >= *(_DWORD *)(v5 + 28) )
      goto LABEL_4;
    v11 = *v7;
    *(_BYTE *)(v10 + *v7) = (unsigned __int16)~a3 >> 8;
  }
  else
  {
    *(_BYTE *)(v10 + *v7) = ~(_BYTE)a3;
    ++*(_WORD *)(v5 + 24);
    v11 = *v7;
    *(_BYTE *)(*(unsigned __int16 *)(v5 + 24) + *v7) = (unsigned __int16)~a3 >> 8;
  }
  ++*(_WORD *)(v5 + 24);
LABEL_8:
  LOWORD(v8) = *(_WORD *)(v5 + 24);
  while ( a3 )
  {
    --a3;
    LOBYTE(v11) = v8;
    if ( (unsigned int)(unsigned __int16)v8 < *(_DWORD *)(v5 + 28) )
    {
      LOBYTE(v11) = *a2;
      *(_BYTE *)((unsigned __int16)v8 + *v7) = *a2;
      ++*(_WORD *)(v5 + 24);
      ++a2;
      goto LABEL_8;
    }
LABEL_4:
    *v9 = 1;
  }
  return v11;
}

```

## disassembly

```asm
0x18000e330  push    rbx
0x18000e332  push    rsi
0x18000e333  push    rdi
0x18000e334  push    r14
0x18000e336  sub     rsp, 28h
0x18000e33a  movzx   ebx, r8w
0x18000e33e  mov     r14, rdx
0x18000e341  mov     r10, rcx
0x18000e344  call    bi_windup
0x18000e349  mov     r8d, [r10+1Ch]
0x18000e34d  lea     r9, [r10+8]
0x18000e351  movzx   ecx, word ptr [r10+18h]
0x18000e356  lea     r11, [r10+40h]
0x18000e35a  lea     eax, [r8-2]
0x18000e35e  cmp     ecx, eax
0x18000e360  jb      short loc_18000E3B3
0x18000e362  cmp     ecx, r8d
0x18000e365  mov     r8d, 1
0x18000e36b  jb      short loc_18000E3D8
0x18000e36d  mov     [r11], r8d
0x18000e370  movzx   edi, cx
0x18000e373  jmp     short loc_18000E3EB
0x18000e375  mov     [r11], r8d
0x18000e378  test    bx, bx
0x18000e37b  jz      short loc_18000E3A9
0x18000e37d  mov     eax, 0FFFFh
0x18000e382  add     bx, ax
0x18000e385  movzx   eax, cx
0x18000e388  cmp     eax, [r10+1Ch]
0x18000e38c  jnb     short loc_18000E375
0x18000e38e  mov     al, [r14]
0x18000e391  movzx   edx, cx
0x18000e394  mov     rcx, [r9]
0x18000e397  mov     [rdx+rcx], al
0x18000e39a  add     [r10+18h], r8w
0x18000e39f  add     r14, r8
0x18000e3a2  movzx   ecx, word ptr [r10+18h]
0x18000e3a7  jmp     short loc_18000E378
0x18000e3a9  add     rsp, 28h
0x18000e3ad  pop     r14
0x18000e3af  pop     rdi
0x18000e3b0  pop     rsi
0x18000e3b1  pop     rbx
0x18000e3b2  retn
0x18000e3b3  mov     rax, [r9]
0x18000e3b6  mov     r8d, 1
0x18000e3bc  mov     [rcx+rax], bl
0x18000e3bf  movzx   ecx, bx
0x18000e3c2  add     [r10+18h], r8w
0x18000e3c7  movzx   edx, word ptr [r10+18h]
0x18000e3cc  mov     rax, [r9]
0x18000e3cf  shr     cx, 8
0x18000e3d3  mov     [rdx+rax], cl
0x18000e3d6  jmp     short loc_18000E409
0x18000e3d8  mov     rax, [r9]
0x18000e3db  mov     [rcx+rax], bl
0x18000e3de  add     [r10+18h], r8w
0x18000e3e3  movzx   edi, word ptr [r10+18h]
0x18000e3e8  movzx   ecx, di
0x18000e3eb  movzx   eax, di
0x18000e3ee  cmp     eax, [r10+1Ch]
0x18000e3f2  jb      short loc_18000E3F9
0x18000e3f4  mov     [r11], r8d
0x18000e3f7  jmp     short loc_18000E416
0x18000e3f9  mov     rax, [r9]
0x18000e3fc  movzx   edx, bx
0x18000e3ff  movzx   ecx, di
0x18000e402  shr     dx, 8
0x18000e406  mov     [rcx+rax], dl
0x18000e409  add     [r10+18h], r8w
0x18000e40e  movzx   edi, word ptr [r10+18h]
0x18000e413  movzx   ecx, di
0x18000e416  mov     edx, [r10+1Ch]
0x18000e41a  movzx   esi, di
0x18000e41d  lea     eax, [rdx-2]
0x18000e420  cmp     esi, eax
0x18000e422  jnb     short loc_18000E44D
0x18000e424  mov     rax, [r9]
0x18000e427  mov     dl, bl
0x18000e429  movzx   ecx, di
0x18000e42c  not     dl
0x18000e42e  mov     [rcx+rax], dl
0x18000e431  movzx   ecx, bx
0x18000e434  add     [r10+18h], r8w
0x18000e439  not     cx
0x18000e43c  movzx   edx, word ptr [r10+18h]
0x18000e441  mov     rax, [r9]
0x18000e444  shr     cx, 8
0x18000e448  mov     [rdx+rax], cl
0x18000e44b  jmp     short loc_18000E490
0x18000e44d  cmp     esi, edx
0x18000e44f  jb      short loc_18000E456
0x18000e451  mov     [r11], r8d
0x18000e454  jmp     short loc_18000E470
0x18000e456  mov     rax, [r9]
0x18000e459  mov     dl, bl
0x18000e45b  movzx   ecx, di
0x18000e45e  not     dl
0x18000e460  mov     [rcx+rax], dl
0x18000e463  add     [r10+18h], r8w
0x18000e468  movzx   edi, word ptr [r10+18h]
0x18000e46d  movzx   ecx, di
0x18000e470  movzx   eax, di
0x18000e473  cmp     eax, [r10+1Ch]
0x18000e477  jnb     loc_18000E375
0x18000e47d  mov     rax, [r9]
0x18000e480  movzx   edx, bx
0x18000e483  movzx   ecx, di
0x18000e486  not     dx
0x18000e489  shr     dx, 8
0x18000e48d  mov     [rcx+rax], dl
0x18000e490  add     [r10+18h], r8w
0x18000e495  jmp     loc_18000E3A2
```
