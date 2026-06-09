# EvaluatePathCandidate(char const *,char const *,unsigned __int64 *)

- ea: `0x180011070`
- end: `0x1800111b2`
- name: `?EvaluatePathCandidate@@YA?AW4PATH_CANDIDATE_EVALUATION@@PEBD0PEA_K@Z`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800111b8`

## callees

- `0x180011070`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180011184`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180011184`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x1800110e9`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x1800110f3`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x1800110e9`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x1800110f3`

## pseudocode

```c
__int64 __fastcall EvaluatePathCandidate(_BYTE *a1, _BYTE *a2, _QWORD *a3)
{
  _QWORD *v4; // rbx
  _BYTE *v5; // rdx
  _BYTE *v6; // r15
  __int64 v7; // r13
  unsigned __int64 v8; // r9
  _BYTE *v9; // rbp
  unsigned int v10; // esi
  char v11; // r12
  unsigned __int64 v12; // rax
  unsigned int v13; // ebx
  int v14; // edi
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  int v18; // eax
  char v19; // cl
  _BYTE *v21; // rax
  _BYTE *v23; // [rsp+78h] [rbp+10h]
  unsigned __int64 v25; // [rsp+88h] [rbp+20h]

  v4 = a3;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v9 = a1;
  v10 = 1;
  v11 = 1;
  if ( !*a1 )
    goto LABEL_17;
  do
  {
    if ( !*a2 )
      break;
    v12 = v8 + 1;
    if ( *v9 == 92 )
      v5 = v9;
    else
      v12 = v8;
    v8 = v12;
    v23 = v5;
    if ( *a2 == 92 )
      v6 = a2;
    v25 = v12;
    if ( v11 )
    {
      v13 = (char)*v9;
      v14 = _o_tolower((unsigned int)(char)*a2, v5, a3, v12);
      v18 = _o_tolower(v13, v15, v16, v17);
      v5 = v23;
      v8 = v25;
      if ( v18 != v14 )
        v11 = 0;
    }
    ++v9;
    ++v7;
    ++a2;
  }
  while ( *v9 );
  if ( !v7 )
  {
LABEL_16:
    v4 = a3;
LABEL_17:
    *v4 = 0;
    return 0;
  }
  v19 = *a2;
  if ( *a2 )
  {
    do
    {
      v21 = a2;
      if ( v19 != 92 )
        v21 = v6;
      ++a2;
      v6 = v21;
      v19 = *a2;
    }
    while ( *a2 );
    if ( v5 )
    {
      if ( v8 < 2 || !v11 )
        goto LABEL_16;
      v10 = 3;
    }
    else
    {
      if ( !v21 || (unsigned int)_o__stricmp(a1, v21 + 1) )
        goto LABEL_16;
      v10 = 2;
    }
  }
  else if ( *v9 || !v11 )
  {
    goto LABEL_16;
  }
  *a3 = v7;
  return v10;
}

