# CompressTables

- ea: `0x18000d45c`
- end: `0x18000d801`
- name: `CompressTables`
- size: `933`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180007fa4`

## callees

- `0x18000d45c`
- `0x18000f264`
- `0x18000f294`
- `0x180011538`
- `0x180011574`
- `0x180014ca0`
- `0x180019804`
- `0x18001a060`
- `0x18001a0c0`
- `0x18001a138`
- `0x18001a2cc`
- `0x18001a3bc`
- `0x18001a808`
- `0x18001ac90`

## pseudocode

```c
__int64 __fastcall CompressTables(__int64 a1, unsigned int *a2)
{
  unsigned int v2; // edi
  unsigned __int16 v3; // r15
  unsigned __int16 v5; // bx
  unsigned int v6; // r14d
  __int64 v7; // rdi
  unsigned __int16 v8; // si
  unsigned int v9; // r12d
  unsigned __int16 v10; // r14
  int v11; // ebx
  unsigned __int16 v12; // bx
  __int16 v14; // r12
  __int64 v15; // rbx
  unsigned int v16; // r12d
  int v17; // eax
  __int64 v18; // r8
  unsigned int v19; // r12d
  char v20; // al
  __int16 v21; // ax
  unsigned int v22; // ebx
  __int16 v23; // r10
  unsigned int v24; // ecx
  unsigned __int16 v25; // bx
  unsigned int v26; // r15d
  unsigned int v27; // [rsp+30h] [rbp-40h] BYREF
  _WORD v28[2]; // [rsp+34h] [rbp-3Ch] BYREF
  int v29; // [rsp+38h] [rbp-38h]
  unsigned int v30; // [rsp+3Ch] [rbp-34h]
  unsigned int *v31; // [rsp+40h] [rbp-30h]
  __int64 v32; // [rsp+48h] [rbp-28h] BYREF
  int v33; // [rsp+50h] [rbp-20h]
  __int128 v34; // [rsp+58h] [rbp-18h] BYREF

  v2 = *(_DWORD *)(a1 + 12);
  v31 = a2;
  v32 = 0;
  v33 = 0;
  v3 = 0;
  LOWORD(v27) = 0;
  v28[0] = 0;
  v34 = 0;
  if ( (unsigned __int16)ReadGeneric(a1, (__int64)&v32, 0xCu, (unsigned __int8 *)&OFFSET_TABLE_CONTROL, v2, &v27) )
    return 1005;
  v5 = WORD2(v32);
  if ( (unsigned __int16)(WORD2(v32) - 1) > 0x3E7u )
    return 1006;
  v6 = v2 + (unsigned __int16)v27;
  v7 = Mem_Alloc(16LL * WORD2(v32));
  if ( !v7 )
    return 1005;
  v8 = 0;
  if ( v5 )
  {
    v9 = v6;
    while ( 1 )
    {
      v10 = ReadGeneric(a1, (__int64)&v34, 0x10u, (unsigned __int8 *)&DIRECTORY_CONTROL, v6, &v27);
      if ( v10 )
        break;
      v6 = v9 + (unsigned __int16)v27;
      if ( (_DWORD)v34 != 16843009 && HIDWORD(v34) && DWORD2(v34) )
        *(_OWORD *)(v7 + 16LL * v8++) = v34;
      ++v3;
      v9 = v6;
      if ( v3 >= v5 )
      {
        v3 = 0;
        goto LABEL_13;
      }
    }
  }
  else
  {
LABEL_13:
    SortByOffset(v7, v8);
    v30 = v8;
    v11 = v8 * (unsigned __int16)GetGenericSize(&DIRECTORY_CONTROL);
    v27 = *(_DWORD *)(a1 + 12) + (unsigned __int16)GetGenericSize(&OFFSET_TABLE_CONTROL) + v11;
    v12 = ZeroLongWordAlign(a1, v27, &v27);
    if ( v12 )
    {
      Mem_Free(v7);
      return v12;
    }
    v29 = 0;
    v14 = 0;
    if ( v8 )
    {
      do
      {
        v15 = 16LL * v3;
        if ( v14 )
        {
          v14 = 0;
          v29 = 0;
        }
        else
        {
          v16 = v27;
          v10 = CopyBlock(a1, v27, *(unsigned int *)(v15 + v7 + 8), *(unsigned int *)(v15 + v7 + 12));
          if ( v10 )
            goto LABEL_33;
          if ( (unsigned int)v3 + 1 < v30 && *(_DWORD *)(v15 + v7 + 8) == *(_DWORD *)(v7 + 16 * (v3 + 1LL) + 8) )
          {
            v17 = *(_DWORD *)(v15 + v7 + 12);
            if ( v17 )
            {
              LOWORD(v29) = 1;
              *(_DWORD *)(v7 + 16 * (v3 + 1LL) + 8) = v16;
              *(_DWORD *)(v7 + 16 * (v3 + 1LL) + 12) = v17;
            }
          }
          v18 = *(unsigned int *)(v15 + v7 + 12);
          *(_DWORD *)(v15 + v7 + 8) = v16;
          v10 = ZeroLongWordGap(a1, v16, v18, &v27);
          if ( v10 )
            goto LABEL_33;
          v14 = v29;
        }
        v10 = CalcChecksum(a1, *(unsigned int *)(v15 + v7 + 8), *(unsigned int *)(v15 + v7 + 12), v15 + v7 + 4);
        if ( v10 )
          goto LABEL_33;
        ++v3;
      }
      while ( v3 < v8 );
    }
    v19 = v27;
    SortByTag(v7, v8);
    WORD2(v32) = v8;
    v20 = log2ui16(v8);
    HIWORD(v32) = 16 * (1 << v20);
    v21 = log2ui16((unsigned __int16)(1 << v20));
    v22 = *(_DWORD *)(a1 + 12);
    LOWORD(v33) = v21;
    HIWORD(v33) = 16 * (v8 - v23);
    v10 = WriteGeneric(a1, (__int64)&v32, 0xCu, (unsigned __int8 *)&OFFSET_TABLE_CONTROL, v22, v28);
    if ( !v10 )
    {
      v24 = v22 + v28[0];
      if ( v8 )
      {
        v25 = 0;
        v26 = v24;
        while ( 1 )
        {
          v10 = WriteGeneric(a1, v7 + 16LL * v25, 0x10u, (unsigned __int8 *)&DIRECTORY_CONTROL, v24, v28);
          if ( v10 )
            break;
          ++v25;
          v24 = v26 + v28[0];
          v26 = v24;
          if ( v25 >= v8 )
            goto LABEL_32;
        }
      }
      else
      {
LABEL_32:
        *v31 = v19;
      }
    }
  }
LABEL_33:
  Mem_Free(v7);
  return v10;
}

