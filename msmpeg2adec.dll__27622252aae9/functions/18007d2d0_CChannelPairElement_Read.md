# CChannelPairElement_Read

- ea: `0x18007d2d0`
- end: `0x18007d4cb`
- name: `CChannelPairElement_Read`
- size: `507`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180074560`

## callees

- `0x1800021a8`
- `0x1800363f0`
- `0x18007d2d0`
- `0x18007d4e0`
- `0x18007e8c0`

## pseudocode

```c
__int64 __fastcall CChannelPairElement_Read(__int64 a1, char **a2, char *a3, __int64 a4)
{
  __int64 v4; // rsi
  char *v8; // rcx
  char *v9; // rcx
  __int64 result; // rax
  int v11; // edx
  char *v12; // rax
  char *v13; // rcx
  size_t v14; // rbp
  int v15; // edi
  _BYTE *v16; // r14
  int v17; // esi
  int v18; // r13d
  __int64 i; // rdi

  v4 = a4;
  if ( *(_DWORD *)a1 < 4u )
    FillBitCache((int *)a1, 4u);
  *(_DWORD *)a1 -= 4;
  (*a2)[927] = (*(_DWORD *)(a1 + 4) >> *(_DWORD *)a1) & 0xF;
  v8 = *a2;
  v8[24] = 0;
  v8[30] = 0;
  v8[31] = *a3;
  v8[32] = a3[8];
  v9 = a2[1];
  v9[24] = 0;
  v9[30] = 0;
  v9[31] = *a3;
  v9[32] = a3[8];
  if ( !*(_DWORD *)a1 )
    FillBitCache((int *)a1, 1u);
  (*a2)[926] = (*(_DWORD *)(a1 + 4) >> --*(_DWORD *)a1) & 1;
  if ( (*a2)[926] )
  {
    result = IcsRead(a1);
    if ( (_DWORD)result )
      return result;
    v12 = *a2;
    v13 = a2[1];
    *(_OWORD *)(v13 + 24) = *(_OWORD *)(*a2 + 24);
    *((_WORD *)v13 + 20) = *((_WORD *)v12 + 20);
    v14 = (*a2)[28];
    v15 = (*a2)[33];
    v16 = (_BYTE *)*((_QWORD *)*a2 + 117);
    if ( *(_DWORD *)a1 < 2u )
      FillBitCache((int *)a1, 2u);
    *(_DWORD *)a1 -= 2;
    *v16 = (*(_DWORD *)(a1 + 4) >> *(_DWORD *)a1) & 3;
    if ( (char)v14 > 0 )
      memset_0(v16 + 1, 0, v14);
    if ( *v16 == 1 )
    {
      v17 = 0;
      v18 = v15;
      if ( (char)v15 > 0 )
      {
        do
        {
          for ( i = 0; (int)i < (int)v14; i = (unsigned int)(i + 1) )
          {
            if ( !*(_DWORD *)a1 )
              FillBitCache((int *)a1, 1u);
            v16[i + 1] |= ((*(_DWORD *)(a1 + 4) >> --*(_DWORD *)a1) & 1) << v17;
          }
          ++v17;
        }
        while ( v17 < v18 );
      }
      v4 = a4;
    }
    else if ( *v16 == 2 && (char)v14 > 0 )
    {
      LOBYTE(v11) = -1;
      memset_0(v16 + 1, v11, v14);
    }
  }
  result = ReadICS((int *)a1, *a2);
  if ( !(_DWORD)result )
  {
    if ( v4 )
    {
      *(_DWORD *)v4 = *(_DWORD *)a1;
      *(_DWORD *)(v4 + 4) = *(_DWORD *)(a1 + 4);
      *(_QWORD *)(v4 + 8) = *(_QWORD *)(a1 + 16);
    }
    return ReadICS((int *)a1, a2[1]);
  }
  return result;
}

