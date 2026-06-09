# CreateNewEventEntry

- ea: `0x180014584`
- end: `0x1800147bc`
- name: `CreateNewEventEntry`
- size: `568`
- prototype: `__int64 __fastcall(__int128 *, unsigned __int8, __int64, char, int, char **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180014a70`

## callees

- `0x180014584`
- `0x1800156c8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001462a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001462a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001461c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001461c`

## pseudocode

```c
__int64 __fastcall CreateNewEventEntry(__int128 *a1, unsigned __int8 a2, __int64 a3, char a4, int a5, char **a6)
{
  __int64 v6; // r10
  __int64 v7; // r11
  unsigned __int8 v8; // r12
  unsigned __int8 v9; // bl
  __int64 v12; // rcx
  __int64 v13; // rax
  unsigned __int64 v15; // rdi
  SIZE_T v16; // rbx
  HANDLE ProcessHeap; // rax
  char *v18; // rax
  int v19; // edx
  char *v20; // rbp
  char *v21; // rsi
  unsigned __int8 v22; // r15
  bool v23; // zf
  unsigned __int8 v24; // r14
  __int64 v25; // r12
  size_t v26; // r8
  char *v27; // rax
  unsigned __int64 v28; // rcx
  char *v29; // rdi
  __int128 v30; // xmm0
  __int64 v31; // r15
  __int64 v32; // r14
  size_t v33; // r8
  char *v34; // rbp
  int v35; // edx
  int v36; // [rsp+20h] [rbp-48h]
  char *v37; // [rsp+28h] [rbp-40h]

  v6 = 0;
  v7 = 0;
  v8 = a2;
  v9 = 0;
  *a6 = 0;
  if ( a2 )
  {
    do
    {
      v12 = *(unsigned int *)(a3 + 16LL * v9 + 8);
      if ( v9 >= 2u )
        v6 += v12;
      v13 = v12 + v7;
      if ( v9 >= 2u )
        v13 = v7;
      ++v9;
      v7 = v13;
    }
    while ( v9 < a2 );
    if ( (unsigned __int64)(v6 + v13) > 0xFFFF )
      return 534;
  }
  v15 = 16LL * a2;
  v16 = v6 + v15 + 46;
  if ( !v16 )
    return 8;
  ProcessHeap = GetProcessHeap();
  v18 = (char *)HeapAlloc(ProcessHeap, 8u, v16);
  v20 = v18;
  if ( !v18 )
    return 8;
  if ( v15 && v16 >= v15 )
  {
    v21 = &v18[v15];
    v16 -= v15;
  }
  else
  {
    v21 = v18;
    v20 = 0;
  }
  v22 = 0;
  v23 = a4 == -2;
  v24 = a4 + 2;
  LOBYTE(v19) = v24;
  v36 = v19;
  if ( !v23 )
  {
    v25 = 0;
    do
    {
      if ( v22 >= 2u )
      {
        v26 = *(unsigned int *)(a3 + 16 * v25 + 8);
        if ( *(_DWORD *)(a3 + 16 * v25 + 8) && v16 >= v26 )
        {
          v27 = v21;
          v21 += v26;
          v16 -= v26;
        }
        else
        {
          v27 = 0;
        }
        v37 = v27;
        memcpy_0(v27, *(const void **)(a3 + 16 * v25), v26);
        *(_QWORD *)&v20[16 * v25] = v37;
        *(_DWORD *)&v20[16 * v25 + 12] = *(_DWORD *)(a3 + 16 * v25 + 12);
        *(_DWORD *)&v20[16 * v25 + 8] = *(_DWORD *)(a3 + 16 * v25 + 8);
      }
      else
      {
        *(_OWORD *)&v20[16 * v25] = *(_OWORD *)(a3 + 16 * v25);
      }
      ++v22;
      ++v25;
    }
    while ( v22 < v24 );
    v8 = a2;
    LOBYTE(v19) = v36;
  }
  v28 = v16;
  v29 = v21;
  if ( v16 >= 0x2E )
  {
    v21 += 46;
    v16 -= 46LL;
  }
  if ( v28 < 0x2E )
    v29 = 0;
  *((_QWORD *)v29 + 2) = v20;
  v30 = *a1;
  v29[45] = a4;
  *((_DWORD *)v29 + 10) = a5;
  v29[44] = v8;
  *(_OWORD *)v29 = v30;
  if ( (unsigned __int8)v19 < v8 )
  {
    v31 = v24;
    do
    {
      v32 = 2 * v31;
      v33 = *(unsigned int *)(a3 + 16 * v31 + 8);
      if ( *(_DWORD *)(a3 + 16 * v31 + 8) && v16 >= v33 )
      {
        v34 = v21;
        v21 += v33;
        v16 -= v33;
      }
      else
      {
        v34 = 0;
      }
      memcpy_0(v34, *(const void **)(a3 + 16 * v31++), v33);
      v35 = v36;
      LOBYTE(v35) = v36 + 1;
      v36 = v35;
      *(_QWORD *)(*((_QWORD *)v29 + 2) + 8 * v32) = v34;
      *(_DWORD *)(*((_QWORD *)v29 + 2) + 8 * v32 + 12) = *(_DWORD *)(a3 + 8 * v32 + 12);
      *(_DWORD *)(*((_QWORD *)v29 + 2) + 8 * v32 + 8) = *(_DWORD *)(a3 + 8 * v32 + 8);
    }
    while ( (unsigned __int8)v35 < v8 );
  }
  *a6 = v29;
  return 0;
}

```