```

## disassembly

```asm
0x18000d45c  mov     [rsp-38h+arg_10], rbx
0x18000d461  push    rbp
0x18000d462  push    rsi
0x18000d463  push    rdi
0x18000d464  push    r12
0x18000d466  push    r13
0x18000d468  push    r14
0x18000d46a  push    r15
0x18000d46c  mov     rbp, rsp
0x18000d46f  sub     rsp, 70h
0x18000d473  mov     rax, cs:__security_cookie
0x18000d47a  xor     rax, rsp
0x18000d47d  mov     [rbp+var_8], rax
0x18000d481  mov     edi, [rcx+0Ch]
0x18000d484  lea     r9, OFFSET_TABLE_CONTROL
0x18000d48b  xor     eax, eax
0x18000d48d  mov     [rbp+var_30], rdx
0x18000d491  mov     [rbp+var_28], rax
0x18000d495  lea     rdx, [rbp+var_28]
0x18000d499  mov     [rbp+var_20], eax
0x18000d49c  xorps   xmm0, xmm0
0x18000d49f  xor     r15d, r15d
0x18000d4a2  mov     r13, rcx
0x18000d4a5  lea     r8d, [rax+0Ch]
0x18000d4a9  mov     word ptr [rbp+var_40], r15w
0x18000d4ae  lea     rax, [rbp+var_40]
0x18000d4b2  mov     [rbp+var_3C], r15w
0x18000d4b7  mov     [rsp+70h+var_48], rax
0x18000d4bc  mov     [rsp+70h+var_50], edi
0x18000d4c0  movups  [rbp+var_18], xmm0
0x18000d4c4  call    ReadGeneric
0x18000d4c9  test    ax, ax
0x18000d4cc  jnz     loc_18000D7D8
0x18000d4d2  movzx   ebx, word ptr [rbp+var_28+4]
0x18000d4d6  mov     ecx, 3E7h
0x18000d4db  lea     eax, [rbx-1]
0x18000d4de  cmp     ax, cx
0x18000d4e1  ja      loc_18000D7D1
0x18000d4e7  movzx   r14d, word ptr [rbp+var_40]
0x18000d4ec  mov     ecx, ebx
0x18000d4ee  shl     rcx, 4; Size
0x18000d4f2  add     r14d, edi
0x18000d4f5  call    Mem_Alloc
0x18000d4fa  mov     rdi, rax
0x18000d4fd  test    rax, rax
0x18000d500  jz      loc_18000D7D8
0x18000d506  mov     esi, r15d
0x18000d509  cmp     r15w, bx
0x18000d50d  jnb     loc_18000D593
0x18000d513  mov     r12d, r14d
0x18000d516  lea     rax, [rbp+var_40]
0x18000d51a  mov     r8d, 10h
0x18000d520  mov     [rsp+70h+var_48], rax
0x18000d525  lea     r9, DIRECTORY_CONTROL
0x18000d52c  lea     rdx, [rbp+var_18]
0x18000d530  mov     [rsp+70h+var_50], r14d
0x18000d535  mov     rcx, r13
0x18000d538  call    ReadGeneric
0x18000d53d  xor     ecx, ecx
0x18000d53f  movzx   r14d, ax
0x18000d543  test    ax, ax
0x18000d546  jnz     loc_18000D7C3
0x18000d54c  movzx   r14d, word ptr [rbp+var_40]
0x18000d551  add     r14d, r12d
0x18000d554  cmp     dword ptr [rbp+var_18], 1010101h
0x18000d55b  jz      short loc_18000D57E
0x18000d55d  cmp     dword ptr [rbp+var_18+0Ch], ecx
0x18000d560  jz      short loc_18000D57E
0x18000d562  cmp     dword ptr [rbp+var_18+8], ecx
0x18000d565  jz      short loc_18000D57E
0x18000d567  movups  xmm0, [rbp+var_18]
0x18000d56b  movzx   eax, si
0x18000d56e  add     rax, rax
0x18000d571  movdqu  xmmword ptr [rdi+rax*8], xmm0
0x18000d576  lea     eax, [rcx+1]
0x18000d579  add     si, ax
0x18000d57c  jmp     short loc_18000D583
0x18000d57e  mov     eax, 1
0x18000d583  add     r15w, ax
0x18000d587  mov     r12d, r14d
0x18000d58a  cmp     r15w, bx
0x18000d58e  jb      short loc_18000D516
0x18000d590  xor     r15d, r15d
0x18000d593  movzx   edx, si
0x18000d596  mov     rcx, rdi
0x18000d599  call    SortByOffset
0x18000d59e  movzx   r14d, si
0x18000d5a2  lea     rcx, DIRECTORY_CONTROL
0x18000d5a9  mov     [rbp+var_34], r14d
0x18000d5ad  call    GetGenericSize
0x18000d5b2  movzx   ebx, ax
0x18000d5b5  lea     rcx, OFFSET_TABLE_CONTROL
0x18000d5bc  imul    ebx, r14d
0x18000d5c0  call    GetGenericSize
0x18000d5c5  movzx   eax, ax
0x18000d5c8  lea     r8, [rbp+var_40]
0x18000d5cc  add     ebx, eax
0x18000d5ce  mov     rcx, r13
0x18000d5d1  add     ebx, [r13+0Ch]
0x18000d5d5  mov     edx, ebx
0x18000d5d7  mov     [rbp+var_40], ebx
0x18000d5da  call    ZeroLongWordAlign
0x18000d5df  movzx   ebx, ax
0x18000d5e2  test    ax, ax
0x18000d5e5  jz      short loc_18000D5F7
0x18000d5e7  mov     rcx, rdi
0x18000d5ea  call    Mem_Free
0x18000d5ef  movzx   eax, bx
0x18000d5f2  jmp     loc_18000D7DD
0x18000d5f7  xor     ecx, ecx
0x18000d5f9  mov     [rbp+var_38], r15d
0x18000d5fd  mov     r12d, r15d
0x18000d600  cmp     cx, si
0x18000d603  jnb     loc_18000D6E0
0x18000d609  movzx   ebx, r15w
0x18000d60d  shl     rbx, 4
0x18000d611  test    r12w, r12w
0x18000d615  jnz     loc_18000D6A5
0x18000d61b  mov     r12d, [rbp+var_40]
0x18000d61f  mov     rcx, r13
0x18000d622  mov     r9d, [rbx+rdi+0Ch]
0x18000d627  mov     edx, r12d
0x18000d62a  mov     r8d, [rbx+rdi+8]
0x18000d62f  call    CopyBlock
0x18000d634  movzx   r14d, ax
0x18000d638  test    ax, ax
0x18000d63b  jnz     loc_18000D7C3
0x18000d641  movzx   ecx, r15w
0x18000d645  lea     eax, [rcx+1]
0x18000d648  cmp     eax, [rbp+var_34]
0x18000d64b  jnb     short loc_18000D679
0x18000d64d  mov     r8d, 1
0x18000d653  add     rcx, r8
0x18000d656  add     rcx, rcx
0x18000d659  mov     eax, [rdi+rcx*8+8]
0x18000d65d  cmp     [rbx+rdi+8], eax
0x18000d661  jnz     short loc_18000D679
0x18000d663  mov     eax, [rbx+rdi+0Ch]
0x18000d667  test    eax, eax
0x18000d669  jz      short loc_18000D679
0x18000d66b  mov     word ptr [rbp+var_38], r8w
0x18000d670  mov     [rdi+rcx*8+8], r12d
0x18000d675  mov     [rdi+rcx*8+0Ch], eax
0x18000d679  mov     r8d, [rbx+rdi+0Ch]
0x18000d67e  lea     r9, [rbp+var_40]
0x18000d682  mov     edx, r12d
0x18000d685  mov     [rbx+rdi+8], r12d
0x18000d68a  mov     rcx, r13
0x18000d68d  call    ZeroLongWordGap
0x18000d692  movzx   r14d, ax
0x18000d696  test    ax, ax
0x18000d699  jnz     loc_18000D7C3
0x18000d69f  mov     r12d, [rbp+var_38]
0x18000d6a3  jmp     short loc_18000D6AB
0x18000d6a5  mov     r12d, ecx
0x18000d6a8  mov     [rbp+var_38], ecx
0x18000d6ab  mov     r8d, [rbx+rdi+0Ch]
0x18000d6b0  lea     r9, [rdi+4]
0x18000d6b4  mov     edx, [rbx+rdi+8]
0x18000d6b8  add     r9, rbx
0x18000d6bb  mov     rcx, r13
0x18000d6be  call    CalcChecksum
0x18000d6c3  xor     ecx, ecx
0x18000d6c5  movzx   r14d, ax
0x18000d6c9  test    ax, ax
0x18000d6cc  jnz     loc_18000D7C3
0x18000d6d2  inc     r15w
0x18000d6d6  cmp     r15w, si
0x18000d6da  jb      loc_18000D609
0x18000d6e0  mov     r12d, [rbp+var_40]
0x18000d6e4  movzx   edx, si
0x18000d6e7  mov     rcx, rdi
0x18000d6ea  call    SortByTag
0x18000d6ef  movzx   ecx, si
0x18000d6f2  mov     word ptr [rbp+var_28+4], si
0x18000d6f6  call    log2ui16
0x18000d6fb  movzx   ecx, ax
0x18000d6fe  mov     r10d, 1
0x18000d704  shl     r10w, cl
0x18000d708  movzx   eax, r10w
0x18000d70c  movzx   ecx, r10w
0x18000d710  shl     ax, 4
0x18000d714  mov     word ptr [rbp+var_28+6], ax
0x18000d718  call    log2ui16
0x18000d71d  mov     ebx, [r13+0Ch]
0x18000d721  lea     r9, OFFSET_TABLE_CONTROL
0x18000d728  mov     word ptr [rbp+var_20], ax
0x18000d72c  lea     rdx, [rbp+var_28]
0x18000d730  movzx   eax, si
0x18000d733  mov     r8d, 0Ch
0x18000d739  sub     ax, r10w
0x18000d73d  mov     rcx, r13
0x18000d740  shl     ax, 4
0x18000d744  mov     word ptr [rbp+var_20+2], ax
0x18000d748  lea     rax, [rbp+var_3C]
0x18000d74c  mov     [rsp+70h+var_48], rax
0x18000d751  mov     [rsp+70h+var_50], ebx
0x18000d755  call    WriteGeneric
0x18000d75a  xor     edx, edx
0x18000d75c  movzx   r14d, ax
0x18000d760  test    ax, ax
0x18000d763  jnz     short loc_18000D7C3
0x18000d765  movzx   ecx, [rbp+var_3C]
0x18000d769  add     ecx, ebx
0x18000d76b  cmp     dx, si
0x18000d76e  jnb     short loc_18000D7BC
0x18000d770  mov     ebx, edx
0x18000d772  mov     r15d, ecx
0x18000d775  lea     rax, [rbp+var_3C]
0x18000d779  movzx   edx, bx
0x18000d77c  shl     rdx, 4
0x18000d780  lea     r9, DIRECTORY_CONTROL
0x18000d787  mov     [rsp+70h+var_48], rax
0x18000d78c  add     rdx, rdi
0x18000d78f  mov     [rsp+70h+var_50], ecx
0x18000d793  mov     r8d, 10h
0x18000d799  mov     rcx, r13
0x18000d79c  call    WriteGeneric
0x18000d7a1  movzx   r14d, ax
0x18000d7a5  test    ax, ax
0x18000d7a8  jnz     short loc_18000D7C3
0x18000d7aa  movzx   ecx, [rbp+var_3C]
0x18000d7ae  inc     bx
0x18000d7b1  add     ecx, r15d
0x18000d7b4  mov     r15d, ecx
0x18000d7b7  cmp     bx, si
0x18000d7ba  jb      short loc_18000D775
0x18000d7bc  mov     rax, [rbp+var_30]
0x18000d7c0  mov     [rax], r12d
0x18000d7c3  mov     rcx, rdi
0x18000d7c6  call    Mem_Free
0x18000d7cb  movzx   eax, r14w
0x18000d7cf  jmp     short loc_18000D7DD
0x18000d7d1  mov     eax, 3EEh
0x18000d7d6  jmp     short loc_18000D7DD
0x18000d7d8  mov     eax, 3EDh
0x18000d7dd  mov     rcx, [rbp+var_8]
0x18000d7e1  xor     rcx, rsp; StackCookie
0x18000d7e4  call    __security_check_cookie
0x18000d7e9  mov     rbx, [rsp+70h+arg_10]
0x18000d7f1  add     rsp, 70h
0x18000d7f5  pop     r15
0x18000d7f7  pop     r14
0x18000d7f9  pop     r13
0x18000d7fb  pop     r12
0x18000d7fd  pop     rdi
0x18000d7fe  pop     rsi
0x18000d7ff  pop     rbp
0x18000d800  retn
```
