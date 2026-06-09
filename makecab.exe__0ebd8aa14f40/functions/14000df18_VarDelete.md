# VarDelete

- ea: `0x14000df18`
- end: `0x14000df87`
- name: `VarDelete`
- size: `111`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400054b0`
- `0x14000df90`

## callees

- `0x14000df18`

## import_xrefs

- `msvcrt!free` at `0x14000df31`
- `msvcrt!free` at `0x14000df40`
- `msvcrt!free` at `0x14000df31`
- `msvcrt!free` at `0x14000df40`
- `msvcrt!free` at `0x14000df80`

## pseudocode

```c
void __fastcall VarDelete(void **a1)
{
  _QWORD *v1; // rdi
  void *v3; // rcx
  void *v4; // rcx
  _QWORD *v5; // rcx
  void *v6; // rax
  _QWORD *v7; // rcx
  void *v8; // rax

  v1 = a1[6];
  v3 = *a1;
  if ( v3 )
    free(v3);
  v4 = a1[1];
  if ( v4 )
    free(v4);
  v5 = a1[5];
  v6 = a1[4];
  if ( v5 )
    v5[4] = v6;
  else
    *v1 = v6;
  v7 = a1[4];
  v8 = a1[5];
  if ( v7 )
    v7[5] = v8;
  else
    v1[1] = v8;
  free(a1);
}

```

## disassembly

```asm
0x14000df18  mov     [rsp+arg_0], rbx
0x14000df1d  push    rdi
0x14000df1e  sub     rsp, 20h
0x14000df22  mov     rdi, [rcx+30h]
0x14000df26  mov     rbx, rcx
0x14000df29  mov     rcx, [rcx]; Block
0x14000df2c  test    rcx, rcx
0x14000df2f  jz      short loc_14000DF37
0x14000df31  call    cs:__imp_free
0x14000df37  mov     rcx, [rbx+8]; Block
0x14000df3b  test    rcx, rcx
0x14000df3e  jz      short loc_14000DF46
0x14000df40  call    cs:__imp_free
0x14000df46  mov     rcx, [rbx+28h]
0x14000df4a  mov     rax, [rbx+20h]
0x14000df4e  test    rcx, rcx
0x14000df51  jnz     short loc_14000DF58
0x14000df53  mov     [rdi], rax
0x14000df56  jmp     short loc_14000DF5C
0x14000df58  mov     [rcx+20h], rax
0x14000df5c  mov     rcx, [rbx+20h]
0x14000df60  mov     rax, [rbx+28h]
0x14000df64  test    rcx, rcx
0x14000df67  jnz     short loc_14000DF6F
0x14000df69  mov     [rdi+8], rax
0x14000df6d  jmp     short loc_14000DF73
0x14000df6f  mov     [rcx+28h], rax
0x14000df73  mov     rcx, rbx
0x14000df76  mov     rbx, [rsp+28h+arg_0]
0x14000df7b  add     rsp, 20h
0x14000df7f  pop     rdi
0x14000df80  jmp     cs:__imp_free
```
