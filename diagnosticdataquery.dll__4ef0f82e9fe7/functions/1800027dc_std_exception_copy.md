# __std_exception_copy

- ea: `0x1800027dc`
- end: `0x18000284b`
- name: `__std_exception_copy`
- size: `111`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180001e1c`
- `0x180001e88`
- `0x180004270`
- `0x180005cb8`
- `0x180005dcc`

## callees

- `0x1800027dc`
- `0x18000513a`
- `0x180005146`
- `0x18000515e`

## pseudocode

```c
void __fastcall _std_exception_copy(__int64 a1, __int64 a2)
{
  const char *v4; // rcx
  __int64 v5; // rax
  rsize_t v6; // rbp
  char *v7; // rax
  char *v8; // rsi

  if ( *(_BYTE *)(a1 + 8) && (v4 = *(const char **)a1) != 0 )
  {
    v5 = -1;
    do
      ++v5;
    while ( v4[v5] );
    v6 = v5 + 1;
    v7 = (char *)malloc_0(v5 + 1);
    v8 = v7;
    if ( v7 )
    {
      strcpy_s_0(v7, v6, *(const char **)a1);
      *(_QWORD *)a2 = v8;
      *(_BYTE *)(a2 + 8) = 1;
    }
    free_0(0);
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
0x1800027dc  push    rbx
0x1800027de  push    rbp
0x1800027df  push    rsi
0x1800027e0  push    rdi
0x1800027e1  sub     rsp, 28h
0x1800027e5  cmp     byte ptr [rcx+8], 0
0x1800027e9  mov     rdi, rdx
0x1800027ec  mov     rbx, rcx
0x1800027ef  jz      short loc_180002838
0x1800027f1  mov     rcx, [rcx]
0x1800027f4  test    rcx, rcx
0x1800027f7  jz      short loc_180002838
0x1800027f9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800027fd  inc     rax
0x180002800  cmp     byte ptr [rcx+rax], 0
0x180002804  jnz     short loc_1800027FD
0x180002806  lea     rbp, [rax+1]
0x18000280a  mov     rcx, rbp; Size
0x18000280d  call    malloc_0
0x180002812  mov     rsi, rax
0x180002815  test    rax, rax
0x180002818  jz      short loc_18000282F
0x18000281a  mov     r8, [rbx]; Source
0x18000281d  mov     rdx, rbp; SizeInBytes
0x180002820  mov     rcx, rax; Destination
0x180002823  call    strcpy_s_0
0x180002828  mov     [rdi], rsi
0x18000282b  mov     byte ptr [rdi+8], 1
0x18000282f  xor     ecx, ecx; Block
0x180002831  call    free_0
0x180002836  jmp     short loc_180002842
0x180002838  mov     rax, [rbx]
0x18000283b  mov     [rdx], rax
0x18000283e  mov     byte ptr [rdx+8], 0
0x180002842  add     rsp, 28h
0x180002846  pop     rdi
0x180002847  pop     rsi
0x180002848  pop     rbp
0x180002849  pop     rbx
0x18000284a  retn
```