```

## disassembly

```asm
0x18007d2d0  mov     [rsp+arg_18], r9
0x18007d2d5  push    rbx
0x18007d2d6  push    rsi
0x18007d2d7  push    rdi
0x18007d2d8  push    r12
0x18007d2da  sub     rsp, 28h
0x18007d2de  cmp     dword ptr [rcx], 4
0x18007d2e1  mov     rsi, r9
0x18007d2e4  mov     rdi, r8
0x18007d2e7  mov     r12, rdx
0x18007d2ea  mov     rbx, rcx
0x18007d2ed  jnb     short loc_18007D2F9
0x18007d2ef  mov     edx, 4
0x18007d2f4  call    FillBitCache
0x18007d2f9  add     dword ptr [rbx], 0FFFFFFFCh
0x18007d2fc  mov     ecx, [rbx]
0x18007d2fe  mov     r8d, [rbx+4]
0x18007d302  mov     rax, [r12]
0x18007d306  shr     r8d, cl
0x18007d309  and     r8b, 0Fh
0x18007d30d  mov     [rax+39Fh], r8b
0x18007d314  mov     rcx, [r12]
0x18007d318  mov     byte ptr [rcx+18h], 0
0x18007d31c  mov     byte ptr [rcx+1Eh], 0
0x18007d320  movzx   eax, byte ptr [rdi]
0x18007d323  mov     [rcx+1Fh], al
0x18007d326  movzx   eax, byte ptr [rdi+8]
0x18007d32a  mov     [rcx+20h], al
0x18007d32d  mov     rcx, [r12+8]
0x18007d332  mov     byte ptr [rcx+18h], 0
0x18007d336  mov     byte ptr [rcx+1Eh], 0
0x18007d33a  movzx   eax, byte ptr [rdi]
0x18007d33d  mov     [rcx+1Fh], al
0x18007d340  movzx   eax, byte ptr [rdi+8]
0x18007d344  mov     [rcx+20h], al
0x18007d347  cmp     dword ptr [rbx], 1
0x18007d34a  jnb     short loc_18007D359
0x18007d34c  mov     edx, 1
0x18007d351  mov     rcx, rbx
0x18007d354  call    FillBitCache
0x18007d359  dec     dword ptr [rbx]
0x18007d35b  mov     edx, [rbx+4]
0x18007d35e  mov     ecx, [rbx]
0x18007d360  mov     rax, [r12]
0x18007d364  shr     edx, cl
0x18007d366  and     dl, 1
0x18007d369  mov     [rax+39Eh], dl
0x18007d36f  mov     rdx, [r12]
0x18007d373  cmp     byte ptr [rdx+39Eh], 0
0x18007d37a  jz      loc_18007D48C
0x18007d380  add     rdx, 18h
0x18007d384  mov     rcx, rbx
0x18007d387  call    IcsRead
0x18007d38c  test    eax, eax
0x18007d38e  jnz     loc_18007D4C0
0x18007d394  mov     rax, [r12]
0x18007d398  mov     rcx, [r12+8]
0x18007d39d  mov     [rsp+48h+arg_0], rbp
0x18007d3a2  mov     [rsp+48h+arg_10], r14
0x18007d3a7  movups  xmm0, xmmword ptr [rax+18h]
0x18007d3ab  movups  xmmword ptr [rcx+18h], xmm0
0x18007d3af  movzx   eax, word ptr [rax+28h]
0x18007d3b3  mov     [rcx+28h], ax
0x18007d3b7  cmp     dword ptr [rbx], 2
0x18007d3ba  mov     rax, [r12]
0x18007d3be  movsx   rbp, byte ptr [rax+1Ch]
0x18007d3c3  movsx   edi, byte ptr [rax+21h]
0x18007d3c7  mov     r14, [rax+3A8h]
0x18007d3ce  jnb     short loc_18007D3DD
0x18007d3d0  mov     edx, 2
0x18007d3d5  mov     rcx, rbx
0x18007d3d8  call    FillBitCache
0x18007d3dd  add     dword ptr [rbx], 0FFFFFFFEh
0x18007d3e0  mov     eax, [rbx+4]
0x18007d3e3  mov     ecx, [rbx]
0x18007d3e5  shr     eax, cl
0x18007d3e7  and     al, 3
0x18007d3e9  mov     [r14], al
0x18007d3ec  test    bpl, bpl
0x18007d3ef  jle     short loc_18007D400
0x18007d3f1  mov     r8, rbp; Size
0x18007d3f4  lea     rcx, [r14+1]; void *
0x18007d3f8  xor     edx, edx; Val
0x18007d3fa  call    memset_0
0x18007d3ff  nop
0x18007d400  movsx   ecx, byte ptr [r14]
0x18007d404  sub     ecx, 1
0x18007d407  jz      short loc_18007D423
0x18007d409  cmp     ecx, 1
0x18007d40c  jnz     short loc_18007D482
0x18007d40e  test    bpl, bpl
0x18007d411  jle     short loc_18007D482
0x18007d413  mov     r8, rbp; Size
0x18007d416  lea     rcx, [r14+1]; void *
0x18007d41a  mov     dl, 0FFh; Val
0x18007d41c  call    memset_0
0x18007d421  jmp     short loc_18007D482
0x18007d423  mov     [rsp+48h+arg_8], r13
0x18007d428  xor     esi, esi
0x18007d42a  mov     [rsp+48h+var_28], r15
0x18007d42f  mov     r13d, edi
0x18007d432  test    dil, dil
0x18007d435  jle     short loc_18007D473
0x18007d437  xor     edi, edi
0x18007d439  test    bpl, bpl
0x18007d43c  jle     short loc_18007D46C
0x18007d43e  xchg    ax, ax
0x18007d440  cmp     dword ptr [rbx], 1
0x18007d443  jnb     short loc_18007D452
0x18007d445  mov     edx, 1
0x18007d44a  mov     rcx, rbx
0x18007d44d  call    FillBitCache
0x18007d452  dec     dword ptr [rbx]
0x18007d454  mov     ecx, [rbx]
0x18007d456  mov     eax, [rbx+4]
0x18007d459  shr     eax, cl
0x18007d45b  mov     ecx, esi
0x18007d45d  and     al, 1
0x18007d45f  shl     al, cl
0x18007d461  or      [rdi+r14+1], al
0x18007d466  inc     edi
0x18007d468  cmp     edi, ebp
0x18007d46a  jl      short loc_18007D440
0x18007d46c  inc     esi
0x18007d46e  cmp     esi, r13d
0x18007d471  jl      short loc_18007D437
0x18007d473  mov     rsi, [rsp+48h+arg_18]
0x18007d478  mov     r13, [rsp+48h+arg_8]
0x18007d47d  mov     r15, [rsp+48h+var_28]
0x18007d482  mov     rbp, [rsp+48h+arg_0]
0x18007d487  mov     r14, [rsp+48h+arg_10]
0x18007d48c  mov     rdx, [r12]
0x18007d490  mov     rcx, rbx
0x18007d493  call    ReadICS
0x18007d498  test    eax, eax
0x18007d49a  jnz     short loc_18007D4C0
0x18007d49c  test    rsi, rsi
0x18007d49f  jz      short loc_18007D4B3
0x18007d4a1  mov     eax, [rbx]
0x18007d4a3  mov     [rsi], eax
0x18007d4a5  mov     eax, [rbx+4]
0x18007d4a8  mov     [rsi+4], eax
0x18007d4ab  mov     rax, [rbx+10h]
0x18007d4af  mov     [rsi+8], rax
0x18007d4b3  mov     rdx, [r12+8]
0x18007d4b8  mov     rcx, rbx
0x18007d4bb  call    ReadICS
0x18007d4c0  add     rsp, 28h
0x18007d4c4  pop     r12
0x18007d4c6  pop     rdi
0x18007d4c7  pop     rsi
0x18007d4c8  pop     rbx
0x18007d4c9  retn
```
