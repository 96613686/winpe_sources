# CreateNewEventEntry

- ea: `0x18000718c`
- end: `0x1800073b6`
- name: `CreateNewEventEntry`
- size: `554`
- prototype: `__int64 __fastcall(__int128 *, __int64, __int64, char, int, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007670`

## callees

- `0x18000718c`
- `0x180008412`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007214`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007214`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007222`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007222`

## pseudocode

```c
__int64 __fastcall CreateNewEventEntry(__int128 *a1, __int64 a2, __int64 a3, char a4, int a5, _QWORD *a6)
{
  __int64 v6; // rdi
  __int64 v7; // r10
  char v8; // r12
  unsigned __int8 v10; // dl
  __int64 v11; // rcx
  __int64 v12; // rax
  SIZE_T v14; // rdi
  HANDLE ProcessHeap; // rax
  char *v16; // rax
  int v17; // edx
  char *v18; // rbp
  char *v19; // rsi
  unsigned __int64 v20; // rbx
  unsigned __int8 v21; // r14
  unsigned __int8 v22; // r13
  __int64 v23; // r12
  size_t v24; // r8
  void *v25; // rax
  unsigned __int64 v26; // rcx
  char *v27; // rdi
  __int128 v28; // xmm0
  __int64 v29; // r12
  __int64 v30; // r14
  size_t v31; // r8
  void *v32; // rbp
  int v33; // edx
  void *v34; // [rsp+20h] [rbp-48h]
  int v36; // [rsp+78h] [rbp+10h]

  v6 = 0;
  v7 = 0;
  v8 = a4;
  v10 = 0;
  *a6 = 0;
  do
  {
    v11 = *(unsigned int *)(a3 + 16LL * v10 + 8);
    if ( v10 >= 2u )
      v6 += v11;
    v12 = v11 + v7;
    if ( v10 >= 2u )
      v12 = v7;
    ++v10;
    v7 = v12;
  }
  while ( v10 < 7u );
  if ( (unsigned __int64)(v6 + v12) > 0xFFFF )
    return 534;
  v14 = v6 + 158;
  if ( !v14 )
    return 8;
  ProcessHeap = GetProcessHeap();
  v16 = (char *)HeapAlloc(ProcessHeap, 8u, v14);
  v18 = v16;
  if ( !v16 )
    return 8;
  if ( v14 < 0x70 )
  {
    v19 = v16;
    v18 = 0;
  }
  else
  {
    v19 = v16 + 112;
  }
  v20 = v14 - 112;
  if ( v14 < 0x70 )
    v20 = v14;
  v21 = 0;
  v22 = v8 + 2;
  LOBYTE(v17) = v8 + 2;
  v36 = v17;
  if ( v8 != -2 )
  {
    v23 = 0;
    do
    {
      if ( v21 >= 2u )
      {
        v24 = *(unsigned int *)(a3 + 16 * v23 + 8);
        if ( *(_DWORD *)(a3 + 16 * v23 + 8) && v20 >= v24 )
        {
          v25 = v19;
          v19 += v24;
          v20 -= v24;
        }
        else
        {
          v25 = 0;
        }
        v34 = v25;
        memcpy_0(v25, *(const void **)(a3 + 16 * v23), v24);
        *(_QWORD *)&v18[16 * v23] = v34;
        *(_DWORD *)&v18[16 * v23 + 12] = *(_DWORD *)(a3 + 16 * v23 + 12);
        *(_DWORD *)&v18[16 * v23 + 8] = *(_DWORD *)(a3 + 16 * v23 + 8);
      }
      else
      {
        *(_OWORD *)&v18[16 * v23] = *(_OWORD *)(a3 + 16 * v23);
      }
      ++v21;
      ++v23;
    }
    while ( v21 < v22 );
    LOBYTE(v17) = v36;
    v8 = a4;
  }
  v26 = v20;
  v27 = v19;
  if ( v20 >= 0x2E )
  {
    v19 += 46;
    v20 -= 46LL;
  }
  if ( v26 < 0x2E )
    v27 = 0;
  *((_QWORD *)v27 + 2) = v18;
  v28 = *a1;
  v27[44] = 7;
  v27[45] = v8;
  *((_DWORD *)v27 + 10) = a5;
  *(_OWORD *)v27 = v28;
  if ( (unsigned __int8)v17 < 7u )
  {
    v29 = v22;
    do
    {
      v30 = 2 * v29;
      v31 = *(unsigned int *)(a3 + 16 * v29 + 8);
      if ( *(_DWORD *)(a3 + 16 * v29 + 8) && v20 >= v31 )
      {
        v32 = v19;
        v19 += v31;
        v20 -= v31;
      }
      else
      {
        v32 = 0;
      }
      memcpy_0(v32, *(const void **)(a3 + 16 * v29++), v31);
      v33 = v36;
      LOBYTE(v33) = v36 + 1;
      v36 = v33;
      *(_QWORD *)(*((_QWORD *)v27 + 2) + 8 * v30) = v32;
      *(_DWORD *)(*((_QWORD *)v27 + 2) + 8 * v30 + 12) = *(_DWORD *)(a3 + 8 * v30 + 12);
      *(_DWORD *)(*((_QWORD *)v27 + 2) + 8 * v30 + 8) = *(_DWORD *)(a3 + 8 * v30 + 8);
    }
    while ( (unsigned __int8)v33 < 7u );
  }
  *a6 = v27;
  return 0;
}

```

