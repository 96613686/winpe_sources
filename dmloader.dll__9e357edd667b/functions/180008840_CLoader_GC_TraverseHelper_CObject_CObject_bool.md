# CLoader::GC_TraverseHelper(CObject *,CObject *,bool)

- ea: `0x180008840`
- end: `0x180008912`
- name: `?GC_TraverseHelper@CLoader@@AEAA_NPEAVCObject@@0_N@Z`
- size: `210`
- prototype: `bool __fastcall(CLoader *__hidden this, struct CObject *, struct CObject *, bool)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800083b0`
- `0x180008840`
- `0x180008918`

## callees

- `0x180008840`

## pseudocode

```c
char __fastcall CLoader::GC_TraverseHelper(CLoader *this, struct CObject *a2, struct CObject *a3, bool a4)
{
  int v7; // r10d
  __int64 v8; // rbx
  unsigned int v9; // r10d
  __int64 v10; // rbp
  __int64 v11; // r14
  unsigned int v12; // r12d
  struct CObject *v13; // rsi

  if ( !a2 )
    return 0;
  v7 = *((_DWORD *)a2 + 48);
  if ( (v7 & 0x1000) == 0 )
    return 0;
  v8 = *((_QWORD *)a2 + 25);
  if ( !v8 || ((*((_DWORD *)a2 + 48) & 0x2000) != 0) == a4 )
    return 0;
  v9 = v7 | 0x2000;
  if ( !a4 )
    v9 = *((_DWORD *)a2 + 48) & 0xFFFFDFFF;
  v10 = 0;
  *((_DWORD *)a2 + 48) = v9;
  v11 = 0;
  v12 = *(_DWORD *)(v8 + 8);
  if ( !v12 )
  {
LABEL_14:
    if ( !a3 )
      *(_DWORD *)(v8 + 8) = v10;
    return 0;
  }
  while ( 1 )
  {
    v13 = *(struct CObject **)(*(_QWORD *)v8 + 8 * v11);
    if ( v13 )
      break;
LABEL_13:
    v11 = (unsigned int)(v11 + 1);
    if ( (unsigned int)v11 >= v12 )
      goto LABEL_14;
  }
  if ( v13 != a3 && !CLoader::GC_TraverseHelper(this, *(struct CObject **)(*(_QWORD *)v8 + 8 * v11), a3, a4) )
  {
    if ( !a3 )
    {
      *(_QWORD *)(*(_QWORD *)v8 + 8 * v10) = v13;
      v10 = (unsigned int)(v10 + 1);
    }
    goto LABEL_13;
  }
  return 1;
}

```

## disassembly

```asm
0x180008840  push    rbx
0x180008842  push    rbp
0x180008843  push    rsi
0x180008844  push    rdi
0x180008845  push    r12
0x180008847  push    r13
0x180008849  push    r14
0x18000884b  push    r15
0x18000884d  sub     rsp, 28h
0x180008851  mov     r15b, r9b
0x180008854  mov     rdi, r8
0x180008857  mov     r13, rcx
0x18000885a  test    rdx, rdx
0x18000885d  jz      loc_1800088FB
0x180008863  mov     r10d, [rdx+0C0h]
0x18000886a  bt      r10d, 0Ch
0x18000886f  jnb     loc_1800088FB
0x180008875  mov     rbx, [rdx+0C8h]
0x18000887c  test    rbx, rbx
0x18000887f  jz      short loc_1800088FB
0x180008881  mov     ecx, r10d
0x180008884  shr     ecx, 0Dh
0x180008887  and     ecx, 1
0x18000888a  cmp     cl, r9b
0x18000888d  jz      short loc_1800088FB
0x18000888f  mov     eax, r10d
0x180008892  bts     r10d, 0Dh
0x180008897  btr     eax, 0Dh
0x18000889b  test    r9b, r9b
0x18000889e  cmovz   r10d, eax
0x1800088a2  xor     ebp, ebp
0x1800088a4  mov     [rdx+0C0h], r10d
0x1800088ab  xor     r14d, r14d
0x1800088ae  mov     r12d, [rbx+8]
0x1800088b2  test    r12d, r12d
0x1800088b5  jz      short loc_1800088F3
0x1800088b7  mov     rax, [rbx]
0x1800088ba  mov     rsi, [rax+r14*8]
0x1800088be  test    rsi, rsi
0x1800088c1  jz      short loc_1800088EB
0x1800088c3  cmp     rsi, rdi
0x1800088c6  jz      short loc_18000890E
0x1800088c8  mov     r9b, r15b; bool
0x1800088cb  mov     r8, rdi; struct CObject *
0x1800088ce  mov     rdx, rsi; struct CObject *
0x1800088d1  mov     rcx, r13; this
0x1800088d4  call    ?GC_TraverseHelper@CLoader@@AEAA_NPEAVCObject@@0_N@Z; CLoader::GC_TraverseHelper(CObject *,CObject *,bool)
0x1800088d9  test    al, al
0x1800088db  jnz     short loc_18000890E
0x1800088dd  test    rdi, rdi
0x1800088e0  jnz     short loc_1800088EB
0x1800088e2  mov     rax, [rbx]
0x1800088e5  mov     [rax+rbp*8], rsi
0x1800088e9  inc     ebp
0x1800088eb  inc     r14d
0x1800088ee  cmp     r14d, r12d
0x1800088f1  jb      short loc_1800088B7
0x1800088f3  test    rdi, rdi
0x1800088f6  jnz     short loc_1800088FB
0x1800088f8  mov     [rbx+8], ebp
0x1800088fb  xor     al, al
0x1800088fd  add     rsp, 28h
0x180008901  pop     r15
0x180008903  pop     r14
0x180008905  pop     r13
0x180008907  pop     r12
0x180008909  pop     rdi
0x18000890a  pop     rsi
0x18000890b  pop     rbp
0x18000890c  pop     rbx
0x18000890d  retn
0x18000890e  mov     al, 1
0x180008910  jmp     short loc_1800088FD
```
