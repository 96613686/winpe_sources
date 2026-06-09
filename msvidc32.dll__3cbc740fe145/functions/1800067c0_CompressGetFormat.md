# CompressGetFormat

- ea: `0x1800067c0`
- end: `0x180006894`
- name: `CompressGetFormat`
- size: `212`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005e00`

## callees

- `0x1800067c0`
- `0x18000689c`
- `0x180007c95`

## pseudocode

```c
__int64 __fastcall CompressGetFormat(__int64 a1, unsigned int *a2, _OWORD *a3)
{
  __int64 result; // rax
  int v6; // r8d
  int v7; // ecx
  int v8; // edx
  __int16 v9; // cx
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax

  result = CompressQuery(a1, a2, 0);
  if ( !(_DWORD)result )
  {
    if ( *((_WORD *)a2 + 7) == 8 )
    {
      v7 = a2[8];
      if ( !v7 )
        v7 = 256;
      v8 = *a2 + 4 * v7;
      if ( !a3 )
        return (unsigned int)v8;
      memmove_0(a3, a2, v8);
      v9 = 8;
    }
    else
    {
      if ( !a3 )
        return *a2;
      v9 = 16;
      *a3 = *(_OWORD *)a2;
      a3[1] = *((_OWORD *)a2 + 1);
      *((_QWORD *)a3 + 4) = *((_QWORD *)a2 + 4);
      *((_DWORD *)a3 + 8) = v6;
    }
    *((_WORD *)a3 + 7) = v9;
    *((_DWORD *)a3 + 1) = a2[1] & 0xFFFFFFFC;
    v10 = a2[2] & 0xFFFFFFFC;
    *((_DWORD *)a3 + 4) = 1296126531;
    *((_DWORD *)a3 + 2) = v10;
    v11 = 10 * a2[1] * a2[2];
    if ( v9 == 8 )
      v12 = v11 >> 4;
    else
      v12 = v11 >> 3;
    *((_DWORD *)a3 + 5) = v12 + 2;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800067c0  mov     [rsp+arg_0], rbx
0x1800067c5  mov     [rsp+arg_8], rsi
0x1800067ca  push    rdi
0x1800067cb  sub     rsp, 20h
0x1800067cf  mov     rdi, r8
0x1800067d2  mov     rbx, rdx
0x1800067d5  xor     r8d, r8d
0x1800067d8  call    CompressQuery
0x1800067dd  test    eax, eax
0x1800067df  jnz     loc_180006884
0x1800067e5  lea     esi, [rax+8]
0x1800067e8  cmp     [rbx+0Eh], si
0x1800067ec  jnz     short loc_18000681C
0x1800067ee  mov     ecx, [rbx+20h]
0x1800067f1  mov     eax, 100h
0x1800067f6  test    ecx, ecx
0x1800067f8  cmovz   ecx, eax
0x1800067fb  mov     eax, [rbx]
0x1800067fd  lea     edx, [rax+rcx*4]
0x180006800  test    rdi, rdi
0x180006803  jnz     short loc_180006809
0x180006805  mov     eax, edx
0x180006807  jmp     short loc_180006884
0x180006809  movsxd  r8, edx; Size
0x18000680c  mov     rcx, rdi; void *
0x18000680f  mov     rdx, rbx; Src
0x180006812  call    memmove_0
0x180006817  movzx   ecx, si
0x18000681a  jmp     short loc_180006846
0x18000681c  test    rdi, rdi
0x18000681f  jnz     short loc_180006825
0x180006821  mov     eax, [rbx]
0x180006823  jmp     short loc_180006884
0x180006825  movups  xmm0, xmmword ptr [rbx]
0x180006828  mov     ecx, 10h
0x18000682d  movups  xmmword ptr [rdi], xmm0
0x180006830  movups  xmm1, xmmword ptr [rbx+10h]
0x180006834  movups  xmmword ptr [rdi+10h], xmm1
0x180006838  movsd   xmm0, qword ptr [rbx+20h]
0x18000683d  movsd   qword ptr [rdi+20h], xmm0
0x180006842  mov     [rdi+20h], r8d
0x180006846  mov     [rdi+0Eh], cx
0x18000684a  mov     eax, [rbx+4]
0x18000684d  and     eax, 0FFFFFFFCh
0x180006850  mov     [rdi+4], eax
0x180006853  mov     eax, [rbx+8]
0x180006856  and     eax, 0FFFFFFFCh
0x180006859  mov     dword ptr [rdi+10h], 4D415243h
0x180006860  mov     [rdi+8], eax
0x180006863  mov     eax, [rbx+8]
0x180006866  imul    eax, [rbx+4]
0x18000686a  lea     eax, [rax+rax*4]
0x18000686d  add     eax, eax
0x18000686f  cmp     cx, si
0x180006872  jnz     short loc_180006879
0x180006874  shr     eax, 4
0x180006877  jmp     short loc_18000687C
0x180006879  shr     eax, 3
0x18000687c  add     eax, 2
0x18000687f  mov     [rdi+14h], eax
0x180006882  xor     eax, eax
0x180006884  mov     rbx, [rsp+28h+arg_0]
0x180006889  mov     rsi, [rsp+28h+arg_8]
0x18000688e  add     rsp, 20h
0x180006892  pop     rdi
0x180006893  retn
```
