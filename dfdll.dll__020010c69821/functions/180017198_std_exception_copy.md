# __std_exception_copy

- ea: `0x180017198`
- end: `0x180017225`
- name: `__std_exception_copy`
- size: `141`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18001605c`
- `0x1800160b8`

## callees

- `0x180017198`
- `0x18001844c`
- `0x180018454`
- `0x18001845c`

## pseudocode

```c
void __fastcall _std_exception_copy(__int64 a1, __int64 a2)
{
  __int64 v4; // rdi
  char *v5; // rax
  char *v6; // rbx

  if ( *(_BYTE *)(a1 + 8) && *(_QWORD *)a1 )
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_BYTE *)(*(_QWORD *)a1 + v4) );
    v5 = (char *)malloc(v4 + 1);
    v6 = v5;
    if ( v5 )
    {
      strcpy_s(v5, v4 + 1, *(const char **)a1);
      *(_BYTE *)(a2 + 8) = 1;
      *(_QWORD *)a2 = v6;
      v6 = 0;
    }
    free(v6);
  }
  else
  {
    *(_QWORD *)a2 = *(_QWORD *)a1;
    *(_BYTE *)(a2 + 8) = 0;
  }
}

```

## disassembly

```asm
0x180017198  mov     [rsp+arg_0], rbx
0x18001719d  mov     [rsp+arg_8], rsi
0x1800171a2  mov     [rsp+arg_10], rdi
0x1800171a7  push    r14
0x1800171a9  sub     rsp, 20h
0x1800171ad  cmp     byte ptr [rcx+8], 0
0x1800171b1  mov     r14, rdx
0x1800171b4  mov     rsi, rcx
0x1800171b7  jz      short loc_180017205
0x1800171b9  mov     rax, [rcx]
0x1800171bc  test    rax, rax
0x1800171bf  jz      short loc_180017205
0x1800171c1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800171c5  inc     rdi
0x1800171c8  cmp     byte ptr [rax+rdi], 0
0x1800171cc  jnz     short loc_1800171C5
0x1800171ce  lea     rcx, [rdi+1]; Size
0x1800171d2  call    malloc
0x1800171d7  mov     rbx, rax
0x1800171da  test    rax, rax
0x1800171dd  jz      short loc_1800171FB
0x1800171df  mov     r8, [rsi]; Source
0x1800171e2  lea     rdx, [rdi+1]; SizeInBytes
0x1800171e6  mov     rcx, rax; Destination
0x1800171e9  call    strcpy_s
0x1800171ee  mov     rax, rbx
0x1800171f1  mov     byte ptr [r14+8], 1
0x1800171f6  mov     [r14], rax
0x1800171f9  xor     ebx, ebx
0x1800171fb  mov     rcx, rbx; Block
0x1800171fe  call    free
0x180017203  jmp     short loc_18001720F
0x180017205  mov     rax, [rcx]
0x180017208  mov     [rdx], rax
0x18001720b  mov     byte ptr [rdx+8], 0
0x18001720f  mov     rbx, [rsp+28h+arg_0]
0x180017214  mov     rsi, [rsp+28h+arg_8]
0x180017219  mov     rdi, [rsp+28h+arg_10]
0x18001721e  add     rsp, 20h
0x180017222  pop     r14
0x180017224  retn
```
