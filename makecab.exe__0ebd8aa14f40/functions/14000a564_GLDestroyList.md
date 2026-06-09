# GLDestroyList

- ea: `0x14000a564`
- end: `0x14000a669`
- name: `GLDestroyList`
- size: `261`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x140001de0`
- `0x140003310`
- `0x140003748`
- `0x1400054b0`
- `0x140006a6c`
- `0x14000a800`
- `0x14000c560`

## callees

- `0x14000a564`
- `0x14000a7a4`
- `0x14000f010`

## import_xrefs

- `msvcrt!free` at `0x14000a579`
- `msvcrt!free` at `0x14000a5c5`
- `msvcrt!free` at `0x14000a642`
- `msvcrt!free` at `0x14000a579`
- `msvcrt!free` at `0x14000a5c5`
- `msvcrt!free` at `0x14000a642`
- `msvcrt!free` at `0x14000a662`

## pseudocode

```c
void __fastcall GLDestroyList(_QWORD *a1)
{
  void *v2; // rcx
  _QWORD *v3; // rbx
  __int64 v4; // rdi
  _QWORD *v5; // rbp
  void (__fastcall *v6)(_QWORD); // rax
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  _QWORD *v15; // rax
  _QWORD *v16; // rcx

  v2 = (void *)a1[5];
  if ( v2 )
  {
    free(v2);
    a1[5] = 0;
  }
  v3 = (_QWORD *)*a1;
  if ( *a1 )
  {
    do
    {
      v4 = v3[5];
      v5 = (_QWORD *)v3[3];
      v6 = *(void (__fastcall **)(_QWORD))(v4 + 24);
      if ( v6 )
        v6(v3[1]);
      v7 = v3[3];
      v8 = v7;
      if ( *v3 )
      {
        free((void *)*v3);
        v7 = v3[3];
        v8 = v7;
      }
      v9 = v3[4];
      if ( v9 )
        *(_QWORD *)(v9 + 24) = v7;
      else
        *(_QWORD *)v4 = v8;
      v10 = v3[3];
      v11 = v3[4];
      if ( v10 )
        *(_QWORD *)(v10 + 32) = v11;
      else
        *(_QWORD *)(v4 + 8) = v11;
      if ( *(_QWORD *)(v4 + 40) )
      {
        v12 = hashString(*v3);
        v13 = *(_QWORD *)(v4 + 40);
        v14 = v12;
        v15 = *(_QWORD **)(v13 + 8LL * v12);
        if ( v3 == v15 )
        {
          *(_QWORD *)(v13 + 8 * v14) = v3[2];
        }
        else
        {
          while ( v15 )
          {
            v16 = v15;
            v15 = (_QWORD *)v15[2];
            if ( v15 == v3 )
            {
              v16[2] = v3[2];
              break;
            }
          }
        }
      }
      free(v3);
      --*(_DWORD *)(v4 + 32);
      v3 = v5;
    }
    while ( v5 );
  }
  free(a1);
}

```

## disassembly

```asm
0x14000a564  push    rbx
0x14000a566  push    rbp
0x14000a567  push    rsi
0x14000a568  push    rdi
0x14000a569  sub     rsp, 28h
0x14000a56d  mov     rsi, rcx
0x14000a570  mov     rcx, [rcx+28h]; Block
0x14000a574  test    rcx, rcx
0x14000a577  jz      short loc_14000A587
0x14000a579  call    cs:__imp_free
0x14000a57f  mov     qword ptr [rsi+28h], 0
0x14000a587  mov     rbx, [rsi]
0x14000a58a  test    rbx, rbx
0x14000a58d  jz      loc_14000A657
0x14000a593  mov     rdi, [rbx+28h]
0x14000a597  mov     rbp, [rbx+18h]
0x14000a59b  mov     rax, [rdi+18h]
0x14000a59f  test    rax, rax
0x14000a5a2  jz      short loc_14000A5B6
0x14000a5a4  mov     rcx, [rbx+8]
0x14000a5a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a5ad  mov     rax, [rbx+18h]
0x14000a5b1  mov     rcx, rax
0x14000a5b4  jmp     short loc_14000A5BC
0x14000a5b6  mov     rax, rbp
0x14000a5b9  mov     rcx, rbp
0x14000a5bc  cmp     qword ptr [rbx], 0
0x14000a5c0  jz      short loc_14000A5D2
0x14000a5c2  mov     rcx, [rbx]; Block
0x14000a5c5  call    cs:__imp_free
0x14000a5cb  mov     rax, [rbx+18h]
0x14000a5cf  mov     rcx, rax
0x14000a5d2  mov     rdx, [rbx+20h]
0x14000a5d6  test    rdx, rdx
0x14000a5d9  jnz     short loc_14000A5E0
0x14000a5db  mov     [rdi], rcx
0x14000a5de  jmp     short loc_14000A5E4
0x14000a5e0  mov     [rdx+18h], rax
0x14000a5e4  mov     rcx, [rbx+18h]
0x14000a5e8  mov     rax, [rbx+20h]
0x14000a5ec  test    rcx, rcx
0x14000a5ef  jnz     short loc_14000A5F7
0x14000a5f1  mov     [rdi+8], rax
0x14000a5f5  jmp     short loc_14000A5FB
0x14000a5f7  mov     [rcx+20h], rax
0x14000a5fb  cmp     qword ptr [rdi+28h], 0
0x14000a600  jz      short loc_14000A63F
0x14000a602  mov     rcx, [rbx]
0x14000a605  call    hashString
0x14000a60a  mov     rdx, [rdi+28h]
0x14000a60e  movsxd  rcx, eax
0x14000a611  mov     rax, [rdx+rcx*8]
0x14000a615  cmp     rbx, rax
0x14000a618  jnz     short loc_14000A630
0x14000a61a  mov     rax, [rbx+10h]
0x14000a61e  mov     [rdx+rcx*8], rax
0x14000a622  jmp     short loc_14000A63F
0x14000a624  lea     rcx, [rax]
0x14000a627  mov     rax, [rax+10h]
0x14000a62b  cmp     rax, rbx
0x14000a62e  jz      short loc_14000A637
0x14000a630  test    rax, rax
0x14000a633  jnz     short loc_14000A624
0x14000a635  jmp     short loc_14000A63F
0x14000a637  mov     rax, [rbx+10h]
0x14000a63b  mov     [rcx+10h], rax
0x14000a63f  mov     rcx, rbx; Block
0x14000a642  call    cs:__imp_free
0x14000a648  dec     dword ptr [rdi+20h]
0x14000a64b  mov     rbx, rbp
0x14000a64e  test    rbp, rbp
0x14000a651  jnz     loc_14000A593
0x14000a657  mov     rcx, rsi
0x14000a65a  add     rsp, 28h
0x14000a65e  pop     rdi
0x14000a65f  pop     rsi
0x14000a660  pop     rbp
0x14000a661  pop     rbx
0x14000a662  jmp     cs:__imp_free
```
