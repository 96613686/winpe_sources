# ETWP_BUFFER_QUEUE::Pop(void)

- ea: `0x1800104c0`
- end: `0x18001054d`
- name: `?Pop@ETWP_BUFFER_QUEUE@@QEAAPEBU_WMI_BUFFER_HEADER@@XZ`
- size: `141`
- prototype: `const struct _WMI_BUFFER_HEADER *__fastcall(ETWP_BUFFER_QUEUE *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000416c`
- `0x18000f384`
- `0x18000f90c`

## callees

- `0x1800104c0`
- `0x180015840`

## pseudocode

```c
const struct _WMI_BUFFER_HEADER *__fastcall ETWP_BUFFER_QUEUE::Pop(ETWP_BUFFER_QUEUE *this)
{
  __int64 v1; // rax
  char *v3; // rcx
  unsigned __int64 v4; // rdx
  __int64 v5; // rsi
  unsigned __int64 v6; // rax
  __int64 v7; // rdi
  char *v8; // rdx

  v1 = *((_QWORD *)this + 3);
  v3 = *(char **)this;
  v4 = v1 + 1;
  v5 = *(_QWORD *)&v3[8 * v1];
  *((_QWORD *)this + 3) = v1 + 1;
  v6 = (__int64)(*((_QWORD *)this + 1) - (_QWORD)v3) >> 3;
  if ( v6 == v4 || v4 > 0x40 && v4 > v6 >> 1 )
  {
    v7 = 8 * v4;
    v8 = &v3[8 * v4];
    if ( v3 != v8 )
    {
      memmove_0(v3, v8, (*((_QWORD *)this + 1) - (_QWORD)v8) & 0xFFFFFFFFFFFFFFF8uLL);
      *((_QWORD *)this + 1) += -8 * (v7 >> 3);
    }
    *((_QWORD *)this + 3) = 0;
  }
  return (const struct _WMI_BUFFER_HEADER *)v5;
}

```

## disassembly

```asm
0x1800104c0  mov     [rsp+arg_0], rbx
0x1800104c5  mov     [rsp+arg_8], rsi
0x1800104ca  push    rdi
0x1800104cb  sub     rsp, 20h
0x1800104cf  mov     rax, [rcx+18h]
0x1800104d3  mov     rbx, rcx
0x1800104d6  mov     rcx, [rcx]; void *
0x1800104d9  lea     rdx, [rax+1]
0x1800104dd  mov     rsi, [rcx+rax*8]
0x1800104e1  mov     [rbx+18h], rdx
0x1800104e5  mov     r8, [rbx+8]
0x1800104e9  mov     rax, r8
0x1800104ec  sub     rax, rcx
0x1800104ef  sar     rax, 3
0x1800104f3  cmp     rax, rdx
0x1800104f6  jz      short loc_180010506
0x1800104f8  cmp     rdx, 40h ; '@'
0x1800104fc  jbe     short loc_18001053A
0x1800104fe  shr     rax, 1
0x180010501  cmp     rdx, rax
0x180010504  jbe     short loc_18001053A
0x180010506  lea     rdi, ds:0[rdx*8]
0x18001050e  lea     rdx, [rdi+rcx]; Src
0x180010512  cmp     rcx, rdx
0x180010515  jz      short loc_180010532
0x180010517  sub     r8, rdx
0x18001051a  and     r8, 0FFFFFFFFFFFFFFF8h; Size
0x18001051e  call    memmove_0
0x180010523  sar     rdi, 3
0x180010527  neg     rdi
0x18001052a  shl     rdi, 3
0x18001052e  add     [rbx+8], rdi
0x180010532  mov     qword ptr [rbx+18h], 0
0x18001053a  mov     rbx, [rsp+28h+arg_0]
0x18001053f  mov     rax, rsi
0x180010542  mov     rsi, [rsp+28h+arg_8]
0x180010547  add     rsp, 20h
0x18001054b  pop     rdi
0x18001054c  retn
```