## disassembly

```asm
0x180014584  mov     rax, rsp
0x180014587  mov     [rax+18h], rbx
0x18001458b  mov     [rax+20h], r9b
0x18001458f  mov     [rax+10h], dl
0x180014592  mov     [rax+8], rcx
0x180014596  push    rbp
0x180014597  push    rsi
0x180014598  push    rdi
0x180014599  push    r12
0x18001459b  push    r13
0x18001459d  push    r14
0x18001459f  push    r15
0x1800145a1  sub     rsp, 30h
0x1800145a5  mov     rax, [rsp+68h+arg_28]
0x1800145ad  xor     r10d, r10d
0x1800145b0  xor     r11d, r11d
0x1800145b3  movzx   r12d, dl
0x1800145b7  xor     bl, bl
0x1800145b9  mov     r14b, r9b
0x1800145bc  mov     r13, r8
0x1800145bf  mov     [rax], r10
0x1800145c2  test    dl, dl
0x1800145c4  jz      short loc_180014603
0x1800145c6  movzx   eax, bl
0x1800145c9  add     rax, rax
0x1800145cc  cmp     bl, 2
0x1800145cf  mov     ecx, [r8+rax*8+8]
0x1800145d4  lea     rax, [rcx+r10]
0x1800145d8  cmovnb  r10, rax
0x1800145dc  lea     rax, [rcx+r11]
0x1800145e0  cmovnb  rax, r11
0x1800145e4  inc     bl
0x1800145e6  mov     r11, rax
0x1800145e9  cmp     bl, r12b
0x1800145ec  jb      short loc_1800145C6
0x1800145ee  add     rax, r10
0x1800145f1  cmp     rax, 0FFFFh
0x1800145f7  jbe     short loc_180014603
0x1800145f9  mov     eax, 216h
0x1800145fe  jmp     loc_1800147A4
0x180014603  mov     rdi, r12
0x180014606  mov     esi, 8
0x18001460b  shl     rdi, 4
0x18001460f  lea     rbx, [rdi+2Eh]
0x180014613  add     rbx, r10
0x180014616  jz      loc_1800147A2
0x18001461c  call    cs:__imp_GetProcessHeap
0x180014622  mov     r8, rbx; dwBytes
0x180014625  mov     edx, esi; dwFlags
0x180014627  mov     rcx, rax; hHeap
0x18001462a  call    cs:__imp_HeapAlloc
0x180014630  mov     rbp, rax
0x180014633  test    rax, rax
0x180014636  jz      loc_1800147A2
0x18001463c  test    rdi, rdi
0x18001463f  jz      short loc_18001464F
0x180014641  cmp     rbx, rdi
0x180014644  jb      short loc_18001464F
0x180014646  lea     rsi, [rdi+rax]
0x18001464a  sub     rbx, rdi
0x18001464d  jmp     short loc_180014654
0x18001464f  mov     rsi, rax
0x180014652  xor     ebp, ebp
0x180014654  xor     r15b, r15b
0x180014657  add     r14b, 2
0x18001465b  mov     dl, r14b
0x18001465e  mov     [rsp+68h+var_48], edx
0x180014662  jz      short loc_1800146DF
0x180014664  xor     r12d, r12d
0x180014667  mov     rdi, r12
0x18001466a  add     rdi, rdi
0x18001466d  cmp     r15b, 2
0x180014671  jnb     short loc_180014681
0x180014673  movups  xmm0, xmmword ptr [r13+rdi*8+0]
0x180014679  movdqu  xmmword ptr [rbp+rdi*8+0], xmm0
0x18001467f  jmp     short loc_1800146CB
0x180014681  mov     r8d, [r13+rdi*8+8]; Size
0x180014686  test    r8, r8
0x180014689  jz      short loc_18001469B
0x18001468b  cmp     rbx, r8
0x18001468e  jb      short loc_18001469B
0x180014690  mov     rax, rsi
0x180014693  add     rsi, r8
0x180014696  sub     rbx, r8
0x180014699  jmp     short loc_18001469D
0x18001469b  xor     eax, eax
0x18001469d  mov     rdx, [r13+rdi*8+0]; Src
0x1800146a2  mov     rcx, rax; void *
0x1800146a5  mov     [rsp+68h+var_40], rax
0x1800146aa  call    memcpy_0
0x1800146af  mov     rax, [rsp+68h+var_40]
0x1800146b4  mov     [rbp+rdi*8+0], rax
0x1800146b9  mov     eax, [r13+rdi*8+0Ch]
0x1800146be  mov     [rbp+rdi*8+0Ch], eax
0x1800146c2  mov     eax, [r13+rdi*8+8]
0x1800146c7  mov     [rbp+rdi*8+8], eax
0x1800146cb  inc     r15b
0x1800146ce  inc     r12
0x1800146d1  cmp     r15b, r14b
0x1800146d4  jb      short loc_180014667
0x1800146d6  mov     r12b, [rsp+68h+arg_8]
0x1800146db  mov     edx, [rsp+68h+var_48]
0x1800146df  mov     rcx, rbx
0x1800146e2  mov     rdi, rsi
0x1800146e5  cmp     rbx, 2Eh ; '.'
0x1800146e9  jb      short loc_1800146F3
0x1800146eb  add     rsi, 2Eh ; '.'
0x1800146ef  sub     rbx, 2Eh ; '.'
0x1800146f3  xor     eax, eax
0x1800146f5  cmp     rcx, 2Eh ; '.'
0x1800146f9  cmovb   rdi, rax
0x1800146fd  mov     rax, [rsp+68h+arg_0]
0x180014702  mov     [rdi+10h], rbp
0x180014706  movups  xmm0, xmmword ptr [rax]
0x180014709  mov     al, [rsp+68h+arg_18]
0x180014710  mov     [rdi+2Dh], al
0x180014713  mov     eax, [rsp+68h+arg_20]
0x18001471a  mov     [rdi+28h], eax
0x18001471d  mov     [rdi+2Ch], r12b
0x180014721  movdqu  xmmword ptr [rdi], xmm0
0x180014725  cmp     dl, r12b
0x180014728  jnb     short loc_180014793
0x18001472a  movzx   r15d, r14b
0x18001472e  mov     r14, r15
0x180014731  add     r14, r14
0x180014734  mov     r8d, [r13+r14*8+8]; Size
0x180014739  test    r8, r8
0x18001473c  jz      short loc_18001474E
0x18001473e  cmp     rbx, r8
0x180014741  jb      short loc_18001474E
0x180014743  mov     rbp, rsi
0x180014746  add     rsi, r8
0x180014749  sub     rbx, r8
0x18001474c  jmp     short loc_180014750
0x18001474e  xor     ebp, ebp
0x180014750  mov     rdx, [r13+r14*8+0]; Src
0x180014755  mov     rcx, rbp; void *
0x180014758  call    memcpy_0
0x18001475d  mov     rax, [rdi+10h]
0x180014761  inc     r15
0x180014764  mov     edx, [rsp+68h+var_48]
0x180014768  inc     dl
0x18001476a  mov     [rsp+68h+var_48], edx
0x18001476e  mov     [rax+r14*8], rbp
0x180014772  mov     rcx, [rdi+10h]
0x180014776  mov     eax, [r13+r14*8+0Ch]
0x18001477b  mov     [rcx+r14*8+0Ch], eax
0x180014780  mov     rcx, [rdi+10h]
0x180014784  mov     eax, [r13+r14*8+8]
0x180014789  mov     [rcx+r14*8+8], eax
0x18001478e  cmp     dl, r12b
0x180014791  jb      short loc_18001472E
0x180014793  mov     rax, [rsp+68h+arg_28]
0x18001479b  mov     [rax], rdi
0x18001479e  xor     eax, eax
0x1800147a0  jmp     short loc_1800147A4
0x1800147a2  mov     eax, esi
0x1800147a4  mov     rbx, [rsp+68h+arg_10]
0x1800147ac  add     rsp, 30h
0x1800147b0  pop     r15
0x1800147b2  pop     r14
0x1800147b4  pop     r13
0x1800147b6  pop     r12
0x1800147b8  pop     rdi
0x1800147b9  pop     rsi
0x1800147ba  pop     rbp
0x1800147bb  retn
```
