# __std_exception_copy

- ea: `0x18001adf0`
- end: `0x18001ae5f`
- name: `__std_exception_copy`
- size: `111`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18001a53c`
- `0x18001a5a8`

## callees

- `0x18001adf0`
- `0x18001b0d0`
- `0x18001b0e0`
- `0x18001b0f0`

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
    v7 = (char *)malloc(v5 + 1);
    v8 = v7;
    if ( v7 )
    {
      strcpy_s(v7, v6, *(const char **)a1);
      *(_QWORD *)a2 = v8;
      *(_BYTE *)(a2 + 8) = 1;
    }
    free(0);
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
0x18001adf0  push    rbx
0x18001adf2  push    rbp
0x18001adf3  push    rsi
0x18001adf4  push    rdi
0x18001adf5  sub     rsp, 28h
0x18001adf9  cmp     byte ptr [rcx+8], 0
0x18001adfd  mov     rdi, rdx
0x18001ae00  mov     rbx, rcx
0x18001ae03  jz      short loc_18001AE4C
0x18001ae05  mov     rcx, [rcx]
0x18001ae08  test    rcx, rcx
0x18001ae0b  jz      short loc_18001AE4C
0x18001ae0d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ae11  inc     rax
0x18001ae14  cmp     byte ptr [rcx+rax], 0
0x18001ae18  jnz     short loc_18001AE11
0x18001ae1a  lea     rbp, [rax+1]
0x18001ae1e  mov     rcx, rbp; Size
0x18001ae21  call    malloc
0x18001ae26  mov     rsi, rax
0x18001ae29  test    rax, rax
0x18001ae2c  jz      short loc_18001AE43
0x18001ae2e  mov     r8, [rbx]; Source
0x18001ae31  mov     rdx, rbp; SizeInBytes
0x18001ae34  mov     rcx, rax; Destination
0x18001ae37  call    strcpy_s
0x18001ae3c  mov     [rdi], rsi
0x18001ae3f  mov     byte ptr [rdi+8], 1
0x18001ae43  xor     ecx, ecx; Block
0x18001ae45  call    free
0x18001ae4a  jmp     short loc_18001AE56
0x18001ae4c  mov     rax, [rbx]
0x18001ae4f  mov     [rdx], rax
0x18001ae52  mov     byte ptr [rdx+8], 0
0x18001ae56  add     rsp, 28h
0x18001ae5a  pop     rdi
0x18001ae5b  pop     rsi
0x18001ae5c  pop     rbp
0x18001ae5d  pop     rbx
0x18001ae5e  retn
```