```

## disassembly

```asm
0x180011070  mov     [rsp+arg_10], r8
0x180011075  mov     [rsp+arg_0], rcx
0x18001107a  push    rbx
0x18001107b  push    rbp
0x18001107c  push    rsi
0x18001107d  push    rdi
0x18001107e  push    r12
0x180011080  push    r13
0x180011082  push    r14
0x180011084  push    r15
0x180011086  sub     rsp, 28h
0x18001108a  xor     edi, edi
0x18001108c  mov     r14, rdx
0x18001108f  mov     rbx, r8
0x180011092  mov     edx, edi
0x180011094  mov     r15d, edi
0x180011097  mov     r13d, edi
0x18001109a  mov     r9d, edi
0x18001109d  mov     rbp, rcx
0x1800110a0  lea     esi, [rdi+1]
0x1800110a3  mov     r12b, sil
0x1800110a6  cmp     [rcx], dil
0x1800110a9  jz      loc_180011144
0x1800110af  cmp     [r14], dil
0x1800110b2  jz      short loc_180011125
0x1800110b4  cmp     byte ptr [rbp+0], 5Ch ; '\'
0x1800110b8  lea     rax, [r9+1]
0x1800110bc  cmovnz  rax, r9
0x1800110c0  cmovz   rdx, rbp
0x1800110c4  cmp     byte ptr [r14], 5Ch ; '\'
0x1800110c8  mov     r9, rax
0x1800110cb  mov     [rsp+68h+arg_8], rdx
0x1800110d0  cmovz   r15, r14
0x1800110d4  mov     [rsp+68h+arg_18], rax
0x1800110dc  test    r12b, r12b
0x1800110df  jz      short loc_180011116
0x1800110e1  movsx   ecx, byte ptr [r14]
0x1800110e5  movsx   ebx, byte ptr [rbp+0]
0x1800110e9  call    cs:__imp__o_tolower
0x1800110ef  mov     ecx, ebx
0x1800110f1  mov     edi, eax
0x1800110f3  call    cs:__imp__o_tolower
0x1800110f9  mov     rdx, [rsp+68h+arg_8]
0x1800110fe  mov     ecx, eax
0x180011100  mov     r9, [rsp+68h+arg_18]
0x180011108  xor     eax, eax
0x18001110a  cmp     ecx, edi
0x18001110c  movzx   r12d, r12b
0x180011110  cmovnz  r12d, eax
0x180011114  xor     edi, edi
0x180011116  add     rbp, rsi
0x180011119  add     r13, rsi
0x18001111c  add     r14, rsi
0x18001111f  cmp     [rbp+0], dil
0x180011123  jnz     short loc_1800110AF
0x180011125  test    r13, r13
0x180011128  jz      short loc_18001113C
0x18001112a  mov     cl, [r14]
0x18001112d  test    cl, cl
0x18001112f  jnz     short loc_18001115A
0x180011131  cmp     [rbp+0], dil
0x180011135  jnz     short loc_18001113C
0x180011137  test    r12b, r12b
0x18001113a  jnz     short loc_1800111A3
0x18001113c  mov     rbx, [rsp+68h+arg_10]
0x180011144  mov     [rbx], rdi
0x180011147  xor     eax, eax
0x180011149  add     rsp, 28h
0x18001114d  pop     r15
0x18001114f  pop     r14
0x180011151  pop     r13
0x180011153  pop     r12
0x180011155  pop     rdi
0x180011156  pop     rsi
0x180011157  pop     rbp
0x180011158  pop     rbx
0x180011159  retn
0x18001115a  cmp     cl, 5Ch ; '\'
0x18001115d  mov     rax, r14
0x180011160  cmovnz  rax, r15
0x180011164  add     r14, rsi
0x180011167  mov     r15, rax
0x18001116a  mov     cl, [r14]
0x18001116d  test    cl, cl
0x18001116f  jnz     short loc_18001115A
0x180011171  test    rdx, rdx
0x180011174  jnz     short loc_180011193
0x180011176  test    rax, rax
0x180011179  jz      short loc_18001113C
0x18001117b  mov     rcx, [rsp+68h+arg_0]
0x180011180  lea     rdx, [rax+1]
0x180011184  call    cs:__imp__o__stricmp
0x18001118a  test    eax, eax
0x18001118c  jnz     short loc_18001113C
0x18001118e  lea     esi, [rax+2]
0x180011191  jmp     short loc_1800111A3
0x180011193  cmp     r9, 2
0x180011197  jb      short loc_18001113C
0x180011199  test    r12b, r12b
0x18001119c  jz      short loc_18001113C
0x18001119e  mov     esi, 3
0x1800111a3  mov     rax, [rsp+68h+arg_10]
0x1800111ab  mov     [rax], r13
0x1800111ae  mov     eax, esi
0x1800111b0  jmp     short loc_180011149
```
