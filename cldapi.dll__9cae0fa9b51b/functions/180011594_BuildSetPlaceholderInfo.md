# BuildSetPlaceholderInfo

- ea: `0x180011594`
- end: `0x1800118eb`
- name: `BuildSetPlaceholderInfo`
- size: `855`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b248`
- `0x18000e250`

## callees

- `0x180011594`
- `0x18001d0ac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800116fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011743`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800116fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011743`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001170e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001170e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011757`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011757`

## pseudocode

```c
__int64 __fastcall BuildSetPlaceholderInfo(__int64 a1, unsigned int a2, _QWORD *a3, unsigned int *a4)
{
  unsigned int v6; // r15d
  unsigned int v7; // r10d
  __int64 v8; // rdx
  unsigned __int64 v9; // rcx
  signed int v10; // ebx
  unsigned __int64 v11; // rcx
  unsigned int v12; // edx
  int v13; // r8d
  unsigned int v14; // ecx
  unsigned int v15; // edx
  unsigned int v16; // edx
  HANDLE ProcessHeap; // rax
  char *v18; // rdi
  HANDLE v19; // rax
  unsigned int v20; // r8d
  unsigned int v21; // r9d
  __int64 v22; // rbx
  int v23; // r15d
  __int64 v24; // r14
  __int64 v25; // rax
  char *v26; // rsi
  unsigned __int16 v27; // cx
  int v28; // r12d
  int v29; // r12d
  int v30; // eax
  int v31; // eax
  unsigned int v33; // [rsp+20h] [rbp-48h]
  signed int v34; // [rsp+28h] [rbp-40h]
  unsigned int v35; // [rsp+78h] [rbp+10h]

  v33 = 0;
  v6 = 0;
  v7 = 0;
  if ( a2 )
  {
    while ( 1 )
    {
      v8 = 88LL * v7;
      v9 = -1;
      do
        ++v9;
      while ( *(_WORD *)(*(_QWORD *)(v8 + a1) + 2 * v9) );
      v10 = 0;
      if ( !v9 )
        v10 = -2147024809;
      if ( v10 < 0 )
        break;
      v10 = v9 > 0x7FFF ? 0x57 : 0;
      if ( v9 > 0x7FFF )
        v10 = (v9 > 0x7FFF ? 0x57 : 0) | 0x80070000;
      if ( v10 < 0 )
        break;
      v11 = 2 * v9;
      v10 = v11 > 0xFFFFFFAF ? 0x57 : 0;
      if ( v11 > 0xFFFFFFAF )
        v10 = (v11 > 0xFFFFFFAF ? 0x57 : 0) | 0x80070000;
      if ( v10 < 0 )
        break;
      v12 = *(_DWORD *)(v8 + a1 + 64);
      v10 = v12 > 0x1000 ? 0x57 : 0;
      if ( v12 > 0x1000 )
        v10 = (v12 > 0x1000 ? 0x57 : 0) | 0x80070000;
      if ( v10 < 0 )
        break;
      v13 = v11 + 80;
      v14 = ~(v11 + 80);
      v10 = v14 < v12 ? 0x57 : 0;
      if ( v12 > v14 )
        v10 = (v14 < v12 ? 0x57 : 0) | 0x80070000;
      if ( v10 < 0 )
        break;
      v15 = v13 + v12;
      v10 = v15 > 0xFFFFFFF8 ? 0x57 : 0;
      if ( v15 > 0xFFFFFFF8 )
        v10 = (v15 > 0xFFFFFFF8 ? 0x57 : 0) | 0x80070000;
      if ( v10 < 0 )
        break;
      v16 = (v15 + 7) & 0xFFFFFFF8;
      v10 = ~v6 < v16 ? 0x57 : 0;
      if ( v16 > ~v6 )
        v10 = (~v6 < v16 ? 0x57 : 0) | 0x80070000;
      if ( v10 < 0 )
        break;
      v6 += v16;
      ++v7;
      v33 = v6;
      if ( v7 >= a2 )
        goto LABEL_26;
    }
  }
  else
  {
LABEL_26:
    ProcessHeap = GetProcessHeap();
    v18 = (char *)HeapAlloc(ProcessHeap, 0, v6);
    v10 = v18 == 0 ? 8 : 0;
    if ( !v18 )
      v10 |= 0x80070000;
    v34 = v10;
    if ( v10 > -1 )
    {
      v35 = 0;
      v20 = 0;
      if ( a2 )
      {
        v21 = a2 - 1;
        v22 = 0;
        v23 = 0;
        do
        {
          v24 = 88 * v22;
          v25 = -1;
          v26 = &v18[v23];
          do
            ++v25;
          while ( *(_WORD *)(*(_QWORD *)(88 * v22 + a1) + 2 * v25) );
          v27 = 2 * v25;
          v28 = *(_DWORD *)(v24 + a1 + 64) + 87;
          *((_DWORD *)v26 + 16) = -1;
          *((_DWORD *)v26 + 1) = 0;
          v29 = (2 * v25 + v28) & 0xFFFFFFF8;
          v30 = 0;
          if ( v20 != v21 )
            v30 = v29;
          *(_DWORD *)v26 = v30;
          if ( (*(_BYTE *)(v24 + a1 + 68) & 1) != 0 )
          {
            *((_DWORD *)v26 + 1) = 64;
            v31 = 64;
          }
          else
          {
            v31 = 0;
          }
          if ( (*(_BYTE *)(v24 + a1 + 68) & 2) != 0 )
          {
            v31 |= 1u;
            *((_DWORD *)v26 + 1) = v31;
          }
          if ( (*(_BYTE *)(v24 + a1 + 68) & 4) != 0 )
          {
            v31 |= 0x4000u;
            *((_DWORD *)v26 + 1) = v31;
          }
          if ( (*(_BYTE *)(v24 + a1 + 68) & 8) != 0 )
            *((_DWORD *)v26 + 1) = v31 | 0x400;
          *((_WORD *)v26 + 4) = 80;
          *((_WORD *)v26 + 5) = v27;
          *((_WORD *)v26 + 6) = v27 + 80;
          *((_WORD *)v26 + 7) = *(_WORD *)(v24 + a1 + 64);
          *(_OWORD *)&v18[v23 + 16] = *(_OWORD *)(v24 + a1 + 8);
          *(_OWORD *)&v18[v23 + 32] = *(_OWORD *)(v24 + a1 + 24);
          *(_QWORD *)&v18[v23 + 48] = *(_QWORD *)(v24 + a1 + 40);
          *((_QWORD *)v26 + 7) = *(_QWORD *)(v24 + a1 + 48);
          memcpy_0(&v18[v23 + 80], *(const void **)(v24 + a1), v27);
          memcpy_0(
            &v26[*((unsigned __int16 *)v26 + 6)],
            *(const void **)(v24 + a1 + 56),
            *((unsigned __int16 *)v26 + 7));
          v21 = a2 - 1;
          v23 += v29;
          v20 = v35 + 1;
          v35 = v20;
          ++v22;
        }
        while ( v20 < a2 );
        v10 = v34;
        v6 = v33;
      }
      *a3 = v18;
      *a4 = v6;
    }
    else if ( v18 )
    {
      v19 = GetProcessHeap();
      HeapFree(v19, 0, v18);
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180011594  mov     [rsp+arg_0], rbx
0x180011599  mov     [rsp+arg_18], r9
0x18001159e  mov     [rsp+arg_10], r8
0x1800115a3  push    rbp
0x1800115a4  push    rsi
0x1800115a5  push    rdi
0x1800115a6  push    r12
0x1800115a8  push    r13
0x1800115aa  push    r14
0x1800115ac  push    r15
0x1800115ae  sub     rsp, 30h
0x1800115b2  xor     r12d, r12d
0x1800115b5  mov     r13d, edx
0x1800115b8  mov     [rsp+68h+var_48], r12d
0x1800115bd  mov     rbp, rcx
0x1800115c0  mov     r15d, r12d
0x1800115c3  mov     r10d, r12d
0x1800115c6  mov     esi, 80070000h
0x1800115cb  test    edx, edx
0x1800115cd  jz      loc_1800116FA
0x1800115d3  mov     edi, 1000h
0x1800115d8  lea     r9d, [r12+57h]
0x1800115dd  mov     r11d, 7FFFh
0x1800115e3  mov     r14d, 0FFFFFFAFh
0x1800115e9  mov     eax, r10d
0x1800115ec  imul    rdx, rax, 58h ; 'X'
0x1800115f0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800115f4  mov     rax, [rdx+rbp]
0x1800115f8  inc     rcx
0x1800115fb  cmp     [rax+rcx*2], r12w
0x180011600  jnz     short loc_1800115F8
0x180011602  test    rcx, rcx
0x180011605  mov     ebx, r12d
0x180011608  cmovz   ebx, r9d
0x18001160c  mov     eax, ebx
0x18001160e  or      eax, esi
0x180011610  test    rcx, rcx
0x180011613  cmovz   ebx, eax
0x180011616  test    ebx, ebx
0x180011618  jz      short loc_180011620
0x18001161a  js      loc_1800118D3
0x180011620  cmp     r11, rcx
0x180011623  sbb     ebx, ebx
0x180011625  and     ebx, r9d
0x180011628  mov     eax, ebx
0x18001162a  or      eax, esi
0x18001162c  cmp     rcx, r11
0x18001162f  cmova   ebx, eax
0x180011632  test    ebx, ebx
0x180011634  jz      short loc_18001163C
0x180011636  js      loc_1800118D3
0x18001163c  add     rcx, rcx
0x18001163f  cmp     r14, rcx
0x180011642  sbb     ebx, ebx
0x180011644  and     ebx, r9d
0x180011647  mov     eax, ebx
0x180011649  or      eax, esi
0x18001164b  cmp     rcx, r14
0x18001164e  cmova   ebx, eax
0x180011651  test    ebx, ebx
0x180011653  jz      short loc_18001165B
0x180011655  js      loc_1800118D3
0x18001165b  mov     edx, [rdx+rbp+40h]
0x18001165f  cmp     edi, edx
0x180011661  sbb     ebx, ebx
0x180011663  and     ebx, r9d
0x180011666  mov     eax, ebx
0x180011668  or      eax, esi
0x18001166a  cmp     edx, edi
0x18001166c  cmova   ebx, eax
0x18001166f  test    ebx, ebx
0x180011671  jz      short loc_180011679
0x180011673  js      loc_1800118D3
0x180011679  lea     r8d, [rcx+50h]
0x18001167d  mov     ecx, r8d
0x180011680  not     ecx
0x180011682  cmp     ecx, edx
0x180011684  sbb     ebx, ebx
0x180011686  and     ebx, r9d
0x180011689  mov     eax, ebx
0x18001168b  or      eax, esi
0x18001168d  cmp     edx, ecx
0x18001168f  cmova   ebx, eax
0x180011692  test    ebx, ebx
0x180011694  jz      short loc_18001169C
0x180011696  js      loc_1800118D3
0x18001169c  add     edx, r8d
0x18001169f  mov     r8d, 0FFFFFFF8h
0x1800116a5  cmp     r8d, edx
0x1800116a8  sbb     ebx, ebx
0x1800116aa  and     ebx, r9d
0x1800116ad  mov     eax, ebx
0x1800116af  or      eax, esi
0x1800116b1  cmp     edx, r8d
0x1800116b4  cmova   ebx, eax
0x1800116b7  test    ebx, ebx
0x1800116b9  jz      short loc_1800116C1
0x1800116bb  js      loc_1800118D3
0x1800116c1  add     edx, 7
0x1800116c4  mov     ecx, r15d
0x1800116c7  and     edx, r8d
0x1800116ca  not     ecx
0x1800116cc  cmp     ecx, edx
0x1800116ce  sbb     ebx, ebx
0x1800116d0  and     ebx, r9d
0x1800116d3  mov     eax, ebx
0x1800116d5  or      eax, esi
0x1800116d7  cmp     edx, ecx
0x1800116d9  cmova   ebx, eax
0x1800116dc  test    ebx, ebx
0x1800116de  jz      short loc_1800116E6
0x1800116e0  js      loc_1800118D3
0x1800116e6  add     r15d, edx
0x1800116e9  inc     r10d
0x1800116ec  mov     [rsp+68h+var_48], r15d
0x1800116f1  cmp     r10d, r13d
0x1800116f4  jb      loc_1800115E9
0x1800116fa  call    cs:__imp_GetProcessHeap
0x180011701  nop     dword ptr [rax+rax+00h]
0x180011706  mov     r8d, r15d; dwBytes
0x180011709  xor     edx, edx; dwFlags
0x18001170b  mov     rcx, rax; hHeap
0x18001170e  call    cs:__imp_HeapAlloc
0x180011715  nop     dword ptr [rax+rax+00h]
0x18001171a  mov     rdi, rax
0x18001171d  neg     rax
0x180011720  sbb     ebx, ebx
0x180011722  not     ebx
0x180011724  and     ebx, 8
0x180011727  mov     eax, ebx
0x180011729  or      eax, esi
0x18001172b  test    rdi, rdi
0x18001172e  cmovz   ebx, eax
0x180011731  mov     [rsp+68h+var_40], ebx
0x180011735  cmp     ebx, 0FFFFFFFFh
0x180011738  jg      short loc_180011768
0x18001173a  test    rdi, rdi
0x18001173d  jz      loc_1800118D3
0x180011743  call    cs:__imp_GetProcessHeap
0x18001174a  nop     dword ptr [rax+rax+00h]
0x18001174f  mov     r8, rdi; lpMem
0x180011752  xor     edx, edx; dwFlags
0x180011754  mov     rcx, rax; hHeap
0x180011757  call    cs:__imp_HeapFree
0x18001175e  nop     dword ptr [rax+rax+00h]
0x180011763  jmp     loc_1800118D3
0x180011768  mov     [rsp+68h+arg_8], r12d
0x18001176d  mov     r8d, r12d
0x180011770  test    r13d, r13d
0x180011773  jz      loc_1800118BD
0x180011779  lea     r9d, [r13-1]
0x18001177d  mov     rbx, r12
0x180011780  mov     r10d, 50h ; 'P'
0x180011786  mov     r15d, r12d
0x180011789  imul    r14, rbx, 58h ; 'X'
0x18001178d  mov     edx, r15d
0x180011790  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011794  mov     rcx, [r14+rbp]
0x180011798  lea     rsi, [rdx+rdi]
0x18001179c  inc     rax
0x18001179f  cmp     [rcx+rax*2], r12w
0x1800117a4  jnz     short loc_18001179C
0x1800117a6  mov     r12d, [r14+rbp+40h]
0x1800117ab  lea     rcx, [rax+rax]
0x1800117af  add     r12d, 57h ; 'W'
0x1800117b3  mov     dword ptr [rsi+40h], 0FFFFFFFFh
0x1800117ba  add     r12d, ecx
0x1800117bd  mov     dword ptr [rsi+4], 0
0x1800117c4  and     r12d, 0FFFFFFF8h
0x1800117c8  xor     eax, eax
0x1800117ca  cmp     r8d, r9d
0x1800117cd  cmovnz  eax, r12d
0x1800117d1  mov     [rsi], eax
0x1800117d3  test    byte ptr [r14+rbp+44h], 1
0x1800117d9  jz      short loc_1800117E9
0x1800117db  mov     dword ptr [rsi+4], 40h ; '@'
0x1800117e2  mov     eax, 40h ; '@'
0x1800117e7  jmp     short loc_1800117EB
0x1800117e9  xor     eax, eax
0x1800117eb  test    byte ptr [r14+rbp+44h], 2
0x1800117f1  jz      short loc_1800117F9
0x1800117f3  or      eax, 1
0x1800117f6  mov     [rsi+4], eax
0x1800117f9  test    byte ptr [r14+rbp+44h], 4
0x1800117ff  jz      short loc_180011808
0x180011801  bts     eax, 0Eh
0x180011805  mov     [rsi+4], eax
0x180011808  test    byte ptr [r14+rbp+44h], 8
0x18001180e  jz      short loc_180011817
0x180011810  bts     eax, 0Ah
0x180011814  mov     [rsi+4], eax
0x180011817  mov     [rsi+8], r10w
0x18001181c  movzx   r8d, cx; Size
0x180011820  lea     rcx, [rdi+50h]
0x180011824  mov     [rsi+0Ah], r8w
0x180011829  add     rcx, rdx; void *
0x18001182c  lea     eax, [r10+r8]
0x180011830  mov     [rsi+0Ch], ax
0x180011834  movzx   eax, word ptr [r14+rbp+40h]
0x18001183a  mov     [rsi+0Eh], ax
0x18001183e  movups  xmm0, xmmword ptr [r14+rbp+8]
0x180011844  movups  xmmword ptr [rdx+rdi+10h], xmm0
0x180011849  movups  xmm1, xmmword ptr [r14+rbp+18h]
0x18001184f  movups  xmmword ptr [rdx+rdi+20h], xmm1
0x180011854  movsd   xmm0, qword ptr [r14+rbp+28h]
0x18001185b  movsd   qword ptr [rdx+rdi+30h], xmm0
0x180011861  mov     rax, [r14+rbp+30h]
0x180011866  mov     [rsi+38h], rax
0x18001186a  mov     rdx, [r14+rbp]; Src
0x18001186e  call    memcpy_0
0x180011873  movzx   ecx, word ptr [rsi+0Ch]
0x180011877  movzx   r8d, word ptr [rsi+0Eh]; Size
0x18001187c  add     rcx, rsi; void *
0x18001187f  mov     rdx, [r14+rbp+38h]; Src
0x180011884  call    memcpy_0
0x180011889  mov     r8d, [rsp+68h+arg_8]
0x18001188e  lea     r9d, [r13-1]
0x180011892  add     r15d, r12d
0x180011895  inc     r8d
0x180011898  mov     r12d, 0
0x18001189e  mov     [rsp+68h+arg_8], r8d
0x1800118a3  inc     rbx
0x1800118a6  lea     r10d, [r12+50h]
0x1800118ab  cmp     r8d, r13d
0x1800118ae  jb      loc_180011789
0x1800118b4  mov     ebx, [rsp+68h+var_40]
0x1800118b8  mov     r15d, [rsp+68h+var_48]
0x1800118bd  mov     rax, [rsp+68h+arg_10]
0x1800118c5  mov     [rax], rdi
0x1800118c8  mov     rax, [rsp+68h+arg_18]
0x1800118d0  mov     [rax], r15d
0x1800118d3  mov     eax, ebx
0x1800118d5  mov     rbx, [rsp+68h+arg_0]
0x1800118da  add     rsp, 30h
0x1800118de  pop     r15
0x1800118e0  pop     r14
0x1800118e2  pop     r13
0x1800118e4  pop     r12
0x1800118e6  pop     rdi
0x1800118e7  pop     rsi
0x1800118e8  pop     rbp
0x1800118e9  retn
```
