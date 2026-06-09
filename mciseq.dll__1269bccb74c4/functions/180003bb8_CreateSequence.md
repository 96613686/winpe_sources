# CreateSequence

- ea: `0x180003bb8`
- end: `0x180003d1f`
- name: `CreateSequence`
- size: `359`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180002eac`
- `0x180005270`

## callees

- `0x18000128c`
- `0x1800012fc`
- `0x180003bb8`
- `0x180003d28`
- `0x1800042b0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003c5d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003c5d`

## pseudocode

```c
__int64 __fastcall CreateSequence(__int64 a1, __int64 *a2)
{
  unsigned __int8 *v4; // r9
  unsigned __int16 v5; // di
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 inited; // rbx
  HLOCAL v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  unsigned __int16 i; // bp
  __int64 v15; // rax
  __int64 v16; // r9
  int v17; // eax

  *a2 = 0;
  if ( *(_DWORD *)(a1 + 32) < 6u )
    return 106;
  v4 = *(unsigned __int8 **)(a1 + 24);
  v5 = v4[3] + (v4[2] << 8);
  if ( v5 > 0x64u )
    return 106;
  v6 = v4[5] + (v4[4] << 8);
  if ( ((v4[5] + (v4[4] << 8)) & 0x8000) != 0 )
  {
    v6 = v4[5];
    v7 = -((unsigned int)(v4[5] + (v4[4] << 8)) >> 8);
  }
  else
  {
    v7 = 0;
  }
  if ( (unsigned int)v6 <= 1 )
    v6 = 1;
  inited = InitASeq(a1, v7, v6);
  if ( !inited )
    return 100;
  v10 = LocalAlloc(0, 8LL * v5);
  *(_DWORD *)(inited + 984) = v5;
  *(_QWORD *)(inited + 976) = v10;
  if ( !v10 )
  {
LABEL_17:
    Destroy(inited, v11, v12, v13);
    return 100;
  }
  for ( i = 0; i < v5; *(_DWORD *)(v16 + 60) = v17 )
  {
    v15 = List_Allocate(*(unsigned int *)(inited + 72));
    v13 = v15;
    if ( !v15 )
      goto LABEL_17;
    *(_QWORD *)(*(_QWORD *)(inited + 976) + 8LL * i) = v15;
    List_Attach_Tail(*(unsigned int *)(inited + 72), v15);
    if ( !*(_QWORD *)(inited + 88) )
      *(_QWORD *)(inited + 88) = v16;
    *(_QWORD *)(v16 + 48) = 0;
    *(_DWORD *)(v16 + 8) = 0;
    *(_DWORD *)v16 = 0;
    *(_QWORD *)(v16 + 64) = *(_QWORD *)a1;
    *(_QWORD *)(v16 + 72) = *(_QWORD *)(a1 + 8);
    v17 = i++;
    *(_DWORD *)(v16 + 20) = 0;
  }
  *a2 = inited;
  return 0;
}

