# EncodeXmlString(ushort const *)

- ea: `0x18000b5f4`
- end: `0x18000b6e7`
- name: `?EncodeXmlString@@YAPEAGPEBG@Z`
- size: `243`
- prototype: `unsigned __int16 *__fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000c008`

## callees

- `0x18000b5f4`
- `0x18000ccd2`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b64a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b64a`

## pseudocode

```c
unsigned __int16 *__fastcall EncodeXmlString(unsigned __int16 *a1)
{
  unsigned __int16 v1; // r8
  const unsigned __int16 *v2; // rdi
  int v3; // edx
  const unsigned __int16 *v4; // r9
  unsigned int v5; // eax
  _WORD *v6; // rax
  _WORD *v7; // rbp
  unsigned __int16 *v8; // rbx
  __int64 v9; // r8
  __int64 v10; // rax
  unsigned int v11; // eax
  size_t v12; // rsi
  _WORD *v14; // rdx
  __int64 v15; // rax

  v1 = *a1;
  v2 = a1;
  v3 = 0;
  v4 = a1;
  while ( v1 )
  {
    v5 = 0;
    while ( v1 != LOWORD(qword_18000F1A0[2 * v5]) )
    {
      if ( ++v5 >= 5 )
        goto LABEL_5;
    }
    v9 = qword_18000F1A0[2 * v5 + 1];
    if ( !v9 )
    {
LABEL_5:
      ++v3;
      goto LABEL_6;
    }
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)(v9 + 2 * v10) );
    v3 += v10;
LABEL_6:
    v1 = *++v4;
  }
  v6 = LocalAlloc(0x40u, 2LL * (unsigned int)(v3 + 1));
  v7 = v6;
  if ( v6 )
  {
    v8 = v6;
    while ( *v2 )
    {
      v11 = 0;
      while ( *v2 != LOWORD(qword_18000F1A0[2 * v11]) )
      {
        if ( ++v11 >= 5 )
          goto LABEL_17;
      }
      v14 = (_WORD *)qword_18000F1A0[2 * v11 + 1];
      if ( !v14 )
      {
LABEL_17:
        v12 = 2;
        *v8 = *v2;
        goto LABEL_18;
      }
      v15 = -1;
      do
        ++v15;
      while ( v14[v15] );
      v12 = 2LL * (unsigned int)v15;
      memcpy_0(v8, v14, v12);
LABEL_18:
      v8 = (unsigned __int16 *)((char *)v8 + v12);
      ++v2;
    }
    *v8 = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x18000b5f4  push    rbx
0x18000b5f6  push    rbp
0x18000b5f7  push    rsi
0x18000b5f8  push    rdi
0x18000b5f9  push    r14
0x18000b5fb  push    r15
0x18000b5fd  sub     rsp, 28h
0x18000b601  movzx   r8d, word ptr [rcx]
0x18000b605  lea     r15, qword_18000F1A0
0x18000b60c  xor     r14d, r14d
0x18000b60f  mov     rdi, rcx
0x18000b612  mov     edx, r14d
0x18000b615  mov     r9, rcx
0x18000b618  jmp     short loc_18000B63A
0x18000b61a  mov     eax, r14d
0x18000b61d  mov     ecx, eax
0x18000b61f  add     rcx, rcx
0x18000b622  cmp     r8w, [r15+rcx*8]
0x18000b627  jz      short loc_18000B65D
0x18000b629  inc     eax
0x18000b62b  cmp     eax, 5
0x18000b62e  jb      short loc_18000B61D
0x18000b630  inc     edx
0x18000b632  add     r9, 2
0x18000b636  movzx   r8d, word ptr [r9]
0x18000b63a  test    r8w, r8w
0x18000b63e  jnz     short loc_18000B61A
0x18000b640  inc     edx
0x18000b642  mov     ecx, 40h ; '@'; uFlags
0x18000b647  add     rdx, rdx; uBytes
0x18000b64a  call    cs:__imp_LocalAlloc
0x18000b650  mov     rbp, rax
0x18000b653  test    rax, rax
0x18000b656  jz      short loc_18000B6AD
0x18000b658  mov     rbx, rax
0x18000b65b  jmp     short loc_18000B6A1
0x18000b65d  mov     r8, [r15+rcx*8+8]
0x18000b662  test    r8, r8
0x18000b665  jz      short loc_18000B630
0x18000b667  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b66b  inc     rax
0x18000b66e  cmp     [r8+rax*2], r14w
0x18000b673  jnz     short loc_18000B66B
0x18000b675  add     edx, eax
0x18000b677  jmp     short loc_18000B632
0x18000b679  mov     eax, r14d
0x18000b67c  mov     ecx, eax
0x18000b67e  add     rcx, rcx
0x18000b681  cmp     dx, [r15+rcx*8]
0x18000b686  jz      short loc_18000B6BD
0x18000b688  inc     eax
0x18000b68a  cmp     eax, 5
0x18000b68d  jb      short loc_18000B67C
0x18000b68f  movzx   eax, word ptr [rdi]
0x18000b692  mov     esi, 2
0x18000b697  mov     [rbx], ax
0x18000b69a  add     rbx, rsi
0x18000b69d  add     rdi, 2
0x18000b6a1  movzx   edx, word ptr [rdi]
0x18000b6a4  test    dx, dx
0x18000b6a7  jnz     short loc_18000B679
0x18000b6a9  mov     [rbx], r14w
0x18000b6ad  mov     rax, rbp
0x18000b6b0  add     rsp, 28h
0x18000b6b4  pop     r15
0x18000b6b6  pop     r14
0x18000b6b8  pop     rdi
0x18000b6b9  pop     rsi
0x18000b6ba  pop     rbp
0x18000b6bb  pop     rbx
0x18000b6bc  retn
0x18000b6bd  mov     rdx, [r15+rcx*8+8]; Src
0x18000b6c2  test    rdx, rdx
0x18000b6c5  jz      short loc_18000B68F
0x18000b6c7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b6cb  inc     rax
0x18000b6ce  cmp     [rdx+rax*2], r14w
0x18000b6d3  jnz     short loc_18000B6CB
0x18000b6d5  mov     esi, eax
0x18000b6d7  mov     rcx, rbx; void *
0x18000b6da  add     rsi, rsi
0x18000b6dd  mov     r8, rsi; Size
0x18000b6e0  call    memcpy_0
0x18000b6e5  jmp     short loc_18000B69A
```
