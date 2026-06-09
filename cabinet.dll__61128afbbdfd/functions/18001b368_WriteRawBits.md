# WriteRawBits

- ea: `0x18001b368`
- end: `0x18001b40a`
- name: `WriteRawBits`
- size: `162`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001b0ec`
- `0x18001b168`

## callees

- `0x18001b368`

## pseudocode

```c
__int64 __fastcall WriteRawBits(unsigned int a1, unsigned int a2, __int64 a3)
{
  unsigned int v3; // r11d
  __int16 v5; // r9
  __int16 v6; // r9
  _WORD *v7; // rcx
  __int16 v8; // ax
  _WORD *v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rcx

  v3 = *(_DWORD *)a3;
  v5 = *(_WORD *)(a3 + 4);
  *(_DWORD *)a3 -= a2;
  if ( v3 < a2 )
  {
    v7 = *(_WORD **)(a3 + 16);
    v8 = (v5 << v3) | (a1 >> (a2 - v3));
    *(_WORD *)(a3 + 4) = v8;
    if ( (unsigned __int64)v7 < *(_QWORD *)(a3 + 32) )
      return 111;
    *v7 = v8;
    *(_QWORD *)(a3 + 16) -= 2LL;
    *(_DWORD *)a3 += 16;
    *(_QWORD *)(*(_QWORD *)(a3 + 40) + 24LL) = *(_QWORD *)(a3 + 16);
    if ( *(int *)a3 < 0 )
    {
      v10 = *(_WORD **)(a3 + 16);
      if ( (unsigned __int64)v10 < *(_QWORD *)(a3 + 32) )
        return 111;
      *v10 = a1 >> -(char)*(_DWORD *)a3;
      *(_QWORD *)(a3 + 16) -= 2LL;
      v11 = *(_QWORD *)(a3 + 40);
      v12 = *(_QWORD *)(a3 + 16);
      *(_DWORD *)a3 += 16;
      *(_QWORD *)(v11 + 24) = v12;
    }
    v6 = a1;
    goto LABEL_9;
  }
  v6 = a1 | (v5 << a2);
LABEL_9:
  *(_WORD *)(a3 + 4) = v6;
  return 0;
}

```

## disassembly

```asm
0x18001b368  mov     r11d, [r8]
0x18001b36b  mov     r10d, ecx
0x18001b36e  movzx   r9d, word ptr [r8+4]
0x18001b373  mov     eax, r11d
0x18001b376  sub     eax, edx
0x18001b378  mov     [r8], eax
0x18001b37b  cmp     r11d, edx
0x18001b37e  jb      short loc_18001B38C
0x18001b380  mov     ecx, edx
0x18001b382  shl     r9w, cl
0x18001b386  or      r9w, r10w
0x18001b38a  jmp     short loc_18001B402
0x18001b38c  sub     edx, r11d
0x18001b38f  mov     eax, r10d
0x18001b392  mov     cl, dl
0x18001b394  shr     eax, cl
0x18001b396  mov     ecx, r11d
0x18001b399  shl     r9w, cl
0x18001b39d  mov     rcx, [r8+10h]
0x18001b3a1  or      ax, r9w
0x18001b3a5  mov     [r8+4], ax
0x18001b3aa  cmp     rcx, [r8+20h]
0x18001b3ae  jnb     short loc_18001B3B6
0x18001b3b0  mov     eax, 6Fh ; 'o'
0x18001b3b5  retn
0x18001b3b6  mov     [rcx], ax
0x18001b3b9  add     qword ptr [r8+10h], 0FFFFFFFFFFFFFFFEh
0x18001b3be  add     dword ptr [r8], 10h
0x18001b3c2  mov     rcx, [r8+10h]
0x18001b3c6  mov     rax, [r8+28h]
0x18001b3ca  mov     [rax+18h], rcx
0x18001b3ce  mov     ecx, [r8]
0x18001b3d1  test    ecx, ecx
0x18001b3d3  jns     short loc_18001B3FE
0x18001b3d5  mov     rdx, [r8+10h]
0x18001b3d9  cmp     rdx, [r8+20h]
0x18001b3dd  jb      short loc_18001B3B0
0x18001b3df  neg     ecx
0x18001b3e1  mov     eax, r10d
0x18001b3e4  shr     eax, cl
0x18001b3e6  mov     [rdx], ax
0x18001b3e9  add     qword ptr [r8+10h], 0FFFFFFFFFFFFFFFEh
0x18001b3ee  mov     rax, [r8+28h]
0x18001b3f2  mov     rcx, [r8+10h]
0x18001b3f6  add     dword ptr [r8], 10h
0x18001b3fa  mov     [rax+18h], rcx
0x18001b3fe  movzx   r9d, r10w
0x18001b402  mov     [r8+4], r9w
0x18001b407  xor     eax, eax
0x18001b409  retn
```