```

## disassembly

```asm
0x180003bb8  push    rbx
0x180003bba  push    rbp
0x180003bbb  push    rsi
0x180003bbc  push    rdi
0x180003bbd  push    r12
0x180003bbf  push    r13
0x180003bc1  push    r14
0x180003bc3  sub     rsp, 20h
0x180003bc7  mov     qword ptr [rdx], 0
0x180003bce  mov     r14, rdx
0x180003bd1  cmp     dword ptr [rcx+20h], 6
0x180003bd5  mov     rsi, rcx
0x180003bd8  jb      loc_180003D0B
0x180003bde  mov     r9, [rcx+18h]
0x180003be2  mov     r12d, 64h ; 'd'
0x180003be8  mov     ecx, 100h
0x180003bed  movzx   edi, byte ptr [r9+2]
0x180003bf2  movzx   eax, byte ptr [r9+3]
0x180003bf7  imul    edi, ecx
0x180003bfa  add     di, ax
0x180003bfd  cmp     di, r12w
0x180003c01  ja      loc_180003D0B
0x180003c07  movzx   r8d, byte ptr [r9+4]
0x180003c0c  movzx   eax, byte ptr [r9+5]
0x180003c11  shl     r8d, 8
0x180003c15  add     r8d, eax
0x180003c18  bt      r8d, 0Fh
0x180003c1d  jb      short loc_180003C23
0x180003c1f  xor     edx, edx
0x180003c21  jmp     short loc_180003C2F
0x180003c23  mov     edx, r8d
0x180003c26  movzx   r8d, r8b
0x180003c2a  shr     edx, 8
0x180003c2d  neg     edx
0x180003c2f  mov     r13d, 1
0x180003c35  mov     rcx, rsi
0x180003c38  cmp     r8d, r13d
0x180003c3b  cmovbe  r8d, r13d
0x180003c3f  call    InitASeq
0x180003c44  mov     rbx, rax
0x180003c47  test    rax, rax
0x180003c4a  jnz     short loc_180003C54
0x180003c4c  mov     eax, r12d
0x180003c4f  jmp     loc_180003D10
0x180003c54  movzx   edx, di
0x180003c57  xor     ecx, ecx; uFlags
0x180003c59  shl     rdx, 3; uBytes
0x180003c5d  call    cs:__imp_LocalAlloc
0x180003c63  movzx   ecx, di
0x180003c66  mov     [rbx+3D8h], ecx
0x180003c6c  mov     [rbx+3D0h], rax
0x180003c73  test    rax, rax
0x180003c76  jz      loc_180003CFE
0x180003c7c  xor     ebp, ebp
0x180003c7e  xor     eax, eax
0x180003c80  cmp     ax, di
0x180003c83  jnb     short loc_180003CF7
0x180003c85  mov     ecx, [rbx+48h]
0x180003c88  call    List_Allocate
0x180003c8d  mov     r9, rax
0x180003c90  test    rax, rax
0x180003c93  jz      short loc_180003CFE
0x180003c95  mov     rcx, [rbx+3D0h]
0x180003c9c  movzx   edx, bp
0x180003c9f  mov     [rcx+rdx*8], rax
0x180003ca3  mov     rdx, rax
0x180003ca6  mov     ecx, [rbx+48h]
0x180003ca9  call    List_Attach_Tail
0x180003cae  cmp     qword ptr [rbx+58h], 0
0x180003cb3  jnz     short loc_180003CB9
0x180003cb5  mov     [rbx+58h], r9
0x180003cb9  mov     qword ptr [r9+30h], 0
0x180003cc1  mov     dword ptr [r9+8], 0
0x180003cc9  mov     dword ptr [r9], 0
0x180003cd0  mov     rax, [rsi]
0x180003cd3  mov     [r9+40h], rax
0x180003cd7  mov     rax, [rsi+8]
0x180003cdb  mov     [r9+48h], rax
0x180003cdf  movzx   eax, bp
0x180003ce2  add     bp, r13w
0x180003ce6  mov     dword ptr [r9+14h], 0
0x180003cee  mov     [r9+3Ch], eax
0x180003cf2  cmp     bp, di
0x180003cf5  jb      short loc_180003C85
0x180003cf7  mov     [r14], rbx
0x180003cfa  xor     eax, eax
0x180003cfc  jmp     short loc_180003D10
0x180003cfe  mov     rcx, rbx
0x180003d01  call    Destroy
0x180003d06  jmp     loc_180003C4C
0x180003d0b  mov     eax, 6Ah ; 'j'
0x180003d10  add     rsp, 20h
0x180003d14  pop     r14
0x180003d16  pop     r13
0x180003d18  pop     r12
0x180003d1a  pop     rdi
0x180003d1b  pop     rsi
0x180003d1c  pop     rbp
0x180003d1d  pop     rbx
0x180003d1e  retn
```
