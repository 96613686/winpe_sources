# pcpComputeGlyphset

- ea: `0x14004d57c`
- end: `0x14004d730`
- name: `pcpComputeGlyphset`
- size: `436`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14004b768`
- `0x14004c740`

## callees

- `0x14004d57c`
- `0x14004d940`
- `0x14004db10`
- `0x14005b59c`
- `0x140074a98`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x14004d673`
- `KERNEL32!GlobalFree` at `0x14004d673`
- `KERNEL32!GlobalAlloc` at `0x14004d60f`
- `KERNEL32!GlobalAlloc` at `0x14004d662`
- `KERNEL32!GlobalAlloc` at `0x14004d60f`
- `KERNEL32!GlobalAlloc` at `0x14004d662`

## pseudocode

```c
unsigned int *__fastcall pcpComputeGlyphset(unsigned int **a1, unsigned int a2, unsigned int a3, unsigned __int8 a4)
{
  unsigned int *v4; // rbx
  __int64 v8; // rbx
  unsigned int v9; // edi
  unsigned int v10; // ecx
  const CHAR *lpMultiByteStr; // rax
  CHAR *v13; // rbp
  const CHAR *v14; // r13
  UINT v15; // ecx
  unsigned int v16; // r14d
  unsigned int *v17; // rax
  unsigned int v18; // edx
  __int64 i; // r8
  UINT v20; // [rsp+30h] [rbp-58h]

  v4 = *a1;
  if ( *a1 )
  {
    do
    {
      if ( v4[1] == a2 && *((_BYTE *)v4 + 12) == a4 && v4[2] == a3 )
        break;
      v4 = (unsigned int *)*((_QWORD *)v4 + 2);
    }
    while ( v4 );
    if ( v4 )
    {
      v10 = *v4 + 1;
      if ( v10 >= *v4 )
      {
        *v4 = v10;
        return v4;
      }
      return 0;
    }
  }
  v20 = ulCharsetToCodePage(a4);
  v8 = a3 - a2;
  v9 = v8 + 1;
  if ( (unsigned int)(v8 + 1) > 0x100 )
    return 0;
  lpMultiByteStr = (const CHAR *)GlobalAlloc(0x40u, 0x5A0u);
  v13 = (CHAR *)lpMultiByteStr;
  if ( !lpMultiByteStr )
    return 0;
  v14 = lpMultiByteStr + 480;
  v15 = v20;
  if ( v20 == 42 )
    v15 = 0;
  v16 = cUnicodeRangesSupported(v15, lpMultiByteStr);
  if ( v20 == 42 )
  {
    v18 = a2;
    for ( i = v9; v18 < v9 + a2; ++v18 )
    {
      if ( (unsigned int)i >= 0x1E0 )
        break;
      if ( v18 >= 0x20 )
      {
        *(_WORD *)&v14[2 * (unsigned int)i] = v18 - 4096;
        v13[(unsigned int)i] = v18 - a2;
        i = (unsigned int)(i + 1);
      }
    }
    if ( *(_WORD *)&v14[2 * v8] > 0xF020u )
      vSort(v14, v13, i);
    if ( v9 != (_DWORD)i )
    {
      ++v16;
      v9 = i;
    }
  }
  v17 = (unsigned int *)GlobalAlloc(0x40u, 4 * (v9 + 4LL * v16) + 40);
  v4 = v17;
  if ( v17 )
  {
    *v17 = 1;
    v17[1] = a2;
    v17[2] = a3;
    *((_BYTE *)v17 + 12) = a4;
    cComputeGlyphSet((_DWORD)v14, (_DWORD)v13, v9, v16, (__int64)(v17 + 6));
    *((_QWORD *)v4 + 2) = *a1;
    *a1 = v4;
  }
  GlobalFree(v13);
  return v4;
}

```

## disassembly

