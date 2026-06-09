# RleDecompressGetFormat

- ea: `0x180002680`
- end: `0x180002779`
- name: `RleDecompressGetFormat`
- size: `249`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001cd0`

## callees

- `0x180002680`
- `0x180002780`
- `0x180003768`

## pseudocode

```c
__int64 __fastcall RleDecompressGetFormat(__int64 a1, unsigned int *a2, __int64 a3)
{
  __int64 result; // rax
  unsigned int v6; // eax
  bool v7; // zf
  __int64 v8; // rax
  unsigned __int64 v9; // rcx
  unsigned int v10; // eax
  unsigned int v11; // ecx
  __int64 v12; // rdx
  unsigned __int64 v13; // rdx

  result = RleDecompressQuery(a1, (__int64)a2, 0);
  if ( !(_DWORD)result )
  {
    v6 = a2[8];
    if ( !v6 && *((_WORD *)a2 + 7) == 8 )
      v6 = 256;
    if ( a3 )
    {
      *(_OWORD *)a3 = *(_OWORD *)a2;
      *(_OWORD *)(a3 + 16) = *((_OWORD *)a2 + 1);
      *(_QWORD *)(a3 + 32) = *((_QWORD *)a2 + 4);
      memcpy_0((void *)(a3 + 40), (char *)a2 + *a2, 4LL * v6);
      v7 = *(_DWORD *)(a3 + 8) == 0x80000000;
      *(_DWORD *)a3 = 40;
      v8 = *((unsigned __int16 *)a2 + 7);
      *(_WORD *)(a3 + 14) = v8;
      *(_DWORD *)(a3 + 16) = 0;
      if ( v7 )
        return 4294967289LL;
      if ( *(int *)(a3 + 4) < 0 )
        return 4294967289LL;
      if ( !(_WORD)v8 )
        return 4294967289LL;
      v9 = v8 * *(unsigned int *)(a3 + 4);
      if ( v9 > 0xFFFFFFFF )
        return 4294967289LL;
      v10 = (unsigned int)v9 >> 3;
      v7 = (v9 & 7) == 0;
      v11 = ((unsigned int)v9 >> 3) + 1;
      if ( v7 )
        v11 = v10;
      if ( (v11 & 3) != 0 )
        v11 = v11 - (v11 & 3) + 4;
      v12 = (unsigned int)-*(_DWORD *)(a3 + 8);
      if ( *(int *)(a3 + 8) > 0 )
        v12 = *(unsigned int *)(a3 + 8);
      v13 = v11 * v12;
      if ( v13 > 0xFFFFFFFF )
      {
        return 4294967289LL;
      }
      else
      {
        *(_DWORD *)(a3 + 20) = v13;
        return 0;
      }
    }
    else
    {
      return 4 * v6 + 40;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002680  mov     [rsp+arg_0], rbx
0x180002685  mov     [rsp+arg_8], rsi
0x18000268a  push    rdi
0x18000268b  sub     rsp, 20h
0x18000268f  mov     rbx, r8
0x180002692  mov     rdi, rdx
0x180002695  xor     r8d, r8d
0x180002698  call    RleDecompressQuery
0x18000269d  xor     esi, esi
0x18000269f  test    eax, eax
0x1800026a1  jnz     loc_180002769
0x1800026a7  mov     eax, [rdi+20h]
0x1800026aa  test    eax, eax
0x1800026ac  jnz     short loc_1800026BB
0x1800026ae  cmp     word ptr [rdi+0Eh], 8
0x1800026b3  mov     ecx, 100h
0x1800026b8  cmovz   eax, ecx
0x1800026bb  test    rbx, rbx
0x1800026be  jnz     short loc_1800026CC
0x1800026c0  lea     eax, ds:28h[rax*4]
0x1800026c7  jmp     loc_180002769
0x1800026cc  movups  xmm0, xmmword ptr [rdi]
0x1800026cf  mov     r8d, eax
0x1800026d2  lea     rcx, [rbx+28h]; void *
0x1800026d6  shl     r8, 2; Size
0x1800026da  movups  xmmword ptr [rbx], xmm0
0x1800026dd  movups  xmm1, xmmword ptr [rdi+10h]
0x1800026e1  movups  xmmword ptr [rbx+10h], xmm1
0x1800026e5  movsd   xmm0, qword ptr [rdi+20h]
0x1800026ea  movsd   qword ptr [rbx+20h], xmm0
0x1800026ef  mov     edx, [rdi]
0x1800026f1  add     rdx, rdi; Src
0x1800026f4  call    memcpy_0
0x1800026f9  cmp     dword ptr [rbx+8], 80000000h
0x180002700  mov     dword ptr [rbx], 28h ; '('
0x180002706  movzx   eax, word ptr [rdi+0Eh]
0x18000270a  mov     [rbx+0Eh], ax
0x18000270e  mov     [rbx+10h], esi
0x180002711  jz      short loc_180002764
0x180002713  cmp     [rbx+4], esi
0x180002716  jl      short loc_180002764
0x180002718  test    ax, ax
0x18000271b  jz      short loc_180002764
0x18000271d  mov     ecx, [rbx+4]
0x180002720  mov     r8d, 0FFFFFFFFh
0x180002726  imul    rcx, rax
0x18000272a  cmp     rcx, r8
0x18000272d  ja      short loc_180002764
0x18000272f  mov     eax, ecx
0x180002731  shr     eax, 3
0x180002734  test    cl, 7
0x180002737  lea     ecx, [rax+1]
0x18000273a  cmovz   ecx, eax
0x18000273d  mov     eax, ecx
0x18000273f  and     eax, 3
0x180002742  jz      short loc_180002749
0x180002744  sub     ecx, eax
0x180002746  add     ecx, 4
0x180002749  mov     edx, [rbx+8]
0x18000274c  neg     edx
0x18000274e  mov     eax, ecx
0x180002750  cmovs   edx, [rbx+8]
0x180002754  imul    rdx, rax
0x180002758  cmp     rdx, r8
0x18000275b  ja      short loc_180002764
0x18000275d  mov     [rbx+14h], edx
0x180002760  xor     eax, eax
0x180002762  jmp     short loc_180002769
0x180002764  mov     eax, 0FFFFFFF9h
0x180002769  mov     rbx, [rsp+28h+arg_0]
0x18000276e  mov     rsi, [rsp+28h+arg_8]
0x180002773  add     rsp, 20h
0x180002777  pop     rdi
0x180002778  retn
```