## disassembly

```asm
0x18000718c  mov     rax, rsp
0x18000718f  mov     [rax+18h], rbx
0x180007193  mov     [rax+20h], r9b
0x180007197  mov     [rax+10h], dl
0x18000719a  mov     [rax+8], rcx
0x18000719e  push    rbp
0x18000719f  push    rsi
0x1800071a0  push    rdi
0x1800071a1  push    r12
0x1800071a3  push    r13
0x1800071a5  push    r14
0x1800071a7  push    r15
0x1800071a9  sub     rsp, 30h
0x1800071ad  mov     rax, [rsp+68h+arg_28]
0x1800071b5  xor     edi, edi
0x1800071b7  xor     r10d, r10d
0x1800071ba  mov     r12b, r9b
0x1800071bd  mov     r15, r8
0x1800071c0  xor     dl, dl
0x1800071c2  mov     [rax], rdi
0x1800071c5  movzx   eax, dl
0x1800071c8  add     rax, rax
0x1800071cb  cmp     dl, 2
0x1800071ce  mov     ecx, [r8+rax*8+8]
0x1800071d3  lea     rax, [rcx+rdi]
0x1800071d7  cmovnb  rdi, rax
0x1800071db  lea     rax, [rcx+r10]
0x1800071df  cmovnb  rax, r10
0x1800071e3  inc     dl
0x1800071e5  mov     r10, rax
0x1800071e8  cmp     dl, 7
0x1800071eb  jb      short loc_1800071C5
0x1800071ed  add     rax, rdi
0x1800071f0  cmp     rax, 0FFFFh
0x1800071f6  jbe     short loc_180007202
0x1800071f8  mov     eax, 216h
0x1800071fd  jmp     loc_18000739E
0x180007202  mov     ebx, 8
0x180007207  add     rdi, 9Eh
0x18000720e  jz      loc_18000739C
0x180007214  call    cs:__imp_GetProcessHeap
0x18000721a  mov     r8, rdi; dwBytes
0x18000721d  mov     edx, ebx; dwFlags
0x18000721f  mov     rcx, rax; hHeap
0x180007222  call    cs:__imp_HeapAlloc
0x180007228  mov     rbp, rax
0x18000722b  test    rax, rax
0x18000722e  jz      loc_18000739C
0x180007234  cmp     rdi, 70h ; 'p'
0x180007238  jb      short loc_180007240
0x18000723a  lea     rsi, [rax+70h]
0x18000723e  jmp     short loc_180007245
0x180007240  mov     rsi, rax
0x180007243  xor     ebp, ebp
0x180007245  cmp     rdi, 70h ; 'p'
0x180007249  lea     rbx, [rdi-70h]
0x18000724d  mov     r13b, r12b
0x180007250  cmovb   rbx, rdi
0x180007254  xor     r14b, r14b
0x180007257  add     r13b, 2
0x18000725b  mov     dl, r13b
0x18000725e  mov     [rsp+68h+arg_8], edx
0x180007262  jz      short loc_1800072E0
0x180007264  xor     r12d, r12d
0x180007267  mov     rdi, r12
0x18000726a  add     rdi, rdi
0x18000726d  cmp     r14b, 2
0x180007271  jnb     short loc_180007280
0x180007273  movups  xmm0, xmmword ptr [r15+rdi*8]
0x180007278  movdqu  xmmword ptr [rbp+rdi*8+0], xmm0
0x18000727e  jmp     short loc_1800072C9
0x180007280  mov     r8d, [r15+rdi*8+8]; Size
0x180007285  test    r8, r8
0x180007288  jz      short loc_18000729A
0x18000728a  cmp     rbx, r8
0x18000728d  jb      short loc_18000729A
0x18000728f  mov     rax, rsi
0x180007292  add     rsi, r8
0x180007295  sub     rbx, r8
0x180007298  jmp     short loc_18000729C
0x18000729a  xor     eax, eax
0x18000729c  mov     rdx, [r15+rdi*8]; Src
0x1800072a0  mov     rcx, rax; void *
0x1800072a3  mov     [rsp+68h+var_48], rax
0x1800072a8  call    memcpy_0
0x1800072ad  mov     rax, [rsp+68h+var_48]
0x1800072b2  mov     [rbp+rdi*8+0], rax
0x1800072b7  mov     eax, [r15+rdi*8+0Ch]
0x1800072bc  mov     [rbp+rdi*8+0Ch], eax
0x1800072c0  mov     eax, [r15+rdi*8+8]
0x1800072c5  mov     [rbp+rdi*8+8], eax
0x1800072c9  inc     r14b
0x1800072cc  inc     r12
0x1800072cf  cmp     r14b, r13b
0x1800072d2  jb      short loc_180007267
0x1800072d4  mov     edx, [rsp+68h+arg_8]
0x1800072d8  mov     r12b, [rsp+68h+arg_18]
0x1800072e0  mov     rcx, rbx
0x1800072e3  mov     rdi, rsi
0x1800072e6  cmp     rbx, 2Eh ; '.'
0x1800072ea  jb      short loc_1800072F4
0x1800072ec  add     rsi, 2Eh ; '.'
0x1800072f0  sub     rbx, 2Eh ; '.'
0x1800072f4  xor     eax, eax
0x1800072f6  cmp     rcx, 2Eh ; '.'
0x1800072fa  cmovb   rdi, rax
0x1800072fe  mov     rax, [rsp+68h+arg_0]
0x180007303  mov     [rdi+10h], rbp
0x180007307  movups  xmm0, xmmword ptr [rax]
0x18000730a  mov     eax, [rsp+68h+arg_20]
0x180007311  mov     byte ptr [rdi+2Ch], 7
0x180007315  mov     [rdi+2Dh], r12b
0x180007319  mov     [rdi+28h], eax
0x18000731c  movdqu  xmmword ptr [rdi], xmm0
0x180007320  cmp     dl, 7
0x180007323  jnb     short loc_18000738D
0x180007325  movzx   r12d, r13b
0x180007329  mov     r14, r12
0x18000732c  add     r14, r14
0x18000732f  mov     r8d, [r15+r14*8+8]; Size
0x180007334  test    r8, r8
0x180007337  jz      short loc_180007349
0x180007339  cmp     rbx, r8
0x18000733c  jb      short loc_180007349
0x18000733e  mov     rbp, rsi
0x180007341  add     rsi, r8
0x180007344  sub     rbx, r8
0x180007347  jmp     short loc_18000734B
0x180007349  xor     ebp, ebp
0x18000734b  mov     rdx, [r15+r14*8]; Src
0x18000734f  mov     rcx, rbp; void *
0x180007352  call    memcpy_0
0x180007357  mov     rax, [rdi+10h]
0x18000735b  inc     r12
0x18000735e  mov     edx, [rsp+68h+arg_8]
0x180007362  inc     dl
0x180007364  mov     [rsp+68h+arg_8], edx
0x180007368  mov     [rax+r14*8], rbp
0x18000736c  mov     rcx, [rdi+10h]
0x180007370  mov     eax, [r15+r14*8+0Ch]
0x180007375  mov     [rcx+r14*8+0Ch], eax
0x18000737a  mov     rcx, [rdi+10h]
0x18000737e  mov     eax, [r15+r14*8+8]
0x180007383  mov     [rcx+r14*8+8], eax
0x180007388  cmp     dl, 7
0x18000738b  jb      short loc_180007329
0x18000738d  mov     rax, [rsp+68h+arg_28]
0x180007395  mov     [rax], rdi
0x180007398  xor     eax, eax
0x18000739a  jmp     short loc_18000739E
0x18000739c  mov     eax, ebx
0x18000739e  mov     rbx, [rsp+68h+arg_10]
0x1800073a6  add     rsp, 30h
0x1800073aa  pop     r15
0x1800073ac  pop     r14
0x1800073ae  pop     r13
0x1800073b0  pop     r12
0x1800073b2  pop     rdi
0x1800073b3  pop     rsi
0x1800073b4  pop     rbp
0x1800073b5  retn
```