```asm
0x14004d57c  mov     [rsp+arg_0], rcx
0x14004d581  push    rbx
0x14004d582  push    rbp
0x14004d583  push    rsi
0x14004d584  push    rdi
0x14004d585  push    r12
0x14004d587  push    r13
0x14004d589  push    r14
0x14004d58b  push    r15
0x14004d58d  sub     rsp, 48h
0x14004d591  mov     rbx, [rcx]
0x14004d594  mov     r12d, r8d
0x14004d597  movzx   r15d, r9b
0x14004d59b  mov     esi, edx
0x14004d59d  test    rbx, rbx
0x14004d5a0  jnz     short loc_14004D5C5
0x14004d5a2  mov     ecx, r15d
0x14004d5a5  call    ulCharsetToCodePage
0x14004d5aa  mov     ebx, r12d
0x14004d5ad  mov     [rsp+88h+var_58], eax
0x14004d5b1  sub     ebx, esi
0x14004d5b3  mov     r14d, eax
0x14004d5b6  lea     edi, [rbx+1]
0x14004d5b9  cmp     edi, 100h
0x14004d5bf  jbe     short loc_14004D605
0x14004d5c1  xor     ebx, ebx
0x14004d5c3  jmp     short loc_14004D5E3
0x14004d5c5  cmp     [rbx+4], esi
0x14004d5c8  jz      short loc_14004D5F7
0x14004d5ca  mov     rbx, [rbx+10h]
0x14004d5ce  test    rbx, rbx
0x14004d5d1  jnz     short loc_14004D5C5
0x14004d5d3  test    rbx, rbx
0x14004d5d6  jz      short loc_14004D5A2
0x14004d5d8  mov     eax, [rbx]
0x14004d5da  lea     ecx, [rax+1]
0x14004d5dd  cmp     ecx, eax
0x14004d5df  jb      short loc_14004D5C1
0x14004d5e1  mov     [rbx], ecx
0x14004d5e3  mov     rax, rbx
0x14004d5e6  add     rsp, 48h
0x14004d5ea  pop     r15
0x14004d5ec  pop     r14
0x14004d5ee  pop     r13
0x14004d5f0  pop     r12
0x14004d5f2  pop     rdi
0x14004d5f3  pop     rsi
0x14004d5f4  pop     rbp
0x14004d5f5  pop     rbx
0x14004d5f6  retn
0x14004d5f7  cmp     [rbx+0Ch], r15b
0x14004d5fb  jnz     short loc_14004D5CA
0x14004d5fd  cmp     [rbx+8], r12d
0x14004d601  jz      short loc_14004D5D3
0x14004d603  jmp     short loc_14004D5CA
0x14004d605  mov     edx, 5A0h; dwBytes
0x14004d60a  mov     ecx, 40h ; '@'; uFlags
0x14004d60f  call    cs:__imp_GlobalAlloc
0x14004d615  mov     rbp, rax
0x14004d618  test    rax, rax
0x14004d61b  jz      short loc_14004D5C1
0x14004d61d  lea     r13, [rax+1E0h]
0x14004d624  mov     [rsp+88h+lpMultiByteStr], rbp; lpMultiByteStr
0x14004d629  xor     eax, eax
0x14004d62b  mov     ecx, r14d
0x14004d62e  cmp     r14d, 2Ah ; '*'
0x14004d632  mov     r9, r13
0x14004d635  mov     r8d, edi
0x14004d638  mov     edx, esi
0x14004d63a  cmovz   ecx, eax; CodePage
0x14004d63d  call    cUnicodeRangesSupported
0x14004d642  cmp     [rsp+88h+var_58], 2Ah ; '*'
0x14004d647  mov     r14d, eax
0x14004d64a  jz      short loc_14004D67E
0x14004d64c  mov     eax, edi
0x14004d64e  mov     ecx, 40h ; '@'; uFlags
0x14004d653  mov     edx, r14d
0x14004d656  lea     rdx, [rax+rdx*4]
0x14004d65a  lea     rdx, ds:28h[rdx*4]; dwBytes
0x14004d662  call    cs:__imp_GlobalAlloc
0x14004d668  mov     rbx, rax
0x14004d66b  test    rax, rax
0x14004d66e  jnz     short loc_14004D6EE
0x14004d670  mov     rcx, rbp; hMem
0x14004d673  call    cs:__imp_GlobalFree
0x14004d679  jmp     loc_14004D5E3
0x14004d67e  lea     r9d, [rdi+rsi]
0x14004d682  mov     edx, esi
0x14004d684  mov     r8d, edi
0x14004d687  cmp     esi, r9d
0x14004d68a  jnb     short loc_14004D6C2
0x14004d68c  cmp     r8d, 1E0h
0x14004d693  jnb     short loc_14004D6C2
0x14004d695  cmp     edx, 20h ; ' '
0x14004d698  jb      short loc_14004D6BB
0x14004d69a  mov     ecx, r8d
0x14004d69d  movzx   eax, dx
0x14004d6a0  mov     r10d, 1000h
0x14004d6a6  sub     ax, r10w
0x14004d6aa  mov     [r13+rcx*2+0], ax
0x14004d6b0  mov     al, dl
0x14004d6b2  sub     al, sil
0x14004d6b5  mov     [rcx+rbp], al
0x14004d6b8  inc     r8d
0x14004d6bb  inc     edx
0x14004d6bd  cmp     edx, r9d
0x14004d6c0  jb      short loc_14004D68C
0x14004d6c2  mov     ecx, 0F020h
0x14004d6c7  cmp     [r13+rbx*2+0], cx
0x14004d6cd  jbe     short loc_14004D6DA
0x14004d6cf  mov     rdx, rbp
0x14004d6d2  mov     rcx, r13
0x14004d6d5  call    vSort
0x14004d6da  cmp     edi, r8d
0x14004d6dd  jz      loc_14004D64C
0x14004d6e3  inc     r14d
0x14004d6e6  mov     edi, r8d
0x14004d6e9  jmp     loc_14004D64C
0x14004d6ee  mov     dword ptr [rax], 1
0x14004d6f4  mov     r9d, r14d
0x14004d6f7  mov     [rax+4], esi
0x14004d6fa  mov     r8d, edi
0x14004d6fd  mov     [rax+8], r12d
0x14004d701  mov     rdx, rbp
0x14004d704  mov     [rax+0Ch], r15b
0x14004d708  mov     rcx, r13
0x14004d70b  add     rax, 18h
0x14004d70f  mov     [rsp+88h+lpMultiByteStr], rax
0x14004d714  call    cComputeGlyphSet
0x14004d719  mov     rcx, [rsp+88h+arg_0]
0x14004d721  mov     rax, [rcx]
0x14004d724  mov     [rbx+10h], rax
0x14004d728  mov     [rcx], rbx
0x14004d72b  jmp     loc_14004D670
```
