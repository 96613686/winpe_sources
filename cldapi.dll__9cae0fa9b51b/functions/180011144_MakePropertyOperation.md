# MakePropertyOperation

- ea: `0x180011144`
- end: `0x180011295`
- name: `MakePropertyOperation`
- size: `337`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180010d50`
- `0x180010e40`
- `0x180010fb0`
- `0x180011080`

## callees

- `0x18000231e`
- `0x180011144`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800111b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800111b1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800111c5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800111c5`

## pseudocode

```c
__int64 __fastcall MakePropertyOperation(
        int a1,
        int a2,
        __int64 a3,
        unsigned int a4,
        _QWORD *a5,
        _QWORD *a6,
        unsigned int *a7)
{
  unsigned int v11; // r8d
  int v12; // edi
  unsigned int v13; // ebp
  HANDLE ProcessHeap; // rax
  _DWORD *v15; // rax
  _DWORD *v16; // rbx
  unsigned int v17; // r8d
  __int64 v18; // rdx
  __int64 v19; // rcx
  int v20; // eax

  v11 = 24 * a4 + 32;
  if ( a3 && a4 && v11 >= 0x20 && 24 * a4 / a4 == 24 )
    v12 = 0;
  else
    v12 = 87;
  if ( v12 )
    v12 |= 0x80070000;
  if ( v12 >= 0 )
  {
    v13 = 152;
    if ( v11 > 0x98 )
      v13 = 24 * a4 + 32;
    ProcessHeap = GetProcessHeap();
    v15 = HeapAlloc(ProcessHeap, 0, v13);
    v16 = v15;
    v12 = v15 == 0 ? 8 : 0;
    if ( !v15 )
      v12 |= 0x80070000;
    if ( v12 >= 0 )
    {
      memset_0(v15, 0, v13);
      v16[1] = a1;
      *v16 = -1879048166;
      v16[2] = a2;
      v16[4] = 32;
      v16[5] = a4;
      if ( a5 )
        *((_QWORD *)v16 + 3) = *a5;
      v17 = 0;
      if ( a4 )
      {
        v18 = 0;
        do
        {
          v19 = 3 * v18;
          ++v17;
          v20 = *(_DWORD *)(a3 + 24 * v18++);
          v16[2 * v19 + 8] = v20;
          v16[2 * v19 + 9] = *(_DWORD *)(a3 + 8 * v19 + 4);
          *(_QWORD *)&v16[2 * v19 + 10] = *(_QWORD *)(a3 + 8 * v19 + 8);
          v16[2 * v19 + 12] = *(_DWORD *)(a3 + 8 * v19 + 16);
        }
        while ( v17 < a4 );
      }
      *a6 = v16;
      *a7 = v13;
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180011144  push    rbx
0x180011146  push    rbp
0x180011147  push    rsi
0x180011148  push    rdi
0x180011149  push    r12
0x18001114b  push    r13
0x18001114d  push    r14
0x18001114f  push    r15
0x180011151  sub     rsp, 28h
0x180011155  mov     r14, r8
0x180011158  lea     eax, [r9+r9*2]
0x18001115c  shl     eax, 3
0x18001115f  mov     esi, r9d
0x180011162  mov     r12d, edx
0x180011165  mov     r13d, ecx
0x180011168  lea     r8d, [rax+20h]
0x18001116c  test    r14, r14
0x18001116f  jz      short loc_180011189
0x180011171  test    r9d, r9d
0x180011174  jz      short loc_180011189
0x180011176  cmp     r8d, 20h ; ' '
0x18001117a  jb      short loc_180011189
0x18001117c  xor     edx, edx
0x18001117e  div     esi
0x180011180  cmp     eax, 18h
0x180011183  jnz     short loc_180011189
0x180011185  xor     edi, edi
0x180011187  jmp     short loc_18001118E
0x180011189  mov     edi, 57h ; 'W'
0x18001118e  mov     eax, edi
0x180011190  or      eax, 80070000h
0x180011195  test    edi, edi
0x180011197  cmovnz  edi, eax
0x18001119a  test    edi, edi
0x18001119c  js      loc_180011281
0x1800111a2  mov     ebp, 98h
0x1800111a7  cmp     r8d, ebp
0x1800111aa  cmova   ebp, r8d
0x1800111ae  mov     r15d, ebp
0x1800111b1  call    cs:__imp_GetProcessHeap
0x1800111b8  nop     dword ptr [rax+rax+00h]
0x1800111bd  mov     r8d, ebp; dwBytes
0x1800111c0  xor     edx, edx; dwFlags
0x1800111c2  mov     rcx, rax; hHeap
0x1800111c5  call    cs:__imp_HeapAlloc
0x1800111cc  nop     dword ptr [rax+rax+00h]
0x1800111d1  mov     rcx, rax
0x1800111d4  mov     rbx, rax
0x1800111d7  neg     rcx
0x1800111da  sbb     edi, edi
0x1800111dc  not     edi
0x1800111de  and     edi, 8
0x1800111e1  mov     ecx, edi
0x1800111e3  or      ecx, 80070000h
0x1800111e9  test    rax, rax
0x1800111ec  cmovz   edi, ecx
0x1800111ef  test    edi, edi
0x1800111f1  js      loc_180011281
0x1800111f7  mov     r8d, r15d; Size
0x1800111fa  xor     edx, edx; Val
0x1800111fc  mov     rcx, rax; void *
0x1800111ff  call    memset_0
0x180011204  mov     rax, [rsp+68h+arg_20]
0x18001120c  mov     [rbx+4], r13d
0x180011210  mov     dword ptr [rbx], 9000001Ah
0x180011216  mov     [rbx+8], r12d
0x18001121a  mov     dword ptr [rbx+10h], 20h ; ' '
0x180011221  mov     [rbx+14h], esi
0x180011224  test    rax, rax
0x180011227  jz      short loc_180011230
0x180011229  mov     rax, [rax]
0x18001122c  mov     [rbx+18h], rax
0x180011230  xor     r8d, r8d
0x180011233  test    esi, esi
0x180011235  jz      short loc_18001126C
0x180011237  xor     edx, edx
0x180011239  lea     rcx, [rdx+rdx*2]
0x18001123d  inc     r8d
0x180011240  mov     eax, [r14+rcx*8]
0x180011244  inc     rdx
0x180011247  mov     [rbx+rcx*8+20h], eax
0x18001124b  mov     eax, [r14+rcx*8+4]
0x180011250  mov     [rbx+rcx*8+24h], eax
0x180011254  mov     rax, [r14+rcx*8+8]
0x180011259  mov     [rbx+rcx*8+28h], rax
0x18001125e  mov     eax, [r14+rcx*8+10h]
0x180011263  mov     [rbx+rcx*8+30h], eax
0x180011267  cmp     r8d, esi
0x18001126a  jb      short loc_180011239
0x18001126c  mov     rax, [rsp+68h+arg_28]
0x180011274  mov     [rax], rbx
0x180011277  mov     rax, [rsp+68h+arg_30]
0x18001127f  mov     [rax], ebp
0x180011281  mov     eax, edi
0x180011283  add     rsp, 28h
0x180011287  pop     r15
0x180011289  pop     r14
0x18001128b  pop     r13
0x18001128d  pop     r12
0x18001128f  pop     rdi
0x180011290  pop     rsi
0x180011291  pop     rbp
0x180011292  pop     rbx
0x180011293  retn
```
