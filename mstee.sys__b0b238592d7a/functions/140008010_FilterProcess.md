# FilterProcess

- ea: `0x140008010`
- end: `0x1400080ef`
- name: `FilterProcess`
- size: `223`
- prototype: `__int64 __fastcall(__int64, __int64 **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400012c0`
- `0x140008010`

## pseudocode

```c
__int64 __fastcall FilterProcess(__int64 a1, __int64 **a2)
{
  __int64 *v2; // r8
  size_t v4; // rdi
  const void *v5; // rsi
  unsigned int *v6; // rdx
  __int64 v7; // rcx
  __int64 *i; // rbx
  __int64 v9; // rax
  __int64 v11; // rcx
  unsigned int v12; // r8d
  __int64 v13; // rax

  v2 = a2[2];
  v4 = *(unsigned int *)(*v2 + 48);
  v5 = *(const void **)(*v2 + 40);
  v6 = *(unsigned int **)(*(_QWORD *)(*v2 + 8) + 16LL);
  *(_DWORD *)(*v2 + 52) = v4;
  v7 = *(_QWORD *)(*v2 + 16);
  if ( !v7 )
  {
    for ( i = *a2; ; ++i )
    {
      v9 = *i;
      if ( !*(_QWORD *)(*i + 32) )
        break;
    }
    if ( *(_DWORD *)(v9 + 48) >= (unsigned int)v4 )
    {
      *(_DWORD *)(v9 + 52) = v4;
      *(_BYTE *)(*i + 60) = 1;
      v11 = *(_QWORD *)(*(_QWORD *)(*i + 8) + 16LL);
      v12 = *(_DWORD *)v11;
      *(_DWORD *)(v11 + 4) = v6[1];
      *(_OWORD *)(v11 + 8) = *(_OWORD *)(v6 + 2);
      *(_QWORD *)(v11 + 24) = *((_QWORD *)v6 + 3);
      *(_DWORD *)(v11 + 48) = v6[12] & 0xFFFFFDFF;
      if ( v12 > 0x38 )
      {
        v13 = *v6;
        if ( v12 >= (unsigned int)v13 )
          memmove((void *)(v11 + 56), v6 + 14, v13 - 56);
      }
      memmove(*(void **)(*i + 40), v5, v4);
      return 0;
    }
    return 3221225473LL;
  }
  if ( *(_DWORD *)(v7 + 48) < (unsigned int)v4 )
    return 3221225473LL;
  *(_DWORD *)(v7 + 52) = v4;
  return 0;
}

```

## disassembly

```asm
0x140008010  mov     [rsp+arg_0], rbx
0x140008015  mov     [rsp+arg_8], rsi
0x14000801a  push    rdi
0x14000801b  sub     rsp, 20h
0x14000801f  mov     r8, [rdx+10h]
0x140008023  mov     rbx, rdx
0x140008026  mov     rcx, [r8]
0x140008029  mov     rax, [rcx+8]
0x14000802d  mov     edi, [rcx+30h]
0x140008030  mov     rsi, [rcx+28h]
0x140008034  mov     rdx, [rax+10h]
0x140008038  mov     [rcx+34h], edi
0x14000803b  mov     rax, [r8]
0x14000803e  mov     rcx, [rax+10h]
0x140008042  test    rcx, rcx
0x140008045  jz      short loc_140008054
0x140008047  cmp     [rcx+30h], edi
0x14000804a  jb      short loc_14000806C
0x14000804c  mov     [rcx+34h], edi
0x14000804f  jmp     loc_1400080DC
0x140008054  mov     rbx, [rbx]
0x140008057  jmp     short loc_14000805D
0x140008059  add     rbx, 8
0x14000805d  mov     rax, [rbx]
0x140008060  cmp     qword ptr [rax+20h], 0
0x140008065  jnz     short loc_140008059
0x140008067  cmp     [rax+30h], edi
0x14000806a  jnb     short loc_140008073
0x14000806c  mov     eax, 0C0000001h
0x140008071  jmp     short loc_1400080DE
0x140008073  mov     [rax+34h], edi
0x140008076  mov     rax, [rbx]
0x140008079  mov     byte ptr [rax+3Ch], 1
0x14000807d  mov     rax, [rbx]
0x140008080  mov     rcx, [rax+8]
0x140008084  mov     eax, [rdx+4]
0x140008087  mov     rcx, [rcx+10h]
0x14000808b  mov     r8d, [rcx]
0x14000808e  mov     [rcx+4], eax
0x140008091  movups  xmm0, xmmword ptr [rdx+8]
0x140008095  movdqu  xmmword ptr [rcx+8], xmm0
0x14000809a  mov     rax, [rdx+18h]
0x14000809e  mov     [rcx+18h], rax
0x1400080a2  mov     eax, [rdx+30h]
0x1400080a5  btr     eax, 9
0x1400080a9  mov     [rcx+30h], eax
0x1400080ac  cmp     r8d, 38h ; '8'
0x1400080b0  jbe     short loc_1400080CA
0x1400080b2  mov     eax, [rdx]
0x1400080b4  cmp     r8d, eax
0x1400080b7  jb      short loc_1400080CA
0x1400080b9  lea     r8, [rax-38h]; Size
0x1400080bd  add     rdx, 38h ; '8'; Src
0x1400080c1  add     rcx, 38h ; '8'; void *
0x1400080c5  call    memmove
0x1400080ca  mov     rcx, [rbx]
0x1400080cd  mov     r8, rdi; Size
0x1400080d0  mov     rdx, rsi; Src
0x1400080d3  mov     rcx, [rcx+28h]; void *
0x1400080d7  call    memmove
0x1400080dc  xor     eax, eax
0x1400080de  mov     rbx, [rsp+28h+arg_0]
0x1400080e3  mov     rsi, [rsp+28h+arg_8]
0x1400080e8  add     rsp, 20h
0x1400080ec  pop     rdi
0x1400080ed  retn
```
