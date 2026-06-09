# GLCopyToList

- ea: `0x14000a3f8`
- end: `0x14000a4ef`
- name: `GLCopyToList`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140005148`

## callees

- `0x1400019d0`
- `0x140008620`
- `0x14000a29c`
- `0x14000a3f8`
- `0x14000a4f8`
- `0x14000a670`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall GLCopyToList(char **a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  char *v7; // rbx
  _QWORD *v8; // rdi
  __int64 v9; // rax
  char *v10; // rax
  char *v11; // rbp
  void (__fastcall *v13)(char *); // rax

  if ( !a2 )
    return 1;
  v7 = a1 ? *a1 : 0LL;
  v8 = *(_QWORD **)a2;
  if ( !*(_QWORD *)a2 )
    return 1;
  while ( 1 )
  {
    if ( !v7 )
    {
      v9 = GLCreateList(*(_QWORD *)(a2 + 16), *(_QWORD *)(a2 + 24), "file parameter", a5);
      v7 = (char *)v9;
      if ( !v9 )
        return 0;
      *a1 = (char *)v9;
    }
    if ( !findItem(*(_QWORD *)v7, *v8) )
    {
      v10 = (char *)DuplicateFileParm(v8[1]);
      v11 = v10;
      if ( !v10 )
      {
        ErrSet(a5, "Out of memory duplicating %1", "%s", "file parameter");
        return 0;
      }
      if ( !GLAdd(*a1, (const char *)*v8, v10, "file parameter", 0, a5) )
        break;
    }
    v8 = (_QWORD *)v8[3];
    if ( !v8 )
      return 1;
  }
  v13 = (void (__fastcall *)(char *))*((_QWORD *)v7 + 3);
  if ( v13 )
    v13(v11);
  return 0;
}

```

## disassembly

```asm
0x14000a3f8  push    rbx
0x14000a3fa  push    rbp
0x14000a3fb  push    rsi
0x14000a3fc  push    rdi
0x14000a3fd  push    r14
0x14000a3ff  push    r15
0x14000a401  sub     rsp, 38h
0x14000a405  mov     r14, rdx
0x14000a408  mov     rsi, rcx
0x14000a40b  test    rdx, rdx
0x14000a40e  jz      loc_14000A4B0
0x14000a414  test    rcx, rcx
0x14000a417  jz      short loc_14000A41E
0x14000a419  mov     rbx, [rcx]
0x14000a41c  jmp     short loc_14000A420
0x14000a41e  xor     ebx, ebx
0x14000a420  mov     rdi, [rdx]
0x14000a423  test    rdi, rdi
0x14000a426  jz      loc_14000A4B0
0x14000a42c  mov     r15, [rsp+68h+arg_20]
0x14000a434  test    rbx, rbx
0x14000a437  jnz     short loc_14000A45F
0x14000a439  mov     rdx, [r14+18h]
0x14000a43d  lea     r8, aFileParameter; "file parameter"
0x14000a444  mov     rcx, [r14+10h]
0x14000a448  mov     r9, r15
0x14000a44b  call    GLCreateList
0x14000a450  mov     rbx, rax
0x14000a453  test    rax, rax
0x14000a456  jz      loc_14000A4EB
0x14000a45c  mov     [rsi], rax
0x14000a45f  mov     rdx, [rdi]
0x14000a462  mov     rcx, [rbx]
0x14000a465  call    findItem
0x14000a46a  test    rax, rax
0x14000a46d  jnz     short loc_14000A4A7
0x14000a46f  mov     rcx, [rdi+8]
0x14000a473  call    DuplicateFileParm
0x14000a478  lea     r9, aFileParameter; "file parameter"
0x14000a47f  mov     rbp, rax
0x14000a482  test    rax, rax
0x14000a485  jz      short loc_14000A4D5
0x14000a487  mov     rdx, [rdi]
0x14000a48a  mov     r8, rax
0x14000a48d  mov     rcx, [rsi]
0x14000a490  mov     [rsp+68h+var_40], r15
0x14000a495  mov     [rsp+68h+var_48], 0
0x14000a49d  call    GLAdd
0x14000a4a2  test    rax, rax
0x14000a4a5  jz      short loc_14000A4C2
0x14000a4a7  mov     rdi, [rdi+18h]
0x14000a4ab  test    rdi, rdi
0x14000a4ae  jnz     short loc_14000A434
0x14000a4b0  mov     eax, 1
0x14000a4b5  add     rsp, 38h
0x14000a4b9  pop     r15
0x14000a4bb  pop     r14
0x14000a4bd  pop     rdi
0x14000a4be  pop     rsi
0x14000a4bf  pop     rbp
0x14000a4c0  pop     rbx
0x14000a4c1  retn
0x14000a4c2  mov     rax, [rbx+18h]
0x14000a4c6  test    rax, rax
0x14000a4c9  jz      short loc_14000A4EB
0x14000a4cb  mov     rcx, rbp
0x14000a4ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a4d3  jmp     short loc_14000A4EB
0x14000a4d5  lea     r8, aS_4; "%s"
0x14000a4dc  mov     rcx, r15
0x14000a4df  lea     rdx, aOutOfMemoryDup; "Out of memory duplicating %1"
0x14000a4e6  call    ErrSet
0x14000a4eb  xor     eax, eax
0x14000a4ed  jmp     short loc_14000A4B5
```
